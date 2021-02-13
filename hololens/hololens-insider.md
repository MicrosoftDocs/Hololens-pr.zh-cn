---
title: Microsoft HoloLens 内部预览版
description: 了解如何开始使用预览体验成员版本，并为 HoloLens 的下一个主要操作系统更新提供有价值的反馈。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 2/2/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 3d7c4b5347019682896bb695690190e633c80677
ms.sourcegitcommit: 23ee06b659d7a51f3000d386c8f67cbf212d5aa4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327396"
---
# <span data-ttu-id="622f6-103">Microsoft HoloLens 内部预览版</span><span class="sxs-lookup"><span data-stu-id="622f6-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="622f6-104">欢迎使用 HoloLens 的最新 Insider Preview 版本！</span><span class="sxs-lookup"><span data-stu-id="622f6-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="622f6-105">开始操作非常简单，并为[](hololens-insider.md#start-receiving-insider-builds)HoloLens 的下一个主要操作系统更新提供有价值的反馈。</span><span class="sxs-lookup"><span data-stu-id="622f6-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="622f6-106">Windows 预览体验成员发行说明</span><span class="sxs-lookup"><span data-stu-id="622f6-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="622f6-107">我们很高兴再次开始向 Windows 预览体验成员提供新功能。</span><span class="sxs-lookup"><span data-stu-id="622f6-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="622f6-108">新内部版本将测试到开发人员频道获取最新更新。</span><span class="sxs-lookup"><span data-stu-id="622f6-108">New builds will be flighting to the Dev Channel for the latest updates.</span></span> <span data-ttu-id="622f6-109">我们将继续更新此页面，因为我们向 Windows 预览体验成员版本添加更多功能和更新。</span><span class="sxs-lookup"><span data-stu-id="622f6-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span>  <span data-ttu-id="622f6-110">感到很高兴，并准备好将这些更新融合到你的现实中。</span><span class="sxs-lookup"><span data-stu-id="622f6-110">Get excited and ready to mix these updates into your reality.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="622f6-111">如果你之前在展台中使用的是"设置"应用或 Microsoft Edge 应用，则我们将这些应用替换为使用不同的应用 ID 的新应用。</span><span class="sxs-lookup"><span data-stu-id="622f6-111">If you were previously using either the Settings app or Microsoft Edge app in a Kiosk, we have replaced these apps with new apps which use a different App ID.</span></span> <span data-ttu-id="622f6-112">我们强烈建议你在下面的展台模式下阅读新[应用的新 AUMID。](#use-the-new-settings-and-edge-apps-in-kiosk-modes)</span><span class="sxs-lookup"><span data-stu-id="622f6-112">We highly encourage you to read [New AUMIDs for new apps in Kiosk mode](#use-the-new-settings-and-edge-apps-in-kiosk-modes) below.</span></span> <span data-ttu-id="622f6-113">这将确保你继续在展台中拥有"设置"应用，或包括新的 Microsoft Edge 应用。</span><span class="sxs-lookup"><span data-stu-id="622f6-113">This will ensure you either continue to have the Settings app in your Kiosk, or include the new Microsoft Edge app.</span></span>

<br>

