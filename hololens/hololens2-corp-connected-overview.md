---
title: 部署指南 - 使用 Dynamics 365 指南的企业连接的 HoloLens 2 - 概述
description: 了解如何通过企业连接网络通过 Dynamics 365 Guides 注册 HoloLens 2 设备。
keywords: HoloLens， 管理， 企业连接， Dynamics 365 指南， AAD， Azure AD， MDM， 移动设备管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448515"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>部署指南 - 使用 Dynamics 365 指南的企业连接的 HoloLens 2 - 概述

本指南将借助 Dynamics 365 指南和指南帮助 IT 专业人员计划和部署 Microsoft HoloLens 2 (指南) 组织。 本指南非常适用于试验和生产部署，类似于方案 [B：在组织的网络内部部署](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 指南。 测试概念证明后，使用本指南将 HoloLens 集成到组织中。

在本指南中，我们将介绍在设备设置后如何将设备注册到现有设备管理中、根据需要应用许可证，并验证最终用户能否运行 Dynamics 365 指南以及使用自定义业务线应用。 

## <a name="prerequisites"></a>必备条件

以下基础结构应已就位：
- Wi-Fi
    - 具有内部资源访问权限和 Internet 或云服务受限访问权的内部企业网络
    - 基于设备的证书身份验证。
- Azure Active Directory (Azure AD) 加入所需的 [Azure AD P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 订阅 (MDM 自动注册) 
- Mdm (Intune) 托管
    - 一个或多个应用程序通过 MDM 部署。
- 网络 
    - SCEP (PKCS 证书) 
    - 代理配置
- 用户使用自己的公司帐户在 Azure AD (登录) 
    - 支持每个设备的一个或多个用户。
- 根据特定用例应用的不同设备锁定配置级别，从完全打开到单个应用展台。

## [<a name="guides-licensing-and-requirements"></a>指南 许可和要求](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Azure AD 帐户
- Dynamics 365 指南应用程序电脑和 HoloLens
- Dynamics 365 Guides 订阅
    - Microsoft Dataverse (包括) 
    - Power Apps (包括) 
- Power BI Desktop
- 网络连接

![企业连接的网络图](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a>部署阶段
### <a name="prepare"></a>准备
> [!div class="checklist"]
>- [了解 HoloLens 2 设备的基础结构要素。](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [详细了解 Azure AD，如果没有，请设置一个。](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [了解标识管理以及如何以最佳方式设置 Azure AD 帐户。](hololens2-corp-connected-prepare.md#identity-management)
>- [了解有关 MDM 和 Intune 设置（如果你还没有准备好 MDM）的更多信息。](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [熟悉基于证书的 WLAN。](hololens2-corp-connected-prepare.md#certificates)
>- [熟悉代理。](hololens2-corp-connected-prepare.md#proxy)
>- [了解如何使用业务线应用。](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [了解有关你为组织使用指南的方式。](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>配置
> [!div class="checklist"]
>- [如何创建用户和组。](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [如何设置自动注册。](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [如何为 Corporate Wi-Fi Connectivity 设置 Wi-Fi 证书和配置文件。](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [上传并分配业务线 (LOB) 应用包。](hololens2-corp-connected-configure.md#app-deployment)
>- [设置 Dynamics 365 Guides。](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [如何配置展台模式 (可选) 。](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [如何配置 WDAC (可选) 。](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>部署
> [!div class="checklist"]
>-  [通过设备和 MDM 验证注册。](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [验证Wi-Fi证书。](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [验证 LOB 应用安装。](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [通过创作和操作验证指南。](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>维护
> [!div class="checklist"]
>- [更新 HoloLens 2。](hololens2-corp-connected-maintain.md#update-hololens)
>- [如何更新指南 (应用) 。](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [如何更新 LOB 应用。](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [开发计划。](hololens2-corp-connected-maintain.md#development-plan) 
>- [制定支持计划。](hololens2-corp-connected-maintain.md#support-plan)
>- [设备管理选项。](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>下一步 
> [!div class="nextstepaction"]
> [企业连接的部署 - 准备](hololens2-corp-connected-prepare.md)
