---
layout: post
title: OLAP Connectivity | PivotTreeMap | ASP.NET | Syncfusion
description: olap connectivity
platform: aspnet
control: PivotTreeMap
documentation: ug
---

# Data binding

## Binding pivot tree map to offline cube
To connect to an OLAP cube available in the local machine, the physical path of the cube should be set in the connection string. The following code sample illustrates this process:

{% highlight c# %}

string connectionString = @"DataSource = system drive:\OfflineCube\Adventure_Works_Ext.cub; Provider = MSOLAP;";
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding pivot tree map to cube in local SQL Server
To connect to an OLAP cube available in the SQL Server Analysis Service of the local machine, the server name and database name should be set in the connection string. If you have any credentials to connect your cube, then set the user ID and password attributes accordingly. The following code sample illustrates this process:

{% highlight c# %}

string connectionString = "Data source=localhost; Initial Catalog=Adventure Works DW;"; 
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding pivot tree map to cube in online SQL Server
To connect to an OLAP cube available in SQL Server Analysis Service in online server through **XML/A**, the host server link and database name should be set in the connection string. If you have any credentials to connect your cube, then set the user ID and password attributes accordingly. The following code sample illustrates this process:

{% highlight c# %}

string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;"; 
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding pivot tree map to cube in online Mondrian Server
To connect to an OLAP cube available in Mondrian Server through **XML/A**, the host server link and database name should be set in the connection string. If you have any credentials to connect your cube, then set the user ID and password attributes accordingly. The following code sample illustrates this process:

{% highlight c# %}

string connectionString = @"Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;";
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian;

{% endhighlight %}

## Binding pivot tree map to cube in online Active Pivot Server
To connect to an OLAP cube available in Active Pivot Server through **XML/A**, the host server link and database name should be set in the connection string. If you have any credentials to connect your cube, then set the user ID and password attributes accordingly. The following code sample illustrates this process:

{% highlight c# %}

string connectionString = @"Data Source = http://localhost:8080/cva_s/xmla; Initial Catalog = CVAS;";
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName=Syncfusion.Olap.DataProvider.Providers.ActivePivot;

{% endhighlight %}


## WCF
**Adding a WCF service**

To add a WCF service in an existing web application, right-click the project in the solution explorer and select **Add > New Item**. In the **Add New Item** window, select the WCF service and name it `OlapService.svc`, and then click **Add**.
 
The WCF service is added to your application, which, in-turn, comprises the following files. The utilization of these files will be explained in the immediate sections.

* OlapService.svc
* OlapService.svc.cs
* IOlapService.cs

**Configuring WCF service class**

Remove the **“DoWork”** method present in both `OlapService.svc.cs` and `IOlapService.cs files`. Next, add **“AspNetCompatibilityRequirements”** attribute on top of the main class present in OlapService.svc.cs and set the **“RequirementsMode”** value to **“Allowed”**.

{% highlight c# %}

namespace PivotTreeMapDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class OlapService : IOlapService
    {

    }
}


{% endhighlight %}

**List of dependency libraries**

Next, you can add the below-mentioned dependency libraries to your web application. These libraries can be found in the GAC (Global Assembly Cache).
 
To add them to your web application, right-click **References** in the solution explorer and select **Add Reference**. In the **Reference Manager** dialog, under **Assemblies > Extension**, the following Syncfusion libraries are found. 

N> If you have installed any version of SQL Server Analysis Service (SSAS) or Microsoft ADOMD.NET utility, then the location of Microsoft.AnalysisServices.AdomdClient library is [system drive:\Program Files (x86)\Microsoft.NET\ADOMD.NET]. And if you have installed any version of Essential Studio, then the location of Syncfusion libraries is [system drive:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Assemblies].

* Microsoft.AnalysisServices.AdomdClient
* Syncfusion.Compression.Base
* Syncfusion.Linq.Base
* Syncfusion.Olap.Base
* Syncfusion.PivotAnalysis.Base
* Syncfusion.EJ
* Syncfusion.EJ.Web
* Syncfusion.EJ.Export
* Syncfusion.EJ.Pivot

**List of namespaces**

Following is the list of namespaces to be added on top of the main class in the `OlapService.svc.cs` file:

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

**Data source initialization**

Now, the connection string to connect the OLAP cube and pivot tree map instances is created immediately in the main class of the `OlapService.svc.cs` file.

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

**Service methods in WCF service**

First, declare the service methods in the **IOlapService** interface, find in the `IOlapService.cs` file which was created while adding the WCF service to the application.

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
Then, elaborate the service methods in the main class, found in the `OlapService.svc.cs` file.

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

**Configuring web configuration file**

The services can be exposed through the properties such as binding, contract, and address by using an endpoint.

* Contract: This property indicates that the contract of the endpoint is exposed. Refer to the `IOlapService` contract and it is written as `PivotTreeMapDemo.IOlapService`.
* Binding: In your application, you can use `webHttpBinding` to post and receive requests and responses between the client-end and the service.
* BehaviorConfiguration: This property contains the name of the behavior to be used in the endpoint.

The endpointBehaviors are illustrated as follows:
 
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

The endpointBehaviors contain all behaviors for an endpoint. You can link each endpoint to the respective behavior only by using the name property.

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

N> In this example, the **“PivotTreeMapDemo”** indicates the name and root namespace of the application that is created in the Visual Studio IDE and the **“OlapService”** indicates the name of the created WCF service.

The above code will generate a simple pivot tree map showing customer count over different customer geographic locations across a period of fiscal years.

{% include image.html url="/js/PivotTreeMap/OLAP-Connectivity_images/olapwebapi.png" %}

