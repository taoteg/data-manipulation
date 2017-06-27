##  ETL: Load

During the load step, it is necessary to ensure that the load is performed correctly and with as little resources as possible.

The target of the Load process is often a database or data warehouse.

In order to make the load process efficient, it is helpful to disable any constraints and indexes before the load and enable them back only after the load completes.

The referential integrity needs to be maintained by the ETL tools to ensure consistency.
