Azure offers 4 scalable objects
1. Blob - Text and Binary data
2. Azure files - managed file shares for cloud or on premises deployment.
3. Azure queue - message store for reliable messaging between application components
4. Azure tables - no schema storag for structured data

# Blob

cheep, images, 
REST API, many languages

# Data lake

big data, peta bytes, 
unlimited scalability
Hadoop compatible
Zone redundant scirity

**In Data Lake Storage Gen 1, data engineers query data by using the U-SQL language. In Gen 2, use the Azure Blob Storage API or the 
Azure Data Lake System, ADLS, API. Because Data Lake Storage supports Azure Active Directory ACLs, security administrators can control 
data access by using the familiar active directory security groups**

# Cosmos DB

globaly distributed multi model database. u can dploy it by using several API models. 

sequel API, MongoDB API, Cassandra API, Gremlin API, Table API - multi mod architecture

### you can use MongoDB for semi structured data, 
### Cassandra for white columns or 
### Gremlin for graph databases.

Azure Cosmos DB is guaranteed to achieve a response time of less than 10 milliseconds for reads and writes

# azur SQL db

Managed relational db service
supports relational and unstructured formats

## key fatures

1. SQL database delivers predictable performance for multiple resource types, service tiers, and compute sizes.
2. Requiring almost no administration, it provides dynamic scalability with no downtime, built in intelligent optimization, global         
   scalability and availability, and advanced security options.


# Azure Synapse Analytics

1. Eng load data easily with PolyBase
2. It removes complexity of the data
3. They take advantage of techniques for big data ingestion and processing by offloading complex calculations to the Cloud.
4. developers use PolyBase to apply stored procedures, labels, views, and SQL to their applications.
5. You can use Azure Data Factory to ingest and process data using PolyBase tool.

**Azure Synapse Analytics supports both SQL Server Authentication and Azure Active Directory**













