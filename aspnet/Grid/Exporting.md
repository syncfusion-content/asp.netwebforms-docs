---
layout: post
title: Exporting | Grid | ASP.NET Webforms | Syncfusion
description: Learn here all about exporting support in Syncfusion ASP.NET Webforms Grid Control, its elements, and more.
platform: aspnet
control: Grid
documentation: ug
---

# Exporting in ASP.NET Webforms Grid

Exporting feature provides support to export Grid data into excel, word and PDF files. The tool bar has ExcelExport, WordExport, PdfExport icons that are used to perform exporting. When you click the toolbar exporting icon, it internally invokes the export() public method of Grid object to make export. You can also invoke export() method manually to make export.

## Server dependencies

Export Helper functions are available in the assembly `Syncfusion.EJ.Export`, which is available in the Essential Studio builds. The list of assemblies needed for the grid export is as follows.

    1.  Syncfusion.EJ
    2.  Syncfusion.EJ.Export
    3.  Syncfusion.Linq.Base
    4.  Syncfusion.Compression.Base
    5.  Syncfusion.DocIO.Base
    6.  Syncfusion.XlsIO.Base
    7.  Syncfusion.PDF.Base

## ASP

In ASP, exporting is achieved by using Grid control server side method. Using Export() server method in Grid server side event, you can export the Grid into excel, PDF and word documents.

N> Refer the knowledge base [link](https://www.syncfusion.com/kb/5442/how-to-export-the-data-when-grid-is-in-updatepanel "link") to export the Grid when it is rendered inside UpdatePanel.

{% tabs %}

{% highlight html %}




<ej:Grid ID="FlatGrid" runat="server" AllowSorting="true" OnServerWordExporting="FlatGrid_ServerWordExporting" OnServerPdfExporting="FlatGrid_ServerPdfExporting" OnServerExcelExporting="FlatGrid_ServerExcelExporting" AllowPaging="true">

            <ToolbarSettings ShowToolbar="true" ToolbarItems="excelExport,wordExport,pdfExport"></ToolbarSettings>

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" TextAlign="Right"/>

                <ej:Column Field="CustomerID" HeaderText="Customer ID" />

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" />

                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" />

                <ej:Column Field="OrderDate" HeaderText="Order Date" TextAlign="Right" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" />

            </Columns>

        </ej:Grid>
{% endhighlight  %}
{% highlight c# %}




public partial class ExcelExporting : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }

        private void BindDataSource()

        {

            int code = 10000;

            for (int i = 1; i < 10; i++)

            {

                order.Add(new Orders(code + 1, "ALFKI", i + 0, 2.3 * i, new DateTime(1991, 05, 15), "Berlin"));

                order.Add(new Orders(code + 2, "ANATR", i + 2, 3.3 * i, new DateTime(1990, 04, 04), "Madrid"));

                order.Add(new Orders(code + 3, "ANTON", i + 1, 4.3 * i, new DateTime(1957, 11, 30), "Cholchester"));

                order.Add(new Orders(code + 4, "BLONP", i + 3, 5.3 * i, new DateTime(1930, 10, 22), "Marseille"));

                order.Add(new Orders(code + 5, "BOLID", i + 4, 6.3 * i, new DateTime(1953, 02, 18), "Tsawassen"));

                code += 5;

            }

            this.FlatGrid.DataSource = order;

            this.FlatGrid.DataBind();

        }



        [Serializable]

        public class Orders

        {

            public Orders()

            {



            }

            public Orders(long OrderId, string CustomerId, int EmployeeId, double Freight, DateTime OrderDate, string ShipCity)

            {

                this.OrderID = OrderId;

                this.CustomerID = CustomerId;

                this.EmployeeID = EmployeeId;

                this.Freight = Freight;

                this.OrderDate = OrderDate;

                this.ShipCity = ShipCity;

            }

            public long OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public double Freight { get; set; }

            public DateTime OrderDate { get; set; }

            public string ShipCity { get; set; }

        }



        protected void FlatGrid_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)

        {

            ExcelExport exp = new ExcelExport();

            exp.Export(FlatGrid.Model, (IEnumerable)FlatGrid.DataSource, "Export.xlsx", ExcelVersion.Excel2010, true, true, "flat-lime");

        }



        protected void FlatGrid_ServerWordExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)

        {

            WordExport exp = new WordExport();

            exp.Export(FlatGrid.Model, (IEnumerable)FlatGrid.DataSource, "Export.docx", true, true, "flat-lime");

        }



        protected void FlatGrid_ServerPdfExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)

        {

            PdfExport exp = new PdfExport();

            exp.Export(FlatGrid.Model, (IEnumerable)FlatGrid.DataSource, "Export.pdf", true, true, "flat-lime");

        }

    }
{% endhighlight  %}

