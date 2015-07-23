---
layout: post
title: Localization
description: localization
platform: aspnet
control: Grid
documentation: ug
---

# Localization

The Localization concept in Grid supports switching the control language with various cultures. The Locale property in Grid is a string type used to define the culture code that has been declared by JQuery globalize script file. The default value for Locale in Grid is en-US.

The following two script files are necessary to perform Localization in Grid.

1. jquery.globalize.min.js
2. globalize.culture.en-US.min.js (Changeable)

The globalize.culture.en-US.min.js scripts are changeable based on the culture name. Each culture has its own culture script file that differs by its culture code. For example en-US is the culture codefor English - United States.

The following code example demonstrates how to switch the culture of Grid as de-DE (German - Germany).


{% highlight html %}




<script src='<%= Page.ResolveClientUrl("~/Scripts/jquery.globalize.min.js")%>'></script>

<script src='<%= Page.ResolveClientUrl("~/Scripts/globalize.culture.de-DE.min.js")%>'></script>



   



<ej:Grid ID="OrdersGrid" runat="server" AllowGrouping="True" AllowPaging="True" Locale="de-DE">

            <GroupSettings EnableDropAreaAutoSizing="False"></GroupSettings>

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />

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

The Grid and Pager has its own locale labels for applying the information about specific fields in its control. You can set them in the sample side for each culture based translation. The following code example is applied in the sample side for all the above platforms.
{% highlight js %}
<script type="text/javascript">

        // Locale labels for ejGrid

ej.Grid.locale["de-DE"] = {

            EmptyRecord: "Keine Aufzeichnungen angezeigt",

            GroupDropArea: "Ziehen Sie eine Spaltenüberschrift hier",

            DeleteOperationAlert: "Keine Einträge für Löschvorgang ausgewählt",

            EditOperationAlert: "Keine Einträge für Bearbeiten Betrieb ausgewählt",

            SaveButton: "Speichern",

            CancelButton: "stornieren",

            EditFormTitle: "Korrektur von",

            GroupCaptionFormat: "{{:field}}: {{:key}} - {{:count}} {{if count == 1}} Beiträge {{else}} Beiträges {{/if}}",

        };

       // Locale labels for ejGrid pager

ej.Pager.locale["de-DE"] = {

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





The default values of locale labels in Grid and ejPager are listed out in the following code example. You can change the label values based on the cultures with its corresponding meaning of words.

{% highlight c# %}

ej.Grid.locale["en-US"] = {

            EmptyRecord: "No records to display",

            //Editing option localization strings

            DeleteOperationAlert: "No records selected for delete operation",

            EditOperationAlert: "No records selected for edit operation",

            SaveButton: "Save",

            OkButton: "OK",

            CancelButton: "Cancel",

            EditFormTitle: "Details of ",

            AddFormTitle: "Add New Record",

            //Key Combination alert message

            Notactionkeyalert: "This Key-Combination is not avaiable",

            Keyconfigalerttext: "This Key-Combination has already been assigned to ",

            //Group drop area and caption format

            GroupDropArea: "Drag a column header here to group its column",

           GroupCaptionFormat: "{{:field}}: {{:key}} - {{:count}} {{if count == 1 }} item {{else}} items {{/if}}",

            //Bulk Editing Alert Messages

            BatchSaveConifrm: "Are you sure you want to save changes?",

            BatchSaveLostChanges: "Unsaved changes will be lost. Are you sure you want to continue?",

            //Pager bar message string

            PagerInfo: "{0} of {1} pages ({2} items)",

            //Frozen Alert Messages

            FrozenColumnsViewAlert: "Frozen columns should be in grid view area",

            FrozenColumnsScrollAlert: "Enable allowScrolling while using frozen Columns",

            FrozenNotSupportedException: "Frozen Columns and Rows are not supported for Grouping, Row Template, Detail Template and Batch Editing",

            //Toolbar tooltip

            Add: "Add",

            Edit: "Edit",

            Delete: "Delete",

            Update: "Update",

            Cancel: "Cancel",

            //Filter menu strings

            StringMenuOptions: [{ text: "StartsWith", value: "StartsWith" }, { text: "EndsWith", value: "EndsWith" }, { text: "Contains", value: "Contains"}, { text: "Equal", value: "Equal" }, { text: "NotEqual", value: "NotEqual" }],

            NumberMenuOptions: [{ text: "LessThan", value: "LessThan" }, { text: "GreaterThan", value: "GreaterThan" }, { text: "LessThanOrEqual", value: "LessThanOrEqual" }, { text: "GreaterThanOrEqual", value: "GreaterThanOrEqual" }, { text: "Equal", value: "Equal" }, { text: "NotEqual", value: "NotEqual" }],

            PredicateAnd: "AND",

            PredicateOr: "OR",

            Filter: "Filter",

            MatchCase: "Match Case",

            Clear: "Clear"



            PrintGrid: "Print",

            ExcelExport: "Excel Export",

            WordExport: "Word Export",

            PdfExport: "PDF Export", 

            ResponsiveFilter: "Filter",

            ResponsiveSorting: "Sort"

        };

ej.Pager.locale["en-US"] = {



        pagerInfo: "{0} of {1} pages ({2} items)",



        firstPageTooltip: "Go to first page",



        lastPageTooltip: "Go to last page",



        nextPageTooltip: "Go to next page",



        previousPageTooltip: "Go to previous page",



        nextPagerTooltip: "Go to next Pager",



        previousPagerTooltip: "Go to previous Pager"

    };



{% endhighlight %}

> _Note: You can get the various minified and unminified formatted culture script files from the local folder “C:\Program Files (x86)\Syncfusion\Essential Studio\xx.x.x.xx\JavaScript\assets\external\cultures”. xx.x.x.xx denotes the current version of Essential Studio, for example 12.4.0.34._

