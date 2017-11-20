---
layout: post
title: The Syncfusion ASP.NET Extensions
description: Syncfusion ASP.NET Extensions
platform: ASP.NET
control: Introduction
documentation: ug

---
# Utility

The Syncfusion ASP.NET Utilities provide quick access to create or configure the Syncfusion ASP.NET projects. The Syncfusion ASP.NET utility have the following features.


1. Syncfusion Project Conversion for ASP.NET Web Application
2. Syncfusion Project Migration for ASP.NET Web Application
3. Sample Creator

## Project Conversion

Syncfusion provides the Project Conversion add-on with Visual Studio, which will converts an existing ASP.NET project into a Syncfusion ASP.NET (EJWEB) project by adding the required assemblies and resource files.

I>	The Syncfusion ASP.NET Web Application Project Conversion utility is available from v13.1.0.30.

### Convert into Syncfusion ASP.NET Project 

The following steps direct you to use the Syncfusion Project Conversion in the existing ASP.NET Project.

1. Open an existing Microsoft ASP.NET Project or create a new Microsoft ASP.NET Project.

2. Right-click on **Project** from Solution Explorer and select **Syncfusion VS Extensions** and choose the **Convert to Syncfusion ASP.NET Application**. Refer to the following screenshot for more information.

   ![](Utility_images/Project-Conversion_img1.jpeg)

3. Project Conversion Wizard opens to configure the project.

   ![](Utility_images/Project-Conversion_img2.jpg)

The following configurations are used in the Project Conversion Wizard.

   **Assemblies From:**

   Choose the assembly location:

   * Added From GAC - Refer to the assemblies from Global Assembly Cache. 

   * Added from Installed Location - Refer to the assemblies from Syncfusion Installed locations.

   * Add Referenced Assemblies to Solution - Copy and refer to the assemblies from project's solution file lib directory.     
   
   ![](Utility_images/Project-Conversion_img3.jpeg)
   
   **Choose the Theme:**
   
   The master page of project will be updated based on selected theme. The Theme Preview section shows the controls preview before convert into a Syncfusion project
   
   ![](Utility_images/Project-Conversion_img4.jpeg)

   **Choose CDN Support:**

   The master page of the project will be updated based on required Syncfusion CDN links.

   ![](Utility_images/Project-Conversion_img13.jpeg)
 
   **Choose Copy Global Resources:**
    
   The localization culture files will be shipped into Scripts\ej\i18n directory of the project.

   ![](Utility_images/Project-Conversion_img14.jpeg)   

4. Choose the required controls from Components section and Click the **Convert** button to convert it into a Syncfusion Project.

   ![](Utility_images/ProjectConversion_img5.jpg)
   
   The **Project Backup** dialog will be opened. If click Yes it will backup the current project before converting it to Syncfusion project. If click No it will convert the project to Syncfusion project without backup. 
   
   ![](Utility_images/Project-Conversion_img6.jpg)

5. The required Syncfusion Reference Assemblies, Scripts and CSS are included in the ASP.NET Project. Refer to the following screenshots for more information.

   ![](Utility_images/Project-Conversion_img7.jpeg)

   ![](Utility_images/Project-Conversion_img8.jpeg)

   ![](Utility_images/Project-Conversion_img9.jpeg)


### Rendering Control after Syncfusion ASP.NET Conversion

Once you converted your ASP.NET Project to Syncfusion ASP.NET Project using Syncfusion Visual Studio Extension, Perform the following steps to render the Syncfusion controls to your project.

1. The CSS, Scripts, Syncfusion References and required Web.config file entries are added to your project by the Syncfusion ASP.NET Conversion.  

2. Add the required CSS and Script files references in master page (Site.Master file) of the project. Please refer to the below screenshot for more information.

   ![](Utility_images\Project-Conversion_img10.jpeg)
   
3. Now, include the Syncfusion controls to your project. Refer the following screenshot for more information.

   ![](Utility_images\Project-Conversion_img11.jpeg)

4. Run the project and the following output will be displayed.

   ![](Utility_images\Project-Conversion_img12.jpeg)


## Project Migration 

