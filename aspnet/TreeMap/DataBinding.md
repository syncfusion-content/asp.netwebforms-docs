---
layout: post
title: DataBinding | TreeMap | ASP.NET | Syncfusion
description: databinding
platform: aspnet
control: TreeMap
documentation: ug
---

# DataBinding

TreeMap control supports Data Binding and it can be achieved using DataSource property.

The `DataSource` property accepts the collection values as input. For example, you can provide the list of objects as input. The following code illustrates you on how to bind a flat collection as datasource for TreeMap.

{% tabs %}
{% highlight C# %}

public partial class treemap1 : Page

{

    protected void Page_Load(object sender, EventArgs e)

    {

        this.treemap.DataSource = TreeMapPopulationData.GetData();

    }

}

[Serializable]
public class TreeMapPopulationData

{

    public string Continent { get; set; }

    public string Country { get; set; }

    public int Growth { get; set; }

    public long Population { get; set; }



    public static List<TreeMapPopulationData> GetData()

    {

        List<TreeMapPopulationData> pop = new List<TreeMapPopulationData>();

        pop.Add(new TreeMapPopulationData() { Continent = "Asia", Country = "Indonesia", Growth = 3, Population = 237641326 });

        pop.Add(new TreeMapPopulationData() { Continent = "Asia", Country = "Russia", Growth = 2, Population = 152518015 });

        pop.Add(new TreeMapPopulationData() { Continent = "Asia", Country = "Mal", Growth = 1, Population = 29672000 });

        pop.Add(new TreeMapPopulationData() { Continent = "North America", Country = "United States", Growth = 4, Population = 315645000 });

        pop.Add(new TreeMapPopulationData() { Continent = "North America", Country = "Mexico", Growth = 2, Population = 112336538 });

        pop.Add(new TreeMapPopulationData() { Continent = "North America", Country = "Canada", Growth = 1, Population = 39056064 });

        pop.Add(new TreeMapPopulationData() { Continent = "South America", Country = "Colombia", Growth = 1, Population = 47000000 });

        pop.Add(new TreeMapPopulationData() { Continent = "South America", Country = "Brazil", Growth = 3, Population = 193946886 });

        pop.Add(new TreeMapPopulationData() { Continent = "Africa", Country = "Nigeria", Growth = 2, Population = 170901000 });

        pop.Add(new TreeMapPopulationData() { Continent = "Africa", Country = "Egypt", Growth = 1, Population = 83661000 });

        pop.Add(new TreeMapPopulationData() { Continent = "Europe", Country = "Germany", Growth = 1, Population = 81993000 });

        pop.Add(new TreeMapPopulationData() { Continent = "Europe", Country = "France", Growth = 1, Population = 65605000 });

        pop.Add(new TreeMapPopulationData() { Continent = "Europe", Country = "UK", Growth = 1, Population = 63181775 });

        return pop;

    }

}

 {% endhighlight %}

 {% highlight html %}

<ej:Treemap ID="treemap" runat="server" WeightValuePath = "Population" ColorValuePath = "Growth">

</ej:Treemap>

{% endhighlight %}
{% endtabs %}


