---
layout: post
title: Behavior settings | Toolbar | ASP.NET | Syncfusion
description: behavior settings
platform: aspnet
control: Toolbar
documentation: ug
---

# Behavior settings

The following are some miscellaneous properties that helps to change the behavior of the Toolbar control. The Toolbar items can be given directly without using database. It can be achieved by Items tag.

## Enabling Toolbar

The Toolbar property enabled is used to enable or disable the Toolbar. The value set to this property is Boolean type. Refer to the following code.

Add the following code example to the corresponding ASPX page to render the Toolbar Control

{% highlight html %}

<%--Refer Local data sections for styles--%>

<ej:Toolbar ID="toolbarcontent" runat="server" Width="290px" Enabled="true">

	<Items>

		<ej:ToolbarItem Id="Left" SpriteCssClass="ToolbarItems LeftAlign_tool" TooltipText="Left"></ej:ToolbarItem>

		<ej:ToolbarItem Id="Center" SpriteCssClass="ToolbarItems CenterAlign_tool" TooltipText="Center"></ej:ToolbarItem>

		<ej:ToolbarItem Id="Right" SpriteCssClass="ToolbarItems RightAlign_tool" TooltipText="Right"></ej:ToolbarItem>

		<ej:ToolbarItem Id="Justify" SpriteCssClass="ToolbarItems Justify_tool" TooltipText="Justify"></ej:ToolbarItem>

	</Items>

	<Items>

		<ej:ToolbarItem Id="Bold" SpriteCssClass="ToolbarItems Bold_tool" TooltipText="Bold"></ej:ToolbarItem>

		<ej:ToolbarItem Id="Italic" SpriteCssClass="ToolbarItems Italic_tool" TooltipText="Italic"></ej:ToolbarItem>

		<ej:ToolbarItem Id="StrikeThrough" SpriteCssClass="ToolbarItems StrikeThrough_tool" TooltipText="StrikeThrough"></ej:ToolbarItem>

		<ej:ToolbarItem Id="UnderLine" SpriteCssClass="ToolbarItems Underline_tool" TooltipText="UnderLine"></ej:ToolbarItem>

	</Items>

</ej:Toolbar>

{% endhighlight %}



## Hiding Toolbar 

The Toolbar property Hide is used to show or hide the Toolbar. The value set to this property is Boolean type.  Add the following code example in your ASPX page.



{% highlight html %}

<%--Refer Local Data section for style and data bound for toolbar items.--%>

<ej:Toolbar ID="toolbarcontent" runat="server" Width="300px" Hide="true" DataIdField="Id" DataTooltipTextField="Tooltip" DataSpriteCssClassField="Css"></ej:Toolbar>

{% endhighlight %}

## Disable Or Enable Separate Toolbar Item

We can enable or disable a separate toolbar item by using the following methods.

### Disable Item

The **Toolbar** method **disableItem** and **disableItemByID** can be used to disable separate toolbar item.  In the below code we have disabled the third toolbar item by using these two methods

{% highlight html %}

    <ej:Toolbar ID="editingToolbar" runat="server" Width="100%">
        <Items>
            <ej:ToolbarItem Id="cut" SpriteCssClass="e-icon e-cut_01" TooltipText="cut"></ej:ToolbarItem>
            <ej:ToolbarItem Id="copy" SpriteCssClass="e-icon e-copy_02" TooltipText="copy"></ej:ToolbarItem>
            <ej:ToolbarItem Id="paste" SpriteCssClass="e-icon e-paste_01" TooltipText="paste" IsSeparator="true"></ej:ToolbarItem>
        </Items>
        <Items>
            <ej:ToolbarItem Id="Bold" SpriteCssClass="e-icon e-bold_01" TooltipText="Bold"></ej:ToolbarItem>
            <ej:ToolbarItem Id="UnderLine" SpriteCssClass="e-icon e-underline_01" TooltipText="UnderLine"></ej:ToolbarItem>
            <ej:ToolbarItem Id="StrikeThrough" SpriteCssClass="e-icon e-strikethrough_01" TooltipText="StrikeThrough"></ej:ToolbarItem>
        </Items>
        <Items>
            <ej:ToolbarItem Id="Left" SpriteCssClass="e-icon e-align-left_01" TooltipText="Left"></ej:ToolbarItem>
            <ej:ToolbarItem Id="Center" SpriteCssClass="e-icon e-align-center_01" TooltipText="Center"></ej:ToolbarItem>
            <ej:ToolbarItem Id="Right" SpriteCssClass="e-icon e-align-right_01" TooltipText="Right"></ej:ToolbarItem>
            <ej:ToolbarItem Id="Justify" SpriteCssClass="e-icon e-align-justify_0" TooltipText="Justify"></ej:ToolbarItem>
        </Items>
    </ej:Toolbar>
    
