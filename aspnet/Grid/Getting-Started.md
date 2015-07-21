---
layout: post
title: Getting-Started
description: getting started
platform: aspnet
control: Grid
documentation: ug
---

# Getting Started

This section explains briefly about how to create a Grid in your application with ASP.NET.

## Create your first Grid in ASP.NET

You can create a Grid with a highly customizable look and feel. You can use Grid control to generate complex, grid-based reports, with rich formatting. In the following example, you can take a look at how the transaction of a product is managed, analysis of a particular sale using filtering and grouping feature. This section describes how you can add a group, filter and page sales products.



{ ![](Getting-Started_images/Getting-Started_img1.png) | markdownify }
{:.image }


1. Create a Syncfusion ASP.NET Web form application.
2.  Add a Grid in the Index.aspx page. 



{ ![](Getting-Started_images/Getting-Started_img2.png) | markdownify }
{:.image }


3. Configure the Grid control with SQL data source using smart tag.



{ ![](Getting-Started_images/Getting-Started_img3.png) | markdownify }
{:.image }




[ASPX]



&lt;ej:Grid ID="FlatGrid" runat="server" DataSourceID="SqlData"&gt;

&lt;/ej:Grid&gt;



&lt;asp:SqlDataSource runat="server" ID="SqlData" ConnectionString="&lt;%$ ConnectionStrings:SQLConnectionString %&gt;" SelectCommand="SELECT * FROM [Orders]">&lt;/asp:SqlDataSource&gt;





> { ![](Getting-Started_images/Getting-Started_img4.jpeg) | markdownify }
{:.image }
 _Note: Create a connection string in Web.config file using SQL database._

> __

[Web.config]



&lt;connectionStrings&gt;



     <add name="SQLConnectionString" connectionString="Data Source=

         (LocalDB)\V11.0;AttachDbFilename=|DataDirectory|

         \NORTHWND.MDF; Integrated Security=True"  

         providerName="System.Data.SqlClient" />



&lt;/connectionStrings&gt;





