---
title: 在商业环境中规划 HoloLens 2 部署
description: 了解在企业环境中部署和管理 HoloLens的核心需求，包括基础结构、Azure Active Directory 和移动设备管理。
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
ms.openlocfilehash: 8273813d85c3b2df2c1a551fb0322a867a5a9c64fdd05e9a85a2097b1590fb62
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664331"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>在商业环境中规划 HoloLens 2 部署

## <a name="overview"></a>概述

> [!NOTE]
> 本概述旨在帮助 IT 专业人员了解在组织中部署Microsoft HoloLens 2 台设备的注意事项。 对于设备最终用户，请参阅[获取HoloLens 2可供开始使用](hololens2-setup.md)。

HoloLens 2运行Windows 10 全息版为组织提供可靠、灵活、内置的移动设备以及应用管理技术。 Windows 10 全息版支持端到端设备生命周期管理，使公司能够控制其设备、数据和应用。 这些HoloLens 2可以轻松纳入标准生命周期实践，从设备注册、配置和应用程序管理，到使用全面的移动设备管理解决方案进行维护和停用。

以下步骤和视频可帮助你完成在组织中HoloLens 2采用的过程。

| &nbsp; | &nbsp; |
|--|--|
| ![步骤 1](images/1green.png)| <br/> **[常见部署方案](hololens-requirements.md)**：了解部署方案，并探索在设备上部署HoloLens 2组件。 |
| ![步骤 2](images/2green.png)| <br/> **[准备](#prepare)**：熟悉开发所需的基础结构HoloLens 2。 |
| ![步骤 3](images/3green.png) | <br/> **[配置](#configure)**：了解如何为基于云的部署配置基本组件。 |
| ![步骤 4](images/4green.png) | <br/> **[部署](#deploy)**：了解如何部署设备并安全高效地分发应用程序。 |
| ![步骤 5](images/5green.png) | <br/> **[维护](#maintain)**：了解正确维护设备状态HoloLens 2并确保符合公司策略所需的内容。 |

<br/>

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a>准备

了解支持一组完整的基础结构功能所需的HoloLens 2服务。

| 组件 | 说明 |
|-----------|------------|
| [Azure AD](hololens-identity.md) | 为用户提供标识和访问HoloLens 2  |
| [移动设备管理](hololens-mdm-configure.md)| 管理HoloLens 2租户的设备  |
| [Wi-Fi 网络](hololens-commercial-infrastructure.md)| Wi-Fi可用且设备可以连接到 Internet  |

## <a name="configure"></a>配置

使用 Intune 和 Autopilot 作为低接触解决方案，HoloLens 2组织的租户和 MDM Azure AD配置数据。

| 组件 | 说明 |
|-----------|------------|
| [自动注册](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | 初始登录后，设备会自动注册Azure AD注册到 MDM  |
| [应用程序许可证](hololens2-cloud-connected-configure.md#application-licenses)| 可应用于用户、用户组或设备组  |
| [Azure 用户和组](hololens2-cloud-connected-configure.md#azure-users-and-groups) | 帮助为应用程序分配配置和HoloLens 2  |

## <a name="deploy"></a>部署

分发HoloLens 2并验证其配置。 

| 组件 | 说明 |
|-----------|------------|
| [注册验证](hololens2-corp-connected-deploy.md#enrollment-validation) | 验证设备是否Azure AD从 设置 Azure 门户加入 |
| [证书验证](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | 检查设置并验证它们已正确分发 |
| [验证应用安装](hololens2-corp-connected-deploy.md#validate-lob-app-install) | 确认应用存在并处理HoloLens 2 |

## <a name="maintain"></a>维护

将 Windows Update for Business 与 MDM 系统或 Microsoft Store一起用于保持HoloLens 2和应用群的更新。

| 组件 | 说明 |
|-----------|------------|
| [更新HoloLens 2](hololens-updates.md) | 根据需要通过企业更新Windows配置更新 |
| [更新应用](app-deploy-overview.md) | 通过 MDM 系统或应用程序Microsoft Store
