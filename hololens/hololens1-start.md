---
title: 设置 HoloLens（第一代）
description: 了解如何使用 Microsoft (MSA) 或 Azure Active Directory (AAD) 帐户首次通过 Wi-Fi 网络设置 HoloLens（第一代）。
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
ms.openlocfilehash: aca7b287b3d26ab37ddb90e4245a1e0b3adc17e2
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283923"
---
# <span data-ttu-id="f3355-103">设置 HoloLens（第一代）</span><span class="sxs-lookup"><span data-stu-id="f3355-103">Set up your HoloLens (1st gen)</span></span>

<span data-ttu-id="f3355-104">首次打开 HoloLens 时，系统将指导你校准设备、设置设备和登录。</span><span class="sxs-lookup"><span data-stu-id="f3355-104">The first time you turn on your HoloLens, you'll be guided through calibrating your device, setting up your device, and signing in.</span></span>  <span data-ttu-id="f3355-105">本文将介绍 HoloLens（第一代）首次启动和设置体验。</span><span class="sxs-lookup"><span data-stu-id="f3355-105">This article walks through the HoloLens (1st gen) first start and setup experience.</span></span>

<span data-ttu-id="f3355-106">在下一部分中，你将了解如何使用 HoloLens 以及与全息影像互动。</span><span class="sxs-lookup"><span data-stu-id="f3355-106">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="f3355-107">要跳转到那篇文章，请参阅[HoloLens（第一代）入门](hololens1-basic-usage.md)。</span><span class="sxs-lookup"><span data-stu-id="f3355-107">To skip ahead to that article, see [Get started with HoloLens (1st gen)](hololens1-basic-usage.md).</span></span>

## <span data-ttu-id="f3355-108">准备工作</span><span class="sxs-lookup"><span data-stu-id="f3355-108">Before you start</span></span>

