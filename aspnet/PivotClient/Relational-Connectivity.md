---
layout: post
title: Relational Connectivity | PivotClient | ASP.NET | Syncfusion
description: relational connectivity
platform: aspnet
control: PivotClient
documentation: ug
---

# Data binding

## Binding pivot client to collection

This section demonstrates binding a collection to the pivot client control as data source. For more information on this pivot client, refer the following links:

If you are using the WebAPI controller, refer the "Datasource Initialization" section under the following [link](https://help.syncfusion.com/aspnet/pivotclient/relational-getting-started#creating-a-simple-application-with-pivotclient-and-relational-datasource-server-mode).

If you are using the WCF Service, refer the "Datasource Initialization" section below:

## WCF
**Adding a WCF Service**

To add a WCF service in an existing web application, right-click the project in the solution explorer and select **Add > New Item**. In the **Add New Item** window, select the WCF Service and name it `RelationalService.svc`, and then click Add.

Now, the WCF service is added to the application that comprises the following files. The utilization of these files is explained in the immediate sections.

* RelationalService.svc
* RelationalService.svc.cs
* IRelationalService.cs

**Configuring WCF service class**

Remove the **“DoWork”** method present in both `RelationalService.svc.cs` and `IRelationalService.cs` files. Next, add **“AspNetCompatibilityRequirements”** attribute on top of the main class present in the `RelationalService.svc.cs` file and set **“RequirementsMode”** value to **“Allowed”**.

{% highlight c# %}

namespace PivotClientDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class RelationalService : IRelationalService
    {

    }
}

{% endhighlight %}

**List of dependency libraries**

You can add the below-mentioned dependency libraries to your web application. These libraries can be found in the GAC (Global Assembly Cache).

To add them to your web application, right-click **References** in the solution explorer and select **Add Reference**. In the **Reference Manager** dialog, under **Assemblies > Extension**, the following Syncfusion libraries are found.

N> If you have installed any version of Essential Studio, then the location of Syncfusion libraries is [system drive:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Assemblies].

* Syncfusion.Compression.Base
* Syncfusion.Linq.Base
* Syncfusion.Olap.Base
* Syncfusion.PivotAnalysis.Base
* System.Data.SqlServerCe (Version: 4.0.0.0)
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

using Syncfusion.JavaScript;
using Syncfusion.PivotAnalysis.Base;
using System;
using System.Collections.Generic;
using System.Data;
using System.ServiceModel.Activation;
using System.Data.SqlServerCe;
using Syncfusion.Olap.Manager;
using System.Linq;
using System.Net.Http;
using System.Text;
using System.Web;
using System.Web.Script.Serialization;
using OLAPUTILS = Syncfusion.JavaScript.Olap;

namespace PivotClientDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class RelationalService : IRelationalService
    {

    }
}

{% endhighlight %}


**Data source initialization**

A simple collection is provided as a data source for the pivot client in this demo section. This data source is placed in a separate class named "ProductSales" in the **RelationalService.svc.cs** file. Please find the code sample below:

