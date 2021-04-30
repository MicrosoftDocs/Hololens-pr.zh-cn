---
title: 预配包
description: 了解适用于 HoloLens 设备的应用打包、预配、部署和企业应用部署。
keywords: 应用，应用部署，企业应用部署，预配
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308400"
---
# <a name="provisioning-package"></a>预配包

预配包可用于在环境中准备和配置设备，而无需访问终结点管理。 还可以将它们部署到设备，而无需考虑用户的身份、注册状态、 (OOBE) ，或在 [安装过程中应用预配包](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)。

## <a name="provisioning-packages-considerations"></a>预配包注意事项：

* 非公共应用
* 仅限 USB 边负载
* 无自动更新 (需要通过 PPKGs 进行手动更新) 

通过预配包安装的应用必须通过本地计算机存储中的证书进行签名。 预配包只能将证书安装到本地计算机) 存储 (设备，因此可以通过相同的设置包安装应用和证书。 如果要从 MDM 部署证书或通过 [证书管理器](certificate-manager.md)进行安装，请确保将证书部署到本地计算机存储区，以便以这种方式对应用进行签名。

若要了解为 HoloLens 设备创建预配包的基础知识，请访问 [Hololens 预配](https://docs.microsoft.com/hololens/hololens-provisioning)。 若要部署应用，必须首先使用 "高级" 设置。

> [!NOTE]
> HoloLens (第一代) 支持通过使用预配包在 **UniversalAppInstall**)  (安装应用程序。 HoloLens (第一代) 设备仅支持在 OOBE 期间仅通过 PPKG 安装应用，并且仅支持使用用户上下文安装进行安装。

## <a name="setup"></a>设置

在 [Windows 配置设计器](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 中，执行以下四个步骤。

1. 将 ApplicationManagement/AllowAllTrustedApps 设置为 "Yes"。 请参阅： [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。

2. 导航到 **UniversalAppInstall**  >  **UserContextAppLicense** 输入 **PackageFamilyName**。 请参阅 [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)。 另请参阅： [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。

   你可以在已安装应用的设备上使用设备门户。 访问 "应用" 页，查看 "PackageRelativeID" 行，"！"是你的 **PackageFamilyName**。

3. 然后，你将看到一个新的 " **ApplicationFile**" 部分。 使用此区域上传 appx 捆绑包。

4. 你需要上传许可证文件或安全证书，具体取决于你是否已购买应用或生成自己的 LOB 应用。

    - 对于许可证文件：导航到 **UniversalAppInstall**  >  **UserContextAppLicence** ，浏览到你的许可证的位置并将其上传。
    - 对于安全文件，请导航到 " **证书** "，并选择要随 .appx 包一起安装的证书。

请确保将项目保存到安全位置。 然后将其 **导出** 为 **预配包**。  

另请参阅： [将预配包应用于 HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)。
