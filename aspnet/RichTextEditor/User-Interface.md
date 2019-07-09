---
layout: post
title: User Interface for the RichTextEditor | Syncfusion | ASP.NET
description: User Interface for RichTextEditor control (toolbar, content area, and footer)
platform: aspnet
control: RTE
documentation: ug
keywords: RichTextEditor, Toolbar Configuration, Toolbar Items, Custom Tools

---

# Toolbar Configuration

The editor’s toolbar contains a collection of tools such as bold, italic and text alignment buttons that are used to format the content.

However, in most integrations, it's desirable to change the toolbar configuration to suit needs. Fortunately, that's quite easy to do too.

<table>
<tr>
    <th> Property <br/><br/></th>
    <th> Description <br/><br/></th>
</tr>
<tr>
    <td> {{'[toolsList](http://help.syncfusion.com/js/api/ejrte#members:toolslist)'| markdownify }} <br/><br/></td>
    <td>  The toolsList option allows you to choose which tools appear on the toolbar, as well as the order and grouping of those items <br/><br/></td>
</tr>
<tr>
    <td> {{'[tools](http://help.syncfusion.com/js/api/ejrte#members:tools)'| markdownify }} <br/><br/></td>
    <td> The toolsList property is used to get the root group order and tools property is used to get the inner order of the corresponding groups displayed.<br/><br/></td>
</tr>
</table>

N> By default, when you tab from the textbox to the RTE, the first tools in the Toolbar of RTE will get focus not in the text area. <BR>
But we can able to focus the RTE text area by setting the tab index attribute as -1 to avoid the focus on RTE toolbar when we tab from textbox to RTE - {{'[Demo](http://jsplayground.syncfusion.com/Sync_1rlmhqbz)'| markdownify }}

## Toolbar Items

The following table lists the available buttons and dropdowns on the toolbar:

