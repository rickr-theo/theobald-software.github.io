
### Preparation - SQL Commands

Defines the action on the target database before the data is inserted into the target table.
- *Drop & Create*: Remove table if available and create new table (default).
- *Truncate Or Create*: Empty table if available, otherwise create.
- *Create If Not Exists*: Create table if not available.
- *Prepare Merge*: prepares the merge process and creates e.g. a temporary staging table. See [merging](./merging-data) for more details. 
- *None*: no action
- *Custom SQL*: Here you can define your own script. See the Custom SQL section below. 

If you only want to create the table in the first step and do not want to insert any data, you have two options:
1. Copy the SQL statement and execute it directly on the target data database.
2. Select the None option for Row Processing and execute the extraction.

Once the table is created, it is up to you to change the table definition, 
by, for example, creating corresponding key fields and indexes or additional fields.


### Row Processing

Defines how the data is inserted into the target table.
- *Insert*: Insert records (default).
- *Fill merge staging table*: Insert records into the staging table.
- *None*: no action.
- *Custom SQL*: Here you can define your own script. See the Custom SQL section below.
- *Merge (deprecated)*: This option is obsolete. Please use the Fill merge staging table option and check the About Merging section. 


### Finalization

Defines the action on the target database after the data has been successfully inserted into the target table.
- *Finalize Merge*: Closes the merge process and deletes the temporary staging table, for example.  
- *None*: no action (default).
- *Custom SQL*: Here you can define your own script. See the Custom SQL section below.


#### About Merging
Merging ensures delta processing: new records are inserted into the database and / or existing records are updated. 
See section [merging data](./merging-data).


#### Custom SQL

Custom SQL option allows creating user-defined SQL or script expressions. Existing SQL commands can 
be used as templates:

1. Within subsection e.g., **Preparation** select the **Custom SQL** (1) option from the drop-down list.
2. Click **[Edit SQL]**. The window "Edit SQL" opens.
3. Navigate to the drop-down menu and select an existing command (3). 
4. Click **[Generate Statement]**. A new statement is generated.
5. Copy the statement for further use and click **[OK]** to confirm.
 
![Formula-ExistsTable](/img/content/Formula-ExistsTable.png){:class="img-responsive"}

Check out the [Microsoft SQL Server example](../microsoft-sql-server/sql-server-custom-sql) for details on predefined expressions.

{:.box-note}
**Note:** the custom SQL code is used for SQL Server destinations. A syntactic adaptation of the code is necessary to use the custom SQL code for other database destinations.

#### Templates

You can write your user-defined SQL expressions and adapt the loading of the data to your needs. <br>
You can additionally execute stored procedures that exist in the database.
To do so, use the SQL templates provided in the following phases:
- *Preparation (e.g., Drop & Create or Create if Not Exists)* 
- *Row Processing (e.g., Insert or Merge)*  
- *Finalization*


#### Script Expressions

You can use [script expressions](../advanced-techniques/script-expressions) for the Custom SQL commands.

{:.box-tip}
**Tip:** *ExistsTable(tableName)* command allows to verify the existence of a table in a database.

<details>
<summary>SQL-Skript</summary>
{% highlight sql %}
#{
   iif
   (
      ExistsTable("MAKT"),
      "TRUNCATE TABLE \"MAKT\";",
      "
         CREATE TABLE \"MAKT\"(
            \"MATNR\" VARCHAR(18),
            \"SPRAS\" VARCHAR(2),
            \"MAKTX\" VARCHAR(40));
      "
   )
}#

{% endhighlight %}
</details>
