---
layout: post
title: Getting Started | ReportDesigner | ASP.NET | Syncfusion
description: getting started
platform: aspnet
control: ReportDesigner
documentation: ug
---

# Getting Started

This section explains briefly about how to create a ReportDesigner in your web application with ASP.NET.

## Create your first ReportDesigner in ASP.NET

The following screenshots displays the Project Creation Wizard in Visual Studio 2012.

Open Visual Studio and create a new project by clicking `New Project`. Select the **Web** category, select the ASP.NET Empty Web Application template, and then click `OK`. The following screenshot displays the Project Creation Wizard.

![](Getting-Started_images/Getting-Started_img1.png) 

Project Creation Wizard
{:.caption}

### Create ASPX Page

To create a new Web Forms in the application

1. Right-Click on the project and select Add

   ![](Getting-Started_images/Getting-Started_img2.png) 
   
   New Item Wizard
   {:.caption}
   
2. Click New Item and select Web Form from the listed templates

   ![](Getting-Started_images/Getting-Started_img3.png) 
   
   Adding Web Forms
   {:.caption}
   
3. Name the page as Default.aspx and click OK.


### Add References, Scripts, Styles and Control in ASPX Page

#### Add References

1. In the Solution Explorer, right-click the References folder and then click Add Reference.

   ![](Getting-Started_images/Getting-Started_img4.png) 
   
   Adding Reference
   {:.caption}
   
2. Add the following assemblies

   * System.Web.Routing
   * System.Web.Http
   * System.Web.WebHost
   * System.Net.Http
   * System.Net.Http.WebRequest
   * System.Net.Http.Formatting
   * Syncfusion.Compression.Base   
   * Syncfusion.EJ.ReportDesigner
   * Syncfusion.EJ.ReportDesigner
   * Syncfusion.Pdf.Base
   * Syncfusion.XlsIO.Base
   * Syncfusion.Presentation.Base
   * Syncfusion.DocIO.Base
   * Syncfusion.Shared.Wpf
   * Syncfusion.Chart.Wpf
   * Syncfusion.Gauge.Wpf
   * Syncfusion.SfMaps.Wpf
   
   > Refer the above assemblies from the installed location, C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Assemblies

   > Refer System.Web.Http, System.Web.WebHost, System.Net.Http.WebRequest and System.Net.Http.Formatting assemblies from ASP.NET WebApi NuGet package.

#### Add Scripts and Styles

Add the script files and CSS files in the &lt;head&gt; tag of the default.aspx page.

N> Use the following code example while adding scripts and styles.

{% highlight html %}

<head>
<link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css"  rel="stylesheet" />
<link href="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.reportdesigner.min.css" rel="stylesheet" />
<link href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/codemirror.min.css" rel="stylesheet" />
<link href="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/show-hint.min.css" rel="stylesheet" />
<script src="http://code.jquery.com/jquery-1.10.2.min.js" type="text/javascript"></script>
<script src="http://cdnjs.cloudflare.com/ajax/libs/jquery-easing/1.3/jquery.easing.min.js" type="text/javascript">
</script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/codemirror.min.js" type="text/javascript"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/show-hint.min.js" type="text/javascript"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/addon/hint/sql-hint.min.js" type="text/javascript"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/codemirror/5.37.0/mode/sql/sql.min.js" type="text/javascript"></script>
<script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"> </script>
<script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.reportdesigner.min.js"> </script>
</head>

{% endhighlight %}

### Add Control in ASPX Page

1. Drag the ReportDesigner control from the Syncfusion Web Toolbox onto the Design Page.

   ![](Getting-Started_images/Getting-Started_img5.png) 
   
   ReportDesigner Control in Toolbox
   {:.caption} 

