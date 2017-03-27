---
layout: post
title: Getting Started | DateTimePicker | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: DateTimePicker
documentation: ug
---

# Getting Started

This section explains briefly how to create a **DateTimePicker** in your application with the ASP.NET.

## Create your first DateTimePicker in ASP.NET	

ASP.NET DateTimePicker provides support to display a calendar within a web page and allows you to pick a date and time from the calendar. In this example, you can learn how to customize the DateTimePicker in a real-time application for an appointment and to choose current time for one week. 

The following screenshot illustrates the functionality of a DateTimePicker with date range of maximum one week.

![](Getting-Started_images/Getting-Started_img1.png)



### Create DateTimePicker 

You can create an ASP.NET Project and add necessary assemblies and scripts with the help of the given [ASP-Getting Started](https://help.syncfusion.com/aspnet/getting-started) Documentation.



You can add the following code example to the corresponding ASPX page to render the DateTimePicker.



{% highlight html %}

<div class="content-container-fluid">

        <div class="row">

            <div class="cols-sample-area">

                <div class="frame">

                    <div class="control">

                        <ej:DateTimePicker ID="DateTimePicker1" runat="server" Value="7/18/2014" Width="180px">

                        </ej:DateTimePicker>

                    </div>

                </div>

            </div>

        </div>

    </div>



{% endhighlight %}



Add the following styles to show the DateTimePicker control in a horizontal order.



{% highlight css %}

        .control
        {
            margin: 0 auto;
            width: 210px;
        }


{% endhighlight %}



The following screenshot displays a DateTimePicker control.

![](Getting-Started_images/Getting-Started_img2.png) 



### Set the Min and Max Date with Time Interval

In a real-time appointment scenario, the appointment is open only for a limited number of days. You have to select a date and time within the given range. This can be achieved by using the properties **MinDateTime** and **MaxDateTime** that enable the specified date range in the DateTimePicker control.



{% highlight html %}



    <ej:DateTimePicker ID="DateTimePicker1" runat="server" Width="180px" Value="9/12/2014 1:30 PM" MinDateTime="9/7/2014 2:00 PM" MaxDateTime="9/30/2014 2:00 PM" Interval="30">

    </ej:DateTimePicker>





{% endhighlight %}



The following screenshot shows the output for the above code example.



![](Getting-Started_images/Getting-Started_img3.png) 



