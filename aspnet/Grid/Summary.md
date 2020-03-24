---
layout: post
title: Summary | Grid | ASP.NET Webforms | Syncfusion
description: summary 
platform: aspnet
control: Grid
documentation: ug
---

# Summary 

Summary is a key feature of Grid that is used to aggregate a particular column. This is useful to analyze the details of a particular column. It has the following types:

* Sum
* Average 
* Count
* Minimum
* Maximum
* Custom

## Default Summary


There are some default summary types available for basic summary formula. The following code example is for Default Summary Types. We can render summary rows for grid using ShowSummary and SummaryRows property of Grid.

{% tabs %}

{% highlight html %}


<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" ShowSummary="true">

<DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"></DataManager>



            <PageSettings PageSize="10"></PageSettings>

            <SummaryRows>

                <ej:SummaryRow Title="Sum">

                    <SummaryColumn>

                       <ej:SummaryColumn SummaryType="Sum" Format="{0:C}" DisplayColumn="Freight" DataMember="Freight" />

                    </SummaryColumn>

                </ej:SummaryRow>

                <ej:SummaryRow Title="Average">

                    <SummaryColumn>

                       <ej:SummaryColumn SummaryType="Average" Format="{0:C}" DisplayColumn="Freight" DataMember="Freight" />

                    </SummaryColumn>

                 </ej:SummaryRow>

           </SummaryRows>

              <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="80" />

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="80" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="90" />

                <ej:Column Field="ShipName" HeaderText="Ship Name" Width="110"/>

                <ej:Column Field="ShipCountry" HeaderText="Ship Country" Width="100" />

                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="80" Format="{0:C}" />

            </Columns>

 </ej:Grid>
{% endhighlight %}
{% highlight c# %}



public partial class DefaultFunctionalities : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }



        private void BindDataSource()

        {

            int code = 10000;

            for (int i = 1; i < 10; i++)

            {

                order.Add(new Orders(code + 1, "ALFKI", i + 0, 2.3 * i, new DateTime(1991, 05, 15), "Berlin"));

                order.Add(new Orders(code + 2, "ANATR", i + 2, 3.3 * i, new DateTime(1990, 04, 04), "Madrid"));

                order.Add(new Orders(code + 3, "ANTON", i + 1, 4.3 * i, new DateTime(1957, 11, 30), "Cholchester"));

                order.Add(new Orders(code + 4, "BLONP", i + 3, 5.3 * i, new DateTime(1930, 10, 22), "Marseille"));

                order.Add(new Orders(code + 5, "BOLID", i + 4, 6.3 * i, new DateTime(1953, 02, 18), "Tsawassen"));

                code += 5;

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

            public Orders(long OrderId, string CustomerId, int EmployeeId, double Freight, DateTime OrderDate, string ShipCity)

            {

                this.OrderID = OrderId;

                this.CustomerID = CustomerId;

                this.EmployeeID = EmployeeId;

                this.Freight = Freight;

                this.OrderDate = OrderDate;

                this.ShipCity = ShipCity;

            }

            public long OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public double Freight { get; set; }

            public DateTime OrderDate { get; set; }

            public string ShipCity { get; set; }

        }

    }

{% endhighlight %}

{% endtabs %}

The following output is displayed as a result of the above code example.

![](Summary_images/Summary_img1.png)



## Custom Summary by String

This property helps you to create custom summary formula for summary. The following code example is for custom summary using Essential ASP.NET. We can achieve custom summary using CustomSummaryValue property.

{% highlight html %}




  <ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" ShowSummary="true">

            <PageSettings PageSize="5"></PageSettings>

            <SummaryRows>

                <ej:SummaryRow Title="Currency">

                    <SummaryColumn>

                        <ej:SummaryColumn SummaryType="Custom" Format="{0:C}" DisplayColumn="Freight" DataMember="Freight" CustomSummaryValue="CustomValue" />

                    </SummaryColumn>

                </ej:SummaryRow>

            </SummaryRows>

              <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="80" />

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="80" />

                <ej:Column Field="Customer ID" HeaderText="Customer ID" TextAlign="Right" Width="80" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="90" />

               <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="80" Format="{0:C}" />

            </Columns>

</ej:Grid>


{% endhighlight  %}


The following output is displayed as a result of the above code example.



![](Summary_images/Summary_img2.png)



## Custom Summary by Function

Custom Summary is used to create custom summary formula for summary. The following code example is for custom summary using Essential ASP.NET.

{% tabs %}

