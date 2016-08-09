---
layout: post
title: Dimensions
description: dimensions
platform: aspnet
control: PivotChart
documentation: ug
---

#Dimensions

##Set size in percentage

You can customize the PivotChart dimension by setting the width and height of the control in percentage.

{% highlight html %}

<html>
<head>
    .....
    .....
    <style>
        #MyPivotChart1 {
            width:100%;
            height:450px;
        }
    </style>
</head>
<body>
    <form id="form1" runat="server">
                <ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" ClientIDMode="Static">
                    //Set size to Chart container                    
                    <Size Width="80%" Height="80%"></Size>
                </ej:PivotChart>
    </form>
</body>
</html>

{% endhighlight %}

##Set size in pixels

You can customize the PivotChart dimension by setting the width and height of the control in pixels.

{% highlight html %}

<html>
<head>
    .....
    .....
    <style>
        #MyPivotChart1 {
            width:950px;
            height:460px;
        }
    </style>
</head>
<body>
    <form id="form1" runat="server">
                <ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" ClientIDMode="Static">
                    //Set size to Chart container                    
                    <Size Width="950xp" Height="460px"></Size>
                </ej:PivotChart>
    </form>
</body>
</html>

{% endhighlight %}
 
![](Dimensions_images/Dimensions.png) 

##Responsive

PivotChart control supports responsive rendering based on the target device (desktop & tablet) resolution. It supports resolution upto 1024x600. You can enable responsiveness in PivotChart by setting `IsResponsive` property to true.

{% highlight html %}

<html>
<head>
    .....
    .....
    <style>
        #MyPivotChart1 {
            min-width:650px;
            min-height:460px;
        }
    </style>
</head>
<body>
    <form id="form1" runat="server">
                //Enable responsiveness to change the Chart size dynamically.
                <ej:PivotChart ID="MyPivotChart1" runat="server" Url="/RelationalChartService.svc" ClientIDMode="Static" IsResponsive="true">               
                    <Size Width="950xp" Height="460px"></Size>
                </ej:PivotChart>
    </form>
</body>
</html>

{% endhighlight %}

![](Dimensions_images/NormalView.png)

_Normal View_

![](Dimensions_images/ResponsiveView.png)

_ResponsiveView_

