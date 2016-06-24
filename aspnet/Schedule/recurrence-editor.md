---
title: Getting started with RecurrenceEditor component and basic render.	 	
description: Rendering a basic Recurrence editor with properties and generate the recurrence rule for Recurrence editor.
platform: aspnet
control: recurrence editor
documentation: ug
keywords: recurrence editor, recurrence widget, ejRecurrenceEditor, aspnet recurrence editor
---
# Recurrence Editor

The Recurrence Editor includes the entire recurrence related information in a separate portable manner which can be either utilized as a separate widget or else can be embed within the appointment window of Scheduler to enable recurrence options within it. The recurrence rule can be easily generated based on the frequency selected. The customizations such as changing the labels of the recurrence editor is also possible to achieve through its properties. The frequencies available are Never, Daily, Weekly, Monthly, Yearly and Every weekday.

## Getting Started

Follow the steps as mentioned in the [Getting Started](http://help.syncfusion.com/aspnet/getting-started) page of the Introduction part to create an MVC application with required assembly references, scripts and stylesheets to render the Recurrence Editor.

Add the basic Recurrence Editor code as shown below,

{% highlight html %}

<body>
    <ej:RecurrenceEditor ID="RecurrenceEditor" runat="server"></ej:RecurrenceEditor>
</body>

{% endhighlight %}

## Generating Recurrence Rule

The Recurrence Editor can be used to generate the recurrence rule as a string, based on the repeat options selected.

The following code example depicts the way to generate the recurrence rule.

{% highlight html %}

<!--Container for ejRecurrenceEditor widget-->
<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">
    <ej:RecurrenceEditor runat="server" SelectedRecurrenceType="2" Create="onCreate"></ej:RecurrenceEditor>
    <ej:Button ID="donerecur1" runat="server"  Type="Button" Text="Generate Rule" ShowRoundedCorner="true" ClientSideOnClick="closerecurrence"></ej:Button>
</asp:Content>

<script type="text/javascript">
    function onCreate() {
        this.element.find("#recurrencetype_wrapper").css("width", "33%");
    }
    function closerecurrence() {
        var obj = $(".e-recurrenceeditor").data("ejRecurrenceEditor")
        obj.closeRecurPublic();
        alert(obj._recRule);
    }
 </script>

{% endhighlight %}
