---
title: 管理 HoloLens 更新
description: 管理员可以使用移动设备管理来管理 HoloLens 设备更新。
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 07/09/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 384d33e72effd298e1874e5723e9c418061c3287
ms.sourcegitcommit: 0d4e67d8e21d34885e0eaee08646e28426c4f641
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2020
ms.locfileid: "10861905"
---
# <span data-ttu-id="6ed86-103">管理 HoloLens 更新</span><span class="sxs-lookup"><span data-stu-id="6ed86-103">Manage HoloLens updates</span></span>

<span data-ttu-id="6ed86-104">HoloLens 使用 Windows 更新的方式与其他 Windows 10 设备相同。</span><span class="sxs-lookup"><span data-stu-id="6ed86-104">HoloLens uses Windows Update in the same manner as other Windows 10 devices.</span></span> <span data-ttu-id="6ed86-105">当有可用更新时，下次设备接通电源并连接到网络时，会自动下载并安装。</span><span class="sxs-lookup"><span data-stu-id="6ed86-105">When an update is available, it is automatically downloaded and installed the next time that your device is plugged in and connected to the internet.</span></span> <span data-ttu-id="6ed86-106">本文介绍如何在企业或其他托管环境中管理 HoloLens 更新。</span><span class="sxs-lookup"><span data-stu-id="6ed86-106">This article describes how to manage updates in an enterprise or other managed environment.</span></span> <span data-ttu-id="6ed86-107">有关如何管理单个 HoloLens 设备更新的信息，请参阅[更新 HoloLens](hololens-update-hololens.md)。</span><span class="sxs-lookup"><span data-stu-id="6ed86-107">For information about how to manage updates to individual HoloLens devices, see [Update HoloLens](hololens-update-hololens.md).</span></span>

## <span data-ttu-id="6ed86-108">自动管理更新</span><span class="sxs-lookup"><span data-stu-id="6ed86-108">Manage updates automatically</span></span>

### <span data-ttu-id="6ed86-109">使用适用于企业的 Windows 更新管理更新</span><span class="sxs-lookup"><span data-stu-id="6ed86-109">Managing updates by using Windows Update for Business</span></span>

