---
layout: post
title: The Syncfusion ASP.NET Extensions
description: Syncfusion ASP.NET Extensions
platform: aspnet
control: Introduction
documentation: ug

---
# Utility

The Syncfusion ASP.NET Utilities provide quick access to create or configure the Syncfusion ASP.NET projects. The Syncfusion ASP.NET utility have the following features.


1. Syncfusion Project Conversion for ASP.NET Web Application
2. Syncfusion Project Migration for ASP.NET Web Application
3. Sample Creator

## Project Conversion

Syncfusion provides the Project Conversion add-on with Visual Studio that will converts an existing ASP.NET project into a Syncfusion ASP.NET (EJWEB) project by adding the required assemblies and resource files.

I>	The Syncfusion ASP.NET Web Application Project Conversion utility is available from v13.1.0.30.

### Convert into Syncfusion ASP.NET Project 

The following steps direct you to use the Syncfusion Project Conversion in the existing ASP.NET Project.

1. Open an existing Microsoft ASP.NET Project or create a new Microsoft ASP.NET Project.

2.  To open Project Conversion Wizard, follow either one of the options below:   
    
    **Option 1:**  
    Click **Syncfusion Menu** and choose **Essential Studio for ASP.NET (EJ1) > Convert to Syncfusion ASP.NET Application…** in **Visual Studio**.

    ![Syncfusion Essential JS 1 ASP.NET Web Forms Project Conversion via Syncfusion menu](Utility_images/Syncfusion_Menu_Project_Conversion1.png)

    N> In Visual Studio 2019, Syncfusion menu available under Extension in Visual Studio menu.

    **Option 2:**    
    Right-click the Project from Solution Explorer, select **Syncfusion Essential JS 1**, and choose the **Convert to Syncfusion ASP.NET (Essential JS 1) Application...** Refer to the following screenshot for more information.

    ![Syncfusion Essential JS 1 ASP.NET Web Forms Project Conversion add-in](Utility_images/Project-Conversion_img1.png)

3. Project Conversion Wizard opens to configure the project.

   ![Utility_images2](Utility_images/Project-Conversion_img2.jpg)

The following configurations are used in the Project Conversion Wizard.

   **Assemblies From:**

   Choose the assembly location:

   * Added From GAC: Refer to the assemblies from Global Assembly Cache.

   * Added from Installed Location: Refer to the assemblies from Syncfusion Installed locations.

   * Add Referenced Assemblies to Solution: Copy and refer to the assemblies from project's solution file lib directory.
   
   ![Utility_images3](Utility_images/Project-Conversion_img3.jpeg)
   
   **Choose the Theme:**
   
   The master page of project will be updated based on the selected theme. The Theme Preview section shows the controls preview before converting to a Syncfusion project
   
   ![Utility_images4](Utility_images/Project-Conversion_img4.jpeg)

   **Choose CDN Support:**

   The master page of the project will be updated based on required Syncfusion CDN links.

   ![Utility_images13](Utility_images/Project-Conversion_img13.jpeg)
 
   **Choose Copy Global Resources:**
    
   The localization culture files will be shipped into Scripts\ej\i18n directory of the project.

   ![Utility_images14](Utility_images/Project-Conversion_img14.jpeg)

4. Choose the required controls from Components section and Click the **Convert** button to convert it into a Syncfusion Project.

   ![Utility_images5](Utility_images/ProjectConversion_img5.jpg)
   
   The **Project Backup** dialog will be opened. Click Yes to backup the current project before converting it to Syncfusion project, and click No to convert the project to Syncfusion project without backup.
   
   ![Utility_images6](Utility_images/Project-Conversion_img6.jpg)

5. The required Syncfusion Reference Assemblies, Scripts and CSS are included in the ASP.NET Project. Refer to the following screenshots for more information.

   ![Utility_images7](Utility_images/Project-Conversion_img7.jpeg)

   ![Utility_images8](Utility_images/Project-Conversion_img8.jpeg)

   ![Utility_images9](Utility_images/Project-Conversion_img9.jpeg)


### Rendering Control after Syncfusion ASP.NET Conversion

Once you converted your ASP.NET Project to Syncfusion ASP.NET Project using Syncfusion Visual Studio Extension, perform the following steps to render the Syncfusion controls to your project.

1. The CSS, Scripts, Syncfusion References, and required Web.config file entries are added to your project by the Syncfusion ASP.NET Conversion.

2. Add the required CSS and Script files references in master page (Site.Master file) of the project. Refer to the following screenshot for more information.

   ![Utility_images10](Utility_images\Project-Conversion_img10.jpeg)
   
3. Now, include the Syncfusion controls to your project. Refer to the following screenshot for more information.

   ![Utility_images11](Utility_images\Project-Conversion_img11.jpeg)

4. Run the project, and the following output will be displayed.

   ![Utility_images12](Utility_images\Project-Conversion_img12.jpeg)


## Project Migration

Syncfusion provides the Project Migration add-on with the Visual Studio that will easily migrate the existing Syncfusion ASP.NET project from one Essential Studio version to another version.

I>	The Syncfusion ASP.NET Web Application Project Migration utility is available from v13.1.0.30.

### Migrate Syncfusion Project 

The following steps help you to migrate your existing Syncfusion ASP.NET application.

