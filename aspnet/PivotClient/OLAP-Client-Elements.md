---
layout: post
title: PivotClient Elements | PivotClient | ASP.NET | Syncfusion
description: PivotClient elements
platform: aspnet
control: PivotClient
documentation: ug
---

# Pivot client: Elements

## Cube selector

The cube selector allows you to select any one of the cubes available in the connected database. This can be achieved with a drop-down list displaying the list of cube names. By selecting a cube from the drop-down list, the corresponding cube elements get loaded.

![Cube Selector in ASP NET pivot client control](OLAP-Client-Elements_images/cubeSelector.png)

## Cube dimension browser

The cube dimension browser is a tree view like structure that organizes the cube elements such as dimensions, hierarchies, measures, etc., from the selected cube into independent logical groups.

### Drag and drop

You can alter the report on fly through the drag-and-drop operation.

![Treenode drop in ASP NET pivot client control](OLAP-Client-Elements_images/ClientTreeview_Drop.png)

### Context menu

You can alter the report by using the context menu.

![Context menu for tree view elements in ASP NET pivot client control](OLAP-Client-Elements_images/ClientTreeview_Menu.png)

### Types of nodes in cube dimension browser

* **Display folder**: A folder that contains a set of similar elements.
* **Measure**: Quantity available for analysis.
* **Dimension**: A name given to the parts of the cube that categorizes the data.
* **Attribute hierarchy**: Level of attributes down the hierarchy.
* **User-defined hierarchy**: Members of a dimension in a hierarchical structure.
* **Level**: Denotes a specific level in the category.
* **Named set**: A collection of tuples and members, that can be defined and saved as a part of cube definition.

### Attribute hierarchy

Attribute hierarchy contains the following levels:

* A leaf level contains distinct attribute member and each member of the leaf level is also known as a leaf member.
* Intermediate levels if the attribute hierarchy is a parent-child hierarchy.
* An optional (all) level (IsAggregatable=True) contains the aggregated value of the attribute hierarchy's leaf members, with the member of the (all) level also known as the (all) member.

### User-defined hierarchy

User-defined hierarchy organizes the members of a dimension into hierarchical structure and provides navigation paths in a cube. For example, take a dimension table that supports three attributes such as year, quarter, and month. The year, quarter, and month attributes are used to construct a user-defined hierarchy, named calendar, in the time dimension that relates to all levels.

### Differentiating user-defined hierarchy and attribute hierarchy

* User-defined hierarchy contains more than one level whereas attribute hierarchy contains only one level.
* User-defined hierarchy provides the navigation path between the levels taken from attribute hierarchies of the same dimension.
* The user-defined hierarchy and attribute hierarchy are represented in different ways as shown in the following table:

### Symbolic representation of the nodes in cube dimension browser

<table>
<tr>
<th>Icon</th>
<th>Name</th>
<th>Node type</th>
<th>Is Draggable</th>
</tr>
<tr>
<td>{{ '![Folder icon in ASP NET pivot client control](OLAP-Client-Elements_images/Folder icon.png)' | markdownify }}</td>
<td>Display Folder</td>
<td>Display Folder</td>
<td>False</td>
</tr>
<tr>
<td>{{ '![Measure icon in ASP NET pivot client control](OLAP-Client-Elements_images/Measure icon.png)' | markdownify }}</td>
<td>Measure</td>
<td>Measure</td>
<td>True</td>
</tr>
<tr>
<td>{{ '![Dimension icon in ASP NET pivot client control](OLAP-Client-Elements_images/Dimension icon.png)' | markdownify }}</td>
<td>Dimension</td>
<td>Dimension</td>
<td>True</td>
</tr>
<tr>
<td>{{ '![User defined hierarchy icon in ASP NET pivot client control](OLAP-Client-Elements_images/user defined hierarchy.png)' | markdownify }}</td>
<td>User Defined Hierarchy</td>
<td>Hierarchy</td>
<td>True</td>
</tr>
<tr>
<td>{{ '![Attribute hierarchy in ASP NET pivot client control](OLAP-Client-Elements_images/attribute hierarchy.png)' | markdownify }}</td>
<td>Attribute Hierarchy</td>
<td>Hierarchy</td>
<td>True</td>
</tr>
<tr>
<td>{{ '![First level icon icon in ASP NET pivot client control](OLAP-Client-Elements_images/first level.png)' | markdownify }}<br/>
{{ '![](OLAP-Client-Elements_images/second level.png)' | markdownify }}<br/>
{{ '![](OLAP-Client-Elements_images/third level.png)' | markdownify }}</td>
<td>Levels (in order)</td>
<td>Level Element</td>
<td>True</td>
</tr>
<tr>
<td>{{ '![NamedSet icon in ASP NET pivot client control](OLAP-Client-Elements_images/names set element.png)' | markdownify }}</td>
<td>Named Set</td>
<td>Named Set</td>
<td>True</td>
</tr>
</table>

## Axis element builder