{% endhighlight %}

{% highlight javascript %}
         $(function () {
            var obj = $("#<%=editingToolbar.ClientID%>").data("ejToolbar");
            obj.disableItem($(".e-toolbar li")[2]);
        })
{% endhighlight %}

OR

{% highlight javascript %}
       
        $(function () {
            var obj = $("#<%=editingToolbar.ClientID%>").data("ejToolbar");
            obj.disableItemByID("paste");
        })
    

{% endhighlight %}


![](Behaviour-settings_images/Behaviour-settings1.jpg)

### Enable Item

The **Toolbar** method **enableItem** and **enableItemByID** can be used to enable separate toolbar item. In the below code we have disabled the first five items initially and enabled the third toolbar item by using these two methods

{% highlight html %}

	 <ej:Toolbar ID="editingToolbar" runat="server" Width="100%" DisabledItemIndices="0,1,2,3,4">
        <Items>
            <ej:ToolbarItem Id="cut" SpriteCssClass="e-icon e-cut_01" TooltipText="cut"></ej:ToolbarItem>
            <ej:ToolbarItem Id="copy" SpriteCssClass="e-icon e-copy_02" TooltipText="copy"></ej:ToolbarItem>
            <ej:ToolbarItem Id="paste" SpriteCssClass="e-icon e-paste_01" TooltipText="paste" IsSeparator="true"></ej:ToolbarItem>
        </Items>
        <Items>
            <ej:ToolbarItem Id="Bold" SpriteCssClass="e-icon e-bold_01" TooltipText="Bold"></ej:ToolbarItem>
            <ej:ToolbarItem Id="UnderLine" SpriteCssClass="e-icon e-underline_01" TooltipText="UnderLine"></ej:ToolbarItem>
            <ej:ToolbarItem Id="StrikeThrough" SpriteCssClass="e-icon e-strikethrough_01" TooltipText="StrikeThrough"></ej:ToolbarItem>
        </Items>
        <Items>
            <ej:ToolbarItem Id="Left" SpriteCssClass="e-icon e-align-left_01" TooltipText="Left"></ej:ToolbarItem>
            <ej:ToolbarItem Id="Center" SpriteCssClass="e-icon e-align-center_01" TooltipText="Center"></ej:ToolbarItem>
            <ej:ToolbarItem Id="Right" SpriteCssClass="e-icon e-align-right_01" TooltipText="Right"></ej:ToolbarItem>
            <ej:ToolbarItem Id="Justify" SpriteCssClass="e-icon e-align-justify_0" TooltipText="Justify"></ej:ToolbarItem>
        </Items>
    </ej:Toolbar>

{% endhighlight %}

{% highlight javascript %}
          $(function () {
            var obj = $("#<%=editingToolbar.ClientID%>").data("ejToolbar");
            obj.enableItem($(".e-toolbar li")[2]);
        })
{% endhighlight %}

OR
{% highlight javascript %}
        $(function () {
                     var obj = $("#<%=editingToolbar.ClientID%>").data("ejToolbar");
                    obj.enableItemByID("paste");
                    
                });

{% endhighlight %}

![](Behaviour-settings_images/Behaviour-settings2.jpg)
