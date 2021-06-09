Nachdem ein Report ausgewählt wurde, muss nun entweder eine Variante und/oder entsprechende Selektionskriterien hinterlegt werden. Es sei an dieser Stelle ausdrücklich empfohlen, alle Selektionen, die nicht unmittelbar dynamisch sein müssen, über eine Variante einzuschränken, um die Übersicht zu behalten. Oftmals sind in dem Report auch Standardfelder belegt, die Sie ohne Variante von Hand füllen müssten.

Einzelne Selektionsfunktionen (Parameter) können über den Edit-Link in der Liste links oben eingeschränkt werden.


![Report-Variants-And-Selections](/img/content/Report-Variants-And-Selections.png){:class="img-responsive"}


Bei den Parametern kann es sich um Einzelwerte, einen Intervall oder um eine komplexe Selektion handeln. 

Bei einer komplexen Selektion springen Sie über den Edit-Link in ein neues Fenster ab. <br>
Natürlich können in die Textfelder auch Variablen eingetragen werden (wie im Bild zu sehen).<br>

Bitte fügen Sie ein @ direkt vor den Wert, um es als Variable zu markieren.

Das folgende Bild zeigt eine komplexe Selektion:

![Parameters-2](/img/content/Parameters-2.png){:class="img-responsive"}

Das Feld Sign hat zwei Optionen: 

- Include 
- Exclude 

Mit dieser Funktion können Sie jene Werte wählen, die Sie für das Ergebnis ein- bzw. ausschließen wollen. 

Das Feld Option enthält den logischen Operator für die Bedingung: <br>

| logischer Operator   | Beschreibung   |
|---------------|------------------------------|
| "="     | ist gleich        |
| "!=" | ist ungleich     |
| "<"     | kleiner als   | 
| "<="      | kleiner oder gleich   | 
| ">"    | größer als   | 
| ">="   | größer oder gleich | 
| "[]" | zwischen (Intervall) | 
| "]["       | nicht zwischen (Intervall) | 
| " * "    | enthält (Like) | 


Die Spalte Low Value muss bei jedem Operator gefüllt werden.<br>
Die Spalte High Value wird nur von den Operatoren verwendet, welche einen zweiten Parameter erwarten. 

{% include _content/de/sap-data-format.md  %}