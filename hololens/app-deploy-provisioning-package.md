---
title: 预配程序包
description: 了解适用于设备的应用打包、预配、部署HoloLens部署。
keywords: 应用， 应用部署， 企业应用部署， 预配
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
ms.openlocfilehash: 5aa554f9e7fdc09c3112b628e0978ac3332bc57d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635511"
---
# <a name="provisioning-package"></a>预配程序包

预配包可用于在环境中准备和配置设备，而无需访问终结点管理。 它们还可以部署到设备，而不考虑用户的标识、注册状态、在开箱即用体验 (OOBE) 期间应用预配[包。](/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)

## <a name="provisioning-packages-considerations"></a>预配包注意事项：

* 非公共应用
* 仅 USB 旁加载
* 没有自动更新 (需要通过 PPKG) 

通过预配包安装的应用必须由本地计算机存储中的证书签名。 预配包只能将证书安装到本地计算机 (存储) ，因此，可以通过同一预配包安装应用和证书。 如果要从 MDM 部署证书或通过证书管理器进行安装，请确保[](certificate-manager.md)将证书部署到本地计算机存储，以对此安装的应用进行签名。

若要了解为设备创建预配包的HoloLens，请访问 HoloLens[设置](/hololens/hololens-provisioning)。 若要部署应用，必须从高级预配开始。

> [!NOTE]
> HoloLens (第一代) 使用预配包 (**UniversalAppInstall**) 应用的支持有限。 HoloLens (第一代) 设备仅支持在 OOBE 期间通过 PPKG 安装应用，并且仅支持用户上下文安装。

## <a name="setup"></a>设置

在[Windows 配置设计器](https://www.microsoft.com/store/productId/9NBLGGH4TX22)执行以下四个步骤。

1. 将 ApplicationManagement/AllowAllTrustedApps 设置为"是"。 请参阅[：ApplicationManagement/AllowAllTrustedApps。](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)

2. 导航到 **UniversalAppInstall**  >  **UserContextAppLicense，输入** **PackageFamilyName**。 请参阅 [UniversalAppInstall](/windows/configuration/wcd/wcd-universalappinstall)。 另请参阅 [：UserContextAppLicense](/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。

   可以在设备门户设备上使用应用。 访问"应用"页，查看 PackageRelativeID 行，"！" **PackageFamilyName**。

3. 然后，你将看到有一个新部分 **ApplicationFile**。 使用此区域上传 appx 捆绑包。

4. 根据已购买应用还是生成自己的 LOB 应用，需要上传许可证文件或安全证书。

    - 对于许可证文件：导航到 **UniversalAppInstall**  >  **UserContextAppLicence** 并浏览到许可证的位置并上传它。
    - 对于安全文件，导航到 **"证书** "，选择要与 .appx 捆绑包一起安装的证书。

确保将项目保存到安全位置。 然后将 **它** 导出为 **预配包**。  

另请参阅[：将预配包应用于 HoloLens。](/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
