<properties
   pageTitle="Use Redgate's Data Platform Studio to load data into SQL Data Warehouse | Microsoft Azure"
   description="Learn how to use Redgate's Data Platform Studio for data warehousing scenarios."
   services="sql-data-warehouse"
   documentationCenter="NA"
   authors="mausher"
   manager="barbkess"
   editor=""/>

<tags
   ms.service="sql-data-warehouse"
   ms.devlang="NA"
   ms.topic="get-started-article"
   ms.tgt_pltfrm="NA"
   ms.workload="data-services"
   ms.date="09/28/2016"
   ms.author="mausher;barbkess;sonyama"/>


# Load data with Redgate Data Platform Studio

> [AZURE.SELECTOR]
- [Redgate](sql-data-warehouse-load-with-redgate.md)
- [Data Factory](sql-data-warehouse-get-started-load-with-azure-data-factory.md)
- [PolyBase](sql-data-warehouse-get-started-load-with-polybase.md)
- [BCP](sql-data-warehouse-load-with-bcp.md)



[Redgate](http://www.red-gate.com/) software is a long-time Microsoft partner that delivers a variety of SQL Server tools. Redgate’s [Data Platform Studio (DPS)](https://www.dataplatformstudio.com/) provides a simple and reliable way to migrate on-premises SQL Server databases to Azure SQL Data Warehouse. DPS automates the data upload and applies the most appropriate compatibility fixes and optimizations. It reduces the time frame for a first data migration from days to hours, giving companies an easy way to explore the potential of the SQL Data Warehouse.

Data Platform Studio utilizes PolyBase to parallelize the data load for optimal performance. 

## Prerequisites

To step through this tutorial, you need:

- A SQL Data Warehouse database
- A SQL Server database
- A web browswer

## Import data into SQL Data Warehouse

In this tutorial, you will connect to an existing SQL Server database and import data into a new table in Azure SQL Data Warehouse.

### Step 1: Navigate to the Data Platform Studio site

Open your web browser and navigate to the the [Data Platform Studio](https://www.dataplatformstudio.com/) website. 

> [AZURE.NOTE] If this is your first time using DPS, you will need to create a user account and sign in. 

### Step 2: Start the Import Wizard
From the DPS main screen, select the **Import to Azure SQL Data Warehouse** link to start the import process. 
![Import Wizard][1]

### Step 3: Install the Redgate Gateway and choose a connection
In order to connect to your on premise SQL Server database, you will need to install the Data Platform Gateway. The Gateway is a client agent that you must install in your on-premises environment to copy data between cloud and on-premises data stores.

To install the Gateway:

1. Click the **Create Gateway** link
2. Download and install the Gateway using the provided installer

Once installed, select the compute you installed the Gateway on from the drop down and select **Next**.

![Gateway][2]

> [AZURE.NOTE] Before proceeding, please ensure that the **Status** is **Connected**.

### Step 4: Enter the name of your on premise SQL Server
In the *Enter Server Name* textbox, enter the name of the server that hosts your database and select **Next**.

### Step 5: Select a database
From the drop down, select the database you would like to import data from.

![Select Database][3]

Once you've selected a database, DPS will inspect that database for tables to import. By default, DPS will select all of the tables in the database. You can select or deselect tables by expanding the *All Tables* link. Select the **Next** button to move forward.

![All Tables][4] 

### Step 6: Choose a storage account to stage the data
DPS will prompt you for a location to store the data in Azure Blob Storage to stage the data. You can choose an existing storage account from your subscription or create a new storage account and then select **Next**.

![Storage][5]

### Step 7: Select a data warehouse
Next, you'll select an [Azure SQL Data Warehouse](http://aka.ms/sqldw) database to import the data into. Once you've selected your database, you will need to enter the credentials to connect to the databae and select **Next**.

![Data Warehouse][6]

### Step 8: Import the data
DPS will confirm that you would like to import the data. Simply click the **Start Import** button to begin the data import

![Start Import][7]

### Step 9: Monitor the import
DPS will display a visualization that shows the progress of exporting the data from the on premise SQL Server, the upload to Azure Blob Storage, and the import into Azure SQL Data Warehouse. 

![Monitor][8]

## Next steps
For an overview of loading, see [Load data into SQL Data Warehouse][].
For more development tips, see [SQL Data Warehouse development overview][].

<!--Image references-->
[1]: media/sql-data-warehouse-redgate/importwizard.png
[2]: media/sql-data-warehouse-redgate/gatewaylink.png
[3]: media/sql-data-warehouse-redgate/selectdatabase.png
[4]: media/sql-data-warehouse-redgate/alltables.png
[5]: media/sql-data-warehouse-redgate/storage.png
[6]: media/sql-data-warehouse-redgate/datawarehouse.png
[7]: media/sql-data-warehouse-redgate/import.png
[8]: media/sql-data-warehouse-redgate/monitor.png

<!--Article references-->

[Load data into SQL Data Warehouse]: ./sql-data-warehouse-overview-load.md
[SQL Data Warehouse development overview]: ./sql-data-warehouse-overview-develop.md