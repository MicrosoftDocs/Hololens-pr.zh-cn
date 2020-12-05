---
title: 部署指南–云连接的 HoloLens 2 和远程协助-概述
description: 通过连接到云的网络注册 HoloLens 设备
keywords: HoloLens、管理、云连接、远程协助、AAD、Azure AD、MDM、移动设备管理
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
ms.openlocfilehash: ba3f826360f999a72e671166af7a19d19ce9c567
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196272"
---
# 部署指南– Cloud 通过远程协助连接 HoloLens 2-概述

本指南可帮助 IT 专业人员规划 Microsoft HoloLens 2 设备并将其部署到其组织，其整体目标是将这些设备云与你的组织连接到你的组织，使其具有可供使用的动态365远程协助。 请记住，这将用作你的组织在各种 HoloLens 2 使用案例中的概念证明部署的模型。

在本指南中，我们将介绍如何将设备注册到你的设备管理，根据需要应用许可证，并验证最终用户是否能够在设置设备时立即使用远程协助。 为此，我们将获得在设置和运行时需要的重要基础结构的重要部分–通过使用 HoloLens 2 的比例实现部署。

## 本指南中

本指南具有在您的 HoloLens 设备上设置远程协助的特定目标。 我们将介绍实现该目标所需的 necessities。 为了保持重点关注此目标，需要预先选择某些准备和配置，以便针对此部署进行优化或减少需要配置的项目。 系统将通知你这些选项，并且可以根据你的业务需求自定义你的部署。

这种设置类似于 [方案 a：部署到云连接设备](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)，这对于许多概念验证部署都是一个不错的选择，其中包括：

- Wi-Fi 网络通常完全开放于 Internet 和云服务
- 具有 MDM 自动注册的 Azure AD 联接-MDM (Intune) 托管
- 用户利用其自己的公司帐户登录 (AAD) 
  - 每个设备支持的单个或多个用户
- 不同级别的设备锁定配置基于特定使用情形（从完全打开到单应用展台）应用

![连接到云的方案](./images/cloud-connected-deployment-chart.png)

本指南中不会应用任何其他设备限制或配置，但我们建议你在完成后研究这些选项。

## 了解远程协助

远程协助允许进行协作维护和修复、远程检查以及知识共享和培训。 通过连接不同角色和位置的人员，使用远程协助的技术人员可以与 Microsoft 团队中的远程协作者联系。 即使在同一位置&#39;t，他们也可以结合视频、屏幕截图和注释来实时解决问题。 远程协作者可以插入参考图像、图表和其他有用的信息技术人员&#39;的物理空间，以便他们可以在使用 HoloLens 和在 HoloLens 上运行时引用示意性的图表。

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## 在本指南中，你将：

准备

> [!div class="checklist"]
> - [了解 HoloLens 2 设备的基础结构基础知识。](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [了解有关 AAD 的详细信息，如果您不是&#39;的，请设置一个。](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [了解身份管理以及如何最佳设置 AAD 帐户。](hololens2-cloud-connected-prepare.md#identity-management)
> - [了解有关 MDM 的详细信息，如果&#39;t 已准备好，则使用 Intune 进行设置。](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [了解远程协助的网络要求。](hololens2-cloud-connected-prepare.md#network)
> - [可选： VPN 连接到组织资源](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

对

> [!div class="checklist"]
> - [如何创建用户和组。](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [如何在 AAD 中设置自动注册。](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [如何分配你的应用程序许可证。](hololens2-cloud-connected-configure.md#application-licenses)

部署

> [!div class="checklist"]
> - [设置 HoloLens 2 并验证注册。](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [验证您是否可以进行远程协助呼叫。](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

着

> [!div class="checklist"]
> - [如何使用 Microsoft Store 应用更新远程协助。](hololens2-cloud-connected-maintain.md#updates)
> - [制定支持计划。](hololens2-cloud-connected-maintain.md#support-plan)
> - [开发计划。](hololens2-cloud-connected-maintain.md#development-plan)

## 下一步

> [!div class="nextstepaction"]
> [云连接部署-准备](hololens2-cloud-connected-prepare.md)

