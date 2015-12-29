---
layout: post
title: Getting Started | OLAPClient | ASP.NET | Syncfusion
description: getting started 
platform: aspnet
control: OLAPClient
documentation: ug
---

# Getting Started

##Creating a simple application with OlapClient

This section covers the information required to create a simple OlapClient bound to OLAP datasource.

N> ASP.NET Web Application will contain a service that transfers data to server-side, processes and returns back to client-side for control rendering and re-rendering. The service utilized for communication could be either WCF or WebAPI based on user requirement.

###Project Initialization
Create a new **ASP.NET Empty Web Application** using Visual Studio IDE and name the project as **“OlapClientDemo”**.

Now add a “Web Form” to the Empty Web Application. For adding a “Web Form”, right-click on the project in Solution Explorer and select **Add > New Item**. In the **Add New Item** window, select “Web Form” and name it as `GettingStarted.aspx` and click “Add”.

To set an appropriate start page, right-click on the **“GettingStarted.aspx”** in Solution Explorer and select **“Set As Start Page”**.

Now add the following dependency libraries as references into your Web Application. In order to add them to your application, right-click on **References** in Solution Explorer and select **Add Reference**. Now in the **Reference Manager** dialog, under **Assemblies > Extension**, the following Syncfusion libraries will be found.  

* Microsoft.AnalysisServices.AdomdClient.dll
* Syncfusion.Compression.Base.dll
* Syncfusion.Linq.Base.dll
* Syncfusion.Olap.Base.dll
* Syncfusion.EJ.dll
* Syncfusion.EJ.Olap.dll
* Syncfusion.XlsIO.Base.dll
* Syncfusion.DocIO.Base.dll
* Syncfusion.Pdf.Base.dll
* System.Data.SqlServerCe.dll (Version: 4.0.0.0).

N> If any version of SQL Server Analysis Service (SSAS) or Microsoft ADOMD.NET utility is installed, then the location of Microsoft.AnalysisServices.AdomdClient library is [system drive:\Program Files (x86)\Microsoft.NET\ADOMD.NET]

###Scripts and CSS Initialization
The scripts and style sheets that are mandatorily required to render OlapClient widget in a Web Application are mentioned in an appropriate order below:

1.	ej.web.all.min.css
2.	jquery-1.10.2.min.js
3.	jquery.easing.1.3.min.js
4.	jquery.globalize.min.js
5.	ej.web.all.min.js

