---
layout: post
title: Getting Datasource of Grid in Sorted Order | Grid | ASP.NET Webforms | Syncfusion
description: Getting Datasource of Grid in Sorted Order
platform: aspnet
control: Grid
documentation: ug
---

## Getting Datasource of Grid in Sorted Order

Grid column can be sorted and after sorting, the datasource can be obtained in the same order using `sortBy` query and `executeLocal` method of DataManager.

The following code example describes the above behavior.

{% tabs %}

 {% highlight html %}

<ej:Button ID="sort" runat="server" Type="Button" Text="GetSorteDdata" ClientSideOnClick="GetSortedData">

</ej:Button>

 <ej:Grid ID="FlatGrid" runat="server" AllowSorting="True" AllowMultiSorting="true" AllowPaging="True">
 
            <Columns>
 
                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" />
                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="80" />
                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="75" Priority="4" />
                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="110" Priority="2" />
 
            </Columns>
 
  </ej:Grid>
  
  {% endhighlight %}
  
  {% highlight js %}

<script type="text/javascript">

 function GetSortedData(args) {
            var obj = $(".e-grid").ejGrid("instance");   
            var Sort = obj.model.sortSettings.sortedColumns;  
            var query = ej.Query();               
            if(obj.model.sortSettings.sortedColumns.length){
                for(var i=Sort.length-1;i>=0;i--){        
                  query.sortBy(Sort[i].field, Sort[i].direction); 
                }
            var SortedDatasource = ej.DataManager(obj.model.dataSource).executeLocal(query); 
                  console.log(SortedDatasource); 
    }
}

</script>

{% endhighlight %}

{% highlight c# %}

 public partial class _Default : Page
    {


        protected void Page_Load(object sender, EventArgs e)
        {

            this.FlatGrid.DataSource = OrderRepository.GetAllRecords().ToList();
            this.FlatGrid.DataBind();
        }

    }
	
{% endhighlight %}

{% endtabs %}

N>  This solution will work only for local data.