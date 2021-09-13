---
title: 部署指南 - 使用 HoloLens 2 大规模部署云Remote Assist - 配置
description: 了解如何设置配置，以使用 HoloLens 通过云连接的网络大规模注册设备Remote Assist。
keywords: HoloLens、管理、云连接、Remote Assist、AAD、Azure AD、MDM、移动设备管理
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032118"
---
# <a name="configure---cloud-connected-guide"></a>配置 - 云连接指南

本指南的此部分将&#39;如何为租户设置自动注册，以及如何为 Intune 和 Remote Assist。

## <a name="azure-users-and-groups"></a>Azure 用户和组

Azure 和 Intune（按该扩展）使用用户和组来帮助分配配置和许可证。 为了验证此部署流并能够从一个用户Remote Assist调用另一个用户，&#39;两个用户帐户。

我们可以创建单个用户组来分配许可证。 我们可以将两个用户加入同一组，并应用 Intune 许可证Remote Assist应用到该组。

如果尚未&#39;两个用户帐户Azure AD可以使用的用户组;下面是以下快速入门指南：

- [如何创建用户](/mem/intune/fundamentals/quickstart-create-user)
- [如何创建组](/mem/intune/fundamentals/quickstart-create-group)
- [将用户添加到组](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 添加创建的用户以创建组
- [配置Azure AD以允许](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) 用户组加入设备 – 确保新用户组有权将设备注册到Azure AD

## <a name="auto-enrollment-on-hololens-2"></a>自动注册HoloLens 2

若要获得顺畅无缝的体验，可以设置 Azure Active Directory Join (AADJ) 和自动注册到 Intune HoloLens 2 设备。 这将允许用户在 OOBE 期间输入其组织登录凭据，并自动向 Azure AD 注册设备并注册到 MDM。

通过使用[Microsoft Endpoint Manager，](https://endpoint.microsoft.com/#home)我们可以选择服务并导航几页，直到可以选择"获取高级版试用版。 你可能会注意到有一Azure Active Directory Premium 1 和 2，因为自动注册 P1 已足够。 可以选择 Intune 并选择自动注册的用户范围，然后选择之前创建的组。

有关完整详细信息和步骤，请阅读有关 [如何为 Intune 启用自动注册的指南](/mem/intune/enrollment/quickstart-setup-auto-enrollment)。

## <a name="application-licenses"></a>应用程序许可证

应用程序许可证允许用户安装公司购买的应用，或者从免费试用版升级到应用的完整版本。 应用程序许可证可应用于用户、用户组或设备组。 你&#39;需要Remote Assist许可证，以便组织中用户使用Remote Assist。 在本指南中，我们将将Remote Assist许可证分配给我们在 Azure 用户和组 中创建 [的用户组](hololens2-cloud-connected-configure.md#azure-users-and-groups)。

许可证的要求可能有所不同，具体取决于用户是从设备进行Remote Assist还是远程协作者从设备Microsoft Teams。 默认情况下，Remote Assist和Teams复选框都标记为 。 对于本指南，建议选中默认框。

1. 详细了解每个角色 [的不同许可和产品要求](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)。 有一些不同类型的Remote Assist许可证，因此请确保获得所需的正确许可证。
2. 你&#39;需要 [获取许可证](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)。
3. [将许可证](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 应用到组。

## <a name="next-step"></a>后续步骤

> [!div class="nextstepaction"]
> [云连接部署 - 部署](hololens2-cloud-connected-deploy.md)