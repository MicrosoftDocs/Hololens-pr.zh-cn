---
title: 重启、重置或恢复 HoloLens
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: 如何使用 Advanced Recovery Companion 将映像刷写到 HoloLens 2。
keywords: 操作方法, 重启, 重置, 恢复, 硬重置, 软重置, 电源周期, HoloLens, 关机, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
ms.openlocfilehash: ad162d1f415430e22e683280089cacf2e1cef02a
ms.sourcegitcommit: 3827d244426ffecb517f6cfa714eeef9363c062d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2021
ms.locfileid: "11253578"
---
# <span data-ttu-id="003d5-104">重启、重置或恢复 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="003d5-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="003d5-105">给设备充电</span><span class="sxs-lookup"><span data-stu-id="003d5-105">Charge the device</span></span>

<span data-ttu-id="003d5-106">在开始任何故障排除过程之前，请确保将设备充电至电池容量的 20 % 至 40%。</span><span class="sxs-lookup"><span data-stu-id="003d5-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="003d5-107">请使用 HoloLens 2 设备附带的充电器和 USB Type-C 电缆。</span><span class="sxs-lookup"><span data-stu-id="003d5-107">Use the charger and the USB Type-C cables that come with the HoloLens 2 device.</span></span> <span data-ttu-id="003d5-108">设备附带的电源和 USB-C 到 C 线缆是向 HoloLens 2 充电的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="003d5-108">The power supply and USB-C-to-C cable that come with the device are the best way to charge your HoloLens 2.</span></span> <span data-ttu-id="003d5-109">充电器提供 18W 的电力（9V，2A）。</span><span class="sxs-lookup"><span data-stu-id="003d5-109">The charger supplies 18W of power (9V at 2A).</span></span> <span data-ttu-id="003d5-110">借助提供的壁式充电器，HoloLens 2 设备可在待机状态下在 65 分钟内将电池充满电。</span><span class="sxs-lookup"><span data-stu-id="003d5-110">Using the wall charger supplied, HoloLens 2 devices can charge the battery to full in less than 65 minutes when the device is in standby.</span></span> <span data-ttu-id="003d5-111">如果这些附件不可用，请确保可用的充电器支持至少 15W 的功率。</span><span class="sxs-lookup"><span data-stu-id="003d5-111">If those accessories aren't available, make sure the charger that's available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="003d5-112">如果可能，请避免使用电脑通过 USB 给设备充电（速度很慢）。</span><span class="sxs-lookup"><span data-stu-id="003d5-112">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="003d5-113">如果设备已正确启动且运行，有三种方法可以检查电池电量：</span><span class="sxs-lookup"><span data-stu-id="003d5-113">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="003d5-114">从 HoloLens 设备 UI 的主菜单。</span><span class="sxs-lookup"><span data-stu-id="003d5-114">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="003d5-115">查看靠近电源按钮的 LED（对于 40% 的电量，应该可看到至少两个稳定的 LED）。</span><span class="sxs-lookup"><span data-stu-id="003d5-115">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
    - <span data-ttu-id="003d5-116">为设备充电时，电池指示灯将亮起，以指示当前的充电进度。</span><span class="sxs-lookup"><span data-stu-id="003d5-116">When the device is charging, the battery indicator lights up to indicate the current level of charge.</span></span>  <span data-ttu-id="003d5-117">最后一盏灯将不停闪烁，表示正在充电。</span><span class="sxs-lookup"><span data-stu-id="003d5-117">The last light will fade in and out to indicate active charging.</span></span>
    - <span data-ttu-id="003d5-118">当 HoloLens 处于打开状态时，电池指示灯以五个增量方式显示电池剩余电量。</span><span class="sxs-lookup"><span data-stu-id="003d5-118">When your HoloLens is on, the battery indicator displays the battery level in five increments.</span></span>
    - <span data-ttu-id="003d5-119">当五盏灯中只有一盏亮起时，表示电池剩余电量低于 20%。</span><span class="sxs-lookup"><span data-stu-id="003d5-119">When only one of the five lights is on, the battery level is below 20 percent.</span></span>
    - <span data-ttu-id="003d5-120">如果在电池剩余电量严重不足时你尝试打开设备，则一盏灯将会短暂闪烁，然后熄灭。</span><span class="sxs-lookup"><span data-stu-id="003d5-120">If the battery level is critically low and you try to turn on the device, one light will blink briefly, then go out.</span></span>