2. Set the desired ReportPath and ServiceUrl to ReportDesigner.
   
   ~~~ html   
   <form id="form1" runat="server">
       <div style="height: 650px;width: 950px;min-height:404px;">
           <ej:ReportDesigner runat="server" ID="designer"  ReportPath="~/App_Data/Sales Dashboard.rdl" ServiceUrl="/api/ReportDesigner">
           </ej:ReportDesigner>
       </div>
   </form>   
   ~~~
   
   N> Add your report files to your application’s App_Data folder.You can obtain sample rdl/rdlc files from Syncfusion installed location (%userprofile%\AppData\Local\Syncfusion\EssentialStudio\{{ site.releaseversion }}\Common\Data\ejReportTemplate). {{ site.releaseversion }} is the Essential Studio Release Version.
	
### Add WebAPI controller for ReportDesigner

The ASP.NET ReportDesigner uses WebApi services to process the report file and process the request from control.

![](Getting-Started_images/Getting-Started_img7.png) 

Adding WebApi Controller
{:.caption} 

### Inherit the ReportDesigner IReportController

The ApiController inherits the IReportController and you can add the following code example to its methods definition in order to process the report file. The interface IReportController contains the required actions and helper methods declaration to process the report. The ReportHelper class contains helper methods that helps to process Post/Get request from control and return the response to control.


