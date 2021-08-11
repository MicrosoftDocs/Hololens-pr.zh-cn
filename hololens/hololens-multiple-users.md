---
title: 与HoloLens共享你的服务
description: 你可以将HoloLens配置为由多个 Azure Active Directory 帐户共享，或者由使用单个帐户的多个用户共享。
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
ms.openlocfilehash: 821ef2d17531226177e508b1428af82012c16406e9fbce3ed1a5617c767adfe8
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663070"
---
# <a name="share-your-hololens-with-multiple-people"></a>与HoloLens共享你的服务

通常与许多人共享一HoloLens共享一组设备，或让许多人共享一组HoloLens设备。  本文介绍共享设备的不同方式。

## <a name="share-with-multiple-people-each-using-their-own-account"></a>与多个人员共享，每个人员使用其自己的帐户

**先决条件**：HoloLens设备必须Windows 10版本 1803 或更高版本。  HoloLens (第一代) 还需要[升级到 Windows Holographic for Business。](hololens-upgrade-enterprise.md)

当他们使用自己的Azure Active Directory (Azure AD) 帐户时，多个用户可以在设备上保留其自己的用户设置和用户数据。

若要确保多个用户可以使用自己的帐户HoloLens，请执行以下步骤进行配置：

1. 确保设备正在运行版本Windows 10 1803 或更高版本。
   > [!IMPORTANT]
   > 如果使用的是第一代HoloLens (，) [设备升级到 Windows Holographic for Business。](hololens1-upgrade-enterprise.md)
1. 设置设备时，选择"我 **的工作或学校** 拥有该设备"，然后使用 Azure AD登录。
1. 完成设置后，请确保"帐户" (设置帐户)   >  **包括"其他用户"。**

若要使用HoloLens，每个用户都执行以下步骤：

1. 如果其他用户一直在使用该设备，请执行下列操作之一：
   - 按电源按钮一次以进入待机状态，然后再次按电源按钮以返回到锁定屏幕
   - HoloLens 2用户可以从用户列表中选择用户磁贴"开始"菜单注销当前用户。

1. 使用Azure AD帐户凭据登录到设备。  
    如果这是第一次使用该设备，必须校准HoloLens自己的眼睛。 [](hololens-calibration.md)

若要查看设备用户列表或从设备中删除用户，请转到"设置  >    >  **用户帐户"。**

## <a name="share-with-multiple-people-all-using-the-same-account"></a>与多个人员共享，全部使用同一帐户

使用单个用户帐户时，HoloLens共享一个设备。

**在 HoloLens 2** 上，当新用户首次将设备放在其头部 (同时使同一帐户登录) 时，设备会提示新用户快速校准并个性化查看体验。 设备可以存储校准信息，以便将来设备可以自动优化每个用户的观看体验的质量和舒适感。 用户无需再次校准设备。

**在HoloLens (第** 一代) 共享帐户的用户将需要要求在 设置 应用中重新设置。  详细了解 [校准](hololens-calibration.md)。
