---
layout: post
title: Getting started for Syncfusion Essential ASP.NET
description: How to create simple ASP.Net Application with Syncfusion Essential ASP.NET controls 
platform: aspnet
control: Introduction
documentation: ug

---
# Getting Started

This section describes how to configure the Syncfusion ASP.NET components into the ASP.NET applications. There are three ways for embedding our controls into ASP.NET application:

1. Using Syncfusion Project Template
2. Through Syncfusion NuGet Packages
3. Through Manual Integration into the new/existing Application

The procedure that are followed in manual integration process is entirely automated, when we create an application using Syncfusion Project template.

## Using Syncfusion Project Template
For creating new ASP.NET Website, you can use the Syncfusion’s Visual Studio project templates. Here, you will see how to add the `DatePicker` control into the ASP.NET Website selecting from the “New Web Site” pop-up,

* Start the Visual Studio and select File -> New -> Website. You can now see the built-in `Syncfusion ASP.NET Website` template in the "New Web Site" pop-up as shown below

![](Getting-Started_images/Getting-Started_img1.png)
Visual Studio 2012 - New Web Site Pop-up
{:.caption}

* Type the application name and click `OK`. This will create a new Web Site with all the Syncfusion ASP.NET control’s client and server side dependencies are preconfigured and copied to it appropriate folders

* Now you can add your required controls in the ASPX Page. The code for adding `DatePicker` control within the "Default.aspx" file is follows

{% highlight html %}

<ej:DatePicker ID="DatePicker" runat="server"></ej:DatePicker>

{% endhighlight %}

* Another way of adding control into the Default.aspx page is by making use of the Toolbox option present in the Visual Studio. You need to just drag the required control from the toolbox and then drop it into the Content section of the Default.aspx page and the required control code automatically gets generated

![](Getting-Started_images/Getting-Started_img2.png)
Toolbox
{:.caption}

* Finally build and run the project by pressing F5, so that you can now see the output similar to the below screenshot in your web browser.

![](Getting-Started_images/Getting-Started_img13.png)
DatePicker control displayed in web browser
{:.caption}

N> The Script Manager is mandatory in order to place our control initialization script in the page.<BR>
Ensure whether the “ScriptManager” is added in the “Site.Master” or else add the “ScriptManager” to your web page. <BR>
You just need to drag the “ScriptManager” from the toolbox under the “AJAX Extension” and then drop it into the Content section of the Default.aspx page, so that the required scripts to initiate our component will be added to your web page. 

{% highlight html %}

     <asp:ScriptManager ID="ScriptManager1" runat="server"> 
     </asp:ScriptManager> 
     
{% endhighlight %}

## Configuring Syncfusion NuGet Packages in Visual Studio 

This topic explains how to add the Syncfusion ASP.NET Web controls into the new ASP.NET Web Forms application by making use of Syncfusion NuGet Packages. 