1. To open Migration Wizard, follow either one of the options below: 

   **Option 1:**   
   Click **Syncfusion Menu** and choose **Essential Studio for ASP.NET (EJ1) > Migrate Project…** in **Visual Studio**.

   ![Syncfusion Essential JS 1 ASP.NET Web Forms Project Migration via Syncfusion menu](Utility_images/Syncfusion_Menu_Project_Migration1.png)

   N> In Visual Studio 2019, Syncfusion menu available under Extension in Visual Studio menu.

   **Option 2:**  
   Right-click the **Syncfusion ASP.NET Application** from Solution Explorer and select **Syncfusion Essential JS 1**. Choose **Migrate the Essential JS 1 Project to Another version…**

   ![Syncfusion Essential JS 1 ASP.NET Web Forms Project Migration add-in](Utility_images/Project-Migration_img1.png)

2. The **Project Migration** window appears. Choose the required Essential Studio version that has to be installed in the machine.

   ![Utility_images2](Utility_images/Project-Migration_img2.jpeg)

3. The **Project Migration** window allows you to configure the following options:

   i. **Essential Studio Version:** Select any version from the list of installed versions.
   
   ii. **Assemblies From:** Choose the assembly location from where it is going to be added to the project.
   
4. Click the Migrate Button. The **Project Backup** dialog will be opened. Click Yes to backup the current project before migrating to the Syncfusion project, and click No to migrate the project to required Syncfusion version without backup.
   
   ![Utility_images3](Utility_images/Project-Migration_img3.jpeg)
   
   
5. The Syncfusion Reference Assemblies, Scripts, and CSS are updated to the corresponding version in the project.


## Sample Creator

Syncfusion provides support for Sample Creator utility that allows you to create Syncfusion ASP.NET Projects along with the samples based on Controls and Features selection.

### Create Syncfusion ASP.NET Web Project from Sample Creator

Sample Creator can be downloaded from the Syncfusion Dashboard. After installing the complete Essential Studio suite or ASP.NET setup, the following steps will help you to create the Syncfusion ASP.NET Project via the Sample Creator utility.

1. To launch ASP.NET (Essential JS 1) Sample Creator application, follow either one of the options below: 

   **Option 1:**   
   Click **Syncfusion Menu** and choose **Essential Studio for ASP.NET (EJ1) > Launch Sample Creator…** in **Visual Studio**.

   ![Syncfusion Essential JS 1 ASP.NET Web Forms control panel to launch Syncfusion Essential JS 1 ASP.NET Web Forms Sample Creator](Sample-Creator_images/Syncfusion_Menu_Sample_Creator.png)

   N> In Visual Studio 2019, Syncfusion menu available under Extension in Visual Studio menu.

   **Option 2:**  
   Launch the Syncfusion ASP.NET (EJ1) Control Panel. Select the Sample Creator button to launch the ASP.NET (Essential JS 1) Sample Creator application. Refer to the following screenshot for more information.

   ![Syncfusion Essential JS 1 ASP.NET Web Forms control panel to launch Syncfusion Essential JS 1 ASP.NET Web Forms Sample Creator](Sample-Creator_images/SampleCreator_img1.png)

2. Syncfusion Sample Creator Wizard displays the **Controls and its Feature Selection** section.

   ![Utility_images2](Sample-Creator_images/SampleCreator_img2.jpeg)


#### Controls selection

Listed here are the Syncfusion ASP.NET controls so you can choose the required controls.

   ![Utility_images3](Sample-Creator_images/SampleCreator_img3.jpeg)

#### Feature selection

Based on the controls, the Feature is enabled to choose the features of the corresponding controls.

   ![Utility_images4](Sample-Creator_images/SampleCreator_img4.jpeg)


#### Project configuration

1. You can configure the following project details in the Sample Creator.

   * Project Type: Select the type of ASP.NET Project, it can be either Web Application or Web Site.

   * Language: Select the language, either C# or VB.

   * VS Version: Choose the Visual Studio version.

   * .NET Framework: Choose the .NET Framework version.

   * Name: Name your Syncfusion ASP.NET Application.

   * Location: Choose the target location of your project.

   * Theme Selection: Choose the required theme. The Theme Preview section shows the controls preview before creating the Syncfusion project.

   ![Utility_images6](Sample-Creator_images/SampleCreator_img6.jpeg)


2. When you click the Create button, the new Syncfusion ASP.NET project is created. The following resources are added in the project:

   * Added the required ASPX and Class files in the project.

     ![Utility_images7](Sample-Creator_images/SampleCreator_img7.jpeg)

   * Included the required Syncfusion ASP.NET scripts and themes files.

     ![Utility_images8](Sample-Creator_images/SampleCreator_img8.jpeg)

   * The required Syncfusion assemblies are added for selected controls under Project Reference.

     ![Utility_images9](Sample-Creator_images/SampleCreator_img9.jpeg)

   * Configure the Web.Config file by adding the Syncfusion reference assemblies, namespaces, and controls.

     ![Utility_images10](Sample-Creator_images/SampleCreator_img10.jpeg)

3. Once the project is created, open the project by clicking the Yes button. If you click No button, the corresponding location of the project will be opened. Refer to the following screenshot for more information.

   ![Utility_images11](Sample-Creator_images/SampleCreator_img11.jpeg)