{% highlight C# %}

using System;
using Syncfusion.EJ.ReportViewer;
using System.Collections.Generic;
using System.Linq;
using System.Net;
using System.Net.Http;
using System.Web.Http;
using Syncfusion.Reports.EJ;
using System.Collections;
using System.Web;
using Syncfusion.EJ.ReportDesigner;
using System.IO;
using Reporting.ExternalServer;

namespace ReportDesignerDemo
{
    public class ReportDesignerController : ApiController, Syncfusion.EJ.ReportDesigner.IReportDesignerController
    {
        string CachePath = "App_Data\\ReportServer\\Cache\\";

        internal ExternalServer Server
        {
            get;
            set;
        }

        internal string ServerURL
        {
            get;
            set;
        }

        internal string AuthorizationHeaderValue
        {
            get;
            set;
        }

        public ReportDesignerController()
        {
            ExternalServer externalServer = new ExternalServer();
            this.Server = externalServer;
            this.ServerURL = "Sample";
            externalServer.ReportServerUrl = this.ServerURL;
            ReportDesignerHelper.ReportingServer = externalServer;
        }

        [HttpPost]
        public void UploadReportAction()
        {
            ReportDesignerHelper.ProcessDesigner(null, this, HttpContext.Current.Request.Files[0]);
        }

        [HttpGet]
        public object GetImage(string key, string image)
        {
            return ReportDesignerHelper.GetImage(key, image, this);
        }

        [HttpPost]
        public object PostDesignerAction(Dictionary<string, object> jsonResult)
        {
            return ReportDesignerHelper.ProcessDesigner(jsonResult, this, null);
        }

        public object PostReportAction(Dictionary<string, object> jsonResult)
        {
            return ReportHelper.ProcessReport(jsonResult, this as IReportController);
        }

        public void OnInitReportOptions(Syncfusion.EJ.ReportViewer.ReportViewerOptions reportOption)
        {
            reportOption.ReportModel.ReportingServer = this.Server;
            reportOption.ReportModel.ReportServerUrl = this.ServerURL;
            reportOption.ReportModel.ReportServerCredential = new NetworkCredential("Sample", "Password");
        }

        public void OnReportLoaded(Syncfusion.EJ.ReportViewer.ReportViewerOptions reportOption)
        {
        }

        public object GetResource(string key, string resourcetype, bool isPrint)
        {
            return ReportHelper.GetResource(key, resourcetype, isPrint);
        }

        public bool UploadFile(HttpPostedFile httpPostedFile)
        {
            string targetFolder = HttpContext.Current.Server.MapPath("~/");
            string fileName = !string.IsNullOrEmpty(ReportDesignerHelper.SaveFileName) ? ReportDesignerHelper.SaveFileName : Path.GetFileName(httpPostedFile.FileName);
            targetFolder += CachePath;

            if (!Directory.Exists(targetFolder))
            {
                Directory.CreateDirectory(targetFolder);
            }

            if (!Directory.Exists(targetFolder + "\\" + ReportDesignerHelper.EJReportDesignerToken))
            {
                Directory.CreateDirectory(targetFolder + "\\" + ReportDesignerHelper.EJReportDesignerToken);
            }

            httpPostedFile.SaveAs(targetFolder + "\\" + ReportDesignerHelper.EJReportDesignerToken + "\\" + fileName);
            return true;
        }

        public List<Syncfusion.EJ.ReportDesigner.FileModel> GetFiles(Syncfusion.EJ.ReportDesigner.FileType fileType)
        {
            List<FileModel> databases = new List<FileModel>();
            var folderPath = HttpContext.Current.Server.MapPath("~/") + CachePath + ReportDesignerHelper.EJReportDesignerToken + "\\";

            if (Directory.Exists(folderPath))
            {
                DirectoryInfo directoryInfo = new DirectoryInfo(folderPath);
                FileInfo[] Files = directoryInfo.GetFiles(this.GetFileExtension(fileType));

                foreach (FileInfo file in Files)
                {
                    databases.Add(new FileModel() { Name = file.Name, Path = "../" + CachePath + ReportDesignerHelper.EJReportDesignerToken + "/" + file.Name });
                }
            }

            return databases;
        }

        private string GetFileExtension(Syncfusion.EJ.ReportDesigner.FileType fileType)
        {
            if (fileType == FileType.Sdf)
            {
                return "*.sdf";
            }
            else if (fileType == FileType.Xml)
            {
                return "*.xml";
            }

            return "*.rdl";
        }

        public string GetFilePath(string fileName)
        {
            string targetFolder = HttpContext.Current.Server.MapPath("~/");
            targetFolder += CachePath;

            if (!Directory.Exists(targetFolder))
            {
                Directory.CreateDirectory(targetFolder);
            }

            if (!Directory.Exists(targetFolder + "\\" + ReportDesignerHelper.EJReportDesignerToken))
            {
                Directory.CreateDirectory(targetFolder + "\\" + ReportDesignerHelper.EJReportDesignerToken);
            }

            var folderPath = HttpContext.Current.Server.MapPath("~/") + CachePath + ReportDesignerHelper.EJReportDesignerToken + "\\";
            return folderPath + fileName;
        }


        public FileModel GetFile(string filename, bool isOverride)
        {
            throw new NotImplementedException();
        }
    }
}

{% endhighlight %}

### WebAPI Routing

1. Right-click the project and select Add and select Global Application Class file from the listed templates.

   ![](Getting-Started_images/Getting-Started_img8.png) 
   
   Adding Global.asax
   {:.caption} 
   
2. You can route the WebAPI in Application_Start event into Global.asax file as follows.
   
{% highlight C# %}

using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;
using System.Web.Security;
using System.Web.SessionState;
using System.Web.Http;

namespace ReportDesignerDemo
{
    public class Global : System.Web.HttpApplication
    {
        protected void Application_Start(object sender, EventArgs e)
        {
            System.Web.Http.GlobalConfiguration.Configuration.Routes.MapHttpRoute(
            name: "DefaultApi",
            routeTemplate: "api/{controller}/{action}/{id}",
            defaults: new { id = RouteParameter.Optional });
            AppDomain.CurrentDomain.SetData("SQLServerCompactEditionUnderWebHosting", true);
        }
    }
}

{% endhighlight %}

### Run the Application

Run the sample application and you can see the ReportDesigner on the page as displayed in the following screenshot.

![](Getting-Started_images/Getting-Started_img9.png)  

# Integrate the component with Report Server

Report Designer can be integrated with the Report Server by using below code snippet. After integrating you can open, browse and edit the reports in the Report Server using Report designer.

Set the Report Server `serviceUrl` and `serviceAuthorizationToken` in the ReportDesigner properties.

{% highlight html %}
<div id="container" style="position: absolute; height: 100%; width: 100%;"></div>
<script type="text/javascript">
   $(function () {
            var dataValue = "";
            var apiRequest = new Object();
            apiRequest.password = "demo";
            apiRequest.userid = "guest";
            $.ajax({
                type: "POST",
                url: "http://reportserver.syncfusion.com/api/get-user-key",
                data: apiRequest,
                success: function (data) {
                    dataValue = data.Token;
                    var token = JSON.parse(dataValue);
                    $("#container").ejReportDesigner(
                    {
                       serviceUrl: 'http://reportserver.syncfusion.com/ReportService/api/Designer',
                       serviceAuthorizationToken: token['token_type'] + ' ' + token['access_token']
                    });
                }
            });
   });
</script>

{% endhighlight %}

## Integrate the component with External Server

Report Designer can be integrated with the External Server or Server file browsing by using below code snippet. After integrating you can open, browse and edit the reports in External Server or Application Data using Report designer.

   ~~~ html 
   <form id="form1" runat="server">
       <div style="height: 650px;width: 950px;min-height:404px;">
           <ej:ReportDesigner runat="server" ID="designer" ServiceUrl="/api/ReportDesigner">
           </ej:ReportDesigner>
       </div>
   </form>
   ~~~

{% highlight C# %}

using Syncfusion.EJ.ReportViewer;
using System.Collections.Generic;
using System.Linq;
using System.Net;
using System.Net.Http;
using System.Web.Http;
using Syncfusion.Reports.EJ;
using System.Collections;
using System.Web;
using Syncfusion.EJ.ReportDesigner;
using System.IO;
using Reporting.ExternalServer;

namespace EJServices.Controllers
{
    public class ReportDesignerController : ApiController, Syncfusion.EJ.ReportDesigner.IReportDesignerController
    {
        public ReportDesignerController()
        {
            ExternalServer externalServer = new ExternalServer();
            externalServer.ReportServerUrl = "Your Path";
            ReportDesignerHelper.ReportingServer = externalServer;
        }

        public FileModel GetFile(string filename, bool isOverride)
        {
            throw new NotImplementedException();
        }

        public string GetFilePath(string key)
        {
            throw new NotImplementedException();
        }

        public List<FileModel> GetFiles(FileType fileType)
        {
            throw new NotImplementedException();
        }

        [HttpGet]
        public object GetImage(string key, string image)
        {
            throw new NotImplementedException();
        }

        [HttpPost]
        public object PostDesignerAction(Dictionary<string, object> jsonResult)
        {
            throw new NotImplementedException();
        }

        public bool UploadFile(HttpPostedFile httpPostedFile)
        {
            throw new NotImplementedException();
        }

        [HttpPost]
        public void UploadReportAction()
        {
            throw new NotImplementedException();
        }

        public object GetResource(string key, string resourcetype, bool isPrint)
        {
            throw new NotImplementedException();
        }

        public void OnInitReportOptions(ReportViewerOptions reportOption)
        {
            reportOption.ReportModel.ReportingServer = this.Server;
            reportOption.ReportModel.ReportServerUrl = this.ServerURL;
            reportOption.ReportModel.ReportServerCredential = new NetworkCredential("Sample", "Password");
        }

        public void OnReportLoaded(ReportViewerOptions reportOption)
        {
            throw new NotImplementedException();
        }

        public object PostReportAction(Dictionary<string, object> jsonResult)
        {
            throw new NotImplementedException();
        }
    }
}

{% endhighlight %}

>NOTE: 
You can refer the External Server sample and service from the installed location 
sample: %public%\Documents\Syncfusion\ASP.NET\{{ site.releaseversion }}\Samples\Web\Dashboard\ReportBuilderTemplate.aspx
API Service: %public%\Documents\Syncfusion\ASP.NET\{{ site.releaseversion }}\ejservices\Controllers\ReportDesignerController.cs
External Server: %public%\Documents\Syncfusion\ASP.NET\{{ site.releaseversion }}\ejservices\Controllers\ExternalReportServer.cs