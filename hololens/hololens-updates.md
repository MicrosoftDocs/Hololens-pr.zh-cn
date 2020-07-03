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
ms.date: 03/24/2020
ms.reviewer: jarrettr
manager: jarrettr
ms.custom:
- CI 115825
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3de48a913779f124c1cee21791af256a41bf45f8
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827668"
---
# <span data-ttu-id="f9f40-103">管理 HoloLens 更新</span><span class="sxs-lookup"><span data-stu-id="f9f40-103">Manage HoloLens updates</span></span>

<span data-ttu-id="f9f40-104">HoloLens 使用 Windows 更新的方式与其他 Windows 10 设备相同。</span><span class="sxs-lookup"><span data-stu-id="f9f40-104">HoloLens uses Windows Update in the same manner as other Windows 10 devices.</span></span> <span data-ttu-id="f9f40-105">当有可用更新时，下次设备接通电源并连接到网络时，会自动下载并安装。</span><span class="sxs-lookup"><span data-stu-id="f9f40-105">When an update is available, it is automatically downloaded and installed the next time that your device is plugged in and connected to the internet.</span></span> <span data-ttu-id="f9f40-106">本文介绍如何在企业或其他托管环境中管理 HoloLens 更新。</span><span class="sxs-lookup"><span data-stu-id="f9f40-106">This article describes how to manage updates in an enterprise or other managed environment.</span></span> <span data-ttu-id="f9f40-107">有关管理单个 HoloLens 设备更新的信息，请参阅[更新 HoloLens](hololens-update-hololens.md)。</span><span class="sxs-lookup"><span data-stu-id="f9f40-107">For information about managing updates to individual HoloLens devices, see [Update HoloLens](hololens-update-hololens.md).</span></span>

## <span data-ttu-id="f9f40-108">自动管理更新</span><span class="sxs-lookup"><span data-stu-id="f9f40-108">Manage updates automatically</span></span>

