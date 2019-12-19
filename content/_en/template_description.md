---
layout: page
title: Template for descriptions
description: Template for creating online help content
permalink: /:collection/template_description
weight: 0
---
### About the template
Especially for "landing pages" that are placed before a bigger section it is advisable to write an introduction:
In this section... / this section gives an overview.../ the following section is about...
the template which is a guideline for simplifying the creation of product descriptions. 
<!--Einleitung und kurze Einführung worum es im Folgenden geht, bitte kein "Will"-Future verwenden-->
The correct headers for the page is H3 and H4 for the subsections. Don't only use bold, otherwise the anchors can not be set at all. 
<!---Überschrift 3, bitte nicht nur fett verwenden, sonst können die Anker gar nicht gesetzt werden-->
### About function descriptions
<!--Unterüberschrift. Optional, wird gesetzt wenn es sinnvoll ist-->
This section does not contain any procedural steps.
Make sure to keep the product descriptions separate from the instructions with steps, when possible.
Each author should first consider whether he wants to describe the product or a part of it or a function (e.g., architecture or use case). This rule of thumb should be considered per section.
If it makes sence to incorporate description in one subsection and procedural steps in the other subsection within the document, the author is free to do so.
Or whether he wants to show the user steps so that the user can perform a particular task. The given template is for a function description. For the creation of the instructions, please use the other template.
<!--Die Produktbeschreibungen sollen möglichst getrennt von den Handlungsanweisungen gehalten werden. 
Jeder Autor sollte zunächst überlegen, ob er eine Funktion beschreiben will (z.B. Architektur oder Use Case)
oder ob er dem Benutzer Schritte aufzeigen will, damit er eine bestimmte Aufgabe Ausführen kann. Die vorliegende Vorlage ist für eine Funktionsbeschreibung. Für die Erstellung der Handlungsanweisungen, verwendet bitte die andere Vorlage.-->

-----------

### Markings in the text
The ULs (unordered lists) are used for listing the elements, when the order is not important.<br>
The OLs (ordered lists) should be used for instructions and steps if possible, see other template. 
<!--Eine UL (unordered list) wird für die Auflistung verwendet. OL (ordered list) soll möglichst für Handlungsanweisungen und Schritte verwendet werden s. anderes Template-->
- Buttons: bold & square brackets - **[Edit]** 
- URLbuttons: just bold - **Subscriptions**
- Fields within a window: bold - **Name** 
- Input values: italics - *MATNR*
- Drop-down menu options: italics - *EC5* 

------

### Tables
<!---Einfache Tabellen verwenden, Markierungen in Tabellen möglichst vermeiden-->
Tables should be kept simple. No markings (bold, italics etc.) in tables, when possible.

First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column

------

### Notes, Warnings etc.
There are three main types of warning messages with the corresponding colors.

Signal word| Color
------------ | -------------
Note |Blue
Warning | Yellow
Tip| Green
Recommendation | Green


#### Note:
Notes is additional information and can be formulated freely.
 <!--Note /Hinweis ist eine zusätzliche Information.-->
<div class="alert alert-info">
  <i class="fas fa-info-circle"></i> <strong>Note:</strong> The corresponding SQL command is generated dynamically and executed on the SAP server.
</div>

<!--Dieser Block wird später von Erwin programmiert und kann leichter befüllt werden. Note / Hinweis (DE) soll verwendet werden, wenn zusätzliche Informationen gegeben werden, die nicht direkt Teil der Beschreibung sind--->

#### Warning - not typical for function descriptions:
The general guideline is to not use many "Warnings" as the less "Problems" the product can cause, the better is the product. The warning **must** be placed in front of the possible issue and not after.
If possible, the warning note should be formulated according to the following principle:
- Type & source of the problem, use bold and break;
- Cause with an explanation of the threat, break;
- Remedy with steps to avoid the threat.

