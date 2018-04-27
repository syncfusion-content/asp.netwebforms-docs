---
layout: post
title: Data adaptor in DropDownList control for Syncfusion ASP.NET WebForm
description: Describes about the data adaptor in DropDownList control for Syncfusion ASP.NET WebForm
platform: aspnet
control: DropDownList
documentation: ug
keywords: DropDownList, dropdown, data binding, REStFul Binding, WebAPI, Web Method, OData, OData4
---
# Data Adaptors

The Data adaptor is a mechanism through which the DataManager interact with the remote service or local dataSource. The DataManager has several preconfigured Data Adaptors, refer to the [link](http://help.syncfusion.com/aspnetmvc/datamanager/data-adaptors).

## OData

OData is a standardized protocol for creating and consuming data. You can provide the [OData service](http://www.odata.org/) URL directly to the Datasource URL property.

{% highlight html %}
    
    <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="ShipName" DataValueField="ShipCountry"></ej:DropDownList>
    
{% endhighlight %}

{% highlight c# %}
    
    protected void Page_Load(object sender, EventArgs e)
    {
        DropDownList1.DataSource = "http://mvc.syncfusion.com/Services/Northwnd.svc/Orders";
    }

{% endhighlight %}

## OData4

ODataV4Adaptor is used for consuming data from OData V4 Service. To consume OData service, set the service link to the Url property and set adaptor type as ODataAdaptor to the Adaptor Property of DataManager and then you can assign it to DropDownList “dataSource”.

{% highlight c# %}

    <ej:DropDownList ID="myList"  DataTextField="RegionDescription" DataValueField="RegionID" runat="server"></ej:DropDownList>
    
{% endhighlight %}

{% highlight javascript %}

    <script type="text/javascript">
        var dataManager = ej.DataManager({
            url: "http://services.odata.org/V4/Northwind/Northwind.svc/Regions/",
            adaptor: new ej.ODataV4Adaptor()
        });
        var query = ej.Query();
        $('#myList').ejDropDownList({
            dataSource: dataManager,
        query : query
        });
    <script>
    
{% endhighlight %}
    
## Web API

WebAPI Adaptor that is extended from ODataAdaptor, is used for consuming data from WebApi Service.

To consume Web API service, set the service link to the Url property and set the adaptor type as ` WebApiAdaptor to the Adaptor Property of DataManager`.
    
{% highlight c# %}

    <ej:DropDownList ID="customer" ClientIDMode="Static" DataTextField="CustomerID" DataValueField="EmployeeID" runat="server" WatermarkText="Select a Customer" Width="100%">
               
    </ej:DropDownList>
    
{% endhighlight %}

{% highlight javascript %}

    <script type="text/javascript">
        var data = ej.DataManager({
            url: "http://mvc.syncfusion.com/UGService/api/Orders",
            adaptor: new ej.WebApiAdaptor()
        });
        var query = ej.Query();
        $("#customer").ejDropDownList({
            dataSource: data,
            query: query
        });
    <script>
    
{% endhighlight %}

## WebMethod Adaptor

The WebMethod Adaptor is used to bind data source from remote services and code behind methods. 

By using “WebMethodAdaptor” we can bind data from WebService to the DropDownList control and also we need to include “ScriptService” Attribute to WebService in order to enable request from client-side.

{% highlight html %}

    [System.Web.Script.Services.ScriptService]
    public class WebService1 : System.Web.Services.WebService
    {

        [WebMethod]
        public object Get()
        {

            List<Employee> Data = new List<Employee>();
            Data.Add(new Employee
            {
                Name = "Erik Linden",
                Role = "Executive"
                
            });
            Data.Add(new Employee
            {
                Name = "John Linden",
                Role = "Representative"
                
            });
            Data.Add(new Employee
            {
                Name = "Louis",
                Role = "Representative"
               
            });
            Data.Add(new Employee
            {
                Name = "Lawrence",
                Role = "Executive"
               
            });
            dynamic count = Data.Count;
            return new
            {
                result = Data,
                count = count
            };

        }
        public class Employee
        {
            public string Name { get; set; }
            public string Role { get; set; }
         
        }

    }
    
{% endhighlight %}

Initialize the DropDownList as follows

{% highlight html %}

    <ej:DropDownList ID="myList" Width="116px" Query="ej.Query().requiresCount()" DataTextField="Name" DataValueField="Country" runat="server">
    </ej:DropDownList>

{% endhighlight %}

You can use the following code example to use WebMethod adaptor and bind the data to the DropDownList.

![](Databinding_images/Data-binding_img1.png)

{% highlight html %}

    <script type="text/javascript">
        var data = ej.DataManager({
            url: "WebService1.asmx/Get",
            adaptor: new ej.WebMethodAdaptor()
        });
        $("#myList").ejDropDownList({
            dataSource: data
        });
    </script>

{% endhighlight %}