---
title: 常见方案–脱机安全 HoloLens 2
description: 了解如何设置适用于 HoloLens 设备的脱机安全部署和应用部署方案。
keywords: HoloLens、管理、脱机、脱机安全
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
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308172"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="c47a7-104">常见方案–脱机安全 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c47a7-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="c47a7-105">概述</span><span class="sxs-lookup"><span data-stu-id="c47a7-105">Overview</span></span>

<span data-ttu-id="c47a7-106">本指南提供了有关应用示例预配包的指导，该设置包将锁定 HoloLens 2 以便在安全环境中使用，但有以下限制：</span><span class="sxs-lookup"><span data-stu-id="c47a7-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="c47a7-107">禁用 WiFi。</span><span class="sxs-lookup"><span data-stu-id="c47a7-107">Disable WiFi.</span></span>
-   <span data-ttu-id="c47a7-108">禁用蓝牙。</span><span class="sxs-lookup"><span data-stu-id="c47a7-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="c47a7-109">禁用麦克风。</span><span class="sxs-lookup"><span data-stu-id="c47a7-109">Disable Microphones.</span></span>
-   <span data-ttu-id="c47a7-110">阻止添加或删除预配包。</span><span class="sxs-lookup"><span data-stu-id="c47a7-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="c47a7-111">任何用户都不能启用上述任何受限制的组件。</span><span class="sxs-lookup"><span data-stu-id="c47a7-111">No user can enable any of the above restricted components.</span></span>

## <a name="prepare"></a><span data-ttu-id="c47a7-112">准备</span><span class="sxs-lookup"><span data-stu-id="c47a7-112">Prepare</span></span>

