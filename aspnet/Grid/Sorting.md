---
layout: post
title: Sorting
description: sorting
platform: aspnet
control: Grid
documentation: ug
---

# Sorting

## Default Sorting

Sorting is a basic technique in Grid. It helps you view Grid records in ascending or descending, based on a particular column. If you want to enable sorting in Grid then use AllowSorting property at Grid initialize. By default, sorting operation can be performed by user interaction (UI) on Grid header.
{% highlight html %}
[ASP]



[aspx]



&lt;ej:Grid ID="FlatGrid" runat="server" AllowSorting="True" AllowPaging="True"&gt;

          &lt;DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" &gt;&lt;/DataManager&gt;   

&lt;/ej:Grid&gt;


{% endhighlight  %}




The following output is displayed as a result of the above code example.



![](Sorting_images/Sorting_img1.png)
{:.image }


> _Note: Grid also has support to sort more than one column. This behavior is called as multi sorting. To enable this behavior in Grid then use allowMultiSorting in Grid._

## External Sorting

In Grid, you have an API to sort a column dynamically. The following code example shows you how to sort a column through API. 
{% highlight html %}
[ASP]



[aspx]

&lt;div&gt;

        &lt;ej:DropDownList runat="server" ID="columns"&gt;

            &lt;Items&gt;

                &lt;ej:DropDownListItem Value="OrderID" Text="Order ID"&gt;&lt;/ej:DropDownListItem&gt;

                &lt;ej:DropDownListItem Value="CustomerID" Text="Customer ID"&gt;&lt;/ej:DropDownListItem&gt;

                &lt;ej:DropDownListItem Value="EmployeeID" Text="Employee ID"&gt;&lt;/ej:DropDownListItem&gt;

                &lt;ej:DropDownListItem Value="ShipCity" Text="Ship City"&gt;&lt;/ej:DropDownListItem&gt;

            &lt;/Items&gt;

        &lt;/ej:DropDownList&gt;

        &lt;br /&gt;

        &lt;ej:DropDownList runat="server" ID="direction"&gt;

            &lt;Items&gt;

                &lt;ej:DropDownListItem Value="Ascending" Text="Ascending"&gt;&lt;/ej:DropDownListItem&gt;

                &lt;ej:DropDownListItem Value="Descending" Text="Descending"&gt;&lt;/ej:DropDownListItem&gt;

            &lt;/Items&gt;

        &lt;/ej:DropDownList&gt;

        &lt;br /&gt;

        &lt;ej:Button Type="button" runat="server" Text="sort" ID="sort" ClientSideOnClick="sort_click" /&gt;

        &lt;br /&gt;

        &lt;ej:Grid ID="FlatGrid" runat="server" AllowSorting="True" AllowPaging="True"&gt;

&lt;DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" &gt;&lt;/DataManager&gt;

&lt;/ej:Grid&gt;



 &lt;/div&gt;
{% endhighlight  %}
{% highlight js %}
[JavaScript]

      &lt;script type="text/javascript"&gt;

        function sort_click(args) {

            $("#FlatGrid").ejGrid("sortColumn", $("#columns").ejDropDownList("getSelectedValue"), ej.sortOrder[$("#direction").ejDropDownList("getSelectedValue")]);

        }

    &lt;/script&gt;



{% endhighlight  %}

The following output is displayed as a result of the above code example.



![](Sorting_images/Sorting_img3.png)
{:.image }


## Multi sorting in Touch device

While using Grid in a touch device environment, you have the option of multi sorting. If you click Grid header it shows a popup to enable or disable single click on Grid header as multi sorting or simple sorting. If you want to enable multi sorting with a single click then click the sorting symbol in popup.

The following output is displayed as a result of the above code example.



![](Sorting_images/Sorting_img4.png)
{:.image }


## Multi sorting key configs

In the normal way of sorting, if you want to sort any column, you can click the header cell of that column. For multi sorting, you need to press ctrl key plus mouse left click.

If you want to clear sorting for a column then you need to use shift plus mouse left click.

## Clear sorting using API

In Grid, you have an API to clear sorted columns. Through this API, you can clear sorting at any stage.
{% highlight html %}
[ASP]

[aspx]



   &lt;div&gt;

     &lt;ej:Button Type="button" ID="clearsorting" runat="server" Text="clear sorting" ClientSideOnClick="clearsorting_click" /&gt;

     &lt;ej:Grid ID="FlatGrid" runat="server" AllowMultiSorting="true" AllowSorting="True" AllowPaging="True"&gt;

&lt;DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"&gt;&lt;/DataManager&gt;

     &lt;/ej:Grid&gt;



    &lt;/div&gt;

[Javascript]

&lt;script&gt;

        function clearsorting_click(args) {

            $("#FlatGrid").ejGrid("clearSorting");

        }

 &lt;/script&gt;




{% endhighlight %}






The following output is displayed as a result of the above code example.



![](Sorting_images/Sorting_img5.png) 
{:.image }




![](Sorting_images/Sorting_img6.png) 
{:.image }


## Merge Sort

In the normal way of sorting, first preference is given to capital letters and then small letters. When you do not want discrimination between small and capital letters, you can set “enableLocalizedSort” API as true to sort both small and capital letters.




{% highlight html %}
[ASP]

[aspx]



   &lt;div&gt;

     &lt;ej:Button Type="button" ID="clearsorting" runat="server" Text="clear sorting" ClientSideOnClick="clearsorting_click" /&gt;

     &lt;ej:Grid ID="FlatGrid" runat="server" AllowMultiSorting="true" AllowSorting="True" AllowPaging="True"&gt;

&lt;DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"&gt;&lt;/DataManager&gt;

     &lt;/ej:Grid&gt;



    &lt;/div&gt;

[Javascript]

&lt;script&gt;

ej.Support.enableLocalizedSort=true

&lt;/script&gt;




{% endhighlight %}


 The following output is displayed as a result of the above code example.



![](Sorting_images/Sorting_img7.png)
{:.image }


