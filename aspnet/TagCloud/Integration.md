---
layout: post
title: Integration | TagCloud | ASP.NET | Syncfusion
description: integration 
platform: aspnet
control: TagCloud
documentation: ug
---

# Integration 

## AngularJS binding

TagCloud control is availed with two types of AngularJS support namely, 

* One-way binding
* Two-way binding 

One-way binding refers to the process of applying scope values to all the available properties of the TagCloud control, but the changes made in the TagCloud control are not reflected or triggered in turn in the scope collection. This kind of binding applies to all the properties of the TagCloud control.

Two-way binding supports both the processes. It applies the scope values to the TagCloud properties and the changes made in the TagCloud control are also reflected and triggered within the AngularJS scope change function.

Apply the plugin and property assigning to the TagCloud control element through the directive that starts with a letter “e-“.

To know more detail about the AngularJS binding, refer to the following link location,

<http://help.syncfusion.com/js/angularjs>

The following example shows the way to bind data to the TagCloud control by using AngularJS support.

{% highlight html %}

<!doctype html>

<html lang="en" ng-app="tagApp">

<head>

    <title>Essential Studio for JavaScript : AngularJS Support for Tagcloud </title>

    <meta name="viewport" content="width=device-width, initial-scale=1.0" charset="utf-8" />

   <link href="[http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/flat-lime/ej.web.all.min.css](http://cdn.syncfusion.com/13.1.0.21/js/web/flat-lime/ej.web.all.min.css)" rel="stylesheet" />

    <!--scripts-->

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.globalize.min.js"> </script>

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js"> </script>

     <script src="[http://cdn.syncfusion.com/js/assets/external/angular.min.js](http://cdn.syncfusion.com/js/assets/external/angular.min.js)">  </script>          

     <script src="[http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/ej.web.all.min.js](http://cdn.syncfusion.com/13.1.0.21/js/web/ej.web.all.min.js)"> </script>

    <script src="[http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/ej.unobtrusive.min.js](http://cdn.syncfusion.com/13.1.0.21/js/web/ej.unobtrusive.min.js)"></script>    

    <script src="[http://cdn.syncfusion.com/ {{site.releaseversion}}/js/ej.widget.angular.min.js](http://cdn.syncfusion.com/13.1.0.21/js/ej.widget.angular.min.js)"></script>

</head>

<body ng-controller="TagCtrl">

    <div id="techweblist" ej-tagcloud e-datasource="dataList" e-title="popular sites" />

    <script>

    var list = [

        { text: "Google", url: "http://www.google.co.in", frequency: 12 },

        { text: "a2zwebhelp", url: "http://www.a2zwebhelp.com", frequency: 3 },

        { text: "Arts Technica", url: "http://arstechnica.com/", frequency: 8 },

        { text: "BxSlider", url: "http://bxslider.com/examples", frequency: 2 },

        { text: "Yahoo", url: "http://in.yahoo.com/", frequency: 12 },

        { text: "Facebook", url: "https://www.facebook.com/", frequency: 5 },

        { text: "BlogSpot", url: "http://www.blogspot.com/", frequency: 8 },

        { text: "Microsoft", url: "http://www.microsoft.com/", frequency: 20 },

        { text: "Amazon.com", url: "http://www.amazon.com/", frequency: 1 },

        { text: "MSN", url: "http://www.msn.com/", frequency: 3 },

        { text: "Engadget", url: "http://www.engadget.com/", frequency: 5 },

        { text: "LinkedIn", url: "http://www.linkedIn.com/", frequency: 9 },

        { text: "Twitter", url: "http://www.Twitter.com/", frequency: 0 },

        { text: "MenuCool", url: "http://www.menucool.com", frequency: 3 },

        { text: "BBC", url: "http://www.bbc.co.uk/", frequency: 11 },

        { text: "ValleyWag", url: "http://valleywag.gawker.com/", frequency: 6 },

        { text: "WOWSlider", url: "http://wowslider.com", frequency: 9 },

        { text: "W3Schools", url: "http://www.w3schools.com/", frequency: 2 }

    ];

        angular.module('tagApp', ['ejangular'])

        .controller('TagCtrl', function ($scope) {

            $scope.dataList = list;

        });

    </script>

</body>

</html>

