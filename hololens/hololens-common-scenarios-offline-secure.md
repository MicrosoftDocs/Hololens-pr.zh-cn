---
title: 常见方案-脱机安全 HoloLens 2
description: 通过预配进行脱机安全部署和应用部署。
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080466"
---
# <span data-ttu-id="921ce-104">常见方案-脱机安全 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="921ce-104">Common Scenarios – Offline Secure HoloLens 2</span></span>

## <span data-ttu-id="921ce-105">概述</span><span class="sxs-lookup"><span data-stu-id="921ce-105">Overview</span></span>
<span data-ttu-id="921ce-106">本指南提供了应用示例预配包的指南，该软件包将在安全环境中锁定 HoloLens 2 以供以下限制使用：</span><span class="sxs-lookup"><span data-stu-id="921ce-106">This guide provides guidance for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments with the following restrictions:</span></span>
-   <span data-ttu-id="921ce-107">禁用 WiFi。</span><span class="sxs-lookup"><span data-stu-id="921ce-107">Disable WiFi.</span></span>
-   <span data-ttu-id="921ce-108">禁用蓝牙。</span><span class="sxs-lookup"><span data-stu-id="921ce-108">Disable BlueTooth.</span></span>
-   <span data-ttu-id="921ce-109">禁用麦克风。</span><span class="sxs-lookup"><span data-stu-id="921ce-109">Disable Microphones.</span></span>
-   <span data-ttu-id="921ce-110">阻止添加或删除预配程序包。</span><span class="sxs-lookup"><span data-stu-id="921ce-110">Prevents adding or removing provisioning packages.</span></span>
-   <span data-ttu-id="921ce-111">任何用户都无法启用上述任何受限制的组件。</span><span class="sxs-lookup"><span data-stu-id="921ce-111">No user can enable any of the above restricted components.</span></span>

