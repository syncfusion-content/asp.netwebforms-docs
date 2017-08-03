---
layout: post
title: Integration | ColorPicker | ASP.NET Webforms | Syncfusion
description: integration
platform: aspnet
control: ColorPicker
documentation: ug
---

# Integration

## AngularJS Binding

The ColorPicker control is availed with two types of AngularJS support namely, 

* One-way binding
* Two-way binding 

One-way binding refers to the process of applying scope values to all the available properties of the ColorPicker control. The changes made in the ColorPicker control are not reflected or triggered in turn to the scope collection. This kind of binding is applied to all the properties of the ColorPicker control.

Two-way binding supports both the processes. It applies the scope values to the ColorPicker properties, as well as the changes made in the ColorPicker control are reflected back and triggered within the AngularJS scope change function.

Apply the plugin and property assigning to the ColorPicker control element through the directive that starts with “e-“.

To know more about the AngularJS binding, you can refer to the online documentation in the following link location,

<http://help.syncfusion.com/js/angularjs>

The following code example explains how to bind data to the ColorPicker control through AngularJS support.

{% highlight html %}

    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{site.releaseversion}}/js/web/ej.unobtrusive.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{site.releaseversion}}/js/ej.widget.angular.min.js"></script>
    <div class="content-container-fluid" ng-app="PickerCtrl">
        <div class="row" style="width: 100%" ng-controller="ColorPickerCtrl">
            <div class="cols-sample-area" style="width: 100%">
                <div class="frame">
                    <div id="control">
                        <div class="element" style="margin-left: 45px;">
                            <input id="picker" ej-colorpicker e-value="colorValue" e-modeltype="palette" />
                        </div>
                        <div class="element" style="margin-left: 234px">
                            <input id="custom" ej-colorpicker e-value="colorValue" e-modeltype="picker" />
                        </div>
                        <h6><span style="font-style: italic; font-weight: normal; position: absolute; margin-top: 5px; margin-left: 45px;">Note:Two Way AngularJS Support</span></h6>
                    </div>
                </div>
            </div>
            <script>
            angular.module('PickerCtrl', ['ejangular'])
              .controller('ColorPickerCtrl', function ($scope) {
                  $scope.colorValue = "#278787";
              });
            </script>
        </div>
    </div>
    <style>
        .element {
            display: inline-block;
        }

        .frame {
            width: 457px;
            border: 0px;
        }

        #control {
            width: 600px;
        }
    </style>


{% endhighlight %}



The following screenshot displays the output of the above code example.

![](Integration_images/Integration_img1.png)



## KnockoutJS Binding

KnockoutJS support allows you to bind the HTML elements against any of the available data models.

Two types of KnockoutJS binding is supported,

* One-way binding
* Two-way binding

One-way binding refers to the process of applying observable values to all the available properties of the ColorPicker control. The changes made in ColorPicker control are not reflected and triggered in turn to the observable collection. This kind of binding is applied to all the properties of the ColorPicker control.

Two-way binding supports both the processes. It applies the observable values to the ColorPicker control properties and also the changes made in the ColorPicker control are reflected back and triggered within the observable collections. 

For more information about KnockoutJS binding, you can refer to the online documentation in the following link location,

<http://help.syncfusion.com/js/knockoutjs>

The following code example explains how you can bind data to the ColorPicker control through KnockoutJS support that enables and populates data to a ColorPicker control based on the value set to the other ColorPicker control.

{% highlight html %}

    <script src="http://cdn.syncfusion.com/js/assets/external/knockout.min.js"></script>
    <script src="http://cdn.syncfusion.com/{{site.releaseversion}}/js/web/ej.unobtrusive.min.js "> </script>
    <script src="http://cdn.syncfusion.com/{{site.releaseversion}}/js/ej.widget.ko.min.js"></script>
    <div class="content-container-fluid">
        <div class="row" style="width: 100%">
            <div class="cols-sample-area" style="width: 100%">
                <div class="frame" style="width: 420px">
                    <div id="control" style="float: left; width: 70%; margin-left: 10px">
                        <input id="colorpick" data-bind="ejColorPicker: { value: value, modelType: palette }" />
                        <h6><span style="font-style: italic; font-weight: normal; position: absolute; margin-top: 5px;">Note:Two Way Knockout Support</span></h6>
                    </div>
                    <div id="binding" style="float: left; width: 23%">
                        <input id="colorpick1" data-bind="ejColorPicker: { value: value, modelType: picker }" />
                    </div>
                </div>
            </div>
        </div>
    </div>
    <script>
    window.viewModel = {
        value: ko.observable("#278787"),
        palette: ko.observable("palette"),
        picker: ko.observable("picker")
    };
    $(function () {
        ko.applyBindings(viewModel);
    });
    </script>
    <style>
        .element {
            display: inline-block;
        }

        .frame {
            width: 600px;
            border: 0px;
        }

        #control {
            width: 600px;
        }
    </style>

{% endhighlight %}



The following screenshot displays the output of the above code.

![](Integration_images/Integration_img2.png)





