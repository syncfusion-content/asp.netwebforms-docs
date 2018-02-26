---
layout: post
title: State Persistance with DropDownList control for Syncfusion ASP.NET 
description: State Persistence support to DropDownList control for Syncfusion ASP.NET 
platform: aspnet
control: DropDownList
documentation: ug
keywords: Persistence, DropDownList, dropdown, State Persistence, View state Maintenance
---

# State Maintenance

## State Persistence

DropDownList stores its model is local storage by defining the property EnablePersistence).
You can sustain the below given functionalities in DropDownList by enabling persistence property,

* Selected items value in the textbox 
* Item’s selection state in the popup list 

Control model will be stored in local storage / cookies of browser before page refreshes and reinitialized with the restored model after refresh.
The following properties are not included while maintaining DropDownList’s state in local storage to keep localStorage compact.

* Fields
* Data source
* Query 

{% tabs %}

	{% highlight html %}
       
         <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="Text" DataValueField="Value" EnablePersistence="true" ></ej:DropDownList>
		
	{% endhighlight %}
    
    {% highlight c# %}
         protected void Page_Load(object sender, EventArgs e)
        {
            List<Data> DropDownData = new List<Data>();
            DropDownData.Add(new Data { Value = "item1", Text = "ListItem 1" });
            DropDownData.Add(new Data { Value = "item2", Text = "ListItem 2" });
            DropDownData.Add(new Data { Value = "item3", Text = "ListItem 3" });
            DropDownData.Add(new Data { Value = "item4", Text = "ListItem 4" });
            DropDownData.Add(new Data { Value = "item5", Text = "ListItem 5" });
            DropDownList1.DataSource = DropDownData;
            
        }
        public class Data
        {
            public string Value { get; set; }
            public string Text { get; set; }
        }
    {% endhighlight %}
    
{% endtabs %}

## Accessing currently stored state

Persisted state can be accessed through local storage using corresponding key name. Key name formation would be in below order. It is combination of plugin name and control id.

{% highlight js %}

	// DropDownList state as string
	var dropdownlistStateString = window.localStorage.ejDropDownListDropDown;

	//DropDownList state as object
	var dropdownlistStateObject = JSON.parse(window.localStorage.ejDropDownListDropDown);

{% endhighlight %}

N> In the above example, ‘ejDropDownList’ is plugin name and ‘DropDown’ is control id.           

## Maintain data bound values after post back

By default behavior of Syncfusion DropDownList, if DataSource is bound from code behind once on rendering the control. Then the control will lose its data binding on any post back actions. Because on postback control will be reinitialized and the datasource will not be set if it is bind page load event when postback is false. If you need to maintain the DataSource bound after postback, you have to use DataSourceCachingMode property with enum value ViewState or Session. This will maintain the data bound values in our controls after post back. 

<table>
<tr>
<th>
Value
</th>
<th>
Description
</th>
</tr>
<tr>
<td>
None
</td>
<td>
DataSource object will not be maintained
</td>
</tr>
<tr>
<td>
ViewState
</td>
<td>
DataSource object will be maintained using view state in client side
</td>
</tr>
<tr>
<td>
Session
</td>
<td>
DataSource object will be maintained using session variable in server
</td>
</tr>
</table>

{% highlight html %}

    <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="Text" DataValueField="ID" DataSourceCachingMode="ViewState" >
    </ej:DropDownList>
    <asp:Button runat="server" ID="button1" Text="Submit" />

{% endhighlight %}

Here data is bound only on initial page load and not on every post back. 

{% highlight c# %}

    protected void Page_Load(object sender, EventArgs e)
    {
        if (!IsPostBack)
        {
            DropDownList1.DataSource = new DropDownData().GetItems();
        }
    }
    public class DropDownData
    {

        public DropDownData(int _id, string _text)
        {

            this.ID = _id;
            this.Text = _text;

        }

        public DropDownData() { }

        [Browsable(true)]
        public int ID
        {

            get;
            set;

        }

        [Browsable(true)]
        public string Text
        {
            get;
            set;
        }

        public List<DropDownData> GetItems()
        {

            List<DropDownData> data = new List<DropDownData>();
            data.Add(new DropDownData(1, "Railways"));
            data.Add(new DropDownData(2, "Roadways"));
            data.Add(new DropDownData(3, "Airways"));
            data.Add(new DropDownData(4, "Waterways"));
            data.Add(new DropDownData(5, "Electric Trains"));
            data.Add(new DropDownData(6, "Diesel Trains"));
            data.Add(new DropDownData(7, "Heavy Motor Vehicles"));
            data.Add(new DropDownData(8, "Light Motor Vehicles"));
            data.Add(new DropDownData(9, "Aero planes"));
            data.Add(new DropDownData(10, "Helicopters"));
            data.Add(new DropDownData(11, "Ships"));
            data.Add(new DropDownData(12, "Submarines"));
            return data;

        }

    }

{% endhighlight %}