---
ref: bc-getting-started-05
layout: page
title: General Settings
description: General Settings
product: board-connector
parent: getting-started
permalink: /:collection/:path
weight: 5
lang: en_GB
old_url: /BOARD-Connector-EN/default.aspx?pageid=general-settings
progressstate: 5
---	
General Settings are independent of the extraction type.

### To open General Settings
1. In the main window of the Designer, double-click an extraction.<br>
The window "Define data source for [...]" opens.<br>
Example:
![General-Settings](/img/content/General-Settings_designer.png){:class="img-responsive"}

2. Within the opened window, click **[General Settings]**.<br>
The window "General Settings" opens.


### Misc. tab
The miscellaneous tab consists of two subsections:
- Options
- Keywords

![General-Settings](/img/content/General-Settings.png){:class="img-responsive"}

#### Options
**Cache results** (1)

{:.box-note}
**Note:** *Cash results* option is only available in pull destinations (e.g., PBI, Qlik etc.).

Pull destinations often pull the data from SAP for several times. To decrease the SAP server load, you can select the **Cache results** option, this way the pull destination pulls the data from cache and not from the SAP.
This increases the performance and limits the impact on the SAP system. If this behavior is not desired (for example, because the data must be always 100% up to date), the cache option must be explicitly turned off.

**Preview Mode** (2)
If preview mode is activated, only a small portion of data is extracted from SAP or, if extraction is not possible, sample data is generated instead.

#### Keywords
One or more keywords (Tags) can be set to an extraction. 
Keywords can be entered directly in the keyword field (3).
Within the Designer you can use these keywords to filter  extractions. 

{:.box-tip}
**Tip:** to display filter options, navigate to **[Extractions] > [Filter]** or press **[CTRL]+[F]**.
 
### Primary Key tab
Table extractions inherit the primary keys from SAP. Other objects such as SAP Query, BW Cube etc. require manual setting of the primary keys.  
![General-Settings-Primary-Key](/img/content/XU_table_Primary_key.png){:class="img-responsive"}

Depicted example demonstrates the SAP object *MAKT* with it's primary key inherited from SAP in the general settings of the Designer. In this example the primary key consists of *MANDT*, *MATNR*, *SPRAS*. The demonstrated primary key is also taken over in the destination. 

{:.box-note}
**Note:** A defined primary key field in a table is a prerequisite for merging data. 


### Security Tab
The security tab is described in the section [access management](https://help.theobald-software.com/en/board-connector/security/access-management).