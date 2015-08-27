---
layout: post
title: Integration
description: integration
platform: aspnet
control: TreeView
documentation: ug
---

## Integration

### Angular Binding

AngularJS is a JavaScript framework. It is added to an HTML page with a <script> tag. It extends HTML attributes with directives, and binds data to HTML with expressions. AngularJS directives allow you to specify custom and reusable HTML tags that moderate the behavior of certain elements.

Angular binding uses directives to plug its action into the page. Directives, all prefaced with ng-, are placed in HTML attributes. To know more about Angular binding refer to the following link,

<http://docs.syncfusion.com/js/angularjs>

Apply the plugin and property assigning the TreeView element through the directive that starts with the letter “e-“. The following example depicts how to bind data to the TreeView control through Angular support.

{% highlight html %}

<%-- Add the following scripts in your aspx page for angular support. --%>

<script src="Scripts/angular.min.js"></script>

<script src="Scripts/ej.unobtrusive.min.js"></script>

<script src="Scripts/ej.widget.angular.min.js"></script>

<div ng-app="treeApp">

    <div ng-controller="TreeCtrl">

        <div id="Div1" ej-treeview e-fields-datasource="dataList" e-fields-id="id" e-fields-parentid="pid"

            e-fields-text="name" e-fields-haschild="hasChild" e-fields-expanded="expanded" />

    </div>

</div>

<script>

    var localData = [

                   { id: 1, name: "Favorites", hasChild: true },

                   { id: 2, pid: 1, name: "Desktop" },

                   { id: 3, pid: 1, name: "Downloads" },

                   { id: 4, pid: 1, name: "Recent places" },

                   { id: 5, name: "libraries", hasChild: true },

                   { id: 6, pid: 5, name: "Documents", hasChild: true },

                   { id: 7, pid: 6, name: "My Documents" },

                   { id: 8, pid: 6, name: "Public Documents" },

                   { id: 9, pid: 5, name: "Pictures", hasChild: true },

                   { id: 10, pid: 9, name: "My Pictures" },

                   { id: 11, pid: 9, name: "Public Pictures" },

                   { id: 12, pid: 5, name: "Music", hasChild: true },

                   { id: 13, pid: 9, name: "My Music" },

                   { id: 14, pid: 9, name: "Public Music" },

                   { id: 15, pid: 5, name: "Subversion" },

                   { id: 16, name: "Computer", hasChild: true },

                   { id: 17, pid: 16, name: "Folder(C)" },

                   { id: 18, pid: 16, name: "Folder(D)" },

                   { id: 19, pid: 16, name: "Folder(F)" },



        ];

    angular.module(' treeApp', ['ejangular']).controller('TreeCtrl', function ($scope) {

        $scope.dataList = localData;

    });

</script>

</div> </div> 



{% endhighlight %}



In the above code example, “ng-app” is a directive that is used to declare an element as a root element of the application, allowing behavior to be modified through custom HTML tags and by using the “ng-controller” directive you can get the scope value of TreeView control.



![](Integration_images/Integration_img1.png) 



### Knockout Binding

KnockoutJS is a JavaScript library that allows you to bind HTML elements against any data model.

It uses a Model-View-ViewModel (MVVM) design pattern, where the Model is your stored data, View is the visual representation of that data (UI) and ViewModel acts as the intermediary between the Model and the View. For more information about the Knockout binding, refer to the online documentation in the following link,

<http://docs.syncfusion.com/js/knockoutjs>

When using KO, the view page is simply an HTML document with declarative bindings and you can link it to the ViewModel. ViewModel is nothing but an object, holding a list of items for creating the TreeView control by using Knockout binding.

In Knockout binding by using ko.observableArray, you can hold the data of TreeView and bind it to an array of values by using ko.applyBindings. When you call ko.applyBindings with a specific element, it binds everything under that element.

The following example depicts the way to bind data to the TreeView control through Knockout Support.

{% highlight html %}

<%--To add the following scripts in your aspx page for knockout support--%>   

<script src="Scripts/knockout-min.js"></script>

<script src="Scripts/ej.unobtrusive.min.js"></script>

<script src="Scripts/ej.widget.ko.min.js"></script>

<div style="width: 250px">

    <div id="Div1" data-bind="ejTreeView: { fields: { dataSource: dataSource, id: 'id', text: 'name', hasChild: 'hasChild', expanded: 'expanded', parentId: 'pid' } } ">

    </div>

</div>

<script type="text/javascript">

        $(function () {

            var localData = [

                   { id: 1, name: "Favorites", hasChild: true },

                   { id: 2, pid: 1, name: "Desktop" },

                   { id: 3, pid: 1, name: "Downloads" },

                   { id: 4, pid: 1, name: "Recent places" },

                   { id: 5, name: "libraries", hasChild: true },

                   { id: 6, pid: 5, name: "Documents", hasChild: true },

                   { id: 7, pid: 6, name: "My Documents" },

                   { id: 8, pid: 6, name: "Public Documents" },

                   { id: 9, pid: 5, name: "Pictures", hasChild: true },

                   { id: 10, pid: 9, name: "My Pictures" },

                   { id: 11, pid: 9, name: "Public Pictures" },

                   { id: 12, pid: 5, name: "Music", hasChild: true },

                   { id: 13, pid: 9, name: "My Music" },

                   { id: 14, pid: 9, name: "Public Music" },

                   { id: 15, pid: 5, name: "Subversion" },

                   { id: 16, name: "Computer", hasChild: true },

                   { id: 17, pid: 16, name: "Folder(C)" },

                   { id: 18, pid: 16, name: "Folder(D)" },

                   { id: 19, pid: 16, name: "Folder(F)" },



        ];

            window.employeeView = {

                dataSource: ko.observableArray(localData),

            };

            ko.applyBindings(employeeView);

        });



</script>



{% endhighlight %}



 ![](Integration_images/Integration_img2.png) 

















