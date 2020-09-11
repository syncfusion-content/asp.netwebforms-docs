---
layout: post
title: Server-side-event-arguments with Grid widget for Syncfusion Essential ASP.NET
description: server side event arguments in asp grid
platform: aspnet
control: Grid
documentation: ug
---

# Server side event arguments in ASP Grid

This section explains in detail about the various server-side events available in the **ASP Grid control** and the arguments that are obtained server-side. 

The **sender** parameter of all the server-side events returns the grid model details. The **Syncfusion.JavaScript.Web.GridEventArgs** arguments provide information specific to this event.

The various server-side events and the arguments corresponding to the events are as follows:

## OnServerAddRow

The **OnServerAddRow** event is triggered upon saving the added record to the grid. The details of the added record can be obtained server-side, as explained in the following table.

_Table 5: Syncfusion.JavaScript.Web.GridEventArgs arguments of OnServerAddRow event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
data</td><td>
It consists of the JSON data newly added to the grid.</td></tr>
<tr>
<td>
action</td><td>
It indicates the action performed in the grid.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerAddRow="OrdersGrid_ServerAddRow">

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

 {% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerAddRow(object sender, GridEventArgs e)

        {

          //code corresponding to any custom operation

        }

    }
    
    {% endhighlight %}
    
{% endtabs %}
	
### OnServerBatchEditRow

The **OnServerBatchEditRow** event is triggered upon saving the batch changes to the grid when the EditMode is set to “Batch”. The batch changes details can be obtained at server-side, as explained in the following table.

