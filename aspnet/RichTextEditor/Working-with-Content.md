---
layout: post
title: Working with content related operation|RTE|Syncfusion|ASP.NET
description: Working with Content related changes in RichTextEditor control
platform: aspnet
control: RTE
documentation: ug
keywords: RichTextEditor, Submit Content, Refresh, IFrame Attributes, Persistence

---
# Working with Content

The editor creates the iframe element as the content area on control initialization, it is used to display and editing the content. In Content Area, the editor displays only the body tag of a &lt; iframe &gt; document. To set or modify details in the &lt; head &gt; tag, use [Source view](#footer#source-view) of the editor.

## IFrame Attributes

The editor allows you to passing an additional attributes to body tag of a &lt; iframe &gt; element using IFrameAttributes property. The property contains name/value pairs in string format, it is used to override the default appearance of the content area.

N> the content area’s font, color, margins, and background can be overridden using iframeAttributes property. You can specifies the editable behavior (content editable) of the content also in this property.

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

N> Background image for the RTE control : {{'[Link](http://jsplayground.syncfusion.com/Sync_cpaoqshs)'| markdownify }} <BR>
Set default font for the Iframe : {{'[Link](http://jsplayground.syncfusion.com/Sync_k2uwsibi)'| markdownify }}

## Adding CSS File

The editor offers you to add external CSS file to style the &lt; iframe &gt; element.  Easily change the appearance of editor’s content using an external CSS file. For example, apply default styles for headings (h1, h2, etc.) and lists (bulleted or numbered) of the editor’s content. 

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

N> Our RTE control editor section is an iframe. An iframe has another scope, so we can't access it to style using class which is defined in main document. To set the styles for the contents that kept inside the editor(iframe) we have to append the styles link in iframe head section.

## Content Editable

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
        editor._rteWrapper.appendTo($("#<%=Dialog1.ClientID%>"));
    }
    function refresh() {
        var editor = $("#<%=RTE1.ClientID%>").ejRTE("instance");
        editor.refresh()
    }
    </script>

{% endhighlight %}

## Persistence

The editor is capable to persist its content with HTML format. By default, the persistence support is disabled in the editor. When you set the EnablePersistence property to true, the persistence will be enabled in the editor.

N>  [local storage](http://www.w3schools.com/html/html5_webstorage.asp#) is not supported below ie9 version, therefore persistence support is fallback to [cookie](http://www.w3schools.com/js/js_cookies.asp#).

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

## Set Default Font Name and Font Size

* Set a default font name and font size to the font name and size drop-down programmatically.

N> •	By default, the editor’s < iframe > is initialized with “Segoe UI” font name and 3(12pt) font size. <BR> 
•	To change it, select a different font name and font size from the drop-down in the editor’s toolbar. <BR>
•	To apply different font style for particular section of the content, select the text that you would like to change, and select a required font style from the drop-down to apply the changes to the selected text.<BR>

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
        var object = editor._fontStyleDDL.ejDropDownList("instance");
        object.selectItemByIndex(7);
        var dropdownSize = editor._fontSizeDDL.ejDropDownList("instance");
        dropdownSize.selectItemByIndex(5);
    }
</script>

{% endhighlight %}

* Set default font name and size  for &lt; iframe &gt;’s body tag using [IFrameAttributes](user-interface#iframe-attributes) property.

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

## Adding Font names and size

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
        var object = editor._fontStyleDDL.ejDropDownList("instance");
        var dropdownSize = editor._fontSizeDDL.ejDropDownList("instance");
        object.option({ "dataSource": editor.defaults.fontName });
        dropdownSize.option({ "dataSource": editor.defaults.fontSize });
        object.selectItemByValue("CalibriLight");
        dropdownSize.selectItemByValue("8");
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
