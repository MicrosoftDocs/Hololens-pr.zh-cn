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
ms.openlocfilehash: a043b2f96bec6127d52622b4662279c777df6f8f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308440"
---
# <a name="set-up-hololens-as-a-kiosk"></a><span data-ttu-id="b6b38-103">将 HoloLens 设置为展台</span><span class="sxs-lookup"><span data-stu-id="b6b38-103">Set up HoloLens as a kiosk</span></span>

<span data-ttu-id="b6b38-104">您可以通过将设备配置为在展台模式下运行，将一个 HoloLens 设备配置为一个固定用途的设备，也称为 *展台*。</span><span class="sxs-lookup"><span data-stu-id="b6b38-104">You can configure a HoloLens device to function as a fixed-purpose device, also called a *kiosk*, by configuring the device to run in kiosk mode.</span></span> <span data-ttu-id="b6b38-105">展台模式限制设备上可用的应用程序 (或用户) 。</span><span class="sxs-lookup"><span data-stu-id="b6b38-105">Kiosk mode limits the applications (or users) that are available on the device.</span></span> <span data-ttu-id="b6b38-106">展台模式是一项方便的功能，可用于将一个 HoloLens 设备专用于企业应用，或在应用演示中使用 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="b6b38-106">Kiosk mode is a convenient feature that you can use to dedicate a HoloLens device to business apps, or to use the HoloLens device in an app demo.</span></span>

