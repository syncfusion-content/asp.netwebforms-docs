---
layout: post
title: Welcome to Syncfusion Essential ASP.NET
description: Overview of Syncfusion Essential ASP.NET widgets based on ASP syntax.
platform: ASP
control: Introduction
documentation: ug

---
# Overview

Essential Studio for ASP.Net is a set of server-side wrappers for Essential JavaScript controls which enables you to create Essential Studio’s HTML5 JavaScript controls through ASP.Net Designer and/or Code Behind file. It includes rich designer support, server-side events and better ViewState handling for all server-side wrappers. 
## How to best read this user guide

* The best way to get started would be to read the common “[Getting Started](#Getting_Started)” document then read the “Getting Started” document of the component that you would like to start using first. The “Getting Started” guide gives just enough information that you need to know before starting to write code. This is the only section that we recommend reading end-to-end before starting to write code, all other information can be referred as needed.

* Now that you are familiar with the basics of using the component, the next step would be to start integrating the component into your application. A good starting point would be to refer to the code snippets in the [online sample browser](http://asp.syncfusion.com/demos/web/#) which contains hundreds of code samples, it is very likely that you will find a code sample that resembles your intended usage scenario.

* After you have integrated the component into your application using one of the sample code snippets as a starting point, it is likely that you would want additonal information on specific features and API. The best option would be to search a the specific topic using the search box that is available at the top of the user guide.

* Another valuable resource is the [API reference](http://help.syncfusion.com/js/api#) which provides detailed information on the object hierarchy as well as the settings available on every object.

## Additional help resources

* The [Knowledge Base](http://www.syncfusion.com/kb/aspnet#) section contains responses to some of the most common questions that other customers have asked us in the past so this would be a good place to search for topics that are not covered in the user guide.

* Similar to the [Knowledge Base](http://www.syncfusion.com/kb/aspnet#), the [forum](http://www.syncfusion.com/forums/aspnet#) section also contains responses to questions that other customers have asked us in the past.

## Create a support incident


If you are still not able to find the information that you are looking for in the self-help resources mentioned above then please [contact us](http://www.syncfusion.com/support/#) by creating a support ticket.
# Getting Started

This section describes how to configure the Syncfusion ASP.NET components into the ASP.NET applications. There are three ways for embedding our controls into ASP.NET application:
1. Using Syncfusion Project Template

2. Through Syncfusion NuGet Packages

3. Through Manual Integration into the new/existing Application

The procedure that are followed in manual integration process is entirely automated, when we create an application using Syncfusion Project template.
## Using Syncfusion Project Template

For creating new ASP.Net Website, you can use the Syncfusion’s Visual Studio project templates. Here, you will see how to add the `DatePicker` control into the ASP.NET Website selecting from the “New Web Site” pop-up,
1. Start the Visual Studio and select File -> New -> Website. You can now see the built-in `Syncfusion ASP.NET Website` template in the "New Web Site" pop-up as shown below
![](Overview_images/Overview_img1.png)

2. Type the application name and click `OK`. This will create a new Web Site with all the Syncfusion ASP.Net control’s client and server side dependencies are preconfigured and copied to it appropriate folders

3. Now you can add your required controls in the ASPX Page. The code for adding `DatePicker` control within the "Default.aspx" file is follows
{% highlight html %}
<table>
<tr>
<td colspan=1 rowspan=1>
<br/><br/><ej:DatePicker ID="DatePicker" runat="server"></ej:DatePicker><br/><br/></td></tr>
</table>
{% endhighlight %}
4. Another way of adding control into the Default.aspx page is by making use of the Toolbox option present in the Visual Studio. You need to just drag the required control from the toolbox and then drop it into the Content section of the Default.aspx page and the required control code automatically gets generated
![](Overview_images/Overview_img2.png)

5. Finally build and run the project by pressing F5, so that you can now see the output similar to the below screenshot in your web browser.

![](Overview_images/Overview_img3.jpeg)

## Through Syncfusion NuGet Packages

This topic explains how to add the Syncfusion ASP.NET Web controls into the new ASP.NET Web Forms application by making use of Syncfusion NuGet Packages. 
### Configuring Syncfusion NuGet Packages

The steps to download and configure the required Syncfusion NuGet Packages in Visual Studio are as follows,
1. Download the Syncfusion NuGet Packages for ASP.NET from [here](http://nuget.syncfusion.com/login#) and save it in your system. The downloaded file is a zip formatted file, therefore unzip the folders and copy only the below specified packages present within it. Create a new folder namely NuGet Packages in any of the particular location in your system and place the below specified files into it
![](Overview_images/Overview_img4.png)
<table>
<tr>
<td colspan=1 rowspan=1>
N> For rendering Syncfusion ASP.NET components within the web application, the script and stylesheet references are mandatory. Installing ASP.NET NuGet package automatically includes all the required scripts as well as the stylesheets to the application.<br/><br/></td></tr>
</table>
2. In Visual Studio, navigate to Tools -> Library Package Manager -> Package Manager Settings, the Options pop-up will appear on the screen as below
![](Overview_images/Overview_img5.png)

3. Select Package Manager -> Package Sources in the above pop-up and click on the ![](Overview_images/Overview_img6.jpeg)
button to navigate to the location where the above collection of NuGet packages are located (namely, within the NuGet Packages folder) in your system
![](Overview_images/Overview_img7.png)
<table>
<tr>
<td colspan=1 rowspan=1>
N> The Source textbox in the above image denotes the location of the NuGet packages in your machine and the Name section, allows you to provide a unique name which we will refer in the package installation section later. <br/></td></tr>
</table>
4. Now click the Add button and the package name will be listed in the Available package sources list as shown below and then Click OK.


![](Overview_images/Overview_img8.png)

### Creating ASP.NET Web Application

Start the Visual Studio. Create a new Web Forms application by using File -> New -> Project and run the application by pressing Ctrl+F5, which shows something similar to the following screenshot in your web browser,
![](Overview_images/Overview_img9.png)


### Installing the NuGet Package

The following steps will help you to add the references of the Syncfusion assemblies, required scripts and CSS files into your Project.
1. Right click on your project in the Solution Explorer and select Manage NuGet Packages options from the sub-menu that pop-up on the screen. Select the Syncfusion NuGet Packages within the Online tab, which will display the list of available packages in it, as shown below
![](Overview_images/Overview_img10.png)
2. Install the Syncfusion.ASPNET45 (based on the .NET framework (4.5) used in our sample application) package now. The below image depicts that the NuGet Package for ASP.NET (with .NET framework version 4.5) has been successfully installed into your project.

![](Overview_images/Overview_img11.png)

Once the package installation is completed, all the required assembly references, scripts and CSS files will be automatically added to your application. Also, it configures the web.config file automatically. The remaining changes that you need to do in your application are as follows.
### Adding dependent Scripts and CSS references in Site.Master

Syncfusion NuGet package will copy all the dependent Scripts and CSS files in the appropriate folders of the project. However you need to manually add the references for those files in the Site.Master page. The code snippet for this is follows.
{% highlight html %}
<table>
<tr>
<td colspan=1 rowspan=1>
<head runat="server"><br/><!-- Insert the following content within "head" tag --><br/><link href="Content/ej/web/default-theme/ej.web.all.min.css" rel="stylesheet" /><br/><!-- If you head section already contain jQuery reference, please remove this jQuery reference --><br/><script src='<%= Page.ResolveClientUrl("~/Scripts/jquery-1.10.2.min.js")%>' type="text/javascript"></script><br/><script src='<%= Page.ResolveClientUrl("~/Scripts/jquery.easing.1.3.min.js")%>' type="text/javascript"></script><br/><script src='<%= Page.ResolveClientUrl("~/Scripts/jquery.globalize.min.js")%>' type="text/javascript"></script><br/><script src='<%= Page.ResolveClientUrl("~/Scripts/jsrender.min.js")%>' type="text/javascript"></script><br/><script src='<%= Page.ResolveClientUrl("~/Scripts/ej/ej.web.all.min.js")%>' type="text/javascript"></script><br/><script src='<%= Page.ResolveClientUrl("~/Scripts/ej/ej.webform.min.js")%>' type="text/javascript"></script><br/></head><br/></td></tr>
</table>
{% endhighlight %}
### Adding Syncfusion ASP.NET control

Here, you will see how to add the `DatePicker` control into the newly created Syncfusion ASP.NET Web Application. To add the control in the Application, you can use either of the following two ways,
1. Add the below `DatePicker` code within the “Default.aspx” file
{% highlight html %}
<table>
<tr>
<td colspan=1 rowspan=1>
<br/><br/><ej:DatePicker ID="DatePicker" runat="server"></ej:DatePicker><br/><br/></td></tr>
</table>
{% endhighlight %}
2. Another way of adding control into the Default.aspx page is by making use of the Toolbox option present in the Visual Studio. When you install Essential Studio or ASP.NET setup in your machine, all the available ASP.NET controls are automatically configured into the Visual Studio Toolbox. You just need to drag the required control from the toolbox and then drop it into the Content section of the Default.aspx page, so that the required control code automatically gets generated
![](Overview_images/Overview_img12.png)
3. Now build and run the project by pressing F5, so that you can now see the output similar to the below screenshot in your web browser,

![](Overview_images/Overview_img13.png)

## Manual Integration of Syncfusion ASP.NET controls into the new/existing Application

This topic mainly focus on how to integrate the Syncfusion ASP.NET controls manually into the newly created/existing ASP.NET Web Forms application.
### Creating ASP.NET Web Application

Start the Visual Studio. Create a new Web Forms application by using File -> New -> Project and run the application by pressing Ctrl+F5, which shows something similar to the following screenshot in your web browser,
![](Overview_images/Overview_img14.png)


### For Existing Applications

If you want to add our Syncfusion ASP.NET controls into your existing application, open your application and proceed with the following steps.
### Adding required CSS files

To render the Syncfusion ASP.NET controls with its unique style and theme, it is necessary to refer the required CSS files into your application. You need to copy all the required CSS files into your application from the following location,
<table>
<tr>
<td colspan=1 rowspan=1>
<installed location>\Syncfusion\Essential Studio\13.1.0.21\JavaScript\assets\css\web<br/>For example, If you have installed the Essential Studio within C:\Program Files (x86), then navigate to the below location,<br/>C:\Program Files (x86)\Syncfusion\Essential Studio\13.1.0.21\JavaScript\assets\css\web<br/></td></tr>
</table>
When you navigate to the above location, you can find the files shown in the below image, which you need to copy entirely and paste it into your root application. 
![](Overview_images/Overview_img15.png)

Before pasting it into your application, create a folder structure with names ej/web within the Content folder of your application and place all the copied files into it as shown below,
![](Overview_images/Overview_img16.png)

<table>
<tr>
<td colspan=1 rowspan=1>
N> The common-images folder is needed to be copied into your application mandatorily, as it includes all the common font icons and other images required for the control to render.<br/><br/></td></tr>
</table>
Once the CSS files are added in your application, include the reference to ej.web.all.min.css file in the Site.Master page, within the head section.
{% highlight html %}
<table>
<tr>
<td colspan=1 rowspan=1>
<link href="Content/ej/web/default-theme/ej.web.all.min.css" rel="stylesheet" /><br/></td></tr>
</table>
{% endhighlight %}
### Adding required Script files

Essential ASP.Net controls has the following list of external JavaScript dependencies. 
* jquery-1.10.2.min.js

* jquery.easing.1.3.min.js

* jquery.globalize.min.js

* jsrender.min.js


Apart from the above external dependencies, each control has its own list of internal dependencies. This dependencies are listed within each component documentation. For the getting started, you can use “ej.web.all.min.js” file which encapsulates all the `ej` controls and frameworks in one single file. Also, Essential ASP.Net controls has additional script dependency to “ej.webform.min.js” which is responsible for raising server-side events.
The dependencies are available in the following locations of your machine. Please copy these files from location given
<table>
<tr>
<td colspan=1 rowspan=1>
Files<br/></td><td colspan=1 rowspan=1>
Location<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
jquery-1.10.2.min.js<br/>jquery.easing.1.3.min.js<br/>jquery.globalize.min.js<br/>jsrender.min.js<br/></td><td colspan=1 rowspan=1>
<Syncfusion Installed Location>\Essential Studio\13.1.0.21\JavaScript\assets\external<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
ej.web.all.min.js<br/></td><td colspan=1 rowspan=1>
<Syncfusion Installed Location>\Essential Studio\13.1.0.21\JavaScript\assets\scripts\web<br/></td></tr>
<tr>
<td colspan=1 rowspan=1>
ej.web.all.min.js<br/></td><td colspan=1 rowspan=1>
<Syncfusion Installed Location>\Essential Studio\13.1.0.21\JavaScript\assets\scripts\common<br/></td></tr>
</table>
N> Example for “Syncfusion Installed location” is “C:\Program Files (x86)\Syncfusion”
Now, create a folder named ej under the Scripts folder of your application and place the copied files ej.web.all.min.js and ej.webform.min.js into it as shown below,
![](Overview_images/Overview_img17.png)

Once the scripts are added in your application, now it is necessary to include the reference to it in your application. This should be done within the Site.Master file, as we did previously for CSS files. 
Add the below script references in the Site.Master file within the head section,
{% highlight html %}
<table>
<tr>
<td colspan=1 rowspan=1>
<link href="Content/ej/web/default-theme/ej.web.all.min.css" rel="stylesheet" /><br/><script src='<%= Page.ResolveClientUrl("~/Scripts/jquery-1.10.2.min.js")%>' type="text/javascript"></script><br/><script src='<%= Page.ResolveClientUrl("~/Scripts/jquery.easing.1.3.min.js")%>' type="text/javascript"></script><br/><script src='<%= Page.ResolveClientUrl("~/Scripts/jquery.globalize.min.js")%>' type="text/javascript"></script><br/><script src='<%= Page.ResolveClientUrl("~/Scripts/jsrender.min.js")%>' type="text/javascript"></script><br/><script src='<%= Page.ResolveClientUrl("~/Scripts/ej/ej.web.all.min.js")%>' type="text/javascript"></script><br/><script src='<%= Page.ResolveClientUrl("~/Scripts/ej/ej.webform.min.js")%>' type="text/javascript"></script><br/><br/></td></tr>
</table>
{% endhighlight %}
### Assembly Reference

Refer the following assemblies in your newly created ASP.NET application, which allows you to use any of the Syncfusion ASP.NET controls within it.
* Syncfusion.EJ

* Syncfusion.EJ.Web


Once you have installed the Essential Studio package in your system, the Syncfusion assemblies are automatically registered in the GAC. You can easily add the reference to your application using `Project -> Add Reference` and selecting the mentioned Assemblies in dialog shown
![](Overview_images/Overview_img18.png)

### Adding Control to the Page

When you install Essential Studio or ASP.NET setup in your machine, all the available ASP.NET controls are automatically configured into the Visual Studio Toolbox. 
You just need to drag the required control from the toolbox and then drop it into the Content section of the Default.aspx page, so that the required control code gets generated automatically.
![](Overview_images/Overview_img19.png)

![](Overview_images/Overview_img20.png)

### Registering Syncfusion Assemblies within the Web.config

In your application’s web.config file, add the below assembly information within the &lt; assemblies &gt; tag.
{% highlight html %}
<table>
<tr>
<td colspan=1 rowspan=1>
<system.web><br/><compilation debug="true" targetFramework="4.5"><br/><assemblies><br/><add assembly="Syncfusion.EJ, Version=13.1450.0.21, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" /><br/><add assembly="Syncfusion.EJ.Web, Version=13.1450.0.21, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" /><br/></assemblies><br/></compilation><br/></system.web><br/><br/></td></tr>
</table>
{% endhighlight %}
Finally build and run the project by pressing F5, so that you can now see the output similar to the below screenshot in your web browser,
![](Overview_images/Overview_img21.png)

