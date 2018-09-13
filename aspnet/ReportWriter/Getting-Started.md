---
layout: post
title: Getting started with Syncfusion Essential ReportWriter for ASP.NET Webforms
description: Getting started walk through to create ReportWriter control.
platform: aspnet
control: ReportWriter
documentation: ug
---

# Getting Started with ASP.NET Application

This section describes how to export the Report Server report as PDF, Word, Excel, PPT and HTML formats in ASP.NET application using ReportWriter.

## Project Creation

This section illustrates how to add ReportWriter to the ASP.NET application. It includes the following steps.

Create a new ASP.NET Empty web application project by selecting the WEB category from the listed project template in Microsoft Visual Studio IDE.

![](ASP_Images/Getting-Started_img1.png) 
   
### Create ASPX Page

To create a new Web Forms in the application.

1. Right-Click on the project and select Add.
 
   ![](ASP_Images/Getting-Started_img2.png)

2. Click New Item and select Web Form from the listed templates.

   ![](ASP_Images/Getting-Started_img3.png)

### Add References   

1. In the Solution Explorer, Right-click on the References folder and then click Add Reference.

   ![](ASP_Images/Getting-Started_img4.png) 

2. Add the following assemblies and click OK.
 
   * Syncfusion.Chart.Wpf
   * Syncfusion.Compression.Base
   * Syncfusion.DocIO.Base   
   * Syncfusion.EJ.ReportViewer   
   * Syncfusion.Gauge.Wpf
   * Syncfusion.Linq.Base
   * Syncfusion.Pdf.Base
   * Syncfusion.SfMaps.Wpf
   * Syncfusion.Shared.Wpf
   * Syncfusion.XlsIO.Base  
 
   N> Refer the above assemblies from the installed location, C:\Program Files (x86)\Syncfusion\Essential Studio\ASP.NET\{{ site.releaseversion }}\Assemblies
 
### Registering Assemblies within the Web.config file  

In your application's root web.config file, add the below assembly information within the &lt;assemblies&gt; tag.

~~~html
<system.web>
    <compilation debug="true" targetFramework="4.5">
        <assemblies>
            <add assembly="Syncfusion.Chart.WPF, Version=14.1400.0.42, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89"/>
            <add assembly="Syncfusion.Compression.Base, Version=14.1400.0.42, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89"/>
            <add assembly="Syncfusion.DocIO.Base, Version=14.1400.0.42, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89"/>
            <add assembly="Syncfusion.EJ.ReportViewer, Version=14.1400.0.42, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89"/>
            <add assembly="Syncfusion.Gauge.WPF, Version=14.1400.0.42, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89"/>
            <add assembly="Syncfusion.Linq.Base, Version=14.1400.0.42, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89"/>
            <add assembly="Syncfusion.Pdf.Base, Version=14.1400.0.42, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89"/>
            <add assembly="Syncfusion.SfMaps.WPF, Version=14.1400.0.42, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89"/>
            <add assembly="Syncfusion.Shared.WPF, Version=14.1400.0.42, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89"/>      
            <add assembly="Syncfusion.XlsIO.Base, Version=14.1400.0.42, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89"/>
        </assemblies>
    </compilation>      
</system.web>
~~~

### Registering namespaces within Web.config

Now you need to register the below mentioned two namespaces in the web.config file present within the Views folder as well as the Root directory of your application.

* Syncfusion.EJ.ReportViewer

~~~html
<namespaces>
    <add namespace="System.Web.Mvc"/>
    <add namespace="System.Web.Mvc.Ajax"/>
    <add namespace="System.Web.Mvc.Html"/>    
    <add namespace="System.Web.Routing"/>
    <add namespace="System.Web.WebPages"/>    
    <add namespace="Syncfusion.EJ.ReportViewer"/>
</namespaces>
~~~

## ReportWriter Initialization  

1. Set the following properties to ReportWriter.   

   * ReportPath - Set the local file system or Report Server path of report.
   
   * ReportProcessingMode - Set ProcessingMode as Remote for RDL and Report Server report also Local for RDLC report.
   
   * WriterFormat - Set WriterFormat as PDF, Excel, Word, PPT and HTML.

