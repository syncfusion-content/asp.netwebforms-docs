---
layout: post
title: Integration
description: integration
platform: aspnet
control: Control Name undefined
documentation: ug
---

# Integration

## Angular binding 

ListBox widget contains two types of angular JS support namely, 

* One way binding
* Two way binding 

One way binding refers to the process of applying scope values to all the available properties of the ListBox widget, but the changes made in ListBox widget does not reflect or trigger in turn to the scope collection. This kind of binding applies to all the properties of the ListBox widget.

Two-way binding supports both the processes – it applies the scope values to the ListBox properties as well as the changes made in the ListBox widget is also reflected back and triggered within the angular scope change function.

To know more detail about the Angular binding, you can refer to the following link location,

[http://help.syncfusion.com/ug/js/documents/angularjs.htm](http://help.syncfusion.com/ug/js/documents/angularjs.htm)

The following example depicts the way to bind data to the ListBox widget through angular support.

Note: You can include the “ej.widget.angular.min.js” file library to achieve this behaviour and you can pass the control properties as data attribute in ul tag itself as like data role behaviour.



In an ASPX page, add an element to configure ListBox.



{% highlight html %}

    <div ng-app="ListCtrl">

        <div ng-controller="ListBoxCtrl">

            <div id="control" style="height: 300px;">

                <table>

                    <tr>

                        <td>

                            <div class="ctrllabel">Select a section</div>

                            <ul id="bookselect" ej-listbox e-datasource="dataList" e-value="value">

                            </ul>

                        </td>

                        <td id="binding">

                            <div>

                                <input type="text" id="dropvalue" class="input ejinputtext" ng-model="value" />

                                <h6><span style="font-style: italic; font-weight: normal; position: absolute; margin-top: 4px;">Note:Two Way Angular Support</span></h6>

                            </div>

                        </td>

                    </tr>

                </table>

            </div>

        </div>

    </div>





{% endhighlight %}



{% highlight js %}

var list = [

                { empid: "cr1", text: "Dodge Avenger" },

                { empid: "cr2", text: "Chrysler 200" },

                { empid: "cr3", text: "Ford Focus" },

                { empid: "cr4", text: "Ford Taurus", },

                { empid: "cr5", text: "Dazzler", },

                { empid: "cr6", text: "Chevy Spark", },

                { empid: "cr7", text: "Chevy Volt", },

                { empid: "cr8", text: "Honda Fit", },

                { empid: "cr9", text: "Honda Crosstour", },

                { empid: "cr10", text: "Acura RL", },

                { empid: "cr11", text: "Hyundai Elantra", },

                { empid: "cr12", text: "Mazda3", }

    ];

    angular.module('ListCtrl', ['ejangular'])

       .controller('ListBoxCtrl', function ($scope) {

           $scope.dataList = list;

           $scope.value = "Ford Focus";

       });





{% endhighlight %}



Add the following styles in your sample

{% highlight css %}

    #binding {

        width: 100px;

        padding-bottom: 216px;

        padding-left: 100px;

    }





{% endhighlight %}



Output of the above steps.

![](Integration_images/Integration_img1.png)



## Knockout binding

Knockout support allows you to bind the other elements against any of the available data models.

Two types of knockout binding is supported,

* One-way binding
* Two-way binding

One way binding refers to the process of applying observable values to all the available properties of the ListBox widget, but the changes made in the widget does not reflect and trigger in turn to the observable collection. This kind of binding applies to all the properties of the ListBox widget.

Two-way binding supports both the processes – it applies the observable values to the ListBox widget properties as well as the changes made in the ListBox widget is also reflected back and triggered within the observable collections. 

For more information about the knockout binding, refer to the following online documentation in the following link location,

[http://help.syncfusion.com/ug/js/documents/knockoutjs.htm](http://help.syncfusion.com/ug/js/documents/knockoutjs.htm)

The following example depicts the way to bind data to the ListBox widget through the knockout support that enables and populates data to a ListBox widget based on the value set to the other ListBox widget.


Note: You caninclude the “ej.widget.knockout.min.js” file library to achieve this behaviour and you can pass the control properties as data attribute in ul tag itself like data role behaviour.

In an ASPX page, add an element to configure ListBox.





{% highlight html %}

<div id="control">

    <table>

        <tr>

            <td>

                <div class="ctrllabel">Select a section</div>

                <ul id="controlselect" data-bind="ejListBox: { dataSource: dataList, value: value }">

                </ul>

            </td>

            <td id="binding">

                <div>

                    <input type="text" id="dropvalue" class="input ejinputtext" data-bind="value: value" />

                    <h6><span style="font-style: italic; font-weight: normal; position: absolute; margin-top: 4px;">Note:Two Way Knockout Support</span></h6>

                </div>

            </td>

        </tr>

    </table>

</div>



{% endhighlight %}



{% highlight js %}

$(function () {

        var carList = [

            { empid: "cr1", text: "Accordion" },

            { empid: "cr2", text: "Autocomplete" },

            { empid: "cr3", text: "Button" },

            { empid: "cr4", text: "Tab", },

            { empid: "cr5", text: "Menu", },

            { empid: "cr6", text: "Rating", },

            { empid: "cr7", text: "Slider", },

            { empid: "cr8", text: "Splitter", },

            { empid: "cr9", text: "Tagcloud", },

            { empid: "cr10", text: "Scroller", },

            { empid: "cr11", text: "TreeView", },

            { empid: "cr12", text: "WaitingPopup", }

        ];

        window.viewModel = {

dataList: ko.observable(carList),

            value: ko.observable("Button"),

        }

 ko.applyBindings(viewModel);

    });





{% endhighlight %}



Configure the styles.



{% highlight css %}

    #binding {

        width: 100px;

        padding-bottom: 216px;

        padding-left: 100px;



{% endhighlight %}



Output of the above steps.



 ![](Integration_images/Integration_img2.png)



