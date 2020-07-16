---
title: 重启、重置或恢复 HoloLens 1
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: a52e8e5bae49973d92efa6ea75391dc44d8b8ddb
ms.sourcegitcommit: 357094acfd39f7c59a0a62f1dd7918b58c209ef7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "10861157"
---
# <span data-ttu-id="2730a-104">重启、重置或恢复 HoloLens（第 1 代）</span><span class="sxs-lookup"><span data-stu-id="2730a-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="2730a-105">如果你的 HoloLens 出现问题，你可能想要尝试重启、重置甚至通过设备恢复进行重刷。</span><span class="sxs-lookup"><span data-stu-id="2730a-105">If you're experiencing problems with your HoloLens you may want to try a restart, reset, or even re-flash with device recovery.</span></span>

<span data-ttu-id="2730a-106">如果 HoloLens 不能正常运行，可尝试以下解决方法。</span><span class="sxs-lookup"><span data-stu-id="2730a-106">Here are some things to try if your HoloLens isn't running well.</span></span>  <span data-ttu-id="2730a-107">本文将指导你逐步完成推荐的恢复步骤。</span><span class="sxs-lookup"><span data-stu-id="2730a-107">This article will guide you through the recommended recovery steps in succession.</span></span>

<span data-ttu-id="2730a-108">如果你想要恢复的是 HoloLens 2，请查看有关[恢复 HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery) 的页面，因为这两种流程存在差异。</span><span class="sxs-lookup"><span data-stu-id="2730a-108">If you are looking to recover a HoloLens 2, please view the page for [Recovering a HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery), as there are differences in the processes.</span></span>

<span data-ttu-id="2730a-109">本文重点介绍 HoloLens 设备和软件，如果你的全息影像看起来有问题，[这篇文章](hololens-environment-considerations.md)讨论了改善全息影像质量的环境因素。</span><span class="sxs-lookup"><span data-stu-id="2730a-109">This article focuses on the HoloLens device and software, if your holograms don't look right, [this article](hololens-environment-considerations.md) talks about environmental factors that improve hologram quality.</span></span>

## <span data-ttu-id="2730a-110">“重新启动”</span><span class="sxs-lookup"><span data-stu-id="2730a-110">Restart</span></span>

### <span data-ttu-id="2730a-111">使用 Cortana 执行安全重启</span><span class="sxs-lookup"><span data-stu-id="2730a-111">Perform a safe restart by using Cortana</span></span>

<span data-ttu-id="2730a-112">重启 HoloLens 的最安全方法是使用 Cortana。</span><span class="sxs-lookup"><span data-stu-id="2730a-112">The safest way to restart the HoloLens is by using Cortana.</span></span> <span data-ttu-id="2730a-113">在 HoloLens 出现问题时，通常会首先执行这一简单操作。</span><span class="sxs-lookup"><span data-stu-id="2730a-113">This is generally an easy first-step when experiencing an issue with HoloLens.</span></span> 

