---
ref: destinations-61
layout: page
title: Microstrategy
description: Microstrategy
product: xtract-universal
parent: destinations
childidentifier: microstrategy
permalink: /:collection/:path
weight: 61
lang: en_GB
old_url: /Xtract-Universal-EN/default.aspx?pageid=microstrategy
progressstate: 5
---

The following section describes the loading of the SAP extraction data to Microstrategy server as Intelligent Cube.


## Requirements

- Microstrategy Server including JSON API: version 10.10 or higher. 
- User credentials with the appropriate rights to connect to the JSON API and create datasets and tables in Microstrategy.  

## Connection

{% include _content/en/xu-specific/destinations/general/connection.md %}	

### Destination Details
![mstr-destination-details](/img/content/mstr-destination-details.png){:class="img-responsive"} 

**JSON Data API Server**<br>
Microstrategy Server Endpoint for the JSON API.<br> 
(e.g.: https://env-12345.customer.cloud.microstrategy.com/MicroStrategyLibrary/api/)

**Project Name**<br>
Project name, where the SAP data is loaded to. The default folder is "My Reports" in "My Personal Objects". To set a specific folder, see [Folder ID](#folder-id).

**User Name**<br>
Name of the Microstrategy user.

**Password**<br> 
Password of the Microstrategy user. 

## Settings

### Opening the Destination Settings
1. Create or select an existing extraction (see also [Getting Started with Xtract Universal](../getting-started/define-a-table-extraction)).
2. Click **[Destinations]**. The window "Destination Settings" opens.
![Destination-settings](/img/content/xu/xu_designer_destination.png){:class="img-responsive"}

The following settings can be defined for the destination:  

### Destination Settings

![mstr-destinations](/img/content/mstr-destinations.png){:class="img-responsive"}

{% include _content/en/xu-specific/destinations/general/file-name.md %}

{% include _content/en/xu-specific/destinations/general/column-name-style.md %}

{% include _content/en/xu-specific/destinations/general/date-conversion.md %}

### Dataset ID

Dataset ID of the Table. This will be automatically generated by the MSTR server and can be found in the log. 
The Dataset ID is set automatically for the default DropAndCreate Update Policy.
For other Update policies it can be set manually.


### Attributes and metrics

Attributes and metrics will be defined automatically based on the data types of the source object. 
If you wish to redefine attributes or metrics click on the correspondent button and then click to generate the JSON definition to modify the definition. 


![mstr-extraction-settings_attr](/img/content/mstr-extraction-settings_attr.png){:class="img-responsive"}

![mstr-extraction-settings_metrics](/img/content/mstr-extraction-settings_metrics.PNG){:class="img-responsive"}

### Folder ID

Optional. Enter the ID of a project folder in Microstrategy. The data will be written into the defined folder. You can also use subfolders.<br>
Folder IDs are displayed in Microstrategy under *Properties*.  

![Folder-ID](/img/content/xu/microstrategy-folder.png){:class="img-responsive"}


### Update Policy

|:---:|:---|
|  **DropAndCreate** | Default. Table will be dropped and created again. Data will be then inserted.  | 
|  **Add** | Adds data to the existing table. Dataset ID is required.  | 
| **Update**  | Updates the metric values in the data set where there is already a matching key in the dataset; new records are ignored.  | 
|  **Upsert** |  Updates existing records and then add new ones. | 
|  **Replace** |  Table will be truncated. Data will be then inserted. Dataset ID is required. | 

