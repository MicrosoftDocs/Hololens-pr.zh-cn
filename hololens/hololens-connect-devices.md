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
ms.openlocfilehash: 5fed56d7a0beeda0a0d96eddc63aaee872f3e52d
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639091"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a><span data-ttu-id="f454b-103">连接到蓝牙和 USB-C 设备</span><span class="sxs-lookup"><span data-stu-id="f454b-103">Connect to Bluetooth and USB-C devices</span></span>

## <a name="pair-bluetooth-devices"></a><span data-ttu-id="f454b-104">配对蓝牙设备</span><span class="sxs-lookup"><span data-stu-id="f454b-104">Pair Bluetooth devices</span></span>

<span data-ttu-id="f454b-105">HoloLens 2 支持以下类别的蓝牙设备：</span><span class="sxs-lookup"><span data-stu-id="f454b-105">HoloLens 2 supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="f454b-106">[HID](/windows-hardware/drivers/hid/)：</span><span class="sxs-lookup"><span data-stu-id="f454b-106">[HID](/windows-hardware/drivers/hid/):</span></span>
    - <span data-ttu-id="f454b-107">鼠标</span><span class="sxs-lookup"><span data-stu-id="f454b-107">Mouse</span></span>
    - <span data-ttu-id="f454b-108">Keyboard</span><span class="sxs-lookup"><span data-stu-id="f454b-108">Keyboard</span></span>
- <span data-ttu-id="f454b-109">音频输出 (A2DP) 设备</span><span class="sxs-lookup"><span data-stu-id="f454b-109">Audio output (A2DP) devices</span></span>

<span data-ttu-id="f454b-110">HoloLens 2 支持以下蓝牙 API：</span><span class="sxs-lookup"><span data-stu-id="f454b-110">HoloLens 2 supports the following Bluetooth APIs:</span></span>
- <span data-ttu-id="f454b-111">GATT [服务器](/windows/uwp/devices-sensors/gatt-server)和[客户端](/windows/uwp/devices-sensors/gatt-client)</span><span class="sxs-lookup"><span data-stu-id="f454b-111">GATT [Server](/windows/uwp/devices-sensors/gatt-server) and [Client](/windows/uwp/devices-sensors/gatt-client)</span></span>
- [<span data-ttu-id="f454b-112">RFCOMM</span><span class="sxs-lookup"><span data-stu-id="f454b-112">RFCOMM</span></span>](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> <span data-ttu-id="f454b-113">你可能必须从 Microsoft Store 安装相应的伴侣应用才能实际使用 HID 和 GATT 设备。</span><span class="sxs-lookup"><span data-stu-id="f454b-113">You may have to install corresponding companion apps from Microsoft Store to actually use the HID and GATT devices.</span></span>

<span data-ttu-id="f454b-114">HoloLens（第 1 代）支持以下类别的蓝牙设备：</span><span class="sxs-lookup"><span data-stu-id="f454b-114">HoloLens (1st gen) supports the following classes of Bluetooth devices:</span></span>

- <span data-ttu-id="f454b-115">鼠标</span><span class="sxs-lookup"><span data-stu-id="f454b-115">Mouse</span></span>
- <span data-ttu-id="f454b-116">Keyboard</span><span class="sxs-lookup"><span data-stu-id="f454b-116">Keyboard</span></span>
- [<span data-ttu-id="f454b-117">HoloLens（第 1 代）点击器</span><span class="sxs-lookup"><span data-stu-id="f454b-117">HoloLens (1st gen) clicker</span></span>](hololens1-clicker.md)

> [!NOTE]
> <span data-ttu-id="f454b-118">其他类型的蓝牙设备（例如，扬声器、耳机、智能手机和游戏板）可能会在 HoloLens 设置中列为可用。</span><span class="sxs-lookup"><span data-stu-id="f454b-118">Other types of Bluetooth devices, such as speakers, headsets, smartphones, and game pads, may be listed as available in HoloLens settings.</span></span> <span data-ttu-id="f454b-119">但是，HoloLens（第 1 代）上不支持这些设备。</span><span class="sxs-lookup"><span data-stu-id="f454b-119">However, these devices aren't supported on HoloLens (1st gen).</span></span> <span data-ttu-id="f454b-120">有关详细信息，请参阅 [HoloLens 设置将设备列为可用，但设备无法使用](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)。</span><span class="sxs-lookup"><span data-stu-id="f454b-120">For more information, see [HoloLens Settings lists devices as available, but the devices don't work](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work).</span></span>

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a><span data-ttu-id="f454b-121">配对蓝牙键盘或鼠标</span><span class="sxs-lookup"><span data-stu-id="f454b-121">Pair a Bluetooth keyboard or mouse</span></span>

