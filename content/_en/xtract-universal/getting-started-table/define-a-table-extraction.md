---
ref: xu-getting-started-table-02
layout: page
title: Step 2 - Define a Table Extraction
description: Step 2 - Define a Table Extraction
product: xtract-universal
parent: getting-started-table
permalink: /:collection/:path
weight: 2
lang: en_GB
---

### Create SAP connection

Select the menu item **Server -> Manage Sources**.

![XU-Create-Connection-1](/img/content/server_manage_sources.png){:class="img-responsive"}

Click on **Add**.

![XU-Create-Connection-2](/img/content/xu_manage_sources.png){:class="img-responsive"}

Enter the freely selectable connection name in the **Name** field. The SAP connection details must then be entered. <br>

The following parameters must be set: <br>
- Client (Client)
- Language (Language)
- User (User) and 
- Password (Password). <br>

If you want to connect to a single application server, fill the Host and System Number fields. <br>

If you want to connect to a message server using load balancing, fill the Message Server , Group, and SID fields. <br>

If you do not know the parameters, look in your SAP GUI or ask your SAP Basis. 

![XU-Create-Connection-3-A](/img/content/xu_source_details.png){:class="img-responsive"}

Then click on *Test Connection* to test the successful connection. 

![XU-Create-Connection-3](/img/content/xu_test_connection.png){:class="img-responsive"}

The SAP connection has now been set up successfully. 

![XU-Create-Connection-4](/img/content/xu_manage_source_2.png){:class="img-responsive"}

### Create Extraction

Click *New* to create a new extraction.

![Create-New-Table-Extraction](/img/content/xu_extraction_anlegen.png){:class="img-responsive"}

Choose the SAP connection you created previously and give the extraction a unique name.

Then define the type of extraction. In our case, we want to extract a *table* from SAP. 

![Add-Extraction](/img/content/xu/xu_tabellen_extraktion_anlegen.png){:class="img-responsive"}

{% include _content/en/tables/define-a-table-extraction.md  %}
