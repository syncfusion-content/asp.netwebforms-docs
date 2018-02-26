---
layout: post
title: Getting Started | TagCloud | ASP.NET | Syncfusion
description: getting started
platform: aspnet
control: TagCloud
documentation: ug
---

# Getting Started

Essential Studio ASP.NET TagCloud has built-in features such as clicking on one of the sites in the TagCloud brings all relevant results only from the selected source. You can easily create the TagCloud control element as follows.

You can create a WEB Project and add the required assemblies, scripts, and styles to it.  Refer to the [ASP-Getting Started.](http://help.syncfusion.com/aspnetmvc/captcha/getting-started#create-your-first-captcha-in-aspnet-mvc)

Create an ASPX file and add the following code to the file.



{% highlight html %}

<ej:TagCloud ID="Events" Title="Tech Sites" runat="server" DataTextField="text"

        DataUrlField="url" DataFrequencyField="frequency"></ej:TagCloud>

{% endhighlight %}



Add the following code in code behind to bind the DataSource with the TagCloud control.


{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)
{

   this.TagEvents.DataSource = new TagCloudData().GetTagCloudItems().ToList();

}

public class TagCloudData
{

	public string text { get; set; }

	public string url { get; set; }

	public int frequency { get; set; }



	public List<TagCloudData> GetTagCloudItems()
	{

		List<TagCloudData> sites = new List<TagCloudData>() ;

		sites.Add(new TagCloudData { text = "Yahoo!", url = "http://search.yahoo.com/", frequency = 20 });

		sites.Add(new TagCloudData { text = "DuckDuckGo", url = "https://duckduckgo.com/", frequency = 5 });

		sites.Add(new TagCloudData { text = "Bing", url = "http://www.bing.com/", frequency = 23 });

		sites.Add(new TagCloudData { text = "Blekko", url = "http://blekko.com/", frequency = 4 });

		sites.Add(new TagCloudData { text = "AlHea", url = "http://www.alhea.com/", frequency = 3 });

		sites.Add(new TagCloudData { text = "MyWebSearch", url = "http://home.mywebsearch.com/index.jhtml", frequency = 10 });

		sites.Add(new TagCloudData { text = "InfoSpace", url = "http://infospace.com/", frequency = 8 });

		sites.Add(new TagCloudData { text = "Google", url = "https://www.google.co.in/", frequency = 24 });

		sites.Add(new TagCloudData { text = "DogPile", url = "http://www.dogpile.com/", frequency = 4 });



		sites.Add(new TagCloudData { text = "Wow", url = "http://www.wow.com/", frequency = 14 });

		sites.Add(new TagCloudData { text = "Info", url = "http://www.info.com/", frequency = 6 });

		sites.Add(new TagCloudData { text = "WebCrawler", url = "http://www.webcrawler.com/", frequency = 12 });

		sites.Add(new TagCloudData { text = "ContenKO", url = "http://www.contenko.com/", frequency = 3 });

		sites.Add(new TagCloudData { text = "AOL Search", url = "http://search.aol.com", frequency = 16 });



		return sites;

	}    

}

{% endhighlight %}

The following screenshot displays the output of the above code example.

![](Getting-Started_images/Getting-Started_img1.png) 



## Set Min and Max Font Sizes

In the above code example, the Frequency properties are used to set the min and max font sizes to the TagCloud list item.

{% highlight c# %}



public List<TagCloudData> GetTagCloudItems()
{

	List<TagCloudData> sites = new List<TagCloudData>() ;

	sites.Add(new TagCloudData { text = "Yahoo!", url = "http://search.yahoo.com/", frequency = 20 });

	sites.Add(new TagCloudData { text = "DuckDuckGo", url = "https://duckduckgo.com/", frequency = 5 });

    //Uses the list values given above

}

{% endhighlight %}

In the above code, the min font size is 5 and max font size is 20.

## Set event to perform an operation

Here, you can set the TagCloud server side click event.

Add the above mentioned DataSource binding codes.

{% highlight html %}

<ej:TagCloud ID="TagEvents" Title="Tech Sites" runat="server" DataTextField="text"

        DataUrlField="url" DataFrequencyField="frequency" OnClick="TagEvents_Click">

    </ej:TagCloud>

    <label id="EventLog" runat="server">

    </label>

{% endhighlight %}



{% highlight c# %}

protected void TagEvents_Click(object sender, Syncfusion.JavaScript.Web.TagCloudEventArgs e)
{

	this.EventLog.InnerHtml += "\n" + "TagCloud Item " + e.Value + "has been clicked< \r\n";

}

{% endhighlight %}


In the code example, the Event log is used to illustrate the events that occurred.