<table>
<tr>
<td>
Name<br/></td><td>
Summary<br/></td><td>
Initialization<br/></td><td>
isDefault?<br/></td></tr>
<tr>
<td>
Font <br/></td><td>
Applies font type, size, and color to the content<br/></td><td>
&lt;ej:RTE ID="RTE1" ToolsList="font" runat="server"><br/>&lt;Tools Font="fontName,fontSize,fontColor,backgroundColor">&lt;/Tools><br/>&lt;/ej:RTE><br/><br/></td><td>
No<br/></td></tr>
<tr>
<td>
Font style<br/></td><td>
Applies bold, italic, underline, and strikethrough formatting to the content<br/></td><td>
&lt;ej:RTE ID="RTE1" ToolsList="style" runat="server"><br/>&lt;Tools Styles="bold,italic,underline,strikethrough">&lt;/Tools><br/>&lt;/ej:RTE><br/><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Alignment<br/></td><td>
Align the content with left, center, and right margin.<br/></td><td>
&lt;ej:RTE ID="RTE1" ToolsList="alignment" runat="server"><br/>&lt;Tools Alignment="justifyLeft,justifyCenter,justifyRight,justifyFull">&lt;/Tools><br/>&lt;/ej:RTE> <br/><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
List<br/></td><td>
Create a new list item (bulleted/numbered).<br/></td><td>
&lt;ej:RTE ID="AllToolsSample" ToolsList=" lists " runat="server"><br/>&lt;Tools Lists="unorderedList,orderedList">&lt;/Tools><br/>&lt;/ej:RTE><br/><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Indents<br/></td><td>
Allows to increase/decrease the indent level of the content.<br/></td><td>
&lt;ej:RTE ID="AllToolsSample" ToolsList=" indenting " runat="server"> <br/>&lt;Tools Indenting="outdent,indent">&lt;/Tools><br/>&lt;/ej:RTE><br/><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Undo/Redo Action<br/></td><td>
Allows to undo/redo the actions<br/></td><td>
&lt;ej:RTE ID="AllToolsSample" ToolsList="doAction" runat="server"> <br/>&lt;Tools DoAction="undo,redo">&lt;/Tools><br/>&lt;/ej:RTE><br/><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Hyperlink<br/></td><td>
Creates a hyperlink to a text or image to a specific location in the content.<br/></td><td>
&lt;ej:RTE ID="AllToolsSample" ToolsList="links" runat="server"> <br/>&lt;Tools links = "createLink, removeLink”>&lt;/Tools><br/>&lt;/ej:RTE><br/><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Images<br/></td><td>
Inserts an image from an online source or local computer.<br/></td><td>
&lt;ej:RTE ID="AllToolsSample" ToolsList="images" runat="server"><br/>&lt;Tools Images="image">&lt;/Tools><br/>&lt;/ej:RTE><br/><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Media<br/></td><td>
Allows to embed a video into the document.<br/></td><td>
&lt;ej:RTE ID="AllToolsSample" ToolsList="media" runat="server"> <br/>&lt;Tools Media="video">&lt;/Tools><br/>&lt;/ej:RTE><br/><br/><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Table<br/></td><td>
Allows to add or modify Tables<br/></td><td>
&lt;ej:RTE ID="AllToolsSample" ToolsList="tables" runat="server"> <br/>&lt;Tools Tables="createTable,addRowAbove,addRowBelow,addColumnLeft,addColumnRight,deleteRow,deleteColumn,deleteTable">&lt;/Tools>   <br/>&lt;/ej:RTE>    <br/><br/><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Casing<br/></td><td>
Change the case of selected text in the content<br/></td><td>
&lt;ej:RTE ID="AllToolsSample" ToolsList="casing" runat="server"> <br/>&lt;Tools Casing="upperCase,lowerCase">&lt;/Tools><br/>&lt;/ej:RTE><br/><br/></td><td>
no<br/></td></tr>
<tr>
<td>
Scripts<br/></td><td>
Makes the selected text as superscript (higher) or subscript (lower).<br/></td><td>
&lt;ej:RTE ID="AllToolsSample" ToolsList="effects" runat="server"> <br/>&lt;Tools Effects="superscript,subscript">&lt;/Tools><br/>&lt;/ej:RTE><br/><br/><br/></td><td>
no<br/></td></tr>
<tr>
<td>
Format<br/></td><td>
Clears the formatting options like bold, italic, underline and more.<br/></td><td>
&lt;ej:RTE ID="AllToolsSample" ToolsList="formatStyle" runat="server"> <br/>&lt;Tools FormatStyle="format">&lt;/Tools><br/>&lt;/ej:RTE><br/><br/></td><td>
yes<br/></td></tr>
<tr>
<td>
Clipboard Actions<br/></td><td>
Controls the clipboard actions by applying specific action on the selected content.<br/></td><td>
&lt;ej:RTE ID="AllToolsSample" ToolsList="clipboard" runat="server"> <br/>&lt;Tools Clipboard="cut,copy,paste">&lt;/Tools><br/>&lt;/ej:RTE><br/><br/></td><td>
no<br/></td></tr>
</table>

## Rearrange Group

The toolbar contains groups, which are similar or related functionalities of toolbar items for efficient access. By default, the groups are arranged using the following order:

{% highlight html %}

	ToolsList = "formatStyle,font,style,effects,alignment,lists,indenting,clipboard,doAction, 
	clear,links,images,media,tables,casing,customTools,view"

{% endhighlight %}

The group can be rearranged on customization using the **ToolsList** property.

{% highlight html %}

<ej:RTE ID="AllToolsSample" Width="100%" Height="440"  runat="server"  ToolsList="links,lists,doAction,style,images">
    <RTEContent>
        Description:
        The Rich Text Editor (RTE) control is an easy to render in
        client side. Customer easy to edit the contents and get the HTML content for
        the displayed content. A rich text editor control provides users with a toolbar
        that helps them to apply rich text formats to the text entered in the text
        area. 
    </RTEContent>
    <Tools Styles="bold,italic,underline,strikethrough"
        DoAction="undo,redo"
        Lists="unorderedList,orderedList"
        Links="createLink,removeLink"
        Images="image">               
    </Tools>
</ej:RTE>

{% endhighlight %}

N> If you are not specifying any group in **ToolsList** property, the editor will create the toolbar with default group.

## Undo and Redo 

Undo and Redo buttons allow you to editing the text by disregard/cancel the recently made changes and restore it to previous state. It is a useful tool to restore the performed action which got changed by mistake. Up to 50 actions can be undo/redo in the editor by default. 

