---
layout: post
title: Save and Load Report | PivotGrid | ASP.NET | Syncfusion 
description: This document illustrates that how to save and load report to database in ASP.NET PivotGrid control 
platform: aspnet
control: PivotGrid
documentation: ug
---

# Save and load report

Allows you to save the current report of the pivot grid and render the control with the saved report later. You can save and load the report in the following two ways:

* Database
* Local storage

## Save report to database

By using the current report name, storage option, and url, you can save the current report of the pivot grid to the database.

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

The service method should be added to the WCF/WebAPI for storing the current report of the pivot grid to the database.

For WebAPI controller, the following method should be added:

{% highlight c# %}

[System.Web.Http.ActionName("SaveReport")]
[System.Web.Http.HttpPost]
public Dictionary<string, object> SaveReport(Dictionary<string, object> jsonResult)
{
    string mode = jsonResult["operationalMode"].ToString();
    bool isDuplicate = true;
    SqlCeConnection con = new SqlCeConnection() { ConnectionString = "Enter appropriate connection string to connect with database" };
    con.Open();
    SqlCeCommand cmd1 = null;
    foreach (DataRow row in GetDataTable().Rows)
    {
        if ((row.ItemArray[0] as string).Equals(jsonResult["reportName"].ToString()))
        {
            isDuplicate = false;
            cmd1 = new SqlCeCommand("update ReportsTable set Report=@Reports where ReportName like @ReportName", con);
        }
    }
    if (isDuplicate)
    {
        cmd1 = new SqlCeCommand("insert into ReportsTable Values(@ReportName,@Reports)", con);
    }
    cmd1.Parameters.Add("@ReportName", jsonResult["reportName"].ToString());
    if (mode == "serverMode")
        cmd1.Parameters.Add("@Reports", OLAPUTILS.Utils.GetReportStream(jsonResult["clientReports"].ToString()).ToArray());
    else if (mode == "clientMode")
        cmd1.Parameters.Add("@Reports", Encoding.UTF8.GetBytes(jsonResult["clientReports"].ToString()).ToArray());
    cmd1.ExecuteNonQuery();
    con.Close();
    return null;
}

{% endhighlight %}

For WCF service, the following method should be added:

{% highlight c# %}

public Dictionary<string, object> SaveReport(string reportName, string operationalMode, string olapReport, string clientReports)
{
    string mode = operationalMode;
    bool isDuplicate = true;
    SqlCeConnection con = new SqlCeConnection() { ConnectionString = "Enter appropriate connection string to connect with database" };
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
    //cmd1.Parameters.Add("@Reports", OLAPUTILS.Utils.GetReportStream(clientReports).ToArray());
    if (mode == "serverMode")
        cmd1.Parameters.Add("@Reports", OLAPUTILS.Utils.GetReportStream(clientReports).ToArray());
    else if (mode == "clientMode")
        cmd1.Parameters.Add("@Reports", Encoding.UTF8.GetBytes(clientReports).ToArray());
    cmd1.ExecuteNonQuery();
    con.Close();
    return null;
}

{% endhighlight %}

## Save report to local storage

To save the current report of the pivot grid to local storage, you can call the `saveReport` method in the pivot grid.

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


## Load report from database

By using the stored report name, database name and url, you can load the saved report of the pivot grid from the database.

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

Service methods should be added to the WCF/WebAPI for loading a stored report in the database.

### Relational

For WebAPI controller, the following method should be added:

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
    if (mode == "serverMode" && jsonResult.ContainsKey("clientReports"))
    {
        reports = jsonResult["clientReports"].ToString();
    }
    else
    {
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
                    reports = OLAPUTILS.Utils.CompressData(row.ItemArray[1] as byte[]);
                    break;
                }
            }
        }
    }
    if (reports != "")
    {
        report = htmlHelper.DeserializedReports(reports);
        htmlHelper.PivotReport = report;
        dictionary = htmlHelper.GetJsonData("loadOperation", ProductSales.GetSalesData(), "Load Report", jsonResult["reportName"].ToString());
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

For WCF service, the following method should be added:

{% highlight c# %}

public Dictionary<string, object> LoadReportFromDB(string reportName, string operationalMode, string olapReport, string clientReports)
{
    byte[] reportString = new byte[2 * 1024];
    PivotReport report = new PivotReport();
    var reports = "";
    string mode = operationalMode;
    Dictionary<string, object> dictionary = new Dictionary<string, object>();
    if (mode == "serverMode" && !string.IsNullOrEmpty(clientReports))
    {
        reports = clientReports;
    }
    else
    {
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
                    break;
                }
            }
        }
    }
    if (reports != "") {
        report = htmlHelper.DeserializedReports(reports);
        htmlHelper.PivotReport = report;
        dictionary = htmlHelper.GetJsonData("loadOperation", ProductSales.GetSalesData(), "Load Report", reportName);
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

For WebAPI controller, the following method should be added:

{% highlight c# %}

[System.Web.Http.ActionName("LoadReportFromDB")]
[System.Web.Http.HttpPost]
public Dictionary<string, object> LoadReportFromDB(Dictionary<string, object> jsonResult)
{
    string mode = jsonResult["operationalMode"].ToString();
    byte[] reportString = new byte[4 * 1024];
    var reports = "";
    Dictionary<string, object> dictionary = new Dictionary<string, object>();
    if (mode == "serverMode" && jsonResult.ContainsKey("clientReports"))
    {
        reports = jsonResult["clientReports"].ToString();
    }
    else
    {
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
                    reports = OLAPUTILS.Utils.CompressData(row.ItemArray[1] as byte[]);
                    break;
                }
            }
        }
    }
    if (reports != "")
    {
        OlapDataManager DataManager = new OlapDataManager(connectionString);
        dynamic customData = serializer.Deserialize<dynamic>(jsonResult["customObject"].ToString());
        var cultureIDInfo = new System.Globalization.CultureInfo(("en-US")).LCID;
        if (customData is Dictionary<string, object> && customData.ContainsKey("Language"))
        {
            cultureIDInfo = new System.Globalization.CultureInfo((customData["Language"])).LCID;
        }
        connectionString = connectionString.Replace("" + cultureIDInfoval + "", "" + cultureIDInfo + "");
        cultureIDInfoval = cultureIDInfo;
        DataManager.Culture = new System.Globalization.CultureInfo((cultureIDInfo));
        DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(reports));
        DataManager.OverrideDefaultFormatStrings = true;
        dictionary = htmlHelper.GetJsonData(jsonResult["action"].ToString(), DataManager, jsonResult["gridLayout"].ToString(), Convert.ToBoolean(jsonResult["enablePivotFieldList"].ToString()));
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

