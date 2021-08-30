---
title: 在商业环境中规划 HoloLens 2 部署
description: 了解在企业环境中部署和管理 HoloLens 的核心需求，包括基础结构、azure active directory 和移动设备管理。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 8605d1a889fb9facdab0e9585a43a61880155952
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "123188893"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>在商业环境中规划 HoloLens 2 部署

## <a name="overview"></a>概述

> [!NOTE]
> 本概述旨在帮助 IT 专业人员了解在组织中部署和管理 Microsoft HoloLens 2 设备的注意事项。 对于设备最终用户，请参阅开始[使用 HoloLens 2](hololens2-setup.md) 。

HoloLens 2 在 Windows 10 全息版上运行，后者为组织提供强大、灵活的内置移动设备和应用管理技术。 Windows 10 全息版支持端到端设备生命周期管理，使公司可以控制其设备、数据和应用。 使用全面的移动设备管理解决方案，可以轻松地将 HoloLens 2 纳入到标准生命周期实践，从设备注册、配置和应用程序管理到维护和停用。

以下步骤和视频可帮助指导你完成组织中的 HoloLens 2 采用过程。

| &nbsp; | &nbsp; |
|--|--|
| ![步骤 1。](images/1green.png)| <br/> **[常见部署方案](hololens-requirements.md)**：了解部署方案，并探索部署 HoloLens 2 设备所需的核心组件。 |
| ![步骤 2.](images/2green.png)| <br/> **[准备](#prepare)**：熟悉 HoloLens 2 所需的基础结构要点。 |
| ![步骤 3.](images/3green.png) | <br/> **[配置](#configure)**：了解如何配置基于云的部署的基本组件。 |
| ![步骤 4.](images/4green.png) | <br/> **[部署](#deploy)**：了解如何部署设备并安全高效地分发应用程序。 |
| ![步骤 5。](images/5green.png) | <br/> **[维护](#maintain)**：查找正确维护 HoloLens 2 设备的状态所需的内容，并确保符合公司策略。 |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>准备

了解支持整套 HoloLens 2 功能所需的基本基础结构服务。

| 组件 | 说明 |
|-----------|------------|
| [Azure AD](hololens-identity.md) | 提供 HoloLens 2 的标识和访问管理  |
| [移动设备管理](hololens-mdm-configure.md)| 管理连接到租户 HoloLens 2 设备  |
| [Wi-fi 网络](hololens-commercial-infrastructure.md)| Wi-Fi 可用并且设备可以连接到 Internet  |

## <a name="configure"></a>配置

使用 Intune 和 Autopilot 作为低接触解决方案，将 HoloLens 2 注册和配置到组织的 Azure AD 租户和 MDM。

| 组件 | 说明 |
|-----------|------------|
| [自动注册](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | 初次登录后，设备会自动注册到 Azure AD 并注册到 MDM  |
| [应用程序许可证](hololens2-cloud-connected-configure.md#application-licenses)| 可应用于用户、用户组或设备组  |
| [Azure 用户和组](hololens2-cloud-connected-configure.md#azure-users-and-groups) | 帮助为 HoloLens 2 分配配置和许可证  |

## <a name="deploy"></a>部署

分发 HoloLens 2 设备并验证其配置。 

| 组件 | 说明 |
|-----------|------------|
| [注册验证](hololens2-corp-connected-deploy.md#enrollment-validation) | 验证设备是否已从设置或 Azure 门户 Azure AD 联接 |
| [证书验证](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | 检查设置，并验证它们是否已正确分发 |
| [验证应用安装](hololens2-corp-connected-deploy.md#validate-lob-app-install) | 确认应用是否存在，并处理 HoloLens 2 |

## <a name="maintain"></a>维护

将 Windows 更新用于业务与 MDM 系统或 Microsoft Store，以使你的 HoloLens 2 和应用更新。

| 组件 | 说明 |
|-----------|------------|
| [更新 HoloLens 2](hololens-updates.md) | 通过 Windows 业务更新来根据需要配置更新 |
| [更新应用](app-deploy-overview.md) | 通过 MDM 系统或 Microsoft Store 进行配置
