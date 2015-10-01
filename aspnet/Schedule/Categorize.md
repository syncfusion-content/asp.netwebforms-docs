---
layout: post
title: Categorize | Schedule | ASP.NET Webforms | Syncfusion
description: categorize	
platform: aspnet
control: Schedule
documentation: ug
---

# Categorize	

* This feature allows you to differentiate the appointments with various categorize options and individual colors. You can also denote the status of the appointments using this categorize option and can specify your own user-defined category collection.

You can use the following code example to include the categorize option.




{% highlight html %}




<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014">

<CategorizeSettings Enable="true" AllowMultiple="true" Id="id" Color="color" FontColor="fontColor" Text="text">

</CategorizeSettings>

</ej:Schedule>

{% endhighlight %}

### Categorize Settings

* The categorizeSettings is an object collection that holds the categorize related information such as the dataSource. It provides the collection of categorize values that are to be used in appointments, allowMultiple that enables/disables the multiple selection of categorize values and other mapper field names to bind the fields of the dataSource. 

The following are the sub-properties used within the categorizeSettings.

#### enable

* This option accepts either true or false, denoting whether to enable/disable the categorize option.

#### allowMultiple

* This property enables or disables the multiple selection of categories in the appointment window. 

#### dataSource

* It either accepts the local JSON data or remote data for binding the category related information. 

#### text

* It holdsthe binding name for text field in the categorize dataSource.

#### id

* It holds the binding name for id field in the categorize dataSource.

#### color

* It holds the binding name for color field in the categorize dataSource.

#### fontColor

* It holds the binding name for fontcolor field in the categorize dataSource.

The following code example illustrates on how to render categorize feature in the Schedule control.

{% tabs %}

{% highlight html %}

<ej:Schedule runat="server" ID="Schedule1" DataSourceID="SqlData CurrentDate="5/2/2014" CurrentView="Month">

<CategorizeSettings Enable="true" AllowMultiple="true" Id="id" Color="color" FontColor="fontColor" Text="text">

</CategorizeSettings>

<AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" Description="Description" Categorize="Categorize"/>

</ej:Schedule>



</div>

<asp: SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings: ScheduleConnectionString %>"

SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}



{% highlight C# %}




namespace WebSampleBrowser.Schedule

{

public partial class multipleresource : System.Web.UI.Page

{

protected void Page_Load(object sender, EventArgs e)

{



List<Categorize> CategorizeValue = new List<Categorize>();

CategorizeValue.Add(new Categorize { text = "Blue Category", id = 1, color = "#7499e1", fontColor = "Red" });

CategorizeValue.Add(new Categorize { text = "Green Category", id = 2, color = "#7cce6e", fontColor = "White" });

CategorizeValue.Add(new Categorize { text = "Orange Category", id = 3, color = "#ffaa00", fontColor = "Green" });



Schedule1.CategorizeSettings.DataSource = CategorizeValue;

}

public class Categorize

{

public string text { set; get; }

public int id { set; get; }

public string fontColor { set; get; }

public string color { set; get; }

}

}

{% endhighlight %}

{% endtabs %}

The output of the above code is illustrated as follows.

![C:/Users/hariprasanths/Desktop/imagess/123/Capture1.PNG](Categorize_images/Categorize_img1.png)


