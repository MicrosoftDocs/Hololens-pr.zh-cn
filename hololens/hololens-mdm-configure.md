---
title: 使用 Microsoft Endpoint Manager Intune 管理 HoloLens 设备
description: 了解如何使用 Intune 在大规模配置 CSP、策略和管理 HoloLens 混合现实设备。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5485a4b2558a11a6c0545ec8b3405c120cff287c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640265"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a><span data-ttu-id="a6ba4-103">使用 Microsoft Endpoint Manager Intune 管理 HoloLens 设备</span><span class="sxs-lookup"><span data-stu-id="a6ba4-103">Using Microsoft’s Endpoint Manager Intune to manage HoloLens devices</span></span>

<span data-ttu-id="a6ba4-104">有多种不同的设置可通过 MDM 进行管理。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-104">There are numerous different settings you can manage via MDM.</span></span> <span data-ttu-id="a6ba4-105">使用 Intune 设备可以组合在一起，并且可以将配置部署到这些用户或设备组。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-105">Using Intune devices can be grouped together and configurations can be deployed to those groups of users or devices.</span></span> <span data-ttu-id="a6ba4-106">还可以部署和管理应用、设置设备以连接到网络，以及将更新配置为在所需时间和需要的更新环上发生。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-106">Apps can also be deployed and managed, setting up devices to connect to your network, as well as configuring updates to occur at the time desired and on the update ring needed.</span></span> 

## <a name="how-to-manage-via-intune"></a><span data-ttu-id="a6ba4-107">如何通过 Intune 进行管理</span><span class="sxs-lookup"><span data-stu-id="a6ba4-107">How to manage via Intune</span></span>

### <a name="device-categories-and-groups"></a><span data-ttu-id="a6ba4-108">设备类别和组</span><span class="sxs-lookup"><span data-stu-id="a6ba4-108">Device categories and groups</span></span>
<span data-ttu-id="a6ba4-109">使用 Intune，你可以创建设备类别，以根据你创建的类别（例如工程、医学、开发人员等）自动将设备添加到组。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-109">Using Intune, you can create device categories to automatically add devices to groups based on categories that you create, such as Engineering, Medical, Developers, and so on.</span></span> <span data-ttu-id="a6ba4-110">其目的是让管理运行 Windows Holographic for Business 的设备变得更轻松。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-110">The idea is to make it easier to manage your devices running Windows Holographic for Business.</span></span>
<span data-ttu-id="a6ba4-111">了解详细信息：将 [设备分类为组](/mem/intune/enrollment/device-group-mapping)</span><span class="sxs-lookup"><span data-stu-id="a6ba4-111">Read more: [Categorize devices into groups](/mem/intune/enrollment/device-group-mapping)</span></span>

### <a name="device-configuration-profiles"></a><span data-ttu-id="a6ba4-112">设备配置文件</span><span class="sxs-lookup"><span data-stu-id="a6ba4-112">Device configuration profiles</span></span>
<span data-ttu-id="a6ba4-113">Intune 提供可在组织内的不同设备上启用或禁用的设置和功能。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-113">Intune includes settings and features that you can enable or disable on different devices within your organization.</span></span> <span data-ttu-id="a6ba4-114">这些设置和功能通过配置文件进行管理。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-114">These settings and features are managed using profiles.</span></span> <span data-ttu-id="a6ba4-115">例如，可以在运行 Windows Holographic for Business 的设备上创建一个启用 Cortana 或使用 Microsoft Defender Smart Screen 的配置文件。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-115">For example, you can create a profile that enables Cortana, or uses Microsoft Defender Smart Screen on your devices running Windows Holographic for Business.</span></span>
<span data-ttu-id="a6ba4-116">在配置文件中，可以使用 OMA-URI 来自定义某些设置、创建设备限制并配置虚拟专用网络 (VPN) 和 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-116">In your profiles, you can use OMA-URI to customize some settings, create device restrictions, and configure a virtual private network (VPN) and Wi-Fi.</span></span>
<span data-ttu-id="a6ba4-117">[配置文件入门](/mem/intune/configuration/device-profiles)和 [配置文件概述](/mem/intune/configuration/device-profile-create)。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-117">[Get started with configuration profiles](/mem/intune/configuration/device-profiles), and [profile overview](/mem/intune/configuration/device-profile-create).</span></span>

## <a name="examples-of-what-can-be-managed-and-configured"></a><span data-ttu-id="a6ba4-118">可管理和配置的示例</span><span class="sxs-lookup"><span data-stu-id="a6ba4-118">Examples of what can be managed and configured</span></span>

<span data-ttu-id="a6ba4-119">使用 MDM 管理设备可提供一系列可以选择的项。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-119">Using MDM to manage devices gives a wide array of items that can be selected.</span></span> 

