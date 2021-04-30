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
# <a name="set-up-your-hololens-1st-gen"></a><span data-ttu-id="68b5e-103">设置 HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="68b5e-103">Set up your HoloLens (1st gen)</span></span>

<span data-ttu-id="68b5e-104">第一次打开 HoloLens 时，会指导你校准设备、设置设备并登录。</span><span class="sxs-lookup"><span data-stu-id="68b5e-104">The first time you turn on your HoloLens, you'll be guided through calibrating your device, setting up your device, and signing in.</span></span>  <span data-ttu-id="68b5e-105">本文逐步讲解 HoloLens (第一代) 首次启动和设置体验。</span><span class="sxs-lookup"><span data-stu-id="68b5e-105">This article walks through the HoloLens (1st gen) first start and setup experience.</span></span>

<span data-ttu-id="68b5e-106">在下一部分中，你将了解如何使用 HoloLens 并与全息影像交互。</span><span class="sxs-lookup"><span data-stu-id="68b5e-106">In the next section, you'll learn how to work with HoloLens and interact with holograms.</span></span> <span data-ttu-id="68b5e-107">若要跳转到该文章，请参阅 [HoloLens (第一代) 入门 ](hololens1-basic-usage.md)。</span><span class="sxs-lookup"><span data-stu-id="68b5e-107">To skip ahead to that article, see [Get started with HoloLens (1st gen)](hololens1-basic-usage.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="68b5e-108">开始之前</span><span class="sxs-lookup"><span data-stu-id="68b5e-108">Before you start</span></span>

<span data-ttu-id="68b5e-109">在开始之前，请确保你具有以下各项：</span><span class="sxs-lookup"><span data-stu-id="68b5e-109">Before you get started, make sure you have the following available:</span></span>

<span data-ttu-id="68b5e-110">**Wi-Fi 连接**。</span><span class="sxs-lookup"><span data-stu-id="68b5e-110">**A Wi-Fi connection**.</span></span> <span data-ttu-id="68b5e-111">需要将 HoloLens 连接到 Wi-Fi 网络进行设置。</span><span class="sxs-lookup"><span data-stu-id="68b5e-111">You'll need to connect your HoloLens to a Wi-Fi network to set it up.</span></span> <span data-ttu-id="68b5e-112">首次连接时，需要一个开放的或受密码保护的网络，而不需要导航到网站或使用证书进行连接。</span><span class="sxs-lookup"><span data-stu-id="68b5e-112">The first time you connect, you'll need an open or password-protected network that doesn't require navigating to a website or using certificates to connect.</span></span> <span data-ttu-id="68b5e-113">[详细了解 HoloLens 使用的网站](hololens-offline.md)。</span><span class="sxs-lookup"><span data-stu-id="68b5e-113">[Learn more about the websites that HoloLens uses](hololens-offline.md).</span></span>