For more information about SQL data source configuration refer the following link: [http://msdn.microsoft.com/en-us/library/vstudio/w1kdt8w2(v=vs.100).aspx](http://msdn.microsoft.com/en-us/library/vstudio/w1kdt8w2(v=vs.100).aspx)

4. By Columns definition, the TextAlign property allows you to align the text of the columns. The Width property is used to define the width of the columns and the Format property allows you to format the particular column’s value.



{ ![](Getting-Started_images/Getting-Started_img5.png) | markdownify }
{:.image }




[ASPX]



&lt;ej:Grid ID="FlatGrid" runat="server" DataSourceID="SqlData" &gt;

    &lt;Columns&gt;

        <ej:Column Field="OrderID" HeaderText="Order ID" 

            IsPrimaryKey="True" TextAlign="Right" Width="75" />

        <ej:Column Field="CustomerID" HeaderText="Customer ID"

            Width="80" />

        <ej:Column Field="ShipName" HeaderText="Ship Name" 

            Width="100" />

        <ej:Column Field="ShipCity" HeaderText="Ship City" 

            Width="100" />

        <ej:Column Field="Freight" HeaderText="Freight" 

            TextAlign="Right" Width="80" Format="{0:C3}" /> 

    &lt;/Columns&gt;

&lt;/ej:Grid&gt;





The following screenshot displays a Grid with the sales data.



{ ![](Getting-Started_images/Getting-Started_img6.png) | markdownify }
{:.image }


Enable Paging

The Paging feature in Grid offers complete navigation support to easily switch between the pages, using the page bar available at the bottom of the Grid control. To enable paging, use AllowPaging property of Grid as follows.



[ASPX]



<ej:Grid ID="FlatGrid" runat="server" DataSourceID="SqlData"

AllowPaging="true">

    &lt;Columns&gt;

       <ej:Column Field="OrderID" HeaderText="Order ID" 

           IsPrimaryKey="True" TextAlign="Right" Width="75" />

       <ej:Column Field="CustomerID" HeaderText="Customer ID" 

           Width="80" />

       <ej:Column Field="ShipName" HeaderText="Ship Name" 

           Width="100" />

       <ej:Column Field="ShipCity" HeaderText="Ship City" 

           Width="100" />

       <ej:Column Field="Freight" HeaderText="Freight" 

           TextAlign="Right" Width="80" Format="{0:C3}" />

    &lt;/Columns&gt;

&lt;/ej:Grid&gt;





The following screenshot displays a Grid withpaging.



{ ![](Getting-Started_images/Getting-Started_img7.jpeg) | markdownify }
{:.image }


Enable Filtering

The Filtering feature in Grid is usedto facilitate the extraction of a subset of records that meet a certain criteria. You can apply Filters to one or more columns. This feature is used to filter particular sales data, in order to review the details.

To enable filtering, use the AllowFiltering property of Grid as follows.



[ASPX]



<ej:Grid ID="FlatGrid" runat="server" DataSourceID="SqlData"

         AllowPaging="true" AllowFiltering="true">

    &lt;Columns&gt;

        <ej:Column Field="OrderID" HeaderText="Order ID" 

            IsPrimaryKey="True" TextAlign="Right" Width="75" />

        <ej:Column Field="CustomerID" HeaderText="Customer ID" 

            Width="80" />

        <ej:Column Field="ShipName" HeaderText="Ship Name" 

            Width="100" />

        <ej:Column Field="ShipCity" HeaderText="Ship City" 

            Width="100" />

        <ej:Column Field="Freight" HeaderText="Freight" 

            TextAlign="Right" Width="80" Format="{0:C3}" />

    &lt;/Columns&gt;

    &lt;FilterSettings FilterType="FilterBar" /&gt;

&lt;/ej:Grid&gt;







The following screenshot shows Grid with filtering option.



{ ![](Getting-Started_images/Getting-Started_img8.jpeg) | markdownify }
{:.image }


Enable Grouping

The Grouping feature in Grid is used to consolidate the Grid data into groups. Grouping allows the categorization of records based on specified columns. You can easily group a particular column by simply dragging the column to the upper portion of the Grid. The Grid data is automatically grouped when you drop a particular column.  In this example, the Grouping feature is used to analyze the shipment details of products.

To enable grouping, use the AllowGrouping property of Grid as follows.



{ ![](Getting-Started_images/Getting-Started_img9.png) | markdownify }
{:.image }




[ASPX]



<ej:Grid ID="FlatGrid" runat="server" DataSourceID="SqlData"

         AllowPaging="true" AllowFiltering="true" 

AllowGrouping="true">

    &lt;Columns&gt;

        <ej:Column Field="OrderID" HeaderText="Order ID" 

            IsPrimaryKey="True" TextAlign="Right" Width="75" />

        <ej:Column Field="CustomerID" HeaderText="Customer ID" 

            Width="80" />

        <ej:Column Field="ShipName" HeaderText="Ship Name" 

            Width="100" />

        <ej:Column Field="ShipCity" HeaderText="Ship City" 

            Width="100" />

        <ej:Column Field="Freight" HeaderText="Freight" 

            TextAlign="Right" Width="80" Format="{0:C3}" />

    &lt;/Columns&gt;

    &lt;FilterSettings FilterType="FilterBar" /&gt;

&lt;GroupSettings GroupedColumns="ShipName" /&gt;

&lt;/ej:Grid&gt;







The following screenshot shows the analysis of shipment details by grouping ShipName.



{ ![](Getting-Started_images/Getting-Started_img10.png) | markdownify }
{:.image }


Enable Group Summary

The Show Summary property allows you to summarize the grid data into groups. Grouping allows the categorization of records based on specified columns. Group Summary summarizes the data present in the group. In the following example, Group Summary is used to summarize freight data of grouped ShipName category.

The following code example shows how you can enable ShowSummary.



{ ![](Getting-Started_images/Getting-Started_img11.png) | markdownify }
{:.image }




[ASPX]

<ej:Grid ID="FlatGrid" runat="server" DataSourceID="SqlData"

         AllowPaging="true" AllowFiltering="true" AllowGrouping="true"         ShowSummary="true">

    &lt;Columns&gt;

        <ej:Column Field="OrderID" HeaderText="Order ID" 

            IsPrimaryKey="True" TextAlign="Right" Width="75" />

        <ej:Column Field="CustomerID" HeaderText="Customer ID" 

            Width="80" />

        <ej:Column Field="ShipName" HeaderText="Ship Name" 

            Width="100" />

        <ej:Column Field="ShipCity" HeaderText="Ship City" 

            Width="100" />

        <ej:Column Field="Freight" HeaderText="Freight" 

            TextAlign="Right" Width="80" Format="{0:C3}" />

    &lt;/Columns&gt;

    &lt;FilterSettings FilterType="FilterBar" /&gt;

    &lt;GroupSettings GroupedColumns="ShipName" /&gt;

    &lt;SummaryRows&gt;

        &lt;ej:SummaryRow ShowTotalSummary="false"&gt;

            &lt;SummaryColumn&gt;

                <ej:SummaryColumn SummaryType="Sum" 

                       DisplayColumn="Freight" DataMember="Freight"

                       Prefix="Sum = " Format="{0:C3}" />

            &lt;/SummaryColumn&gt;

        &lt;/ej:SummaryRow&gt;

    &lt;/SummaryRows&gt;

&lt;/ej:Grid&gt;





The following screenshot shows the group summary.

{ ![](Getting-Started_images/Getting-Started_img12.png) | markdownify }
{:.image }


