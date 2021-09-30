---
layout: post
title: Convert Project | ASP.NET Web Forms (Essential JS1) | Syncfusion
description: Syncfusion ASP.NET Web Forms (Essential JS1) Project Conversion Extension that converts an existing ASP.NET project into a Essential JS1 ASP.NET Project.
platform: aspnet
control: Syncfusion Extensions
documentation: ug
---

# Converting ASP.NET application to Syncfusion ASP.NET application

The Syncfusion project conversion add-in for Visual Studio converts an existing ASP.NET application into the Syncfusion ASP.NET (Essential JS 1) application by adding the necessary assemblies and resource files.

I> The Syncfusion ASP.NET Web Application Project Conversion utility is available beginning with v13.1.0.30.

The following steps will assist you to use the Syncfusion Project conversion in your existing ASP.NET application:

> Before use, the Syncfusion ASP.NET Web Forms Project Conversion, check whether the **ASP.NET Web Forms Extensions - Syncfusion** installed or not in Visual Studio Extension Manager by clicking on the Tools -> Extensions and Updates -> Installed for Visual Studio 2017 or lower and for Visual Studio 2019 by clicking on the Extensions -> Manage Extensions -> Installed. Also, check whether the corresponding Essential Studio version build installed or not. If the Essential Studio version is not same for both the Extension and build, then the Project Conversion will not be shown.

1. Open an existing Microsoft ASP.NET Project or create a new Microsoft ASP.NET Project.

2. Open the conversion dialog by selecting one of the following options: 

   **Option 1**  
   Click **Syncfusion Menu** and choose **Essential Studio for ASP.NET Web Forms (EJ1) > Convert to Syncfusion ASP.NET Application…** in **Visual Studio**.

   ![Syncfusion Essential JS 1 ASP.NET Web Forms Project Conversion via Syncfusion menu](Convert-Project_images/Syncfusion_Menu_Project_Conversion1.png)

   N> In Visual Studio 2019, Syncfusion menu is available under Extensions in Visual Studio menu.

   **Option 2**   
   Right-click the Project from Solution Explorer, select **Syncfusion Web (Essential JS 1)**, and choose the **Convert to Syncfusion ASP.NET (Essential JS 1) Application...** Refer to the following screenshot for more information.

   ![Syncfusion Essential JS 1 ASP.NET Web Forms Project Conversion add-in](Convert-Project_images/Project-Conversion-img1.png)

3. The Project Conversion Wizard appears, allowing you to configure the project.

   ![Syncfusion Essential JS 1 ASP.NET Web Forms Project Conversion wizard](Convert-Project_images/Project-Conversion-img2.png)

   The following configurations are used in the Project Conversion wizard:

   **Assemblies From:** Choose the assembly location, from where the assembly will be added to the project.
   
   ![Choose the assembly location from where assemblies to be referred to the ASP.NET Web Forms project](Convert-Project_images/Project-Conversion-img3.jpeg)
   
   **Choose the Theme:** Based on the theme chosen, the project's master page will be updated. The Theme Preview section displays a preview of the components before converting them into a Syncfusion project.
   
   ![Choose the theme to apply on the master page of the ASP.NET Web Forms project](Convert-Project_images/Project-Conversion-img4.png)

   **Choose CDN Support:** The project's master page will be updated based on the required Syncfusion CDN links.

   ![Choose CDN Support to refer the Syncfusion assets from CDN for ASP.NET Web Forms project](Convert-Project_images/Project-Conversion-img6.jpeg)
 
   **Copy Global Resources:** If you select the Copy Global Resources option, the Syncfusion localization culture files will be shipped to the project from the Installed Location.

   ![Choose Copy Global Resources to ship the localization culture files for ASP.NET Web Forms project](Convert-Project_images/Project-Conversion-img7.jpeg)   

   N> Copy Global Resources option will disable when choose the CDN option.

   **Components:** Choose the required components.

   ![Choose the required controls](Convert-Project_images/Project-Conversion-img8.jpg)

4. When you click the **Convert** button, the **Project Backup** dialog will appear. If you click **Yes** in the dialog, it will backup the current project before converting it to a Syncfusion project. If you choose **No**, the project will be converted to a Syncfusion project without a backup.

   ![Syncfusion Essential JS 1 ASP.NET Web Forms Project Conversion backup dialog](Convert-Project_images/Project-Conversion-img9.png)

5. The necessary Syncfusion Assembly references, Scripts, and CSS, as well as the necessary Web.config entries, have been added to the project.

    ![Reference assemblies use of Syncfusion Essential JS 1 ASP.NET Web Forms Project](Convert-Project_images/Project-Conversion-img10.png)

   ![Scripts and CSS for Syncfusion Essential JS 1 ASP.NET Web Forms Project](Convert-Project_images/Project-Conversion-img11.png)

   ![Web.config assembly reference of Syncfusion Essential JS 1 ASP.NET Web Forms Project](Convert-Project_images/Project-Conversion-img12.png)

6. If you installed the trial setup or NuGet packages from nuget.org you must register the Syncfusion license key to your project since Syncfusion introduced the licensing system from 2018 Volume 2 (v16.2.0.41) Essential Studio release. Navigate to the [help topic](https://help.syncfusion.com/common/essential-studio/licensing/license-key#how-to-generate-syncfusion-license-key) to generate and register the Syncfusion license key to your project. Refer to this [blog](https://blog.syncfusion.com/post/Whats-New-in-2018-Volume-2-Licensing-Changes-in-the-1620x-Version-of-Essential-Studio.aspx?_ga=2.11237684.1233358434.1587355730-230058891.1567654773) post for understanding the licensing changes introduced in Essential Studio.