{% endtabs %}

![Exporting_images1](Exporting_images/Exporting_img1.png)

##  Multiple exporting

We can handle the multiple Grid exporting in server side while exporting the Grid to various files such as Excel, PDF, Word.

{% tabs %}

{% highlight html %}

<div>
        Employee Grid
    </div>
    <div>
        <ej:Grid ID="EmployeesGrid" runat="server" OnServerExcelExporting="EmployeesGrid_ServerExcelExporting" OnServerWordExporting="EmployeesGrid_ServerWordExporting" OnServerPdfExporting="EmployeesGrid_ServerPdfExporting" AllowSelection="True">
            <ToolbarSettings ShowToolbar="true" ToolbarItems="excelExport,wordExport,pdfExport"></ToolbarSettings>
            <Columns>
                <ej:Column Field="EmployeeID" HeaderText="Employee ID" IsPrimaryKey="true" TextAlign="Right" Width="100" />
                <ej:Column Field="FirstName" HeaderText="First Name" Width="100" />
                <ej:Column Field="LastName" HeaderText="Last Name" Width="100" />
                <ej:Column Field="Title" HeaderText="Title" Width="90" />
                <ej:Column Field="BirthDate" HeaderText="Birth Date" Width="100" TextAlign="Right" Format="{0:MM/dd/yyyy}" />
                <ej:Column Field="Country" HeaderText="Country" Width="120" />
            </Columns>
        </ej:Grid>
    </div>
    <div>
        Orders Grid
    </div>
    <div>
        <ej:Grid ID="OrdersGrid" runat="server" AllowPaging="False">
            <Columns>
                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />
                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="80" />
                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="75" />
                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="75" Format="{0:C}" />
                <ej:Column Field="OrderDate" HeaderText="Order Date" Width="80" TextAlign="Right" Format="{0:MM/dd/yyyy}" />
                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="110" />
            </Columns>
        </ej:Grid>
    </div>

{% endhighlight  %}
{% highlight c# %}

        protected void EmployeesGrid_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)
        {
            ExcelExport exp = new ExcelExport();
            IWorkbook workbook = exp.Export(EmployeesGrid.Model, (IEnumerable)EmployeesGrid.DataSource, "Export.xlsx", ExcelVersion.Excel2010, true, true, "flat-lime", true);
            exp.Export(OrdersGrid.Model, (IEnumerable)OrdersGrid.DataSource, "Export.xlsx", ExcelVersion.Excel2010, true, true, "flat-lime", false, workbook, MultipleExportType.AppendToSheet, "Orders Grid");
        }

        protected void EmployeesGrid_ServerWordExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)
        {
            WordExport exp = new WordExport();
            IWordDocument document = exp.Export(EmployeesGrid.Model, (IEnumerable)EmployeesGrid.DataSource, "Export.docx", true, true, "flat-lime", true);
            exp.Export(OrdersGrid.Model, (IEnumerable)OrdersGrid.DataSource, "Export.docx", true, true, "flat-lime", false, document, "Second Grid");
        }

        protected void EmployeesGrid_ServerPdfExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)
        {
            PdfExport exp = new PdfExport();
            PdfDocument document = exp.Export(EmployeesGrid.Model, (IEnumerable)EmployeesGrid.DataSource, "Export.pdf", true, true, "flat-lime", true);
            exp.Export(OrdersGrid.Model, (IEnumerable)OrdersGrid.DataSource, "Export.pdf", true, true, "flat-lime", false, document, "Second Grid");
        }
        