<span data-ttu-id="6ed86-110">Windows Holographic for Business 可使用[适用于企业的 Windows 更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)管理更新。</span><span class="sxs-lookup"><span data-stu-id="6ed86-110">Windows Holographic for Business can use [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) to manage updates.</span></span> <span data-ttu-id="6ed86-111">所有 HoloLens 2 设备均可使用 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="6ed86-111">All HoloLens 2 devices can use Windows Holographic for Business.</span></span> <span data-ttu-id="6ed86-112">确保你的 HoloLens 2 设备使用 Windows Holographic for Business 10.0.18362.1042 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="6ed86-112">Make sure that they use Windows Holographic for Business build 10.0.18362.1042 or a later build.</span></span> <span data-ttu-id="6ed86-113">如果使用的是 HoloLens（第一代）设备，必须[将它们升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 以管理更新。</span><span class="sxs-lookup"><span data-stu-id="6ed86-113">If you have HoloLens (1st gen) devices, you have to [upgrade them to Windows Holographic for Business](hololens1-upgrade-enterprise.md) in order to manage their updates.</span></span>

<span data-ttu-id="6ed86-114">适用于企业的 Windows 更新将 HoloLens 设备直接连接到 Windows 更新服务。</span><span class="sxs-lookup"><span data-stu-id="6ed86-114">Windows Update for Business connects HoloLens devices directly to the Windows Update service.</span></span> <span data-ttu-id="6ed86-115">通过使用适用于企业的 Windows 更新，你可以控制更新过程的多个方面&mdash;：具体而言，哪些设备将在什么时候获取哪些更新。</span><span class="sxs-lookup"><span data-stu-id="6ed86-115">By using Windows Update for Business, you can control multiple aspects of the update process&mdash;that is, which devices get which updates at what time.</span></span> <span data-ttu-id="6ed86-116">例如，可先将更新部署到设备的某个子集进行测试，随后再对剩余的设备进行更新。</span><span class="sxs-lookup"><span data-stu-id="6ed86-116">For example, you can roll out updates to a subset of devices for testing, then later roll out updates to the remaining devices.</span></span> <span data-ttu-id="6ed86-117">或是为不同类型的更新制定不同的更新计划。</span><span class="sxs-lookup"><span data-stu-id="6ed86-117">Or, you can define different update schedules for different types of updates.</span></span>

> [!NOTE]  
> <span data-ttu-id="6ed86-118">可以自动管理 HoloLens 设备的功能更新（每年发布两次）和质量更新（每月发布或根据需要发布，包括关键安全更新）。</span><span class="sxs-lookup"><span data-stu-id="6ed86-118">For HoloLens devices, you can automatically manage feature updates (released two times a year) and quality updates (released monthly or as required, including critical security updates).</span></span> <span data-ttu-id="6ed86-119">有关更新类型的更多信息，请参阅[适用于企业的 Windows 更新托管的更新类型](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)。</span><span class="sxs-lookup"><span data-stu-id="6ed86-119">For more information about update types, see [Types of updates managed by Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).</span></span>

<span data-ttu-id="6ed86-120">可以使用移动设备管理 (MDM) 解决方案中的 Microsoft Intune 等策略为 HoloLens 配置适用于企业的 Windows 更新设置。</span><span class="sxs-lookup"><span data-stu-id="6ed86-120">You can configure Windows Update for Business settings for HoloLens by using policies in a Mobile Device Management (MDM) solution such as Microsoft Intune.</span></span>

### <span data-ttu-id="6ed86-121">使用 Microsoft Intune 管理适用于企业的 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="6ed86-121">Managing Windows Update for Business by using Microsoft Intune</span></span>

<span data-ttu-id="6ed86-122">如需详细了解如何使用 Intune 配置适用于企业的 Windows 更新，请参阅[在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="6ed86-122">For a detailed discussion about how to use Intune to configure Windows Update for Business, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="6ed86-123">有关 HoloLens 支持的特定 Intune 功能的信息，参见“[HoloLens 支持的 Intune 更新管理功能](#intune-update-management-functions-that-hololens-supports)”。</span><span class="sxs-lookup"><span data-stu-id="6ed86-123">For more information about the specific Intune functionality that HoloLens supports, see [Intune update management functions that HoloLens supports](#intune-update-management-functions-that-hololens-supports).</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="6ed86-124">Intune 提供两种更新管理策略，分别是：*Windows 10 更新通道*和 *Windows 10 功能更新*。</span><span class="sxs-lookup"><span data-stu-id="6ed86-124">Intune provides two policy types for managing updates: *Windows 10 update ring* and *Windows 10 feature update*.</span></span> <span data-ttu-id="6ed86-125">Windows 10 功能更新策略目前尚处于公共预览版阶段，暂不支持 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6ed86-125">The Windows 10 feature update policy type is in public preview at this time and is not supported for HoloLens.</span></span>
>  
> <span data-ttu-id="6ed86-126">你可以使用 Windows 10 更新通道策略管理 HoloLens 2 更新。</span><span class="sxs-lookup"><span data-stu-id="6ed86-126">You can use Windows 10 update ring policies to manage HoloLens 2 updates.</span></span>

### <span data-ttu-id="6ed86-127">配置 HoloLens 2 或 HoloLens（第一代）更新策略</span><span class="sxs-lookup"><span data-stu-id="6ed86-127">Configure update policies for HoloLens 2 or HoloLens (1st gen)</span></span>

<span data-ttu-id="6ed86-128">本节介绍用于管理 HoloLens 2 或 HoloLens（第一代）更新的策略。</span><span class="sxs-lookup"><span data-stu-id="6ed86-128">This section describes the policies that you can use to manage updates for either HoloLens 2 or HoloLens (1st gen).</span></span> <span data-ttu-id="6ed86-129">有关 HoloLens 2 可用功能的更多信息，请参阅[规划和配置 HoloLens 2 更新推出](#plan-and-configure-update-rollouts-for-hololens-2)。</span><span class="sxs-lookup"><span data-stu-id="6ed86-129">For more information about the functionality that is available for HoloLens 2, see [Plan and configure update rollouts for HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).</span></span>

<span data-ttu-id="6ed86-130">[策略 CSP - 更新](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) 制定配置适用于企业的 Windows 更新的策略。</span><span class="sxs-lookup"><span data-stu-id="6ed86-130">[Policy CSP - Update](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) defines the policies that configure Windows Update for Business.</span></span>

> [!NOTE]  
> <span data-ttu-id="6ed86-131">有关特定版本的 HoloLens 支持的特定策略配置服务提供程序（CSP）的列表，请参阅 [HoloLens 设备支持的策略 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)。</span><span class="sxs-lookup"><span data-stu-id="6ed86-131">For a list of specific policy configuration service providers (CSPs) that are supported by specific editions of HoloLens, see [Policy CSPs supported by HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).</span></span>

#### <span data-ttu-id="6ed86-132">配置自动检查更新</span><span class="sxs-lookup"><span data-stu-id="6ed86-132">Configure automatic checks for updates</span></span>

<span data-ttu-id="6ed86-133">可以使用 **Update/AllowAutoUpdate** 策略自动管理扫描、下载和安装更新等更新行为。</span><span class="sxs-lookup"><span data-stu-id="6ed86-133">You can use the **Update/AllowAutoUpdate** policy to manage automatic update behavior, such as scanning, downloading, and installing updates.</span></span> <span data-ttu-id="6ed86-134">如需详细了解该策略的可用设置，请参阅 [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)。</span><span class="sxs-lookup"><span data-stu-id="6ed86-134">For more information about the available settings for this policy, see [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).</span></span>

> [!NOTE]  
> <span data-ttu-id="6ed86-135">在 Microsoft Intune 中，你可以使用**自动更新行为**更改该策略。</span><span class="sxs-lookup"><span data-stu-id="6ed86-135">In Microsoft Intune, you can use **Automatic Update Behavior** to change this policy.</span></span> <span data-ttu-id="6ed86-136">有关详细信息，请参阅[在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/intune/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="6ed86-136">For more information, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

#### <span data-ttu-id="6ed86-137">配置更新计划</span><span class="sxs-lookup"><span data-stu-id="6ed86-137">Configure an update schedule</span></span>

<span data-ttu-id="6ed86-138">要配置应用更新的方式和时间，请使用以下策略：</span><span class="sxs-lookup"><span data-stu-id="6ed86-138">To configure how and when updates are applied, use the following policies:</span></span>

- [<span data-ttu-id="6ed86-139">Update/ScheduledInstallDay</span><span class="sxs-lookup"><span data-stu-id="6ed86-139">Update/ScheduledInstallDay</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - <span data-ttu-id="6ed86-140">值的范围：**0**–**7**（其中 0 代表每天，1 代表周日，7 代表周六）</span><span class="sxs-lookup"><span data-stu-id="6ed86-140">Values: **0**–**7** (0 = every day, 1 = Sunday, 7 = Saturday)</span></span>
  - <span data-ttu-id="6ed86-141">默认值：**0**（每天）</span><span class="sxs-lookup"><span data-stu-id="6ed86-141">Default value: **0** (every day)</span></span>
- [<span data-ttu-id="6ed86-142">Update/ScheduledInstallTime</span><span class="sxs-lookup"><span data-stu-id="6ed86-142">Update/ScheduledInstallTime</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - <span data-ttu-id="6ed86-143">值的范围：0-23（其中 0 代表午夜，23 代表晚上 11 点）</span><span class="sxs-lookup"><span data-stu-id="6ed86-143">Values: 0–23 (0 = midnight, 23 = 11 PM)</span></span>
  - <span data-ttu-id="6ed86-144">默认值：下午 3 点</span><span class="sxs-lookup"><span data-stu-id="6ed86-144">Default value: 3 PM</span></span>

#### <span data-ttu-id="6ed86-145">只针对运行 Windows 10 1607 版本的设备</span><span class="sxs-lookup"><span data-stu-id="6ed86-145">For devices that run Windows 10, version 1607 only</span></span>

<span data-ttu-id="6ed86-146">可以使用以下更新策略配置设备从 Windows Server Update Services (WSUS) 而非 从 Windows 更新获取更新：</span><span class="sxs-lookup"><span data-stu-id="6ed86-146">You can use the following update policies to configure devices to get updates from Windows Server Update Service (WSUS), instead of from Windows Update:</span></span>

- [<span data-ttu-id="6ed86-147">Update/AllowUpdateService</span><span class="sxs-lookup"><span data-stu-id="6ed86-147">Update/AllowUpdateService</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [<span data-ttu-id="6ed86-148">Update/RequireUpdateApproval</span><span class="sxs-lookup"><span data-stu-id="6ed86-148">Update/RequireUpdateApproval</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [<span data-ttu-id="6ed86-149">Update/UpdateServiceUrl</span><span class="sxs-lookup"><span data-stu-id="6ed86-149">Update/UpdateServiceUrl</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <span data-ttu-id="6ed86-150">规划和配置 HoloLens 2 更新推出</span><span class="sxs-lookup"><span data-stu-id="6ed86-150">Plan and configure update rollouts for HoloLens 2</span></span>

<span data-ttu-id="6ed86-151">相比 HoloLens（第一代），HoloLens 2 支持更多自动化更新功能。</span><span class="sxs-lookup"><span data-stu-id="6ed86-151">HoloLens 2 supports more update automation features than HoloLens (1st gen) does.</span></span> <span data-ttu-id="6ed86-152">如果你使用 Microsoft Intune 来管理适用于企业的 Windows 更新策略，尤其如此。</span><span class="sxs-lookup"><span data-stu-id="6ed86-152">This is especially true if you use Microsoft Intune to manage Windows Update for Business policies.</span></span> <span data-ttu-id="6ed86-153">借助这些功能，可更轻松地规划和部署整个组织的更新。</span><span class="sxs-lookup"><span data-stu-id="6ed86-153">These features make it easier for you to plan and implement update rollouts across your organization.</span></span>

#### <span data-ttu-id="6ed86-154">规划更新策略</span><span class="sxs-lookup"><span data-stu-id="6ed86-154">Plan the update strategy</span></span>

<span data-ttu-id="6ed86-155">适用于企业的 Windows 更新支持延期策略。</span><span class="sxs-lookup"><span data-stu-id="6ed86-155">Windows Updates for Business supports deferral policies.</span></span> <span data-ttu-id="6ed86-156">Microsoft 发布更新后，你可以使用延期策略定义在设备上等待多久后安装该更新。</span><span class="sxs-lookup"><span data-stu-id="6ed86-156">After Microsoft releases an update, you can use a deferral policy to define how long to wait before installing that update on devices.</span></span> <span data-ttu-id="6ed86-157">通过将设备子集（即“*更新通道*”）与不同的延期策略相关联，可协调组织的更新推出策略。</span><span class="sxs-lookup"><span data-stu-id="6ed86-157">By associating subsets of your devices (also known as *update rings*) with different deferral policies, you can coordinate an update rollout strategy for your organization.</span></span>

<span data-ttu-id="6ed86-158">例如，假设某个组织拥有 1,000 台设备，并且必须通过 5 种方式更新设备。</span><span class="sxs-lookup"><span data-stu-id="6ed86-158">For example, consider an organization that has 1,000 devices, and has to update the devices in five waves.</span></span> <span data-ttu-id="6ed86-159">该组织可按下表所示，创建 5 个更新通道。</span><span class="sxs-lookup"><span data-stu-id="6ed86-159">The organization can create five update rings, as shown in the following table.</span></span>

|<span data-ttu-id="6ed86-160">组</span><span class="sxs-lookup"><span data-stu-id="6ed86-160">Group</span></span> |<span data-ttu-id="6ed86-161">设备数量</span><span class="sxs-lookup"><span data-stu-id="6ed86-161">Number of devices</span></span> |<span data-ttu-id="6ed86-162">延期（天数）</span><span class="sxs-lookup"><span data-stu-id="6ed86-162">Deferral (days)</span></span> |
| ---| :---: | :---: |
|<span data-ttu-id="6ed86-163">组 1（IT 人员）</span><span class="sxs-lookup"><span data-stu-id="6ed86-163">Grp 1 (IT staff)</span></span> |<span data-ttu-id="6ed86-164">5</span><span class="sxs-lookup"><span data-stu-id="6ed86-164">5</span></span> |<span data-ttu-id="6ed86-165">0</span><span class="sxs-lookup"><span data-stu-id="6ed86-165">0</span></span> |
|<span data-ttu-id="6ed86-166">组 2（早期采用者）</span><span class="sxs-lookup"><span data-stu-id="6ed86-166">Grp 2 (early adopters)</span></span> |<span data-ttu-id="6ed86-167">50</span><span class="sxs-lookup"><span data-stu-id="6ed86-167">50</span></span> |<span data-ttu-id="6ed86-168">60</span><span class="sxs-lookup"><span data-stu-id="6ed86-168">60</span></span> |
|<span data-ttu-id="6ed86-169">组 3（主要设备 1）</span><span class="sxs-lookup"><span data-stu-id="6ed86-169">Grp 3 (main 1)</span></span> |<span data-ttu-id="6ed86-170">250</span><span class="sxs-lookup"><span data-stu-id="6ed86-170">250</span></span> |<span data-ttu-id="6ed86-171">120</span><span class="sxs-lookup"><span data-stu-id="6ed86-171">120</span></span> |
|<span data-ttu-id="6ed86-172">组 4（主要设备 2）</span><span class="sxs-lookup"><span data-stu-id="6ed86-172">Grp 4 (main 2)</span></span> |<span data-ttu-id="6ed86-173">300</span><span class="sxs-lookup"><span data-stu-id="6ed86-173">300</span></span> |<span data-ttu-id="6ed86-174">150</span><span class="sxs-lookup"><span data-stu-id="6ed86-174">150</span></span> |
|<span data-ttu-id="6ed86-175">组 5（主要设备 3）</span><span class="sxs-lookup"><span data-stu-id="6ed86-175">Grp 5 (main 3)</span></span> |<span data-ttu-id="6ed86-176">395</span><span class="sxs-lookup"><span data-stu-id="6ed86-176">395</span></span> |<span data-ttu-id="6ed86-177">180</span><span class="sxs-lookup"><span data-stu-id="6ed86-177">180</span></span> |

<span data-ttu-id="6ed86-178">随着时间推移，整个组织将按照此过程推出更新。</span><span class="sxs-lookup"><span data-stu-id="6ed86-178">Here's how the rollout progresses over time to the whole organization.</span></span>

![更新部署日程表](./images/hololens-updates-timeline.png)

#### <span data-ttu-id="6ed86-180">配置更新延期策略</span><span class="sxs-lookup"><span data-stu-id="6ed86-180">Configure an update deferral policy</span></span>

<span data-ttu-id="6ed86-181">延期策略指定可用更新日期和向设备提供更新日期之间间隔的天数。</span><span class="sxs-lookup"><span data-stu-id="6ed86-181">A deferral policy specifies the number of days between the date on which an update becomes available and the date on which the update is offered to a device.</span></span>

<span data-ttu-id="6ed86-182">可为功能更新和质量更新配置不同的延期天数。</span><span class="sxs-lookup"><span data-stu-id="6ed86-182">You can configure different deferrals for feature updates and quality updates.</span></span> <span data-ttu-id="6ed86-183">下表列出了每种类型要使用的具体策略及每个类型最多可以延期的天数。</span><span class="sxs-lookup"><span data-stu-id="6ed86-183">The following table lists the specific policies to use for each type, and the maximum deferral for each.</span></span>

|<span data-ttu-id="6ed86-184">类别</span><span class="sxs-lookup"><span data-stu-id="6ed86-184">Category</span></span> |<span data-ttu-id="6ed86-185">策略</span><span class="sxs-lookup"><span data-stu-id="6ed86-185">Policy</span></span> |<span data-ttu-id="6ed86-186">最大延迟</span><span class="sxs-lookup"><span data-stu-id="6ed86-186">Maximum deferral</span></span> |
| --- | --- | --- |
|<span data-ttu-id="6ed86-187">功能更新</span><span class="sxs-lookup"><span data-stu-id="6ed86-187">Feature updates</span></span> |<span data-ttu-id="6ed86-188">DeferFeatureUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="6ed86-188">DeferFeatureUpdatesPeriodInDays</span></span> |<span data-ttu-id="6ed86-189">365 天</span><span class="sxs-lookup"><span data-stu-id="6ed86-189">365 days</span></span> |
|<span data-ttu-id="6ed86-190">质量更新</span><span class="sxs-lookup"><span data-stu-id="6ed86-190">Quality updates</span></span> |<span data-ttu-id="6ed86-191">DeferQualityUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="6ed86-191">DeferQualityUpdatesPeriodInDays</span></span> |<span data-ttu-id="6ed86-192">30 天</span><span class="sxs-lookup"><span data-stu-id="6ed86-192">30 days</span></span> |

#### <span data-ttu-id="6ed86-193">HoloLens 支持的 Intune 更新管理功能</span><span class="sxs-lookup"><span data-stu-id="6ed86-193">Intune update management functions that HoloLens supports</span></span>

<span data-ttu-id="6ed86-194">可使用下列 Intune 更新管理功能来管理 HoloLens 更新。</span><span class="sxs-lookup"><span data-stu-id="6ed86-194">You can use the following Intune update management functions to manage updates for HoloLens.</span></span>

- <span data-ttu-id="6ed86-195">**创建**和**分配**：这些功能将 Windows 10 更新通道添加到更新通道列表中。</span><span class="sxs-lookup"><span data-stu-id="6ed86-195">**Create** and **Assign**: These functions add a Windows 10 update ring to the list of update rings.</span></span> <span data-ttu-id="6ed86-196">有关详细信息，请参阅[创建和分配更新通道](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)。</span><span class="sxs-lookup"><span data-stu-id="6ed86-196">For more information, see [Create and assign update rings](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).</span></span>

- <span data-ttu-id="6ed86-197">**暂停**：如果部署功能或质量更新时遇到问题，可暂停更新 35 天（从指定日期开始计算）。</span><span class="sxs-lookup"><span data-stu-id="6ed86-197">**Pause**: If you encounter a problem when you deploy a feature or quality update, you can pause the update for 35 days (starting from a specified date).</span></span> <span data-ttu-id="6ed86-198">暂停后会阻止其他设备安装更新，直至你解决或缓解该问题。</span><span class="sxs-lookup"><span data-stu-id="6ed86-198">This pause prevents other devices from installing the update until you resolve or mitigate the problem.</span></span> <span data-ttu-id="6ed86-199">即使暂停功能更新，仍会向设备提供质量更新以确保它们保持安全。</span><span class="sxs-lookup"><span data-stu-id="6ed86-199">If you pause a feature update, quality updates are still offered to devices to make sure that they stay secure.</span></span> <span data-ttu-id="6ed86-200">暂停更新类型后，相应通道的“概述”窗格会显示更新类型恢复前剩余的天数。</span><span class="sxs-lookup"><span data-stu-id="6ed86-200">When an update type is paused, the Overview pane for that ring displays how many days remain before that update type resumes.</span></span> <span data-ttu-id="6ed86-201">指定时间过后，暂停将自动过期，并继续更新进程。</span><span class="sxs-lookup"><span data-stu-id="6ed86-201">After the specified time has passed, the pause automatically expires, and the update process resumes.</span></span>

  <span data-ttu-id="6ed86-202">暂停更新通道时，可选择以下任一选项：</span><span class="sxs-lookup"><span data-stu-id="6ed86-202">While the update ring is paused, you can select either of the following options:</span></span>

  - <span data-ttu-id="6ed86-203">**延长**：延长更新类型暂停期限 35 天。</span><span class="sxs-lookup"><span data-stu-id="6ed86-203">**Extend**: Extend the pause period for an update type for 35 days.</span></span>
  - <span data-ttu-id="6ed86-204">**恢复**：将该通道的更新还原为活动操作</span><span class="sxs-lookup"><span data-stu-id="6ed86-204">**Resume**: Restore updates for that ring to active operation.</span></span> <span data-ttu-id="6ed86-205">如果有必要，可以再次暂停更新通道。</span><span class="sxs-lookup"><span data-stu-id="6ed86-205">You can pause the update ring again, if it is necessary.</span></span>

  > [!NOTE]  
  > <span data-ttu-id="6ed86-206">HoloLens 2 设备不支持更新通道的“**卸载**”操作。</span><span class="sxs-lookup"><span data-stu-id="6ed86-206">The **Uninstall** operation for update rings is not supported for HoloLens 2 devices.</span></span>

## <span data-ttu-id="6ed86-207">手动检查更新</span><span class="sxs-lookup"><span data-stu-id="6ed86-207">Manually check for updates</span></span>

<span data-ttu-id="6ed86-208">虽然 HoloLens 会定期检查系统更新，但在某些情况下，仍可能需要手动检查。</span><span class="sxs-lookup"><span data-stu-id="6ed86-208">Although HoloLens periodically checks for system updates, there may be circumstances in which you want to manually check.</span></span>

<span data-ttu-id="6ed86-209">若要手动检查更新，请转到“**设置**” > “**更新和安全**” > “**检查更新**”。</span><span class="sxs-lookup"><span data-stu-id="6ed86-209">To manually check for updates, go to **Settings** > **Update & Security** > **Check for updates**.</span></span> <span data-ttu-id="6ed86-210">如果“设置”应用指示你的设备已是最新版本，则表示你已安装所有可用更新。</span><span class="sxs-lookup"><span data-stu-id="6ed86-210">If the Settings app indicates that your device is up to date, you have all the updates that are currently available.</span></span>

## <span data-ttu-id="6ed86-211">后动回滚更新</span><span class="sxs-lookup"><span data-stu-id="6ed86-211">Manually roll back an update</span></span>

<span data-ttu-id="6ed86-212">在某些情况下，你可能想要还原到 HoloLens 软件的早期版本。</span><span class="sxs-lookup"><span data-stu-id="6ed86-212">In some cases, you might want to revert to a previous version of the HoloLens software.</span></span> <span data-ttu-id="6ed86-213">视您使用的是 HoloLens 2 还是 HoloLens（第一代），请选择以下对应的操作流程。</span><span class="sxs-lookup"><span data-stu-id="6ed86-213">The process for doing this depends on whether you are using HoloLens 2 or HoloLens (1st gen).</span></span>

### <span data-ttu-id="6ed86-214">还原到早期版本 (HoloLens 2)</span><span class="sxs-lookup"><span data-stu-id="6ed86-214">Revert to a previous version (HoloLens 2)</span></span>

<span data-ttu-id="6ed86-215">可使用“[高级恢复助手](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)”将 HoloLens 重置为早期版本，以实现回滚并返回到 HoloLens 2 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="6ed86-215">You can roll back updates and return to a previous version of HoloLens 2 by using the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="6ed86-216">还原到早期版本会删除你的个人文件和设置。</span><span class="sxs-lookup"><span data-stu-id="6ed86-216">Reverting to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="6ed86-217">若要还原到 HoloLens 2 的早期版本，请按照如下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="6ed86-217">To revert to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="6ed86-218">请确保你没有任何手机或 Windows 设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="6ed86-218">Make sure that you don't have any phones or Windows devices plugged in to your computer.</span></span>
1. <span data-ttu-id="6ed86-219">在你的电脑上，从 Microsoft 应用商店下载[高级恢复助手](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)。</span><span class="sxs-lookup"><span data-stu-id="6ed86-219">On your computer, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="6ed86-220">下载[最新版本的 HoloLens 2](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="6ed86-220">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="6ed86-221">完成这些下载后，打开“**文件资源管理器**” > “**下载**”，右键单击刚才下载的 zip 压缩文件夹，然后选择“**提取全部**” > “**提取**”以展开该文件。</span><span class="sxs-lookup"><span data-stu-id="6ed86-221">After these downloads finish, open **File explorer** > **Downloads**, right-click the compressed (.zip) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="6ed86-222">使用 USB-A 到 USB-C 数据线将 HoloLens 设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="6ed86-222">Use a USB-A to USB-C cable to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="6ed86-223">即使你在连接 HoloLens 时一直使用的是其他数据线，但此数据线的使用效果更好。</span><span class="sxs-lookup"><span data-stu-id="6ed86-223">Even if you've been using other cables to connect your HoloLens, this kind of cable works best.</span></span>
1. <span data-ttu-id="6ed86-224">“高级恢复助手”会自动检测到 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="6ed86-224">The Advanced Recovery Companion automatically detects your HoloLens device.</span></span> <span data-ttu-id="6ed86-225">选择“**Microsoft HoloLens**”磁贴。</span><span class="sxs-lookup"><span data-stu-id="6ed86-225">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="6ed86-226">在下一个屏幕中，选择“**手动选择包**”，然后打开先前展开的文件夹。</span><span class="sxs-lookup"><span data-stu-id="6ed86-226">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span>
1. <span data-ttu-id="6ed86-227">选择安装 (.ffu) 文件。</span><span class="sxs-lookup"><span data-stu-id="6ed86-227">Select the installation (.ffu) file.</span></span>
1. <span data-ttu-id="6ed86-228">选择**安装软件**，然后按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="6ed86-228">Select **Install software**, and then follow the instructions.</span></span>

### <span data-ttu-id="6ed86-229">HoloLens（第一代）如何还原到早期版本</span><span class="sxs-lookup"><span data-stu-id="6ed86-229">Revert to a previous version (HoloLens (1st gen))</span></span>

<span data-ttu-id="6ed86-230">可使用 “[Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)” 将 HoloLens 重置为早期版本，以实现回滚并返回到 HoloLens（第一代）的早期版本。</span><span class="sxs-lookup"><span data-stu-id="6ed86-230">You can roll back updates and return to a previous version of HoloLens (1st gen) by using the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="6ed86-231">还原到 HoloLens 早期版本会删除你的个人文件和设置。</span><span class="sxs-lookup"><span data-stu-id="6ed86-231">Reverting to an earlier HoloLens version deletes your personal files and settings.</span></span>

<span data-ttu-id="6ed86-232">要还原到 HoloLens（第一代）的早期版本，请按照如下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="6ed86-232">To revert to a previous version of HoloLens (1st gen), follow these steps:</span></span>

1. <span data-ttu-id="6ed86-233">请确保你没有任何手机或 Windows 设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="6ed86-233">Make sure that you don't have any phones or Windows devices plugged into your computer.</span></span>
1. <span data-ttu-id="6ed86-234">在你的电脑上，下载并安装 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)。</span><span class="sxs-lookup"><span data-stu-id="6ed86-234">On your computer, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="6ed86-235">下载 [HoloLens 周年更新恢复包](https://aka.ms/hololensrecovery)。</span><span class="sxs-lookup"><span data-stu-id="6ed86-235">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="6ed86-236">完成下载后，打开“**文件资源管理器**” > “**下载**”，右键单击刚才下载的 .zip 压缩文件夹，然后选择“**提取全部**” > “**提取**”以展开该文件。</span><span class="sxs-lookup"><span data-stu-id="6ed86-236">After the downloads finish, open **File explorer** > **Downloads**, right-click the compressed (.zip) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="6ed86-237">使用与 HoloLens 设备随附的 micro-USB 数据线将 HoloLens 设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="6ed86-237">Use the micro-USB cable that was provided together with your HoloLens device to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="6ed86-238">即使你在连接 HoloLens 时一直使用的是其他数据线，但原厂数据线的使用效果更好。</span><span class="sxs-lookup"><span data-stu-id="6ed86-238">Even if you've been using other cables to connect your HoloLens device, this one works best.</span></span>
1. <span data-ttu-id="6ed86-239">Windows Device Recovery Tool 会自动检测到 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="6ed86-239">The WDRT automatically detects your HoloLens device.</span></span> <span data-ttu-id="6ed86-240">选择“**Microsoft HoloLens**”磁贴。</span><span class="sxs-lookup"><span data-stu-id="6ed86-240">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="6ed86-241">在下一个屏幕中，选择“**手动选择包**”，然后打开先前展开的文件夹。</span><span class="sxs-lookup"><span data-stu-id="6ed86-241">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span>
1. <span data-ttu-id="6ed86-242">选择安装 (.ffu) 文件。</span><span class="sxs-lookup"><span data-stu-id="6ed86-242">Select the installation (.ffu) file.</span></span>
1. <span data-ttu-id="6ed86-243">选择**安装软件**，然后按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="6ed86-243">Select **Install software**, and then follow the instructions.</span></span>

**<span data-ttu-id="6ed86-244">如果 WDRT 未检测到你的设备</span><span class="sxs-lookup"><span data-stu-id="6ed86-244">If WDRT doesn't detect your device</span></span>**

<span data-ttu-id="6ed86-245">如果 Windows Device Recovery Tool 未检测到 HoloLens 设备，请尝试重启电脑。</span><span class="sxs-lookup"><span data-stu-id="6ed86-245">If WDRT doesn't detect your HoloLens device, try restarting your computer.</span></span> <span data-ttu-id="6ed86-246">如果重启不起作用，请选择“**未检测到我的设备**”，选择“**Microsoft HoloLens**”，然后按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="6ed86-246">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="6ed86-247">相关文章</span><span class="sxs-lookup"><span data-stu-id="6ed86-247">Related articles</span></span>

- [<span data-ttu-id="6ed86-248">HoloLens 2 发行说明</span><span class="sxs-lookup"><span data-stu-id="6ed86-248">HoloLens 2 release notes</span></span>](https://docs.microsoft.com/hololens/hololens-release-notes)
- [<span data-ttu-id="6ed86-249">什么是适用于企业的 Windows 更新？</span><span class="sxs-lookup"><span data-stu-id="6ed86-249">What is Windows Update for Business?</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [<span data-ttu-id="6ed86-250">将设备分配给 Windows 10 更新的服务分支</span><span class="sxs-lookup"><span data-stu-id="6ed86-250">Assign devices to servicing channels for Windows 10 updates</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [<span data-ttu-id="6ed86-251">在 Intune 中管理 Windows 10 软件更新</span><span class="sxs-lookup"><span data-stu-id="6ed86-251">Manage Windows 10 software updates in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
