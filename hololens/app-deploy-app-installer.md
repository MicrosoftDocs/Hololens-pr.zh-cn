---
title: 如何通过 HoloLens 2 应用安装程序加载和安装应用
description: 幻灯片加载并通过 UI 安装应用
keywords: 应用程序管理、应用、hololens、应用安装程序
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 10/26/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 4e2256f1086c92cdf0e788ba9dddf5b74a733116
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135523"
---
# 通过应用安装程序在 HoloLens 2 上安装应用

在我们的 Windows 预览体验计划版本中，我们将 **添加 (应用安装程序) 的新功能，让你能够在 HoloLens 2 设备上更流畅地安装应用程序** 。  现在，你可以安装应用，而无需启用开发人员模式或使用 Device Portal。  只需通过 USB 或边缘) 将 (下载到你的设备，然后在文件资源管理器中导航到 Appx 捆绑系统，系统会提示你启动安装。  或者， [从网页启动安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  与使用 MDM 的 LOB 应用部署功能从 Microsoft Store 或旁加载安装的应用一样，应用需要使用 [签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 进行数字签名，并且 [用于签名的证书必须受](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) HoloLens 设备信任才能部署应用。   

此更新与桌面（[默认情况下为启用旁加载](https://blogs.windows.com/windows-insider/2019/08/07/announcing-windows-10-insider-preview-build-18956/)）的位置对齐

> [!IMPORTANT]
> 此功能目前仅在 Windows 预览体验计划内部版本19041.1377 中 avalible。 [了解有关如何在 Windows 预览体验计划内部版本中注册的详细信息](hololens-insider.md)。

> [!NOTE]
> 对于希望禁用此功能的 IT 管理员，请使用以下程序包系列名称作为你的 [WDAC 策略](windows-defender-application-control-wdac.md)的一部分。 这将仅阻止应用安装程序应用，而不会阻止从其他源（如 Microsoft Store 或你的 MDM 解决方案）安装的应用。
```
Microsoft.DesktopAppInstaller_8wekyb3d8bbwe
```
> [!NOTE]
> 建议使用 [WDAC 策略](windows-defender-application-control-wdac.md) 控制应用，但如果你只想允许 microsoft store 应用，则配置为将 [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps) 策略显式设置为 "不允许" 的设备将仅允许从 Microsoft Store 安装应用。 

## 要求

### 对于您的设备： 
> [!NOTE]
> 此功能目前仅在 Windows 预览体验计划内部版本19041.1377 中 avalible。 [了解有关如何在 Windows 预览体验计划内部版本中注册的详细信息](hololens-insider.md)。

### 对于你的应用： 
你的应用的解决方案配置必须是 " **主** " 或 " **发布** "，因为应用安装程序将使用应用商店中的依赖关系。 查看有关 [创建应用包](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)的详细信息。

通过此方法安装的应用必须经过数字签名。 您需要使用证书对应用进行签名。 你可以从 [MS 受信任 CA 列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)中获取证书，在这种情况下，你无需执行任何其他操作。 或者，你可以对自己的证书进行签名，但需要将证书推送到设备上。 
- 如何[使用签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)对应用进行签名。

**证书选项：** 
- [MS 受信任的 CA 列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**选择证书部署方法。** 
- [预配程序包](hololens-provisioning.md) 可应用于本地设备。
- 可以使用 MDM [将证书应用于设备配置](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。
- 使用 "设备 [证书管理器](hololens-insider.md#certificate-manager)"。 

## 安装方法

1.  确保 HoloLens 2 设备已开机且已登录。
1.  在你的电脑上导航到你的自定义应用，并将 yourapp 复制到 yourdevicename\Internal Storage\Downloads。 
    完成文件复制后，您可能会断开您的设备并在以后完成安装。
1.  从 HoloLens 2 设备打开 " **开始" 菜单**，选择 " **所有应用** "，然后启动 " **文件资源管理器** " 应用。
1.  导航到 "下载" 文件夹。 你可能需要在应用的左侧面板上，选择 " **此设备** "，然后导航到 "下载"。
1.  选择 yourapp 文件。 
1.  应用安装程序将启动。 选择 " **安装** " 按钮以安装你的应用。 

已安装的应用将在安装完成后自动启动。 

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

### 安装疑难解答
如果你的应用无法安装，请检查以下内容：
-   你的应用是 "主" 或 "发布" 内部版本。
- 你的设备已更新为可使用此功能的版本。 
-   您已 [连接到 internet](hololens-network.md)。
-   已正确配置 [Microsoft Store 的终结点](hololens-offline.md) 。  

## Web 安装程序

用户可以直接从 web 服务器安装应用。 这会将应用安装程序与轻松下载和安装分发方法结合使用。 

### 如何设置 web 安装：
1.  确保你的应用已正确配置为安装。
1.  请按照以下 [步骤在网页上启用此操作](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。 

### 最终用户体验：
1. 用户使用之前选择的方法接收和安装设备证书。 
1. 用户访问上述步骤中创建的 URL。

该应用现在将安装到设备。 若要查找应用，请打开 " **开始" 菜单** ，然后选择 " **所有应用** " 按钮以查找你的应用。 

-   有关此安装方法的疑难解答帮助，请访问 [应用安装程序问题疑难解答](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。 

> [!NOTE]
> 更新过程中不支持 UI。 因此，不支持 [此页面](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 上的 ShowPrompt 选项和相关选项。

## 示例应用

如果你想要使用某些示例应用尝试此操作，请查看我们的一些可用示例：
- [MRTK 示例中心](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [图](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [可用于测试的 UWP 示例应用](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
