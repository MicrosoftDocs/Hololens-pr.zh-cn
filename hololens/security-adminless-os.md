---
title: 无管理操作系统安全性
description: 了解 HoloLens 混合现实设备上无管理操作系统、设备所有者和安全性。
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全, hololens, 无管理, 操作系统, 无管理操作系统, 管理操作系统, 无管理操作系统, hololens 2, hololens 2 安全,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ed2d5134a6bc5952063f7dc5dc5d0e31db972b08
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034212"
---
# <a name="admin-less-operating-system"></a>无管理操作系统

HoloLens 2 通过禁用对 Administrators 组的支持并将所有第三方 UWP 应用程序代码限制为仅作为 AppContainer 沙盒内的标准用户执行，从而最大限度地减少了特权提升的覆盖范围。 除了所有 AppContainer 都可以访问的资源之外，此代码仅授予未提升用户访问受应用程序中明确显示的功能保护的资源的权限。
这些应用程序功能仍然具有三层分类模型：
  * 常规
  * 受限
  * Windows

Windows 组件还可以通过系统 UWP 利用 AppContainer 沙盒。 若要了解有关通用 Windows 平台 (UWP) 的更多信息，请参阅 [UWP 文档](/windows/uwp/)。 此外，具有较大权限缩减需求的 Windows 组件（如浏览器内容页或分析程序）使用较低权限的 AppContainer (LPAC) 沙盒，该沙盒能省去所有 AppContainers 可访问的资源集的访问权限。

## <a name="device-owner"></a>设备所有者

最后，仅允许“设备所有者”执行特定设备范围的操作，例如将设备加入租户或用户管理。 此组由设备上的用户通过以下步骤之一填充：
  * 设备上的第一个用户始终被指定为所有者。 
> [!IMPORTANT]
>对于 Azure AD 用户，此规则的例外情况是，如果设备通过 Autopilot 或批量 Azure AD 注册加入 Azure AD，则其使用非真实用户。 在这种情况下，第一个登录到设备的 AAD 用户不会自动成为设备所有者，除非该用户在 Azure 门户中分配了“全局管理员”或“设备管理员”角色。 有关详细信息，请参阅以下备注。  

  * 当用户被设备上的另一所有者从"设置用户体验"提升为所有者。
  * 如果设备所有者不再可用（已离开公司），并且设备是加入 Azure AD 的，则租户管理员可以在 Azure 门户中将设备所有者更改为新用户。 Azure AD 租户的全局管理员和设备管理员在设备上以所有者形式隐式登录，无需执行上述任一步骤。  

 IT 管理员可以通过[隐私](/windows/client-management/mdm/policy-csp-privacy)策略管理应用可访问的内容。 

> [!NOTE]
> 若要了解有关谁将被设为加入 Azure AD 的设备的设备所有者的详细信息，请参阅[“分配本地管理员”文档](/azure/active-directory/devices/assign-local-admin)（但请将“本地管理员”视为“设备所有者”，因为 HoloLens 上不存在管理员）。