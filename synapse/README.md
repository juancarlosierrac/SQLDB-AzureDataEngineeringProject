# Azure Synapse Pipeline - Create SQL Serverless Views  

---

## Architecture  
<div align="center">
    <img src="https://raw.githubusercontent.com/juancarlosierrac/SQLDB-AzureDataEngineeringProject/main/images/Synapse_Data_Pipeline.png" width="1000px"/>
</div>  

---

## Process Flow  
This Azure Synapse pipeline automates the creation of SQL Serverless Views in the `gold_db` database.  

### Steps:
1. **Get Metadata Activity** 
   - Retrieves all table names from the `gold_db` database.  

2. **ForEach Activity**  
   - Iterates over each table name and executes a **Stored Procedure** to create a SQL Serverless View.

3. **Stored Procedure Execution**  
   - The stored procedure `CreateSQLServerlessView_gold` dynamically generates views based on the table names.  
   - Each view points to the corresponding Delta table stored in Azure Data Lake Storage Gen2 (`gold` layer).

---

## Stored Procedure  
The stored procedure used in this pipeline is located in the repository:  

📂 **[sql/sp_CreateSQLServerlessView_gold.sql](https://github.com/juancarlosierrac/SQLDB-AzureDataEngineeringProject/blob/main/sql/sp_CreateSQLServerlessView_gold.sql)**  

This procedure dynamically creates views for each table in gold_db.
