##  ETLT

Data warehouse loader utilities have become so fast that it is practical to move data into the data warehouse at an early point in the data transformation process.  Consequently, the performance bottleneck is shifting from the data warehouse to the ETL servers.

The idea behind *ETLT* (extract,  format transformation, load, referential transformation) is to combine ETL and ELT to exploit the strengths of each approach to achieve optimum performance and scalability. The goal is to move certain transformation processing onto the data warehouse platform to take advantage of the inherent parallelism and the relational integration of data.

**ET Phase:** In this arrangement, the ETL tool is responsible for extracting and consolidating data from the source systems,  performing scalar data cleansing, and formatting the change data to look much like the target tables. At this point the “ET” phase data is loaded into the staging area of the data warehouse appliance.  The loading operation is performed by the appliance high speed loader.

<!-- Some ETL tools can leverage the appliance high speed loader through ODBC/JDBC or platform-specific connectors.  If not, the ETL tool creates flat files for loading. -->

**LT Phase:**  Once that data is loaded into the appliance, the remaining “LT” transformation is completed using SQL-based set level operations. The *ETLT Framework Manager* handles end-to-end control including task dependencies, data archiving, restart/recovery, error-handling and event logging.
