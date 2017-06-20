##  Extract, Transform & Load (ETL)

Extract-Transform-Load (ETL) refers to the process of transferring data in bulk from one system to another. ETL systems extract and transform large volumes of source data into a new dataset, and then load that data into a new data store, for subsequent querying.

<!--
Extract, Transform and Load tools and frameworks are meant to handle the initial stages of data processing:

  * Ingest data from many sources
  * Perform some basic operations on the data
  * Save the data to a final target datastore
-->

ETL sounds like three distinct phases but in fact the phases overlap and it’s not necessarily a serial process. The ‘users’ of ETL systems are always other software systems or people involved in data analysis, rather than interactive customers or end-users.

Compared to transactional systems, ETL systems do not have an ongoing ‘live’ state. Instead they typically operate on a data load cycle that might be daily, weekly, or monthly, usually containing a ‘critical’ period where data must be loaded within a specific timeframe in order to meet internal or external deadlines.
