---
# required metadata

title: Add Microsoft Edge for Windows 10 to Microsoft Intune
titleSuffix:
description: Learn about adding Microsoft Edge for Windows to Microsoft Intune.
keywords:
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology:
ms.assetid: 

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: kellieei
ms.suite: ems
search.appverid: MET150
#ms.tgt_pltfrm:
ms.custom: 
ms.collection: M365-identity-device-management
---

# Add Microsoft Edge for Windows 10 to Microsoft Intune

Before you can deploy, configure, monitor, or protect apps, you must add them to Intune. One of the available [app types](~/apps/apps-add.md#app-types-in-microsoft-intune) is Microsoft Edge *version 77 and later*. By selecting this app type in Intune, you can assign and install Microsoft Edge *version 77 and later* to devices you manage that run Windows 10.

> [!IMPORTANT]
> This app type is in **public preview** and offers developer and beta channels for Windows 10. The deployment is in English (EN) only, however end users can change the display language in the browser under **Settings** > **Languages**. Microsoft Edge is a Win32 app installed in system context and on like for like architectures (x86 app on x86 OS, and x64 app on x64 OS). Intune will detect any pre-existing Microsoft Edge installations. If it is installed in user context, a system installation will overwrite it. If it is installed in system context, installion success is reported. In addition, automatic updates of Microsoft Edge are **On** by default, and Microsoft Edge cannot be uninstalled.

> [!NOTE]
> Microsoft Edge *version 77 and later* is available for macOS as well.
> 
> You cannot use the built-in application deployment of Microsoft Edge for workplace join computers. Built-in application deployment requires the Intune management extension, which only exists for AAD joined devices. You can still deploy Microsoft Edge *version 77 and later* using an *.msi* uploaded to **Apps**, see [Add a Windows line-of-business app to Microsoft Intune](~/apps/lob-apps-windows.md).

## Prerequisites
- Windows 10 RS2 and above is required.
- Any pre-installed versions of Microsoft Edge *version 77 and later* for **developer** and **beta** channels in user context will be overwritten with Edge installed in system context.

## Configure the app in Intune
You can add a Microsoft Edge version 77 and later to Intune using the following steps:

1. Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Select **Apps** > **All apps** > **Add**.
3. In the **App type** list under the **Microsoft Edge, version 77 and later**, select **Windows 10**.

## Configure app information
In this step, you provide information about this app deployment. This information helps you identify the app in Intune, and it helps users find the app in the company portal.

1. Click **App information** to display the **App information** pane.
2. In the **App information** pane, you provide information about this app deployment. This information helps you identify the app in Intune, and it helps users find the app in the company portal.
    - **Name**: Enter the name of the app as it will be displayed in the company portal. Make sure that all names are unique. If the same app name exists twice, only one of the apps is displayed to users in the company portal.
    - **Description**: Enter a description for the app. For example, you could list the targeted users in the description.
    - **Publisher**: Microsoft appears as the publisher.
    - **Category**: Optionally, select one or more of the built-in app categories or a category that you created. This setting makes it easier for users to find the app when they browse the company portal.
    - **Display this as a featured app in the Company Portal**: Select this option to display the app prominently on the main page of the company portal when users browse for apps.
    - **Information URL**: Optionally, enter the URL of a website that contains information about this app. The URL is displayed to users in the company portal.
    - **Privacy URL**: Optionally, enter the URL of a website that contains privacy information for this app. The URL is displayed to users in the company portal.
    - **Developer**: Microsoft appears as the developer.
    - **Owner**: Microsoft appears as the owner.
    - **Notes**: Optionally, enter any notes that you want to associate with this app.
3. Select **OK**.

## Configure app settings
In this step, configure installation options for the app.

1. In the **Add App** pane, select **App settings**.
2. In the **App settings** pane, select either **Beta** or **Dev** from the **Channel** list to determine which Edge Channel you will deploy the app from.
    - **Beta** Channel is the most stable Microsoft Edge preview experience and the best choice for a full pilot within your organization. With major updates every six weeks, each release incorporates the learnings and improvements from the Dev Channel.
    - **Dev** Channel is ready for enterprise feedback on Windows, Windows Server and macOS. It updates every week and contains the latest improvements and fixes.

    > [!NOTE]
    > The Microsoft Edge browser logo is displayed with the app when users browse the company portal.

3.	Select **OK**.

## Select scope tags (optional)
You can use scope tags to determine who can see client app information in Intune. For full details about scope tags, see Use role-based access control and scope tags for distributed IT.
1.	Select **Scope (Tags)** > **Add**.
2.	Use the **Select** box to search for scope tags.
3.	Select the check box next to the scope tags you want to assign to this app.
4.	Click **Select** > **OK**.

## Add the app
When you've completed configuring the app, select **Add** from the **App app** pane. 

The app you've created is displayed in the apps list, where you can assign it to the groups that you select. 

> [!NOTE]
> Currently, if you unassign the deployment of Microsoft Edge, it will remain on the device.

## Troubleshooting
**Microsoft Edge version 77 and later for Windows 10:**<br>
Intune uses the Intune management extension to download and deploy the Microsoft Edge installer to assigned Windows 10 devices, then communicates the deployment settings to the Microsoft Edge installer, which downloads and installs the Microsoft Edge browser directly from the CDN. Reference the [prerequisites for the Intune management extension](~/apps/intune-management-extension.md#prerequisites), and the best practices outlined in accessing Azure Update Service and the CDN to ensure that your network configuration permits Windows 10 devices to access these locations. In addition, to allow access to installation files from a CDN to install the browser, you need to allow access to Windows Update endpoints. For more information, see [Manage connection endpoints for Windows 10, version 1809 – Windows Update](https://docs.microsoft.com/windows/privacy/manage-windows-1809-endpoints#windows-update) and [Network endpoints for Microsoft Intune](~/fundamentals/intune-endpoints.md).

## Next steps
- [Assign apps to groups](~/apps/apps-deploy.md)
