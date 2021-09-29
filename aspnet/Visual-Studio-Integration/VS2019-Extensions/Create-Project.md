---
layout: post
title: Create Project | ASP.NET Web Forms | Syncfusion
description: Syncfusion provides Visual Studio Project Templates for the ASP.NET platform to create Syncfusion ASP.NET Web Application using Essential JS 1 components
platform: aspnet
control: Syncfusion Extensions
documentation: ug
---

# Creating SyncfusionASP.NET Web Application

Syncfusion offers **Visual Studio Project Templates** for the Syncfusion ASP.NET platform, which can be used to create a Syncfusion ASP.NET Web Application or a Syncfusion ASP.NET Web Site.

I> Syncfusion ASP.NET Website templates are available beginning with v12.2.0.36, and Syncfusion ASP.NET Web Application templates are available beginning with v13.3.0.7. 

To create the **Syncfusion ASP.NET (Essential JS 1) Application** using the **Visual Studio Project Template**, follow the steps below:

> Before use the Syncfusion ASP.NET Web Forms Project Template, check whether the **ASP.NET Web Forms Extensions - Syncfusion** installed or not in Visual Studio Extension Manager by clicking on the Tools -> Extensions and Updates -> Installed for Visual Studio 2017 or lower and for Visual Studio 2019 by clicking on the Extensions -> Manage Extensions -> Installed.

1. To create a Syncfusion ASP.NET (Essential JS 1) Web Forms project, use one of the following methods:

   **Option 1**  
   Click **Syncfusion Menu** and choose **Essential Studio for ASP.NET Web Forms (EJ1) > Create New Syncfusion ASPNET Web Forms Project…** in **Visual Studio**.

   ![Choose Syncfusion ASP.NET Web Application or Syncfusion ASP.NET Web Site from Visual Studio new project dialog via Syncfusion menu](Create-Project_images/Syncfusion_Menu_ProjectTemplate.png)

   N> From Visual Studio 2019, Syncfusion menu is available under Extensions in Visual Studio menu.

   **Option 2**  
   Choose **File > New > Project** and navigate to **Syncfusion > Web > Syncfusion ASP.NET Web Forms Application** in **Visual Studio**.

   ![Choose Syncfusion ASP.NET Web Forms Application from Visual Studio new project dialog](Create-Project_images/Syncfusion-Project-Templates-img1.png)

2. Name the **project**, select the destination location, and configure the project's .NET Framework, then click **OK**. The Project Configuration Wizard is displayed. 

   N> The minimum target framework for Syncfusion ASP.NET Project Templates is 3.5.

3. Using the following Project Configuration window, select the options to configure the Syncfusion ASP.NET Web Forms Application.

   ![Syncfusion Essential JS 1 ASP.NET Web Forms Project configuration wizard](Create-Project_images/Syncfusion-Project-Templates-img2.png)

**Project Configurations**

**Project Type:** Choose the appropriate Project Type either Website or WebApplication.

   ![Choose appropriate Project Type version](Create-Project_images/Syncfusion-Project-Templates-img3.png)

**Theme:** Choose the appropriate theme.

   ![Choose required theme](Create-Project_images/Syncfusion-Project-Templates-img4.png)

**Language:** Choose the language, either C# or VB.

   ![Choose required language](Create-Project_images/Syncfusion-Project-Templates-img5.png)

**Assemblies From:** Choose the assembly location, from where the assembly will be added to the project.

   ![Choose the assembly location from where it is going to be added to the prject](Create-Project_images/Syncfusion-Project-Templates-img6.png)

**Assets From:** Choose the Syncfusion Essential JS assets to be added to the ASP.NET Web Forms Project from the NuGet, CDN, or Installed Location.

   ![Choose the Syncfusion Essential JS assets to ASP.NET Web Forms Project, either NuGet, CDN or Installed Location](Create-Project_images/Syncfusion-Project-Templates-img7.png)

**Installed Version** Choose the version of the project that needs to be created.

   ![Choose the Version](Create-Project_images/Syncfusion-Project-Templates-img8.png)

4. Select the components, Assemblies, and Scripts that should be added to the project, and then click the Create button. The Syncfusion ASP.NET Web Forms project will be created.

   ![Syncfusion Essential ASP.NET Web Feature selection](Create-Project_images/Syncfusion-Project-Templates-img9.png)

   ![Syncfusion Essential ASP.NET Web Feature selection](Create-Project_images/Syncfusion-Project-Templates-img14.PNG)

5. The necessary Syncfusion Assembly references, Scripts, and CSS, as well as the necessary Web.config entries, have been added to the project.

   ![References of Syncfusion Essential JS 1 ASP.NET Web Forms project](Create-Project_images/Syncfusion-Project-Templates-img10.png)

   ![Scripts and Themes of Syncfusion Essential JS 1 ASP.NET Web Forms project](Create-Project_images/Syncfusion-Project-Templates-img11.png)

   ![Web.config references of Syncfusion Essential JS 1 ASP.NET Web Forms project](Create-Project_images/Syncfusion-Project-Templates-img12.png)
   

6.Then, Syncfusion licensing registration required message box will be shown if you installed the trial setup or NuGet packages since Syncfusion introduced the licensing system from 2018 Volume 2 (v16.2.0.41) Essential Studio release. Navigate to the  [help topic](https://help.syncfusion.com/common/essential-studio/licensing/license-key#how-to-generate-syncfusion-license-key), which is shown in the licensing message box to generate and register the Syncfusion license key to your project. Refer to this [blog](https://blog.syncfusion.com/post/Whats-New-in-2018-Volume-2-Licensing-Changes-in-the-1620x-Version-of-Essential-Studio.aspx) post for understanding the licensing changes introduced in Essential Studio.

   ![Syncfusion license registration information message box for Syncfusion Essential JS 1 ASP.NET Web Forms project](Create-Project_images/Syncfusion-Project-Templates-img13.jpeg)



