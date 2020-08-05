---
title: 重启、重置或恢复 HoloLens 1
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: 如何使用 Windows Device Recovery Tool 将映像刷写到第 1 代 HoloLens。
keywords: 操作方法, 重启, 重置, 恢复, 硬重置, 软重置, 电源周期, HoloLens, 关机, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: cd3e7a14ea811f6f3f3086563e7ead3bcd0115ae
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915938"
---
# <span data-ttu-id="fc4a4-104">重启、重置或恢复 HoloLens（第 1 代）</span><span class="sxs-lookup"><span data-stu-id="fc4a4-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="fc4a4-105">如果你的 HoloLens 出现问题，你可能想尝试重新启动或重置，甚至通过使用设备恢复来刷新设备。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="fc4a4-106">本文将按顺序指导你完成建议的恢复步骤。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="fc4a4-107">如果要恢复 HoloLens 2，请参阅[恢复 HoloLens 2 ](https://docs.microsoft.com/hololens/hololens-recovery)，因为此过程有所不同。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="fc4a4-108">本文重点介绍 HoloLens 设备和软件。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="fc4a4-109">如果全息影像不正确，请参阅 **[HoloLens 环境注意事项](hololens-environment-considerations.md)**，了解有关改进全息质量因素的信息。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <span data-ttu-id="fc4a4-110">“重新启动”</span><span class="sxs-lookup"><span data-stu-id="fc4a4-110">Restart</span></span>

### <span data-ttu-id="fc4a4-111">使用 Cortana 执行安全重启</span><span class="sxs-lookup"><span data-stu-id="fc4a4-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="fc4a4-112">重新启动 HoloLens 的最安全方法是使用 Cortana，这通常是在遇到 HoloLens 问题时首先要尝试的方法。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="fc4a4-113">并非所有设备上都支持使用 Cortana。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="fc4a4-114">Cortana 在所有 HoloLens（第 1 代）设备上都可用。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="fc4a4-115">在 HoloLens 2 设备上，Cortana 在 Windows Holograpic 版本 2004 更新之前的内部版本上可用。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="fc4a4-116">打开 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="fc4a4-117">请确保用户已登录，并且设备并非是在等待用密码来进行解锁。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="fc4a4-118">说“你好小娜，请重启”。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="fc4a4-119">Cortana 会回复并提示您确认。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="fc4a4-120">提问后等待播放声音，然后说“是”。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="fc4a4-121">设备将启动。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-121">The device will restart.</span></span>

### <span data-ttu-id="fc4a4-122">使用“电源”按钮执行安全重启</span><span class="sxs-lookup"><span data-stu-id="fc4a4-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="fc4a4-123">如果仍然无法重启设备，可尝试使用**电源**按钮进行重启：</span><span class="sxs-lookup"><span data-stu-id="fc4a4-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="fc4a4-124">按住**电源**按钮 5 秒。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="fc4a4-125">1 秒后，所有五个 LED 都将点亮，然后从右到左缓慢关闭一个 LED。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="fc4a4-126">5 秒钟后，所有指示灯将熄灭，表明已成功关闭。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="fc4a4-127">一定要在所有 LED 都熄灭后立即释放该按钮。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="fc4a4-128">等待 1 分钟以完成关闭。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="fc4a4-129">即使屏幕关闭后，关机也可能仍在进行中。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="fc4a4-130">通过按住**电源**按钮 1 秒钟，重新打开设备。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <span data-ttu-id="fc4a4-131">使用 Windows 设备门户执行安全重启</span><span class="sxs-lookup"><span data-stu-id="fc4a4-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="fc4a4-132">为此，必须将 HoloLens 配置为开发人员设备。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="fc4a4-133">阅读有关 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="fc4a4-134">如果以上程序不起作用，可尝试使用 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)来重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="fc4a4-135">在右上角，可查找重启或关闭设备的选项。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <span data-ttu-id="fc4a4-136">执行不安全强制重启</span><span class="sxs-lookup"><span data-stu-id="fc4a4-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="fc4a4-137">如果以前的方法没有重新启动 HoloLens，请强制重新启动。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="fc4a4-138">此方法等同于取下并重新安装电池。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="fc4a4-139">这很危险，因为它可能会使您的设备处于损坏状态。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="fc4a4-140">如果发生这种情况，则必须刷写 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="fc4a4-141">这是一种可能有害的方法，仅在之前引用的方法无效的情况下使用。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="fc4a4-142">按住**电源**按钮至少 10 秒。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="fc4a4-143">长按时间超出 10 秒也没有关系。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="fc4a4-144">忽略任何 LED 活动的做法是安全的。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="fc4a4-145">释放该按钮，等待 2-3 秒钟。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="fc4a4-146">按住**电源**按钮 1 秒。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="fc4a4-147">如果仍有问题，请按住**电源**按钮 4 秒钟，直至所有电池指示灯熄灭，且屏幕停止显示全息影像。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="fc4a4-148">等待 1 分钟，然后再次按下**电源**按钮以打开设备。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <span data-ttu-id="fc4a4-149">重置为出厂设置</span><span class="sxs-lookup"><span data-stu-id="fc4a4-149">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="fc4a4-150">电池电量至少达到 40% 才能进行重置。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-150">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="fc4a4-151">如果 HoloLens 仍然有问题，请尝试将其重置为出厂状态。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-151">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="fc4a4-152">此步骤会保留安装在其上的 Windows Holographic 软件的版本，而将其他所有内容返回到出厂设置。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-152">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="fc4a4-153">如果重置设备，则将擦除所有个人数据、应用和设置，包括 TPM 重置信息。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-153">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="fc4a4-154">重置将仅安装最新安装的 Windows 全息版本。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-154">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="fc4a4-155">必须重新执行所有初始化步骤（校准、连接到 Wi-Fi、创建用户帐户、下载应用程序等）</span><span class="sxs-lookup"><span data-stu-id="fc4a4-155">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="fc4a4-156">启动“设置”应用，然后选择“**更新**” > “**恢复**”。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-156">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="fc4a4-157">选择“重置设备”\*\*\*\* 选项，然后阅读确认消息。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="fc4a4-158">确认重置。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-158">Confirm the reset.</span></span> <span data-ttu-id="fc4a4-159">设备将重新启动并显示一组旋转的齿轮和一个进度栏。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-159">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="fc4a4-160">等待约 30 分钟，直至该过程完成。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-160">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="fc4a4-161">完成时，设备将重启进入开箱即用体验。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-161">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <span data-ttu-id="fc4a4-162">重新安装操作系统</span><span class="sxs-lookup"><span data-stu-id="fc4a4-162">Reinstall the operating system</span></span>

