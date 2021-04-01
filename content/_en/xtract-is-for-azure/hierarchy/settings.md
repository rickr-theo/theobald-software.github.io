---
ref: xi-hierarchy-03
layout: page
title: Settings
description: Settings
product: xtract-is
parent: hierarchy
permalink: /:collection/:path
weight: 3
lang: en_GB
old_url: /Xtract-IS-EN/default.aspx?pageid=hierarchy-settings
---

Click the *Settings* link to open the settings dialog.

![XIS_BWHierarchy_settings](/img/content/XIS_BWHierarchy_settings.png){:class="img-responsive" }

**Automatic String Conversion**<br>
All strings are converted into VarChar strings if the source system is non-Unicode, and all strings are converted into NVarChar if the source system is Unicode.

**Convert Strings to VarChar**<br>
All strings are converted to VarChar regardless of whether the source system is Unicode or not.

**Convert Strings to NVarChar**<br>
All strings are converted to NVarChar regardless of whether the source system is Unicode or not.


**Representation**

- **Parent-child**: The hierarchy has the SAP default parent-child format.
- **Natural/flattened**: The parent child hierarchy will be transformed to a flattened format.

**Remove leading zeros**<br>
Removes all leading zeros using ALPHA conversion in the column NodeName. NodeName can then be used in a join condition with the corresponding Dimension-Key of a BWCube extraction.
Works also for compound InfoObjects. Example: 0CO_AREA (1000) and 0COSTCENTER (0000003100) will become 1000/3100.


**Fetch description texts**<br>
This means that the field NodeText contains the node text based on the system language settings. 

**Legacy Mode**<br>
If the option is enabled, links and intervals will not be resolved and invalid nodes in hierarchies with time-dependent structure will not be filtered. Node-IDs will be delivered as they are in the SAP hierarchy table.

**Natural Representation Settings**<br>
is active only, when Representation has the value *Natural/flattened*.

**Level Count**<br>
Defines the maximum number of levels if the representation natural is selected. In the following screenshot you see the hierarchie shown in the previous screenshot with five levels in the representation natural.

**Leaves only**<br>
Delivers only the leaves as data records.

**Fill empty levels**

**Description texts for levels**<br>
Means, that the output has a field LevelTextN for each field LevelN, that contains the text based on the system language settings.