{% highlight html %}




    <div>

        <ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" ShowSummary="true">



             <SummaryRows>

                <ej:SummaryRow Title="Currency" >

                    <SummaryColumn>

                        <ej:SummaryColumn SummaryType="Custom" CustomSummaryValue="currency" DisplayColumn="Freight"

                            Format="{0:C2}" />

                    </SummaryColumn>

                </ej:SummaryRow>

            </SummaryRows>

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="80" />

                 <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="80" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="90" />

                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="80" Format="{0:C}" />
                
            </Columns>

        </ej:Grid>

    </div>



    <script type="text/javascript">

        function currency(args,data) {

             var value = ej.sum(data, "Freight");

             return value;

        }

    </script>




{% endhighlight  %}

{% highlight c# %}




namespace WebSampleBrowser.Grid

{

    public partial class CustomSummary : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }



        private void BindDataSource()

        {

            int code = 10000;

            for (int i = 1; i < 10; i++)

            {

                order.Add(new Orders(code + 1, i + 0, "Berlin", 2.3 * i));

                order.Add(new Orders(code + 2, i + 2, "Madrid", 3.3 * i));

                order.Add(new Orders(code + 3, i + 1, "Cholchester", 4.3 * i));

                order.Add(new Orders(code + 4, i + 3, "Marseille", 5.3 * i));

                order.Add(new Orders(code + 5, i + 4, "London", 6.3 * i));

                code += 5;

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

            public Orders(long OrderId, int EmployeeId, string ShipCity, double Freight)

            {

                this.OrderID = OrderId;

                this.EmployeeID = EmployeeId;

                this.ShipCity = ShipCity;

                this.Freight = Freight;
                
            }

            public long OrderID { get; set; }

            public int EmployeeID { get; set; }

            public string ShipCity { get; set; }

            public double Freight { get; set; }
            
        }

    }

}}

{% endhighlight  %}

{% endtabs %}

![](Summary_images/Summary_img3.PNG)


## Title for summary

Title name of any summary value can be change using the `Title` property of `SummaryColumns`. Title displaying column can be set using the `TitleColumn`.

{% tabs %}

{% highlight html %}

   <div>

      <ej:Grid ID="OrdersGrid" runat="server" AllowPaging="true" ShowSummary="true">

           <SummaryRows>

                <ej:SummaryRow Title="Summation" TitleColumn="EmployeeID">

                    <SummaryColumn>

                       <ej:SummaryColumn SummaryType="Sum" Format="{0:C}" DisplayColumn="Freight" DataMember="Freight" />

                    </SummaryColumn>

                </ej:SummaryRow>

           </SummaryRows>

              <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="80" />

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="80" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="90" />

                <ej:Column Field="ShipCountry" HeaderText="Ship Country" Width="100" />

                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="80" Format="{0:C}" />

              </Columns>

      </ej:Grid>

    </div>


{% endhighlight  %}

{% highlight c# %}

namespace WebSampleBrowser.Grid

{

    public partial class CustomSummary : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }

        private void BindDataSource()

        {
            int orderId = 10247;
           
            int empId = 0;
            for (int i = 1; i < 9; i++)
            {
                order.Add(new Orders(orderId + 1, "VINET", empId + 1, 32.38, new DateTime(2014, 12, 25), "Reims", "France"));
                order.Add(new Orders(orderId + 2, "TOMSP", empId + 2, 11.61, new DateTime(2014, 12, 21), "Munster", "Germany"));
                order.Add(new Orders(orderId + 3, "ANATER", empId + 3, 45.34, new DateTime(2014, 10, 18), "Berlin", "Brazil"));
                order.Add(new Orders(orderId + 4, "ALFKI", empId + 4, 37.28, new DateTime(2014, 11, 23), "Mexico","France" ));
                order.Add(new Orders(orderId + 5, "FRGYE", empId + 5, 67.00, new DateTime(2014, 05, 05), "Colchester","Belgium"));
                order.Add(new Orders(orderId + 5, "FRGYE", empId + 5, 67.00, new DateTime(2014, 05, 05), "Colchester", "Brazil"));
                orderId += 5;
                empId += 5;
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
            public Orders(int orderId, string customerId, int empId, double freight, DateTime orderDate, string shipCity, string shipCountry)
            {
                this.OrderID = orderId;
                this.CustomerID = customerId;
                this.EmployeeID = empId;
                this.Freight = freight;
                this.OrderDate = orderDate;
                this.ShipCity = shipCity;
                this.ShipCountry = shipCountry;
            }
            public int? OrderID { get; set; }
            public string CustomerID { get; set; }
            public int? EmployeeID { get; set; }
            public double? Freight { get; set; }
            public DateTime? OrderDate { get; set; }
            public string ShipCity { get; set; }
            public string ShipCountry { get; set; }
        }
    }

}}

