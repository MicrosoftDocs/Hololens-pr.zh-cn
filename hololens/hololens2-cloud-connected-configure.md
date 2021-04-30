---
title: 部署指南–云连接的 HoloLens 2 大规模部署，具有远程协助-配置
description: 了解如何设置配置以使用远程协助在大规模连接的云连接网络上注册 HoloLens 设备。
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308388"
---
# <a name="configure---cloud-connected-guide"></a>配置-云连接指南

在本指南的此部分中，我们&#39;介绍如何为租户设置自动注册，以及如何为 Intune 和远程协助应用许可证。

## <a name="azure-users-and-groups"></a>Azure 用户和组

Azure 以及该扩展的 Intune 使用用户和组来帮助分配配置和许可证。 为了验证此部署流并能够向另一个用户提供远程协助调用，&#39;需要两个用户帐户。

我们可以将单个用户组作为分配许可证的目的。 我们可以将这两个用户加入到同一个组中，并将 Intune 和远程协助的许可证应用到该组。

如果你不&#39;t 已经有权访问用户组中可以使用的两个 Azure AD 帐户;下面是有关的快速入门指南：

- [如何创建用户](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [如何创建组](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [将用户添加到组](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) –将创建的用户添加到创建组
- [配置 Azure AD 允许用户组加入设备](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) –确保新的用户组有权注册设备 Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>在 HoloLens 2 上自动注册

若要获得流畅且无缝的体验，请将 Azure Active Directory 加入 (AADJ) 和自动注册到 Intune 2 设备的 Intune，这就是一种方法。 这将允许用户在 OOBE 期间输入其组织的登录凭据，并自动注册 Azure AD 并将设备注册到 MDM。

通过使用 [Microsoft 终结点管理器](https://endpoint.microsoft.com/#home)，我们可以选择 "服务" 并导航几个页面，直到可以选择 "获取高级试用版"。 你可能会注意到 Azure Active Directory Premium 1 和2，自动注册 P1 就已足够。 我们可以选择 Intune 并选择自动注册的用户作用域，并选择之前创建的组。

有关完整的详细信息和步骤，请阅读有关 [如何启用 Intune 自动注册](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)的指南。

## <a name="application-licenses"></a>应用程序许可证

使用应用程序许可证，用户可以安装公司购买的应用，也可以从免费试用版升级到完整版本的应用。 可将应用程序许可证应用到用户、用户组或设备组。 你&#39;要求你的组织中的用户使用远程协助。 出于本指南的目的，我们将向我们在 [Azure 用户和组](hololens2-cloud-connected-configure.md#azure-users-and-groups)中创建的用户组分配远程协助许可证。

根据用户是要从设备进行远程协助调用，还是从 Microsoft 团队远程协作，就许可证的要求可能会有所不同。 默认情况下，将标记 "远程协助" 和 "团队" 复选框。 出于本指南的目的，我们建议保留默认框处于选中状态。

1. 详细了解 [每个角色的不同许可和产品要求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)。 有几种不同类型的远程协助许可证，请务必根据需要获取正确的许可证。
2. 你&#39;需要 [获取许可证](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)。
3. [将许可证应用](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 到组。

## <a name="next-step"></a>后续步骤

> [!div class="nextstepaction"]
> [云连接部署-部署](hololens2-cloud-connected-deploy.md)