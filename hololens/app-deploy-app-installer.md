---
title: 如何通过 HoloLens 2 应用安装程序进行端加载和安装应用
description: 了解如何通过应用程序安装程序和端加载应用程序并对应用程序进行故障排除，以及如何通过 UI 安装应用程序。
keywords: 应用程序管理，应用，hololens，应用安装程序
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
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308356"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>通过应用安装程序在 HoloLens 2 上安装应用

> [!NOTE]
> 此功能在 [Windows 全息版20H2 –2020年12月版更新](hololens-release-notes.md)中提供。 确保你的设备已 [更新](hololens-update-hololens.md) 为使用此功能。

我们 **添加了新功能 (应用安装程序) ，使你能够在 HoloLens 2 设备上更无缝地安装应用程序** 。 **默认情况下，对于非托管设备**，此功能将处于启用状态。 若要防止企业中断，此时将不能 **为托管设备提供** 应用安装程序。  

如果满足以下 **任一** 条件，则将设备视为 "托管"：

- 已[注册](hololens-enroll-mdm.md)MDM
- 配置了 [预配包](hololens-provisioning.md)
- 用户 [标识](hololens-identity.md) Azure AD

你现在可以安装应用，而无需启用开发人员模式或使用设备门户。  通过 USB 或 Microsoft Edge 下载 () Appx 绑定到设备，并在文件资源管理器中导航到 Appx 捆绑，以提示开始安装。  或者， [通过网页启动安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  与使用 MDM 的 LOB 应用部署功能从 Microsoft Store 或旁加载安装的应用一样，需要使用 [签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 对应用进行数字签名，并且在部署应用之前，必须由 HoloLens 设备 [信任用于签署的证书](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 。

## <a name="requirements"></a>要求

### <a name="for-your-devices"></a>对于你的设备：

此功能当前在适用于 HoloLens 2 设备的 Windows 全息20H2 版本中可用。 确保所有使用此方法的设备都已 [更新](hololens-update-hololens.md)。

### <a name="for-your-apps"></a>对于你的应用：

应用的解决方案配置必须为 **Master** 或 **Release** ，因为应用安装程序将使用应用商店中的依赖项。 请参阅 [创建应用包](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)的详细信息。

通过此方法安装的应用必须进行数字签名。 需要使用证书对应用进行签名。 你可以从 [MS 可信 CA 列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)中获取证书，在这种情况下，你无需执行任何额外操作。 或者，你可以对自己的证书进行签名，但需要将证书推送到设备上。

- 如何[使用签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)对应用进行签名。

**证书选项：**

- [MS 受信任的 CA 列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**选择证书部署方法。**

- [预配包](hololens-provisioning.md) 可应用于本地设备。
- MDM 可用于 [应用具有设备配置的证书](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。
- 在设备 [证书管理器](certificate-manager.md)上使用。

## <a name="installation-method"></a>安装方法

1. 检查设备是否被视为托管设备。
1. 检查你的 HoloLens 2 设备是否已开机并且已登录。
1. 在电脑上导航到自定义应用，并将 yourapp 复制到 yourdevicename\Internal Storage\Downloads。
    完成文件复制后，你可能会断开设备连接并稍后完成安装。
1. 在 HoloLens 2 设备上，打开 " **开始" 菜单**，选择 " **所有应用** "，然后启动 " **文件资源管理器** " 应用。
1. 导航到 "下载" 文件夹。 你可能需要在应用程序的左侧面板上选择 " **此设备** "，然后导航到 "下载"。
1. 选择 yourapp 文件。
1. 应用程序安装程序将启动。 选择 " **安装** " 按钮以安装您的应用程序。

安装完成后，安装的应用将自动启动。

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>安装疑难解答

如果你的应用程序安装失败，请检查以下内容以进行故障排除：

- 您的应用程序可以是主版本或发布版本。
- 你的设备已更新到可用此功能的版本。
- 你已 [连接到 internet](hololens-network.md)。
- 已正确配置 [Microsoft Store 的终结点](hololens-offline.md) 。  

## <a name="web-installer"></a>Web 安装程序

用户可以直接从 web 服务器安装应用程序。 此流程将应用安装程序与轻松下载和安装分发方法结合使用。

### <a name="how-to-set-up-web-install"></a>如何设置 web 安装：

1. 确保你的应用已正确配置为安装。
1. 按照以下 [步骤启用从网页安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。

### <a name="end-user-experience"></a>最终用户体验：

1. 用户使用之前选择的方法接收证书并将其安装到设备。
1. 用户访问上述步骤中创建的 URL。

现在，该应用将安装到设备上。 若要查找应用，请打开 " **开始" 菜单** ，并选择 " **所有应用** " 按钮以查找应用。

- 有关应用程序安装程序安装方法疑难解答的更多帮助，请访问 [排查应用程序安装问题](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。

> [!NOTE]
> 更新过程中不支持 UI。 因此，不支持 [此页](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 上的 ShowPrompt 选项以及相关选项。

## <a name="sample-apps"></a>示例应用

若要试用具有一些示例应用的应用安装程序，请查看我们的一些可用示例：

- [MRTK 中心示例](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [表面](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [可用于测试的 UWP 示例应用](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
