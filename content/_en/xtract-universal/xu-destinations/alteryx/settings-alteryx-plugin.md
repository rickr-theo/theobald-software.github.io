---
ref: xu-alteryx-04
layout: page
title: Settings (Alteryx)
description: Settings (Alteryx)
product: xtract-universal
parent: alteryx
permalink: /:collection/:path
weight: 4
lang: en_GB
old_url: /Xtract-Universal-EN/default.aspx?pageid=settings-alteryx-plugin-en-
---

To use the Xtract Universal tool you will have to add it to a workflow.

![XU_alteryx_plugin](/img/content/XU_alteryx_plugin.png){:class="img-responsive"}

Following settings have to be specified for the Xtract Universal tool in the Alteryx Designer.

## Connection

**Server**<br>
the name, IP or domain and port the server can be accessed with within the network.

**Extraction**<br>
the name of the desired extraction. When clicking the arrow next to the text area, all available extractions will be loaded into a dropdown menu. Only those extractions will be displayed, for which you selected the alteryx destination type in Xtract Universal designer.
For this functionality the Xtract Universal server has to be up and running.

The **Send SAP credentials** <br>
setting is only required, if the *Require SAP Credentials* checkbox has been flagged in the *[Security]()* tab in the extraction's *General Settings*.
This might be useful in self service scenarios, where each extraction needs to be executed using an individual user's *SAP credentials* instead of the one, globally defined in the *Xtract Universal SAP* source.

![alteryx-extraction-selection](/img/content/alteryx-extraction-selection.png){:class="img-responsive"}

## Parameters 
When selecting the **Parameters** tab, the tool will load the available parameters for the specified extraction. 

**Override custom Parameters with static values**<br>

In this case we have an extraction of SAP customers, where the city parameter in the **custom defined parameters** tab will be overwritten with a static value. This is done by checking the **Override** field and entering a new **value**.

![alteryx-custom-parameters](/img/content/alteryx-custom-parameters.PNG){:class="img-responsive"}

**Override custom Parameters with dynamic values**<br>
The Xtract Universal tool can also have an input, e.g. the Input Data Tool.
The data input can dynamically be used to override the custom parameter in Xtract Universal.<br> 
In this case we have an extraction of SAP customers, where the city parameter will be dynamically parametrized.
Those can be edited by checking the **Override** and **Map** field and selecting the incomping input field as a new **value**.

![alteryx-custom-parameters](/img/content/alteryx-custom-parameters-override.PNG){:class="img-responsive"}

You can read more about custom parameters [here](../../advanced-techniques/user-defined-variables).

If the connection to the specified Xtract Universal server could be established without any errors, the tool will have a tooltip in the following format: [Extraction] @ [Server]

![alteryx-full-workflow](/img/content/alteryx-full-workflow.PNG){:class="img-responsive"}