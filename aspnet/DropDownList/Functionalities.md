---
layout: post
title: Functionalities in the DropDownList control for Syncfusion ASP.NET WebForm
description: Functionalities in the DropDownList control for Syncfusion ASP.NET WebForm
control: DropDownList
documentation: ug
---
# Functionalities

## Selection

By default only one item can be selected from the popup list. For multiple selection, you have to enable [checkboxes](Checkbox). The selected item consist of active class (“e-active”) to differentiate it from other items.

### Using value or text

To select an item initially you can pass the item’s value via Value or SelectItemByValue property. To achieve this DropDownList control must be initiated with the associate value. 

{% tabs %}

	{% highlight html %}
    
        <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="Text" DataValueField="Value" Value="item1"></ej:DropDownList>
		
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

![](Functionalities_images/Functionalities_img1.png)

N> To retrieve the selected item’s value you can use Value property in code behind.

{% tabs %}
	
    {% highlight html %}
        
       <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="Text" DataValueField="Value" Value="item1"></ej:DropDownList>
       <ej:Button ID="Button1" OnClick="Button1_Click" Text="Get Value" runat="server"></ej:Button>
        

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
        protected void Button1_Click(object Sender, Syncfusion.JavaScript.Web.ButtonEventArgs e)
        {
            var value = DropDownList1.Value;
        }
    {% endhighlight %}

{% endtabs %}

### Using indices

You can select a single or more than one item by passing index values to the properties SelectedIndex or SelectedIndices respectively. Index starts from 0 here.

{% tabs %}

	{% highlight html %}
    
       <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="Text" DataValueField="Value" SelectedIndex="2"></ej:DropDownList>
		
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

![](Functionalities_images/Functionalities_img2.png)

I> To use "SelectedIndices" property, you should enable either ShowCheckbox or MultiSelectMode property First.

{% tabs %}

	{% highlight html %}
         <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="Text" DataValueField="Value" ShowCheckbox="true"></ej:DropDownList>
		
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
            DropDownList1.SelectedIndices = new List<int> { 1, 2 };

        }
        public class Data
        {
            public string Value { get; set; }
            public string Text { get; set; }
        }
        
    {% endhighlight %}
    
{% endtabs %}

### Unselect items

