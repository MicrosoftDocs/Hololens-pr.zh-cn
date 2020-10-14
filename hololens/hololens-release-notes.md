---
title: HoloLens 2 发行说明
description: 了解每个新的 HoloLens 2 版本中的更新。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/9/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 23ec5478c35977d1fd1fa20a33827e441d4b5c12
ms.sourcegitcommit: 264c8ff6726f702c3770525d774e0c1d263a2705
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117767"
---
# <span data-ttu-id="82678-103">HoloLens 2 发行说明</span><span class="sxs-lookup"><span data-stu-id="82678-103">HoloLens 2 release notes</span></span>

<span data-ttu-id="82678-104">为确保您的 HoloLens 设备具有高效的体验，我们将继续发布功能、缺陷和安全更新。</span><span class="sxs-lookup"><span data-stu-id="82678-104">To ensure you have a productive experience with your HoloLens devices, we continue to release feature, bug, and security updates.</span></span> <span data-ttu-id="82678-105">在此页面上，您可以查看每月 HoloLens 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="82678-105">On this page, you can see what’s new for HoloLens each month.</span></span> <span data-ttu-id="82678-106">若要获取最新的 HoloLens 2 完整闪存更新 (FFU) [通过 "高级恢复助理" 将您的设备闪存](hololens-recovery.md#clean-reflash-the-device)，请 [在此处下载](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="82678-106">To get the latest HoloLens 2 Full Flash Update (FFU) to [flash your device via Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device), [download it here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="82678-107">下载将保持最新状态，并提供最新的通用内部版本。</span><span class="sxs-lookup"><span data-stu-id="82678-107">The download is kept up to date and provides the latest generally available build.</span></span>

>[!NOTE]
> <span data-ttu-id="82678-108">若要阅读 HoloLens 模拟器发行说明，请 [访问存档](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)。</span><span class="sxs-lookup"><span data-stu-id="82678-108">To read HoloLens Emulator release notes, [visit the archive](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).</span></span>

## <span data-ttu-id="82678-109">Windows 全息版 2004-2020 更新</span><span class="sxs-lookup"><span data-stu-id="82678-109">Windows Holographic, version 2004 - October 2020 Update</span></span>
- <span data-ttu-id="82678-110">内部版本19041.1124</span><span class="sxs-lookup"><span data-stu-id="82678-110">Build 19041.1124</span></span>
 
<span data-ttu-id="82678-111">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="82678-111">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="82678-112">已删除导致运行时系统错误的不必要检查。</span><span class="sxs-lookup"><span data-stu-id="82678-112">Removed an unnecessary check that caused runtime system fault.</span></span>

## <span data-ttu-id="82678-113">Windows 全息版 1903-2020 更新</span><span class="sxs-lookup"><span data-stu-id="82678-113">Windows Holographic, version 1903 - October 2020 Update</span></span>
- <span data-ttu-id="82678-114">内部版本18362.1081</span><span class="sxs-lookup"><span data-stu-id="82678-114">Build 18362.1081</span></span>

<span data-ttu-id="82678-115">此每月质量更新不包含任何显著更改，我们鼓励你试用 Windows 全息版2004的最新版本。</span><span class="sxs-lookup"><span data-stu-id="82678-115">This monthly quality update doesn't contain any notable changes, we encourage you to try out our latest builds for Windows Holographic, version 2004.</span></span>

## <span data-ttu-id="82678-116">Windows 全息版 2004-2020 更新</span><span class="sxs-lookup"><span data-stu-id="82678-116">Windows Holographic, version 2004 - September 2020 Update</span></span>
- <span data-ttu-id="82678-117">内部版本19041.1117</span><span class="sxs-lookup"><span data-stu-id="82678-117">Build 19041.1117</span></span>

<span data-ttu-id="82678-118">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="82678-118">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="82678-119">解决了阻止 Visual Studio 在 package.appxmanifest 中存在 SupportsMultipleInstances = "true" 时调试应用程序的问题。</span><span class="sxs-lookup"><span data-stu-id="82678-119">Addresses an issue that prevented Visual Studio from debugging an application when SupportsMultipleInstances=”true” is present in the appxmanifest.</span></span>
- <span data-ttu-id="82678-120">此版本包括 NCSI 代理检测修复，以解决通过网络代理进行的 Internet 检测失败。</span><span class="sxs-lookup"><span data-stu-id="82678-120">This release includes NCSI proxy detection fix to address failed Internet detection over network proxy.</span></span> <span data-ttu-id="82678-121">NCSI 可以使用计算机代理和每个配置文件的代理进行 Internet 连接检测。</span><span class="sxs-lookup"><span data-stu-id="82678-121">NCSI can use machine proxy and per-profile proxy for Internet connectivity detection.</span></span> <span data-ttu-id="82678-122">未来版本中的 NCSI 将支持每用户代理。</span><span class="sxs-lookup"><span data-stu-id="82678-122">Per-user proxy will be supported by NCSI in future release.</span></span>
- <span data-ttu-id="82678-123">在大多数 Windows Mixed Reality 设备上，当用户的 head 位于要进行转发的中性位置时，向前矢量平行于地面。</span><span class="sxs-lookup"><span data-stu-id="82678-123">On most Windows Mixed Reality devices, the forward direction vector is parallel to the ground when the user's head is in a neutral position looking forward.</span></span> <span data-ttu-id="82678-124">但是，较早版本的 HoloLens 2 将矢量调整为垂直于显示面板，而不是相对于理想方向向下倾斜几度。</span><span class="sxs-lookup"><span data-stu-id="82678-124">However, earlier versions of HoloLens 2 aligned the vector to be perpendicular to the display panels instead, which is tilted downward a few degrees relative to the ideal orientation.</span></span> <span data-ttu-id="82678-125">较新版本的 HoloLens 2 已更正此情况，以确保各种形式因素的语义一致性。</span><span class="sxs-lookup"><span data-stu-id="82678-125">Newer versions of HoloLens 2 have corrected this to ensure semantic consistency across form factors.</span></span>
- <span data-ttu-id="82678-126">改善了右手跟踪的可靠性，这些可靠性将导致特定方案中的跟踪损失较少。</span><span class="sxs-lookup"><span data-stu-id="82678-126">Improved hand tracking robustness that will result in fewer tracking losses in specific scenarios.</span></span>
- <span data-ttu-id="82678-127">此版本包含一个修补程序，可改进音频时间戳质量，这可能会导致视频捕获问题。</span><span class="sxs-lookup"><span data-stu-id="82678-127">This release contains a fix to improve audio timestamp quality which may have contributed to video capture issues.</span></span>

## <span data-ttu-id="82678-128">Windows 全息版 1903-2020 更新</span><span class="sxs-lookup"><span data-stu-id="82678-128">Windows Holographic, version 1903 - September 2020 Update</span></span>
- <span data-ttu-id="82678-129">内部版本18362.1079</span><span class="sxs-lookup"><span data-stu-id="82678-129">Build 18362.1079</span></span>

<span data-ttu-id="82678-130">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="82678-130">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="82678-131">在大多数 Windows Mixed Reality 设备上，当用户的 head 位于要进行转发的中性位置时，向前矢量平行于地面。</span><span class="sxs-lookup"><span data-stu-id="82678-131">On most Windows Mixed Reality devices, the forward direction vector is parallel to the ground when the user's head is in a neutral position looking forward.</span></span> <span data-ttu-id="82678-132">但是，较早版本的 HoloLens 2 将矢量调整为垂直于显示面板，而不是相对于理想方向向下倾斜几度。</span><span class="sxs-lookup"><span data-stu-id="82678-132">However, earlier versions of HoloLens 2 aligned the vector to be perpendicular to the display panels instead, which is tilted downward a few degrees relative to the ideal orientation.</span></span> <span data-ttu-id="82678-133">较新版本的 HoloLens 2 已更正此情况，以确保各种形式因素的语义一致性。</span><span class="sxs-lookup"><span data-stu-id="82678-133">Newer versions of HoloLens 2 have corrected this to ensure semantic consistency across form factors.</span></span>
- <span data-ttu-id="82678-134">改善了右手跟踪的可靠性，这些可靠性将导致特定方案中的跟踪损失较少。</span><span class="sxs-lookup"><span data-stu-id="82678-134">Improved hand tracking robustness that will result in fewer tracking losses in specific scenarios.</span></span>

## <span data-ttu-id="82678-135">Windows 全息版 2004-2020 更新</span><span class="sxs-lookup"><span data-stu-id="82678-135">Windows Holographic, version 2004 - August 2020 Update</span></span>
- <span data-ttu-id="82678-136">内部版本19041.1113</span><span class="sxs-lookup"><span data-stu-id="82678-136">Build 19041.1113</span></span>

<span data-ttu-id="82678-137">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="82678-137">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="82678-138">"设置" 应用将不再关注用户进入虹膜注册或目视跟踪校准体验。</span><span class="sxs-lookup"><span data-stu-id="82678-138">Settings app will no longer follow the user into Iris Enrollment or Eye Tracking Calibration experiences.</span></span>
- <span data-ttu-id="82678-139">修复了在 OOBE 期间应用预配包的 bug，用于重命名设备并执行其他操作 (例如，连接到网络) 将无法在设备重启（由于重命名）后执行其他操作。</span><span class="sxs-lookup"><span data-stu-id="82678-139">Fixed a bug where applying a provisioning package during OOBE that renames the device and performs other actions (such as connecting to a network) would fail to perform the other actions after the device reboot due to rename.</span></span>
- <span data-ttu-id="82678-140">已修改初始设备设置流的配色方案，以提高视觉质量。</span><span class="sxs-lookup"><span data-stu-id="82678-140">Modified color scheme of initial device setup flows to improve visual quality.</span></span>

## <span data-ttu-id="82678-141">Windows 全息版 1903-2020 更新</span><span class="sxs-lookup"><span data-stu-id="82678-141">Windows Holographic, version 1903 - August 2020 Update</span></span>
- <span data-ttu-id="82678-142">内部版本18362.1074</span><span class="sxs-lookup"><span data-stu-id="82678-142">Build 18362.1074</span></span>

<span data-ttu-id="82678-143">此每月质量更新不包含任何显著更改，我们鼓励你试用 Windows 全息版2004的最新版本。</span><span class="sxs-lookup"><span data-stu-id="82678-143">This monthly quality update doesn't contain any notable changes, we encourage you to try out our latest builds for Windows Holographic, version 2004.</span></span>

## <span data-ttu-id="82678-144">Windows 全息版 2004-2020 年7月更新</span><span class="sxs-lookup"><span data-stu-id="82678-144">Windows Holographic, version 2004 - July 2020 Update</span></span>
- <span data-ttu-id="82678-145">内部版本19041.1109</span><span class="sxs-lookup"><span data-stu-id="82678-145">Build 19041.1109</span></span>

<span data-ttu-id="82678-146">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="82678-146">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="82678-147">现在，开发人员可以在启用或禁用设备门户时选择是否需要安全连接。</span><span class="sxs-lookup"><span data-stu-id="82678-147">Developers can now choose between enabling or disabling having Device Portal require a secure connection.</span></span>
- <span data-ttu-id="82678-148">操作系统更新后，应用程序启动时的可靠性有所改进。</span><span class="sxs-lookup"><span data-stu-id="82678-148">Reliability improved for application launches after OS updates.</span></span>
- <span data-ttu-id="82678-149">已将默认收件箱亮度更改为100%。</span><span class="sxs-lookup"><span data-stu-id="82678-149">Changed default inbox brightness to 100 percent.</span></span>
- <span data-ttu-id="82678-150">解决了有关 HoloLens 2 上的 Windows Device Portal 的 HTTPS 转发的问题。</span><span class="sxs-lookup"><span data-stu-id="82678-150">Addressed an issue about HTTPS forwarding for the Windows Device Portal on HoloLens 2.</span></span>

## <span data-ttu-id="82678-151">Windows 全息版 1903-2020 年7月更新</span><span class="sxs-lookup"><span data-stu-id="82678-151">Windows Holographic, version 1903 - July 2020 Update</span></span>
- <span data-ttu-id="82678-152">内部版本18362.1071</span><span class="sxs-lookup"><span data-stu-id="82678-152">Build 18362.1071</span></span>

<span data-ttu-id="82678-153">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="82678-153">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="82678-154">修复了一个问题，该问题可能会导致全息图在丢失或执行跟踪时无法在 Unity 应用程序中消失。</span><span class="sxs-lookup"><span data-stu-id="82678-154">Fixed an issue that could cause holograms to disappear in Unity applications when losing or regaining tracking.</span></span>
- <span data-ttu-id="82678-155">修复了在某些设备上使用 HoloLens 模拟器和硬件加速时，导致独占 HoloLens 应用崩溃的问题。</span><span class="sxs-lookup"><span data-stu-id="82678-155">Fixed an issue that caused exclusive HoloLens apps to crash back to the shell while using the HoloLens Emulator with hardware acceleration on certain devices.</span></span>
- <span data-ttu-id="82678-156">解决了与 HoloLens 2 上的 Windows Device Portal 的 HTTPS 转发有关的问题。</span><span class="sxs-lookup"><span data-stu-id="82678-156">Addressed an issue concerning HTTPS forwarding for the Windows Device Portal on HoloLens 2.</span></span>

## <span data-ttu-id="82678-157">Windows 全息版 2004-2020 更新</span><span class="sxs-lookup"><span data-stu-id="82678-157">Windows Holographic, version 2004 - June 2020 Update</span></span>
- <span data-ttu-id="82678-158">内部版本19041.1106</span><span class="sxs-lookup"><span data-stu-id="82678-158">Build 19041.1106</span></span>

<span data-ttu-id="82678-159">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="82678-159">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="82678-160">如果未指定某些属性，自定义 MRC 记录器现在具有新的默认值。</span><span class="sxs-lookup"><span data-stu-id="82678-160">Custom MRC recorders now have new default values for certain properties if they aren't specified.</span></span>
  - <span data-ttu-id="82678-161">在 " *MRC 视频" 效果*中：</span><span class="sxs-lookup"><span data-stu-id="82678-161">On the *MRC Video Effect*:</span></span>
    - <span data-ttu-id="82678-162">PreferredHologramPerspective (1 PhotoVideoCamera) </span><span class="sxs-lookup"><span data-stu-id="82678-162">PreferredHologramPerspective (1 PhotoVideoCamera)</span></span>
    - <span data-ttu-id="82678-163">GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式头戴式耳机) # A5</span><span class="sxs-lookup"><span data-stu-id="82678-163">GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Immersive headset))</span></span>
  - <span data-ttu-id="82678-164">在 " *MRC 音频" 效果*中：</span><span class="sxs-lookup"><span data-stu-id="82678-164">On the *MRC Audio Effect*:</span></span>
    - <span data-ttu-id="82678-165">LoopbackGain (Windows Device Portal 中混合现实捕获页面上的当前 "应用音频收益" 值) </span><span class="sxs-lookup"><span data-stu-id="82678-165">LoopbackGain (the current "App Audio Gain" value on the Mixed Reality Capture page in Windows Device Portal)</span></span>
    - <span data-ttu-id="82678-166">MicrophoneGain (Windows Device Portal 中混合现实捕获页面上的当前 "Mic Audio 增益" 值) </span><span class="sxs-lookup"><span data-stu-id="82678-166">MicrophoneGain (the current "Mic Audio Gain" value on the Mixed Reality Capture page in Windows Device Portal)</span></span>
