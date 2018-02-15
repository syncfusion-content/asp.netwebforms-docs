---
layout: post
title: Perform Grid Actions on External button click | Grid | ASP.NET Webforms | Syncfusion
description: perform grid actions on external button click
platform: aspnet
control: Grid
documentation: ug
---

## Perform Grid Actions on External button click

### CRUD operations

Using [`addRecord`](https://help.syncfusion.com/api/js/ejgrid#methods:addRecord “addRecord”) method of Grid, you can add a record to a Grid externally without using in-built toolbar add support. While using [`addRecord`](https://help.syncfusion.com/api/js/ejgrid#methods:addRecord “addRecord”) method it is necessary to set `AllowAdding` property as `true`.
Using [`deleteRecord`](https://help.syncfusion.com/api/js/ejgrid#methods:deleteRecord “deleteRecord”) method of Grid, you can delete a record to a Grid externally without using in-built toolbar delete support. While using [`deleteRecord`](https://help.syncfusion.com/api/js/ejgrid#methods:deleteRecord “deleteRecord”) method it is necessary to set `AllowDeleting` property as `true`.
Using [`updateRecord`](https://help.syncfusion.com/api/js/ejgrid#methods:updateRecord “updateRecord”) method of Grid, you can update a record to a Grid externally without using in-built toolbar update support. While using [`updateRecord`](https://help.syncfusion.com/api/js/ejgrid#methods:updateRecord “updateRecord”) method it is necessary to set `AllowEditing` property as `true`.

### Filtering

Using [`filterColumn`](https://help.syncfusion.com/api/js/ejgrid#methods:filterColumn “filterColumn”) method of Grid, you can filter the data in the Grid externally without using in-built filter support. While using [`filterColumn`](https://help.syncfusion.com/api/js/ejgrid#methods:filterColumn “filterColumn”) method it is necessary to set `AllowFiltering` property as `true`.

### Grouping

Using [`groupColumn`](https://help.syncfusion.com/api/js/ejgrid#methods:groupColumn “groupColumn”) and [`ungroupColumn`](https://help.syncfusion.com/api/js/ejgrid#methods:ungroupColumn “ungroupColumn”) method of Grid, you can group/ungroup the Grid externally without using in-built grouping support. While using [`groupColumn`](https://help.syncfusion.com/api/js/ejgrid#methods:groupcolumn “groupColumn”) and [`ungroupColumn`](https://help.syncfusion.com/api/js/ejgrid#methods:ungroupcolumn “ungroupColumn”) method it is necessary to set `AllowGrouping` property as `true`.

### Sorting

Using [`sortColumn`](https://help.syncfusion.com/api/js/ejgrid#methods:sortcolumn “sortColumn”) method of Grid, you can sort the Grid externally without using in-built sorting support. While using [`sortColumn`](https://help.syncfusion.com/api/js/ejgrid#methods:sortcolumn “sortColumn”) method it is necessary to set `AllowSorting` property as `true`.

The following code example explains the above behavior.

{% tabs %}
{% highlight html %}
<table>
    <tr>
        <td><b>CRUD</b><br><ej:Button Type="Button" ClientSideOnClick="addRecord" runat="server" Text="AddRecord"></ej:Button><br><ej:Button Type="Button" ClientSideOnClick="deleteRecord" runat="server" Text="DeleteRecord"></ej:Button><br><ej:Button Type="Button" ClientSideOnClick="deleteRecord" runat="server" Text="DeleteRecord"></ej:Button></td>
        <td><b>Filtering</b><br><br><ej:DropDownList ID="OrderList" runat="server" DataTextField="OrderID"  WatermarkText="Select Filter value" Width="230" ClientSideOnSelect="Filterfn" >
             <Items>
                    <ej:DropDownListItem Text="10001" Value="10001"></ej:DropDownListItem>
                    <ej:DropDownListItem Text="10002" Value="10002"></ej:DropDownListItem>
                    <ej:DropDownListItem Text="10003" Value="10003"></ej:DropDownListItem>
                    <ej:DropDownListItem Text="10004" Value="10004"></ej:DropDownListItem>
                    <ej:DropDownListItem Text="10005" Value="10005"></ej:DropDownListItem>
                </Items>
            </ej:DropDownList><br><ej:Button Type="Button" ClientSideOnClick="clearfilterfn" runat="server" Text="Clear Filter"></td>
        <td><b>Grouping</b><br><br><ej:DropDownList ID="OrderList" runat="server" DataTextField="OrderID"  SelectedItemIndex=0 Width="230" ClientSideOnChange="Groupfn" >
             <Items>
                    <ej:DropDownListItem Text="OrderID" Value="OrderID"></ej:DropDownListItem>
                    <ej:DropDownListItem Text="CustomerID" Value="CustomerID"></ej:DropDownListItem>
                    <ej:DropDownListItem Text="Freight" Value="Freight"></ej:DropDownListItem>
                    <ej:DropDownListItem Text="ShipName" Value="ShipName"></ej:DropDownListItem>
                    <ej:DropDownListItem Text="Verified" Value="Verified"></ej:DropDownListItem>
                </Items>
            </ej:DropDownList><br>
            <ej:Button Type="Button" ClientSideOnClick="clicktoGroup" runat="server" Text="GroupColumn"></ej:Button>
            <ej:Button Type="Button" ClientSideOnClick="clicktoGroup" runat="server" Text="UnGroupColumn"></ej:Button>
        </td>
        <td><b>Sorting</b><br><br>
            <select id="sortcolumnName" class="e-ddl" style="width: 100px" data-bind="value: field">
                <option value="OrderID" selected="selected">Order ID</option>
                <option value="CustomerID">Customer ID</option>
                <option value="EmployeeID">Employee ID</option>
                <option value="Freight">Freight</option>
                <option value="OrderDate">Order Date</option>
            </select>
            <select id="directions" class="e-ddl" style="width: 100px" data-bind="value: field">
                <option value="ascending" selected="selected">Ascending</option>
                <option value="descending">Descending</option>
            </select>
            <button id="doSorting" style="width: 100px">Sort</button>
            <button id="clearSort" style="width: 100px">Clear</button>
        </td>
    </tr>
</table>
<div id="Grid"></div>

{% endhighlight %}

{% highlight js %}
<script>
    $("#Grid").ejGrid({
        dataSource : window.gridData,
        allowPaging : true,
        isResponsive:true,
        allowSearching:true,
        allowFiltering:true,
        allowGrouping:true, 
        allowReordering:true,
        allowSorting:true,
        editSettings : {
            allowEditing : true,
            allowAdding : true,
            allowDeleting : true,
            editMode : "normal"
        },
        toolbarSettings : {
            showToolbar : true,
            toolbarItems : ["add", "edit", "delete", "update", "cancel"]
        },
        columns : [{ field: "OrderID", headerText: "Order ID",isPrimaryKey:true, width: 70 },
                   { field: "CustomerID", headerText: "Customer ID", width: 70 },
                   { field: "EmployeeID", headerText: "Employee ID", width: 70},
                   { field: "Freight", headerText: "Freight", width: 70},
                   { field: "OrderDate", headerText: "Order Date", width: 70}]
    });
    $('#selectFilter').ejDropDownList({ targetID: "Order", watermarkText:"Select Filter value", width: "230", select:"Filterfn"});
    $("#columnName").ejDropDownList({ width: "115", selectedItemIndex: 0, change: "Groupfn" });
    $("#groupColumn").ejButton({ size: "medium", click: "clicktoGroup", width: "100px" });
    $("#unGroupColumn").ejButton({ size: "medium", click: "clicktoGroup", width: "115px" });
    $("#Addrecord").ejButton({ size: "medium", click: "addRecord", width: "100px" });
    $("#DeleteRecord").ejButton({ size: "medium", click: "deleteRecord", width: "100px" });
    $("#Updaterecord").ejButton({ size: "medium", click: "updateRecord", width: "100px" });
    $("#ClearFilter").ejButton({ size: "medium", click: "clearfilterfn", width: "100px" });
    $("#unGroupColumn").ejButton("disable");
    $("#sortcolumnName").ejDropDownList({ width: "120" });
    $("#directions").ejDropDownList({ width: "120" });
    $("#sortcolumnName").ejDropDownList("option",{"selectedItemIndex":1});
    $("#directions").ejDropDownList("option", { "selectedItemIndex": 0 });
    $("#doSorting,#clearSort").ejButton({ "click": "Sortfn", width: "100" });
    function addRecord(){
        var gridObj = $('#Grid').data("ejGrid");
        gridObj.addRecord({ "OrderID": 12333 });
    }
    function deleteRecord(){
        var gridObj = $('#Grid').data("ejGrid");
        gridObj.deleteRecord("OrderID", { OrderID: gridObj.model.dataSource[gridObj.model.selectedRowIndex].OrderID }); 
    }
    function updateRecord(){
        var gridObj = $('#Grid').data("ejGrid");
        gridObj.updateRecord("OrderID", { OrderID: 10249, EmployeeID: 3 }); 
    }
    var group = true;
    function Filterfn(args) {
        var gridObj = $("#Grid").data("ejGrid");
        gridObj.filterColumn("OrderID", "equal", args.value, "and", true);
    }
    function clearfilterfn(args) {
        var gridObj = $("#Grid").data("ejGrid");
        gridObj.clearFiltering();
    }
    function Sortfn(args) {
        var gridObj = $("#Grid").data("ejGrid");
        var columnName = $("#sortcolumnName").data("ejDropDownList")._selectedValue;
        var sortDirection = $("#directions").data("ejDropDownList")._selectedValue;
        if (this.element.attr("id") == "doSorting") {
            gridObj.sortColumn(columnName, sortDirection);
        }
        else {
            gridObj.clearSorting();
        }
    }
    function Groupfn() {
        var gridObj = $("#Grid").data("ejGrid");
        var columnName = $("#columnName").ejDropDownList("getSelectedValue");
        if ($.inArray(columnName, gridObj.model.groupSettings.groupedColumns) != -1) {
            $("#unGroupColumn").ejButton("enable");
            $("#groupColumn").ejButton("disable");
        }
        else {
            $("#groupColumn").ejButton("enable");
            $("#unGroupColumn").ejButton("disable");
        }
    }
    function clicktoGroup(args) {
        var gridObj = $("#Grid").data("ejGrid");
        var columnName = $("#columnName").ejDropDownList("getSelectedValue");
        if (this.element.attr("id") == "groupColumn") {
            gridObj.groupColumn(columnName);
            if (group) {
                $("#groupColumn").ejButton("disable");
                $("#unGroupColumn").ejButton("enable");
            }
        }
        else {
            gridObj.ungroupColumn(columnName);
            group = true;
            $("#unGroupColumn").ejButton("disable");
            $("#groupColumn").ejButton("enable");
        }
    }
</script>


{% endhighlight %}

{% endtabs %}
The following output is displayed as a result of the above code example.
![](externalsearch_images/Actionswithexternalbutton_img1.png)