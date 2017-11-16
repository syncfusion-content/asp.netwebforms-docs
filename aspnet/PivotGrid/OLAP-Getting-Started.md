---
layout: post
title: OLAP Getting Started | PivotGrid | ASP.NET | Syncfusion
description: olap getting started
platform: aspnet
control: PivotGrid
documentation: ug
---


# Getting Started

## Creating a simple application with PivotGrid and OLAP datasource (Client Mode)

This section covers the information that you need to know to populate a simple PivotGrid with OLAP data completely on the client-side.

### Project Initialization

Create a new **ASP.NET Empty Web Application** using Visual Studio IDE and name the project as **“PivotGridDemo”**.

Now add a “Web Form” to the Empty Web Application. For adding a “Web Form”, right-click on the project in Solution Explorer and select **Add > New Item**. In the **Add New Item** window, select “Web Form” and name it as `GettingStarted.aspx` and click “Add”.

To set an appropriate start page, right-click on the **“GettingStarted.aspx”** in Solution Explorer and select **“Set As Start Page”**.  

Now add the following dependency libraries as references into your Web Application. In order to add them to your application, right-click on **References** in Solution Explorer and select Add Reference. Now in the **Reference Manager** dialog, under **Assemblies > Extension**, the following Syncfusion libraries will be found.

* Syncfusion.EJ
* Syncfusion.EJ.Export
* Syncfusion.EJ.Pivot

Register the referenced assemblies in Web.config files available at the root of the application.

{% highlight xml %}

<compilation debug="true" targetFramework="4.5">
    <assemblies> 
        ……
        ……
        <add assembly="Syncfusion.EJ, Version= {{ site.45esreleaseversion}}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.EJ.Pivot, Version= {{ site.45esreleaseversion}}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.EJ.Export, Version= {{ site.45esreleaseversion}}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />            

    </assemblies>
</compilation>
{% endhighlight %}

### Scripts and CSS References  

Create a GettingStarted.aspx page and scripts and style sheets that are mandatorily required to render PivotGrid control in a Web Application are mentioned in an appropriate order below:

1. ej.web.all.min.css
2. jQuery-3.0.0.min.js
3. ej.web.all.min.js

Scripts and style sheets are referred under the <head> tag in GettingStarted.aspx page.

{% highlight html %}    

<head>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" type="text/css" />
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js" type="text/javascript"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js" type="text/javascript"></script>
    
</head>    

{% endhighlight %}

### Initialize PivotGrid

Either drag and drop the PivotGrid control from the toolbox (under Syncfusion BI Web category) or manually define the control like in the below code sample inside "GettingStarted.aspx" page.

{% highlight html %}

<%@ Register Assembly="Syncfusion.EJ.Pivot" Namespace="Syncfusion.JavaScript.Web" TagPrefix="ej" %>
<%@ Register Assembly="Syncfusion.EJ.Pivot" Namespace="Syncfusion.JavaScript.Models" TagPrefix="ej" %>

<html> 
    …… 
    ……

<body>
    <form runat="server">
        <ej:PivotGrid ID="PivotGrid1" runat="server" ClientIDMode="Static">
        </ej:PivotGrid>
        <asp:ScriptManager ID="ScriptManager1" runat="server"></asp:ScriptManager>
    </form>
</body>

</html>

{% endhighlight %}

### Populate PivotGrid with dataSource

Initializes the OLAP datasource for PivotGrid control as shown below.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    <DataSource Catalog="Adventure Works DW 2008 SE" Cube="Adventure Works" Data="http://bi.syncfusion.com/olap/msmdpump.dll">
        <Rows>
            <ej:Field FieldName="[Date].[Fiscal]"></ej:Field>
        </Rows>
        <Columns>
            <ej:Field FieldName="[Customer].[Customer Geography]"></ej:Field>
        </Columns>
        <Values>
            <ej:Field Axis="Column">
                <Measures>
                    <ej:MeasuresItems FieldName="[Measures].[Internet Sales Amount]" />
                </Measures>
            </ej:Field>
        </Values>
    </DataSource>
</ej:PivotGrid>
<asp:ScriptManager ID="ScriptManager1" runat="server"></asp:ScriptManager>
     
{% endhighlight %}

The above code will generate a simple PivotGrid with "Fiscal" field in Row, "Customer Geography" field in Column and "Internet Sales Amount" field in Value section.

![](Getting-Started_images/OlapClientside.png)


## Creating a simple application PivotGrid and OLAP datasource (Server Mode)

This section covers the information required to create a simple PivotGrid bound to OLAP datasource. 

N> ASP.NET MVC Web Application will contain a service that transfers data to server-side, processes and returns back to client-side for control rendering and re-rendering. The service utilized for communication could be either WCF or WebAPI based on user requirement.

