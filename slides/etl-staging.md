##  ETL: Staging

It should be possible to restart some of the ETL phases independently from the others.
If the transformation step fails, it should not be necessary to restart the Extract step.

We can ensure this by implementing proper *Staging*.

**Staging** means that the data is simply dumped to a location called the *Staging Area* so that it can then be read by the next processing phase.

The staging area is also used during ETL process to store intermediate results of processing. The staging area may therefore contain incomplete or in-the-middle-of-the-processing data and should be accessed by the load ETL process only. It should never be available to anyone else, especially not to end users as it is not intended for data presentation to the end-user.
