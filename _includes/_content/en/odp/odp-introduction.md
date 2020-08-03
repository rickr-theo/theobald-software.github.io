
### About ODP 

The ODP component can be used to extract data via the SAP Operational Data Provisioning (ODP) framework. 

ODP is a framework in SAP ABAP applications for transferring data between systems. 
It provides a technical infrastructure for data extraction and replication from different SAP (ABAP) Systems, e.g. 
- ECC 
- S/4 HANA
- BW and 
- BW/4 HANA. 

It allows to subscribe to (ODP Consumer) and publish various data providers (ODP Providers). Data can be sent to different ODP Consumers (also several in 
parallel).  

Operational data provisioning supports also delta mechanisms. 
With SAP BW/4HANA, Operational Data Provisioning (ODP) becomes the central infrastructure for data extraction and replication from SAP (ABAP) applications to a SAP BW/4HANA Data Warehouse. 
<br/>
![ODP Component](/img/content/odp/odp-component-general.png){:class="img-responsive"}
<br/>
ODP provide data transfer from the following Providers (also called Provider Context): 
- SAP DataSources (Extractors) 
- ABAP CDS Views 
- SAP BW and SAP BW/4HANA InfoProviders
- SAP HANA Information Views in SAP ABAP based Systems 

Depending on the connected SAP source system you would see the available provider context. 
See below the ODP provider content available in our demo ECC system. 
<br/>
![ODP Provider Context from an ERP System](/img/content/odp/odp-component-context-erp.png){:class="img-responsive"}

See below the ODP provider content available in our demo BW/4 HANA system. 
<br/>
![ODP Provider Context from an BW/4 HANA System](/img/content/odp/odp-component-context-bw.png){:class="img-responsive"}


### Technical prerequisites

There are a few prerequisites, that need to be fulfilled on the SAP side, when using ODP. SAP has released a number of SAP notes that deal with questions around ODP. These notes do apply when using our ODP component, as far as the SAP source system is concerned.

- [1931427 - ODP Data Replication API 2.0](https://launchpad.support.sap.com/#/notes/1931427)
- [2232584 - Release of SAP extractors for ODP replication (ODP SAPI)](https://launchpad.support.sap.com/#/notes/2232584)
- [1560241 - Release of DataSources for ODP data replication API](https://launchpad.support.sap.com/#/notes/1560241)

