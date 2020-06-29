---
title: 连接到网络
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
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0bc5a5f7f3eaf3d811da055a7bda664fd3f0daff
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827978"
---
# <span data-ttu-id="c436f-104">连接到网络</span><span class="sxs-lookup"><span data-stu-id="c436f-104">Connect to a network</span></span>

<span data-ttu-id="c436f-105">要想在 HoloLens 上进行更多操作，则必须连接到网络。</span><span class="sxs-lookup"><span data-stu-id="c436f-105">To do most things on your HoloLens, you have to be connected to a network.</span></span> <span data-ttu-id="c436f-106">本指南将帮助你：</span><span class="sxs-lookup"><span data-stu-id="c436f-106">This guide will help you:</span></span>

- <span data-ttu-id="c436f-107">使用 WLAN 或以太网通过 USB-C（仅适用于 HoloLens 2）连接到网络</span><span class="sxs-lookup"><span data-stu-id="c436f-107">Connect to a network using Wi-Fi or (for HoloLens 2 only) Ethernet over USB-C</span></span>
- <span data-ttu-id="c436f-108">禁用并重新启用 WLAN</span><span class="sxs-lookup"><span data-stu-id="c436f-108">Disable and re-enable Wi-Fi</span></span>

<span data-ttu-id="c436f-109">了解[脱机使用 HoloLens](hololens-offline.md)的更多信息。</span><span class="sxs-lookup"><span data-stu-id="c436f-109">Read more about [using HoloLens offline](hololens-offline.md).</span></span>

## <span data-ttu-id="c436f-110">首次连接</span><span class="sxs-lookup"><span data-stu-id="c436f-110">Connecting for the first time</span></span>

<span data-ttu-id="c436f-111">首次使用 HoloLens 时，系统会指导你连接到 WLAN 网络。</span><span class="sxs-lookup"><span data-stu-id="c436f-111">The first time you use your HoloLens, you'll be guided through connecting to a Wi-Fi network.</span></span> <span data-ttu-id="c436f-112">如果在设置期间连接到 WLAN 时遇到问题，请确保你的网络是开放网络、受密码保护网络或者强制门户网络。</span><span class="sxs-lookup"><span data-stu-id="c436f-112">If you have trouble connecting to Wi-Fi during setup, make sure that your network is either an open, password-protected network or a captive portal network.</span></span> <span data-ttu-id="c436f-113">确保不需要使用证书就能连接网络。</span><span class="sxs-lookup"><span data-stu-id="c436f-113">Make sure that the network doesn't require you to use a certificate to connect.</span></span> <span data-ttu-id="c436f-114">完成设置后，你可以连接到其他类型的 WLAN 网络。</span><span class="sxs-lookup"><span data-stu-id="c436f-114">After setup, you can connect to other types of Wi-Fi networks.</span></span>

## <span data-ttu-id="c436f-115">设置完成后连接到 WLAN</span><span class="sxs-lookup"><span data-stu-id="c436f-115">Connecting to Wi-Fi after setup</span></span>

1. <span data-ttu-id="c436f-116">选择**开始** > **设置**。</span><span class="sxs-lookup"><span data-stu-id="c436f-116">Select **Start** > **Settings**.</span></span>
   - <span data-ttu-id="c436f-117">*仅限 HoloLens（第一代）*：通过注视定位“设置”应用，然后通过隔空敲击或说“放置”来进行放置。</span><span class="sxs-lookup"><span data-stu-id="c436f-117">*HoloLens (1st gen) only*: Use your gaze to position the Settings app, then air tap to place it, or say "Place."</span></span>
1. <span data-ttu-id="c436f-118">选择**网络和 Internet** > **WLAN**。</span><span class="sxs-lookup"><span data-stu-id="c436f-118">Select **Network & Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="c436f-119">如果未看到你的网络，请向下滚动列表。</span><span class="sxs-lookup"><span data-stu-id="c436f-119">If you don't see your network, scroll down the list.</span></span>
1. <span data-ttu-id="c436f-120">选择一个网络，然后选择**连接**。</span><span class="sxs-lookup"><span data-stu-id="c436f-120">Select a network, then select **Connect**.</span></span>
1. <span data-ttu-id="c436f-121">如果系统提示你输入网络密码，请键入密码，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c436f-121">If you are prompted for a network password type it and then select **Next**.</span></span>

## <span data-ttu-id="c436f-122">在 HoloLens（第一代）上连接到 WLAN</span><span class="sxs-lookup"><span data-stu-id="c436f-122">Connecting to Wi-Fi on HoloLens (1st gen)</span></span>

