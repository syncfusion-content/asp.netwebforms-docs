---
layout: post
title: Data binding in DropDownList | Syncfusion | ASP.NET WebForms
description: Describes about the data binding in DropDownList control for Syncfusion ASP.NET WebForm
platform: aspnet
control: DropDownList
documentation: ug
keywords: DropDownList, dropdown, data binding, Local data, Remote data
---

# Data Binding

To populate data in the DropDownList widget, define [dataSource](http://help.syncfusion.com/js/api/ejdropdownlist#members:datasource) property with associated fields. In DropDownList, can bind either local array or OData, WebApi and other [RESTful](https://en.wikipedia.org/wiki/Representational_state_transfer) services.

## Fields

The below listed fields are the data collection fields which maps fields for the data items of the DropDownList. 

<table>
    <tr>
        <th>
            Properties
            <br/>
        </th>
        <th>
            Description
            <br/>
        </th>
    </tr>
    <tr>
        <td>
            DataSource
            <br/>
        </td>
        <td>
            The data source contains the list of data for generating the popup list items.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Query
            <br/>
        </td>
        <td>
            It specifies the query to retrieve the data from the online server.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Fields
            <br/>
        </td>
        <td>
            It specifies the mapping fields for the data items of the DropDownList control.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            ID
            <br/>
        </td>
        <td>
            It specifies the ID of the tag.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Text
            <br/>
        </td>
        <td>
            It specifies the text content of the tag.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Value
            <br/>
        </td>
        <td>
            It specifies the value of the tag.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Category
            <br/>
        </td>
        <td>
            It is used to categorize the items based on a specific field. The value mapped to this field must be able to group the popup items.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            ImageUrl
            <br/>
        </td>
        <td>
            It defines the image location.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            ImageAttributes
            <br/>
        </td>
        <td>
            It defines the image attributes such as height, width, styles, etc.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            SpriteCssClass
            <br/>
        </td>
        <td>
            It defines the sprite CSS for the image tag to add a prefix icon to all popup items.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            HtmlAttributes
            <br/>
        </td>
        <td>
            It defines the HTML attributes such as class and styles for an item.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Selected
            <br/>
        </td>
        <td>
            This field defines the tag value to be selected initially. Corresponding field mapped has Boolean values to select the list items on control creation. The data with value true in this field is selected automatically when the control is initialized with checkbox.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            TableName
            <br/>
        </td>
        <td>
            It defines the table name for the tag value or displays text while rendering remote data.
            <br/>
        </td>
    </tr>
     <tr>
        <td>
            DataIdField
            <br/>
        </td>
        <td>
            It specifies the ID field name that is to be mapped.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataSourceID
            <br/>
        </td>
        <td>
            Specifies the ID of the DataSource.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataMember
            <br/>
        </td>
        <td>
            Specifies the member in a data source to bind to the data list control.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataTextField
            <br/>
        </td>
        <td>
            It specifies the name of the column value that binds the DropDownList text.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataValueField
            <br/>
        </td>
        <td>
            It specifies the value field to be bound.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataImageUrlField
            <br/>
        </td>
        <td>
            It maps the imageURL field name that have the image location.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataImageAttributesField
            <br/>
        </td>
        <td>
            It maps the field name that has image attributes such as height, width, styles, etc.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataSpriteCssField
            <br/>
        </td>
        <td>
            It maps to the field having sprite CSS for the image tag.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataHtmlAttributesField
            <br/>
        </td>
        <td>
            It maps the field name that has the HTML attributes such as ID, class, styles for the item.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataSelectedField
            <br/>
        </td>
        <td>
            This field defines the tag value to be selected initially. Corresponding field that is mapped has boolean values to select the list items on control creation. The data with value true in this field is selected automatically when the control is initialized.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataTableNameField
            <br/>
        </td>
        <td>
            It defines the table name for tag value or displays text while rendering remote data.
            <br/>
        </td>
    </tr>
</table>

## Local Data

Define a List data and initialize the control with DataSource property. Specify the column names in the Fields property. <br/>

N> The columns are bounded automatically when the fields are specified with the default names like id, text, etc...

{% tabs %}

	{% highlight html %}
       
       <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="Text" DataValueField="Country" DataGroupByField="Role" DataImageUrlField="Image" DataImageAttributesField="ImageAttr"></ej:DropDownList>
	
    {% endhighlight %}
    
    {% highlight css %}

    	.ImageId {
        	margin: -7px;
        	padding: 3px 10px 3px 3px;
        	border: 0 none;
        	width: 60px;
        	height: 60px;
        	float: none;
    	}

    {% endhighlight %}
    
    {% highlight c# %}
        protected void Page_Load(object sender, EventArgs e)
        {
            List<Employee> Data = new List<Employee>();
            Data.Add(new Employee
            {
                Text = "Erik Linden",
                Role = "Executive",
                Country = "England",
                Image = "../Content/Employees/3.png",
                ImageAttr = "class='ImageId'"
            });
            Data.Add(new Employee
            {
                Text = "John Linden",
                Role = "Representative",
                Country = "Norway",
                Image = "../Content/Employees/6.png",
                ImageAttr = "class='ImageId'"
            });
            Data.Add(new Employee
            {
                Text = "Louis",
                Role = "Representative",
                Country = "Australia",
                Image = "../Content/Employees/7.png",
                ImageAttr = "class='ImageId'"
            });
            Data.Add(new Employee
            {
                Text = "Lawrence",
                Role = "Executive",
                Country = "India",
                Image = "../Content/Employees/8.png",
                ImageAttr = "class='ImageId'"
            });
            DropDownList1.DataSource = Data;
        }
        public class Employee
        {
            public string Text { get; set; }
            public string Role { get; set; }
            public string Country { get; set; }
            public string Image { get; set; }
            public string ImageAttr { get; set; }
        }
    {% endhighlight %}
    
{% endtabs %}


![Local Data](DataBinding_images/DataBinding_img1.jpeg)

N> Images for this sample are available in (installed location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\samples\web\themes\images<br/> 
           
## Virtual Scrolling 

To improve the performance when displaying large data set, you can use “AllowVirtualScrolling” and VirtualScrollMode property. This retrieves only a fixed amount of list items and loads remaining data on scrolling. The items will be fetched via AJAX request.

This supports two modes of virtualization. They are,

* Normal Mode
* Continuous Mode

I> 1. Sorting and Grouping is not supported with Virtual Scrolling
I> 2. “VirtualScrollMode” property accepts Syncfusion.JavaScript.VirtualScrollMode enum value.

### Normal Mode

It loads the data on scrolling the list of items. This can be achieved by setting Syncfusion.JavaScript.VirtualScrollMode.Normal value to the VirtualScrollMode property.


{% tabs %}

	{% highlight html %}
       
       <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="ShipCountry" DataValueField="ShipCountry" AllowVirtualScrolling="true" VirtualScrollMode="Normal" ItemsCount="7">
	
    {% endhighlight %}
    
    {% highlight c# %}
        protected void Page_Load(object sender, EventArgs e)
        {
            DropDownList1.DataSource = "http://mvc.syncfusion.com/Services/Northwnd.svc/Orders";
        }
        
    {% endhighlight %}
    
{% endtabs %}


### Continuous Mode

It loads the set of items when the scroller reaches at the end. This behaves like infinity scrolling. So when scroll reaches the end, it will fetch the remaining set of items and bind with your DropDownList. This can be achieved by setting Syncfusion.JavaScript.Continuous value to the "VirtualScrollMode" property.

N> In both modes, set of items will be fetched based on the count specified in the ItemsCount property and next set of items will be loaded on scrolling.

{% tabs %}

	{% highlight html %}
       
       <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="ShipCountry" DataValueField="ShipCountry" AllowVirtualScrolling="true" VirtualScrollMode="Continuous" ItemsCount="7">
	
    {% endhighlight %}
    
    {% highlight c# %}
        protected void Page_Load(object sender, EventArgs e)
        {
            DropDownList1.DataSource = "http://mvc.syncfusion.com/Services/Northwnd.svc/Orders";
        }
        
    {% endhighlight %}
    
{% endtabs %}