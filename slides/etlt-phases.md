##  ETLT Phases

**ET Phase:** In this arrangement, the ETL tool is responsible for extracting and consolidating data from the source systems,  performing scalar data cleansing, and formatting the change data to look much like the target tables. At this point the “ET” phase data is loaded into the staging area of the data warehouse appliance.  The loading operation is often performed by an appliance high speed loader.

<!-- Some ETL tools can leverage the appliance high speed loader through ODBC/JDBC or platform-specific connectors.  If not, the ETL tool creates flat files for loading. -->

**LT Phase:**  Once that data is loaded into the appliance, the remaining “LT” transformation is completed using SQL-based set level operations. The *ETLT Framework Manager* handles end-to-end control including task dependencies, data archiving, restart/recovery, error-handling and event logging.
