---
title: '设置 HoloLens (第一代) '
description: 了解如何在 Wi-Fi 网络上首次使用 Microsoft (MSA) 或 Azure Active Directory (AAD) 帐户来设置 HoloLens (第一代) 。
ms.assetid: 0136188e-1305-43be-906e-151d70292e87
ms.prod: hololens
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.date: 8/12/2019
manager: jarrettr
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: f0ec62e55f15fda6d5a8304ea2bb77039d644b9e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308389"
---
# <a name="set-up-your-hololens-1st-gen"></a>设置 HoloLens (第一代) 

第一次打开 HoloLens 时，会指导你校准设备、设置设备并登录。  本文逐步讲解 HoloLens (第一代) 首次启动和设置体验。

在下一部分中，你将了解如何使用 HoloLens 并与全息影像交互。 若要跳转到该文章，请参阅 [HoloLens (第一代) 入门 ](hololens1-basic-usage.md)。

## <a name="before-you-start"></a>开始之前

在开始之前，请确保你具有以下各项：

**Wi-Fi 连接**。 需要将 HoloLens 连接到 Wi-Fi 网络进行设置。 首次连接时，需要一个开放的或受密码保护的网络，而不需要导航到网站或使用证书进行连接。 [详细了解 HoloLens 使用的网站](hololens-offline.md)。

**Microsoft 帐户或工作帐户**。 如果你的组织拥有设备) 登录到 HoloLens，则还需要使用 Microsoft 帐户 (或工作帐户。 如果没有 Microsoft 帐户，请跳到 [account.microsoft.com](https://account.microsoft.com) 并免费设置一个。

**安全、良好的空间，不** 会受到干扰。 [健康和安全信息](https://go.microsoft.com/fwlink/p/?LinkId=746661)。

HoloLens 随附的 **可选舒适的附件**，可帮助你获得最舒适的适应。 [更适合和舒适](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)。

> [!NOTE]
>  
> - 第一次使用 HoloLens 时， [Cortana](hololens-cortana.md) 已经打开并准备好指导您 (但在设置设备) 之前，她将无法响应您的问题。 可以在 Cortana 的设置中随时关闭 Cortana。
> - 若要切换到中文版或日语版的 HoloLens 版，需要下载计算机上的语言版本，然后将其安装在 HoloLens 上。 有关详细信息，请参阅 [安装 HoloLens (第一代) 的本地化版本 ](hololens1-install-localized.md)。

## <a name="start-your-hololens-and-set-up-windows"></a>开始安装 Hololens 并设置 Windows

首次启动 HoloLens 时，第一个任务是在设备上设置 Windows 全息版。

1. 连接到 internet (HoloLens 指导您选择 Wi-Fi 网络) 。

1. 登录到你的用户帐户。 选择 **"我的工作" 或 "学校拥有"** **并拥有它。**
    - 选择 **"我的工作" 或 "学校拥有**" 时，可以使用 Azure AD 帐户登录。 如果你的组织使用 Azure AD Premium 并且已配置自动 MDM 注册，则 HoloLens 会自动在 MDM 中注册。 如果你的组织不使用 Azure AD Premium，则无法使用自动 MDM 注册，因此你将需要 [在设备管理中手动注册 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。 若要在第一次使用工作或学校帐户登录设备，请执行以下步骤：
        1. 输入你的组织帐户信息。
        1. 接受隐私声明。
        1. 使用 Azure AD 的凭据登录。 此操作可能会重定向到组织的登录页面。
        1. 继续设置设备。
    - 选择 " **我拥有**" 时，可以使用 Microsoft 帐户登录。 安装完成后，可以在 " [设备管理" 中手动注册 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。
        1. 输入 Microsoft 帐户信息。
        1. 输入密码。 如果你的 Microsoft 帐户需要进行[双重验证 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，请完成验证过程。

1. 设备根据其从 Wi-Fi 网络获得的信息设置时区。

## <a name="calibration"></a>校准

Cortana 引入后，下一个安装步骤是校准。 为了获得最佳的 HoloLens 体验，应在安装过程中完成校准过程。

HoloLens (第一代) 使用瞳孔 (IPD 或 [interpupillary 距离](https://en.wikipedia.org/wiki/Interpupillary_distance)) 之间的距离，使影像清晰且易于交互。 如果 IPD 不正确，则可能是全息影像可能不稳定或距离不正确。

校准期间，HoloLens 要求你将手指与每个眼睛一系列六个目标对齐。 HoloLens 使用此过程为眼睛设置正确的 IPD。 如果需要更新或调整新用户的校准，则新用户可以在安装程序外运行校准应用。

![第二步的 IPD finger 对齐屏幕](./images/ipd-finger-alignment-300px.jpg)

*第二步的 IPD finger 对齐屏幕*

恭喜！ 安装程序已完成，可以开始使用 HoloLens。

## <a name="next-steps"></a>后续步骤

> [!div class="nextstepaction"]
> [HoloLens (第一代入门) ](hololens1-basic-usage.md)