The axis element builder allows you to build the elements in the axes of the pivot client. This supports three axes namely categorical, series, and slicer. Based on the construction of axes, the pivot grid and the pivot chart will display the resultant data.

### Categorical (column)

The categorical axis defines one or more elements that are displayed along the chart’s Y-axis as labels in the columns of the grid. If more than one dimension is present on the categorical axis, then the chart/grid will stack each dimension. The stacking order of dimensions is based on the order that they appear on the categorical axis.

### Series (row)

The series axis defines one or more that are displayed along the chart’s X-axis as labels in the rows of the grid. If more than one dimension is present on the series axis, then the chart/grid will stack each dimension. The stacking order of dimensions is based on the order that they appear on the series axis.

### Slicer

The slicer axis is used as a filter to narrow the focus of the multidimensional data displayed in the chart/grid. The slicer axis allows you to analyze a member of the dimension in-depth. To display the member’s data in the slicer, the corresponding member must not be present on both categorical axis and series axis.

![Axis element builder in ASP NET pivot client control](OLAP-Client-Elements_images/Axis Element Builder.png)

### Split button

The split button highlights the elements in the axis element builder, and holds measures, dimensions, and named sets. When a dimension/hierarchy/level/named set node is dragged and dropped from the cube dimensional browser into the axis element builder, a split button is created and displayed along with the corresponding dimension/named set caption.

When a measure node is dragged and dropped, the axis element builder will create a split button for holding the measures. The next time a measure is added, it will maintain the same single split button to hold the entire measure collection.

The split buttons can be removed with the help of remove button which is available on its side.

![Measure split button in JavScript pivot client control](OLAP-Client-Elements_images/Measure split button.png)

![Dimension split button in ASP NET pivot client control](OLAP-Client-Elements_images/date.png)

### Addition elements to an axis

The measure, dimension, hierarchy, level, and named set elements can be dragged from the cube dimension browser and dropped into the axis element builder at the desired position by using the drag-and-drop operation. These elements can be moved from one axis to another by dragging an appropriate split button and dropping them at the desired position.

![Adding elements to an axis in ASP NET pivot client control](OLAP-Client-Elements_images/addelement.png)

### Remove elements from an axis

To remove measures, dimension, hierarchy, level, and named set elements from the axis element builder, click the remove button available next to the split button.

![Removing elements from an axis in ASP NET pivot client control](OLAP-Client-Elements_images/removeelement.png)

### Rearrange elements in an axis

Rearranging can be done by dragging and dropping the elements at the desired position.

![Rearranging elements in an axis of ASP NET pivot client control](OLAP-Client-Elements_images/rearrangeelement.png)

![Rearranged elements in ASP NET pivot client control](OLAP-Client-Elements_images/rearrange 1.png)

### Context menu

You can alter the report by using the context menu.

![Context menu for pivot button in ASP NET pivot client control](OLAP-Client-Elements_images/ClientBtn_Menu.png)

## Elements editor

### Measure editor

The measure editor is a dialog that displays the collection of measures in the current report.

![Measure editor in ASP NET pivot client control](OLAP-Client-Elements_images/measureeditor.png)

To remove a measure, click the remove icon next to the corresponding measure. To avoid removing the current selection, click cancel.

![Removing measure from ASP NET pivot client control](OLAP-Client-Elements_images/deletemeasureeditor.png)

### Member editor

The member editor is a dialog that displays the members of the current hierarchy in a tree view structure.

![Member editor in ASP NET pivot client control](OLAP-Client-Elements_images/membereditor.png)

