---
layout: post
title: OLAP Connectivity | PivotTreeMap | ASP.NET | Syncfusion
description: olap connectivity
platform: aspnet
control: PivotTreeMap
documentation: ug
---

# DataBinding 

## Binding PivotTreeMap to Offline Cube
To connect an OLAP Cube available in local machine, physical path of the Cube needs to be set in the connection string. Below code sample illustrates the same.

{% highlight c# %}

string connectionString = @"DataSource = system drive:\OfflineCube\Adventure_Works_Ext.cub; Provider = MSOLAP;";
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding PivotTreeMap to Cube in local SQL Server
To connect an OLAP Cube available in SQL Server Analysis Service in local machine, server name and database name needs to be set in the connection string. If you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. Below code sample illustrates the same.

{% highlight c# %}

string connectionString = "Data source=localhost; Initial Catalog=Adventure Works DW;"; 
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding PivotTreeMap to Cube in online SQL Server
To connect an OLAP Cube available in SQL Server Analysis Service in online server through **XML/A**, host server link and database name needs to be set in the connection string. If you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. Below code sample illustrates the same.

{% highlight c# %}

string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;"; 
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding PivotTreeMap to Cube in online Mondrian Server
To connect an OLAP Cube available in Mondrian Server through **XML/A**, host server link and database name needs to be set in the connection string. If you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. Below code sample illustrates the same.

{% highlight c# %}

string connectionString = @"Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;";
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian;

{% endhighlight %}

## Binding PivotTreeMap to Cube in online ActivePivot Server
To connect an OLAP Cube available in ActivePivot Server through **XML/A**, host server link and database name needs to be set in the connection string. If you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. Below code sample illustrates the same.

{% highlight c# %}

string connectionString = @"Data Source = http://localhost:8080/cva_s/xmla; Initial Catalog = CVAS;";
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName=Syncfusion.Olap.DataProvider.Providers.ActivePivot;

{% endhighlight %}


## WCF
**Adding a WCF Service**

To add a WCF service in an existing Web application, right-click on the project in Solution Explorer and select **Add > New Item**. In the **Add New Item** window, select WCF Service and name it as `OlapService.svc`, click **Add**.
 
Now WCF service is added into your application successfully which in-turn comprise of the following files. The utilization of these files will be explained in the immediate sections. 

* OlapService.svc
* OlapService.svc.cs
* IOlapService.cs

**Configuring WCF Service Class**

Remove the **“DoWork”** method present inside both `OlapService.svc.cs` and `IOlapService.cs files`. Next, add **“AspNetCompatibilityRequirements”** attribute on top of main class present inside OlapService.svc.cs and set **“RequirementsMode”** value to **“Allowed”**.

{% highlight c# %}

namespace PivotTreeMapDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class OlapService : IOlapService
    {

    }
}


{% endhighlight %}

**List of Dependency Libraries**

Next you need to add the below mentioned dependency libraries into your Web Application. These libraries could be found in GAC (Global Assembly Cache) as well.
 
To add them to your Web Application, right-click on **References** in Solution Explorer and select **Add Reference**. Now in the **Reference Manager** dialog, under **Assemblies > Extension**, the following Syncfusion libraries are found. 

N> If you have installed any version of SQL Server Analysis Service (SSAS) or Microsoft ADOMD.NET utility, then the location of Microsoft.AnalysisServices.AdomdClient library is [system drive:\Program Files (x86)\Microsoft.NET\ADOMD.NET]. And if you have installed any version of Essential Studio, then the location of Syncfusion libraries is [system drive:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Assemblies].

* Microsoft.AnalysisServices.AdomdClient
* Syncfusion.Compression.Base
* Syncfusion.Linq.Base
* Syncfusion.Olap.Base
* Syncfusion.PivotAnalysis.Base
* Syncfusion.EJ
* Syncfusion.EJ.Web
* Syncfusion.EJ.Pivot

**List of Namespaces**

Following are the list of namespaces to be added on top of the main class inside `OlapService.svc.cs` file.

{% highlight c# %}

using System.Web;
using System.Collections.Generic;
using System.Configuration;
using System.Linq;
using System.Net;
using System.Web.Script.Serialization;
using Syncfusion.Olap.Manager;
using Syncfusion.Olap.Reports;
using System.ServiceModel.Activation;
using Syncfusion.JavaScript;
using OLAPUTILS = Syncfusion.JavaScript.Olap;

namespace PivotTreeMaptDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class OlapService : IOlapService
    {

    }
}

{% endhighlight %}

**Datasource Initialization**

Now the connection string to connect OLAP Cube and PivotTreeMap instances are created immediately inside the main class in `OlapService.svc.cs` file.

{% highlight c# %}

namespace PivotTreeMaptDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class OlapService : IOlapService
    {
        PivotTreeMap htmlHelper = new PivotTreeMap();
        string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        //Other codes

    }
}

{% endhighlight %}

**Service methods in WCF Service**

First, declare the service methods inside **IOlapService** interface, found in `IOlapService.cs` file, created while adding WCF Service to the Application.

 {% highlight c# %}

namespace PivotTreeMaptDemo
{
    [ServiceContract]
    public interface IOlapService
    {
        [OperationContract]
        Dictionary< string, object > InitializeTreeMap(string action, string currentReport, string customObject);

        [OperationContract]
        Dictionary<string, object> DrillTreeMap(string action, string drillInfo, string olapReport, string customObject);
    }
}

{% endhighlight %}
Then, elaborate the service methods inside the main class, found in `OlapService.svc.cs` file. 

{% highlight c# %}

namespace PivotTreeMaptDemo 
{ 
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)] 
    public class OlapService : IOlapService
    {
        PivotTreeMap htmlHelper = new PivotTreeMap(); 
        string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        //This method provides the required information from the server side when initializing the PivotTreeMap.
        public Dictionary< string, object > InitializeTreeMap(string action, string currentReport, string customObject)
        {
            OlapDataManager DataManager = null;
            DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(CreateOlapReport());
            return htmlHelper.GetJsonData(action, DataManager);
        }

        public Dictionary<string, object> DrillTreeMap(string action, string drillInfo, string olapReport, string customObject)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);            
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(olapReport));
            return htmlHelper.GetJsonData(action, DataManager, drillInfo);
        }

        private OlapReport CreateOlapReport()
        {
            OlapReport olapReport = new OlapReport();
            olapReport.Name = "Default Report";
            olapReport.CurrentCubeName = "Adventure Works";

            DimensionElement dimensionElementColumn = new DimensionElement();
            //Specifying the Name for the Dimension Element
            dimensionElementColumn.Name = "Date";
            dimensionElementColumn.AddLevel("Fiscal", "Fiscal Year");

            MeasureElements measureElementColumn = new MeasureElements();
            //Specifying the Name for the Measure Element
            measureElementColumn.Elements.Add(new MeasureElement { Name = "Customer Count" });

            DimensionElement dimensionElementRow = new DimensionElement();
            //Specifying the Dimension Name
            dimensionElementRow.Name = "Customer";
            dimensionElementRow.AddLevel("Customer Geography", "Country");

            ///Adding Row Members
            olapReport.SeriesElements.Add(dimensionElementRow);
            ///Adding Column Members
            olapReport.CategoricalElements.Add(dimensionElementColumn);
            ///Adding Measure Element
            olapReport.CategoricalElements.Add(measureElementColumn);
            return olapReport;
        }
    }
}


{% endhighlight %}

**Configuring Web Configuration File**

The services could be exposed through the properties, binding, contract and address by using an endpoint.

* Contract: This property indicates that the contract of the endpoint is exposing. Here you are referring to `IOlapService` contract and hence it is `PivotTreeMapDemo.IOlapService`.
* Binding: In your application, you use `webHttpBinding` to post and receive the requests and responses between the client-end and the service.
* BehaviorConfiguration: This property contains the name of the behavior to be used in the endpoint.

The endpointBehaviors are illustrated as follows. 
 
{% highlight xaml %}

<system.serviceModel> 
    ...... 
    ...... 
    <services> 
        <service name="PivotTreeMapDemo.OlapService"> 
            <endpoint address="" behaviorConfiguration="PivotTreeMapDemo.OlapServiceAspNetAjaxBehavior" binding="webHttpBinding" contract="PivotTreeMapDemo.IOlapService" /> 
        </service> 
    </services> 
</system.serviceModel>

{% endhighlight %}

The endpointBehaviors contain all the behaviors for an endpoint. You can link each endpoint to the respective behavior only by using this name property.

{% highlight xaml %}

<system.serviceModel> 
<behaviors> 
        <endpointBehaviors> 
            <behavior name="PivotTreeMapDemo.OlapServiceAspNetAjaxBehavior"> 
                <enableWebScript /> 
            </behavior> 
        </endpointBehaviors> 
    </behaviors> 
    ...... 
    ...... 
</system.serviceModel>


{% endhighlight %}

N> In this example, **“PivotTreeMapDemo”** indicates the name and root namespace of the Application created in Visual Studio IDE and **“OlapService”** indicates the name of the WCF service created.

The above code will generate a simple PivotTreeMap showing Customer Count over different customer geographic locations across a period of fiscal years.

{% include image.html url="/js/PivotTreeMap/OLAP-Connectivity_images/olapwebapi.png" %}

