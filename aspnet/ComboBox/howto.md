---
layout: post
title: Cascading in ComboBox widget for Syncfusion Essential WebForm
description: Describes about the cascading in ComboBox widget for Syncfusion Essential WebForm
platform: aspnet
control: ComboBox
documentation: ug
keywords: ComboBox, combobox, Cascading ComboBox, Autofill supported with ComboBox
---

# How To

## Configure the Cascading ComboBox

The cascading ComboBox is a series of ComboBox, where the value of one ComboBox depends upon  another's value. This can be configured by using the `ClientSideOnChange` event of the parent ComboBox. Within that change event handler, data has to be loaded to the child ComboBox based on the selected
value of the parent ComboBox.

The following example, shows the cascade behavior of Group and Country ComboBox. Here, the `dataBind` method is used to reflect the property changes immediately
to the ComboBox.

{% tabs %}
	
{% highlight html %}
	
<div class="row">
    <div class="col-xs-8 col-sm-4">
        <span class="txt">Select Group</span>
        <ej:ComboBox ID="groupsList" runat="server" DataTextField="text" DataValueField="parentId" ClientSideOnChange="onChange"></ej:ComboBox>
    </div>
    <div class="col-xs-8 col-sm-4">
        <span class="txt">Select Country</span>
        <ej:ComboBox ID="countryList" runat="server" DataTextField="text" Enabled="false"></ej:ComboBox>
    </div>
</div>

{% endhighlight %}
    
{% highlight javascript %}

<script type="text/javascript">
    function onChange(e) {
        var country = $('#<%=countryList.ClientID%>').data("ejComboBox");
        country.option({ enabled: true, query: new ej.Query().where('parentId', 'equal', e.model.value), value: null });
    }
</script>

{% endhighlight %}

{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)
{
    List<GroupsList> groups = new List<GroupsList>();
    groups.Add(new GroupsList("a", "Group A"));
    groups.Add(new GroupsList("b", "Group B"));
    groups.Add(new GroupsList("c", "Group C"));
    groups.Add(new GroupsList("d", "Group D"));
    groups.Add(new GroupsList("e", "Group E"));           
    this.groupsList.DataSource = groups;

    List<CountryList> countries = new List<CountryList>();            
    countries.Add(new CountryList(11, "a", "Algeria", "flag-dz"));
    countries.Add(new CountryList(12, "a", "Armenia", "flag-am"));
    countries.Add(new CountryList(13, "a", "Bangladesh", "flag-bd"));
    countries.Add(new CountryList(14, "a", "Cuba", "flag-cu"));
    countries.Add(new CountryList(15, "b", "Denmark", "flag-dk"));
    countries.Add(new CountryList(16, "b", "Egypt", "flag-eg"));
    countries.Add(new CountryList(17, "c", "Finland", "flag-fi"));
    countries.Add(new CountryList(18, "c", "India", "flag-in"));
    countries.Add(new CountryList(19, "c", "Malaysia", "flag-my"));
    countries.Add(new CountryList(20, "d", "New Zealand", "flag-nz"));
    countries.Add(new CountryList(21, "d", "Norway", "flag-no"));
    countries.Add(new CountryList(22, "d", "Poland", "flag-pl"));
    countries.Add(new CountryList(23, "e", "Romania", "flag-ro"));
    countries.Add(new CountryList(24, "e", "Singapore", "flag-sg"));
    countries.Add(new CountryList(25, "e", "Thailand", "flag-th"));
    countries.Add(new CountryList(26, "e", "Ukraine", "flag-ua"));                        
    this.countryList.DataSource = countries;
}
[Serializable]
class CountryList
{
    public int value { get; set; }
    public string parentId { get; set; }
    public string text { get; set; }
    public string sprite { get; set; }
    public CountryList(int value, string id, string country, string sprite)
    {
        this.value = value;
        this.parentId = id;
        this.text = country;
        this.sprite = sprite;

    }
}
[Serializable]
class GroupsList
{
    public string parentId { get; set; }
    public string text { get; set; }
    public GroupsList(string gID, string group)
    {
        this.parentId = gID;
        this.text = group;
    }
}

{% endhighlight %}

{% endtabs %}

![Cascading](HowTo-images/image1.png)

## Show the list items with icons

You can render **icons** to the list items by mapping the DataIconCSSField field. This `DataIconCSSField` field create a span in the list item with mapped class name
to allow styling as per your need.

In the following sample, icon classes are mapped with `DataIconCSSField` field.

{% tabs %}
	
{% highlight html %}
	
<div class="row">
    <ej:ComboBox ID="selectIcon" runat="server" Placeholder="Select a icon" Width="100%"></ej:ComboBox>
</div>

{% endhighlight %}
    
{% highlight css %}