- <span data-ttu-id="82678-167">修复了在混合现实捕获方案中提高音频质量的 bug。</span><span class="sxs-lookup"><span data-stu-id="82678-167">Fixed a bug to improve audio quality in mixed reality capture scenarios.</span></span> <span data-ttu-id="82678-168">尤其是，此修补程序应在显示 " **开始** " 菜单时消除录制中的音频 glitching。</span><span class="sxs-lookup"><span data-stu-id="82678-168">Specifically, this fix should eliminate audio glitching in the recording when the **Start** menu is displayed.</span></span>
- <span data-ttu-id="82678-169">改进了录制视频中的全息图稳定性。</span><span class="sxs-lookup"><span data-stu-id="82678-169">Improved hologram stability in recorded videos.</span></span>
- <span data-ttu-id="82678-170">解决了在设备离开待机状态几天后混合现实捕获无法录制视频的问题。</span><span class="sxs-lookup"><span data-stu-id="82678-170">Resolved an issue where mixed reality capture couldn't record video after the device was left in standby state for multiple days.</span></span>
- <span data-ttu-id="82678-171">对于 Unity 应用程序，HolographicSpace 通常禁用 UserPresence API。</span><span class="sxs-lookup"><span data-stu-id="82678-171">The HolographicSpace.UserPresence API is generally disabled for Unity applications.</span></span> <span data-ttu-id="82678-172">此行为可避免在面板翻转时导致某些应用暂停的问题，即使已启用 "在后台运行" 设置。</span><span class="sxs-lookup"><span data-stu-id="82678-172">This behavior avoids an issue that caused some apps to pause when the visor was flipped up, even if the "run in the background" setting was enabled.</span></span> <span data-ttu-id="82678-173">现已针对 Unity 版本2018.4.18 及更高版本和2019.3.4 及更高版本启用 API。</span><span class="sxs-lookup"><span data-stu-id="82678-173">The API is now enabled for Unity versions 2018.4.18 and later and 2019.3.4 and later.</span></span>
- <span data-ttu-id="82678-174">通过 Wi-Fi 连接访问 Device Portal 时，web 浏览器可能会阻止访问，因为证书无效。</span><span class="sxs-lookup"><span data-stu-id="82678-174">When you access Device Portal over a Wi-Fi connection, a web browser might prevent access to due to an invalid certificate.</span></span> <span data-ttu-id="82678-175">浏览器可能会报告诸如 "ERR_SSL_PROTOCOL_ERROR" 之类的错误，即使设备证书以前已受信任。</span><span class="sxs-lookup"><span data-stu-id="82678-175">The browser might report an error such as "ERR_SSL_PROTOCOL_ERROR," even if the device certificate was previously trusted.</span></span> <span data-ttu-id="82678-176">在这种情况下，你无法对 Device Portal 进行进度，因为没有用于忽略安全警告的选项。</span><span class="sxs-lookup"><span data-stu-id="82678-176">In this case, you can't progress to Device Portal, as there's no option to ignore security warnings.</span></span> <span data-ttu-id="82678-177">此更新解决了此问题。</span><span class="sxs-lookup"><span data-stu-id="82678-177">This update resolved the issue.</span></span> <span data-ttu-id="82678-178">如果以前在电脑上下载并信任设备证书以删除浏览器安全警告，并且发生 SSL 错误，则必须下载新证书并信任该证书才能解决浏览器安全警告。</span><span class="sxs-lookup"><span data-stu-id="82678-178">If the device certificate was previously downloaded and trusted on a PC to remove browser security warnings, and the SSL error occurs, the new certificate has to be downloaded and trusted to address browser security warnings.</span></span>
- <span data-ttu-id="82678-179">已启用创建可使用 MSIX 程序包安装应用的运行时预配包的功能。</span><span class="sxs-lookup"><span data-stu-id="82678-179">Enabled the ability to create a runtime provisioning package that can install an app by using MSIX packages.</span></span>
- <span data-ttu-id="82678-180">在**设置**系统全息图中添加了一项设置  >  **System**  >  **Holograms** ，使用户可以在设备关闭时自动删除混合现实主页中的所有全息影像。</span><span class="sxs-lookup"><span data-stu-id="82678-180">Added a setting in **Settings** > **System** > **Holograms** that allows users to automatically remove all holograms from Mixed Reality home when the device shuts down.</span></span>
- <span data-ttu-id="82678-181">修复了导致 hololens 应用更改像素格式的问题，这些应用会在 HoloLens 模拟器中呈现黑色。</span><span class="sxs-lookup"><span data-stu-id="82678-181">Fixed an issue that caused HoloLens apps that change their pixel format to render black in the HoloLens emulator.</span></span>
- <span data-ttu-id="82678-182">修复了在虹膜登录期间导致崩溃的 bug。</span><span class="sxs-lookup"><span data-stu-id="82678-182">Fixed a bug that caused a crash during Iris login.</span></span>
- <span data-ttu-id="82678-183">修复了有关为现有应用重复下载的应用的问题。</span><span class="sxs-lookup"><span data-stu-id="82678-183">Fixed an issue about repeated store downloads for already-current apps.</span></span>
- <span data-ttu-id="82678-184">修复了一个 bug 以防止沉浸式应用重复打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="82678-184">Fixed a bug to prevent immersive apps from opening Microsoft Edge repeatedly.</span></span>
- <span data-ttu-id="82678-185">修复了从1903版本更新后初始引导中的 "照片" 应用启动时出现的问题。</span><span class="sxs-lookup"><span data-stu-id="82678-185">Fixed an issue with launches of the Photos app in initial boots after updating from the 1903 release.</span></span>
- <span data-ttu-id="82678-186">提高了性能和可靠性。</span><span class="sxs-lookup"><span data-stu-id="82678-186">Improved performance and reliability.</span></span>

