### Look up a Report or Transaction
1. In the main window of the component click the **[Search]** button (magnifying glass symbol). The window “Report Lookup” opens.
2. In the field **Report Name** (1) enter the name of a report using wildcards (*) if needed. Alternatively you can search for SAP Transaction Codes by selecting TCODE.
![Look-Up-Report](/img/content/Look-Up-Report.png){:class="img-responsive"}
3. Click **[Search]** (magnifying glass symbol) and select the report of your choice from the displayed list (3).
4. Click **[OK]** (4) to confirm.


### Variants and Selections

1. Choose a variant from the drop-down-list *Variant* (1). <br>
![Report-Variants-Section](/img/content/Report-Variants-Selection.png){:class="img-responsive"}
2. Choose a selection criterion you want to change or dynamize from the list in the section *Selection Screen* (2).
3. Click the **[Edit]** button next to the selection you want to edit. The window "Edit Selection" opens.
![Report-Edit-Selections](/img/content/Report-Edit-Selections.png){:class="img-responsive"}
4. Choose if the selection is to be included or excluded (3) from the extracted data.
5. Select an operator (*Equal*, *GreaterThan*, etc.) from the *Option* drop-down list (4). 
6. Enter the selection in the respective *Low* and *High* fields. The *High* field is active for input when the *between* or *not between* operator was selected.
7. Optional: click **[Add Selection]** (5) to add conditions.
8. Click **[OK]** (6) to confirm the selections.

{: .box-note }
**Note:** For more information on variants and selections, see [Variants and Selections](./variants-and-selections).<br>
For more information on how to use selections with parameters, see [Runtime Parameters](./report-edit-runtime-parameters).

### Define Report Columns

1. Click ** [Automatically detect columns]** to execute the report based on the selected variant or selections and detect columns automatically.<br>
![Report-automatic-columns](/img/content/Report_new_automatic_columns.png){:class="img-responsive"}
2. Click **[Load Preview]** to display the rows in the preview screen.
3. Check if the automatically detected columns are accurate. When automatic column detection is not possible, the report’s column names, widths and offsets must be set manually, see [Define Columns manually](./report-columns-define#define-columns-manually).

{: .box-note }
**Note:** For more information on how to define report columns automatically and manually, see [Define Columns](./report-columns-define).


#### Related Links
- [Types of ABAP Reports](https://wiki.scn.sap.com/wiki/display/ABAP/Types+of+Reports)


<!---
### Further reading..

Most reports can be extracted in dialog mode. Some reports have to be extracted in background mode.
Reports that may cause issues:
- Reports w/o column separator '|', such as RM07MBST
- Reports with a '|' in the actual data.
- Reports, that split a line over multiple lines
- Interactive Reports that are meant for reporting purposes and offer navigational features.
- Reports created via report painter

{: .box-tip }
**Tip:** Instead of hard coding manual selections or variants, use parameters. This allows setting selections and variants at runtime.

--->