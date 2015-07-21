---
layout: post
title: KO-ResultSet
description: ko resultset
platform: aspnet
control: DataManager
documentation: ug
---

# KO ResultSet

The DataManager contains a default method to subscribe the viewmodel properties as KO observable. This is done at the success of the executeQuery by using the getKnockoutModel. You can also provide computed properties to the viewmodel by using the getKnockoutModel.

The following code example illustrates on how the model is made observable and updated.

{% highlight html %}

&lt;asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="MainContent"&gt;

    &lt;ej:DataManager ID="FlatData" runat="server" Adaptor="JsonAdaptor"/&gt;

    &lt;div&gt;

        &lt;div id="Grid" data-bind="ejGrid: { dataSource: dataSource, allowPaging: true, pageSettings: { currentPage: currentPage, pageSize: 4 }}"&gt;&lt;/div&gt;

    &lt;/div&gt;

     &lt;ej:Button runat="server" Type="Button" Text="Binding" ClientSideOnClick="onClick" ID="submit"&gt;&lt;/ej:Button&gt;

&lt;/asp:Content&gt;

&lt;asp:Content ID="Content2" ContentPlaceHolderID="ScriptSection" runat="server"&gt;

    &lt;script src="../Scripts/knockout-min.js"&gt;&lt;/script&gt;

    &lt;script src="../Scripts/ej/ej.widget.ko.min.js"&gt;&lt;/script&gt;

    &lt;script type="text/javascript" class="jsScript"&gt;

        function onClick(arg) {

            var data = window.FlatData;

            window.employeeView = {

                dataSource: ko.observableArray(data),

            };

            ko.applyBindings(employeeView);

            var proxy = $("#MainContent_OrdersGrid").ejGrid("instance");

            proxy.refreshContent();

        }



    &lt;/script&gt;

 &lt;/asp:Content&gt;
 
 {% endhighlight %}

The result of the above code example is illustrated as follows.

Before changing the model, EmployeeID 1 has FullName value as Nancy Davolio. After changing, the result is as follows.

![](KO-ResultSet_images/KO-ResultSet_img1.png) 
{:.image }