<!-- Dieser Block wird später von Erwin programmiert und kann leichter befüllt werden. 
Warning / Warnung wird verwendet, wenn beim Missachten etwas tatsächlich passieren kann. z.B. Datenverlust. Dieser Hinweis wird öfter in den Handlungsanweisungen verwendet.
Der Warning-Hinweis soll möglichst nach dem folgenden Prinzip formuliert werden:
- Type & source of the problem, use bold and <br>:
- Cause with an explanation of the threat + <br>:
- Remedy:
 -->

<div class="alert alert-warning">
  <i class="fas fa-exclamation-triangle"></i> <strong>Warning:</strong> 
  <!--Type & source of the problem, use bold and <br> --> <strong>Data loss</strong> <br>
  <!--- Cause with an explanation of the threat + <br>: ---> A big amount of information is collected when debug logging is activated. This can decrease the capacity of your hard drives dramatically.<br>
  <!---Remedy:--> Activate the debug logging only when necessary, e.g., upon request of the support team.
</div><br>

#### Tip & Recommendation:
Tips and recommendations can be formulated freely. <br>

**Tip:** This is a tip.<br>
Tips can be an alternative solution or additional information. For example, this can also be looked up in SAP using this transaction.
<!--Soll verwendet werden, wenn es um eine alternative Lösung sich handelt oder etwas zusätzliches angesprochen werden kann. z.B. dies kann über diese Transaktion auch in SAP nachgeschaut werden. Wenn es soweit ist, stellt Erwin ein grünes Kästchen für die Tipps und Empfehlungen zur Verfügung-->
**Recommendation:** This is a recommendation.<br>
A recommendation from Theobald Software is a piece of information that comes from the experience of the team or from best practices. Make sure to avoid "we" and "our" when formulating recommendations.
<!--Eine Recommendation von Theobald Software, die aus der eignen Erfahrung oder aus Best Practices kommt - hiermit wird das "we" und "our" vermieden-->
<div class="alert alert-success">
  <i class="fas fa-lightbulb"></i> Basics of the product Xtract Universal are described in the section <a href= "https://help.theobald-software.com/en/xtract-universal/getting-started-table" class="alert-link">Getting Started with Table</a>.<br>
</div>

------
### Window, not ~~dialog~~

The window "Connection settings" opens. The designations or titles of the windows should be put into quotation marks.
<!--Die Bezeichnungen der Fenster soll in Anführungszeichen gesetzt werden-->
In the main menu bar of the designer there are additional adjustable settings:   **Servers > Settings**.
The symbol ">" can be used to demonstrate menu jumps. 
<!--Mit dem Symbol ">" können Menusprünge ausgedrückt werden-->

----

### Paths & URLs

#### URLs
Don't use the "full qualified URLs". Square brackets should contain a meaningful description, not just "click here" or "click me".

For more information on defining of the extractions, see [Define an Extraction](https://help.theobald-software.com/en/xtract-universal/getting-started-table/define-a-table-extraction) with the "SAP Table or View" component as an example.

<!-- Nicht den "full qualified URL" verwenden.
In den eckigen Klammern soll eine sinnvolle Bezeichung stehen, nicht z.B. nur "hier" oder "Klick mich".-->
#### Paths
Paths should be marked with the element Inline Code. If it makes sense, the paths can be placed into a new line, by using break.

You find the installation file in the following folder:

`C:\Program Files\ERPConnect Services\ERPConnectServices.NintexWorkflowActions.exe`

<!--Pfade sollen mit dem Element `Inline Code` markiert werden. Wenn es sinnvoll ist, können die Pfade eingerückt werden--->

#### Code
Code should be marked with the element Inline Code.

Use also the automatic highlighting of keywords based on programming language:

```javascript
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
```

```sql
UPDATE [dbo].[KNA1] 
SET [Extraction_Date] = '#{DateTime.Now}#' 
WHERE [Extraction_Date] IS NULL;
```

<!--Code soll mit dem Element inline code ausgezeichnet werden-->


### Examples - Blockquotes

>This is an example.

<!--Kann für Beispiele verwendet werden-->