<span data-ttu-id="c436f-123">HoloLens 包含一个支持 802.11ac 的 2x2 WLAN 无线电收发器。</span><span class="sxs-lookup"><span data-stu-id="c436f-123">HoloLens contains a 802.11ac-capable, 2x2 Wi-Fi radio.</span></span> <span data-ttu-id="c436f-124">将 HoloLens 连接到 WLAN 网络的过程类似于将 Windows 10 桌面或移动设备连接到 WLAN 网络。</span><span class="sxs-lookup"><span data-stu-id="c436f-124">Connecting HoloLens to a Wi-Fi network is similar to connecting a Windows 10 Desktop or Mobile device to a Wi-Fi network.</span></span>

![HoloLens WLAN 设置](./images/wifi-hololens-600px.jpg)

1. <span data-ttu-id="c436f-126">打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="c436f-126">Open the **Start** menu.</span></span>
1. <span data-ttu-id="c436f-127">从**开始**菜单或**开始**菜单右侧的**所有应用**列表中选择“设置”应用。</span><span class="sxs-lookup"><span data-stu-id="c436f-127">Select the Settings app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="c436f-128">“设置”应用将自动放置在你面前。</span><span class="sxs-lookup"><span data-stu-id="c436f-128">The Settings app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="c436f-129">选择**网络和 Internet**。</span><span class="sxs-lookup"><span data-stu-id="c436f-129">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="c436f-130">确保 WLAN 已打开。</span><span class="sxs-lookup"><span data-stu-id="c436f-130">Make sure Wi-Fi is turned on.</span></span>
1. <span data-ttu-id="c436f-131">从列表中选择 WLAN 网络。</span><span class="sxs-lookup"><span data-stu-id="c436f-131">Select a Wi-Fi network from the list.</span></span>
1. <span data-ttu-id="c436f-132">如果需要，请键入 WLAN 网络密码。</span><span class="sxs-lookup"><span data-stu-id="c436f-132">If needed, type in the Wi-Fi network password.</span></span>

<span data-ttu-id="c436f-133">你还可以通过检查**开始**菜单中的 WLAN 状态来确认是否连接到 WLAN 网络：</span><span class="sxs-lookup"><span data-stu-id="c436f-133">You can also confirm you are connected to a Wi-Fi network by checking the Wi-Fi status in the **Start** menu:</span></span>

1. <span data-ttu-id="c436f-134">打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="c436f-134">Open the **Start** menu.</span></span>
1. <span data-ttu-id="c436f-135">查看**开始**菜单左上方的 WLAN 状态。</span><span class="sxs-lookup"><span data-stu-id="c436f-135">Look at the top left of the **Start** menu for Wi-Fi status.</span></span> <span data-ttu-id="c436f-136">那里将显示 WLAN 状态和已连接网络的 SSID。</span><span class="sxs-lookup"><span data-stu-id="c436f-136">The state of Wi-Fi and the SSID of the connected network will be shown.</span></span>

## <span data-ttu-id="c436f-137">Wi-Fi 连接故障排除</span><span class="sxs-lookup"><span data-stu-id="c436f-137">Troubleshooting your connection to Wi-Fi</span></span>