<span data-ttu-id="c47a7-113">Windows 10 电脑安装程序</span><span class="sxs-lookup"><span data-stu-id="c47a7-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="c47a7-114">将[最新的 HoloLens 2 OS 文件直接下载](https://aka.ms/hololens2download)到 PC。</span><span class="sxs-lookup"><span data-stu-id="c47a7-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="c47a7-115">版本19041.1117 及更高版本中包含了对此配置的支持。</span><span class="sxs-lookup"><span data-stu-id="c47a7-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="c47a7-116">[从 Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)到 PC 下载/安装高级恢复助理 (ARC) 工具</span><span class="sxs-lookup"><span data-stu-id="c47a7-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="c47a7-117">下载/安装最新的 [Windows 配置设计器 (WCD) ](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 工具从 MICROSOFT STORE 到 PC。</span><span class="sxs-lookup"><span data-stu-id="c47a7-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="c47a7-118">[下载包含项目文件的 OfflineSecureHL2_Sample 文件夹](https://aka.ms/HoloLensDocs-SecureOfflineSample) 以生成 PPKG。</span><span class="sxs-lookup"><span data-stu-id="c47a7-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="c47a7-119">准备 [PPKG 部署的脱机业务线应用程序](app-deploy-provisioning-package.md)。</span><span class="sxs-lookup"><span data-stu-id="c47a7-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="c47a7-120">配置</span><span class="sxs-lookup"><span data-stu-id="c47a7-120">Configure</span></span>

<span data-ttu-id="c47a7-121">构建安全配置预配包</span><span class="sxs-lookup"><span data-stu-id="c47a7-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="c47a7-122">在电脑上启动 WCD 工具。</span><span class="sxs-lookup"><span data-stu-id="c47a7-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="c47a7-123">选择 " **文件-> 打开项目**"。</span><span class="sxs-lookup"><span data-stu-id="c47a7-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="c47a7-124">导航到之前保存的 OfflineSecureHL2_Sample 文件夹的位置，并选择： OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="c47a7-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="c47a7-125">项目应会打开，此时应会显示一个可用自定义项列表：</span><span class="sxs-lookup"><span data-stu-id="c47a7-125">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c47a7-126">![在 WCD 中打开的配置包的屏幕截图](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="c47a7-126">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="c47a7-127">此预配包中设置的配置：</span><span class="sxs-lookup"><span data-stu-id="c47a7-127">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="c47a7-128">项</span><span class="sxs-lookup"><span data-stu-id="c47a7-128">Item</span></span>                                                |     <span data-ttu-id="c47a7-129">设置</span><span class="sxs-lookup"><span data-stu-id="c47a7-129">Setting</span></span>                       |     <span data-ttu-id="c47a7-130">描述</span><span class="sxs-lookup"><span data-stu-id="c47a7-130">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="c47a7-131">帐户/用户</span><span class="sxs-lookup"><span data-stu-id="c47a7-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="c47a7-132">本地用户名 & 密码</span><span class="sxs-lookup"><span data-stu-id="c47a7-132">Local User Name & Password</span></span>    |     <span data-ttu-id="c47a7-133">对于这些脱机设备，需要为设备的所有用户设置和共享单个用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="c47a7-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="c47a7-134">首次体验/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="c47a7-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="c47a7-135">True</span><span class="sxs-lookup"><span data-stu-id="c47a7-135">True</span></span>                          |     <span data-ttu-id="c47a7-136">仅在初始设备安装过程中跳过校准</span><span class="sxs-lookup"><span data-stu-id="c47a7-136">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="c47a7-137">首次体验/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="c47a7-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="c47a7-138">True</span><span class="sxs-lookup"><span data-stu-id="c47a7-138">True</span></span>                          |     <span data-ttu-id="c47a7-139">初始设备安装过程中跳过设备培训</span><span class="sxs-lookup"><span data-stu-id="c47a7-139">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="c47a7-140">首次体验/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="c47a7-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="c47a7-141">True</span><span class="sxs-lookup"><span data-stu-id="c47a7-141">True</span></span>                          |     <span data-ttu-id="c47a7-142">初始设备安装过程中跳过 Wi-Fi 配置</span><span class="sxs-lookup"><span data-stu-id="c47a7-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="c47a7-143">策略/连接/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="c47a7-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="c47a7-144">否</span><span class="sxs-lookup"><span data-stu-id="c47a7-144">No</span></span>                            |     <span data-ttu-id="c47a7-145">禁用蓝牙</span><span class="sxs-lookup"><span data-stu-id="c47a7-145">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="c47a7-146">策略/体验/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="c47a7-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="c47a7-147">否</span><span class="sxs-lookup"><span data-stu-id="c47a7-147">No</span></span>                            |     <span data-ttu-id="c47a7-148">禁用 Cortana (以消除在禁用麦克风后出现的潜在问题) </span><span class="sxs-lookup"><span data-stu-id="c47a7-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="c47a7-149">策略/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="c47a7-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="c47a7-150">是</span><span class="sxs-lookup"><span data-stu-id="c47a7-150">Yes</span></span>                           |     <span data-ttu-id="c47a7-151">禁用麦克风</span><span class="sxs-lookup"><span data-stu-id="c47a7-151">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="c47a7-152">策略/隐私/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="c47a7-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="c47a7-153">强制拒绝</span><span class="sxs-lookup"><span data-stu-id="c47a7-153">Force deny</span></span>                    |     <span data-ttu-id="c47a7-154">阻止应用尝试访问位置数据 (以消除潜在问题，因为已禁用位置跟踪) </span><span class="sxs-lookup"><span data-stu-id="c47a7-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="c47a7-155">策略/隐私/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="c47a7-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="c47a7-156">强制拒绝</span><span class="sxs-lookup"><span data-stu-id="c47a7-156">Force deny</span></span>                    |     <span data-ttu-id="c47a7-157">阻止应用尝试访问麦克风 (以消除在禁用麦克风后出现的潜在问题) </span><span class="sxs-lookup"><span data-stu-id="c47a7-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="c47a7-158">策略/安全性/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="c47a7-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="c47a7-159">否</span><span class="sxs-lookup"><span data-stu-id="c47a7-159">No</span></span>                            |     <span data-ttu-id="c47a7-160">阻止任何人添加可能尝试替代锁定策略的预配包。</span><span class="sxs-lookup"><span data-stu-id="c47a7-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="c47a7-161">策略/安全性/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="c47a7-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="c47a7-162">否</span><span class="sxs-lookup"><span data-stu-id="c47a7-162">No</span></span>                            |     <span data-ttu-id="c47a7-163">阻止任何人删除此锁定的预配包。</span><span class="sxs-lookup"><span data-stu-id="c47a7-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="c47a7-164">策略/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="c47a7-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="c47a7-165">否</span><span class="sxs-lookup"><span data-stu-id="c47a7-165">No</span></span>                            |     <span data-ttu-id="c47a7-166">阻止设备尝试跟踪位置数据。</span><span class="sxs-lookup"><span data-stu-id="c47a7-166">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="c47a7-167">策略/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="c47a7-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="c47a7-168">否</span><span class="sxs-lookup"><span data-stu-id="c47a7-168">No</span></span>                            |     <span data-ttu-id="c47a7-169">禁用 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="c47a7-169">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="c47a7-170">在 "运行时设置" 下，选择 " **帐户/用户/用户名： Holo/Password**"。</span><span class="sxs-lookup"><span data-stu-id="c47a7-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="c47a7-171">记下密码，并根据需要重置。</span><span class="sxs-lookup"><span data-stu-id="c47a7-171">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="c47a7-172">导航到 UniversalAppInstall/UserContextApp，并配置将部署到这些设备 [的 LOB 应用](app-deploy-provisioning-package.md) 。</span><span class="sxs-lookup"><span data-stu-id="c47a7-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c47a7-173">![用于在 WCD 中添加应用程序的屏幕截图。](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="c47a7-173">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="c47a7-174">完成后，选择 "导出" 按钮并按照所有提示操作，直到创建了预配包。</span><span class="sxs-lookup"><span data-stu-id="c47a7-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c47a7-175">![WCD 中此包的 "导出" 按钮的屏幕截图。](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="c47a7-175">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="c47a7-176">部署</span><span class="sxs-lookup"><span data-stu-id="c47a7-176">Deploy</span></span>

1. <span data-ttu-id="c47a7-177">通过 USB 电缆将 HL2 连接到 Windows 10 电脑。</span><span class="sxs-lookup"><span data-stu-id="c47a7-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="c47a7-178">启动 "ARC" 工具，然后选择 " **HoloLens 2** "</span><span class="sxs-lookup"><span data-stu-id="c47a7-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2 清理刷新初始屏幕](images/ARC2.png)

1. <span data-ttu-id="c47a7-180">在下一个屏幕上，选择 " **手动包选择**"。</span><span class="sxs-lookup"><span data-stu-id="c47a7-180">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 ARC 信息屏幕](images/arc_device_info.png)

1. <span data-ttu-id="c47a7-182">导航到以前下载的 ffu 文件，然后选择 " **打开**"。</span><span class="sxs-lookup"><span data-stu-id="c47a7-182">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="c47a7-183">在警告页面上，选择 " **继续**"。</span><span class="sxs-lookup"><span data-stu-id="c47a7-183">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 ARC 警告屏幕](images/arc_warning.png)

