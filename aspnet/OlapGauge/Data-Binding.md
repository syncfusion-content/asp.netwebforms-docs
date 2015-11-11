---
layout: post
title: Data Binding | OLAPGauge | ASP.NET | Syncfusion
description: data binding
platform: aspnet
control: OLAPGauge
documentation: ug
---

# Data Binding

##Binding OlapGauge to Offline Cube

To connect an OLAP Cube available in local machine, physical path of the Cube needs to be set in the connection string. Below code sample illustrates the same.

{% highlight c# %}

string connectionString = @"DataSource = system drive:\OfflineCube\Adventure_Works_Ext.cub; Provider = MSOLAP;";
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

##Binding OlapGauge to Cube in local SQL Server

To connect an OLAP Cube available in SQL Server Analysis Service in local machine, server name and database name needs to be set in the connection string. If you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. Below code sample illustrates the same.

{% highlight c# %}

string connectionString = "Data source=localhost; Initial Catalog=Adventure Works DW;"; 
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

##Binding OlapGauge to Cube in local SQL Server

To connect an OLAP Cube available in SQL Server Analysis Service in online server through XML/A, host server link and database name needs to be set in the connection string. If you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. Below code sample illustrates the same.

{% highlight c# %}

string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;"; 
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

##Binding OlapGauge to Cube in online Mondrian Server

To connect an OLAP Cube available in Mondrian Server through XML/A, host server link and database name needs to be set in the connection string. If you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. Below code sample illustrates the same.

{% highlight c# %}

string connectionString = @"Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;";
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian;

{% endhighlight %}

##Binding OlapGauge to Cube in online ActivePivot Server

{% highlight c# %}

string connectionString = @"Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;"; 
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName=Syncfusion.Olap.DataProvider.Providers.ActivePivot;

{% endhighlight %}

##WCF
**Adding a WCF Service**

To add a WCF service in an existing Web Application, right-click on the project in Solution Explorer and select **Add > New Item**. In the **Add New Item** window, select WCF Service and name it as `OlapGaugeService.svc`, click Add.

Now, WCF service is added into the application successfully that comprises of the following files. The utilization of these files is explained in the immediate sections

* OlapGaugeService.svc
* OlapGaugeService.svc.cs
* IOlapGaugeService.cs

**Configuring WCF Service Class**

The following are the list of namespaces to be added on top of the main class inside `OlapGaugeService.svc.cs` file. Remove the **“DoWork”** method present inside both `OlapGaugeService.svc.cs` and `IOlapGaugeService.cs` files.  Next, add **“AspNetCompatibilityRequirements”** attribute on top of main class present inside OlapGaugeService.svc.cs and set **“RequirementsMode”** value to **“Allowed”**.

{% highlight c# %}

using Syncfusion.JavaScript.Olap;
using Syncfusion.Olap.Manager;
using Syncfusion.Olap.Reports;
using System;
using System.Collections.Generic;
using System.Configuration;
using System.Linq;
using System.Runtime.Serialization;
using System.ServiceModel;
using System.ServiceModel.Activation;
using System.Text;
using System.Web.Script.Serialization;

namespace OlapGaugeDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class OlapGaugeService: IOlapGaugeService
    {
    
    }
}
{% endhighlight %}

**Datasource Initialization**

Now the connection string to connect OLAP Cube, OlapGauge and JavaScriptSerializer instances are created immediately inside the main class in `OLAPGaugeService.svc.cs` file.

{% highlight c# %}

namespace OlapGaugeDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class OlapGaugeService: IOlapGaugeService
    {
        OlapGauge htmlHelper = new OlapGauge();
        string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        JavaScriptSerializer serializer = new JavaScriptSerializer();
      	……
        ……
    }
}

{% endhighlight %}

**Service methods in WCF Service**

First, declare the service methods inside **IOlapGaugeService** interface, found in `IOlapGaugeService.cs` file created while adding WCF Service to the Application.

{% highlight c# %}
namespace OlapGaugeDemo
{
    [ServiceContract]
    public interface IOlapGaugeService
    {
        [OperationContract]
        Dictionary < string, object > InitializeGauge(string action, string customObject);
    }
}
{% endhighlight %}

Then, elaborate the service methods inside the main class, found in `OlapGaugeService.svc.cs` file.

{% highlight c# %}

namespace OlapGaugeDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class OlapGaugeService: IOlapGaugeService
    {
        OlapGauge htmlHelper = new OlapGauge();
        string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        JavaScriptSerializer serializer = new JavaScriptSerializer();
        //This method provides the required information from server-side for initializing the OlapGauge.
        public Dictionary < string, object > InitializeGauge(string action, string customObject)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                DataManager.SetCurrentReport(CreateOlapReport());
                return htmlHelper.GetJsonData(action, DataManager);
            }
            //This method carries the information about the default report that is rendered within OlapGauge initially. 
        private OlapReport CreateOlapReport()
        {
            OlapReport report = new OlapReport();
            report.CurrentCubeName = "Adventure Works";
            KpiElements kpiElement = new KpiElements();
            kpiElement.Elements.Add(new KpiElement
            {
                Name = "Revenue", ShowKPIGoal = true, ShowKPIStatus = true, ShowKPIValue = true, ShowKPITrend = true
            });
            DimensionElement dimensionElement1 = new DimensionElement();
            DimensionElement dimensionElement2 = new DimensionElement();
            DimensionElement dimensionElement3 = new DimensionElement();
            MeasureElements measureElement = new MeasureElements();
            measureElement.Elements.Add(new MeasureElement
            {
                UniqueName = "[Measures].[Customer Count]"
            });
            dimensionElement1.Name = "Date";
            dimensionElement1.AddLevel("Fiscal Year", "Fiscal Year");
            dimensionElement1.Hierarchy.LevelElements["Fiscal Year"].Add("FY 2004");
            dimensionElement1.Hierarchy.LevelElements["Fiscal Year"].IncludeAvailableMembers = true;
            dimensionElement2.Name = "Sales Channel";
            dimensionElement2.AddLevel("Sales Channel", "Sales Channel");
            dimensionElement2.Hierarchy.LevelElements["Sales Channel"].Add("Reseller");
            dimensionElement2.Hierarchy.LevelElements["Sales Channel"].IncludeAvailableMembers = true;
            dimensionElement3.Name = "Product";
            dimensionElement3.AddLevel("Product Model Lines", "Product Line");
            report.CategoricalElements.Add(new Item
            {
                ElementValue = dimensionElement2
            });
            report.CategoricalElements.Add(new Item
            {
                ElementValue = dimensionElement1
            });
            report.CategoricalElements.Add(new Item
            {
                ElementValue = kpiElement
            });
            report.SeriesElements.Add(new Item
            {
                ElementValue = dimensionElement3
            });
            return report;
        }
    }
}

{% endhighlight %}

**Configuring Web Configuration File**

The services could be exposed through the properties, binding, contract and address by using an endpoint.

* Contract: This property indicates that the contract of the endpoint is exposing. Here you are referring to **IOlapGaugeService** contract and hence it is **OlapGaugeDemo.IOlapGaugeService**.
* Binding: In your application, you use webHttpBinding to post and receive the requests and responses between the client-end and the service.
* BehaviorConfiguration: This property contains the name of the behavior to be used in the endpoint

The endpointBehaviors are illustrated as follows

<system.serviceModel> 
    …… 
    ……
    <services>
        <service name="OlapGaugeDemo.OlapGaugeervice">
            <endpoint address="" behaviorConfiguration="OlapGaugeDemo.OlapGaugeServiceAspNetAjaxBehavior" binding="webHttpBinding" contract="OlapGaugeDemo.IOlapGaugeService" /> </service>
    </services>
</system.serviceModel>

{% endhighlight %}

The endpointBehaviors contain all the behaviors for an endpoint. You can link each endpoint to the respective behavior only by using this name property.

{% highlight xml %}

<system.serviceModel> 
    …… 
    ……
    <behaviors> 
        …… 
        ……
        <endpointBehaviors>
            <behavior name="OlapGaugeDemo.OlapGaugeServiceAspNetAjaxBehavior">
                <enableWebScript /> </behavior>
        </endpointBehaviors>
    </behaviors>
</system.serviceModel>

{% endhighlight %}

N> In this example, **“OlapGaugeDemo”** indicates the name and root namespace of the Application created in Visual Studio IDE and **“OlapGaugeService”** indicates the name of the WCF service created.

In this example, OlapGauge is rendered with Internet Revenue for Internet Sales Amount over a Fiscal Year 2004 across different customer geographic locations.
 
![](Data-Binding_images/OlapGauge.png)   

