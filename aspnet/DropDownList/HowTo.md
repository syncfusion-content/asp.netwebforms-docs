---
layout: post
title: How to - DropDownList control for Syncfusion ASP.NET Webform
description: How To Section in DropDownList control for Syncfusion ASP.NET Webform
platform: js
control: DropDownList
documentation: ug
---

# How To

## Retrieve the selected item data from select event via arguments?

Bind the OnValueSelect event and you can retrieve the value from select event arguments in code behind. 

{% tabs %}

    {% highlight html %}
    
        <ej:DropDownList ID="DropDownList1" runat="server" OnValueSelect="DropDownList1_ValueSelect">
            <Items>
                <ej:DropDownListItem ID="DropDownListItem1" runat="server" Text="ListItem 1" Value="item1">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem2" runat="server" Text="ListItem 2" Value="item2">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem3" runat="server" Text="ListItem 3" Value="item3">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem4" runat="server" Text="ListItem 4" Value="item4">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem5" runat="server" Text="ListItem 5" Value="item5">
                </ej:DropDownListItem>
            </Items>
        </ej:DropDownList>
        <br />
        <asp:Label runat="server" ID="Label1"></asp:Label>
          
	{% endhighlight %}
    
    {% highlight c# %}

        protected void DropDownList1_ValueSelect(object sender, Syncfusion.JavaScript.Web.DropdownListEventArgs e)
        {
            Label1.Text = "Selected item text is " + e.SelectedText + " and value is " + e.Value;
        }
 
    {% endhighlight %}
    
{% endtabs %}

In the following screenshot you can get the argument details for OnValueSelect event

![](HowTo_images/HowTo_img3.jpeg)

## Add check all option in popup list?

You can use HeaderTemplate property to add any HTML element. Code snippet to add check all option is given below,

{% tabs %}

    {% highlight html %}

        <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="Text" DataValueField="Value" ShowCheckbox="true" HeaderTemplate="<div class='temp' ><input id ='check' type='checkbox'></div>" ClientSideOnCreate="OnCreate">  </ej:DropDownList>
        
    {% endhighlight %}

    {% highlight css %}

            .temp {
                height: 30px;
                display: block;
                padding-left: 13px;
                padding-top: 5px;
                border-bottom: 1px solid #c8c8c8;
            }
            .e-chkbox-wrap .e-text {
                font-size: 14px;
                padding-left: 10px;
            }

        
    {% endhighlight %}

    {% highlight js %}

            function OnCreate(args) {

                $("#check").ejCheckBox({ text: "Check All", change: "onallChange" });

            }
            function onallChange(args) {
                window.flag = true;
                var obj = $("#<%=DropDownList1.ClientID%>").ejDropDownList("instance");
                if (args.isChecked) obj.checkAll();
                else obj.uncheckAll();
                window.flag = false;
            }

    {% endhighlight %}

    {% highlight c# %}
        
            protected void Page_Load(object sender, EventArgs e)
            {
                List<Data> DropdownData = new List<Data>();
                DropdownData.Add(new Data { Value = "item1", Text = "ListItem 1" });
                DropdownData.Add(new Data { Value = "item2", Text = "ListItem 2" });
                DropdownData.Add(new Data { Value = "item3", Text = "ListItem 3" });
                DropdownData.Add(new Data { Value = "item4", Text = "ListItem 4" });
                DropdownData.Add(new Data { Value = "item5", Text = "ListItem 5" });
                DropDownList1.DataSource = DropdownData;
                
            }
            public class Data
            {
                public string Value { get; set; }
                public string Text { get; set; }
            }
            
    {% endhighlight %}

{% endtabs %}

The following screenshot exhibits the output of the above code,

![](HowTo_images/HowTo_img2.jpeg)

## To maintain data bound values after post back
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

            data.Add(new DropDownData(9, "Aeroplanes"));

            data.Add(new DropDownData(10, "Helicopters"));

            data.Add(new DropDownData(11, "Ships"));

            data.Add(new DropDownData(12, "Submarines"));

            return data;

        }

    }

{% endhighlight %}
