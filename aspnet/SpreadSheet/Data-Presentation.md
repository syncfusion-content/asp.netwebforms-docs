---
layout: post
title: Data presentation | Essential ASP.NET Spreadsheet | Syncfusion
description: How to perform the proper representation of data with Syncfusion Essential ASP.NET Spreadsheet widget.
platform: aspnet
control: Spreadsheet
documentation: ug
--- 

# Spreadsheet Data Presentation

Data presentation is helpful for proper representation of data in Spreadsheet. You have following features in Data Presentation.

* Cell types
* Chart
* Conditional formatting
* Filtering 
* Picture
* Pivot table
* Sorting 
* Table

## Cell Type

You can insert the controls like Button, Checkbox, Dropdown list and Date picker. You can use `AllowCellType` property to enable/disable cell type operations.

### To insert a Cell Type.

You can insert the cell type to the selected range of cells by one of the following ways

* Using `CellTypes` property in sheets.
* Using [`addCellTypes`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlcelltype-addcelltypes "addCellTypes") method. 

### To remove Cell Type

You can delete the cell type in the selected range of cells by using [`removeCellTypes`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlcelltype-removecelltypes "removeCellTypes") method.

The following code example describes the above behavior. 

{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" AllowCellType="true" runat="server">
   <ClientSideEvents LoadComplete="loadComplete" />
        <Sheets>
                <ej:Sheet>
                    <RangeSettings>
                        <ej:RangeSetting StartCell="A1" />
                    </RangeSettings>
                    <CellTypes>
                        <ej:CellType Range="A1">
                            <Settings Type="DropDownList" DataSourceRange="A2:A11" />
                        </ej:CellType>
                        <ej:CellType Range="D1">
                            <Settings Type="Button" Text="Button1" BackgroundColor="green" />
                        </ej:CellType>
                        <ej:CellType Range="C1">
                            <Settings Type="DropDownList"  DataSourceRange="A2:A11" />
                        </ej:CellType>
                    </CellTypes>
                </ej:Sheet>
            </Sheets>
</ej:Spreadsheet>

<script type="text/javascript">
function loadComplete() {
            var excelCellType = this.XLCellType;
            if (!this.isImport) {
                excelCellType.addCellTypes("B1", { "type": ej.Spreadsheet.CustomCellType.DatePicker, 'value': '2/12/2016' }, 1);
                excelCellType.addCellTypes("E1", { "type": ej.Spreadsheet.CustomCellType.CheckBox, "isChecked": true }, 1);
                excelCellType.removeCellTypes("C1");
            }
        }
</script>
{% endhighlight %}



{% highlight c# %}

 protected void Page_Load(object sender, EventArgs e)
        {
            if (!IsPostBack)
            {
                BindDataSource();
            }
        }
 
  private void BindDataSource()
        {
             var dataSource = new OrderItemsDataContext().GetAllItemDetails.ToList();
            this.FlatSpreadsheet.Sheets[0].RangeSetting[0].Datasource = dataSource;  
        }
{% endhighlight %}

{% endtabs %}


The following output is displayed as a result of the above code example.

![Cell Type](Data-Presentation_images/Data-Presentation_img1.png)

## Chart

Chart is a graphical representation of data, that organizes and represents a set of numerical or qualitative data. It mostly displays the selected range of data in terms of x axis and y axis. You can use `AllowCharts` property to enable/disable chart operations.

### Types of Chart

The following types of charts are available in Spreadsheet.

* Area Chart
* Bar Chart
* Column Chart
* Line Chart
* Pie Chart
* Radar Chart
* Scatter Chart

You can create the Chart by one of the following ways,

* Using "Chart Type" button to Select the type of chart under Charts group of INSERT Tab in ribbon.
* Using [`createChart`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlchart-createchart "createChart") method to create the chart.

### Chart Customization

You can perform the following customizations for chart. These are available in DESIGN Tab which is enabled while clicking the chart element.

<table>
    <colgroup><col width="180px" /></colgroup>
    <tr><th>Feature</th><th>Description</th></tr>
    <tr><td>Add Chart Elements</td><td>You can add a chart element like chart axes, legends, chart title, axis title, data labels and grid lines.</td></tr>
    <tr><td>Switch Row/Column</td><td>You can switch the row of the chart to column of the chart and vice versa.</td></tr>
    <tr><td>Select Data</td><td>You can modify the data source of Chart.</td></tr>
    <tr><td>Chart Type</td><td>You can change the type of the chart using Chart Type dialog.</td></tr>
    <tr><td>Height and Width</td><td>You can change the height and width of the chart.</td></tr>
    <tr><td>Chart Themes</td><td>You can change the theme of the chart. The available themes are saffron, lemon and azure in dark, light themes.</td></tr>
</table>

The following code example describes the above behavior.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" AllowCharts="true" runat="server">
   <ClientSideEvents LoadComplete="loadComplete" />
        <Sheets>
                <ej:Sheet>
                    <RangeSettings>
                        <ej:RangeSetting StartCell="A1" />
                    </RangeSettings>
                </ej:Sheet>
            </Sheets>
</ej:Spreadsheet>

<script type="text/javascript">
function loadComplete() {
           if (!this.isImport) {
        this.XLChart.createChart("D1:E6", { type: "column", enable3D: false, marker: false, top: 40, left: 260, width: 340, height: 250 });
        this.performSelection("E1");
        this.XLChart.createChart("E1:F6", { type: "stackingcolumn", enable3D: false, marker: { visible: false }, top: 40, left: 620, width: 340, height: 250 });                     
    }
        }
</script>
{% endhighlight %}



{% highlight c# %}

 protected void Page_Load(object sender, EventArgs e)
        {
            if (!IsPostBack)
            {
                BindDataSource();
            }
        }
 
  private void BindDataSource()
        {
             var dataSource = new OrderItemsDataContext().GetAllItemDetails.ToList();
            this.FlatSpreadsheet.Sheets[0].RangeSetting[0].Datasource = dataSource;  
        }
{% endhighlight %}

{% endtabs %}

The following output is displayed as a result of the above code example.

![Chart](Data-Presentation_images/Data-Presentation_img2.png)

## Conditional Formatting

Conditional formatting helps you to apply formats to a cell or range with certain color based on the cells values. You can use `AllowConditionalFormats` property to enable/disable Conditional formats.

### Condition Definition

You can define conditions such as greater than, less than, between, equal to, text contains and date occurring for selected cells and defining value for condition. It highlights the specified cell. 
You can do this by one of the following ways,

* Using "Conditional Formatting" option in Conditional Formatting button of HOME Tab in ribbon to open the conditional formatting dialog.
* Using [`setCFRule`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlcformat-setcfrule "setCFRule") method to define the condition.

The following code example describes the above behavior.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" AllowConditionalFormats="true" runat="server">
    <ClientSideEvents LoadComplete="loadComplete" />
</ej:Spreadsheet>

<script type="text/javascript">
 function loadComplete() {
    var xlCFormat = this.XLCFormat;
    if (!this.isImport) {
        xlCFormat.setCFRule({ "action": "greaterthan", "inputs": ["10"], "color": "redft", "range": "G2:G11" });
        xlCFormat.setCFRule({ "action": "lessthan", "inputs": ["20"], "color": "yellowft", "range": "E1:E11" });
        xlCFormat.setCFRule({ "action": "between", "inputs": ["300", "600"], "color": "greenft", "range": "F2:F11" });
        xlCFormat.setCFRule({ "action": "textcontains", "inputs": ["loafers"], "color": "redt", "range": "A1:A11" });
        xlCFormat.setCFRule({ "action": "dateoccur", "inputs": ["02/04/2014"], "color": "redft", "range": "B1:B11" });
		xlCFormat.setCFRule({ "action": "databar", "color": "redft", "range": "H1:H11" });
		xlCFormat.setCFRule({action: "colorscale", color: "gyr", range: "D2:D11"});
    }
}
</script>
{% endhighlight %}



{% highlight c# %}

 protected void Page_Load(object sender, EventArgs e)
        {
            if (!IsPostBack)
            {
                BindDataSource();
            }
        }
 
  private void BindDataSource()
        {
             var dataSource = new OrderItemsDataContext().GetAllItemDetails.ToList();
            this.FlatSpreadsheet.Sheets.Add(new Syncfusion.JavaScript.Models.Sheet()
            {
                Datasource = dataSource

            });
        }
{% endhighlight %}

{% endtabs %}


The following output is displayed as a result of the above code example.

![Conditional Formatting](Data-Presentation_images/Data-Presentation_img3.png)

### Clear Rules

You can clear the defined rules by using one of the following ways,

* Using "Clear Rules" option in Conditional Formatting button of HOME Tab in ribbon to clear the rule.
* Using [`clearCF`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlcformat-clearcf "clearCF") method to clear the defined rules.

The following code example describes the above behavior.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" AllowConditionalFormats="true" runat="server">
    <ClientSideEvents LoadComplete="loadComplete" />
</ej:Spreadsheet>

<script type="text/javascript">
 function loadComplete() {
    var excelFormat = this.XLCFormat;
    if (!this.isImport) {
        excelFormat.setCFRule({ "action": "greaterthan", "inputs": ["10"], "color": "redft", "range": "G2:G11" });
        excelFormat.setCFRule({ "action": "lessthan", "inputs": ["20"], "color": "yellowft", "range": "E1:E11" });
        excelFormat.setCFRule({ "action": "between", "inputs": ["300", "600"], "color": "greenft", "range": "F2:F11" });
        excelFormat.clearCF(true, "G2:G11");
        excelFormat.clearCF(true, "F2:F11");
    }
}
</script>
{% endhighlight %}



{% highlight c# %}

 protected void Page_Load(object sender, EventArgs e)
        {
            if (!IsPostBack)
            {
                BindDataSource();
            }
        }
 
  private void BindDataSource()
        {
             var dataSource = new OrderItemsDataContext().GetAllItemDetails.ToList();
            this.FlatSpreadsheet.Sheets.Add(new Syncfusion.JavaScript.Models.Sheet()
            {
                Datasource = dataSource

            });
        }
{% endhighlight %}

{% endtabs %}

The following output is displayed as a result of the above code example.

![Clear Rules](Data-Presentation_images/Data-Presentation_img4.png)

## Filtering

Filtering allows you to view specific rows in Spreadsheet, while hiding the other rows. When a filter is added to the header row, a drop-down menu appears in each cell of the header row. You can use `AllowFiltering` property to enable/disable filtering. 

You can apply filtering by one of the following ways,

* Using "Filter" option in Sort & Filter button under Editing group of HOME Tab in ribbon.
* Using "Filter" button under Sort and Filter group of DATA Tab in ribbon.

You have following options in Filtering.

* Filter by Value.
* Filter by Color.
* Clear Filter.

### Filter by Value

You can perform filtering by using number, string. The filtered rows are only visible in the Spreadsheet. All the other rows within the filtered range were hidden.

You can do this by one of the following ways,

* Using dropdown button in filter header to open the filter dialog.
* Using context menu to select "Filter by Selected Cell's Value" option in Filter. 
* Using [`filterByActiveCell`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlfilter-filterbyactivecell "filterByActiveCell") method.

The following code example describes the above behavior.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" AllowFiltering="true" runat="server">
    <ClientSideEvents LoadComplete="loadComplete" />
</ej:Spreadsheet>

<script type="text/javascript">
 function loadComplete() {
    var excelFilter = this.XLFilter;
    if (!this.isImport) {
        this.performSelection("E2");
        excelFilter.filterByActiveCell();
    }
}
</script>
{% endhighlight %}



{% highlight c# %}

 protected void Page_Load(object sender, EventArgs e)
        {
            if (!IsPostBack)
            {
                BindDataSource();
            }
        }
 
  private void BindDataSource()
        {
             var dataSource = new OrderItemsDataContext().GetAllItemDetails.ToList();
            this.FlatSpreadsheet.Sheets.Add(new Syncfusion.JavaScript.Models.Sheet()
            {
                Datasource = dataSource

            });
        }
{% endhighlight %}

{% endtabs %}

The following output is displayed as a result of the above code example.

![Filtering](Data-Presentation_images/Data-Presentation_img5.png)

### Filter by Color

You can perform filtering by the selected cell color or font color. The filtered rows are only visible in the Spreadsheet. You can do this by clicking "Filter by Color" option in filter dialog to select filter by cell color or font color.

N> This option is only available if the selected range of cells having any color.

### Clear Filter

You can clear the filtering to show all the filtered rows in the spreadsheet within the filtered range.

You can do this by one of the following ways,

* Using "Clear Filter" option in the filter dialog.
* Using context menu to select "Clear Filter" option in Filter.
* Using "Clear Filter" option in "Sort & Filter" button under Editing group of HOME Tab in ribbon.
* Using "Clear Filter" option under Sort and Filter group of DATA Tab in ribbon.
* Using [`clearFilter`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlfilter-clearfilter "clearFilter") method to perform clear filtering.

The following code example describes the above behavior.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" AllowFiltering="true" runat="server">
    <ClientSideEvents LoadComplete="loadComplete" />
</ej:Spreadsheet>

<script type="text/javascript">
 function loadComplete() {
    var excelFilter = this.XLFilter;
    if (!this.isImport) {
        this.performSelection("E2");
        excelFilter.filterByActiveCell();
        excelFilter.clearFilter();
    }
}
</script>
{% endhighlight %}



{% highlight c# %}

 protected void Page_Load(object sender, EventArgs e)
        {
            if (!IsPostBack)
            {
                BindDataSource();
            }
        }
 
  private void BindDataSource()
        {
             var dataSource = new OrderItemsDataContext().GetAllItemDetails.ToList();
            this.FlatSpreadsheet.Sheets.Add(new Syncfusion.JavaScript.Models.Sheet()
            {
                Datasource = dataSource

            });
        }
{% endhighlight %}

{% endtabs %}

The following output is displayed as a result of the above code example.

![Clear Filter](Data-Presentation_images/Data-Presentation_img6.png)

## Picture

You can insert a picture by selecting the "Pictures" button under Illustrations group of INSERT Tab in ribbon.

### Picture Customization

You can perform the following customizations for picture. These are available in DESIGN Tab which is enabled while clicking the picture element.

<table>
    <colgroup><col width="150px" /></colgroup>
    <tr><th>Feature</th><th>Description</th></tr>
    <tr><td>Change Picture</td><td>You can change the picture with existing picture.</td></tr>
    <tr><td>Reset Picture</td><td>You can reset the changes done in the picture such as border changes, height and width changes.</td></tr>
    <tr><td>Picture Border</td><td>You can add border to the picture. You have Border Color, Border Type and Border weight options to draw a border.</td></tr>
    <tr><td>Height and Width</td><td>You can change the height and width of the picture.</td></tr>
</table>

## Pivot Table

Pivot table is a program tool that allows you to reorganize and summarize selected columns and rows of data to obtain a desired report. You can use `EnablePivotTable` property to enable/disable pivot table operations. 

You can do this by one of the following ways,

* Using "Pivot Table" option under Tables group of INSERT Tab in ribbon.
* Using [`createPivotTable`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlpivot-createpivottable "createPivotTable") method to create pivot table
* Using [`deletePivotTable`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlpivot-deletepivottable "deletePivotTable") method to remove the pivot table.

The following code example describes the above behavior.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" EnablePivotTable="true" runat="server">
    <ClientSideEvents LoadComplete="loadComplete" />
</ej:Spreadsheet>

<script type="text/javascript">
function loadComplete() {
    if (!this.isImport) {
        var settings = {
            rows: [{fieldName: "Country"}, { fieldName: "State"}],
            columns: [{fieldName: "Product"}],
            values: [{fieldName: "Amount"},{fieldName: "Quantity"}],
            filters: [{fieldName: "Date"}]
        };
        this.XLPivot.createPivotTable("Sheet1!$A$1:$F$25", null, null, settings); 
        //this.XLPivot.deletePivotTable("name");
    }
}
</script>
{% endhighlight %}



{% highlight c# %}

 protected void Page_Load(object sender, EventArgs e)
        {
            BindDataSource();
        }
 
  private void BindDataSource()
        {
             List<PivotData> data = new List<PivotData>();

            data.Add(new PivotData() { Amount = 100, Country = "Canada", Date = "FY 2005", Product = "Bike", Quantity = 2, State = "Alberta" });
            data.Add(new PivotData() { Amount = 200, Country = "Canada", Date = "FY 2006", Product = "Van", Quantity = 3, State = "British Columbia" });
            data.Add(new PivotData() { Amount = 300, Country = "Canada", Date = "FY 2007", Product = "Car", Quantity = 4, State = "Brunswick" });
            data.Add(new PivotData() { Amount = 150, Country = "Canada", Date = "FY 2008", Product = "Bike", Quantity = 3, State = "Manitoba" });
            data.Add(new PivotData() { Amount = 200, Country = "Canada", Date = "FY 2006", Product = "Car", Quantity = 4, State = "Ontario" });
            data.Add(new PivotData() { Amount = 100, Country = "Canada", Date = "FY 2007", Product = "Van", Quantity = 1, State = "Quebec" });
            data.Add(new PivotData() { Amount = 200, Country = "France", Date = "FY 2005", Product = "Bike", Quantity = 2, State = "Charente-Maritime" });
            data.Add(new PivotData() { Amount = 250, Country = "France", Date = "FY 2006", Product = "Van", Quantity = 4, State = "Essonne" });
            data.Add(new PivotData() { Amount = 300, Country = "France", Date = "FY 2007", Product = "Car", Quantity = 3, State = "Garonne (Haute)" });
            data.Add(new PivotData() { Amount = 150, Country = "France", Date = "FY 2008", Product = "Van", Quantity = 2, State = "Gers" });
            data.Add(new PivotData() { Amount = 200, Country = "Germany", Date = "FY 2006", Product = "Van", Quantity = 3, State = "Bayern" });
            data.Add(new PivotData() { Amount = 250, Country = "Germany", Date = "FY 2007", Product = "Car", Quantity = 3, State = "Brandenburg" });
            data.Add(new PivotData() { Amount = 150, Country = "Germany", Date = "FY 2008", Product = "Car", Quantity = 4, State = "Hamburg" });
            data.Add(new PivotData() { Amount = 200, Country = "Germany", Date = "FY 2008", Product = "Bike", Quantity = 4, State = "Hessen" });
            data.Add(new PivotData() { Amount = 150, Country = "Germany", Date = "FY 2007", Product = "Van", Quantity = 3, State = "Nordrhein-Westfalen" });
            data.Add(new PivotData() { Amount = 100, Country = "Germany", Date = "FY 2005", Product = "Bike", Quantity = 2, State = "Saarland" });
            data.Add(new PivotData() { Amount = 150, Country = "United Kingdom", Date = "FY 2008", Product = "Bike", Quantity = 5, State = "England" });
            data.Add(new PivotData() { Amount = 250, Country = "United States", Date = "FY 2007", Product = "Car", Quantity = 4, State = "Alabama" });
            data.Add(new PivotData() { Amount = 200, Country = "United States", Date = "FY 2005", Product = "Van", Quantity = 4, State = "California" });
            data.Add(new PivotData() { Amount = 100, Country = "United States", Date = "FY 2006", Product = "Bike", Quantity = 2, State = "Colorado" });
            data.Add(new PivotData() { Amount = 150, Country = "United States", Date = "FY 2008", Product = "Car", Quantity = 3, State = "New Mexico" });
            data.Add(new PivotData() { Amount = 200, Country = "United States", Date = "FY 2005", Product = "Bike", Quantity = 4, State = "New York" });
            data.Add(new PivotData() { Amount = 250, Country = "United States", Date = "FY 2008", Product = "Car", Quantity = 3, State = "North Carolina" });
            data.Add(new PivotData() { Amount = 300, Country = "United States", Date = "FY 2007", Product = "Van", Quantity = 4, State = "South Carolina" });

            this.FlatSpreadsheet.Sheets.Add(new Syncfusion.JavaScript.Models.Sheet()
            {
                Datasource = data
            });
        }

        [Serializable]
        public class PivotData
        {
            public int Amount { get; set; }
            public string State { get; set; }
            public int Quantity { get; set; }
            public string Product { get; set; }
            public string Date { get; set; }
            public string Country { get; set; }
        }
        
{% endhighlight %}

{% endtabs %}


The following output is displayed as a result of the above code example.

![Pivot Table](Data-Presentation_images/Data-Presentation_img7.png)

## Sorting

Sorting helps you to arrange the data to particular order in a selected range of cells. You can use `AllowSorting` property to enable/disable sorting. 

You have following options in sorting.

* Sort by Ascending or Descending.
* Sort by Color.

### Sort by Ascending and Descending

You can perform number sorting by ascending or descending and string sorting by A to Z or Z to A to arrange the data. 

You can do this by one of the following ways,

* By choosing "Sort A to Z" or "Sort Z to A" in Sort & Filter button under Editing group of HOME Tab in ribbon. 
* Using "Sort A to Z" or "Sort Z to A" button in Sort & Filter group of DATA Tab in ribbon.
* Using context menu to select "Sort A to Z" or "Sort Z to A" for strings and option in Sort.
* Using "Sort A to Z" or "Sort Z to A" for strings an "Sort Smallest to Largest" or "Sort Largest to Smallest" for numbers in filter dialog.
* Using [`sortByRange`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlsort-sortbyrange "sortByRange") method.

The following code example describes the above behavior.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" AllowSorting="true" runat="server">
    <ClientSideEvents LoadComplete="loadComplete" />
</ej:Spreadsheet>

<script type="text/javascript">
 function loadComplete() {
    var excelSort = this.XLSort, XLFormat = this.XLFormat;
    if (!this.isImport) {
        excelSort.sortByRange("A2:A10", "A", "ascending");
        excelSort.sortByRange("E2:E10", "E", "descending");     
    }
}
</script>
{% endhighlight %}



{% highlight c# %}

 protected void Page_Load(object sender, EventArgs e)
        {
            if (!IsPostBack)
            {
                BindDataSource();
            }
        }
 
  private void BindDataSource()
        {
             var dataSource = new OrderItemsDataContext().GetAllItemDetails.ToList();
            this.FlatSpreadsheet.Sheets.Add(new Syncfusion.JavaScript.Models.Sheet()
            {
                Datasource = dataSource

            });
        }
{% endhighlight %}

{% endtabs %}

The following output is displayed as a result of the above code example.

![Sorting](Data-Presentation_images/Data-Presentation_img8.png)

### Sort by Color

You can perform sort by color to arrange the data based on the selected cell's background color or font color. This option is only available if the selected range of cells having any color.

You can do this by one of the following ways,

* Using "Sort By Color" option in filter dialog to perform sorting by cell color or font color.
* Using context menu to select "Put Selected Cell Color To The Top" or "Put Selected Font Color To The Top" in Sort option.

## Table

A table is a data structure that organizes information into rows and columns. You can use `AllowFormatAsTable` property to enable/disable table operations. 

You can do this by one of the following ways,

* Using "Format As Table" under Styles group of HOME Tab in ribbon.
* Using Table option under Tables group of INSERT Tab in ribbon.
* Using [`createTable`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlformat-createtable "createTable") method to insert a table and [`removeTable`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlformat-removetable "removeTable") to delete a table.

### Table Customization

You can perform the following customizations for table. These are available in DESIGN Tab which is enabled while clicking the table.

<table>
    <colgroup><col width="150px" /></colgroup>
    <tr><th>Feature</th><th>Description</th></tr>
    <tr><td>Resize Table</td><td>You can resize the table only to increase row count.</td></tr>
    <tr><td>Convert to Range</td><td>You can remove the table using this option.</td></tr>
    <tr><td>First Column</td><td>You can highlight the first column of the table.</td></tr>
    <tr><td>Last Column</td><td>You can highlight the last column of the table.</td></tr>
    <tr><td>Total Row</td><td>You can insert a new row in the bottom of the table to display the total value of the last column. You can toggle this by using checkbox.</td></tr>
    <tr><td>Filter Button</td><td>You can able to hide or unhide the filter icons in the filter header of a table.</td></tr>
</table>

The following code example describes the above behavior.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" AllowFormatAsTable="true" runat="server">
    <ClientSideEvents LoadComplete="loadComplete" />
        <Sheets>
            <ej:Sheet>
                 <RangeSettings>
                        <ej:RangeSetting ShowHeader="false" />
                    </RangeSettings>
                </ej:Sheet>
            </Sheets>
</ej:Spreadsheet>

<script type="text/javascript">
function loadComplete() {
    var excelFormat = this.XLFormat;
    if (!this.isImport) {
        excelFormat.createTable({ "header": true, "formatName": "TableStyleLight8" }, "A1:B4");
        excelFormat.createTable({ "header": true, "formatName": "TableStyleLight10" }, "D1:E4");
    }
}
</script>
{% endhighlight %}



{% highlight c# %}

 protected void Page_Load(object sender, EventArgs e)
        {
            BindDataSource();
        }

        private void BindDataSource()
        {
            var dataSource = new OrderItemsDataContext().GetTableDetails.ToList();
            this.Spreadsheet.Sheets[0].RangeSetting[0].Datasource = dataSource;
        }
{% endhighlight %}

{% endtabs %}
The following output is displayed as a result of the above code example.

![Table](Data-Presentation_images/Data-Presentation_img9.png)