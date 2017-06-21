##  ETL Transform Script (Python 2009)


```

# 7/28/2009 - Ryan Robitaille (http://ryrobes.com/)
# An easy Python DTS / ETL "package" script | Reading data from one source (Oracle) and writing it to another (MS SQL or Oracle)
# Please let me comments / fixes / changes on this post (http://ryrobes.com/featured-articles/using-a-simple-python-script-for-end-to-end-data-transformation-and-etl-part-1/)

# DataSource:	Random Data generated from Oracle's DBMS_RANDOM.x functions (just as an example)

# Destination:	Very basic table on MSSQL and Oracle (see below - create statement should work on both platforms)
#		CREATE TABLE test --just a test destination table
#		(field1 VARCHAR(50), field2 VARCHAR(50),
#		field3 INT, field4 VARCHAR(50))


# First we need to import all the modules we will be using - for now its only 3 easy ones
import string, pymssql, cx_Oracle

## Define Oracle connection - format ("username/password@TNSNAME")
ora_conn = cx_Oracle.connect("xxxx/xxxx@XXXXX")      

## Define the Oracle cursor objects
ora_cursor = ora_conn.cursor()		#Allocate a cursor to that particular database connection

## Define the MSSQL server connection - format is self-explanitory
mssql_conn = pymssql.connect(host='xxxxx', user='rrobitaille', password='xxxxx', database='XXXXXX')

## Define the MSSQL cursor objects
mssql_cursor = mssql_conn.cursor()	#Allocate a cursor to that particular database connection


## Truncate our destination tables
ora_cursor.execute("truncate table test")
mssql_cursor.execute("truncate table test")



## Fetch our source rows into a cursor
## (this is just using a simple function to randomly generate a bunch of garbage strings for now)
ora_cursor.execute("""SELECT DBMS_RANDOM.STRING('P',40) field1,
DBMS_RANDOM.STRING('X',30) field2, ROUND(DBMS_RANDOM.VALUE(1000, 9999)) field3,
DBMS_RANDOM.STRING('A',20) field4  FROM DUAL CONNECT BY LEVEL<=3000""")

ResultSet_Py_List = []  #Create an empty list, then and populate it with cursor results (below)
# Basically we're looping through the now-loaded cursor, pulling out the results and appending them into a Python "List" object
# Why? Well because this makes the inserts MUCH easier to deal with AND if we needed to do any data transformation - its easier.
for field1, field2, field3, field4 in ora_cursor:
   try:
     ResultSet_Py_List.append((field1, field2, field3, field4))
   except AttributeError: #if we run out of rows - which we will evevntually, we don't want the interpreter to freak out
     pass

# just do a quick count of the list we created to make sure that we've got all our rows
print str(len(ResultSet_Py_List)) + ' Records SELECTED from Source (into list ready for insertion)'

# For the Oracle insert we need to do a "prepare" with the paramatized SQL and then an "executemany" with the actual list
# Notice we're re-using the cursor from before since we don't need it anymore - all the values have be put in the ResultSet_Py_List list object
ora_cursor.prepare("""INSERT INTO test (field1, field2, field3, field4)
			VALUES (:field1, :field2, :field3, :field4)""")
ora_cursor.executemany(None, ResultSet_Py_List)
ora_conn.commit() #COMMIT that shit before that data gets away!


#insert statement with bind variables
mssql_cursor.executemany("INSERT INTO test (field1, field2, field3, field4) VALUES (%s, %s, %s, %s)", ResultSet_Py_List)
mssql_conn.commit() #COMMIT that shit before that data gets away!



#ora_cursor.execute("select count(*) from test")
#for row in ora_cursor:
#   print str(row).replace("(","").replace(")","").replace(","," ") + 'Records INSERTED into Oracle TEST table'

ora_cursor.execute("select count(*) from test")
ora_row_count = ora_cursor.fetchone()
print str(ora_row_count[0]) + ' Records INSERTED into Oracle TEST table'

mssql_cursor.execute("select count(*) from rrobitaille.test")
mssql_row_count = mssql_cursor.fetchone()
print str(mssql_row_count[0]) + ' Records INSERTED into MSSQL TEST table'

## All done, Lars. Now lets get a drink.

## We will even be nice and close the connections.
##       Its like tipping your hat to the Database engine.
mssql_conn.close()
ora_conn.close()
```
