---
title: 如何通过 HoloLens 2 应用安装程序旁加载和安装应用
description: 通过 UI 加载和安装应用
keywords: 应用管理， 应用， hololens， 应用安装程序
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
ms.openlocfilehash: ab0c58d5a97d5dbaf83adf321d1f9fbc01b3ad03
ms.sourcegitcommit: 37910c10f0f98aa9cbdc29124cd8f14ee0af3fbd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2021
ms.locfileid: "11280651"
---
# 通过应用安装程序在 HoloLens 2 上安装应用

> [!NOTE]
> 此功能在 Windows 全息版版本 [20H2 – 2020 年 12 月更新中可用](hololens-release-notes.md)。 确保设备 [已更新](hololens-update-hololens.md) 为使用此功能。

我们已 **在应用安装程序 (新增** 功能) 允许你在 HoloLens 2 设备上更加无缝地安装应用程序。 对于非 **托管设备，该功能将默认打开**。 为了防止企业中断，应用安装程序目前对托管 **设备** 不可用。  

如果以下任一项为真， **则设备** 将被视为"托管"设备：

- MDM [已注册](hololens-enroll-mdm.md)
- 使用预配 [包配置](hololens-provisioning.md)
- 用户 [标识](hololens-identity.md) 为 Azure AD

你现在无需启用开发人员模式或使用 Device Portal 即可安装应用。  将 (USB 或 Microsoft Edge) Appx 捆绑包下载到设备，并在文件资源管理器中导航到 Appx 捆绑包，以提示开始安装。  或者， [从网页启动安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  与从 Microsoft Store 安装的应用或使用 MDM 的 LOB 应用部署功能旁加载的应用一样，需要使用签名[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)工具对应用进行[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)数字签名，并且用于签名的证书必须受 HoloLens 设备信任，然后才能部署应用。

## 要求

### 对于你的设备：

 功能目前适用于 HoloLens 2 设备的 Windows Holographic 20H2 版本。 确保已更新使用此方法的任何 [设备](hololens-update-hololens.md)。

### 对于你的应用： 
应用的解决方案配置必须是**主**版本或版本，因为应用**** 安装程序将使用应用商店中的依赖项。 查看有关创建 [应用包的更多内容](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)。

通过此方法安装的应用必须进行数字签名。 你需要使用证书对应用进行签名。 可以从 MS 受信任 [CA](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)列表获取证书，在这种情况下，无需执行任何额外操作。 或者你可以对你自己的证书进行签名，但是该证书将需要推送到设备。

- 如何使用签名 [工具对应用进行签名。](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**证书选项：**

- [MS 受信任 CA 列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**选取证书部署方法。**

- [预配包](hololens-provisioning.md) 可应用于本地设备。
- MDM 可用于应用 [具有设备配置的证书](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。
- 使用 on 设备 [证书管理器](certificate-manager.md)。

## 安装方法

1. 检查设备是否被视为托管设备。
1. 检查 HoloLens 2 设备是否打开并登录。
1. 在电脑上导航到自定义应用，将app.appxbundle 复制到 yourdevicename\Internal Storage\Downloads。
    复制完文件后，可能会断开设备连接，稍后完成安装。
1. 从 HoloLens 2 设备打开"开始" **菜单**，选择 **"所有应用** "并启动 **"文件资源管理器"** 应用。
1. 导航到"下载"文件夹。 你可能需要在应用的左侧面板上先选择"此设备****"，然后导航到"下载"。
1. 选择 yourapp.appxbundle 文件。
1. 应用安装程序将启动。 选择 **"安装** "按钮以安装应用。

安装完成后，已安装的应用将自动启动。

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

### 安装疑难解答

如果应用安装失败，请查看以下内容进行疑难解答：

- 你的应用是主版本或发布版本。
- 你的设备将更新为提供此功能的生成。
- 你[已连接到 Internet。](hololens-network.md)
- 正确 [配置了 Microsoft Store](hololens-offline.md) 终结点。  

## Web 安装程序

用户可以直接从 Web 服务器安装应用。 此流将应用安装程序与简单的下载和安装分发方法结合使用。

### 如何设置 Web 安装：

1. 确保应用已正确配置为安装。
1. 按照 [以下步骤从网页启用安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。

### 最终用户体验：

1. 用户使用之前选择的方法接收证书并安装到设备。
1. 用户访问通过上述步骤创建的 URL。

应用现在将安装到设备。 若要查找应用， **请打开"** 开始"菜单并选择"所有 **应用"** 按钮以查找你的应用。

- 有关应用安装程序安装方法疑难解答的更多帮助，请访问 [疑难解答应用安装程序问题](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。

> [!NOTE]
> 不支持更新过程中 UI。 因此，此页上的 ShowPrompt [选项](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 和相关选项不受支持。

## 示例应用

若要使用一些示例应用试用应用安装程序，请查看我们的一些可用示例：

- [MRTK 示例中心](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [Surfaces](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [可用于测试的 UWP 示例应用](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
