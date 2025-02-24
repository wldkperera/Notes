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

# 1. Self hosted Intgration runtime

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

### Creat SHIR

1. Select Manage in the leftmost pane, and select Integration runtimes. Select +New.
2. On the Integration runtime setup page, select Azure, Self-Hosted, and then select Continue.
3. On the Integration runtime setup page, type in a name of MySelfHostedIR, and click Create
4. Copy and paste the authentication key. Select Download and install integration runtime.
5. Download the self-hosted integration runtime on a local Windows machine. Run the installer.
6. On the New Integration Runtime (Self-hosted) Node page, select Finish.
7. After the self-hosted integration runtime is registered successfully, you see the following window:
Create 9



# 2. Azure integration runtime

1. Running Data Flows in Azure
2. Running Copy Activity between cloud data stores
3. Dispatching the following transform activities in public network

You can set a certain location of an Azure IR, in which case the data movement or activity dispatch will happen in that specific region. If you choose to use the auto-resolve Azure IR which is the default, ADF will make a best effort to automatically detect your sink and source data store to choose the best location either in the same region if available or the closest one in the same geography for the Copy Activity. For anything else, it will use the IR in the Data Factory region. Azure Integration Runtime also has support for virtual networks.

### Create Azur IR

1. Select Integration runtimes on the left pane, and then select +New.
2. On the Integration runtime setup page, select Azure IR, and then select Continue.
3. You'll see a pop-up notification when the creation completes. On the Integration runtimes page, make sure that you see the newly created IR in the list.

## data ingestion security considerations

 To restrict access, you should configure a Network Security Group or NSG.
 NSG is automatically created by Azure Data Factory, and Port 3389 is open. 
 Port 3389 is used for Remote Desktop Protocol or RDP.
 Lock this port down to ensure that only your administrators have access.

Azure Security Center integrated threat intelligence to deny communications with known malicious or unused Internet IP addresses.
Azure Firewall with threat intelligence can be used to control network access.


#### you can use Azure Monitor to centralize the storage of ingestion logs that are generated by Azure Data Factory and query them using Log Analytics.


# ADF transformation methods

1. Mapping - clenssing , transformation, aggregation
   Apache Spark clusters that are automatically provisioned when executed
   
2. compute resources
3. SSIS package

### ADF provides the ability to lift and shift existing SSIS workload by creating an Azure SSIS integration runtime to natively execute SSIS packages.

SSIS IR will enable you to deploy and manage your existing SSIS packages with little to no change using familiar tools such as SQL Server Data Tools or SSDT and SQL Server Management Studio, SSMS. Just like using SSIS on-premises.


# Azure Data Factory transformation types

Mapping Data Flows provides a number of different transformation types that enable you to modify data. They are broken down into the following categories:

