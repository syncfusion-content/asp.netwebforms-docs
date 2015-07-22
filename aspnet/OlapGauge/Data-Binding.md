---
layout: post
title: Data-Binding
description: data binding
platform: aspnet
control: OLAP Gauge
documentation: ug
---

# Data Binding

OLAP Gauge control enables you to retrieve multidimensional data either from SSAS or from any XML/A provider and present the OLAP information in a meaningful way.

## SSAS

Binding OLAP Gauge to the Offline Cube

The following code illustrates how to connect to an offline cube:


{% highlight c# %}
 
string connectionString = @"DataSource= C:\Users\<UserName>\appdata\local\syncfusion\essentialstudio\x.x.x.x\Common\Data\OfflineCube\Adventure_Works_Ext.cub; Provider = MSOLAP;";

OlapDataManager DataManager = new OlapDataManager(connectionString);
{% endhighlight %}
Binding OLAP Gauge to the SQL Server (Local)

The following code illustrates how to connect to a Cube available in local SQL Server:


{% highlight c# %}
 
string connectionString = @"DataSource= C:\Users\<UserName>\appdata\local\syncfusion\essentialstudio\x.x.x.x\Common\Data\OfflineCube\Adventure_Works_Ext.cub; Provider = MSOLAP;";

OlapDataManager DataManager = new OlapDataManager(connectionString);
{% endhighlight %}
## XML/A

XML for Analysis (XML/A) is a standard that allows the client applications to transfer multi-dimensional or OLAP data sources from an OLAP Server that is available online. The back and forth communication is done using the web standards – HTTP, SOAP, and XML. The query language used is MDX, which is most widely supported for reporting from multi-dimensional data stores.

Use Case Scenarios

XML/A provides the most efficient way to access an OLAP database over the Internet.

Connecting to SSAS Server (Online)

The following code illustrates how to connect to the SSAS server available online:


{% highlight c# %}
 
static string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";   

OlapDataManager DataManager = new OlapDataManager(connectionString);
{% endhighlight %}
Connecting to Mondrian Server

The following code illustrates how to connect to the Mondrian Server:


{% highlight c# %}

// Connecting to Mondrian Server

string connectionString = @"Data Source = http://localhost:8080/mondrian/xmla; Initial Catalog =FoodMart;";

OlapDataManager DataManager = new OlapDataManager(connectionString);

DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.Mondrian; 
{% endhighlight %}
Connecting to Active Pivot Server

The following code illustrates how to connect to Active Pivot Server:



{% highlight c# %}
 
// Connecting to Active Pivot Server

string connectionString= @"Data Source=http://localhost:8081/var_s/xmla;  Initial Catalog=VaRCubes; User ID=; Password=; Transport Compression=None;";

OlapDataManager DataManager = new OlapDataManager(connectionString);

DataManager.DataProvider.ProviderName = Syncfusion.Olap.DataProvider.Providers.ActivePivot;

{% endhighlight %}


