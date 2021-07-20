---
title: 适用于 HoloLens 2 的 Windows Autopilot
description: 了解如何在 HoloLens 2 设备上对 Autopilot 进行设置、配置和故障排除。
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
ms.openlocfilehash: cc73f5cbb438119f4c626ae76db9c91373e19aff
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635358"
---
# <a name="windows-autopilot-for-hololens-2"></a><span data-ttu-id="a3e36-104">适用于 HoloLens 2 的 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="a3e36-104">Windows Autopilot for HoloLens 2</span></span>

<span data-ttu-id="a3e36-105">从 Windows 全息版 2004 开始，HoloLens 2 支持使用 Microsoft Intune 的 Windows Autopilot [自部署模式](/mem/autopilot/self-deploying)（不支持第三方 MDM）。</span><span class="sxs-lookup"><span data-stu-id="a3e36-105">Starting with Windows Holographic version 2004, HoloLens 2 supports Windows Autopilot [Self-Deploying Mode](/mem/autopilot/self-deploying) with Microsoft Intune (3rd party MDMs are not supported).</span></span> <span data-ttu-id="a3e36-106">管理员可在 Microsoft Endpoint Manager 中配置全新体验 (OOBE)，并允许终端用户在几乎没有交互的情况下为业务使用准备设备。</span><span class="sxs-lookup"><span data-stu-id="a3e36-106">Administrators can configure the out-of-box experience (OOBE) in Microsoft Endpoint Manager and enable end-users to prepare devices for business use with little to no interaction.</span></span> <span data-ttu-id="a3e36-107">这减少了库存管理开销、动手准备设备的成本以及员工在设置过程中的支持电话。</span><span class="sxs-lookup"><span data-stu-id="a3e36-107">This reduces inventory management overhead, cost of hands-on device preparation and support calls from employees during the setup experience.</span></span> <span data-ttu-id="a3e36-108">在 [Windows Autopilot](/mem/autopilot/windows-autopilot) 文档中了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="a3e36-108">Learn more in the [Windows Autopilot](/mem/autopilot/windows-autopilot) documentation.</span></span>