![image](https://github.com/user-attachments/assets/77dda028-cef6-4625-9be7-cc15ac9599a0)

Transformations available in the mapping data flows

![image](https://github.com/user-attachments/assets/b8918e22-a48f-44b3-8721-c4e634bd2f17)
![image](https://github.com/user-attachments/assets/c0ad0b96-d0e1-469c-b143-4f63819aa766)

# data Flow Expression Builder

customize the functionality of a transformation using columns, fields, variables, parameters, functions from your data flow in these boxes.


# Data Flow

data flows will run on your own execution cluster for scaled-out data processing
Debug mode = interactive spark cluster


### Data flow transformation

1. Select transformation to rename and drop a column
2. Filter Transformation to filter out unwanted years
3. Derive Transformation to calculate primary genre
4. Rank via a Window Transformation
5. Aggregate ratings with an Aggregate Transformation
6. Specify Upsert condition via an Alter Row Transformation - specify insert, delete, update, upsert



## Note

1. If your dataset is pointing at a folder with other files and you only want to use one file, you may need to create another dataset or utilize parameterization to make sure only a specific file is read
2. If the schema in ADLS haven't imported yet, dataset >> schema >> import schema

### following datasets can be used in a source transformation

1. Azure Blob Storage (JSON, Avro, Text, Parquet)
2. Azure Data Lake Storage Gen1 (JSON, Avro, Text, Parquet)
3. Azure Data Lake Storage Gen2 (JSON, Avro, Text, Parquet)
4. Azure Synapse Analytics
5. Azure SQL Database
6. Azure CosmosDB

** Integration runtime has 8 cores in it.**

# How Integrate SQL server integration services packages within Azure Data Factory

https://www.coursera.org/learn/azure-data-factory-data-integration/supplement/2VK3A/integrate-sql-server-integration-services-packages-within-azure-data-factory


## ADF can also call on compute resources to transform data by a data platform service that may be better suited to the job.

![image](https://github.com/user-attachments/assets/92d084bb-00c2-4d44-93fc-2df6c513db64)




Slowly Changing Dimensions - SCD

SCD - tables in a dimensional model that handle changs to dimension values over time.

mapping data flow, that can incrementally update a slowly changing dimension table in a dedicated SQL pool

SCD is applies when the values of a business entity change over time and not on a set schedule. 

The most common are type 1 and type 2.

1. Type 1 - always show the latest values. when changes in source data are detected, the dimension table data is overwritten. automatically linked to updateed row.

2. Type 2 - supports versioning of dimension members. Often the source system doesn't store versions, so the data warehouse load, process, detects, and manages changes in a dimension table. 

when a change happen in type 2 member, create a new row with appropiate startdate and endDate. 

use a surrogate key to provide a unique reference to a version of the dimension member.

3. Type 3 - SCD supports storing two versions of a dimension member as separate columns. use additional column.
The table includes a column for the current value of a member plus either the original or previous value of the member. So, Type 3 uses additional columns to track one key instance of history, rather than storing additional rows to track each change like in a Type 2 SCD.

4. Type 6 - combination of 1, 2,3. design you also store the current value in all versions of that entity so you can easily report on the current value or the historical value.



# Control Flow

orchestrating data movement and transforming data at scale

1. control flow is an orchestration of pipeline activities.
2. That orchestration includes chaining activities in a sequence, branching, defining parameters at the pipeline level, and passing arguments while invoking the pipeline on demand or from a trigger.
3. Control flow can also include looping containers that can pass information for each iteration of the looping container. 

branching activity - if statement

# ADF Triggers

1. Schedule - invokes a pipeline on a wall clock shcedule
2. Tumbling window - trigger that operates on a periodic interval while also retaining state.
3. Event based - trigger rhat rspond to an event
   
# Activitiees in ADF

1. data movment - from source >> destination
2. Data transformation - Spark, flows, azure functions that can be added to pipelines individually or chained with anothr activity
3. Control - activity depndncy defines how subsquent activity dpnds on previous activity

# Depndeciews

1. succeed
2. skipped
3. failed
4. compleetion


# ADF connectors that can parameterize

![image](https://github.com/user-attachments/assets/baed432b-3694-4919-9f20-a431c9bdb1e4)

**When u integratee global parameteers in pipeline using CI/CD with ADF:**
1. Includ global parameters in ARM templatee - **benificial** 
2. Deploy global parameeters via a power shell script 


# Azure Synapse

## Integrate a Notebook within Azure Synapse Pipelines
https://www.coursera.org/learn/azure-data-factory-data-integration/supplement/jP5MF/exercise-integrate-a-notebook-within-azure-synapse-pipelines


1. Azure Data factory enables you to execute packages for SSIS
2. with ADF, you can provision SSIS, Integration Runtime, IR.

### Connect to a Git repository

https://www.coursera.org/learn/azure-data-factory-data-integration/supplement/wlUKA/connect-to-a-git-repository


### CI/ CD

https://www.coursera.org/learn/azure-data-factory-data-integration/supplement/4DDjW/continuous-integration-and-deployment


### Monitor Azure Data Factory pipelines

https://www.coursera.org/learn/azure-data-factory-data-integration/supplement/SQ5hF/monitor-azure-data-factory-pipelines


### Set up alerts for Azure Data Factory

https://www.coursera.org/learn/azure-data-factory-data-integration/supplement/P9KuU/set-up-alerts-for-azure-data-factory



# Git and ADF

for version controling
![image](https://github.com/user-attachments/assets/dacb2060-d23c-4797-9cac-6210522f4568)

1. ability to track and audit changes 
2. ability to revert changes that introduced bugs.


## Share and receive data using Azure Data Share and transform data using Azure Data Factory
https://www.coursera.org/learn/azure-data-factory-data-integration/supplement/YZ88l/exercise-share-and-receive-data-using-azure-data-share-and-transform-data-using


**Mapping flow can used to combine two tabbles**


## How to Sink dataset into Azure Synapse Analytics with Azure Data Factory
https://www.coursera.org/learn/azure-data-factory-data-integration/supplement/QFnQj/exercise-sink-dataset-into-azure-synapse-analytics-with-azure-data-factory


**Monitor tab stores run informations of pipeline for 45 days by default**


Data professionals - ETL
dveelopers - ELT


