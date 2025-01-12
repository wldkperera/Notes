# Azure Synapse Analytics

1. Descriptive - What is happening?
3. Diagnostic - Why is it happning?
4. Predictive - What is likely to happen?
5. Prescriptive - What should I do?

![image](https://github.com/user-attachments/assets/88b9ef39-7a33-49c5-a24f-0d1309685993)

### When to use synapse

1. modern data warehousing,
2. advanced analytics, \
3. data exploration and discovery,
4. real-time analytics - synapse link, stream analytics, data explorer
5. data integration,
6. integrated analytics.

![image](https://github.com/user-attachments/assets/68384d7c-0c4f-4315-b059-f189489a6ba6)

### Data Virtualization

allows you to interact with data without the need to understand how the data is formatted, structured, or what the data type is. 

### ad hoc

unlock insights from their own data stores without going through the formal processes of setting up a data warehouse.

## Spark Pools

spark pool clusters are group of computeres working as a singke computer and handle the execution of commands issued from notebooks.
clusters allow procssing of data accrosss many comouters to improve scale and performance.
cluster consist of spark driver and worker nodes.
The driver node sends work to the worker nodes and instructs them to pull data from a specified data source.

Benefits - speed and efficiency, ease of creation, ease of use, and scalability.
spark instance begins - 60 nides < 2 mins, 60 nods >  5 mins
shuts down after 5 mins of inactivity

creeate  pool - Azure portal, power shell, synapse .NET SDK

You can pass the data through to the Spark cluster to perform the calculation and then pass the process data back into the data warehouse or back to the data lake. 

Anaconda libraries pre-installed.


![image](https://github.com/user-attachments/assets/d12def90-44b5-4696-9e8b-52a8c8202a89)


the execution of a stored procedure Hive query or Pig script to transform the data, and pushing data into a machine learning model to perform analysis.

multiple activities can be logically grouped together with an object referred to as a pipeline.

Control flow is an orchestration of pipeline activities that include cheating activities in a sequence, branching and defining parameters at a pipeline level, and passing arguments while invoking the pipeline on-demand or from a trigger.


**Built in pool** - best used when you need predictable performance and cost.
**Dedicatd pool** - ideal for unplanned or ad hoc workloads that the diagnostic analytics approach would generate. It works best when performing data exploration or preparing data for data virtualization.


### paramters

![image](https://github.com/user-attachments/assets/cd866c88-8b16-42f1-a8b3-363b61341e3e)


Parameters are key value pairs of read-only configuration. 

The arguments for the defined parameters are passed during execution from the run context that was created by a trigger or a pipeline that was executed manually. Finally, activities within the pipeline consumed the parameter values.

# Synapse Link

Azure Synapse Link for Azure Cosmos DB is a cloud-native hybrid transactional and analytical processing (HTAP) capability. 

It enables you to run near real-time analytics over operational data in Azure Cosmos DB without impacting the performance of transactional workloads on Azure Cosmos DB.


**Understand hybrid transactional analytical processing with Azure Synapse Link**

Hybrid Transactional and Analytical Processing (HTAP) allows businesses to conduct analytics on transactional databases without compromising performance. Tailwind Traders utilizes Azure Cosmos DB for storing eCommerce user profiles, benefiting from its NoSQL capabilities and SQL syntax compatibility. However, they face cost concerns with executing analytical queries across multiple partitions. To address this, they enable Azure Synapse Link, which integrates Azure Cosmos DB with Azure Synapse Analytics, allowing for real-time analytics without impacting transactional workloads. This setup eliminates the need for ETL processes, enabling data professionals to run analytics and machine learning pipelines efficiently. The process includes creating a new container with an analytical store to optimize data handling and performance.

With Azure Synapse Link enabled, and the analytical store provision, you are then able to query the analytical store directly from Azure Synapse Analytics, or create a pipeline to copy the contents of the analytical store.


**Data Warehousing** - The goal of data warehousing is to create a database of historical data that can be retrieved and analyzed to provide useful insight into the organization's operations.


Data in a data warehouse is stored in permanent tables that are populated using an extract, transform, and load (ETL) process by services such as Azure Synapse pipelines, or Azure Data Factory. 

As a result, you need to understand the data that is stored in the sources systems and how it should arrive within the data warehouse. This in turn dictates how you should cleanse or transform the data.



# Synapse pages

## 1. Data Hub

   The Data hub is where you access your provisioned SQL pool databases and SQL serverless databases in your workspace, as well as external data sources, such as storage accounts and other linked services.

   The tables listed under the SQL pool store data from multiple sources, such as SAP Hana, Twitter, Azure SQL Database, and external files copied over from an orchestration pipeline. Synapse Analytics gives us the ability to combine these data sources for analytics and reporting, all in one location.
   

**Linked tab** - Azure data lake gen 2 (primary storage)


  The file explorer capabilities allow you to quickly find files and perform actions on them, like preview file contents, generate new SQL scripts or notebooks to access the file, create a new data flow or dataset, and manage the file.


## 2. Develop hub

manage SQL scripts, Synapse notebooks, data flows, and Power BI reports.

SQL scripts - T SQL
Notebooks - Spark poools as compute targets
data flows - use apachee spark but are authored using a code - free GUI
Power BI - mbeddd dashboards


## 3. Intgrate

manage pipelines, 


## 4. Monitor hub

View pipelines and trigger runs
view running IR
Spark pool, SQL requests and flow debug activities


**Pipeline** runs shows all pipeline run activities. view run details, including inputs and outputs for the activities, and any error messages occurred. stop a pipeline, if needed.

**Trigger runs** shows you all pipeline runs caused by automated triggers. You can create triggers that run on a recurring schedule or tumbling window. You can also create event-based triggers that execute a pipeline any time a blob is created or deleted in a storage container.

**Integration runtimes** shows the status of all self-hosted and Azure integration runtimes.

**Apache Spark applications** shows all the Spark applications that are running or have run in your workspace.

**SQL requests** shows all SQL scripts executed either directly by you or another user, or executed in other ways, like from a pipeline run.

**Data flow** debug shows active and previous debug sessions. When you author a data flow, you can enable the debugger and execute the data flow without needing to add it to a pipeline and trigger an execute. Using the debugger speeds up and simplifies the development process. Since the debugger requires an active Spark cluster, it can take a few minutes after you enable the debugger before you can use it.


## 5. Manage hub

**SQL pools**. Lists the provisioned SQL pools and on-demand SQL serverless pools for the workspace. You can add new pools or hover over a SQL pool to pause or scale it. You should pause a SQL pool when it's not being used to save costs.

**Apache Spark pools** Lets you manage your Spark pools by configuring the auto-pause and auto-scale settings. You can provision a new Apache Spark pool from this blade.

**Linked services** Enables you to manage connections to external resources. Here you can see linked services for our data lake storage account, Azure Key Vault, Power BI, and Synapse Analytics. Task: Select + New to show how many types of linked services you can add.

**Azure Purview (Preview)** Provides integration with Azure Purview to provide data governance and lineage within Azure Synapse Analytics.

**Triggers** Provides you a central location to create or remove pipeline triggers. Alternatively, you can add triggers from the pipeline.

**Integration runtimes** Lists the IR for the workspace, which serves as the compute infrastructure for data integration capabilities, like those provided by pipelines. Task: Hover over the integration runtimes to show the monitoring, code, and delete (if applicable) links. Click on a code link to show how you can modify the parameters in JSON format, including the TTL (time to live) setting for the IR.

**Access control** This is where you go to add and remove users to one of three security groups: workspace admin, SQL admin, and Apache Spark for Azure Synapse Analytics admin.

**Credentials** Contains objects that hold authentication information that can be used by Azure Synapse Analytics.

**Managed private endpoints** This is where you manage private endpoints, which use a private IP address from within a virtual network to connect to an Azure service or your own private link service. Connections using private endpoints listed here provide access to Synapse workspace endpoints (SQL, SqlOndemand and Dev).

**Workspace packages** Workspace packages can be custom code or a specific version of an open-source library that you would like to use in your Apache Spark pools held in the Azure Synapse Analytics Workspace.

**Git configuration** Enables you to connect your workspace to a Git repository to enable source control.




# Data Warehouses

 let you bring together all ur data at any scale eeasily.
 Synapse can store a wide variety of data in its raw format, making the process of ingesting data into a data warehouse much easier.
 
![image](https://github.com/user-attachments/assets/08e82ae2-91ce-4a42-9106-cdc3bda886b4)


1. data warhous's hierarchical namespace organizes files into a hierarchy of directories for efficient access and more granular security, down to the file-level.
2. ADLS Gen2 provides virtually limitless scale for your data lake. You can attach additional ADLS Gen2 accounts for greater scale and flexibility as needed.


## Data Ingstion

data flows are powerful data transformation workflows that use the power of Apache Spark, but are authored using a code-free GUI. The work you do in the UI gets transformed into code executed by a managed Spark cluster, automatically, without having to write any code or manage the cluster.


# Data storage for noder5n data ware houses

1. Although you can ingest data at the source directly into a data warehouse, it is more typical to store the source data within a staging area = landing zone.
2. a neutral storage area that sits between the source systems and the data warehouse.

![image](https://github.com/user-attachments/assets/42e413a5-9191-41c4-a32c-b65e7c94e1f7)


#### why staging area at modern datawarehouses

1. To reduce contention on source systems. - Grab data >> dumping to stage area
2. To deal with the ingestion of source systems on different schedules. - handle different schedules
3. To join data together from different source systems. - Mapping tables
4. To rerun failed data warehouse loads from a staging area. - 


Data lake - unstructured (bolbs)


# File format and structure for a modern data warehouse


### 3 latencies of daata loading velocity

1. Batch interactive query -  querying batch data at human interactive speeds which with the current generation of technologies means results are ready in time frames measured in seconds to minutes.

  1.1  initial data wrangling
  1.2 complete GTL pipeline
  1.3 preparation for downstream analytics

2. real-time - live data
3. near real time - loive data (seconds, mili)


# Data storage formats

1. CSV - store raw data, don't store metadata
2. JSON - Web APIs and NoSQL
3. Parquet - cleaned and filtered data

  Skipping unwanted columns - column pruning
  Stored metadata


**With a hierarchical name space enabled, a storage account becomes capable of providing the scalability and cost effectiveness of object storage.**

**ADLS Gen2, it is a best practice to have a dedicated storage account for production, and a separate storage account for dev and test workloads. This will ensure that dev or test workloads never interfere with production.**


### Seperate foldes by the deegre of refinement

1. bronze folder might contain raw data.
2. Silver contains the cleaned, prepared, and integrated data
3. Gold contains data ready to support analytics, which might include final refinements, such as pre-computed aggregates.


**When data is stored in data lake storage Gen2,**

1. the file size,
2. number of files, and
3. folder structure have an impact on performance.

And if you store your data as many small files, this can negatively affect performance. 

In general, organize your data into larger sized files for better performance, 256 megabytes, 200 gigbytes in size. 

Some engines and applications might have trouble efficiently processing files that are greater than 100 gigabytes in size. 








