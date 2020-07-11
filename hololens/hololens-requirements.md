---
title: 在商业环境中设置 HoloLens
description: 了解有关在企业环境中部署和管理 HoloLens 的详细信息。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.openlocfilehash: e53e6575ef688e01ce2d1f6124f3214b18b05c95
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865561"
---
# <span data-ttu-id="0f715-103">在商业环境中部署 HoloLens</span><span class="sxs-lookup"><span data-stu-id="0f715-103">Deploy HoloLens in a commercial environment</span></span>

<span data-ttu-id="0f715-104">你可以在商业设置中按比例部署和配置 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="0f715-104">You can deploy and configure HoloLens at scale in a commercial setting.</span></span> <span data-ttu-id="0f715-105">本文提供了有关在商业环境中部署 HoloLens 设备的说明。</span><span class="sxs-lookup"><span data-stu-id="0f715-105">This article provides instructions for deploying HoloLens devices in a commercial environment.</span></span> <span data-ttu-id="0f715-106">本指南假设您对 HoloLens 基本熟悉。</span><span class="sxs-lookup"><span data-stu-id="0f715-106">This guide assumes basic familiarity with HoloLens.</span></span> <span data-ttu-id="0f715-107">请按照[入门指南](hololens1-setup.md)首次设置 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="0f715-107">Follow the [get started guide](hololens1-setup.md) to set up HoloLens for the first time.</span></span>