{% endhighlight  %}

{% endtabs %}

## ColumnTemplate Exporting

To export the grid with columnTemplate we have to set `IsTemplateColumnIncluded` as true in the parameter of the export method. You can handle the template elements in server side event while exporting grid to various files such as Excel, PDF and Word.

The server side events available in template column exporting and its argument types are listed in the following table.

<table>
<tr>
<th>
Event Name
</th>
<th>
Argument
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
ServerExcelColumnTemplateInfo
</td>
<td>
currentCell, Row
</td>
<td>
It returns the current cell and row of excel sheet.
</td>
</tr>
<tr>
<td>
ServerWordColumnTemplateInfo
</td>
<td>
currentCell, Row
</td>
<td>
It returns the current cell and row of word.
</td>
</tr>
<tr>
<td>
ServerPdfColumnTemplateInfo
</td>
<td>
currentCell, Row
</td>
<td>
It returns the current cell and row of PDF.
</td>
</tr>
</table>

You can modify the template column of exporting files using server events. The code snippet for this is

{% tabs %}

{% highlight html %}

<script type="text/x-jsrender" id="columnTemplate">
        <a href="https://www.syncfusion.com">{{:FirstName}}</a>
</script>

<ej:Grid ID="EmployeesGrid" runat="server" AllowPaging="true" OnServerExcelExporting="EmployeesGrid_ServerExcelExporting" OnServerWordExporting="EmployeesGrid_ServerWordExporting" OnServerPdfExporting="EmployeesGrid_ServerPdfExporting" OnServerExcelColumnTemplateInfo="EmployeesGrid_ServerExcelColumnTemplateInfo" OnServerWordColumnTemplateInfo="EmployeesGrid_ServerWordColumnTemplateInfo" OnServerPdfColumnTemplateInfo="EmployeesGrid_ServerPdfColumnTemplateInfo">
     <ToolbarSettings ShowToolbar="true" ToolbarItems="excelExport,wordExport,pdfExport"></ToolbarSettings>
        <Columns>
            <ej:Column HeaderText="First Name" Template="#columnTemplate" TextAlign="Center" Width="110" />
            <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="100" />
            <ej:Column Field="LastName" HeaderText="Last Name" Width="100" />
            <ej:Column Field="BirthDate" HeaderText="Birth Date" TextAlign="Right" Width="100" Format="{0:MM/dd/yyyy}" />
            <ej:Column Field="Country" Width="100" HeaderText="Country" />
        </Columns>
   </ej:Grid>

{% endhighlight %}

