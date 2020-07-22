---
title: 将 HoloLens 连接到网络
description: 介绍如何使用 HoloLens 连接到 Internet 以及如何识别设备的 IP 地址。
ms.assetid: 0895606e-96c0-491e-8b1c-52e56b00365d
author: mattzmsft
ms.author: mazeller
keywords: HoloLens, wifi, 无线, Internet, ip, ip 地址
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
ms.openlocfilehash: 0f46ff4a1bef95d153d9fa93c746c8977dc49771
ms.sourcegitcommit: 47bc3b696936dd7011b3f9dd683deb872ed25b90
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "10883146"
---
# <span data-ttu-id="87b39-104">将 HoloLens 连接到网络</span><span class="sxs-lookup"><span data-stu-id="87b39-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="87b39-105">要想在 HoloLens 上进行更多操作，则必须连接到网络。</span><span class="sxs-lookup"><span data-stu-id="87b39-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="87b39-106">本指南将帮助你：</span><span class="sxs-lookup"><span data-stu-id="87b39-106">This guide will help you:</span></span>

- <span data-ttu-id="87b39-107">使用 WLAN 或以太网通过 USB-C（仅适用于 HoloLens 2）连接到网络</span><span class="sxs-lookup"><span data-stu-id="87b39-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="87b39-108">禁用并重新启用 WLAN</span><span class="sxs-lookup"><span data-stu-id="87b39-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="87b39-109">了解[脱机使用 HoloLens](hololens-offline.md)的更多信息。</span><span class="sxs-lookup"><span data-stu-id="87b39-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="87b39-110">首次连接</span><span class="sxs-lookup"><span data-stu-id="87b39-110">Connecting for the first time</span></span>

<span data-ttu-id="87b39-111">首次使用 HoloLens 时，系统会指导你连接到 WLAN 网络。</span><span class="sxs-lookup"><span data-stu-id="87b39-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="87b39-112">如果在设置期间连接到 WLAN 时遇到问题，请确保你的网络是开放网络、受密码保护网络或者强制门户网络。</span><span class="sxs-lookup"><span data-stu-id="87b39-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="87b39-113">确保不需要使用证书就能连接网络。</span><span class="sxs-lookup"><span data-stu-id="87b39-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="87b39-114">完成设置后，你可以连接到其他类型的 WLAN 网络。</span><span class="sxs-lookup"><span data-stu-id="87b39-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

