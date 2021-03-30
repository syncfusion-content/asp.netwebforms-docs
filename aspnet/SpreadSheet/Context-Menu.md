---
layout: post
title: Context Menu with Spreadsheet widget for Syncfusion Essential JS
description: Learn about context menu support in Syncfusion ASP.NET Webforms Spreadsheet control and more details.
platform:  aspnet
control: Spreadsheet
documentation: ug
---

# Context Menu

Context Menu is used to improve user interaction with Spreadsheet using popup menu. This will open when right clicking on Cell/Column Header/Row Header/ Pager in Spreadsheet. You can use `EnableContextMenu` property to enable/disable context menu. 

## Default Context Menu items

Please find the below table for default context menu items and its actions.

<table>
    <colgroup><col width= "150px"/><col width = "180px"/></colgroup>
    <tr><th>Section<br/></th><th>Context Menu items<br/></th><th>Action<br/></th></tr>
    <tr><td rowspan = "11">Row Cell<br/></td><td>Cut<br/></td><td>Cut the selected cells content to the clipboard, so that you can paste it somewhere else.<br/></td></tr>
    <tr><td>Copy <br/></td><td>Copy the selected cells content to the clipboard, so that you can paste it to somewhere else.<br/></td></tr>
    <tr><td>Paste<br/></td><td>Paste the content from clipboard to spreadsheet.<br/></td></tr>
    <tr><td>Insert<br/></td><td>Insert new cells or rows or columns to worksheet.<br/></td></tr>
    <tr><td>Delete<br/></td><td>Delete existing cells or rows or columns from worksheet.<br/></td></tr>
    <tr><td>Sort<br/></td><td>Perform sorting to the selected range of cells by ascending or descending.<br/></td></tr>
    <tr><td>Filter<br/></td><td>Perform filtering to the selected cells based an active cell's value or active cell's color.<br/></td></tr>
    <tr><td>Hyperlink<br/></td><td>Create a link in the spreadsheet for quick access to webpages or worksheet reference.<br/></td></tr>
    <tr><td>Comment<br/></td><td>Add a note or extra information about the active cell.<br/></td></tr>
    <tr><td>Format Cells<br/></td><td>Apply number format to the selected cells.<br/></td></tr>
    <tr><td>Clear Contents<br/></td><td>Delete the contents in the selected cells.<br/></td></tr>
    <tr><td rowspan = "8">Row Header / Column Header<br/></td><td>Cut<br/></td><td>Cut the selected cells content to the clipboard, so that you can paste it to somewhere else.<br/></td></tr>
    <tr><td>Copy <br/></td><td>Copy the selected cells content to the clipboard, so that you can paste it to somewhere else.<br/></td></tr>
    <tr><td>Paste<br/></td><td>Paste the content from clipboard to spreadsheet.<br/></td></tr>
    <tr><td>Clear Contents<br/></td><td>Delete the contents in the selected cells.<br/></td></tr>
    <tr><td>Insert<br/></td><td>Insert new cells or rows or columns to worksheet.<br/></td></tr>
    <tr><td>Delete<br/></td><td>Delete existing cells or rows or columns from worksheet.<br/></td></tr>
    <tr><td>Hide<br/></td><td>Hide the selected columns / rows.<br/></td></tr>
    <tr><td>Unhide<br/></td><td>Unhide the selected columns / rows.<br/></td></tr>
    <tr><td rowspan = "7">Pager<br/></td><td>Insert<br/></td><td>Insert new worksheet to spreadsheet.<br/></td></tr>
    <tr><td>Delete<br/></td><td>Delete the selected worksheet from spreadsheet.<br/></td></tr>
    <tr><td>Move or copy<br/></td><td>Opens move or copy dialog to move worksheet or to create duplicate worksheet.<br/></td></tr>
    <tr><td>Rename<br/></td><td>Rename the selected worksheet.<br/></td></tr>
    <tr><td>Protect Sheet<br/></td><td>Prevent unwanted changes from others by limiting their ability to edit.<br/></td></tr>
    <tr><td>Hide <br/></td><td>Hide the selected worksheet.<br/></td></tr>
    <tr><td>Unhide<br/></td><td>Opens unhide dialog to unhide worksheet.<br/></td></tr>
</table>

The following code example describes the above behavior.

{% highlight html %}
<ej:Spreadsheet ID="FlatSpreadsheet" EnableContextMenu="true" runat="server">
</ej:Spreadsheet> 
{% endhighlight %}

![ASPNET Spreadsheet Context-Menu Image1](Context-Menu_images/context-menu_img1.png)

ContextMenu at Cell
{:.caption}


![ASPNET Spreadsheet Context-Menu Image2](Context-Menu_images/context-menu_img2.png)

ContextMenu at Column Header
{:.caption}

![ASPNET Spreadsheet Context-Menu Image3](Context-Menu_images/context-menu_img3.png)

ContextMenu at Row Header
{:.caption}

![ASPNET Spreadsheet Context-Menu Image4](Context-Menu_images/context-menu_img4.png)

ContextMenu at Pager
{:.caption}
