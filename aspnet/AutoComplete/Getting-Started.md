---
layout: post
title: Getting Started | AutoComplete | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: AutoComplete
documentation: ug
---

# Getting Started

## Create your first AutoComplete in ASP.NET

This section helps you to configure the AutoComplete control in your application and also to learn how to pass the required data to it and to customize its various options according to your requirements.

In this ASP.NET section use the flat-lime as the default theme.

The following screenshot illustrates the AutoComplete control that searches the list of components available in the database.

![](Getting-Started_images/Getting-Started_img1.png) 



### Create an AutoComplete

You can create an ASP.NET Project and add necessary Dll’s and Scripts with the help of the given 
[WebForms-Getting Started](http://help.syncfusion.com/aspnetmvc/autocomplete/getting-started) documentation.  
Initialize the corresponding AutoComplete control in the ASPX page.

{% highlight html %}



<div>

    Select a component:

<ej:Autocomplete ID="ComponentList" runat="server"/>

</div>



{% endhighlight %}



Execute the above code to create the AutoComplete textbox as illustrated in the following screenshot.





![](Getting-Started_images/Getting-Started_img2.png)



## Populate Data to AutoComplete

The data provided to the AutoComplete customizes the list of Data either locally or remotely. 

### Local Data Binding

AutoComplete provides data binding support to populate AutoComplete items, so that the values can be mapped to the AutoComplete fields, namely DataUniqueKeyField and DataTextField. DataBinding helps you bind a key value pair to AutoComplete textbox. DataUniqueKeyField takes the unique id of the dataSource elements. DataTextField gets the value to be displayed in the AutoComplete textbox.

#### Defining the Local data for AutoComplete

The following steps explain local data binding of a list data to an AutoComplete textbox.

Define local DataSource elements by using the Key and Text fields in code behind and map the list data to DataSource property

{% highlight c# %}

    protected void Page_Load(object sender, EventArgs e)

            {

    this.AutoComplete.DataSource = new LocalData().GetDataItems().ToList();

            }



    public class LocalData

            {



                public LocalData(int _id, string _text)

                {

                    this.ID = _id;

                    this.Text = _text;

                }

                public LocalData() { }





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

                public List<LocalData> GetDataItems()

                {

                    List<LocalData> data = new List<LocalData>();

                    data.Add(new LocalData(1, "Audi S6"));

                    data.Add(new LocalData(2, "Austin-Healey"));

                    data.Add(new LocalData(3, "Aston Martin"));

                    data.Add(new LocalData(4, "BMW 7"));

                    data.Add(new LocalData(5, "Bentley Mulsanne"));

                    data.Add(new LocalData(6, "Bugatti Veyron"));

                    data.Add(new LocalData(7, "Chevrolet Camaro"));

                    data.Add(new LocalData(8, "Cadillac "));

                    data.Add(new LocalData(9, "Honda S2000"));

                    data.Add(new LocalData(10, "Hyundai Santro"));

                    data.Add(new LocalData(11, "Mercedes-Benz "));

                    data.Add(new LocalData(12, "Mercury Coupe"));

                    data.Add(new LocalData(13, "Maruti Alto 800"));

                    data.Add(new LocalData(14, "Volkswagen Shirako"));

                    data.Add(new LocalData(15, "Lotus Esprit "));

                    data.Add(new LocalData(16, "Lamborghini Diablo"));

                    data.Add(new LocalData(17, "Nissan Qashqai "));

                    data.Add(new LocalData(18, "Oldsmobile S98 "));

                    data.Add(new LocalData(19, "Opel Superboss "));

                    data.Add(new LocalData(20, "Scion SRS/SC/SD "));

                    data.Add(new LocalData(21, "Saab Sportcombi "));

                    data.Add(new LocalData(22, "Subaru Sambar "));

                    data.Add(new LocalData(23, "Suzuki Swift "));

                    data.Add(new LocalData(24, "Volvo P1800 "));

                    data.Add(new LocalData(25, "Kia Sedona EX "));

                    data.Add(new LocalData(26, "Koenigsegg Agera "));

                    data.Add(new LocalData(27, "Ford Boss 302 "));

                    data.Add(new LocalData(28, "Ferrari 360 "));

                    data.Add(new LocalData(29, "Ford Thunderbird "));

                    data.Add(new LocalData(30, "Alfa Romeo"));

                    return data;

                }

        }

{% endhighlight %}


In the Design page, add an AutoComplete element from ToolBox and assign values for DataTextField and DataUniqueKeyField.

{% highlight html %}

<%-- Map the data fields to the corresponding Field items--%>


<div>

Select a component/s:

<ej:Autocomplete ID="ComponentList" runat="server" DataTextField="Text" DataUniqueKeyField="ID" Width="500px"></ej:Autocomplete>

</div>


{% endhighlight %}



Run this code to render the AutoComplete with components list.

![](Getting-Started_images/Getting-Started_img3.png)



You can also set common customization changes to the AutoComplete textbox like enabling multiple-selection, highlight search and add dropdown icon in order to get the desired result.

### Configure Visual Mode with filter option

By default, the AutoComplete is rendered with single-value selection that is set to multiple-value selection by using the property MultiSelectMode as VisualMode that allows you to select multiple data. You can set the FilterType option as StartsWith to sort the suggestion list based on the starting character.

{% highlight html %}



<div>

Select a component/s:

<ej:Autocomplete ID="ComponentList" runat="server" DataTextField="Text" DataUniqueKeyField="ID" FilterType="StartsWith" MultiSelectMode="VisualMode" Width="500px"> </ej:Autocomplete>

</div>





{% endhighlight %}



The following screenshot displays the AutoComplete textbox with selection visual mode.

![](Getting-Started_images/Getting-Started_img4.png) 



### Configure Highlight Search and Rounded corners

{% highlight html %}

<div>

Select a component/s:

<ej:Autocomplete ID="ComponentList" runat="server"DataTextField="Text" DataUniqueKeyField="ID"

FilterType="StartsWith" MultiSelectMode="VisualMode" HighlightSearch="true" ShowRoundedCorner="true" Width="500px"></ej:Autocomplete>

</div>


{% endhighlight %}

When you set the HighlightSearch property to ‘true’, the characters typed in textbox gets highlighted in the suggestion list. To display the textbox with rounded ends, you can enable the ShowRoundedCorner property.

The following screenshot displays the AutoComplete textbox with highlight search enabled.

![](Getting-Started_images/Getting-Started_img5.png) 


### Configure Popup button

To enable the Popup button, you can set ShowPopupButton property to ‘true’ that displays the PopupButton icon at the end of textbox. By default, search icon replaces other icons and so you need to override the CSS classes and replace the content toDropDown arrow icon available in core CSS file as follows.

{% highlight css %}



<style>

.e-icon.e-search:before {

               content:"\e63b";

        }

</style>





{% endhighlight %}



{% highlight html %}



<div>

Select a component/s:

<ej:Autocomplete ID="ComponentList" runat="server" DataTextField="Text" DataUniqueKeyField="ID" 

FilterType="StartsWith" MultiSelectMode="VisualMode" HighlightSearch="true" ShowRoundedCorner="true" ShowPopupButton="true"Width="500px"> </ej:Autocomplete>

</div>


{% endhighlight %}



The following screenshot displays the AutoComplete textbox with dropdown icon.



![](Getting-Started_images/Getting-Started_img6.png)



