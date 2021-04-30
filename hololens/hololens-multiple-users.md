---
title: 与多人共享你的 HoloLens
description: 可以将 HoloLens 配置为由多个 Azure Active Directory 帐户共享，也可以配置为使用单个帐户的多个用户共享。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 39de72bb704ff500b0262f2268d003a08d520eb2
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308435"
---
# <a name="share-your-hololens-with-multiple-people"></a>与多人共享你的 HoloLens

很常见的情况是与许多人分享一项 HoloLens，或让许多人共享一组 HoloLens 设备。  本文介绍共享设备的不同方法。

## <a name="share-with-multiple-people-each-using-their-own-account"></a>与多个用户共享，每个人使用自己的帐户

**先决条件**： HoloLens 设备必须运行 Windows 10 版本1803或更高版本。  HoloLens (第一代) 还需要 [升级到 Windows 全息 For Business](hololens-upgrade-enterprise.md)。

当他们使用自己的 Azure Active Directory (Azure AD) 帐户时，多个用户可以在设备上保留自己的用户设置和用户数据。

若要确保多个用户可以在你的 HoloLens 上使用自己的帐户，请按照以下步骤进行配置：

1. 请确保设备正在运行 Windows 10 版本1803或更高版本。
   > [!IMPORTANT]
   > 如果你使用的是 HoloLens (第一代) 设备，请将 [该设备升级到 Windows 全息 For Business](hololens1-upgrade-enterprise.md)。
1. 设置设备时，请选择 **"我的工作" 或 "学校拥有** "，并使用 Azure AD 帐户登录。
1. 完成设置后，请确保 "帐户设置" (的 "**设置**  >  **帐户**") 包括 **其他用户**。

若要使用 HoloLens，每个用户都遵循以下步骤：

1. 如果另一位用户使用了该设备，请执行以下操作之一：
   - 按下电源按钮进入待机状态，然后再次按下电源按钮，返回到锁定屏幕
   - HoloLens 2 用户可以从 "开始" 菜单中选择用户磁贴来注销当前用户。

1. 使用你的 Azure AD 帐户凭据登录到设备。  
    如果这是你首次使用设备，则必须将 HoloLens [校准](hololens-calibration.md) 到你自己的眼睛。

若要查看设备用户列表或要从设备中删除用户，请参阅 "**设置**" "帐户" "  >    >  **其他用户**"。

## <a name="share-with-multiple-people-all-using-the-same-account"></a>使用同一个帐户与多个用户共享

使用单个用户帐户时，多个用户还可以共享 HoloLens 设备。

**在 HoloLens 2 上**，当新用户第一次将设备放在其磁头上时 (，同时让同一帐户登录) ，设备会提示新用户快速校准并个性化查看体验。 设备可存储校准信息，以便将来能够自动优化质量并舒适了解每个用户的查看体验。 用户无需再次校准设备。

**在 HoloLens (第一代)** 共享帐户的用户需要在 "设置" 应用中请求重新校准。  阅读有关 [校准](hololens-calibration.md)的详细信息。
