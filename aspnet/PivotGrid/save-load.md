---
layout: post
title: Save and Load Report | PivotGrid | ASP.NET | Syncfusion 
description: save and load report
platform: aspnet
control: PivotGrid
documentation: ug
---

# Save and Load Report

Allows you to save the current report of PivotGrid and render the control with the saved report later. We can save and load the report in two ways:

* Database
* Local Storage

## Save Report to Database

By using current report name, storage option and url, we can save the current report of PivotGrid to database.  

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    //...
</ej:PivotGrid>
<ej:Button ClientSideOnClick="saveToDB" runat="server" Text="save To DB"></ej:Button>

<script>
    function saveToDB(){
        url = "../RelationalService",
        name = "report",
        storage = "db",
        pGridObj.saveReport(name, storage, url);
    }
</script>

{% endhighlight %}

Service method needs to be added in WCF/WebAPI for storing current report of PivotGrid to database.

For WebAPI controller, the below method needs to be added.

{% highlight c# %}

[System.Web.Http.ActionName("SaveReport")]
[System.Web.Http.HttpPost]
public Dictionary<string, object> SaveReport(Dictionary<string, object> jsonResult)
{
    string mode = jsonResult["operationalMode"].ToString();
    SqlCeConnection con = new SqlCeConnection() { ConnectionString = "Enter appropriate connection string to connect with database" };
    con.Open();
    SqlCeCommand cmd1 = new SqlCeCommand("insert into ReportsTable Values(@ReportName,@Reports)", con);
    cmd1.Parameters.Add("@ReportName", jsonResult["reportName"].ToString());
    if (mode == "serverMode")
        cmd1.Parameters.Add("@Reports", Syncfusion.JavaScript.Olap.Utils.GetReportStream(jsonResult["clientReports"].ToString()).ToArray());
    else if (mode == "clientMode")
        cmd1.Parameters.Add("@Reports", Encoding.UTF8.GetBytes(jsonResult["clientReports"].ToString()).ToArray());
    cmd1.ExecuteNonQuery();
    con.Close();
    return null;
}

{% endhighlight %}

For WCF service, the below method needs to be added.

{% highlight c# %}

public Dictionary<string, object> SaveReport(string reportName, string operationalMode, string olapReport, string clientReports)
{
    string mode = operationalMode;
    SqlCeConnection con = new SqlCeConnection() { ConnectionString = "Enter appropriate connection string to connect with database" };
    con.Open();
    SqlCeCommand cmd1 = new SqlCeCommand("insert into ReportsTable Values(@ReportName,@Reports)", con);
    cmd1.Parameters.Add("@ReportName", reportName);
    //cmd1.Parameters.Add("@Reports", Syncfusion.JavaScript.Olap.Utils.GetReportStream(clientReports).ToArray());
    if (mode == "serverMode")
        cmd1.Parameters.Add("@Reports", Syncfusion.JavaScript.Olap.Utils.GetReportStream(clientReports).ToArray());
    else if (mode == "clientMode")
        cmd1.Parameters.Add("@Reports", Encoding.UTF8.GetBytes(clientReports).ToArray());
    cmd1.ExecuteNonQuery();
    con.Close();
    return null;
}

{% endhighlight %}

## Save Report to Local Storage

To save the current report of PivotGrid to local storage, we need to call the `SaveReport` method in PivotGrid.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    //...
    <ClientSideEvents SaveReport = "saveToLocal" />
</ej:PivotGrid>
<ej:Button ClientSideOnClick="saveLocal" runat="server" Text="Save"></ej:Button>
<script>
    function saveLocal(){
        url = "",
        name = "report",
        storage = "local",
        pGridObj.saveReport(name, storage, url);
    }        
    function saveToLocal(args){
        localStorage.setItem("report", JSON.stringify(args.report));
    }
</script>

{% endhighlight %}


## Load Report from Database

By using the stored report name, database name and url, we can load the saved report of PivotGrid from database.  

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    //...
</ej:PivotGrid>
<ej:Button ClientSideOnClick="loadDB" runat="server" Text="Load DB"></ej:Button>

<script>
    function loadDB(){
        url = "../RelationalService",
        name = "report",
        storage = "db",
        pGridObj.loadReport(name, storage, url);
    }
</script>

{% endhighlight %}

Service methods need to be added in WCF/WebAPI for loading a stored report in database.

### Relational

For WebAPI controller, the below methods need to be added.

{% highlight c# %}

[System.Web.Http.ActionName("LoadReportFromDB")]
[System.Web.Http.HttpPost]
public Dictionary<string, object> LoadReportFromDB(Dictionary<string, object> jsonResult)
{
    byte[] reportString = new byte[2 * 1024];
    PivotReport report = new PivotReport();
    var reports = "";
    string mode = jsonResult["operationalMode"].ToString();
    Dictionary<string, object> dictionary = new Dictionary<string, object>();
    foreach (DataRow row in GetDataTable().Rows)
    {
        if ((row.ItemArray[0] as string).Equals(jsonResult["reportName"].ToString()))
        {
            if (mode == "clientMode")
            {
                reportString = (row.ItemArray[1] as byte[]);
                dictionary.Add("report", Encoding.UTF8.GetString(reportString));
                break;
            }
            else if (mode == "serverMode")
            {
                reports = Syncfusion.JavaScript.Olap.Utils.CompressData(row.ItemArray[1] as byte[]);
                report = htmlHelper.DeserializedReports(reports);
                htmlHelper.PivotReport = report;
                dictionary = htmlHelper.GetJsonData("loadOperation", ProductSales.GetSalesData(), "Load Report", jsonResult["reportName"].ToString());
                break;
            }
        }
    }
    return dictionary;
}


private DataTable GetDataTable()
{
    SqlCeConnection con = new SqlCeConnection() { ConnectionString = "Enter appropriate connection string to connect with database" };
    con.Open();
    DataSet dSet = new DataSet();
    new SqlCeDataAdapter("Select * from ReportsTable", con).Fill(dSet);
    con.Close();
    return dSet.Tables[0];
}

{% endhighlight %}

For WCF service, the below methods need to be added.

{% highlight c# %}

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
                reports = Syncfusion.JavaScript.Olap.Utils.CompressData(row.ItemArray[1] as byte[]);
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
    SqlCeConnection con = new SqlCeConnection() { ConnectionString = "Enter appropriate connection string to connect with database" };
    con.Open();
    DataSet dSet = new DataSet();
    new SqlCeDataAdapter("Select * from ReportsTable", con).Fill(dSet);
    con.Close();
    return dSet.Tables[0];
}

{% endhighlight %}

### OLAP

For WebAPI controller, the below methods need to be added.

{% highlight c# %}

[System.Web.Http.ActionName("LoadReportFromDB")]
[System.Web.Http.HttpPost]
public Dictionary<string, object> LoadReportFromDB(Dictionary<string, object> jsonResult)
{
    string mode = jsonResult["operationalMode"].ToString();
    byte[] reportString = new byte[4 * 1024];
    Dictionary<string, object> dictionary = new Dictionary<string, object>();
    foreach (DataRow row in GetDataTable().Rows)
    {
        if ((row.ItemArray[0] as string).Equals(jsonResult["reportName"].ToString()))
        {
            if (mode == "clientMode")
            {
                reportString = row.ItemArray[1] as byte[];
                dictionary.Add("report", Encoding.UTF8.GetString(reportString));
                break;
            }
            else if (mode == "serverMode")
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                var reports = "";
                if ((row.ItemArray[0] as string).Equals(jsonResult["reportName"].ToString()))
                {
                    reports = Syncfusion.JavaScript.Olap.Utils.CompressData(row.ItemArray[1] as byte[]);
                }
                DataManager.SetCurrentReport(Utils.DeserializeOlapReport(reports));
                dictionary = htmlHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["gridLayout"].ToString(), Convert.ToBoolean(jsonResult["enablePivotFieldList"].ToString()));
            }
        }
    }
    return dictionary;
}

private DataTable GetDataTable()
{
    SqlCeConnection con = new SqlCeConnection() { ConnectionString = "Enter appropriate connection string to connect with database" };
    con.Open();
    DataSet dSet = new DataSet();
    new SqlCeDataAdapter("Select * from ReportsTable", con).Fill(dSet);
    con.Close();
    return dSet.Tables[0];
}

{% endhighlight %}

For WCF service, the below methods need to be added.

{% highlight c# %}

public Dictionary<string, object> LoadReportFromDB(string action, string layout, bool enablePivotFieldList, object customObject, string reportName, string operationalMode, string olapReport, string clientReports)
{
    string mode = operationalMode;
    byte[] reportString = new byte[4 * 1024];
    Dictionary<string, object> dictionary = new Dictionary<string, object>();
    foreach (DataRow row in GetDataTable().Rows)
    {
        if ((row.ItemArray[0] as string).Equals(reportName))
        {
            if (mode == "clientMode")
            {
                reportString = row.ItemArray[1] as byte[];
                dictionary.Add("report", Encoding.UTF8.GetString(reportString));
                break;
            }
            else if (mode == "serverMode")
            {
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                var reports = "";
                if ((row.ItemArray[0] as string).Equals(reportName))
                {
                    reports = Syncfusion.JavaScript.Olap.Utils.CompressData(row.ItemArray[1] as byte[]);
                }
                DataManager.SetCurrentReport(Utils.DeserializeOlapReport(reports));
                dictionary = htmlHelper.GetJsonData(action, DataManager, layout, enablePivotFieldList);
            }
        }
    }
    return dictionary;
}

private DataTable GetDataTable()
{
    SqlCeConnection con = new SqlCeConnection() { ConnectionString = "Enter appropriate connection string to connect with database" };
    con.Open();
    DataSet dSet = new DataSet();
    new SqlCeDataAdapter("Select * from ReportsTable", con).Fill(dSet);
    con.Close();
    return dSet.Tables[0];
}

{% endhighlight %}

## Load Report from Local Storage

To load a stored report of PivotGrid from local storage, we need to call the `LoadReport` method in PivotGrid.

{% highlight html %}

<ej:PivotGrid ID="PivotGrid1" runat="server">
    //...
    <ClientSideEvents LoadReport = "loadFromLocal" />
</ej:PivotGrid>
<ej:Button ClientSideOnClick="loadReport" runat="server" Text="Load"></ej:Button>

<script>
    function loadReport(){
        url = "",
        name = "report",
        storage = "local",
        pGridObj.loadReport(name, storage, url);
    }        
    function loadFromLocal(args){
        args.targetControl.model.dataSource = JSON.parse(localStorage.getItem("report"));
    }
</script>

{% endhighlight %}