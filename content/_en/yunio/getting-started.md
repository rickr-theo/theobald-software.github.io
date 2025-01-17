---
ref: yunio-04
layout: page
title: Getting Started
description: Getting Started
product: yunio
parent: yunio
permalink: /:collection/:path
weight: 9
lang: en_EN
---


The following section gives a general introduction to working with yunIO. 
The information described in the following section is a prerequisite for all subsequent sections.

### Starting yunIO

To access the yunIO Designer, enter the designer-URL in a [web browser](https://help.theobald-software.com/en/yunio/introduction/requirements#supported-web-browsers).<br>
The URL pattern to access the yunIO Designer is `http://[host]:[port]`. Example: `http://localhost:8077`.<br>
- If the yunIO service runs on a local server, replace `[host]` with *localhost*.
- If the yunIO service does not run on the same machine as the browser, replace `[host]` with the name or IP address of the host on which the service runs.
- After the installation the yunIO Designer is accessible under the default port 8077. <br>
You can configure the port under *Settings* in the yunIO Designer.

{: .box-note}
**Note:** Make sure that the *yunIO* service is running and that the default port 8077 is not blocked by your firewall.


### Adding an SAP Connection

In the *Connection* menu you can add new SAP connections and edit or delete existing connections.

1. To add a new SAP connection, click **[Add Connection]** (1).<br>
To edit an existing connection, click on the name of the connection you want to edit (2).
![web-ui](/img/content/yunio/web-ui.png){:class="img-responsive"}
2. Enter the connection information of your SAP system under *System* (3).<br>
![yunIO-connection](/img/content/yunio/yunio-connections.png){:class="img-responsive" width="750px" }
3. Enter your SAP credentials under *Authentication* (4).
4. To validate the connection parameters, click **[Test Connection]** (5). A window with a status message opens.
5. Click **[Save]** to save the connection settings. <br>

For more detailed information on establishing an SAP connection, see [SAP Connection](./sap-connection).

### Creating a service

In the *Services* menu you can create new web services and edit, run or delete existing web services.

1. To create a new service, click **[Add Service]** (1).<br>
To edit an existing service, click on the name of the service you want to edit (2).<br>
![yunIO-Services](/img/content/yunio/yunio-services.png){:class="img-responsive" }
2. Enter a name for the service and choose an existing SAP connection under *General* (3).<br>
![yunIO-new-service](/img/content/yunio/create-table.png){:class="img-responsive" width="750px"}
3. Choose an **Extraction Type** (4). yunIO offers the following options: *SAP Tables or Views*,*Function Modules* or *Transaction*. 
4. Optional: Add a short description for the service (5).
5. Click **[Save and edit]**.
To set up the service, see [SAP Table or View](./table-and-views), [Function Module / BAPI](./bapis-and-function-modules) or [Transactions](./transactions).


### How to use a service

Web services created with yunIO can be integrated into all cloud applications that support REST API/Swagger (OpenAPI), e.g. Power Automate, Nintex, etc.

To test a service after creation, trigger the URL of the service endpoint under **Service** (1). The service is then executed in your web browser. <br>

{: .box-note}
**Note:** Only services that do not require parameters supplied by a caller will display any SAP results in the browser. For parameterized services, use a tool
that supports Swagger/OpenAPI definitions (e.g.[Swagger Inspector](https://kb.theobald-software.com/yunio/running-a-yunio-service-in-swagger-inspector), [Postman](https://kb.theobald-software.com/yunio/running-a-yunio-service-in-postman)) . 

To integrate a yunIO web service into a tool that supports Swagger/OpenAPI, copy the code or download the service definition (2).

![yunIO-Services](/img/content/yunio/yunio-run-services.png){:class="img-responsive" }

*****
#### Related Links
- [SAP Table or Views](./table-and-views)
- [Function Module / BAPI](./bapis-and-function-modules)
- [Transactions](./transactions)