[Click here](http://help.syncfusion.com/js/cdn) to know more about scripts and style sheets available online (CDN Link).

Scripts and style sheets are referred under the <head> tag in **GettingStarted.aspx** page.

{% highlight html %}

<head>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js" type="text/javascript"> </script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js" type="text/javascript"> </script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.globalize.min.js"> </script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"> </script>
</head>

{% endhighlight %}

###Control Initialization

Either drag and drop the **OlapClient** control from the toolbox (under **Syncfusion BI Web** category) or manually define the widget like in the below code sample inside **“GettingStarted.aspx”** page.
 
Once the widget is placed into the web page, add **‘ScriptManager’** next to it in-order to generate appropriate scripts.

{% highlight html %}

<%@ Register Assembly="Syncfusion.EJ.Olap, Version={{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" Namespace="Syncfusion.JavaScript.Web.Olap" TagPrefix="ej" %> 

<html> 
    …… 
    ……

<body>
    <form runat="server">
        <ej:OlapClient ID="OlapClient1" Url="../OlapClient" runat="server"> </ej:OlapClient>
        <asp:ScriptManager ID="ScriptManager1" runat="server"></asp:ScriptManager>
    </form>
</body>

</html>
 
 {% endhighlight %}
 
 The **“Url”** property in OlapClient widget points the service endpoint, where data are processed and fetched in the form of JSON. The services used in OlapClient widget as endpoint are WCF and WebAPI.

N> The above “GettingStarted.aspx” contains WebAPI Url, which is, “../OlapClient”. If WCF service is used as endpoint, the Url would look like “../OlapClientService.svc”.

If you are manually entering the code instead of dragging and dropping the OlapClient widget from toolbox, then you need to register the referenced assemblies in Web.config file.

{% highlight xml %}

<compilation debug="true" targetFramework="4.5">
    <assemblies> 
        …… 
        ……
        <add assembly="Syncfusion.EJ, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.EJ.Olap, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.Linq.Base, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.Olap.Base, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.Compression.Base, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.Pdf.Base, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.XlsIO.Base, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.DocIO.Base, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" /> 
    </assemblies>
</compilation>
    
{% endhighlight %}

###WebAPI

**Adding a WebAPI Controller**

To add a WebAPI controller in an existing Web Application, right-click on the project in Solution Explorer and select **Add > New Item**. In the **Add New Item** window, select **WebAPI Controller Class** and name it as `OlapClientController.cs`, click Add.

Now, WebAPI controller is added into the application successfully with the file **“OlapClientController.cs”**.

N> While adding WebAPI Controller Class, name it with the suffix ‘Controller’ that is mandatory. For example, in this demo the controller is named as “OlapClientController”.

Next, remove all the existing methods such as “Get”, “Post”, “Put” and “Delete” present inside `OlapClientController.cs` file.

{% highlight c# %}

namespace OlapClientDemo
{
    public class OlapClientController: ApiController
    {
    
    }
}

{% endhighlight %}

**Adding the List of Namespaces**

The following are the list of namespaces to be added on top of the main class inside `OlapClientController.cs` file.

{% highlight c# %}

using System;
using System.Collections.Generic;
using System.Data;
using System.Data.SqlServerCe;
using System.Web;
using System.Web.Http;
using Syncfusion.JavaScript.Olap;
using Syncfusion.Olap.Manager;
using Syncfusion.Olap.Reports;
using System.Web.Script.Serialization;
using OLAPUTILS = Syncfusion.JavaScript.Olap;

namespace OlapClientDemo
{
    public class OlapClientController: ApiController
    {
    
    }
}

{% endhighlight %}

**Datasource Initialization**

Now, the connection string to connect OLAP Cube, OlapClient and JavaScriptSerializer instances are created immediately inside the main class in `OlapClientController.cs` file.

{% highlight c# %}

namespace OlapClientDemo
{
    public class OlapClientController: ApiController
    {
        OlapClient olapClientHelper = new OlapClient();
        string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        string conStringforDB = "DataSource=" + HttpContext.Current.Server.MapPath(".").Split(new string[]
        {
            "\\api"
        }, StringSplitOptions.None)[0] + "\\database\\ReportsTable.sdf; Persist Security Info=False", reportTableName = "ReportsTable";
        OlapChart htmlHelper = new OlapChart();
        JavaScriptSerializer serializer = new JavaScriptSerializer();
    }
}

{% endhighlight %}

**Service methods in WebAPI Controller**

Define the service methods inside OlapClientController class, found inside `OlapClientController.cs` file, created while adding WebAPI Controller Class to the Application.

{% highlight c# %}

namespace OlapClientDemo
{
    public class OlapClientController: ApiController
    {
        OlapClient olapClientHelper = new OlapClient();
        string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        string conStringforDB = "DataSource=" + HttpContext.Current.Server.MapPath(".").Split(new string[]
        {
            "\\api"
        }, StringSplitOptions.None)[0] + "\\database\\ReportsTable.sdf; Persist Security Info=False", reportTableName = "ReportsTable";
        OlapChart htmlHelper = new OlapChart();
        JavaScriptSerializer serializer = new JavaScriptSerializer();
        [ActionName("InitializeClient")]
        [HttpPost]
        public Dictionary < string, object > InitializeClient(Dictionary < string, object > jsonResult)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                DataManager.SetCurrentReport(CreateOlapReport());
                return olapClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["clientParams"].ToString());
            }
            [ActionName("InitializeGrid")]
            [HttpPost]
        public Dictionary < string, object > InitializeGrid(Dictionary < string, object > jsonResult)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
                return olapClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["gridLayout"].ToString());
            }
            [ActionName("InitializeChart")]
            [HttpPost]
        public Dictionary < string, object > InitializeChart(Dictionary < string, object > jsonResult)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
                return htmlHelper.GetJsonData(jsonResult["action"].ToString(), DataManager);
            }
            [ActionName("DrillChart")]
            [HttpPost]
        public Dictionary < string, object > DrillChart(Dictionary < string, object > jsonResult)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
                DataManager.Reports = olapClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
                return htmlHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["drilledSeries"].ToString());
            }
            [ActionName("FilterElement")]
            [HttpPost]
        public Dictionary < string, object > FilterElement(Dictionary < string, object > jsonResult)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
                DataManager.Reports = olapClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
                return olapClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["clientParams"].ToString());
            }
            [ActionName("RemoveSplitButton")]
            [HttpPost]
        public Dictionary < string, object > RemoveSplitButton(Dictionary < string, object > jsonResult)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
                DataManager.Reports = olapClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
                return olapClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["clientParams"].ToString());
            }
            [ActionName("FetchMemberTreeNodes")]
            [HttpPost]
        public Dictionary < string, object > FetchMemberTreeNodes(Dictionary < string, object > jsonResult)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
                return olapClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["dimensionName"].ToString());
            }
            [ActionName("DrillGrid")]
            [HttpPost]
        public Dictionary < string, object > DrillGrid(Dictionary < string, object > jsonResult)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
                DataManager.Reports = olapClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
                return olapClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["cellPosition"].ToString(), jsonResult["headerInfo"].ToString(), jsonResult["layout"].ToString());
            }
            [ActionName("NodeDropped")]
            [HttpPost]
        public Dictionary < string, object > NodeDropped(Dictionary < string, object > jsonResult)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
                DataManager.Reports = olapClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
                return olapClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["dropType"].ToString(), jsonResult["nodeInfo"].ToString());
            }
            [ActionName("CubeChanged")]
            [HttpPost]
        public Dictionary < string, object > CubeChanged(Dictionary < string, object > jsonResult)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                return olapClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["cubeName"].ToString(), jsonResult["clientParams"].ToString());
            }
            [ActionName("MeasureGroupChanged")]
            [HttpPost]
        public Dictionary < string, object > MeasureGroupChanged(Dictionary < string, object > jsonResult)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                return olapClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["measureGroupName"].ToString());
            }
            [ActionName("ToolbarOperations")]
            [HttpPost]
        public Dictionary < string, object > ToolbarOperations(Dictionary < string, object > jsonResult)
            {
                var toolbarOperation = "";
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                if (jsonResult["olapReport"] != null && (!string.IsNullOrEmpty(jsonResult["olapReport"].ToString()))) DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
                if (!string.IsNullOrEmpty(jsonResult["clientReports"].ToString())) DataManager.Reports = olapClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
                toolbarOperation = jsonResult["toolbarOperation"] == null ? null : jsonResult["toolbarOperation"].ToString();
                return olapClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, toolbarOperation, jsonResult["clientInfo"].ToString());
            }
            [ActionName("MemberExpanded")]
            [HttpPost]
        public Dictionary < string, object > MemberExpanded(Dictionary < string, object > jsonResult)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                if (!string.IsNullOrEmpty(jsonResult["olapReport"].ToString())) DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
                if (!string.IsNullOrEmpty(jsonResult["clientReports"].ToString())) DataManager.Reports = olapClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
                return olapClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, Convert.ToBoolean(jsonResult["checkedStatus"].ToString()), jsonResult["parentNode"].ToString(), jsonResult["tag"].ToString(), jsonResult["dimensionName"].ToString(), jsonResult["cubeName"].ToString());
            }
            [ActionName("UpdateReport")]
            [HttpPost]
        public Dictionary < string, object > UpdateReport(Dictionary < string, object > jsonResult)
            {
                return olapClientHelper.GetJsonData(jsonResult["action"].ToString(), jsonResult["clientParams"].ToString(), jsonResult["olapReport"].ToString(), jsonResult["clientReports"].ToString());
            }
            [ActionName("SaveReportToDB")]
            [HttpPost]
        public Dictionary < string, object > SaveReportToDB(Dictionary < string, object > jsonResult)
            {
                SqlCeConnection con = new SqlCeConnection()
                {
                    ConnectionString = conStringforDB
                };
                con.Open();
                SqlCeCommand cmd1 = new SqlCeCommand("insert into ReportsTable Values(@ReportName,@Reports)", con);
                cmd1.Parameters.Add("@ReportName", jsonResult["reportName"].ToString());
                cmd1.Parameters.Add("@Reports", OLAPUTILS.Utils.GetReportStream(jsonResult["clientReports"].ToString()).ToArray());
                cmd1.ExecuteNonQuery();
                con.Close();
                return null;
            }
            [ActionName("FetchReportListFromDB")]
            [HttpPost]
        public Dictionary < string, object > FetchReportListFromDB()
            {
                string reportNames = string.Empty;
                foreach(System.Data.DataRow row in GetDataTable().Rows)
                reportNames = reportNames == "" ? (row.ItemArray[0] as string) : reportNames + "__" + (row.ItemArray[0] as string);
                Dictionary < string, object > dictionary = new Dictionary < string, object > ();
                dictionary.Add("ReportNameList", reportNames);
                return dictionary;
            }
            [ActionName("LoadReportFromDB")]
            [HttpPost]
        public Dictionary < string, object > LoadReportFromDB(Dictionary < string, object > jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            var reportString = "";
            foreach(DataRow row in GetDataTable().Rows)
            {
                if ((row.ItemArray[0] as string).Equals(jsonResult["reportName"].ToString()))
                {
                    reportString = OLAPUTILS.Utils.CompressData(row.ItemArray[1] as byte[]);
                    break;
                }
            }
            DataManager.Reports = olapClientHelper.DeserializedReports(reportString);
            DataManager.SetCurrentReport(DataManager.Reports[0]);
            return olapClientHelper.GetJsonData("toolbarOperation", DataManager, "Load Report", jsonResult["reportName"].ToString());
        }
        private DataTable GetDataTable()
            {
                SqlCeConnection con = new SqlCeConnection()
                {
                    ConnectionString = conStringforDB
                };
                con.Open();
                DataSet dSet = new DataSet();
                new SqlCeDataAdapter("Select * from ReportsTable", con).Fill(dSet);
                con.Close();
                return dSet.Tables[0];
            }
            [ActionName("Export")]
            [HttpPost]
        public void Export()
            {
                string args = HttpContext.Current.Request.Form.GetValues(0)[0];
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                string fileName = "Sample";
                olapClientHelper.ExportOlapClient(DataManager, args, fileName, System.Web.HttpContext.Current.Response);
            }
            [ActionName("GetMDXQuery")]
            [HttpPost]
        public string GetMDXQuery(Dictionary < string, object > jsonResult)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
                return DataManager.GetMDXQuery();
            }
            [ActionName("ToggleAxis")]
            [HttpPost]
        public Dictionary < string, object > ToggleAxis(Dictionary < string, object > jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
            DataManager.Reports = olapClientHelper.DeserializedReports(jsonResult["clientReports"].ToString());
            DataManager.ToggleAxis(DataManager.CurrentReport);
            return olapClientHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["clientReports"].ToString());
        }
        private OlapReport CreateOlapReport()
        {
            OlapReport olapReport = new OlapReport()
            {
                Name = "Default Report"
            };
            olapReport.CurrentCubeName = "Adventure Works";
            MeasureElements measureElement = new MeasureElements();
            measureElement.Elements.Add(new MeasureElement
            {
                UniqueName = "[Measures].[Customer Count]"
            });
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

**Configure routing in Global Application Class**

To add a Global.asax, right-click on the project in Solution Explorer and select **Add > New Item**. In the **Add New Item** window, select **Global Application Class** and name it as `Global.asax`, click **Add**. After the addition of **Global.asax** file, immediately add the namespace **“using System.Web.Http;”** and then you can configure routing like in the following code example.

{% highlight c# %}

public class Global: System.Web.HttpApplication
{
    protected void Application_Start(object sender, EventArgs e)
    {
        GlobalConfiguration.Configuration.Routes.MapHttpRoute(name: "DefaultApi", routeTemplate: "{controller}/{action}/{id}", defaults: new
        {
            id = RouteParameter.Optional
        });
        AppDomain.CurrentDomain.SetData("SQLServerCompactEditionUnderWebHosting", true);
    }
}

{% endhighlight %}

Now, OlapClient is rendered with OlapChart and PivotGrid showing Customer Count over a period of fiscal years.

![](Getting-Started_images/OlapClient.png)

###WCF

This section demonstrates the utilization of WCF service as endpoint binding OLAP datasource to a simple OlapClient. For more details on this topic, [click here](http://help.syncfusion.com/aspnet/olapclient/data-binding#wcf).

