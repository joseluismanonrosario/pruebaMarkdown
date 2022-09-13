# Use the Windows App SDK in an existing project

>* Article
>* 09/02/2022
>* 3 minutes to read
>* 6 contributors


If you have an existing desktop project in which you want to use the Windows App SDK, you can install the latest version of the Windows App SDK NuGet package in your project. Unpackaged apps (that is, apps that do not use MSIX for their deployment technology) must follow this procedure to use the Windows App SDK, but packaged apps can do this too.

> **Important**
>
>If you're working on a UWP app, refer to Migrate from UWP to the Windows App SDK.

> **Note**
>
>This procedure is supported in C# .NET 6 (and later) and C++ desktop projects. These projects can use the NuGet package from the stable release channel, preview release channge or experimental release channel.

## Prerequisites
- Visual Studio 2019 or Visual Studio 2022 with the required workloads and components for Windows app development. For more information, see Install tools for the Windows App SDK.
## Instructions
1. Open an existing project in Visual Studio.

    > Note
    >
    >If you have a C# desktop project, make sure the TargetFramework element in the project file is assigned to a Windows 10-specific moniker, such as net6.0-windows10.0.19041.0, so that it can call Windows Runtime APIs. For more information, see Call Windows Runtime APIs in desktop apps. Additionally, you must be targeting 18362 or higher as there is a known issue blocking apps that target 17763.

2. Make sure package references are enabled:

* In Visual Studio, click Tools -> NuGet Package Manager -> Package Manager Settings.
* Make sure PackageReference is selected for Default package management format.
3. Right-click your project in Solution Explorer and choose Manage NuGet Packages.

4. In the NuGet Package Manager window, select the Include prerelease check box near the top of the window, select the Browse tab, and search for one of the following packages:

* To install one of the 1.0 or later releases, search for the Microsoft.WindowsAppSDK package.
* To install one of the 0.8 releases, search for the Microsoft.ProjectReunion package.
5. After the appropriate Windows App SDK NuGet package is found, select the package and then click Install in the right pane of the NuGet Package Manager window.

![Screenshot of the Windows App SDK NuGet package being installed](https://docs.microsoft.com/en-us/windows/apps/windows-app-sdk/images/reunion-nuget-install.png)


> Note
>
>The Windows App SDK NuGet package contains other sub-packages (including Microsoft.WindowsAppSDK.Foundation, Microsoft.WindowsAppSDK.WinUI, and more) that contain the implementations for specific components in the Windows App SDK. You cannot install these sub-packages individually to reference only certain components in your project. You must install the main Windows App SDK NuGet package, which includes all of the components.

6. For unpackaged apps only: Before your unpackaged app can use Windows App SDK APIs and components, your app must call first load the Windows App SDK runtime to reference the Windows App SDK framework package. For more information, see Load the Windows App SDK runtime and Tutorial: Use the bootstrapper API in a non-MSIX-packaged app that uses the Windows App SDK.

7. Your app can now use Windows App SDK APIs and components that are available in the release channel you installed. For the list of available features, see release channels.

## Further info
If your existing project is a C++ project, and you want to call Windows Runtime APIs in the Windows App SDK, then you'll need to add support for C++/WinRT. See Visual Studio support for C++/WinRT, XAML, the VSIX extension, and the NuGet package. Look for info there about the Microsoft.Windows.CppWinRT NuGet package. Without that package, your project won't be able to find the namespace header files for Windows Runtime APIs in the Windows App SDK.

If you encounter a "Class not registered" error when you try to use a Windows App SDK component, then you might have to add to your project a dynamic dependency on the Windows App SDK Framework package. For more info, see MSIX framework packages and dynamic dependencies.

## Related topics
+ [Windows App SDK](https://docs.microsoft.com/en-us/windows/apps/windows-app-sdk/)
+ Release channels and release notes
+ Install tools for the Windows App SDK
+ Deploy apps that use the Windows App SDK