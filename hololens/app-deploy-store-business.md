---
title: 适用于企业的 Microsoft Store
description: 了解如何使用适用于企业的 Microsoft Store 将混合现实应用程序发布到企业。
keywords: 适用于企业的 Microsoft Store，msfb，应用部署，应用商店
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
ms.openlocfilehash: 5bc719539aaa254b8aacb05e24554152231f7e5a
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924321"
---
# <a name="microsoft-store-for-business"></a>适用于企业的 Microsoft Store

该[适用于企业的 Microsoft Store](/microsoft-store/microsoft-store-for-business-overview)主要面向企业或组织中的 IT 决策者和管理员，并具有一种灵活的方法，可用于在 "选择市场" 中查找、获取、管理和分发免费和付费应用，并将其用于 Windows 10 设备。 

你可以在一次清点中管理 Microsoft Store 应用和私有业务线应用，并根据需要分配和重复使用许可证。 你还可以为你的组织选择最佳分发方法：直接将应用分配给个人和团队，将应用发布到 Microsoft Store 中的专用页面，或连接到管理解决方案以获取更多选项。

当最终用户使用适用于企业的 Microsoft Store 时，它们将启动 Microsoft Store 应用。 启动后，用户将能够选择包含其组织名称的选项卡，然后将向用户提供可供他们或设备使用的应用。

> [!Note]
> 适用于企业的 Microsoft Store 不会自动将 (推送) 应用下载到设备。 但是，可以将适用于企业的 Microsoft Store 中的应用程序与你的设备管理 (MDM) 服务器关联，并将应用同步到设备。

请访问以下页面，了解有关如何使用适用于企业的 Microsoft Store 的详细信息：

* [用于安装应用程序的权限级别](/mem/intune/configuration/device-restrictions-windows-holographic#app-store)
* [如何将应用添加到适用于企业的应用商店](/mem/intune/apps/store-apps-windows)
* [如何将应用分配给员工组](/mem/intune/apps/windows-store-for-business)

若要关联适用于企业的 Microsoft Store，请访问[将适用于企业的 Microsoft Store 与 Intune 关联](/mem/intune/apps/windows-store-for-business#associate-your-microsoft-store-for-business-account-with-intune)。

> [!Tip]
> 若要详细了解如何在使用高级恢复 (ARC) 和 Windows 配置设计器 (WCD) 中的应用时[分发脱机应用](/microsoft-store/distribute-offline-apps)。

## <a name="use-only-private-store-apps-for-microsoft-store"></a>仅对 Microsoft Store 使用专用应用商店应用

- 在[Windows 全息版 21H2](hololens-release-notes.md#windows-holographic-version-21h2)中引入。

已为 HoloLens 启用 RequirePrivateStoreOnly 策略。 此策略允许将 Microsoft Store 应用配置为仅显示为组织配置的专用存储。 仅将访问权限限制为可用的应用。

了解有关[ApplicationManagement/RequirePrivateStoreOnly](http://windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-requireprivatestoreonly)的详细信息

## <a name="smart-retry-for-app-updates"></a>应用更新的智能重试

- 在[Windows 全息版 21H2](hololens-release-notes.md#windows-holographic-version-21h2)中引入。

现在为 HoloLens 启用了新策略，该策略允许 IT 管理员设置定期或一次性日期，以重新启动由于正在使用的应用程序允许应用更新而导致更新失败的应用。 可以基于几个不同的触发器（如计划时间或登录）来设置这些设置。 若要了解有关如何使用此策略的详细信息，请参阅 [ApplicationManagement/ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)。