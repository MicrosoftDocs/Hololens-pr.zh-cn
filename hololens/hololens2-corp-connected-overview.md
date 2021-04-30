---
title: 部署指南–公司连接的 HoloLens 2 （含 Dynamics 365 指南）-概述
description: 了解如何通过企业连接的网络使用 Dynamics 365 指南注册 HoloLens 2 设备。
keywords: HoloLens，管理，企业连接，Dynamics 365 指南，AAD，Azure AD，MDM，移动设备管理
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308481"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>部署指南-通过 Dynamics 365 的企业连接的 HoloLens 2 指南-概述

本指南将帮助 IT 专业人员规划和部署具有 Dynamics 365 指南的 Microsoft HoloLens 2 设备， (指南) 到其组织。 本指南适用于试点和生产部署，类似于 [方案 B：在组织的网络中部署](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 指南。 测试概念证明后，请使用本指南继续将 HoloLens 集成到你的组织中。

在本指南中，我们将介绍如何将设备注册到现有设备管理，根据需要应用许可证，并验证最终用户是否能够操作 Dynamics 365 指南，以及如何在设备设置后使用自定义业务线应用。 

## <a name="prerequisites"></a>先决条件

以下基础结构应该已准备就绪：
- Wi-Fi
    - 有权访问内部资源并访问 internet 或云服务的内部公司网络
    - 基于设备的证书身份验证。
- Azure Active Directory (Azure AD) 加入 MDM 自动注册 (需要 Azure AD [P1 订阅](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)) 
- MDM (Intune) 托管
    - 一个或多个应用程序通过 MDM 部署。
- 网络 
    -  (SCEP 或 PKCS) 证书
    - 代理配置
- 用户用自己的公司帐户登录 (Azure AD) 
    - 支持每个设备一个或多个用户。
- 根据特定用例应用的不同级别的设备锁定配置，从完全打开到单应用展台。

## <a name="guides-licensing-and-requirements"></a>[指导许可和要求](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- Azure AD 帐户
- Dynamics 365 指导应用程序 PC 和 HoloLens
- Dynamics 365 指南订阅
    - Microsoft Dataverse (包含) 
    -  (包含的 Power Apps) 
- Power BI Desktop
- 网络连接

![公司连接网络示意图](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a>部署阶段
### <a name="prepare"></a>准备
> [!div class="checklist"]
>- [了解 HoloLens 2 设备的基础结构基础结构。](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [了解 Azure AD 的详细信息，并设置一个（如果没有）。](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [了解身份管理，以及如何最好地设置 Azure AD 帐户。](hololens2-corp-connected-prepare.md#identity-management)
>- [如果尚未准备好，请详细了解 MDM 并使用 Intune 进行设置。](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [熟悉基于证书的 Wi-fi。](hololens2-corp-connected-prepare.md#certificates)
>- [熟悉代理。](hololens2-corp-connected-prepare.md#proxy)
>- [了解如何使用业务线应用。](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [详细了解你的组织使用指南的方式。](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>配置
> [!div class="checklist"]
>- [如何创建用户和组。](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [如何设置自动注册。](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [如何为公司 Wi-Fi 连接设置 Wi-Fi 证书和配置文件。](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [将业务线 (LOB) 应用包上传和分配。](hololens2-corp-connected-configure.md#app-deployment)
>- [设置 Dynamics 365 指南。](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [如何配置展台模式 (可选) 。](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [如何配置 WDAC (可选) 。](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a>部署
> [!div class="checklist"]
>-  [通过设备和 MDM 验证注册。](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [验证 Wi-Fi 证书。](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [验证 LOB 应用安装。](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [通过创作和操作来验证指南。](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a>维护
> [!div class="checklist"]
>- [更新 HoloLens 2。](hololens2-corp-connected-maintain.md#update-hololens)
>- [如何)  (应用商店应用的更新指南。](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [如何更新 LOB 应用。](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [开发计划。](hololens2-corp-connected-maintain.md#development-plan) 
>- [制定支持计划。](hololens2-corp-connected-maintain.md#support-plan)
>- [设备管理选项。](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>后续步骤 
> [!div class="nextstepaction"]
> [企业连接部署-准备](hololens2-corp-connected-prepare.md)
