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
ms.openlocfilehash: 8828444a69d7e5d46293340ff771f97eb5eb01e6
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397878"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a><span data-ttu-id="645f4-104">常见方案–脱机安全 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="645f4-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <a name="overview"></a><span data-ttu-id="645f4-105">概述</span><span class="sxs-lookup"><span data-stu-id="645f4-105">Overview</span></span>

<span data-ttu-id="645f4-106">本指南提供了有关应用示例预配包的指导，该设置包将锁定 HoloLens 2 以便在安全环境中使用，但有以下限制：</span><span class="sxs-lookup"><span data-stu-id="645f4-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>

-   <span data-ttu-id="645f4-107">禁用 WiFi。</span><span class="sxs-lookup"><span data-stu-id="645f4-107">Disable WiFi.</span></span>
-   <span data-ttu-id="645f4-108">禁用蓝牙。</span><span class="sxs-lookup"><span data-stu-id="645f4-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="645f4-109">禁用麦克风。</span><span class="sxs-lookup"><span data-stu-id="645f4-109">Disable Microphones.</span></span>
-   <span data-ttu-id="645f4-110">阻止添加或删除预配包。</span><span class="sxs-lookup"><span data-stu-id="645f4-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="645f4-111">任何用户都不能启用上述任何受限制的组件。</span><span class="sxs-lookup"><span data-stu-id="645f4-111">No user can enable any of the above restricted components.</span></span>

