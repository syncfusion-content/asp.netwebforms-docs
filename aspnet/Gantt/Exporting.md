---
layout: post
title: Exporting| Gantt | ASP.NET MVC | Syncfusion
description: exporting
platform: ejmvc
control: Gantt
documentation: ug
---
# Export

Exporting feature provides support to export Gantt content to excel and PDF files. To export the contents, the `ExcelExport` and `PdfExport` toolbar items must be added in the toolbar using the `ToolbarItems` property of `ToolbarSettings`. When you click, the toolbar exporting icons, it internally invokes the export public method of Gantt object to export.

The below code snippet explains the above behavior,

{% tabs %}
{% highlight html %}

<ej:Gantt runat="server" ID="GanttControlExporting" OnServerPdfExporting="GanttControlExporting_ServerPdfExporting">
<ToolbarSettings ShowToolbar="true" ToolbarItems="pdfExport, excelExport" />
</ej:Gantt>

{% endhighlight %}

{% highlight c# %}

    public partial class GanttExporting : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            TaskDetailsCollection TaskCollection = new TaskDetailsCollection();
            this.GanttControlExporting.DataSource = TaskCollection.GetDataSource();
            this.GanttControlExporting.DataBind();
        }

        protected void GanttControlExporting_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.GanttEventArgs e)
        {
            ExcelExport exp = new ExcelExport();
            GanttExportSettings settings = new GanttExportSettings();
            settings.Theme = ExportTheme.FlatLime;
            exp.Export(this.GanttControlExporting.Model, (IEnumerable)this.GanttControlExporting.DataSource, "Export.xlsx", ExcelVersion.Excel2010, new GanttExportSettings() { Theme = ExportTheme.FlatLime });
        }

        protected void GanttControlExporting_ServerPdfExporting(object sender, Syncfusion.JavaScript.Web.GanttEventArgs e)
        {
            PdfExport exp = new PdfExport();
            GanttPdfExportSettings settings = new GanttPdfExportSettings();
            settings.EnableFooter = true;
            settings.ProjectName = "Project Tracker";
            settings.Locale = e.Arguments["locale"].ToString();
            settings.Theme = GanttExportTheme.FlatLime;
            exp.Export(this.GanttControlExporting.Model, (IEnumerable)this.GanttControlExporting.DataSource, settings, "Gantt");
        }
    }

{% endhighlight %}
{% endtabs %} 

The below screen shot shows Gantt with excel and Pdf exporting enabled.
![](Export_images/Export_img1.png)

## Server dependencies
Export Helper functions are available in the Assembly `Syncfusion.EJ.Export`, which is available in the Essential Studio & Essential ASP.NET builds. The list of assemblies needed for Gantt Export as follows

* Syncfusion.EJ
* Syncfusion.EJ.Export
* Syncfusion.Linq.Base
* Syncfusion.Compression.Base
* Syncfusion.XlsIO.Base
* Syncfusion.PDF.Base

## Supported Export Types
Currently server helper function allows following two types of exporting.

* Excel
* PDF

## Multiple exporting
Multiple export is used for export more than one Gantt object in the same file. 

The following code example describes exporting multiple Gantt

{% tabs %} 
{% highlight html %}

 <ej:Gantt runat="server" ID="GanttControlExporting" ChildMapping="SubTasks" TreeColumnIndex="1" IsResponsive="true" 
            OnServerExcelExporting="GanttControlExporting_ServerExcelExporting" 
            OnServerPdfExporting="GanttControlExporting_ServerPdfExporting"
            Load="load">
            <ToolbarSettings ShowToolbar="true" ToolbarItems="excelExport, pdfExport" />
 </ej:Gantt>

 <ej:Gantt runat="server" ID="GanttControlDesign" ChildMapping="SubTasks" TreeColumnIndex="1" Load="load">

 </ej:Gantt>

 <ej:Gantt runat="server" ID="GanttControlImplementation" ChildMapping="SubTasks" TreeColumnIndex="1" Load="load">
 
 </ej:Gantt>

{% endhighlight %}

{% highlight c# %}

    public partial class GanttMultipleExporting : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            ExportTaskDetailsCollection TaskCollection = new ExportTaskDetailsCollection();
            this.GanttControlExporting.DataSource = TaskCollection.GetDataSource();
            this.GanttControlExporting.DataBind();
            this.GanttControlDesign.DataSource = TaskCollection.GetDesignPhaseDataSource();
            this.GanttControlDesign.DataBind();
            this.GanttControlImplementation.DataSource = TaskCollection.GetImplementationPhaseDataSource();
            this.GanttControlImplementation.DataBind();
        }
        protected void GanttControlExporting_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.GanttEventArgs e)
        {
            ExcelExport exp = new ExcelExport();
            IWorkbook document = exp.Export(this.GanttControlExporting.Model, (IEnumerable)this.GanttControlExporting.DataSource, new GanttExportSettings() { Theme = ExportTheme.FlatLime }, true, "Planning Phase");
            document = exp.Export(this.GanttControlDesign.Model, (IEnumerable)this.GanttControlDesign.DataSource, new GanttExportSettings() { Theme = ExportTheme.FlatLime }, "Export", document, true, "Design Phase");
            exp.Export(this.GanttControlImplementation.Model, (IEnumerable)this.GanttControlImplementation.DataSource, new GanttExportSettings() { Theme = ExportTheme.FlatLime }, "Export.xlsx", document, false, "Implementation Phase");
        }

        protected void GanttControlExporting_ServerPdfExporting(object sender, Syncfusion.JavaScript.Web.GanttEventArgs e)
        {
            PdfExport exp = new PdfExport();
            GanttPdfExportSettings settings = new GanttPdfExportSettings();
            settings.Theme = GanttExportTheme.FlatLime;
            settings.Locale = e.Arguments["locale"].ToString();
            PdfDocument document = exp.Export(this.GanttControlExporting.Model, (IEnumerable)this.GanttControlExporting.DataSource, settings, false);
            document = exp.Export(this.GanttControlDesign.Model, (IEnumerable)this.GanttControlDesign.DataSource, settings, document, false);
            exp.Export(this.GanttControlImplementation.Model, (IEnumerable)this.GanttControlImplementation.DataSource, settings, "Gantt", document, true);
        }

    }

{% endhighlight %}
{% endtabs %} 

## Export Theme
The Gantt export supports the below themes, 

* flat-azure
* flat-azure-dark
* flat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark
* bootstrap-theme

The desired theme should be passed as a parameter to the Export method and the code snippet for this as follows

{% highlight c# %}

        protected void GanttControlExporting_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.GanttEventArgs e)
          {
            ExcelExport exp = new ExcelExport();
            GanttExportSettings settings = new GanttExportSettings();
            settings.Theme = ExportTheme.FlatLime;
            exp.Export(this.GanttControlExporting.Model, (IEnumerable)this.GanttControlExporting.DataSource, "Export.xlsx", ExcelVersion.Excel2010, new GanttExportSettings() { Theme = ExportTheme.FlatLime });
          }

{% endhighlight %}