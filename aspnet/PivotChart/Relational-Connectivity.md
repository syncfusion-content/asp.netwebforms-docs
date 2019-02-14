---
layout: post
title: Relational Connectivity | PivotChart | ASP.NET | Syncfusion
description: relational connectivity
platform: aspnet
control: PivotChart
documentation: ug
---

# Data binding

## Binding pivot chart to collection
This section demonstrates binding a collection to the pivot chart control as a data source. For more information on this data source, refer to the following links:

If you are using WebAPI controller, refer to the “Datasource Initialization” section under the following [link](https://help.syncfusion.com/js/pivotchart/relational-getting-started#creating-a-simple-application-with-pivotchart-and-relational-datasource-server-mode).

If you are using WCF Service, refer to the "Datasource Initialization" section below.

## WCF
**Adding a WCF service**

To add a WCF service in an existing web application, right-click the project in the solution explorer and select **Add > New Item**. In the **Add New Item** window, select WCF service and name it `RelationalService.svc`, and then click **Add.**

Now, the WCF service is added to the application that comprises the following files. The utilization of these files is explained in the immediate sections.

* RelationalService.svc
* RelationalService.svc.cs
* IRelationalService.cs

**Configuring WCF service class**

Remove the “DoWork” method present in both `RelationalService.svc.cs` and `IRelationalService.cs` files. Next, add “AspNetCompatibilityRequirements” attribute on top of the main class present in the `RelationalService.svc.cs` file and set the **“RequirementsMode”** value to **“Allowed”**.

{% highlight c# %}

namespace PivotChartDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class RelationalService : IRelationalService
    {

    }
}
{% endhighlight %}

**List of dependency libraries**

Next, you can add the below-mentioned dependency libraries to your web application. These libraries could be found in the GAC (Global Assembly Cache).

To add them to your web application, right-click **References** in the solution explorer and select **Add Reference**. In the **Reference Manager** dialog, under **Assemblies > Extension**, the following Syncfusion libraries are found.

N> If you have installed any version of Essential Studio, then the location of Syncfusion libraries is [system drive:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Assemblies].

* Syncfusion.Compression.Base
* Syncfusion.Linq.Base
* Syncfusion.Olap.Base
* Syncfusion.PivotAnalysis.Base
* Syncfusion.XlsIO.Base
* Syncfusion.Pdf.Base
* Syncfusion.DocIO.Base
* Syncfusion.EJ
* Syncfusion.EJ.Web
* Syncfusion.EJ.Export
* Syncfusion.EJ.Pivot

**List of namespaces**

Following are the list of namespaces to be added on top of the main class in the `RelationalService.svc.cs` file:

{% highlight c# %}

using System.ServiceModel.Activation;
using Syncfusion.JavaScript;
using Syncfusion.PivotAnalysis.Base;

namespace PivotChartDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class RelationalService : IRelationalService
    {

    }
}
{% endhighlight %}

**Data source initialization**

A simple collection is provided as a data source for the pivot chart in this demo section. This data source is placed in a separate class named “ProductSales” in the `RelationalService.svc.cs` file. Refer to the following code example:

{% highlight c# %}

namespace PivotChartDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class RelationalService : IRelationalService
    {
        //....
        //....
    }

    internal class ProductSales
    {
        public string Product { get; set; }

        public string Date { get; set; }

        public string Country { get; set; }

        public string State { get; set; }

        public int Quantity { get; set; }

        public double Amount { get; set; }


        public static ProductSalesCollection GetSalesData()
        {
            /// Geography
            string[] countries = new string[] { "Australia", "Canada", "France", "Germany", "United Kingdom", "United States" };
            string[] ausStates = new string[] { "New South Wales", "Queensland", "South Australia", "Tasmania", "Victoria" };
            string[] canadaStates = new string[] { "Alberta", "British Columbia", "Brunswick", "Manitoba", "Ontario", "Quebec" };
            string[] franceStates = new string[] { "Charente-Maritime", "Essonne", "Garonne (Haute)", "Gers", };
            string[] germanyStates = new string[] { "Bayern", "Brandenburg", "Hamburg", "Hessen", "Nordrhein-Westfalen", "Saarland" };
            string[] ukStates = new string[] { "England" };
            string[] ussStates = new string[] { "New York", "North Carolina", "Alabama", "California", "Colorado", "New Mexico", "South Carolina" };

            /// Time
            string[] dates = new string[] { "FY 2005", "FY 2006", "FY 2007", "FY 2008", "FY 2009" };

            /// Products
            string[] products = new string[] { "Bike", "Van", "Car" };
            Random r = new Random(123345345);

            int numberOfRecords = 2000;
            ProductSalesCollection listOfProductSales = new ProductSalesCollection();
            for (int i = 0; i < numberOfRecords; i++)
            {
                ProductSales sales = new ProductSales();
                sales.Country = countries[r.Next(1, countries.GetLength(0))];
                sales.Quantity = r.Next(1, 12);
                /// 1 percent discount for 1 quantity
                double discount = (30000 * sales.Quantity) * (double.Parse(sales.Quantity.ToString()) / 100);
                sales.Amount = (30000 * sales.Quantity) - discount;
                sales.Date = dates[r.Next(r.Next(dates.GetLength(0) + 1))];
                sales.Product = products[r.Next(r.Next(products.GetLength(0) + 1))];
                switch (sales.Product)
                {
                    case "Car":
                    {
                        sales.Date = "FY 2005";
                        break;
                    }
                }
                switch (sales.Country)
                {
                    case "Australia":
                    {
                        sales.State = ausStates[r.Next(ausStates.GetLength(0))];
                        break;
                    }
                    case "Canada":
                    {
                        sales.State = canadaStates[r.Next(canadaStates.GetLength(0))];
                        break;
                    }
                    case "France":
                    {
                        sales.State = franceStates[r.Next(franceStates.GetLength(0))];
                        break;
                    }
                    case "Germany":
                    {
                        sales.State = germanyStates[r.Next(germanyStates.GetLength(0))];
                        break;
                    }
                    case "United Kingdom":
                    {
                        sales.State = ukStates[r.Next(ukStates.GetLength(0))];
                        break;
                    }
                    case "United States":
                    {
                        sales.State = ussStates[r.Next(ussStates.GetLength(0))];
                        break;
                    }
                }
                listOfProductSales.Add(sales);
            }
            return listOfProductSales;
        }

        public override string ToString()
        {
            return string.Format("{0}-{1}-{2}", this.Country, this.State, this.Product);
        }

        public class ProductSalesCollection : List<ProductSales>
        {
        }
    }
}
{% endhighlight %}

**Service methods in WCF service**

First, you can define the service methods in the IRelationalService interface, find in the `IRelationalService.cs` file which was created while adding the WCF service to your web application.

{% highlight c# %}

namespace PivotChartDemo
{
    [ServiceContract]
    public interface IRelationalService
    {
        [OperationContract]
        Dictionary<string, object> InitializeChart(string action, string currentReport, string customObject);
        [OperationContract]
        Dictionary<string, object> DrillChart(string action, string drilledSeries);
    }
}
{% endhighlight %}

Then, you can elaborate the service methods in the main class that is found in the `RelationalService.svc.cs` file.

{% highlight c# %}

namespace PivotChartDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class RelationalService : IRelationalService
    {
        PivotChart PivotChart = new PivotChart();

        public Dictionary<string, object> InitializeChart(string action, string currentReport, string customObject)
        {
            this.BindData();
            return PivotChart.GetJsonData(action, ProductSales.GetSalesData());
        }

        public Dictionary<string, object> DrillChart(string action, string drilledSeries)
        {
            this.BindData();
            return PivotChart.GetJsonData(action, ProductSales.GetSalesData(), drilledSeries);
        }

        private void BindData()
        {
            this.PivotChart.PivotEngine.PivotRows.Add(new PivotItem { FieldMappingName = "Country", FieldHeader = "Country", TotalHeader = "Total" });
            this.PivotChart.PivotEngine.PivotRows.Add(new PivotItem { FieldMappingName = "State", FieldHeader = "State", TotalHeader = "Total" });
            this.PivotChart.PivotEngine.PivotRows.Add(new PivotItem { FieldMappingName = "Date", FieldHeader = "Date", TotalHeader = "Total" });
            this.PivotChart.PivotEngine.PivotColumns.Add(new PivotItem { FieldMappingName = "Product", FieldHeader = "Product", TotalHeader = "Total" });
            this.PivotChart.PivotEngine.PivotCalculations.Add(new PivotComputationInfo { CalculationName = "Amount", Description = "Amount", FieldHeader = "Amount", FieldName = "Amount", Format = "C", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.DoubleTotalSum });
        }
    }
    .....
    ..... // Datasource initialization
    .....
}
{% endhighlight %}

**Configuring web configuration file**

You can expose the services through the properties such as binding, contract, and address by using an endpoint.

1. Contract: This property indicates that the contract of the endpoint is exposed. Refer to the `IRelationalService` contract, and it is written as `PivotChartDemo.IRelationalService`.
2. Binding: In your application, you can use `webHttpBinding` to post and receive requests and responses between the client-end and the service.
3. behaviorConfiguration: This property contains the name of the behavior to be used in the endpoint.

The endpointBehaviors are illustrated as follows:

{% highlight xml %}

<system.serviceModel>
    ……
    ……
    <services>
        <service name="PivotChartDemo.RelationalService">
            <endpoint address="" behaviorConfiguration="PivotChartDemo.RelationalServiceAspNetAjaxBehavior"
            binding="webHttpBinding" contract="PivotChartDemo.IRelationalService" />
        </service>
    </services>
</system.serviceModel>
{% endhighlight %}

The endpointBehaviors contain all behaviors for an endpoint. You can link each endpoint to the respective behavior only by using this name property.

{% highlight xml %}

<system.serviceModel>
    <behaviors>
        <endpointBehaviors>
            <behavior name="PivotChartDemo.RelationalServiceAspNetAjaxBehavior">
                <enableWebScript />
            </behavior>
        </endpointBehaviors>
    </behaviors>
    ……
    ……
</system.serviceModel>
{% endhighlight %}

N> In this example, the **“PivotChartDemo”** indicates the name and root namespace of the web application created in the Visual Studio IDE, and the **“RelationalService”** indicates the name of the created WCF service.

Now, the **pivot chart** will be rendered with amount over a set of products across different customer geographic locations.


![ASP NET pivot chart control with relational wcf service](Relational-Connectivity_images/ServerModeWCF.png)

