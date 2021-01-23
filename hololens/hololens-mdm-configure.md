---
title: 使用 Microsoft 的 Endpoint Manager Intune 管理 HoloLens 设备
description: 了解如何使用 MDM 使用 Intune 大规模配置云解决方案提供商、策略和管理 HoloLens 混合现实设备。
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
ms.openlocfilehash: ce288afdcb112c17ffde75078d641f3637a8448c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283953"
---
# <span data-ttu-id="27fd9-103">使用 Microsoft 的 Endpoint Manager Intune 管理 HoloLens 设备</span><span class="sxs-lookup"><span data-stu-id="27fd9-103">Using Microsoft’s Endpoint Manager Intune to manage HoloLens devices</span></span>

<span data-ttu-id="27fd9-104">可以通过 MDM 管理许多不同的设置。</span><span class="sxs-lookup"><span data-stu-id="27fd9-104">There are numerous different settings you can manage via MDM.</span></span> <span data-ttu-id="27fd9-105">使用 Intune 设备可以组合在一起，并且可以将配置部署到这些用户组或设备组。</span><span class="sxs-lookup"><span data-stu-id="27fd9-105">Using Intune devices can be grouped together and configurations can be deployed to those groups of users or devices.</span></span> <span data-ttu-id="27fd9-106">还可以部署和管理应用、将设备设置为连接到网络，以及配置在所需时间和所需的更新环上发生的更新。</span><span class="sxs-lookup"><span data-stu-id="27fd9-106">Apps can also be deployed and managed, setting up devices to connect to your network, as well as configuring updates to occur at the time desired and on the update ring needed.</span></span> 

## <span data-ttu-id="27fd9-107">如何通过 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="27fd9-107">How to manage via Intune</span></span>

### <span data-ttu-id="27fd9-108">设备类别和组</span><span class="sxs-lookup"><span data-stu-id="27fd9-108">Device categories and groups</span></span>
<span data-ttu-id="27fd9-109">使用 Intune，你可以创建设备类别，以根据你创建的类别（如工程、医疗、开发人员等）将设备自动添加到组。</span><span class="sxs-lookup"><span data-stu-id="27fd9-109">Using Intune, you can create device categories to automatically add devices to groups based on categories that you create, such as Engineering, Medical, Developers, and so on.</span></span> <span data-ttu-id="27fd9-110">其理念是更轻松地管理运行 Windows Holographic for Business 的设备。</span><span class="sxs-lookup"><span data-stu-id="27fd9-110">The idea is to make it easier to manage your devices running Windows Holographic for Business.</span></span>
<span data-ttu-id="27fd9-111">阅读更多内容 [：将设备分为多个组](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)</span><span class="sxs-lookup"><span data-stu-id="27fd9-111">Read more: [Categorize devices into groups](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)</span></span>

