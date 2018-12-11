---
layout: post
title: Getting Started | BulletGraph | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: BulletGraph	
documentation: ug
---

# Getting Started

This section explains briefly about how to create a BulletGraph in your ASP.NET application.

## Create your first BulletGraph in ASP.NET

This section encompasses the details on how to configure the BulletGraph control in your application. It also allows you to learn how to pass the required data to it and customize its various options according to your requirements.

In the following screenshot, a BulletGraph is used to compare the actual monsoon rainfall received in a state versus its forecasted values for the years ranging from 1988 to 2013.



![](Getting-Started_images/Getting-Started_img1.png) 


1. First create an ASP Project and adding necessary Dll’s and Scripts with the help of the given ASP-Getting Started Documentation.
2. Configure web.config files for assemblies

   * The following assemblies references are added properly in web.config file.  

   ~~~ html	
	
		<compilation debug="true" targetFramework="4.5">
		
			<assemblies>
			
				<add assembly="Syncfusion.EJ.Web, Version=12.2450.0.36, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89"/>
				
				<add assembly="Syncfusion.EJ, Version=12.2450.0.36, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89"/>
				
			</assemblies>
			
		</compilation>	
		
		<httpRuntime targetFramework="4.5" />
		
		<pages> 
		
			<controls>
			
				<add namespace="Syncfusion.JavaScript.Web" assembly="Syncfusion.EJ.Web, Version=12.2450.0.36, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" tagPrefix="ej"/>
				
				<add namespace="Syncfusion.JavaScript.Web" assembly="Syncfusion.EJ, Version=12.2450.0.36, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" tagPrefix="ej"/>
				
				<add  namespace="Syncfusion.JavaScript.DataVisualization.Models" assembly="Syncfusion.EJ" tagPrefix="ej"/>
				
			</controls>
			
		</pages>	
		
   ~~~

3. Adding Script Reference,
    
By default, Syncfusion JavaScript source files has been included into the EJ.Web assembly as an embedded source. So we no need to refer jQuery and Syncfusion scripts externally. For debugging purpose want to refer script files externally, set false to **LoadEJResourcesFromAssembly** in Web.config file as shows in the below image and refer jQuery and Syncfusion script files.

![](Getting-Started_images/Getting-Started_img8.png)

{% highlight html %}


    <!--  jquery script  -->
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"></script>

    <!-- Essential JS UI widget -->
    <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>

{% endhighlight %}

N> If you are using the Essential Studio below 13.4.0.53 version, then you need to refer **jQuery.globalize.js** script file along with the above references to render the bullet graph control.

4. Create simple BulletGraph.

   ~~~ html

        <ej:Bulletgraph ID="BulletGraph1" runat="server">

        </ej:Bulletgraph>
	
   ~~~
   

5. Execute the above code to display the BulletGraph. To customize the measure bars in the BulletGraph, you can pass the data either locally or remotely.

   ![](Getting-Started_images/Getting-Started_img2.png)



### Provide Required Data

You can customize the values of feature and comparative measure bars in a BulletGraph, either locally or remotely. The category data is optional, and it is used to display label values parallel to the measure bars. 

Assign the data in BulletLocalDataBind variable to the DataSource property of BulletGraph as illustrated in the following code example. 


