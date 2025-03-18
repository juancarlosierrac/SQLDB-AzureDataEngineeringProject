# Azure Data Factory Pipeline - SQLDB to Azure Data Lake

---

## Architecture  
<div align="center">
    <img src="https://raw.githubusercontent.com/juancarlosierrac/SQLDB-AzureDataEngineeringProject/main/images/Azure%20Data%20Factory%20PL.png" width="1200px"/>
</div>  

---

## Process Flow  
1. **Dataset Configuration**: A dataset was created to dynamically extract tables from the `SalesLT` schema in **Azure SQL Database**.
2. **ForEach Activity**: Iterates through all tables in the `SalesLT` schema, automatically configuring the source dataset.
3. **Copy Data Activity**: Transfers data from Azure SQL Database to an **Azure Data Lake Storage Gen2** container named `Bronze`, storing the data in `.parquet` format.
4. **Dynamic Table Selection**: Using a parameterized approach, the pipeline dynamically sets the schema and table names during execution.

<div align="center">
    <img src="https://raw.githubusercontent.com/juancarlosierrac/SQLDB-AzureDataEngineeringProject/main/images/Bronze_Data.png" width="1200px"/>
</div>  
