# Activities

Copy, Dataflow, Look up, Get Metadata, and Delete 

# Formats

avro, Binary, Dlimited, JSON, ORC, Parquate

# copy data

1. Source
2. New dataset
![image](https://github.com/user-attachments/assets/17376894-ee11-4597-9c0e-2cd450ccd57e)

select format

3. Sink
4. Select the Azure Data lake Storage Gen2 tile and click continue.
   ![image](https://github.com/user-attachments/assets/d165cb5f-6682-4040-aaf3-26d2b0665c37)


1. In Data Factory, an activity defines the action to be performed.
2. A linked service defines a target data store or a compute service.
3. An integration runtime provides the bridge between the activity and linked services.

# Self hosted Intgration runtime

1. Running copy activity between a cloud data store and a data store in the private network.
2. Dispatching the following transform activities against compute resources in on-premises or Azure Virtual Network:

HDInsight Hive activity (BYOC-Bring Your Own Cluster)

HDInsight Pig activity (BYOC)

HDInsight MapReduce activity (BYOC)

HDInsight Spark activity (BYOC)

HDInsight Streaming activity (BYOC)

Machine Learning Batch Execution activity

Machine Learning Update Resource activities

Stored Procedure activity

Data Lake Analytics U-SQL activity

Custom activity (runs on Azure Batch)

Lookup activity

Get Metadata activity

**Note**
The self-hosted integration runtime is logically registered to the Azure Data Factory and the compute resource used to support its function as provided by you. Therefore there is no explicit location property for self-hosted IR. When used to perform data movement, the self-hosted IR extracts data from the source and writes it into the destination.






































