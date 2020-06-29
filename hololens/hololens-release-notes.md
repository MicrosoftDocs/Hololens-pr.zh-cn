---
title: HoloLens 2 发行说明
description: 了解每个新的 HoloLens 版本中的更新。
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
ms.openlocfilehash: 25a1bc21638090cc5d22bc4482299f3931641dea
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827923"
---
# <span data-ttu-id="f7385-103">HoloLens 2 发行说明</span><span class="sxs-lookup"><span data-stu-id="f7385-103">HoloLens 2 release notes</span></span>

<span data-ttu-id="f7385-104">为确保您的 HoloLens 设备具有高效的体验，我们将继续发布功能、bug 和安全更新。</span><span class="sxs-lookup"><span data-stu-id="f7385-104">To ensure you have a productive experience with your HoloLens devices, we continue to release feature, bug and security updates.</span></span> <span data-ttu-id="f7385-105">在此页面中，您可以了解每月 HoloLens 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="f7385-105">In this page you can learn about what’s new on HoloLens each month.</span></span> <span data-ttu-id="f7385-106">如果你想要下载最新的 HoloLens 2 FFU 以通过 "[高级恢复助理](hololens-recovery.md#clean-reflash-the-device)" 刷新你的设备，你可以从[此处](https://aka.ms/hololens2download)下载。</span><span class="sxs-lookup"><span data-stu-id="f7385-106">If you would like to download the latest HoloLens 2 FFU to flash your device via [Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) then you may download it from [here](https://aka.ms/hololens2download).</span></span> <span data-ttu-id="f7385-107">这将保持最新，并且将与最新的通用内部版本匹配。</span><span class="sxs-lookup"><span data-stu-id="f7385-107">This is kept up-to-date and will match the latest generally available build.</span></span> 

<span data-ttu-id="f7385-108">HoloLens 模拟器发行说明可在[此处](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)找到。</span><span class="sxs-lookup"><span data-stu-id="f7385-108">HoloLens Emulator Release Notes can be found [here](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive).</span></span>

## <span data-ttu-id="f7385-109">Windows 全息版 2004-2020 更新</span><span class="sxs-lookup"><span data-stu-id="f7385-109">Windows Holographic, version 2004 - June 2020 Update</span></span>
- <span data-ttu-id="f7385-110">内部版本19041.1106</span><span class="sxs-lookup"><span data-stu-id="f7385-110">Build 19041.1106</span></span>

<span data-ttu-id="f7385-111">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="f7385-111">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="f7385-112">如果未指定某些属性，则自定义 MRC 记录器具有新的默认值。</span><span class="sxs-lookup"><span data-stu-id="f7385-112">Custom MRC recorders have new default values for certain properties if they aren't specified.</span></span>
  - <span data-ttu-id="f7385-113">在 "MRC 视频" 效果中：</span><span class="sxs-lookup"><span data-stu-id="f7385-113">On the MRC Video Effect:</span></span>
    - <span data-ttu-id="f7385-114">PreferredHologramPerspective （1 PhotoVideoCamera）</span><span class="sxs-lookup"><span data-stu-id="f7385-114">PreferredHologramPerspective (1 PhotoVideoCamera)</span></span>
    - <span data-ttu-id="f7385-115">GlobalOpacityCoefficient （0.9 （HoloLens）1.0 （沉浸式头戴式耳机））</span><span class="sxs-lookup"><span data-stu-id="f7385-115">GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Immersive headset))</span></span>
  - <span data-ttu-id="f7385-116">在 "MRC 音频" 效果中：</span><span class="sxs-lookup"><span data-stu-id="f7385-116">On the MRC Audio Effect:</span></span>
    - <span data-ttu-id="f7385-117">LoopbackGain （Windows Device Portal 中混合现实捕获页面上的当前 "应用音频增益" 值）</span><span class="sxs-lookup"><span data-stu-id="f7385-117">LoopbackGain (the current "App Audio Gain" value on the Mixed Reality Capture page in Windows Device Portal)</span></span>
    - <span data-ttu-id="f7385-118">MicrophoneGain （Windows Device Portal 中混合现实捕获页面上的当前 "Mic Audio 增益" 值）</span><span class="sxs-lookup"><span data-stu-id="f7385-118">MicrophoneGain (the current "Mic Audio Gain" value on the Mixed Reality Capture page in Windows Device Portal)</span></span>
- <span data-ttu-id="f7385-119">此更新包含一个可在混合现实捕获方案中提高音频质量的 bug 修复。</span><span class="sxs-lookup"><span data-stu-id="f7385-119">This update contains a bug fix that improves audio quality in Mixed Reality Capture scenarios.</span></span> <span data-ttu-id="f7385-120">尤其是，在显示 "开始" 菜单时，它应该消除录制中的任何音频 glitching。</span><span class="sxs-lookup"><span data-stu-id="f7385-120">Specifically, it should eliminate any audio glitching in the recording when the Start Menu is displayed.</span></span>
- <span data-ttu-id="f7385-121">改进了录制视频中的全息图稳定性。</span><span class="sxs-lookup"><span data-stu-id="f7385-121">Improved hologram stability in recorded videos.</span></span>
- <span data-ttu-id="f7385-122">解决了混合现实捕获在设备离开待机状态几天后无法录制视频的问题。</span><span class="sxs-lookup"><span data-stu-id="f7385-122">Resolves an issue where mixed reality capture couldn't record video after device is left in standby state for multiple days.</span></span>
- <span data-ttu-id="f7385-123">对于 Unity 应用程序，UserPresence API 通常是禁用的，以避免在面板翻转时导致某些应用暂停的问题，即使在后台运行的设置处于启用状态时也是如此。</span><span class="sxs-lookup"><span data-stu-id="f7385-123">The HolographicSpace.UserPresence API is generally disabled for Unity applications to avoid an issue which causes some apps to pause when the visor is flipped up, even if the setting to run in the background is enabled.</span></span> <span data-ttu-id="f7385-124">现已针对 Unity 版本2018.4.18 及更高版本、2019.3.4 和更高版本启用 API。</span><span class="sxs-lookup"><span data-stu-id="f7385-124">The API is now enabled for Unity versions 2018.4.18 and higher, and 2019.3.4 and higher.</span></span>
- <span data-ttu-id="f7385-125">通过 WiFi 连接访问 Device Portal 时，web 浏览器可能会阻止访问，因为证书无效、报告诸如 "ERR_SSL_PROTOCOL_ERROR" 之类的错误，即使设备证书以前已受信任。</span><span class="sxs-lookup"><span data-stu-id="f7385-125">When accessing Device Portal over a WiFi connection, a web browser might prevent access to due to an invalid certificate, reporting an error such as "ERR_SSL_PROTOCOL_ERROR," even if the device certificate has previously been trusted.</span></span>  <span data-ttu-id="f7385-126">在这种情况下，你将无法对 Device Portal 进行处理，因为忽略安全警告的选项不可用。</span><span class="sxs-lookup"><span data-stu-id="f7385-126">In this case, you would be unable to progress to Device Portal as options to ignore security warnings are not available.</span></span>  <span data-ttu-id="f7385-127">此更新可解决此问题。</span><span class="sxs-lookup"><span data-stu-id="f7385-127">This update resolves the issue.</span></span>  <span data-ttu-id="f7385-128">如果设备证书以前已在电脑上下载并受信任，用于删除浏览器安全警告，并且遇到 SSL 错误，则需要下载新证书并信任该证书才能解决浏览器安全警告。</span><span class="sxs-lookup"><span data-stu-id="f7385-128">If the device certificate was previously downloaded and trusted on a PC to remove browser security warnings and the SSL error has been encountered, the new certificate will need to be downloaded and trusted to address browser security warnings.</span></span>
- <span data-ttu-id="f7385-129">支持创建可使用 MSIX 程序包安装应用的运行时预配包的功能。</span><span class="sxs-lookup"><span data-stu-id="f7385-129">Enabled ability to create a runtime provisioning package which can install an app using MSIX packages.</span></span>
- <span data-ttu-id="f7385-130">用户可以在设置 > 系统 > 全息影像下找到的新设置，允许用户在设备关闭时自动删除混合现实家庭中的所有全息影像。</span><span class="sxs-lookup"><span data-stu-id="f7385-130">New setting that users can find under Settings > System > Holograms, that allows users to automatically remove all holograms from the mixed reality home when the device shuts down.</span></span>
- <span data-ttu-id="f7385-131">修复了导致 hololens 应用更改像素格式的问题，这些应用会在 HoloLens 模拟器中呈现黑色。</span><span class="sxs-lookup"><span data-stu-id="f7385-131">Fixed an issue that caused HoloLens apps that change their pixel format to render black in the HoloLens emulator.</span></span>
- <span data-ttu-id="f7385-132">修复了在虹膜登录期间导致崩溃的 bug。</span><span class="sxs-lookup"><span data-stu-id="f7385-132">Fixed bug that caused a crash during Iris Login.</span></span>
- <span data-ttu-id="f7385-133">修复了现有应用的重复应用商店下载问题。</span><span class="sxs-lookup"><span data-stu-id="f7385-133">Fixes an issue around repeated store downloads for already current apps.</span></span>
- <span data-ttu-id="f7385-134">修复了一个 bug 以防止沉浸式应用多次启动边缘。</span><span class="sxs-lookup"><span data-stu-id="f7385-134">Fixed a bug to preventing immersive apps from launching Edge multiple times.</span></span>
- <span data-ttu-id="f7385-135">修复了从1903版本更新后初始引导中的 "照片" 应用程序启动时出现的问题。</span><span class="sxs-lookup"><span data-stu-id="f7385-135">Fixes an issue around launches of the Photos app in initial boots after updating from the 1903 release.</span></span>
- <span data-ttu-id="f7385-136">提高了性能和可靠性。</span><span class="sxs-lookup"><span data-stu-id="f7385-136">Improved performance and reliability.</span></span>

