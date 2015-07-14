---
layout: post
title: Rows
description: rows
platform: aspnet
control: TreeGrid
documentation: ug
---

## Rows

The TreeGrid rows displays the information of each row from the bounded data source.

### Row Template

Row template is used to customize the TreeGrid rows based on requirements. In TreeGrid, RowTemplateID and AltRowTemplateID properties are used for customizing the row.

RowTemplateID is used to customize all the rows in TreeGrid. For this property, ID of the row template is to be provided.

AltRowTemplateID is used to customize the alternative rows in TreeGrid. For this property, ID of the alternative row template is to be provided.





{% highlight html %}

 [ASPX]

<ej:TreeGrid runat="server" ID="TreeGridControlRowTemplate" ChildMapping="Children" RowTemplateId="rowTemplateScript" AltRowTemplateId="altRowTemplateScript">

  <columns>

     <ej:TreeGridColumn HeaderText="Employee ID" Field="EmployeeID" Width="180" />

     <ej:TreeGridColumn HeaderText="Employee Name" Field="Name" />

     <ej:TreeGridColumn HeaderText="Employee picture" Field="Address" />

      ej:TreeGridColumn HeaderText="DOB" Field="DOB" />

  </columns>            

  <EditSettings AllowEditing="true" EditMode="cellEditing"/>   

</ej:TreeGrid>



