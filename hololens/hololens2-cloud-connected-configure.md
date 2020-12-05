---
title: 部署指南-云通过远程辅助功能在扩展时连接到 HoloLens 2 部署-配置
description: 如何设置配置以通过云连接的网络注册 HoloLens 设备
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
ms.openlocfilehash: 43b9db96a2c29d1e3a798d0c695ab6edaa8199ac
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196267"
---
# 配置-云连接指南

在本指南的此部分中，我们&#39;将介绍如何为租户设置自动注册，以及如何为 Intune 和远程协助应用许可证。

## Azure 用户和组

Azure 和通过该扩展的 Intune，使用用户和组来帮助分配配置和许可证。 为了验证此部署流程并能够使来自一个用户的远程协助呼叫成为另一个用户，&#39;需要2个用户帐户。

我们可以创建单个用户组来分配许可证。 我们可以将这两个用户加入同一组，并对该组应用 Intune 和远程协助的许可证。

如果您没有&#39;t 对您可以使用的用户组中的两个 AAD 帐户具有访问权限，请执行以下设置：以下是的快速入门指南：

- [如何创建用户](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [如何创建组](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [将用户添加到组](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) -添加创建的用户以创建组
- [将 AAD 配置为允许用户组加入设备](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) -确保新用户组有权向 AAD 注册设备

## HoloLens 2 上的自动注册

为了获得流畅且无缝的体验，设置 Azure Active Directory 加入 (AADJ) 并将自动注册到 HoloLens 2 设备的方式是转到 Intune 2 设备。 这将允许用户只需在 OOBE 期间输入其组织的登录凭据，并自动向 AAD 注册，并将设备注册到 MDM。

通过使用 [Microsoft 终结点管理器](https://endpoint.microsoft.com/#home) ，我们可以选择服务并导航几个页面，直到可以选择 "获取 Premium 试用版"。 你很多注意到有 Azure Active Directory Premium 1 和2，因此自动注册 P1 已足够。 我们可以选择 Intune 并选择自动注册的用户范围，并选择之前创建的组。

有关完整的详细信息和步骤，请阅读有关 [如何启用 Intune 自动注册](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)的指南。

## 应用程序许可证

应用程序许可证允许用户安装公司购买的应用或从免费试用版升级到应用的完整版本。 应用程序许可证可应用于用户、用户组或设备组。 您&#39;需要您组织中的用户使用远程协助的远程协助许可证。 出于本指南的目的，我们将向在 [Azure 用户和组](hololens2-cloud-connected-configure.md#azure-users-and-groups)中创建的用户组分配远程协助许可证。

根据用户是否要从设备进行远程协助呼叫或从 Microsoft 团队发起远程协作者，许可证的要求可能有所不同。 默认情况下，"远程协助" 和 "团队" 复选框均标记。 出于本指南的目的，建议保持选中 "默认框"。

1. 了解有关 [每个角色的不同许可和产品要求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)的详细信息。 有几种不同类型的远程协助许可证，因此请务必为您的需要获得正确的许可证。
2. 您&#39;需要 [获取许可证](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)。
3. [将许可证应用](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 到组。

## 下一步

> [!div class="nextstepaction"]
> [云连接部署-部署](hololens2-cloud-connected-deploy.md)