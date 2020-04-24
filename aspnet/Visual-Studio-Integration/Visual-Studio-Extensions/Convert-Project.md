---
layout: post
title: Convert Project | ASP.NET Web Forms (Essential JS1) | Syncfusion
description: Syncfusion ASP.NET Web Forms (Essential JS1) Project Conversion Extension that converts an existing ASP.NET project into a Essential JS1 ASP.NET Project.
platform: aspnet
control: Syncfusion Extensions
documentation: ug
---

# Convert Project

Syncfusion project conversion is a Visual Studio add-in that converts an existing ASP.NET application into the Syncfusion ASP.NET (Essential JS 1) application by adding the required assemblies and resource files.

I> The Syncfusion ASP.NET Web Application Project Conversion utility is available from v13.1.0.30. 

The following steps help you use the Syncfusion Project conversion in the existing ASP.NET application:

1. Open an existing Microsoft ASP.NET Project or create a new Microsoft ASP.NET Project.

2. Open the conversion dialog by either one of the options below: 

   **Option 1**  
   Click **Syncfusion Menu** and choose **Essential Studio for ASP.NET Web Forms (EJ1) > Convert to Syncfusion ASP.NET Application…** in **Visual Studio**.

   ![Syncfusion Essential JS 1 ASP.NET Web Forms Project Conversion via Syncfusion menu](Convert-Project_images/Syncfusion_Menu_Project_Conversion1.png)

   N> In Visual Studio 2019, Syncfusion menu is available under Extensions in Visual Studio menu.

   **Option 2**   
   Right-click the Project from Solution Explorer, select **Syncfusion Essential JS 1**, and choose the **Convert to Syncfusion ASP.NET (Essential JS 1) Application...** Refer to the following screenshot for more information.

   ![Syncfusion Essential JS 1 ASP.NET Web Forms Project Conversion add-in](Convert-Project_images/Project-Conversion-img1.png)

3. Project Conversion wizard opens to configure the project.

   ![Syncfusion Essential JS 1 ASP.NET Web Forms Project Conversion wizard](Convert-Project_images/Project-Conversion-img2.png)

   The following configurations are used in the Project Conversion wizard:

   **Assemblies From:** Choose the assembly location, from where the assembly is added to the project.     
   
   ![Choose the assembly location from where assemblies to be referred to the ASP.NET Web Forms project](Convert-Project_images/Project-Conversion-img3.jpeg)
   
   **Choose the Theme:** The master page of project will be updated based on selected theme. The Theme Preview section shows the controls preview before convert into a Syncfusion project.
   
   ![Choose the theme to apply on the master page of the ASP.NET Web Forms project](Convert-Project_images/Project-Conversion-img4.png)

   **Choose CDN Support:** The master page of the project will be updated based on required Syncfusion CDN links.

   ![Choose CDN Support to refer the Syncfusion assets from CDN for ASP.NET Web Forms project](Convert-Project_images/Project-Conversion-img6.jpeg)
 
   **Copy Global Resources:** If choose Copy Global Resources option, the Syncfusion localization culture files will be shipped to project from Installed Location. 

   ![Choose Copy Global Resources to ship the localization culture files for ASP.NET Web Forms project](Convert-Project_images/Project-Conversion-img7.jpeg)   

   N> Copy Global Resources option will disable when choose the CDN option.

   **Components:** Choose the required controls.

   ![Choose the required controls](Convert-Project_images/Project-Conversion-img8.jpg)

4. The **Project Backup** dialog will appear when **Click** the **Convert** button. In the dialog, if click **Yes**, it will backup the current project before converting into Syncfusion project. If click **No**, it will convert the project to Syncfusion project without backup.

   ![Syncfusion Essential JS 1 ASP.NET Web Forms Project Conversion backup dialog](Convert-Project_images/Project-Conversion-img9.png)

5. The required Syncfusion Assembly references, Scripts, and CSS and required Web.config entries have been added to the project.

    ![Reference assemblies use of Syncfusion Essential JS 1 ASP.NET Web Forms Project](Convert-Project_images/Project-Conversion-img10.png)

   ![Scripts and CSS for Syncfusion Essential JS 1 ASP.NET Web Forms Project](Convert-Project_images/Project-Conversion-img11.png)

   ![Web.config assembly reference of Syncfusion Essential JS 1 ASP.NET Web Forms Project](Convert-Project_images/Project-Conversion-img12.png)

6. If you installed the trial setup or NuGet packages from nuget.org you have to register the Syncfusion license key to your project since Syncfusion introduced the licensing system from 2018 Volume 2 (v16.2.0.41) Essential Studio release. Navigate to the [help topic](https://help.syncfusion.com/common/essential-studio/licensing/license-key#how-to-generate-syncfusion-license-key) to generate and register the Syncfusion license key to your project. Refer to this [blog](https://blog.syncfusion.com/post/Whats-New-in-2018-Volume-2-Licensing-Changes-in-the-1620x-Version-of-Essential-Studio.aspx?_ga=2.11237684.1233358434.1587355730-230058891.1567654773) post for understanding the licensing changes introduced in Essential Studio.