## <span data-ttu-id="f7385-137">Windows 全息版 1903-2020 更新</span><span class="sxs-lookup"><span data-stu-id="f7385-137">Windows Holographic, version 1903 - June 2020 Update</span></span>
- <span data-ttu-id="f7385-138">内部版本18362.1064</span><span class="sxs-lookup"><span data-stu-id="f7385-138">Build 18362.1064</span></span>

<span data-ttu-id="f7385-139">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="f7385-139">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="f7385-140">如果未指定某些属性，则自定义 MRC 记录器具有新的默认值。</span><span class="sxs-lookup"><span data-stu-id="f7385-140">Custom MRC recorders have new default values for certain properties if they aren't specified.</span></span>
  - <span data-ttu-id="f7385-141">在 "MRC 视频" 效果中：</span><span class="sxs-lookup"><span data-stu-id="f7385-141">On the MRC Video Effect:</span></span>
    - <span data-ttu-id="f7385-142">PreferredHologramPerspective （1 PhotoVideoCamera）</span><span class="sxs-lookup"><span data-stu-id="f7385-142">PreferredHologramPerspective (1 PhotoVideoCamera)</span></span>
    - <span data-ttu-id="f7385-143">GlobalOpacityCoefficient （0.9 （HoloLens）1.0 （沉浸式头戴式耳机））</span><span class="sxs-lookup"><span data-stu-id="f7385-143">GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (Immersive headset))</span></span>
  - <span data-ttu-id="f7385-144">在 "MRC 音频" 效果中：</span><span class="sxs-lookup"><span data-stu-id="f7385-144">On the MRC Audio Effect:</span></span>
    - <span data-ttu-id="f7385-145">LoopbackGain （Windows Device Portal 中混合现实捕获页面上的当前 "应用音频增益" 值）</span><span class="sxs-lookup"><span data-stu-id="f7385-145">LoopbackGain (the current "App Audio Gain" value on the Mixed Reality Capture page in Windows Device Portal)</span></span>
    - <span data-ttu-id="f7385-146">MicrophoneGain （Windows Device Portal 中混合现实捕获页面上的当前 "Mic Audio 增益" 值）</span><span class="sxs-lookup"><span data-stu-id="f7385-146">MicrophoneGain (the current "Mic Audio Gain" value on the Mixed Reality Capture page in Windows Device Portal)</span></span>
- <span data-ttu-id="f7385-147">对于 Unity 应用程序，UserPresence API 通常是禁用的，以避免在面板翻转时导致某些应用暂停的问题，即使在后台运行的设置处于启用状态时也是如此。</span><span class="sxs-lookup"><span data-stu-id="f7385-147">The HolographicSpace.UserPresence API is generally disabled for Unity applications to avoid an issue which causes some apps to pause when the visor is flipped up, even if the setting to run in the background is enabled.</span></span> <span data-ttu-id="f7385-148">现已针对 Unity 版本2018.4.18 及更高版本、2019.3.4 和更高版本启用 API。</span><span class="sxs-lookup"><span data-stu-id="f7385-148">The API is now enabled for Unity versions 2018.4.18 and higher, and 2019.3.4 and higher.</span></span>
- <span data-ttu-id="f7385-149">修复了导致 hololens 应用更改像素格式的问题，这些应用会在 HoloLens 模拟器中呈现黑色。</span><span class="sxs-lookup"><span data-stu-id="f7385-149">Fixed an issue that caused HoloLens apps that change their pixel format to render black in the HoloLens emulator.</span></span>
- <span data-ttu-id="f7385-150">修复了从1903版本更新后初始引导中的 "照片" 应用程序启动时出现的问题。</span><span class="sxs-lookup"><span data-stu-id="f7385-150">Fixes an issue around launches of the Photos app in initial boots after updating from the 1903 release.</span></span>

## <span data-ttu-id="f7385-151">Windows 全息版2004</span><span class="sxs-lookup"><span data-stu-id="f7385-151">Windows Holographic, version 2004</span></span>  
<span data-ttu-id="f7385-152">内部版本-19041.1103</span><span class="sxs-lookup"><span data-stu-id="f7385-152">Build - 19041.1103</span></span>

<span data-ttu-id="f7385-153">我们很高兴地宣布，我们可能会更新 HoloLens 2、 **Windows 全息、版本 2004**的2020主要软件更新。</span><span class="sxs-lookup"><span data-stu-id="f7385-153">We are excited to announce our May 2020 major software update for HoloLens 2, **Windows Holographic, version 2004**.</span></span> <span data-ttu-id="f7385-154">此版本包含大量激动人心的新功能，例如 Windows Autopilot 支持、应用深色模式、5G/LTE 热点 USB 以太网支持等。</span><span class="sxs-lookup"><span data-stu-id="f7385-154">This release includes a host of exciting new capabilities, such as support for Windows Autopilot, app dark mode, USB Ethernet support for 5G/LTE hotspots, and much more.</span></span> <span data-ttu-id="f7385-155">若要更新到最新版本，请打开 " **设置" 应用**，转到 " **更新 & 安全**"，然后选择 " **检查更新**"   按钮。</span><span class="sxs-lookup"><span data-stu-id="f7385-155">To update to the latest release, open the **Settings app**, go to **Update & Security**, then select the **Check for Updates** button.</span></span> 

