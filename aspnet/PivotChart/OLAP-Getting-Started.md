---
layout: post
title: OLAP Getting Started | PivotChart| ASP.NET | Syncfusion
description: olap getting started
platform: aspnet
control: PivotChart
documentation: ug
---

# Getting Started

## Creating a simple application with PivotChart and OLAP datasource (Client Mode)

This section covers the information required to populate a simple PivotChart with OLAP data completely on the client-side.

## Project Initialization

Create a new **ASP.NET Empty Web Application** using Visual Studio IDE and name the project as **“PivotChartDemo”**.

Now add a **“Web Form”** to the ASP.NET Empty Web Application. For adding a “Web Form”, right-click on the project in Solution Explorer and select **Add > New Item**. In the Add New Item window, select “Web Form” and name it as Default.aspx and click **Add**.

Now add the following dependency libraries as references into your Web Application. In order to add them to your application, right-click on **References** in Solution Explorer and select Add Reference. Now in the **Reference Manager** dialog, under **Assemblies > Extension**, the following Syncfusion libraries will be found.

* Syncfusion.EJ
* Syncfusion.EJ.Olap

Register the referenced assemblies in Web.config files available at the root of the application.

{% highlight xml %}

    <compilation debug="true" targetFramework="4.5">
        <assemblies> 
            ……
            ……
            <add assembly="Syncfusion.EJ, Version= {{ site.45esreleaseversion}}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
            <add assembly="Syncfusion.EJ.Olap, Version= {{ site.45esreleaseversion}}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />            

        </assemblies>
    </compilation>
{% endhighlight %}

### Scripts and CSS Initialization

The scripts and style sheets that are mandatorily required to render PivotChart control in a Web Application are mentioned in an appropriate order below:

1.  ej.web.all.min.css
2.	jquery-1.10.2.min.js
3.	jquery.easing.1.3.min.js
4.	ej.web.all.min.js 

[Click here](http://help.syncfusion.com/js/cdn) here to know more about scripts and style sheets available online (CDN Link).

Scripts and style sheets are referred under the <head> tag in **Default.aspx** file.
    
{% highlight html %}

    <head>
        <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
        <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js" type="text/javascript"> </script>
        <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js" type="text/javascript"> </script>
        <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"> </script>
    </head>
    
{% endhighlight %}

### Initialize PivotChart

Either drag and drop the **PivotChart** control from the toolbox (under Syncfusion BI Web category) or manually define the control like in the below code sample inside “Default.aspx” page.

{% highlight html %}

    <%@ Register Assembly="Syncfusion.EJ.Olap" Namespace="Syncfusion.JavaScript.Web" TagPrefix="ej" %>
    <%@ Register Assembly="Syncfusion.EJ.Olap" Namespace="Syncfusion.JavaScript.Models" TagPrefix="ej" %>

    <html> 
    <head>
    .....
    .....
    <style>
        #MyPivotChart1 {
            width:100%;
            height:460px;
        }
    </style>
    </head>
    <body>
        <form runat="server">
            <ej:PivotChart ID="MyPivotChart1" runat="server" ClientIDMode="Static">
            <Size Width="100%" Height="460px"></Size>
            </ej:PivotChart>
        </form>
    </body>
    
    </html>
{% endhighlight %}

### Populate PivotChart With DataSource

Initializes the OLAP datasource for PivotChart control as shown below.


{% highlight html %}

    <ej:PivotChart ID="MyPivotChart1" runat="server">
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
        <Size Width="100%" Height="460px"></Size>
    </ej:PivotChart>

{% endhighlight %}

Now, **PivotChart** is rendered with Internet Sales Amount over a period of fiscal years across different customer geographic locations.

![](OLAP-Getting-Started_images/PopulatePivotChartWithDataSource.png) 

## Creating a simple application with PivotChart and OLAP datasource (Server Mode)
 
This section covers the information required to create a simple PivotChart bound to OLAP datasource.

N> ASP.NET Empty Web Application will contain a service that transfers data to server-side, processes and returns back to client-side for control rendering and re-rendering. The service utilized for communication could be either WCF or WebAPI based on user requirement.

### Project Initialization

