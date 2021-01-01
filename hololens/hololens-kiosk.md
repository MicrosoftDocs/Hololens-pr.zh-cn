---
title: 将 HoloLens 设置为 Kiosk
description: 使用展台配置锁定 HoloLens 上的应用。
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
ms.openlocfilehash: 777c90c4be397e176281ee72cb684a561ba78cfa
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253029"
---
# <span data-ttu-id="151df-103">将 HoloLens 设置为 Kiosk</span><span class="sxs-lookup"><span data-stu-id="151df-103">Set up HoloLens as a kiosk</span></span>

<span data-ttu-id="151df-104">你可以将 HoloLens 设备配置为在展台模式下运行，以用作固定用途的设备\*\*（也称为展台）。</span><span class="sxs-lookup"><span data-stu-id="151df-104">You can configure a HoloLens device to function as a fixed-purpose device, also called a *kiosk*, by configuring the device to run in kiosk mode.</span></span> <span data-ttu-id="151df-105">展台模式限制 (或) 设备上可用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="151df-105">Kiosk mode limits the applications (or users) that are available on the device.</span></span> <span data-ttu-id="151df-106">展台模式是一项便捷功能，可用于将 HoloLens 设备专用于业务应用，或在应用演示中使用 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="151df-106">Kiosk mode is a convenient feature that you can use to dedicate a HoloLens device to business apps, or to use the HoloLens device in an app demo.</span></span>

