
Eine Formel wird in C#.NET-ähnlicher Syntax geschrieben und muss mit #{ anfangen und #} enden.<br>
Grundlegende .NET Typen und die entsprechenden Operationen aus dem System-Namensraum der .NET-Umgebung sowie Verkettungen werden standardmäßig unterstützt. 

Beispiele:

| Beschreibung                           | Eingabe                                                                         | Ausgabe              |
|---------------------------------------|-------------------------------------------------------------------------------|---------------------|
| Jetziges Datum und Zeitstempel            |``` #{ DateTime.Now}#```                                                             | 23.07.2013 10:17:37 |
| Datum vor 5 Tagen                       | ```#{ DateTime.Now.AddDays(-5).ToString("d") }#```                                 | 18.07.2013          |
| Jetziges Datum                          | ```#{ DateTime.Now.ToShortDateString() }#```                                        | 23.07.2013          |
| Jetziges Datum im SAP-Format            | ```#{ DateTime.Now.ToString("yyyyMMdd") }#```                                       | 20130723            |
| Jetziges Jahr mit "0101" verketten | ```#{ String.Concat(DateTime.Now.Year.ToString(), "0101") }#```                     | 20130101            |
| Jetziges Jahr mit "0101" verketten | ```#{ String.Concat(DateTime.Now.ToString("yyyy"), "0101") }#```                    | 20130101            |
| Jetziges Jahr mit "0101" verketten | ```#{ String.Concat(DateTime.Now.ToString("yyyyMMdd").Substring(0,4), "0101") }#``` | 20130101            |


### Verwendung

Script-Ausdrücke können sowohl für die [Where-Bedingung](../table/where-bedingung) einer Tabelle als auch in den Destination Settings mittels [Custom SQL](https://help.theobald-software.com/de/xtract-universal/xu-zielumgebungen/microsoft-sql-server/sql-server-custom-sql) (Xtract Universal Beispiel) verwendet werden. 

### IF-Abfrage

Eine IF-Abfrage hat die folgende Syntax: iif(bool condition, string trueResult, string falseResult)  

Beispiel:

| Beschreibung                                                        | Eingabe                                             | Ausgabe |
|--------------------------------------------------------------------|---------------------------------------------------|--------|
| Wenn wir im 7. Monat sind, dann "July" ausgeben, sonst "Unknown"  | #{ iif(DateTime.Now.Month==7, "July","Unknown")}# | July   |

## Definierte Ausdrücke

### Definierte Methoden

bool ExistsTable(string tableName): überprüft, ob die Tabelle auf der Zieldatenbank existiert.


### Definierte Eigeschaften

Folgende Ausdrücke sind definiert und können verwendet werden: 

```
#{ Extraction.TableName }# : Name der Extraktion 
#{ Extraction.RowsCount }# : Anzahl der extrahierten Datensätze
#{Extraction.RunState}#: Status der Extraktion (Running, FinishedNoErrors, FinishedErrors)
#{(int)Extraction.RunState}#: Status der Extraktion als Zahl (2 = Running, 3 = FinishedNoErrors, 4 = FinishedErrors)
#{Extraction.Timestamp}#: Zeitstempel der Extraktion
```

Sehen Sie auch das [Beispiel](https://help.theobald-software.com/de/xtract-universal/xu-zielumgebungen/microsoft-sql-server/sql-server-custom-sql) für die Verwendung von definierten Ausdrücken mittels Custom-SQL in den Destinationseinstellungen.


### Unterstützte Datentypen

Folgende .NET-Datentypen werden unterstützt:<br>
Object, object<br>
Boolean, bool<br>
Char, char<br>
String, string<br>
SByte<br>
Byte, byte<br>
int<br>
Int16<br>
UInt16<br>
Int32<br>
UInt32<br>
long<br>
Int64<br>
UInt64<br>
Single<br>
Double, double<br>
Decimal, decimal<br>
DateTime<br>
TimeSpan<br>
Guid<br>
Math und<br> 
Convert<br>

### Unterstützte Schlüsselwörter 

Folgende Schlüsselwörter werden unterstützt: <br>
true, false und null.

Informationen zu den [.NET-Typen](https://docs.microsoft.com/de-de/dotnet/api/system?redirectedfrom=MSDN&view=netframework-4.7.2) und [Format für Datum und Zeit](https://docs.microsoft.com/de-de/dotnet/standard/base-types/custom-date-and-time-format-strings) finden Sie im MSDN.


 