<span data-ttu-id="f9f40-109">Windows Holographic for Business 可使用[适用于企业的 Windows 更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)管理更新。</span><span class="sxs-lookup"><span data-stu-id="f9f40-109">Windows Holographic for Business can use [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) to manage updates.</span></span> <span data-ttu-id="f9f40-110">所有 HoloLens 2 设备均可使用 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="f9f40-110">All HoloLens 2 devices can use Windows Holographic for Business.</span></span> <span data-ttu-id="f9f40-111">确保你的 HoloLens 2 设备使用 Windows Holographic for Business 10.0.18362.1042 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="f9f40-111">Make sure that they use Windows Holographic for Business build 10.0.18362.1042 or a later build.</span></span> <span data-ttu-id="f9f40-112">如果你使用的是 HoloLens（第一代）设备，则必须[将它们升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 以管理更新。</span><span class="sxs-lookup"><span data-stu-id="f9f40-112">If you have HoloLens (1st gen) devices, you have to [upgrade them to Windows Holographic for Business](hololens1-upgrade-enterprise.md) to manage their updates.</span></span>

<span data-ttu-id="f9f40-113">适用于企业的 Windows 更新将 HoloLens 设备直接连接到 Windows 更新服务。</span><span class="sxs-lookup"><span data-stu-id="f9f40-113">Windows Update for Business connects HoloLens devices directly to the Windows Update service.</span></span> <span data-ttu-id="f9f40-114">通过使用适用于企业的 Windows 更新，你可以控制更新过程的多个方面&mdash;：具体而言，哪些设备将在什么时候获取哪些更新。</span><span class="sxs-lookup"><span data-stu-id="f9f40-114">By using Windows Update for Business, you can control multiple aspects of the update process&mdash;that is, which devices get which updates at what time.</span></span> <span data-ttu-id="f9f40-115">例如，可先将更新部署到设备的某个子集进行测试，日后再对剩余的设备进行更新。</span><span class="sxs-lookup"><span data-stu-id="f9f40-115">For example, you can roll out updates to a subset of devices for testing, then roll out updates to the remaining devices at a later date.</span></span> <span data-ttu-id="f9f40-116">或是为不同类型的更新制定不同的更新计划。</span><span class="sxs-lookup"><span data-stu-id="f9f40-116">Or, you can define different update schedules for different types of updates.</span></span>

> [!NOTE]  
> <span data-ttu-id="f9f40-117">你可以自动管理 HoloLens 设备的功能更新（每年发布两次）和质量更新（每月发布或根据需要发布，包括关键安全更新）。</span><span class="sxs-lookup"><span data-stu-id="f9f40-117">For HoloLens devices, you can automatically manage feature updates (released twice a year) and quality updates (released monthly or as required, including critical security updates).</span></span> <span data-ttu-id="f9f40-118">有关更新类型的更多信息，请参阅[适用于企业的 Windows 更新托管的更新类型](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)。</span><span class="sxs-lookup"><span data-stu-id="f9f40-118">For more information about update types, see [Types of updates managed by Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).</span></span>

<span data-ttu-id="f9f40-119">可以使用移动设备管理 (MDM) 解决方案中的 Microsoft Intune 等策略为 HoloLens 配置适用于企业的 Windows 更新设置。</span><span class="sxs-lookup"><span data-stu-id="f9f40-119">You can configure Windows Update for Business settings for HoloLens by using policies in a Mobile Device Management (MDM) solution such as Microsoft Intune.</span></span>

<span data-ttu-id="f9f40-120">如需详细了解如何使用 Intune 配置适用于企业的 Windows 更新，请参阅[在 Intune 中管理 Windows 10 软件更新](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="f9f40-120">For a detailed discussion about how to use Intune to configure Windows Update for Business, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/intune/protect/windows-update-for-business-configure).</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="f9f40-121">Intune 提供两种更新管理策略，分别是：*Windows 10 更新通道*和 *Windows 10 功能更新*。</span><span class="sxs-lookup"><span data-stu-id="f9f40-121">Intune provides two policy types for managing updates: *Windows 10 update ring* and *Windows 10 feature updates*.</span></span> <span data-ttu-id="f9f40-122">Windows 10 功能更新策略目前尚处于公共预览版阶段，暂不支持 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="f9f40-122">The Windows 10 feature update policy type is in public preview at this time and is not supported for HoloLens.</span></span>
>  
> <span data-ttu-id="f9f40-123">你可以使用 Windows 10 更新通道策略管理 HoloLens 2 更新。</span><span class="sxs-lookup"><span data-stu-id="f9f40-123">You can use Windows 10 update ring policies to manage HoloLens 2 updates.</span></span>

### <span data-ttu-id="f9f40-124">配置 HoloLens 2 或 HoloLens（第一代）更新策略</span><span class="sxs-lookup"><span data-stu-id="f9f40-124">Configure update policies for HoloLens 2 or HoloLens (1st gen)</span></span>

<span data-ttu-id="f9f40-125">本节介绍用于管理 HoloLens 2 或 HoloLens（第一代）更新的策略。</span><span class="sxs-lookup"><span data-stu-id="f9f40-125">This section describes the policies that you can use to manage updates for either HoloLens 2 or HoloLens (1st gen).</span></span> <span data-ttu-id="f9f40-126">有关 HoloLens 2 更多可用功能的信息，请参阅[规划和配置 HoloLens 2 更新推出](#plan-and-configure-update-rollouts-for-hololens-2)。</span><span class="sxs-lookup"><span data-stu-id="f9f40-126">For information about additional functionality that is available for HoloLens 2, see [Plan and configure update rollouts for HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).</span></span>

<span data-ttu-id="f9f40-127">[策略配置服务提供商 (CSP)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) 制定配置适用于企业的 Windows 更新的策略。</span><span class="sxs-lookup"><span data-stu-id="f9f40-127">The [Policy configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update) defines the policies that configure Windows Update for Business.</span></span>

> [!NOTE]  
> <span data-ttu-id="f9f40-128">如需详细了解 HoloLens 特定版本支持的具体策略，请参阅 [HoloLens 设备支持的策略](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices)。</span><span class="sxs-lookup"><span data-stu-id="f9f40-128">For details about specific policies that are supported by specific editions of HoloLens, see [Policies supported by HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-hololens-devices).</span></span>

#### <span data-ttu-id="f9f40-129">配置自动检查更新</span><span class="sxs-lookup"><span data-stu-id="f9f40-129">Configure automatic checks for updates</span></span>

<span data-ttu-id="f9f40-130">可以使用 **Update/AllowAutoUpdate** 策略自动管理扫描、下载和安装更新等更新行为。</span><span class="sxs-lookup"><span data-stu-id="f9f40-130">You can use the **Update/AllowAutoUpdate** policy to manage automatic update behavior, such as scanning, downloading, and installing updates.</span></span>

<span data-ttu-id="f9f40-131">该策略支持以下值：</span><span class="sxs-lookup"><span data-stu-id="f9f40-131">This policy supports the following values:</span></span>

- <span data-ttu-id="f9f40-132">**0** - 当适用于设备的更新已准备好下载时通知用户。</span><span class="sxs-lookup"><span data-stu-id="f9f40-132">**0** - Notify the user when there is an update that is ready to download that applies to the device.</span></span>
- <span data-ttu-id="f9f40-133">**1** - 自动安装更新，然后通知用户计划设备重启。</span><span class="sxs-lookup"><span data-stu-id="f9f40-133">**1** - Automatically install the update, and then notify the user to schedule a device restart.</span></span>  
- <span data-ttu-id="f9f40-134">**2** - 自动安装更新，然后重启设备。</span><span class="sxs-lookup"><span data-stu-id="f9f40-134">**2** - Automatically install the update, and then restart the device.</span></span> <span data-ttu-id="f9f40-135">该策略默认使用并推荐该值。</span><span class="sxs-lookup"><span data-stu-id="f9f40-135">This is the recommended value, and it is the default value for this policy.</span></span>  

- <span data-ttu-id="f9f40-136">**3** - 自动安装更新，然后在特定时间重启设备。</span><span class="sxs-lookup"><span data-stu-id="f9f40-136">**3** - Automatically install the update, and then restart at a specified time.</span></span> <span data-ttu-id="f9f40-137">指定日期和时间安装更新。</span><span class="sxs-lookup"><span data-stu-id="f9f40-137">Specify the installation day and time.</span></span> <span data-ttu-id="f9f40-138">如不指定具体日期和时间，则默认在每天凌晨 3 点安装。</span><span class="sxs-lookup"><span data-stu-id="f9f40-138">If no day and time are specified, the default is daily at 3 A.M.</span></span>  

- <span data-ttu-id="f9f40-139">**4** - 自动安装更新，然后重启设备。</span><span class="sxs-lookup"><span data-stu-id="f9f40-139">**4** - Automatically install the update, and then restart the device.</span></span> <span data-ttu-id="f9f40-140">该选项同样会将“设置”页面设置为“只读”。</span><span class="sxs-lookup"><span data-stu-id="f9f40-140">This option also sets the Settings page to read-only.</span></span>

- <span data-ttu-id="f9f40-141">**5** - 关闭自动更新。</span><span class="sxs-lookup"><span data-stu-id="f9f40-141">**5** - Turn off automatic updates.</span></span>

<span data-ttu-id="f9f40-142">如需详细了解该策略的可用设置，请参阅 [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)。</span><span class="sxs-lookup"><span data-stu-id="f9f40-142">For more details about the available settings for this policy, see [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).</span></span>

> [!NOTE]  
> <span data-ttu-id="f9f40-143">在 Microsoft Intune 中，你可以使用**自动更新行为**更改该策略。</span><span class="sxs-lookup"><span data-stu-id="f9f40-143">In Microsoft Intune, you can use **Automatic Update Behavior** to change this policy.</span></span> <span data-ttu-id="f9f40-144">如需了解更多信息，请参阅[在 Microsoft Intune 中管理软件更新](https://docs.microsoft.com/intune/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="f9f40-144">For more information, see [Manage software updates in Microsoft Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

#### <span data-ttu-id="f9f40-145">配置更新计划</span><span class="sxs-lookup"><span data-stu-id="f9f40-145">Configure an update schedule</span></span>

<span data-ttu-id="f9f40-146">要配置应用更新的方式和时间，请使用以下策略：</span><span class="sxs-lookup"><span data-stu-id="f9f40-146">To configure how and when updates are applied, use the following policies:</span></span>

- <span data-ttu-id="f9f40-147">[Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)。</span><span class="sxs-lookup"><span data-stu-id="f9f40-147">[Update/ScheduledInstallDay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday).</span></span>  
   - <span data-ttu-id="f9f40-148">值的范围：**0**–**7**（其中 0 代表每天，1 代表周日，7 代表周六）</span><span class="sxs-lookup"><span data-stu-id="f9f40-148">Values: **0**–**7** (0 = every day, 1 = Sunday, 7 = Saturday)</span></span>
   - <span data-ttu-id="f9f40-149">默认值：**0**（每天）</span><span class="sxs-lookup"><span data-stu-id="f9f40-149">Default value: **0** (every day)</span></span>
- <span data-ttu-id="f9f40-150">[Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)。</span><span class="sxs-lookup"><span data-stu-id="f9f40-150">[Update/ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime).</span></span>
   - <span data-ttu-id="f9f40-151">值的范围：0-23（其中 0 代表午夜，23 代表晚上 11 点）</span><span class="sxs-lookup"><span data-stu-id="f9f40-151">Values: 0–23 (0 = midnight, 23 = 11 P.M.)</span></span>
   - <span data-ttu-id="f9f40-152">默认值：凌晨 3 点</span><span class="sxs-lookup"><span data-stu-id="f9f40-152">Default value: 3 P.M.</span></span>

#### <span data-ttu-id="f9f40-153">只针对运行 Windows 10 1607 版本的设备</span><span class="sxs-lookup"><span data-stu-id="f9f40-153">For devices that run Windows 10, version 1607 only</span></span>

<span data-ttu-id="f9f40-154">可以使用以下更新策略配置设备从 Windows Server Update Services (WSUS) 而非 Windows 更新获取更新：</span><span class="sxs-lookup"><span data-stu-id="f9f40-154">You can use the following update policies to configure devices to get updates from the Windows Server Update Service (WSUS), instead of Windows Update:</span></span>

- [<span data-ttu-id="f9f40-155">Update/AllowUpdateService</span><span class="sxs-lookup"><span data-stu-id="f9f40-155">Update/AllowUpdateService</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [<span data-ttu-id="f9f40-156">Update/RequireUpdateApproval</span><span class="sxs-lookup"><span data-stu-id="f9f40-156">Update/RequireUpdateApproval</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [<span data-ttu-id="f9f40-157">Update/UpdateServiceUrl</span><span class="sxs-lookup"><span data-stu-id="f9f40-157">Update/UpdateServiceUrl</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <span data-ttu-id="f9f40-158">规划和配置 HoloLens 2 更新推出</span><span class="sxs-lookup"><span data-stu-id="f9f40-158">Plan and configure update rollouts for HoloLens 2</span></span>

<span data-ttu-id="f9f40-159">相比 HoloLens（第一代），HoloLens 2 支持更多自动化更新功能。</span><span class="sxs-lookup"><span data-stu-id="f9f40-159">HoloLens 2 supports more update automation features than HoloLens (1st gen).</span></span> <span data-ttu-id="f9f40-160">如果你使用 Microsoft Intune 来管理适用于企业的 Windows 更新策略，尤其如此。</span><span class="sxs-lookup"><span data-stu-id="f9f40-160">this is especially true if you use Microsoft Intune to manage Windows Update for Business policy.</span></span> <span data-ttu-id="f9f40-161">借助这些功能，可更轻松地规划和部署整个组织的更新。</span><span class="sxs-lookup"><span data-stu-id="f9f40-161">These features make it easier for you to plan and implement update rollouts across your organization.</span></span>

#### <span data-ttu-id="f9f40-162">规划更新策略</span><span class="sxs-lookup"><span data-stu-id="f9f40-162">Plan the update strategy</span></span>

<span data-ttu-id="f9f40-163">适用于企业的 Windows 更新支持延期策略。</span><span class="sxs-lookup"><span data-stu-id="f9f40-163">Windows Updates for Business supports deferral policies.</span></span> <span data-ttu-id="f9f40-164">Microsoft 发布更新后，你可以使用延期策略定义在设备上等待多久后安装该更新。</span><span class="sxs-lookup"><span data-stu-id="f9f40-164">After Microsoft releases an update, you can use a deferral policy to define how long to wait before installing that update on devices.</span></span> <span data-ttu-id="f9f40-165">通过将设备子集（称为“*更新通道*”）与不同的延期策略相关联，可协调组织的更新推出策略。</span><span class="sxs-lookup"><span data-stu-id="f9f40-165">By associating subsets of your devices (referred to as *update rings*) with different deferral policies, you can coordinate an update rollout strategy for your organization.</span></span>

<span data-ttu-id="f9f40-166">例如，假设某个组织拥有 1,000 台设备，并且必须通过 5 种方式更新这些设备。</span><span class="sxs-lookup"><span data-stu-id="f9f40-166">For example, consider an organization that has 1,000 devices and has to update them in five ways.</span></span> <span data-ttu-id="f9f40-167">该组织可按下表所示，创建 5 个更新通道。</span><span class="sxs-lookup"><span data-stu-id="f9f40-167">The organization can create five update rings, as shown in the following table.</span></span>

|<span data-ttu-id="f9f40-168">组</span><span class="sxs-lookup"><span data-stu-id="f9f40-168">Group</span></span> |<span data-ttu-id="f9f40-169">设备数量</span><span class="sxs-lookup"><span data-stu-id="f9f40-169">Number of devices</span></span> |<span data-ttu-id="f9f40-170">延期（天数）</span><span class="sxs-lookup"><span data-stu-id="f9f40-170">Deferral (days)</span></span> |
| ---| :---: | :---: |
|<span data-ttu-id="f9f40-171">组 1（IT 人员）</span><span class="sxs-lookup"><span data-stu-id="f9f40-171">Grp 1 (IT staff)</span></span> |<span data-ttu-id="f9f40-172">5</span><span class="sxs-lookup"><span data-stu-id="f9f40-172">5</span></span> |<span data-ttu-id="f9f40-173">0</span><span class="sxs-lookup"><span data-stu-id="f9f40-173">0</span></span> |
|<span data-ttu-id="f9f40-174">组 2（早期采用者）</span><span class="sxs-lookup"><span data-stu-id="f9f40-174">Grp 2 (early adopters)</span></span> |<span data-ttu-id="f9f40-175">50</span><span class="sxs-lookup"><span data-stu-id="f9f40-175">50</span></span> |<span data-ttu-id="f9f40-176">60</span><span class="sxs-lookup"><span data-stu-id="f9f40-176">60</span></span> |
|<span data-ttu-id="f9f40-177">组 3（主要设备 1）</span><span class="sxs-lookup"><span data-stu-id="f9f40-177">Grp 3 (main 1)</span></span> |<span data-ttu-id="f9f40-178">250</span><span class="sxs-lookup"><span data-stu-id="f9f40-178">250</span></span> |<span data-ttu-id="f9f40-179">120</span><span class="sxs-lookup"><span data-stu-id="f9f40-179">120</span></span> |
|<span data-ttu-id="f9f40-180">组 4（主要设备 2）</span><span class="sxs-lookup"><span data-stu-id="f9f40-180">Grp 4 (main 2)</span></span> |<span data-ttu-id="f9f40-181">300</span><span class="sxs-lookup"><span data-stu-id="f9f40-181">300</span></span> |<span data-ttu-id="f9f40-182">150</span><span class="sxs-lookup"><span data-stu-id="f9f40-182">150</span></span> |
|<span data-ttu-id="f9f40-183">组 5（主要设备 3）</span><span class="sxs-lookup"><span data-stu-id="f9f40-183">Grp 5 (main 3)</span></span> |<span data-ttu-id="f9f40-184">395</span><span class="sxs-lookup"><span data-stu-id="f9f40-184">395</span></span> |<span data-ttu-id="f9f40-185">180</span><span class="sxs-lookup"><span data-stu-id="f9f40-185">180</span></span> |

<span data-ttu-id="f9f40-186">随着时间推移，整个组织将按照此过程推出更新。</span><span class="sxs-lookup"><span data-stu-id="f9f40-186">Here's how the rollout progresses over time to the entire organization.</span></span>

![更新部署日程表](./images/hololens-updates-timeline.png)

#### <span data-ttu-id="f9f40-188">配置更新延期策略</span><span class="sxs-lookup"><span data-stu-id="f9f40-188">Configure an update deferral policy</span></span>

<span data-ttu-id="f9f40-189">延期策略指定可用更新日期和向设备提供更新日期之间间隔的天数。</span><span class="sxs-lookup"><span data-stu-id="f9f40-189">A deferral policy specifies the number of days between the date that an update becomes available and the date that the update is offered to a device.</span></span>

<span data-ttu-id="f9f40-190">可为功能更新和质量更新配置不同的延期天数。</span><span class="sxs-lookup"><span data-stu-id="f9f40-190">You can configure different deferrals for feature updates and quality updates.</span></span> <span data-ttu-id="f9f40-191">下表列出了每种类型要使用的具体策略，以及每个类型最多可以延期的天数。</span><span class="sxs-lookup"><span data-stu-id="f9f40-191">The following table lists the specific policies to use for each type, as well as the maximum deferral for each.</span></span>

|<span data-ttu-id="f9f40-192">类别</span><span class="sxs-lookup"><span data-stu-id="f9f40-192">Category</span></span> |<span data-ttu-id="f9f40-193">策略</span><span class="sxs-lookup"><span data-stu-id="f9f40-193">Policy</span></span> |<span data-ttu-id="f9f40-194">最大延迟</span><span class="sxs-lookup"><span data-stu-id="f9f40-194">Maximum deferral</span></span> |
| --- | --- | --- |
|<span data-ttu-id="f9f40-195">功能更新</span><span class="sxs-lookup"><span data-stu-id="f9f40-195">Feature updates</span></span> |<span data-ttu-id="f9f40-196">DeferFeatureUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="f9f40-196">DeferFeatureUpdatesPeriodInDays</span></span> |<span data-ttu-id="f9f40-197">365 天</span><span class="sxs-lookup"><span data-stu-id="f9f40-197">365 days</span></span> |
|<span data-ttu-id="f9f40-198">质量更新</span><span class="sxs-lookup"><span data-stu-id="f9f40-198">Quality updates</span></span> |<span data-ttu-id="f9f40-199">DeferQualityUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="f9f40-199">DeferQualityUpdatesPeriodInDays</span></span> |<span data-ttu-id="f9f40-200">30 天</span><span class="sxs-lookup"><span data-stu-id="f9f40-200">30 days</span></span> |

####  <span data-ttu-id="f9f40-201">示例：使用 Intune 管理更新</span><span class="sxs-lookup"><span data-stu-id="f9f40-201">Examples: Using Intune to manage updates</span></span>

**<span data-ttu-id="f9f40-202">示例 1：创建和分配更新通道</span><span class="sxs-lookup"><span data-stu-id="f9f40-202">Example 1: Create and assign an update ring</span></span>**

<span data-ttu-id="f9f40-203">有关此示例的更详细版本，请参阅[创建和分配更新通道](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)。</span><span class="sxs-lookup"><span data-stu-id="f9f40-203">For a more detailed version of this example, see [Create and assign update rings](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).</span></span>

1. <span data-ttu-id="f9f40-204">登录到 [Microsoft Endpoint Manager 管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，然后导航到你的 Intune 配置文件。</span><span class="sxs-lookup"><span data-stu-id="f9f40-204">Sign in to the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), and navigate to your Intune profiles.</span></span>
1. <span data-ttu-id="f9f40-205">选择“**软件更新**” > “**Windows 10 更新通道**” > “**创建**”。</span><span class="sxs-lookup"><span data-stu-id="f9f40-205">Select **Software Updates** > **Windows 10 update rings** > **Create**.</span></span>
1. <span data-ttu-id="f9f40-206">在“**基础**”下，指定名称和说明（选填），然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f9f40-206">Under **Basics**, specify a name and a description (optional), and then select **Next**.</span></span>
1. <span data-ttu-id="f9f40-207">在“**更新通道设置**”下，**服务频道**请选择“**半年频道**”，然后将**功能更新延期期限更改**为 **120 天**。</span><span class="sxs-lookup"><span data-stu-id="f9f40-207">Under **Update ring settings**, for **Servicing channel**, select **Semi-Annual Channel**, and then change **Feature update deferral period** to **120**.</span></span> <span data-ttu-id="f9f40-208">然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f9f40-208">Then, select **Next**.</span></span>
1. <span data-ttu-id="f9f40-209">在“**分配**”下，选择“**+ 选择要包含的组**”，然后将更新通道分配给一个或多个组。</span><span class="sxs-lookup"><span data-stu-id="f9f40-209">Under **Assignments**, select **+ Select groups to include**, and then assign the update ring to one or more groups.</span></span> <span data-ttu-id="f9f40-210">使用“**+ 选择要排除的组**”微调分配。</span><span class="sxs-lookup"><span data-stu-id="f9f40-210">Use **+ Select groups to exclude** to fine-tune the assignments.</span></span> <span data-ttu-id="f9f40-211">然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="f9f40-211">Then, select **Next**.</span></span>
1. <span data-ttu-id="f9f40-212">在**审核 + 创建**下，查看设置。</span><span class="sxs-lookup"><span data-stu-id="f9f40-212">Under **Review + create**, review the settings.</span></span> <span data-ttu-id="f9f40-213">当你准备好保存更新通道配置时，请选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="f9f40-213">When you're ready to save the update ring configuration, select **Create**.</span></span>

<span data-ttu-id="f9f40-214">更新通道列表现在包括新的 Windows 10 更新通道。</span><span class="sxs-lookup"><span data-stu-id="f9f40-214">The list of update rings now includes the new Windows 10 update ring.</span></span>

**<span data-ttu-id="f9f40-215">示例 2：暂停更新通道</span><span class="sxs-lookup"><span data-stu-id="f9f40-215">Example 2: Pause an update ring</span></span>**

<span data-ttu-id="f9f40-216">如果部署功能或质量更新时遇到问题，可暂停更新 35 天（从指定日期开始计算）。</span><span class="sxs-lookup"><span data-stu-id="f9f40-216">If you encounter a problem when you deploy a feature or quality update, you can pause the update for 35 days (starting from a specified date).</span></span> <span data-ttu-id="f9f40-217">暂停后会阻止其他设备安装更新，直至你解决或缓解该问题。</span><span class="sxs-lookup"><span data-stu-id="f9f40-217">This pause prevents other devices from installing the update until you resolve or mitigate the issue.</span></span> <span data-ttu-id="f9f40-218">即使暂停功能更新，仍会向设备提供质量更新以确保它们保持安全。</span><span class="sxs-lookup"><span data-stu-id="f9f40-218">If you pause a feature update, quality updates are still offered to devices to make sure that they stay secure.</span></span> <span data-ttu-id="f9f40-219">指定时间过后，暂停将自动过期。</span><span class="sxs-lookup"><span data-stu-id="f9f40-219">After the specified time has passed, the pause automatically expires.</span></span> <span data-ttu-id="f9f40-220">此时，将恢复更新过程。</span><span class="sxs-lookup"><span data-stu-id="f9f40-220">At that point, the update process resumes.</span></span>

<span data-ttu-id="f9f40-221">若要暂停 Intune 中的更新通道，请按照如下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f9f40-221">To pause an update ring in Intune, follow these steps:</span></span>

1. <span data-ttu-id="f9f40-222">在更新通道的“概述”页面，选择“**暂停**”。</span><span class="sxs-lookup"><span data-stu-id="f9f40-222">On the overview page for the update ring, select **Pause**.</span></span>
1. <span data-ttu-id="f9f40-223">选择要暂停的更新类型（**功能**或**质量**更新），然后选择“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="f9f40-223">Select the type of update (**Feature** or **Quality**) to pause, and then select **OK**.</span></span>

<span data-ttu-id="f9f40-224">暂停更新类型后，相应通道的“概述”窗格会显示更新类型恢复前剩余的天数。</span><span class="sxs-lookup"><span data-stu-id="f9f40-224">When an update type is paused, the Overview pane for that ring displays how many days remain before that update type resumes.</span></span>

<span data-ttu-id="f9f40-225">暂停更新通道时，可选择以下任一选项：</span><span class="sxs-lookup"><span data-stu-id="f9f40-225">While the update ring is paused, you can select either of the following options:</span></span>

- <span data-ttu-id="f9f40-226">若要延长更新类型暂停期限 35 天，请选择“**延长**”。</span><span class="sxs-lookup"><span data-stu-id="f9f40-226">To extend the pause period for an update type for 35 days, select **Extend**.</span></span>
- <span data-ttu-id="f9f40-227">若要将该通道的更新还原为活动操作，请选择“**恢复**”。</span><span class="sxs-lookup"><span data-stu-id="f9f40-227">To restore updates for that ring to active operation, select **Resume**.</span></span> <span data-ttu-id="f9f40-228">如果有必要，可以再次暂停更新通道。</span><span class="sxs-lookup"><span data-stu-id="f9f40-228">You can pause the update ring again if it is necessary.</span></span>

> [!NOTE]  
> <span data-ttu-id="f9f40-229">HoloLens 2 设备不支持更新通道的“**卸载**”操作。</span><span class="sxs-lookup"><span data-stu-id="f9f40-229">The **Uninstall** operation for update rings is not supported for HoloLens 2 devices.</span></span>

## <span data-ttu-id="f9f40-230">手动检查更新</span><span class="sxs-lookup"><span data-stu-id="f9f40-230">Manually check for updates</span></span>

<span data-ttu-id="f9f40-231">虽然 HoloLens 会定期检查系统更新，免去手动检查之苦，但在某些情况下，仍可能需要手动检查。</span><span class="sxs-lookup"><span data-stu-id="f9f40-231">Although HoloLens periodically checks for system updates so that you don't have to, there may be circumstances in which you want to manually check.</span></span>

<span data-ttu-id="f9f40-232">若要手动检查更新，请转到“**设置**” > “**更新和安全**” > “**检查更新**”。</span><span class="sxs-lookup"><span data-stu-id="f9f40-232">To manually check for updates, go to **Settings** > **Update & Security** > **Check for updates**.</span></span> <span data-ttu-id="f9f40-233">如果“设置”应用指示你的设备已是最新版本，则表示你已安装所有可用更新。</span><span class="sxs-lookup"><span data-stu-id="f9f40-233">If the Settings app indicates that your device is up to date, you have all the updates that are currently available.</span></span>

## <span data-ttu-id="f9f40-234">手动还原更新</span><span class="sxs-lookup"><span data-stu-id="f9f40-234">Manually revert an update</span></span>

<span data-ttu-id="f9f40-235">在某些情况下，你可能想要返回到 HoloLens 软件的早期版本。</span><span class="sxs-lookup"><span data-stu-id="f9f40-235">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="f9f40-236">视您使用的是 HoloLens 2 还是 HoloLens（第一代），请选择以下对应的操作流程。</span><span class="sxs-lookup"><span data-stu-id="f9f40-236">The process for doing this depends on whether you are using HoloLens 2 or HoloLens (1st gen).</span></span>

### <span data-ttu-id="f9f40-237">HoloLens 2 如何返回到早期版本</span><span class="sxs-lookup"><span data-stu-id="f9f40-237">Go back to a previous version (HoloLens 2)</span></span>

<span data-ttu-id="f9f40-238">可使用“高级恢复助手”将 HoloLens 重置为早期版本，以实现回滚并返回到 HoloLens 2 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="f9f40-238">You can roll back updates and return to a previous version of HoloLens 2 by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="f9f40-239">还原到早期版本会删除你的个人文件和设置。</span><span class="sxs-lookup"><span data-stu-id="f9f40-239">Reverting to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="f9f40-240">若要返回到 HoloLens 2 的早期版本，请按照如下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f9f40-240">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="f9f40-241">请确保你没有任何手机或 Windows 设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="f9f40-241">Make sure that you don't have any phones or Windows devices plugged in to your computer.</span></span>
1. <span data-ttu-id="f9f40-242">在你的电脑上，从 Microsoft 应用商店下载[高级恢复助手](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)。</span><span class="sxs-lookup"><span data-stu-id="f9f40-242">On your computer, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="f9f40-243">下载[最新版本的 HoloLens 2](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="f9f40-243">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="f9f40-244">完成以上下载后，打开“**文件资源管理器**” > “**下载**”，右键单击刚才下载的 zip 压缩文件夹，然后选择“**提取全部**” > “**提取**”以展开该文件。</span><span class="sxs-lookup"><span data-stu-id="f9f40-244">When you have finished these downloads, open **File explorer** > **Downloads**, right-click the compressed (zipped) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="f9f40-245">使用 USB-A 到 USB-C 数据线将 HoloLens 设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="f9f40-245">Use a USB-A to USB-C cable to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="f9f40-246">即使你在连接 HoloLens 时一直使用的是其他数据线，但此数据线的使用效果更好。</span><span class="sxs-lookup"><span data-stu-id="f9f40-246">Even if you've been using other cables to connect your HoloLens, this kind of cable works best.</span></span>
1. <span data-ttu-id="f9f40-247">“高级恢复助手”会自动检测到 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="f9f40-247">The Advanced Recovery Companion automatically detects your HoloLens device.</span></span> <span data-ttu-id="f9f40-248">选择“**Microsoft HoloLens**”磁贴。</span><span class="sxs-lookup"><span data-stu-id="f9f40-248">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="f9f40-249">在下一个屏幕中，选择“**手动选择包**”，然后打开先前展开的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f9f40-249">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span> 
1. <span data-ttu-id="f9f40-250">选择安装文件（扩展名为 .ffu 的文件）。</span><span class="sxs-lookup"><span data-stu-id="f9f40-250">Select the installation file (the file that has an .ffu extension).</span></span>
1. <span data-ttu-id="f9f40-251">选择**安装软件**，然后按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="f9f40-251">Select **Install software**, and then follow the instructions.</span></span>

### <span data-ttu-id="f9f40-252">HoloLens（第一代）如何返回到早期版本</span><span class="sxs-lookup"><span data-stu-id="f9f40-252">Go back to a previous version (HoloLens (1st gen))</span></span>

<span data-ttu-id="f9f40-253">可使用“Windows Device Recovery Tool”将 HoloLens 重置为早期版本，以实现回滚并返回到 HoloLens（第一代）的早期版本。</span><span class="sxs-lookup"><span data-stu-id="f9f40-253">You can roll back updates and return to a previous version of HoloLens (1st gen) by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="f9f40-254">还原到早期版本会删除你的个人文件和设置。</span><span class="sxs-lookup"><span data-stu-id="f9f40-254">Reverting to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="f9f40-255">要返回到 HoloLens（第一代）的早期版本，请按照如下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="f9f40-255">To go back to a previous version of HoloLens (1st gen), follow these steps:</span></span>

1. <span data-ttu-id="f9f40-256">请确保你没有任何手机或 Windows 设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="f9f40-256">Make sure that you don't have any phones or Windows devices plugged in to your computer.</span></span>
1. <span data-ttu-id="f9f40-257">在你的电脑上，下载并安装 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)。</span><span class="sxs-lookup"><span data-stu-id="f9f40-257">On your computer, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="f9f40-258">下载 [HoloLens 周年更新恢复包](https://aka.ms/hololensrecovery)。</span><span class="sxs-lookup"><span data-stu-id="f9f40-258">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="f9f40-259">完成下载后，打开“**文件资源管理器**” > “**下载**”，右键单击刚才下载的 zip 压缩文件夹，然后选择“**提取全部**” > “**提取**”以展开该文件。</span><span class="sxs-lookup"><span data-stu-id="f9f40-259">After the downloads finish, open **File explorer** > **Downloads**, right-click the compressed (zipped) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="f9f40-260">使用与 HoloLens 设备随附的 micro-USB 数据线将 HoloLens 设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="f9f40-260">Use the micro-USB cable that was provided together with your HoloLens device to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="f9f40-261">即使你在连接 HoloLens 时一直使用的是其他数据线，但原厂数据线的使用效果更好。</span><span class="sxs-lookup"><span data-stu-id="f9f40-261">Even if you've been using other cables to connect your HoloLens device, this one works best.</span></span>
1. <span data-ttu-id="f9f40-262">Windows Device Recovery Tool 会自动检测到 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="f9f40-262">The WDRT automatically detects your HoloLens device.</span></span> <span data-ttu-id="f9f40-263">选择“**Microsoft HoloLens**”磁贴。</span><span class="sxs-lookup"><span data-stu-id="f9f40-263">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="f9f40-264">在下一个屏幕中，选择“**手动选择包**”，然后打开先前展开的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f9f40-264">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span> 
1. <span data-ttu-id="f9f40-265">选择安装文件（扩展名为 .ffu 的文件）。</span><span class="sxs-lookup"><span data-stu-id="f9f40-265">Select the installation file (the file that has an .ffu extension).</span></span>
1. <span data-ttu-id="f9f40-266">选择**安装软件**，然后按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="f9f40-266">Select **Install software**, and then follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="f9f40-267">如果 Windows Device Recovery Tool 未检测到 HoloLens 设备，请尝试重启电脑。</span><span class="sxs-lookup"><span data-stu-id="f9f40-267">If the WDRT doesn't detect your HoloLens device, try restarting your computer.</span></span> <span data-ttu-id="f9f40-268">如果重启不起作用，请选择“**未检测到我的设备**”，选择“**Microsoft HoloLens**”，然后按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="f9f40-268">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="f9f40-269">相关文章</span><span class="sxs-lookup"><span data-stu-id="f9f40-269">Related articles</span></span>

- [<span data-ttu-id="f9f40-270">使用适用于企业的 Windows 更新部署更新</span><span class="sxs-lookup"><span data-stu-id="f9f40-270">Deploy updates using Windows Update for Business</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)
- [<span data-ttu-id="f9f40-271">将设备分配给 Windows 10 更新的服务分支</span><span class="sxs-lookup"><span data-stu-id="f9f40-271">Assign devices to servicing channels for Windows 10 updates</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [<span data-ttu-id="f9f40-272">在 Intune 中管理 Windows 10 软件更新</span><span class="sxs-lookup"><span data-stu-id="f9f40-272">Manage Windows 10 software updates in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)
