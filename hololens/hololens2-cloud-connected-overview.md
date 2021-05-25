---
title: 具有远程协助的云连接的 HoloLens 2 概述
description: 了解如何使用 Dynamics 365 远程协助通过云连接的网络注册 HoloLens 2 设备。
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397648"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a>部署指南–云连接了 HoloLens 2 与远程协助–概述

本指南可帮助 IT 专业人员规划和部署 Microsoft HoloLens 2 设备到其组织，其整体目标是将这些设备云连接到你的组织，并使用 Dynamics 365 远程协助来使用。 请记住，这将作为对你的组织进行概念证明部署的模型，涵盖各种 HoloLens 2 用例。

在本指南中，我们将介绍如何将设备注册到设备管理，根据需要应用许可证，并验证最终用户是否能够在设备设置时立即使用远程协助。 要执行此操作，我们将介绍设置和运行所需的重要基础结构，即利用 HoloLens 2 大规模实现部署。

[![云连接方案 ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)
## <a name="in-this-guide"></a>本指南内容

本指南具有在你的 HoloLens 设备上设置远程协助的具体目标。 我们将介绍实现该目标所需的必要条件。 为了保持焦点在此目标上，将预先选择某些准备和配置，以便针对此部署进行优化或减少配置所需的项。 系统会通知你这些选择，并可根据你的业务需求自定义你的部署。

这是一种设置，类似于 [方案 a：部署到云连接设备](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)，这对于许多概念证明部署是一个不错的选择，其中包括：

- Wi-Fi 网络通常会完全开放到 Internet 和云服务
- 与 MDM 自动注册 Azure AD 联接--MDM (Intune) 托管
- 用户用自己的公司帐户登录 (Azure AD) 
  - 每个设备支持一个或多个用户
- 根据特定用例（从"完全打开"到"单应用展台"）应用不同级别的设备锁定配置



本指南中不会应用其他设备限制或配置，但我们建议在完成后浏览这些选项。

## <a name="learn-about-remote-assist"></a>了解Remote Assist

Remote Assist协作维护和修复、远程检查以及知识共享和培训。 通过连接不同角色和位置的用户，使用 Remote Assist可以与 Microsoft Teams 上的远程协作者进行连接。 它们可以组合视频、屏幕截图和批注，以实时解决问题，即使它们&#39;位于同一位置。 远程协作者可以插入参考图像、示意图和其他有用的信息，以便技术人员&#39;物理空间，以便他们可以在 HoloLens 上向上和无手工作的同时引用示意图。

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a>本指南中，你将实现以下操作：

准备：

> [!div class="checklist"]
> - [了解适用于设备HoloLens 2要素。](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [详细了解Azure AD，如果还没有，&#39;设置一个。](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [了解标识管理以及如何以最佳方式设置Azure AD帐户。](hololens2-cloud-connected-prepare.md#identity-management)
> - [详细了解 MDM，如果尚未准备好 MDM，&#39;Intune 进行设置。](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [了解应用程序的网络Remote Assist。](hololens2-cloud-connected-prepare.md#network)
> - [（可选）：用于连接到组织资源的 VPN](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

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
> [云连接部署-准备](hololens2-cloud-connected-prepare.md)

