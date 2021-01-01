---
title: 部署指南 – 使用远程协助大规模部署云连接的 HoloLens 2 - 配置
description: 如何设置配置以通过云连接网络注册 HoloLens 设备
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
ms.openlocfilehash: 042a29fe436b21ca37a2fcd7921fc53d6a9686d5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253039"
---
# 配置 - 云连接指南

在本指南的这一部分中，&#39;将介绍如何为租户设置自动注册以及如何为 Intune 和 Remote Assist 应用许可证。

## Azure 用户和组

Azure 和 Intune 通过该扩展使用用户和组来帮助分配配置和许可证。 为了验证此部署流并能够从一个用户向另一个用户进行远程协助呼叫，&#39;两个用户帐户。

我们可以创建一个用户组来分配许可证。 我们可以将两个用户加入同一个组，然后向该组应用 Intune 和 Remote Assist 的许可证。

如果尚未&#39;用户组中的两个 Azure AD 帐户，可以使用;下面是以下快速入门指南：

- [如何创建用户](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [如何创建组](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- [向组添加用户](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 添加已创建用户以创建组
- [配置 Azure AD 以允许](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) 用户组加入设备 – 确保新用户组具有将设备注册到 Azure AD 的权限

## HoloLens 2 上的自动注册

若要获得流畅而无缝的体验，可以设置 Azure Active Directory Join (AADJ) 和自动注册到适用于 HoloLens 2 设备的 Intune。 这将允许用户在 OOBE 期间输入其组织登录凭据，并自动向 Azure AD 注册设备并注册到 MDM 中。

通过使用 [Microsoft Endpoint Manager，](https://endpoint.microsoft.com/#home)我们可以选择服务并导航几个页面，直到选择"获取高级试用版"。 你可能会注意到有 Azure Active Directory Premium 1 和 2，对于自动注册 P1 就足够了。 我们可以选择 Intune 并选择用户范围进行自动注册，然后选择之前创建的组。

有关完整的详细信息和步骤，请阅读有关如何 [为 Intune 启用自动注册的指南](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)。

## 应用程序许可证

应用程序许可证允许用户安装公司购买的应用，或从免费试用版升级到应用的完整版本。 应用程序许可证可应用于用户、用户组或设备组。 你需要&#39;远程协助许可证，组织的用户可以使用远程协助。 出于本指南的目的，我们将为上面在 Azure 用户和组中创建的用户组分配远程协助 [许可证](hololens2-cloud-connected-configure.md#azure-users-and-groups)。

许可证要求可能有所不同，具体取决于用户是从设备进行远程协助呼叫还是来自 Microsoft Teams 的远程协作者。 默认情况下，远程协助和 Teams 复选框都标记为。 出于本指南的目的，我们建议将默认框保留为选中状态。

1. 详细了解每个角色 [的不同许可和产品要求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)。 There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.
2. 你&#39;需要 [获取许可证](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)。
3. [将许可证应用于](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 组。

## 下一步

> [!div class="nextstepaction"]
> [云连接部署 - 部署](hololens2-cloud-connected-deploy.md)