<span data-ttu-id="151df-107">本文提供有关特定于 HoloLens 设备的展台配置的各个方面的信息。</span><span class="sxs-lookup"><span data-stu-id="151df-107">This article provides information about aspects of kiosk configuration that are specific to HoloLens devices.</span></span> <span data-ttu-id="151df-108">有关不同类型的基于 Windows 的展台以及如何配置这些展台的常规信息，请参阅在 Windows 桌面版上配置展台和 [数字签名](https://docs.microsoft.com/windows/configuration/kiosk-methods)。</span><span class="sxs-lookup"><span data-stu-id="151df-108">For general information about the different types of Windows-based kiosks and how to configure them, see [Configure kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).</span></span>  

> [!IMPORTANT]  
> <span data-ttu-id="151df-109">展台模式确定当用户登录设备时可用的应用。</span><span class="sxs-lookup"><span data-stu-id="151df-109">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="151df-110">但是，展台模式不是一种安全方法。</span><span class="sxs-lookup"><span data-stu-id="151df-110">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="151df-111">它不会阻止"允许"应用打开不允许的另一个应用。</span><span class="sxs-lookup"><span data-stu-id="151df-111">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="151df-112">若要阻止应用或进程打开，请使用 [WDAC](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) Windows Defender应用程序 (CSP) 创建适当的策略。</span><span class="sxs-lookup"><span data-stu-id="151df-112">In order to block apps or processes from opening, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span>
>
> <span data-ttu-id="151df-113">了解有关为用户提供 HoloLens 2 使用的高级安全级别的 Microsoft 服务，详细了解状态分离和隔离 [- Defender 保护](security-state-separation-isolation.md#defender-protections)。</span><span class="sxs-lookup"><span data-stu-id="151df-113">Learn more about the Microsoft services to give users an advanced level of security that HoloLens 2 uses, read more about [State separation and isolation - Defender protections](security-state-separation-isolation.md#defender-protections).</span></span> <span data-ttu-id="151df-114">或者了解如何使用 WDAC 和 Windows PowerShell Microsoft Intune 在 [HoloLens 2 设备上允许或阻止应用](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)。</span><span class="sxs-lookup"><span data-stu-id="151df-114">Or learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="151df-115">可以在单应用或多应用配置中使用展台模式，并且可以使用三个进程之一来设置和部署展台配置。</span><span class="sxs-lookup"><span data-stu-id="151df-115">You can use kiosk mode in either a single-app or a multi-app configuration, and you can use one of three processes to set up and deploy the kiosk configuration.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="151df-116">删除多应用配置会删除分配的访问权限功能创建的用户锁定配置文件。</span><span class="sxs-lookup"><span data-stu-id="151df-116">Deleting the multi-app configuration removes the user lockdown profiles that the assigned access feature created.</span></span> <span data-ttu-id="151df-117">但是，它不会还原所有策略更改。</span><span class="sxs-lookup"><span data-stu-id="151df-117">However, it does not revert all the policy changes.</span></span> <span data-ttu-id="151df-118">若要还原这些策略，你必须将设备重置为出厂设置。</span><span class="sxs-lookup"><span data-stu-id="151df-118">To revert these policies, you have to reset the device to the factory settings.</span></span>

## <span data-ttu-id="151df-119">规划展台部署</span><span class="sxs-lookup"><span data-stu-id="151df-119">Plan the kiosk deployment</span></span>

<span data-ttu-id="151df-120">规划展台时，你需要能够回答以下问题。</span><span class="sxs-lookup"><span data-stu-id="151df-120">When planning your Kiosk you'll need to be able to answer the following questions.</span></span> <span data-ttu-id="151df-121">下面是阅读此页面时要考虑的一些决策以及这些问题的一些注意事项。</span><span class="sxs-lookup"><span data-stu-id="151df-121">Here are some decisions to think about while reading this page and some considerations for these questions.</span></span>
1. **<span data-ttu-id="151df-122">谁将使用你的展台，以及他们将 [ () 的帐户类型 ](hololens-identity.md) ？</span><span class="sxs-lookup"><span data-stu-id="151df-122">Who will be using your Kiosk, and what [type of account(s)](hololens-identity.md) will they be using?</span></span>** <span data-ttu-id="151df-123">这是你可能已做出的决定，不应为了展台而进行调整，但会影响稍后如何分配展台。</span><span class="sxs-lookup"><span data-stu-id="151df-123">This is a decision you have likely already made and shouldn't be adjusted for the sake of your Kiosk, but will affect how the Kiosk is assigned later.</span></span>
1. **<span data-ttu-id="151df-124">是否需要为每个用户/组启用不同的展台，或者没有为某些用户/组启用展台？</span><span class="sxs-lookup"><span data-stu-id="151df-124">Do you need to have either different Kiosks per user/group or a Kiosk not enabled for some?</span></span>** <span data-ttu-id="151df-125">如果是这样，你将希望通过 XML 创建展台。</span><span class="sxs-lookup"><span data-stu-id="151df-125">If so, you'll want to create your Kiosk via XML.</span></span> 
1. **<span data-ttu-id="151df-126">展台中有多少应用？</span><span class="sxs-lookup"><span data-stu-id="151df-126">How many apps will be in your Kiosk?</span></span>** <span data-ttu-id="151df-127">如果你有多个应用，则需要多应用展台。</span><span class="sxs-lookup"><span data-stu-id="151df-127">If you have more than 1 app, you'll need a multi-app Kiosk.</span></span> 
1. **<span data-ttu-id="151df-128">展 (将) 哪个应用？</span><span class="sxs-lookup"><span data-stu-id="151df-128">Which app(s) will be in your Kiosk?</span></span>** <span data-ttu-id="151df-129">请使用下面的 AUMID 列表添加除你自己的In-Box应用。</span><span class="sxs-lookup"><span data-stu-id="151df-129">Please use our list of AUMIDs below to add any In-Box apps in addition to your own.</span></span>
1. **<span data-ttu-id="151df-130">如何计划部署展台？</span><span class="sxs-lookup"><span data-stu-id="151df-130">How do you plan to deploy your Kiosk?</span></span>** <span data-ttu-id="151df-131">如果你在 MDM 中注册设备，我们建议使用 MDM 部署你的展台。</span><span class="sxs-lookup"><span data-stu-id="151df-131">If you are enrolling device in MDM then we suggest using MDM to deploy your Kiosk.</span></span> <span data-ttu-id="151df-132">如果未使用 MDM，则提供具有预配包的部署。</span><span class="sxs-lookup"><span data-stu-id="151df-132">If you are not using MDM then deployment with Provisioning Package is available.</span></span>  

### <span data-ttu-id="151df-133">展台模式要求</span><span class="sxs-lookup"><span data-stu-id="151df-133">Kiosk mode requirements</span></span>

<span data-ttu-id="151df-134">你可以配置任何 HoloLens 2 设备以使用展台模式。</span><span class="sxs-lookup"><span data-stu-id="151df-134">You can configure any HoloLens 2 device to use kiosk mode.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="151df-135">展台模式仅在设备具有 Windows Holographic for Business 时可用。</span><span class="sxs-lookup"><span data-stu-id="151df-135">Kiosk mode is available only if the device has Windows Holographic for Business.</span></span> <span data-ttu-id="151df-136">所有 HoloLens 2 设备都随 Windows Holographic for Business 一起提供，没有其他版本。</span><span class="sxs-lookup"><span data-stu-id="151df-136">All HoloLens 2 devices ship with Windows Holographic for Business and there are no other editions.</span></span> <span data-ttu-id="151df-137">每个 HoloLens 2 设备都能开箱即用运行展台模式。</span><span class="sxs-lookup"><span data-stu-id="151df-137">Every HoloLens 2 devices is able to run Kiosk mode out of the box.</span></span>
>
> <span data-ttu-id="151df-138">HoloLens (第一代) 需要在操作系统版本和操作系统版本方面进行升级。</span><span class="sxs-lookup"><span data-stu-id="151df-138">HoloLens (1st gen) devices need to be upgraded both in terms of OS build and OS edition.</span></span> <span data-ttu-id="151df-139">下面是有关将 HoloLens 第一代 (更新) [Windows Holographic for Business](hololens1-upgrade-enterprise.md) 版本的信息。</span><span class="sxs-lookup"><span data-stu-id="151df-139">Here is more information on updating a HoloLens (1st gen) to [Windows Holographic for Business](hololens1-upgrade-enterprise.md) edition.</span></span> <span data-ttu-id="151df-140">若要将 HoloLens (第一代) 设备更新为使用展台模式，必须先确保设备运行 Windows 10 版本 1803 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="151df-140">To update a HoloLens (1st gen) device to use kiosk mode, you must first make sure that the device runs Windows 10, version 1803, or a later version.</span></span> <span data-ttu-id="151df-141">如果你已使用 Windows 设备恢复工具将 HoloLens (第一代) 设备恢复到其默认版本，或者如果你已安装了最新更新，则设备已准备好进行配置。</span><span class="sxs-lookup"><span data-stu-id="151df-141">If you have used the Windows Device Recovery Tool to recover your HoloLens (1st gen) device to its default build, or if you have installed the most recent updates, your device is ready to configure.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="151df-142">若要帮助保护在展台模式下运行的设备，请考虑添加关闭 USB 连接等功能的设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="151df-142">To help protect devices that run in kiosk mode, consider adding device management policies that turn off features such as USB connectivity.</span></span> <span data-ttu-id="151df-143">此外，请检查更新圈设置以确保在工作时间不会发生自动更新。</span><span class="sxs-lookup"><span data-stu-id="151df-143">Additionally, check your update ring settings to make sure that automatic updates do not occur during business hours.</span></span>

### <span data-ttu-id="151df-144">在单应用展台或多应用展台之间做出决定</span><span class="sxs-lookup"><span data-stu-id="151df-144">Decide between a single-app kiosk or a multi-app kiosk</span></span>

<span data-ttu-id="151df-145">当用户登录设备时，单应用展台将启动指定的应用。</span><span class="sxs-lookup"><span data-stu-id="151df-145">A single-app kiosk starts the specified app when the user signs in to the device.</span></span> <span data-ttu-id="151df-146">"开始"菜单被禁用，就像 Cortana 一样。</span><span class="sxs-lookup"><span data-stu-id="151df-146">The Start menu is disabled, as is Cortana.</span></span> <span data-ttu-id="151df-147">HoloLens 2 设备不响应"开始 ["手势](hololens2-basic-usage.md#start-gesture) 。</span><span class="sxs-lookup"><span data-stu-id="151df-147">A HoloLens 2 device does not respond to the [Start](hololens2-basic-usage.md#start-gesture) gesture.</span></span> <span data-ttu-id="151df-148">HoloLens (第一代) 设备不响应"放 [红"](hololens1-basic-usage.md) 手势。</span><span class="sxs-lookup"><span data-stu-id="151df-148">A HoloLens (1st gen) device does not respond to the [bloom](hololens1-basic-usage.md) gesture.</span></span> <span data-ttu-id="151df-149">因为只有一个应用可以运行，所以用户不能放置其他应用。</span><span class="sxs-lookup"><span data-stu-id="151df-149">Because only one app can run, the user cannot place other apps.</span></span>

<span data-ttu-id="151df-150">当用户登录设备时，多应用展台将显示"开始"菜单。</span><span class="sxs-lookup"><span data-stu-id="151df-150">A multi-app kiosk displays the Start menu when the user signs in to the device.</span></span> <span data-ttu-id="151df-151">展台配置确定哪些应用在"开始"菜单上可用。</span><span class="sxs-lookup"><span data-stu-id="151df-151">The kiosk configuration determines which apps are available on the Start menu.</span></span> <span data-ttu-id="151df-152">可以使用多应用展台为用户提供易于理解的体验，只需向用户呈现他们必须使用的事情，并删除他们不需要使用的事情。</span><span class="sxs-lookup"><span data-stu-id="151df-152">You can use a multi-app kiosk to provide an easy-to-understand experience for users by presenting to them only the things that they have to use, and removing the things they don't need to use.</span></span>

<span data-ttu-id="151df-153">下表列出了不同展台模式中的功能。</span><span class="sxs-lookup"><span data-stu-id="151df-153">The following table lists the feature capabilities in the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="151df-154">“开始”菜单</span><span class="sxs-lookup"><span data-stu-id="151df-154">Start menu</span></span> |<span data-ttu-id="151df-155">快速操作菜单</span><span class="sxs-lookup"><span data-stu-id="151df-155">Quick Actions menu</span></span> |<span data-ttu-id="151df-156">相机和视频</span><span class="sxs-lookup"><span data-stu-id="151df-156">Camera and video</span></span> |<span data-ttu-id="151df-157">Miracast</span><span class="sxs-lookup"><span data-stu-id="151df-157">Miracast</span></span> |<span data-ttu-id="151df-158">Cortana</span><span class="sxs-lookup"><span data-stu-id="151df-158">Cortana</span></span> |<span data-ttu-id="151df-159">内置语音命令</span><span class="sxs-lookup"><span data-stu-id="151df-159">Built-in voice commands</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|<span data-ttu-id="151df-160">单应用展台</span><span class="sxs-lookup"><span data-stu-id="151df-160">Single-app kiosk</span></span> |<span data-ttu-id="151df-161">已禁用</span><span class="sxs-lookup"><span data-stu-id="151df-161">Disabled</span></span> |<span data-ttu-id="151df-162">已禁用</span><span class="sxs-lookup"><span data-stu-id="151df-162">Disabled</span></span>   |<span data-ttu-id="151df-163">已禁用</span><span class="sxs-lookup"><span data-stu-id="151df-163">Disabled</span></span> |<span data-ttu-id="151df-164">已禁用</span><span class="sxs-lookup"><span data-stu-id="151df-164">Disabled</span></span>   |<span data-ttu-id="151df-165">已禁用</span><span class="sxs-lookup"><span data-stu-id="151df-165">Disabled</span></span> |<span data-ttu-id="151df-166">已启用 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="151df-166">Enabled<sup>1</span></span></sup> |
|<span data-ttu-id="151df-167">多应用展台。</span><span class="sxs-lookup"><span data-stu-id="151df-167">Multi-app kiosk</span></span> |<span data-ttu-id="151df-168">启用</span><span class="sxs-lookup"><span data-stu-id="151df-168">Enabled</span></span> |<span data-ttu-id="151df-169">已启用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="151df-169">Enabled<sup>2</span></span></sup> |<span data-ttu-id="151df-170">可用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="151df-170">Available<sup>2</span></span></sup> |<span data-ttu-id="151df-171">可用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="151df-171">Available<sup>2</span></span></sup> |<span data-ttu-id="151df-172">可用 <sup> 2、3</span><span class="sxs-lookup"><span data-stu-id="151df-172">Available<sup>2, 3</span></span></sup>  |<span data-ttu-id="151df-173">已启用 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="151df-173">Enabled<sup>1</span></span></sup> |

> <sup><span data-ttu-id="151df-174">1 </sup> 与已禁用功能相关的语音命令无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="151df-174">1</sup> Voice commands that relate to disabled features do not function.</span></span>  
> <sup><span data-ttu-id="151df-175">2 </sup> 若要详细了解如何配置这些功能，请参阅["选择展台应用"。](#plan-kiosk-apps)</span><span class="sxs-lookup"><span data-stu-id="151df-175">2</sup> For more information about how to configure these features, see [Select kiosk apps](#plan-kiosk-apps).</span></span>  
> <sup><span data-ttu-id="151df-176">3 </sup> 即使禁用 Cortana，内置语音命令也处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="151df-176">3</sup> Even if Cortana is disabled, the built-in voice commands are enabled.</span></span>

<span data-ttu-id="151df-177">下表列出了不同展台模式的用户支持功能。</span><span class="sxs-lookup"><span data-stu-id="151df-177">The following table lists the user support features of the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="151df-178">支持的用户类型</span><span class="sxs-lookup"><span data-stu-id="151df-178">Supported user types</span></span> | <span data-ttu-id="151df-179">自动登录</span><span class="sxs-lookup"><span data-stu-id="151df-179">Automatic sign-in</span></span> | <span data-ttu-id="151df-180">多个访问级别</span><span class="sxs-lookup"><span data-stu-id="151df-180">Multiple access levels</span></span> |
| --- | --- | --- | --- |
|<span data-ttu-id="151df-181">单应用展台</span><span class="sxs-lookup"><span data-stu-id="151df-181">Single-app kiosk</span></span> |<span data-ttu-id="151df-182">Azure Active Directory (Azure) 或本地帐户 (托管服务) MSA 帐户</span><span class="sxs-lookup"><span data-stu-id="151df-182">Managed Service Account (MSA) in Azure Active Directory (Azure AD) or local account</span></span> |<span data-ttu-id="151df-183">是</span><span class="sxs-lookup"><span data-stu-id="151df-183">Yes</span></span> |<span data-ttu-id="151df-184">否</span><span class="sxs-lookup"><span data-stu-id="151df-184">No</span></span> |
|<span data-ttu-id="151df-185">多应用展台。</span><span class="sxs-lookup"><span data-stu-id="151df-185">Multi-app kiosk</span></span> |<span data-ttu-id="151df-186">Azure AD 帐户</span><span class="sxs-lookup"><span data-stu-id="151df-186">Azure AD account</span></span> |<span data-ttu-id="151df-187">否</span><span class="sxs-lookup"><span data-stu-id="151df-187">No</span></span> |<span data-ttu-id="151df-188">是</span><span class="sxs-lookup"><span data-stu-id="151df-188">Yes</span></span> |

<span data-ttu-id="151df-189">有关如何使用这些功能的示例，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="151df-189">For examples of how to use these capabilities, see the following table.</span></span>

|<span data-ttu-id="151df-190">将单应用展台用于：</span><span class="sxs-lookup"><span data-stu-id="151df-190">Use a single-app kiosk for:</span></span> |<span data-ttu-id="151df-191">将多应用展台用于：</span><span class="sxs-lookup"><span data-stu-id="151df-191">Use a multi-app kiosk for:</span></span> |
| --- | --- |
|<span data-ttu-id="151df-192">仅为新员工运行 Dynamics 365 指南的设备。</span><span class="sxs-lookup"><span data-stu-id="151df-192">A device that runs only a Dynamics 365 Guide for new employees.</span></span> |<span data-ttu-id="151df-193">为一系列员工运行指南和远程协助的设备。</span><span class="sxs-lookup"><span data-stu-id="151df-193">A device that runs both Guides and Remote Assistance for a range of employees.</span></span> |
|<span data-ttu-id="151df-194">仅运行自定义应用的设备。</span><span class="sxs-lookup"><span data-stu-id="151df-194">A device that runs only a custom app.</span></span> |<span data-ttu-id="151df-195">作为大多数用户的展台的设备 (运行自定义应用) ，但用作特定组用户的标准设备。</span><span class="sxs-lookup"><span data-stu-id="151df-195">A device that functions as a kiosk for most users (running only a custom app), but functions as a standard device for a specific group of users.</span></span> |

### <span data-ttu-id="151df-196">规划展台应用</span><span class="sxs-lookup"><span data-stu-id="151df-196">Plan kiosk apps</span></span>

<span data-ttu-id="151df-197">有关如何选择展台应用的常规信息，请参阅有关在展台模式下选择分配的访问权限的应用 ([指南) 。 ](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)</span><span class="sxs-lookup"><span data-stu-id="151df-197">For general information about how to choose kiosk apps, see [Guidelines for choosing an app for assigned access (kiosk mode)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).</span></span>

<span data-ttu-id="151df-198">如果使用 Windows Device Portal 配置单应用展台，请在安装过程中选择该应用。</span><span class="sxs-lookup"><span data-stu-id="151df-198">If you use the Windows Device Portal to configure a single-app kiosk, you select the app during the setup process.</span></span>  

<span data-ttu-id="151df-199">如果使用移动设备管理 (MDM) 系统或预配包配置展台模式，请使用 [AssignedAccess ](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 配置服务提供程序 (CSP) 来指定应用程序。</span><span class="sxs-lookup"><span data-stu-id="151df-199">If you use a Mobile Device Management (MDM) system or a provisioning package to configure kiosk mode, you use the [AssignedAccess Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) to specify applications.</span></span> <span data-ttu-id="151df-200">CSP 使用 [应用程序用户模型 ID (AUMID) ](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 标识应用程序。</span><span class="sxs-lookup"><span data-stu-id="151df-200">The CSP uses [Application User Model IDs (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) to identify applications.</span></span> <span data-ttu-id="151df-201">下表列出了可在多应用展台中使用的一些 In-box 应用程序的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="151df-201">The following table lists the AUMIDs of some in-box applications that you can use in a multi-app kiosk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="151df-202">展台模式确定当用户登录设备时可用的应用。</span><span class="sxs-lookup"><span data-stu-id="151df-202">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="151df-203">但是，展台模式不是一种安全方法。</span><span class="sxs-lookup"><span data-stu-id="151df-203">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="151df-204">它不会阻止"允许"应用打开不允许的另一个应用。</span><span class="sxs-lookup"><span data-stu-id="151df-204">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="151df-205">因为我们不限制此行为，所以应用仍可从 Edge、文件资源管理器和 Microsoft Store 应用启动。</span><span class="sxs-lookup"><span data-stu-id="151df-205">Because we do not restrict this behavior, apps can still be launched from Edge, File explorer, and the Microsoft Store apps.</span></span> <span data-ttu-id="151df-206">如果不希望从展台启动特定应用，请使用 [WDAC](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) Windows Defender CSP (应用程序控制) 创建相应的策略。</span><span class="sxs-lookup"><span data-stu-id="151df-206">If there are specific apps you don't want launched from a Kiosk, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span> 
> 
> <span data-ttu-id="151df-207">此外，混合现实主页无法设置为网亭应用。</span><span class="sxs-lookup"><span data-stu-id="151df-207">In addition, the Mixed Reality Home is not able to be set as a kiosk app.</span></span>

<a id="aumids"></a>

|<span data-ttu-id="151df-208">应用名称</span><span class="sxs-lookup"><span data-stu-id="151df-208">App Name</span></span> |<span data-ttu-id="151df-209">AUMID</span><span class="sxs-lookup"><span data-stu-id="151df-209">AUMID</span></span> |
| --- | --- |
|<span data-ttu-id="151df-210">3D 查看器</span><span class="sxs-lookup"><span data-stu-id="151df-210">3D Viewer</span></span> |<span data-ttu-id="151df-211">Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\！Microsoft.Microsoft3DViewer</span><span class="sxs-lookup"><span data-stu-id="151df-211">Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\!Microsoft.Microsoft3DViewer</span></span> |
|<span data-ttu-id="151df-212">日历</span><span class="sxs-lookup"><span data-stu-id="151df-212">Calendar</span></span> |<span data-ttu-id="151df-213">microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\！microsoft.windowslive.calendar</span><span class="sxs-lookup"><span data-stu-id="151df-213">microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar</span></span> |
|<span data-ttu-id="151df-214">相机 <sup> 1、2</span><span class="sxs-lookup"><span data-stu-id="151df-214">Camera<sup>1, 2</span></span></sup> |<span data-ttu-id="151df-215">HoloCamera\_cw5n1h2txyewy\！HoloCamera</span><span class="sxs-lookup"><span data-stu-id="151df-215">HoloCamera\_cw5n1h2txyewy\!HoloCamera</span></span> |
|<span data-ttu-id="151df-216">Cortana <sup> 3</span><span class="sxs-lookup"><span data-stu-id="151df-216">Cortana<sup>3</span></span></sup> |<span data-ttu-id="151df-217">Microsoft.549981C3F5F10\_8wekyb3d8bbwe\！应用</span><span class="sxs-lookup"><span data-stu-id="151df-217">Microsoft.549981C3F5F10\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="151df-218">HoloLens 上的设备选取器 (第一代) </span><span class="sxs-lookup"><span data-stu-id="151df-218">Device Picker on HoloLens (1st gen)</span></span> |<span data-ttu-id="151df-219">HoloDevicesFlow\_cw5n1h2txyewy\！HoloDevicesFlow</span><span class="sxs-lookup"><span data-stu-id="151df-219">HoloDevicesFlow\_cw5n1h2txyewy\!HoloDevicesFlow</span></span> |
|<span data-ttu-id="151df-220">HoloLens 2 上的设备选取器</span><span class="sxs-lookup"><span data-stu-id="151df-220">Device Picker on HoloLens 2</span></span> |<span data-ttu-id="151df-221">Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\！Microsoft.Windows.DevicesFlowHost</span><span class="sxs-lookup"><span data-stu-id="151df-221">Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\!Microsoft.Windows.DevicesFlowHost</span></span> |
|<span data-ttu-id="151df-222">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="151df-222">Dynamics 365 Guides</span></span> |<span data-ttu-id="151df-223">Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\！MicrosoftGuides</span><span class="sxs-lookup"><span data-stu-id="151df-223">Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\!MicrosoftGuides</span></span> |
|<span data-ttu-id="151df-224">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="151df-224">Dynamics 365 Remote Assist</span></span> |<span data-ttu-id="151df-225">Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\！Microsoft.RemoteAssist</span><span class="sxs-lookup"><span data-stu-id="151df-225">Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\!Microsoft.RemoteAssist</span></span> |
|<span data-ttu-id="151df-226">反馈 &nbsp; 中心</span><span class="sxs-lookup"><span data-stu-id="151df-226">Feedback&nbsp;Hub</span></span> |<span data-ttu-id="151df-227">Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\！应用</span><span class="sxs-lookup"><span data-stu-id="151df-227">Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="151df-228">文件资源管理器</span><span class="sxs-lookup"><span data-stu-id="151df-228">File Explorer</span></span> |<span data-ttu-id="151df-229">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span><span class="sxs-lookup"><span data-stu-id="151df-229">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span></span> |
|<span data-ttu-id="151df-230">Mail</span><span class="sxs-lookup"><span data-stu-id="151df-230">Mail</span></span> |<span data-ttu-id="151df-231">microsoft.windowscommunicationsapps_8wekyb3d8bbwe！microsoft.windowslive.mail</span><span class="sxs-lookup"><span data-stu-id="151df-231">microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail</span></span> |
|<span data-ttu-id="151df-232">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="151df-232">Microsoft Store</span></span> |<span data-ttu-id="151df-233">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span><span class="sxs-lookup"><span data-stu-id="151df-233">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span></span> |
|<span data-ttu-id="151df-234">Miracast <sup> 4</span><span class="sxs-lookup"><span data-stu-id="151df-234">Miracast<sup>4</span></span></sup> |&nbsp; |
|<span data-ttu-id="151df-235">电影和电视</span><span class="sxs-lookup"><span data-stu-id="151df-235">Movies & TV</span></span> |<span data-ttu-id="151df-236">Microsoft.ZuneVideo\_8wekyb3d8bbwe\！Microsoft.ZuneVideo</span><span class="sxs-lookup"><span data-stu-id="151df-236">Microsoft.ZuneVideo\_8wekyb3d8bbwe\!Microsoft.ZuneVideo</span></span> |
|<span data-ttu-id="151df-237">OneDrive</span><span class="sxs-lookup"><span data-stu-id="151df-237">OneDrive</span></span> |<span data-ttu-id="151df-238">microsoft.microsoftskydrive\_8wekyb3d8bbwe\！应用</span><span class="sxs-lookup"><span data-stu-id="151df-238">microsoft.microsoftskydrive\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="151df-239">照片</span><span class="sxs-lookup"><span data-stu-id="151df-239">Photos</span></span> |<span data-ttu-id="151df-240">Microsoft.Windows.Photos\_8wekyb3d8bbwe\！应用</span><span class="sxs-lookup"><span data-stu-id="151df-240">Microsoft.Windows.Photos\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="151df-241">“设置”</span><span class="sxs-lookup"><span data-stu-id="151df-241">Settings</span></span> |<span data-ttu-id="151df-242">HolographicSystemSettings\_cw5n1h2txyewy\！应用</span><span class="sxs-lookup"><span data-stu-id="151df-242">HolographicSystemSettings\_cw5n1h2txyewy\!App</span></span> |
|<span data-ttu-id="151df-243">提示</span><span class="sxs-lookup"><span data-stu-id="151df-243">Tips</span></span> |<span data-ttu-id="151df-244">Microsoft.HoloLensTips\_8wekyb3d8bbwe\！HoloLensTips</span><span class="sxs-lookup"><span data-stu-id="151df-244">Microsoft.HoloLensTips\_8wekyb3d8bbwe\!HoloLensTips</span></span> |

> <sup><span data-ttu-id="151df-245">1 </sup> 若要启用照片或视频捕获，你必须将相机应用启用为展台应用。</span><span class="sxs-lookup"><span data-stu-id="151df-245">1</sup> To enable photo or video capture, you have to enable the Camera app as a kiosk app.</span></span>  
> <sup><span data-ttu-id="151df-246">2 </sup> 当你启用相机应用时，请注意以下条件：</span><span class="sxs-lookup"><span data-stu-id="151df-246">2</sup> When you enable the Camera app, be aware of the following conditions:</span></span>
> - <span data-ttu-id="151df-247">"快速操作"菜单包括"照片和视频"按钮。</span><span class="sxs-lookup"><span data-stu-id="151df-247">The Quick Actions menu includes the Photo and Video buttons.</span></span>  
> - <span data-ttu-id="151df-248">你还应启用可与图片 (或检索图片) 例如照片、邮件或 OneDrive 应用。</span><span class="sxs-lookup"><span data-stu-id="151df-248">You should also enable an app (such as Photos, Mail, or OneDrive) that can interact with or retrieve pictures.</span></span>  
>  
> <sup><span data-ttu-id="151df-249">3 </sup> 即使你未启用 Cortana 作为网亭应用，内置语音命令也已启用。</span><span class="sxs-lookup"><span data-stu-id="151df-249">3</sup> Even if you do not enable Cortana as a kiosk app, built-in voice commands are enabled.</span></span> <span data-ttu-id="151df-250">但是，与已禁用功能相关的命令不起作用。</span><span class="sxs-lookup"><span data-stu-id="151df-250">However, commands that are related to disabled features have no effect.</span></span>  
> <sup><span data-ttu-id="151df-251">4 </sup> 不能直接启用 Miracast。</span><span class="sxs-lookup"><span data-stu-id="151df-251">4</sup> You cannot enable Miracast directly.</span></span> <span data-ttu-id="151df-252">若要将 Miracast 启用为展台应用，请启用相机应用和设备选取器应用。</span><span class="sxs-lookup"><span data-stu-id="151df-252">To enable Miracast as a kiosk app enable the Camera app and the Device Picker app.</span></span>

### <span data-ttu-id="151df-253">为用户或组规划展台配置文件</span><span class="sxs-lookup"><span data-stu-id="151df-253">Plan kiosk profiles for users or groups</span></span>

<span data-ttu-id="151df-254">创建 xml 文件或使用 Intune 的 UI 设置展台时，需要考虑谁将成为展台的用户。</span><span class="sxs-lookup"><span data-stu-id="151df-254">When either creating the xml file or using Intune’s UI to set up a Kiosk you’ll need to consider who will be user the Kiosk.</span></span> <span data-ttu-id="151df-255">展台配置可以限制为单个帐户或 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="151df-255">A Kiosk configuration can be limited to either an individual account or Azure AD groups.</span></span> 

<span data-ttu-id="151df-256">通常为用户或用户组启用展台。</span><span class="sxs-lookup"><span data-stu-id="151df-256">Typically Kiosks are enabled for either a user, or user group.</span></span> <span data-ttu-id="151df-257">但是，如果你计划编写自己的 XML 展台，则你可能要考虑全局分配的访问权限，其中展台在设备级别应用，而不考虑标识。</span><span class="sxs-lookup"><span data-stu-id="151df-257">However if you plan on writing your own XML Kiosk, then you may want to consider Global Assigned Access, in which the Kiosk is applied at the device level regardless of Identity.</span></span> <span data-ttu-id="151df-258">如果吸引你阅读 [有关全局分配的访问权限展台的更多内容。](hololens-global-assigned-access-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="151df-258">If this appeals to you [read more about Global Assigned Access Kiosks.](hololens-global-assigned-access-kiosk.md)</span></span>

#### <span data-ttu-id="151df-259">如果要创建 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="151df-259">If you are creating an XML file:</span></span>
-   <span data-ttu-id="151df-260">许多用户创建多个展台配置文件，并将每个配置文件分配给不同的用户/组。</span><span class="sxs-lookup"><span data-stu-id="151df-260">You many create multiple Kiosk profiles, and assign each to different users/groups.</span></span> <span data-ttu-id="151df-261">例如，Azure AD 组的展台（具有多个应用）和具有多个应用展台且应用单数的访问者。</span><span class="sxs-lookup"><span data-stu-id="151df-261">Such as a Kiosk for your Azure AD Group that has many apps, and a Visitor that has a multiple app kiosk with a singular app.</span></span>
-   <span data-ttu-id="151df-262">展台配置将被称为配置文件 **ID，** 并且具有 GUID。</span><span class="sxs-lookup"><span data-stu-id="151df-262">Your kiosk configuration will be called a **Profile Id** and have a GUID.</span></span>
-   <span data-ttu-id="151df-263">通过指定用户类型并将相同的 GUID 用于 **DefaultProfile Id，** 你将在"配置"部分分配该配置文件。</span><span class="sxs-lookup"><span data-stu-id="151df-263">You will assign that Profile in the configs section by specifying the user type and using the same GUID for the **DefaultProfile Id**.</span></span>
- <span data-ttu-id="151df-264">XML 文件可以通过 MDM 创建但仍应用于设备，方法为创建自定义 OMA URI 设备配置文件，然后使用 URI 值将其应用到 HoloLens 设备组：./Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="151df-264">A XML file can be created but still applied to a device via MDM by creating a custom OMA URI device configuration profile and applying it to HoloLens device group using the URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

#### <span data-ttu-id="151df-265">如果你在 Intune 中创建展台。</span><span class="sxs-lookup"><span data-stu-id="151df-265">If you are creating a Kiosk in Intune.</span></span>
-   <span data-ttu-id="151df-266">每台设备只能接收一个展台配置文件，否则将产生冲突，并没有任何展台配置。</span><span class="sxs-lookup"><span data-stu-id="151df-266">Each device may only receive a single Kiosk profile, otherwise it will create a conflict and receive no Kiosk configurations at all.</span></span> 
    -   <span data-ttu-id="151df-267">其他类型的配置文件和策略（如与展台配置文件不相关的设备限制）不会与展台配置文件冲突。</span><span class="sxs-lookup"><span data-stu-id="151df-267">Other kinds of profiles and policies, such as device restrictions that are not related to the kiosk configuration profile, do not conflict with the kiosk configuration profile.</span></span>
-   <span data-ttu-id="151df-268">将为属于用户登录类型的所有用户启用展台，这将使用用户或 Azure AD 组进行设置。</span><span class="sxs-lookup"><span data-stu-id="151df-268">The Kiosk will be enabled for all users who are a part of the User logon type, this will be set with a user or Azure AD group.</span></span> 
-   <span data-ttu-id="151df-269">在设置展台配置和用户登录 **类型 (选择** 可以登录到展台) 且应用的用户，仍必须将设备配置分配给组。</span><span class="sxs-lookup"><span data-stu-id="151df-269">After the Kiosk configuration is set and the **User logon type** (users who can log into the Kiosk) and the Apps are selected, the Device Configuration must still be assigned to a group.</span></span> <span data-ttu-id="151df-270">已分配 (组) 确定哪些设备接收网亭设备配置，但是，如果展台已启用，则不与之交互。</span><span class="sxs-lookup"><span data-stu-id="151df-270">The Assigned group(s) determines which devices receive the Kiosk device configuration, however does not interact with if the Kiosk is enabled or not.</span></span> 
    - <span data-ttu-id="151df-271">有关在 Intune 中分配配置文件的效果的完全讨论，请参阅在 [Microsoft Intune 中分配用户和设备配置文件](https://docs.microsoft.com/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="151df-271">For a full discussion of the effects of assigning configuration profiles in Intune, see [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).</span></span>

### <span data-ttu-id="151df-272">选择部署方法</span><span class="sxs-lookup"><span data-stu-id="151df-272">Select a deployment method</span></span>

<span data-ttu-id="151df-273">可以选择以下方法之一来部署展台配置：</span><span class="sxs-lookup"><span data-stu-id="151df-273">You can select one of the following methods to deploy kiosk configurations:</span></span>

- [<span data-ttu-id="151df-274">Microsoft Intune 或其他移动设备管理 (MDM) 服务</span><span class="sxs-lookup"><span data-stu-id="151df-274">Microsoft Intune or other mobile device management (MDM) service</span></span>](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="151df-275">设置包</span><span class="sxs-lookup"><span data-stu-id="151df-275">Provisioning package</span></span>](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="151df-276">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="151df-276">Windows Device Portal</span></span>](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > <span data-ttu-id="151df-277">由于此方法要求在设备上启用开发人员模式，因此我们建议你仅将它用于演示。</span><span class="sxs-lookup"><span data-stu-id="151df-277">Because this method requires that Developer Mode be enabled on the device, we recommend that you use it only for demonstrations.</span></span>

<span data-ttu-id="151df-278">下表列出了每个部署方法的功能和优点。</span><span class="sxs-lookup"><span data-stu-id="151df-278">The following table lists the capabilities and benefits of each of the deployment methods.</span></span>

| &nbsp; |<span data-ttu-id="151df-279">使用 Windows Device Portal 部署</span><span class="sxs-lookup"><span data-stu-id="151df-279">Deploy by using Windows Device Portal</span></span> |<span data-ttu-id="151df-280">使用预配包进行部署</span><span class="sxs-lookup"><span data-stu-id="151df-280">Deploy by using a provisioning package</span></span> |<span data-ttu-id="151df-281">使用 MDM 部署</span><span class="sxs-lookup"><span data-stu-id="151df-281">Deploy by using MDM</span></span> |
| --------------------------- | ------------- | -------------------- | ---- |
|<span data-ttu-id="151df-282">部署单应用展台</span><span class="sxs-lookup"><span data-stu-id="151df-282">Deploy single-app kiosks</span></span>   | <span data-ttu-id="151df-283">是</span><span class="sxs-lookup"><span data-stu-id="151df-283">Yes</span></span>           | <span data-ttu-id="151df-284">是</span><span class="sxs-lookup"><span data-stu-id="151df-284">Yes</span></span>                  | <span data-ttu-id="151df-285">是</span><span class="sxs-lookup"><span data-stu-id="151df-285">Yes</span></span>  |
|<span data-ttu-id="151df-286">部署多应用展台</span><span class="sxs-lookup"><span data-stu-id="151df-286">Deploy multi-app kiosks</span></span>    | <span data-ttu-id="151df-287">否</span><span class="sxs-lookup"><span data-stu-id="151df-287">No</span></span>            | <span data-ttu-id="151df-288">是</span><span class="sxs-lookup"><span data-stu-id="151df-288">Yes</span></span>                  | <span data-ttu-id="151df-289">是</span><span class="sxs-lookup"><span data-stu-id="151df-289">Yes</span></span>  |
|<span data-ttu-id="151df-290">仅部署到本地设备</span><span class="sxs-lookup"><span data-stu-id="151df-290">Deploy to local devices only</span></span> | <span data-ttu-id="151df-291">是</span><span class="sxs-lookup"><span data-stu-id="151df-291">Yes</span></span>           | <span data-ttu-id="151df-292">是</span><span class="sxs-lookup"><span data-stu-id="151df-292">Yes</span></span>                  | <span data-ttu-id="151df-293">否</span><span class="sxs-lookup"><span data-stu-id="151df-293">No</span></span>   |
|<span data-ttu-id="151df-294">使用开发人员模式部署</span><span class="sxs-lookup"><span data-stu-id="151df-294">Deploy by using Developer Mode</span></span> |<span data-ttu-id="151df-295">必需</span><span class="sxs-lookup"><span data-stu-id="151df-295">Required</span></span>       | <span data-ttu-id="151df-296">不需要</span><span class="sxs-lookup"><span data-stu-id="151df-296">Not required</span></span>            | <span data-ttu-id="151df-297">不需要</span><span class="sxs-lookup"><span data-stu-id="151df-297">Not required</span></span>   |
|<span data-ttu-id="151df-298">使用 Azure Active Directory (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="151df-298">Deploy by using Azure Active Directory (Azure AD)</span></span>  | <span data-ttu-id="151df-299">不需要</span><span class="sxs-lookup"><span data-stu-id="151df-299">Not required</span></span>            | <span data-ttu-id="151df-300">不需要</span><span class="sxs-lookup"><span data-stu-id="151df-300">Not required</span></span>                   | <span data-ttu-id="151df-301">必需</span><span class="sxs-lookup"><span data-stu-id="151df-301">Required</span></span>  |
|<span data-ttu-id="151df-302">自动部署</span><span class="sxs-lookup"><span data-stu-id="151df-302">Deploy automatically</span></span>      | <span data-ttu-id="151df-303">否</span><span class="sxs-lookup"><span data-stu-id="151df-303">No</span></span>            | <span data-ttu-id="151df-304">否</span><span class="sxs-lookup"><span data-stu-id="151df-304">No</span></span>                   | <span data-ttu-id="151df-305">是</span><span class="sxs-lookup"><span data-stu-id="151df-305">Yes</span></span>  |
|<span data-ttu-id="151df-306">部署速度</span><span class="sxs-lookup"><span data-stu-id="151df-306">Deployment speed</span></span>            | <span data-ttu-id="151df-307">迅速</span><span class="sxs-lookup"><span data-stu-id="151df-307">Fast</span></span>       | <span data-ttu-id="151df-308">迅速</span><span class="sxs-lookup"><span data-stu-id="151df-308">Fast</span></span>                 | <span data-ttu-id="151df-309">慢速</span><span class="sxs-lookup"><span data-stu-id="151df-309">Slow</span></span> |
|<span data-ttu-id="151df-310">大规模部署</span><span class="sxs-lookup"><span data-stu-id="151df-310">Deploy at scale</span></span> | <span data-ttu-id="151df-311">不建议</span><span class="sxs-lookup"><span data-stu-id="151df-311">Not recommended</span></span>    | <span data-ttu-id="151df-312">推荐</span><span class="sxs-lookup"><span data-stu-id="151df-312">Recommended</span></span>        | <span data-ttu-id="151df-313">推荐</span><span class="sxs-lookup"><span data-stu-id="151df-313">Recommended</span></span> |

## <span data-ttu-id="151df-314">使用 Microsoft Intune 或其他 MDM 设置单应用或多应用展台</span><span class="sxs-lookup"><span data-stu-id="151df-314">Use Microsoft Intune or other MDM to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="151df-315">若要使用 Microsoft Intune 或其他 MDM 系统设置展台模式，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="151df-315">To set up kiosk mode by using Microsoft Intune or another MDM system, follow these steps.</span></span>

1. <span data-ttu-id="151df-316">[准备注册设备](#mdmenroll)。</span><span class="sxs-lookup"><span data-stu-id="151df-316">[Prepare to enroll the devices](#mdmenroll).</span></span>
1. <span data-ttu-id="151df-317">[创建展台配置文件](#mdmprofile)。</span><span class="sxs-lookup"><span data-stu-id="151df-317">[Create a kiosk configuration profile](#mdmprofile).</span></span>
1. <span data-ttu-id="151df-318">配置展台。</span><span class="sxs-lookup"><span data-stu-id="151df-318">Configure the kiosk.</span></span>
   - <span data-ttu-id="151df-319">[配置单应用展台的设置](#mdmconfigsingle)。</span><span class="sxs-lookup"><span data-stu-id="151df-319">[Configure the settings for a single-app kiosk](#mdmconfigsingle).</span></span>
   - <span data-ttu-id="151df-320">[配置多应用展台的设置](#mdmconfigmulti)。</span><span class="sxs-lookup"><span data-stu-id="151df-320">[Configure the settings for a multi-app kiosk](#mdmconfigmulti).</span></span>
1. <span data-ttu-id="151df-321">[将展台配置文件分配给组](#mdmassign)。</span><span class="sxs-lookup"><span data-stu-id="151df-321">[Assign the kiosk configuration profile to a group](#mdmassign).</span></span>
1. <span data-ttu-id="151df-322">部署设备。</span><span class="sxs-lookup"><span data-stu-id="151df-322">Deploy the devices.</span></span>
   - <span data-ttu-id="151df-323">[部署单应用展台](#mdmsingledeploy)。</span><span class="sxs-lookup"><span data-stu-id="151df-323">[Deploy a single-app kiosk](#mdmsingledeploy).</span></span>
   - <span data-ttu-id="151df-324">[部署多应用展台](#mdmmultideploy)。</span><span class="sxs-lookup"><span data-stu-id="151df-324">[Deploy a multi-app kiosk](#mdmmultideploy).</span></span>

### <a id="mdmenroll"></a><span data-ttu-id="151df-325">MDM，步骤 1 &ndash; 准备注册设备</span><span class="sxs-lookup"><span data-stu-id="151df-325">MDM, step 1 &ndash; Prepare to enroll the devices</span></span>

<span data-ttu-id="151df-326">你可以将 MDM 系统配置为在用户首次登录时自动注册 HoloLens 设备，或让用户手动注册设备。</span><span class="sxs-lookup"><span data-stu-id="151df-326">You can configure your MDM system to enroll HoloLens devices automatically when the user first signs in, or have users enroll devices manually.</span></span> <span data-ttu-id="151df-327">设备还必须加入 Azure AD 域，并分配到相应的组。</span><span class="sxs-lookup"><span data-stu-id="151df-327">The devices also have to be joined to your Azure AD domain, and assigned to the appropriate groups.</span></span>

<span data-ttu-id="151df-328">若要详细了解如何注册设备，请参阅在 WINDOWS 设备的 MDM 和 Intune 注册方法中注册[HoloLens。](hololens-enroll-mdm.md) [](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)</span><span class="sxs-lookup"><span data-stu-id="151df-328">For more information about how to enroll the devices, see [Enroll HoloLens in MDM](hololens-enroll-mdm.md) and [Intune enrollment methods for Windows devices](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).</span></span>

### <a id="mdmprofile"></a><span data-ttu-id="151df-329">MDM，步骤 2 &ndash; 创建展台配置文件</span><span class="sxs-lookup"><span data-stu-id="151df-329">MDM, step 2 &ndash; Create a kiosk configuration profile</span></span>

1. <span data-ttu-id="151df-330">打开 [Azure](https://portal.azure.com/) 门户并登录到 Intune 管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="151df-330">Open the [Azure](https://portal.azure.com/) portal and sign in to your Intune administrator account.</span></span>
1. <span data-ttu-id="151df-331">选择**Microsoft Intune**  >  **设备配置 - 配置文件**  >  **创建配置文件**。</span><span class="sxs-lookup"><span data-stu-id="151df-331">Select **Microsoft Intune** > **Device configuration - Profiles** > **Create profile**.</span></span>
1. <span data-ttu-id="151df-332">输入配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="151df-332">Enter a profile name.</span></span>
1. <span data-ttu-id="151df-333">选择**平台**  >  **Windows 10 和更高版本**，然后选择**配置文件类型**  > **设备限制**。</span><span class="sxs-lookup"><span data-stu-id="151df-333">Select **Platform** > **Windows 10 and later**, and then select **Profile type** >**Device restrictions**.</span></span>
1. <span data-ttu-id="151df-334">选择 **"**  >  配置**展**台"，然后选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="151df-334">Select **Configure** > **Kiosk**, and then select one of the following:</span></span>
   - <span data-ttu-id="151df-335">若要创建单应用展台，请选择**展台模式**  >  **单应用展台**。</span><span class="sxs-lookup"><span data-stu-id="151df-335">To create a single-app kiosk, select **Kiosk Mode** > **Single-app kiosk**.</span></span>
   - <span data-ttu-id="151df-336">若要创建多应用展台，请选择**展台模式**  >  **多应用展台**。</span><span class="sxs-lookup"><span data-stu-id="151df-336">To create a multi-app kiosk, select **Kiosk Mode** > **Multi-app kiosk**.</span></span>
1. <span data-ttu-id="151df-337">若要开始配置展台，请选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="151df-337">To start configuring the kiosk, select **Add**.</span></span>

<span data-ttu-id="151df-338">你的下一步将有所不同，具体取决于你需要的展台类型。</span><span class="sxs-lookup"><span data-stu-id="151df-338">Your next steps differ depending on the type of kiosk that you want.</span></span> <span data-ttu-id="151df-339">有关详细信息，请选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="151df-339">For more information, select one of the following options:</span></span>  

- [<span data-ttu-id="151df-340">单应用展台</span><span class="sxs-lookup"><span data-stu-id="151df-340">Single-app kiosk</span></span>](#mdmconfigsingle)
- [<span data-ttu-id="151df-341">多应用展台。</span><span class="sxs-lookup"><span data-stu-id="151df-341">Multi-app kiosk</span></span>](#mdmconfigmulti)

<span data-ttu-id="151df-342">若要详细了解如何创建展台配置文件，请参阅 [Windows 10](https://docs.microsoft.com/intune/configuration/kiosk-settings)和 Windows Holographic for Business 设备设置，以使用 Intune 作为专用展台运行。</span><span class="sxs-lookup"><span data-stu-id="151df-342">For more information about how to create a kiosk configuration profile, see [Windows 10 and Windows Holographic for Business device settings to run as a dedicated kiosk using Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).</span></span>

### <a id="mdmconfigsingle"></a><span data-ttu-id="151df-343">MDM，步骤 3 (单应用) &ndash;  配置单应用展台的设置</span><span class="sxs-lookup"><span data-stu-id="151df-343">MDM, step 3 (single-app) &ndash;  Configure the settings for a single-app kiosk</span></span>

<span data-ttu-id="151df-344">本部分总结了单个应用展台所需的设置。</span><span class="sxs-lookup"><span data-stu-id="151df-344">This section summarizes the settings that a single-app kiosk requires.</span></span> <span data-ttu-id="151df-345">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="151df-345">For more details, see the following articles:</span></span>

- <span data-ttu-id="151df-346">若要了解如何在 Intune 中配置展台配置文件，请参阅如何使用 [Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)配置展台模式。</span><span class="sxs-lookup"><span data-stu-id="151df-346">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="151df-347">有关 Intune 中单应用展台的可用设置详细信息，请参阅 [单个全屏应用展台](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="151df-347">For more information about the available settings for single-app kiosks in Intune, see [Single full-screen app kiosks](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span></span>
- <span data-ttu-id="151df-348">对于其他 MDM 服务，请参阅提供商文档中的说明。</span><span class="sxs-lookup"><span data-stu-id="151df-348">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="151df-349">如果你必须使用自定义 XML 配置在 MDM 服务中设置展台，请创建一个定义展台配置的 [XML 文件](#ppkioskconfig)。</span><span class="sxs-lookup"><span data-stu-id="151df-349">If you have to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span>

1. <span data-ttu-id="151df-350">选择"用户**登录**类型本地用户帐户"，然后输入可登录展台的本地 (设备) 帐户或 Microsoft 帐户  >  \*\*\*\* (MSA) 的用户名。</span><span class="sxs-lookup"><span data-stu-id="151df-350">Select **User logon type** > **Local user account**, and then enter the user name of the local (device) account or Microsoft Account (MSA) that can sign in to the kiosk.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="151df-351">**Windows Holographic** for Business 不支持自动登录用户帐户类型。</span><span class="sxs-lookup"><span data-stu-id="151df-351">**Autologon** user account types aren't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="151df-352">选择 **"应用程序类型**  >  **应用商店"应用**，然后从列表中选择应用。</span><span class="sxs-lookup"><span data-stu-id="151df-352">Select **Application type** > **Store app**, and then select an app from the list.</span></span>

<span data-ttu-id="151df-353">下一步是 [将配置文件](#mdmassign) 分配给组。</span><span class="sxs-lookup"><span data-stu-id="151df-353">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmconfigmulti"></a><span data-ttu-id="151df-354">MDM，步骤 3 (多应用) &ndash; 配置多应用展台的设置</span><span class="sxs-lookup"><span data-stu-id="151df-354">MDM, step 3 (multi-app) &ndash; Configure the settings for a multi-app kiosk</span></span>

<span data-ttu-id="151df-355">本部分总结了多应用展台所需的设置。</span><span class="sxs-lookup"><span data-stu-id="151df-355">This section summarizes the settings that a multi-app kiosk requires.</span></span> <span data-ttu-id="151df-356">有关更多详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="151df-356">For more detailed information, see the following articles:</span></span>

- <span data-ttu-id="151df-357">若要了解如何在 Intune 中配置展台配置文件，请参阅如何使用 [Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)配置展台模式。</span><span class="sxs-lookup"><span data-stu-id="151df-357">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="151df-358">有关 Intune 中多应用展台的可用设置详细信息，请参阅 [多应用展台](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="151df-358">For more information about the available settings for multi-app kiosks in Intune, see [Multi-app kiosks](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span></span>
- <span data-ttu-id="151df-359">对于其他 MDM 服务，请参阅提供商文档中的说明。</span><span class="sxs-lookup"><span data-stu-id="151df-359">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="151df-360">如果你需要使用自定义 XML 配置在 MDM 服务中设置展台，请创建 [一个定义](#ppkioskconfig)展台配置的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="151df-360">If you need to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span> <span data-ttu-id="151df-361">如果使用 XML 文件，请确保包含"开始 ["屏幕布局](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="151df-361">If you use an XML file, make sure to include the [Start layout](#start-layout-for-hololens).</span></span>  
- <span data-ttu-id="151df-362">可以选择将自定义"开始"屏幕布局与 Intune 或其他 MDM 服务一同使用。</span><span class="sxs-lookup"><span data-stu-id="151df-362">You can optionally use a custom Start layout with Intune or other MDM services.</span></span> <span data-ttu-id="151df-363">有关详细信息，请参阅[MDM 的"开始"屏幕布局 (Intune 和其他) 。 ](#start-layout-file-for-mdm-intune-and-others)</span><span class="sxs-lookup"><span data-stu-id="151df-363">For more information, see [Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

1. <span data-ttu-id="151df-364">选择 **"S 模式设备否"中的目标 Windows 10。**  >  \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="151df-364">Select **Target Windows 10 in S mode devices** > **No**.</span></span>  
   >[!NOTE]  
   > <span data-ttu-id="151df-365">Windows Holographic for Business 不支持 S 模式。</span><span class="sxs-lookup"><span data-stu-id="151df-365">S mode isn't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="151df-366">选择**用户登录类型**  >  **Azure AD 用户或组**或**用户登录类型**  >  **HoloLens 访问者**，然后添加一个或多个用户组或帐户。</span><span class="sxs-lookup"><span data-stu-id="151df-366">Select **User logon type** > **Azure AD user or group** or **User logon type** > **HoloLens visitor**, and then add one or more user groups or accounts.</span></span>  

   <span data-ttu-id="151df-367">只有属于你在用户登录类型中指定的组或帐户的用户才能\*\*\*\* 使用展台体验。</span><span class="sxs-lookup"><span data-stu-id="151df-367">Only users who belong to the groups or accounts that you specify in **User logon type** can use the kiosk experience.</span></span>

1. <span data-ttu-id="151df-368">使用下列选项选择一个或多个应用：</span><span class="sxs-lookup"><span data-stu-id="151df-368">Select one or more apps by using the following options:</span></span>
   - <span data-ttu-id="151df-369">若要添加已上载的业务线应用，请选择"添加 **应用商店** 应用"，然后选择需要的应用。</span><span class="sxs-lookup"><span data-stu-id="151df-369">To add an uploaded line-of-business app, select **Add store app** and then select the app that you want.</span></span>
   - <span data-ttu-id="151df-370">若要通过指定应用 AUMID 添加应用，请选择"按 **AUMID** 添加"，然后输入应用的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="151df-370">To add an app by specifying its AUMID, select **Add by AUMID** and then enter the AUMID of the app.</span></span> [<span data-ttu-id="151df-371">请参阅可用 AUMID 的列表</span><span class="sxs-lookup"><span data-stu-id="151df-371">See the list of available AUMIDs</span></span>](#aumids)

<span data-ttu-id="151df-372">下一步是 [将配置文件](#mdmassign) 分配给组。</span><span class="sxs-lookup"><span data-stu-id="151df-372">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmassign"></a><span data-ttu-id="151df-373">MDM，步骤 4 &ndash; 将展台配置文件分配给组</span><span class="sxs-lookup"><span data-stu-id="151df-373">MDM, step 4 &ndash; Assign the kiosk configuration profile to a group</span></span>

<span data-ttu-id="151df-374">使用 **展** 台配置文件的"分配"页面设置希望展台配置部署在何处。</span><span class="sxs-lookup"><span data-stu-id="151df-374">Use the **Assignments** page of the kiosk configuration profile to set where you want the kiosk configuration to deploy.</span></span> <span data-ttu-id="151df-375">在最简单的情况下，你将展台配置文件分配给设备在 MDM 中注册时将包含 HoloLens 设备的组。</span><span class="sxs-lookup"><span data-stu-id="151df-375">In the simplest case, you assign the kiosk configuration profile to a group that will contain the HoloLens device when the device enrolls in MDM.</span></span>

### <a id="mdmsingledeploy"></a><span data-ttu-id="151df-376">MDM，步骤 5 (单应用) &ndash; 部署单应用展台</span><span class="sxs-lookup"><span data-stu-id="151df-376">MDM, step 5 (single-app) &ndash; Deploy a single-app kiosk</span></span>

<span data-ttu-id="151df-377">使用 MDM 系统时，可以在 OOBE 期间在 MDM 中注册设备。</span><span class="sxs-lookup"><span data-stu-id="151df-377">When you use an MDM system, you can enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="151df-378">OOBE 完成后，轻松登录设备。</span><span class="sxs-lookup"><span data-stu-id="151df-378">After OOBE finishes, signing in to the device is easy.</span></span>

<span data-ttu-id="151df-379">在 OOBE 期间，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="151df-379">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="151df-380">使用你在展台配置文件中指定的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="151df-380">Sign in by using the account that you specified in the kiosk configuration profile.</span></span>
1. <span data-ttu-id="151df-381">注册设备。</span><span class="sxs-lookup"><span data-stu-id="151df-381">Enroll the device.</span></span> <span data-ttu-id="151df-382">确保设备已添加到分配了展台配置文件的组。</span><span class="sxs-lookup"><span data-stu-id="151df-382">Make sure that the device is added to the group that the kiosk configuration profile is assigned to.</span></span>
1. <span data-ttu-id="151df-383">等待 OOBE 完成、应用商店应用下载和安装以及应用策略。</span><span class="sxs-lookup"><span data-stu-id="151df-383">Wait for OOBE to finish, for the store app to download and install, and for policies to be applied.</span></span> <span data-ttu-id="151df-384">然后重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="151df-384">Then restart the device.</span></span>

<span data-ttu-id="151df-385">下次登录设备时，展台应用应自动启动。</span><span class="sxs-lookup"><span data-stu-id="151df-385">The next time you sign in to the device, the kiosk app should automatically start.</span></span>

<span data-ttu-id="151df-386">如果此时看不到展台配置，请检查 [分配状态](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="151df-386">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

### <a id="mdmmultideploy"></a><span data-ttu-id="151df-387">MDM，步骤 5 (部署多应用) &ndash; 部署多应用展台</span><span class="sxs-lookup"><span data-stu-id="151df-387">MDM, step 5 (multi-app) &ndash; Deploy a multi-app kiosk</span></span>

<span data-ttu-id="151df-388">使用 MDM 系统时，可以在 OOBE 期间将设备加入 Azure AD 租户，并注册 MDM 中的设备。</span><span class="sxs-lookup"><span data-stu-id="151df-388">When you use an MDM system, you can join the device to your Azure AD tenant and enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="151df-389">如果适用，向用户提供注册信息，以便他们可以在 OOBE 过程中使用注册信息。</span><span class="sxs-lookup"><span data-stu-id="151df-389">If appropriate, provide the enrollment information to the users so that they have it available during the OOBE process.</span></span>

> [!NOTE]  
> <span data-ttu-id="151df-390">如果已将展台配置文件分配给包含用户的组，请确保其中一个用户帐户是登录到设备的第一个帐户。</span><span class="sxs-lookup"><span data-stu-id="151df-390">If you have assigned the kiosk configuration profile to a group that contains users, make sure that one of those user accounts is the first account to sign in to the device.</span></span>

<span data-ttu-id="151df-391">在 OOBE 期间，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="151df-391">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="151df-392">使用属于用户登录类型 **组的帐户登录** 。</span><span class="sxs-lookup"><span data-stu-id="151df-392">Sign in by using the account that belongs to the **User logon type** group.</span></span>
1. <span data-ttu-id="151df-393">注册设备。</span><span class="sxs-lookup"><span data-stu-id="151df-393">Enroll the device.</span></span>
1. <span data-ttu-id="151df-394">等待作为展台配置文件一部分的任何应用下载和安装。</span><span class="sxs-lookup"><span data-stu-id="151df-394">Wait for any apps that are part of the kiosk configuration profile to download and install.</span></span> <span data-ttu-id="151df-395">此外，请等待应用策略。</span><span class="sxs-lookup"><span data-stu-id="151df-395">Also, wait for policies to be applied.</span></span>  
1. <span data-ttu-id="151df-396">OOBE 完成后，你可以从 Microsoft Store 安装其他应用或旁加载。</span><span class="sxs-lookup"><span data-stu-id="151df-396">After OOBE finishes, you can install additional apps from the Microsoft store or by sideloading.</span></span> <span data-ttu-id="151df-397">[设备](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) 所属的组所需的应用将自动安装。</span><span class="sxs-lookup"><span data-stu-id="151df-397">[Required apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) for the group that the device belongs to install automatically.</span></span>
1. <span data-ttu-id="151df-398">安装完成后，重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="151df-398">After the installation finishes, restart the device.</span></span>

<span data-ttu-id="151df-399">下次使用属于用户登录类型的帐户登录设备时，展台应用应自动启动\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="151df-399">The next time you sign in to the device by using an account that belongs to the **User logon type**, the kiosk app should automatically launch.</span></span>

<span data-ttu-id="151df-400">如果此时看不到展台配置，请检查 [分配状态](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="151df-400">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

## <span data-ttu-id="151df-401">使用预配包设置单应用或多应用展台</span><span class="sxs-lookup"><span data-stu-id="151df-401">Use a provisioning package to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="151df-402">若要使用预配包设置展台模式，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="151df-402">To set up kiosk mode by using a provisioning package, follow these steps.</span></span>

1. <span data-ttu-id="151df-403">[创建定义展台配置的 XML 文件](#ppkioskconfig)。，包括"开始 ["屏幕布局](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="151df-403">[Create an XML file that defines the kiosk configuration.](#ppkioskconfig), including a [Start layout](#start-layout-for-hololens).</span></span>
2. [<span data-ttu-id="151df-404">将 XML 文件添加到预配包。</span><span class="sxs-lookup"><span data-stu-id="151df-404">Add the XML file to a provisioning package.</span></span>](#ppconfigadd)
3. [<span data-ttu-id="151df-405">将预配包应用到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="151df-405">Apply the provisioning package to HoloLens.</span></span>](#ppapply)

### <a id="ppkioskconfig"></a><span data-ttu-id="151df-406">预配包，步骤 1 &ndash; 创建展台配置 XML 文件</span><span class="sxs-lookup"><span data-stu-id="151df-406">Provisioning package, step 1 &ndash; Create a kiosk configuration XML file</span></span>

<span data-ttu-id="151df-407">按照 [一般说明创建适用于 Windows 桌面的展台配置 XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)文件，以下各项除外：</span><span class="sxs-lookup"><span data-stu-id="151df-407">Follow [the general instructions to create a kiosk configuration XML file for Windows desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), except for the following:</span></span>

- <span data-ttu-id="151df-408">请勿将经典 Windows 应用程序 (Win32) 。</span><span class="sxs-lookup"><span data-stu-id="151df-408">Do not include Classic Windows applications (Win32).</span></span> <span data-ttu-id="151df-409">HoloLens 不支持这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="151df-409">HoloLens does not support these applications.</span></span>
- <span data-ttu-id="151df-410">将 [占位符"开始"屏幕布局 XML](#start-layout-for-hololens) 用于 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="151df-410">Use the [placeholder Start layout XML](#start-layout-for-hololens) for HoloLens.</span></span>
- <span data-ttu-id="151df-411">可选：向展台配置添加来宾访问</span><span class="sxs-lookup"><span data-stu-id="151df-411">Optional: Add guest access to the kiosk configuration</span></span>

#### <a id="ppkioskguest"></a><span data-ttu-id="151df-412">可选：向展台配置添加来宾访问</span><span class="sxs-lookup"><span data-stu-id="151df-412">Optional: Add guest access to the kiosk configuration</span></span>

<span data-ttu-id="151df-413">在 XML 文件的[**"**](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)配置"部分，可以配置一个名为 **"** 访问者"的特殊组，以允许来宾使用展台。</span><span class="sxs-lookup"><span data-stu-id="151df-413">In the [**Configs** section of the XML file](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), you can configure a special group named **Visitor** to allow guests to use the kiosk.</span></span> <span data-ttu-id="151df-414">当展台配置为支持**访问者特殊组**时，"来宾"选项将\*\*\*\* 添加到登录页面。</span><span class="sxs-lookup"><span data-stu-id="151df-414">When the kiosk is configured to support the **Visitor** special group, a "**Guest**" option is added to the sign-in page.</span></span> <span data-ttu-id="151df-415">**来宾**帐户不需要密码，当帐户退出时，与该帐户关联的任何数据都将被删除。</span><span class="sxs-lookup"><span data-stu-id="151df-415">The **Guest** account does not require a password, and any data that is associated with the account is deleted when the account signs out.</span></span>

<span data-ttu-id="151df-416">若要启用 **来宾帐户** ，请向展台配置 XML 添加以下代码段：</span><span class="sxs-lookup"><span data-stu-id="151df-416">To enable the **Guest** account, add the following snippet to your kiosk configuration XML:</span></span>

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a><span data-ttu-id="151df-417">HoloLens 的占位符"开始"屏幕布局</span><span class="sxs-lookup"><span data-stu-id="151df-417">Placeholder Start layout for HoloLens</span></span>

<span data-ttu-id="151df-418">如果使用 [预配包配置](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 多应用展台，此过程需要"开始"屏幕布局。</span><span class="sxs-lookup"><span data-stu-id="151df-418">If you use a [provisioning package](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) to configure a multi-app kiosk, the procedure requires a Start layout.</span></span> <span data-ttu-id="151df-419">Windows Holographic for Business 不支持"开始"屏幕布局自定义。</span><span class="sxs-lookup"><span data-stu-id="151df-419">Start layout customization isn't supported in Windows Holographic for Business.</span></span> <span data-ttu-id="151df-420">因此，你必须使用占位符"开始"屏幕布局。</span><span class="sxs-lookup"><span data-stu-id="151df-420">Therefore, you'll have to use a placeholder Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="151df-421">由于单应用展台在用户登录时启动展台应用，因此它不使用"开始"菜单，也无需具有"开始"屏幕布局。</span><span class="sxs-lookup"><span data-stu-id="151df-421">Because a single-app kiosk starts the kiosk app when a user signs in, it does not use a Start menu and does not have to have a Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="151df-422">如果使用 [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 设置多应用展台，可以选择使用"开始"屏幕布局。</span><span class="sxs-lookup"><span data-stu-id="151df-422">If you use [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) to set up a multi-app kiosk, you can optionally use a Start layout.</span></span> <span data-ttu-id="151df-423">有关详细信息，请参阅 Mdm 的占位符"开始"屏幕布局 ([Intune 和其他) 。 ](#start-layout-file-for-mdm-intune-and-others)</span><span class="sxs-lookup"><span data-stu-id="151df-423">For more information, see [Placeholder Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

<span data-ttu-id="151df-424">对于"开始"屏幕布局，将 **以下 StartLayout** 部分添加到展台预配 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="151df-424">For the Start layout, add the following **StartLayout** section to the kiosk provisioning XML file:</span></span>

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

#### <a id="start-layout-file-for-mdm-intune-and-others"></a><span data-ttu-id="151df-425">适用于 Intune 和其他托管 (MDM 的占位符"开始"屏幕布局) </span><span class="sxs-lookup"><span data-stu-id="151df-425">Placeholder Start layout file for MDM (Intune and others)</span></span>

<span data-ttu-id="151df-426">将以下示例另存为 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="151df-426">Save the following sample as an XML file.</span></span> <span data-ttu-id="151df-427">在 Microsoft Intune 应用中配置多应用展台时，或在提供展台配置文件 (另一个 MDM 服务中配置展台时，可以使用) 。</span><span class="sxs-lookup"><span data-stu-id="151df-427">You can use this file when you configure the multi-app kiosk in Microsoft Intune (or in another MDM service that provides a kiosk profile).</span></span>

> [!NOTE]
> <span data-ttu-id="151df-428">如果你必须使用自定义设置和完整的 XML 配置在 MDM 服务中设置展台，请使用预配包的"开始" [屏幕布局说明](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="151df-428">If you have to use a custom setting and full XML configuration to set up a kiosk in your MDM service, use the [Start layout instructions for a provisioning package](#start-layout-for-hololens).</span></span>

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

### <a id="ppconfigadd"></a><span data-ttu-id="151df-429">Prov.</span><span class="sxs-lookup"><span data-stu-id="151df-429">Prov.</span></span> <span data-ttu-id="151df-430">包，步骤 2 &ndash; 将展台配置 XML 文件添加到预配包</span><span class="sxs-lookup"><span data-stu-id="151df-430">package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package</span></span>

1. <span data-ttu-id="151df-431">打开 [Windows 配置设计器](https://www.microsoft.com/store/apps/9nblggh4tx22)。</span><span class="sxs-lookup"><span data-stu-id="151df-431">Open [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span>
1. <span data-ttu-id="151df-432">选择 **"高级预配"，** 输入项目名称，然后选择"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="151df-432">Select **Advanced provisioning**, enter a name for your project, and then select **Next**.</span></span>
1. <span data-ttu-id="151df-433">选择**Windows 10 全息版**，然后选择"下**一步"。**</span><span class="sxs-lookup"><span data-stu-id="151df-433">Select **Windows 10 Holographic**, and then select **Next**.</span></span>
1. <span data-ttu-id="151df-434">选择 **"完成"。**</span><span class="sxs-lookup"><span data-stu-id="151df-434">Select **Finish**.</span></span> <span data-ttu-id="151df-435">此时将打开你的程序包的工作区。</span><span class="sxs-lookup"><span data-stu-id="151df-435">The workspace for your package opens.</span></span>
1. <span data-ttu-id="151df-436">选择**运行时设置**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**。</span><span class="sxs-lookup"><span data-stu-id="151df-436">Select **Runtime settings** > **AssignedAccess** > **MultiAppAssignedAccessSettings**.</span></span>
1. <span data-ttu-id="151df-437">在中央窗格中，选择 **"浏览** "以查找并选择你创建的展台配置 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="151df-437">In the center pane, select **Browse** to locate and select the kiosk configuration XML file that you created.</span></span>

   ![Windows 配置设计器中的 MultiAppAssignedAccessSettings 字段的屏幕截图](./images/multiappassignedaccesssettings.png)

1. <span data-ttu-id="151df-439">**可选**。</span><span class="sxs-lookup"><span data-stu-id="151df-439">**Optional**.</span></span> <span data-ttu-id="151df-440"> (如果你想要在设备的初始设置后应用预配包，并且展台设备上已有管理员用户，请跳过此步骤。) **选择运行时**设置帐户用户，然后创建用户帐户。 &gt;\ \*\*\** &gt;\ \*\*\**</span><span class="sxs-lookup"><span data-stu-id="151df-440">(If you want to apply the provisioning package after the initial setup of the device, and there is an admin user already available on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a user account.</span></span> <span data-ttu-id="151df-441">提供用户名和密码，然后选择 **"用户组**  >  **管理员"。**</span><span class="sxs-lookup"><span data-stu-id="151df-441">Provide a user name and password, and then select **UserGroup** > **Administrators**.</span></span>  
  
     <span data-ttu-id="151df-442">使用此帐户，可以查看设置状态和日志。</span><span class="sxs-lookup"><span data-stu-id="151df-442">By using this account, you can view the provisioning status and logs.</span></span>  
1. <span data-ttu-id="151df-443">**可选**。</span><span class="sxs-lookup"><span data-stu-id="151df-443">**Optional**.</span></span> <span data-ttu-id="151df-444"> (如果展台设备上已有非管理员帐户，请跳过此步骤。) **选择运行时**设置帐户用户，然后创建本地 &gt;\ \*\*\** &gt;\ \*\*\** 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="151df-444">(If you already have a non-admin account on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a local user account.</span></span> <span data-ttu-id="151df-445">确保用户名与在配置 XML 中指定的帐户相同。</span><span class="sxs-lookup"><span data-stu-id="151df-445">Make sure that the user name is the same as for the account that you specify in the configuration XML.</span></span> <span data-ttu-id="151df-446">选择**UserGroup**  >  **标准用户**。</span><span class="sxs-lookup"><span data-stu-id="151df-446">Select **UserGroup** > **Standard Users**.</span></span>
1. <span data-ttu-id="151df-447">选择 **"文件**  >  **保存"。**</span><span class="sxs-lookup"><span data-stu-id="151df-447">Select **File** > **Save**.</span></span>
1. <span data-ttu-id="151df-448">选择 **"**  >  **导出预配包"，** 然后选择"**所有者**  >  **IT 管理员"。** 这设置此预配包的优先级高于从其他源应用到此设备的预配包。</span><span class="sxs-lookup"><span data-stu-id="151df-448">Select **Export** > **Provisioning package**, and then select **Owner** > **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages that are applied to this device from other sources.</span></span>
1. <span data-ttu-id="151df-449">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="151df-449">Select **Next**.</span></span>
1. <span data-ttu-id="151df-450">在 **"预配包安全** "页上，选择一个安全选项。</span><span class="sxs-lookup"><span data-stu-id="151df-450">On the **Provisioning package security** page, select a security option.</span></span>
   > [!IMPORTANT]  
   > <span data-ttu-id="151df-451">如果选择" **启用程序包签名**"，则还必须选择用于对程序包进行签名的有效证书。</span><span class="sxs-lookup"><span data-stu-id="151df-451">If you select **Enable package signing**, you also have to select a valid certificate to use for signing the package.</span></span> <span data-ttu-id="151df-452">为此，请选择" **浏览** "，然后选择要用于对程序包进行签名的证书。</span><span class="sxs-lookup"><span data-stu-id="151df-452">To do this, select **Browse** and select the certificate that you want to use to sign the package.</span></span>
   
   > [!CAUTION]  
   > <span data-ttu-id="151df-453">不要选择 **"启用程序包加密"。**</span><span class="sxs-lookup"><span data-stu-id="151df-453">Do not select **Enable package encryption**.</span></span> <span data-ttu-id="151df-454">在 HoloLens 设备上，此设置会导致预配失败。</span><span class="sxs-lookup"><span data-stu-id="151df-454">On HoloLens devices, this setting causes provisioning to fail.</span></span>
1. <span data-ttu-id="151df-455">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="151df-455">Select **Next**.</span></span>
1. <span data-ttu-id="151df-456">指定您希望预配包在生成时转到的输出位置。</span><span class="sxs-lookup"><span data-stu-id="151df-456">Specify the output location where you want the provisioning package to go when it's built.</span></span> <span data-ttu-id="151df-457">默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。</span><span class="sxs-lookup"><span data-stu-id="151df-457">By default, Windows Configuration Designer uses the project folder as the output location.</span></span> <span data-ttu-id="151df-458">如果要更改输出位置，请选择"浏览 **"。**</span><span class="sxs-lookup"><span data-stu-id="151df-458">If you want to change the output location, select **Browse**.</span></span> <span data-ttu-id="151df-459">完成后，选择"下一**步"。**</span><span class="sxs-lookup"><span data-stu-id="151df-459">When you are finished, select **Next**.</span></span>
1. <span data-ttu-id="151df-460">选择 **"生成** "开始生成程序包。</span><span class="sxs-lookup"><span data-stu-id="151df-460">Select **Build** to start building the package.</span></span> <span data-ttu-id="151df-461">无需花费太长时间即可生成预配包。</span><span class="sxs-lookup"><span data-stu-id="151df-461">The provisioning package doesn't take long to build.</span></span> <span data-ttu-id="151df-462">生成页显示项目信息，进度栏指示生成状态。</span><span class="sxs-lookup"><span data-stu-id="151df-462">The build page displays the project information, and the progress bar indicates the build status.</span></span>

### <a id="ppapply"></a><span data-ttu-id="151df-463">预配包，步骤 3 &ndash; 将预配包应用到 HoloLens</span><span class="sxs-lookup"><span data-stu-id="151df-463">Provisioning package, step 3 &ndash; Apply the provisioning package to HoloLens</span></span>

<span data-ttu-id="151df-464">"使用预配包配置 HoloLens"一文提供了在下列情况下应用预配包的详细说明：</span><span class="sxs-lookup"><span data-stu-id="151df-464">The "Configure HoloLens by using a provisioning package" article provides detailed instructions to apply the provisioning package under the following circumstances:</span></span>

- <span data-ttu-id="151df-465">你可以最初[在设置期间将预配包应用到 HoloLens。](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="151df-465">You can initially [apply a provisioning package to HoloLens during setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).</span></span>

- <span data-ttu-id="151df-466">设置后[，还可以将预配包应用到 HoloLens。](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)</span><span class="sxs-lookup"><span data-stu-id="151df-466">You can also [apply a provisioning package to HoloLens after setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).</span></span>

## <span data-ttu-id="151df-467">使用 Windows Device Portal 设置单应用展台</span><span class="sxs-lookup"><span data-stu-id="151df-467">Use the Windows Device Portal to set up a single-app kiosk</span></span>

<span data-ttu-id="151df-468">若要使用 Windows Device Portal 设置展台模式，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="151df-468">To set up kiosk mode by using the Windows Device Portal, follow these steps.</span></span>

1. <span data-ttu-id="151df-469">[将 HoloLens 设备设置为使用 Windows Device Portal。](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)</span><span class="sxs-lookup"><span data-stu-id="151df-469">[Set up the HoloLens device to use the Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal).</span></span> <span data-ttu-id="151df-470">Device Portal 是 HoloLens 上的 Web 服务器，你可以从电脑上的 Web 浏览器连接到它。</span><span class="sxs-lookup"><span data-stu-id="151df-470">The Device Portal is a web server on your HoloLens that you can connect to from a web browser on your PC.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="151df-471">将 HoloLens 设置为使用 Device Portal 时，你必须在设备上启用开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="151df-471">When you set up HoloLens to use the Device Portal, you have to enable Developer Mode on the device.</span></span> <span data-ttu-id="151df-472">通过具有 Windows Holographic for Business 的设备的开发人员模式，你可以旁加载应用。</span><span class="sxs-lookup"><span data-stu-id="151df-472">Developer Mode on a device that has Windows Holographic for Business enables you to side-load apps.</span></span> <span data-ttu-id="151df-473">但是，此设置会面临用户安装尚未通过 Microsoft Store 认证的应用的风险。</span><span class="sxs-lookup"><span data-stu-id="151df-473">However, this setting creates a risk that a user can install apps that have not been certified by the Microsoft Store.</span></span> <span data-ttu-id="151df-474">管理员可以使用策略 CSP 中的**ApplicationManagement/AllowDeveloper Unlock**设置阻止启用开发人员[模式。](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)</span><span class="sxs-lookup"><span data-stu-id="151df-474">Administrators can block the ability to enable Developer Mode by using the **ApplicationManagement/AllowDeveloper Unlock** setting in the [Policy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider).</span></span> [<span data-ttu-id="151df-475">了解有关开发人员模式的详细信息。</span><span class="sxs-lookup"><span data-stu-id="151df-475">Learn more about Developer Mode.</span></span>](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. <span data-ttu-id="151df-476">在计算机上，使用 [WLAN](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 或 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="151df-476">On a computer, connect to the HoloLens by using [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) or [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).</span></span>

1. <span data-ttu-id="151df-477">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="151df-477">Do one of the following:</span></span>
   - <span data-ttu-id="151df-478">如果是首次连接到 Windows Device Portal，请 [创建用户名和密码](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span><span class="sxs-lookup"><span data-stu-id="151df-478">If you are connecting to the Windows Device Portal for the first time, [create a user name and password](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span></span>
   - <span data-ttu-id="151df-479">输入您之前设置的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="151df-479">Enter the user name and password that you previously set up.</span></span>

    > [!TIP]
    > <span data-ttu-id="151df-480">如果发现浏览器中的证书错误，请遵循[以下疑难解答步骤](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)。</span><span class="sxs-lookup"><span data-stu-id="151df-480">If you see a certificate error in the browser, follow [these troubleshooting steps](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).</span></span>

1. <span data-ttu-id="151df-481">在 Windows Device Portal 中，选择 **展台模式**。</span><span class="sxs-lookup"><span data-stu-id="151df-481">In the Windows Device Portal, select **Kiosk Mode**.</span></span>

1. <span data-ttu-id="151df-482">选择 **"启用展台模式**"，选择要在设备启动时运行的应用，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="151df-482">Select **Enable Kiosk Mode**, select an app to run when the device starts, and then select **Save**.</span></span>

    ![展台模式](images/kiosk.png)
1. <span data-ttu-id="151df-484">重新启动 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="151df-484">Restart HoloLens.</span></span> <span data-ttu-id="151df-485">如果你仍然打开 Device Portal 页面，可以选择 **页面顶部的"** 重新启动"。</span><span class="sxs-lookup"><span data-stu-id="151df-485">If you still have your Device Portal page open, you can select **Restart** at the top of the page.</span></span>

> [!NOTE]
> <span data-ttu-id="151df-486">Kiosk Mode can be set via Device Portal's REST API by doing a POST to /api/holographic/kioskmode/settings with one required query string parameter ("kioskModeEnabled" with a value of "true" or "false") and one optional parameter ("startupApp" with a value of a package name) .</span><span class="sxs-lookup"><span data-stu-id="151df-486">Kiosk Mode can be set via Device Portal’s REST API by doing a POST to /api/holographic/kioskmode/settings with one required query string parameter (“kioskModeEnabled” with a value of “true” or “false”) and one optional parameter (“startupApp” with a value of a package name).</span></span> <span data-ttu-id="151df-487">请记住，Device Portal 仅面向开发人员，不应在非开发人员设备上启用。</span><span class="sxs-lookup"><span data-stu-id="151df-487">Please keep in mind that Device Portal is intended for developers only and should not be enabled on non-developer devices.</span></span> <span data-ttu-id="151df-488">REST API 在将来的更新/版本中可能会更改。</span><span class="sxs-lookup"><span data-stu-id="151df-488">The REST API is subject to change in future updates/releases.</span></span>

## <span data-ttu-id="151df-489">详细信息</span><span class="sxs-lookup"><span data-stu-id="151df-489">More information</span></span>

### <span data-ttu-id="151df-490">了解如何使用预配包配置展台。</span><span class="sxs-lookup"><span data-stu-id="151df-490">Watch how to configure a kiosk by using a provisioning package.</span></span>  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <span data-ttu-id="151df-491">全局分配的访问权限 – 展台模式</span><span class="sxs-lookup"><span data-stu-id="151df-491">Global Assigned Access – Kiosk Mode</span></span>
- <span data-ttu-id="151df-492">通过启用在系统级别应用展台模式的新展台方法，减少展台的标识管理。</span><span class="sxs-lookup"><span data-stu-id="151df-492">Reduced Identity management for Kiosk, by enabling new Kiosk method that applies Kiosk mode at the system level.</span></span>

<span data-ttu-id="151df-493">此新功能允许 IT 管理员为适用于系统级别的多个应用展台模式配置 HoloLens 2 设备，此模式与系统上的任何标识没有任何关联，并且适用于登录设备的每个人。</span><span class="sxs-lookup"><span data-stu-id="151df-493">This new feature allows an IT Admin to configure a HoloLens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> <span data-ttu-id="151df-494">在此处详细阅读有关此[新功能。](hololens-global-assigned-access-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="151df-494">Read about this new feature in detail [here](hololens-global-assigned-access-kiosk.md).</span></span>

### <span data-ttu-id="151df-495">在多应用展台模式下自动启动应用程序</span><span class="sxs-lookup"><span data-stu-id="151df-495">Automatic launch of an application in multiple-app kiosk mode</span></span> 
- <span data-ttu-id="151df-496">自动应用启动的集中体验，进一步增加了为展台模式体验选择的 UI 和应用选择。</span><span class="sxs-lookup"><span data-stu-id="151df-496">Focused experience with automatic app launch, further increasing the UI and app selections chosen for Kiosk mode experiences.</span></span>

<span data-ttu-id="151df-497">仅适用于多应用展台模式，并且只能使用分配的访问权限配置中的以下突出显示属性将 1 个应用指定为自动启动。</span><span class="sxs-lookup"><span data-stu-id="151df-497">Applies only to multiple-app kiosk mode and only 1 app can be designated to auto-launch using highlighted attribute below in Assigned Access configuration.</span></span> 

<span data-ttu-id="151df-498">当用户登录时，将自动启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="151df-498">Application is automatically launched when user signs-in.</span></span> 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <span data-ttu-id="151df-499">用于处理故障的展台模式行为更改</span><span class="sxs-lookup"><span data-stu-id="151df-499">Kiosk mode behavior changes for handling of failures</span></span>
- <span data-ttu-id="151df-500">通过消除展台模式故障上的可用应用，实现更安全的展台模式。</span><span class="sxs-lookup"><span data-stu-id="151df-500">More secure Kiosk mode by eliminating available apps on Kiosk mode failures.</span></span> 

<span data-ttu-id="151df-501">在应用展台模式失败之前，HoloLens 用于在"开始"菜单中显示所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="151df-501">Earlier on encountering failures in applying kiosk mode, HoloLens used to show up all applications in start menu.</span></span> <span data-ttu-id="151df-502">现在，在 Windows 全息版 20H2 中，如果发生故障，不会在"开始"菜单中显示应用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="151df-502">Now in Windows Holographic version 20H2 in the case of failures no apps will be shown in the start menu as below:</span></span> 

![展台模式在出现故障时的外观的图像。](images/hololens-kiosk-failure-behavior.png )

### <span data-ttu-id="151df-504">为脱机展台缓存 Azure AD 组成员身份</span><span class="sxs-lookup"><span data-stu-id="151df-504">Cache Azure AD Group membership for offline Kiosk</span></span>
- <span data-ttu-id="151df-505">已启用脱机展台，可与 Azure AD 组一起使用，最多 60 天。</span><span class="sxs-lookup"><span data-stu-id="151df-505">Enabled Offline Kiosks to be used with Azure AD groups for up to 60 days.</span></span>

<span data-ttu-id="151df-506">此策略控制允许 Azure AD 组成员身份缓存用于面向已登录用户的 Azure AD 组的分配的访问权限配置天数。</span><span class="sxs-lookup"><span data-stu-id="151df-506">This policy controls for how many days, Azure AD group membership cache is allowed to be used for Assigned Access configurations targeting Azure AD groups for signed in user.</span></span> <span data-ttu-id="151df-507">一旦此策略值设置为大于 0 的值，则不使用缓存。</span><span class="sxs-lookup"><span data-stu-id="151df-507">Once this policy value is set to value greater than 0 only then cache is used otherwise not.</span></span>  

<span data-ttu-id="151df-508">名称：AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span><span class="sxs-lookup"><span data-stu-id="151df-508">Name: AADGroupMembershipCacheValidityInDays URI value: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span></span>

<span data-ttu-id="151df-509">最小值 - 0 天</span><span class="sxs-lookup"><span data-stu-id="151df-509">Min - 0 days</span></span>  
<span data-ttu-id="151df-510">最大值 - 60 天</span><span class="sxs-lookup"><span data-stu-id="151df-510">Max - 60 days</span></span> 

<span data-ttu-id="151df-511">正确使用此策略的步骤：</span><span class="sxs-lookup"><span data-stu-id="151df-511">Steps to use this policy correctly:</span></span> 
1. <span data-ttu-id="151df-512">创建面向 Azure AD 组的展台的设备配置文件，并将其分配给 HoloLens () 。</span><span class="sxs-lookup"><span data-stu-id="151df-512">Create a device configuration profile for kiosk targeting Azure AD groups and assign it to HoloLens device(s).</span></span> 
1. <span data-ttu-id="151df-513">创建基于 OMA URI 的自定义设备配置，该配置将此策略值设置为所需天数 (> 0) 并将其分配给 HoloLens 设备 () 。</span><span class="sxs-lookup"><span data-stu-id="151df-513">Create a custom OMA URI based device configuration which sets this policy value to desired number of days (> 0) and assign it to HoloLens device(s).</span></span> 
    1. <span data-ttu-id="151df-514">URI 值应在 OMA-URI 文本框中输入为 ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span><span class="sxs-lookup"><span data-stu-id="151df-514">The URI value should be entered in OMA-URI text box as ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span></span>
    1. <span data-ttu-id="151df-515">该值可以介于允许的最小值/最大值之间。</span><span class="sxs-lookup"><span data-stu-id="151df-515">The value can be between min / max allowed.</span></span>
1. <span data-ttu-id="151df-516">注册 HoloLens 设备并验证这两种配置是否适用于该设备。</span><span class="sxs-lookup"><span data-stu-id="151df-516">Enroll HoloLens devices and verify both configurations get applied to the device.</span></span> 
1. <span data-ttu-id="151df-517">在 Internet 可用时允许 Azure AD 用户 1 登录，一旦成功确认用户登录和 Azure AD 组成员身份，将创建缓存。</span><span class="sxs-lookup"><span data-stu-id="151df-517">Let Azure AD user 1 sign-in when internet is available, once user signs-in and Azure AD group membership is confirmed successfully, cache will be created.</span></span> 
1. <span data-ttu-id="151df-518">现在，Azure AD 用户 1 可以将 HoloLens 脱机并用于展台模式，只要策略值允许 X 天数。</span><span class="sxs-lookup"><span data-stu-id="151df-518">Now Azure AD user 1 can take HoloLens offline and use it for kiosk mode as long as policy value allows for X number of days.</span></span> 
1. <span data-ttu-id="151df-519">对于任何其他 Azure AD 用户 N，可以重复步骤 4 和 5。此处的关键点是任何 Azure AD 用户都必须使用 Internet 登录设备，以便我们至少能确定他们是展台配置所面向的 Azure AD 组的成员。</span><span class="sxs-lookup"><span data-stu-id="151df-519">Steps 4 and 5 can be repeated for any other Azure AD user N. Key point here is that any Azure AD user must sign-in to device using Internet so at least once we can determine that they are member of Azure AD group to which Kiosk configuration is targeted.</span></span> 
 
> [!NOTE]
> <span data-ttu-id="151df-520">为 Azure AD 用户执行步骤 4 之前，将遇到"断开连接"环境中提及的失败行为。</span><span class="sxs-lookup"><span data-stu-id="151df-520">Until step 4 is performed for a Azure AD user will experience failure behavior mentioned in “disconnected” environments.</span></span> 


## <span data-ttu-id="151df-521">适用于 HoloLens 的 XML 展台代码示例</span><span class="sxs-lookup"><span data-stu-id="151df-521">XML Kiosk Code Samples for HoloLens</span></span>

### <span data-ttu-id="151df-522">面向 Azure AD 组的多个应用展台模式。</span><span class="sxs-lookup"><span data-stu-id="151df-522">Multiple app kiosk mode targeting an Azure AD group.</span></span> 
<span data-ttu-id="151df-523">此展台为 Azure AD 组的用户部署一个展台，他们将启用一个展台，其中包括 3 个应用：设置、远程协助和反馈中心。</span><span class="sxs-lookup"><span data-stu-id="151df-523">This kiosk deploys a Kiosk that for users in the Azure AD group, they will have a Kiosk enabled that includes the 3 apps: Settings, Remote Assist, and Feedback Hub.</span></span> <span data-ttu-id="151df-524">若要修改此示例以立即使用，请确保更改下面突出显示的 GUID，以匹配你自己的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="151df-524">To modify this sample to be used immediately, make sure to change the GUID highlighted below to match an Azure AD Group of your own.</span></span> 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <span data-ttu-id="151df-525">面向 Azure AD 帐户的多个应用展台模式。</span><span class="sxs-lookup"><span data-stu-id="151df-525">Multiple app kiosk mode targeting Azure AD account.</span></span>
<span data-ttu-id="151df-526">此展台为单个用户部署展台，他们将启用包括 3 个应用的展台：设置、远程协助和反馈中心。</span><span class="sxs-lookup"><span data-stu-id="151df-526">This kiosk deploys a Kiosk for a single user, they will have a Kiosk enabled that includes the 3 apps: Settings, Remote Assist, and Feedback Hub.</span></span> <span data-ttu-id="151df-527">若要修改此示例以立即使用，请确保更改下面突出显示的帐户，以匹配你自己的 Azure AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="151df-527">To modify this sample to be used immediately, make sure to change the account highlighted below to match an Azure AD Account of your own.</span></span> 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

