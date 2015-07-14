---
layout: post
title: Filtering
description: filtering
platform: aspnet
control: Grid
documentation: ug
---

## Filtering

Filtering is used to filter particular or related records in Grid to review details of records. To enable filtering behavior in Grid you can add AllowFiltering property at Grid initialize. There are three types of filtering features in grid. They are

* Filter menu
* Filter Bar
* Excel styled menu
### Filter Menu 


After you enable Filter Menu in Grid, it shows filter menu to filter records. This menu contains filtering options based on column type.

Filter menu types

* String menu filtering 
* Numeric menu filtering
* Date menu filtering
* Boolean menu filtering

Filter menus are a good UI based filtering option. It visibly denotes filtering option and is flexible to filter records. In String menu filtering, ejAutoComplete is used as default control to filter; in Numeric menu filtering, ejNumericTextbox is used as default control to filter. In Date menu filtering, ejDatePicker control is used as default control to filter and in Boolean menu filtering, ejCheckBox is used for filtering. 



[ASP]



[aspx]



&lt;ej:Grid ID="FlatGrid" runat="server" AllowFiltering="true" AllowPaging="True" &gt;

&lt;DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"&gt;&lt;/DataManager&gt;

            &lt;FilterSettings FilterType="Menu" /&gt;         

&lt;/ej:Grid&gt; 







The following output is displayed as a result of the above code example.



{ ![](Filtering_images/Filtering_img1.png) | markdownify }
{:.image }


### Filter Bar

Filter bar is one of the types of filtering. It is otherwise called text filtering as filter bar working is based on text boxes. Through this you can filter records. Filter bars have expression to filter records. They are based on type of column. 

_Table_ _2__: List of Filter Bar Expressions_

<table>
<tr>
<td rowspan = "4">
Numeric column</td><td>
> value</td><td rowspan = "4">
To filter numeric column. You can use these expressions.</td></tr>
<tr>
<td>
< value</td></tr>
<tr>
<td>
= value</td></tr>
<tr>
<td>
!= value</td></tr>
<tr>
<td>
String</td><td>
startsWith</td><td>
By default, string filtering works starts with operator</td></tr>
<tr>
<td>
Date</td><td>
Equal</td><td>
By default, date filter bar matches records with same date value</td></tr>
<tr>
<td>
Boolean</td><td>
Equal</td><td>
Boolean filter bar works with either true or false.</td></tr>
</table>


[ASP]



[aspx]



  &lt;ej:Grid ID="FlatGrid" runat="server" AllowFiltering="true" AllowPaging="True" &gt;

&lt;DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"&gt;&lt;/DataManager&gt;



            &lt;FilterSettings FilterType="FilterBar" /&gt;

  &lt;/ej:Grid&gt;    







The following output is displayed as a result of the above code example.



{ ![](Filtering_images/Filtering_img2.png) | markdownify }
{:.image }


### Excel styled menu

You can enable the Excel like filter menu by setting the FilterType as “excel” of the FilterSettings property. The filter menu is displayed after clicking the filter icon in the column headers. 

The filter menu contains options such as Sorting, Clear filter, submenu for the advanced filter options, 

#### Checkbox list

The Checkbox list is available in the menu that contains the possible filter value for the column. It shows the list of possible filter values with the checkbox. The filter value can be selected by clicking the checkbox corresponding to that value. By clicking the Ok button, the column is filtered based on the values checked in the checkbox list. The SelectAll checkbox is also present in the checkbox list that allows either select or deselect all the checkboxes.

{ ![](Filtering_images/Filtering_img3.png) | markdownify }
{:.image }


A Search box is available at the top of the check box list that is used to search the possible filter choices. The number of possible filter choices are restricted by the setting the MaxFilterChoices property of the FilterSettings. 

#### Advanced Filter

The Submenu items in the filter menu provide the advanced filtering options for end users. When selecting a sub menu item, a separate dialog box opens and displays an advanced filter drop-down that lists the available filter operators for the respective filtering column. The filtering is performed by clicking the Ok button.

{ ![](Filtering_images/Filtering_img4.png) | markdownify }
{:.image }


{ ![](Filtering_images/Filtering_img5.png) | markdownify }
{:.image }






[ASPX]

&lt;ej:Grid ID="OrdersGrid" runat="server" AllowFiltering="True" AllowPaging="True" AllowSorting="true"&gt;

            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="90" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="100" /&gt;

                &lt;ej:Column Field="OrderDate" HeaderText="Order Date" Format="{0:MM/dd/yyyy}" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="110" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="90" Format="{0:C}" /&gt;              

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="100" /&gt;

                &lt;ej:Column Field="Verified" HeaderText="Verified" Width="100" /&gt;

            &lt;/Columns&gt;

            &lt;FilterSettings FilterType="Excel" MaxFilterChoices="100" EnableCaseSensitivity="false"&gt;&lt;/FilterSettings&gt;

&lt;/ej:Grid&gt;





[Code Behind]



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

                order.Add(new Orders(orderId + 1, "VINET", empId + 1, 32.38, "Reims", true));

                order.Add(new Orders(orderId + 2, "TOMSP", empId + 2, 11.61, "Munster", false));

                order.Add(new Orders(orderId + 3, "ANATER", empId + 3, 45.34, "Berlin", true));

                order.Add(new Orders(orderId + 4, "ALFKI", empId + 4, 37.28, "Mexico", false));

                order.Add(new Orders(orderId + 5, "FRGYE", empId + 5, 67.00, "Colchester", true));

                order.Add(new Orders(orderId + 6, "JGERT", empId + 6, 23.32, "Newyork", true));

                orderId += 6;

                empId += 6;

            }

            this.OrdersGrid.DataSource = order;

            this.OrdersGrid.DataBind();

        }