2. Initialize ReportWriter by using the following code example in the Default.aspx.cs page export button click event.

   ~~~ csharp
   protected void ExportButton_Click(object sender, EventArgs e)
   {
       try
       {
           string fileName = null;
           WriterFormat format;
           HttpContext httpContext = System.Web.HttpContext.Current;
           ReportWriter reportWriter = new ReportWriter();
           reportWriter.ReportPath = Server.MapPath("~/App_Data/GroupingAgg.rdl");
           reportWriter.ReportProcessingMode = ProcessingMode.Remote;

           if (this.ExportFormat.SelectedValue == "PDF")
           {
               fileName = "GroupingAgg.pdf";
               format = WriterFormat.PDF;
           }
           else if (this.ExportFormat.SelectedValue == "Word")
           {
               fileName = "GroupingAgg.doc";
               format = WriterFormat.Word;
           }
           else if (this.ExportFormat.SelectedValue == "Html")
           {
               fileName = "GroupingAgg.Html";
               format = WriterFormat.HTML;
           }
           else if (this.ExportFormat.SelectedValue == "PPT")
           {
               fileName = "GroupingAgg.ppt";
               format = WriterFormat.PPT;
           }
           else
           {
               fileName = "GroupingAgg.xls";
               format = WriterFormat.Excel;
           }
           reportWriter.Save(fileName, format, httpContext.Response);
       }
       catch { }
   }
   ~~~
   
3. Add the following code example in the &lt;body&gt; tag of the Default.aspx page to view ReportWriter export options.

   ~~~ html
   <body>
       <div class="container">
           <div class="header">
               <span style="color: white; font-size: 2em">ReportWriter Demo</span>
           </div>
           <div class="content_section">
               <form id="form1" runat="server">
                   <div id="description_Pane" style="text-align: justify;">
                       <h3>Description</h3>
                       <span>
                           Essential ReportWriter is a powerful control for exporting RDL files into specified
                           format files.The following are some of the key features of this component: Provides
                           support for various chart types that include Area, Bar, Column, Pie, Funnel, Radar,
                           Line and so on. Provides support for both Matrix and Table and also provides support for
                           both single, and multi-level row groupings and column groupings. Provides support
                           for other common controls such as Textbox, Image, Rectangle, Line and both Circular
                           Linear Gauges. Provides support for report parameter.
                       </span>
                   /div>
                   <div id="export_Pane" style="margin-top: 4%;">
                       <h3>Export Report</h3>
                       <span>
                           Choose a file format to view the selected document generated from Report file by using Essential ReportWriter.
                       </span>
                       <div id="selection_Pane" style="margin-top: 2%;">
                           <asp:Label Style="font-size: large;" runat="server">
                               Save As :
                           </asp:Label>

                           <asp:RadioButtonList RepeatLayout="Flow" ID="ExportFormat" RepeatDirection="Horizontal" runat="server">
                               <asp:ListItem Selected="True">PDF</asp:ListItem>
                               <asp:ListItem>Word</asp:ListItem>
                               <asp:ListItem>Excel</asp:ListItem>
                               <asp:ListItem>Html</asp:ListItem>
                               <asp:ListItem>PPT</asp:ListItem>
                           </asp:RadioButtonList>

                           <asp:Button style="width: 18%; margin-left: 2%;" ID="ExportButton" runat="server" OnClick="ExportButton_Click" Text="Generate" />
                       </div>
                   </div>
               </form>
           </div>
       </div>
   </body>   
   ~~~
   
4. Run the application. The following output displays ReportWriter export options, Select the export option and click on Generate button.

   ![](ASP_Images/Getting-Started_img5.png) 
   
5. The following output displays exported report in PDF format.

   ![](ASP_Images/Getting-Started_img6.png)
 
## Generate RDL Reports

The ReportWriter has options to export the RDL reports. The following code example helps you to export the RDL report using ReportWriter.

Specify the `ReportPath`, `ReportProcessingMode` and `WriterFormat` properties for ReportWriter to generate report.

~~~csharp   
string reportPath = @"..\ReportTemplate\GroupingAgg.rdl";
ReportWriter reportWriter = new ReportWriter(reportPath);
reportWriter.ReportProcessingMode = ProcessingMode.Remote;
reportWriter.Save("GroupingAgg.xls", WriterFormat.Excel);
~~~  

## Generate RDLC Reports

The ReportWriter has support to view and save the RDLC reports. The following code helps you to bind data to ReportWriter.

