---
ref: destinations-100
layout: page
title: Salesforce
description: Salesforce
product: xtract-universal
parent: destinations
childidentifier: salesforce
permalink: /:collection/:path
weight: 100
lang: en_GB
old_url: /Xtract-Universal-EN/default.aspx?pageid=salesforce
progressstate: 5
---

The following section describes the loading of the SAP extraction data to Salesforce.

## Requirements

**Salesforce Edition**<br>
This destination requires one of the following Salesforce editions:
- *Enterprise*
- *Unlimited*
- *Performance Edition*
The Salesforce edition has to include the Integration via web service API feature.

**Permissions**<br>
To run an extraction the API-Enabled permission is needed.
If the object has to be created the user also needs following permissions:
- *Mofidy All Data*
- *Customize Application*
- *Manage Profiles and Permission Sets*

## Connection

{% include _content/en/xu-specific/destinations/general/connection.md %}	

### Destination Details
![sf-destination-details](/img/content/sf-destination-details.png){:class="img-responsive"}

**Username**<br>
Enter your Salesforce username.

**Password**<br>
Enter the corresponding password.

**Security Token**<br>
Enter the Security Token that was generated by Salesforce and is used to access API functions. The **Reset Security Token** link will take you to the website where you can reset your current Security Token.

To reset your security token on Salesforce go at the top navigation bar go to 
*your name > Setup > Personal Setup > My Personal Information > Reset My Security Token*.

**Test connection**<br>
Check the database connection. 

## Settings

### Opening the Destination Settings
1. Create or select an existing extraction (see also [Getting Started with Xtract Universal](../getting-started/define-a-table-extraction)).
2. Click **[Destinations]**. The window "Destination Settings" opens.
![Destination-settings](/img/content/xu/xu_designer_destination.png){:class="img-responsive"}

The following settings can be defined for the destination:  

### Destination Settings


![sf-destination-settings3](/img/content/sf-destination-settings3.PNG){:class="img-responsive"}

{% include _content/en/xu-specific/destinations/general/file-name.md %}
{% include _content/en/xu-specific/destinations/general/column-name-style.md %}
{% include _content/en/xu-specific/destinations/general/date-conversion.md %}

### Preparation

- **Delete & Create**: Deletes the object with the specified name and creates a new one.
- **Create if not exists**: Creates a new object if no object with the specified name could be found.

### Row processing

- **Insert**: Inserts all records into the specified object.
- **Merge**: Inserts all records into the specified object and updates already existing entries.

### Concurrency mode

- **Parallel**: Process batches in parallel mode. This is the default value.
- **Serial**: Process batches in serial mode. Processing in parallel can cause database contention. When this is severe, the job may fail. If you're experiencing this issue, submit the job with serial concurrency mode. This guarantees that batches are processed one at a time. Note that using this option may significantly increase the processing time for a job.