1. <span data-ttu-id="f454b-122">打开键盘或鼠标，使其能够被检测到。</span><span class="sxs-lookup"><span data-stu-id="f454b-122">Turn on your keyboard or mouse, and make it discoverable.</span></span> <span data-ttu-id="f454b-123">若要了解如何使设备可被检测到，请在设备（或其文档）中查找相关信息或访问制造商的网站。</span><span class="sxs-lookup"><span data-stu-id="f454b-123">To learn how to make the device discoverable, look for information on the device (or its documentation) or visit the manufacturer's website.</span></span>

1. <span data-ttu-id="f454b-124">使用开花手势（HoloLens [第 1 代]）或开始手势 (HoloLens 2) 转到“开始”，然后选择“设置”。</span><span class="sxs-lookup"><span data-stu-id="f454b-124">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings**.</span></span>

1. <span data-ttu-id="f454b-125">选择“设备”，并确保已启用蓝牙。</span><span class="sxs-lookup"><span data-stu-id="f454b-125">Select **Devices**, and make sure that Bluetooth is on.</span></span>  

1. <span data-ttu-id="f454b-126">看到设备名称后，选择“配对”，然后按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="f454b-126">When you see the device name, select **Pair**, and then follow the instructions.</span></span>

## <a name="disable-bluetooth"></a><span data-ttu-id="f454b-127">禁用蓝牙</span><span class="sxs-lookup"><span data-stu-id="f454b-127">Disable Bluetooth</span></span>

<span data-ttu-id="f454b-128">此程序将关闭蓝牙无线电收发器的 RF 组件，并禁用 Microsoft HoloLens 上的所有蓝牙功能。</span><span class="sxs-lookup"><span data-stu-id="f454b-128">This procedure turns off the RF components of the Bluetooth radio and disables all Bluetooth functionality on Microsoft HoloLens.</span></span>

1. <span data-ttu-id="f454b-129">使用开花手势（HoloLens [第 1 代]）或开始手势 (HoloLens 2) 转到“开始”，然后选择“设置” > “设备”。</span><span class="sxs-lookup"><span data-stu-id="f454b-129">Use the bloom gesture (HoloLens (1st gen)) or the start gesture (HoloLens 2) to go to **Start**, and then select **Settings** > **Devices**.</span></span>

1. <span data-ttu-id="f454b-130">将“蓝牙”的滑块开关移至“关闭”位置。</span><span class="sxs-lookup"><span data-stu-id="f454b-130">Move the slider switch for **Bluetooth** to the **Off** position.</span></span>

## <a name="hololens-2-connect-usb-c-devices"></a><span data-ttu-id="f454b-131">HoloLens 2：连接 USB-C 设备</span><span class="sxs-lookup"><span data-stu-id="f454b-131">HoloLens 2: Connect USB-C devices</span></span>

<span data-ttu-id="f454b-132">HoloLens 2 支持以下类别的 USB-C 设备：</span><span class="sxs-lookup"><span data-stu-id="f454b-132">HoloLens 2 supports the following classes of USB-C devices:</span></span>