<span data-ttu-id="a3e36-109">与 Surface 设备一样，我们建议客户与其 Microsoft [云解决方案提供商](https://partner.microsoft.com/cloud-solution-provider)（经销商或分销商）合作，通过合作伙伴中心将设备注册到 Autopilot 服务。</span><span class="sxs-lookup"><span data-stu-id="a3e36-109">Like for Surface devices, it is recommended that customers work with their Microsoft [Cloud Solution Provider](https://partner.microsoft.com/cloud-solution-provider) (reseller or distributor) to get devices registered with the Autopilot service through Partner Center.</span></span> <span data-ttu-id="a3e36-110">[添加设备](/mem/autopilot/add-devices)文档中概述了设备注册的其他方法，不过利用 Microsoft 的渠道合作伙伴可确保最有效的端到端路径。</span><span class="sxs-lookup"><span data-stu-id="a3e36-110">Other methods for device registration are outlined in the [add device](/mem/autopilot/add-devices) documentation, though leveraging Microsoft's channel partners ensures the most effective end-to-end path.</span></span>

> [!NOTE]
> <span data-ttu-id="a3e36-111">自 2020 年 11 月 20 日起，Microsoft Endpoint Manager 中 HoloLens 的 Autopilot 配置将转换为公共预览。</span><span class="sxs-lookup"><span data-stu-id="a3e36-111">As of 11/20/2020 Autopilot configuration for HoloLens in Microsoft Endpoint Manager is transitioning to **Public Preview**.</span></span> <span data-ttu-id="a3e36-112">客户无需再注册私人预览，所有租户都可在 MEM 管理中心中设置 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="a3e36-112">Customers no longer need to enroll in the private preview and all tenants will be able to setup Autopilot in the MEM admin center.</span></span>

<span data-ttu-id="a3e36-113">当用户启动 Autopilot 自部署过程时，Autopilot 会完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a3e36-113">When a user starts the Autopilot self-deploying process, Autopilot completes the following steps:</span></span>

1. <span data-ttu-id="a3e36-114">将设备加入 Azure Active Directory (Azure AD)。</span><span class="sxs-lookup"><span data-stu-id="a3e36-114">Join the device to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="a3e36-115">请注意，适用于 HoloLens 的 Autopilot 不支持 Active Directory 联接或混合 Azure AD 联接。</span><span class="sxs-lookup"><span data-stu-id="a3e36-115">Note that Autopilot for HoloLens does not support Active Directory join or Hybrid Azure AD join.</span></span>

1. <span data-ttu-id="a3e36-116">使用 Azure AD 在 Microsoft Endpoint Manager（或其他 MDM 服务）中注册设备。</span><span class="sxs-lookup"><span data-stu-id="a3e36-116">Use Azure AD to enroll the device in Microsoft Endpoint Manager (or another MDM service).</span></span>

1. <span data-ttu-id="a3e36-117">下载并应用面向设备的策略、证书、网络配置文件和应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3e36-117">Download and apply device-targeted policies, certificates, networking profiles and applications.</span></span>

1. <span data-ttu-id="a3e36-118">预配设备。</span><span class="sxs-lookup"><span data-stu-id="a3e36-118">Provision the device.</span></span>

1. <span data-ttu-id="a3e36-119">向用户展示登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="a3e36-119">Present the sign-in screen to the user.</span></span>

## <a name="configuring-autopilot-for-hololens-2"></a><span data-ttu-id="a3e36-120">配置适用于 HoloLens 2 的 Autopilot</span><span class="sxs-lookup"><span data-stu-id="a3e36-120">Configuring Autopilot for HoloLens 2</span></span>

<span data-ttu-id="a3e36-121">请按照以下步骤设置环境：</span><span class="sxs-lookup"><span data-stu-id="a3e36-121">Please follow the steps below to set up your environment:</span></span>

1. [<span data-ttu-id="a3e36-122">查看适用于 HoloLens 2 的 Windows Autopilot 要求。</span><span class="sxs-lookup"><span data-stu-id="a3e36-122">Review requirements for Windows Autopilot for HoloLens 2.</span></span>](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [<span data-ttu-id="a3e36-123">启用自动 MDM 注册</span><span class="sxs-lookup"><span data-stu-id="a3e36-123">Enable Automatic MDM Enrollment</span></span>](#2-enable-automatic-mdm-enrollment)

1. [<span data-ttu-id="a3e36-124">在 Windows Autopilot 中注册设备。</span><span class="sxs-lookup"><span data-stu-id="a3e36-124">Register devices in Windows Autopilot.</span></span>](#3-register-devices-in-windows-autopilot)

1. [<span data-ttu-id="a3e36-125">创建设备组。</span><span class="sxs-lookup"><span data-stu-id="a3e36-125">Create a device group.</span></span>](#4-create-a-device-group)

1. [<span data-ttu-id="a3e36-126">创建部署配置文件。</span><span class="sxs-lookup"><span data-stu-id="a3e36-126">Create a deployment profile.</span></span>](#5-create-a-deployment-profile)

1. [<span data-ttu-id="a3e36-127">验证注册状态页 (ESP) 配置。</span><span class="sxs-lookup"><span data-stu-id="a3e36-127">Verify the Enrollment Status Page (ESP) configuration.</span></span>](#6-verify-the-esp-configuration)

1. [<span data-ttu-id="a3e36-128">验证 HoloLens 设备的配置文件状态。</span><span class="sxs-lookup"><span data-stu-id="a3e36-128">Verify the profile status of the HoloLens devices.</span></span>](#7-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a><span data-ttu-id="a3e36-129">1. 查看适用于 HoloLens 2 的 Windows Autopilot 要求</span><span class="sxs-lookup"><span data-stu-id="a3e36-129">1. Review requirements for Windows Autopilot for HoloLens 2</span></span>

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a><span data-ttu-id="a3e36-130">参阅 Windows Autopilot 要求文章的以下部分：</span><span class="sxs-lookup"><span data-stu-id="a3e36-130">Review the following sections of the Windows Autopilot requirements article:</span></span>

- [<span data-ttu-id="a3e36-131">网络要求</span><span class="sxs-lookup"><span data-stu-id="a3e36-131">Network requirements</span></span>](/mem/autopilot/networking-requirements)  
- [<span data-ttu-id="a3e36-132">许可要求</span><span class="sxs-lookup"><span data-stu-id="a3e36-132">Licensing requirements</span></span>](/mem/autopilot/licensing-requirements)  
- [<span data-ttu-id="a3e36-133">配置要求</span><span class="sxs-lookup"><span data-stu-id="a3e36-133">Configuration requirements</span></span>](/mem/autopilot/configuration-requirements)

<span data-ttu-id="a3e36-134">查看 Windows Autopilot 自部署模式文章“[要求](/windows/deployment/windows-autopilot/self-deploying#requirements)”部分。</span><span class="sxs-lookup"><span data-stu-id="a3e36-134">**Review the "[Requirements](/windows/deployment/windows-autopilot/self-deploying#requirements)" section of the Windows Autopilot Self-Deploying mode article.**</span></span> <span data-ttu-id="a3e36-135">环境必须满足这些要求以及 Windows Autopilot 标准要求。</span><span class="sxs-lookup"><span data-stu-id="a3e36-135">Your environment has to meet these requirements as well as the standard Windows Autopilot requirements.</span></span> <span data-ttu-id="a3e36-136">无需查看文章中的“分步操作”和“验证”部分。</span><span class="sxs-lookup"><span data-stu-id="a3e36-136">You do not have to review the "Step by step" and "Validation" sections of the article.</span></span> <span data-ttu-id="a3e36-137">本文后面的过程将提供特定于 HoloLens 的相应步骤。</span><span class="sxs-lookup"><span data-stu-id="a3e36-137">The procedures later in this article provide corresponding steps that are specific to HoloLens.</span></span>

<span data-ttu-id="a3e36-138">有关如何注册设备和配置配置文件的信息，请参阅本文中的 [2. 在 Windows Autopilot 中注册设备](#3-register-devices-in-windows-autopilot)和 [4. 创建部署配置文件](#5-create-a-deployment-profile)。</span><span class="sxs-lookup"><span data-stu-id="a3e36-138">For information about how to register devices and configure profiles, see [2. Register devices in Windows Autopilot](#3-register-devices-in-windows-autopilot) and [4. Create a deployment profile](#5-create-a-deployment-profile) in this article.</span></span> <span data-ttu-id="a3e36-139">若要配置和管理 Autopilot 自部署模式配置文件，请确保你有权访问 [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="a3e36-139">To configure and manage the Autopilot self-deploying mode profiles, make sure that you have access to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>

#### <a name="review-hololens-os-requirements"></a><span data-ttu-id="a3e36-140">查看 HoloLens 操作系统要求：</span><span class="sxs-lookup"><span data-stu-id="a3e36-140">Review HoloLens OS requirements:</span></span>

- <span data-ttu-id="a3e36-141">设备必须使用 [Windows 全息版（版本 2004）](hololens-release-notes.md#windows-holographic-version-2004)（内部版本 19041.1103）或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a3e36-141">Devices must be on [Windows Holographic, version 2004](hololens-release-notes.md#windows-holographic-version-2004) (build 19041.1103) or later.</span></span> <span data-ttu-id="a3e36-142">若要确认设备上的内部版本或重刷到最新的操作系统，请使用 [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) 和我们的[设备重刷说明](/hololens/hololens-recovery#clean-reflash-the-device)。</span><span class="sxs-lookup"><span data-stu-id="a3e36-142">To confirm the build version on your device or re-flash to the latest OS, use the [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab) and our [device re-flash instructions](/hololens/hololens-recovery#clean-reflash-the-device).</span></span> <span data-ttu-id="a3e36-143">请注意，在 2020 年 9 月底之前交付的设备已预安装 Windows 全息版（版本 1903）。</span><span class="sxs-lookup"><span data-stu-id="a3e36-143">Note that devices delivered until late September 2020 have Windows Holographic version 1903 pre-installed.</span></span> <span data-ttu-id="a3e36-144">请与经销商联系，确保向你提供的是预安装了 Autopilot 的设备。</span><span class="sxs-lookup"><span data-stu-id="a3e36-144">Please contact your reseller to ensure that Autopilot-ready devices are shipped to you.</span></span>

- <span data-ttu-id="a3e36-145">Windows 全息版（版本 2004）仅支持通过以太网连接部署 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="a3e36-145">Windows Holographic, version 2004 only supports Autopilot over ethernet connection.</span></span> <span data-ttu-id="a3e36-146">在打开 HoloLens 之前，使用“USB-C 转以太网”适配器确保其已连接到以太网。</span><span class="sxs-lookup"><span data-stu-id="a3e36-146">Ensure the HoloLens is connected to ethernet using a "USB-C to Ethernet" adapter **before turning it on**.</span></span> <span data-ttu-id="a3e36-147">设备启动后，无需用户交互。</span><span class="sxs-lookup"><span data-stu-id="a3e36-147">Upon device boot no user interaction is required.</span></span> <span data-ttu-id="a3e36-148">如果计划将 Autopilot 部署到多个 HoloLens 设备，我们建议对适配器基础结构进行规划。</span><span class="sxs-lookup"><span data-stu-id="a3e36-148">If you are planning for an Autopilot roll-out to many HoloLens devices, we recommend that you plan for the adapter infrastructure.</span></span> <span data-ttu-id="a3e36-149">我们不建议使用 USB 集线器，因为它们通常需要安装其他第三方驱动程序，而 HoloLens 不支持这些驱动程序。</span><span class="sxs-lookup"><span data-stu-id="a3e36-149">We do not recommend USB Hubs, as they often require additional third-party drivers to be installed which is not supported on HoloLens.</span></span>

- <span data-ttu-id="a3e36-150">[Windows 全息版（版本 20H2）](hololens-release-notes.md#windows-holographic-version-20h2)（内部版本 19041.1128）或更高版本支持通过 Wi-Fi 部署 Autopilot，不过你仍可使用以太网适配器。</span><span class="sxs-lookup"><span data-stu-id="a3e36-150">[Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) (build 19041.1128) or later support Autopilot over Wi-Fi, although you may still use ethernet adapters.</span></span> <span data-ttu-id="a3e36-151">对于通过 Wi-Fi 连接的设备，用户必须仅：</span><span class="sxs-lookup"><span data-stu-id="a3e36-151">For devices connected via Wi-fi, the user must only:</span></span>

     - <span data-ttu-id="a3e36-152">转到 hummingbird 场景</span><span class="sxs-lookup"><span data-stu-id="a3e36-152">Go through the hummingbird scene</span></span>
     - <span data-ttu-id="a3e36-153">选择语言和区域设置</span><span class="sxs-lookup"><span data-stu-id="a3e36-153">Choose the language and locale</span></span>
     - <span data-ttu-id="a3e36-154">运行目视校准</span><span class="sxs-lookup"><span data-stu-id="a3e36-154">Run eye-calibration</span></span>
     - <span data-ttu-id="a3e36-155">建立网络连接</span><span class="sxs-lookup"><span data-stu-id="a3e36-155">Establish network connection</span></span>

- <span data-ttu-id="a3e36-156">Windows 全息版（版本 20H2）支持 [Tenantlockdown CSP 和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)，这会将设备锁定在一个租户上，并确保在无意或有意重置或擦除的情况下，设备仍与该租户绑定。</span><span class="sxs-lookup"><span data-stu-id="a3e36-156">Windows Holographic, version 20H2 supports [Tenantlockdown CSP and Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot), which locks a device to a tenant and  ensures that the device remains bound to that tenant in case of accidental or intentional resets or wipes.</span></span>  

- <span data-ttu-id="a3e36-157">确保设备尚未成为 Azure AD 的成员，并且未在 Intune（或其他 MDM 系统）中注册。</span><span class="sxs-lookup"><span data-stu-id="a3e36-157">Ensure that the devices are not already members of Azure AD, and are not enrolled in Intune (or another MDM system).</span></span> <span data-ttu-id="a3e36-158">Autopilot 自部署过程完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="a3e36-158">The Autopilot self-deploying process completes these steps.</span></span> <span data-ttu-id="a3e36-159">若要确保所有设备相关信息都已得到清理，请检查 Azure AD 和 Intune 门户中的“设备”页面。</span><span class="sxs-lookup"><span data-stu-id="a3e36-159">To make sure that all the device-related information is cleaned up, check the **Devices** pages in both Azure AD and Intune Portals.</span></span> <span data-ttu-id="a3e36-160">请注意，目前 HoloLens 不支持“将所有目标设备转换为 Autopilot”的功能。</span><span class="sxs-lookup"><span data-stu-id="a3e36-160">Note that "Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  

### <a name="2-enable-automatic-mdm-enrollment"></a><span data-ttu-id="a3e36-161">2. 启用自动 MDM 注册：</span><span class="sxs-lookup"><span data-stu-id="a3e36-161">2. Enable Automatic MDM Enrollment:</span></span>

<span data-ttu-id="a3e36-162">为使 Autopilot 成功运行，需要在 Azure 门户中启用自动 MDM 注册。</span><span class="sxs-lookup"><span data-stu-id="a3e36-162">In order for Autopilot to succeed you'll need to enable Automatic MDM Enrollment in your Azure portal.</span></span> <span data-ttu-id="a3e36-163">这将允许设备在没有用户的情况下注册。</span><span class="sxs-lookup"><span data-stu-id="a3e36-163">This will enable the device to enroll without a user.</span></span>

<span data-ttu-id="a3e36-164">在 [Azure 门户](https://portal.azure.com/#home)中，选择“Azure Active Directory” -> “移动性(MDM 和 MAM)” -> “Microsoft Intune”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-164">In the [Azure portal](https://portal.azure.com/#home) select **Azure Active Directory** -> **Mobility (MDM and MAM)** -> **Microsoft Intune**.</span></span> <span data-ttu-id="a3e36-165">然后配置“MDM 用户范围”，你需要选择“全部”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-165">Then configure the **MDM user scope**, you will need to select **All**.</span></span>

<span data-ttu-id="a3e36-166">请阅读以下关于[启用 MDM 自动注册的简短指南](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal)或[自动注册快速入门指南](/mem/intune/enrollment/quickstart-setup-auto-enrollment)，以获取更多设置信息。</span><span class="sxs-lookup"><span data-stu-id="a3e36-166">Please review the following short [guide on enabling MDM Automatic Enrollment](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal) or the [Auto Enrollment Quick start guide](/mem/intune/enrollment/quickstart-setup-auto-enrollment) for even more information getting set up.</span></span>

### <a name="3-register-devices-in-windows-autopilot"></a><span data-ttu-id="a3e36-167">3. 在 Windows Autopilot 中注册设备</span><span class="sxs-lookup"><span data-stu-id="a3e36-167">3. Register devices in Windows Autopilot</span></span>

<span data-ttu-id="a3e36-168">在首次设置之前，设备必须在 Windows Autopilot 中注册。</span><span class="sxs-lookup"><span data-stu-id="a3e36-168">Your devices must be registered in Windows Autopilot before first setup.</span></span> <span data-ttu-id="a3e36-169">有关设备注册的 MEM 文档，请参阅[将设备添加到 Autopilot](/mem/autopilot/add-devices)。</span><span class="sxs-lookup"><span data-stu-id="a3e36-169">For MEM documentation on device registration please see [Adding devices to Autopilot](/mem/autopilot/add-devices).</span></span>  

<span data-ttu-id="a3e36-170">注册 HoloLens 设备有三种主要方法：</span><span class="sxs-lookup"><span data-stu-id="a3e36-170">There are three primary ways to register HoloLens devices:</span></span>

 - <span data-ttu-id="a3e36-171">当你下订单时，经销商可在合作伙伴中心注册设备。</span><span class="sxs-lookup"><span data-stu-id="a3e36-171">**Reseller can register devices in the Partner Center when you place an order.**</span></span>

   > [!NOTE]  
   > <span data-ttu-id="a3e36-172">这是添加设备到 Autopilot 服务的推荐方法。</span><span class="sxs-lookup"><span data-stu-id="a3e36-172">This is the recommended path for adding devices to the Autopilot service.</span></span> <span data-ttu-id="a3e36-173">[了解详细信息](/mem/autopilot/partner-registration)。</span><span class="sxs-lookup"><span data-stu-id="a3e36-173">[Learn more](/mem/autopilot/partner-registration).</span></span>  

 - <span data-ttu-id="a3e36-174">你可以直接向 Microsoft [提交支持请求](hololens2-autopilot-registration-support.md)。</span><span class="sxs-lookup"><span data-stu-id="a3e36-174">**You can [submit a support request](hololens2-autopilot-registration-support.md) directly to Microsoft.**</span></span>
 - <span data-ttu-id="a3e36-175">检索硬件哈希（也称为硬件 ID）并在 MEM 管理中心手动注册设备。</span><span class="sxs-lookup"><span data-stu-id="a3e36-175">**Retrieve the hardware hash (also known as the hardware ID) and register the device manually in MEM admin center**.</span></span>

#### <a name="obtain-hardware-hash"></a><span data-ttu-id="a3e36-176">获取硬件哈希</span><span class="sxs-lookup"><span data-stu-id="a3e36-176">Obtain hardware hash</span></span>
<span data-ttu-id="a3e36-177">检索硬件哈希有两种方法。</span><span class="sxs-lookup"><span data-stu-id="a3e36-177">There are two ways to retrieve the hardware hash.</span></span>
1. <span data-ttu-id="a3e36-178">你可以直接向 Microsoft [提交支持请求](hololens2-autopilot-registration-support.md)。</span><span class="sxs-lookup"><span data-stu-id="a3e36-178">You can [submit a support request](hololens2-autopilot-registration-support.md) directly to Microsoft.</span></span>
2. <span data-ttu-id="a3e36-179">你也可以从设备中对其进行检索。</span><span class="sxs-lookup"><span data-stu-id="a3e36-179">You can retrieve it from the device.</span></span> <span data-ttu-id="a3e36-180">设备在进行 OOBE 过程时，或之后当设备所有者启动诊断日志收集过程时（在以下过程中描述），设备将其硬件哈希记录在 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="a3e36-180">The device records its hardware hash in a CSV file during the OOBE process, or later when a device owner starts the diagnostic log collection process (described in the following procedure).</span></span> <span data-ttu-id="a3e36-181">通常情况下，设备所有者是第一个登录到设备的用户。</span><span class="sxs-lookup"><span data-stu-id="a3e36-181">Typically, the device owner is the first user to sign in to the device.</span></span>
     > [!WARNING]
     > <span data-ttu-id="a3e36-182">在 20H2 之前的内部版本中，如果已进行 OOBE 过程，并且遥测设置为“必需”，则无法通过此方法收集 Autopilot 的硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="a3e36-182">In builds prior to 20H2, if you have gone through OOBE and the telemetry was set to Required, you cannot collect the hardware hash for Autopilot through this method.</span></span> <span data-ttu-id="a3e36-183">为了通过此方法收集硬件哈希，请通过“设置应用”将遥测选项设置为“完全”，并选择“隐私”>“诊断”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-183">In          order to collect your hardware hash via this method set your telemetry option to Full via the Settings App and select Privacy -> Diagnostics.</span></span>

    1. <span data-ttu-id="a3e36-184">启动 HoloLens 2 设备。</span><span class="sxs-lookup"><span data-stu-id="a3e36-184">Start the HoloLens 2 device.</span></span>

    1. <span data-ttu-id="a3e36-185">在设备上，同时按下“电源”和“调低音量”按钮，然后释放这两个按钮 。</span><span class="sxs-lookup"><span data-stu-id="a3e36-185">On the device, press the **Power** and **Volume Down** buttons at the same time and then release them.</span></span> <span data-ttu-id="a3e36-186">设备将收集诊断日志和硬件哈希，并将它们存储在一组 .zip 文件中。</span><span class="sxs-lookup"><span data-stu-id="a3e36-186">The device collects diagnostic logs and the hardware hash, and stores them in a set of .zip files.</span></span>

   1. <span data-ttu-id="a3e36-187">有关如何执行此操作的完整详细信息和指导视频，请阅读有关[脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics)。</span><span class="sxs-lookup"><span data-stu-id="a3e36-187">For full details and an instructional video for how to preform this please read about [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span>

    1. <span data-ttu-id="a3e36-188">使用 USB-C 电缆将设备连接到计算机。</span><span class="sxs-lookup"><span data-stu-id="a3e36-188">Use a USB-C cable to connect the device to a computer.</span></span>

    1. <span data-ttu-id="a3e36-189">在计算机上，打开文件资源管理器。</span><span class="sxs-lookup"><span data-stu-id="a3e36-189">On the computer, open File Explorer.</span></span> <span data-ttu-id="a3e36-190">打开 This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents，找到 AutopilotDiagnostics.zip 文件。</span><span class="sxs-lookup"><span data-stu-id="a3e36-190">Open **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**, and locate the AutopilotDiagnostics.zip file.</span></span>  

       > [!NOTE]  
       > <span data-ttu-id="a3e36-191">.zip 文件可能不会立即可用。</span><span class="sxs-lookup"><span data-stu-id="a3e36-191">The .zip file may not immediately be available.</span></span> <span data-ttu-id="a3e36-192">如果文件尚未准备好，可能会在“文档”文件夹中看到一个 HoloLensDiagnostics.temp文件。</span><span class="sxs-lookup"><span data-stu-id="a3e36-192">If the file is not ready yet you may see a HoloLensDiagnostics.temp file in the Documents folder.</span></span> <span data-ttu-id="a3e36-193">若要更新文件列表，请刷新窗口。</span><span class="sxs-lookup"><span data-stu-id="a3e36-193">To update the list of files, refresh the window.</span></span>
    
    1. <span data-ttu-id="a3e36-194">提取 AutopilotDiagnostics.zip 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="a3e36-194">Extract the contents of the AutopilotDiagnostics.zip file.</span></span>

    1. <span data-ttu-id="a3e36-195">在提取的文件中，找到文件名前缀为 “DeviceHash”的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="a3e36-195">In the extracted files, locate the CSV file that has a file name prefix of "DeviceHash."</span></span> <span data-ttu-id="a3e36-196">将该文件复制到计算机的驱动器中，方便以后在此处访问该文件。</span><span class="sxs-lookup"><span data-stu-id="a3e36-196">Copy that file to a drive on the computer where you can access it later.</span></span>  

       > [!IMPORTANT]  
       > <span data-ttu-id="a3e36-197">CSV 文件中的数据应使用以下标题和行格式：</span><span class="sxs-lookup"><span data-stu-id="a3e36-197">The data in the CSV file should use the following header and line format:</span></span>
       > ```
       > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
       >```

#### <a name="register-device-through-mem"></a><span data-ttu-id="a3e36-198">通过 MEM 注册设备</span><span class="sxs-lookup"><span data-stu-id="a3e36-198">Register device through MEM</span></span>

1. <span data-ttu-id="a3e36-199">在 [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com)中，选择“设备” > “Windows” > “Windows 注册”，然后选择“Windows Autopilot Deployment 计划”下的“设备” > “导入”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-199">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment**, and then select **Devices** > **Import** under **Windows Autopilot Deployment Program**.</span></span>

1. <span data-ttu-id="a3e36-200">在“添加 Windows Autopilot 设备”下，选择 DeviceHash CSV 文件，选择“打开”，再选择“导入”  。</span><span class="sxs-lookup"><span data-stu-id="a3e36-200">Under **Add Windows Autopilot devices**, select the DeviceHash CSV file, select **Open**, and then select **Import**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a3e36-201">![使用“导入”命令导入硬件哈希。](./images/hololens-ap-hash-import.png)</span><span class="sxs-lookup"><span data-stu-id="a3e36-201">![Use the Import command to import the hardware hash.](./images/hololens-ap-hash-import.png)</span></span>

1. <span data-ttu-id="a3e36-202">导入完成后，选择“设备” > “Windows” > “Windows 注册” > “设备” > “同步”。此过程可能需要几分钟才能完成，具体取决于要同步的设备数。</span><span class="sxs-lookup"><span data-stu-id="a3e36-202">After the import finishes, select **Devices** > **Windows** > **Windows enrollment** > **Devices** > **Sync**. The process might take a few minutes to complete, depending on how many devices are being synchronized.</span></span> <span data-ttu-id="a3e36-203">若要查看已注册的设备，请选择“刷新”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-203">To see the registered device, select **Refresh**.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a3e36-204">![使用“同步”和“刷新”命令查看设备列表。](./images/hololens-ap-devices-sync.png)</span><span class="sxs-lookup"><span data-stu-id="a3e36-204">![Use the Sync and Refresh commands to view the device list.](./images/hololens-ap-devices-sync.png)</span></span>  

### <a name="4-create-a-device-group"></a><span data-ttu-id="a3e36-205">4. 创建设备组</span><span class="sxs-lookup"><span data-stu-id="a3e36-205">4. Create a device group</span></span>

1. <span data-ttu-id="a3e36-206">在 [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com)中，选择“组” > “新建组”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-206">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Groups** > **New group**.</span></span>

1. <span data-ttu-id="a3e36-207">对于“组类型”，选择“安全性” ，然后输入组名称和说明。</span><span class="sxs-lookup"><span data-stu-id="a3e36-207">For **Group type**, select **Security**, and then enter a group name and description.</span></span>

1. <span data-ttu-id="a3e36-208">对于“成员身份类型”，选择“已分配”或“动态设备”  。</span><span class="sxs-lookup"><span data-stu-id="a3e36-208">For **Membership type**, select either **Assigned** or **Dynamic Device**.</span></span>

1. <span data-ttu-id="a3e36-209">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="a3e36-209">Do one of the following:</span></span>  

   - <span data-ttu-id="a3e36-210">如果在上一步中为“成员身份类型”选择了“已分配”，请选择“成员”  ，然后将 Autopilot 设备添加到组。</span><span class="sxs-lookup"><span data-stu-id="a3e36-210">If you selected **Assigned** for **Membership type** in the previous step, select **Members**, and then add Autopilot devices to the group.</span></span> <span data-ttu-id="a3e36-211">通过将设备序列号用作设备名称，列出尚未注册的 Autopilot 设备。</span><span class="sxs-lookup"><span data-stu-id="a3e36-211">Autopilot devices that aren't yet enrolled are listed by using the device serial number as the device name.</span></span>
   - <span data-ttu-id="a3e36-212">如果在上一步中为“成员身份类型”选择了“动态设备”，请选择“动态设备成员”  ，然后在“高级规则”中输入类似于以下内容的代码：</span><span class="sxs-lookup"><span data-stu-id="a3e36-212">If you selected **Dynamic Devices** for **Membership type** in the previous step, select **Dynamic device members**, and then enter code in **Advanced rule** that resembles the following:</span></span>
     - <span data-ttu-id="a3e36-213">若要创建包括所有 Autopilot 设备的组，请键入：`(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`</span><span class="sxs-lookup"><span data-stu-id="a3e36-213">If you want to create a group that includes all of your Autopilot devices, type: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`</span></span>
     - <span data-ttu-id="a3e36-214">Intune 的组标签字段映射到 Azure AD 设备上的 OrderID 属性。</span><span class="sxs-lookup"><span data-stu-id="a3e36-214">Intune's group tag field maps to the **OrderID** attribute on Azure AD devices.</span></span> <span data-ttu-id="a3e36-215">如果要创建一个包含所有具有特定组标签的 Autopilot 设备的组（Azure AD 设备 OrderID），必须键入：`(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`</span><span class="sxs-lookup"><span data-stu-id="a3e36-215">If you want to create a group that includes all of your Autopilot devices that have a specific group tag (the Azure AD device OrderID), you must type: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`</span></span>
     - <span data-ttu-id="a3e36-216">如果想要创建包含所有具有特定采购订单 ID 的 Autopilot 设备的组，请键入：`(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`</span><span class="sxs-lookup"><span data-stu-id="a3e36-216">If you want to create a group that includes all your Autopilot devices that have a specific Purchase Order ID, type: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`</span></span>

     > [!NOTE]  
     > <span data-ttu-id="a3e36-217">这些规则针对 Autopilot 设备独有的属性。</span><span class="sxs-lookup"><span data-stu-id="a3e36-217">These rules target attributes that are unique to Autopilot devices.</span></span>
1. <span data-ttu-id="a3e36-218">依次选择“保存”和“创建”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-218">Select **Save**, and then select **Create**.</span></span>

### <a name="5-create-a-deployment-profile"></a><span data-ttu-id="a3e36-219">5. 创建部署配置文件</span><span class="sxs-lookup"><span data-stu-id="a3e36-219">5. Create a deployment profile</span></span>

1. <span data-ttu-id="a3e36-220">在 [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com)中，依次选择选择“设备” > “Windows” > “Windows 注册” > “Windows Autopilot 部署配置文件” > “创建配置文件” > “HoloLens”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-220">In [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com), select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens**.</span></span>
   <span data-ttu-id="a3e36-221">![“创建配置文件”下拉菜单包括一个 HoloLens 项。](./images/hololens-ap-enrollment-profiles.png)</span><span class="sxs-lookup"><span data-stu-id="a3e36-221">![Create profile dropdown includes a HoloLens item.](./images/hololens-ap-enrollment-profiles.png)</span></span>

1. <span data-ttu-id="a3e36-222">输入配置文件名称和说明，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-222">Enter a profile name and description, and then select **Next**.</span></span>  
   <span data-ttu-id="a3e36-223">你将看到一个包含 HoloLens 的列表。</span><span class="sxs-lookup"><span data-stu-id="a3e36-223">You should see a list that includes **HoloLens**.</span></span> <span data-ttu-id="a3e36-224">如果不存在此选项，请使用[反馈](hololens2-autopilot.md#feedback-and-support-for-autopilot)选项之一与我们联系。</span><span class="sxs-lookup"><span data-stu-id="a3e36-224">If this option is not present, use one of the [Feedback](hololens2-autopilot.md#feedback-and-support-for-autopilot) options to contact us.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a3e36-225">![添加配置文件名称和说明](./images/hololens-ap-profile-name.png)</span><span class="sxs-lookup"><span data-stu-id="a3e36-225">![Add a profile name and description](./images/hololens-ap-profile-name.png)</span></span>

1. <span data-ttu-id="a3e36-226">在“全新体验(OOBE)”页上，大多数设置已预先配置，以简化此评估的 OOBE。</span><span class="sxs-lookup"><span data-stu-id="a3e36-226">On the **Out-of-box experience (OOBE)** page, most of the settings are pre-configured to streamline OOBE for this evaluation.</span></span> <span data-ttu-id="a3e36-227">另外，还可配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="a3e36-227">Optionally, you can configure the following settings:</span></span>  

   - <span data-ttu-id="a3e36-228">“语言(地区)”：选择 OOBE 的语言。</span><span class="sxs-lookup"><span data-stu-id="a3e36-228">**Language (Region)**: Select the language for OOBE.</span></span> <span data-ttu-id="a3e36-229">建议从 [HoloLens 2 支持的语言](hololens2-language-support.md)列表中选择一种语言。</span><span class="sxs-lookup"><span data-stu-id="a3e36-229">We recommend that you select a language from the list of [supported languages for HoloLens 2](hololens2-language-support.md).</span></span>
   - <span data-ttu-id="a3e36-230">“自动配置键盘”：若要确保键盘与所选语言匹配，请选择“是”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-230">**Automatically configure keyboard**: To make sure that the keyboard matches the selected language, select **Yes**.</span></span>
   - <span data-ttu-id="a3e36-231">“应用设备名称模板”：若要在 OOBE 期间自动设置设备名称，请选择“是”，然后在“输入一个名称”中输入模板短语和占位符，例如，输入前缀和 `%RAND:4%` &mdash; 四位随机数字的占位符。</span><span class="sxs-lookup"><span data-stu-id="a3e36-231">**Apply device name template**: To automatically set the device name during OOBE, select **Yes** and then enter the template phrase and placeholders in **Enter a name** For example, enter a prefix and `%RAND:4%`&mdash;a placeholder for a four-digit random number.</span></span>
     > [!NOTE]  
     > <span data-ttu-id="a3e36-232">如果使用设备名称模板，OOBE 进程将在应用设备名称之后和将设备加入 Azure AD 之前再次重新启动该设备。</span><span class="sxs-lookup"><span data-stu-id="a3e36-232">If you use a device name template, the OOBE process restarts the device one additional time after it applies the device name and before it joins the device to Azure AD.</span></span> <span data-ttu-id="a3e36-233">重新启动后，新名称才会生效。</span><span class="sxs-lookup"><span data-stu-id="a3e36-233">This restart enables the new name to take effect.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a3e36-234">![配置 OOBE 设置](./images/hololens-ap-profile-oobe.png)</span><span class="sxs-lookup"><span data-stu-id="a3e36-234">![Configure OOBE settings](./images/hololens-ap-profile-oobe.png)</span></span>

1. <span data-ttu-id="a3e36-235">配置设置后，选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-235">After you configure the settings, select **Next**.</span></span>
1. <span data-ttu-id="a3e36-236">在“作用域标签”页上，按需添加要应用到此配置文件的作用域标签。</span><span class="sxs-lookup"><span data-stu-id="a3e36-236">On the **Scope tags** page, optionally add the scope tags that you want to apply to this profile.</span></span> <span data-ttu-id="a3e36-237">若要详细了解作用域标记，请参阅[将基于角色的访问控制和作用域标记用于分布式 IT](/mem/intune/fundamentals/scope-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="a3e36-237">For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](/mem/intune/fundamentals/scope-tags.md).</span></span> <span data-ttu-id="a3e36-238">完成后，选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-238">When finished, select **Next**.</span></span>
1. <span data-ttu-id="a3e36-239">在“分配”页上，为“分配给”选择“所选组”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-239">On the **Assignments** page, select **Selected groups** for **Assign to**.</span></span>
1. <span data-ttu-id="a3e36-240">在“所选组”下，选择“+ 选择要包括的组”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-240">Under **SELECTED GROUPS**, select **+ Select groups to include**.</span></span>
1. <span data-ttu-id="a3e36-241">在“选择要包括的组”列表中，选择为 Autopilot HoloLens 设备创建的设备组，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-241">In the **Select groups to include** list, select the device group that you created for the Autopilot HoloLens devices, and then select **Next**.</span></span>  
  
   <span data-ttu-id="a3e36-242">如果要排除任何组，请选择“选择要排除的组”，然后选择要排除的组。</span><span class="sxs-lookup"><span data-stu-id="a3e36-242">If you want to exclude any groups, select **Select groups to exclude**, and select the groups that you want to exclude.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a3e36-243">![将设备组分配给配置文件。](./images/hololens-ap-profile-assign-devicegroup.png)</span><span class="sxs-lookup"><span data-stu-id="a3e36-243">![Assigning a device group to the profile.](./images/hololens-ap-profile-assign-devicegroup.png)</span></span>

1. <span data-ttu-id="a3e36-244">在“查看 + 创建”页上，查看设置，然后选择“创建”创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="a3e36-244">On the **Review + Create** page, review the settings and then select **Create** to create the profile.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a3e36-245">![审阅 + 创建](./images/hololens-ap-profile-summ.png)</span><span class="sxs-lookup"><span data-stu-id="a3e36-245">![Review + create](./images/hololens-ap-profile-summ.png)</span></span>

### <a name="6-verify-the-esp-configuration"></a><span data-ttu-id="a3e36-246">6. 验证 ESP 配置</span><span class="sxs-lookup"><span data-stu-id="a3e36-246">6. Verify the ESP configuration</span></span>

<span data-ttu-id="a3e36-247">注册状态页面 (ESP) 显示完整的设备配置过程的状态，此过程在 MDM 托管用户首次登录设备时运行。</span><span class="sxs-lookup"><span data-stu-id="a3e36-247">The Enrollment Status Page (ESP) displays the status of the complete device configuration process that runs when an MDM managed user signs into a device for the first time.</span></span> <span data-ttu-id="a3e36-248">请确保你的 ESP 配置类似于以下内容，并验证分配是否正确。</span><span class="sxs-lookup"><span data-stu-id="a3e36-248">Make sure that your ESP configuration resembles the following, and verify that the assignments are correct.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a3e36-249">![ESP 配置](./images/hololens-ap-profile-settings.png)</span><span class="sxs-lookup"><span data-stu-id="a3e36-249">![ESP configuration](./images/hololens-ap-profile-settings.png)</span></span>

### <a name="7-verify-the-profile-status-of-the-hololens-devices"></a><span data-ttu-id="a3e36-250">7. 验证 HoloLens 设备的配置文件状态</span><span class="sxs-lookup"><span data-stu-id="a3e36-250">7. Verify the profile status of the HoloLens devices</span></span>

1. <span data-ttu-id="a3e36-251">在 Microsoft Endpoint Manager 管理中心中，依次选择“设备” > “Windows” > “Windows 注册” > “设备”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-251">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment** > **Devices**.</span></span>

1. <span data-ttu-id="a3e36-252">验证是否列出了 HoloLens 设备，以及其配置文件的状态是否为“已分配”。</span><span class="sxs-lookup"><span data-stu-id="a3e36-252">Verify that the HoloLens devices are listed, and that their profile status is **Assigned**.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="a3e36-253">可能需要几分钟的时间才能将配置文件分配给设备。</span><span class="sxs-lookup"><span data-stu-id="a3e36-253">It may take a few minutes for the profile to be assigned to the device.</span></span>  

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a3e36-254">![设备和配置文件分配。](./images/hololens-ap-devices-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="a3e36-254">![Device and profile assignments.](./images/hololens-ap-devices-assignments.png)</span></span>

## <a name="windows-autopilot-for-hololens-2-user-experience"></a><span data-ttu-id="a3e36-255">适用于 HoloLens 2 的 Windows Autopilot 用户体验</span><span class="sxs-lookup"><span data-stu-id="a3e36-255">Windows Autopilot for HoloLens 2 User Experience</span></span>

<span data-ttu-id="a3e36-256">完成上述说明操作后，HoloLens 2 用户将通过以下体验来预配其 HoloLens 设备：</span><span class="sxs-lookup"><span data-stu-id="a3e36-256">Once the above instructions are completed, your HoloLens 2 users will go through the following experience to provision their HoloLens devices:</span></span>  

1. <span data-ttu-id="a3e36-257">Autopilot 体验需要访问 Internet。</span><span class="sxs-lookup"><span data-stu-id="a3e36-257">Autopilot experience requires internet access.</span></span> <span data-ttu-id="a3e36-258">请使用以下选项之一提供 Internet 访问：</span><span class="sxs-lookup"><span data-stu-id="a3e36-258">Please use one of following options to provide internet access:</span></span>

    - <span data-ttu-id="a3e36-259">在 OOBE 期间，将设备连接到 Wi-Fi 网络，然后让它自动检测 Autopilot 体验。</span><span class="sxs-lookup"><span data-stu-id="a3e36-259">Connect your device to a Wi-Fi network in OOBE and then let it detect Autopilot experience automatically.</span></span> <span data-ttu-id="a3e36-260">这是唯一需要你与 OOBE 交互的地方，直到 Autopilot 体验自行完成。</span><span class="sxs-lookup"><span data-stu-id="a3e36-260">This is the only time you will need to interact with OOBE until Autopilot experience completes on its own.</span></span> <span data-ttu-id="a3e36-261">请注意，默认情况下，HoloLens 2 在检测到 Internet 后会等待 10 秒以检测 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="a3e36-261">Please note that by default HoloLens 2 waits for 10 seconds to detect Autopilot after detecting internet.</span></span> <span data-ttu-id="a3e36-262">如果在 10 秒内未检测到 autopilot 配置文件，OOBE 将显示 EULA。</span><span class="sxs-lookup"><span data-stu-id="a3e36-262">If no autopilot profile is detected within 10 seconds, OOBE will present EULA.</span></span> <span data-ttu-id="a3e36-263">如果遇到这种情况，请重新启动你的设备，以便再次尝试检测 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="a3e36-263">If you encounter this scenario, please reboot your device so another attempt can be made to detect Autopilot.</span></span> <span data-ttu-id="a3e36-264">另请注意，只有在设备上设置了 TenantLockdown 策略时，OOBE 才会无限期地等待 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="a3e36-264">Please also note that OOBE can wait indefinitely for Autopilot only if TenantLockdown policy is set on the device.</span></span>

    - <span data-ttu-id="a3e36-265">使用“USB-C 转以太网”适配器将设备与以太网连接，以实现有线 Internet 连接，并让 HoloLens 2 自动完成 Autopilot 体验。</span><span class="sxs-lookup"><span data-stu-id="a3e36-265">Connect your device with Ethernet using "USB-C to Ethernet" adapters for wired internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

    - <span data-ttu-id="a3e36-266">通过“USB-C 转 Wifi”适配器连接设备以实现无线 Internet 连接，并让 HoloLens 2 自动完成 Autopilot 体验。</span><span class="sxs-lookup"><span data-stu-id="a3e36-266">Connect your device with "USB-C to Wifi" adapters for wireless internet connectivity and let HoloLens 2 complete Autopilot experience automatically.</span></span>

        > [!IMPORTANT]  
       > <span data-ttu-id="a3e36-267">尝试在 OOBE 过程中使用 Wi-Fi 网络完成 Autopilot 体验的设备必须使用 [Windows 全息版（版本 20H2）](hololens-release-notes.md#windows-holographic-version-20h2)。</span><span class="sxs-lookup"><span data-stu-id="a3e36-267">Devices attempting to use Wi-Fi networks in OOBE for Autopilot must be on [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2).</span></span>
       >
       > <span data-ttu-id="a3e36-268">对于使用以太网适配器的设备，必须在全新体验 (OOBE) 启动之前将设备连接到网络。</span><span class="sxs-lookup"><span data-stu-id="a3e36-268">For devices using ethernet adapters you must connect the device to the network before the Out-of-the-Box-Experience (OOBE) starts.</span></span> <span data-ttu-id="a3e36-269">设备在第一个 OOBE 屏幕上确定是否将其预配为 Autopilot 设备。</span><span class="sxs-lookup"><span data-stu-id="a3e36-269">The device determines whether it is provisioning as an Autopilot device while on the first OOBE screen.</span></span> <span data-ttu-id="a3e36-270">如果设备无法连接到网络，或者如果选择不将设备预配为 Autopilot 设备，则以后无法更改为 Autopilot 预配。</span><span class="sxs-lookup"><span data-stu-id="a3e36-270">If the device cannot connect to the network, or if you choose not to provision the device as an Autopilot device, you cannot change to Autopilot provisioning at a later time.</span></span> <span data-ttu-id="a3e36-271">相反，必须重新开始此过程，才能将设备预配为 Autopilot 设备。</span><span class="sxs-lookup"><span data-stu-id="a3e36-271">Instead, you would have to start this procedure over in order to provision the device as an Autopilot device.</span></span>

1. <span data-ttu-id="a3e36-272">设备应自动启动 OOBE。</span><span class="sxs-lookup"><span data-stu-id="a3e36-272">The device should automatically start OOBE.</span></span> <span data-ttu-id="a3e36-273">不要与 OOBE 交互。</span><span class="sxs-lookup"><span data-stu-id="a3e36-273">Do not interact with OOBE.</span></span> <span data-ttu-id="a3e36-274">坐下来放松一下！</span><span class="sxs-lookup"><span data-stu-id="a3e36-274">Instead sit, back and relax!</span></span> <span data-ttu-id="a3e36-275">让 HoloLens 2 检测网络连接并允许它自动完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="a3e36-275">Let HoloLens 2 detect network connectivity and allow it complete OOBE automatically.</span></span> <span data-ttu-id="a3e36-276">设备可能会在 OOBE 过程中重启。</span><span class="sxs-lookup"><span data-stu-id="a3e36-276">The device may restart during OOBE.</span></span> <span data-ttu-id="a3e36-277">OOBE 屏幕应类似于以下内容。</span><span class="sxs-lookup"><span data-stu-id="a3e36-277">The OOBE screens should resemble the following.</span></span>

   <span data-ttu-id="a3e36-278">![OOBE 步骤 1](./images/autopilot-welcome.jpg)
   ![OOBE 步骤 2](./images/autopilot-step-complete.jpg)
   ![OOBE 步骤 3](./images/autopilot-device-setup.jpg)</span><span class="sxs-lookup"><span data-stu-id="a3e36-278">![OOBE step 1](./images/autopilot-welcome.jpg)
![OOBE step 2](./images/autopilot-step-complete.jpg)
![OOBE step 3](./images/autopilot-device-setup.jpg)</span></span>

1. <span data-ttu-id="a3e36-279">OOBE 结束时，你可以使用用户名和密码登录到设备。</span><span class="sxs-lookup"><span data-stu-id="a3e36-279">At the end of OOBE, you can sign in to the device by using your user name and password.</span></span>

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenantlockdown-csp-and-autopilot"></a><span data-ttu-id="a3e36-280">Tenantlockdown 云解决方案提供商和 Autopilot</span><span class="sxs-lookup"><span data-stu-id="a3e36-280">Tenantlockdown CSP and Autopilot</span></span>

<span data-ttu-id="a3e36-281">从 Windows 全息版（版本 20H2）起，HoloLens 2 设备支持 TenantLockdown 云解决方案提供商。</span><span class="sxs-lookup"><span data-stu-id="a3e36-281">HoloLens 2 devices support TenantLockdown CSP as of Windows Holographic, version 20H2.</span></span> <span data-ttu-id="a3e36-282">该云解决方案提供商将设备锁定在组织的租户上，即使在设备重置或重刷的情况下，也能将设备保持在该租户上。</span><span class="sxs-lookup"><span data-stu-id="a3e36-282">This CSP keeps devices on the organization's tenant by locking them to that tenant even through device reset or reflash.</span></span>

<span data-ttu-id="a3e36-283">[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) 云解决方案提供商允许仅使用 Autopilot 将 HoloLens 2 绑定到 MDM 注册。</span><span class="sxs-lookup"><span data-stu-id="a3e36-283">[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) CSP enables HoloLens 2 to be tied to MDM enrollment using Autopilot only.</span></span> <span data-ttu-id="a3e36-284">在 HoloLens 2 上将 TenantLockdown 云解决方案提供商的 RequireNetworkInOOBE 节点设置为 true 或 false（初始设置）值后，即使执行了重刷、操作系统更新等操作，值仍将保留在设备上。</span><span class="sxs-lookup"><span data-stu-id="a3e36-284">Once TenantLockdown CSP’s RequireNetworkInOOBE node is set to either true or false (initially set) value on HoloLens 2, that value remains on the device despite re-flashing, OS updates, etc.</span></span>

<span data-ttu-id="a3e36-285">在 HoloLens 2 上将 TenantLockdown 云解决方案提供商的 RequireNetworkInOOBE 节点设置为 true 后，OOBE 将无限期等待 Autopilot 配置文件在网络连接后成功下载并应用。</span><span class="sxs-lookup"><span data-stu-id="a3e36-285">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, OOBE waits indefinitely for Autopilot profile to be successfully downloaded and applied, after network connectivity.</span></span>

<span data-ttu-id="a3e36-286">在 HoloLens 2 上将 TenantLockdown 云解决方案提供商的 RequireNetworkInOOBE 节点设置为 true 后，OOBE 中将不允许执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a3e36-286">Once TenantLockdown CSPs’ RequireNetworkInOOBE node is set to true on HoloLens 2, following operations are disallowed in OOBE:</span></span>

- <span data-ttu-id="a3e36-287">使用运行时预配创建本地用户</span><span class="sxs-lookup"><span data-stu-id="a3e36-287">Creating local user using runtime provisioning</span></span> 
- <span data-ttu-id="a3e36-288">通过运行时预配执行 Azure AD 加入操作</span><span class="sxs-lookup"><span data-stu-id="a3e36-288">Performing Azure AD join operation via runtime provisioning</span></span> 
- <span data-ttu-id="a3e36-289">选择 OOBE 体验中的设备所有者</span><span class="sxs-lookup"><span data-stu-id="a3e36-289">Selecting who owns the device in OOBE experience</span></span> 

#### <a name="how-to-set-this-using-intune"></a><span data-ttu-id="a3e36-290">如何使用 Intune 对此进行设置？</span><span class="sxs-lookup"><span data-stu-id="a3e36-290">How to set this using Intune?</span></span> 
1. <span data-ttu-id="a3e36-291">创建自定义 OMA URI 设备配置文件，并为 RequireNetworkInOOBE 节点指定 true，如下所示。</span><span class="sxs-lookup"><span data-stu-id="a3e36-291">Create a custom OMA URI device configuration profile and specify true for RequireNetworkInOOBE node as shown below.</span></span>
<span data-ttu-id="a3e36-292">OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span><span class="sxs-lookup"><span data-stu-id="a3e36-292">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a3e36-293">![通过 OMA-URI 设置租户锁定](images/hololens-tenant-lockdown.png)</span><span class="sxs-lookup"><span data-stu-id="a3e36-293">![Setting tennant lockdown via OMA-URI](images/hololens-tenant-lockdown.png)</span></span>

1. <span data-ttu-id="a3e36-294">创建组并将设备配置文件分配给该设备组。</span><span class="sxs-lookup"><span data-stu-id="a3e36-294">Create a group and assign the device configuration profile to that device group.</span></span>

1. <span data-ttu-id="a3e36-295">使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。</span><span class="sxs-lookup"><span data-stu-id="a3e36-295">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>  

<span data-ttu-id="a3e36-296">在 Intune 门户中验证设备配置是否已成功应用。</span><span class="sxs-lookup"><span data-stu-id="a3e36-296">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="a3e36-297">此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的影响将处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="a3e36-297">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be active.</span></span>

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a><span data-ttu-id="a3e36-298">如何使用 Intune 在 HoloLens 2 上取消设置 TenantLockdown 的 RequireNetworkInOOBE？</span><span class="sxs-lookup"><span data-stu-id="a3e36-298">How to unset TenantLockdown’s RequireNetworkInOOBE on HoloLens 2 using Intune?</span></span>

1. <span data-ttu-id="a3e36-299">将 HoloLens 2 从先前分配了上面创建的设备配置的设备组中删除。</span><span class="sxs-lookup"><span data-stu-id="a3e36-299">Remove the HoloLens 2 from the device group to which the device configuration created above was previously assigned.</span></span>

1. <span data-ttu-id="a3e36-300">创建基于 OMA URI 的自定义设备配置文件，并为 RequireNetworkInOOBE 指定 false，如下所示。</span><span class="sxs-lookup"><span data-stu-id="a3e36-300">Create a custom OMA URI based device configuration profile and specify false for RequireNetworkInOOBE as shown below.</span></span>
<span data-ttu-id="a3e36-301">OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span><span class="sxs-lookup"><span data-stu-id="a3e36-301">OMA-URI value should be ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a3e36-302">![在 Intune 中通过 OMA URI 将 RequireNetworkInOOBE 设置为 false 的屏幕截图](images/hololens-tenant-lockdown-false.png)</span><span class="sxs-lookup"><span data-stu-id="a3e36-302">![Screenshot of setting RequireNetworkInOOBE to false via OMA URI in Intune](images/hololens-tenant-lockdown-false.png)</span></span>

1. <span data-ttu-id="a3e36-303">创建组并将设备配置文件分配给该设备组。</span><span class="sxs-lookup"><span data-stu-id="a3e36-303">Create a group and assign the device configuration profile to that device group.</span></span> 

1. <span data-ttu-id="a3e36-304">使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。</span><span class="sxs-lookup"><span data-stu-id="a3e36-304">Make the HoloLens 2 device member of the group created in previous step and trigger sync.</span></span>

<span data-ttu-id="a3e36-305">在 Intune 门户中验证设备配置是否已成功应用。</span><span class="sxs-lookup"><span data-stu-id="a3e36-305">Verify in the Intune portal that device configuration has been successfully applied.</span></span> <span data-ttu-id="a3e36-306">此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的影响将处于非活动状态。</span><span class="sxs-lookup"><span data-stu-id="a3e36-306">Once this device configuration successfully applies on the HoloLens 2 device, effects of TenantLockdown will be inactive.</span></span>

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a><span data-ttu-id="a3e36-307">将 TenantLockdown 设置为 true 后，如果在 HoloLens 上取消分配 Autopilot 配置文件，在 OOBE 期间会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="a3e36-307">What would happen during OOBE, if Autopilot profile is unassigned on a HoloLens after TenantLockdown was set to true?</span></span> 
<span data-ttu-id="a3e36-308">OOBE 将无限期等待 Autopilot 配置文件下载，并将显示以下对话框。</span><span class="sxs-lookup"><span data-stu-id="a3e36-308">OOBE will wait indefinitely for Autopilot profile to download and following dialog will be presented.</span></span> <span data-ttu-id="a3e36-309">为了删除 TenantLockdown 的影响，必须首先仅使用 Autopilot 将设备注册到其原始租户，并且必须按照上一步中的说明取消设置 RequireNetworkInOOBE，然后才能删除 TenantLockdown 云解决方案提供商引入的限制。</span><span class="sxs-lookup"><span data-stu-id="a3e36-309">In order to remove effects of TenantLockdown, device must be enrolled with its original tenant first using Autopilot only and RequireNetworkInOOBE must be unset as described in previous step before restrictions introduced by TenantLockdown CSP are removed.</span></span>

![在设备上实施策略时的设备内视图。](images/hololens-autopilot-lockdown.png)

## <a name="known-issues--limitations"></a><span data-ttu-id="a3e36-311">已知问题和限制</span><span class="sxs-lookup"><span data-stu-id="a3e36-311">Known Issues & limitations</span></span>

- <span data-ttu-id="a3e36-312">我们正在研究在 MEM 中配置的基于设备上下文的应用程序安装不适用于 HoloLens 的问题。</span><span class="sxs-lookup"><span data-stu-id="a3e36-312">We are investigating an issue where device-context based application install configured in MEM does not apply to HoloLens.</span></span> [<span data-ttu-id="a3e36-313">了解有关设备上下文和用户上下文安装的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a3e36-313">Learn more about device context and user context installs.</span></span>](/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- <span data-ttu-id="a3e36-314">通过 Wi-Fi 设置 Autopilot 时，可能会出现首次建立 Internet 连接时未能下载 Autopilot 配置文件的问题。</span><span class="sxs-lookup"><span data-stu-id="a3e36-314">While setting up Autopilot over Wi-Fi, there may be an instance where the Autopilot profile is not downloaded when Internet connection is first established.</span></span> <span data-ttu-id="a3e36-315">在这种情况下，将显示最终用户许可协议 (EULA) ，并且用户可以选择继续执行非 Autopilot 设置体验。</span><span class="sxs-lookup"><span data-stu-id="a3e36-315">In this case End User License Agreement (EULA) is presented and the user has the option to proceed with non-Autopilot setup experience.</span></span> <span data-ttu-id="a3e36-316">若要重试 Autopilot 设置，请将设备置于睡眠状态，然后重新启动，或者重启设备，然后重试。</span><span class="sxs-lookup"><span data-stu-id="a3e36-316">To retry setting up with Autopilot, put the device to sleep and then power up, or reboot the device and let it try again.</span></span>
- <span data-ttu-id="a3e36-317">HoloLens 目前暂不支持“将所有目标设备转换为 Autopilot”的功能。</span><span class="sxs-lookup"><span data-stu-id="a3e36-317">"Convert all targeted devices to Autopilot" feature is not supported on HoloLens at the moment.</span></span>  

### <a name="troubleshooting"></a><span data-ttu-id="a3e36-318">疑难解答</span><span class="sxs-lookup"><span data-stu-id="a3e36-318">Troubleshooting</span></span>

<span data-ttu-id="a3e36-319">以下文章可能是你了解更多信息和解决 Autopilot 问题的有用资源，但请注意，这些文章是基于Windows 10 桌面版的，并非所有信息都适用于 HoloLens：</span><span class="sxs-lookup"><span data-stu-id="a3e36-319">The following articles may be a useful resource for you to learn more information and troubleshoot Autopilot Issues, however please be aware that these articles are based on Windows 10 Desktop and not all information may apply to HoloLens:</span></span>

- [<span data-ttu-id="a3e36-320">Windows Autopilot - 已知问题</span><span class="sxs-lookup"><span data-stu-id="a3e36-320">Windows Autopilot - known issues</span></span>](/mem/autopilot/known-issues)
- [<span data-ttu-id="a3e36-321">Microsoft Intune 中的 Windows 设备注册问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="a3e36-321">Troubleshoot Windows device enrollment problems in Microsoft Intune</span></span>](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [<span data-ttu-id="a3e36-322">Windows Autopilot - 策略冲突</span><span class="sxs-lookup"><span data-stu-id="a3e36-322">Windows Autopilot - Policy Conflicts</span></span>](/mem/autopilot/policy-conflicts)

## <a name="feedback-and-support-for-autopilot"></a><span data-ttu-id="a3e36-323">Autopilot 反馈与支持</span><span class="sxs-lookup"><span data-stu-id="a3e36-323">Feedback and support for Autopilot</span></span>

<span data-ttu-id="a3e36-324">若要提供反馈或报告问题，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="a3e36-324">To provide feedback or report issues, use one of the following methods:</span></span>

- <span data-ttu-id="a3e36-325">有关设备注册方面的支持，请联系你的经销商或分销商。</span><span class="sxs-lookup"><span data-stu-id="a3e36-325">For support on device registration, please contact your reseller or distributor.</span></span>
- <span data-ttu-id="a3e36-326">有关 Windows Autopilot 的常规支持问询或配置文件分配、组创建或 MEM 门户控件等问题，[请联系 Microsoft Endpoint Manager 支持](/mem/get-support)</span><span class="sxs-lookup"><span data-stu-id="a3e36-326">For general support inquiries about Windows Autopilot, or for issues like profile assignments, group creation or MEM portal controls, [please contact Microsoft Endpoint Manager support](/mem/get-support)</span></span>  
- <span data-ttu-id="a3e36-327">如果你的设备已注册到 Autopilot 服务，并且配置文件已分配在 MEM 门户上，请联系 HoloLens [支持](/hololens/)（参见“支持”卡）。</span><span class="sxs-lookup"><span data-stu-id="a3e36-327">If your device is registered to the Autopilot service and the profile is assigned on MEM portal, contact HoloLens [support](/hololens/) (see 'Support' card).</span></span> <span data-ttu-id="a3e36-328">请开具支持票证，如果适用，请在全新体验 (OOBE) 期间捕获[脱机诊断日志](hololens-diagnostic-logs.md#offline-diagnostics)（包括屏幕截图和日志）。</span><span class="sxs-lookup"><span data-stu-id="a3e36-328">Please open a support ticket and if applicable, include screenshots and logs by capturing [offline diagnostic logs](hololens-diagnostic-logs.md#offline-diagnostics) during the out-of-box-experience (OOBE).</span></span>
- <span data-ttu-id="a3e36-329">若要从设备上报告问题，请使用 HoloLens 上的反馈中心应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3e36-329">To report an issue from the device, use the Feedback Hub app on your HoloLens.</span></span> <span data-ttu-id="a3e36-330">在反馈中心，选择“企业管理” > “设备”类别。</span><span class="sxs-lookup"><span data-stu-id="a3e36-330">In Feedback Hub, select the **Enterprise Management** > **Device** category.</span></span>
- <span data-ttu-id="a3e36-331">若要提供有关适用于 HoloLens 的 Autopilot 的常规反馈，可提交此[调查](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)</span><span class="sxs-lookup"><span data-stu-id="a3e36-331">To provide general feedback on Autopilot for HoloLens, you can submit this [survey](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)</span></span>