{% highlight c# %}

public partial class ColumnTemplateExporting : System.Web.UI.Page
{
    List<Orders> order = new List<Orders>();

    protected void Page_Load(object sender, EventArgs e)
    {
       BindDataSource();
    }

    private void BindDataSource()
    {
       order.Add(new Orders(1, "Nancy", "Davolio", new DateTime(1948, 12, 08), "USA"));
       order.Add(new Orders(2, "Andrew", "Fuller", new DateTime(1952, 02, 19), "USA"));
       order.Add(new Orders(3, "Janet", "Leverling", new DateTime(1963, 08, 30), "USA"));
       order.Add(new Orders(4, "Margaret", "Peacock", new DateTime(1937, 09, 19), "USA"));
       order.Add(new Orders(5, "Steven", "Buchanan", new DateTime(1955, 03, 04), "UK"));
       order.Add(new Orders(6, "Michael", "Suyama", new DateTime(1963, 07, 02), "UK"));
       order.Add(new Orders(7, "Robert", "King", new DateTime(1960, 05, 29), "UK"));
       order.Add(new Orders(8, "Laura", "Callahan", new DateTime(1958, 01, 09), "USA"));

       this.EmployeesGrid.DataSource = order;
       this.EmployeesGrid.DataBind();
    }

    [Serializable]
    public class Orders
    {
       public Orders()
       {

       }
       public Orders(int EmployeeId, string FirstName, string LastName, DateTime BirthDate, string Country)
       {
          this.EmployeeID = EmployeeId;
          this.FirstName = FirstName;
          this.LastName = LastName;
          this.BirthDate = BirthDate;
          this.Country = Country;
        }
        
        public int EmployeeID { get; set; }
        public string FirstName { get; set; }
        public string LastName { get; set; }
        public DateTime BirthDate { get; set; }
        public string Country { get; set; }
    }

    protected void EmployeesGrid_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)
    {
        ExcelExport exp = new ExcelExport();
        GridProperties obj = ConvertGridObject(e.Arguments["model"].ToString());
        GridExcelExport exp1 = new GridExcelExport() {  IsTemplateColumnIncluded = true, Theme = "flat-lime", FileName = "Export.xlsx" };
        exp.Export(obj, (IEnumerable)EmployeesGrid.DataSource, exp1);
    }

    protected void EmployeesGrid_ServerWordExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)
    {
        WordExport exp = new WordExport();
        GridProperties obj = ConvertGridObject(e.Arguments["model"].ToString());
        GridWordExport exp1 = new GridWordExport() { IsTemplateColumnIncluded = true, Theme = "flat-lime", FileName = "Export.docx" };
        exp.Export(obj, (IEnumerable)EmployeesGrid.DataSource, exp1);
    }

    protected void EmployeesGrid_ServerPdfExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)
    {
        PdfExport exp = new PdfExport();
        GridProperties obj = ConvertGridObject(e.Arguments["model"].ToString());
        GridPdfExport exp1 = new GridPdfExport() { IsTemplateColumnIncluded = true, Theme = "flat-lime", FileName = "Export.pdf" };
        exp.Export(obj, (IEnumerable)EmployeesGrid.DataSource, exp1);
    }

    private GridProperties ConvertGridObject(string gridProperty)
    {
       JavaScriptSerializer serializer = new JavaScriptSerializer();
       IEnumerable div = (IEnumerable)serializer.Deserialize(gridProperty, typeof(IEnumerable));
       GridProperties gridProp = this.EmployeesGrid.Model;
       foreach (KeyValuePair<string, object> data in div)
       {
          var property = gridProp.GetType().GetProperty(data.Key, BindingFlags.Instance | BindingFlags.Public | BindingFlags.IgnoreCase);

          if (property != null)
          {
             Type type = property.PropertyType;
             string serialize = serializer.Serialize(data.Value);
             object value = serializer.Deserialize(serialize, type);
             property.SetValue(gridProp, value, null);
          }
        }
        return gridProp;
     }

     protected void EmployeesGrid_ServerExcelColumnTemplateInfo(object arg1, object arg2)
     {
        IRange range = (IRange)arg1;
        object templates;
        foreach (var data in arg2.GetType().GetProperties())
        {
            if (range.Value.Contains(data.Name))
            {
              templates = arg2.GetType().GetProperty(data.Name).GetValue(arg2, null);
              range.Value = range.Value.Replace(data.Name, templates.ToString());
              var regex = new Regex("<a [^>]*href=(?:'(?<href>.*?)')|(?:\"(?<href>.*?)\")", RegexOptions.IgnoreCase);
              var urls = regex.Matches(range.Value.ToString()).OfType<Match>().Select(m => m.Groups["href"].Value).SingleOrDefault();
              IHyperLink hyperlink = (range.Parent as Syncfusion.XlsIO.Implementation.WorksheetImpl).HyperLinks.Add(range);
              hyperlink.Type = ExcelHyperLinkType.Url;
              hyperlink.TextToDisplay = templates.ToString();
              hyperlink.Address = urls;
            }
          }
     }

     protected void EmployeesGrid_ServerWordColumnTemplateInfo(object arg1, object arg2)
     {
        WTableCell wCell = (WTableCell)arg1;
        object templates;
        foreach (var data in arg2.GetType().GetProperties())
        {
            if (wCell.LastParagraph.Text.ToString().Contains(data.Name))
            {
                templates = arg2.GetType().GetProperty(data.Name).GetValue(arg2, null);
                var regex = new Regex("<a [^>]*href=(?:'(?<href>.*?)')|(?:\"(?<href>.*?)\")", RegexOptions.IgnoreCase);
                var urls = regex.Matches(wCell.LastParagraph.Text).OfType<Match>().Select(m => m.Groups["href"].Value).SingleOrDefault();
                wCell.LastParagraph.Text = "";
                IWField field = wCell.LastParagraph.AppendHyperlink(urls, templates.ToString(), HyperlinkType.WebLink);
            }
        }
    }

    protected void EmployeesGrid_ServerPdfColumnTemplateInfo(object arg1, object arg2)
    {
        Syncfusion.Pdf.Grid.PdfGridCell range = (Syncfusion.Pdf.Grid.PdfGridCell)arg1;
        object templates;
        range.Value = Uri.UnescapeDataString(range.Value.ToString());
        foreach (var data in arg2.GetType().GetProperties())
        {
            if (range.Value.ToString().Contains(data.Name))
            {
                templates = arg2.GetType().GetProperty(data.Name).GetValue(arg2, null);
                var regex = new Regex("<a [^>]*href=(?:'(?<href>.*?)')|(?:\"(?<href>.*?)\")", RegexOptions.IgnoreCase);
                var urls = regex.Matches(range.Value.ToString()).OfType<Match>().Select(m => m.Groups["href"].Value).SingleOrDefault();
                RectangleF rectangle = new RectangleF(10, 40, 30, 30);
                PdfUriAnnotation uriAnnotation = new PdfUriAnnotation(rectangle, urls);
                uriAnnotation.Text = templates.ToString();
                range.Value = uriAnnotation;
            }
        }
    }
}

