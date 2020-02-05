---
ref: ecs-getting-started-creating-a-new-model-07
layout: page
title: Where Clause
description: Where Clause
product: erpconnect-services
parent: creating-a-new-model
permalink: /:collection/:path
weight: 7
lang: en_GB
old_url: /ERPConnect-Services-EN/default.aspx?pageid=bcs-where-clause
---

For the Finder operation (Read Table) of a table entity you can define a where clause.

![BCS-Where](/img/content/BCS-Where.png){:class="img-responsive"}

The WHERE clause must comply with the SAP OpenSQL syntax.

- Before and after the equal sign, you must enter a space, eg YEAR = '1999 '. For YEAR= '1999 ', YEAR ='1999' or YEAR='1999' you will get the error message '*A dynamically specified column name is unknown*'.
- Floating point numbers must always be set in single quotation mark, e.g. KMENG > '10.3'. For KMENG > 10.3 you get the error message '*The WHERE clause has an unexpected format*'.
- The Where clause must not contain any line break (return key).

You will find more information about the OpenSQL syntax on the SAP help site: [https://help.sap.com/doc/abapdocu_752_index_htm/7.52/en-US/abapwhere.htm?file=abapwhere.htm](https://help.sap.com/doc/abapdocu_752_index_htm/7.52/en-US/abapwhere.htm?file=abapwhere.htm)

Values must have the internal SAP representation:

- The date 01.01.1999 has the internal representation 19990101 (YYYYMMDD),
- The year period 001.1999 has the internal representation 1999001 (YYYYPPP),
- Numbers must have the leading zeros, e.g. customer number 1000 has the internal representation 0000001000.