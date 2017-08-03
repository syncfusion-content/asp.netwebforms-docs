---
layout: post
title: Editing | TreeGrid | ASP.NET | Syncfusion
description: editing
platform: aspnet
control: TreeGrid
documentation: ug
---

# Editing

## Editing Modes

TreeGrid provides support to add, edit and delete the records and the folllowing are the types of editing modes available, 

* Cell Editing
* Row Editing
* Dialog Editing

You can enable editing in TreeGrid by enabling the property `EditSettings.AllowEditing`.

### Cell Editing

Update the record details through cell editing by setting `EditSettings.EditMode` as `CellEditing`.

The following code example shows you how to enable cell editing in TreeGrid control.


{% highlight html %}

<ej:TreeGrid runat="server" ID="TreeGridControlEditing">

    //...

    <EditSettings AllowEditing="true" EditMode="cellEditing"/>

</ej:TreeGrid>

{% endhighlight %}

The output of TreeGrid with cell editing is as follows.

![](Editing_images/Editing_img1.png) 

### Row Editing

It is possible to make the entire row to editable state and to update a record by setting `EditSettings.EditMode` as `rowEditing`.

The following code example shows you how to enable rowEditing in TreeGrid control.

{% highlight html %}

<ej:TreeGrid runat="server" ID="TreeGridControlEditing">

    //...

    <EditSettings AllowEditing="true" EditMode="rowEditing"/>

</ej:TreeGrid>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/rowEditing.png)


### Dialog Editing

Set `EditSettings.EditMode` as `dialogEditing` to edit/add a record using dialog.

The following code example shows you how to enable dialog editing in TreeGrid control.

{% highlight html %}

<ej:TreeGrid runat="server" ID="TreeGridControlEditing">
    //...
    <EditSettings AllowEditing="true" EditMode="dialogEditing" />
</ej:TreeGrid>

{% endhighlight %}

The output of the TreeGrid with dialog editing is as follows.

![](Editing_images/dialogEditing.png)


#### Dialog Template

You can edit any of the fields pertaining to a single record of data and apply it to a template so that the same format is applied to all the other records that you may edit later.
Using this template support, you can edit/add the fields that are not bound to TreeGrid columns.
To edit/add the records using dialog template form, set `EditSettings.EditMode` as `dialogEditing` and specify the template id to `EditSettings.DialogEditorTemplateID` property.

N> 1. `value` attribute is used to bind the corresponding field value while editing.
N> 2. `name` attribute is used to get the changed field values while saving the edited record.
N> 3.  `id` attribute must to be set in the format of ( treegrid control id + fieldname).

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

<ej:TreeGrid runat="server" ID="TreeGridControlEditing">
    //...
    <EditSettings AllowEditing="true" EditMode="dialogEditing" DialogEditorTemplateID="template"/>
</ej:TreeGrid>

{% endhighlight %}

The following output is displayed as a result of the above code example.

![](Editing_images/dialogTemplate.png)


## Cell Edit Template

Edit template is used to create custom editor for editing the column values. It can be created by using `EditTemplate` property of `Columns`.

The following are the functions available for edit template,

* `create` - It is used to create the control at time of initialize.
* `read` - It is used to read the input value at time of save.
* `write` - It is used to assign the value to control at time of editing.

The following code example describes edit template behavior

{% highlight html %}

<ej:TreeGrid runat="server ID="TreeGridControlEditing">
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