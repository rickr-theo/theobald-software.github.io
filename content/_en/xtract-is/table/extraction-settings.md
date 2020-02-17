---
ref: xi-table-06
layout: page
title: Extraction settings
description: Table Properties
product: xtract-is
parent: table
permalink: /:collection/:path
weight: 6
lang: en_GB
old_url: 
---
{% include _content/en/tables/extraction-settings.md  %}

![Table-XIS-Properties](/img/content/Table-XIS-Properties.png){:class="img-responsive"}

### Custom Properties

**ConvertsDates**<br>
The default value of this property is *True*. Setting this property to *True* does two things:
1. SAP date fields (YYYYMMDD) are typed to SSIS pipeline type DT_DBDATE (instead of DT_WSTR).
2. The following date conversions are applied in case of invalid data in SAP date fields: InvalidDateReplacement, MaxDateReplacement and MinDateReplacement. For the date conversions to apply, the *UseLegacyDateConversion* propery must be set to *False*.<br>

**InvalidDateReplacement** <br>
* Enter a replacement value for invalid SAP dates, such as '20190132' (January 32nd  2019).
* Enter the replacement value in the following format: yyyy-mm-dd
* The value NULL is supported 
* The default value of this property is 1970-01-02

**MaxDateReplacement** <br>
* Enter a replacement value for SAP dates that contain the year '9999'. Example: '99990101' (January 1st 9999)
* Enter the replacement value in the following format: yyyy-mm-dd
* The value NULL is supported
* The default value of this property is 2099-12-31 

**MinDateReplacement** <br>
* Enter a replacement value for SAP dates that contain the year '0000'. Example: '00000000' 
* Enter the replacement value in the following format: yyyy-mm-dd
* The value NULL is supported
* The default value of this property is 1970-01-01 

**UseLegacyDateConversion**<br>
This property is meant for migration of table extractions from Xtract IS versions < 5.0.0. The default value of this property is *False*. As a prerequisite for using this property, the *ConvertsDates* property must be set to *True*. Setting *UseLegacyDateConversion* to *True* does the following:
* Invalid SAP date values are replaced with the value entered in the *InvalidDateReplacement* property.
* There is no replacement for SAP dates that contain the year '9999'. The value entered in the MaxDateReplacement property is *not* considered.
* SAP dates that contain the year '0000' are replaced with NULL. The value entered in the MinDateReplacement property is *not* considered.

**Use Field Exits**<br>
Defines whether the conversion routines stored in the ABAP Data Dictionary are used for the respective fields. Typical examples are the language key (for example, D in the database, but DE after conversion) or the project number (for example, T000012738GT in the database, T/12738/GT after conversion). After the conversion, the value is always displayed as it would appear in a transaction in the SAP GUI. <br>