<script id="rowTemplateScript" type="text/x-jsrender">



 <tr style="background-color:#F2F2F2">



   <td class="border" style='height:30px;' >

      <div>{{:#data['EmployeeID']}}</div>

   </td>



   <td class="border" style='height:30px;' >

      <div style="font-size:14px;">{{:#data['Name']}}

        <p style="font-size:8px;">{{:#data['Designation']}}</p>

      </div>

   </td>



   <td class="border">

   <div>

     <div style="display:inline-flex !important;">

       <img src="Images/{{:#data['FullName']}}.png" /></div>

     <div style="display:inline-block;padding-left:10px;">

{{:#data['Address']}}

        <p>{{:#data['Country']}}</p>

        <p style="font-size:12px;">{{:#data['Contact']}}</p>

      </div></div>                 

     </td>



     <td class="border" style='height:30px;' >

        <div>{{:#data['DOB']}}</div>

     </td>



   </tr>



 </script>

<script id="altRowTemplateScript" type="text/x-jsrender">



  <tr style="background-color:#E6E6E6">



    <td class="border" style='height:30px;' >

       <div>{{:#data['EmployeeID']}}</div>

    </td>



    <td class="border" style='height:30px;' >

      <div style="font-size:14px;">{{:#data['Name']}}

        <p style="font-size:9px;">{{:#data['Designation']}}</p>

      </div>

    </td>



    <td class="border">

     <div>

      <div style="display:inline-flex !important;">

         <img src="Images/{{:#data['FullName']}}.png" /></div>

      <div style="display:inline-block;padding-left:10px;">

{{:#data['Address']}}

         <p>{{:#data['Country']}}</p>

         <p style="font-size:12px;">{{:#data['Contact']}}</p>

      </div></div>

    </td>



    <td class="border" style='height:30px;' >

      <div>{{:#data['DOB']}}</div>

    </td>                



  </tr>



</script>



<style type="text/css">



  .e-treegrid .e-selectionbackground {

     background-color:#CED8F6;

  } 



  .border {

     border-color:#BDBDBD;

     border-width:1px;

     border-style:solid;

   }



</style>





[ASPX.CS]

public class TemplateData

 {

   public string Name { get; set; }

   public string FullName { get; set; }

   public string Designation { get; set; }

   public string EmployeeID { get; set; }

   public string Address { get; set; }

   public string Contact { get; set; }

   public string Country { get; set; }

   public string DOB { get; set; }

   public List<TemplateData> Children { get; set; }

} 



protected void Page_Load(object sender, EventArgs e)

{

  RowTemplateData TaskCollection = new RowTemplateData();

  this.TreeGridControlRowTemplate.DataSource = TaskCollection.GetData();

  this.TreeGridControlRowTemplate.DataBind();

} 



public class RowTemplateData

{

  public List<TemplateData> GetData()

  {

      List<TemplateData> datas = new List<TemplateData>();

      datas.Add(new TemplateData()

      {

        Name = "Robert King",

        FullName = "Robert King",

        Designation = "Chief Executive Officer",

        EmployeeID = "EMP001",

        Address = "507 - 20th Ave. E.Apt. 2A, Seattle",

        Contact = "(206) 555-9857",

        Country = "USA",

        DOB = "2/15/1963",

      });

      datas[0].Children = new List<TemplateData>();

      datas[0].Children.Add(new TemplateData()

      {

         Name = "David william",

         FullName = "David william",

         Designation = "Vice President",

         EmployeeID = "EMP004",

         Address = "722 Moss Bay Blvd., Kirkland",

         Country = "USA",

         Contact = "(206) 555-3412",

         DOB = "5/20/1971",

       });

           // ...



           // ...

    return datas;

  }

 }



{% endhighlight %}



The output of TreeGrid with Row Template is as follows.



{ ![](Rows_images/Rows_img1.png) | markdownify }
{:.image }


### Row Drag and Drop

It is possible to dynamically re-arrange the rows in the TreeGrid control by using the AllowDragAndDrop property. With this property, row drag can be enabled or disabled. Rows can be inserted above, below as a sibling or as a child to the existing row with the help of this feature. A default tooltip is rendered while dragging the TreeGrid row and this tooltip can be customized by the DragTooltip property. This propertyhas inner properties such as ShowTooltip, TooltipItems and TooltipTemplate.

The ShowTooltip property is used to enable or disable the tooltip. By default, this property value is false.

The following code explains about enabling the row drag and drop with the default tooltip in the TreeGrid.





&lt;ej:TreeGrid runat="server" ID="TreeGridControlDragAndDrop" … AllowDragAndDrop="true"&gt;	 //...

         &lt;columns&gt;

                &lt;ej:TreeGridColumn HeaderText="Task Id" Field="TaskID" /&gt;

                &lt;ej:TreeGridColumn HeaderText="Task Name" Field="TaskName" /&gt;//…

         &lt;/columns&gt;

          &lt;DragTooltip ShowTooltip="true"/&gt;

        //...

   &lt;/ej:TreeGrid&gt;





The following screenshot depicts a row drag and drop in the TreeGrid.

{ ![](Rows_images/Rows_img2.png) | markdownify }
{:.image }


### Customizing Drag tooltip

The TooltipItems property is used to customize the tooltip items. By using this property, specific fields can be rendered in the tooltip. By default this property value is null, and all the defined field items are rendered in the tooltip.

The following code shows how to render row drag tooltip with the desired field items





{% highlight html %}

<ej:TreeGrid runat="server" ID="TreeGridControlDragAndDrop" … AllowDragAndDrop="true">

    //...

   <DragTooltip ShowTooltip="true" TooltipItems="TaskID,TaskName,StartDate,EndDate" />

    // ...

</ej:TreeGrid>





{% endhighlight %}

The TooltipTemplate property renders the template tooltip for row drag and drop in the TreeGrid control by using the JS Render template. You can provide either the id value of the script element or the script element to the property.

The following code shows how to render row drag tooltip with tooltip template.





{% highlight html %}

<ej:TreeGrid runat="server" ID="TreeGridControlDragAndDrop" AllowDragAndDrop="true">	 //...         

         <DragTooltip ShowTooltip="true" TooltipTemplate="#customtooltip" />

        // ...

</ej:TreeGrid>



<asp:Content ID="Content2" runat="server" ContentPlaceHolderID="ScriptSection"> 



         <script id="#customtooltip" type="text/x-jsrender">            

              <tr>

                  <td class="border" style='height:30px;' >

                     <div>{{:#data['TaskID']}}</div>

                  </td>



                  <td class="border" style='height:30px;' >

                     <div>{{:#data['TaskName']}}</div>

                  </td>



             </tr>

          </script>



</asp:Content>





{% endhighlight %}



{ ![](Rows_images/Rows_img3.png) | markdownify }
{:.image }




