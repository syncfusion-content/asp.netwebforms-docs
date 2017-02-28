---
layout: post
title: Server-side-event-arguments with Spreadsheet widget for Syncfusion Essential ASP.NET
description: server side event arguments in asp Spreadsheet
platform: aspnet
control: Spreadsheet
documentation: ug
---

## Server side events

This section explains in detail about the server-side events available in the **ASP Spreadsheet control** and the arguments that are obtained server-side. 

The **sender** parameter of all the server-side events returns the spreadsheet model details.

The various server-side events and the arguments corresponding to the events are as follows:

## OnServerCellSave

The **OnServerCellSave** event is triggered upon saving the cell in the spreadsheet control. The details of the cell can be obtained server-side, as explained in the following table.


<table class="params">
<thead>
<tr>
<th>Name</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td class="name">argument</td>
<td class="type"><span class="param-type">object</span></td>
<td class="description">Arguments when cellSave event is triggered. 
<table class="params">
<thead>
<tr>
<th>Name</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td class="name">cell</td>
<td class="type"><span class="param-type">Element</span></td>
<td class="description">Returns the save cell element.</td>
</tr>
<tr>
<td class="name">columnName</td>
<td class="type"><span class="param-type">string</span></td>
<td class="description">Returns the columnName of clicked cell.</td>
</tr>
<tr>
<td class="name">columnObject</td>
<td class="type"><span class="param-type">object</span></td>
<td class="description">Returns the column field information.</td>
</tr>
<tr>
<td class="name">rowIndex</td>
<td class="type"><span class="param-type">Number</span></td>
<td class="description">Returns the index of the row.</td>
</tr>
<tr>
<td class="name">colIndex</td>
<td class="type"><span class="param-type">Number</span></td>
<td class="description">Returns the index of the column.</td>
</tr>
<tr>
<td class="name">model</td>
<td class="type"><ts ref="ej.Spreadsheet.Model"/><span class="param-type">object</span></td>
<td class="description">Returns the Spreadsheet model.</td>
</tr>
<tr>
<td class="name">pValue</td>
<td class="type"><span class="param-type">string</span></td>
<td class="description">Returns the previous value of the cell.</td>
</tr>
<tr>
<td class="name">type</td>
<td class="type"><span class="param-type">string</span></td>
<td class="description">Returns the name of the event.</td>
</tr>
<tr>
<td class="name">cancel</td>
<td class="type"><span class="param-type">boolean</span></td>
<td class="description">Returns the cancel option value.</td>
</tr>
<tr>
<td class="name">target</td>
<td class="type"><span class="param-type">Element</span></td>
<td class="description">Returns the target element.</td>
</tr>
<tr>
<td class="name">value</td>
<td class="type"><span class="param-type">string</span></td>
<td class="description">Returns the cell value.</td>
</tr>
</tbody>
</table>
</td></tr>
</tbody>
</table>

{% tabs %}

{% highlight html %}

 <ej:Spreadsheet ID="Spreadsheet" OnServerCellSave="Spreadsheet_ServerCellSave" runat="server">
                </ej:Spreadsheet>

{% endhighlight %}

 {% highlight c# %}

 public partial class ServerSaveEvent : System.Web.UI.Page
    {
        private List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)
        {
            if (!IsPostBack)
            {
                BindDataSource();
                ViewState["DataSource"] = order;
            }
        }

        private void BindDataSource()
        {
            int code = 10000;
            for (int i = 1; i <= 20; i++)
            {
                order.Add(new Orders(code + 1, "TOMSP", i + 0, "Münster", "Toms Spezialitäten", "Germany"));
                order.Add(new Orders(code + 2, "HANAR", i + 2, "Rio de Janeiro", "Hanari Carnes", "Brazil"));
                order.Add(new Orders(code + 3, "VICTE", i + 1, "Lyon", "Victuailles en stock", "France"));
                order.Add(new Orders(code + 4, "VINET", i + 3, "Reims", "Vins et alcools Chevalier", "France"));
                order.Add(new Orders(code + 5, "SUPRD", i + 4, "Charleroi", "Suprêmes délices", "Belgium"));
                code += 5;
            }
            this.Spreadsheet.Sheets[0].RangeSetting[0].Datasource = order;
        }

        [Serializable]
        public class Orders
        {
            public Orders()
            {

            }
            public Orders(long OrderId, string CustomerId, int EmployeeId, string ShipCity, string ShipName, string ShipCountry)
            {
                this.OrderID = OrderId.ToString();
                this.CustomerID = CustomerId;
                this.EmployeeID = EmployeeId.ToString();
                this.ShipName = ShipName;
                this.ShipCity = ShipCity;
                this.ShipCountry = ShipCountry;
            }
            public string OrderID { get; set; }
            public string CustomerID { get; set; }
            public string EmployeeID { get; set; }
            public string ShipCity { get; set; }
            public string ShipName { get; set; }
            public string ShipCountry { get; set; }
        }

        protected void Spreadsheet_ServerCellSave(object sender, SpreadsheetEventArgs e)
        {
            List<Orders> data = ViewState["DataSource"] as List<Orders>;
            Dictionary<string, object> KeyVal = e.Arguments as Dictionary<string, object>;
            var rowIdx = Convert.ToInt32(KeyVal["rowIndex"]);

            if (e.EventType == "cellSave" && rowIdx < data.Count)
            {
                Orders record = data[rowIdx];
                var colIdx = Convert.ToInt32(KeyVal["colIndex"]);
                if (colIdx < record.GetType().GetProperties().Length)
                {
                    var value = KeyVal["value"];
                    string colName = record.GetType().GetProperties()[Convert.ToInt32(KeyVal["colIndex"])].Name;
                    if (colName == "OrderID")
                        record.OrderID = Convert.ToString(value);
                    else if (colName == "CustomerID")
                        record.CustomerID = Convert.ToString(value);
                    else if (colName == "EmployeeID")
                        record.EmployeeID = Convert.ToString(value);
                    else if (colName == "ShipCity")
                        record.ShipCity = Convert.ToString(value);
                    else if (colName == "ShipCountry")
                        record.ShipCountry = Convert.ToString(value);
                    else if (colName == "ShipName")
                        record.ShipName = Convert.ToString(value);
                }
            }
            ViewState["DataSource"] = data;
            this.Spreadsheet.Sheets[0].RangeSetting[0].Datasource = data;
            serverEvent.InnerHtml = serverEvent.InnerHtml + span + "cell Save</span> event called</span><hr>";
        }
    }
}
    
 {% endhighlight %}
    
