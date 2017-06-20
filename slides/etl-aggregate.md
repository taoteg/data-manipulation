##  ETL: Aggregate

> The single most dramatic way to affect performance in a large data warehouse is to provide a proper set of aggregate (summary) records that coexist with the primary base records. Aggregates can have a very significant effect on performance, in some cases speeding queries by a factor of one hundred or even one thousand. No other means exist to harvest such spectacular gains. **~ Ralph Kimball**

An aggregate (in its simplest form) is a summary table that can be derived by performing a Group by SQL query. A more common use of aggregates is to take a dimension and change the granularity of this dimension.

Aggregates are sometimes referred to as pre-calculated summary data, since aggregations are usually precomputed, partially summarized data, that are stored in new aggregated tables.