Create a new **ASP.NET Empty Web Application** using Visual Studio IDE and name the project as **"PivotChartDemo"**. 

Now add a “Web Form” to the Empty Web Application. For adding a “Web Form”, right-click on the project in Solution Explorer and select **Add > New Item**. In the Add New Item window, select “Web Form” and name it as Default.aspx and click “Add”.

Now add the following dependency libraries as references into your Empty Web Application. In order to add them to your application, right-click on **References** in Solution Explorer and select **Add Reference**. Now in the **Reference Manager** dialog, under **Assemblies > Extension**, the following Syncfusion libraries will be found.

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

N> If any version of SQL Server Analysis Service (SSAS) or Microsoft ADOMD.NET utility is installed, then the location of Microsoft.AnalysisServices.AdomdClient library is [system drive:\Program Files (x86)\Microsoft.NET\ADOMD.NET].


Register the referenced assemblies in Web.config files at the root of the application.

{% highlight xml %}

    <compilation debug="true" targetFramework="4.5">
        <assemblies> 
            …… 
            ……
            <add assembly="Syncfusion.EJ, Version= {{ site.45esreleaseversion}}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
            <add assembly="Syncfusion.EJ.Olap, Version= {{ site.45esreleaseversion}}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
            <add assembly="Syncfusion.Linq.Base, Version= {{ site.45esreleaseversion}}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
            <add assembly="Syncfusion.Olap.Base, Version= {{ site.45esreleaseversion}}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
            <add assembly="Syncfusion.Compression.Base, Version= {{ site.45esreleaseversion}}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" /> 
            <add assembly="Syncfusion.PivotAnalysis.Base, Version= {{ site.45esreleaseversion}}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" /> 
            <add assembly="Syncfusion.Pdf.Base, Version= {{ site.45esreleaseversion}}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
            <add assembly="Syncfusion.XlsIO.Base, Version= {{ site.45esreleaseversion}}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
            <add assembly="Syncfusion.DocIO.Base, Version= {{ site.45esreleaseversion}}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" /> 
        </assemblies>
    </compilation>

{% endhighlight %}


### Scripts and CSS Initialization

The scripts and style sheets that are mandatorily required to render PivotChart control in a Web Application are mentioned in an appropriate order below:

1.  ej.web.all.min.css
2.	jquery-1.10.2.min.js
3.	jquery.easing.1.3.min.js
4.	ej.web.all.min.js 

[Click here](http://help.syncfusion.com/js/cdn) here to know more about scripts and style sheets available online (CDN Link).

Scripts and style sheets are referred under the **head** tag in **Default.aspx** file.
    
{% highlight html %}

    <head>
        <link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />
        <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js" type="text/javascript"> </script>
        <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js" type="text/javascript"> </script>
        <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"> </script>
    </head>
{% endhighlight %}

### Control Initialization

Either drag and drop the **PivotChart** control from the toolbox (under Syncfusion BI Web category) or manually define the control like in the below code sample inside “Default.aspx” page.

{% highlight html %}

    <%@ Register Assembly="Syncfusion.EJ.Olap" Namespace="Syncfusion.JavaScript.Web" TagPrefix="ej" %>
    <%@ Register Assembly="Syncfusion.EJ.Olap" Namespace="Syncfusion.JavaScript.Models" TagPrefix="ej" %>

    <html> 
    <head>
    .....
    .....
    <style>
        #MyPivotChart1 {
            width:100%;
            height:460px;
        }
    </style>
    </head>
    <body>
        <form runat="server">
            <ej:PivotChart ID="MyPivotChart1" runat="server" Url="/OlapChart" ClientIDMode="Static">
            <Size Width="100%" Height="460px"></Size>
            </ej:PivotChart>
        </form>
    </body>
    
    </html>
    
{% endhighlight %}

The **“Url”** property in PivotChart control points the service endpoint, where data are processed and fetched in the form of JSON. The services used in PivotChart control as endpoint are WCF and WebAPI.

N> The above "Default.aspx" contains WebAPI URL, which is "/OlapChart". If WCF service is used as endpoint, the URL would look like "/OlapChartService.svc".


### WebAPI

**Adding a WebAPI Controller**