<span data-ttu-id="f3355-109">开始之前，必须做好以下准备：</span><span class="sxs-lookup"><span data-stu-id="f3355-109">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="f3355-110">**WLAN 连接**。</span><span class="sxs-lookup"><span data-stu-id="f3355-110">**A Wi-Fi connection**.</span></span> <span data-ttu-id="f3355-111">需要将 HoloLens 连接到 WLAN 网络才能进行设置。</span><span class="sxs-lookup"><span data-stu-id="f3355-111">You'll need to connect your HoloLens to a Wi-Fi network to set it up.</span></span> <span data-ttu-id="f3355-112">首次连接时，需要一个无需导航到网站或使用证书即可连接的开放网络或受密码保护的网络。</span><span class="sxs-lookup"><span data-stu-id="f3355-112">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="f3355-113">[详细了解 HoloLens 使用的网站](hololens-offline.md).</span><span class="sxs-lookup"><span data-stu-id="f3355-113">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="f3355-114">**Microsoft 帐户或工作帐户**。</span><span class="sxs-lookup"><span data-stu-id="f3355-114">**A Microsoft account or a work account**.</span></span> <span data-ttu-id="f3355-115">你还需要使用 Microsoft 帐户（如果你的组织配备有该设备，则使用你的工作帐户）登录 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="f3355-115">You'll also need to use a Microsoft account (or a work account, if your organization owns the device) to sign in to HoloLens.</span></span> <span data-ttu-id="f3355-116">如果你没有 Microsoft 帐户，则转至 [account.microsoft.com](https://account.microsoft.com) 免费设置一个帐户。</span><span class="sxs-lookup"><span data-stu-id="f3355-116">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="f3355-117">**安全、光线充足、无绊倒危险的空间**。</span><span class="sxs-lookup"><span data-stu-id="f3355-117">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="f3355-118">[健康和安全信息](https://go.microsoft.com/fwlink/p/?LinkId=746661)。</span><span class="sxs-lookup"><span data-stu-id="f3355-118">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="f3355-119">HoloLens 附带有**可选的舒适配件**，可帮助你获得最为舒适的体验。</span><span class="sxs-lookup"><span data-stu-id="f3355-119">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="f3355-120">[更多舒适佩戴信息](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)。</span><span class="sxs-lookup"><span data-stu-id="f3355-120">[More on fit and comfort](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="f3355-121">首次使用 HoloLens 时，[Cortana](hololens-cortana.md) 就已处于启用状态并准备为你提供指导（虽然在设置设备之前，其无法响应你的问题）。</span><span class="sxs-lookup"><span data-stu-id="f3355-121">The first time that you use your HoloLens, [Cortana](hololens-cortana.md) is already on and ready to guide you (though she won't be able to respond to your questions until after you set up your device).</span></span> <span data-ttu-id="f3355-122">你可以随时在 Cortana 设置中关闭 Cortana。</span><span class="sxs-lookup"><span data-stu-id="f3355-122">You can turn Cortana off at any time in Cortana's settings.</span></span>
> - <span data-ttu-id="f3355-123">为了切换到中文版或日语版 HoloLens，你需要在电脑上下载相应语言的内部版本，然后将其安装到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="f3355-123">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to download the build for the language on a PC and then install it on your HoloLens.</span></span> <span data-ttu-id="f3355-124">有关详细信息，请参阅[安装 HoloLens（第一代）的本地化版本](hololens1-install-localized.md)。</span><span class="sxs-lookup"><span data-stu-id="f3355-124">For more information, see [Install localized versions of HoloLens (1st gen)](hololens1-install-localized.md).</span></span>

## <span data-ttu-id="f3355-125">启动 Hololens 和设置 Windows</span><span class="sxs-lookup"><span data-stu-id="f3355-125">Start your Hololens and set up Windows</span></span>

<span data-ttu-id="f3355-126">首次启动 HoloLens 时，第一项任务是在设备上设置 Windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="f3355-126">The first time you start your HoloLens, your first task is to set up Windows Holographic on your device.</span></span>

1. <span data-ttu-id="f3355-127">连接到 Internet（HoloLens 将指导你选择 WLAN 网络）。</span><span class="sxs-lookup"><span data-stu-id="f3355-127">Connect to the internet (HoloLens guides you to select Wi-Fi network).</span></span>

1. <span data-ttu-id="f3355-128">登录到你的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f3355-128">Sign in to your user account.</span></span> <span data-ttu-id="f3355-129">在**我的工作单位或学校拥有它**与**我拥有它**之间选择。</span><span class="sxs-lookup"><span data-stu-id="f3355-129">Choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="f3355-130">选择**我的工作单位或学校拥有它**时，使用 Azure AD 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f3355-130">When you choose **My work or school owns it**, you sign in by using an Azure AD account.</span></span> <span data-ttu-id="f3355-131">如果你的组织使用 Azure AD Premium 并配置了自动 MDM 注册功能，HoloLens 将自动注册 MDM。</span><span class="sxs-lookup"><span data-stu-id="f3355-131">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="f3355-132">如果你的组织未使用 Azure AD Premium，则自动 MDM 注册功能将无法使用，你需要 [在设备管理中手动注册 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。</span><span class="sxs-lookup"><span data-stu-id="f3355-132">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available, so you will need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span> <span data-ttu-id="f3355-133">要使用工作或学校帐户首次登录设备，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f3355-133">To sign in to your device the first time by using a work or school account, follow these steps:</span></span>
        1. <span data-ttu-id="f3355-134">输入你的组织帐户信息。</span><span class="sxs-lookup"><span data-stu-id="f3355-134">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="f3355-135">接受隐私声明。</span><span class="sxs-lookup"><span data-stu-id="f3355-135">Accept the privacy statement.</span></span>
        1. <span data-ttu-id="f3355-136">使用 Azure AD 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="f3355-136">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="f3355-137">此操作可能会重定向到组织的登录页面。</span><span class="sxs-lookup"><span data-stu-id="f3355-137">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="f3355-138">继续设置设备。</span><span class="sxs-lookup"><span data-stu-id="f3355-138">Continue setting up the device.</span></span>
    - <span data-ttu-id="f3355-139">选择**我拥有它**时，使用 Microsoft 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f3355-139">When you choose **I own it**, you sign in by using a Microsoft account.</span></span> <span data-ttu-id="f3355-140">设置完成后，你可以[在设备管理中手动注册 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。</span><span class="sxs-lookup"><span data-stu-id="f3355-140">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="f3355-141">输入你的 Microsoft 帐户信息。</span><span class="sxs-lookup"><span data-stu-id="f3355-141">Enter your Microsoft account information.</span></span>
        1. <span data-ttu-id="f3355-142">输入密码。</span><span class="sxs-lookup"><span data-stu-id="f3355-142">Enter your password.</span></span> <span data-ttu-id="f3355-143">如果你的 Microsoft 帐户需要进行[双重验证 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，请完成验证过程。</span><span class="sxs-lookup"><span data-stu-id="f3355-143">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

1. <span data-ttu-id="f3355-144">设备会根据它从 WLAN 网络获取的信息设置你的时区。</span><span class="sxs-lookup"><span data-stu-id="f3355-144">The device sets your time zone based on information that it obtains from the Wi-Fi network.</span></span>

## <span data-ttu-id="f3355-145">校准</span><span class="sxs-lookup"><span data-stu-id="f3355-145">Calibration</span></span>

<span data-ttu-id="f3355-146">在 Cortana 介绍自己后，下一个设置步骤是校准。</span><span class="sxs-lookup"><span data-stu-id="f3355-146">After Cortana introduces herself, the next setup step is calibration.</span></span> <span data-ttu-id="f3355-147">为了获得最佳 HoloLens 体验，你应该在设置期间完成校准过程。</span><span class="sxs-lookup"><span data-stu-id="f3355-147">For the best HoloLens experience, you should complete the calibration process during setup.</span></span>

<span data-ttu-id="f3355-148">HoloLens（第一代）根据瞳孔（IPD 或[瞳孔间距](https://en.wikipedia.org/wiki/Interpupillary_distance)）之间的距离清晰呈现全息影像，且使之易于交互。</span><span class="sxs-lookup"><span data-stu-id="f3355-148">HoloLens (1st gen) uses the distance between your pupils (IPD or [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) to make holograms clear and easy to interact with.</span></span> <span data-ttu-id="f3355-149">如果 IPD 不正确，则全息影像可能看起来不稳定或距离有误。</span><span class="sxs-lookup"><span data-stu-id="f3355-149">If the IPD is not correct, holograms may appear to be unstable or at an incorrect distance.</span></span>

<span data-ttu-id="f3355-150">校准期间，HoloLens 会要求你将手指与每只眼睛注视的六个目标对齐。</span><span class="sxs-lookup"><span data-stu-id="f3355-150">During calibration, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="f3355-151">HoloLens 通过此过程为眼睛设置正确的 IPD。</span><span class="sxs-lookup"><span data-stu-id="f3355-151">HoloLens uses this process to set the correct IPD for your eyes.</span></span> <span data-ttu-id="f3355-152">如需为新用户更新或调整校准，则新用户可以在设置之外运行“校准”应用。</span><span class="sxs-lookup"><span data-stu-id="f3355-152">If the calibration needs to be updated or adjusted for a new user, the new user can run the Calibration app  outside of setup.</span></span>

![第二步中的 IPD 手指对齐屏幕](./images/ipd-finger-alignment-300px.jpg)

*<span data-ttu-id="f3355-154">第二步中的 IPD 手指对齐屏幕</span><span class="sxs-lookup"><span data-stu-id="f3355-154">IPD finger-alignment screen at second step</span></span>*

<span data-ttu-id="f3355-155">恭喜你！</span><span class="sxs-lookup"><span data-stu-id="f3355-155">Congratulations!</span></span> <span data-ttu-id="f3355-156">设置完成，你可以开始使用 HoloLens 了。</span><span class="sxs-lookup"><span data-stu-id="f3355-156">Setup is complete and you can begin using HoloLens.</span></span>

## <span data-ttu-id="f3355-157">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f3355-157">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f3355-158">HoloLens（第一代）入门</span><span class="sxs-lookup"><span data-stu-id="f3355-158">Get started with HoloLens (1st gen)</span></span>](hololens1-basic-usage.md)
