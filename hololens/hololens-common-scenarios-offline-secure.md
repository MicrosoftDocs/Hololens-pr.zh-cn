---
title: 常见方案 – 脱机安全 HoloLens 2
description: 了解如何使用 HoloLens 设备的预配设置脱机安全部署应用部署方案。
keywords: HoloLens， 管理， 脱机， 脱机安全
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 03003995f1e63708652955e6217e506d53555c1b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283413"
---
# <span data-ttu-id="43166-104">常见方案 – 脱机安全 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="43166-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="43166-105">概述</span><span class="sxs-lookup"><span data-stu-id="43166-105">Overview</span></span>

<span data-ttu-id="43166-106">本指南提供应用示例预配包的指南，该预配包将锁定 HoloLens 2，以在具有以下限制的安全环境中使用：</span><span class="sxs-lookup"><span data-stu-id="43166-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="43166-107">禁用 WiFi。</span><span class="sxs-lookup"><span data-stu-id="43166-107">Disable WiFi.</span></span>
-   <span data-ttu-id="43166-108">禁用蓝牙。</span><span class="sxs-lookup"><span data-stu-id="43166-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="43166-109">禁用麦克风。</span><span class="sxs-lookup"><span data-stu-id="43166-109">Disable Microphones.</span></span>
-   <span data-ttu-id="43166-110">阻止添加或删除预配包。</span><span class="sxs-lookup"><span data-stu-id="43166-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="43166-111">任何用户都不得启用上述任何受限组件。</span><span class="sxs-lookup"><span data-stu-id="43166-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="43166-112">准备</span><span class="sxs-lookup"><span data-stu-id="43166-112">Prepare</span></span>

<span data-ttu-id="43166-113">Windows 10 电脑设置</span><span class="sxs-lookup"><span data-stu-id="43166-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="43166-114">[将最新的 HoloLens 2 操作系统文件直接](https://aka.ms/hololens2download) 下载到电脑。</span><span class="sxs-lookup"><span data-stu-id="43166-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="43166-115">内部版本 19041.1117 及以上版本中包含对此配置的支持。</span><span class="sxs-lookup"><span data-stu-id="43166-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="43166-116">将高级恢复助手 (ARC) 工具 [从 Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 下载到电脑</span><span class="sxs-lookup"><span data-stu-id="43166-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="43166-117">将最新的 Windows 配置设计器 ([WCD) ](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 从 Microsoft Store 下载到电脑。</span><span class="sxs-lookup"><span data-stu-id="43166-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="43166-118">[下载OfflineSecureHL2_Sample文件生成](https://aka.ms/HoloLensDocs-SecureOfflineSample) PPKG 的文件文件夹。</span><span class="sxs-lookup"><span data-stu-id="43166-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="43166-119">为 [PPKG 部署准备脱机业务线应用程序](app-deploy-provisioning-package.md)。</span><span class="sxs-lookup"><span data-stu-id="43166-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="43166-120">配置</span><span class="sxs-lookup"><span data-stu-id="43166-120">Configure</span></span>

<span data-ttu-id="43166-121">生成安全配置预配包</span><span class="sxs-lookup"><span data-stu-id="43166-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="43166-122">在电脑上启动 WCD 工具。</span><span class="sxs-lookup"><span data-stu-id="43166-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="43166-123">选择 **"文件>打开项目。**</span><span class="sxs-lookup"><span data-stu-id="43166-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="43166-124">导航到之前保存的OfflineSecureHL2_Sample的位置，然后选择：OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="43166-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="43166-125">项目应打开，现在应该具有可用自定义项列表：</span><span class="sxs-lookup"><span data-stu-id="43166-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中打开的配置包的屏幕截图](images/offline-secure-sample-wcd.png)

