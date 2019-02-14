---
layout: post
title: OLAP Connectivity | PivotClient | ASP.NET | Syncfusion
description: olap connectivity
platform: aspnet
control: PivotClient
documentation: ug
---

# Data binding

## Binding pivot client to offline cube

To connect to an OLAP cube available in the local machine, the physical path of the cube should be set in the connection string. The following code sample illustrates this process:

{% highlight c# %}

string connectionString = @"DataSource = system drive:\OfflineCube\Adventure_Works_Ext.cub; Provider = MSOLAP;";
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding pivot client to cube in local SQL server

To connect to an OLAP cube available in the SQL Server Analysis Service of the local machine, the server name and database name should be set in the connection string. If you have any credentials to connect your cube, then set the user ID and password attributes accordingly. The following code sample illustrates this process:

{% highlight c# %}

string connectionString = "Data source=localhost; Initial Catalog=Adventure Works DW;";
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding pivot client to cube in online SQL Server

To connect to an OLAP cube available in the SQL Server Analysis Service in online server through XML/A, the host server link and database name should be set in the connection string. If you have any credentials to connect your cube, then set the user ID and password attributes accordingly. The following code sample illustrates this process:

{% highlight c# %}

string connectionString = "Data Source=https://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
OlapDataManager DataManager = new OlapDataManager(connectionString);

{% endhighlight %}

## Binding pivot client to cube in online Mondrian Server

To connect to an OLAP cube available in the Mondrian Server through XML/A, the host server link and database name should be set in the connection string. If you have any credentials to connect your cube, then set the user ID and password attributes accordingly. The following code sample illustrates this process:

{% highlight c# %}

string connectionString = @"Data Source = https://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;";
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian;

{% endhighlight %}

## Binding pivot client to cube in online Active Pivot Server

{% highlight c# %}

string connectionString = @"Data Source = https://localhost:8080/cva_s/xmla; Initial Catalog = CVAS;";
OlapDataManager DataManager = new OlapDataManager(connectionString);
DataManager.DataProvider.ProviderName=Syncfusion.Olap.DataProvider.Providers.ActivePivot;

{% endhighlight %}

## WCF
**Adding a WCF service**

To add a WCF service in an existing web application, right-click the project in the solution explorer and select **Add > New Item**. In the **Add New Item** window, select WCF Service and name it `OlapService.svc`, and then click Add.

Now, the WCF service is added to the application that comprises the following files. The utilization of these files is explained in the immediate sections.

* OlapService.svc
* OlapService.svc.cs
* IOlapService.cs

**Configuring WCF service class**

Remove the **“DoWork”** method present in both the `OlapService.svc.cs` and `IOlapService.cs` files. Next, add **“AspNetCompatibilityRequirements”** attribute on top of the main class present in the OlapService.svc.cs file and set the **“RequirementsMode”** value to **Allowed**.

{% highlight c# %}

namespace PivotClientDemo
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
* System.Data.SqlServerCe (Version: 4.0.0.0)
* Syncfusion.XlsIO.Base
* Syncfusion.Pdf.Base
* Syncfusion.DocIO.Base
* Syncfusion.EJ
* Syncfusion.EJ.Web
* Syncfusion.EJ.Export
* Syncfusion.EJ.Pivot

**List of namespaces**

Following are the list of namespaces to be added on top of the main class in the `OlapService.svc.cs` file:

{% highlight c# %}

using Syncfusion.JavaScript;
using Syncfusion.Olap.Manager;
using Syncfusion.Olap.Reports;
using System;
using System.Collections.Generic;
using System.Configuration;
using System.Data;
using System.ServiceModel.Activation;
using System.Data.SqlServerCe;
using System.IO;
using System.Linq;
using System.Text;
using System.Web;
using System.Web.Script.Serialization;
using OLAPUTILS = Syncfusion.JavaScript.Olap;

namespace PivotClientDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class OlapService : IOlapService
    {

    }
}

{% endhighlight %}


**Data source initialization**

Now, the connection string to connect the OLAP cube, the pivot client and JavaScriptSerializer instances is created immediately in the main class of the `OlapService.svc.cs` file.

{% highlight c# %}

namespace PivotClientDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class OlapService: IOlapService
    {
        PivotClient pivotClientHelper = new PivotClient();
        PivotTreeMap treemapHelper = new PivotTreeMap();
        PivotChart chartHelper = new PivotChart();
        JavaScriptSerializer serializer = new JavaScriptSerializer();
        string connectionString = "Data Source=https://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        string conStringforDB = "";//Enter appropriate connection string to connect database for saving and loading operation of reports
        //Other codes

    }
}

{% endhighlight %}

**Service methods in WCF service**

First, declare the service methods in the **IOlapService** interface, find in the `IOlapService.cs` file which was created while adding the WCF Service to the application.

{% highlight c# %}

namespace PivotClientDemo
{
    [ServiceContract]
    public interface IOlapService
    {
        [OperationContract]
        Dictionary<string, object> InitializeClient(string action, string customObject, string clientParams);
        [OperationContract]
        Dictionary<string, object> FetchMemberTreeNodes(string action, string dimensionName, string olapReport);
        [OperationContract]
        Dictionary<string, object> InitializeChart(string action, string currentReport, string customObject);
        [OperationContract]
        Dictionary<string, object> InitializeTreeMap(string action, string currentReport, string customObject);
        [OperationContract]
        Dictionary<string, object> DrillChart(string action, string drilledSeries, string olapReport, string clientReports);
        [OperationContract]
        Dictionary<string, object> DrillTreeMap(string action, string drillInfo, string olapReport, string clientReports);
        [OperationContract]
        Dictionary<string, object> InitializeGrid(string action, string currentReport, string gridLayout, string customObject);
        [OperationContract]
        Dictionary<string, object> DrillGrid(string action, string cellPosition, string currentReport, string clientReports, string headerInfo, string layout);
        [OperationContract]
        Dictionary<string, object> FilterElement(string action, string clientParams, string olapReport, string clientReports);
        [OperationContract]
        Dictionary<string, object> RemoveSplitButton(string action, string clientParams, string olapReport, string clientReports);
        [OperationContract]
        Dictionary<string, object> NodeDropped(string action, string dropType, string nodeInfo, string olapReport, string clientReports);
        [OperationContract]
        Dictionary<string, object> CubeChanged(string action, string cubeName, string clientParams,string olapReport, string clientReports);
        [OperationContract]
        Dictionary<string, object> MeasureGroupChanged(string action, string measureGroupName);
        [OperationContract]
        Dictionary<string, object> ToolbarOperations(string action, string toolbarOperation, string clientInfo, string olapReport, string clientReports);
        [OperationContract]
        Dictionary<string, object> UpdateReport(string action, string clientParams, string olapReport, string clientReports);
        [OperationContract]
        Dictionary<string, object> SaveReportToDB(string reportName, string operationalMode, string analysisMode, string olapReport, string clientReports);
        [OperationContract]
        Dictionary<string, object> RemoveReportFromDB(string reportName, string operationalMode, string analysisMode);
        [OperationContract]
        Dictionary<string, object> RenameReportInDB(string selectedReport, string renameReport, string operationalMode, string analysisMode);
        [OperationContract]
        Dictionary<string, object> LoadReportFromDB(string reportName, string operationalMode, string analysisMode, string olapReport, string clientReports);
        [OperationContract]
        Dictionary<string, object> FetchReportListFromDB(string action, string operationalMode, string analysisMode);
        [OperationContract]
        Dictionary<string, object> MemberExpanded(string action, bool checkedStatus, string parentNode, string tag, string dimensionName, string cubeName, string olapReport, string clientReports);
        [OperationContract]
        void Export(System.IO.Stream stream);
        [OperationContract]
        string GetMDXQuery(string olapReport);
        [OperationContract]
        Dictionary<string, object> ToggleAxis(string action, string currentReport, string clientReports);
    }
}

{% endhighlight %}

Then, elaborate the service methods in the main class that is found in the `OlapService.svc.cs` file.

{% highlight c# %}

namespace PivotClientDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class OlapService : IOlapService
    {
        PivotClient pivotClientHelper = new PivotClient();
        PivotTreeMap treemapHelper = new PivotTreeMap();
        PivotChart chartHelper = new PivotChart();
        JavaScriptSerializer serializer = new JavaScriptSerializer();
        string connectionString = "Data Source=https://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        string conStringforDB = "";//Enter appropriate connection string to connect database for saving and loading operation of reports
        public Dictionary<string, object> InitializeClient(string action, string customObject, string clientParams)
        {
            OlapDataManager DataManager = null;
            DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(CreateOlapReport());
            return pivotClientHelper.GetJsonData(action, DataManager, clientParams);
        }

        public Dictionary<string, object> InitializeGrid(string action, string currentReport, string gridLayout, string customObject)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
            return pivotClientHelper.GetJsonData(action, DataManager, gridLayout);
        }

        public Dictionary<string, object> InitializeChart(string action, string currentReport, string customObject)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
            return chartHelper.GetJsonData(action, DataManager);
        }

        public Dictionary<string, object> InitializeTreeMap(string action, string currentReport, string customObject)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
            return treemapHelper.GetJsonData(action, DataManager);
        }

        public Dictionary<string, object> DrillChart(string action, string drilledSeries, string olapReport, string clientReports)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(olapReport));
            DataManager.Reports = pivotClientHelper.DeserializedReports(clientReports);
            return chartHelper.GetJsonData(action, DataManager, drilledSeries);
        }

        public Dictionary<string, object> DrillTreeMap(string action, string drillInfo, string olapReport, string clientReports)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(olapReport));
            DataManager.Reports = pivotClientHelper.DeserializedReports(clientReports);
            return treemapHelper.GetJsonData(action, DataManager, drillInfo);
        }

        public Dictionary<string, object> FilterElement(string action, string clientParams, string olapReport, string clientReports)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(olapReport));
            DataManager.Reports = pivotClientHelper.DeserializedReports(clientReports);
            return pivotClientHelper.GetJsonData(action, DataManager, clientParams);
        }

        public Dictionary<string, object> RemoveSplitButton(string action, string clientParams, string olapReport, string clientReports)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(olapReport));
            DataManager.Reports = pivotClientHelper.DeserializedReports(clientReports);
            return pivotClientHelper.GetJsonData(action, DataManager, clientParams);
        }

        public Dictionary<string, object> FetchMemberTreeNodes(string action, string dimensionName, string olapReport)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(olapReport));
            return pivotClientHelper.GetJsonData(action, DataManager, dimensionName);
        }

        public Dictionary<string, object> DrillGrid(string action, string cellPosition, string currentReport,string clientReports, string headerInfo, string layout)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
            DataManager.Reports = pivotClientHelper.DeserializedReports(clientReports);
            return pivotClientHelper.GetJsonData(action, DataManager, cellPosition, headerInfo, layout);
        }

        public Dictionary<string, object> NodeDropped(string action, string dropType, string nodeInfo, string olapReport, string clientReports)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(olapReport));
            DataManager.Reports = pivotClientHelper.DeserializedReports(clientReports);
            return pivotClientHelper.GetJsonData(action, DataManager, dropType, nodeInfo);
        }

        public Dictionary<string, object> CubeChanged(string action, string cubeName, string clientParams, string olapReport, string clientReports)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            if (olapReport != "")
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(olapReport));
            if (clientReports != "")
                DataManager.Reports = pivotClientHelper.DeserializedReports(clientReports);
            return pivotClientHelper.GetJsonData(action, DataManager, cubeName, clientParams);
        }

        public Dictionary<string, object> MeasureGroupChanged(string action, string measureGroupName)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            return pivotClientHelper.GetJsonData(action, DataManager, measureGroupName);
        }

        public Dictionary<string, object> ToolbarOperations(string action, string toolbarOperation, string clientInfo, string olapReport, string clientReports)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            if (!string.IsNullOrEmpty(olapReport))
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(olapReport));
            if (!string.IsNullOrEmpty(clientReports))
                DataManager.Reports = pivotClientHelper.DeserializedReports(clientReports);
            return pivotClientHelper.GetJsonData(action, DataManager, toolbarOperation, clientInfo);
        }
        public Dictionary<string, object> MemberExpanded(string action, bool checkedStatus, string parentNode, string tag, string dimensionName, string cubeName, string olapReport, string clientReports)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            if (!string.IsNullOrEmpty(olapReport))
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(olapReport));
            if (!string.IsNullOrEmpty(clientReports))
                DataManager.Reports = pivotClientHelper.DeserializedReports(clientReports);
            return pivotClientHelper.GetJsonData(action, DataManager, checkedStatus, parentNode, tag, dimensionName, cubeName);
        }

        public Dictionary<string, object> UpdateReport(string action, string clientParams, string olapReport, string clientReports)
        {
            return pivotClientHelper.GetJsonData(action, clientParams, olapReport, clientReports);
        }

        public Dictionary<string, object> SaveReportToDB(string reportName, string operationalMode, string analysisMode, string olapReport, string clientReports)
        {
            reportName = reportName + "##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower();
            bool isDuplicate = true;
            SqlCeConnection con = new SqlCeConnection() { ConnectionString = conStringforDB };
            con.Open();
            SqlCeCommand cmd1 = null;
            foreach (DataRow row in GetDataTable().Rows)
            {
                if ((row.ItemArray[0] as string).Equals(reportName))
                {
                    isDuplicate = false;
                    cmd1 = new SqlCeCommand("update ReportsTable set Report=@Reports where ReportName like @ReportName", con);
                }
            }
            if (isDuplicate)
            {
                cmd1 = new SqlCeCommand("insert into ReportsTable Values(@ReportName,@Reports)", con);
            }
            cmd1.Parameters.Add("@ReportName", reportName);
            cmd1.Parameters.Add("@Reports", Encoding.UTF8.GetBytes(clientReports).ToArray());
            cmd1.ExecuteNonQuery();
            con.Close();
            Dictionary<string, object> dictionary = new Dictionary<string, object>();
            dictionary.Add("CurrentAction", "Save");
            return dictionary;
        }

        public Dictionary<string, object> RemoveReportFromDB(string reportName, string operationalMode, string analysisMode)
        {
            SqlCeConnection con = new SqlCeConnection() { ConnectionString = conStringforDB };
            con.Open();
            reportName = reportName + "##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower();
            SqlCeCommand cmd1 = null;
            foreach (DataRow row in GetDataTable().Rows)
            {
                if ((row.ItemArray[0] as string).Equals(reportName))
                {
                    cmd1 = new SqlCeCommand("DELETE FROM ReportsTable WHERE ReportName LIKE '%" + reportName + "%'", con);
                }
            }
            cmd1.ExecuteNonQuery();
            con.Close();
            Dictionary<string, object> dictionary = new Dictionary<string, object>();
            dictionary.Add("CurrentAction", "Remove");
            return dictionary;
        }

        public Dictionary<string, object> RenameReportInDB(string selectedReport, string renameReport, string operationalMode, string analysisMode)
        {
            SqlCeConnection con = new SqlCeConnection() { ConnectionString = conStringforDB };
            con.Open();
            selectedReport = selectedReport + "##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower();
            renameReport = renameReport + "##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower();
            SqlCeCommand cmd1 = null;
            foreach (DataRow row in GetDataTable().Rows)
            {
                if ((row.ItemArray[0] as string).Equals(selectedReport))
                {
                    cmd1 = new SqlCeCommand("update ReportsTable set ReportName=@RenameReport where ReportName like '%" + selectedReport + "%'", con);
                }
            }
            cmd1.Parameters.Add("@RenameReport", renameReport);
            cmd1.ExecuteNonQuery();
            con.Close();
            Dictionary<string, object> dictionary = new Dictionary<string, object>();
            dictionary.Add("CurrentAction", "Rename");
            return dictionary;
        }

        public Dictionary<string, object> FetchReportListFromDB(string action, string operationalMode, string analysisMode)
        {
            string reportNames = string.Empty;
            string currentRptName = string.Empty;
            foreach (System.Data.DataRow row in GetDataTable().Rows)
            {
                currentRptName = (row.ItemArray[0] as string);
                if (currentRptName.IndexOf("##" + operationalMode + "#>>#" + analysisMode) >= 0)
                {
                    currentRptName = currentRptName.Replace("##" + operationalMode + "#>>#" + analysisMode, "");
                    reportNames = reportNames == "" ? currentRptName : reportNames + "__" + currentRptName;
                }
            }
            Dictionary<string, object> dictionary = new Dictionary<string, object>();
            dictionary.Add("ReportNameList", reportNames);
            dictionary.Add("action", action);
            return dictionary;
        }

        public Dictionary<string, object> LoadReportFromDB(string reportName, string operationalMode, string analysisMode, string olapReport, string clientReports)
        {
            PivotReport report = new PivotReport();
            Dictionary<string, object> dictionary = new Dictionary<string, object>();
            string currentRptName = string.Empty;
            foreach (DataRow row in GetDataTable().Rows)
            {
                currentRptName = (row.ItemArray[0] as string).Replace("##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower(), "");
                if (currentRptName.Equals(reportName))
                {
                    byte[] reportByte = new byte[2 * 1024];
                    reportByte = (row.ItemArray[1] as byte[]);
                    if (operationalMode.ToLower() == "servermode" && analysisMode == "olap")
                    {
                        var repCol = Encoding.UTF8.GetString(reportByte);
                        OlapDataManager DataManager = new OlapDataManager(connectionString);
                        if (repCol.IndexOf("<?xml version") == 0)
                        {
                            var reportString = "";
                            reportString = Syncfusion.JavaScript.Olap.Utils.CompressData(row.ItemArray[1] as byte[]);
                            DataManager.Reports = pivotClientHelper.DeserializedReports(reportString);
                            DataManager.SetCurrentReport(DataManager.Reports[0]);
                            return pivotClientHelper.GetJsonData("toolbarOperation", DataManager, "Load Report", reportName);
                        }
                        else
                        {
                            dynamic customData = serializer.Deserialize<dynamic>(repCol.ToString());
                            DataManager.Reports = pivotClientHelper.DeserializedReports(customData[customData[customData.Length - 1]["cubeIndex"]]["Reports"]);
                            DataManager.SetCurrentReport(DataManager.Reports[customData[customData[customData.Length - 1]["cubeIndex"]]["ReportIndex"]]);
                            dictionary = pivotClientHelper.GetJsonData("toolbarOperation", DataManager, "Load Report", reportName);
                            dictionary.Add("Collection", repCol);
                        }
                    }
                }
            }
            return dictionary;
        }

        private DataTable GetDataTable()
        {
            SqlCeConnection con = new SqlCeConnection() { ConnectionString = conStringforDB };
            con.Open();
            DataSet dSet = new DataSet();
            new SqlCeDataAdapter("Select * from ReportsTable", con).Fill(dSet);
            con.Close();
            return dSet.Tables[0];
        }

        public void Export(Stream stream)
        {
            System.IO.StreamReader sReader = new System.IO.StreamReader(stream);
            string args = System.Web.HttpContext.Current.Server.UrlDecode(sReader.ReadToEnd()).Remove(0, 5);
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            string fileName = "Sample";
            pivotClientHelper.ExportPivotClient(DataManager, args, fileName, System.Web.HttpContext.Current.Response);
        }

        public string GetMDXQuery(string olapReport)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(olapReport));
            return DataManager.GetMDXQuery();
        }

        public Dictionary<string, object> ToggleAxis(string action, string currentReport, string clientReports)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(currentReport));
            DataManager.Reports = pivotClientHelper.DeserializedReports(clientReports);
            DataManager.ToggleAxis(DataManager.CurrentReport);
            return pivotClientHelper.GetJsonData(action, DataManager, clientReports);
        }

        private OlapReport CreateOlapReport()
        {
            OlapReport olapReport = new OlapReport() { Name = "Default Report" };
            olapReport.CurrentCubeName = "Adventure Works";

            MeasureElements measureElement = new MeasureElements();
            measureElement.Elements.Add(new MeasureElement { UniqueName = "[Measures].[Customer Count]" });

            DimensionElement dimensionElementRow = new DimensionElement();
            dimensionElementRow.Name = "Date";
            dimensionElementRow.AddLevel("Fiscal", "Fiscal Year");

            olapReport.SeriesElements.Add(dimensionElementRow);
            olapReport.CategoricalElements.Add(measureElement);

            return olapReport;
        }
    }
}