{% endhighlight %}

{% endtabs %}

## DetailTemplate Exporting

To export the grid with detail template we have to set `IncludeDetailRow` as true in the parameter of the export method. You can handle template elements using server side event while exporting grid to various files such as Excel, PDF and Word.

The server side events available in detail template exporting and its argument types are listed in the following table.

<table>
<tr>
<th>
Event Name
</th>
<th>
Argument
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
ServerExcelDetailTemplateInfo
</td>
<td>
currentCell, Row
</td>
<td>
It returns the current cell and row of excel sheet.
</td>
</tr>
<tr>
<td>
ServerWordDetailTemplateInfo
</td>
<td>
currentCell, Row
</td>
<td>
It returns the current cell and row of word.
</td>
</tr>
<tr>
<td>
ServerPdfDetailTemplateInfo
</td>
<td>
currentCell, Row
</td>
<td>
It returns the current cell and row of PDF.
</td>
</tr>
</table>

You can modify the detailTemplate of exporting files using server events. The code snippet for this is

{% tabs %}

{% highlight html %}

<script id="tabGridContents" type="text/x-jsrender">
    <b> More Details: </b> <br /><br /> <b class='detail'>Last Name</b> - {{:LastName}} <br /> <br /> <b class='detail'>Home Phone</b> - {{:HomePhone}} <br /> <br /> <b class='detail'>Extension No</b> - {{:Extension}}
  
</script>

<ej:Grid ID="EmployeesGrid" runat="server" DetailsTemplate="#tabGridContents" OnServerExcelDetailTemplateInfo="EmployeesGrid_ServerExcelDetailTemplateInfo" OnServerWordDetailTemplateInfo="EmployeesGrid_ServerWordDetailTemplateInfo" OnServerPdfDetailTemplateInfo="EmployeesGrid_ServerPdfDetailTemplateInfo" OnServerExcelExporting="EmployeesGrid_ServerExcelExporting" OnServerWordExporting="EmployeesGrid_ServerWordExporting" OnServerPdfExporting="EmployeesGrid_ServerPdfExporting">
      <Columns>
         <ej:Column Field="EmployeeID" HeaderText="Employee ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />
         <ej:Column Field="FirstName" HeaderText="First Name" Width="100" />
         <ej:Column Field="Title" HeaderText="Title" Width="120" />
         <ej:Column Field="City" HeaderText="City" Width="100" />
         <ej:Column Field="Country" HeaderText="Country" Width="100" />
      </Columns>
