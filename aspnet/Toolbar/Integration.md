---
layout: post
title: Integration | Toolbar | ASP.NET | Syncfusion
description: integration
platform: aspnet
control: Toolbar
documentation: ug
---

# Integration

## AngularJS

The Toolbar is availed with two types of AngularJS support namely, 

* One way binding
* Two way binding 

One way binding refers to the process of applying scope values to all the available properties of the Toolbar, but the changes made in the Toolbar widget does not reflect or get triggered in turn to the scope collection. This kind of binding applies to all the properties of the Toolbar.

Two-way binding supports both the processes – it applies the scope values to the Toolbar properties as well as the changes made in the Toolbar widget is also reflected back and triggered within the AngularJS scope change function.

To know more detail about the AngularJS binding, refer to the following link location,

<http://help.syncfusion.com/js/angularjs>

N> Add the following script files as given in the following example to access the AngularJS binding. They provide JS library for AngularJS binding.
N>
N> _angular-min.js_
N>
N> _ej.widget.angular.min.js_

The following code example explains the way to bind the data to the Toolbar widget through AngularJS support.

Add the following code example into the corresponding ASPX page to render the ToolBar Control

{% highlight html %}

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">

<head runat="server">

    <title>Essential Studio for JavaScript :AngularJS Support for Toolbar</title>

    <link href=" http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />

    <!--scripts-->

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.globalize.min.js"></script>

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js"></script>

    <script src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/ej.web.all.min.js"></script>

   <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>

    <script src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/web/ej.unobtrusive.min.js"> </script>

    <script src="http://cdn.syncfusion.com/ {{site.releaseversion}}/js/ej.widget.angular.min.js"> </script>

</head>

<body>

   <div ng-app="toolApp">

                <div ng-controller="ToolCtrl">

                    <div id="toolbar1" ej-toolbar e-datasource="dataList" e-width="210px"

                        e-fields-id="id" e-fields-spritecssclass="spriteCss">

                    </div>

                </div>

            </div>

</body>

</html>

{% endhighlight %}



{% highlight js %}

<script>

     var list = [

{

    id: "1",

    spriteCss: "tools movetofolder",



}, {

    id: "2",

    spriteCss: "tools categorize",



}, {

    id: "3",

    spriteCss: "tools flag",



}, {

    id: "4",

    spriteCss: "tools forward",



}, {

    id: "5",

    spriteCss: "tools newmail",



},

 {

     id: "6",

     spriteCss: "tools reply",



 },

 {

     id: "7",

     spriteCss: "tools done",



 }

     ];



     angular.module('toolApp', ['ejangular']).controller('ToolCtrl', function ($scope) {

         $scope.dataList = list;

     });

</script>

{% endhighlight %}



{% highlight css %}

<style type="text/css">

     .darktheme .cols-sample-area .e-tooltxt .tools {

        background-image: url('../images/toolbar/maild.png');

    }



    .cols-sample-area .e-tooltxt .tools {

        display: block;

        background-image: url('../images/toolbar/maill.png');

        height: 24px;

        width: 24px;

        background-repeat: no-repeat;

    }



    .e-tooltxt:hover .tools, .darktheme .cols-sample-area .e-tooltxt:hover .tools {

        background-image: url('../images/toolbar/mailh.png');

    }



    .tools.done {

        background-position: -11px -140px;

    }



    .tools.movetofolder {

        background-position: -12px -40px;

    }



    .tools.categorize {

        background-position: -14px -248px;

    }



    .tools.flag {

        background-position: -13px -282px;

    }



    .tools.forward {

        background-position: -14px -314px;

    }



    .tools.newmail {

        background-position: -14px -348px;

    }



    .tools.reply {

        background-position: -14px -388px;

    }

</style>

{% endhighlight %}



The following screenshot displays the output of the above code.



 ![](Integration_images/Integration_img1.png) 
 



### KnockoutJS

KnockoutJS support allows you to bind the HTML elements against any of the available data models.

Two types of KnockoutJS binding is supported,

* One-way binding
* Two-way binding

One way binding refers to the process of applying observable values to all the available properties of the Toolbar, but the changes made in the Toolbar widget is not reflected and triggered in turn to the observable collection. This kind of binding applies to all the properties of the Toolbar.

Two-way binding supports both the processes – it applies the observable values to the Toolbar properties as well as the changes made in the Toolbar widget is also reflected back and triggered within the observable collections. 

For more information about the KnockoutJS binding, refer to the following online documentation in the following link location,

<http://help.syncfusion.com/js/knockoutjs>