{% endhighlight %}

**Configuring web configuration file**

The services can be exposed through the properties such as binding, contract, and address by using an endpoint.

* Contract: This property indicates that the contract of the endpoint is exposed. Refer to the `IOlapService` contract, and it is written as `PivotClientDemo.IOlapService`.
* Binding: In your application, you can use `webHttpBinding` to post and receive requests and responses between the client-end and the service.
* BehaviorConfiguration: This property contains the name of the behavior to be used in the endpoint.

The endpointBehaviors are illustrated as follows:

{% highlight xml %}

<system.serviceModel>
    ……
    ……
    <services>
        <service name="PivotClientDemo.OlapService">
            <endpoint address="" behaviorConfiguration="PivotClientDemo.OlapServiceAspNetAjaxBehavior" binding="webHttpBinding" contract="PivotClientDemo.IOlapService" /> </service>
    </services>
</system.serviceModel>

{% endhighlight %}

The endpointBehaviors contain all behaviors for an endpoint. You can link each endpoint to the respective behavior only by using this name property.

{% highlight xml %}

<system.serviceModel>
    ……
    ……
    <behaviors>
        <endpointBehaviors>
            <behavior name="PivotClientDemo.OlapServiceAspNetAjaxBehavior">
                <enableWebScript /> </behavior>
        </endpointBehaviors>
    </behaviors>
</system.serviceModel>

{% endhighlight %}

N> In this example, the **"PivotClientDemo"** indicates the name and root namespace of the application created in the Visual Studio IDE and **"OlapService"** indicates the name of the created WCF service.

Now, the **pivot client** is rendered with pivot chart and pivot grid showing customer count over a period of fiscal years.

![ASP NET pivot client control with OLAP server mode](Getting-Started_images/olapwebapi.png)

