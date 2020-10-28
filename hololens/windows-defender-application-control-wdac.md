---
title: Windows Defender 应用程序控制 - WDAC
description: 概述什么是 WDAC 以及如何使用来管理 HoloLens 设备。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: dc1deb2b159d3d41b1a1f73c33f1cd44731f8e4d
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135564"
---
# Windows Defender 应用程序控制 - WDAC

WDAC 允许 IT 管理员配置其设备，阻止在设备上启动应用。 这与设备限制的方法（如 Kiosk 模式）不同，其中显示了用户将隐藏设备上的应用但仍可启动的 UI。 在实现 WDAC 时，应用仍在 "所有应用" 列表中可见，但 WDAC 将阻止设备用户启动这些应用和进程。

> [!NOTE]
> 当最终用户尝试启动由 WDAC 阻止的应用时，在 HoloLens 上，他们将不会收到有关无法启动该应用的通知。

以下是用户了解如何 [使用 WDAC 和 Windows PowerShell 在 HoloLens 2 设备上使用 Microsoft Intune 允许或阻止应用](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)的指南。

当用户使用第一个示例步骤搜索在其 Windows 10 电脑上安装的应用时，可能需要先尝试缩小结果范围。

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

如果不知道程序包的完整名称，可能需要多次运行 "Add-appxpackage-name \ * YourBestGuess \ *" 才能找到它。 然后，一旦名称运行 "$package 1 = Get-AppxPackage name PackageName"

例如，运行以下 for Edge 将返回多个结果，但从该列表中，你可以确定所需的完整名称是 MicrosoftEdge。 

```powershell
Get-AppxPackage -name *edge*
``` 

## 用于 HoloLens 应用的程序包系列名称

在上面链接的指南中，你可以手动编辑 newPolicy.xml，并为仅在 HoloLens 上安装的应用程序添加程序包系列名称。 有时，你可能使用的应用不在桌面电脑上，而你希望添加到策略。 

下面是用于 HoloLens 2 设备的常用和 In-Box 应用的列表。

| 应用名称                   | 程序包系列名称                                |
|----------------------------|----------------------------------------------------|
| 3D 查看器                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| 应用安装程序              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</sup>         |
| 日历                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| 相机                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| 反馈中心               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| 文件资源管理器              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| 电影和电视                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| 照片                     | Microsoft.Windows.Photos_8wekyb3d8bbwe             |
| “设置”                   | HolographicSystemSettings_cw5n1h2txyewy            |
| 提示                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1-阻止应用安装程序仅阻止应用安装程序应用，而不会阻止从其他源（如 Microsoft Store 或你的 MDM 解决方案）安装的应用。

### 如何查找程序包系列名称

如果应用不在此列表中，则用户可以使用 Device Portal 连接到安装了希望阻止的应用的 HoloLens 2，以确定 PackageRelativeID 以及从那里获取 PackageFamilyName。

1. 在 HoloLens 2 设备上安装该应用。 
1. 打开设置 >-为开发人员 & 便捷性 > 更新，并启用 **开发人员模式** 和 **Device portal**。 
    1. 有关详细信息的详细说明 [，请参阅在此处设置和使用 device portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。
1. 连接设备门户后，导航到 " **视图** "，然后导航到 " **应用**"。 
1. 在 "已安装的应用" 面板中，使用下拉列表选择已安装的应用。 
1. 找到 PackageRelativeID。 
1. 在！之前复制应用字符，这将是你的 PackageFamilyName。

## 示例阻止应用安装程序

例如，你可能希望阻止 [应用安装程序](app-deploy-app-installer.md) 应用。 我们为此示例提供了一些示例代码。 请下载 [此示例的这些代码示例](https://aka.ms/HoloLensDocs-Sample-WDAC-App-Installer)。 在 zip 文件中，您可以找到：

| 文件 | 用途 |
|-|-|
| compiledPolicy | [在步骤9中创建，在最后步骤10中使用。](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| mergedPolicy.xml | [在步骤6中创建。](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| WDAC_Set syncml | 不在 WDAC 中使用，但可用于 [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) |

如果你想要尝试立即阻止应用，在这种情况下是应用安装程序安装应用，请使用 compiledPolicy 文件，然后跳到上面的链接中的步骤10。 这将允许你测试自定义策略并确保组分配和策略配置正确无误。 

如果你想要将阻止应用安装程序的 WDAC 策略与上述列表中的其他应用程序合并，或任何其他应用，则可以使用 mergedPolicy.xml 文件并继续合并新策略。 正如上面所述，WDAC 策略是累加的，因此不是必需的。 

由于应用程序安装程序应用通过尝试打开文件启动，将显示一个提示。 按 WDAC 阻止的上述应用不会出现提示，因为用户正在尝试在其设备上打开文件，因此会显示一个错误以打开文件。 

![从 WDAC 阻止应用安装](images\wdac-app-installer-no-launch.jpg)

如果你不希望使用 WDAC，你可以选择使用 [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) 来删除应用安装 UX，它是一个应用。 这样做的结果是将从设备卸载应用安装程序应用。 .appx、msix、msixbundle 和其他文件扩展名以及用于 web 到应用启动的协议将不再由应用安装程序应用处理。 用户将收到在应用商店中搜索文件扩展名/协议的处理程序的提示，并且由于未列出该应用，因此不会找到该应用。