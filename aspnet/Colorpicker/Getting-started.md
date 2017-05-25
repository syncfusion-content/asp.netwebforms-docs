---
layout: post
title: Getting started | ColorPicker | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: ColorPicker
documentation: ug
---

# Getting started

## Create your first ColorPicker in ASP.NET

The Essential ASP.NET WebForms ColorPicker control provides you support for selecting the colors in different sources such as palettes, picker or custom palettes. You can also rend the color value from control in three formats such as RGB, HSV and HEXCODE.

In this example, you can learn how to customize the ColorPicker control in a category Application.

![](Getting-started_images/Getting-started_img1.png)



In the following sections you can learn, How to:

* Create ColorPicker control
* Initialize the other widgets
* Add Value to ListBox Control

### Create ColorPicker Control

Use the following steps to create the ColorPicker control.

Create a WebFormsProject and add necessary Dll’s and scripts with the help of the given [WebForms-Getting Started](https://help.syncfusion.com/aspnet/getting-started) Documentation.

Create the ASPX page and add the following code to it for ColorPicker creation. 

{% highlight html %}



<ej:ColorPicker runat="server" ID="CategoryColor" Value="#278787"> </ej:ColorPicker>



{% endhighlight %}



 Run this code to render the resultant output of the above steps.

![](Getting-started_images/Getting-started_img2.png)



### Initialize the other widgets

To add the priority value to the ListBox, the text value is obtained from the input element and color for each priority is received by the ColorPicker control. To add each new priority value to the ListBox control, click the Add button.

You can refer to the following link for more information on creation on the ListBox

<https://help.syncfusion.com/api/js/ejlistbox>

The following code example is used to create the Priority form by using ListBox control and ColorPicker control.

{% highlight html %}



<div class="content-container-fluid">
        <div class="row">
            <div class="sample-area">
                <div class="frame">
                    <div id="control">
                        <ul id="ColorValues">
                            <li><span class="color high"></span>High</li>
                            <li><span class="color normal"></span>Normal</li>
                            <li><span class="color low"></span>Low</li>
                        </ul>
                        <ej:ListBox ID="selectPriority" runat="server"TargetID="ColorValues"></ej:ListBox>
                    </div>
                </div>
            </div>
            <div id="Properties">
                <table class="prop-grid">
                    <tr class="row">
                        <td class="column">Name
                        </td>
                        <td class="column">
                            <input type="text" id="categoryName" />
                        </td>
                    </tr>
                    <tr class="row">
                        <td class="column">Color
                        </td>
                        <td class="column">
                            <!--Colorpicker element-->
                            <ej:ColorPicker ID="CategoryColor" runat="server"Value="#278787"></ej:ColorPicker>                           
                        </td>
                        <td class="column">
                            <!--Add button for add the new category-->
                            <ej:Button ID="AddCategory" runat="server" Text="Add"Width="82px" Type="Button" Height="21px" ClientSideOnClick="addCategoryValue"> </ej:Button>                           
                        </td>
                    </tr>                   
                </table>
            </div>
        </div>
    </div>


{% endhighlight %}



Add the following style section to align form fields. 

{% highlight css %}

    .content-container-fluid > .row {
        width: 410px;
        border: 1px solid #bbbcbb;
        padding: 16px;
        height: 272px;
    }
    .color.high {
        background-color: red;
    }
    .color.normal {
        background-color: green;
    }
    .color.low {
        background-color: blue;
    }
    .sample-area {
        width: 205px;
    }
    .sample-area, #Properties {
        display: inline-block;
        float: left;
    }
    #Properties #categoryName {
        width: 140px;
        height: 20px;
    }
    #Properties .column {
        display: inline-block;
        width: 45px;
        margin: 10px 0 0;
    }
    #Properties .row {
        padding: 10px 0px 5px 0px;
    }
    .color {
        width: 13px;
        height: 13px;
        border: 1px solid;
        display: inline-block;
        margin-right: 6px;
        margin-bottom: -3px;
    }

{% endhighlight %}

Initialize the element in &lt;script&gt; tag. 

{% highlight js %}

    var listBoxObj, colorObj;

    jQuery(function ($) {

        //initialize the listbox with object creation

        listBoxObj = $("#selectPriority").data('ejListBox');

        //initialize the colorpicker with object creation

        colorObj = $("#CategoryColor").data('ejColorPicker');       

    });





{% endhighlight %}



Run the above code to render the following output.

![](Getting-started_images/Getting-started_img3.png)



### Add value to ListBox Control

You can add the value to the ListBox with selected color by performing the button click event. The following script section define the click event for the button element.

Initialize the click event to button element in the &lt;script&gt; tag.

{% highlight js %}

        jQuery(function ($) {

        function addCategoryValue() {

            if ($("#categoryName").val() !== "") {

                listBoxObj.addItem("<span class='color' style='background-color: " + colorObj.getValue() + "' ></span>" + $("#categoryName").val());

                $("#categoryName").val("");

            }

        }





{% endhighlight %}



The following screenshot illustrates the resultant output after you click Add button.

![](Getting-started_images/Getting-started_img4.png)



