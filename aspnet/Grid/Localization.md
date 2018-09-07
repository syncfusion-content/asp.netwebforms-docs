---
layout: post
title: Localization with Grid widget for Syncfusion Essential ASP.NET
description: How to use globalization and localization
platform: aspnet
control: Grid
documentation: ug
---


# Globalization and Localization

## Localization

All text in Grid can be localized using `ej.Grid.Locale` object. Please find the table with list of properties and its value in locale object.

<table>
<tr>
<th>
Locale key words </th><th>
Text</th></tr>
<tr>
<td>
EmptyRecord</td><td>
No records to display</td></tr>
<tr>
<td>
PagerInfo</td><td>
{0} of {1} pages ({2} items)</td></tr>
<tr>
<td>
GroupDropArea</td><td>
Drag a column header here to group its column</td></tr>
<tr>
<td>
DeleteOperationAlert</td><td>
No records selected for delete operation</td></tr>
<tr>
<td>
EditOperationAlert</td><td>
No records selected for edit operation</td></tr>
<tr>
<td>
SaveButton</td><td>
Save</td></tr>
<tr>
<td>
OKButton</td><td>
OK</td></tr>
<tr>
<td>
CancelButton</td><td>
Cancel</td></tr>
<tr>
<td>
EditFormTitle</td><td>
Details of</td></tr>
<tr>
<td>
AddFormTitle</td><td>
Add New Record</td></tr>
<tr>
<td>
GroupCaptionFormat</td><td>
{{"{{"}}:headerText{{}}}}: {{"{{"}}:key{{}}}} - {{"{{"}}:count{{}}}} {{"{{"}}if count == 1 {{}}}} item {{"{{"}}else{{}}}} items {{"{{"}}/if{{}}}}</td></tr>
<tr>
<td>
BatchSaveConfirm</td><td>
Are you sure you want to save changes?</td></tr>
<tr>
<td>
BatchSaveLostChanges</td><td>
Unsaved changes will be lost. Are you sure you want to continue?</td></tr>
<tr>
<td>
ConfirmDelete</td><td>
Are you sure you want to Delete Record?</td></tr>
<tr>
<td>
FrozenColumnsViewAlert</td><td>
Frozen columns should be in grid view area</td></tr>
<tr>
<td>
FrozenColumnsScrollAlert</td><td>
Enable allowScrolling while using frozen Columns</td></tr>
<tr>
<td>
FrozenNotSupportedException</td><td>
Frozen Columns and Rows are not supported for Grouping, Row Template, Detail Template, Hierarchy Grid and Batch Editing</td></tr>
<tr>
<td>
Add</td><td>
Add</td></tr>
<tr>
<td>
Edit</td><td>
Edit</td></tr>
<tr>
<td>
Delete</td><td>
Delete</td></tr>
<tr>
<td>
Update</td><td>
Update</td></tr>
<tr>
<td>
Cancel</td><td>
Cancel</td></tr>
<tr>
<td>
Done</td><td>
Done</td></tr>
<tr>
<td>
Columns</td><td>
Columns</td></tr>
<tr>
<td>
PrintGrid</td><td>
Print</td></tr>
<tr>
<td>
ExcelExport</td><td>
Excel Export</td></tr>
<tr>
<td>
WordExport</td><td>
Word Export</td></tr>
<tr>
<td>
PdfExport</td><td>
PDF Export</td></tr>
<tr>
<td>
StringMenuOptions</td><td>
[{text: "StartsWith",value: "StartsWith"},{text: "EndsWith",value: "EndsWith"},{text: "Contains",value: "Contains"},{text: "Equal",value: "Equal"},{text: "NotEqual",value: "NotEqual"}]</td></tr>
<tr>
<td>
NumberMenuOptions</td><td>
[{text: "LessThan",value: "LessThan"},{text: "GreaterThan",value: "GreaterThan"},{text: "LessThanOrEqual",value: "LessThanOrEqual"},{text: "GreaterThanOrEqual",value: "GreaterThanOrEqual"},{text: "Equal",value: "Equal"},{text: "NotEqual",value: "NotEqual"}]</td></tr>
<tr>
<td>
PredicateAnd</td><td>
AND</td></tr>
<tr>
<td>
PredicateOr</td><td>
OR</td></tr>
<tr>
<td>
Filter</td><td>
Filter</td></tr>
<tr>
<td>
FilterMenuCaption</td><td>
Filter Value</td></tr>
<tr>
<td>
FilterbarTitle</td><td>
's filter bar cell</td></tr>
<tr>
<td>
MatchCase</td><td>
Match Case</td></tr>
<tr>
<td>
Clear</td><td>
Clear</td></tr>
<tr>
<td>
ResponsiveFilter</td><td>
Filter</td></tr>
<tr>
<td>
ResponsiveSorting</td><td>
Sort</td></tr>
<tr>
<td>
Search</td><td>
Search</td></tr>
<tr>
<td>
DatePickerWaterMark</td><td>
Select date</td></tr>
<tr>
<td>
EmptyDataSource</td><td>
DataSource must not be empty at initial load since columns are generated from dataSource in AutoGenerate Column Grid</td></tr>
<tr>
<td>
True</td><td>
True</td></tr>
<tr>
<td>
False</td><td>
False</td></tr>
<tr>
<td>
UnGroup</td><td>
Click here to ungroup</td></tr>
<tr>
<td>
AddRecord</td><td>
Add Record</td></tr>
<tr>
<td>
EditRecord</td><td>
Edit Record</td></tr>
<tr>
<td>
DeleteRecord</td><td>
Delete Record</td></tr>
<tr>
<td>
Save</td><td>
Save</td></tr>
<tr>
<td>
Grouping</td><td>
Grouping</td></tr>
<tr>
<td>
Ungrouping</td><td>
Ungrouping</td></tr>
<tr>
<td>
SortInAscendingOrder</td><td>
Sort In Ascending Order</td></tr>
<tr>
<td>
SortInDescendingOrder</td><td>
Sort In Descending Order</td></tr>
</table>


