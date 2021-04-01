---
ref: xi-bapi-04
layout: page
title: Tables
description: Tables
product: xtract-is
parent: bapi
permalink: /:collection/:path
weight: 4
lang: en_GB
old_url: /Xtract-IS-EN/default.aspx?pageid=tables
---

Tables can be entered in and extracted from the function module / BAPI. Therefore, there are two types of behavior for tables: *input type* and *output type*.

![BAPI-Tables](/img/content/BAPI-Tables.png){:class="img-responsive" }


The following options are possible:

**Pipeline**<br>
This means that the table is imported from (or exported to) a pipeline within the data flow task. To import tables via a pipeline, use the *Edit* link to open up a dialog to map the pipeline elements.

**Static**<br>
This means that the table values are static and independent of all pipeline types. Use the *Edit* link to open a dialog to define static table values. The type *Static* is only available for the input type.

**Skip**<br>
This simply means that the table is ignored.