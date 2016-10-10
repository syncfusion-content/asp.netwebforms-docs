---
layout: post
title: Relational Connectivity | PivotGrid | ASP.NET | Syncfusion
description: relational connectivity 
platform: aspnet
control: PivotGrid
documentation: ug
---

# Data Binding

## Binding PivotGrid to Collection

This section demonstrates binding of a collection to the PivotGrid control as datasource. For more information on this datasource refer the following links.

If you are using WebAPI controller, refer the "Datasource Initialization" section under the following [link](http://help.syncfusion.com/aspnet/pivotgrid/relational-getting-started#creating-a-simple-application-with-pivotgrid-and-relational-datasource-server-mode).

If you are using WCF Service, refer the "Datasource Initialization" section below.

## WCF
**Adding a WCF Service**

To add a WCF service in an existing Web Application, right-click on the project in Solution Explorer and select **Add > New Item**. In the **Add New Item** window, select WCF Service and name it as `RelationalService.svc`, click Add.

Now, WCF service is added into the application successfully that comprises of the following files. The utilization of these files is explained in the immediate sections

* RelationalService.svc
* RelationalService.svc.cs
* IRelationalService.cs

**Configuring WCF Service Class**

Remove the **“DoWork”** method present inside both `RelationalService.svc.cs` and `IRelationalService.cs` files.  Next, add **“AspNetCompatibilityRequirements”** attribute on top of main class present inside `RelationalService.svc.cs` and set **“RequirementsMode”** value to **“Allowed”**.

{% highlight c# %}

namespace PivotGridDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class RelationalService : IRelationalService
    {

    }
}

{% endhighlight %}

**List of Dependency Libraries**

Next you need to add the below mentioned dependency libraries into your Web Application. These libraries could be found in GAC (Global Assembly Cache) as well.
 
To add them to your Web Application, right-click on **References** in Solution Explorer and select **Add Reference**. Now in the **Reference Manager** dialog, under **Assemblies > Extension**, the following Syncfusion libraries are found. 

* Syncfusion.Compression.Base
* Syncfusion.Linq.Base
* Syncfusion.Olap.Base
* Syncfusion.PivotAnalysis.Base
* System.Data.SqlServerCe (Version: 4.0.0.0)
* Syncfusion.XlsIO.Base
* Syncfusion.Pdf.Base
* Syncfusion.DocIO.Base
* Syncfusion.EJ
* Syncfusion.EJ.Export
* Syncfusion.EJ.Pivot
* Syncfusion.EJ.Web

**List of Namespaces**

Following are the list of namespaces to be added on top of the main class inside `RelationalService.svc.cs` file.

{% highlight c# %}

using Syncfusion.JavaScript;
using Syncfusion.PivotAnalysis.Base;
using System;
using System.Collections.Generic;
using System.Data;
using System.ServiceModel.Activation;
using System.Data.SqlServerCe;
using System.Linq;
using System.Text;
using System.Web;
using System.Web.Http;
using System.Web.Script.Serialization;
using OLAPUTILS = Syncfusion.JavaScript.Olap;

namespace PivotGridDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class RelationalService : IRelationalService
    {

    }
}

{% endhighlight %}


**Datasource Initialization**

A simple collection is provided as a datasource for our PivotGrid in this demo section. This datasource is placed inside a separate class named "ProductSales" in **RelationalService.svc.cs** file. Please find the code sample below.

{% highlight c# %}

namespace PivotGridDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class RelationalService : IRelationalService
    {
    ……
    …… 
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

**Service methods in WCF Service**

First, declare the service methods inside **IRelationalService** interface, found in `IRelationalService.cs` file created while adding WCF Service to the Application.

{% highlight c# %}

namespace PivotGridDemo
{
    [ServiceContract]
    public interface IRelationalService
    {
        [OperationContract]
        Dictionary<string, object> InitializeGrid(string action);
        [OperationContract]
        Dictionary<string, object> FetchMembers(string action, string headerTag, string sortedHeaders, string currentReport);
        [OperationContract]
        Dictionary<string, object> Filtering(string action, string filterParams, string sortedHeaders, string currentReport);
        [OperationContract]
        Dictionary<string, object> NodeStateModified(string action, string headerTag, string dropAxis, string sortedHeaders, string filterParams, string currentReport);
        [OperationContract]
        Dictionary<string, object> NodeDropped(string action, string dropAxis, string headerTag, string sortedHeaders, string filterParams, string currentReport);
        [OperationContract]
        Dictionary<string, object> Sorting(string action, string sortedHeaders, string currentReport);
        [OperationContract]
        void Export(System.IO.Stream stream);
        [OperationContract]
        Dictionary<string, object> DeferUpdate(string action, string filterParams, string sortedHeaders, string currentReport);
        [OperationContract]
        Dictionary<string, object> CalculatedField(string action, string headerTag, string currentReport);
        [OperationContract]
        Dictionary<string, object> CellEditing(string action, string index, string valueHeaders, string summaryValues, string currentReport);
        [OperationContract]
        Dictionary<string, object> SaveReport(string reportName, string operationalMode, string olapReport, string clientReports);
        [OperationContract]
        Dictionary<string, object> LoadReportFromDB(string reportName, string operationalMode, string olapReport, string clientReports);
    }
}

{% endhighlight %}

Then, elaborate the service methods inside the main class, found in `RelationalService.svc.cs` file.

{% highlight c# %}

namespace PivotGridDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class RelationalService : IRelationalService
    {
        PivotGrid htmlHelper = new PivotGrid();
        JavaScriptSerializer serializer = new JavaScriptSerializer();
        Dictionary<string, object> dict = new Dictionary<string, object>();
        static int cultureIDInfoval = 1033;
        string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";
        string conStringforDB = ""; //Enter appropriate connection string to connect database for saving and loading operation of reports

        public Dictionary<string, object> InitializeGrid(string action)
        {
            htmlHelper.PivotReport = BindDefaultData();
            dict = htmlHelper.GetJsonData(action, ProductSales.GetSalesData());
            return dict;
        }
        public Dictionary<string, object> FetchMembers(string action, string headerTag, string sortedHeaders, string currentReport)
        {
            htmlHelper.PopulateData(currentReport);
            dict = htmlHelper.GetJsonData(action, ProductSales.GetSalesData(), headerTag, sortedHeaders);
            return dict;
        }

        public Dictionary<string, object> Filtering(string action, string filterParams, string sortedHeaders, string currentReport)
        {
            htmlHelper.PopulateData(currentReport);
            dict = htmlHelper.GetJsonData(action, ProductSales.GetSalesData(), filterParams, sortedHeaders);
            return dict;
        }

        public Dictionary<string, object> NodeStateModified(string action, string headerTag, string dropAxis, string sortedHeaders, string filterParams, string currentReport)
        {
            htmlHelper.PopulateData(currentReport);
            dict = htmlHelper.GetJsonData(action, ProductSales.GetSalesData(), headerTag, dropAxis, filterParams, sortedHeaders);
            return dict;
        }

        public Dictionary<string, object> NodeDropped(string action, string dropAxis, string headerTag, string sortedHeaders, string filterParams, string currentReport)
        {
            htmlHelper.PopulateData(currentReport);
            dict = htmlHelper.GetJsonData(action, ProductSales.GetSalesData(), dropAxis, headerTag, filterParams, sortedHeaders);
            return dict;
        }
        public Dictionary<string, object> Sorting(string action, string sortedHeaders, string currentReport)
        {
            htmlHelper.PopulateData(currentReport);
            dict = htmlHelper.GetJsonData(action, ProductSales.GetSalesData(), sortedHeaders);
            return dict;
        }
        public Dictionary<string, object> CalculatedField(string action, string headerTag, string currentReport)
        {
            htmlHelper.PopulateData(currentReport);
            dict = htmlHelper.GetJsonData(action, ProductSales.GetSalesData(), null, headerTag);
            return dict;
        }
        public void Export(System.IO.Stream stream)
        {
            System.IO.StreamReader sReader = new System.IO.StreamReader(stream);
            string args = System.Web.HttpContext.Current.Server.UrlDecode(sReader.ReadToEnd()).Remove(0, 5);
            Dictionary<string, string> gridParams = serializer.Deserialize<Dictionary<string, string>>(args);
            htmlHelper.PopulateData(gridParams["currentReport"]);
            string fileName = "Sample";
            htmlHelper.ExportPivotGrid(ProductSales.GetSalesData(), args, fileName, System.Web.HttpContext.Current.Response);
        }

        public Dictionary<string, object> SaveReport(string reportName, string operationalMode, string olapReport, string clientReports)
        {
            string mode = operationalMode;
            SqlCeConnection con = new SqlCeConnection() { ConnectionString = conStringforDB };
            con.Open();
            SqlCeCommand cmd1 = new SqlCeCommand("insert into ReportsTable Values(@ReportName,@Reports)", con);
            cmd1.Parameters.Add("@ReportName", reportName);
            //cmd1.Parameters.Add("@Reports", OLAPUTILS.Utils.GetReportStream(clientReports).ToArray());
            if (mode == "serverMode")
                cmd1.Parameters.Add("@Reports", OLAPUTILS.Utils.GetReportStream(clientReports).ToArray());
            else if (mode == "clientMode")
                cmd1.Parameters.Add("@Reports", Encoding.UTF8.GetBytes(clientReports).ToArray());
            cmd1.ExecuteNonQuery();
            con.Close();
            return null;
        }

        public Dictionary<string, object> LoadReportFromDB(string reportName, string operationalMode, string olapReport, string clientReports)
        {
            byte[] reportString = new byte[2 * 1024];
            PivotReport report = new PivotReport();
            var reports = "";
            string mode = operationalMode;
            Dictionary<string, object> dictionary = new Dictionary<string, object>();
            foreach (DataRow row in GetDataTable().Rows)
            {
                if ((row.ItemArray[0] as string).Equals(reportName))
                {
                    if (mode == "clientMode")
                    {
                        reportString = (row.ItemArray[1] as byte[]);
                        dictionary.Add("report", Encoding.UTF8.GetString(reportString));
                        break;
                    }
                    else if (mode == "serverMode")
                    {
                        reports = OLAPUTILS.Utils.CompressData(row.ItemArray[1] as byte[]);
                        report = htmlHelper.DeserializedReports(reports);
                        htmlHelper.PivotReport = report;
                        dictionary = htmlHelper.GetJsonData("loadOperation", ProductSales.GetSalesData(), "Load Report", reportName);
                        break;
                    }
                }
            }
            return dictionary;
        }

        private DataTable GetDataTable()
        {
            SqlCeConnection con = new SqlCeConnection() { ConnectionString = conStringforDB };
            con.Open();
            DataSet dSet = new DataSet();
            new SqlCeDataAdapter("Select * from ReportsTable", con).Fill(dSet);
            con.Close();
            return dSet.Tables[0];
        }

        public Dictionary<string, object> DeferUpdate(string action, string filterParams, string sortedHeaders, string currentReport)
        {
            htmlHelper.PopulateData(currentReport);
            dict = htmlHelper.GetJsonData(action, ProductSales.GetSalesData(), null, null, null, sortedHeaders, filterParams);
            return dict;
        }
        public Dictionary<string, object> CellEditing(string action, string index, string valueHeaders, string summaryValues, string currentReport)
        {
            htmlHelper.PopulateData(currentReport);
            dict = htmlHelper.GetJsonData(action, ProductSales.GetSalesData(), index, summaryValues, valueHeaders);
            return dict;
        }
        private PivotReport BindDefaultData()
        {
            PivotReport pivotSetting = new PivotReport();
            pivotSetting.PivotRows.Add(new PivotItem { FieldMappingName = "Product", FieldHeader = "Product", TotalHeader = "Total" });
            pivotSetting.PivotColumns.Add(new PivotItem { FieldMappingName = "Country", FieldHeader = "Country", TotalHeader = "Total" });
            pivotSetting.PivotCalculations.Add(new PivotComputationInfo { CalculationName = "Amount", Description = "Amount", FieldHeader = "Amount", FieldName = "Amount", Format = "C", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.DoubleTotalSum });
            return pivotSetting;
        }
    }
    .....
    ..... // Initialize the datasourse
    .....
}

{% endhighlight %}

**Configuring Web Configuration File**

The services could be exposed through the properties, binding, contract and address by using an endpoint.

* Contract: This property indicates that the contract of the endpoint is exposing. Here you are referring to **IRelationalService** contract and hence it is **PivotGridDemo.IRelationalService**.
* Binding: In your application, you use webHttpBinding to post and receive the requests and responses between the client-end and the service.
* BehaviorConfiguration: This property contains the name of the behavior to be used in the endpoint

The endpointBehaviors are illustrated as follows

{% highlight xml %}

<system.serviceModel>
    ……
    ……
    <services>
    <service name="PivotGridDemo.RelationalService">
        <endpoint address="" behaviorConfiguration="PivotGridDemo.RelationalServiceAspNetAjaxBehavior"
        binding="webHttpBinding" contract="PivotGridDemo.IRelationalService" />
    </service>
    </services>
</system.serviceModel>

{% endhighlight %}

The endpointBehaviors contain all the behaviors for an endpoint. You can link each endpoint to the respective behavior only using this name property.

{% highlight xml %}

<system.serviceModel>
    <behaviors>
    <endpointBehaviors>
        <behavior name="PivotGridDemo.RelationalServiceAspNetAjaxBehavior">
        <enableWebScript />
        </behavior>
    </endpointBehaviors>
    </behaviors>
    ……
    ……
</system.serviceModel>

{% endhighlight %}

N> In this example, **"PivotGridDemo"** indicates the name and root namespace of the Web Application created in Visual Studio IDE and **"RelationalService"** indicates the name of the WCF service created.

Now, **PivotGrid** will be rendered with Sales Amount over a set of products across different customer geographic locations.

![](Getting-Started_images/relational.png)   


