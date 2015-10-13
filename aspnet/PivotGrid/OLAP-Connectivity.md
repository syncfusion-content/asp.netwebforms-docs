---
layout: post
title: OLAP Connectivity | PivotGrid | ASP.NET | Syncfusion
description: olap connectivity 
platform: aspnet
control: PivotGrid
documentation: ug
---

# OLAP Connectivity 

PivotGrid control enables you to retrieve multidimensional data either from SSAS or from any XML/A provider and present the OLAP information in significant ways.

## SSAS

### Binding PivotGrid to the Offline Cube

The following code example illustrates how to connect to an offline cube.

{% highlight C# %}
string connectionString = @"DataSource= C:\Users\<UserName>\appdata\local\syncfusion\essentialstudio\x.x.x.x\Common\Data\OfflineCube\Adventure_Works_Ext.cub; Provider = MSOLAP;";

OlapDataManager DataManager = new OlapDataManager(connectionString);
{% endhighlight %}


### Binding PivotGrid to the SQL Server (Local)

The following code example illustrates how to connect to a Cube available in local SQL Server.

{% highlight C# %}
string connectionString = "Data source=localhost; Initial Catalog=Adventure Works DW;";

OlapDataManager DataManager = new OlapDataManager(connectionString);
{% endhighlight %}

## XML/A

XML for Analysis (XML/A) is a standard that allows the client applications to transfer multi-dimensional or OLAP data sources from an OLAP Server that is available online. The back and forth communication is done using the web standards – HTTP, SOAP, and XML. The query language used is MDX that is most widely supported for reporting from multi-dimensional data stores.

### Use Case Scenarios

XML/A provides the most efficient way to access an OLAP database over the Internet.

### Connecting to SSAS Server (Online)

The following code example illustrates how to connect to the SSAS server available online:

{% highlight C# %}
static string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";   

OlapDataManager DataManager = new OlapDataManager(connectionString);
{% endhighlight %}

### Connecting to Mondrian Server

The following code example illustrates how to connect to the Mondrian Server:

{% highlight C# %}
string connectionString = @"Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;";

OlapDataManager DataManager = new OlapDataManager(connectionString);

DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian; 
{% endhighlight %}

### Connecting to Active Pivot Server

The following code example illustrates how to connect to Active Pivot Server:

{% highlight C# %}
string connectionString= @"Data Source=http://localhost:8081/var_s/xmla;  Initial Catalog=VaRCubes; User ID=; Password=; Transport Compression=None;";

OlapDataManager DataManager = new OlapDataManager(connectionString);

DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.ActivePivot;
{% endhighlight %}