To add a WebAPI controller in your existing Web Application, right-click on the project in Solution Explorer and select **Add > New Item.** In the **Add New Item** window, select **WebAPI Controller Class** and name it as “OlapChartController.cs”, click **Add.**

Now WebAPI controller is added into your application successfully which in-turn comprise of the following file. The utilization of this file will be explained in the following sections.
 
* OlapChartController.cs

N> While adding WebAPI Controller Class, name it with the suffix “Controller” that is mandatory. For example, in demo the controller is named as “OlapChartController”.

Next, remove all the existing methods such as “Get”, “Post”, “Put” and “Delete” present inside `OlapChartController.cs` file. 

{% highlight c# %}

    namespace PivotChartDemo
    {
        public class OlapChartController : ApiController
        {
        
        }
    }

{% endhighlight %}

**List of Namespaces**

Following are the list of namespaces to be added on top of the main class inside `OlapChartController.cs` file.

{% highlight c# %}

    using Syncfusion.Olap.Manager;
    using Syncfusion.Olap.Reports;
    using Syncfusion.JavaScript;

    namespace PivotChartDemo
    {
        public class OlapChartController : ApiController
        {

        }
    }

{% endhighlight %}

**Datasource Initialization**

Now, the connection string to connect OLAP Cube, PivotChart instances are created immediately inside the main class in `OlapChartController.cs` file.

{% highlight c# %}

    namespace PivotChartDemo
    {
        public class OlapChartController : ApiController
        {
            string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
            PivotChart htmlHelper = new PivotChart();
            //Other codes
        }
    }

{% endhighlight %}

**Service methods in WebAPI Controller**

Now you need to define the service methods inside OlapChartController class, found inside `OlapChartController.cs` file, created while adding WebAPI Controller Class to your Web Application.
 
{% highlight c# %}

    namespace PivotChartDemo
    {
        public class OlapChartController : ApiController
        {
            string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
            PivotChart htmlHelper = new PivotChart();

            [System.Web.Http.ActionName("InitializeChart")]
            [System.Web.Http.HttpPost]
            public Dictionary<string, object> InitializeChart(Dictionary<string, object> jsonResult)
            {
                OlapDataManager DataManager = null;
                DataManager = new OlapDataManager(connectionString);
                DataManager.SetCurrentReport(CreateOlapReport());
                return htmlHelper.GetJsonData(jsonResult["action"].ToString(), DataManager);
            }

            [System.Web.Http.ActionName("DrillChart")]
            [System.Web.Http.HttpPost]
            public Dictionary<string, object> DrillChart(Dictionary<string, object> jsonResult)
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                DataManager.SetCurrentReport(Syncfusion.JavaScript.Olap.Utils.DeserializeOlapReport(jsonResult["olapReport"].ToString()));
                return htmlHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["drilledSeries"].ToString());
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

**Configure routing in Global Application Class**

To add a Global.asax in your existing Web Application, right-click on the project in Solution Explorer and select **Add > New** Item. In the **Add New Item** window, select **Global Application** Class and name it as **“Global.asax”**, click **Add.**
 
Once you finish adding the **Global.asax** file, delete all the methods inside the **Global** class and add the namespace **“using System.Web.Http;”** and then you can configure routing like in the following code example.

{% highlight c# %}

    public class Global : System.Web.HttpApplication
    {
        protected void Application_Start(object sender, EventArgs e)
        {
            GlobalConfiguration.Configuration.Routes.MapHttpRoute(
                name: "DefaultApi",
                routeTemplate: "{controller}/{action}/{id}",
                defaults: new { id = RouteParameter.Optional });
            AppDomain.CurrentDomain.SetData("SQLServerCompactEditionUnderWebHosting", true);
        }
    }
{% endhighlight %}

Now, **PivotChart** is rendered with customer count over a period of fiscal years across different customer geographic locations.


![](OLAP-Getting-Started_images/ServerMode.png) 

### WCF

This section demonstrates the utilization of WCF service as endpoint binding OLAP datasource to a simple PivotChart. For more details on this topic, [click here](http://help.syncfusion.com/aspnet/PivotChart/olap-connectivity#wcf).