To undo and redo operations, do one of the following:

* Press the undo/redo button on the toolbar
* Press the **Ctrl** **+** **Z**/**Ctrl** **+** **Y** combination on the keyboard

{% highlight html %}

<ej:RTE ID="RTE1"  ToolsList="doAction" runat="server">
    <RTEContent>
        Description:
        <p> The Rich Text Editor (RTE) control is an easy to render in
        client side. Customer easy to edit the contents and get the HTML content for
        the displayed content. A rich text editor control provides users with a toolbar
        that helps them to apply rich text formats to the text entered in the text
        area. </p>
    </RTEContent>
    <Tools DoAction="undo,redo">               
    </Tools>
</ej:RTE>
	
{% endhighlight %}
	
## Clipboard Operations

The editor provides support for the clipboard operations (cut, copy, and paste) in all text and images using the toolbar buttons and the keyboard shortcuts. Toolbar includes buttons through which the clipboard operations, such as Cut, Copy, and Paste can be accessed.

You can use the keyboard shortcuts to perform the clipboard operations.

* Cut - CTRL+X
* Copy - CTRL+C
* Paste - CTRL+V

N> Some browsers block the clipboard access from JavaScript. If you want to use the Cut, Copy, and Paste buttons on the toolbar, you need to allow JavaScript to use the clipboard. If you don’t want to do this configuration, use CTRL+C, CTRL+X, and CTRL+V keyboard commands.

{% highlight html %}	

<ej:RTE ID="RTE1" ToolsList="clipboard" runat="server">
    <RTEContent>
        Description:
        <p> The Rich Text Editor (RTE) control is an easy to render in
        client side. Customer easy to edit the contents and get the HTML content for
        the displayed content. A rich text editor control provides users with a toolbar
        that helps them to apply rich text formats to the text entered in the text
        area. </p>
    </RTEContent>
    <Tools Clipboard="cut,copy,paste">               
    </Tools>
</ej:RTE>

{% endhighlight %}

## Specify Custom Tools

Beside the available built-in tools, the RichTextEditor’s toolbar functionality can be extended through custom tools, defined in the tools through the customTools options, which renders the custom toolbar items along with the built-in toolbar items.

The example below demonstrates how to add a custom tool button

{% highlight html %}

<ej:RTE ID="AllToolsSample" Width="100%" Height="440"  runat="server"  ToolsList="customTools">
    <RTEContent>
        Description:
        The Rich Text Editor (RTE) control is an easy to render in
        client side. Customer easy to edit the contents and get the HTML content for
        the displayed content. A rich text editor control provides users with a toolbar
        that helps them to apply rich text formats to the text entered in the text
        area. 
    </RTEContent>
        <Tools>
            <CustomTools>
                <ej:CustomTools Action="CustomTool" Css="insert-special-character" Name="specialCharacter" Text="Insert - O" Tooltip="Special Characters" />
            </CustomTools>      
    </Tools>
</ej:RTE>
	
{% endhighlight %}

Upon clicking the "Insert" button, the special character will be added to the RTE's content.

{% highlight html %}

<script>
        var rteObj =  $("#<%=AllToolsSample.ClientID%>").data("ejRTE");
    $(".insert-special-character").ejButton();
    $("#specialCharacter").ejDialog({ enableResize: false, enableModal: true, showOnInit: false, width: "auto", position: { X: 218, Y: 38 } });
    $(".special-table tbody tr td" ).addClass("special-table-data").on( "click", customTdClick);
    function customTdClick(args) {
        rteObj.executeCommand("inserthtml", args.currentTarget.innerText);
        $("#specialCharacter").ejDialog("close");
    }  
    function CustomTool(args){
        $("#specialCharacter").ejDialog("open");   
    }
</script>
    
{% endhighlight %}

Define the CSS that will be applied to the custom tool.

{% highlight html %}

.e-special-table tr td
{
    border:1px solid #c8c8c8;
}
.e-special-table-data:hover
{
    background-color:#86bcea;
    cursor:pointer;
}
	
{% endhighlight %}

N> The CSS class that defined for custom tool is directly applies to the newly added toolbar item. 

I> The custom buttons get a `insert-special-character` CSS class to allow styling, where name is the name specified in the custom tool configuration.
