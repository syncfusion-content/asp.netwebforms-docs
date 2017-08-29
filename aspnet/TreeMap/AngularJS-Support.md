---
layout: post
title: AngularJS Support | TreeMap | ASP.NET | Syncfusion
description: angularjs support
platform: aspnet
control: TreeMap
documentation: ug
---

# AngularJS Support

AngularJS is a JavaScript framework added to a HTML page with a &lt;script&gt; tag. It extends HTML attributes with directives and binds data to HTML with expressions. AngularJS directives allow you to specify custom and reusable HTML tags that moderate the behavior of certain elements. Angular binding uses directives to plug its action into the page. Directives, all prefaced with ng-, are placed in HTML attributes. To know more about Angular binding refer to: <http://help.syncfusion.com/js/angularjs>

Apply the plugin and property assigning the Treemap element through the directive that starts with the letter “e-“.  The following code illustrates how to bind data to the Treemap  component through Angular support.

{% tabs %}
{% highlight js %}

 <script>
 
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
	
</script>

{% endhighlight %}

{% highlight c# %}

public partial class AngularTreemap : Page

{

    protected void Page_Load(object sender, EventArgs e)

    {         



    }

}   

{% endhighlight %}

{% highlight html %}

//References to be added for angular support.

    <script src=" https:/ajax.googleapis.com/ajax/libs/angularjs/1.0.1/angular.min.js">

    </script>

    <script src=" http://cdn.syncfusion.com/js/ej.widget.angular-latest.min.js"></script>

//Initializes controller

<div ng-app="SyncApp">

    //Initializes controller

    <div ng-controller="TreeMapController">

        //Initializes TreeMap

        <div id="treemap" ej-treemap e-datasource="nDataSource" e-uniColorMapping-color="nColor" e-weightvaluepath="nWeightValuePath"
             e-colorvaluepath="nColorValuePath" e-leafitemsettings-labelpath="nLabelPath" style="width: 700px;height:370px;">



              <e-levels>

                  <e-level e-grouppath="nGroupPath" e-groupgap="nGroupGap"    e-showheader="nShowHeader">          

                  </e-level>

               </e-levels>



         </div> 

        //Renders a checkbox to change the header visibility

        <div>

            Show Header:  <input type="checkbox" ng-model="nShowHeader" style="outline: none;"/>   

       </div> 

       //Renders a textbox to change the groupGap value

       <div>

            Group Gap:  <input type="text" id="Text11" ng-model="ngroupGap" style="width: 110px" />

      </div> 

        <script>

           angular.module('syncApp', ['ejangular'])      



           .controller('TreeMapController', function ($scope) {

                $scope.nDataSource = population_data;

                $scope.nColorValuePath = "Growth";

                $scope.nWeightValuePath = "Growth";

                $scope.nLabelPath = "Country";



                $scope.nGroupPath = "Continent";

                $scope.nGroupGap = 5;

                $scope.nShowHeader = true;



                $scope.nColor = "#2380BB";

            });

        </script> 

    </div>

</div>

{% endhighlight %}
{% endtabs %}
{% highlight c# %}

public partial class TreeMapController : Controller

{

 public ActionResult AngularTreeMap()

    {

        return View();

    }

}


{% endhighlight %}


![](AngularJS-Support_images/AngularJS-Support_img1.png) 