N> Add the following script files along with the given code to access the KnockoutJS binding. They provide JS library for KnockoutJS binding.
N>
N> _knockout-min.js_
N>
N> _ej.widget.ko-latest.min.js_

The link for those script files are as follows:

[http://cdn.syncfusion.com/js/assets/external/knockout.min.js](http://cdn.syncfusion.com/js/assets/external/knockout.min.js)

[http://cdn.syncfusion.com/13.1.0.21/js/ej.widget.ko.min.js](http://cdn.syncfusion.com/13.1.0.21/js/ej.widget.ko.min.js)

The following code example explains how to bind data to the Toolbar through the KnockoutJS support. 

Add the following code example into the corresponding ASPX page to render the Toolbar control

{% highlight html %}

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">

<head runat="server">

    <title>Essential Studio for JavaScript :AngularJS Support for Toolbar</title>

    <link href=" http://cdn.syncfusion.com/{{site.releaseversion}}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />

    <!--scripts-->

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.globalize.min.js"></script>

    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js"></script>

    <script src="http://cdn.syncfusion.com/{{site.releaseversion}}/js/web/ej.web.all.min.js"></script>

    <script src="http://cdn.syncfusion.com/js/assets/external/knockout.min.js"> </script>

    <script src="http://cdn.syncfusion.com/{{site.releaseversion}}/js/web/ej.unobtrusive.min.js"> </script>

    <script src="http://cdn.syncfusion.com/{{site.releaseversion}}/js/ej.widget.ko.min.js"> </script>

</head>

<body>

    <div class="frame">

        <div class="control">

            <div id="toolbar1" data-bind="ejToolbar: { dataSource: dataList, fields: { id: 'id', spriteCssClass: 'spriteCss', text: 'text' }, width: width }"></div>

        </div>

    </div>

</body>

</html>

{% endhighlight %}



{% highlight js %}

    <script>

        $(function () {

            var tool = [

        {

            id: "1",

            spriteCss: "editTools cursor",

            text: "Cursor",

        }, {

            id: "2",

            spriteCss: "editTools select",

            text: "Select",

        }, {

            id: "3",

            spriteCss: "editTools move",

            text: "Move",

        }, {

            id: "4",

            spriteCss: "editTools rectselect",

            text: "Rectangle Select",

        }, {

            id: "5",

            spriteCss: "editTools roundselect",

            text: "Round Select",

        }, {

            id: "6",

            spriteCss: "editTools brush",

            text: "Brushes",

        }, {

            id: "7",

            spriteCss: "editTools pen",

            text: "Pen",

        }, {

            id: "8",

            spriteCss: "editTools gradient",

            text: "Gradients",

        }, {

            id: "9",

            spriteCss: "editTools crop",

            text: "Crop",

        }, {

            id: "10",

            spriteCss: "editTools symbols",

            text: "Symbols",

        }



            ];



            window.viewModel = {

                dataList: ko.observableArray(tool),

                width: ko.observable("100%"),

            };

            ko.applyBindings(viewModel);

        });

    </script>

{% endhighlight %}



{% highlight css %}

<style type="text/css" > .darktheme .cols-sample-area .e-tooltxt .editTools {

    background-image: url('../images/toolbar/editToolbar.png');

}



.cols-sample-area .e-tooltxt .editTools {

    display: block;

    background-image: url('../images/toolbar/editToolbarl.png');

    height: 26px;

    width: 26px;

    background-repeat: no-repeat;

}



.e-tooltxt:hover .editTools, .darktheme .cols-sample-area .e-tooltxt:hover .editTools {

    background-image: url('../images/toolbar/editToolbarh.png');

}



.editTools.cursor {

    background-position: -0px -0px;

}



.editTools.select {

    background-position: -0px -36px;

}



.editTools.move {

    background-position: -0px -72px;

}



.editTools.rectselect {

    background-position: -0px -108px;

}



.editTools.roundselect {

    background-position: -0px -144px;

}



.editTools.brush {

    background-position: -0px -180px;

}



.editTools.pen {

    background-position: -0px -216px;

}



.editTools.gradient {

    background-position: -0px -252px;

}



.editTools.crop {

    background-position: -0px -288px;

}



.editTools.symbols {

    background-position: -0px -324px;

}



.frame {

    height: 280px;

    width: 90%;

    border-radius: none;

    margin-left: 80px;

    margin-top: 40px;

    padding: 0;

}



.control {

    margin: 120px 120px 0;

}



</style >

{% endhighlight %}



The following screenshot displays the output of the above code.

![](Integration_images/Integration_img2.png) 










