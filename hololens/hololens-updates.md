---
title: 管理 HoloLens 更新
description: 了解管理员如何使用移动设备管理来管理 HoloLens 设备更新。
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
audience: ITPro
ms.topic: article
ms.localizationpriority: high
ms.date: 10/13/2020
ms.reviewer: jarrettr
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.custom:
- CI 116337
- CI 115825
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 5ec26c64a971b8bfc9f8d1f9044e2e651a218816
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639992"
---
# <a name="manage-hololens-updates"></a><span data-ttu-id="22632-103">管理 HoloLens 更新</span><span class="sxs-lookup"><span data-stu-id="22632-103">Manage HoloLens updates</span></span>

<span data-ttu-id="22632-104">HoloLens 使用 Windows 更新的方式与其他 Windows 10 设备相同。</span><span class="sxs-lookup"><span data-stu-id="22632-104">HoloLens uses Windows Update in the same manner as other Windows 10 devices.</span></span> <span data-ttu-id="22632-105">当有可用更新时，下次设备接通电源并连接到 Internet 时，会自动下载并安装。</span><span class="sxs-lookup"><span data-stu-id="22632-105">When an update is available, it is automatically downloaded and installed the next time that your device is plugged in and connected to the internet.</span></span> <span data-ttu-id="22632-106">本文介绍如何在企业或其他托管环境中管理 HoloLens 更新。</span><span class="sxs-lookup"><span data-stu-id="22632-106">This article describes how to manage updates in an enterprise or other managed environment.</span></span> <span data-ttu-id="22632-107">有关如何管理单个 HoloLens 设备更新的信息，请参阅[更新 HoloLens](hololens-update-hololens.md)。</span><span class="sxs-lookup"><span data-stu-id="22632-107">For information about how to manage updates to individual HoloLens devices, see [Update HoloLens](hololens-update-hololens.md).</span></span>

## <a name="manage-updates-automatically"></a><span data-ttu-id="22632-108">自动管理更新</span><span class="sxs-lookup"><span data-stu-id="22632-108">Manage updates automatically</span></span>

### <a name="managing-updates-by-using-windows-update-for-business"></a><span data-ttu-id="22632-109">使用适用于企业的 Windows 更新管理更新</span><span class="sxs-lookup"><span data-stu-id="22632-109">Managing updates by using Windows Update for Business</span></span>