{% endhighlight  %}

{% endtabs %}

![](Summary_images/Summary_img8.PNG)


## Group Summary

This property helps you to enable the group summary column in Grid. The following code example is for Group summary.

{% tabs %}


{% highlight html %}




<ej:Grid ID="OrdersGrid" runat="server" AllowGrouping="true" ShowSummary="true">

            <PageSettings PageSize="10"></PageSettings>

 <GroupSettings GroupedColumns="CustomerID"></GroupSettings>

            <SummaryRows>

                <ej:SummaryRow ShowTotalSummary="false">

                    <SummaryColumn>

                       <ej:SummaryColumn SummaryType="Average" Format="{0:C}" DisplayColumn="Freight" DataMember="Freight" Prefix="Average = " />

                    </SummaryColumn>

                 </ej:SummaryRow>

            </SummaryRows>

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="80" />

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="90" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="90" />

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="80" />

                <ej:Column Field="Freight" HeaderText="Freight" Width="80" TextAlign="Right"  Format="{0:C}" />

            </Columns>

</ej:Grid>

{% endhighlight  %}
{% highlight c# %}


public partial class DefaultFunctionalities : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }



        private void BindDataSource()

        {

            int code = 10000;

            for (int i = 1; i < 10; i++)

            {

                order.Add(new Orders(code + 1, "ALFKI", i + 0, 2.3 * i, new DateTime(1991, 05, 15), "Berlin"));

                order.Add(new Orders(code + 2, "ANATR", i + 2, 3.3 * i, new DateTime(1990, 04, 04), "Madrid"));

                order.Add(new Orders(code + 3, "ANTON", i + 1, 4.3 * i, new DateTime(1957, 11, 30), "Cholchester"));

                order.Add(new Orders(code + 4, "BLONP", i + 3, 5.3 * i, new DateTime(1930, 10, 22), "Marseille"));

                order.Add(new Orders(code + 5, "BOLID", i + 4, 6.3 * i, new DateTime(1953, 02, 18), "Tsawassen"));

                code += 5;

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

            public Orders(long OrderId, string CustomerId, int EmployeeId, double Freight, DateTime OrderDate, string ShipCity)

            {

                this.OrderID = OrderId;

                this.CustomerID = CustomerId;

                this.EmployeeID = EmployeeId;

                this.Freight = Freight;

                this.OrderDate = OrderDate;

                this.ShipCity = ShipCity;

            }

            public long OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public double Freight { get; set; }

            public DateTime OrderDate { get; set; }

            public string ShipCity { get; set; }

        }

    }

{% endhighlight %}

{% endtabs %}

The following output is displayed as a result of the above code example.



![](Summary_images/Summary_img4.png)



## Caption Summary

This property is used to create Caption Summary column in Grid. The following code example is for Caption Summary.

ShowCaptionSummary property used to achieve caption summary feature.

{% tabs %}

{% highlight html %}



<ej:Grid ID="OrdersGrid" runat="server" AllowGrouping="true" ShowSummary="true">



    <PageSettings PageSize="10"></PageSettings>

    <SummaryRows>

  <ej:SummaryRow ShowCaptionSummary="true" ShowTotalSummary="false">

          <SummaryColumn>

  <ej:SummaryColumn SummaryType="Average" DisplayColumn="Freight" DataMember="Freight" Format="{0:C}" Prefix="Average = " />

          </SummaryColumn>

       </ej:SummaryRow>

    </SummaryRows>

    <GroupSettings GroupedColumns="CustomerID"></GroupSettings>

    <Columns>

     <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true"   TextAlign="Right" Width="80" />

         <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="80" />

         <ej:Column Field="ShipCity" HeaderText="Ship City" Width="90" />

        <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="75" />

    <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="120" Format="{0:C}" />

    </Columns>

</ej:Grid>


{% endhighlight  %}
{% highlight c# %}


public partial class DefaultFunctionalities : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }



        private void BindDataSource()

        {

            int code = 10000;

            for (int i = 1; i < 10; i++)

            {

                order.Add(new Orders(code + 1, "ALFKI", i + 0, 2.3 * i, new DateTime(1991, 05, 15), "Berlin"));

                order.Add(new Orders(code + 2, "ANATR", i + 2, 3.3 * i, new DateTime(1990, 04, 04), "Madrid"));

                order.Add(new Orders(code + 3, "ANTON", i + 1, 4.3 * i, new DateTime(1957, 11, 30), "Cholchester"));

                order.Add(new Orders(code + 4, "BLONP", i + 3, 5.3 * i, new DateTime(1930, 10, 22), "Marseille"));

                order.Add(new Orders(code + 5, "BOLID", i + 4, 6.3 * i, new DateTime(1953, 02, 18), "Tsawassen"));

                code += 5;

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

            public Orders(long OrderId, string CustomerId, int EmployeeId, double Freight, DateTime OrderDate, string ShipCity)

            {

                this.OrderID = OrderId;

                this.CustomerID = CustomerId;

                this.EmployeeID = EmployeeId;

                this.Freight = Freight;

                this.OrderDate = OrderDate;

                this.ShipCity = ShipCity;

            }

            public long OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public double Freight { get; set; }

            public DateTime OrderDate { get; set; }

            public string ShipCity { get; set; }

        }

    }

