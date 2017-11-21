####

RDD resilient distributed dataset
sc.parallelize(seq)
sc.textFile("textfile.txt") external datastorage
can read from database too.

[](Transformation functions)
  filter and map
  build a new RDD
  lazy evaluation only when action is enforced.

new SparkConf().setAppName("name")
        .setMaster("local[2]")  - 2 cores
        .setMaster("local[x]")  - All available cores
        .setMaster("local")  - single core

  set function on two RDD[T]

  - Union
  - Intersection
  - Subtract
  - Cartesian product

[](Action functions)  

    will enforce transformation on RDD

  - collect - brings data locally to driver.
  - count (size of items) and countbyValue (map of uniques values and occurrence)
  - take  - take n elements from an RDD
  - saveAsTextFile  - write data to filesystem, hdfs,s3
  - reduce

[](RDD)
  RDD - are broken in to multiple pieces called partitions and these partitions are divided across the clusters. cluster -> n nodes.   
  immutable
  resilient - can be recreated from data at any time. fault tolerant.

[](Persistence and cache)
  multiple action on RDD is expensive.
  persist - StorageLevel MEMORY_ONLY OR MEMORY_ONLY_SER

![  Spark architecture (from https://intellipaat.com/tutorial/spark-tutorial/spark-architecture/)](https://cdn.intellipaat.com/mediaFiles/2017/02/three-ways-Apache-Spark.jpg)

[](Spark Components)
- Spark core

- Spark SQL

- Spark Streaming

- Mlib

- GraphX