<span data-ttu-id="c436f-138">如果连接到 Wi-fi 时遇到问题，请参阅“[无法连接到 Wi-fi](./hololens-faq.md#i-cant-connect-to-wi-fi)”。</span><span class="sxs-lookup"><span data-stu-id="c436f-138">If you experience problems connecting to Wi-Fi, see [I can't connect to Wi-Fi](./hololens-faq.md#i-cant-connect-to-wi-fi).</span></span>

<span data-ttu-id="c436f-139">在设备上登录到企业或组织账户时，如果策略由 IT 管理员配置，也可能应用移动设备管理（MDM）策略。</span><span class="sxs-lookup"><span data-stu-id="c436f-139">When you sign into an enterprise or organizational account on the device, it may also apply Mobile Device Management (MDM) policy, if the policy is configured by your IT administrator.</span></span>

## <span data-ttu-id="c436f-140">在 HoloLens（第一代）上禁用 WLAN</span><span class="sxs-lookup"><span data-stu-id="c436f-140">Disabling Wi-Fi on HoloLens (1st gen)</span></span>

### <span data-ttu-id="c436f-141">在 HoloLens 上使用“设置”应用</span><span class="sxs-lookup"><span data-stu-id="c436f-141">Using the Settings app on HoloLens</span></span>

1. <span data-ttu-id="c436f-142">打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="c436f-142">Open the **Start** menu.</span></span>
1. <span data-ttu-id="c436f-143">从**开始**菜单或**开始**菜单右侧的**所有应用**列表中选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="c436f-143">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="c436f-144">**设置**应用将自动放置在你面前。</span><span class="sxs-lookup"><span data-stu-id="c436f-144">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="c436f-145">选择**网络和 Internet**。</span><span class="sxs-lookup"><span data-stu-id="c436f-145">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="c436f-146">选择 WLAN 滑块开关将其移至**关闭**位置。</span><span class="sxs-lookup"><span data-stu-id="c436f-146">Select the Wi-Fi slider switch to move it to the **Off** position.</span></span> <span data-ttu-id="c436f-147">这将关闭 WLAN 无线电收发器的射频器件，并禁用 HoloLens 上的所有 WLAN 功能。</span><span class="sxs-lookup"><span data-stu-id="c436f-147">This will turn off the RF components of the Wi-Fi radio and disable all Wi-Fi functionality on HoloLens.</span></span>

    > [!WARNING]
    > <span data-ttu-id="c436f-148">禁用 WLAN 无线电收发器后，HoloLens 将无法自动加载你的[空间](hololens-spaces.md)。</span><span class="sxs-lookup"><span data-stu-id="c436f-148">When the Wi-Fi radio is disabled, HoloLens will not be able to automatically load your [spaces](hololens-spaces.md).</span></span>

1. <span data-ttu-id="c436f-149">将滑块开关移至**打开**位置，打开 WLAN 无线电收发器，并在 Microsoft HoloLens 上恢复 WLAN 功能。</span><span class="sxs-lookup"><span data-stu-id="c436f-149">Move the slider switch to the **On** position to turn on the Wi-Fi radio and restore Wi-Fi functionality on Microsoft HoloLens.</span></span> <span data-ttu-id="c436f-150">选定的 WLAN 无线电收发器状态（**打开**或**关闭**）将在重启后保持原状态。</span><span class="sxs-lookup"><span data-stu-id="c436f-150">The selected Wi-Fi radio state (**On** or **Off**) will persist across reboots.</span></span>

## <span data-ttu-id="c436f-151">识别你的 HoloLens 在 WLAN 网络上的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="c436f-151">Identifying the IP Address of your HoloLens on the Wi-Fi network</span></span>

### <span data-ttu-id="c436f-152">通过使用“设置”应用</span><span class="sxs-lookup"><span data-stu-id="c436f-152">By using the Settings app</span></span>

1. <span data-ttu-id="c436f-153">打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="c436f-153">Open the **Start** menu.</span></span>
1. <span data-ttu-id="c436f-154">从**开始**菜单或**开始**菜单右侧的**所有应用**列表中选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="c436f-154">Select the **Settings** app from **Start** or from the **All Apps** list on the right of the **Start** menu.</span></span> <span data-ttu-id="c436f-155">**设置**应用将自动放置在你面前。</span><span class="sxs-lookup"><span data-stu-id="c436f-155">The **Settings** app will be auto-placed in front of you.</span></span>
1. <span data-ttu-id="c436f-156">选择**网络和 Internet**。</span><span class="sxs-lookup"><span data-stu-id="c436f-156">Select **Network & Internet**.</span></span>
1. <span data-ttu-id="c436f-157">向下滚动到可用 WLAN 网络列表下方，选择**硬件属性**。</span><span class="sxs-lookup"><span data-stu-id="c436f-157">Scroll down to beneath the list of available Wi-Fi networks and select **Hardware properties**.</span></span>

    ![WLAN 设置中的硬件属性](./images/wifi-hololens-hwdetails.jpg)

   <span data-ttu-id="c436f-159">IP 地址出现在 **IPv4 地址**旁边。</span><span class="sxs-lookup"><span data-stu-id="c436f-159">The IP address appears next to **IPv4 address**.</span></span>

### <span data-ttu-id="c436f-160">通过使用 Cortana</span><span class="sxs-lookup"><span data-stu-id="c436f-160">By using Cortana</span></span>

<span data-ttu-id="c436f-161">说：“你好小娜，我的 IP 地址是什么？”，</span><span class="sxs-lookup"><span data-stu-id="c436f-161">Say "Hey Cortana, What's my IP address?"</span></span> <span data-ttu-id="c436f-162">Cortana 便会显示并读出你的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c436f-162">and Cortana will display and read out your IP address.</span></span>

### <span data-ttu-id="c436f-163">通过使用 Windows 设备门户</span><span class="sxs-lookup"><span data-stu-id="c436f-163">By using Windows Device Portal</span></span>

1. <span data-ttu-id="c436f-164">在电脑上的 Web 浏览器中，打开[设备门户](/windows/mixed-reality/using-the-windows-device-portal.md#networking)。</span><span class="sxs-lookup"><span data-stu-id="c436f-164">In a web browser on your PC, open the [device portal](/windows/mixed-reality/using-the-windows-device-portal.md#networking).</span></span>
1. <span data-ttu-id="c436f-165">导航到**网络**部分。</span><span class="sxs-lookup"><span data-stu-id="c436f-165">Navigate to the **Networking** section.</span></span>  
   <span data-ttu-id="c436f-166">此部分将显示你的 IP 地址和其他网络信息。</span><span class="sxs-lookup"><span data-stu-id="c436f-166">This section displays your IP address and other network information.</span></span> <span data-ttu-id="c436f-167">通过使用此方法，你可以在开发电脑上复制粘贴该 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c436f-167">By using this method, you can copy and paste of the IP address on your development PC.</span></span>
