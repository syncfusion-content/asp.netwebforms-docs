---
layout: post
title: Installation and Deployment process for Syncfusion Essential Studio ASP.NET products
description: Learn how to install and deploy the Syncfusion ASP.NET component
platform: ASP.NET
control: Installation and Deployment
documentation: ug

---

# Installation and Deployment

## Installing with UI   

The following procedure illustrates how to install Essential Studio ASP.NET platform.

1. Double-click the Syncfusion Essential Studio Platform Setup file. The Setup Wizard opens and extracts the package automatically.

   ![](ES-Installer-for-Individual-Platform_images/Step-by-Step-Installation_img1.png)

   N> The Setup wizard extracts the syncfusionessentialstudio_(version).exe dialog, displaying the unzip operation of the package.

2. From the 2016 Vol 3 release(v14.3.0.49), you are provided with two options to unlock the Syncfusion setup.

   
   **Login To Install**   
   
   **Use Unlock Key**
   
   N> While installing the Syncfusion setup, by default **Login To Install** screen will be displayed. You can provide the email ID and password registered with Syncfusion for unlocking the Essential Studio setup and your license will be configured. For unlocking the setup with License Key, you can select the **Use Unlock Key** option in the Installer and you will be prompt to enter the license key.
   
   
   **Login To Install**

   ![](ES-Installer-for-Individual-Platform_images/Step-by-Step-Installation_img2.png)

   N> You should enter your Syncfusion Direct-Trac login credentials. If you don't have Syncfusion Direct-Trac login credentials, then you can click on Sign Up to a create new account. Else if you forgot your password, click on Reset Password to create new password. Here Email address and Password is validated and the Platform Selection window opens.


   **Use Unlock Key**

   ![](ES-Installer-for-Individual-Platform_images/Step-by-Step-Installation_img3.png)

   N> The Unlock key is validated and the Path Selection window opens.


3. After reading the License Terms and Conditions, check the **I agree to the License Terms and Conditions** check box.


4. Click Next. Select the Installation, Samples Folder and Advanced Options screen opens. 


    ![](ES-Installer-for-Individual-Platform_images/Step-by-Step-Installation_img4.png)


   N> To install in the displayed default location, click Install. You can also browse and choose a location by clicking Browse. When you have already installed any other same version‘s setup, you cannot change the install and samples path.

   * Select the **Install Syncfusion Samples** check box to install Syncfusion samples, or leave the check box clear, when you do not want to install Syncfusion samples.
   * Select the **Register Syncfusion Assemblies in GAC** check box to install the latest Syncfusion assemblies in GAC, or clear this check box when you do not want to install the latest assemblies in GAC.
   * Select the **Uninstall the previously installed Syncfusion assemblies from GAC** check box to uninstall the previously installed Syncfusion assemblies from GAC, or clear this check box to maintain the previously installed assemblies.
   * Select the **Configure Syncfusion controls in Visual Studio Toolbox** check box to configure the Syncfusion controls in the Visual Studio toolbox, or clear this check box when you do not want to configure the Syncfusion controls in the Visual Studio toolbox during setup installation. Note that you must also select the Register Syncfusion assemblies in GAC check box when you select this check box.
   * Select the **Install Syncfusion Extensions** checkbox to configure the Syncfusion Extensions in Visual Studio or clear this check box when you do not want to configure the Syncfusion Extensions in Visual Studio.


5.  Click Install.


    ![](ES-Installer-for-Individual-Platform_images/Step-by-Step-Installation_img5.png)

     N> The Completed screen is displayed once the package is installed.

    ![](ES-Installer-for-Individual-Platform_images/Step-by-Step-Installation_img6.png)


6. Select the **Run Syncfusion Control Panel** check box to launch the Syncfusion Control Panel after installing.


7. Click Finish. Essential Studio is installed in your system.

## Installing in silent mode

The Syncfusion Essential Studio Platform Installer supports installing/uninstalling the setup through Command Line. The following sections illustrate this ability. 

### Command Line Installation

Follow the steps below to install through Command Line in Silent mode.

1. Double-click the Syncfusion Essential Studio platform Setup file. The Setup Wizard opens and extracts the package automatically.
2. The SyncfusionEssentialStudio(platform)_(version).exe file is extracted into the Temp folder.
3. Run %temp%. The Temp folder will open. The SyncfusionEssentialStudio(platform)_(version).exe file is available in one of the folders.
4. Copy the SyncfusionEssentialStudio_(version).exe file in local drive. Example: D:\temp
5. Cancel the Wizard.
6. Open the Command Prompt in administrator mode and pass the following arguments.

   
   **Arguments:** “Setup file path\SyncfusionEssentialStudio(platform)_(version).exe” /Install silent /PIDKEY:“(product unlock key)” [/log “{Log file path}”] [/InstallPath:{Location to install}] [/InstallSamples:{true/false}] [/InstallAssemblies:{true/false}] [/UninstallExistAssemblies:{true/false}] [/InstallToolbox:{true/false}]


   N> [..] – Arguments inside the square brackets are optional.

   **Example:** “D:\Temp\SyncfusionEssentialStudio(platform)_13.2.0.30.exe” /Install silent /PIDKEY:“product unlock key” /log “C:\Temp\EssentialStudio_Platform.log” /InstallPath:C:\Syncfusion\x.x.x.x /InstallSamples:true /InstallAssemblies:true /UninstallExistAssemblies:true /InstallToolbox:true

	
7. Setup is installed.

   N> x.x.x.x needs to be replaced with the Essential Studio version installed in your machine and the Product Unlock Key needs to be replaced with the Unlock Key for that version. The platform should be replaced with ASP.NET, ASP.NET MVC, ASP.NET MVC Classic, Silverlight, Windows Forms, Windows Phone, WinRT, WPF, JavaScript, or LightSwitch.
   

### Command Line Uninstallation

Syncfusion Essential Studio supports uninstalling the setup through Command Line in Silent mode. The following steps illustrate this. 

1. When you do not have the extracted setup (SyncfusionEssentialStudio(platform)_(version).exe) then follow the steps from 2 to 7.
2. Double-click the Syncfusion Essential Studio platform Setup file. The Setup Wizard opens and extracts the package automatically.
3. The SyncfusionEssentialStudio(platform)_(version).exe file is extracted into the Temp folder.
4. Run %temp%. The Temp folder will open. The SyncfusionEssentialStudio(platform)_(version).exe file is available in one of the folders.
5. Copy the SyncfusionEssentialStudio(platform)_(version).exe file in local drive. Example: D:\temp
6. Cancel the Wizard.
7. Open the Command Prompt in administrator mode and pass the following arguments.
   
   **Arguments:** “Setup file path\SyncfusionEssentialStudio(platform)_(version).exe” /uninstall silent 

   **Example:** “D:\Temp\SyncfusionEssentialStudio(platform)_13.2.0.30.exe" /uninstall silent


8. Setup is uninstalled.

   N> x.x.x.x needs to be replaced with the Essential Studio version installed in your machine and the Product Unlock Key needs to be replaced with the unlock key for that version. Platform should be replaced with corresponding platform that needs to be uninstalled.
