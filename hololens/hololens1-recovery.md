---
title: 重启、重置或恢复HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: 如何使用设备Windows工具将映像刷刷到第一代HoloLens映像。
keywords: 操作说明、重启、重置、恢复、硬重置、软重置、电源循环、HoloLens、关闭、wdrt、Windows 设备恢复工具
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
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635222"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a><span data-ttu-id="4e8ff-104">重启、重置或恢复HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="4e8ff-104">Restart, reset, or recover HoloLens (1st Gen)</span></span>

<span data-ttu-id="4e8ff-105">如果遇到设备问题，HoloLens尝试重启或重置，甚至使用设备恢复来重新运行设备。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-105">If you're experiencing problems with your HoloLens, you may want to try a restart or reset, or even reflash the device by using device recovery.</span></span> <span data-ttu-id="4e8ff-106">本文指导你按序完成建议的恢复步骤。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-106">This article guides you through the recommended recovery steps in order.</span></span>

<span data-ttu-id="4e8ff-107">如果要恢复服务，请参阅HoloLens 2恢复[HoloLens 2，因为](hololens-recovery.md)该过程有所不同。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-107">If you're looking to recover a HoloLens 2, see [Recovering a HoloLens 2](hololens-recovery.md), as that process differs.</span></span>

> [!NOTE]
> <span data-ttu-id="4e8ff-108">本文重点介绍HoloLens和软件。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-108">This article focuses on the HoloLens device and software.</span></span> <span data-ttu-id="4e8ff-109">如果全息影像看起来不正确，请参阅HoloLens环境注意事项，**[](hololens-environment-considerations.md)** 了解提高全息影像质量的因素。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-109">If your holograms don't look right, see **[HoloLens environment considerations](hololens-environment-considerations.md)** for information about factors that improve hologram quality.</span></span>

## <a name="restart"></a><span data-ttu-id="4e8ff-110">重启</span><span class="sxs-lookup"><span data-stu-id="4e8ff-110">Restart</span></span>

### <a name="do-a-safe-restart-by-using-cortana"></a><span data-ttu-id="4e8ff-111">使用安全重启Cortana</span><span class="sxs-lookup"><span data-stu-id="4e8ff-111">Do a safe restart by using Cortana</span></span>

<span data-ttu-id="4e8ff-112">重启 HoloLens 的最安全Cortana是使用 Cortana，这通常是遇到问题时要尝试的第一HoloLens。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-112">The safest way to restart the HoloLens is by using Cortana, which is generally the first thing to try when you experience an issue with HoloLens.</span></span>

> [!NOTE] 
> <span data-ttu-id="4e8ff-113">Cortana并非在所有设备上都可用。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-113">Cortana is not available on all devices.</span></span>
> - <span data-ttu-id="4e8ff-114">Cortana第一代HoloLens (设备上均) 可用。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-114">Cortana is available on all HoloLens (1st Gen) devices.</span></span> 
> - <span data-ttu-id="4e8ff-115">Cortana Holograpic 版本 2004 更新HoloLens 2版本之前，Windows设备上可用。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-115">Cortana is available on HoloLens 2 devices on builds prior to the Windows Holograpic, Version 2004 update.</span></span>

1. <span data-ttu-id="4e8ff-116">打开HoloLens。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-116">Turn on your HoloLens.</span></span>
1. <span data-ttu-id="4e8ff-117">确保用户已登录，并且设备未等待密码解锁。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-117">Make sure that a user is logged in and the device isn't waiting for a password to unlock it.</span></span>
2. <span data-ttu-id="4e8ff-118">说"你好，Cortana，重启"或"你好Cortana，重启"。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-118">Say "Hey Cortana, reboot" or "Hey Cortana, restart."</span></span>
3. <span data-ttu-id="4e8ff-119">Cortana响应并提示你确认。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-119">Cortana will respond and prompt you to confirm.</span></span> <span data-ttu-id="4e8ff-120">等待问题后播放声音，然后说"是"。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-120">Wait for a sound to play after the question, and then say "Yes."</span></span> <span data-ttu-id="4e8ff-121">设备将重启。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-121">The device will restart.</span></span>

