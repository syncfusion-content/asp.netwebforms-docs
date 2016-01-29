---
layout: post
title: User Interface for the RichTextEditor control for Syncfusion Essential ASP.NET
description: User Interface for RichTextEditor control (toolbar, content area, and footer)
platform: ASP.NET
control: RTE
documentation: ug

---
# User Interface

The editor user interface (UI) is designed with the toolbar, content area (iframe), and footer elements.

## Toolbar

The editor’s toolbar contains buttons and dropdowns that help you to format your content.

### Toolbar Items

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

### Customize Toolbar

You can customize and rearrange the items (buttons and dropdowns) by adding, removing, and enabling/disabling on the editor’s toolbar. 

#### Rearrange Group

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

#### Add Toolbar item

The editor’s toolbar can be extended through the **CustomTools** option, which renders the custom toolbar items along with the built-in toolbar items. 

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
	                <ej:CustomTools Action="CustomTool" Css="e-rte-toolbar-icon insertcode" Name="insertcode" Text="insertcode" Tooltip="Insert code snippets" />
	          </CustomTools>      
	    </Tools>
	</ej:RTE>
	<script>
	    function CustomTool() {
	        var rte = $("#<%=AllToolsSample.ClientID%>").data("ejRTE");
	        // handle the execute action on click the custom tool
	    }
	</script> 
	
{% endhighlight %}

Define the CSS that will be applied to the custom tool.

{% highlight html %}

	<style>
	    .e-rte-toolbar-icon.insertcode:before{
	        content:"\e780";
	        font-size:18px;
	        margin:3px;
	    }
	</style>
	
{% endhighlight %}

N> The CSS class that defined for custom tool is directly applies to the newly added toolbar item. 

#### Remove Toolbar item

