---
ref: xtract-is-03
layout: page
title: Xtract IS for Azure
description: Xtract IS for Azure
product: xtract-is
parent: xtract-is
childidentifier: for-azure
permalink: /:collection/:path
weight: 3
lang: en_GB
old_url: /Xtract-IS-EN/default.aspx?pageid=xtract_is_for_azure
progressstate: 3
---

*Xtract IS for Azure* is a solution that allows running SSIS packages, containing Xtract IS components, on an [Azure-SSIS Integration Runtime (IR), based on Microsoft's Azure Data Factory v2 (ADFv2)](https://azure.microsoft.com/en-us/blog/lift-sql-server-integration-services-packages-to-azure-with-azure-data-factory/).

With Azure-SSIS IR, SSIS packages will still be developed on a local (on prem) Visual Studio/SSDT environment.
However, instead of deploying those packages to an on prem SSIS server, those packages will be deployed to an Azure-SSIS IR (part of ADFv2) to be scheduled and run in the Azure cloud.

### Architecture

![XISforAzure_Architecture](/img/content/xis/Xtract_IS_for_Azure.png){:class="img-responsive"}

Xtract IS for Azure makes sure, that Azure-SSIS IR supports SSIS packages, containing Xtract IS components for connecting to and extracting data from SAP. You need to make sure that your SAP system is accessible from your Azure cloud environment, for instance through a VPN tunnel.

Xtract IS for Azure is based on the existing Xtract IS version, that's been around for on prem installations for years now.
Hence Xtract IS for Azure offers exactly the same SAP data extraction functionality as Xtract IS.

**Prerequisites and installation on a Visual Studio/SSDT environment** (for development of SSIS packages) don't differ from the [existing Xtract IS setup](./introduction/installation).

**Prerequisites and installation on an Azure-SSIS IR** (for running SSIS packages) are described in the following chapter.

{% include _content/table-of-contents.html parent=page.childidentifier collection=site.en %}