### <a name="use-the-power-button-to-do-a-safe-restart"></a><span data-ttu-id="4e8ff-122">使用电源按钮执行安全重启</span><span class="sxs-lookup"><span data-stu-id="4e8ff-122">Use the power button to do a safe restart</span></span>

<span data-ttu-id="4e8ff-123">如果仍无法重启设备，请尝试使用电源按钮 **重启** 设备：</span><span class="sxs-lookup"><span data-stu-id="4e8ff-123">If you still can't restart your device, try to restart it by using the **power** button:</span></span>

1. <span data-ttu-id="4e8ff-124">按住电源 **按钮** 5 秒。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-124">Press and hold the **power** button for 5 seconds.</span></span> <span data-ttu-id="4e8ff-125">1 秒后，所有五个 LED 都会亮起，然后从右到左缓慢地一个地关闭。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-125">After 1 second, all five LEDs will illuminate and then slowly turn off one by one from right to left.</span></span> <span data-ttu-id="4e8ff-126">5 秒后，所有 LED 都将关闭，表示已成功关闭。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-126">After 5 seconds, all LEDs will be off, indicating successful shutdown.</span></span>
      
   > [!IMPORTANT]
   > <span data-ttu-id="4e8ff-127">在所有 LED 关闭后立即停止按下按钮。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-127">Stop pressing the button immediately after all the LEDs have turned off.</span></span>
1. <span data-ttu-id="4e8ff-128">等待 1 分钟，关闭完成。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-128">Wait 1 minute for the shutdown to complete.</span></span> <span data-ttu-id="4e8ff-129">即使关闭显示器，关闭也可能仍在进行中。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-129">The shutdown may still be in progress even after the displays are turned off.</span></span>
2. <span data-ttu-id="4e8ff-130">通过按住电源按钮 1 秒再次打开设备。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-130">Turn on the device again by pressing and holding the **power** button for 1 second.</span></span>

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a><span data-ttu-id="4e8ff-131">使用安全重启Windows 设备门户</span><span class="sxs-lookup"><span data-stu-id="4e8ff-131">Do a safe restart by using Windows Device Portal</span></span>

> [!NOTE]
> <span data-ttu-id="4e8ff-132">对于此过程，HoloLens必须配置为开发人员设备。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-132">For this process, HoloLens has to be configured as a developer device.</span></span> <span data-ttu-id="4e8ff-133">有关详细信息[，Windows 设备门户。](/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="4e8ff-133">Learn more at [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span>

