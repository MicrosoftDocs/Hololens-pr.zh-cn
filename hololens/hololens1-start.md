---
title: 设置 HoloLens（第一代）
description: 本指南将指导你完成首次设置。  你需要 WLAN 网络和 Microsoft (MSA) 或 Azure Active Directory (Azure AD) 帐户。
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 9a20a2ddd52c08a2b44dad452aac07ad9e69de85
ms.sourcegitcommit: 7edbb99e0972d3d857e5e87c062c3c64cacc1f41
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2020
ms.locfileid: "10903228"
---
# 设置 HoloLens（第一代）

首次打开 HoloLens 时，系统将指导你校准设备、设置设备和登录。  本文将介绍 HoloLens（第一代）首次启动和设置体验。

在下一部分中，你将了解如何使用 HoloLens 以及与全息影像互动。 要跳转到那篇文章，请参阅[HoloLens（第一代）入门](hololens1-basic-usage.md)。

## 开始之前

开始之前，必须做好以下准备：

**WLAN 连接**。 需要将 HoloLens 连接到 WLAN 网络才能进行设置。 首次连接时，需要一个无需导航到网站或使用证书即可连接的开放网络或受密码保护的网络。 [详细了解 HoloLens 使用的网站](hololens-offline.md).

**Microsoft 帐户或工作帐户**。 你还需要使用 Microsoft 帐户（如果你的组织配备有该设备，则使用你的工作帐户）登录 HoloLens。 如果你没有 Microsoft 帐户，则转至 [account.microsoft.com](https://account.microsoft.com) 免费设置一个帐户。

**安全、光线充足、无绊倒危险的空间**。 [健康和安全信息](https://go.microsoft.com/fwlink/p/?LinkId=746661)。

HoloLens 附带有**可选的舒适配件**，可帮助你获得最为舒适的体验。 [更多舒适佩戴信息](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)。

> [!NOTE]
>  
> - 首次使用 HoloLens 时，[Cortana](hololens-cortana.md) 就已处于启用状态并准备为你提供指导（虽然在设置设备之前，其无法响应你的问题）。 你可以随时在 Cortana 设置中关闭 Cortana。
> - 为了切换到中文版或日语版 HoloLens，你需要在电脑上下载相应语言的内部版本，然后将其安装到 HoloLens。 有关详细信息，请参阅[安装 HoloLens（第一代）的本地化版本](hololens1-install-localized.md)。

## 启动 Hololens 和设置 Windows

首次启动 HoloLens 时，第一项任务是在设备上设置 Windows 全息版。

1. 连接到 Internet（HoloLens 将指导你选择 WLAN 网络）。

1. 登录到你的用户帐户。 在**我的工作单位或学校拥有它**与**我拥有它**之间选择。
    - 选择**我的工作单位或学校拥有它**时，使用 Azure AD 帐户登录。 如果你的组织使用 Azure AD Premium 并配置了自动 MDM 注册功能，HoloLens 将自动注册 MDM。 如果你的组织未使用 Azure AD Premium，则自动 MDM 注册功能将无法使用，你需要 [在设备管理中手动注册 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。 要使用工作或学校帐户首次登录设备，请按照下列步骤操作：
        1. 输入你的组织帐户信息。
        1. 接受隐私声明。
        1. 使用 Azure AD 凭据登录。 此操作可能会重定向到组织的登录页面。
        1. 继续设置设备。
    - 选择**我拥有它**时，使用 Microsoft 帐户登录。 设置完成后，你可以[在设备管理中手动注册 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。
        1. 输入你的 Microsoft 帐户信息。
        1. 输入密码。 如果你的 Microsoft 帐户需要进行[双重验证 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，请完成验证过程。

1. 设备会根据它从 WLAN 网络获取的信息设置你的时区。

## 校准

在 Cortana 介绍自己后，下一个设置步骤是校准。 为了获得最佳 HoloLens 体验，你应该在设置期间完成校准过程。

HoloLens（第一代）根据瞳孔（IPD 或[瞳孔间距](https://en.wikipedia.org/wiki/Interpupillary_distance)）之间的距离清晰呈现全息影像，且使之易于交互。 如果 IPD 不正确，则全息影像可能看起来不稳定或距离有误。

校准期间，HoloLens 会要求你将手指与每只眼睛注视的六个目标对齐。 HoloLens 通过此过程为眼睛设置正确的 IPD。 如需为新用户更新或调整校准，则新用户可以在设置之外运行“校准”应用。

![第二步中的 IPD 手指对齐屏幕](./images/ipd-finger-alignment-300px.jpg)

*第二步中的 IPD 手指对齐屏幕*

祝贺你！ 设置完成，你可以开始使用 HoloLens 了。

## 后续步骤

> [!div class="nextstepaction"]
> [HoloLens（第一代）入门](hololens1-basic-usage.md)