> [!NOTE]
> <span data-ttu-id="2730a-114">并非所有设备上都支持使用 Cortana。</span><span class="sxs-lookup"><span data-stu-id="2730a-114">Cortana is not avalible on all devices.</span></span> <span data-ttu-id="2730a-115">Cortana 在所有 HoloLens（第 1 代）设备上都可用。</span><span class="sxs-lookup"><span data-stu-id="2730a-115">Cortana is avalible to all HoloLens (1st Gen) devices.</span></span>
> <span data-ttu-id="2730a-116">在 HoloLens 2 设备上，Cortana 在 Windows Holograpic 版本 2004 更新之前的内部版本上可用。</span><span class="sxs-lookup"><span data-stu-id="2730a-116">Cortana is avalible on HoloLens 2 devices on a build prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="2730a-117">戴上你的设备</span><span class="sxs-lookup"><span data-stu-id="2730a-117">Put on your device</span></span>
1. <span data-ttu-id="2730a-118">请确保已接通电源，用户已登录，并且设备并非是在等待用密码来进行解锁。</span><span class="sxs-lookup"><span data-stu-id="2730a-118">Make sure it's powered on, a user is logged in, and the device is not waiting for a password to unlock it.</span></span>
1. <span data-ttu-id="2730a-119">说“你好小娜，请重启”。</span><span class="sxs-lookup"><span data-stu-id="2730a-119">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
1. <span data-ttu-id="2730a-120">收到后，她会要求你确认。</span><span class="sxs-lookup"><span data-stu-id="2730a-120">When she acknowledges she will ask you for confirmation.</span></span> <span data-ttu-id="2730a-121">在她问完问题后，稍等片刻会有一个声音响起（这表示她正在听你说话），然后说“是”。</span><span class="sxs-lookup"><span data-stu-id="2730a-121">Wait a second for a sound to play after she has finished her question, indicating she is listening to you and then say "Yes."</span></span>
1. <span data-ttu-id="2730a-122">此时设备将重启。</span><span class="sxs-lookup"><span data-stu-id="2730a-122">The device will now restart.</span></span>

### <span data-ttu-id="2730a-123">使用电源按钮执行安全重启</span><span class="sxs-lookup"><span data-stu-id="2730a-123">Perform a safe restart by using the power button</span></span>

<span data-ttu-id="2730a-124">如果仍然无法重启设备，可以尝试使用电源按钮进行重启：</span><span class="sxs-lookup"><span data-stu-id="2730a-124">If you still can't restart your device, you can try to restart it by using the power button:</span></span>

1. <span data-ttu-id="2730a-125">按住电源按钮 5 秒。</span><span class="sxs-lookup"><span data-stu-id="2730a-125">Press and hold the power button for five seconds.</span></span>
   1. <span data-ttu-id="2730a-126">一秒钟后，你将看到五个 LED 全部亮起，然后从右到左慢慢熄灭。</span><span class="sxs-lookup"><span data-stu-id="2730a-126">After one second, you will see all five LEDs illuminate, then slowly turn off from right to left.</span></span>
   1. <span data-ttu-id="2730a-127">五秒钟后，所有 LED 全部熄灭，表示已成功发出关机命令。</span><span class="sxs-lookup"><span data-stu-id="2730a-127">After five seconds, all LEDs will be off, indicating the shutdown command was issued successfully.</span></span>
   1. <span data-ttu-id="2730a-128">请注意，一定要在所有 LED 都熄灭后立即释放该按钮。</span><span class="sxs-lookup"><span data-stu-id="2730a-128">Note that it's important to stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="2730a-129">等待 1 分钟，以便完全关机。</span><span class="sxs-lookup"><span data-stu-id="2730a-129">Wait one minute for the shutdown to cleanly succeed.</span></span> <span data-ttu-id="2730a-130">请注意，即使屏幕关闭，关机也可能仍在进行中。</span><span class="sxs-lookup"><span data-stu-id="2730a-130">Note that the shutdown may still be in progress even if the displays are turned off.</span></span>
1. <span data-ttu-id="2730a-131">通过按住电源按钮一秒钟，重新打开设备电源。</span><span class="sxs-lookup"><span data-stu-id="2730a-131">Power on the device again by pressing and holding the power button for one second.</span></span>

### <span data-ttu-id="2730a-132">使用 Windows 设备门户执行安全重启</span><span class="sxs-lookup"><span data-stu-id="2730a-132">Perform a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="2730a-133">若要执行此操作，必须将 HoloLens 配置为开发人员设备。</span><span class="sxs-lookup"><span data-stu-id="2730a-133">To do this, HoloLens has to be configured as a developer device.</span></span>  
> <span data-ttu-id="2730a-134">阅读有关 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2730a-134">Read more about [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="2730a-135">如果以上程序不起作用，可以尝试使用 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)来重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="2730a-135">If the previous procedure doesn't work, you can try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="2730a-136">右上角有一个可重启或关闭设备的选项。</span><span class="sxs-lookup"><span data-stu-id="2730a-136">In the upper right corner, there is an option to restart or shut down the device.</span></span>

