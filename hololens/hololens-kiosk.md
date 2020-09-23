---
title: 将 HoloLens 设置为 Kiosk
description: 使用展台配置锁定 HoloLens 上的应用。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 8844f691ec5395f9c69bce7df44125da9c838f14
ms.sourcegitcommit: 7bf0f92aaf1683c7c39ed6b17ac47231c5088365
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "11072789"
---
# <span data-ttu-id="84c2e-103">将 HoloLens 设置为 Kiosk</span><span class="sxs-lookup"><span data-stu-id="84c2e-103">Set up HoloLens as a kiosk</span></span>

<span data-ttu-id="84c2e-104">你可以将 HoloLens 设备配置为固定用途的设备（也称为 *展台*），方法是将设备配置为在展台模式下运行。</span><span class="sxs-lookup"><span data-stu-id="84c2e-104">You can configure a HoloLens device to function as a fixed-purpose device, also called a *kiosk*, by configuring the device to run in kiosk mode.</span></span> <span data-ttu-id="84c2e-105">展台模式限制设备上可用 (或用户) 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="84c2e-105">Kiosk mode limits the applications (or users) that are available on the device.</span></span> <span data-ttu-id="84c2e-106">展台模式是一种方便的功能，可用于将 HoloLens 设备专用于商业应用，或在应用演示中使用 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-106">Kiosk mode is a convenient feature that you can use to dedicate a HoloLens device to business apps, or to use the HoloLens device in an app demo.</span></span>

