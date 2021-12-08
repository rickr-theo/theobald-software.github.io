---
ref: xtract-universal-19
layout: page
title: Running yunIO Services in Swagger Editor
description: Running Extractions in Swagger Editor
product: xtract-universal
parent: xtract-universal
permalink: /:collection/:path
weight: 90
lang: en_GB
progressstate: 5
---

<!---
Once the yunIO OH is up, adjust the links!
-->

This article shows how to run a yunIO service in the Swagger Editor.
The Swagger Editor is an open source editor to design, define and document RESTful APIs in the Swagger Specification. 
For more information on the Swagger Editor, see [Swagger Editor Documentation](https://swagger.io/docs/open-source-tools/swagger-editor/).

### Prerequisites in yunIO

1. Create a service in yunIO. For this article we use a Table extraction with the following settings:<br>
![Table-Extraction](/img/contents/yunio/table-settings.png){:class="img-responsive" width="800px" }
2. Copy the URL of the service (![copy-URL](/img/contents/yunio/copyURL.png) icon) or download the service definition (![download-file](/img/contents/yunio/download.png) icon).<br>
![yunio-Services](/img/contents/yunio/yunio-run-services.png){:class="img-responsive" width="800px"}

### Loading a yunIO Service into Swagger Editor

1. Open the Swagger Editor in your browser.
2. There are 2 ways to load a yunIO service into the swagger editor:<br>
- Click **File > Import URL** and enter the URL of the yunIO service.
- Click **File > Import File** and load a service definition from your harddrive.

Once the service is loaded, the service definition is diplayed on the left side of the Swagger Editor. The right side offers a user interface for the service definition.<br>
![Swagger-Editor](/img/contents/yunio/swagger-editor.png){:class="img-responsive"}

### Running and Parameterizing a yunIO Service in the Swagger Editor

You can edit parameters directly in the service definition or use the user interface on the right side of the Swagger Editor.
The following instructions apply to the user interface:
1. Unfold the content of your service to access the *Parameter* and *Responses* sections of the service.
2. Click **[Try it out]** in the *Parameter* section to edit parameters and to testrun the service.
3. To edit a parameter, overwrite the parameter definition (1) e.g., change the [WHERE clause](https://help.theobald-software.com/en/xtract-universal/table/where-clause) of the table from `"whereClause": "LAND1 = 'DE'"` to `"whereClause": "LAND1 = 'US'"` to only extract data where the LAND1 field equals 'US'.<br>
![WHERE-clause](/img/contents/yunio/swagger-where-clause.png){:class="img-responsive" width="800px"}
4. Click **[Execute]** to run the service. The results are displayed in the **Response** section of the Swagger Editor.
You can copy or download the test results from the *Response body* (2). <br>
![Server-Responses](/img/contents/yunio/server-responses.png){:class="img-responsive" width="800px"}

After executing the service in the Swagger Editor, the *Response* section of the Swagger Editor provides the following information:
- The *Curl command* to execute the service.
- The *Request URL* to execute the service.
- The server response that includes the return codes, the header and the body of the results.

******

#### Related Links
- [Web Version of the Swagger Editor](https://editor.swagger.io/)
- [Swagger Editor Documentation](https://swagger.io/docs/open-source-tools/swagger-editor/)
- [yunIO Help: How to Run a Service](https://help.theobald-software.com/en/yunio#how-to-run-a-service)