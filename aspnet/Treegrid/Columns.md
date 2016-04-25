---
layout: post
title: Columns | TreeGrid | ASP.NET | Syncfusion
description: columns
platform: aspnet
control: TreeGrid
documentation: ug
---

# Columns

The TreeGrid column displays the information from a bounded data source and it is editable to update the task details through TreeGrid.

## Column Resizing

You can change the width of the column in TreeGrid to show the entire text of the column by resizing the column. The following code example shows you how to enable the Column Resize feature at Gantt initialize.

{% highlight html %}

<ej:TreeGrid runat="server" ID="TreeGridControlDefault" 

             AllowColumnResize="true"

</ej:TreeGrid>


{% endhighlight %}

## Column Template

Column Template is used to customize the column’s look and feel based on requirement.

The following code example shows you how to display the icon in the TreeGrid column.

{% tabs %}
{% highlight c# %}

TreeGrid.aspx.cs

using System;

using System.Collections.Generic;

using System.Linq;

using System.Web;

using System.Web.UI;

using System.Web.UI.WebControls;

using WebSampleBrowser.TreeGrid.Model;

namespace WebSampleBrowser.TreeGrid

{

    public partial class ColumnTemplate : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            FileInfoCollection Fileinfocollection = new FileInfoCollection();

            this.TreeGridColumnTemplate.DataSource = Fileinfocollection.GetFileInfoCollections();

            this.TreeGridColumnTemplate.DataBind();            

        }

    }



    public class FileInfoCollection

    {



        public List<FileInfo> GetFileInfoCollections()

        {

            List<FileInfo> FileinfoCollection = new List<FileInfo>();

            FileinfoCollection.Add(new FileInfo()

            {

                Name = "EJ.Web",

                DateModified = "06/16/2014",

                DateCreated = "06/16/2014",

                Type = "File Folder"

            });



            FileinfoCollection[0].SubFolder = new List<FileInfo>();



            FileinfoCollection[0].SubFolder.Add(new FileInfo()

            {

                Name = "Samples",

                DateModified = "06/26/2014",

                DateCreated = "06/16/2014",

                Type = "File Folder"

            });



            FileinfoCollection[0].SubFolder[0].SubFolder = new List<FileInfo>();



            FileinfoCollection[0].SubFolder[0].SubFolder.Add(new FileInfo()

            {

                Name = "Web",

                DateModified = "07/07/2014",

                DateCreated = "06/16/2014",

                Type = "File Folder"

            });



            FileinfoCollection[0].SubFolder[0].SubFolder[0].SubFolder = new List<FileInfo>();

            FileinfoCollection[0].SubFolder[0].SubFolder[0].SubFolder.Add(new FileInfo()

            {

                Name = "TreeGrid",

                DateModified = "07/07/2014",

                DateCreated = "06/16/2014",

                Type = "File Folder"

            });



            FileinfoCollection[0].SubFolder[0].SubFolder[0].SubFolder[0].SubFolder = new List<FileInfo>();



            FileinfoCollection[0].SubFolder[0].SubFolder[0].SubFolder[0].SubFolder.Add(new FileInfo()

            {

                Name = "ColumnTemplate",

                DateModified = "07/01/2014",

                DateCreated = "06/30/2014",

                Type = "ASPX File"

            });


            //...

           //...


            return FileinfoCollection;

        }  

    }



    public class FileInfo

    {

        public string Name { get; set; }

        public string DateModified { get; set; }

        public string Type { get; set; }

        public string DateCreated { get; set; }

        public List<FileInfo> SubFolder { get; set; }

    }

}

{% endhighlight %}

{% highlight cshtml %}


