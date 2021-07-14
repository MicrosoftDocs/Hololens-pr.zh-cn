---
title: 设置 HoloLens 2
description: 了解如何使用 Microsoft (MSA) 或 Azure Active Directory (AAD) 帐户首次通过 Wi-Fi 网络设置 HoloLens 2。
ms.assetid: 507305f4-e85a-47c5-a055-a3400ae8a10e
ms.date: 6/09/2021
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 0d087037e94bcaed2cd79d9cff77ed3039919a09
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923679"
---
# <a name="set-up-your-hololens-2"></a>设置 HoloLens 2

第一次打开 HoloLens 时，你需要设置设备、使用用户帐户登录以及根据眼部校准 HoloLens。  此部分介绍 HoloLens 2 的初始设置体验。

在下一部分中，你将了解如何使用 HoloLens 以及与全息影像互动。 若要跳到这篇文章，请参阅[了解 HoloLens 2](hololens2-basic-usage.md)。

## <a name="before-you-start"></a>准备工作

开始之前，必须做好以下准备：

网络连接。 你需要将 HoloLens 连接到网络才能对其进行设置。 使用 HoloLens 2，你可以通过 Wi-Fi 或以太网连接（需要 USB-C 到以太网适配器）。 首次连接时，需要一个无需导航到网站或使用证书即可连接的开放网络或受密码保护的网络。 [详细了解 HoloLens 使用的网站](hololens-offline.md)。

Microsoft 帐户。 你还需要使用 Microsoft 帐户（如果你的组织配备有该设备，则使用你的工作帐户）登录到 HoloLens。 如果没有服务，请转到 [account.microsoft.com](https://account.microsoft.com) 免费设置一个。

一个安全、照明良好的空间，没有绊倒危险。 [运行状况和安全信息](https://go.microsoft.com/fwlink/p/?LinkId=746661)。

HoloLens 附带的可选舒适附件，可帮助你获得最舒适的贴合度。 [详细了解贴合度和舒适性](hololens2-setup.md#adjust-fit)。

## <a name="set-up-windows"></a>设置 Windows

首次启动 HoloLens 2 时，第一项任务是设置 Windows 全息版。  启动 HoloLens 时，你会听到音乐并看到 Windows 徽标。

![首次启动时的第一个屏幕](images/01-magic-moment.png)

HoloLens 2 将引导你完成以下步骤：

1. 选择语言。

    ![选择语言](images/04-language.png)

1. 选择你的区域。

    ![选择区域](images/05-region.png)

1. 根据你的眼睛校准 HoloLens。  如果选择跳过校准，下次登录时将提示你。 

    1. 首先，调整面罩。
    
        ![校准选择屏幕](images/06-et-corners.png)

    2. 要进行校准，请注视一组目标（称为“宝石”）。 校准期间，眨眼或闭眼都可以，但是尽量不要盯着房间或物理空间中的其他物体。 HoloLens 利用此过程来获取你的眼球位置，以便更好地向你呈现全息世界。 

        ![根据眼睛进行调整](images/07-adjust-eyes.png)

        校准后，会正确显示全息图，即使面罩在你的头上移动时也是如此。 校准信息存储在本地设备上，与任何帐户信息无关。 有关详细信息，请参阅[校准数据和安全性](hololens-calibration.md#calibration-data-and-security)。

        ![校准完成](images/calibration-complete.png)

1. 连接到 Internet（选择 Wi-Fi 或以太网连接）。

     HoloLens 根据从 Wi-Fi 网络获得的信息自动设置你的时区。 设置完成后，你可以使用“设置”应用更改时区。

    ![连接到 Wi-Fi](images/11-network.png)

    > [!NOTE] 
    > 如果执行了 Wi-Fi 步骤，但后来仍需要在设置过程中切换到其他网络，则在运行 2019 年 10 月或更高版本的操作系统的情况下，可以同时按“关闭音量”和“电源”按钮返回到此步骤。 对于较早版本，可能需要[重置设备](hololens-recovery.md)，或在 Wi-Fi 网络不可用的地方重启设备，以防止其自动连接。
    > 
    > 另请注意，在 HoloLens 设置期间，凭据会在两分钟后超时。 需要在两分钟内输入用户名/密码，否则用户名字段将被自动清空。

1. HoloLens 2 将搜索并应用 Autopilot 配置文件（如果存在）。 此屏幕上无需任何操作。
 
    ![Autopilot 配置文件搜索](images/autopilot-profile-search.png) 

1. 在许可屏幕上单击“接受”。

    ![Windows 许可协议](images/windows-license-agreement.png)

1. 登录到你的用户帐户。 你将在“我的工作或学校拥有它”和“我拥有它”之间作出选择。

    - 选择 **我的工作单位或学校拥有它** 时，使用 Azure AD 帐户登录。 如果你的组织使用 Azure AD Premium 并配置了自动 MDM 注册功能，HoloLens 将自动注册 MDM。 如果你的组织不使用 Azure AD Premium，则自动 MDM 注册功能不可用。 在这种情况下，需要[在设备管理中手动注册 HoloLens。](hololens-enroll-mdm.md#different-ways-to-enroll)

        1. 输入你的组织帐户信息。
        1. 接受隐私声明和最终用户许可协议。
        1. 使用 Azure AD 凭据登录。 此操作可能会重定向到组织的登录页面。
        1. 继续设置设备。

    - 选择 **我拥有它** 时，使用 Microsoft 帐户登录。 完成设置后，你可以[手动在设备管理中注册 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。

        1. 输入你的 Microsoft 帐户信息。
        2. 输入密码。 如果你的 Microsoft 帐户需要进行[双重验证 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，请完成验证过程。

    ![设置用户](images/13-device-owner.png)

1. 选择“下一步”设置虹膜登录。 你将经历与眼部校准类似的体验。 扫描完成后，选择“完成”。 还可以选择“跳过”以跳过此步骤。
    
    ![虹膜设置](images/setup-iris.png)![虹膜设置完成](images/iris-setup-complete.png) 
     
  
1. 你将设置一个 PIN 以登录到设备。 此 PIN 特定于设备。 

    ![设置 Windows Hello](images/setup-windows-hello.png)

    ![设置 Windows Hello PIN](images/windows-hello-pin.png)

    ![Windows Hello 设置成功](images/windows-hello-successful.png) 
    
1. 选择是否在 HoloLens 2 上启用语音。

    ![启用 Cortana](images/22-do-more-with-voice.png)

1. 选择是否在 HoloLens 2 上启用位置。
    
    ![启用本地服务](images/setup-location-services.png)

1. 选择遥测级别。 如果可以，请启用可选遥测。 此信息能为 HoloLens 工程团队提供切实帮助。

     ![遥测级别](images/24-telemetry.png)

1. 了解如何在 HoloLens 2 上使用开始手势。

     ![了解如何使用开始手势，图像 1](images/26-01-startmenu-learning.png)

     ![了解如何使用开始手势，图像 2](images/26-02-startmenu-learning.png)

恭喜！  设置完成，现在可以使用 HoloLens 了！

## <a name="next-steps"></a>后续步骤

1. 立即开始与混合现实交互，并在 HoloLens 上导航 Windows 10 - 查看“使用技巧”应用，以获取手势交互的实际教程。 使用开始手势转到“开始”或说出“转到开始”，然后选择“使用技巧”。

1. 单击下方以继续阅读关于开始使用 HoloLens 2 的内容。

> [!div class="nextstepaction"]
> [HoloLens 2 入门](hololens2-basic-usage.md)
