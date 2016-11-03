---
layout: post
title: Getting Started | Button | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: Button
documentation: ug
---

# Getting Started

This section explains you briefly on how to create a Button in your application with ASP.NET

## Create your first Button in ASP.NET

Essential JavaScript Button helps to display a Button widget within a web page and allows you to Click, Toggle Click, Reset, and Submit. The following example illustrates how to customize Button control in a Media Player and Office Ribbon Application. 

The following screenshot illustrates the functionality of a Button control in Media Player and Office Ribbon Application.

![](Getting-Started_images/Getting-Started_img1.png)


## Create Button control

ASP.NET Button control has different functionalities such as Display as Only Image Content or Image Content with Text.

You can create an ASP.NETProject and add necessary Dll’s and Scripts with the help of the given [ ASP.NET -Getting Started](http://help.syncfusion.com/aspnet/button/getting-started) Documentation.

 Add the following code example to the corresponding ASPX page to render Button. Refer to the following links to know details on ToggleButton and SplitButton.

ToggleButton : <http://help.syncfusion.com/js/togglebutton/getting-started>

SplitButton :  <http://help.syncfusion.com/js/splitbutton/getting-started>



{% highlight html %}

<div class="case1">

    <table>

        <tr>

            <td>

                <ej:togglebutton id="Play" runat="server" showroundedcorner="true" defaulttext="Play"

                    activetext="Pause" size="Large" clientsideonclick="playpause" contenttype="TextAndImage"

                    activeprefixicon="e-icon e-mediapause" defaultprefixicon="e-icon e-mediaplay">

                    </ej:togglebutton>

            </td>

            <td>

                <ej:button id="Start" runat="server" text="Start" size="Large" showroundedcorner="true"

                    clientsideonclick="stop">

                    </ej:button>

            </td>

            <td>

                <ej:button id="Stop" runat="server" text="stop" size="Large" showroundedcorner="true"

                    clientsideonclick="start">

                    </ej:button>

            </td>

            <td>

                <ej:button id="Open" runat="server" text="Open" size="Large" showroundedcorner="true">

                    </ej:button>

            </td>

            <td>

                <ej:splitbutton id="Save" runat="server" size="Large" showroundedcorner="true" text="save">

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

        <span>Hi Welcome!</span></p>

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

    <ej:togglebutton id="Bold" runat="server" defaulttext="Bold" activetext="Bold" showroundedcorner="true"

        size="Small" clientsideonclick="boldSetunset">

                    </ej:togglebutton>

</td>

<td>

    <ej:togglebutton id="Italic" runat="server" defaulttext="Italic" showroundedcorner="true"

        size="Small" clientsideonclick="italicSetunset">

                    </ej:togglebutton>

</td>

<td>

    <ej:splitbutton id="Underline" runat="server" text="Underline" size="Small" showroundedcorner="true"

        clientsideonclick="underlineSetunset" clientsideonitemselected="select">

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

    function boldSetunset(e) {

        if (e.isChecked) {

            $(".sample span").wrap("<b></b>");<%--add the bold tag to span--%>

        }

        else {

            $(".sample span").unwrap("<b></b>");<%--remove the bold tag to span--%>

        }

    }

    function italicSetunset(e) {

        if ($(".sample span").parents().is("i")) {

            $(".sample span").unwrap("<i></i>");<%--remove the italic tag to span--%>

        }

        else {

            $(".sample span").wrap("<i></i>");<%--add the italic tag to span--%>

        }

    }

    function underlineSetunset(e) {

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


