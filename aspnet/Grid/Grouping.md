---
layout: post
title: Grouping | Grid | ASP.NET Webforms | Syncfusion
description: grouping
platform: aspnet
control: Grid
documentation: ug
---

# Grouping

Grouping is an important feature in Grid. If you want to analysis any particular records, based on its category, you can simply group that column and analyse records based on category. There are several flexible options, such as grouped buttons, group close etc. To enable Grouping in Grid, add AllowGrouping at Grid Initialize. 

## Initial Grouping

In Grid, there is an option to group columns at Grid Initialize that is rendered through AllowGrouping and  GroupedColumns property in Grid. This is an important option because in some scenarios, need to analyse Grid records with Grouping may arise, at the time of initialize.



{% highlight html %}



<ej:Grid ID="OrdersGrid" runat="server" AllowGrouping="True">

<DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"></DataManager>

<GroupSettings GroupedColumns="ShipCity"></GroupSettings>

</ej:Grid>


{% endhighlight %}


The following output is displayed as a result of the above code example.



![](Grouping_images/Grouping_img1.png)  



## Group Buttons

Group buttons is one of the features under Grouping. It is helpful to do Grouping easily without doing drag and drop. To enable this feature use ShowToggleButton at Grid Initialize.  


{% highlight html %}


<ej:Grid ID="OrdersGrid" runat="server" AllowGrouping="True">

<DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"></DataManager>



    <GroupSettings ShowToggleButton="True" GroupedColumns="ShipCity">



    </GroupSettings>

</ej:Grid>


{% endhighlight %}
The following output is displayed as a result of the above code example.



![](Grouping_images/Grouping_img2.png)



## Hide Ungroup Button

In GroupDropArea, grouped columns have an option to ungroup a column using GroupButton. It is easier than using Drag and Drop to ungroup columns.  By default this UngroupButton is visible. If you want to hide this button, you can use ShowUngroupButton property to hide columns.



![](Grouping_images/Grouping_img3.png) 




{% highlight html %}


<ej:Grid ID="OrdersGrid" runat="server" AllowGrouping="True" >

<DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"></DataManager>

   <GroupSettings ShowUngroupButton="False" GroupedColumns="ShipCity">

   </GroupSettings>

 </ej:Grid>


{% endhighlight %}


The following output is displayed as a result of the above code example.


![](Grouping_images/Grouping_img4.png) 



## AutoSize Drop Area

If you drag any header to Group column in Grid, it expands smoothly its Group Drop Area portion. In some scenarios, you need to stop this type of animation while grouping. You can use the EnableDropAreaAutoSizing property to stop animation in Group Drop Area.
{% highlight html %}


<ej:Grid ID="OrdersGrid" runat="server" AllowGrouping="True">

<DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"></DataManager>

    <GroupSettings EnableDropAreaAutoSizing="False"></GroupSettings>

</ej:Grid>






{% endhighlight %}
The following output is displayed as a result of the above code example.



![](Grouping_images/Grouping_img5.png)



## Hide Group Drop Area from Grid

In Grid, there is an option to hide the Group Drop Area at Grid Initialize that is achieved through the ShowDropArea property of a GroupSettings in the Grid. The default value is true. By using this property, you can avoid ungrouping or further grouping of a column after the initial column grouping.

When the ShowDropArea property is set to false, the GroupDropArea is hidden. 

{% highlight html %}



<ej:Grid ID="Grid" runat="server" DataSourceID="ObjectData" AllowGrouping="True">

        <GroupSettings EnableDropAreaAutoSizing="False" GroupedColumns="ShipCountry" ShowDropArea="false"></GroupSettings>  



</ej:Grid>



{% endhighlight  %}

The following output is displayed as a result of the above code example.

![C:/Users/NandhiniK/Desktop/Capture.PNG](Grouping_images/Grouping_img6.png)



