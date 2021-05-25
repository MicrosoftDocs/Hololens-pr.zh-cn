---
title: 将 HoloLens 设置为展台
description: 了解如何设置和使用展台配置来锁定 HoloLens 设备上的应用。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 347501c3ac8f1b115b0d537332a17938a99d3257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397798"
---
# <a name="set-up-hololens-as-a-kiosk"></a><span data-ttu-id="922e9-103">将 HoloLens 设置为展台</span><span class="sxs-lookup"><span data-stu-id="922e9-103">Set up HoloLens as a kiosk</span></span>

<span data-ttu-id="922e9-104">可以通过将 HoloLens 设备配置为在展台模式下运行，将设备配置为用作固定用途设备（也称为展台）。</span><span class="sxs-lookup"><span data-stu-id="922e9-104">You can configure a HoloLens device to function as a fixed-purpose device, also called a *kiosk*, by configuring the device to run in kiosk mode.</span></span> <span data-ttu-id="922e9-105">展台模式限制 (或) 设备上可用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="922e9-105">Kiosk mode limits the applications (or users) that are available on the device.</span></span> <span data-ttu-id="922e9-106">展台模式是一项方便的功能，可用于将 HoloLens 设备专用于业务应用，或在应用演示中使用 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="922e9-106">Kiosk mode is a convenient feature that you can use to dedicate a HoloLens device to business apps, or to use the HoloLens device in an app demo.</span></span>

