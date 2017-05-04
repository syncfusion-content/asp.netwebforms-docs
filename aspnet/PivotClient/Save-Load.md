---
layout: post
title: Save and Load Report | PivotClient | ASP.NET | Syncfusion 
description: save and load report
platform: aspnet
control: PivotClient
documentation: ug
---

# Save and load report

The save and load report allows you to save the current report collection of the pivot client and render the control when you loading the same.

You can save and load the report in two ways.

* Database
* Local storage

## Save report to database

You can store the report collection of the pivot client to database by using the [`SaveReport`] event in the pivot client control.

{% highlight html %}

<ej:PivotClient ID=" PivotClient1" runat="server">
    //...
    <ClientSideEvents SaveReport="saveReportSettings" />
</ej:PivotClient>

<script>
    function saveReportSettings(args) {
        if(args.saveReportSettings)
            return args.saveReportSetting.url = "../wcf/OlapService.svc";
    }
</script>

{% endhighlight %}

Service method should be added in WCF/WebAPI for storing the pivot client report collection in the database.

For WebAPI controller, the following method should be added:

{% highlight c# %}

[System.Web.Http.ActionName("SaveReportToDB")]
[System.Web.Http.HttpPost]
public Dictionary<string, object> SaveReportToDB(Dictionary<string, object> jsonResult)
{
    string operationalMode = jsonResult["operationalMode"].ToString(), analysisMode = jsonResult["analysisMode"].ToString(), reportName = string.Empty;
    bool isDuplicate = true;
    SqlCeConnection con = new SqlCeConnection() { ConnectionString = conStringforDB };
    con.Open();
    reportName = jsonResult["reportName"].ToString() + "##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower();
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
    if (operationalMode.ToLower() == "servermode" && analysisMode == "olap")
        cmd1.Parameters.Add("@Reports", OLAPUTILS.Utils.GetReportStream(jsonResult["clientReports"].ToString()).ToArray());
    else
        cmd1.Parameters.Add("@Reports", Encoding.UTF8.GetBytes(jsonResult["clientReports"].ToString()).ToArray());
    cmd1.ExecuteNonQuery();
    con.Close();
    return null;
}

{% endhighlight %}

For WCF controller, the following method should be added:

{% highlight c# %}

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
    if (operationalMode.ToLower() == "servermode" && analysisMode == "olap")
        cmd1.Parameters.Add("@Reports", OLAPUTILS.Utils.GetReportStream(clientReports).ToArray());
    else 
        cmd1.Parameters.Add("@Reports", Encoding.UTF8.GetBytes(clientReports).ToArray());
    cmd1.ExecuteNonQuery();
    con.Close();
    return null;
}

{% endhighlight %}

## Save report to local storage

You can store the report collection of the pivot client to local storage by setting the [`EnableLocalStorage`] property to true and by defining the [`SaveReport`] event of the pivot client.

{% highlight html %}

<ej:PivotClient ID=" PivotClient1" EnableLocalStorage="true" runat="server">
    //...
    <ClientSideEvents SaveReport="saveReportSettings" />
</ej:PivotClient>

<script>
function saveReportSettings(args) {
    var reportCollection = [];
    if ((localStorage.pivotClientRPTCollection != "" && !ej.isNullOrUndefined(localStorage.pivotClientRPTCollection))) {
        reportCollection = JSON.parse(localStorage.pivotClientRPTCollection);
    }
    if(args.saveReportSettings){
        reportCollection.push(({ reportName: args.saveReportSetting.reportName, reportCol: args.saveReportSetting.reportCollection }));
        localStorage.pivotClientRPTCollection = JSON.stringify(reportCollection);;
    }
}
</script>

{% endhighlight %}

## Load report from database

You can load the stored report collection of the pivot client from the database by using the [`FetchReport`]  and [`LoadReport`] events in the pivot client.

{% highlight html %}

<ej:PivotClient ID=" PivotClient1" runat="server">
    //...
    <ClientSideEvents LoadReport="reportSettings" FetchReport="reportSettings" />
</ej:PivotClient>

<script>
function reportSettings(args) {
    if (args.fetchReportSetting)
        return args.fetchReportSetting.url = "../wcf/OlapClientService.svc";
    else if (args.loadReportSetting)
        return args.loadReportSetting.url = "../wcf/OlapClientService.svc";
}
</script>

{% endhighlight %}

Service methods should be added in the WCF/WebAPI for storing the pivot client report collection in the database.

For WebAPI controller, the following methods should be added.

{% highlight c# %}

[System.Web.Http.ActionName("FetchReportListFromDB")]
[System.Web.Http.HttpPost]
public Dictionary<string, object> FetchReportListFromDB(Dictionary<string, object> jsonResult)
{
    string reportNames = string.Empty, currentRptName = string.Empty, operationalMode = jsonResult["operationalMode"].ToString(), analysisMode = jsonResult["analysisMode"].ToString();
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
    dictionary.Add("action", jsonResult["action"].ToString());
    return dictionary;
}

[System.Web.Http.ActionName("LoadReportFromDB")]
[System.Web.Http.HttpPost]
public Dictionary<string, object> LoadReportFromDB(Dictionary<string, object> jsonResult)
{
    PivotReport report = new PivotReport();
    string operationalMode = jsonResult["operationalMode"].ToString(), analysisMode = jsonResult["analysisMode"].ToString();
    Dictionary<string, object> dictionary = new Dictionary<string, object>();
    string currentRptName = string.Empty;
    foreach (DataRow row in GetDataTable().Rows)
    {
        currentRptName = (row.ItemArray[0] as string).Replace("##" + operationalMode.ToLower() + "#>>#" + analysisMode.ToLower(), "");
        if (currentRptName.Equals(jsonResult["reportName"].ToString()))
        {
            if (operationalMode.ToLower() == "servermode" && analysisMode == "olap")
            {
                var reportString = "";
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                reportString = OLAPUTILS.Utils.CompressData(row.ItemArray[1] as byte[]);
                DataManager.Reports = olapClientHelper.DeserializedReports(reportString);
                DataManager.SetCurrentReport(DataManager.Reports[0]);
                return olapClientHelper.GetJsonData("toolbarOperation", DataManager, "Load Report", jsonResult["reportName"].ToString());
            }
            else
            {
                byte[] reportString = new byte[2 * 1024];
                reportString = (row.ItemArray[1] as byte[]);
                if (analysisMode.ToLower() == "pivot" && operationalMode.ToLower() == "servermode")
                    dictionary = olapClientHelper.GetJsonData("LoadReport", ProductSales.GetSalesData(), Encoding.UTF8.GetString(reportString));
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

{% endhighlight %}

For WCF controller, the following methods should be added.

{% highlight c# %}

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
                OlapDataManager DataManager = new OlapDataManager(connectionString);
                reportString = OLAPUTILS.Utils.CompressData(row.ItemArray[1] as byte[]);
                DataManager.Reports = olapClientHelper.DeserializedReports(reportString);
                DataManager.SetCurrentReport(DataManager.Reports[0]);
                return olapClientHelper.GetJsonData("toolbarOperation", DataManager, "Load Report", reportName);
            }
            else
            {
                byte[] reportString = new byte[2 * 1024];
                reportString = (row.ItemArray[1] as byte[]);
                if (analysisMode.ToLower() == "pivot" && operationalMode.ToLower() == "servermode")
                    dictionary = olapClientHelper.GetJsonData("LoadReport", ProductSales.GetSalesData(), Encoding.UTF8.GetString(reportString));
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

{% endhighlight %}

## Load report from local storage

You can load the stored report collection of the pivot client from the local storage by setting the [`EnableLocalStorage`] property to true and using the [`LoadReport`] and [`FetchReport`] events in the pivot client.

{% highlight html %}

<ej:PivotClient ID=" PivotClient1" EnableLocalStorage="true" runat="server">
    //...
    <ClientSideEvents LoadReport="reportSettings" FetchReport="reportSettings" />
</ej:PivotClient>

<script>
function reportSettings(args) {
    var reportCollection = [];
    if ((localStorage.pivotClientRPTCollection != "" && !ej.isNullOrUndefined(localStorage.pivotClientRPTCollection))) {
        reportCollection = JSON.parse(localStorage.pivotClientRPTCollection);
    }
    if (args.fetchReportSetting) 
        args.fetchReportSetting.reportList = $.map(reportCollection, function (item, index) { return item.reportName; }).join("__");
    else if (args.loadReportSetting) 
        args.loadReportSetting.reportCollection = $.map(reportCollection, function (item, index) { if (item.reportName == args.loadReportSetting.selectedReport) return item.reportCol; });
}
</script>

{% endhighlight %}