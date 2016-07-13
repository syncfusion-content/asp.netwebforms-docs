---
layout: post
title: Integration | Slider | ASP.NET | Syncfusion
description: integration
platform: aspnet
control: Slider
documentation: ug
---

# Integration

## AngularJS binding

AngularJS is structural Framework to create dynamic web apps. It is distributed as a JavaScript file. It extends HTML attributes with Directives, and binds data to HTML with Expressions. To learn more about AngularJS, refer to the following link

<https://angularjs.org/>

Slider control is provided with AngularJS support. The support is achieved by including the ej.widget.angular.min.js file. Refer to the following link to know more about the AngularJS support.

<http://help.syncfusion.com/js/angularjs>

Slider control is defined by using the directive slider. The properties of the Slider control can be included as inline HTML attributes by prefixing the properties with e-. The properties are not case sensitive when defining it. AngularJS provides two types of data binding one way binding and two way binding.

All properties in the Slider supports one way data binding. Here one way binding specifies that the values for the Slider properties are assigned automatically when specified through the data binding notation, but the property values is not changed in the model. That is, the values are displayed only in the HTML view not in the application data.

The Slider properties, value and values are provided with two way binding support. The changes made to these properties are reflected both in the application data (model) and in HTML view.

In an ASPX page, initialize the Slider by using the directive and in JavaScript bind the value and width properties in AngularJS way. 

{% highlight html %}

<div ng-app="syncApp">

    <div ng-controller="SliderCtrl">

        <div class="frame" style="width: 50%">

            <div id="control" style="float: left; width: 45%;">

                <div id="BasicSlider" ej-slider e-width="width" e-value="sliderValue">

                </div>

            </div>

            <div id="binding" style="float: right; width: 45%;">

                <input type="text" name="slider" class="input ejinputtext" ng-model="sliderValue" />

            </div>

        </div>

    </div>

</div>

{% endhighlight %}



Include the following Script to achieve the AngularJS binding.

{% highlight js %}

    angular.module('syncApp', ['ejangular'])

    .controller('SliderCtrl', function ($scope) {

        $scope.sliderValue = 60;

    });

{% endhighlight %}



The following screenshot displays the output of the above code example.

 ![](Integration_images/Integration_img1.png)



## JS binding

KnockoutJS is a JavaScript library that follows the MVVM pattern to build sophisticated user interface with a clean underlying data model. It supports to update the UI dynamically. Refer to the following link to know more about KnockoutJS.

[http://knockoutjs.com/documentation/introduction.html](http://knockoutjs.com/documentation/introduction.html)

Slider control includes support to use it with the KnockoutJS. The support is achieved by integration of the JS library ej.widget.ko.min.js file. Refer to the following link to know more about the KnockoutJS support.

<http://help.syncfusion.com/js/knockoutjs>

The binding handler name for Slider component is Slider. Both one way binding and two way binding support is included. All properties of the Slider component supports one way binding. In the HTML markup, specify the property using the binding handler.

Two way binding support is included only for the applicable Slider properties, value and values. To activate two way binding support, you can specify these properties as observables in the ViewModel. Then, use the ko.applyBindings to activate it. Now these properties bind the underlying data model and the changes are reflected automatically.

The following example explains you the binding of value property by using the KnockoutJS support.

In an ASPX page, initialize the Slider and bind the value property. 

{% highlight html %}

<div class="frame">

        <div id="control" style="float: left; width: 45%;">

            <div id="BasicSlider" data-bind="ejSlider: { value: sliderValue }"></div>           

        </div>

        <div id="binding" style="float: right; width: 45%;">

            <input type="text" name="slider" class="input ejinputtext" value="" data-bind="value: sliderValue" />

        </div>

    </div>

{% endhighlight %}



In JavaScript, specify the value property as observable in the ViewModel to enable the two way binding.

{% highlight js %}

$(function () {

	// declaration           

	window.viewModel = {

		sliderValue: ko.observable(40),

	};

	ko.applyBindings(viewModel);

});

{% endhighlight %}



The following screenshot displays the output of the above code example.

 ![](Integration_images/Integration_img2.png)





