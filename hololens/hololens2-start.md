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
ms.openlocfilehash: 31c2c9ed7b2a35c759a0e1d86b89a2f0ab75d965
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385611"
---
# <a name="set-up-your-hololens-2"></a><span data-ttu-id="47e0c-104">设置 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="47e0c-104">Set up your HoloLens 2</span></span>

<span data-ttu-id="47e0c-105">第一次打开 HoloLens 时，你需要设置设备、使用用户帐户登录以及根据眼睛校准 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="47e0c-105">The first time you turn on your HoloLens, you'll be guided through setting up your device, signing in with a user account, and calibrating the HoloLens to your eyes.</span></span>  <span data-ttu-id="47e0c-106">此部分介绍 HoloLens 2 的初始设置体验。</span><span class="sxs-lookup"><span data-stu-id="47e0c-106">This section walks through the HoloLens 2 initial setup experience.</span></span>

<span data-ttu-id="47e0c-107">在下一部分中，你将了解如何使用 HoloLens 以及与全息影像互动。</span><span class="sxs-lookup"><span data-stu-id="47e0c-107">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="47e0c-108">要跳转到那篇文章，请参阅[HoloLens 2 入门](hololens2-basic-usage.md)。</span><span class="sxs-lookup"><span data-stu-id="47e0c-108">To skip ahead to that article, see [Get started with HoloLens 2](hololens2-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="47e0c-109">准备工作</span><span class="sxs-lookup"><span data-stu-id="47e0c-109">Before you start</span></span>

<span data-ttu-id="47e0c-110">开始之前，必须做好以下准备：</span><span class="sxs-lookup"><span data-stu-id="47e0c-110">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="47e0c-111">**网络连接**。</span><span class="sxs-lookup"><span data-stu-id="47e0c-111">**A network connection**.</span></span> <span data-ttu-id="47e0c-112">你需要将 HoloLens 连接到网络才能对其进行设置。</span><span class="sxs-lookup"><span data-stu-id="47e0c-112">You'll need to connect your HoloLens to a network to set it up.</span></span> <span data-ttu-id="47e0c-113">使用 HoloLens 2，你可以通过 WLAN 或以太网连接（需要 USB-C 到以太网适配器）。</span><span class="sxs-lookup"><span data-stu-id="47e0c-113">With HoloLens 2, you can connect with Wi-Fi or by using ethernet (you'll need a USB-C-to-Ethernet adapter).</span></span> <span data-ttu-id="47e0c-114">首次连接时，需要一个无需导航到网站或使用证书即可连接的开放网络或受密码保护的网络。</span><span class="sxs-lookup"><span data-stu-id="47e0c-114">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="47e0c-115">[详细了解 HoloLens 使用的网站](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="47e0c-115">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="47e0c-116">**Microsoft 帐户**。</span><span class="sxs-lookup"><span data-stu-id="47e0c-116">**A Microsoft account**.</span></span> <span data-ttu-id="47e0c-117">你还需要使用 Microsoft 帐户（如果你的组织配备有该设备，则使用你的工作帐户）登录到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="47e0c-117">You'll also need to sign in to HoloLens with a Microsoft account (or with your work account, if your organization owns the device).</span></span> <span data-ttu-id="47e0c-118">如果你没有 Microsoft 帐户，则转至 [account.microsoft.com](https://account.microsoft.com) 免费设置一个帐户。</span><span class="sxs-lookup"><span data-stu-id="47e0c-118">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="47e0c-119">**安全、光线充足、无绊倒危险的空间**。</span><span class="sxs-lookup"><span data-stu-id="47e0c-119">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="47e0c-120">[健康和安全信息](https://go.microsoft.com/fwlink/p/?LinkId=746661)。</span><span class="sxs-lookup"><span data-stu-id="47e0c-120">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="47e0c-121">HoloLens 附带有**可选的舒适配件**，可帮助你获得最为舒适的体验。</span><span class="sxs-lookup"><span data-stu-id="47e0c-121">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="47e0c-122">[更多舒适佩戴信息](hololens2-setup.md#adjust-fit)。</span><span class="sxs-lookup"><span data-stu-id="47e0c-122">[More on fit and comfort](hololens2-setup.md#adjust-fit).</span></span>

## <a name="set-up-windows"></a><span data-ttu-id="47e0c-123">设置 Windows</span><span class="sxs-lookup"><span data-stu-id="47e0c-123">Set up Windows</span></span>

<span data-ttu-id="47e0c-124">首次启动 HoloLens 2 时，第一项任务是设置 Windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="47e0c-124">The first time you start your HoloLens 2, your first task is to set up Windows Holographic.</span></span>  <span data-ttu-id="47e0c-125">启动 HoloLens 时，你会听到音乐并看到 Windows 徽标。</span><span class="sxs-lookup"><span data-stu-id="47e0c-125">When you start your HoloLens, you will hear music and see a Windows logo.</span></span>

![首次启动时的第一个屏幕](images/01-magic-moment.png)

<span data-ttu-id="47e0c-127">HoloLens 2 将引导你完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="47e0c-127">HoloLens 2 will walk you through the following steps:</span></span>

1. <span data-ttu-id="47e0c-128">选择你的语言。</span><span class="sxs-lookup"><span data-stu-id="47e0c-128">Select your language.</span></span>
    ![选择语言](images/04-language.png)

1. <span data-ttu-id="47e0c-130">选择你所在的区域。</span><span class="sxs-lookup"><span data-stu-id="47e0c-130">Select your region.</span></span>
    ![选择区域](images/05-region.png)

1. <span data-ttu-id="47e0c-132">根据你的瞳距校准 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="47e0c-132">Calibrate HoloLens to your eyes.</span></span>  <span data-ttu-id="47e0c-133">如果选择跳过校准，则当你下次登录时系统会提示你。</span><span class="sxs-lookup"><span data-stu-id="47e0c-133">If you choose to skip calibration, you'll be prompted the next time you log in.</span></span>

    <span data-ttu-id="47e0c-134">要进行校准，请注视一组目标（称为“宝石”）。</span><span class="sxs-lookup"><span data-stu-id="47e0c-134">To calibrate, you'll look at a set of targets (referred to as gems).</span></span> <span data-ttu-id="47e0c-135">校准期间，你眨眼或闭眼都可以，但是尽量不要盯着房间或物理空间中的其他物体。</span><span class="sxs-lookup"><span data-stu-id="47e0c-135">It's fine if you blink or close your eyes during calibration, but try not to stare at other objects in the room or physical space.</span></span> <span data-ttu-id="47e0c-136">HoloLens 利用此过程来获取你的眼球位置，以便更好地向你呈现全息世界。</span><span class="sxs-lookup"><span data-stu-id="47e0c-136">HoloLens uses this process to learn about your eye position so that it can better render your holographic world.</span></span> <span data-ttu-id="47e0c-137">校准后，会正确显示全息图，即使面罩在你的头上移动时也是如此。</span><span class="sxs-lookup"><span data-stu-id="47e0c-137">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

    <span data-ttu-id="47e0c-138">校准信息本地存储在设备上，与任何帐户信息无关。</span><span class="sxs-lookup"><span data-stu-id="47e0c-138">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="47e0c-139">有关详细信息，请参阅[校准数据和安全](hololens-calibration.md#calibration-data-and-security)。</span><span class="sxs-lookup"><span data-stu-id="47e0c-139">For more information, see [Calibration data and security](hololens-calibration.md#calibration-data-and-security).</span></span>

    ![校准选择屏幕](images/06-et-corners.png)

1. <span data-ttu-id="47e0c-141">连接到 Internet（选择 WLAN 或以太网连接）。</span><span class="sxs-lookup"><span data-stu-id="47e0c-141">Connect to the internet (select Wi-Fi or your ethernet connection).</span></span>
     <span data-ttu-id="47e0c-142">HoloLens 根据从 WLAN 网络获得的信息自动设置你的时区。</span><span class="sxs-lookup"><span data-stu-id="47e0c-142">HoloLens sets your time zone automatically based on information obtained from the Wi-Fi network.</span></span> <span data-ttu-id="47e0c-143">设置完成后，你可以使用“设置”应用更改时区。</span><span class="sxs-lookup"><span data-stu-id="47e0c-143">After setup finishes, you can change the time zone by using the Settings app.</span></span>

    ![连接到 WLAN](images/11-network.png)
> [!NOTE] 
> <span data-ttu-id="47e0c-145">如果执行了 WLAN 步骤，但后来仍需要在设置过程中切换到其他网络，则在运行 2019 年 10 月或更高版本的操作系统的情况下，可以同时按**降低音量**和**电源**按钮返回到此步骤。</span><span class="sxs-lookup"><span data-stu-id="47e0c-145">If you progress past the Wi-Fi step and later need to switch to a different network while still in setup, you can press the **Volume Down** and **Power** buttons simultaneously to return to this step if you are running an OS version from October 2019 or later.</span></span> <span data-ttu-id="47e0c-146">对于较早版本，可能需要[重置设备](hololens-recovery.md)，或在 WLAN 网络不可用的地方重启设备，以防止其自动连接。</span><span class="sxs-lookup"><span data-stu-id="47e0c-146">For earlier versions, you may need to [reset the device](hololens-recovery.md) or restart it in a location where the Wi-Fi network is not available to prevent it from automatically connecting.</span></span>
> 
> <span data-ttu-id="47e0c-147">另请注意，在 HoloLens 设置期间，凭据会在两分钟后超时。</span><span class="sxs-lookup"><span data-stu-id="47e0c-147">Also note that during HoloLens Setup, there is a credential timeout of two minutes.</span></span> <span data-ttu-id="47e0c-148">需要在两分钟内输入用户名/密码，否则用户名字段将被自动清空。</span><span class="sxs-lookup"><span data-stu-id="47e0c-148">The username/password needs to be entered within two minutes otherwise the username field will be automatically cleared.</span></span>

1. <span data-ttu-id="47e0c-149">登录到你的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="47e0c-149">Sign in to your user account.</span></span> <span data-ttu-id="47e0c-150">在**我的工作单位或学校拥有它**和**我拥有它**之间选择。</span><span class="sxs-lookup"><span data-stu-id="47e0c-150">You'll choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="47e0c-151">当你选择**我的工作单位或学校拥有它**时，请使用 Azure AD 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="47e0c-151">When you choose **My work or school owns it**, you sign in with an Azure AD account.</span></span> <span data-ttu-id="47e0c-152">如果你的组织使用 Azure AD Premium 并配置了自动 MDM 注册功能，HoloLens 将自动注册 MDM。</span><span class="sxs-lookup"><span data-stu-id="47e0c-152">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="47e0c-153">如果你的组织不使用 Azure AD Premium，则自动 MDM 注册功能不可用。</span><span class="sxs-lookup"><span data-stu-id="47e0c-153">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available.</span></span> <span data-ttu-id="47e0c-154">这时，你需要[在设备管理中手动注册 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。</span><span class="sxs-lookup"><span data-stu-id="47e0c-154">In that case, you need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="47e0c-155">输入你的组织帐户信息。</span><span class="sxs-lookup"><span data-stu-id="47e0c-155">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="47e0c-156">接受隐私声明和最终用户许可协议。</span><span class="sxs-lookup"><span data-stu-id="47e0c-156">Accept the privacy statement and the end user license agreement.</span></span>
        1. <span data-ttu-id="47e0c-157">使用 Azure AD 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="47e0c-157">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="47e0c-158">此操作可能会重定向到组织的登录页面。</span><span class="sxs-lookup"><span data-stu-id="47e0c-158">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="47e0c-159">继续设置设备。</span><span class="sxs-lookup"><span data-stu-id="47e0c-159">Continue setting up the device.</span></span>
    - <span data-ttu-id="47e0c-160">选择**我拥有它**时，请使用 Microsoft 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="47e0c-160">When you choose **I own it**, you sign in with a Microsoft account.</span></span> <span data-ttu-id="47e0c-161">设置完成后，你可以[在设备管理中手动注册 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。</span><span class="sxs-lookup"><span data-stu-id="47e0c-161">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="47e0c-162">输入你的 Microsoft 帐户信息。</span><span class="sxs-lookup"><span data-stu-id="47e0c-162">Enter your Microsoft account information.</span></span>
        2. <span data-ttu-id="47e0c-163">输入密码。</span><span class="sxs-lookup"><span data-stu-id="47e0c-163">Enter your password.</span></span> <span data-ttu-id="47e0c-164">如果你的 Microsoft 帐户需要[两步验证 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，请完成验证过程。</span><span class="sxs-lookup"><span data-stu-id="47e0c-164">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

    ![设置用户](images/13-device-owner.png)

1. <span data-ttu-id="47e0c-166">选择是否启用 HoloLens 2 上的语音功能，以及是否发送诊断遥测数据。</span><span class="sxs-lookup"><span data-stu-id="47e0c-166">Select whether to enable speech on HoloLens 2, and whether to send diagnostic telemetry.</span></span>
    ![启用 Cortana](images/22-do-more-with-voice.png)

1. <span data-ttu-id="47e0c-168">选择遥测级别。</span><span class="sxs-lookup"><span data-stu-id="47e0c-168">Select your telemetry level.</span></span> <span data-ttu-id="47e0c-169">可以的话，请启用完整遥测级别。</span><span class="sxs-lookup"><span data-stu-id="47e0c-169">If you can, please enable Full telemetry.</span></span> <span data-ttu-id="47e0c-170">此信息能为 HoloLens 工程团队提供切实帮助。</span><span class="sxs-lookup"><span data-stu-id="47e0c-170">This information really helps the HoloLens engineering team.</span></span>
     ![遥测级别](images/24-telemetry.png)

1. <span data-ttu-id="47e0c-172">了解如何在 HoloLens 2 上使用开始手势。</span><span class="sxs-lookup"><span data-stu-id="47e0c-172">Learn how to use the start gesture on HoloLens 2.</span></span>
     ![了解如何使用开始手势，图像 1](images/26-01-startmenu-learning.png) ![了解如何使用开始手势，图像 2](images/26-02-startmenu-learning.png)

<span data-ttu-id="47e0c-174">恭喜你！</span><span class="sxs-lookup"><span data-stu-id="47e0c-174">Congratulations!</span></span>  <span data-ttu-id="47e0c-175">设置已完成，你现在可以使用 HoloLens 了！</span><span class="sxs-lookup"><span data-stu-id="47e0c-175">Setup is complete and you're ready to use HoloLens!</span></span>

## <a name="next-steps"></a><span data-ttu-id="47e0c-176">后续步骤</span><span class="sxs-lookup"><span data-stu-id="47e0c-176">Next steps</span></span>

1. <span data-ttu-id="47e0c-177">立即开始与混合事实交互，并在 HoloLens 上导航 Windows 10 - 查看 **Tips** 应用，以获取手势交互的实际教程。</span><span class="sxs-lookup"><span data-stu-id="47e0c-177">Start interacting right away with with Mixed Reality and navigating Windows 10 on your HoloLens - check out the **Tips** app for hands-on tutorials for hand interactions.</span></span> <span data-ttu-id="47e0c-178">使用开始手势转到“开始”或说出“转到开始”，然后选择“使用技巧”。</span><span class="sxs-lookup"><span data-stu-id="47e0c-178">Use the start gesture to go to Start or say "Go to Start" and select Tips.</span></span> 
1. <span data-ttu-id="47e0c-179">单击下方以继续阅读关于开始使用 HoloLens 2 的内容。</span><span class="sxs-lookup"><span data-stu-id="47e0c-179">Click below to continue reading about getting around HoloLens 2.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="47e0c-180">HoloLens 2 入门</span><span class="sxs-lookup"><span data-stu-id="47e0c-180">Get started with HoloLens 2</span></span>](hololens2-basic-usage.md)
