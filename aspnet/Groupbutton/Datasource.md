---
layout: post
title: Easy Customization | GroupButton | ASP.NET Webforms | Syncfusion
description: easy customization
platform: aspnet
control: GroupButton
documentation: ug
---

# DataSource

GroupButton can populate the groupbutton items based on datasource and by specifying the associated fields. You can bind data from both remote and local sources.
Refer the below table to know about the available fields

<table>
<tr>
<th>
{{ '**Name**' | markdownify }}</th>
<th>
{{ '**Description**' | markdownify }}</th>
</tr>
<tr>
<td>
DataSource</td><td>
DataSource receives list that are to be added in Groupbutton items. </td></tr>
<tr>
<td>
Query</td>
<td>
It receives query to retrieve data from the table (query is same as SQL). Example:  ej.Query().from("Categories").select("CategoryID,CategoryName").take(4);</td></tr>
<tr>
<td>
DataTextField</td><td>
Specifies the text of Groupbutton items</td></tr>
<tr>
<td>
DataUrlField</td><td>
Specifies the href attribute of “A” Groupbutton items</td></tr>
<tr>
<td>
DataLinkAttributeField</td><td>
Specifies the link attribute to “A” tag in Groupbutton items</td></tr>
<tr>
<td>
DataImageAttributeField</td><td>
Specifies the image attribute to “IMG” tag in Groupbutton items</td></tr>
<tr>
<td>
DataHtmlAttributeField</td><td>
Specifies the HTML attributes to “LI” item list</td></tr>
<tr>
<td>
DataImagePositionField</td><td>
Specifies the position of the prefix icon </td></tr>
<tr>
<td>
DataPrefixIconField</td><td>
Specifies the prefix icon class of GroupButton items </td></tr>
<tr>
<td>
DataSuffixIconField</td><td>
Specifies the suffix icon class of GroupButton items </td></tr>
<tr>
<td>
DataSelectedField</td><td>
Specifies whether the groupbutton item is selected or not </td></tr>
</table>

## Object DataSource
You can populate groupbutton items with local data by using the ObjectDataSource control which returns the Dataset or IEnumerable Object.
Connect to the local ObjectDataSource with DataSourceID property and map the datasource fields to the properties available in the object datasource.

Add the following code to the Aspx page.

{% highlight html %}

<ej:GroupButton runat="server" ID="Grp_btn_ds" ClientIDMode="Static" DataTextField="text" DataSourceID="ObjectDatasource_grp" Size="Large">
</ej:GroupButton>

<asp:ObjectDataSource ID="ObjectDatasource_grp" runat="server" TypeName="SyncfusionASPNETWebApplication1.Models.Datasource" SelectMethod="getDataSource"></asp:ObjectDataSource>

{% endhighlight %}

Define Object DataSource elements with the DataTextField that are to be mapped to GroupButton in code behind and map the list data to DataSource property.

{% highlight c# %}

public class DataItems
{
    public string text {get; set;}
}
public class DataSource
{
    public List<DataItems> GroupButtonItems{get; set;}
    public List<DataItems> getDataSource()
    {
        this.GroupButtonItems = new List<DataItems>();
        this.GroupButtonItems.Add(new DataItems { text = "dataitem1" });
        this.GroupButtonItems.Add(new DataItems { text = "dataitem2" });
        this.GroupButtonItems.Add(new DataItems { text = "dataitem3" });
        return this.GroupButtonItems;
    }
}

{% endhighlight %}

The following screenshot displays the output of above code.

![](Datasource_images/object.png)

### Remote Datasource

The Groupbutton control provides support to bind the items with Remote source. Here the datasource is accessed from a web service in the form of JSON Data in page load event.

In the following code example, [http://mvc.syncfusion.com/Services/Northwnd.svc/](http://mvc.syncfusion.com/Services/Northwnd.svc/) is used as the URL. Here, it acts as web service that is located in the Syncfusion server. The web service used here is Northwnd.svc. 

Add the following code example in your ASPX page.

{% highlight html %}

<ej:GroupButton runat="server" ID="GroupButton6" ClientIDMode="Static" DataTextField="CategoryName" Size="Large">
</ej:GroupButton>

{% endhighlight %}

{% highlight c# %}

  protected void Page_Load(object sender, EventArgs e)
    {
        GroupButton6.DataSource = "http://mvc.syncfusion.com/Services/Northwnd.svc/";
        GroupButton6.Query = "ej.Query().from('Categories').select('CategoryID,CategoryName').take(4)";
    }

{% endhighlight %}

The following screenshot displays the output of the above code example. 

![](Datasource_images/remote.png)

## XML Data binding

XML data can be used in Groupbutton to populate the groupbutton items by using XmlDataSource control. This control can be mapped to Groupbutton control by using DataSourceID property available in Groupbutton.
In the design page, map the Groupbutton item properties to XML data properties as given below.

{% highlight html %}

<ej:GroupButton runat="server" ID="GroupButton7" ClientIDMode="Static" DataTextField="Text" DataSourceID="xml_grp_btn">
</ej:GroupButton>

<asp:XmlDataSource ID="xml_grp_btn" runat="server" DataFile ="App_Data/XMLData.xml"></asp:XmlDataSource>

{% endhighlight %}

Load the Groupbutton items in the XML data as illustrated in the following code example in a XML file “XMLData.xml”.

{% highlight xml %}

<?xml version="1.0" encoding="utf-8" ?>

<Items>
<Item Text="Foundation"></Item>

<Item Text="Launch"></Item>

<Item Text="Company" ></Item>

<Item Text="Location"></Item>

</Items>

{% endhighlight %}

The following screenshot displays the output for the XML Data binding.                                                                                                       

![](Datasource_images/xml.png) 