The check all and uncheck all option in the dialog allows you to select and unselect entire nodes for filtering. For more details about filtering, [click here](https://help.syncfusion.com/aspnet/pivotclient/olap-data-exploration#filtering-by-member).

## Toolbar

![Toolbar in ASP NET pivot client control](OLAP-Client-Elements_images/toolbar.png)

The options available in the toolbar are:

* **New report**: Creates a new report list, and clears the existing report collection to provide a new platform for new deployment based on the existing cube elements.
* **Add report**: Adds a new report to the existing list of reports.
* **Remove report**: Removes the current report from the report list.  If the report list contains only one report, you cannot remove it.
* **Rename report**: The rename option allows you to change the name of the current report.
* **Report manipulation in DB**: Contains options to manipulate the reports in the database.
* **MDX query**: This option displays the executed MDX query to retrieve the data at that instant.
* **Defer update**: This option allows you to update the widget on-demand rather than updating it for every interaction.
* **Export to Excel**: Export the grid and chart to an Excel worksheet.
* **Export to Word**: Exports the grid and chart to a Word document.
* **Export to PDF**: Exports the grid and chart to a PDF document.
* **Full screen view**: Displays the active control (chart/grid) in full/maximized view.
* **Filter/sort column**: Filters/sorts the data in the OLAP report with respect to the column.
* **Filter/sort row**: Filters/sorts the data in the OLAP report with respect to the row.
* **Toggle axis**: Interchanges the items between categorical and series axes.
* **Chart types**: Allows you to change the chart type dynamically.
* **Report list**: Holds all reports of the current session of the pivot client control and displays in a drop-down list. You can select a report from the drop-down list.

Following are the options available for database report manipulation:

![Report manipulation icons in ASP NET pivot client control](OLAP-Client-Elements_images/Toolbar1.png)

* **Save**: Saves the report collection by only one name in a database.
* **Save As**: Saves the report collection by more than one name in the database.
* **Load**: Picks the saved report collection from the database and loads this by clearing the existing collection of reports.
* **Remove**: Removes the selected report from the saved report list in the database.
* **Rename**: Allows you to change the name of the selected report from the saved report list in the database.

## Report manipulation

### New report

This option allows you to create a new report collection with a single report by clearing the existing report collection. By clicking the new report icon in toolbar, the new report dialog opens as follows:

![New report in ASP NET pivot client control](OLAP-Client-Elements_images/newreport.png)

After giving the required name and click OK, the report collection gets loaded with only one empty report with entered name. By clicking cancel, the new report creation gets canceled.

![New report in ASP NET pivot client control](OLAP-Client-Elements_images/newreport1.png)

### Add report

This option allows you to add a report to the existing report collection. By clicking the add report icon in the toolbar, the add report dialog opens to provide a name for the report to be added as shown below:

![Add report dialog in ASP NET pivot client control](OLAP-Client-Elements_images/addreport.png)

After giving an appropriate name in the respective column and click OK, a report with the entered name is added to the collection. By clicking cancel, the report creation gets canceled.

![Adding a report in ASP NET pivot client control](OLAP-Client-Elements_images/newreport1.png)

### Remove report

This option allows you to remove the current/active report from the report collection. By clicking the remove icon on the toolbar, a dialog will open for user’s confirmation on removal of report as shown below:

![Remove report dialog in ASP NET pivot client control](OLAP-Client-Elements_images/removereport.png)

Click OK to remove the report from the collection or click cancel to withdraw the removing operation.

This option works only if the report collection has more than one report. If not, the following dialog will open:

![Alert dialog for single report in ASP NET pivot client control](OLAP-Client-Elements_images/aferremovereport.png)

### Rename report

This option allows you to rename the current/active report. By clicking the rename icon on the toolbar, the following dialog will open:

![Rename report dialog in ASP NET pivot client control](OLAP-Client-Elements_images/renamereport.png)

After an appropriate name has been provided, click OK. The active report is refreshed with the new name.

![Renaming of the previous report in ASP NET pivot client control](OLAP-Client-Elements_images/afterrenamereport.png)

### Save
This option saves the entire report collection by only one name to a database. The database is connected to the application through a connection string provided in the service.

By clicking the save icon, the following save dialog will open:

![Save report dialog in ASP NET pivot client control](OLAP-Client-Elements_images/savereport.png)

After an appropriate name has been provided, click OK. The report collection will be saved to the connected database. Otherwise, click cancel to withdraw the saving operation.

### Save As
This option saves the entire report collection by two or more names to a database. The database is connected to the application through a connection string provided in the service.

By clicking the save as icon, the following save as dialog will open:

![Save As dialog in ASP NET pivot client control](OLAP-Client-Elements_images/saveasreport.png)

After an appropriate name has been provided, click OK. The report collection will be saved to the connected database. Otherwise click cancel to withdraw the saving operation.

### Load
The load option loads a saved report collection from the database through the service. By clicking the load icon on the toolbar, the following load dialog will open:

![Load dialog in ASP NET pivot client control](OLAP-Client-Elements_images/loadreport.png)

Select a report from the report collection through the drop-down list and click OK for loading the selected report collection. Otherwise, click cancel to abort the report loading operation.

![ASP NET pivot client control loaded with saved report](OLAP-Client-Elements_images/loadreport1.png)

### Remove
This option removes the saved report from the report collection. By clicking the remove icon on the toolbar, a remove dialog will open for user’s confirmation for removal of the report as shown below:

![Removing saved report from database of ASP NET pivot client control](OLAP-Client-Elements_images/removerecord1.png)

Click OK to remove the report from the collection. Otherwise, click cancel to abort the remove operation.

### Rename
Rename option allows you to rename the saved report. By clicking the rename icon on the toolbar, the following dialog will open:

![Renaming saved report of ASP NET pivot client control](OLAP-Client-Elements_images/renameRecord.png)

After an appropriate name has been provided, click OK. The active report is refreshed with the new name.

### Report List

Report list drop-down contains the names of all reports in the report collection.

![Report collection in ASP NET pivot client control](OLAP-Client-Elements_images/reportlist.png)

Select the required report from the report list. The selected report will be set as active report, and loaded.

![ASP NET pivot client control with selected report](OLAP-Client-Elements_images/afterreportlist.png)

## Pivot grid and pivot chart

The [pivot grid](https://help.syncfusion.com/aspnet/pivotgrid/overview) and [pivot chart](https://help.syncfusion.com/aspnet/pivotchart/overview) controls will be rendered with respect to the operations done at axis element builder.



