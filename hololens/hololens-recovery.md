---
title: 重启、重置或恢复 HoloLens
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: 2c7fa9b8c86900c89bbced1a10f3e9e2bc69bcd0
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857760"
---
# <span data-ttu-id="31ec7-104">重启、重置或恢复 HoloLens</span><span class="sxs-lookup"><span data-stu-id="31ec7-104">Restart, reset, or recover HoloLens</span></span>

## <span data-ttu-id="31ec7-105">对设备充电</span><span class="sxs-lookup"><span data-stu-id="31ec7-105">Charging the device</span></span>

<span data-ttu-id="31ec7-106">在开始任何故障排除程序之前，如果可能，请确保设备电量至少在 20% 到 40% 之间。</span><span class="sxs-lookup"><span data-stu-id="31ec7-106">Before starting any troubleshooting procedure, if possible, ensure that your device is charged at least between 20% and 40%.</span></span>

<span data-ttu-id="31ec7-107">请确保使用 HoloLens2 设备附带的充电器和 USB Type-C 电缆。</span><span class="sxs-lookup"><span data-stu-id="31ec7-107">Please ensure you are using the charger and the USB Type-C cables that come with the HoloLens2 device.</span></span> <span data-ttu-id="31ec7-108">如果没有，请确保所用的充电器支持至少 15W 的功率。</span><span class="sxs-lookup"><span data-stu-id="31ec7-108">In case they are not available ensure the charger available can support at least 15W of power.</span></span>

> [!NOTE]
> <span data-ttu-id="31ec7-109">如有可能，请勿使用电脑通过 USB 对设备进行充电，因为这将导致充电非常慢。</span><span class="sxs-lookup"><span data-stu-id="31ec7-109">If possible, do not use a PC to charge the device over USB as this will provide a very slow charge.</span></span>

<span data-ttu-id="31ec7-110">如果设备已正确启动且运行，有三种不同的方法可用来检查电池的电量。</span><span class="sxs-lookup"><span data-stu-id="31ec7-110">If the device is correctly booted and running there are three different ways of checking the charge of your battery.</span></span>

1. <span data-ttu-id="31ec7-111">从 HoloLens 设备 UI 的主菜单。</span><span class="sxs-lookup"><span data-stu-id="31ec7-111">From the main menu of the HoloLens Device UI.</span></span>
2. <span data-ttu-id="31ec7-112">使用靠近电源按钮的 LED（对于 40% 的电量，应该可看到至少两个稳定的 LED）。</span><span class="sxs-lookup"><span data-stu-id="31ec7-112">Using the LED close to the power button (for 40% you should see at least two solid LEDS).</span></span>
3. <span data-ttu-id="31ec7-113">在主机上，打开“文件资源管理器”窗口，然后在左侧的“此电脑”下查找 HoloLens 2 设备。</span><span class="sxs-lookup"><span data-stu-id="31ec7-113">On your Host PC open File Explorer window and look for your HoloLens 2 device on left side under “This PC”.</span></span>
    
      <span data-ttu-id="31ec7-114">a.</span><span class="sxs-lookup"><span data-stu-id="31ec7-114">a.</span></span> <span data-ttu-id="31ec7-115">右键单击设备的名称，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="31ec7-115">Right click on the name of the device and select properties.</span></span> <span data-ttu-id="31ec7-116">此时将出现一个对话框，显示你设备的电池电量。</span><span class="sxs-lookup"><span data-stu-id="31ec7-116">A dialog will appear showing the battery level for your device.</span></span>

![HoloLens 2 重置恢复](images/ResetRecovery2.png)

