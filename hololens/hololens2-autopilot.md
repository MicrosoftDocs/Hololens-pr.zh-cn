---
title: 适用于 HoloLens 2 的 Windows Autopilot
description: 如何在 HoloLens 2 设备上设置 Autopilot。
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: 5090a433b3d06e92cd36bdadbfbae3758432bb41
ms.sourcegitcommit: 8656379a4871e118b9e06e72eab1dbcc8eb3cd42
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182443"
---
# <span data-ttu-id="047a9-104">适用于 HoloLens 2 的 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="047a9-104">Windows Autopilot for HoloLens 2</span></span>

<span data-ttu-id="047a9-105">从 Windows 全息版 2004 版本开始，HoloLens 2 支持 Windows Autopilot [自部署模式](https://docs.microsoft.com/mem/autopilot/self-deploying)。</span><span class="sxs-lookup"><span data-stu-id="047a9-105">Starting with Windows Holographic version 2004, HoloLens 2 supports Windows Autopilot [Self-Deploying Mode](https://docs.microsoft.com/mem/autopilot/self-deploying).</span></span> <span data-ttu-id="047a9-106">管理员可在 Microsoft 终结点管理器中配置（OOBE）的全新体验，并允许终端用户在几乎未有交互的情况中为业务使用准备设备。</span><span class="sxs-lookup"><span data-stu-id="047a9-106">Administrators can configure the out-of-box experience (OOBE) in Microsoft Endpoint Manager and enable end-users to prepare devices for business use with little to no interaction.</span></span> <span data-ttu-id="047a9-107">这减少了库存管理的开销、设备准备的成本以及员工在设置体验期间的支持电话。</span><span class="sxs-lookup"><span data-stu-id="047a9-107">This reduces inventory management overhead, cost of hands-on device preparation and support calls from employees during the setup experience.</span></span> <span data-ttu-id="047a9-108">若要了解更多有关 Windows Autopilot 的详细信息，请单击 [此处](https://docs.microsoft.com/mem/autopilot/windows-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="047a9-108">To learn more about Windows Autopilot, click [here](https://docs.microsoft.com/mem/autopilot/windows-autopilot).</span></span>

<span data-ttu-id="047a9-109">与 Surface 设备一样，建议客户使用其 Microsoft [云解决方案提供商](https://partner.microsoft.com/cloud-solution-provider) (经销商或分销商) ，以通过合作伙伴中心将设备注册到 Autopilot 服务中。</span><span class="sxs-lookup"><span data-stu-id="047a9-109">Like for Surface devices, it is recommended that customers work with their Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (reseller or distributor) to get devices registered with the Autopilot service through Partner Center.</span></span> <span data-ttu-id="047a9-110">[此处](https://docs.microsoft.com/mem/autopilot/add-devices)概述了设备注册的其他方法，尽管利用 Microsoft 的渠道合作伙伴可确保最有效的端到端路径。</span><span class="sxs-lookup"><span data-stu-id="047a9-110">Other methods for device registration are outlined [here](https://docs.microsoft.com/mem/autopilot/add-devices), though leveraging Microsoft's channel partners ensures the most effective end-to-end path.</span></span> 

> [!NOTE]
> <span data-ttu-id="047a9-111">截至11/20/2020，Microsoft 终结点管理器中 HoloLens 的 Autopilot 配置正在到 **公共预览版**。</span><span class="sxs-lookup"><span data-stu-id="047a9-111">As of 11/20/2020 Autopilot configuration for HoloLens in Microsoft Endpoint Manager is transitioning to **Public Preview**.</span></span> <span data-ttu-id="047a9-112">客户无需再注册私人预览，所有租户都可在 MEM 管理中心中设置 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="047a9-112">Customers no longer need to enroll in the private preview and all tenants will be able to setup Autopilot in the MEM admin center.</span></span>

<span data-ttu-id="047a9-113">当用户启动 Autopilot 自部署过程时，Autopilot 会完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="047a9-113">When a user starts the Autopilot self-deploying process, Autopilot completes the following steps:</span></span>

1. <span data-ttu-id="047a9-114">将设备加入 Azure Active Directory （Azure AD）。</span><span class="sxs-lookup"><span data-stu-id="047a9-114">Join the device to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="047a9-115">请注意，Autopilot for HoloLens 不支持可用目录联接或混合 Azure AD 联接。</span><span class="sxs-lookup"><span data-stu-id="047a9-115">Note that Autopilot for HoloLens does not support Active Directory join or Hybrid Azure AD join.</span></span>
   
1. <span data-ttu-id="047a9-116">使用 Azure AD 将设备注册到 Microsoft 终结点管理器（或其他 MDM 服务）中。</span><span class="sxs-lookup"><span data-stu-id="047a9-116">Use Azure AD to enroll the device in Microsoft Endpoint Manager (or another MDM service).</span></span>

1. <span data-ttu-id="047a9-117">下载并应用针对设备的策略、证书、网络配置文件和应用程序。</span><span class="sxs-lookup"><span data-stu-id="047a9-117">Download and apply device-targeted policies, certificates, networking profiles and applications.</span></span>

1. <span data-ttu-id="047a9-118">预配设备。</span><span class="sxs-lookup"><span data-stu-id="047a9-118">Provision the device.</span></span>

1. <span data-ttu-id="047a9-119">向用户呈现登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="047a9-119">Present the sign-in screen to the user.</span></span>


## <span data-ttu-id="047a9-120">为 HoloLens 2 配置 Autopilot</span><span class="sxs-lookup"><span data-stu-id="047a9-120">Configuring Autopilot for HoloLens 2</span></span>

<span data-ttu-id="047a9-121">请按照以下步骤设置你的环境：</span><span class="sxs-lookup"><span data-stu-id="047a9-121">Please follow the steps below to set up your environment:</span></span>

1. [<span data-ttu-id="047a9-122">查看 HoloLens 2 的 Windows Autopilot 要求。</span><span class="sxs-lookup"><span data-stu-id="047a9-122">Review requirements for Windows Autopilot for HoloLens 2.</span></span>](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [<span data-ttu-id="047a9-123">在 Windows Autopilot 注册设备。</span><span class="sxs-lookup"><span data-stu-id="047a9-123">Register devices in Windows Autopilot.</span></span>](#2-register-devices-in-windows-autopilot)

1. [<span data-ttu-id="047a9-124">创建设备组。</span><span class="sxs-lookup"><span data-stu-id="047a9-124">Create a device group.</span></span>](#3-create-a-device-group)

1. [<span data-ttu-id="047a9-125">创建部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="047a9-125">Create a deployment profile.</span></span>](#4-create-a-deployment-profile)

1. [<span data-ttu-id="047a9-126">验证注册状态页面（ESP）配置。</span><span class="sxs-lookup"><span data-stu-id="047a9-126">Verify the Enrollment Status Page (ESP) configuration.</span></span>](#5-verify-the-esp-configuration)

1. [<span data-ttu-id="047a9-127">验证 HoloLens 设备的配置文件状态。</span><span class="sxs-lookup"><span data-stu-id="047a9-127">Verify the profile status of the HoloLens devices.</span></span>](#6-verify-the-profile-status-of-the-hololens-devices)


#### <span data-ttu-id="047a9-128">1. 查看适用于 HoloLens 2 的 Windows Autopilot 的要求</span><span class="sxs-lookup"><span data-stu-id="047a9-128">1. Review requirements for Windows Autopilot for HoloLens 2</span></span>

**<span data-ttu-id="047a9-129">参阅 Windows Autopilot 要求文章的以下部分：</span><span class="sxs-lookup"><span data-stu-id="047a9-129">Review the following sections of the Windows Autopilot requirements article:</span></span>**

- [<span data-ttu-id="047a9-130">网络要求</span><span class="sxs-lookup"><span data-stu-id="047a9-130">Network requirements</span></span>](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [<span data-ttu-id="047a9-131">许可要求</span><span class="sxs-lookup"><span data-stu-id="047a9-131">Licensing requirements</span></span>](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [<span data-ttu-id="047a9-132">配置需求</span><span class="sxs-lookup"><span data-stu-id="047a9-132">Configuration requirements</span></span>](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

**<span data-ttu-id="047a9-133">查看 Windows Autopilo 自部署模式文章的“[要求](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)”部分。</span><span class="sxs-lookup"><span data-stu-id="047a9-133">Review the "[Requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" section of the Windows Autopilot Self-Deploying mode article.</span></span>** <span data-ttu-id="047a9-134">环境必须满足这些要求以及 Windows Autopilot 标准要求。</span><span class="sxs-lookup"><span data-stu-id="047a9-134">Your environment has to meet these requirements as well as the standard Windows Autopilot requirements.</span></span> <span data-ttu-id="047a9-135">无需查看本文的“分步操作”和“验证”部分。</span><span class="sxs-lookup"><span data-stu-id="047a9-135">You do not have to review the "Step by step" and "Validation" sections of the article.</span></span> <span data-ttu-id="047a9-136">本文后面的过程提供了特定于 HoloLens 的相应步骤。</span><span class="sxs-lookup"><span data-stu-id="047a9-136">The procedures later in this article provide corresponding steps that are specific to HoloLens.</span></span> <span data-ttu-id="047a9-137">有关如何注册设备和配置配置文件的信息，请参阅 [2. 在 Windows Autopilot 中注册设备](#2-register-devices-in-windows-autopilot) 以及 [4. 在本文中创建部署配置文件](#4-create-a-deployment-profile) 。</span><span class="sxs-lookup"><span data-stu-id="047a9-137">For information about how to register devices and configure profiles, see [2. Register devices in Windows Autopilot](#2-register-devices-in-windows-autopilot) and [4. Create a deployment profile](#4-create-a-deployment-profile) in this article.</span></span> <span data-ttu-id="047a9-138">若要配置和管理 Autopilot 自部署模式配置文件，请确保你有权访问[Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="047a9-138">To configure and manage the Autopilot self-deploying mode profiles, make sure that you have access to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>

**<span data-ttu-id="047a9-139">查看 HoloLens 操作系统要求：</span><span class="sxs-lookup"><span data-stu-id="047a9-139">Review HoloLens OS requirements:</span></span>**

- <span data-ttu-id="047a9-140">设备必须使用 [Windows 全息版，2004 版本](hololens-release-notes.md#windows-holographic-version-2004) （内部版本 19041.1103）或更高版本。</span><span class="sxs-lookup"><span data-stu-id="047a9-140">Devices must be on [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) or later.</span></span> <span data-ttu-id="047a9-141">若要确认设备上的内部版本或重新刷新到最新操作系统，可使用 [高级恢复配套（ARC）](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab)。</span><span class="sxs-lookup"><span data-stu-id="047a9-141">To confirm the build version on your device or re-flash to the latest OS, you can use the [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab).</span></span> <span data-ttu-id="047a9-142">可在 [此处](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device) 找到说明。</span><span class="sxs-lookup"><span data-stu-id="047a9-142">You can find instructions [here](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span> <span data-ttu-id="047a9-143">请注意，在 2020 年 9 月底之前交付的设备已预安装了 Windows 全息 1903 版本。</span><span class="sxs-lookup"><span data-stu-id="047a9-143">Note that devices delivered until late September 2020 have Windows Holographic version 1903 pre-installed.</span></span> <span data-ttu-id="047a9-144">请与经销商联系，以确保 Autopilot 的设备已向你发送。</span><span class="sxs-lookup"><span data-stu-id="047a9-144">Please contact your reseller to ensure that Autopilot-ready devices are shipped to you.</span></span>

- <span data-ttu-id="047a9-145">Windows 全息 2004 版本仅支持通过以太网连接的 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="047a9-145">Windows Holographic, version 2004 only supports Autopilot over ethernet connection.</span></span> <span data-ttu-id="047a9-146">**在开启 HoloLens 之前**，请确保使用 “USB-C转以太网” 适配器已连接到以太网。</span><span class="sxs-lookup"><span data-stu-id="047a9-146">Ensure the HoloLens is connected to ethernet using a "USB-C to Ethernet" adapter **before turning it on**.</span></span> <span data-ttu-id="047a9-147">设备启动后，无需用户交互。</span><span class="sxs-lookup"><span data-stu-id="047a9-147">Upon device boot no user interaction is required.</span></span> <span data-ttu-id="047a9-148">如果计划将 Autopilot 推广到许多 HoloLens 设备上，我们建议对适配器基础设施进行规划。</span><span class="sxs-lookup"><span data-stu-id="047a9-148">If you are planning for an Autopilot roll-out to many HoloLens devices, we recommend that you plan for the adapter infrastructure.</span></span> <span data-ttu-id="047a9-149">我们不推荐使用 USB 集线器，因为它们通常需要安装额外的第三方驱动程序，而 HoloLens 不支持这些驱动程序。</span><span class="sxs-lookup"><span data-stu-id="047a9-149">We do not recommend USB Hubs, as they often require additional third-party drivers to be installed which is not supported on HoloLens.</span></span> 

- <span data-ttu-id="047a9-150">[Windows 全息 20H2 版本](hololens-release-notes.md#windows-holographic-version-20h2)（内部版本 19041.1128）或更高版本通过 Wi-Fi 支持 Autopilot，尽管仍然可使用以太网适配器。 </span><span class="sxs-lookup"><span data-stu-id="047a9-150">[Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) or later support Autopilot over Wi-Fi, although you may still use ethernet adapters.</span></span> <span data-ttu-id="047a9-151">对于通过 Wi-Fi 连接的设备，用户必须仅：</span><span class="sxs-lookup"><span data-stu-id="047a9-151">For devices connected via Wi-fi, the user must only:</span></span>

     - <span data-ttu-id="047a9-152">转到 hummingbird 场景</span><span class="sxs-lookup"><span data-stu-id="047a9-152">Go through the hummingbird scene</span></span>
     - <span data-ttu-id="047a9-153">选择语言和地区</span><span class="sxs-lookup"><span data-stu-id="047a9-153">Choose the language and locale</span></span>
     - <span data-ttu-id="047a9-154">运行目视校准</span><span class="sxs-lookup"><span data-stu-id="047a9-154">Run eye-calibration</span></span>
     - <span data-ttu-id="047a9-155">建立网络连接</span><span class="sxs-lookup"><span data-stu-id="047a9-155">Establish network connection</span></span>


- <span data-ttu-id="047a9-156">Windows 全息 20H2 版本支持 [Tenantlockdown 云解决方案提供商和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)，这会将设备锁定在一个租户上，并确保在意外或故意重置或擦除的情况下，设备仍与该租户绑定。</span><span class="sxs-lookup"><span data-stu-id="047a9-156">Windows Holographic, version 20H2 supports [Tenantlockdown CSP and Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), which locks a device to a tenant and  ensures that the device remains bound to that tenant in case of accidental or intentional resets or wipes.</span></span>  

- <span data-ttu-id="047a9-157">确保设备尚未成为 Azure AD 的成员，并且未在 Intune （或其他 MDM 系统）中注册。</span><span class="sxs-lookup"><span data-stu-id="047a9-157">Ensure that the devices are not already members of Azure AD, and are not enrolled in Intune (or another MDM system).</span></span> <span data-ttu-id="047a9-158">Autopilot 自部署过程完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="047a9-158">The Autopilot self-deploying process completes these steps.</span></span> <span data-ttu-id="047a9-159">若要确保清理所有设备相关信息，请检查 Azure AD 和 Intune 门户中的“**设备**”页面。</span><span class="sxs-lookup"><span data-stu-id="047a9-159">To make sure that all the device-related information is cleaned up, check the **Devices** pages in both Azure AD and Intune Portals.</span></span> <span data-ttu-id="047a9-160">请注意，目前 HoloLens 不支持 “将所有目标设备转换为 Autopilot 功能。</span><span class="sxs-lookup"><span data-stu-id="047a9-160">Note that "Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  

### <span data-ttu-id="047a9-161">2. 在 Windows Autopilot 中注册设备</span><span class="sxs-lookup"><span data-stu-id="047a9-161">2. Register devices in Windows Autopilot</span></span>

<span data-ttu-id="047a9-162">在首次设置之前，设备必须在 Windows Autopilot 中注册。</span><span class="sxs-lookup"><span data-stu-id="047a9-162">Your devices must be registered in Windows Autopilot before first setup.</span></span> <span data-ttu-id="047a9-163">有关 MEM 的设备注册文档，请参阅 [将设备添加到 Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices)。</span><span class="sxs-lookup"><span data-stu-id="047a9-163">For MEM documentation on device registration please see [Adding devices to Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices).</span></span>  

<span data-ttu-id="047a9-164">注册 HoloLens 设备有两种主要方法：</span><span class="sxs-lookup"><span data-stu-id="047a9-164">There are two primary ways to register HoloLens devices:</span></span> 

1. **<span data-ttu-id="047a9-165">当你下订单时，经销商可在合作伙伴中心注册设备。</span><span class="sxs-lookup"><span data-stu-id="047a9-165">Reseller can register devices in the Partner Center when you place an order.</span></span>** 
 > [!NOTE]  
   > <span data-ttu-id="047a9-166">这是添加设备到 Autopilot 服务的推荐路径。</span><span class="sxs-lookup"><span data-stu-id="047a9-166">This is the recommended path for adding devices to the Autopilot service.</span></span> <span data-ttu-id="047a9-167">[了解详细信息](https://docs.microsoft.com/mem/autopilot/add-devices#reseller-distributor-or-partner-registration)。</span><span class="sxs-lookup"><span data-stu-id="047a9-167">[Learn more](https://docs.microsoft.com/mem/autopilot/add-devices#reseller-distributor-or-partner-registration).</span></span>  

   <span data-ttu-id="047a9-168">或者</span><span class="sxs-lookup"><span data-stu-id="047a9-168">or</span></span>
   
2. <span data-ttu-id="047a9-169">**检索硬件哈希（也称为硬件 ID）并在 MEM 管理中心手动注册设备**。 </span><span class="sxs-lookup"><span data-stu-id="047a9-169">**Retrieve the hardware hash (also known as the hardware ID) and register the device manually in MEM admin center**.</span></span> 

**<span data-ttu-id="047a9-170">检索硬件哈希</span><span class="sxs-lookup"><span data-stu-id="047a9-170">Retrieve hardware hash</span></span>**

<span data-ttu-id="047a9-171">设备在 OOBE 过程中，或之后当设备所有者启动诊断日志收集过程时，将其硬件哈希记录在 CSV 文件中（在以下过程中描述）。</span><span class="sxs-lookup"><span data-stu-id="047a9-171">The device records its hardware hash in a CSV file during the OOBE process, or later when a device owner starts the diagnostic log collection process (described in the following procedure).</span></span> <span data-ttu-id="047a9-172">通常情况下，设备所有者是第一个登录到设备的用户。</span><span class="sxs-lookup"><span data-stu-id="047a9-172">Typically, the device owner is the first user to sign in to the device.</span></span>

1. <span data-ttu-id="047a9-173">启动 HoloLens 2 设备。</span><span class="sxs-lookup"><span data-stu-id="047a9-173">Start the HoloLens 2 device.</span></span>

1. <span data-ttu-id="047a9-174">在设备上，同时按下 **电源** 和 **音量** 按钮，然后松开它们。</span><span class="sxs-lookup"><span data-stu-id="047a9-174">On the device, press the **Power** and **Volume Down** buttons at the same time and then release them.</span></span> <span data-ttu-id="047a9-175">设备收集诊断日志和硬件哈希，并将它们存储在一组 .zip 文件中。</span><span class="sxs-lookup"><span data-stu-id="047a9-175">The device collects diagnostic logs and the hardware hash, and stores them in a set of .zip files.</span></span> 

   1. <span data-ttu-id="047a9-176">有关完整的详细信息和如何执行此操作的说明视频，请阅读有关[脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics)的信息。</span><span class="sxs-lookup"><span data-stu-id="047a9-176">For full details and an instructional video for how to preform this please read about [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> 
   
1. <span data-ttu-id="047a9-177">使用 USB-C 电缆将设备连接到计算机。</span><span class="sxs-lookup"><span data-stu-id="047a9-177">Use a USB-C cable to connect the device to a computer.</span></span>

1. <span data-ttu-id="047a9-178">在计算机上，打开“文件资源管理器”。</span><span class="sxs-lookup"><span data-stu-id="047a9-178">On the computer, open File Explorer.</span></span> <span data-ttu-id="047a9-179">打开**此计算机 \\\<*HoloLens device name*>\\内部存储\\文档**，并定位至AutopilotDiagnostics.zip 文件。</span><span class="sxs-lookup"><span data-stu-id="047a9-179">Open **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**, and locate the AutopilotDiagnostics.zip file.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="047a9-180">.zip 文件可能不会立即可用。</span><span class="sxs-lookup"><span data-stu-id="047a9-180">The .zip file may not immediately be available.</span></span> <span data-ttu-id="047a9-181">如果该文件尚未准备好，可能会在“文档”文件夹中看到一个 HoloLensDiagnostics.temp文件。</span><span class="sxs-lookup"><span data-stu-id="047a9-181">If the file is not ready yet you may see a HoloLensDiagnostics.temp file in the Documents folder.</span></span> <span data-ttu-id="047a9-182">若要更新文件列表，请刷新窗口。</span><span class="sxs-lookup"><span data-stu-id="047a9-182">To update the list of files, refresh the window.</span></span>

1. <span data-ttu-id="047a9-183">提取 AutopilotDiagnostics.zip 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="047a9-183">Extract the contents of the AutopilotDiagnostics.zip file.</span></span>

1. <span data-ttu-id="047a9-184">在提取的文件中，找到文件名前缀为 “DeviceHash” 的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="047a9-184">In the extracted files, locate the CSV file that has a file name prefix of "DeviceHash."</span></span> <span data-ttu-id="047a9-185">将该文件复制到计算机上的驱动器上，以后可以访问它。</span><span class="sxs-lookup"><span data-stu-id="047a9-185">Copy that file to a drive on the computer where you can access it later.</span></span>  

   > [!IMPORTANT]  
   > <span data-ttu-id="047a9-186">CSV 文件中的数据应使用以下标题和行格式：</span><span class="sxs-lookup"><span data-stu-id="047a9-186">The data in the CSV file should use the following header and line format:</span></span>
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**<span data-ttu-id="047a9-187">通过 MEM 注册设备</span><span class="sxs-lookup"><span data-stu-id="047a9-187">Register device through MEM</span></span>**

1. <span data-ttu-id="047a9-188">在[Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com)中，选择\*\* 设备 \*\* > **Windows** >  **Windows 注册**设备"，然后选择**设备** > **导入**至**Windows Autopilot 部署程序**下的设备。</span><span class="sxs-lookup"><span data-stu-id="047a9-188">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment**, and then select **Devices** > **Import** under **Windows Autopilot Deployment Program**.</span></span>

1. <span data-ttu-id="047a9-189">在“**添加 Windows Autopilot 设备**”中，选择 DeviceHash CSV 文件，选择“**打开**”，然后选择“**导入**”。</span><span class="sxs-lookup"><span data-stu-id="047a9-189">Under **Add Windows Autopilot devices**, select the DeviceHash CSV file, select **Open**, and then select **Import**.</span></span>  
   
   ![使用导入命令导入硬件哈希。](./images/hololens-ap-hash-import.png)
   
1. <span data-ttu-id="047a9-191">完成导入后，选择“**设备**” > “**Windows**” > “**Windows 注册**” > “**设备**” > “**同步**”。此过程可能需要几分钟时间才能完成，具体取决于同步的设备数量。</span><span class="sxs-lookup"><span data-stu-id="047a9-191">After the import finishes, select **Devices** > **Windows** > **Windows enrollment** > **Devices** > **Sync**. The process might take a few minutes to complete, depending on how many devices are being synchronized.</span></span> <span data-ttu-id="047a9-192">若要查看已注册的设备，请选择“**刷新**”。</span><span class="sxs-lookup"><span data-stu-id="047a9-192">To see the registered device, select **Refresh**.</span></span>  
   
   ![使用“同步”和“刷新”命令查看设备列表。](./images/hololens-ap-devices-sync.png)  

### <span data-ttu-id="047a9-194">3. 创建设备组</span><span class="sxs-lookup"><span data-stu-id="047a9-194">3. Create a device group</span></span>

1. <span data-ttu-id="047a9-195">在 [Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com) 中，选择 **组** > **新组**。</span><span class="sxs-lookup"><span data-stu-id="047a9-195">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Groups** > **New group**.</span></span>

1. <span data-ttu-id="047a9-196">对于“**组类型**”，选择“**安全性**”，然后输入组名称和描述。</span><span class="sxs-lookup"><span data-stu-id="047a9-196">For **Group type**, select **Security**, and then enter a group name and description.</span></span>

1. <span data-ttu-id="047a9-197">对于“**成员身份类型**”，选择“**已指派**” 或“**动态设备**”。</span><span class="sxs-lookup"><span data-stu-id="047a9-197">For **Membership type**, select either **Assigned** or **Dynamic Device**.</span></span>

1. <span data-ttu-id="047a9-198">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="047a9-198">Do one of the following:</span></span>  
   
   - <span data-ttu-id="047a9-199">如果在上一步中为“**成员身份类型**”选择了“**已指派**”，请选择“**成员**”，然后将 Autopilot 设备添加到组中。</span><span class="sxs-lookup"><span data-stu-id="047a9-199">If you selected **Assigned** for **Membership type** in the previous step, select **Members**, and then add Autopilot devices to the group.</span></span> <span data-ttu-id="047a9-200">通过将设备序列号用作设备名称，列出尚未注册的 Autopilot 设备。</span><span class="sxs-lookup"><span data-stu-id="047a9-200">Autopilot devices that aren't yet enrolled are listed by using the device serial number as the device name.</span></span>
   - <span data-ttu-id="047a9-201">如果在上一步中为“**成员身份类型**”选择了“**动态设备**”，请选择“**动态设备成员**”，然后在“**高级规则**”中输入代码，如下所示：</span><span class="sxs-lookup"><span data-stu-id="047a9-201">If you selected **Dynamic Devices** for **Membership type** in the previous step, select **Dynamic device members**, and then enter code in **Advanced rule** that resembles the following:</span></span>
     - <span data-ttu-id="047a9-202">若要创建包含所有 Autopilot 设备的组，请键入：</span><span class="sxs-lookup"><span data-stu-id="047a9-202">If you want to create a group that includes all of your Autopilot devices, type:</span></span> `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - <span data-ttu-id="047a9-203">Intune 的“组标记”字段映射到 Azure AD 设备的“**OrderID**”属性。</span><span class="sxs-lookup"><span data-stu-id="047a9-203">Intune's group tag field maps to the **OrderID** attribute on Azure AD devices.</span></span> <span data-ttu-id="047a9-204">如果要创建一个包含所有具有特定组标签的 Autopilot 设备的组（Azure AD 设备OrderID），必须键入：</span><span class="sxs-lookup"><span data-stu-id="047a9-204">If you want to create a group that includes all of your Autopilot devices that have a specific group tag (the Azure AD device OrderID), you must type:</span></span> `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - <span data-ttu-id="047a9-205">如果你想要创建包含所有具有特定购买订单 ID 的 Autopilot 设备的组，请键入：</span><span class="sxs-lookup"><span data-stu-id="047a9-205">If you want to create a group that includes all your Autopilot devices that have a specific Purchase Order ID, type:</span></span> `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > <span data-ttu-id="047a9-206">这些规则针对 Autopilot 设备独有的属性。</span><span class="sxs-lookup"><span data-stu-id="047a9-206">These rules target attributes that are unique to Autopilot devices.</span></span>
1. <span data-ttu-id="047a9-207">选择 **保存**，然后选择**创建**。</span><span class="sxs-lookup"><span data-stu-id="047a9-207">Select **Save**, and then select **Create**.</span></span>

### <span data-ttu-id="047a9-208">4. 创建部署配置文件</span><span class="sxs-lookup"><span data-stu-id="047a9-208">4. Create a deployment profile</span></span>

1. <span data-ttu-id="047a9-209">在[Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com)中，选择 **设备** > **Windows** > **Windows 注册** > **Windows Autopilot 部署配置文件** > **创建配置文件** > **HoloLens**。</span><span class="sxs-lookup"><span data-stu-id="047a9-209">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens**.</span></span>
   ![创建配置文件下拉菜单包括一个 HoloLens 项目。](./images/hololens-ap-enrollment-profiles.png)

1. <span data-ttu-id="047a9-211">输入配置文件名称和说明，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="047a9-211">Enter a profile name and description, and then select **Next**.</span></span>  
   <span data-ttu-id="047a9-212">你将看到包括 **HoloLens**的列表。</span><span class="sxs-lookup"><span data-stu-id="047a9-212">You should see a list that includes **HoloLens**.</span></span> <span data-ttu-id="047a9-213">如果不存在此选项，请使用[反馈](hololens2-autopilot.md#feedback-and-support-for-autopilot)选项之一与我们联系。</span><span class="sxs-lookup"><span data-stu-id="047a9-213">If this option is not present, use one of the [Feedback](hololens2-autopilot.md#feedback-and-support-for-autopilot) options to contact us.</span></span>

   ![添加配置文件名称和说明](./images/hololens-ap-profile-name.png)
1. <span data-ttu-id="047a9-215">在“**全新体验（OOBE）**”页面上，大多数设置都是预配置的，用于简化此评估的 OOBE。</span><span class="sxs-lookup"><span data-stu-id="047a9-215">On the **Out-of-box experience (OOBE)** page, most of the settings are pre-configured to streamline OOBE for this evaluation.</span></span> <span data-ttu-id="047a9-216">另外可配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="047a9-216">Optionally, you can configure the following settings:</span></span>  

   - <span data-ttu-id="047a9-217">**语言（区域）**：选择 OOBE 语言。</span><span class="sxs-lookup"><span data-stu-id="047a9-217">**Language (Region)**: Select the language for OOBE.</span></span> <span data-ttu-id="047a9-218">我们建议从[支持 HoloLens 2 的语言](hololens2-language-support.md)列表中选择一种语言。</span><span class="sxs-lookup"><span data-stu-id="047a9-218">We recommend that you select a language from the list of [supported languages for HoloLens 2](hololens2-language-support.md).</span></span>
   - <span data-ttu-id="047a9-219">**自动配置键盘**：若要确保键盘匹配所选语言，请选择“**是**”。</span><span class="sxs-lookup"><span data-stu-id="047a9-219">**Automatically configure keyboard**: To make sure that the keyboard matches the selected language, select **Yes**.</span></span>
   - <span data-ttu-id="047a9-220">**应用设备名称模板**：若要在 OOBE 期间自动设置设备名称，请选择“**是**”，然后在“\*\* 输入名称\*\*”中输入模板短语和占位符。例如，输入前缀和`%RAND:4%`&mdash;四位随机数字的占位符。</span><span class="sxs-lookup"><span data-stu-id="047a9-220">**Apply device name template**: To automatically set the device name during OOBE, select **Yes** and then enter the template phrase and placeholders in **Enter a name** For example, enter a prefix and `%RAND:4%`&mdash;a placeholder for a four-digit random number.</span></span>
     > [!NOTE]  
     > <span data-ttu-id="047a9-221">如果使用设备名称模板，OOBE 进程将在应用设备名称之后和将设备加入 Azure AD 之前再次重新启动该设备。</span><span class="sxs-lookup"><span data-stu-id="047a9-221">If you use a device name template, the OOBE process restarts the device one additional time after it applies the device name and before it joins the device to Azure AD.</span></span> <span data-ttu-id="047a9-222">重新启动后，新名称才会生效。</span><span class="sxs-lookup"><span data-stu-id="047a9-222">This restart enables the new name to take effect.</span></span>  

   ![配置 OOBE 设置](./images/hololens-ap-profile-oobe.png)
1. <span data-ttu-id="047a9-224">配置设置后，选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="047a9-224">After you configure the settings, select **Next**.</span></span>
1. <span data-ttu-id="047a9-225">在“**范围标记**”页面上，选择添加要应用于此配置文件的范围标记。</span><span class="sxs-lookup"><span data-stu-id="047a9-225">On the **Scope tags** page, optionally add the scope tags that you want to apply to this profile.</span></span> <span data-ttu-id="047a9-226">有关范围标记的详细信息，请参阅 [将基于角色的访问控制和范围标记用于分布式 IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="047a9-226">For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md).</span></span> <span data-ttu-id="047a9-227">完成后，选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="047a9-227">When finished, select **Next**.</span></span>
1. <span data-ttu-id="047a9-228">在“**分配 **”页面上，为“**分配至**”选择“**所选组**”。</span><span class="sxs-lookup"><span data-stu-id="047a9-228">On the **Assignments** page, select **Selected groups** for **Assign to**.</span></span>
1. <span data-ttu-id="047a9-229">在“**所选组**”下，选择“\*\* + 选择要包括的组\*\*”。</span><span class="sxs-lookup"><span data-stu-id="047a9-229">Under **SELECTED GROUPS**, select **+ Select groups to include**.</span></span>
1. <span data-ttu-id="047a9-230">在“**选择要包含的组**”列表中，选择为 Autopilot HoloLens 设备创建的设备组，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="047a9-230">In the **Select groups to include** list, select the device group that you created for the Autopilot HoloLens devices, and then select **Next**.</span></span>  
  
   <span data-ttu-id="047a9-231">如果要排除任何组，请选择“**选择要排除的组**”，然后选择希望排除的组。</span><span class="sxs-lookup"><span data-stu-id="047a9-231">If you want to exclude any groups, select **Select groups to exclude**, and select the groups that you want to exclude.</span></span>

   ![将设备组分配到配置文件。](./images/hololens-ap-profile-assign-devicegroup.png)
   
1. <span data-ttu-id="047a9-233">在“**审阅 + 创建**”页面上，查看设置，然后选择“**创建**”以创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="047a9-233">On the **Review + Create** page, review the settings and then select **Create** to create the profile.</span></span>  
   
   ![审阅 + 创建](./images/hololens-ap-profile-summ.png)

### <span data-ttu-id="047a9-235">5. 验证 ESP 配置</span><span class="sxs-lookup"><span data-stu-id="047a9-235">5. Verify the ESP configuration</span></span>

<span data-ttu-id="047a9-236">注册状态页面（ESP）显示完整的设备配置过程的状态，此过程在 MDM 托管用户首次登录设备时运行。</span><span class="sxs-lookup"><span data-stu-id="047a9-236">The Enrollment Status Page (ESP) displays the status of the complete device configuration process that runs when an MDM managed user signs into a device for the first time.</span></span> <span data-ttu-id="047a9-237">请确保你的 ESP 配置类似于以下内容，并验证分配是否正确。</span><span class="sxs-lookup"><span data-stu-id="047a9-237">Make sure that your ESP configuration resembles the following, and verify that the assignments are correct.</span></span>  

> [!div class="mx-imgBorder"]
> ![ESP 配置](./images/hololens-ap-profile-settings.png)

### <span data-ttu-id="047a9-239">6. 验证 HoloLens 设备的配置文件状态</span><span class="sxs-lookup"><span data-stu-id="047a9-239">6. Verify the profile status of the HoloLens devices</span></span>

1. <span data-ttu-id="047a9-240">在 Microsoft 终结点管理器管理中心中，选择“**设备**” > “**Windows**” > “**Windows 注册**” > “**设备**”。</span><span class="sxs-lookup"><span data-stu-id="047a9-240">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment** > **Devices**.</span></span>

1. <span data-ttu-id="047a9-241">验证是否列出了 HoloLens 设备，以及其配置文件的状态是否为“**已指派**”。</span><span class="sxs-lookup"><span data-stu-id="047a9-241">Verify that the HoloLens devices are listed, and that their profile status is **Assigned**.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="047a9-242">可能需要几分钟时间，配置文件才会分配到设备。</span><span class="sxs-lookup"><span data-stu-id="047a9-242">It may take a few minutes for the profile to be assigned to the device.</span></span>  

   > [!div class="mx-imgBorder"]   
   > ![设备和配置文件分配。](./images/hololens-ap-devices-assignments.png)

## <span data-ttu-id="047a9-244">适用于 HoloLens 2 用户体验的 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="047a9-244">Windows Autopilot for HoloLens 2 User Experience</span></span>

<span data-ttu-id="047a9-245">完成上述说明后，HoloLens 2 用户将通过以下体验来预配其 HoloLens 设备：</span><span class="sxs-lookup"><span data-stu-id="047a9-245">Once the above instructions are completed, your HoloLens 2 users will go through the following experience to provision their HoloLens devices:</span></span>  

1. <span data-ttu-id="047a9-246">Autopilot 体验需要 Internet 访问。</span><span class="sxs-lookup"><span data-stu-id="047a9-246">Autopilot experience requires internet access.</span></span> <span data-ttu-id="047a9-247">请使用以下选项之一提供 Internet 访问：</span><span class="sxs-lookup"><span data-stu-id="047a9-247">Please use one of following options to provide internet access:</span></span>

    - <span data-ttu-id="047a9-248">将你的设备连接到 OOBE 中的 Wi-Fi 网络，然后让它自动检测 Autopilot 体验。</span><span class="sxs-lookup"><span data-stu-id="047a9-248">Connect your device to a Wi-Fi network in OOBE and then let it detect Autopilot experience automatically.</span></span> <span data-ttu-id="047a9-249">这是你唯一需要与 OOBE 交互的时间，直到 Autopilot 体验自行完成。</span><span class="sxs-lookup"><span data-stu-id="047a9-249">This is the only time you will need to interact with OOBE until Autopilot experience completes on its own.</span></span> <span data-ttu-id="047a9-250">请注意，默认情况下，HoloLens 2 会在检测到 Internet 后等待 10 秒钟以检测 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="047a9-250">Please note that by default HoloLens 2 waits for 10 seconds to detect Autopilot after detecting internet.</span></span> <span data-ttu-id="047a9-251">如果在 10 秒内未检测到 autopilot 配置文件，OOBE 将显示 EULA。</span><span class="sxs-lookup"><span data-stu-id="047a9-251">If no autopilot profile is detected within 10 seconds, OOBE will present EULA.</span></span> <span data-ttu-id="047a9-252">如果遇到这种情况，请重新启动你的设备，以便再次尝试检测 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="047a9-252">If you encounter this scenario, please reboot your device so another attempt can be made to detect Autopilot.</span></span> <span data-ttu-id="047a9-253">另请注意，只有在设备上设置了 TenantLockdown 策略时，OOBE 才能无限期地等待 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="047a9-253">Please also note that OOBE can wait indefinitely for Autopilot only if TenantLockdown policy is set on the device.</span></span>
    
    - <span data-ttu-id="047a9-254">使用“USB-C 到以太网”适配器将设备与以太网连接，以实现有线 Internet 连接，并使 HoloLens 2 自动完成 Autopilot 体验。</span><span class="sxs-lookup"><span data-stu-id="047a9-254">Connect your device with Ethernet using "USB-C to Ethernet" adapters for wired internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>
    
    - <span data-ttu-id="047a9-255">通过“USB-C 到 Wifi”适配器连接设备以实现无线 Internet 连接，并使 HoloLens 2 自动完成 Autopilot 体验。</span><span class="sxs-lookup"><span data-stu-id="047a9-255">Connect your device with "USB-C to Wifi" adapters for wireless internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

       > [!NOTE]
       > <span data-ttu-id="047a9-256">使用 Autopilot 将对[设备所有者](security-adminless-os.md#device-owner)产生影响。</span><span class="sxs-lookup"><span data-stu-id="047a9-256">Using Autopilot will have an effect on the [device owner](security-adminless-os.md#device-owner).</span></span>
   
       > [!IMPORTANT]  
       > <span data-ttu-id="047a9-257">尝试将 OOBE 中的 Wi-Fi 网络用于 Autopilot 的设备必须位于 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 上。</span><span class="sxs-lookup"><span data-stu-id="047a9-257">Devices attempting to use Wi-Fi networks in OOBE for Autopilot must be on [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2).</span></span>
       >
       > <span data-ttu-id="047a9-258">对于使用以太网适配器的设备，必须在开箱即用体验 (OOBE) 启动之前将设备连接到网络。</span><span class="sxs-lookup"><span data-stu-id="047a9-258">For devices using ethernet adapters you must connect the device to the network before the Out-of-the-Box-Experience (OOBE) starts.</span></span> <span data-ttu-id="047a9-259">设备在第一个 OOBE 屏幕上确定是否将其配置为 Autopilot 设备。</span><span class="sxs-lookup"><span data-stu-id="047a9-259">The device determines whether it is provisioning as an Autopilot device while on the first OOBE screen.</span></span> <span data-ttu-id="047a9-260">如果设备无法连接到网络，或者选择不将其配置为 Autopilot 设备，则以后无法更改为 Autopilot 配置。</span><span class="sxs-lookup"><span data-stu-id="047a9-260">If the device cannot connect to the network, or if you choose not to provision the device as an Autopilot device, you cannot change to Autopilot provisioning at a later time.</span></span> <span data-ttu-id="047a9-261">相反，必须启动此过程，以便将设备设置为 Autopilot 设备。</span><span class="sxs-lookup"><span data-stu-id="047a9-261">Instead, you would have to start this procedure over in order to provision the device as an Autopilot device.</span></span>

1. <span data-ttu-id="047a9-262">设备应自动启动 OOBE。</span><span class="sxs-lookup"><span data-stu-id="047a9-262">The device should automatically start OOBE.</span></span> <span data-ttu-id="047a9-263">不要与 OOBE 交互。</span><span class="sxs-lookup"><span data-stu-id="047a9-263">Do not interact with OOBE.</span></span> <span data-ttu-id="047a9-264">放松一下！</span><span class="sxs-lookup"><span data-stu-id="047a9-264">Instead sit, back and relax!</span></span> <span data-ttu-id="047a9-265">让 HoloLens 2 检测网络连接并允许自动完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="047a9-265">Let HoloLens 2 detect network connectivity and allow it complete OOBE automatically.</span></span> <span data-ttu-id="047a9-266">设备可能会在 OOBE 过程中重启。</span><span class="sxs-lookup"><span data-stu-id="047a9-266">The device may restart during OOBE.</span></span> <span data-ttu-id="047a9-267">OOBE 屏幕应类似于以下内容。</span><span class="sxs-lookup"><span data-stu-id="047a9-267">The OOBE screens should resemble the following.</span></span>
   
   <span data-ttu-id="047a9-268">![OOBE 步骤 1](./images/autopilot-welcome.jpg)
   ![OOBE 步骤 2](./images/autopilot-step-complete.jpg)
   ![OOBE 步骤3](./images/autopilot-device-setup.jpg)</span><span class="sxs-lookup"><span data-stu-id="047a9-268">![OOBE step 1](./images/autopilot-welcome.jpg)
![OOBE step 2](./images/autopilot-step-complete.jpg)
![OOBE step 3](./images/autopilot-device-setup.jpg)</span></span>

1. <span data-ttu-id="047a9-269">OOBE 结束时，可以使用用户名和密码登录到设备。</span><span class="sxs-lookup"><span data-stu-id="047a9-269">At the end of OOBE, you can sign in to the device by using your user name and password.</span></span>

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <span data-ttu-id="047a9-270">Tenantlockdown 云解决方案提供商和 Autopilot</span><span class="sxs-lookup"><span data-stu-id="047a9-270">Tenantlockdown CSP and Autopilot</span></span>

<span data-ttu-id="047a9-271">HoloLens 2 设备从 Windows 全息 20H2 版本开始支持 TenantLockdown 云解决方案提供商。</span><span class="sxs-lookup"><span data-stu-id="047a9-271">HoloLens 2 devices support TenantLockdown CSP as of Windows Holographic, version 20H2.</span></span> <span data-ttu-id="047a9-272">该 CSP 将设备锁定在组织的租户上，即使在设备重置或重新刷新的情况下也能保持设备在该租户上。</span><span class="sxs-lookup"><span data-stu-id="047a9-272">This CSP keeps devices on the organization's tenant by locking them to that tenant even through device reset or reflash.</span></span> 

<span data-ttu-id="047a9-273">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 允许仅使用 Autopilot 将 HoloLens 2 绑定到 MDM 注册。 </span><span class="sxs-lookup"><span data-stu-id="047a9-273">[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP enables HoloLens 2 to be tied to MDM enrollment using Autopilot only.</span></span> <span data-ttu-id="047a9-274">在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 或 false（初始设置）值后，即使进行重新刷新、操作系统更新，该值仍将保留在设备上。</span><span class="sxs-lookup"><span data-stu-id="047a9-274">Once TenantLockdown CSP’s RequireNetworkInOOBE node is set to either true or false (initially set) value on HoloLens 2, that value remains on the device despite re-flashing, OS updates, etc.</span></span> 

<span data-ttu-id="047a9-275">在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 后， OOBE 将无限期等待 Autopilot 配置文件在网络连接后成功下载并应用。</span><span class="sxs-lookup"><span data-stu-id="047a9-275">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, OOBE waits indefinitely for Autopilot profile to be successfully downloaded and applied, after network connectivity.</span></span> 

<span data-ttu-id="047a9-276">在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 后，OOBE 中不允许执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="047a9-276">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, following operations are disallowed in OOBE:</span></span> 
- <span data-ttu-id="047a9-277">使用运行时预配创建本地用户</span><span class="sxs-lookup"><span data-stu-id="047a9-277">Creating local user using runtime provisioning</span></span> 
- <span data-ttu-id="047a9-278">通过运行时预配执行 AAD 加入操作</span><span class="sxs-lookup"><span data-stu-id="047a9-278">Performing AAD join operation via runtime provisioning</span></span> 
- <span data-ttu-id="047a9-279">在 OOBE 体验中选择设备所有者</span><span class="sxs-lookup"><span data-stu-id="047a9-279">Selecting who owns the device in OOBE experience</span></span> 

#### <span data-ttu-id="047a9-280">如何使用 Intune 设置此选项？</span><span class="sxs-lookup"><span data-stu-id="047a9-280">How to set this using Intune?</span></span> 
1. <span data-ttu-id="047a9-281">创建自定义 OMA URI 设备配置配置文件，并为 RequireNetworkInOOBE 节点指定 true，如下所示。</span><span class="sxs-lookup"><span data-stu-id="047a9-281">Create a custom OMA URI device configuration profile and specify true for RequireNetworkInOOBE node as shown below.</span></span>
<span data-ttu-id="047a9-282">OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span><span class="sxs-lookup"><span data-stu-id="047a9-282">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > ![通过 OMA-URI 设置租户锁定](images/hololens-tenant-lockdown.png)

1. <span data-ttu-id="047a9-284">创建组并将设备配置文件分配给该设备组。</span><span class="sxs-lookup"><span data-stu-id="047a9-284">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="047a9-285">使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。</span><span class="sxs-lookup"><span data-stu-id="047a9-285">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>  

<span data-ttu-id="047a9-286">在 Intune 门户中验证设备配置是否已成功应用。</span><span class="sxs-lookup"><span data-stu-id="047a9-286">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="047a9-287">此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的效果将处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="047a9-287">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be active.</span></span>

#### <span data-ttu-id="047a9-288">如何使用 Intune 在 HoloLens 2 上取消设置 TenantLockdown 的 RequireNetworkInOOBE？</span><span class="sxs-lookup"><span data-stu-id="047a9-288">How to unset TenantLockdown’s RequireNetworkInOOBE on HoloLens 2 using Intune?</span></span> 
1. <span data-ttu-id="047a9-289">从先前分配了上面创建的设备配置的设备组中删除 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="047a9-289">Remove the HoloLens 2 from the device group to which the device configuration created above was previously assigned.</span></span> 

1. <span data-ttu-id="047a9-290">创建基于 OMA URI 的自定义设备配置配置文件，并为 RequireNetworkInOOBE 指定 false，如下所示。</span><span class="sxs-lookup"><span data-stu-id="047a9-290">Create a custom OMA URI based device configuration profile and specify false for RequireNetworkInOOBE as shown below.</span></span> <span data-ttu-id="047a9-291">OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span><span class="sxs-lookup"><span data-stu-id="047a9-291">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > ![通过 Intune 中的 OMA URI 将 RequireNetworkInOOBE 设置为 false 的屏幕截图](images/hololens-tenant-lockdown-false.png)

1. <span data-ttu-id="047a9-293">创建组并将设备配置文件分配给该设备组。</span><span class="sxs-lookup"><span data-stu-id="047a9-293">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="047a9-294">使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。</span><span class="sxs-lookup"><span data-stu-id="047a9-294">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>

<span data-ttu-id="047a9-295">在 Intune 门户中验证设备配置是否已成功应用。</span><span class="sxs-lookup"><span data-stu-id="047a9-295">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="047a9-296">此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的效果将处于非活动状态。</span><span class="sxs-lookup"><span data-stu-id="047a9-296">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be inactive.</span></span> 

#### <span data-ttu-id="047a9-297">如果在 TenantLockdown 设置为 true 后在 HoloLens 上取消分配 Autopilot 配置文件，则 OOBE 期间会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="047a9-297">What would happen during OOBE, if Autopilot profile is unassigned on a HoloLens after TenantLockdown was set to true?</span></span> 
<span data-ttu-id="047a9-298">OOBE 将无限期等待 Autopilot 配置文件下载，并将显示以下对话框。</span><span class="sxs-lookup"><span data-stu-id="047a9-298">OOBE will wait indefinitely for Autopilot profile to download and following dialog will be presented.</span></span> <span data-ttu-id="047a9-299">为了消除 TenantLockdown 的影响，必须首先仅使用 Autopilot 将设备注册到其原始租户，并且必须按照上一步中的说明取消设置 RequireNetworkInOOBE，然后才能删除 TenantLockdown CSP 引入的限制。</span><span class="sxs-lookup"><span data-stu-id="047a9-299">In order to remove effects of TenantLockdown, device must be enrolled with its original tenant first using Autopilot only and RequireNetworkInOOBE must be unset as described in previous step before restrictions introduced by TenantLockdown CSP are removed.</span></span> 

![在设备上实施策略时的设备内视图。](images/hololens-autopilot-lockdown.png)

## <span data-ttu-id="047a9-301">已知的问题 & 限制</span><span class="sxs-lookup"><span data-stu-id="047a9-301">Known Issues & limitations</span></span>

- <span data-ttu-id="047a9-302">我们正在研究在 MEM 中配置的基于设备上下文的应用程序安装在不适用于 HoloLens 的问题。</span><span class="sxs-lookup"><span data-stu-id="047a9-302">We are investigating an issue where device-context based application install configured in MEM does not apply to HoloLens.</span></span> [<span data-ttu-id="047a9-303">了解有关设备上下文和用户上下文安装的详细信息。</span><span class="sxs-lookup"><span data-stu-id="047a9-303">Learn more about device context and user context installs.</span></span>](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- <span data-ttu-id="047a9-304">通过 Wi-Fi 设置 Autopilot 时，可能存在 Autopilot 配置文件在首次建立 Internet 连接时未下载的情况。</span><span class="sxs-lookup"><span data-stu-id="047a9-304">While setting up Autopilot over Wi-Fi, there may be an instance where the Autopilot profile is not downloaded when Internet connection is first established.</span></span> <span data-ttu-id="047a9-305">在此情况下，将显示最终用户许可协议 (EULA) ，并且用户可以选择继续非 Autopilot 的设置体验。</span><span class="sxs-lookup"><span data-stu-id="047a9-305">In this case End User License Agreement (EULA) is presented and the user has the option to proceed with non-Autopilot setup experience.</span></span> <span data-ttu-id="047a9-306">若要重新尝试使用自动驾驶仪进行设置，请将设备置于睡眠状态再重新启动，或者重启设备，让其再次尝试。</span><span class="sxs-lookup"><span data-stu-id="047a9-306">To retry setting up with Autopilot, put the device to sleep and then power up, or reboot the device and let it try again.</span></span>
- <span data-ttu-id="047a9-307">目前在 HoloLens 上还未支持 "将所有目标设备转换为 Autopilot" 的功能。</span><span class="sxs-lookup"><span data-stu-id="047a9-307">"Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  

### <span data-ttu-id="047a9-308">疑难解答</span><span class="sxs-lookup"><span data-stu-id="047a9-308">Troubleshooting</span></span>

<span data-ttu-id="047a9-309">以下文章可能是你了解更多信息和解决自动驾驶问题的有用资源，但请注意，这些文章是基于Windows 10 桌面版，并非所有信息都适用于 HoloLens：</span><span class="sxs-lookup"><span data-stu-id="047a9-309">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>
- [<span data-ttu-id="047a9-310">Windows Autopilot - 已知问题</span><span class="sxs-lookup"><span data-stu-id="047a9-310">Windows Autopilot - known issues</span></span>](https://docs.microsoft.com/mem/autopilot/known-issues)
- [<span data-ttu-id="047a9-311">解决 Microsoft Intune 中的 Windows 设备注册问题</span><span class="sxs-lookup"><span data-stu-id="047a9-311">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="047a9-312">Windows Autopilot - 策略冲突</span><span class="sxs-lookup"><span data-stu-id="047a9-312">Windows Autopilot - Policy Conflicts</span></span>](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## <span data-ttu-id="047a9-313">Autopilot 的反馈与支持</span><span class="sxs-lookup"><span data-stu-id="047a9-313">Feedback and support for Autopilot</span></span>

<span data-ttu-id="047a9-314">若要提供反馈或报告问题，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="047a9-314">To provide feedback or report issues, use one of the following methods:</span></span>

- <span data-ttu-id="047a9-315">有关设备注册的支持，请联系你的经销商或分销商。</span><span class="sxs-lookup"><span data-stu-id="047a9-315">For support on device registration please contact your reseller or distributor.</span></span>
- <span data-ttu-id="047a9-316">有关 Windows Autopilot 的常规支持查询或有关配置文件分配、组创建或 MEM 门户控件等问题， [请联系 Microsoft 终结点管理器支持](https://docs.microsoft.com/mem/get-support)</span><span class="sxs-lookup"><span data-stu-id="047a9-316">For general support inquiries about Windows Autopilot, or for issues like profile assignments, group creation or MEM portal controls, [please contact Microsoft Endpoint Manager support](https://docs.microsoft.com/mem/get-support)</span></span>  
- <span data-ttu-id="047a9-317">如果你的设备已注册到 Autopilot 服务，并且配置文件分配在 MEM 门户上，请联系 HoloLens [支持部门](https://docs.microsoft.com/hololens/)（参阅 “支持” 卡）。</span><span class="sxs-lookup"><span data-stu-id="047a9-317">If your device is registered to the Autopilot service and the profile is assigned on MEM portal, contact HoloLens [support](https://docs.microsoft.com/hololens/) (see 'Support' card).</span></span> <span data-ttu-id="047a9-318">请开具支持票证，如果适用，请在开箱体验（OOBE）期间捕获 [脱机诊断日志](hololens-diagnostic-logs.md#offline-diagnostics) ，包括截图和日志。</span><span class="sxs-lookup"><span data-stu-id="047a9-318">Please open a support ticket and if applicable, include screenshots and logs by capturing [offline diagnostic logs](hololens-diagnostic-logs.md#offline-diagnostics) during the out-of-box-experience (OOBE).</span></span>
- <span data-ttu-id="047a9-319">若要从设备上报告问题，请使用 HoloLens 上的反馈中心应用程序。</span><span class="sxs-lookup"><span data-stu-id="047a9-319">To report an issue from the device, use the Feedback Hub app on your HoloLens.</span></span> <span data-ttu-id="047a9-320">在反馈中心中，选择**企业管理** > **设备**类别。</span><span class="sxs-lookup"><span data-stu-id="047a9-320">In Feedback Hub, select the **Enterprise Management** > **Device** category.</span></span> 
- <span data-ttu-id="047a9-321">若要提供有关 HoloLens Autopilot 的常规反馈以及，可提交此 [调查问卷](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)</span><span class="sxs-lookup"><span data-stu-id="047a9-321">To provide general feedback on Autopilot for HoloLens, you can submit this [survey](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)</span></span> 


