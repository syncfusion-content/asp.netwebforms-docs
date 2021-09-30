---
layout: post
title: Syncfusion Troubleshooter | ASP.NET | Syncfusion
description: Syncfusion Troubleshooter is Visual Studio extension to troubleshoot the configuration issues in Syncfusion assembly reference, webconfig entries in projects.
platform: aspnet
control: Syncfusion Extensions
documentation: ug
---

# Troubleshoot the project

Troubleshoot the project with the Syncfusion configuration and apply the fix, such as wrong.NET Framework version of a Syncfusion assembly to the project or missing any Syncfusion dependent assembly of a referred assembly. The Syncfusion Troubleshooter can perform the following tasks:

* Report the Configuration issues.  

* Apply the solution

## Report the Configuration issues

The steps below will assist you in using the Syncfusion Troubleshooter by Visual Studio.

> Before use the Syncfusion Troubleshooter for ASP.NET Web Forms, check whether the **ASP.NET Web Forms Extensions - Syncfusion** installed or not in Visual Studio Extension Manager by clicking on the Tools -> Extensions and Updates -> Installed for Visual Studio 2017 or lower and for Visual Studio 2019 by clicking on the Extensions -> Manage Extensions -> Installed. 

1. To launch the Syncfusion Troubleshooter Wizard, select one of the options below:
   
   **Option 1**  
   Open an existing Syncfusion ASP.NET Web Forms Application, Click **Syncfusion Menu** and choose **Essential Studio for ASP.NET Web Forms (EJ1) > Troubleshoot…** in Visual Studio.

   ![Syncfusion Troubleshooter via Syncfusion menu](SyncfusionTroubleshooter_images/Syncfusion_Menu_Troubleshooter.png)

   N> In Visual Studio 2019, Syncfusion menu is available under Extensions in Visual Studio menu.

   **Option 2**  
   Right-click the Project file in Solution Explorer, then select the command **Syncfusion Troubleshooter…**

   ![Syncfusion Troubleshooter add-in](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img1.png)

2. Now, analyze the project, and if any issues are discovered, it will report the project configuration issues of Syncfusion components in the Troubleshooter dialogue. If the project has no configuration issues, the dialogue box will indicate that no configuration changes are required in the following areas:

    * Syncfusion assembly references.

    * Syncfusion NuGet Packages. 

    * Syncfusion Web.config Entries.

    * Syncfusion Script files.

    * Toolbox Configuration.

   ![No configuration changes required dialog box](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img2.png)

   I> The Syncfusion Troubleshooter command will be visible only for Syncfusion projects, which means the project must contain the referred Syncfusion assemblies or NuGet packages.

   The Syncfusion Troubleshooter handles the following project configuration issues: 

   1. Assembly reference issues.

   2. NuGet related issues.

   3. Web.config entries related issues.

   4. Script file related issues.

   5. Toolbox Configuration issues.

### Assembly reference issues

The Syncfusion Troubleshooter handles the assembly reference issues listed below in Syncfusion Projects.

1. Dependent assemblies are missing for referred assemblies from project. 

   **For Instance:**  If the “Syncfusion.EJ.Pivot” assembly is referenced in the project but “Syncfusion.PivotAnalysis.Base” and other dependent assemblies of Syncfusion.EJ.Pivot are not referenced in the project, the Syncfusion Troubleshooter will report that the dependent assembly is missing.

   ![Dependent assemblies missing issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img3.png)

2. The Syncfusion assembly version is mismatched. In the same project, compare all Syncfusion assembly versions. If any Syncfusion assembly version inconsistency is discovered, the Syncfusion Troubleshooter will display the Syncfusion assembly’s version mismatch.

   **For Instance:** If the “Syncfusion.OfficeChart.Base” assembly (v15.2450.0.40) is referred to in the project, but the assembly version referred to by other Syncfusion assemblies is v15.2450.0.43. The Syncfusion Troubleshooter will display a mismatched Syncfusion assembly version.

   ![Assembly version mismatched issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img4.png)

3.	.NET Framework version mismatch (Syncfusion Assemblies) with project's .NET Framework version. The details for the supported .NET Framework for Syncfusion assemblies can be found at the following link.

   <https://help.syncfusion.com/common/essential-studio/assembly-information#supported-framework-version-for-essential-studio-assemblies> 

   **For Instance:** The application's .NET Framework is v4.6, and the "Syncfusion.EJ.PdfViewer" assembly (v16.4400.0.42 & .NET Framework version 4.0) is referred to in the same application. The Syncfusion Troubleshooter will indicate that the Syncfusion assembly's .NET Framework version is incompatible with the project's .NET Framework version.

   ![Target Framework version of application](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img5.png)

   ![Framework mismatch issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img6.png)

