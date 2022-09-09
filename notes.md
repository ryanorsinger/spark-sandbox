## Anatomy of Spark
- The Spark Driver (yoru laptop running pyspark)
- The Cluster Manager
- Exectors on each node ()

## 2 Kinds of DataFrame Manipulation
- **Transformations** are lazy computations/functions 
- **Actions** are when we apply a specified action like .show or count rows

## Spark in Practice
- We chain our transformations.
- Many transformations

## Shuffling
- The Shuffle is an expensive operation since it involves disk I/O, data serialization, and network I/O. 
- A shuffle is a transformation requiring looking at data in another partition or executor
- arithmetic does not require a shuffle, because the process is parallelized
- calculating the average of the dataframe does require a shuffle, because we need data from all partitions
- shuffles increase computational complexity

## Operations that *might* cause a shuffle
- cogroup
- groupWith
- join: hash partition
- leftOuterJoin: hash partition
- rightOuterJoin: hash partition
- groupByKey: hash partition
- reduceByKey: hash partition
- combineByKey: hash partition
- sortByKey: range partition
- distinct
- intersection: hash partition
- repartition
- coalesce