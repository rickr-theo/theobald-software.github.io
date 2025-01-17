---
ref: destinations-110
layout: page
title: Tableau
description: Tableau
product: xtract-universal
parent: destinations
childidentifier: tableau
permalink: /:collection/:path
weight: 110
lang: en_GB
old_url: /Xtract-Universal-EN/default.aspx?pageid=tableau
progressstate: 5
---
The following section describes the loading of the SAP extraction data into Tableau Analytics Platform. 

The Tableau Destination enables you to save data extracted from SAP as Hyper files.

It is also possible to upload the Hyper file to Tableau Server or Tableau Online.


## Requirements
No further tool installation is required. 

The required Visual C++ 2013 / 2015 Runtime and the Tableau Export Library will be installed automatically by XtractUniversalSetup.

![XU_Setup](/img/content/xu/XU_Setup_4.png){:class="img-responsive"}

{: .box-note }
**Note:** Make sure to check the checkbox "Tableau Extract API" during setup.

## Connection

{% include _content/en/xu-specific/destinations/general/connection.md %}	

### Destination Details
![tableauDestinationDetails-hyper](/img/content/tableauDestinationDetails-hyper.png){:class="img-responsive"}

### Output directory
Enter the directory on the Xtract Universal Server to store the generated Tableau files in.

{: .box-note }
**Note:** Make sure that the directory exists.

### Tableau Server
- **Upload to Tableau Server**<br>
Option to upload the extracted file (as a data source) to Tableau Server or Tableau Online.
- **Delete local file after upload**<br>
Option to remove the local file after a successful upload.

**Host**<br>
Enter the IP address or domain name of the remote server, starting with `http://` or `https://`.

**Username**<br>
Enter your username for Tableau Server/Online.

**Password**<br>
Enter your password for Tableau Server/Online.

**Site (for Tableau online)**<br>
Enter the ID of the site for publishing your data source. 
This field is mandatory and cannot be left blank. 

Get the correct site URL from [Tableau Online](https://online.tableau.com/#/site/Site/workbooks).

For the extraction of data to Tableau Online the role "Server Administrator" is required as "Site Role".
![Tableau_Server_Admin](/img/content/xu/tableau_server_admin.png){:class="img-responsive"}

**[Test Connection]**<br>
Check the database connection. 

#### Tableau Server Settings
**Site**<br>
A drop-down list of the sites stored on the connected on-prem server. Selecting a site is mandatory for uploading files. 

**Project**<br>
The project for publishing data source.

## Settings

### Opening the Destination Settings
1. Create or select an existing extraction (see also [Getting Started with Xtract Universal](../getting-started/define-a-table-extraction)).
2. Click **[Destinations]**. The window "Destination Settings" opens.
![Destination-settings](/img/content/xu/xu_designer_destination.png){:class="img-responsive"}

The following settings can be defined for the destination:  

### Destination Settings
![Tableau-Extraction-Specific-Settings](/img/content/Tableau-Extraction-Specific-Settings.png){:class="img-responsive"}

{% include _content/en/xu-specific/destinations/general/file-name.md %}

{% include _content/en/xu-specific/destinations/general/column-name-style.md %}

{% include _content/en/xu-specific/destinations/general/date-conversion.md %}

{% include _content/en/xu-specific/destinations/general/existing-files.md %}


*****
## Related Links
- [Webinar: Visualize your SAP data in Tableau](https://www.youtube.com/watch?v=X6T3NfVDhJE)