</ej:Grid>

{% endhighlight %}

{% highlight c# %}

public partial class DetailTemplateExporting : System.Web.UI.Page
{
    List<Orders> order = new List<Orders>();

    protected void Page_Load(object sender, EventArgs e)
    {
       BindDataSource();
    }

    private void BindDataSource()
    {
       order.Add(new Orders(1, "Nancy", "Davolio", new DateTime(1948, 12, 08), "USA"));
       order.Add(new Orders(2, "Andrew", "Fuller", new DateTime(1952, 02, 19), "USA"));
       order.Add(new Orders(3, "Janet", "Leverling", new DateTime(1963, 08, 30), "USA"));
       order.Add(new Orders(4, "Margaret", "Peacock", new DateTime(1937, 09, 19), "USA"));
       order.Add(new Orders(5, "Steven", "Buchanan", new DateTime(1955, 03, 04), "UK"));
       order.Add(new Orders(6, "Michael", "Suyama", new DateTime(1963, 07, 02), "UK"));
       order.Add(new Orders(7, "Robert", "King", new DateTime(1960, 05, 29), "UK"));
       order.Add(new Orders(8, "Laura", "Callahan", new DateTime(1958, 01, 09), "USA"));

       this.EmployeesGrid.DataSource = order;
       this.EmployeesGrid.DataBind();
    }

    [Serializable]
    public class Orders
    {
       public Orders()
       {

       }
       public Orders(int EmployeeId, string FirstName, string LastName, DateTime BirthDate, string Country)
       {
          this.EmployeeID = EmployeeId;
          this.FirstName = FirstName;
          this.LastName = LastName;
          this.BirthDate = BirthDate;
          this.Country = Country;
        }
        
        public int EmployeeID { get; set; }
        public string FirstName { get; set; }
        public string LastName { get; set; }
        public DateTime BirthDate { get; set; }
        public string Country { get; set; }
    }

    protected void EmployeesGrid_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)
    {
        ExcelExport exp = new ExcelExport();
        GridProperties obj = ConvertGridObject(e.Arguments["model"].ToString());
        GridExcelExport exp1 = new GridExcelExport() {  IncludeDetailRow = true, Theme = "flat-lime", FileName = "Export.xlsx" };
        exp.Export(obj, (IEnumerable)EmployeesGrid.DataSource, exp1);
    }

    protected void EmployeesGrid_ServerWordExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)
    {
        WordExport exp = new WordExport();
        GridProperties obj = ConvertGridObject(e.Arguments["model"].ToString());
        GridWordExport exp1 = new GridWordExport() { IncludeDetailRow = true, Theme = "flat-lime", FileName = "Export.docx" };
        exp.Export(obj, (IEnumerable)EmployeesGrid.DataSource, exp1);
    }

    protected void EmployeesGrid_ServerPdfExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)
    {
        PdfExport exp = new PdfExport();
        GridProperties obj = ConvertGridObject(e.Arguments["model"].ToString());
        GridPdfExport exp1 = new GridPdfExport() { IncludeDetailRow = true, Theme = "flat-lime", FileName = "Export.pdf" };
        exp.Export(obj, (IEnumerable)EmployeesGrid.DataSource, exp1);
    }

    private GridProperties ConvertGridObject(string gridProperty)
    {
       JavaScriptSerializer serializer = new JavaScriptSerializer();
       IEnumerable div = (IEnumerable)serializer.Deserialize(gridProperty, typeof(IEnumerable));
       GridProperties gridProp = this.EmployeesGrid.Model;
       foreach (KeyValuePair<string, object> data in div)
       {
          var property = gridProp.GetType().GetProperty(data.Key, BindingFlags.Instance | BindingFlags.Public | BindingFlags.IgnoreCase);

          if (property != null)
          {
             Type type = property.PropertyType;
             string serialize = serializer.Serialize(data.Value);
             object value = serializer.Deserialize(serialize, type);
             property.SetValue(gridProp, value, null);
          }
        }
        return gridProp;
     }

     protected void EmployeesGrid_ServerExcelDetailTemplateInfo(object arg1, object arg2)
     {
        IRange range = (IRange)arg1;
        object templates;
        foreach (var data in arg2.GetType().GetProperties())
        {
          if (range.Value.Contains(data.Name))
          {
            templates = arg2.GetType().GetProperty(data.Name).GetValue(arg2, null);
            range.Value = range.Value.Replace(data.Name, templates.ToString());
            var charsToRemove = new string[] { '{', '}', '<b>', ':', '</b>', '<br />', 'style', '=', 'class', '</div>', '<p>', '</p>', 'detail', '<b', '>', };
            foreach (var c in charsToRemove)
            {
              range.Value = range.Value.ToString().Replace(c, string.Empty);
            }
            range.HorizontalAlignment = ExcelHAlign.HAlignCenter;
          }
        }
     }

     protected void EmployeesGrid_ServerWordDetailTemplateInfo(object arg1, object arg2)
     {
        WTableCell wCell = (WTableCell)arg1;
        object templates;
        foreach (var data in arg2.GetType().GetProperties())
        {
          if (wCell.LastParagraph.Text.ToString().Contains(data.Name))
          {
             templates = arg2.GetType().GetProperty(data.Name).GetValue(arg2, null);
             wCell.LastParagraph.Text = wCell.LastParagraph.Text.ToString().Replace(data.Name, templates.ToString());
             var charsToRemove = new string[] { '{', '}', '<b>', ':', '</b>', '<br />', 'style', '=', 'class', '</div>', '<p>', '</p>', 'detail', '<b', '>', };
             foreach (var c in charsToRemove)
             {
               wCell.LastParagraph.Text  = wCell.LastParagraph.Text.ToString().Replace(c, string.Empty); //
             }
          }
        }
     }

    protected void EmployeesGrid_ServerPdfDetailTemplateInfo(object arg1, object arg2)
    {
      Syncfusion.Pdf.Grid.PdfGridCell range = (Syncfusion.Pdf.Grid.PdfGridCell)arg1;
      object templates;
      foreach (var data in arg2.GetType().GetProperties())
      {
        if (range.Value.ToString().Contains(data.Name))
        {
          templates = arg2.GetType().GetProperty(data.Name).GetValue(arg2, null);
          range.Value = range.Value.ToString().Replace(data.Name, templates.ToString());
          var charsToRemove = new string[] { '{', '}', '<b>', ':', '</b>', '<br />', 'style', '=', 'class', '</div>', '<p>', '</p>', 'detail', '<b', '>', };
          foreach (var c in charsToRemove)
          {
            range.Value = range.Value.ToString().Replace(c, string.Empty);
          }
        }
      }
    }
}

