---
title: 连接到蓝牙和 USB-C 设备
description: 开始从 HoloLens 混合现实设备连接到蓝牙和 USB-C 设备及附件。
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
ms.openlocfilehash: 728bf8547315be96f879ff94a1290c1e2b3e7bf8
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385485"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="bd45b-103">连接到蓝牙和 USB-C 设备</span><span class="sxs-lookup"><span data-stu-id="bd45b-103">Connect to Bluetooth and USB-C devices</span></span>

> [!NOTE]
> <span data-ttu-id="bd45b-104">无法使用外置麦克风。</span><span class="sxs-lookup"><span data-stu-id="bd45b-104">External microphones cannot be used.</span></span> <span data-ttu-id="bd45b-105">HoloLens 2 使用内置 [麦克风阵列](hololens2-hardware.md#audio-and-speech)。</span><span class="sxs-lookup"><span data-stu-id="bd45b-105">HoloLens 2 uses its built-in [microphone array](hololens2-hardware.md#audio-and-speech).</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="bd45b-106">配对蓝牙设备</span><span class="sxs-lookup"><span data-stu-id="bd45b-106">Pair Bluetooth devices</span></span>

<span data-ttu-id="bd45b-107">HoloLens 2 支持以下类别的蓝牙设备：</span><span class="sxs-lookup"><span data-stu-id="bd45b-107">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="bd45b-108">鼠标</span><span class="sxs-lookup"><span data-stu-id="bd45b-108">Mouse</span></span>
- <span data-ttu-id="bd45b-109">键盘</span><span class="sxs-lookup"><span data-stu-id="bd45b-109">Keyboard</span></span>
- <span data-ttu-id="bd45b-110">蓝牙音频输出 (A2DP) 设备</span><span class="sxs-lookup"><span data-stu-id="bd45b-110">Bluetooth audio output (A2DP) devices</span></span>

<span data-ttu-id="bd45b-111">HoloLens（第 1 代）支持以下类别的蓝牙设备：</span><span class="sxs-lookup"><span data-stu-id="bd45b-111">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="bd45b-112">鼠标</span><span class="sxs-lookup"><span data-stu-id="bd45b-112">Mouse</span></span>
- <span data-ttu-id="bd45b-113">键盘</span><span class="sxs-lookup"><span data-stu-id="bd45b-113">Keyboard</span></span>
- [<span data-ttu-id="bd45b-114">HoloLens（第 1 代）点击器</span><span class="sxs-lookup"><span data-stu-id="bd45b-114">HoloLens (1st gen) clicker</span></span>](https://docs.microsoft.com/hololens/hololens1-clicker)

> [!NOTE]
> <span data-ttu-id="bd45b-115">其他类型的蓝牙设备（例如，扬声器、耳机、智能手机和游戏板）可能会在 HoloLens 设置中列为可用。</span><span class="sxs-lookup"><span data-stu-id="bd45b-115">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="bd45b-116">但是，HoloLens（第 1 代）上不支持这些设备。</span><span class="sxs-lookup"><span data-stu-id="bd45b-116">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="bd45b-117">有关详细信息，请参阅 [HoloLens 设置将设备列为可用，但设备无法正常工作](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)。</span><span class="sxs-lookup"><span data-stu-id="bd45b-117">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="bd45b-118">配对蓝牙键盘或鼠标</span><span class="sxs-lookup"><span data-stu-id="bd45b-118">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="bd45b-119">打开键盘或鼠标，使其能够被检测到。</span><span class="sxs-lookup"><span data-stu-id="bd45b-119">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="bd45b-120">若要了解如何使设备可被检测到，请在设备（或其文档）中查找相关信息或访问制造商的网站。</span><span class="sxs-lookup"><span data-stu-id="bd45b-120">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="bd45b-121">使用开花手势（HoloLens [第 1 代]）或开始手势 (HoloLens 2) 转到“开始”\*\*\*\*，然后选择“设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bd45b-121">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="bd45b-122">选择“设备”\*\*\*\*，并确保已启用蓝牙。</span><span class="sxs-lookup"><span data-stu-id="bd45b-122">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="bd45b-123">看到设备名称后，选择“**配对**”，然后按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="bd45b-123">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="bd45b-124">禁用蓝牙</span><span class="sxs-lookup"><span data-stu-id="bd45b-124">Disable Bluetooth</span></span>

<span data-ttu-id="bd45b-125">此程序将关闭蓝牙无线电收发器的 RF 组件，并禁用 Microsoft HoloLens 上的所有蓝牙功能。</span><span class="sxs-lookup"><span data-stu-id="bd45b-125">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="bd45b-126">使用开花手势（HoloLens [第 1 代]）或开始手势 (HoloLens 2) 转到“开始”\*\*\*\*，然后选择“设置”\*\*\*\* > “设备”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bd45b-126">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="bd45b-127">将“蓝牙”\*\*\*\* 的滑块开关移至“关闭”\*\*\*\* 位置。</span><span class="sxs-lookup"><span data-stu-id="bd45b-127">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="bd45b-128">HoloLens 2：连接 USB-C 设备</span><span class="sxs-lookup"><span data-stu-id="bd45b-128">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="bd45b-129">HoloLens 2 支持以下类别的 USB-C 设备：</span><span class="sxs-lookup"><span data-stu-id="bd45b-129">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="bd45b-130">大容量存储设备（如 U 盘）</span><span class="sxs-lookup"><span data-stu-id="bd45b-130">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="bd45b-131">以太网适配器（包括以太网 + 充电）</span><span class="sxs-lookup"><span data-stu-id="bd45b-131">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="bd45b-132">USB-C 转 3.5 毫米数字音频适配器</span><span class="sxs-lookup"><span data-stu-id="bd45b-132">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="bd45b-133">USB-C 数字音频耳机（包括耳机适配器 + 充电）</span><span class="sxs-lookup"><span data-stu-id="bd45b-133">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="bd45b-134">有线鼠标</span><span class="sxs-lookup"><span data-stu-id="bd45b-134">Wired mouse</span></span>
- <span data-ttu-id="bd45b-135">有线键盘</span><span class="sxs-lookup"><span data-stu-id="bd45b-135">Wired keyboard</span></span>
- <span data-ttu-id="bd45b-136">组合 PD 集线器（USB A + PD 充电）</span><span class="sxs-lookup"><span data-stu-id="bd45b-136">Combination PD hubs (USB A plus PD charging)</span></span>

> [!NOTE]
> <span data-ttu-id="bd45b-137">为了回应客户的反馈，我们已通过 USB-C 向直接连接到 HoloLens 的手机网络连接提供有限的支持。</span><span class="sxs-lookup"><span data-stu-id="bd45b-137">In response to customer feedback we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="bd45b-138">有关详细信息，请参阅 [连接到手机网络和 5G](hololens-cellular.md)。</span><span class="sxs-lookup"><span data-stu-id="bd45b-138">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="bd45b-139">USB-C 集线器</span><span class="sxs-lookup"><span data-stu-id="bd45b-139">USB-C Hubs</span></span>

<span data-ttu-id="bd45b-140">某些用户可能需要一次连接多个设备。</span><span class="sxs-lookup"><span data-stu-id="bd45b-140">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="bd45b-141">对于想要预览体验成员功能和与其他已连接设备一起 [使用 USB-C 麦克风](hololens-insider.md#usb-c-external-microphone-support) 的用户，USB-C 集线器可能满足其需求。</span><span class="sxs-lookup"><span data-stu-id="bd45b-141">For users who would like to preview an Insider feature and [use a USB-C microphone](hololens-insider.md#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="bd45b-142">Microsoft 尚未测试这些设备，我们也不能推荐任何特定品牌。</span><span class="sxs-lookup"><span data-stu-id="bd45b-142">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

**<span data-ttu-id="bd45b-143">USB-C 集线器和已连接设备的要求：</span><span class="sxs-lookup"><span data-stu-id="bd45b-143">Requirements for USB-C hub and connected devices:</span></span>**

- <span data-ttu-id="bd45b-144">连接的设备不得要求安装驱动程序。</span><span class="sxs-lookup"><span data-stu-id="bd45b-144">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="bd45b-145">所有已连接设备的总功耗必须低于 4.5 瓦。</span><span class="sxs-lookup"><span data-stu-id="bd45b-145">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="bd45b-146">连接到 Miracast</span><span class="sxs-lookup"><span data-stu-id="bd45b-146">Connect to Miracast</span></span>

<span data-ttu-id="bd45b-147">若要使用 Miracast，请按照下列步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="bd45b-147">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="bd45b-148">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="bd45b-148">Do one of the following:</span></span>  

   - <span data-ttu-id="bd45b-149">打开“开始”\*\*\*\* 菜单，然后选择显示图标。</span><span class="sxs-lookup"><span data-stu-id="bd45b-149">Open the **Start** menu, and select the display icon.</span></span>
   - <span data-ttu-id="bd45b-150">盯着“开始”\*\*\*\* 菜单说“连接”。</span><span class="sxs-lookup"><span data-stu-id="bd45b-150">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="bd45b-151">在所显示设备的列表中，选择一个可用的设备。</span><span class="sxs-lookup"><span data-stu-id="bd45b-151">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="bd45b-152">完成配对，开始进行投影。</span><span class="sxs-lookup"><span data-stu-id="bd45b-152">Complete the pairing to begin projecting.</span></span>
