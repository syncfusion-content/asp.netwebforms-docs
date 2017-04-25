---
layout: post
title: Helper Functions | DataManager | ASP.NET MVC | Syncfusion
description: helper functions
platform: ejmvc
control: DataManager
documentation: ug
keywords: parseJSON, parseTable, getGuid, merge, serverTimezoneOffset, swap
---

# Helper Functions

**ej.parseJSON**

This method is used to parse the string to **JSON**. 

**ej.parseTable**

This method is used to parse the **HTML** element into the **JSON** Array and is used commonly in element binding using **DataManager**.

**ej.getGuid**

This method returns the globally unique identifier and it generates unique identifier with the prefix provided as parameter.

**ej.merge**

The ej.merge is used to merge two arrays and the result is merged in the first array. 

**ej.support**

The ej.support property contains a collection of properties representing different browser features or bugs. The property are as follows.

1. cors – represents the cross browser support.

2. enableLocalizedSort – enables the localized sort operation.

3. stableSort – enables stable sort operation.

4. outerHTML – represents the outerHTML support.

**ej.swap**

This method is used to swap the position of element in an array. It accepts three arguments such as input array and two swap positions.

**ej.serverTimezoneOffset**

This property is used to set the time-zone offset from UTC, in hours

N> Suppose, application has been hosted in EST time zone and client may be in IST, GMT etc. in that case, date will differ from database. The below given solution will fix the conflict. 

<table>
    <tr> 
        Property <br>
        Name: ej.serverTimezoneOffset 
        Data type: number
        Default Value: 0 
    </tr>
</table>

N> By default, The server time zone will be in UTC, if its other than the UTC, set the proper format time zone offset value to the ej.serverTimezoneOffset property. <BR>
Please refer the online (link)[https://en.wikipedia.org/wiki/Time_zone#List_of_UTC_offsets] for time zone offset values.

<table>
    <tr>
        Time-zone offset calculation from UTC: <br>
        ej.serverTimezoneOffset = serverTimeZoneDiff(in hours) + ClientSideTimeZoneDiff(in hours); 
    </tr>
</table>

{% highlight html %}

    <div class="content-container-fluid">
        <div class="row">
            <div class="cols-sample-area">
                <div id="Grid"></div>
            </div>
        </div>
    </div>
    <script type="text/javascript">
        var serverTimeZoneDiff = -5.0   // if your server is in EST time zone (UTC -5.0) (in hours)
        var clientSideTimeZoneDiff = new Date().getTimezoneOffset() / 60; // get client time zone differents and convert it to hours;
        ej.serverTimezoneOffset = serverTimeZoneDiff + clientSideTimeZoneDiff;
        $(function () {
            var dm = ej.DataManager({ url: "http://mvc.syncfusion.com/services/Northwnd.svc/Orders" });
            $("#Grid").ejGrid({
                dataSource: dm,
                allowPaging: true,
                columns: ["OrderID", "EmployeeID", "CustomerID", "OrderDate", "Freight"]
            });
        });
    </script>

{% endhighlight %}

N> When the Daylight saving time mode is enabled in the sever, take care about this time adjustment with the server time-zone offset calculation.

The countries that are using Eastern Standard Time (EST) when observing standard time (autumn/winter) are 5 hours behind Coordinated Universal Time (UTC−05:00).

Eastern Daylight Time (EDT), when observing daylight saving time DST (spring/summer) is 4 hours behind Coordinated Universal Time (UTC−04:00).

Let see an example, when they observe the Daylight saving time.

{% highlight html %}

    <div class="content-container-fluid">
        <div class="row">
            <div class="cols-sample-area">
                <div id="Grid"></div>
            </div>
        </div>
    </div>
    <script type="text/javascript">
        var serverTimeZoneDiff = -4.0  // if your server is in EDT time zone (UTC -4.0) (in hours)
        var clientSideTimeZoneDiff = new Date().getTimezoneOffset() / 60; // get client time zone differents and convert it to hours;
        ej.serverTimezoneOffset = serverTimeZoneDiff + clientSideTimeZoneDiff;
        $(function () {
            var dm = ej.DataManager({ url: "http://mvc.syncfusion.com/services/Northwnd.svc/Orders" });
            $("#Grid").ejGrid({
                dataSource: dm,
                allowPaging: true,
                columns: ["OrderID", "EmployeeID", "CustomerID", "OrderDate", "Freight"]
            });
        });
    </script>

{% endhighlight %}