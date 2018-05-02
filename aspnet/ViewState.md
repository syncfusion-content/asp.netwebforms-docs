---
layout: post
title: View State Syncfusion ASP.NET controls
description: View State of Syncfusion ASP.NET controls
platform: aspnet
control: Introduction
documentation: ug

---

# View State 

View State is the method that the ASP.NET page Framework uses to preserve page and control values between round trips. When the HTML markup for the page is rendered, the current state of the page and values should be retained during postback.

Syncfusion controls can maintain their values even after form post or browser refresh by using the EnablePersistence property.

Sustain the entire widget model of EJWEB DatePicker even after form post or browser refresh by using the EnablePersistence property. The entire model values are as follows:
•	Selected date
•	Highlighted date
•	Start and depth level

These are stored in local storage/cookies of browser before page refreshes, and reinitialized with the restored model after refresh.

{% highlight html %}

    <ej:DatePicker ID="datepick" EnablePersistence="true" runat="server"></ej:DatePicker>

{% endhighlight %}

## Maintain data bound values after post back

By default, behavior of the Syncfusion DataSource controls such as DropDownList, Treeview, if DataSource is bound from code behind once on rendering the control. Then the control will lose the data that is bound on any post back actions. Because on postback, the control will be reinitialized and the datasource will not be set if it is binding page load event when IsPostBack is false. If you need to maintain the DataSource bound after postback, you have to use DataSourceCachingMode property with enum value ViewState or Session. This will maintain the data bound values in our controls after post back.

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
DataSource object will not be maintained.
</td>
</tr>
<tr>
<td>
ViewState
</td>
<td>
DataSource object will be maintained using view state in client side.
</td>
</tr>
<tr>
<td>
Session
</td>
<td>
DataSource object will be maintained using session variable in server.
</td>
</tr>
</table>

Let see an example, how to maintain the DataSource of DropDownList control after the post back.

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