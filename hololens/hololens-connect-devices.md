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
ms.openlocfilehash: 53d426b4319dafd0dd976e67111992020507f719
ms.sourcegitcommit: 563797405f7470f979a27718c604df920efbb368
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881242"
---
# <span data-ttu-id="9db39-103">连接到蓝牙和 USB-C 设备</span><span class="sxs-lookup"><span data-stu-id="9db39-103">Connect to Bluetooth and USB-C devices</span></span>

## <span data-ttu-id="9db39-104">配对蓝牙设备</span><span class="sxs-lookup"><span data-stu-id="9db39-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="9db39-105">HoloLens 2 支持以下类别的蓝牙设备：</span><span class="sxs-lookup"><span data-stu-id="9db39-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="9db39-106">鼠标</span><span class="sxs-lookup"><span data-stu-id="9db39-106">Mouse</span></span>
- <span data-ttu-id="9db39-107">键盘</span><span class="sxs-lookup"><span data-stu-id="9db39-107">Keyboard</span></span>
- <span data-ttu-id="9db39-108">蓝牙音频输出 (A2DP) 设备</span><span class="sxs-lookup"><span data-stu-id="9db39-108">Bluetooth audio output (A2DP) devices</span></span>

> [!NOTE]
> <span data-ttu-id="9db39-109">无法使用外置麦克风。</span><span class="sxs-lookup"><span data-stu-id="9db39-109">External microphones cannot be used.</span></span> <span data-ttu-id="9db39-110">HoloLens 2 使用内置 [麦克风阵列](hololens2-hardware.md#audio-and-speech)。</span><span class="sxs-lookup"><span data-stu-id="9db39-110">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

<span data-ttu-id="9db39-111">HoloLens（第 1 代）支持以下类别的蓝牙设备：</span><span class="sxs-lookup"><span data-stu-id="9db39-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="9db39-112">鼠标</span><span class="sxs-lookup"><span data-stu-id="9db39-112">Mouse</span></span>
- <span data-ttu-id="9db39-113">键盘</span><span class="sxs-lookup"><span data-stu-id="9db39-113">Keyboard</span></span>
- <span data-ttu-id="9db39-114">HoloLens（第 1 代）点击器</span><span class="sxs-lookup"><span data-stu-id="9db39-114">HoloLens (1st gen) clicker</span></span>

> [!NOTE]
> <span data-ttu-id="9db39-115">其他类型的蓝牙设备（例如，扬声器、耳机、智能手机和游戏板）可能会在 HoloLens 设置中列为可用。</span><span class="sxs-lookup"><span data-stu-id="9db39-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="9db39-116">但是，HoloLens（第 1 代）上不支持这些设备。</span><span class="sxs-lookup"><span data-stu-id="9db39-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="9db39-117">有关详细信息，请参阅 [HoloLens 设置将设备列为可用，但设备无法正常工作](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)。</span><span class="sxs-lookup"><span data-stu-id="9db39-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <span data-ttu-id="9db39-118">配对蓝牙键盘或鼠标</span><span class="sxs-lookup"><span data-stu-id="9db39-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="9db39-119">打开键盘或鼠标，使其能够被检测到。</span><span class="sxs-lookup"><span data-stu-id="9db39-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="9db39-120">若要了解如何使设备可被检测到，请在设备（或其文档）中查找相关信息或访问制造商的网站。</span><span class="sxs-lookup"><span data-stu-id="9db39-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="9db39-121">使用开花手势（HoloLens [第 1 代]）或开始手势 (HoloLens 2) 转到“开始”\*\*\*\*，然后选择“设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9db39-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="9db39-122">选择“设备”\*\*\*\*，并确保已启用蓝牙。</span><span class="sxs-lookup"><span data-stu-id="9db39-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="9db39-123">看到设备名称后，选择“配对”\*\*\*\*，然后按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="9db39-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

### <span data-ttu-id="9db39-124">HoloLens（第 1 代）：配对点击器</span><span class="sxs-lookup"><span data-stu-id="9db39-124">HoloLens (1st gen): Pair the clicker</span></span>

1. <span data-ttu-id="9db39-125">使用开花手势转到“开始”\*\*\*\*，然后选择“设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9db39-125">Use the bloom gesture to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="9db39-126">选择“设备”\*\*\*\*，并确保已启用蓝牙。</span><span class="sxs-lookup"><span data-stu-id="9db39-126">Select **Devices**, and make sure that Bluetooth is on.</span></span>

1. <span data-ttu-id="9db39-127">使用笔尖长按点击器配对按钮，直到点击器状态灯呈白色闪烁。</span><span class="sxs-lookup"><span data-stu-id="9db39-127">Use the tip of a pen to press and hold the clicker pairing button until the clicker status light blinks white.</span></span> <span data-ttu-id="9db39-128">请确保按住该按钮直至指示灯开始闪烁。</span><span class="sxs-lookup"><span data-stu-id="9db39-128">Make sure to hold down the button until the light starts blinking.</span></span>  

   <span data-ttu-id="9db39-129">配对按钮在点击器的底部，指环旁边。</span><span class="sxs-lookup"><span data-stu-id="9db39-129">The pairing button is on the underside of the clicker, next to the finger loop.</span></span>
   
   ![配对按钮在指环旁边](images/use-hololens-clicker-1.png)
   
1. <span data-ttu-id="9db39-131">在配对屏幕上，选择“点击器\*\*\*\*” > “配对\*\*\*\*”。</span><span class="sxs-lookup"><span data-stu-id="9db39-131">On the pairing screen, select **Clicker** > **Pair**.</span></span>

## <span data-ttu-id="9db39-132">HoloLens 2：连接 USB-C 设备</span><span class="sxs-lookup"><span data-stu-id="9db39-132">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="9db39-133">HoloLens 2 支持以下类别的 USB-C 设备：</span><span class="sxs-lookup"><span data-stu-id="9db39-133">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="9db39-134">大容量存储设备（如 U 盘）</span><span class="sxs-lookup"><span data-stu-id="9db39-134">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="9db39-135">以太网适配器（包括以太网 + 充电）</span><span class="sxs-lookup"><span data-stu-id="9db39-135">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="9db39-136">USB-C 转 3.5 毫米数字音频适配器</span><span class="sxs-lookup"><span data-stu-id="9db39-136">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="9db39-137">USB-C 数字音频耳机（包括耳机适配器 + 充电）</span><span class="sxs-lookup"><span data-stu-id="9db39-137">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="9db39-138">有线鼠标</span><span class="sxs-lookup"><span data-stu-id="9db39-138">Wired mouse</span></span>
- <span data-ttu-id="9db39-139">有线键盘</span><span class="sxs-lookup"><span data-stu-id="9db39-139">Wired keyboard</span></span>
- <span data-ttu-id="9db39-140">组合 PD 集线器（USB A + PD 充电）</span><span class="sxs-lookup"><span data-stu-id="9db39-140">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="9db39-141">一些具有 USB-C 连接的移动设备会将自身作为以太网适配器呈现给 HoloLens，因此可在网络共享配置中使用（从 Windows Holographic 2004 版本开始）。</span><span class="sxs-lookup"><span data-stu-id="9db39-141">Some mobile devices with USB-C connections present themselves to the HoloLens as ethernet adaptors, and therefore could be used in a tethering configuration, starting with Windows Holographic, version 2004.</span></span> <span data-ttu-id="9db39-142">不支持需要单独的驱动程序和/或通过安装的应用程序进行配置的 USB LTE 调制解调器。</span><span class="sxs-lookup"><span data-stu-id="9db39-142">USB LTE modems that require a separate driver, and/or application installed for configuration are not supported.</span></span>

## <span data-ttu-id="9db39-143">连接到 Miracast</span><span class="sxs-lookup"><span data-stu-id="9db39-143">Connect to Miracast</span></span>

<span data-ttu-id="9db39-144">若要使用 Miracast，请按照下列步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="9db39-144">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="9db39-145">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="9db39-145">Do one of the following:</span></span>  

   - <span data-ttu-id="9db39-146">打开“开始”\*\*\*\* 菜单，然后选择显示图标。</span><span class="sxs-lookup"><span data-stu-id="9db39-146">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="9db39-147">盯着“开始”\*\*\*\* 菜单说“连接”。</span><span class="sxs-lookup"><span data-stu-id="9db39-147">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="9db39-148">在所显示设备的列表中，选择一个可用的设备。</span><span class="sxs-lookup"><span data-stu-id="9db39-148">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="9db39-149">完成配对，开始进行投影。</span><span class="sxs-lookup"><span data-stu-id="9db39-149">Complete the pairing to begin projecting.</span></span>

## <span data-ttu-id="9db39-150">禁用蓝牙</span><span class="sxs-lookup"><span data-stu-id="9db39-150">Disable Bluetooth</span></span>

<span data-ttu-id="9db39-151">此程序将关闭蓝牙无线电收发器的 RF 组件，并禁用 Microsoft HoloLens 上的所有蓝牙功能。</span><span class="sxs-lookup"><span data-stu-id="9db39-151">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="9db39-152">使用开花手势（HoloLens [第 1 代]）或开始手势 (HoloLens 2) 转到“开始”\*\*\*\*，然后选择“设置”\*\*\*\* > “设备”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9db39-152">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="9db39-153">将“蓝牙”\*\*\*\* 的滑块开关移至“关闭”\*\*\*\* 位置。</span><span class="sxs-lookup"><span data-stu-id="9db39-153">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>