| <span data-ttu-id="622f6-114">功能名称</span><span class="sxs-lookup"><span data-stu-id="622f6-114">Feature Name</span></span>                                              | <span data-ttu-id="622f6-115">简短说明</span><span class="sxs-lookup"><span data-stu-id="622f6-115">Short description</span></span>                                                                      | <span data-ttu-id="622f6-116">在内部版本可用</span><span class="sxs-lookup"><span data-stu-id="622f6-116">Available in build</span></span> |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [<span data-ttu-id="622f6-117">新版 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="622f6-117">New Microsoft Edge</span></span>](#introducing-the-new-microsoft-edge) | <span data-ttu-id="622f6-118">新的基于 Chromium 的 Microsoft Edge 现在可用于 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="622f6-118">The new, Chromium-based Microsoft Edge is now available for HoloLens 2</span></span>                         | <span data-ttu-id="622f6-119">20279.1006</span><span class="sxs-lookup"><span data-stu-id="622f6-119">20279.1006</span></span> |
| [<span data-ttu-id="622f6-120">WebXR 和 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="622f6-120">WebXR and 360 Viewer</span></span>](#webxr-and-360-viewer)             | <span data-ttu-id="622f6-121">尝试沉浸式 Web 体验和 360 视频播放</span><span class="sxs-lookup"><span data-stu-id="622f6-121">Try immersive web experiences and 360 video playback</span></span>                                           | <span data-ttu-id="622f6-122">20289.1000</span><span class="sxs-lookup"><span data-stu-id="622f6-122">20289.1000</span></span> |
| [<span data-ttu-id="622f6-123">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="622f6-123">New Settings app</span></span>](#new-settings-app)                     | <span data-ttu-id="622f6-124">旧式"设置"应用将替换为具有新功能和设置的更新版本</span><span class="sxs-lookup"><span data-stu-id="622f6-124">The legacy Settings app is being replaced by an updated version with new features and settings</span></span> | <span data-ttu-id="622f6-125">20279.1006</span><span class="sxs-lookup"><span data-stu-id="622f6-125">20279.1006</span></span> |
| [<span data-ttu-id="622f6-126">默认应用选取器</span><span class="sxs-lookup"><span data-stu-id="622f6-126">Default app picker</span></span>](#default-app-picker)                 | <span data-ttu-id="622f6-127">选择应针对每个文件或链接类型启动的应用</span><span class="sxs-lookup"><span data-stu-id="622f6-127">Choose which app should launch for each file or link type</span></span>                                      | <span data-ttu-id="622f6-128">20279.1006</span><span class="sxs-lookup"><span data-stu-id="622f6-128">20279.1006</span></span> |
| [<span data-ttu-id="622f6-129">Office Web 应用</span><span class="sxs-lookup"><span data-stu-id="622f6-129">Office web app</span></span>](#office-web-app)                         | <span data-ttu-id="622f6-130">Office Web 应用的快捷方式现在列在"所有应用"中</span><span class="sxs-lookup"><span data-stu-id="622f6-130">A shortcut to the Office web app is now listed in "All apps"</span></span>                                   | <span data-ttu-id="622f6-131">20279.1006</span><span class="sxs-lookup"><span data-stu-id="622f6-131">20279.1006</span></span> |
| [<span data-ttu-id="622f6-132">轻扫以键入</span><span class="sxs-lookup"><span data-stu-id="622f6-132">Swipe to type</span></span>](#swipe-to-type)                           | <span data-ttu-id="622f6-133">使用手指提示在全息键盘上"轻扫"字词</span><span class="sxs-lookup"><span data-stu-id="622f6-133">Use the tip of your finger to "swipe" words on the holographic keyboard</span></span>                        | <span data-ttu-id="622f6-134">20279.1006</span><span class="sxs-lookup"><span data-stu-id="622f6-134">20279.1006</span></span> |
| [<span data-ttu-id="622f6-135">USB-C 外部麦克风支持</span><span class="sxs-lookup"><span data-stu-id="622f6-135">USB-C External Microphone Support</span></span>](#usb-c-external-microphone-support) | <span data-ttu-id="622f6-136">将 USB-C 麦克风用于应用和/或远程协助。</span><span class="sxs-lookup"><span data-stu-id="622f6-136">Use USB-C microphones for apps and / or Remote Assist.</span></span>| <span data-ttu-id="622f6-137">20279.1006</span><span class="sxs-lookup"><span data-stu-id="622f6-137">20279.1006</span></span> |
| [<span data-ttu-id="622f6-138">展台模式下新应用的新 AUMID</span><span class="sxs-lookup"><span data-stu-id="622f6-138">New AUMIDs for new apps in Kiosk mode</span></span>](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | <span data-ttu-id="622f6-139">新设置和边缘应用的 AUMID</span><span class="sxs-lookup"><span data-stu-id="622f6-139">AUMIDs for new Settings and Edge apps</span></span> | <span data-ttu-id="622f6-140">20279.1006</span><span class="sxs-lookup"><span data-stu-id="622f6-140">20279.1006</span></span> |
| [<span data-ttu-id="622f6-141">页面设置可见性的新 SettingsURIs</span><span class="sxs-lookup"><span data-stu-id="622f6-141">New SettingsURIs for Page Settings Visibility</span></span>](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | <span data-ttu-id="622f6-142">设置/PageVisibilityList 策略的 20+ 新 SettingsURIs</span><span class="sxs-lookup"><span data-stu-id="622f6-142">20+ new SettingsURIs for Settings/PageVisibilityList policy</span></span> | <span data-ttu-id="622f6-143">20289.1000</span><span class="sxs-lookup"><span data-stu-id="622f6-143">20289.1000</span></span> |
| [<span data-ttu-id="622f6-144">改进的展台模式故障帮助</span><span class="sxs-lookup"><span data-stu-id="622f6-144">Improved Kiosk mode failure handing</span></span>](#kiosk-mode-behavior-changes-for-handling-of-failures) | <span data-ttu-id="622f6-145">展台模式在空的"开始"菜单之前查找全局分配的访问权限。</span><span class="sxs-lookup"><span data-stu-id="622f6-145">Kiosk mode looks for Global Assigned Access before empty start menu.</span></span> | <span data-ttu-id="622f6-146">20279.1006</span><span class="sxs-lookup"><span data-stu-id="622f6-146">20279.1006</span></span> |
| [<span data-ttu-id="622f6-147">配置回退诊断</span><span class="sxs-lookup"><span data-stu-id="622f6-147">Configure Fallback Diagnostics</span></span>](#configuring-fallback-diagnostics-via-settings-app) | <span data-ttu-id="622f6-148">在"设置"应用中设置回退诊断行为</span><span class="sxs-lookup"><span data-stu-id="622f6-148">Setting Fallback Diagnostic Behavior in Settings App</span></span> | <span data-ttu-id="622f6-149">20279.1006</span><span class="sxs-lookup"><span data-stu-id="622f6-149">20279.1006</span></span> |
| [<span data-ttu-id="622f6-150">与附近设备共享内容</span><span class="sxs-lookup"><span data-stu-id="622f6-150">Share things with nearby devices</span></span>](#share-things-with-nearby-devices) | <span data-ttu-id="622f6-151">将文件或 URL 从 HoloLens 共享到电脑</span><span class="sxs-lookup"><span data-stu-id="622f6-151">Share files or URLs from a HoloLens to a PC</span></span> | <span data-ttu-id="622f6-152">20279.1006</span><span class="sxs-lookup"><span data-stu-id="622f6-152">20279.1006</span></span> |
| [<span data-ttu-id="622f6-153">新的操作系统更新疑难解答程序</span><span class="sxs-lookup"><span data-stu-id="622f6-153">New OS Update troubleshooter</span></span>](#new-os-update-troubleshooter) | <span data-ttu-id="622f6-154">操作系统更新的设置中的新疑难解答</span><span class="sxs-lookup"><span data-stu-id="622f6-154">New troubleshooter in Settings for OS updates</span></span> | <span data-ttu-id="622f6-155">20279.1006</span><span class="sxs-lookup"><span data-stu-id="622f6-155">20279.1006</span></span> |
| [<span data-ttu-id="622f6-156">更新中的改进和修复</span><span class="sxs-lookup"><span data-stu-id="622f6-156">Improvements and fixes in the update</span></span>](#improvements-and-fixes-in-the-update) | <span data-ttu-id="622f6-157">更新中的其他修补程序。</span><span class="sxs-lookup"><span data-stu-id="622f6-157">Additional fixes in the update.</span></span> | <span data-ttu-id="622f6-158">20279.1006</span><span class="sxs-lookup"><span data-stu-id="622f6-158">20279.1006</span></span> |

### <span data-ttu-id="622f6-159">新 Microsoft Edge 的介绍</span><span class="sxs-lookup"><span data-stu-id="622f6-159">Introducing the new Microsoft Edge</span></span>

![旧 Microsoft Edge 徽标到新 Microsoft Edge 徽标的动画](images/new-edge.gif)

<span data-ttu-id="622f6-161">新的 Microsoft Edge [采用 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 开放源代码项目，为客户创建更好的兼容性，减少 Web 开发人员的 Web 碎片。</span><span class="sxs-lookup"><span data-stu-id="622f6-161">The new Microsoft Edge [adopts the Chromium open source project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) to create better compatibility for customers and less fragmentation of the web for web developers.</span></span>

<span data-ttu-id="622f6-162">通过此预览体验成员预览版，新 Microsoft Edge 首次提供给 HoloLens 2 客户！</span><span class="sxs-lookup"><span data-stu-id="622f6-162">With this Insider preview, the new Microsoft Edge is available to HoloLens 2 customers for the first time!</span></span> <span data-ttu-id="622f6-163">虽然新 Microsoft Edge 最终将替换 HoloLens 2 上的旧版 Microsoft Edge，但预览体验成员目前可以使用这两种浏览器。</span><span class="sxs-lookup"><span data-stu-id="622f6-163">While the new Microsoft Edge will eventually replace legacy Microsoft Edge on HoloLens 2, both browsers are currently available to Insiders.</span></span> <span data-ttu-id="622f6-164">请通过新 Microsoft Edge 中的"\*\*\*\* 发送反馈"功能或通过"反馈中心"与团队[共享反馈和 Bug。](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="622f6-164">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span></span>

![新 Microsoft Edge 屏幕截图](images/new-edge-ui.png)

#### <span data-ttu-id="622f6-166">启动新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="622f6-166">Launching the new Microsoft Edge</span></span>

<span data-ttu-id="622f6-167">预览体验成员可以使用两个版本的 Microsoft Edge：新的 Microsoft Edge 新 Microsoft Edge 图标 (由蓝色和绿色旋转图标) 表示，旧 Microsoft Edge (由白色 ![ ](images/new_edge_logo.png) "e"图标) 表示。</span><span class="sxs-lookup"><span data-stu-id="622f6-167">There are two versions of Microsoft Edge available to Insiders: the new Microsoft Edge ![new Microsoft Edge icon](images/new_edge_logo.png) (represented by a blue and green swirl icon) and legacy Microsoft Edge (represented by the white "e" icon).</span></span> <span data-ttu-id="622f6-168">新的 Microsoft Edge 固定到"开始"菜单，并且会在激活 Web 链接时自动启动。</span><span class="sxs-lookup"><span data-stu-id="622f6-168">The new Microsoft Edge is pinned to the Start menu and will automatically launch when you activate a web link.</span></span> <span data-ttu-id="622f6-169">如果要恢复为使用旧版 Microsoft Edge 作为默认 Web 浏览器，请参阅下面的说明 [重置默认应用](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="622f6-169">If you would like to revert to using legacy Microsoft Edge as your default web browser, see the instructions below for [resetting default apps](#default-app-picker).</span></span>

> [!NOTE]
> <span data-ttu-id="622f6-170">当你首次在 HoloLens 2 上启动新的 Microsoft Edge 时，你的设置和数据将导入旧版 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="622f6-170">When you first launch the new Microsoft Edge on HoloLens 2, your settings and data will be imported from legacy Microsoft Edge.</span></span> <span data-ttu-id="622f6-171">如果在启动新的 Microsoft Edge 后继续使用旧版 Microsoft Edge，则新数据将不会从旧 Microsoft Edge 同步到新的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="622f6-171">If you continue to use legacy Microsoft Edge after launching the new Microsoft Edge, that new data will not be synced from legacy Microsoft Edge to the new Microsoft Edge.</span></span>

#### <span data-ttu-id="622f6-172">配置新 Microsoft Edge 的策略设置</span><span class="sxs-lookup"><span data-stu-id="622f6-172">Configuring policy settings for the new Microsoft Edge</span></span>

<span data-ttu-id="622f6-173">新 Microsoft Edge 为 IT 管理员提供了一组比旧版 Microsoft Edge 更为广泛的 HoloLens 2 浏览器策略。</span><span class="sxs-lookup"><span data-stu-id="622f6-173">The new Microsoft Edge offers IT admins a much broader set of browser policies on HoloLens 2 than were previously available with legacy Microsoft Edge.</span></span>

<span data-ttu-id="622f6-174">下面是一些有用的资源，用于了解有关管理新 Microsoft Edge 的策略设置的信息：</span><span class="sxs-lookup"><span data-stu-id="622f6-174">Here are some helpful resources for learning more about managing policy settings for the new Microsoft Edge:</span></span>

- [<span data-ttu-id="622f6-175">使用 Microsoft Intune 配置 Microsoft Edge 策略设置</span><span class="sxs-lookup"><span data-stu-id="622f6-175">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [<span data-ttu-id="622f6-176">Microsoft Edge 旧版到 Microsoft Edge 策略映射</span><span class="sxs-lookup"><span data-stu-id="622f6-176">Microsoft Edge Legacy to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [<span data-ttu-id="622f6-177">Google Chrome 到 Microsoft Edge 策略映射</span><span class="sxs-lookup"><span data-stu-id="622f6-177">Google Chrome to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- <span data-ttu-id="622f6-178">[完整的 Microsoft Edge 企业版文档](https://docs.microsoft.com/deployedge/)</span><span class="sxs-lookup"><span data-stu-id="622f6-178">Full [Microsoft Edge Enterprise documentation](https://docs.microsoft.com/deployedge/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="622f6-179">由于新的 Microsoft Edge 支持大量浏览器策略，因此团队无法保证每个新策略都适用于 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="622f6-179">Because of the volume of browser policies supported by the new Microsoft Edge, our team is unable to guarantee that each new policy works on HoloLens 2.</span></span> <span data-ttu-id="622f6-180">但是，我们已测试和确认与 HoloLens 2 上以前支持的每个旧 Microsoft Edge 策略等效的新 Microsoft Edge 策略的等效项可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="622f6-180">However, we've tested and confirmed than the new Microsoft Edge equivalent of each legacy Microsoft Edge policy previously supported on HoloLens 2 work as expected.</span></span> <span data-ttu-id="622f6-181">请参阅 [Microsoft Edge 旧版到 Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 策略映射，查找与 HoloLens 2 一同使用的每个旧版 Microsoft Edge 浏览器策略的新 Microsoft Edge 等效项。</span><span class="sxs-lookup"><span data-stu-id="622f6-181">See [Microsoft Edge Legacy to Microsoft Edge policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) to find the new Microsoft Edge equivalent of each legacy Microsoft Edge browser policy you were using with HoloLens 2.</span></span>
>
> <span data-ttu-id="622f6-182">我们了解至少有两个新的 Microsoft Edge 策略将 *不能与* HoloLens 2 一起使用：</span><span class="sxs-lookup"><span data-stu-id="622f6-182">There are at least two new Microsoft Edge policies that we know *will not* work with HoloLens 2:</span></span>
> - <span data-ttu-id="622f6-183">EnterpriseModeSiteList</span><span class="sxs-lookup"><span data-stu-id="622f6-183">EnterpriseModeSiteList</span></span>
> - <span data-ttu-id="622f6-184">EnterpriseSiteListServiceURL</span><span class="sxs-lookup"><span data-stu-id="622f6-184">EnterpriseSiteListServiceURL</span></span>

#### <span data-ttu-id="622f6-185">HoloLens 2 上新 Microsoft Edge 的预计功能</span><span class="sxs-lookup"><span data-stu-id="622f6-185">What to expect from the new Microsoft Edge on HoloLens 2</span></span>

<span data-ttu-id="622f6-186">由于新的 Microsoft Edge 是本机 Win32 应用，具有新的 UWP 适配器层，允许它在仅 UWP 设备（如 HoloLens 2）上运行，因此某些功能可能不会立即可用。</span><span class="sxs-lookup"><span data-stu-id="622f6-186">Because the new Microsoft Edge is a native Win32 app with a new UWP adapter layer allowing it to run on UWP-only devices like HoloLens 2, some features may not be immediately available.</span></span> <span data-ttu-id="622f6-187">我们将支持未来几个月的新方案和功能，因此请查看此空间了解最新信息。</span><span class="sxs-lookup"><span data-stu-id="622f6-187">We'll be supporting new scenarios and features over the coming months, so check this space for up-to-date information.</span></span>

**<span data-ttu-id="622f6-188">预期可工作的方案和功能：</span><span class="sxs-lookup"><span data-stu-id="622f6-188">Scenarios and features expected to work:</span></span>**
- <span data-ttu-id="622f6-189">首次运行体验、登录配置文件和同步</span><span class="sxs-lookup"><span data-stu-id="622f6-189">First-run experience, sign in to profile, and sync</span></span>
- <span data-ttu-id="622f6-190">网站应按预期呈现和行为</span><span class="sxs-lookup"><span data-stu-id="622f6-190">Websites should render and behave as expected</span></span>
- <span data-ttu-id="622f6-191">大多数浏览器功能 (收藏夹、历史记录等) 应正常工作</span><span class="sxs-lookup"><span data-stu-id="622f6-191">Most browser functionality (Favorites, History, etc.) should work as expected</span></span>
- <span data-ttu-id="622f6-192">深色模式</span><span class="sxs-lookup"><span data-stu-id="622f6-192">Dark mode</span></span>
- <span data-ttu-id="622f6-193">将 Web 应用安装到设备</span><span class="sxs-lookup"><span data-stu-id="622f6-193">Installing web apps to the device</span></span>
- <span data-ttu-id="622f6-194">安装扩展 (请告诉我们，如果你使用的任何扩展在 HoloLens 2) </span><span class="sxs-lookup"><span data-stu-id="622f6-194">Installing extensions (please let us know if you use any extensions that don't work properly on HoloLens 2)</span></span>
- <span data-ttu-id="622f6-195">查看和标记 PDF</span><span class="sxs-lookup"><span data-stu-id="622f6-195">Viewing and marking up a PDF</span></span>
- <span data-ttu-id="622f6-196">单个浏览器窗口中的空间声音</span><span class="sxs-lookup"><span data-stu-id="622f6-196">Spatial sound from a single browser window</span></span>
- <span data-ttu-id="622f6-197">浏览器的自动和手动更新</span><span class="sxs-lookup"><span data-stu-id="622f6-197">Automatic and manual updating of the browser</span></span>
- <span data-ttu-id="622f6-198">使用"保存到 PDF"选项 (打印菜单中保存 PDF) </span><span class="sxs-lookup"><span data-stu-id="622f6-198">Saving a PDF from the Print menu (using "Save to PDF" option)</span></span>

**<span data-ttu-id="622f6-199">即将推出方案和功能：</span><span class="sxs-lookup"><span data-stu-id="622f6-199">Scenarios and features coming soon:</span></span>**
- <span data-ttu-id="622f6-200">WebXR 和 360 查看器扩展</span><span class="sxs-lookup"><span data-stu-id="622f6-200">WebXR and 360 Viewer extension</span></span>
- <span data-ttu-id="622f6-201">在环境中跨多个窗口浏览时，内容还原以更正窗口</span><span class="sxs-lookup"><span data-stu-id="622f6-201">Content restoration to correct window when browsing across multiple windows placed in your environment</span></span>

**<span data-ttu-id="622f6-202">不需要工作的方案和功能：</span><span class="sxs-lookup"><span data-stu-id="622f6-202">Scenarios and features not expected to work:</span></span>**
- <span data-ttu-id="622f6-203">具有同时音频流的多个窗口的空间声音</span><span class="sxs-lookup"><span data-stu-id="622f6-203">Spatial sound from multiple windows with simultaneous audio streams</span></span>
- <span data-ttu-id="622f6-204">"查看它，说出它"</span><span class="sxs-lookup"><span data-stu-id="622f6-204">"See it, say it"</span></span>
- <span data-ttu-id="622f6-205">打印</span><span class="sxs-lookup"><span data-stu-id="622f6-205">Printing</span></span>

**<span data-ttu-id="622f6-206">热门的浏览器问题：</span><span class="sxs-lookup"><span data-stu-id="622f6-206">Top known browser issues:</span></span>**
- <span data-ttu-id="622f6-207">重置设备将删除新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="622f6-207">Resetting your device will remove the new Microsoft Edge</span></span>
- <span data-ttu-id="622f6-208">全息键盘中的放大镜预览显示不正确的内容</span><span class="sxs-lookup"><span data-stu-id="622f6-208">The magnifier preview in the holographic keyboard shows incorrect content</span></span>

#### <span data-ttu-id="622f6-209">Microsoft Edge 预览体验成员频道</span><span class="sxs-lookup"><span data-stu-id="622f6-209">Microsoft Edge Insider channels</span></span>

<span data-ttu-id="622f6-210">Microsoft Edge 团队向 Edge 预览体验成员社区提供三个预览频道：Beta、Dev 和 Canary。</span><span class="sxs-lookup"><span data-stu-id="622f6-210">The Microsoft Edge team makes three preview channels available to the Edge Insider community: Beta, Dev, and Canary.</span></span> <span data-ttu-id="622f6-211">安装预览通道不会卸载 HoloLens 2 上发布的 Microsoft Edge 版本，并且可以同时安装多个。</span><span class="sxs-lookup"><span data-stu-id="622f6-211">Installing a preview channel doesn't uninstall the released version of Microsoft Edge on your HoloLens 2, and you can install more than one at the same time.</span></span> 

<span data-ttu-id="622f6-212">访问 [Microsoft Edge 预览体验成员主页](https://www.microsoftedgeinsider.com) ，了解有关 Edge 预览体验成员社区的信息。</span><span class="sxs-lookup"><span data-stu-id="622f6-212">Visit the [Microsoft Edge Insider homepage](https://www.microsoftedgeinsider.com) to learn more about the Edge Insider community.</span></span> <span data-ttu-id="622f6-213">若要了解有关不同边缘预览体验成员频道和入门的信息，请访问 Edge [预览体验成员下载页面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="622f6-213">To learn more about the different Edge Insider channels and get started, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>

<span data-ttu-id="622f6-214">有两种方法可用于将 Microsoft Edge 预览体验成员频道安装到 HoloLens 2：</span><span class="sxs-lookup"><span data-stu-id="622f6-214">There are a couple methods available for installing Microsoft Edge Insider channels to HoloLens 2:</span></span>

**<span data-ttu-id="622f6-215">直接安装在设备上 (当前仅适用于非托管设备) </span><span class="sxs-lookup"><span data-stu-id="622f6-215">Direct install on device (currently only available to unmanaged devices)</span></span>**
  1. <span data-ttu-id="622f6-216">在 HoloLens 2 上，访问 [Edge 预览体验成员下载页面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="622f6-216">On your HoloLens 2, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>
  1. <span data-ttu-id="622f6-217">选择要安装的边缘预览体验成员频道的"下载 **HoloLens 2"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="622f6-217">Select the **Download for HoloLens 2** button for the Edge Insider channel you wish to install.</span></span>
  1. <span data-ttu-id="622f6-218">使用"文件资源管理器" (从边缘下载队列或设备的"下载"文件夹中启动下载的 .msix) 。</span><span class="sxs-lookup"><span data-stu-id="622f6-218">Launch the downloaded .msix file from the Edge download queue or from your device's "Downloads" folder (using File Explorer).</span></span>
  1. <span data-ttu-id="622f6-219">[应用安装程序](app-deploy-app-installer.md) 将启动。</span><span class="sxs-lookup"><span data-stu-id="622f6-219">[App installer](app-deploy-app-installer.md) will launch.</span></span>
  1. <span data-ttu-id="622f6-220">选择 **"安装"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="622f6-220">Select the **Install** button.</span></span>
  1. <span data-ttu-id="622f6-221">成功安装后，你将在"开始"菜单的"所有应用"列表中发现 Microsoft Edge Beta、Dev 或 Canary 作为单独的条目。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="622f6-221">After successful install, you'll find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu.</span></span>

**<span data-ttu-id="622f6-222">通过具有 Windows Device Portal [ (的电脑进行](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) 安装需要在 HoloLens 2 设备上启用开发人员) </span><span class="sxs-lookup"><span data-stu-id="622f6-222">Install via PC with Windows Device Portal (requires [developer mode](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) to be enabled on HoloLens 2)</span></span>**
  1. <span data-ttu-id="622f6-223">在电脑上，访问 [Edge 预览体验成员下载页面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="622f6-223">On your PC, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>
  1. <span data-ttu-id="622f6-224">选择要 **安装** 的边缘预览体验成员频道的"为 Windows 10 下载"按钮旁边的下拉箭头按钮。</span><span class="sxs-lookup"><span data-stu-id="622f6-224">Select the **drop-down arrow button** next to the "Download for Windows 10" button for the Edge Insider channel you wish to install.</span></span>
  1. <span data-ttu-id="622f6-225">在**下拉菜单中选择 HoloLens 2。**</span><span class="sxs-lookup"><span data-stu-id="622f6-225">Select **HoloLens 2** in the drop-down menu.</span></span>
  1. <span data-ttu-id="622f6-226">将 .msix 文件保存到电脑文件夹的"下载 (或其他文件夹，你可以轻松找到) 。</span><span class="sxs-lookup"><span data-stu-id="622f6-226">Save the .msix file to the "Downloads" folder of your PC (or another folder you can easily find).</span></span>
  1. <span data-ttu-id="622f6-227">使用 [电脑上的 Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 在 HoloLens 2 上安装下载的 .msix 文件。</span><span class="sxs-lookup"><span data-stu-id="622f6-227">Use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) on your PC to install the downloaded .msix file on HoloLens 2.</span></span>
  1. <span data-ttu-id="622f6-228">成功安装后，你将在"开始"菜单的"所有应用"列表中发现 Microsoft Edge Beta、Dev 或 Canary 作为单独的条目。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="622f6-228">After successful install, you'll find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu.</span></span>

> [!NOTE]
> <span data-ttu-id="622f6-229">在此适用于 HoloLens 2 的 Windows 预览体验成员预览版期间，你设备上 Microsoft Edge 的版本可能高于某些 (或所有) Microsoft Edge 预览体验成员频道中提供的版本。</span><span class="sxs-lookup"><span data-stu-id="622f6-229">During this Windows Insider preview for HoloLens 2, the version of Microsoft Edge on your device may be higher than those available in some (or all) of the Microsoft Edge Insider channels.</span></span> <span data-ttu-id="622f6-230">这是为了确保专门面向 HoloLens 2 上的 Web 浏览器的新功能和修补程序尽快进入我们的 Windows 预览体验成员。</span><span class="sxs-lookup"><span data-stu-id="622f6-230">This is to ensure new features and fixes specifically targeting the web browser on HoloLens 2 are getting to our Windows Insiders as quickly as possible.</span></span> <span data-ttu-id="622f6-231">在公开发布下一个 Windows 更新后，Microsoft Edge 预览体验成员频道版本将超过 HoloLens 2 上的 Microsoft Edge 版本，并保持领先。</span><span class="sxs-lookup"><span data-stu-id="622f6-231">Shortly after the public release of the next Windows update, the Microsoft Edge Insider channel builds will surpass, and stay ahead of, the version of Microsoft Edge on your HoloLens 2.</span></span>

### <span data-ttu-id="622f6-232">WebXR 和 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="622f6-232">WebXR and 360 Viewer</span></span>

*<span data-ttu-id="622f6-233">在 Windows 预览体验成员版本 20289.1000 中添加</span><span class="sxs-lookup"><span data-stu-id="622f6-233">Added in Windows Insider build 20289.1000</span></span>*

<span data-ttu-id="622f6-234">新的 Microsoft Edge 包括对 WebXR 的支持，WebXR 是用于创建沉浸式 Web 体验的新标准， (WebVR) 。</span><span class="sxs-lookup"><span data-stu-id="622f6-234">The new Microsoft Edge includes support for WebXR, which is the new standard for creating immersive web experiences (replacing WebVR).</span></span> <span data-ttu-id="622f6-235">许多沉浸式 Web 体验在设计时都考虑到了 (将你的视野替换为虚拟环境) ，但 HoloLens 2 也支持这些体验。</span><span class="sxs-lookup"><span data-stu-id="622f6-235">Many immersive web experiences were designed with VR in mind (they replace your field of view with a virtual environment), but these experiences are also supported by HoloLens 2.</span></span> <span data-ttu-id="622f6-236">WebXR 标准还支持使用物理环境的增强和混合现实沉浸式 Web 体验。</span><span class="sxs-lookup"><span data-stu-id="622f6-236">The WebXR standard also enables augmented and mixed reality immersive web experiences that use your physical environment.</span></span> <span data-ttu-id="622f6-237">随着开发人员在 WebXR 上花费更多时间，我们预计新的增强和混合现实沉浸式体验将到达 HoloLens 2 客户试用！</span><span class="sxs-lookup"><span data-stu-id="622f6-237">As developers spend more time with WebXR, we anticipate new augmented and mixed reality immersive experiences will arrive for HoloLens 2 customers to try!</span></span>

<span data-ttu-id="622f6-238">360 查看器扩展基于 WebXR 构建，并自动与 HoloLens 2 上的新 Microsoft Edge 一起安装。</span><span class="sxs-lookup"><span data-stu-id="622f6-238">The 360 Viewer extension is built on WebXR and automatically installs alongside the new Microsoft Edge on HoloLens 2.</span></span> <span data-ttu-id="622f6-239">此 Web 扩展让你能够沉浸于 360 度视频中。</span><span class="sxs-lookup"><span data-stu-id="622f6-239">This web extension gives you the ability to immerse yourself in 360-degree videos.</span></span> <span data-ttu-id="622f6-240">YouTube 提供了最多 360 个视频选择，因此我们建议您从该视频开始。</span><span class="sxs-lookup"><span data-stu-id="622f6-240">YouTube offers the largest selection of 360 videos, so we encourage you to start there.</span></span>

#### <span data-ttu-id="622f6-241">如何使用 WebXR</span><span class="sxs-lookup"><span data-stu-id="622f6-241">How to use WebXR</span></span>

1. <span data-ttu-id="622f6-242">导航到具有 WebXR 支持的网站。</span><span class="sxs-lookup"><span data-stu-id="622f6-242">Navigate to a website with WebXR support.</span></span>
1. <span data-ttu-id="622f6-243">选择网站上 **"输入VR"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="622f6-243">Select the **Enter VR** button on the website.</span></span> <span data-ttu-id="622f6-244">此按钮的位置和视觉表示形式可能因网站而异，但外观可能类似于：</span><span class="sxs-lookup"><span data-stu-id="622f6-244">The location and visual representation of this button may vary per website, but it may look similar to:</span></span>

    ![输入"VR"按钮示例](images/75px-enter-vr.png)

1. <span data-ttu-id="622f6-246">首次尝试启动特定域上的 WebXR 体验时，浏览器会请求同意以输入沉浸式视图，选择"**允许"。**</span><span class="sxs-lookup"><span data-stu-id="622f6-246">The first time you try to launch a WebXR experience on a specific domain, the browser will ask for consent to enter an immersive view, select **Allow**.</span></span>
1. <span data-ttu-id="622f6-247">使用 [HoloLens 2 手势](hololens2-basic-usage.md#the-hand-tracking-frame) 操作体验。</span><span class="sxs-lookup"><span data-stu-id="622f6-247">Use [HoloLens 2 gestures](hololens2-basic-usage.md#the-hand-tracking-frame) to manipulate the experience.</span></span>
1. <span data-ttu-id="622f6-248">如果体验没有**退出按钮，** 请使用"开始"手势返回主页[](hololens2-basic-usage.md#start-gesture)。</span><span class="sxs-lookup"><span data-stu-id="622f6-248">If the experience doesn't have an **Exit** button, use the [Start gesture](hololens2-basic-usage.md#start-gesture) to return home.</span></span>

**<span data-ttu-id="622f6-249">建议的 WebXR 示例</span><span class="sxs-lookup"><span data-stu-id="622f6-249">Recommended WebXR samples</span></span>**
- <span data-ttu-id="622f6-250">360 Viewer (请参阅下一节) </span><span class="sxs-lookup"><span data-stu-id="622f6-250">360 Viewer (see next section)</span></span>
- [<span data-ttu-id="622f6-251">XR 恐龙</span><span class="sxs-lookup"><span data-stu-id="622f6-251">XR Dinosaurs</span></span>](https://www.xrdinosaurs.com/)
- [<span data-ttu-id="622f6-252">Barista Express</span><span class="sxs-lookup"><span data-stu-id="622f6-252">Barista Express</span></span>](https://constructarca.de/game/barista-express/)
- [<span data-ttu-id="622f6-253">WebXR 绘制</span><span class="sxs-lookup"><span data-stu-id="622f6-253">WebXR Paint</span></span>](https://threejs.org/examples/webxr_vr_paint.html)

#### <span data-ttu-id="622f6-254">如何使用 360 查看器</span><span class="sxs-lookup"><span data-stu-id="622f6-254">How to use 360 Viewer</span></span>

1. <span data-ttu-id="622f6-255">导航到 YouTube 上的 360 度视频。</span><span class="sxs-lookup"><span data-stu-id="622f6-255">Navigate to a 360-degree video on YouTube.</span></span>
1. <span data-ttu-id="622f6-256">在视频帧中，选择混合现实耳机按钮：</span><span class="sxs-lookup"><span data-stu-id="622f6-256">In the video frame, select the mixed reality headset button:</span></span>

    ![用于激活 360 查看器的按钮](images/enter-360-viewer.jpg)

1. <span data-ttu-id="622f6-258">首次尝试在特定域中启动 360 查看器时，浏览器将请求同意输入沉浸式视图。</span><span class="sxs-lookup"><span data-stu-id="622f6-258">The first time you try to launch 360 Viewer on a specific domain, the browser will ask for consent to enter an immersive view.</span></span> <span data-ttu-id="622f6-259">选择 **"允许"。**</span><span class="sxs-lookup"><span data-stu-id="622f6-259">Select **Allow**.</span></span>
1. <span data-ttu-id="622f6-260">[通过点击](hololens2-basic-usage.md#select-using-air-tap) 来显示播放控件。</span><span class="sxs-lookup"><span data-stu-id="622f6-260">[Air tap](hololens2-basic-usage.md#select-using-air-tap) to bring up the playback controls.</span></span> <span data-ttu-id="622f6-261">使用 [手](hololens2-basic-usage.md#select-using-air-tap) 风和空点击播放/暂停、向前/后退、打开/关闭标题或停止体验 (退出沉浸式视图) 。</span><span class="sxs-lookup"><span data-stu-id="622f6-261">Use [hand rays and air tap](hololens2-basic-usage.md#select-using-air-tap) to play/pause, skip forward/back, turn captions on/off, or stop the experience (which exits the immersive view).</span></span> <span data-ttu-id="622f6-262">播放控件将在几秒钟的不活动状态后消失。</span><span class="sxs-lookup"><span data-stu-id="622f6-262">The playback controls will disappear after a few seconds of inactivity.</span></span>

#### <span data-ttu-id="622f6-263">热门 WebXR 和 360 Viewer 已知问题</span><span class="sxs-lookup"><span data-stu-id="622f6-263">Top WebXR and 360 Viewer known issues</span></span>
- <span data-ttu-id="622f6-264">在 WebXR 体验中，当你倾斜头或四处移动时，全息影像可能会移动或倾斜。</span><span class="sxs-lookup"><span data-stu-id="622f6-264">In WebXR experiences, holograms may shift or tilt when you tilt your head or move around your environment.</span></span>
- <span data-ttu-id="622f6-265">根据 WebXR 体验的复杂性，帧速率可能会下降或不一样。</span><span class="sxs-lookup"><span data-stu-id="622f6-265">Depending on the complexity of the WebXR experience, the framerate may drop or stutter.</span></span>
- <span data-ttu-id="622f6-266">WebXR 中尚不提供手接点。</span><span class="sxs-lookup"><span data-stu-id="622f6-266">Articulated hand joints are not yet available in WebXR.</span></span>
- <span data-ttu-id="622f6-267">退出 WebXR 或 360 查看器体验时，混合现实家庭中的全息影像可能需要 30 秒或更多时间重新出现。</span><span class="sxs-lookup"><span data-stu-id="622f6-267">When exiting a WebXR or 360 Viewer experience, it may take 30 seconds or more for holograms in the mixed reality home to reappear.</span></span>
- <span data-ttu-id="622f6-268">来自 YouTube 网站（而非 YouTube）的 360 个视频可能无法如期工作。</span><span class="sxs-lookup"><span data-stu-id="622f6-268">360 videos from websites other than YouTube may not work as expected.</span></span>
- <span data-ttu-id="622f6-269">如果 360 个视频未进入沉浸式 (或混合现实耳机按钮未) ，请尝试刷新页面。</span><span class="sxs-lookup"><span data-stu-id="622f6-269">If 360 videos don't enter immersive view (or the mixed reality headset button doesn't appear), try refreshing the page.</span></span>
- <span data-ttu-id="622f6-270">标题在 HoloLens 2 上的 360 查看器中尚不可见。</span><span class="sxs-lookup"><span data-stu-id="622f6-270">Captions are not yet visible in 360 Viewer on HoloLens 2.</span></span>
- <span data-ttu-id="622f6-271">暂停 360 查看器中的视频会阻止视频 (但正确选择播放按钮可恢复) 。</span><span class="sxs-lookup"><span data-stu-id="622f6-271">Pausing a video in 360 Viewer stops the video from rendering (but selecting the play button correctly resumes playback).</span></span>
- <span data-ttu-id="622f6-272">360 Viewer 中的"下一个视频"按钮当前不起作用。</span><span class="sxs-lookup"><span data-stu-id="622f6-272">The "next video" button in 360 Viewer does not currently work.</span></span>
- <span data-ttu-id="622f6-273">可以在沉浸式"theater"模式下播放 2D 视频，但帧速率将小于 30 fps。</span><span class="sxs-lookup"><span data-stu-id="622f6-273">You can play 2D videos in an immersive "theater" mode, but the framerate will be less than 30 fps.</span></span>

#### <span data-ttu-id="622f6-274">提供有关 WebXR 和 360 查看器的反馈</span><span class="sxs-lookup"><span data-stu-id="622f6-274">Providing feedback on WebXR and 360 Viewer</span></span>

<span data-ttu-id="622f6-275">请通过新 Microsoft Edge 中的"\*\*\*\* 发送反馈"功能与团队共享反馈和 Bug。</span><span class="sxs-lookup"><span data-stu-id="622f6-275">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge.</span></span>

### <span data-ttu-id="622f6-276">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="622f6-276">New Settings app</span></span>

<span data-ttu-id="622f6-277">通过此版本，我们将引入新版本的"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="622f6-277">With this release, we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="622f6-278">新的"设置"应用包括以下领域的 HoloLens 2 新功能和扩展设置：声音、Power & 睡眠、网络 & Internet、应用、帐户、轻松使用等。</span><span class="sxs-lookup"><span data-stu-id="622f6-278">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="622f6-279">由于新的"设置"应用不同于旧式"设置"应用，因此更新时将删除之前放置在环境周围的任何"设置"窗口。</span><span class="sxs-lookup"><span data-stu-id="622f6-279">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

!["新建设置"应用主页](images/new-settings-app.png)

**<span data-ttu-id="622f6-281">新功能和设置</span><span class="sxs-lookup"><span data-stu-id="622f6-281">New features and settings</span></span>**
- <span data-ttu-id="622f6-282">设置搜索：使用关键字或设置名称从"设置"主页搜索设置。</span><span class="sxs-lookup"><span data-stu-id="622f6-282">Settings search: search for settings from the Settings homepage using keywords or the setting's name.</span></span>
- <span data-ttu-id="622f6-283">系统>声音：</span><span class="sxs-lookup"><span data-stu-id="622f6-283">System > Sound:</span></span>
  - <span data-ttu-id="622f6-284">输入和输出音频设备：独立选择输入和输出音频设备 (例如，通过 Bluetooth 耳机收听音频或使用 USB-C 麦克风进行音频输入) 。</span><span class="sxs-lookup"><span data-stu-id="622f6-284">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span> 
    > [!NOTE]
    > <span data-ttu-id="622f6-285">Bluetooth HoloLens 2 不支持麦克风。</span><span class="sxs-lookup"><span data-stu-id="622f6-285">Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="622f6-286">应用量：独立调整每个应用的音量。</span><span class="sxs-lookup"><span data-stu-id="622f6-286">App volume: independently adjust the volume of each app.</span></span>
- <span data-ttu-id="622f6-287">系统>电源&睡眠：选择设备在一段时间不活动后应何时进入睡眠状态。</span><span class="sxs-lookup"><span data-stu-id="622f6-287">System > Power & sleep: choose when the device should go to sleep after a period of inactivity.</span></span>
- <span data-ttu-id="622f6-288">系统>：手动启用节电模式或设置节电模式自动打开的电池阈值。</span><span class="sxs-lookup"><span data-stu-id="622f6-288">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically.</span></span>
- <span data-ttu-id="622f6-289">USB >设备：默认情况下可以禁用 USB 连接。</span><span class="sxs-lookup"><span data-stu-id="622f6-289">Devices > USB: you can disable USB connections by default.</span></span>
- <span data-ttu-id="622f6-290">Internet &网络：</span><span class="sxs-lookup"><span data-stu-id="622f6-290">Network & Internet:</span></span>
  - <span data-ttu-id="622f6-291">USB-C 以太网适配器现在将显示在 Internet &中。</span><span class="sxs-lookup"><span data-stu-id="622f6-291">USB-C Ethernet adapters will now appear in Network & Internet.</span></span>
  - <span data-ttu-id="622f6-292">USB-C 以太网适配器设置现已可用，包括其 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="622f6-292">USB-C Ethernet adapter settings are now available, including its IP address.</span></span>
  - <span data-ttu-id="622f6-293">你现在可以在 HoloLens 2 上启用飞行模式。</span><span class="sxs-lookup"><span data-stu-id="622f6-293">You can now enable airplane mode on HoloLens 2.</span></span>
- <span data-ttu-id="622f6-294">应用：你可以重置用于文件和链接类型的默认应用。</span><span class="sxs-lookup"><span data-stu-id="622f6-294">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="622f6-295">有关详细信息，请参阅 [默认应用选取器](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="622f6-295">For more information see [Default app picker](#default-app-picker).</span></span>
- <span data-ttu-id="622f6-296">其他用户>帐户：设备所有者可以添加用户、将标准用户升级到设备所有者、将设备所有者降级为标准用户以及删除用户。</span><span class="sxs-lookup"><span data-stu-id="622f6-296">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="622f6-297">轻松访问：更改文本大小和一些视觉效果。</span><span class="sxs-lookup"><span data-stu-id="622f6-297">Ease of Access: change text size and some visual effects.</span></span>

**<span data-ttu-id="622f6-298">已知问题</span><span class="sxs-lookup"><span data-stu-id="622f6-298">Known issues</span></span>**
- <span data-ttu-id="622f6-299">之前放置的"设置"窗口将被删除 (请参阅上述) 。</span><span class="sxs-lookup"><span data-stu-id="622f6-299">Previously placed Settings windows will be removed (see note above).</span></span>
- <span data-ttu-id="622f6-300">访问"通知"页可能会使"设置"应用崩溃 (调查) 。</span><span class="sxs-lookup"><span data-stu-id="622f6-300">Visiting the Notifications page may crash the Settings app (investigating).</span></span>
- <span data-ttu-id="622f6-301">以太网页面当前不会显示 (即将修复) 。</span><span class="sxs-lookup"><span data-stu-id="622f6-301">The Ethernet page currently doesn't show up (to be fixed soon).</span></span>
- <span data-ttu-id="622f6-302">你无法再使用"设置"应用重命名设备 (IT 管理员可以使用预配包或 MDM 重命名设备) 。</span><span class="sxs-lookup"><span data-stu-id="622f6-302">You can no longer rename your device with the Settings app (IT admins can use provisioning packages or MDM to rename devices).</span></span>
- <span data-ttu-id="622f6-303">新 Microsoft Edge 的电池使用情况可能不准确，因为其性质是 UWP 适配器层支持的 Win32 桌面应用程序 (预计) 。</span><span class="sxs-lookup"><span data-stu-id="622f6-303">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon).</span></span>

### <span data-ttu-id="622f6-304">默认应用选取器</span><span class="sxs-lookup"><span data-stu-id="622f6-304">Default app picker</span></span>

<span data-ttu-id="622f6-305">激活超链接或打开具有多个已安装应用（支持该超链接）的文件类型时，你将看到一个新窗口打开，提示你选择应处理文件或链接类型的已安装应用。</span><span class="sxs-lookup"><span data-stu-id="622f6-305">When you activate a hyperlink or open a file type with more than one installed app, which supports it, you will see a new window open prompting you to select which installed app should handle the file or link type.</span></span> <span data-ttu-id="622f6-306">在此窗口中，还可以选择让所选应用处理文件或链接类型"一次"或"始终"。</span><span class="sxs-lookup"><span data-stu-id="622f6-306">In this window, you can also choose to have the selected app handle the file or link type "Once" or "Always."</span></span>

![应用选取器窗口](images/default-app-picker.png)

<span data-ttu-id="622f6-308">如果你选择"始终"，但后来想要更改哪个应用处理特定文件或链接类型，可以在"设置"或"应用"中重置> **默认值**。</span><span class="sxs-lookup"><span data-stu-id="622f6-308">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span></span> <span data-ttu-id="622f6-309">滚动到页面底部，然后选择"文件类型的默认应用\*\*\*\*"和/或"链接类型的默认应用"下的"清除"按钮。</span><span class="sxs-lookup"><span data-stu-id="622f6-309">Scroll to the bottom of the page and select the **Clear** button under "Default apps for file types" and/or "Default apps for link types."</span></span> <span data-ttu-id="622f6-310">与桌面电脑中的类似设置不同，不能重置单个文件类型默认值。</span><span class="sxs-lookup"><span data-stu-id="622f6-310">Unlike the similar setting on desktop PCs, you can't reset individual file type defaults.</span></span>

### <span data-ttu-id="622f6-311">Office Web 应用</span><span class="sxs-lookup"><span data-stu-id="622f6-311">Office web app</span></span>

<span data-ttu-id="622f6-312">Office Web 应用已添加到"开始"菜单中的"所有应用"列表中。</span><span class="sxs-lookup"><span data-stu-id="622f6-312">The Office web app has been added to the "All apps" list in the Start menu.</span></span> <span data-ttu-id="622f6-313">此 Web 应用还可以固定到"开始"页面或卸载。</span><span class="sxs-lookup"><span data-stu-id="622f6-313">This web app can also be pinned to Start or uninstalled.</span></span> <span data-ttu-id="622f6-314">因为这是一个 Web 应用，因此其功能与通过访问体验完全匹配 https://www.office.com 。</span><span class="sxs-lookup"><span data-stu-id="622f6-314">Because this is a web app, its functionality matches exactly what you'd experience by visiting https://www.office.com.</span></span> <span data-ttu-id="622f6-315">仅在 HoloLens 2 具有活动的 Internet 连接时，Office Web 应用功能才可用。</span><span class="sxs-lookup"><span data-stu-id="622f6-315">Office web app functionality is only available when your HoloLens 2 has an active internet connection.</span></span>

### <span data-ttu-id="622f6-316">轻扫以键入</span><span class="sxs-lookup"><span data-stu-id="622f6-316">Swipe to type</span></span>

<span data-ttu-id="622f6-317">一些客户发现，通过轻扫要键入的单词的形状，在虚拟键盘上"键入"速度更快，我们正在预览全息键盘的此功能。</span><span class="sxs-lookup"><span data-stu-id="622f6-317">Some customers find it faster to "type" on virtual keyboards by swiping the shape of the word they intend to type, and we're previewing this feature for the holographic keyboard.</span></span> <span data-ttu-id="622f6-318">通过通过全息键盘的平面传递手指的尖角，轻扫该单词的形状，然后从键盘平面上撤消手指的提示，可以一次轻扫一个单词。</span><span class="sxs-lookup"><span data-stu-id="622f6-318">You can swipe one word at a time by passing the tip of your finger through the plane of the holographic keyboard, swiping the shape of the word, and then withdrawing the tip of your finger from the plane of the keyboard.</span></span> <span data-ttu-id="622f6-319">通过从键盘中删除手指，无需按空格键，即可轻扫后续字词。</span><span class="sxs-lookup"><span data-stu-id="622f6-319">You can swipe follow up words without needing to press the spacebar by removing your finger from the keyboard between words.</span></span> <span data-ttu-id="622f6-320">如果你看到手指在键盘上移动后有轻扫轨迹，你将知道该功能正在工作。</span><span class="sxs-lookup"><span data-stu-id="622f6-320">You will know the feature is working if you see a swipe trail following your finger's movement on the keyboard.</span></span>

<span data-ttu-id="622f6-321">请注意，此功能可能很难使用和掌握，因为全息键盘的性质，与移动电话显示器 (无法抵御手指) 。</span><span class="sxs-lookup"><span data-stu-id="622f6-321">Please note, this feature can be tricky to use and master because of the nature of a holographic keyboard where you don't feel resistance against your finger (unlike a mobile phone display).</span></span> <span data-ttu-id="622f6-322">我们正在评估此功能以公开发布，因此您的反馈非常重要;无论你发现此功能有用还是有反馈反馈，请通过反馈中心 [告诉我们](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="622f6-322">We are evaluating this feature for public release, so your feedback is important; whether you find the feature useful or you have constructive feedback, please let us know via [Feedback Hub](hololens-feedback.md).</span></span>

### <span data-ttu-id="622f6-323">USB-C 外部麦克风支持</span><span class="sxs-lookup"><span data-stu-id="622f6-323">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="622f6-324">插入 **USB 麦克风不会自动将其设置为输入设备**。</span><span class="sxs-lookup"><span data-stu-id="622f6-324">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="622f6-325">在插入一组 USB-C 耳机时，用户将观察到耳机的音频将自动重定向到耳机，但 HoloLens 操作系统会将内部麦克风阵列设置为高于任何其他输入设备的优先级。</span><span class="sxs-lookup"><span data-stu-id="622f6-325">When plugging in a set of USB-C headphones users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> **<span data-ttu-id="622f6-326">若要使用 USB-C 麦克风，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="622f6-326">In order to use a USB-C microphone follow the steps below.</span></span>**

<span data-ttu-id="622f6-327">用户可以使用"声音设置"面板选择连接 USB-C **的外部麦克风** 。</span><span class="sxs-lookup"><span data-stu-id="622f6-327">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="622f6-328">USB-C 麦克风可用于呼叫、录制等。</span><span class="sxs-lookup"><span data-stu-id="622f6-328">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="622f6-329">打开"**设置"** 应用，然后选择 **"系统**  ->  **声音"。**</span><span class="sxs-lookup"><span data-stu-id="622f6-329">Open the **Settings** app and select **System** -> **Sound**.</span></span>

![声音设置](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="622f6-331">若要将外部麦克风与 **远程协助**一同使用，用户需要单击"管理声音设备"超链接。</span><span class="sxs-lookup"><span data-stu-id="622f6-331">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="622f6-332">然后使用下拉列表将外部麦克风设置为"默认" **或** " **通信默认值"。**</span><span class="sxs-lookup"><span data-stu-id="622f6-332">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="622f6-333">选择 **"** 默认值"意味着外部麦克风将在任何位置使用。</span><span class="sxs-lookup"><span data-stu-id="622f6-333">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="622f6-334">选择 **"** 通信默认值"意味着外部麦克风将用于远程协助和其他通信应用，但 HoloLens 麦克风阵列仍可用于其他任务。</span><span class="sxs-lookup"><span data-stu-id="622f6-334">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![管理声音设备](images/usbc-mic-2.png)

<br>

![设置麦克风默认值](images/usbc-mic-3.jpg)

#### <span data-ttu-id="622f6-337">麦克风Bluetooth如何？</span><span class="sxs-lookup"><span data-stu-id="622f6-337">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="622f6-338">遗憾的是Bluetooth HoloLens 2 上当前仍不支持麦克风。</span><span class="sxs-lookup"><span data-stu-id="622f6-338">Unfortunately Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

#### <span data-ttu-id="622f6-339">USB-C 麦克风疑难解答</span><span class="sxs-lookup"><span data-stu-id="622f6-339">Troubleshooting USB-C microphones</span></span>

<span data-ttu-id="622f6-340">请注意，某些 USB-C 麦克风错误地将自己报告为麦克风*和扬声器。*</span><span class="sxs-lookup"><span data-stu-id="622f6-340">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="622f6-341">这是麦克风的问题，而不是 HoloLens 的问题。</span><span class="sxs-lookup"><span data-stu-id="622f6-341">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="622f6-342">将其中一个麦克风插入 HoloLens 时，可能会丢失声音。</span><span class="sxs-lookup"><span data-stu-id="622f6-342">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="622f6-343">幸运的是，有一个简单的解决方法。</span><span class="sxs-lookup"><span data-stu-id="622f6-343">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="622f6-344">在 **"设置**  ->  **系统**  ->  **声音\*\*\*\*\*\*"中，将内置扬声器 (**模拟功能\*\*音频驱动程序) 默认设备。</span><span class="sxs-lookup"><span data-stu-id="622f6-344">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="622f6-345">HoloLens 应记住此设置，即使稍后删除了麦克风并重新连接。</span><span class="sxs-lookup"><span data-stu-id="622f6-345">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C 麦克风疑难解答](images/usbc-mic-4.png)

### <span data-ttu-id="622f6-347">在展台模式下使用新的"设置"和"边缘"应用</span><span class="sxs-lookup"><span data-stu-id="622f6-347">Use the new Settings and Edge apps in Kiosk modes</span></span>

<span data-ttu-id="622f6-348">在 [展台中](hololens-kiosk.md)加入应用时，IT 管理员通常会将应用添加到展台，但使用应用用户模型 ID (AUMID) 。</span><span class="sxs-lookup"><span data-stu-id="622f6-348">When including apps in [Kiosks](hololens-kiosk.md), an IT Admin often adds the app to the Kiosk but using it's App User Model ID (AUMID).</span></span> <span data-ttu-id="622f6-349">由于"设置"应用和 Microsoft Edge 应用都被视为新应用，并且不同于使用这些应用的 AUMID 的较旧应用展台，因此将需要更新以使用新的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="622f6-349">Because both the Settings app and Microsoft Edge app are considered new apps and different than the older apps Kiosks that use AUMIDs for those apps will need to be updated to use the new AUMID.</span></span>

<span data-ttu-id="622f6-350">在修改展台以包含新应用时，我们建议在新的 AUMID 中添加并保留旧应用。</span><span class="sxs-lookup"><span data-stu-id="622f6-350">When modifying a Kiosk to include the new apps, we recommend adding in the new AUMID as well as leaving the old one.</span></span> <span data-ttu-id="622f6-351">这将在用户更新操作系统时创建一个简单的转换，并且不需要接收新策略来继续如期使用展台。</span><span class="sxs-lookup"><span data-stu-id="622f6-351">This will create an easy transition when users update the OS and won't need to receive new policies to keep using the Kiosk as intended.</span></span>

| <span data-ttu-id="622f6-352">应用</span><span class="sxs-lookup"><span data-stu-id="622f6-352">App</span></span>                    | <span data-ttu-id="622f6-353">AUMID</span><span class="sxs-lookup"><span data-stu-id="622f6-353">AUMID</span></span>                                                  |
|------------------------|--------------------------------------------------------|
| <span data-ttu-id="622f6-354">旧设置应用</span><span class="sxs-lookup"><span data-stu-id="622f6-354">Old Settings App</span></span>       | <span data-ttu-id="622f6-355">HolographicSystemSettings_cw5n1h2txyewy！应用</span><span class="sxs-lookup"><span data-stu-id="622f6-355">HolographicSystemSettings_cw5n1h2txyewy!App</span></span>            |
| <span data-ttu-id="622f6-356">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="622f6-356">New Settings App</span></span>       | <span data-ttu-id="622f6-357">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！应用</span><span class="sxs-lookup"><span data-stu-id="622f6-357">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App</span></span> |
| <span data-ttu-id="622f6-358">旧 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="622f6-358">Old Microsoft Edge app</span></span> | <span data-ttu-id="622f6-359">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span><span class="sxs-lookup"><span data-stu-id="622f6-359">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span></span>    |
| <span data-ttu-id="622f6-360">新的 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="622f6-360">New Microsoft Edge app</span></span> | <span data-ttu-id="622f6-361">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE</span><span class="sxs-lookup"><span data-stu-id="622f6-361">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE</span></span>    |

### <span data-ttu-id="622f6-362">页面设置可见性的新 SettingsURIs</span><span class="sxs-lookup"><span data-stu-id="622f6-362">New SettingsURIs for Page Settings Visibility</span></span>

<span data-ttu-id="622f6-363">在 [Windows 全息版版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中，我们添加了 ["设置/PageVisibilityList"](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 策略，以限制"设置"应用中显示的页面。</span><span class="sxs-lookup"><span data-stu-id="622f6-363">In [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) we added the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="622f6-364">PageVisibilityList 是一项策略，它允许 IT 管理员阻止查看或访问“系统设置”应用中的特定页面，或者对除指定页面之外的所有页面执行此操作。</span><span class="sxs-lookup"><span data-stu-id="622f6-364">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

<span data-ttu-id="622f6-365">如果你访问 [页面设置可见性](settings-uri-list.md)，你可以找到使用此 CSP 的说明和以前版本中提供的 URI 列表。</span><span class="sxs-lookup"><span data-stu-id="622f6-365">If you visit [Page Settings Visibility](settings-uri-list.md), you can find instructions to use this CSP and the list of URIs available in previous releases.</span></span>

<span data-ttu-id="622f6-366">在 Windows 预览体验成员内部版本，我们正在扩展可用设置 URI 的列表，IT 管理员可以管理该列表。</span><span class="sxs-lookup"><span data-stu-id="622f6-366">In Windows Insider builds we are expanding upon the list of list of available Settings URIs, which IT Admins can manage.</span></span> <span data-ttu-id="622f6-367">其中一些 URI 用于新"设置"应用中的新可用区域。</span><span class="sxs-lookup"><span data-stu-id="622f6-367">Some of these URIs are for newly available areas within the new Settings app.</span></span> <span data-ttu-id="622f6-368">如果使用的是"设置/PageVisibilityList"策略，请查看以下列表并根据需要调整允许或阻止的页面。</span><span class="sxs-lookup"><span data-stu-id="622f6-368">If you are using Settings/PageVisibilityList policy, review the following list and adjust your allowed or blocked pages as needed.</span></span>

> [!NOTE]
> **<span data-ttu-id="622f6-369">已弃用：ms-settings：network-proxy</span><span class="sxs-lookup"><span data-stu-id="622f6-369">Deprecated: ms-settings:network-proxy</span></span>**
>
> <span data-ttu-id="622f6-370">在这些较新的内部版本中，一个设置页已弃用。</span><span class="sxs-lookup"><span data-stu-id="622f6-370">One settings page is deprecated in these newer builds.</span></span> <span data-ttu-id="622f6-371">旧的 **"& Internet**代理"页  >  \*\*\*\* 不再作为全局设置提供。</span><span class="sxs-lookup"><span data-stu-id="622f6-371">The old **Network & Internet** > **Proxy** page is no longer available as a global setting.</span></span> <span data-ttu-id="622f6-372">新的每连接代理设置位于**Internet**  >  **Wi-Fi**&或 Internet 以太网&  >  \*\*\*\*\*\*\*\*  >  \*\*\*\*  >  **下**。</span><span class="sxs-lookup"><span data-stu-id="622f6-372">The new per-connection proxy settings can be found under **Network & Internet** > **Wi-Fi** > **Properties** or **Network & Internet** > **Ethernet** > **Properties**.</span></span>

<br>

| <span data-ttu-id="622f6-373">设置页面</span><span class="sxs-lookup"><span data-stu-id="622f6-373">Settings page</span></span>                                        | <span data-ttu-id="622f6-374">URI</span><span class="sxs-lookup"><span data-stu-id="622f6-374">URI</span></span>                                              |
|------------------------------------------------------|--------------------------------------------------|
| <span data-ttu-id="622f6-375">应用>应用&功能</span><span class="sxs-lookup"><span data-stu-id="622f6-375">Apps > Apps & features</span></span>                               | `ms-settings:appsfeatures`                         |
| <span data-ttu-id="622f6-376">应用>应用&高级>功能</span><span class="sxs-lookup"><span data-stu-id="622f6-376">Apps > Apps & features > Advanced options</span></span>          | `ms-settings:appsfeatures-app`                     |
| <span data-ttu-id="622f6-377">离线>应用</span><span class="sxs-lookup"><span data-stu-id="622f6-377">Apps > Offline maps</span></span>                                  | `ms-settings:maps`                                 |
| <span data-ttu-id="622f6-378">应用>离线地图>下载地图</span><span class="sxs-lookup"><span data-stu-id="622f6-378">Apps > Offline maps > Download maps</span></span>                  | `ms-settings:maps-downloadmaps`                    |
| <span data-ttu-id="622f6-379">鼠标>设备</span><span class="sxs-lookup"><span data-stu-id="622f6-379">Devices > Mouse</span></span>                                      | `ms-settings:mouse`                                |
| <span data-ttu-id="622f6-380">USB >设备</span><span class="sxs-lookup"><span data-stu-id="622f6-380">Devices > USB</span></span>                                        | `ms-settings:usb`                                  |
| <span data-ttu-id="622f6-381">网络& Internet >飞行模式</span><span class="sxs-lookup"><span data-stu-id="622f6-381">Network & Internet > Airplane mode</span></span>                   | `ms-settings:network-airplanemode`                 |
| <span data-ttu-id="622f6-382">隐私>常规</span><span class="sxs-lookup"><span data-stu-id="622f6-382">Privacy > General</span></span>                                    | `ms-settings:privacy-general`                      |
| <span data-ttu-id="622f6-383">隐私>墨迹&个性化设置</span><span class="sxs-lookup"><span data-stu-id="622f6-383">Privacy > Ink & typing personalization</span></span>             | `ms-settings:privacy-speechtyping`                 |
| <span data-ttu-id="622f6-384">隐私>动作</span><span class="sxs-lookup"><span data-stu-id="622f6-384">Privacy > Motion</span></span>                                     | `ms-settings:privacy-motion`                       |
| <span data-ttu-id="622f6-385">隐私>屏幕截图边框</span><span class="sxs-lookup"><span data-stu-id="622f6-385">Privacy > Screenshot borders</span></span>                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| <span data-ttu-id="622f6-386">隐私>屏幕截图和应用</span><span class="sxs-lookup"><span data-stu-id="622f6-386">Privacy > Screenshots and apps</span></span>                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| <span data-ttu-id="622f6-387">系统>电池</span><span class="sxs-lookup"><span data-stu-id="622f6-387">System > Battery</span></span>                                     | `ms-settings:batterysaver`                         |
| <span data-ttu-id="622f6-388">系统>电池</span><span class="sxs-lookup"><span data-stu-id="622f6-388">System > Battery</span></span>                                     | `ms-settings:batterysaver-settings`                |
| <span data-ttu-id="622f6-389">系统>声音</span><span class="sxs-lookup"><span data-stu-id="622f6-389">System > Sound</span></span>                                       | `ms-settings:sound`                                |
| <span data-ttu-id="622f6-390">系统>声音>应用音量和设备首选项</span><span class="sxs-lookup"><span data-stu-id="622f6-390">System > Sound > App volume and device preferences</span></span> | `ms-settings:apps-volume`                          |
| <span data-ttu-id="622f6-391">系统>声音>管理声音设备</span><span class="sxs-lookup"><span data-stu-id="622f6-391">System > Sound > Manage sound   devices</span></span>              | `ms-settings:sound-devices`                        |
| <span data-ttu-id="622f6-392">系统>存储>配置存储感知</span><span class="sxs-lookup"><span data-stu-id="622f6-392">System > Storage > Configure Storage Sense</span></span>         | `ms-settings:storagepolicies`                      |
| <span data-ttu-id="622f6-393">Time & Language > Date & time</span><span class="sxs-lookup"><span data-stu-id="622f6-393">Time & Language > Date & time</span></span>                        | `ms-settings:dateandtime`                          |
| <span data-ttu-id="622f6-394">时间&语言>键盘</span><span class="sxs-lookup"><span data-stu-id="622f6-394">Time & Language > Keyboard</span></span>                           | `ms-settings:keyboard`                             |
| <span data-ttu-id="622f6-395">Time & Language > Language</span><span class="sxs-lookup"><span data-stu-id="622f6-395">Time & Language > Language</span></span>                           | `ms-settings:language`                             |
| <span data-ttu-id="622f6-396">Time & Language > Language</span><span class="sxs-lookup"><span data-stu-id="622f6-396">Time & Language > Language</span></span>                           | `ms-settings:regionlanguage-languageoptions`       |
| <span data-ttu-id="622f6-397">更新&安全>重置&恢复</span><span class="sxs-lookup"><span data-stu-id="622f6-397">Update & Security > Reset & recovery</span></span>               | `ms-settings:reset`                                |

#### <span data-ttu-id="622f6-398">更新的 URI</span><span class="sxs-lookup"><span data-stu-id="622f6-398">Updated URIs</span></span>

<span data-ttu-id="622f6-399">以前，以下两个 URI 不会将用户直接带至指示的页面，而只会阻止主更新页面。</span><span class="sxs-lookup"><span data-stu-id="622f6-399">Previously the following two URIs would not take a user directly to the pages indicated but only blocked the main updates page.</span></span> <span data-ttu-id="622f6-400">以下项已更新为直接显示其页面：</span><span class="sxs-lookup"><span data-stu-id="622f6-400">The following items have been updated to direct to their pages:</span></span>

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <span data-ttu-id="622f6-401">用于处理故障的展台模式行为更改</span><span class="sxs-lookup"><span data-stu-id="622f6-401">Kiosk mode behavior changes for handling of failures</span></span>

<span data-ttu-id="622f6-402">在较旧的内部版本中，如果设备具有展台配置（这是全局分配的访问权限和 AAD 组成员身份分配的访问权限的组合）。如果确定 AAD 组成员身份失败，用户将看到"开始"[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)菜单中未显示任何内容。</span><span class="sxs-lookup"><span data-stu-id="622f6-402">In older builds, if a device had a kiosk configuration, which is a combination of both global assigned access and AAD group member assigned access, if determining AAD group membership failed, the user would see “[nothing shown in start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)” menu.</span></span>

<span data-ttu-id="622f6-403">从 Windows 预览体验成员版本开始，如果 AAD 组展台模式 (出现故障) ，展台体验将回退到全局展台配置。</span><span class="sxs-lookup"><span data-stu-id="622f6-403">Starting in Windows Insider release, the kiosk experience will fallback to global kiosk configuration (if present) in case of failures during AAD group kiosk mode.</span></span>

### <span data-ttu-id="622f6-404">通过"设置"应用配置回退诊断</span><span class="sxs-lookup"><span data-stu-id="622f6-404">Configuring Fallback Diagnostics via Settings app</span></span>

<span data-ttu-id="622f6-405">现在，在"设置"应用中，用户可以配置 [回退诊断的行为](hololens-diagnostic-logs.md)。</span><span class="sxs-lookup"><span data-stu-id="622f6-405">Now in Settings App, a user can configure the behavior of [Fallback Diagnostics](hololens-diagnostic-logs.md).</span></span> <span data-ttu-id="622f6-406">在"设置"应用中，导航到 **"隐私**  ->  **疑难解答"** 页以配置此设置。</span><span class="sxs-lookup"><span data-stu-id="622f6-406">In the Settings app navigate to **Privacy** -> **Troubleshooting** page to configure this setting.</span></span>

> [!NOTE]
> <span data-ttu-id="622f6-407">如果为设备配置了 MDM 策略，用户将不能覆盖该行为。</span><span class="sxs-lookup"><span data-stu-id="622f6-407">If there is MDM policy configured for the device, user will not be able to override that behavior.</span></span>  

### <span data-ttu-id="622f6-408">与附近设备共享内容</span><span class="sxs-lookup"><span data-stu-id="622f6-408">Share things with nearby devices</span></span>

<span data-ttu-id="622f6-409">与 Windows 10 设备（包括运行 HoloLens Insider 版本 20279.1006+的其他 HoloLens 2 设备）附近共享内容。</span><span class="sxs-lookup"><span data-stu-id="622f6-409">Share things with near by Windows 10 devices, including both PCs and other HoloLens 2 devices running HoloLens Insider builds 20279.1006+.</span></span> <span data-ttu-id="622f6-410">可以在"设置**系统共享体验**"中试用，以将文件或 URL 从  ->  \*\*\*\*  ->  \*\*\*\* HoloLens 共享到电脑。</span><span class="sxs-lookup"><span data-stu-id="622f6-410">You can try it out in **Settings** -> **System** -> **Shared Experiences** to share files or URLs from a HoloLens to a PC.</span></span> <span data-ttu-id="622f6-411">有关更多详细信息，请阅读有关如何在 [Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)中与附近设备共享内容的详细信息。</span><span class="sxs-lookup"><span data-stu-id="622f6-411">For more details read more about how to [Share things with nearby devices in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).</span></span>

<span data-ttu-id="622f6-412">此功能可以通过 [Connectivity/AllowConnectedDevices 进行管理](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)。</span><span class="sxs-lookup"><span data-stu-id="622f6-412">This feature can be managed via [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).</span></span>

### <span data-ttu-id="622f6-413">新的操作系统更新疑难解答程序</span><span class="sxs-lookup"><span data-stu-id="622f6-413">New OS Update troubleshooter</span></span>

<span data-ttu-id="622f6-414">除了"设置"应用中以前的疑难解答程序之外，还添加了新的疑难解答程序，并添加了新的 OS 更新的"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="622f6-414">In addition to the previous troubleshooters within the Settings app, a new troubleshooter has been added with the addition of the new Settings app for OS Updates.</span></span> <span data-ttu-id="622f6-415">导航到 **"设置**  ->  **更新 &amp; 安全性**  ->  **疑**  ->  **难解答 Windows 更新**"，然后选择"**开始"。**</span><span class="sxs-lookup"><span data-stu-id="622f6-415">Navigate to **Settings** -> **Update &amp; Security** -> **Troubleshoot** -> **Windows Update** and select **Start**.</span></span> <span data-ttu-id="622f6-416">这允许你在通过操作系统更新重现问题时收集跟踪，以帮助更好地解决 IT 或支持问题。</span><span class="sxs-lookup"><span data-stu-id="622f6-416">This allows you to collect traces while reproducing your issue with OS Updates to assist better in troubleshooting with your IT or support.</span></span>

### <span data-ttu-id="622f6-417">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="622f6-417">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="622f6-418">[脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics) 还将包括序列号和操作系统版本的其他设备信息。</span><span class="sxs-lookup"><span data-stu-id="622f6-418">[Offline diagnostics](hololens-diagnostic-logs.md#offline-diagnostics) will also include additional device information for serial number and OS version.</span></span>






## <span data-ttu-id="622f6-419">开始接收预览体验成员版本</span><span class="sxs-lookup"><span data-stu-id="622f6-419">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="622f6-420">如果你最近尚未更新，请重启设备以更新状态并获取最新内部版本。</span><span class="sxs-lookup"><span data-stu-id="622f6-420">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="622f6-421">"重新启动设备"语音命令运行良好。</span><span class="sxs-lookup"><span data-stu-id="622f6-421">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="622f6-422">还可以选择"设置/Windows 预览体验计划"中的"重启"按钮。</span><span class="sxs-lookup"><span data-stu-id="622f6-422">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="622f6-423">我们在后端有一个你可能会遇到的 bug，这样你才能重新上路。</span><span class="sxs-lookup"><span data-stu-id="622f6-423">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="622f6-424">在 HoloLens 2 设备上 **，转到"** 设置更新&  >  \*\*\*\*  >  **安全 Windows 预览体验计划**，然后选择 **"开始使用"。**</span><span class="sxs-lookup"><span data-stu-id="622f6-424">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="622f6-425">链接你用于注册为 Windows 预览体验成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="622f6-425">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="622f6-426">Windows 预览体验成员现在将迁移到频道。</span><span class="sxs-lookup"><span data-stu-id="622f6-426">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="622f6-427">快**圈**将成为开发人员**频道**，慢圈将成为\*\*\*\*\*\*Beta**渠道，并且发布**预览圈将成为\*\*\*\*版本预览频道\*\*。</span><span class="sxs-lookup"><span data-stu-id="622f6-427">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="622f6-428">该映射如下所示：</span><span class="sxs-lookup"><span data-stu-id="622f6-428">Here is what that mapping looks like:</span></span>

![Windows 预览体验成员频道说明](images/WindowsInsiderChannels.png)

<span data-ttu-id="622f6-430">有关详细信息，请参阅 Windows 博客 [上的 Windows 预览体验成员](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 频道介绍。</span><span class="sxs-lookup"><span data-stu-id="622f6-430">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="622f6-431">然后，选择 **"Windows 的活动**开发"，选择是希望接收 **开发人员** 频道还是 **Beta 渠道** 版本，并查看计划条款。</span><span class="sxs-lookup"><span data-stu-id="622f6-431">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="622f6-432">选择 **">立即重启** 以完成。</span><span class="sxs-lookup"><span data-stu-id="622f6-432">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="622f6-433">重启设备后，转到"设置>更新& **安全>检查** 更新，获取最新内部版本。</span><span class="sxs-lookup"><span data-stu-id="622f6-433">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <span data-ttu-id="622f6-434">使用0x80070490更新错误</span><span class="sxs-lookup"><span data-stu-id="622f6-434">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="622f6-435">如果在开发人员或 Beta 渠道0x80070490更新时遇到更新错误，请尝试以下短期方法。</span><span class="sxs-lookup"><span data-stu-id="622f6-435">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="622f6-436">这包括移动预览体验成员频道、选取更新，然后将预览体验成员频道移回。</span><span class="sxs-lookup"><span data-stu-id="622f6-436">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <span data-ttu-id="622f6-437">第一阶段 - 版本预览</span><span class="sxs-lookup"><span data-stu-id="622f6-437">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="622f6-438">设置，更新&，Windows 预览体验计划，选择 **版本预览频道**。</span><span class="sxs-lookup"><span data-stu-id="622f6-438">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="622f6-439">设置， &安全， Windows 更新， **检查更新**。</span><span class="sxs-lookup"><span data-stu-id="622f6-439">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="622f6-440">更新后，继续第二阶段。</span><span class="sxs-lookup"><span data-stu-id="622f6-440">After the update, continue on to Stage two.</span></span>

#### <span data-ttu-id="622f6-441">第二阶段 - 开发人员频道</span><span class="sxs-lookup"><span data-stu-id="622f6-441">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="622f6-442">设置，更新&，Windows 预览体验计划，选择 **开发人员频道**。</span><span class="sxs-lookup"><span data-stu-id="622f6-442">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="622f6-443">设置， &安全， Windows 更新， **检查更新**。</span><span class="sxs-lookup"><span data-stu-id="622f6-443">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <span data-ttu-id="622f6-444">FFU 下载和快速方向</span><span class="sxs-lookup"><span data-stu-id="622f6-444">FFU download and flash directions</span></span>
<span data-ttu-id="622f6-445">若要使用已签名的 ffu 进行测试，首先需要先对设备进行飞行解锁，然后闪烁已签名的 Ffu。</span><span class="sxs-lookup"><span data-stu-id="622f6-445">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="622f6-446">在电脑上：</span><span class="sxs-lookup"><span data-stu-id="622f6-446">On PC:</span></span>

    1. <span data-ttu-id="622f6-447">从 下载 ffu 到电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="622f6-447">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="622f6-448">从 Microsoft store (ARC) 高级恢复配套设备： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .</span><span class="sxs-lookup"><span data-stu-id="622f6-448">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="622f6-449">On HoloLens - Flight Unlock： Open **Settings**  >  **Update & Security**Windows Insider  >  **Program** then sign up， reboot device.</span><span class="sxs-lookup"><span data-stu-id="622f6-449">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="622f6-450">Flash FFU - 现在可以使用 ARC 对已进行飞行的 FFU 进行闪烁。</span><span class="sxs-lookup"><span data-stu-id="622f6-450">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="622f6-451">提供反馈并报告问题</span><span class="sxs-lookup"><span data-stu-id="622f6-451">Provide feedback and report issues</span></span>

<span data-ttu-id="622f6-452">请使用 [HoloLens](hololens-feedback.md) 上的"反馈中心"应用提供反馈并报告问题。</span><span class="sxs-lookup"><span data-stu-id="622f6-452">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="622f6-453">使用反馈中心可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。</span><span class="sxs-lookup"><span data-stu-id="622f6-453">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="622f6-454">应该以相同方式报告有关 HoloLens 中文和日文版本的问题。</span><span class="sxs-lookup"><span data-stu-id="622f6-454">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="622f6-455">请务必接受询问您是否希望反馈中心访问"文档"文件夹的提示， (系统提示"是") 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="622f6-455">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="622f6-456">针对开发人员的注意事项</span><span class="sxs-lookup"><span data-stu-id="622f6-456">Note for developers</span></span>

<span data-ttu-id="622f6-457">欢迎和鼓励你尝试使用 HoloLens 预览体验成员版本开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="622f6-457">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="622f6-458">请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 开始。</span><span class="sxs-lookup"><span data-stu-id="622f6-458">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="622f6-459">这些相同的说明与 HoloLens 的预览体验成员版本一致。</span><span class="sxs-lookup"><span data-stu-id="622f6-459">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="622f6-460">可以使用与 HoloLens Visual Studio相同的 Unity 版本和版本。</span><span class="sxs-lookup"><span data-stu-id="622f6-460">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="622f6-461">停止接收预览体验成员版本</span><span class="sxs-lookup"><span data-stu-id="622f6-461">Stop receiving Insider builds</span></span>

<span data-ttu-id="622f6-462">如果你不再希望接收 Windows 全息版的预览体验成员版本，你可以选择在 HoloLens 运行生产版本时退出，或者可以使用高级恢复助手[](hololens-recovery.md)将设备恢复为非预览体验成员版本的 Windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="622f6-462">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="622f6-463">存在一个已知问题，即手动重新安装新的预览版后从 Insider Preview 版本取消注册的用户将遇到蓝屏。</span><span class="sxs-lookup"><span data-stu-id="622f6-463">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="622f6-464">之后，他们必须手动恢复设备。</span><span class="sxs-lookup"><span data-stu-id="622f6-464">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="622f6-465">有关是否将受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。</span><span class="sxs-lookup"><span data-stu-id="622f6-465">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="622f6-466">若要验证 HoloLens 是否正在运行生产内部版本，</span><span class="sxs-lookup"><span data-stu-id="622f6-466">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="622f6-467">转到 **">系统>设置"，** 并查找内部版本号。</span><span class="sxs-lookup"><span data-stu-id="622f6-467">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="622f6-468">[请参阅生产内部版本号发行说明](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="622f6-468">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="622f6-469">若要选择退出预览体验成员版本：</span><span class="sxs-lookup"><span data-stu-id="622f6-469">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="622f6-470">在运行生产内部测试的 HoloLens 上，转到"设置>更新& Windows 预览体验计划 **>"，** 然后选择"停止预览**体验成员版本"。**</span><span class="sxs-lookup"><span data-stu-id="622f6-470">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="622f6-471">按照说明选择退出设备。</span><span class="sxs-lookup"><span data-stu-id="622f6-471">Follow the instructions to opt out your device.</span></span>
