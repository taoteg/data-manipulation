##  ETL vs ELT

Instead of transforming the data before it’s written, ELT leverages the target system to do the transformation. The data is copied to the target and then transformed in place.

ELT makes sense when the target is a high-end data engine, such as a data appliance, Hadoop cluster, or cloud installation.

ELT has no transformation engine – the work is done by the target system.

The ETL approach can provide drastically better performance under certain scenarios.

The training and development costs of ETL need to be weighed against the need for better performance.

Additionally, if you don’t have a target system powerful enough for ELT, ETL may be more economical as well.