|             <span data-ttu-id="f7385-156">功能</span><span class="sxs-lookup"><span data-stu-id="f7385-156">Feature</span></span>                              |          <span data-ttu-id="f7385-157">描述</span><span class="sxs-lookup"><span data-stu-id="f7385-157">Description</span></span>                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       <span data-ttu-id="f7385-158">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="f7385-158">Windows Autopilot</span></span>                          |          <span data-ttu-id="f7385-159">通过 Windows AutoPilot 预配置和无缝设置用于生产的新设备</span><span class="sxs-lookup"><span data-stu-id="f7385-159">Pre-configure and seamlessly set up   new devices for production, with Windows AutoPilot</span></span>                 |
|       <span data-ttu-id="f7385-160">FIDO 2 支持</span><span class="sxs-lookup"><span data-stu-id="f7385-160">FIDO 2 support</span></span>                             |          <span data-ttu-id="f7385-161">支持 FIDO2 安全密钥以对共享设备启用快速和安全身份验证</span><span class="sxs-lookup"><span data-stu-id="f7385-161">Support for FIDO2 Security Keys to   enable fast and secure authentication for shared devices</span></span>            |
|       <span data-ttu-id="f7385-162">改进的预配</span><span class="sxs-lookup"><span data-stu-id="f7385-162">Improved provisioning</span></span>                      |          <span data-ttu-id="f7385-163">将预配包从 u 盘无缝应用到 HoloLens</span><span class="sxs-lookup"><span data-stu-id="f7385-163">Seamlessly apply a provisioning   package from a USB drive to your HoloLens</span></span>                              |
|       <span data-ttu-id="f7385-164">应用程序安装状态</span><span class="sxs-lookup"><span data-stu-id="f7385-164">Application install status</span></span>                 |          <span data-ttu-id="f7385-165">在 "设置" 应用中，检查应用的安装状态是否已通过 MDM 推送到 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="f7385-165">Check install status for apps have   been pushed to HoloLens 2 via MDM, in the Settings app</span></span>              |
|       <span data-ttu-id="f7385-166">配置服务提供商（Csp）</span><span class="sxs-lookup"><span data-stu-id="f7385-166">Configuration Service Providers   (CSPs)</span></span>   |          <span data-ttu-id="f7385-167">添加了新配置服务提供程序（Csp），增强了管理员控制功能。</span><span class="sxs-lookup"><span data-stu-id="f7385-167">Added new Configuration Service   Providers (CSPs) enhancing admin control capabilities.</span></span>                 |
|       <span data-ttu-id="f7385-168">USB 5G/LTE 支持</span><span class="sxs-lookup"><span data-stu-id="f7385-168">USB 5G/LTE support</span></span>                       |          <span data-ttu-id="f7385-169">扩展的 USB 以太网功能支持 5G/LTE 支持</span><span class="sxs-lookup"><span data-stu-id="f7385-169">Expanded USB Ethernet capability   enables support for 5G/LTE</span></span>                                    |
|       <span data-ttu-id="f7385-170">深色应用模式</span><span class="sxs-lookup"><span data-stu-id="f7385-170">Dark App Mode</span></span>                              |          <span data-ttu-id="f7385-171">适用于支持深色模式和浅色模式的应用的深色应用模式，改善了查看体验</span><span class="sxs-lookup"><span data-stu-id="f7385-171">Dark App Mode for apps that support   both dark and light modes, improving the viewing experience</span></span>        |
|       <span data-ttu-id="f7385-172">语音命令</span><span class="sxs-lookup"><span data-stu-id="f7385-172">Voice Commands</span></span>                             |          <span data-ttu-id="f7385-173">支持其他系统语音命令，以控制 HoloLens、无人参与</span><span class="sxs-lookup"><span data-stu-id="f7385-173">Support for additional system voice   commands to control HoloLens, hands-free</span></span>                           |
|       <span data-ttu-id="f7385-174">手动跟踪改进</span><span class="sxs-lookup"><span data-stu-id="f7385-174">Hand Tracking improvements</span></span>                 |          <span data-ttu-id="f7385-175">手动跟踪改进使按钮和2D 平板交互更准确</span><span class="sxs-lookup"><span data-stu-id="f7385-175">Hand Tracking improvements make   buttons and 2D slate interactions more accurate</span></span>                        |
|       <span data-ttu-id="f7385-176">质量改进和修复</span><span class="sxs-lookup"><span data-stu-id="f7385-176">Quality improvements and fixes</span></span>                 |          <span data-ttu-id="f7385-177">跨平台的各种系统性能和可靠性改进</span><span class="sxs-lookup"><span data-stu-id="f7385-177">Various system performance and   reliability improvements across the platform</span></span>                            |

### <span data-ttu-id="f7385-178">Windows Autopilot 支持</span><span class="sxs-lookup"><span data-stu-id="f7385-178">Support for Windows Autopilot</span></span> 

<span data-ttu-id="f7385-179">用于 HoloLens 2 的 Windows Autopilot 允许设备销售渠道预注册 HoloLens 到你的 Intune 租户。</span><span class="sxs-lookup"><span data-stu-id="f7385-179">Windows Autopilot for HoloLens 2 lets the device sales channel pre-enroll HoloLens into your Intune tenant.</span></span>  <span data-ttu-id="f7385-180">当设备到达时，它们准备就绪，可以作为你的租户下的共享设备进行自我部署。</span><span class="sxs-lookup"><span data-stu-id="f7385-180">When devices arrive, they’re ready to self-deploy as shared devices under your tenant.</span></span> <span data-ttu-id="f7385-181">若要利用自我部署，设备需要在安装程序的第一屏中使用 USB 至以太网转换器或将 USB-C 连接到 LTE 转换器时连接到网络。</span><span class="sxs-lookup"><span data-stu-id="f7385-181">To take advantage of self-deployment, devices will need to connect to a network during the first screen in setup using either a USB-C to ethernet dongle or USB-C to LTE dongle.</span></span> 

<span data-ttu-id="f7385-182">用户启动 Autopilot 自部署进程时，该过程完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f7385-182">When a user starts the Autopilot self-deploying process, the process completes the following steps:</span></span> 

1. <span data-ttu-id="f7385-183">将设备加入 Azure Active Directory (Azure AD)。</span><span class="sxs-lookup"><span data-stu-id="f7385-183">Join the device to Azure Active Directory (Azure AD).</span></span> 
1. <span data-ttu-id="f7385-184">使用 Azure AD 在 Microsoft Intune （或其他 MDM 服务）中注册设备。</span><span class="sxs-lookup"><span data-stu-id="f7385-184">Use Azure AD to enroll the device in Microsoft Intune (or another MDM service).</span></span> 
1. <span data-ttu-id="f7385-185">下载面向设备的策略、证书和网络配置文件。</span><span class="sxs-lookup"><span data-stu-id="f7385-185">Download the device-targeted policies, certificates, and networking profiles.</span></span> 
1. <span data-ttu-id="f7385-186">预配设备。</span><span class="sxs-lookup"><span data-stu-id="f7385-186">Provision the device.</span></span> 
1. <span data-ttu-id="f7385-187">向用户呈现登录屏幕。</span><span class="sxs-lookup"><span data-stu-id="f7385-187">Present the sign-in screen to the user.</span></span> 

