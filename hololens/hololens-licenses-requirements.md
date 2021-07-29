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
ms.openlocfilehash: bd7a7d03c81dced4fb66d8ebb176887811e823c9
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640266"
---
# <a name="license-requirements"></a>许可要求

## <a name="hololens-2-device-managed"></a>HoloLens 2 设备（托管）

[Azure AD 帐户](/azure/active-directory/)

> [!IMPORTANT]
> Active Directory (AD) 不能用于管理 HoloLens 设备。

[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) 或其他 MDM。
- [适用于 HoloLens 2 的 Windows Autopilot](hololens2-autopilot.md) - 简化了 IT 管理员和最终用户的预配体验。 IT 管理员可以预配 HoloLens 2 策略，并且首次启动时，设备将部署为无最终用户交互的业务就绪状态。 

  > [!NOTE]
  > Windows Autopilot 需先为低接触 Autopilot 流程和设备部署配置 [Azure P1](/azure/active-directory/fundamentals/active-directory-whatis) 和[自动注册](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)。 

### <a name="business-use-case"></a>业务用例： 

- [部署方案 A](hololens-requirements.md#scenario-a-deploy-to-cloud-connected-devices) - 概念验证或试点部署。

- [部署方案 B](hololens-requirements.md#scenario-b-deploy-inside-your-organizations-network) - 大规模部署。

## <a name="hololens-2-device-only-non-managed"></a>HoloLens 2 仅限设备（非托管）

使用 Microsoft 帐户 (MSA) 或本地帐户时，这些帐户不需要额外的许可证。

[本地帐户](/windows/security/identity-protection/access-control/local-accounts)

- 必须使用 Windows 配置设计器 (WCD) 提前[预配](hololens-provisioning.md#provisioning-package-hololens-wizard)此帐户。

[Microsoft 帐户 (MSA)](/windows/security/identity-protection/access-control/microsoft-accounts)

> [!WARNING]
> 使用这些帐户之一的设备不支持多个用户。

### <a name="business-use-case"></a>业务用例： 

- [部署方案 C](hololens-requirements.md#scenario-c-deploy-in-secure-offline-environment) - 脱机或安全部署。
 
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

- Microsoft Teams 或 [Teams 免费增值](https://products.office.com/microsoft-teams/free)。

- 网络连接

如果你计划实施此[跨租户方案](/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)，你可能需要一个信息障碍许可证。 请参阅[本文](/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)确定是否需要信息障碍许可证。

### <a name="dynamics-365-guides"></a>Dynamics 365 Guides 

#### <a name="admin"></a>管理员

- Azure AD 帐户（购买订阅和分配许可证时需要）
- Dynamics 365 [Guides 订阅或免费试用版](/dynamics365/mixed-reality/guides/setup-step-one)

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
