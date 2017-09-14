---
layout: post
title: Print with Spreadsheet widget for Syncfusion Essential JS
description: How to use the Spreadsheet Print
platform: aspnet
control: Spreadsheet
documentation: ug
---

# Print

This feature is used for produce text and graphics from a computer screen or file onto a sheet of paper. You can use `AllowPrinting` property in `PrintSettings` to enable/disable the print operation.

You have following options in printing.

* Print Sheet / Print Selected Area.
* Print with Gridlines
* Print with Headers

## Print Sheet / Print Selected Area

You can print the sheet or print the selected area by following ways,

* Using the Print button or Print Selected button under Print group of PAGE LAYOUT tab in ribbon.
* Using [`printSheet`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlprint-printsheet "printSheet") or [`printSelection`](https://help.syncfusion.com/api/js/ejspreadsheet#methods:xlprint-printselection "printSelection") method to print the spreadsheet.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" runat="server">
   <PrintSettings AllowPrinting="true" />
</ej:Spreadsheet>
<ej:Button ID="btnPrint" Width="80" ShowRoundedCorner="true" Type="Button" ClientSideOnClick="printClick" runat="server"></ej:Button>
<ej:Button ID="btnPrintSel" Width="80" ShowRoundedCorner="true" Type="Button" ClientSideOnClick ="printSelClick" runat ="server"></ej:Button>

<script type="text/javascript">
 function printClick(e) {
            var excelObj = $('#<%= FlatSpreadsheet.ClientID %>').data("ejSpreadsheet");
            excelObj.XLPrint.printSheet();
        }
function printSelClick(e) {
            var excelObj = $('#<%= FlatSpreadsheet.ClientID %>').data("ejSpreadsheet");
            excelObj.XLPrint.printSelection();
        }
</script>
{% endhighlight %}



{% highlight c# %}

 protected void Page_Load(object sender, EventArgs e)
        {
            if (!IsPostBack)
            {
                BindDataSource();
            }
        }
 
  private void BindDataSource()
        {
             var dataSource = new OrderItemsDataContext().GetAllItemDetails.ToList();
            this.FlatSpreadsheet.Sheets.Add(new Syncfusion.JavaScript.Models.Sheet()
            {
                Datasource = dataSource

            });
        }
{% endhighlight %}

{% endtabs %}

The following output is displayed as a result of the above code example.

![](Print_images/Print_img1.png)

![](Print_images/Print_img2.png)

Print dialog with entire sheet in Chrome browser
{:.caption}

![](Print_images/Print_img3.png)

Print dialog with selected area print in chrome browser
{:.caption}

## Print with Gridlines

You have an option to print the spreadsheet with gridlines or without gridlines. You can do this by one of the following ways,

* Check the Gridlines option under Show group of PAGE LAYOUT tab in ribbon to print with Gridlines.
* Using `ShowGridlines` property to enable / disable the gridlines.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" runat="server">
        <Sheets>
         <ej:Sheet ShowGridlines="false"></ej:Sheet>
     </Sheets>
</ej:Spreadsheet>

{% endhighlight %}



{% highlight c# %}

 protected void Page_Load(object sender, EventArgs e)
        {
            if (!IsPostBack)
            {
                BindDataSource();
            }
        }

        private void BindDataSource()
        {
            var dataSource = new OrderItemsDataContext().GetAllItemDetails.ToList();
            this.FlatSpreadsheet.Sheets.Add(new Syncfusion.JavaScript.Models.Sheet()
            {
                Datasource = dataSource
            });
        }

{% endhighlight %}

{% endtabs %}

![](Print_images/Print_img4.png)

Print dialog without gridlines in chrome browser
{:.caption}

## Print with Headings

You have an option to print the spreadsheet with headers or without headers. You can do this by one of the following ways,

* Check the Headings option under Show group of PAGE LAYOUT tab in ribbon. 
* Using `ShowHeadings` property to enable / disable headings.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" runat="server">
        <Sheets>
         <ej:Sheet ShowHeadings="false"></ej:Sheet>
     </Sheets>
</ej:Spreadsheet>

{% endhighlight %}



{% highlight c# %}

 protected void Page_Load(object sender, EventArgs e)
        {
            if (!IsPostBack)
            {
                BindDataSource();
            }
        }

        private void BindDataSource()
        {
            var dataSource = new OrderItemsDataContext().GetAllItemDetails.ToList();
            this.FlatSpreadsheet.Sheets.Add(new Syncfusion.JavaScript.Models.Sheet()
            {
                Datasource = dataSource
            });
        }

{% endhighlight %}

{% endtabs %}

![](Print_images/Print_img5.png)

Print dialog without headings in chrome browser
{:.caption}
