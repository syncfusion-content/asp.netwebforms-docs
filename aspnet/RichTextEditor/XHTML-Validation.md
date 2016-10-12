---
layout: post
title: XHTML Validation in RichTextEditor control for Syncfusion Essential ASP.NET Webform
description: XHTML Validation to format the RichTextEditor control's content
platform: aspnet
control: RTE
documentation: ug
keywords: RichTextEditor, XHTML Validation, RTE import, RTE export, export to PDF, export to Word

---
# XHTML Validation

The editor provides option to validate its content through the EnableXHTML property. When you set or modify the content into the editor, it continuously checks whether the HTML source of the content that you are creating is valid. The editor examines the HTML markup and then removes the elements or attributes that are not valid. 

{% highlight html %}

  <ej:RTE ID="RTE1" runat="server" EnableXHTML="true">
      <RTEContent>
              The Rich Text Editor  (RTE) control is an easy to render in client side. Customer easy to edit the contents and get the HTML content for the displayed content. A rich text editor control provides users with a toolbar that helps them to apply rich text formats to the text entered  in the text area.
      </RTEContent>
  </ej:RTE>
    
{% endhighlight %}

The editor checks the following settings on validation:

* **Attributes** 
  * Must be specified in lowercase 
  * Proper use of quotation marks around the attributes
  * Must be valid attributes for corresponding HTML element
  * All the required attributes must be included in the HTML element
  * Accepts the allowed values alone such as true or false.
* **HTML** **Elements** 
  * Must be in lowercase 
  * All opening tags must be closed
  * Allows only the valid HTML elements

  
# Import 

Import feature provides support to import a word document into the editor textarea. To enable import option in the RTE tool bar,  `import` toolbar items needs to be added in RTE toolbar toolsList using `importExport` which adds the tool in the toolbar. In `ImportSettings` Url option, the server page for import is needed to be mapped. When you click the toolbar import icon, it opens a dialog to browse the select a word file. The selected word file will be imported into the editor textarea.

{% tabs %}
 
{% highlight html %}

    <ej:RTE ID="ImportExportSample" Width="100%" Height="100%"  runat="server" MinWidth="200px" >
        <RTEContent>
            &lt;p&gt;The Rich Text Editor (RTE) control is an easy to render in
            client side. Customer easy to edit the contents and get the HTML content for
            the displayed content. A rich text editor control provides users with a toolbar
            that helps them to apply rich text formats to the text entered in the text
            area. &lt;/p&gt;
        </RTEContent>
        <ImportSettings Url="Import.ashx" />
        <Tools ImportExport="import"></Tools>
    </ej:RTE>