{% highlight c# %}

namespace PivotClientDemo
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

First, declare the service methods in the **IRelationalService** interface, find in the `IRelationalService.cs` file which was created while adding the WCF service to the application.

{% highlight c# %}

namespace PivotClientDemo
{
    [ServiceContract]
    public interface IRelationalService
    {
        [OperationContract]
        Dictionary<string, object> InitializeClient(string action);
        [OperationContract]
        Dictionary<string, object> FetchMembers(string action, string currentReport, string customObject, string headerTag);
        [OperationContract]
        Dictionary<string, object> DrillChart(string action, string drilledSeries);
        [OperationContract]
        Dictionary<string, object> Filtering(string action, string filterParams, string currentReport, string customObject);
        [OperationContract]
        Dictionary<string, object> NodeDropped(string action, string args);
        [OperationContract]
        Dictionary<string, object> ToolbarOperations(string action, string args);
        [OperationContract]
        Dictionary<string, object> SaveReportToDB(string reportName, string operationalMode, string analysisMode, string olapReport, string clientReports);
        [OperationContract]
        Dictionary<string, object> RemoveReportFromDB(string reportName, string operationalMode, string analysisMode);
        [OperationContract]
        Dictionary<string, object> RenameReportInDB(string selectedReport, string renameReport, string operationalMode, string analysisMode);
        [OperationContract]
        Dictionary<string, object> LoadReportFromDB(string reportName, string operationalMode, string analysisMode, string olapReport, string clientReports);
        [OperationContract]
        Dictionary<string, object> FetchReportListFromDB(string action, string operationalMode, string analysisMode);
        [OperationContract]
        void Export(System.IO.Stream stream);
    }
}

{% endhighlight %}

Then, elaborate the service methods in the main class that is found in the `RelationalService.svc.cs` file.

{% highlight c# %}

namespace PivotClientDemo
{
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]
    public class RelationalService : IRelationalService
    {
        PivotClient pivotClient = new PivotClient();
        PivotChart pivotChart = new PivotChart();
        PivotGrid pivotGrid = new PivotGrid();
        string conStringforDB = "";//Enter appropriate connection string to connect database for saving and loading operation of reports
        JavaScriptSerializer serializer = new JavaScriptSerializer();

        public Dictionary<string, object> InitializeClient(string action)
        {
            this.BindData();
            return pivotClient.GetJsonData(action, ProductSales.GetSalesData(), null);
        }

        public Dictionary<string, object> FetchMembers(string action, string currentReport, string customObject, string headerTag)
        {
            pivotClient.PopulateData(currentReport);
            return pivotClient.GetJsonData(action, ProductSales.GetSalesData(), headerTag);
        }

        public Dictionary<string, object> DrillChart(string action, string drilledSeries)
        {
            this.BindData();
            this.pivotChart.PivotEngine.PivotRows = this.pivotClient.PivotReport.PivotRows;
            this.pivotChart.PivotEngine.PivotColumns = this.pivotClient.PivotReport.PivotColumns;
            this.pivotChart.PivotEngine.PivotCalculations = this.pivotClient.PivotReport.PivotCalculations;
            return pivotChart.GetJsonData(action, ProductSales.GetSalesData(), drilledSeries);
        }

        public Dictionary<string, object> Filtering(string action, string filterParams, string currentReport, string customObject)
        {
            pivotClient.PopulateData(currentReport);
            return pivotClient.GetJsonData(action, ProductSales.GetSalesData(), filterParams);
        }

        public Dictionary<string, object> NodeDropped(string action, string args)
        {
            return pivotClient.GetJsonData(action, ProductSales.GetSalesData(), args);
        }

        public Dictionary<string, object> ToolbarOperations(string action, string args)
        {
            return pivotClient.GetJsonData(action, ProductSales.GetSalesData(), args);
        }
        public Dictionary<string, object> SaveReportToDB(string reportName, string operationalMode, string analysisMode, string olapReport, string clientReports)
        {
            reportName = reportName + "##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower();
            bool isDuplicate = true;
            SqlCeConnection con = new SqlCeConnection() { ConnectionString = conStringforDB };
            con.Open();
            SqlCeCommand cmd1 = null;
            foreach (DataRow row in GetDataTable().Rows)
            {
                if ((row.ItemArray[0] as string).Equals(reportName))
                {
                    isDuplicate = false;
                    cmd1 = new SqlCeCommand("update ReportsTable set Report=@Reports where ReportName like @ReportName", con);
                }
            }
            if (isDuplicate)
            {
                cmd1 = new SqlCeCommand("insert into ReportsTable Values(@ReportName,@Reports)", con);
            }
            cmd1.Parameters.Add("@ReportName", reportName);
            cmd1.Parameters.Add("@Reports", Encoding.UTF8.GetBytes(clientReports).ToArray());
            cmd1.ExecuteNonQuery();
            con.Close();
            Dictionary<string, object> dictionary = new Dictionary<string, object>();
            dictionary.Add("CurrentAction", "Save");
            return dictionary;
        }

        public Dictionary<string, object> RemoveReportFromDB(string reportName, string operationalMode, string analysisMode)
        {
            SqlCeConnection con = new SqlCeConnection() { ConnectionString = conStringforDB };
            con.Open();
            reportName = reportName + "##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower();
            SqlCeCommand cmd1 = null;
            foreach (DataRow row in GetDataTable().Rows)
            {
                if ((row.ItemArray[0] as string).Equals(reportName))
                {
                    cmd1 = new SqlCeCommand("DELETE FROM ReportsTable WHERE ReportName LIKE '%" + reportName + "%'", con);
                }
            }
            cmd1.ExecuteNonQuery();
            con.Close();
            Dictionary<string, object> dictionary = new Dictionary<string, object>();
            dictionary.Add("CurrentAction", "Remove");
            return dictionary;
        }

        public Dictionary<string, object> RenameReportInDB(string selectedReport, string renameReport, string operationalMode, string analysisMode)
        {
            SqlCeConnection con = new SqlCeConnection() { ConnectionString = conStringforDB };
            con.Open();
            selectedReport = selectedReport + "##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower();
            renameReport = renameReport + "##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower();
            SqlCeCommand cmd1 = null;
            foreach (DataRow row in GetDataTable().Rows)
            {
                if ((row.ItemArray[0] as string).Equals(selectedReport))
                {
                    cmd1 = new SqlCeCommand("update ReportsTable set ReportName=@RenameReport where ReportName like '%" + selectedReport + "%'", con);
                }
            }
            cmd1.Parameters.Add("@RenameReport", renameReport);
            cmd1.ExecuteNonQuery();
            con.Close();
            Dictionary<string, object> dictionary = new Dictionary<string, object>();
            dictionary.Add("CurrentAction", "Rename");
            return dictionary;
        }

        public Dictionary<string, object> FetchReportListFromDB(string action, string operationalMode, string analysisMode)
        {
            string reportNames = string.Empty;
            string currentRptName = string.Empty;
            foreach (System.Data.DataRow row in GetDataTable().Rows)
            {
                currentRptName = (row.ItemArray[0] as string);
                if (currentRptName.IndexOf("##" + operationalMode + "#>>#" + analysisMode) >= 0)
                {
                    currentRptName = currentRptName.Replace("##" + operationalMode + "#>>#" + analysisMode, "");
                    reportNames = reportNames == "" ? currentRptName : reportNames + "__" + currentRptName;
                }
            }
            Dictionary<string, object> dictionary = new Dictionary<string, object>();
            dictionary.Add("ReportNameList", reportNames);
            dictionary.Add("action", action);
            return dictionary;
        }

        public Dictionary<string, object> LoadReportFromDB(string reportName, string operationalMode, string analysisMode, string olapReport, string clientReports)
        {
            PivotReport report = new PivotReport();
            Dictionary<string, object> dictionary = new Dictionary<string, object>();
            string currentRptName = string.Empty;
            foreach (DataRow row in GetDataTable().Rows)
            {
                currentRptName = (row.ItemArray[0] as string).Replace("##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower(), "");
                if (currentRptName.Equals(reportName))
                {
                    if (operationalMode.ToLower() == "servermode" && analysisMode == "olap")
                    {
                        var reportString = "";
                        OlapDataManager DataManager = new OlapDataManager();
                        reportString = OLAPUTILS.Utils.CompressData(row.ItemArray[1] as byte[]);
                        DataManager.Reports = pivotClient.DeserializedReports(reportString);
                        DataManager.SetCurrentReport(DataManager.Reports[0]);
                        return pivotClient.GetJsonData("toolbarOperation", DataManager, "Load Report", reportName);
                    }
                    else
                    {
                        byte[] reportString = new byte[2 * 1024];
                        reportString = (row.ItemArray[1] as byte[]);
                        if (analysisMode.ToLower() == "pivot" && operationalMode.ToLower() == "servermode")
                            dictionary = pivotClient.GetJsonData("LoadReport", ProductSales.GetSalesData(), Encoding.UTF8.GetString(reportString));
                        else
                            dictionary.Add("report", Encoding.UTF8.GetString(reportString));
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
        public void Export(System.IO.Stream stream)
        {
            System.IO.StreamReader sReader = new System.IO.StreamReader(stream);
            string args = System.Web.HttpContext.Current.Server.UrlDecode(sReader.ReadToEnd()).Remove(0, 5);
            Dictionary<string, string> gridParams = serializer.Deserialize<Dictionary<string, string>>(args);
            pivotClient.PopulateData(gridParams["currentReport"]);
            string fileName = "Sample";
            pivotClient.ExportPivotClient(ProductSales.GetSalesData(), args, fileName, System.Web.HttpContext.Current.Response);
        }

        private void BindData()
        {
            this.pivotClient.PivotReport.PivotRows.Add(new PivotItem { FieldMappingName = "Country", FieldHeader = "Country", TotalHeader = "Total" });
            this.pivotClient.PivotReport.PivotColumns.Add(new PivotItem { FieldMappingName = "Product", FieldHeader = "Product", TotalHeader = "Total" });
            this.pivotClient.PivotReport.PivotCalculations.Add(new PivotComputationInfo { CalculationName = "Amount", Description = "Amount", FieldHeader = "Amount", FieldName = "Amount", Format = "C", SummaryType = Syncfusion.PivotAnalysis.Base.SummaryType.DoubleTotalSum });
        }
    }
    .....
    ..... // Initialize the datasource
    .....
}

{% endhighlight %}

**Configuring web configuration file**

The services can be exposed through the properties such as binding, contract, and address by using an endpoint.

* Contract: This property indicates that the contract of the endpoint is exposed. Refer to the **IRelationalService** contract, and it is written as **PivotClientDemo.IRelationalService**.
* Binding: In your application, you can use "webHttpBinding" to post and receive requests and responses between the client-end and the service.
* BehaviorConfiguration: This property contains the name of the behavior to be used in the endpoint.

The endpointBehaviors are illustrated as follows:

{% highlight xml %}

<system.serviceModel>
    ……
    ……
    <services>
    <service name="PivotClientDemo.RelationalService">
        <endpoint address="" behaviorConfiguration="PivotClientDemo.RelationalServiceAspNetAjaxBehavior"
        binding="webHttpBinding" contract="PivotClientDemo.IRelationalService" />
    </service>
    </services>
</system.serviceModel>

{% endhighlight %}

The endpointBehaviors contain all behaviors for an endpoint. You can link each endpoint to the respective behavior only by using the name property.

{% highlight xml %}

<system.serviceModel>
    <behaviors>
    <endpointBehaviors>
        <behavior name="PivotClientDemo.RelationalServiceAspNetAjaxBehavior">
        <enableWebScript />
        </behavior>
    </endpointBehaviors>
    </behaviors>
……
……
</system.serviceModel>

{% endhighlight %}

N> In this example, the **"PivotClientDemo"** indicates the name and root namespace of the web application created in the Visual Studio IDE, and **"RelationalService"** indicates the name of the created WCF service.

Now, the **pivot client** is rendered with pivot chart and pivot grid with "Country" field in the row, "Product" field in the column, and "Amount" field in the value section.

![ASP NET pivot client control with relational wcf](Getting-Started_images/relaionalwebapi.png)