<span data-ttu-id="fc4a4-163">如果设备在重启和重置后仍然存在问题，可在计算机上使用恢复工具重装 HoloLens 的操作系统和固件。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-163">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="fc4a4-164">HoloLens 重置所需的数据封装在映像刷写工具（FFU）中，它与 .iso、.wim 或 .vhd 文件相似。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-164">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="fc4a4-165">了解 FFU 映像文件格式。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="fc4a4-166">可通过使用 Windows Device Recovery Tool 在 HoloLens（第 1 代）上安装新操作系统。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-166">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="fc4a4-167">使用此工具之前，请先看看重启或重置 HoloLens 能否修复相应问题。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-167">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="fc4a4-168">恢复过程可能需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-168">The recovery process may take a while.</span></span> <span data-ttu-id="fc4a4-169">完成后，将安装最新版本的 Windows Holographic 软件。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-169">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="fc4a4-170">若要使用此工具，需要使用运行 Windows 10 或更高版本的计算机，其中至少有 4 GB 的可用存储空间。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-170">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="fc4a4-171">不能在虚拟机上运行此工具。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-171">You can't run this tool on a virtual machine.</span></span>

### <span data-ttu-id="fc4a4-172">恢复 HoloLens</span><span class="sxs-lookup"><span data-stu-id="fc4a4-172">Recover your HoloLens</span></span>

1. <span data-ttu-id="fc4a4-173">在你的计算机上，下载并安装 [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="fc4a4-174">通过使用 HoloLens 随附的 Micro USB 电缆将 HoloLens（第 1 代）连接到计算机。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-174">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="fc4a4-175">打开 Windows Device Recovery Tool 并按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-175">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="fc4a4-176">如果未自动检测到 HoloLens（第一代），请选择“**未检测到我的设备**”。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="fc4a4-177">然后按照说明将设备置于恢复模式。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-177">Then follow the instructions to put the device into recovery mode.</span></span>

### <span data-ttu-id="fc4a4-178">手动刷写模式</span><span class="sxs-lookup"><span data-stu-id="fc4a4-178">Manual flashing mode</span></span>

<span data-ttu-id="fc4a4-179">如果未检测到设备，请按照以下步骤将其置于闪烁模式：</span><span class="sxs-lookup"><span data-stu-id="fc4a4-179">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="fc4a4-180">将设备与任何电源断开。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-180">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="fc4a4-181">如果设备处于开启状态，请按住**电源**按钮，直到完全关闭。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-181">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="fc4a4-182">按住**上调音量**按钮，然后轻触**电源**按钮。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-182">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="fc4a4-183">此时设备应启动，仅显示中间的 LED 指示灯。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-183">The device should start and display only the middle LED light.</span></span>
3. <span data-ttu-id="fc4a4-184">将设备连接至电脑。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-184">Plug the device into your PC.</span></span>
4. <span data-ttu-id="fc4a4-185">打开 Windows Device Recovery Tool。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-185">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="fc4a4-186">选择“**未检测到我的设备**”，然后选择“**HoloLens**”。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-186">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="fc4a4-187">按照说明恢复设备。</span><span class="sxs-lookup"><span data-stu-id="fc4a4-187">Follow the instructions to recover your device.</span></span>
