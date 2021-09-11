---
title: 许可要求
description: 了解最新的移动设备管理、HoloLens 和 Remote Assist 的所有许可要求和指南。
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens 2
ms.openlocfilehash: 6224cd5e07794d9fca3c0a406e787d1a3fd88b43
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428021"
---
# <a name="license-requirements"></a>许可要求

## <a name="overview"></a>概述
本页提供在组织中部署托管和非托管 HoloLens 2 设备所需的许可证和帐户的概述。 它还包括 Dynamics 365 [Remote Assist](#dynamics-365-remote-assist) 和 [Guides](#dynamics-365-guides) 的许可的信息。

## <a name="hololens-2-license-and-account-requirements"></a>HoloLens 2 的许可证和帐户要求

 
|       &nbsp;      | 托管的 HoloLens | 非托管的 HoloLens |
|-------------------|-----------------|---------------------|
| **业务用例** | | |
| [部署到连接到云的设备 - 概念验证/试点部署](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices)  | ✔️| |
| [在组织网络内部署 - 大规模部署](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) | ✔️| |
| [在安全的脱机环境中进行部署](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) | | ✔️ |
| **许可证** | | |
| Azure Active Directory | ✔️ | |
| MDM（Intune<sup>1</sup> 或 <sup>2</sup>） | ✔️  | |
| **帐户** |  | |
| Azure AD 管理员帐户 | ✔️ |  |
| Azure AD 用户帐户 | ✔️ | |
| [Microsoft 帐户 (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)| | ✔️ |
| [本地帐户](/windows/security/identity-protection/access-control/local-accounts)<sup>3</sup> | | ✔️ |
- <sup>1</sup>在初始设备设置期间[自动注册](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)，这会注册和联接 Azure Active Directory 并使设备能通过 Intune 进行管理。
- <sup>2</sup> [适用于 HoloLens 2 的 Windows Autopilot ](hololens2-autopilot.md) 简化了 IT 管理员和最终用户的预配体验。 IT 管理员可以预配 HoloLens 2 策略，并且首次启动时，设备将部署为无最终用户交互的业务就绪状态。
- <sup>3</sup> 必须使用 Windows 配置设计器 (WCD) 提前[预配](hololens-provisioning.md#provisioning-package-hololens-wizard)此帐户。

> [!IMPORTANT]
> Active Directory (AD) 不能用于管理 HoloLens 设备。
 
> [!WARNING]
> 使用 MSA 或本地帐户的设备不支持多个用户。

## <a name="dynamics-365-licensing-and-requirements"></a>Dynamics 365 许可和要求

### <a name="dynamics-365-remote-assist"></a>Dynamics 365 Remote Assist 

#### <a name="admin"></a>管理员

- Azure AD 帐户（购买订阅和分配许可证时需要）
- [Remote Assist 订阅](/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)（或 [Remote Assist 试用版](/dynamics365/mixed-reality/remote-assist/try-remote-assist)）
    
#### <a name="dynamics-365-remote-assist-user"></a>Dynamics 365 Remote Assist 用户

- Azure AD 帐户

- Remote Assist 许可证 

  > [!NOTE]
  > Microsoft Teams 与 Remote Assist 捆绑

- 网络连接

#### <a name="microsoft-teams-user"></a>Microsoft Teams 用户

- Azure AD 帐户

- Microsoft Teams 或 [Teams Freemium](https://products.office.com/microsoft-teams/free)

- 网络连接

如果你计划实施此[跨租户方案](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)，你可能需要一个信息障碍许可证。 请参阅[本文](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)确定是否需要信息障碍许可证。

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>管理员

1. Azure AD 帐户（购买订阅和分配许可证时需要）
2. Dynamics 365 [Guides 订阅或免费试用版](/dynamics365/mixed-reality/guides/setup-step-one)

#### <a name="guides-author"></a>Guides 作者

1. Azure AD 帐户
1. [Dynamics 365 Guides 许可证](/dynamics365/mixed-reality/guides/requirements)
1. PC 或 HoloLens 上安装的 Dynamics 365 Guides 应用程序
1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/)（用于查看分析仪表板）
1. 作者角色（用于创建指南）
1. 网络连接

#### <a name="guides-user"></a>Guides 用户

1. Azure AD 帐户
1. [Dynamics 365 Guides 许可证](/dynamics365/mixed-reality/guides/requirements)
1. HoloLens 上安装的 Dynamics 365 Guides 应用
1. 操作员角色（用于测试或使用指南）
1. 网络连接