<span data-ttu-id="4e8ff-134">如果上一过程不起作用，请尝试使用 Windows 设备门户[重启设备](/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-134">If the previous procedure didn't work, try to restart the device by using [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="4e8ff-135">在右上角，找到重启或关闭设备的选项。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-135">In the upper-right corner, find the option to restart or shut down the device.</span></span>

### <a name="do-an-unsafe-forced-restart"></a><span data-ttu-id="4e8ff-136">执行不安全的强制重启</span><span class="sxs-lookup"><span data-stu-id="4e8ff-136">Do an unsafe forced restart</span></span>

<span data-ttu-id="4e8ff-137">如果前面的方法未重启HoloLens，请强制重启。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-137">If the previous methods didn't restart your HoloLens, force a restart.</span></span> <span data-ttu-id="4e8ff-138">此方法等效于删除并重新安装电池。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-138">This method is equivalent to removing and reinstalling the battery.</span></span> <span data-ttu-id="4e8ff-139">这十分危险，因为它可能会使设备保持损坏状态。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-139">It's dangerous because it might leave your device in a corrupted state.</span></span> <span data-ttu-id="4e8ff-140">如果发生这种情况，必须刷出HoloLens。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-140">If that happens, you'll have to flash your HoloLens.</span></span>  

> [!WARNING]
> <span data-ttu-id="4e8ff-141">这是一种可能有害的方法，应仅在前面引用的方法不起作用时使用。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-141">This is a potentially harmful method and should only be used if the previously cited methods didn't work.</span></span>

1. <span data-ttu-id="4e8ff-142">按住电源 **按钮** 至少 10 秒。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-142">Press and hold the **power** button for at least 10 seconds.</span></span>
   - <span data-ttu-id="4e8ff-143">可以按住按钮超过 10 秒。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-143">It's okay to hold the button for longer than 10 seconds.</span></span>
   - <span data-ttu-id="4e8ff-144">可以放心地忽略任何 LED 活动。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-144">It's safe to ignore any LED activity.</span></span>
1. <span data-ttu-id="4e8ff-145">释放按钮并等待 2-3 秒。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-145">Release the button and wait for 2-3 seconds.</span></span>
1. <span data-ttu-id="4e8ff-146">按住 **电源按钮** 1 秒。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-146">Press and hold the **power** button for 1  second.</span></span>
1. <span data-ttu-id="4e8ff-147">如果仍有问题，请按电源按钮4 秒，直到所有电池指示器消失，屏幕停止显示全息影像。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-147">If you still have problems, press the **power** button for 4 seconds, until all the battery indicators fade out and the screen stops displaying holograms.</span></span> <span data-ttu-id="4e8ff-148">等待 1 分钟，然后再次按 **电源** 按钮打开设备。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-148">Wait 1 minute, and then press the **power** button again to turn on the device.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="4e8ff-149">返回到以前的版本 - HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="4e8ff-149">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="4e8ff-150">在某些情况下，你可能想要返回到早期版本的 HoloLens 软件。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-150">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="4e8ff-151">为此，可以使用 Windows Device Recovery 工具将HoloLens重置为早期版本。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-151">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="4e8ff-152">返回到早期版本会删除个人文件和设置。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-152">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="4e8ff-153">若要返回到早期版本的 HoloLens 1，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4e8ff-153">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="4e8ff-154">请确保未将任何手机或Windows设备插入电脑。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-154">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="4e8ff-155">在电脑上，下载[WINDOWS 设备恢复工具 (WDRT) 。 ](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="4e8ff-155">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="4e8ff-156">下载 HoloLens[周年更新恢复包](https://aka.ms/hololensrecovery)。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-156">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="4e8ff-157">下载完成后，打开"文件 **资源管理器**  >  **下载"。**</span><span class="sxs-lookup"><span data-stu-id="4e8ff-157">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="4e8ff-158">右键单击刚下载的压缩文件夹，然后选择"**提取所有**  >  **提取**"将其解压缩。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-158">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="4e8ff-159">连接HoloLens微型 USB 电缆将设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-159">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="4e8ff-160"> (即使一直在使用其他电缆来连接HoloLens，此电缆也效果最佳。) </span><span class="sxs-lookup"><span data-stu-id="4e8ff-160">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="4e8ff-161">WDRT 会自动检测HoloLens。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-161">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="4e8ff-162">选择 **"Microsoft HoloLens** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-162">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="4e8ff-163">下一个屏幕选择" **手动包** 选择"，然后选择步骤 4 中解压缩的文件夹中包含的安装文件。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-163">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="4e8ff-164"> (查找扩展名为 .ffu.) </span><span class="sxs-lookup"><span data-stu-id="4e8ff-164">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="4e8ff-165">选择 **"安装软件**"，并按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-165">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="4e8ff-166">如果 WDRT 未检测到你的HoloLens，请尝试重启电脑。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-166">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="4e8ff-167">如果不起作用，请选择"未检测到我的设备 **"，** 选择 **Microsoft HoloLens，然后** 按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-167">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="reset-to-factory-settings"></a><span data-ttu-id="4e8ff-168">重置为出厂设置</span><span class="sxs-lookup"><span data-stu-id="4e8ff-168">Reset to factory settings</span></span>

> [!NOTE]
> <span data-ttu-id="4e8ff-169">电池需要至少 40% 的费用进行重置。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-169">The battery needs at least a 40-percent charge to reset.</span></span>

<span data-ttu-id="4e8ff-170">如果HoloLens仍然存在问题，请尝试将问题重置为工厂状态。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-170">If your HoloLens still has a problem, try resetting it to factory state.</span></span> <span data-ttu-id="4e8ff-171">此步骤将保留安装Windows全息软件的版本，并返回工厂设置中其他所有内容。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-171">This step keeps the version of the Windows Holographic software that's installed on it and returns everything else to factory settings.</span></span>

>[!WARNING]
> <span data-ttu-id="4e8ff-172">如果重置设备，将清除所有个人数据、应用和设置，包括 TPM 重置信息。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-172">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset information.</span></span> <span data-ttu-id="4e8ff-173">重置将仅安装 Holographic Windows版本。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-173">Resetting will only install the latest installed version of Windows Holographic.</span></span> <span data-ttu-id="4e8ff-174">必须重新执行所有初始化步骤， (校准、连接到 Wi-Fi、创建用户帐户、下载应用) 。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-174">You'll have to redo all the initialization steps (calibrate, connect to Wi-Fi, create a user account, download apps, and so on).</span></span>

1. <span data-ttu-id="4e8ff-175">打开设置应用，然后选择"更新 **恢复**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="4e8ff-175">Open the Settings app, and then select **Update** > **Recovery**.</span></span>
1. <span data-ttu-id="4e8ff-176">选择" **重置设备"** 选项并阅读确认消息。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-176">Select the **Reset device** option and read the confirmation message.</span></span>
1. <span data-ttu-id="4e8ff-177">确认重置。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-177">Confirm the reset.</span></span> <span data-ttu-id="4e8ff-178">设备将重启并显示一组旋转齿轮和进度栏。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-178">The device will restart and display a set of spinning gears and a progress bar.</span></span>
1. <span data-ttu-id="4e8ff-179">等待大约 30 分钟，等待此过程完成。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-179">Wait about 30 minutes for this process to complete.</span></span> <span data-ttu-id="4e8ff-180">完成后，设备将重启进入"开箱即用"体验。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-180">When it's done, the device will restart into the "out-of-the-box" experience.</span></span>

## <a name="reinstall-the-operating-system"></a><span data-ttu-id="4e8ff-181">重新安装操作系统</span><span class="sxs-lookup"><span data-stu-id="4e8ff-181">Reinstall the operating system</span></span>

<span data-ttu-id="4e8ff-182">如果重启和重置后设备仍然出现问题，可以使用计算机上恢复工具重新安装HoloLens和固件。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-182">If the device is still having a problem after restart and reset, you can use a recovery tool on your computer to reinstall the HoloLens operating system and firmware.</span></span>  

<span data-ttu-id="4e8ff-183">重置HoloLens数据打包在完全闪存更新 (FFU) 中，类似于 .iso、.wim 或 .vhd 文件。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-183">The data that HoloLens needs for the reset is packaged in a Full Flash Update (FFU), which is similar to an .iso, .wim, or .vhd file.</span></span> [<span data-ttu-id="4e8ff-184">了解 FFU 图像文件格式。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-184">Learn about FFU image file formats.</span></span>](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

<span data-ttu-id="4e8ff-185">可以使用设备恢复工具HoloLens (第一代) 安装Windows操作系统。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-185">You can install a new operating system on your HoloLens (1st gen) by using the Windows Device Recovery Tool.</span></span> <span data-ttu-id="4e8ff-186">使用该工具之前，请参阅重新启动或重置HoloLens问题。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-186">Before you use that tool, see if restarting or resetting your HoloLens fixes the problem.</span></span>

<span data-ttu-id="4e8ff-187">恢复过程可能需要一段时间。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-187">The recovery process may take a while.</span></span> <span data-ttu-id="4e8ff-188">完成后，将安装最新版本Windows全息软件。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-188">When it's done, the latest version of the Windows Holographic software will be installed.</span></span>

<span data-ttu-id="4e8ff-189">若要使用该工具，需要一台运行 Windows 10 或更高版本的计算机，该计算机至少具有 4 GB 的可用存储空间。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-189">To use the tool, you need a computer running Windows 10 or later with at least 4 GB of free storage space.</span></span> <span data-ttu-id="4e8ff-190">无法对虚拟机运行此工具。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-190">You can't run this tool on a virtual machine.</span></span>

### <a name="recover-your-hololens"></a><span data-ttu-id="4e8ff-191">恢复HoloLens</span><span class="sxs-lookup"><span data-stu-id="4e8ff-191">Recover your HoloLens</span></span>

1. <span data-ttu-id="4e8ff-192">在计算机上下载Windows[设备](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)恢复工具。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-192">Download and install the [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) on your computer.</span></span>
1. <span data-ttu-id="4e8ff-193">连接HoloLens (设备) Micro USB 电缆将第一代设备连接到HoloLens。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-193">Connect the HoloLens (1st gen) to your computer by using the Micro USB cable that came with your HoloLens.</span></span>
1. <span data-ttu-id="4e8ff-194">打开"Windows恢复工具"并按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-194">Open the Windows Device Recovery Tool and follow the instructions.</span></span>

<span data-ttu-id="4e8ff-195">如果未HoloLens (第一代) ，请选择"未 **检测到我的设备"。**</span><span class="sxs-lookup"><span data-stu-id="4e8ff-195">If the HoloLens (1st gen) isn't automatically detected, select **My device was not detected**.</span></span> <span data-ttu-id="4e8ff-196">然后按照说明将设备置于恢复模式。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-196">Then follow the instructions to put the device into recovery mode.</span></span>

### <a name="manual-flashing-mode"></a><span data-ttu-id="4e8ff-197">手动闪烁模式</span><span class="sxs-lookup"><span data-stu-id="4e8ff-197">Manual flashing mode</span></span>

<span data-ttu-id="4e8ff-198">如果未检测到设备，请按照以下步骤将设备置于闪烁模式：</span><span class="sxs-lookup"><span data-stu-id="4e8ff-198">If your device isn't detected, follow these steps to put it into flashing mode:</span></span>

1. <span data-ttu-id="4e8ff-199">从任何电源拔下设备。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-199">Unplug the device from any power source.</span></span>
1. <span data-ttu-id="4e8ff-200">如果设备已打开，请按住 **电源** 按钮，直到完全关闭。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-200">If the device is on, hold down the **power** button until it completely turns off.</span></span>
2. <span data-ttu-id="4e8ff-201">按住 " **音量向上** " 按钮，并单击 " **电源** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-201">Hold the **volume up** button, and briefly tap the **power** button.</span></span> <span data-ttu-id="4e8ff-202">设备应启动并仅显示中间 LED。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-202">The device should start and display only the middle LED.</span></span>
3. <span data-ttu-id="4e8ff-203">将设备插入 PC。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-203">Plug the device into your PC.</span></span>
4. <span data-ttu-id="4e8ff-204">打开 Windows 设备恢复工具。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-204">Open the Windows Device Recovery Tool.</span></span>
5. <span data-ttu-id="4e8ff-205">**未检测到 "我的设备"** ，然后 **HoloLens**。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-205">Select **My device was not detected** and then **HoloLens**.</span></span> 
6. <span data-ttu-id="4e8ff-206">按照说明恢复你的设备。</span><span class="sxs-lookup"><span data-stu-id="4e8ff-206">Follow the instructions to recover your device.</span></span>
