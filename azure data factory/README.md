# Azure Data Factory Pipeline - AdventureWorks Data

---

## Architecture  
<div align="center">
    <img src="https://raw.githubusercontent.com/juancarlosierrac/SQLDB-AzureDataEngineeringProject/main/images/Azure%20Data%20Factory%20PL.png" width="1000px"/>
</div>  

---

## Process Flow  
1. **ForEach Activity**: Iterates through all tables under the `SalesLT` schema in the AdventureWorks database.
2. **Copy Data Activity**: Transfers the tables from Azure SQL Database to Azure Data Lake Storage Gen2 in `.parquet` format.
3. **Databricks Notebook Execution (Bronze to Silver)**: A Databricks notebook processes raw data, applies necessary transformations, and saves it to the Silver layer in Delta format.
4. **Databricks Notebook Execution (Silver to Gold)**: Another Databricks notebook further refines the data, applying aggregations and business logic before saving it to the Gold layer.

<div align="center">
<img src="https://raw.githubusercontent.com/juancarlosierrac/SQLDB-AzureDataEngineeringProject/main/images/Bronze_Data.png" width="1000px"/>
</div>