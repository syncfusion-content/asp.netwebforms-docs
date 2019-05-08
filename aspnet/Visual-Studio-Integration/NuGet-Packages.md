---
layout: post
title: ASP.NET NuGet Packages | ASP.NET | Syncfusion
description: 
platform: aspnet
control: NuGet Packages
documentation: ug
---

# NuGet Packages

[NuGet](https://www.nuget.org/) can be used to automatically add files and references to your Visual Studio projects. You can use the Syncfusion ASP.NET Web Forms NuGet packages without installing the Essential Studio or ASP.NET Web Forms platform installation to development with the Syncfusion ASP.NET controls. 

From v16.2.0.46 (2018 Volume 2 Service Pack 1) onwards, all the Syncfusion components are available as NuGet packages at [nuget.org](https://www.nuget.org/profiles/SyncfusionInc). 

Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet package, you must include a license key in your projects. Refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to learn about registering Syncfusion license key in your ASP.NET application to use Syncfusion controls.

N> Starting from v17.1.0.32 (2018 Volume 1), Syncfusion will no longer publish NuGet packages at [nuget.syncfusion.com](https://nuget.syncfusion.com/).

## Installing NuGet Packages

### Using NuGet Package Manager

The NuGet Package Manager can be used to search and install NuGet packages in the Visual Studio solution or project:

1.	Right-click the project or solution in the Solution Explorer tab, and choose **Manage NuGet Packages…**

    ![ASP.NET nuget package manager](NuGet_Packages_Images/img6.png)

    Alternatively, click **Tools** menu, `NuGet Package Manager | Manage NuGet Packages for Solution...`

2.	Select the NuGet.org from the **Package source** drop-down. 

     ![Selecting one of the syncfusion universal nuget package](NuGet_Packages_Images/img7.png)             

3.	The Syncfusion ASP.NET Web Forms NuGet Packages are listed and available. Search and install the required packages in your application, by clicking **Install** button.

N> The Syncfusion NuGet packages are published in public [NuGet.org](https://www.nuget.org/) from v16.2.0.46. To Install earlier version of 16.2.0.46 Syncfusion NuGet packages, [configure Syncfusion private feed URL](https://help.syncfusion.com/aspnet/Visual-Studio-Integration/nuget-packages#syncfusion-nuget-feed-url-configuration).

### Using Package Manager Console

To reference the Syncfusion ASP.NET Web Forms component using the Package Manager Console as NuGet packages, follow the below steps: 

1.	On the **Tools** menu, select **NuGet Package Manager** and then **Package Manager Console**. 

2.	Run the following NuGet installation commands:

    ~~~
    #install specified package in default project
    Install-Package <Package Name>

    #install specified package in specified project 
    Install-Package <Package Name> - ProjectName <Project Name>
    ~~~

    **For example:**

    ~~~
    #install specified package in default project
    Install-Package Syncfusion.AspNet

    #install specified package in specified project 
    Install-Package Syncfusion.AspNet -ProjectName SyncfusionDemoApplication
    ~~~


### Using Visual Studio for macOS


Add packages can be used to search and install NuGet packages to the Visual Studio project in macOS.

1.	Right-click the folder in the project, and then select **Add Packages…** 

    ![NuGet package manager add-in for macOS](NuGet_Packages_Images/img8.png)  
              
2.	Select the NuGet.org from the **Package source** drop-down. 

    ![Add packages dialog](NuGet_Packages_Images/img9.png)  

3.	The Syncfusion ASP.NET Web Forms NuGet Packages are listed and available. Search and install the required packages in your application, by clicking **Add Package** button.

## Managing NuGet package using NuGet CLI

The NuGet Command Line Interface (CLI), nuget.exe, provides the full extent of NuGet functionality to install, create, publish, and manage packages without making any change to the project files.

1.	Download the latest NuGet CLI from [here](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe).

    N> To update the existing nuget.exe to latest version use the following command:

    ~~~
    nuget update -self
    ~~~

2.	Open the downloaded executable location in the command window, and run the following commands to download and install the required NuGet packages to a project specified in the package.config.  

    ~~~
    #install specified package in default project from specified package source for Windows Platform 
    nuget.exe install <Package name | ConfigFilePath > <Options>

    #install specified package in default project from specified package source for MAC/Linux Platform 
    mono nuget.exe install <Package name | ConfigFilePath > <Options>
    ~~~

    N> configFilePath is optional. This identifies the packages.config or solutions file that lists the packages utilized in the project. 

    **For example:**

    ~~~
    #install specific package for Windows 
    nuget.exe install “Syncfusion.AspNet”

    #install all package which mention in package.config path for Windows 
    nuget.exe install “C:\Users\SyncfusionApplication\package.config”

    #install specific package for Mac and Linux 
    mono nuget.exe install “Syncfusion.AspNet”

    #install all package which mention in package.config path for Mac and Linux 
    mono nuget.exe install “C:\Users\SyncfusionApplication\package.config”
    ~~~

N> To Install earlier version of 16.2.0.46 Syncfusion NuGet packages, [configure Syncfusion private feed URL](https://help.syncfusion.com/aspnet/Visual-Studio-Integration/nuget-packages#syncfusion-nuget-feed-url-configuration).

## Upgrading NuGet packages

### Using NuGet Package Manager 

NuGet packages can be updated to their specific version or latest version available in the Visual Studio solution or project.

1. Right-click the project or solution in the Solution Explorer tab, and choose **Manage NuGet Packages…**
   Alternatively, click **Tools** menu, `NuGet Package Manager | Manage NuGet Packages for Solution...`

2. Select the **Updates** tab to see the packages available for update. Select the required packages and the specific version from the dropdown, and click the **Update** button.

### Using Visual Studio for macOS

Using **Update** context menu from Visual Studio for Mac application, NuGet packages can be updated:

1.	Right-click the Packages folder in the project, and select **Update**. 

    ![NuGet package manager add-in for macOS](NuGet_Packages_Images/img10.png) 

2.	This will update the NuGet package to the latest version. You can double-click the Add packages and choose the specific version.

N> To update all the projects from solution, use update option in the solution level. 

### Using Package Manger Console

To update the installed Syncfusion ASP.NET Web Forms NuGet packages using the Package Manager Console, follow the below steps:

1.	On the **Tools** menu, select **NuGet Package Manager**, and then **Package Manager Console.** 

2.	Run the following NuGet installation commands:

    ~~~ 
    #Update specific NuGet package in default project
    Update-Package <Package Name>

    #Update all the packages in default project
    Update-Package 

    #Update specified package in specified project 
    Update-Package <Package Name> - ProjectName <Project Name>
    ~~~

    **For example:**

    ~~~
    #Update specified Syncfusion ASP.NET Web Forms NuGet package 
    Update-Package Syncfusion.AspNet

    #Update specified package in specified project 
    Update-Package Syncfusion.AspNet -ProjectName SyncfusionDemoApplication
    ~~~

### Using NuGet CLI

Using the NuGet CLI, all the NuGet packages in the project can be updated to the available latest version. 

1.	Download the latest NuGet CLI from [here](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe).

    N> To update the existing nuget.exe to latest version use the following command:

    ~~~
    nuget update -self
    ~~~

2.	Open the downloaded executable location in the command window. Run the following “update commands” to update the Syncfusion ASP.NET Web Forms NuGet packages:

    ~~~ 
    #update all NuGet packages from config file
    nuget update <configPath> [options]

    #update all NuGet packages
    nuget update 
    ~~~      

    N> configPath is optional. This identifies the packages.config or solutions file lists the packages utilized in the project. 
	
    **For example:**

    ~~~          
    #Update all NuGet packages from config file
    nuget update “C:\Users\SyncfusionApplication\package.config”
    ~~~

    N> Update command is not working as expected in Mono (Mac and Linux) and projects using PackageReference format.
   
## Syncfusion NuGet feed URL Configuration

### Get the Syncfusion NuGet feed URL 

You should get the private Syncfusion ASP.NET Web Forms NuGet feed URL to install or upgrade the Syncfusion ASP.NET Web Forms NuGet packages. To get the URL from Syncfusion website use the following steps:

1. Navigate to [nuget.syncfusion.com](https://nuget.syncfusion.com/), and select the **WEB** tab.     

2. Navigate to **WEB (Essential JS1)**, click the Copy URL label under ASP.NET Web Forms platform to copy the Syncfusion ASP.NET Web Forms platform NuGet feed to clipboard or directly use the following URL: 

    [https://nuget.syncfusion.com/nuget_aspnet/nuget/getsyncfusionpackages/aspnet](https://nuget.syncfusion.com/nuget_aspnet/nuget/getsyncfusionpackages/aspnet) 

    ![Syncfusion Essential JS 1 ASP.NET NuGet feed URL](NuGet_Packages_Images/img1.png)

3. Now, use this NuGet feed URL to access the Syncfusion NuGet Packages in Visual Studio. 

### Add the Syncfusion NuGet feed URL

#### Windows

1.	Open your Visual Studio application. 

2.	On the **Tools** menu, select **Options**.

3.	Expand the **NuGet Package Manager** and select **Package Sources**.

4.	Click the **Add** button (green plus), and enter the ‘Package Name’ and ‘Package Source URL’ of the Syncfusion ASP.NET Web Forms NuGet packages.
    
    **Name:** Name of the package listed in the available package sources.
    
    **Source:** Syncfusion ASP.NET NuGet Feed URL      
    [https://nuget.syncfusion.com/nuget_aspnet/nuget/getsyncfusionpackages/aspnet](https://nuget.syncfusion.com/nuget_aspnet/nuget/getsyncfusionpackages/aspnet).

5.	Click the **Update** button to add the name and source details to package sources. 

    ![NuGet Package Manager dialog with Syncfusion ASP.NET NuGet feed URL for reference](NuGet_Packages_Images/img2.png)

#### macOS 

1.	Open your Visual Studio application. 

2.	Right-click the Packages folder in the project, and then select **Add Packages…**
 
    ![NuGet package manager add-in for macOS](NuGet_Packages_Images/img3.png)

3.	Choose the **Configure Sources…** from the dropdown that appears in the left corner of the Add Packages dialog. 

    ![Add packages dialog to choose the Configure Sources](NuGet_Packages_Images/img4.png)

4.	At the bottom right corner of the dialog, click the **Add** button to enter the feed name and the URL. 
   
    **Name:** Enter the name (For e.g., Syncfusion ASP.NET Web Forms Packages).
   
    **Location:** Enter the following URL – [https://nuget.syncfusion.com/nuget_aspnet/nuget/getsyncfusionpackages/aspnet](https://nuget.syncfusion.com/nuget_aspnet/nuget/getsyncfusionpackages/aspnet).

    ![Add Package Source dialog to add Syncfusion NuGet feed](NuGet_Packages_Images/img5.png)
 
5.	Now, click **Add Source** and then click **OK**.

#### NuGet CLI 

1.	Download the latest NuGet CLI from [here](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe).

    N> To update the existing nuget.exe to latest version use the following command:

    ~~~
    nuget update -self
    ~~~

2.	Open the downloaded executable location in the command window, and run the following commands to configure the Syncfusion ASP.NET Web Forms NuGet packages:

    ~~~
    #Add specified package source in NuGet.config file for Windows platform
    nuget.exe Sources Add –Name <Source name> –Source <Source location>

    #Add specified Package Source in Nuget.config file for MAC/Linux platform
    mono nuget.exe Sources Add –Name <Source name> –Source <Source location>
    ~~~

    **For example:**

    ~~~
    #For Windows platform
    nuget.exe Sources Add –Name “Syncfusion Source” –Source “https://nuget.syncfusion.com/nuget_aspnet/nuget/getsyncfusionpackages/aspnet”

    #For MAC/Linux platform
    mono nuget.exe Sources Add –Name “Syncfusion Source” –Source “https://nuget.syncfusion.com/nuget_aspnet/nuget/getsyncfusionpackages/aspnet”
    ~~~
	
## NuGet Packages Structure

The following structure is maintained for ASP.NET platform NuGet packages from 2015 Volume 2(v13.2.0.29). The latest package cannot be updated because of the installed Syncfusion NuGet packages prior version of 2015 Volume 2(V13.2.0.29). To update Syncfusion NuGet packages latest or above version of 2015 Volume 1 Service Pack-2(v13.1.0.30), uninstall the existing packages and install the following required package manually.

<table>
   <tr>
		<td colspan="1" rowspan="2">
			Categories/Package Name<br/>
		</td>
		<td colspan="1" rowspan="2">
			Supported Controls<br/>
		</td>
		<td colspan="1" rowspan="2">
			Assemblies<br/>
		</td>
		<td colspan="2" rowspan="1">
			Assets<br/>
		</td>
		<td>
			Dependencies<br/>
		</td>
	</tr>
    <tr>
		<td>
			Scripts<br/>
		</td>
		<td>
			CSS<br/>
		</td>
		<td>
			<br/>
		</td>
	</tr>
  	<tr>
		<td>
			Syncfusion.AspNet<br/>
		</td>
		<td>
			Grid<br/>Data Visualization<br/>Layout<br/>Editors<br/>Navigation<br/>Notification<br/>To know more information about the controls for above categories navigate to the following link.<br/> {{'<http://www.syncfusion.com/products/aspnet>'| markdownify }}<br/><br/>
		</td>
		<td>
			EJ.Web<br/>
		</td>
		<td>
			ej.webform.min.js<br/><br/>
		</td>
		<td>
			-<br/>
		</td>
		<td>
			Syncfusion.Web.Base<br/>
            Syncfusion.Web.FileFormatsBase<br/>
		</td>
	</tr>
		<tr>
		<td>
			Syncfusion.AspNet.PdfViewer<br/>
		</td>
		<td>
			Pdf Viewer<br/>
		</td>
		<td>
			EJ.PdfViewer<br/>
		</td>
		<td>
			-<br/>
		</td>
		<td>
			-<br/>
		</td>
		<td>
			Syncfusion.AspNet<br/>
            Syncfusion.Web.FileFormatsBase<br/>
		</td>
	</tr>
	<tr>
		<td>
			Syncfusion.AspNet.ReportViewer<br/>
		</td>
		<td>
			Report Viewer<br/>
		</td>
		<td>
			Shared.WPF<br/>RichTextBoxAdv.WPF<br/>Chart.WPF<br/>GridCommon.WPF<br/>Grid.WPF<br/>SfMaps.WPF<br/>ReportControls.WPF<br/>ReportWriter.Base<br/>EJ.ReportViewer<br/>Gauge.WPF<br/>
		</td>
		<td>
			-<br/>
		</td>
		<td>
			-<br/>
		</td>
		<td>
			Syncfusion.AspNet<br/>Syncfusion.Web.Base<br/>Syncfusion.Web.FileFormatsBase<br/>
		</td>
	</tr>
	<tr>
		<td>
			Syncfusion.AspNet.FileFormats<br/>
		</td>
		<td>
			Excel<br/>Word<br/>PDF<br/>Power Point(Preview)<br/>
		</td>
		<td>
			DocToPDFConverter.Base<br/>ExcelToPDFConverter.Base<br/>PresentationToPDFConverter.Base<br/>HtmlConverter.Base<br/>OfficeChartToImageConverter.WPF<br/>ExcelChartToImageConverter.WPF<br/>SfChart.WPF<br/>Shared.WPF<br/>
		</td>
		<td>
			-<br/>
		</td>
		<td>
			-<br/>
		</td>
		<td>
			Syncfusion.Web.FileFormatsBase<br/>
		</td>
	</tr>
	<tr>
		<td>
			Syncfusion.AspNet.Pivot<br/>
		</td>
		<td>
			Pivot Grid<br/>Pivot Chart<br/>Pivot Client<br/>Pivot Gauge<br/>
		</td>
		<td>
			Olap.Base<br/>EJ.Pivot<br/>PivotAnalysis.Base<br/>
		</td>
		<td>
			ej.webform.min.js<br/><br/>
		</td>
		<td>
			-<br/>
		</td>
		<td>
			Syncfusion.Web.Base<br/>Syncfusion.Web.FileFormatsBase<br/>
		</td>
	</tr>
  <tr>
		<td>
			Syncfusion.Web.Base<br/>
		</td>
    <td>
			-<br/>
		</td>
		<td>
			Linq.Base<br/>EJ<br/>EJ.Export<br/>
		</td>
		<td>
			-<br/>
		</td>
		<td>
			-<br/>
		</td>
		<td>
			Syncfusion.JavaScript<br/>
		</td>
	</tr>
	<tr>
		<td>
			Syncfusion.Web.FileFormatsBase<br/>
		</td>
		<td>
			-<br/>
		</td>
		<td>
			Compression.Base<br/>XlsIO.Base<br/>Pdf.Base<br/>DocIO.Base<br/>OfficeChart.Base<br/>Presentation.Base<br/>
		</td>
		<td>
			-<br/>
		</td>
		<td>
			-<br/>
		</td>
		<td>
			-<br/>
		</td>
	</tr>
</table>


