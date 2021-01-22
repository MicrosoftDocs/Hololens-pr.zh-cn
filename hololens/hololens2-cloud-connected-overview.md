---
title: 云连接的 HoloLens 2 和远程协助概述
description: 了解如何使用 Dynamics 365 远程协助通过云连接网络注册 HoloLens 2 设备。
keywords: HoloLens， 管理， 云连接， 远程协助， AAD， Azure AD， MDM， 移动设备管理
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
ms.openlocfilehash: 835b4be101b665d2b86c2170a65c04697686e403
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283073"
---
# 部署指南 – 云连接的 HoloLens 2 和远程协助 – 概述

本指南可帮助 IT 专业人员计划 Microsoft HoloLens 2 设备并部署到其组织，总体目标是使这些设备云连接到你的组织，并准备好使用 Dynamics 365 远程协助。 请记住，这将用作跨各种 HoloLens 2 用例向组织进行概念证明部署的模型。

在指南中，我们将介绍如何将设备注册到设备管理中，根据需要应用许可证，并验证最终用户能否在设备设置时立即使用远程协助。 为此，我们将了解设置和运行所需的重要基础结构部分 ， 通过 HoloLens 2 大规模实现部署。

## 本指南中

本指南的特定目标是在 HoloLens 设备上在组织中设置远程协助。 我们将介绍实现该目标所需的措施。 为了继续关注此目标，将预先选择某些准备和配置，以便针对此部署进行优化或减少配置所需的项目。 将告知你这些选项，并可以根据您的业务需求自定义部署。

这是类似于方案 [A：](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)部署到云连接设备的设置，这是许多概念证明部署的良好选择，其中包括：

- Wi-Fi网络通常对 Internet 和云服务完全开放
- 通过 MDM 自动注册加入 Azure AD - MDM (Intune) 托管
- 用户使用自己的公司帐户登录 Azure AD (Azure AD) 
  - 支持每个设备的一个或多个用户
- 根据特定用例应用不同级别的设备锁定配置，从"完全打开"到"单个应用展台"

![云连接方案](./images/cloud-connected-guide-diagram.png)

本指南中不会应用任何其他设备限制或配置，但我们鼓励你在完成后探索这些选项。

## 了解远程协助

远程协助支持协作维护和修复、远程检查以及知识共享和培训。 通过连接不同角色和位置的用户，使用远程协助的技术人员可以与 Microsoft Teams 上的远程协作者联系。 他们可以将视频、屏幕截图和注释组合在一起，以实时解决问题，即使它们&#39;位置不同。 远程协作者可以插入参考图像、示意图和其他有用的信息，技术人员&#39;物理空间，以便他们可以在 HoloLens 上进行工作向上和自由操作时参考示意图。

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## 在本指南中，你将：

准备：

> [!div class="checklist"]
> - [了解 HoloLens 2 设备的基础结构要素。](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [了解有关 Azure AD 以及设置 Azure AD（如果尚未&#39;）的信息。](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [了解标识管理以及如何以最佳方式设置 Azure AD 帐户。](hololens2-cloud-connected-prepare.md#identity-management)
> - [了解有关 MDM 的更多信息，如果尚未准备好，&#39;使用 Intune 进行设置。](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [了解远程协助的网络要求。](hololens2-cloud-connected-prepare.md#network)
> - [（可选）：用于连接到组织资源的 VPN](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

配置：

> [!div class="checklist"]
> - [如何创建用户和组。](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [如何在 Azure AD 中设置自动注册。](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [如何分配应用程序许可证。](hololens2-cloud-connected-configure.md#application-licenses)

部署：

> [!div class="checklist"]
> - [设置 HoloLens 2 并验证注册。](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [验证你可以进行远程协助呼叫。](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

维护：

> [!div class="checklist"]
> - [如何使用 Microsoft Store 应用更新远程协助。](hololens2-cloud-connected-maintain.md#updates)
> - [制定支持计划。](hololens2-cloud-connected-maintain.md#support-plan)
> - [开发计划。](hololens2-cloud-connected-maintain.md#development-plan)

## 下一步

> [!div class="nextstepaction"]
> [云连接部署 - 准备](hololens2-cloud-connected-prepare.md)