<script type="text/x-jsrender" id="customColumnTemplate">     

     <div  style='height:20px;' unselectable='on'>{{if hasChildRecords}}<div class='intend' style='height:1px; float:left; width:{{:level*20}}px; display:inline-block;'></div>

       {{else !hasChildRecords}}

       <div class='intend' style='height:1px; float:left; width:{{:(level)*20}}px; display:inline-block;'></div>

       {{/if}}                         

       <div class='{{if expanded}}e-treegridexpand {{else hasChildRecords}}e-treegridcollapse {{/if}} {{if level===4}}e-doc{{/if}}' style='height:20px;width:30px;margin:auto;float:left;margin-left:10px;

       style='float: left;display:inline-block; unselectable='on'></div>

       <div class='e-cell' style='display:inline-block;width:100%' unselectable='on'>{{:#data['Name']}}</div>

     </div>

    </script>   





<ej:TreeGrid runat="server" ID="TreeGridColumnTemplate" ChildMapping="SubFolder" >

   <columns>

      <ej:TreeGridColumn HeaderText="Name" Field="Name" IsTemplateColumn="true" TemplateID="customColumnTemplate"/>

      <ej:TreeGridColumn HeaderText="Type" Field="Type"  Width="150"/>

      <ej:TreeGridColumn HeaderText="Date Created" Field="DateCreated"  Width="150" />

      <ej:TreeGridColumn HeaderText="Date Modified" Field="DateModified"  Width="150"/>                

   </columns>            

</ej:TreeGrid>



<style type="text/css">

    .e-treegrid .e-treegridexpand {

        background-image: url(Images/folder-open.png);

        background-repeat: no-repeat;

        width: 14px;

        height: 14px;

    }

    .e-treegrid .e-treegridcollapse {

        background-image: url(Images/Folder.png);

        background-repeat: no-repeat;

        width: 14px;

        height: 14px;

    }

    .e-treegrid .e-doc {

        background-image: url(Images/Document.png);

        background-repeat: no-repeat;

        width: 14px;

        height: 14px;

    }



    .e-treegrid .e-treegridexpand:before {

        content: none;

    }



    .e-treegrid .e-treegridcollapse:before {

        content: none;

    }

</style>

{% endhighlight %}
{% endtabs %}


The following screenshot displays the customized column in TreeGrid control.

![](Columns_images/Columns_img1.png) 



## Column Filtering

Column Filtering in TreeGrid is used to filter the records by single or multiple column conditions. In TreeGrid control, column filtering can be enabled with AllowFiltering property, by setting this property to ‘true’, a filter bar is rendered in all available columns, providing filtering support to every columns. You can also limit filtering to specific column by setting ‘false’ to AllowFiltering property in each column object.

Filtering modes can be toggled between Immediate and OnEnter modes using FilterBarMode property.

* Immediate- In this mode, filtering starts with key press event.
* OnEnter- In this mode, filtering starts when enter key is pressed.

Filtering type can be defined by FilterEditType property in each column object.

### FilterEditType:

* String edit
* Numeric edit
* Boolean edit
* Dropdownlist
* Datepicker
* Datetimepicker

{% highlight html %}

<ej:TreeGrid runat="server" ID="TreeGridControlFiltering" ChildMapping="SubTasks" AllowFiltering="true" TreeColumnIndex="1"> 

     //..
          <columns>

                <ej:TreeGridColumn HeaderText="Task Id" Field="TaskID" Width="45" EditType="Numeric" AllowFiltering="false"/>

                <ej:TreeGridColumn HeaderText="Task Name" Field="TaskName" EditType="String" FilterEditType="String"/>

                <ej:TreeGridColumn HeaderText="Start Date" Field="StartDate" EditType="Datepicker" FilterEditType="Datepicker"/>

                <ej:TreeGridColumn HeaderText="End Date" Field="EndDate" EditType="Datepicker" FilterEditType="Datepicker"/>

                <ej:TreeGridColumn HeaderText="Duration" Field="Duration" EditType="Numeric" FilterEditType="Numeric"/>

                <ej:TreeGridColumn HeaderText="Progress" Field="Progress" EditType="Numeric" FilterEditType="Numeric"/>

           </columns>               

     // ...

</ej:TreeGrid>

{% endhighlight %}



The following screenshot displays the column filtering in TreeGrid control.

![](Columns_images/Columns_img2.png) 



## Column Chooser

TreeGrid supports enabling and disabling the visibility of the columns dynamically with the ShowColumnChooser property. By using this property, the visibility of the custom columns can also be toggled. The Column chooser option is rendered as sub menu item within column menu in the TreeGrid columns.

 ![](Columns_images/Columns_img3.png)
 
The column menu is enabled with the ShowColumnChooser property and the default value for this property is false

The column menu provides the following options

* Sort Ascending
* Sort Descending
* Columns 

The Sort Ascending and Sort Descending options are enabled or disabled by using the AllowSorting property. With these options, single level sorting can be performed in the TreeGrid columns. To perform multilevel sorting, the AllowMultiSorting property should be enabled. 

You can also disable the visibility of the particular column in column collection manually by setting the Visible property to false.

{% highlight html %}

<ej:TreeGrid ID="treegrid1" runat="server" ShowColumnChooser="true"

             AllowSorting="true" AllowMultiSorting="true" >

    // ...

    <Columns>

         // ...

         <ej:TreeGridColumn field="duration" HeaderText="Duration" Visible="false">

         // ...

    </Columns>

    // ...

</ej:TreeGrid>

{% endhighlight %}

![](Columns_images/Columns_img4.png) 