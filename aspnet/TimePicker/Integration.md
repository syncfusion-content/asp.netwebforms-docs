---
layout: post
title: Integration | TimePicker | ASP.NET | Syncfusion
description: integration
platform: aspnet
control: TimePicker
documentation: ug
---

# Integration

## AngularJS Support

TimePicker control is availed with two types of AngularJS supports namely, 

* One way binding
* Two way binding 

One way binding refers to the process of applying scope values to all the available properties of the TimePicker control where the changes made in the control are not reflected or triggered in turn to the scope collection. This kind of binding applies to all the properties of the TimePicker control.

Two-way binding supports both the processes – it applies the scope values to the TimePicker properties as well as the changes made in the control are also reflected back and triggered within the AngularJS scope change function.

Apply the plugin property assigning to the TimePicker control element through the directive that starts with a letter “e-“.

To know more details about AngularJS binding, refer to the following link location,

<http://help.syncfusion.com/js/angularjs>

The following code example depicts you the way to bind data to the TimePicker control through AngularJS support.


{% highlight html %}

 <html ng-app="TimeCtrl">
    <head>
        <title>Essential Studio for JavaScript : Timepicker AngularJS</title>
        <meta name="viewport" content="width=device-width, initial-scale=1.0" charset="utf-8" />
        <link href="[http://cdn.syncfusion.com/{{site.releaseversion}} /js/web/flat-azure/ej.web.all.min.css](http://cdn.syncfusion.com/13.1.0.21/js/web/flat-azure/ej.web.all.min.css)" rel="stylesheet" />
        <!--scripts-->
        <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>
        <script src="http://cdn.syncfusion.com/js/assets/external/jquery.globalize.min.js"> </script>
        <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js"> </script>
        <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
        <script src="[http://cdn.syncfusion.com/{{site.releaseversion}} /js/web/ej.web.all.min.js](http://cdn.syncfusion.com/13.1.0.21/js/web/ej.web.all.min.js)"></script>
        <script src="[http://cdn.syncfusion.com/{{site.releaseversion}} /js/web/ej.unobtrusive.min.js](http://cdn.syncfusion.com/13.1.0.21/js/web/ej.unobtrusive.min.js)"></script>
        <script src="[http://cdn.syncfusion.com/{{site.releaseversion}} /js/ej.widget.angular.min.js](http://cdn.syncfusion.com/13.1.0.21/js/ej.widget.angular.min.js)"> </script>
    </head>
    <body ng-controller="TimePickerCtrl">
        <div class="content-container-fluid">
            <div class="row">
                <div class="cols-sample-area">
                    <div class="frame" style="width: 30%; height: 17px;">
                        <div id="control" style="float: left;width: 45%;">
                            <input id="time" type="text" ej-timepicker e-value="timeValue" />
                            <h6><span style="font-style: italic; font-weight: normal; position: absolute; margin-top: 5px;">Note:Two Way AngularJS Support</span></h6>
                        </div>
                        <div id="binding" style=" float right;width 45%;">
                            <input id="timectrl" type="text" ej-timepicker e-value="timeValue" e-interval="10" />
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <script type="text/javascript">
        angular.module('TimeCtrl', ['ejangular'])
               .controller('TimePickerCtrl', function ($scope) {
                   $scope.timeValue = "12:50 AM";
               });
        </script>
        <style type="text/css" class="cssStyles">
            .control {
                margin: 0 auto;
                width: 136px;
            }

            #time_timewidget, #timectrl_timewidget {
                width: 84%;
            }

            #timeValue {
                text-indent: 10px;
            }
        </style>
    </body>
</html>

{% endhighlight %}


Run the above code to render the following output.

![](Integration_images/Integration_img1.png) 



## KnockoutJS Support

KnockoutJS support allows you to bind the ASPX elements against any of the available data model.

Two types of KnockoutJS binding are supported,

* One-way binding
* Two-way binding

One way binding refers to the process of applying observable values to all the available properties of the TimePicker control, where the changes made in the control are not reflected and triggered in turn to the observable collection. This kind of binding applies to all the properties of the TimePicker control.

Two-way binding supports both the processes – it applies the observable values to the TimePicker control properties as well as the changes made in the TimePicker control are also reflected back and triggered within the observable collections. 

For more information about the KnockoutJS binding, refer to the following link location,

<http://help.syncfusion.com/js/knockoutjs>

The following example depicts the way to bind data to the TimePicker control through the KnockoutJS support that enables and populates data to the TimePicker control based on the value set to another TimePicker control.

{% highlight html %}

<html>
<head>
    <title>Essential Studio for JavaScript : Timepicker KnockoutJS</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" charset="utf-8"  />
    <!-- Style sheet for default theme (flat azure) -->
    <link href=" [http://cdn.syncfusion.com/{{site.releaseversion}} /js/web/flat-azure/ej.web.all.min.css](http://cdn.syncfusion.com/13.1.0.21/js/web/flat-azure/ej.web.all.min.css)" rel="stylesheet" />
    <!--scripts-->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.globalize.min.js"> </script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js"> </script>
    <script src="http://cdn.syncfusion.com/js/assets/external/knockout.min.js"></script>    
    <script src="[http://cdn.syncfusion.com/{{site.releaseversion}} /js/web/ej.web.all.min.js](http://cdn.syncfusion.com/13.1.0.21/js/web/ej.web.all.min.js)"></script>
    <script src="[http://cdn.syncfusion.com/{{site.releaseversion}} /js/web/ej.unobtrusive.min.js](http://cdn.syncfusion.com/13.1.0.21/js/web/ej.unobtrusive.min.js)"></script>
    <script src="[http://cdn.syncfusion.com/{{site.releaseversion}} /js/ej.widget.ko.min.js](http://cdn.syncfusion.com/13.1.0.21/js/ej.widget.ko.min.js)"></script>
</head>
    <!--Adds custom scripts here -->
</head>
<body>
    <div class="content-container-fluid">      
            <div class="row">                
                <div class="cols-sample-area">                                  
                    <div class="frame">
                        <div class="control" style="width: 136px;">
                             <label style="width: 130px;">Select Show Time </label>
                             <input id="time" type="text" data-bind="ejTimePicker:{value:timeValue }"/>
                        </div>
                     </div>                    
                </div>
                <div id="sampleProperties">
                   <div class="prop-grid">
                      <div class="row">
                         <div class="col-md-3">Time Value</div>
                         <div class="col-md-3">
                             <input type="text" id="timeValue" class="input ejinputtext" value="" data-bind="value: timeValue" />
                         </div>
                         <div class="col-md-3">Selected time</div>
                         <div class="col-md-3">
                            <input type="button" class="e-btn inputBtn" id="getTime" value="Get Time" />
   				         </div>
                      </div>		
                  </div>
           </div>
       </div>
    </div>
    <script type="text/javascript">
       window.viewModel = {
            //TimePicker
            timeValue: ko.observable("11:30 AM")       
        }
        $(function () {
            // Declaration
            ko.applyBindings(viewModel);
            var timeObj = $('#time').data("ejTimePicker");
            $("#getTime").click(function () {
                alert("Selected time is : " + timeObj.getValue());
            });
            $("#sampleProperties").ejPropertiesPanel();
        });
    </script>
 </body>
</html>

{% endhighlight %}



Run the above code to render the following output.

![](Integration_images/Integration_img2.png) 



