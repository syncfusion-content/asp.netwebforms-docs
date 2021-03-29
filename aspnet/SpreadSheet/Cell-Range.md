---
title: Cell Range with Spreadsheet widget for Syncfusion Essential JS
description: Learn about cell range support in Syncfusion ASP.NET Webforms Spreadsheet control and more details.
platform: aspnet
control: Spreadsheet
documentation: ug
--- 

# Cell Range

A Cell Range is a collection of cells in a sheet. It represents single cell or selection of cells. When cells have been selected, they are surrounded by border. 

You have following features in Cell Range,

* Comment
* Cell Navigation
* Data Validation
* Drag and Drop
* Auto Fill
* Hyperlink
* Merge Cell

## Comment

Comment is used to give additional information for an individual cell about the data it contains. When a cell has a comment, a red indicator appears in the corner of the cell. When mouse hover on the cell, the comment will appear. You can use `AllowComments` property to enable/disable comments. 

### To insert a Comment

You can insert a comment by using one of the following ways,

* Using "New" button under Comments group of REVIEW Tab in ribbon.
* Using context menu to select "Insert Comment" option in "Comment".
* Using [`setComment`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:xlcomment-setcomment "setComment") method.

### To remove a Comment

You can remove a comment by using one of the following ways,

* Using "Delete" button under Comments group of REVIEW Tab in ribbon.
* Using context menu to select "Delete Comment" option in "Comment".
* Using [`deleteComment`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:xlcomment-deletecomment "deleteComment") method.

The following code example describes the above behavior.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" AllowComments = "true" runat="server">
       <ClientSideEvents LoadComplete="loadComplete" />
</ej:Spreadsheet>

 <script type="text/javascript">