### <span data-ttu-id="2730a-137">执行不安全强制重启</span><span class="sxs-lookup"><span data-stu-id="2730a-137">Perform an unsafe forced restart</span></span>

<span data-ttu-id="2730a-138">如果上述方法都无法成功重启设备，可以进行强制重启。</span><span class="sxs-lookup"><span data-stu-id="2730a-138">If none of the previous methods are able to successfully restart your device, you can force a restart.</span></span> <span data-ttu-id="2730a-139">此方法等同于从 HoloLens 中取出电池。</span><span class="sxs-lookup"><span data-stu-id="2730a-139">This method is equivalent to pulling the battery from the HoloLens.</span></span>  <span data-ttu-id="2730a-140">该操作很危险，可能会使你的设备进入损坏状态。</span><span class="sxs-lookup"><span data-stu-id="2730a-140">It is a dangerous operation which may leave your device in a corrupt state.</span></span>  <span data-ttu-id="2730a-141">如果发生这种情况，则必须刷写 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="2730a-141">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="2730a-142">这是一种可能有害的方法，只有在上述方法都不起作用时才能使用。</span><span class="sxs-lookup"><span data-stu-id="2730a-142">This is a potentially harmful method and should only be used in the event none of the above methods work.</span></span>

1. <span data-ttu-id="2730a-143">按住电源按钮至少 10 秒。</span><span class="sxs-lookup"><span data-stu-id="2730a-143">Press and hold the power button for at least 10 seconds.</span></span>
   - <span data-ttu-id="2730a-144">长按时间超出 10 秒也没有关系。</span><span class="sxs-lookup"><span data-stu-id="2730a-144">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="2730a-145">忽略任何 LED 活动的做法是安全的。</span><span class="sxs-lookup"><span data-stu-id="2730a-145">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="2730a-146">释放该按钮，等待两到三秒钟。</span><span class="sxs-lookup"><span data-stu-id="2730a-146">Release the button and wait for two or three seconds.</span></span>
1. <span data-ttu-id="2730a-147">通过按住电源按钮一秒钟，重新打开设备电源。</span><span class="sxs-lookup"><span data-stu-id="2730a-147">Power on the device again by pressing and holding the power button for one second.</span></span>
<span data-ttu-id="2730a-148">如果仍有问题，请按住电源按钮 4 秒钟，直至所有电池指示灯熄灭，且屏幕停止显示全息影像。</span><span class="sxs-lookup"><span data-stu-id="2730a-148">If you're still having problems, press the power button for 4 seconds, until all of the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="2730a-149">等待 1 分钟，然后再次按下电源按钮以打开设备。</span><span class="sxs-lookup"><span data-stu-id="2730a-149">Wait 1 minute, then press the power button again to turn on the device.</span></span>

## <span data-ttu-id="2730a-150">重置为出厂设置</span><span class="sxs-lookup"><span data-stu-id="2730a-150">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="2730a-151">电池电量至少达到 40% 才能进行重置。</span><span class="sxs-lookup"><span data-stu-id="2730a-151">The battery needs at least 40 percent charge to reset.</span></span>

<span data-ttu-id="2730a-152">如果 HoloLens 在重启后仍存在问题，请尝试将其重置为出厂状态。</span><span class="sxs-lookup"><span data-stu-id="2730a-152">If your HoloLens is still experiencing issues after restarting, try resetting it to factory state.</span></span>  <span data-ttu-id="2730a-153">重置 HoloLens 时，会保留安装在其上的 Windows Holographic 软件的版本，而将其他所有内容返回到出厂设置。</span><span class="sxs-lookup"><span data-stu-id="2730a-153">Resetting your HoloLens keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