## <span data-ttu-id="82678-187">Windows 全息版 1903-2020 更新</span><span class="sxs-lookup"><span data-stu-id="82678-187">Windows Holographic, version 1903 - June 2020 Update</span></span>
- <span data-ttu-id="82678-188">内部版本18362.1064</span><span class="sxs-lookup"><span data-stu-id="82678-188">Build 18362.1064</span></span>

<span data-ttu-id="82678-189">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="82678-189">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="82678-190">如果未指定某些属性，则自定义 MRC 记录器具有新的默认值。</span><span class="sxs-lookup"><span data-stu-id="82678-190">Custom MRC recorders have new default values for certain properties if they aren't specified.</span></span>
  - <span data-ttu-id="82678-191">在 " *MRC 视频" 效果*中：</span><span class="sxs-lookup"><span data-stu-id="82678-191">On the *MRC Video Effect*:</span></span>
    - <span data-ttu-id="82678-192">PreferredHologramPerspective (1 PhotoVideoCamera) </span><span class="sxs-lookup"><span data-stu-id="82678-192">PreferredHologramPerspective (1 PhotoVideoCamera)</span></span>
    - <span data-ttu-id="82678-193">GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式头戴式耳机) # A5</span><span class="sxs-lookup"><span data-stu-id="82678-193">GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Immersive headset))</span></span>
  - <span data-ttu-id="82678-194">在 " *MRC 音频" 效果*中：</span><span class="sxs-lookup"><span data-stu-id="82678-194">On the *MRC Audio Effect*:</span></span>
    - <span data-ttu-id="82678-195">LoopbackGain (Windows Device Portal 中混合现实捕获页面上的当前 "应用音频收益" 值) </span><span class="sxs-lookup"><span data-stu-id="82678-195">LoopbackGain (the current "App Audio Gain" value on the Mixed Reality Capture page in Windows Device Portal)</span></span>
    - <span data-ttu-id="82678-196">MicrophoneGain (Windows Device Portal 中混合现实捕获页面上的当前 "Mic Audio 增益" 值) </span><span class="sxs-lookup"><span data-stu-id="82678-196">MicrophoneGain (the current "Mic Audio Gain" value on the Mixed Reality Capture page in Windows Device Portal)</span></span>
- <span data-ttu-id="82678-197">对于 Unity 应用程序，HolographicSpace 通常禁用 UserPresence API。</span><span class="sxs-lookup"><span data-stu-id="82678-197">The HolographicSpace.UserPresence API is generally disabled for Unity applications.</span></span> <span data-ttu-id="82678-198">此行为可避免在面板翻转时导致某些应用暂停的问题，即使启用了在后台运行的设置也是如此。</span><span class="sxs-lookup"><span data-stu-id="82678-198">This behavior avoids an issue that causes some apps to pause when the visor is flipped up, even if the setting to run in the background is enabled.</span></span> <span data-ttu-id="82678-199">现已针对 Unity 版本2018.4.18 和更高版本以及2019.3.4 和更高版本启用 API。</span><span class="sxs-lookup"><span data-stu-id="82678-199">The API is now enabled for Unity versions 2018.4.18 and later, and 2019.3.4 and later.</span></span>
- <span data-ttu-id="82678-200">修复了导致 hololens 应用更改像素格式的问题，这些应用会在 HoloLens 模拟器中呈现黑色。</span><span class="sxs-lookup"><span data-stu-id="82678-200">Fixed an issue that caused HoloLens apps that change their pixel format to render black in the HoloLens Emulator.</span></span>
- <span data-ttu-id="82678-201">修复了从1903版本更新后初始启动时启动照片应用的问题。</span><span class="sxs-lookup"><span data-stu-id="82678-201">Fixed an issue about launches of the Photos app in initial boots after updating from the 1903 release.</span></span>

## <span data-ttu-id="82678-202">Windows 全息版2004</span><span class="sxs-lookup"><span data-stu-id="82678-202">Windows Holographic, version 2004</span></span>  
- <span data-ttu-id="82678-203">内部版本-19041.1103</span><span class="sxs-lookup"><span data-stu-id="82678-203">Build - 19041.1103</span></span>

<span data-ttu-id="82678-204">适用于 HoloLens 2、 *Windows 全息版、版本 2004* 的2020主要软件更新包括一种令人兴奋的新功能，例如对 Windows Autopilot、应用深色模式、USB 以太网支持 5G/LTE 热点的支持等。</span><span class="sxs-lookup"><span data-stu-id="82678-204">The May 2020 major software update for HoloLens 2, *Windows Holographic, version 2004* includes a host of exciting new capabilities, such as support for Windows Autopilot, app dark mode, USB Ethernet support for 5G/LTE hotspots, and much more.</span></span> <span data-ttu-id="82678-205">若要更新到最新版本，请打开 "**设置**"   应用，转到 " **更新 & 安全**"，然后选择 " **检查更新**"   按钮。</span><span class="sxs-lookup"><span data-stu-id="82678-205">To update to the latest release, open the **Settings** app, go to **Update & Security**, and select the **Check for Updates** button.</span></span> 

