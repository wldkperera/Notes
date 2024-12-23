# Azure Synapse

Apache Spark is a parallel processing framework that supports in-memory processing to boost the performance of big data analytics applications. 
Apache Spark core engine resources are managed by Yarn.

Spark pools in Azure Synapse Analytics are compatible with Azure Storage and Azure Data Lake Generation 2 Storage. 

## Directed acylic graph (DAG)
nodes are used to read and write data from and to the file system. 
Spark context also converts applications to a DAG, the graph executes individual tasks within an executor process on the nodes. To manage DAG processes, create an Apache Spark pool in Azure Synapse Analytics.

![image](https://github.com/user-attachments/assets/e9a480eb-ba99-4388-a81b-94b7e7e78a29)

## Apache Spark pools in Azure Synapse Analytics:
Apache Spark pools in Azure Synapse Analytics has Apache Spark capabilities embedded. For organizations that don’t have existing Apache Spark implementations yet, Apache Spark pools in Azure Synapse Analytics provide the functionality to spin up an Apache Spark cluster to meet data engineering needs without the overhead of the other Apache Spark platforms. 

Data engineers, data scientist, data platform experts, and data analyst can come together within Azure Synapse Analytics where the Apache Spark cluster is running to quickly collaborate on various analytical solutions.

## Apache Spark for Azure Synapse:
Apache Spark is an open-source, memory-optimized system for managing big data workloads, It is used when you require a Spark engine for big data processing or data science, and you don’t mind that there is no service level agreement provided to keep the services running. 

Usually it is of interest of open-source professionals. The reason for Apache Spark is to overcome the limitations of what was known as SMP systems for big data workloads.

## Azure HDInsight (HDI):
HDI is an implementation by Microsoft of open-source Apache Spark, managed on the Azure Platform. You can use HDI for an Apache Spark environment when you are aware of the benefits of Apache Spark in its OSS form, but you want a Service Level Agreement (SLA). 

This implementation is usually of interest to open-source professionals who required an SLA, and data platform experts experienced with Microsoft products and services.

## Azure Databricks:
Azure Databricks is a managed Apache Spark-as-a-Service propriety solution that provides an end-to-end data engineering/data science platform. Azure Databricks is of interest for many data engineers and data scientists working on big data projects today. It provides the platform in which you can create and manage the big data/data science projects all on one platform.

These services are not mutually exclusive. It is common to find customers who use a combination of these technologies working together.


# Magic commands

![image](https://github.com/user-attachments/assets/0ca4c5f0-9034-4f08-b064-9404aa68cb0c)

## Working with Different Languages in Azure Synapse Studio

If you need to work with multiple languages in notebooks,

1. create a temp table using scala
2. acces the dataframe in PySpark
3. Use the df in SQL

# Why use temporary table?

**Cross language compatibilty** - tmp tabls allow u to share data between diffrent languages in the same notbook.

# supported languages

Scala
pySpark
.Net
Spark SQL


# Introduction to DataFrames in Spark pools in Azure Synapse Analytics

you can load data into an Apache Spark DataFrame from different file types stored in an Azure Storage Account, or from data stored in a dedicated SQL pool.

If you would like to load data to or from a table into a Spark DataFrame, you can use the Azure Synapse Apache Spark pool to Synapse SQL connector.

The Azure Synapse Apache Spark pool to Synapse SQL connector is a data source implementation for Apache Spark, and it uses Azure Data Lake Storage Generation 2 and PolyBase, and dedicated SQL pools to efficiently transfer data between the Spark cluster and the Azure Synapse dedicated SQL pool instance.

![image](https://github.com/user-attachments/assets/71486a3d-1983-4629-8bd4-e4a535f25006)


## common issues that data engineers encounter \

Complex data types are increasingly common and represent a challenge for data engineers because analyzing nested schema and data arrays often include time-consuming and complex SQL queries. It can be difficult to rename or casts the nested column datatype.

Performance issues can also arise when working with deeply nested objects. 

-- SOLUTION

**With Azure Synapse Apache Spark pools it's easy to transform nested structures into columns and array elements into multiple rows**

Azure Synapse Apache Spark pools makes it easy for developers to transform nested structures into columns and array elements into multiple rows.






















