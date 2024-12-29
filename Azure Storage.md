Azure offers 4 scalable objects
1. Blob - Text and Binary data
2. Azure files - managed file shares for cloud or on premises deployment.
3. Azure queue - message store for reliable messaging between application components
4. Azure tables - no schema storag for structured data

# 1. Blob

cheep, images, 
REST API, many languages

Blob storage is ideal for serving images or documents directly to a browser, including full static websites, storing files for distributed access, streaming video and audio, storing data for backup and restoration.

# Types of Blobs

1. ### Block Blobs
   texts, binary files up to 5TB, 50000 blocks of 100 MB in size. media files or image files for websites.
   files larger than 100 megabytes must be uploaded a small blocks. These blocks are then consolidated or committed into the final blob. 

   
3. ### Page blobs
   hold random access files up to 8 TB
   used primarily as the backing storage for the virtual hard disks or VHDs used to provide durable discs for Azure virtual machines or Azure VMs.
   provide random read write access to 512-byte pages.
   
   
5. ### Append blobs
   made up of blobs like block blobs, but optimized in appeand operation.
   frequently used for logging information from one or more sources into the same blob
   A single append blob can be up to 195 gigabyte.
   
   eg:  write all your trace logging to the same append blob for an application running on multiple VMs.
   

# 2. Azure Files

1. enables you to set up highly available network file shares that can be accessed using the standard server message block or SMB protocol. This means that multiple VMs can share the same files with both read and write access.
2. You can also read the files using the REST interface and the storage client libraries.
3. Finally, you can also associate a unique URL to any file to allow fine grained access to a private file for a set period.
4. File shares can be used for many common scenarios, storing shared configuration files for VMs, tools or utilities so that everyone is using the same version. 

## Use cases

1. storing shared configuration files for VMs, tools or utilities so that everyone is using the same version.
2. Log files such as diagnostics, metrics and crash dumps and shared data between on premises applications and Azure VMs to allow migration of apps to the cloud over a period.

# Azure Queue - store and retrieve messages

1. Queue messages can be up to 64 kilobytes in size and a queue can contain millions of messages.
2. Finally, queue are used to store lists of messages to be processed asynchronously.
3. You can use queue to loosely connect different parts of your application together.

### eg: we could perform image processing on the photos uploaded by our users. Perhaps we want to provide some sort of face detection or tagging capability so people can search through all the images they have stored in our service. And we could use queues to pass messages to our image processing service to let it know that new images have been uploaded and are ready for processing.

## Storage types

1. ### Standard General Purpose v2 - blobs, file shares, queues and tables, it is recommended from most scenarios using Azure storage.
2. ### premium blok blobs - block blobs and a pen blobs.
   recommended for scenarios with high transaction rates, scenarios that use smaller objects or those that require consistently low storage latency.
4. ### Premium files shares account -  file shares only.
   It is recommended for enterprise or high performance scale applications. This is useful if you require both SMB and NFS, file share support.
5. ### Premium page blobs


















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


# IoT hub

1. IoT hub is the cloud gateway that connects IoT devices.
2. Features in Azure IoT hub enrich the relationship between your devices and your back end systems.


# Azure event hubs 

1. Azure event hubs provide big data streaming service.
2. It's designed for high data throughput allowing customers to send billions of requests per day.
3. event hubs uses a partitioned consumer model to scale out Azure data stream.

# HD Insights

1. low cost cloud solution
2. supports batch processing, data warehousing, IoT and data S.
3. includes apache Hive, HBase, Spark and Kafka

**Hadoop stores data in a file system or HDFS, and Spark stores data in memory**

# HBase

1. HBase is a NoSQL database built on Hadoop.
2. It's commonly used for search engines.
3. HBase offers automatic failover


# Kafka

!. Kafka is an open source platform that's used to compose data pipelines.
2. It offers message queue functionality which allows users to publish or subscribe to real-time data streams.

# Storm

1. Storm is a distributed real-time streamlining analytic solution.
2. It supports common programming languages like Java, C-sharp and Python. 



**Single subscriptiopn can hold 200 storage account, each can have 500 TB data.**

# **Storagee APIs**