{% endtabs %}


## OnServerExcelExporting

The OnServerExcelExporting event is triggered when a request to export the Spreadsheet to excel document. The spreadsheet model details can be obtained server-side, as explained in the following table.


<table class="params">
<thead>
<tr>
<th>Name</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td class="name">argument</td>
<td class="type"><span class="param-type">object</span></td>
<td class="description">Arguments when excel export event is triggered. 
<table class="params">
<thead>
<tr>
<th>Name</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td class="name">password</td>
<td class="type"><span class="param-type">string</span></td>
<td class="description">Returns the password for the excel document.</td>
</tr>
<tr>
<td class="name">sheetModel</td>
<td class="type"><span class="param-type">object</span></td>
<td class="description">Returns the sheet model.</td>
</tr>
<tr>
<td class="name">sheetData</td>
<td class="type"><span class="param-type">object</span></td>
<td class="description">Returns the sheet data.</td>
</tr>
</tbody>
</table>
</td></tr>
</tbody>
</table>

{% tabs %}

{% highlight html %}

 <ej:Spreadsheet ID="Spreadsheet" OnServerExcelExporting="Spreadsheet_ServerExcelExporting" runat="server">
                </ej:Spreadsheet>

{% endhighlight %}

 {% highlight c# %}

 protected void Spreadsheet_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.SpreadsheetEventArgs e)
        {
            var args = e.Arguments;
            string password = args["password"].ToString();
            string sheetModel = args["sheetModel"].ToString();
            string sheetData = args["sheetData"].ToString();

            if (!string.IsNullOrEmpty(password))

                Spreadsheet.Save(sheetModel, sheetData, "sample", ExportFormat.XLSX, ExcelVersion.Excel2013, password);
            else
                Spreadsheet.Save(sheetModel, sheetData, "sample", ExportFormat.XLSX, ExcelVersion.Excel2013);
        }
    
{% endhighlight %}
    
{% endtabs %}	


## OnServerCsvExporting

The OnServerCsvExporting event is triggered when a request to export the Spreadsheet to csv document. The spreadsheet model details can be obtained server-side, as explained in the following table.


<table class="params">
<thead>
<tr>
<th>Name</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td class="name">argument</td>
<td class="type"><span class="param-type">object</span></td>
<td class="description">Arguments when csv export event is triggered. 
<table class="params">
<thead>
<tr>
<th>Name</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td class="name">sheetModel</td>
<td class="type"><span class="param-type">object</span></td>
<td class="description">Returns the sheet model.</td>
</tr>
<tr>
<td class="name">sheetData</td>
<td class="type"><span class="param-type">object</span></td>
<td class="description">Returns the sheet data.</td>
</tr>
</tbody>
</table>
</td></tr>
</tbody>
</table>

{% tabs %}

{% highlight html %}

 <ej:Spreadsheet ID="Spreadsheet" OnServerCsvExporting="Spreadsheet_ServerCsvExporting" runat="server">
                </ej:Spreadsheet>

{% endhighlight %}

 {% highlight c# %}

  protected void Spreadsheet_ServerCsvExporting(object sender, Syncfusion.JavaScript.Web.SpreadsheetEventArgs e)
        {
            var args = e.Arguments;
            Spreadsheet.Save(args["sheetModel"].ToString(), args["sheetData"].ToString(), "sample", ExportFormat.CSV);
        }

    
{% endhighlight %}
    
{% endtabs %}	

## OnServerPdfExporting

The OnServerPdfExporting event is triggered when a request to export the Spreadsheet to pdf document. The spreadsheet model details can be obtained server-side, as explained in the following table.


<table class="params">
<thead>
<tr>
<th>Name</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td class="name">argument</td>
<td class="type"><span class="param-type">object</span></td>
<td class="description">Arguments when pdf export event is triggered. 
<table class="params">
<thead>
<tr>
<th>Name</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td class="name">sheetModel</td>
<td class="type"><span class="param-type">object</span></td>
<td class="description">Returns the sheet model.</td>
</tr>
<tr>
<td class="name">sheetData</td>
<td class="type"><span class="param-type">object</span></td>
<td class="description">Returns the sheet data.</td>
</tr>
</tbody>
</table>
</td></tr>
</tbody>
</table>

{% tabs %}

{% highlight html %}

 <ej:Spreadsheet ID="Spreadsheet" OnServerPdfExporting="Spreadsheet_ServerPdfExporting" runat="server">
                </ej:Spreadsheet>

{% endhighlight %}

 {% highlight c# %}

 protected void Spreadsheet_ServerPdfExporting(object sender, Syncfusion.JavaScript.Web.SpreadsheetEventArgs e)
        {
            var args = e.Arguments;
            Spreadsheet.Save(args["sheetModel"].ToString(), args["sheetData"].ToString(), "sample", ExportFormat.PDF);
        }
    
 {% endhighlight %}
    
{% endtabs %}	
