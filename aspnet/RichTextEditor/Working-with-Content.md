---
layout: post
title: Working with content related operation in RichTextEditor control for Syncfusion Essential ASP.NET
description: Working with Content related changes in RichTextEditor control
platform: ASP.NET
control: RTE
documentation: ug

---
# Working with Content

## Submit Content

The editor allows you to process its content before it is being submitted to the server on form submit event. You can use EnableHtmlEncode property to validate content on the client side to prevent invalid data from being submitted to the server.

{% highlight html %}

	<ej:RTE ID="RTE1" EnableHtmlEncode="true" runat="server">
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

## Refresh

When you move the editor’s wrapper element into another DOM element, the editor needs to be reinitialized by the [refresh](http://help.syncfusion.com/js/api/ejrte#methods:refresh) method to retain its content. The method reload the content area and rebind the events of the editor. 

{% highlight html %}

    <ej:RTE ID="RTE1" runat="server">
	    <RTEContent>
	        Description:
	        <p> The Rich Text Editor (RTE) control is an easy to render in
	        client side. Customer easy to edit the contents and get the HTML content for
	        the displayed content. A rich text editor control provides users with a toolbar
	        that helps them to apply rich text formats to the text entered in the text
	        area. </p>
	    </RTEContent>
	</ej:RTE>
	
	<ej:Dialog ID="Dialog1" runat="server"></ej:Dialog>
	
	<ej:Button ID="Button1" ClientSideOnClick ="appendTo" runat="server" Text="Append To"></ej:Button>
	<ej:Button ID="Button2" ClientSideOnClick="refresh" runat="server" Text="Refresh"></ej:Button>
	
	<script type="text/javascript">
	    function appendTo() {
	        var editor = $("#<%=RTE1.ClientID%>").ejRTE("instance");
	        editor._rteWapper.appendTo($("#<%=Dialog1.ClientID%>"));
	    }
	    function refresh() {
	        var editor = $("#<%=RTE1.ClientID%>").ejRTE("instance");
	        editor.refresh()
	    }
	 </script>

{% endhighlight %}

## Editing and Formatting 

The editor’s [toolbar](/js/richtexteditor/user-interface#toolbar) contains buttons and dropdowns that allow you to editing and formatting in your content.

* Font name, font size, and color
* Bold, italic, underline, and strikethrough
* Text Alignment – left, right, center, and justify
* Indent – left and right
* styles – quotation, normal,  headings, and sub-headings
* superscript and subscript
* casing – convert to lower case and upper case
* list – create ordered and unordered list

{% highlight html %}

	<ej:RTE ID="RTE1" ToolsList="formatStyle,font,style,effects,alignment,lists,indenting,clipboard,doAction,casing" runat="server">
        <RTEContent>
            Description:
            <p> The Rich Text Editor (RTE) control is an easy to render in
            client side. Customer easy to edit the contents and get the HTML content for
            the displayed content. A rich text editor control provides users with a toolbar
            that helps them to apply rich text formats to the text entered in the text
            area. </p>
        </RTEContent>
        <Tools Font="fontName,fontSize,fontColor,backgroundColor"
                Styles="bold,italic,underline,strikethrough"
                Alignment="justifyLeft,justifyCenter,justifyRight,justifyFull"
                Lists="unorderedList,orderedList"
                Clipboard="cut,copy,paste"
                DoAction="undo,redo"
                Effects="superscript,subscript"
                Casing="upperCase,lowerCase"
                FormatStyle="format"
                Indenting="outdent,indent" >               
            </Tools>
    </ej:RTE>

{% endhighlight %}

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

## Persistence

The editor is capable to persist its content with HTML format. By default, the persistence support is disabled in the editor. When you set the EnablePersistence property to true, the persistence will be enabled in the editor.

N>  [localstorage](http://www.w3schools.com/html/html5_webstorage.asp#) is not supported below ie9 version, therefore persistence support is fallback to [cookie](http://www.w3schools.com/js/js_cookies.asp#).

{% highlight html %}

	<ej:RTE ID="RTE1" EnablePersistence="true" runat="server">
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

## Change the Font

By default, the editor’s &lt; iframe &gt; is initialized with “Segoe UI” font name and 3(12pt) font size. To change it, select a different font name and font size from the drop-down in the editor’s toolbar. To apply different font style for particular section of the content, select the text that you would like to change, and select a required font style from the drop-down to apply the changes to the selected text.

### Set Default Font Name and Font Size

* Set a default font name and font size to the font name and size drop-down programmatically


{% highlight html %}

    <ej:RTE ID="RTE1" ClientSideOnCreate="onChange" ToolsList="font" runat="server">
        <RTEContent>
            Description:
            <p> The Rich Text Editor (RTE) control is an easy to render in
            client side. Customer easy to edit the contents and get the HTML content for
            the displayed content. A rich text editor control provides users with a toolbar
            that helps them to apply rich text formats to the text entered in the text
            area. </p>
        </RTEContent>
        <Tools Font="fontName,fontSize,fontColor,backgroundColor"></Tools>
    </ej:RTE>

    <script type="text/javascript">
        function onChange() {
            var editor = $("#<%=RTE1.ClientID%>").ejRTE("instance");
            var ddl = editor._fontStyleDDL.ejDropDownList("instance");
            ddl.selectItemByIndex(7);
            var ddlSize = editor._fontSizeDDL.ejDropDownList("instance");
            ddlSize.selectItemByIndex(5);
        }
     </script>

{% endhighlight %}

* You can set default font name and size  for &lt; iframe &gt;’s body tag using [IFrameAttributes](user-interface#iframe-attributes) property.

{% highlight html %}

	<ej:RTE ID="RTE1" runat="server">
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

In code behind, define IFrameAttribute value

{% highlight html %}

	RTE1.IFrameAttributes = new Dictionary<string, object> {{ "style", "font-family:Arial;font-size:14px"}};
    
{% endhighlight %}

* If you want to override the default font from CSS, create a style tag with CSS styles and append it to the &lt; iframe &gt;’s head tag of the editor.

{% highlight html %}

	<ej:RTE ID="RTE1" ClientSideOnCreate="onChange" runat="server">
        <RTEContent>
            Description:
            <p> The Rich Text Editor (RTE) control is an easy to render in
            client side. Customer easy to edit the contents and get the HTML content for
            the displayed content. A rich text editor control provides users with a toolbar
            that helps them to apply rich text formats to the text entered in the text
            area. </p>
        </RTEContent>
    </ej:RTE>
    <script>
        function onChange() {
            var css = "html,body{font-family:sans-serif;font-size:14px; }";
            var editorDoc = $("#<%=RTE1.ClientID%>").ejRTE("instance").getDocument();
            var styleTag = document.createElement("style");
            styleTag.type = "text/css";
            if (styleTag.styleSheet) 
                styleTag.styleSheet.cssText = css;
            else 
                styleTag.appendChild(document.createTextNode(css));
            editorDoc.head.appendChild(styleTag);
        }
    </script>

{% endhighlight %}

### Adding Font names and size

If you want to add additional font names and sizes to font drop-down, pass the font information as JSON data and bind it with instance of drop-down. 

{% highlight html %}

	<ej:RTE ID="RTE1" ToolsList="font" ClientSideOnCreate="onChange" runat="server">
        <RTEContent>
            Description:
            <p> The Rich Text Editor (RTE) control is an easy to render in
            client side. Customer easy to edit the contents and get the HTML content for
            the displayed content. A rich text editor control provides users with a toolbar
            that helps them to apply rich text formats to the text entered in the text
            area. </p>
        </RTEContent>
         <Tools Font="fontName,fontSize,fontColor,backgroundColor"></Tools>
    </ej:RTE>
    <script>
        function onChange() {
            var editor = $("#<%=RTE1.ClientID%>").ejRTE("instance");
            editor.defaults.fontName.push({ text: "Calibri Light", value: "CalibriLight" }, { text: "Calibri", value: "Calibri" });
            editor.defaults.fontSize.push({ text: "8 (42pt)", value: "8" });
    		var ddl = editor._fontStyleDDL.ejDropDownList("instance");
    		var ddlSize = editor._fontSizeDDL.ejDropDownList("instance");
            ddl.option({ "dataSource": editor.defaults.fontName });
    		ddlSize.option({ "dataSource": editor.defaults.fontSize });
            ddl.selectItemByValue("CalibriLight");
    		ddlSize.selectItemByValue("8");
        }
    </script>

{% endhighlight %}

## Insert the content at cursor

If you want to insert/paste the content at the current cursor position (or) to replace the selected content with some formatting, you can use pasteContent method in the editor.

{% highlight html %}

	<ej:RTE ID="RTE1" runat="server">
        <RTEContent>
            Description:
            <p> The Rich Text Editor (RTE) control is an easy to render in
            client side. Customer easy to edit the contents and get the HTML content for
            the displayed content. A rich text editor control provides users with a toolbar
            that helps them to apply rich text formats to the text entered in the text
            area. </p>
        </RTEContent>
    </ej:RTE>
    <ej:Button ID="Button1" ClientSideOnClick="onChange" runat="server" Text="Past Content"></ej:Button>
    <script>
        function onChange() {
            var editor = $("#<%=RTE1.ClientID%>").ejRTE("instance");
            var selectedHtml = editor.getSelectedHtml();
            editor.pasteContent("<p style ='background-color:yellow;color:skyblue'>" + selectedHtml + "</p>");
        }
    </script>

{% endhighlight %}

## Validation 

You can validate the RichTextEditor’s value on form submission by applying ValidationRules and ValidationMessage to the RichTextEditor.

N> [jquery.validate.min](http://cdn.syncfusion.com/js/assets/external/jquery.validate.min.js) script file should be referred for validation, for more details, refer [here](http://jqueryvalidation.org/documentation).

### jQuery Validation Methods

The following are jquery validation methods.

_List of jquery validation methods_

<table>
<tr>
<th>
Rules</th><th>
Description</th></tr>
<tr>
<td>
required</td><td>
 Requires value for the RichTextEditor control.</td></tr>
<tr>
<td>
minWordCount</td><td>
 Requires the value to be of given minimum words count.</td></tr>
<tr>
<td>
minlength</td><td>
 Requires the value to be of given minimum characters count.</td></tr>
<tr>
<td>
maxlength</td><td>
 Requires the value to be of given maximum characters count.</td></tr>
</table>

#### Validation Rules

The validation rules help you to verify the content by adding validation attributes to the text area. This can be set by using ValidationRules property.


#### Validation Messages 

You can set your own custom error message by using ValidationMessage property. To display the error message, specify the corresponding annotation attribute followed by the message to display.


N> jQuery predefined error messages to that annotation attribute will be shown when this property is not defined. 


When you initialize the RichTextEditor widget, it creates a text area hidden element which is used to store the value. Hence, the validation is performed based on the value stored in this hidden element.

Required field and minWordCount values validation is demonstrated in the below given example.

{% highlight html %}

    <ej:RTE ID="RTE1"  runat="server">
          <ValidationRule>
              <ej:KeyValue Key="required" Value="true" />
              <ej:KeyValue Key="minWordCount" Value="10" />
              <ej:KeyValue Key="maxWordCount" Value="100" />
          </ValidationRule>
          <ValidationMessage >
              <ej:KeyValue Key="required" Value="Please enter the content" />
              <ej:KeyValue Key="minWordCount" Value="A minimum of {10} words is required here." />
              <ej:KeyValue Key="maxWordCount" Value="A maximum of {100} words is required here." />
          </ValidationMessage>
          <RTEContent>
              When a user          
          </RTEContent>
      </ej:RTE>
      <br />
      <ej:Button ID="btn1" Text="Validate" OnClick="click" runat="server"> </ej:Button>
   
{% endhighlight %}

![](Additional_images/Validation.jpg)

### Using ASP.NET Validator

To use ASP.NET validators with RichTextEditor control, set the ID of the RichTextEditor as the value of the ControlToValidate property of the validator.

{% highlight html %}

    <asp:ValidationSummary ID="ValidationSummary1" runat="server" 
      DisplayMode ="BulletList" ShowSummary ="true" HeaderText="Errors:" />

     <ej:RTE ID="rteSample" Width="550px" Height="440" ShowFooter="true" ShowHtmlSource="true" IsResponsive="true" runat="server">
     </ej:RTE>

    <asp:RequiredFieldValidator ID="RequiredFieldValidator2"
        runat="server" ControlToValidate="rteSample"
        ErrorMessage="Please enter the value">
        </asp:RequiredFieldValidator>

    <ej:Button Type="Submit" Text="Validate" runat="server"></ej:Button>
     <br />

{% endhighlight %}

Executing the above code will validate the RichTextEditor control values on every form submit before post back occurs.

![](Additional_images/ValidatorASP.png)