---
title: 与多人共享 HoloLens
description: 你可以将 HoloLens 配置为由多个 Azure Active Directory 帐户或使用单个帐户的多个用户共享。
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
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827979"
---
# 与多人共享 HoloLens

与很多人共享一个 HoloLens 或让多个用户共享一组 HoloLens 设备很常见。  本文介绍了可用于共享设备的不同方式。

## 与多人共享，每个人都使用自己的帐户

**先决条件**： HoloLens 设备必须运行 Windows 10 版本1803或更高版本。  HoloLens （第1代）也需要[升级到 Windows 全息版企业](hololens-upgrade-enterprise.md)版。

当他们使用自己的 Azure Active Directory （Azure AD）帐户时，多个用户可以在设备上保留自己的用户设置和用户数据。

若要确保多人可以在 HoloLens 上使用自己的帐户，请按照以下步骤进行配置：

1. 请确保设备运行的是 Windows 10 版本1803或更高版本。
   > [!IMPORTANT]
   > 如果您使用的是 HoloLens （第1代）设备，请将[设备升级到 Windows 全息版 For Business](hololens1-upgrade-enterprise.md)。
1. 设置设备时，请选择 **"我的工作或学校拥有它**"，然后使用 Azure AD 帐户登录。
1. 完成设置后，请确保帐户设置（**设置**  >  **帐户**）包括**其他用户**。

若要使用 HoloLens，每个用户都可以按照以下步骤操作：

1. 如果其他用户已使用该设备，请执行下列操作之一：
   - 按下 "电源" 按钮，转到 "待机"，然后再次按 "电源" 按钮以返回到锁屏界面
   - HoloLens 2 用户可以从 "开始" 菜单中选择 "用户" 磁贴来注销当前用户。

1. 使用 Azure AD 帐户凭据登录到设备。  
    如果这是你首次使用该设备，则必须将 HoloLens[校准](hololens-calibration.md)到你自己的眼睛。

若要查看设备用户列表或从设备中删除用户，请转到 " **Settings**  >  **Accounts**  >  **其他用户**的设置帐户"。

## 与多人共享，所有使用同一个帐户

多个用户也可以在使用单个用户帐户时共享 HoloLens 设备。

**在 HoloLens 2 上**，当新用户首次将设备放在其头上时（在保持相同帐户登录的同时），设备会提示新用户快速校准和个性化查看体验。 设备可以存储校准信息，以便将来的设备可以自动优化质量并舒适了解每个用户的观看体验。 用户无需再次校准设备。

**在 HoloLens （第1代）上**共享帐户的用户需要在 "设置" 应用中要求重新校准。  阅读有关[校准](hololens-calibration.md)的详细信息。
