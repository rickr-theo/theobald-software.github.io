### About Script Expressions

Script expressions offer a way of adding dynamic parameters to Xtract Universal. They can be used instead of entering a hard coded value. Script expressions are resolved at extraction runtime.
The output of a script expression is a string. This string can be used as input for further .NET string operations (see below)

Script expressions can be used in the following scenarios:
- as dynamic selection parameters for extractions
- as dynamic folder paths in destinations where a flat file is written
- as parameters in database destinations

There are two types of script expressions in Xtract Universal:
1. XU-specific custom script expressions 
2. Script expressions which are based on .NET classes


### Syntax of Script Expressions
In script expressions, a formula is written in C# syntax: The formula must begin and end with a hash symbol (#). The formula starts with and ends with curly brackets ({}).
Example: ```#{ Extraction.TableName }# ```

{: .box-note }
**Note:** XU-specific custom expressions are case sensitive. The exact syntax as documented on this page has to be used.



### Script Expressions based on .NET 
Xtract Universal script expressions support the following .NET objects, properties and methods from the .NET System Namespace of Xtract Universal's current [.NET framework](https://help.theobald-software.com/en/xtract-universal/introduction/requirements#other-applications-and-frameworks).

```Object```,
```Boolean```,
```Char```,
```String```,
```SByte```,
```Byte```,
```Int16```,
```UInt16```,
```Int32```,
```UInt32```,
```Int64```,
```UInt64```,
```Single```,
```Double```,
```Decimal```,
```DateTime```,
```TimeSpan```,
```Guid```,
```Math```,
```Convert```


