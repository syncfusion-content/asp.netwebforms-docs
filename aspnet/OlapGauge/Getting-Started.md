---
layout: post
title: Getting-Started
description: getting started 
platform: aspnet
control: OLAP Gauge
documentation: ug
---

# Getting Started 

This section explains briefly about how to create an OLAP Gauge in your application with ASP.NET.

## Create your first OLAP Gauge in ASP.NET

Control Structure

The following screenshot shows the structure of an OLAP Gauge control.

{ ![](Getting-Started_images/Getting-Started_img1.png) | markdownify }
{:.image }


Syncfusion OLAP Controls – Architecture

{ ![Description: C:/Users/Narendhran Muthuvel/Desktop/blockdiagram.PNG](Getting-Started_images/Getting-Started_img2.png) | markdownify }
{:.image }


As shown in an above architecture, control rendering takes place at client-side and all other analytical operations on each action takes place at server-side.

Service for OLAP Controls

The primary reasons for using service in an OLAP processing are:

1. DataSource Connectivity: In order to establish a connection between different cube data sources such as
1. Offline Cube
2. Online Cube (XML/A)
3. Cube within SQL Server (locally or through remote), you can move the connectivity related coding to service-side as it is impossible at client-side other than Online Cube (XML/A) option. Using service, you can connect any type of cube data source without any limitation.
2. Cube Schema: As the connection is moved to service side, you obviously use MicrosoftADOMDassembly, to get the entire cube schema. Only with the cube schema the following details are achieved for control rendering.
1. Availability of cubes.
2. Complete end-to-end details such as name, caption, unique name, parent information, child information, its properties etc. about the dimension, hierarchy, level, members are available in cube schema only. 
3. Localized information is also available in cube schema.  
3. MDX Generator: You can frame the MDX query using an MDX generator in Syncfusion.Olap.Base assembly. To execute the framed MDX from the cube data source, you need to send framed MDX via Microsoft__ADOMD__assembly The executed query is returned in the form of cell set (contains values) that is converted to Pivot Engine and then to JSON data to render any OLAP controls.
4. OLAP Report: The OlapReport class in the Syncfusion.Olap.Base holds the complete information of each axes such as column, row and slicer. Using OlapReport class, you can maintain the dimension element, measure element, hierarchy name, level name as well as the member information that is included and excluded.  

As the OlapControl is the key for each and every operation, initially you need to serialize the OlapReport and send to client-side in a form of string.

When you perform any operation such as drill up/down, filtering, sorting etc., you are required to send OlapReport from the client-side to the service in a de-serialized and updated format.

Further operations are carried with updated OlapReports only and you can send the updated OlapReport back to client-side with JSON data in a serialized format again. 

This process has the OlapReport always updated. You cannot operate serialized OlapReport in client-side and hence it is carried to service having its class in Syncfusion.Olap.Base assembly to perform the update operation_._

Create an application

This section encompasses on how to configure the OLAP Gauge control in applications. You can also learn how to pass the required data to OLAP Gauge and to customize its various options according to your requirements. 

In the following example, OLAP Gauge is used to visualize the Revenue for Reseller over a Fiscal Year 2004 on the product category - Accessories.



{ ![](Getting-Started_images/Getting-Started_img3.png) | markdownify }
{:.image }


Open Visual Studio and create a new project by clicking New Project. Select the Web category, select the ASP.NET Empty Web Application template, and then click OK.

{ ![](Getting-Started_images/Getting-Started_img4.png) | markdownify }
{:.image }


Add Control in Application

1. Right click the project and select Add > New Folder.  Name the folder as olapgauge.

{ ![](Getting-Started_images/Getting-Started_img5.png) | markdownify }
{:.image }


2. Now right click on the olapgauge folder newly created and select Add > New Item.

{ ![](Getting-Started_images/Getting-Started_img6.png) | markdownify }
{:.image }


3. Select Web Form and name it as Default.aspx.


{ ![](Getting-Started_images/Getting-Started_img7.png) | markdownify }
{:.image }


4. Drag the OLAP Guage control from the Syncfusion BI Web Toolbox into the Design page.



{ ![](Getting-Started_images/Getting-Started_img8.png) | markdownify }
{:.image }


{ ![](Getting-Started_images/Getting-Started_img9.png) | markdownify }
{:.image }


5. Initialize the control using below code snippet.
> 
{ ![note](Getting-Started_images/Getting-Started_img10.jpeg) | markdownify }
{:.image }
_Note: URL value needs to be defined in order to fetch the data from the service. Default properties values need to be initialized as follows to render the control appropriately._ 

