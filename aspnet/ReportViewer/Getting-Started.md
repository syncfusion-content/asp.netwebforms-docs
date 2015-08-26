---
layout: post
title: Getting-Started
description: getting started
platform: aspnet
control: ReportViewer
documentation: ug
---

# Getting Started

This section explains briefly about how to create a ReportViewer in your web application with ASP.NET.

## Create your first ReportViewer in ASP.NET

### Control Structure

The following screenshot shows the control structure of theReportViewer.

![C:/Users/pandimurugana/AppData/Local/Microsoft/Windows/INetCache/Content.Word/reportviewer1.png](Getting-Started_images/Getting-Started_img1.png) 





## Create an Application

This section explains how to configure a ReportViewer component in web application. As ReportViewer uses WebApi to process the report file, you can also learn how to create WebApi Service to process the report for ReportViewer. In the following example, the ReportViewer component displays the Sales Dashboard Report. 

Open Visual Studio and create a new project by clicking New Project. Select the Web category, select the ASP.NET Empty Web Application template, and then click OK. The following screenshot displays the Project Creation Wizard.

![](Getting-Started_images/Getting-Started_img2.png) 



### Create ASPX Page

To create a new web form in the application

1. Right-Click on the project and select Add

   ![IMG_21102014_033459](Getting-Started_images/Getting-Started_img3.png) 
   

2. Click New Item and select Web Form from the listed templates

   ![](Getting-Started_images/Getting-Started_img4.png) 
   

3. Name the page as Default.aspx and click OK.



## Add References, Scripts, Styles and Control in ASPX Page

### Add References

1. In the Solution Explorer, right-click the References folder and then click Add Reference

   ![](Getting-Started_images/Getting-Started_img5.png) 
   


2. Add the following assemblies

   * System.Web.Routing,  
   * System.Web.Http,
   * System.Web.WebHost
   * System.Net.Http,
   * System.Net.Http.WebRequest,
   * System.Net.Http.Formatting,
   * Syncfusion.EJ
   * Syncfusion.EJ.Web
   * Syncfusion.Core.dll,
   * Syncfusion.Linq.Base.dll,
   * Syncfusion.EJ.ReportViewer,
   * Syncfusion.ReportControls.Wpf
   * Syncfusion.ReportWriter.Base
   * Syncfusion.Pdf.Base,
   * Syncfusion.XlsIO.Base,
   * Syncfusion.DocIO.Base
   * Synfusion.Shared.Wpf
   * Syncfusion.Chart.Wpf
   * Syncfusion.Gauge.Wpf
   * Syncfusion.SfMaps.Wpf 
   
   N> Refer System.Web.Http, System.Web.WebHost, System.Net.Http.WebRequest and System.Net.Http.Formatting dlls from ASP.NET WebApi nuget package.

3. Click OK



### Add Scripts and Styles

### Add the script files and CSS files in the &lttitle&gt tag of the default.html page.

N> Use the following code example while adding scripts and styles.


{% highlight html %}
	
	<head>
   
		<link href="http://cdn.syncfusion.com/js/web/flat-azure/ej.web.all-latest.min.css" rel="stylesheet"/>
   	
		<script src="http://code.jquery.com/jquery-1.10.2.min.js" type="text/javascript"> </script>
		
   		<script src="http://cdnjs.cloudflare.com/ajax/libs/jquery-easing/1.3/jquery.easing.min.js" type="text/javascript"> </script>

   	 	<script src="~/Scripts/jquery.globalize.min.js"></script>

  		<script src="http://cdn.syncfusion.com/js/web/ej.web.all-latest.min.js"></script>

	</head>
	
{% endhighlight %}

### Add Control in ASPX Page

1. Drag the ReportViewer control from the Syncfusion Web Toolbox onto the Design Page

   ![IMG_21102014_064430](Getting-Started_images/Getting-Started_img8.png) 
   
   
   ![](Getting-Started_images/Getting-Started_img9.png)    
   