<span data-ttu-id="84c2e-107">本文提供有关特定于 HoloLens 设备的展台配置方面的信息。</span><span class="sxs-lookup"><span data-stu-id="84c2e-107">This article provides information about aspects of kiosk configuration that are specific to HoloLens devices.</span></span> <span data-ttu-id="84c2e-108">有关不同类型的基于 Windows 的网亭以及如何配置它们的常规信息，请参阅 [在 Windows 桌面版上配置网亭和数字签名](https://docs.microsoft.com/windows/configuration/kiosk-methods)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-108">For general information about the different types of Windows-based kiosks and how to configure them, see [Configure kiosks and digital signs on Windows desktop editions](https://docs.microsoft.com/windows/configuration/kiosk-methods).</span></span>  

> [!IMPORTANT]  
> <span data-ttu-id="84c2e-109">展台模式确定当用户登录到设备时，哪些应用可用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-109">Kiosk mode determines which apps are available when a user signs in to the device.</span></span> <span data-ttu-id="84c2e-110">但是，展台模式不是一种安全方法。</span><span class="sxs-lookup"><span data-stu-id="84c2e-110">However, kiosk mode is not a security method.</span></span> <span data-ttu-id="84c2e-111">它不会阻止 "允许" 应用打开不允许的另一个应用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-111">It does not stop an "allowed" app from opening another app that is not allowed.</span></span> <span data-ttu-id="84c2e-112">为了阻止应用或进程打开，请使用 [Windows Defender 应用程序控件 (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 来创建相应的策略。</span><span class="sxs-lookup"><span data-stu-id="84c2e-112">In order to block apps or processes from opening, use [Windows Defender Application Control (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) to create appropriate policies.</span></span>
>
> <span data-ttu-id="84c2e-113">了解有关 Microsoft 服务的详细信息，以便为用户提供 HoloLens 2 使用的高级安全级别，请阅读有关 [状态分隔和隔离 Defender 保护](security-state-separation-isolation.md#defender-protections)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="84c2e-113">Learn more about the Microsoft services to give users an advanced level of security that HoloLens 2 uses, read more about [State separation and isolation - Defender protections](security-state-separation-isolation.md#defender-protections).</span></span> <span data-ttu-id="84c2e-114">或了解如何 [使用 WDAC 和 Windows PowerShell 在 HoloLens 2 设备上使用 Microsoft Intune 允许或阻止应用](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-114">Or learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="84c2e-115">你可以在单个应用或多个应用配置中使用展台模式，并且可以使用三个进程之一来设置和部署展台配置。</span><span class="sxs-lookup"><span data-stu-id="84c2e-115">You can use kiosk mode in either a single-app or a multi-app configuration, and you can use one of three processes to set up and deploy the kiosk configuration.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="84c2e-116">删除多应用配置将删除分配的访问功能所创建的用户锁定配置文件。</span><span class="sxs-lookup"><span data-stu-id="84c2e-116">Deleting the multi-app configuration removes the user lockdown profiles that the assigned access feature created.</span></span> <span data-ttu-id="84c2e-117">但是，它不会还原所有策略更改。</span><span class="sxs-lookup"><span data-stu-id="84c2e-117">However, it does not revert all the policy changes.</span></span> <span data-ttu-id="84c2e-118">若要还原这些策略，必须将设备重置为出厂设置。</span><span class="sxs-lookup"><span data-stu-id="84c2e-118">To revert these policies, you have to reset the device to the factory settings.</span></span>

## <span data-ttu-id="84c2e-119">规划展台部署</span><span class="sxs-lookup"><span data-stu-id="84c2e-119">Plan the kiosk deployment</span></span>

### <span data-ttu-id="84c2e-120">展台模式要求</span><span class="sxs-lookup"><span data-stu-id="84c2e-120">Kiosk mode requirements</span></span>

<span data-ttu-id="84c2e-121">您可以将任何 HoloLens 2 设备配置为使用展台模式。</span><span class="sxs-lookup"><span data-stu-id="84c2e-121">You can configure any HoloLens 2 device to use kiosk mode.</span></span>

<span data-ttu-id="84c2e-122">若要将 HoloLens (第一代) 设备配置为使用展台模式，必须首先确保该设备运行的是 Windows 10 版本1803或更高版本。</span><span class="sxs-lookup"><span data-stu-id="84c2e-122">To configure a HoloLens (1st gen) device to use kiosk mode, you must first make sure that the device runs Windows 10, version 1803, or a later version.</span></span> <span data-ttu-id="84c2e-123">如果你已使用 Windows 设备恢复工具将 HoloLens (第一代) 设备恢复为默认版本，或者如果已安装了最新的更新，则设备已准备好进行配置。</span><span class="sxs-lookup"><span data-stu-id="84c2e-123">If you have used the Windows Device Recovery Tool to recover your HoloLens (1st gen) device to its default build, or if you have installed the most recent updates, your device is ready to configure.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="84c2e-124">若要帮助保护在展台模式下运行的设备，请考虑添加关闭诸如 USB 连接等功能的设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="84c2e-124">To help protect devices that run in kiosk mode, consider adding device management policies that turn off features such as USB connectivity.</span></span> <span data-ttu-id="84c2e-125">此外，检查更新铃声设置以确保在工作时间内不会自动更新。</span><span class="sxs-lookup"><span data-stu-id="84c2e-125">Additionally, check your update ring settings to make sure that automatic updates do not occur during business hours.</span></span>

### <span data-ttu-id="84c2e-126">在单应用展台或多应用展台之间做出选择</span><span class="sxs-lookup"><span data-stu-id="84c2e-126">Decide between a single-app kiosk or a multi-app kiosk</span></span>

<span data-ttu-id="84c2e-127">当用户登录到设备时，单应用展台会启动指定的应用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-127">A single-app kiosk starts the specified app when the user signs in to the device.</span></span> <span data-ttu-id="84c2e-128">"开始" 菜单已禁用，与 Cortana 一样。</span><span class="sxs-lookup"><span data-stu-id="84c2e-128">The Start menu is disabled, as is Cortana.</span></span> <span data-ttu-id="84c2e-129">HoloLens 2 设备不响应 [开始](hololens2-basic-usage.md#start-gesture) 手势。</span><span class="sxs-lookup"><span data-stu-id="84c2e-129">A HoloLens 2 device does not respond to the [Start](hololens2-basic-usage.md#start-gesture) gesture.</span></span> <span data-ttu-id="84c2e-130">HoloLens (第一代) 设备不会响应 [绽放](hololens1-basic-usage.md) 手势。</span><span class="sxs-lookup"><span data-stu-id="84c2e-130">A HoloLens (1st gen) device does not respond to the [bloom](hololens1-basic-usage.md) gesture.</span></span> <span data-ttu-id="84c2e-131">由于只有一个应用可以运行，因此用户无法放置其他应用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-131">Because only one app can run, the user cannot place other apps.</span></span>

<span data-ttu-id="84c2e-132">当用户登录到设备时，多应用展台显示 "开始" 菜单。</span><span class="sxs-lookup"><span data-stu-id="84c2e-132">A multi-app kiosk displays the Start menu when the user signs in to the device.</span></span> <span data-ttu-id="84c2e-133">展台配置确定哪些应用在 "开始" 菜单上可用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-133">The kiosk configuration determines which apps are available on the Start menu.</span></span> <span data-ttu-id="84c2e-134">你可以使用多应用展台为用户提供简单易懂的体验，只需向他们展示他们必须使用的功能，并删除不需要使用的功能。</span><span class="sxs-lookup"><span data-stu-id="84c2e-134">You can use a multi-app kiosk to provide an easy-to-understand experience for users by presenting to them only the things that they have to use, and removing the things they don't need to use.</span></span>

<span data-ttu-id="84c2e-135">下表列出了不同展台模式下的功能功能。</span><span class="sxs-lookup"><span data-stu-id="84c2e-135">The following table lists the feature capabilities in the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="84c2e-136">“开始”菜单</span><span class="sxs-lookup"><span data-stu-id="84c2e-136">Start menu</span></span> |<span data-ttu-id="84c2e-137">"快速操作" 菜单</span><span class="sxs-lookup"><span data-stu-id="84c2e-137">Quick Actions menu</span></span> |<span data-ttu-id="84c2e-138">摄像头和视频</span><span class="sxs-lookup"><span data-stu-id="84c2e-138">Camera and video</span></span> |<span data-ttu-id="84c2e-139">Miracast</span><span class="sxs-lookup"><span data-stu-id="84c2e-139">Miracast</span></span> |<span data-ttu-id="84c2e-140">Cortana</span><span class="sxs-lookup"><span data-stu-id="84c2e-140">Cortana</span></span> |<span data-ttu-id="84c2e-141">内置语音命令</span><span class="sxs-lookup"><span data-stu-id="84c2e-141">Built-in voice commands</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|<span data-ttu-id="84c2e-142">单应用展台</span><span class="sxs-lookup"><span data-stu-id="84c2e-142">Single-app kiosk</span></span> |<span data-ttu-id="84c2e-143">已禁用</span><span class="sxs-lookup"><span data-stu-id="84c2e-143">Disabled</span></span> |<span data-ttu-id="84c2e-144">已禁用</span><span class="sxs-lookup"><span data-stu-id="84c2e-144">Disabled</span></span>   |<span data-ttu-id="84c2e-145">已禁用</span><span class="sxs-lookup"><span data-stu-id="84c2e-145">Disabled</span></span> |<span data-ttu-id="84c2e-146">已禁用</span><span class="sxs-lookup"><span data-stu-id="84c2e-146">Disabled</span></span>   |<span data-ttu-id="84c2e-147">已禁用</span><span class="sxs-lookup"><span data-stu-id="84c2e-147">Disabled</span></span> |<span data-ttu-id="84c2e-148">已启用 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="84c2e-148">Enabled<sup>1</span></span></sup> |
|<span data-ttu-id="84c2e-149">多应用展台</span><span class="sxs-lookup"><span data-stu-id="84c2e-149">Multi-app kiosk</span></span> |<span data-ttu-id="84c2e-150">启用</span><span class="sxs-lookup"><span data-stu-id="84c2e-150">Enabled</span></span> |<span data-ttu-id="84c2e-151">已启用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="84c2e-151">Enabled<sup>2</span></span></sup> |<span data-ttu-id="84c2e-152">可用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="84c2e-152">Available<sup>2</span></span></sup> |<span data-ttu-id="84c2e-153">可用 <sup> 2</span><span class="sxs-lookup"><span data-stu-id="84c2e-153">Available<sup>2</span></span></sup> |<span data-ttu-id="84c2e-154">可用 <sup> 2，3</span><span class="sxs-lookup"><span data-stu-id="84c2e-154">Available<sup>2, 3</span></span></sup>  |<span data-ttu-id="84c2e-155">已启用 <sup> 1</span><span class="sxs-lookup"><span data-stu-id="84c2e-155">Enabled<sup>1</span></span></sup> |

> <sup><span data-ttu-id="84c2e-156">1与 </sup> 禁用的功能相关的语音命令不起作用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-156">1</sup> Voice commands that relate to disabled features do not function.</span></span>  
> <sup><span data-ttu-id="84c2e-157">2有关 </sup> 如何配置这些功能的详细信息，请参阅 [选择展台应用](#plan-kiosk-apps)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-157">2</sup> For more information about how to configure these features, see [Select kiosk apps](#plan-kiosk-apps).</span></span>  
> <sup><span data-ttu-id="84c2e-158">3 </sup> 即使禁用 Cortana，也会启用内置语音命令。</span><span class="sxs-lookup"><span data-stu-id="84c2e-158">3</sup> Even if Cortana is disabled, the built-in voice commands are enabled.</span></span>

<span data-ttu-id="84c2e-159">下表列出了不同展台模式的用户支持功能。</span><span class="sxs-lookup"><span data-stu-id="84c2e-159">The following table lists the user support features of the different kiosk modes.</span></span>

| &nbsp; |<span data-ttu-id="84c2e-160">支持的用户类型</span><span class="sxs-lookup"><span data-stu-id="84c2e-160">Supported user types</span></span> | <span data-ttu-id="84c2e-161">自动登录</span><span class="sxs-lookup"><span data-stu-id="84c2e-161">Automatic sign-in</span></span> | <span data-ttu-id="84c2e-162">多个访问级别</span><span class="sxs-lookup"><span data-stu-id="84c2e-162">Multiple access levels</span></span> |
| --- | --- | --- | --- |
|<span data-ttu-id="84c2e-163">单应用展台</span><span class="sxs-lookup"><span data-stu-id="84c2e-163">Single-app kiosk</span></span> |<span data-ttu-id="84c2e-164">托管服务帐户在 Azure Active Directory (AAD) 或本地帐户中 (MSA) </span><span class="sxs-lookup"><span data-stu-id="84c2e-164">Managed Service Account (MSA) in Azure Active Directory (AAD) or local account</span></span> |<span data-ttu-id="84c2e-165">是</span><span class="sxs-lookup"><span data-stu-id="84c2e-165">Yes</span></span> |<span data-ttu-id="84c2e-166">否</span><span class="sxs-lookup"><span data-stu-id="84c2e-166">No</span></span> |
|<span data-ttu-id="84c2e-167">多应用展台</span><span class="sxs-lookup"><span data-stu-id="84c2e-167">Multi-app kiosk</span></span> |<span data-ttu-id="84c2e-168">AAD 帐户</span><span class="sxs-lookup"><span data-stu-id="84c2e-168">AAD account</span></span> |<span data-ttu-id="84c2e-169">否</span><span class="sxs-lookup"><span data-stu-id="84c2e-169">No</span></span> |<span data-ttu-id="84c2e-170">是</span><span class="sxs-lookup"><span data-stu-id="84c2e-170">Yes</span></span> |

<span data-ttu-id="84c2e-171">有关如何使用这些功能的示例，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="84c2e-171">For examples of how to use these capabilities, see the following table.</span></span>

|<span data-ttu-id="84c2e-172">使用单应用展台进行以下操作：</span><span class="sxs-lookup"><span data-stu-id="84c2e-172">Use a single-app kiosk for:</span></span> |<span data-ttu-id="84c2e-173">使用多应用展台进行以下操作：</span><span class="sxs-lookup"><span data-stu-id="84c2e-173">Use a multi-app kiosk for:</span></span> |
| --- | --- |
|<span data-ttu-id="84c2e-174">仅运行新员工的 Dynamics 365 指南的设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-174">A device that runs only a Dynamics 365 Guide for new employees.</span></span> |<span data-ttu-id="84c2e-175">为一系列员工运行指南和远程协助的设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-175">A device that runs both Guides and Remote Assistance for a range of employees.</span></span> |
|<span data-ttu-id="84c2e-176">仅运行自定义应用的设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-176">A device that runs only a custom app.</span></span> |<span data-ttu-id="84c2e-177">作为大多数用户的展台工作的设备 (仅运行自定义应用) ，但作为特定用户组的标准设备运行。</span><span class="sxs-lookup"><span data-stu-id="84c2e-177">A device that functions as a kiosk for most users (running only a custom app), but functions as a standard device for a specific group of users.</span></span> |

### <span data-ttu-id="84c2e-178">规划展台应用</span><span class="sxs-lookup"><span data-stu-id="84c2e-178">Plan kiosk apps</span></span>

<span data-ttu-id="84c2e-179">有关如何选择展台应用的一般信息，请参阅 [ (展台模式下为分配的 access 选择应用指南) ](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-179">For general information about how to choose kiosk apps, see [Guidelines for choosing an app for assigned access (kiosk mode)](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app).</span></span>

<span data-ttu-id="84c2e-180">如果你使用 Windows Device Portal 配置单应用展台，请在安装过程中选择该应用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-180">If you use the Windows Device Portal to configure a single-app kiosk, you select the app during the setup process.</span></span>  

<span data-ttu-id="84c2e-181">如果你使用 (MDM) 系统或预配包来配置展台模式的移动设备管理，请使用 [AssignedAccess 配置服务提供程序 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 来指定应用程序。</span><span class="sxs-lookup"><span data-stu-id="84c2e-181">If you use a Mobile Device Management (MDM) system or a provisioning package to configure kiosk mode, you use the [AssignedAccess Configuration Service Provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) to specify applications.</span></span> <span data-ttu-id="84c2e-182">CSP 使用 [应用程序用户模型 id (aumid) ](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 来标识应用程序。</span><span class="sxs-lookup"><span data-stu-id="84c2e-182">The CSP uses [Application User Model IDs (AUMIDs)](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) to identify applications.</span></span> <span data-ttu-id="84c2e-183">下表列出了可在多应用展台中使用的一些内置应用程序的 Aumid。</span><span class="sxs-lookup"><span data-stu-id="84c2e-183">The following table lists the AUMIDs of some in-box applications that you can use in a multi-app kiosk.</span></span>

> [!CAUTION]
> <span data-ttu-id="84c2e-184">您不能选择 "外壳" 应用作为展台应用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-184">You cannot select the Shell app as a kiosk app.</span></span> <span data-ttu-id="84c2e-185">此外，我们 **建议你不要选择 "** microsoft Edge"、"microsoft Store" 或 "文件资源管理器" 作为展台应用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-185">Addition, we recommend that you do **not** select Microsoft Edge, Microsoft Store, or File Explorer as a kiosk app.</span></span>  

<a id="aumids"></a>

|<span data-ttu-id="84c2e-186">应用名称</span><span class="sxs-lookup"><span data-stu-id="84c2e-186">App Name</span></span> |<span data-ttu-id="84c2e-187">AUMID</span><span class="sxs-lookup"><span data-stu-id="84c2e-187">AUMID</span></span> |
| --- | --- |
|<span data-ttu-id="84c2e-188">3D 查看器</span><span class="sxs-lookup"><span data-stu-id="84c2e-188">3D Viewer</span></span> |<span data-ttu-id="84c2e-189">Microsoft3DViewer \ _8wekyb3d8bbwe \！Microsoft3DViewer</span><span class="sxs-lookup"><span data-stu-id="84c2e-189">Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\!Microsoft.Microsoft3DViewer</span></span> |
|<span data-ttu-id="84c2e-190">日历</span><span class="sxs-lookup"><span data-stu-id="84c2e-190">Calendar</span></span> |<span data-ttu-id="84c2e-191">windowscommunicationsapps \ _8wekyb3d8bbwe \！ windowslive。</span><span class="sxs-lookup"><span data-stu-id="84c2e-191">microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\!microsoft.windowslive.calendar</span></span> |
|<span data-ttu-id="84c2e-192">相机 <sup> 1、2</span><span class="sxs-lookup"><span data-stu-id="84c2e-192">Camera<sup>1, 2</span></span></sup> |<span data-ttu-id="84c2e-193">HoloCamera \ _cw5n1h2txyewy \！HoloCamera</span><span class="sxs-lookup"><span data-stu-id="84c2e-193">HoloCamera\_cw5n1h2txyewy\!HoloCamera</span></span> |
|<span data-ttu-id="84c2e-194">Cortana <sup> 3</span><span class="sxs-lookup"><span data-stu-id="84c2e-194">Cortana<sup>3</span></span></sup> |<span data-ttu-id="84c2e-195">549981C3F5F10 \ _8wekyb3d8bbwe \！应用</span><span class="sxs-lookup"><span data-stu-id="84c2e-195">Microsoft.549981C3F5F10\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="84c2e-196">HoloLens 上的设备选取器 (第一代) </span><span class="sxs-lookup"><span data-stu-id="84c2e-196">Device Picker on HoloLens (1st gen)</span></span> |<span data-ttu-id="84c2e-197">HoloDevicesFlow \ _cw5n1h2txyewy \！HoloDevicesFlow</span><span class="sxs-lookup"><span data-stu-id="84c2e-197">HoloDevicesFlow\_cw5n1h2txyewy\!HoloDevicesFlow</span></span> |
|<span data-ttu-id="84c2e-198">HoloLens 2 上的设备选取器</span><span class="sxs-lookup"><span data-stu-id="84c2e-198">Device Picker on HoloLens 2</span></span> |<span data-ttu-id="84c2e-199">DevicesFlowHost \ _cw5n1h2txyewy \！DevicesFlowHost</span><span class="sxs-lookup"><span data-stu-id="84c2e-199">Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\!Microsoft.Windows.DevicesFlowHost</span></span> |
|<span data-ttu-id="84c2e-200">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="84c2e-200">Dynamics 365 Guides</span></span> |<span data-ttu-id="84c2e-201">Dynamics365 _8wekyb3d8bbwe \！MicrosoftGuides</span><span class="sxs-lookup"><span data-stu-id="84c2e-201">Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\!MicrosoftGuides</span></span> |
|<span data-ttu-id="84c2e-202">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="84c2e-202">Dynamics 365 Remote Assist</span></span> |<span data-ttu-id="84c2e-203">MicrosoftRemoteAssist \ _8wekyb3d8bbwe \！RemoteAssist</span><span class="sxs-lookup"><span data-stu-id="84c2e-203">Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\!Microsoft.RemoteAssist</span></span> |
|<span data-ttu-id="84c2e-204">反馈 &nbsp; 中心</span><span class="sxs-lookup"><span data-stu-id="84c2e-204">Feedback&nbsp;Hub</span></span> |<span data-ttu-id="84c2e-205">WindowsFeedbackHub \ _8wekyb3d8bbwe \！应用</span><span class="sxs-lookup"><span data-stu-id="84c2e-205">Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="84c2e-206">文件资源管理器</span><span class="sxs-lookup"><span data-stu-id="84c2e-206">File Explorer</span></span> |<span data-ttu-id="84c2e-207">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span><span class="sxs-lookup"><span data-stu-id="84c2e-207">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App</span></span> |
|<span data-ttu-id="84c2e-208">Mail</span><span class="sxs-lookup"><span data-stu-id="84c2e-208">Mail</span></span> |<span data-ttu-id="84c2e-209">windowscommunicationsapps_8wekyb3d8bbwe！ windowslive！</span><span class="sxs-lookup"><span data-stu-id="84c2e-209">microsoft.windowscommunicationsapps_8wekyb3d8bbwe!microsoft.windowslive.mail</span></span> |
|<span data-ttu-id="84c2e-210">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="84c2e-210">Microsoft Store</span></span> |<span data-ttu-id="84c2e-211">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span><span class="sxs-lookup"><span data-stu-id="84c2e-211">Microsoft.WindowsStore_8wekyb3d8bbwe!App</span></span> |
|<span data-ttu-id="84c2e-212">Miracast <sup> 4</span><span class="sxs-lookup"><span data-stu-id="84c2e-212">Miracast<sup>4</span></span></sup> |&nbsp; |
|<span data-ttu-id="84c2e-213">电影和电视</span><span class="sxs-lookup"><span data-stu-id="84c2e-213">Movies & TV</span></span> |<span data-ttu-id="84c2e-214">ZuneVideo \ _8wekyb3d8bbwe \！ZuneVideo</span><span class="sxs-lookup"><span data-stu-id="84c2e-214">Microsoft.ZuneVideo\_8wekyb3d8bbwe\!Microsoft.ZuneVideo</span></span> |
|<span data-ttu-id="84c2e-215">OneDrive</span><span class="sxs-lookup"><span data-stu-id="84c2e-215">OneDrive</span></span> |<span data-ttu-id="84c2e-216">microsoftskydrive \ _8wekyb3d8bbwe \！应用</span><span class="sxs-lookup"><span data-stu-id="84c2e-216">microsoft.microsoftskydrive\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="84c2e-217">照片</span><span class="sxs-lookup"><span data-stu-id="84c2e-217">Photos</span></span> |<span data-ttu-id="84c2e-218">_8wekyb3d8bbwe \ 照片。应用</span><span class="sxs-lookup"><span data-stu-id="84c2e-218">Microsoft.Windows.Photos\_8wekyb3d8bbwe\!App</span></span> |
|<span data-ttu-id="84c2e-219">“设置”</span><span class="sxs-lookup"><span data-stu-id="84c2e-219">Settings</span></span> |<span data-ttu-id="84c2e-220">HolographicSystemSettings \ _cw5n1h2txyewy \！应用</span><span class="sxs-lookup"><span data-stu-id="84c2e-220">HolographicSystemSettings\_cw5n1h2txyewy\!App</span></span> |
|<span data-ttu-id="84c2e-221">提示</span><span class="sxs-lookup"><span data-stu-id="84c2e-221">Tips</span></span> |<span data-ttu-id="84c2e-222">HoloLensTips \ _8wekyb3d8bbwe \！HoloLensTips</span><span class="sxs-lookup"><span data-stu-id="84c2e-222">Microsoft.HoloLensTips\_8wekyb3d8bbwe\!HoloLensTips</span></span> |

> <sup><span data-ttu-id="84c2e-223">1 </sup> 要启用照片或视频捕获，您必须将相机应用启用为展台应用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-223">1</sup> To enable photo or video capture, you have to enable the Camera app as a kiosk app.</span></span>  
> <sup><span data-ttu-id="84c2e-224">2 </sup> 启用摄像头应用时，请注意以下条件：</span><span class="sxs-lookup"><span data-stu-id="84c2e-224">2</sup> When you enable the Camera app, be aware of the following conditions:</span></span>
> - <span data-ttu-id="84c2e-225">"快速操作" 菜单包含 "照片" 和 "视频" 按钮。</span><span class="sxs-lookup"><span data-stu-id="84c2e-225">The Quick Actions menu includes the Photo and Video buttons.</span></span>  
> - <span data-ttu-id="84c2e-226">你还应启用可与图片交互或检索图片的应用 (例如照片、邮件或 OneDrive) 。</span><span class="sxs-lookup"><span data-stu-id="84c2e-226">You should also enable an app (such as Photos, Mail, or OneDrive) that can interact with or retrieve pictures.</span></span>  
>  
> <sup><span data-ttu-id="84c2e-227">3 </sup> 即使不将 Cortana 启用为展台应用，也会启用内置语音命令。</span><span class="sxs-lookup"><span data-stu-id="84c2e-227">3</sup> Even if you do not enable Cortana as a kiosk app, built-in voice commands are enabled.</span></span> <span data-ttu-id="84c2e-228">但是，与禁用的功能相关的命令不起作用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-228">However, commands that are related to disabled features have no effect.</span></span>  
> <sup><span data-ttu-id="84c2e-229">4 </sup> 不能直接启用 Miracast。</span><span class="sxs-lookup"><span data-stu-id="84c2e-229">4</sup> You cannot enable Miracast directly.</span></span> <span data-ttu-id="84c2e-230">若要将 Miracast 启用为展台应用，请启用相机应用和设备选取器应用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-230">To enable Miracast as a kiosk app enable the Camera app and the Device Picker app.</span></span>

### <span data-ttu-id="84c2e-231">规划用户和设备组</span><span class="sxs-lookup"><span data-stu-id="84c2e-231">Plan user and device groups</span></span>

<span data-ttu-id="84c2e-232">在 MDM 环境中，使用组管理设备配置和用户访问。</span><span class="sxs-lookup"><span data-stu-id="84c2e-232">In an MDM environment, you use groups to manage device configurations and user access.</span></span> 

<span data-ttu-id="84c2e-233">展台配置文件包括 " **用户登录类型** " 设置。</span><span class="sxs-lookup"><span data-stu-id="84c2e-233">The kiosk configuration profile includes the **User logon type** setting.</span></span> <span data-ttu-id="84c2e-234">**用户登录类型** 标识用户 (或组，其中包含可以使用你添加的应用或应用的用户) 。</span><span class="sxs-lookup"><span data-stu-id="84c2e-234">**User logon type** identifies the user (or group that contains the users) who can use the app or apps that you add.</span></span> <span data-ttu-id="84c2e-235">如果用户使用未包含在配置文件中的帐户登录，则该用户无法使用展台上的应用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-235">If a user signs in by using an account that is not included in the configuration profile, that user cannot use apps on the kiosk.</span></span>  

> [!NOTE]  
> <span data-ttu-id="84c2e-236">单应用展台的 **用户登录类型** 指定单个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="84c2e-236">The **User logon type** of a single-app kiosk specifies a single user account.</span></span> <span data-ttu-id="84c2e-237">这是在其下运行展台的用户上下文。</span><span class="sxs-lookup"><span data-stu-id="84c2e-237">This is the user context under which the kiosk runs.</span></span> <span data-ttu-id="84c2e-238">多应用展台的 **用户登录类型** 可以指定可以使用展台的一个或多个用户帐户或组。</span><span class="sxs-lookup"><span data-stu-id="84c2e-238">The **User logon type** of a multi-app kiosk can specify one or more user accounts or groups that can use the kiosk.</span></span>

<span data-ttu-id="84c2e-239">在将 kiosk 配置部署到设备之前，必须将 kiosk 配置配置文件 *分配* 给包含设备的组或可登录设备的用户。</span><span class="sxs-lookup"><span data-stu-id="84c2e-239">Before you can deploy the kiosk configuration to a device, you have to *assign* the kiosk configuration profile to a group that contains the device or a user who can sign in to the device.</span></span> <span data-ttu-id="84c2e-240">此设置将产生如下所示的行为。</span><span class="sxs-lookup"><span data-stu-id="84c2e-240">This setting produces behavior such as the following.</span></span>

- <span data-ttu-id="84c2e-241">如果设备是分配组的成员，则在任何用户首次登录设备时，展台配置将部署到设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-241">If the device is a member of the assigned group, the kiosk configuration deploys to the device the first time that any user signs in on the device.</span></span>  
- <span data-ttu-id="84c2e-242">如果设备不是分配组的成员，但属于该组成员的用户登录，则 kiosk 配置将在此时部署到设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-242">If the device is not a member of the assigned group, but a user who is a member of that group signs in, the kiosk configuration deploys to the device at that time.</span></span>

<span data-ttu-id="84c2e-243">有关在 Intune 中分配配置文件的效果的完整讨论，请参阅 [在 Microsoft Intune 中分配用户和设备配置文件](https://docs.microsoft.com/intune/configuration/device-profile-assign)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-243">For a full discussion of the effects of assigning configuration profiles in Intune, see [Assign user and device profiles in Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-profile-assign).</span></span>

> [!NOTE]  
> <span data-ttu-id="84c2e-244">以下示例介绍了多应用网亭。</span><span class="sxs-lookup"><span data-stu-id="84c2e-244">The following examples describe multi-app kiosks.</span></span> <span data-ttu-id="84c2e-245">单应用网亭以类似的方式运行，但只有一个用户帐户才获得展台体验。</span><span class="sxs-lookup"><span data-stu-id="84c2e-245">Single-app kiosks behave in a similar manner, but only one user account gets the kiosk experience.</span></span>

**<span data-ttu-id="84c2e-246">示例 1</span><span class="sxs-lookup"><span data-stu-id="84c2e-246">Example 1</span></span>**

<span data-ttu-id="84c2e-247">为设备和用户使用单个组 (组 1) 。</span><span class="sxs-lookup"><span data-stu-id="84c2e-247">You use a single group (Group 1) for both devices and users.</span></span> <span data-ttu-id="84c2e-248">一个设备和用户 A、B 和 C 是该组的成员。</span><span class="sxs-lookup"><span data-stu-id="84c2e-248">One device and users A, B, and C are members of this group.</span></span> <span data-ttu-id="84c2e-249">配置展台配置文件的方式如下所示：</span><span class="sxs-lookup"><span data-stu-id="84c2e-249">You configure the kiosk configuration profile as follows:</span></span>  

- <span data-ttu-id="84c2e-250">**用户登录类型**：组1</span><span class="sxs-lookup"><span data-stu-id="84c2e-250">**User logon type**: Group 1</span></span>
- <span data-ttu-id="84c2e-251">**已分配的组**：组1</span><span class="sxs-lookup"><span data-stu-id="84c2e-251">**Assigned group**: Group 1</span></span>

<span data-ttu-id="84c2e-252">无论哪个用户首先登录到设备 (并通过 "全新体验" 或 "OOBE) "，"展台配置" 都将部署到设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-252">Regardless of which user signs on to the device first (and goes through the Out-of-Box Experience, or OOBE), the kiosk configuration deploys to the device.</span></span> <span data-ttu-id="84c2e-253">用户 A、B 和 C 均可登录到设备并获取 kiosk 体验。</span><span class="sxs-lookup"><span data-stu-id="84c2e-253">Users A, B, and C can all sign in to the device and get the kiosk experience.</span></span>

**<span data-ttu-id="84c2e-254">示例 2</span><span class="sxs-lookup"><span data-stu-id="84c2e-254">Example 2</span></span>**

<span data-ttu-id="84c2e-255">您向需要不同展台体验的两个不同供应商推出了设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-255">You contract out devices to two different vendors who need different kiosk experiences.</span></span> <span data-ttu-id="84c2e-256">两个供应商都有用户，您希望所有用户都可以从其自己的供应商和其他供应商处访问展台。</span><span class="sxs-lookup"><span data-stu-id="84c2e-256">Both vendors have users, and you want all the users to have access to kiosks from both their own vendor and the other vendor.</span></span> <span data-ttu-id="84c2e-257">按如下方式配置组：</span><span class="sxs-lookup"><span data-stu-id="84c2e-257">You configure groups as follows:</span></span>

- <span data-ttu-id="84c2e-258">设备组1：</span><span class="sxs-lookup"><span data-stu-id="84c2e-258">Device Group 1:</span></span>
  - <span data-ttu-id="84c2e-259">设备 1 (供应商 1) </span><span class="sxs-lookup"><span data-stu-id="84c2e-259">Device 1 (Vendor 1)</span></span>
  - <span data-ttu-id="84c2e-260">设备 2 (供应商 1) </span><span class="sxs-lookup"><span data-stu-id="84c2e-260">Device 2 (Vendor 1)</span></span>

- <span data-ttu-id="84c2e-261">设备组2：</span><span class="sxs-lookup"><span data-stu-id="84c2e-261">Device Group 2:</span></span>
  - <span data-ttu-id="84c2e-262">设备 3 (供应商 2) </span><span class="sxs-lookup"><span data-stu-id="84c2e-262">Device 3 (Vendor 2)</span></span>
  - <span data-ttu-id="84c2e-263">设备 4 (供应商 2) </span><span class="sxs-lookup"><span data-stu-id="84c2e-263">Device 4 (Vendor 2)</span></span>

- <span data-ttu-id="84c2e-264">用户组：</span><span class="sxs-lookup"><span data-stu-id="84c2e-264">User Group:</span></span>
  - <span data-ttu-id="84c2e-265">用户 A (供应商 1) </span><span class="sxs-lookup"><span data-stu-id="84c2e-265">User A (Vendor 1)</span></span>
  - <span data-ttu-id="84c2e-266">用户 B (供应商 2) </span><span class="sxs-lookup"><span data-stu-id="84c2e-266">User B (Vendor 2)</span></span>

<span data-ttu-id="84c2e-267">创建两个具有以下设置的展台配置文件：</span><span class="sxs-lookup"><span data-stu-id="84c2e-267">You create two kiosk configuration profiles that have the following settings:</span></span>

- <span data-ttu-id="84c2e-268">展台档案1：</span><span class="sxs-lookup"><span data-stu-id="84c2e-268">Kiosk Profile 1:</span></span>
   - <span data-ttu-id="84c2e-269">**用户登录类型**：用户组</span><span class="sxs-lookup"><span data-stu-id="84c2e-269">**User logon type**: User Group</span></span>
   - <span data-ttu-id="84c2e-270">**已分配的组**：设备组1</span><span class="sxs-lookup"><span data-stu-id="84c2e-270">**Assigned group**: Device Group 1</span></span>

- <span data-ttu-id="84c2e-271">展台档案2：</span><span class="sxs-lookup"><span data-stu-id="84c2e-271">Kiosk Profile 2:</span></span>
   - <span data-ttu-id="84c2e-272">**用户登录类型**：用户组</span><span class="sxs-lookup"><span data-stu-id="84c2e-272">**User logon type**: User Group</span></span>
   - <span data-ttu-id="84c2e-273">**已分配的组**：设备组2</span><span class="sxs-lookup"><span data-stu-id="84c2e-273">**Assigned group**: Device Group 2</span></span>

<span data-ttu-id="84c2e-274">这些配置将产生以下结果：</span><span class="sxs-lookup"><span data-stu-id="84c2e-274">These configurations produce the following results:</span></span>

- <span data-ttu-id="84c2e-275">当任何用户登录到设备1或设备2时，Intune 将展台配置文件1部署到该设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-275">When any user signs in to Device 1 or Device 2, Intune deploys Kiosk Profile 1 to that device.</span></span>
- <span data-ttu-id="84c2e-276">当任何用户登录到设备3或设备4时，Intune 将展台配置文件2部署到该设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-276">When any user signs in to Device 3 or Device 4, Intune deploys Kiosk Profile 2 to that device.</span></span>
- <span data-ttu-id="84c2e-277">用户 A 和用户 B 可以登录到四个设备中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="84c2e-277">User A and user B can sign in to any of the four devices.</span></span> <span data-ttu-id="84c2e-278">如果他们登录到设备1或设备2，他们将看到供应商1的展台体验。</span><span class="sxs-lookup"><span data-stu-id="84c2e-278">If they sign in to Device 1 or Device 2, they see the Vendor 1 kiosk experience.</span></span> <span data-ttu-id="84c2e-279">如果他们登录到设备3或设备4，他们将看到供应商2的展台体验。</span><span class="sxs-lookup"><span data-stu-id="84c2e-279">If they sign in to Device 3 or Device 4, they see the Vendor 2 kiosk experience.</span></span>

#### <span data-ttu-id="84c2e-280">配置文件冲突</span><span class="sxs-lookup"><span data-stu-id="84c2e-280">Profile conflicts</span></span>

<span data-ttu-id="84c2e-281">如果两个或更多展台配置文件的目标设备相同，则会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="84c2e-281">If two or more kiosk configuration profiles target the same device, they conflict.</span></span> <span data-ttu-id="84c2e-282">在 Intune 托管设备的情况下，Intune 不会应用任何冲突的配置文件。</span><span class="sxs-lookup"><span data-stu-id="84c2e-282">In the case of Intune-managed devices, Intune does not apply any of the conflicting profiles.</span></span>

<span data-ttu-id="84c2e-283">其他类型的配置文件和策略（如与展台配置文件无关的设备限制）不会与展台配置文件冲突。</span><span class="sxs-lookup"><span data-stu-id="84c2e-283">Other kinds of profiles and policies, such as device restrictions that are not related to the kiosk configuration profile, do not conflict with the kiosk configuration profile.</span></span>

### <span data-ttu-id="84c2e-284">选择部署方法</span><span class="sxs-lookup"><span data-stu-id="84c2e-284">Select a deployment method</span></span>

<span data-ttu-id="84c2e-285">你可以选择以下方法之一来部署展台配置：</span><span class="sxs-lookup"><span data-stu-id="84c2e-285">You can select one of the following methods to deploy kiosk configurations:</span></span>

- [<span data-ttu-id="84c2e-286"> (MDM) 服务的 Microsoft Intune 或其他移动设备管理</span><span class="sxs-lookup"><span data-stu-id="84c2e-286">Microsoft Intune or other mobile device management (MDM) service</span></span>](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="84c2e-287">设置包</span><span class="sxs-lookup"><span data-stu-id="84c2e-287">Provisioning package</span></span>](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [<span data-ttu-id="84c2e-288">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="84c2e-288">Windows Device Portal</span></span>](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > <span data-ttu-id="84c2e-289">由于此方法需要在设备上启用开发人员模式，因此我们建议仅将其用于演示。</span><span class="sxs-lookup"><span data-stu-id="84c2e-289">Because this method requires that Developer Mode be enabled on the device, we recommend that you use it only for demonstrations.</span></span>

<span data-ttu-id="84c2e-290">下表列出了每个部署方法的功能和优点。</span><span class="sxs-lookup"><span data-stu-id="84c2e-290">The following table lists the capabilities and benefits of each of the deployment methods.</span></span>

| &nbsp; |<span data-ttu-id="84c2e-291">使用 Windows Device Portal 进行部署</span><span class="sxs-lookup"><span data-stu-id="84c2e-291">Deploy by using Windows Device Portal</span></span> |<span data-ttu-id="84c2e-292">使用预配包进行部署</span><span class="sxs-lookup"><span data-stu-id="84c2e-292">Deploy by using a provisioning package</span></span> |<span data-ttu-id="84c2e-293">使用 MDM 进行部署</span><span class="sxs-lookup"><span data-stu-id="84c2e-293">Deploy by using MDM</span></span> |
| --------------------------- | ------------- | -------------------- | ---- |
|<span data-ttu-id="84c2e-294">部署单应用网亭</span><span class="sxs-lookup"><span data-stu-id="84c2e-294">Deploy single-app kiosks</span></span>   | <span data-ttu-id="84c2e-295">是</span><span class="sxs-lookup"><span data-stu-id="84c2e-295">Yes</span></span>           | <span data-ttu-id="84c2e-296">是</span><span class="sxs-lookup"><span data-stu-id="84c2e-296">Yes</span></span>                  | <span data-ttu-id="84c2e-297">是</span><span class="sxs-lookup"><span data-stu-id="84c2e-297">Yes</span></span>  |
|<span data-ttu-id="84c2e-298">部署多路应用网亭</span><span class="sxs-lookup"><span data-stu-id="84c2e-298">Deploy multi-app kiosks</span></span>    | <span data-ttu-id="84c2e-299">否</span><span class="sxs-lookup"><span data-stu-id="84c2e-299">No</span></span>            | <span data-ttu-id="84c2e-300">是</span><span class="sxs-lookup"><span data-stu-id="84c2e-300">Yes</span></span>                  | <span data-ttu-id="84c2e-301">是</span><span class="sxs-lookup"><span data-stu-id="84c2e-301">Yes</span></span>  |
|<span data-ttu-id="84c2e-302">仅部署到本地设备</span><span class="sxs-lookup"><span data-stu-id="84c2e-302">Deploy to local devices only</span></span> | <span data-ttu-id="84c2e-303">是</span><span class="sxs-lookup"><span data-stu-id="84c2e-303">Yes</span></span>           | <span data-ttu-id="84c2e-304">是</span><span class="sxs-lookup"><span data-stu-id="84c2e-304">Yes</span></span>                  | <span data-ttu-id="84c2e-305">否</span><span class="sxs-lookup"><span data-stu-id="84c2e-305">No</span></span>   |
|<span data-ttu-id="84c2e-306">使用开发人员模式进行部署</span><span class="sxs-lookup"><span data-stu-id="84c2e-306">Deploy by using Developer Mode</span></span> |<span data-ttu-id="84c2e-307">必需</span><span class="sxs-lookup"><span data-stu-id="84c2e-307">Required</span></span>       | <span data-ttu-id="84c2e-308">不需要</span><span class="sxs-lookup"><span data-stu-id="84c2e-308">Not required</span></span>            | <span data-ttu-id="84c2e-309">不需要</span><span class="sxs-lookup"><span data-stu-id="84c2e-309">Not required</span></span>   |
|<span data-ttu-id="84c2e-310">使用 Azure Active Directory (AAD) 进行部署</span><span class="sxs-lookup"><span data-stu-id="84c2e-310">Deploy by using Azure Active Directory (AAD)</span></span>  | <span data-ttu-id="84c2e-311">不需要</span><span class="sxs-lookup"><span data-stu-id="84c2e-311">Not required</span></span>            | <span data-ttu-id="84c2e-312">不需要</span><span class="sxs-lookup"><span data-stu-id="84c2e-312">Not required</span></span>                   | <span data-ttu-id="84c2e-313">必需</span><span class="sxs-lookup"><span data-stu-id="84c2e-313">Required</span></span>  |
|<span data-ttu-id="84c2e-314">自动部署</span><span class="sxs-lookup"><span data-stu-id="84c2e-314">Deploy automatically</span></span>      | <span data-ttu-id="84c2e-315">否</span><span class="sxs-lookup"><span data-stu-id="84c2e-315">No</span></span>            | <span data-ttu-id="84c2e-316">否</span><span class="sxs-lookup"><span data-stu-id="84c2e-316">No</span></span>                   | <span data-ttu-id="84c2e-317">是</span><span class="sxs-lookup"><span data-stu-id="84c2e-317">Yes</span></span>  |
|<span data-ttu-id="84c2e-318">部署速度</span><span class="sxs-lookup"><span data-stu-id="84c2e-318">Deployment speed</span></span>            | <span data-ttu-id="84c2e-319">迅速</span><span class="sxs-lookup"><span data-stu-id="84c2e-319">Fastest</span></span>       | <span data-ttu-id="84c2e-320">迅速</span><span class="sxs-lookup"><span data-stu-id="84c2e-320">Fast</span></span>                 | <span data-ttu-id="84c2e-321">慢速</span><span class="sxs-lookup"><span data-stu-id="84c2e-321">Slow</span></span> |
|<span data-ttu-id="84c2e-322">按比例部署</span><span class="sxs-lookup"><span data-stu-id="84c2e-322">Deploy at scale</span></span> | <span data-ttu-id="84c2e-323">不建议</span><span class="sxs-lookup"><span data-stu-id="84c2e-323">Not recommended</span></span>    | <span data-ttu-id="84c2e-324">不建议</span><span class="sxs-lookup"><span data-stu-id="84c2e-324">Not recommended</span></span>        | <span data-ttu-id="84c2e-325">推荐</span><span class="sxs-lookup"><span data-stu-id="84c2e-325">Recommended</span></span> |

## <span data-ttu-id="84c2e-326">使用 Microsoft Intune 或其他 MDM 设置单应用或多应用展台</span><span class="sxs-lookup"><span data-stu-id="84c2e-326">Use Microsoft Intune or other MDM to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="84c2e-327">若要使用 Microsoft Intune 或其他 MDM 系统设置展台模式，请按照下列步骤操作。</span><span class="sxs-lookup"><span data-stu-id="84c2e-327">To set up kiosk mode by using Microsoft Intune or another MDM system, follow these steps.</span></span>

1. <span data-ttu-id="84c2e-328">[准备注册设备](#mdmenroll)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-328">[Prepare to enroll the devices](#mdmenroll).</span></span>
1. <span data-ttu-id="84c2e-329">[创建展台配置文件](#mdmprofile)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-329">[Create a kiosk configuration profile](#mdmprofile).</span></span>
1. <span data-ttu-id="84c2e-330">配置展台。</span><span class="sxs-lookup"><span data-stu-id="84c2e-330">Configure the kiosk.</span></span>
   - <span data-ttu-id="84c2e-331">[配置单应用展台的设置](#mdmconfigsingle)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-331">[Configure the settings for a single-app kiosk](#mdmconfigsingle).</span></span>
   - <span data-ttu-id="84c2e-332">[配置多应用展台的设置](#mdmconfigmulti)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-332">[Configure the settings for a multi-app kiosk](#mdmconfigmulti).</span></span>
1. <span data-ttu-id="84c2e-333">[将展台配置文件分配到组](#mdmassign)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-333">[Assign the kiosk configuration profile to a group](#mdmassign).</span></span>
1. <span data-ttu-id="84c2e-334">部署设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-334">Deploy the devices.</span></span>
   - <span data-ttu-id="84c2e-335">[部署单应用展台](#mdmsingledeploy)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-335">[Deploy a single-app kiosk](#mdmsingledeploy).</span></span>
   - <span data-ttu-id="84c2e-336">[部署多应用展台](#mdmmultideploy)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-336">[Deploy a multi-app kiosk](#mdmmultideploy).</span></span>

### <a id="mdmenroll"></a><span data-ttu-id="84c2e-337">MDM，步骤 1 &ndash; 准备注册设备</span><span class="sxs-lookup"><span data-stu-id="84c2e-337">MDM, step 1 &ndash; Prepare to enroll the devices</span></span>

<span data-ttu-id="84c2e-338">你可以将 MDM 系统配置为在用户首次登录时自动注册 HoloLens 设备，或者让用户手动注册设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-338">You can configure your MDM system to enroll HoloLens devices automatically when the user first signs in, or have users enroll devices manually.</span></span> <span data-ttu-id="84c2e-339">设备还必须加入到 Azure AD 域，并分配给相应的组。</span><span class="sxs-lookup"><span data-stu-id="84c2e-339">The devices also have to be joined to your Azure AD domain, and assigned to the appropriate groups.</span></span>

<span data-ttu-id="84c2e-340">有关如何注册设备的详细信息，请参阅 [在 MDM 中注册 HoloLens](hololens-enroll-mdm.md) 和 [Windows 设备的 Intune 注册方法](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-340">For more information about how to enroll the devices, see [Enroll HoloLens in MDM](hololens-enroll-mdm.md) and [Intune enrollment methods for Windows devices](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods).</span></span>

### <a id="mdmprofile"></a><span data-ttu-id="84c2e-341">MDM、步骤 2 &ndash; 创建展台配置文件</span><span class="sxs-lookup"><span data-stu-id="84c2e-341">MDM, step 2 &ndash; Create a kiosk configuration profile</span></span>

1. <span data-ttu-id="84c2e-342">打开 [Azure](https://portal.azure.com/) 门户并登录到你的 Intune 管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="84c2e-342">Open the [Azure](https://portal.azure.com/) portal and sign in to your Intune administrator account.</span></span>
1. <span data-ttu-id="84c2e-343">选择 " **Microsoft Intune**  >  **设备配置"-配置文件**  >  **创建配置文件**。</span><span class="sxs-lookup"><span data-stu-id="84c2e-343">Select **Microsoft Intune** > **Device configuration - Profiles** > **Create profile**.</span></span>
1. <span data-ttu-id="84c2e-344">输入配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="84c2e-344">Enter a profile name.</span></span>
1. <span data-ttu-id="84c2e-345">选择 "**平台**  >  **Windows 10 及更高版本**"，然后选择 "**配置文件类型**  > **设备限制**"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-345">Select **Platform** > **Windows 10 and later**, and then select **Profile type** >**Device restrictions**.</span></span>
1. <span data-ttu-id="84c2e-346">选择 "**配置**  >  **展台**"，然后选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="84c2e-346">Select **Configure** > **Kiosk**, and then select one of the following:</span></span>
   - <span data-ttu-id="84c2e-347">若要创建单应用展台，请选择 "**展台模式**  >  **单应用展台**"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-347">To create a single-app kiosk, select **Kiosk Mode** > **Single-app kiosk**.</span></span>
   - <span data-ttu-id="84c2e-348">若要创建多应用程序亭，请选择 "**展台模式**  >  **多应用展台**"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-348">To create a multi-app kiosk, select **Kiosk Mode** > **Multi-app kiosk**.</span></span>
1. <span data-ttu-id="84c2e-349">要开始配置展台，请选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-349">To start configuring the kiosk, select **Add**.</span></span>

<span data-ttu-id="84c2e-350">根据所需的展台类型，后续步骤会有所不同。</span><span class="sxs-lookup"><span data-stu-id="84c2e-350">Your next steps differ depending on the type of kiosk that you want.</span></span> <span data-ttu-id="84c2e-351">有关详细信息，请选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="84c2e-351">For more information, select one of the following options:</span></span>  

- [<span data-ttu-id="84c2e-352">单应用展台</span><span class="sxs-lookup"><span data-stu-id="84c2e-352">Single-app kiosk</span></span>](#mdmconfigsingle)
- [<span data-ttu-id="84c2e-353">多应用展台</span><span class="sxs-lookup"><span data-stu-id="84c2e-353">Multi-app kiosk</span></span>](#mdmconfigmulti)

<span data-ttu-id="84c2e-354">有关如何创建展台配置文件的详细信息，请参阅 [windows 10 和 Windows 全息版 For Business 设备设置，以使用 Intune 作为专用展台运行](https://docs.microsoft.com/intune/configuration/kiosk-settings)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-354">For more information about how to create a kiosk configuration profile, see [Windows 10 and Windows Holographic for Business device settings to run as a dedicated kiosk using Intune](https://docs.microsoft.com/intune/configuration/kiosk-settings).</span></span>

### <a id="mdmconfigsingle"></a><span data-ttu-id="84c2e-355">MDM、步骤 3 (单应用) &ndash;  配置单应用展台的设置</span><span class="sxs-lookup"><span data-stu-id="84c2e-355">MDM, step 3 (single-app) &ndash;  Configure the settings for a single-app kiosk</span></span>

<span data-ttu-id="84c2e-356">本部分概述了单应用展台所需的设置。</span><span class="sxs-lookup"><span data-stu-id="84c2e-356">This section summarizes the settings that a single-app kiosk requires.</span></span> <span data-ttu-id="84c2e-357">有关更多详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="84c2e-357">For more details, see the following articles:</span></span>

- <span data-ttu-id="84c2e-358">有关如何在 Intune 中配置展台配置文件的信息，请参阅 [如何使用 Microsoft Intune 配置展台模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-358">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="84c2e-359">有关 Intune 中的单应用网亭可用设置的详细信息，请参阅 [单个全屏应用网亭](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="84c2e-359">For more information about the available settings for single-app kiosks in Intune, see [Single full-screen app kiosks](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)</span></span>
- <span data-ttu-id="84c2e-360">对于其他 MDM 服务，请参阅提供商文档中的说明。</span><span class="sxs-lookup"><span data-stu-id="84c2e-360">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="84c2e-361">如果必须使用自定义 XML 配置在 MDM 服务中设置展台，请 [创建一个定义 kiosk 配置的 XML 文件](#ppkioskconfig)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-361">If you have to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span>

1. <span data-ttu-id="84c2e-362">选择 "**用户登录类型**  >  **本地用户帐户**"，然后输入可登录到展台的本地 (设备) 帐户或 Microsoft 帐户 (MSA) 的用户名。</span><span class="sxs-lookup"><span data-stu-id="84c2e-362">Select **User logon type** > **Local user account**, and then enter the user name of the local (device) account or Microsoft Account (MSA) that can sign in to the kiosk.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="84c2e-363">Windows 全息版商业版不支持**自动登录**用户帐户类型。</span><span class="sxs-lookup"><span data-stu-id="84c2e-363">**Autologon** user account types aren't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="84c2e-364">选择 "**应用程序类型**  >  **存储应用**"，然后从列表中选择一个应用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-364">Select **Application type** > **Store app**, and then select an app from the list.</span></span>

<span data-ttu-id="84c2e-365">下一步是将配置文件 [分配](#mdmassign) 给组。</span><span class="sxs-lookup"><span data-stu-id="84c2e-365">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmconfigmulti"></a><span data-ttu-id="84c2e-366">MDM、步骤 3 (多应用) &ndash; 配置多应用展台的设置</span><span class="sxs-lookup"><span data-stu-id="84c2e-366">MDM, step 3 (multi-app) &ndash; Configure the settings for a multi-app kiosk</span></span>

<span data-ttu-id="84c2e-367">本部分概述了多应用展台所需的设置。</span><span class="sxs-lookup"><span data-stu-id="84c2e-367">This section summarizes the settings that a multi-app kiosk requires.</span></span> <span data-ttu-id="84c2e-368">有关更多详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="84c2e-368">For more detailed information, see the following articles:</span></span>

- <span data-ttu-id="84c2e-369">有关如何在 Intune 中配置展台配置文件的信息，请参阅 [如何使用 Microsoft Intune 配置展台模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-369">For information about how to configure a kiosk configuration profile in Intune, see [How to Configure Kiosk Mode Using Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune).</span></span>
- <span data-ttu-id="84c2e-370">有关 Intune 中的多应用网亭可用设置的详细信息，请参阅 [多路应用网亭](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span><span class="sxs-lookup"><span data-stu-id="84c2e-370">For more information about the available settings for multi-app kiosks in Intune, see [Multi-app kiosks](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)</span></span>
- <span data-ttu-id="84c2e-371">对于其他 MDM 服务，请参阅提供商文档中的说明。</span><span class="sxs-lookup"><span data-stu-id="84c2e-371">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="84c2e-372">如果需要使用自定义 XML 配置在 MDM 服务中设置展台，请 [创建一个定义 kiosk 配置的 XML 文件](#ppkioskconfig)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-372">If you need to use a custom XML configuration to set up a kiosk in your MDM service, [create an XML file that defines the kiosk configuration](#ppkioskconfig).</span></span> <span data-ttu-id="84c2e-373">如果使用 XML 文件，请确保包含 " [开始" 布局](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-373">If you use an XML file, make sure to include the [Start layout](#start-layout-for-hololens).</span></span>  
- <span data-ttu-id="84c2e-374">你可以选择将自定义开始布局与 Intune 或其他 MDM 服务配合使用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-374">You can optionally use a custom Start layout with Intune or other MDM services.</span></span> <span data-ttu-id="84c2e-375">有关详细信息，请参阅 [为 MDM (启动布局文件 Intune 和其他) ](#start-layout-file-for-mdm-intune-and-others)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-375">For more information, see [Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

1. <span data-ttu-id="84c2e-376">选择 **"在 S 模式设备中确定目标 Windows 10 设备"**  >  **No**</span><span class="sxs-lookup"><span data-stu-id="84c2e-376">Select **Target Windows 10 in S mode devices** > **No**.</span></span>  
   >[!NOTE]  
   > <span data-ttu-id="84c2e-377">S 模式在 Windows 全息版商业版上不受支持。</span><span class="sxs-lookup"><span data-stu-id="84c2e-377">S mode isn't supported on Windows Holographic for Business.</span></span>
1. <span data-ttu-id="84c2e-378">选择 "**用户登录类型**"  >  **Azure AD 用户或组**或**用户登录类型**  >  **HoloLens 访问者**，然后添加一个或多个用户组或帐户。</span><span class="sxs-lookup"><span data-stu-id="84c2e-378">Select **User logon type** > **Azure AD user or group** or **User logon type** > **HoloLens visitor**, and then add one or more user groups or accounts.</span></span>  

   <span data-ttu-id="84c2e-379">只有属于你在 " **用户登录类型** " 中指定的组或帐户的用户才能使用展台体验。</span><span class="sxs-lookup"><span data-stu-id="84c2e-379">Only users who belong to the groups or accounts that you specify in **User logon type** can use the kiosk experience.</span></span>

1. <span data-ttu-id="84c2e-380">使用以下选项选择一个或多个应用：</span><span class="sxs-lookup"><span data-stu-id="84c2e-380">Select one or more apps by using the following options:</span></span>
   - <span data-ttu-id="84c2e-381">若要添加已上载的业务线应用程序，请选择 " **添加应用商店应用** "，然后选择所需的应用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-381">To add an uploaded line-of-business app, select **Add store app** and then select the app that you want.</span></span>
   - <span data-ttu-id="84c2e-382">若要通过指定其 AUMID 添加应用，请选择 " **由 AUMID 添加** "，然后输入应用的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="84c2e-382">To add an app by specifying its AUMID, select **Add by AUMID** and then enter the AUMID of the app.</span></span> [<span data-ttu-id="84c2e-383">查看可用的 Aumid 列表</span><span class="sxs-lookup"><span data-stu-id="84c2e-383">See the list of available AUMIDs</span></span>](#aumids)

<span data-ttu-id="84c2e-384">下一步是将配置文件 [分配](#mdmassign) 给组。</span><span class="sxs-lookup"><span data-stu-id="84c2e-384">Your next step is to [assign](#mdmassign) the profile to a group.</span></span>

### <a id="mdmassign"></a><span data-ttu-id="84c2e-385">MDM，步骤 4 &ndash; 将展台配置文件分配到组</span><span class="sxs-lookup"><span data-stu-id="84c2e-385">MDM, step 4 &ndash; Assign the kiosk configuration profile to a group</span></span>

<span data-ttu-id="84c2e-386">使用展台配置文件的 " **分配** " 页面设置要在其中部署 kiosk 配置的位置。</span><span class="sxs-lookup"><span data-stu-id="84c2e-386">Use the **Assignments** page of the kiosk configuration profile to set where you want the kiosk configuration to deploy.</span></span> <span data-ttu-id="84c2e-387">在最简单的情况下，你将展台配置配置文件分配给将在使用 MDM 注册设备时包含 HoloLens 设备的组。</span><span class="sxs-lookup"><span data-stu-id="84c2e-387">In the simplest case, you assign the kiosk configuration profile to a group that will contain the HoloLens device when the device enrolls in MDM.</span></span>

### <a id="mdmsingledeploy"></a><span data-ttu-id="84c2e-388">MDM、步骤 5 (单应用) &ndash; 部署单应用展台</span><span class="sxs-lookup"><span data-stu-id="84c2e-388">MDM, step 5 (single-app) &ndash; Deploy a single-app kiosk</span></span>

<span data-ttu-id="84c2e-389">使用 MDM 系统时，可以在 OOBE 期间在 MDM 中注册设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-389">When you use an MDM system, you can enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="84c2e-390">在 OOBE 完成后，登录到设备非常简单。</span><span class="sxs-lookup"><span data-stu-id="84c2e-390">After OOBE finishes, signing in to the device is easy.</span></span>

<span data-ttu-id="84c2e-391">在 OOBE 期间，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="84c2e-391">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="84c2e-392">使用在展台配置文件中指定的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="84c2e-392">Sign in by using the account that you specified in the kiosk configuration profile.</span></span>
1. <span data-ttu-id="84c2e-393">注册设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-393">Enroll the device.</span></span> <span data-ttu-id="84c2e-394">请确保将设备添加到将设备配置文件分配到的组。</span><span class="sxs-lookup"><span data-stu-id="84c2e-394">Make sure that the device is added to the group that the kiosk configuration profile is assigned to.</span></span>
1. <span data-ttu-id="84c2e-395">等待 OOBE 完成，针对要下载和安装的应用商店应用以及要应用的策略。</span><span class="sxs-lookup"><span data-stu-id="84c2e-395">Wait for OOBE to finish, for the store app to download and install, and for policies to be applied.</span></span> <span data-ttu-id="84c2e-396">然后重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-396">Then restart the device.</span></span>

<span data-ttu-id="84c2e-397">下次登录设备时，展台应用应自动启动。</span><span class="sxs-lookup"><span data-stu-id="84c2e-397">The next time you sign in to the device, the kiosk app should automatically start.</span></span>

<span data-ttu-id="84c2e-398">如果此时看不到展台配置，请 [检查作业状态](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-398">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

### <a id="mdmmultideploy"></a><span data-ttu-id="84c2e-399">MDM、步骤 5 (多应用) &ndash; 部署多应用展台</span><span class="sxs-lookup"><span data-stu-id="84c2e-399">MDM, step 5 (multi-app) &ndash; Deploy a multi-app kiosk</span></span>

<span data-ttu-id="84c2e-400">使用 MDM 系统时，你可以将设备加入 Azure AD 租户，并在 OOBE 期间在 MDM 中注册设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-400">When you use an MDM system, you can join the device to your Azure AD tenant and enroll the device in MDM during OOBE.</span></span> <span data-ttu-id="84c2e-401">如果适用，请向用户提供注册信息，以便用户可以在 OOBE 过程中使用它。</span><span class="sxs-lookup"><span data-stu-id="84c2e-401">If appropriate, provide the enrollment information to the users so that they have it available during the OOBE process.</span></span>

> [!NOTE]  
> <span data-ttu-id="84c2e-402">如果您已将展台配置文件分配给包含用户的组，请确保其中一个用户帐户是登录到该设备的第一个帐户。</span><span class="sxs-lookup"><span data-stu-id="84c2e-402">If you have assigned the kiosk configuration profile to a group that contains users, make sure that one of those user accounts is the first account to sign in to the device.</span></span>

<span data-ttu-id="84c2e-403">在 OOBE 期间，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="84c2e-403">During OOBE, follow these steps:</span></span>

1. <span data-ttu-id="84c2e-404">使用属于 " **用户登录类型** " 组的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="84c2e-404">Sign in by using the account that belongs to the **User logon type** group.</span></span>
1. <span data-ttu-id="84c2e-405">注册设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-405">Enroll the device.</span></span>
1. <span data-ttu-id="84c2e-406">等待所有属于展台配置文件的应用下载并安装。</span><span class="sxs-lookup"><span data-stu-id="84c2e-406">Wait for any apps that are part of the kiosk configuration profile to download and install.</span></span> <span data-ttu-id="84c2e-407">此外，请等待应用策略。</span><span class="sxs-lookup"><span data-stu-id="84c2e-407">Also, wait for policies to be applied.</span></span>  
1. <span data-ttu-id="84c2e-408">在 OOBE 完成后，你可以通过 Microsoft store 或通过旁加载来安装其他应用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-408">After OOBE finishes, you can install additional apps from the Microsoft store or by sideloading.</span></span> <span data-ttu-id="84c2e-409">设备所属的组自动安装[所需的应用](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-409">[Required apps](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) for the group that the device belongs to install automatically.</span></span>
1. <span data-ttu-id="84c2e-410">安装完成后，重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="84c2e-410">After the installation finishes, restart the device.</span></span>

<span data-ttu-id="84c2e-411">下次使用属于 **用户登录类型**的帐户登录设备时，展台应用应自动启动。</span><span class="sxs-lookup"><span data-stu-id="84c2e-411">The next time you sign in to the device by using an account that belongs to the **User logon type**, the kiosk app should automatically launch.</span></span>

<span data-ttu-id="84c2e-412">如果此时看不到展台配置，请 [检查作业状态](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-412">If you don't see your kiosk configuration at this point, [check the assignment status](https://docs.microsoft.com/intune/configuration/device-profile-monitor).</span></span>

## <span data-ttu-id="84c2e-413">使用预配包设置单应用或多应用展台</span><span class="sxs-lookup"><span data-stu-id="84c2e-413">Use a provisioning package to set up a single-app or multi-app kiosk</span></span>

<span data-ttu-id="84c2e-414">若要使用预配包设置展台模式，请按照下列步骤操作。</span><span class="sxs-lookup"><span data-stu-id="84c2e-414">To set up kiosk mode by using a provisioning package, follow these steps.</span></span>

1. <span data-ttu-id="84c2e-415">[创建一个定义展台配置的 XML 文件](#ppkioskconfig)，包括 "开始" [布局](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-415">[Create an XML file that defines the kiosk configuration.](#ppkioskconfig), including a [Start layout](#start-layout-for-hololens).</span></span>
2. [<span data-ttu-id="84c2e-416">将 XML 文件添加到预配包。</span><span class="sxs-lookup"><span data-stu-id="84c2e-416">Add the XML file to a provisioning package.</span></span>](#ppconfigadd)
3. [<span data-ttu-id="84c2e-417">将预配包应用于 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="84c2e-417">Apply the provisioning package to HoloLens.</span></span>](#ppapply)

### <a id="ppkioskconfig"></a><span data-ttu-id="84c2e-418">预配程序包，步骤 1 &ndash; 创建展台配置 XML 文件</span><span class="sxs-lookup"><span data-stu-id="84c2e-418">Provisioning package, step 1 &ndash; Create a kiosk configuration XML file</span></span>

<span data-ttu-id="84c2e-419">按照 [常规说明为 Windows 桌面版创建展台配置 XML 文件](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)，但以下内容除外：</span><span class="sxs-lookup"><span data-stu-id="84c2e-419">Follow [the general instructions to create a kiosk configuration XML file for Windows desktop](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file), except for the following:</span></span>

- <span data-ttu-id="84c2e-420">不要在 Win32) 中包括经典 Windows 应用程序 (。</span><span class="sxs-lookup"><span data-stu-id="84c2e-420">Do not include Classic Windows applications (Win32).</span></span> <span data-ttu-id="84c2e-421">HoloLens 不支持这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="84c2e-421">HoloLens does not support these applications.</span></span>
- <span data-ttu-id="84c2e-422">使用适用于 HoloLens 的 [占位符开始布局 XML](#start-layout-for-hololens) 。</span><span class="sxs-lookup"><span data-stu-id="84c2e-422">Use the [placeholder Start layout XML](#start-layout-for-hololens) for HoloLens.</span></span>
- <span data-ttu-id="84c2e-423">可选：将来宾访问添加到展台配置</span><span class="sxs-lookup"><span data-stu-id="84c2e-423">Optional: Add guest access to the kiosk configuration</span></span>

#### <a id="ppkioskguest"></a><span data-ttu-id="84c2e-424">可选：将来宾访问添加到展台配置</span><span class="sxs-lookup"><span data-stu-id="84c2e-424">Optional: Add guest access to the kiosk configuration</span></span>

<span data-ttu-id="84c2e-425">在 XML 文件的 "配置" 部分中，可以将名为 "**访问者**" 的特殊组配置为允许来宾使用展台。 [ **Configs** ](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)</span><span class="sxs-lookup"><span data-stu-id="84c2e-425">In the [**Configs** section of the XML file](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs), you can configure a special group named **Visitor** to allow guests to use the kiosk.</span></span> <span data-ttu-id="84c2e-426">当展台配置为支持 **访问者** 特殊组时，登录页面中将添加一个 "**来宾**" 选项。</span><span class="sxs-lookup"><span data-stu-id="84c2e-426">When the kiosk is configured to support the **Visitor** special group, a "**Guest**" option is added to the sign-in page.</span></span> <span data-ttu-id="84c2e-427">**来宾**帐户不需要密码，并且与帐户关联的任何数据在帐户注销时都将被删除。</span><span class="sxs-lookup"><span data-stu-id="84c2e-427">The **Guest** account does not require a password, and any data that is associated with the account is deleted when the account signs out.</span></span>

<span data-ttu-id="84c2e-428">若要启用 **来宾** 帐户，请将以下代码片段添加到展台配置 XML：</span><span class="sxs-lookup"><span data-stu-id="84c2e-428">To enable the **Guest** account, add the following snippet to your kiosk configuration XML:</span></span>

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a><span data-ttu-id="84c2e-429">HoloLens 的占位符开始布局</span><span class="sxs-lookup"><span data-stu-id="84c2e-429">Placeholder Start layout for HoloLens</span></span>

<span data-ttu-id="84c2e-430">如果使用 [预配包](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 配置多应用展台，则该过程需要 "开始" 布局。</span><span class="sxs-lookup"><span data-stu-id="84c2e-430">If you use a [provisioning package](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) to configure a multi-app kiosk, the procedure requires a Start layout.</span></span> <span data-ttu-id="84c2e-431">Windows 全息版中不支持 "开始布局自定义"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-431">Start layout customization isn't supported in Windows Holographic for Business.</span></span> <span data-ttu-id="84c2e-432">因此，你必须使用占位符开始布局。</span><span class="sxs-lookup"><span data-stu-id="84c2e-432">Therefore, you'll have to use a placeholder Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="84c2e-433">由于单应用展台在用户登录时启动展台应用，因此它不使用 "开始" 菜单，也不需要具有 "开始" 布局。</span><span class="sxs-lookup"><span data-stu-id="84c2e-433">Because a single-app kiosk starts the kiosk app when a user signs in, it does not use a Start menu and does not have to have a Start layout.</span></span>

> [!NOTE]  
> <span data-ttu-id="84c2e-434">如果使用 [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 设置多应用展台，则可以选择使用 "开始" 布局。</span><span class="sxs-lookup"><span data-stu-id="84c2e-434">If you use [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) to set up a multi-app kiosk, you can optionally use a Start layout.</span></span> <span data-ttu-id="84c2e-435">有关详细信息，请参阅 [MDM (Intune 和其他) 的占位符启动布局文件 ](#start-layout-file-for-mdm-intune-and-others)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-435">For more information, see [Placeholder Start layout file for MDM (Intune and others)](#start-layout-file-for-mdm-intune-and-others).</span></span>

<span data-ttu-id="84c2e-436">对于 "开始" 布局，将以下 **StartLayout** 部分添加到展台预配 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="84c2e-436">For the Start layout, add the following **StartLayout** section to the kiosk provisioning XML file:</span></span>

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

#### <a id="start-layout-file-for-mdm-intune-and-others"></a><span data-ttu-id="84c2e-437">适用于 MDM (Intune 和其他人的占位符开始布局文件) </span><span class="sxs-lookup"><span data-stu-id="84c2e-437">Placeholder Start layout file for MDM (Intune and others)</span></span>

<span data-ttu-id="84c2e-438">将以下示例另存为 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="84c2e-438">Save the following sample as an XML file.</span></span> <span data-ttu-id="84c2e-439">在 Microsoft Intune 中配置多应用展台时，你可以使用此文件 (或在提供展台配置文件的其他 MDM 服务中使用此文件) 。</span><span class="sxs-lookup"><span data-stu-id="84c2e-439">You can use this file when you configure the multi-app kiosk in Microsoft Intune (or in another MDM service that provides a kiosk profile).</span></span>

> [!NOTE]
> <span data-ttu-id="84c2e-440">如果必须使用自定义设置和完整的 XML 配置来设置 MDM 服务中的展台，请使用 [预配包的启动布局说明](#start-layout-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-440">If you have to use a custom setting and full XML configuration to set up a kiosk in your MDM service, use the [Start layout instructions for a provisioning package](#start-layout-for-hololens).</span></span>

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

### <a id="ppconfigadd"></a><span data-ttu-id="84c2e-441">Prov.</span><span class="sxs-lookup"><span data-stu-id="84c2e-441">Prov.</span></span> <span data-ttu-id="84c2e-442">程序包，步骤 2 &ndash; 将 kiosk 配置 XML 文件添加到预配包</span><span class="sxs-lookup"><span data-stu-id="84c2e-442">package, step 2 &ndash; Add the kiosk configuration XML file to a provisioning package</span></span>

1. <span data-ttu-id="84c2e-443">打开 [Windows 配置设计器](https://www.microsoft.com/store/apps/9nblggh4tx22)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-443">Open [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22).</span></span>
1. <span data-ttu-id="84c2e-444">选择 " **高级设置**"，输入项目的名称，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-444">Select **Advanced provisioning**, enter a name for your project, and then select **Next**.</span></span>
1. <span data-ttu-id="84c2e-445">选择 " **Windows 10 全息**版"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-445">Select **Windows 10 Holographic**, and then select **Next**.</span></span>
1. <span data-ttu-id="84c2e-446">选择 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-446">Select **Finish**.</span></span> <span data-ttu-id="84c2e-447">此时将打开你的程序包的工作区。</span><span class="sxs-lookup"><span data-stu-id="84c2e-447">The workspace for your package opens.</span></span>
1. <span data-ttu-id="84c2e-448">选择 "**运行时设置**"  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**。</span><span class="sxs-lookup"><span data-stu-id="84c2e-448">Select **Runtime settings** > **AssignedAccess** > **MultiAppAssignedAccessSettings**.</span></span>
1. <span data-ttu-id="84c2e-449">在中心窗格中，选择 " **浏览** "，找到并选择您创建的展台配置 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="84c2e-449">In the center pane, select **Browse** to locate and select the kiosk configuration XML file that you created.</span></span>

   ![Windows 配置设计器中的 MultiAppAssignedAccessSettings 字段的屏幕截图](./images/multiappassignedaccesssettings.png)

1. <span data-ttu-id="84c2e-451">**可选**。</span><span class="sxs-lookup"><span data-stu-id="84c2e-451">**Optional**.</span></span> <span data-ttu-id="84c2e-452"> (如果你希望在设备的初始设置之后应用预配程序包，并且在展台设备上已有管理员用户，请跳过此步骤。 ) 选择 " **运行时设置** &gt; **帐户** &gt; **用户**"，然后创建用户帐户。</span><span class="sxs-lookup"><span data-stu-id="84c2e-452">(If you want to apply the provisioning package after the initial setup of the device, and there is an admin user already available on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a user account.</span></span> <span data-ttu-id="84c2e-453">提供用户名和密码，然后选择 " **UserGroup**  >  **管理员**"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-453">Provide a user name and password, and then select **UserGroup** > **Administrators**.</span></span>  
  
     <span data-ttu-id="84c2e-454">通过使用此帐户，你可以查看预配状态和日志。</span><span class="sxs-lookup"><span data-stu-id="84c2e-454">By using this account, you can view the provisioning status and logs.</span></span>  
1. <span data-ttu-id="84c2e-455">**可选**。</span><span class="sxs-lookup"><span data-stu-id="84c2e-455">**Optional**.</span></span> <span data-ttu-id="84c2e-456"> (如果在展台设备上已有非管理员帐户，请跳过此步骤。 ) 选择 " **运行时设置** &gt; **帐户** &gt; **用户**"，然后创建一个本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="84c2e-456">(If you already have a non-admin account on the kiosk device, skip this step.) Select **Runtime settings** &gt; **Accounts** &gt; **Users**, and then create a local user account.</span></span> <span data-ttu-id="84c2e-457">请确保用户名与你在配置 XML 中指定的帐户相同。</span><span class="sxs-lookup"><span data-stu-id="84c2e-457">Make sure that the user name is the same as for the account that you specify in the configuration XML.</span></span> <span data-ttu-id="84c2e-458">选择 " **UserGroup**  >  **标准用户**"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-458">Select **UserGroup** > **Standard Users**.</span></span>
1. <span data-ttu-id="84c2e-459">选择**File**"  >  **保存**文件"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-459">Select **File** > **Save**.</span></span>
1. <span data-ttu-id="84c2e-460">选择 "**导出**  >  **预配包**"，然后选择 "**所有者**  >  **IT 管理员**"。这会将此预配包的优先级设置为高于从其他源应用到此设备的预配包。</span><span class="sxs-lookup"><span data-stu-id="84c2e-460">Select **Export** > **Provisioning package**, and then select **Owner** > **IT Admin**. This sets the precedence of this provisioning package higher than provisioning packages that are applied to this device from other sources.</span></span>
1. <span data-ttu-id="84c2e-461">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="84c2e-461">Select **Next**.</span></span>
1. <span data-ttu-id="84c2e-462">在 " **预配程序包安全** " 页面上，选择一个安全选项。</span><span class="sxs-lookup"><span data-stu-id="84c2e-462">On the **Provisioning package security** page, select a security option.</span></span>
   > [!IMPORTANT]  
   > <span data-ttu-id="84c2e-463">如果选择 " **启用包签名**"，还必须选择用于对程序包进行签名的有效证书。</span><span class="sxs-lookup"><span data-stu-id="84c2e-463">If you select **Enable package signing**, you also have to select a valid certificate to use for signing the package.</span></span> <span data-ttu-id="84c2e-464">若要执行此操作，请选择 " **浏览** "，然后选择要用于对程序包进行签名的证书。</span><span class="sxs-lookup"><span data-stu-id="84c2e-464">To do this, select **Browse** and select the certificate that you want to use to sign the package.</span></span>
   
   > [!CAUTION]  
   > <span data-ttu-id="84c2e-465">不要选择 " **启用包加密**"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-465">Do not select **Enable package encryption**.</span></span> <span data-ttu-id="84c2e-466">在 HoloLens 设备上，此设置会导致预配失败。</span><span class="sxs-lookup"><span data-stu-id="84c2e-466">On HoloLens devices, this setting causes provisioning to fail.</span></span>
1. <span data-ttu-id="84c2e-467">选择**下一步** 。</span><span class="sxs-lookup"><span data-stu-id="84c2e-467">Select **Next**.</span></span>
1. <span data-ttu-id="84c2e-468">指定在构建预配包时希望该预配包转到的输出位置。</span><span class="sxs-lookup"><span data-stu-id="84c2e-468">Specify the output location where you want the provisioning package to go when it's built.</span></span> <span data-ttu-id="84c2e-469">默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。</span><span class="sxs-lookup"><span data-stu-id="84c2e-469">By default, Windows Configuration Designer uses the project folder as the output location.</span></span> <span data-ttu-id="84c2e-470">如果要更改输出位置，请选择 " **浏览**"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-470">If you want to change the output location, select **Browse**.</span></span> <span data-ttu-id="84c2e-471">完成后，选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-471">When you are finished, select **Next**.</span></span>
1. <span data-ttu-id="84c2e-472">选择 " **生成** " 开始构建程序包。</span><span class="sxs-lookup"><span data-stu-id="84c2e-472">Select **Build** to start building the package.</span></span> <span data-ttu-id="84c2e-473">无需花费太长时间即可生成预配包。</span><span class="sxs-lookup"><span data-stu-id="84c2e-473">The provisioning package doesn't take long to build.</span></span> <span data-ttu-id="84c2e-474">"生成" 页面显示项目信息，进度栏指示生成状态。</span><span class="sxs-lookup"><span data-stu-id="84c2e-474">The build page displays the project information, and the progress bar indicates the build status.</span></span>

### <a id="ppapply"></a><span data-ttu-id="84c2e-475">预配程序包，步骤 3 &ndash; 将预配包应用于 HoloLens</span><span class="sxs-lookup"><span data-stu-id="84c2e-475">Provisioning package, step 3 &ndash; Apply the provisioning package to HoloLens</span></span>

<span data-ttu-id="84c2e-476">"使用预配包配置 HoloLens" 一文提供了在以下情况下应用预配包的详细说明：</span><span class="sxs-lookup"><span data-stu-id="84c2e-476">The "Configure HoloLens by using a provisioning package" article provides detailed instructions to apply the provisioning package under the following circumstances:</span></span>

- <span data-ttu-id="84c2e-477">在安装期间，您最初可以 [将预配包应用于 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-477">You can initially [apply a provisioning package to HoloLens during setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup).</span></span>

- <span data-ttu-id="84c2e-478">您还可以 [在安装完成后将预配包应用于 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-478">You can also [apply a provisioning package to HoloLens after setup](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup).</span></span>

## <span data-ttu-id="84c2e-479">使用 Windows Device Portal 设置单应用展台</span><span class="sxs-lookup"><span data-stu-id="84c2e-479">Use the Windows Device Portal to set up a single-app kiosk</span></span>

<span data-ttu-id="84c2e-480">若要使用 Windows Device Portal 设置展台模式，请按照下列步骤操作。</span><span class="sxs-lookup"><span data-stu-id="84c2e-480">To set up kiosk mode by using the Windows Device Portal, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84c2e-481">展台模式仅在设备安装了 [Windows 全息版企业](hololens1-upgrade-enterprise.md) 版时可用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-481">Kiosk mode is available only if the device has [Windows Holographic for Business](hololens1-upgrade-enterprise.md) installed.</span></span>

1. <span data-ttu-id="84c2e-482">[将 HoloLens 设备设置为使用 Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-482">[Set up the HoloLens device to use the Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal).</span></span> <span data-ttu-id="84c2e-483">Device Portal 是 HoloLens 上的 Web 服务器，你可以从电脑上的 Web 浏览器连接到它。</span><span class="sxs-lookup"><span data-stu-id="84c2e-483">The Device Portal is a web server on your HoloLens that you can connect to from a web browser on your PC.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="84c2e-484">将 HoloLens 设置为使用 Device Portal 时，必须在设备上启用开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="84c2e-484">When you set up HoloLens to use the Device Portal, you have to enable Developer Mode on the device.</span></span> <span data-ttu-id="84c2e-485">具有 Windows 全息版企业版的设备上的开发人员模式使你能够使用面加载应用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-485">Developer Mode on a device that has Windows Holographic for Business enables you to side-load apps.</span></span> <span data-ttu-id="84c2e-486">但是，此设置会创建一个风险，用户可以安装 Microsoft Store 尚未认证的应用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-486">However, this setting creates a risk that a user can install apps that have not been certified by the Microsoft Store.</span></span> <span data-ttu-id="84c2e-487">管理员可以通过使用[策略 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)中的**ApplicationManagement/AllowDeveloper 解锁**设置阻止启用开发人员模式的功能。</span><span class="sxs-lookup"><span data-stu-id="84c2e-487">Administrators can block the ability to enable Developer Mode by using the **ApplicationManagement/AllowDeveloper Unlock** setting in the [Policy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider).</span></span> [<span data-ttu-id="84c2e-488">了解有关开发人员模式的详细信息。</span><span class="sxs-lookup"><span data-stu-id="84c2e-488">Learn more about Developer Mode.</span></span>](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. <span data-ttu-id="84c2e-489">在计算机上，使用 [wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 或 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="84c2e-489">On a computer, connect to the HoloLens by using [Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) or [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb).</span></span>

1. <span data-ttu-id="84c2e-490">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="84c2e-490">Do one of the following:</span></span>
   - <span data-ttu-id="84c2e-491">如果您是首次连接到 Windows Device Portal，请 [创建用户名和密码](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span><span class="sxs-lookup"><span data-stu-id="84c2e-491">If you are connecting to the Windows Device Portal for the first time, [create a user name and password](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)</span></span>
   - <span data-ttu-id="84c2e-492">输入您以前设置的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="84c2e-492">Enter the user name and password that you previously set up.</span></span>

    > [!TIP]
    > <span data-ttu-id="84c2e-493">如果发现浏览器中的证书错误，请遵循[以下疑难解答步骤](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)。</span><span class="sxs-lookup"><span data-stu-id="84c2e-493">If you see a certificate error in the browser, follow [these troubleshooting steps](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate).</span></span>

1. <span data-ttu-id="84c2e-494">在 Windows Device Portal 中，选择 " **展台模式**"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-494">In the Windows Device Portal, select **Kiosk Mode**.</span></span>

1. <span data-ttu-id="84c2e-495">选择 " **启用展台模式**"，选择要在设备启动时运行的应用，然后选择 " **保存**"。</span><span class="sxs-lookup"><span data-stu-id="84c2e-495">Select **Enable Kiosk Mode**, select an app to run when the device starts, and then select **Save**.</span></span>

    ![展台模式](images/kiosk.png)
1. <span data-ttu-id="84c2e-497">重新启动 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="84c2e-497">Restart HoloLens.</span></span> <span data-ttu-id="84c2e-498">如果您的设备门户页面仍处于打开状态，则可以在页面顶部选择 " **重新启动** "。</span><span class="sxs-lookup"><span data-stu-id="84c2e-498">If you still have your Device Portal page open, you can select **Restart** at the top of the page.</span></span>

> [!NOTE]
> <span data-ttu-id="84c2e-499">可以通过设备门户的 REST API 设置展台模式，方法是使用一个必需的查询字符串参数 ( "kioskModeEnabled"，使用值为 "true" 或 "false" ) ，使用一个可选参数 ( "startupApp"，并使用包名称) 的值来设置/api/holographic/kioskmode/settings。</span><span class="sxs-lookup"><span data-stu-id="84c2e-499">Kiosk Mode can be set via Device Portal’s REST API by doing a POST to /api/holographic/kioskmode/settings with one required query string parameter (“kioskModeEnabled” with a value of “true” or “false”) and one optional parameter (“startupApp” with a value of a package name).</span></span> <span data-ttu-id="84c2e-500">请记住，Device Portal 仅面向开发人员，不应在非开发人员设备上启用。</span><span class="sxs-lookup"><span data-stu-id="84c2e-500">Please keep in mind that Device Portal is intended for developers only and should not be enabled on non-developer devices.</span></span> <span data-ttu-id="84c2e-501">REST API 可能会在将来的更新/发布中更改。</span><span class="sxs-lookup"><span data-stu-id="84c2e-501">The REST API is subject to change in future updates/releases.</span></span>

## <span data-ttu-id="84c2e-502">详细信息</span><span class="sxs-lookup"><span data-stu-id="84c2e-502">More information</span></span>

<span data-ttu-id="84c2e-503">观看如何使用预配包配置展台。</span><span class="sxs-lookup"><span data-stu-id="84c2e-503">Watch how to configure a kiosk by using a provisioning package.</span></span>  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]
