---
layout: post
title: AngularJS-Support
description: angularjs support
platform: aspnet
control: TreeMap
documentation: ug
---

# AngularJS Support

AngularJS is a JavaScript framework added to a HTML page with a &lt;script&gt; tag. It extends HTML attributes with directives and binds data to HTML with expressions. AngularJS directives allow you to specify custom and reusable HTML tags that moderate the behavior of certain elements. Angularbinding uses directives to plug its action into the page. Directives, all prefaced with ng-, are placed in HTML attributes. To know more about Angular binding refer to: [http://help.syncfusion.com/ug/js/#!documents/angularjs.htm](http://help.syncfusion.com/ug/js/)



Apply the plugin and property assigning the Treemap element through the directive that starts with the letter “e-“.  The following code illustrates how to bind data to the Treemap  component through Angularsupport.



{% highlight html %}

 &lt;script&gt;



    var population_data = [

 { Continent: "Asia", Country: "Indonesia", Growth: 3, Population: 237641326 },

 { Continent: "Asia", Country: "Russia", Growth: 2, Population: 152518015 },

 { Continent: "Asia", Country: "Malaysia", Growth: 1, Population: 29672000 },

 { Continent: "North America", Country: "United States", Growth: 4, Population: 315645000 },

 { Continent: "North America", Country: "Mexico", Growth: 2, Population: 112336538 },

 { Continent: "North America", Country: "Canada", Growth: 1, Population: 39056064 },

 { Continent: "South America", Country: "Colombia", Growth: 1, Population: 47000000 },

 { Continent: "South America", Country: "Brazil", Growth: 3, Population: 193946886 },

 { Continent: "Africa", Country: "Nigeria", Growth: 2, Population: 170901000 },

 { Continent: "Africa", Country: "Egypt", Growth: 1, Population: 83661000 },

 { Continent: "Europe", Country: "Germany", Growth: 1, Population: 81993000 },

 { Continent: "Europe", Country: "France", Growth: 1, Population: 65605000 },

 { Continent: "Europe", Country: "UK", Growth: 1, Population: 63181775 },

    ];



&lt;/script&gt;







[ASPX.CS]



public partial class AngularTreemap : Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {         



        }

    }   





 [ASP]

[ASPX]

//References to be added for angular support.



    &lt;script src=" https:/ajax.googleapis.com/ajax/libs/angularjs/1.0.1/angular.min.js"&gt;

    &lt;/script&gt;

    &lt;script src=" http://cdn.syncfusion.com/js/ej.widget.angular-latest.min.js"&gt;&lt;/script&gt;

//Initializes controller

&lt;div ng-app="SyncApp"&gt;

//Initializes controller

&lt;div ng-controller="TreeMapcontroller"&gt;



    //Initializes TreeMap

    &lt;div id="treemap" ej-treemap e-datasource="ndatasource" e-uniColorMapping-color="ncolor" e-weightvaluepath="nweightValuePath" e-colorvaluepath="ncolorValuePath" e-leafitemsettings-labelpath="nlabelPath" style="width: 700px;height:370px;"&gt;



                    &lt;e-levels&gt;

                  &lt;e-level e-grouppath="ngroupPath" e-groupgap="ngroupGap"                    e-showheader="nshowHeader"&gt;          

                  &lt;/e-level&gt;

                    &lt;/e-levels&gt;



     &lt;/div&gt; 

    //Renders a checkbox to change the header visibility

    &lt;div&gt;

        Show Header:  &lt;input type="checkbox" ng-model="nshowHeader" style="outline: none;"/&gt;   

   &lt;/div&gt; 

   //Renders a textbox to change the groupGap value

   &lt;div&gt;

        Group Gap:  &lt;input type="text" id="Text11" ng-model="ngroupGap" style="width: 110px" /&gt;

  &lt;/div&gt; 

    &lt;script&gt;

       angular.module('syncApp', ['ejangular'])      



       .controller('TreeMapcontroller', function ($scope) {

$scope.ndatasource = population_data;

$scope.ncolorValuePath = "Growth";

$scope.nweightValuePath = "Growth";

$scope.nlabelPath = "Country";



$scope.ngroupPath = "Continent";

$scope.ngroupGap = 5;

$scope.nshowHeader = true;



$scope.ncolor = "#2380BB";

});

    &lt;/script&gt; 

&lt;/div&gt;

&lt;/div&gt;

[Controller]



public partial class TreeMapController : Controller

    {

     public ActionResult AngularTreeMap()

        {

            return View();

        }

    }


{% endhighlight %}



![](AngularJS-Support_images/AngularJS-Support_img1.png) 
{:.image }