## Pager Localization

Paging in Grid can also be localized using the `ej.Pager.Locale` object. Please find the table with list of properties and its value in locale object.

<table>
<tr>
<th>
Locale key words </th><th>
Text</th></tr>
<tr>
<td>
PagerInfo</td><td>
{0} of {1} pages ({2} items)</td></tr>
<tr>
<td>
firstPageTooltip</td><td>
Go to first page</td></tr>
<tr>
<td>
lastPageTooltip</td><td>
Go to last page</td></tr>
<tr>
<td>
nextPageTooltip</td><td>
Go to next page</td></tr>
<tr>
<td>
previousPageTooltip</td><td>
Go to previous page</td></tr>
<tr>
<td>
nextPagerTooltip</td><td>
Go to next Pager</td></tr>
<tr>
<td>
previousPagerTooltip</td><td>
Go to previous Pager</td></tr>
</table>


{% tabs %}

{% highlight html %}


<script src="../Scripts/i18n/ej.culture.de-DE.min.js" type="text/javascript"></script>

<ej:Grid ID="OrdersGrid" runat="server" AllowGrouping="true" AllowPaging="true" Locale="de-DE">

            <GroupSettings EnableDropAreaAutoSizing="false"></GroupSettings>

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="90" />

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="80" />

                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="75" Format="{0:C}" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="90" />

            </Columns>

        </ej:Grid>

{% endhighlight %}

{% highlight c# %}




public partial class Localization : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }



        private void BindDataSource()

        {

            int orderId = 10000;

            int empId = 0;

            for (int i = 1; i < 9; i++)

            {

                order.Add(new Orders(orderId + 1, "VINET", empId + 1, 32.38, new DateTime(2014, 12, 25), "Reims"));

                order.Add(new Orders(orderId + 2, "TOMSP", empId + 2, 11.61, new DateTime(2014, 12, 21), "Munster"));

                order.Add(new Orders(orderId + 3, "ANATER", empId + 3, 45.34, new DateTime(2014, 10, 18), "Berlin"));

                order.Add(new Orders(orderId + 4, "ALFKI", empId + 4, 37.28, new DateTime(2014, 11, 23), "Mexico"));

                order.Add(new Orders(orderId + 5, "FRGYE", empId + 5, 67.00, new DateTime(2014, 05, 05), "Colchester"));

                order.Add(new Orders(orderId + 6, "JGERT", empId + 6, 23.32, new DateTime(2014, 10, 18), "Newyork"));

                orderId += 6;

                empId += 6;

            }

            this.OrdersGrid.DataSource = order;

            this.OrdersGrid.DataBind();

        }



        [Serializable]

        public class Orders

        {

           public Orders()

            {



            }

            public Orders(int orderId, string customerId, int empId, double freight, DateTime orderDate, string shipCity)

            {

                this.OrderID = orderId;

                this.CustomerID = customerId;

                this.EmployeeID = empId;

                this.Freight = freight;

                this.OrderDate = orderDate;

                this.ShipCity = shipCity;

            }

            public int OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public double Freight { get; set; }

            public DateTime OrderDate { get; set; }

            public string ShipCity { get; set; }

        }

    }

