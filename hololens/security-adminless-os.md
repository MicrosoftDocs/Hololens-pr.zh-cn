---
title: 安全无管理操作系统
description: 无管理操作系统和 hololens 安全
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: 安全, hololens, 无管理, 操作系统, 无管理操作系统, 管理操作系统, 无管理操作系统, hololens 2, hololens 2 安全,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e8a10a32d30206877eb79d53c90e59307b3990ab
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009560"
---
# 无管理操作系统

HoloLens 2 通过禁用对 Administrators 组的支持并将所有第三方 UWP 应用程序代码限制为仅作为 AppContainer 沙盒内的标准用户执行，从而最大限度地减少了特权提升的覆盖范围。 除了所有 AppContainer 都可以访问的资源之外，此代码仅授予未提升用户访问受应用程序中明确显示的功能保护的资源的权限。
这些应用程序功能仍然具有三层分类模型：
  * 常规
  * Restricted (受限的)
  * Windows

Windows 组件还可以通过系统 UWPs 利用 AppContainer 沙盒。 若要了解有关通用 Windows 平台 (UWP) 的详细信息，请参阅 [UWP 文档](https://docs.microsoft.com/windows/uwp/)。 此外，具有更大特权减少需求的 Windows 组件（例如浏览器内容页、分析程序）使用特权较少的 AppContainer (LPAC) 沙盒，该沙盒会切断对所有 AppContainer 可访问的资源集的访问。

最后，仅允许“设备所有者”执行特定设备范围的操作，例如将设备加入租户或用户管理。 此组由设备上的用户通过以下步骤之一填充：
  * 设备上的第一个用户始终被指定为所有者。 
    * 此规则的例外情况是，如果设备已加入 AAD，则执行加入的用户将成为设备所有者。 例如，如果设备是通过 Autopilot 加入 AAD 的，则此规则适用，在这种情况下，登录设备的第一个用户未加入 AAD，因此不会成为设备所有者。 若要了解有关谁将被设为加入 AAD 的设备的设备所有者的详细信息，请参阅[“分配本地管理员”文档](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin)（但请将“本地管理员”视为“设备所有者”，因为 HoloLens 上不存在管理员）。
  * 当设备上的另一个所有者从“设置 UX”将用户提升为所有者时。
  * 如果设备所有者不再可用（例如离开公司）且设备已加入 AAD，则租户管理员可以在 Azure 门户中将设备所有者更改为新用户。
Azure AD 租户的全局管理员在设备上以所有者身份隐式登录，而无需执行上述任一步骤。 

IT 管理员可以通过[隐私](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy)策略管理应用可访问的内容。 
