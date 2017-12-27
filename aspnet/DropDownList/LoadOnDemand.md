---

layout: post
title: Load on demand in DropDownList control for Syncfusion ASP.NET WebForm
description: Describes about the load on demand in DropDownList control for Syncfusion ASP.NET WebForm
platform: Web
control: DropDownList
documentation: ug
keywords: DropDownList, dropdown, loadOnDemand

---
## Load On Demand

The popup and lists will be generated while click on dropdown icon or text box. For this feature, the loadOnDemand property must be enabled.

{% highlight html %}

    <ej:DropDownList ID="selectCar" runat="server" TargetId="carsList" Width="100%" WatermarkText="Select a Car" LoadOnDemand="true"></ej:DropDownList>
            <div id="carsList">
                <ul>
                    <li>Audi A4</li>
                    <li>Audi A5</li>
                    <li>Audi A6</li>
                    <li>Audi A7</li>
                    <li>Audi A8</li>
                </ul>
            </div>

     
{% endhighlight %}

{% highlight javascript %}
  
        var target;
        
		$(function() { 
            var items = [{
                text: "ListItem 1",
                value: "item1"
            }, {
                text: "ListItem 2",
                value: "item2"
            }, {
                text: "ListItem 3",
                value: "item3"
            }, {
                text: "ListItem 4",
                value: "item4"
            }, {
                text: "ListItem 5",
                value: "item5"
            }];
        $('#dropdown1').ejDropDownList({
            dataSource: items,
            fields: {
                text: "text",
                value: "value"
            },
            loadOnDemand: true
        });
        
       

{% endhighlight %}

![](LoadOnDemand/loadondemand.png)