### <span data-ttu-id="27fd9-112">设备配置文件</span><span class="sxs-lookup"><span data-stu-id="27fd9-112">Device configuration profiles</span></span>
<span data-ttu-id="27fd9-113">Intune 包括可在组织的不同设备上启用或禁用的设置和功能。</span><span class="sxs-lookup"><span data-stu-id="27fd9-113">Intune includes settings and features that you can enable or disable on different devices within your organization.</span></span> <span data-ttu-id="27fd9-114">这些设置和功能使用配置文件进行管理。</span><span class="sxs-lookup"><span data-stu-id="27fd9-114">These settings and features are managed using profiles.</span></span> <span data-ttu-id="27fd9-115">例如，你可以创建启用 Cortana 的配置文件，或在运行 Windows Holographic for Business 的设备上使用 Microsoft Defender 智能屏幕。</span><span class="sxs-lookup"><span data-stu-id="27fd9-115">For example, you can create a profile that enables Cortana, or uses Microsoft Defender Smart Screen on your devices running Windows Holographic for Business.</span></span>
<span data-ttu-id="27fd9-116">在配置文件中，可以使用 OMA-URI 自定义一些设置、创建设备限制，以及配置虚拟专用网络 (VPN) WI-Fi。</span><span class="sxs-lookup"><span data-stu-id="27fd9-116">In your profiles, you can use OMA-URI to customize some settings, create device restrictions, and configure a virtual private network (VPN) and Wi-Fi.</span></span>
<span data-ttu-id="27fd9-117">[配置文件和配置文件概述](https://docs.microsoft.com/mem/intune/configuration/device-profiles)[入门](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)。</span><span class="sxs-lookup"><span data-stu-id="27fd9-117">[Get started with configuration profiles](https://docs.microsoft.com/mem/intune/configuration/device-profiles), and [profile overview](https://docs.microsoft.com/mem/intune/configuration/device-profile-create).</span></span>

## <span data-ttu-id="27fd9-118">可以管理和配置哪些功能的示例</span><span class="sxs-lookup"><span data-stu-id="27fd9-118">Examples of what can be managed and configured</span></span>

<span data-ttu-id="27fd9-119">使用 MDM 管理设备会提供大量可选项。</span><span class="sxs-lookup"><span data-stu-id="27fd9-119">Using MDM to manage devices gives a wide array of items that can be selected.</span></span> 

### <span data-ttu-id="27fd9-120">WLAN</span><span class="sxs-lookup"><span data-stu-id="27fd9-120">Wi-Fi</span></span>
<span data-ttu-id="27fd9-121">[WLAN 设置](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) 将无线网络设置分配给用户和设备。</span><span class="sxs-lookup"><span data-stu-id="27fd9-121">[Wi-Fi settings](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) assigns wireless network settings to users and devices.</span></span> <span data-ttu-id="27fd9-122">分配一个Wi-Fi配置文件时，用户无需自行Wi-Fi即可访问你的公司网站。</span><span class="sxs-lookup"><span data-stu-id="27fd9-122">When you assign a Wi-Fi profile, users get access to your corporate Wi-Fi without having to configure it themselves.</span></span>
<span data-ttu-id="27fd9-123">了解有关为 [HoloLens 配置网络](hololens-commercial-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="27fd9-123">Learn more about [configuring your network for HoloLens](hololens-commercial-infrastructure.md)</span></span>

### <span data-ttu-id="27fd9-124">证书</span><span class="sxs-lookup"><span data-stu-id="27fd9-124">Certificates</span></span>
<span data-ttu-id="27fd9-125">证书通过提供帐户身份验证、Wi-Fi、VPN 加密和 Web 内容的 SSL 加密来帮助提高安全性。</span><span class="sxs-lookup"><span data-stu-id="27fd9-125">Certificates help improve security by providing account authentication, Wi-Fi authentication, VPN encryption, and SSL encryption of web content.</span></span> <span data-ttu-id="27fd9-126">尽管管理员可以通过预配包手动管理设备上证书，但最佳做法是在整个生命周期（从注册到续订和吊销）使用 MDM 系统管理这些证书。</span><span class="sxs-lookup"><span data-stu-id="27fd9-126">Although administrators can manage certificates on devices manually through provisioning packages, it’s a best practice to use your MDM system to manage those certificates throughout their entire lifecycle – from enrollment through renewal and revocation.</span></span> <span data-ttu-id="27fd9-127">MDM 系统可以在注册设备 (后自动将这些证书部署到设备的证书存储，只要 MDM 系统支持简单证书注册协议 (SCEP) 或公钥加密标准 #12 (PKCS#12) ) 。</span><span class="sxs-lookup"><span data-stu-id="27fd9-127">Your MDM system can automatically deploy these certificates to the devices’ certificate stores after you enroll the device (as long as the MDM system supports the Simple Certificate Enrollment Protocol (SCEP) or Public Key Cryptography Standards #12 (PKCS#12)).</span></span> <span data-ttu-id="27fd9-128">MDM 还可以在当前证书过期之前查询和删除已注册的客户端证书或触发新的注册请求。</span><span class="sxs-lookup"><span data-stu-id="27fd9-128">MDM can also query and delete enrolled client certificates or trigger a new enrollment request before the current certificate is expired.</span></span> 

### <span data-ttu-id="27fd9-129">代理</span><span class="sxs-lookup"><span data-stu-id="27fd9-129">Proxy</span></span>
<span data-ttu-id="27fd9-130">大多数企业 Intranet 网络都利用代理来管理内部流量。</span><span class="sxs-lookup"><span data-stu-id="27fd9-130">Most corporate intranet networks leverage a proxy to manage internal traffic.</span></span> <span data-ttu-id="27fd9-131">使用 HoloLens 2，可以配置用于以太网和 Wi-Fi连接的代理服务器。</span><span class="sxs-lookup"><span data-stu-id="27fd9-131">With HoloLens 2 you can configure a proxy server for ethernet and Wi-Fi connections.</span></span> <span data-ttu-id="27fd9-132">这些设置不适用于 VPN 连接。</span><span class="sxs-lookup"><span data-stu-id="27fd9-132">These settings do not apply to VPN connections.</span></span> <span data-ttu-id="27fd9-133">有关 Windows 10 的代理设置的更多详细信息，请参阅[NetworkProxy CSP。](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)</span><span class="sxs-lookup"><span data-stu-id="27fd9-133">For more details on proxy settings for Windows 10, see [NetworkProxy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp).</span></span>

### <span data-ttu-id="27fd9-134">VPN</span><span class="sxs-lookup"><span data-stu-id="27fd9-134">VPN</span></span>
<span data-ttu-id="27fd9-135">组织通常使用 VPN 来控制对其公司 Intranet 上的应用和资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="27fd9-135">Organizations often use a VPN to control access to apps and resources on their company’s intranet.</span></span> <span data-ttu-id="27fd9-136">HoloLens 2 支持 SSL VPN 连接，这需要从 Microsoft Store 下载插件，并且特定于你选择的 VPN 供应商。</span><span class="sxs-lookup"><span data-stu-id="27fd9-136">HoloLens 2 supports SSL VPN connections, which require a downloadable plugin from the Microsoft Store and are specific to the VPN vendor of your choice.</span></span> 
- <span data-ttu-id="27fd9-137">阅读有关 [HoloLens 上的 VPN 的更多信息](hololens-network.md#vpn)。</span><span class="sxs-lookup"><span data-stu-id="27fd9-137">Read more about [VPN on HoloLens](hololens-network.md#vpn).</span></span>
- <span data-ttu-id="27fd9-138">有关 VPN 配置文件的更多详细信息，请参阅[VPNv2 CSP。](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)</span><span class="sxs-lookup"><span data-stu-id="27fd9-138">For more details about VPN profiles, see the [VPNv2 CSP](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>

### <span data-ttu-id="27fd9-139">部署和管理应用</span><span class="sxs-lookup"><span data-stu-id="27fd9-139">Deploy and manage apps</span></span>
<span data-ttu-id="27fd9-140">使用 Intune，你可以将应用添加到运行 Windows Holographic for Business 的设备。</span><span class="sxs-lookup"><span data-stu-id="27fd9-140">Using Intune, you can add apps to your devices running Windows Holographic for Business.</span></span> <span data-ttu-id="27fd9-141">MDM 解决方案使 IT 决策者和管理员可以专用地自动安装 (推送) 其内部、业务线应用，或通过应用商店为一组用户购买应用。</span><span class="sxs-lookup"><span data-stu-id="27fd9-141">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="27fd9-142">部署应用的方法有很多，包括：</span><span class="sxs-lookup"><span data-stu-id="27fd9-142">There are many ways to deploy apps, including:</span></span>
-   [<span data-ttu-id="27fd9-143">Intune 和公司门户</span><span class="sxs-lookup"><span data-stu-id="27fd9-143">Intune and Company Portal</span></span>]( app-deploy-intune.md)
-   [<span data-ttu-id="27fd9-144">适用于企业的 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="27fd9-144">Microsoft Store for Business</span></span>]( app-deploy-store-business.md)

<span data-ttu-id="27fd9-145">详细了解如何通过 Intune 管理应用。</span><span class="sxs-lookup"><span data-stu-id="27fd9-145">Learn more about app management through Intune.</span></span>
-   [<span data-ttu-id="27fd9-146">将应用添加到 Intune</span><span class="sxs-lookup"><span data-stu-id="27fd9-146">Add apps to Intune</span></span>](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [<span data-ttu-id="27fd9-147">添加 Microsoft Store 应用</span><span class="sxs-lookup"><span data-stu-id="27fd9-147">Add Microsoft Store apps</span></span>](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [<span data-ttu-id="27fd9-148">添加你创建的应用</span><span class="sxs-lookup"><span data-stu-id="27fd9-148">Add apps you create</span></span>](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [<span data-ttu-id="27fd9-149">将应用分配给组</span><span class="sxs-lookup"><span data-stu-id="27fd9-149">Assign apps to groups</span></span>](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### <span data-ttu-id="27fd9-150">软件更新</span><span class="sxs-lookup"><span data-stu-id="27fd9-150">Software updates</span></span>
<span data-ttu-id="27fd9-151">Intune 包括一项称为 Windows 10 设备的更新圈的功能。</span><span class="sxs-lookup"><span data-stu-id="27fd9-151">Intune includes a feature called update rings for Windows 10 devices.</span></span> <span data-ttu-id="27fd9-152">这些更新圈包括一组确定如何安装更新的设置。</span><span class="sxs-lookup"><span data-stu-id="27fd9-152">These update rings include a group of settings that determine how updates are installed.</span></span> <span data-ttu-id="27fd9-153">例如，可以创建维护时间窗口来安装更新，或选择在安装更新后重启。</span><span class="sxs-lookup"><span data-stu-id="27fd9-153">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span> <span data-ttu-id="27fd9-154">更新圈可应用于运行 Windows Holographic for Business 的多个设备。</span><span class="sxs-lookup"><span data-stu-id="27fd9-154">An update ring can be applied to multiple devices running Windows Holographic for Business.</span></span>
<span data-ttu-id="27fd9-155">阅读更多有关通过 Intune 管理 [HoloLens](hololens-updates.md) 更新 [和管理软件更新的信息](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。</span><span class="sxs-lookup"><span data-stu-id="27fd9-155">Read more about how to [Manage HoloLens updates](hololens-updates.md) and [Manage software updates via Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

### <span data-ttu-id="27fd9-156">配置展台模式</span><span class="sxs-lookup"><span data-stu-id="27fd9-156">Configure kiosk mode</span></span>
<span data-ttu-id="27fd9-157">使用 Intune 中提供的共享或来宾电脑功能，你可以将 Windows Holographic for Business 设备配置为作为展台运行。</span><span class="sxs-lookup"><span data-stu-id="27fd9-157">Using the shared or guest PC features available in Intune, you can configure Windows Holographic for Business devices to run as a kiosk.</span></span> <span data-ttu-id="27fd9-158">这些设备可以在单应用展台 (运行一个应用) ，或在多应用展台模式下 (多个应用) 。</span><span class="sxs-lookup"><span data-stu-id="27fd9-158">These devices can run one app (single-app kiosk mode), or run multiple apps (multi-app kiosk mode).</span></span> <span data-ttu-id="27fd9-159">展台模式是一种 UI，用于控制默认情况下哪些标识有权访问哪些应用。</span><span class="sxs-lookup"><span data-stu-id="27fd9-159">Kiosk mode is a UI to control which identities have access to which apps by default.</span></span>
<span data-ttu-id="27fd9-160">了解如何将 [HoloLens 设置为展台]( hololens-kiosk.md)</span><span class="sxs-lookup"><span data-stu-id="27fd9-160">Learn how to [set up HoloLens as a kiosk]( hololens-kiosk.md)</span></span>

