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
ms.openlocfilehash: 9c9dd12b596d8fafdfe575797193f18e7b96919c
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915951"
---
# <span data-ttu-id="9fab7-104">重启、重置或恢复 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="9fab7-104">Restart, reset, or recover HoloLens 2</span></span>

## <span data-ttu-id="9fab7-105">给设备充电</span><span class="sxs-lookup"><span data-stu-id="9fab7-105">Charge the device</span></span>

<span data-ttu-id="9fab7-106">在开始任何故障排除过程之前，请确保将设备充电至电池容量的 20 % 至 40%。</span><span class="sxs-lookup"><span data-stu-id="9fab7-106">Before you start any troubleshooting procedure, make sure that your device is charged to 20 to 40 percent of battery capacity if possible.</span></span> <span data-ttu-id="9fab7-107">请使用 HoloLens2 设备附带的充电器和 USB Type-C 电缆。</span><span class="sxs-lookup"><span data-stu-id="9fab7-107">Use the charger and the USB Type-C cables that come with the HoloLens2 device.</span></span> <span data-ttu-id="9fab7-108">如果这些附件不可用，请确保可用的充电器支持至少 15 W 的功率。</span><span class="sxs-lookup"><span data-stu-id="9fab7-108">If those accessories aren't available, make sure the charger that's available can support at least 15 W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="9fab7-109">如果可能，请避免使用电脑通过 USB 给设备充电（速度很慢）。</span><span class="sxs-lookup"><span data-stu-id="9fab7-109">If possible, avoid using a PC to charge the device over USB, which is slow.</span></span>

<span data-ttu-id="9fab7-110">如果设备已正确启动且运行，有三种方法可以检查电池电量：</span><span class="sxs-lookup"><span data-stu-id="9fab7-110">If the device is correctly booted and running, there are three ways to check the battery charge level:</span></span>

- <span data-ttu-id="9fab7-111">从 HoloLens 设备 UI 的主菜单。</span><span class="sxs-lookup"><span data-stu-id="9fab7-111">From the main menu of the HoloLens device UI.</span></span>
- <span data-ttu-id="9fab7-112">查看靠近电源按钮的 LED（对于 40% 的电量，应该可看到至少两个稳定的 LED）。</span><span class="sxs-lookup"><span data-stu-id="9fab7-112">View the LED close to the power button (for a 40-percent charge, you should see at least two solid LEDS).</span></span>
- <span data-ttu-id="9fab7-113">在主机上，打开“文件资源管理器”，然后在左侧的“**此电脑**”下查找 HoloLens 2 设备。</span><span class="sxs-lookup"><span data-stu-id="9fab7-113">On your host PC, open File Explorer and look for your HoloLens 2 device on left side under **This PC**.</span></span> <span data-ttu-id="9fab7-114">右键单击设备并选择“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="9fab7-114">Right-click the device, and select **Properties**.</span></span> <span data-ttu-id="9fab7-115">对话框将显示电池电量。</span><span class="sxs-lookup"><span data-stu-id="9fab7-115">A dialog box will show the battery charge level.</span></span>

   ![HoloLens 2 属性屏幕显示电池变化级别](images/ResetRecovery2.png)

<span data-ttu-id="9fab7-117">如果设备无法引导到启动菜单，请注意主机计算机上的 LED 外观和设备枚举。</span><span class="sxs-lookup"><span data-stu-id="9fab7-117">If the device can't boot to the startup menu, note the LED appearance and device enumeration on the host PC.</span></span> <span data-ttu-id="9fab7-118">然后，按照[疑难解答指南](https://docs.microsoft.com/hololens/hololens-troubleshooting)进行操作。</span><span class="sxs-lookup"><span data-stu-id="9fab7-118">Then follow the [troubleshooting guide](https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="9fab7-119">如果设备的状态与疑难解答指南中列出的任何状态都不匹配，请在设备连接到电源而不是主机的情况下执行*硬重置程序*。</span><span class="sxs-lookup"><span data-stu-id="9fab7-119">If the state of the device doesn't match any of the states listed in the troubleshooting guide, do the *hard reset procedure* with the device connected to the power supply, not to your host PC.</span></span> <span data-ttu-id="9fab7-120">等待至少一小时，让设备充电。</span><span class="sxs-lookup"><span data-stu-id="9fab7-120">Wait at least one hour for the device to charge.</span></span>