{% endhighlight  %}

{% endtabs %}

The following output is displayed as a result of the above code example.



![](Summary_images/Summary_img5.png)

## Summary Template

Using `Template` property of `SummaryColumns` you can render any type of JsRender templates or customizing the summary value.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" ShowSummary="true">
    
    <SummaryRows>

        <ej:SummaryRow Title="Average">

          <SummaryColumn>

                <ej:SummaryColumn SummaryType="Average" DisplayColumn="Freight" DataMember="Freight" Format="{0:C}" Template = "#templateData" />

          </SummaryColumn>

       </ej:SummaryRow>

    </SummaryRows>

    <Columns>

         <ej:Column Field="OrderID" />

         <ej:Column Field="EmployeeID" />

         <ej:Column Field="Freight" Format="{0:C}" />

    </Columns>

</ej:Grid>


{% endhighlight  %}
{% highlight c# %}


public partial class DefaultFunctionalities : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            var DataSource = new NorthwindDataContext().OrdersViews.Take(5).ToList();
            
            this.OrdersGrid.DataSource = DataSource;
            
            this.OrdersGrid.DataBind();

        }

    }

{% endhighlight  %}

{% highlight js %}

<script id="templateData" type="text/x-jsrender">
     Freight has Average of {{"{{"}}:summaryValue{{"}}"}} in  dollars
</script>

{% endhighlight %}

{% endtabs %}


The following output is displayed as a result of the above code example.

![](Summary_images/summaryGrid_img7.PNG)

## Handling Aggregation in server side

The Aggregation at server side is handled by using aggregate key. While using remote data, Summary Row must be handled by returning summary column datasource into the aggregate property of result object.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}



<ej:DataManager runat="server" ID="FlatData" URL="/Default.aspx/Data" Adaptor="WebMethodAdaptor" />
    
<ej:Grid ID="OrdersGrid" runat="server" DataManagerID="FlatData" ShowSummary="true" AllowPaging="true">

    <PageSettings PageSize="10"></PageSettings>

    <SummaryRows>

        <ej:SummaryRow ShowTotalSummary="true" Title="Avg">

            <SummaryColumn>

                <ej:SummaryColumn SummaryType="Average" Format="{0:C}" DisplayColumn="Freight" DataMember="Freight" Prefix="Average = " />

            </SummaryColumn>

            </ej:SummaryRow>

    </SummaryRows>

    <Columns>

        <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="80" />

        <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="90" />

        <ej:Column Field="ShipCity" HeaderText="Ship City" Width="90" />

        <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="80" />

        <ej:Column Field="Freight" HeaderText="Freight" Width="80" TextAlign="Right"  Format="{0:C}" />

    </Columns>
    
</ej:Grid>


{% endhighlight  %}
{% highlight c# %}


public partial class _Default : Page
{

    protected void Page_Load(object sender, EventArgs e)
    {
        
    }

    [WebMethod]
    [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
    public static object Data(Syncfusion.JavaScript.DataManager value)
    {
        IEnumerable DataSource = OrderRepository.GetAllRecords();
        DataResult result = new DataResult();
        DataOperations operation = new DataOperations();
        List<string> str = new List<string>();
        if (value.Aggregates != null)
        {
            for (var i = 0; i < value.Aggregates.Count; i++)
                str.Add(value.Aggregates[i].Field);
            result.aggregate = operation.PerformSelect(DataSource, str);
        }
        DataSource = operation.PerformSkip(DataSource, value.Skip);
        result.result = operation.PerformTake(DataSource, value.Take);
        result.count = DataSource.AsQueryable().Count();
        return result;
    }

    public class DataResult
    {
        public IEnumerable result { get; set; }
        public int count { get; set; }
        public IEnumerable aggregate { get; set; }
        public IEnumerable groupDs { get; set; }
    }

}

{% endhighlight  %}

{% endtabs %}

The following output is displayed as a result of the above code example.



![](Summary_images/Summary_img6.png)



