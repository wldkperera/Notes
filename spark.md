earlier, we used RDD(resilient distributed dataframes) to store data.
Now, using dataframes and datasets.

# dataFrames

offers query optimization via catalyst
whole stage code gneration with DMA - Direct memoty access

# datasets

good in complex ETL pipelines
query optimization through catalyst
dvelpper friendly

# Parquet with snappy compression -  default in Spark version 2

stores data in columner format
It is compressed and highly optimized in Apache Spark and it is splittable to decompress

# caching

there is a native built-in Apache Spark caching mechanism.
Caching might be most effective when using small datasets. 
It might also come in handy when working with ETL pipelines where caching of intermediate results is necessary.

# memory efficiency

1. One way to manage memory resources might be to check smaller data partitions along with data size, types and 
   distributions when formulating a partitioning strategy.
2. **kryo data serialization** 

Kryo is a significantly optimized serializer, and performs better than the standard java serializer for just about 
everything. 
3. kep monitor and tune apache spark configurations.

# Bucketing 

almost similar to data partitioning
main difference is bucket holds a set of column values instead of one.
It might work well when you partition on large values like product identifiers on the scale of millions or even more

bucketing doesn't exclude partitioning. They go hand in hand so you can use partitioning and bucketing at the same time.
Joins and shuffles are the key

# Data Skew - reason to delay joins and shuffls

Data skew is data that is stored asymmetrically on your system.

Fix data skew, 
      1. you can sort the entire key or use an isolated salt for only some subset of keys.
      2. introduce a bucket column or pre aggregated data in buckets.

# SortMerge join type - apache

for big data, computationally xpensive

# When running concurrnt queries

Start with 30 gigabytes per executer, along with all Machine cores, create multiple parallel Apache Spark applications by 
over subscribing CPU around 30 percent latency improvement.

Distribute queries across parallel applications and modify size based on both trial runs and the preceding factors, 
such as GC overhead.

# Automate scaling of Apache Spark pools in Azure Synapse Analytics

![image](https://github.com/user-attachments/assets/4c40f012-3db7-4796-a041-0b42cf95ad50)

## the autoscale functionality will issue a scale request based on the metrics outlined in the table below:

![image](https://github.com/user-attachments/assets/bc9b8ef1-d2ec-4dc0-b225-9ee043eaa997)