{% endhighlight  %}
{% highlight c# %}

    public class Import : IHttpHandler
    {

        public void ProcessRequest(HttpContext context)
        {
            HttpContext.Current.Response.Write(ImportDoc());
        }
        public string ImportDoc()
        {
            string HtmlString = string.Empty;
            if (HttpContext.Current.Request.Files.AllKeys.Any())
            {
                string RTEID = HttpContext.Current.Request.QueryString["rteid"];
                var fileName = RTEID + "_importUpload";
                var httpPostedFile = HttpContext.Current.Request.Files[fileName];
                if (httpPostedFile != null)
                {
                    using (var mStream = new MemoryStream())
                    {
                        new WordDocument(httpPostedFile.InputStream).Save(mStream, FormatType.Html);
                        mStream.Position = 0;
                        HtmlString = new StreamReader(mStream).ReadToEnd();
                    };

                    HtmlString = ExtractBodyContent(HtmlString);

                    foreach (var item in DecodeKeys())
                    {
                        HtmlString = HtmlString.Replace(item.Key, item.Value);
                    }
                }
                else HttpContext.Current.Response.Write("Select any file to upload.");

            }
            return HtmlString;
        }
        public string ExtractBodyContent(string html)
        {
            if (html.Contains("<html") && html.Contains("<body"))
            {
                return html.Remove(0, html.IndexOf("<body>") + 6).Replace("</body></html>", "");

            }
            return html;
        }

        public IDictionary<string, string> DecodeKeys()
        {
            IDictionary<string, string> KeyValuePair = new Dictionary<string, string>()
            {
               {"\"", "'"},{"\r", " "},{"\n", "<br/> "},{"\r\n", " "},{"( )+", " "},{"&nbsp;", " "},{"&bull;", "*"},{"&lsaquo;", "<"},
               {"&rsaquo;", ">"},{"&trade;", "(tm)"},{"&copy;", "(c)"},{"&reg;", "(r)"}
            };

            return KeyValuePair;
        }

        public bool IsReusable
        {
            get
            {
                return false;
            }
        }
    }

{% endhighlight  %}
{% endtabs %} 

## Server Dependencies

Full list of assemblies needed for RTE Import are as follows

    1.  Syncfusion.EJ
    2.  Syncfusion.EJ.Export
    3.  Syncfusion.Linq.Base
    4.  Syncfusion.Compression.Base
    5.  Syncfusion.DocIO.Base

![](XHTML-Validation_images/import_images.png)

# Export 

Export feature provides support to export editor textarea content into word and PDF files. To enable Export option in the RTE tool bar,  `wordExport` , `pdfExport` toolbar items needs to be added in RTE toolbar toolsList using `importExport` which adds the tool in the toolbar. `ExportToWordSettings` consists of Url and FileName sub properties. In Url property, the server page for export to word is needed to be mapped and In FileName property, the name for the exported word file is given. `ExportToPdfSettings` consists of Url and FileName sub properties. In Url property, the server page for export to pdf is needed to be mapped and In FileName property, the name for the exported pdf file is given. When you click the toolbar pdfExport or wordExport icon, it performs server side XHTML Validation on the editor textarea content and exports it into a Word or pdf File.

{% tabs %}
 
{% highlight html %}

    <ej:RTE ID="ImportExportSample" Width="100%" Height="100%"  runat="server" MinWidth="200px" >
        <RTEContent>
            &lt;p&gt;The Rich Text Editor (RTE) control is an easy to render in
            client side. Customer easy to edit the contents and get the HTML content for
            the displayed content. A rich text editor control provides users with a toolbar
            that helps them to apply rich text formats to the text entered in the text
            area. &lt;/p&gt;
        </RTEContent>
        <ExportToWordSettings Url="ImportExport.aspx/ExportToWord" FileName="WordExport" />
        <ExportToPdfSettings Url="ImportExport.aspx/ExportToPDF" FileName="PdfExport" />
        <Tools  ImportExport="wordExport,pdfExport"></Tools>
    </ej:RTE>



{% endhighlight  %}
{% highlight c# %}

    public partial class ImportExport : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            string exportDoc = "ImportExport.aspx/ExportToWord",  exportPdf = "ImportExport.aspx/ExportToPDF";
            string RequestURL = HttpContext.Current.Request.Url.ToString();           
            if (RequestURL.Contains(exportDoc)) ExportToWord();
            else if (RequestURL.Contains(exportPdf)) ExportToPDF();
        }
        
        //Export to Word Document
        public void ExportToWord()
        {

            string RTEID = HttpContext.Current.Request.QueryString["rteid"];
            string FileName = HttpContext.Current.Request.Params[RTEID + "_inputFile"];
            string htmlText = HttpContext.Current.Request.Params[RTEID + "_inputVal"];
            WordDocument document = GetDocument(htmlText);
            document.Save(FileName + ".docx", FormatType.Docx, HttpContext.Current.Response, HttpContentDisposition.Attachment);
        }

        //Export to PDF Document
        public void ExportToPDF()
        {
            string RTEID = HttpContext.Current.Request.QueryString["rteid"];
            string FileName = HttpContext.Current.Request.Params[RTEID + "_inputFile"];
            string htmlText = HttpContext.Current.Request.Params[RTEID + "_inputVal"];
            WordDocument document = GetDocument(htmlText);
            DocToPDFConverter converter = new DocToPDFConverter();
            PdfDocument pdfDocument = converter.ConvertToPDF(document);
            pdfDocument.Save(FileName + ".pdf", HttpContext.Current.Response, HttpReadType.Save);
        }


        public  WordDocument GetDocument(string htmlText)
        {
            WordDocument document = null;
            MemoryStream stream = new MemoryStream();
            StreamWriter writer = new StreamWriter(stream, System.Text.Encoding.Default);
            htmlText = htmlText.Replace("\"", "'");
            XmlConversion XmlText = new XmlConversion(htmlText);
            XhtmlConversion XhtmlText = new XhtmlConversion(XmlText);
            writer.Write(XhtmlText.ToString());
            writer.Flush();
            stream.Position = 0;
            document = new WordDocument(stream, FormatType.Html, XHTMLValidationType.None);
            return document;
        }
    }

{% endhighlight  %}
{% endtabs %} 

## Server Dependencies

Export Helper functions are available in the Assembly `Syncfusion.EJ.Export`, which is available in the Essential Studio builds. Full list of assemblies needed for RTE Export as follows

    1.  Syncfusion.EJ
    2.  Syncfusion.EJ.Export
    3.  Syncfusion.Linq.Base
    4.  Syncfusion.Compression.Base
    5.  Syncfusion.DocIO.Base
    6.  Syncfusion.PDF.Base


![](XHTML-Validation_images/export_images.png)
![](XHTML-Validation_images/export_pdf_images.png)