> 

[ASPX]

  &lt;ej:OlapGauge ID="OlapGauge1" runat="server" Url="../wcf/OlapGaugeService.svc" EnableTooltip="true" BackgroundColor="transparent"&gt;

        &lt;Scales&gt;

            &lt;ej:CircularScales ShowRanges="true" Radius="150" ShowScaleBar="true" Size="1"  ShowIndicators="true" ShowLabels="true"&gt;

                &lt;Border Width ="0.5" /&gt;

                &lt;PointerCollection&gt;                    

                    &lt;ej:Pointers ShowBackNeedle="true" BackNeedleLength="20"  Length="125" Width="7" &gt;&lt;/ej:Pointers&gt;

                    &lt;ej:Pointers Type="Marker" MarkerType="Diamond" DistanceFromScale="5" Placement="Center" BackgroundColor="#29A4D9" Length="25" Width="15"&gt;&lt;/ej:Pointers&gt;

                &lt;/PointerCollection&gt;

                &lt;TickCollection&gt;

                    &lt;ej:CircularTicks Type="Major" DistanceFromScale="2" Height="16" Width="1" Color="#8c8c8c" /&gt;

                    &lt;ej:CircularTicks Type="Minor" Height="6" Width="1" DistanceFromScale="2" Color="#8c8c8c" /&gt;

                &lt;/TickCollection&gt;

                &lt;LabelCollection&gt;

                    &lt;ej:CircularLabels Color="#8c8c8c"&gt;&lt;/ej:CircularLabels&gt;

                &lt;/LabelCollection&gt;

                &lt;RangeCollection&gt;

                    &lt;ej:CircularRanges DistanceFromScale="-5" BackgroundColor="#fc0606"&gt;

                        &lt;Border Color="#fc0606"/&gt;&lt;/ej:CircularRanges&gt;

                    &lt;ej:CircularRanges DistanceFromScale="-5"&gt;&lt;/ej:CircularRanges&gt;

                &lt;/RangeCollection&gt;

                &lt;CustomLabelCollection&gt;

                    &lt;ej:CircularCustomLabel Color="#666666"&gt;

                        &lt;Position X="180" Y="290" /&gt;

                        &lt;Font Size="10px" FontFamily="Segoe UI" FontStyle="Normal"&gt;&lt;/Font&gt;

                    &lt;/ej:CircularCustomLabel&gt;

                    &lt;ej:CircularCustomLabel Color="#666666"&gt;

                        &lt;Position X="180" Y="320" /&gt;

                        &lt;Font Size="10px" FontFamily="Segoe UI" FontStyle="Normal"&gt;&lt;/Font&gt;

                    &lt;/ej:CircularCustomLabel&gt;

                    &lt;ej:CircularCustomLabel Color="#666666"&gt;

                        &lt;Position X="180" Y="150" /&gt;

                        &lt;Font Size="12px" FontFamily="Segoe UI" FontStyle="Normal"&gt;&lt;/Font&gt;

                    &lt;/ej:CircularCustomLabel&gt;

                &lt;/CustomLabelCollection&gt;   

            &lt;/ej:CircularScales&gt;

        &lt;/Scales&gt;

    &lt;/ej:OlapGauge&gt;

Add References, Scripts, Styles and Control

Add References

1. In the Solution Explorer, right click the References folder and then click Add Reference.

{ ![](Getting-Started_images/Getting-Started_img11.png) | markdownify }
{:.image }


{ ![Description: C:/Users/Narendhran Muthuvel/Desktop/screenshots/sshot-4.png](Getting-Started_images/Getting-Started_img12.png) | markdownify }
{:.image }


1. Select the following assemblies: 
* Microsoft.AnalysisServices.AdomdClient.dll

Syncfusion.Core.dll 

Syncfusion.Linq.Base.dll 

Syncfusion.EJ.dll 

Syncfusion.EJ.Olap.dll

Syncfusion.Olap.Base.dll

2. Click OK.

Add Scripts and Styles

Add the script files and CSS files in the head tag of the Default.aspx page.

> { ![](Getting-Started_images/Getting-Started_img13.jpeg) | markdownify }
{:.image }
_Note: 1. Follow the given order while adding scripts and styles._

>    _2. Apart from cdn files rest of them can be acquired from the following location._

C:\Users\&lt;UserName&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version&gt;\JavaScript\assets\

[ASPX]

&lt;head&gt;