For WCF service, the following method should be added:

{% highlight c# %}

public Dictionary<string, object> LoadReportFromDB(string action, string layout, bool enablePivotFieldList, object customObject, string reportName, string operationalMode, string olapReport, string clientReports)
{
    string mode = operationalMode;
    var reports = "";
    byte[] reportString = new byte[4 * 1024];
    Dictionary<string, object> dictionary = new Dictionary<string, object>();
    if (mode == "serverMode" && !string.IsNullOrEmpty(clientReports))
    {
        reports = clientReports;
    }
    else
    {
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
                    reports = OLAPUTILS.Utils.CompressData(row.ItemArray[1] as byte[]);
                    break;
                }
            }
        }
    }
    if (reports != "")
    {
        OlapDataManager DataManager = new OlapDataManager(connectionString);
        dynamic customData = serializer.Deserialize<dynamic>(customObject.ToString());
        var cultureIDInfo = new System.Globalization.CultureInfo(("en-US")).LCID;
        if (customData is Dictionary<string, object> && customData.ContainsKey("Language"))
        {
            cultureIDInfo = new System.Globalization.CultureInfo((customData["Language"])).LCID;
        }
        connectionString = connectionString.Replace("" + cultureIDInfoval + "", "" + cultureIDInfo + "");
        cultureIDInfoval = cultureIDInfo;
        DataManager.Culture = new System.Globalization.CultureInfo((cultureIDInfo));
        DataManager.SetCurrentReport(OLAPUTILS.Utils.DeserializeOlapReport(reports));
        DataManager.OverrideDefaultFormatStrings = true;
        dictionary = htmlHelper.GetJsonData(action, DataManager, layout, enablePivotFieldList);
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

## Load report from local storage

To load a stored report of the pivot grid from the local storage, you can call the `loadReport` method in the pivot grid.

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

## Save and Load XML Report

I> This feature is applicable only for the relational datasource at Server Mode alone.

This feature allows you to save the current report of PivotGrid as XML and render the control with the saved XML report later.

N> The following dependency libraries should be added to your web application.

* Syncfusion.PivotAnalysis.Wpf
* Syncfusion.Grid.Wpf

### Save XML Report

By using the 'saveXMLReport' method, you can save the current report of PivotGrid as XML file.

{% highlight HTML %}

    <ej:PivotGrid ID="PivotGrid1" Url="/Relational" runat="server" ClientIDMode="Static"></ej:PivotGrid>
    <ej:Button runat="server" ClientSideOnClick="saveReport" Text="Save"></ej:Button>

    <script>

        function saveReport() {
            pGridObj = $('#PivotGrid1').data("ejPivotGrid");
            url = "/Relational/XmlExport";
            pGridObj.saveXMLReport("XML", url); // YOu can specify XML file name here
        }

    </script>

{% endhighlight %}

The service method should be added in WebAPI for exporting the current report as XML.

For **WebAPI controller**, the following method should be added:

N> The following namespaces should be added on the top of the main class in WebAPI controller file.

* using System.IO;
* using System.Xml;
* using System.Xml.Serialization;
* using Syncfusion.Windows.Controls.PivotGrid;

{% highlight c# %}

PivotGrid htmlHelper = new PivotGrid();

[System.Web.Http.ActionName("XmlExport")]
[System.Web.Http.HttpPost]
public void XmlExport()
{
    string clientReport = HttpContext.Current.Request.Form.GetValues(0)[0];
    string fileName = HttpContext.Current.Request.Form.GetValues(1)[0];
    htmlHelper.ExportToXml(clientReport, fileName, HttpContext.Current.Response);
}

{% endhighlight %}

### Load XML Report

You can load the XML report in PivotGrid by using the following methods.

{% highlight HTML %}

    <ej:PivotGrid ID="PivotGrid1" Url="/Relational" runat="server" ClientIDMode="Static"></ej:PivotGrid>

{% endhighlight %}

The service methods should be added in WebAPI for loading the stored XML report.

For **WebAPI controller**, the following methods should be added.

{% highlight c# %}

PivotGrid htmlHelper = new PivotGrid();
JavaScriptSerializer serializer = new JavaScriptSerializer();
Dictionary<string, bool> clientSideAPI = new Dictionary<string, bool>();
Syncfusion.Windows.Controls.PivotGrid.PivotGridSerializer xmlSerializer = new Syncfusion.Windows.Controls.PivotGrid.PivotGridSerializer();
string filePath = HttpContext.Current.Server.MapPath(".").Split(new string[] { "\\api" }, StringSplitOptions.None)[0] + "\\pivot.xml";

[System.Web.Http.ActionName("XmlImport")]
[System.Web.Http.HttpPost]
public Dictionary<string, object> XmlImport()
{
    Dictionary<string, object> dictionary = new Dictionary<string, object>();
    StreamReader stream = null;
    stream = new StreamReader(@"C:\\Users\\Desktop\\file.xml"); //here you can specify xml file path
    string xmlString = stream.ReadToEnd();
    XmlDocument doc = new XmlDocument();
    doc.LoadXml(xmlString);
    if (doc.DocumentElement.Name.ToString() == "PivotGridSerializer")
    {
        XmlSerializer GridSerializer = new XmlSerializer(typeof(PivotGridSerializer), new Type[] { typeof(DoubleTotalSummary), typeof(CountSummary), typeof(IntTotalSummary), typeof(DoubleAverageSummary), typeof(DoubleMaxSummary), typeof(DoubleMinSummary), typeof(DoubleStDevSummary), typeof(DoubleVarianceSummary), typeof(DecimalTotalSummary) });
        PivotGridSerializer PivotGridControl = new PivotGridSerializer();
        PivotReport pivotReport = new PivotReport();
        using (TextReader reader = new StringReader(xmlString))
        {
            if (doc.DocumentElement.Name.ToString() == "PivotGridSerializer")
                PivotGridControl = (PivotGridSerializer)GridSerializer.Deserialize(reader);

            htmlHelper.PivotReport = this.UpdateXMLReport(PivotGridControl, pivotReport, doc.DocumentElement.Name.ToString());

        }
    }
    else if (doc.DocumentElement.Name.ToString() == "PivotReport")
    {
        htmlHelper.ImportFromXml(xmlString);
    }
    var ser = serializer.Serialize(clientSideAPI);
    dictionary = htmlHelper.GetJsonData("xmlImport", ProductSales.GetSalesData(), ser, null);
    return dictionary;
}

private PivotReport UpdateXMLReport(PivotGridSerializer PivotGridControl, PivotReport pivotReport, string documentName)
{
    PivotReport report = new PivotReport();
    if (documentName == "PivotGridSerializer")
    {
        foreach (PivotItem item in PivotGridControl.PivotRows)
            report.PivotRows.Add(item);
        foreach (PivotItem item in PivotGridControl.PivotColumns)
            report.PivotColumns.Add(item);
        foreach (PivotComputationInfo item in PivotGridControl.PivotCalculations)
            report.PivotCalculations.Add(item);
        foreach (FilterExpression item in PivotGridControl.Filters)
        {
            item.DimensionName = (string.IsNullOrEmpty(item.DimensionName)) ? item.DimensionHeader : item.DimensionName;
            report.Filters.Add(item);
        }
        foreach (var item1 in report.PivotColumns)
        {
            var sortItem = PivotGridControl.GridSortCollection.Where(i => i.FieldMappingName == item1.FieldMappingName).FirstOrDefault();
            if (sortItem != null && sortItem.IsDescSort)
            {
                item1.Comparer = new Syncfusion.JavaScript.ReverseOrderComparer();
            }
        }
        foreach (var item1 in report.PivotRows)
        {
            var sortItem = PivotGridControl.GridSortCollection.Where(i => i.FieldMappingName == item1.FieldMappingName).FirstOrDefault();
            if (sortItem != null && sortItem.IsDescSort)
            {
                item1.Comparer = new Syncfusion.JavaScript.ReverseOrderComparer();
            }
        }
        clientSideAPI.Add("ShowGroupingBar", PivotGridControl.ShowGroupingBar);
        clientSideAPI.Add("ShowGrandTotals", PivotGridControl.ShowGrandTotals);
        clientSideAPI.Add("AllowResizeColumns", PivotGridControl.AllowResizeColumns);
        clientSideAPI.Add("ResizePivotGridToFit", PivotGridControl.ResizePivotGridToFit);
        clientSideAPI.Add("AllowSelection", PivotGridControl.AllowSelection);
        clientSideAPI.Add("DeferLayoutUpdate", PivotGridControl.DeferLayoutUpdate);
        clientSideAPI.Add("FreezeHeaders", PivotGridControl.FreezeHeaders);
        clientSideAPI.Add("ShowFieldList", PivotGridControl.ShowFieldList);
        clientSideAPI.Add("ShowSubTotals", PivotGridControl.ShowSubTotals);
    }
    return report;
}

[System.Web.Http.ActionName("InitializeGrid")]
[System.Web.Http.HttpPost]
public Dictionary<string, object> InitializeGrid(Dictionary<string, object> jsonResult)
{
    StreamReader stream = null;
    stream = new StreamReader(filePath); //here you can specify xml file path
    string xmlString = stream.ReadToEnd();
    XmlDocument doc = new XmlDocument();
    doc.LoadXml(xmlString);
    htmlHelper.ImportFromXml(xmlString);
    var ser = serializer.Serialize(clientSideAPI);
    dict = htmlHelper.GetJsonData("xmlImport", ProductSales.GetSalesData(), ser, null);
    return dict;
}

{% endhighlight %}