Syncfusion ASP.NET Web Forms NuGet packages are available [here](http://nuget.syncfusion.com/package/aspnet).

### NuGet Configuration  

The steps to install the Syncfusion ASP.NET Web Forms NuGet Packages in Visual Studio are as follows,

1. In Visual Studio, navigate to `Tools | NuGet Package Manager | Package Manager Settings`, the options dialog will appear on the screen as shows below,

   ![](Getting-Started_images/NuGetConfig1.jpeg)

2. Select `NuGet Package Manager | Package Sources` and click `Add` button to add the `Package Name` and `Package Source` of Syncfusion NuGet Packages.    

   **Name**: Name of the package that listed in Available package sources  
   **Source**: Syncfusion ASP.NET Web Forms NuGet Package feed URL 
   [http://nuget.syncfusion.com/aspnet](http://nuget.syncfusion.com/aspnet)
    
   ![](Getting-Started_images/NuGetConfig2.jpeg)

   N> The `Source` text box in the above image denotes the location of the NuGet packages and the `Name` section, allows you to provide a unique name for NuGet Packages Source.
    
I> Syncfusion other platforms NuGet packages feed links are available [here](http://nuget.syncfusion.com/)

### Creating ASP.NET Web Application
Start the Visual Studio. Create a new Web Forms application by using File -> New -> Project and run the application by pressing Ctrl+F5, which shows something similar to the following screenshot in your web browser,

![](Getting-Started_images/Getting-Started_img9.png)
Empty Application when run on the web browser
{:.caption}

### NuGet Installation

Syncfusion ASP.NET Web Forms NuGet can install once configured the package source. The NuGet installation steps as below,

1. Once configured the Package source with Syncfusion NuGet Packages, right click on project and choose `Manage NuGet Packages | Online | <Package Source Name>`.

   ![](Getting-Started_images/NuGetConfig3.jpeg)

2. The NuGet Packages are listed which are available in package source location. Install the required packages to your application by clicking `Install` button.

   N> NuGet packages can be install directly through the **command line** (Package Manager Console). Further details click [here](http://help.syncfusion.com/extension/syncfusion-nuget-packages/nuget-install-and-configuration#install-from-package-manager-console)

### Adding dependent Scripts and CSS references in Site.Master
Syncfusion NuGet package will copy all the dependent Scripts and CSS files in the appropriate folders of the project. However you need to manually add the references for those files in the Site.Master page. The code snippet for this is follows.

{% highlight html %}
<head runat="server">
  <!-- Insert the following content within "head" tag -->
  <link href="Content/ej/web/default-theme/ej.web.all.min.css" rel="stylesheet" />
  <!-- If your head section already contain jQuery reference, please remove this jQuery reference -->
  <script src='<%= Page.ResolveClientUrl("~/Scripts/jquery-1.10.2.min.js")%>' type="text/javascript"></script>
  <script src='<%= Page.ResolveClientUrl("~/Scripts/jquery.easing.1.3.min.js")%>' type="text/javascript"></script>
  <script src='<%= Page.ResolveClientUrl("~/Scripts/jsrender.min.js")%>' type="text/javascript"></script>
  <script src='<%= Page.ResolveClientUrl("~/Scripts/ej/ej.web.all.min.js")%>' type="text/javascript"></script>
  <script src='<%= Page.ResolveClientUrl("~/Scripts/ej/ej.webform.min.js")%>' type="text/javascript"></script>
</head>
{% endhighlight %}

### Adding Syncfusion ASP.NET control
Here, you will see how to add the `DatePicker` control into the newly created Syncfusion ASP.NET Web Application. To add the control in the Application, you can use either of the following two ways,

* Add the below `DatePicker` code within the “Default.aspx” file

{% highlight html %}
<ej:DatePicker ID="DatePicker" runat="server"></ej:DatePicker>
{% endhighlight %}

* Another way of adding control into the Default.aspx page is by making use of the Toolbox option present in the Visual Studio. When you install Essential Studio or ASP.NET setup in your machine, all the available ASP.NET controls are automatically configured into the Visual Studio Toolbox. You just need to drag the required control from the toolbox and then drop it into the Content section of the Default.aspx page, so that the required control code automatically gets generated

![](Getting-Started_images/Getting-Started_img12.png)
Toolbox
{:.caption}

* Now build and run the project by pressing F5, so that you can now see the output similar to the below screenshot in your web browser,

![](Getting-Started_images/Getting-Started_img13.png)
 DatePicker control displayed on the web browser
 {:.caption}
 
N> The Script Manager is mandatory in order to place our control initialization script in the page.<BR>
Ensure whether the “ScriptManager” is added in the “Site.Master” or else add the “ScriptManager” to your web page. <BR>
You just need to drag the “ScriptManager” from the toolbox under the “AJAX Extension” and then drop it into the Content section of the Default.aspx page, so that the required scripts to initiate our component will be added to your web page. 

{% highlight html %}

     <asp:ScriptManager ID="ScriptManager1" runat="server"> 
     </asp:ScriptManager> 
     
{% endhighlight %}

### Updating a NuGet Package

Using the `Manage NuGet Packages` in Visual Studio, NuGet packages can be update.
 
1. Right click on Project and Navigate to the `Manage NuGet Packages` and click on the `Updates` tab to check for updates.

2. Select the `Updates -> <Syncfusion Package Source>`. Refer to the following screenshot for more information.

   ![](Getting-Started_images/NuGetConfig4.jpeg)

3. If there is a new version of NuGet you will see it in the list of available updates.

4. Select NuGet Package in the list and click `Update`. When the update is complete, close and re-open all open instances of Visual Studio.

   N> By clicking `Update All` button, all NuGet packages are getting update. When the update is complete, close and re-open all open instances of Visual Studio.

## Manual Integration of Syncfusion ASP.NET controls into the new/existing Application
This topic mainly focus on how to integrate the Syncfusion ASP.NET controls manually into the newly created/existing ASP.NET Web Forms application.

### Creating ASP.NET Web Application
Start the Visual Studio. Create a new Web Forms application by using File -> New -> Project and run the application by pressing Ctrl+F5, which shows something similar to the following screenshot in your web browser,

![](Getting-Started_images/Getting-Started_img14.png)
Empty application when run on the web browser
{:.caption}

### For Existing Applications
If you want to add our Syncfusion ASP.NET controls into your existing application, open your application and proceed with the following steps.

### Adding required CSS files
To render the Syncfusion ASP.NET controls with its unique style and theme, it is necessary to refer the required CSS files into your application. You need to copy all the required CSS files into your application from the following location,

N> <installed location>\Syncfusion\Essential Studio\13.1.0.21\JavaScript\assets\css\web
N> For example, If you have installed the Essential Studio within C:\Program Files (x86), then navigate to the below location,
N> C:\Program Files (x86)\Syncfusion\Essential Studio\13.1.0.21\JavaScript\assets\css\web

When you navigate to the above location, you can find the files shown in the below image, which you need to copy entirely and paste it into your root application. 

![](Getting-Started_images/Getting-Started_img15.png)
CSS files to be copied from the installed location
{:.caption}

Before pasting it into your application, create a folder structure with names ej/web within the Content folder of your application and place all the copied files into it as shown below,

![](Getting-Started_images/Getting-Started_img16.png)
Solution Explorer - Project with CSS files copied into the Content folder
{:.caption}

N> The common-images folder is needed to be copied into your application mandatorily, as it includes all the common font icons and other images required for the control to render.

Once the CSS files are added in your application, include the reference to "ej.web.all.min.css" file in the Site.Master page, within the head section.

{% highlight html %}

<link href="Content/ej/web/default-theme/ej.web.all.min.css" rel="stylesheet" />

{% endhighlight %}

### Adding required Script files
Essential ASP.NET controls has the following list of external JavaScript dependencies. 

* jQuery-1.10.2.min.js
* jquery.easing.1.3.min.js
* jsrender.min.js


Apart from the above external dependencies, each control has its own list of internal dependencies. This dependencies are listed within each component documentation. For the getting started, you can use “ej.web.all.min.js” file which encapsulates all the `ej` controls and frameworks in one single file. Also, Essential ASP.NET controls has additional script dependency to “ej.webform.min.js” which is responsible for raising server-side events.
The dependencies are available in the following locations of your machine. Please copy these files from location given

<table>
<tr>
<th>Files</th>
<th>Location</th>
</tr>
<tr>
<td>jquery-1.10.2.min.js<br/>jQuery.easing.1.3.min.js<br/>jsrender.min.js</td>
<td>&lt;Syncfusion Installed Location&gt;\Essential Studio\13.1.0.21\JavaScript\assets\external</td>
</tr>
<tr>
<td>ej.web.all.min.js</td>
<td>&lt;Syncfusion Installed Location&gt;\Essential Studio\13.1.0.21\JavaScript\assets\scripts\web</td>
</tr>
<tr>
<td>ej.web.all.min.js</td>
<td>&lt;Syncfusion Installed Location&gt;\Essential Studio\13.1.0.21\JavaScript\assets\scripts\common</td>
</tr>
</table>

N> Example for "Syncfusion Installed location" is "C:\Program Files (x86)\Syncfusion"

Now, create a folder named `ej`, under the Scripts folder of your application and place the copied files ej.web.all.min.js and ej.webform.min.js into it as shown below,

![](Getting-Started_images/Getting-Started_img17.png)
Solution Explorer - Script files copied into the Scripts folder of the project
{:.caption}

Once the scripts are added in your application, now it is necessary to include the reference to it in your application. This should be done within the Site.Master file, as we did previously for CSS files. 
Add the below script references in the Site.Master file within the head section,

{% highlight html %}

<link href="Content/ej/web/default-theme/ej.web.all.min.css" rel="stylesheet" />
<script src='<%= Page.ResolveClientUrl("~/Scripts/jquery-1.10.2.min.js")%>' type="text/javascript"></script>
<script src='<%= Page.ResolveClientUrl("~/Scripts/jquery.easing.1.3.min.js")%>' type="text/javascript"></script>
<script src='<%= Page.ResolveClientUrl("~/Scripts/jsrender.min.js")%>' type="text/javascript"></script>
<script src='<%= Page.ResolveClientUrl("~/Scripts/ej/ej.web.all.min.js")%>' type="text/javascript"></script>
<script src='<%= Page.ResolveClientUrl("~/Scripts/ej/ej.webform.min.js")%>' type="text/javascript"></script>

{% endhighlight %}

### Assembly Reference
Refer the following assemblies in your newly created ASP.NET application, which allows you to use any of the Syncfusion ASP.NET controls within it.

* Syncfusion.EJ
* Syncfusion.EJ.Web

Once you have installed the Essential Studio package in your system, the Syncfusion assemblies are automatically registered in the GAC. You can easily add the reference to your application using `Project -> Add Reference` and selecting the mentioned Assemblies in dialog shown

![](Getting-Started_images/Getting-Started_img18.png)
Reference Manager Pop-up
{:.caption}

### Adding Control to the Page
When you install Essential Studio or ASP.NET setup in your machine, all the available ASP.NET controls are automatically configured into the Visual Studio Toolbox. 
You just need to drag the required control from the toolbox and then drop it into the Content section of the Default.aspx page, so that the required control code gets generated automatically.

![](Getting-Started_images/Getting-Started_img19.png)
Toolbox
{:.caption}

![](Getting-Started_images/Getting-Started_img20.png)
Default.aspx page with DatePicker control code and assembly registered for it at the top
{:.caption}

### Registering Assemblies within the Web.config file
In your application’s web.config file, add the below assembly information within the &lt;assemblies&gt; tag and &lt;controls&gt; tag.

{% highlight xml %}
<system.web>
  <compilation debug="true" targetFramework="4.5">
    <assemblies>
	  <add assembly="Syncfusion.EJ, Version=13.1450.0.21, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
	  <add assembly="Syncfusion.EJ.Web, Version=13.1450.0.21, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />
	</assemblies>
  </compilation>
  <controls>
      <add namespace="Syncfusion.JavaScript.Web" assembly="Syncfusion.EJ.Web, Version=13.1450.0.21, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" tagPrefix="ej"/>
      <add namespace="Syncfusion.JavaScript.Web" assembly="Syncfusion.EJ, Version=13.1450.0.21, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" tagPrefix="ej"/>
      <add namespace="Syncfusion.JavaScript.Models" assembly="Syncfusion.EJ, Version=13.1450.0.21, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" tagPrefix="ej"/>
  </controls>
</system.web>
{% endhighlight %}

Finally build and run the project by pressing F5, so that you can now see the output similar to the below screenshot in your web browser,

![](Getting-Started_images/Getting-Started_img21.png)
DatePicker control displaying on the web browser
{:.caption}

N> The Script Manager is mandatory in order to place our control initialization script in the page.<BR>
Ensure whether the “ScriptManager” is added in the “Site.Master” or else add the “ScriptManager” to your web page. <BR>
You just need to drag the “ScriptManager” from the toolbox under the “AJAX Extension” and then drop it into the Content section of the Default.aspx page, so that the required scripts to initiate our component will be added to your web page. 

{% highlight html %}

     <asp:ScriptManager ID="ScriptManager1" runat="server"> 
     </asp:ScriptManager> 
     
{% endhighlight %}
