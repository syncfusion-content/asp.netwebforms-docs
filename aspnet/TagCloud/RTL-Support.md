---
layout: post
title: RTL Support | TagCloud | ASP.NET | Syncfusion
description: rtl support
platform: aspnet
control: TagCloud
documentation: ug
---

# RTL Support

This feature allows you to change the left-to-right alignment of the TagCloud control to right-to-left (RTL) alignment. This displays the content from right to left in the control. You can achieve this by using the EnableRTL property that is set to false, by default.

## Enabling RTL Support

To enable the right-to-left property in TagCloud, include the following TagCloud control code example in the ASPX page.

{% highlight html %}

<ej:TagCloud ID="tagcloud" runat="server" DataTextField="text" DataUrlField="url" DataFrequencyField="frequency" EnableRTL="true"></ej:TagCloud>

{% endhighlight %}



{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)

{

	this.tagcloud.DataSource = new TagCloudData().GetTagCloudItems();

}

public class TagCloudData

{

	public TagCloudData()

	{



	}

	public TagCloudData(string _text, string _url, int _frequency)

	{

		this.text = _text;

		this.url = _url;

		this.frequency = _frequency;

	}

	public string text

	{

		get;

		set;

	}

	public string url

	{

		get;

		set;

	}

	public int frequency

	{

		get;

		set;

	}

	public List<TagCloudData> GetTagCloudItems()

	{

		List<TagCloudData> data = new List<TagCloudData>();

		data.Add(new TagCloudData("Hindustan Motors", "http://www.zigwheels.com/newcars/Hindustan-Motors", 10));

		data.Add(new TagCloudData("Bentley Continental ", "http://www.zigwheels.com/newcars/Bentley/Continental", 3));

		data.Add(new TagCloudData("BMW 7", "http://www.zigwheels.com/newcars/BMW/7-Series", 4));

		data.Add(new TagCloudData("Bugatti Veyron", "http://www.zigwheels.com/newcars/Bugatti/Veyron", 2));

		data.Add(new TagCloudData("Honda", "http://www.zigwheels.com/newcars/Honda", 3));

		data.Add(new TagCloudData("Chevrolet Beat", "http://www.zigwheels.com/newcars/Chevrolet/Beat", 7));

		return data;

	 }

}





{% endhighlight %}



The following screenshot illustrates the TagCloud control with RTL support.



![](RTL-Support_images/RTL-Support_img1.png) 