<span data-ttu-id="31ec7-118">如果设备无法启动到启动菜单，请记下 LED 和主机上的和枚举情况，然后按照故障排除指南 (https://docs.microsoft.com/hololens/hololens-troubleshooting) 进行操作。</span><span class="sxs-lookup"><span data-stu-id="31ec7-118">If the device cannot be booted to the Startup Menu, please take note of the LEDs and enumeration on the host PC and follow the troubleshooting guide (https://docs.microsoft.com/hololens/hololens-troubleshooting).</span></span> <span data-ttu-id="31ec7-119">如果设备的状态不符合故障排除指南中列出的任何状态，请执行硬重置程序\*\*\*\*，且不是将设备重新连接到主机，而是将其连接到电源。</span><span class="sxs-lookup"><span data-stu-id="31ec7-119">In case the state of the device does not fall in any of the states listed in the troubleshooting guide, execute the **hard reset procedure** without reconnecting the device to your host PC, but connect it instead to the power supply.</span></span> <span data-ttu-id="31ec7-120">至少等待一小时，让设备充电。</span><span class="sxs-lookup"><span data-stu-id="31ec7-120">Wait for at least one hour for the device to charge.</span></span>

## <span data-ttu-id="31ec7-121">重置设备</span><span class="sxs-lookup"><span data-stu-id="31ec7-121">Reset the device</span></span>

<span data-ttu-id="31ec7-122">在某些情况下，客户可能需要在不使用 SW UI 的情况下手动重置设备。</span><span class="sxs-lookup"><span data-stu-id="31ec7-122">Under certain circumstances the customer may be required to manually reset the device without using the SW UI.</span></span> 

### <span data-ttu-id="31ec7-123">标准程序</span><span class="sxs-lookup"><span data-stu-id="31ec7-123">Standard procedure</span></span>
1. <span data-ttu-id="31ec7-124">拔出 Type-C 电缆，以断开设备与电源或主机的连接。</span><span class="sxs-lookup"><span data-stu-id="31ec7-124">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="31ec7-125">按住电源按钮\*\*\*\* 15 秒。</span><span class="sxs-lookup"><span data-stu-id="31ec7-125">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="31ec7-126">所有 LED 均应熄灭。</span><span class="sxs-lookup"><span data-stu-id="31ec7-126">All LEDs should be off.</span></span>

3. <span data-ttu-id="31ec7-127">等待 2-3 秒，然后短按电源按钮\*\*\*\*，电源按钮旁的 LED 将亮起，设备将开始启动。</span><span class="sxs-lookup"><span data-stu-id="31ec7-127">Wait 2-3 seconds and Short press the **power button**, the LEDs close to the power button will light up and the device will start to boot.</span></span> 

4. <span data-ttu-id="31ec7-128">将设备连接到主机，打开设备管理器（对于 Windows 10，请按“Windows”键\*\*\*\*，然后按“X”\*\*\*\* 键，然后单击“设备管理器”），并确保设备正确枚举为 Microsoft HoloLens，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="31ec7-128">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below:</span></span>

![HoloLens 2 MicrosoftHoloLens恢复](images/MicrosoftHoloLens_DeviceManager.png)

### <span data-ttu-id="31ec7-130">硬重置程序</span><span class="sxs-lookup"><span data-stu-id="31ec7-130">Hard-reset procedure</span></span>

<span data-ttu-id="31ec7-131">如果标准重置程序不起作用，可使用硬重置程序。</span><span class="sxs-lookup"><span data-stu-id="31ec7-131">If the standard reset procedure does not work, you can use the hard-reset procedure.</span></span>

1. <span data-ttu-id="31ec7-132">拔出 Type-C 电缆，以断开设备与电源或主机的连接。</span><span class="sxs-lookup"><span data-stu-id="31ec7-132">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span>

2. <span data-ttu-id="31ec7-133">按住下调音量按钮 + 电源按钮\*\*\*\* 15 秒钟。</span><span class="sxs-lookup"><span data-stu-id="31ec7-133">Hold **volume down + power button** for 15 seconds.</span></span>

3. <span data-ttu-id="31ec7-134">设备将自动重启。</span><span class="sxs-lookup"><span data-stu-id="31ec7-134">The device will automatically reboot.</span></span> 

4. <span data-ttu-id="31ec7-135">将设备连接到主机，打开设备管理器（对于 Windows 10，请按“Windows”键\*\*\*\*，然后按“X”\*\*\*\* 键，然后单击“设备管理器”），并确保设备正确枚举为 Microsoft HoloLens，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="31ec7-135">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the pictures below.</span></span>

![HoloLens 2 MicrosoftHoloLens恢复](images/MicrosoftHoloLens_DeviceManager.png)

## <span data-ttu-id="31ec7-137">对设备进行干净重刷</span><span class="sxs-lookup"><span data-stu-id="31ec7-137">Clean reflash the device</span></span>

<span data-ttu-id="31ec7-138">在特别情况下，可能需要对设备进行干净刷写。</span><span class="sxs-lookup"><span data-stu-id="31ec7-138">In extraordinary situations you may be required to clean flash the device.</span></span> <span data-ttu-id="31ec7-139">对 HoloLens2 设备进行重刷的方法共有两种。</span><span class="sxs-lookup"><span data-stu-id="31ec7-139">There are two ways to reflash a HoloLens2 device.</span></span> <span data-ttu-id="31ec7-140">所有重刷程序都要求[从 Windows Store 安装 Advanced Recovery Companion 应用](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。</span><span class="sxs-lookup"><span data-stu-id="31ec7-140">For all reflashing procedures you will be required to [install the Advanced Recovery Companion app from the Windows Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span> <span data-ttu-id="31ec7-141">如果重置设备，则将擦除所有个人数据、应用和设置，包括 TPM 重置。</span><span class="sxs-lookup"><span data-stu-id="31ec7-141">If you reset your device, all your personal data, apps, and settings will be erased, including TPM reset.</span></span>

<span data-ttu-id="31ec7-142">Advanced Recovery Companion 目前已设置为下载 [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004) 的功能发布内部版本。若要下载最新的 HoloLens 2 FFU 以通过 Advanced Recovery Companion 来刷写设备，可从[此处](https://aka.ms/hololens2download)下载。</span><span class="sxs-lookup"><span data-stu-id="31ec7-142">Advanced Recovery Companion is currently set to download the feature release build for [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004), if you would like to download the latest HoloLens 2 FFU to flash your device via Advanced Recovery Companion then you may download it from [here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="31ec7-143">此处的 FFU 会实时更新，并将与最新的通用内部版本匹配。</span><span class="sxs-lookup"><span data-stu-id="31ec7-143">This is kept up-to-date and will match the latest generally available build.</span></span> 

<span data-ttu-id="31ec7-144">开始刷写程序之前，请确保已在 Windows 10 电脑上安装并运行该应用，并已准备好检测设备。</span><span class="sxs-lookup"><span data-stu-id="31ec7-144">Before starting the flashing procedure make sure the app is installed and running on your Windows 10 PC and ready to detect the device.</span></span>

![HoloLens 2 干净重刷](images/ARC1.png)

### <span data-ttu-id="31ec7-146">正常程序</span><span class="sxs-lookup"><span data-stu-id="31ec7-146">Normal procedure</span></span>

1. <span data-ttu-id="31ec7-147">在 HoloLens 设备运行期间，将其连接到你先前启动了 Advanced Recovery Companion 应用的 Windows 10 电脑。</span><span class="sxs-lookup"><span data-stu-id="31ec7-147">While the HoloLens device is running, connect it to your Windows 10 PC where you previously launched the Advanced Recovery Companion App.</span></span>

2. <span data-ttu-id="31ec7-148">系统将自动检测设备，Advanced Recovery Companion 应用的 UI 将更新为如下所示：</span><span class="sxs-lookup"><span data-stu-id="31ec7-148">The device will automatically be detected and the Advanced Recovery Companion App UI will update as follows:</span></span>

![HoloLens 2 干净重刷](images/ARC2.png)

3. <span data-ttu-id="31ec7-150">在 Advanced Recovery Companion 应用 UI 中选择 HoloLens2 设备，然后按照说明完成刷写。</span><span class="sxs-lookup"><span data-stu-id="31ec7-150">Select the HoloLens2 device in the Advanced Recovery Companion App UI and follow the instructions to complete the flashing.</span></span>

### <span data-ttu-id="31ec7-151">手动程序</span><span class="sxs-lookup"><span data-stu-id="31ec7-151">Manual procedure</span></span>

<span data-ttu-id="31ec7-152">如果设备未正确启动，可能需要将 HoloLens 2 设备置于恢复模式。</span><span class="sxs-lookup"><span data-stu-id="31ec7-152">If the device does not boot correctly you may need to put the HoloLens 2 device in Recovery mode.</span></span>

1. <span data-ttu-id="31ec7-153">拔出 Type-C 电缆，以断开设备与电源或主机的连接。</span><span class="sxs-lookup"><span data-stu-id="31ec7-153">Disconnect the device from the power supply or the host PC by unplugging the Type-C cable.</span></span> 

2. <span data-ttu-id="31ec7-154">按住电源按钮\*\*\*\* 15 秒。</span><span class="sxs-lookup"><span data-stu-id="31ec7-154">Press and hold the **power button** for 15 seconds.</span></span> <span data-ttu-id="31ec7-155">所有 LED 均应熄灭。</span><span class="sxs-lookup"><span data-stu-id="31ec7-155">All LEDs should turn off.</span></span> 

3. <span data-ttu-id="31ec7-156">在按下上调音量按钮的同时\*\*\*\*，按下并释放电源按钮\*\*\*\* 以启动设备。</span><span class="sxs-lookup"><span data-stu-id="31ec7-156">While pressing the **volume up button**, press and release the **power button** to boot the device.</span></span> <span data-ttu-id="31ec7-157">请等待 15 秒钟，然后再释放上调音量按钮。</span><span class="sxs-lookup"><span data-stu-id="31ec7-157">Wait 15 seconds before releasing the volume up button.</span></span> <span data-ttu-id="31ec7-158">在设备上的 5 个 LED 中，只有中间的 LED 会亮起。</span><span class="sxs-lookup"><span data-stu-id="31ec7-158">Out of the 5 LEDs on the device, only the middle LED will light up.</span></span>

4. <span data-ttu-id="31ec7-159">将设备连接到主机，打开设备管理器（对于 Windows 10，请按“Windows”键\*\*\*\*，然后按“X”\*\*\*\* 键，然后单击“设备管理器”），并确保设备正确枚举为 Microsoft HoloLens，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="31ec7-159">Connect the device to the host PC, open Device Manager (for Windows 10 press the **“Windows” key** and then the **“x” key** and click on “Device Manager”) and make sure the device enumerates correctly as Microsoft HoloLens as shown in the image below.</span></span>

![HoloLens 2 MicrosoftHoloLens恢复](images/MicrosoftHoloLensRecovery.png)

5. <span data-ttu-id="31ec7-161">系统将自动检测设备，Advanced Recovery Companion 应用的 UI 将更新为如下所示：</span><span class="sxs-lookup"><span data-stu-id="31ec7-161">The device will be automatically detected, and the Advanced Recovery Companion app UI will update as follows:</span></span>

![HoloLens 2 干净重刷](images/ARC2.png)

6. <span data-ttu-id="31ec7-163">在 Advanced Recovery Companion 应用 UI 中选择 HoloLens 2 设备，然后按照说明完成刷写。</span><span class="sxs-lookup"><span data-stu-id="31ec7-163">Select the HoloLens 2 device in the Advanced Recovery Companion app UI and follow the instructions to complete the flashing.</span></span>

## <span data-ttu-id="31ec7-164">在不使用应用商店的情况下下载 ARC</span><span class="sxs-lookup"><span data-stu-id="31ec7-164">Downloading ARC without using the app store</span></span>

<span data-ttu-id="31ec7-165">如果 IT 环境阻止使用 Windows Store 应用或限制对该零售商店的访问，IT 管理员可通过其他“脱机”部署路径提供此应用。</span><span class="sxs-lookup"><span data-stu-id="31ec7-165">If an IT environment prevents the use of the Windows Store app or limits access to the retail store, IT administrators can make this app available through other ‘offline’ deployment paths.</span></span> 

- <span data-ttu-id="31ec7-166">此流程也可用于其他应用，如步骤 2 所示。</span><span class="sxs-lookup"><span data-stu-id="31ec7-166">This process may also be used for other apps, as seen in step 2.</span></span> <span data-ttu-id="31ec7-167">本指南将重点介绍 Advanced Recovery Companion，对于其他脱机应用则可能需要稍作修改。</span><span class="sxs-lookup"><span data-stu-id="31ec7-167">This guide will focus on Advanced Recovery Companion, but my be modified for other offline apps.</span></span>  

<span data-ttu-id="31ec7-168">可通过以下步骤启用此部署路径：</span><span class="sxs-lookup"><span data-stu-id="31ec7-168">This deployment path can be enabled with the following steps:</span></span>
1.  <span data-ttu-id="31ec7-169">转到[适用于企业的 Microsoft Store](https://businessstore.microsoft.com) 网站并使用 Azure AD 标识登录。</span><span class="sxs-lookup"><span data-stu-id="31ec7-169">Go to the [Store For Business website](https://businessstore.microsoft.com) and sign-in with an Azure AD identity.</span></span>
1.  <span data-ttu-id="31ec7-170">转到“管理”–“设置”\*\*\*\*，然后打开“购物体验”下的“显示脱机应用”\*\*\*\*\*\*\*\*，详见 https://businessstore.microsoft.com/manage/settings/shop</span><span class="sxs-lookup"><span data-stu-id="31ec7-170">Go to **Manage – Settings**, and turn on **Show offline apps** under **Shopping experience** as described at https://businessstore.microsoft.com/manage/settings/shop</span></span> 
1.  <span data-ttu-id="31ec7-171">转到“为我的组购买”\*\*\*\*，搜索 [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) 应用。</span><span class="sxs-lookup"><span data-stu-id="31ec7-171">Go to **shop for my group** and search for the [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) app.</span></span>
1.  <span data-ttu-id="31ec7-172">将“许可证类型”\*\*\*\* 框更改为“脱机”，然后单击“管理”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="31ec7-172">Change the **License Type** box to offline and click **Manage**.</span></span>
1.  <span data-ttu-id="31ec7-173">在“下载脱机使用的程序包”下，单击第二个蓝色“下载”\*\*\*\* 按钮。</span><span class="sxs-lookup"><span data-stu-id="31ec7-173">Under Download the package for offline use click the second blue **“Download”** button .</span></span> <span data-ttu-id="31ec7-174">确保文件扩展名为 .appxbundle。</span><span class="sxs-lookup"><span data-stu-id="31ec7-174">Ensure the file extension is .appxbundle.</span></span>
1.  <span data-ttu-id="31ec7-175">在这个阶段，如果台式电脑可以访问 Internet，只需双击并安装。</span><span class="sxs-lookup"><span data-stu-id="31ec7-175">At this stage, if the Desktop PC has Internet access, simply double click and install.</span></span> 
1.  <span data-ttu-id="31ec7-176">IT 管理员也可以通过 System Center Configuration Manager (SCCM) 或 Intune 分发此应用。</span><span class="sxs-lookup"><span data-stu-id="31ec7-176">The IT administrator can also distribute this app through System Center Configuration Manager (SCCM) or Intune.</span></span>
1.  <span data-ttu-id="31ec7-177">如果目标电脑没有 Internet 连接，则需要额外执行一些步骤：</span><span class="sxs-lookup"><span data-stu-id="31ec7-177">If the target PC has no Internet connectivity, some additional steps are needed:</span></span> 
    1.  <span data-ttu-id="31ec7-178">选择未编码的许可证并单击“生成许可证”，然后在“所需框架”下单击“下载”。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="31ec7-178">Select the unencoded license and click **“Generate license”** and under **“Required Frameworks”** click **“Download.”**</span></span> 
    1.  <span data-ttu-id="31ec7-179">无法访问 Internet 的电脑将需要使用 DISM 来应用具有依赖项的程序包和许可证。</span><span class="sxs-lookup"><span data-stu-id="31ec7-179">PCs without internet access will need to use DISM to apply the package with the dependency and license.</span></span> <span data-ttu-id="31ec7-180">在管理员命令提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="31ec7-180">In an administrator command prompt, type:</span></span>

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> <span data-ttu-id="31ec7-181">此代码示例中的版本号可能与当前可用的版本不匹配。</span><span class="sxs-lookup"><span data-stu-id="31ec7-181">The version number in this code example may not match the currently avalible version.</span></span> <span data-ttu-id="31ec7-182">你可能还选择了与给定示例不同的下载位置。</span><span class="sxs-lookup"><span data-stu-id="31ec7-182">You may have also choosen a different download location than in the example given.</span></span> <span data-ttu-id="31ec7-183">请确保根据需要进行更改。</span><span class="sxs-lookup"><span data-stu-id="31ec7-183">Please make sure to make any changes as needed.</span></span>

> [!TIP]
> <span data-ttu-id="31ec7-184">在计划使用 Advanced Recovery Companion 来脱机安装 FFU 时，下载刷写映像可能会很有用，这里是 [HoloLens 2 的当前映像](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="31ec7-184">When planning to use Advanced Recovery Companion to install an ffu offline it may be useful to download your flashing image to be availible, here is the [current image for HoloLens 2](https://aka.ms/hololens2download).</span></span> 

<span data-ttu-id="31ec7-185">其他资源：</span><span class="sxs-lookup"><span data-stu-id="31ec7-185">Other resources:</span></span>
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


