---
title: 与远程协助 HoloLens 2 云连接的概述
description: 了解如何使用 Dynamics 365 Remote Assist 通过云连接网络注册 HoloLens 2 设备。
keywords: HoloLens，管理，云连接，远程协助，AAD，Azure AD，MDM，移动设备管理
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
ms.openlocfilehash: 86d36275d5cf1296ca3e9fec90684a188a29f3f0
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635120"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>部署指南–云连接 HoloLens 2 与远程协助–概述

本指南将帮助 IT 专业人员规划和部署 Microsoft HoloLens 2 个设备，并向其组织提供远程协助。 在各种 HoloLens 2 用例中，这将充当对你的组织进行概念证明部署的模型。 此设置类似于 [方案 A：部署到云连接设备](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)。 

在本指南中，我们将介绍如何将设备注册到设备管理，根据需要应用许可证，并验证最终用户是否能够在设备设置时立即使用远程协助。 为此，我们将介绍设置和运行所需的重要基础结构，即利用 HoloLens 2 大规模实现部署。 本指南中不会应用任何其他设备限制或配置，但是，我们建议你在完成后浏览这些选项。

## <a name="prerequisites"></a>先决条件

为了部署 HoloLens 2，应准备好以下基础结构。 如果不是，则本指南中包括设置 Azure 和 Intune：

这是一种设置，类似于 [方案 a：部署到云连接设备](/hololens/common-scenarios#scenario-a)，这对于许多概念证明部署是一个不错的选择，其中包括：

- Wi-Fi 网络通常会完全开放到 Internet 和云服务
- 与 MDM 自动注册 Azure AD 联接--MDM (Intune) 托管
- 用户用自己的公司帐户登录 (Azure AD) 
    - 支持每个设备一个或多个用户。

:::image type="content" alt-text="云连接方案" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a>了解远程协助

远程协助允许协作式维护和修复、远程检查以及知识共享和培训。 通过连接不同角色和位置的人员，使用远程协助的技术人员可以连接 Microsoft Teams 上的远程协作者。 即使在同一位置&#39;t，它们也可以结合视频、屏幕截图和批注来实时解决问题。 远程协作者可以插入引用图像、图表和其他有用信息。该技术人员&#39;的物理空间，因此，在 HoloLens 时，他们可以参考该示意性。

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a>远程协助许可和要求

- 需要 Azure AD 帐户 (购买订阅和分配许可证) 
- [远程协助订阅](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (或 [远程协助试验](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)) 
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist 用户

- 远程协助许可证
- 网络连接

#### <a name="microsoft-teams-user"></a>Microsoft Teams 用户

- Microsoft Teams 或[Teams 免费增值](https://products.office.com/microsoft-teams/free)。
- 网络连接

如果你计划实施此 [跨租户方案](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)，你可能需要一个信息障碍许可证。 请参阅 [本文](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) ，确定是否需要信息障碍许可证。

## <a name="in-this-guide-you-will"></a>本指南中，你将实现以下操作：

准备：

> [!div class="checklist"]
> - [了解 HoloLens 2 设备的基础结构基础结构。](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [如果没有&#39;t，请详细了解 Azure AD 并设置一个。](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [了解身份管理，以及如何最好地设置 Azure AD 帐户。](hololens2-cloud-connected-prepare.md#identity-management)
> - [了解有关 MDM 的详细信息，并使用 Intune 进行设置（如果你未&#39;t 已经准备就绪）。](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [了解远程协助的网络要求。](hololens2-cloud-connected-prepare.md#network)
> - [（可选）：用于连接到组织资源的 VPN](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

配置：

> [!div class="checklist"]
> - [如何创建用户和组。](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [如何在 Azure AD 中设置自动注册。](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [如何分配应用程序许可证。](hololens2-cloud-connected-configure.md#application-licenses)

部署：

> [!div class="checklist"]
> - [设置 HoloLens 2 并验证注册。](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [验证是否可以进行远程协助呼叫。](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

维护：

> [!div class="checklist"]
> - [如何使用 Microsoft Store 应用程序更新远程协助。](hololens2-cloud-connected-maintain.md#updates)
> - [制定支持计划。](hololens2-cloud-connected-maintain.md#support-plan)
> - [开发计划。](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a>下一步

> [!div class="nextstepaction"]
> [云连接部署-准备](hololens2-cloud-connected-prepare.md)

