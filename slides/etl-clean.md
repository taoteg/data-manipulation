##  ETL: Clean

The cleaning step is one of the most important as it ensures the quality of the data in the data warehouse.

Cleaning should perform basic data unification rules such as:

* Identify and remove duplicates
* Convert numbers to a consistent representation
* Convert dates and times to a consistent representation
* Remove case sensitivity, or make it consistent throughout
* Normalize spelling for a given dictionary or term
* Making identifiers unique
* Convert null values into a standardized value
* Validate address fields, convert them into proper naming, e.g. Street/St/St./Str./Str
* Validate address fields against each other (State/Country, City/State, City/ZIP code, City/Street)