Syncfusion provides the Project Migration add-on with the Visual Studio, which will easily migrate the existing Syncfusion ASP.NET project from one Essential Studio version to another version.

I>	The Syncfusion ASP.NET Web Application Project Migration utility is available from v13.1.0.30.

### Migrate Syncfusion Project 

The following steps direct you to migrate your existing Syncfusion ASP.NET application. 

1. Right-click on **Syncfusion ASP.NET Project** from Solution Explorer and select **Syncfusion VS Extensions**. Choose **Migrate the Project to Another version**

   ![](Utility_images/Project-Migration_img1.jpeg)

2. The **Project Migration** window appears. You can choose the required Essential Studio version that is installed in the machine. 

   ![](Utility_images/Project-Migration_img2.jpeg)

3. The **Project Migration** window allows you to configure the following options:

   i. **Essential Studio Version:** Select any version from the list of installed versions.
   
   ii. **Assemblies From:** Choose the assembly location from where it is going to be added to the project.
   
4. Click the Migrate Button. The **Project Backup** dialog will be opened. If click Yes it will backup the current project before migrate the Syncfusion project. If click No it will migrate the project to required Syncfusion version without backup
   
   ![](Utility_images/Project-Migration_img3.jpeg)
   
   
5. The Syncfusion Reference Assemblies, Scripts and CSS are updated to the corresponding version in the project.


## Sample Creator

Syncfusion provides support for Sample Creator utility, which allows you to create Syncfusion ASP.NET Projects along with the samples based on Controls and Features selection.

### Create Syncfusion ASP.NET Web Project from Sample Creator

Sample Creator can be download from the Syncfusion Dashboard. After installing the complete Essential Studio suite or ASP.NET setup, following below steps help you to create the Syncfusion ASP.NET Project via the Sample Creator utility.

1. Launch the Syncfusion Essential Studio Dashboard and select the ASP.NET platform. Select the **Sample Creator** button to launch the ASP.NET Sample Creator Wizard. Refer the following screenshot for more information.

   ![](Sample-Creator_images/SampleCreator_img1.jpeg)

2. Syncfusion Sample Creator Wizard displaying the **Controls and its Feature Selection** section

   ![](Sample-Creator_images/SampleCreator_img2.jpeg)


#### Controls Selection

Listed here are the Syncfusion ASP.NET controls so you can choose the required controls.

   ![](Sample-Creator_images/SampleCreator_img3.jpeg)

#### Feature Selection

Based on the controls, the Feature is enabled to choose the features of the corresponding controls.

   ![](Sample-Creator_images/SampleCreator_img4.jpeg)


#### Project Configuration

1. You can configure the following project details in the Sample Creator.

   * Project Type – Select the type of ASP.NET Project, either Web Application or Web Site.

   * Language – Select the language, either C# or VB.

   * VS Version – Choose the Visual Studio version.

   * .NET Framework – Choose the .NET Framework version.

   * Name – Name your Syncfusion ASP.NET Application.

   * Location – Choose the target location of your project.

   * Theme Selection – Choose the required theme.The Theme Preview section shows the controls preview before create the Syncfusion project.

   ![](Sample-Creator_images/SampleCreator_img6.jpeg)


2. When you click the Create button, the new Syncfusion ASP.NET project is created. The following resources are added in the project:

   * Added the required ASPX and Class files in the project.

     ![](Sample-Creator_images/SampleCreator_img7.jpeg)

   * Included the required Syncfusion ASP.NET scripts and themes files.

     ![](Sample-Creator_images/SampleCreator_img8.jpeg)

   * The required Syncfusion assemblies are added for selected controls under Project Reference.

     ![](Sample-Creator_images/SampleCreator_img9.jpeg)

   * Configure the Web.Config file by adding the Syncfusion reference assemblies, namespaces and controls.

     ![](Sample-Creator_images/SampleCreator_img10.jpeg)

3. Once the project is created you can open the project by clicking the Yes button. If you click No button the corresponding location of the project will be opened. Refer the following screenshot for more information.

   ![](Sample-Creator_images/SampleCreator_img11.jpeg)