- <span data-ttu-id="f454b-133">大容量存储设备（如 U 盘）</span><span class="sxs-lookup"><span data-stu-id="f454b-133">Mass storage devices (such as thumb drives)</span></span>
- <span data-ttu-id="f454b-134">以太网适配器（包括以太网 + 充电）</span><span class="sxs-lookup"><span data-stu-id="f454b-134">Ethernet adapters (including ethernet plus charging)</span></span>
- <span data-ttu-id="f454b-135">USB-C 转 3.5 毫米数字音频适配器</span><span class="sxs-lookup"><span data-stu-id="f454b-135">USB-C-to-3.5mm digital audio adapters</span></span>
- <span data-ttu-id="f454b-136">USB-C 数字音频耳机（包括耳机适配器 + 充电）</span><span class="sxs-lookup"><span data-stu-id="f454b-136">USB-C digital audio headsets (including headset adapters plus charging)</span></span>
- <span data-ttu-id="f454b-137">USB-C 外置麦克风（[Windows 全息版 21H1](hololens-release-notes.md#windows-holographic-version-21h1) 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="f454b-137">USB-C External Microphones ([Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher)</span></span>
- <span data-ttu-id="f454b-138">有线鼠标</span><span class="sxs-lookup"><span data-stu-id="f454b-138">Wired mouse</span></span>
- <span data-ttu-id="f454b-139">有线键盘</span><span class="sxs-lookup"><span data-stu-id="f454b-139">Wired keyboard</span></span>
- <span data-ttu-id="f454b-140">组合 PD 集线器（USB A + PD 充电）</span><span class="sxs-lookup"><span data-stu-id="f454b-140">Combination PD hubs (USB A plus PD charging)</span></span>


> [!NOTE]
> <span data-ttu-id="f454b-141">为了回应客户的反馈，我们已通过 USB-C 向直接连接到 HoloLens 的手机网络连接提供有限的支持。</span><span class="sxs-lookup"><span data-stu-id="f454b-141">In response to customer feedback, we have enabled limited support for cellular connectivity tethered directly to the HoloLens via USB-C.</span></span> <span data-ttu-id="f454b-142">有关详细信息，请参阅[连接到手机网络和 5G](hololens-cellular.md)。</span><span class="sxs-lookup"><span data-stu-id="f454b-142">See [Connect to Cellular and 5G](hololens-cellular.md) for more information.</span></span>

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="f454b-143">USB-C 外置麦克风支持</span><span class="sxs-lookup"><span data-stu-id="f454b-143">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f454b-144">插入 **USB 麦克风不会自动将其设置为输入设备**。</span><span class="sxs-lookup"><span data-stu-id="f454b-144">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="f454b-145">当插入一组 USB-C 耳机时，用户会看到耳机音频将自动重定向到耳机，但 HoloLens OS 会将内置麦克风阵列的优先级优于任何其他输入设备。</span><span class="sxs-lookup"><span data-stu-id="f454b-145">When plugging in a set of USB-C headphones, users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> <span data-ttu-id="f454b-146">若要使用 USB-C 麦克风，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="f454b-146">**In order to use a USB-C microphone follow the steps below.**</span></span>

> [!NOTE]
> <span data-ttu-id="f454b-147">在 [Windows 全息版 21H1](hololens-release-notes.md#windows-holographic-version-21h1) 及更高版本之前的内部版本中，不能使用外置麦克风。</span><span class="sxs-lookup"><span data-stu-id="f454b-147">External microphones cannot be used in builds prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) and higher.</span></span> 

<span data-ttu-id="f454b-148">用户可以使用“声音”设置面板选择 USB-C 连接的外置麦克风。</span><span class="sxs-lookup"><span data-stu-id="f454b-148">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="f454b-149">USB-C 麦克风可用于呼叫、录制等。</span><span class="sxs-lookup"><span data-stu-id="f454b-149">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="f454b-150">打开“设置”应用并选择“系统” > “声音”。</span><span class="sxs-lookup"><span data-stu-id="f454b-150">Open the **Settings** app and select **System** > **Sound**.</span></span>

![声音设置](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="f454b-152">若要将外置麦克风用于 Remote Assist，用户需要单击“管理声音设备”超链接。</span><span class="sxs-lookup"><span data-stu-id="f454b-152">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="f454b-153">然后，使用下拉菜单将外置麦克风设置为“默认值”或“通信默认值”。</span><span class="sxs-lookup"><span data-stu-id="f454b-153">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="f454b-154">选择“默认值”表示将在任何位置使用外置麦克风。</span><span class="sxs-lookup"><span data-stu-id="f454b-154">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="f454b-155">选择“通信默认值”表示将在 Remote Assist 和其他通信应用中使用外置麦克风，但 HoloLens 麦克风阵列仍可用于其他任务。</span><span class="sxs-lookup"><span data-stu-id="f454b-155">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![管理声音设备](images/usbc-mic-2.png)

<br>

![设置麦克风默认值](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="f454b-158">蓝牙麦克风支持怎么样？</span><span class="sxs-lookup"><span data-stu-id="f454b-158">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="f454b-159">遗憾的是，HoloLens 2 目前仍不支持蓝牙麦克风。</span><span class="sxs-lookup"><span data-stu-id="f454b-159">Unfortunately, Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

### <a name="usb-c-hubs"></a><span data-ttu-id="f454b-160">USB-C 集线器</span><span class="sxs-lookup"><span data-stu-id="f454b-160">USB-C Hubs</span></span>

<span data-ttu-id="f454b-161">某些用户可能需要一次连接多个设备。</span><span class="sxs-lookup"><span data-stu-id="f454b-161">Some users may need to connect multiple devices at once.</span></span> <span data-ttu-id="f454b-162">对于想要将 [USB-C 麦克风](#usb-c-external-microphone-support)与其他已连接设备一起使用的用户，USB-C 集线器可能满足客户的需求。</span><span class="sxs-lookup"><span data-stu-id="f454b-162">For users who would like to use a [USB-C microphone](#usb-c-external-microphone-support) along with another connected device, USB-C hubs may fit the customer's need.</span></span> <span data-ttu-id="f454b-163">Microsoft 尚未测试这些设备，我们也不能推荐任何特定品牌。</span><span class="sxs-lookup"><span data-stu-id="f454b-163">Microsoft has not tested these devices, nor can we recommend any specific brands.</span></span>

<span data-ttu-id="f454b-164">USB-C 集线器和已连接设备的要求：</span><span class="sxs-lookup"><span data-stu-id="f454b-164">**Requirements for USB-C hub and connected devices:**</span></span>

- <span data-ttu-id="f454b-165">连接的设备不得要求安装驱动程序。</span><span class="sxs-lookup"><span data-stu-id="f454b-165">Connected devices must not require a driver to be installed.</span></span>
- <span data-ttu-id="f454b-166">所有已连接设备的总功耗必须低于 4.5 瓦。</span><span class="sxs-lookup"><span data-stu-id="f454b-166">The total power draw of all connected devices must be below 4.5 Watts.</span></span>

## <a name="connect-to-miracast"></a><span data-ttu-id="f454b-167">连接到 Miracast</span><span class="sxs-lookup"><span data-stu-id="f454b-167">Connect to Miracast</span></span>

<span data-ttu-id="f454b-168">若要使用 Miracast，请按照下列步骤进行操作：</span><span class="sxs-lookup"><span data-stu-id="f454b-168">To use Miracast, follow these steps:</span></span>

1. <span data-ttu-id="f454b-169">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f454b-169">Do one of the following:</span></span>  

   - <span data-ttu-id="f454b-170">打开“开始”菜单，然后选择“显示”图标。</span><span class="sxs-lookup"><span data-stu-id="f454b-170">Open the **Start** menu, and select the **Display** icon.</span></span>
   - <span data-ttu-id="f454b-171">盯着“开始”菜单说“连接”。</span><span class="sxs-lookup"><span data-stu-id="f454b-171">Say "Connect" while you gaze at the **Start** menu.</span></span>  

1. <span data-ttu-id="f454b-172">在所显示设备的列表中，选择一个可用的设备。</span><span class="sxs-lookup"><span data-stu-id="f454b-172">On the list of devices that appears, select an available device.</span></span>

1. <span data-ttu-id="f454b-173">完成配对，开始进行投影。</span><span class="sxs-lookup"><span data-stu-id="f454b-173">Complete the pairing to begin projecting.</span></span>
