---
title: 连接到蓝牙和 USB-C 设备
description: 本指南介绍了如何连接到蓝牙和 USB-C 设备和配件。
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2f2de4d776a0fdb99555687a96719d111ffb6460
ms.sourcegitcommit: 8bf8e9196c4ea89297f210b5c1d41b31f9edd407
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2020
ms.locfileid: "11156289"
---
# <span data-ttu-id="3b29f-103">连接到蓝牙和 USB-C 设备</span><span class="sxs-lookup"><span data-stu-id="3b29f-103">Connect to Bluetooth and USB-C devices</span></span>

> [!NOTE]
> <span data-ttu-id="3b29f-104">无法使用外置麦克风。</span><span class="sxs-lookup"><span data-stu-id="3b29f-104">External microphones cannot be used.</span></span> <span data-ttu-id="3b29f-105">HoloLens 2 使用内置 [麦克风阵列](hololens2-hardware.md#audio-and-speech)。</span><span class="sxs-lookup"><span data-stu-id="3b29f-105">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

## <span data-ttu-id="3b29f-106">配对蓝牙设备</span><span class="sxs-lookup"><span data-stu-id="3b29f-106">Pair Bluetooth devices</span></span>

<span data-ttu-id="3b29f-107">HoloLens 2 支持以下类别的蓝牙设备：</span><span class="sxs-lookup"><span data-stu-id="3b29f-107">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="3b29f-108">鼠标</span><span class="sxs-lookup"><span data-stu-id="3b29f-108">Mouse</span></span>
- <span data-ttu-id="3b29f-109">键盘</span><span class="sxs-lookup"><span data-stu-id="3b29f-109">Keyboard</span></span>
- <span data-ttu-id="3b29f-110">蓝牙音频输出 (A2DP) 设备</span><span class="sxs-lookup"><span data-stu-id="3b29f-110">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="3b29f-111">HoloLens（第 1 代）支持以下类别的蓝牙设备：</span><span class="sxs-lookup"><span data-stu-id="3b29f-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="3b29f-112">鼠标</span><span class="sxs-lookup"><span data-stu-id="3b29f-112">Mouse</span></span>
- <span data-ttu-id="3b29f-113">键盘</span><span class="sxs-lookup"><span data-stu-id="3b29f-113">Keyboard</span></span>
- <span data-ttu-id="3b29f-114">HoloLens（第 1 代）点击器</span><span class="sxs-lookup"><span data-stu-id="3b29f-114">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="3b29f-115">其他类型的蓝牙设备（例如，扬声器、耳机、智能手机和游戏板）可能会在 HoloLens 设置中列为可用。</span><span class="sxs-lookup"><span data-stu-id="3b29f-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="3b29f-116">但是，HoloLens（第 1 代）上不支持这些设备。</span><span class="sxs-lookup"><span data-stu-id="3b29f-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="3b29f-117">有关详细信息，请参阅 [HoloLens 设置将设备列为可用，但设备无法正常工作](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)。</span><span class="sxs-lookup"><span data-stu-id="3b29f-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="3b29f-118">配对蓝牙键盘或鼠标</span><span class="sxs-lookup"><span data-stu-id="3b29f-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="3b29f-119">打开键盘或鼠标，使其能够被检测到。</span><span class="sxs-lookup"><span data-stu-id="3b29f-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="3b29f-120">若要了解如何使设备可被检测到，请在设备（或其文档）中查找相关信息或访问制造商的网站。</span><span class="sxs-lookup"><span data-stu-id="3b29f-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="3b29f-121">使用开花手势（HoloLens [第 1 代]）或开始手势 (HoloLens 2) 转到“开始”\*\*\*\*，然后选择“设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b29f-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="3b29f-122">选择“设备”\*\*\*\*，并确保已启用蓝牙。</span><span class="sxs-lookup"><span data-stu-id="3b29f-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="3b29f-123">看到设备名称后，选择“配对”\*\*\*\*，然后按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="3b29f-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="3b29f-124">HoloLens（第 1 代）：配对点击器</span><span class="sxs-lookup"><span data-stu-id="3b29f-124">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="3b29f-125">使用开花手势转到“开始”\*\*\*\*，然后选择“设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b29f-125">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="3b29f-126">选择“设备”\*\*\*\*，并确保已启用蓝牙。</span><span class="sxs-lookup"><span data-stu-id="3b29f-126">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="3b29f-127">使用笔尖长按点击器配对按钮，直到点击器状态灯呈白色闪烁。</span><span class="sxs-lookup"><span data-stu-id="3b29f-127">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="3b29f-128">请确保按住该按钮直至指示灯开始闪烁。</span><span class="sxs-lookup"><span data-stu-id="3b29f-128">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="3b29f-129">配对按钮在点击器的底部，指环旁边。</span><span class="sxs-lookup"><span data-stu-id="3b29f-129">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>
   
   ![配对按钮在指环旁边](images/use-hololens-clicker-1.png)
   
1. <span data-ttu-id="3b29f-131">在配对屏幕上，选择“点击器\*\*\*\*” > “配对\*\*\*\*”。</span><span class="sxs-lookup"><span data-stu-id="3b29f-131">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="3b29f-132">禁用蓝牙</span><span class="sxs-lookup"><span data-stu-id="3b29f-132">Disable Bluetooth</span></span>

<span data-ttu-id="3b29f-133">此程序将关闭蓝牙无线电收发器的 RF 组件，并禁用 Microsoft HoloLens 上的所有蓝牙功能。</span><span class="sxs-lookup"><span data-stu-id="3b29f-133">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="3b29f-134">使用开花手势（HoloLens [第 1 代]）或开始手势 (HoloLens 2) 转到“开始”\*\*\*\*，然后选择“设置”\*\*\*\* > “设备”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b29f-134">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="3b29f-135">将“蓝牙”\*\*\*\* 的滑块开关移至“关闭”\*\*\*\* 位置。</span><span class="sxs-lookup"><span data-stu-id="3b29f-135">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <span data-ttu-id="3b29f-136">HoloLens 2：连接 USB-C 设备</span><span class="sxs-lookup"><span data-stu-id="3b29f-136">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="3b29f-137">HoloLens 2 支持以下类别的 USB-C 设备：</span><span class="sxs-lookup"><span data-stu-id="3b29f-137">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="3b29f-138">大容量存储设备（如 U 盘）</span><span class="sxs-lookup"><span data-stu-id="3b29f-138">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="3b29f-139">以太网适配器（包括以太网 + 充电）</span><span class="sxs-lookup"><span data-stu-id="3b29f-139">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="3b29f-140">USB-C 转 3.5 毫米数字音频适配器</span><span class="sxs-lookup"><span data-stu-id="3b29f-140">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="3b29f-141">USB-C 数字音频耳机（包括耳机适配器 + 充电）</span><span class="sxs-lookup"><span data-stu-id="3b29f-141">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="3b29f-142">有线鼠标</span><span class="sxs-lookup"><span data-stu-id="3b29f-142">Wired mouse</span></span>
- <span data-ttu-id="3b29f-143">有线键盘</span><span class="sxs-lookup"><span data-stu-id="3b29f-143">Wired keyboard</span></span>
- <span data-ttu-id="3b29f-144">组合 PD 集线器（USB A + PD 充电）</span><span class="sxs-lookup"><span data-stu-id="3b29f-144">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="3b29f-145">一些具有 USB-C 连接的移动设备会将自身作为以太网适配器呈现给 HoloLens，因此可在网络共享配置中使用（从 Windows Holographic 2004 版本开始）。</span><span class="sxs-lookup"><span data-stu-id="3b29f-145">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="3b29f-146">不支持需要单独的驱动程序和/或通过安装的应用程序进行配置的 USB LTE 调制解调器。</span><span class="sxs-lookup"><span data-stu-id="3b29f-146">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported.</span></span>

<span data-ttu-id="3b29f-147">为了回应客户的反馈，我们已通过 USB-C 为直接连接到 HoloLens 的蜂窝网络提供有限的支持。</span><span class="sxs-lookup"><span data-stu-id="3b29f-147">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span>  <span data-ttu-id="3b29f-148">连接的网络仅适用于支持通用 Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) 驱动程序实施的设备，且不需要安装任何其他驱动程序或应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b29f-148">Tethered connectivity only works for devices that support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver implementation and that don’t require any additional drivers or application installs.</span></span>  <span data-ttu-id="3b29f-149">连接后，此类设备将在 HoloLens 2 网络设置 UI 中自动显示为新的以太网连接。</span><span class="sxs-lookup"><span data-stu-id="3b29f-149">Such device, when connected, will automatically appear as a new Ethernet connection in the HoloLens 2 Network Settings UI.</span></span> <span data-ttu-id="3b29f-150">请联系设备的制造商，咨询其是否支持通用 Microsoft RNDIS 驱动程序的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="3b29f-150">Please consult your device’s manufacturer for further details on whether it supports the generic Microsoft RNDIS driver.</span></span>

## <span data-ttu-id="3b29f-151">连接到 Miracast</span><span class="sxs-lookup"><span data-stu-id="3b29f-151">Connect to Miracast</span></span>

<span data-ttu-id="3b29f-152">若要使用 Miracast，请按照下列步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="3b29f-152">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="3b29f-153">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="3b29f-153">Do one of the following:</span></span>  

   - <span data-ttu-id="3b29f-154">打开“开始”\*\*\*\* 菜单，然后选择显示图标。</span><span class="sxs-lookup"><span data-stu-id="3b29f-154">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="3b29f-155">盯着“开始”\*\*\*\* 菜单说“连接”。</span><span class="sxs-lookup"><span data-stu-id="3b29f-155">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="3b29f-156">在所显示设备的列表中，选择一个可用的设备。</span><span class="sxs-lookup"><span data-stu-id="3b29f-156">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="3b29f-157">完成配对，开始进行投影。</span><span class="sxs-lookup"><span data-stu-id="3b29f-157">Complete the pairing to begin projecting.</span></span>