### NuGet issues

The Syncfusion Troubleshooter handles the following NuGet package issues in Syncfusion projects.

1. Syncfusion NuGet Packages are installed in multiple versions. If one Syncfusion NuGet Package version differs from another, the Syncfusion Troubleshooter will indicate that the Syncfusion NuGet package version is mismatched.

   **For Instance:** If you have multiple versions of the Syncfusion Web platform packages installed (v16.4.0.54 and v17.1.0.38), the Syncfusion Troubleshooter will display Syncfusion package version mismatch.
 
   ![Syncfusion NuGet Packages version mismatched issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img7.png)

2. Dependent NuGet package of the installed Syncfusion NuGet packages is missing.

   **For Instance:** If you install the Syncfusion Web NuGet package in your project without any dependencies, the Syncfusion Troubleshooter will report that the Syncfusion.Compression.Base and other dependent NuGet packages are missing.
 
   ![Dependent NuGet package missing issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img8.png)

   I> To restore the missing dependent packages, an Internet connection is required. The dependent packages will not be restored if the internet is not available.

### Web.config issues

The Syncfusion Troubleshooter handles with Web.config entry-related issues in Syncfusion projects.

1. The version of the Syncfusion assembly entry was mismatched. Each Syncfusion assembly entry version/.NET Framework version will be compared to the application's corresponding referred Syncfusion assembly.

   **For Instance:** If the “Syncfusion.EJ.Pivot” assembly (v17.1450.0.38) is mentioned in the project, but the “Syncfusion.EJ.Pivot” assembly entry version (v16.4450.0.54) is mentioned in the Web.config file. The Syncfusion Troubleshooter will display a mismatched Syncfusion assembly entry version.
 
   ![Syncfusion Toolbox Framework version mismatched issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img9.png)

2. Syncfusion assembly entry has multiple versions and is duplicated. When a Syncfusion assembly entry is presented in Web.config that is not referred to in the project, or when multiple Syncfusion assembly entries are presented in Web.config for the same Syncfusion assembly, Syncfusion Troubleshooter will display the duplicate assembly entry.

   **For Instance:** If the project contains a “Syncfusion.EJ.Web” assembly (v17.1450.0.38) entry in the Web.config file, but the “Syncfusion.EJ.Web” assembly is not referred to in the project. Duplicate assembly entry will be displayed by Syncfusion Troubleshooter.
 
   ![Duplicate Syncfusion reference assembly entry issue shown in Troubleshooter wizard ](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img10.png)

   **For Instance:** If a project contains multiple “Syncfusion.EJ.Web” assembly entries (v16.4460.0.54 && v17.1460.0.38) with mismatched assembly version/.NET Framework version in Web.config, Syncfusion Troubleshooter will display the Duplicate assembly entry and Multiple Syncfusion assembly entries.

   ![Multiple version Syncfusion reference assembly entry issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img11.png)

3. The version of the namespace entry was mismatched. If any Namespace entry version (assembly version) in ASP.NET Web Application is mismatched with the corresponding referred assembly version, Syncfusion Troubleshooter will display Namespace entry version mismatched.

   **For Instance:** If the “Syncfusion.EJ” assembly (v17.1450.0.38) is referenced in the project and the “Syncfusion.JavaScript.DataVisualization” Namespace entry version (v16.4450.0.54) is referenced in the Web.config file. The Syncfusion Troubleshooter will display a mismatched Syncfusion namespace entry version.
   
   ![Namespace entry missing issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img12.png)

4. Mismatch HTTP/Server handler entry. If any Syncfusion HTTP/Server handler entry version is mismatched when compared to the corresponding referred assembly version in the project, the Syncfusion Troubleshooter will show HTTP/Server handler entry mismatched.

   **For Instance:** If the “Syncfusion.EJ.” assembly (v17.1450.0.38) is mentioned in the project, but the “Syncfusion.JavaScript.ImageHandler” HTTP/Server handler entry version (v16.4450.0.54) is specified in the Web.config file. The Syncfusion Troubleshooter will display a mismatched Syncfusion HTTP/Server handler entry version.
   
   ![Syncfusion HTTP/Server handler entry mismatched issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img13.png)

### Toolbox Configuration Issues

The Syncfusion Troubleshooter handles the Toolbox Configuration issues listed below in Syncfusion projects.

