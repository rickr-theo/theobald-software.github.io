
{% include _content/en/xis-specific/parameterization/parametrization-about.md  %}

### Custom Properties

The *Custom Properties* define the properties unique to the Xtract OHS component. <br>
When parameterizing the OHS component using SSIS variables or Data Flow Properties, the *Custom Porperties* are overwritten.

List of relevant *Custom Properties* of the OHS component:

|Property|Comment|
|:----|:----|
| *ConvertsDates* | When this property is set to *True* (default) SAP date fields (YYYYMMDD) assume the SSIS pipeline type DT_DBDATE instead of DT_WSTR. In case of invalid data in SAP date fields, the following date conversions are applied: <br>*InvalidDateReplacement*, *MaxDateReplacement*, *MinDateReplacement*. |
| *ConvertsTimes* | Enable or disable conversion of SAP times.|
| *InvalidDateReplacement* | Allows the replacement of an invalid date format. The default value of the property is *1970-01-02*. <br>To use the property enter a replacement value for invalid SAP dates, such as '20190132' (January 32nd  2019) in the format yyyy-mm-dd. The value NULL is supported.|
| *MaxDateReplacement* | Allows replacing the SAP dates with the year 9999. The default value of the property is 2099-12-31. <br>To use the property enter a replacement value in the format yyyy-mm-dd that contains the year ‘9999’. Example: ‘99990101’ (January 1st 9999). The value NULL is supported.|
| *MinDateReplacement* | Allows replacing the SAP dates with the year *0000*. The default value of the property is 1970-01-01. <br>To use the property enter a replacement value in the format yyyy-mm-dd that contains the year '0000'. Example: '00000000'. The value NULL is supported.|

### Parameterization using Data Flow Properties
The following *Custom Properties* can be parameterized:

|Property Name|Description|
|:----|:----|
| *[Xtract OHS].[ConvertsDates]*| Enable or disable conversion of SAP dates, see [Custom Properties](#custom-properties). |
| *[Xtract OHS].[ConvertsTimes]*| Enable or disable conversion of SAP times. |
| *[Xtract OHS].[InvalidDateReplacement]*| In case of invalid date values you need to enter a default date value. Every invalid value will be converted into this value, see [Custom Properties](#custom-properties).|
| *[Xtract OHS].[MaxDateReplacement]*| Converts the SAP date 9999XXXX to the entered value, see [Custom Properties](#custom-properties). |
| *[Xtract OHS].[MinDateReplacement]*| Converts the SAP date 00000000 to the entered value, see [Custom Properties](#custom-properties).|


### Parameterization using SSIS Variables
The following fields and/or *Custom Properties* of the component allow entry of an SSIS variable:

|Field Name|Comment|
|:----|:----|
| *Package Size* | Sets the package size in bytes, see [Extraction Settings](./settings#extraction-settings).|
| *Row Limit* | Corresponds to the field *Row limit* in the OHS component, see [Extraction Settings](./settings#extraction-settings).|
| *Gateway host* | Corresponds to the field *Gateway host* in the OHS component, see [Third party tool Settings](./settings#third-party-tool-settings). |
| *Gateway service* | Corresponds to the field *Gateway service* in the OHS component, see [Third party tool Settings](./settings#third-party-tool-settings).|
| *Program ID* | Corresponds to the field *Program ID* in the OHS component, see [Third party tool Settings](./settings#third-party-tool-settings).|

****
#### Related Links
- [How to Use Expressions for Properties](../parameterization/parameterization-prop#how-to-use-expressions-for-properties) 
- [Dynamization of WHERE conditions of the XIS table components](https://kb.theobald-software.com/xtract-is/Dynamization-of-WHERE-conditions-of-the-XIS-table-components)
- [How to use SSIS Variables with Xtract Components](../parameterization/parameterization-var) 
- [Integration Services (SSIS) Variables](https://docs.microsoft.com/en-us/sql/integration-services/integration-services-ssis-variables?view=sql-server-ver15)

