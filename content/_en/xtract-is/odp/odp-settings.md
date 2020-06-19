---
ref: xis-odp-settings
layout: page
title: ODP Settings
description: ODP Settings
product: xtract-is
parent: odp
permalink: /:collection/:path
weight: 6
lang: en_GB
progresstate: 5
---

{% include _content/en/odp/odp-settings-update_mode.md %} 
{% include _content/en/odp/odp-settings-subscriptions.md %}
{% include _content/en/odp/odp-settings-filtering.md %} 
{% include _content/en/odp/odp-settings-parameters.md %} 

### To display parameters within SSIS
Parameters appear as properties of the Xtract ODP object as well as the SSIS Data Flow. The parameters and properties be populated at SSIS package runtime using standard SSIS functionality, such as expressions, variables, etc. 
![ODP properties](/img/content/xis/odp_parameter.png){:class="img-responsive"}
