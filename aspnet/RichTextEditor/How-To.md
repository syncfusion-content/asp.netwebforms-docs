---
layout: post
title: XHTML Validation in RichTextEditor control for Syncfusion Essential ASP.NET Webform
description: XHTML Validation to format the RichTextEditor control's content
platform: aspnet
control: RTE
documentation: ug

---
# How to

## Initiate RTE in server side

Create an instance of the RichTextEditor control and set its properties in server side, as shown in the following example:

{% highlight html %}

    protected void Page_Load(object sender, EventArgs e)
    {
        Syncfusion.JavaScript.Web.RTE rte = new Syncfusion.JavaScript.Web.RTE();
            
        rte.ID = "RTE1";

        rte.Value = "The Essential RichTextEditor is a perfect HTML text editor component for the web that helps to enhance the editing experience. The editor provides powerful features such as file manager, formatting, links, tables, lists, localization, accessibility, and more.";

        List<String> toolsList = new List<string>() { "formatStyle", "font", "style", "effects", "alignment" };

        rte.ToolsList = toolsList;

        List<String> font = new List<string>() { "fontName", "fontSize", "fontColor", "backgroundColor" };
        List<String> style = new List<string>() { "bold", "italic", "underline", "strikethrough" };
        List<String> alignment = new List<string>() { "justifyLeft", "justifyCenter", "justifyRight", "justifyFull" };
        List<String> formatStyle = new List<string>() { "format" };
        List<String> effects = new List<string>() { "superscript", "subscript" };

        rte.Tools.Font = font;
        rte.Tools.FormatStyle = formatStyle;
        rte.Tools.Effects = effects;
        rte.Tools.Alignment = alignment;
        rte.Tools.Styles = style;


        ContentPlaceHolder ctrl = (ContentPlaceHolder)this.Master.FindControl("MainContent");
        ctrl.Controls.Add(rte);
    }

{% endhighlight %}