<span data-ttu-id="922e9-107">本文提供有关特定于 HoloLens 设备的展台配置的各个方面的信息。</span><span class="sxs-lookup"><span data-stu-id="922e9-107">This article provides information about aspects of kiosk configuration that are specific to HoloLens devices.</span></span> <span data-ttu-id="922e9-108">有关不同类型的基于 Windows 的展台以及如何配置这些展台的常规信息，请参阅在 [Windows 桌面](https://docs.microsoft.com/windows/configuration/kiosk-methods)版 上配置展台和数字签名。</span><span class="sxs-lookup"><span data-stu-id="922e9-108">For general information about the different types of Windows-based kiosks and how to configure them, see [Configure kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).</span></span>  

> [!IMPORTANT]  
> <span data-ttu-id="922e9-109">展台模式确定用户登录设备时可用的应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-109">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="922e9-110">但是，展台模式不是一种安全方法。</span><span class="sxs-lookup"><span data-stu-id="922e9-110">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="922e9-111">它不会阻止"允许"应用打开不允许的另一个应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-111">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="922e9-112">若要阻止打开应用或进程，请使用 WINDOWS DEFENDER 应用程序控制 ([WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 创建适当的策略。</span><span class="sxs-lookup"><span data-stu-id="922e9-112">In order to block apps or processes from opening, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span>
>
> <span data-ttu-id="922e9-113">详细了解如何Microsoft 服务用户使用的高级安全级别，HoloLens 2状态分离和 [隔离 - Defender 保护](security-state-separation-isolation.md#defender-protections)。</span><span class="sxs-lookup"><span data-stu-id="922e9-113">Learn more about the Microsoft services to give users an advanced level of security that HoloLens 2 uses, read more about [State separation and isolation - Defender protections](security-state-separation-isolation.md#defender-protections).</span></span> <span data-ttu-id="922e9-114">或者，了解如何使用 WDAC 和 Windows PowerShell 来允许或阻止HoloLens 2[设备上使用 Microsoft Intune。](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)</span><span class="sxs-lookup"><span data-stu-id="922e9-114">Or learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="922e9-115">可以在单应用或多应用配置中使用展台模式，并且可以使用三个流程之一来设置和部署展台配置。</span><span class="sxs-lookup"><span data-stu-id="922e9-115">You can use kiosk mode in either a single-app or a multi-app configuration, and you can use one of three processes to set up and deploy the kiosk configuration.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="922e9-116">删除多应用配置会删除分配的访问权限功能创建的用户锁定配置文件。</span><span class="sxs-lookup"><span data-stu-id="922e9-116">Deleting the multi-app configuration removes the user lockdown profiles that the assigned access feature created.</span></span> <span data-ttu-id="922e9-117">但是，它不会还原所有策略更改。</span><span class="sxs-lookup"><span data-stu-id="922e9-117">However, it does not revert all the policy changes.</span></span> <span data-ttu-id="922e9-118">若要还原这些策略，你必须将设备重置为出厂设置。</span><span class="sxs-lookup"><span data-stu-id="922e9-118">To revert these policies, you have to reset the device to the factory settings.</span></span>

## <a name="plan-the-kiosk-deployment"></a><span data-ttu-id="922e9-119">规划展台部署</span><span class="sxs-lookup"><span data-stu-id="922e9-119">Plan the kiosk deployment</span></span>

<span data-ttu-id="922e9-120">规划展台时，需要能够回答以下问题。</span><span class="sxs-lookup"><span data-stu-id="922e9-120">When planning your Kiosk you'll need to be able to answer the following questions.</span></span> <span data-ttu-id="922e9-121">下面是在阅读本页时要考虑的一些决定，还需要考虑这些问题。</span><span class="sxs-lookup"><span data-stu-id="922e9-121">Here are some decisions to think about while reading this page and some considerations for these questions.</span></span>
1. <span data-ttu-id="922e9-122">**谁将使用您的展台，他们将使用哪 [种类型的帐户 ()](hololens-identity.md) ？**</span><span class="sxs-lookup"><span data-stu-id="922e9-122">**Who will be using your Kiosk, and what [type of account(s)](hololens-identity.md) will they be using?**</span></span> <span data-ttu-id="922e9-123">这是你可能已做出的决定，不应为展台进行调整，但会影响稍后分配展台的方式。</span><span class="sxs-lookup"><span data-stu-id="922e9-123">This is a decision you have likely already made and shouldn't be adjusted for the sake of your Kiosk, but will affect how the Kiosk is assigned later.</span></span>
1. <span data-ttu-id="922e9-124">**是否需要为每个用户/组使用不同的网亭，或者是否为某些展台启用了一个？**</span><span class="sxs-lookup"><span data-stu-id="922e9-124">**Do you need to have either different Kiosks per user/group or a Kiosk not enabled for some?**</span></span> <span data-ttu-id="922e9-125">如果是这样，则需要通过 XML 创建展台。</span><span class="sxs-lookup"><span data-stu-id="922e9-125">If so, you'll want to create your Kiosk via XML.</span></span> 
1. <span data-ttu-id="922e9-126">**展台会有多少应用？**</span><span class="sxs-lookup"><span data-stu-id="922e9-126">**How many apps will be in your Kiosk?**</span></span> <span data-ttu-id="922e9-127">如果有1个以上的应用，则需要一个多应用展台。</span><span class="sxs-lookup"><span data-stu-id="922e9-127">If you have more than 1 app, you'll need a multi-app Kiosk.</span></span> 
1. <span data-ttu-id="922e9-128">**你的展台中 () 哪些应用？**</span><span class="sxs-lookup"><span data-stu-id="922e9-128">**Which app(s) will be in your Kiosk?**</span></span> <span data-ttu-id="922e9-129">除了你自己的应用外，请使用下面的 AUMIDs 列表添加任何 In-Box 应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-129">Please use our list of AUMIDs below to add any In-Box apps in addition to your own.</span></span>
1. <span data-ttu-id="922e9-130">**你计划如何部署展台？**</span><span class="sxs-lookup"><span data-stu-id="922e9-130">**How do you plan to deploy your Kiosk?**</span></span> <span data-ttu-id="922e9-131">如果要在 MDM 中注册设备，则建议使用 MDM 部署展台。</span><span class="sxs-lookup"><span data-stu-id="922e9-131">If you are enrolling device in MDM then we suggest using MDM to deploy your Kiosk.</span></span> <span data-ttu-id="922e9-132">如果不使用 MDM，则可以使用预配包进行部署。</span><span class="sxs-lookup"><span data-stu-id="922e9-132">If you are not using MDM then deployment with Provisioning Package is available.</span></span>  

### <a name="kiosk-mode-requirements"></a><span data-ttu-id="922e9-133">展台模式要求</span><span class="sxs-lookup"><span data-stu-id="922e9-133">Kiosk mode requirements</span></span>

<span data-ttu-id="922e9-134">可以将任何 HoloLens 2 设备配置为使用展台模式。</span><span class="sxs-lookup"><span data-stu-id="922e9-134">You can configure any HoloLens 2 device to use kiosk mode.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="922e9-135">仅当设备具有 Windows 全息 for Business 时，Kiosk 模式才可用。</span><span class="sxs-lookup"><span data-stu-id="922e9-135">Kiosk mode is available only if the device has Windows Holographic for Business.</span></span> <span data-ttu-id="922e9-136">所有 HoloLens 2 设备附带 Windows 全息 for Business，无其他版本。</span><span class="sxs-lookup"><span data-stu-id="922e9-136">All HoloLens 2 devices ship with Windows Holographic for Business and there are no other editions.</span></span> <span data-ttu-id="922e9-137">每个 HoloLens 2 设备都可以运行展台模式。</span><span class="sxs-lookup"><span data-stu-id="922e9-137">Every HoloLens 2 devices is able to run Kiosk mode out of the box.</span></span>
>
> <span data-ttu-id="922e9-138">HoloLens (第一代) 设备需要在操作系统版本和操作系统版本中进行升级。</span><span class="sxs-lookup"><span data-stu-id="922e9-138">HoloLens (1st gen) devices need to be upgraded both in terms of OS build and OS edition.</span></span> <span data-ttu-id="922e9-139">下面详细介绍了如何将 HoloLens (第一代) 更新到 [Windows 全息版企业](hololens1-upgrade-enterprise.md) 版。</span><span class="sxs-lookup"><span data-stu-id="922e9-139">Here is more information on updating a HoloLens (1st gen) to [Windows Holographic for Business](hololens1-upgrade-enterprise.md) edition.</span></span> <span data-ttu-id="922e9-140">若要更新 HoloLens (第一代) 设备以使用展台模式，你必须首先确保设备运行 Windows 10、版本1803或更高版本。</span><span class="sxs-lookup"><span data-stu-id="922e9-140">To update a HoloLens (1st gen) device to use kiosk mode, you must first make sure that the device runs Windows 10, version 1803, or a later version.</span></span> <span data-ttu-id="922e9-141">如果已使用 Windows 设备恢复工具将 HoloLens (第一代) 设备恢复到其默认内部版本，或者安装了最新更新，则设备已准备好进行配置。</span><span class="sxs-lookup"><span data-stu-id="922e9-141">If you have used the Windows Device Recovery Tool to recover your HoloLens (1st gen) device to its default build, or if you have installed the most recent updates, your device is ready to configure.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="922e9-142">若要帮助保护在展台模式下运行的设备，请考虑添加关闭 USB 连接等功能的设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="922e9-142">To help protect devices that run in kiosk mode, consider adding device management policies that turn off features such as USB connectivity.</span></span> <span data-ttu-id="922e9-143">此外，请检查更新环设置，以确保在营业时间内不会发生自动更新。</span><span class="sxs-lookup"><span data-stu-id="922e9-143">Additionally, check your update ring settings to make sure that automatic updates do not occur during business hours.</span></span>

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a><span data-ttu-id="922e9-144">决定单应用展台还是多应用展台</span><span class="sxs-lookup"><span data-stu-id="922e9-144">Decide between a single-app kiosk or a multi-app kiosk</span></span>

<span data-ttu-id="922e9-145">单应用展台在用户登录设备时启动指定的应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-145">A single-app kiosk starts the specified app when the user signs in to the device.</span></span> <span data-ttu-id="922e9-146">该“开始”菜单 Cortana 一样处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="922e9-146">The Start menu is disabled, as is Cortana.</span></span> <span data-ttu-id="922e9-147">HoloLens 2设备不响应"启动 ["](hololens2-basic-usage.md#start-gesture) 手势。</span><span class="sxs-lookup"><span data-stu-id="922e9-147">A HoloLens 2 device does not respond to the [Start](hololens2-basic-usage.md#start-gesture) gesture.</span></span> <span data-ttu-id="922e9-148">HoloLens (第一代) 设备不响应布满 [手势](hololens1-basic-usage.md) 。</span><span class="sxs-lookup"><span data-stu-id="922e9-148">A HoloLens (1st gen) device does not respond to the [bloom](hololens1-basic-usage.md) gesture.</span></span> <span data-ttu-id="922e9-149">由于只能运行一个应用，因此用户无法放置其他应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-149">Because only one app can run, the user cannot place other apps.</span></span>

<span data-ttu-id="922e9-150">当用户登录设备时，“开始”菜单应用展台会显示应用信息。</span><span class="sxs-lookup"><span data-stu-id="922e9-150">A multi-app kiosk displays the Start menu when the user signs in to the device.</span></span> <span data-ttu-id="922e9-151">展台配置确定哪些应用在 “开始”菜单。</span><span class="sxs-lookup"><span data-stu-id="922e9-151">The kiosk configuration determines which apps are available on the Start menu.</span></span> <span data-ttu-id="922e9-152">可以使用多应用展台为用户提供易于理解的体验，只需向用户呈现他们必须使用的东西，并删除他们不需要使用的东西。</span><span class="sxs-lookup"><span data-stu-id="922e9-152">You can use a multi-app kiosk to provide an easy-to-understand experience for users by presenting to them only the things that they have to use, and removing the things they don't need to use.</span></span>

<span data-ttu-id="922e9-153">下表列出了不同展台模式下的功能。</span><span class="sxs-lookup"><span data-stu-id="922e9-153">The following table lists the feature capabilities in the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="922e9-154">“开始”菜单</span><span class="sxs-lookup"><span data-stu-id="922e9-154">Start menu</span></span> |<span data-ttu-id="922e9-155">"快速操作"菜单</span><span class="sxs-lookup"><span data-stu-id="922e9-155">Quick Actions menu</span></span> |<span data-ttu-id="922e9-156">相机和视频</span><span class="sxs-lookup"><span data-stu-id="922e9-156">Camera and video</span></span> |<span data-ttu-id="922e9-157">Miracast</span><span class="sxs-lookup"><span data-stu-id="922e9-157">Miracast</span></span> |<span data-ttu-id="922e9-158">Cortana</span><span class="sxs-lookup"><span data-stu-id="922e9-158">Cortana</span></span> |<span data-ttu-id="922e9-159">内置语音命令</span><span class="sxs-lookup"><span data-stu-id="922e9-159">Built-in voice commands</span></span> |
| --- | --- | --- | --- | --- | --- | --- | 
|<span data-ttu-id="922e9-160">单应用展台</span><span class="sxs-lookup"><span data-stu-id="922e9-160">Single-app kiosk</span></span> |<span data-ttu-id="922e9-161">已禁用</span><span class="sxs-lookup"><span data-stu-id="922e9-161">Disabled</span></span> |<span data-ttu-id="922e9-162">已禁用</span><span class="sxs-lookup"><span data-stu-id="922e9-162">Disabled</span></span> |<span data-ttu-id="922e9-163">已禁用</span><span class="sxs-lookup"><span data-stu-id="922e9-163">Disabled</span></span> |<span data-ttu-id="922e9-164">已禁用</span><span class="sxs-lookup"><span data-stu-id="922e9-164">Disabled</span></span>   |<span data-ttu-id="922e9-165">已禁用</span><span class="sxs-lookup"><span data-stu-id="922e9-165">Disabled</span></span> |<span data-ttu-id="922e9-166">已启用<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="922e9-166">Enabled<sup>1</sup></span></span> |
|<span data-ttu-id="922e9-167">多应用展台</span><span class="sxs-lookup"><span data-stu-id="922e9-167">Multi-app kiosk</span></span> |<span data-ttu-id="922e9-168">Enabled</span><span class="sxs-lookup"><span data-stu-id="922e9-168">Enabled</span></span> |<span data-ttu-id="922e9-169">已启用<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="922e9-169">Enabled<sup>2</sup></span></span> |<span data-ttu-id="922e9-170">可用<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="922e9-170">Available<sup>2</sup></span></span> |<span data-ttu-id="922e9-171">可用<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="922e9-171">Available<sup>2</sup></span></span> |<span data-ttu-id="922e9-172">可用<sup>2、3</sup></span><span class="sxs-lookup"><span data-stu-id="922e9-172">Available<sup>2, 3</sup></span></span>  |<span data-ttu-id="922e9-173">已启用<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="922e9-173">Enabled<sup>1</sup></span></span> |

> <span data-ttu-id="922e9-174"><sup>1</sup> 与禁用功能相关的语音命令不起作用。</span><span class="sxs-lookup"><span data-stu-id="922e9-174"><sup>1</sup> Voice commands that relate to disabled features do not function.</span></span>  
> <span data-ttu-id="922e9-175"><sup>2</sup> 有关如何配置这些功能的详细信息，请参阅 [选择展台应用](#plan-kiosk-apps)。</span><span class="sxs-lookup"><span data-stu-id="922e9-175"><sup>2</sup> For more information about how to configure these features, see [Select kiosk apps](#plan-kiosk-apps).</span></span>  
> <span data-ttu-id="922e9-176"><sup>3</sup> 即使 Cortana 已禁用，也会启用内置语音命令。</span><span class="sxs-lookup"><span data-stu-id="922e9-176"><sup>3</sup> Even if Cortana is disabled, the built-in voice commands are enabled.</span></span>

<span data-ttu-id="922e9-177">下表列出了不同展台模式的用户支持功能。</span><span class="sxs-lookup"><span data-stu-id="922e9-177">The following table lists the user support features of the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="922e9-178">支持的用户类型</span><span class="sxs-lookup"><span data-stu-id="922e9-178">Supported user types</span></span> | <span data-ttu-id="922e9-179">自动登录</span><span class="sxs-lookup"><span data-stu-id="922e9-179">Automatic sign-in</span></span> | <span data-ttu-id="922e9-180">多个访问级别</span><span class="sxs-lookup"><span data-stu-id="922e9-180">Multiple access levels</span></span> |
| --- | --- | --- | --- |
|<span data-ttu-id="922e9-181">单应用展台</span><span class="sxs-lookup"><span data-stu-id="922e9-181">Single-app kiosk</span></span> |<span data-ttu-id="922e9-182">托管服务帐户 (Azure Active Directory (Azure AD) 或本地帐户中的 MSA) </span><span class="sxs-lookup"><span data-stu-id="922e9-182">Managed Service Account (MSA) in Azure Active Directory (Azure AD) or local account</span></span> |<span data-ttu-id="922e9-183">是</span><span class="sxs-lookup"><span data-stu-id="922e9-183">Yes</span></span> |<span data-ttu-id="922e9-184">否</span><span class="sxs-lookup"><span data-stu-id="922e9-184">No</span></span> |
|<span data-ttu-id="922e9-185">多应用展台</span><span class="sxs-lookup"><span data-stu-id="922e9-185">Multi-app kiosk</span></span> |<span data-ttu-id="922e9-186">Azure AD 帐户</span><span class="sxs-lookup"><span data-stu-id="922e9-186">Azure AD account</span></span> |<span data-ttu-id="922e9-187">否</span><span class="sxs-lookup"><span data-stu-id="922e9-187">No</span></span> |<span data-ttu-id="922e9-188">是</span><span class="sxs-lookup"><span data-stu-id="922e9-188">Yes</span></span> |

<span data-ttu-id="922e9-189">有关如何使用这些功能的示例，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="922e9-189">For examples of how to use these capabilities, see the following table.</span></span>

|<span data-ttu-id="922e9-190">将单应用展台用于：</span><span class="sxs-lookup"><span data-stu-id="922e9-190">Use a single-app kiosk for:</span></span> |<span data-ttu-id="922e9-191">使用多应用展台进行以下操作：</span><span class="sxs-lookup"><span data-stu-id="922e9-191">Use a multi-app kiosk for:</span></span> |
| --- | --- |
|<span data-ttu-id="922e9-192">仅对新员工运行 Dynamics 365 指南的设备。</span><span class="sxs-lookup"><span data-stu-id="922e9-192">A device that runs only a Dynamics 365 Guide for new employees.</span></span> |<span data-ttu-id="922e9-193">一种设备，用于为一系列员工运行指南和远程协助。</span><span class="sxs-lookup"><span data-stu-id="922e9-193">A device that runs both Guides and Remote Assistance for a range of employees.</span></span> |
|<span data-ttu-id="922e9-194">仅运行自定义应用的设备。</span><span class="sxs-lookup"><span data-stu-id="922e9-194">A device that runs only a custom app.</span></span> |<span data-ttu-id="922e9-195">作为大多数用户的展台工作的设备， (仅) 运行自定义应用程序，但作为特定用户组的标准设备工作。</span><span class="sxs-lookup"><span data-stu-id="922e9-195">A device that functions as a kiosk for most users (running only a custom app), but functions as a standard device for a specific group of users.</span></span> |

### <a name="plan-kiosk-apps"></a><span data-ttu-id="922e9-196">规划 kiosk 应用</span><span class="sxs-lookup"><span data-stu-id="922e9-196">Plan kiosk apps</span></span>

<span data-ttu-id="922e9-197">有关如何选择展台应用的一般信息，请参阅有关在展台模式下选择分配 ([应用) 。 ](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)</span><span class="sxs-lookup"><span data-stu-id="922e9-197">For general information about how to choose kiosk apps, see [Guidelines for choosing an app for assigned access (kiosk mode)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).</span></span>

<span data-ttu-id="922e9-198">如果使用 Windows 设备门户配置单应用展台，请在安装过程中选择该应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-198">If you use the Windows Device Portal to configure a single-app kiosk, you select the app during the setup process.</span></span>  

<span data-ttu-id="922e9-199">如果使用 Mobile 设备管理 (MDM) 系统或预配包来配置展台模式，请使用 [AssignedAccess 配置 ](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 服务提供程序 (CSP) 来指定应用程序。</span><span class="sxs-lookup"><span data-stu-id="922e9-199">If you use a Mobile Device Management (MDM) system or a provisioning package to configure kiosk mode, you use the [AssignedAccess Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) to specify applications.</span></span> <span data-ttu-id="922e9-200">CSP 使用 [AUMID 的应用程序用户 (ID) ](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 标识应用程序。</span><span class="sxs-lookup"><span data-stu-id="922e9-200">The CSP uses [Application User Model IDs (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) to identify applications.</span></span> <span data-ttu-id="922e9-201">下表列出了可在多应用展台中使用的一些开箱式应用程序的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="922e9-201">The following table lists the AUMIDs of some in-box applications that you can use in a multi-app kiosk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="922e9-202">展台模式确定用户登录设备时可用的应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-202">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="922e9-203">但是，展台模式不是一种安全方法。</span><span class="sxs-lookup"><span data-stu-id="922e9-203">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="922e9-204">它不会阻止"允许"应用打开不允许的另一个应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-204">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="922e9-205">由于我们不限制此行为，因此仍可从 Edge、文件资源管理器和 Microsoft Store启动应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-205">Because we do not restrict this behavior, apps can still be launched from Edge, File explorer, and the Microsoft Store apps.</span></span> <span data-ttu-id="922e9-206">如果不希望从展台启动特定应用，请使用 [WDAC](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) Windows Defender CSP (应用程序控制) 创建适当的策略。</span><span class="sxs-lookup"><span data-stu-id="922e9-206">If there are specific apps you don't want launched from a Kiosk, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span> 
> 
> <span data-ttu-id="922e9-207">此外，混合现实主页无法设置为展台应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-207">In addition, the Mixed Reality Home is not able to be set as a kiosk app.</span></span>

<a id="aumids"></a>

|<span data-ttu-id="922e9-208">应用名称</span><span class="sxs-lookup"><span data-stu-id="922e9-208">App Name</span></span> |<span data-ttu-id="922e9-209">AUMID</span><span class="sxs-lookup"><span data-stu-id="922e9-209">AUMID</span></span> |
| --- | --- |
|<span data-ttu-id="922e9-210">3D 查看器</span><span class="sxs-lookup"><span data-stu-id="922e9-210">3D Viewer</span></span> |<span data-ttu-id="922e9-211">Microsoft.Microsoft3DViewer \_ 8wekyb3d8bbwe \! Microsoft.Microsoft3DViewer</span><span class="sxs-lookup"><span data-stu-id="922e9-211">Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\!Microsoft.Microsoft3DViewer</span></span> |
|<span data-ttu-id="922e9-212">日历</span><span class="sxs-lookup"><span data-stu-id="922e9-212">Calendar</span></span> |<span data-ttu-id="922e9-213">microsoft.windowscommunicationsapps \_ 8wekyb3d8bbwe \! microsoft.windowslive.calendar</span><span class="sxs-lookup"><span data-stu-id="922e9-213">microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar</span></span> |
|<span data-ttu-id="922e9-214">相机<sup>1、2</sup></span><span class="sxs-lookup"><span data-stu-id="922e9-214">Camera<sup>1, 2</sup></span></span> |<span data-ttu-id="922e9-215">HoloCamera \_ cw5n1h2txyewy \! HoloCamera</span><span class="sxs-lookup"><span data-stu-id="922e9-215">HoloCamera\_cw5n1h2txyewy\!HoloCamera</span></span> |
|<span data-ttu-id="922e9-216">Cortana<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="922e9-216">Cortana<sup>3</sup></span></span> |<span data-ttu-id="922e9-217">Microsoft.549981C3F5F10 \_ 8wekyb3d8bbwe \! 应用</span><span class="sxs-lookup"><span data-stu-id="922e9-217">Microsoft.549981C3F5F10\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="922e9-218">HoloLens 上的设备选取器 (第一代) </span><span class="sxs-lookup"><span data-stu-id="922e9-218">Device Picker on HoloLens (1st gen)</span></span> |<span data-ttu-id="922e9-219">HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow</span><span class="sxs-lookup"><span data-stu-id="922e9-219">HoloDevicesFlow\_cw5n1h2txyewy\!HoloDevicesFlow</span></span> |
|<span data-ttu-id="922e9-220">HoloLens 2 上的设备选取器</span><span class="sxs-lookup"><span data-stu-id="922e9-220">Device Picker on HoloLens 2</span></span> |<span data-ttu-id="922e9-221">DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft. DevicesFlowHost</span><span class="sxs-lookup"><span data-stu-id="922e9-221">Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\!Microsoft.Windows.DevicesFlowHost</span></span> |
|<span data-ttu-id="922e9-222">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="922e9-222">Dynamics 365 Guides</span></span> |<span data-ttu-id="922e9-223">Dynamics365 \_ 8wekyb3d8bbwe \! MicrosoftGuides</span><span class="sxs-lookup"><span data-stu-id="922e9-223">Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\!MicrosoftGuides</span></span> |
|<span data-ttu-id="922e9-224">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="922e9-224">Dynamics 365 Remote Assist</span></span> |<span data-ttu-id="922e9-225">MicrosoftRemoteAssist \_ 8Wekyb3d8bbwe \! RemoteAssist</span><span class="sxs-lookup"><span data-stu-id="922e9-225">Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\!Microsoft.RemoteAssist</span></span> |
|<span data-ttu-id="922e9-226">反馈 &nbsp; 中心</span><span class="sxs-lookup"><span data-stu-id="922e9-226">Feedback&nbsp;Hub</span></span> |<span data-ttu-id="922e9-227">WindowsFeedbackHub \_ 8wekyb3d8bbwe \! 应用</span><span class="sxs-lookup"><span data-stu-id="922e9-227">Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="922e9-228">文件资源管理器</span><span class="sxs-lookup"><span data-stu-id="922e9-228">File Explorer</span></span> |<span data-ttu-id="922e9-229">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span><span class="sxs-lookup"><span data-stu-id="922e9-229">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span></span> |
|<span data-ttu-id="922e9-230">Mail</span><span class="sxs-lookup"><span data-stu-id="922e9-230">Mail</span></span> |<span data-ttu-id="922e9-231">microsoft.windowscommunicationsapps_8wekyb3d8bbwe！ windowslive</span><span class="sxs-lookup"><span data-stu-id="922e9-231">microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail</span></span> |
|<span data-ttu-id="922e9-232">旧的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="922e9-232">Old Microsoft Edge</span></span> |<span data-ttu-id="922e9-233">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span><span class="sxs-lookup"><span data-stu-id="922e9-233">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span></span> |
|<span data-ttu-id="922e9-234">新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="922e9-234">New Microsoft Edge</span></span> |<span data-ttu-id="922e9-235">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE</span><span class="sxs-lookup"><span data-stu-id="922e9-235">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE</span></span> |
|<span data-ttu-id="922e9-236">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="922e9-236">Microsoft Store</span></span> |<span data-ttu-id="922e9-237">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span><span class="sxs-lookup"><span data-stu-id="922e9-237">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span></span> |
|<span data-ttu-id="922e9-238">Miracast<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="922e9-238">Miracast<sup>4</sup></span></span> |&nbsp; |
|<span data-ttu-id="922e9-239">电影和电视</span><span class="sxs-lookup"><span data-stu-id="922e9-239">Movies & TV</span></span> |<span data-ttu-id="922e9-240">ZuneVideo \_ 8Wekyb3d8bbwe \! ZuneVideo</span><span class="sxs-lookup"><span data-stu-id="922e9-240">Microsoft.ZuneVideo\_8wekyb3d8bbwe\!Microsoft.ZuneVideo</span></span> |
|<span data-ttu-id="922e9-241">OneDrive</span><span class="sxs-lookup"><span data-stu-id="922e9-241">OneDrive</span></span> |<span data-ttu-id="922e9-242">microsoftskydrive \_ 8wekyb3d8bbwe \! 应用</span><span class="sxs-lookup"><span data-stu-id="922e9-242">microsoft.microsoftskydrive\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="922e9-243">照片</span><span class="sxs-lookup"><span data-stu-id="922e9-243">Photos</span></span> |<span data-ttu-id="922e9-244">\_8wekyb3d8bbwe \! 应用</span><span class="sxs-lookup"><span data-stu-id="922e9-244">Microsoft.Windows.Photos\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="922e9-245">旧设置</span><span class="sxs-lookup"><span data-stu-id="922e9-245">Old Settings</span></span> |<span data-ttu-id="922e9-246">HolographicSystemSettings_cw5n1h2txyewy！应用</span><span class="sxs-lookup"><span data-stu-id="922e9-246">HolographicSystemSettings_cw5n1h2txyewy!App</span></span> |
|<span data-ttu-id="922e9-247">新设置</span><span class="sxs-lookup"><span data-stu-id="922e9-247">New Settings</span></span> |<span data-ttu-id="922e9-248">BAEAEF15-9BAB-47FC-ACECAD2AE94B_cw5n1h2txyewy 800B！应用</span><span class="sxs-lookup"><span data-stu-id="922e9-248">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App</span></span> |
|<span data-ttu-id="922e9-249">提示</span><span class="sxs-lookup"><span data-stu-id="922e9-249">Tips</span></span> |<span data-ttu-id="922e9-250">HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips</span><span class="sxs-lookup"><span data-stu-id="922e9-250">Microsoft.HoloLensTips\_8wekyb3d8bbwe\!HoloLensTips</span></span> |

> <span data-ttu-id="922e9-251"><sup>1</sup> 若要启用照片或视频捕获，你必须将相机应用启用为展台应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-251"><sup>1</sup> To enable photo or video capture, you have to enable the Camera app as a kiosk app.</span></span>  
> <span data-ttu-id="922e9-252"><sup>2</sup> 启用相机应用时，请注意以下条件：</span><span class="sxs-lookup"><span data-stu-id="922e9-252"><sup>2</sup> When you enable the Camera app, be aware of the following conditions:</span></span>
> - <span data-ttu-id="922e9-253">"快速操作"菜单包括"照片和视频"按钮。</span><span class="sxs-lookup"><span data-stu-id="922e9-253">The Quick Actions menu includes the Photo and Video buttons.</span></span>  
> - <span data-ttu-id="922e9-254">还应启用可以与图片 (照片、邮件或 OneDrive) 等应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-254">You should also enable an app (such as Photos, Mail, or OneDrive) that can interact with or retrieve pictures.</span></span>  
>  
> <span data-ttu-id="922e9-255"><sup>3</sup> 即使未启用 Cortana 作为展台应用，内置语音命令也已启用。</span><span class="sxs-lookup"><span data-stu-id="922e9-255"><sup>3</sup> Even if you do not enable Cortana as a kiosk app, built-in voice commands are enabled.</span></span> <span data-ttu-id="922e9-256">但是，与已禁用功能相关的命令不起作用。</span><span class="sxs-lookup"><span data-stu-id="922e9-256">However, commands that are related to disabled features have no effect.</span></span>  
> <span data-ttu-id="922e9-257"><sup>4</sup> 不能直接启用 Miracast。</span><span class="sxs-lookup"><span data-stu-id="922e9-257"><sup>4</sup> You cannot enable Miracast directly.</span></span> <span data-ttu-id="922e9-258">若要启用 Miracast 作为展台应用，请启用相机应用和设备选取器应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-258">To enable Miracast as a kiosk app enable the Camera app and the Device Picker app.</span></span>

### <a name="plan-kiosk-profiles-for-users-or-groups"></a><span data-ttu-id="922e9-259">为用户或组规划展台配置文件</span><span class="sxs-lookup"><span data-stu-id="922e9-259">Plan kiosk profiles for users or groups</span></span>

<span data-ttu-id="922e9-260">创建 xml 文件或使用 Intune 的 UI 设置展台时，需要考虑谁将成为展台的用户。</span><span class="sxs-lookup"><span data-stu-id="922e9-260">When either creating the xml file or using Intune’s UI to set up a Kiosk you’ll need to consider who will be user the Kiosk.</span></span> <span data-ttu-id="922e9-261">展台配置可以限制为单个帐户或Azure AD组。</span><span class="sxs-lookup"><span data-stu-id="922e9-261">A Kiosk configuration can be limited to either an individual account or Azure AD groups.</span></span> 

<span data-ttu-id="922e9-262">通常为用户或用户组启用展台。</span><span class="sxs-lookup"><span data-stu-id="922e9-262">Typically Kiosks are enabled for either a user, or user group.</span></span> <span data-ttu-id="922e9-263">但是，如果打算编写自己的 XML 展台，可以考虑全局分配的访问权限，其中，展台在设备级别应用，而不考虑标识。</span><span class="sxs-lookup"><span data-stu-id="922e9-263">However if you plan on writing your own XML Kiosk, then you may want to consider Global Assigned Access, in which the Kiosk is applied at the device level regardless of Identity.</span></span> <span data-ttu-id="922e9-264">如果此要求你阅读 [有关全局分配访问展台的更多信息。](hololens-global-assigned-access-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="922e9-264">If this appeals to you [read more about Global Assigned Access Kiosks.](hololens-global-assigned-access-kiosk.md)</span></span>

#### <a name="if-you-are-creating-an-xml-file"></a><span data-ttu-id="922e9-265">如果要创建 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="922e9-265">If you are creating an XML file:</span></span>
-   <span data-ttu-id="922e9-266">你创建多个展台配置文件，并将每个配置文件分配给不同的用户/组。</span><span class="sxs-lookup"><span data-stu-id="922e9-266">You many create multiple Kiosk profiles, and assign each to different users/groups.</span></span> <span data-ttu-id="922e9-267">例如，具有多个应用Azure AD组展台，以及具有多个应用展台且应用单一的访问者。</span><span class="sxs-lookup"><span data-stu-id="922e9-267">Such as a Kiosk for your Azure AD Group that has many apps, and a Visitor that has a multiple app kiosk with a singular app.</span></span>
-   <span data-ttu-id="922e9-268">展台配置将称为"配置文件 **ID"，** 并且具有 GUID。</span><span class="sxs-lookup"><span data-stu-id="922e9-268">Your kiosk configuration will be called a **Profile Id** and have a GUID.</span></span>
-   <span data-ttu-id="922e9-269">通过指定用户类型并将同一 GUID 用于 **DefaultProfile ID**，在"配置"部分中分配该配置文件。</span><span class="sxs-lookup"><span data-stu-id="922e9-269">You will assign that Profile in the configs section by specifying the user type and using the same GUID for the **DefaultProfile Id**.</span></span>
- <span data-ttu-id="922e9-270">通过创建自定义 OMA URI 设备配置文件，然后使用 URI 值将其应用于 HoloLens 设备组，可创建 XML 文件，但仍通过 MDM 将其应用于设备：./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="922e9-270">A XML file can be created but still applied to a device via MDM by creating a custom OMA URI device configuration profile and applying it to HoloLens device group using the URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a><span data-ttu-id="922e9-271">如果要在 Intune 中创建展台。</span><span class="sxs-lookup"><span data-stu-id="922e9-271">If you are creating a Kiosk in Intune.</span></span>
-   <span data-ttu-id="922e9-272">每台设备只能接收单个展台配置文件，否则它将创建冲突，根本不接收展台配置。</span><span class="sxs-lookup"><span data-stu-id="922e9-272">Each device may only receive a single Kiosk profile, otherwise it will create a conflict and receive no Kiosk configurations at all.</span></span> 
    -   <span data-ttu-id="922e9-273">其他类型的配置文件和策略（如与展台配置文件无关的设备限制）不与展台配置文件冲突。</span><span class="sxs-lookup"><span data-stu-id="922e9-273">Other kinds of profiles and policies, such as device restrictions that are not related to the kiosk configuration profile, do not conflict with the kiosk configuration profile.</span></span>
-   <span data-ttu-id="922e9-274">将为属于用户登录类型的所有用户启用展台，这将使用用户或 Azure AD 组进行设置。</span><span class="sxs-lookup"><span data-stu-id="922e9-274">The Kiosk will be enabled for all users who are a part of the User logon type, this will be set with a user or Azure AD group.</span></span> 
-   <span data-ttu-id="922e9-275">设置展台配置后， **用户登录类型** (可以登录展台的用户) 并且选择了应用，则必须仍将设备配置分配给组。</span><span class="sxs-lookup"><span data-stu-id="922e9-275">After the Kiosk configuration is set and the **User logon type** (users who can log into the Kiosk) and the Apps are selected, the Device Configuration must still be assigned to a group.</span></span> <span data-ttu-id="922e9-276">分配的组 () 确定哪些设备接收展台设备配置，但如果启用了展台，则不会与交互。</span><span class="sxs-lookup"><span data-stu-id="922e9-276">The Assigned group(s) determines which devices receive the Kiosk device configuration, however does not interact with if the Kiosk is enabled or not.</span></span> 
    - <span data-ttu-id="922e9-277">有关在 Intune 中分配配置文件的效果的完整讨论，请参阅 [在 Microsoft Intune 中分配用户和设备配置文件](https://docs.microsoft.com/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="922e9-277">For a full discussion of the effects of assigning configuration profiles in Intune, see [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).</span></span>

### <a name="select-a-deployment-method"></a><span data-ttu-id="922e9-278">选择部署方法</span><span class="sxs-lookup"><span data-stu-id="922e9-278">Select a deployment method</span></span>

<span data-ttu-id="922e9-279">您可以选择下列方法之一来部署展台配置：</span><span class="sxs-lookup"><span data-stu-id="922e9-279">You can select one of the following methods to deploy kiosk configurations:</span></span>

- [<span data-ttu-id="922e9-280">Microsoft Intune 或其他移动设备管理 (MDM) 服务</span><span class="sxs-lookup"><span data-stu-id="922e9-280">Microsoft Intune or other mobile device management (MDM) service</span></span>](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="922e9-281">预配包</span><span class="sxs-lookup"><span data-stu-id="922e9-281">Provisioning package</span></span>](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="922e9-282">Windows 设备门户</span><span class="sxs-lookup"><span data-stu-id="922e9-282">Windows Device Portal</span></span>](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > <span data-ttu-id="922e9-283">由于此方法要求在设备上启用开发人员模式，因此我们建议你仅将其用于演示。</span><span class="sxs-lookup"><span data-stu-id="922e9-283">Because this method requires that Developer Mode be enabled on the device, we recommend that you use it only for demonstrations.</span></span>

<span data-ttu-id="922e9-284">下表列出了每种部署方法的功能和优势。</span><span class="sxs-lookup"><span data-stu-id="922e9-284">The following table lists the capabilities and benefits of each of the deployment methods.</span></span>

| &nbsp; |<span data-ttu-id="922e9-285">使用 Windows 设备门户进行部署</span><span class="sxs-lookup"><span data-stu-id="922e9-285">Deploy by using Windows Device Portal</span></span> |<span data-ttu-id="922e9-286">使用预配包进行部署</span><span class="sxs-lookup"><span data-stu-id="922e9-286">Deploy by using a provisioning package</span></span> |<span data-ttu-id="922e9-287">使用 MDM 进行部署</span><span class="sxs-lookup"><span data-stu-id="922e9-287">Deploy by using MDM</span></span> |
| --------------------------- | ------------- | -------------------- | ---- |
|<span data-ttu-id="922e9-288">部署单应用展台</span><span class="sxs-lookup"><span data-stu-id="922e9-288">Deploy single-app kiosks</span></span>   | <span data-ttu-id="922e9-289">是</span><span class="sxs-lookup"><span data-stu-id="922e9-289">Yes</span></span>           | <span data-ttu-id="922e9-290">是</span><span class="sxs-lookup"><span data-stu-id="922e9-290">Yes</span></span>                  | <span data-ttu-id="922e9-291">是</span><span class="sxs-lookup"><span data-stu-id="922e9-291">Yes</span></span>  |
|<span data-ttu-id="922e9-292">部署多应用展台</span><span class="sxs-lookup"><span data-stu-id="922e9-292">Deploy multi-app kiosks</span></span>    | <span data-ttu-id="922e9-293">否</span><span class="sxs-lookup"><span data-stu-id="922e9-293">No</span></span>            | <span data-ttu-id="922e9-294">是</span><span class="sxs-lookup"><span data-stu-id="922e9-294">Yes</span></span>                  | <span data-ttu-id="922e9-295">是</span><span class="sxs-lookup"><span data-stu-id="922e9-295">Yes</span></span>  |
|<span data-ttu-id="922e9-296">仅部署到本地设备</span><span class="sxs-lookup"><span data-stu-id="922e9-296">Deploy to local devices only</span></span> | <span data-ttu-id="922e9-297">是</span><span class="sxs-lookup"><span data-stu-id="922e9-297">Yes</span></span>           | <span data-ttu-id="922e9-298">是</span><span class="sxs-lookup"><span data-stu-id="922e9-298">Yes</span></span>                  | <span data-ttu-id="922e9-299">否</span><span class="sxs-lookup"><span data-stu-id="922e9-299">No</span></span>   |
|<span data-ttu-id="922e9-300">使用开发人员模式进行部署</span><span class="sxs-lookup"><span data-stu-id="922e9-300">Deploy by using Developer Mode</span></span> |<span data-ttu-id="922e9-301">必须</span><span class="sxs-lookup"><span data-stu-id="922e9-301">Required</span></span>       | <span data-ttu-id="922e9-302">不是必需</span><span class="sxs-lookup"><span data-stu-id="922e9-302">Not required</span></span>            | <span data-ttu-id="922e9-303">不是必需</span><span class="sxs-lookup"><span data-stu-id="922e9-303">Not required</span></span>   |
|<span data-ttu-id="922e9-304">使用 Azure Active Directory (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="922e9-304">Deploy by using Azure Active Directory (Azure AD)</span></span>  | <span data-ttu-id="922e9-305">不是必需</span><span class="sxs-lookup"><span data-stu-id="922e9-305">Not required</span></span>            | <span data-ttu-id="922e9-306">不需要</span><span class="sxs-lookup"><span data-stu-id="922e9-306">Not required</span></span>                   | <span data-ttu-id="922e9-307">必须</span><span class="sxs-lookup"><span data-stu-id="922e9-307">Required</span></span>  |
|<span data-ttu-id="922e9-308">自动部署</span><span class="sxs-lookup"><span data-stu-id="922e9-308">Deploy automatically</span></span>      | <span data-ttu-id="922e9-309">否</span><span class="sxs-lookup"><span data-stu-id="922e9-309">No</span></span>            | <span data-ttu-id="922e9-310">否</span><span class="sxs-lookup"><span data-stu-id="922e9-310">No</span></span>                   | <span data-ttu-id="922e9-311">是</span><span class="sxs-lookup"><span data-stu-id="922e9-311">Yes</span></span>  |
|<span data-ttu-id="922e9-312">部署速度</span><span class="sxs-lookup"><span data-stu-id="922e9-312">Deployment speed</span></span>            | <span data-ttu-id="922e9-313">快速</span><span class="sxs-lookup"><span data-stu-id="922e9-313">Fast</span></span>       | <span data-ttu-id="922e9-314">快</span><span class="sxs-lookup"><span data-stu-id="922e9-314">Fast</span></span>                 | <span data-ttu-id="922e9-315">慢</span><span class="sxs-lookup"><span data-stu-id="922e9-315">Slow</span></span> |
|<span data-ttu-id="922e9-316">大规模部署</span><span class="sxs-lookup"><span data-stu-id="922e9-316">Deploy at scale</span></span> | <span data-ttu-id="922e9-317">不推荐</span><span class="sxs-lookup"><span data-stu-id="922e9-317">Not recommended</span></span>    | <span data-ttu-id="922e9-318">建议</span><span class="sxs-lookup"><span data-stu-id="922e9-318">Recommended</span></span>        | <span data-ttu-id="922e9-319">建议</span><span class="sxs-lookup"><span data-stu-id="922e9-319">Recommended</span></span> |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a><span data-ttu-id="922e9-320">使用Microsoft Intune或其他 MDM 设置单应用或多应用展台</span><span class="sxs-lookup"><span data-stu-id="922e9-320">Use Microsoft Intune or other MDM to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="922e9-321">若要使用设备或其他 MDM Microsoft Intune设置展台模式，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="922e9-321">To set up kiosk mode by using Microsoft Intune or another MDM system, follow these steps.</span></span>

1. <span data-ttu-id="922e9-322">[准备注册设备](#mdmenroll)。</span><span class="sxs-lookup"><span data-stu-id="922e9-322">[Prepare to enroll the devices](#mdmenroll).</span></span>
1. <span data-ttu-id="922e9-323">[创建展台配置文件](#mdmprofile)。</span><span class="sxs-lookup"><span data-stu-id="922e9-323">[Create a kiosk configuration profile](#mdmprofile).</span></span>
1. <span data-ttu-id="922e9-324">配置展台。</span><span class="sxs-lookup"><span data-stu-id="922e9-324">Configure the kiosk.</span></span>
   - <span data-ttu-id="922e9-325">[配置单应用展台的设置](#mdmconfigsingle)。</span><span class="sxs-lookup"><span data-stu-id="922e9-325">[Configure the settings for a single-app kiosk](#mdmconfigsingle).</span></span>
   - <span data-ttu-id="922e9-326">[配置多应用展台的设置](#mdmconfigmulti)。</span><span class="sxs-lookup"><span data-stu-id="922e9-326">[Configure the settings for a multi-app kiosk](#mdmconfigmulti).</span></span>
1. <span data-ttu-id="922e9-327">[将展台配置文件分配给组](#mdmassign)。</span><span class="sxs-lookup"><span data-stu-id="922e9-327">[Assign the kiosk configuration profile to a group](#mdmassign).</span></span>
1. <span data-ttu-id="922e9-328">部署设备。</span><span class="sxs-lookup"><span data-stu-id="922e9-328">Deploy the devices.</span></span>
   - <span data-ttu-id="922e9-329">[部署单应用展台](#mdmsingledeploy)。</span><span class="sxs-lookup"><span data-stu-id="922e9-329">[Deploy a single-app kiosk](#mdmsingledeploy).</span></span>
   - <span data-ttu-id="922e9-330">[部署多应用展台](#mdmmultideploy)。</span><span class="sxs-lookup"><span data-stu-id="922e9-330">[Deploy a multi-app kiosk](#mdmmultideploy).</span></span>

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a><span data-ttu-id="922e9-331">MDM，步骤 1 &ndash; 准备注册设备</span><span class="sxs-lookup"><span data-stu-id="922e9-331">MDM, step 1 &ndash; Prepare to enroll the devices</span></span>

<span data-ttu-id="922e9-332">可以将 MDM 系统配置为在用户首次登录时自动注册 HoloLens 设备，或让用户手动注册设备。</span><span class="sxs-lookup"><span data-stu-id="922e9-332">You can configure your MDM system to enroll HoloLens devices automatically when the user first signs in, or have users enroll devices manually.</span></span> <span data-ttu-id="922e9-333">设备还必须加入到你的Azure AD域，并分配到相应的组。</span><span class="sxs-lookup"><span data-stu-id="922e9-333">The devices also have to be joined to your Azure AD domain, and assigned to the appropriate groups.</span></span>

<span data-ttu-id="922e9-334">若要详细了解如何注册设备，请参阅在 MDM 中注册 [HoloLens](hololens-enroll-mdm.md) 和 Windows 设备的 [Intune 注册方法](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)。</span><span class="sxs-lookup"><span data-stu-id="922e9-334">For more information about how to enroll the devices, see [Enroll HoloLens in MDM](hololens-enroll-mdm.md) and [Intune enrollment methods for Windows devices](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).</span></span>

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a><span data-ttu-id="922e9-335">MDM，步骤 2 &ndash; 创建展台配置文件</span><span class="sxs-lookup"><span data-stu-id="922e9-335">MDM, step 2 &ndash; Create a kiosk configuration profile</span></span>

1. <span data-ttu-id="922e9-336">打开 [Azure](https://portal.azure.com/) 门户并登录到Intune 管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="922e9-336">Open the [Azure](https://portal.azure.com/) portal and sign in to your Intune administrator account.</span></span>
1. <span data-ttu-id="922e9-337">选择 **Microsoft Intune**  >  **设备配置-配置** 文件 ""  >  **创建配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="922e9-337">Select **Microsoft Intune** > **Device configuration - Profiles** > **Create profile**.</span></span>
1. <span data-ttu-id="922e9-338">输入配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="922e9-338">Enter a profile name.</span></span>
1. <span data-ttu-id="922e9-339">选择 "**平台**  >  **Windows 10 和更高版本**"，然后选择 "**配置文件类型**" "  > **设备限制**"。</span><span class="sxs-lookup"><span data-stu-id="922e9-339">Select **Platform** > **Windows 10 and later**, and then select **Profile type** >**Device restrictions**.</span></span>
1. <span data-ttu-id="922e9-340">选择 "**配置**  >  **展台**"，然后选择下列各项之一：</span><span class="sxs-lookup"><span data-stu-id="922e9-340">Select **Configure** > **Kiosk**, and then select one of the following:</span></span>
   - <span data-ttu-id="922e9-341">若要创建单应用展台，请选择 **展台模式**  >  **单应用展台**。</span><span class="sxs-lookup"><span data-stu-id="922e9-341">To create a single-app kiosk, select **Kiosk Mode** > **Single-app kiosk**.</span></span>
   - <span data-ttu-id="922e9-342">若要创建多应用展台，请选择 **展台模式**  >  **多应用展台**。</span><span class="sxs-lookup"><span data-stu-id="922e9-342">To create a multi-app kiosk, select **Kiosk Mode** > **Multi-app kiosk**.</span></span>
1. <span data-ttu-id="922e9-343">若要开始配置展台，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="922e9-343">To start configuring the kiosk, select **Add**.</span></span>

<span data-ttu-id="922e9-344">后续步骤会有所不同，具体取决于所需的展台类型。</span><span class="sxs-lookup"><span data-stu-id="922e9-344">Your next steps differ depending on the type of kiosk that you want.</span></span> <span data-ttu-id="922e9-345">有关详细信息，请选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="922e9-345">For more information, select one of the following options:</span></span>  

- [<span data-ttu-id="922e9-346">单应用展台</span><span class="sxs-lookup"><span data-stu-id="922e9-346">Single-app kiosk</span></span>](#mdmconfigsingle)
- [<span data-ttu-id="922e9-347">多应用展台</span><span class="sxs-lookup"><span data-stu-id="922e9-347">Multi-app kiosk</span></span>](#mdmconfigmulti)

<span data-ttu-id="922e9-348">有关如何创建展台配置文件的详细信息，请参阅 [使用 Intune 作为专用展台运行的 windows 10 和 Windows 全息版设备设置](https://docs.microsoft.com/intune/configuration/kiosk-settings)。</span><span class="sxs-lookup"><span data-stu-id="922e9-348">For more information about how to create a kiosk configuration profile, see [Windows 10 and Windows Holographic for Business device settings to run as a dedicated kiosk using Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).</span></span>

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a><span data-ttu-id="922e9-349">MDM，步骤 3 (单应用) &ndash;  配置单应用展台的设置</span><span class="sxs-lookup"><span data-stu-id="922e9-349">MDM, step 3 (single-app) &ndash;  Configure the settings for a single-app kiosk</span></span>

<span data-ttu-id="922e9-350">本部分总结了单应用展台所需的设置。</span><span class="sxs-lookup"><span data-stu-id="922e9-350">This section summarizes the settings that a single-app kiosk requires.</span></span> <span data-ttu-id="922e9-351">有关更多详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="922e9-351">For more details, see the following articles:</span></span>

- <span data-ttu-id="922e9-352">有关如何在 Intune 中配置展台配置文件的信息，请参阅 [如何使用 Microsoft Intune 配置展台模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="922e9-352">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="922e9-353">有关 Intune 中的单应用展台可用设置的详细信息，请参阅 [单一全屏应用网亭](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="922e9-353">For more information about the available settings for single-app kiosks in Intune, see [Single full-screen app kiosks](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span></span>
- <span data-ttu-id="922e9-354">对于其他 MDM 服务，请查看提供程序的文档以了解相关说明。</span><span class="sxs-lookup"><span data-stu-id="922e9-354">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="922e9-355">如果必须使用自定义 XML 配置在 MDM 服务中设置展台，请 [创建一个定义 kiosk 配置的 XML 文件](#ppkioskconfig)。</span><span class="sxs-lookup"><span data-stu-id="922e9-355">If you have to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span>

1. <span data-ttu-id="922e9-356">选择 "**用户登录类型**"  >  "**本地用户帐户**"，然后输入可以登录到展台的本地 (设备) 帐户或 Microsoft 帐户)  (的用户名。</span><span class="sxs-lookup"><span data-stu-id="922e9-356">Select **User logon type** > **Local user account**, and then enter the user name of the local (device) account or Microsoft Account (MSA) that can sign in to the kiosk.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="922e9-357">Windows Holographic for Business 不支持“自动登录”用户帐户类型。</span><span class="sxs-lookup"><span data-stu-id="922e9-357">**Autologon** user account types aren't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="922e9-358">选择 "**应用程序类型**  >  **存储应用**"，然后从列表中选择一个应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-358">Select **Application type** > **Store app**, and then select an app from the list.</span></span>

<span data-ttu-id="922e9-359">下一步是 [将配置文件](#mdmassign) 分配给组。</span><span class="sxs-lookup"><span data-stu-id="922e9-359">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a><span data-ttu-id="922e9-360">MDM，步骤 3 (多应用) &ndash; 配置多应用展台的设置</span><span class="sxs-lookup"><span data-stu-id="922e9-360">MDM, step 3 (multi-app) &ndash; Configure the settings for a multi-app kiosk</span></span>

<span data-ttu-id="922e9-361">本部分总结了多应用展台所需的设置。</span><span class="sxs-lookup"><span data-stu-id="922e9-361">This section summarizes the settings that a multi-app kiosk requires.</span></span> <span data-ttu-id="922e9-362">有关更详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="922e9-362">For more detailed information, see the following articles:</span></span>

- <span data-ttu-id="922e9-363">若要了解如何在 Intune 中配置展台配置文件，请参阅[How to Configure Kiosk Mode Using Microsoft Intune。](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="922e9-363">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="922e9-364">有关 Intune 中多应用展台的可用设置详细信息，请参阅 [多应用展台](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="922e9-364">For more information about the available settings for multi-app kiosks in Intune, see [Multi-app kiosks](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span></span>
- <span data-ttu-id="922e9-365">对于其他 MDM 服务，请查看提供商的文档，了解相关说明。</span><span class="sxs-lookup"><span data-stu-id="922e9-365">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="922e9-366">如果需要使用自定义 XML 配置在 MDM 服务中设置展台，请创建 [定义](#ppkioskconfig)展台配置的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="922e9-366">If you need to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span> <span data-ttu-id="922e9-367">如果使用 XML 文件，请确保包含"开始 ["布局](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="922e9-367">If you use an XML file, make sure to include the [Start layout](#start-layout-for-hololens).</span></span>  
- <span data-ttu-id="922e9-368">可以选择将自定义的"开始"布局与 Intune 或其他 MDM 服务一同使用。</span><span class="sxs-lookup"><span data-stu-id="922e9-368">You can optionally use a custom Start layout with Intune or other MDM services.</span></span> <span data-ttu-id="922e9-369">有关详细信息，请参阅启动[Intune 和 Intune (MDM 的布局) 。 ](#start-layout-file-for-mdm-intune-and-others)</span><span class="sxs-lookup"><span data-stu-id="922e9-369">For more information, see [Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

1. <span data-ttu-id="922e9-370">选择 **"Windows 10 S 模式设备""目标设备**  >  **否"。**</span><span class="sxs-lookup"><span data-stu-id="922e9-370">Select **Target Windows 10 in S mode devices** > **No**.</span></span>  
>[!NOTE]  
> <span data-ttu-id="922e9-371">Windows Holographic for Business 上不支持 S 模式。</span><span class="sxs-lookup"><span data-stu-id="922e9-371">S mode isn't supported on Windows Holographic for Business.</span></span>

1. <span data-ttu-id="922e9-372">选择 **"用户登录类型Azure AD** 组或用户登录类型  >    >  **HoloLens visitor，** 然后添加一个或多个用户组或帐户。</span><span class="sxs-lookup"><span data-stu-id="922e9-372">Select **User logon type** > **Azure AD user or group** or **User logon type** > **HoloLens visitor**, and then add one or more user groups or accounts.</span></span>  

   <span data-ttu-id="922e9-373">只有属于你在用户登录类型中指定的组或帐户 **的用户** 才能使用展台体验。</span><span class="sxs-lookup"><span data-stu-id="922e9-373">Only users who belong to the groups or accounts that you specify in **User logon type** can use the kiosk experience.</span></span>

1. <span data-ttu-id="922e9-374">使用下列选项选择一个或多个应用：</span><span class="sxs-lookup"><span data-stu-id="922e9-374">Select one or more apps by using the following options:</span></span>
   - <span data-ttu-id="922e9-375">若要添加已上传的业务线应用，请选择" **添加应用商店应用** "，然后选择想要的应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-375">To add an uploaded line-of-business app, select **Add store app** and then select the app that you want.</span></span>
   - <span data-ttu-id="922e9-376">若要通过指定应用的 AUMID 来添加应用，请选择"按 **AUMID** 添加"，然后输入应用的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="922e9-376">To add an app by specifying its AUMID, select **Add by AUMID** and then enter the AUMID of the app.</span></span> [<span data-ttu-id="922e9-377">查看可用 AUMID 的列表</span><span class="sxs-lookup"><span data-stu-id="922e9-377">See the list of available AUMIDs</span></span>](#aumids)

<span data-ttu-id="922e9-378">下一步是 [将配置文件](#mdmassign) 分配给组。</span><span class="sxs-lookup"><span data-stu-id="922e9-378">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a><span data-ttu-id="922e9-379">MDM，步骤 4 &ndash; 将展台配置文件分配给组</span><span class="sxs-lookup"><span data-stu-id="922e9-379">MDM, step 4 &ndash; Assign the kiosk configuration profile to a group</span></span>

<span data-ttu-id="922e9-380">使用 **展** 台配置文件的"分配"页可设置展台配置的部署位置。</span><span class="sxs-lookup"><span data-stu-id="922e9-380">Use the **Assignments** page of the kiosk configuration profile to set where you want the kiosk configuration to deploy.</span></span> <span data-ttu-id="922e9-381">最简单的情况是，在设备在 MDM 中注册时，将展台配置文件分配给将包含 HoloLens 设备的组。</span><span class="sxs-lookup"><span data-stu-id="922e9-381">In the simplest case, you assign the kiosk configuration profile to a group that will contain the HoloLens device when the device enrolls in MDM.</span></span>

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a><span data-ttu-id="922e9-382">MDM，步骤 5 (单应用) &ndash; 部署单应用展台</span><span class="sxs-lookup"><span data-stu-id="922e9-382">MDM, step 5 (single-app) &ndash; Deploy a single-app kiosk</span></span>

<span data-ttu-id="922e9-383">使用 MDM 系统时，可以在 OOBE 期间在 MDM 中注册设备。</span><span class="sxs-lookup"><span data-stu-id="922e9-383">When you use an MDM system, you can enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="922e9-384">在 OOBE 完成后，登录到设备很简单。</span><span class="sxs-lookup"><span data-stu-id="922e9-384">After OOBE finishes, signing in to the device is easy.</span></span>

<span data-ttu-id="922e9-385">在 OOBE 期间，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="922e9-385">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="922e9-386">使用在展台配置文件中指定的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="922e9-386">Sign in by using the account that you specified in the kiosk configuration profile.</span></span>
1. <span data-ttu-id="922e9-387">注册该设备。</span><span class="sxs-lookup"><span data-stu-id="922e9-387">Enroll the device.</span></span> <span data-ttu-id="922e9-388">请确保设备已添加到展台配置文件分配到的组。</span><span class="sxs-lookup"><span data-stu-id="922e9-388">Make sure that the device is added to the group that the kiosk configuration profile is assigned to.</span></span>
1. <span data-ttu-id="922e9-389">等待 OOBE 完成，针对要下载并安装的应用商店应用，以及要应用的策略。</span><span class="sxs-lookup"><span data-stu-id="922e9-389">Wait for OOBE to finish, for the store app to download and install, and for policies to be applied.</span></span> <span data-ttu-id="922e9-390">然后重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="922e9-390">Then restart the device.</span></span>

<span data-ttu-id="922e9-391">下次登录到设备时，kiosk 应用应自动启动。</span><span class="sxs-lookup"><span data-stu-id="922e9-391">The next time you sign in to the device, the kiosk app should automatically start.</span></span>

<span data-ttu-id="922e9-392">如果此时未看到展台配置，请 [检查分配状态](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="922e9-392">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a><span data-ttu-id="922e9-393">MDM，步骤 5 (多应用程序) &ndash; 部署多应用展台</span><span class="sxs-lookup"><span data-stu-id="922e9-393">MDM, step 5 (multi-app) &ndash; Deploy a multi-app kiosk</span></span>

<span data-ttu-id="922e9-394">使用 MDM 系统时，可以将设备加入到 Azure AD 租户，并在 OOBE 期间在 MDM 中注册设备。</span><span class="sxs-lookup"><span data-stu-id="922e9-394">When you use an MDM system, you can join the device to your Azure AD tenant and enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="922e9-395">如果需要，请向用户提供注册信息，使其在 OOBE 过程中可用。</span><span class="sxs-lookup"><span data-stu-id="922e9-395">If appropriate, provide the enrollment information to the users so that they have it available during the OOBE process.</span></span>

> [!NOTE]  
> <span data-ttu-id="922e9-396">如果已将 kiosk 配置文件分配到包含用户的组，请确保其中一个用户帐户是登录到该设备的第一个帐户。</span><span class="sxs-lookup"><span data-stu-id="922e9-396">If you have assigned the kiosk configuration profile to a group that contains users, make sure that one of those user accounts is the first account to sign in to the device.</span></span>

<span data-ttu-id="922e9-397">在 OOBE 期间，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="922e9-397">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="922e9-398">使用属于 **用户登录类型** 组的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="922e9-398">Sign in by using the account that belongs to the **User logon type** group.</span></span>
1. <span data-ttu-id="922e9-399">注册该设备。</span><span class="sxs-lookup"><span data-stu-id="922e9-399">Enroll the device.</span></span>
1. <span data-ttu-id="922e9-400">等待要下载和安装的展台配置文件中的任何应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-400">Wait for any apps that are part of the kiosk configuration profile to download and install.</span></span> <span data-ttu-id="922e9-401">另外，请等待策略应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-401">Also, wait for policies to be applied.</span></span>  
1. <span data-ttu-id="922e9-402">在 OOBE 完成后，可以通过 Microsoft 应用商店或旁加载来安装其他应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-402">After OOBE finishes, you can install additional apps from the Microsoft store or by sideloading.</span></span> <span data-ttu-id="922e9-403">[设备](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) 所属的组的必需应用会自动安装。</span><span class="sxs-lookup"><span data-stu-id="922e9-403">[Required apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) for the group that the device belongs to install automatically.</span></span>
1. <span data-ttu-id="922e9-404">安装完成后，重启设备。</span><span class="sxs-lookup"><span data-stu-id="922e9-404">After the installation finishes, restart the device.</span></span>

<span data-ttu-id="922e9-405">下次使用属于用户登录类型的帐户登录到设备时，展台应用应会自动启动。</span><span class="sxs-lookup"><span data-stu-id="922e9-405">The next time you sign in to the device by using an account that belongs to the **User logon type**, the kiosk app should automatically launch.</span></span>

<span data-ttu-id="922e9-406">如果此时看不到展台配置， [请检查分配状态](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="922e9-406">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a><span data-ttu-id="922e9-407">使用预配包设置单应用或多应用展台</span><span class="sxs-lookup"><span data-stu-id="922e9-407">Use a provisioning package to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="922e9-408">若要使用预配包设置展台模式，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="922e9-408">To set up kiosk mode by using a provisioning package, follow these steps.</span></span>

1. <span data-ttu-id="922e9-409">[创建定义展台配置的 XML 文件。，](#ppkioskconfig)包括"开始 ["布局](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="922e9-409">[Create an XML file that defines the kiosk configuration.](#ppkioskconfig), including a [Start layout](#start-layout-for-hololens).</span></span>
2. [<span data-ttu-id="922e9-410">将 XML 文件添加到预配包。</span><span class="sxs-lookup"><span data-stu-id="922e9-410">Add the XML file to a provisioning package.</span></span>](#ppconfigadd)
3. [<span data-ttu-id="922e9-411">将预配包应用于 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="922e9-411">Apply the provisioning package to HoloLens.</span></span>](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a><span data-ttu-id="922e9-412">预配包，步骤 1 &ndash; 创建展台配置 XML 文件</span><span class="sxs-lookup"><span data-stu-id="922e9-412">Provisioning package, step 1 &ndash; Create a kiosk configuration XML file</span></span>

<span data-ttu-id="922e9-413">按照 [一般说明为 Windows](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)桌面创建展台配置 XML 文件，但以下情况除外：</span><span class="sxs-lookup"><span data-stu-id="922e9-413">Follow [the general instructions to create a kiosk configuration XML file for Windows desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), except for the following:</span></span>

- <span data-ttu-id="922e9-414">不要将经典 Windows 应用程序 (Win32) 。</span><span class="sxs-lookup"><span data-stu-id="922e9-414">Do not include Classic Windows applications (Win32).</span></span> <span data-ttu-id="922e9-415">HoloLens 不支持这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="922e9-415">HoloLens does not support these applications.</span></span>
- <span data-ttu-id="922e9-416">使用 [占位符"开始布局 XML](#start-layout-for-hololens) for HoloLens"。</span><span class="sxs-lookup"><span data-stu-id="922e9-416">Use the [placeholder Start layout XML](#start-layout-for-hololens) for HoloLens.</span></span>
- <span data-ttu-id="922e9-417">可选：向展台配置添加来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="922e9-417">Optional: Add guest access to the kiosk configuration</span></span>

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a><span data-ttu-id="922e9-418">可选：向展台配置添加来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="922e9-418">Optional: Add guest access to the kiosk configuration</span></span>

<span data-ttu-id="922e9-419">在 [XML **文件的"配置**](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)"部分中，可以配置名为 **Visitor** 的特殊组，以允许来宾使用展台。</span><span class="sxs-lookup"><span data-stu-id="922e9-419">In the [**Configs** section of the XML file](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), you can configure a special group named **Visitor** to allow guests to use the kiosk.</span></span> <span data-ttu-id="922e9-420">当展台配置为支持"访问者 **"特殊组** 时，登录页中会添加"来宾"选项。</span><span class="sxs-lookup"><span data-stu-id="922e9-420">When the kiosk is configured to support the **Visitor** special group, a "**Guest**" option is added to the sign-in page.</span></span> <span data-ttu-id="922e9-421">**来宾** 帐户不需要密码，当帐户退出时，与帐户关联的任何数据都将被删除。</span><span class="sxs-lookup"><span data-stu-id="922e9-421">The **Guest** account does not require a password, and any data that is associated with the account is deleted when the account signs out.</span></span>

<span data-ttu-id="922e9-422">若要启用 **来宾帐户** ，请向展台配置 XML 添加以下代码片段：</span><span class="sxs-lookup"><span data-stu-id="922e9-422">To enable the **Guest** account, add the following snippet to your kiosk configuration XML:</span></span>

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a><span data-ttu-id="922e9-423">启用访问者自动登录</span><span class="sxs-lookup"><span data-stu-id="922e9-423">Enable Visitor Autologon</span></span>

<span data-ttu-id="922e9-424">生成 [Windows 全息版时，版本 21H1](hololens-release-notes.md#windows-holographic-version-21h1) 和更高版本：</span><span class="sxs-lookup"><span data-stu-id="922e9-424">On builds [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and onwards:</span></span>
- <span data-ttu-id="922e9-425">AAD 和非添加配置都支持为展台模式启用自动登录的访问者帐户。</span><span class="sxs-lookup"><span data-stu-id="922e9-425">AAD and Non-ADD configurations both support visitor accounts being auto-logon enabled for Kiosk modes.</span></span>

##### <a name="non-aad-configuration"></a><span data-ttu-id="922e9-426">非 AAD 配置</span><span class="sxs-lookup"><span data-stu-id="922e9-426">Non-AAD configuration</span></span>

1. <span data-ttu-id="922e9-427">创建一个预配包，其中：</span><span class="sxs-lookup"><span data-stu-id="922e9-427">Create a provisioning package that:</span></span>
    1. <span data-ttu-id="922e9-428">将运行时设置 AssignedAccess 配置为允许访问者帐户。</span><span class="sxs-lookup"><span data-stu-id="922e9-428">Configures Runtime settings/AssignedAccess to allow Visitor accounts.</span></span>
    1. <span data-ttu-id="922e9-429">（可选）在 MDM (运行时设置/工作区/注册) 中注册设备，以便以后可以对其进行管理。</span><span class="sxs-lookup"><span data-stu-id="922e9-429">Optionally enrolls the device in MDM (Runtime settings/Workplace/Enrollments) so that it can be managed later.</span></span>
    1. <span data-ttu-id="922e9-430">不创建本地帐户</span><span class="sxs-lookup"><span data-stu-id="922e9-430">Do not create a local account</span></span>
2. <span data-ttu-id="922e9-431">[应用设置包](https://docs.microsoft.com/hololens/hololens-provisioning)。</span><span class="sxs-lookup"><span data-stu-id="922e9-431">[Apply the provisioning package](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

##### <a name="aad-configuration"></a><span data-ttu-id="922e9-432">AAD 配置</span><span class="sxs-lookup"><span data-stu-id="922e9-432">AAD configuration</span></span>

<span data-ttu-id="922e9-433">为展台模式配置的 AAD 加入设备可以通过在登录屏幕上点击一次按钮，登录访问者帐户。</span><span class="sxs-lookup"><span data-stu-id="922e9-433">AAD joined devices configured for kiosk mode can sign in a Visitor account with a single button tap from the sign in screen.</span></span> <span data-ttu-id="922e9-434">登录到访问者帐户后，在从 "开始" 菜单中显式注销访问者或重新启动设备之前，该设备将不会提示登录。</span><span class="sxs-lookup"><span data-stu-id="922e9-434">Once signed in to the visitor account, the device will not prompt for sign in again until the Visitor is explicitly signed out from the start menu or the device is restarted.</span></span>

<span data-ttu-id="922e9-435">可以通过 [自定义 OMA URI 策略](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)来管理访问者自动登录：</span><span class="sxs-lookup"><span data-stu-id="922e9-435">Visitor Auto logon can be managed via [custom OMA-URI policy](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10):</span></span>

- <span data-ttu-id="922e9-436">URI 值：./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon</span><span class="sxs-lookup"><span data-stu-id="922e9-436">URI value: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon</span></span>


| <span data-ttu-id="922e9-437">策略</span><span class="sxs-lookup"><span data-stu-id="922e9-437">Policy</span></span> |<span data-ttu-id="922e9-438">描述</span><span class="sxs-lookup"><span data-stu-id="922e9-438">Description</span></span> |<span data-ttu-id="922e9-439">配置</span><span class="sxs-lookup"><span data-stu-id="922e9-439">Configurations</span></span> 
| --------------------------- | ------------- | -------------------- |
| <span data-ttu-id="922e9-440">MixedReality/VisitorAutoLogon</span><span class="sxs-lookup"><span data-stu-id="922e9-440">MixedReality/VisitorAutoLogon</span></span> | <span data-ttu-id="922e9-441">允许访问者自动登录到展台。</span><span class="sxs-lookup"><span data-stu-id="922e9-441">Allows for a Visitor to Auto logon to a Kiosk.</span></span> | <span data-ttu-id="922e9-442">1 (是) ，0 (否，默认值为 ) </span><span class="sxs-lookup"><span data-stu-id="922e9-442">1 (Yes), 0 (No, default.)</span></span> |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a><span data-ttu-id="922e9-443">HoloLens 的占位符开始布局</span><span class="sxs-lookup"><span data-stu-id="922e9-443">Placeholder Start layout for HoloLens</span></span>

<span data-ttu-id="922e9-444">如果使用 [预配包](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 配置多应用展台，此过程需要开始布局。</span><span class="sxs-lookup"><span data-stu-id="922e9-444">If you use a [provisioning package](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) to configure a multi-app kiosk, the procedure requires a Start layout.</span></span> <span data-ttu-id="922e9-445">Windows 全息 for Business 不支持开始布局自定义。</span><span class="sxs-lookup"><span data-stu-id="922e9-445">Start layout customization isn't supported in Windows Holographic for Business.</span></span> <span data-ttu-id="922e9-446">因此，你必须使用占位符"开始"布局。</span><span class="sxs-lookup"><span data-stu-id="922e9-446">Therefore, you'll have to use a placeholder Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="922e9-447">由于单应用展台在用户登录时启动展台应用，因此它“开始”菜单并且无需具有"开始"布局。</span><span class="sxs-lookup"><span data-stu-id="922e9-447">Because a single-app kiosk starts the kiosk app when a user signs in, it does not use a Start menu and does not have to have a Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="922e9-448">如果使用 [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 设置多应用展台，可以选择使用"启动"布局。</span><span class="sxs-lookup"><span data-stu-id="922e9-448">If you use [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) to set up a multi-app kiosk, you can optionally use a Start layout.</span></span> <span data-ttu-id="922e9-449">有关详细信息，请参阅 Intune 中 MDM ([的占位符" ](#start-layout-file-for-mdm-intune-and-others)开始"布局文件) 。</span><span class="sxs-lookup"><span data-stu-id="922e9-449">For more information, see [Placeholder Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

<span data-ttu-id="922e9-450">对于"开始"布局，将以下 **StartLayout** 部分添加到展台预配 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="922e9-450">For the Start layout, add the following **StartLayout** section to the kiosk provisioning XML file:</span></span>

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a><span data-ttu-id="922e9-451">Intune 和其他设备中 MDM (的占位符"开始") </span><span class="sxs-lookup"><span data-stu-id="922e9-451">Placeholder Start layout file for MDM (Intune and others)</span></span>

<span data-ttu-id="922e9-452">将以下示例另存为 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="922e9-452">Save the following sample as an XML file.</span></span> <span data-ttu-id="922e9-453">在 Microsoft Intune (或提供展台配置文件的另一个 MDM 服务中配置多应用展台时，可以使用) 。</span><span class="sxs-lookup"><span data-stu-id="922e9-453">You can use this file when you configure the multi-app kiosk in Microsoft Intune (or in another MDM service that provides a kiosk profile).</span></span>

> [!NOTE]
> <span data-ttu-id="922e9-454">如果必须使用自定义设置和完整的 XML 配置在 MDM 服务中设置展台，请使用预配包 的"启动布局 ["说明](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="922e9-454">If you have to use a custom setting and full XML configuration to set up a kiosk in your MDM service, use the [Start layout instructions for a provisioning package](#start-layout-for-hololens).</span></span>

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a><span data-ttu-id="922e9-455">箴。</span><span class="sxs-lookup"><span data-stu-id="922e9-455">Prov.</span></span> <span data-ttu-id="922e9-456">包，步骤 2 &ndash; 将展台配置 XML 文件添加到预配包</span><span class="sxs-lookup"><span data-stu-id="922e9-456">package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package</span></span>

1. <span data-ttu-id="922e9-457">打开 [Windows 配置设计器](https://www.microsoft.com/store/apps/9nblggh4tx22)。</span><span class="sxs-lookup"><span data-stu-id="922e9-457">Open [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span>
1. <span data-ttu-id="922e9-458">选择 **"高级预配"，** 输入项目的名称，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="922e9-458">Select **Advanced provisioning**, enter a name for your project, and then select **Next**.</span></span>
1. <span data-ttu-id="922e9-459">选择 **Windows 10 全息版，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="922e9-459">Select **Windows 10 Holographic**, and then select **Next**.</span></span>
1. <span data-ttu-id="922e9-460">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="922e9-460">Select **Finish**.</span></span> <span data-ttu-id="922e9-461">此时将打开你的程序包的工作区。</span><span class="sxs-lookup"><span data-stu-id="922e9-461">The workspace for your package opens.</span></span>
1. <span data-ttu-id="922e9-462">选择 **"运行时设置**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings"。**</span><span class="sxs-lookup"><span data-stu-id="922e9-462">Select **Runtime settings** > **AssignedAccess** > **MultiAppAssignedAccessSettings**.</span></span>
1. <span data-ttu-id="922e9-463">在中心窗格中，选择 **"浏览** "以找到并选择创建的展台配置 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="922e9-463">In the center pane, select **Browse** to locate and select the kiosk configuration XML file that you created.</span></span>

   ![Windows 配置设计器中的 MultiAppAssignedAccessSettings 字段的屏幕截图](./images/multiappassignedaccesssettings.png)

1. <span data-ttu-id="922e9-465">可选。</span><span class="sxs-lookup"><span data-stu-id="922e9-465">**Optional**.</span></span> <span data-ttu-id="922e9-466"> (如果要在设备初始设置后应用预配包，并且展台设备上已有管理员用户，请跳过此步骤。) 选择运行时设置"帐户用户"，然后创建 &gt;  &gt; 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="922e9-466">(If you want to apply the provisioning package after the initial setup of the device, and there is an admin user already available on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a user account.</span></span> <span data-ttu-id="922e9-467">提供用户名和密码，然后选择"**用户组管理员**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="922e9-467">Provide a user name and password, and then select **UserGroup** > **Administrators**.</span></span>  
  
     <span data-ttu-id="922e9-468">使用此帐户可以查看预配状态和日志。</span><span class="sxs-lookup"><span data-stu-id="922e9-468">By using this account, you can view the provisioning status and logs.</span></span>  
1. <span data-ttu-id="922e9-469">可选。</span><span class="sxs-lookup"><span data-stu-id="922e9-469">**Optional**.</span></span> <span data-ttu-id="922e9-470"> (如果你已在展台设备上拥有非管理员帐户，请跳过此步骤。 ) 选择 " **运行时设置** &gt; **帐户** &gt; **用户**"，然后创建一个本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="922e9-470">(If you already have a non-admin account on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a local user account.</span></span> <span data-ttu-id="922e9-471">确保用户名与你在配置 XML 中指定的帐户相同。</span><span class="sxs-lookup"><span data-stu-id="922e9-471">Make sure that the user name is the same as for the account that you specify in the configuration XML.</span></span> <span data-ttu-id="922e9-472">选择 **UserGroup**  >  **Standard Users**。</span><span class="sxs-lookup"><span data-stu-id="922e9-472">Select **UserGroup** > **Standard Users**.</span></span>
1. <span data-ttu-id="922e9-473">选择“文件” > “保存”。</span><span class="sxs-lookup"><span data-stu-id="922e9-473">Select **File** > **Save**.</span></span>
1. <span data-ttu-id="922e9-474">选择 "**导出**  >  **设置包**"，然后选择 "**所有者**  >  **IT 管理员**"。这会将此预配包的优先级设置为高于从其他源应用于此设备的预配包。</span><span class="sxs-lookup"><span data-stu-id="922e9-474">Select **Export** > **Provisioning package**, and then select **Owner** > **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages that are applied to this device from other sources.</span></span>
1. <span data-ttu-id="922e9-475">选择“**下一页**”。</span><span class="sxs-lookup"><span data-stu-id="922e9-475">Select **Next**.</span></span>
1. <span data-ttu-id="922e9-476">在 " **设置包安全性** " 页上，选择一个安全选项。</span><span class="sxs-lookup"><span data-stu-id="922e9-476">On the **Provisioning package security** page, select a security option.</span></span>
   > [!IMPORTANT]  
   > <span data-ttu-id="922e9-477">如果选择 " **启用包签名**"，则还必须选择用于对包进行签名的有效证书。</span><span class="sxs-lookup"><span data-stu-id="922e9-477">If you select **Enable package signing**, you also have to select a valid certificate to use for signing the package.</span></span> <span data-ttu-id="922e9-478">为此，请选择 " **浏览** "，然后选择要用于对包进行签名的证书。</span><span class="sxs-lookup"><span data-stu-id="922e9-478">To do this, select **Browse** and select the certificate that you want to use to sign the package.</span></span>
   
   > [!CAUTION]  
   > <span data-ttu-id="922e9-479">不要选择 " **启用包加密**"。</span><span class="sxs-lookup"><span data-stu-id="922e9-479">Do not select **Enable package encryption**.</span></span> <span data-ttu-id="922e9-480">在 HoloLens 设备上，此设置会导致预配失败。</span><span class="sxs-lookup"><span data-stu-id="922e9-480">On HoloLens devices, this setting causes provisioning to fail.</span></span>
1. <span data-ttu-id="922e9-481">选择“**下一页**”。</span><span class="sxs-lookup"><span data-stu-id="922e9-481">Select **Next**.</span></span>
1. <span data-ttu-id="922e9-482">指定生成时要在其中进行预配包的输出位置。</span><span class="sxs-lookup"><span data-stu-id="922e9-482">Specify the output location where you want the provisioning package to go when it's built.</span></span> <span data-ttu-id="922e9-483">默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。</span><span class="sxs-lookup"><span data-stu-id="922e9-483">By default, Windows Configuration Designer uses the project folder as the output location.</span></span> <span data-ttu-id="922e9-484">如果要更改输出位置，请选择 " **浏览**"。</span><span class="sxs-lookup"><span data-stu-id="922e9-484">If you want to change the output location, select **Browse**.</span></span> <span data-ttu-id="922e9-485">完成后，选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="922e9-485">When you are finished, select **Next**.</span></span>
1. <span data-ttu-id="922e9-486">选择 " **生成** " 开始生成包。</span><span class="sxs-lookup"><span data-stu-id="922e9-486">Select **Build** to start building the package.</span></span> <span data-ttu-id="922e9-487">无需花费太长时间即可构建设置包。</span><span class="sxs-lookup"><span data-stu-id="922e9-487">The provisioning package doesn't take long to build.</span></span> <span data-ttu-id="922e9-488">"生成" 页显示项目信息，进度栏指示生成状态。</span><span class="sxs-lookup"><span data-stu-id="922e9-488">The build page displays the project information, and the progress bar indicates the build status.</span></span>

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a><span data-ttu-id="922e9-489">预配包，步骤 3 &ndash; 将预配包应用于 HoloLens</span><span class="sxs-lookup"><span data-stu-id="922e9-489">Provisioning package, step 3 &ndash; Apply the provisioning package to HoloLens</span></span>

<span data-ttu-id="922e9-490">本文提供了在以下情况下应用预配包的详细说明：</span><span class="sxs-lookup"><span data-stu-id="922e9-490">The "Configure HoloLens by using a provisioning package" article provides detailed instructions to apply the provisioning package under the following circumstances:</span></span>

- <span data-ttu-id="922e9-491">最初可以 [在安装过程中将预配包应用于 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="922e9-491">You can initially [apply a provisioning package to HoloLens during setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).</span></span>

- <span data-ttu-id="922e9-492">你还可以 [在安装完成后将预配包应用于 HoloLens](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)。</span><span class="sxs-lookup"><span data-stu-id="922e9-492">You can also [apply a provisioning package to HoloLens after setup](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup).</span></span>

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a><span data-ttu-id="922e9-493">使用 Windows 设备门户设置单应用展台</span><span class="sxs-lookup"><span data-stu-id="922e9-493">Use the Windows Device Portal to set up a single-app kiosk</span></span>

<span data-ttu-id="922e9-494">若要使用 Windows 设备门户设置展台模式，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="922e9-494">To set up kiosk mode by using the Windows Device Portal, follow these steps.</span></span>

1. <span data-ttu-id="922e9-495">[将 HoloLens 设备设置为使用 Windows 设备门户](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)。</span><span class="sxs-lookup"><span data-stu-id="922e9-495">[Set up the HoloLens device to use the Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal).</span></span> <span data-ttu-id="922e9-496">Device Portal 是 HoloLens 上的 Web 服务器，你可以从电脑上的 Web 浏览器连接到它。</span><span class="sxs-lookup"><span data-stu-id="922e9-496">The Device Portal is a web server on your HoloLens that you can connect to from a web browser on your PC.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="922e9-497">将 HoloLens 设置为使用 设备门户，你必须在设备上启用开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="922e9-497">When you set up HoloLens to use the Device Portal, you have to enable Developer Mode on the device.</span></span> <span data-ttu-id="922e9-498">使用设备上具有Windows Holographic for Business模式，可以旁加载应用。</span><span class="sxs-lookup"><span data-stu-id="922e9-498">Developer Mode on a device that has Windows Holographic for Business enables you to side-load apps.</span></span> <span data-ttu-id="922e9-499">但是，此设置会创建一个风险，即用户可能会安装尚未通过应用程序认证Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="922e9-499">However, this setting creates a risk that a user can install apps that have not been certified by the Microsoft Store.</span></span> <span data-ttu-id="922e9-500">管理员可以使用策略 CSP 中的 **ApplicationManagement/AllowDeveloper Unlock** 设置阻止启用开发人员 [模式](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)。</span><span class="sxs-lookup"><span data-stu-id="922e9-500">Administrators can block the ability to enable Developer Mode by using the **ApplicationManagement/AllowDeveloper Unlock** setting in the [Policy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider).</span></span> [<span data-ttu-id="922e9-501">了解有关开发人员模式的详细信息。</span><span class="sxs-lookup"><span data-stu-id="922e9-501">Learn more about Developer Mode.</span></span>](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. <span data-ttu-id="922e9-502">在计算机上，使用 [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 或 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="922e9-502">On a computer, connect to the HoloLens by using [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) or [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).</span></span>

1. <span data-ttu-id="922e9-503">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="922e9-503">Do one of the following:</span></span>
   - <span data-ttu-id="922e9-504">如果是首次连接到Windows 设备门户，请 [创建用户名和密码](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span><span class="sxs-lookup"><span data-stu-id="922e9-504">If you are connecting to the Windows Device Portal for the first time, [create a user name and password](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span></span>
   - <span data-ttu-id="922e9-505">输入之前设置的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="922e9-505">Enter the user name and password that you previously set up.</span></span>

    > [!TIP]
    > <span data-ttu-id="922e9-506">如果发现浏览器中的证书错误，请遵循[以下疑难解答步骤](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)。</span><span class="sxs-lookup"><span data-stu-id="922e9-506">If you see a certificate error in the browser, follow [these troubleshooting steps](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).</span></span>

1. <span data-ttu-id="922e9-507">在"Windows 设备门户"中，选择"**展台模式"。**</span><span class="sxs-lookup"><span data-stu-id="922e9-507">In the Windows Device Portal, select **Kiosk Mode**.</span></span>

1. <span data-ttu-id="922e9-508">选择 **"启用展台模式**"，选择要在设备启动时运行的应用，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="922e9-508">Select **Enable Kiosk Mode**, select an app to run when the device starts, and then select **Save**.</span></span>

    ![展台模式](images/kiosk.png)
1. <span data-ttu-id="922e9-510&quot;>重启 HoloLens。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;922e9-510&quot;>Restart HoloLens.</span></span> <span data-ttu-id=&quot;922e9-511&quot;>如果仍处于打开状态设备门户，可以选择页面顶部的&quot;重启&quot;。 </span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;922e9-511&quot;>If you still have your Device Portal page open, you can select **Restart** at the top of the page.</span></span>

> [!NOTE]
> <span data-ttu-id=&quot;922e9-512&quot;>展台模式可以通过 设备门户 的 REST API 进行 POST 设置，对 /api/holographic/kioskmode/settings 执行 POST，其中一个必需的查询字符串参数 (&quot;kioskModeEnabled&quot;的值为&quot;true&quot;或&quot;false") ，以及一个可选参数 ("startupApp"，其值为包名称) 。</span><span class="sxs-lookup"><span data-stu-id="922e9-512">Kiosk Mode can be set via Device Portal’s REST API by doing a POST to /api/holographic/kioskmode/settings with one required query string parameter (“kioskModeEnabled” with a value of “true” or “false”) and one optional parameter (“startupApp” with a value of a package name).</span></span> <span data-ttu-id="922e9-513">请记住，设备门户仅供开发人员使用，不应在非开发人员设备上启用。</span><span class="sxs-lookup"><span data-stu-id="922e9-513">Please keep in mind that Device Portal is intended for developers only and should not be enabled on non-developer devices.</span></span> <span data-ttu-id="922e9-514">将来REST API更新/发布中，更新版本可能会更改。</span><span class="sxs-lookup"><span data-stu-id="922e9-514">The REST API is subject to change in future updates/releases.</span></span>

## <a name="more-information"></a><span data-ttu-id="922e9-515">详细信息</span><span class="sxs-lookup"><span data-stu-id="922e9-515">More information</span></span>

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a><span data-ttu-id="922e9-516">了解如何使用预配包配置展台。</span><span class="sxs-lookup"><span data-stu-id="922e9-516">Watch how to configure a kiosk by using a provisioning package.</span></span>  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a><span data-ttu-id="922e9-517">全局分配访问权限 - 展台模式</span><span class="sxs-lookup"><span data-stu-id="922e9-517">Global Assigned Access – Kiosk Mode</span></span>
- <span data-ttu-id="922e9-518">通过启用在系统级别应用展台模式的新展台方法，减少了展台的标识管理。</span><span class="sxs-lookup"><span data-stu-id="922e9-518">Reduced Identity management for Kiosk, by enabling new Kiosk method that applies Kiosk mode at the system level.</span></span>

<span data-ttu-id="922e9-519">此新功能允许 IT 管理员为多个应用展台模式配置 HoloLens 2 设备，该模式适用于系统级别，与系统上的任何标识没有关联，并且适用于登录设备的每个人。</span><span class="sxs-lookup"><span data-stu-id="922e9-519">This new feature allows an IT Admin to configure a HoloLens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> <span data-ttu-id="922e9-520">有关此新功能的更多详细信息，请参阅 [HoloLens 全局分配的访问展台](hololens-global-assigned-access-kiosk.md) 文档。</span><span class="sxs-lookup"><span data-stu-id="922e9-520">See the [HoloLens global assigned access kiosk](hololens-global-assigned-access-kiosk.md) documentation for more details on this new feature.</span></span>

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a><span data-ttu-id="922e9-521">在多应用展台模式下自动启动应用程序</span><span class="sxs-lookup"><span data-stu-id="922e9-521">Automatic launch of an application in multiple-app kiosk mode</span></span> 
- <span data-ttu-id="922e9-522">自动应用启动的聚焦体验，进一步增加了为展台模式体验选择的 UI 和应用选择。</span><span class="sxs-lookup"><span data-stu-id="922e9-522">Focused experience with automatic app launch, further increasing the UI and app selections chosen for Kiosk mode experiences.</span></span>

<span data-ttu-id="922e9-523">仅适用于多应用展台模式，并且只有1个应用可以使用下面的突出显示属性指定为自动启动。</span><span class="sxs-lookup"><span data-stu-id="922e9-523">Applies only to multiple-app kiosk mode and only 1 app can be designated to auto-launch using highlighted attribute below in Assigned Access configuration.</span></span> 

<span data-ttu-id="922e9-524">当用户登录时，应用程序将自动启动。</span><span class="sxs-lookup"><span data-stu-id="922e9-524">Application is automatically launched when user signs-in.</span></span> 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a><span data-ttu-id="922e9-525">用于处理故障的展台模式行为更改</span><span class="sxs-lookup"><span data-stu-id="922e9-525">Kiosk mode behavior changes for handling of failures</span></span>
<span data-ttu-id="922e9-526">如果在应用展台模式时遇到故障，会出现以下行为：</span><span class="sxs-lookup"><span data-stu-id="922e9-526">Upon encountering failures in applying kiosk mode, the following behavior appears:</span></span>

- <span data-ttu-id="922e9-527">在 Windows 全息版之前，版本 20H2-HoloLens 将显示 "开始" 菜单中的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="922e9-527">Prior to Windows Holographic, version 20H2 - HoloLens will show all applications in the Start menu.</span></span>
- <span data-ttu-id="922e9-528">Windows 全息，版本 20H2-如果某个设备具有展台配置，该配置是全局分配的访问权限和 AAD 组成员分配的访问权限，如果确定 AAD 组成员身份失败，则用户将看到 "不在启动时显示任何内容" 菜单。</span><span class="sxs-lookup"><span data-stu-id="922e9-528">Windows Holographic, version 20H2 - if a device has a kiosk configuration which is a combination of both global assigned access and AAD group member assigned access, if determining AAD group membership fails, the user will see “nothing shown in start” menu.</span></span>

![显示故障时的展台模式的图像。](images/hololens-kiosk-failure-behavior.png )


- <span data-ttu-id="922e9-530">从 [Windows 全息开始，版本 21H1](hololens-release-notes.md#windows-holographic-version-21h1)，展台模式将在显示空的 "开始" 菜单之前查找全局分配的访问权限。</span><span class="sxs-lookup"><span data-stu-id="922e9-530">Starting with [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), Kiosk mode looks for Global Assigned Access before showing an empty start menu.</span></span> <span data-ttu-id="922e9-531">如果) 在 AAD 组展台模式下发生故障，则展台体验将回退到全局展台配置 (。</span><span class="sxs-lookup"><span data-stu-id="922e9-531">The kiosk experience will fallback to a global kiosk configuration (if present) in case of failures during AAD group kiosk mode.</span></span>

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a><span data-ttu-id="922e9-532">缓存 Azure AD 脱机展台的组成员身份</span><span class="sxs-lookup"><span data-stu-id="922e9-532">Cache Azure AD Group membership for offline Kiosk</span></span>

- <span data-ttu-id="922e9-533">通过消除展台模式故障中的可用应用，更安全的展台模式。</span><span class="sxs-lookup"><span data-stu-id="922e9-533">More secure Kiosk mode by eliminating available apps on Kiosk mode failures.</span></span>
- <span data-ttu-id="922e9-534">已将脱机展台用于 Azure AD 组，最多60天。</span><span class="sxs-lookup"><span data-stu-id="922e9-534">Enabled Offline Kiosks to be used with Azure AD groups for up to 60 days.</span></span>

<span data-ttu-id="922e9-535">此策略控制允许使用 Azure AD 组成员身份缓存来指定已登录用户 Azure AD 组的指定访问配置的天数。</span><span class="sxs-lookup"><span data-stu-id="922e9-535">This policy controls for how many days, Azure AD group membership cache is allowed to be used for Assigned Access configurations targeting Azure AD groups for signed in user.</span></span> <span data-ttu-id="922e9-536">一旦将此策略值设置为大于0的值，则不使用缓存。</span><span class="sxs-lookup"><span data-stu-id="922e9-536">Once this policy value is set to value greater than 0 only then cache is used otherwise not.</span></span>  

<span data-ttu-id="922e9-537">名称： AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span><span class="sxs-lookup"><span data-stu-id="922e9-537">Name: AADGroupMembershipCacheValidityInDays URI value: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span></span>

<span data-ttu-id="922e9-538">最小值为0天</span><span class="sxs-lookup"><span data-stu-id="922e9-538">Min - 0 days</span></span>  
<span data-ttu-id="922e9-539">最大-60 天</span><span class="sxs-lookup"><span data-stu-id="922e9-539">Max - 60 days</span></span> 

<span data-ttu-id="922e9-540">正确使用此策略的步骤：</span><span class="sxs-lookup"><span data-stu-id="922e9-540">Steps to use this policy correctly:</span></span> 
1. <span data-ttu-id="922e9-541">为展台组创建设备配置文件，Azure AD并将其分配给 HoloLens (设备) 。</span><span class="sxs-lookup"><span data-stu-id="922e9-541">Create a device configuration profile for kiosk targeting Azure AD groups and assign it to HoloLens device(s).</span></span> 
1. <span data-ttu-id="922e9-542">创建基于 OMA URI 的自定义设备配置，将此策略值设置为所需的天数 (> 0) 并将其分配给 HoloLens () 。</span><span class="sxs-lookup"><span data-stu-id="922e9-542">Create a custom OMA URI based device configuration which sets this policy value to desired number of days (> 0) and assign it to HoloLens device(s).</span></span> 
    1. <span data-ttu-id="922e9-543">URI 值应在 OMA-URI 文本框中输入为 ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span><span class="sxs-lookup"><span data-stu-id="922e9-543">The URI value should be entered in OMA-URI text box as ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span></span>
    1. <span data-ttu-id="922e9-544">该值可以介于允许的最小值/最大值之间。</span><span class="sxs-lookup"><span data-stu-id="922e9-544">The value can be between min / max allowed.</span></span>
1. <span data-ttu-id="922e9-545">注册 HoloLens 设备，并验证这两种配置是否应用到设备。</span><span class="sxs-lookup"><span data-stu-id="922e9-545">Enroll HoloLens devices and verify both configurations get applied to the device.</span></span> 
1. <span data-ttu-id="922e9-546">在Azure AD Internet 可用时让用户 1 登录，用户登录并成功Azure AD组成员身份后，将创建缓存。</span><span class="sxs-lookup"><span data-stu-id="922e9-546">Let Azure AD user 1 sign-in when internet is available, once user signs-in and Azure AD group membership is confirmed successfully, cache will be created.</span></span> 
1. <span data-ttu-id="922e9-547">现在Azure AD用户 1 可以脱机使用 HoloLens，只要策略值允许 X 天，就可以将 HoloLens 用于展台模式。</span><span class="sxs-lookup"><span data-stu-id="922e9-547">Now Azure AD user 1 can take HoloLens offline and use it for kiosk mode as long as policy value allows for X number of days.</span></span> 
1. <span data-ttu-id="922e9-548">对于任何其他 Azure AD 用户 N，可以重复步骤 4 和 5。此处的要点是，任何 Azure AD 用户都必须使用 Internet 登录到设备，以便我们至少能够确定他们是展台配置所面向的 Azure AD 组的成员。</span><span class="sxs-lookup"><span data-stu-id="922e9-548">Steps 4 and 5 can be repeated for any other Azure AD user N. Key point here is that any Azure AD user must sign-in to device using Internet so at least once we can determine that they are member of Azure AD group to which Kiosk configuration is targeted.</span></span> 
 
> [!NOTE]
> <span data-ttu-id="922e9-549">在针对用户执行步骤 4 之前Azure AD用户将遇到"断开连接"环境中提到的失败行为。</span><span class="sxs-lookup"><span data-stu-id="922e9-549">Until step 4 is performed for a Azure AD user will experience failure behavior mentioned in “disconnected” environments.</span></span> 


## <a name="xml-kiosk-code-samples-for-hololens"></a><span data-ttu-id="922e9-550">HoloLens 的 XML 展台代码示例</span><span class="sxs-lookup"><span data-stu-id="922e9-550">XML Kiosk Code Samples for HoloLens</span></span>

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a><span data-ttu-id="922e9-551">面向单个组的多个应用展Azure AD模式。</span><span class="sxs-lookup"><span data-stu-id="922e9-551">Multiple app kiosk mode targeting an Azure AD group.</span></span> 
<span data-ttu-id="922e9-552">此展台部署一个展台，对于 Azure AD 组的用户，他们将启用一个展台，其中包括 3 个应用：设置、Remote Assist 和 反馈中心。</span><span class="sxs-lookup"><span data-stu-id="922e9-552">This kiosk deploys a Kiosk that for users in the Azure AD group, they will have a Kiosk enabled that includes the 3 apps: Settings, Remote Assist, and Feedback Hub.</span></span> <span data-ttu-id="922e9-553">若要修改此示例以立即使用，请确保更改下面突出显示的 GUID，以匹配Azure AD组。</span><span class="sxs-lookup"><span data-stu-id="922e9-553">To modify this sample to be used immediately, make sure to change the GUID highlighted below to match an Azure AD Group of your own.</span></span> 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a><span data-ttu-id="922e9-554">多个应用展台模式，Azure AD帐户。</span><span class="sxs-lookup"><span data-stu-id="922e9-554">Multiple app kiosk mode targeting Azure AD account.</span></span>
<span data-ttu-id="922e9-555">此展台为单个用户部署展台，他们将启用一个展台，其中包括 3 个应用：设置、Remote Assist和反馈中心。</span><span class="sxs-lookup"><span data-stu-id="922e9-555">This kiosk deploys a Kiosk for a single user, they will have a Kiosk enabled that includes the 3 apps: Settings, Remote Assist, and Feedback Hub.</span></span> <span data-ttu-id="922e9-556">若要修改此示例以立即使用，请确保更改下面突出显示的帐户，以匹配Azure AD帐户。</span><span class="sxs-lookup"><span data-stu-id="922e9-556">To modify this sample to be used immediately, make sure to change the account highlighted below to match an Azure AD Account of your own.</span></span> 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

