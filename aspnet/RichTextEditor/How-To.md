---
layout: post
title: XHTML Validation in RichTextEditor control for Syncfusion Essential ASP.NET Webform
description: XHTML Validation to format the RichTextEditor control's content
platform: aspnet
control: RTE
documentation: ug
keywords: RichTextEditor, Server side events, Page Breaker
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

## Add the Page Breaker to the RTE’s tools

We don't have support for page break built-in RTE. But this can be achieved in custom tool options in RTE. We have prepared a sample by using line break in RTE.

Initialize the RTE with custom tool in the ToolsList.

{% highlight html %}

<ej:RTE ID="rteSample" AllowEditing="true" Width="100%" ToolsList="customTools" runat="server" MinWidth="200px">
    <RTEContent>
            The Rich Text Editor (RTE) control is an easy to render in
        client side. Customer easy to edit the contents and get the HTML content for
        the displayed content. A rich text editor control provides users with a toolbar
        that helps them to apply rich text formats to the text entered in the text
        area. 
    </RTEContent>
    <Tools>
        <CustomTools>
            <ej:CustomTools Action="pageBreak" Name="pageBreak" Text="pageBreak" Tooltip="Page Break" />
        </CustomTools>
    </Tools>
</ej:RTE>

{% endhighlight %}

Upon clicking to the pageBreak button, the corresponding function(“pageBreak”) will be triggered. In that, the “hr” tag will be inserted to the RTE by using “executeCommand” method.

{% highlight html %}

<script type="text/javascript">
    var rteObj; 
    function pageBreak() {
        rteObj = $("#<%=rteSample.ClientID%>").data("ejRTE");
        var para = document.createElement("hr");
        rteObj.executeCommand("inserthtml", para.outerHTML);  
    } 
</script>

{% endhighlight %}

![](HowTo_images/pageBreak.png)

## Render the RTE inside in the Dialog

While rendering RTE control inside Dialog, initially child control RTE will be rendered first, the parent control Dialog is rendered next, after which it will be appended in the document. 

{% highlight html %}

<ej:Dialog ID="Dialog1" ClientSideOnCreate="OnCreate" runat="server">
    <DialogContent>
        <ej:RTE ID="DefaultRTE" runat="server">
            <RTEContent>
                Description:
                The Rich Text Editor (RTE) control is an easy to render in
                client side. Customer easy to edit the contents and get the HTML content for
                the displayed content. A rich text editor control provides users with a toolbar
                that helps them to apply rich text formats to the text entered in the text
                area.
            </RTEContent>
        </ej:RTE>
    </DialogContent>
</ej:Dialog>

{% endhighlight %}

In this case, events will not be bounded for RTE control. So we cannot enter text into RTE while rendering RTE inside Dialog. To resolve this, you need to call refresh method of RTE control in the “ClientSideOnCreate” event of Dialog. This refresh method is used to refresh the RTE control and the events are re-bound. Please find the code for same:

{% highlight html %}

<script type="text/javascript">
    function OnCreate(args)
    {
        var rteObj = $("#<%=DefaultRTE.ClientID%>").data("ejRTE");
        rteObj.refresh();
    }
    
</script>

{% endhighlight %}

![](HowTo_images/Dialog.png)

## Post RichTextEditor content to server-side on submit without reloading the page

The RichTextEditor value can be sent from client-side using AJAX post to the server . Bind the click event for submit button and pass the RichTextEditor text value as data through AJAX. This value can be retrieved as string in controller. To avoid full postback, render RichTextEditor inside `<asp:UpdatePanel>` with Asynchronous PostBack trigger. Refer to the following code.

{% highlight html %}

    <asp:UpdatePanel ID="panel" runat="server">
        <ContentTemplate>
            <ej:RTE ID="DefaultRTE" Width="100%" Height="100%" runat="server" MinWidth="200px">
                <RTEContent>
                    <p><b>Description:</b></p>
                    <p>
                        The Rich Text Editor (RTE) control is an easy to render in
        client side. Customer easy to edit the contents and get the HTML content for
        the displayed content. A rich text editor control provides users with a toolbar
        that helps them to apply rich text formats to the text entered in the text
        area.
                    </p>
                </RTEContent>
            </ej:RTE>
            <button id="submit" type="submit" onclick="onPost()">Submit</button>
        </ContentTemplate>
        <Triggers>
            <asp:AsyncPostBackTrigger ControlID="DefaultRTE" />
        </Triggers>
    </asp:UpdatePanel>
    <script>
        function onPost() {
            var rteObj = $("#<%=DefaultRTE.ClientID%>").data("ejRTE");
            $.ajax({
                type: "POST",
                url: "Default.aspx/Update",
                data: '{value: "' + rteObj.getText() + '" }',
                contentType: "application/json; charset=utf-8",
                dataType: "json",
                success: OnSuccess,
                failure: function (response) {
                    alert(response.d);
                }
            });
        }
        function OnSuccess(response) {
            alert(response.d);
        }
    </script>

{% endhighlight %}

RichTextEditor value can also be retrieved using `Value` property using its instance

{% highlight html %}

     protected void Page_Load(object sender, EventArgs e)
        {
            if (IsPostBack)
            {
                var RTEcontent = DefaultRTE.Value; //access the value here using control’s ID 
            }
        }

        [System.Web.Services.WebMethod]
        public static string Update(string value)
        {
            
            return value;
        }
{% endhighlight %}
