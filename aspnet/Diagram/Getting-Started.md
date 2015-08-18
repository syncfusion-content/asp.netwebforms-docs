---
layout: post
title: Getting-Started
description: getting started
platform: aspnet
control: Diagram
documentation: ug
---

# Getting Started

This section explains briefly how to create the Diagram in your application with ASP.NET.

## Control Structure

The following screenshot illustrates the structure of the Diagram control.



![](Getting-Started_images/Getting-Started_img1.png) 

 _Diagram_

## Create your first Diagram in ASP.NET

### Initialize Diagram

1. Create an ASPX file and add the necessary script and CSS files in the &lt;Head&gt; tag as shown in the following code example.
   
   ~~~ html

		<html xmlns="http://www.w3.org/1999/xhtml">

			<head>

				<title>

					Getting Started with the Diagram control for ASP.Net

				</title>



				<!-- jQuery Script -->

                <script src="http://code.jquery.com/jquery-1.10.2.min.js"></script>

					<!--script to create Diagram-->

                <script src="http://cdn.syncfusion.com/js/ej.widgets.all-latest.min.js"></script>

			</head>

			<body>
		
			
			</body>
			
		</html>

   ~~~
   {:.prettyprint }

2. Add the <ej:Diagram> element in the <body> tag to render the Diagram.

   ~~~ html
   
        <html>
		
		<body>
		
		    <ej:Diagram ID="DiagramContent" runat="server" Height="600px" Width="600px">
			
			</ej:Diagram>
			
		</body>
		
		</html>		
		
   ~~~
   {:.prettyprint }



3. This creates an empty Diagram. In the following section, you can learn how to add employee details in the Diagram.

   ![http://help.syncfusion.com/ug/js/ImagesExt/image147_3.png](Getting-Started_images/Getting-Started_img2.png) 

   _Empty Diagram_


### Initialize Data

Initially, you can create hierarchical employee information, JSONData, and assign it to a variable data.



{% highlight html %}

<head>

    <!-- ... -->

    <script type="text/javascript">

//Initialize data source

 var data =

  [{"name": "Elizabeth", "fillColor": "rgb(0, 139, 139)" },

   {"name": "Christina", "fillColor": "rgb(30, 30, 113)",

    "ReportingPerson": "Elizabeth"},

   {"name": "Yoshi", "fillColor": "rgb(0, 100

     0)","ReportingPerson":"Christina" },

   {"name": "Philip", "fillColor": "rgb(0, 100, 0)", 

    "ReportingPerson": "Christina"},

   {"name": "Yang", "fillColor": "rgb(30, 30, 113)", 

    "ReportingPerson": "Elizabeth"},

   {"name": "Roland", "fillColor": "rgb(0, 100, 0)", 

    "ReportingPerson": "Yang" },

   {"name": "Yvonne", "fillColor": "rgb(0, 100, 0)", 

    "ReportingPerson": "Yang"}];   

 </script>

</head>



{% endhighlight %}

### Populate Organizational Chart

You can populate the organizational chart by specifying the necessary fields of data source.

{% highlight c# %}

//Customizes node before rendering

function nodeTemplate(diagram, node) {

     node.labels[0].text = node.Name; 

 }

//Initializes the node template.

 $(window).load(function () {

     $("#DiagramWebControl1").ejDiagram({ nodeTemplate: nodeTemplate  });

 });  



{% endhighlight %}



{% highlight c# %}

  DiagramWebControl1.Model.Width = "70px";

  DiagramWebControl1.Model.Height = "30px";



//Uses automatic layout to arrange elements on the page

  DiagramWebControl1.Model.Layout.Type = LayoutTypes. HierarchicalTree;

  DiagramWebControl1.Model.Layout.MarginY = 50;

  DiagramWebControl1.Model.Layout.HorizontalSpacing = 50;

  DiagramWebControl1.Model.Layout.VerticalSpacing = 50;



//Configures data source for diagram

  DiagramWebControl1.Model.DataSourceSettings.DataSource = GetOrgChartData();

  DiagramWebControl1.Model.DataSourceSettings.Parent = "ReportingPerson";

  DiagramWebControl1.Model.DataSourceSettings.Id = "name";



//Sets the default properties of the nodes.

  DiagramWebControl1.Model.DefaultSettings.Node = new Node() { 

      Width = 70, 

      Height = 30,

      Shape = { type: "rectangle","cornerRadius": 5 },

  };

  Label label = new Label() { 

        Name = "label1",

        FontSize = 11, 

        Bold = true, 

        FontFamily = "Segoe UI", 

  };



 DiagramWebControl1.Model.DefaultSettings.Node.Labels.Add(label);



//Sets the default properties of the connectors.

 DiagramWebControl1.Model.DefaultSettings.Connector = new Connector() {

    Segments = new Collection() { new Segment(Segments.Orthogonal) },

    TargetDecorator = new Decorator() { Shape = DecoratorShapes.Arrow }

 },



 public Array GetOrgChartData(){

// Returns datasource

   }

{% endhighlight %}



The employee data is displayed in the following Diagram.



![](Getting-Started_images/Getting-Started_img3.png) 

 _Diagram_


