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
ms.openlocfilehash: c4c4b533538ab7998f8438d7cc0c2f3d88143ec6
ms.sourcegitcommit: 4e168380c23e8463438aa8a1388baf8d5ac1a1ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154183"
---
# <span data-ttu-id="bbceb-103">将 HoloLens 设置为 Kiosk</span><span class="sxs-lookup"><span data-stu-id="bbceb-103">Set up HoloLens as a kiosk</span></span>

<span data-ttu-id="bbceb-104">你可以将 HoloLens 设备配置为固定用途的设备（也称为 *展台*），方法是将设备配置为在展台模式下运行。</span><span class="sxs-lookup"><span data-stu-id="bbceb-104">You can configure a HoloLens device to function as a fixed-purpose device, also called a *kiosk*, by configuring the device to run in kiosk mode.</span></span> <span data-ttu-id="bbceb-105">展台模式限制设备上可用 (或用户) 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bbceb-105">Kiosk mode limits the applications (or users) that are available on the device.</span></span> <span data-ttu-id="bbceb-106">展台模式是一种方便的功能，可用于将 HoloLens 设备专用于商业应用，或在应用演示中使用 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="bbceb-106">Kiosk mode is a convenient feature that you can use to dedicate a HoloLens device to business apps, or to use the HoloLens device in an app demo.</span></span>

