---
title: 设置 HoloLens 2
description: 了解如何使用 Microsoft (MSA) 或 Azure Active Directory (AAD) 帐户首次通过 Wi-Fi 网络设置 HoloLens 2。
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 9/17/2019
keywords: Hololens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 9824de1d81fd6ba9ccafc8627d660aebefeaed15
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283873"
---
# 设置 HoloLens 2

第一次打开 HoloLens 时，你需要设置设备、使用用户帐户登录以及根据眼睛校准 HoloLens。  此部分介绍 HoloLens 2 的初始设置体验。

在下一部分中，你将了解如何使用 HoloLens 以及与全息影像互动。 要跳转到那篇文章，请参阅[HoloLens 2 入门](hololens2-basic-usage.md)。

## 准备工作

开始之前，必须做好以下准备：

**网络连接**。 你需要将 HoloLens 连接到网络才能对其进行设置。 使用 HoloLens 2，你可以通过 WLAN 或以太网连接（需要 USB-C 到以太网适配器）。 首次连接时，需要一个无需导航到网站或使用证书即可连接的开放网络或受密码保护的网络。 [详细了解 HoloLens 使用的网站](hololens-offline.md).

**Microsoft 帐户**。 你还需要使用 Microsoft 帐户（如果你的组织配备有该设备，则使用你的工作帐户）登录到 HoloLens。 如果你没有 Microsoft 帐户，则转至 [account.microsoft.com](https://account.microsoft.com) 免费设置一个帐户。

**安全、光线充足、无绊倒危险的空间**。 [健康和安全信息](https://go.microsoft.com/fwlink/p/?LinkId=746661)。

HoloLens 附带有**可选的舒适配件**，可帮助你获得最为舒适的体验。 [更多舒适佩戴信息](hololens2-setup.md#adjust-fit)。

## 设置 Windows

首次启动 HoloLens 2 时，第一项任务是设置 Windows 全息版。  启动 HoloLens 时，你会听到音乐并看到 Windows 徽标。

![首次启动时的第一个屏幕](images/01-magic-moment.png)

HoloLens 2 将引导你完成以下步骤：

1. 选择你的语言。
    ![选择语言](images/04-language.png)

1. 选择你所在的区域。
    ![选择区域](images/05-region.png)

1. 根据你的瞳距校准 HoloLens。  如果选择跳过校准，则当你下次登录时系统会提示你。

    要进行校准，请注视一组目标（称为“宝石”）。 校准期间，你眨眼或闭眼都可以，但是尽量不要盯着房间或物理空间中的其他物体。 HoloLens 利用此过程来获取你的眼球位置，以便更好地向你呈现全息世界。 校准后，会正确显示全息图，即使面罩在你的头上移动时也是如此。

    校准信息本地存储在设备上，与任何帐户信息无关。 有关详细信息，请参阅[校准数据和安全](hololens-calibration.md#calibration-data-and-security)。

    ![校准选择屏幕](images/06-et-corners.png)

1. 连接到 Internet（选择 WLAN 或以太网连接）。
     HoloLens 根据从 WLAN 网络获得的信息自动设置你的时区。 设置完成后，你可以使用“设置”应用更改时区。

    ![连接到 WLAN](images/11-network.png)
> [!NOTE] 
> 如果执行了 WLAN 步骤，但后来仍需要在设置过程中切换到其他网络，则在运行 2019 年 10 月或更高版本的操作系统的情况下，可以同时按**降低音量**和**电源**按钮返回到此步骤。 对于较早版本，可能需要[重置设备](hololens-recovery.md)，或在 WLAN 网络不可用的地方重启设备，以防止其自动连接。
> 
> 另请注意，在 HoloLens 设置期间，凭据会在两分钟后超时。 需要在两分钟内输入用户名/密码，否则用户名字段将被自动清空。

1. 登录到你的用户帐户。 在**我的工作单位或学校拥有它**和**我拥有它**之间选择。
    - 当你选择**我的工作单位或学校拥有它**时，请使用 Azure AD 帐户登录。 如果你的组织使用 Azure AD Premium 并配置了自动 MDM 注册功能，HoloLens 将自动注册 MDM。 如果你的组织不使用 Azure AD Premium，则自动 MDM 注册功能不可用。 这时，你需要[在设备管理中手动注册 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。
        1. 输入你的组织帐户信息。
        1. 接受隐私声明和最终用户许可协议。
        1. 使用 Azure AD 凭据登录。 此操作可能会重定向到组织的登录页面。
        1. 继续设置设备。
    - 选择**我拥有它**时，请使用 Microsoft 帐户登录。 设置完成后，你可以[在设备管理中手动注册 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。
        1. 输入你的 Microsoft 帐户信息。
        2. 输入密码。 如果你的 Microsoft 帐户需要[两步验证 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，请完成验证过程。

    ![设置用户](images/13-device-owner.png)

1. 选择是否启用 HoloLens 2 上的语音功能，以及是否发送诊断遥测数据。
    ![启用 Cortana](images/22-do-more-with-voice.png)

1. 选择遥测级别。 可以的话，请启用完整遥测级别。 此信息能为 HoloLens 工程团队提供切实帮助。
     ![遥测级别](images/24-telemetry.png)

1. 了解如何在 HoloLens 2 上使用开始手势。
     ![了解如何使用开始手势，图像 1](images/26-01-startmenu-learning.png) ![了解如何使用开始手势，图像 2](images/26-02-startmenu-learning.png)

恭喜你！  设置已完成，你现在可以使用 HoloLens 了！

## 后续步骤

> [!div class="nextstepaction"]
> [HoloLens 2 入门](hololens2-basic-usage.md)
