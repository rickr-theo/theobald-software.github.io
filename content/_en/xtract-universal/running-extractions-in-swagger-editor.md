---
ref: xtract-universal-19
layout: page
title: Running Extractions in Swagger Editor
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

This article shows how to use a yunIO service in swagger editor.

### Prerequisites in yunIO

1. Create a service in yunIO. This example uses a Table extraction with the following settings:<br>
![Table-Extraction](/img/contents/yunio/table-settings.png){:class="img-responsive" width="800px" }
2. Copy the URL of the service (![copy-URL](/img/contents/yunio/copyURL.png) icon) or download the service definition (![download-file](/img/contents/yunio/download.png) icon).<br>
![yunio-Services](/img/contents/yunio/yunio-run-services.png){:class="img-responsive" width="800px"}

### Loading a yunIO Service into Swagger Editor

1. There are 2 ways to load a yunIO service into the swagger editor:<br>
- Click **File > Import URL** and enter the URL of the yunIO service.
- Click **File > Import File** and load a service definition from your harddrive.
2. Once the service is loaded, the service definition is diplayed on the left side of the window...
3. ...
4. Click **[Try it out]** to set parameters and run the extraction:
- To edit a parameter, overwrite the parameter definition (1) e.g., change `"whereClause": "LAND1 = 'DE'"` to `"whereClause": "LAND1 = 'EN'"` to extract ...<br>
![WHERE-clause](/img/contents/yunio/swagger-where-clause.png){:class="img-responsive" width="800px"}
- Click **[Execute]** to run the extraction. The results are displayed under **Responsed** > *Server response* in the *response body*.
