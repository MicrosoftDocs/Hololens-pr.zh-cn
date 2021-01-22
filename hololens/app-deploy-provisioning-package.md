---
title: 预配程序包
description: 了解 HoloLens 设备的应用打包、预配、部署和企业应用部署。
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
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283693"
---
# 预配程序包

预配包可用于在无法访问终结点管理的环境中准备和配置设备。 它们还可以部署到设备，而不考虑用户的身份、注册状态、在开箱即用体验 (OOBE) 期间或在设置期间应用预配 [包](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)。

## 预配包注意事项：

* 非公共应用
* 仅 USB 旁加载
* 无需自动更新 (需要通过 PPG 或) 

通过预配包安装的应用必须由本地计算机存储中的证书签名。 预配包只能将证书安装到本地计算机 (本地计算机) 存储中，因此应用和证书可以通过同一预配包进行安装。 如果要从 MDM 部署证书或通过证书管理器进行安装，请确保[](certificate-manager.md)将证书部署到本地计算机存储，以通过这种方法对安装的应用进行签名。

若要了解为 HoloLens 设备创建预配包的基础知识，请访问 [HoloLens 预配](https://docs.microsoft.com/hololens/hololens-provisioning)。 若要部署应用，必须从高级预配开始。

> [!NOTE]
> HoloLens (第一代) 具有有限的支持，支持使用预配包 (**UniversalAppInstall**) 安装应用。 HoloLens (第一代) 设备仅在 OOBE 期间仅支持通过 PPKG 安装应用，并且仅支持用户上下文安装。

## 安装

在 [Windows 配置设计器中](https://www.microsoft.com/store/productId/9NBLGGH4TX22) ，执行以下四个步骤。

1. 将 ApplicationManagement/AllowAllTrustedApps 设置为"是"。 请参阅 [：ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。

2. 导航到**UniversalAppInstall**  >  **UserContextAppLicense，** 输入**PackageFamilyName。** 请参阅 [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)。 另请参阅 [：UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。

   可以在已安装应用的设备上使用 Device Portal。 访问"应用"页，查看 PackageRelativeID 行，"！"是 **PackageFamilyName**。

3. 然后，你将看到有一个新节**ApplicationFile。** 使用此区域上载 appx 捆绑包。

4. 根据你已购买应用还是生成自己的 LOB 应用，你将需要上载许可证文件或安全证书。

    - 对于许可证文件：导航到**UniversalAppInstall**  >  **UserContextAppLicence**并浏览到许可证的位置并上载它。
    - 对于安全文件，导航到 **"证书** "，然后选择要随 .appx 捆绑包一起安装的证书。

确保将项目保存到安全位置。 然后 **导出** 为 **预配包**。  

另请参阅：[将预配包应用到 HoloLens。](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)
