---
title: 重新启动、重置或恢复 HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: 如何使用 Windows 设备恢复工具将映像闪存到 HoloLens 第一代。
keywords: 操作方法、重新启动、重置、恢复、硬重置、软重置、电源周期、HoloLens、关机、wdrt、windows 设备恢复工具
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 5963be84a5fbb186c77965d9bbf112713fea8242
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923510"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="cceb5-104">重新启动、重置或恢复 HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="cceb5-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="cceb5-105">如果你在使用 HoloLens 时遇到问题，可能需要尝试重新启动或重置，甚至使用设备恢复刷新设备。</span><span class="sxs-lookup"><span data-stu-id="cceb5-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="cceb5-106">本文将指导你按顺序执行建议的恢复步骤。</span><span class="sxs-lookup"><span data-stu-id="cceb5-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="cceb5-107">如果希望恢复 HoloLens 2，请参阅 [恢复 hololens 2](hololens-recovery.md)，因为该过程有所不同。</span><span class="sxs-lookup"><span data-stu-id="cceb5-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="cceb5-108">本文重点介绍 HoloLens 设备和软件。</span><span class="sxs-lookup"><span data-stu-id="cceb5-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="cceb5-109">如果你的全息影像看起来不正确，请参阅 **[HoloLens 环境注意事项](hololens-environment-considerations.md)** ，了解有关改善全息影像质量的因素的信息。</span><span class="sxs-lookup"><span data-stu-id="cceb5-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="cceb5-110">重启</span><span class="sxs-lookup"><span data-stu-id="cceb5-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="cceb5-111">使用 Cortana 执行安全重新启动</span><span class="sxs-lookup"><span data-stu-id="cceb5-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="cceb5-112">重新启动 HoloLens 的最安全方法是使用 Cortana，这通常是在你遇到 HoloLens 问题时首先要尝试的操作。</span><span class="sxs-lookup"><span data-stu-id="cceb5-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="cceb5-113">Cortana 在所有设备上都不可用。</span><span class="sxs-lookup"><span data-stu-id="cceb5-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="cceb5-114">Cortana 在所有 HoloLens (第一代) 设备上都可用。</span><span class="sxs-lookup"><span data-stu-id="cceb5-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="cceb5-115">在 Windows Holograpic 版本2004更新之前，在版本中的版本的设备上提供 Cortana。</span><span class="sxs-lookup"><span data-stu-id="cceb5-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="cceb5-116">打开 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="cceb5-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="cceb5-117">请确保用户已登录，且设备未等待密码来解锁。</span><span class="sxs-lookup"><span data-stu-id="cceb5-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="cceb5-118">说 "你好 Cortana，reboot" 或 "你好 Cortana，restart"。</span><span class="sxs-lookup"><span data-stu-id="cceb5-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="cceb5-119">Cortana 将做出响应，并提示你进行确认。</span><span class="sxs-lookup"><span data-stu-id="cceb5-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="cceb5-120">等待一段时间后播放声音，然后说 "是"。</span><span class="sxs-lookup"><span data-stu-id="cceb5-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="cceb5-121">设备将重新启动。</span><span class="sxs-lookup"><span data-stu-id="cceb5-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="cceb5-122">使用 "电源" 按钮执行安全重新启动</span><span class="sxs-lookup"><span data-stu-id="cceb5-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="cceb5-123">如果仍无法重新启动设备，请尝试使用 " **电源** " 按钮重新启动它：</span><span class="sxs-lookup"><span data-stu-id="cceb5-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="cceb5-124">按住 **电源** 按钮5秒钟。</span><span class="sxs-lookup"><span data-stu-id="cceb5-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="cceb5-125">1秒后，所有五个 Led 都将发亮，然后慢慢地按从右到左的顺序关闭。</span><span class="sxs-lookup"><span data-stu-id="cceb5-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="cceb5-126">5秒钟后，所有 Led 都将关闭，指示已成功关闭。</span><span class="sxs-lookup"><span data-stu-id="cceb5-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="cceb5-127">在所有 Led 都关闭后立即停止按按钮。</span><span class="sxs-lookup"><span data-stu-id="cceb5-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="cceb5-128">等待1分钟，让关闭完成。</span><span class="sxs-lookup"><span data-stu-id="cceb5-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="cceb5-129">即使在显示关闭后，关闭仍可能仍在进行中。</span><span class="sxs-lookup"><span data-stu-id="cceb5-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="cceb5-130">按住 **电源** 按钮1秒钟，再次打开设备。</span><span class="sxs-lookup"><span data-stu-id="cceb5-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="cceb5-131">使用 Windows 设备门户执行安全重新启动</span><span class="sxs-lookup"><span data-stu-id="cceb5-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="cceb5-132">对于此过程，必须将 HoloLens 配置为开发人员设备。</span><span class="sxs-lookup"><span data-stu-id="cceb5-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="cceb5-133">有关详细信息，请参阅 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="cceb5-133">Learn more at [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="cceb5-134">如果前面的过程不起作用，请尝试使用 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="cceb5-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="cceb5-135">在右上角，找到重新启动或关闭设备的选项。</span><span class="sxs-lookup"><span data-stu-id="cceb5-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="cceb5-136">执行不安全的强制重新启动</span><span class="sxs-lookup"><span data-stu-id="cceb5-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="cceb5-137">如果以前的方法未重启 HoloLens，请强制重新启动。</span><span class="sxs-lookup"><span data-stu-id="cceb5-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="cceb5-138">此方法等效于删除和重新安装电池。</span><span class="sxs-lookup"><span data-stu-id="cceb5-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="cceb5-139">这是很危险的，因为这可能会使你的设备处于损坏状态。</span><span class="sxs-lookup"><span data-stu-id="cceb5-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="cceb5-140">如果发生这种情况，则必须闪现 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="cceb5-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="cceb5-141">这是潜在的有害方法，只应在以前引用的方法不起作用时使用。</span><span class="sxs-lookup"><span data-stu-id="cceb5-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="cceb5-142">按住 **电源** 按钮至少10秒。</span><span class="sxs-lookup"><span data-stu-id="cceb5-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="cceb5-143">可以保持按钮超过10秒。</span><span class="sxs-lookup"><span data-stu-id="cceb5-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="cceb5-144">忽略任何 LED 活动是安全的。</span><span class="sxs-lookup"><span data-stu-id="cceb5-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="cceb5-145">释放按钮，等待2-3 秒。</span><span class="sxs-lookup"><span data-stu-id="cceb5-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="cceb5-146">按住 **电源** 按钮1秒。</span><span class="sxs-lookup"><span data-stu-id="cceb5-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="cceb5-147">如果仍有问题，请按下 **电源** 按钮4秒钟，直到所有电池指示器都淡出并且屏幕停止显示全息影像。</span><span class="sxs-lookup"><span data-stu-id="cceb5-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="cceb5-148">等待1分钟，然后再次按 **电源** 按钮打开设备。</span><span class="sxs-lookup"><span data-stu-id="cceb5-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="cceb5-149">返回到以前的版本-HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="cceb5-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="cceb5-150">在某些情况下，你可能想要返回到以前版本的 HoloLens 软件。</span><span class="sxs-lookup"><span data-stu-id="cceb5-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="cceb5-151">为此，可以使用 Windows 设备恢复工具将 HoloLens 重置为早期版本。</span><span class="sxs-lookup"><span data-stu-id="cceb5-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="cceb5-152">返回到早期版本会删除你的个人文件和设置。</span><span class="sxs-lookup"><span data-stu-id="cceb5-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="cceb5-153">若要返回到以前版本的 HoloLens 1，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="cceb5-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="cceb5-154">请确保没有任何手机或 Windows 设备连接到您的 PC。</span><span class="sxs-lookup"><span data-stu-id="cceb5-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="cceb5-155">在电脑上，下载 [Windows 设备恢复工具 (WDRT) ](https://support.microsoft.com/help/12379)。</span><span class="sxs-lookup"><span data-stu-id="cceb5-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="cceb5-156">下载 [HoloLens 周年更新恢复包](https://aka.ms/hololensrecovery)。</span><span class="sxs-lookup"><span data-stu-id="cceb5-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="cceb5-157">下载完成后，打开 **文件资源管理器**  >  **下载**。</span><span class="sxs-lookup"><span data-stu-id="cceb5-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="cceb5-158">右键单击刚下载的压缩文件夹，然后选择 "**提取所有**  >  **提取**" 将其解压缩。</span><span class="sxs-lookup"><span data-stu-id="cceb5-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="cceb5-159">使用随附的微 USB 电缆将您的 HoloLens 连接到您的 PC。</span><span class="sxs-lookup"><span data-stu-id="cceb5-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="cceb5-160">即使已使用其他电缆连接 HoloLens，也 (，这种方法的效果最佳。 ) </span><span class="sxs-lookup"><span data-stu-id="cceb5-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="cceb5-161">WDRT 将自动检测你的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="cceb5-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="cceb5-162">选择 " **Microsoft HoloLens** " 磁贴。</span><span class="sxs-lookup"><span data-stu-id="cceb5-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="cceb5-163">在下一个屏幕上，选择 " **手动包选择** "，然后选择在步骤4中解压缩的文件夹中包含的安装文件。</span><span class="sxs-lookup"><span data-stu-id="cceb5-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="cceb5-164"> (查找扩展名为 ffu 的文件 ) </span><span class="sxs-lookup"><span data-stu-id="cceb5-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="cceb5-165">选择 " **安装软件**"，然后按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="cceb5-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="cceb5-166">如果 WDRT 未检测到 HoloLens，请尝试重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="cceb5-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="cceb5-167">如果这不起作用，请选择 **"未检测到设备**"，选择 " **Microsoft HoloLens**"，然后按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="cceb5-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="cceb5-168">重置为出厂设置</span><span class="sxs-lookup"><span data-stu-id="cceb5-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="cceb5-169">电池需要至少40% 的电量才能重置。</span><span class="sxs-lookup"><span data-stu-id="cceb5-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="cceb5-170">如果 HoloLens 仍有问题，请尝试将其重置为出厂状态。</span><span class="sxs-lookup"><span data-stu-id="cceb5-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="cceb5-171">此步骤保留安装在其上的 Windows 全息软件的版本，并将其他所有内容返回到出厂设置。</span><span class="sxs-lookup"><span data-stu-id="cceb5-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="cceb5-172">如果重置设备，将擦除所有个人数据、应用和设置，包括 TPM 重置信息。</span><span class="sxs-lookup"><span data-stu-id="cceb5-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="cceb5-173">重置将仅安装最新安装的 Windows 全息版本。</span><span class="sxs-lookup"><span data-stu-id="cceb5-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="cceb5-174">必须重做所有初始化步骤 (校准、连接到 Wi-fi、创建用户帐户、下载应用，等等) 。</span><span class="sxs-lookup"><span data-stu-id="cceb5-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="cceb5-175">打开 "设置" 应用，然后选择 "**更新**  >  **恢复**"。</span><span class="sxs-lookup"><span data-stu-id="cceb5-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="cceb5-176">选择 " **重置设备** " 选项并阅读确认消息。</span><span class="sxs-lookup"><span data-stu-id="cceb5-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="cceb5-177">确认重置。</span><span class="sxs-lookup"><span data-stu-id="cceb5-177">Confirm the reset.</span></span> <span data-ttu-id="cceb5-178">设备将重新启动并显示一组旋转齿轮和一个进度栏。</span><span class="sxs-lookup"><span data-stu-id="cceb5-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="cceb5-179">等待大约30分钟才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="cceb5-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="cceb5-180">完成后，设备将重新启动进入 "现成" 体验。</span><span class="sxs-lookup"><span data-stu-id="cceb5-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="cceb5-181">重新安装操作系统</span><span class="sxs-lookup"><span data-stu-id="cceb5-181">Reinstall the operating system</span></span>

<span data-ttu-id="cceb5-182">如果在重新启动并重置后设备仍有问题，你可以在计算机上使用恢复工具来重新安装 HoloLens 操作系统和固件。</span><span class="sxs-lookup"><span data-stu-id="cceb5-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="cceb5-183">用于重置的 HoloLens 要求的数据将打包 (FFU) ，这与 .iso、.wim 或 .vhd 文件类似。</span><span class="sxs-lookup"><span data-stu-id="cceb5-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="cceb5-184">了解 FFU 图像文件格式。</span><span class="sxs-lookup"><span data-stu-id="cceb5-184">Learn about FFU image file formats.</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="cceb5-185">可以使用 Windows 设备恢复工具在 HoloLens (第一代) 上安装新操作系统。</span><span class="sxs-lookup"><span data-stu-id="cceb5-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="cceb5-186">使用该工具之前，请查看重新启动或重置 HoloLens 是否会解决此问题。</span><span class="sxs-lookup"><span data-stu-id="cceb5-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="cceb5-187">恢复过程可能需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="cceb5-187">The recovery process may take a while.</span></span> <span data-ttu-id="cceb5-188">完成后，将安装最新版本的 Windows 全息软件。</span><span class="sxs-lookup"><span data-stu-id="cceb5-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="cceb5-189">若要使用该工具，需要一台运行 Windows 10 或更高版本的计算机，其中至少有 4 GB 的可用存储空间。</span><span class="sxs-lookup"><span data-stu-id="cceb5-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="cceb5-190">不能在虚拟机上运行此工具。</span><span class="sxs-lookup"><span data-stu-id="cceb5-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="cceb5-191">恢复 HoloLens</span><span class="sxs-lookup"><span data-stu-id="cceb5-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="cceb5-192">在计算机上下载并安装 [Windows 设备恢复工具](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) 。</span><span class="sxs-lookup"><span data-stu-id="cceb5-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="cceb5-193">使用 HoloLens 随附的微 USB 电缆将 HoloLens (第一代) 连接到计算机。</span><span class="sxs-lookup"><span data-stu-id="cceb5-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="cceb5-194">打开 Windows 设备恢复工具并按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="cceb5-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="cceb5-195">如果未自动检测 HoloLens (第一代) ，请选择 **"我的设备未检测到"**。</span><span class="sxs-lookup"><span data-stu-id="cceb5-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="cceb5-196">然后按照说明将设备置于恢复模式。</span><span class="sxs-lookup"><span data-stu-id="cceb5-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="cceb5-197">手动闪烁模式</span><span class="sxs-lookup"><span data-stu-id="cceb5-197">Manual flashing mode</span></span>

<span data-ttu-id="cceb5-198">如果未检测到设备，请按照以下步骤将其置于闪烁模式：</span><span class="sxs-lookup"><span data-stu-id="cceb5-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="cceb5-199">从任何电源拔出设备。</span><span class="sxs-lookup"><span data-stu-id="cceb5-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="cceb5-200">如果设备已打开，请按住 **电源** 按钮，直到它完全关闭。</span><span class="sxs-lookup"><span data-stu-id="cceb5-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="cceb5-201">按住 **音量向上** 按钮，然后短暂点击 **电源** 按钮。</span><span class="sxs-lookup"><span data-stu-id="cceb5-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="cceb5-202">设备应启动并仅显示中间 LED。</span><span class="sxs-lookup"><span data-stu-id="cceb5-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="cceb5-203">将设备插入电脑。</span><span class="sxs-lookup"><span data-stu-id="cceb5-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="cceb5-204">打开 Windows 设备恢复工具。</span><span class="sxs-lookup"><span data-stu-id="cceb5-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="cceb5-205">选择 **"未检测到我的设备"，** 然后选择 **"HoloLens"。**</span><span class="sxs-lookup"><span data-stu-id="cceb5-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="cceb5-206">按照说明恢复设备。</span><span class="sxs-lookup"><span data-stu-id="cceb5-206">Follow the instructions to recover your device.</span></span>