<span data-ttu-id="645f4-112">[![脱机安全方案 ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="645f4-112">[ ![Offline Secure scenario](./images/deployment-guides-revised-scenario-c-01.png) ](./images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

## <a name="prepare"></a><span data-ttu-id="645f4-113">准备</span><span class="sxs-lookup"><span data-stu-id="645f4-113">Prepare</span></span>

<span data-ttu-id="645f4-114">Windows 10 电脑安装程序</span><span class="sxs-lookup"><span data-stu-id="645f4-114">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="645f4-115">将[最新的 HoloLens 2 OS 文件直接下载](https://aka.ms/hololens2download)到 PC。</span><span class="sxs-lookup"><span data-stu-id="645f4-115">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="645f4-116">版本19041.1117 及更高版本中包含了对此配置的支持。</span><span class="sxs-lookup"><span data-stu-id="645f4-116">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="645f4-117">[从 Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)到 PC 下载/安装高级恢复助理 (ARC) 工具</span><span class="sxs-lookup"><span data-stu-id="645f4-117">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="645f4-118">下载/安装最新的 [Windows 配置设计器 (WCD) ](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 工具从 MICROSOFT STORE 到 PC。</span><span class="sxs-lookup"><span data-stu-id="645f4-118">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="645f4-119">[下载包含项目文件的 OfflineSecureHL2_Sample 文件夹](https://aka.ms/HoloLensDocs-SecureOfflineSample) 以生成 PPKG。</span><span class="sxs-lookup"><span data-stu-id="645f4-119">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="645f4-120">准备 [PPKG 部署的脱机业务线应用程序](app-deploy-provisioning-package.md)。</span><span class="sxs-lookup"><span data-stu-id="645f4-120">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <a name="configure"></a><span data-ttu-id="645f4-121">配置</span><span class="sxs-lookup"><span data-stu-id="645f4-121">Configure</span></span>

<span data-ttu-id="645f4-122">构建安全配置预配包</span><span class="sxs-lookup"><span data-stu-id="645f4-122">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="645f4-123">在电脑上启动 WCD 工具。</span><span class="sxs-lookup"><span data-stu-id="645f4-123">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="645f4-124">选择 **"文件 "->打开项目"。**</span><span class="sxs-lookup"><span data-stu-id="645f4-124">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="645f4-125">导航到以前保存的 OfflineSecureHL2_Sample 文件夹的位置，然后选择：OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="645f4-125">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="645f4-126">项目应打开，现在应具有可用自定义项的列表：</span><span class="sxs-lookup"><span data-stu-id="645f4-126">The project should open and you should now have a list of Available Customizations:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="645f4-127">![在 WCD 中打开的配置包的屏幕截图](images/offline-secure-sample-wcd.png)</span><span class="sxs-lookup"><span data-stu-id="645f4-127">![Screenshot of the configuration package open in WCD](images/offline-secure-sample-wcd.png)</span></span>

   <span data-ttu-id="645f4-128">此预配包中设置的配置：</span><span class="sxs-lookup"><span data-stu-id="645f4-128">Configurations set in this provisioning package:</span></span>
   
   |     <span data-ttu-id="645f4-129">项目</span><span class="sxs-lookup"><span data-stu-id="645f4-129">Item</span></span>                                                |     <span data-ttu-id="645f4-130">设置</span><span class="sxs-lookup"><span data-stu-id="645f4-130">Setting</span></span>                       |     <span data-ttu-id="645f4-131">说明</span><span class="sxs-lookup"><span data-stu-id="645f4-131">Description</span></span>                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     <span data-ttu-id="645f4-132">帐户/用户</span><span class="sxs-lookup"><span data-stu-id="645f4-132">Accounts / Users</span></span>                                    |     <span data-ttu-id="645f4-133">本地用户名&密码</span><span class="sxs-lookup"><span data-stu-id="645f4-133">Local User Name & Password</span></span>    |     <span data-ttu-id="645f4-134">对于这些脱机设备，需要设置单个用户名和密码，并且由设备的所有用户共享。</span><span class="sxs-lookup"><span data-stu-id="645f4-134">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
   |     <span data-ttu-id="645f4-135">First Experience / HoloLens / SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="645f4-135">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="645f4-136">正确</span><span class="sxs-lookup"><span data-stu-id="645f4-136">True</span></span>                          |     <span data-ttu-id="645f4-137">仅在初始设备设置期间跳过校准</span><span class="sxs-lookup"><span data-stu-id="645f4-137">Skips calibration during initial device setup only</span></span>                                                                             |
   |     <span data-ttu-id="645f4-138">First Experience / HoloLens / SkipTraining</span><span class="sxs-lookup"><span data-stu-id="645f4-138">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="645f4-139">正确</span><span class="sxs-lookup"><span data-stu-id="645f4-139">True</span></span>                          |     <span data-ttu-id="645f4-140">在初始设备设置过程中跳过设备训练</span><span class="sxs-lookup"><span data-stu-id="645f4-140">Skips device training during initial device setup</span></span>                                                                              |
   |     <span data-ttu-id="645f4-141">First Experience / HoloLens / WiFi</span><span class="sxs-lookup"><span data-stu-id="645f4-141">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="645f4-142">正确</span><span class="sxs-lookup"><span data-stu-id="645f4-142">True</span></span>                          |     <span data-ttu-id="645f4-143">在Wi-Fi安装期间跳过配置</span><span class="sxs-lookup"><span data-stu-id="645f4-143">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
   |     <span data-ttu-id="645f4-144">策略/连接/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="645f4-144">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="645f4-145">否</span><span class="sxs-lookup"><span data-stu-id="645f4-145">No</span></span>                            |     <span data-ttu-id="645f4-146">禁用蓝牙</span><span class="sxs-lookup"><span data-stu-id="645f4-146">Disables Bluetooth</span></span>                                                                                                             |
   |     <span data-ttu-id="645f4-147">Policies/Experience/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="645f4-147">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="645f4-148">否</span><span class="sxs-lookup"><span data-stu-id="645f4-148">No</span></span>                            |     <span data-ttu-id="645f4-149">禁用 Cortana (消除潜在问题，因为麦克风已禁用) </span><span class="sxs-lookup"><span data-stu-id="645f4-149">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
   |     <span data-ttu-id="645f4-150">Policies/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="645f4-150">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="645f4-151">是</span><span class="sxs-lookup"><span data-stu-id="645f4-151">Yes</span></span>                           |     <span data-ttu-id="645f4-152">禁用麦克风</span><span class="sxs-lookup"><span data-stu-id="645f4-152">Disables Microphone</span></span>                                                                                                            |
   |     <span data-ttu-id="645f4-153">策略/隐私/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="645f4-153">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="645f4-154">强制拒绝</span><span class="sxs-lookup"><span data-stu-id="645f4-154">Force deny</span></span>                    |     <span data-ttu-id="645f4-155">阻止应用尝试访问位置数据 (以消除潜在问题，因为已禁用位置跟踪) </span><span class="sxs-lookup"><span data-stu-id="645f4-155">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
   |     <span data-ttu-id="645f4-156">策略/隐私/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="645f4-156">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="645f4-157">强制拒绝</span><span class="sxs-lookup"><span data-stu-id="645f4-157">Force deny</span></span>                    |     <span data-ttu-id="645f4-158">阻止应用尝试访问麦克风 (以消除在禁用麦克风后出现的潜在问题) </span><span class="sxs-lookup"><span data-stu-id="645f4-158">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
   |     <span data-ttu-id="645f4-159">策略/安全性/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="645f4-159">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="645f4-160">否</span><span class="sxs-lookup"><span data-stu-id="645f4-160">No</span></span>                            |     <span data-ttu-id="645f4-161">阻止任何人添加可能尝试替代锁定策略的预配包。</span><span class="sxs-lookup"><span data-stu-id="645f4-161">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
   |     <span data-ttu-id="645f4-162">策略/安全性/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="645f4-162">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="645f4-163">否</span><span class="sxs-lookup"><span data-stu-id="645f4-163">No</span></span>                            |     <span data-ttu-id="645f4-164">阻止任何人删除此锁定的预配包。</span><span class="sxs-lookup"><span data-stu-id="645f4-164">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
   |     <span data-ttu-id="645f4-165">策略/System/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="645f4-165">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="645f4-166">否</span><span class="sxs-lookup"><span data-stu-id="645f4-166">No</span></span>                            |     <span data-ttu-id="645f4-167">阻止设备尝试跟踪位置数据。</span><span class="sxs-lookup"><span data-stu-id="645f4-167">Prevents the device from trying to track location data.</span></span>                                                                        |
   |     <span data-ttu-id="645f4-168">策略/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="645f4-168">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="645f4-169">否</span><span class="sxs-lookup"><span data-stu-id="645f4-169">No</span></span>                            |     <span data-ttu-id="645f4-170">禁用 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="645f4-170">Disables Wi-Fi</span></span>                                                                                                                 |

1. <span data-ttu-id="645f4-171">在 "运行时设置" 下，选择 " **帐户/用户/用户名： Holo/Password**"。</span><span class="sxs-lookup"><span data-stu-id="645f4-171">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**.</span></span>

   <span data-ttu-id="645f4-172">记下密码，并根据需要重置。</span><span class="sxs-lookup"><span data-stu-id="645f4-172">Note the password and reset if desired.</span></span>

1. <span data-ttu-id="645f4-173">导航到 UniversalAppInstall/UserContextApp，并配置将部署到这些设备 [的 LOB 应用](app-deploy-provisioning-package.md) 。</span><span class="sxs-lookup"><span data-stu-id="645f4-173">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="645f4-174">![用于在 WCD 中添加应用程序的屏幕截图。](images/offline-secure-sample-wcd-usercontextapp2.png)</span><span class="sxs-lookup"><span data-stu-id="645f4-174">![Screenshot of where to add your app in WCD.](images/offline-secure-sample-wcd-usercontextapp2.png)</span></span>

1. <span data-ttu-id="645f4-175">完成后，选择 "导出" 按钮并按照所有提示操作，直到创建了预配包。</span><span class="sxs-lookup"><span data-stu-id="645f4-175">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="645f4-176">![WCD 中此包的 "导出" 按钮的屏幕截图。](images/offline-secure-sample-wcd-export.png)</span><span class="sxs-lookup"><span data-stu-id="645f4-176">![Screenshot of the Export button for this package in WCD.](images/offline-secure-sample-wcd-export.png)</span></span>

## <a name="deploy"></a><span data-ttu-id="645f4-177">部署</span><span class="sxs-lookup"><span data-stu-id="645f4-177">Deploy</span></span>

1. <span data-ttu-id="645f4-178">通过 USB 电缆将 HL2 Windows 10电脑。</span><span class="sxs-lookup"><span data-stu-id="645f4-178">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="645f4-179">启动 ARC 工具并选择 **"HoloLens 2**</span><span class="sxs-lookup"><span data-stu-id="645f4-179">Launch the ARC tool and select **HoloLens 2**</span></span>

   ![HoloLens 2干净重新滑动初始屏幕](images/ARC2.png)

1. <span data-ttu-id="645f4-181">在下一个屏幕上，选择"**手动包选择"。**</span><span class="sxs-lookup"><span data-stu-id="645f4-181">On the next screen select **Manual package selection**.</span></span>

   ![HoloLens 2 ARC 信息屏幕](images/arc_device_info.png)

1. <span data-ttu-id="645f4-183">导航到以前下载的 .ffu 文件，然后选择"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="645f4-183">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="645f4-184">在"警告"页上，选择"**继续"。**</span><span class="sxs-lookup"><span data-stu-id="645f4-184">At the Warning page select **Continue**.</span></span>

   ![HoloLens 2 ARC 警告屏幕](images/arc_warning.png)

1. <span data-ttu-id="645f4-186">等待 ARC 工具完成 HOLOLENS 2 OS 安装。</span><span class="sxs-lookup"><span data-stu-id="645f4-186">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="645f4-187">设备完成安装并启动后，从电脑导航到文件资源管理器，将以前保存的 PPKG 文件复制到设备文件夹。</span><span class="sxs-lookup"><span data-stu-id="645f4-187">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="645f4-188">![电脑窗口内电脑上的 PPKG 文件资源管理器文件。](images/offline-secure-file-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="645f4-188">![PPKG file on PC in File Explorer window.](images/offline-secure-file-explorer.png)</span></span>

1. <span data-ttu-id="645f4-189">在HoloLens 2，按以下按钮组合以运行预配包：同时点击"音量降低"和"**电源** 按钮"。</span><span class="sxs-lookup"><span data-stu-id="645f4-189">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="645f4-190">系统将提示你应用预配包，选择"确认 **"**</span><span class="sxs-lookup"><span data-stu-id="645f4-190">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="645f4-191">预配包完成后，选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="645f4-191">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="645f4-192">然后，系统会提示你使用共享的本地帐户和密码登录到设备。</span><span class="sxs-lookup"><span data-stu-id="645f4-192">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <a name="maintain"></a><span data-ttu-id="645f4-193">维护</span><span class="sxs-lookup"><span data-stu-id="645f4-193">Maintain</span></span>

<span data-ttu-id="645f4-194">通过此配置，建议重启上述过程，使用 ARC 工具重新运行设备，并应用新的 PPKG，对 OS 和/或应用程序进行 (更新) 。</span><span class="sxs-lookup"><span data-stu-id="645f4-194">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span>
