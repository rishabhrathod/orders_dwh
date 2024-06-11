# Datawarehouse ETL job

This notebook is designed to run in incremental fashion where it picks most recent file from the source.

The script does follows 

    1 -> Reads files from the csv in specific format (201901_orders_2019_02_01_23_00_00)

    2 -> File is loaded into staging/bronze layer, and entry is made to log table to keep all loads in check with source row count

    3 -> Basic data quality checks performed using Great_expecations (consistency, uniqueness, pattern matching)

    4 ->  Loads the data into silver layer while treating it and generates Sks when and where required.

    5 -> Scipt handles insertloads(not to insert if already exists a value), SCD2 , invalidating records in transaction tables 
