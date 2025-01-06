
# SSIS - SQL seerver integration service

![image](https://github.com/user-attachments/assets/b278ad04-7265-477a-b750-a4e33d949768)

ETL solutions for on-prem data warahouses, analytical solutions, migration projects, automateed projects

1. SSIS, is a platform for building complex, extract, transform, and load, or ETL Solutions.
2. SSIS is a component within SQL Server and consists of a Windows service that manages the execution of ETL workflows, along with several tools and components for developing those workflows.
3. SSIS is typically used to develop data integration pipelines for On-premises data warehousing solutions.
4. It can also be used to create data migration pipelines when migrating data between different systems.
5. SSIS Is primarily a control flow engine that manages the execution of workflows.
6. Task workflows reffered as control flows >> includes one or more tasks which manages oprations such as data flows.
7. workflow of tasks in SSIS package = control flow


## Azure SSIS Integration Runtime

SSIS locaion doesn't need to be the same as ADF location. 
Should be Azure SQL DB or Azure SQL server managed instance server, where SSIS DB is to be hosted (easy access/ no traffic)

During the provisioning of SSIS IR, specify:

1. Node size - no. cores and no. nodes in the cluster
2. Azure SQL DB - existing instance of db to host the SSIS catalog db or SSIS db and service tier for db.
3. max parallel xecution per node.

With SSIS IR enabled manage, monitor, schedule: SSIS package using SSMS or SQL server data tools.


## Setup an Azure-SSIS Integration Runtime

https://www.coursera.org/learn/azure-data-factory-data-integration/supplement/76K08/example-setup-an-azure-ssis-integration-runtime

## Run SSIS packages in Azure Data Factory

https://www.coursera.org/learn/azure-data-factory-data-integration/supplement/y80mn/example-run-ssis-packages-in-azure-data-factory

## Migrate SSIS packages to Azure Data Factory

https://www.coursera.org/learn/azure-data-factory-data-integration/supplement/OQu8H/example-migrate-ssis-packages-to-azure-data-factory