<span data-ttu-id="f7385-188">请通过适用于[HoloLens 2 评估指南的 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="f7385-188">Learn more from the [Windows Autopilot for HoloLens 2 evaluation guide](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>

**<span data-ttu-id="f7385-189">请与您的帐户管理员联系，立即加入 AutoPilot 预览版。</span><span class="sxs-lookup"><span data-stu-id="f7385-189">Contact your Account Manager to join the AutoPilot preview now.</span></span> <span data-ttu-id="f7385-190">Autopilot 已准备好的设备即将开始发货。</span><span class="sxs-lookup"><span data-stu-id="f7385-190">Autopilot-ready devices will begin shipping soon.</span></span>**

### <span data-ttu-id="f7385-191">FIDO2 安全密钥支持</span><span class="sxs-lookup"><span data-stu-id="f7385-191">FIDO2 Security Key support</span></span> 

<span data-ttu-id="f7385-192">许多人在工作或学校环境中与许多人共享一个 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="f7385-192">Many of you share a HoloLens device with lots of people in a work or school environment.</span></span> <span data-ttu-id="f7385-193">无论是在课堂上的学生之间共享设备，还是从设备保险箱中签出设备，很重要的一点是，无需键入长用户名和密码即可快速轻松地更改用户。</span><span class="sxs-lookup"><span data-stu-id="f7385-193">Whether devices are shared between students in a classroom or they're checked out from a device locker, it's important to be able to change users quickly and easily without typing long usernames and passwords.</span></span> 

<span data-ttu-id="f7385-194">FIDO 允许你组织中的任何人（AAD 租户）无需输入用户名或密码即可无缝登录到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="f7385-194">FIDO lets anyone in your organization (AAD tenant) seamlessly sign into HoloLens without entering a username or password.</span></span> 

<span data-ttu-id="f7385-195">FIDO2 安全密钥是基于 unphishable 标准的 passwordless 身份验证方法，可采用任何形式的外观。</span><span class="sxs-lookup"><span data-stu-id="f7385-195">FIDO2 security keys are an unphishable standards-based passwordless authentication method that can come in any form factor.</span></span> <span data-ttu-id="f7385-196">快速身份在线（FIDO）是 passwordless 身份验证的开放标准。</span><span class="sxs-lookup"><span data-stu-id="f7385-196">Fast Identity Online (FIDO) is an open standard for passwordless authentication.</span></span> <span data-ttu-id="f7385-197">FIDO 使用户和组织可以利用标准登录到其资源，而无需使用外部安全密钥或内置于设备的平台密钥的用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="f7385-197">FIDO allows users and organizations to leverage the standard to sign-in to their resources without a username or password using an external security key or a platform key built into a device.</span></span> 

<span data-ttu-id="f7385-198">阅读[passwordless 安全文档](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)以开始使用。</span><span class="sxs-lookup"><span data-stu-id="f7385-198">Read the [passwordless security docs](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key) to get started.</span></span> 

### <span data-ttu-id="f7385-199">通过预配包改进了 MDM 注册</span><span class="sxs-lookup"><span data-stu-id="f7385-199">Improved MDM enrollment via provisioning package</span></span> 

<span data-ttu-id="f7385-200">预配程序包允许你通过配置文件设置 HoloLens 配置，而不是通过 HoloLens 全新体验。</span><span class="sxs-lookup"><span data-stu-id="f7385-200">Provisioning packages let you set HoloLens configuration through a config file rather than going through the HoloLens out of box experience.</span></span> <span data-ttu-id="f7385-201">以前，预配程序包必须复制到 HoloLens "内部内存"，现在它们可以位于 USB 驱动器上，以便更容易在多个 HoloLens 上重复使用，因此更多的人可以并行预配 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="f7385-201">Previously, provisioning packages had to be copied onto HoloLens' internal memory, now they can be on a USB drive so they're easier to re-use on multiple HoloLens and so more people can provision HoloLens in parallel.</span></span>  <span data-ttu-id="f7385-202">此外，预配包支持用于注册设备管理的新字段，因此不会手动设置后期设置。</span><span class="sxs-lookup"><span data-stu-id="f7385-202">In addition, provisioning packages support a new field to enroll in device management so there is no manual set up post-provisioning.</span></span> 

1. <span data-ttu-id="f7385-203">若要试用，请从 Windows 应用商店中将最新版本的 Windows 配置设计器下载到你的电脑。</span><span class="sxs-lookup"><span data-stu-id="f7385-203">To try it out, download the latest version of the Windows Configuration Designer from the Windows store onto your PC.</span></span> 
1. <span data-ttu-id="f7385-204">选择 "**设置 Hololens 设备**" > 选择 "**设置 hololens 2 设备**"</span><span class="sxs-lookup"><span data-stu-id="f7385-204">Select **Provision HoloLens Devices** > Select **Provision HoloLens 2 devices**</span></span> 
1. <span data-ttu-id="f7385-205">构建配置文件，完成后，复制所有创建到 USB-C 存储设备的文件。</span><span class="sxs-lookup"><span data-stu-id="f7385-205">Build your configuration profile and, when you're done, copy all files created to a USB-C storage device.</span></span> 
1. <span data-ttu-id="f7385-206">将其插入任何全新刷新的 HoloLens 并按**下音量 + Power**以应用预配包。</span><span class="sxs-lookup"><span data-stu-id="f7385-206">Plug it into any freshly flashed HoloLens and press **Volume down + Power** to apply your provisioning package.</span></span> 

### <span data-ttu-id="f7385-207">业务线应用程序安装状态</span><span class="sxs-lookup"><span data-stu-id="f7385-207">Line of Business application install status</span></span> 

<span data-ttu-id="f7385-208">适用于业务线（LOB）应用的 MDM 应用部署和管理对我们的客户至关重要。</span><span class="sxs-lookup"><span data-stu-id="f7385-208">MDM app deployment and management for Line of Business (LOB) apps is critical for our customers.</span></span> <span data-ttu-id="f7385-209">管理员和用户需要能够查看应用安装状态，以供审核和诊断之用。</span><span class="sxs-lookup"><span data-stu-id="f7385-209">Admins and users need to be able to view app install status, for auditing and diagnosis purposes.</span></span> <span data-ttu-id="f7385-210">在此版本中，我们将在 **"> 帐户" > Access 工作或学校 > 单击您的帐户 > 信息**的 "设置" 中添加更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="f7385-210">In this release we are adding more details in **Settings > Accounts > Access work or school > Click on your account > Info.**</span></span>

### <span data-ttu-id="f7385-211">其他 Csp 和策略</span><span class="sxs-lookup"><span data-stu-id="f7385-211">Additional CSPs and Policies</span></span> 

<span data-ttu-id="f7385-212">[配置服务提供程序（CSP）](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)是用于读取、设置、修改或删除设备上的配置设置的接口。</span><span class="sxs-lookup"><span data-stu-id="f7385-212">A [configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) is an interface to read, set, modify, or delete configuration settings on a device.</span></span> <span data-ttu-id="f7385-213">在此版本中，我们将添加对更多策略的支持，从而提高控制管理员对已部署的 HoloLens 设备的控制权。</span><span class="sxs-lookup"><span data-stu-id="f7385-213">In this release, we are adding support for more policies, increasing the control administrators have over deployed HoloLens devices.</span></span> <span data-ttu-id="f7385-214">有关 HoloLens 支持的 Csp 列表，请访问此[链接](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。</span><span class="sxs-lookup"><span data-stu-id="f7385-214">For the list of CSPs supported by HoloLens, visit this [link](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="f7385-215">此版本中的新增内容：</span><span class="sxs-lookup"><span data-stu-id="f7385-215">New in this release:</span></span>

**<span data-ttu-id="f7385-216">策略云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="f7385-216">Policy CSP</span></span>** 

<span data-ttu-id="f7385-217">策略配置服务提供程序使企业能够在 Windows 设备上配置策略。</span><span class="sxs-lookup"><span data-stu-id="f7385-217">The Policy configuration service provider enables the enterprise to configure policies on Windows devices.</span></span> <span data-ttu-id="f7385-218">在此版本中，我们将为 HoloLens 添加新策略，如下所示。</span><span class="sxs-lookup"><span data-stu-id="f7385-218">In this release, we are adding new policies for HoloLens, listed below.</span></span> <span data-ttu-id="f7385-219">你可以在[此处](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)了解有关受支持的策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f7385-219">You can learn more about supported policies [here](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2).</span></span>  

- <span data-ttu-id="f7385-220">LetAppsAccessCamera_ForceAllowTheseApps</span><span class="sxs-lookup"><span data-stu-id="f7385-220">LetAppsAccessCamera_ForceAllowTheseApps</span></span>  
- <span data-ttu-id="f7385-221">LetAppsAccessCamera_ForceDenyTheseApps</span><span class="sxs-lookup"><span data-stu-id="f7385-221">LetAppsAccessCamera_ForceDenyTheseApps</span></span>  
- <span data-ttu-id="f7385-222">LetAppsAccessCamera_UserInControlOfTheseApps</span><span class="sxs-lookup"><span data-stu-id="f7385-222">LetAppsAccessCamera_UserInControlOfTheseApps</span></span> 
- <span data-ttu-id="f7385-223">LetAppsAccessGazeInput</span><span class="sxs-lookup"><span data-stu-id="f7385-223">LetAppsAccessGazeInput</span></span> 
- <span data-ttu-id="f7385-224">LetAppsAccessGazeInput_ForceAllowTheseApps</span><span class="sxs-lookup"><span data-stu-id="f7385-224">LetAppsAccessGazeInput_ForceAllowTheseApps</span></span> 
- <span data-ttu-id="f7385-225">LetAppsAccessGazeInput_ForceDenyTheseApps</span><span class="sxs-lookup"><span data-stu-id="f7385-225">LetAppsAccessGazeInput_ForceDenyTheseApps</span></span> 
- <span data-ttu-id="f7385-226">LetAppsAccessGazeInput_UserInControlOfTheseApps</span><span class="sxs-lookup"><span data-stu-id="f7385-226">LetAppsAccessGazeInput_UserInControlOfTheseApps</span></span> 
- <span data-ttu-id="f7385-227">LetAppsAccessMicrophone_ForceAllowTheseApps</span><span class="sxs-lookup"><span data-stu-id="f7385-227">LetAppsAccessMicrophone_ForceAllowTheseApps</span></span> 
- <span data-ttu-id="f7385-228">LetAppsAccessMicrophone_ForceDenyTheseApps</span><span class="sxs-lookup"><span data-stu-id="f7385-228">LetAppsAccessMicrophone_ForceDenyTheseApps</span></span> 
- <span data-ttu-id="f7385-229">LetAppsAccessMicrophone_UserInControlOfTheseApps</span><span class="sxs-lookup"><span data-stu-id="f7385-229">LetAppsAccessMicrophone_UserInControlOfTheseApps</span></span> 
- <span data-ttu-id="f7385-230">AllowWiFi</span><span class="sxs-lookup"><span data-stu-id="f7385-230">AllowWiFi</span></span> 

<span data-ttu-id="f7385-231">**NETWORKQOSPOLICY CSP**NetworkQoSPolicy 配置服务提供程序创建网络服务质量（QoS）策略。</span><span class="sxs-lookup"><span data-stu-id="f7385-231">**NetworkQoSPolicy CSP** The NetworkQoSPolicy configuration service provider creates network Quality of Service (QoS) policies.</span></span> <span data-ttu-id="f7385-232">QoS 策略根据一组匹配的条件对网络流量执行一组操作。</span><span class="sxs-lookup"><span data-stu-id="f7385-232">A QoS policy performs a set of actions on network traffic based on a set of matching conditions.</span></span> <span data-ttu-id="f7385-233">可在[此处](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)了解有关此策略的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f7385-233">You can learn more about this policy [here](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> 

### <span data-ttu-id="f7385-234">已展开的 USB 以太网支持 5G/LTE tethered 设备</span><span class="sxs-lookup"><span data-stu-id="f7385-234">Expanded USB Ethernet support for 5G/LTE tethered devices</span></span>

<span data-ttu-id="f7385-235">在通过 USB tethered 到 HoloLens 2 时，已添加支持以启用某些移动宽带设备，例如 5G/LTE 手机和 WiFi hotpots。</span><span class="sxs-lookup"><span data-stu-id="f7385-235">Support has been added to enable certain mobile broadband devices, such as 5G/LTE phones and WiFi hotpots when tethered to the HoloLens 2 via USB.</span></span> <span data-ttu-id="f7385-236">这些设备将在 "网络设置" 中显示为另一个以太网连接。</span><span class="sxs-lookup"><span data-stu-id="f7385-236">These devices will be displayed in network settings as another ethernet connection.</span></span> <span data-ttu-id="f7385-237">不支持需要外部驱动程序的移动宽带设备。</span><span class="sxs-lookup"><span data-stu-id="f7385-237">Mobile broadband devices that require an external driver are not supported.</span></span> <span data-ttu-id="f7385-238">这将在 WiFi 不可用的情况下启用高带宽连接，并且 WiFi tethering 不具备足够的性能。</span><span class="sxs-lookup"><span data-stu-id="f7385-238">This enables high bandwidth connections in scenarios where WiFi is not available, and WiFi tethering isn’t performant enough.</span></span> <span data-ttu-id="f7385-239">可在[此处](https://docs.microsoft.com/hololens/hololens-connect-devices)了解有关受支持的 USB 设备的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f7385-239">You can learn more about supported USB devices [here](https://docs.microsoft.com/hololens/hololens-connect-devices).</span></span>  

### <span data-ttu-id="f7385-240">手动跟踪改进</span><span class="sxs-lookup"><span data-stu-id="f7385-240">Hand Tracking Improvements</span></span>

<span data-ttu-id="f7385-241">在此版本中，手动跟踪已收到多项改进。</span><span class="sxs-lookup"><span data-stu-id="f7385-241">Hand tracking has received several improvements in this release.</span></span> 

- <span data-ttu-id="f7385-242">**指针具有稳定性：** 当 palm occluded 时，系统将会对索引手指的弯曲。</span><span class="sxs-lookup"><span data-stu-id="f7385-242">**Pointing pose stability:** The system will now resist bending the index finger when it becomes occluded by the palm.</span></span>  <span data-ttu-id="f7385-243">这可提高推送按钮、键入、滚动内容等内容的准确性！</span><span class="sxs-lookup"><span data-stu-id="f7385-243">This improves accuracy when pushing buttons, typing, scrolling content, and more!</span></span> 
- <span data-ttu-id="f7385-244">**减少意外 AirTaps：** 我们改进了 AirTap 手势的检测。</span><span class="sxs-lookup"><span data-stu-id="f7385-244">**Reduced accidental AirTaps:** We’ve improved detection of the AirTap gesture.</span></span>  <span data-ttu-id="f7385-245">现在，在几种常见情况下出现意外激活的次数较少，例如将手放在一侧。</span><span class="sxs-lookup"><span data-stu-id="f7385-245">Now there are fewer accidental activations in several common cases, such as dropping your hands to your side.</span></span> 
- <span data-ttu-id="f7385-246">**用户切换可靠性：** 在来回共享设备时，在更新手形的大小时，系统现在更快、更可靠。</span><span class="sxs-lookup"><span data-stu-id="f7385-246">**User switch reliability:** The system is now faster and more reliable at updating the hand size when sharing a device back and forth.</span></span> 
- <span data-ttu-id="f7385-247">**减少右手偷窃：** 我们改进了两个参与传感器的视图的处理方式。</span><span class="sxs-lookup"><span data-stu-id="f7385-247">**Reduced hand stealing:** We’ve improved handling of cases where there are more than 2 hands in view of the sensors.</span></span>  <span data-ttu-id="f7385-248">如果多人密切协作，那么，在场景中，所跟踪的手势将从用户跳转到其他人的手边。</span><span class="sxs-lookup"><span data-stu-id="f7385-248">If multiple people are working close together, there is now a much lower chance that the tracked hand will jump from the user to the hand of someone else in the scene.</span></span> 
- <span data-ttu-id="f7385-249">**系统可靠性：** 修复了一个问题，该问题会导致手动跟踪在设备处于高负载下时停止工作。</span><span class="sxs-lookup"><span data-stu-id="f7385-249">**System reliability:** Fixed an issue that would cause hand tracking to stop working for a period if the device is under high load.</span></span> 

### <span data-ttu-id="f7385-250">深色模式</span><span class="sxs-lookup"><span data-stu-id="f7385-250">Dark mode</span></span>

<span data-ttu-id="f7385-251">许多 Windows 应用现在支持深色模式和浅色模式，并且 HoloLens 2 客户可以为同时支持这两种应用的应用选择默认模式。</span><span class="sxs-lookup"><span data-stu-id="f7385-251">Many Windows apps now support both dark and light modes, and HoloLens 2 customers can choose the default mode for apps that support both.</span></span> <span data-ttu-id="f7385-252">一旦更新，默认应用模式将为 "深色"，但可以轻松更改。</span><span class="sxs-lookup"><span data-stu-id="f7385-252">Once updated, the default app mode will be "dark," but can be changed easily.</span></span> <span data-ttu-id="f7385-253">导航到 "系统 > 颜色" > 的 "设置"，找到 "选择默认应用模式"。</span><span class="sxs-lookup"><span data-stu-id="f7385-253">Navigate to Settings > System > Colors to find "Choose your default app mode."</span></span> <span data-ttu-id="f7385-254">下面是一些支持深色模式的内置应用：</span><span class="sxs-lookup"><span data-stu-id="f7385-254">Here are some of the in-box apps that support Dark mode:</span></span> 

- <span data-ttu-id="f7385-255">设置</span><span class="sxs-lookup"><span data-stu-id="f7385-255">Settings</span></span> 
- <span data-ttu-id="f7385-256">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f7385-256">Microsoft Store</span></span> 
- <span data-ttu-id="f7385-257">邮件</span><span class="sxs-lookup"><span data-stu-id="f7385-257">Mail</span></span> 
- <span data-ttu-id="f7385-258">日历</span><span class="sxs-lookup"><span data-stu-id="f7385-258">Calendar</span></span> 
- <span data-ttu-id="f7385-259">文件资源管理器</span><span class="sxs-lookup"><span data-stu-id="f7385-259">File Explorer</span></span> 
- <span data-ttu-id="f7385-260">反馈中心</span><span class="sxs-lookup"><span data-stu-id="f7385-260">Feedback Hub</span></span> 
- <span data-ttu-id="f7385-261">OneDrive</span><span class="sxs-lookup"><span data-stu-id="f7385-261">OneDrive</span></span> 
- <span data-ttu-id="f7385-262">照片</span><span class="sxs-lookup"><span data-stu-id="f7385-262">Photos</span></span> 
- <span data-ttu-id="f7385-263">3D 查看器</span><span class="sxs-lookup"><span data-stu-id="f7385-263">3D Viewer</span></span> 
- <span data-ttu-id="f7385-264">电影和电视</span><span class="sxs-lookup"><span data-stu-id="f7385-264">Movies & TV</span></span> 

![深色模式窗口平铺](images/DarkMode.jpg)

### <span data-ttu-id="f7385-266">系统语音命令</span><span class="sxs-lookup"><span data-stu-id="f7385-266">System voice commands</span></span>

<span data-ttu-id="f7385-267">现在，你可以使用设备上的任何应用在你的语音中快速访问和使用命令。</span><span class="sxs-lookup"><span data-stu-id="f7385-267">You can now quickly access and use commands with your voice while using any app on the device.</span></span> <span data-ttu-id="f7385-268">如果你使用其他语言运行系统，请尝试使用该语言的相应命令。</span><span class="sxs-lookup"><span data-stu-id="f7385-268">If you're running your system with a different language, please try the appropriate commands in that language.</span></span> <span data-ttu-id="f7385-269">有关这些命令以及如何使用它们的详细信息，请参阅我们的[文档。](https://docs.microsoft.com/hololens/hololens-cortana)</span><span class="sxs-lookup"><span data-stu-id="f7385-269">For more details on the commands and how to use them, see our documentation [here](https://docs.microsoft.com/hololens/hololens-cortana).</span></span>  

### <span data-ttu-id="f7385-270">Cortana 更新</span><span class="sxs-lookup"><span data-stu-id="f7385-270">Cortana updates</span></span> 

<span data-ttu-id="f7385-271">已更新的应用与 Microsoft 365 （当前仅限英语（美国））集成，以帮助你在设备上更好地完成工作。</span><span class="sxs-lookup"><span data-stu-id="f7385-271">The updated app integrates with Microsoft 365, currently in English (United States) only, to help you get more done across your devices.</span></span> <span data-ttu-id="f7385-272">在 HoloLens 2 上，Cortana 将不再支持某些特定于设备的命令，如调整音量或重启设备，这些命令现在受上述新系统语音命令支持。</span><span class="sxs-lookup"><span data-stu-id="f7385-272">On HoloLens 2, Cortana will no longer support certain device-specific commands like adjusting the volume or restarting the device, which are now supported with the new system voice commands mentioned above.</span></span> <span data-ttu-id="f7385-273">在[此处](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)了解有关新的 Cortana 应用及其方向的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f7385-273">Learn more about the new Cortana app and its direction on our blog [here](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/).</span></span> 

### <span data-ttu-id="f7385-274">质量改进和修复</span><span class="sxs-lookup"><span data-stu-id="f7385-274">Quality improvements and fixes</span></span> 

<span data-ttu-id="f7385-275">更新中也有改进和修复：</span><span class="sxs-lookup"><span data-stu-id="f7385-275">Improvements and Fixes also in the update:</span></span>  
- <span data-ttu-id="f7385-276">此更新引入了一个活动的显示校准系统。</span><span class="sxs-lookup"><span data-stu-id="f7385-276">The update introduces an active display calibration system.</span></span> <span data-ttu-id="f7385-277">这将改善全息影像的稳定性和对齐方式，从而有助于它们在移动您的头面时保持不变。</span><span class="sxs-lookup"><span data-stu-id="f7385-277">This improves the stability and alignment of holograms, which helps them stay in place when moving your head side-to-side.</span></span> 
- <span data-ttu-id="f7385-278">修复了用于 HoloLens 的 Wi-fi 流式处理定期中断的 bug。</span><span class="sxs-lookup"><span data-stu-id="f7385-278">Fixed a bug where Wi-Fi streaming to HoloLens gets disrupted periodically.</span></span> <span data-ttu-id="f7385-279">如果应用程序指示它需要低延迟流，则可以通过调用[此函数](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)来完成此修补程序。</span><span class="sxs-lookup"><span data-stu-id="f7385-279">If an application indicates that it needs low latency streaming this fix is can be accomplished by calling [this function](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode).</span></span> 
- <span data-ttu-id="f7385-280">修复了在使用研究模式流式处理期间设备可能挂起的问题。</span><span class="sxs-lookup"><span data-stu-id="f7385-280">Fixed an issue where the device could hang during streaming in research mode.</span></span> 
- <span data-ttu-id="f7385-281">修复的 bug，在某些情况下，在恢复会话时，登录屏幕上将不会显示正确的用户。</span><span class="sxs-lookup"><span data-stu-id="f7385-281">Fixed bug where in some cases the right user would not be displayed on sign-in screen when resuming session.</span></span> 
- <span data-ttu-id="f7385-282">修复了用户无法通过设置导出 MDM 日志的问题。</span><span class="sxs-lookup"><span data-stu-id="f7385-282">Fixed an issue where users could not export MDM logs through settings.</span></span> 
- <span data-ttu-id="f7385-283">修复了紧跟在安装后立即关注的目视跟踪的问题：安装可能低于规范。</span><span class="sxs-lookup"><span data-stu-id="f7385-283">Fixed an issue where the accuracy of eye tracking immediately following out-of-box-setup could be lower than specification.</span></span> 
- <span data-ttu-id="f7385-284">修复了在某些条件下，目视跟踪子系统无法初始化和/或执行校准的问题。</span><span class="sxs-lookup"><span data-stu-id="f7385-284">Fixed an issue where eye tracking subsystem would fail to initialize and/or perform calibration under certain conditions.</span></span> 
- <span data-ttu-id="f7385-285">修复了提示校准已校准用户的问题。</span><span class="sxs-lookup"><span data-stu-id="f7385-285">Fixed an issue where eye calibration would be prompted for an already calibrated user.</span></span> 
- <span data-ttu-id="f7385-286">修复了在目视校准期间驱动程序崩溃的问题。</span><span class="sxs-lookup"><span data-stu-id="f7385-286">Fixed an issue where a driver would crash during eye calibration.</span></span> 
- <span data-ttu-id="f7385-287">修复了重复的电源按钮按下可能导致60秒的系统超时和外壳崩溃的问题。</span><span class="sxs-lookup"><span data-stu-id="f7385-287">Fixed an issue where repeated power button presses can cause a 60 second system time-out and shell crash.</span></span> 
- <span data-ttu-id="f7385-288">改善了深度缓冲区的稳定性。</span><span class="sxs-lookup"><span data-stu-id="f7385-288">Improved stability for depth buffers.</span></span> 
- <span data-ttu-id="f7385-289">在反馈中心中添加了 "共享" 按钮，以便用户可以更轻松地共享反馈。</span><span class="sxs-lookup"><span data-stu-id="f7385-289">Added ‘Share’ button in Feedback Hub so users can more easily share feedback.</span></span> 
- <span data-ttu-id="f7385-290">修复了 RoboRaid 未正确安装的 bug。</span><span class="sxs-lookup"><span data-stu-id="f7385-290">Fixed a bug where RoboRaid did not install correctly.</span></span> 

### <span data-ttu-id="f7385-291">已知问题</span><span class="sxs-lookup"><span data-stu-id="f7385-291">Known issues</span></span>

- <span data-ttu-id="f7385-292">我们正在研究使用 zh-cn&platform system 语言的问题，该问题阻止使用语音命令跟踪混合现实捕获或显示设备 IP 地址的工作。</span><span class="sxs-lookup"><span data-stu-id="f7385-292">We are investigating an issue surrounding the use of the zh-CN system language that prevents the voice commands for taking a mixed reality capture or displaying the device IP address from working.</span></span>
- <span data-ttu-id="f7385-293">我们正在调查需要你在启动设备后启动 Cortana 应用才能使用 "你好 Cortana" 语音激活的问题，并且如果你从18362版本更新，你可能会在 "开始" 中看到以前版本的 Cortana 应用的第二个应用磁贴，不再有效。</span><span class="sxs-lookup"><span data-stu-id="f7385-293">We're investigating an issue that requires you to launch the Cortana app after booting the device in order to use the "Hey Cortana" voice activation, and if you updated from a 18362 build, you may see a second app tile for the previous version of the Cortana app in Start that no longer works.</span></span> 

## <span data-ttu-id="f7385-294">Windows 全息版 1903-五月2020更新</span><span class="sxs-lookup"><span data-stu-id="f7385-294">Windows Holographic, version 1903 - May 2020 Update</span></span> 
- <span data-ttu-id="f7385-295">内部版本18362.1061</span><span class="sxs-lookup"><span data-stu-id="f7385-295">Build 18362.1061</span></span>

<span data-ttu-id="f7385-296">此 "每月质量更新" 不包含任何更改，因为团队致力于向您提供最高质量的功能更新，您现在可以在 Windows 全息版本2004中更新上述详细信息。</span><span class="sxs-lookup"><span data-stu-id="f7385-296">This monthly quality update does not contain any changes of note because the team has been focused on providing you with the highest quality Feature Update now available in the Windows Holographic, version 2004 May Update detailed above.</span></span> <span data-ttu-id="f7385-297">请转到最新功能更新，以获得大量激动人心的新更改。</span><span class="sxs-lookup"><span data-stu-id="f7385-297">Please take this opportunity to move to the latest feature update to get a ton of exciting new changes.</span></span>

## <span data-ttu-id="f7385-298">Windows 全息版 1903-2020 年4月更新</span><span class="sxs-lookup"><span data-stu-id="f7385-298">Windows Holographic, version 1903 - April 2020 Update</span></span>
- <span data-ttu-id="f7385-299">内部版本18362.1059</span><span class="sxs-lookup"><span data-stu-id="f7385-299">Build 18362.1059</span></span>

**<span data-ttu-id="f7385-300">支持的应用的深色模式</span><span class="sxs-lookup"><span data-stu-id="f7385-300">Dark mode for supported apps</span></span>** 

<span data-ttu-id="f7385-301">许多 Windows 应用均支持深色模式和浅色模式，不久 HoloLens 2 客户可以为支持两种配色方案的应用选择默认模式！</span><span class="sxs-lookup"><span data-stu-id="f7385-301">Many Windows apps support both dark and light modes, and soon HoloLens 2 customers can choose the default mode for apps that support both color schemes!</span></span> <span data-ttu-id="f7385-302">根据 overwhelmingly 肯定的客户反馈，通过此更新，我们将默认应用模式设置为 "深色"，但你可以随时轻松地更改此设置。</span><span class="sxs-lookup"><span data-stu-id="f7385-302">Based on overwhelmingly positive customer feedback, with this update we are setting the default app mode to "dark," but you can easily change this setting at any time.</span></span>
<span data-ttu-id="f7385-303">导航到 "**系统 > 颜色" >** 的 **"设置"，找到 "选择默认应用模式"。**</span><span class="sxs-lookup"><span data-stu-id="f7385-303">Navigate to **Settings > System > Colors** to find **"Choose your default app mode."**</span></span>

<span data-ttu-id="f7385-304">下面是一些支持深色模式的内置应用：</span><span class="sxs-lookup"><span data-stu-id="f7385-304">Here are some of the in-box apps that support dark mode:</span></span>
- <span data-ttu-id="f7385-305">设置</span><span class="sxs-lookup"><span data-stu-id="f7385-305">Settings</span></span>
- <span data-ttu-id="f7385-306">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="f7385-306">Microsoft Store</span></span>
- <span data-ttu-id="f7385-307">邮件</span><span class="sxs-lookup"><span data-stu-id="f7385-307">Mail</span></span>
- <span data-ttu-id="f7385-308">日历</span><span class="sxs-lookup"><span data-stu-id="f7385-308">Calendar</span></span>
- <span data-ttu-id="f7385-309">文件资源管理器</span><span class="sxs-lookup"><span data-stu-id="f7385-309">File Explorer</span></span>
- <span data-ttu-id="f7385-310">反馈中心</span><span class="sxs-lookup"><span data-stu-id="f7385-310">Feedback Hub</span></span>
- <span data-ttu-id="f7385-311">OneDrive</span><span class="sxs-lookup"><span data-stu-id="f7385-311">OneDrive</span></span>
- <span data-ttu-id="f7385-312">照片</span><span class="sxs-lookup"><span data-stu-id="f7385-312">Photos</span></span>
- <span data-ttu-id="f7385-313">3D 查看器</span><span class="sxs-lookup"><span data-stu-id="f7385-313">3D Viewer</span></span>
- <span data-ttu-id="f7385-314">电影和电视</span><span class="sxs-lookup"><span data-stu-id="f7385-314">Movies & TV</span></span>

**<span data-ttu-id="f7385-315">更新中也有改进和修复：</span><span class="sxs-lookup"><span data-stu-id="f7385-315">Improvements and fixes also in the update:</span></span>** 
- <span data-ttu-id="f7385-316">确保在混合现实捕获中包含外壳覆盖。</span><span class="sxs-lookup"><span data-stu-id="f7385-316">Ensure shell overlays are included in mixed reality captures.</span></span>
- <span data-ttu-id="f7385-317">Unreal 开发人员现在可以使用 Device Portal 中的3D 视图页面来测试和调试其应用程序。</span><span class="sxs-lookup"><span data-stu-id="f7385-317">Unreal developers are now able to use the 3D View page in Device Portal to test and debug their applications.</span></span>
- <span data-ttu-id="f7385-318">在使用 HolographicDepthReprojectionMethod DepthReprojection 算法时，在混合现实捕获中改进全息图稳定性。</span><span class="sxs-lookup"><span data-stu-id="f7385-318">Improve hologram stability in mixed reality capture when the HolographicDepthReprojectionMethod DepthReprojection algorithm is used.</span></span>
- <span data-ttu-id="f7385-319">固定 WinRT IStreamSocketListener API 类在32位 ARM 应用上未注册错误。</span><span class="sxs-lookup"><span data-stu-id="f7385-319">Fixed WinRT IStreamSocketListener API Class Not Registered error on 32-bit ARM app.</span></span>

## <span data-ttu-id="f7385-320">Windows 全息版、版本 1903-2020 更新</span><span class="sxs-lookup"><span data-stu-id="f7385-320">Windows Holographic, version 1903 - March 2020 Update</span></span> 
- <span data-ttu-id="f7385-321">内部版本18362.1056</span><span class="sxs-lookup"><span data-stu-id="f7385-321">Build 18362.1056</span></span>

<span data-ttu-id="f7385-322">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="f7385-322">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="f7385-323">在使用 HolographicDepthReprojectionMethod AutoPlanar 算法时，在混合现实捕获中改进全息图稳定性。</span><span class="sxs-lookup"><span data-stu-id="f7385-323">Improve hologram stability in mixed reality capture when the HolographicDepthReprojectionMethod AutoPlanar algorithm is used.</span></span>
- <span data-ttu-id="f7385-324">确保连接到 depth MF 示例的坐标系与公共文档一致。</span><span class="sxs-lookup"><span data-stu-id="f7385-324">Ensures the coordinate system attached to a depth MF sample is consistent with public documentation.</span></span>
- <span data-ttu-id="f7385-325">通过让客户通过 device portal 粘贴大量文本，提高了开发者的工作效率。</span><span class="sxs-lookup"><span data-stu-id="f7385-325">Developers productivity improvement by enabling customers to paste large amount of text through device portal.</span></span>

## <span data-ttu-id="f7385-326">Windows 全息版 1903-2 月2020更新</span><span class="sxs-lookup"><span data-stu-id="f7385-326">Windows Holographic, version 1903 - February 2020 Update</span></span> 
- <span data-ttu-id="f7385-327">内部版本18362.1053</span><span class="sxs-lookup"><span data-stu-id="f7385-327">Build 18362.1053</span></span>

<span data-ttu-id="f7385-328">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="f7385-328">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="f7385-329">已暂时禁用 Unity 应用程序的 HolographicSpace API，以避免在面板翻转时导致某些应用暂停的问题，即使启用了在后台运行的设置也是如此。</span><span class="sxs-lookup"><span data-stu-id="f7385-329">Temporarily disabled the HolographicSpace.UserPresence API for Unity applications to avoid an issue which causes some apps to pause when the visor is flipped up, even if the setting to run in the background is enabled.</span></span>
- <span data-ttu-id="f7385-330">修复了手动跟踪的随机 HUP 大小，在这种情况下，用户将在几秒钟后注意到 UI 冻结，然后返回到外壳。</span><span class="sxs-lookup"><span data-stu-id="f7385-330">Fixed a random HUP crash cased by hand tracking, in which user will notice an UI freeze then back to shell after several seconds.</span></span>
- <span data-ttu-id="f7385-331">我们对手跟踪进行了改进，因此在使用食指 poking 时，手指的上半部分将不太可能意外卷曲。</span><span class="sxs-lookup"><span data-stu-id="f7385-331">We made an improvement in hand tracking so that while poking using index finger, the upper part of that finger will be less likely to curl unexpectedly.</span></span>
- <span data-ttu-id="f7385-332">改进了 head 跟踪、空间映射和其他运行时的可靠性。</span><span class="sxs-lookup"><span data-stu-id="f7385-332">Improved reliability of head tracking, spatial mapping, and other runtimes.</span></span>

## <span data-ttu-id="f7385-333">Windows 全息版 1903-2020 更新</span><span class="sxs-lookup"><span data-stu-id="f7385-333">Windows Holographic, version 1903 - January 2020 Update</span></span> 
- <span data-ttu-id="f7385-334">内部版本18362.1043</span><span class="sxs-lookup"><span data-stu-id="f7385-334">Build 18362.1043</span></span>

<span data-ttu-id="f7385-335">更新改进：</span><span class="sxs-lookup"><span data-stu-id="f7385-335">Improvement in the update:</span></span>

- <span data-ttu-id="f7385-336">使用 HoloLens 2 模拟器时，对独占应用的稳定性有所改进。</span><span class="sxs-lookup"><span data-stu-id="f7385-336">Stability improvements for exclusive apps when working with the HoloLens 2 emulator.</span></span>

## <span data-ttu-id="f7385-337">Windows 全息版 1903-2019 更新</span><span class="sxs-lookup"><span data-stu-id="f7385-337">Windows Holographic, version 1903 - December 2019 Update</span></span> 
- <span data-ttu-id="f7385-338">内部版本18362.1042</span><span class="sxs-lookup"><span data-stu-id="f7385-338">Build 18362.1042</span></span>

<span data-ttu-id="f7385-339">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="f7385-339">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="f7385-340">介绍 LSR （最后阶段重现）修补程序。</span><span class="sxs-lookup"><span data-stu-id="f7385-340">Introduces LSR (Last Stage Reproduction) fixes.</span></span> <span data-ttu-id="f7385-341">改善全息影像的视觉呈现，使其更准确地获得更稳定的深度。</span><span class="sxs-lookup"><span data-stu-id="f7385-341">Improves visual rendering of holograms to appear more stable and crisp by more accurately accounting for their depth.</span></span> <span data-ttu-id="f7385-342">如果应用在此更新后未正确设置全息影像的深度，此操作将更明显。</span><span class="sxs-lookup"><span data-stu-id="f7385-342">This will be more noticeable if apps do not set the depth of holograms correctly, after this update.</span></span>
- <span data-ttu-id="f7385-343">修复了独占应用和独占应用之间的导航的稳定性。</span><span class="sxs-lookup"><span data-stu-id="f7385-343">Fixes stability of exclusive apps and navigation between exclusive apps.</span></span>
- <span data-ttu-id="f7385-344">解决了混合现实捕获在设备离开待机状态几天后无法录制视频的问题。</span><span class="sxs-lookup"><span data-stu-id="f7385-344">Resolves an issue where Mixed Reality Capture couldn't record video after device is left in standby state for multiple days.</span></span>
- <span data-ttu-id="f7385-345">改善全息图稳定性。</span><span class="sxs-lookup"><span data-stu-id="f7385-345">Improves hologram stability.</span></span>

## <span data-ttu-id="f7385-346">Windows 全息版、版本 1903-2019 更新</span><span class="sxs-lookup"><span data-stu-id="f7385-346">Windows Holographic, version 1903 - November 2019 Update</span></span> 
- <span data-ttu-id="f7385-347">内部版本18362.1039</span><span class="sxs-lookup"><span data-stu-id="f7385-347">Build 18362.1039</span></span>

<span data-ttu-id="f7385-348">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="f7385-348">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="f7385-349">修复了在初始设置 en CA 和 en-us 时出现的 **"选择"** 语音命令。</span><span class="sxs-lookup"><span data-stu-id="f7385-349">Fixes for **"Select"** voice commands during initial set-up for en-CA and en-AU.</span></span>
- <span data-ttu-id="f7385-350">改进了在最新的 Unity 和 MRTK 版本中放置的对象的视觉质量。</span><span class="sxs-lookup"><span data-stu-id="f7385-350">Improvements in visual quality of objects placed far away in latest Unity and MRTK versions.</span></span>
- <span data-ttu-id="f7385-351">修复了在启动并再次关闭 "引脚" 面板时，在启动时仍处于暂停状态的全息应用程序的解决问题。</span><span class="sxs-lookup"><span data-stu-id="f7385-351">Fixes addressing issues with holographic applications being stuck in a paused state on launch until the pins panel is brought up and dismissed again.</span></span>
- <span data-ttu-id="f7385-352">适用于 HoloLens 2 和模拟器的 OpenXR 运行时一致性修复和改进。</span><span class="sxs-lookup"><span data-stu-id="f7385-352">OpenXR runtime conformance fixes and improvements for HoloLens 2 and the emulator.</span></span>