## <span data-ttu-id="87b39-115">设置完成后连接到 WLAN</span><span class="sxs-lookup"><span data-stu-id="87b39-115">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="87b39-116">执行**开始手势**并选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="87b39-116">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="87b39-117">“设置”应用将自动放置在你面前。</span><span class="sxs-lookup"><span data-stu-id="87b39-117">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="87b39-118">选择**网络和 Internet** > **WLAN**。</span><span class="sxs-lookup"><span data-stu-id="87b39-118">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="87b39-119">确保 WLAN 已打开。</span><span class="sxs-lookup"><span data-stu-id="87b39-119">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="87b39-120">如果未看到你的网络，请向下滚动列表。</span><span class="sxs-lookup"><span data-stu-id="87b39-120">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="87b39-121">选择一个网络，然后选择**连接**。</span><span class="sxs-lookup"><span data-stu-id="87b39-121">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="87b39-122">如果系统提示你输入网络密码，请键入密码，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="87b39-122">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="87b39-123">HoloLens 包含一个支持 802.11ac 的 2x2 WLAN 无线电收发器。</span><span class="sxs-lookup"><span data-stu-id="87b39-123">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="87b39-124">将 HoloLens 连接到 WLAN 网络的过程类似于将 Windows 10 桌面或移动设备连接到 WLAN 网络。</span><span class="sxs-lookup"><span data-stu-id="87b39-124">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![HoloLens WLAN 设置](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="87b39-126">你还可以通过检查**开始**菜单中的 WLAN 状态来确认是否连接到 WLAN 网络：</span><span class="sxs-lookup"><span data-stu-id="87b39-126">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="87b39-127">打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="87b39-127">Open the **Start** menu.</span></span>
1. <span data-ttu-id="87b39-128">查看**开始**菜单左上方的 WLAN 状态。</span><span class="sxs-lookup"><span data-stu-id="87b39-128">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="87b39-129">那里将显示 WLAN 状态和已连接网络的 SSID。</span><span class="sxs-lookup"><span data-stu-id="87b39-129">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="87b39-130">Wi-Fi 连接故障排除</span><span class="sxs-lookup"><span data-stu-id="87b39-130">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="87b39-131">如果连接到 Wi-fi 时遇到问题，请参阅“[无法连接到 Wi-fi](./hololens-faq.md#i-cant-connect-to-wi-fi)”。</span><span class="sxs-lookup"><span data-stu-id="87b39-131">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="87b39-132">在设备上登录到企业或组织账户时，如果策略由 IT 管理员配置，也可能应用移动设备管理（MDM）策略。</span><span class="sxs-lookup"><span data-stu-id="87b39-132">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="87b39-133">VPN</span><span class="sxs-lookup"><span data-stu-id="87b39-133">VPN</span></span>
<span data-ttu-id="87b39-134">VPN 连接可以帮助提供更安全的连接，并可访问公司网络和 Internet。</span><span class="sxs-lookup"><span data-stu-id="87b39-134">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="87b39-135">HoloLens 2 支持内置 VPN 客户端和通用 Windows 平台 (UWP) VPN 插件。</span><span class="sxs-lookup"><span data-stu-id="87b39-135">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="87b39-136">支持的内置 VPN 协议：</span><span class="sxs-lookup"><span data-stu-id="87b39-136">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="87b39-137">IKEv2</span><span class="sxs-lookup"><span data-stu-id="87b39-137">IKEv2</span></span>
- <span data-ttu-id="87b39-138">L2TP</span><span class="sxs-lookup"><span data-stu-id="87b39-138">L2TP</span></span>
- <span data-ttu-id="87b39-139">PPTP</span><span class="sxs-lookup"><span data-stu-id="87b39-139">PPTP</span></span>

<span data-ttu-id="87b39-140">如果使用证书对内置 VPN 客户端进行身份验证，则需要将所需的客户端证书添加到用户证书存储。</span><span class="sxs-lookup"><span data-stu-id="87b39-140">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="87b39-141">要查找第三方 VPN 插件是否支持 HoloLens 2，请前往 Microsoft Store 定位 VPN 应用并检查 HoloLens 是否被列为支持的设备，以及系统要求页面中应用是否支持 ARM 或 ARM64 架构。</span><span class="sxs-lookup"><span data-stu-id="87b39-141">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="87b39-142">HoloLens 只支持第三方 VPN 的通用 Windows 平台应用程序。</span><span class="sxs-lookup"><span data-stu-id="87b39-142">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

<span data-ttu-id="87b39-143">默认情况下 VPN 未启用，可通过打开 **设置** 应用然后导航到 **网络和 Internet -> VPN** 手动启用。</span><span class="sxs-lookup"><span data-stu-id="87b39-143">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span> <span data-ttu-id="87b39-144">MDM 通过 [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)可管理VPN，并通过 [Vpnv2-csp 策略](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp) 进行设置。</span><span class="sxs-lookup"><span data-stu-id="87b39-144">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>
<span data-ttu-id="87b39-145">了解更多关于[如何配置 VPN ](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)的信息，可参阅[这些指南](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)。</span><span class="sxs-lookup"><span data-stu-id="87b39-145">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

## <span data-ttu-id="87b39-146">在 HoloLens（第一代）上禁用 WLAN</span><span class="sxs-lookup"><span data-stu-id="87b39-146">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="87b39-147">在 HoloLens 上使用“设置”应用</span><span class="sxs-lookup"><span data-stu-id="87b39-147">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="87b39-148">打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="87b39-148">Open the **Start** menu.</span></span>
1. <span data-ttu-id="87b39-149">从**开始**菜单或**开始**菜单右侧的**所有应用**列表中选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="87b39-149">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="87b39-150">**设置**应用将自动放置在你面前。</span><span class="sxs-lookup"><span data-stu-id="87b39-150">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="87b39-151">选择**网络和 Internet**。</span><span class="sxs-lookup"><span data-stu-id="87b39-151">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="87b39-152">选择 WLAN 滑块开关将其移至**关闭**位置。</span><span class="sxs-lookup"><span data-stu-id="87b39-152">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="87b39-153">这将关闭 WLAN 无线电收发器的射频器件，并禁用 HoloLens 上的所有 WLAN 功能。</span><span class="sxs-lookup"><span data-stu-id="87b39-153">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="87b39-154">禁用 WLAN 无线电收发器后，HoloLens 将无法自动加载你的[空间](hololens-spaces.md)。</span><span class="sxs-lookup"><span data-stu-id="87b39-154">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="87b39-155">将滑块开关移至**打开**位置，打开 WLAN 无线电收发器，并在 Microsoft HoloLens 上恢复 WLAN 功能。</span><span class="sxs-lookup"><span data-stu-id="87b39-155">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="87b39-156">选定的 WLAN 无线电收发器状态（**打开**或**关闭**）将在重启后保持原状态。</span><span class="sxs-lookup"><span data-stu-id="87b39-156">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="87b39-157">识别你的 HoloLens 在 WLAN 网络上的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="87b39-157">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="87b39-158">通过使用“设置”应用</span><span class="sxs-lookup"><span data-stu-id="87b39-158">By using the Settings app</span></span>

1. <span data-ttu-id="87b39-159">打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="87b39-159">Open the **Start** menu.</span></span>
1. <span data-ttu-id="87b39-160">从**开始**菜单或**开始**菜单右侧的**所有应用**列表中选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="87b39-160">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="87b39-161">**设置**应用将自动放置在你面前。</span><span class="sxs-lookup"><span data-stu-id="87b39-161">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="87b39-162">选择**网络和 Internet**。</span><span class="sxs-lookup"><span data-stu-id="87b39-162">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="87b39-163">向下滚动到可用 WLAN 网络列表下方，选择**硬件属性**。</span><span class="sxs-lookup"><span data-stu-id="87b39-163">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![WLAN 设置中的硬件属性](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="87b39-165">IP 地址出现在 **IPv4 地址**旁边。</span><span class="sxs-lookup"><span data-stu-id="87b39-165">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="87b39-166">通过使用语音命令</span><span class="sxs-lookup"><span data-stu-id="87b39-166">By using voice commands</span></span>

<span data-ttu-id="87b39-167">根据设备版本，可使用内置语音命令或 Cortana 来显示你的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="87b39-167">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="87b39-168">[19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 之后的版本，请说“我的 IP 地址是什么？”</span><span class="sxs-lookup"><span data-stu-id="87b39-168">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="87b39-169">然后它会显示。</span><span class="sxs-lookup"><span data-stu-id="87b39-169">and it will be displayed.</span></span> <span data-ttu-id="87b39-170">对于较早的版本或 HoloLens (第一代)，请说“你好小娜，我的 IP 地址是什么？”</span><span class="sxs-lookup"><span data-stu-id="87b39-170">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="87b39-171">Cortana 便会显示并读出你的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="87b39-171">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="87b39-172">通过使用 Windows 设备门户</span><span class="sxs-lookup"><span data-stu-id="87b39-172">By using Windows Device Portal</span></span>

1. <span data-ttu-id="87b39-173">在电脑上的 Web 浏览器中，打开[设备门户](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。</span><span class="sxs-lookup"><span data-stu-id="87b39-173">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="87b39-174">导航到**网络**部分。</span><span class="sxs-lookup"><span data-stu-id="87b39-174">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="87b39-175">此部分将显示你的 IP 地址和其他网络信息。</span><span class="sxs-lookup"><span data-stu-id="87b39-175">This section displays your IP address and other network information.</span></span> <span data-ttu-id="87b39-176">通过使用此方法，你可以在开发电脑上复制粘贴该 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="87b39-176">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