<span data-ttu-id="0f715-108">本文档还假设 HoloLens 已被安全团队评估为安全团队在企业网络上使用。</span><span class="sxs-lookup"><span data-stu-id="0f715-108">This document also assumes that the HoloLens has been evaluated by security teams as safe to use on the corporate network.</span></span>  
> [!Tip]
> <span data-ttu-id="0f715-109">了解有关[HoloLens 安全性](security-overview.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0f715-109">Learn more about [HoloLens security](security-overview.md).</span></span>
> <span data-ttu-id="0f715-110">对于 HoloLens (第一代) 安全请查看[此常见问题解答](hololens1-faq-security.md)。</span><span class="sxs-lookup"><span data-stu-id="0f715-110">For HoloLens (1st Gen) security please review [this FAQ](hololens1-faq-security.md).</span></span>

## <span data-ttu-id="0f715-111">部署步骤概述</span><span class="sxs-lookup"><span data-stu-id="0f715-111">Overview of Deployment Steps</span></span>

1. [<span data-ttu-id="0f715-112">确定所需功能</span><span class="sxs-lookup"><span data-stu-id="0f715-112">Determine what features you need</span></span>](hololens-requirements.md#step-1-determine-what-you-need)
1. [<span data-ttu-id="0f715-113">确定所需的许可证</span><span class="sxs-lookup"><span data-stu-id="0f715-113">Determine what licenses you need</span></span>](hololens-licenses-requirements.md)
1. <span data-ttu-id="0f715-114">[为 HoloLens 配置你的网络](hololens-commercial-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="0f715-114">[Configure your network for HoloLens](hololens-commercial-infrastructure.md).</span></span>
    1. <span data-ttu-id="0f715-115">本部分包括需要在防火墙上允许的带宽要求、URL 和端口;Azure AD 指南;移动设备管理 (MDM) 指南;应用部署/管理指南;和证书指南。</span><span class="sxs-lookup"><span data-stu-id="0f715-115">This section includes bandwidth requirements, URL, and ports that need to be allowed on your firewall; Azure AD guidance; Mobile Device Management (MDM) Guidance; app deployment/management guidance; and certificate guidance.</span></span>
1. <span data-ttu-id="0f715-116"> (可选) [使用预配包配置 HoloLens](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="0f715-116">(Optional) [Configure HoloLens using a provisioning package](hololens-provisioning.md)</span></span>
1. [<span data-ttu-id="0f715-117">注册设备</span><span class="sxs-lookup"><span data-stu-id="0f715-117">Enroll Device</span></span>](hololens-enroll-mdm.md)
1. [<span data-ttu-id="0f715-118">为 HoloLens 设置基于圈的更新</span><span class="sxs-lookup"><span data-stu-id="0f715-118">Set up ring based updates for HoloLens</span></span>](hololens-updates.md)
1. [<span data-ttu-id="0f715-119">启用适用于 HoloLens 的 Bitlocker 设备加密</span><span class="sxs-lookup"><span data-stu-id="0f715-119">Enable Bitlocker device encryption for HoloLens</span></span>](security-encryption-data-protection.md)

## <span data-ttu-id="0f715-120">步骤 1：</span><span class="sxs-lookup"><span data-stu-id="0f715-120">Step 1.</span></span> <span data-ttu-id="0f715-121">确定所需内容</span><span class="sxs-lookup"><span data-stu-id="0f715-121">Determine what you need</span></span>

<span data-ttu-id="0f715-122">在你的环境中部署 HoloLens 之前，首先确定需要哪些功能、应用和标识类型非常重要。</span><span class="sxs-lookup"><span data-stu-id="0f715-122">Before deploying the HoloLens in your environment, it is important to first determine what features, apps, and type of identities are needed.</span></span> <span data-ttu-id="0f715-123">确保安全团队在公司网络上使用 HoloLens 的批准也非常重要。</span><span class="sxs-lookup"><span data-stu-id="0f715-123">It is also important to ensure that your security team has approved of the use of the HoloLens on the company's network.</span></span> <span data-ttu-id="0f715-124">有关其他安全信息，请参阅[HoloLens2 security](security-overview.md) 。</span><span class="sxs-lookup"><span data-stu-id="0f715-124">Please see [HoloLens2 security](security-overview.md) for additional security information.</span></span>

### <span data-ttu-id="0f715-125">标识的类型</span><span class="sxs-lookup"><span data-stu-id="0f715-125">Type of Identity</span></span>

<span data-ttu-id="0f715-126">确定将用于登录设备的标识类型。</span><span class="sxs-lookup"><span data-stu-id="0f715-126">Determine the type of identity that will be used to sign into the device.</span></span>

1. <span data-ttu-id="0f715-127">**本地帐户：** 此帐户在 windows 电脑上的本地管理员帐户 () 。</span><span class="sxs-lookup"><span data-stu-id="0f715-127">**Local Accounts:** This account is local to the device (like a local admin account on a windows PC).</span></span> <span data-ttu-id="0f715-128">这将仅允许1个用户登录到设备。</span><span class="sxs-lookup"><span data-stu-id="0f715-128">This will allow only 1 user to log into the device.</span></span>
2. <span data-ttu-id="0f715-129">**MSA：** 这是个人帐户 (如 outlook、hotmail、gmail、yahoo 等，) 这将仅允许1个用户登录到设备。</span><span class="sxs-lookup"><span data-stu-id="0f715-129">**MSA:** This is a personal account (like outlook, hotmail, gmail, yahoo, etc.) This will allow only 1 user to log into the device.</span></span>
3. <span data-ttu-id="0f715-130">Azure **Active Directory (AZURE AD) 帐户：** 这是在 Azure AD 中创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="0f715-130">**Azure Active Directory (Azure AD) accounts:** This is an account created in Azure AD.</span></span> <span data-ttu-id="0f715-131">这会授予您的公司管理 HoloLens 设备的能力。</span><span class="sxs-lookup"><span data-stu-id="0f715-131">This grants your corporation the ability to manage the HoloLens device.</span></span> <span data-ttu-id="0f715-132">这将允许多个用户登录到 HoloLens 第一代商业版套件/HoloLens 2 设备。</span><span class="sxs-lookup"><span data-stu-id="0f715-132">This will allow multiple users to log into the HoloLens 1st Gen Commercial Suite/the HoloLens 2 device.</span></span>

<span data-ttu-id="0f715-133">有关标识类型的详细信息，请访问我们的[HoloLens 标识](hololens-identity.md)文章。</span><span class="sxs-lookup"><span data-stu-id="0f715-133">For more detailed information about identity types, please visit our [HoloLens Identity](hololens-identity.md) article.</span></span>

### <span data-ttu-id="0f715-134">功能类型</span><span class="sxs-lookup"><span data-stu-id="0f715-134">Type of Features</span></span>

<span data-ttu-id="0f715-135">您的功能要求将确定所需的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="0f715-135">Your feature requirements will determine which HoloLens you need.</span></span> <span data-ttu-id="0f715-136">我们在客户环境中经常部署的一个常用功能是 Kiosk 模式。</span><span class="sxs-lookup"><span data-stu-id="0f715-136">One popular feature that we see deployed in customer environments frequently is Kiosk Mode.</span></span> <span data-ttu-id="0f715-137">可在[此处](hololens-commercial-features.md)找到 hololens 密钥功能的列表以及支持它们的 hololens 版本。</span><span class="sxs-lookup"><span data-stu-id="0f715-137">A list of HoloLens key features, and the editions of HoloLens that support them, can be found [here](hololens-commercial-features.md).</span></span>

**<span data-ttu-id="0f715-138">什么是 Kiosk 模式？</span><span class="sxs-lookup"><span data-stu-id="0f715-138">What is Kiosk Mode?</span></span>**

<span data-ttu-id="0f715-139">展台模式是一种限制用户有权访问的应用的方式。</span><span class="sxs-lookup"><span data-stu-id="0f715-139">Kiosk mode is a way to restrict the apps that a user has access to.</span></span> <span data-ttu-id="0f715-140">这意味着仅允许用户访问某些应用程序。</span><span class="sxs-lookup"><span data-stu-id="0f715-140">This means that users will only be allowed to access certain apps.</span></span>

**<span data-ttu-id="0f715-141">我需要什么 Kiosk 模式？</span><span class="sxs-lookup"><span data-stu-id="0f715-141">What Kiosk Mode do I require?</span></span>**

<span data-ttu-id="0f715-142">展台模式有两种类型：单个应用和多应用。</span><span class="sxs-lookup"><span data-stu-id="0f715-142">There are two types of Kiosk Modes: Single app and multi-app.</span></span> <span data-ttu-id="0f715-143">单应用展台模式允许用户仅访问一个应用，而多应用展台模式允许用户访问多个指定的应用。</span><span class="sxs-lookup"><span data-stu-id="0f715-143">Single app kiosk mode allows user to only access one app while multi-app kiosk mode allows users to access multiple, specified apps.</span></span> <span data-ttu-id="0f715-144">要确定哪种展台模式适合您的公司，需要回答以下两个问题：</span><span class="sxs-lookup"><span data-stu-id="0f715-144">To determine which kiosk mode is right for your corporation, the following two questions need to be answered:</span></span>

1. **<span data-ttu-id="0f715-145">不同用户是否需要不同的体验/限制？</span><span class="sxs-lookup"><span data-stu-id="0f715-145">Do different users require different experiences/restrictions?</span></span>** <span data-ttu-id="0f715-146">请考虑以下示例：用户 A 是一种仅需要访问远程协助的现场服务工程师。</span><span class="sxs-lookup"><span data-stu-id="0f715-146">Consider the following example: User A is a field service engineer who only needs access to Remote Assist.</span></span> <span data-ttu-id="0f715-147">用户 B 是仅需要访问指南的 trainee。</span><span class="sxs-lookup"><span data-stu-id="0f715-147">User B is a trainee who only needs access to Guides.</span></span>
    1. <span data-ttu-id="0f715-148">如果是，您将需要以下各项：</span><span class="sxs-lookup"><span data-stu-id="0f715-148">If yes, you will require the following:</span></span>
        1. <span data-ttu-id="0f715-149">Azure AD 帐户作为登录设备的方法。</span><span class="sxs-lookup"><span data-stu-id="0f715-149">Azure AD Accounts as the method of signing into the device.</span></span>
        1. <span data-ttu-id="0f715-150">**多应用**展台模式。</span><span class="sxs-lookup"><span data-stu-id="0f715-150">**Multi-app** kiosk mode.</span></span>
    1. <span data-ttu-id="0f715-151">如果不是，请继续提问二</span><span class="sxs-lookup"><span data-stu-id="0f715-151">If no, continue to question two</span></span>
1. **<span data-ttu-id="0f715-152">是否需要多个应用体验？</span><span class="sxs-lookup"><span data-stu-id="0f715-152">Do you require a multi-app experience?</span></span>**
    1. <span data-ttu-id="0f715-153">如果是，则需要**多路应用**展台模式</span><span class="sxs-lookup"><span data-stu-id="0f715-153">If yes, **Multi-app** kiosk is mode is needed</span></span>
    1. <span data-ttu-id="0f715-154">如果问题1和2的答案都不是，则可以使用**单应用**展台模式</span><span class="sxs-lookup"><span data-stu-id="0f715-154">If your answer to question 1 and 2 are both no, **single-app** kiosk mode can be used</span></span>

**<span data-ttu-id="0f715-155">如何配置展台模式：</span><span class="sxs-lookup"><span data-stu-id="0f715-155">How to Configure Kiosk Mode:</span></span>**

<span data-ttu-id="0f715-156">有两种主要方法 ([预配程序包](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)和[MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) 为 HoloLens 部署展台模式。</span><span class="sxs-lookup"><span data-stu-id="0f715-156">There are two main ways ([provisioning packages](hololens-kiosk.md#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) and [MDM](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)) to deploy kiosk mode for HoloLens.</span></span> <span data-ttu-id="0f715-157">这些选项稍后将在文档中进行讨论;但是，你可以使用上面的链接跳转到此文档中的各个部分。</span><span class="sxs-lookup"><span data-stu-id="0f715-157">These options will be discussed later in the document; however, you can use the links above to jump to the respective sections in this doc.</span></span>

### <span data-ttu-id="0f715-158">应用和应用特定方案</span><span class="sxs-lookup"><span data-stu-id="0f715-158">Apps and App Specific Scenarios</span></span>

<span data-ttu-id="0f715-159">本文档中的大部分步骤也将应用于以下应用：</span><span class="sxs-lookup"><span data-stu-id="0f715-159">The majority of the steps found in this document will also apply to the following apps:</span></span>

| <span data-ttu-id="0f715-160">应用</span><span class="sxs-lookup"><span data-stu-id="0f715-160">App</span></span> | <span data-ttu-id="0f715-161">特定于应用的方案</span><span class="sxs-lookup"><span data-stu-id="0f715-161">App Specific Scenarios</span></span> |
| --- | --- |
| <span data-ttu-id="0f715-162">远程协助</span><span class="sxs-lookup"><span data-stu-id="0f715-162">Remote Assist</span></span> | [<span data-ttu-id="0f715-163">跨租户通信</span><span class="sxs-lookup"><span data-stu-id="0f715-163">Cross Tenant Communication</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview)|
| <span data-ttu-id="0f715-164">指南</span><span class="sxs-lookup"><span data-stu-id="0f715-164">Guides</span></span>  | *<span data-ttu-id="0f715-165">即将推出</span><span class="sxs-lookup"><span data-stu-id="0f715-165">Coming Soon</span></span>* |
|<span data-ttu-id="0f715-166">自定义应用</span><span class="sxs-lookup"><span data-stu-id="0f715-166">Custom Apps</span></span> | *<span data-ttu-id="0f715-167">即将推出</span><span class="sxs-lookup"><span data-stu-id="0f715-167">Coming Soon</span></span>* |

### <span data-ttu-id="0f715-168">确定注册方法</span><span class="sxs-lookup"><span data-stu-id="0f715-168">Determine your enrollment method</span></span>

1. <span data-ttu-id="0f715-169">使用预配包中的安全令牌进行批量注册。</span><span class="sxs-lookup"><span data-stu-id="0f715-169">Bulk enrollment with a security token in a provisioning package.</span></span>  
  <span data-ttu-id="0f715-170">专业人员：这是最自动化的方法 </span><span class="sxs-lookup"><span data-stu-id="0f715-170">Pros: this is the most automated approach</span></span>\
  <span data-ttu-id="0f715-171">缺点：获取初始服务器端设置</span><span class="sxs-lookup"><span data-stu-id="0f715-171">Cons: takes initial server-side setup</span></span>  
1. <span data-ttu-id="0f715-172">自动注册用户登录。</span><span class="sxs-lookup"><span data-stu-id="0f715-172">Auto-enroll on user sign in.</span></span>  
  <span data-ttu-id="0f715-173">专业人士：最简单的方法</span><span class="sxs-lookup"><span data-stu-id="0f715-173">Pros: easiest approach</span></span>  
  <span data-ttu-id="0f715-174">缺点：在应用预配包后，用户将需要完成设置</span><span class="sxs-lookup"><span data-stu-id="0f715-174">Cons: users will need to complete set up after the provisioning package has been applied</span></span>
1. <span data-ttu-id="0f715-175">_不推荐_-手动注册安装后。</span><span class="sxs-lookup"><span data-stu-id="0f715-175">_not recommended_ - Manually enroll post-setup.</span></span>  
  <span data-ttu-id="0f715-176">专业人员：设置完成后可能注册</span><span class="sxs-lookup"><span data-stu-id="0f715-176">Pros: possible to enroll after set up</span></span>  
  <span data-ttu-id="0f715-177">缺点：在手动注册之前，大多数手动方法和设备不能集中管理。</span><span class="sxs-lookup"><span data-stu-id="0f715-177">Cons: most manual approach and devices aren't centrally manageable until they're manually enrolled.</span></span>

  <span data-ttu-id="0f715-178">可[在此处](hololens-enroll-mdm.md)找到详细信息</span><span class="sxs-lookup"><span data-stu-id="0f715-178">More information can be found [here](hololens-enroll-mdm.md)</span></span>

### <span data-ttu-id="0f715-179">确定是否需要创建预配包</span><span class="sxs-lookup"><span data-stu-id="0f715-179">Determine if you need to create a provisioning package</span></span>

<span data-ttu-id="0f715-180">可使用两种方法配置 HoloLens 设备 (预配软件包和 MDMs) 。</span><span class="sxs-lookup"><span data-stu-id="0f715-180">There are two methods to configure a HoloLens device (Provisioning packages and MDMs).</span></span> <span data-ttu-id="0f715-181">建议使用 MDM 配置 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="0f715-181">We suggest using your MDM to configure you HoloLens device.</span></span> <span data-ttu-id="0f715-182">但是，在某些情况下，使用预配包是更好的选择：</span><span class="sxs-lookup"><span data-stu-id="0f715-182">However, there are some scenarios where using a provisioning package is the better choice:</span></span>

1. <span data-ttu-id="0f715-183">你希望配置 HoloLens 以跳过 Box 体验 (OOBE) </span><span class="sxs-lookup"><span data-stu-id="0f715-183">You want to configure the HoloLens to skip the Out of Box Experience (OOBE)</span></span>
1. <span data-ttu-id="0f715-184">在复杂网络中部署证书时遇到问题。</span><span class="sxs-lookup"><span data-stu-id="0f715-184">You are having trouble deploying certificate in a complex network.</span></span> <span data-ttu-id="0f715-185">即使在复杂的环境) 中，也可以使用 MDM (部署证书。</span><span class="sxs-lookup"><span data-stu-id="0f715-185">The majority of the time you can deploy certificates using MDM (even in complex environments).</span></span> <span data-ttu-id="0f715-186">但是，某些方案需要通过预配包来部署证书。</span><span class="sxs-lookup"><span data-stu-id="0f715-186">However, some scenarios require certificates to be deployed through the provisioning package.</span></span>

<span data-ttu-id="0f715-187">以下是可在预配包中应用的部分 HoloLens 配置：</span><span class="sxs-lookup"><span data-stu-id="0f715-187">Some of the HoloLens configurations you can apply in a provisioning package:</span></span>

- <span data-ttu-id="0f715-188">将证书应用到设备</span><span class="sxs-lookup"><span data-stu-id="0f715-188">Apply certificates to the device</span></span>
- <span data-ttu-id="0f715-189">设置 Wi-Fi 连接</span><span class="sxs-lookup"><span data-stu-id="0f715-189">Set up a Wi-Fi connection</span></span>
- <span data-ttu-id="0f715-190">预配置现成的设置，例如语言和区域设置</span><span class="sxs-lookup"><span data-stu-id="0f715-190">Pre-configure out of box questions like language and locale</span></span>
- <span data-ttu-id="0f715-191">(HoloLens 2) 在移动设备管理中批量注册</span><span class="sxs-lookup"><span data-stu-id="0f715-191">(HoloLens 2) bulk enroll in mobile device management</span></span>
- <span data-ttu-id="0f715-192">(HoloLens v1) 应用密钥以启用 Windows Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="0f715-192">(HoloLens v1) Apply key to enable Windows Holographic for Business</span></span>

<span data-ttu-id="0f715-193">如果您决定使用预配程序包，请按照[本指南](hololens-provisioning.md)操作。</span><span class="sxs-lookup"><span data-stu-id="0f715-193">If you decide to use provisioning packages, follow [this guide](hololens-provisioning.md).</span></span>

## <span data-ttu-id="0f715-194">获取支持</span><span class="sxs-lookup"><span data-stu-id="0f715-194">Get support</span></span>

<span data-ttu-id="0f715-195">通过 Microsoft 支持网站获取支持。</span><span class="sxs-lookup"><span data-stu-id="0f715-195">Get support through the Microsoft support site.</span></span>

[<span data-ttu-id="0f715-196">文件 a 支持请求</span><span class="sxs-lookup"><span data-stu-id="0f715-196">File a support request</span></span>](https://support.microsoft.com/supportforbusiness/productselection?sapid=e9391227-fa6d-927b-0fff-f96288631b8f)
