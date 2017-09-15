---
layout: post
title: Getting Started | Button | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: Button
documentation: ug
---

# Getting Started

This section explains you briefly on how to create a **Button** in your application with ASP.NET

## Create your first Button in ASP.NET

**Essential ASP.NET Button** helps to display a Button widget within a web page and allows you to Click, Toggle Click, Reset, and Submit. The following example illustrates how to customize Button control in a Media Player and Office Ribbon Application. 

The following screenshot illustrates the functionality of a Button control in Media Player and Office Ribbon Application.

![](Getting-Started_images/Getting-Started_img1.png)


## Create Button control

ASP.NET Button control has different functionalities such as Display as Only Image Content or Image Content with Text.

You can create an ASP.NETProject and add necessary Dll’s and Scripts with the help of the given [ ASP.NET -Getting Started](https://help.syncfusion.com/aspnet/getting-started) Documentation.

 Add the following code example in the corresponding ASPX page to render Button. Refer the following links to know details on ToggleButton and SplitButton.

ToggleButton : <http://help.syncfusion.com/js/togglebutton/getting-started>

SplitButton :  <http://help.syncfusion.com/js/splitbutton/getting-started>



{% highlight html %}

    <div class="case1">
        <table>
            <tr>
                <td>
                    <ej:togglebutton ID="Play" runat="server" ShowRoundedCorner="true" DefaultText="Play"
                                     ActiveText="Pause" Size="Large" ClientSideOnClick="playPause" ContentType="TextAndImage"
                                     ActivePrefixIcon="e-icon e-mediapause" DefaultPrefixIcon="e-icon e-mediaplay">
                    </ej:togglebutton>
                </td>
                <td>
                    <ej:button ID="Start" runat="server" Text="Start" Size="Large" ShowRoundedCorner="true"
                               ClientSideOnClick="stop"></ej:button>
                </td>
                <td>
                    <ej:button ID="Stop" runat="server" Text="stop" Size="Large" ShowRoundedCorner="true"
                               ClientSideOnClick="start"></ej:button>
                </td>
                <td>
                    <ej:button ID="Open" runat="server" Text="Open" Size="Large" ShowRoundedCorner="true"></ej:button>
                </td>
                <td>
                    <ej:splitbutton ID="Save" runat="server" Size="Large" ShowRoundedCorner="true" Text="save">
                        <Items>
                            <ej:SplitItem Text="Open...">
                            </ej:SplitItem>
                            <ej:SplitItem Text="Save">
                            </ej:SplitItem>
                            <ej:SplitItem Text="Delete">
                            </ej:SplitItem>
                        </Items>
                    </ej:splitbutton>
                </td>
            </tr>
        </table>
        <p class="sample">
            <span>Hi Welcome!</span>
        </p>
    </div>

{% endhighlight %}

Add the following styles to show the Button control in the center of a web page. 

{% highlight css %}

<style type="text/css">
        ul li span {
            color: white;
        }
        .case1 {
            margin: 100px;
        }
        .officeribben {
            margin: 100px;
        }
        .sample {
            margin: 100px;
        }
        .audiodiv {
            margin: 100px;
        }
    </style>

{% endhighlight %}

![C:/Users/jeganprakash/Desktop/Documentation/Images/Button/1.PNG](Getting-Started_images/Getting-Started_img2.png)


## Create Office Ribbon Control

In a real-time scenario, MS Office Bold and Italic options work as a Toggle Button and Underline option works as a Split Button. Here, you can learn how to use Button control feature by using the Office Ribbon options.

Add Button controls by using the following code example. 

{% highlight html %}

 <td>
        <ej:togglebutton ID="Bold" runat="server" DefaultText="Bold" ActiveText="Bold" ShowRoundedCorner="true"
                         Size="Small" ClientSideOnClick="boldSetUnset">
        </ej:togglebutton>
    </td>
    <td>
        <ej:togglebutton ID="Italic" runat="server" DefaultText="Italic" ShowRoundedCorner="true"
                         Size="Small" ClientSideOnClick="italicSetUnset">
        </ej:togglebutton>
    </td>
    <td>
        <ej:splitbutton ID="Underline" runat="server" Text="Underline" Size="Small" ShowRoundedCorner="true"
                        ClientSideOnClick="underlineSetUnset" ClientSideOnItemSelected="select">
            <Items>
                <ej:SplitItem Text="Dotted Line">
                </ej:SplitItem>
                <ej:SplitItem Text="solid">
                </ej:SplitItem>
                <ej:SplitItem Text="dashed">
                </ej:SplitItem>
            </Items>
        </ej:splitbutton>
</td>

{% endhighlight %}

Add Function Definition from click event to Button function. 

{% highlight js %}

<script type="text/javascript">
    function boldSetUnset(e) {
        if (e.isChecked) {
            $(".sample span").wrap("<b></b>");<%--add the bold tag to span--%>
        }
        else {
            $(".sample span").unwrap("<b></b>");<%--remove the bold tag to span--%>
        }
    }
    function italicSetUnset(e) {
        if ($(".sample span").parents().is("i")) {
            $(".sample span").unwrap("<i></i>");<%--remove the italic tag to span--%>
        }
        else {
            $(".sample span").wrap("<i></i>");<%--add the italic tag to span--%>
        }
    }
    function underlineSetUnset(e) {
        if ($(".sample span").parents().is("u")) {
            $(".sample span").unwrap("<u></u>");<%--remove the underline tag to span--%>
        } else {
            $(".sample span").wrap("<u></u>");<%--add the underline tag to span--%>
        }
    }
    function select(e) {
        if ($(".sample span:last-child").parents().is("span")) {
            $(".sample #under span").unwrap("<span id='under'></span>");
        }
        switch (e.events.text) {
            case "Dotted Line": $(".sample span").wrap("<span id='under' style='border-bottom: 1px dotted #000000;'></span>");
                break;
            case "solid": $(".sample span").wrap("<span id='under' style='border-bottom: 1px solid #000000;'></span>");
                break;
            case "dashed": $(".sample span").wrap("<span id='under' style='border-bottom: 1px dashed #000000;'></span>");
                break;
        }
    }
</script>

{% endhighlight %}

<table>
<tr>
<td>
{{ '![C:/Users/jeganprakash/Desktop/Documentation/Images/Button/3.PNG](Getting-Started_images/Getting-Started_img3.png)' | markdownify }}
</td></tr>
<tr>
<td>
{{ '![](Getting-Started_images/Getting-Started_img4.png)' | markdownify }}
</td></tr>
</table>