<span data-ttu-id="43166-127">在此预配包中设置的配置：</span><span class="sxs-lookup"><span data-stu-id="43166-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="43166-128">项目</span><span class="sxs-lookup"><span data-stu-id="43166-128">Item</span></span>                                                |     <span data-ttu-id="43166-129">设置</span><span class="sxs-lookup"><span data-stu-id="43166-129">Setting</span></span>                       |     <span data-ttu-id="43166-130">描述</span><span class="sxs-lookup"><span data-stu-id="43166-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="43166-131">帐户/用户</span><span class="sxs-lookup"><span data-stu-id="43166-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="43166-132">本地用户名&密码</span><span class="sxs-lookup"><span data-stu-id="43166-132">Local User Name & Password</span></span>    |     <span data-ttu-id="43166-133">对于这些脱机设备，需要由设备的所有用户设置和共享单个用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="43166-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="43166-134">First Experience / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="43166-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="43166-135">True</span><span class="sxs-lookup"><span data-stu-id="43166-135">True</span></span>                          |     <span data-ttu-id="43166-136">仅在初始设备设置期间跳过校准</span><span class="sxs-lookup"><span data-stu-id="43166-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="43166-137">First Experience / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="43166-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="43166-138">True</span><span class="sxs-lookup"><span data-stu-id="43166-138">True</span></span>                          |     <span data-ttu-id="43166-139">在初始设备设置期间跳过设备培训</span><span class="sxs-lookup"><span data-stu-id="43166-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="43166-140">First Experience / HoloLens / WiFi</span><span class="sxs-lookup"><span data-stu-id="43166-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="43166-141">True</span><span class="sxs-lookup"><span data-stu-id="43166-141">True</span></span>                          |     <span data-ttu-id="43166-142">在Wi-Fi安装期间跳过配置</span><span class="sxs-lookup"><span data-stu-id="43166-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="43166-143">Policies/Connectivity/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="43166-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="43166-144">否</span><span class="sxs-lookup"><span data-stu-id="43166-144">No</span></span>                            |     <span data-ttu-id="43166-145">禁用Bluetooth</span><span class="sxs-lookup"><span data-stu-id="43166-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="43166-146">策略/体验/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="43166-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="43166-147">否</span><span class="sxs-lookup"><span data-stu-id="43166-147">No</span></span>                            |     <span data-ttu-id="43166-148">禁用 Cortana (消除潜在的问题，因为麦克风在) </span><span class="sxs-lookup"><span data-stu-id="43166-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="43166-149">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="43166-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="43166-150">是</span><span class="sxs-lookup"><span data-stu-id="43166-150">Yes</span></span>                           |     <span data-ttu-id="43166-151">禁用麦克风</span><span class="sxs-lookup"><span data-stu-id="43166-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="43166-152">Policies/Privacy/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="43166-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="43166-153">强制拒绝</span><span class="sxs-lookup"><span data-stu-id="43166-153">Force deny</span></span>                    |     <span data-ttu-id="43166-154">阻止应用尝试访问位置 (消除潜在的问题，因为禁用了位置跟踪) </span><span class="sxs-lookup"><span data-stu-id="43166-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="43166-155">Policies/Privacy/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="43166-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="43166-156">强制拒绝</span><span class="sxs-lookup"><span data-stu-id="43166-156">Force deny</span></span>                    |     <span data-ttu-id="43166-157">阻止应用尝试访问麦克风 (消除潜在的问题，因为麦克风已被禁用) </span><span class="sxs-lookup"><span data-stu-id="43166-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="43166-158">Policies/Security/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="43166-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="43166-159">否</span><span class="sxs-lookup"><span data-stu-id="43166-159">No</span></span>                            |     <span data-ttu-id="43166-160">阻止任何人添加可能尝试覆盖锁定策略的预配包。</span><span class="sxs-lookup"><span data-stu-id="43166-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="43166-161">Policies/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="43166-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="43166-162">否</span><span class="sxs-lookup"><span data-stu-id="43166-162">No</span></span>                            |     <span data-ttu-id="43166-163">阻止任何人删除此锁定的预配包。</span><span class="sxs-lookup"><span data-stu-id="43166-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="43166-164">Policies/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="43166-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="43166-165">否</span><span class="sxs-lookup"><span data-stu-id="43166-165">No</span></span>                            |     <span data-ttu-id="43166-166">阻止设备尝试跟踪位置数据。</span><span class="sxs-lookup"><span data-stu-id="43166-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="43166-167">Policies/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="43166-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="43166-168">否</span><span class="sxs-lookup"><span data-stu-id="43166-168">No</span></span>                            |     <span data-ttu-id="43166-169">禁用Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="43166-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="43166-170">在"运行时设置"下 **，选择帐户/用户/用户名：Holo/Password**</span><span class="sxs-lookup"><span data-stu-id="43166-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="43166-171">记下密码并重置（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="43166-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="43166-172">导航到 UniversalAppInstall /UserContextApp，并配置你要部署到这些设备的 [LOB](app-deploy-provisioning-package.md) 应用。</span><span class="sxs-lookup"><span data-stu-id="43166-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中添加应用位置的屏幕截图。](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="43166-174">完成后，选择"导出"按钮并按照所有提示操作，直到创建预配包。</span><span class="sxs-lookup"><span data-stu-id="43166-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD 中此程序包的"导出"按钮的屏幕截图。](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="43166-176">部署</span><span class="sxs-lookup"><span data-stu-id="43166-176">Deploy</span></span>

1. <span data-ttu-id="43166-177">通过 USB 电缆将 HL2 连接到 Windows 10 电脑。</span><span class="sxs-lookup"><span data-stu-id="43166-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="43166-178">启动 ARC 工具并选择 **HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="43166-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="43166-179">On the next screen select **Manual package selection**.</span><span class="sxs-lookup"><span data-stu-id="43166-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="43166-180">导航到之前下载的 .ffu 文件，然后选择"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="43166-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="43166-181">在"警告"页上，选择"**继续"。**</span><span class="sxs-lookup"><span data-stu-id="43166-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="43166-182">等待 ARC 工具完成 HoloLens 2 操作系统安装。</span><span class="sxs-lookup"><span data-stu-id="43166-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="43166-183">设备完成安装和启动备份后，从电脑导航到文件资源管理器，将之前保存的 PPKG 文件复制到设备文件夹。</span><span class="sxs-lookup"><span data-stu-id="43166-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![文件资源管理器窗口中电脑上的 PPKG 文件。](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="43166-185">在 HoloLens 2 上，按以下按钮组合以运行预配包 **：同时点击** 音量降低和 **电源** 按钮。</span><span class="sxs-lookup"><span data-stu-id="43166-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="43166-186">系统将提示你应用预配包，选择"确认 **"**</span><span class="sxs-lookup"><span data-stu-id="43166-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="43166-187">设置包完成后，选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="43166-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="43166-188">然后，系统将提示你使用共享的本地帐户和密码登录设备。</span><span class="sxs-lookup"><span data-stu-id="43166-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="43166-189">维护</span><span class="sxs-lookup"><span data-stu-id="43166-189">Maintain</span></span>

<span data-ttu-id="43166-190">通过此配置，建议重新启动上述过程，使用 ARC 工具重新将设备放大并应用新的 PPKG，以对操作系统和/或应用程序进行 (更新) 。</span><span class="sxs-lookup"><span data-stu-id="43166-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