<span data-ttu-id="68b5e-114">**Microsoft 帐户或工作帐户**。</span><span class="sxs-lookup"><span data-stu-id="68b5e-114">**A Microsoft account or a work account**.</span></span> <span data-ttu-id="68b5e-115">如果你的组织拥有设备) 登录到 HoloLens，则还需要使用 Microsoft 帐户 (或工作帐户。</span><span class="sxs-lookup"><span data-stu-id="68b5e-115">You'll also need to use a Microsoft account (or a work account, if your organization owns the device) to sign in to HoloLens.</span></span> <span data-ttu-id="68b5e-116">如果没有 Microsoft 帐户，请跳到 [account.microsoft.com](https://account.microsoft.com) 并免费设置一个。</span><span class="sxs-lookup"><span data-stu-id="68b5e-116">If you don't have a Microsoft account, go to [account.microsoft.com](https://account.microsoft.com) and set one up for free.</span></span>

<span data-ttu-id="68b5e-117">**安全、良好的空间，不** 会受到干扰。</span><span class="sxs-lookup"><span data-stu-id="68b5e-117">**A safe, well-lit space with no tripping hazards**.</span></span> <span data-ttu-id="68b5e-118">[健康和安全信息](https://go.microsoft.com/fwlink/p/?LinkId=746661)。</span><span class="sxs-lookup"><span data-stu-id="68b5e-118">[Health and safety info](https://go.microsoft.com/fwlink/p/?LinkId=746661).</span></span>

<span data-ttu-id="68b5e-119">HoloLens 随附的 **可选舒适的附件**，可帮助你获得最舒适的适应。</span><span class="sxs-lookup"><span data-stu-id="68b5e-119">**The optional comfort accessories** that came with your HoloLens, to help you get the most comfortable fit.</span></span> <span data-ttu-id="68b5e-120">[更适合和舒适](https://support.microsoft.com/help/12632/hololens-fit-your-hololens)。</span><span class="sxs-lookup"><span data-stu-id="68b5e-120">[More on fit and comfort](https://support.microsoft.com/help/12632/hololens-fit-your-hololens).</span></span>

> [!NOTE]
>  
> - <span data-ttu-id="68b5e-121">第一次使用 HoloLens 时， [Cortana](hololens-cortana.md) 已经打开并准备好指导您 (但在设置设备) 之前，她将无法响应您的问题。</span><span class="sxs-lookup"><span data-stu-id="68b5e-121">The first time that you use your HoloLens, [Cortana](hololens-cortana.md) is already on and ready to guide you (though she won't be able to respond to your questions until after you set up your device).</span></span> <span data-ttu-id="68b5e-122">可以在 Cortana 的设置中随时关闭 Cortana。</span><span class="sxs-lookup"><span data-stu-id="68b5e-122">You can turn Cortana off at any time in Cortana's settings.</span></span>
> - <span data-ttu-id="68b5e-123">若要切换到中文版或日语版的 HoloLens 版，需要下载计算机上的语言版本，然后将其安装在 HoloLens 上。</span><span class="sxs-lookup"><span data-stu-id="68b5e-123">In order to switch to the Chinese or Japanese version of HoloLens, you’ll need to download the build for the language on a PC and then install it on your HoloLens.</span></span> <span data-ttu-id="68b5e-124">有关详细信息，请参阅 [安装 HoloLens (第一代) 的本地化版本 ](hololens1-install-localized.md)。</span><span class="sxs-lookup"><span data-stu-id="68b5e-124">For more information, see [Install localized versions of HoloLens (1st gen)](hololens1-install-localized.md).</span></span>

## <a name="start-your-hololens-and-set-up-windows"></a><span data-ttu-id="68b5e-125">开始安装 Hololens 并设置 Windows</span><span class="sxs-lookup"><span data-stu-id="68b5e-125">Start your Hololens and set up Windows</span></span>

<span data-ttu-id="68b5e-126">首次启动 HoloLens 时，第一个任务是在设备上设置 Windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="68b5e-126">The first time you start your HoloLens, your first task is to set up Windows Holographic on your device.</span></span>

1. <span data-ttu-id="68b5e-127">连接到 internet (HoloLens 指导您选择 Wi-Fi 网络) 。</span><span class="sxs-lookup"><span data-stu-id="68b5e-127">Connect to the internet (HoloLens guides you to select Wi-Fi network).</span></span>

1. <span data-ttu-id="68b5e-128">登录到你的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="68b5e-128">Sign in to your user account.</span></span> <span data-ttu-id="68b5e-129">选择 **"我的工作" 或 "学校拥有"** **并拥有它。**</span><span class="sxs-lookup"><span data-stu-id="68b5e-129">Choose between **My work or school owns it** and **I own it**.</span></span>
    - <span data-ttu-id="68b5e-130">选择 **"我的工作" 或 "学校拥有**" 时，可以使用 Azure AD 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="68b5e-130">When you choose **My work or school owns it**, you sign in by using an Azure AD account.</span></span> <span data-ttu-id="68b5e-131">如果你的组织使用 Azure AD Premium 并且已配置自动 MDM 注册，则 HoloLens 会自动在 MDM 中注册。</span><span class="sxs-lookup"><span data-stu-id="68b5e-131">If your organization uses Azure AD Premium and has configured automatic MDM enrollment, HoloLens automatically enrolls in MDM.</span></span> <span data-ttu-id="68b5e-132">如果你的组织不使用 Azure AD Premium，则无法使用自动 MDM 注册，因此你将需要 [在设备管理中手动注册 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。</span><span class="sxs-lookup"><span data-stu-id="68b5e-132">If your organization does not use Azure AD Premium, automatic MDM enrollment isn't available, so you will need to [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span> <span data-ttu-id="68b5e-133">若要在第一次使用工作或学校帐户登录设备，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="68b5e-133">To sign in to your device the first time by using a work or school account, follow these steps:</span></span>
        1. <span data-ttu-id="68b5e-134">输入你的组织帐户信息。</span><span class="sxs-lookup"><span data-stu-id="68b5e-134">Enter your organizational account information.</span></span>
        1. <span data-ttu-id="68b5e-135">接受隐私声明。</span><span class="sxs-lookup"><span data-stu-id="68b5e-135">Accept the privacy statement.</span></span>
        1. <span data-ttu-id="68b5e-136">使用 Azure AD 的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="68b5e-136">Sign in by using your Azure AD credentials.</span></span> <span data-ttu-id="68b5e-137">此操作可能会重定向到组织的登录页面。</span><span class="sxs-lookup"><span data-stu-id="68b5e-137">This may redirect to your organization's sign-in page.</span></span>
        1. <span data-ttu-id="68b5e-138">继续设置设备。</span><span class="sxs-lookup"><span data-stu-id="68b5e-138">Continue setting up the device.</span></span>
    - <span data-ttu-id="68b5e-139">选择 " **我拥有**" 时，可以使用 Microsoft 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="68b5e-139">When you choose **I own it**, you sign in by using a Microsoft account.</span></span> <span data-ttu-id="68b5e-140">安装完成后，可以在 " [设备管理" 中手动注册 HoloLens](hololens-enroll-mdm.md#different-ways-to-enroll)。</span><span class="sxs-lookup"><span data-stu-id="68b5e-140">After setup is complete, you can [manually enroll HoloLens in device management](hololens-enroll-mdm.md#different-ways-to-enroll).</span></span>
        1. <span data-ttu-id="68b5e-141">输入 Microsoft 帐户信息。</span><span class="sxs-lookup"><span data-stu-id="68b5e-141">Enter your Microsoft account information.</span></span>
        1. <span data-ttu-id="68b5e-142">输入密码。</span><span class="sxs-lookup"><span data-stu-id="68b5e-142">Enter your password.</span></span> <span data-ttu-id="68b5e-143">如果你的 Microsoft 帐户需要进行[双重验证 (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/)，请完成验证过程。</span><span class="sxs-lookup"><span data-stu-id="68b5e-143">If your Microsoft account requires [two-step verification (2FA)](https://blogs.technet.microsoft.com/microsoft_blog/2013/04/17/microsoft-account-gets-more-secure/), complete the verification process.</span></span>

1. <span data-ttu-id="68b5e-144">设备根据其从 Wi-Fi 网络获得的信息设置时区。</span><span class="sxs-lookup"><span data-stu-id="68b5e-144">The device sets your time zone based on information that it obtains from the Wi-Fi network.</span></span>

## <a name="calibration"></a><span data-ttu-id="68b5e-145">校准</span><span class="sxs-lookup"><span data-stu-id="68b5e-145">Calibration</span></span>

<span data-ttu-id="68b5e-146">Cortana 引入后，下一个安装步骤是校准。</span><span class="sxs-lookup"><span data-stu-id="68b5e-146">After Cortana introduces herself, the next setup step is calibration.</span></span> <span data-ttu-id="68b5e-147">为了获得最佳的 HoloLens 体验，应在安装过程中完成校准过程。</span><span class="sxs-lookup"><span data-stu-id="68b5e-147">For the best HoloLens experience, you should complete the calibration process during setup.</span></span>

<span data-ttu-id="68b5e-148">HoloLens (第一代) 使用瞳孔 (IPD 或 [interpupillary 距离](https://en.wikipedia.org/wiki/Interpupillary_distance)) 之间的距离，使影像清晰且易于交互。</span><span class="sxs-lookup"><span data-stu-id="68b5e-148">HoloLens (1st gen) uses the distance between your pupils (IPD or [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance)) to make holograms clear and easy to interact with.</span></span> <span data-ttu-id="68b5e-149">如果 IPD 不正确，则可能是全息影像可能不稳定或距离不正确。</span><span class="sxs-lookup"><span data-stu-id="68b5e-149">If the IPD is not correct, holograms may appear to be unstable or at an incorrect distance.</span></span>

<span data-ttu-id="68b5e-150">校准期间，HoloLens 要求你将手指与每个眼睛一系列六个目标对齐。</span><span class="sxs-lookup"><span data-stu-id="68b5e-150">During calibration, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="68b5e-151">HoloLens 使用此过程为眼睛设置正确的 IPD。</span><span class="sxs-lookup"><span data-stu-id="68b5e-151">HoloLens uses this process to set the correct IPD for your eyes.</span></span> <span data-ttu-id="68b5e-152">如果需要更新或调整新用户的校准，则新用户可以在安装程序外运行校准应用。</span><span class="sxs-lookup"><span data-stu-id="68b5e-152">If the calibration needs to be updated or adjusted for a new user, the new user can run the Calibration app  outside of setup.</span></span>

![第二步的 IPD finger 对齐屏幕](./images/ipd-finger-alignment-300px.jpg)

<span data-ttu-id="68b5e-154">*第二步的 IPD finger 对齐屏幕*</span><span class="sxs-lookup"><span data-stu-id="68b5e-154">*IPD finger-alignment screen at second step*</span></span>

<span data-ttu-id="68b5e-155">恭喜！</span><span class="sxs-lookup"><span data-stu-id="68b5e-155">Congratulations!</span></span> <span data-ttu-id="68b5e-156">安装程序已完成，可以开始使用 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="68b5e-156">Setup is complete and you can begin using HoloLens.</span></span>

## <a name="next-steps"></a><span data-ttu-id="68b5e-157">后续步骤</span><span class="sxs-lookup"><span data-stu-id="68b5e-157">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="68b5e-158">HoloLens (第一代入门) </span><span class="sxs-lookup"><span data-stu-id="68b5e-158">Get started with HoloLens (1st gen)</span></span>](hololens1-basic-usage.md)
