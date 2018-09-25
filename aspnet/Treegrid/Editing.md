---
layout: post
title: Editing | TreeGrid | ASP.NET | Syncfusion
description: editing
platform: aspnet
control: TreeGrid
documentation: ug
---

# Editing

TreeGrid provides support to add, edit and delete the records dynamically using `EditSettings` property.

## Add new record

TreeGrid provides support for adding a new record by setting `AllowAdding` property as `true`. You can add new record by toolbar add item click or context menu.

The below code example shows how to enable add option in TreeGrid.

{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer">
    <EditSettings AllowAdding="true" />
</ej:TreeGrid>

{% endhighlight %}

![](Editing_images/addnewRowBefore.png)
The above screenshot shows before add a new record in TreeGrid.
{:.caption}

![](Editing_images/addnewRowAfter.png)
The above screenshot shows after add a new record in TreeGrid.
{:.caption}

## Add row position

Using the `EditSettings.RowPosition` parameter, user can able to insert the record at any desired index at run-time. The user can insert a record dynamically in the following positions

* Top: Top to all the existing records
* Bottom: Bottom to all the existing records
* AboveSelectedRow: Above to the selected row
* BelowSelectedRow: Below to the selected row
* Child: As a child to the selected row 

The below code example shows how to set row position for new record add in TreeGrid.

{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer">
    <EditSettings AllowAdding="true" RowPosition="Child"/>
</ej:TreeGrid>

{% endhighlight %}

![](Editing_images/addnewRowChild.png)
The above screenshot shows new record added in row position of `Child`.
{:.caption}

### Adding records using method

Using [`addRow`](/api/js/ejtreegrid#methods:addrow "addRow") method records can be added dynamically to the TreeGrid. Before calling this method, you should enable the `AllowAdding` property.

The below code snippet explains dynamically inserting a record in TreeGrid. The record will be inserted as a child node to the current selected record.

{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer">
    <EditSettings AllowAdding="true" />
</ej:TreeGrid>

<asp:ScriptManager ID="ScriptManager" runat="server"/>

<script type="text/javascript">
$("#add").click(function () {
    var treeGridObj = $("#TreeGridContainer").data("ejTreeGrid");
    var data = {
            taskId: "40",
            taskName: "New Task 40",
            startDate: "2/20/2014",
            startDate: "2/25/2014"
        };
   treeGridObj.addRow(data, ej.TreeGrid.RowPosition.Child); // To add a task
    })

</script>

{% endhighlight %}

## Edit Modes

TreeGrid supports the below editModes, 

* Cell Editing
* Row Editing
* Dialog Editing
* Batch Editing

You can enable editing in TreeGrid by enabling the property `AllowEditing`.

### Cell Editing

Update the record through editing a cell by setting `EditMode` as the `CellEditing`.

The following code example shows you how to enable the `CellEditing` in TreeGrid control.


{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer">
  <EditSettings AllowEditing="true" EditMode="CellEditing"/>
</ej:TreeGrid>

{% endhighlight %}

The output of TreeGrid with `CellEditing` is as follows.

![](Editing_images/cellEditing.png)

### Prevent cell editing

In cell edit action `BeginEdit` and `EndEdit` events are triggered before and after the editing action. Cell editing for specific cell can be prevented by using `BeginEdit` event.

The following code example show, how to prevent cell editing in TreeGrid.

{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer" BeginEdit="beginEdit" EndEdit="endEdit">
  <EditSettings AllowEditing="true" EditMode="CellEditing"/>
</ej:TreeGrid>

<asp:ScriptManager ID="ScriptManager" runat="server"/>

<script type="text/javascript">
function beginEdit(args) {
      if (args.columnIndex == 1)
            args.cancel = true;
}
        
function endEdit(args) {
      //To perform actions after editing
}
</script>

{% endhighlight %}

### Row Editing

It is possible to make the entire row to editable state and to update a record by setting `EditMode` as `RowEditing`.

The following code example shows you how to enable `RowEditing` in TreeGrid control.

{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer">    
    <EditSettings AllowEditing="true" EditMode="RowEditing"/>
</ej:TreeGrid>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/rowEditing.png)


### Dialog Editing

Set the `EditMode` as `DialogEditing` to edit/add a record using dialog.

The following code example shows you how to enable the `DialogEditing` in TreeGrid control.

{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer">    
    <EditSettings AllowEditing="true" EditMode="DialogEditing" />
</ej:TreeGrid>

{% endhighlight %}

The output of the TreeGrid with dialog editing is as follows.

![](Editing_images/dialogEditing.png)

The add and edit dialogs can be opened on custom actions instead of toolbar icons using the methods [`showAddDialog`](https://help.syncfusion.com/api/js/ejtreegrid#methods:showadddialog "showAddDialog") and [`showEditDialog`](https://help.syncfusion.com/api/js/ejtreegrid#methods:showeditdialog "showEditDialog").

### Prevent dialog editing

In dialog editing action `ActionBegin` and `ActionComplete` client side events are triggered before and after the edit action. Dialog editing for specific row can be prevented by using `ActionBegin` event.

The following code example show, how to prevent dialog editing in TreeGrid.

{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer" ActionBegin="actionBegin" ActionComplete="actionComplete">    
    <EditSettings AllowEditing="true" EditMode="DialogEditing" />
</ej:TreeGrid>

<asp:ScriptManager ID="ScriptManager" runat="server"/>

<script type="text/javascript">
function actionBegin(args) {
      if(args.requestType == "beforeOpenEditDialog")
            {
                  if(args.data.taskID == 4)
                        args.cancel = true;
            }
}
        
function actionComplete(args) {
      //To perform actions on action complete
}
</script>

{% endhighlight %}

N> While saving the edited record `ActionComplete` event will be triggered with updated record value in `data` argument and `requestType` as `recordUpdate`. Using this event we can update the database.

### Batch Editing

The batch editing support in the tree grid is used to save all added, edited, and deleted changes to the database with a single action. This can be enabled by setting the `EditMode` property to `BatchEditing`. The following code example shows how to enable the batchEditing in the tree grid control.

{% highlight html %}

   <ej:TreeGrid runat="server" ID="Treegrid">
         <EditSettings EditMode="BatchEditing">
         </EditSettings>
   </ej:TreeGrid>

{% endhighlight %}

The output of a tree grid with `BatchEditing` is as follows.

![](Editing_images/BatchEdit_img1.png)


In batch editing, the edit mode can be changed to **Cell** or **Row** or **Dialog** with the `BatchEditSettings.EditMode` property. The following code snippet shows how to set the editMode to row in the `BatchEditSettings` property.

{% highlight js %}

   <ej:TreeGrid runat="server" ID="Treegrid">
       <EditSettings EditMode="BatchEditing">
            <BatchEditSettings EditMode="Row" />
       </EditSettings>
   </ej:TreeGrid>


{% endhighlight %}

The output of a tree grid with `BatchEditSettings` and `EditMode` set as `Row` is as follows.

![](Editing_images/BatchEdit_img2.png)


N> After modifying all changes in the tree grid, click the save button in the toolbar. The `ActionComplete` event will be triggered with updated records in the `batchChanges` argument with `requestType` argument as `batchSave`. Using this event, you can update all the modified records to the database.

## Edit type and its params

The edit type of columns can be customized using `EditType` property of `Columns`. The following controls are supported built-in by `EditType`. You can set the `EditType` based on specific data type of the column.

* **CheckBox** control for boolean data type.
* **NumericTextBox** control for integers, double, and decimal data types.
* **InputTextBox** control for string data type.
* **DatePicker** control for date data type.
* **DateTimePicker** control for date-time data type.
* **DropDownList** control for list of data type.

And also you can define the model for all the EditTypes controls while editing through `EditOptions` property of `Columns`.

The following code example describes the above behavior.

{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer" >
<Columns>
    <ej:TreeGridColumn Field="taskID" HeaderText= "Task Id" EditType="Numeric"></ej:TreeGridColumn>
    <ej:TreeGridColumn Field="taskName" HeaderText= "Task Name" EditType="String"></ej:TreeGridColumn>
    <ej:TreeGridColumn Field="startDate" HeaderText= "Start Date" EditType="Datepicker"></ej:TreeGridColumn>
    <ej:TreeGridColumn Field="EndDate" HeaderText= "End Date" EditType="Datepicker"></ej:TreeGridColumn>
    <ej:TreeGridColumn Field="Duration" HeaderText= "Duration" EditType="Numeric">
    <NumericEditOptions  DecimalPlaces="2" />
    </ej:TreeGridColumn>
    </Columns>
</ej:TreeGrid>

{% endhighlight %}

![](Editing_images/editType.png)

The above screenshot shows TreeGrid with different Edit type.
{:.caption}

### Assign data source for drop down edit type

In TreeGrid, we need to assign the data source for drop down list control to populate the suggestion list while editing the column in TreeGrid. The `DropdownData` property is used to set the drop down list data source in TreeGrid control.

The following code example shows how to set data source for drop down edit type.
{% tabs %}
{% highlight C# %}

public partial class TreeGridColumn : System.Web.UI.Page {
    protected void Page_Load(object sender, EventArgs e) 
    {
        StageDetails stages=new StageDetails();
        var data = stages.GetStageCollection();
        var index1 = this.TreeGridColumn.Columns.FindIndex(col => col.Field == "Priority");
        this.TreeGridColumn.Columns.ElementAt(index1).DropDownData = data;            
    }
    public class Stage
    {
        public int id { get; set; }
        public string text { get; set; }
        public string value { get; set; }
    }
      public class StageDetails
      {
        public List<Stage> GetStageCollection()
        {
            List<Stage> stageCollection = new List<Stage>();
                  stageCollection.Add(new Stage() { id = 1, text = "Low", value = "Low" });
                  stageCollection.Add(new Stage() { id = 2, text = "Normal", value = "Normal" });
                  stageCollection.Add(new Stage() { id = 3, text = "High", value = "High" });
                  stageCollection.Add(new Stage() { id = 4, text = "Critical", value = "Critical" });
                  return stageCollection;
        }
      }
    }    

{% endhighlight %}

{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer" >
<Columns>
    <ej:TreeGridColumn Field="Priority" HeaderText= "Priority" EditType="Dropdown"></ej:TreeGridColumn>
</Columns>
</ej:TreeGrid>

{% endhighlight %}
{% endtabs %}

![](Editing_images/dropdownEdit.png)

The above screenshot shows drop down edit type in TreeGrid.
{:.caption}

#### Dialog Template

You can edit any of the fields pertaining to a single record of data and apply it to a template so that the same format is applied to all the other records that you may edit later.
Using this template support, you can edit/add the fields that are not bound to TreeGrid columns.
To edit/add the records using dialog template form, set `EditMode` as `DialogEditing` and specify the template id to `DialogEditorTemplateID` property of `EditSettings`.

N> The `value` attribute is used to bind the corresponding field value while editing.
   The `name` attribute is used to get the changed field values while saving the edited record.
   The `id` attribute must to be set in the format of ( treegrid control id + fieldname).

The following code example describes the above behavior.

{% highlight js %}

<script type="text/x-jsrender" id="template">
    <div>
        <b>Task Details</b>
        <table cellspacing="10" class="beta">
            <tr>
                <td style="text-align:right;padding: 10px;">
                    TaskID
                </td>
                <td style="text-align: left;padding: 10px;">
                    <input id="TreeGridContainertaskID" type="number" name="taskID" value="{{'{{'}}:taskID{{}}}}" disabled="disabled" class="e-field e-ejinputtext valid e-disable"/>
                </td>
                <td style="text-align: right;padding: 10px;">
                    TaskName
                </td>
                <td style="text-align: left;padding: 10px;">
                    <input id="TreeGridContainertaskName" name="taskName" value="{{'{{'}}:taskName{{}}}}" class="e-field e-ejinputtext valid"/>
                </td>
            </tr>
            <tr>
                <td style="text-align: right;padding: 10px;">
                    StartDate
                </td>
                <td style="text-align: left;padding: 10px;">
                    <input type="text" id="TreeGridContainerstartDate" name="startDate" value="{{'{{'}}:startDate{{}}}}" class="e-field e-ejinputtext valid" />
                </td>
                <td style="text-align: right;padding: 10px;">
                    EndDate
                </td>
                <td style="text-align: left;padding: 10px;">
                    <input id="TreeGridContainerendDate" type="text" name="endDate" value="{{'{{'}}:endDate{{}}}}" class="e-field e-ejinputtext valid"  />
                </td>
            </tr>
        </table>
    </div>
</script>

{% endhighlight %}


{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer">    
    <EditSettings AllowEditing="true" EditMode="DialogEditing" DialogEditorTemplateID="#template"/>
</ej:TreeGrid>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/dialogTemplate.png)

[Click](https://asp.syncfusion.com/demos/web/treegrid/dialogediting.aspx) here to view the online demo sample for Dialog Template.

### Using methods to open dialog

It is possible to open the add dialog dynamically using [`showAddDialog`](https://help.syncfusion.com/api/js/ejtreegrid#methods:showadddialog "showAddDialog") method.

Similarly, open the edit dialog dynamically using the method [`showEditDialog(index)`](https://help.syncfusion.com/api/js/ejtreegrid#methods:showeditdialog "showEditDialog"), with the index of the row to be edited as parameter.

{% highlight html %}
<ej:TreeGrid ID="TreeGridContainer">
</ej:TreeGrid>
<asp:ScriptManager ID="ScriptManager" runat="server" />
<script type="text/javascript">
$("#add").click(function () {
    treegridObj = $("#TreeGridContainer").data("ejTreeGrid");
    treegridObj.showAddDialog();
    })
$("#edit").click(function () {
    treegridObj = $("#TreeGridContainer").data("ejTreeGrid");
    treegridObj.showEditDialog(3);
    })
</script>
{% endhighlight %}

## BeginEditAction - edit cell/row by single/double click

In TreeGrid we can perform edit action by single or double click using `BeginEditAction` , default value of this property is `DblClick`.

The following code example shows how to enable single click edit in TreeGrid.

{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer">    
    <EditSettings BeginEditAction="Click"/>
</ej:TreeGrid>

{% endhighlight %}

## Cell Edit Template

Edit template is used to create custom editor for editing the column values. It can be created by using `EditTemplate` property of `Columns`.

Following functions required to render edit template in TreeGrid,

* `Create` - It is used to create the control on initialization.
* `Read` - It is used to read the input value on save.
* `Write` - It is used to assign the value to control on editing.

The following code example describes edit template behavior

{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer">
      <Columns>
           <ej:TreeGridColumn HeaderText="Task Name" Field="TaskName">
                <EditTemplate Create="create" Read="read" Write="write" />
           </ej:TreeGridColumn>
      </Columns>
</ej:TreeGrid>

{% endhighlight %}

{% highlight js %}

<script>
var autocompleteData = ["Planning", "Plan Timeline", "Plan Budget", "Allocate Resources", "Planning Complete"];

function create()
{
      return "<input>";
}

function write(args)
{
      args.element.ejAutocomplete({ 
           width: "100%", 
           dataSource: autocompleteData,
           enableDistinct: true,
           value: args.rowdata !== undefined ? args.rowdata["taskName"] : "" 
      });
}

function read(args)
{
      args.ejAutocomplete('suggestionList').css('display', 'none');
      return args.ejAutocomplete("getValue");
}
</script>

{% endhighlight %}

The output of the TreeGrid width EditTemplate as follows

![](Editing_images/editTemplate.png)

The updated record values are maintained in collection in TreeGrid, and the user can retrieve the updated record collection at any time by using the [`getUpdatedRecords`](https://help.syncfusion.com/api/js/ejtreegrid#methods:getupdatedrecords "getUpdatedRecords") method.

[Click](https://asp.syncfusion.com/demos/web/treegrid/treegridedittemplate.aspx) here to view the online demo sample for Edit Template.

## Delete record

TreeGrid provides support to delete a record by enabling `AllowDeleting` property.

The below code example shows how to enable delete option in TreeGrid.

{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer">    
    <EditSettings AllowDeleting="true"/>
</ej:TreeGrid>

{% endhighlight %}

![](Editing_images/beforeDelete.png)

The above screenshot shows before delete a record in TreeGrid.
{:.caption}

![](Editing_images/afterDelete.png)

The above screenshot shows after delete a record in TreeGrid.
{:.caption}

## Delete confirmation message

Delete confirmation message is used to get the confirmation from the user before deleting action. This confirmation message can be enabled by setting `ShowDeleteConfirmDialog` property as `true`.

The following code snippet explains how to enable delete confirmation message in TreeGrid.

{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer">    
    <EditSettings AllowDeleting="true" ShowDeleteConfirmDialog="true"/>
</ej:TreeGrid>

{% endhighlight %}

![](Editing_images/deleteConfirmation.png)

[Click](https://asp.syncfusion.com/demos/web/treegrid/treegridediting.aspx) here to view the online demo sample for Editing.