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
ms.openlocfilehash: 0db64ffb4113ff948651c708c28b91da535cb09b
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009520"
---
# <span data-ttu-id="41584-104">将 HoloLens 连接到网络</span><span class="sxs-lookup"><span data-stu-id="41584-104">Connect HoloLens to a network</span></span>

<span data-ttu-id="41584-105">要想在 HoloLens 上进行更多操作，则必须连接到网络。</span><span class="sxs-lookup"><span data-stu-id="41584-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="41584-106">本指南将帮助你：</span><span class="sxs-lookup"><span data-stu-id="41584-106">This guide will help you:</span></span>

- <span data-ttu-id="41584-107">使用 WLAN 或以太网通过 USB-C（仅适用于 HoloLens 2）连接到网络</span><span class="sxs-lookup"><span data-stu-id="41584-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="41584-108">禁用并重新启用 WLAN</span><span class="sxs-lookup"><span data-stu-id="41584-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="41584-109">了解[脱机使用 HoloLens](hololens-offline.md)的更多信息。</span><span class="sxs-lookup"><span data-stu-id="41584-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="41584-110">首次连接</span><span class="sxs-lookup"><span data-stu-id="41584-110">Connecting for the first time</span></span>

<span data-ttu-id="41584-111">首次使用 HoloLens 时，系统会指导你连接到 WLAN 网络。</span><span class="sxs-lookup"><span data-stu-id="41584-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="41584-112">如果在设置期间连接到 WLAN 时遇到问题，请确保你的网络是开放网络、受密码保护网络或者强制门户网络。</span><span class="sxs-lookup"><span data-stu-id="41584-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="41584-113">确保不需要使用证书就能连接网络。</span><span class="sxs-lookup"><span data-stu-id="41584-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="41584-114">完成设置后，你可以连接到其他类型的 WLAN 网络。</span><span class="sxs-lookup"><span data-stu-id="41584-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