1. If the project's .NET Framework version is not installed/configured, the Syncfusion Troubleshooter will report that the Syncfusion Toolbox .NET Framework version is mismatched.

   **For Instance:** The .NET Framework version of the project is 4.5, and Syncfusion Toolbox is not installed. 4.6 framework assemblies only in the corresponding Visual Studio, the Syncfusion Troubleshooter will display Syncfusion Toolbox framework version mismatch.
 
   ![Syncfusion Toolbox Framework version mismatched issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img14.png)

2. If the configured version of Syncfusion Toolbox differs from the most recent Syncfusion assembly reference version or NuGet package version in the same project, the Syncfusion Troubleshooter will indicate that the Syncfusion Toolbox version is mismatch.

   **For Instance:** If the most recent Syncfusion assembly reference version is v17.1.0.38 but the Toolbox assemblies are configured with v17.1.0.32, the Syncfusion Troubleshooter will report Syncfusion Toolbox version mismatch.
  
   ![Syncfusion Toolbox version mismatched issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img15.png)

### Script file issues

The Syncfusion Troubleshooter handles the following Script file issues in Syncfusion projects.

1. The version of the Syncfusion script file is mismatch. Each Syncfusion script file version will be compared to the latest version of the corresponding referred Syncfusion assembly in the application.

   **For Instance:** If Syncfusion assemblies (v17.1450.0.38) and Syncfusion script file (v16.4.0.54) are referenced in the project. The Syncfusion Troubleshooter will display a Syncfusion script file version (v16.4.0.54) that is incompatible with the project's/package version of Syncfusion (v17.1.0.38).
 
   ![Syncfusion script file version mismatched issue shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img16.png)

   **For Instance:** If Syncfusion assemblies (v17.1450.0.38) are referred to in the project, but Syncfusion script file version (v16.4.0.54) is referred to in View files when script files are referred to via a CDN link. The Syncfusion Troubleshooter will report that the Syncfusion script file version (v16.4.0.54) is incompatible with the project's Syncfusion assembly/package version (v17.1.0.38) from CDN.

   ![Syncfusion script file version mismatched issue based on CDN link shown in Troubleshooter wizard](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img17.png)

2. Syncfusion script files that are duplicates. When a Syncfusion script file is presented in the project location, which is referred to in View files by CDN link, or when Syncfusion script files are presented in multiple locations in the same project, Syncfusion Troubleshooter will display duplicate script files.

   **For Instance:** If the project has a “ej.web.all.min.js” script file entry in the View file and a “ej.web.all.min.js” script file in the project location (Scripts\ej), the Syncfusion Troubleshooter will show duplicate Syncfusion script files presented in Scripts\ej due to this script file being referred from CDN.
  
   ![Syncfusion script file duplicate issue by CDN with local script](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img18.png)

   **For Instance:** If a project has the “ej.web.all.min.js” script file available in multiple project locations ("\Scripts\ej" and "\Scripts\"), the Syncfusion Troubleshooter will display Duplicate Syncfusion script files in Scripts.
  
   ![Syncfusion script file duplicate issue by mulitple location ](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img19.png)

## Apply the solution

1. Check the corresponding check box of the issue to be resolved after loading the Syncfusion Troubleshooter dialog. Then, check “Fix Issue(s)” button.

   ![Syncfusion Troubleshooter wizard with project configuration issues](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img20.png)

2. A dialog appears, prompting you to create a backup of the project before proceeding with the troubleshooting process. Click the "Yes" button if you need to backup the project before troubleshooting.

   ![Syncfusion Troubleshooter backup dialog](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img21.jpeg)

3. Wait a moment while the Syncfusion Troubleshooter resolves the issues you selected. When the troubleshooting process is finished, a message will appear in the Visual Studio status bar that says, "Troubleshooting process completed successfully."

   ![Syncfusion Troubleshooter process success status message in visual studio status bar](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img22.jpeg)

4. Then, Syncfusion licensing registration required message box will be shown if you installed the trial setup or NuGet packages since Syncfusion introduced the licensing system from 2018 Volume 2 (v16.2.0.41) Essential Studio release. Navigate to the  [help topic](https://help.syncfusion.com/common/essential-studio/licensing/license-key#how-to-generate-syncfusion-license-key), which is shown in the licensing message box to generate and register the Syncfusion license key to your project. Refer to this [blog](https://blog.syncfusion.com/post/Whats-New-in-2018-Volume-2-Licensing-Changes-in-the-1620x-Version-of-Essential-Studio.aspx) post for understanding the licensing changes introduced in Essential Studio.   

   ![Syncfusion license registration required information dialog in Syncfusion Troubleshooter](SyncfusionTroubleshooter_images/SyncfusionTroubleshooter-img23.jpeg)