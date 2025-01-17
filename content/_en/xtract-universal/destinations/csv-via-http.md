---
ref: destinations-11
layout: page
title: Web Service - CSV
description: CSV (via HTTP)
product: xtract-universal
parent: destinations
permalink: /:collection/:path
weight: 12
lang: en_GB
old_url: /Xtract-Universal-EN/default.aspx?pageid=csv-via-http
progressstate: 5
---

This destination is a generic CSV stream over HTTP. 
The CSV (via HTTP) destination is supported by many products. The following products have been tested: Layer2, INFONEA and KNIME. 

## Connection
### Adding a Destination

1. In the main window of the Designer, navigate to **Server > [Manage Destinations](./managing-destinations)**. The window “Manage Destinations” opens.
2. Click **[Add]** to create a new destination. The window "Destination Details" opens.
3. Enter a **Name** for the destination.
4. Select the destination **Type** from the drop-down menu.

### Destination Details
![CSV-Destination-Details](/img/content/xu/CSV-Destination-Details.png){:class="img-responsive"}

{% include _content/en/xu-specific/destinations/general/csv-settings.md %}														 

{% include _content/en/xu-specific/destinations/general/convert-encoding.md %}	

****
## Related Links
- KNIME Integration via [SAP Reader (Theobald Software)](https://kb.theobald-software.com/xtract-universal/knime-integration-via-sap-reader)
- [Dynamic Runtime Parameter within KNIME Workflow](https://kb.theobald-software.com/xtract-universal/dynamic-runtime-paramater%20within-KNIME-workflow)
