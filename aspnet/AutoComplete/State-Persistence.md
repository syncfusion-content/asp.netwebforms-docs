---
layout: post
title: State Persistence | AutoComplete | ASP.NET Webforms | Syncfusion
description: This section explains how to perform state persistence in the Syncfusion ASP.NET Web Forms Autocomplete component.
platform: aspnet
control: AutoComplete
documentation: ug
---

# State Persistence

AutoComplete control can store the model value in the browser’s cookies. Every time after initial rendering, the control gets the model from the cookie only. By using EnablePersistence property, you can store the model value in cookies. So when any changes are made dynamically, the values are updated in the cookie. On refreshing the page, the previous state of the AutoComplete control is maintained in the cookie and the control is rendered from it.

## Configure state persistence of AutoComplete	

The following steps explain how to enable state maintenance for AutoComplete.

In the design page, add an AutoComplete element from ToolBox and set EnablePersistence value as true.

{% highlight html %}

<%--Refer the ObjectDataSource binding for DataBinding to this code snippet--%>

<ej:Autocomplete ID="AutoComplete" runat="server" DataSourceID="ObjectDataSource1" DataTextField="Text" DataUniqueKeyField="ID" EnablePersistence="true" /> 



{% endhighlight %}



The following screenshot is the output for AutoComplete when EnablePersistence is set to true.

![State Persistence](State-Persistence_images/State-Persistence_img1.png)



## Templates

You can provide a template for customizing the appearance of the AutoComplete textbox suggestions. This is achieved by assigning a string template to the Template property.

### Configuring Templates

The following steps explain how to define a template to display a text and image for an AutoComplete textbox.

Define an ObjectDataSource in the web page and configure the data source elements with text and sprite fields. Add the class file to App_Data folder in your web application.