{% endhighlight %}

{% endtabs %}

## Exporting with Custom Summary

In Exporting, custom summary needs to be handled using `QueryCustomSummaryInfo` server-side event.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

<ej:Grid ID="FlatGrid" runat="server" AllowPaging="true" ShowSummary="true"  OnServerWordExporting="FlatGrid_ServerWordExporting" OnServerPdfExporting="FlatGrid_ServerPdfExporting" OnServerExcelExporting="FlatGrid_ServerExcelExporting">
    <ToolbarSettings ShowToolbar="true" ToolbarItems="excelExport,wordExport,pdfExport"></ToolbarSettings>
    <SummaryRows>
        <ej:SummaryRow Title="Currency" >
            <SummaryColumn>
                    <ej:SummaryColumn SummaryType="Custom" CustomSummaryValue="currency" DisplayColumn="Freight"
                        Format="{0:C2}" />
            </SummaryColumn>
        </ej:SummaryRow>
    </SummaryRows>
    <Columns>
        <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="80" />
        <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="80" />
        <ej:Column Field="ShipCity" HeaderText="Ship City" Width="90" />
        <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="80" Format="{0:C}" />
    </Columns>
</ej:Grid>


{% endhighlight %}

{% highlight js %}
<script type="text/javascript">
    function currency() {
            var rs = 100000;
            var value = 0.017;
            return (rs * value);
    }
