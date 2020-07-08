---
title: 预配程序包
description: 应用、应用部署、企业应用 demployment、预配
keywords: 应用、应用部署、企业应用 demployment、预配
author: v-jodben
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
ms.openlocfilehash: 7417f9e8cf1921d9fdb57dbd96fff094e21c44f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857885"
---
# 预配程序包

预配程序包可用于在环境中准备和配置设备，而无需访问终结点管理。 也可以将它们部署到设备，而无需考虑用户身份、注册状态、在全新体验（OOBE）期间或在[安装期间应用预配包](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)。

## 预配程序包注意事项：
* 非公共应用
* 仅限 USB 盘面加载
* 无自动更新（需要通过 PPKGs 手动更新）

> [!NOTE] 
> 若要了解为 HoloLens 设备创建预配包的基础知识，请访问[HoloLens 预配](https://docs.microsoft.com/hololens/hololens-provisioning)。 若要部署应用，必须首先从高级预配开始。 

## 安装

在[Windows 配置设计器](https://www.microsoft.com/store/productId/9NBLGGH4TX22)中，请执行以下4个步骤。

1. 将 ApplicationManagement/AllowAllTrustedApps 设置为 "Yes"。 请参阅： [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。
2. 在**UniversalAppInstall**  >  **UserContextAppLicense**请输入**PackageFamilyName**。 请参阅[UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)。 另请参阅： [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。
    - 如果不知道这一点，则可以在已安装应用的设备上使用 Device Portal。 访问 "应用" 页面，查看 PackageRelativeID 行，"！" 之前的所有信息是您的**PackageFamilyName**。
3. 然后，你将看到你有一个新分区**ApplicationFile**。 使用此区域上载你的 appx 捆绑包。 
4. 根据你是否已购买你的应用或构建自己的 LOB 应用，你需要上载许可证文件或安全证书。
    - 对于许可证文件：在**UniversalAppInstall**  >  **UserContextAppLience**下，浏览到许可证的位置并上传。 
    - 对于安全文件，导航到 "**证书**" 并选择要在您的 .appx 捆绑包旁安装的证书。 

请确保将项目保存到安全位置。 然后将其**导出**为**预配包**。  
    
另请参阅：[将 provisiong 程序包应用于 HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)。
