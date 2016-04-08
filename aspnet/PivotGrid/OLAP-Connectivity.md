---
layout: post
title: OLAP Connectivity | PivotGrid | ASP.NET | Syncfusion
description: olap connectivity 
platform: aspnet
control: PivotGrid
documentation: ug
---

# Data Binding

## Binding PivotGrid to Offline Cube

To connect an OLAP Cube available in local machine, physical path of the Cube needs to be set in the connection string. Below code sample illustrates the same.

{% highlight c# %}

string connectionString = @"DataSource = system drive:\OfflineCube\Adventure_Works_Ext.cub; Provider = MSOLAP;";
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding PivotGrid to Cube in local SQL Server

To connect an OLAP Cube available in SQL Server Analysis Service in local machine, server name and database name needs to be set in the connection string. If you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. Below code sample illustrates the same.

{% highlight c# %}

string connectionString = "Data source=localhost; Initial Catalog=Adventure Works DW;"; 
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding PivotGrid to Cube in online SQL Server

To connect an OLAP Cube available in SQL Server Analysis Service in online server through XML/A, host server link and database name needs to be set in the connection string. If you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. Below code sample illustrates the same.

{% highlight c# %}

string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;"; 
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding PivotGrid to Cube in online Mondrian Server

To connect an OLAP Cube available in Mondrian Server through XML/A, host server link and database name needs to be set in the connection string. If you have any credentials to connect your Cube, then set the “User ID” and “Password” attributes accordingly. Below code sample illustrates the same.

{% highlight c# %}

string connectionString = @"Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;";
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian;

{% endhighlight %}

## Binding PivotGrid to Cube in online ActivePivot Server

{% highlight c# %}

string connectionString = @"Data Source = http://localhost:8080/cva_s/xmla; Initial Catalog = CVAS;"; 
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName=Syncfusion.Olap.DataProvider.Providers.ActivePivot;

{% endhighlight %}

## WCF
**Adding a WCF Service**

To add a WCF service in an existing Web Application, right-click on the project in Solution Explorer and select **Add > New Item**. In the **Add New Item** window, select WCF Service and name it as `PivotGridService.svc`, click Add.

Now, WCF service is added into the application successfully that comprises of the following files. The utilization of these files is explained in the immediate sections

* PivotGridService.svc
* PivotGridService.svc.cs
* IPivotGridService.cs

**Configuring WCF Service Class**

Remove the **“DoWork”** method present inside both `PivotGridService.svc.cs` and `IPivotGridService.cs` files.  Next, add **“AspNetCompatibilityRequirements”** attribute on top of main class present inside PivotGridService.svc.cs and set **“RequirementsMode”** value to **“Allowed”**.

{% highlight c# %}

namespace PivotGridDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class PivotGridService : IPivotGridService
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
* Syncfusion.EJ.Olap

**List of Namespaces**

Following are the list of namespaces to be added on top of the main class inside `PivotGridService.svc.cs` file.

{% highlight c# %}

using System.Web.Script.Serialization;
using System.ServiceModel.Activation;
using Syncfusion.Olap.Manager;
using Syncfusion.Olap.Reports;
using Syncfusion.JavaScript;
using OLAPUTILS = Syncfusion.JavaScript.Olap;

namespace PivotGridDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class PivotGridService : IPivotGridService
    {

    }
}

{% endhighlight %}


**Datasource Initialization**

Now the connection string to connect OLAP Cube, PivotGrid and JavaScriptSerializer instances are created immediately inside the main class in `PivotGridService.svc.cs` file.

{% highlight c# %}

namespace PivotGridDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class PivotGridService: IPivotGridService
    {
        PivotGrid htmlHelper = new PivotGrid();
        string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        JavaScriptSerializer serializer = new JavaScriptSerializer();
        ....
		....
		
    }
}

{% endhighlight %}

**Service methods in WCF Service**

First, declare the service methods inside **IPivotGridService** interface, found in `IPivotGridService.cs` file created while adding WCF Service to the Application.

{% highlight c# %}

namespace PivotGridDemo
{
    [ServiceContract]
    public interface IPivotGridService
    {
        [OperationContract]
        Dictionary<string, object> InitializeGrid(string action, string gridLayout, bool enablePivotFieldList, object customObject);

        [OperationContract]
        Dictionary<string, object> DrillGrid(string action, string cellPosition, string currentReport, string headerInfo, string layout, object customObject);

        [OperationContract]
        Dictionary<string, object> Paging(string action, string pagingInfo, string currentReport, string gridLayout, object customObject);

        [OperationContract]
        Dictionary<string, object> NodeDropped(string action, string dropType, string nodeInfo, string filterParams, string currentReport);

        [OperationContract]
        Dictionary<string, object> RemoveButton(string action, string headerInfo, string currentReport);

        [OperationContract]
        Dictionary<string, object> FetchMembers(string action, string headerTag, string currentReport);

        [OperationContract]
        Dictionary<string, object> Filtering(string action, string filterParams, string currentReport);

        [OperationContract]
        Dictionary<string, object> MemberExpanded(string action, bool checkedStatus, string parentNode, string tag, string cubeName, string currentReport);

        [OperationContract]
        void Export(System.IO.Stream stream);
    }
}

{% endhighlight %}

Then, elaborate the service methods inside the main class, found in `PivotGridService.svc.cs` file.

{% highlight c# %}

namespace PivotGridDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class PivotGridService : IPivotGridService
    {
        PivotGrid htmlHelper = new PivotGrid();
        string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        JavaScriptSerializer serializer = new JavaScriptSerializer();

        //This method provides the required information from the server side when initializing the PivotGrid.
        public Dictionary<string, object> InitializeGrid(string action, string gridLayout, bool enablePivotFieldList, object customObject)
        {
            OlapDataManager DataManager = null;
            dynamic customData = serializer.Deserialize<dynamic>(customObject.ToString());
            DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(CreateOlapReport());
            return htmlHelper.GetJsonData(action, DataManager, gridLayout, enablePivotFieldList);
        }

        //This method provides the required information from the server side when drill up/down operation is performed in PivotGrid.
        public Dictionary<string, object> DrillGrid(string action, string cellPosition, string currentReport, string headerInfo, string layout, object customObject)
        {
            dynamic customData = serializer.Deserialize<dynamic>(customObject.ToString());
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
            return htmlHelper.GetJsonData(action, connectionString, DataManager, cellPosition, headerInfo, layout);
        }

        //This method provides the required information from the server side when tree node is dropped in PivotTable Field List.
        public Dictionary<string, object> NodeDropped(string action, string dropType, string nodeInfo, string filterParams, string currentReport)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
            return htmlHelper.GetJsonData(action, DataManager, dropType, nodeInfo, filterParams, true);
        }

        //This method provides the required information from the server side when filtering values in PivotTable Field List.
        public Dictionary<string, object> Filtering(string action, string filterParams, string currentReport)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
            return htmlHelper.GetJsonData(action, DataManager, null, filterParams);
        }

        //This method provides the required information from the server side when opening the editor in PivotTable Field List.
        public Dictionary<string, object> FetchMembers(string action, string headerTag, string currentReport)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
            return htmlHelper.GetJsonData(action, DataManager, null, headerTag);
        }

        //This method provides the required information from the server side when paging is done in PivotGrid.
        public Dictionary<string, object> Paging(string action, string pagingInfo, string currentReport, string gridLayout, object customObject)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(htmlHelper.SetPaging(currentReport, pagingInfo));
            return htmlHelper.GetJsonData(action, DataManager, gridLayout);
        }

        //This method provides the required information from the server side when removing the split button from PivotTable Field List.
        public Dictionary<string, object> RemoveButton(string action, string headerInfo, string currentReport)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
            return htmlHelper.GetJsonData(action, DataManager, null, headerInfo);
        }

        //This method provides the required information from the server side when expanding member in member editor.
        public Dictionary<string, object> MemberExpanded(string action, bool checkedStatus, string parentNode, string tag, string cubeName, string currentReport)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            if (!string.IsNullOrEmpty(currentReport))
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
            return htmlHelper.GetJsonData(action, DataManager, checkedStatus, parentNode, tag, cubeName);
        }

        //This method export PivotGrid to Excel, CSV, Word and PDF.
        public void Export(System.IO.Stream stream)
        {
            System.IO.StreamReader sReader = new System.IO.StreamReader(stream);
            string args = System.Web.HttpContext.Current.Server.UrlDecode(sReader.ReadToEnd());
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            string fileName = "Sample";
            htmlHelper.ExportPivotGrid(DataManager, args, fileName, System.Web.HttpContext.Current.Response);
        }

        //This method carries the information about the default report which when be rendered within PivotGrid initially.
        private OlapReport CreateOlapReport()
        {
            OlapReport olapReport = new OlapReport();
            olapReport.CurrentCubeName = "Adventure Works";

            MeasureElements measureElement = new MeasureElements();
            measureElement.Elements.Add(new MeasureElement { UniqueName = "[Measures].[Internet Sales Amount]" });

            DimensionElement dimensionElementRow = new DimensionElement();
            dimensionElementRow.Name = "Date";
            dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

            DimensionElement dimensionElementColumn = new DimensionElement();
            dimensionElementColumn.Name = "Customer";
            dimensionElementColumn.AddLevel("Customer Geography", "Country");

            olapReport.SeriesElements.Add(dimensionElementRow);
            olapReport.CategoricalElements.Add(dimensionElementColumn);
            olapReport.CategoricalElements.Add(measureElement);

            return olapReport;
        }
    }
}

{% endhighlight %}

**Configuring Web Configuration File**

The services could be exposed through the properties, binding, contract and address by using an endpoint.

* Contract: This property indicates that the contract of the endpoint is exposing. Here you are referring to `IPivotGridService` contract and hence it is `PivotGridDemo.IPivotGridService`.
* Binding: In your application, you use `webHttpBinding` to post and receive the requests and responses between the client-end and the service.
* BehaviorConfiguration: This property contains the name of the behavior to be used in the endpoint

The endpointBehaviors are illustrated as follows

{% highlight xml %}

<system.serviceModel> 
    …… 
    ……
    <services>
        <service name="PivotGridDemo.PivotGridService">
            <endpoint address="" behaviorConfiguration="PivotGridDemo.PivotGridServiceAspNetAjaxBehavior" binding="webHttpBinding" contract="PivotGridDemo.IPivotGridService" /> </service>
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
            <behavior name="PivotGridDemo.PivotGridServiceAspNetAjaxBehavior">
                <enableWebScript /> </behavior>
        </endpointBehaviors>
    </behaviors>
</system.serviceModel>

{% endhighlight %}

N> In this example, **"PivotGridDemo"** indicates the name and root namespace of the Application created in Visual Studio IDE and **"PivotGridService"** indicates the name of the WCF service created.

Now, **PivotGrid** will be rendered with Internet Sales Amount over a period of fiscal years across different customer geographic locations.

![](Getting-Started_images/pivotgrid.png) 