</script>
{% endhighlight  %}

{% highlight c# %}

public partial class CustomSummaryExporting : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }

        private void BindDataSource()

        {

            int code = 10000;

            for (int i = 1; i < 10; i++)

            {

                order.Add(new Orders(code + 1, "ALFKI", i + 0, 2.3 * i, new DateTime(1991, 05, 15), "Berlin"));

                order.Add(new Orders(code + 2, "ANATR", i + 2, 3.3 * i, new DateTime(1990, 04, 04), "Madrid"));

                order.Add(new Orders(code + 3, "ANTON", i + 1, 4.3 * i, new DateTime(1957, 11, 30), "Cholchester"));

                order.Add(new Orders(code + 4, "BLONP", i + 3, 5.3 * i, new DateTime(1930, 10, 22), "Marseille"));

                order.Add(new Orders(code + 5, "BOLID", i + 4, 6.3 * i, new DateTime(1953, 02, 18), "Tsawassen"));

                code += 5;

            }

            this.FlatGrid.DataSource = order;

            this.FlatGrid.DataBind();

        }



        [Serializable]

        public class Orders

        {

            public Orders()

            {



            }

            public Orders(long OrderId, string CustomerId, int EmployeeId, double Freight, DateTime OrderDate, string ShipCity)

            {

                this.OrderID = OrderId;

                this.CustomerID = CustomerId;

                this.EmployeeID = EmployeeId;

                this.Freight = Freight;

                this.OrderDate = OrderDate;

                this.ShipCity = ShipCity;

            }

            public long OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public double Freight { get; set; }

            public DateTime OrderDate { get; set; }

            public string ShipCity { get; set; }

        }



        protected void FlatGrid_ServerExcelExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)

        {

            ExcelExport exp = new ExcelExport();
            GridExcelExport GridExp = new GridExcelExport();
            GridExp.QueryCustomSummaryInfo = SummaryCellInfo;
            GridExp.Theme = "flat-lime";
            GridExp.FileName = "Export.xlsx";
            exp.Export(FlatGrid.Model, (IEnumerable)FlatGrid.DataSource, GridExp);

        }



        protected void FlatGrid_ServerWordExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)

        {

            WordExport exp = new WordExport();
            GridWordExport GridExp = new GridWordExport();
            GridExp.QueryCustomSummaryInfo = SummaryCellInfo;
            GridExp.Theme = "flat-lime";
            GridExp.FileName = "Export.docx";
            exp.Export(FlatGrid.Model, (IEnumerable)FlatGrid.DataSource, GridExp);

        }



        protected void FlatGrid_ServerPdfExporting(object sender, Syncfusion.JavaScript.Web.GridEventArgs e)

        {

            PdfExport exp = new PdfExport();
            GridPdfExport GridExp = new GridPdfExport();
            GridExp.QueryCustomSummaryInfo = SummaryCellInfo;
            GridExp.Theme = "flat-lime";
            GridExp.FileName = "Export.pdf";
            exp.Export(FlatGrid.Model, (IEnumerable)FlatGrid.DataSource, GridExp);

        }

        private object SummaryCellInfo(IQueryable arg1, SummaryColumn arg2)
        {
            var rs = 0; double value = 0;
            if (arg2.DisplayColumn == "Freight")
            {
                rs = 100000;
                value = 0.017;
            }
            return (rs * value);
        }

    }

{% endhighlight %}

{% endtabs %}
