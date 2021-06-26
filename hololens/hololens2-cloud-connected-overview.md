---
title: 云连接云HoloLens 2概述Remote Assist
description: 了解如何使用云HoloLens 2通过云连接的网络注册Dynamics 365 Remote Assist。
keywords: HoloLens， 管理， 云连接， Remote Assist， AAD， Azure AD， MDM， 移动设备管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923527"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>部署指南 - 云HoloLens 2云Remote Assist - 概述

本指南将帮助 IT 专业人员计划 2 Microsoft HoloLens设备，Remote Assist部署到其组织。 这将充当跨各种用例向组织部署概念证明HoloLens 2模型。 设置类似于方案 [A：部署到云连接设备](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)。 

在本指南中，我们将介绍如何将设备注册到设备管理中、根据需要应用许可证，以及验证最终用户能否在设备设置Remote Assist立即使用设备。 为此，我们将了解设置和运行所需的重要基础结构部分 - 使用 HoloLens 2。 本指南中不会应用其他设备限制或配置，但是，我们建议在完成后浏览这些选项。

## <a name="prerequisites"></a>先决条件

应采用以下基础结构来部署HoloLens 2。 如果没有，本指南中将包含设置 Azure 和 Intune：

- Wi-Fi
    - 网络通常对 Internet 和云服务开放
- Azure Active Directory (Azure AD) 注册所需的 MDM 自动注册[ (Azure AD P1 订阅) ](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
- MDM (Intune) 托管
    - 一个或多个应用程序是通过 MDM 部署的。
- 用户使用自己的公司帐户登录 (Azure AD) 
    - 支持每个设备的一个或多个用户。

:::image type="content" alt-text="云连接方案" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>了解Remote Assist

Remote Assist协作维护和修复、远程检查以及知识共享和培训。 通过连接不同角色和位置的用户，使用 Remote Assist可以与 Microsoft Teams 上的远程协作者进行连接。 它们可以组合视频、屏幕截图和批注，以实时解决问题，即使它们&#39;位于同一位置。 远程协作者可以插入参考图像、示意图和其他有用的信息，以便技术人员&#39;物理空间，以便他们可以在 HoloLens 上向上和无手工作的同时引用示意图。

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>Remote Assist许可和要求

- Azure AD订阅 (分配许可证时所需的帐户) 
- [Remote Assist订阅](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (或[Remote Assist试用版) ](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist用户

- Remote Assist许可证
- 网络连接

#### <a name="microsoft-teams-user"></a>Microsoft Teams 用户

- Microsoft Teams 或 [Teams Freemium](https://products.office.com/microsoft-teams/free)。
- 网络连接

如果计划实现此跨租户 [方案，](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)可能需要信息屏障许可证。 请参阅 [本文](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) ，确定是否需要信息屏障许可证。

## <a name="in-this-guide-you-will"></a>本指南中，你将实现以下操作：

准备：

> [!div class="checklist"]
> - [了解适用于设备HoloLens 2要素。](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [详细了解Azure AD，如果还没有，&#39;设置一个。](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [了解标识管理以及如何以最佳方式设置Azure AD帐户。](hololens2-cloud-connected-prepare.md#identity-management)
> - [详细了解 MDM，如果尚未准备好 MDM，&#39;Intune 进行设置。](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [了解应用程序的网络Remote Assist。](hololens2-cloud-connected-prepare.md#network)
> - [（可选）：用于连接到组织资源的 VPN](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

配置：

> [!div class="checklist"]
> - [如何创建用户和组。](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [如何在 Azure AD 中设置自动Azure AD。](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [如何分配应用程序许可证。](hololens2-cloud-connected-configure.md#application-licenses)

部署：

> [!div class="checklist"]
> - [设置你的HoloLens 2并验证注册。](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [验证是否可进行Remote Assist调用。](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

维护：

> [!div class="checklist"]
> - [如何使用 Remote Assist 应用更新Microsoft Store应用。](hololens2-cloud-connected-maintain.md#updates)
> - [制定支持计划。](hololens2-cloud-connected-maintain.md#support-plan)
> - [开发计划。](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>后续步骤

> [!div class="nextstepaction"]
> [云连接部署 - 准备](hololens2-cloud-connected-prepare.md)