<span data-ttu-id="2730a-154">如果重置设备，则将擦除所有个人数据、应用和设置，包括 TPM 重置。</span><span class="sxs-lookup"><span data-stu-id="2730a-154">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span> <span data-ttu-id="2730a-155">重置操作将仅安装最近安装的 Windows Holographic 版本，你必须重新执行所有初始化步骤（校准、连接到 Wi-Fi、创建用户帐户、下载应用等）。</span><span class="sxs-lookup"><span data-stu-id="2730a-155">Resetting will only install the latest installed version of Windows Holographic and you will have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so forth).</span></span>

1. <span data-ttu-id="2730a-156">启动“设置”应用，然后选择“更新”\*\*\*\* > “重置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2730a-156">Launch the Settings app, and then select **Update** > **Reset**.</span></span>
1. <span data-ttu-id="2730a-157">选择“重置设备”\*\*\*\* 选项，然后阅读确认消息。</span><span class="sxs-lookup"><span data-stu-id="2730a-157">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="2730a-158">如果你同意重置设备，则设备将重新启动并显示一组旋转的齿轮和一个进度栏。</span><span class="sxs-lookup"><span data-stu-id="2730a-158">If you agree to reset your device, the device will restart and display a set of spinning gears with a progress bar.</span></span>
1. <span data-ttu-id="2730a-159">等待约 30 分钟，直至该过程完成。</span><span class="sxs-lookup"><span data-stu-id="2730a-159">Wait about 30 minutes for this process to complete.</span></span>
1. <span data-ttu-id="2730a-160">重置将完成，并且设备将重启进入开箱即用体验。</span><span class="sxs-lookup"><span data-stu-id="2730a-160">The reset will complete and the device will restart into the out-of-the-box experience.</span></span>

## <span data-ttu-id="2730a-161">重装操作系统</span><span class="sxs-lookup"><span data-stu-id="2730a-161">Re-install the operating system</span></span>

<span data-ttu-id="2730a-162">如果设备在重启和重置后仍然存在问题，可在计算机上使用恢复工具重装 HoloLens 的操作系统和固件。</span><span class="sxs-lookup"><span data-stu-id="2730a-162">If the device is still having a problem after rebooting and resetting, you can use a recovery tool on your computer to reinstall the HoloLens' operating system and firmware.</span></span>  

