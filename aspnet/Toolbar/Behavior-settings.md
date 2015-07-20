---
layout: post
title: Behavior-settings
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



