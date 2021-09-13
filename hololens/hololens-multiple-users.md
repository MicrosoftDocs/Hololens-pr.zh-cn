---
title: 与多人共享你的 HoloLens
description: 可以将 HoloLens 配置为由多个 Azure Active Directory 帐户共享，也可以由使用单个帐户的多个用户共享。
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-qianwen
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/3/2021
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e3acd2665e93e44bce2c5dad467c825dc768bfed
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032159"
---
# <a name="share-your-hololens-with-multiple-people"></a>与多人共享你的 HoloLens

## <a name="overview"></a>概述
企业经常投入许多共享 HoloLens 设备。 使用 HoloLens 在整个板中是灵活的，具体取决于您的个人需求。 下面是一些多用户体验的示例： 

- 收费并具有 Dynamics 365 Guides 的设备，并允许员工打开设置应用来对所需 Wi-Fi 进行调整，但启用了 "页面设置可见性" 策略，以限制设置应用中可用的页数。
- 用于远程协助的设备，以及租赁给其他公司的业务线应用。 这些设备的网亭只包含应用和远程协助。 使用 WDAC 来保持设置应用和 Microsoft Edge 的启动。 租赁附带了一个 USB-C 电池组，使设备在多个班次上保持完全充电。
- 已为 Autopilot 设置了所有设备，并下载了公司的所有应用。 已设置了几个不同的展台配置文件，面向不同的 Azure AD 组。 每个用户都使用 FIDO2 密钥登录到 HoloLens，并登录到自己的 Azure AD 帐户，并提供定制体验。



## <a name="share-with-multiple-people-each-using-their-own-account"></a>与多个用户共享，每个人使用自己的帐户

**先决条件**： HoloLens 设备必须 Windows 10 版本1803或更高版本运行。  还需要将第一代) HoloLens ([升级到 Windows Holographic for Business](hololens-upgrade-enterprise.md)。

当他们使用自己的 Azure Active Directory (Azure AD) 帐户时，多个用户可以在设备上保留自己的用户设置和用户数据。

若要确保多个用户可以在 HoloLens 上使用自己的帐户，请按照以下步骤进行配置：

1. 请确保设备运行的是版本1803或更高版本 Windows 10。
   > [!IMPORTANT]
   > 如果使用 HoloLens (1 代) 设备，请将[该设备升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md)。
1. 设置设备时，请选择 **"我的工作" 或 "学校拥有** "，并使用 Azure AD 帐户登录。
1. 完成设置后，请确保帐户设置 (**设置**  >  **帐户**) 包括 **其他用户**。

若要使用 HoloLens，每个用户都遵循以下步骤：

1. 如果另一位用户使用了该设备，请选择下列选项之一：
   - 按下电源按钮进入待机状态，然后再次按下电源按钮，返回到锁定屏幕
   - HoloLens 2 用户可以从 "开始"菜单中选择用户磁贴来注销当前用户。

1. 使用你的 Azure AD 帐户凭据登录到设备。  
    如果是第一次使用设备，则必须将 HoloLens[校准](hololens-calibration.md)到自己的眼睛。

若要查看设备用户列表或从设备中删除用户，请访问 **设置**  >  **帐户**""  >  **其他用户**"。

## <a name="share-with-multiple-people-all-using-the-same-account"></a>使用同一个帐户与多个用户共享

使用单个用户帐户时，多个用户还可以共享 HoloLens 设备。

**在 HoloLens 2 上**，当新用户第一次将设备放在其打印头上时 (，同时使同一帐户登录) ，该设备会提示新用户快速校准并个性化查看体验。 设备可存储校准信息，以便将来能够自动优化质量并舒适了解每个用户的查看体验。 用户无需再次校准设备。

**在 HoloLens (第一代)** 共享帐户的用户需要在设置应用中请求重新校准。  阅读有关 [校准](hololens-calibration.md)的详细信息。