_Table 8: Syncfusion.JavaScript.Web.GridEventArgs arguments of OnServerBatchEditRow event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
batchChanges</td><td>
It contains the details of the added, modified and deleted records.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerBatchEditRow="OrdersGrid_ServerbatchEditRow"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {        

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerBatchEditRow(object sender, GridEventArgs e)

        {

          //code corresponding to any custom operation

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerDeleteRow

The **OnServerDeleteRow** event is triggered upon deleting a record from the grid. The details of the deleted record can be obtained from the server-side, as explained in the following table.

_Table 7: Syncfusion.JavaScript.Web.GridEventArgs arguments of OnServerDeleteRow event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
data</td><td>
It returns the deleted record details.</td></tr>
<tr>
<td>
action</td><td>
It indicates the action performed in the grid.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerDeleteRow="OrdersGrid_ServerDeleteRow"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerDeleteRow(object sender, GridEventArgs e)

        {

          //code corresponding to any custom operation

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerEditRow

The **OnServerEditRow** event is triggered upon saving the edited record to the grid. The details of the edited record can be obtained from server-side, as explained in the following table.

_Table 6: Syncfusion.JavaScript.Web.GridEventArgs arguments of OnServerEditRow event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
data</td><td>
It returns the edited record details.</td></tr>
<tr>
<td>
action</td><td>
It indicates the action performed in the grid.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerEditRow="OrdersGrid_ServerEditRow"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerEditRow(object sender, GridEventArgs e)

        {

          //code corresponding to any custom operation

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerCommandButtonClick

The **OnServerCommandButtonClick** event is triggered when a command(pre-defined or custom) button is clicked. The selected row details and the button details is obtained from server-side.

_Table 2: Syncfusion.JavaScript.Web.GridEventArgs arguments of OnServerCommandButtonClick event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
rowIndex</td><td>
It indicates the index of the selected row.</td></tr>
<tr>
<td>
data</td><td>
It contains the JSON data of the selected row.</td></tr>
<tr>
<td>
buttonModel</td><td>
It contains the model of the ejButton clicked.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerCommandButtonClick="OrdersGrid_ServerCommandButtonClick"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column HeaderText="Employee Details" TextAlign="Center" Width="150">                    
                    <Command>
                        <ej:Commands Type="detail">
                            <ButtonOptions Text="Details" Width="100" Click="onClick"></ButtonOptions>
                        </ej:Commands>
                        <ej:Commands Type="edit">
                            <ButtonOptions Text="Edit"></ButtonOptions>
                        </ej:Commands>
                        <ej:Commands Type="delete">
                            <ButtonOptions Text="Delete"></ButtonOptions>
                        </ej:Commands>
                        <ej:Commands Type="save">
                            <ButtonOptions Text="Save"></ButtonOptions>
                        </ej:Commands>
                        <ej:Commands Type="cancel">
                            <ButtonOptions Text="Cancel"></ButtonOptions>
                        </ej:Commands>
                    </Command>
                </ej:Column>                     

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerCommandButtonClick(object sender, GridEventArgs e)

        {

          //code corresponding to any custom operation

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerRecordClick

The **OnServerRecordClick** event is triggered when a record is clicked. The selected record details and the selected record index is obtained from server-side.

_Table 2: Syncfusion.JavaScript.Web.GridEventArgs arguments of OnServerRecordClick event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
rowIndex</td><td>
It indicates the index of the selected record.</td></tr>
<tr>
<td>
data</td><td>
It contains the JSON data of the selected record.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerRecordClick="OrdersGrid_ServerRecordClick"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerRecordClick(object sender, GridEventArgs e)

        {

          //code corresponding to any custom operation

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerRecordDoubleClick

The **OnServerRecordDoubleClick** event is triggered when any grid record is double clicked. The details of the record double clicked can be obtained from server-side, as explained in the following table.

_Table 3: Syncfusion.JavaScript.Web.GridEventArgs arguments of OnServerRecordDoubleClick event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
rowIndex</td><td>
It indicates the index of the selected record.</td></tr>
<tr>
<td>
data</td><td>
It consists of the JSON data of the double clicked record.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerRecordDoubleClick="OrdersGrid_ServerRecordDoubleClick"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerRecordDoubleClick(object sender, GridEventArgs e)

        {

          //code corresponding to any custom operation

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerRowSelected

The **OnServerRowSelected** event is triggered when any of the rows are selected. The details of the row selected is obtained from server-side in the event argument.

_Table 1: Syncfusion.JavaScript.Web.GridEventArgs arguments of OnServerRowSelected event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
rowIndex</td><td>
It indicates the index of the selected record.</td></tr>
<tr>
<td>
data</td><td>
It consists of the JSON data of the selected record.</td></tr>
<tr>
<td>
prevRowIndex</td><td>
It returns the previously selected row index.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerRowSelected="OrdersGrid_ServerRowSelected"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerRowSelected(object sender, GridEventArgs e)

        {

          //code corresponding to custom operation

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerToolBarClick

The **OnServerToolBarClick** event is triggered when any of the toolbar icon is clicked. The details of the icon clicked can be obtained from server-side, as explained in the following table.

_Table 4: Syncfusion.JavaScript.Web.GridEventArgs arguments of OnServerToolBarClick event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
itemName</td><td>
It indicates the current toolbar item’s name.</td></tr>
<tr>
<td>
itemId</td><td>
It indicates the current toolbar id.</td></tr>
<tr>
<td>
itemIndex</td><td>
It returns the current index of toolbar item.</td></tr>
<tr>
<td>
itemCurrentTarget</td><td>
It returns the current HTML item.</td></tr>
<tr>
<td>
gridModel</td><td>
It returns the grid model in dictionary format.</td></tr>
<tr>
<td>
itemTarget</td><td>
It returns the HTML element of the target item.</td></tr>
<tr>
<td>
toolbarData</td><td>
It returns the toolbar model in a dictionary format.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerToolBarClick="OrdersGrid_ServerToolBarClick"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerToolBarClick(object sender, GridEventArgs e)

        {

          //code corresponding to any custom operation

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerExcelExporting

The **OnServerExcelExporting** event is triggered when a request is made to Export the grid to excel file. The grid model details can be obtained from server-side, as explained in the following table.

_Table 9: Syncfusion.JavaScript.Web.GridEventArgs argument of OnServerExcelExporting event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
model</td><td>
It returns the grid model details.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerExcelExporting="OrdersGrid_ServerExcelExporting"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel,excelExport,wordExport,pdfExport "></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerExcelExporting(object sender, GridEventArgs e)

        {

            ExcelExport exp = new ExcelExport();

            exp.Export(OrdersGrid.Model, (IEnumerable)OrdersGrid.DataSource, "Export.xlsx", ExcelVersion.Excel2010, true, true, "flat-lime");

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerExcelQueryCellInfo

The **OnServerExcelQueryCellInfo** event is triggered every time a data is entered into a cell of the Excel sheet. So this event is triggered as many times as the data is entered into a cell written in the excel sheet. The properties corresponding to the XlsIO IRange Class are obtained from server-side, as explained in the following table.

_Table 10: Argument of OnServerExcelQueryCellInfo event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
object</td><td>
object of type IRange class from Syncfusion.XlsIO which returns the properties of the IRange class.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerExcelQueryCellInfo="OrdersGrid_ServerExcelQueryCellInfo" OnServerExcelExporting="OrdersGrid_ServerExcelExporting"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel,excelExport,wordExport,pdfExport "></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();
        }

       protected void OrdersGrid_ServerExcelExporting(object sender, GridEventArgs e)

        {

            ExcelExport exp = new ExcelExport();

            exp.Export(OrdersGrid.Model, (IEnumerable)OrdersGrid.DataSource, "Export.xlsx", ExcelVersion.Excel2010, true, true, "flat-lime");

        }

       protected void OrdersGrid_ServerExcelQueryCellInfo(object obj)

        {

            IRange range = (IRange)obj;

            if(range.Value == "Berlin")

            range.CellStyle.ColorIndex = ExcelKnownColors.Aqua;

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerExcelRowInfo

The **OnServerExcelRowInfo** event is triggered every time a row is appended to the excel sheet. The properties corresponding to the XlsIO IRange Class are obtained server-side, as explained in the following table.

_Table 11: Argument of OnServerExcelRowInfo event_

<table>
<tr>
<th>
Argument</th><th>
Description</th></tr>
<tr>
<td>
object</td><td>
object of type IRange class from Syncfusion.XlsIO which returns the properties of the IRange class.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerExcelRowInfo="OrdersGrid_ServerExcelRowInfo" OnServerExcelExporting="OrdersGrid_ServerExcelExporting"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel,excelExport,wordExport,pdfExport "></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerExcelExporting(object sender, GridEventArgs e)

        {

            ExcelExport exp = new ExcelExport();

            exp.Export(OrdersGrid.Model, (IEnumerable)OrdersGrid.DataSource, "Export.xlsx", ExcelVersion.Excel2010, true, true, "flat-lime");

        }

       protected void OrdersGrid_ServerExcelRowInfo(object obj)

        {

            IRange range = (IRange)obj;

            if(range.Value == "Berlin")

            range.CellStyle.ColorIndex = ExcelKnownColors.Aqua;

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerPdfExporting

The **OnServerPdfExporting** event is triggered when a request to Export the grid to PDF document. The grid model details can be obtained server-side, as explained in the following table.

_Table 12: Syncfusion.JavaScript.Web.GridEventArgs argument of OnServerPdfExporting event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
model</td><td>
It returns the grid model details</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerPdfExporting="OrdersGrid_ServerPdfExporting"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel,excelExport,wordExport,pdfExport "></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerPdfExporting(object sender, GridEventArgs e)

        {

            PdfExport exp = new PdfExport();

            exp.Export(OrdersGrid.Model, (IEnumerable)OrdersGrid.DataSource, "Export.pdf", true, true, "flat-lime");

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerPdfQueryCellInfo

The **OnServerPdfQueryCellInfo** event is triggered every time data is written to the cell of the PdfGrid table. So this event is triggered as many times as that of the cell written to the grid table. The properties corresponding to the Pdf.Grid.PdfGridCell Class are obtained server-side, as explained in the following table.

_Table 13: Argument of OnServerPdfQueryCellInfo event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
object</td><td>
object of type PdfGridCell that returns the various properties of the PdfGridCell class of the Pdf.Grid namespace</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerPdfQueryCellInfo="OrdersGrid_ServerPdfQueryCellInfo" OnServerPdfExporting="OrdersGrid_ServerPdfExporting"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel,excelExport,wordExport,pdfExport "></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerPdfQueryCellInfo(object obj)

        {

            PdfGridCell gCell = (PdfGridCell)obj;

            if(gCell.Value == "Berlin")

            gCell.StringFormat = new PdfStringFormat(PdfTextAlignment.Left, PdfVerticalAlignment.Middle);

        }

       protected void OrdersGrid_ServerPdfExporting(object sender, GridEventArgs e)

        {

            PdfExport exp = new PdfExport();

            exp.Export(OrdersGrid.Model, (IEnumerable)OrdersGrid.DataSource, "Export.pdf", true, true, "flat-lime");

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerPdfRowInfo

The **OnServerPdfRowInfo** event is triggered every time a row is inserted to the PdfGrid. The properties corresponding to the Pdf.Grid.PdfGridRow Class are obtained server-side, as explained in the following table.

_Table 14: Argument of OnServerPdfRowInfo event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
object</td><td>
object of type PdfGridRow that returns the various properties of the PdfGridRow class of the Pdf.Grid namespace</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerPdfRowInfo="OrdersGrid_ServerPdfRowInfo" OnServerPdfExporting="OrdersGrid_ServerPdfExporting"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel,excelExport,wordExport,pdfExport "></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerPdfRowInfo(object obj)

        {

            PdfGridRow gRow = (PdfGridRow)obj;            

            gRow.Style.TextBrush = PdfBrushes.Pink;

        }

       protected void OrdersGrid_ServerPdfExporting(object sender, GridEventArgs e)

        {

            PdfExport exp = new PdfExport();

            exp.Export(OrdersGrid.Model, (IEnumerable)OrdersGrid.DataSource, "Export.pdf", true, true, "flat-lime");

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerWordExporting

The **OnServerWordExporting** event is triggered when a request to export the grid to a word document. The grid model details can be obtained server-side as explained in the following table.

_Table 15: Syncfusion.JavaScript.Web.GridEventArgs argument of OnServerWordExporting event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
model</td><td>
It returns the grid model details.</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerWordExporting="OrdersGrid_ServerWordExporting"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel,excelExport,wordExport,pdfExport "></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerWordExporting(object sender, GridEventArgs e)

        {

            WordExport exp = new WordExport();

            exp.Export(OrdersGrid.Model, (IEnumerable)OrdersGrid.DataSource, "Export.docx", true, true, "flat-lime");

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerWordQueryCellInfo

The **OnServerWordQueryCellInfo** event is triggered every time a cell data is written to the Word document. So this event is triggered as many times as that of the cell written to the word document. The properties corresponding to the DocIO.DLS.WTableCell Class is obtained server-side as explained in the following table.

_Table 16: Argument of OnServerWordQueryCellInfo event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
object</td><td>
Object of type WTableCell that returns the properties of the WTableCell Class of the DocIO.DLS namespace</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerWordQueryCellInfo="OrdersGrid_ServerWordQueryCellInfo" OnServerWordExporting="OrdersGrid_ServerWordExporting"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel,excelExport,wordExport,pdfExport "></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerWordQueryCellInfo(object obj)

        {

            WTableCell wCell = (WTableCell)obj;

            wCell.CellFormat.Borders.Color = Color.Magenta;

        }

       protected void OrdersGrid_ServerWordExporting(object sender, GridEventArgs e)

        {

            WordExport exp = new WordExport();

            exp.Export(OrdersGrid.Model, (IEnumerable)OrdersGrid.DataSource, "Export.docx", true, true, "flat-lime");

        }

    }
    
{% endhighlight %}

{% endtabs %}
    
## OnServerWordRowInfo

The **OnServerWordRowInfo** event is triggered every time a row is inserted into the word document. The properties corresponding to the DocIO.DLS.WTableRow Class is obtained server-side as explained in the following table.

_Table 17: Argument of OnServerWordRowInfo event_

<table>
<tr>
<th>
Arguments</th><th>
Description</th></tr>
<tr>
<td>
object</td><td>
Object of type WTableRow that returns the properties corresponding to the WTableRow class of the DocIO.DLS namespace</td></tr>
</table>

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" OnServerWordRowInfo="OrdersGrid_ServerWordRowInfo" OnServerWordExporting="OrdersGrid_ServerWordExporting"> 

       <EditSettings AllowEditing="true" AllowAdding="true" AllowDeleting="true"></EditSettings>

       <Columns>                                   

           <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

           <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="75" />

           <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="75" />

           <ej:Column Field="ShipCity" HeaderText="Ship City" Width="75" />                        

       </Columns>

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel,excelExport,wordExport,pdfExport "></ToolbarSettings>

   </ej:Grid> 

{% endhighlight %}

{% highlight c# %}

public partial class _Default : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            OrdersGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            OrdersGrid.DataBind();

        }

       protected void OrdersGrid_ServerWordRowInfo(object obj)

        {

            WTableRow wRow = (WTableRow)obj;

            wRow.RowFormat.Borders.Color = Color.Wheat;

        }

       protected void OrdersGrid_ServerWordExporting(object sender, GridEventArgs e)

        {

            WordExport exp = new WordExport();

            exp.Export(OrdersGrid.Model, (IEnumerable)OrdersGrid.DataSource, "Export.docx", true, true, "flat-lime");

        }

    }  
    
    {% endhighlight %}        
    
{% endtabs %}