1. <span data-ttu-id="c47a7-185">等待 ARC 工具完成 HoloLens 2 操作系统安装。</span><span class="sxs-lookup"><span data-stu-id="c47a7-185">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="c47a7-186">设备完成安装并重新启动后，从电脑导航到文件资源管理器，并将以前保存的 PPKG 文件复制到设备文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c47a7-186">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c47a7-187">![文件资源管理器窗口中的 PC 上的 PPKG 文件。](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="c47a7-187">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="c47a7-188">在 HoloLens 2 上，按以下按钮组合运行预配包：点击 " **关闭** " 和 " **电源" 按钮** 。</span><span class="sxs-lookup"><span data-stu-id="c47a7-188">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="c47a7-189">系统将提示你应用预配包，并选择 "**确认**"</span><span class="sxs-lookup"><span data-stu-id="c47a7-189">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="c47a7-190">预配包完成后，请选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c47a7-190">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="c47a7-191">然后，系统将提示你通过共享本地帐户和密码登录到设备。</span><span class="sxs-lookup"><span data-stu-id="c47a7-191">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="c47a7-192">维护</span><span class="sxs-lookup"><span data-stu-id="c47a7-192">Maintain</span></span>

<span data-ttu-id="c47a7-193">使用此配置时，建议重启上述过程，并使用 ARC 工具刷新设备，并应用新的 PPKG 来对 OS 和/或应用程序进行任何 () 的更新。</span><span class="sxs-lookup"><span data-stu-id="c47a7-193">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
