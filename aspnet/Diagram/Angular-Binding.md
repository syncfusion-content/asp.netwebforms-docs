---
layout: post
title: Angular-Binding
description: angular binding
platform: aspnet
control: Diagram
documentation: ug
---

# Angular Binding

AngularJS is a JavaScript framework added to an ASPX page with a <script> tag. It extends HTML attributes with directives and binds data to HTML with expressions. AngularJS directives allow you to specify custom and reusable HTML tags that moderate the behavior of certain elements. Angularbinding uses directives to plug its action into the page. Directives, all prefaced with ng-, are placed in HTML attributes. To know more about Angular binding refer to: [http://help.syncfusion.com/ug/js/#!documents/angularjs.htm](http://help.syncfusion.com/ug/js/)



Apply the plugin and property assigning the Diagram element through the directive that starts with the letter e-.  The following code illustrates how to bind data to the Diagram component through Angularsupport.



{% highlight html %}

//References to be added for angular support.

    <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.0.1/angular.min.js"></script>

    <script src=" http://cdn.syncfusion.com/js/web/ej.unobtrusive-latest.min.js "></script>

    <script src=" http://cdn.syncfusion.com/js/ej.widget.angular-latest.min.js"></script>



//Initializes diagram.

<div id="diagramCore" 

       ej-diagram e-height="500px" 

       e-width="700px" 

       e-pagesettings-  

       pagebackgroundcolor="pageSettings.pageBackgroundColor"  

       e-pagesettings-pageheight="pageSettings.pageHeight"

       e-pagesettings-pagewidth="pageSettings.pageWidth"</div>



                <div>



//Renders a dropdown box to display a list of colors

 <input ej-dropdownlist e-datasource="pageColor"   

  value="pageSettings.pageBackgroundColor" 

  e-width="100px" />



angular.module('syncApp', ['ejangular'])

        .controller('diagram', 

            function ($scope) {

            $scope.pageSettings = {

                pageBackgroundColor: "Indigo",

                pageWidth: 500,

                pageHeight: 500,

                multiplePage: false

            };

            $scope.pvalue = 400;

            $scope.nodes = [];

            $scope.pageColor = [{ text: "Black" }, 

                                { text: "White"},

                                { text: "Goldenrod" }];

}); 



{% endhighlight %}



![](Angular-Binding_images/Angular-Binding_img1.png)



