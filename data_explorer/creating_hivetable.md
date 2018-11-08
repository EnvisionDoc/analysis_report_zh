# Creating a hive table

This topic instructs how to create a hive table through Data Explorer.


## About this task
The data retrived from external data sources needs to be stored as Hive tables to be consumed by other EnOS data processing functions. You'll need to create the Hive table by using the Data Explorer.

## Procedure

1. In the EnOS Console, click **Data Explorer** from the left navigation panel.

2. In the **Data Explorer** panel, import or create a note.
   - If you already have a note created with table creation script included, click **Import Note**.
   - If you want to create a note, click **New Note**.

3. If you chose to create a note in step 2, enter the URL of the note and select **hive** as the note type. For example, if you entered `yourname/hive/tablename` as the URL, a hive table with the name `tablename` is created under the `yourname/hive` directory.

3. Click the **Enter note** icon (![Enter note](media/enter_note.jpg)) from the directory tree. In the notebook, enter the commands to create the table. For example,
  ```
  create table if not exists dpdw_dim_site_full(
	   site_id string,
	   site_name string,
	   capacity string,
	   equipment_amount string,
	   air_denity string,
	   area string,
	   state_name string
  ) comment 'wind domain dimension table'
  ```
  For more information about the commands, see [Apache Hive documentation on table creation](https://cwiki.apache.org/confluence/display/Hive/LanguageManual+DDL#LanguageManualDDL-CreateTable).


5. Click the **Run this paragraph** icon (![Run this paragraph](media/run.jpg)). You'll see your table created successfully as shown in the following screenshot:
   ![Resultant Hive Table](media/create_hive.jpg)


## Results
A table is created, and you can run a query to test your result.
```
%hive
select * from dw_meter_1h_demo limit 2
```
Run the query and you'll a result like this:
   ![Test query](media/test_query.jpg)


## What to do next

If you are creating the Hive table to store data from external data source, you'll then need specify the table as a target and map columns from the data source to the target through the Data Integration function. For more information, see [Data integration](https://docs.eniot.com/docs/offline-data/en/latest/data_integration/index.html) in *Batch Data Processing*.