## <span data-ttu-id="921ce-112">准备</span><span class="sxs-lookup"><span data-stu-id="921ce-112">Prepare</span></span> 
<span data-ttu-id="921ce-113">Windows 10 电脑设置</span><span class="sxs-lookup"><span data-stu-id="921ce-113">Windows 10 PC Setup</span></span>
1. <span data-ttu-id="921ce-114">将[最新的 HoloLens 2 OS 文件直接下载](https://aka.ms/hololens2download)到电脑。</span><span class="sxs-lookup"><span data-stu-id="921ce-114">[Download the latest HoloLens 2 OS file](https://aka.ms/hololens2download) directly to a PC.</span></span> 
   1. <span data-ttu-id="921ce-115">内部版本19041.1117 和更高版本中包含对此配置的支持。</span><span class="sxs-lookup"><span data-stu-id="921ce-115">Support for this configuration is included in Build 19041.1117 and above.</span></span>
1. <span data-ttu-id="921ce-116">[从 Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)下载/安装高级恢复配套 (ARC) 工具</span><span class="sxs-lookup"><span data-stu-id="921ce-116">Download/Install the Advanced Recovery Companion(ARC) tool [from the Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) to your PC</span></span>
1. <span data-ttu-id="921ce-117">从 Microsoft Store 中的 WCD) 工具下载/安装最新 [Windows 配置设计器 (](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 工具。</span><span class="sxs-lookup"><span data-stu-id="921ce-117">Download/Install the latest [Windows Configuration Designer (WCD)](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) tool from the Microsoft Store to your PC.</span></span>
1. <span data-ttu-id="921ce-118">[下载包含项目文件的 OfflineSecureHL2_Sample 文件夹](https://aka.ms/HoloLensDocs-SecureOfflineSample) 以生成 PPKG。</span><span class="sxs-lookup"><span data-stu-id="921ce-118">[Download the OfflineSecureHL2_Sample folder with the project files](https://aka.ms/HoloLensDocs-SecureOfflineSample) to build the PPKG.</span></span>
1. <span data-ttu-id="921ce-119">[为 PPKG 部署准备脱机的业务线应用程序](app-deploy-provisioning-package.md)。</span><span class="sxs-lookup"><span data-stu-id="921ce-119">Prepare your offline [Line of Business application for PPKG deployment](app-deploy-provisioning-package.md).</span></span> 


## <span data-ttu-id="921ce-120">配置</span><span class="sxs-lookup"><span data-stu-id="921ce-120">Configure</span></span>
<span data-ttu-id="921ce-121">构建安全配置预配程序包</span><span class="sxs-lookup"><span data-stu-id="921ce-121">Build a Secure Configuration Provisioning Package</span></span>

1. <span data-ttu-id="921ce-122">在电脑上启动 WCD 工具。</span><span class="sxs-lookup"><span data-stu-id="921ce-122">Launch the WCD tool on your PC.</span></span>
1. <span data-ttu-id="921ce-123">选择 " **文件"-> "打开项目**"。</span><span class="sxs-lookup"><span data-stu-id="921ce-123">Select **File -> Open project**.</span></span>
  1. <span data-ttu-id="921ce-124">导航到之前保存的 OfflineSecureHL2_Sample 文件夹的位置，然后选择： OfflineSecureHL2_Sample.icdproj.xml</span><span class="sxs-lookup"><span data-stu-id="921ce-124">Navigate to the location of the previously saved OfflineSecureHL2_Sample folder, and select: OfflineSecureHL2_Sample.icdproj.xml</span></span>
1. <span data-ttu-id="921ce-125">此时应打开该项目，您现在应具有可用的自定义列表：</span><span class="sxs-lookup"><span data-stu-id="921ce-125">The project should open and you should now have a list of Available Customizations:</span></span> 

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中打开的配置包的屏幕截图](images/offline-secure-sample-wcd.png)

<span data-ttu-id="921ce-127">此预配包中设置的配置：</span><span class="sxs-lookup"><span data-stu-id="921ce-127">Configurations set in this provisioning package:</span></span>

|     <span data-ttu-id="921ce-128">项目</span><span class="sxs-lookup"><span data-stu-id="921ce-128">Item</span></span>                                                |     <span data-ttu-id="921ce-129">设置</span><span class="sxs-lookup"><span data-stu-id="921ce-129">Setting</span></span>                       |     <span data-ttu-id="921ce-130">描述</span><span class="sxs-lookup"><span data-stu-id="921ce-130">Description</span></span>                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="921ce-131">帐户/用户</span><span class="sxs-lookup"><span data-stu-id="921ce-131">Accounts / Users</span></span>                                    |     <span data-ttu-id="921ce-132">本地用户名 & 密码</span><span class="sxs-lookup"><span data-stu-id="921ce-132">Local User Name & Password</span></span>    |     <span data-ttu-id="921ce-133">对于这些脱机设备，需要为该设备的所有用户设置和共享单个用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="921ce-133">For these offline devices, a single user name and password will need to be set and shared by all users of the device.</span></span>          |
|     <span data-ttu-id="921ce-134">首次体验/HoloLens/SkipCalibration</span><span class="sxs-lookup"><span data-stu-id="921ce-134">First Experience / HoloLens / SkipCalibration</span></span>       |     <span data-ttu-id="921ce-135">True</span><span class="sxs-lookup"><span data-stu-id="921ce-135">True</span></span>                          |     <span data-ttu-id="921ce-136">仅在初始设备设置期间跳过校准</span><span class="sxs-lookup"><span data-stu-id="921ce-136">Skips calibration during initial device setup only</span></span>                                                                             |
|     <span data-ttu-id="921ce-137">首次体验/HoloLens/SkipTraining</span><span class="sxs-lookup"><span data-stu-id="921ce-137">First Experience / HoloLens / SkipTraining</span></span>          |     <span data-ttu-id="921ce-138">True</span><span class="sxs-lookup"><span data-stu-id="921ce-138">True</span></span>                          |     <span data-ttu-id="921ce-139">在初始设备设置过程中跳过设备培训</span><span class="sxs-lookup"><span data-stu-id="921ce-139">Skips device training during initial device setup</span></span>                                                                              |
|     <span data-ttu-id="921ce-140">首次体验/HoloLens/WiFi</span><span class="sxs-lookup"><span data-stu-id="921ce-140">First Experience / HoloLens / WiFi</span></span>                  |     <span data-ttu-id="921ce-141">True</span><span class="sxs-lookup"><span data-stu-id="921ce-141">True</span></span>                          |     <span data-ttu-id="921ce-142">在初始设备设置期间跳过 Wi-fi 配置</span><span class="sxs-lookup"><span data-stu-id="921ce-142">Skips Wi-Fi config during initial device setup</span></span>                                                                                 |
|     <span data-ttu-id="921ce-143">策略/连接/AllowBluetooth</span><span class="sxs-lookup"><span data-stu-id="921ce-143">Policies/Connectivity/AllowBluetooth</span></span>                |     <span data-ttu-id="921ce-144">否</span><span class="sxs-lookup"><span data-stu-id="921ce-144">No</span></span>                            |     <span data-ttu-id="921ce-145">禁用蓝牙</span><span class="sxs-lookup"><span data-stu-id="921ce-145">Disables Bluetooth</span></span>                                                                                                             |
|     <span data-ttu-id="921ce-146">政策/体验/AllowCortana</span><span class="sxs-lookup"><span data-stu-id="921ce-146">Policies/Experience/AllowCortana</span></span>                    |     <span data-ttu-id="921ce-147">否</span><span class="sxs-lookup"><span data-stu-id="921ce-147">No</span></span>                            |     <span data-ttu-id="921ce-148">禁用 Cortana (可在禁用麦克风后消除潜在问题) </span><span class="sxs-lookup"><span data-stu-id="921ce-148">Disables Cortana (to eliminate potential problems since the microphones are disabled)</span></span>                                          |
|     <span data-ttu-id="921ce-149">政策/MixedReality/MicrophoneDisabled</span><span class="sxs-lookup"><span data-stu-id="921ce-149">Policies/MixedReality/MicrophoneDisabled</span></span>            |     <span data-ttu-id="921ce-150">是</span><span class="sxs-lookup"><span data-stu-id="921ce-150">Yes</span></span>                           |     <span data-ttu-id="921ce-151">禁用麦克风</span><span class="sxs-lookup"><span data-stu-id="921ce-151">Disables Microphone</span></span>                                                                                                            |
|     <span data-ttu-id="921ce-152">政策/隐私权/LetAppsAccessLocation</span><span class="sxs-lookup"><span data-stu-id="921ce-152">Policies/Privacy/LetAppsAccessLocation</span></span>              |     <span data-ttu-id="921ce-153">强制拒绝</span><span class="sxs-lookup"><span data-stu-id="921ce-153">Force deny</span></span>                    |     <span data-ttu-id="921ce-154">阻止应用尝试访问位置数据 (以消除潜在问题，因为禁用位置跟踪) </span><span class="sxs-lookup"><span data-stu-id="921ce-154">Prevents Apps from trying to access Location data (to eliminate potential problems since the Location tracking is disabled)</span></span>    |
|     <span data-ttu-id="921ce-155">政策/隐私权/LetAppsAccessMicrophone</span><span class="sxs-lookup"><span data-stu-id="921ce-155">Policies/Privacy/LetAppsAccessMicrophone</span></span>            |     <span data-ttu-id="921ce-156">强制拒绝</span><span class="sxs-lookup"><span data-stu-id="921ce-156">Force deny</span></span>                    |     <span data-ttu-id="921ce-157">阻止应用尝试访问麦克风 (，以便在禁用麦克风后消除潜在问题) </span><span class="sxs-lookup"><span data-stu-id="921ce-157">Prevents Apps from trying to access Microphones (to eliminate potential problems since the Microphones are disabled)</span></span>           |
|     <span data-ttu-id="921ce-158">政策/Security/AllowAddProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="921ce-158">Policies/Security/AllowAddProvisioningPackage</span></span>       |     <span data-ttu-id="921ce-159">否</span><span class="sxs-lookup"><span data-stu-id="921ce-159">No</span></span>                            |     <span data-ttu-id="921ce-160">阻止任何人添加可能会尝试覆盖已锁定策略的预配包。</span><span class="sxs-lookup"><span data-stu-id="921ce-160">Prevents anyone from adding provisioning packages that might attempt to override locked down policies.</span></span>                         |
|     <span data-ttu-id="921ce-161">政策/Security/AllowRemoveProvisioningPackage</span><span class="sxs-lookup"><span data-stu-id="921ce-161">Policies/Security/AllowRemoveProvisioningPackage</span></span>    |     <span data-ttu-id="921ce-162">否</span><span class="sxs-lookup"><span data-stu-id="921ce-162">No</span></span>                            |     <span data-ttu-id="921ce-163">阻止任何人删除此锁定的预配包。</span><span class="sxs-lookup"><span data-stu-id="921ce-163">Prevents anyone from removing this locked down provisioning package.</span></span>                                                           |
|     <span data-ttu-id="921ce-164">政策/系统/AllowLocation</span><span class="sxs-lookup"><span data-stu-id="921ce-164">Policies/System/AllowLocation</span></span>                       |     <span data-ttu-id="921ce-165">否</span><span class="sxs-lookup"><span data-stu-id="921ce-165">No</span></span>                            |     <span data-ttu-id="921ce-166">阻止设备尝试跟踪位置数据。</span><span class="sxs-lookup"><span data-stu-id="921ce-166">Prevents the device from trying to track location data.</span></span>                                                                        |
|     <span data-ttu-id="921ce-167">政策/WiFi/AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="921ce-167">Policies/WiFi/AllowWiFi</span></span>                             |     <span data-ttu-id="921ce-168">否</span><span class="sxs-lookup"><span data-stu-id="921ce-168">No</span></span>                            |     <span data-ttu-id="921ce-169">禁用 Wi-fi</span><span class="sxs-lookup"><span data-stu-id="921ce-169">Disables Wi-Fi</span></span>                                                                                                                 |

4. <span data-ttu-id="921ce-170">在 "运行时设置" 下，选择 "**帐户/用户/用户名： Holo/密码**"</span><span class="sxs-lookup"><span data-stu-id="921ce-170">Under Runtime Settings, Select **Accounts / Users / UserName: Holo / Password**</span></span> 
    - <span data-ttu-id="921ce-171">记下密码，如果需要，重置。</span><span class="sxs-lookup"><span data-stu-id="921ce-171">Note the password and reset if desired.</span></span>
5. <span data-ttu-id="921ce-172">导航到 UniversalAppInstall/UserContextApp 并配置将部署到这些设备 [的 LOB 应用](app-deploy-provisioning-package.md) 。</span><span class="sxs-lookup"><span data-stu-id="921ce-172">Navigate to UniversalAppInstall / UserContextApp and [configure the LOB app](app-deploy-provisioning-package.md) you will be deploying to these devices.</span></span>

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中的何处添加应用的屏幕截图。](images/offline-secure-sample-wcd-usercontextapp.png)

6. <span data-ttu-id="921ce-174">完成后，选择 "导出" 按钮并按照所有提示进行操作，直到创建你的预配包。</span><span class="sxs-lookup"><span data-stu-id="921ce-174">Once complete, select the “Export” button and follow all prompts until your provisioning package is created.</span></span>

   > [!div class="mx-imgBorder"]
   > ![WCD 中此程序包的 "导出" 按钮的屏幕截图。](images/offline-secure-sample-wcd-export.png)


## <span data-ttu-id="921ce-176">部署</span><span class="sxs-lookup"><span data-stu-id="921ce-176">Deploy</span></span>
1. <span data-ttu-id="921ce-177">通过 USB 电缆将 HL2 连接到 Windows 10 电脑。</span><span class="sxs-lookup"><span data-stu-id="921ce-177">Connect the HL2 to your Windows 10 PC via USB cable.</span></span>
1. <span data-ttu-id="921ce-178">启动 "弧形" 工具，然后选择 " **HoloLens 2** "</span><span class="sxs-lookup"><span data-stu-id="921ce-178">Launch the ARC tool and select **HoloLens 2**</span></span>

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. <span data-ttu-id="921ce-179">在下一个屏幕上，选择 " **手动程序包选择**"。</span><span class="sxs-lookup"><span data-stu-id="921ce-179">On the next screen select **Manual package selection**.</span></span>
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. <span data-ttu-id="921ce-180">导航到以前下载的 ffu 文件，然后选择 " **打开**"。</span><span class="sxs-lookup"><span data-stu-id="921ce-180">Navigate to the previously downloaded .ffu file, and select **Open**.</span></span>
1. <span data-ttu-id="921ce-181">在警告页面上选择 " **继续**"。</span><span class="sxs-lookup"><span data-stu-id="921ce-181">At the Warning page select **Continue**.</span></span>

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. <span data-ttu-id="921ce-182">等待弧形工具完成 HoloLens 2 操作系统安装。</span><span class="sxs-lookup"><span data-stu-id="921ce-182">Wait for the ARC tool to complete the HoloLens 2 OS install.</span></span>
1. <span data-ttu-id="921ce-183">设备完成安装并重新启动后，从你的电脑导航到 "文件资源管理器" 并将以前保存的 PPKG 文件复制到设备文件夹。</span><span class="sxs-lookup"><span data-stu-id="921ce-183">Once the device completes the install and boots back up, from your PC navigate to File Explorer and copy the previously saved PPKG file over to the device folder.</span></span>

   > [!div class="mx-imgBorder"]
   > ![PPKG 在文件资源管理器窗口中的 PC 上的文件。](images/offline-secure-file-explorer.png)

1. <span data-ttu-id="921ce-185">在 HoloLens 2 上，按以下按钮组合运行预配包：点击 " **音量降低** " 和 " **电源" 按钮** 。</span><span class="sxs-lookup"><span data-stu-id="921ce-185">On the HoloLens 2, press the following button combo to run the Provisioning Package: Tap **Volume Down** and **Power Button** at the same time.</span></span>
1. <span data-ttu-id="921ce-186">系统将提示你应用预配包，请选择 "**确认**"</span><span class="sxs-lookup"><span data-stu-id="921ce-186">You will be prompted to apply the Provisioning Package, select **Confirm**</span></span>
1. <span data-ttu-id="921ce-187">预配包完成后，选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="921ce-187">Once the provisioning package completes select **OK**.</span></span>
1. <span data-ttu-id="921ce-188">然后，系统将提示您通过共享的本地帐户和密码登录到设备。</span><span class="sxs-lookup"><span data-stu-id="921ce-188">You should then be prompted to sign into the device with the shared local account and password.</span></span>

## <span data-ttu-id="921ce-189">维护</span><span class="sxs-lookup"><span data-stu-id="921ce-189">Maintain</span></span>
<span data-ttu-id="921ce-190">使用此配置时，建议重启上述过程并使用 ARC 工具 reflash 设备，并应用新的 PPKG，以便对操作系统和/或应用程序 (s) 进行任何更新。</span><span class="sxs-lookup"><span data-stu-id="921ce-190">With this configuration, it is recommended to restart the process above and reflash the device with the ARC tool and apply a new PPKG to make any updates to the OS and/or application(s).</span></span> 

