---
layout: post
title: Paging | TreeGrid | ASP.NET | Syncfusion
description: paging
platform: aspnet
control: TreeGrid
documentation: ug
---

# Paging

The TreeGrid control provides support for displaying records in paginated view. Paging can be enabled in TreeGrid by setting the `AllowPaging` property as `true`.

The below code snippet explains enabling paging in TreeGrid.

{% highlight html %}
 
<ej:TreeGrid ID="TreeGridControlPagerTemplate" AllowPaging="true">            
         //...     
</ej:TreeGrid>

{% endhighlight %}

The output of the TreeGrid with paging enabled is displayed below

![](Paging_images/Paging_img1.png)

## Paging settings

The paging in TreeGrid can be customized by using the `PageSettings` property.

* **PageSize** - Using this property we can limit the number of records to be displayed per page.
* **PageSizeMode** - By setting this property as `Root` we can limit the number of root nodes or the 0th level records to be displayed per page . 
When the `PageSizeMode` property is set as `Root` the number of records to be displayed per page which is defined in the the `PageSize` property will be considered only for the root nodes or the 0th level records.
* **PageCount** - It is used to display the page number to be displayed in the pager.
* **CurrentPage** - This property is used to set the active page to be displayed initially.
* **TotalRecordsCount** - This property is used to limit the total number of records from the data source to be displayed in TreeGrid.
 The following code example explains the properties in pageSettings. 

{% highlight html %}

<ej:TreeGrid ID="TreeGridControlPagingAPI" AllowPaging="true">   
       <PageSettings PageCount="5" PageSize="12" PageSizeMode="All"  CurrentPage="3" TotalRecordsCount="50" /> 
</ej:TreeGrid>

{% endhighlight %}

You can also find the demo for settings in paging [here](http://asp.syncfusion.com/demos/web/treegrid/treegridpagingapi.aspx)

## Pager Template

It is possible to customize the default pager in TreeGrid by using the `PageSettings.Template` property.
The below code snippet explains how to customize the default pager with template

{% highlight html %}
<script type="text/x-jsrender" id="template">
    <div class="e-pagercontainer">
        <div class="e-first e-icon e-mediaback e-firstpagedisabled e-disable" title="Go to first page"></div>
        <div class="e-prev e-icon e-arrowheadleft-2x e-prevpagedisabled e-disable" style="border-right:none" title="Go to previous page"></div>
    </div>
    <div class="e-pagercontainer e-currentPageContainer" style="border-radius:0px">
        <input id="currentPage" class="e-pagercontainer" type="text" style="text-align:center; margin:0px;border:none;width:32px;height:23px" />
    </div>
    <div id="totalPages" class="e-pagercontainer" style="margin-left: 2px;margin-bottom:5px;border: none; ">
        <span></span>
    </div>
    <div class="e-pagercontainer">
        <div class="e-nextpage e-icon e-arrowheadright-2x e-default" title="Go to next page"></div>
        <div class="e-lastpage e-icon e-mediaforward e-default" title="Go to last page"></div>
    </div>
</script> 

{% endhighlight %}

{% highlight css %}
    #currentPage {
        background-color: white;
    }

    .e-currentPageContainer {
        border-bottom: 1px solid #e0e0e0!important;
    }

    .e-pagercontainer .e-icon {
        display: inline-block;
        height: 8px;
    }

    .e-pager .e-pagercontainer {
        margin: 0px;
        margin-left: 6px;
    }
{% endhighlight %}

{% highlight html %}

<ej:TreeGrid ID="TreeGridControlPagerTemplate" AllowPaging="true">            
    <PageSettings Template="#Template" />       
</ej:TreeGrid>

{% endhighlight %}

{% highlight js %}

//Code for navigating to the page 
$("#currentPage").keydown(function(e) {
    var obj = $("#TreeGridContainer").data("ejTreeGrid");
    var val = parseInt($("#currentPage").val());
    if (e.keyCode == 13) {
        if (val > obj.model.pageSettings.totalPages)
            val = obj.model.pageSettings.totalPages;
        if (val <= 0)
            val = 1;
        obj.gotoPage(val);
        return false;
    }
});

{% endhighlight %}

You can also find the demo for TreeGrid with pager template [here](http://asp.syncfusion.com/demos/web/treegrid/treegridpagertemplate.aspx)

The below image displays TreeGrid with paging template.
![](Paging_images/Paging_img2.png)

It is possible to navigate to a specific page with a custom action instead of clicking pager button by using the [`gotoPage`]( /api/js/ejtreegrid#methods:gotopage "gotoPage") method.

The below code snippet explains how to navigate to 3rd page in TreeGrid by using `gotoPage` method

{% highlight js %}
<script>
    var treeObject = $("#TreeGridContainer").data("ejTreeGrid");
        treeObject.gotoPage(3);
</script>
{% endhighlight %}

## Paging - Touch Option

With paging and responsive mode enabled in TreeGrid, it is possible to change the current page using swipe action.

{% highlight html %}

 <ej:TreeGrid ID="TreeGridControlPagerTemplate" AllowPaging="true" IsResponsive="true">       
 </ej:TreeGrid>

{% endhighlight %}