<span data-ttu-id="41584-115">在 HoloLens 2 设备上，用户也可以[使用 USB-C 以太网适配器](hololens-connect-devices.md#hololens-2-connect-usb-c-devices)直接连接到 Wi-Fi，帮助协助设置设备。</span><span class="sxs-lookup"><span data-stu-id="41584-115">On HoloLens 2 devices a user may also [use a USB-C to Ethernet adapter](hololens-connect-devices.md#hololens-2-connect-usb-c-devices) to connect directly to Wi-Fi to help assist in setting up the device.</span></span> <span data-ttu-id="41584-116">设置好设备后，用户可以继续使用该适配器，或者可将设备从适配器断开，并且[在设置完毕后连接到 wi-fi](hololens-network.md#connecting-to-wi-fi-after-setup)。</span><span class="sxs-lookup"><span data-stu-id="41584-116">Once the device has been set up a user may continue to user the adapter or they may disconnect the device from the adapter and [connect to wi-fi after set up](hololens-network.md#connecting-to-wi-fi-after-setup).</span></span> 

## <span data-ttu-id="41584-117">设置完成后连接到 WLAN</span><span class="sxs-lookup"><span data-stu-id="41584-117">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="41584-118">执行**开始手势**并选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="41584-118">Preform the **Start gesture** and select **Settings**.</span></span> <span data-ttu-id="41584-119">“设置”应用将自动放置在你面前。</span><span class="sxs-lookup"><span data-stu-id="41584-119">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="41584-120">选择**网络和 Internet** > **WLAN**。</span><span class="sxs-lookup"><span data-stu-id="41584-120">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="41584-121">确保 WLAN 已打开。</span><span class="sxs-lookup"><span data-stu-id="41584-121">Make sure Wi-Fi is turned on.</span></span> <span data-ttu-id="41584-122">如果未看到你的网络，请向下滚动列表。</span><span class="sxs-lookup"><span data-stu-id="41584-122">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="41584-123">选择一个网络，然后选择**连接**。</span><span class="sxs-lookup"><span data-stu-id="41584-123">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="41584-124">如果系统提示你输入网络密码，请键入密码，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="41584-124">If you are prompted for a network password type it and then select **Next**.</span></span>

<span data-ttu-id="41584-125">HoloLens 包含一个支持 802.11ac 的 2x2 WLAN 无线电收发器。</span><span class="sxs-lookup"><span data-stu-id="41584-125">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="41584-126">将 HoloLens 连接到 WLAN 网络的过程类似于将 Windows 10 桌面或移动设备连接到 WLAN 网络。</span><span class="sxs-lookup"><span data-stu-id="41584-126">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![HoloLens WLAN 设置](./images/wifi-hololens-600px.jpg)

<span data-ttu-id="41584-128">你还可以通过检查**开始**菜单中的 WLAN 状态来确认是否连接到 WLAN 网络：</span><span class="sxs-lookup"><span data-stu-id="41584-128">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="41584-129">打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="41584-129">Open the **Start** menu.</span></span>
1. <span data-ttu-id="41584-130">查看**开始**菜单左上方的 WLAN 状态。</span><span class="sxs-lookup"><span data-stu-id="41584-130">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="41584-131">那里将显示 WLAN 状态和已连接网络的 SSID。</span><span class="sxs-lookup"><span data-stu-id="41584-131">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="41584-132">Wi-Fi 连接故障排除</span><span class="sxs-lookup"><span data-stu-id="41584-132">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="41584-133">如果连接到 Wi-fi 时遇到问题，请参阅“[无法连接到 Wi-fi](./hololens-faq.md#i-cant-connect-to-wi-fi)”。</span><span class="sxs-lookup"><span data-stu-id="41584-133">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="41584-134">在设备上登录到企业或组织账户时，如果策略由 IT 管理员配置，也可能应用移动设备管理（MDM）策略。</span><span class="sxs-lookup"><span data-stu-id="41584-134">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="41584-135">VPN</span><span class="sxs-lookup"><span data-stu-id="41584-135">VPN</span></span>
<span data-ttu-id="41584-136">VPN 连接可以帮助提供更安全的连接，并可访问公司网络和 Internet。</span><span class="sxs-lookup"><span data-stu-id="41584-136">A VPN connection can help provide a more secure connection and access to your company's network and the Internet.</span></span> <span data-ttu-id="41584-137">HoloLens 2 支持内置 VPN 客户端和通用 Windows 平台 (UWP) VPN 插件。</span><span class="sxs-lookup"><span data-stu-id="41584-137">HoloLens 2 supports built-in VPN client and Universal Windows Platform (UWP) VPN plug-in.</span></span> 

<span data-ttu-id="41584-138">支持的内置 VPN 协议：</span><span class="sxs-lookup"><span data-stu-id="41584-138">Supported Built-in VPN protocols:</span></span>
- <span data-ttu-id="41584-139">IKEv2</span><span class="sxs-lookup"><span data-stu-id="41584-139">IKEv2</span></span>
- <span data-ttu-id="41584-140">L2TP</span><span class="sxs-lookup"><span data-stu-id="41584-140">L2TP</span></span>
- <span data-ttu-id="41584-141">PPTP</span><span class="sxs-lookup"><span data-stu-id="41584-141">PPTP</span></span>

<span data-ttu-id="41584-142">如果使用证书对内置 VPN 客户端进行身份验证，则需要将所需的客户端证书添加到用户证书存储。</span><span class="sxs-lookup"><span data-stu-id="41584-142">If certificate is used for authentication for built-in VPN client, the required client certificate needs to be added to user certificate store.</span></span> <span data-ttu-id="41584-143">要查找第三方 VPN 插件是否支持 HoloLens 2，请前往 Microsoft Store 定位 VPN 应用并检查 HoloLens 是否被列为支持的设备，以及系统要求页面中应用是否支持 ARM 或 ARM64 架构。</span><span class="sxs-lookup"><span data-stu-id="41584-143">To find if a 3rd party VPN plug-in supports HoloLens 2, go to Store to locate VPN app and check if HoloLens is listed as a supported device and in the System Requirement page the app supports ARM or ARM64 architecture.</span></span> <span data-ttu-id="41584-144">HoloLens 只支持第三方 VPN 的通用 Windows 平台应用程序。</span><span class="sxs-lookup"><span data-stu-id="41584-144">HoloLens only supports Universal Windows Platform applications for 3rd party VPN.</span></span>

<span data-ttu-id="41584-145">默认情况下 VPN 未启用，可通过打开 **设置** 应用然后导航到 **网络和 Internet -> VPN** 手动启用。</span><span class="sxs-lookup"><span data-stu-id="41584-145">VPN is not enabled by default but can be enabled manually by opening **Settings** app and navigating to  **Network & Internet -> VPN**.</span></span> <span data-ttu-id="41584-146">MDM 通过 [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)可管理VPN，并通过 [Vpnv2-csp 策略](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp) 进行设置。</span><span class="sxs-lookup"><span data-stu-id="41584-146">VPN can be managed by MDM via [Settings/AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn), and set via  [Vpnv2-csp policy](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp).</span></span>
<span data-ttu-id="41584-147">了解更多关于[如何配置 VPN ](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn)的信息，可参阅[这些指南](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide)。</span><span class="sxs-lookup"><span data-stu-id="41584-147">Learn more about [how to configure VPN](https://support.microsoft.com/help/20510/windows-10-connect-to-vpn) with [these guides](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-guide).</span></span>  

## <span data-ttu-id="41584-148">在 HoloLens（第一代）上禁用 WLAN</span><span class="sxs-lookup"><span data-stu-id="41584-148">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="41584-149">在 HoloLens 上使用“设置”应用</span><span class="sxs-lookup"><span data-stu-id="41584-149">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="41584-150">打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="41584-150">Open the **Start** menu.</span></span>
1. <span data-ttu-id="41584-151">从**开始**菜单或**开始**菜单右侧的**所有应用**列表中选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="41584-151">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="41584-152">**设置**应用将自动放置在你面前。</span><span class="sxs-lookup"><span data-stu-id="41584-152">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="41584-153">选择**网络和 Internet**。</span><span class="sxs-lookup"><span data-stu-id="41584-153">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="41584-154">选择 WLAN 滑块开关将其移至**关闭**位置。</span><span class="sxs-lookup"><span data-stu-id="41584-154">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="41584-155">这将关闭 WLAN 无线电收发器的射频器件，并禁用 HoloLens 上的所有 WLAN 功能。</span><span class="sxs-lookup"><span data-stu-id="41584-155">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="41584-156">禁用 WLAN 无线电收发器后，HoloLens 将无法自动加载你的[空间](hololens-spaces.md)。</span><span class="sxs-lookup"><span data-stu-id="41584-156">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="41584-157">将滑块开关移至**打开**位置，打开 WLAN 无线电收发器，并在 Microsoft HoloLens 上恢复 WLAN 功能。</span><span class="sxs-lookup"><span data-stu-id="41584-157">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="41584-158">选定的 WLAN 无线电收发器状态（**打开**或**关闭**）将在重启后保持原状态。</span><span class="sxs-lookup"><span data-stu-id="41584-158">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="41584-159">识别你的 HoloLens 在 WLAN 网络上的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="41584-159">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="41584-160">通过使用“设置”应用</span><span class="sxs-lookup"><span data-stu-id="41584-160">By using the Settings app</span></span>

1. <span data-ttu-id="41584-161">打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="41584-161">Open the **Start** menu.</span></span>
1. <span data-ttu-id="41584-162">从**开始**菜单或**开始**菜单右侧的**所有应用**列表中选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="41584-162">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="41584-163">**设置**应用将自动放置在你面前。</span><span class="sxs-lookup"><span data-stu-id="41584-163">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="41584-164">选择**网络和 Internet**。</span><span class="sxs-lookup"><span data-stu-id="41584-164">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="41584-165">向下滚动到可用 WLAN 网络列表下方，选择**硬件属性**。</span><span class="sxs-lookup"><span data-stu-id="41584-165">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![WLAN 设置中的硬件属性](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="41584-167">IP 地址出现在 **IPv4 地址**旁边。</span><span class="sxs-lookup"><span data-stu-id="41584-167">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="41584-168">通过使用语音命令</span><span class="sxs-lookup"><span data-stu-id="41584-168">By using voice commands</span></span>

<span data-ttu-id="41584-169">根据设备版本，可使用内置语音命令或 Cortana 来显示你的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="41584-169">Depending on your devices build you can either use built in voice commands or Cortana to display your IP address.</span></span> <span data-ttu-id="41584-170">[19041.1103](hololens-release-notes.md#windows-holographic-version-2004) 之后的版本，请说“我的 IP 地址是什么？”</span><span class="sxs-lookup"><span data-stu-id="41584-170">On builds after [19041.1103](hololens-release-notes.md#windows-holographic-version-2004) speak "What's my IP address?"</span></span> <span data-ttu-id="41584-171">然后它会显示。</span><span class="sxs-lookup"><span data-stu-id="41584-171">and it will be displayed.</span></span> <span data-ttu-id="41584-172">对于较早的版本或 HoloLens (第一代)，请说“你好小娜，我的 IP 地址是什么？”</span><span class="sxs-lookup"><span data-stu-id="41584-172">For earlier builds or HoloLens (1st gen) say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="41584-173">Cortana 便会显示并读出你的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="41584-173">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="41584-174">通过使用 Windows 设备门户</span><span class="sxs-lookup"><span data-stu-id="41584-174">By using Windows Device Portal</span></span>

1. <span data-ttu-id="41584-175">在电脑上的 Web 浏览器中，打开[设备门户](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。</span><span class="sxs-lookup"><span data-stu-id="41584-175">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="41584-176">导航到**网络**部分。</span><span class="sxs-lookup"><span data-stu-id="41584-176">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="41584-177">此部分将显示你的 IP 地址和其他网络信息。</span><span class="sxs-lookup"><span data-stu-id="41584-177">This section displays your IP address and other network information.</span></span> <span data-ttu-id="41584-178">通过使用此方法，你可以在开发电脑上复制粘贴该 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="41584-178">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