1. Assign `ReportPath`, `ProcessingMode` and `ExportFormat` to ReportWriter.

   ~~~ csharp
   string reportPath = @"..ReportTemplate\RDLC\ProductCatalog.rdlc";
   ReportWriter reportWriter = new ReportWriter(reportPath, dataSources);
   reportWriter.ReportProcessingMode = ProcessingMode.Local;
   reportWriter.Save("ProductCatalog.doc", WriterFormat.WORD);
   ~~~
   
2. Add Datasource to the RDLC report.

   ~~~ csharp
   ReportDataSourceCollection dataSources = new ReportDataSourceCollection();
   dataSources.Add(new ReportDataSource { Name = "ProductCatalog", Value = ProductCatalogSource.GetData() });
   ~~~

3. Assign values for the datasource which is given in the RDLC.

   ~~~ csharp
   #region ProductCatalog Details
   public class ProductCatalogSource
   {
       public string ProdSubCat { get; set; }
       public string ProdModel { get; set; }
       public string ProdCat { get; set; }
       public string Description { get; set; }
       public string ProdName { get; set; }
       public string ProductNumber { get; set; }
       public string Color { get; set; }
       public string Size { get; set; }
       public double? Weight { get; set; }
       public double? StandardCost { get; set; }
       public string Style { get; set; }
       public string Class { get; set; }
       public double? ListPrice { get; set; }
       public static IList GetData()
       {
           List<ProductCatalogSource> datas = new List<ProductCatalogSource>();
           ProductCatalogSource data = null;
           data = new ProductCatalogSource()
           {
               ProdSubCat = "Road Frames",
               ProdModel = "HL Road Frame",
               ProdCat = "Components",
               Description = "Our lightest and best quality aluminum frame made from the newest alloy; it is welded and heat-treated for strength. Our innovative design results in maximum comfort and performance.",
               ProdName = "HL Road Frame - Black, 58",
               ProductNumber = "FR-R92B-58",
               Color = "Black",
               Size = "58",
               Weight = 2.24,
               StandardCost = 1059.3100,
               Style = "U ",
               Class = "H ",
               ListPrice = 1431.5000
           };
           datas.Add(data);
           data = new ProductCatalogSource()
           {
               ProdSubCat = "Road Frames",
               ProdModel = "HL Road Frame",
               ProdCat = "Components",
               Description = "Our lightest and best quality aluminum frame made from the newest alloy; it is welded and heat-treated for strength. Our innovative design results in maximum comfort and performance.",
               ProdName = "HL Road Frame - Red, 58",
               ProductNumber = "FR-R92R-58",
               Color = "Red",
               Size = "58",
               Weight = 2.24,
               StandardCost = 1059.3100,
               Style = "U ",
               Class = "H ",
               ListPrice = 1431.5000
           };
           datas.Add(data);
           data = new ProductCatalogSource()
           {
               ProdSubCat = "Helmets",
               ProdModel = "Sport-100",
               ProdCat = "Accessories",
               Description = "Universal fit, well-vented, lightweight , snap-on visor.",
               ProdName = "Sport-100 Helmet, Red",
               ProductNumber = "HL-U509-R",
               Color = "Red",
               Size = "",
               Weight = null,
               StandardCost = 13.0863,
               Style = "",
               Class = "",
               ListPrice = 34.9900
           };
           datas.Add(data);
           return datas;
       }
   }
   #endregion
   ~~~
   
## Generate SSRS Reports

The ReportWriter has options to export the SSRS reports. The following code example helps you to generate the SSRS report using ReportWriter.

Specify the `ReportPath`, `ReportServerUrl`, `ReportServerCredential`, `ReportProcessingMode` and `WriterFormat` properties for ReportWriter to generate report.

~~~csharp
HttpContext httpContext = System.Web.HttpContext.Current;
ReportWriter reportWriter = new ReportWriter();
reportWriter.ReportPath = "45db67a0-3fd6-4684-b03c-aa640a521c97";
reportWriter.ReportServerUrl = "http://reportserver.syncfusion.com:80/";
reportWriter.ReportingServer = new ReportingServerExt();
reportWriter.ReportServerCredential = new System.Net.NetworkCredential("guest", "demo");
reportWriter.ReportProcessingMode = ProcessingMode.Remote;
reportWriter.Save("GroupingAgg.doc", WriterFormat.Word, httpContext.Response);  
~~~