<span data-ttu-id="bbceb-107">本文提供有关特定于 HoloLens 设备的展台配置方面的信息。</span><span class="sxs-lookup"><span data-stu-id="bbceb-107">This article provides information about aspects of kiosk configuration that are specific to HoloLens devices.</span></span> <span data-ttu-id="bbceb-108">有关不同类型的基于 Windows 的网亭以及如何配置它们的常规信息，请参阅 [在 Windows 桌面版上配置网亭和数字签名](https://docs.microsoft.com/windows/configuration/kiosk-methods)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-108">For general information about the different types of Windows-based kiosks and how to configure them, see [Configure kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).</span></span>  

> [!IMPORTANT]  
> <span data-ttu-id="bbceb-109">展台模式确定当用户登录到设备时，哪些应用可用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-109">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="bbceb-110">但是，展台模式不是一种安全方法。</span><span class="sxs-lookup"><span data-stu-id="bbceb-110">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="bbceb-111">它不会阻止 "允许" 应用打开不允许的另一个应用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-111">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="bbceb-112">为了阻止应用或进程打开，请使用 [Windows Defender 应用程序控件 (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 来创建相应的策略。</span><span class="sxs-lookup"><span data-stu-id="bbceb-112">In order to block apps or processes from opening, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span>
>
> <span data-ttu-id="bbceb-113">了解有关 Microsoft 服务的详细信息，以便为用户提供 HoloLens 2 使用的高级安全级别，请阅读有关 [状态分隔和隔离 Defender 保护](security-state-separation-isolation.md#defender-protections)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bbceb-113">Learn more about the Microsoft services to give users an advanced level of security that HoloLens 2 uses, read more about [State separation and isolation - Defender protections](security-state-separation-isolation.md#defender-protections).</span></span> <span data-ttu-id="bbceb-114">或了解如何 [使用 WDAC 和 Windows PowerShell 在 HoloLens 2 设备上使用 Microsoft Intune 允许或阻止应用](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-114">Or learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="bbceb-115">你可以在单个应用或多个应用配置中使用展台模式，并且可以使用三个进程之一来设置和部署展台配置。</span><span class="sxs-lookup"><span data-stu-id="bbceb-115">You can use kiosk mode in either a single-app or a multi-app configuration, and you can use one of three processes to set up and deploy the kiosk configuration.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="bbceb-116">删除多应用配置将删除分配的访问功能所创建的用户锁定配置文件。</span><span class="sxs-lookup"><span data-stu-id="bbceb-116">Deleting the multi-app configuration removes the user lockdown profiles that the assigned access feature created.</span></span> <span data-ttu-id="bbceb-117">但是，它不会还原所有策略更改。</span><span class="sxs-lookup"><span data-stu-id="bbceb-117">However, it does not revert all the policy changes.</span></span> <span data-ttu-id="bbceb-118">若要还原这些策略，必须将设备重置为出厂设置。</span><span class="sxs-lookup"><span data-stu-id="bbceb-118">To revert these policies, you have to reset the device to the factory settings.</span></span>

## <span data-ttu-id="bbceb-119">规划展台部署</span><span class="sxs-lookup"><span data-stu-id="bbceb-119">Plan the kiosk deployment</span></span>

<span data-ttu-id="bbceb-120">规划展台后，您需要能够回答以下问题。</span><span class="sxs-lookup"><span data-stu-id="bbceb-120">When planning your Kiosk you'll need to be able to answer the following questions.</span></span> <span data-ttu-id="bbceb-121">下面是阅读本页面时需要考虑的一些决策以及这些问题的一些注意事项。</span><span class="sxs-lookup"><span data-stu-id="bbceb-121">Here are some decisions to think about while reading this page and some considerations for these questions.</span></span>
1. **<span data-ttu-id="bbceb-122">谁将使用你的展台，以及他们 [ (s 的帐户) ](hololens-identity.md) 将使用哪种类型？</span><span class="sxs-lookup"><span data-stu-id="bbceb-122">Who will be using your Kiosk, and what [type of account(s)](hololens-identity.md) will they be using?</span></span>** <span data-ttu-id="bbceb-123">这是你可能已做出的决定，不应针对你的展台进行调整，但会影响稍后分配展台的方式。</span><span class="sxs-lookup"><span data-stu-id="bbceb-123">This is a decision you have likely already made and shouldn't be adjusted for the sake of your Kiosk, but will affect how the Kiosk is assigned later.</span></span>
1. **<span data-ttu-id="bbceb-124">您是否需要为每个用户/组提供不同的网亭，或者没有为某些展台启用该功能区？</span><span class="sxs-lookup"><span data-stu-id="bbceb-124">Do you need to have either different Kiosks per user/group or a Kiosk not enabled for some?</span></span>** <span data-ttu-id="bbceb-125">如果是这样，你将希望通过 XML 创建你的展台。</span><span class="sxs-lookup"><span data-stu-id="bbceb-125">If so, you'll want to create your Kiosk via XML.</span></span> 
1. **<span data-ttu-id="bbceb-126">您的展台中将有多少个应用？</span><span class="sxs-lookup"><span data-stu-id="bbceb-126">How many apps will be in your Kiosk?</span></span>** <span data-ttu-id="bbceb-127">如果你有多个应用，你将需要多应用展台。</span><span class="sxs-lookup"><span data-stu-id="bbceb-127">If you have more than 1 app, you'll need a multi-app Kiosk.</span></span> 
1. **<span data-ttu-id="bbceb-128">您的展台) 的应用 (s？</span><span class="sxs-lookup"><span data-stu-id="bbceb-128">Which app(s) will be in your Kiosk?</span></span>** <span data-ttu-id="bbceb-129">除了你自己的 Aumid，请使用下面的列表添加任何 In-Box 应用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-129">Please use our list of AUMIDs below to add any In-Box apps in addition to your own.</span></span>
1. **<span data-ttu-id="bbceb-130">如何计划部署展台？</span><span class="sxs-lookup"><span data-stu-id="bbceb-130">How do you plan to deploy your Kiosk?</span></span>** <span data-ttu-id="bbceb-131">如果你在 MDM 中注册设备，我们建议使用 MDM 部署你的展台。</span><span class="sxs-lookup"><span data-stu-id="bbceb-131">If you are enrolling device in MDM then we suggest using MDM to deploy your Kiosk.</span></span> <span data-ttu-id="bbceb-132">如果未使用 MDM，则可以使用预配包进行部署。</span><span class="sxs-lookup"><span data-stu-id="bbceb-132">If you are not using MDM then deployment with Provisioning Package is available.</span></span>  

### <span data-ttu-id="bbceb-133">展台模式要求</span><span class="sxs-lookup"><span data-stu-id="bbceb-133">Kiosk mode requirements</span></span>

<span data-ttu-id="bbceb-134">您可以将任何 HoloLens 2 设备配置为使用展台模式。</span><span class="sxs-lookup"><span data-stu-id="bbceb-134">You can configure any HoloLens 2 device to use kiosk mode.</span></span>

<span data-ttu-id="bbceb-135">若要将 HoloLens (第一代) 设备配置为使用展台模式，必须首先确保该设备运行的是 Windows 10 版本1803或更高版本。</span><span class="sxs-lookup"><span data-stu-id="bbceb-135">To configure a HoloLens (1st gen) device to use kiosk mode, you must first make sure that the device runs Windows 10, version 1803, or a later version.</span></span> <span data-ttu-id="bbceb-136">如果你已使用 Windows 设备恢复工具将 HoloLens (第一代) 设备恢复为默认版本，或者如果已安装了最新的更新，则设备已准备好进行配置。</span><span class="sxs-lookup"><span data-stu-id="bbceb-136">If you have used the Windows Device Recovery Tool to recover your HoloLens (1st gen) device to its default build, or if you have installed the most recent updates, your device is ready to configure.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="bbceb-137">若要帮助保护在展台模式下运行的设备，请考虑添加关闭诸如 USB 连接等功能的设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="bbceb-137">To help protect devices that run in kiosk mode, consider adding device management policies that turn off features such as USB connectivity.</span></span> <span data-ttu-id="bbceb-138">此外，检查更新铃声设置以确保在工作时间内不会自动更新。</span><span class="sxs-lookup"><span data-stu-id="bbceb-138">Additionally, check your update ring settings to make sure that automatic updates do not occur during business hours.</span></span>

### <span data-ttu-id="bbceb-139">在单应用展台或多应用展台之间做出选择</span><span class="sxs-lookup"><span data-stu-id="bbceb-139">Decide between a single-app kiosk or a multi-app kiosk</span></span>

<span data-ttu-id="bbceb-140">当用户登录到设备时，单应用展台会启动指定的应用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-140">A single-app kiosk starts the specified app when the user signs in to the device.</span></span> <span data-ttu-id="bbceb-141">"开始" 菜单已禁用，与 Cortana 一样。</span><span class="sxs-lookup"><span data-stu-id="bbceb-141">The Start menu is disabled, as is Cortana.</span></span> <span data-ttu-id="bbceb-142">HoloLens 2 设备不响应 [开始](hololens2-basic-usage.md#start-gesture) 手势。</span><span class="sxs-lookup"><span data-stu-id="bbceb-142">A HoloLens 2 device does not respond to the [Start](hololens2-basic-usage.md#start-gesture) gesture.</span></span> <span data-ttu-id="bbceb-143">HoloLens (第一代) 设备不会响应 [绽放](hololens1-basic-usage.md) 手势。</span><span class="sxs-lookup"><span data-stu-id="bbceb-143">A HoloLens (1st gen) device does not respond to the [bloom](hololens1-basic-usage.md) gesture.</span></span> <span data-ttu-id="bbceb-144">由于只有一个应用可以运行，因此用户无法放置其他应用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-144">Because only one app can run, the user cannot place other apps.</span></span>

<span data-ttu-id="bbceb-145">当用户登录到设备时，多应用展台显示 "开始" 菜单。</span><span class="sxs-lookup"><span data-stu-id="bbceb-145">A multi-app kiosk displays the Start menu when the user signs in to the device.</span></span> <span data-ttu-id="bbceb-146">展台配置确定哪些应用在 "开始" 菜单上可用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-146">The kiosk configuration determines which apps are available on the Start menu.</span></span> <span data-ttu-id="bbceb-147">你可以使用多应用展台为用户提供简单易懂的体验，只需向他们展示他们必须使用的功能，并删除不需要使用的功能。</span><span class="sxs-lookup"><span data-stu-id="bbceb-147">You can use a multi-app kiosk to provide an easy-to-understand experience for users by presenting to them only the things that they have to use, and removing the things they don't need to use.</span></span>

<span data-ttu-id="bbceb-148">下表列出了不同展台模式下的功能功能。</span><span class="sxs-lookup"><span data-stu-id="bbceb-148">The following table lists the feature capabilities in the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="bbceb-149">“开始”菜单</span><span class="sxs-lookup"><span data-stu-id="bbceb-149">Start menu</span></span> |<span data-ttu-id="bbceb-150">"快速操作" 菜单</span><span class="sxs-lookup"><span data-stu-id="bbceb-150">Quick Actions menu</span></span> |<span data-ttu-id="bbceb-151">摄像头和视频</span><span class="sxs-lookup"><span data-stu-id="bbceb-151">Camera and video</span></span> |<span data-ttu-id="bbceb-152">Miracast</span><span class="sxs-lookup"><span data-stu-id="bbceb-152">Miracast</span></span> |<span data-ttu-id="bbceb-153">Cortana</span><span class="sxs-lookup"><span data-stu-id="bbceb-153">Cortana</span></span> |<span data-ttu-id="bbceb-154">内置语音命令</span><span class="sxs-lookup"><span data-stu-id="bbceb-154">Built-in voice commands</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|<span data-ttu-id="bbceb-155">单应用展台</span><span class="sxs-lookup"><span data-stu-id="bbceb-155">Single-app kiosk</span></span> |<span data-ttu-id="bbceb-156">已禁用</span><span class="sxs-lookup"><span data-stu-id="bbceb-156">Disabled</span></span> |<span data-ttu-id="bbceb-157">已禁用</span><span class="sxs-lookup"><span data-stu-id="bbceb-157">Disabled</span></span>   |<span data-ttu-id="bbceb-158">已禁用</span><span class="sxs-lookup"><span data-stu-id="bbceb-158">Disabled</span></span> |<span data-ttu-id="bbceb-159">已禁用</span><span class="sxs-lookup"><span data-stu-id="bbceb-159">Disabled</span></span>   |<span data-ttu-id="bbceb-160">已禁用</span><span class="sxs-lookup"><span data-stu-id="bbceb-160">Disabled</span></span> |<span data-ttu-id="bbceb-161">已启用 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="bbceb-161">Enabled<sup>1</span></span></sup> |
|<span data-ttu-id="bbceb-162">多应用展台。</span><span class="sxs-lookup"><span data-stu-id="bbceb-162">Multi-app kiosk</span></span> |<span data-ttu-id="bbceb-163">启用</span><span class="sxs-lookup"><span data-stu-id="bbceb-163">Enabled</span></span> |<span data-ttu-id="bbceb-164">已启用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="bbceb-164">Enabled<sup>2</span></span></sup> |<span data-ttu-id="bbceb-165">可用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="bbceb-165">Available<sup>2</span></span></sup> |<span data-ttu-id="bbceb-166">可用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="bbceb-166">Available<sup>2</span></span></sup> |<span data-ttu-id="bbceb-167">可用 <sup> 2，3</span><span class="sxs-lookup"><span data-stu-id="bbceb-167">Available<sup>2, 3</span></span></sup>  |<span data-ttu-id="bbceb-168">已启用 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="bbceb-168">Enabled<sup>1</span></span></sup> |

> <sup><span data-ttu-id="bbceb-169">1与 </sup> 禁用的功能相关的语音命令不起作用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-169">1</sup> Voice commands that relate to disabled features do not function.</span></span>  
> <sup><span data-ttu-id="bbceb-170">2有关 </sup> 如何配置这些功能的详细信息，请参阅 [选择展台应用](#plan-kiosk-apps)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-170">2</sup> For more information about how to configure these features, see [Select kiosk apps](#plan-kiosk-apps).</span></span>  
> <sup><span data-ttu-id="bbceb-171">3 </sup> 即使禁用 Cortana，也会启用内置语音命令。</span><span class="sxs-lookup"><span data-stu-id="bbceb-171">3</sup> Even if Cortana is disabled, the built-in voice commands are enabled.</span></span>

<span data-ttu-id="bbceb-172">下表列出了不同展台模式的用户支持功能。</span><span class="sxs-lookup"><span data-stu-id="bbceb-172">The following table lists the user support features of the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="bbceb-173">支持的用户类型</span><span class="sxs-lookup"><span data-stu-id="bbceb-173">Supported user types</span></span> | <span data-ttu-id="bbceb-174">自动登录</span><span class="sxs-lookup"><span data-stu-id="bbceb-174">Automatic sign-in</span></span> | <span data-ttu-id="bbceb-175">多个访问级别</span><span class="sxs-lookup"><span data-stu-id="bbceb-175">Multiple access levels</span></span> |
| --- | --- | --- | --- |
|<span data-ttu-id="bbceb-176">单应用展台</span><span class="sxs-lookup"><span data-stu-id="bbceb-176">Single-app kiosk</span></span> |<span data-ttu-id="bbceb-177">托管服务帐户在 Azure Active Directory (AAD) 或本地帐户中 (MSA) </span><span class="sxs-lookup"><span data-stu-id="bbceb-177">Managed Service Account (MSA) in Azure Active Directory (AAD) or local account</span></span> |<span data-ttu-id="bbceb-178">是</span><span class="sxs-lookup"><span data-stu-id="bbceb-178">Yes</span></span> |<span data-ttu-id="bbceb-179">否</span><span class="sxs-lookup"><span data-stu-id="bbceb-179">No</span></span> |
|<span data-ttu-id="bbceb-180">多应用展台。</span><span class="sxs-lookup"><span data-stu-id="bbceb-180">Multi-app kiosk</span></span> |<span data-ttu-id="bbceb-181">AAD 帐户</span><span class="sxs-lookup"><span data-stu-id="bbceb-181">AAD account</span></span> |<span data-ttu-id="bbceb-182">否</span><span class="sxs-lookup"><span data-stu-id="bbceb-182">No</span></span> |<span data-ttu-id="bbceb-183">是</span><span class="sxs-lookup"><span data-stu-id="bbceb-183">Yes</span></span> |

<span data-ttu-id="bbceb-184">有关如何使用这些功能的示例，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="bbceb-184">For examples of how to use these capabilities, see the following table.</span></span>

|<span data-ttu-id="bbceb-185">使用单应用展台进行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bbceb-185">Use a single-app kiosk for:</span></span> |<span data-ttu-id="bbceb-186">使用多应用展台进行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bbceb-186">Use a multi-app kiosk for:</span></span> |
| --- | --- |
|<span data-ttu-id="bbceb-187">仅运行新员工的 Dynamics 365 指南的设备。</span><span class="sxs-lookup"><span data-stu-id="bbceb-187">A device that runs only a Dynamics 365 Guide for new employees.</span></span> |<span data-ttu-id="bbceb-188">为一系列员工运行指南和远程协助的设备。</span><span class="sxs-lookup"><span data-stu-id="bbceb-188">A device that runs both Guides and Remote Assistance for a range of employees.</span></span> |
|<span data-ttu-id="bbceb-189">仅运行自定义应用的设备。</span><span class="sxs-lookup"><span data-stu-id="bbceb-189">A device that runs only a custom app.</span></span> |<span data-ttu-id="bbceb-190">作为大多数用户的展台工作的设备 (仅运行自定义应用) ，但作为特定用户组的标准设备运行。</span><span class="sxs-lookup"><span data-stu-id="bbceb-190">A device that functions as a kiosk for most users (running only a custom app), but functions as a standard device for a specific group of users.</span></span> |

### <span data-ttu-id="bbceb-191">规划展台应用</span><span class="sxs-lookup"><span data-stu-id="bbceb-191">Plan kiosk apps</span></span>

<span data-ttu-id="bbceb-192">有关如何选择展台应用的一般信息，请参阅 [ (展台模式下为分配的 access 选择应用指南) ](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-192">For general information about how to choose kiosk apps, see [Guidelines for choosing an app for assigned access (kiosk mode)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).</span></span>

<span data-ttu-id="bbceb-193">如果你使用 Windows Device Portal 配置单应用展台，请在安装过程中选择该应用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-193">If you use the Windows Device Portal to configure a single-app kiosk, you select the app during the setup process.</span></span>  

<span data-ttu-id="bbceb-194">如果你使用 (MDM) 系统或预配包来配置展台模式的移动设备管理，请使用 [AssignedAccess 配置服务提供程序 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 来指定应用程序。</span><span class="sxs-lookup"><span data-stu-id="bbceb-194">If you use a Mobile Device Management (MDM) system or a provisioning package to configure kiosk mode, you use the [AssignedAccess Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) to specify applications.</span></span> <span data-ttu-id="bbceb-195">CSP 使用 [应用程序用户模型 id (aumid) ](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 来标识应用程序。</span><span class="sxs-lookup"><span data-stu-id="bbceb-195">The CSP uses [Application User Model IDs (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) to identify applications.</span></span> <span data-ttu-id="bbceb-196">下表列出了可在多应用展台中使用的一些内置应用程序的 Aumid。</span><span class="sxs-lookup"><span data-stu-id="bbceb-196">The following table lists the AUMIDs of some in-box applications that you can use in a multi-app kiosk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbceb-197">展台模式确定当用户登录到设备时，哪些应用可用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-197">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="bbceb-198">但是，展台模式不是一种安全方法。</span><span class="sxs-lookup"><span data-stu-id="bbceb-198">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="bbceb-199">它不会阻止 "允许" 应用打开不允许的另一个应用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-199">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="bbceb-200">由于我们不限制此行为，因此仍可从 Edge、文件资源管理器和 Microsoft Store 应用启动应用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-200">Because we do not restrict this behavior, apps can still be launched from Edge, File explorer, and the Microsoft Store apps.</span></span> <span data-ttu-id="bbceb-201">如果你不想从展台启动特定应用，请使用 [Windows Defender 应用程序控件 (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 来创建相应的策略。</span><span class="sxs-lookup"><span data-stu-id="bbceb-201">If there are specific apps you don't want launched from a Kiosk, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span> 
> 
> <span data-ttu-id="bbceb-202">此外，混合现实主页无法设置为展台应用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-202">In addition, the Mixed Reality Home is not able to be set as a kiosk app.</span></span>

<a id="aumids"></a>

|<span data-ttu-id="bbceb-203">应用名称</span><span class="sxs-lookup"><span data-stu-id="bbceb-203">App Name</span></span> |<span data-ttu-id="bbceb-204">AUMID</span><span class="sxs-lookup"><span data-stu-id="bbceb-204">AUMID</span></span> |
| --- | --- |
|<span data-ttu-id="bbceb-205">3D 查看器</span><span class="sxs-lookup"><span data-stu-id="bbceb-205">3D Viewer</span></span> |<span data-ttu-id="bbceb-206">Microsoft3DViewer \ _8wekyb3d8bbwe \！Microsoft3DViewer</span><span class="sxs-lookup"><span data-stu-id="bbceb-206">Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\!Microsoft.Microsoft3DViewer</span></span> |
|<span data-ttu-id="bbceb-207">日历</span><span class="sxs-lookup"><span data-stu-id="bbceb-207">Calendar</span></span> |<span data-ttu-id="bbceb-208">windowscommunicationsapps \ _8wekyb3d8bbwe \！ windowslive。</span><span class="sxs-lookup"><span data-stu-id="bbceb-208">microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar</span></span> |
|<span data-ttu-id="bbceb-209">相机 <sup> 1、2</span><span class="sxs-lookup"><span data-stu-id="bbceb-209">Camera<sup>1, 2</span></span></sup> |<span data-ttu-id="bbceb-210">HoloCamera \ _cw5n1h2txyewy \！HoloCamera</span><span class="sxs-lookup"><span data-stu-id="bbceb-210">HoloCamera\_cw5n1h2txyewy\!HoloCamera</span></span> |
|<span data-ttu-id="bbceb-211">Cortana <sup> 3</span><span class="sxs-lookup"><span data-stu-id="bbceb-211">Cortana<sup>3</span></span></sup> |<span data-ttu-id="bbceb-212">549981C3F5F10 \ _8wekyb3d8bbwe \！应用</span><span class="sxs-lookup"><span data-stu-id="bbceb-212">Microsoft.549981C3F5F10\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="bbceb-213">HoloLens 上的设备选取器 (第一代) </span><span class="sxs-lookup"><span data-stu-id="bbceb-213">Device Picker on HoloLens (1st gen)</span></span> |<span data-ttu-id="bbceb-214">HoloDevicesFlow \ _cw5n1h2txyewy \！HoloDevicesFlow</span><span class="sxs-lookup"><span data-stu-id="bbceb-214">HoloDevicesFlow\_cw5n1h2txyewy\!HoloDevicesFlow</span></span> |
|<span data-ttu-id="bbceb-215">HoloLens 2 上的设备选取器</span><span class="sxs-lookup"><span data-stu-id="bbceb-215">Device Picker on HoloLens 2</span></span> |<span data-ttu-id="bbceb-216">DevicesFlowHost \ _cw5n1h2txyewy \！DevicesFlowHost</span><span class="sxs-lookup"><span data-stu-id="bbceb-216">Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\!Microsoft.Windows.DevicesFlowHost</span></span> |
|<span data-ttu-id="bbceb-217">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="bbceb-217">Dynamics 365 Guides</span></span> |<span data-ttu-id="bbceb-218">Dynamics365 _8wekyb3d8bbwe \！MicrosoftGuides</span><span class="sxs-lookup"><span data-stu-id="bbceb-218">Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\!MicrosoftGuides</span></span> |
|<span data-ttu-id="bbceb-219">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="bbceb-219">Dynamics 365 Remote Assist</span></span> |<span data-ttu-id="bbceb-220">MicrosoftRemoteAssist \ _8wekyb3d8bbwe \！RemoteAssist</span><span class="sxs-lookup"><span data-stu-id="bbceb-220">Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\!Microsoft.RemoteAssist</span></span> |
|<span data-ttu-id="bbceb-221">反馈 &nbsp; 中心</span><span class="sxs-lookup"><span data-stu-id="bbceb-221">Feedback&nbsp;Hub</span></span> |<span data-ttu-id="bbceb-222">WindowsFeedbackHub \ _8wekyb3d8bbwe \！应用</span><span class="sxs-lookup"><span data-stu-id="bbceb-222">Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="bbceb-223">文件资源管理器</span><span class="sxs-lookup"><span data-stu-id="bbceb-223">File Explorer</span></span> |<span data-ttu-id="bbceb-224">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span><span class="sxs-lookup"><span data-stu-id="bbceb-224">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span></span> |
|<span data-ttu-id="bbceb-225">Mail</span><span class="sxs-lookup"><span data-stu-id="bbceb-225">Mail</span></span> |<span data-ttu-id="bbceb-226">microsoft.windowscommunicationsapps_8wekyb3d8bbwe！ windowslive</span><span class="sxs-lookup"><span data-stu-id="bbceb-226">microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail</span></span> |
|<span data-ttu-id="bbceb-227">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="bbceb-227">Microsoft Store</span></span> |<span data-ttu-id="bbceb-228">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span><span class="sxs-lookup"><span data-stu-id="bbceb-228">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span></span> |
|<span data-ttu-id="bbceb-229">Miracast <sup> 4</span><span class="sxs-lookup"><span data-stu-id="bbceb-229">Miracast<sup>4</span></span></sup> |&nbsp; |
|<span data-ttu-id="bbceb-230">电影和电视</span><span class="sxs-lookup"><span data-stu-id="bbceb-230">Movies & TV</span></span> |<span data-ttu-id="bbceb-231">ZuneVideo \ _8wekyb3d8bbwe \！ZuneVideo</span><span class="sxs-lookup"><span data-stu-id="bbceb-231">Microsoft.ZuneVideo\_8wekyb3d8bbwe\!Microsoft.ZuneVideo</span></span> |
|<span data-ttu-id="bbceb-232">OneDrive</span><span class="sxs-lookup"><span data-stu-id="bbceb-232">OneDrive</span></span> |<span data-ttu-id="bbceb-233">microsoftskydrive \ _8wekyb3d8bbwe \！应用</span><span class="sxs-lookup"><span data-stu-id="bbceb-233">microsoft.microsoftskydrive\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="bbceb-234">照片</span><span class="sxs-lookup"><span data-stu-id="bbceb-234">Photos</span></span> |<span data-ttu-id="bbceb-235">_8wekyb3d8bbwe \ 照片。应用</span><span class="sxs-lookup"><span data-stu-id="bbceb-235">Microsoft.Windows.Photos\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="bbceb-236">“设置”</span><span class="sxs-lookup"><span data-stu-id="bbceb-236">Settings</span></span> |<span data-ttu-id="bbceb-237">HolographicSystemSettings \ _cw5n1h2txyewy \！应用</span><span class="sxs-lookup"><span data-stu-id="bbceb-237">HolographicSystemSettings\_cw5n1h2txyewy\!App</span></span> |
|<span data-ttu-id="bbceb-238">提示</span><span class="sxs-lookup"><span data-stu-id="bbceb-238">Tips</span></span> |<span data-ttu-id="bbceb-239">HoloLensTips \ _8wekyb3d8bbwe \！HoloLensTips</span><span class="sxs-lookup"><span data-stu-id="bbceb-239">Microsoft.HoloLensTips\_8wekyb3d8bbwe\!HoloLensTips</span></span> |

> <sup><span data-ttu-id="bbceb-240">1 </sup> 要启用照片或视频捕获，您必须将相机应用启用为展台应用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-240">1</sup> To enable photo or video capture, you have to enable the Camera app as a kiosk app.</span></span>  
> <sup><span data-ttu-id="bbceb-241">2 </sup> 启用摄像头应用时，请注意以下条件：</span><span class="sxs-lookup"><span data-stu-id="bbceb-241">2</sup> When you enable the Camera app, be aware of the following conditions:</span></span>
> - <span data-ttu-id="bbceb-242">"快速操作" 菜单包含 "照片" 和 "视频" 按钮。</span><span class="sxs-lookup"><span data-stu-id="bbceb-242">The Quick Actions menu includes the Photo and Video buttons.</span></span>  
> - <span data-ttu-id="bbceb-243">你还应启用可与图片交互或检索图片的应用 (例如照片、邮件或 OneDrive) 。</span><span class="sxs-lookup"><span data-stu-id="bbceb-243">You should also enable an app (such as Photos, Mail, or OneDrive) that can interact with or retrieve pictures.</span></span>  
>  
> <sup><span data-ttu-id="bbceb-244">3 </sup> 即使不将 Cortana 启用为展台应用，也会启用内置语音命令。</span><span class="sxs-lookup"><span data-stu-id="bbceb-244">3</sup> Even if you do not enable Cortana as a kiosk app, built-in voice commands are enabled.</span></span> <span data-ttu-id="bbceb-245">但是，与禁用的功能相关的命令不起作用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-245">However, commands that are related to disabled features have no effect.</span></span>  
> <sup><span data-ttu-id="bbceb-246">4 </sup> 不能直接启用 Miracast。</span><span class="sxs-lookup"><span data-stu-id="bbceb-246">4</sup> You cannot enable Miracast directly.</span></span> <span data-ttu-id="bbceb-247">若要将 Miracast 启用为展台应用，请启用相机应用和设备选取器应用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-247">To enable Miracast as a kiosk app enable the Camera app and the Device Picker app.</span></span>

### <span data-ttu-id="bbceb-248">为用户或组规划展台配置文件</span><span class="sxs-lookup"><span data-stu-id="bbceb-248">Plan kiosk profiles for users or groups</span></span>

<span data-ttu-id="bbceb-249">当创建 xml 文件或使用 Intune 的 UI 设置展台时，你需要考虑谁将是用户的展台。</span><span class="sxs-lookup"><span data-stu-id="bbceb-249">When either creating the xml file or using Intune’s UI to set up a Kiosk you’ll need to consider who will be user the Kiosk.</span></span> <span data-ttu-id="bbceb-250">展台配置可以限制为单个帐户或 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="bbceb-250">A Kiosk configuration can be limited to either an individual account or Azure AD groups.</span></span> 

<span data-ttu-id="bbceb-251">通常为用户或用户组启用展台。</span><span class="sxs-lookup"><span data-stu-id="bbceb-251">Typically Kiosks are enabled for either a user, or user group.</span></span> <span data-ttu-id="bbceb-252">但是，如果你计划编写自己的 XML 展台，你可能需要考虑全局分配的访问权限，在该访问中，将在设备级别应用展台（不考虑身份）。</span><span class="sxs-lookup"><span data-stu-id="bbceb-252">However if you plan on writing your own XML Kiosk, then you may want to consider Global Assigned Access, in which the Kiosk is applied at the device level regardless of Identity.</span></span> <span data-ttu-id="bbceb-253">如果你了解 [有关全局分配的 Access 网亭的详细信息，请参阅。](hololens-global-assigned-access-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="bbceb-253">If this appeals to you [read more about Global Assigned Access Kiosks.](hololens-global-assigned-access-kiosk.md)</span></span>

#### <span data-ttu-id="bbceb-254">如果要创建 XML 文件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bbceb-254">If you are creating an XML file:</span></span>
-   <span data-ttu-id="bbceb-255">你可以创建多个展台配置文件，并将每个配置文件分配给不同的用户/组。</span><span class="sxs-lookup"><span data-stu-id="bbceb-255">You many create multiple Kiosk profiles, and assign each to different users/groups.</span></span> <span data-ttu-id="bbceb-256">例如，具有许多应用的 AAD 组的展台，以及具有多个应用展台且具有单一应用的访问者。</span><span class="sxs-lookup"><span data-stu-id="bbceb-256">Such as a Kiosk for your AAD Group that has many apps, and a Visitor that has a multiple app kiosk with a singular app.</span></span>
-   <span data-ttu-id="bbceb-257">您的展台配置将被称为 **配置文件 Id** ，并且具有 GUID。</span><span class="sxs-lookup"><span data-stu-id="bbceb-257">Your kiosk configuration will be called a **Profile Id** and have a GUID.</span></span>
-   <span data-ttu-id="bbceb-258">你将通过指定用户类型并对 **DefaultProfile Id**使用相同的 GUID，将该配置文件分配到 "配置" 部分。</span><span class="sxs-lookup"><span data-stu-id="bbceb-258">You will assign that Profile in the configs section by specifying the user type and using the same GUID for the **DefaultProfile Id**.</span></span>
- <span data-ttu-id="bbceb-259">通过创建自定义 OMA URI 设备配置文件并将其应用到 HoloLens 设备组（使用 URI 值），可以创建 XML 文件，但仍通过 MDM 将其应用于设备。/Device/Vendor/MSFT/AssignedAccess/Configuration</span><span class="sxs-lookup"><span data-stu-id="bbceb-259">A XML file can be created but still applied to a device via MDM by creating a custom OMA URI device configuration profile and applying it to HoloLens device group using the URI value: ./Device/Vendor/MSFT/AssignedAccess/Configuration</span></span>

#### <span data-ttu-id="bbceb-260">如果你在 Intune 中创建展台。</span><span class="sxs-lookup"><span data-stu-id="bbceb-260">If you are creating a Kiosk in Intune.</span></span>
-   <span data-ttu-id="bbceb-261">每个设备可能只会接收到一个展台配置文件，否则它将产生冲突并根本不接收任何展台配置。</span><span class="sxs-lookup"><span data-stu-id="bbceb-261">Each device may only receive a single Kiosk profile, otherwise it will create a conflict and receive no Kiosk configurations at all.</span></span> 
    -   <span data-ttu-id="bbceb-262">其他类型的配置文件和策略（如与展台配置文件无关的设备限制）不会与展台配置文件冲突。</span><span class="sxs-lookup"><span data-stu-id="bbceb-262">Other kinds of profiles and policies, such as device restrictions that are not related to the kiosk configuration profile, do not conflict with the kiosk configuration profile.</span></span>
-   <span data-ttu-id="bbceb-263">将为所有属于用户登录类型的用户启用展台，此操作将使用用户或 AAD 组进行设置。</span><span class="sxs-lookup"><span data-stu-id="bbceb-263">The Kiosk will be enabled for all users who are a part of the User logon type, this will be set with a user or AAD group.</span></span> 
-   <span data-ttu-id="bbceb-264">设置展台配置后， **用户登录类型** (可以登录展台的用户) 并且选择了应用，则设备配置仍然必须分配到组。</span><span class="sxs-lookup"><span data-stu-id="bbceb-264">After the Kiosk configuration is set and the **User logon type** (users who can log into the Kiosk) and the Apps are selected, the Device Configuration must still be assigned to a group.</span></span> <span data-ttu-id="bbceb-265">分配的组 (s) 确定哪些设备将接收展台设备配置，但如果启用了展台，则不会与之交互。</span><span class="sxs-lookup"><span data-stu-id="bbceb-265">The Assigned group(s) determines which devices receive the Kiosk device configuration, however does not interact with if the Kiosk is enabled or not.</span></span> 
    - <span data-ttu-id="bbceb-266">有关在 Intune 中分配配置文件的效果的完整讨论，请参阅 [在 Microsoft Intune 中分配用户和设备配置文件](https://docs.microsoft.com/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-266">For a full discussion of the effects of assigning configuration profiles in Intune, see [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).</span></span>

### <span data-ttu-id="bbceb-267">选择部署方法</span><span class="sxs-lookup"><span data-stu-id="bbceb-267">Select a deployment method</span></span>

<span data-ttu-id="bbceb-268">你可以选择以下方法之一来部署展台配置：</span><span class="sxs-lookup"><span data-stu-id="bbceb-268">You can select one of the following methods to deploy kiosk configurations:</span></span>

- [<span data-ttu-id="bbceb-269"> (MDM) 服务的 Microsoft Intune 或其他移动设备管理</span><span class="sxs-lookup"><span data-stu-id="bbceb-269">Microsoft Intune or other mobile device management (MDM) service</span></span>](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="bbceb-270">设置包</span><span class="sxs-lookup"><span data-stu-id="bbceb-270">Provisioning package</span></span>](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="bbceb-271">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="bbceb-271">Windows Device Portal</span></span>](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > <span data-ttu-id="bbceb-272">由于此方法需要在设备上启用开发人员模式，因此我们建议仅将其用于演示。</span><span class="sxs-lookup"><span data-stu-id="bbceb-272">Because this method requires that Developer Mode be enabled on the device, we recommend that you use it only for demonstrations.</span></span>

<span data-ttu-id="bbceb-273">下表列出了每个部署方法的功能和优点。</span><span class="sxs-lookup"><span data-stu-id="bbceb-273">The following table lists the capabilities and benefits of each of the deployment methods.</span></span>

| &nbsp; |<span data-ttu-id="bbceb-274">使用 Windows Device Portal 进行部署</span><span class="sxs-lookup"><span data-stu-id="bbceb-274">Deploy by using Windows Device Portal</span></span> |<span data-ttu-id="bbceb-275">使用预配包进行部署</span><span class="sxs-lookup"><span data-stu-id="bbceb-275">Deploy by using a provisioning package</span></span> |<span data-ttu-id="bbceb-276">使用 MDM 进行部署</span><span class="sxs-lookup"><span data-stu-id="bbceb-276">Deploy by using MDM</span></span> |
| --------------------------- | ------------- | -------------------- | ---- |
|<span data-ttu-id="bbceb-277">部署单应用网亭</span><span class="sxs-lookup"><span data-stu-id="bbceb-277">Deploy single-app kiosks</span></span>   | <span data-ttu-id="bbceb-278">是</span><span class="sxs-lookup"><span data-stu-id="bbceb-278">Yes</span></span>           | <span data-ttu-id="bbceb-279">是</span><span class="sxs-lookup"><span data-stu-id="bbceb-279">Yes</span></span>                  | <span data-ttu-id="bbceb-280">是</span><span class="sxs-lookup"><span data-stu-id="bbceb-280">Yes</span></span>  |
|<span data-ttu-id="bbceb-281">部署多路应用网亭</span><span class="sxs-lookup"><span data-stu-id="bbceb-281">Deploy multi-app kiosks</span></span>    | <span data-ttu-id="bbceb-282">否</span><span class="sxs-lookup"><span data-stu-id="bbceb-282">No</span></span>            | <span data-ttu-id="bbceb-283">是</span><span class="sxs-lookup"><span data-stu-id="bbceb-283">Yes</span></span>                  | <span data-ttu-id="bbceb-284">是</span><span class="sxs-lookup"><span data-stu-id="bbceb-284">Yes</span></span>  |
|<span data-ttu-id="bbceb-285">仅部署到本地设备</span><span class="sxs-lookup"><span data-stu-id="bbceb-285">Deploy to local devices only</span></span> | <span data-ttu-id="bbceb-286">是</span><span class="sxs-lookup"><span data-stu-id="bbceb-286">Yes</span></span>           | <span data-ttu-id="bbceb-287">是</span><span class="sxs-lookup"><span data-stu-id="bbceb-287">Yes</span></span>                  | <span data-ttu-id="bbceb-288">否</span><span class="sxs-lookup"><span data-stu-id="bbceb-288">No</span></span>   |
|<span data-ttu-id="bbceb-289">使用开发人员模式进行部署</span><span class="sxs-lookup"><span data-stu-id="bbceb-289">Deploy by using Developer Mode</span></span> |<span data-ttu-id="bbceb-290">必需</span><span class="sxs-lookup"><span data-stu-id="bbceb-290">Required</span></span>       | <span data-ttu-id="bbceb-291">不需要</span><span class="sxs-lookup"><span data-stu-id="bbceb-291">Not required</span></span>            | <span data-ttu-id="bbceb-292">不需要</span><span class="sxs-lookup"><span data-stu-id="bbceb-292">Not required</span></span>   |
|<span data-ttu-id="bbceb-293">使用 Azure Active Directory (AAD) 进行部署</span><span class="sxs-lookup"><span data-stu-id="bbceb-293">Deploy by using Azure Active Directory (AAD)</span></span>  | <span data-ttu-id="bbceb-294">不需要</span><span class="sxs-lookup"><span data-stu-id="bbceb-294">Not required</span></span>            | <span data-ttu-id="bbceb-295">不需要</span><span class="sxs-lookup"><span data-stu-id="bbceb-295">Not required</span></span>                   | <span data-ttu-id="bbceb-296">必需</span><span class="sxs-lookup"><span data-stu-id="bbceb-296">Required</span></span>  |
|<span data-ttu-id="bbceb-297">自动部署</span><span class="sxs-lookup"><span data-stu-id="bbceb-297">Deploy automatically</span></span>      | <span data-ttu-id="bbceb-298">否</span><span class="sxs-lookup"><span data-stu-id="bbceb-298">No</span></span>            | <span data-ttu-id="bbceb-299">否</span><span class="sxs-lookup"><span data-stu-id="bbceb-299">No</span></span>                   | <span data-ttu-id="bbceb-300">是</span><span class="sxs-lookup"><span data-stu-id="bbceb-300">Yes</span></span>  |
|<span data-ttu-id="bbceb-301">部署速度</span><span class="sxs-lookup"><span data-stu-id="bbceb-301">Deployment speed</span></span>            | <span data-ttu-id="bbceb-302">迅速</span><span class="sxs-lookup"><span data-stu-id="bbceb-302">Fast</span></span>       | <span data-ttu-id="bbceb-303">迅速</span><span class="sxs-lookup"><span data-stu-id="bbceb-303">Fast</span></span>                 | <span data-ttu-id="bbceb-304">慢速</span><span class="sxs-lookup"><span data-stu-id="bbceb-304">Slow</span></span> |
|<span data-ttu-id="bbceb-305">按比例部署</span><span class="sxs-lookup"><span data-stu-id="bbceb-305">Deploy at scale</span></span> | <span data-ttu-id="bbceb-306">不建议</span><span class="sxs-lookup"><span data-stu-id="bbceb-306">Not recommended</span></span>    | <span data-ttu-id="bbceb-307">推荐</span><span class="sxs-lookup"><span data-stu-id="bbceb-307">Recommended</span></span>        | <span data-ttu-id="bbceb-308">推荐</span><span class="sxs-lookup"><span data-stu-id="bbceb-308">Recommended</span></span> |

## <span data-ttu-id="bbceb-309">使用 Microsoft Intune 或其他 MDM 设置单应用或多应用展台</span><span class="sxs-lookup"><span data-stu-id="bbceb-309">Use Microsoft Intune or other MDM to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="bbceb-310">若要使用 Microsoft Intune 或其他 MDM 系统设置展台模式，请按照下列步骤操作。</span><span class="sxs-lookup"><span data-stu-id="bbceb-310">To set up kiosk mode by using Microsoft Intune or another MDM system, follow these steps.</span></span>

1. <span data-ttu-id="bbceb-311">[准备注册设备](#mdmenroll)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-311">[Prepare to enroll the devices](#mdmenroll).</span></span>
1. <span data-ttu-id="bbceb-312">[创建展台配置文件](#mdmprofile)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-312">[Create a kiosk configuration profile](#mdmprofile).</span></span>
1. <span data-ttu-id="bbceb-313">配置展台。</span><span class="sxs-lookup"><span data-stu-id="bbceb-313">Configure the kiosk.</span></span>
   - <span data-ttu-id="bbceb-314">[配置单应用展台的设置](#mdmconfigsingle)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-314">[Configure the settings for a single-app kiosk](#mdmconfigsingle).</span></span>
   - <span data-ttu-id="bbceb-315">[配置多应用展台的设置](#mdmconfigmulti)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-315">[Configure the settings for a multi-app kiosk](#mdmconfigmulti).</span></span>
1. <span data-ttu-id="bbceb-316">[将展台配置文件分配到组](#mdmassign)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-316">[Assign the kiosk configuration profile to a group](#mdmassign).</span></span>
1. <span data-ttu-id="bbceb-317">部署设备。</span><span class="sxs-lookup"><span data-stu-id="bbceb-317">Deploy the devices.</span></span>
   - <span data-ttu-id="bbceb-318">[部署单应用展台](#mdmsingledeploy)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-318">[Deploy a single-app kiosk](#mdmsingledeploy).</span></span>
   - <span data-ttu-id="bbceb-319">[部署多应用展台](#mdmmultideploy)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-319">[Deploy a multi-app kiosk](#mdmmultideploy).</span></span>

### <a id="mdmenroll"></a><span data-ttu-id="bbceb-320">MDM，步骤 1 &ndash; 准备注册设备</span><span class="sxs-lookup"><span data-stu-id="bbceb-320">MDM, step 1 &ndash; Prepare to enroll the devices</span></span>

<span data-ttu-id="bbceb-321">你可以将 MDM 系统配置为在用户首次登录时自动注册 HoloLens 设备，或者让用户手动注册设备。</span><span class="sxs-lookup"><span data-stu-id="bbceb-321">You can configure your MDM system to enroll HoloLens devices automatically when the user first signs in, or have users enroll devices manually.</span></span> <span data-ttu-id="bbceb-322">设备还必须加入到 Azure AD 域，并分配给相应的组。</span><span class="sxs-lookup"><span data-stu-id="bbceb-322">The devices also have to be joined to your Azure AD domain, and assigned to the appropriate groups.</span></span>

<span data-ttu-id="bbceb-323">有关如何注册设备的详细信息，请参阅 [在 MDM 中注册 HoloLens](hololens-enroll-mdm.md) 和 [Windows 设备的 Intune 注册方法](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-323">For more information about how to enroll the devices, see [Enroll HoloLens in MDM](hololens-enroll-mdm.md) and [Intune enrollment methods for Windows devices](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).</span></span>

### <a id="mdmprofile"></a><span data-ttu-id="bbceb-324">MDM、步骤 2 &ndash; 创建展台配置文件</span><span class="sxs-lookup"><span data-stu-id="bbceb-324">MDM, step 2 &ndash; Create a kiosk configuration profile</span></span>

1. <span data-ttu-id="bbceb-325">打开 [Azure](https://portal.azure.com/) 门户并登录到你的 Intune 管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="bbceb-325">Open the [Azure](https://portal.azure.com/) portal and sign in to your Intune administrator account.</span></span>
1. <span data-ttu-id="bbceb-326">选择 " **Microsoft Intune**  >  **设备配置"-配置文件**  >  **创建配置文件**。</span><span class="sxs-lookup"><span data-stu-id="bbceb-326">Select **Microsoft Intune** > **Device configuration - Profiles** > **Create profile**.</span></span>
1. <span data-ttu-id="bbceb-327">输入配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="bbceb-327">Enter a profile name.</span></span>
1. <span data-ttu-id="bbceb-328">选择 "**平台**  >  **Windows 10 及更高版本**"，然后选择 "**配置文件类型**  > **设备限制**"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-328">Select **Platform** > **Windows 10 and later**, and then select **Profile type** >**Device restrictions**.</span></span>
1. <span data-ttu-id="bbceb-329">选择 "**配置**  >  **展台**"，然后选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="bbceb-329">Select **Configure** > **Kiosk**, and then select one of the following:</span></span>
   - <span data-ttu-id="bbceb-330">若要创建单应用展台，请选择 "**展台模式**  >  **单应用展台**"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-330">To create a single-app kiosk, select **Kiosk Mode** > **Single-app kiosk**.</span></span>
   - <span data-ttu-id="bbceb-331">若要创建多应用程序亭，请选择 "**展台模式**  >  **多应用展台**"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-331">To create a multi-app kiosk, select **Kiosk Mode** > **Multi-app kiosk**.</span></span>
1. <span data-ttu-id="bbceb-332">要开始配置展台，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-332">To start configuring the kiosk, select **Add**.</span></span>

<span data-ttu-id="bbceb-333">根据所需的展台类型，后续步骤会有所不同。</span><span class="sxs-lookup"><span data-stu-id="bbceb-333">Your next steps differ depending on the type of kiosk that you want.</span></span> <span data-ttu-id="bbceb-334">有关详细信息，请选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="bbceb-334">For more information, select one of the following options:</span></span>  

- [<span data-ttu-id="bbceb-335">单应用展台</span><span class="sxs-lookup"><span data-stu-id="bbceb-335">Single-app kiosk</span></span>](#mdmconfigsingle)
- [<span data-ttu-id="bbceb-336">多应用展台。</span><span class="sxs-lookup"><span data-stu-id="bbceb-336">Multi-app kiosk</span></span>](#mdmconfigmulti)

<span data-ttu-id="bbceb-337">有关如何创建展台配置文件的详细信息，请参阅 [windows 10 和 Windows 全息版 For Business 设备设置，以使用 Intune 作为专用展台运行](https://docs.microsoft.com/intune/configuration/kiosk-settings)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-337">For more information about how to create a kiosk configuration profile, see [Windows 10 and Windows Holographic for Business device settings to run as a dedicated kiosk using Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).</span></span>

### <a id="mdmconfigsingle"></a><span data-ttu-id="bbceb-338">MDM、步骤 3 (单应用) &ndash;  配置单应用展台的设置</span><span class="sxs-lookup"><span data-stu-id="bbceb-338">MDM, step 3 (single-app) &ndash;  Configure the settings for a single-app kiosk</span></span>

<span data-ttu-id="bbceb-339">本部分概述了单应用展台所需的设置。</span><span class="sxs-lookup"><span data-stu-id="bbceb-339">This section summarizes the settings that a single-app kiosk requires.</span></span> <span data-ttu-id="bbceb-340">有关更多详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="bbceb-340">For more details, see the following articles:</span></span>

- <span data-ttu-id="bbceb-341">有关如何在 Intune 中配置展台配置文件的信息，请参阅 [如何使用 Microsoft Intune 配置展台模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-341">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="bbceb-342">有关 Intune 中的单应用网亭可用设置的详细信息，请参阅 [单个全屏应用网亭](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="bbceb-342">For more information about the available settings for single-app kiosks in Intune, see [Single full-screen app kiosks](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span></span>
- <span data-ttu-id="bbceb-343">对于其他 MDM 服务，请参阅提供商文档中的说明。</span><span class="sxs-lookup"><span data-stu-id="bbceb-343">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="bbceb-344">如果必须使用自定义 XML 配置在 MDM 服务中设置展台，请 [创建一个定义 kiosk 配置的 XML 文件](#ppkioskconfig)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-344">If you have to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span>

1. <span data-ttu-id="bbceb-345">选择 "**用户登录类型**  >  **本地用户帐户**"，然后输入可登录到展台的本地 (设备) 帐户或 Microsoft 帐户 (MSA) 的用户名。</span><span class="sxs-lookup"><span data-stu-id="bbceb-345">Select **User logon type** > **Local user account**, and then enter the user name of the local (device) account or Microsoft Account (MSA) that can sign in to the kiosk.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="bbceb-346">Windows 全息版商业版不支持**自动登录**用户帐户类型。</span><span class="sxs-lookup"><span data-stu-id="bbceb-346">**Autologon** user account types aren't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="bbceb-347">选择 "**应用程序类型**  >  **存储应用**"，然后从列表中选择一个应用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-347">Select **Application type** > **Store app**, and then select an app from the list.</span></span>

<span data-ttu-id="bbceb-348">下一步是将配置文件 [分配](#mdmassign) 给组。</span><span class="sxs-lookup"><span data-stu-id="bbceb-348">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmconfigmulti"></a><span data-ttu-id="bbceb-349">MDM、步骤 3 (多应用) &ndash; 配置多应用展台的设置</span><span class="sxs-lookup"><span data-stu-id="bbceb-349">MDM, step 3 (multi-app) &ndash; Configure the settings for a multi-app kiosk</span></span>

<span data-ttu-id="bbceb-350">本部分概述了多应用展台所需的设置。</span><span class="sxs-lookup"><span data-stu-id="bbceb-350">This section summarizes the settings that a multi-app kiosk requires.</span></span> <span data-ttu-id="bbceb-351">有关更多详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="bbceb-351">For more detailed information, see the following articles:</span></span>

- <span data-ttu-id="bbceb-352">有关如何在 Intune 中配置展台配置文件的信息，请参阅 [如何使用 Microsoft Intune 配置展台模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-352">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="bbceb-353">有关 Intune 中的多应用网亭可用设置的详细信息，请参阅 [多路应用网亭](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="bbceb-353">For more information about the available settings for multi-app kiosks in Intune, see [Multi-app kiosks](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span></span>
- <span data-ttu-id="bbceb-354">对于其他 MDM 服务，请参阅提供商文档中的说明。</span><span class="sxs-lookup"><span data-stu-id="bbceb-354">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="bbceb-355">如果需要使用自定义 XML 配置在 MDM 服务中设置展台，请 [创建一个定义 kiosk 配置的 XML 文件](#ppkioskconfig)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-355">If you need to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span> <span data-ttu-id="bbceb-356">如果使用 XML 文件，请确保包含 " [开始" 布局](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-356">If you use an XML file, make sure to include the [Start layout](#start-layout-for-hololens).</span></span>  
- <span data-ttu-id="bbceb-357">你可以选择将自定义开始布局与 Intune 或其他 MDM 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-357">You can optionally use a custom Start layout with Intune or other MDM services.</span></span> <span data-ttu-id="bbceb-358">有关详细信息，请参阅 [为 MDM (启动布局文件 Intune 和其他) ](#start-layout-file-for-mdm-intune-and-others)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-358">For more information, see [Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

1. <span data-ttu-id="bbceb-359">选择 **"在 S 模式设备中确定目标 Windows 10 设备"**  >  **No**</span><span class="sxs-lookup"><span data-stu-id="bbceb-359">Select **Target Windows 10 in S mode devices** > **No**.</span></span>  
   >[!NOTE]  
   > <span data-ttu-id="bbceb-360">S 模式在 Windows 全息版商业版上不受支持。</span><span class="sxs-lookup"><span data-stu-id="bbceb-360">S mode isn't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="bbceb-361">选择 "**用户登录类型**"  >  **Azure AD 用户或组**或**用户登录类型**  >  **HoloLens 访问者**，然后添加一个或多个用户组或帐户。</span><span class="sxs-lookup"><span data-stu-id="bbceb-361">Select **User logon type** > **Azure AD user or group** or **User logon type** > **HoloLens visitor**, and then add one or more user groups or accounts.</span></span>  

   <span data-ttu-id="bbceb-362">只有属于你在 " **用户登录类型** " 中指定的组或帐户的用户才能使用展台体验。</span><span class="sxs-lookup"><span data-stu-id="bbceb-362">Only users who belong to the groups or accounts that you specify in **User logon type** can use the kiosk experience.</span></span>

1. <span data-ttu-id="bbceb-363">使用以下选项选择一个或多个应用：</span><span class="sxs-lookup"><span data-stu-id="bbceb-363">Select one or more apps by using the following options:</span></span>
   - <span data-ttu-id="bbceb-364">若要添加已上载的业务线应用程序，请选择 " **添加应用商店应用** "，然后选择所需的应用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-364">To add an uploaded line-of-business app, select **Add store app** and then select the app that you want.</span></span>
   - <span data-ttu-id="bbceb-365">若要通过指定其 AUMID 添加应用，请选择 " **由 AUMID 添加** "，然后输入应用的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="bbceb-365">To add an app by specifying its AUMID, select **Add by AUMID** and then enter the AUMID of the app.</span></span> [<span data-ttu-id="bbceb-366">查看可用的 Aumid 列表</span><span class="sxs-lookup"><span data-stu-id="bbceb-366">See the list of available AUMIDs</span></span>](#aumids)

<span data-ttu-id="bbceb-367">下一步是将配置文件 [分配](#mdmassign) 给组。</span><span class="sxs-lookup"><span data-stu-id="bbceb-367">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmassign"></a><span data-ttu-id="bbceb-368">MDM，步骤 4 &ndash; 将展台配置文件分配到组</span><span class="sxs-lookup"><span data-stu-id="bbceb-368">MDM, step 4 &ndash; Assign the kiosk configuration profile to a group</span></span>

<span data-ttu-id="bbceb-369">使用展台配置文件的 " **分配** " 页面设置要在其中部署 kiosk 配置的位置。</span><span class="sxs-lookup"><span data-stu-id="bbceb-369">Use the **Assignments** page of the kiosk configuration profile to set where you want the kiosk configuration to deploy.</span></span> <span data-ttu-id="bbceb-370">在最简单的情况下，你将展台配置配置文件分配给将在使用 MDM 注册设备时包含 HoloLens 设备的组。</span><span class="sxs-lookup"><span data-stu-id="bbceb-370">In the simplest case, you assign the kiosk configuration profile to a group that will contain the HoloLens device when the device enrolls in MDM.</span></span>

### <a id="mdmsingledeploy"></a><span data-ttu-id="bbceb-371">MDM、步骤 5 (单应用) &ndash; 部署单应用展台</span><span class="sxs-lookup"><span data-stu-id="bbceb-371">MDM, step 5 (single-app) &ndash; Deploy a single-app kiosk</span></span>

<span data-ttu-id="bbceb-372">使用 MDM 系统时，可以在 OOBE 期间在 MDM 中注册设备。</span><span class="sxs-lookup"><span data-stu-id="bbceb-372">When you use an MDM system, you can enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="bbceb-373">在 OOBE 完成后，登录到设备非常简单。</span><span class="sxs-lookup"><span data-stu-id="bbceb-373">After OOBE finishes, signing in to the device is easy.</span></span>

<span data-ttu-id="bbceb-374">在 OOBE 期间，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="bbceb-374">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="bbceb-375">使用在展台配置文件中指定的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="bbceb-375">Sign in by using the account that you specified in the kiosk configuration profile.</span></span>
1. <span data-ttu-id="bbceb-376">注册设备。</span><span class="sxs-lookup"><span data-stu-id="bbceb-376">Enroll the device.</span></span> <span data-ttu-id="bbceb-377">请确保将设备添加到将设备配置文件分配到的组。</span><span class="sxs-lookup"><span data-stu-id="bbceb-377">Make sure that the device is added to the group that the kiosk configuration profile is assigned to.</span></span>
1. <span data-ttu-id="bbceb-378">等待 OOBE 完成，针对要下载和安装的应用商店应用以及要应用的策略。</span><span class="sxs-lookup"><span data-stu-id="bbceb-378">Wait for OOBE to finish, for the store app to download and install, and for policies to be applied.</span></span> <span data-ttu-id="bbceb-379">然后重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="bbceb-379">Then restart the device.</span></span>

<span data-ttu-id="bbceb-380">下次登录设备时，展台应用应自动启动。</span><span class="sxs-lookup"><span data-stu-id="bbceb-380">The next time you sign in to the device, the kiosk app should automatically start.</span></span>

<span data-ttu-id="bbceb-381">如果此时看不到展台配置，请 [检查作业状态](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-381">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

### <a id="mdmmultideploy"></a><span data-ttu-id="bbceb-382">MDM、步骤 5 (多应用) &ndash; 部署多应用展台</span><span class="sxs-lookup"><span data-stu-id="bbceb-382">MDM, step 5 (multi-app) &ndash; Deploy a multi-app kiosk</span></span>

<span data-ttu-id="bbceb-383">使用 MDM 系统时，你可以将设备加入 Azure AD 租户，并在 OOBE 期间在 MDM 中注册设备。</span><span class="sxs-lookup"><span data-stu-id="bbceb-383">When you use an MDM system, you can join the device to your Azure AD tenant and enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="bbceb-384">如果适用，请向用户提供注册信息，以便用户可以在 OOBE 过程中使用它。</span><span class="sxs-lookup"><span data-stu-id="bbceb-384">If appropriate, provide the enrollment information to the users so that they have it available during the OOBE process.</span></span>

> [!NOTE]  
> <span data-ttu-id="bbceb-385">如果您已将展台配置文件分配给包含用户的组，请确保其中一个用户帐户是登录到该设备的第一个帐户。</span><span class="sxs-lookup"><span data-stu-id="bbceb-385">If you have assigned the kiosk configuration profile to a group that contains users, make sure that one of those user accounts is the first account to sign in to the device.</span></span>

<span data-ttu-id="bbceb-386">在 OOBE 期间，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="bbceb-386">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="bbceb-387">使用属于 " **用户登录类型** " 组的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="bbceb-387">Sign in by using the account that belongs to the **User logon type** group.</span></span>
1. <span data-ttu-id="bbceb-388">注册设备。</span><span class="sxs-lookup"><span data-stu-id="bbceb-388">Enroll the device.</span></span>
1. <span data-ttu-id="bbceb-389">等待所有属于展台配置文件的应用下载并安装。</span><span class="sxs-lookup"><span data-stu-id="bbceb-389">Wait for any apps that are part of the kiosk configuration profile to download and install.</span></span> <span data-ttu-id="bbceb-390">此外，请等待应用策略。</span><span class="sxs-lookup"><span data-stu-id="bbceb-390">Also, wait for policies to be applied.</span></span>  
1. <span data-ttu-id="bbceb-391">在 OOBE 完成后，你可以通过 Microsoft store 或通过旁加载来安装其他应用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-391">After OOBE finishes, you can install additional apps from the Microsoft store or by sideloading.</span></span> <span data-ttu-id="bbceb-392">设备所属的组自动安装[所需的应用](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-392">[Required apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) for the group that the device belongs to install automatically.</span></span>
1. <span data-ttu-id="bbceb-393">安装完成后，重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="bbceb-393">After the installation finishes, restart the device.</span></span>

<span data-ttu-id="bbceb-394">下次使用属于 **用户登录类型**的帐户登录设备时，展台应用应自动启动。</span><span class="sxs-lookup"><span data-stu-id="bbceb-394">The next time you sign in to the device by using an account that belongs to the **User logon type**, the kiosk app should automatically launch.</span></span>

<span data-ttu-id="bbceb-395">如果此时看不到展台配置，请 [检查作业状态](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-395">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

## <span data-ttu-id="bbceb-396">使用预配包设置单应用或多应用展台</span><span class="sxs-lookup"><span data-stu-id="bbceb-396">Use a provisioning package to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="bbceb-397">若要使用预配包设置展台模式，请按照下列步骤操作。</span><span class="sxs-lookup"><span data-stu-id="bbceb-397">To set up kiosk mode by using a provisioning package, follow these steps.</span></span>

1. <span data-ttu-id="bbceb-398">[创建一个定义展台配置的 XML 文件](#ppkioskconfig)，包括 "开始" [布局](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-398">[Create an XML file that defines the kiosk configuration.](#ppkioskconfig), including a [Start layout](#start-layout-for-hololens).</span></span>
2. [<span data-ttu-id="bbceb-399">将 XML 文件添加到预配包。</span><span class="sxs-lookup"><span data-stu-id="bbceb-399">Add the XML file to a provisioning package.</span></span>](#ppconfigadd)
3. [<span data-ttu-id="bbceb-400">将预配包应用于 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="bbceb-400">Apply the provisioning package to HoloLens.</span></span>](#ppapply)

### <a id="ppkioskconfig"></a><span data-ttu-id="bbceb-401">预配程序包，步骤 1 &ndash; 创建展台配置 XML 文件</span><span class="sxs-lookup"><span data-stu-id="bbceb-401">Provisioning package, step 1 &ndash; Create a kiosk configuration XML file</span></span>

<span data-ttu-id="bbceb-402">按照 [常规说明为 Windows 桌面版创建展台配置 XML 文件](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)，但以下内容除外：</span><span class="sxs-lookup"><span data-stu-id="bbceb-402">Follow [the general instructions to create a kiosk configuration XML file for Windows desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), except for the following:</span></span>

- <span data-ttu-id="bbceb-403">不要在 Win32) 中包括经典 Windows 应用程序 (。</span><span class="sxs-lookup"><span data-stu-id="bbceb-403">Do not include Classic Windows applications (Win32).</span></span> <span data-ttu-id="bbceb-404">HoloLens 不支持这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="bbceb-404">HoloLens does not support these applications.</span></span>
- <span data-ttu-id="bbceb-405">使用适用于 HoloLens 的 [占位符开始布局 XML](#start-layout-for-hololens) 。</span><span class="sxs-lookup"><span data-stu-id="bbceb-405">Use the [placeholder Start layout XML](#start-layout-for-hololens) for HoloLens.</span></span>
- <span data-ttu-id="bbceb-406">可选：将来宾访问添加到展台配置</span><span class="sxs-lookup"><span data-stu-id="bbceb-406">Optional: Add guest access to the kiosk configuration</span></span>

#### <a id="ppkioskguest"></a><span data-ttu-id="bbceb-407">可选：将来宾访问添加到展台配置</span><span class="sxs-lookup"><span data-stu-id="bbceb-407">Optional: Add guest access to the kiosk configuration</span></span>

<span data-ttu-id="bbceb-408">在 XML 文件的 "配置" 部分中，可以将名为 "**访问者**" 的特殊组配置为允许来宾使用展台。 [ **Configs** ](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)</span><span class="sxs-lookup"><span data-stu-id="bbceb-408">In the [**Configs** section of the XML file](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), you can configure a special group named **Visitor** to allow guests to use the kiosk.</span></span> <span data-ttu-id="bbceb-409">当展台配置为支持 **访问者** 特殊组时，登录页面中将添加一个 "**来宾**" 选项。</span><span class="sxs-lookup"><span data-stu-id="bbceb-409">When the kiosk is configured to support the **Visitor** special group, a "**Guest**" option is added to the sign-in page.</span></span> <span data-ttu-id="bbceb-410">**来宾**帐户不需要密码，并且与帐户关联的任何数据在帐户注销时都将被删除。</span><span class="sxs-lookup"><span data-stu-id="bbceb-410">The **Guest** account does not require a password, and any data that is associated with the account is deleted when the account signs out.</span></span>

<span data-ttu-id="bbceb-411">若要启用 **来宾** 帐户，请将以下代码片段添加到展台配置 XML：</span><span class="sxs-lookup"><span data-stu-id="bbceb-411">To enable the **Guest** account, add the following snippet to your kiosk configuration XML:</span></span>

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a><span data-ttu-id="bbceb-412">HoloLens 的占位符开始布局</span><span class="sxs-lookup"><span data-stu-id="bbceb-412">Placeholder Start layout for HoloLens</span></span>

<span data-ttu-id="bbceb-413">如果使用 [预配包](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 配置多应用展台，则该过程需要 "开始" 布局。</span><span class="sxs-lookup"><span data-stu-id="bbceb-413">If you use a [provisioning package](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) to configure a multi-app kiosk, the procedure requires a Start layout.</span></span> <span data-ttu-id="bbceb-414">Windows 全息版中不支持 "开始布局自定义"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-414">Start layout customization isn't supported in Windows Holographic for Business.</span></span> <span data-ttu-id="bbceb-415">因此，你必须使用占位符开始布局。</span><span class="sxs-lookup"><span data-stu-id="bbceb-415">Therefore, you'll have to use a placeholder Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="bbceb-416">由于单应用展台在用户登录时启动展台应用，因此它不使用 "开始" 菜单，也不需要具有 "开始" 布局。</span><span class="sxs-lookup"><span data-stu-id="bbceb-416">Because a single-app kiosk starts the kiosk app when a user signs in, it does not use a Start menu and does not have to have a Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="bbceb-417">如果使用 [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 设置多应用展台，则可以选择使用 "开始" 布局。</span><span class="sxs-lookup"><span data-stu-id="bbceb-417">If you use [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) to set up a multi-app kiosk, you can optionally use a Start layout.</span></span> <span data-ttu-id="bbceb-418">有关详细信息，请参阅 [MDM (Intune 和其他) 的占位符启动布局文件 ](#start-layout-file-for-mdm-intune-and-others)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-418">For more information, see [Placeholder Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

<span data-ttu-id="bbceb-419">对于 "开始" 布局，将以下 **StartLayout** 部分添加到展台预配 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="bbceb-419">For the Start layout, add the following **StartLayout** section to the kiosk provisioning XML file:</span></span>

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

#### <a id="start-layout-file-for-mdm-intune-and-others"></a><span data-ttu-id="bbceb-420">适用于 MDM (Intune 和其他人的占位符开始布局文件) </span><span class="sxs-lookup"><span data-stu-id="bbceb-420">Placeholder Start layout file for MDM (Intune and others)</span></span>

<span data-ttu-id="bbceb-421">将以下示例另存为 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="bbceb-421">Save the following sample as an XML file.</span></span> <span data-ttu-id="bbceb-422">在 Microsoft Intune 中配置多应用展台时，你可以使用此文件 (或在提供展台配置文件的其他 MDM 服务中使用此文件) 。</span><span class="sxs-lookup"><span data-stu-id="bbceb-422">You can use this file when you configure the multi-app kiosk in Microsoft Intune (or in another MDM service that provides a kiosk profile).</span></span>

> [!NOTE]
> <span data-ttu-id="bbceb-423">如果必须使用自定义设置和完整的 XML 配置来设置 MDM 服务中的展台，请使用 [预配包的启动布局说明](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-423">If you have to use a custom setting and full XML configuration to set up a kiosk in your MDM service, use the [Start layout instructions for a provisioning package](#start-layout-for-hololens).</span></span>

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

### <a id="ppconfigadd"></a><span data-ttu-id="bbceb-424">Prov.</span><span class="sxs-lookup"><span data-stu-id="bbceb-424">Prov.</span></span> <span data-ttu-id="bbceb-425">程序包，步骤 2 &ndash; 将 kiosk 配置 XML 文件添加到预配包</span><span class="sxs-lookup"><span data-stu-id="bbceb-425">package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package</span></span>

1. <span data-ttu-id="bbceb-426">打开 [Windows 配置设计器](https://www.microsoft.com/store/apps/9nblggh4tx22)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-426">Open [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span>
1. <span data-ttu-id="bbceb-427">选择 " **高级设置**"，输入项目的名称，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-427">Select **Advanced provisioning**, enter a name for your project, and then select **Next**.</span></span>
1. <span data-ttu-id="bbceb-428">选择 " **Windows 10 全息**版"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-428">Select **Windows 10 Holographic**, and then select **Next**.</span></span>
1. <span data-ttu-id="bbceb-429">选择 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-429">Select **Finish**.</span></span> <span data-ttu-id="bbceb-430">此时将打开你的程序包的工作区。</span><span class="sxs-lookup"><span data-stu-id="bbceb-430">The workspace for your package opens.</span></span>
1. <span data-ttu-id="bbceb-431">选择 "**运行时设置**"  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**。</span><span class="sxs-lookup"><span data-stu-id="bbceb-431">Select **Runtime settings** > **AssignedAccess** > **MultiAppAssignedAccessSettings**.</span></span>
1. <span data-ttu-id="bbceb-432">在中心窗格中，选择 " **浏览** "，找到并选择您创建的展台配置 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="bbceb-432">In the center pane, select **Browse** to locate and select the kiosk configuration XML file that you created.</span></span>

   ![Windows 配置设计器中的 MultiAppAssignedAccessSettings 字段的屏幕截图](./images/multiappassignedaccesssettings.png)

1. <span data-ttu-id="bbceb-434">**可选**。</span><span class="sxs-lookup"><span data-stu-id="bbceb-434">**Optional**.</span></span> <span data-ttu-id="bbceb-435"> (如果你希望在设备的初始设置之后应用预配程序包，并且在展台设备上已有管理员用户，请跳过此步骤。 ) 选择 " **运行时设置** &gt; **帐户** &gt; **用户**"，然后创建用户帐户。</span><span class="sxs-lookup"><span data-stu-id="bbceb-435">(If you want to apply the provisioning package after the initial setup of the device, and there is an admin user already available on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a user account.</span></span> <span data-ttu-id="bbceb-436">提供用户名和密码，然后选择 " **UserGroup**  >  **管理员**"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-436">Provide a user name and password, and then select **UserGroup** > **Administrators**.</span></span>  
  
     <span data-ttu-id="bbceb-437">通过使用此帐户，你可以查看预配状态和日志。</span><span class="sxs-lookup"><span data-stu-id="bbceb-437">By using this account, you can view the provisioning status and logs.</span></span>  
1. <span data-ttu-id="bbceb-438">**可选**。</span><span class="sxs-lookup"><span data-stu-id="bbceb-438">**Optional**.</span></span> <span data-ttu-id="bbceb-439"> (如果在展台设备上已有非管理员帐户，请跳过此步骤。 ) 选择 " **运行时设置** &gt; **帐户** &gt; **用户**"，然后创建一个本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="bbceb-439">(If you already have a non-admin account on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a local user account.</span></span> <span data-ttu-id="bbceb-440">请确保用户名与你在配置 XML 中指定的帐户相同。</span><span class="sxs-lookup"><span data-stu-id="bbceb-440">Make sure that the user name is the same as for the account that you specify in the configuration XML.</span></span> <span data-ttu-id="bbceb-441">选择 " **UserGroup**  >  **标准用户**"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-441">Select **UserGroup** > **Standard Users**.</span></span>
1. <span data-ttu-id="bbceb-442">选择**File**"  >  **保存**文件"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-442">Select **File** > **Save**.</span></span>
1. <span data-ttu-id="bbceb-443">选择 "**导出**  >  **预配包**"，然后选择 "**所有者**  >  **IT 管理员**"。这会将此预配包的优先级设置为高于从其他源应用到此设备的预配包。</span><span class="sxs-lookup"><span data-stu-id="bbceb-443">Select **Export** > **Provisioning package**, and then select **Owner** > **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages that are applied to this device from other sources.</span></span>
1. <span data-ttu-id="bbceb-444">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="bbceb-444">Select **Next**.</span></span>
1. <span data-ttu-id="bbceb-445">在 " **预配程序包安全** " 页面上，选择一个安全选项。</span><span class="sxs-lookup"><span data-stu-id="bbceb-445">On the **Provisioning package security** page, select a security option.</span></span>
   > [!IMPORTANT]  
   > <span data-ttu-id="bbceb-446">如果选择 " **启用包签名**"，还必须选择用于对程序包进行签名的有效证书。</span><span class="sxs-lookup"><span data-stu-id="bbceb-446">If you select **Enable package signing**, you also have to select a valid certificate to use for signing the package.</span></span> <span data-ttu-id="bbceb-447">若要执行此操作，请选择 " **浏览** "，然后选择要用于对程序包进行签名的证书。</span><span class="sxs-lookup"><span data-stu-id="bbceb-447">To do this, select **Browse** and select the certificate that you want to use to sign the package.</span></span>
   
   > [!CAUTION]  
   > <span data-ttu-id="bbceb-448">不要选择 " **启用包加密**"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-448">Do not select **Enable package encryption**.</span></span> <span data-ttu-id="bbceb-449">在 HoloLens 设备上，此设置会导致预配失败。</span><span class="sxs-lookup"><span data-stu-id="bbceb-449">On HoloLens devices, this setting causes provisioning to fail.</span></span>
1. <span data-ttu-id="bbceb-450">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="bbceb-450">Select **Next**.</span></span>
1. <span data-ttu-id="bbceb-451">指定在构建预配包时希望该预配包转到的输出位置。</span><span class="sxs-lookup"><span data-stu-id="bbceb-451">Specify the output location where you want the provisioning package to go when it's built.</span></span> <span data-ttu-id="bbceb-452">默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。</span><span class="sxs-lookup"><span data-stu-id="bbceb-452">By default, Windows Configuration Designer uses the project folder as the output location.</span></span> <span data-ttu-id="bbceb-453">如果要更改输出位置，请选择 " **浏览**"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-453">If you want to change the output location, select **Browse**.</span></span> <span data-ttu-id="bbceb-454">完成后，选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-454">When you are finished, select **Next**.</span></span>
1. <span data-ttu-id="bbceb-455">选择 " **生成** " 开始构建程序包。</span><span class="sxs-lookup"><span data-stu-id="bbceb-455">Select **Build** to start building the package.</span></span> <span data-ttu-id="bbceb-456">无需花费太长时间即可生成预配包。</span><span class="sxs-lookup"><span data-stu-id="bbceb-456">The provisioning package doesn't take long to build.</span></span> <span data-ttu-id="bbceb-457">"生成" 页面显示项目信息，进度栏指示生成状态。</span><span class="sxs-lookup"><span data-stu-id="bbceb-457">The build page displays the project information, and the progress bar indicates the build status.</span></span>

### <a id="ppapply"></a><span data-ttu-id="bbceb-458">预配程序包，步骤 3 &ndash; 将预配包应用于 HoloLens</span><span class="sxs-lookup"><span data-stu-id="bbceb-458">Provisioning package, step 3 &ndash; Apply the provisioning package to HoloLens</span></span>

<span data-ttu-id="bbceb-459">"使用预配包配置 HoloLens" 一文提供了在以下情况下应用预配包的详细说明：</span><span class="sxs-lookup"><span data-stu-id="bbceb-459">The "Configure HoloLens by using a provisioning package" article provides detailed instructions to apply the provisioning package under the following circumstances:</span></span>

- <span data-ttu-id="bbceb-460">在安装期间，您最初可以 [将预配包应用于 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-460">You can initially [apply a provisioning package to HoloLens during setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).</span></span>

- <span data-ttu-id="bbceb-461">您还可以 [在安装完成后将预配包应用于 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-461">You can also [apply a provisioning package to HoloLens after setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).</span></span>

## <span data-ttu-id="bbceb-462">使用 Windows Device Portal 设置单应用展台</span><span class="sxs-lookup"><span data-stu-id="bbceb-462">Use the Windows Device Portal to set up a single-app kiosk</span></span>

<span data-ttu-id="bbceb-463">若要使用 Windows Device Portal 设置展台模式，请按照下列步骤操作。</span><span class="sxs-lookup"><span data-stu-id="bbceb-463">To set up kiosk mode by using the Windows Device Portal, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bbceb-464">展台模式仅在设备安装了 [Windows 全息版企业](hololens1-upgrade-enterprise.md) 版时可用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-464">Kiosk mode is available only if the device has [Windows Holographic for Business](hololens1-upgrade-enterprise.md) installed.</span></span>

1. <span data-ttu-id="bbceb-465">[将 HoloLens 设备设置为使用 Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-465">[Set up the HoloLens device to use the Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal).</span></span> <span data-ttu-id="bbceb-466">Device Portal 是 HoloLens 上的 Web 服务器，你可以从电脑上的 Web 浏览器连接到它。</span><span class="sxs-lookup"><span data-stu-id="bbceb-466">The Device Portal is a web server on your HoloLens that you can connect to from a web browser on your PC.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="bbceb-467">将 HoloLens 设置为使用 Device Portal 时，必须在设备上启用开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="bbceb-467">When you set up HoloLens to use the Device Portal, you have to enable Developer Mode on the device.</span></span> <span data-ttu-id="bbceb-468">具有 Windows 全息版企业版的设备上的开发人员模式使你能够使用面加载应用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-468">Developer Mode on a device that has Windows Holographic for Business enables you to side-load apps.</span></span> <span data-ttu-id="bbceb-469">但是，此设置会创建一个风险，用户可以安装 Microsoft Store 尚未认证的应用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-469">However, this setting creates a risk that a user can install apps that have not been certified by the Microsoft Store.</span></span> <span data-ttu-id="bbceb-470">管理员可以通过使用[策略 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)中的**ApplicationManagement/AllowDeveloper 解锁**设置阻止启用开发人员模式的功能。</span><span class="sxs-lookup"><span data-stu-id="bbceb-470">Administrators can block the ability to enable Developer Mode by using the **ApplicationManagement/AllowDeveloper Unlock** setting in the [Policy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider).</span></span> [<span data-ttu-id="bbceb-471">了解有关开发人员模式的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bbceb-471">Learn more about Developer Mode.</span></span>](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. <span data-ttu-id="bbceb-472">在计算机上，使用 [wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 或 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="bbceb-472">On a computer, connect to the HoloLens by using [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) or [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).</span></span>

1. <span data-ttu-id="bbceb-473">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="bbceb-473">Do one of the following:</span></span>
   - <span data-ttu-id="bbceb-474">如果您是首次连接到 Windows Device Portal，请 [创建用户名和密码](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span><span class="sxs-lookup"><span data-stu-id="bbceb-474">If you are connecting to the Windows Device Portal for the first time, [create a user name and password](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span></span>
   - <span data-ttu-id="bbceb-475">输入您以前设置的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="bbceb-475">Enter the user name and password that you previously set up.</span></span>

    > [!TIP]
    > <span data-ttu-id="bbceb-476">如果发现浏览器中的证书错误，请遵循[以下疑难解答步骤](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)。</span><span class="sxs-lookup"><span data-stu-id="bbceb-476">If you see a certificate error in the browser, follow [these troubleshooting steps](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).</span></span>

1. <span data-ttu-id="bbceb-477">在 Windows Device Portal 中，选择 " **展台模式**"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-477">In the Windows Device Portal, select **Kiosk Mode**.</span></span>

1. <span data-ttu-id="bbceb-478">选择 " **启用展台模式**"，选择要在设备启动时运行的应用，然后选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-478">Select **Enable Kiosk Mode**, select an app to run when the device starts, and then select **Save**.</span></span>

    ![展台模式](images/kiosk.png)
1. <span data-ttu-id="bbceb-480">重新启动 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="bbceb-480">Restart HoloLens.</span></span> <span data-ttu-id="bbceb-481">如果您的设备门户页面仍处于打开状态，则可以在页面顶部选择 " **重新启动** "。</span><span class="sxs-lookup"><span data-stu-id="bbceb-481">If you still have your Device Portal page open, you can select **Restart** at the top of the page.</span></span>

> [!NOTE]
> <span data-ttu-id="bbceb-482">可以通过设备门户的 REST API 设置展台模式，方法是使用一个必需的查询字符串参数 ( "kioskModeEnabled"，使用值为 "true" 或 "false" ) ，使用一个可选参数 ( "startupApp"，并使用包名称) 的值来设置/api/holographic/kioskmode/settings。</span><span class="sxs-lookup"><span data-stu-id="bbceb-482">Kiosk Mode can be set via Device Portal’s REST API by doing a POST to /api/holographic/kioskmode/settings with one required query string parameter (“kioskModeEnabled” with a value of “true” or “false”) and one optional parameter (“startupApp” with a value of a package name).</span></span> <span data-ttu-id="bbceb-483">请记住，Device Portal 仅面向开发人员，不应在非开发人员设备上启用。</span><span class="sxs-lookup"><span data-stu-id="bbceb-483">Please keep in mind that Device Portal is intended for developers only and should not be enabled on non-developer devices.</span></span> <span data-ttu-id="bbceb-484">REST API 可能会在将来的更新/发布中更改。</span><span class="sxs-lookup"><span data-stu-id="bbceb-484">The REST API is subject to change in future updates/releases.</span></span>

## <span data-ttu-id="bbceb-485">详细信息</span><span class="sxs-lookup"><span data-stu-id="bbceb-485">More information</span></span>

<span data-ttu-id="bbceb-486">观看如何使用预配包配置展台。</span><span class="sxs-lookup"><span data-stu-id="bbceb-486">Watch how to configure a kiosk by using a provisioning package.</span></span>  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

## <span data-ttu-id="bbceb-487">适用于 HoloLens 的 XML 展台代码示例</span><span class="sxs-lookup"><span data-stu-id="bbceb-487">XML Kiosk Code Samples for HoloLens</span></span>

### <span data-ttu-id="bbceb-488">面向 AAD 组的多个应用展台模式。</span><span class="sxs-lookup"><span data-stu-id="bbceb-488">Multiple app kiosk mode targeting an AAD group.</span></span> 
<span data-ttu-id="bbceb-489">此展台为 AAD 组中的用户部署了一个展台，他们将启用一个展台，其中包含3个应用：设置、远程协助和反馈中心。</span><span class="sxs-lookup"><span data-stu-id="bbceb-489">This kiosk deploys a Kiosk that for users in the AAD group, they will have a Kiosk enabled that includes the 3 apps: Settings, Remote Assist, and Feedback Hub.</span></span> <span data-ttu-id="bbceb-490">若要将此示例修改为立即使用，请确保更改下面突出显示的 GUID，以匹配您自己的 AAD 组。</span><span class="sxs-lookup"><span data-stu-id="bbceb-490">To modify this sample to be used immediately, make sure to change the GUID highlighted below to match an AAD Group of your own.</span></span> 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <span data-ttu-id="bbceb-491">针对 AAD 帐户的多个应用展台模式。</span><span class="sxs-lookup"><span data-stu-id="bbceb-491">Multiple app kiosk mode targeting AAD account.</span></span>
<span data-ttu-id="bbceb-492">此展台为单个用户部署展台，他们将启用一个展台，其中包含3个应用： "设置"、"远程协助" 和 "反馈中心"。</span><span class="sxs-lookup"><span data-stu-id="bbceb-492">This kiosk deploys a Kiosk for a single user, they will have a Kiosk enabled that includes the 3 apps: Settings, Remote Assist, and Feedback Hub.</span></span> <span data-ttu-id="bbceb-493">若要将此示例修改为立即使用，请确保将下面突出显示的帐户更改为与您自己的 AAD 帐户相匹配。</span><span class="sxs-lookup"><span data-stu-id="bbceb-493">To modify this sample to be used immediately, make sure to change the account highlighted below to match an AAD Account of your own.</span></span> 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

