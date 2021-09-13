---
title: 部署指南 - 使用 HoloLens 2 连接Dynamics 365 Guides - 概述
description: 了解如何通过企业HoloLens 2网络Dynamics 365 Guides设备注册设备。
keywords: HoloLens、管理、企业连接、Dynamics 365 Guides、AAD、Azure AD、MDM、移动设备管理
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
ms.openlocfilehash: 541c1080d7f5fe9491d6cb11179ea98b160f687c
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032104"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a>部署指南 - 企业连接HoloLens 2与 Dynamics 365 Guides - 概述

本指南将帮助 IT 专业人员使用 Dynamics 365 Guides (指南将 Microsoft HoloLens 2 台设备的计划) 部署到其组织。 本指南适用于试点和生产部署，类似于方案 [B：在组织的网络内部署指南](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 。 测试概念证明后，使用本指南继续将HoloLens集成到组织中。

在本指南中，我们将介绍如何在设置设备后将设备注册到现有设备管理中、根据需要应用许可证，并验证最终用户是否能够操作 Dynamics 365 指南以及使用自定义业务线应用。 

## <a name="prerequisites"></a>先决条件

以下基础结构应已就位：
- Wi-Fi
    - 可以访问内部资源且对 Internet 或云服务的访问受限的内部公司网络
    - 基于设备的证书身份验证。
- Azure Active Directory (Azure AD) 注册所需的 MDM 自动注册[ (Azure AD P1 订阅) ](/azure/active-directory/fundamentals/active-directory-whatis)
- MDM (Intune) 托管
    - 一个或多个应用程序是通过 MDM 部署的。
- 网络 
    - SCEP (PKCS 证书) 
    - 代理配置
- 用户使用自己的公司帐户登录 (Azure AD) 
    - 支持每个设备的一个或多个用户。
- 根据特定用例应用的不同设备锁定配置级别，从"完全打开"到"单应用展台"。

## <a name="guides-licensing-and-requirements"></a>[指南许可和要求](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- Azure AD 帐户
- Dynamics 365 Guides PC 和 HoloLens
- Dynamics 365 Guides订阅
    - Microsoft Dataverse (包括) 
    - Power Apps (包含) 
- Power BI Desktop
- 网络连接

[![公司联网网络示意图，阶段 1。 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![公司联网网络示意图，阶段 2。 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

## <a name="in-this-guide-you-will"></a>本指南中，你将实现以下操作：
### <a name="prepare"></a>准备
> [!div class="checklist"]
>- [了解适用于设备HoloLens 2要素。](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [详细了解Azure AD，如果没有，请设置一个。](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [了解标识管理以及如何以最佳方式设置Azure AD帐户。](hololens2-corp-connected-prepare.md#identity-management)
>- [详细了解 MDM，并设置 Intune（如果尚未准备好）。](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [熟悉基于证书的 Wi-Fi。](hololens2-corp-connected-prepare.md#certificates)
>- [熟悉代理。](hololens2-corp-connected-prepare.md#proxy)
>- [了解如何使用业务线应用。](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [详细了解为组织使用指南的方式。](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a>配置
> [!div class="checklist"]
>- [如何创建用户和组。](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [如何设置自动注册。](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [如何为企业Wi-Fi连接设置Wi-Fi证书和配置文件。](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [Upload和分配业务线 (LOB) 应用包。](hololens2-corp-connected-configure.md#app-deployment)
>- [安装程序Dynamics 365 Guides。](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
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
>- [更新HoloLens 2。](hololens2-corp-connected-maintain.md#update-hololens)
>- [如何更新指南 (应用商店应用) 。](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [如何更新 LOB 应用。](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [开发计划。](hololens2-corp-connected-maintain.md#development-plan) 
>- [制定支持计划。](hololens2-corp-connected-maintain.md#support-plan)
>- [设备管理选项。](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a>后续步骤 
> [!div class="nextstepaction"]
> [企业连接部署 - 准备](hololens2-corp-connected-prepare.md)
