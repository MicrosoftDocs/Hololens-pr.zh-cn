---
title: 适用于 HoloLens 2 的 Windows Autopilot （个人预览版）
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 4/10/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: 6851249ab9ed79e7dcdea6afc853fee66fdddf19
ms.sourcegitcommit: a51f2e409f0207fc7457e97403b5298f1e0ad7dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "11145653"
---
# <span data-ttu-id="7a332-103">适用于 HoloLens 2 的 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="7a332-103">Windows Autopilot for HoloLens 2</span></span>

<span data-ttu-id="7a332-104">为 Windows Autopilot 计划设置 HoloLens 2 设备时，用户可以按照一个简单的过程从云中预配设备。</span><span class="sxs-lookup"><span data-stu-id="7a332-104">When you set up HoloLens 2 devices for the Windows Autopilot program, your users can follow a simple process to provision the devices from the cloud.</span></span>

<span data-ttu-id="7a332-105">此 Autopilot 计划支持 Autopilot 自行部署模式，可将 HoloLens 2 设备设置为租户下的共享设备。</span><span class="sxs-lookup"><span data-stu-id="7a332-105">This Autopilot program supports Autopilot self-deploying mode to provision HoloLens 2 devices as shared devices under your tenant.</span></span> <span data-ttu-id="7a332-106">自部署模式在预配过程中利用设备的预安装 OEM 映像和驱动程序。</span><span class="sxs-lookup"><span data-stu-id="7a332-106">Self-deploying mode leverages the device's preinstalled OEM image and drivers during the provisioning process.</span></span> <span data-ttu-id="7a332-107">用户可预配设备，无需将设备采用并完成全新体验（OOBE）。</span><span class="sxs-lookup"><span data-stu-id="7a332-107">A user can provision the device without putting the device on and going through the Out-of-the-box Experience (OOBE).</span></span> <span data-ttu-id="7a332-108">了解适用于 Windows 10 的 Windows Autopilot 的更多信息，请单击[此处](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)"。</span><span class="sxs-lookup"><span data-stu-id="7a332-108">To learn more about Windows Autopilot for Windows 10 click [here](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

<span data-ttu-id="7a332-109">用户启动 Autopilot 自部署进程时，该过程完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7a332-109">When a user starts the Autopilot self-deploying process, the process completes the following steps:</span></span>

1. <span data-ttu-id="7a332-110">将设备加入 Azure Active Directory (Azure AD)。</span><span class="sxs-lookup"><span data-stu-id="7a332-110">Join the device to Azure Active Directory (Azure AD).</span></span>
   > [!NOTE]  
   > <span data-ttu-id="7a332-111">适用于 HoloLens 的 Autopilot 不支持加入 Active Directory 或混合加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="7a332-111">Autopilot for HoloLens does not support Active Directory join or Hybrid Azure AD join.</span></span>
1. <span data-ttu-id="7a332-112">使用 Azure AD 在 Microsoft Intune （或其他 MDM 服务）中注册设备。</span><span class="sxs-lookup"><span data-stu-id="7a332-112">Use Azure AD to enroll the device in Microsoft Intune (or another MDM service).</span></span>
1. <span data-ttu-id="7a332-113">下载面向设备的策略、面向用户的应用、证书和网络配置文件。</span><span class="sxs-lookup"><span data-stu-id="7a332-113">Download the device-targeted policies, user-targeted apps, certificates, and networking profiles.</span></span>
1. <span data-ttu-id="7a332-114">预配设备。</span><span class="sxs-lookup"><span data-stu-id="7a332-114">Provision the device.</span></span>
1. <span data-ttu-id="7a332-115">向用户呈现登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="7a332-115">Present the sign-in screen to the user.</span></span>

## <span data-ttu-id="7a332-116">适用于 HoloLens 2 的 Windows Autopilot 个人预览版</span><span class="sxs-lookup"><span data-stu-id="7a332-116">Windows Autopilot for HoloLens 2 Private Preview</span></span>

<span data-ttu-id="7a332-117">请按照以下步骤设置私人预览版的环境：</span><span class="sxs-lookup"><span data-stu-id="7a332-117">Please follow the steps below to set up your environment for the private preview:</span></span>

1. <span data-ttu-id="7a332-118">请确保符合适用于 HoloLens 2 的 Windows Autopilot 的要求。</span><span class="sxs-lookup"><span data-stu-id="7a332-118">Make sure that you meet the requirements for Windows Autopilot for HoloLens 2</span></span>
1. <span data-ttu-id="7a332-119">注册“适用于 HoloLens 2 的 Windows Autopilot”个人预览版计划</span><span class="sxs-lookup"><span data-stu-id="7a332-119">Enroll in the Windows Autopilot for HoloLens 2 private preview program</span></span>
1. <span data-ttu-id="7a332-120">验证租户是否已启用 （已注册参加计划）</span><span class="sxs-lookup"><span data-stu-id="7a332-120">Verify that your tenant is flighted (enrolled to participate in the program)</span></span>
1. <span data-ttu-id="7a332-121">在 Windows Autopilot 中注册设备</span><span class="sxs-lookup"><span data-stu-id="7a332-121">Register your devices in Windows Autopilot</span></span>
1. <span data-ttu-id="7a332-122">创建设备组</span><span class="sxs-lookup"><span data-stu-id="7a332-122">Create a device group</span></span>
1. <span data-ttu-id="7a332-123">创建部署配置文件</span><span class="sxs-lookup"><span data-stu-id="7a332-123">Create a deployment profile</span></span>
1. <span data-ttu-id="7a332-124">验证 ESP 配置</span><span class="sxs-lookup"><span data-stu-id="7a332-124">Verify the ESP configuration</span></span>
1. <span data-ttu-id="7a332-125">配置 HoloLens 设备的自定义配置文件（已知问题）</span><span class="sxs-lookup"><span data-stu-id="7a332-125">Configure a custom configuration profile for HoloLens devices (known issue)</span></span>
1. <span data-ttu-id="7a332-126">验证 HoloLens 设备的配置文件状态</span><span class="sxs-lookup"><span data-stu-id="7a332-126">Verify the profile status of the HoloLens devices</span></span>