<style>
    #container {
        visibility: hidden;
    }
    #loader {
    color: #008cff;
    height: 40px;
    width: 30%;
    position: absolute;
    top: 45%;
    left: 45%;
    }
    .e-list-icon{
        line-height: 1.3;
        padding-right: 10px;
        text-indent: 5px;
    }
    .asc-sort:before {
        content: '\e73f';
        font-family: 'e-icons';  
        font-size: 20px;

    }
    .desc-sort:before {
        content: '\e721';
        font-family: 'e-icons';   
        font-size: 20px;
    }
    .filter:before {
        content: '\e818';
        font-family: 'e-icons';  
        font-size: 20px;
        opacity: 0.78;
    }
    .clear:before {
        content: '\e7db';
        font-family: 'e-icons';  
        font-size: 20px;
    }
</style>

{% endhighlight %}

{% highlight c# %}

public partial class Icons : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        this.selectIcon.DataSource = IconCss.GetIconList();
        this.selectIcon.DataTextField = "Name";
        this.selectIcon.DataIconCSSField = "IconClass";
    }
}

public class IconCss
{
    public string Name { get; set; }
    public string IconClass { get; set; }
    public static List<IconCss> GetIconList()
    {
        List<IconCss> icon = new List<IconCss>();
        icon.Add(new IconCss { IconClass = "asc-sort", Name = "Sort A to Z" });
        icon.Add(new IconCss { IconClass = "desc-sort", Name = "Sort Z to A " });
        icon.Add(new IconCss { IconClass = "filter", Name = "Filter" });
        icon.Add(new IconCss { IconClass = "clear", Name = "Clear" });
        return icon;
    }
}

{% endhighlight %}

{% endtabs %}

## AutoFill supported with ComboBox

The ComboBox supports the `AutoFill` behavior with the help of AutoFill property. Whenever you change the input value, the ComboBox will autocomplete your data by matching the typed character. Suppose, if no matches
found then, comboBox doesn't suggest any item.

In the following sample, showcase that how to work autofill with ComboBox.

{% tabs %}
	
{% highlight html %}
	
<div class="row">
    <ej:ComboBox ID="searchCustomer" AutoFill="true" runat="server" Width="100%" DataTextField="ContactName" Placeholder="Search a customer">
        <DataManager URL="http://js.syncfusion.com/ejServices/wcf/NorthWind.svc/" CrossDomain="true"></DataManager>
    </ej:ComboBox>
</div>

{% endhighlight %}
    
{% highlight c# %}

 protected void Page_Load(object sender, EventArgs e)
{
    this.searchCustomer.Query = "ej.Query().from('Suppliers').select('SupplierID', 'ContactName')";
}		
		
{% endhighlight %}

{% endtabs %}

![AutoFill](HowTo-images/image2.png)

## Validation of ComboBox using jQuery Validator

Validation of ComboBox can be done on form submission using jQuery Validations by adding name attribute for ComboBox through `htmlAttributes` property. Also, you can remove this error message during item selection through select or change event of ComboBox

N> [jquery.validate.min](http://cdn.syncfusion.com/js/assets/external/jquery.validate.min.js) script file should be referred for validation, for more details, refer [here](http://jqueryvalidation.org/documentation).

{% tabs %}

{% highlight html%}

    <div class="frame">
    <div class="row">
        <div class="col-xs-8 col-sm-4">
            <span class="txt">Select Country</span>
            <ej:ComboBox ID="countryList" runat="server"         
            AutoFill="true"
             DataValueField="text" DataTextField="text" Placeholder="Select a Country" Width="100%"  ClientSideOnSelect="select">
            </ej:ComboBox>
            <asp:Label class="message" runat="server"></asp:Label>
            <br />
            <asp:Button ID="valid" runat="server" OnClientClick="validate()" Text="Validate" />
        </div>                   
    </div>
    </div>
    <script>
        function validate() {
            var rules = {};
            $("form[id$=form1] input[name$=select]").each(function () {
                rules[this.name] = "required";
            });
            $('form[id$="form1"]').validate({
                rules: rules,
                errorPlacement: function (error, element) {
                    $(error).insertAfter($(".message"));
                }
            });
        }
        function select(args) {
            if (args.value != "") {
                $("label.error").css("display", "none")  //hide error message when value is selected.
            }
        }
    </script>
     
{% endhighlight%}

{% highlight c# %}

        Dictionary<string, object> htmlAttributes = new Dictionary<string, object>();
        protected void Page_Load(object sender, EventArgs e)
        {
            htmlAttributes.Add("name", "select");
            List<CountryList> countries = new List<CountryList>();
            countries.Add(new CountryList(11, "a", "Algeria"));
            countries.Add(new CountryList(12, "a", "Armenia"));
            countries.Add(new CountryList(13, "a", "Bangladesh"));
            countries.Add(new CountryList(14, "a", "Cuba"));
            countries.Add(new CountryList(15, "b", "Denmark"));
            countries.Add(new CountryList(16, "b", "Egypt"));
            this.countryList.DataSource = countries;
            this.countryList.HtmlAttributes = htmlAttributes;
        }	
		
{% endhighlight %}

{% endtabs %}