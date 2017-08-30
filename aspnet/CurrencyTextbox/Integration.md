---
layout: post
title: Integration | CurrencyTextBox | ASP.NET Webforms | Syncfusion
description: integration
platform: aspnet
control: Currency TextBox
documentation: ug
---

# Integration

## AngularJS Support

The CurrencyTextbox control supports two types of Angular JS support,

* One-way binding
* Two-way binding

One-way binding refers to the process of applying scope values to all the available properties of the CurrencyTextbox control, but the changes made in the CurrencyTextbox control are not reflected or triggered in turn to the scope collection. This kind of binding applies to all the properties of the CurrencyTextbox control.

Two-way binding supports both the processes. It applies the scope values to the CurrencyTextbox properties and the changes made in the CurrencyTextbox control are reflected back and triggered within the AngularJS scope change function.

Apply the plugin and property assigning to the CurrencyTextbox control element through the directive that starts with the letter “e-“.

To know more details about the Angular binding, refer to the following link:

<http://help.syncfusion.com/js/angularjs>

The following example shows the way to bind data to the CurrencyTextbox control through Angular Support.

{% highlight html %}



<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml" ng-app="TextCtrl">

<head>

    <title></title>

    <link href="Content/bootstrap.min.css" rel="stylesheet" />

    <link href=" http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>

    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>  

    <script src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/ej.web.all.min.js"></script>

    <script src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/ej.unobtrusive.min.js"></script>

    <script src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/ej.widget.angular.min.js"></script>

</head>

<body ng-controller="TextboxCtrl">

    <div id="center">

        <table cellpadding="10">

            <tbody>

                 <tr>



                    <td>



                        <label for="currency">Currency</label>



                    </td>



                    <td>



                        <input id="currency" type="text" ej-currencytextbox e-value="currencyValue" />



                    </td>



                    <td>



                        <input type="text" class="input ejinputtext" ng-model="currencyValue" />



                    </td>



                </tr>

            </tbody>

        </table>

    </div>

    <script type="text/javascript">

        angular.module('TextCtrl', ['ejangular'])

           .controller('TextboxCtrl', function ($scope) {

               $scope.currencyValue = 400;

           });

    </script>

</body>

</html>



{% endhighlight %}



The following is the output of CurrencyTextbox control with two-way AngularJS binding.

![](Integration_images/Integration_img1.jpeg)



![](Integration_images/Integration_img2.jpeg)



## Knockout Support

Knockout support allows you to bind the HTML elements against any of the available data model. It is of two types.

* One-way binding
* Two-way binding

One-way binding refers to the process of applying observable values to all the available properties of the CurrencyTextbox control, but the changes made in CurrencyTextbox control are not reflected and triggered in turn to the observable collection. This kind of binding applies to all the properties of the CurrencyTextbox control.

Two-way binding supports both the processes. It applies the observable values to the CurrencyTextbox control properties and the changes made in the CurrencyTextbox control are reflected back and triggered within the observable collections.

For more information about the Knockout Binding, refer to the following online documentation in the given link location: <http://help.syncfusion.com/js/knockoutjs>.

The following example depicts the way to bind data to the CurrencyTextbox control through Knockout Support that enables and populates data based on the value set to the other CurrencyTextbox controls.

{% highlight html %}

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">

<head>

    <title></title>

    <link href="Content/bootstrap.min.css" rel="stylesheet" />

    <link href=" http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>

    <script src="http://cdn.syncfusion.com/js/assets/external/knockout.min.js"></script>

    <script src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/ej.web.all.min.js"></script>

    <script src=" http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/ej.unobtrusive.min.js "></script>

    <script src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/ej.widget.ko.min.js"></script>

</head>

<body>

    <div id="center">

        <table cellpadding="10">

            <tbody>

               <tr>



                    <td>



                        <label for="currency">Currency</label>



                    </td>



                    <td>



                        <input id="currency" type="text" data-bind="ejCurrencyTextbox: { value: currencyValue }" />



                    </td>



                    <td>



                        <input type="text" class="input ejinputtext" data-bind="value: currencyValue" />



                    </td>



                </tr>



            </tbody>

        </table>

    </div>

    <script type="text/javascript">

        var currencyObject;

        window.viewModel = {

            currencyValue: ko.observable(80)

        }

        jQuery(function ($) {

            ko.applyBindings(viewModel);

            currencyObject = $("#currency").data("ejCurrencyTextbox");



            $(".input").blur(function () {

                var val = parseInt(this.value);

                if (!isNaN(val)) {

                    currencyObject.option(this.id, val);

                }

            });

        });

    </script>

</body>

</html>



{% endhighlight %}



The output of Knockout binding in the CurrencyTextbox.

![](Integration_images/Integration_img3.jpeg)



![](Integration_images/Integration_img4.jpeg)