- <span data-ttu-id="003d5-121">在主机上，打开**文件资源管理器**，然后在左侧的**此电脑**下查找 HoloLens 2 设备。</span><span class="sxs-lookup"><span data-stu-id="003d5-121">On your host PC, open **File Explorer** and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="003d5-122">右键单击设备并选择“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="003d5-122">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="003d5-123">对话框将显示电池电量。</span><span class="sxs-lookup"><span data-stu-id="003d5-123">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 属性屏幕显示电池变化级别](images/ResetRecovery2.png)

<span data-ttu-id="003d5-125">如果设备无法引导到启动菜单，请注意主机计算机上的 LED 外观和设备枚举。</span><span class="sxs-lookup"><span data-stu-id="003d5-125">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="003d5-126">然后，按照[疑难解答指南](https://docs.microsoft.com/hololens/hololens-troubleshooting)进行操作。</span><span class="sxs-lookup"><span data-stu-id="003d5-126">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="003d5-127">如果设备的状态与疑难解答指南中列出的任何状态都不匹配，请在设备连接到电源而不是主机的情况下预先执行[硬重置程序](hololens-recovery.md#hard-reset-procedure)。</span><span class="sxs-lookup"><span data-stu-id="003d5-127">If the state of the device doesn't match any of the states listed in the troubleshooting guide, preform the [hard reset procedure](hololens-recovery.md#hard-reset-procedure) with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="003d5-128">等待至少一小时，让设备充电。</span><span class="sxs-lookup"><span data-stu-id="003d5-128">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="003d5-129">重置设备</span><span class="sxs-lookup"><span data-stu-id="003d5-129">Reset the device</span></span>

<span data-ttu-id="003d5-130">在某些情况下，可能需要在不使用软件 UI 的情况下手动重置设备。</span><span class="sxs-lookup"><span data-stu-id="003d5-130">Under certain circumstances, you may have to manually reset the device without using the software UI.</span></span>

### <span data-ttu-id="003d5-131">标准程序</span><span class="sxs-lookup"><span data-stu-id="003d5-131">Standard procedure</span></span>
1. <span data-ttu-id="003d5-132">拔下 Type-C 电缆，以断开设备与电源或主机计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="003d5-132">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="003d5-133">按住**电源**按钮 15 秒。</span><span class="sxs-lookup"><span data-stu-id="003d5-133">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="003d5-134">所有 LED 均应熄灭。</span><span class="sxs-lookup"><span data-stu-id="003d5-134">All LEDs should be off.</span></span>

3. <span data-ttu-id="003d5-135">等待 2-3 秒，然后短按**电源**按钮。</span><span class="sxs-lookup"><span data-stu-id="003d5-135">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="003d5-136">电源按钮附近的指示灯将亮起，并且设备将开始启动。</span><span class="sxs-lookup"><span data-stu-id="003d5-136">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="003d5-137">将设备连接到主机计算机，然后打开设备管理器。</span><span class="sxs-lookup"><span data-stu-id="003d5-137">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="003d5-138">（对于 Windows 10，请按“**Windows**”键，然后按“**X**”键，然后选择“**设备管理器**”），并确保设备正确枚举为 *Microsoft HoloLens*，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="003d5-138">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery 设备管理器](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="003d5-140">硬重置程序</span><span class="sxs-lookup"><span data-stu-id="003d5-140">Hard-reset procedure</span></span>

<span data-ttu-id="003d5-141">如果标准重置程序不起作用，可使用硬重置程序：</span><span class="sxs-lookup"><span data-stu-id="003d5-141">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="003d5-142">拔下 Type-C 电缆，以断开设备与电源或主机计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="003d5-142">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="003d5-143">按住 “**下调音量**” + “**电源**”按钮 15 秒。</span><span class="sxs-lookup"><span data-stu-id="003d5-143">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="003d5-144">设备将自动重启。</span><span class="sxs-lookup"><span data-stu-id="003d5-144">The device will automatically restart.</span></span>

4. <span data-ttu-id="003d5-145">将设备连接到主机计算机。</span><span class="sxs-lookup"><span data-stu-id="003d5-145">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="003d5-146">打开设备管理器（对于 Windows 10，请按 “**Windows**” 键，然后按 “**X**” 键，然后选择“**设备管理器**”）。</span><span class="sxs-lookup"><span data-stu-id="003d5-146">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="003d5-147">确保设备正确枚举为 *Microsoft HoloLens*，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="003d5-147">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLensRecovery 设备管理器 2](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="003d5-149">对设备进行干净重刷</span><span class="sxs-lookup"><span data-stu-id="003d5-149">Clean-reflash the device</span></span>

<span data-ttu-id="003d5-150">在特别情况下，可能需要对 HoloLens 2 进行干净刷写。</span><span class="sxs-lookup"><span data-stu-id="003d5-150">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="003d5-151">请注意，清理重刷预期不会引起以下问题：</span><span class="sxs-lookup"><span data-stu-id="003d5-151">Please note that clean-reflash isn’t expected to affect the following issues:</span></span>
- [<span data-ttu-id="003d5-152">显示颜色一致性</span><span class="sxs-lookup"><span data-stu-id="003d5-152">Display color uniformity</span></span>](hololens2-display.md)
- <span data-ttu-id="003d5-153">使用声音启动但无显示输出</span><span class="sxs-lookup"><span data-stu-id="003d5-153">Booting with sound but no display output</span></span>
- [<span data-ttu-id="003d5-154">1-3-5-LED 图案</span><span class="sxs-lookup"><span data-stu-id="003d5-154">1-3-5-LED pattern</span></span>](hololens2-setup.md#lights-to-indicate-problems)
- [<span data-ttu-id="003d5-155">过热</span><span class="sxs-lookup"><span data-stu-id="003d5-155">Overheating</span></span>](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- <span data-ttu-id="003d5-156">操作系统崩溃（不同于应用程序崩溃）</span><span class="sxs-lookup"><span data-stu-id="003d5-156">OS crashes (which are distinct from application crashes)</span></span>

<span data-ttu-id="003d5-157">对设备进行重刷的方法共有两种。</span><span class="sxs-lookup"><span data-stu-id="003d5-157">There are two ways to reflash the device.</span></span> <span data-ttu-id="003d5-158">对于这两种情况，必须首先 [从 Windows 应用商店安装高级恢复助手](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="003d5-158">For both, you must first [install Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="003d5-159">如果刷写设备，则将擦除所有个人数据、应用和设置，包括 TPM 重置。</span><span class="sxs-lookup"><span data-stu-id="003d5-159">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="003d5-160">默认情况下，“高级恢复助手”设置为下载最新的功能版本版本，请查看此处阅读[发行说明](hololens-release-notes.md#)以了解最新功能版本。</span><span class="sxs-lookup"><span data-stu-id="003d5-160">By default, Advanced Recovery Companion is set to download the most recent feature release build, check here to read our [Release notes](hololens-release-notes.md#) to learn about the latest feature release.</span></span> <span data-ttu-id="003d5-161">若要获取最新的 HoloLens 2 映像刷写工具 (FFU) 程序包以通过“高级恢复助手”重刷设备，[请点击这里下载最新的每月 HoloLens 2 图像](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="003d5-161">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [click here to download the latest monthly HoloLens 2 image](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="003d5-162">此版本是最新的通用版本。</span><span class="sxs-lookup"><span data-stu-id="003d5-162">This version is the latest generally available build.</span></span>

<span data-ttu-id="003d5-163">开始刷写程序前，请确保已在 Windows 10 电脑上安装并运行该应用，并已准备好检测设备。</span><span class="sxs-lookup"><span data-stu-id="003d5-163">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![HoloLens 2 干净重刷屏幕截图](images/ARC1.png)

### <span data-ttu-id="003d5-165">正常程序</span><span class="sxs-lookup"><span data-stu-id="003d5-165">Normal procedure</span></span>

1. <span data-ttu-id="003d5-166">在 HoloLens 设备运行期间，将其连接到你先前打开了 Advanced Recovery Companion 应用的 Windows 10 电脑。</span><span class="sxs-lookup"><span data-stu-id="003d5-166">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="003d5-167">系统将自动检测设备，Advanced Recovery Companion 应用的 UI 将开始更新进程：</span><span class="sxs-lookup"><span data-stu-id="003d5-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 干净重刷初始屏幕](images/ARC2.png)

3. <span data-ttu-id="003d5-169">在 Advanced Recovery Companion 应用 UI 中选择 HoloLens 2 设备，然后按照说明完成刷写。</span><span class="sxs-lookup"><span data-stu-id="003d5-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="003d5-170">手动程序</span><span class="sxs-lookup"><span data-stu-id="003d5-170">Manual procedure</span></span>

<span data-ttu-id="003d5-171">如果 HoloLens 2 无法正常启动，可能需要将设备置于恢复模式：</span><span class="sxs-lookup"><span data-stu-id="003d5-171">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="003d5-172">拔下 Type-C 电缆，以断开设备与电源或主机计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="003d5-172">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="003d5-173">按住**电源**按钮 15 秒。</span><span class="sxs-lookup"><span data-stu-id="003d5-173">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="003d5-174">所有 LED 均应熄灭。</span><span class="sxs-lookup"><span data-stu-id="003d5-174">All LEDs should turn off.</span></span>

3. <span data-ttu-id="003d5-175">在按下**上调音量**按钮的同时，按下并释放**电源按钮**以启动设备。</span><span class="sxs-lookup"><span data-stu-id="003d5-175">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="003d5-176">请等待 15 秒钟，然后再释放**上调音量**按钮。</span><span class="sxs-lookup"><span data-stu-id="003d5-176">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="003d5-177">五个 LED 中只有中间的 LED 会亮起。</span><span class="sxs-lookup"><span data-stu-id="003d5-177">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="003d5-178">将设备连接到主机电脑，然后打开设备管理器。</span><span class="sxs-lookup"><span data-stu-id="003d5-178">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="003d5-179">（对于 Windows 10，请按“**Windows**”键，然后按“**X**”键，然后选择“**设备管理器**”），并确保设备正确枚举为 Microsoft HoloLens，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="003d5-179">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLens恢复](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="003d5-181">系统将自动检测设备，Advanced Recovery Companion 应用的 UI 将开始更新进程：</span><span class="sxs-lookup"><span data-stu-id="003d5-181">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 干净重刷屏幕](images/ARC2.png)

6. <span data-ttu-id="003d5-183">在 Advanced Recovery Companion 应用 UI 中选择 HoloLens 2 设备，然后按照说明完成刷写。</span><span class="sxs-lookup"><span data-stu-id="003d5-183">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="003d5-184">在不使用应用商店的情况下下载 ARC</span><span class="sxs-lookup"><span data-stu-id="003d5-184">Download ARC without using the app store</span></span>

<span data-ttu-id="003d5-185">如果 IT 环境阻止使用 Windows Store 应用或限制对该零售商店的访问，IT 管理员可通过“脱机”部署路径提供此应用。</span><span class="sxs-lookup"><span data-stu-id="003d5-185">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE] 
 > - <span data-ttu-id="003d5-186">IT 管理员也可以通过 System Center Configuration Manager (SCCM) 或 Intune 分发此应用。</span><span class="sxs-lookup"><span data-stu-id="003d5-186">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="003d5-187">本指南重点介绍 Advanced Recovery Companion，但该过程也可用于其他“脱机”应用程序。</span><span class="sxs-lookup"><span data-stu-id="003d5-187">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="003d5-188">请按照以下步骤启用部署路径：</span><span class="sxs-lookup"><span data-stu-id="003d5-188">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="003d5-189">转到[适用于企业的 Microsoft Store](https://businessstore.microsoft.com)，然后使用 Azure Active Directory 身份登录。</span><span class="sxs-lookup"><span data-stu-id="003d5-189">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="003d5-190">转到“**管理 – 设置**”。</span><span class="sxs-lookup"><span data-stu-id="003d5-190">Go to **Manage – Settings**.</span></span> <span data-ttu-id="003d5-191">在“**购物体验**”下打开“**显示离线应用**”。</span><span class="sxs-lookup"><span data-stu-id="003d5-191">Turn on **Show offline apps** under **Shopping experience**.</span></span> 
1. <span data-ttu-id="003d5-192">转到“**为我的组购买**”，搜索 [\**_高级恢复助手_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="003d5-192">Go to **shop for my group**, and search for [\**_Advanced Recovery Companion_*_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="003d5-193">将“_*许可证类型\*\*”更改为“*\*_脱机_\*”_，然后选择_\*“管理”\*\*。</span><span class="sxs-lookup"><span data-stu-id="003d5-193">Change the _*License Type*\* to \**_offline_*_, and select _\*Manage\*\*.</span></span>
1. <span data-ttu-id="003d5-194">在“**下载脱机使用的程序包**”下，单击第二个蓝色“**下载**”按钮。</span><span class="sxs-lookup"><span data-stu-id="003d5-194">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="003d5-195">确保文件扩展名为 *.appxbundle*。</span><span class="sxs-lookup"><span data-stu-id="003d5-195">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="003d5-196">在此阶段，如果台式机可以访问互联网，请双击程序包以安装该应用。</span><span class="sxs-lookup"><span data-stu-id="003d5-196">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>


    - <span data-ttu-id="003d5-197">如果目标电脑没有 Internet 连接，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="003d5-197">If the destination PC has no internet connectivity, follow these steps:</span></span> 
       1. <span data-ttu-id="003d5-198">选择解码的许可证，然后选择“**生成许可证**”。</span><span class="sxs-lookup"><span data-stu-id="003d5-198">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="003d5-199">在“**所需框架**”下，选择“**下载**”。</span><span class="sxs-lookup"><span data-stu-id="003d5-199">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="003d5-200">使用 DISM 将软件包与依赖项和许可证一起应用。</span><span class="sxs-lookup"><span data-stu-id="003d5-200">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="003d5-201">从管理员命令提示符运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="003d5-201">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="003d5-202">此代码示例中的版本号可能与当前可用的版本不匹配。</span><span class="sxs-lookup"><span data-stu-id="003d5-202">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="003d5-203">可能还选择了与给定示例不同的下载位置。</span><span class="sxs-lookup"><span data-stu-id="003d5-203">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="003d5-204">根据需要对命令进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="003d5-204">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="003d5-205">计划使用 Advanced Recovery Companion 脱机安装 FFU 时，下载刷写映像可能会很有用。</span><span class="sxs-lookup"><span data-stu-id="003d5-205">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="003d5-206">[**下载 HoloLens 2 的最新映像**](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="003d5-206">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="003d5-207">其他资源：</span><span class="sxs-lookup"><span data-stu-id="003d5-207">Other resources:</span></span>
- [<span data-ttu-id="003d5-208">分配离线应用</span><span class="sxs-lookup"><span data-stu-id="003d5-208">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="003d5-209">DISM 应用程序包（.appx 或 .appxbundle）服务命令行选项</span><span class="sxs-lookup"><span data-stu-id="003d5-209">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
