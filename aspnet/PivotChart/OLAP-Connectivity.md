---
layout: post
title: OLAP Connectivity | PivotChart | ASP.NET | Syncfusion
description: olap connectivity 
platform: aspnet
control: PivotChart
documentation: ug
---

# DataBinding 

## Binding PivotChart to Offline Cube
To connect an OLAP Cube available in local machine, set the physical path of the Cube in the connection string. The following code example illustrates the same.

{% highlight c# %}

string connectionString = @"DataSource = system drive:\OfflineCube\Adventure_Works_Ext.cub; Provider = MSOLAP;";
OlapDataManager DataManager = new OlapDataManager(connectionString);
{% endhighlight %}

## Binding PivotChart to Cube in local SQL Server
To connect an OLAP Cube available in SQL Server Analysis Service in local machine, set the server name and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code example illustrates the same.

{% highlight c# %}

string connectionString = "Data source=localhost; Initial Catalog=Adventure Works DW;"; 
OlapDataManager DataManager = new OlapDataManager(connectionString);
{% endhighlight %}

## Binding PivotChart to Cube in online SQL Server
To connect an OLAP Cube available in SQL Server Analysis Service in online server through **XML/A**, set the host server link and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code example illustrates the same.

{% highlight c# %}

string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;"; 
OlapDataManager DataManager = new OlapDataManager(connectionString);
{% endhighlight %}

## Binding PivotChart to Cube in online Mondrian Server
To connect an OLAP Cube available in Mondrian Server through **XML/A**, set the host server link and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code example illustrates the same.

{% highlight c# %}

string connectionString = @"Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;";
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian;
{% endhighlight %}

## Binding PivotChart to Cube in online ActivePivot Server
To connect an OLAP Cube available in ActivePivot Server through **XML/A**, set the host server link and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code example illustrates the same.

{% highlight c# %}

string connectionString = @"Data Source = http://localhost:8080/cva_s/xmla; Initial Catalog = CVAS;";
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName=Syncfusion.Olap.DataProvider.Providers.ActivePivot;
{% endhighlight %}


## WCF
**Adding a WCF Service**

To add a WCF service in an existing web application, right-click on the project in Solution Explorer and select **Add > New Item**. In the **Add New Item** window, select WCF Service and name it as **“OlapService.svc”**, click **Add**.
 
Now WCF service is added into your application successfully which in-turn comprise of the following files. The utilization of these files will be explained in the immediate sections. 

* OlapService.svc
* OlapService.svc.cs
* IOlapService.cs

**Configuring WCF Service Class**

Remove the “DoWork” method present inside both `OlapService.svc.cs` and `IOlapService.cs files`. Next, add “AspNetCompatibilityRequirements” attribute on top of main class present inside `OlapService.svc.cs` and set “RequirementsMode” value to “Allowed”.

{% highlight c# %}

namespace PivotChartDemo
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
* Syncfusion.XlsIO.Base
* Syncfusion.Pdf.Base
* Syncfusion.DocIO.Base
* Syncfusion.EJ
* Syncfusion.EJ.Web
* Syncfusion.EJ.Pivot

**List of Namespaces**

Following are the list of namespaces to be added on top of the main class inside `OlapService.svc.cs` file.

{% highlight c# %}

using System.ServiceModel.Activation;
using Syncfusion.Olap.Manager;
using Syncfusion.Olap.Reports;
using Syncfusion.JavaScript;

namespace PivotChartDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class OlapService : IOlapService
    {

    }
}
{% endhighlight %}

**Datasource Initialization**

Now the connection string to connect OLAP Cube, PivotChart instances are created immediately inside the main class in `OlapService.svc.cs` file.

{% highlight c# %}

namespace PivotChartDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class OlapService : IOlapService
    {
        PivotChart htmlHelper = new PivotChart();
        string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        //Other codes

    }
}
{% endhighlight %}

**Service methods in WCF Service**

First, you need to define the service methods inside IOlapService interface, found in `IOlapService.cs` file, created while adding WCF Service to your Web Application.

{% highlight c# %}

namespace PivotChartDemo
{
    [ServiceContract]
    public interface IOlapService
    {
        [OperationContract]
        Dictionary<string, object> InitializeChart(string action, string customObject);
        [OperationContract]
        Dictionary<string, object> DrillChart(string action, string drilledSeries, string olapReport, string customObject);
    }
}
{% endhighlight %}

Secondly, you need to elaborate the service methods inside the main class, found in `OlapService.svc.cs` file 

{% highlight c# %}

namespace PivotChartDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class OlapService : IOlapService
    {
        PivotChart htmlHelper = new PivotChart();
        string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";

        public Dictionary<string, object> InitializeChart(string action, string customObject)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(CreateOlapReport());
            return htmlHelper.GetJsonData(action, DataManager);
        }

        public Dictionary<string, object> DrillChart(string action, string drilledSeries, string olapReport, string customObject)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(Syncfusion.JavaScript.Olap.Utils.DeserializeOlapReport(olapReport));
            return htmlHelper.GetJsonData(action, DataManager, drilledSeries);
        }

        private OlapReport CreateOlapReport()
        {
            OlapReport olapReport = new OlapReport();
            olapReport.Name = "Default Report";
            olapReport.CurrentCubeName = "Adventure Works";

            DimensionElement dimensionElementColumn = new DimensionElement();
            //Specifying the Name for the Dimension Element
            dimensionElementColumn.Name = "Customer";
            dimensionElementColumn.AddLevel("Customer Geography", "Country");

            MeasureElements measureElementColumn = new MeasureElements();
            //Specifying the Name for the Measure Element
            measureElementColumn.Elements.Add(new MeasureElement { Name = "Customer Count" });

            DimensionElement dimensionElementRow = new DimensionElement();
            //Specifying the Dimension Name
            dimensionElementRow.Name = "Date";
            dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

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

You can expose services through the properties such as binding, contract and address by using an endpoint.

* Contract: This property indicates that the contract of the endpoint is exposing. Here you are referring to **IOlapService** contract and hence it is **PivotChartDemo.IOlapService**.
* Binding: In your application, you use **webHttpBinding** to post and receive the requests and responses between the client-end and the service.
* behaviorConfiguration: This property contains the name of the behavior to be used in the endpoint.

The endpointBehaviors are illustrated as follows. 
 
{% highlight xml %}

<system.serviceModel>
    ……
    ……
    <services>
        <service name="PivotChartDemo.OlapService">
            <endpoint address="" behaviorConfiguration="PivotChartDemo.OlapServiceAspNetAjaxBehavior" binding="webHttpBinding" contract="PivotChartDemo.IOlapService" />
        </service>
    </services>
</system.serviceModel>
{% endhighlight %}

The endpointBehaviors contain all the behaviors for an endpoint. You can link each endpoint to the respective behavior only by using this name property.

{% highlight xml %}

<system.serviceModel>
    <behaviors>
        <endpointBehaviors>
            <behavior name="PivotChartDemo.OlapServiceAspNetAjaxBehavior">
                <enableWebScript />
            </behavior>
        </endpointBehaviors>
    </behaviors>
    ……
    ……
</system.serviceModel>
    
{% endhighlight %}

Now, PivotChart will be rendered with customer count over a period of fiscal years across different customer geographic locations.

![](OLAP-Connectivity_images/ServerModeWCF.png)