### <a name="wi-fi"></a><span data-ttu-id="a6ba4-120">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a6ba4-120">Wi-Fi</span></span>
<span data-ttu-id="a6ba4-121">[Wi-Fi 设置](/mem/intune/configuration/wi-fi-settings-configure)将无线网络设置分配给用户和设备。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-121">[Wi-Fi settings](/mem/intune/configuration/wi-fi-settings-configure) assigns wireless network settings to users and devices.</span></span> <span data-ttu-id="a6ba4-122">分配 Wi-Fi 配置文件时，用户可以访问公司 Wi-Fi，而无需自行配置。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-122">When you assign a Wi-Fi profile, users get access to your corporate Wi-Fi without having to configure it themselves.</span></span>
<span data-ttu-id="a6ba4-123">详细了解如何[配置网络以进行 HoloLens](hololens-commercial-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="a6ba4-123">Learn more about [configuring your network for HoloLens](hololens-commercial-infrastructure.md)</span></span>

### <a name="certificates"></a><span data-ttu-id="a6ba4-124">证书</span><span class="sxs-lookup"><span data-stu-id="a6ba4-124">Certificates</span></span>
<span data-ttu-id="a6ba4-125">证书通过提供 web 内容的帐户身份验证、Wi-Fi 身份验证、VPN 加密和 SSL 加密来帮助提高安全性。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-125">Certificates help improve security by providing account authentication, Wi-Fi authentication, VPN encryption, and SSL encryption of web content.</span></span> <span data-ttu-id="a6ba4-126">尽管管理员可以通过预配包手动管理设备上的证书，但最佳做法是使用 MDM 系统管理整个生命周期中的那些证书–从注册到续订和吊销。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-126">Although administrators can manage certificates on devices manually through provisioning packages, it’s a best practice to use your MDM system to manage those certificates throughout their entire lifecycle – from enrollment through renewal and revocation.</span></span> <span data-ttu-id="a6ba4-127">注册 (设备后，你的 MDM 系统可以自动将这些证书部署到设备的证书存储中，只要 MDM 系统支持简单证书注册协议 (SCEP) 或公钥加密标准 #12 (PKCS # 12) ) 。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-127">Your MDM system can automatically deploy these certificates to the devices’ certificate stores after you enroll the device (as long as the MDM system supports the Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standards #12 (PKCS#12)).</span></span> <span data-ttu-id="a6ba4-128">MDM 还可以查询和删除已注册的客户端证书，或在当前证书过期之前触发新的注册请求。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-128">MDM can also query and delete enrolled client certificates or trigger a new enrollment request before the current certificate is expired.</span></span> 

### <a name="proxy"></a><span data-ttu-id="a6ba4-129">代理</span><span class="sxs-lookup"><span data-stu-id="a6ba4-129">Proxy</span></span>
<span data-ttu-id="a6ba4-130">大多数公司 intranet 网络都利用代理来管理内部流量。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-130">Most corporate intranet networks leverage a proxy to manage internal traffic.</span></span> <span data-ttu-id="a6ba4-131">使用 HoloLens 2 可以为以太网和 Wi-Fi 连接配置代理服务器。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-131">With HoloLens 2 you can configure a proxy server for ethernet and Wi-Fi connections.</span></span> <span data-ttu-id="a6ba4-132">这些设置不适用于 VPN 连接。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-132">These settings do not apply to VPN connections.</span></span> <span data-ttu-id="a6ba4-133">有关 Windows 10 的代理设置的详细信息，请参阅[NetworkProxy CSP](/windows/client-management/mdm/networkproxy-csp)。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-133">For more details on proxy settings for Windows 10, see [NetworkProxy CSP](/windows/client-management/mdm/networkproxy-csp).</span></span>

### <a name="vpn"></a><span data-ttu-id="a6ba4-134">VPN</span><span class="sxs-lookup"><span data-stu-id="a6ba4-134">VPN</span></span>
<span data-ttu-id="a6ba4-135">组织通常使用 VPN 来控制对其公司 Intranet 上的应用和资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-135">Organizations often use a VPN to control access to apps and resources on their company’s intranet.</span></span> <span data-ttu-id="a6ba4-136">HoloLens 2 支持 SSL VPN 连接，这需要来自 Microsoft Store 的可下载插件并且特定于所选的 VPN 供应商。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-136">HoloLens 2 supports SSL VPN connections, which require a downloadable plugin from the Microsoft Store and are specific to the VPN vendor of your choice.</span></span> 
- <span data-ttu-id="a6ba4-137">阅读[HoloLens 上有关 VPN 的](hololens-network.md#vpn)详细信息。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-137">Read more about [VPN on HoloLens](hololens-network.md#vpn).</span></span>
- <span data-ttu-id="a6ba4-138">有关 VPN 配置文件的详细信息，请参阅 [VPNV2 CSP](/windows/client-management/mdm/vpnv2-csp)。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-138">For more details about VPN profiles, see the [VPNv2 CSP](/windows/client-management/mdm/vpnv2-csp).</span></span>

### <a name="deploy-and-manage-apps"></a><span data-ttu-id="a6ba4-139">部署和管理应用</span><span class="sxs-lookup"><span data-stu-id="a6ba4-139">Deploy and manage apps</span></span>
<span data-ttu-id="a6ba4-140">使用 Intune 可以向运行 Windows Holographic for Business 的设备添加应用。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-140">Using Intune, you can add apps to your devices running Windows Holographic for Business.</span></span> <span data-ttu-id="a6ba4-141">通过 MDM 解决方案，IT 决策者和管理员可通过个人自动安装 (推送) 其内部、业务线应用，或者通过应用商店为一组用户购买应用。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-141">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="a6ba4-142">有多种部署应用的方法，包括：</span><span class="sxs-lookup"><span data-stu-id="a6ba4-142">There are many ways to deploy apps, including:</span></span>
-   [<span data-ttu-id="a6ba4-143">Intune 和公司门户</span><span class="sxs-lookup"><span data-stu-id="a6ba4-143">Intune and Company Portal</span></span>]( app-deploy-intune.md)
-   [<span data-ttu-id="a6ba4-144">适用于企业的 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="a6ba4-144">Microsoft Store for Business</span></span>]( app-deploy-store-business.md)

<span data-ttu-id="a6ba4-145">了解有关通过 Intune 进行的应用管理的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-145">Learn more about app management through Intune.</span></span>
-   [<span data-ttu-id="a6ba4-146">向 Intune 添加应用</span><span class="sxs-lookup"><span data-stu-id="a6ba4-146">Add apps to Intune</span></span>](/mem/intune/apps/apps-add)
-   [<span data-ttu-id="a6ba4-147">添加 Microsoft Store 应用</span><span class="sxs-lookup"><span data-stu-id="a6ba4-147">Add Microsoft Store apps</span></span>](/mem/intune/apps/store-apps-windows)
-   [<span data-ttu-id="a6ba4-148">添加自己创建的应用</span><span class="sxs-lookup"><span data-stu-id="a6ba4-148">Add apps you create</span></span>](/mem/intune/apps/lob-apps-windows)
- [<span data-ttu-id="a6ba4-149">将应用分配给组</span><span class="sxs-lookup"><span data-stu-id="a6ba4-149">Assign apps to groups</span></span>](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a><span data-ttu-id="a6ba4-150">软件更新</span><span class="sxs-lookup"><span data-stu-id="a6ba4-150">Software updates</span></span>
<span data-ttu-id="a6ba4-151">Intune 提供了一个名为“更新圈”的功能供 Windows 10 设备使用。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-151">Intune includes a feature called update rings for Windows 10 devices.</span></span> <span data-ttu-id="a6ba4-152">这些更新圈包括一组用于确定更新安装方式的设置。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-152">These update rings include a group of settings that determine how updates are installed.</span></span> <span data-ttu-id="a6ba4-153">例如，你可以创建一个维护时段来安装更新，也可以选择在安装更新后重新启动。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-153">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span> <span data-ttu-id="a6ba4-154">更新圈可应用于运行 Windows Holographic for Business 的多个设备。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-154">An update ring can be applied to multiple devices running Windows Holographic for Business.</span></span>
<span data-ttu-id="a6ba4-155">详细了解如何通过 Intune[管理 HoloLens 更新](hololens-updates.md)和[管理软件更新](/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-155">Read more about how to [Manage HoloLens updates](hololens-updates.md) and [Manage software updates via Intune](/mem/intune/protect/windows-update-for-business-configure).</span></span>

### <a name="configure-kiosk-mode"></a><span data-ttu-id="a6ba4-156">配置展台模式</span><span class="sxs-lookup"><span data-stu-id="a6ba4-156">Configure kiosk mode</span></span>
<span data-ttu-id="a6ba4-157">使用 Intune 提供的共享或来宾 PC 功能，可将 Windows Holographic for Business 设备配置为作为展台运行。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-157">Using the shared or guest PC features available in Intune, you can configure Windows Holographic for Business devices to run as a kiosk.</span></span> <span data-ttu-id="a6ba4-158">这些设备可以运行一个（单个应用展台模式）或多个应用（多个应用展台模式）。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-158">These devices can run one app (single-app kiosk mode), or run multiple apps (multi-app kiosk mode).</span></span> <span data-ttu-id="a6ba4-159">展台模式是一种 UI，用于控制默认情况下哪些标识有权访问哪些应用。</span><span class="sxs-lookup"><span data-stu-id="a6ba4-159">Kiosk mode is a UI to control which identities have access to which apps by default.</span></span>
<span data-ttu-id="a6ba4-160">了解如何[将 HoloLens 设置为展台]( hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="a6ba4-160">Learn how to [set up HoloLens as a kiosk]( hololens-kiosk.md)</span></span>