<span data-ttu-id="2730a-163">HoloLens 需要重置的所有数据都将打包在一个完整刷写更新 (FFU) 内。</span><span class="sxs-lookup"><span data-stu-id="2730a-163">All of the data HoloLens needs to reset is packaged in a Full Flash Update (ffu).</span></span>  <span data-ttu-id="2730a-164">这类似于 iso、wim 或 vhd。</span><span class="sxs-lookup"><span data-stu-id="2730a-164">This is similar to an iso, wim, or vhd.</span></span>  [<span data-ttu-id="2730a-165">了解 FFU 映像文件格式。</span><span class="sxs-lookup"><span data-stu-id="2730a-165">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="2730a-166">如有必要，可使用 Windows Device Recovery Tool 在 HoloLens（第 1 代）上安装全新的操作系统。</span><span class="sxs-lookup"><span data-stu-id="2730a-166">If necessary, you can install a completely new operating system on your HoloLens (1st gen) with the Windows Device Recovery Tool.</span></span>

<span data-ttu-id="2730a-167">使用此工具之前，请先确定重启或重置 HoloLens 能否修复相应问题。</span><span class="sxs-lookup"><span data-stu-id="2730a-167">Before you use this tool, determine if restarting or resetting your HoloLens fixes the problem.</span></span> <span data-ttu-id="2730a-168">恢复过程可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="2730a-168">The recovery process may take some time.</span></span>  <span data-ttu-id="2730a-169">完成后，系统将安装批准用于 HoloLens 的最新版本 Windows Holographic 软件。</span><span class="sxs-lookup"><span data-stu-id="2730a-169">When you're done, the latest version of the Windows Holographic software approved for your HoloLens will be installed.</span></span>

<span data-ttu-id="2730a-170">若要使用此工具，需要使用运行 Windows 10 或更高版本的计算机，其中至少有 4 GB 的可用存储空间。</span><span class="sxs-lookup"><span data-stu-id="2730a-170">To use the tool, you'll need a computer running Windows 10 or later, with at least 4 GB of free storage space.</span></span>  <span data-ttu-id="2730a-171">请注意，不能在虚拟机上运行此工具。</span><span class="sxs-lookup"><span data-stu-id="2730a-171">Please note that you can't run this tool on a virtual machine.</span></span>

### <span data-ttu-id="2730a-172">恢复 HoloLens：</span><span class="sxs-lookup"><span data-stu-id="2730a-172">Recover your HoloLens:</span></span>

1. <span data-ttu-id="2730a-173">在你的计算机上，下载并安装 [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)。</span><span class="sxs-lookup"><span data-stu-id="2730a-173">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="2730a-174">使用 HoloLens 随附的 Micro USB 电缆将 HoloLens（第 1 代）连接到计算机。</span><span class="sxs-lookup"><span data-stu-id="2730a-174">Connect the HoloLens (1st gen) to your computer using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="2730a-175">运行 Windows Device Recovery Tool 并按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="2730a-175">Run the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="2730a-176">如果该工具未自动检测到 HoloLens（第 1 代），请选择“未检测到我的设备”\*\*\*\* 并按照说明将设备置于恢复模式。</span><span class="sxs-lookup"><span data-stu-id="2730a-176">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected** and follow the instructions to put your device into recovery mode.</span></span>

### <span data-ttu-id="2730a-177">手动刷写模式：</span><span class="sxs-lookup"><span data-stu-id="2730a-177">Manual Flashing Mode:</span></span>

<span data-ttu-id="2730a-178">如果未检测到你的设备，请使用以下方法手动将其置于刷写模式。</span><span class="sxs-lookup"><span data-stu-id="2730a-178">In the event that your device is not being detected please use the following method to manually place it into flashing mode.</span></span>

1. <span data-ttu-id="2730a-179">将设备与所有电源断开。</span><span class="sxs-lookup"><span data-stu-id="2730a-179">Unplug the device from all power sources.</span></span>
1. <span data-ttu-id="2730a-180">如果设备处于开启状态，请按住电源按钮，直到完全关闭。</span><span class="sxs-lookup"><span data-stu-id="2730a-180">If the device is on please hold down the power button until it is completely off.</span></span>
1. <span data-ttu-id="2730a-181">按住**上调音量**按钮，然后轻触**电源按钮**。</span><span class="sxs-lookup"><span data-stu-id="2730a-181">Hold the **Volume Up** button, and briefly tap the **Power button**.</span></span> 
1. <span data-ttu-id="2730a-182">此时设备应启动，然后仅显示中间的 LED 指示灯。</span><span class="sxs-lookup"><span data-stu-id="2730a-182">The device should boot and then display only the middle LED light.</span></span>
1. <span data-ttu-id="2730a-183">将设备连接至电脑。</span><span class="sxs-lookup"><span data-stu-id="2730a-183">Plug the device into your PC.</span></span>
1. <span data-ttu-id="2730a-184">启动 Windows Device Recovery Tool。</span><span class="sxs-lookup"><span data-stu-id="2730a-184">Launch Windows Device Recovery Tool.</span></span>
1. <span data-ttu-id="2730a-185">你将需要选择“未检测到我的设备”\*\*\*，然后选择“HoloLens”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2730a-185">You will need to select \*My device was not detected\*\*, and then select **HoloLens**.</span></span> 
1. <span data-ttu-id="2730a-186">按照说明恢复设备。</span><span class="sxs-lookup"><span data-stu-id="2730a-186">Follow the instructions to recover your device.</span></span>