<span data-ttu-id="b6b38-107">本文提供了有关特定于 HoloLens 设备的展台配置的各个方面的信息。</span><span class="sxs-lookup"><span data-stu-id="b6b38-107">This article provides information about aspects of kiosk configuration that are specific to HoloLens devices.</span></span> <span data-ttu-id="b6b38-108">有关不同类型的基于 Windows 的展台以及如何对其进行配置的常规信息，请参阅 [在 Windows desktop 上配置展台和数字签名](https://docs.microsoft.com/windows/configuration/kiosk-methods)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-108">For general information about the different types of Windows-based kiosks and how to configure them, see [Configure kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).</span></span>  

> [!IMPORTANT]  
> <span data-ttu-id="b6b38-109">展台模式确定用户登录到设备时可用的应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-109">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="b6b38-110">但展台模式并不是一种安全方法。</span><span class="sxs-lookup"><span data-stu-id="b6b38-110">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="b6b38-111">它不会阻止 "允许" 的应用打开不允许的其他应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-111">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="b6b38-112">为了阻止应用或进程打开，请使用 [Windows Defender 应用程序控制 (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 来创建相应的策略。</span><span class="sxs-lookup"><span data-stu-id="b6b38-112">In order to block apps or processes from opening, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span>
>
> <span data-ttu-id="b6b38-113">了解有关 Microsoft 服务的详细信息，为用户授予 HoloLens 2 使用的高级安全级别，详细了解 [状态分离和隔离 Defender 保护](security-state-separation-isolation.md#defender-protections)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-113">Learn more about the Microsoft services to give users an advanced level of security that HoloLens 2 uses, read more about [State separation and isolation - Defender protections](security-state-separation-isolation.md#defender-protections).</span></span> <span data-ttu-id="b6b38-114">或了解如何 [使用 WDAC 和 Windows PowerShell 通过 Microsoft Intune 允许或阻止 HoloLens 2 设备上的应用](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-114">Or learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="b6b38-115">可以在单应用或多应用配置中使用展台模式，并且可以使用三个过程之一来设置和部署展台配置。</span><span class="sxs-lookup"><span data-stu-id="b6b38-115">You can use kiosk mode in either a single-app or a multi-app configuration, and you can use one of three processes to set up and deploy the kiosk configuration.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="b6b38-116">删除多应用配置将删除已分配的访问功能创建的用户锁定配置文件。</span><span class="sxs-lookup"><span data-stu-id="b6b38-116">Deleting the multi-app configuration removes the user lockdown profiles that the assigned access feature created.</span></span> <span data-ttu-id="b6b38-117">但是，它不会还原所有策略更改。</span><span class="sxs-lookup"><span data-stu-id="b6b38-117">However, it does not revert all the policy changes.</span></span> <span data-ttu-id="b6b38-118">若要还原这些策略，你必须将设备重置为出厂设置。</span><span class="sxs-lookup"><span data-stu-id="b6b38-118">To revert these policies, you have to reset the device to the factory settings.</span></span>

## <a name="plan-the-kiosk-deployment"></a><span data-ttu-id="b6b38-119">规划展台部署</span><span class="sxs-lookup"><span data-stu-id="b6b38-119">Plan the kiosk deployment</span></span>

<span data-ttu-id="b6b38-120">规划展台时，需要能够回答以下问题。</span><span class="sxs-lookup"><span data-stu-id="b6b38-120">When planning your Kiosk you'll need to be able to answer the following questions.</span></span> <span data-ttu-id="b6b38-121">下面是在阅读本页时要考虑的一些决定，还需要考虑这些问题。</span><span class="sxs-lookup"><span data-stu-id="b6b38-121">Here are some decisions to think about while reading this page and some considerations for these questions.</span></span>
1. <span data-ttu-id="b6b38-122">**谁将使用您的展台，他们将使用哪 [种类型的帐户 ()](hololens-identity.md) ？**</span><span class="sxs-lookup"><span data-stu-id="b6b38-122">**Who will be using your Kiosk, and what [type of account(s)](hololens-identity.md) will they be using?**</span></span> <span data-ttu-id="b6b38-123">这是你可能已做出的决定，不应为展台进行调整，但会影响稍后分配展台的方式。</span><span class="sxs-lookup"><span data-stu-id="b6b38-123">This is a decision you have likely already made and shouldn't be adjusted for the sake of your Kiosk, but will affect how the Kiosk is assigned later.</span></span>
1. <span data-ttu-id="b6b38-124">**是否需要为每个用户/组使用不同的网亭，或者是否为某些展台启用了一个？**</span><span class="sxs-lookup"><span data-stu-id="b6b38-124">**Do you need to have either different Kiosks per user/group or a Kiosk not enabled for some?**</span></span> <span data-ttu-id="b6b38-125">如果是这样，则需要通过 XML 创建展台。</span><span class="sxs-lookup"><span data-stu-id="b6b38-125">If so, you'll want to create your Kiosk via XML.</span></span> 
1. <span data-ttu-id="b6b38-126">**展台会有多少应用？**</span><span class="sxs-lookup"><span data-stu-id="b6b38-126">**How many apps will be in your Kiosk?**</span></span> <span data-ttu-id="b6b38-127">如果有1个以上的应用，则需要一个多应用展台。</span><span class="sxs-lookup"><span data-stu-id="b6b38-127">If you have more than 1 app, you'll need a multi-app Kiosk.</span></span> 
1. <span data-ttu-id="b6b38-128">**你的展台中 () 哪些应用？**</span><span class="sxs-lookup"><span data-stu-id="b6b38-128">**Which app(s) will be in your Kiosk?**</span></span> <span data-ttu-id="b6b38-129">除了你自己的应用外，请使用下面的 AUMIDs 列表添加任何 In-Box 应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-129">Please use our list of AUMIDs below to add any In-Box apps in addition to your own.</span></span>
1. <span data-ttu-id="b6b38-130">**你计划如何部署展台？**</span><span class="sxs-lookup"><span data-stu-id="b6b38-130">**How do you plan to deploy your Kiosk?**</span></span> <span data-ttu-id="b6b38-131">如果要在 MDM 中注册设备，则建议使用 MDM 部署展台。</span><span class="sxs-lookup"><span data-stu-id="b6b38-131">If you are enrolling device in MDM then we suggest using MDM to deploy your Kiosk.</span></span> <span data-ttu-id="b6b38-132">如果不使用 MDM，则可以使用预配包进行部署。</span><span class="sxs-lookup"><span data-stu-id="b6b38-132">If you are not using MDM then deployment with Provisioning Package is available.</span></span>  

### <a name="kiosk-mode-requirements"></a><span data-ttu-id="b6b38-133">展台模式要求</span><span class="sxs-lookup"><span data-stu-id="b6b38-133">Kiosk mode requirements</span></span>

<span data-ttu-id="b6b38-134">可以将任何 HoloLens 2 设备配置为使用展台模式。</span><span class="sxs-lookup"><span data-stu-id="b6b38-134">You can configure any HoloLens 2 device to use kiosk mode.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6b38-135">仅当设备具有 Windows 全息 for Business 时，Kiosk 模式才可用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-135">Kiosk mode is available only if the device has Windows Holographic for Business.</span></span> <span data-ttu-id="b6b38-136">所有 HoloLens 2 设备附带 Windows 全息 for Business，无其他版本。</span><span class="sxs-lookup"><span data-stu-id="b6b38-136">All HoloLens 2 devices ship with Windows Holographic for Business and there are no other editions.</span></span> <span data-ttu-id="b6b38-137">每个 HoloLens 2 设备都可以运行展台模式。</span><span class="sxs-lookup"><span data-stu-id="b6b38-137">Every HoloLens 2 devices is able to run Kiosk mode out of the box.</span></span>
>
> <span data-ttu-id="b6b38-138">HoloLens (第一代) 设备需要在操作系统版本和操作系统版本中进行升级。</span><span class="sxs-lookup"><span data-stu-id="b6b38-138">HoloLens (1st gen) devices need to be upgraded both in terms of OS build and OS edition.</span></span> <span data-ttu-id="b6b38-139">下面详细介绍了如何将 HoloLens (第一代) 更新到 [Windows 全息版企业](hololens1-upgrade-enterprise.md) 版。</span><span class="sxs-lookup"><span data-stu-id="b6b38-139">Here is more information on updating a HoloLens (1st gen) to [Windows Holographic for Business](hololens1-upgrade-enterprise.md) edition.</span></span> <span data-ttu-id="b6b38-140">若要更新 HoloLens (第一代) 设备以使用展台模式，你必须首先确保设备运行 Windows 10、版本1803或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b6b38-140">To update a HoloLens (1st gen) device to use kiosk mode, you must first make sure that the device runs Windows 10, version 1803, or a later version.</span></span> <span data-ttu-id="b6b38-141">如果你已使用 Windows 设备恢复工具将 HoloLens (第一代) 设备恢复为其默认版本，或者你已安装了最新的更新，则设备已准备好进行配置。</span><span class="sxs-lookup"><span data-stu-id="b6b38-141">If you have used the Windows Device Recovery Tool to recover your HoloLens (1st gen) device to its default build, or if you have installed the most recent updates, your device is ready to configure.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="b6b38-142">若要帮助保护在展台模式下运行的设备，请考虑添加关闭 USB 连接等功能的设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="b6b38-142">To help protect devices that run in kiosk mode, consider adding device management policies that turn off features such as USB connectivity.</span></span> <span data-ttu-id="b6b38-143">此外，请检查更新圈设置，确保在工作时间内不会进行自动更新。</span><span class="sxs-lookup"><span data-stu-id="b6b38-143">Additionally, check your update ring settings to make sure that automatic updates do not occur during business hours.</span></span>

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a><span data-ttu-id="b6b38-144">确定单应用展台还是多应用展台</span><span class="sxs-lookup"><span data-stu-id="b6b38-144">Decide between a single-app kiosk or a multi-app kiosk</span></span>

<span data-ttu-id="b6b38-145">当用户登录到设备时，单应用展台启动指定的应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-145">A single-app kiosk starts the specified app when the user signs in to the device.</span></span> <span data-ttu-id="b6b38-146">"开始" 菜单被禁用，就像 Cortana 一样。</span><span class="sxs-lookup"><span data-stu-id="b6b38-146">The Start menu is disabled, as is Cortana.</span></span> <span data-ttu-id="b6b38-147">HoloLens 2 设备不响应 [开始](hololens2-basic-usage.md#start-gesture) 手势。</span><span class="sxs-lookup"><span data-stu-id="b6b38-147">A HoloLens 2 device does not respond to the [Start](hololens2-basic-usage.md#start-gesture) gesture.</span></span> <span data-ttu-id="b6b38-148">HoloLens (第一代) 设备不响应 [布隆](hololens1-basic-usage.md) 手势。</span><span class="sxs-lookup"><span data-stu-id="b6b38-148">A HoloLens (1st gen) device does not respond to the [bloom](hololens1-basic-usage.md) gesture.</span></span> <span data-ttu-id="b6b38-149">由于只有一个应用可以运行，因此用户无法放置其他应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-149">Because only one app can run, the user cannot place other apps.</span></span>

<span data-ttu-id="b6b38-150">当用户登录到设备时，多应用展台会显示 "开始" 菜单。</span><span class="sxs-lookup"><span data-stu-id="b6b38-150">A multi-app kiosk displays the Start menu when the user signs in to the device.</span></span> <span data-ttu-id="b6b38-151">展台配置确定哪些应用在 "开始" 菜单中可用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-151">The kiosk configuration determines which apps are available on the Start menu.</span></span> <span data-ttu-id="b6b38-152">你可以使用多应用展台为用户提供易于理解的体验，只需向他们展示他们必须使用的东西，并删除不需要使用的东西。</span><span class="sxs-lookup"><span data-stu-id="b6b38-152">You can use a multi-app kiosk to provide an easy-to-understand experience for users by presenting to them only the things that they have to use, and removing the things they don't need to use.</span></span>

<span data-ttu-id="b6b38-153">下表列出了不同展台模式下的功能。</span><span class="sxs-lookup"><span data-stu-id="b6b38-153">The following table lists the feature capabilities in the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="b6b38-154">“开始”菜单</span><span class="sxs-lookup"><span data-stu-id="b6b38-154">Start menu</span></span> |<span data-ttu-id="b6b38-155">快速操作菜单</span><span class="sxs-lookup"><span data-stu-id="b6b38-155">Quick Actions menu</span></span> |<span data-ttu-id="b6b38-156">照相机和视频</span><span class="sxs-lookup"><span data-stu-id="b6b38-156">Camera and video</span></span> |<span data-ttu-id="b6b38-157">Miracast</span><span class="sxs-lookup"><span data-stu-id="b6b38-157">Miracast</span></span> |<span data-ttu-id="b6b38-158">Cortana</span><span class="sxs-lookup"><span data-stu-id="b6b38-158">Cortana</span></span> |<span data-ttu-id="b6b38-159">内置语音命令</span><span class="sxs-lookup"><span data-stu-id="b6b38-159">Built-in voice commands</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|<span data-ttu-id="b6b38-160">单应用展台</span><span class="sxs-lookup"><span data-stu-id="b6b38-160">Single-app kiosk</span></span> |<span data-ttu-id="b6b38-161">已禁用</span><span class="sxs-lookup"><span data-stu-id="b6b38-161">Disabled</span></span> |<span data-ttu-id="b6b38-162">已禁用</span><span class="sxs-lookup"><span data-stu-id="b6b38-162">Disabled</span></span>   |<span data-ttu-id="b6b38-163">已禁用</span><span class="sxs-lookup"><span data-stu-id="b6b38-163">Disabled</span></span> |<span data-ttu-id="b6b38-164">已禁用</span><span class="sxs-lookup"><span data-stu-id="b6b38-164">Disabled</span></span>   |<span data-ttu-id="b6b38-165">已禁用</span><span class="sxs-lookup"><span data-stu-id="b6b38-165">Disabled</span></span> |<span data-ttu-id="b6b38-166">已启用<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b6b38-166">Enabled<sup>1</sup></span></span> |
|<span data-ttu-id="b6b38-167">多应用展台</span><span class="sxs-lookup"><span data-stu-id="b6b38-167">Multi-app kiosk</span></span> |<span data-ttu-id="b6b38-168">Enabled</span><span class="sxs-lookup"><span data-stu-id="b6b38-168">Enabled</span></span> |<span data-ttu-id="b6b38-169">已启用<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b6b38-169">Enabled<sup>2</sup></span></span> |<span data-ttu-id="b6b38-170">可用<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b6b38-170">Available<sup>2</sup></span></span> |<span data-ttu-id="b6b38-171">可用<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b6b38-171">Available<sup>2</sup></span></span> |<span data-ttu-id="b6b38-172">可用<sup>2、3</sup></span><span class="sxs-lookup"><span data-stu-id="b6b38-172">Available<sup>2, 3</sup></span></span>  |<span data-ttu-id="b6b38-173">已启用<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b6b38-173">Enabled<sup>1</sup></span></span> |

> <span data-ttu-id="b6b38-174"><sup>1</sup> 与禁用功能相关的语音命令不起作用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-174"><sup>1</sup> Voice commands that relate to disabled features do not function.</span></span>  
> <span data-ttu-id="b6b38-175"><sup>2</sup> 有关如何配置这些功能的详细信息，请参阅 [选择展台应用](#plan-kiosk-apps)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-175"><sup>2</sup> For more information about how to configure these features, see [Select kiosk apps](#plan-kiosk-apps).</span></span>  
> <span data-ttu-id="b6b38-176"><sup>3</sup> 即使 Cortana 已禁用，也会启用内置语音命令。</span><span class="sxs-lookup"><span data-stu-id="b6b38-176"><sup>3</sup> Even if Cortana is disabled, the built-in voice commands are enabled.</span></span>

<span data-ttu-id="b6b38-177">下表列出了不同展台模式的用户支持功能。</span><span class="sxs-lookup"><span data-stu-id="b6b38-177">The following table lists the user support features of the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="b6b38-178">支持的用户类型</span><span class="sxs-lookup"><span data-stu-id="b6b38-178">Supported user types</span></span> | <span data-ttu-id="b6b38-179">自动登录</span><span class="sxs-lookup"><span data-stu-id="b6b38-179">Automatic sign-in</span></span> | <span data-ttu-id="b6b38-180">多个访问级别</span><span class="sxs-lookup"><span data-stu-id="b6b38-180">Multiple access levels</span></span> |
| --- | --- | --- | --- |
|<span data-ttu-id="b6b38-181">单应用展台</span><span class="sxs-lookup"><span data-stu-id="b6b38-181">Single-app kiosk</span></span> |<span data-ttu-id="b6b38-182">托管服务帐户 (Azure Active Directory (Azure AD) 或本地帐户中的 MSA) </span><span class="sxs-lookup"><span data-stu-id="b6b38-182">Managed Service Account (MSA) in Azure Active Directory (Azure AD) or local account</span></span> |<span data-ttu-id="b6b38-183">是</span><span class="sxs-lookup"><span data-stu-id="b6b38-183">Yes</span></span> |<span data-ttu-id="b6b38-184">否</span><span class="sxs-lookup"><span data-stu-id="b6b38-184">No</span></span> |
|<span data-ttu-id="b6b38-185">多应用展台</span><span class="sxs-lookup"><span data-stu-id="b6b38-185">Multi-app kiosk</span></span> |<span data-ttu-id="b6b38-186">Azure AD 帐户</span><span class="sxs-lookup"><span data-stu-id="b6b38-186">Azure AD account</span></span> |<span data-ttu-id="b6b38-187">否</span><span class="sxs-lookup"><span data-stu-id="b6b38-187">No</span></span> |<span data-ttu-id="b6b38-188">是</span><span class="sxs-lookup"><span data-stu-id="b6b38-188">Yes</span></span> |

<span data-ttu-id="b6b38-189">有关如何使用这些功能的示例，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="b6b38-189">For examples of how to use these capabilities, see the following table.</span></span>

|<span data-ttu-id="b6b38-190">将单应用展台用于：</span><span class="sxs-lookup"><span data-stu-id="b6b38-190">Use a single-app kiosk for:</span></span> |<span data-ttu-id="b6b38-191">使用多应用展台进行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b6b38-191">Use a multi-app kiosk for:</span></span> |
| --- | --- |
|<span data-ttu-id="b6b38-192">仅对新员工运行 Dynamics 365 指南的设备。</span><span class="sxs-lookup"><span data-stu-id="b6b38-192">A device that runs only a Dynamics 365 Guide for new employees.</span></span> |<span data-ttu-id="b6b38-193">一种设备，用于为一系列员工运行指南和远程协助。</span><span class="sxs-lookup"><span data-stu-id="b6b38-193">A device that runs both Guides and Remote Assistance for a range of employees.</span></span> |
|<span data-ttu-id="b6b38-194">仅运行自定义应用的设备。</span><span class="sxs-lookup"><span data-stu-id="b6b38-194">A device that runs only a custom app.</span></span> |<span data-ttu-id="b6b38-195">作为大多数用户的展台工作的设备， (仅) 运行自定义应用程序，但作为特定用户组的标准设备工作。</span><span class="sxs-lookup"><span data-stu-id="b6b38-195">A device that functions as a kiosk for most users (running only a custom app), but functions as a standard device for a specific group of users.</span></span> |

### <a name="plan-kiosk-apps"></a><span data-ttu-id="b6b38-196">规划 kiosk 应用</span><span class="sxs-lookup"><span data-stu-id="b6b38-196">Plan kiosk apps</span></span>

<span data-ttu-id="b6b38-197">有关如何选择展台应用的一般信息，请参阅 [ (展台模式) 的 "为分配的访问选择应用的准则 ](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)"。</span><span class="sxs-lookup"><span data-stu-id="b6b38-197">For general information about how to choose kiosk apps, see [Guidelines for choosing an app for assigned access (kiosk mode)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).</span></span>

<span data-ttu-id="b6b38-198">如果使用 Windows 设备门户配置单应用展台，请在安装过程中选择该应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-198">If you use the Windows Device Portal to configure a single-app kiosk, you select the app during the setup process.</span></span>  

<span data-ttu-id="b6b38-199">如果使用移动设备管理 (MDM) 系统或预配包来配置展台模式，请使用 [AssignedAccess 配置服务提供程序 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 来指定应用程序。</span><span class="sxs-lookup"><span data-stu-id="b6b38-199">If you use a Mobile Device Management (MDM) system or a provisioning package to configure kiosk mode, you use the [AssignedAccess Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) to specify applications.</span></span> <span data-ttu-id="b6b38-200">CSP 使用 [应用程序用户模型 id (AUMIDs) ](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 来标识应用程序。</span><span class="sxs-lookup"><span data-stu-id="b6b38-200">The CSP uses [Application User Model IDs (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) to identify applications.</span></span> <span data-ttu-id="b6b38-201">下表列出了可在多应用展台中使用的某些内置应用程序的 AUMIDs。</span><span class="sxs-lookup"><span data-stu-id="b6b38-201">The following table lists the AUMIDs of some in-box applications that you can use in a multi-app kiosk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6b38-202">展台模式确定用户登录到设备时可用的应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-202">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="b6b38-203">但展台模式并不是一种安全方法。</span><span class="sxs-lookup"><span data-stu-id="b6b38-203">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="b6b38-204">它不会阻止 "允许" 的应用打开不允许的其他应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-204">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="b6b38-205">由于我们不限制此行为，因此仍可以从边缘、文件资源管理器和 Microsoft Store 应用启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="b6b38-205">Because we do not restrict this behavior, apps can still be launched from Edge, File explorer, and the Microsoft Store apps.</span></span> <span data-ttu-id="b6b38-206">如果你不想从展台启动特定的应用，请使用 [Windows Defender 应用程序控制 (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 来创建相应的策略。</span><span class="sxs-lookup"><span data-stu-id="b6b38-206">If there are specific apps you don't want launched from a Kiosk, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span> 
> 
> <span data-ttu-id="b6b38-207">此外，不能将混合现实主页设置为展台应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-207">In addition, the Mixed Reality Home is not able to be set as a kiosk app.</span></span>

<a id="aumids"></a>

|<span data-ttu-id="b6b38-208">应用名称</span><span class="sxs-lookup"><span data-stu-id="b6b38-208">App Name</span></span> |<span data-ttu-id="b6b38-209">AUMID</span><span class="sxs-lookup"><span data-stu-id="b6b38-209">AUMID</span></span> |
| --- | --- |
|<span data-ttu-id="b6b38-210">3D 查看器</span><span class="sxs-lookup"><span data-stu-id="b6b38-210">3D Viewer</span></span> |<span data-ttu-id="b6b38-211">Microsoft3DViewer \_ 8Wekyb3d8bbwe \! Microsoft3DViewer</span><span class="sxs-lookup"><span data-stu-id="b6b38-211">Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\!Microsoft.Microsoft3DViewer</span></span> |
|<span data-ttu-id="b6b38-212">日历</span><span class="sxs-lookup"><span data-stu-id="b6b38-212">Calendar</span></span> |<span data-ttu-id="b6b38-213">windowscommunicationsapps \_ 8wekyb3d8bbwe \! windowslive。</span><span class="sxs-lookup"><span data-stu-id="b6b38-213">microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar</span></span> |
|<span data-ttu-id="b6b38-214">照相机<sup>1、2</sup></span><span class="sxs-lookup"><span data-stu-id="b6b38-214">Camera<sup>1, 2</sup></span></span> |<span data-ttu-id="b6b38-215">HoloCamera \_ cw5n1h2txyewy \! HoloCamera</span><span class="sxs-lookup"><span data-stu-id="b6b38-215">HoloCamera\_cw5n1h2txyewy\!HoloCamera</span></span> |
|<span data-ttu-id="b6b38-216">Cortana<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b6b38-216">Cortana<sup>3</sup></span></span> |<span data-ttu-id="b6b38-217">549981C3F5F10 \_ 8wekyb3d8bbwe \! 应用</span><span class="sxs-lookup"><span data-stu-id="b6b38-217">Microsoft.549981C3F5F10\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="b6b38-218">HoloLens 上的设备选取器 (第一代) </span><span class="sxs-lookup"><span data-stu-id="b6b38-218">Device Picker on HoloLens (1st gen)</span></span> |<span data-ttu-id="b6b38-219">HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow</span><span class="sxs-lookup"><span data-stu-id="b6b38-219">HoloDevicesFlow\_cw5n1h2txyewy\!HoloDevicesFlow</span></span> |
|<span data-ttu-id="b6b38-220">HoloLens 2 上的设备选取器</span><span class="sxs-lookup"><span data-stu-id="b6b38-220">Device Picker on HoloLens 2</span></span> |<span data-ttu-id="b6b38-221">DevicesFlowHost \_ cw5n1h2txyewy \! Microsoft. DevicesFlowHost</span><span class="sxs-lookup"><span data-stu-id="b6b38-221">Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\!Microsoft.Windows.DevicesFlowHost</span></span> |
|<span data-ttu-id="b6b38-222">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="b6b38-222">Dynamics 365 Guides</span></span> |<span data-ttu-id="b6b38-223">Dynamics365 \_ 8wekyb3d8bbwe \! MicrosoftGuides</span><span class="sxs-lookup"><span data-stu-id="b6b38-223">Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\!MicrosoftGuides</span></span> |
|<span data-ttu-id="b6b38-224">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="b6b38-224">Dynamics 365 Remote Assist</span></span> |<span data-ttu-id="b6b38-225">MicrosoftRemoteAssist \_ 8Wekyb3d8bbwe \! RemoteAssist</span><span class="sxs-lookup"><span data-stu-id="b6b38-225">Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\!Microsoft.RemoteAssist</span></span> |
|<span data-ttu-id="b6b38-226">反馈 &nbsp; 中心</span><span class="sxs-lookup"><span data-stu-id="b6b38-226">Feedback&nbsp;Hub</span></span> |<span data-ttu-id="b6b38-227">WindowsFeedbackHub \_ 8wekyb3d8bbwe \! 应用</span><span class="sxs-lookup"><span data-stu-id="b6b38-227">Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="b6b38-228">文件资源管理器</span><span class="sxs-lookup"><span data-stu-id="b6b38-228">File Explorer</span></span> |<span data-ttu-id="b6b38-229">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span><span class="sxs-lookup"><span data-stu-id="b6b38-229">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span></span> |
|<span data-ttu-id="b6b38-230">Mail</span><span class="sxs-lookup"><span data-stu-id="b6b38-230">Mail</span></span> |<span data-ttu-id="b6b38-231">microsoft.windowscommunicationsapps_8wekyb3d8bbwe！ windowslive</span><span class="sxs-lookup"><span data-stu-id="b6b38-231">microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail</span></span> |
|<span data-ttu-id="b6b38-232">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b6b38-232">Microsoft Edge</span></span> |<span data-ttu-id="b6b38-233">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE</span><span class="sxs-lookup"><span data-stu-id="b6b38-233">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE</span></span> |
|<span data-ttu-id="b6b38-234">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="b6b38-234">Microsoft Store</span></span> |<span data-ttu-id="b6b38-235">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span><span class="sxs-lookup"><span data-stu-id="b6b38-235">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span></span> |
|<span data-ttu-id="b6b38-236">Miracast<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="b6b38-236">Miracast<sup>4</sup></span></span> |&nbsp; |
|<span data-ttu-id="b6b38-237">电影和电视</span><span class="sxs-lookup"><span data-stu-id="b6b38-237">Movies & TV</span></span> |<span data-ttu-id="b6b38-238">ZuneVideo \_ 8Wekyb3d8bbwe \! ZuneVideo</span><span class="sxs-lookup"><span data-stu-id="b6b38-238">Microsoft.ZuneVideo\_8wekyb3d8bbwe\!Microsoft.ZuneVideo</span></span> |
|<span data-ttu-id="b6b38-239">OneDrive</span><span class="sxs-lookup"><span data-stu-id="b6b38-239">OneDrive</span></span> |<span data-ttu-id="b6b38-240">microsoftskydrive \_ 8wekyb3d8bbwe \! 应用</span><span class="sxs-lookup"><span data-stu-id="b6b38-240">microsoft.microsoftskydrive\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="b6b38-241">照片</span><span class="sxs-lookup"><span data-stu-id="b6b38-241">Photos</span></span> |<span data-ttu-id="b6b38-242">\_8wekyb3d8bbwe \! 应用</span><span class="sxs-lookup"><span data-stu-id="b6b38-242">Microsoft.Windows.Photos\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="b6b38-243">设置</span><span class="sxs-lookup"><span data-stu-id="b6b38-243">Settings</span></span> |<span data-ttu-id="b6b38-244">HolographicSystemSettings \_ cw5n1h2txyewy \! 应用</span><span class="sxs-lookup"><span data-stu-id="b6b38-244">HolographicSystemSettings\_cw5n1h2txyewy\!App</span></span> |
|<span data-ttu-id="b6b38-245">提示</span><span class="sxs-lookup"><span data-stu-id="b6b38-245">Tips</span></span> |<span data-ttu-id="b6b38-246">HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips</span><span class="sxs-lookup"><span data-stu-id="b6b38-246">Microsoft.HoloLensTips\_8wekyb3d8bbwe\!HoloLensTips</span></span> |

> <span data-ttu-id="b6b38-247"><sup>1</sup> 若要启用照片或视频捕获，你必须将相机应用启用为展台应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-247"><sup>1</sup> To enable photo or video capture, you have to enable the Camera app as a kiosk app.</span></span>  
> <span data-ttu-id="b6b38-248"><sup>2</sup> 在启用照相机应用时，请注意以下情况：</span><span class="sxs-lookup"><span data-stu-id="b6b38-248"><sup>2</sup> When you enable the Camera app, be aware of the following conditions:</span></span>
> - <span data-ttu-id="b6b38-249">"快速操作" 菜单包括 "照片" 和 "视频" 按钮。</span><span class="sxs-lookup"><span data-stu-id="b6b38-249">The Quick Actions menu includes the Photo and Video buttons.</span></span>  
> - <span data-ttu-id="b6b38-250">还应启用应用 (如照片、邮件或 OneDrive) ，这些可以与图片交互或检索图片。</span><span class="sxs-lookup"><span data-stu-id="b6b38-250">You should also enable an app (such as Photos, Mail, or OneDrive) that can interact with or retrieve pictures.</span></span>  
>  
> <span data-ttu-id="b6b38-251"><sup>3</sup> 即使不将 Cortana 启用为展台应用，也会启用内置语音命令。</span><span class="sxs-lookup"><span data-stu-id="b6b38-251"><sup>3</sup> Even if you do not enable Cortana as a kiosk app, built-in voice commands are enabled.</span></span> <span data-ttu-id="b6b38-252">但是，与禁用的功能相关的命令不起作用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-252">However, commands that are related to disabled features have no effect.</span></span>  
> <span data-ttu-id="b6b38-253"><sup>4</sup> 无法直接启用 Miracast。</span><span class="sxs-lookup"><span data-stu-id="b6b38-253"><sup>4</sup> You cannot enable Miracast directly.</span></span> <span data-ttu-id="b6b38-254">若要启用 Miracast 作为展台应用，请启用相机应用和设备选取器应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-254">To enable Miracast as a kiosk app enable the Camera app and the Device Picker app.</span></span>

### <a name="plan-kiosk-profiles-for-users-or-groups"></a><span data-ttu-id="b6b38-255">为用户或组计划展台配置文件</span><span class="sxs-lookup"><span data-stu-id="b6b38-255">Plan kiosk profiles for users or groups</span></span>

<span data-ttu-id="b6b38-256">当创建 xml 文件或使用 Intune 的 UI 来设置展台时，需要考虑谁将成为展台。</span><span class="sxs-lookup"><span data-stu-id="b6b38-256">When either creating the xml file or using Intune’s UI to set up a Kiosk you’ll need to consider who will be user the Kiosk.</span></span> <span data-ttu-id="b6b38-257">展台配置可以限制为单个帐户或 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="b6b38-257">A Kiosk configuration can be limited to either an individual account or Azure AD groups.</span></span> 

<span data-ttu-id="b6b38-258">通常为用户或用户组启用展台。</span><span class="sxs-lookup"><span data-stu-id="b6b38-258">Typically Kiosks are enabled for either a user, or user group.</span></span> <span data-ttu-id="b6b38-259">但是，如果你计划编写自己的 XML 展台，则可能需要考虑全局分配的访问权限，在该访问中，将在设备级别应用展台，而不考虑标识。</span><span class="sxs-lookup"><span data-stu-id="b6b38-259">However if you plan on writing your own XML Kiosk, then you may want to consider Global Assigned Access, in which the Kiosk is applied at the device level regardless of Identity.</span></span> <span data-ttu-id="b6b38-260">如果这对你很有吸引力，请 [详细了解全局分配的访问亭。](hololens-global-assigned-access-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="b6b38-260">If this appeals to you [read more about Global Assigned Access Kiosks.](hololens-global-assigned-access-kiosk.md)</span></span>

#### <a name="if-you-are-creating-an-xml-file"></a><span data-ttu-id="b6b38-261">如果要创建 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="b6b38-261">If you are creating an XML file:</span></span>
-   <span data-ttu-id="b6b38-262">许多人都创建了多个展台配置文件，并将每个配置文件分配给不同的用户/组。</span><span class="sxs-lookup"><span data-stu-id="b6b38-262">You many create multiple Kiosk profiles, and assign each to different users/groups.</span></span> <span data-ttu-id="b6b38-263">例如，具有多个应用程序的 Azure AD 组的展台，以及一个具有多个应用程序亭和一个单一应用程序的访问者。</span><span class="sxs-lookup"><span data-stu-id="b6b38-263">Such as a Kiosk for your Azure AD Group that has many apps, and a Visitor that has a multiple app kiosk with a singular app.</span></span>
-   <span data-ttu-id="b6b38-264">展台配置将称为 **配置文件 Id** ，并具有一个 GUID。</span><span class="sxs-lookup"><span data-stu-id="b6b38-264">Your kiosk configuration will be called a **Profile Id** and have a GUID.</span></span>
-   <span data-ttu-id="b6b38-265">你将通过指定用户类型并对 **DefaultProfile Id** 使用相同的 GUID，将该配置文件分配到 "配置" 部分。</span><span class="sxs-lookup"><span data-stu-id="b6b38-265">You will assign that Profile in the configs section by specifying the user type and using the same GUID for the **DefaultProfile Id**.</span></span>
- <span data-ttu-id="b6b38-266">通过创建自定义的 OMA URI 设备配置文件并将其应用到使用 URI 值的 HoloLens 设备组，可以创建一个 XML 文件，但仍可通过 MDM 将该文件应用到该设备：/Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="b6b38-266">A XML file can be created but still applied to a device via MDM by creating a custom OMA URI device configuration profile and applying it to HoloLens device group using the URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a><span data-ttu-id="b6b38-267">如果正在 Intune 中创建展台。</span><span class="sxs-lookup"><span data-stu-id="b6b38-267">If you are creating a Kiosk in Intune.</span></span>
-   <span data-ttu-id="b6b38-268">每台设备只能接收单个展台配置文件，否则它将创建冲突，根本不接收展台配置。</span><span class="sxs-lookup"><span data-stu-id="b6b38-268">Each device may only receive a single Kiosk profile, otherwise it will create a conflict and receive no Kiosk configurations at all.</span></span> 
    -   <span data-ttu-id="b6b38-269">其他类型的配置文件和策略（如与展台配置文件无关的设备限制）不与展台配置文件冲突。</span><span class="sxs-lookup"><span data-stu-id="b6b38-269">Other kinds of profiles and policies, such as device restrictions that are not related to the kiosk configuration profile, do not conflict with the kiosk configuration profile.</span></span>
-   <span data-ttu-id="b6b38-270">将为属于用户登录类型的所有用户启用展台，这将使用用户或 Azure AD 组进行设置。</span><span class="sxs-lookup"><span data-stu-id="b6b38-270">The Kiosk will be enabled for all users who are a part of the User logon type, this will be set with a user or Azure AD group.</span></span> 
-   <span data-ttu-id="b6b38-271">设置展台配置后， **用户登录类型** (可以登录展台的用户) 并且选择了应用，则必须仍将设备配置分配给组。</span><span class="sxs-lookup"><span data-stu-id="b6b38-271">After the Kiosk configuration is set and the **User logon type** (users who can log into the Kiosk) and the Apps are selected, the Device Configuration must still be assigned to a group.</span></span> <span data-ttu-id="b6b38-272">分配的组 () 确定哪些设备接收展台设备配置，但如果启用了展台，则不会与交互。</span><span class="sxs-lookup"><span data-stu-id="b6b38-272">The Assigned group(s) determines which devices receive the Kiosk device configuration, however does not interact with if the Kiosk is enabled or not.</span></span> 
    - <span data-ttu-id="b6b38-273">有关在 Intune 中分配配置文件的效果的完整讨论，请参阅 [在 Microsoft Intune 中分配用户和设备配置文件](https://docs.microsoft.com/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-273">For a full discussion of the effects of assigning configuration profiles in Intune, see [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).</span></span>

### <a name="select-a-deployment-method"></a><span data-ttu-id="b6b38-274">选择部署方法</span><span class="sxs-lookup"><span data-stu-id="b6b38-274">Select a deployment method</span></span>

<span data-ttu-id="b6b38-275">您可以选择下列方法之一来部署展台配置：</span><span class="sxs-lookup"><span data-stu-id="b6b38-275">You can select one of the following methods to deploy kiosk configurations:</span></span>

- [<span data-ttu-id="b6b38-276">Microsoft Intune 或其他移动设备管理 (MDM) 服务</span><span class="sxs-lookup"><span data-stu-id="b6b38-276">Microsoft Intune or other mobile device management (MDM) service</span></span>](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="b6b38-277">预配包</span><span class="sxs-lookup"><span data-stu-id="b6b38-277">Provisioning package</span></span>](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="b6b38-278">Windows 设备门户</span><span class="sxs-lookup"><span data-stu-id="b6b38-278">Windows Device Portal</span></span>](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > <span data-ttu-id="b6b38-279">由于此方法要求在设备上启用开发人员模式，因此我们建议你仅将其用于演示。</span><span class="sxs-lookup"><span data-stu-id="b6b38-279">Because this method requires that Developer Mode be enabled on the device, we recommend that you use it only for demonstrations.</span></span>

<span data-ttu-id="b6b38-280">下表列出了每种部署方法的功能和优势。</span><span class="sxs-lookup"><span data-stu-id="b6b38-280">The following table lists the capabilities and benefits of each of the deployment methods.</span></span>

| &nbsp; |<span data-ttu-id="b6b38-281">使用 Windows 设备门户进行部署</span><span class="sxs-lookup"><span data-stu-id="b6b38-281">Deploy by using Windows Device Portal</span></span> |<span data-ttu-id="b6b38-282">使用预配包进行部署</span><span class="sxs-lookup"><span data-stu-id="b6b38-282">Deploy by using a provisioning package</span></span> |<span data-ttu-id="b6b38-283">使用 MDM 进行部署</span><span class="sxs-lookup"><span data-stu-id="b6b38-283">Deploy by using MDM</span></span> |
| --------------------------- | ------------- | -------------------- | ---- |
|<span data-ttu-id="b6b38-284">部署单应用展台</span><span class="sxs-lookup"><span data-stu-id="b6b38-284">Deploy single-app kiosks</span></span>   | <span data-ttu-id="b6b38-285">是</span><span class="sxs-lookup"><span data-stu-id="b6b38-285">Yes</span></span>           | <span data-ttu-id="b6b38-286">是</span><span class="sxs-lookup"><span data-stu-id="b6b38-286">Yes</span></span>                  | <span data-ttu-id="b6b38-287">是</span><span class="sxs-lookup"><span data-stu-id="b6b38-287">Yes</span></span>  |
|<span data-ttu-id="b6b38-288">部署多应用展台</span><span class="sxs-lookup"><span data-stu-id="b6b38-288">Deploy multi-app kiosks</span></span>    | <span data-ttu-id="b6b38-289">否</span><span class="sxs-lookup"><span data-stu-id="b6b38-289">No</span></span>            | <span data-ttu-id="b6b38-290">是</span><span class="sxs-lookup"><span data-stu-id="b6b38-290">Yes</span></span>                  | <span data-ttu-id="b6b38-291">是</span><span class="sxs-lookup"><span data-stu-id="b6b38-291">Yes</span></span>  |
|<span data-ttu-id="b6b38-292">仅部署到本地设备</span><span class="sxs-lookup"><span data-stu-id="b6b38-292">Deploy to local devices only</span></span> | <span data-ttu-id="b6b38-293">是</span><span class="sxs-lookup"><span data-stu-id="b6b38-293">Yes</span></span>           | <span data-ttu-id="b6b38-294">是</span><span class="sxs-lookup"><span data-stu-id="b6b38-294">Yes</span></span>                  | <span data-ttu-id="b6b38-295">否</span><span class="sxs-lookup"><span data-stu-id="b6b38-295">No</span></span>   |
|<span data-ttu-id="b6b38-296">使用开发人员模式进行部署</span><span class="sxs-lookup"><span data-stu-id="b6b38-296">Deploy by using Developer Mode</span></span> |<span data-ttu-id="b6b38-297">必需</span><span class="sxs-lookup"><span data-stu-id="b6b38-297">Required</span></span>       | <span data-ttu-id="b6b38-298">不是必需</span><span class="sxs-lookup"><span data-stu-id="b6b38-298">Not required</span></span>            | <span data-ttu-id="b6b38-299">不是必需</span><span class="sxs-lookup"><span data-stu-id="b6b38-299">Not required</span></span>   |
|<span data-ttu-id="b6b38-300">使用 Azure Active Directory (Azure AD 进行部署) </span><span class="sxs-lookup"><span data-stu-id="b6b38-300">Deploy by using Azure Active Directory (Azure AD)</span></span>  | <span data-ttu-id="b6b38-301">不是必需</span><span class="sxs-lookup"><span data-stu-id="b6b38-301">Not required</span></span>            | <span data-ttu-id="b6b38-302">不是必需</span><span class="sxs-lookup"><span data-stu-id="b6b38-302">Not required</span></span>                   | <span data-ttu-id="b6b38-303">必需</span><span class="sxs-lookup"><span data-stu-id="b6b38-303">Required</span></span>  |
|<span data-ttu-id="b6b38-304">自动部署</span><span class="sxs-lookup"><span data-stu-id="b6b38-304">Deploy automatically</span></span>      | <span data-ttu-id="b6b38-305">否</span><span class="sxs-lookup"><span data-stu-id="b6b38-305">No</span></span>            | <span data-ttu-id="b6b38-306">否</span><span class="sxs-lookup"><span data-stu-id="b6b38-306">No</span></span>                   | <span data-ttu-id="b6b38-307">是</span><span class="sxs-lookup"><span data-stu-id="b6b38-307">Yes</span></span>  |
|<span data-ttu-id="b6b38-308">部署速度</span><span class="sxs-lookup"><span data-stu-id="b6b38-308">Deployment speed</span></span>            | <span data-ttu-id="b6b38-309">快速</span><span class="sxs-lookup"><span data-stu-id="b6b38-309">Fast</span></span>       | <span data-ttu-id="b6b38-310">快</span><span class="sxs-lookup"><span data-stu-id="b6b38-310">Fast</span></span>                 | <span data-ttu-id="b6b38-311">慢</span><span class="sxs-lookup"><span data-stu-id="b6b38-311">Slow</span></span> |
|<span data-ttu-id="b6b38-312">大规模部署</span><span class="sxs-lookup"><span data-stu-id="b6b38-312">Deploy at scale</span></span> | <span data-ttu-id="b6b38-313">不推荐</span><span class="sxs-lookup"><span data-stu-id="b6b38-313">Not recommended</span></span>    | <span data-ttu-id="b6b38-314">建议</span><span class="sxs-lookup"><span data-stu-id="b6b38-314">Recommended</span></span>        | <span data-ttu-id="b6b38-315">建议</span><span class="sxs-lookup"><span data-stu-id="b6b38-315">Recommended</span></span> |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a><span data-ttu-id="b6b38-316">使用 Microsoft Intune 或其他 MDM 设置单个应用程序或多应用程序亭</span><span class="sxs-lookup"><span data-stu-id="b6b38-316">Use Microsoft Intune or other MDM to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="b6b38-317">若要使用 Microsoft Intune 或其他 MDM 系统设置展台模式，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="b6b38-317">To set up kiosk mode by using Microsoft Intune or another MDM system, follow these steps.</span></span>

1. <span data-ttu-id="b6b38-318">[准备注册设备](#mdmenroll)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-318">[Prepare to enroll the devices](#mdmenroll).</span></span>
1. <span data-ttu-id="b6b38-319">[创建展台配置文件](#mdmprofile)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-319">[Create a kiosk configuration profile](#mdmprofile).</span></span>
1. <span data-ttu-id="b6b38-320">配置展台。</span><span class="sxs-lookup"><span data-stu-id="b6b38-320">Configure the kiosk.</span></span>
   - <span data-ttu-id="b6b38-321">[配置单应用展台的设置](#mdmconfigsingle)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-321">[Configure the settings for a single-app kiosk](#mdmconfigsingle).</span></span>
   - <span data-ttu-id="b6b38-322">[配置多应用展台的设置](#mdmconfigmulti)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-322">[Configure the settings for a multi-app kiosk](#mdmconfigmulti).</span></span>
1. <span data-ttu-id="b6b38-323">[将 kiosk 配置文件分配给组](#mdmassign)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-323">[Assign the kiosk configuration profile to a group](#mdmassign).</span></span>
1. <span data-ttu-id="b6b38-324">部署设备。</span><span class="sxs-lookup"><span data-stu-id="b6b38-324">Deploy the devices.</span></span>
   - <span data-ttu-id="b6b38-325">[部署单应用展台](#mdmsingledeploy)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-325">[Deploy a single-app kiosk](#mdmsingledeploy).</span></span>
   - <span data-ttu-id="b6b38-326">[部署多应用展台](#mdmmultideploy)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-326">[Deploy a multi-app kiosk](#mdmmultideploy).</span></span>

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a><span data-ttu-id="b6b38-327">MDM，步骤 1 &ndash; 准备注册设备</span><span class="sxs-lookup"><span data-stu-id="b6b38-327">MDM, step 1 &ndash; Prepare to enroll the devices</span></span>

<span data-ttu-id="b6b38-328">你可以将 MDM 系统配置为在用户首次登录时自动注册 HoloLens 设备，或者让用户手动注册设备。</span><span class="sxs-lookup"><span data-stu-id="b6b38-328">You can configure your MDM system to enroll HoloLens devices automatically when the user first signs in, or have users enroll devices manually.</span></span> <span data-ttu-id="b6b38-329">设备还必须加入到 Azure AD 域，并分配给相应的组。</span><span class="sxs-lookup"><span data-stu-id="b6b38-329">The devices also have to be joined to your Azure AD domain, and assigned to the appropriate groups.</span></span>

<span data-ttu-id="b6b38-330">有关如何注册设备的详细信息，请参阅 [在 MDM 中注册 HoloLens](hololens-enroll-mdm.md) 和 [用于 Windows 设备的 Intune 注册方法](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-330">For more information about how to enroll the devices, see [Enroll HoloLens in MDM](hololens-enroll-mdm.md) and [Intune enrollment methods for Windows devices](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).</span></span>

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a><span data-ttu-id="b6b38-331">MDM，步骤 2 &ndash; 创建展台配置文件</span><span class="sxs-lookup"><span data-stu-id="b6b38-331">MDM, step 2 &ndash; Create a kiosk configuration profile</span></span>

1. <span data-ttu-id="b6b38-332">打开 [Azure](https://portal.azure.com/) 门户并登录到你的 Intune 管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="b6b38-332">Open the [Azure](https://portal.azure.com/) portal and sign in to your Intune administrator account.</span></span>
1. <span data-ttu-id="b6b38-333">选择 **Microsoft Intune**  >  **设备配置-配置** 文件 ""  >  **创建配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="b6b38-333">Select **Microsoft Intune** > **Device configuration - Profiles** > **Create profile**.</span></span>
1. <span data-ttu-id="b6b38-334">输入配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="b6b38-334">Enter a profile name.</span></span>
1. <span data-ttu-id="b6b38-335">选择 "**平台**  >  **Windows 10 和更高版本**"，然后选择 "**配置文件类型**" "  > **设备限制**"。</span><span class="sxs-lookup"><span data-stu-id="b6b38-335">Select **Platform** > **Windows 10 and later**, and then select **Profile type** >**Device restrictions**.</span></span>
1. <span data-ttu-id="b6b38-336">选择 "**配置**  >  **展台**"，然后选择下列各项之一：</span><span class="sxs-lookup"><span data-stu-id="b6b38-336">Select **Configure** > **Kiosk**, and then select one of the following:</span></span>
   - <span data-ttu-id="b6b38-337">若要创建单应用展台，请选择 **展台模式**  >  **单应用展台**。</span><span class="sxs-lookup"><span data-stu-id="b6b38-337">To create a single-app kiosk, select **Kiosk Mode** > **Single-app kiosk**.</span></span>
   - <span data-ttu-id="b6b38-338">若要创建多应用展台，请选择 **展台模式**  >  **多应用展台**。</span><span class="sxs-lookup"><span data-stu-id="b6b38-338">To create a multi-app kiosk, select **Kiosk Mode** > **Multi-app kiosk**.</span></span>
1. <span data-ttu-id="b6b38-339">若要开始配置展台，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="b6b38-339">To start configuring the kiosk, select **Add**.</span></span>

<span data-ttu-id="b6b38-340">后续步骤会有所不同，具体取决于所需的展台类型。</span><span class="sxs-lookup"><span data-stu-id="b6b38-340">Your next steps differ depending on the type of kiosk that you want.</span></span> <span data-ttu-id="b6b38-341">有关详细信息，请选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b6b38-341">For more information, select one of the following options:</span></span>  

- [<span data-ttu-id="b6b38-342">单应用展台</span><span class="sxs-lookup"><span data-stu-id="b6b38-342">Single-app kiosk</span></span>](#mdmconfigsingle)
- [<span data-ttu-id="b6b38-343">多应用展台</span><span class="sxs-lookup"><span data-stu-id="b6b38-343">Multi-app kiosk</span></span>](#mdmconfigmulti)

<span data-ttu-id="b6b38-344">有关如何创建展台配置文件的详细信息，请参阅 [使用 Intune 作为专用展台运行的 windows 10 和 Windows 全息版设备设置](https://docs.microsoft.com/intune/configuration/kiosk-settings)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-344">For more information about how to create a kiosk configuration profile, see [Windows 10 and Windows Holographic for Business device settings to run as a dedicated kiosk using Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).</span></span>

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a><span data-ttu-id="b6b38-345">MDM，步骤 3 (单应用) &ndash;  配置单应用展台的设置</span><span class="sxs-lookup"><span data-stu-id="b6b38-345">MDM, step 3 (single-app) &ndash;  Configure the settings for a single-app kiosk</span></span>

<span data-ttu-id="b6b38-346">本部分总结了单应用展台所需的设置。</span><span class="sxs-lookup"><span data-stu-id="b6b38-346">This section summarizes the settings that a single-app kiosk requires.</span></span> <span data-ttu-id="b6b38-347">有关更多详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="b6b38-347">For more details, see the following articles:</span></span>

- <span data-ttu-id="b6b38-348">有关如何在 Intune 中配置展台配置文件的信息，请参阅 [如何使用 Microsoft Intune 配置展台模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-348">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="b6b38-349">有关 Intune 中的单应用展台可用设置的详细信息，请参阅 [单一全屏应用网亭](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="b6b38-349">For more information about the available settings for single-app kiosks in Intune, see [Single full-screen app kiosks](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span></span>
- <span data-ttu-id="b6b38-350">对于其他 MDM 服务，请查看提供程序的文档以了解相关说明。</span><span class="sxs-lookup"><span data-stu-id="b6b38-350">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="b6b38-351">如果必须使用自定义 XML 配置在 MDM 服务中设置展台，请 [创建一个定义 kiosk 配置的 XML 文件](#ppkioskconfig)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-351">If you have to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span>

1. <span data-ttu-id="b6b38-352">选择 "**用户登录类型**"  >  "**本地用户帐户**"，然后输入可以登录到展台的本地 (设备) 帐户或 Microsoft 帐户)  (的用户名。</span><span class="sxs-lookup"><span data-stu-id="b6b38-352">Select **User logon type** > **Local user account**, and then enter the user name of the local (device) account or Microsoft Account (MSA) that can sign in to the kiosk.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="b6b38-353">Windows Holographic for Business 不支持“自动登录”用户帐户类型。</span><span class="sxs-lookup"><span data-stu-id="b6b38-353">**Autologon** user account types aren't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="b6b38-354">选择 "**应用程序类型**  >  **存储应用**"，然后从列表中选择一个应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-354">Select **Application type** > **Store app**, and then select an app from the list.</span></span>

<span data-ttu-id="b6b38-355">下一步是将配置文件 [分配](#mdmassign) 给组。</span><span class="sxs-lookup"><span data-stu-id="b6b38-355">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a><span data-ttu-id="b6b38-356">MDM，步骤 3 (多应用程序) &ndash; 配置多应用展台的设置</span><span class="sxs-lookup"><span data-stu-id="b6b38-356">MDM, step 3 (multi-app) &ndash; Configure the settings for a multi-app kiosk</span></span>

<span data-ttu-id="b6b38-357">本部分总结了多应用展台所需的设置。</span><span class="sxs-lookup"><span data-stu-id="b6b38-357">This section summarizes the settings that a multi-app kiosk requires.</span></span> <span data-ttu-id="b6b38-358">有关更详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="b6b38-358">For more detailed information, see the following articles:</span></span>

- <span data-ttu-id="b6b38-359">有关如何在 Intune 中配置展台配置文件的信息，请参阅 [如何使用 Microsoft Intune 配置展台模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-359">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="b6b38-360">有关 Intune 中多应用展台可用设置的详细信息，请参阅 [多应用展台](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="b6b38-360">For more information about the available settings for multi-app kiosks in Intune, see [Multi-app kiosks](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span></span>
- <span data-ttu-id="b6b38-361">对于其他 MDM 服务，请查看提供程序的文档以了解相关说明。</span><span class="sxs-lookup"><span data-stu-id="b6b38-361">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="b6b38-362">如果需要使用自定义 XML 配置在 MDM 服务中设置展台，请 [创建一个定义 kiosk 配置的 XML 文件](#ppkioskconfig)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-362">If you need to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span> <span data-ttu-id="b6b38-363">如果使用 XML 文件，请确保包含 [开始布局](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-363">If you use an XML file, make sure to include the [Start layout](#start-layout-for-hololens).</span></span>  
- <span data-ttu-id="b6b38-364">你可以选择将自定义开始布局与 Intune 或其他 MDM 服务一起使用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-364">You can optionally use a custom Start layout with Intune or other MDM services.</span></span> <span data-ttu-id="b6b38-365">有关详细信息，请参阅 [启动 MDM (Intune 的布局文件和其他) ](#start-layout-file-for-mdm-intune-and-others)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-365">For more information, see [Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

1. <span data-ttu-id="b6b38-366">选择 **"在 S 模式设备中面向 Windows 10"**  >  。</span><span class="sxs-lookup"><span data-stu-id="b6b38-366">Select **Target Windows 10 in S mode devices** > **No**.</span></span>  
   >[!NOTE]  
   > <span data-ttu-id="b6b38-367">Windows Holographic for Business 上不支持 S 模式。</span><span class="sxs-lookup"><span data-stu-id="b6b38-367">S mode isn't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="b6b38-368">选择 "**用户登录类型**"  >  **Azure AD "用户或组**" 或 "**用户登录类型**  >  " "**HoloLens 访问者**"，然后添加一个或多个用户组或帐户。</span><span class="sxs-lookup"><span data-stu-id="b6b38-368">Select **User logon type** > **Azure AD user or group** or **User logon type** > **HoloLens visitor**, and then add one or more user groups or accounts.</span></span>  

   <span data-ttu-id="b6b38-369">只有属于你在 " **用户登录类型** " 中指定的组或帐户的用户才能使用展台体验。</span><span class="sxs-lookup"><span data-stu-id="b6b38-369">Only users who belong to the groups or accounts that you specify in **User logon type** can use the kiosk experience.</span></span>

1. <span data-ttu-id="b6b38-370">使用以下选项选择一个或多个应用：</span><span class="sxs-lookup"><span data-stu-id="b6b38-370">Select one or more apps by using the following options:</span></span>
   - <span data-ttu-id="b6b38-371">若要添加上传的业务线应用，请选择 " **添加应用商店应用** "，然后选择所需的应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-371">To add an uploaded line-of-business app, select **Add store app** and then select the app that you want.</span></span>
   - <span data-ttu-id="b6b38-372">若要通过指定应用程序的 AUMID 添加应用程序，请选择 " **添加" AUMID** ，然后输入应用的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="b6b38-372">To add an app by specifying its AUMID, select **Add by AUMID** and then enter the AUMID of the app.</span></span> [<span data-ttu-id="b6b38-373">查看可用的 AUMIDs 列表</span><span class="sxs-lookup"><span data-stu-id="b6b38-373">See the list of available AUMIDs</span></span>](#aumids)

<span data-ttu-id="b6b38-374">下一步是将配置文件 [分配](#mdmassign) 给组。</span><span class="sxs-lookup"><span data-stu-id="b6b38-374">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a><span data-ttu-id="b6b38-375">MDM，步骤 4 &ndash; 将展台配置文件分配给组</span><span class="sxs-lookup"><span data-stu-id="b6b38-375">MDM, step 4 &ndash; Assign the kiosk configuration profile to a group</span></span>

<span data-ttu-id="b6b38-376">使用展台配置文件的 " **分配** " 页，设置要将展台配置部署到的位置。</span><span class="sxs-lookup"><span data-stu-id="b6b38-376">Use the **Assignments** page of the kiosk configuration profile to set where you want the kiosk configuration to deploy.</span></span> <span data-ttu-id="b6b38-377">最简单的情况是，在设备在 MDM 中注册时，将展台配置文件分配给将包含 HoloLens 设备的组。</span><span class="sxs-lookup"><span data-stu-id="b6b38-377">In the simplest case, you assign the kiosk configuration profile to a group that will contain the HoloLens device when the device enrolls in MDM.</span></span>

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a><span data-ttu-id="b6b38-378">MDM，步骤 5 (单应用) &ndash; 部署单应用展台</span><span class="sxs-lookup"><span data-stu-id="b6b38-378">MDM, step 5 (single-app) &ndash; Deploy a single-app kiosk</span></span>

<span data-ttu-id="b6b38-379">使用 MDM 系统时，可以在 OOBE 期间在 MDM 中注册设备。</span><span class="sxs-lookup"><span data-stu-id="b6b38-379">When you use an MDM system, you can enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="b6b38-380">在 OOBE 完成后，登录到设备很简单。</span><span class="sxs-lookup"><span data-stu-id="b6b38-380">After OOBE finishes, signing in to the device is easy.</span></span>

<span data-ttu-id="b6b38-381">在 OOBE 期间，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b6b38-381">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="b6b38-382">使用在展台配置文件中指定的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="b6b38-382">Sign in by using the account that you specified in the kiosk configuration profile.</span></span>
1. <span data-ttu-id="b6b38-383">注册该设备。</span><span class="sxs-lookup"><span data-stu-id="b6b38-383">Enroll the device.</span></span> <span data-ttu-id="b6b38-384">请确保设备已添加到展台配置文件分配到的组。</span><span class="sxs-lookup"><span data-stu-id="b6b38-384">Make sure that the device is added to the group that the kiosk configuration profile is assigned to.</span></span>
1. <span data-ttu-id="b6b38-385">等待 OOBE 完成，针对要下载并安装的应用商店应用，以及要应用的策略。</span><span class="sxs-lookup"><span data-stu-id="b6b38-385">Wait for OOBE to finish, for the store app to download and install, and for policies to be applied.</span></span> <span data-ttu-id="b6b38-386">然后重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="b6b38-386">Then restart the device.</span></span>

<span data-ttu-id="b6b38-387">下次登录到设备时，kiosk 应用应自动启动。</span><span class="sxs-lookup"><span data-stu-id="b6b38-387">The next time you sign in to the device, the kiosk app should automatically start.</span></span>

<span data-ttu-id="b6b38-388">如果此时未看到展台配置，请 [检查分配状态](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-388">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a><span data-ttu-id="b6b38-389">MDM，步骤 5 (多应用程序) &ndash; 部署多应用展台</span><span class="sxs-lookup"><span data-stu-id="b6b38-389">MDM, step 5 (multi-app) &ndash; Deploy a multi-app kiosk</span></span>

<span data-ttu-id="b6b38-390">使用 MDM 系统时，可以将设备加入到 Azure AD 租户，并在 OOBE 期间在 MDM 中注册设备。</span><span class="sxs-lookup"><span data-stu-id="b6b38-390">When you use an MDM system, you can join the device to your Azure AD tenant and enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="b6b38-391">如果需要，请向用户提供注册信息，使其在 OOBE 过程中可用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-391">If appropriate, provide the enrollment information to the users so that they have it available during the OOBE process.</span></span>

> [!NOTE]  
> <span data-ttu-id="b6b38-392">如果已将 kiosk 配置文件分配到包含用户的组，请确保其中一个用户帐户是登录到该设备的第一个帐户。</span><span class="sxs-lookup"><span data-stu-id="b6b38-392">If you have assigned the kiosk configuration profile to a group that contains users, make sure that one of those user accounts is the first account to sign in to the device.</span></span>

<span data-ttu-id="b6b38-393">在 OOBE 期间，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b6b38-393">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="b6b38-394">使用属于 **用户登录类型** 组的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="b6b38-394">Sign in by using the account that belongs to the **User logon type** group.</span></span>
1. <span data-ttu-id="b6b38-395">注册该设备。</span><span class="sxs-lookup"><span data-stu-id="b6b38-395">Enroll the device.</span></span>
1. <span data-ttu-id="b6b38-396">等待要下载和安装的展台配置文件中的任何应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-396">Wait for any apps that are part of the kiosk configuration profile to download and install.</span></span> <span data-ttu-id="b6b38-397">另外，请等待策略应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-397">Also, wait for policies to be applied.</span></span>  
1. <span data-ttu-id="b6b38-398">在 OOBE 完成后，可以通过 Microsoft 应用商店或旁加载来安装其他应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-398">After OOBE finishes, you can install additional apps from the Microsoft store or by sideloading.</span></span> <span data-ttu-id="b6b38-399">设备所属的组[所需的应用](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)将自动安装。</span><span class="sxs-lookup"><span data-stu-id="b6b38-399">[Required apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) for the group that the device belongs to install automatically.</span></span>
1. <span data-ttu-id="b6b38-400">安装完成后，重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="b6b38-400">After the installation finishes, restart the device.</span></span>

<span data-ttu-id="b6b38-401">下次使用属于 **用户登录类型** 的帐户登录到设备时，kiosk 应用应会自动启动。</span><span class="sxs-lookup"><span data-stu-id="b6b38-401">The next time you sign in to the device by using an account that belongs to the **User logon type**, the kiosk app should automatically launch.</span></span>

<span data-ttu-id="b6b38-402">如果此时未看到展台配置，请 [检查分配状态](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-402">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a><span data-ttu-id="b6b38-403">使用预配包设置单个应用程序或多应用展台</span><span class="sxs-lookup"><span data-stu-id="b6b38-403">Use a provisioning package to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="b6b38-404">若要使用预配包设置展台模式，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="b6b38-404">To set up kiosk mode by using a provisioning package, follow these steps.</span></span>

1. <span data-ttu-id="b6b38-405">[创建定义 kiosk 配置的 XML 文件](#ppkioskconfig)，包括 [开始布局](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-405">[Create an XML file that defines the kiosk configuration.](#ppkioskconfig), including a [Start layout](#start-layout-for-hololens).</span></span>
2. [<span data-ttu-id="b6b38-406">将 XML 文件添加到预配包。</span><span class="sxs-lookup"><span data-stu-id="b6b38-406">Add the XML file to a provisioning package.</span></span>](#ppconfigadd)
3. [<span data-ttu-id="b6b38-407">将预配包应用于 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="b6b38-407">Apply the provisioning package to HoloLens.</span></span>](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a><span data-ttu-id="b6b38-408">预配包，步骤 1 &ndash; 创建展台配置 XML 文件</span><span class="sxs-lookup"><span data-stu-id="b6b38-408">Provisioning package, step 1 &ndash; Create a kiosk configuration XML file</span></span>

<span data-ttu-id="b6b38-409">按照 [常规说明为 Windows desktop 创建展台配置 XML 文件](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)，但以下情况除外：</span><span class="sxs-lookup"><span data-stu-id="b6b38-409">Follow [the general instructions to create a kiosk configuration XML file for Windows desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), except for the following:</span></span>

- <span data-ttu-id="b6b38-410">不要包括经典 Windows 应用程序 (Win32) 。</span><span class="sxs-lookup"><span data-stu-id="b6b38-410">Do not include Classic Windows applications (Win32).</span></span> <span data-ttu-id="b6b38-411">HoloLens 不支持这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="b6b38-411">HoloLens does not support these applications.</span></span>
- <span data-ttu-id="b6b38-412">使用适用于 HoloLens 的 [占位符开始布局 XML](#start-layout-for-hololens) 。</span><span class="sxs-lookup"><span data-stu-id="b6b38-412">Use the [placeholder Start layout XML](#start-layout-for-hololens) for HoloLens.</span></span>
- <span data-ttu-id="b6b38-413">可选：向展台配置添加来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="b6b38-413">Optional: Add guest access to the kiosk configuration</span></span>

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a><span data-ttu-id="b6b38-414">可选：向展台配置添加来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="b6b38-414">Optional: Add guest access to the kiosk configuration</span></span>

<span data-ttu-id="b6b38-415">在 XML 文件的 "配置" [ 部分](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)中，可以配置名为 "**访问者**" 的特殊组，以允许来宾使用展台。</span><span class="sxs-lookup"><span data-stu-id="b6b38-415">In the [**Configs** section of the XML file](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), you can configure a special group named **Visitor** to allow guests to use the kiosk.</span></span> <span data-ttu-id="b6b38-416">当展台配置为支持 **访问者** 特殊组时，会将 "**来宾**" 选项添加到登录页。</span><span class="sxs-lookup"><span data-stu-id="b6b38-416">When the kiosk is configured to support the **Visitor** special group, a "**Guest**" option is added to the sign-in page.</span></span> <span data-ttu-id="b6b38-417">**Guest** 帐户不需要密码，当帐户注销时，将删除与该帐户关联的任何数据。</span><span class="sxs-lookup"><span data-stu-id="b6b38-417">The **Guest** account does not require a password, and any data that is associated with the account is deleted when the account signs out.</span></span>

<span data-ttu-id="b6b38-418">若要启用 **来宾** 帐户，请将以下代码片段添加到展台配置 XML：</span><span class="sxs-lookup"><span data-stu-id="b6b38-418">To enable the **Guest** account, add the following snippet to your kiosk configuration XML:</span></span>

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a><span data-ttu-id="b6b38-419">HoloLens 的占位符开始布局</span><span class="sxs-lookup"><span data-stu-id="b6b38-419">Placeholder Start layout for HoloLens</span></span>

<span data-ttu-id="b6b38-420">如果使用 [预配包](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 配置多应用展台，此过程需要开始布局。</span><span class="sxs-lookup"><span data-stu-id="b6b38-420">If you use a [provisioning package](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) to configure a multi-app kiosk, the procedure requires a Start layout.</span></span> <span data-ttu-id="b6b38-421">Windows 全息 for Business 不支持开始布局自定义。</span><span class="sxs-lookup"><span data-stu-id="b6b38-421">Start layout customization isn't supported in Windows Holographic for Business.</span></span> <span data-ttu-id="b6b38-422">因此，您必须使用占位符开始布局。</span><span class="sxs-lookup"><span data-stu-id="b6b38-422">Therefore, you'll have to use a placeholder Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="b6b38-423">由于单应用展台会在用户登录时启动展台应用，因此它不使用 "开始" 菜单，并且无需具有开始布局。</span><span class="sxs-lookup"><span data-stu-id="b6b38-423">Because a single-app kiosk starts the kiosk app when a user signs in, it does not use a Start menu and does not have to have a Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="b6b38-424">如果使用 [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 设置多应用展台，则可以选择使用 "开始布局"。</span><span class="sxs-lookup"><span data-stu-id="b6b38-424">If you use [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) to set up a multi-app kiosk, you can optionally use a Start layout.</span></span> <span data-ttu-id="b6b38-425">有关详细信息，请参阅 [MDM (Intune 的占位符启动布局文件和其他) ](#start-layout-file-for-mdm-intune-and-others)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-425">For more information, see [Placeholder Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

<span data-ttu-id="b6b38-426">对于 "开始" 布局，请将以下 " **StartLayout** " 部分添加到展台预配 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="b6b38-426">For the Start layout, add the following **StartLayout** section to the kiosk provisioning XML file:</span></span>

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a><span data-ttu-id="b6b38-427">MDM (Intune 和其他人的占位符开始布局文件) </span><span class="sxs-lookup"><span data-stu-id="b6b38-427">Placeholder Start layout file for MDM (Intune and others)</span></span>

<span data-ttu-id="b6b38-428">将以下示例另存为 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="b6b38-428">Save the following sample as an XML file.</span></span> <span data-ttu-id="b6b38-429">在 Microsoft Intune (或另一个提供展台配置文件) 的 MDM 服务中配置多应用展台时，可以使用此文件。</span><span class="sxs-lookup"><span data-stu-id="b6b38-429">You can use this file when you configure the multi-app kiosk in Microsoft Intune (or in another MDM service that provides a kiosk profile).</span></span>

> [!NOTE]
> <span data-ttu-id="b6b38-430">如果需要使用自定义设置和完整的 XML 配置在 MDM 服务中设置展台，请使用 [预配包的启动布局说明](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-430">If you have to use a custom setting and full XML configuration to set up a kiosk in your MDM service, use the [Start layout instructions for a provisioning package](#start-layout-for-hololens).</span></span>

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a><span data-ttu-id="b6b38-431">Prov.</span><span class="sxs-lookup"><span data-stu-id="b6b38-431">Prov.</span></span> <span data-ttu-id="b6b38-432">包，步骤 2 &ndash; 将展台配置 XML 文件添加到预配包</span><span class="sxs-lookup"><span data-stu-id="b6b38-432">package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package</span></span>

1. <span data-ttu-id="b6b38-433">打开 [Windows 配置设计器](https://www.microsoft.com/store/apps/9nblggh4tx22)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-433">Open [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span>
1. <span data-ttu-id="b6b38-434">选择 " **高级设置**"，输入项目的名称，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b6b38-434">Select **Advanced provisioning**, enter a name for your project, and then select **Next**.</span></span>
1. <span data-ttu-id="b6b38-435">选择 " **Windows 10 全息** 版"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b6b38-435">Select **Windows 10 Holographic**, and then select **Next**.</span></span>
1. <span data-ttu-id="b6b38-436">选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="b6b38-436">Select **Finish**.</span></span> <span data-ttu-id="b6b38-437">此时将打开你的程序包的工作区。</span><span class="sxs-lookup"><span data-stu-id="b6b38-437">The workspace for your package opens.</span></span>
1. <span data-ttu-id="b6b38-438">选择 "**运行时设置**"  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**。</span><span class="sxs-lookup"><span data-stu-id="b6b38-438">Select **Runtime settings** > **AssignedAccess** > **MultiAppAssignedAccessSettings**.</span></span>
1. <span data-ttu-id="b6b38-439">在中心窗格中，选择 " **浏览** " 以查找并选择已创建的展台配置 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="b6b38-439">In the center pane, select **Browse** to locate and select the kiosk configuration XML file that you created.</span></span>

   ![Windows 配置设计器中的 MultiAppAssignedAccessSettings 字段的屏幕截图](./images/multiappassignedaccesssettings.png)

1. <span data-ttu-id="b6b38-441">可选。</span><span class="sxs-lookup"><span data-stu-id="b6b38-441">**Optional**.</span></span> <span data-ttu-id="b6b38-442"> (如果要在设备的初始设置后应用预配包，并且展台设备上已有管理员用户，请跳过此步骤。 ) 选择 " **运行时设置** &gt; **帐户** &gt; " " **用户**"，然后创建用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b6b38-442">(If you want to apply the provisioning package after the initial setup of the device, and there is an admin user already available on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a user account.</span></span> <span data-ttu-id="b6b38-443">提供 "用户名" 和 "密码"，然后选择 " **UserGroup**  >  **Administrators**"。</span><span class="sxs-lookup"><span data-stu-id="b6b38-443">Provide a user name and password, and then select **UserGroup** > **Administrators**.</span></span>  
  
     <span data-ttu-id="b6b38-444">通过使用此帐户，你可以查看预配状态和日志。</span><span class="sxs-lookup"><span data-stu-id="b6b38-444">By using this account, you can view the provisioning status and logs.</span></span>  
1. <span data-ttu-id="b6b38-445">可选。</span><span class="sxs-lookup"><span data-stu-id="b6b38-445">**Optional**.</span></span> <span data-ttu-id="b6b38-446"> (如果你已在展台设备上拥有非管理员帐户，请跳过此步骤。 ) 选择 " **运行时设置** &gt; **帐户** &gt; **用户**"，然后创建一个本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b6b38-446">(If you already have a non-admin account on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a local user account.</span></span> <span data-ttu-id="b6b38-447">确保用户名与你在配置 XML 中指定的帐户相同。</span><span class="sxs-lookup"><span data-stu-id="b6b38-447">Make sure that the user name is the same as for the account that you specify in the configuration XML.</span></span> <span data-ttu-id="b6b38-448">选择 **UserGroup**  >  **Standard Users**。</span><span class="sxs-lookup"><span data-stu-id="b6b38-448">Select **UserGroup** > **Standard Users**.</span></span>
1. <span data-ttu-id="b6b38-449">选择“文件” > “保存”。</span><span class="sxs-lookup"><span data-stu-id="b6b38-449">Select **File** > **Save**.</span></span>
1. <span data-ttu-id="b6b38-450">选择 "**导出**  >  **设置包**"，然后选择 "**所有者**  >  **IT 管理员**"。这会将此预配包的优先级设置为高于从其他源应用于此设备的预配包。</span><span class="sxs-lookup"><span data-stu-id="b6b38-450">Select **Export** > **Provisioning package**, and then select **Owner** > **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages that are applied to this device from other sources.</span></span>
1. <span data-ttu-id="b6b38-451">选择“**下一页**”。</span><span class="sxs-lookup"><span data-stu-id="b6b38-451">Select **Next**.</span></span>
1. <span data-ttu-id="b6b38-452">在 " **设置包安全性** " 页上，选择一个安全选项。</span><span class="sxs-lookup"><span data-stu-id="b6b38-452">On the **Provisioning package security** page, select a security option.</span></span>
   > [!IMPORTANT]  
   > <span data-ttu-id="b6b38-453">如果选择 " **启用包签名**"，则还必须选择用于对包进行签名的有效证书。</span><span class="sxs-lookup"><span data-stu-id="b6b38-453">If you select **Enable package signing**, you also have to select a valid certificate to use for signing the package.</span></span> <span data-ttu-id="b6b38-454">为此，请选择 " **浏览** "，然后选择要用于对包进行签名的证书。</span><span class="sxs-lookup"><span data-stu-id="b6b38-454">To do this, select **Browse** and select the certificate that you want to use to sign the package.</span></span>
   
   > [!CAUTION]  
   > <span data-ttu-id="b6b38-455">不要选择 " **启用包加密**"。</span><span class="sxs-lookup"><span data-stu-id="b6b38-455">Do not select **Enable package encryption**.</span></span> <span data-ttu-id="b6b38-456">在 HoloLens 设备上，此设置会导致预配失败。</span><span class="sxs-lookup"><span data-stu-id="b6b38-456">On HoloLens devices, this setting causes provisioning to fail.</span></span>
1. <span data-ttu-id="b6b38-457">选择“**下一页**”。</span><span class="sxs-lookup"><span data-stu-id="b6b38-457">Select **Next**.</span></span>
1. <span data-ttu-id="b6b38-458">指定生成时要在其中进行预配包的输出位置。</span><span class="sxs-lookup"><span data-stu-id="b6b38-458">Specify the output location where you want the provisioning package to go when it's built.</span></span> <span data-ttu-id="b6b38-459">默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。</span><span class="sxs-lookup"><span data-stu-id="b6b38-459">By default, Windows Configuration Designer uses the project folder as the output location.</span></span> <span data-ttu-id="b6b38-460">如果要更改输出位置，请选择 " **浏览**"。</span><span class="sxs-lookup"><span data-stu-id="b6b38-460">If you want to change the output location, select **Browse**.</span></span> <span data-ttu-id="b6b38-461">完成后，选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="b6b38-461">When you are finished, select **Next**.</span></span>
1. <span data-ttu-id="b6b38-462">选择 " **生成** " 开始生成包。</span><span class="sxs-lookup"><span data-stu-id="b6b38-462">Select **Build** to start building the package.</span></span> <span data-ttu-id="b6b38-463">无需花费太长时间即可构建设置包。</span><span class="sxs-lookup"><span data-stu-id="b6b38-463">The provisioning package doesn't take long to build.</span></span> <span data-ttu-id="b6b38-464">"生成" 页显示项目信息，进度栏指示生成状态。</span><span class="sxs-lookup"><span data-stu-id="b6b38-464">The build page displays the project information, and the progress bar indicates the build status.</span></span>

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a><span data-ttu-id="b6b38-465">预配包，步骤 3 &ndash; 将预配包应用于 HoloLens</span><span class="sxs-lookup"><span data-stu-id="b6b38-465">Provisioning package, step 3 &ndash; Apply the provisioning package to HoloLens</span></span>

<span data-ttu-id="b6b38-466">本文提供了在以下情况下应用预配包的详细说明：</span><span class="sxs-lookup"><span data-stu-id="b6b38-466">The "Configure HoloLens by using a provisioning package" article provides detailed instructions to apply the provisioning package under the following circumstances:</span></span>

- <span data-ttu-id="b6b38-467">最初可以 [在安装过程中将预配包应用于 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-467">You can initially [apply a provisioning package to HoloLens during setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).</span></span>

- <span data-ttu-id="b6b38-468">你还可以 [在安装完成后将预配包应用于 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-468">You can also [apply a provisioning package to HoloLens after setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).</span></span>

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a><span data-ttu-id="b6b38-469">使用 Windows 设备门户设置单应用展台</span><span class="sxs-lookup"><span data-stu-id="b6b38-469">Use the Windows Device Portal to set up a single-app kiosk</span></span>

<span data-ttu-id="b6b38-470">若要使用 Windows 设备门户设置展台模式，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="b6b38-470">To set up kiosk mode by using the Windows Device Portal, follow these steps.</span></span>

1. <span data-ttu-id="b6b38-471">[将 HoloLens 设备设置为使用 Windows 设备门户](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-471">[Set up the HoloLens device to use the Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal).</span></span> <span data-ttu-id="b6b38-472">Device Portal 是 HoloLens 上的 Web 服务器，你可以从电脑上的 Web 浏览器连接到它。</span><span class="sxs-lookup"><span data-stu-id="b6b38-472">The Device Portal is a web server on your HoloLens that you can connect to from a web browser on your PC.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="b6b38-473">将 HoloLens 设置为使用设备门户时，必须在设备上启用开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="b6b38-473">When you set up HoloLens to use the Device Portal, you have to enable Developer Mode on the device.</span></span> <span data-ttu-id="b6b38-474">使用 Windows 全息 for Business 的设备上的开发人员模式，可用于装载应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-474">Developer Mode on a device that has Windows Holographic for Business enables you to side-load apps.</span></span> <span data-ttu-id="b6b38-475">但是，此设置会创建一个风险，用户可在其中安装尚未由 Microsoft Store 认证的应用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-475">However, this setting creates a risk that a user can install apps that have not been certified by the Microsoft Store.</span></span> <span data-ttu-id="b6b38-476">管理员可以通过使用 [策略 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)中的 **ApplicationManagement/AllowDeveloper 解锁** 设置来阻止启用开发人员模式的功能。</span><span class="sxs-lookup"><span data-stu-id="b6b38-476">Administrators can block the ability to enable Developer Mode by using the **ApplicationManagement/AllowDeveloper Unlock** setting in the [Policy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider).</span></span> [<span data-ttu-id="b6b38-477">了解有关开发人员模式的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b6b38-477">Learn more about Developer Mode.</span></span>](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. <span data-ttu-id="b6b38-478">在计算机上，使用 [wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 或 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="b6b38-478">On a computer, connect to the HoloLens by using [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) or [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).</span></span>

1. <span data-ttu-id="b6b38-479">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b6b38-479">Do one of the following:</span></span>
   - <span data-ttu-id="b6b38-480">如果是首次连接到 Windows 设备门户，请 [创建用户名和密码](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span><span class="sxs-lookup"><span data-stu-id="b6b38-480">If you are connecting to the Windows Device Portal for the first time, [create a user name and password](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span></span>
   - <span data-ttu-id="b6b38-481">输入先前设置的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="b6b38-481">Enter the user name and password that you previously set up.</span></span>

    > [!TIP]
    > <span data-ttu-id="b6b38-482">如果发现浏览器中的证书错误，请遵循[以下疑难解答步骤](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)。</span><span class="sxs-lookup"><span data-stu-id="b6b38-482">If you see a certificate error in the browser, follow [these troubleshooting steps](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).</span></span>

1. <span data-ttu-id="b6b38-483">在 Windows 设备门户中，选择 " **展台模式**"。</span><span class="sxs-lookup"><span data-stu-id="b6b38-483">In the Windows Device Portal, select **Kiosk Mode**.</span></span>

1. <span data-ttu-id="b6b38-484">选择 " **启用展台模式**"，选择要在设备启动时运行的应用，然后选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="b6b38-484">Select **Enable Kiosk Mode**, select an app to run when the device starts, and then select **Save**.</span></span>

    ![展台模式](images/kiosk.png)
1. <span data-ttu-id="b6b38-486">重新启动 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="b6b38-486">Restart HoloLens.</span></span> <span data-ttu-id="b6b38-487">如果仍然打开了设备门户页面，可以选择页面顶部的 " **重新启动** "。</span><span class="sxs-lookup"><span data-stu-id="b6b38-487">If you still have your Device Portal page open, you can select **Restart** at the top of the page.</span></span>

> [!NOTE]
> <span data-ttu-id="b6b38-488">通过 ( 使用 "kioskModeEnabled" 值为 "true" 或 "false ) " 的/api/holographic/kioskmode/settings 和一个可选参数 ( "startupApp"，其中的值为包名称) ，可以通过设备门户的 REST API 设置展台模式。</span><span class="sxs-lookup"><span data-stu-id="b6b38-488">Kiosk Mode can be set via Device Portal’s REST API by doing a POST to /api/holographic/kioskmode/settings with one required query string parameter (“kioskModeEnabled” with a value of “true” or “false”) and one optional parameter (“startupApp” with a value of a package name).</span></span> <span data-ttu-id="b6b38-489">请记住，设备门户仅适用于开发人员，不应在非开发人员设备上启用。</span><span class="sxs-lookup"><span data-stu-id="b6b38-489">Please keep in mind that Device Portal is intended for developers only and should not be enabled on non-developer devices.</span></span> <span data-ttu-id="b6b38-490">在将来的更新/发布中，REST API 可能会更改。</span><span class="sxs-lookup"><span data-stu-id="b6b38-490">The REST API is subject to change in future updates/releases.</span></span>

## <a name="more-information"></a><span data-ttu-id="b6b38-491">更多信息</span><span class="sxs-lookup"><span data-stu-id="b6b38-491">More information</span></span>

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a><span data-ttu-id="b6b38-492">观看如何使用设置包配置展台。</span><span class="sxs-lookup"><span data-stu-id="b6b38-492">Watch how to configure a kiosk by using a provisioning package.</span></span>  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a><span data-ttu-id="b6b38-493">全局分配的访问–展台模式</span><span class="sxs-lookup"><span data-stu-id="b6b38-493">Global Assigned Access – Kiosk Mode</span></span>
- <span data-ttu-id="b6b38-494">通过启用在系统级别应用展台模式的新展台方法，降低了展台的标识管理。</span><span class="sxs-lookup"><span data-stu-id="b6b38-494">Reduced Identity management for Kiosk, by enabling new Kiosk method that applies Kiosk mode at the system level.</span></span>

<span data-ttu-id="b6b38-495">这项新功能可让 IT 管理员为多个 app 展台模式（在系统级上适用）配置一个 HoloLens 2 设备，该模式与系统上的任何标识都无关联，并且适用于登录到该设备的所有用户。</span><span class="sxs-lookup"><span data-stu-id="b6b38-495">This new feature allows an IT Admin to configure a HoloLens 2 device for multiple app kiosk mode which is applicable at system level, has no affinity with any identity on the system and applies to everyone who signs into the device.</span></span> <span data-ttu-id="b6b38-496">有关此新功能的更多详细信息，请参阅 [HoloLens 全局分配的访问展台](hololens-global-assigned-access-kiosk.md) 文档。</span><span class="sxs-lookup"><span data-stu-id="b6b38-496">See the [HoloLens global assigned access kiosk](hololens-global-assigned-access-kiosk.md) documentation for more details on this new feature.</span></span>

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a><span data-ttu-id="b6b38-497">在多应用展台模式下自动启动应用程序</span><span class="sxs-lookup"><span data-stu-id="b6b38-497">Automatic launch of an application in multiple-app kiosk mode</span></span> 
- <span data-ttu-id="b6b38-498">自动应用启动的聚焦体验，进一步增加了为展台模式体验选择的 UI 和应用选择。</span><span class="sxs-lookup"><span data-stu-id="b6b38-498">Focused experience with automatic app launch, further increasing the UI and app selections chosen for Kiosk mode experiences.</span></span>

<span data-ttu-id="b6b38-499">仅适用于多应用展台模式，并且只有1个应用可以使用下面的突出显示属性指定为自动启动。</span><span class="sxs-lookup"><span data-stu-id="b6b38-499">Applies only to multiple-app kiosk mode and only 1 app can be designated to auto-launch using highlighted attribute below in Assigned Access configuration.</span></span> 

<span data-ttu-id="b6b38-500">当用户登录时，应用程序将自动启动。</span><span class="sxs-lookup"><span data-stu-id="b6b38-500">Application is automatically launched when user signs-in.</span></span> 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a><span data-ttu-id="b6b38-501">用于处理故障的展台模式行为更改</span><span class="sxs-lookup"><span data-stu-id="b6b38-501">Kiosk mode behavior changes for handling of failures</span></span>
- <span data-ttu-id="b6b38-502">通过消除展台模式故障中的可用应用，更安全的展台模式。</span><span class="sxs-lookup"><span data-stu-id="b6b38-502">More secure Kiosk mode by eliminating available apps on Kiosk mode failures.</span></span> 

<span data-ttu-id="b6b38-503">早于在应用展台模式时遇到故障，HoloLens 用于显示 "开始" 菜单中的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="b6b38-503">Earlier on encountering failures in applying kiosk mode, HoloLens used to show up all applications in start menu.</span></span> <span data-ttu-id="b6b38-504">现在，在 Windows 全息版20H2 中，如果出现故障，则在 "开始" 菜单中将不会显示任何应用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b6b38-504">Now in Windows Holographic version 20H2 in the case of failures no apps will be shown in the start menu as below:</span></span> 

![显示故障时的展台模式的图像。](images/hololens-kiosk-failure-behavior.png )

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a><span data-ttu-id="b6b38-506">缓存 Azure AD 脱机展台的组成员身份</span><span class="sxs-lookup"><span data-stu-id="b6b38-506">Cache Azure AD Group membership for offline Kiosk</span></span>
- <span data-ttu-id="b6b38-507">已将脱机展台用于 Azure AD 组，最多60天。</span><span class="sxs-lookup"><span data-stu-id="b6b38-507">Enabled Offline Kiosks to be used with Azure AD groups for up to 60 days.</span></span>

<span data-ttu-id="b6b38-508">此策略控制允许使用 Azure AD 组成员身份缓存来指定已登录用户 Azure AD 组的指定访问配置的天数。</span><span class="sxs-lookup"><span data-stu-id="b6b38-508">This policy controls for how many days, Azure AD group membership cache is allowed to be used for Assigned Access configurations targeting Azure AD groups for signed in user.</span></span> <span data-ttu-id="b6b38-509">一旦将此策略值设置为大于0的值，则不使用缓存。</span><span class="sxs-lookup"><span data-stu-id="b6b38-509">Once this policy value is set to value greater than 0 only then cache is used otherwise not.</span></span>  

<span data-ttu-id="b6b38-510">名称： AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span><span class="sxs-lookup"><span data-stu-id="b6b38-510">Name: AADGroupMembershipCacheValidityInDays URI value: ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span></span>

<span data-ttu-id="b6b38-511">最小值为0天</span><span class="sxs-lookup"><span data-stu-id="b6b38-511">Min - 0 days</span></span>  
<span data-ttu-id="b6b38-512">最大-60 天</span><span class="sxs-lookup"><span data-stu-id="b6b38-512">Max - 60 days</span></span> 

<span data-ttu-id="b6b38-513">正确使用此策略的步骤：</span><span class="sxs-lookup"><span data-stu-id="b6b38-513">Steps to use this policy correctly:</span></span> 
1. <span data-ttu-id="b6b38-514">为展台 Azure AD 组创建设备配置文件，并将其分配给 HoloLens 设备 (s) 。</span><span class="sxs-lookup"><span data-stu-id="b6b38-514">Create a device configuration profile for kiosk targeting Azure AD groups and assign it to HoloLens device(s).</span></span> 
1. <span data-ttu-id="b6b38-515">创建基于自定义 OMA URI 的设备配置，该配置将此策略值设置为所需的天数 (> 0) 并将其分配给 HoloLens 设备 () 。</span><span class="sxs-lookup"><span data-stu-id="b6b38-515">Create a custom OMA URI based device configuration which sets this policy value to desired number of days (> 0) and assign it to HoloLens device(s).</span></span> 
    1. <span data-ttu-id="b6b38-516">应在 OMA-URI 文本框中输入 URI 值作为/Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays。</span><span class="sxs-lookup"><span data-stu-id="b6b38-516">The URI value should be entered in OMA-URI text box as ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays</span></span>
    1. <span data-ttu-id="b6b38-517">该值可以介于最小值/最大允许值之间。</span><span class="sxs-lookup"><span data-stu-id="b6b38-517">The value can be between min / max allowed.</span></span>
1. <span data-ttu-id="b6b38-518">注册 HoloLens 设备，并验证这两项配置是否适用于设备。</span><span class="sxs-lookup"><span data-stu-id="b6b38-518">Enroll HoloLens devices and verify both configurations get applied to the device.</span></span> 
1. <span data-ttu-id="b6b38-519">当 internet 可用时，让 Azure AD 用户1登录，一旦用户登录并 Azure AD 组成员身份已成功确认，就会创建缓存。</span><span class="sxs-lookup"><span data-stu-id="b6b38-519">Let Azure AD user 1 sign-in when internet is available, once user signs-in and Azure AD group membership is confirmed successfully, cache will be created.</span></span> 
1. <span data-ttu-id="b6b38-520">现在 Azure AD 用户1可以使 HoloLens 脱机并将其用于展台模式，只要策略值允许 X 天。</span><span class="sxs-lookup"><span data-stu-id="b6b38-520">Now Azure AD user 1 can take HoloLens offline and use it for kiosk mode as long as policy value allows for X number of days.</span></span> 
1. <span data-ttu-id="b6b38-521">对于任何其他 Azure AD 用户 N，可以重复执行步骤4和步骤5。以下是任何 Azure AD 用户都必须使用 Internet 登录设备，因此至少可以确定它们是展台配置所针对的 Azure AD 组的成员。</span><span class="sxs-lookup"><span data-stu-id="b6b38-521">Steps 4 and 5 can be repeated for any other Azure AD user N. Key point here is that any Azure AD user must sign-in to device using Internet so at least once we can determine that they are member of Azure AD group to which Kiosk configuration is targeted.</span></span> 
 
> [!NOTE]
> <span data-ttu-id="b6b38-522">直到 Azure AD 执行步骤4后，才会在 "断开连接" 环境中遇到失败行为。</span><span class="sxs-lookup"><span data-stu-id="b6b38-522">Until step 4 is performed for a Azure AD user will experience failure behavior mentioned in “disconnected” environments.</span></span> 


## <a name="xml-kiosk-code-samples-for-hololens"></a><span data-ttu-id="b6b38-523">用于 HoloLens 的 XML 展台代码示例</span><span class="sxs-lookup"><span data-stu-id="b6b38-523">XML Kiosk Code Samples for HoloLens</span></span>

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a><span data-ttu-id="b6b38-524">面向 Azure AD 组的多个 app 展台模式。</span><span class="sxs-lookup"><span data-stu-id="b6b38-524">Multiple app kiosk mode targeting an Azure AD group.</span></span> 
<span data-ttu-id="b6b38-525">这一展台为 Azure AD 组中的用户部署了展台，他们将启用展台，其中包含3个应用：设置、远程协助和反馈中心。</span><span class="sxs-lookup"><span data-stu-id="b6b38-525">This kiosk deploys a Kiosk that for users in the Azure AD group, they will have a Kiosk enabled that includes the 3 apps: Settings, Remote Assist, and Feedback Hub.</span></span> <span data-ttu-id="b6b38-526">若要修改此示例以立即使用，请确保更改下面突出显示的 GUID，以匹配您自己的 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="b6b38-526">To modify this sample to be used immediately, make sure to change the GUID highlighted below to match an Azure AD Group of your own.</span></span> 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a><span data-ttu-id="b6b38-527">面向 Azure AD 帐户的多个 app 展台模式。</span><span class="sxs-lookup"><span data-stu-id="b6b38-527">Multiple app kiosk mode targeting Azure AD account.</span></span>
<span data-ttu-id="b6b38-528">这一展台为单一用户部署了展台，他们将启用展台，其中包含3个应用：设置、远程协助和反馈中心。</span><span class="sxs-lookup"><span data-stu-id="b6b38-528">This kiosk deploys a Kiosk for a single user, they will have a Kiosk enabled that includes the 3 apps: Settings, Remote Assist, and Feedback Hub.</span></span> <span data-ttu-id="b6b38-529">若要立即修改此示例，请确保更改下面突出显示的帐户，使其与你自己的 Azure AD 帐户相匹配。</span><span class="sxs-lookup"><span data-stu-id="b6b38-529">To modify this sample to be used immediately, make sure to change the account highlighted below to match an Azure AD Account of your own.</span></span> 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

