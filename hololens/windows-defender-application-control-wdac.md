---
title: Windows Defender 应用程序控制 - WDAC
description: 概述什么是 WDAC 以及如何用于管理 HoloLens 设备。
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
ms.openlocfilehash: d337f9856eaeac433524d7bb8b60e9a24e264b80
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252643"
---
# Windows Defender 应用程序控制 - WDAC

WDAC 允许 IT 管理员配置其设备以阻止在设备上启动应用。 这不同于设备限制方法（如展台模式）的方法，即向用户显示隐藏设备上应用但仍可以启动应用的 UI。 实现 WDAC 时，应用仍显示在"所有应用"列表中，但 WDAC 会阻止设备用户启动这些应用和进程。

可以为设备分配多个 WDAC 策略。 如果在一个系统上设置了多个 WDAC 策略，则最严格的策略将生效。 

> [!NOTE]
> 当最终用户尝试启动被 WDAC 阻止的应用时，在 HoloLens 上，他们将不会收到有关无法启动该应用的通知。

以下是用户了解如何使用 WDAC 和 Windows PowerShell在 [HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)设备上使用 Microsoft Intune 允许或阻止应用的指南。

当用户使用第一个示例步骤搜索安装在其 Windows 10 电脑上的应用时，他们可能需要尝试缩小结果范围。

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

如果不知道程序包的完整名称，可能需要多次运行"Get-AppxPackage -name \*YourBestGuess\*"才能找到它。 然后，运行名称"$package 1 = Get-AppxPackage -name Actual.PackageName"

例如，为 Microsoft Edge 运行以下代码将返回多个结果，但从该列表可确定所需的全名是 Microsoft.MicrosoftEdge。

```powershell
Get-AppxPackage -name *edge*
``` 

## HoloLens 上应用的程序包系列名称

在以上链接的指南中，你可以手动编辑newPolicy.xml并添加仅安装在 HoloLens 及其程序包系列名称上的应用程序的规则。 有时，你可能使用一些应用，这些应用不在你希望添加到策略的台式电脑上。

下面是 HoloLens 2 设备的常用In-Box应用列表。

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

- 1 - 阻止应用安装程序将仅阻止应用安装程序应用，不会阻止从其他源（如 Microsoft Store 或 MDM 解决方案）安装的应用。

### 如何查找程序包系列名称

如果应用不在此列表上，则用户可以使用 Device Portal（连接到已安装希望阻止的应用的 HoloLens 2）来确定 PackageRelativeID，然后从该门户获取 PackageFamilyName。

1. 在 HoloLens 2 设备上安装应用。 
1. 打开"设置>更新&安全 ->，然后启用开发人员**模式****，然后启用 Device Portal。** 
    1. 更多详细信息说明在此处阅读有关 [设置和使用设备门户的详细信息](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。
1. 连接 Device Portal 后，导航到 **"视图**"和"**应用"。** 
1. 在"已安装的应用"面板中，使用下拉列表选择已安装的应用。 
1. 找到 PackageRelativeID。 
1. 在 ！之前复制应用字符，这些字符将是你的 PackageFamilyName。


