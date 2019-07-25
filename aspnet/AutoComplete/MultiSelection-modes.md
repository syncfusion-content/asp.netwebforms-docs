---
layout: post
title: MultiSelection modes | AutoComplete | ASP.NET | Syncfusion
description: This section explains how to select multiple data in the Syncfusion ASP.NET Web Forms Autocomplete suggestion list.
platform: aspnet
control: AutoComplete
documentation: ug
---

# MultiSelection modes

AutoComplete control allows you to select multiple values from the suggestions list by using the MultiSelectMode property. Multiple values can be selected when MultiSelectMode value is set to VisualMode or Delimiter. 

Delimiter mode separates multiple items by using a separator character defined. When the Delimiter mode is set, you can define the delimiter character by using Delimiter property as well. It takes a single character and it must be a symbol. 

Visual mode selects multiple items by enclosing the item in a rounded rectangle with a close icon to remove item from the selection.

## Configuring MultiSelection Mode

The following steps explain the configuration of the MultiSelectMode for an AutoComplete textbox.

In the design page, define the AutoComplete control and configure its MultiSelectMode property accordingly.

{% highlight html %}

<%--Refer the ObjectDataSource binding for DataBinding to this code snippet--%>



<div style="width: 600px">

    <div style="display:inline-block; float:left; margin-right:25px">

    <span style="display:block; margin-bottom:12px">Using Delimiter</span>       <ej:Autocomplete ID="AutoCompleteBelmt" runat="server" DataSourceID="ObjectDataSource1" 

            DataTextField="Text" DataUniqueKeyField="ID" 

MultiSelectMode="Delimiter" Delimiter=";"/>

    </div>

    <div style="display:inline-block; float:left; margin-right:25px">

    <span style="display:block; margin-bottom:12px">Using VisualMode</span> 

 <ej:Autocomplete ID="AutoCompleteVisl" runat="server" DataSourceID="ObjectDataSource1" 

            DataTextField="Text" DataUniqueKeyField="ID" 

            MultiSelectMode="VisualMode"/>

    </div>

    <div style="display:inline-block; float:left;">

        <span style="display:block; margin-bottom:12px">Single selection</span>

<ej:Autocomplete ID="AutoComplete" runat="server" DataSourceID="ObjectDataSource1" 

            DataTextField="Text" DataUniqueKeyField="ID" 

MultiSelectMode="None"/>

    </div>

</div>





{% endhighlight %}



The following screenshot is the output for AutoComplete control with configured multiple selection.

![MultiSelection Mode](MultiSelection-modes_images/MultiSelection-modes_img1.png)



## Grouping

AutoComplete control provides grouping support for the suggestions list based on the category specified in the dataSource. By default AllowGrouping is set to false. To enable grouping for your AutoComplete control, set the value to true.

### Configuring Grouping for AutoComplete

The following steps explain how to configure grouping for an AutoComplete textbox by using ObjectDataSource.

Define an ObjectDataSource in the web page and configure the data source elements with Category field.

{% highlight c# %}

namespace ASPWeb

{

    public class ObjectData

    {

        public ObjectData(int _id, string _text, string _category)

        {

            this.ID = _id;

            this.Text = _text;

            this.Category = _category;

        }

        public ObjectData() { }

        public int ID

        {

            get;

            set;

        }



        public string Text

        {

            get;

            set;

        }

        public string Category

        {

            get;

            set;

        }

        public List<ObjectData> GetGroupingData()

        {

            List<ObjectData> cars = new List<ObjectData>();

cars.Add(new ObjectData { ID = 1, Text = "Audi S6", Category = "Audi" });

cars.Add(new ObjectData { ID = 2, Text = "Austin-Healey", Category = "Austin" });

cars.Add(new ObjectData { ID = 3, Text = "BMW 7", Category = "BMW" });

cars.Add(new ObjectData { ID = 4, Text = "Chevrolet Camaro", Category = "Chevrolet" });

cars.Add(new ObjectData { ID = 5, Text = "Mercedes-Benz", Category = "Mercedes" });

cars.Add(new ObjectData { ID = 6, Text = "Toyota 2000GT", Category = "Toyota" });

cars.Add(new ObjectData { ID = 7, Text = "Volvo P1800", Category = "Volvo" });

cars.Add(new ObjectData { ID = 8, Text = "Audi Avant RS 2", Category = "Audi" });

cars.Add(new ObjectData { ID = 9, Text = "Audi S4 quattro", Category = "Audi" });

cars.Add(new ObjectData { ID = 10, Text = "BMW M Roadster E85", Category = "BMW" });

cars.Add(new ObjectData { ID = 11, Text = "Mercedes-Benz Sprinter", Category = "Mercedes" });

cars.Add(new ObjectData { ID = 12, Text = "Corvette", Category = "Chevrolet" });

cars.Add(new ObjectData { ID = 13, Text = "Volvo P1800", Category = "Volvo" }); 

            return cars;

        }

    }

}



{% endhighlight %}



In the Design page, add an AutoComplete element from ToolBox and assign values for DataTextField, DataUniqueKeyField and DataCategoryField. Category field allows you to configure grouping. Set the AllowGrouping property to true

{% highlight html %}

<ej:Autocomplete ID="AutoComplete" runat="server" DataSourceID="ObjectDataSource1" DataTextField="Text" DataUniqueKeyField="ID" DataCategoryField="Category" AllowGrouping="true" FilterType="Contains" />

        <asp:ObjectDataSource ID="ObjectDataSource1" runat="server" SelectMethod="GetGroupingData" TypeName="ASP_896.ObjectData"></asp:ObjectDataSource>


{% endhighlight %}


The following screenshot is the output for AutoComplete control that provides grouping.

![Grouping](MultiSelection-modes_images/MultiSelection-modes_img2.png)



