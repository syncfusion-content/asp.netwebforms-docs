---
layout: post
title: Working-with-Lists | RichTextEditor | ASP.NET Webforms | Syncfusion
description: working-with-lists
platform: aspnet
control: RichTextEditor
documentation: ug
keywords: RichTextEditor, Create a Lists, Custom Lists, customOrderedList, customUnorderedList

---
# Working with Lists

The editor provides tools to makes your content as list such as an ordered and unordered list.

## Create a Lists

By default, [Insert Lists](http://help.syncfusion.com/js/api/ejrte#members:tools-lists) tool is enabled in the editor’s toolbar.The editor’s have ordered and unordered list types.

{% highlight html %}

<ej:RTE ID="rteSample" AllowEditing="true" ToolsList="lists" runat="server">
    <Tools Lists="unorderedList,orderedList">
    </Tools>
</ej:RTE>
    
{% endhighlight %}

## Custom Lists

You can use [custom lists](http://help.syncfusion.com/js/api/ejrte#members:tools-customOrderedList) tools to insert lists with custom behaviors.You can create a list with related attributes (such as listImage, listStyle, title, name, and text) using the custom list tool.Ordered and Unordered list having own customize ways to insert a list into the editor’s content.

* [Insert a customOrderedList](#insert-a-customOrderedList)
* [Insert a customUnorderedList](#insert-a-customUnorderedList)  


### Insert a customOrderedList

you need to enable [customOrderedList](http://help.syncfusion.com/js/api/ejrte#members:tools-customOrderedList) tool on the editor’s toolbar.

The customOrderedList having below options for an ordered list customization.

<table>
<tr>
<th>
Option<br/><br/></th><th>
Summary<br/><br/></th></tr>
<tr><td>Name</td><td>Specifies the name for customOrderedList item.</td></tr>
<tr><td>Tooltip</td><td>Specifies the title for customOrderedList item.</td></tr>
<tr><td>CSS</td><td>Specifies the styles for customOrderedList item.</td></tr>
<tr><td>Text</td><td>Specifies the text for customOrderedList item.</td></tr>
<tr><td>ListStyle</td><td>Specifies the list style for customOrderedList item.</td></tr>
<tr><td>ListImage</td><td>Specifies the image for customOrderedList item.</td></tr>
</table>

{% highlight html %}

<ej:RTE ID="rteSample" AllowEditing="true" ToolsList="lists" runat="server">
    <Tools Lists="unorderedList,orderedList">
            <CustomOrderedList>
                    <ej:CustomOrderedList Text="Lower-Greek" ListStyle="lower-greek" Name="orderInsert" Tooltip="Custom OrderList" Css="e-rte-toolbar-icon e-rte-listitems customOrder" />
            </CustomOrderedList> 
    </Tools>
</ej:RTE>
    
{% endhighlight %}


![](WorkingwithLists_images/ordered.png)

### Insert a customUnorderedList

you need to enable [customUnorderedList](http://help.syncfusion.com/js/api/ejrte#members:tools-customUnorderedList) tool on the editor’s toolbar.

The customUnorderedList having below options for an unordered list customization.

<table>
<tr>
<th>
Option<br/><br/></th><th>
Summary<br/><br/></th></tr>
<tr><td>Name</td><td>Specifies the name for customUnorderedList item.</td></tr>
<tr><td>Tooltip</td><td>Specifies the title for customUnorderedList item.</td></tr>
<tr><td>CSS</td><td>Specifies the styles for customUnorderedList item.</td></tr>
<tr><td>Text</td><td>Specifies the text for customUnorderedList item.</td></tr>
<tr><td>ListStyle</td><td>Specifies the list style for customUnorderedList item.</td></tr>
<tr><td>ListImage</td><td>Specifies the image for customUnorderedList item.</td></tr>
</table>

{% highlight html %}

<ej:RTE ID="rteSample" AllowEditing="true" ToolsList="lists" runat="server">
    <Tools Lists="unorderedList,orderedList">
        <CustomUnorderedList>
            <ej:CustomUnorderedList Text="Smiley" ListImage="url('../Content/images/rte/Smiley-GIF.gif')" Name="unOrderInsert" Tooltip="Custom UnOrderList" Css="e-rte-toolbar-icon e-rte-unlistitems customUnOrder" />
        </CustomUnorderedList>
    </Tools>
</ej:RTE>
    
{% endhighlight %}

![](WorkingwithLists_images/unordered.png)