### <span data-ttu-id="7a332-127">1. 请确保符合适用于 HoloLens 2 的 Windows Autopilot 的要求。</span><span class="sxs-lookup"><span data-stu-id="7a332-127">1. Make sure that you meet the requirements for Windows Autopilot for HoloLens 2</span></span>

**<span data-ttu-id="7a332-128">参阅 Windows Autopilot 要求文章的以下部分：</span><span class="sxs-lookup"><span data-stu-id="7a332-128">Review the following sections of the Windows Autopilot requirements article:</span></span>**

- [<span data-ttu-id="7a332-129">网络要求</span><span class="sxs-lookup"><span data-stu-id="7a332-129">Network requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [<span data-ttu-id="7a332-130">许可要求</span><span class="sxs-lookup"><span data-stu-id="7a332-130">Licensing requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [<span data-ttu-id="7a332-131">配置需求</span><span class="sxs-lookup"><span data-stu-id="7a332-131">Configuration requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)

**<span data-ttu-id="7a332-132">查看 Windows Autopilo 自部署模式文章的“[要求](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)”部分。</span><span class="sxs-lookup"><span data-stu-id="7a332-132">Review the "[Requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)" section of the Windows Autopilot Self-Deploying mode article.</span></span>** <span data-ttu-id="7a332-133">环境必须满足这些要求以及 Windows Autopilot 标准要求。</span><span class="sxs-lookup"><span data-stu-id="7a332-133">Your environment has to meet these requirements as well as the standard Windows Autopilot requirements.</span></span> <span data-ttu-id="7a332-134">无需查看本文的“分步操作”和“验证”部分。</span><span class="sxs-lookup"><span data-stu-id="7a332-134">You do not have to review the "Step by step" and "Validation" sections of the article.</span></span> <span data-ttu-id="7a332-135">本文后面的过程提供了特定于 HoloLens 的相应步骤。</span><span class="sxs-lookup"><span data-stu-id="7a332-135">The procedures later in this article provide corresponding steps that are specific to HoloLens.</span></span> <span data-ttu-id="7a332-136">有关如何注册设备和配置配置文件的信息，请参见本文中的[ 4. 在 Windows Autopilot 中注册设备](#4-register-devices-in-windows-autopilot)和[6. 创建部署配置文件](#6-create-a-deployment-profile)。</span><span class="sxs-lookup"><span data-stu-id="7a332-136">For information about how to register devices and configure profiles, see [4. Register devices in Windows Autopilot](#4-register-devices-in-windows-autopilot) and [6. Create a deployment profile](#6-create-a-deployment-profile) in this article.</span></span> <span data-ttu-id="7a332-137">这些部分提供了适用于 HoloLens 的特殊步骤。</span><span class="sxs-lookup"><span data-stu-id="7a332-137">These sections provide steps that are specific to HoloLens.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="7a332-138">适用于 HoloLens 2 的 Windows Autopilot 有特定的操作系统要求。</span><span class="sxs-lookup"><span data-stu-id="7a332-138">Windows Autopilot for HoloLens 2 has specific operating system requirements.</span></span> <span data-ttu-id="7a332-139">Autopilot 依赖于 HoloLens 设备上预安装的 Windows 全息版的版本 2004（内部版本 19041.1103 或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="7a332-139">Autopilot relies on Windows Holographic, version 2004 (build 19041.1103 or later) being pre-installed on HoloLens devices.</span></span> <span data-ttu-id="7a332-140">在 2020 年 9 月底之前交付的设备已预装了 Windows 全息版（版本 1903）。</span><span class="sxs-lookup"><span data-stu-id="7a332-140">Devices delivered until late September 2020 have Windows Holographic, version 1903 pre-installed.</span></span> <span data-ttu-id="7a332-141">请联系分销商，了解向你派发可使用 Autopilot 的设备的时间。</span><span class="sxs-lookup"><span data-stu-id="7a332-141">Please contact your distributor to learn about when Autopilot-ready devices can be shipped to you.</span></span> <span data-ttu-id="7a332-142">如果想加入私人预览版，请查看下面的说明和要求。</span><span class="sxs-lookup"><span data-stu-id="7a332-142">If you wish to participate to the private preview, please review instructions and requirements below.</span></span>

**<span data-ttu-id="7a332-143">如果你想尝试 Autopilot 预览版，请在启动 OOBE 和预配过程之前，确保 HoloLens 设备符合以下要求：</span><span class="sxs-lookup"><span data-stu-id="7a332-143">If you wish to try the Autopilot preview, before you start the OOBE and provisioning process, make sure that the HoloLens devices meet the following requirements:</span></span>**

- <span data-ttu-id="7a332-144">确保设备安装了 Windows 全息版的版本 2004（内部版本 19041.1103 或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="7a332-144">Ensure your device is on Windows Holographic, version 2004 (build 19041.1103 or later).</span></span> <span data-ttu-id="7a332-145">如果未预安装最新操作系统，则必须使用“[高级恢复配套（ARC）](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab)”手动更新。</span><span class="sxs-lookup"><span data-stu-id="7a332-145">If the latest OS is not pre-installed you must manually update using the [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab).</span></span> <span data-ttu-id="7a332-146">可在[此处](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)找到说明。</span><span class="sxs-lookup"><span data-stu-id="7a332-146">You can find instructions [here](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device).</span></span> 
- <span data-ttu-id="7a332-147">设备必须在 Windows Autopilot 中注册。</span><span class="sxs-lookup"><span data-stu-id="7a332-147">Your devices must be registered in Windows Autopilot.</span></span> <span data-ttu-id="7a332-148">有关如何注册设备的更多信息，请参阅 [4. 在 Windows Autopilot 中注册设备](#4-register-devices-in-windows-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="7a332-148">For information about how to register devices see [4. Register devices in Windows Autopilot](#4-register-devices-in-windows-autopilot).</span></span> <span data-ttu-id="7a332-149">推荐的方法是让经销商或分销商为你注册设备。</span><span class="sxs-lookup"><span data-stu-id="7a332-149">The recommended path is for your reseller or distributor to register devices for you.</span></span>     
- <span data-ttu-id="7a332-150">在当前版本中，在打开 HoloLens 和启动 Autopilot 预配过程之前，需要将设备连接到 Internet。</span><span class="sxs-lookup"><span data-stu-id="7a332-150">In the current release, devices need to be connected to the internet before turning on the HoloLens and initiating the Autopilot provisioning process.</span></span> <span data-ttu-id="7a332-151">使用“适用于以太网的 USB-C”适配器将设备连接到以太网，以便连接到有线 Internet。</span><span class="sxs-lookup"><span data-stu-id="7a332-151">Connect your device to Ethernet using a "USB-C to Ethernet" adapter for wired internet connectivity.</span></span> 
- <span data-ttu-id="7a332-152">设备尚不是 Azure AD 的成员，并且未在 Intune （或其他 MDM 系统）中注册。</span><span class="sxs-lookup"><span data-stu-id="7a332-152">The devices are not already members of Azure AD, and are not enrolled in Intune (or another MDM system).</span></span> <span data-ttu-id="7a332-153">Autopilot 自部署过程完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="7a332-153">The Autopilot self-deploying process completes these steps.</span></span> <span data-ttu-id="7a332-154">若要确保清理所有设备相关信息，请检查 Azure AD 和 Intune 门户中的“**设备**”页面。</span><span class="sxs-lookup"><span data-stu-id="7a332-154">To make sure that all the device-related information is cleaned up, check the **Devices** pages in both Azure AD and Intune Portals.</span></span>
- <span data-ttu-id="7a332-155">若要配置和管理 Autopilot 自部署模式配置文件，请确保你有权访问[Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="7a332-155">To configure and manage the Autopilot self-deploying mode profiles, make sure that you have access to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>


### <span data-ttu-id="7a332-156">2. 注册“适用于 HoloLens 2 的 Windows Autopilot”计划</span><span class="sxs-lookup"><span data-stu-id="7a332-156">2. Enroll in the Windows Autopilot for HoloLens 2 program</span></span>

**<span data-ttu-id="7a332-157">若要参与该计划，必须将租户注册到“专用预览版计划”。</span><span class="sxs-lookup"><span data-stu-id="7a332-157">To participate in the program, you must have your tenant enrolled to the Private Preview program.</span></span> <span data-ttu-id="7a332-158">这将为 Autopilot 启用 HoloLens 特定 Intune （也称为 MEM） UI 控件。</span><span class="sxs-lookup"><span data-stu-id="7a332-158">This enables HoloLens-specific Intune (aka MEM) UI controls for Autopilot.</span></span>** <span data-ttu-id="7a332-159">若要执行此操作，请转到 [适用于 HoloLens 专用预览版的 Windows Autopilot](https://aka.ms/APHoloLensTAP) 或使用以下 QR 码提交请求。</span><span class="sxs-lookup"><span data-stu-id="7a332-159">To do this, go to  [Windows Autopilot for HoloLens Private Preview request](https://aka.ms/APHoloLensTAP) or use the following QR code to submit a request.</span></span>  

![Autopilot QR 码](./images/hololens-ap-qrcode.png)  

<span data-ttu-id="7a332-161">Microsoft 每周将会测试一次租户。</span><span class="sxs-lookup"><span data-stu-id="7a332-161">Microsoft flights tenants once a week.</span></span> <span data-ttu-id="7a332-162">测试完成后，你将收到一封电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="7a332-162">You will receive an email notification once the flighting is complete.</span></span> 

<span data-ttu-id="7a332-163">在此请求中，提供以下信息：</span><span class="sxs-lookup"><span data-stu-id="7a332-163">In this request, provide the following information:</span></span>

- <span data-ttu-id="7a332-164">租户域</span><span class="sxs-lookup"><span data-stu-id="7a332-164">Tenant domain</span></span>
- <span data-ttu-id="7a332-165">租户 ID</span><span class="sxs-lookup"><span data-stu-id="7a332-165">Tenant ID</span></span>
- <span data-ttu-id="7a332-166">参与此评估的 HoloLens 2 设备数量</span><span class="sxs-lookup"><span data-stu-id="7a332-166">Number of HoloLens 2 devices that are participating in this evaluation</span></span>
- <span data-ttu-id="7a332-167">计划使用 Autopilot 自部署模式部署的 HoloLens 2 设备数量</span><span class="sxs-lookup"><span data-stu-id="7a332-167">Number of HoloLens 2 devices that you plan to deploy by using Autopilot self-deploying mode</span></span>

### <span data-ttu-id="7a332-168">3. 验证租户是否已启用</span><span class="sxs-lookup"><span data-stu-id="7a332-168">3. Verify that your tenant is flighted</span></span>

<span data-ttu-id="7a332-169">提交请求后，若要验证是否为 Autopilot 计划启用了租户，请按照以下步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="7a332-169">To verify that your tenant is flighted for the Autopilot program after you submit your request, follow these steps:</span></span>

1. <span data-ttu-id="7a332-170">登录 [Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="7a332-170">Sign in to [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com).</span></span>
1. <span data-ttu-id="7a332-171">选择“**设备**” > “**Windows**” > “**Windows 注册**” > “**Windows Autopilot 部署配置文件**” > “**创建配置文件**”。</span><span class="sxs-lookup"><span data-stu-id="7a332-171">Select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile**.</span></span>  
   
   ![“创建配置文件”下拉列表包含一个 HoloLens 项。](./images/hololens-ap-enrollment-profiles.png)
  <span data-ttu-id="7a332-173">你将看到包括 **HoloLens**的列表。</span><span class="sxs-lookup"><span data-stu-id="7a332-173">You should see a list that includes **HoloLens**.</span></span> <span data-ttu-id="7a332-174">如果不存在此选项，请使用[反馈](#feedback)选项之一与我们联系。</span><span class="sxs-lookup"><span data-stu-id="7a332-174">If this option is not present, use one of the [Feedback](#feedback) options to contact us.</span></span>

### <span data-ttu-id="7a332-175">4. 在 Windows Autopilot 注册设备</span><span class="sxs-lookup"><span data-stu-id="7a332-175">4. Register devices in Windows Autopilot</span></span>

<span data-ttu-id="7a332-176">在准备阶段，有两种主要方式可将设备注册到 Windows Autopilot：</span><span class="sxs-lookup"><span data-stu-id="7a332-176">In the preparation phase, there are two primary ways you can register devices to Windows Autopilot:</span></span> 

1. <span data-ttu-id="7a332-177">**下订单时，联系分销商或经销商以注册设备**或</span><span class="sxs-lookup"><span data-stu-id="7a332-177">**Contact your distributor or reseller when you place an order to have your devices registered** or</span></span>
2. **<span data-ttu-id="7a332-178">检索硬件哈希（也称为硬件 ID）并手动注册设备。</span><span class="sxs-lookup"><span data-stu-id="7a332-178">Retrieve the hardware hash (also known as the hardware ID) and register the device manually.</span></span>** 

<span data-ttu-id="7a332-179">有关设备注册的详细信息，请参阅 [将设备添加到 Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices) 文档。</span><span class="sxs-lookup"><span data-stu-id="7a332-179">For more information on device registration please review the [Adding devices to Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices) documentation.</span></span>  

**<span data-ttu-id="7a332-180">检索设备硬件哈希</span><span class="sxs-lookup"><span data-stu-id="7a332-180">Retrieve a device hardware hash</span></span>**

<span data-ttu-id="7a332-181">设备可以在 OOBE 过程中，或者稍后当设备所有者启动诊断日志收集过程（在以下过程中描述）时，将其硬件哈希记录在 CSV 文件中。</span><span class="sxs-lookup"><span data-stu-id="7a332-181">The device can record its hardware hash in a CSV file during the OOBE process, or later when a device owner starts the diagnostic log collection process (described in the following procedure).</span></span> <span data-ttu-id="7a332-182">通常情况下，设备所有者是第一个登录到设备的用户。</span><span class="sxs-lookup"><span data-stu-id="7a332-182">Typically, the device owner is the first user to sign in to the device.</span></span>

1. <span data-ttu-id="7a332-183">启动 HoloLens 2 设备。</span><span class="sxs-lookup"><span data-stu-id="7a332-183">Start the HoloLens 2 device.</span></span>
1. <span data-ttu-id="7a332-184">在设备上，同时按“电源”和“音量”按钮，然后松开。</span><span class="sxs-lookup"><span data-stu-id="7a332-184">On the device, press the Power and Volume Down buttons at the same time and then release them.</span></span> <span data-ttu-id="7a332-185">设备收集诊断日志和硬件哈希，并将它们存储在一组 .zip 文件中。</span><span class="sxs-lookup"><span data-stu-id="7a332-185">The device collects diagnostic logs and the hardware hash, and stores them in a set of .zip files.</span></span>
1. <span data-ttu-id="7a332-186">使用 USB-C 电缆将设备连接到计算机。</span><span class="sxs-lookup"><span data-stu-id="7a332-186">Use a USB-C cable to connect the device to a computer.</span></span>
1. <span data-ttu-id="7a332-187">在计算机上，打开“文件资源管理器”。</span><span class="sxs-lookup"><span data-stu-id="7a332-187">On the computer, open File Explorer.</span></span> <span data-ttu-id="7a332-188">打开**此计算机 \\\<*HoloLens device name*>\\内部存储\\文档**，并定位至AutopilotDiagnostics.zip 文件。</span><span class="sxs-lookup"><span data-stu-id="7a332-188">Open **This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents**, and locate the AutopilotDiagnostics.zip file.</span></span>  

   > [!NOTE]  
   > <span data-ttu-id="7a332-189">.zip 文件可能不会立即可用。</span><span class="sxs-lookup"><span data-stu-id="7a332-189">The .zip file may not immediately be available.</span></span> <span data-ttu-id="7a332-190">如果该文件尚未准备好，可能会在“文档”文件夹中看到一个 HoloLensDiagnostics.temp文件。</span><span class="sxs-lookup"><span data-stu-id="7a332-190">If the file is not ready yet you may see a HoloLensDiagnostics.temp file in the Documents folder.</span></span> <span data-ttu-id="7a332-191">若要更新文件列表，请刷新窗口。</span><span class="sxs-lookup"><span data-stu-id="7a332-191">To update the list of files, refresh the window.</span></span>

1. <span data-ttu-id="7a332-192">提取 AutopilotDiagnostics.zip 文件的内容。</span><span class="sxs-lookup"><span data-stu-id="7a332-192">Extract the contents of the AutopilotDiagnostics.zip file.</span></span>
1. <span data-ttu-id="7a332-193">在提取的文件中，找到文件名前缀为 “DeviceHash” 的 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="7a332-193">In the extracted files, locate the CSV file that has a file name prefix of "DeviceHash."</span></span> <span data-ttu-id="7a332-194">将该文件复制到计算机上的驱动器上，以后可以访问它。</span><span class="sxs-lookup"><span data-stu-id="7a332-194">Copy that file to a drive on the computer where you can access it later.</span></span>  
   > [!IMPORTANT]  
   > <span data-ttu-id="7a332-195">CSV 文件中的数据应使用以下标题和行格式：</span><span class="sxs-lookup"><span data-stu-id="7a332-195">The data in the CSV file should use the following header and line format:</span></span>
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**<span data-ttu-id="7a332-196">注册设备至 Windows Autopilot 中</span><span class="sxs-lookup"><span data-stu-id="7a332-196">Register the device in Windows Autopilot</span></span>**

1. <span data-ttu-id="7a332-197">在 Microsoft 终结点管理器管理中心中，选择“**设备**” > “\*\* Windows **” >  “**Windows 注册**”，然后选择 **Windows Autopilot 部署计划**下的“**设备**” > “**导入\*\*”。</span><span class="sxs-lookup"><span data-stu-id="7a332-197">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment**, and then select **Devices** > **Import** under **Windows Autopilot Deployment Program**.</span></span>

1. <span data-ttu-id="7a332-198">在“**添加 Windows Autopilot 设备**”中，选择 DeviceHash CSV 文件，选择“**打开**”，然后选择“**导入**”。</span><span class="sxs-lookup"><span data-stu-id="7a332-198">Under **Add Windows Autopilot devices**, select the DeviceHash CSV file, select **Open**, and then select **Import**.</span></span>  
   
   ![使用导入命令导入硬件哈希。](./images/hololens-ap-hash-import.png)
1. <span data-ttu-id="7a332-200">完成导入后，选择“**设备**” > “**Windows**” > “**Windows 注册**” > “**设备**” > “**同步**”。此过程可能需要几分钟时间才能完成，具体取决于同步的设备数量。</span><span class="sxs-lookup"><span data-stu-id="7a332-200">After the import finishes, select **Devices** > **Windows** > **Windows enrollment** > **Devices** > **Sync**. The process might take a few minutes to complete, depending on how many devices are being synchronized.</span></span> <span data-ttu-id="7a332-201">若要查看已注册的设备，请选择“**刷新**”。</span><span class="sxs-lookup"><span data-stu-id="7a332-201">To see the registered device, select **Refresh**.</span></span>  
   
   ![使用“同步”和“刷新”命令查看设备列表。](./images/hololens-ap-devices-sync.png)  

### <span data-ttu-id="7a332-203">5. 创建设备组</span><span class="sxs-lookup"><span data-stu-id="7a332-203">5. Create a device group</span></span>

1. <span data-ttu-id="7a332-204">在Microsoft 终结点管理器管理中心中，选择“**组**” > “**新建组**”。</span><span class="sxs-lookup"><span data-stu-id="7a332-204">In Microsoft Endpoint Manager admin center, select **Groups** > **New group**.</span></span>
1. <span data-ttu-id="7a332-205">对于“**组类型**”，选择“**安全性**”，然后输入组名称和描述。</span><span class="sxs-lookup"><span data-stu-id="7a332-205">For **Group type**, select **Security**, and then enter a group name and description.</span></span>
1. <span data-ttu-id="7a332-206">对于“**成员身份类型**”，选择“**已指派**” 或“**动态设备**”。</span><span class="sxs-lookup"><span data-stu-id="7a332-206">For **Membership type**, select either **Assigned** or **Dynamic Device**.</span></span>
1. <span data-ttu-id="7a332-207">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="7a332-207">Do one of the following:</span></span>  
   
   - <span data-ttu-id="7a332-208">如果在上一步中为“**成员身份类型**”选择了“**已指派**”，请选择“**成员**”，然后将 Autopilot 设备添加到组中。</span><span class="sxs-lookup"><span data-stu-id="7a332-208">If you selected **Assigned** for **Membership type** in the previous step, select **Members**, and then add Autopilot devices to the group.</span></span> <span data-ttu-id="7a332-209">通过将设备序列号用作设备名称，列出尚未注册的 Autopilot 设备。</span><span class="sxs-lookup"><span data-stu-id="7a332-209">Autopilot devices that aren't yet enrolled are listed by using the device serial number as the device name.</span></span>
   - <span data-ttu-id="7a332-210">如果在上一步中为“**成员身份类型**”选择了“**动态设备**”，请选择“**动态设备成员**”，然后在“**高级规则**”中输入代码，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7a332-210">If you selected **Dynamic Devices** for **Membership type** in the previous step, select **Dynamic device members**, and then enter code in **Advanced rule** that resembles the following:</span></span>
     - <span data-ttu-id="7a332-211">若要创建包含所有 Autopilot 设备的组，请键入：</span><span class="sxs-lookup"><span data-stu-id="7a332-211">If you want to create a group that includes all of your Autopilot devices, type:</span></span> `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - <span data-ttu-id="7a332-212">Intune 的“组标记”字段映射到 Azure AD 设备的“**OrderID**”属性。</span><span class="sxs-lookup"><span data-stu-id="7a332-212">Intune's group tag field maps to the **OrderID** attribute on Azure AD devices.</span></span> <span data-ttu-id="7a332-213">如果要创建一个包含所有具有特定组标签的 Autopilot 设备的组（Azure AD 设备OrderID），必须键入：</span><span class="sxs-lookup"><span data-stu-id="7a332-213">If you want to create a group that includes all of your Autopilot devices that have a specific group tag (the Azure AD device OrderID), you must type:</span></span> `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - <span data-ttu-id="7a332-214">如果你想要创建包含所有具有特定购买订单 ID 的 Autopilot 设备的组，请键入：</span><span class="sxs-lookup"><span data-stu-id="7a332-214">If you want to create a group that includes all your Autopilot devices that have a specific Purchase Order ID, type:</span></span> `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > <span data-ttu-id="7a332-215">这些规则针对 Autopilot 设备独有的属性。</span><span class="sxs-lookup"><span data-stu-id="7a332-215">These rules target attributes that are unique to Autopilot devices.</span></span>
1. <span data-ttu-id="7a332-216">选择“**保存**”，然后选择“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="7a332-216">Select **Save**, and then select **Create**.</span></span>

### <span data-ttu-id="7a332-217">6. 创建部署配置文件</span><span class="sxs-lookup"><span data-stu-id="7a332-217">6. Create a deployment profile</span></span>

1. <span data-ttu-id="7a332-218">在 Microsoft 终结点管理器管理中心中，选择“**设备**” > “**Windows**” > “**Windows 注册**” > “**Windows Autopilot 部署配置文件**” > “**创建配置文件**” > “**HoloLens**”。</span><span class="sxs-lookup"><span data-stu-id="7a332-218">In Microsoft Endpoint Manager admin center, select **Devices** > **Windows** > **Windows enrollment** > **Windows Autopilot deployment profiles** > **Create profile** > **HoloLens**.</span></span>
1. <span data-ttu-id="7a332-219">输入配置文件名称和说明，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7a332-219">Enter a profile name and description, and then select **Next**.</span></span>  
   
   ![添加配置文件名称和说明](./images/hololens-ap-profile-name.png)
1. <span data-ttu-id="7a332-221">在“**全新体验（OOBE）**”页面上，大多数设置都是预配置的，用于简化此评估的 OOBE。</span><span class="sxs-lookup"><span data-stu-id="7a332-221">On the **Out-of-box experience (OOBE)** page, most of the settings are pre-configured to streamline OOBE for this evaluation.</span></span> <span data-ttu-id="7a332-222">另外可配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="7a332-222">Optionally, you can configure the following settings:</span></span>  

   - <span data-ttu-id="7a332-223">**语言（区域）**：选择 OOBE 语言。</span><span class="sxs-lookup"><span data-stu-id="7a332-223">**Language (Region)**: Select the language for OOBE.</span></span> <span data-ttu-id="7a332-224">我们建议从[支持 HoloLens 2 的语言](hololens2-language-support.md)列表中选择一种语言。</span><span class="sxs-lookup"><span data-stu-id="7a332-224">We recommend that you select a language from the list of [supported languages for HoloLens 2](hololens2-language-support.md).</span></span>
   - <span data-ttu-id="7a332-225">**自动配置键盘**：若要确保键盘匹配所选语言，请选择“**是**”。</span><span class="sxs-lookup"><span data-stu-id="7a332-225">**Automatically configure keyboard**: To make sure that the keyboard matches the selected language, select **Yes**.</span></span>
   - <span data-ttu-id="7a332-226">**应用设备名称模板**：若要在 OOBE 期间自动设置设备名称，请选择“**是**”，然后在“\*\* 输入名称\*\*”中输入模板短语和占位符。例如，输入前缀和`%RAND:4%`&mdash;四位随机数字的占位符。</span><span class="sxs-lookup"><span data-stu-id="7a332-226">**Apply device name template**: To automatically set the device name during OOBE, select **Yes** and then enter the template phrase and placeholders in **Enter a name** For example, enter a prefix and `%RAND:4%`&mdash;a placeholder for a four-digit random number.</span></span>
     > [!NOTE]  
     > <span data-ttu-id="7a332-227">如果使用设备名称模板，OOBE 进程将在应用设备名称之后和将设备加入 Azure AD 之前再次重新启动该设备。</span><span class="sxs-lookup"><span data-stu-id="7a332-227">If you use a device name template, the OOBE process restarts the device one additional time after it applies the device name and before it joins the device to Azure AD.</span></span> <span data-ttu-id="7a332-228">重新启动后，新名称才会生效。</span><span class="sxs-lookup"><span data-stu-id="7a332-228">This restart enables the new name to take effect.</span></span>  

   ![配置 OOBE 设置](./images/hololens-ap-profile-oobe.png)
1. <span data-ttu-id="7a332-230">配置设置后，选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7a332-230">After you configure the settings, select **Next**.</span></span>
1. <span data-ttu-id="7a332-231">在“**范围标记**”页面上，选择添加要应用于此配置文件的范围标记。</span><span class="sxs-lookup"><span data-stu-id="7a332-231">On the **Scope tags** page, optionally add the scope tags that you want to apply to this profile.</span></span> <span data-ttu-id="7a332-232">有关范围标记的详细信息，请参阅 [将基于角色的访问控制和范围标记用于分布式 IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="7a332-232">For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md).</span></span> <span data-ttu-id="7a332-233">完成后，选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7a332-233">When finished, select **Next**.</span></span>
1. <span data-ttu-id="7a332-234">在“**分配 **”页面上，为“**分配至**”选择“**所选组**”。</span><span class="sxs-lookup"><span data-stu-id="7a332-234">On the **Assignments** page, select **Selected groups** for **Assign to**.</span></span>
1. <span data-ttu-id="7a332-235">在“**所选组**”下，选择“\*\* + 选择要包括的组\*\*”。</span><span class="sxs-lookup"><span data-stu-id="7a332-235">Under **SELECTED GROUPS**, select **+ Select groups to include**.</span></span>
1. <span data-ttu-id="7a332-236">在“**选择要包含的组**”列表中，选择为 Autopilot HoloLens 设备创建的设备组，然后选择“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7a332-236">In the **Select groups to include** list, select the device group that you created for the Autopilot HoloLens devices, and then select **Next**.</span></span>  
  
   <span data-ttu-id="7a332-237">如果要排除任何组，请选择“**选择要排除的组**”，然后选择希望排除的组。</span><span class="sxs-lookup"><span data-stu-id="7a332-237">If you want to exclude any groups, select **Select groups to exclude**, and select the groups that you want to exclude.</span></span>

   ![将设备组分配到配置文件。](./images/hololens-ap-profile-assign-devicegroup.png)
1. <span data-ttu-id="7a332-239">在“**审阅 + 创建**”页面上，查看设置，然后选择“**创建**”以创建配置文件。</span><span class="sxs-lookup"><span data-stu-id="7a332-239">On the **Review + Create** page, review the settings and then select **Create** to create the profile.</span></span>  
   
   ![审阅 + 创建](./images/hololens-ap-profile-summ.png)

### <span data-ttu-id="7a332-241">7. 验证 ESP 配置</span><span class="sxs-lookup"><span data-stu-id="7a332-241">7. Verify the ESP configuration</span></span>

<span data-ttu-id="7a332-242">注册状态页面（ESP）显示完整的设备配置过程的状态，此过程在 MDM 托管用户首次登录设备时运行。</span><span class="sxs-lookup"><span data-stu-id="7a332-242">The Enrollment Status Page (ESP) displays the status of the complete device configuration process that runs when an MDM managed user signs into a device for the first time.</span></span> <span data-ttu-id="7a332-243">请确保你的 ESP 配置类似于以下内容，并验证分配是否正确。</span><span class="sxs-lookup"><span data-stu-id="7a332-243">Make sure that your ESP configuration resembles the following, and verify that the assignments are correct.</span></span>  

![EAP 配置](./images/hololens-ap-profile-settings.png)

### <span data-ttu-id="7a332-245">8. 验证 HoloLens 设备的配置文件状态</span><span class="sxs-lookup"><span data-stu-id="7a332-245">8. Verify the profile status of the HoloLens devices</span></span>

1. <span data-ttu-id="7a332-246">在 Microsoft 终结点管理器管理中心中，选择“**设备**” > “**Windows**” > “**Windows 注册**” > “**设备**”。</span><span class="sxs-lookup"><span data-stu-id="7a332-246">In Microsoft Endpoint Manager Admin Center, select **Devices** > **Windows** > **Windows enrollment** > **Devices**.</span></span>
1. <span data-ttu-id="7a332-247">验证是否列出了 HoloLens 设备，以及其配置文件的状态是否为“**已指派**”。</span><span class="sxs-lookup"><span data-stu-id="7a332-247">Verify that the HoloLens devices are listed, and that their profile status is **Assigned**.</span></span>  
   > [!NOTE]  
   > <span data-ttu-id="7a332-248">可能需要几分钟时间，配置文件才会分配到设备。</span><span class="sxs-lookup"><span data-stu-id="7a332-248">It may take a few minutes for the profile to be assigned to the device.</span></span>  
   
   ![设备和配置文件分配。](./images/hololens-ap-devices-assignments.png)

## <span data-ttu-id="7a332-250">适用于 HoloLens 2 用户体验的 Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="7a332-250">Windows Autopilot for HoloLens 2 User Experience</span></span>

<span data-ttu-id="7a332-251">完成上述说明的步骤后，HoloLens 2 用户将通过以下体验来预配其 HoloLens 设备：</span><span class="sxs-lookup"><span data-stu-id="7a332-251">Once the above instructions are completed, your HoloLens 2 users will go through the following experience to provision their HoloLens devices:</span></span>  

> [!NOTE]
> <span data-ttu-id="7a332-252">使用 Autopilot 将对[设备所有者](security-adminless-os.md#device-owner)产生影响。</span><span class="sxs-lookup"><span data-stu-id="7a332-252">Using Autopilot will have an effect on the [device owner](security-adminless-os.md#device-owner).</span></span>

1. <span data-ttu-id="7a332-253">如前所述，在当前版本中，在打开 HoloLens 和启动 Autopilot 预配过程之前，需要将设备连接到 Internet。</span><span class="sxs-lookup"><span data-stu-id="7a332-253">As mentioned, in the current release, devices need to be connected to the internet before turning on the HoloLens and initiating the Autopilot provisioning process.</span></span> <span data-ttu-id="7a332-254">使用“USB-C到以太网”适配器进行有线 Internet 连接，也可以使用“USB-C 到 Wifi”适配器进行无线 Internet 连接，将设备连接到以太网。</span><span class="sxs-lookup"><span data-stu-id="7a332-254">Connect your device to Ethernet using "USB-C to Ethernet" adapters for wired internet connectivity or "USB-C to Wifi" adapters for wireless internet connectivity.</span></span>
   
   > [!IMPORTANT]  
   > <span data-ttu-id="7a332-255">开始全新体验（OOBE）前，必须将设备连接到网络。</span><span class="sxs-lookup"><span data-stu-id="7a332-255">You must connect the device to the network before the Out-of-the-Box-Experience (OOBE) starts.</span></span> <span data-ttu-id="7a332-256">设备在第一个OOBE屏幕上确定是否将其配置为 Autopilot 设备。</span><span class="sxs-lookup"><span data-stu-id="7a332-256">The device determines whether it is provisioning as an Autopilot device while on the first OOBE screen.</span></span> <span data-ttu-id="7a332-257">如果设备无法连接到网络，或者选择不将其配置为 Autopilot 设备，则以后无法更改为 Autopilot 配置。</span><span class="sxs-lookup"><span data-stu-id="7a332-257">If the device cannot connect to the network, or if you choose not to provision the device as an Autopilot device, you cannot change to Autopilot provisioning at a later time.</span></span> <span data-ttu-id="7a332-258">相反，必须启动此过程，以便将设备设置为 Autopilot 设备。</span><span class="sxs-lookup"><span data-stu-id="7a332-258">Instead, you would have to start this procedure over in order to provision the device as an Autopilot device.</span></span>

1. <span data-ttu-id="7a332-259">设备应自动启动 OOBE。</span><span class="sxs-lookup"><span data-stu-id="7a332-259">The device should automatically start OOBE.</span></span> <span data-ttu-id="7a332-260">不要与 OOBE 交互。</span><span class="sxs-lookup"><span data-stu-id="7a332-260">Do not interact with OOBE.</span></span> <span data-ttu-id="7a332-261">放松一下！</span><span class="sxs-lookup"><span data-stu-id="7a332-261">Instead sit, back and relax!</span></span> <span data-ttu-id="7a332-262">让 HoloLens 2 检测网络连接并允许自动完成 OOBE。</span><span class="sxs-lookup"><span data-stu-id="7a332-262">Let HoloLens 2 detect network connectivity and allow it complete OOBE automatically.</span></span> <span data-ttu-id="7a332-263">设备可能会在 OOBE 过程中重启。</span><span class="sxs-lookup"><span data-stu-id="7a332-263">The device may restart during OOBE.</span></span> <span data-ttu-id="7a332-264">OOBE 屏幕应类似于以下内容。</span><span class="sxs-lookup"><span data-stu-id="7a332-264">The OOBE screens should resemble the following.</span></span>
   
   <span data-ttu-id="7a332-265">![OOBE 步骤 1](./images/hololens-ap-uex-1.png)
   ![OOBE 步骤 2](./images/hololens-ap-uex-2.png)
   ![OOBE 步骤 3](./images/hololens-ap-uex-3.png)
   ![OOBE 步骤 4](./images/hololens-ap-uex-4.png)</span><span class="sxs-lookup"><span data-stu-id="7a332-265">![OOBE step 1](./images/hololens-ap-uex-1.png)
![OOBE step 2](./images/hololens-ap-uex-2.png)
![OOBE step 3](./images/hololens-ap-uex-3.png)
![OOBE step 4](./images/hololens-ap-uex-4.png)</span></span>

1. <span data-ttu-id="7a332-266">OOBE 结束时，可以使用用户名和密码登录到设备。</span><span class="sxs-lookup"><span data-stu-id="7a332-266">At the end of OOBE, you can sign in to the device by using your user name and password.</span></span>

  ![OOBE 步骤 5](./images/hololens-ap-uex-5.png)

## <span data-ttu-id="7a332-268">已知问题</span><span class="sxs-lookup"><span data-stu-id="7a332-268">Known Issues</span></span>

- <span data-ttu-id="7a332-269">无法安装使用设备安全上下文的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7a332-269">You cannot install applications that use the device security context.</span></span>

## <span data-ttu-id="7a332-270">反馈</span><span class="sxs-lookup"><span data-stu-id="7a332-270">Feedback</span></span>

<span data-ttu-id="7a332-271">若要提供反馈或报告问题，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="7a332-271">To provide feedback or report issues, use one of the following methods:</span></span>

- <span data-ttu-id="7a332-272">使用反馈中心应用。</span><span class="sxs-lookup"><span data-stu-id="7a332-272">Use the Feedback Hub app.</span></span> <span data-ttu-id="7a332-273">可以在已连接 HoloLens 的计算机上找到此应用。</span><span class="sxs-lookup"><span data-stu-id="7a332-273">You can find this app on a HoloLens-connected computer.</span></span> <span data-ttu-id="7a332-274">在反馈中心中，选择“**企业管理**” > “**设备**”类别。</span><span class="sxs-lookup"><span data-stu-id="7a332-274">In Feedback Hub, select the **Enterprise Management** > **Device** category.</span></span>  

  <span data-ttu-id="7a332-275">提供反馈或报告问题时，请提供详细说明。</span><span class="sxs-lookup"><span data-stu-id="7a332-275">When you provide feedback or report an issue, provide a detailed description.</span></span> <span data-ttu-id="7a332-276">如果适用，则包括屏幕截图和日志。</span><span class="sxs-lookup"><span data-stu-id="7a332-276">If applicable, include screenshots and logs.</span></span>
- <span data-ttu-id="7a332-277">向 [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com)发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7a332-277">Send an email message to [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com).</span></span> <span data-ttu-id="7a332-278">在“电子邮件主题”中，输入**\<*Tenant*>适用于 HoloLens 2 的 Autopilot 评估反馈**（其中 \<*Tenant*> 是 Intune 租户的名称）。</span><span class="sxs-lookup"><span data-stu-id="7a332-278">For the email subject, enter **\<*Tenant*> Autopilot for HoloLens 2 evaluation feedback** (where \<*Tenant*> is the name of your Intune tenant).</span></span>

  <span data-ttu-id="7a332-279">在邮件中提供详细说明。</span><span class="sxs-lookup"><span data-stu-id="7a332-279">Provide a detailed description in your message.</span></span> <span data-ttu-id="7a332-280">但是，除非支持人员特别要求，否则请勿包括屏幕截图或日志之类的数据。</span><span class="sxs-lookup"><span data-stu-id="7a332-280">However, unless Support personnel specifically request it, do not include data such as screenshots or logs.</span></span> <span data-ttu-id="7a332-281">此类数据可能包括私人或个人身份信息（PII）。</span><span class="sxs-lookup"><span data-stu-id="7a332-281">Such data might include private or personally identifiable information (PII).</span></span>
