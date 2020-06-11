---
layout: post
title: Add header and footer in the Exported file (Excel, Word or Pdf) | Grid | ASP.NET Webforms | Syncfusion
description: Add header and footer in the Exported file (Excel, Word or Pdf)
platform: aspnet
control: Grid
documentation: ug
---

# Adding header and footer in the Exported file (Excel, Word or PDF)

We can add header and footer in the exported file while exporting the grid control.

## Adding header and footer in Excel sheet

Using the Range Text property and SetValue method of the XlsIO IRange Class, we can add headers and footers in Excel sheet. 

{% tabs %}

{% highlight html %}

    <ej:Grid ID="FlatGrid" runat="server" AllowSorting="True" OnServerExcelExporting="FlatGrid_ServerExcelExporting" AllowPaging="True">
            <ToolbarSettings ShowToolbar="true" ToolbarItems="excelExport"></ToolbarSettings>
            <Columns>
                <ej:Column Field="OrderID" HeaderText="Order ID" TextAlign="Right"/>
                <ej:Column Field="CustomerID" HeaderText="Customer ID" />
                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" />
                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" />
            </Columns>
    </ej:Grid>
 
        
{% endhighlight %}
{% highlight c# %}

    public partial class GridExporting : System.Web.UI.Page
    { 
        protected void Page_Load(object sender, EventArgs e)
        {
            this.FlatGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            this.FlatGrid.DataBind();
        }        

        protected void FlatGrid_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)
        {
            ExcelExport exp = new ExcelExport();
            IWorkbook book = exp.Export(FlatGrid.Model, (IEnumerable)FlatGrid.DataSource, "Export.xlsx", ExcelVersion.Excel2010, false, false, "flat-lime", true);
            
            // Inserted new row for adding title
            book.ActiveSheet.InsertRow(1);
            
            // Merging the sheet from Range A1 to D1 for adding title space
            book.ActiveSheet.Range["A1:D1"].Merge();
            
            //Adding the title using Text property
            book.ActiveSheet.Range["A1"].Text = "Grid Order Data";
            book.ActiveSheet.Range["A1"].CellStyle.HorizontalAlignment = ExcelHAlign.HAlignCenter;//set text alignment
            
            //Adding footer using SetValue method
            book.ActiveSheet.SetValue(book.ActiveSheet.Rows.Length + 2, book.ActiveSheet.Columns.Length - 3, "CopyRights");
            book.SaveAs("Export.xlsx", ExcelSaveType.SaveAsXLS, System.Web.HttpContext.Current.Response, ExcelDownloadType.Open);
        }
    }

{% endhighlight %}
{% endtabs %}

## Adding header and footer in Exported Word document

We can add header and footer to the word document using the HeadersFooters property in the WHeadersFooters class of the DocIO namespace. We can create an instance of the IWParagraph class and append the header/footer text to it using the AppendText method.

{% tabs %}

{% highlight html %}

    <ej:Grid ID="FlatGrid" runat="server" AllowSorting="True" OnServerWordExporting="FlatGrid_ServerWordExporting" AllowPaging="True">
            <ToolbarSettings ShowToolbar="true" ToolbarItems="wordExport"></ToolbarSettings>
            <Columns>
                <ej:Column Field="OrderID" HeaderText="Order ID" TextAlign="Right"/>
                <ej:Column Field="CustomerID" HeaderText="Customer ID" />
                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" />
                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" />
            </Columns>
    </ej:Grid> 

{% endhighlight %}
{% highlight c# %}

    public partial class GridExporting : System.Web.UI.Page
    { 
        protected void Page_Load(object sender, EventArgs e)
        {
            this.FlatGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            this.FlatGrid.DataBind();
        }        

        protected void FlatGrid_ServerWordExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)
        {
            WordExport exp = new WordExport();
            IWordDocument document = exp.Export(FlatGrid.Model, (IEnumerable)FlatGrid.DataSource, "Export.docx", false, false, "flat-lime", true);
            IWParagraph para = new WParagraph(document);

            //Add header to the word document
            para = document.Sections[0].HeadersFooters.Header.AddParagraph();
            //Insert the header text using AppendText method
            para.AppendText("[Header]");
            //Add footer to the word document
            para = document.Sections[0].HeadersFooters.Footer.AddParagraph();
            //Insert the footer text using AppendText method
            para.AppendText("[Footer]");

            //Adding Title to the Grid
            var index = document.LastSection.Body.ChildEntities.IndexOf(document.LastSection.Tables[0]);
            WParagraph para1 = new WParagraph(document);
            para1.Text = "Grid Title";
            document.LastSection.Body.ChildEntities.Insert(index, para1); 
            document.Save("Export.docx", FormatType.Docx, System.Web.HttpContext.Current.Response, HttpContentDisposition.Attachment);
        }

    }
    
{% endhighlight %}
{% endtabs %}

## Adding header and footer in Exported PDF document

We can add header/footer to a PDF documents using PdfPageTemplateElement class. The header and footer can contain any types of element including dynamic fields.

{% tabs %}

{% highlight html %}

   <ej:Grid ID="FlatGrid" runat="server" AllowSorting="True" OnServerPdfExporting="FlatGrid_ServerPdfExporting" AllowPaging="True">
            <ToolbarSettings ShowToolbar="true" ToolbarItems="pdfExport"></ToolbarSettings>
            <Columns>
                <ej:Column Field="OrderID" HeaderText="Order ID" TextAlign="Right"/>
                <ej:Column Field="CustomerID" HeaderText="Customer ID" />
                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" />
                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" />
            </Columns>
    </ej:Grid>  
        
{% endhighlight %}
{% highlight c# %}

    public partial class GridExporting : System.Web.UI.Page
    { 
        protected void Page_Load(object sender, EventArgs e)
        {
            this.FlatGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            this.FlatGrid.DataBind();
        }        

        protected void FlatGrid_ServerPdfExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)
        {
            PdfExport exp = new PdfExport();
            PdfDocument pdfDocument = exp.Export(FlatGrid.Model, (IEnumerable)FlatGrid.DataSource, "Export.pdf", false, false, "flat-lime", true);
            
            RectangleF rect = new RectangleF(0, 0, pdfDocument.PageSettings.Width, 50);
            
            //create a header pager template
            PdfPageTemplateElement header = new PdfPageTemplateElement(rect);
            
            //create a footer pager template
            PdfPageTemplateElement footer = new PdfPageTemplateElement(rect);

            Font  f = new Font("Helvetica", 10, FontStyle.Bold);

            PdfFont font = new PdfTrueTypeFont(f, true);
            
            header.Graphics.DrawString("Demo Report", font, PdfBrushes.Black, new Point(250, 0)); //Add custom text to the Header
            pdfDocument.Template.Top = header; //Append custom template to the document           
            
            footer.Graphics.DrawString("CopyRights", font, PdfBrushes.Gray, new Point(250, 0));//Add Custom text to footer
            pdfDocument.Template.Bottom = footer;//Add the footer template to document
            
            pdfDocument.Save("Export.pdf", Response, HttpReadType.Save);
        }


    }
    
{% endhighlight %}
{% endtabs %}