## <span data-ttu-id="9fab7-121">重置设备</span><span class="sxs-lookup"><span data-stu-id="9fab7-121">Reset the device</span></span>

<span data-ttu-id="9fab7-122">在某些情况下，可能需要在不使用 SW UI 的情况下手动重置设备。</span><span class="sxs-lookup"><span data-stu-id="9fab7-122">Under certain circumstances, you may have to manually reset the device without using the SW UI.</span></span>

### <span data-ttu-id="9fab7-123">标准程序</span><span class="sxs-lookup"><span data-stu-id="9fab7-123">Standard procedure</span></span>
1. <span data-ttu-id="9fab7-124">拔下 Type-C 电缆，以断开设备与电源或主机计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="9fab7-124">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="9fab7-125">按住**电源**按钮 15 秒。</span><span class="sxs-lookup"><span data-stu-id="9fab7-125">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="9fab7-126">所有 LED 均应熄灭。</span><span class="sxs-lookup"><span data-stu-id="9fab7-126">All LEDs should be off.</span></span>

3. <span data-ttu-id="9fab7-127">等待 2-3 秒，然后短按**电源**按钮。</span><span class="sxs-lookup"><span data-stu-id="9fab7-127">Wait 2-3 seconds, and then short-press the **power** button.</span></span> <span data-ttu-id="9fab7-128">电源按钮附近的指示灯将亮起，并且设备将开始启动。</span><span class="sxs-lookup"><span data-stu-id="9fab7-128">The LEDs close to the power button will light up, and the device will begin to start up.</span></span>