{: .box-note }
**Note:** The most common usage scenario is using the methods and properties of the .NET ```DateTime``` and ```String``` classes. For further information of supported [.NET classes and their properties and methods](https://docs.microsoft.com/en-us/dotnet/api/system?redirectedfrom=MSDN&view=netframework-4.7.2) including [DateTime](https://docs.microsoft.com/en-us/dotnet/standard/base-types/custom-date-and-time-format-strings) and [String](https://docs.microsoft.com/en-us/dotnet/api/system.string?view=netframework-4.7.2) see the Microsoft online documentation.

**Examples:**

|   Input                         | Output                                                                         | Description              |
|:--------------------------------------|:------------------------------------------------------------------------------|:--------------------|
|```#{ DateTime.Now}#```                                                             | DD.MM.YYYY HH:MM:SS | Current date and timestamp |
|```#{ DateTime.Now.AddDays(-5).ToString("d") }#```                                  | DD.MM.YYYY | Date 5 days ago. If today's date is 10th, then 05th is the output.         |
|```#{ DateTime.Now.ToShortDateString() }#```                                        | DD.MM.YYYY | Current date         |
|```#{ DateTime.Now.ToString("yyyyMMdd") }#```                                       | yyyyMMdd | Current date in SAP format          |
|```#{ String.Concat(DateTime.Now.Year.ToString(), "0101") }#```                     | yyyy0101 | Current year concatenated with "0101"           |
|```#{ String.Concat(DateTime.Now.ToString("yyyy"), "0101") }#```                    | yyyy0101 | Current year concatenated with "0101"            |
|```#{ String.Concat(DateTime.Now.ToString("yyyyMMdd").Substring(0,4), "0101") }#``` | yyyy0101 | Current year concatenated with "0101"           |
|```#{Extraction.SapObjectName.TrimStart("/".ToCharArray())}# ```                    | BIO/TMATERIAL | Trims the first slash '/' of an SAP object, e.g. /BIO/TMATERIAL, so as not to create an empty folder in a file path.
|```#{Extraction.SapObjectName.Replace('/', '_')}#``` | _BIO_TMATERIAL | Replaces all slashes '/' of an SAP object, e.g. /BIO/TMATERIAL, so as not to split the SAP object name by folders in a file path.         |






### Using Script Expressions as Selection Parameters for Extractions

Script expressions can be used as selection parameters in Table or DeltaQ extractions. They are usually used to determine a dynamic date based on the current date. With Table extractions they are used as part of the [WHERE Clause](../table/where-clause).

This scenario supports:
- Script expressions based on .NET

{: .box-note }
**Note:** When using a WHERE Clause, the value must be entered in single quotation marks.<br>
*Syntax:*```[Field_name][Space][Operator][Space]'#[Script-Expression]#'```<br>
*Example:*```BUDAT >= '#{DateTime.Now.AddDays(-30).ToString("d")}#'```


### Using Script Expressions as Dynamic Folder Paths

{: .box-note }
**Note:** This is currently only supported for the [Azure Storage destination](https://help.theobald-software.com/en/xtract-universal/xu-destinations/azure-storage).

In this scenario, script expressions are used for generating a dynamic folder path for destinations that write a flat file. This allows generating a folder path which is composed of an extraction's properties like extraction name, SAP source object, etc.


This scenario supports:
- Script expressions based on .NET
- XU-specific custom script expressions

The following XU-specific custom script expressions are supported: 

| Input                                                   | Description|
|:--------------------------------------------------------|:-----------|
|```#{Source.Name}# ```|  Name of the extraction's SAP source|
|```#{Extraction.ExtractionName}# ```| Name of the extraction |
|```#{Extraction.Type}# ```|  The extraction type, such as *Table*, *ODP*, *DeltaQ*, etc. |
|```#{Extraction.SapObjectName}# ```|  The name of the SAP object the extraction is extracting data from |
|```#{Extraction.Context}# ```|  Only contains values for ODP extractions. The context of the ODP object, such as *SAPI*, *ABAP_CDS*, etc. |
|```#{Extraction.Timestamp}# ```|  Timestamp of the extraction  |


**Examples:** 

| Input                                                   | Output   | Description|
|:--------------------------------------------------------|:---------|:-------|
|```#{Source.Name}#/#{Extraction.SapObjectName}#/#{Extraction.ExtractionName}#/#{Extraction.Timestamp}# ```| ```ECC/2LIS_02_ITM/MyDataSource1/2021-01-30_20-27-19.686/[filename]```   | If the SAP Source is called *ECC* and the extracted object is SAP DataSource *2LIS_02_ITM* and the extraction name is *MyDataSource1*, the generated file path could look like illustrated in the *Output* column.

### Using Script Expressions in Database Destinations

In this scenario script expressions are used as part of a Custom-SQL statement (see example [here](https://help.theobald-software.com/en/xtract-universal/xu-destinations/microsoft-sql-server/sql-server-custom-sql)).

This scenario supports:
- Script expressions based on .NET
- XU-specific custom script expressions

The following XU-specific custom script expressions are supported: 

| Input                                                   | Description|
|:--------------------------------------------------------|:-----------|
|```#{Extraction.TableName }# ```|  Name of the database table extracted data is written to|
|```#{Extraction.RowsCount }# ```| Count of the extracted rows |
|```#{Extraction.RunState}# ```|  Status of the extraction (Running, FinishedNoErrors, FinishedErrors) |
|```#{(int)Extraction.RunState}# ```|  Status of the extraction as number (2 = Running, 3 = FinishedNoErrors, 4 = FinishedErrors) |
|```#{Extraction.Timestamp}# ```|  Timestamp of the extraction  |


The following XU-specific custom function can be used:

| Input                                                   | Description|
|:--------------------------------------------------------|:-------|
|``` bool ExistsTable(string tableName) ``` | Check if the the table exists on the database destination. |


### IF-Statement 

An IF-statement (ternary operator) is supported and has the following syntax: ```iif([bool condition], [string trueResult], [string falseResult])``` 

**Examples:** 

| Input                                                   | Output   | Description|
|:--------------------------------------------------------|:---------|:-------|
|```#{ iif(DateTime.Now.Month==7, "July","Unknown")}# ```| July     | When we are in the 7th month, the output is "July", all else is "Unknown". |
|```#{Extraction.ExtractionName}##{ iif(string.IsNullOrEmpty(Extraction.Context), string.Empty, "/" + Extraction.Context)}#```|| *Extraction.Context* returns a result only with ODP extractions. With all other extraction types the result is empty. If the extraction name is 'SAP_1' and the extraction type is 'Table', the resulting file path would be ```SAP_1/[filename]```. If the extraction name is 'SAP_2' and the extraction type is 'ODP' and a SAP DataSource (extraction context: SAPI) is being extracted, the resulting file path would be ```SAP_2/SAPI/[filename]```. 






### Supported Key Words

Following key words are supported: 
- true
- false
- null




