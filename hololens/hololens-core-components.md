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
ms.openlocfilehash: 684059b1ab91860dc6af63cbd6f0927876fefb8c
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112961386"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a>在商业环境中规划 HoloLens 2 部署

## <a name="overview"></a>概述
> [!NOTE]
> 本概述旨在帮助 IT 专业人员了解在组织中部署和管理 Microsoft HoloLens 2 设备的注意事项。 有关设备最终用户的信息，请参阅入门 [基础知识](hololens2-setup.md) 。

HoloLens 2 在 Windows 10 全息版上运行，可为组织提供强大灵活的内置移动设备和应用管理技术。 Windows 10 全息版支持端到端设备生命周期管理，使公司可以控制其设备、数据和应用。 使用全面的移动设备管理解决方案，可以轻松地将 HoloLens 2 纳入到标准生命周期实践中，从设备注册、配置和应用程序管理到维护和停用。

以下步骤可帮助指导你完成在你的组织中使用 HoloLens 2 的过程。

| | |
|--|--|
| ![步骤 1](images/1green.png)| <br/> **[常见部署方案](hololens-requirements.md)**：了解部署方案，并探索部署 HoloLens 2 设备所需的核心组件。 |
| ![步骤 2](images/2green.png)| <br/> **[准备](#prepare)**：熟悉 HoloLens 2 所需的基础结构要点。 |
| ![步骤 3](images/3green.png) | <br/> **[配置](#configure)**：了解如何配置基于云的部署的基本组件。 |
| ![步骤 4](images/4green.png) | <br/> **[部署](#deploy)**：了解如何部署设备并安全高效地分发应用程序。 |
| ![步骤 5](images/5green.png) | <br/> **[维护](#maintain)**：查找正确维护 HoloLens 2 设备的状态所需的内容，并确保符合公司策略。 |

## <a name="prepare"></a>准备

了解支持整套 HoloLens 2 功能所需的基本基础结构服务。 

| 组件 | 说明 |
|-----------|------------|
| [Azure AD](hololens-identity.md) | 提供 HoloLens 2 的标识和访问管理  |
| [移动设备管理](hololens-mdm-configure.md)| 管理连接到租户的 HoloLens 2 设备  |
| [Wi-fi 网络](hololens-commercial-infrastructure.md)| Wi-Fi 可用并且设备可以连接到 Internet  |

## <a name="configure"></a>配置

使用 Intune 和 Autopilot 作为低接触解决方案，将 HoloLens 2 注册并配置到组织的 Azure AD 租户和 MDM。

| 组件 | 说明 |
|-----------|------------|
| [自动注册](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | 初次登录后，设备会自动注册到 Azure AD 并注册到 MDM  |
| [应用程序许可证](hololens2-cloud-connected-configure.md#application-licenses)| 可应用于用户、用户组或设备组  |
| [Azure 用户和组](hololens2-cloud-connected-configure.md#azure-users-and-groups) | 帮助为 HoloLens 2 分配配置和许可证  |

## <a name="deploy"></a>部署

分发你的 HoloLens 2 设备并验证其配置。 

| 组件 | 说明 |
|-----------|------------|
| [注册验证](hololens2-corp-connected-deploy.md#enrollment-validation) | 验证设备是否已从设置或 Azure 门户连接 Azure AD |
| [证书验证](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | 检查设置，并验证它们是否已正确分发 |
| [验证应用安装](hololens2-corp-connected-deploy.md#validate-lob-app-install) | 确认应用是否存在并在 HoloLens 2 上工作 |

## <a name="maintain"></a>维护

将 Windows 更新 for Business 与 MDM 系统或 Microsoft Store 一起使用，以将你的 HoloLens 2 和应用更新到一起。

| 组件 | 说明 |
|-----------|------------|
| [更新 HoloLens 2](hololens-updates.md) | 通过适用于企业的 Windows 更新按需配置更新 |
| [更新应用](app-deploy-overview.md) | 通过 MDM 系统或 Microsoft Store 进行配置