4. <span data-ttu-id="9fab7-129">将设备连接到主机计算机，然后打开设备管理器。</span><span class="sxs-lookup"><span data-stu-id="9fab7-129">Connect the device to the host PC, and then open Device Manager.</span></span> <span data-ttu-id="9fab7-130">（对于 Windows 10，请按“**Windows**”键，然后按“**X**”键，然后选择“**设备管理器**”），并确保设备正确枚举为 *Microsoft HoloLens*，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="9fab7-130">(For Windows 10, press the **Windows** key and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLens恢复](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="9fab7-132">硬重置程序</span><span class="sxs-lookup"><span data-stu-id="9fab7-132">Hard-reset procedure</span></span>

<span data-ttu-id="9fab7-133">如果标准重置程序不起作用，可使用硬重置程序：</span><span class="sxs-lookup"><span data-stu-id="9fab7-133">If the standard reset procedure didn't work, use the hard-reset procedure:</span></span>

1. <span data-ttu-id="9fab7-134">拔下 Type-C 电缆，以断开设备与电源或主机计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="9fab7-134">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="9fab7-135">按住 “**下调音量**” + “**电源**”按钮 15 秒。</span><span class="sxs-lookup"><span data-stu-id="9fab7-135">Hold down the **volume down** + **power** buttons for 15 seconds.</span></span> <span data-ttu-id="9fab7-136">设备将自动重启。</span><span class="sxs-lookup"><span data-stu-id="9fab7-136">The device will automatically restart.</span></span>

4. <span data-ttu-id="9fab7-137">将设备连接到主机计算机。</span><span class="sxs-lookup"><span data-stu-id="9fab7-137">Connect the device to the host PC.</span></span>
5. <span data-ttu-id="9fab7-138">打开设备管理器（对于 Windows 10，请按 “**Windows**” 键，然后按 “**X**” 键，然后选择“**设备管理器**”）。</span><span class="sxs-lookup"><span data-stu-id="9fab7-138">Open Device Manager (for Windows 10 press the **Windows** key and then the **X** key, and then select **Device Manager**).</span></span> <span data-ttu-id="9fab7-139">确保设备正确枚举为 *Microsoft HoloLens*，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="9fab7-139">Make sure the device enumerates correctly as *Microsoft HoloLens* as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLens恢复](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="9fab7-141">对设备进行干净重刷</span><span class="sxs-lookup"><span data-stu-id="9fab7-141">Clean-reflash the device</span></span>

<span data-ttu-id="9fab7-142">在特别情况下，可能需要对 HoloLens 2 进行干净刷写。</span><span class="sxs-lookup"><span data-stu-id="9fab7-142">In extraordinary situations, you may have to "clean-flash" the HoloLens 2.</span></span> <span data-ttu-id="9fab7-143">对设备进行重刷的方法共有两种。</span><span class="sxs-lookup"><span data-stu-id="9fab7-143">There are two ways to reflash the device.</span></span> <span data-ttu-id="9fab7-144">对于两种情况，都必须首先[从 Windows Store 安装 Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="9fab7-144">For both, you must first install [Advanced Recovery Companion from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>

>[!WARNING]
><span data-ttu-id="9fab7-145">如果刷写设备，则将擦除所有个人数据、应用和设置，包括 TPM 重置。</span><span class="sxs-lookup"><span data-stu-id="9fab7-145">If you reflash your device, all your personal data, apps, and settings will be erased, including TPM-reset information.</span></span>

<span data-ttu-id="9fab7-146">默认情况下，Advanced Recovery Companion 当前设置为下载 [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004) 的功能版。</span><span class="sxs-lookup"><span data-stu-id="9fab7-146">By default, Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004).</span></span> <span data-ttu-id="9fab7-147">若要获取最新的 HoloLens 2 映像刷写工具（FFU）程序包以通过 Advanced Recovery Companion 重刷设备，请[在此处下载](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="9fab7-147">To get the latest HoloLens 2 Full Flash Update (FFU) package to reflash your device via Advanced Recovery Companion, [download it here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="9fab7-148">此版本是最新的通用版本。</span><span class="sxs-lookup"><span data-stu-id="9fab7-148">This version is the latest generally available build.</span></span>

<span data-ttu-id="9fab7-149">开始刷写程序前，请确保已在 Windows 10 电脑上安装并运行该应用，并已准备好检测设备。</span><span class="sxs-lookup"><span data-stu-id="9fab7-149">Before you start the reflash procedure, make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![HoloLens 2 干净重刷屏幕截图](images/ARC1.png)

### <span data-ttu-id="9fab7-151">正常程序</span><span class="sxs-lookup"><span data-stu-id="9fab7-151">Normal procedure</span></span>

1. <span data-ttu-id="9fab7-152">在 HoloLens 设备运行期间，将其连接到你先前打开了 Advanced Recovery Companion 应用的 Windows 10 电脑。</span><span class="sxs-lookup"><span data-stu-id="9fab7-152">While the HoloLens device is running, connect it to the Windows 10 PC where you previously opened the Advanced Recovery Companion app.</span></span>
 
   <span data-ttu-id="9fab7-153">系统将自动检测设备，Advanced Recovery Companion 应用的 UI 将开始更新进程：</span><span class="sxs-lookup"><span data-stu-id="9fab7-153">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 干净重刷初始屏幕](images/ARC2.png)

3. <span data-ttu-id="9fab7-155">在 Advanced Recovery Companion 应用 UI 中选择 HoloLens 2 设备，然后按照说明完成刷写。</span><span class="sxs-lookup"><span data-stu-id="9fab7-155">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and follow the instructions to complete the reflash.</span></span>

### <span data-ttu-id="9fab7-156">手动程序</span><span class="sxs-lookup"><span data-stu-id="9fab7-156">Manual procedure</span></span>

<span data-ttu-id="9fab7-157">如果 HoloLens 2 无法正常启动，可能需要将设备置于恢复模式：</span><span class="sxs-lookup"><span data-stu-id="9fab7-157">If the HoloLens 2 doesn't start correctly, you may need to put the device into Recovery mode:</span></span>

1. <span data-ttu-id="9fab7-158">拔下 Type-C 电缆，以断开设备与电源或主机计算机的连接。</span><span class="sxs-lookup"><span data-stu-id="9fab7-158">Unplug the Type-C cable to disconnect the device from the power supply or the host PC.</span></span>

2. <span data-ttu-id="9fab7-159">按住**电源**按钮 15 秒。</span><span class="sxs-lookup"><span data-stu-id="9fab7-159">Press and hold the **power** button for 15 seconds.</span></span> <span data-ttu-id="9fab7-160">所有 LED 均应熄灭。</span><span class="sxs-lookup"><span data-stu-id="9fab7-160">All LEDs should turn off.</span></span>

3. <span data-ttu-id="9fab7-161">在按下**上调音量**按钮的同时，按下并释放**电源按钮**以启动设备。</span><span class="sxs-lookup"><span data-stu-id="9fab7-161">While pressing the **volume up** button, press and release the **power** button to start the device.</span></span> <span data-ttu-id="9fab7-162">请等待 15 秒钟，然后再释放**上调音量**按钮。</span><span class="sxs-lookup"><span data-stu-id="9fab7-162">Wait 15 seconds, and then release the **volume up** button.</span></span> <span data-ttu-id="9fab7-163">五个 LED 中只有中间的 LED 会亮起。</span><span class="sxs-lookup"><span data-stu-id="9fab7-163">Only the middle LED of the five LEDs will light up.</span></span>

4. <span data-ttu-id="9fab7-164">将设备连接到主机电脑，然后打开设备管理器。</span><span class="sxs-lookup"><span data-stu-id="9fab7-164">Connect the device to the host PC, and open Device Manager.</span></span> <span data-ttu-id="9fab7-165">（对于 Windows 10，请按“**Windows**”键，然后按“**X**”键，然后选择“**设备管理器**”），并确保设备正确枚举为 Microsoft HoloLens，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="9fab7-165">(For Windows 10 press the **Windows** key, and then the **X** key, and then select **Device Manager**.) Make sure the device enumerates correctly as Microsoft HoloLens as shown in the following image:</span></span>

   ![HoloLens 2 MicrosoftHoloLens恢复](images/MicrosoftHoloLensRecovery.png)

   <span data-ttu-id="9fab7-167">系统将自动检测设备，Advanced Recovery Companion 应用的 UI 将开始更新进程：</span><span class="sxs-lookup"><span data-stu-id="9fab7-167">The device will be automatically detected, and the Advanced Recovery Companion app UI will start the update process:</span></span>

   ![HoloLens 2 干净重刷屏幕](images/ARC2.png)

6. <span data-ttu-id="9fab7-169">在 Advanced Recovery Companion 应用 UI 中选择 HoloLens 2 设备，然后按照说明完成刷写。</span><span class="sxs-lookup"><span data-stu-id="9fab7-169">Select the HoloLens 2 device in the Advanced Recovery Companion app UI, and then follow the instructions to complete the reflash.</span></span>

## <span data-ttu-id="9fab7-170">在不使用应用商店的情况下下载 ARC</span><span class="sxs-lookup"><span data-stu-id="9fab7-170">Download ARC without using the app store</span></span>

<span data-ttu-id="9fab7-171">如果 IT 环境阻止使用 Windows Store 应用或限制对该零售商店的访问，IT 管理员可通过“脱机”部署路径提供此应用。</span><span class="sxs-lookup"><span data-stu-id="9fab7-171">If the IT environment prevents the use of the Windows Store app or limits access to the retail store, the IT administrator can make this app available through an "offline" deployment path.</span></span>

 >[!NOTE] 
 > - <span data-ttu-id="9fab7-172">IT 管理员也可以通过 System Center Configuration Manager (SCCM) 或 Intune 分发此应用。</span><span class="sxs-lookup"><span data-stu-id="9fab7-172">IT administrators can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
 > - <span data-ttu-id="9fab7-173">本指南重点介绍 Advanced Recovery Companion，但该过程也可用于其他“脱机”应用程序。</span><span class="sxs-lookup"><span data-stu-id="9fab7-173">This guide focuses on Advanced Recovery Companion, but the process can also be used for other "offline" apps.</span></span>

<span data-ttu-id="9fab7-174">请按照以下步骤启用部署路径：</span><span class="sxs-lookup"><span data-stu-id="9fab7-174">Follow these steps to enable the deployment path:</span></span>
1. <span data-ttu-id="9fab7-175">转到[适用于企业的 Microsoft Store](https://businessstore.microsoft.com)，然后使用 Azure Active Directory 身份登录。</span><span class="sxs-lookup"><span data-stu-id="9fab7-175">Go to the [Microsoft Store for Business](https://businessstore.microsoft.com) and sign in using an Azure Active Directory identity.</span></span>

1. <span data-ttu-id="9fab7-176">转到“**管理 – 设置**”。</span><span class="sxs-lookup"><span data-stu-id="9fab7-176">Go to **Manage – Settings**.</span></span> <span data-ttu-id="9fab7-177">在“**购物体验**”下打开“**显示离线应用**”。</span><span class="sxs-lookup"><span data-stu-id="9fab7-177">Turn on **Show offline apps** under **Shopping experience**.</span></span> 
1. <span data-ttu-id="9fab7-178">转到“**为我的组购买**”，搜索 [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) 应用。</span><span class="sxs-lookup"><span data-stu-id="9fab7-178">Go to **shop for my group**, and search for [***Advanced Recovery Companion***](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8).</span></span>
1. <span data-ttu-id="9fab7-179">将“**许可证类型**”更改为“**脱机**”，然后选择“***管理***”。</span><span class="sxs-lookup"><span data-stu-id="9fab7-179">Change the **License Type** to ***offline***, and select **Manage**.</span></span>
1. <span data-ttu-id="9fab7-180">在“**下载脱机使用的程序包**”下，单击第二个蓝色“**下载**”按钮。</span><span class="sxs-lookup"><span data-stu-id="9fab7-180">Under **Download the package for offline use**, select the second blue **Download** button.</span></span> <span data-ttu-id="9fab7-181">确保文件扩展名为 *.appxbundle*。</span><span class="sxs-lookup"><span data-stu-id="9fab7-181">Make sure that the file extension is *.appxbundle*.</span></span>

    - <span data-ttu-id="9fab7-182">在此阶段，如果台式机可以访问互联网，请双击程序包以安装该应用程序。</span><span class="sxs-lookup"><span data-stu-id="9fab7-182">At this stage, if the Desktop PC has internet access, double-click the package to install the app.</span></span>


    - <span data-ttu-id="9fab7-183">如果目标计算机没有 Internet 连接，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="9fab7-183">If the desination PC has no internet connectivity, follow these steps:</span></span> 
       1. <span data-ttu-id="9fab7-184">选择解码的许可证，然后选择“**生成许可证**”。</span><span class="sxs-lookup"><span data-stu-id="9fab7-184">Select the unencoded license, and then select **Generate license**.</span></span>
       2. <span data-ttu-id="9fab7-185">在“**所需框架**”下，选择“**下载**”。</span><span class="sxs-lookup"><span data-stu-id="9fab7-185">Under **Required Frameworks**, select **Download**.</span></span>
       3. <span data-ttu-id="9fab7-186">使用 DISM 将软件包与依赖项和许可证一起应用。</span><span class="sxs-lookup"><span data-stu-id="9fab7-186">Use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="9fab7-187">从管理员命令提示符运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9fab7-187">From an administrator command prompt, run the following command:</span></span>

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
            > [!NOTE]
            > <span data-ttu-id="9fab7-188">此代码示例中的版本号可能与当前可用的版本不匹配。</span><span class="sxs-lookup"><span data-stu-id="9fab7-188">The version number in this code example may not match the currently available version.</span></span> <span data-ttu-id="9fab7-189">可能还选择了与给定示例不同的下载位置。</span><span class="sxs-lookup"><span data-stu-id="9fab7-189">You may have also chosen a different download location than in the example.</span></span> <span data-ttu-id="9fab7-190">根据需要对命令进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="9fab7-190">Make any changes to the command as needed.</span></span>

> [!TIP]
> <span data-ttu-id="9fab7-191">计划使用 Advanced Recovery Companion 脱机安装 FFU 时，下载刷写映像可能会很有用。</span><span class="sxs-lookup"><span data-stu-id="9fab7-191">When you plan to use Advanced Recovery Companion to install an FFU offline, it may be useful to download your flash image.</span></span> <span data-ttu-id="9fab7-192">[**下载 HoloLens 2 的最新映像**](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="9fab7-192">[**Download the current image for HoloLens 2**](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="9fab7-193">其他资源：</span><span class="sxs-lookup"><span data-stu-id="9fab7-193">Other resources:</span></span>
- [<span data-ttu-id="9fab7-194">分配离线应用</span><span class="sxs-lookup"><span data-stu-id="9fab7-194">Distribute offline apps</span></span>](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 
- [<span data-ttu-id="9fab7-195">DISM 应用程序包（.appx 或 .appxbundle）服务命令行选项</span><span class="sxs-lookup"><span data-stu-id="9fab7-195">DISM app package (.appx or .appxbundle) servicing command-line options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