{% endhighlight  %}

{% endtabs %}


The Grid and Pager has its own locale labels for applying the information about specific fields in its control. You can set them in the sample side for each culture based translation. The following code example is applied in the sample side.

{% highlight js %}

<script type="text/javascript">

        // Locale labels for ejGrid

 ej.Grid.Locale["de-DE"] = {
    EmptyRecord: "Keine Aufzeichnungen angezeigt",
    GroupDropArea: "Ziehen Sie eine Spaltenüberschrift hier",
    DeleteOperationAlert: "Keine Einträge für Löschvorgang ausgewählt",
    EditOperationAlert: "Keine Einträge für Bearbeiten Betrieb ausgewählt",
    SaveButton: "Speichern",
    CancelButton: "stornieren",
    EditFormTitle: "Korrektur von",
    GroupCaptionFormat: "{{"{{"}}:field{{}}}}: {{"{{"}}:key{{}}}} - {{"{{"}}:count{{}}}} {{"{{"}}if count == 1{{}}}}Beiträge{{"{{"}}else{{}}}}Beiträges{{"{{"}}/if{{}}}}",
    UnGroup: "Klicken Sie hier, um die Gruppierung aufheben"
 };
 ej.Pager.Locale["de-DE"] = {
    pagerInfo: "{0} von {1} Seiten ({2} Beiträge)",
    firstPageTooltip: "Zur ersten Seite",
    lastPageTooltip: "Zur letzten Seite",
    nextPageTooltip: "Zur nächsten Seite",
    previousPageTooltip: "Zurück zur letzten Seite",
    nextPagerTooltip: "Zum nächsten Pager",
    previousPagerTooltip: "Zum vorherigen Pager"
 };

    </script>


{% endhighlight  %}


The output for the above code example is displayed as the following screenshot.

![](Localization_images/Localization_img1.png) 



## Excel-Filter Localization


All text in Excel-Filter can be localized using the `ej.ExcelFilter.Locale` object. Please find the table with list of properties and its value in locale object.

<table>
<tr>
<th>
Locale key words </th><th>
Text</th></tr>
<tr>
<td>
SortNoSmaller</td><td>
Sort Smallest to Largest</td></tr>
<tr>
<td>
SortNoLarger</td><td>
Sort Largest to smallest</td></tr>
<tr>
<td>
SortTextAscending</td><td>
Sort A to Z</td></tr>
<tr>
<td>
SortTextDescending</td><td>
Sort Z to A</td></tr>
<tr>
<td>
SortDateOldest</td><td>
Sort By Oldest</td></tr>
<tr>
<td>
SortDateNewest</td><td>
Sort By Newest</td></tr>
<tr>
<td>
SortByColor</td><td>
Sort By Color</td></tr>
<tr>
<td>
SortByCellColor</td><td>
Sort By Cell Color</td></tr>
<tr>
<td>
SortByFontColor:</td><td>
Sort By Font Color:</td></tr>
<tr>
<td>
FilterByColor</td><td>
Filter By Color</td></tr>
<tr>
<td>
SortColorOptions:</td><td>
[{ id: 1, background:"#FFFFFF"}, {id: 2, background:"#5EABDA"}],</td></tr>
<tr>
<td>
CustomSort</td><td>
Custom Sort</td></tr>
<tr>
<td>
FilterColorOptions</td><td>
{ id: 1, background:"#FFFFFF"}, {id: 2, background:"#5EABDA"}],</td></tr>
<tr>
<td>
FilterByCellColor</td><td>
Filter By Cell Color</td></tr>
<tr>
<td>
FilterByFontColor</td><td>
Filter By Font Color</td></tr>
<tr>
<td>
ClearFilter</td><td>
Clear Filter</td></tr>
<tr>
<td>
NumberFilter</td><td>
Number Filter</td></tr>
<tr>
<td>
TextFilter</td><td>
Text Filter</td></tr>
<tr>
<td>
DateFilter</td><td>
Date Filter</td></tr>
<tr>
<td>
DateTimeFilter</td><td>
Date Time Filters</td></tr>
<tr>
<td>
GuidFilter</td><td>
Guid Filters</td></tr>
<tr>
<td>
StringMenuOptions</td><td>
[{ text:"Equal",value:"equal"},{ text:"Not Equal", value:"notequal"},{ text:"Starts With",value:"startswith"}, { text:"Ends With",value:"endswith"},{ text:"Contains",value:"contains"}, {text:"Custom Filter", value:"customfilter"}],</td></tr>
<tr>
<td>
NumberMenuOptions</td><td>
[{text:"Equal",value:"equal"}, {text:"Not Equal",value:"notequal"}, { text:"Less Than",value:"lessthan"}, {text:"Less Than Or Equal", value:"lessthanorequal"}, {text:"Greater Than",value:"greaterthan"},{ text:"Greater Than Or Equal", value:"greaterthanorequal"}, { text:"Between",value:"between"},{ text:"Custom Filter", value:"customfilter"}]</td></tr>
<tr>
<td>
DateMenuOptions</td><td>
[{ text:"Equal", value:"equal"}, {text:"Not Equal",value:"notequal"},{text:"Less Than",>value:"lessthan"}, {text:"Less Than Or Equal",value:"lessthanorequal"}, {text:"Greater Than",value:"greaterthan"},{text:"Greater Than Or Equal", value:"greaterthanorequal"}, { text:"Between",value:"between"},{ text:"Custom Filter", value:"customfilter"}]</td></tr>
<tr>
<td>
DatetimeMenuOptions</td><td>
[{ text: "Equal", value: "equal" }, { text: "Not Equal", value: "notequal" }, { text: "Less Than", value: "lessthan" }, { text: "Less Than Or Equal", value: "lessthanorequal" }, { text: "Greater Than", value: "greaterthan" }, { text: "Greater Than Or Equal", value: "greaterthanorequal" }, { text: "Between", value: "between" }, { text: "Custom Filter", value: "customfilter" }]</td></tr>
<tr>
<td>
Top10MenuOptions</td><td>
[{ text:"Top", value:"top"},{text:"Bottom", value:"bottom"}]</td></tr>
<tr>
<td>GuidMenuOptions</td>
<td>[{ text: "Equal", value: "equal" }, { text: "Not Equal", value: "notequal" }, { text: "Custom Filter", value: "customfilter" }]</td>
</tr>
<tr>
<td>
title</td><td>
Custom Filter</td></tr>
<tr>
<td>
PredicateOr</td><td>
OR</td></tr>
<tr>
<td>
PredicateAnd</td><td>
AND</td></tr>
<tr>
<td>
OK</td><td>
OK</td></tr>
<tr>
<td>
MathCase</td><td>
Match Case</td></tr>
<tr>
<td>
Cancel</td><td>
Cancel</td></tr>
<tr>
<td>
NoResult</td><td>
No Match Found</td></tr>
<tr>
<td>
CheckBoxStatusMsg</td><td>
Not all items showing</td></tr>
<tr>
<td>
DatePickerWaterMark</td><td>
Select date</td></tr>
<tr>
<td>
DateTimePickerWaterMark</td><td>
Select date time</td></tr>
<tr>
<td>
True</td><td>
True</td></tr>
<tr>
<td>
False</td><td>
False</td></tr>
<tr>
<td>
SelectAll</td><td>
Select All</td></tr>
<tr>
<td>
Blanks</td><td>
Blanks</td></tr>
<tr>
<td>
Showrowswhere</td><td>
Show rows where</td></tr>
<tr>
<td>
NumericTextboxWaterMark</td><td>
Enter value</td></tr>
<tr>
<td>
Search</td><td>
Search</td></tr>
<tr>
<td>
AddToFilter</td><td>
Add current selection to filter</td></tr>
</table>

Please find the code

{% tabs %}

{% highlight html %}

<script src="../Scripts/i18n/ej.culture.de-DE.min.js" type="text/javascript"></script>

<ej:Grid ID="OrdersGrid" runat="server" AllowFiltering="true" AllowPaging="true" Locale="de-DE">


            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="90" />

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="80" />

                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="75" Format="{0:C}" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="90" />

            </Columns>
            <FilterSettings FilterType="Excel"></FilterSettings>
        </ej:Grid>

{% endhighlight %}

{% highlight c# %}


public partial class Localization : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }



        private void BindDataSource()

        {

            int orderId = 10000;

            int empId = 0;

            for (int i = 1; i < 9; i++)

            {

                order.Add(new Orders(orderId + 1, "VINET", empId + 1, 32.38, new DateTime(2014, 12, 25), "Reims"));

                order.Add(new Orders(orderId + 2, "TOMSP", empId + 2, 11.61, new DateTime(2014, 12, 21), "Munster"));

                order.Add(new Orders(orderId + 3, "ANATER", empId + 3, 45.34, new DateTime(2014, 10, 18), "Berlin"));

                order.Add(new Orders(orderId + 4, "ALFKI", empId + 4, 37.28, new DateTime(2014, 11, 23), "Mexico"));

                order.Add(new Orders(orderId + 5, "FRGYE", empId + 5, 67.00, new DateTime(2014, 05, 05), "Colchester"));

                order.Add(new Orders(orderId + 6, "JGERT", empId + 6, 23.32, new DateTime(2014, 10, 18), "Newyork"));

                orderId += 6;

                empId += 6;

            }

            this.OrdersGrid.DataSource = order;

            this.OrdersGrid.DataBind();

        }



        [Serializable]

        public class Orders

        {

           public Orders()

            {



            }

            public Orders(int orderId, string customerId, int empId, double freight, DateTime orderDate, string shipCity)

            {

                this.OrderID = orderId;

                this.CustomerID = customerId;

                this.EmployeeID = empId;

                this.Freight = freight;

                this.OrderDate = orderDate;

                this.ShipCity = shipCity;

            }

            public int OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public double Freight { get; set; }

            public DateTime OrderDate { get; set; }

            public string ShipCity { get; set; }

        }

    }

{% endhighlight  %}

{% highlight js %}

<script type="text/javascript">

ej.ExcelFilter.Locale["de-DE"] = {
      SortNoSmaller: "Art Anzahl kleiner",
      SortNoLarger: "Art Anzahl größer",
      SortTextAscending: "Sortieren aufsteigend Text",
      SortTextDescending: "Sortieren absteigend Text",
      SortDateOldest: "Sortieren Datum Älteste",
      SortDateNewest: "Datum sortieren Neueste",
      ClearFilter: "Filter löschen",
      DateFilter: "Datum Filter"
  }
</script>

{% endhighlight  %}

{% endtabs %}

![](Localization_images/Localization_img2.png)

I> We have uploaded the predefined language packs for some commonly used cultures in [`this`](https://github.com/syncfusion/ej-global/tree/master/l10n) github location. Refer to the github location for getting the predefined language packs for the corresponding culture. The culture file has localized texts for all the Syncfusion controls.

## Globalization

`ej.globalize` library is used to globalize numeric values in Grid control using `Format` property in `Columns`. Globalize values will be automatically used when `Locale` property is set with Locale string value for example `de-DE`.

{% tabs %}

{% highlight html %}

<script src="../Scripts/i18n/ej.culture.de-DE.min.js" type="text/javascript"></script>

<ej:Grid ID="OrdersGrid" runat="server" AllowGrouping="true" AllowPaging="true" Locale="de-DE">

            <GroupSettings EnableDropAreaAutoSizing="false"></GroupSettings>

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="90" />

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="80" />

                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="75" Format="{0:C}" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="90" />

            </Columns>

        </ej:Grid>

{% endhighlight %}

{% highlight c# %}




public partial class Localization : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }



        private void BindDataSource()

        {

            int orderId = 10000;

            int empId = 0;

            for (int i = 1; i < 9; i++)

            {

                order.Add(new Orders(orderId + 1, "VINET", empId + 1, 32.38, new DateTime(2014, 12, 25), "Reims"));

                order.Add(new Orders(orderId + 2, "TOMSP", empId + 2, 11.61, new DateTime(2014, 12, 21), "Munster"));

                order.Add(new Orders(orderId + 3, "ANATER", empId + 3, 45.34, new DateTime(2014, 10, 18), "Berlin"));

                order.Add(new Orders(orderId + 4, "ALFKI", empId + 4, 37.28, new DateTime(2014, 11, 23), "Mexico"));

                order.Add(new Orders(orderId + 5, "FRGYE", empId + 5, 67.00, new DateTime(2014, 05, 05), "Colchester"));

                order.Add(new Orders(orderId + 6, "JGERT", empId + 6, 23.32, new DateTime(2014, 10, 18), "Newyork"));

                orderId += 6;

                empId += 6;

            }

            this.OrdersGrid.DataSource = order;

            this.OrdersGrid.DataBind();

        }



        [Serializable]

        public class Orders

        {

           public Orders()

            {



            }

            public Orders(int orderId, string customerId, int empId, double freight, DateTime orderDate, string shipCity)

            {

                this.OrderID = orderId;

                this.CustomerID = customerId;

                this.EmployeeID = empId;

                this.Freight = freight;

                this.OrderDate = orderDate;

                this.ShipCity = shipCity;

            }

            public int OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public double Freight { get; set; }

            public DateTime OrderDate { get; set; }

            public string ShipCity { get; set; }

        }

    }

{% endhighlight  %}

{% endtabs %}


![](Localization_images/Localization_img3.png)

I> To translate our control content from default English to any of the culture, say For example - German language, then you need to refer the **ej.culture.de-DE.min.js** file in your application, after the reference of ej.web.all.min.js file. For all culture files, please download from the [GitHub](https://github.com/syncfusion/ej-global/tree/master/i18n) location.

## Right to Left - RTL

By default, Grid render its text and layout from left to right. To customize Grid's direction, you can change direction from LTR to RTL by using `EnableRTL` as true.
{% tabs %}

{% highlight html %}

<script src="../Scripts/i18n/ej.culture.de-DE.min.js" type="text/javascript"></script>

<ej:Grid ID="OrdersGrid" runat="server" AllowGrouping="true" AllowPaging="true" EnableRTL="true" Locale="de-DE">

            <GroupSettings EnableDropAreaAutoSizing="false"></GroupSettings>

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="90" />

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="80" />

                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="75" Format="{0:C}" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="90" />

            </Columns>

        </ej:Grid>

{% endhighlight %}
{% highlight c# %}




public partial class Localization : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }



        private void BindDataSource()

        {

            int orderId = 10000;

            int empId = 0;

            for (int i = 1; i < 9; i++)

            {

                order.Add(new Orders(orderId + 1, "VINET", empId + 1, 32.38, new DateTime(2014, 12, 25), "Reims"));

                order.Add(new Orders(orderId + 2, "TOMSP", empId + 2, 11.61, new DateTime(2014, 12, 21), "Munster"));

                order.Add(new Orders(orderId + 3, "ANATER", empId + 3, 45.34, new DateTime(2014, 10, 18), "Berlin"));

                order.Add(new Orders(orderId + 4, "ALFKI", empId + 4, 37.28, new DateTime(2014, 11, 23), "Mexico"));

                order.Add(new Orders(orderId + 5, "FRGYE", empId + 5, 67.00, new DateTime(2014, 05, 05), "Colchester"));

                order.Add(new Orders(orderId + 6, "JGERT", empId + 6, 23.32, new DateTime(2014, 10, 18), "Newyork"));

                orderId += 6;

                empId += 6;

            }

            this.OrdersGrid.DataSource = order;

            this.OrdersGrid.DataBind();

        }



        [Serializable]

        public class Orders

        {

           public Orders()

            {



            }

            public Orders(int orderId, string customerId, int empId, double freight, DateTime orderDate, string shipCity)

            {

                this.OrderID = orderId;

                this.CustomerID = customerId;

                this.EmployeeID = empId;

                this.Freight = freight;

                this.OrderDate = orderDate;

                this.ShipCity = shipCity;

            }

            public int OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public double Freight { get; set; }

            public DateTime OrderDate { get; set; }

            public string ShipCity { get; set; }

        }

    }

{% endhighlight  %}


{% endtabs %}




![](Localization_images/Localization_img4.png)



N> You can get the various minified and unminified formatted culture script files from the local folder “C:\Program Files (x86)\Syncfusion\Essential Studio\xx.x.x.xx\JavaScript\assets\external\i18n”. xx.x.x.xx denotes the current version of Essential Studio, for example 12.4.0.34.