Azure storage provides a Rest API to work with the containers and data stored in each account. There are independent APIs available to work with each type of data you can store.

1. Blobs
2. Queues
3. Tables
4. Files

# client library

1. Client libraries can save a significant amount of work for app developers because the API is tested, and it often provides nicer wrappers around the data model sent and received by the Rest API.\
2. .Net, Java, Python, Node.js, and Go can used

## connect to azure storage account

To work with data in a storage account, your app will need two pieces of data; 1. access key and 
                                                                               2. REST API endpoint.

**Access keys are the easiest approach to authenticating access to a storage account**

**Storage accounts offer a separate authentication mechanism called shared access signatures that support exploration and limited permissions for scenarios where you need to grant limited access**

# When Regenerating Access keys, The proper sequence to prevent downtime is 

1. Update the connection strings in your application code to reference the secondary access key of the storage account.

2. Regenerate the primary access key for your storage account using the Azure portal or command line tool.

3. Update the connection strings in your code to reference the new primary access key.

4. Finally, regenerate the secondary access key in the same manner.



# **Azure storage security features**

all the data in azure storage enncrypted using 256-bit cypher and decrypt happening automatically.

**CORS support** is an optional flag you can enable on storage accounts. The flag as the appropriate headers when you use http get requests to retrieve resources from the storage account. 

### RBAC or role based access control

1. most flexible principle
2. RBAC roles that are scoped to a subscription, a resource group, a storage account and an individual container or queue. 

**You can use Active Directory to authorize resource management operations, such as configuration.**
**Active Directory is supported for data operations on Blob and Queue storage.**

### Auditing

1. Auditing is another part of controlling access.
2. You can audit Azure storage access by using the built in storage analytics service.
3. Storage analytics, logs every operation in real time. And you can search the storage analytics logs for specific requests.

**Microsoft Azure Storage accounts can create authorized apps in Active Directory to control access to the data in blobs and queues. For other storage models, clients can use a shared key, or shared secret.**

## threat protection and learn how to control network access

untrusted clients - used Shared Access Signaturee (SAS)

1. service level SAS - allow access to specific resources in a storage account and retrieve a list of files in a file system or to download a file.
2. account level SAS - allow access to anything that a service level SAS can allow plus additional resources and abilities

Accounts that store user data have to typical designs, a 
1. front-end proxy service - upload and download data through a front end proxy service which performs authentication
2. lightweight or SAS provider service - authenticates the client as needed, access dirctly via genrated SAS

## Advanced threat protection

1. Security alerts are triggered when anomalies in activity occur
2. securuity defernder should enable
   
available for Azure Data Lake Storage Gen 2, Blob Storage, File storage  

![image](https://github.com/user-attachments/assets/9eb423bd-331d-404b-a0e4-bb4467d3552e)



# **Blob Storage** - Binary large objects

1. Blobs give you file storage in the cloud and an API that lets you build apps to access the data
2. Blobs are files for the Cloud
3. is unstructured
4. Blob could contain gigabytes of binary data streamed from a scientific instrument, an encrypted message for another application, or data in a custom format for an app you're developing
5. not appropriate for structured data that needs to be queried frequently
6. They have higher latency than memory and local disk and don't have the indexing features that make databases efficient at running queries.
7. Ideal for storing up to 8 TB data for VMs, storing data for analysis by an On-premises or Azure hosting service, storing data for backup and restore disaster recovery and archiving, Streaming video and audio, storing files for distributed access, and serving images or documents directly to a browser
8. Blob Storage does not provide any mechanism for searching or sorting Blobs by metadata.
9. The Blob Storage API is REST-based and supported by client libraries in many popular languages

### Block blobs

best choice, fast download and uploads
![image](https://github.com/user-attachments/assets/f459d804-723a-401c-9a1b-31be786e61c7)

### append blobs

![image](https://github.com/user-attachments/assets/20124f31-4d29-4b2c-94f8-7b0b1ec8d07e)

### Page blobs

![image](https://github.com/user-attachments/assets/8e88911f-23a1-4c07-a3d2-3f3b1cd8c97f)

**Every blob lives inside a blob container. You can store an unlimited number of blobs in a container and an unlimited number of containers in a storage account.**