{% highlight c# %}

List<BulletLocalDataBind> data = new List<BulletLocalDataBind>();

            data.Add(new BulletLocalDataBind { category = "1988", value = "95", comparativeMeasureValue = "85" });

            data.Add(new BulletLocalDataBind { category = "1989", value = "99", comparativeMeasureValue = "87" });

            data.Add(new BulletLocalDataBind { category = "1990", value = "105", comparativeMeasureValue = "95" });

            data.Add(new BulletLocalDataBind { category = "1991", value = "75", comparativeMeasureValue = "85" });

            data.Add(new BulletLocalDataBind { category = "1992", value = "85", comparativeMeasureValue = "95" });

            data.Add(new BulletLocalDataBind { category = "1993", value = "90", comparativeMeasureValue = "86" });

            data.Add(new BulletLocalDataBind { category = "1994", value = "110", comparativeMeasureValue = "76" });

            data.Add(new BulletLocalDataBind { category = "1995", value = "101", comparativeMeasureValue = "66" });

            data.Add(new BulletLocalDataBind { category = "1996", value = "82", comparativeMeasureValue = "76" });

            data.Add(new BulletLocalDataBind { category = "1997", value = "87", comparativeMeasureValue = "96" });

            data.Add(new BulletLocalDataBind { category = "1998", value = "96", comparativeMeasureValue = "96" });

            data.Add(new BulletLocalDataBind { category = "1999", value = "100", comparativeMeasureValue = "106" });

            data.Add(new BulletLocalDataBind { category = "2000", value = "112", comparativeMeasureValue = "83" });

            data.Add(new BulletLocalDataBind { category = "2001", value = "97", comparativeMeasureValue = "73" });

            data.Add(new BulletLocalDataBind { category = "2002", value = "90", comparativeMeasureValue = "85" });

            data.Add(new BulletLocalDataBind { category = "2003", value = "80", comparativeMeasureValue = "65" });

            data.Add(new BulletLocalDataBind { category = "2004", value = "75", comparativeMeasureValue = "82" });

            data.Add(new BulletLocalDataBind { category = "2005", value = "85", comparativeMeasureValue = "54" });

            data.Add(new BulletLocalDataBind { category = "2006", value = "95", comparativeMeasureValue = "64" });

            data.Add(new BulletLocalDataBind { category = "2007", value = "97", comparativeMeasureValue = "87" });

            data.Add(new BulletLocalDataBind { category = "2008", value = "103", comparativeMeasureValue = "72" });

            data.Add(new BulletLocalDataBind { category = "2009", value = "108", comparativeMeasureValue = "94" });

            data.Add(new BulletLocalDataBind { category = "2010", value = "93", comparativeMeasureValue = "100" });

            data.Add(new BulletLocalDataBind { category = "2011", value = "75", comparativeMeasureValue = "60" });

            data.Add(new BulletLocalDataBind { category = "2012", value = "115", comparativeMeasureValue = "79" });

            data.Add(new BulletLocalDataBind { category = "2013", value = "109", comparativeMeasureValue = "90" });

            this.BulletGraph1.DataSource = data;

            this.BulletGraph1.DataBind();


{% endhighlight %}
Once the DataSource property is assigned with the required values, you can bind the variable names used in the JSON data to the corresponding fields of the BulletGraph as shown in the following code example.

{% highlight html %}


<ej:Bulletgraph ID="BulletGraph1" runat="server" Height="540" Width="850" QualitativeRangeSize="800"  QuantitativeScaleLength="425"  >

<Fields CategoryField="category" ComparativeMeasureField="comparitiveMeasureValue" FeatureMeasureField="value" />

</ej:Bulletgraph>

{% endhighlight  %}

### Set Default and Scale Values

You can plot any number of measure bars within the BulletGraph by increasing the height and width of the control to locate all the measure bars within the graph. Set the QualitativeRangeSize and QuantitativeScaleLength properties according to the following code example.

By default, the BulletGraph is rendered in the horizontal orientation with its flow direction set to Forward. In this example, to achieve the desired output, change the horizontal orientation to vertical orientation with the flow direction set to Backward.

Minimum, Maximum and Interval values for the QuantitativeScale of the BulletGraph are set, as illustrated in the following code example. The ticks and labels within the scale are also positioned.


{% highlight html %}


<ej:Bulletgraph ID="BulletGraph1" runat="server" Height="540" Width="850" QualitativeRangeSize="800"  QuantitativeScaleLength="425" Orientation="Vertical" FlowDirection="Backward" >

<TooltipSettings Visible="true" Template="Tooltip"   />

<QuantitativeScaleSettings Minimum="50" Maximum="130" Interval="10" TickPosition="Above" MinorTicksPerInterval="4">

<LabelSettings Position="Above"></LabelSettings>

<MinorTickSettings Width="1" Size="7" />

<MajorTickSettings Size="10" Width="1" />

</QuantitativeScaleSettings>

<Fields CategoryField="category" ComparativeMeasureField="comparitiveMeasureValue" FeatureMeasureField="value" />

</ej:Bulletgraph>

{% endhighlight %}

![](Getting-Started_images/Getting-Started_img3.png)



The above image illustrates the BulletGraph without any ranges displayed in the background.

### Add Qualitative Ranges

By default, 3 ranges are displayed in the BulletGraph control during the initial rendering of the control with its default values. To customize it, you can set appropriate values for the RangeEnd and RangeStroke properties.  Any number of QualitativeRanges can be added to the control.

{% highlight html %}


<ej:Bulletgraph ID="BulletGraph1" runat="server" Height="540" Width="850" QualitativeRangeSize="800"  QuantitativeScaleLength="425" Orientation="Vertical" FlowDirection="Backward" >

<TooltipSettings Visible="true" Template="Tooltip"   />

<QuantitativeScaleSettings Minimum="50" Maximum="130" Interval="10" TickPosition="Above" MinorTicksPerInterval="4">

<LabelSettings Position="Above"></LabelSettings>

<MinorTickSettings Width="1" Size="7" />

<MajorTickSettings Size="10" Width="1" />

</QuantitativeScaleSettings>

<Fields CategoryField="category" ComparativeMeasureField="comparitiveMeasureValue" FeatureMeasureField="value" />

<QualitativeRanges>

<ej:QualitativeRanges RangeEnd="90" />

<ej:QualitativeRanges RangeEnd="110" />

<ej:QualitativeRanges RangeEnd="130" RangeStroke="lightgray" />



</QualitativeRanges>

<CaptionSettings Text="Monsoon Rainfall - Actual vs Forecast" TextAngle="90" Location-X="470" Location-Y="270" Font-FontFamily="Segoe UI" Font-FontStyle="normal" Font-Size="20px" Font-FontWeight="Normal" Font-Opacity="1">

<SubTitle Text= "Rainfall (mm)" Location-X="180" Location-Y="4" Font-FontColor="null" Font-FontFamily="Segoe UI" Font-FontStyle="normal" Font-Size="14px" Font-FontWeight="Normal" Font-Opacity="1" />

</CaptionSettings>

</ej:Bulletgraph>

{% endhighlight  %}

After adding QualitativeRanges to the BulletGraph, the control appears as follows.



![](Getting-Started_images/Getting-Started_img4.png) 



### Ticks and Measure Bars Customization

You can do the following code changes in the quantitative scale to customize the tick size, the color of the feature bar and the comparative measure symbols.
{% highlight html %}

<ej:Bulletgraph ID="BulletGraph1" runat="server" Height="540" Width="850" QualitativeRangeSize="800"  QuantitativeScaleLength="425" Orientation="Vertical" FlowDirection="Backward" >

<TooltipSettings Visible="true" Template="Tooltip"   />

<QuantitativeScaleSettings Minimum="50" Maximum="130" Interval="10" TickPosition="Above" MinorTicksPerInterval="4">

<LabelSettings Position="Above"></LabelSettings>

<MinorTickSettings Width="1" Size="7" />

<MajorTickSettings Size="10" Width="1" />

<ComparativeMeasureSettings Stroke="gray" />

<FeaturedMeasureSettings Stroke="cadetblue" />

</QuantitativeScaleSettings>

<Fields CategoryField="category" ComparativeMeasureField="comparitiveMeasureValue" FeatureMeasureField="value" />

<QualitativeRanges>

<ej:QualitativeRanges RangeEnd="90" />

<ej:QualitativeRanges RangeEnd="110" />

<ej:QualitativeRanges RangeEnd="130" RangeStroke="lightgray" />

</QualitativeRanges>

<CaptionSettings Text="Monsoon Rainfall - Actual vs Forecast" TextAngle="90" Location-X="470" Location-Y="270" Font-FontFamily="Segoe UI" Font-FontStyle="normal" Font-Size="20px" Font-FontWeight="Normal" Font-Opacity="1">

<SubTitle Text= "Rainfall (mm)" Location-X="180" Location-Y="4" Font-FontColor="null" Font-FontFamily="Segoe UI" Font-FontStyle="normal" Font-Size="14px" Font-FontWeight="Normal" Font-Opacity="1" />

</CaptionSettings>

</ej:Bulletgraph>

{% endhighlight  %}

When you customize the ticks and measure bar, the BulletGraph appears as follows.


![](Getting-Started_images/Getting-Started_img5.png)



### Add Caption and Subtitle

You can add the following code example to display an appropriate Caption and Subtitle to the BulletGraph.


{% highlight html %}

<ej:Bulletgraph ID="BulletGraph1" runat="server" Height="540" Width="850" QualitativeRangeSize="800"  QuantitativeScaleLength="425" Orientation="Vertical" FlowDirection="Backward" >

<TooltipSettings Visible="true" Template="Tooltip"   />

<QuantitativeScaleSettings Minimum="50" Maximum="130" Interval="10" TickPosition="Above">

<LabelSettings Position="Above"></LabelSettings>

<MinorTickSettings Width="1" />

<MajorTickSettings Size="7" Width="1" />

<ComparativeMeasureSettings Stroke="gray" />

<FeaturedMeasureSettings Stroke="cadetblue" />

</QuantitativeScaleSettings>

<Fields CategoryField="category" ComparativeMeasureField="comparitiveMeasureValue" FeatureMeasureField="value" />

<QualitativeRanges>

<ej:QualitativeRanges RangeEnd="90" />

<ej:QualitativeRanges RangeEnd="110" />

<ej:QualitativeRanges RangeEnd="130" RangeStroke="lightgray" />

</QualitativeRanges>

<CaptionSettings Text="Monsoon Rainfall - Actual vs Forecast" TextAngle="90" Location-X="470" Location-Y="270" Font-FontFamily="Segoe UI" Font-FontStyle="normal" Font-Size="20px" Font-FontWeight="Normal" Font-Opacity="1">

<SubTitle Text= "Rainfall (mm)" Location-X="180" Location-Y="4" Font-FontColor="null" Font-FontFamily="Segoe UI" Font-FontStyle="normal" Font-Size="14px" Font-FontWeight="Normal" Font-Opacity="1" />

</CaptionSettings>

</ej:Bulletgraph>

{% endhighlight %}





The following screenshot displays a BulletGraph with a Caption and Subtitle.

![](Getting-Started_images/Getting-Started_img6.png)



### Show Tooltip

You can use a Tooltip in your application to display the values of forecasted rainfall, actual rainfall received in millimeter and also the appropriate year. The Tooltip Visible property is set to true to enable the Tooltip option. To set the template Tooltip, you can pass the template id to it as illustrated in the following code example.


{% highlight html %}

<ej:Bulletgraph ID="BulletGraph1" runat="server" Height="540" Width="850" QualitativeRangeSize="800"  QuantitativeScaleLength="425" Orientation="Vertical" FlowDirection="Backward" >

<TooltipSettings Visible="true" Template="Tooltip"   />

<QuantitativeScaleSettings Minimum="50" Maximum="130" Interval="10" TickPosition="Above">

<LabelSettings Position="Above"></LabelSettings>

<MinorTickSettings Width="1" />

<MajorTickSettings Size="7" Width="1" />

<ComparativeMeasureSettings Stroke="gray" />

<FeaturedMeasureSettings Stroke="cadetblue" />

</QuantitativeScaleSettings>

<Fields CategoryField="category" ComparativeMeasureField="comparitiveMeasureValue" FeatureMeasureField="value" />

<QualitativeRanges>

<ej:QualitativeRanges RangeEnd="90" />

<ej:QualitativeRanges RangeEnd="110" />

<ej:QualitativeRanges RangeEnd="130" RangeStroke="lightgray" />

</QualitativeRanges>

<CaptionSettings Text="Monsoon Rainfall - Actual vs Forecast" TextAngle="90" Location-X="470" Location-Y="270" Font-FontFamily="Segoe UI" Font-FontStyle="normal" Font-Size="20px" Font-FontWeight="Normal" Font-Opacity="1">

<SubTitle Text= "Rainfall (mm)" Location-X="180" Location-Y="4" Font-FontColor="null" Font-FontFamily="Segoe UI" Font-FontStyle="normal" Font-Size="14px" Font-FontWeight="Normal" Font-Opacity="1" />

</CaptionSettings>

</ej:Bulletgraph>


[Template content]



<divid="Tooltip"style="display:none; width:125px;padding-top: 10px;padding-bottom:10px">



<divalign="center"style="font-weight:bold">

           Rainfall </div>

<table>

<tr><td>Actual</td>

<td>: {{:currentValue}}mm</td></tr>

<tr><td>Forecast</td>

<td>: {{:targetValue}}mm</td></tr>

<tr><td>Year</td>

<td>: {{:category}}</td></tr>

</table>

</div>

{% endhighlight %}

The following screenshot displays a customized BulletGraph.



![](Getting-Started_images/Getting-Started_img7.png)  