&lt;link href="http://cdn.syncfusion.com/13.1.0.21/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" /&gt;

&lt;script src="http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js"&gt; &lt;/script&gt;

&lt;script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js" type="text/javascript"&gt; &lt;/script&gt;

&lt;script src="http://cdn.syncfusion.com/13.1.0.21/js/web/ej.web.all.min.js"&gt; &lt;/script&gt;

&lt;/head&gt;



Add WCF service for OLAP Gauge

Create WCF Services

1. Right click on the project and select Add > New Folder.  Name the folder as wcf.

{ ![](Getting-Started_images/Getting-Started_img14.png) | markdownify }
{:.image }


2. Now right click the wcf folder created and select Add > New Item. 

{ ![](Getting-Started_images/Getting-Started_img15.png) | markdownify }
{:.image }


3. In the Add New Item window, select WCF Service and name it OlapGaugeService.svc. Click Add.



{ ![](Getting-Started_images/Getting-Started_img16.png) | markdownify }
{:.image }


Add service methods inside Interface

Add the following code inside the IOlapGaugeService interface available in the IOlapGaugeService.cs file.

[C#]

[ServiceContract]

    public interface IOlapGaugeService

    {

        [OperationContract]

        Dictionary<string, object> InitializeGauge(string action,string customObject);                    }

Add Namespaces

Add the following necessary namespaces required to implement the service methods.

[C#]

using System;

using System.Collections.Generic;

using System.Linq;

using System.Runtime.Serialization;

using System.ServiceModel;

using System.Text;

using System.ServiceModel.Activation;

using Syncfusion.JavaScript.Olap;

using System.Web.Script.Serialization;

using Syncfusion.Olap.Manager;

using Syncfusion.Olap.Reports;

Create Class in Service file

Create the OlapGaugeService class to implement the service methods. Inherit the class from the IOlapGaugeService interface created automatically when any new service is added.

[C#]

namespace Sample

{

    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]

    public class OlapGaugeService : IOlapGaugeService

    {

    }

}

Implement Service Methods

Add the following methods to the service invoked for any server-side operations to be performed in OlapGauge.

1. Initialize the OlapGauges helper class.

[C#]

        OlapGauge htmlHelper = new OlapGauge();       

        static string connectionString = "Data Source=http://bi.syncfusion.com/olap/msmdpump.dll; Initial Catalog=Adventure Works DW 2008 SE;";

        JavaScriptSerializer serializer = new JavaScriptSerializer();





2. Initialize the following relevant service methods need to be added.

[C#]



         //This method provides the required information from the server side for initializing the OlapGauge.

public Dictionary<string, object> InitializeGauge(string action,string customObject)

        {

            OlapDataManager DataManager = null;

            dynamic customData = serializer.Deserialize<dynamic>(customObject.ToString());



                DataManager = new OlapDataManager(connectionString);                         

            DataManager.SetCurrentReport(CreateOlapReport());

            return htmlHelper.GetJsonData(action, DataManager);

        }                

        //This method carries the information about the default report which would be rendered within OlapGauge initially. 

        private OlapReport CreateOlapReport()

        {

            OlapReport report = new OlapReport();

            report.CurrentCubeName = "Adventure Works";



            KpiElements kpiElement = new KpiElements();

            kpiElement.Elements.Add(new KpiElement { Name = "Revenue", ShowKPIGoal = true, ShowKPIStatus = true, ShowKPIValue = true, ShowKPITrend = true });



            DimensionElement dimensionElement1 = new DimensionElement();

            DimensionElement dimensionElement2 = new DimensionElement();

            DimensionElement dimensionElement3 = new DimensionElement();



            MeasureElements measureElement = new MeasureElements();

            measureElement.Elements.Add(new MeasureElement { UniqueName = "[Measures].[Customer Count]" });



            dimensionElement1.Name = "Date";

            dimensionElement1.AddLevel("Fiscal Year", "Fiscal Year");

            dimensionElement1.Hierarchy.LevelElements["Fiscal Year"].Add("FY 2004");

            dimensionElement1.Hierarchy.LevelElements["Fiscal Year"].IncludeAvailableMembers = true;



            dimensionElement2.Name = "Sales Channel";

            dimensionElement2.AddLevel("Sales Channel", "Sales Channel");

            dimensionElement2.Hierarchy.LevelElements["Sales Channel"].Add("Reseller");

            dimensionElement2.Hierarchy.LevelElements["Sales Channel"].IncludeAvailableMembers = true;



            dimensionElement3.Name = "Product";

            dimensionElement3.AddLevel("Product Model Lines", "Product Line");

            report.CategoricalElements.Add(new Item { ElementValue = dimensionElement2 });

            report.CategoricalElements.Add(new Item { ElementValue = dimensionElement1 });

            report.CategoricalElements.Add(new Item { ElementValue = kpiElement });

            report.SeriesElements.Add(new Item { ElementValue = dimensionElement3 });

            return report;

        }

Configuring Web.Config

1. You can expose services through the properties such as binding, contract and address etc. using an endpoint. In your application the service name is "Sample.OlapGaugeService" where "OlapGaugeService" is the service class name and “Sample" is the namespace name where service class appears.The following are the properties are that meet the appropriate endpoint.  

contract: This property indicates the contract of the endpoint is exposing. Here you are referring IOlapGaugeService contract and hence it is "Sample.IOlapGaugeService".

binding: In your application, you use webHttpBinding to post and receive the requests and responses between the client-end and the service-end.

behaviorConfiguration: This property contains the name of the behavior to be used in the endpoint. endpointBehaviors are illustrated as follows



[web.config]

&lt;system.serviceModel&gt;

    &lt;services&gt;

      &lt;service name="Sample.OlapGaugeService"&gt;

        <endpoint address="" behaviorConfiguration="Sample.OlapGaugeServiceAspNetAjaxBehavior"

          binding="webHttpBinding" contract="Sample.IOlapGaugeService" />

      &lt;/service&gt;

    &lt;/services&gt;

&lt;/system.serviceModel&gt;



2. The endpointBehaviors contain all the behaviors for an endpoint. You can link each endpoint to the respective behavior only using this name property. In the following code sample "Sample.OlapGaugeServiceAspNetAjaxBehavior" would point the OlapGaugeService class under the namespace Sample in OlapGaugeService.svc.cs file that is the appropriate behavior for the endpoint. 

[web.config]

&lt;system.serviceModel&gt;

    &lt;behaviors&gt;

      &lt;endpointBehaviors&gt;

        &lt;behavior name="Sample.OlapGaugeServiceAspNetAjaxBehavior"&gt;

          &lt;enableWebScript /&gt;

        &lt;/behavior&gt;

      &lt;/endpointBehaviors&gt;

    &lt;/behaviors&gt;

&lt;/system.serviceModel&gt;



3. Register the assembly in web.config file by adding the following codes.

[web.config]

&lt;system.web&gt;

      &lt;compilation debug="true" targetFramework="4.5" &gt;

        &lt;assemblies&gt;

          &lt;add assembly="Syncfusion.EJ, Version=X.X.X.X, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" /&gt;

          &lt;add assembly="Syncfusion.EJ.Olap, Version=X.X.X.X, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" /&gt;

           &lt;add assembly="Syncfusion.Olap.Base, Version=X.X.X.X, Culture=neutral, PublicKeyToken=3D67ED1F87D44C89"/&gt;

        &lt;/assemblies&gt;

      &lt;/compilation&gt;

 &lt;/system.web&gt; 

> 

> { ![note](Getting-Started_images/Getting-Started_img17.jpeg) | markdownify }
{:.image }
_Note:__x.x.x.x in the above code example refers to the current version of the Essential Studio running in your system._

4. Register the namespace in web.config file by adding the following codes.

[web.config]

&lt;system.web&gt;

 &lt;pages validateRequest="false"&gt;

      &lt;controls&gt;

          &lt;add  namespace="Syncfusion.JavaScript.Web.Olap" assembly="Syncfusion.EJ.Olap, Version=X.X.X.X, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" tagPrefix="ej"/&gt;

          &lt;add  namespace="Syncfusion.JavaScript.Web" assembly="Syncfusion.EJ.Web, Version=X.X.X.X, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" tagPrefix="ej"/&gt;

          &lt;add  namespace="Syncfusion.JavaScript.DataVisualization.Models" assembly="Syncfusion.EJ, Version=X.X.X.X, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" tagPrefix="ej"/&gt;

      &lt;/controls&gt;

   &lt;/pages&gt;

&lt;/system.web&gt; 

> 

> { ![](Getting-Started_images/Getting-Started_img18.jpeg) | markdownify }
{:.image }
_Note: In this example, “Sample” indicates the name of the project and “OlapGaugeService” indicates the name of the WCF service created. And_ x.x.x.x _in the above code example refers to the current version of the Essential Studio running in your system._

