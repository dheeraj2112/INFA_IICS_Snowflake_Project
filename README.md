#Sample_Datawarehouse_Project

1) Project Overview

The goal of a data warehouse project is to consolidate data from various sources into a centralized repository for analysis and reporting. This enhances decision-making capabilities by providing a holistic view of the organization's data.

2) Source and Target 

Source: Source is Oracle on-prem HR schema. The script can be used to generate that data set, if not available handy. https://github.com/dheeraj2112/INFA_IICS_Snowflake_Project/blob/a69bf3a16396e40a7a6fa0aedafebf485ddfecd8/HR%20Objects%20and%20Data%20For%20Live%20SQL.sql

Target: Target is Snowflake having both EDW_STG and EDW Layers. The DDLs can be found in the repo. https://github.com/dheeraj2112/INFA_IICS_Snowflake_Project/blob/a69bf3a16396e40a7a6fa0aedafebf485ddfecd8/IICS_ORA_SNFLK_EDW_DDL.sql

3) ETL/ELT Data Flows


Source (Oracle) to Stg(Snowflake) : Using SCD Type-1

Stg (Snowflake) to EDW(Snowflake) : Using SCD Type-2

Optinal: EDW_STG to EDW data flow can be implemented using Snowflake features itself using Streams, Tasks, Stored Proc etc. The code can be found here.  https://github.com/dheeraj2112/INFA_IICS_Snowflake_Project/blob/a69bf3a16396e40a7a6fa0aedafebf485ddfecd8/EDW%20STG%20to%20EDW%20Pipelines%20using%20Snowflake%20based%20on%20ORA%20HR%20DB.sql

4) ETL Code using IICS

**Pre-requisite: Valid IICS account and an agent with DIS service should be up and running. Once this is already in place then re-configure/re-point the connections (DB, Flat File and APIs etc) to your enviroment accordingly.**

The ETL Code can be found in the repo.  https://github.com/dheeraj2112/INFA_IICS_Snowflake_Project/blob/a69bf3a16396e40a7a6fa0aedafebf485ddfecd8/Enterprise%20Data%20Warehouse%20Export%204_Octtober_2024.zip

SRC to EDW STG: Enterprise Data Warehouse\EDW_STG
EDW STG to EDW: Enterprise Data Warehouse\EDW
EDW_EXTR: Enterprise Data Warehouse\EDW_EXTR

Note: ODBC connection has been used from IICS to Snowflake  but if you have the JDBC connector feel free to re-point the Snowflake database and other connections accordingly.

5) Analysis and Reporting
   
EDW_EXTR: Enterprise Data Warehouse\EDW_EXTR

Views or Dynamic tables can be leveraged accordingly. This can be done from ETL job or Snowflake db objects as per need. https://github.com/dheeraj2112/INFA_IICS_Snowflake_Project/blob/a69bf3a16396e40a7a6fa0aedafebf485ddfecd8/EDW_EXTR%20Views%20and%20Dynamic%20Tables%20for%20Reporting.sql

<END OF DOCUMENT>
