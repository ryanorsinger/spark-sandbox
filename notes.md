## Anatomy of Spark
- The Spark Driver (yoru laptop running pyspark)
- The Cluster Manager
- Exectors on each node

## 2 Kinds of DataFrame Manipulation
- transformations are lazy computations/functions 
- actions are when we apply a specified action like .show or count rows

## Shuffling
- A shuffle is a transformation requiring looking at data in another partition or executor
- arithmetic does not require a shuffle, because the process is parallelized
- calculating the average of the dataframe does require a shuffle, because we need data from all partitions
- shuffles increase computational complexity
