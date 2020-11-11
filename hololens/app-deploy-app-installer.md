---
title: 如何通过 HoloLens 2 应用安装程序加载和安装应用
description: 幻灯片加载并通过 UI 安装应用
keywords: 应用程序管理、应用、hololens、应用安装程序
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: eba1fd00215ef197f9e32949e958bdbded089d6d
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162896"
---
# 通过应用安装程序在 HoloLens 2 上安装应用


我们将在 Windows 全息版20H2 更新后立即发布应用安装程序功能。 我们正在 ** (应用安装程序) 添加新功能，使你能够在 HoloLens 2 设备上更流畅地安装应用程序** 。 默认情况下，此功能将 **在非托管设备上处于打开**状态。 为了防止企业中断，应用安装程序此时将不可 **用于托管设备** 。  

> [!IMPORTANT]
> 此功能目前仅适用于 Windows 预览体验成员版本。 [了解有关如何在 Windows 预览体验计划内部版本中注册的详细信息](hololens-insider.md)。

在我们的 Windows 预览体验计划版本中，我们将 **添加 (应用安装程序) 的新功能，让你能够在 HoloLens 2 设备上更流畅地安装应用程序** 。 默认情况下，此功能将 **在非托管设备上处于打开**状态。 为了防止企业中断，应用安装程序此时将不可 **用于托管设备** 。  

如果以下 **任何** 条件成立，设备将被视为 "托管"：
- MDM 已 [注册](hololens-enroll-mdm.md)
- 配置了 [预配包](hololens-provisioning.md)
- 用户 [标识](hololens-identity.md) 为 AAD

现在，你可以安装应用，而无需启用开发人员模式或使用 Device Portal。  只需通过 USB 或边缘) 将 (下载到你的设备，然后在文件资源管理器中导航到 Appx 捆绑系统，系统会提示你启动安装。  或者， [从网页启动安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  与使用 MDM 的 LOB 应用部署功能从 Microsoft Store 或旁加载安装的应用一样，应用需要使用 [签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 进行数字签名，并且 [用于签名的证书必须受](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) HoloLens 设备信任才能部署应用。   

## 要求

### 对于您的设备： 
当前在适用于 HoloLens 2 设备的 [Windows 预览体验成员内部版本](hololens-insider.md) 中 avalible。 请确保使用此方法的任何设备均 [已更新](hololens-update-hololens.md)。 

### 对于你的应用： 
你的应用的解决方案配置必须是 " **主** " 或 " **发布** "，因为应用安装程序将使用应用商店中的依赖关系。 查看有关 [创建应用包](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)的详细信息。

通过此方法安装的应用必须经过数字签名。 您需要使用证书对应用进行签名。 你可以从 [MS 受信任 CA 列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)中获取证书，在这种情况下，你无需执行任何其他操作。 或者，你可以对自己的证书进行签名，但需要将证书推送到设备上。 
- 如何[使用签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)对应用进行签名。

**证书选项：** 
- [MS 受信任的 CA 列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**选择证书部署方法。** 
- [预配程序包](hololens-provisioning.md) 可应用于本地设备。
- 可以使用 MDM [将证书应用于设备配置](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。
- 使用 "设备 [证书管理器](certificate-manager.md)"。 

## 安装方法

1.  确保您的设备不被视为托管设备。
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