{% highlight c# %}

namespace ASPWeb

{

    public class ObjectData

    {



        public ObjectData(string _text, string _sprite)

        {

            this.Text = _text;

            this.Sprite = _sprite;

        }

        public ObjectData() { }



        public string Text

        {

            get;

            set;

        }



        public string Sprite

        {

            get;

            set;

        }



        public List<ObjectData> GetTemplateData()

        {

            List<ObjectData> data = new List<ObjectData>();



            data.Add(new ObjectData(Text = "Algeria", Sprite = "flag-dz"));

            data.Add(new ObjectData(Text = "Argentina", Sprite = "flag-ar"));

            data.Add(new ObjectData(Text = "Armenia", Sprite = "flag-am"));

            data.Add(new ObjectData(Text = "Brazil", Sprite = "flag-br"));

            data.Add(new ObjectData(Text = "Bangladesh", Sprite = "flag-bd"));

            data.Add(new ObjectData(Text = "Canada", Sprite = "flag-ca"));

            data.Add(new ObjectData(Text = "Cuba", Sprite = "flag-cu"));

            data.Add(new ObjectData(Text = "China", Sprite = "flag-cn"));

            data.Add(new ObjectData(Text = "Denmark", Sprite = "flag-dk"));

            data.Add(new ObjectData(Text = "Estonia", Sprite = "flag-ea"));

            data.Add(new ObjectData(Text = "Egypt", Sprite = "flag-eg"));

            data.Add(new ObjectData(Text = "France", Sprite = "flag-fr"));

            data.Add(new ObjectData(Text = "Finland", Sprite = "flag-fi"));

            data.Add(new ObjectData(Text = "Greenland", Sprite = "flag-gl"));

            data.Add(new ObjectData(Text = "India", Sprite = "flag-in"));

            data.Add(new ObjectData(Text = "Indonesia", Sprite = "flag-id"));

            data.Add(new ObjectData(Text = "Malaysia", Sprite = "flag-my"));

            data.Add(new ObjectData(Text = "Mexico", Sprite = "flag-mx"));

            data.Add(new ObjectData(Text = "New Zealand", Sprite = "flag-nz"));

            data.Add(new ObjectData(Text = "Netherlands", Sprite = "flag-nl"));

            data.Add(new ObjectData(Text = "Norway", Sprite = "flag-no"));

            data.Add(new ObjectData(Text = "Portugal", Sprite = "flag-pt"));

            data.Add(new ObjectData(Text = "Poland", Sprite = "flag-pl"));

            data.Add(new ObjectData(Text = "Qatar", Sprite = "flag-qr"));

            return data;

        }

    }

}



{% endhighlight %}



Define the CSS classes for the sprite images, you can find the images in the following location

[Installed Drive]:\Users\[user name]\AppData\Local\Syncfusion\EssentialStudio\ {{site.releaseversion}}\JS \Samples\ web \images\autocomplete\flags.png



{% highlight css %}

<style type="text/css">

        /* Sprite CSS for country flags */

        .flag

        {

            background: url("Styles/flags.png") no-repeat;

            float: left;

            height: 15px;

            margin-right: 10px;

            margin-top: 3px;

            width: 25px;

        }



        .flag.flag-am {background-position: -25px 0}

        .flag.flag-ar {background-position: -50px 0}

        .flag.flag-bd {background-position: -75px 0}

        .flag.flag-br {background-position: -100px 0}

        .flag.flag-ca {background-position: -125px 0}

        .flag.flag-cn {background-position: 0 -15px}

        .flag.flag-cu {background-position: -25px -15px}

        .flag.flag-dk {background-position: -50px -15px}

        .flag.flag-dz {background-position: -75px -15px}

        .flag.flag-ea {background-position: -100px -15px}

        .flag.flag-eg {background-position: -125px -15px}

        .flag.flag-es {background-position: 0 -30px}

        .flag.flag-fi {background-position: -25px -30px}

        .flag.flag-fr {background-position: -50px -30px}

        .flag.flag-gl {background-position: -75px -30px}

        .flag.flag-id {background-position: -100px -30px}

        .flag.flag-in {background-position: -125px -30px}

        .flag.flag-mx {background-position: 0 -45px}

        .flag.flag-my {background-position: -25px -45px}

        .flag.flag-nl {background-position: -50px -45px}

        .flag.flag-no {background-position: -75px -45px}

        .flag.flag-nz {background-position: -100px -45px}

        .flag.flag-pl {background-position: -125px -45px}

        .flag.flag-pt {background-position: 0 -60px}

        .flag.flag-qr {background-position: -25px -60px}

        .flag.flag-ro {background-position: -50px -60px}

        .flag.flag-sa {background-position: -75px -60px}

        .flag.flag-sg {background-position: -100px -60px}

        .flag.flag-th {background-position: -125px -60px}

        .flag.flag-tr {background-position: 0 -75px}

        .flag.flag-ua {background-position: -25px -75px}

        .flag.flag-us {background-position: -50px -75px}

        .flag.flag-uy {background-position: -75px -75px}

        .flag.flag-vn {background-position: -100px -75px}

        .flag.flag-ye {background-position: -125px -75px}

        .txt {

            display: table-cell;

            height: 20px;

            vertical-align: middle;

        }  

    </style>





{% endhighlight %}



Configure the template structure for AutoComplete control by including a &lt;div&gt; element with an image and text in every row of the popup panel. Assign the corresponding variable name within ${<field name>} to map them into the list.



{% highlight html %}

<ej:Autocomplete ID="AutoComplete" runat="server" DataSourceID="ObjectDataSource1" Template="<div class='flag ${Sprite}'> </div> <div class='txt'>${Text}</div>" DataTextField="Text" />

        <asp:ObjectDataSource ID="ObjectDataSource1" runat="server" SelectMethod="GetTemplateData" TypeName="ASPWeb.ObjectData"></asp:ObjectDataSource>



{% endhighlight %}





The following image is the output for AutoComplete control with template support.

![Templates](State-Persistence_images/State-Persistence_img2.png)



