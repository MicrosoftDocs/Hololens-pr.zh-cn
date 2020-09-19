---
title: Windows Defender 应用程序控制-WDAC
description: 概述什么是 WDAC 以及如何使用来管理 HoloLens 设备。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d1147b202d3b575fa1f2dd20f620005c786ea9fc
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016760"
---
# Windows Defender 应用程序控制-WDAC

WDAC 允许 IT 管理员配置其设备，阻止在设备上启动应用。 这与设备限制的方法（如 Kiosk 模式）不同，其中显示了用户将隐藏设备上的应用但仍可启动的 UI。 在实现 WDAC 时，应用仍在 "所有应用" 列表中可见，但 WDAC 将阻止设备用户启动这些应用和进程。

> [!NOTE]
> 当最终用户尝试启动由 WDAC 阻止的应用时，在 HoloLens 上，他们将不会收到有关无法启动该应用的通知。

以下是用户了解如何 [使用 WDAC 和 Windows PowerShell 在 HoloLens 2 设备上使用 Microsoft Intune 允许或阻止应用](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)的指南。

当用户使用第一个示例步骤搜索在其 Windows 10 电脑上安装的应用时，可能需要先尝试缩小结果范围。

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

如果不知道程序包的完整名称，可能需要多次运行 "Add-appxpackage-name \ * YourBestGuess \ *" 才能找到它。 然后，一旦名称运行 "$package 1 = Add-appxpackage-name PackageName"

例如，运行以下 for Edge 将返回多个结果，但从该列表中，你可以确定所需的完整名称是 MicrosoftEdge。 

```powershell
Get-AppxPackage -name *edge*
``` 

## 用于 HoloLens 应用的程序包系列名称

在上面链接的指南中，你可以手动编辑 newPolicy.xml，并为仅在 HoloLens 上安装的应用程序添加程序包系列名称。 有时，你可能使用的应用不在桌面电脑上，而你希望添加到策略。 

下面是用于 HoloLens 2 设备的常用应用和内置应用的列表。

| 应用名称                   | 程序包系列名称                                |
|----------------------------|----------------------------------------------------|
| 3D 查看器                  | Microsoft3DViewer_8wekyb3d8bbwe          |
| 日历                   | windowscommunicationsapps_8wekyb3d8bbwe  |
| 相机                     | HoloCamera_cw5n1h2txyewy                           |
| Cortana                    | 549981C3F5F10_8wekyb3d8bbwe              |
| Dynamics 365 Guides        | Dynamics365 Guides_8wekyb3d8bbwe         |
| Dynamics 365 Remote Assist | MicrosoftRemoteAssist_8wekyb3d8bbwe      |
| 反馈中心               | WindowsFeedbackHub_8wekyb3d8bbwe         |
| 文件资源管理器              | c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy |
| Mail                       | windowscommunicationsapps_8wekyb3d8bbwe  |
| Microsoft Store            | WindowsStore_8wekyb3d8bbwe               |
| 电影和电视                | ZuneVideo_8wekyb3d8bbwe                  |
| OneDrive                   | microsoftskydrive_8wekyb3d8bbwe          |
| 照片                     | Photos_8wekyb3d8bbwe             |
| “设置”                   | HolographicSystemSettings_cw5n1h2txyewy            |
| 提示                       | HoloLensTips_8wekyb3d8bbwe               |

如果应用不在此列表中，则用户可以使用 Device Portal 连接到安装了希望阻止的应用的 HoloLens 2，以确定 PackageRelativeID 以及从那里获取 PackageFamilyName。

1. 在 HoloLens 2 设备上安装该应用。 
1. 打开设置 >-为开发人员 & 便捷性 > 更新，并启用 **开发人员模式** 和 **Device portal**。 
    1. 有关详细信息的详细说明 [，请参阅在此处设置和使用 device portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。
1. 连接设备门户后，导航到 " **视图** "，然后导航到 " **应用**"。 
1. 在 "已安装的应用" 面板中，使用下拉列表选择已安装的应用。 
1. 找到 PackageRelativeID。 
1. 在！之前复制应用字符，这将是你的 PackageFamilyName。