To remove a particular toolbar item, pass the id of a toolbar item to the [removeToolbarItem](http://help.syncfusion.com/js/api/ejrte#methods:removetoolbaritem) method.

{% highlight html %}

	<ej:RTE ID="AllToolsSample" ClientSideOnCreate="OnCreate" Width="100%" Height="440" runat="server"  ToolsList="font,style,alignment,lists,clipboard">
	    <RTEContent>
		    Description:
		    The Rich Text Editor (RTE) control is an easy to render in
		    client side. Customer easy to edit the contents and get the HTML content for
		    the displayed content. A rich text editor control provides users with a toolbar
		    that helps them to apply rich text formats to the text entered in the text
		    area. 
	    </RTEContent>
	      <Tools Font="fontName,fontSize,fontColor,backgroundColor"
	            Styles="bold,italic,underline,strikethrough"
	            Alignment="justifyLeft,justifyCenter,justifyRight,justifyFull"
	            Lists="unorderedList,orderedList"
	            Clipboard="cut,copy,paste">
	      </Tools>
	</ej:RTE>
	<script>
	    function OnCreate() {
	        var rte = $("#<%=AllToolsSample.ClientID%>").data("ejRTE");
	        rte.removeToolbarItem("bold");
	
	    }
	</script>   
	
{% endhighlight %}

N> This method completely removes the DOM element along with the events bounded to it.

#### Enable/Disable Toolbar item

The state of each toolbar item can be controlled by calling the client-side methods such as [enableToolbarItem](http://help.syncfusion.com/js/api/ejrte#methods:enabletoolbaritem) and [disableToolbatItem](http://help.syncfusion.com/js/api/ejrte#methods:disabletoolbaritem).

{% highlight js %}

	<script>
	    function OnCreate() {
	        var rte = $("#<%=AllToolsSample.ClientID%>").data("ejRTE");
	        rte.disableToolbarItem("bold");
	
	    }
	</script>
	
{% endhighlight %}

{% highlight js %}

	<script>
	    function OnCreate() {
	        var rte =$("#<%=AllToolsSample.ClientID%>").data("ejRTE");
	        rte.enableToolbarItem("bold");
	
	    }
	</script>  

{% endhighlight %}

N> If a toolbar item is in disabled state, then it will not have any interactivity including mouse hover.

### Show/Hide Toolbar

The toolbar can be initially set to visible or hidden within the editor using ShowToolbar API. Default value is “true”.

{% highlight html %}
	
	<ej:RTE ID="AllToolsSample" ShowToolBar="false" Width="100%" Height="440"   runat="server">
	    
	</ej:RTE>

{% endhighlight %}

## Content Area

The editor creates the iframe element as the content area on control initialization, it is used to display and editing the content. In Content Area, the editor displays only the body tag of a &lt; iframe &gt; document. To set or modify details in the &lt; head &gt; tag, use [Source view](#source-view) of the editor.

### IFrame Attributes

The editor allows you to passing an additional attributes to body tag of a &lt; iframe &gt; element using IFrameAttributes property. The property contains name/value pairs in string format, it is used to override the default appearance of the content area. For example, the content area’s font, color, margins, and background can be overridden using IFrameAttributes property. You can specifies the editable behavior (content editable) of the content also in this property. For more information about the content editable, see [content editable](#content-editable).

{% highlight html %}

	<ej:RTE ID="AllToolsSample" Width="100%" Height="440" runat="server">
	    <RTEContent>
		    Description:
		    The Rich Text Editor (RTE) control is an easy to render in
		    client side. Customer easy to edit the contents and get the HTML content for
		    the displayed content. A rich text editor control provides users with a toolbar
		    that helps them to apply rich text formats to the text entered in the text
		    area. 
	  
	    </RTEContent> 
	</ej:RTE>
	
{% endhighlight %}

In Code behind, define IFrameAttributes values,

{% highlight html %}

	 AllToolsSample.IFrameAttributes = new Dictionary<string, object> { { "style", "background-color:#e0ffff;color:#6495ed;" } };

{% endhighlight %}

### Adding CSS File

The editor offers you to add external CSS file to style the &lt; iframe &gt; element.  You can change the appearance of editor’s content using an external CSS file. For example, apply default styles for headings (h1, h2, etc.) and lists (bulleted or numbered) of the editor’s content. 

{% highlight html %}

	<ej:RTE ID="AllToolsSample" Width="100%" Height="440" runat="server" ExternalCSS="Content/Css/iframe-custom.css">
	    <RTEContent>
		    Description:
		    The Rich Text Editor (RTE) control is an easy to render in
		    client side. Customer easy to edit the contents and get the HTML content for
		    the displayed content. A rich text editor control provides users with a toolbar
		    that helps them to apply rich text formats to the text entered in the text
		    area. 
	  
	    </RTEContent> 
	</ej:RTE>

{% endhighlight %}

The new file named iframe-custom.css is created and moved to the content folder with the following styles.

{% highlight html %}

	h1 {
		color: navy;
		margin-left: 20px;
	}
	
	ul { 
		display: block;
		list-style-type: square;
		margin-left: 10px;
	}
	
	ol {
		display: block;
		list-style-type: circle;
		margin-right: 10px;
	}
	
{% endhighlight %}

### Content Editable

The editor provides option to control the editable behavior using AllowEditing property. When the AllowEditing property is set to false, the editor disables its editing functionality. 

{% highlight html %}
	
	<ej:RTE ID="AllToolsSample" Width="100%" Height="440" AllowEditing ="false" runat="server">
	    <RTEContent>
		    Description:
		    The Rich Text Editor (RTE) control is an easy to render in
		    client side. Customer easy to edit the contents and get the HTML content for
		    the displayed content. A rich text editor control provides users with a toolbar
		    that helps them to apply rich text formats to the text entered in the text
		    area. 
		  
	    </RTEContent> 
	</ej:RTE>

{% endhighlight %}

The ContentEditable attribute allows you to make any element of HTML content to become editable or non-editable.  

{% highlight html %}

	<ej:RTE ID="AllToolsSample" ClientSideOnCreate="onCreate" Width="100%" Height="440" runat="server">
	    <RTEContent>
	        Description:
			 <p>
	            The Rich Text Editor (RTE) control is an easy to render in
	            client side. Customer easy to edit the contents and get the HTML content for
	            the displayed content. A rich text editor control provides users with a toolbar
	            that helps them to apply rich text formats to the text entered in the text
	            area.
			</p> 
	    </RTEContent> 
	</ej:RTE>
	<script>
	    function onCreate() {
	         var editor = $("#<%=AllToolsSample.ClientID%>").ejRTE("instance");
	        var iframeDoc = editor.getDocument();
	        var paragraph = $("p", iframeDoc.body);
	        $($(paragraph)[0]).attr("contenteditable", "false");
	    }
	    
	</script>
	
{% endhighlight %}

N> Content editable is fully compatible with latest browsers, to know more details, see [here](http://www.w3schools.com/tags/att_global_contenteditable.asp#).

## Footer

This option allows you to specify which footer elements should be shown at the bottom of the editor. The available footer elements are listed below:

1. HTML View
2. HTML Tag Info
3. Characters Count / Word Count 
4. Clear Format
5. Resizer

When the footer is enabled, it displays the html tag, word Count, character count, clear format, resize icon and clear all the content icons, by default.

{% highlight html %}

	<ej:RTE ID="AllToolsSample"  ShowFooter="true" Width="100%" Height="440" runat="server">
	    <RTEContent>
	        Description:
	           <p> The Rich Text Editor (RTE) control is an easy to render in
	            client side. Customer easy to edit the contents and get the HTML content for
	            the displayed content. A rich text editor control provides users with a toolbar
	            that helps them to apply rich text formats to the text entered in the text
	            area. </p>
	  
	    </RTEContent> 
	</ej:RTE>
	
{% endhighlight %}

### Source View

Source view displays the HTML code of the content in a separate dialog. Source view allows you to view and edit the HTML Tags, scripts, and styles directly. If you made any modification in Source view directly, click **Update** button to synchronize with Design view.

You can paste HTML text into Source view. If you cut or copy from HTML source such as page source of Browser, paste as HTML (without escape characters) into Source view. 

{% highlight html %}

	<ej:RTE ID="AllToolsSample"  ShowFooter="true" ShowHtmlSource="true" Width="100%" Height="440" runat="server">
	    <RTEContent>
	        Description:
	           <p> The Rich Text Editor (RTE) control is an easy to render in
	            client side. Customer easy to edit the contents and get the HTML content for
	            the displayed content. A rich text editor control provides users with a toolbar
	            that helps them to apply rich text formats to the text entered in the text
	            area. </p>
	  
	    </RTEContent> 
	</ej:RTE>
{% endhighlight %}

N> Source view is useful for working directly with raw HTML text, so this tool is mainly used for advanced users who would like to have more control over the source of their content. 

### HTML Tag Info

The HTML tag info tool that shows the path of currently selected tag along with hierarchy of parent tags to which it belongs. The tag information is displayed at the bottom of the editor. It is used to determine which element has the focus in the editor’s content. 

{% highlight html %}

	<ej:RTE ID="AllToolsSample"  ShowFooter="true" ShowHtmlTagInfo="true" Width="100%" Height="440" runat="server">
	    <RTEContent>
	        Description:
	           <p> The Rich Text Editor (RTE) control is an easy to render in
	            client side. Customer easy to edit the contents and get the HTML content for
	            the displayed content. A rich text editor control provides users with a toolbar
	            that helps them to apply rich text formats to the text entered in the text
	            area. </p>
	  
	    </RTEContent> 
	</ej:RTE>
	
{% endhighlight %}

N> The outermost tag is the body tag of &lt; iframe &gt; element in design view, so it shows the path from currently selected path to the body tag.

### Characters Count/Word Count
The editor automatically counts the number of characters and words in the content while you type. The characters and words count displayed at the bottom of the editor. You can limit the number of characters in your content using [maxLength](http://help.syncfusion.com/js/api/ejrte#members:maxlength) property. By default, the editor sets the characters limit value as 7000 characters.

{% highlight html %}

	<ej:RTE ID="AllToolsSample"  ShowFooter="true" ShowCharCount="true" ShowWordCount="true" MaxLength="500" Width="100%" Height="440" runat="server">
	    <RTEContent>
	        Description:
	           <p> The Rich Text Editor (RTE) control is an easy to render in
	            client side. Customer easy to edit the contents and get the HTML content for
	            the displayed content. A rich text editor control provides users with a toolbar
	            that helps them to apply rich text formats to the text entered in the text
	            area. </p>
	  
	    </RTEContent> 
	</ej:RTE> 
	
{% endhighlight %}

N> The editor counts the characters by including the space, and this validation occurs while pasting the content into the editor also.

### Clear Format

The clear format tool is useful to remove all formatting styles (such as bold, italic, underline, color, superscript, subscript, and more) from currently selected text. As a result, all the text formatting will be cleared and return to its default formatting styles. When you set the ShowClearFormat property to true, the clear format tool will be displayed at bottom of the editor.

{% highlight html %}

	<ej:RTE ID="AllToolsSample"  ShowFooter="true" ShowClearFormat="true" Width="100%" Height="440" runat="server">
	    <RTEContent>
	        Description:
	           <p> The Rich Text Editor (RTE) control is an easy to render in
	            client side. Customer easy to edit the contents and get the HTML content for
	            the displayed content. A rich text editor control provides users with a toolbar
	            that helps them to apply rich text formats to the text entered in the text
	            area. </p>
	  
	    </RTEContent> 
	</ej:RTE> 

{% endhighlight %}

### Resize Handle

When you set the EnableResize property to true, resize handle will be displayed at bottom-right corner of the editor. You can drag the handle to change its size. On resizing, the editor will automatically adjust the toolbar, content area, and footer within it accordingly. Resize limits can be defined via MinHeight, MaxHeight, MinWidth, and MaxWidth properties. You can specify the size of the editor programmatically through the Height and Width properties. 

{% highlight html %}

	<ej:RTE ID="AllToolsSample"  ShowFooter="true" EnableResize="true" MaxHeight="500" MinHeight="250" MaxWidth="750" MinWidth="250" Width="100%" Height="440" runat="server">
	    <RTEContent>
	        Description:
	           <p> The Rich Text Editor (RTE) control is an easy to render in
	            client side. Customer easy to edit the contents and get the HTML content for
	            the displayed content. A rich text editor control provides users with a toolbar
	            that helps them to apply rich text formats to the text entered in the text
	            area. </p>
	  
	    </RTEContent> 
	</ej:RTE> 

{% endhighlight %}

N> When you set the EnableRTL property to true, the resize handle will automatically positioned to the bottom-left corner of the editor.






	