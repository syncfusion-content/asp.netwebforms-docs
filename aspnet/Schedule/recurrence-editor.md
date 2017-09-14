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

Follow the steps mentioned in the [Getting Started](http://help.syncfusion.com/aspnet/getting-started#manual-integration-of-syncfusion-aspnet-controls-into-the-newexisting-application) page of the Introduction part to create an ASP.NET application with the required assemblies, scripts and stylesheet reference. Simply add the below Recurrence Editor rendering code in the Source code section of the application.

{% highlight html %}

    <!--Container for ejRecurrenceEditor widget-->
    <ej:RecurrenceEditor ID="RecurrenceEditor1" runat="server"></ej:RecurrenceEditor>

{% endhighlight %}

## Generating Recurrence Rule

The Recurrence Editor can be used to generate the recurrence rule as a string, based on the repeat options selected.

The following code example depicts the way to generate the recurrence rule.

{% highlight html %}

<!--Container for ejRecurrenceEditor widget-->
<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">
    <ej:RecurrenceEditor ID="RecurrenceEditor1" runat="server" SelectedRecurrenceType="2" Create="onCreate"></ej:RecurrenceEditor>
    
    <!--Place a button control - so that while clicking on it, generate the recurrence rule for the selected options in the recurrence editor-->
    <ej:Button ID="donerecur1" runat="server"  Type="Button" Text="Generate Rule" ShowRoundedCorner="true" ClientSideOnClick="closeRecurrence"></ej:Button>
</asp:Content>

<script type="text/javascript">
    function onCreate() {
        this.element.find("#RecurrenceType_Wrapper").css("width", "33%");
    }
    function closeRecurrence() {
        var obj = $("#RecurrenceEditor1").data("ejRecurrenceEditor");        
        alert(obj.getRecurrenceRule());
    }
 </script>

{% endhighlight %}