### Filter operators

Grid uses filter operators from DataManager, that are used at the time of filtering. Filter operators are used to denote filtering type.

_Table_ _3__: List of Column type and Filter operators_

<table>
<tr>
<td>
Column type</td><td>
Filter operators</td></tr>
<tr>
<td>
Number</td><td>
ej.FilterOperators.greaterThanej.FilterOperators.greaterThanOrEqualej.FilterOperators.lessThanej.FilterOperators.lessThanOrEqualej.FilterOperators.equal</td></tr>
<tr>
<td>
String</td><td>
ej.FilterOperators.startsWithej.FilterOperators.endsWithej.FilterOperators.containsej.FilterOperators.equalej.FilterOperators.notEqual</td></tr>
<tr>
<td>
Boolean</td><td>
ej.FilterOperators.equalej.FilterOperators.notEqual</td></tr>
<tr>
<td>
Date</td><td>
ej.FilterOperators.greaterThanej.FilterOperators.greaterThanOrEqualej.FilterOperators.lessThanej.FilterOperators.lessThanOrEqualej.FilterOperators.equal</td></tr>
</table>
### External Filtering

Grid contains an API to do filtering dynamically after Grid initialize, without the use of User Interaction. It is useful to do filtering dynamically.



[ASP]



[aspx]

    &lt;div&gt;

        &lt;div class="row"&gt;

            &lt;div class="col-md-1"&gt;

                Columns

            &lt;/div&gt;

            &lt;div class="col-md-1"&gt;

                &lt;ej:DropDownList ID="columns" runat="server"&gt;

                    &lt;Items&gt;

                        &lt;ej:DropDownListItem Value="OrderID" Text="Order ID"&gt;&lt;/ej:DropDownListItem&gt;

                        &lt;ej:DropDownListItem Value="CustomerID" Text="Customer ID"&gt;&lt;/ej:DropDownListItem&gt;

                        &lt;ej:DropDownListItem Value="EmployeeID" Text="Employee ID"&gt;&lt;/ej:DropDownListItem&gt;

                        &lt;ej:DropDownListItem Value="ShipCity" Text="Ship City"&gt;&lt;/ej:DropDownListItem&gt;

                        &lt;ej:DropDownListItem Value="Verified" Text="Verified"&gt;&lt;/ej:DropDownListItem&gt;

                    &lt;/Items&gt;

                &lt;/ej:DropDownList&gt;

            &lt;/div&gt;

        &lt;/div&gt;

        &lt;br /&gt;

        &lt;div class="row"&gt;

            &lt;div class="col-md-1"&gt;

                Operator

            &lt;/div&gt;

            &lt;div class="col-md-1"&gt;

                &lt;ej:DropDownList ID="operator" runat="server"&gt;

                    &lt;Items&gt;

                        &lt;ej:DropDownListItem Value="contains" Text="Contains"&gt;&lt;/ej:DropDownListItem&gt;

                        &lt;ej:DropDownListItem Value="endswith" Text="Endswith"&gt;&lt;/ej:DropDownListItem&gt;

                        &lt;ej:DropDownListItem Value="equal" Text="Equal"&gt;&lt;/ej:DropDownListItem&gt;

                        &lt;ej:DropDownListItem Value="greaterthan" Text="Greaterthan"&gt;&lt;/ej:DropDownListItem&gt;

                        &lt;ej:DropDownListItem Value="greaterthanorequal" Text="GreaterThanOrEqual"&gt;&lt;/ej:DropDownListItem&gt;

                        &lt;ej:DropDownListItem Value="lessthan" Text="LessThan"&gt;&lt;/ej:DropDownListItem&gt;

                        &lt;ej:DropDownListItem Value="lessthanorequal" Text="LessThanOrEqual"&gt;&lt;/ej:DropDownListItem&gt;

                        &lt;ej:DropDownListItem Value="notequal" Text="NotEqual"&gt;&lt;/ej:DropDownListItem&gt;

                        &lt;ej:DropDownListItem Value="startswith" Text="StartsWith"&gt;&lt;/ej:DropDownListItem&gt;

                    &lt;/Items&gt;

                &lt;/ej:DropDownList&gt;

            &lt;/div&gt;

        &lt;/div&gt;

        &lt;br /&gt;

        &lt;div class="row"&gt;

            &lt;div class="col-md-1"&gt;

                Value

            &lt;/div&gt;

            &lt;div class="col-md-1"&gt;

                &lt;input type="text" class="e-ejinputtext" id="value" style="width: 143px; height: 26px" /&gt;

            &lt;/div&gt;

        &lt;/div&gt;

        &lt;br /&gt;

        &lt;div class="row"&gt;

            &lt;div class="col-md-2"&gt;

                &lt;ej:Button Type="button" runat="server" ID="filter" ClientSideOnClick="button_click" Text="filter" /&gt;

            &lt;/div&gt;

        &lt;/div&gt;

        &lt;ej:Grid ID="FlatGrid" runat="server" AllowFiltering="true" AllowPaging="True"&gt;

&lt;DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"&gt;&lt;/DataManager&gt;



            &lt;FilterSettings FilterType="Menu" /&gt;

        &lt;/ej:Grid&gt;

    &lt;/div&gt;





[javascript]

  &lt;script&gt;

        function button_click(args) {

            $("#FlatGrid").ejGrid("filterColumn", $("#columns").ejDropDownList("getSelectedValue"), $("#operator").ejDropDownList("getSelectedValue"), $("#value").val(), "and");

        }



    &lt;/script&gt;







The following output is displayed as a result of the above code example.



{ ![](Filtering_images/Filtering_img6.png) | markdownify }
{:.image }


