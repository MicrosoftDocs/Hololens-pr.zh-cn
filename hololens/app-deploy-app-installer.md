---
title: 如何旁加载和安装应用HoloLens 2 应用安装程序
description: 了解如何使用应用安装程序安装和排查应用问题，以及如何通过 UI 旁加载和安装应用。
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
ms.openlocfilehash: 071dfb3b211928c561fc84754dd7ed4d64886f61
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "123188910"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a>通过 HoloLens 2 在 应用安装程序

> [!NOTE]
> 此功能在 Holographic 版本[20H2 Windows 2020 年 12](hololens-release-notes.md)月更新中提供。 确保设备 [已更新为](hololens-update-hololens.md) 使用此功能。

我们 **添加了一项新功能 (应用安装程序) ，** 让你能够更无缝地在 HoloLens 2 设备上安装应用程序。 对于非 **托管设备，此功能默认为打开状态**。 为了防止企业中断，应用安装程序 **目前不适用于托管** 设备。  

如果以下任一情况 **成立，则** 设备被视为"托管"设备：

- MDM [已注册](hololens-enroll-mdm.md)
- 配置了 [预配包](hololens-provisioning.md)
- 用户 [标识](hololens-identity.md) Azure AD

现在可以安装应用，而无需启用开发人员模式或设备门户。  通过 (USB Microsoft Edge) Appx 捆绑包Microsoft Edge) 下载应用包，并导航到 文件资源管理器 中的 Appx 捆绑包，以提示你启动安装。  或者， [从网页 启动安装](/windows/msix/app-installer/installing-windows10-apps-web)。 就像使用 MDM 的 LOB 应用部署功能从 Microsoft Store 安装的应用或旁加载一样，应用需要使用签名工具进行数字签名，[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)并且用于签名的[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)证书必须受 HoloLens 设备信任，然后才能部署应用。

## <a name="requirements"></a>要求

### <a name="for-your-devices"></a>对于设备：

此功能当前在适用于Windows的 Holographic 20H2 内部HoloLens 2提供。 确保已更新使用此方法的任何 [设备](hololens-update-hololens.md)。

### <a name="for-your-apps"></a>对于应用：

应用的"解决方案配置"必须是 **"主**"或"发布"，应用安装程序将使用存储中的依赖项。 详细了解如何 [创建应用包](/windows/msix/app-installer/create-appinstallerfile-vs)。

通过此方法安装的应用必须进行数字签名。 你需要使用证书对应用进行签名。 可以从 MS 受信任的 CA 列表 [获取](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)证书，在这种情况下，无需执行任何额外操作。 也可以对自己的证书进行签名，但需要将证书推送到设备上。

- 如何使用签名 [工具对应用进行签名。](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)

**证书选项：**

- [MS 受信任的 CA 列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**选择证书部署方法。**

- [预配包](hololens-provisioning.md) 可应用于本地设备。
- MDM 可用于应用 [具有设备配置的证书](/mem/intune/protect/certificates-configure)。
- 使用设备证书 [管理器 上的](certificate-manager.md)。

## <a name="installation-method"></a>安装方法

1. 检查设备是否被视为托管设备。
1. 检查你的HoloLens 2设备是否已打开且已登录。
1. 在电脑上导航到自定义应用，将 yourapp.appxbundle 复制到 yourdevicename\Internal 存储\Downloads。
    复制完文件后，可以断开设备连接，并稍后完成安装。
1. 从HoloLens 2打开"开始 **"菜单**，选择"所有 **应用**"**并** 启动文件资源管理器应用。
1. 导航到"下载"文件夹。 可能需要先在应用的左侧面板中选择"此 **设备** "，然后导航到"下载"。
1. 选择 yourapp.appxbundle 文件。
1. 系统应用安装程序启动。 选择" **安装** "按钮以安装应用。

安装完成后，已安装的应用将自动启动。

![通过 应用安装程序 安装 MRTK 示例。](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a>安装疑难解答

如果应用安装失败，请检查以下各项以进行故障排除：

- 应用是主版本或发布版本。
- 设备将更新为提供此功能的生成。
- 已[连接到 Internet。](hololens-network.md)
- [已正确配置Microsoft Store](hololens-offline.md)终结点。  

## <a name="web-installer"></a>Web 安装程序

用户可以直接从 Web 服务器安装应用。 此流使用结合使用应用安装程序下载和安装分发方法。

### <a name="how-to-set-up-web-install"></a>如何设置 Web 安装：

1. 确保应用已正确配置为安装。
1. 按照 [以下步骤从网页 启用安装](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。

### <a name="end-user-experience"></a>最终用户体验：

1. 用户使用前面选择的方法接收证书并安装到设备。
1. 用户访问通过上述步骤创建的 URL。

应用现在将安装到设备。 若要查找应用，请打开"开始"菜单并选择"所有 **应用**"按钮以查找应用。

- 有关排查应用安装程序安装方法问题的帮助，请访问 [排查应用安装程序问题](/windows/msix/app-installer/troubleshoot-appinstaller-issues)。

> [!NOTE]
> 不支持在更新过程中使用 UI。 因此，此页上的 ShowPrompt [选项](/windows/msix/app-installer/update-settings) 和相关选项不受支持。

## <a name="sample-apps"></a>示例应用

尝试使用应用安装程序示例应用之一进行试用。 
> [!div class="nextstepaction"]
> [示例应用](/windows/mixed-reality/develop/features-and-samples)