{% endhighlight %}



The following screenshot illustrates the TagCloud control with AngularJS data binding.

![](Integration_images/Integration_img1.png) 



## KnockoutJS binding

Two types of KnockoutJS binding are supported by TagCloud,

* One-way binding
* Two-way binding

One-way binding refers to the process of applying observable values to all the available properties of the TagCloud control, but the changes made are not reflected and triggered in turn to the observable collection. This kind of binding applies to all the properties of the TagCloud control.

Two-way binding supports both the processes. It applies the observable values to the TagCloud control properties and the changes made in the TagCloud control are also reflected back and triggered within the observable collections. 

For more information about the KnockoutJS binding, refer to the following link location,

<http://help.syncfusion.com/js/knockoutjs>

The following code example shows the way to bind data to the TagCloud control by using KnockoutJS support.

{% highlight html %}

<!doctype html>

<html>

<head>

    <title>Essential Studio for JavaScript :  KO Support for Tagcloud</title>

    <meta name="viewport" content="width=device-width, initial-scale=1.0" charset="utf-8"  />

    <link href="[http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/flat-lime/ej.web.all.min.css](http://cdn.syncfusion.com/13.1.0.21/js/web/flat-lime/ej.web.all.min.css)" rel="stylesheet" />

    <!--scripts-->

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>



    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.globalize.min.js"></script>



    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js"> </script>

    <script src="[http://cdn.syncfusion.com/js/assets/external/knockout.min.js](http://cdn.syncfusion.com/js/assets/external/knockout.min.js)"></script>

    <script src="[http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/ej.web.all.min.js](http://cdn.syncfusion.com/13.1.0.21/js/web/ej.web.all.min.js)"></script>

    <script src="[http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/ej.unobtrusive.min.js](http://cdn.syncfusion.com/13.1.0.21/js/web/ej.unobtrusive.min.js)"></script>

    <script src="[http://cdn.syncfusion.com/ {{site.releaseversion}}/js/ej.widget.ko.min.js](http://cdn.syncfusion.com/13.1.0.21/js/ej.widget.ko.min.js)"></script>



</head>

<body>

    <div class="content-container-fluid">

        <div class="row">

            <div id="techweblist" data-bind="ejTagCloud: { dataSource: dataList, titleText: title }">

            </div>

        </div>

    </div>

    <script>

	 $(function () { 

     var view = [

        { text: "Google", url: "http://www.google.com", frequency: 12 },

        { text: "a2zwebhelp", url: "http://www.a2zwebhelp.com", frequency: 3 },

        { text: "Arts Technica", url: "http://arstechnica.com/", frequency: 8 },

        { text: "BxSlider", url: "http://bxslider.com/examples", frequency: 2 },

        { text: "Yahoo", url: "http://in.yahoo.com/", frequency: 12 },

        { text: "Facebook", url: "https://www.facebook.com/", frequency: 5 },

        { text: "Crave", url: "http://news.cnet.com/crave/", frequency: 8 },

        { text: "Wikipedia", url: "http://www.wikipedia.org/", frequency: 20 },

        { text: "Amazon.com", url: "http://www.amazon.com/", frequency: 1 },

        { text: "Electronista", url: "http://www.electronista.com/", frequency: 3 },

        { text: "Engadget", url: "http://www.engadget.com/", frequency: 5 },

        { text: "LinkedIn", url: "http://www.linkedIn.com/", frequency: 9 },

        { text: "Information Week",url:"http://www.informationweek.com/",frequency:0 },

        { text: "MenuCool", url: "http://www.menucool.com", frequency: 11 },

        { text: "Tech Republic", url: "http://techrepublic.com/", frequency: 3 },

        { text: "ValleyWag", url: "http://valleywag.gawker.com/", frequency: 6 },

        { text: "WOWSlider", url: "http://wowslider.com", frequency: 9 },

        { text: "W3Schools", url: "http://www.w3schools.com/", frequency: 2 }

     ];	

			window.viewModel = { 

                dataList: ko.observableArray(view),

                title: ko.observable("Popular Sites"),

            };	        		

            ko.applyBindings(viewModel);

         });



    </script>

</body>

</html>

{% endhighlight %}



Run the above code to render the following output.

![](Integration_images/Integration_img2.png) 





