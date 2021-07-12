
{% include _content/de/xis-specific/parametrisierung/parametrization-about.md  %}

### Custom Properties

Die Eigenschaften der Xtract ODP Komponente wird in den *Custom Properties* der Komponente definiert. <br>
Bei der Parametrisierung der Komponente durch SSIS Variablen oder Data Flow Properties werden diese Eigenschaften überschrieben.

Liste der *Custom Properties* der ODP Komponente:

|Property|Beschreibung|
|:----|:----|
| *ConvertsDates* | Aktiviert oder deaktiviert die Umwandlung von SAP Daten.|
| *ExtractDataOnDeltaInit* | Führt eine Delta-Initialisierung mit oder ohne Datenextraktion aus, siehe [Update Mode](./odp-functions-ov#load-verfahren-update-mode).|
| *HierarchyName* | Nur für Datenquellen vom Typ Hierarchy, siehe [Select Hierarchy](./odp-functions-ov#select-hierarchy).|
| *InvalidDateReplacement* | Im Fall unzulässiger Werte für Daten, geben Sie hier einen Standardwert ein. Jedes ungültige Datum bekommt diesen Wert zugewiesen.|
| *MaxDateReplacement* | Verwendet den eingegebenen Wert anstelle des SAP Datums 9999XXXX.|
| *MinDateReplacement* | Verwendet den eingegebenen Wert anstelle des SAP Datums 00000000.|
| *PackageSize* | Wählt die Paketgröße in Bytes, siehe [Advanced Settings](./odp-functions-ov#advanced-settings).|
| *SubscriptionSuffix* | Fügt dem von der ODP Komponente erstellten ODP Abonnement ein Suffix hinzu.|
| *UpdateMode* | Stellt den Update Mode einer Extraktion ein. Erlaubt Werte sind: (F)ull, (D)elta and (R)ecovery, siehe [Update Mode](./odp-functions-ov#load-verfahren-update-mode).|
| *UserComponentTypeName* | |

### Parametrisierung mit Data Flow Properties
Die folgenden *Custom Properties* können parametrisiert werden:

|Property|Beschreibung|
|:----|:----|
| *[Xtract ODP].[SubscriptionSuffix]*| Fügt dem von der ODP Komponente erstellten ODP Abonnement ein Suffix hinzu. Das erlaubt die Verwendung von SSIS Paketen in zwei unterschiedlichen SSIS Umgebungen, z.B. greifen QA und PROD. auf dasselbe SAP-System zu. Das Suffix erlaubt auch die Erstellung von Abonnenten für jede SSIS Umgebung.|
| *[Xtract ODP].[UpdateMode]*| Stellt den Update Mode einer Extraktion ein. Erlaubt Werte sind: (F)ull, (D)elta and (R)ecovery, siehe [Update Mode](./odp-functions-ov#load-verfahren-update-mode).|
| *[Xtract.ODP].[ExtractDataOnDeltaInit]*| Führt eine Delta-Initialisierung mit oder ohne Datenextraktion aus, siehe [Update Mode](./odp-functions-ov#load-verfahren-update-mode).|
| *[Xtract.ODP].[HierarchyName]*| Nur für Datenquellen vom Typ Hierarchy. Geben Sie den Namen der zu extrahierenden Hierarchie ein, siehe [Select Hierarchy](./odp-functions-ov#select-hierarchy). |
| *[Xtract.ODP].[PackageSize]*| Wählt die Paketgröße in Bytes, siehe [Advanced Settings](./odp-functions-ov#advanced-settings). |
| *[Xtract.ODP].[ &lt;Selection Parameter &gt;]*| Auswahlparameter, die in der Komponente definiert sind, sind in den *Properties* der Komponente verfügbar, siehe [Edit Parameters](./odp-functions-ov#parameter-bearbeiten---edit-parameters). |

### Parametrierung mit SSIS Variablen
Die folgenden Felder und/oder *Custom Properties* der Komponente erlauben die Verwendung von SSIS-Variablen:

|Feldname|Beschreibung|
|:----|:----|
| *Edit*|Geben Sie eine SSIS-Variable als Auswahlkriterium ein, siehe [Selektion und Filter](./odp-functions-ov#selektion-und-filter).|
| *Package Size* | Entspricht dem Feld *Package Size* in der OHS Komponente, siehe [Fortgeschrittene Einstellungen](./odp-settings#fortgeschrittene-einstellungen).|

****
#### Related Links
- [Ausdrücke für Properties verwenden](../parametrisierung/parametrisierung-properties#ausdrücke-für-properties-verwenden) 
- [Dynamization of WHERE conditions of the XIS table components](https://kb.theobald-software.com/xtract-is/Dynamization-of-WHERE-conditions-of-the-XIS-table-components)
- [How to use SSIS Variables with Xtract Components](../parametrisierung/parametrisierung-variablen) 
- [Integration Services-Variablen (SSIS)](https://docs.microsoft.com/de-de/sql/integration-services/integration-services-ssis-variables?view=sql-server-ver15)