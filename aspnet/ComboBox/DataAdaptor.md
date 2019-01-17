---
layout: post
title: Data adaptor in ComboBox control for Syncfusion ASP.NET WebForm
description: Describes about the data adaptor in ComboBox control for Syncfusion ASP.NET WebForm
platform: aspnet
control: ComboBox
documentation: ug
keywords: ComboBox, ComboBox, data binding, REStFul Binding, WebAPI, Web Method, OData, OData4
---
# Data Adaptors

The Data adaptor is a mechanism through which the DataManager interact with the remote service or local dataSource. The DataManager has several preconfigured Data Adaptors, refer to the [link](http://help.syncfusion.com/aspnetmvc/datamanager/data-adaptors).

## OData

OData is a standardized protocol for creating and consuming data. You can provide the [OData service](http://www.odata.org/) URL directly to the Datasource URL property.

{% tabs %}

{% highlight html %}
    
<ej:ComboBox ID="countryList" AutoFill="true" runat="server" Width="100%" DataTextField="ShipName" DataValueField="ShipCountry" Placeholder="Search a Ship">
    <DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders" Adaptor="ODataAdaptor" CrossDomain="true"></DataManager>
</ej:ComboBox>

{% endhighlight %}

{% endtabs %}

![](DataAdaptor_images/DataAdaptor_image1.png)

## OData4

ODataV4Adaptor is used for consuming data from OData V4 Service. To consume OData service, set the service link to the Url property and set adaptor type as ODataV4Adaptor to the Adaptor Property of DataManager.

{% tabs %}

{% highlight html %}
    
<ej:ComboBox ID="regionList" AutoFill="true" runat="server" Width="100%" DataTextField="RegionDescription" DataValueField="RegionID" Placeholder="Search a Ship">
    <DataManager URL="http://services.odata.org/V4/Northwind/Northwind.svc/Regions/" Adaptor="ODataV4Adaptor"  CrossDomain="true"></DataManager>
</ej:ComboBox>

{% endhighlight %}

{% endtabs %}
    
![](DataAdaptor_images/DataAdaptor_image2.png)

## Web API

WebAPI Adaptor that is extended from ODataAdaptor, is used for consuming data from WebApi Service.

To consume Web API service, set the service link to the Url property and set the adaptor type as ` WebApiAdaptor to the Adaptor Property of DataManager`.
    
{% highlight html %}
    
<ej:ComboBox ID="searchCustomer" AutoFill="true" runat="server" Width="100%" Query ="ej.Query().select('CustomerID').take(5)" DataTextField="CustomerID" DataValueField="CustomerID" Placeholder="Search a OrderID">
    <DataManager URL="http://js.syncfusion.com/demos/ejServices/Wcf/Northwind.svc/Orders/" Adaptor="WebApiAdaptor" CrossDomain="true"></DataManager>
</ej:ComboBox>

{% endhighlight %}

## WebMethod Adaptor

The WebMethod Adaptor is used to bind data source from web services and code behind methods. For every operation, an AJAX post will be sent to specified service. 

By using “WebMethodAdaptor” we can bind data from WebService to the ComboBox control and also we need to include “ScriptService” Attribute to WebService in order to enable request from client-side.Please refer [here](https://help.syncfusion.com/aspnet/datamanager/data-adaptors#webmethod-adaptor) to know more details on WebMethod Adaptor.

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

Initialize the ComboBox as follows

{% highlight html %}

    <ej:ComboBox ID="employeeList" Width="116px" Query="ej.Query().requiresCount()" DataTextField="Name" DataValueField="Country" runat="server">
        <DataManager URL="Default.aspx/Get" CrossDomain="true" Adaptor="WebMethodAdaptor"></DataManager>
    </ej:ComboBox>

{% endhighlight %}

