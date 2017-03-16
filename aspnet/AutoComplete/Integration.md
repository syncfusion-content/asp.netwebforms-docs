---
layout: post
title: Integration | AutoComplete | ASP.NET Webforms | Syncfusion
description: integration
platform: aspnet
control: AutoComplete
documentation: ug
---

# Integration

## AngularJS

AutoComplete control is availed with two types of AngularJS support namely, 

* One-way binding
* Two-way binding 

One-way binding refers to the process of applying scope values to all the available properties of the AutoComplete control, but the changes made in AutoComplete control is not reflected or triggered in turn, to the scope collection. This kind of binding applies to all the properties of the AutoComplete control.

Two-way binding supports both the processes. It applies the scope values to the AutoComplete properties, as well as the changes made in the AutoComplete control are reflected back and triggered within the AngularJS scope change function.

Apply the plugin and property assigning to the AutoComplete control element through the directive that starts with “e-“.

To know more about the AngularJS binding, refer to the following online documentation link.

<http://help.syncfusion.com/js/angularjs>

The following example depicts the way to bind data to the AutoComplete control through AngularJS support.

Add the following code example to corresponding ASPX page to render AutoComplete control



{% highlight html %}

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">

<head runat="server">

    <title>Essential Studio for JavaScript :AngularJS Support for Autocomplete</title>

    <link href=" http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />

    <!--scripts-->

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.globalize.min.js"></script>

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js"></script>

    <script src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/ej.web.all.min.js"></script>

    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>

    <script src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/ej.unobtrusive.min.js">     </script>

    <script src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/ej.widget.angular.min.js"> </script>

</head>

<body>

<div ng-app="syncApp">

    <div ng-controller="AutocompleteCtrl">

        <div style="width: 400px">

            <div style="float: left;">

                <input type="text" name="AutoComplete" ej-autocomplete e-datasource="list" e-value="setValue" />

                <h6>

                    <span style="font-style: italic; font-weight: normal; position: absolute; margin-top: 5px;">

                        Note:Two Way AngularJS Support</span>

                </h6>

            </div>

            <div id="binding" style="float: right;">

                <input type="text" name="AutoComplAng" style="height:26px;" class="input ejinputtext" ng-model="setValue" />

            </div>

        </div>

    </div>

</div>





{% endhighlight %}



In the Script section, define the data to be bid and by using AngularJS support, map fields to AutoComplete.



{% highlight js %}

<div ng-app="syncApp">

    <div ng-controller="AutocompleteCtrl">

        <div style="width: 400px">

            <div style="float: left;">

                <input type="text" name="AutoComplete" ej-autocomplete e-datasource="list" e-value="setValue" />

                <h6>

                    <span style="font-style: italic; font-weight: normal; position: absolute; margin-top: 5px;">

                        Note:Two Way AngularJS Support</span>

                </h6>

            </div>

            <div id="binding" style="float: right;">

                <input type="text" name="AutoComplAng" style="height:26px;" class="input ejinputtext" ng-model="setValue" />

            </div>

        </div>

    </div>

</div>

</head>

<body>



{% endhighlight %}



The following screenshot is the output of AutoComplete control with two way AngularJS binding.

![](Integration_images/Integration_img1.png)



## KnockoutJS

Knockout support allows you to bind the HTML elements against any of the available data models.

Two types of KnockoutJS binding is supported,

* One-way binding
* Two-way binding

One-way binding refers to the process of applying observable values to all the available properties of the AutoComplete control, but the changes made in AutoComplete control are not reflected and triggered in turn to the observable collection. This kind of binding applies to all the properties of the AutoComplete control.

Two-way binding supports both the processes. It applies the observable values to the AutoComplete control properties, and also the changes made in the AutoComplete control are reflected back and triggered within the observable collections. 

For more information about KnockoutJS binding, refer to the following online documentation link,

<http://help.syncfusion.com/js/knockoutjs>

The following example depicts how you can bind data to the AutoComplete control through KnockoutJS support that enables and populates data to an AutoComplete control, based on the value set to the other AutoComplete control.

Add the following code example to corresponding ASPX page to render AutoComplete control.

{% highlight html %}

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">

<head runat="server">

    <title>Essential Studio for JavaScript :KnockoutJS Support for Autocomplete</title>

    <link href=" http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />

    <!--scripts-->

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.globalize.min.js"></script>

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js"></script>

    <script src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/ej.web.all.min.js"></script>

    <script src="http://cdn.syncfusion.com/js/assets/external/knockout.min.js"> </script>

    <script src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/ej.unobtrusive.min.js"> </script>

    <script src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/ej.widget.ko.min.js"> </script>

</head>

<body>

 <div style="width: 400px">

    <div style="float: left;">

        <h6>

            <span style="font-style: italic; font-weight: normal; position: absolute; margin-top: -30px;"> Select Country</span>

        </h6>

        <input id="country" data-bind='value: countryName, valueUpdate: ["onchange", "input", "blur"]' />

    </div>

    <div id="binding" style="float: right;">

        <h6>

            <span style="font-style: italic; font-weight: normal; position: absolute; margin-top: -30px;"> Select State</span>

        </h6>

        <input id="state" data-bind='value: stateName' />

    </div>

 </div>

 </head>

<body>



{% endhighlight %}



In the script section, add the code to bind observable values by using Knockout binding as follows.



{% highlight js %}

<script type="text/javascript">

           $(function () {

               var countryList = ["United States", "Australia", "Austria", "India"];

               $('#country').ejAutocomplete({

                   watermarkText: "Select country",

                   showPopupButton: true,

                   dataSource: countryList

               });

               $('#state').ejAutocomplete({

                   showPopupButton: true

               });

               $("#GetValue").click(function () {

                   alert("Current value is : " + autocomplete.getValue());

               });

               var stateObj = $('#state').data("ejAutocomplete");

               stateObj.disable();

               // declaration             

               var ViewModel = function () {

     var usaStates = ["California", "New York", "South Carolina", "Washington"];

     var australiaStates = ["West Island", "Sydney", "Kingston", "Melbourne"];

     var austriaStates = ["Burgenland", "Carinthia", "Styria", "Vienna"];

     var indiaStates = ["Tamil Nadu", "Rajasthan", "West Bengal", "Maharashtra"];

                   this.countryName = ko.observable();

                   this.stateName = ko.computed(function () {

                       var source = null;

                       switch (this.countryName()) {

                           case "United States": source = usaStates; break;

                           case "Australia": source = australiaStates; break;

                           case "Austria": source = austriaStates; break;

                           case "India": source = indiaStates; break;

                       }

                       if (source) {

                           stateObj.enable();

                           stateObj.setModel({ dataSource: source });

                           return source[0];

                       }

                       else stateObj.setModel({ dataSource: null });



                       return "";

                   }, this);

               };

               ko.applyBindings(new ViewModel());

               autocomplete = $('#country').data("ejAutocomplete");

           });

    </script> 



{% endhighlight %}



The following screenshot is the result of the above code examples.

![](Integration_images/Integration_img2.png) 





