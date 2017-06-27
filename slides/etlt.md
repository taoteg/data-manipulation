##  ETLT

Data warehouse loader utilities have become so fast that it is practical to move data into the data warehouse at an early point in the data transformation process.  Consequently, the performance bottleneck is shifting from the data warehouse to the ETL servers.

The idea behind *ETLT* (extract,  format transformation, load, referential transformation) is to combine ETL and ELT to exploit the strengths of each approach to achieve optimum performance and scalability. The goal is to move certain transformation processing onto the data warehouse platform to take advantage of the inherent parallelism and the relational integration of data.
