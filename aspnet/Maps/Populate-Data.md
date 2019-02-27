---
layout: post
title: Populate Data | Maps | ASP.NET Webforms | Syncfusion
description: populate data
platform: aspnet
control: Maps
documentation: ug
---

# Populate Data

In this section you can learn how to populate shape data for providing Data input to Map control and usage of DataSource property.

## Shape Data

The Shape Data collection describing geographical shape information can be obtained from [GEOJSON format shapes](http://www.syncfusion.com/uploads/user/uploads/Maps_GeoJSON.zip).

In this example, USA shape is used as shape data by utilizing the “United States of America.json” file in the following folder structure obtained from downloaded Maps_GeoJSON folder.

..\ Maps_GeoJSON\All Countries with States

You can store the “United States of America.json” file in App_Data folder as “USA.json”. Then, read the complete contents in “USA.json” file and assign to new MapData object in “Map.aspx.cs”  in the following folder location,


{% highlight c# %}


public object GetUSA()

        {

            string allText = System.IO.File.ReadAllText(Server.MapPath("~/App_Data/USA.json"));

            JavaScriptSerializer ser = new JavaScriptSerializer();

            ser.MaxJsonLength = int.MaxValue;

            return new MapData(allText);

        }



{% endhighlight %}

## Data Binding

The Maps control supports data binding with the DataSource property in the shape layers.

## Properties required

The following properties in shape layers is be used for binding data in Maps control,

* DataSource
* ShapeDataPath
* ShapePropertyPath

## Data Source

The DataSource property accepts the collection values as input. For example, you can provide the list of objects as input.

## Shape Data Path

The ShapeDataPath property is used to refer the data ID in DataSource. For example, population MapData contains data ids ‘Name’ and ‘Population’. The ShapeDataPath and the ShapePropertyPath properties are related to each other (refer to ShapePropertyPath for more details).

## Shape Property Path

The ShapePropertyPath property is similar to the ShapeDataPath that refers to the column name in the Data property of shape layers to identify the shape. Wen the values of the ShapeDataPath property in the DataSource property and the value of ShapePropertyPath in the Data property match, then the associated object from the DataSource is bound to the corresponding shape.

The datasource is populated with JSON data relative to shape data and stored in JSON object. The USA population as datasource is used for better understanding.

  “Map.aspx.cs” is populated with data of USA Population and maintained as a list. After populating the data, you can refer to both shape data and datasource as illustrated in the following “Map.aspx.cs”.



{% highlight c# %}

public List<CountyPopulationData> GetUSPopulationData()
{
   List<CountyPopulationData> populationData = new List<CountyPopulationData>
   {
	new CountyPopulationData(){ Name= "California", Population=38332521},
	new CountyPopulationData(){ Name= "Texas", Population=26448193},
	new CountyPopulationData(){ Name= "New York", Population=19651127},
	new CountyPopulationData(){ Name= "Florida", Population=19552860},
	new CountyPopulationData(){ Name= "Illinois", Population=12882135},
	new CountyPopulationData(){ Name= "Pennsylvania", Population=12773801},
	new CountyPopulationData(){ Name= "Ohio", Population=11570808},
	new CountyPopulationData(){ Name= "Georgia", Population=9992167},
	new CountyPopulationData(){ Name= "Michigan", Population=9895622},
	new CountyPopulationData(){ Name= "North Carolina", Population=9848060},
	new CountyPopulationData(){ Name= "New Jersey", Population=8899339},
	new CountyPopulationData(){ Name= "Virginia", Population=8260405},
	new CountyPopulationData(){ Name= "Washington", Population=6971406},
	new CountyPopulationData(){ Name= "Massachusetts", Population=6692824},
	new CountyPopulationData(){ Name= "Arizona", Population=6626624},
	new CountyPopulationData(){ Name= "Indiana", Population=6570902},
	new CountyPopulationData(){ Name= "Tennessee", Population=6495978},
	new CountyPopulationData(){ Name= "Missouri", Population=6044171},
	new CountyPopulationData(){ Name= "Maryland", Population=5928814},
	new CountyPopulationData(){ Name= "Wisconsin", Population=5742713},
	new CountyPopulationData(){ Name= "Minnesota", Population=5420380},
	new CountyPopulationData(){ Name= "Colorado", Population=5268367},
	new CountyPopulationData(){ Name= "Alabama", Population=4833722},
	new CountyPopulationData(){ Name= "South Carolina", Population=4774839},
	new CountyPopulationData(){ Name= "Louisiana", Population=4625470},
	new CountyPopulationData(){ Name= "Kentucky", Population=4395295},
	new CountyPopulationData(){ Name= "Oregon", Population=3930065},
	new CountyPopulationData(){ Name= "Oklahoma", Population=3850568},
	new CountyPopulationData(){ Name= "Puerto Rico", Population=3615086},
	new CountyPopulationData(){ Name= "Connecticut", Population=3596080},
	new CountyPopulationData(){ Name= "Iowa", Population=3090416},
	new CountyPopulationData(){ Name= "Mississippi", Population=2991207},
	new CountyPopulationData(){ Name= "Arkansas", Population=2959373},
	new CountyPopulationData(){ Name= "Utah", Population=2900872},
	new CountyPopulationData(){ Name= "Kansas", Population=2893957},
	new CountyPopulationData(){ Name= "Nevada", Population=2790136},
	new CountyPopulationData(){ Name= "New Mexico", Population=2085287},
	new CountyPopulationData(){ Name= "Nebraska", Population=1868516},
	new CountyPopulationData(){ Name= "West Virginia", Population=1854304},
	new CountyPopulationData(){ Name= "Idaho", Population=1612136},
	new CountyPopulationData(){ Name= "Hawaii", Population=1404054},
	new CountyPopulationData(){ Name= "Maine", Population=1328302},
	new CountyPopulationData(){ Name= "New Hampshire", Population=1323459},
	new CountyPopulationData(){ Name= "Rhode Island", Population=1051511},
	new CountyPopulationData(){ Name= "Montana", Population=1015165},
	new CountyPopulationData(){ Name= "Delaware", Population=925749},
	new CountyPopulationData(){ Name= "South Dakota", Population=844877},
	new CountyPopulationData(){ Name= "Alaska", Population=735132},
	new CountyPopulationData(){ Name= "North Dakota", Population=723393},
	new CountyPopulationData(){ Name= "District of Columbia", Population=646449},
	new CountyPopulationData(){ Name= "Vermont", Population=626630},
	new CountyPopulationData(){ Name= "Wyoming", Population=582658}
  };
  return populationData;
}

[Serializable]
public class CountyPopulationData
 {

   public string name;

   public string Name
   {
   get { return name; }
   set { name = value; }
   }

   public double population;

   public double Population
   {
   get { return population; }
   set { population = value; }
   }

 }
   protected void Page_Load(object sender, EventArgs e)
   {
    (this.map.Layers[0] as ShapeLayer).DataSource = Election_Result.GetUSPopulationData();
    (this.map.Layers[0] as ShapeLayer).ShapeData = this.GetUSA();
   }

{% endhighlight %}

The JSON object “populationData” is used as dataSource in the following code example.

{% highlight html %}

   <ej:Map ID="map" runat="server">

        <Layers>

            <ej:ShapeLayer ShapeDataPath = "name" ShapePropertyPath= "name">

        </Layers>

     </ ej:Map >

{% endhighlight %}