2. Set the desired ReportPath and ReportServiceUrl to ReportViewer.
   
   ~~~ html
	
		<form id="form1" runat="server">
		
			<div style="height: 650px;width: 950px;min-height:404px;">
			
				<ej:ReportViewer runat="server" ID="viewer"  ReportPath="~/App_Data/Sales Dashboard.rdl" ReportServiceUrl="/api/ReportApi">
				
				</ej:ReportViewer>
				
			</div>
			
		</form>
   ~~~
   {:.prettyprint }
	
   N> Add your report files to your application’s App_Data folder.You can obtain sample rdl/rdlc files from Syncfusion installed location (%userprofile%\AppData\Local\Syncfusion\EssentialStudio\ XX.X.X.XX\Common\Data\ejReportTemplate). “X.X.X.X” is the Essential Studio Release Version.
	
## Add WebAPI controller for ReportViewer

The ASP.NET ReportViewer uses WebApi services to process the report file and process the request from control.

![](Getting-Started_images/Getting-Started_img10.png) 





## Inherit the ReportViewer IReportController

The ApiController inherits the IReportController and you can add the following code example to its methods definition in order to process the report file. The interface IReportController contains the required actions and helper methods declaration to process the report. The ReportHelper class contains helper methods that helps to process Post/Get request from control and return the response to control.



