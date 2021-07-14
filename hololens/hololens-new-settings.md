---
title: 新“设置”应用简介
description: 了解新的“设置”应用
author: joyjaz
ms.author: v-jjaswinski
keywords: HoloLens, 设置, 应用选取器, 音量
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
ms.openlocfilehash: bf1a2080c15346843b9ea9b2d0dc93154e185107
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110398854"
---
# <a name="new-settings-app"></a><span data-ttu-id="eba69-104">新“设置”应用</span><span class="sxs-lookup"><span data-stu-id="eba69-104">New Settings app</span></span>

<span data-ttu-id="eba69-105">在 [Windows 全息版 21H1](hololens-release-notes.md#windows-holographic-version-21h1) 中，我们将引入新版“设置”应用。</span><span class="sxs-lookup"><span data-stu-id="eba69-105">With [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="eba69-106">新的“设置”应用包括 HoloLens 2 在以下领域的新功能和扩展设置：声音、电源和休眠、网络和 Internet、应用、帐户、轻松访问等。</span><span class="sxs-lookup"><span data-stu-id="eba69-106">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="eba69-107">由于新的“设置”应用不同于旧版“设置”应用，因此，此前围绕环境放置的任何“设置”窗口都将在更新时删除。</span><span class="sxs-lookup"><span data-stu-id="eba69-107">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

![新“设置”应用主页](images/new-settings-app.png)

<span data-ttu-id="eba69-109">**新功能和设置**</span><span class="sxs-lookup"><span data-stu-id="eba69-109">**New features and settings**</span></span>
- <span data-ttu-id="eba69-110">设置搜索：使用关键字或设置名称搜索“设置”主页中的设置。</span><span class="sxs-lookup"><span data-stu-id="eba69-110">Settings search: search for settings from the Settings homepage using keywords or the setting's name.</span></span>
- <span data-ttu-id="eba69-111">系统 > [颜色校准](hololens2-display.md#how-to-use-display-color-calibration)</span><span class="sxs-lookup"><span data-stu-id="eba69-111">System > [Color calibration](hololens2-display.md#how-to-use-display-color-calibration)</span></span>
    - <span data-ttu-id="eba69-112">为 HoloLens 2 屏幕选择替代颜色配置文件。</span><span class="sxs-lookup"><span data-stu-id="eba69-112">Select an alternative color profile for your HoloLens 2 display.</span></span>
- <span data-ttu-id="eba69-113">系统> 声音：</span><span class="sxs-lookup"><span data-stu-id="eba69-113">System > Sound:</span></span>
  - <span data-ttu-id="eba69-114">输入和输出音频设备：独立选择输入和输出音频设备（例如，通过蓝牙耳机侦听音频，或使用 USB-C 麦克风进行音频输入）。</span><span class="sxs-lookup"><span data-stu-id="eba69-114">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span>
    > [!NOTE]
    > <span data-ttu-id="eba69-115">HoloLens 2 不支持蓝牙麦克风。</span><span class="sxs-lookup"><span data-stu-id="eba69-115">Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="eba69-116">应用音量：独立调整每个应用的音量。</span><span class="sxs-lookup"><span data-stu-id="eba69-116">App volume: independently adjust the volume of each app.</span></span> <span data-ttu-id="eba69-117">请参阅[每个应用的音量控制](holographic-home.md#per-app-volume-control)。</span><span class="sxs-lookup"><span data-stu-id="eba69-117">See [per app volume control](holographic-home.md#per-app-volume-control).</span></span>
- <span data-ttu-id="eba69-118">系统 > 电源和休眠：如果希望设备在一段时间不活动后进入休眠状态时选择此选项。</span><span class="sxs-lookup"><span data-stu-id="eba69-118">System > Power & sleep: choose when the device should go to sleep after a period of inactivity.</span></span>
- <span data-ttu-id="eba69-119">系统 > 电池：手动启用节电模式或设置节电模式模式自动打开的电池阈值。</span><span class="sxs-lookup"><span data-stu-id="eba69-119">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically.</span></span>
- <span data-ttu-id="eba69-120">设备 > USB：默认禁用 USB 连接。</span><span class="sxs-lookup"><span data-stu-id="eba69-120">Devices > USB: you can disable USB connections by default.</span></span>
- <span data-ttu-id="eba69-121">网络和 Internet：</span><span class="sxs-lookup"><span data-stu-id="eba69-121">Network & Internet:</span></span>
  - <span data-ttu-id="eba69-122">USB-C 以太网适配器将出现在“网络和 Internet”中。</span><span class="sxs-lookup"><span data-stu-id="eba69-122">USB-C Ethernet adapters will now appear in Network & Internet.</span></span>
  - <span data-ttu-id="eba69-123">USB-C 以太网适配器设置现已可用，包括其 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="eba69-123">USB-C Ethernet adapter settings are now available, including its IP address.</span></span>
  - <span data-ttu-id="eba69-124">现在可以在 HoloLens 2 上启用飞行模式。</span><span class="sxs-lookup"><span data-stu-id="eba69-124">You can now enable airplane mode on HoloLens 2.</span></span>
- <span data-ttu-id="eba69-125">应用：可以重置用于文件和链接类型的默认应用。</span><span class="sxs-lookup"><span data-stu-id="eba69-125">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="eba69-126">有关详细信息，请参见[默认应用选取器](holographic-home.md#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="eba69-126">For more information see [Default app picker](holographic-home.md#default-app-picker).</span></span>
- <span data-ttu-id="eba69-127">帐户 > 其他用户：设备所有者可以添加用户、将标准用户升级到设备所有者、将设备所有者降级为标准用户以及删除用户。</span><span class="sxs-lookup"><span data-stu-id="eba69-127">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="eba69-128">轻松访问：更改文本大小和一些视觉效果。</span><span class="sxs-lookup"><span data-stu-id="eba69-128">Ease of Access: change text size and some visual effects.</span></span>

<span data-ttu-id="eba69-129">**已知问题**</span><span class="sxs-lookup"><span data-stu-id="eba69-129">**Known issues**</span></span>
- <span data-ttu-id="eba69-130">将删除之前放置的“设置”窗口（请参见上面的注释）。</span><span class="sxs-lookup"><span data-stu-id="eba69-130">Previously placed Settings windows will be removed (see note above).</span></span>
- <span data-ttu-id="eba69-131">无法再使用“设置”应用重命名设备。</span><span class="sxs-lookup"><span data-stu-id="eba69-131">You can no longer rename your device with the Settings app.</span></span> <span data-ttu-id="eba69-132">IT 管理员可以使用[适用于 HoloLens 2 的 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot) 设备名称模板或 MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 节点来重命名设备。</span><span class="sxs-lookup"><span data-stu-id="eba69-132">IT admins can rename devices by using the [Windows Autopilot for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) device name template or the MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName node.</span></span>
- <span data-ttu-id="eba69-133">“以太网”页随时显示一个虚拟以太网设备（“UsbNcm”）。</span><span class="sxs-lookup"><span data-stu-id="eba69-133">The Ethernet page shows a virtual Ethernet device ("UsbNcm") at all times.</span></span>
- <span data-ttu-id="eba69-134">新 Microsoft Edge 的电池使用情况可能不准确，因为它是一个由 UWP 适配器层支持的 Win32 桌面应用程序（预计近期不会有任何修复）。</span><span class="sxs-lookup"><span data-stu-id="eba69-134">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon).</span></span>

