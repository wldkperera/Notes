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























