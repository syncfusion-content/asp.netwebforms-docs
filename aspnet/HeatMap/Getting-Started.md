---
layout: post
title: Getting started with Syncfusion Essential HeatMap for JavaScript
description: Getting started walk through to create your first Heat map.
platform: ejweb
control: HeatMap
documentation: ug
---

# Getting Started

## Initialize the SfHeatMap

Initialize `HeatMap` to the Html Page as shown in the following code sample.

{% highlight aspx-cs %}

@*Initializes heat map control*@

<div>
    <ej:HeatMap runat="server" ID="TableHeatmap" Width="950">
    </ej:HeatMap>
</div>
    
{% endhighlight %}
 

## Prepare data

Populate product information in a collection

{% highlight c# %}

[Serializable]
public class SampleTableData
{
    private string productName;
    [JsonProperty("ProductName")]
    [DefaultValue("")]
    public string ProductName
    {
        get { return productName; }
        set { productName = value; }
    }

    private double y2010;
    [JsonProperty("Y2010")]
    [DefaultValue("")]
    public double Y2010
    {
        get { return y2010; }
        set { y2010 = value; }
    }

    private double y2011;
    [JsonProperty("Y2011")]
    [DefaultValue("")]
    public double Y2011
    {
        get { return y2011; }
        set { y2011 = value; }
    }

    private double y2012;
    [JsonProperty("Y2012")]
    [DefaultValue("")]
    public double Y2012
    {
        get { return y2012; }
        set { y2012 = value; }
    }

    private double y2013;
    [JsonProperty("Y2013")]
    [DefaultValue("")]
    public double Y2013
    {
        get { return y2013; }
        set { y2013 = value; }
    }

    private double y2014;
    [JsonProperty("Y2014")]
    [DefaultValue("")]
    public double Y2014
    {
        get { return y2014; }
        set { y2014 = value; }
    }

    private double y2015;
    [JsonProperty("Y2015")]
    [DefaultValue("")]
    public double Y2015
    {
        get { return y2015; }
        set { y2015 = value; }
    }
}
 
{% endhighlight %}

## Populate data

Populate product information in a collection.

{% highlight c# %} 
       
public void CreateTableHeatmap()
{
    TableHeatmap.ItemsSource = GetTableSource();
}

public Collection GetTableSource()
{
    Collection collection = new Collection();
    Random random = new Random();
    string[] rows = { "Vegie-spread", "Tofuaa", "Alice Mutton", "Konbu", "Fløtemysost", "Perth Pasties", "Boston Crab Meat", "Raclette Courdavault" };
    for (int i = 0; i < 8; i++)
    {
        collection.Add(new SampleTableData()
        {
            ProductName = rows[i],
            Y2010 = random.Next(0, 100),
            Y2011 = random.Next(0, 100),
            Y2012 = random.Next(0, 100),
            Y2013 = random.Next(0, 100),
            Y2014 = random.Next(0, 100),
            Y2015 = random.Next(0, 100)
        });
    }
    return collection;
}

{% endhighlight %}

## Map data into HeatMap

Now data is ready, next we need to configure data source and map rows and columns to visualize.

* Prepare `ItemsMapping` add it in resource.

{% highlight c# %}

TableMapping TableMapping = new TableMapping();
TableMapping.HeaderMapping = new HeaderMapping() { PropertyName = "ProductName", DisplayName = "Product Name" };
TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2010", DisplayName = "Y2010" });
TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2011", DisplayName = "Y2011" });
TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2012", DisplayName = "Y2012" });
TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2013", DisplayName = "Y2013" });
TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2014", DisplayName = "Y2014" });
TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2015", DisplayName = "Y2015" });
TableHeatmap.ItemsMapping = TableMapping;
        
{% endhighlight %}

 
![](Getting-Started_images/Getting-Started_img1.png)
 
##Color Mapping
  
Next we can configure color range for these values using color mapping
 
* Configure items mapping based on items source.
 
{% highlight aspx-cs %}  
        
<ej:HeatMap runat="server" ID="TableHeatmap" Width="950">
    <ColorMappingCollection>
        <ej:HeatMapColorMapping Color="#8ec8f8" Value="0">
            <label text="0"></label>
        </ej:HeatMapColorMapping>
        <ej:HeatMapColorMapping Color="#0d47a1" Value="100">
            <label text="100"></label>
        </ej:HeatMapColorMapping>
    </ColorMappingCollection>
</ej:HeatMap>
            
{% endhighlight %} 
 

* This will show the grid data with color based on the range given.
 
![](Getting-Started_images/Getting-Started_img2.png)
 
 
## Legend
 
A legend control is used to represent range value in a gradient, create a legend with the same color mapping as shown below.
  
{% highlight aspx-cs %}
   
@*Initializes heat map control*@
<div>
        <ej:HeatMapLegend runat="server" ClientIDMode="static" ID="TableHeatmapLegend" Height="50px" Width="75%" legendmode="Gradient" orientation="Horizontal" IsResponsive="true">
            <ColorMappingCollection>
                <ej:HeatMapColorMapping Color="#8ec8f8" Value="0">
                    <label text="0"></label>
                </ej:HeatMapColorMapping>
                <ej:HeatMapColorMapping Color="#0d47a1" Value="100">
                    <label text="100"></label>
                </ej:HeatMapColorMapping>
            </ColorMappingCollection>
        </ej:HeatMapLegend>
</div>
    
{% endhighlight %}

Final script file looks like this.

{% tabs %}
{% highlight aspx-cs %}

<div style="width: 950px; margin: 0 auto; text-align: center;">
    <ej:HeatMap runat="server" ID="TableHeatmap" Width="950" IsResponsive="true">
        <ColorMappingCollection>
            <ej:HeatMapColorMapping Color="#8ec8f8" Value="0">
                <label text="0"></label>
            </ej:HeatMapColorMapping>
            <ej:HeatMapColorMapping Color="#0d47a1" Value="100">
                <label text="100"></label>
            </ej:HeatMapColorMapping>
        </ColorMappingCollection>
    </ej:HeatMap>
    <div style="height: 15px; width: 100%;"></div>
    <ej:HeatMapLegend runat="server" ClientIDMode="static" ID="TableHeatmapLegend" Height="50px" Width="75%" legendmode="Gradient" orientation="Horizontal" IsResponsive="true">
        <ColorMappingCollection>
            <ej:HeatMapColorMapping Color="#8ec8f8" Value="0">
                <label text="0"></label>
            </ej:HeatMapColorMapping>
            <ej:HeatMapColorMapping Color="#0d47a1" Value="100">
                <label text="100"></label>
            </ej:HeatMapColorMapping>
        </ColorMappingCollection>
    </ej:HeatMapLegend>
</div>
        
{% endhighlight %}

{% highlight c# %}

public class TableMapBinding : System.Web.UI.Page
{

    protected void Page_Load(object sender, EventArgs e)
    {
        if (!IsPostBack)
        {
            TableHeatmap.LegendCollection.Add("TableHeatmapLegend");
            TableMapping TableMapping = new TableMapping();
            TableMapping.HeaderMapping = new HeaderMapping() { PropertyName = "ProductName", DisplayName = "Product Name", ColumnStyle = new ColumnStyle() { Width = 140, TextAlign = HeatMapTextAlign.Right } };
            TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2010", DisplayName = "Y2010" });
            TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2011", DisplayName = "Y2011" });
            TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2012", DisplayName = "Y2012" });
            TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2013", DisplayName = "Y2013" });
            TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2014", DisplayName = "Y2014" });
            TableMapping.ColumnMapping.Add(new HeaderMapping() { PropertyName = "Y2015", DisplayName = "Y2015" });
            TableHeatmap.ItemsMapping = TableMapping;
            TableHeatmap.ItemsSource = GetTableSource();

        }
    }

    public Collection GetTableSource()
    {
        Collection collection = new Collection();
        Random random = new Random();
        string[] rows = { "Vegie-spread", "Tofuaa", "Alice Mutton", "Konbu", "Fløtemysost", "Perth Pasties", "Boston Crab Meat", "Raclette Courdavault" };
        for (int i = 0; i < 8; i++)
        {
            collection.Add(new SampleTableData()
            {
                ProductName = rows[i],
                Y2010 = random.Next(0, 100),
                Y2011 = random.Next(0, 100),
                Y2012 = random.Next(0, 100),
                Y2013 = random.Next(0, 100),
                Y2014 = random.Next(0, 100),
                Y2015 = random.Next(0, 100)
            });
        }
        return collection;
    }
}

[Serializable]
public class SampleTableData
{
    private string productName;
    [JsonProperty("ProductName")]
    [DefaultValue("")]
    public string ProductName
    {
        get { return productName; }
        set { productName = value; }
    }

    private double y2010;
    [JsonProperty("Y2010")]
    [DefaultValue("")]
    public double Y2010
    {
        get { return y2010; }
        set { y2010 = value; }
    }

    private double y2011;
    [JsonProperty("Y2011")]
    [DefaultValue("")]
    public double Y2011
    {
        get { return y2011; }
        set { y2011 = value; }
    }

    private double y2012;
    [JsonProperty("Y2012")]
    [DefaultValue("")]
    public double Y2012
    {
        get { return y2012; }
        set { y2012 = value; }
    }

    private double y2013;
    [JsonProperty("Y2013")]
    [DefaultValue("")]
    public double Y2013
    {
        get { return y2013; }
        set { y2013 = value; }
    }

    private double y2014;
    [JsonProperty("Y2014")]
    [DefaultValue("")]
    public double Y2014
    {
        get { return y2014; }
        set { y2014 = value; }
    }

    private double y2015;
    [JsonProperty("Y2015")]
    [DefaultValue("")]
    public double Y2015
    {
        get { return y2015; }
        set { y2015 = value; }
    }
}

{% endhighlight %}
{% endtabs %}

![](Getting-Started_images/Getting-Started_img3.png)