Similarly, you can unselect a single or multiple items by using [unselectItemByValue](http://help.syncfusion.com/js/api/ejdropdownlist#methods:unselectitembyvalue) or [unselectItemByIndices](http://help.syncfusion.com/js/api/ejdropdownlist#methods:unselectitembyindices) or [unselectItemByText](http://help.syncfusion.com/js/api/ejdropdownlist#methods:unselectitembytext) methods. This will remove the selection state of the corresponding data item from the popup list and textbox. 

{% tabs %}

	{% highlight html%}
    
        <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="Text" DataValueField="Value" ShowCheckbox="true" SelectedIndex="2"></ej:DropDownList>
        <ej:Button ID="Button1" ClientSideOnClick="unselect" runat="server" Text="unSelect"></ej:Button>
        <script>
            
            function unselect() {
                obj = $("#<%=DropDownList1.ClientID%>").data("ejDropDownList");
                obj.unselectItemByValue("item2");
                obj.unselectItemByIndices(2);
                obj.unselectItemByText("ListItem 4");
            }
        </script>
        
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

## Grouping

The DropDownList items can be categorized by using a specific field in the popup list. This is enabled by using Category field on data source binding. By default grouping is disabled in DropDownList.
The below given example explains the behavior of grouping with List data binding.

{% tabs %}

	{% highlight html %}
    
        <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="Name" DataValueField="Name" DataGroupByField="Category" ></ej:DropDownList>
        
	{% endhighlight %}
    
    {% highlight c# %}
    
        protected void Page_Load(object sender, EventArgs e)
        {
            List<VegetableList> VegeList = new List<VegetableList>();
            VegeList.Add(new VegetableList { Name = "Cabbage", Category = "Leafy and Salad" });
            VegeList.Add(new VegetableList { Name = "Pea", Category = "Leafy and Salad" });
            VegeList.Add(new VegetableList { Name = "Spinach", Category = "Leafy and Salad" });
            VegeList.Add(new VegetableList { Name = "Wheatgrass", Category = "Leafy and Salad" });
            VegeList.Add(new VegetableList { Name = "Yarrow", Category = "Leafy and Salad" });
            VegeList.Add(new VegetableList { Name = "Chickpea", Category = "Beans" });
            VegeList.Add(new VegetableList { Name = "Green bean", Category = "Beans" });
            VegeList.Add(new VegetableList { Name = "Horse gram", Category = "Beans" });
            VegeList.Add(new VegetableList { Name = "Peanut", Category = "Beans" });
            VegeList.Add(new VegetableList { Name = "Pigeon pea", Category = "Beans" });
            VegeList.Add(new VegetableList { Name = "Garlic", Category = "Bulb and Stem" });
            VegeList.Add(new VegetableList { Name = "Garlic Chives", Category = "Bulb and Stem" });
            VegeList.Add(new VegetableList { Name = "Lotus root", Category = "Bulb and Stem" });
            VegeList.Add(new VegetableList { Name = "Nopal", Category = "Bulb and Stem" });
            VegeList.Add(new VegetableList { Name = "Onion", Category = "Bulb and Stem" });
            VegeList.Add(new VegetableList { Name = "Shallot", Category = "Bulb and Stem" });
            VegeList.Add(new VegetableList { Name = "Beetroot", Category = "Root and Tuberous" });
            VegeList.Add(new VegetableList { Name = "Carrot", Category = "Root and Tuberous" });
            VegeList.Add(new VegetableList { Name = "Ginger", Category = "Root and Tuberous" });
            VegeList.Add(new VegetableList { Name = "Potato", Category = "Root and Tuberous" });
            VegeList.Add(new VegetableList { Name = "Radish", Category = "Root and Tuberous" });
            VegeList.Add(new VegetableList { Name = "Turmeric", Category = "Root and Tuberous" });
            DropDownList1.DataSource = VegeList;
            
        }
        public class VegetableList
        {
            public string Name { get; set; }
            public string Category { get; set; }
        }
        
    {% endhighlight %}
    
{% endtabs %}

![](Functionalities_images/Functionalities_img3.jpeg)

N> Grouping has restrictions in the following scenarios,
N> 1.  It is not supported on using HTML "select" element with predefined set of options
N> 2.  When using UL-LI elements you need to use “e-category” class in li element to specify it as the grouping header. The following code will explain this behavior,


{% highlight html %}

    <ej:DropDownList ID="DropDownList1" runat="server" TargetID="#groupinglist"></ej:DropDownList>

     <div id="groupinglist">
            <ul>
                <span class="e-category">Header 1</span>
                <li>Item 1</li>
                <li>Item 2</li>
                <span class="e-category">Header 2</span>
                <li>Item 3</li>
                <li>Item 4</li>
                <li>Item 5</li>
            </ul>
        </div>
        
{% endhighlight %}

![](Functionalities_images/Functionalities_img4.jpeg)

I> Virtual scrolling is not supported with Grouping.

## Sorting

Sorting is enabled in order to display the items alphabetically in either ascending or descending order. By default the items is displayed in the initialized order, use EnableSorting property to automatically sort strings based on text field value. You can assign either SortOrder.Ascending or SortOrder.Descending enum values to the SortOrder property to sort out the list items. By default ascending order is followed when SortOrder property is not specified. 

{% tabs %}

	{% highlight html %}
    
        <ej:DropDownList ID="DropDownList1" runat="server" DataValueField="Value" DataTextField="Text" SortOrder="Descending" EnableSorting="true"></ej:DropDownList>
		
	{% endhighlight %}
    
    {% highlight c# %}
       
        protected void Page_Load(object sender, EventArgs e)
        {
            List<Data> DropDownData = new List<Data>();
            DropDownData.Add(new Data { Value = "item1", Text = "List Item 1" });
            DropDownData.Add(new Data { Value = "item5", Text = "List Item 5" });
            DropDownData.Add(new Data { Value = "item4", Text = "List Item 4" });
            DropDownData.Add(new Data { Value = "item2", Text = "List Item 2" });
            DropDownData.Add(new Data { Value = "item3", Text = "List Item 3" });
            DropDownList1.DataSource = DropDownData;
            
        }
        public class Data
        {
            public string Value { get; set; }
            public string Text { get; set; }
        }
    
    {% endhighlight %}
    
{% endtabs %}

I> Virtual scrolling is not supported with Sorting.

## Cascading

This works for series of DropDownList in which items are filtered based on the previous DropDownList‘s selection. Cascading is performed based on the value field and this field should be bounded with a foreign key. To perform cascading, specify the child DropDownList’s id in CascadeTo property and use delimiter (“,”) to specify more than one child DropDownList.

Configuring the data items for cascading to the series of DropDownList is demonstrated below

{% tabs %}

	{% highlight html %}
        
        <div style="width: 400px;">
           <div style="float: left;">
               <span>Select Group</span>
                <ej:DropDownList ID="groupsList" runat="server" DataTextField="text" DataValueField="parentId" CascadeTo="LayoutSection_ControlsSection_countryList" ClientSideOnChange="onChange"></ej:DropDownList>
           </div>

           <div style="float: right;">
               <span>Select Country</span>
               <ej:DropDownList ID="countryList" runat="server" Enabled="false"></ej:DropDownList>
           </div>
       </div>
       
	{% endhighlight %}
    
    {% highlight js %}

        function onChange() {
            var ctry = $('#<%=countryList.ClientID%>').data("ejDropDownList");
            ctry.element.val("");
        }

    {% endhighlight %}

    {% highlight c# %}
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
            public CountryList(int cvalue, string cid, string ctext, string sprt)
            {
                this.value = cvalue;
                this.parentId = cid;
                this.text = ctext;
                this.sprite = sprt;
               
            }
        }
        [Serializable]
        class GroupsList
        {          
            public string parentId { get; set; }
            public string text { get; set; }
            public GroupsList(string gID, string gtext)
            {
                this.parentId = gID;
                this.text = gtext;
            }
        }
    {% endhighlight %}
    
{% endtabs %}

![](Functionalities_images/Functionalities_img5.jpeg)

![](Functionalities_images/Functionalities_img6.jpeg)

You can also bind the data source to the cascading DropDownList dynamically using ClientSideEventt Cascade as demonstrated below,

{% tabs %}

	{% highlight html %}
        @model MVCApplication.Controllers.HomeController
        
        <div style="width: 530px;">
           <div style="float: left;">
               <span>Select Group</span>
               <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="text" DataValueField="parentId" CascadeTo="DropDownList2" ClientSideOnChange="onChange"></ej:DropDownList>
           </div>

           <div style="float: left; padding-left: 50px;">
               <span>Select Country</span>
               <ej:DropDownList ID="DropDownList2" runat="server"  DataTextField="text" Enabled="false"></ej:DropDownList>
           </div>

           <div style="float: right;">
               <span>Select Players</span>
               <ej:DropDownList ID="DropDownList3" runat="server"  DataTextField="text" Enabled="false"></ej:DropDownList>
           </div>
       </div>
       
	{% endhighlight %}
    
    {% highlight js %}

        function onChange() {
            var ctry = $('#<%=DropDownList2.ClientID%>').data("ejDropDownList");
            ctry.enable();
            var player = $('#<%=DropDownList3.ClientID%>').data("ejDropDownList");
            player.enable();
        }

    {% endhighlight %}

    {% highlight c# %}
            List<Groups> groups = new List<Groups>();
            groups.Add(new Groups("a", "Group A"));
            groups.Add(new Groups("b", "Group B"));

            this.DropDownList1.DataSource = groups;

            List<Country> country = new List<Country>();
            country.Add(new Country("a", "Algeria"));
            country.Add(new Country("a", "Armenia"));
            country.Add(new Country("b", "Denmark"));
            country.Add(new Country("b", "Egypt"));
            this.DropDownList2.DataSource = country;

            List<Players> PlayerList = new List<Players>();
            PlayerList.Add(new Players("a", "Adams"));
            PlayerList.Add(new Players ( "a", "Clarke" ));
            PlayerList.Add(new Players ( "b", "Brett" ));
            PlayerList.Add(new Players ( "b", "James" ));
            this.DropDownList3.DataSource = PlayerList;
        }
        [Serializable]
        class Groups
        {
            public string parentId { get; set; }
            public string text { get; set; }
            public Groups(string cid, string ctext)
            {
                this.parentId = cid;
                this.text = ctext;
            }
        }
        [Serializable]
        class Country
        {
            public string parentId { get; set; }
            public string text { get; set; }
            public Country(string cid, string ctext)
            {
                this.parentId = cid;
                this.text = ctext;
            }
        }
        [Serializable]
        class Players
        {
            public string parentId { get; set; }
            public string text { get; set; }
            public Players(string cid, string ctext)
            {
                this.parentId = cid;
                this.text = ctext;
            }
        }
    {% endhighlight %}
    
{% endtabs %}

![](Functionalities_images/Functionalities_img7.jpeg)

## Search

Items are searched based on the keyed in values to the textbox. There are two types of searches,

* Incremental Search
* Filter Search

### Incremental Search

Selects the item in the popup list based on the keyed in value. If the time taken to type exceeds 1000 milliseconds then filtered items will be reset based on the current input value. By default this mode of search is enabled. Incremental search can be case sensitive or case insensitive. To make case sensitive, you can use CaseSensitiveSearch property.

{% tabs %}

	{% highlight html %}
        <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="Text" DataValueField="Value" EnableIncrementalSearch="true" CaseSensitiveSearch="true"></ej:DropDownList>
		
	{% endhighlight %}
    
    {% highlight c# %}
        protected void Page_Load(object sender, EventArgs e)
        {
            List<Data> DropDownData = new List<Data>();
            DropDownData.Add(new Data { Value = "emp1", Text = "Adams" });
            DropDownData.Add(new Data { Value = "emp2", Text = "James"});
            DropDownData.Add(new Data { Value = "emp3", Text = "Maria"});
            DropDownData.Add(new Data { Value = "emp4", Text = "Jessica"});
            DropDownData.Add(new Data { Value = "emp5", Text = "Jenneth" });
            DropDownList1.DataSource = DropDownData;
            
        }
        public class Data
        {
            public string Value { get; set; }
            public string Text { get; set; }
        }
    
    {% endhighlight %}
    
{% endtabs %}

![](Functionalities_images/Functionalities_img8.jpeg)

### Filter search

You can quickly locate specific item within a large data source by filtering matches with a search box. A text box appears in the popup list for searching when EnableFilterSearch property is enabled. By default, filtering returns the matched items list based on text in search textbox. 
You can configure the search filter by using FilterType property. There is two types of filter options,

* Starts With 
* Contains

N> Items are filtered based on “contains” filter type by default.

{% tabs %}

	{% highlight html %}
        <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="Text" DataValueField="Value" EnableFilterSearch="false" FilterType="StartsWith"></ej:DropDownList>
		
	{% endhighlight %}
    
    {% highlight c# %}
      protected void Page_Load(object sender, EventArgs e)
        {
            List<Data> DropDownData = new List<Data>();
            DropDownData.Add(new Data { Value = "emp1", Text = "Adams" });
            DropDownData.Add(new Data { Value = "emp2", Text = "James"});
            DropDownData.Add(new Data { Value = "emp3", Text = "Maria"});
            DropDownData.Add(new Data { Value = "emp4", Text = "Jessica"});
            DropDownData.Add(new Data { Value = "emp5", Text = "Jenneth" });
            DropDownList1.DataSource = DropDownData;
            
        }
        public class Data
        {
            public string Value { get; set; }
            public string Text { get; set; }
        }
    {% endhighlight %}
    
{% endtabs %}

![](Functionalities_images/Functionalities_img9.jpeg)

I> When VirtualScrolling enabled with searching, then filter will be applied only on the DropDownList items available at the moment.