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


