{% highlight c# %}

	using Syncfusion.EJ.ReportViewer;

	using System;

	using System.Collections.Generic;

	using System.Linq;

	using System.Net;

	using System.Net.Http;

	using System.Web.Http;


	namespace ReportViewerDemo.Api

	{

    public class ReportApiController : ApiController, IReportController

    {

			//Post action for processing the rdl/rdlc report

			public object PostReportAction(Dictionary<string, object> jsonResult)

			{

				return ReportHelper.ProcessReport(jsonResult, this);

			}



			//Get action for getting resources from the report

			[System.Web.Http.ActionName("GetResource")]

			[AcceptVerbs("GET")]

			public object GetResource(string key, string resourcetype, bool isPrint)

			{

				return ReportHelper.GetResource(key, resourcetype, isPrint);

			}



			//Method will be called when initialize the report options before start processing the report        public void OnInitReportOptions(ReportViewerOptions reportOption)

			{

				//You can update report options here

			}



				//Method will be called when reported is loaded

			public void OnReportLoaded(ReportViewerOptions reportOption)

			{

				//You can update report options here

			}   

		}

	}

{% endhighlight %}



## WebAPI Routing

1. Right-click the project and select Add and select Global.asax file from the listed templates.

   ![](Getting-Started_images/Getting-Started_img11.png) 
   
   
   You can route the WebAPI in Application_Start event into Global.asax file as follows.
   
{% highlight c# %}
   
    using System;
   
    using System.Collections.Generic;
   
    using System.Linq;
   
    using System.Web;
   
    using System.Web.Security;
   
    using System.Web.SessionState;
   
    using System.Web.Http;
   
    namespace ReportViewerDemo
   
    {

     public class Global : System.Web.HttpApplication

     {

        protected void Application_Start(object sender, EventArgs e)

        {

          System.Web.Http.GlobalConfiguration.Configuration.Routes.MapHttpRoute(

          name: "DefaultApi",

          routeTemplate: "api/{controller}/{action}/{id}",

          defaults: new { id = RouteParameter.Optional });

        }

     }
    }
	
{% endhighlight %}

### Run the Application

Run the sample application and you can see the ReportViewer on the page as displayed in the following screenshot.

![C:/Users/pandimurugana/AppData/Local/Microsoft/Windows/INetCache/Content.Word/reportviewer.png](Getting-Started_images/Getting-Started_img12.png)  




## Load SSRS Server Reports

ReportViewer supports to load RDL/RDLC files from SSRS Server. The following steps help you to load reports from SSRS Server.

1. Set the ReportPath from SSRS and SSRS ReportServerUrl in the ReportViewer properties.

   ~~~ html
	
	 	
	 
        <form id="form1" runat="server">
		
            <div style="height: 650px;width: 950px;min-height:404px;">
			
				<ej:ReportViewer ID="viewer" runat="server" ReportServiceUrl="/api/SSRSReport" ReportServerUrl="http://76.74.153.81/ReportServer"  ReportPath="/SSRSSamples2/Territory Sales">
				
				</ej:ReportViewer>
				
			</div>
			
        </form>
		
   ~~~
   {:.prettyprint }

2. Add the credential information in ReportApiController’sOnInitReportOptions method that is available in IReportController

   ~~~ cs   
   
        public void OnInitReportOptions(ReportViewerOptions reportOption)
        {
			//Add SSRS Server and database credentials here 
            reportOption.ReportModel.ReportServerCredential = new System.Net.NetworkCredential("ssrs", "RDLReport1");
            reportOption.ReportModel.DataSourceCredentials.Add(new DataSourceCredentials("AdventureWorks", "ssrs1", "RDLReport1"));
        }		
   ~~~
   {:.prettyprint }
		
3. Run the application and you can see the ReportViewer on the page as displayed in the following screenshot.

      ![](Getting-Started_images/Getting-Started_img13.png) 
      


## Load RDLC Reports

The ReportViewer has data binding support to visualize the RDLC reports. The following steps help you to bind data to ReportViewer.

1. Assign the RDLC report path to ReportViewer’sReportPath property

   ~~~ html
   
        <div style="width:100%;height:100%;"> 
		
			<ej:ReportViewer ID="viewer" runat="server" ReportServiceUrl="/api/ReportApi" ReportPath="~/App_Data/Product List.rdlc" ProcessingMode="Local">
			
			</ej:ReportViewer>
			
		</div> 
		
   ~~~
   {:.prettyprint }

2. Add business object data source to ReportViewer’sDataSources from aspx.cs.

   ~~~ cs 
	
		namespace ReportViewerDemo
		{
			public partial class ProductListDemo : System.Web.UI.Page
			{
				protected void Page_Load(object sender, EventArgs e)
				{
					ProductList prodlist = new ProductList();
					List<ReportDataSource> rptDatasources = new List<ReportDataSource>();
					ReportDataSource rptDatasource =new ReportDataSource();
					rptDatasource.Name = "list";
					rptDatasource.Value = prodlist.GetData();
					rptDatasources.Add(rptDatasource);
					this.viewer.DataSources = rptDatasources;
				}
			}
 
			public class ProductList
			{
				public string ProductName { get; set; }
				public string OrderId { get; set; }
				public double Price { get; set; }
				public string Category { get; set; }
				public string Ingredients { get; set; }
				public string ProductImage { get; set; }
 
				public IList GetData()
				{
					List<ProductList> datas = new List<ProductList>();
					ProductList data = null;
					data = new ProductList() { ProductName = "Baked Chicken and Cheese", OrderId = "323B60", Price = 55, Category = "Non-Veg", Ingredients = "grilled chicken, corn and olives.", ProductImage = "" };
					datas.Add(data);
					data = new ProductList() { ProductName = "Chicken Delite", OrderId = "323B61", Price = 100, Category = "Non-Veg", Ingredients = "cheese, chicken chunks, onions & pineapple chunks.", ProductImage = "" };
					datas.Add(data);
					data = new ProductList() { ProductName = "Chicken Tikka", OrderId = "323B62", Price = 64, Category = "Non-Veg", Ingredients = "onions, grilled chicken, chicken salami & tomatoes.", ProductImage = "" };
					datas.Add(data);
					return datas;
				}
			}
		}
   ~~~
   {:.prettyprint }

3. Run the application and you can see the ReportViewer on the page as displayed in the following screenshot.

    ![](Getting-Started_images/Getting-Started_img14.png) 
     


