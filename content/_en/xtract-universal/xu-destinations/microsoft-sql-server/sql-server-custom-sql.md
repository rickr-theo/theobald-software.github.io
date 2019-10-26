---
ref: xu-microsoft-sql-server-06
layout: page
title: Custom SQL
description: Custom SQL
product: xtract-universal
parent: microsoft-sql-server
permalink: /:collection/:path
weight: 6
lang: en_GB
old_url: /Xtract-Universal-EN/default.aspx?pageid=sql-server-settings
---

You have the possibility to use your own SQL statement for the three different DB process steps and / or to adapt it to your requirements.

The necessary adjustments must be made for the sections Preparation, Row & Processing and Finalization in the destination settings. 
To do this, select an existing extraction in Xtract Universal and click on the Destination button.

![Destination-Settings](/img/content/destination_settings.png){:class="img-responsive"}

In the following example, the table *KNA1* is extended by a column with the current time stamp of type *datetime*. 
This new column is filled dynamically using a .NET-based function. 
The data types that can be used in the SQL statement depend on the SQL Server database version.

![Custom-SQL_Prep](/img/content/custom_sql_generate_statement.png){:class="img-responsive"}

Start by selecting *Custom SQL* in the Preparation section from the drop-down menu. Then click the *Edit SQL* button to edit the code.
From the drop-down menu, select *Drop & Create* and click *Generate Statement*. At the end of the generated statement, add the following line and confirm with *OK*.
```
[DATE] datetime
```

![Custom-SQL_DATUM_insert](/img/content/custom_sql_column_datum_einfügen.png){:class="img-responsive"}

In the *Row Processing* section, the column values from SAP are processed in the previously created columns of the SQL target table. This SQL statement is therefore left on the standard *Insert* as an SQL statement. At this point, no data is written from the SAP source system, but `NULL` values are written to the newly created *Date* column.

In the last section *Finalization*, the `NULL` values are filled with the following SQL statement of the current date of the extraction and written to the SQL target table by the T-SQL command `UPDATE`. Confirm the input with *OK*.
```
UPDATE [dbo].[KNA1] 
SET [DATUM] = GETDATE() 
WHERE [DATUM] IS NULL;
```
![Custom-SQL_Final](/img/content/custom_sql_finalization_statement.png){:class="img-responsive"}