|             <span data-ttu-id="82678-206">功能</span><span class="sxs-lookup"><span data-stu-id="82678-206">Feature</span></span>                              |          <span data-ttu-id="82678-207">描述</span><span class="sxs-lookup"><span data-stu-id="82678-207">Description</span></span>                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       <span data-ttu-id="82678-208">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="82678-208">Windows Autopilot</span></span>                          |          <span data-ttu-id="82678-209">使用 Windows AutoPilot 为生产预配置和无缝设置新设备</span><span class="sxs-lookup"><span data-stu-id="82678-209">Pre-configure and seamlessly set up   new devices for production by using Windows AutoPilot</span></span>                 |
|       <span data-ttu-id="82678-210">FIDO 2 支持</span><span class="sxs-lookup"><span data-stu-id="82678-210">FIDO 2 support</span></span>                             |          <span data-ttu-id="82678-211">支持 FIDO2 安全密钥以对共享设备启用快速和安全身份验证</span><span class="sxs-lookup"><span data-stu-id="82678-211">Support for FIDO2 Security Keys to   enable fast and secure authentication for shared devices</span></span>            |
|       <span data-ttu-id="82678-212">改进的预配</span><span class="sxs-lookup"><span data-stu-id="82678-212">Improved provisioning</span></span>                      |          <span data-ttu-id="82678-213">将预配包从 u 盘无缝应用到 HoloLens</span><span class="sxs-lookup"><span data-stu-id="82678-213">Seamlessly apply a provisioning   package from a USB drive to your HoloLens</span></span>                              |
|       <span data-ttu-id="82678-214">应用程序安装状态</span><span class="sxs-lookup"><span data-stu-id="82678-214">Application install status</span></span>                 |          <span data-ttu-id="82678-215">在应用的 "设置" 应用中检查安装状态已通过 MDM 推送到 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="82678-215">Check install status in the Settings app for apps have been pushed to HoloLens 2 via MDM</span></span>               |
|       <span data-ttu-id="82678-216"> (Csp) 的配置服务提供商</span><span class="sxs-lookup"><span data-stu-id="82678-216">Configuration service providers   (CSPs)</span></span>   |          <span data-ttu-id="82678-217">添加了新的配置服务提供程序以增强管理员控制功能</span><span class="sxs-lookup"><span data-stu-id="82678-217">Added new configuration service providers to enhance admin control capabilities</span></span>                 |
|       <span data-ttu-id="82678-218">USB 5G/LTE 支持</span><span class="sxs-lookup"><span data-stu-id="82678-218">USB 5G/LTE support</span></span>                       |          <span data-ttu-id="82678-219">扩展的 USB 以太网功能支持 5G/LTE 支持</span><span class="sxs-lookup"><span data-stu-id="82678-219">Expanded USB Ethernet capability   enables support for 5G/LTE</span></span>                                    |
|       <span data-ttu-id="82678-220">深色应用模式</span><span class="sxs-lookup"><span data-stu-id="82678-220">Dark app mode</span></span>                              |          <span data-ttu-id="82678-221">适用于支持深色模式和浅色模式的应用的深色应用模式，改善了查看体验</span><span class="sxs-lookup"><span data-stu-id="82678-221">Dark app mode available for apps that support both dark and light modes, improving the viewing experience</span></span>        |
|       <span data-ttu-id="82678-222">语音命令</span><span class="sxs-lookup"><span data-stu-id="82678-222">Voice commands</span></span>                             |          <span data-ttu-id="82678-223">支持用于控制 HoloLens 免提的其他系统语音命令</span><span class="sxs-lookup"><span data-stu-id="82678-223">Support for additional system voice   commands to control HoloLens hands-free</span></span>                           |
|       <span data-ttu-id="82678-224">手动跟踪改进</span><span class="sxs-lookup"><span data-stu-id="82678-224">Hand tracking improvements</span></span>                 |          <span data-ttu-id="82678-225">手动跟踪改进使按钮和2D 平板交互更准确</span><span class="sxs-lookup"><span data-stu-id="82678-225">Hand tracking improvements make buttons and 2D slate interactions more accurate</span></span>                        |
|       <span data-ttu-id="82678-226">质量改进和修复</span><span class="sxs-lookup"><span data-stu-id="82678-226">Quality improvements and fixes</span></span>                 |          <span data-ttu-id="82678-227">跨平台的各种系统性能和可靠性改进</span><span class="sxs-lookup"><span data-stu-id="82678-227">Various system performance and   reliability improvements across the platform</span></span>                            |

### <span data-ttu-id="82678-228">Windows Autopilot 支持</span><span class="sxs-lookup"><span data-stu-id="82678-228">Support for Windows Autopilot</span></span>

<span data-ttu-id="82678-229">用于 HoloLens 2 的 Windows Autopilot 允许设备销售渠道预注册 HoloLens 到你的 Intune 租户。</span><span class="sxs-lookup"><span data-stu-id="82678-229">Windows Autopilot for HoloLens 2 lets the device sales channel pre-enroll HoloLens into your Intune tenant.</span></span> <span data-ttu-id="82678-230">当设备到达时，它们准备就绪，可以作为你的租户下的共享设备进行自我部署。</span><span class="sxs-lookup"><span data-stu-id="82678-230">When devices arrive, they’re ready to self-deploy as shared devices under your tenant.</span></span> <span data-ttu-id="82678-231">若要利用自我部署，设备必须在安装过程的第一个屏幕中使用 USB-C-以太网或 USB--LTE 转换器连接到网络。</span><span class="sxs-lookup"><span data-stu-id="82678-231">To take advantage of self-deployment, the device must connect to a network during the first screen in setup by using a USB-C-to-Ethernet or USB-C-to-LTE dongle.</span></span>

<span data-ttu-id="82678-232">用户启动 Autopilot 自部署过程后，该过程将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="82678-232">After a user starts the Autopilot self-deploying process, the process completes the following steps:</span></span>

1. <span data-ttu-id="82678-233">将设备加入 Azure Active Directory (Azure AD)。</span><span class="sxs-lookup"><span data-stu-id="82678-233">Join the device to Azure Active Directory (Azure AD).</span></span>
1. <span data-ttu-id="82678-234">使用 Azure AD 在 Microsoft Intune （或其他 MDM 服务）中注册设备。</span><span class="sxs-lookup"><span data-stu-id="82678-234">Use Azure AD to enroll the device in Microsoft Intune (or another MDM service).</span></span>
1. <span data-ttu-id="82678-235">下载面向设备的策略、证书和网络配置文件。</span><span class="sxs-lookup"><span data-stu-id="82678-235">Download the device-targeted policies, certificates, and networking profiles.</span></span>
1. <span data-ttu-id="82678-236">预配设备。</span><span class="sxs-lookup"><span data-stu-id="82678-236">Provision the device.</span></span>
1. <span data-ttu-id="82678-237">向用户呈现登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="82678-237">Present the sign-in screen to the user.</span></span>