### Project Initialization

Create a new **ASP.NET Empty Web Application** using Visual Studio IDE and name the project as **“PivotGridDemo”**.

Now add a "Web Form" to the Empty Web Application. For adding a "Web Form", right-click on the project in Solution Explorer and select **Add > New Item**. In the **Add New Item** window, select "Web Form" and name it as `GettingStarted.aspx` and click **"Add"**.

To set an appropriate start page, right-click on the **"GettingStarted.aspx"** in Solution Explorer and select **"Set As Start Page"**.

Now add the following dependency libraries as references into your Web Application. In order to add them to your application, right-click on **References** in Solution Explorer and select **Add Reference**. Now in the **Reference Manager** dialog, under **Assemblies > Extension**, the following Syncfusion libraries will be found.  

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
* Syncfusion.EJ.Export
* Syncfusion.EJ.Pivot
* Syncfusion.EJ.Web

### Scripts and CSS Initialization

The scripts and style sheets that are mandatorily required to render PivotGrid control in a Web Application are mentioned in an appropriate order below:

1. ej.web.all.min.css
2. jQuery-3.0.0.min.js
3. ej.web.all.min.js

[Click here](http://help.syncfusion.com/js/cdn) to know more about scripts and style sheets available online (CDN Link).

Scripts and style sheets are referred under the <head> tag in **GettingStarted.aspx** page.

{% highlight html %}

<head>
    <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" type="text/css" />
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-3.0.0.min.js" type="text/javascript"></script>
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js" type="text/javascript"></script>
</head>

{% endhighlight %}

### Control Initialization

Either drag and drop the **PivotGrid** control from the toolbox (under **Syncfusion BI Web** category) or manually define the control like in the below code sample inside **"GettingStarted.aspx"** page.
 
Once the control is placed into the web page, add **'ScriptManager'** next to it in-order to generate appropriate scripts.

{% highlight html %}

<%@ Register Assembly="Syncfusion.EJ.Pivot, Version={{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" Namespace="Syncfusion.JavaScript.Web" TagPrefix="ej" %> 

<html> 
    …… 
    ……

<body>
    <form runat="server">
        <ej:PivotGrid ID="PivotGrid1" Url="/Olap" runat="server" ClientIDMode="Static"></ej:PivotGrid>
        <asp:ScriptManager ID="ScriptManager1" runat="server"></asp:ScriptManager>
    </form>
</body>

</html>

{% endhighlight %}

The **“Url”** property in PivotGrid control points the service endpoint, where data are processed and fetched in the form of JSON. The services used in PivotGrid control as endpoint are WCF and WebAPI.

N> The above “GettingStarted.aspx” contains WebAPI URL, which is “/Olap”. If WCF service is used as endpoint, the URL would look like “/OlapService.svc”.

If you are manually entering the code instead of drag and drop operation from toolbox, then you need to register the referenced assemblies in Web.config file. 


{% highlight xml %}

<compilation debug="true" targetFramework="4.5">
    <assemblies> 
        …… 
        ……
        <add assembly="Syncfusion.EJ, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.EJ.Web, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.EJ.Pivot, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.Compression.Base, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.Linq.Base, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.Olap.Base, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.PivotAnalysis.Base, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.Pdf.Base, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.XlsIO.Base, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
        <add assembly="Syncfusion.DocIO.Base, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" /> 
    
    </assemblies>
</compilation>
    
{% endhighlight %}

### WebAPI

**Adding a WebAPI Controller**

To add a WebAPI controller in an existing Web Application, right-click on the project in Solution Explorer and select **Add > New Item**. In the **Add New Item** window, select **WebAPI Controller Class** and name it as `OlapController.cs`, click Add.

Now, WebAPI controller is added to the application successfully containing the file **“OlapController.cs”**.

N> While adding WebAPI Controller Class, name it with the suffix 'Controller' that is mandatory. For example, in this demo the controller is named as "OlapController".

Next, remove all the existing methods such as "Get", "Post", "Put" and "Delete" present inside `OlapController.cs` file.

{% highlight c# %}

namespace PivotGridDemo
{
    public class OlapController : ApiController
    {
        
    }
}

{% endhighlight %}

**Adding the List of Namespaces**

The following are the list of namespaces to be added on top of the main class inside `OlapController.cs` file.

{% highlight c# %}

using Syncfusion.Olap.Manager;
using Syncfusion.Olap.Reports;
using System;
using System.Collections.Generic;
using System.Configuration;
using System.Linq;
using System.Web.Http;
using System.Web.Script.Serialization;
using Syncfusion.JavaScript.Olap;
using System.Web;
using System.Data.SqlServerCe;
using OLAPUTILS = Syncfusion.JavaScript.Olap;
using System.Data;
using System.Text;

namespace PivotGridDemo
{
    public class OlapController: ApiController
    {
    
    }
}

{% endhighlight %}

**Datasource Initialization**

Now, the connection string to connect OLAP Cube, PivotGrid and JavaScriptSerializer instances are created immediately inside the main class in OlapController.cs file.

{% highlight c# %}

namespace PivotGridDemo
{
    public class OlapController : ApiController
    {
        Syncfusion.JavaScript.PivotGrid htmlHelper = new Syncfusion.JavaScript.PivotGrid();
        static int cultureIDInfoval = 1033; 
        string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        JavaScriptSerializer serializer = new JavaScriptSerializer();
        string conStringforDB = ""; //Enter appropriate connection string to connect database for saving and loading operation of reports
        //Other codes
    }
}

{% endhighlight %}

**Service methods in WebAPI Controller**

Define the service methods inside OlapController class, found inside `OlapController.cs` file, created while adding WebAPI Controller Class to the Application.

{% highlight c# %}

namespace PivotGridDemo
{
    public class OlapController : ApiController
    {
        Syncfusion.JavaScript.PivotGrid htmlHelper = new Syncfusion.JavaScript.PivotGrid();
        static int cultureIDInfoval = 1033; 
        string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        JavaScriptSerializer serializer = new JavaScriptSerializer();
        string conStringforDB = ""; //Enter appropriate connection string to connect database for saving and loading operation of reports

        [System.Web.Http.ActionName("InitializeGrid")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> InitializeOlapGrid(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = null;
            DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(CreateOlapReport());
            DataManager.OverrideDefaultFormatStrings = true;
            return htmlHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult.ContainsKey("gridLayout") ? jsonResult["gridLayout"].ToString() : null, Convert.ToBoolean(jsonResult["enablePivotFieldList"].ToString()));
        }

        [System.Web.Http.ActionName("DrillGrid")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> DrillGrid(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
            return htmlHelper.GetJsonData(jsonResult["action"].ToString(), connectionString, DataManager, jsonResult["cellPosition"].ToString(), jsonResult["headerInfo"].ToString(), jsonResult["layout"].ToString());
        }

        [System.Web.Http.ActionName("NodeDropped")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> NodeDropped(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
            return htmlHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["dropType"].ToString(), jsonResult["nodeInfo"].ToString(), jsonResult.ContainsKey("filterParams") ? jsonResult["filterParams"].ToString() : null, jsonResult["gridLayout"].ToString(), true);
        }

        [System.Web.Http.ActionName("Filtering")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> Filtering(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
            return htmlHelper.GetJsonData(jsonResult["action"].ToString(), connectionString, DataManager, null, jsonResult["filterParams"].ToString(), jsonResult["gridLayout"].ToString());
        }

        [System.Web.Http.ActionName("FetchMembers")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> FetchMembers(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
            return htmlHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, null, jsonResult["headerTag"].ToString());
        }

        [System.Web.Http.ActionName("RemoveButton")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> RemoveButton(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
            return htmlHelper.GetJsonData(jsonResult["action"].ToString(), connectionString, DataManager, null, jsonResult["headerInfo"].ToString(), jsonResult["gridLayout"].ToString());
        }

        [System.Web.Http.ActionName("MemberExpanded")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> MemberExpanded(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            if (!string.IsNullOrEmpty(jsonResult["currentReport"].ToString()))
                DataManager.SetCurrentReport(Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
            return htmlHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, Convert.ToBoolean(jsonResult["checkedStatus"].ToString()), jsonResult["parentNode"].ToString(), jsonResult["tag"].ToString(), jsonResult["cubeName"].ToString());
        }

        [System.Web.Http.ActionName("Export")]
        [System.Web.Http.HttpPost]
        public void Export()
        {
            string args = HttpContext.Current.Request.Form.GetValues(0)[0];
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            string fileName = "Sample";
            htmlHelper.ExportPivotGrid(DataManager, args, fileName, System.Web.HttpContext.Current.Response);
        }

        [System.Web.Http.ActionName("SaveReport")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> SaveReport(Dictionary<string, object> jsonResult)
        {
            string mode = jsonResult["operationalMode"].ToString();
            bool isDuplicate = true;
            SqlCeConnection con = new SqlCeConnection() { ConnectionString = conStringforDB };
            con.Open();
            SqlCeCommand cmd1 = null;
            foreach (DataRow row in GetDataTable().Rows)
            {
                if ((row.ItemArray[0] as string).Equals(jsonResult["reportName"].ToString()))
                {
                    isDuplicate = false;
                    cmd1 = new SqlCeCommand("update ReportsTable set Report=@Reports where ReportName like @ReportName", con);
                }
            }
            if (isDuplicate)
            {
                cmd1 = new SqlCeCommand("insert into ReportsTable Values(@ReportName,@Reports)", con);
            }
            cmd1.Parameters.Add("@ReportName", jsonResult["reportName"].ToString());
            if (mode == "clientMode")
                cmd1.Parameters.Add("@Reports", Encoding.UTF8.GetBytes(jsonResult["clientReports"].ToString()).ToArray());
            else if (mode == "serverMode")
                cmd1.Parameters.Add("@Reports", OLAPUTILS.Utils.GetReportStream(jsonResult["clientReports"].ToString()).ToArray());
            cmd1.ExecuteNonQuery();
            con.Close();
            return null;
        }


        [System.Web.Http.ActionName("LoadReportFromDB")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> LoadReportFromDB(Dictionary<string, object> jsonResult)
        {
            string mode = jsonResult["operationalMode"].ToString();
            byte[] reportString = new byte[4 * 1024];
            var reports = "";
            Dictionary<string, object> dictionary = new Dictionary<string, object>();
            if (mode == "serverMode" && jsonResult.ContainsKey("clientReports"))
            {
                reports = jsonResult["clientReports"].ToString();
            }
            else
            {
                foreach (DataRow row in GetDataTable().Rows)
                {
                    if ((row.ItemArray[0] as string).Equals(jsonResult["reportName"].ToString()))
                    {
                        if (mode == "clientMode")
                        {
                            reportString = row.ItemArray[1] as byte[];
                            dictionary.Add("report", Encoding.UTF8.GetString(reportString));
                            break;
                        }
                        else if (mode == "serverMode")
                        {
                            reports = OLAPUTILS.Utils.CompressData(row.ItemArray[1] as byte[]);
                            break;
                        }
                    }
                }
            }
            if (reports != "")
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                dynamic customData = serializer.Deserialize<dynamic>(jsonResult["customObject"].ToString());
                var cultureIDInfo = new System.Globalization.CultureInfo(("en-US")).LCID;
                if (customData is Dictionary<string, object> && customData.ContainsKey("Language"))
                {
                    cultureIDInfo = new System.Globalization.CultureInfo((customData["Language"])).LCID;
                }
                connectionString = connectionString.Replace("" + cultureIDInfoval + "", "" + cultureIDInfo + "");
                cultureIDInfoval = cultureIDInfo;
                DataManager.Culture = new System.Globalization.CultureInfo((cultureIDInfo));
                DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(reports));
                DataManager.OverrideDefaultFormatStrings = true;
                dictionary = htmlHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["gridLayout"].ToString(), Convert.ToBoolean(jsonResult["enablePivotFieldList"].ToString()));
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


        [System.Web.Http.ActionName("DeferUpdate")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> DeferUpdate(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(Utils.DeserializeOlapReport(jsonResult["currentReport"].ToString()));
            return htmlHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, null, jsonResult["filterParams"].ToString());
        }

        [System.Web.Http.ActionName("Paging")]
        [System.Web.Http.HttpPost]
        public Dictionary<string, object> Paging(Dictionary<string, object> jsonResult)
        {
            OlapDataManager DataManager = new OlapDataManager(connectionString);
            DataManager.SetCurrentReport(htmlHelper.SetPaging(jsonResult["currentReport"].ToString(), jsonResult["pagingInfo"].ToString()));
            return htmlHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["layout"].ToString());
        }

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

**Configure routing in Global Application Class**

To add a Global.asax, right-click on the project in Solution Explorer and select **Add > New Item**. In the **Add New Item** window, select **Global Application Class** and name it as `Global.asax`, click **Add**. After the addition of **Global.asax** file, immediately add the namespace **“using System.Web.Http;”** and then you can configure routing like in the following code example.

{% highlight c# %}

public class Global : System.Web.HttpApplication
    {
        protected void Application_Start(object sender, EventArgs e)
        {
            System.Web.Http.GlobalConfiguration.Configuration.Routes.MapHttpRoute(
                name: "DefaultApi",
                routeTemplate: "{controller}/{action}/{id}",
                defaults: new { id = RouteParameter.Optional });
            AppDomain.CurrentDomain.SetData("SQLServerCompactEditionUnderWebHosting", true);
        }
}

{% endhighlight %}

Now, **PivotGrid** will be rendered with Internet Sales Amount over a period of fiscal years across different customer geographic locations.

![](Getting-Started_images/pivotgrid.png) 

### WCF

This section demonstrates the utilization of WCF service as endpoint binding OLAP datasource to a simple PivotGrid. For more details on this topic, [click here](http://help.syncfusion.com/aspnet/pivotgrid/olap-connectivity#wcf).