function loadComplete(args) {
    if(!this.isImport) {
        this.XLComment.setComment("A2", " Casual Foot wears with wide variety of colors.", false);
        this.XLComment.setComment("A4", " Formal Foot wears with wide variety of sizes.", true); // If true comment is in Editing mode.
        //To Remove a Comment
        this.XLComment.deleteComment ("A2");
    }
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
![ASPNET Spreadsheet Cell-Ranges Image1](Cell-Ranges_images/Cell-Ranges_img1.png)

## Cell Navigation

Cell navigation is used to navigate through the cells using keyboard. You can use `AllowKeyBoardNavigation` property to enable/disable cell navigation. The following list of keys used for cell navigation are,

<table>
<colgroup><col width="180px" /></colgroup>
<tr><th>Keys<br/></th><th>Description<br/></th></tr>
<tr><td>Ctrl + Home<br/></td><td>Go to first cell in the first row.<br/></td></tr>
<tr><td>Ctrl + End<br/></td><td>Go to last cell in the last row.<br/></td></tr>
<tr><td>Up Arrow<br/></td><td>Go to previous cell in the same column<br/></td></tr>
<tr><td>Down Arrow<br/></td><td>Go to next cell in the same column<br/></td></tr>
<tr><td>Right Arrow<br/></td><td>Go to next cell in the same row<br/></td></tr>
<tr><td>Left Arrow<br/></td><td>Go to previous cell in the same row<br/></td></tr>
<tr><td>Page Down<br/></td><td>Go to next block<br/></td></tr>
<tr><td>Page Up<br/></td><td>Go to previous block<br/></td></tr>
<tr><td>Home<br/></td><td>Go to first cell of the same row<br/></td></tr>
<tr><td>End<br/></td><td>Go to last cell of the same row<br/></td></tr>
<tr><td>Enter<br/></td><td>Save the current cell changes and navigate to the next row.<br/></td></tr>
<tr><td>Tab<br/></td><td>Go to next cell<br/></td></tr>
<tr><td>Shift + Tab<br/></td><td>Go to previous cell<br/></td></tr>
<tr><td>Shift + Up Arrow<br/></td><td>Go to previous row or previous row cell with selection<br/></td></tr>
<tr><td>Shift+ Down Arrow<br/></td><td>Go to next row or next row cell with selection<br/></td></tr>
<tr><td>Shift + Right Arrow<br/></td><td>Go to next cell within the same row with selection<br/></td></tr>
<tr><td>Shift + Left Arrow<br/></td><td>Go to previous cell within the same row with selection<br/></td></tr>
<tr><td>Ctrl + Up Arrow<br/></td><td>Go to next cell from the first empty cell in upwards.<br/></td></tr>
<tr><td>Ctrl + Down Arrow<br/></td><td>Go to previous cell from the first empty cell in downwards.<br/></td></tr>
<tr><td>Ctrl + Left Arrow<br/></td><td>Go to next cell from the first empty cell in leftwards.<br/></td></tr>
<tr><td>Ctrl+ Right Arrow<br/></td><td>Go to previous cell from the first empty cell in rightwards.<br/></td></tr>
</table>

N> In the above table, "Ctrl + Home" and "Ctrl + End" is based on the used range.

## Data Validation

Data Validation is used to restrict the user to enter the invalid data. You can use `AllowDataValidation` property to enable/disable data validation. 

N> The below validation script files are needed for validation.
N> * jquery.validate.min.js
N> * jquery.validate.unobtrusive.min.js

#### To apply validation.

You can apply data validation by using one of the following ways,

* Using "Data Validation" option in Data Validation button under Data Tools group of DATA Tab in ribbon, Data Validation dialog will be opened in that you can perform Validation.
* Using [`applyDVRules`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:xlvalidate-applydvrules "applyDVRules") method.

The following code example describes the above behavior.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" runat="server">
       <ClientSideEvents LoadComplete="loadComplete" />
</ej:Spreadsheet>

 <script type="text/javascript">
function loadComplete(args) {
    if(!this.isImport) {
        this.XLValidate.applyDVRules("G2:G12", ["Greater", 6], "number", true, true);
        //the last two boolean values used to ignore blank value and error alert.
    }
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

#### To clear validation

You can clear data validation rule by one of the following ways,

* Using "Clear Validation" option in Data Validation button under Data Tools group of DATA Tab in ribbon.
* Using [`clearDV`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:xlvalidate-cleardv "clearDV") method.

The following code example describes the above behavior.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" runat="server">
       <ClientSideEvents LoadComplete="loadComplete" />
</ej:Spreadsheet>

 <script type="text/javascript">
function loadComplete(args) {
    if(!this.isImport) {
        this.XLValidate.applyDVRules("G2:G12", ["Greater", 6], "number", true, true);
        //the last two boolean values used to ignore blank value and error alert.
        this.XLValidate.clearDV("G2:G12");
    }
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

#### To format invalid data

You can highlight the invalid data by using following ways,

* Using "Format Invalid Data" option in Data Validation button under Data Tools group of DATA Tab in ribbon.
* Using [`highlightInvalidData`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:xlvalidate-highlightinvaliddata "highlightInvalidData") method.

The following code example describes the above behavior.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" runat="server">
       <ClientSideEvents LoadComplete="loadComplete" />
</ej:Spreadsheet>

 <script type="text/javascript">
function loadComplete(args) {
    if(!this.isImport) {
        this.XLValidate.applyDVRules("G2:G12", ["Greater", 6], "number", true, true);
        //the last two boolean values used to ignore blank value and error alert.
        this.XLValidate.highlightInvalidData ("G2:G12");
    }
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
![ASPNET Spreadsheet Cell-Ranges Image2](Cell-Ranges_images/Cell-Ranges_img2.png)

## Drag and Drop

Drag and drop is used to pick a selected cells and drop it into a new place on the worksheet. You can use `AllowDragAndDrop` property to enable/disable drag and drop. 

You can do this by one of the following ways,

* Using mouse drag and drop.
* Using [`moveRangeTo`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:xldragdrop-moverangeto "moveRangeTo") Method.

The following code example describes the above behavior.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" runat="server">
       <ClientSideEvents LoadComplete="loadComplete" />
</ej:Spreadsheet>

 <script type="text/javascript">
function loadComplete(args) {
    if(!this.isImport)
        this.XLDragDrop.moveRangeTo([1, 6, 4, 7], [1, 9, 4, 10]);
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
![ASPNET Spreadsheet Cell-Ranges Image3](Cell-Ranges_images/Cell-Ranges_img3.png)

## Auto Fill

Auto Fill is used to fill the cells with data based on adjacent cells. It also follows a pattern from adjacent cells if available. There is no need to enter the repeated data manually. You can use `AllowAutoFill` property to enable/disable the auto fill support. You can also use `ShowFillOptions` property to enable/disable the fill option and `FillType` property to change the default auto fill option which is available in `AutoFillSettings`. 

You can do this by one of the following ways,

* Using “AutoFillOptions” menu which is open, while drag and drop the cell using fill handle element.
* Using [`autoFill`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:xldragfill-autofill "autoFill") method.

In Auto Fill we have following options, 

* Copy Cells
* Fill Series
* Fill Formatting Only
* Fill Without Formatting
* Flash Fill

N> The default auto fill option is "FillSeries" which can be referred from `FillType` property.

#### Copy Cells

To copy the selected cell content to the adjacent cells. You can do this by one of the following ways,

* Using fill handle to select the adjacent cell range and "Copy Cells" option in "AutoFillOptions" menu to fill the adjacent cells.
* Using "CopyCells" as fill type in [`autoFill`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:xldragfill-autofill "autoFill") method to fill the adjacent cells.

#### Fill Series

To fill the series of numbers, characters, or dates based on selected cell content to the adjacent cells with their formats.

You can do this by one of the following ways,

* Using fill handle to select the adjacent cell range and "Fill Series" option in "AutoFillOptions" menu to fill the adjacent cells.
* Using "fillSeries" as fill type in [`autoFill`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:xldragfill-autofill "autoFill") method to fill the adjacent cells.

#### Fill Formatting Only

To fill the cell style and number formatting based on the selected cell content to the adjacent cells without their content.

You can do this by one of the following ways,

* Using fill handle to select the adjacent cell range and "Fill Formatting Only" option in "AutoFillOptions" menu to fill the adjacent cells.
* Using "FillFormattingOnly" as fill type in [`autoFill`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:xldragfill-autofill "autoFill") method to fill the adjacent cells.

#### Fill Without Formatting

To fill series of numbers, characters, or dates based on the selected cells to the adjacent cells without their formats.

You can do this by one of the following ways,

* Using fill handle to select the adjacent cell range and "Fill Without Formatting" option in "AutoFillOptions" menu to fill the adjacent cells.
* Using "FillWithoutFormatting" as fill type in [`autoFill`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:xldragfill-autofill "autoFill") method to fill the adjacent cells.

#### Flash Fill 

To fill the column when it senses a pattern from adjacent column data based on what you type.

You can do this by one of the following ways,

* Using fill handle to select the adjacent cell range and "Flash Fill" option in "AutoFillOptions" menu to fill the adjacent cells.
* Using "FlashFill" as fill type in [`autoFill`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:xldragfill-autofill "autoFill") method to fill the adjacent cells.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" runat="server">
       <ClientSideEvents LoadComplete="loadComplete" />
	   <Sheets>
        <ej:Sheet>
            <RangeSettings>
                <ej:RangeSetting StartCell="A1" ShowHeader="true"/>
                <ej:RangeSetting StartCell="I2"/>
            </RangeSettings>
        </ej:Sheet>
    </Sheets>
</ej:Spreadsheet>

<script type="text/javascript">
 function loadComplete(args) {
    if(!this.isImport) {
        this.XLEdit.updateValue("N2", "Name");
        this.XLEdit.updateValue("N3", "Casual Shoes");
        this.XLEdit.updateValue("N4", "Formal Shoes");
        this.XLEdit.updateValue("N5", "Sports Shoes");
        this.XLEdit.updateValue("O2", "FirstName");
        this.XLEdit.updateValue("O3", "Casual");
        this.XLFormat.format({ "style": { "background-color": "yellow" } }, "K2:L2");
        this.XLFormat.format({ "style": { "background-color": "red" } }, "K4:L4");
        this.XLFormat.format({ "style": { "background-color": "blue" } }, "K5:L5");
        this.XLDragFill.autoFill({sheetIdx: 1, dataRange:[1, 8, 4, 8], fillRange: "I6:I10", fillType: "copycells", direction:"down"}); //copy Cells
        this.XLDragFill.autoFill({sheetIdx: 1, dataRange:[1, 9, 4, 9], fillRange: "J6:J10", fillType: "fillseries", direction:"down"}); //fill series
        this.XLDragFill.autoFill({sheetIdx: 1, dataRange:[1, 10, 4, 10], fillRange: "K6:K10", fillType: "fillformattingonly", direction:"down"}); //fill formatting only
        this.XLDragFill.autoFill({sheetIdx: 1, dataRange:[1, 11, 4, 11], fillRange: "L6:L10", fillType: "fillwithoutformatting", direction:"down"}); //fill without formatting
        this.XLDragFill.autoFill({sheetIdx: 1, dataRange:[2, 14, 2, 14], fillRange: "O4:O6", fillType: "flashfill", direction:"down"}); //flash fill
    }      
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
             this.FlatSpreadsheet.Sheets[0].RangeSetting[0].Datasource = dataSource;
			 List<sampleData> sampleData = new List<sampleData>();
                sampleData.Add(new sampleData() { i = 1, j = 1, k = 1, l = 1 });
                sampleData.Add(new sampleData() { i = 2, j = 2, k = 2, l = 2 });
                sampleData.Add(new sampleData() { i = 3, j = 3, k = 3, l = 3 });
                sampleData.Add(new sampleData() { i = 4, j = 4, k = 4, l = 4 });
		    this.FlatSpreadsheet.Sheets[0].RangeSetting[1].Datasource = sampleData;
        }

		[Serializable]
        public class sampleData
        {
            public sampleData()
            {

            }
            public sampleData(int i, int j, int k, int l)
            {
                this.i = i;
                this.j = j;
                this.k = k;
                this.l = l;
            }
            public int i{ get; set; }
            public int j{ get; set;}
            public int k{ get; set; }
            public int l{ get; set;}
        }


{% endhighlight %}

{% endtabs %}

The following output is displayed as a result of the above code example.
![ASPNET Spreadsheet Cell-Ranges Image5](Cell-Ranges_images/Cell-Ranges_img5.png)

## Hyperlink

Hyperlink is used to navigate to web links or cell reference within the sheet or to other sheets in Spreadsheet. You can use `AllowHyperLink` property to enable/disable Hyperlink.

### To insert a Hyperlink

You can insert a hyperlink by one of the following ways,

* Using "Hyperlink" button under Links group of INSERT Tab in ribbon.
* Using context menu to select "Insert Hyperlink" option in "Hyperlink".
* Using [`setHyperlink`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:sethyperlink "setHyperlink") method.

### To remove a Hyperlink

You can remove a hyperlink by one of the following ways,

* Using context menu to select "Remove Hyperlink" option in Hyperlink.
* Using [`removeHyperlink`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:removehyperlink "removeHyperlink") method.

The following code example describes the above behavior.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" runat="server">
       <ClientSideEvents LoadComplete="loadComplete" />
</ej:Spreadsheet>

<script type="text/javascript">
 function loadComplete(args) {
    if(!this.isImport) {
        this.XLEdit.updateValue("I2", "amazon");
        this.XLEdit.updateValue("J2", "flipkart");
        this.setHyperlink("E3:E3", { "cellAddr": "A1:D2" }, 2);
        this.setHyperlink("I2:I2", { "webAddr": "http://www.amazon.com" }, 1);
        this.setHyperlink("J2:J2", { "webAddr": "http://www.flipkart.com" }, 1);
        //To Remove a Hyperlink
        this.removeHyperlink("J2:J2");
    }
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
![ASPNET Spreadsheet Cell-Ranges Image6](Cell-Ranges_images/Cell-Ranges_img6.png)

## Merge Cell

Merge cell is a single cell created by combining two or more individual cells together. You can use `AllowMerging` property to enable/disable merge cells. The cell reference for a merged cell is the cell in the upper left corner of the original selected range or group of cells. 

You have following options in Merge Cell,

* Merge Cells
* Merge & Center
* Merge Across
 
### Merge Cells

You can combine two or more cells located in the same row or column into a single cell. When cells with multiple values are merged, upper-left most cell's data will be the data of merged cell. 

You can do this by one of the following ways,

* Using "Merge Cells" option in Merge & Center button under Alignment group of HOME Tab in ribbon.
* Using [`mergeCells`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:mergecells "mergeCells") method.

### Merge & Center

You can combine two or more cells located in the same row or column into a single cell with center text align. When cells with multiple values are merged, upper-left most cell's data will be the data of the merged cell. You can do this by one of the following ways,

* Using Merge & Center button under Alignment group of HOME Tab in ribbon.
* Using "Merge & Center" option in Merge & Center button under Alignment group of HOME Tab in ribbon.
* Using [`mergeCells`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:mergecells "mergeCells") method with `MergeCenter` property as `true` to enable the center alignment.

### Merge Across

You can combine two or more cells located in the same row into a single cell. When cells with multiple values are merged, left most cell's data will be the data of the merged cell.

You can do this by one of the following ways,

* Using "Merge Across" option in Merge & Center button under Alignment group of HOME Tab in ribbon.
* Using [`mergeAcrossCells`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:mergeacrosscells "mergeAcrossCells") method.

The following code example describes the behavior of merge Cells, merge & center and merge Across.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" runat="server">
       <ClientSideEvents LoadComplete="loadComplete" />
</ej:Spreadsheet>

 <script type="text/javascript">
function loadComplete(args) {
    if(!this.isImport) {
        this.mergeCells("A2:B4", true);
        this.mergeCenter = true;
        this.mergeCells("D2:E4", true); // true is to prevent the alert message.
        this.mergeAcrossCells("G2:H4", true); // true is to prevent the alert message.
    }
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
![ASPNET Spreadsheet Cell-Ranges Image7](Cell-Ranges_images/Cell-Ranges_img7.png)

### Unmerge Cells

You can split the merged cell into multiple cells. You can do this by one of the following ways,

* Using "Unmerge cells" option in Merge & Center button under Alignment group of HOME Tab in ribbon.
* Using [`unMergeCells`](http://help.syncfusion.com/api/js/ejspreadsheet#methods:unmergecells "unMergeCells") method.

The following code example describes the above behavior.
{% tabs %}

{% highlight html %}

<ej:Spreadsheet ID="FlatSpreadsheet" runat="server">
       <ClientSideEvents LoadComplete="loadComplete" />
</ej:Spreadsheet>

 <script type="text/javascript">
function loadComplete(args) {
    if(!this.isImport) {
        this.mergeCells("B2:C4", true); // true is to prevent the alert message.
        this.unmergeCells("B2:C4");
    }
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
![ASPNET Spreadsheet Cell-Ranges Image8](Cell-Ranges_images/Cell-Ranges_img8.png)