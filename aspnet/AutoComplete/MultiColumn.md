---
layout: post
title: Multiple Columns | AutoComplete | ASP.NET Webforms | Syncfusion
description: multiple columns
platform: aspnet
control: AutoComplete
documentation: ug
---

# Multiple Columns

The Autocomplete allows list of data to be displayed in several columns and column collection can be defined and customized through the **MultiColumnSettings** property.

In AutoComplete Multiple Column search is based on **searchColumnIndices** property which allows user to search text for any number of fields in the suggestion list without modifying the selected text format.

N> if we use **searchColumnIndices** as “[0,1,2]” means search based on 0, 1 and 2 columns data alone.

In AutoComplete Multiple Column searched value is updated to autocomplete input box based on **StringFormat** property which specifies values to updated.

N> **StringFormat** as “{0} ({1}) ({2})” means search based on 0, 1 and 2 columns data.

<table><tr><th>Name</th><th>Description</th></tr>
<tr><td>Enable</td><td>Allow list of data to be displayed in several columns.</td></tr>
<tr><td>ShowHeader</td><td>Allow header text to be displayed in corresponding columns.</td></tr>
<tr><td>StringFormat</td><td>Displayed selected value and autocomplete search based on mentioned column value specified in that format.</td></tr>
<tr><td>Columns</td><td>Field and Header Text collections can be defined and customized through this field.</td></tr>
<tr><td>Field</td><td>Get or set a value that indicates to display the columns in the autocomplete mapping with column name of the dataSource.</td></tr>
<tr><td>HeaderText</td><td>Get or set a value that indicates to display the title of that particular column.</td></tr></table>


## Configuring Multiple Columns

The following steps explain the configuration of the multiple columns for an AutoComplete textbox.

In the design page, define the AutoComplete control and configure its **MultiColumnSettings** property accordingly.


{% highlight html %}

<%--Refer the ObjectDataSource binding for DataBinding to this code snippet--%>

Add the below code in corresponding code behind. 
  <%--this.AutoCompleteBelmt.MultiColumnSettings.SearchColumnIndices = new List<int> { 0,1,2 };--%>

    <div style="width: 600px">

    <div style="display:inline-block; float:left; margin-right:25px">

    <span style="display:block; margin-bottom:12px">Using Delimiter</span>    
    <ej:Autocomplete ID="AutoCompleteBelmt" runat="server" DataSourceID="ObjectDataSource1" 

    <MultiColumnSettings Enable="true" ShowHeader="true" StringFormat="{0}"   >
    <Columns>
    <ej:Columns Field="ID" HeaderText="ID" />
    <ej:Columns Field="Text" HeaderText="Text" />
    <ej:Columns Field="Catagory" HeaderText="Catagory" />
    </Columns>
    </MultiColumnSettings> 
    </div>

    </div>

{% endhighlight %}



The following screenshot is the output for AutoComplete control with configured multiple columns.

![](multicolumn_images/multicolumn_img1.png)