<span data-ttu-id="22632-110">Windows Holographic for Business 可以使用[适用于企业的 Windows 更新](/windows/deployment/update/waas-manage-updates-wufb)管理更新。</span><span class="sxs-lookup"><span data-stu-id="22632-110">Windows Holographic for Business can use [Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb) to manage updates.</span></span> <span data-ttu-id="22632-111">所有 HoloLens 2 设备均可使用 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="22632-111">All HoloLens 2 devices can use Windows Holographic for Business.</span></span> <span data-ttu-id="22632-112">确保它们使用 Windows Holographic for Business 内部版本 10.0.18362.1042 或更高内部版本。</span><span class="sxs-lookup"><span data-stu-id="22632-112">Make sure that they use Windows Holographic for Business build 10.0.18362.1042 or a later build.</span></span> <span data-ttu-id="22632-113">如果使用的是 HoloLens（第一代）设备，则必须[将其升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 才能管理其更新。</span><span class="sxs-lookup"><span data-stu-id="22632-113">If you have HoloLens (1st gen) devices, you have to [upgrade them to Windows Holographic for Business](hololens1-upgrade-enterprise.md) in order to manage their updates.</span></span>

<span data-ttu-id="22632-114">适用于企业的 Windows 更新将 HoloLens 设备直接连接到 Windows 更新服务。</span><span class="sxs-lookup"><span data-stu-id="22632-114">Windows Update for Business connects HoloLens devices directly to the Windows Update service.</span></span> <span data-ttu-id="22632-115">通过使用适用于企业的 Windows 更新，你可以控制更新过程的多个方面&mdash;：具体而言，哪些设备将在什么时候获取哪些更新。</span><span class="sxs-lookup"><span data-stu-id="22632-115">By using Windows Update for Business, you can control multiple aspects of the update process&mdash;that is, which devices get which updates at what time.</span></span> <span data-ttu-id="22632-116">例如，可先将更新部署到设备的某个子集进行测试，随后再对剩余的设备进行更新。</span><span class="sxs-lookup"><span data-stu-id="22632-116">For example, you can roll out updates to a subset of devices for testing, then later roll out updates to the remaining devices.</span></span> <span data-ttu-id="22632-117">或是为不同类型的更新制定不同的更新计划。</span><span class="sxs-lookup"><span data-stu-id="22632-117">Or, you can define different update schedules for different types of updates.</span></span>

> [!NOTE]  
> <span data-ttu-id="22632-118">可以自动管理 HoloLens 设备的功能更新（每年发布两次）和质量更新（每月发布或根据需要发布，包括关键安全更新）。</span><span class="sxs-lookup"><span data-stu-id="22632-118">For HoloLens devices, you can automatically manage feature updates (released two times a year) and quality updates (released monthly or as required, including critical security updates).</span></span> <span data-ttu-id="22632-119">有关更新类型的详细信息，请参阅[适用于企业的 Windows 更新管理的更新类型](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business)。</span><span class="sxs-lookup"><span data-stu-id="22632-119">For more information about update types, see [Types of updates managed by Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb#types-of-updates-managed-by-windows-update-for-business).</span></span>

<span data-ttu-id="22632-120">可以使用移动设备管理 (MDM) 解决方案中的 Microsoft Intune 等策略为 HoloLens 配置适用于企业的 Windows 更新设置。</span><span class="sxs-lookup"><span data-stu-id="22632-120">You can configure Windows Update for Business settings for HoloLens by using policies in a Mobile Device Management (MDM) solution such as Microsoft Intune.</span></span>

### <a name="managing-windows-update-for-business-by-using-microsoft-intune"></a><span data-ttu-id="22632-121">使用 Microsoft Intune 管理适用于企业的 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="22632-121">Managing Windows Update for Business by using Microsoft Intune</span></span>

<span data-ttu-id="22632-122">如需详细了解如何使用 Intune 配置适用于企业的 Windows 更新，请参阅[在 Intune 中管理 Windows 10 软件更新](/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="22632-122">For a detailed discussion about how to use Intune to configure Windows Update for Business, see [Manage Windows 10 software updates in Intune](/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="22632-123">有关 HoloLens 支持的特定 Intune 功能的详细信息，请参阅 [HoloLens 支持的 Intune 更新管理功能](#intune-update-management-functions-that-hololens-supports)。</span><span class="sxs-lookup"><span data-stu-id="22632-123">For more information about the specific Intune functionality that HoloLens supports, see [Intune update management functions that HoloLens supports](#intune-update-management-functions-that-hololens-supports).</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="22632-124">Intune 提供两种管理更新的策略类型，分别是：Windows 10 更新通道和 Windows 10 功能更新。</span><span class="sxs-lookup"><span data-stu-id="22632-124">Intune provides two policy types for managing updates: *Windows 10 update ring* and *Windows 10 feature update*.</span></span> <span data-ttu-id="22632-125">Windows 10 功能更新策略目前尚处于公共预览版阶段，暂不支持 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="22632-125">The Windows 10 feature update policy type is in public preview at this time and is not supported for HoloLens.</span></span>
>  
> <span data-ttu-id="22632-126">你可以使用 Windows 10 更新通道策略管理 HoloLens 2 更新。</span><span class="sxs-lookup"><span data-stu-id="22632-126">You can use Windows 10 update ring policies to manage HoloLens 2 updates.</span></span>

### <a name="configure-update-policies-for-hololens-2-or-hololens-1st-gen"></a><span data-ttu-id="22632-127">配置 HoloLens 2 或 HoloLens（第一代）更新策略</span><span class="sxs-lookup"><span data-stu-id="22632-127">Configure update policies for HoloLens 2 or HoloLens (1st gen)</span></span>

<span data-ttu-id="22632-128">本部分介绍用于管理 HoloLens 2 或 HoloLens（第一代）更新的策略。</span><span class="sxs-lookup"><span data-stu-id="22632-128">This section describes the policies that you can use to manage updates for either HoloLens 2 or HoloLens (1st gen).</span></span> <span data-ttu-id="22632-129">有关可用于 HoloLens 2 的功能的详细信息，请参阅[规划和配置 HoloLens 2 更新推出](#plan-and-configure-update-rollouts-for-hololens-2)。</span><span class="sxs-lookup"><span data-stu-id="22632-129">For more information about the functionality that is available for HoloLens 2, see [Plan and configure update rollouts for HoloLens 2](#plan-and-configure-update-rollouts-for-hololens-2).</span></span>

<span data-ttu-id="22632-130">[策略 CSP - 更新](/windows/client-management/mdm/policy-csp-update)定义配置适用于企业的 Windows 更新的策略。</span><span class="sxs-lookup"><span data-stu-id="22632-130">[Policy CSP - Update](/windows/client-management/mdm/policy-csp-update) defines the policies that configure Windows Update for Business.</span></span>

> [!NOTE]  
> <span data-ttu-id="22632-131">有关特定版本的 HoloLens 支持的特定策略配置服务提供程序 (CSP) 的列表，请参阅 [HoloLens 设备支持的策略 CSP](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices)。</span><span class="sxs-lookup"><span data-stu-id="22632-131">For a list of specific policy configuration service providers (CSPs) that are supported by specific editions of HoloLens, see [Policy CSPs supported by HoloLens devices](/windows/client-management/mdm/policy-configuration-service-provider#policy-csps-supported-by-hololens-devices).</span></span>

#### <a name="configure-automatic-checks-for-updates"></a><span data-ttu-id="22632-132">配置自动检查更新</span><span class="sxs-lookup"><span data-stu-id="22632-132">Configure automatic checks for updates</span></span>

<span data-ttu-id="22632-133">可以使用“Update/AllowAutoUpdate”策略管理扫描、下载和安装更新等自动更新行为。</span><span class="sxs-lookup"><span data-stu-id="22632-133">You can use the **Update/AllowAutoUpdate** policy to manage automatic update behavior, such as scanning, downloading, and installing updates.</span></span> <span data-ttu-id="22632-134">有关此策略的可用设置的详细信息，请参阅 [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)。</span><span class="sxs-lookup"><span data-stu-id="22632-134">For more information about the available settings for this policy, see [Update/AllowAutoUpdate](/windows/client-management/mdm/policy-csp-update#update-allowautoupdate).</span></span>

> [!NOTE]  
> <span data-ttu-id="22632-135">在 Microsoft Intune 中，可以使用 **自动更新行为** 来更改此策略。</span><span class="sxs-lookup"><span data-stu-id="22632-135">In Microsoft Intune, you can use **Automatic Update Behavior** to change this policy.</span></span> <span data-ttu-id="22632-136">有关详细信息，请参阅[在 Intune 中管理 Windows 10 软件更新](/intune/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="22632-136">For more information, see [Manage Windows 10 software updates in Intune](/intune/windows-update-for-business-configure).</span></span>

#### <a name="configure-an-update-schedule"></a><span data-ttu-id="22632-137">配置更新计划</span><span class="sxs-lookup"><span data-stu-id="22632-137">Configure an update schedule</span></span>

<span data-ttu-id="22632-138">若要配置应用更新的方式和时间，请使用以下策略：</span><span class="sxs-lookup"><span data-stu-id="22632-138">To configure how and when updates are applied, use the following policies:</span></span>

- [<span data-ttu-id="22632-139">Update/ScheduledInstallDay</span><span class="sxs-lookup"><span data-stu-id="22632-139">Update/ScheduledInstallDay</span></span>](/windows/client-management/mdm/policy-csp-update#update-scheduledinstallday)  
  - <span data-ttu-id="22632-140">值的范围：0–7（其中 0 代表每天，1 代表周日，7 代表周六）</span><span class="sxs-lookup"><span data-stu-id="22632-140">Values: **0**–**7** (0 = every day, 1 = Sunday, 7 = Saturday)</span></span>
  - <span data-ttu-id="22632-141">默认值：0（每天）</span><span class="sxs-lookup"><span data-stu-id="22632-141">Default value: **0** (every day)</span></span>
- [<span data-ttu-id="22632-142">Update/ScheduledInstallTime</span><span class="sxs-lookup"><span data-stu-id="22632-142">Update/ScheduledInstallTime</span></span>](/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)
  - <span data-ttu-id="22632-143">值的范围：0-23（其中 0 代表午夜，23 代表晚上 11 点）</span><span class="sxs-lookup"><span data-stu-id="22632-143">Values: 0–23 (0 = midnight, 23 = 11 PM)</span></span>
  - <span data-ttu-id="22632-144">默认值：凌晨 3 点</span><span class="sxs-lookup"><span data-stu-id="22632-144">Default value: 3 AM</span></span>

#### <a name="configure-active-hours"></a><span data-ttu-id="22632-145">配置使用时段</span><span class="sxs-lookup"><span data-stu-id="22632-145">Configure active hours</span></span>
<span data-ttu-id="22632-146">从 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 开始，IT 管理员可以指定 HoloLens 2 设备的使用时段范围。</span><span class="sxs-lookup"><span data-stu-id="22632-146">Starting with [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) an IT Admin can specify the active hours range for HoloLens 2 devices.</span></span>

<span data-ttu-id="22632-147">“使用时段”可标识你希望设备正在使用中的时段。</span><span class="sxs-lookup"><span data-stu-id="22632-147">Active hours identify the period of time when you expect the device to be in use.</span></span> <span data-ttu-id="22632-148">更新后自动重启将在使用时段外发生。</span><span class="sxs-lookup"><span data-stu-id="22632-148">Automatic restarts after an update will occur outside of the active hours.</span></span> <span data-ttu-id="22632-149">指定的范围将从使用时段开始时间计算。</span><span class="sxs-lookup"><span data-stu-id="22632-149">The specified range will be counted from the active hours start time.</span></span> <span data-ttu-id="22632-150">可以使用 MDM，如[使用 MDM 配置使用时段](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm)中所述。</span><span class="sxs-lookup"><span data-stu-id="22632-150">You can use MDM, as described in [Configuring active hours with MDM](/windows/deployment/update/waas-restart#configuring-active-hours-with-mdm).</span></span> <span data-ttu-id="22632-151">MDM 使用策略 CSP 中的 Update/ActiveHoursStart 和 Update/ActiveHoursEnd 以及 Update/ActiveHoursMaxRange 设置配置使用时段。</span><span class="sxs-lookup"><span data-stu-id="22632-151">MDM uses the Update/ActiveHoursStart and Update/ActiveHoursEnd and Update/ActiveHoursMaxRange settings in the Policy CSP to configure active hours.</span></span>

-   <span data-ttu-id="22632-152">[Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) - 此值设置结束时间。</span><span class="sxs-lookup"><span data-stu-id="22632-152">[Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend) - This value sets the end time.</span></span> <span data-ttu-id="22632-153">从开始时间起最长为 12 小时。</span><span class="sxs-lookup"><span data-stu-id="22632-153">There is a 12-hour maximum from start time.</span></span>
    -   <span data-ttu-id="22632-154">支持的值为 0-23，其中 0 为中午 12 点，1 为凌晨 1 点，依此类推。</span><span class="sxs-lookup"><span data-stu-id="22632-154">Supported values are 0-23, where 0 is 12 AM, 1 is 1 AM, etc.</span></span>
    -   <span data-ttu-id="22632-155">默认值为 17（下午 5 点）。</span><span class="sxs-lookup"><span data-stu-id="22632-155">The default is 17 (5 PM).</span></span>
-   <span data-ttu-id="22632-156">[Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) - 此值设置从开始时间起的最大使用时段。</span><span class="sxs-lookup"><span data-stu-id="22632-156">[Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange) - This value sets max number of active hours from start time.</span></span>
    -   <span data-ttu-id="22632-157">支持的值为 8-18。</span><span class="sxs-lookup"><span data-stu-id="22632-157">Supported values are 8-18.</span></span>
    -   <span data-ttu-id="22632-158">默认值为 18（小时）。</span><span class="sxs-lookup"><span data-stu-id="22632-158">The default value is 18 (hours).</span></span>
-   <span data-ttu-id="22632-159">[Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) - 此值设置开始时间。</span><span class="sxs-lookup"><span data-stu-id="22632-159">[Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart) - This value sets the start time.</span></span> <span data-ttu-id="22632-160">从结束时间起最长为 12 小时。</span><span class="sxs-lookup"><span data-stu-id="22632-160">There is a 12-hour maximum from end time.</span></span>
    -   <span data-ttu-id="22632-161">支持的值为 0-23，其中 0 为中午 12 点，1 为凌晨 1 点，依此类推。</span><span class="sxs-lookup"><span data-stu-id="22632-161">Supported values are 0-23, where 0 is 12 AM, 1 is 1 AM, etc.</span></span>
    -   <span data-ttu-id="22632-162">默认值为 8（早上 8 点）。</span><span class="sxs-lookup"><span data-stu-id="22632-162">The default value is 8 (8 AM).</span></span>

#### <a name="for-devices-that-run-windows-10-version-1607-only"></a><span data-ttu-id="22632-163">只针对运行 Windows 10 1607 版本的设备</span><span class="sxs-lookup"><span data-stu-id="22632-163">For devices that run Windows 10, version 1607 only</span></span>

<span data-ttu-id="22632-164">可以使用以下更新策略配置设备从 Windows Server Update Services (WSUS) 而非从 Windows 更新获取更新：</span><span class="sxs-lookup"><span data-stu-id="22632-164">You can use the following update policies to configure devices to get updates from Windows Server Update Service (WSUS), instead of from Windows Update:</span></span>

- [<span data-ttu-id="22632-165">Update/AllowUpdateService</span><span class="sxs-lookup"><span data-stu-id="22632-165">Update/AllowUpdateService</span></span>](/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)
- [<span data-ttu-id="22632-166">Update/RequireUpdateApproval</span><span class="sxs-lookup"><span data-stu-id="22632-166">Update/RequireUpdateApproval</span></span>](/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)
- [<span data-ttu-id="22632-167">Update/UpdateServiceUrl</span><span class="sxs-lookup"><span data-stu-id="22632-167">Update/UpdateServiceUrl</span></span>](/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

### <a name="plan-and-configure-update-rollouts-for-hololens-2"></a><span data-ttu-id="22632-168">规划和配置 HoloLens 2 更新推出</span><span class="sxs-lookup"><span data-stu-id="22632-168">Plan and configure update rollouts for HoloLens 2</span></span>

<span data-ttu-id="22632-169">相比 HoloLens（第一代），HoloLens 2 支持更多自动化更新功能。</span><span class="sxs-lookup"><span data-stu-id="22632-169">HoloLens 2 supports more update automation features than HoloLens (1st gen) does.</span></span> <span data-ttu-id="22632-170">如果你使用 Microsoft Intune 来管理适用于企业的 Windows 更新策略，尤其如此。</span><span class="sxs-lookup"><span data-stu-id="22632-170">This is especially true if you use Microsoft Intune to manage Windows Update for Business policies.</span></span> <span data-ttu-id="22632-171">借助这些功能，可更轻松地规划和部署整个组织的更新。</span><span class="sxs-lookup"><span data-stu-id="22632-171">These features make it easier for you to plan and implement update rollouts across your organization.</span></span>

#### <a name="plan-the-update-strategy"></a><span data-ttu-id="22632-172">规划更新策略</span><span class="sxs-lookup"><span data-stu-id="22632-172">Plan the update strategy</span></span>

<span data-ttu-id="22632-173">适用于企业的 Windows 更新支持延期策略。</span><span class="sxs-lookup"><span data-stu-id="22632-173">Windows Updates for Business supports deferral policies.</span></span> <span data-ttu-id="22632-174">Microsoft 发布更新后，你可以使用延期策略定义在设备上等待多久后安装该更新。</span><span class="sxs-lookup"><span data-stu-id="22632-174">After Microsoft releases an update, you can use a deferral policy to define how long to wait before installing that update on devices.</span></span> <span data-ttu-id="22632-175">通过将设备子集（即“更新通道”）与不同的延期策略相关联，可协调组织的更新推出策略。</span><span class="sxs-lookup"><span data-stu-id="22632-175">By associating subsets of your devices (also known as *update rings*) with different deferral policies, you can coordinate an update rollout strategy for your organization.</span></span>

<span data-ttu-id="22632-176">例如，假设某个组织拥有 1,000 台设备，并且必须通过 5 种方式更新设备。</span><span class="sxs-lookup"><span data-stu-id="22632-176">For example, consider an organization that has 1,000 devices, and has to update the devices in five waves.</span></span> <span data-ttu-id="22632-177">该组织可按下表所示，创建 5 个更新通道。</span><span class="sxs-lookup"><span data-stu-id="22632-177">The organization can create five update rings, as shown in the following table.</span></span>

|<span data-ttu-id="22632-178">Group</span><span class="sxs-lookup"><span data-stu-id="22632-178">Group</span></span> |<span data-ttu-id="22632-179">设备数</span><span class="sxs-lookup"><span data-stu-id="22632-179">Number of devices</span></span> |<span data-ttu-id="22632-180">延期（天数）</span><span class="sxs-lookup"><span data-stu-id="22632-180">Deferral (days)</span></span> |
| ---| :---: | :---: |
|<span data-ttu-id="22632-181">组 1（IT 人员）</span><span class="sxs-lookup"><span data-stu-id="22632-181">Grp 1 (IT staff)</span></span> |<span data-ttu-id="22632-182">5</span><span class="sxs-lookup"><span data-stu-id="22632-182">5</span></span> |<span data-ttu-id="22632-183">0</span><span class="sxs-lookup"><span data-stu-id="22632-183">0</span></span> |
|<span data-ttu-id="22632-184">组 2（早期采用者）</span><span class="sxs-lookup"><span data-stu-id="22632-184">Grp 2 (early adopters)</span></span> |<span data-ttu-id="22632-185">50</span><span class="sxs-lookup"><span data-stu-id="22632-185">50</span></span> |<span data-ttu-id="22632-186">60</span><span class="sxs-lookup"><span data-stu-id="22632-186">60</span></span> |
|<span data-ttu-id="22632-187">组 3（主要设备 1）</span><span class="sxs-lookup"><span data-stu-id="22632-187">Grp 3 (main 1)</span></span> |<span data-ttu-id="22632-188">250</span><span class="sxs-lookup"><span data-stu-id="22632-188">250</span></span> |<span data-ttu-id="22632-189">120</span><span class="sxs-lookup"><span data-stu-id="22632-189">120</span></span> |
|<span data-ttu-id="22632-190">组 4（主要设备 2）</span><span class="sxs-lookup"><span data-stu-id="22632-190">Grp 4 (main 2)</span></span> |<span data-ttu-id="22632-191">300</span><span class="sxs-lookup"><span data-stu-id="22632-191">300</span></span> |<span data-ttu-id="22632-192">150</span><span class="sxs-lookup"><span data-stu-id="22632-192">150</span></span> |
|<span data-ttu-id="22632-193">组 5（主要设备 3）</span><span class="sxs-lookup"><span data-stu-id="22632-193">Grp 5 (main 3)</span></span> |<span data-ttu-id="22632-194">395</span><span class="sxs-lookup"><span data-stu-id="22632-194">395</span></span> |<span data-ttu-id="22632-195">180</span><span class="sxs-lookup"><span data-stu-id="22632-195">180</span></span> |

<span data-ttu-id="22632-196">随着时间推移，整个组织将按照此过程推出更新。</span><span class="sxs-lookup"><span data-stu-id="22632-196">Here's how the rollout progresses over time to the whole organization.</span></span>

![更新部署日程表](./images/hololens-updates-timeline.png)

#### <a name="configure-an-update-deferral-policy"></a><span data-ttu-id="22632-198">配置更新延期策略</span><span class="sxs-lookup"><span data-stu-id="22632-198">Configure an update deferral policy</span></span>

<span data-ttu-id="22632-199">延期策略指定可用更新日期和向设备提供更新日期之间间隔的天数。</span><span class="sxs-lookup"><span data-stu-id="22632-199">A deferral policy specifies the number of days between the date on which an update becomes available and the date on which the update is offered to a device.</span></span>

<span data-ttu-id="22632-200">可为功能更新和质量更新配置不同的延期天数。</span><span class="sxs-lookup"><span data-stu-id="22632-200">You can configure different deferrals for feature updates and quality updates.</span></span> <span data-ttu-id="22632-201">下表列出了每种类型要使用的具体策略及每个类型最多可以延期的天数。</span><span class="sxs-lookup"><span data-stu-id="22632-201">The following table lists the specific policies to use for each type, and the maximum deferral for each.</span></span>

|<span data-ttu-id="22632-202">类别</span><span class="sxs-lookup"><span data-stu-id="22632-202">Category</span></span> |<span data-ttu-id="22632-203">策略</span><span class="sxs-lookup"><span data-stu-id="22632-203">Policy</span></span> |<span data-ttu-id="22632-204">最大延迟</span><span class="sxs-lookup"><span data-stu-id="22632-204">Maximum deferral</span></span> |
| --- | --- | --- |
|<span data-ttu-id="22632-205">功能更新</span><span class="sxs-lookup"><span data-stu-id="22632-205">Feature updates</span></span> |<span data-ttu-id="22632-206">DeferFeatureUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="22632-206">DeferFeatureUpdatesPeriodInDays</span></span> |<span data-ttu-id="22632-207">365 天</span><span class="sxs-lookup"><span data-stu-id="22632-207">365 days</span></span> |
|<span data-ttu-id="22632-208">质量更新</span><span class="sxs-lookup"><span data-stu-id="22632-208">Quality updates</span></span> |<span data-ttu-id="22632-209">DeferQualityUpdatesPeriodInDays</span><span class="sxs-lookup"><span data-stu-id="22632-209">DeferQualityUpdatesPeriodInDays</span></span> |<span data-ttu-id="22632-210">30 天</span><span class="sxs-lookup"><span data-stu-id="22632-210">30 days</span></span> |

#### <a name="pause-updates-via-device"></a><span data-ttu-id="22632-211">通过设备暂停更新</span><span class="sxs-lookup"><span data-stu-id="22632-211">Pause Updates via Device</span></span>

<span data-ttu-id="22632-212">如果用户无权访问 MDM，则他们可以在包含内部版本 [Windows 全息版 2004](hololens-release-notes.md#windows-holographic-version-2004) 或更高版本的 HoloLens 2 设备上分别手动暂停更新长达 35 天。</span><span class="sxs-lookup"><span data-stu-id="22632-212">If a user does not have access to MDM they can individually Pause updates for up to 35 days manually on a HoloLens 2 device on build [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) or later.</span></span> <span data-ttu-id="22632-213">用户可以通过导航至“设置”>“更新和安全”>“高级选项”并滚动至“暂停更新”，选择将暂停更新的结束日期，来实现此设置。</span><span class="sxs-lookup"><span data-stu-id="22632-213">Users can reach this setting by navigating to **Settings > Update & Security > Advanced options** scroll down to **Pause updates** and select the date until which they will pause updates.</span></span> <span data-ttu-id="22632-214">用户达到暂停限制后，设备将需要获取新的更新，然后它们才能再次暂停。</span><span class="sxs-lookup"><span data-stu-id="22632-214">Once a user reached the pause limit, the device will need to get new updates before they can pause again.</span></span> 

<span data-ttu-id="22632-215">从 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 开始，可以为 HoloLens 2 设备管理此暂停更新功能。</span><span class="sxs-lookup"><span data-stu-id="22632-215">Starting with [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2), this pause updates function can be managed for HoloLens 2 devices.</span></span> 
- <span data-ttu-id="22632-216">[Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)。</span><span class="sxs-lookup"><span data-stu-id="22632-216">[Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess).</span></span>
    - <span data-ttu-id="22632-217">0（默认值）– 已启用</span><span class="sxs-lookup"><span data-stu-id="22632-217">0 (default) – Enabled</span></span>
    - <span data-ttu-id="22632-218">1 – 已禁用</span><span class="sxs-lookup"><span data-stu-id="22632-218">1 – Disabled</span></span>

#### <a name="intune-update-management-functions-that-hololens-supports"></a><span data-ttu-id="22632-219">HoloLens 支持的 Intune 更新管理功能</span><span class="sxs-lookup"><span data-stu-id="22632-219">Intune update management functions that HoloLens supports</span></span>

<span data-ttu-id="22632-220">可使用下列 Intune 更新管理功能来管理 HoloLens 更新。</span><span class="sxs-lookup"><span data-stu-id="22632-220">You can use the following Intune update management functions to manage updates for HoloLens.</span></span>

- <span data-ttu-id="22632-221">创建和分配：这些功能将 Windows 10 更新通道添加到更新通道列表中。</span><span class="sxs-lookup"><span data-stu-id="22632-221">**Create** and **Assign**: These functions add a Windows 10 update ring to the list of update rings.</span></span> <span data-ttu-id="22632-222">有关详细信息，请参阅[创建和分配更新通道](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)。</span><span class="sxs-lookup"><span data-stu-id="22632-222">For more information, see [Create and assign update rings](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings).</span></span>

- <span data-ttu-id="22632-223">暂停：如果部署功能或质量更新时遇到问题，可暂停更新 35 天（从指定日期开始计算）。</span><span class="sxs-lookup"><span data-stu-id="22632-223">**Pause**: If you encounter a problem when you deploy a feature or quality update, you can pause the update for 35 days (starting from a specified date).</span></span> <span data-ttu-id="22632-224">暂停后会阻止其他设备安装更新，直至你解决或缓解该问题。</span><span class="sxs-lookup"><span data-stu-id="22632-224">This pause prevents other devices from installing the update until you resolve or mitigate the problem.</span></span> <span data-ttu-id="22632-225">即使暂停功能更新，仍会向设备提供质量更新以确保它们保持安全。</span><span class="sxs-lookup"><span data-stu-id="22632-225">If you pause a feature update, quality updates are still offered to devices to make sure that they stay secure.</span></span> <span data-ttu-id="22632-226">暂停更新类型后，该通道的“概述”窗格将显示该更新类型恢复之前剩余的天数。</span><span class="sxs-lookup"><span data-stu-id="22632-226">When an update type is paused, the Overview pane for that ring displays how many days remain before that update type resumes.</span></span> <span data-ttu-id="22632-227">指定时间过后，暂停将自动过期，并继续更新进程。</span><span class="sxs-lookup"><span data-stu-id="22632-227">After the specified time has passed, the pause automatically expires, and the update process resumes.</span></span>

  <span data-ttu-id="22632-228">暂停更新通道时，可选择以下任一选项：</span><span class="sxs-lookup"><span data-stu-id="22632-228">While the update ring is paused, you can select either of the following options:</span></span>

  - <span data-ttu-id="22632-229">延长：延长更新类型暂停期限 35 天。</span><span class="sxs-lookup"><span data-stu-id="22632-229">**Extend**: Extend the pause period for an update type for 35 days.</span></span>
  - <span data-ttu-id="22632-230">恢复：将该通道的更新还原为活动操作。</span><span class="sxs-lookup"><span data-stu-id="22632-230">**Resume**: Restore updates for that ring to active operation.</span></span> <span data-ttu-id="22632-231">如果有必要，可以再次暂停更新通道。</span><span class="sxs-lookup"><span data-stu-id="22632-231">You can pause the update ring again, if it is necessary.</span></span>

  > [!NOTE]  
  > <span data-ttu-id="22632-232">HoloLens 2 设备不支持更新通道的“卸载”操作。</span><span class="sxs-lookup"><span data-stu-id="22632-232">The **Uninstall** operation for update rings is not supported for HoloLens 2 devices.</span></span>

### <a name="delivery-optimization-preview"></a><span data-ttu-id="22632-233">传递优化预览版</span><span class="sxs-lookup"><span data-stu-id="22632-233">Delivery Optimization Preview</span></span>

<span data-ttu-id="22632-234">[Windows 全息版 21H1](hololens-release-notes.md#windows-holographic-version-21h1) 已启用传递优化设置的早期预览版，以减少从多个 HoloLens 设备下载的带宽消耗。</span><span class="sxs-lookup"><span data-stu-id="22632-234">[Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) has enabled an early preview for delivery optimization settings to reduce bandwidth consumption for downloads from multiple HoloLens devices.</span></span> <span data-ttu-id="22632-235">此处提供了此功能的更完整说明以及建议的网络配置：[Windows 10 更新的传递优化](/windows/deployment/update/waas-delivery-optimization)。</span><span class="sxs-lookup"><span data-stu-id="22632-235">A fuller description of this functionality along with the recommended network configuration is available here: [Delivery Optimization for Windows 10 updates](/windows/deployment/update/waas-delivery-optimization).</span></span>

<span data-ttu-id="22632-236">以下设置作为管理图面的一部分启用，并且[可以从 Intune 进行配置](/mem/intune/configuration/delivery-optimization-settings)：</span><span class="sxs-lookup"><span data-stu-id="22632-236">The following settings are enabled as part of the management surface and [can be configured from Intune](/mem/intune/configuration/delivery-optimization-settings):</span></span>

- [<span data-ttu-id="22632-237">DOCacheHost</span><span class="sxs-lookup"><span data-stu-id="22632-237">DOCacheHost</span></span>](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [<span data-ttu-id="22632-238">DOCacheHostSource</span><span class="sxs-lookup"><span data-stu-id="22632-238">DOCacheHostSource</span></span>](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [<span data-ttu-id="22632-239">DODelayCacheServerFallbackBackground</span><span class="sxs-lookup"><span data-stu-id="22632-239">DODelayCacheServerFallbackBackground</span></span>](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [<span data-ttu-id="22632-240">DODelayCacheServerFallbackForeground</span><span class="sxs-lookup"><span data-stu-id="22632-240">DODelayCacheServerFallbackForeground</span></span>](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [<span data-ttu-id="22632-241">DODownloadMode</span><span class="sxs-lookup"><span data-stu-id="22632-241">DODownloadMode</span></span>](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [<span data-ttu-id="22632-242">DOMaxBackgroundDownloadBandwidth</span><span class="sxs-lookup"><span data-stu-id="22632-242">DOMaxBackgroundDownloadBandwidth</span></span>](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [<span data-ttu-id="22632-243">DOMaxForegroundDownloadBandwidth</span><span class="sxs-lookup"><span data-stu-id="22632-243">DOMaxForegroundDownloadBandwidth</span></span>](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [<span data-ttu-id="22632-244">DOPercentageMaxBackgroundBandwidth</span><span class="sxs-lookup"><span data-stu-id="22632-244">DOPercentageMaxBackgroundBandwidth</span></span>](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [<span data-ttu-id="22632-245">DOPercentageMaxForegroundBandwidth</span><span class="sxs-lookup"><span data-stu-id="22632-245">DOPercentageMaxForegroundBandwidth</span></span>](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [<span data-ttu-id="22632-246">DOSetHoursToLimitForegroundDownloadBandwidth</span><span class="sxs-lookup"><span data-stu-id="22632-246">DOSetHoursToLimitForegroundDownloadBandwidth</span></span>](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [<span data-ttu-id="22632-247">DOSetHoursToLimitBackgroundDownloadBandwidth</span><span class="sxs-lookup"><span data-stu-id="22632-247">DOSetHoursToLimitBackgroundDownloadBandwidth</span></span>](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

<span data-ttu-id="22632-248">有关此预览版产品/服务的一些注意事项：</span><span class="sxs-lookup"><span data-stu-id="22632-248">A few caveats about this preview offering:</span></span>

- <span data-ttu-id="22632-249">此预览版中的 HoloLens 支持仅限于 OS 更新。</span><span class="sxs-lookup"><span data-stu-id="22632-249">HoloLens support is limited in this preview to OS updates only.</span></span>
- <span data-ttu-id="22632-250">Windows Holographic for Business 仅支持 HTTP 下载模式并从 [Microsoft 联网缓存终结点](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)进行下载；目前，HoloLens 设备不支持对等下载模式和组分配。</span><span class="sxs-lookup"><span data-stu-id="22632-250">Windows Holographic for Business only supports HTTP download modes and downloads from a [Microsoft Connected Cache endpoint](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); peer-to-peer download modes and group assignments are not supported for HoloLens devices at this time.</span></span>
- <span data-ttu-id="22632-251">HoloLens 不支持 Windows Server Update Services 终结点的部署或传递优化。</span><span class="sxs-lookup"><span data-stu-id="22632-251">HoloLens does not support deployment or delivery optimization for Windows Server Update Services endpoints.</span></span>
- <span data-ttu-id="22632-252">故障排除将需要对联网缓存服务器进行诊断，或通过“设置” > “更新和安全” >  “故障排除” >  “Windows 更新”在 HoloLens 上收集跟踪。</span><span class="sxs-lookup"><span data-stu-id="22632-252">Troubleshooting will require either diagnostics on the Connected Cache server or collecting a trace on HoloLens on HoloLens via **Settings** > **Update & Security** >  **Troubleshooting** >  **Windows Update**.</span></span>

## <a name="manually-check-for-updates"></a><span data-ttu-id="22632-253">手动检查更新</span><span class="sxs-lookup"><span data-stu-id="22632-253">Manually check for updates</span></span>

<span data-ttu-id="22632-254">虽然 HoloLens 会定期检查系统更新，但在某些情况下，仍可能需要手动检查。</span><span class="sxs-lookup"><span data-stu-id="22632-254">Although HoloLens periodically checks for system updates, there may be circumstances in which you want to manually check.</span></span>

<span data-ttu-id="22632-255">若要手动检查更新，请转到“更新” > “更新和安全” > “检查更新”。</span><span class="sxs-lookup"><span data-stu-id="22632-255">To manually check for updates, go to **Settings** > **Update & Security** > **Check for updates**.</span></span> <span data-ttu-id="22632-256">如果“设置”应用指示你的设备已是最新版本，则表示你已安装所有可用更新。</span><span class="sxs-lookup"><span data-stu-id="22632-256">If the Settings app indicates that your device is up to date, you have all the updates that are currently available.</span></span>

## <a name="manually-roll-back-an-update"></a><span data-ttu-id="22632-257">手动回滚更新</span><span class="sxs-lookup"><span data-stu-id="22632-257">Manually roll back an update</span></span>

<span data-ttu-id="22632-258">在某些情况下，你可能想要还原到 HoloLens 软件的早期版本。</span><span class="sxs-lookup"><span data-stu-id="22632-258">In some cases, you might want to revert to a previous version of the HoloLens software.</span></span> <span data-ttu-id="22632-259">根据使用的是 HoloLens 2 还是 HoloLens（第一代），选择以下对应的操作流程。</span><span class="sxs-lookup"><span data-stu-id="22632-259">The process for doing this depends on whether you are using HoloLens 2 or HoloLens (1st gen).</span></span>

### <a name="revert-to-a-previous-version-hololens-2"></a><span data-ttu-id="22632-260">还原到早期版本 (HoloLens 2)</span><span class="sxs-lookup"><span data-stu-id="22632-260">Revert to a previous version (HoloLens 2)</span></span>

<span data-ttu-id="22632-261">可使用 [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 将 HoloLens 重置为早期版本，以实现回滚并返回到 HoloLens 2 的早期版本。</span><span class="sxs-lookup"><span data-stu-id="22632-261">You can roll back updates and return to a previous version of HoloLens 2 by using the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="22632-262">还原到早期版本会删除你的个人文件和设置。</span><span class="sxs-lookup"><span data-stu-id="22632-262">Reverting to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="22632-263">若要还原到 HoloLens 2 的早期版本，请按照如下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="22632-263">To revert to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="22632-264">请确保你没有任何手机或 Windows 设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="22632-264">Make sure that you don't have any phones or Windows devices plugged in to your computer.</span></span>
1. <span data-ttu-id="22632-265">在计算机上，从 Microsoft Store 下载 [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)。</span><span class="sxs-lookup"><span data-stu-id="22632-265">On your computer, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="22632-266">下载[最新的 HoloLens 2 版本](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="22632-266">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="22632-267">完成这些下载后，打开“文件资源管理器” > “下载”，右键单击刚才下载的压缩 (.zip) 文件夹，然后选择“全部解压缩” > “解压缩”以展开该文件。</span><span class="sxs-lookup"><span data-stu-id="22632-267">After these downloads finish, open **File explorer** > **Downloads**, right-click the compressed (.zip) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="22632-268">使用 USB-A 到 USB-C 数据线将 HoloLens 设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="22632-268">Use a USB-A to USB-C cable to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="22632-269">即使你在连接 HoloLens 时一直使用的是其他数据线，但此数据线的使用效果更好。</span><span class="sxs-lookup"><span data-stu-id="22632-269">Even if you've been using other cables to connect your HoloLens, this kind of cable works best.</span></span>
1. <span data-ttu-id="22632-270">“Advanced Recovery Companion”会自动检测到 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="22632-270">The Advanced Recovery Companion automatically detects your HoloLens device.</span></span> <span data-ttu-id="22632-271">选择“Microsoft HoloLens”磁贴。</span><span class="sxs-lookup"><span data-stu-id="22632-271">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="22632-272">在下一个屏幕中，选择“手动包选择”，然后打开先前展开的文件夹。</span><span class="sxs-lookup"><span data-stu-id="22632-272">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span>
1. <span data-ttu-id="22632-273">选择安装 (.ffu) 文件。</span><span class="sxs-lookup"><span data-stu-id="22632-273">Select the installation (.ffu) file.</span></span>
1. <span data-ttu-id="22632-274">选择“安装软件”，然后按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="22632-274">Select **Install software**, and then follow the instructions.</span></span>

### <a name="revert-to-a-previous-version-hololens-1st-gen"></a><span data-ttu-id="22632-275">还原到早期版本（HoloLens (第一代)）</span><span class="sxs-lookup"><span data-stu-id="22632-275">Revert to a previous version (HoloLens (1st gen))</span></span>

<span data-ttu-id="22632-276">可使用 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) 将 HoloLens 重置为早期版本，以实现回滚并返回到 HoloLens（第一代）的早期版本。</span><span class="sxs-lookup"><span data-stu-id="22632-276">You can roll back updates and return to a previous version of HoloLens (1st gen) by using the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379) to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="22632-277">还原到 HoloLens 早期版本会删除你的个人文件和设置。</span><span class="sxs-lookup"><span data-stu-id="22632-277">Reverting to an earlier HoloLens version deletes your personal files and settings.</span></span>

<span data-ttu-id="22632-278">要还原到 HoloLens（第一代）的早期版本，请按照如下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="22632-278">To revert to a previous version of HoloLens (1st gen), follow these steps:</span></span>

1. <span data-ttu-id="22632-279">请确保你没有任何手机或 Windows 设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="22632-279">Make sure that you don't have any phones or Windows devices plugged into your computer.</span></span>
1. <span data-ttu-id="22632-280">在计算机上，下载 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)。</span><span class="sxs-lookup"><span data-stu-id="22632-280">On your computer, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="22632-281">下载 [HoloLens 周年更新恢复包](https://aka.ms/hololensrecovery)。</span><span class="sxs-lookup"><span data-stu-id="22632-281">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="22632-282">完成这些下载后，打开“文件资源管理器” > “下载”，右键单击刚才下载的压缩 (.zip) 文件夹，然后选择“全部解压缩” > “解压缩”以展开该文件。</span><span class="sxs-lookup"><span data-stu-id="22632-282">After the downloads finish, open **File explorer** > **Downloads**, right-click the compressed (.zip) folder that you just downloaded, and then select **Extract all** > **Extract** to expand the file.</span></span>
1. <span data-ttu-id="22632-283">使用与 HoloLens 设备随附的 micro-USB 数据线将 HoloLens 设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="22632-283">Use the micro-USB cable that was provided together with your HoloLens device to connect your HoloLens device to your computer.</span></span> <span data-ttu-id="22632-284">即使你在连接 HoloLens 时一直使用的是其他数据线，但原厂数据线的使用效果更好。</span><span class="sxs-lookup"><span data-stu-id="22632-284">Even if you've been using other cables to connect your HoloLens device, this one works best.</span></span>
1. <span data-ttu-id="22632-285">WDRT 会自动检测到 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="22632-285">The WDRT automatically detects your HoloLens device.</span></span> <span data-ttu-id="22632-286">选择“Microsoft HoloLens”磁贴。</span><span class="sxs-lookup"><span data-stu-id="22632-286">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="22632-287">在下一个屏幕中，选择“手动包选择”，然后打开先前展开的文件夹。</span><span class="sxs-lookup"><span data-stu-id="22632-287">On the next screen, select **Manual package selection**, and then open the folder that you previously expanded.</span></span>
1. <span data-ttu-id="22632-288">选择安装 (.ffu) 文件。</span><span class="sxs-lookup"><span data-stu-id="22632-288">Select the installation (.ffu) file.</span></span>
1. <span data-ttu-id="22632-289">选择“安装软件”，然后按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="22632-289">Select **Install software**, and then follow the instructions.</span></span>

<span data-ttu-id="22632-290">如果 WDRT 未检测到你的设备</span><span class="sxs-lookup"><span data-stu-id="22632-290">**If WDRT doesn't detect your device**</span></span>

<span data-ttu-id="22632-291">如果 WDRT 未检测到 HoloLens 设备，请尝试重启电脑。</span><span class="sxs-lookup"><span data-stu-id="22632-291">If WDRT doesn't detect your HoloLens device, try restarting your computer.</span></span> <span data-ttu-id="22632-292">如果重启不起作用，请选择“未检测到我的设备”，选择“Microsoft HoloLens”，然后按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="22632-292">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="related-articles"></a><span data-ttu-id="22632-293">相关文章</span><span class="sxs-lookup"><span data-stu-id="22632-293">Related articles</span></span>

- [<span data-ttu-id="22632-294">HoloLens 2 发行说明</span><span class="sxs-lookup"><span data-stu-id="22632-294">HoloLens 2 release notes</span></span>](hololens-release-notes.md)
- [<span data-ttu-id="22632-295">什么是适用于企业的 Windows 更新？</span><span class="sxs-lookup"><span data-stu-id="22632-295">What is Windows Update for Business?</span></span>](/windows/deployment/update/waas-manage-updates-wufb)
- [<span data-ttu-id="22632-296">将设备分配给 Windows 10 更新的服务分支</span><span class="sxs-lookup"><span data-stu-id="22632-296">Assign devices to servicing channels for Windows 10 updates</span></span>](/windows/deployment/update/waas-servicing-channels-windows-10-updates)
- [<span data-ttu-id="22632-297">在 Intune 中管理 Windows 10 软件更新</span><span class="sxs-lookup"><span data-stu-id="22632-297">Manage Windows 10 software updates in Intune</span></span>](/mem/intune/protect/windows-update-for-business-configure)
