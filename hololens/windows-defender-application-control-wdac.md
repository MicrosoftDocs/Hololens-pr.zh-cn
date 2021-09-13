---
title: Windows Defender 应用程序控制 (WDAC)
description: 概述 Windows Defender 应用程序控件的定义，以及如何使用它来管理 HoloLens 混合现实设备。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: b5c3b55273346f330580b07e5294e7e8e65ea12d
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032162"
---
# <a name="windows-defender-application-control---wdac"></a>Windows Defender 应用程序控制 - WDAC

## <a name="overview"></a>概述

通过 WDAC，你可以配置 HoloLens 以阻止应用程序启动。 这不同于展台模式，UI 在此模式下隐藏了应用，但仍可以启动这些应用。 借助 WDAC，可以看到这些应用，但无法启动。

> [!NOTE]
> 当最终用户尝试启动 HoloLens 上的 WDAC 阻止的应用时，不能通知他们无法启动该应用。

可以为设备分配多个 WDAC 策略。 如果在系统上设置了多个 WDAC 策略，则最严格的策略会生效。 

下面是一个指导，让用户了解如何[使用 WDAC 和 Windows PowerShell 来允许或阻止 Microsoft Intune 上的 HoloLens 2 设备上的应用](/mem/intune/configuration/custom-profile-hololens)。

当用户使用第一个示例步骤搜索安装在其 Windows 10 PC 上的应用时，可能需要进行一些尝试来缩小结果范围。

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

如果你不知道包的完整名称，则可能需要多次运行 "Add-appxpackage-name \* YourBestGuess \* " 才能找到它。 一旦名称运行 "$package 1 = Get-AppxPackage PackageName"

例如，为 Microsoft Edge 运行以下代码将返回多个结果，但从该列表中，可以确定所需的完整名称为 MicrosoftEdge。

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a>HoloLens 上的应用包的包系列名称

在上面链接的指南中，你可以手动编辑 newPolicy.xml 并为仅安装在 HoloLens 上的应用程序添加其包系列名称的规则。 有时，你可能会使用不在台式计算机上的应用，你想要添加到策略中。

下面列出了适用于 HoloLens 2 设备的常用和 In-Box 应用。

| 应用名称                   | 包系列名称                                |
|----------------------------|----------------------------------------------------|
| 3D 查看器                  | Microsoft.Microsoft3DViewer_8wekyb3d8bbwe          |
| 应用安装程序              | Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup>         |
| 日历                   | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| 照相机                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | Microsoft.549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Microsoft.Dynamics365.Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| 反馈中心               | Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe         |
| 文件资源管理器              | c5e2524a-ea46-4f67-6a9465d9d515_cw5n1h2txyewy 841f |
| Mail                       | microsoft.windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | Microsoft.WindowsStore_8wekyb3d8bbwe               |
| 电影和电视                | Microsoft.ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoft.microsoftskydrive_8wekyb3d8bbwe          |
| 照片                     | 微软.Windows。Photos_8wekyb3d8bbwe             |
| 设置                   | HolographicSystemSettings_cw5n1h2txyewy            |
| 提示                       | Microsoft.HoloLensTips_8wekyb3d8bbwe               |

- 1-阻止应用程序安装程序将仅阻止应用程序安装程序应用程序，而不会阻止从其他源（例如 Microsoft Store 或 MDM 解决方案）安装的应用程序。

### <a name="how-to-find-a-package-family-name"></a>如何查找包系列名称

如果应用不在此列表中，则用户可以使用设备门户连接到已安装了希望被阻止的应用的 HoloLens 2，以确定 PackageRelativeID，并从那里获取 PackageFamilyName。

1. 在 HoloLens 2 设备上安装应用。 
1. 为开发人员打开设置 > 更新 & 安全 >，并启用 **开发人员模式** 和 **设备门户**。 
    1. 更多详细信息说明详细了解如何 [设置和使用设备门户](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。
1. 连接设备门户后，请导航到 " **视图** "，然后导航到 " **应用**"。 
1. 在 "已安装的应用" 面板中，使用下拉列表选择已安装的应用。 
1. 找到 PackageRelativeID。 
1. 在之前复制应用字符 `!` ，这些字符将是你的 PackageFamilyName。

