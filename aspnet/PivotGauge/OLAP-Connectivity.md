---
layout: post
title: OLAP Connectivity | PivotGauge | ASP.NET  | Syncfusion
description: olap connectivity 
platform: aspnet
control: PivotGauge
documentation: ug
---

# DataBinding 

## Binding PivotGauge to Offline Cube
To connect an OLAP Cube available in local machine, set the physical path of the Cube in the connection string. The following code example illustrates the same.

{% highlight c# %}

    string connectionString = @"DataSource = system drive:\OfflineCube\Adventure_Works_Ext.cub; Provider = MSOLAP;";
    OlapDataManager DataManager = new OlapDataManager(connectionString);
{% endhighlight %}

## Binding PivotGauge to Cube in local SQL Server
To connect an OLAP Cube available in SQL Server Analysis Service in local machine, set the server name and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code example illustrates the same.

{% highlight c# %}

    string connectionString = "Data source=localhost; Initial Catalog=Adventure Works DW;"; 
    OlapDataManager DataManager = new OlapDataManager(connectionString);
{% endhighlight %}

## Binding PivotGauge to Cube in online SQL Server
To connect an OLAP Cube available in SQL Server Analysis Service in online server through **XML/A**, set the host server link and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code example illustrates the same.

{% highlight c# %}

    string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;"; 
    OlapDataManager DataManager = new OlapDataManager(connectionString);
{% endhighlight %}

## Binding PivotGauge to Cube in online Mondrian Server
To connect an OLAP Cube available in Mondrian Server through **XML/A**, set the host server link and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code example illustrates the same.

{% highlight c# %}

    string connectionString = @"Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;";
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian;
{% endhighlight %}

## Binding PivotGauge to Cube in online ActivePivot Server
To connect an OLAP Cube available in ActivePivot Server through **XML/A**, set the host server link and database name in the connection string. When you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. The following code example illustrates the same.

{% highlight c# %}

    string connectionString = @"Data Source = http://localhost:8080/cva_s/xmla; Initial Catalog = CVAS;";
    OlapDataManager DataManager = new OlapDataManager(connectionString);
    DataManager.DataProvider.ProviderName=Syncfusion.Olap.DataProvider.Providers.ActivePivot;
{% endhighlight %}


## WCF
**Adding a WCF Service**

To add a WCF service in an existing web application, right-click on the project in Solution Explorer and select **Add > New Item**. In the **Add New Item** window, select WCF Service and name it as **“OlapGaugeService.svc”**, click **Add**.
 
Now WCF service is added into your application successfully which in-turn comprise of the following files. The utilization of these files will be explained in the immediate sections. 

* OlapGaugeService.svc
* OlapGaugeService.svc.cs
* IOlapGaugeService.cs

**Configuring WCF Service Class**

Remove the “DoWork” method present inside both `OlapGaugeService.svc.cs` and `IOlapGaugeService.cs files`. Next, add “AspNetCompatibilityRequirements” attribute on top of main class present inside `OlapGaugeService.svc.cs` and set “RequirementsMode” value to “Allowed”.

{% highlight c# %}

    namespace PivotGaugeDemo
    {
        [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
        public class OlapGaugeService : IOlapGaugeService
        {

        }
    }
{% endhighlight %}

**List of Dependency Libraries**

Next you need to add the below mentioned dependency libraries into your Web Application. These libraries could be found in GAC (Global Assembly Cache) as well.
 
To add them to your Web Application, right-click on **References** in Solution Explorer and select **Add Reference**. Now in the **Reference Manager** dialog, under **Assemblies > Extension**, the following Syncfusion libraries are found. 

N> If you have installed any version of SQL Server Analysis Service (SSAS) or Microsoft ADOMD.NET utility, then the location of Microsoft.AnalysisServices.AdomdClient library is [system drive:\Program Files (x86)\Microsoft.NET\ADOMD.NET]

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
* Syncfusion.EJ.Olap

**List of Namespaces**

Following are the list of namespaces to be added on top of the main class inside `OlapGaugeService.svc.cs` file.

{% highlight c# %}

    using System.ServiceModel.Activation;
    using Syncfusion.Olap.Manager;
    using Syncfusion.Olap.Reports;
    using Syncfusion.JavaScript;

    namespace PivotGaugeDemo
    {
        [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
        public class OlapGaugeService : IOlapGaugeService
        {

        }
    }
{% endhighlight %}

**Datasource Initialization**

Now the connection string to connect OLAP Cube, PivotGauge instances are created immediately inside the main class in `OlapGaugeService.svc.cs` file.

{% highlight c# %}

    namespace PivotGaugeDemo
    {
        [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
        public class OlapGaugeService : IOlapGaugeService
        {
            PivotGauge htmlHelper = new PivotGauge();
            string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
            //Other codes

        }
    }
{% endhighlight %}

**Service methods in WCF Service**

First, you need to define the service methods inside IOlapGaugeService interface, found in `IOlapGaugeService.cs` file, created while adding WCF Service to your Web Application.

{% highlight c# %}

    namespace PivotGaugeDemo
    {
        [ServiceContract]
        public interface IOlapGaugeService
        {
            [OperationContract]
            Dictionary<string, object> InitializeGauge(string action,string customObject);
        }
    }
{% endhighlight %}

Secondly, you need to elaborate the service methods inside the main class, found in `OlapGaugeService.svc.cs` file 

{% highlight c# %}

    namespace PivotGaugeDemo
    {
        [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
        public class OlapGaugeService : IOlapGaugeService
        {
            PivotGauge htmlHelper = new PivotGauge();
            string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";

            public Dictionary<string, object> InitializeGauge(string action,string customObject)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                DataManager.SetCurrentReport(CreateOlapReport());
                return htmlHelper.GetJsonData(action, DataManager);
            }

            private OlapReport CreateOlapReport()
            {
                OlapReport report = new OlapReport();
                report.CurrentCubeName = "Adventure Works";

                //Specifying the KPI name
                KpiElements kpiElement = new KpiElements();
                kpiElement.Elements.Add(new KpiElement { Name = "Internet Revenue", ShowKPIGoal = true, ShowKPIStatus = true, ShowKPIValue = true, ShowKPITrend = true });

                DimensionElement dimensionElementColumn = new DimensionElement();
                //Specifying the dimension name
                dimensionElementColumn.Name = "Customer";
                //Adding the level with the hierarchy Name
                dimensionElementColumn.AddLevel("Customer Geography", "Country");

                //Specifying the measure name
                MeasureElements measureElementColumn = new MeasureElements();
                measureElementColumn.Elements.Add(new MeasureElement { Name = "Internet Sales Amount" });

                DimensionElement dimensionElementRow = new DimensionElement();
                //Specifying the dimension name
                dimensionElementRow.Name = "Date";
                //Adding the level with the hierarchy Name
                dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");
                dimensionElementRow.Hierarchy.LevelElements["Fiscal Year"].Add("FY 2004");
                dimensionElementRow.Hierarchy.LevelElements["Fiscal Year"].IncludeAvailableMembers = true;

                report.CategoricalElements.Add(dimensionElementColumn);
                report.CategoricalElements.Add(kpiElement);
                report.CategoricalElements.Add(measureElementColumn);
                report.SeriesElements.Add(dimensionElementRow);
                return report;
            }
        }
    }
{% endhighlight %}

**Configuring Web Configuration File**

You can expose services through the properties such as binding, contract and address by using an endpoint.

* Contract: This property indicates that the contract of the endpoint is exposing. Here you are referring to **IOlapGaugeService** contract and hence it is **PivotGaugeDemo.IOlapGaugeService**.
* Binding: In your application, you use **webHttpBinding** to post and receive the requests and responses between the client-end and the service.
* behaviorConfiguration: This property contains the name of the behavior to be used in the endpoint.

The endpointBehaviors are illustrated as follows. 
 
{% highlight xml %}

    <system.serviceModel>
        ……
        ……
        <services>
            <service name="PivotGaugeDemo.OlapGaugeService">
                <endpoint address="" behaviorConfiguration="PivotGaugeDemo.OlapGaugeServiceAspNetAjaxBehavior" binding="webHttpBinding" contract="PivotGaugeDemo.IOlapGaugeService" />
            </service>
        </services>
    </system.serviceModel>
{% endhighlight %}

The endpointBehaviors contain all the behaviors for an endpoint. You can link each endpoint to the respective behavior only by using this name property.

{% highlight xml %}

    <system.serviceModel>
        <behaviors>
            <endpointBehaviors>
                <behavior name="PivotGaugeDemo.OlapGaugeServiceAspNetAjaxBehavior">
                    <enableWebScript />
                </behavior>
            </endpointBehaviors>
        </behaviors>
        ……
        ……
    </system.serviceModel>
{% endhighlight %}

Now, PivotGauge is rendered with Internet Revenue for Internet Sales Amount over a Fiscal Year 2004 across different customer geographic locations

![](Olap-Connectivity_images/ServerModeWCF.png)