---
layout: post
title: UserInteraction
description: How to enable and cutomize the scrollbar, selection and highlighting in Essential ASP.NET RangeNavigator.
platform: aspnet
control: RangeNavigator
documentation: ug
---

# User Interactions

## Highlight

EjRangeNavigator provides highlighting supports to the intervals on mouse hover. To enable the highlighting option, set the `Enable` property to true in the `HighlightSettings` of `NavigatorStyleSettings`.

{% highlight html %}

  <ej:RangeNavigator ID="RangeNavigator1" runat="server">
        <NavigatorStyleSettings>
            <%--enable the highlight settings--%>
            <HighlightSettings Enable="true"></HighlightSettings>
        </NavigatorStyleSettings>
    </ej:RangeNavigator>

{% endhighlight %}


![](User-Interactions_images/User-Interactions_img1.png) 


[Click](http://asp.syncfusion.com/demos/web/rangenavigator/highlight.aspx) here to view the highlight and selections online demo sample.

### Customize the highlight style

To customize the highlighted intervals, use `Color`, `Border` and `Opacity` options in the `HighlightSettings`.To customize border of highlighted interval, use `Color` and `Width` options in `Border`.

{% highlight html %}

<ej:RangeNavigator ID="RangeNavigator1" runat="server">
        <NavigatorStyleSettings>
            <%--enable the highlight settings--%>
            <HighlightSettings Enable="true" Color="#006fa0">
                <%--customizing style--%>
                <Border Color="red" Width="2" />
            </HighlightSettings>
        </NavigatorStyleSettings>
    </ej:RangeNavigator>

{% endhighlight %}

![](User-Interactions_images/User-Interactions_img2.png)


## Selection

EjRangeNavigator provides selection supports to the intervals by, clicking and dragging the highlighted intervals. To enable the selection option, set the `Enable` property to true in the `SelectionSettings`.

{% highlight html %}

    <ej:RangeNavigator ID="RangeNavigator1" runat="server">
        <NavigatorStyleSettings>
            <%--enable the selection settings--%>
            <SelectionSettings Enable="true" Color="#27e8e5">
              
            </SelectionSettings>
        </NavigatorStyleSettings>
    </ej:RangeNavigator>

{% endhighlight %}


![](User-Interactions_images/User-Interactions_img3.png) 


[Click](http://asp.syncfusion.com/demos/web/rangenavigator/highlight.aspx) here to view the highlight and selections online demo sample.

### Customize the selection style

To customize the selected intervals, use `Color`, `Border` and `Opacity` options in the `SelectionSettings`. To customize border of selected interval, use`Color` and `Width` options in `Border`.

{% highlight html %}

   <ej:RangeNavigator ID="RangeNavigator1" runat="server">
        <NavigatorStyleSettings>
            <%--enable the selection settings--%>
            <SelectionSettings Enable="true" Color="#27e8e5">
                <%--customizing style--%>
                <Border Color="red" Width="2" />
            </SelectionSettings>
        </NavigatorStyleSettings>
    </ej:RangeNavigator>


{% endhighlight %}

![](User-Interactions_images/User-Interactions_img4.png)


## Scrollbar

* To render the Scrollbar in RangeNavigator, you need to enable `EnableScrollbar` option.
 
* `ScrollRangeSettings` of  rangenavigator `Start` and `End` value is used to set the minimum and maximum datasource value to be added in the rangenavigator.
 
* Based on the ScrollRangeSettings *Start, End* value and dataSource *Start, End* value scrollbar will be adjust.

* When you change the scrollbar position, `ScrollEnd` event returns the current position of start and end range value.

{% highlight html %}

     <ej:RangeNavigator ID="RangeNavigator1" runat="server" EnableScrollbar="true" onClientSideScrollEnd="onScrollbarChange">
        <%--Maximum data to be displayed in the rangenavigator control--%>
       <ScrollRangeSettings Start="2010/1/1" End="2011/11/31" />
        <Series>
            <ej:Series>
                <%--Add DataSource to RangeNavigator--%>
                <%--........--%>
            </ej:Series>
        </Series>
    </ej:RangeNavigator>
     
   <script>
         function onScrollbarChange(sender) {
              var start  = sender.data.newRange.start;
              var end  = sender.data.newRange.end;
         }
    </script>
{% endhighlight %}

![](User-Interactions_images/User-Interactions_img5.png)

[Click](http://asp.syncfusion.com/demos/web/rangenavigator/rangescrollbar.aspx) here to view scrollbar online demo sample.