<span data-ttu-id="82678-238">请通过适用于 [HoloLens 2 评估指南的 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="82678-238">Learn more from the [Windows Autopilot for HoloLens 2 evaluation guide](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>

*<span data-ttu-id="82678-239">请与您的帐户管理员联系，立即加入 AutoPilot 预览版。</span><span class="sxs-lookup"><span data-stu-id="82678-239">Contact your Account Manager to join the AutoPilot preview now.</span></span> <span data-ttu-id="82678-240">Autopilot 已准备好的设备即将开始发货。</span><span class="sxs-lookup"><span data-stu-id="82678-240">Autopilot-ready devices will begin shipping soon.</span></span>*

### <span data-ttu-id="82678-241">FIDO2 安全密钥支持</span><span class="sxs-lookup"><span data-stu-id="82678-241">FIDO2 security key support</span></span>

<span data-ttu-id="82678-242">某些用户在工作或学校环境中与其他用户共享一个 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="82678-242">Some users share a HoloLens device with others in a work or school environment.</span></span> <span data-ttu-id="82678-243">因此，用户不必输入长的用户名和密码，就很重要。</span><span class="sxs-lookup"><span data-stu-id="82678-243">So it's important that users can easily without typing long user names and passwords.</span></span> <span data-ttu-id="82678-244">快速身份联机 (FIDO) 允许你组织中的任何人 (Azure AD 租户) 无需输入用户名或密码即可无缝登录到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="82678-244">Fast Identity Online (FIDO) lets anyone in your organization (Azure AD tenant) seamlessly sign-in to HoloLens without entering a user name or password.</span></span>

<span data-ttu-id="82678-245">FIDO2 安全密钥是一种基于标准的 "unphishable" passwordless 身份验证方法，可采用任何形式的外观。</span><span class="sxs-lookup"><span data-stu-id="82678-245">FIDO2 security keys are an "unphishable" standards-based passwordless authentication method that can come in any form factor.</span></span> <span data-ttu-id="82678-246">FIDO 是一种用于 passwordless 身份验证的开放式标准。</span><span class="sxs-lookup"><span data-stu-id="82678-246">FIDO is an open standard for passwordless authentication.</span></span> <span data-ttu-id="82678-247">它允许用户和组织无需用户名或密码即可登录到其资源。</span><span class="sxs-lookup"><span data-stu-id="82678-247">It allows users and organizations to sign in to their resources without a user name or password.</span></span> <span data-ttu-id="82678-248">而是使用内置的安全密钥或内置于设备的平台密钥。</span><span class="sxs-lookup"><span data-stu-id="82678-248">Instead they use an external security key or a platform key built into a device.</span></span>

<span data-ttu-id="82678-249">若要开始使用，请参阅 [启用 passwordless 安全密钥登录](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。</span><span class="sxs-lookup"><span data-stu-id="82678-249">To get started, see [Enable passwordless security key sign-in](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key).</span></span>

### <span data-ttu-id="82678-250">通过预配包改进了 MDM 注册</span><span class="sxs-lookup"><span data-stu-id="82678-250">Improved MDM enrollment via provisioning package</span></span>

<span data-ttu-id="82678-251">预配程序包允许你通过配置文件（而不是 HoloLens 全新体验）设置 HoloLens 配置。</span><span class="sxs-lookup"><span data-stu-id="82678-251">Provisioning packages let you set HoloLens configuration through a config file rather than through the HoloLens out-of-box experience.</span></span> <span data-ttu-id="82678-252">以前，必须将预配包复制到 HoloLens 内部内存。</span><span class="sxs-lookup"><span data-stu-id="82678-252">Previously, provisioning packages had to be copied onto the HoloLens internal memory.</span></span> <span data-ttu-id="82678-253">现在，他们可以在 USB 驱动器上使用，以便更轻松地在多个 HoloLens 设备上重用，并且可以并行预配设备。</span><span class="sxs-lookup"><span data-stu-id="82678-253">Now they can be on a USB drive so they're easier to reuse on multiple HoloLens devices and you can provision devices in parallel.</span></span> <span data-ttu-id="82678-254">预配程序包现在还支持用于注册设备管理的字段，因此预配后无手动设置。</span><span class="sxs-lookup"><span data-stu-id="82678-254">Provisioning packages now also support a field to enroll in device management so there's no manual setup after provisioning.</span></span>

<span data-ttu-id="82678-255">若要试用：</span><span class="sxs-lookup"><span data-stu-id="82678-255">To try it out:</span></span>

1. <span data-ttu-id="82678-256">将 windows 配置设计器的最新版本从 Windows 应用商店下载到你的电脑。</span><span class="sxs-lookup"><span data-stu-id="82678-256">Download the latest version of the Windows Configuration Designer from the Windows store onto your PC.</span></span>
1. <span data-ttu-id="82678-257">选择 "**预配 hololens 设备**"  >  **预配 hololens 2 设备**。</span><span class="sxs-lookup"><span data-stu-id="82678-257">Select **Provision HoloLens Devices** > **Provision HoloLens 2 devices**.</span></span>
2. <span data-ttu-id="82678-258">构建配置文件。</span><span class="sxs-lookup"><span data-stu-id="82678-258">Build your configuration profile.</span></span> <span data-ttu-id="82678-259">然后将创建的所有文件复制到一个 USB-C 存储设备。</span><span class="sxs-lookup"><span data-stu-id="82678-259">Then copy all files that were created to a USB-C storage device.</span></span>
3. <span data-ttu-id="82678-260">将 USB-C 设备插入任何全新刷新的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="82678-260">Plug the USB-C device into any freshly flashed HoloLens.</span></span> <span data-ttu-id="82678-261">然后按**音量按下**  +  **电源**按钮以应用预配包。</span><span class="sxs-lookup"><span data-stu-id="82678-261">Then press the **volume down** + **power** buttons to apply your provisioning package.</span></span>

### <span data-ttu-id="82678-262">业务线应用程序安装状态</span><span class="sxs-lookup"><span data-stu-id="82678-262">Line-of-business application install status</span></span>

<span data-ttu-id="82678-263">适用于 HoloLens 的 MDM 应用部署和业务线应用的管理是 HoloLens 的关键。</span><span class="sxs-lookup"><span data-stu-id="82678-263">MDM app deployment and management for line of business apps is critical to HoloLens.</span></span> <span data-ttu-id="82678-264">管理员和用户需要查看用于审核和诊断的应用安装状态。</span><span class="sxs-lookup"><span data-stu-id="82678-264">Admins and users need to view app install status for auditing and diagnosis.</span></span> <span data-ttu-id="82678-265">在此版本中，我们在**设置**帐户中添加了更多详细信息  >  **Accounts**  >  **访问工作或学校**  >  **单击您的帐户**  >  **信息**。</span><span class="sxs-lookup"><span data-stu-id="82678-265">In this release, we added more details in **Settings** > **Accounts** > **Access work or school** > **Click on your account** > **Info**.</span></span>

### <span data-ttu-id="82678-266">其他 Csp 和策略</span><span class="sxs-lookup"><span data-stu-id="82678-266">Additional CSPs and policies</span></span>

<span data-ttu-id="82678-267">[配置服务提供程序 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)是用于读取、设置、修改或删除设备上的配置设置的接口。</span><span class="sxs-lookup"><span data-stu-id="82678-267">A [configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) is an interface to read, set, modify, or delete configuration settings on a device.</span></span> <span data-ttu-id="82678-268">在此版本中，我们添加了对更多策略的支持，以增加管理员对已部署的 HoloLens 设备的控制。</span><span class="sxs-lookup"><span data-stu-id="82678-268">In this release, we add support for more policies to increase the control administrators have over deployed HoloLens devices.</span></span> <span data-ttu-id="82678-269">有关 HoloLens 支持的 Csp 列表，请参阅 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。</span><span class="sxs-lookup"><span data-stu-id="82678-269">For the list of CSPs supported by HoloLens, see [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span>

<span data-ttu-id="82678-270">此版本中的新增内容：</span><span class="sxs-lookup"><span data-stu-id="82678-270">New in this release:</span></span>

**<span data-ttu-id="82678-271">策略云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="82678-271">Policy CSP</span></span>** 

<span data-ttu-id="82678-272">策略配置服务提供程序使企业能够在 Windows 设备上配置策略。</span><span class="sxs-lookup"><span data-stu-id="82678-272">The Policy configuration service provider enables the enterprise to configure policies on Windows devices.</span></span> <span data-ttu-id="82678-273">在此版本中，我们为 HoloLens 添加了新策略，这些策略将在此处列出。</span><span class="sxs-lookup"><span data-stu-id="82678-273">In this release, we added new policies for HoloLens, which are listed here.</span></span> <span data-ttu-id="82678-274">若要了解详细信息，请参阅 [HoloLens 2 支持的策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)。</span><span class="sxs-lookup"><span data-stu-id="82678-274">To learn more, see [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).</span></span>  

- <span data-ttu-id="82678-275">LetAppsAccessCamera_ForceAllowTheseApps</span><span class="sxs-lookup"><span data-stu-id="82678-275">LetAppsAccessCamera_ForceAllowTheseApps</span></span>  
- <span data-ttu-id="82678-276">LetAppsAccessCamera_ForceDenyTheseApps</span><span class="sxs-lookup"><span data-stu-id="82678-276">LetAppsAccessCamera_ForceDenyTheseApps</span></span>  
- <span data-ttu-id="82678-277">LetAppsAccessCamera_UserInControlOfTheseApps</span><span class="sxs-lookup"><span data-stu-id="82678-277">LetAppsAccessCamera_UserInControlOfTheseApps</span></span> 
- <span data-ttu-id="82678-278">LetAppsAccessGazeInput</span><span class="sxs-lookup"><span data-stu-id="82678-278">LetAppsAccessGazeInput</span></span> 
- <span data-ttu-id="82678-279">LetAppsAccessGazeInput_ForceAllowTheseApps</span><span class="sxs-lookup"><span data-stu-id="82678-279">LetAppsAccessGazeInput_ForceAllowTheseApps</span></span> 
- <span data-ttu-id="82678-280">LetAppsAccessGazeInput_ForceDenyTheseApps</span><span class="sxs-lookup"><span data-stu-id="82678-280">LetAppsAccessGazeInput_ForceDenyTheseApps</span></span> 
- <span data-ttu-id="82678-281">LetAppsAccessGazeInput_UserInControlOfTheseApps</span><span class="sxs-lookup"><span data-stu-id="82678-281">LetAppsAccessGazeInput_UserInControlOfTheseApps</span></span> 
- <span data-ttu-id="82678-282">LetAppsAccessMicrophone_ForceAllowTheseApps</span><span class="sxs-lookup"><span data-stu-id="82678-282">LetAppsAccessMicrophone_ForceAllowTheseApps</span></span> 
- <span data-ttu-id="82678-283">LetAppsAccessMicrophone_ForceDenyTheseApps</span><span class="sxs-lookup"><span data-stu-id="82678-283">LetAppsAccessMicrophone_ForceDenyTheseApps</span></span> 
- <span data-ttu-id="82678-284">LetAppsAccessMicrophone_UserInControlOfTheseApps</span><span class="sxs-lookup"><span data-stu-id="82678-284">LetAppsAccessMicrophone_UserInControlOfTheseApps</span></span> 
- <span data-ttu-id="82678-285">AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="82678-285">AllowWiFi</span></span> 

**<span data-ttu-id="82678-286">NetworkQoSPolicy 云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="82678-286">NetworkQoSPolicy CSP</span></span>**

<span data-ttu-id="82678-287">NetworkQoSPolicy 配置服务提供程序创建网络服务质量 (QoS) 策略。</span><span class="sxs-lookup"><span data-stu-id="82678-287">The NetworkQoSPolicy configuration service provider creates network quality-of-service (QoS) policies.</span></span> <span data-ttu-id="82678-288">QoS 策略根据一组匹配的条件对网络流量执行一组操作。</span><span class="sxs-lookup"><span data-stu-id="82678-288">A QoS policy performs a set of actions on network traffic based on a set of matching conditions.</span></span> <span data-ttu-id="82678-289">若要了解详细信息，请参阅 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。</span><span class="sxs-lookup"><span data-stu-id="82678-289">To learn more, see [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span>

### <span data-ttu-id="82678-290">已展开的 USB 以太网支持 5G/LTE tethered 设备</span><span class="sxs-lookup"><span data-stu-id="82678-290">Expanded USB Ethernet support for 5G/LTE tethered devices</span></span>

<span data-ttu-id="82678-291">已添加支持以启用某些移动宽带设备，如 5G/LTE 电话和 Wi-Fi hotpots，它们通过 USB tethered 到 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="82678-291">Support was added to enable certain mobile broadband devices, such as 5G/LTE phones and Wi-Fi hotpots, when they're tethered to the HoloLens 2 via USB.</span></span> <span data-ttu-id="82678-292">这些设备现在在 " **网络设置** " 中显示为另一个以太网连接。</span><span class="sxs-lookup"><span data-stu-id="82678-292">These devices are now displayed in **network settings** as another Ethernet connection.</span></span> <span data-ttu-id="82678-293">不支持需要外部驱动程序的 (移动宽带设备。 ) 此功能可在 Wi-Fi 不可用时启用高带宽连接，并且 Wi-Fi 的 tethering 没有足够的性能。</span><span class="sxs-lookup"><span data-stu-id="82678-293">(Mobile broadband devices that require an external driver aren't supported.) This functionality enables high-bandwidth connections when Wi-Fi is not available and Wi-Fi tethering isn't performant enough.</span></span> <span data-ttu-id="82678-294">若要了解有关受支持的 USB 设备的详细信息，请参阅 [连接到蓝牙和 USB-C 设备](https://docs.microsoft.com/hololens/hololens-connect-devices)。</span><span class="sxs-lookup"><span data-stu-id="82678-294">To learn more about supported USB devices, see [Connect to Bluetooth and USB-C devices](https://docs.microsoft.com/hololens/hololens-connect-devices).</span></span>  

### <span data-ttu-id="82678-295">手动跟踪改进</span><span class="sxs-lookup"><span data-stu-id="82678-295">Hand tracking improvements</span></span>

<span data-ttu-id="82678-296">此版本包括多项跟踪改进：</span><span class="sxs-lookup"><span data-stu-id="82678-296">This release includes several hand tracking improvements:</span></span>

- <span data-ttu-id="82678-297">**指针具有稳定性：** 现在，系统通过 palm 获取 occluded 时，resists 将对食指进行弯曲。</span><span class="sxs-lookup"><span data-stu-id="82678-297">**Pointing pose stability:** The system now resists bending the index finger when it gets occluded by the palm.</span></span> <span data-ttu-id="82678-298">当你推送按钮、键入、滚动内容等时，此更改可提高精确度。</span><span class="sxs-lookup"><span data-stu-id="82678-298">This change improves the accuracy when you push buttons, type, scroll content, and more!</span></span> 
- <span data-ttu-id="82678-299">**减少了意外的空中点击：** 我们改进了对空中点击手势的检测。</span><span class="sxs-lookup"><span data-stu-id="82678-299">**Reduced accidental air taps:** We improved detection of the air tap gesture.</span></span> <span data-ttu-id="82678-300">现在，在几种常见方案中（例如，当您将手放到您的一侧时），会减少意外激活的次数。</span><span class="sxs-lookup"><span data-stu-id="82678-300">There are now fewer accidental activations in several common scenarios, such as when you drop your hands to your sides.</span></span>
- <span data-ttu-id="82678-301">**用户切换可靠性：** 当您共享设备时，系统现在可以更快、更可靠地更新手形大小。</span><span class="sxs-lookup"><span data-stu-id="82678-301">**User switch reliability:** The system is now faster and more reliable at updating the hand size when you share a device.</span></span>
- <span data-ttu-id="82678-302">**减少右手偷窃：** 我们改进了对传感器的两次手的处理情形。</span><span class="sxs-lookup"><span data-stu-id="82678-302">**Reduced hand stealing:** We improved handling of cases where there are more than two hands in view of the sensors.</span></span> <span data-ttu-id="82678-303">如果多人一起密切协作，现在，所跟踪的手势将从用户 "跳转" 到场景中其他人的手边。</span><span class="sxs-lookup"><span data-stu-id="82678-303">If multiple people are working close together, there's now a much lower chance that the tracked hand will "jump" from the user to the hand of someone else in the scene.</span></span>
- <span data-ttu-id="82678-304">**系统可靠性：** 修复了当设备处于高负载时导致手动跟踪停止工作的问题。</span><span class="sxs-lookup"><span data-stu-id="82678-304">**System reliability:** Fixed an issue that caused hand tracking to stop working when the device is under high load.</span></span>

### <span data-ttu-id="82678-305">深色模式</span><span class="sxs-lookup"><span data-stu-id="82678-305">Dark mode</span></span>

<span data-ttu-id="82678-306">许多 Windows 应用现在支持深色模式和浅色模式。</span><span class="sxs-lookup"><span data-stu-id="82678-306">Many Windows apps now support both dark and light modes.</span></span> <span data-ttu-id="82678-307">HoloLens 2 用户可以为支持两者的应用选择默认模式。</span><span class="sxs-lookup"><span data-stu-id="82678-307">HoloLens 2 users can choose the default mode for apps that support both.</span></span> <span data-ttu-id="82678-308">更新后，默认应用模式为 "深色"，但你可以轻松地更改此设置：导航到 "**设置**"  >  **系统**  >  **颜色**  >  **选择默认应用模式**。</span><span class="sxs-lookup"><span data-stu-id="82678-308">After the update, the default app mode is "dark," but you can easily change this setting: Navigate to **Settings** > **System** > **Colors** > **Choose your default app mode**.</span></span> 

<span data-ttu-id="82678-309">这些 "机箱中" 应用支持深色模式：</span><span class="sxs-lookup"><span data-stu-id="82678-309">These "in-box" apps support dark mode:</span></span> 

- <span data-ttu-id="82678-310">“设置”</span><span class="sxs-lookup"><span data-stu-id="82678-310">Settings</span></span> 
- <span data-ttu-id="82678-311">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="82678-311">Microsoft Store</span></span> 
- <span data-ttu-id="82678-312">Mail</span><span class="sxs-lookup"><span data-stu-id="82678-312">Mail</span></span> 
- <span data-ttu-id="82678-313">日历</span><span class="sxs-lookup"><span data-stu-id="82678-313">Calendar</span></span> 
- <span data-ttu-id="82678-314">文件资源管理器</span><span class="sxs-lookup"><span data-stu-id="82678-314">File Explorer</span></span> 
- <span data-ttu-id="82678-315">反馈中心</span><span class="sxs-lookup"><span data-stu-id="82678-315">Feedback Hub</span></span> 
- <span data-ttu-id="82678-316">OneDrive</span><span class="sxs-lookup"><span data-stu-id="82678-316">OneDrive</span></span> 
- <span data-ttu-id="82678-317">照片</span><span class="sxs-lookup"><span data-stu-id="82678-317">Photos</span></span> 
- <span data-ttu-id="82678-318">3D 查看器</span><span class="sxs-lookup"><span data-stu-id="82678-318">3D Viewer</span></span> 
- <span data-ttu-id="82678-319">电影和电视</span><span class="sxs-lookup"><span data-stu-id="82678-319">Movies & TV</span></span> 

![深色模式窗口平铺](images/DarkMode.jpg)

### <span data-ttu-id="82678-321">系统语音命令</span><span class="sxs-lookup"><span data-stu-id="82678-321">System voice commands</span></span>

<span data-ttu-id="82678-322">现在，你可以将语音命令与设备上的任何应用配合使用。</span><span class="sxs-lookup"><span data-stu-id="82678-322">You can now use voice commands with any app on the device.</span></span> <span data-ttu-id="82678-323">有关详细信息，请参阅 [使用语音操作 HoloLens](https://docs.microsoft.com/hololens/hololens-cortana)。</span><span class="sxs-lookup"><span data-stu-id="82678-323">For more information, see [Use your voice to operate HoloLens](https://docs.microsoft.com/hololens/hololens-cortana).</span></span> <span data-ttu-id="82678-324">另请参阅 [HoloLens 2 支持的语言](https://docs.microsoft.com/hololens/hololens2-language-support)。</span><span class="sxs-lookup"><span data-stu-id="82678-324">Also see [Supported languages for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-language-support).</span></span>  

### <span data-ttu-id="82678-325">Cortana 更新</span><span class="sxs-lookup"><span data-stu-id="82678-325">Cortana updates</span></span>

<span data-ttu-id="82678-326">已更新的应用与 Microsoft 365 集成以帮助你在设备上进行更多的操作 (当前仅 US-English) 。</span><span class="sxs-lookup"><span data-stu-id="82678-326">The updated app integrates with Microsoft 365 to help you get more done across your devices (currently in US-English only).</span></span> <span data-ttu-id="82678-327">在 HoloLens 2 上，Cortana 不再支持特定于设备的命令，如调整音量或重启。</span><span class="sxs-lookup"><span data-stu-id="82678-327">On HoloLens 2, Cortana no longer supports certain device-specific commands, like adjusting volume or restarting.</span></span> <span data-ttu-id="82678-328">新的系统语音命令现在支持这些选项。</span><span class="sxs-lookup"><span data-stu-id="82678-328">These options are now supported by the new system voice commands.</span></span> <span data-ttu-id="82678-329">在我们的 [博客](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)中了解有关新的 Cortana 应用的详细信息。</span><span class="sxs-lookup"><span data-stu-id="82678-329">Learn more about the new Cortana app in our [blog](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).</span></span>

### <span data-ttu-id="82678-330">质量改进和修复</span><span class="sxs-lookup"><span data-stu-id="82678-330">Quality improvements and fixes</span></span>

<span data-ttu-id="82678-331">更新中也有改进和修复：</span><span class="sxs-lookup"><span data-stu-id="82678-331">Improvements and fixes also in the update:</span></span>  
- <span data-ttu-id="82678-332">引入了活动的显示校准系统。</span><span class="sxs-lookup"><span data-stu-id="82678-332">Introduced an active display calibration system.</span></span> <span data-ttu-id="82678-333">此功能可改善全息影像的稳定性和对齐方式。</span><span class="sxs-lookup"><span data-stu-id="82678-333">This feature improves the stability and alignment of holograms.</span></span> <span data-ttu-id="82678-334">当您的打印头并排移动时，它们将保留在原地。</span><span class="sxs-lookup"><span data-stu-id="82678-334">They now stay in place when you move your head from side to side.</span></span>
- <span data-ttu-id="82678-335">修复了 Wi-Fi 到 HoloLens 的数据流定期中断的 bug。</span><span class="sxs-lookup"><span data-stu-id="82678-335">Fixed a bug where Wi-Fi streaming to HoloLens got disrupted periodically.</span></span> <span data-ttu-id="82678-336">如果应用程序指示它需要低延迟流，请通过调用 [SetSocketMediaStreamingMode 函数](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)来实现修复。</span><span class="sxs-lookup"><span data-stu-id="82678-336">If an application indicates that it needs low latency streaming, implement the fix by calling the [SetSocketMediaStreamingMode function](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).</span></span>
- <span data-ttu-id="82678-337">修复了在研究模式下流式处理期间发生的设备挂起。</span><span class="sxs-lookup"><span data-stu-id="82678-337">Fixed a device hang that occurred during streaming in research mode.</span></span>
- <span data-ttu-id="82678-338">修复了一个 bug，在某些情况下，在恢复会话时，在登录屏幕上无法显示正确的用户。</span><span class="sxs-lookup"><span data-stu-id="82678-338">Fixed a bug where in some cases the right user wouldn't be displayed on the sign-in screen when resuming a session.</span></span>
- <span data-ttu-id="82678-339">修复了用户无法通过 **设置**导出 MDM 日志的问题。</span><span class="sxs-lookup"><span data-stu-id="82678-339">Fixed an issue where users couldn't export MDM logs through **Settings**.</span></span>
- <span data-ttu-id="82678-340">修复了立即关注全新设置的目视跟踪的问题，这可能比预期的要低。</span><span class="sxs-lookup"><span data-stu-id="82678-340">Fixed an issue where the accuracy of eye tracking immediately following out-of-box setup could be lower than expected.</span></span>
- <span data-ttu-id="82678-341">修复了目视跟踪子系统无法在特定条件下初始化或执行校准的问题。</span><span class="sxs-lookup"><span data-stu-id="82678-341">Fixed an issue where the eye tracking subsystem failed to initialize or perform calibration under certain conditions.</span></span>
- <span data-ttu-id="82678-342">修复了提示校准已校准用户的问题。</span><span class="sxs-lookup"><span data-stu-id="82678-342">Fixed an issue where eye calibration would be prompted for an already-calibrated user.</span></span>
- <span data-ttu-id="82678-343">修复了在目视校准期间驱动程序崩溃的问题。</span><span class="sxs-lookup"><span data-stu-id="82678-343">Fixed an issue where a driver would crash during eye calibration.</span></span>
- <span data-ttu-id="82678-344">修复了重复的电源按钮按下可能导致60秒系统超时和外壳崩溃的问题。</span><span class="sxs-lookup"><span data-stu-id="82678-344">Fixed an issue where repeated power button presses could cause a 60-second system timeout and shell crash.</span></span>
- <span data-ttu-id="82678-345">改善了深度缓冲区的稳定性。</span><span class="sxs-lookup"><span data-stu-id="82678-345">Improved stability for depth buffers.</span></span>
- <span data-ttu-id="82678-346">在 "反馈中心" 添加了 " **共享** " 按钮，以便用户可以更轻松地共享反馈。</span><span class="sxs-lookup"><span data-stu-id="82678-346">Added a **Share** button in the Feedback Hub so users can more easily share feedback.</span></span>
- <span data-ttu-id="82678-347">修复了 RoboRaid wan't 正确安装的 bug。</span><span class="sxs-lookup"><span data-stu-id="82678-347">Fixed a bug where RoboRaid wan't installed correctly.</span></span>

### <span data-ttu-id="82678-348">已知问题</span><span class="sxs-lookup"><span data-stu-id="82678-348">Known issues</span></span>

- <span data-ttu-id="82678-349">Zh-cn&platform 系统语言的问题阻止语音命令接受混合现实捕获或显示设备 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="82678-349">An issue with the zh-CN system language prevents voice commands from taking a mixed reality capture or displaying the device IP address.</span></span>
- <span data-ttu-id="82678-350">问题要求你在启动设备后启动 Cortana 应用以使用 "你好 Cortana" 语音激活。</span><span class="sxs-lookup"><span data-stu-id="82678-350">An issue requires you to launch the Cortana app after starting the device to use "Hey Cortana" voice activation.</span></span> <span data-ttu-id="82678-351">如果从18362版本更新，你可能还会看到以前版本的 Cortana 应用的第二个应用磁贴，在 **开始**时不再有效。</span><span class="sxs-lookup"><span data-stu-id="82678-351">If you updated from a 18362 build, you may also see a second app tile for the previous version of the Cortana app that no longer works in **Start**.</span></span>

## <span data-ttu-id="82678-352">Windows 全息版 1903-五月2020更新</span><span class="sxs-lookup"><span data-stu-id="82678-352">Windows Holographic, version 1903 - May 2020 Update</span></span> 
- <span data-ttu-id="82678-353">内部版本18362.1061</span><span class="sxs-lookup"><span data-stu-id="82678-353">Build 18362.1061</span></span>

<span data-ttu-id="82678-354">此每月质量更新不包含任何显著的更改，因为团队正在处理 Windows 全息版本2004可能会更新，如前文所述。</span><span class="sxs-lookup"><span data-stu-id="82678-354">This monthly quality update doesn't contain any notable changes because the team was working on the Windows Holographic version 2004 May Update, as described earlier.</span></span>

## <span data-ttu-id="82678-355">Windows 全息版 1903-2020 年4月更新</span><span class="sxs-lookup"><span data-stu-id="82678-355">Windows Holographic, version 1903 - April 2020 Update</span></span>
- <span data-ttu-id="82678-356">内部版本18362.1059</span><span class="sxs-lookup"><span data-stu-id="82678-356">Build 18362.1059</span></span>

**<span data-ttu-id="82678-357">支持的应用的深色模式</span><span class="sxs-lookup"><span data-stu-id="82678-357">Dark mode for supported apps</span></span>** 

<span data-ttu-id="82678-358">许多 Windows 应用均支持深色模式和浅色模式。</span><span class="sxs-lookup"><span data-stu-id="82678-358">Many Windows apps support both dark and light mode.</span></span> <span data-ttu-id="82678-359">HoloLens 2 客户现在可以为支持两种配色方案的应用选择默认模式。</span><span class="sxs-lookup"><span data-stu-id="82678-359">HoloLens 2 customers can now choose the default mode for apps that support both color schemes.</span></span> <span data-ttu-id="82678-360">根据客户反馈，我们将默认应用模式设置为 "深色"，但你可以随时轻松地更改此设置：导航到 " **设置" > "系统 > 颜色** " 以找到 **"选择默认应用模式"。**</span><span class="sxs-lookup"><span data-stu-id="82678-360">Based on customer feedback, we set the default app mode to "dark," but you can easily change this setting at any time: Navigate to **Settings > System > Colors** to find **"Choose your default app mode."**</span></span>

<span data-ttu-id="82678-361">这些 "机箱中" 应用支持深色模式：</span><span class="sxs-lookup"><span data-stu-id="82678-361">These "in-box" apps support dark mode:</span></span>
- <span data-ttu-id="82678-362">“设置”</span><span class="sxs-lookup"><span data-stu-id="82678-362">Settings</span></span>
- <span data-ttu-id="82678-363">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="82678-363">Microsoft Store</span></span>
- <span data-ttu-id="82678-364">Mail</span><span class="sxs-lookup"><span data-stu-id="82678-364">Mail</span></span>
- <span data-ttu-id="82678-365">日历</span><span class="sxs-lookup"><span data-stu-id="82678-365">Calendar</span></span>
- <span data-ttu-id="82678-366">文件资源管理器</span><span class="sxs-lookup"><span data-stu-id="82678-366">File Explorer</span></span>
- <span data-ttu-id="82678-367">反馈中心</span><span class="sxs-lookup"><span data-stu-id="82678-367">Feedback Hub</span></span>
- <span data-ttu-id="82678-368">OneDrive</span><span class="sxs-lookup"><span data-stu-id="82678-368">OneDrive</span></span>
- <span data-ttu-id="82678-369">照片</span><span class="sxs-lookup"><span data-stu-id="82678-369">Photos</span></span>
- <span data-ttu-id="82678-370">3D 查看器</span><span class="sxs-lookup"><span data-stu-id="82678-370">3D Viewer</span></span>
- <span data-ttu-id="82678-371">电影和电视</span><span class="sxs-lookup"><span data-stu-id="82678-371">Movies & TV</span></span>

**<span data-ttu-id="82678-372">更新中也有改进和修复：</span><span class="sxs-lookup"><span data-stu-id="82678-372">Improvements and fixes also in the update:</span></span>** 
- <span data-ttu-id="82678-373">确保在混合现实捕获中包含外壳覆盖。</span><span class="sxs-lookup"><span data-stu-id="82678-373">Ensured that shell overlays are included in mixed reality captures.</span></span>
- <span data-ttu-id="82678-374">Unreal 开发人员现在可以使用 Device Portal 中的3D 视图页面来测试和调试其应用程序。</span><span class="sxs-lookup"><span data-stu-id="82678-374">Unreal developers can now use the 3D View page in Device Portal to test and debug their applications.</span></span>
- <span data-ttu-id="82678-375">在使用 *HolographicDepthReprojectionMethod DepthReprojection* 算法时，在混合现实捕获中改进了全息图稳定性。</span><span class="sxs-lookup"><span data-stu-id="82678-375">Improved hologram stability in mixed reality capture when the *HolographicDepthReprojectionMethod DepthReprojection* algorithm is used.</span></span>
- <span data-ttu-id="82678-376">修复了32位 ARM 应用上的 "WinRT IStreamSocketListener API 类未注册" 错误。</span><span class="sxs-lookup"><span data-stu-id="82678-376">Fixed the "WinRT IStreamSocketListener API Class not registered" error on 32-bit ARM apps.</span></span>

## <span data-ttu-id="82678-377">Windows 全息版、版本 1903-2020 更新</span><span class="sxs-lookup"><span data-stu-id="82678-377">Windows Holographic, version 1903 - March 2020 Update</span></span> 
- <span data-ttu-id="82678-378">内部版本18362.1056</span><span class="sxs-lookup"><span data-stu-id="82678-378">Build 18362.1056</span></span>

<span data-ttu-id="82678-379">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="82678-379">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="82678-380">在使用 *HolographicDepthReprojectionMethod AutoPlanar* 算法时，在混合现实捕获中改进了全息图稳定性。</span><span class="sxs-lookup"><span data-stu-id="82678-380">Improved hologram stability in mixed reality capture when the *HolographicDepthReprojectionMethod AutoPlanar* algorithm is used.</span></span>
- <span data-ttu-id="82678-381">已确保连接到 depth MF 示例的坐标系与公共文档一致。</span><span class="sxs-lookup"><span data-stu-id="82678-381">Ensured that the coordinate system attached to a depth MF sample is consistent with public documentation.</span></span>
- <span data-ttu-id="82678-382">通过让客户通过 device portal 粘贴大量文本，提高了开发人员的工作效率。</span><span class="sxs-lookup"><span data-stu-id="82678-382">Improved developer productivity by enabling customers to paste large amounts of text through the device portal.</span></span>

## <span data-ttu-id="82678-383">Windows 全息版 1903-2 月2020更新</span><span class="sxs-lookup"><span data-stu-id="82678-383">Windows Holographic, version 1903 - February 2020 Update</span></span> 
- <span data-ttu-id="82678-384">内部版本18362.1053</span><span class="sxs-lookup"><span data-stu-id="82678-384">Build 18362.1053</span></span>

<span data-ttu-id="82678-385">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="82678-385">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="82678-386">已暂时禁用 Unity 应用程序的 UserPresence API HolographicSpace。</span><span class="sxs-lookup"><span data-stu-id="82678-386">Temporarily disabled the HolographicSpace.UserPresence API for Unity applications.</span></span> <span data-ttu-id="82678-387">此更改避免了在面板翻转时导致某些应用暂停的问题，即使 "在后台运行" 设置也是如此。</span><span class="sxs-lookup"><span data-stu-id="82678-387">This change avoids an issue that caused some apps to pause when the visor was flipped up, even if the "run in the background" setting was enabled.</span></span>
- <span data-ttu-id="82678-388">修复了手动跟踪导致的随机 HUP 崩溃，在此情况下，用户注意到 UI 冻结，然后在几秒钟后返回到外壳。</span><span class="sxs-lookup"><span data-stu-id="82678-388">Fixed a random HUP crash caused by hand tracking, in which the user noticed a UI freeze then back to shell after several seconds.</span></span>
- <span data-ttu-id="82678-389">改善了手动跟踪，以便在您用食指向您外出时，该手指的上半部分不太可能意外卷曲。</span><span class="sxs-lookup"><span data-stu-id="82678-389">Improved hand tracking so that when you poke with your index finger, the upper part of that finger is less likely to curl unexpectedly.</span></span>
- <span data-ttu-id="82678-390">改进了 head 跟踪、空间映射和其他运行时的可靠性。</span><span class="sxs-lookup"><span data-stu-id="82678-390">Improved reliability of head tracking, spatial mapping, and other runtimes.</span></span>

## <span data-ttu-id="82678-391">Windows 全息版 1903-2020 更新</span><span class="sxs-lookup"><span data-stu-id="82678-391">Windows Holographic, version 1903 - January 2020 Update</span></span> 
- <span data-ttu-id="82678-392">内部版本18362.1043</span><span class="sxs-lookup"><span data-stu-id="82678-392">Build 18362.1043</span></span>
 
<span data-ttu-id="82678-393">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="82678-393">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="82678-394">使用 HoloLens 2 模拟器时，改进了独占应用的稳定性。</span><span class="sxs-lookup"><span data-stu-id="82678-394">Improved stability for exclusive apps when working with the HoloLens 2 emulator.</span></span>

## <span data-ttu-id="82678-395">Windows 全息版 1903-2019 更新</span><span class="sxs-lookup"><span data-stu-id="82678-395">Windows Holographic, version 1903 - December 2019 Update</span></span> 
- <span data-ttu-id="82678-396">内部版本18362.1042</span><span class="sxs-lookup"><span data-stu-id="82678-396">Build 18362.1042</span></span>

<span data-ttu-id="82678-397">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="82678-397">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="82678-398">引入了上一阶段复制 (LSR) 修复。</span><span class="sxs-lookup"><span data-stu-id="82678-398">Introduced last stage reproduction (LSR) fixes.</span></span> <span data-ttu-id="82678-399">改进了全息图的视觉呈现，使其更准确地获得更稳定的深度。</span><span class="sxs-lookup"><span data-stu-id="82678-399">Improved visual rendering of holograms to appear more stable and crisp by more accurately accounting for their depth.</span></span> <span data-ttu-id="82678-400">如果应用未正确设置全息影像的深度，此更新后的症状将更明显。</span><span class="sxs-lookup"><span data-stu-id="82678-400">This symptom will be more noticeable after this update if apps don't set the depth of holograms correctly.</span></span>
- <span data-ttu-id="82678-401">固定应用和独占应用之间导航的固定稳定性。</span><span class="sxs-lookup"><span data-stu-id="82678-401">Fixed stability of exclusive apps and navigation between exclusive apps.</span></span>
- <span data-ttu-id="82678-402">解决了在设备处于待机状态几天后混合现实捕获无法录制视频的问题。</span><span class="sxs-lookup"><span data-stu-id="82678-402">Resolved an issue where mixed reality capture couldn't record video after the device was in standby state for several days.</span></span>
- <span data-ttu-id="82678-403">改进了全息图稳定性。</span><span class="sxs-lookup"><span data-stu-id="82678-403">Improved hologram stability.</span></span>

## <span data-ttu-id="82678-404">Windows 全息版、版本 1903-2019 更新</span><span class="sxs-lookup"><span data-stu-id="82678-404">Windows Holographic, version 1903 - November 2019 Update</span></span> 
- <span data-ttu-id="82678-405">内部版本18362.1039</span><span class="sxs-lookup"><span data-stu-id="82678-405">Build 18362.1039</span></span>

<span data-ttu-id="82678-406">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="82678-406">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="82678-407">固定的功能：在初始设置中为 en-us 和 en-us **选择** 语音命令。</span><span class="sxs-lookup"><span data-stu-id="82678-407">Fixed functionality of **Select** voice commands during initial setup for en-CA and en-AU.</span></span>
- <span data-ttu-id="82678-408">改进了在最新的 Unity 和混合现实工具包中最远地放置的对象的视觉质量 (MRTK) 版本。</span><span class="sxs-lookup"><span data-stu-id="82678-408">Improved visual quality of objects placed far away in the latest Unity and Mixed Reality Toolkit (MRTK) versions.</span></span>
- <span data-ttu-id="82678-409">修复了在启动时，全息应用程序在处于暂停状态时处于暂停状态的问题，直到打开 "开始" 菜单，然后关闭。</span><span class="sxs-lookup"><span data-stu-id="82678-409">Fixed addressing issues with holographic applications getting stuck in a paused state on startup until the Start menu was opened and then closed.</span></span>
- <span data-ttu-id="82678-410">适用于 HoloLens 2 和模拟器的 OpenXR 运行时一致性修复和改进。</span><span class="sxs-lookup"><span data-stu-id="82678-410">OpenXR runtime conformance fixes and improvements for HoloLens 2 and the emulator.</span></span>
