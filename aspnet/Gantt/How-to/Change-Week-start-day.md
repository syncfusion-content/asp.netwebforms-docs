---
layout: post
title: Change-Week-start-day | Gantt |  ASP.NET Webforms | Syncfusion
description: Week start day customization
platform: aspnet
control: Gantt
documentation: ug
---

# Change week start day in month timescale mode

## Using start date mode as Month

When setting the `TimescaleStartDateMode` property as month, the project will start from the first date of the same month of the first task in a project. Using below code example we can change the week start day of the project start date in month timescale mode.

{% highlight html %}
<ej:Gantt ID="Gantt" runat="server" Load="load">
     <scheduleheadersettings ScheduleHeaderType="Month" 
	 TimescaleStartDateMode="Month" 
	 MonthHeaderFormat="MMM yyyy" 
	 WeekHeaderFormat="M/dd" 
	 WeekStartDay="1"/>
</ej:Gantt>
<script type="text/javascript">
    function load(args) {         
        this._enableMonthStart = false;
        }
<script>
{% endhighlight %}

![](/js/Gantt/How-to/Change-Weekstart-Day-images/image-1.png)

## Using start date mode as Year

When setting the `TimescaleStartDateMode` property as Year, the project will start from the first date of the same year to which the first task in a project starts. Using below code example we can change the week start day of the project start date in year timescale mode.

{% highlight html %}
<ej:Gantt ID="Gantt" runat="server" Load="load">
     <scheduleheadersettings ScheduleHeaderType="Month" 
	 TimescaleStartDateMode="Year" 	 
	 WeekHeaderFormat="M/dd" 
	 WeekStartDay="1"/>
</ej:Gantt>
<script type="text/javascript">
    function load(args) {         
        this._enableMonthStart = false;
        }
<script>
{% endhighlight %}
![](/js/Gantt/How-to/Change-Weekstart-Day-images/image-2.png)

By default _enableMonthStart property will be true. Week header in month schedule mode will be rendered with month/year start day. To customize the week start day in month mode we need to set _enableMonthStart as false.
