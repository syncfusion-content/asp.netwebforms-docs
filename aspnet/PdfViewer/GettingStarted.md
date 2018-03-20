---
layout: post
title: Getting Started | PDF viewer | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: PDF viewer
documentation: ug
---


# Getting Started

This section explains briefly about how to include PDF viewer in ASP.NET Web Forms.

**Create your first PDF viewer application in ASP.NET**

Create a new project in the Visual Studio by selecting the ASP.NET Empty Web Application template. The following screenshot displays the Project Creation Wizard in Visual Studio 2012.

![](Gettingstarted_images/Gettingstarted_img1.jpeg)

**Adding Web Form**

Add a new Web Form to the project and name it as **Default.aspx**

![](Gettingstarted_images/Gettingstarted_img2.jpeg)

Add below references to the project and set the Copy Local property to **True**

* Syncfusion.Compression.Base
* Syncfusion.Pdf.Base
* Syncfusion.EJ
* Syncfusion.EJ.PdfViewer
* Syncfusion.EJ.Web

**i) PDF viewer using remote service**

Add below code snippet to Default.aspx. Here, PDF viewer uses the hosted service in the remote machine to display the PDF.

{% highlight HTML %}

<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="PdfViewerEJWeb.Default" %>
<%@ Register assembly="Syncfusion.EJ.Web" namespace="Syncfusion.JavaScript.Web" tagprefix="ej" %>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title>PDF viewer</title>
    <link href="assets/css/web/default-theme/ej.web.all.min.css" rel="stylesheet" />
    <script src="assets/external/jquery-2.1.4.min.js"></script>
    <script src="assets/external/jquery.easing.1.3.min.js"></script>
    <script src="assets/scripts/web/ej.web.all.min.js"></script>
</head>
<body>
    <form id="form1" runat="server">
    <div class="control">
        <ej:pdfviewer id="PdfViewer1" Height="800"  
            ServiceUrl="http://js.syncfusion.com/ejServices/api/PdfViewer"
            PdfService="Local"
            runat="server">
        </ej:pdfviewer>
    </div>
    </form>
</body>
</html>
{% endhighlight %}


N> For adding scripts and styles, please refer **Add Scripts and Styles** section of [ejPdfViewer](http://help.syncfusion.com/js/pdfviewer/getting-started)

**ii) PDF viewer using Web API**

Add new folder **WebApi** in the solution and create new Web API Controller Class to it. Name it as **PdfViewerController** and click Add.

![](Gettingstarted_images/Gettingstarted_img3.jpeg)

Replace the below code in the PdfViewerController.cs

{% highlight C# %}
using Newtonsoft.Json;
using Syncfusion.EJ.PdfViewer;
using System.Collections.Generic;
using System.IO;
using System.Web;
using System.Web.Http;
namespace PdfViewerEJWeb.WebApi
{
    public class PdfViewerController : ApiController
    {
        //Post action for processing the PDF documents.
        public object Load(Dictionary<string, string> jsonResult)
        {
            PdfViewerHelper helper = new PdfViewerHelper();
            if (jsonResult.ContainsKey("isInitialLoading"))
                helper.Load(HttpContext.Current.Server.MapPath("~/Data/HTTP Succinctly.pdf"));
            return JsonConvert.SerializeObject(helper.ProcessPdf(jsonResult));
        }

        //Post action for processing the PDF documents when uploading to the ejPdfviewer widget.
        public object FileUpload(Dictionary<string, string> jsonResult)
        {
            PdfViewerHelper helper = new PdfViewerHelper();
            if (jsonResult.ContainsKey("uploadedFile"))
            {
                var fileUrl = jsonResult["uploadedFile"];
                byte[] byteArray = Convert.FromBase64String(fileUrl);
                MemoryStream stream = new MemoryStream(byteArray);
                helper.Load(stream);
            }
            return JsonConvert.SerializeObject(helper.ProcessPdf(jsonResult));
        }

        //Post action for downloading the PDF documents from the ejPdfviewer widget.
        public object Download(Dictionary<string, string> jsonResult)
        {
            PdfViewerHelper helper = new PdfViewerHelper();
            return helper.GetDocumentData(jsonResult);
        }
    }
}

{% endhighlight %}

N> Please, create a folder named **Data** in the project location and add the PDF document to be viewed in PDF viewer.

###Web API Routing

Right-Click the Project, select Add and select Global.asax file from the listed templates.

![](Gettingstarted_images/Gettingstarted_img4.jpeg)

You can route the Web API in Application_Start event in the Global.asax file as follows.

{% highlight C# %}

using System;
using System.Web.Http;
namespace PdfViewerEJWeb
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

Add below code snippet to Default.aspx. Here, PDF viewer uses the Web API to process the PDF.

{% highlight HTML %}

<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="PdfViewerEJWeb.Default" %>
<%@ Register assembly="Syncfusion.EJ.Web" namespace="Syncfusion.JavaScript.Web" tagprefix="ej" %>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title>PDF viewer</title>
    <link href="assets/css/web/default-theme/ej.web.all.min.css" rel="stylesheet" />
    <script src="assets/external/jquery-2.1.4.min.js"></script>
    <script src="assets/external/jquery.easing.1.3.min.js"></script>
    <script src="assets/scripts/web/ej.web.all.min.js"></script>
</head>
<body>
    <form id="form1" runat="server">
    <div class="control">
        <ej:pdfviewer id="PdfViewer1" Height="800"  
            ServiceUrl="api/PdfViewer"
            PdfService="Local"
            runat="server">
        </ej:pdfviewer>
    </div>
    </form>
</body>
</html>

{% endhighlight %}

N> For adding scripts and styles, please refer **Add Scripts and Styles** section of [ejPdfViewer](http://help.syncfusion.com/js/pdfviewer/getting-started)

###Output

Run the sample and you will see the PDF viewer control as in the below screenshot.

![](Gettingstarted_images/Gettingstarted_img5.png)

