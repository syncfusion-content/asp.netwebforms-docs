---
title: How To | ListView | ASP.NET Webforms | Syncfusion
description: “How to do” section for ListView
platform: aspnet
control: ListView
documentation: UG
keywords: ListView,  Syncfusion, EJ MVC Webforms, UG document, How To
---
# How To

## Get the selected values on post back

**Single selection**

Enable the property [PersistSelection](https://help.syncfusion.com/api/js/ejlistview#members:persistselection) in order to use selection in ListView. Then use the [getActiveItemText](https://help.syncfusion.com/api/js/ejlistview#methods:getactiveitemtext) method take the selected active text through javascript and then pass it to the controller via AJAX. 

 
{% highlight html %}

<ej:ListView ID="ListView1" runat="server" Height="450" Width="400" PersistSelection="true">

        <Items>
            <ej:ListViewItems Text="Artwork"></ej:ListViewItems>
            <ej:ListViewItems Text="Abstract"></ej:ListViewItems>
            <ej:ListViewItems Text="2 Acrylic Mediums"></ej:ListViewItems>
            <ej:ListViewItems Text="Creative Acrylic"></ej:ListViewItems>
            <ej:ListViewItems Text="Modern Painting"></ej:ListViewItems>
            <ej:ListViewItems Text="Canvas Art"></ej:ListViewItems>
            <ej:ListViewItems Text="Black white"></ej:ListViewItems>
            <ej:ListViewItems Text="Children"></ej:ListViewItems>
            <ej:ListViewItems Text="Preschool Crafts"></ej:ListViewItems>
            <ej:ListViewItems Text="School-age Crafts"></ej:ListViewItems>
        </Items>

</ej:ListView>

      <input id="btn" type="button" value="Post" onclick="Selecteddata()" />

<script>

        function Selecteddata() {

            var text = $("#<%=ListView1.ClientID%>").ejListView("getActiveItemText");

            $.ajax({
                type: "POST",
                url: "Default.aspx/Getselecteddata",
                data: { value: text },
                contentType: "application/json; charset=utf-8",
                dataType: "json",
                success: function (response) {
                    alert(response);
                },
                failure: function (response) {
                    alert("Error");
                }
            });

        }

    </script>

    
{% endhighlight %}

    
    {% highlight c# %}
    
     [System.Web.Services.WebMethod]

        public static string Getselecteddata(string value)
        {

            string selectedval = value;
            return selectedval;
        }

    
    {% endhighlight %}



**Multiple selection**

Multiple items can be selected by using [EnableCheckMark](https://help.syncfusion.com/api/js/ejlistview#members:enablecheckmark) property. Hence we need to use the [getCheckedItemsText](https://help.syncfusion.com/api/js/ejlistview#methods:getcheckeditemstext) method to take all the checked items and then pass it to the controller using javascript AJAX. 


{% highlight html %}

<ej:ListView ID="ListView1" runat="server" Height="450" Width="400" EnableCheckMark="true">

        <Items>
            <ej:ListViewItems Text="Artwork"></ej:ListViewItems>
            <ej:ListViewItems Text="Abstract"></ej:ListViewItems>
            <ej:ListViewItems Text="2 Acrylic Mediums"></ej:ListViewItems>
            <ej:ListViewItems Text="Creative Acrylic"></ej:ListViewItems>
            <ej:ListViewItems Text="Modern Painting"></ej:ListViewItems>
            <ej:ListViewItems Text="Canvas Art"></ej:ListViewItems>
            <ej:ListViewItems Text="Black white"></ej:ListViewItems>
            <ej:ListViewItems Text="Children"></ej:ListViewItems>
            <ej:ListViewItems Text="Preschool Crafts"></ej:ListViewItems>
            <ej:ListViewItems Text="School-age Crafts"></ej:ListViewItems>
        </Items>

</ej:ListView>

      <input id="btn" type="button" value="Post" onclick="Selecteddata()" />


<script>

        function Selecteddata() {

            var text = $("#<%=ListView1.ClientID%>").ejListView("getCheckedItemsText");

            $.ajax({
                type: "POST",
                url: "Default.aspx/Getselecteddata",
                data: { value: text },
                contentType: "application/json; charset=utf-8",
                dataType: "json",
                success: function (response) {
                    alert(response);
                },
                failure: function (response) {
                    alert("Error");
                }
            });

        }

    </script>

    
{% endhighlight %}


    
{% highlight c# %}
    
   [System.Web.Services.WebMethod]
        public static string Getselecteddata(object value)
        {

            var val = value;
            return "Selected item value is " + val;
        }

    
    {% endhighlight %}
    
