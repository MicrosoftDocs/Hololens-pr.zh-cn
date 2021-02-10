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
ms.openlocfilehash: 4573f3b2e88af36c397fd1735ec9c6a96b4c52d6
ms.sourcegitcommit: 76a99370ab841c06e533cc2f4a0c78c1fb7eac70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "11324795"
---
# <span data-ttu-id="0009b-103">Microsoft HoloLens 内部预览版</span><span class="sxs-lookup"><span data-stu-id="0009b-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="0009b-104">欢迎使用 HoloLens 的最新 Insider Preview 版本！</span><span class="sxs-lookup"><span data-stu-id="0009b-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="0009b-105">开始操作非常简单，并为[](hololens-insider.md#start-receiving-insider-builds)HoloLens 的下一个主要操作系统更新提供有价值的反馈。</span><span class="sxs-lookup"><span data-stu-id="0009b-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="0009b-106">Windows 预览体验成员发行说明</span><span class="sxs-lookup"><span data-stu-id="0009b-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="0009b-107">我们希望再次开始向 Windows 预览体验成员提供新功能。</span><span class="sxs-lookup"><span data-stu-id="0009b-107">We are excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="0009b-108">我们将测试到开发人员频道获取最新更新。</span><span class="sxs-lookup"><span data-stu-id="0009b-108">We will be flighting to the Dev Channel for the latest updates.</span></span> <span data-ttu-id="0009b-109">我们将继续更新此页面，因为我们向 Windows 预览体验成员版本添加更多功能和更新。</span><span class="sxs-lookup"><span data-stu-id="0009b-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span>  <span data-ttu-id="0009b-110">感到兴奋并准备好将这些更新融合到你的现实中。</span><span class="sxs-lookup"><span data-stu-id="0009b-110">Get excited and ready to mix these updates into your reality.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0009b-111">如果你之前在展台中使用的是"设置"应用或 Microsoft Edge 应用，我们将这些应用替换为使用不同的应用 ID 的新应用。</span><span class="sxs-lookup"><span data-stu-id="0009b-111">If you were previously using either the Settings app or Microsoft Edge app in a Kiosk, we have replaced these apps with new apps which use a different App ID.</span></span> <span data-ttu-id="0009b-112">我们强烈建议你在下面的展台模式下阅读新应用[的新 AUMID。](#use-the-new-settings-and-edge-apps-in-kiosk-modes)</span><span class="sxs-lookup"><span data-stu-id="0009b-112">We highly encourage you to read [New AUMIDs for new apps in Kiosk mode](#use-the-new-settings-and-edge-apps-in-kiosk-modes) below.</span></span> <span data-ttu-id="0009b-113">这将确保你继续在展台中拥有"设置"应用，或包括新的 Microsoft Edge 应用。</span><span class="sxs-lookup"><span data-stu-id="0009b-113">This will ensure you either continue to have the Settings app in your Kiosk, or include the new Microsoft Edge app.</span></span>

<br>

| <span data-ttu-id="0009b-114">功能名称</span><span class="sxs-lookup"><span data-stu-id="0009b-114">Feature Name</span></span>                                              | <span data-ttu-id="0009b-115">简短说明</span><span class="sxs-lookup"><span data-stu-id="0009b-115">Short description</span></span>                                                                      | <span data-ttu-id="0009b-116">在内部版本可用</span><span class="sxs-lookup"><span data-stu-id="0009b-116">Available in build</span></span> |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [<span data-ttu-id="0009b-117">新版 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0009b-117">New Microsoft Edge</span></span>](#introducing-the-new-microsoft-edge) | <span data-ttu-id="0009b-118">新的基于 Chromium 的 Microsoft Edge 现在可用于 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="0009b-118">The new, Chromium-based Microsoft Edge is now available for HoloLens 2</span></span>                         | <span data-ttu-id="0009b-119">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0009b-119">20279.1006</span></span> |
| [<span data-ttu-id="0009b-120">WebXR 和 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="0009b-120">WebXR and 360 Viewer</span></span>](#webxr-and-360-viewer)             | <span data-ttu-id="0009b-121">尝试沉浸式 Web 体验和 360 视频播放</span><span class="sxs-lookup"><span data-stu-id="0009b-121">Try immersive web experiences and 360 video playback</span></span>                                           | <span data-ttu-id="0009b-122">20289.1000</span><span class="sxs-lookup"><span data-stu-id="0009b-122">20289.1000</span></span> |
| [<span data-ttu-id="0009b-123">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="0009b-123">New Settings app</span></span>](#new-settings-app)                     | <span data-ttu-id="0009b-124">旧"设置"应用将替换为具有新功能和设置的更新版本</span><span class="sxs-lookup"><span data-stu-id="0009b-124">The legacy Settings app is being replaced by an updated version with new features and settings</span></span> | <span data-ttu-id="0009b-125">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0009b-125">20279.1006</span></span> |
| [<span data-ttu-id="0009b-126">默认应用选取器</span><span class="sxs-lookup"><span data-stu-id="0009b-126">Default app picker</span></span>](#default-app-picker)                 | <span data-ttu-id="0009b-127">选择应针对每个文件或链接类型启动的应用</span><span class="sxs-lookup"><span data-stu-id="0009b-127">Choose which app should launch for each file or link type</span></span>                                      | <span data-ttu-id="0009b-128">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0009b-128">20279.1006</span></span> |
| [<span data-ttu-id="0009b-129">Office Web 应用</span><span class="sxs-lookup"><span data-stu-id="0009b-129">Office web app</span></span>](#office-web-app)                         | <span data-ttu-id="0009b-130">Office Web 应用的快捷方式现在列在"所有应用"中</span><span class="sxs-lookup"><span data-stu-id="0009b-130">A shortcut to the Office web app is now listed in "All apps"</span></span>                                   | <span data-ttu-id="0009b-131">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0009b-131">20279.1006</span></span> |
| [<span data-ttu-id="0009b-132">轻扫以键入</span><span class="sxs-lookup"><span data-stu-id="0009b-132">Swipe to type</span></span>](#swipe-to-type)                           | <span data-ttu-id="0009b-133">使用手指尖在全息键盘上"轻扫"字词</span><span class="sxs-lookup"><span data-stu-id="0009b-133">Use the tip of your finger to "swipe" words on the holographic keyboard</span></span>                        | <span data-ttu-id="0009b-134">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0009b-134">20279.1006</span></span> |
| [<span data-ttu-id="0009b-135">USB-C 外部麦克风支持</span><span class="sxs-lookup"><span data-stu-id="0009b-135">USB-C External Microphone Support</span></span>](#usb-c-external-microphone-support) | <span data-ttu-id="0009b-136">将 USB-C 麦克风用于应用和/或远程协助。</span><span class="sxs-lookup"><span data-stu-id="0009b-136">Use USB-C microphones for apps and / or Remote Assist.</span></span>| <span data-ttu-id="0009b-137">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0009b-137">20279.1006</span></span> |
| [<span data-ttu-id="0009b-138">展台模式下新应用的新 AUMID</span><span class="sxs-lookup"><span data-stu-id="0009b-138">New AUMIDs for new apps in Kiosk mode</span></span>](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | <span data-ttu-id="0009b-139">新设置和边缘应用的 AUMID</span><span class="sxs-lookup"><span data-stu-id="0009b-139">AUMIDs for new Settings and Edge apps</span></span> | <span data-ttu-id="0009b-140">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0009b-140">20279.1006</span></span> |
| [<span data-ttu-id="0009b-141">改进的展台模式故障帮助</span><span class="sxs-lookup"><span data-stu-id="0009b-141">Improved Kiosk mode failure handing</span></span>](#kiosk-mode-behavior-changes-for-handling-of-failures) | <span data-ttu-id="0009b-142">展台模式在空的"开始"菜单之前查找全局分配的访问权限。</span><span class="sxs-lookup"><span data-stu-id="0009b-142">Kiosk mode looks for Global Assigned Access before empty start menu.</span></span> | <span data-ttu-id="0009b-143">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0009b-143">20279.1006</span></span> |
| [<span data-ttu-id="0009b-144">配置回退诊断</span><span class="sxs-lookup"><span data-stu-id="0009b-144">Configure Fallback Diagnostics</span></span>](#configuring-fallback-diagnostics-via-settings-app) | <span data-ttu-id="0009b-145">在"设置"应用中设置回退诊断行为</span><span class="sxs-lookup"><span data-stu-id="0009b-145">Setting Fallback Diagnostic Behavior in Settings App</span></span> | <span data-ttu-id="0009b-146">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0009b-146">20279.1006</span></span> |
| [<span data-ttu-id="0009b-147">与附近设备共享内容</span><span class="sxs-lookup"><span data-stu-id="0009b-147">Share things with nearby devices</span></span>](#share-things-with-nearby-devices) | <span data-ttu-id="0009b-148">将 HoloLens 中的文件或 URL 共享到电脑</span><span class="sxs-lookup"><span data-stu-id="0009b-148">Share files or URLs from a HoloLens to a PC</span></span> | <span data-ttu-id="0009b-149">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0009b-149">20279.1006</span></span> |
| [<span data-ttu-id="0009b-150">新的操作系统更新疑难解答程序</span><span class="sxs-lookup"><span data-stu-id="0009b-150">New OS Update troubleshooter</span></span>](#new-os-update-troubleshooter) | <span data-ttu-id="0009b-151">操作系统更新的设置中的新疑难解答</span><span class="sxs-lookup"><span data-stu-id="0009b-151">New troubleshooter in Settings for OS updates</span></span> | <span data-ttu-id="0009b-152">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0009b-152">20279.1006</span></span> |
| [<span data-ttu-id="0009b-153">更新中的改进和修复</span><span class="sxs-lookup"><span data-stu-id="0009b-153">Improvements and fixes in the update</span></span>](#improvements-and-fixes-in-the-update) | <span data-ttu-id="0009b-154">更新中的其他修补程序。</span><span class="sxs-lookup"><span data-stu-id="0009b-154">Additional fixes in the update.</span></span> | <span data-ttu-id="0009b-155">20279.1006</span><span class="sxs-lookup"><span data-stu-id="0009b-155">20279.1006</span></span> |

### <span data-ttu-id="0009b-156">引入新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0009b-156">Introducing the new Microsoft Edge</span></span>

![旧 Microsoft Edge 徽标到新 Microsoft Edge 徽标的动画](images/new-edge.gif)

<span data-ttu-id="0009b-158">新的 Microsoft Edge [采用 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 开放源代码项目，为客户创建更好的兼容性，减少 Web 开发人员的 Web 碎片。</span><span class="sxs-lookup"><span data-stu-id="0009b-158">The new Microsoft Edge [adopts the Chromium open source project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) to create better compatibility for customers and less fragmentation of the web for web developers.</span></span>

<span data-ttu-id="0009b-159">通过此预览体验成员预览版，HoloLens 2 客户首次可以使用新的 Microsoft Edge！</span><span class="sxs-lookup"><span data-stu-id="0009b-159">With this Insider preview, the new Microsoft Edge is available to HoloLens 2 customers for the first time!</span></span> <span data-ttu-id="0009b-160">虽然新 Microsoft Edge 最终将替换 HoloLens 2 上的旧版 Microsoft Edge，但预览体验成员目前可以使用这两种浏览器。</span><span class="sxs-lookup"><span data-stu-id="0009b-160">While the new Microsoft Edge will eventually replace legacy Microsoft Edge on HoloLens 2, both browsers are currently available to Insiders.</span></span> <span data-ttu-id="0009b-161">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="0009b-161">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span></span>

![新 Microsoft Edge 屏幕截图](images/new-edge-ui.png)

#### <span data-ttu-id="0009b-163">启动新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0009b-163">Launching the new Microsoft Edge</span></span>

<span data-ttu-id="0009b-164">预览体验成员可以使用两个版本的 Microsoft Edge：新的 Microsoft Edge 新 Microsoft Edge 图标 (由蓝绿色旋转图标) 表示，旧 Microsoft Edge (由白色 ![ ](images/new_edge_logo.png) "e"图标) 表示。</span><span class="sxs-lookup"><span data-stu-id="0009b-164">There are two versions of Microsoft Edge available to Insiders: the new Microsoft Edge ![new Microsoft Edge icon](images/new_edge_logo.png) (represented by a blue and green swirl icon) and legacy Microsoft Edge (represented by the white "e" icon).</span></span> <span data-ttu-id="0009b-165">新的 Microsoft Edge 固定到"开始"菜单，将在激活 Web 链接时自动启动。</span><span class="sxs-lookup"><span data-stu-id="0009b-165">The new Microsoft Edge is pinned to the Start menu and will automatically launch when you activate a web link.</span></span> <span data-ttu-id="0009b-166">如果你想要还原为使用旧版 Microsoft Edge 作为默认 Web 浏览器，请参阅下面的说明 [重置默认应用](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="0009b-166">If you would like to revert to using legacy Microsoft Edge as your default web browser, see the instructions below for [resetting default apps](#default-app-picker).</span></span>

> [!NOTE]
> <span data-ttu-id="0009b-167">当你首次在 HoloLens 2 上启动新的 Microsoft Edge 时，你的设置和数据将导入旧版 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="0009b-167">When you first launch the new Microsoft Edge on HoloLens 2, your settings and data will be imported from legacy Microsoft Edge.</span></span> <span data-ttu-id="0009b-168">如果在启动新的 Microsoft Edge 后继续使用旧版 Microsoft Edge，则新数据将不会从旧版 Microsoft Edge 同步到新的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="0009b-168">If you continue to use legacy Microsoft Edge after launching the new Microsoft Edge, that new data will not be synced from legacy Microsoft Edge to the new Microsoft Edge.</span></span>

#### <span data-ttu-id="0009b-169">配置新 Microsoft Edge 的策略设置</span><span class="sxs-lookup"><span data-stu-id="0009b-169">Configuring policy settings for the new Microsoft Edge</span></span>

<span data-ttu-id="0009b-170">新的 Microsoft Edge 为 IT 管理员提供 HoloLens 2 上的一组比以前适用于旧版 Microsoft Edge 的更为广泛的浏览器策略。</span><span class="sxs-lookup"><span data-stu-id="0009b-170">The new Microsoft Edge offers IT admins a much broader set of browser policies on HoloLens 2 than were previously available with legacy Microsoft Edge.</span></span>

<span data-ttu-id="0009b-171">下面是一些有用的资源，有助于详细了解如何管理新 Microsoft Edge 的策略设置：</span><span class="sxs-lookup"><span data-stu-id="0009b-171">Here are some helpful resources for learning more about managing policy settings for the new Microsoft Edge:</span></span>

- [<span data-ttu-id="0009b-172">使用 Microsoft Intune 配置 Microsoft Edge 策略设置</span><span class="sxs-lookup"><span data-stu-id="0009b-172">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [<span data-ttu-id="0009b-173">Microsoft Edge 旧版到 Microsoft Edge 策略映射</span><span class="sxs-lookup"><span data-stu-id="0009b-173">Microsoft Edge Legacy to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [<span data-ttu-id="0009b-174">Google Chrome 到 Microsoft Edge 策略映射</span><span class="sxs-lookup"><span data-stu-id="0009b-174">Google Chrome to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- <span data-ttu-id="0009b-175">[完整的 Microsoft Edge 企业版文档](https://docs.microsoft.com/deployedge/)</span><span class="sxs-lookup"><span data-stu-id="0009b-175">Full [Microsoft Edge Enterprise documentation](https://docs.microsoft.com/deployedge/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0009b-176">由于新的 Microsoft Edge 支持大量浏览器策略，团队无法保证每个新策略都适用于 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="0009b-176">Because of the volume of browser policies supported by the new Microsoft Edge, our team is unable to guarantee that each new policy works on HoloLens 2.</span></span> <span data-ttu-id="0009b-177">但是，我们已经测试并确认 HoloLens 2 上以前支持的每个旧 Microsoft Edge 策略的新 Microsoft Edge 等效项可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="0009b-177">However, we've tested and confirmed that the new Microsoft Edge equivalent of each legacy Microsoft Edge policy previously supported on HoloLens 2 work as expected.</span></span> <span data-ttu-id="0009b-178">请参阅 [Microsoft Edge 旧版到 Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 策略映射，查找与 HoloLens 2 一起使用的每个旧版 Microsoft Edge 浏览器策略的新 Microsoft Edge 等效项。</span><span class="sxs-lookup"><span data-stu-id="0009b-178">See [Microsoft Edge Legacy to Microsoft Edge policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) to find the new Microsoft Edge equivalent of each legacy Microsoft Edge browser policy you were using with HoloLens 2.</span></span>
>
> <span data-ttu-id="0009b-179">我们了解至少有两个新的 Microsoft Edge 策略 *将不能* 与 HoloLens 2 一起使用：</span><span class="sxs-lookup"><span data-stu-id="0009b-179">There are at least two new Microsoft Edge policies that we know *will not* work with HoloLens 2:</span></span>
> - <span data-ttu-id="0009b-180">EnterpriseModeSiteList</span><span class="sxs-lookup"><span data-stu-id="0009b-180">EnterpriseModeSiteList</span></span>
> - <span data-ttu-id="0009b-181">EnterpriseSiteListServiceURL</span><span class="sxs-lookup"><span data-stu-id="0009b-181">EnterpriseSiteListServiceURL</span></span>

#### <span data-ttu-id="0009b-182">HoloLens 2 上新 Microsoft Edge 的预计功能</span><span class="sxs-lookup"><span data-stu-id="0009b-182">What to expect from the new Microsoft Edge on HoloLens 2</span></span>

<span data-ttu-id="0009b-183">由于新的 Microsoft Edge 是具有新的 UWP 适配器层的本机 Win32 应用，允许它在仅 UWP 设备（如 HoloLens 2）上运行，因此某些功能可能不会立即可用。</span><span class="sxs-lookup"><span data-stu-id="0009b-183">Because the new Microsoft Edge is a native Win32 app with a new UWP adapter layer allowing it to run on UWP-only devices like HoloLens 2, some features may not be immediately available.</span></span> <span data-ttu-id="0009b-184">我们将支持未来几个月的新方案和功能，因此请查看此空间了解最新信息。</span><span class="sxs-lookup"><span data-stu-id="0009b-184">We'll be supporting new scenarios and features over the coming months, so please check this space for up-to-date information.</span></span>

**<span data-ttu-id="0009b-185">应用场景和功能应能正常工作：</span><span class="sxs-lookup"><span data-stu-id="0009b-185">Scenarios and features expected to work:</span></span>**
- <span data-ttu-id="0009b-186">首次运行体验、登录配置文件和同步</span><span class="sxs-lookup"><span data-stu-id="0009b-186">First-run experience, sign-in to profile, and sync</span></span>
- <span data-ttu-id="0009b-187">网站应按预期呈现和行为</span><span class="sxs-lookup"><span data-stu-id="0009b-187">Websites should render and behave as expected</span></span>
- <span data-ttu-id="0009b-188">大多数浏览器功能 (收藏夹、历史记录等) 应正常工作</span><span class="sxs-lookup"><span data-stu-id="0009b-188">Most browser functionality (Favorites, History, etc.) should work as expected</span></span>
- <span data-ttu-id="0009b-189">深色模式</span><span class="sxs-lookup"><span data-stu-id="0009b-189">Dark mode</span></span>
- <span data-ttu-id="0009b-190">将 Web 应用安装到设备</span><span class="sxs-lookup"><span data-stu-id="0009b-190">Installing web apps to the device</span></span>
- <span data-ttu-id="0009b-191">安装扩展 (请告知我们，如果你使用的任何扩展在 HoloLens 2) </span><span class="sxs-lookup"><span data-stu-id="0009b-191">Installing extensions (please let us know if you use any extensions that don't work properly on HoloLens 2)</span></span>
- <span data-ttu-id="0009b-192">查看和标记 PDF</span><span class="sxs-lookup"><span data-stu-id="0009b-192">Viewing and marking up a PDF</span></span>
- <span data-ttu-id="0009b-193">单个浏览器窗口中的空间声音</span><span class="sxs-lookup"><span data-stu-id="0009b-193">Spatial sound from a single browser window</span></span>
- <span data-ttu-id="0009b-194">浏览器的自动和手动更新</span><span class="sxs-lookup"><span data-stu-id="0009b-194">Automatic and manual updating of the browser</span></span>
- <span data-ttu-id="0009b-195">使用"保存到 PDF"选项 (打印菜单中保存 PDF) </span><span class="sxs-lookup"><span data-stu-id="0009b-195">Saving a PDF from the Print menu (using "Save to PDF" option)</span></span>

**<span data-ttu-id="0009b-196">即将推出方案和功能：</span><span class="sxs-lookup"><span data-stu-id="0009b-196">Scenarios and features coming soon:</span></span>**
- <span data-ttu-id="0009b-197">WebXR 和 360 Viewer 扩展</span><span class="sxs-lookup"><span data-stu-id="0009b-197">WebXR and 360 Viewer extension</span></span>
- <span data-ttu-id="0009b-198">在环境中跨多个窗口浏览时，内容还原以更正窗口</span><span class="sxs-lookup"><span data-stu-id="0009b-198">Content restoration to correct window when browsing across multiple windows placed in your environment</span></span>

**<span data-ttu-id="0009b-199">无法工作的方案和功能：</span><span class="sxs-lookup"><span data-stu-id="0009b-199">Scenarios and features not expected to work:</span></span>**
- <span data-ttu-id="0009b-200">具有同时音频流的多个窗口的空间声音</span><span class="sxs-lookup"><span data-stu-id="0009b-200">Spatial sound from multiple windows with simultaneous audio streams</span></span>
- <span data-ttu-id="0009b-201">"查看它，说出它"</span><span class="sxs-lookup"><span data-stu-id="0009b-201">"See it, say it"</span></span>
- <span data-ttu-id="0009b-202">打印</span><span class="sxs-lookup"><span data-stu-id="0009b-202">Printing</span></span>

**<span data-ttu-id="0009b-203">热门浏览器问题：</span><span class="sxs-lookup"><span data-stu-id="0009b-203">Top known browser issues:</span></span>**
- <span data-ttu-id="0009b-204">重置设备将删除新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0009b-204">Resetting your device will remove the new Microsoft Edge</span></span>
- <span data-ttu-id="0009b-205">全息键盘中的放大镜预览显示不正确的内容</span><span class="sxs-lookup"><span data-stu-id="0009b-205">The magnifier preview in the holographic keyboard shows incorrect content</span></span>

#### <span data-ttu-id="0009b-206">Microsoft Edge 预览体验成员频道</span><span class="sxs-lookup"><span data-stu-id="0009b-206">Microsoft Edge Insider channels</span></span>

<span data-ttu-id="0009b-207">Microsoft Edge 团队向 Edge 预览体验成员社区提供三个预览频道：Beta、Dev 和 Canary。</span><span class="sxs-lookup"><span data-stu-id="0009b-207">The Microsoft Edge team makes three preview channels available to the Edge Insider community: Beta, Dev, and Canary.</span></span> <span data-ttu-id="0009b-208">安装预览频道不会卸载 HoloLens 2 上发布的 Microsoft Edge 版本，并且可以同时安装多个。</span><span class="sxs-lookup"><span data-stu-id="0009b-208">Installing a preview channel doesn't uninstall the released version of Microsoft Edge on your HoloLens 2, and you can install more than one at the same time.</span></span> 

<span data-ttu-id="0009b-209">访问 [Microsoft Edge 预览体验成员主页](https://www.microsoftedgeinsider.com) ，详细了解 Edge 预览体验成员社区。</span><span class="sxs-lookup"><span data-stu-id="0009b-209">Visit the [Microsoft Edge Insider homepage](https://www.microsoftedgeinsider.com) to learn more about the Edge Insider community.</span></span> <span data-ttu-id="0009b-210">若要了解有关不同边缘预览体验成员频道和入门信息，请访问 Edge [预览体验成员下载页面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="0009b-210">To learn more about the different Edge Insider channels and get started, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>

<span data-ttu-id="0009b-211">有两种方法可用于将 Microsoft Edge 预览体验成员频道安装到 HoloLens 2：</span><span class="sxs-lookup"><span data-stu-id="0009b-211">There are a couple methods available for installing Microsoft Edge Insider channels to HoloLens 2:</span></span>

**<span data-ttu-id="0009b-212">直接安装在设备上 (当前仅适用于非托管设备) </span><span class="sxs-lookup"><span data-stu-id="0009b-212">Direct install on device (currently only available to unmanaged devices)</span></span>**
  1. <span data-ttu-id="0009b-213">在 HoloLens 2 上，访问 [Edge 预览体验成员下载页面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="0009b-213">On your HoloLens 2, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>
  1. <span data-ttu-id="0009b-214">选择要安装的边缘预览体验成员频道的"下载 **HoloLens 2"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="0009b-214">Select the **Download for HoloLens 2** button for the Edge Insider channel you wish to install.</span></span>
  1. <span data-ttu-id="0009b-215">使用"文件资源管理器" (从边缘下载队列或设备的"下载"文件夹中启动下载的 .msix) 。</span><span class="sxs-lookup"><span data-stu-id="0009b-215">Launch the downloaded .msix file from the Edge download queue or from your device's "Downloads" folder (using File Explorer).</span></span>
  1. <span data-ttu-id="0009b-216">[应用安装程序](app-deploy-app-installer.md) 将启动。</span><span class="sxs-lookup"><span data-stu-id="0009b-216">[App installer](app-deploy-app-installer.md) will launch.</span></span>
  1. <span data-ttu-id="0009b-217">选择 **"安装"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="0009b-217">Select the **Install** button.</span></span>
  1. <span data-ttu-id="0009b-218">成功安装后，你将在"开始"菜单的"所有应用"列表中发现 Microsoft Edge \*\*\*\* Beta、Dev 或 Canary 作为单独的条目。</span><span class="sxs-lookup"><span data-stu-id="0009b-218">After successful install, you will find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu.</span></span>

**<span data-ttu-id="0009b-219">通过具有 Windows Device Portal [ (电脑进行](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) 安装需要在 HoloLens 2 设备上启用开发人员) </span><span class="sxs-lookup"><span data-stu-id="0009b-219">Install via PC with Windows Device Portal (requires [developer mode](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) to be enabled on HoloLens 2)</span></span>**
  1. <span data-ttu-id="0009b-220">在电脑上，访问 [Edge 预览体验成员下载页面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="0009b-220">On your PC, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>
  1. <span data-ttu-id="0009b-221">选择要 **安装** 的边缘预览体验成员频道的"下载适用于 Windows 10"按钮旁边的下拉箭头按钮。</span><span class="sxs-lookup"><span data-stu-id="0009b-221">Select the **drop-down arrow button** next to the "Download for Windows 10" button for the Edge Insider channel you wish to install.</span></span>
  1. <span data-ttu-id="0009b-222">在**下拉菜单中选择 HoloLens 2。**</span><span class="sxs-lookup"><span data-stu-id="0009b-222">Select **HoloLens 2** in the drop-down menu.</span></span>
  1. <span data-ttu-id="0009b-223">将 .msix 文件保存到电脑文件夹的"下载 (或其他文件夹，你可以轻松找到) 。</span><span class="sxs-lookup"><span data-stu-id="0009b-223">Save the .msix file to the "Downloads" folder of your PC (or another folder you can easily find).</span></span>
  1. <span data-ttu-id="0009b-224">使用 [电脑上的 Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 在 HoloLens 2 上安装下载的 .msix 文件。</span><span class="sxs-lookup"><span data-stu-id="0009b-224">Use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) on your PC to install the downloaded .msix file on HoloLens 2.</span></span>
  1. <span data-ttu-id="0009b-225">成功安装后，你将在"开始"菜单的"所有应用"列表中发现 Microsoft Edge \*\*\*\* Beta、Dev 或 Canary 作为单独的条目。</span><span class="sxs-lookup"><span data-stu-id="0009b-225">After successful install, you will find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu.</span></span>

> [!NOTE]
> <span data-ttu-id="0009b-226">在此适用于 HoloLens 2 的 Windows 预览体验成员预览体验期间，你设备上 Microsoft Edge 的版本可能高于某些 (或 Microsoft Edge 预览体验成员) 中提供的版本。</span><span class="sxs-lookup"><span data-stu-id="0009b-226">During this Windows Insider preview for HoloLens 2, the version of Microsoft Edge on your device may be higher than those available in some (or all) of the Microsoft Edge Insider channels.</span></span> <span data-ttu-id="0009b-227">这是为了确保专门针对 HoloLens 2 上的 Web 浏览器的新功能和修补程序尽快进入我们的 Windows 预览体验成员。</span><span class="sxs-lookup"><span data-stu-id="0009b-227">This is to ensure new features and fixes specifically targeting the web browser on HoloLens 2 are getting to our Windows Insiders as quickly as possible.</span></span> <span data-ttu-id="0009b-228">在公开发布下一个 Windows 更新后，Microsoft Edge 预览体验成员频道版本将超过 HoloLens 2 上的 Microsoft Edge 版本，并保持领先。</span><span class="sxs-lookup"><span data-stu-id="0009b-228">Shortly after the public release of the next Windows update, the Microsoft Edge Insider channel builds will surpass, and stay ahead of, the version of Microsoft Edge on your HoloLens 2.</span></span>

### <span data-ttu-id="0009b-229">WebXR 和 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="0009b-229">WebXR and 360 Viewer</span></span>

*<span data-ttu-id="0009b-230">在 Windows 预览体验成员版本 20289.1000 中添加</span><span class="sxs-lookup"><span data-stu-id="0009b-230">Added in Windows Insider build 20289.1000</span></span>*

<span data-ttu-id="0009b-231">新的 Microsoft Edge 包括对 WebXR 的支持，WebXR 是创建沉浸式 Web 体验的新标准， (WebVR) 。</span><span class="sxs-lookup"><span data-stu-id="0009b-231">The new Microsoft Edge includes support for WebXR, which is the new standard for creating immersive web experiences (replacing WebVR).</span></span> <span data-ttu-id="0009b-232">许多沉浸式 Web 体验在设计时都考虑到了 (将你的视野替换为虚拟环境) ，但 HoloLens 2 也支持这些体验。</span><span class="sxs-lookup"><span data-stu-id="0009b-232">Many immersive web experiences were designed with VR in mind (they replace your field of view with a virtual environment), but these experiences are also supported by HoloLens 2.</span></span> <span data-ttu-id="0009b-233">WebXR 标准还支持利用物理环境的增强和混合现实沉浸式 Web 体验。</span><span class="sxs-lookup"><span data-stu-id="0009b-233">The WebXR standard also enables augmented and mixed reality immersive web experiences that leverage your physical environment.</span></span> <span data-ttu-id="0009b-234">随着开发人员在 WebXR 上花费更多时间，我们预计新的增强和混合现实沉浸式体验将到达，供 HoloLens 2 客户试用！</span><span class="sxs-lookup"><span data-stu-id="0009b-234">As developers spend more time with WebXR, we anticipate new augmented and mixed reality immersive experiences will arrive for HoloLens 2 customers to try!</span></span>

<span data-ttu-id="0009b-235">360 Viewer 扩展基于 WebXR 构建，并自动随 HoloLens 2 上的新 Microsoft Edge 一起安装。</span><span class="sxs-lookup"><span data-stu-id="0009b-235">The 360 Viewer extension is built on WebXR and automatically installs alongside the new Microsoft Edge on HoloLens 2.</span></span> <span data-ttu-id="0009b-236">此 Web 扩展让你能够沉浸于 360 度视频中。</span><span class="sxs-lookup"><span data-stu-id="0009b-236">This web extension gives you the ability to immerse yourself in 360-degree videos.</span></span> <span data-ttu-id="0009b-237">YouTube 提供最多 360 个视频选择，因此我们鼓励您从该视频开始。</span><span class="sxs-lookup"><span data-stu-id="0009b-237">YouTube offers the largest selection of 360 videos, so we encourage you to start there.</span></span>

#### <span data-ttu-id="0009b-238">如何使用 WebXR</span><span class="sxs-lookup"><span data-stu-id="0009b-238">How to use WebXR</span></span>

1. <span data-ttu-id="0009b-239">导航到支持 WebXR 的网站。</span><span class="sxs-lookup"><span data-stu-id="0009b-239">Navigate to a website with WebXR support.</span></span>
1. <span data-ttu-id="0009b-240">选择网站上 **"输入VR"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="0009b-240">Select the **Enter VR** button on the website.</span></span> <span data-ttu-id="0009b-241">此按钮的位置和视觉表示形式可能因网站而异，但它可能类似于：</span><span class="sxs-lookup"><span data-stu-id="0009b-241">The location and visual representation of this button may vary per website, but it may look similar to:</span></span>

    ![输入"VR"按钮示例](images/75px-enter-vr.png)

1. <span data-ttu-id="0009b-243">首次尝试启动特定域上的 WebXR 体验时，浏览器会请求同意输入沉浸式视图，选择"**允许"。**</span><span class="sxs-lookup"><span data-stu-id="0009b-243">The first time you try to launch a WebXR experience on a specific domain, the browser will ask for consent to enter an immersive view, select **Allow**.</span></span>
1. <span data-ttu-id="0009b-244">使用 [HoloLens 2 手势](hololens2-basic-usage.md#the-hand-tracking-frame) 操作体验。</span><span class="sxs-lookup"><span data-stu-id="0009b-244">Use [HoloLens 2 gestures](hololens2-basic-usage.md#the-hand-tracking-frame) to manipulate the experience.</span></span>
1. <span data-ttu-id="0009b-245">如果体验没有**退出按钮，** 请使用"开始"手势返回主页[](hololens2-basic-usage.md#start-gesture)。</span><span class="sxs-lookup"><span data-stu-id="0009b-245">If the experience doesn't have an **Exit** button, use the [Start gesture](hololens2-basic-usage.md#start-gesture) to return home.</span></span>

**<span data-ttu-id="0009b-246">建议的 WebXR 示例</span><span class="sxs-lookup"><span data-stu-id="0009b-246">Recommended WebXR samples</span></span>**
- <span data-ttu-id="0009b-247">360 Viewer (请参阅下一节) </span><span class="sxs-lookup"><span data-stu-id="0009b-247">360 Viewer (see next section)</span></span>
- [<span data-ttu-id="0009b-248">XR 恐龙</span><span class="sxs-lookup"><span data-stu-id="0009b-248">XR Dinosaurs</span></span>](https://www.xrdinosaurs.com/)
- [<span data-ttu-id="0009b-249">Barista Express</span><span class="sxs-lookup"><span data-stu-id="0009b-249">Barista Express</span></span>](https://constructarca.de/game/barista-express/)
- [<span data-ttu-id="0009b-250">WebXR 绘制</span><span class="sxs-lookup"><span data-stu-id="0009b-250">WebXR Paint</span></span>](https://threejs.org/examples/webxr_vr_paint.html)

#### <span data-ttu-id="0009b-251">如何使用 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="0009b-251">How to use 360 Viewer</span></span>

1. <span data-ttu-id="0009b-252">导航到 YouTube 上的 360 度视频。</span><span class="sxs-lookup"><span data-stu-id="0009b-252">Navigate to a 360-degree video on YouTube.</span></span>
1. <span data-ttu-id="0009b-253">在视频帧中，选择混合现实耳机按钮：</span><span class="sxs-lookup"><span data-stu-id="0009b-253">In the video frame, select the mixed reality headset button:</span></span>

    ![用于激活 360 查看器的按钮](images/enter-360-viewer.jpg)

1. <span data-ttu-id="0009b-255">首次尝试启动特定域上的 360 查看器时，浏览器将请求同意进入沉浸式视图。</span><span class="sxs-lookup"><span data-stu-id="0009b-255">The first time you try to launch 360 Viewer on a specific domain, the browser will ask for consent to enter an immersive view.</span></span> <span data-ttu-id="0009b-256">选择 **"允许"。**</span><span class="sxs-lookup"><span data-stu-id="0009b-256">Select **Allow**.</span></span>
1. <span data-ttu-id="0009b-257">[通过空](hololens2-basic-usage.md#select-using-air-tap) 点击来显示播放控件。</span><span class="sxs-lookup"><span data-stu-id="0009b-257">[Air tap](hololens2-basic-usage.md#select-using-air-tap) to bring up the playback controls.</span></span> <span data-ttu-id="0009b-258">使用 [手部光线和空](hololens2-basic-usage.md#select-using-air-tap) 点击播放/暂停、跳过前进/后退、打开/关闭标题或停止体验 (退出沉浸式视图) 。</span><span class="sxs-lookup"><span data-stu-id="0009b-258">Use [hand rays and air tap](hololens2-basic-usage.md#select-using-air-tap) to play/pause, skip forward/back, turn captions on/off, or stop the experience (which exits the immersive view).</span></span> <span data-ttu-id="0009b-259">几秒钟不活动后，播放控件将消失。</span><span class="sxs-lookup"><span data-stu-id="0009b-259">The playback controls will disappear after a few seconds of inactivity.</span></span>

#### <span data-ttu-id="0009b-260">热门 WebXR 和 360 Viewer 已知问题</span><span class="sxs-lookup"><span data-stu-id="0009b-260">Top WebXR and 360 Viewer known issues</span></span>
- <span data-ttu-id="0009b-261">在 WebXR 体验中，当你倾斜头部或四处移动环境时，全息影像可能会移动或倾斜。</span><span class="sxs-lookup"><span data-stu-id="0009b-261">In WebXR experiences, holograms may shift or tilt when you tilt your head or move around your environment.</span></span>
- <span data-ttu-id="0009b-262">根据 WebXR 体验的复杂性，帧速率可能会下降或不一样。</span><span class="sxs-lookup"><span data-stu-id="0009b-262">Depending on the complexity of the WebXR experience, the framerate may drop or stutter.</span></span>
- <span data-ttu-id="0009b-263">WebXR 中尚不提供手部接点。</span><span class="sxs-lookup"><span data-stu-id="0009b-263">Articulated hand joints are not yet available in WebXR.</span></span>
- <span data-ttu-id="0009b-264">退出 WebXR 或 360 查看器体验时，混合现实主页中的全息影像可能需要 30 秒或更多时间重新出现。</span><span class="sxs-lookup"><span data-stu-id="0009b-264">When exiting a WebXR or 360 Viewer experience, it may take 30 seconds or more for holograms in the mixed reality home to reappear.</span></span>
- <span data-ttu-id="0009b-265">YouTube 外的其他网站的 360 个视频可能无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="0009b-265">360 videos from websites other than YouTube may not work as expected.</span></span>
- <span data-ttu-id="0009b-266">如果 360 个视频未进入沉浸式 (或混合现实耳机按钮未) ，请尝试刷新页面。</span><span class="sxs-lookup"><span data-stu-id="0009b-266">If 360 videos don't enter immersive view (or the mixed reality headset button doesn't appear), try refreshing the page.</span></span>
- <span data-ttu-id="0009b-267">标题在 HoloLens 2 上的 360 查看器中尚不可见。</span><span class="sxs-lookup"><span data-stu-id="0009b-267">Captions are not yet visible in 360 Viewer on HoloLens 2.</span></span>
- <span data-ttu-id="0009b-268">在 360 查看器中暂停视频会阻止视频 (但选择播放按钮会正确恢复播放) 。</span><span class="sxs-lookup"><span data-stu-id="0009b-268">Pausing a video in 360 Viewer stops the video from rendering (but selecting the play button correctly resumes playback).</span></span>
- <span data-ttu-id="0009b-269">360 Viewer 中的"下一个视频"按钮当前不起作用。</span><span class="sxs-lookup"><span data-stu-id="0009b-269">The "next video" button in 360 Viewer does not currently work.</span></span>
- <span data-ttu-id="0009b-270">可以在沉浸式"电影"模式下播放 2D 视频，但帧速率将小于 30 fps。</span><span class="sxs-lookup"><span data-stu-id="0009b-270">You can play 2D videos in an immersive "theater" mode, but the framerate will be less than 30 fps.</span></span>

#### <span data-ttu-id="0009b-271">提供有关 WebXR 和 360 查看器的反馈</span><span class="sxs-lookup"><span data-stu-id="0009b-271">Providing feedback on WebXR and 360 Viewer</span></span>

<span data-ttu-id="0009b-272">请通过新 Microsoft Edge 中的"发送反馈"功能 **与** 团队共享反馈和 Bug。</span><span class="sxs-lookup"><span data-stu-id="0009b-272">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge.</span></span>

### <span data-ttu-id="0009b-273">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="0009b-273">New Settings app</span></span>

<span data-ttu-id="0009b-274">在此版本中，我们将引入新版本的"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="0009b-274">With this release, we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="0009b-275">新的"设置"应用在以下方面包括 HoloLens 2 的新功能和扩展设置：声音、Power & 睡眠、网络 & Internet、应用、帐户、轻松使用等。</span><span class="sxs-lookup"><span data-stu-id="0009b-275">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="0009b-276">由于新的"设置"应用不同于旧式"设置"应用，因此更新时将删除之前围绕环境放置的任何"设置"窗口。</span><span class="sxs-lookup"><span data-stu-id="0009b-276">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

!["新建设置"应用主页](images/new-settings-app.png)

**<span data-ttu-id="0009b-278">新功能和设置</span><span class="sxs-lookup"><span data-stu-id="0009b-278">New features and settings</span></span>**
- <span data-ttu-id="0009b-279">设置搜索：使用关键字或设置名称从"设置"主页搜索设置。</span><span class="sxs-lookup"><span data-stu-id="0009b-279">Settings search: search for settings from the Settings homepage using keywords or the setting's name.</span></span>
- <span data-ttu-id="0009b-280">系统>声音：</span><span class="sxs-lookup"><span data-stu-id="0009b-280">System > Sound:</span></span>
  - <span data-ttu-id="0009b-281">输入和输出音频设备：独立选择输入和输出音频设备 (例如，通过 Bluetooth 耳机收听音频或使用 USB-C 麦克风进行音频输入) 。</span><span class="sxs-lookup"><span data-stu-id="0009b-281">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span> 
    > [!NOTE]
    > <span data-ttu-id="0009b-282">Bluetooth HoloLens 2 不支持麦克风。</span><span class="sxs-lookup"><span data-stu-id="0009b-282">Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="0009b-283">应用量：独立调整每个应用的音量。</span><span class="sxs-lookup"><span data-stu-id="0009b-283">App volume: independently adjust the volume of each app.</span></span>
- <span data-ttu-id="0009b-284">系统>电源&睡眠：选择设备在一段时间不活动后应何时进入睡眠状态。</span><span class="sxs-lookup"><span data-stu-id="0009b-284">System > Power & sleep: choose when the device should go to sleep after a period of inactivity.</span></span>
- <span data-ttu-id="0009b-285">系统>电池：手动启用节电模式或设置节电模式自动打开的电池阈值。</span><span class="sxs-lookup"><span data-stu-id="0009b-285">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically.</span></span>
- <span data-ttu-id="0009b-286">设备> USB：默认情况下可以禁用 USB 连接。</span><span class="sxs-lookup"><span data-stu-id="0009b-286">Devices > USB: you can disable USB connections by default.</span></span>
- <span data-ttu-id="0009b-287">Internet &网络：</span><span class="sxs-lookup"><span data-stu-id="0009b-287">Network & Internet:</span></span>
  - <span data-ttu-id="0009b-288">USB-C 以太网适配器现在将显示在网络和 Internet &中。</span><span class="sxs-lookup"><span data-stu-id="0009b-288">USB-C Ethernet adapters will now appear in Network & Internet.</span></span>
  - <span data-ttu-id="0009b-289">USB-C 以太网适配器设置现已可用，包括其 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="0009b-289">USB-C Ethernet adapter settings are now available, including its IP address.</span></span>
  - <span data-ttu-id="0009b-290">现在可以在 HoloLens 2 上启用飞行模式。</span><span class="sxs-lookup"><span data-stu-id="0009b-290">You can now enable airplane mode on HoloLens 2.</span></span>
- <span data-ttu-id="0009b-291">应用：你可以重置用于文件和链接类型的默认应用。</span><span class="sxs-lookup"><span data-stu-id="0009b-291">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="0009b-292">有关详细信息 [，请参阅](#default-app-picker) 默认应用选取器。</span><span class="sxs-lookup"><span data-stu-id="0009b-292">See [Default app picker](#default-app-picker) for more information.</span></span>
- <span data-ttu-id="0009b-293">其他用户>的帐户：设备所有者可以添加用户、将标准用户升级到设备所有者、将设备所有者降级为标准用户以及删除用户。</span><span class="sxs-lookup"><span data-stu-id="0009b-293">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="0009b-294">轻松使用：更改文本大小和一些视觉效果。</span><span class="sxs-lookup"><span data-stu-id="0009b-294">Ease of Access: change text size and some visual effects.</span></span>

**<span data-ttu-id="0009b-295">已知问题</span><span class="sxs-lookup"><span data-stu-id="0009b-295">Known issues</span></span>**
- <span data-ttu-id="0009b-296">以前放置的"设置"窗口将被删除 (请参阅上面的) 。</span><span class="sxs-lookup"><span data-stu-id="0009b-296">Previously placed Settings windows will be removed (see note above).</span></span>
- <span data-ttu-id="0009b-297">访问"通知"页可能会使"设置"应用崩溃 (调查) 。</span><span class="sxs-lookup"><span data-stu-id="0009b-297">Visiting the Notifications page may crash the Settings app (investigating).</span></span>
- <span data-ttu-id="0009b-298">以太网页面当前不会显示 (即将修复) 。</span><span class="sxs-lookup"><span data-stu-id="0009b-298">The Ethernet page currently doesn't show up (to be fixed soon).</span></span>
- <span data-ttu-id="0009b-299">你无法再使用"设置"应用重命名设备 (IT 管理员可以使用预配包或 MDM 将设备重命名为) 。</span><span class="sxs-lookup"><span data-stu-id="0009b-299">You can no longer rename your device with the Settings app (IT admins can use provisioning packages or MDM to rename devices).</span></span>
- <span data-ttu-id="0009b-300">新 Microsoft Edge 的电池使用情况可能不准确，因为其性质是 UWP 适配器层支持的 Win32 桌面应用程序， (即将) 。</span><span class="sxs-lookup"><span data-stu-id="0009b-300">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon).</span></span>

### <span data-ttu-id="0009b-301">默认应用选取器</span><span class="sxs-lookup"><span data-stu-id="0009b-301">Default app picker</span></span>

<span data-ttu-id="0009b-302">激活超链接或打开具有多个支持超链接的已安装应用的文件类型时，你将看到一个新窗口打开，提示你选择应处理文件或链接类型的已安装应用。</span><span class="sxs-lookup"><span data-stu-id="0009b-302">When you activate a hyperlink or open a file type with more than one installed app which supports it, you will see a new window open prompting you to select which installed app should handle the file or link type.</span></span> <span data-ttu-id="0009b-303">在此窗口中，还可以选择让所选应用处理文件或链接类型"一次"或"始终"。</span><span class="sxs-lookup"><span data-stu-id="0009b-303">In this window you can also choose to have the selected app handle the file or link type "Once" or "Always."</span></span>

![应用选取器窗口](images/default-app-picker.png)

<span data-ttu-id="0009b-305">如果你选择"始终"，但后来想要更改哪个应用处理特定文件或链接类型，可以在"设置"或"应用"中重置> **默认值**。</span><span class="sxs-lookup"><span data-stu-id="0009b-305">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span></span> <span data-ttu-id="0009b-306">滚动到页面底部，然后选择"文件类型的默认应用\*\*\*\*"和/或"链接类型的默认应用"下的"清除"按钮。</span><span class="sxs-lookup"><span data-stu-id="0009b-306">Scroll to the bottom of the page and select the **Clear** button under "Default apps for file types" and/or "Default apps for link types."</span></span> <span data-ttu-id="0009b-307">与桌面电脑的类似设置不同，不能重置单个文件类型默认值。</span><span class="sxs-lookup"><span data-stu-id="0009b-307">Unlike the similar setting on desktop PCs, you can't reset individual file type defaults.</span></span>

### <span data-ttu-id="0009b-308">Office Web 应用</span><span class="sxs-lookup"><span data-stu-id="0009b-308">Office web app</span></span>

<span data-ttu-id="0009b-309">Office Web 应用已添加到"开始"菜单中的"所有应用程序"列表中。</span><span class="sxs-lookup"><span data-stu-id="0009b-309">The Office web app has been added to the "All apps" list in the Start menu.</span></span> <span data-ttu-id="0009b-310">还可以将此 Web 应用固定到"开始"页面或将其卸载。</span><span class="sxs-lookup"><span data-stu-id="0009b-310">This web app can also be pinned to Start or uninstalled.</span></span> <span data-ttu-id="0009b-311">由于这是一个 Web 应用，因此其功能与通过访问体验完全匹配 https://www.office.com 。</span><span class="sxs-lookup"><span data-stu-id="0009b-311">Because this is a web app, its functionality matches exactly what you'd experience by visiting https://www.office.com.</span></span> <span data-ttu-id="0009b-312">仅在 HoloLens 2 具有活动的 Internet 连接时，Office Web 应用功能才可用。</span><span class="sxs-lookup"><span data-stu-id="0009b-312">Office web app functionality is only available when your HoloLens 2 has an active internet connection.</span></span>

### <span data-ttu-id="0009b-313">轻扫以键入</span><span class="sxs-lookup"><span data-stu-id="0009b-313">Swipe to type</span></span>

<span data-ttu-id="0009b-314">一些客户发现通过轻扫要键入的单词的形状，在虚拟键盘上"键入"速度更快，我们正在预览全息键盘的此功能。</span><span class="sxs-lookup"><span data-stu-id="0009b-314">Some customers find it faster to "type" on virtual keyboards by swiping the shape of the word they intend to type, and we're previewing this feature for the holographic keyboard.</span></span> <span data-ttu-id="0009b-315">通过通过全息键盘的平面传递手指的尖角，轻扫该单词的形状，然后从键盘平面撤消手指的尖角，可以一次轻扫一个单词。</span><span class="sxs-lookup"><span data-stu-id="0009b-315">You can swipe one word at a time by passing the tip of your finger through the plane of the holographic keyboard, swiping the shape of the word, and then withdrawing the tip of your finger from the plane of the keyboard.</span></span> <span data-ttu-id="0009b-316">通过从键盘删除单词之间的手指，无需按空格键，即可轻扫后续单词。</span><span class="sxs-lookup"><span data-stu-id="0009b-316">You can swipe follow-up words without needing to press the spacebar by removing your finger from the keyboard between words.</span></span> <span data-ttu-id="0009b-317">如果你看到手指在键盘上的移动后看到轻扫轨迹，你将知道该功能正在工作。</span><span class="sxs-lookup"><span data-stu-id="0009b-317">You will know the feature is working if you see a swipe trail following your finger's movement on the keyboard.</span></span>

<span data-ttu-id="0009b-318">请注意，此功能可能很难使用和掌握，因为全息键盘的性质，与移动电话显示屏不同，你无法抵御手指 (因此) 。</span><span class="sxs-lookup"><span data-stu-id="0009b-318">Please note, this feature can be tricky to use and master because of the nature of a holographic keyboard where you don't feel resistance against your finger (unlike a mobile phone display).</span></span> <span data-ttu-id="0009b-319">我们正在评估此功能以公开发布，因此您的反馈非常重要;无论你发现此功能有用还是有反馈反馈，请通过反馈中心 [告诉我们](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="0009b-319">We are evaluating this feature for public release, so your feedback is important; whether you find the feature useful or you have constructive feedback, please let us know via [Feedback Hub](hololens-feedback.md).</span></span>

### <span data-ttu-id="0009b-320">USB-C 外部麦克风支持</span><span class="sxs-lookup"><span data-stu-id="0009b-320">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0009b-321">插入 USB **麦克风不会自动将其设置为输入设备**。</span><span class="sxs-lookup"><span data-stu-id="0009b-321">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="0009b-322">在插入一组 USB-C 耳机时，用户将观察到耳机的音频将自动重定向到耳机，但 HoloLens 操作系统将内部麦克风阵列设置为高于任何其他输入设备的优先级。</span><span class="sxs-lookup"><span data-stu-id="0009b-322">When plugging in a set of USB-C headphones users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> **<span data-ttu-id="0009b-323">若要使用 USB-C 麦克风，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="0009b-323">In order to use a USB-C microphone follow the steps below.</span></span>**

<span data-ttu-id="0009b-324">用户可以使用"声音设置"面板选择连接 USB-C **的外部麦克风** 。</span><span class="sxs-lookup"><span data-stu-id="0009b-324">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="0009b-325">USB-C 麦克风可用于呼叫、录制等。</span><span class="sxs-lookup"><span data-stu-id="0009b-325">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="0009b-326">打开"**设置"** 应用，然后选择 **"系统**  ->  **声音"。**</span><span class="sxs-lookup"><span data-stu-id="0009b-326">Open the **Settings** app and select **System** -> **Sound**.</span></span>

![声音设置](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="0009b-328">若要将外部麦克风与 **远程协助**一同使用，用户需要单击"管理声音设备"超链接。</span><span class="sxs-lookup"><span data-stu-id="0009b-328">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="0009b-329">然后使用下拉列表将外部麦克风设置为"默认" **或** " **通信默认值"。**</span><span class="sxs-lookup"><span data-stu-id="0009b-329">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="0009b-330">选择 **"** 默认值"意味着外部麦克风将无处不在。</span><span class="sxs-lookup"><span data-stu-id="0009b-330">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="0009b-331">选择 **"** 通信默认值"意味着外部麦克风将用于远程协助和其他通信应用，但 HoloLens 麦克风阵列可能仍用于其他任务。</span><span class="sxs-lookup"><span data-stu-id="0009b-331">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![管理声音设备](images/usbc-mic-2.png)

<br>

![设置麦克风默认值](images/usbc-mic-3.jpg)

#### <span data-ttu-id="0009b-334">麦克风Bluetooth如何？</span><span class="sxs-lookup"><span data-stu-id="0009b-334">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="0009b-335">遗憾的是Bluetooth HoloLens 2 上目前仍不支持麦克风。</span><span class="sxs-lookup"><span data-stu-id="0009b-335">Unfortunately Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

#### <span data-ttu-id="0009b-336">USB-C 麦克风疑难解答</span><span class="sxs-lookup"><span data-stu-id="0009b-336">Troubleshooting USB-C microphones</span></span>

<span data-ttu-id="0009b-337">请注意，某些 USB-C 麦克风错误地将自己报告为 *麦克风和扬声器* 。</span><span class="sxs-lookup"><span data-stu-id="0009b-337">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="0009b-338">这是麦克风而不是 HoloLens 的问题。</span><span class="sxs-lookup"><span data-stu-id="0009b-338">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="0009b-339">将其中一个麦克风插入 HoloLens 时，可能会丢失声音。</span><span class="sxs-lookup"><span data-stu-id="0009b-339">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="0009b-340">幸运的是，有一个简单的解决方法。</span><span class="sxs-lookup"><span data-stu-id="0009b-340">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="0009b-341">在 **"设置**系统声音"中，将内置扬声器 (模拟功能音频) 设置为  ->  \*\*\*\*  ->  \*\*\*\*\*\*默认设备\*\*。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0009b-341">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="0009b-342">HoloLens 应记住此设置，即使麦克风稍后被删除并重新连接。</span><span class="sxs-lookup"><span data-stu-id="0009b-342">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C 麦克风疑难解答](images/usbc-mic-4.png)

### <span data-ttu-id="0009b-344">在展台模式下使用新的"设置"和"边缘"应用</span><span class="sxs-lookup"><span data-stu-id="0009b-344">Use the new Settings and Edge apps in Kiosk modes</span></span>

<span data-ttu-id="0009b-345">在展 [台中加入](hololens-kiosk.md)应用时，IT 管理员通常会将应用添加到展台，但使用应用用户模型 ID (AUMID) 。</span><span class="sxs-lookup"><span data-stu-id="0009b-345">When including apps in in [Kiosks](hololens-kiosk.md), an IT Admin often adds the app to the Kiosk but using it's App User Model ID (AUMID).</span></span> <span data-ttu-id="0009b-346">由于"设置"应用和 Microsoft Edge 应用都被视为新应用，并且与为这些应用使用 AUMID 的较旧应用展台需要更新以使用新的 AUMID 不同。</span><span class="sxs-lookup"><span data-stu-id="0009b-346">Because both the Settings app and Microsoft Edge app are considered new apps and different that the older apps Kiosks that use AUMIDs for those apps will need to be updated to use the new AUMID.</span></span>

<span data-ttu-id="0009b-347">修改展台以包含新应用时，我们建议在新的 AUMID 中添加并保留旧 AUMID。</span><span class="sxs-lookup"><span data-stu-id="0009b-347">When modifying a Kiosk to include the new apps, we recommend adding in the new AUMID as well as leaving the old one.</span></span> <span data-ttu-id="0009b-348">这将在用户更新操作系统时创建一个简单的转换，并且不需要接收新策略来继续像预期一样使用展台。</span><span class="sxs-lookup"><span data-stu-id="0009b-348">This will create an easy transition when users update the OS and won't need to receive new policies to keep using the Kiosk as intended.</span></span>

| <span data-ttu-id="0009b-349">应用</span><span class="sxs-lookup"><span data-stu-id="0009b-349">App</span></span>                    | <span data-ttu-id="0009b-350">AUMID</span><span class="sxs-lookup"><span data-stu-id="0009b-350">AUMID</span></span>                                                  |
|------------------------|--------------------------------------------------------|
| <span data-ttu-id="0009b-351">旧设置应用</span><span class="sxs-lookup"><span data-stu-id="0009b-351">Old Settings App</span></span>       | <span data-ttu-id="0009b-352">HolographicSystemSettings_cw5n1h2txyewy！应用</span><span class="sxs-lookup"><span data-stu-id="0009b-352">HolographicSystemSettings_cw5n1h2txyewy!App</span></span>            |
| <span data-ttu-id="0009b-353">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="0009b-353">New Settings App</span></span>       | <span data-ttu-id="0009b-354">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！应用</span><span class="sxs-lookup"><span data-stu-id="0009b-354">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App</span></span> |
| <span data-ttu-id="0009b-355">旧 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="0009b-355">Old Microsoft Edge app</span></span> | <span data-ttu-id="0009b-356">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span><span class="sxs-lookup"><span data-stu-id="0009b-356">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span></span>    |
| <span data-ttu-id="0009b-357">新的 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="0009b-357">New Microsoft Edge app</span></span> | <span data-ttu-id="0009b-358">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE</span><span class="sxs-lookup"><span data-stu-id="0009b-358">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE</span></span>    |

### <span data-ttu-id="0009b-359">用于处理故障的展台模式行为更改</span><span class="sxs-lookup"><span data-stu-id="0009b-359">Kiosk mode behavior changes for handling of failures</span></span>

<span data-ttu-id="0009b-360">在较旧的内部版本，如果设备具有展台配置（即全局分配的访问权限和 AAD 组成员身份的组合）。如果确定 AAD 组成员身份失败，用户将看到"开始"菜单中未显示[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)任何内容。</span><span class="sxs-lookup"><span data-stu-id="0009b-360">In older builds, if a device had a kiosk configuration, which is a combination of both global assigned access and AAD group member assigned access, if determining AAD group membership failed, the user would see “[nothing shown in start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)” menu.</span></span>

<span data-ttu-id="0009b-361">从 Windows 预览体验成员版本开始，展台体验将回退到全局展台配置 (如果存在，) AAD 组展台模式期间发生故障的情况。</span><span class="sxs-lookup"><span data-stu-id="0009b-361">Starting in Windows Insider release, the kiosk experience will fallback to global kiosk configuration (if present) in case of failures during AAD group kiosk mode.</span></span>

### <span data-ttu-id="0009b-362">通过"设置"应用配置回退诊断</span><span class="sxs-lookup"><span data-stu-id="0009b-362">Configuring Fallback Diagnostics via Settings app</span></span>

<span data-ttu-id="0009b-363">现在，在"设置"应用中，用户可以配置 [回退诊断的行为](hololens-diagnostic-logs.md)。</span><span class="sxs-lookup"><span data-stu-id="0009b-363">Now in Settings App, a user can configure the behavior of [Fallback Diagnostics](hololens-diagnostic-logs.md).</span></span> <span data-ttu-id="0009b-364">在"设置"应用中，**导航到**"隐私  ->  **疑难**解答"页以配置此设置。</span><span class="sxs-lookup"><span data-stu-id="0009b-364">In the Settings app navigate to **Privacy** -> **Troubleshooting** page to configure this setting.</span></span>

> [!NOTE]
> <span data-ttu-id="0009b-365">如果为设备配置了 MDM 策略，用户将不能覆盖该行为。</span><span class="sxs-lookup"><span data-stu-id="0009b-365">If there is MDM policy configured for the device, user will not be able to override that behavior.</span></span>  

### <span data-ttu-id="0009b-366">与附近设备共享内容</span><span class="sxs-lookup"><span data-stu-id="0009b-366">Share things with nearby devices</span></span>

<span data-ttu-id="0009b-367">与 Windows 10 设备（包括运行 HoloLens 预览体验成员版本 20279.1006+的其他 HoloLens 2 设备）附近共享内容。</span><span class="sxs-lookup"><span data-stu-id="0009b-367">Share things with near by Windows 10 devices, including both PCs and other HoloLens 2 devices running HoloLens Insider builds 20279.1006+.</span></span> <span data-ttu-id="0009b-368">你可以尝试在"**设置系统**共享体验"中试用，以将文件或  ->  \*\*\*\*  ->  \*\*\*\* URL 从 HoloLens 共享到电脑。</span><span class="sxs-lookup"><span data-stu-id="0009b-368">You can try it out in **Settings** -> **System** -> **Shared Experiences** to share files or URLs from a HoloLens to a PC.</span></span> <span data-ttu-id="0009b-369">有关更多详细信息，请阅读有关如何在 [Windows 10 中与附近设备共享内容的详细信息](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)。</span><span class="sxs-lookup"><span data-stu-id="0009b-369">For more details read more about how to [Share things with nearby devices in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).</span></span>

<span data-ttu-id="0009b-370">可通过 [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)管理此功能。</span><span class="sxs-lookup"><span data-stu-id="0009b-370">This feature can be managed via [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).</span></span>

### <span data-ttu-id="0009b-371">新的操作系统更新疑难解答程序</span><span class="sxs-lookup"><span data-stu-id="0009b-371">New OS Update troubleshooter</span></span>

<span data-ttu-id="0009b-372">除了"设置"应用中的上一个疑难解答程序外，还添加了新的疑难解答程序，并添加了新的操作系统更新设置应用。</span><span class="sxs-lookup"><span data-stu-id="0009b-372">In addition to the previous troubleshooters within the Settings app, a new troubleshooter has been added with the addition of the new Settings app for OS Updates.</span></span> <span data-ttu-id="0009b-373">导航到 **"设置**  ->  **更新 &amp; 安全性**  ->  \*\*\*\*  ->  **疑难解答"Windows 更新**，然后选择"**开始"。**</span><span class="sxs-lookup"><span data-stu-id="0009b-373">Navigate to **Settings** -> **Update &amp; Security** -> **Troubleshoot** -> **Windows Update** and select **Start**.</span></span> <span data-ttu-id="0009b-374">这允许你在通过操作系统更新重现问题的同时收集跟踪，以更好地帮助 IT 或支持进行疑难解答。</span><span class="sxs-lookup"><span data-stu-id="0009b-374">This allows you to collect traces while reproducing your issue with OS Updates to assist better in troubleshooting with your IT or support.</span></span>

### <span data-ttu-id="0009b-375">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="0009b-375">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="0009b-376">[脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics) 还将包含序列号和操作系统版本的其他设备信息。</span><span class="sxs-lookup"><span data-stu-id="0009b-376">[Offline diagnostics](hololens-diagnostic-logs.md#offline-diagnostics) will also include additional device information for serial number and OS version.</span></span>






## <span data-ttu-id="0009b-377">开始接收预览体验成员版本</span><span class="sxs-lookup"><span data-stu-id="0009b-377">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="0009b-378">如果最近尚未更新，请重启设备以更新状态并获取最新内部版本。</span><span class="sxs-lookup"><span data-stu-id="0009b-378">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="0009b-379">"重新启动设备"语音命令运行正常。</span><span class="sxs-lookup"><span data-stu-id="0009b-379">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="0009b-380">还可以选择"设置/Windows 预览体验计划"中的"重启"按钮。</span><span class="sxs-lookup"><span data-stu-id="0009b-380">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="0009b-381">后端有一个你可能会遇到的 Bug，这样你才能重新进入轨道。</span><span class="sxs-lookup"><span data-stu-id="0009b-381">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="0009b-382">在 HoloLens 2 设备上 **，转到&** Windows 预览  >  \*\*\*\*  >  **体验计划**"设置更新"，然后选择 **"开始使用"。**</span><span class="sxs-lookup"><span data-stu-id="0009b-382">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="0009b-383">链接你用于注册为 Windows 预览体验成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="0009b-383">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="0009b-384">Windows 预览体验成员现在迁移到频道。</span><span class="sxs-lookup"><span data-stu-id="0009b-384">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="0009b-385">快速**圈**将变为**开发人员频道**，慢圈将成为\*\*\*\* **Beta**渠道，而发布预览圈将成为\*\*\*\*\*\*发布预览频道\*\*。</span><span class="sxs-lookup"><span data-stu-id="0009b-385">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="0009b-386">该映射如下所示：</span><span class="sxs-lookup"><span data-stu-id="0009b-386">Here is what that mapping looks like:</span></span>

![Windows 预览体验成员频道说明](images/WindowsInsiderChannels.png)

<span data-ttu-id="0009b-388">有关详细信息，请参阅 Windows 博客 [上的 Windows 预览](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 体验成员频道介绍。</span><span class="sxs-lookup"><span data-stu-id="0009b-388">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="0009b-389">然后，选择 **"Windows**的活动开发"，选择是希望接收 **开发人员** 频道还是 **Beta 渠道** 版本，并查看计划条款。</span><span class="sxs-lookup"><span data-stu-id="0009b-389">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="0009b-390">选择 **">立即重启** 以完成。</span><span class="sxs-lookup"><span data-stu-id="0009b-390">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="0009b-391">重启设备后，转到"设置>更新& **安全>检查** 更新，获取最新内部版本。</span><span class="sxs-lookup"><span data-stu-id="0009b-391">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <span data-ttu-id="0009b-392">更新0x80070490问题</span><span class="sxs-lookup"><span data-stu-id="0009b-392">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="0009b-393">如果在开发或 Beta 渠道0x80070490更新时遇到更新错误，请尝试以下短期方法。</span><span class="sxs-lookup"><span data-stu-id="0009b-393">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="0009b-394">它涉及移动预览体验成员频道、选取更新，然后将预览体验成员频道移回。</span><span class="sxs-lookup"><span data-stu-id="0009b-394">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <span data-ttu-id="0009b-395">第一阶段 - 版本预览</span><span class="sxs-lookup"><span data-stu-id="0009b-395">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="0009b-396">设置，更新&安全，Windows 预览体验计划，选择 **版本预览频道**。</span><span class="sxs-lookup"><span data-stu-id="0009b-396">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="0009b-397">设置， &安全性， Windows 更新， **检查更新**。</span><span class="sxs-lookup"><span data-stu-id="0009b-397">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="0009b-398">更新后，继续第二阶段。</span><span class="sxs-lookup"><span data-stu-id="0009b-398">After the update, continue on to Stage two.</span></span>

#### <span data-ttu-id="0009b-399">第二阶段 - 开发人员频道</span><span class="sxs-lookup"><span data-stu-id="0009b-399">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="0009b-400">设置，更新&安全，Windows 预览体验计划，选择 **开发人员频道**。</span><span class="sxs-lookup"><span data-stu-id="0009b-400">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="0009b-401">设置， &安全性， Windows 更新， **检查更新**。</span><span class="sxs-lookup"><span data-stu-id="0009b-401">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <span data-ttu-id="0009b-402">FFU 下载和快速方向</span><span class="sxs-lookup"><span data-stu-id="0009b-402">FFU download and flash directions</span></span>
<span data-ttu-id="0009b-403">若要使用已签名的 Ffu 进行测试，首先需要先对设备进行解锁，然后才能闪烁已进行测试的已签名 ffu。</span><span class="sxs-lookup"><span data-stu-id="0009b-403">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="0009b-404">在电脑上：</span><span class="sxs-lookup"><span data-stu-id="0009b-404">On PC:</span></span>

    1. <span data-ttu-id="0009b-405">从 下载 ffu 到你的电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="0009b-405">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="0009b-406">从 Microsoft store (ARC) 高级恢复配套设备 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) ： 。</span><span class="sxs-lookup"><span data-stu-id="0009b-406">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="0009b-407">在 HoloLens - Flight Unlock： Open **Settings**  >  **Update & Security**Windows Insider  >  **Program** then sign up， reboot device.</span><span class="sxs-lookup"><span data-stu-id="0009b-407">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="0009b-408">Flash FFU - 现在可以使用 ARC 对已进行飞行的 FFU 进行闪烁。</span><span class="sxs-lookup"><span data-stu-id="0009b-408">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="0009b-409">提供反馈并报告问题</span><span class="sxs-lookup"><span data-stu-id="0009b-409">Provide feedback and report issues</span></span>

<span data-ttu-id="0009b-410">请使用 [HoloLens](hololens-feedback.md) 上的"反馈中心"应用提供反馈并报告问题。</span><span class="sxs-lookup"><span data-stu-id="0009b-410">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="0009b-411">使用反馈中心可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。</span><span class="sxs-lookup"><span data-stu-id="0009b-411">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="0009b-412">应以相同方式报告与 HoloLens 的中文和日文版本有关的问题。</span><span class="sxs-lookup"><span data-stu-id="0009b-412">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="0009b-413">请务必接受询问您是否希望反馈中心访问"文档"文件夹的提示， (系统提示"是") 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0009b-413">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="0009b-414">开发人员注意事项</span><span class="sxs-lookup"><span data-stu-id="0009b-414">Note for developers</span></span>

<span data-ttu-id="0009b-415">欢迎并鼓励你尝试使用 HoloLens 预览体验成员版本开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="0009b-415">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="0009b-416">请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 开始。</span><span class="sxs-lookup"><span data-stu-id="0009b-416">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="0009b-417">这些相同的说明与 HoloLens 的预览体验成员版本一致。</span><span class="sxs-lookup"><span data-stu-id="0009b-417">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="0009b-418">可以使用与 HoloLens Visual Studio相同的 Unity 版本和版本。</span><span class="sxs-lookup"><span data-stu-id="0009b-418">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="0009b-419">停止接收预览体验成员内部版本</span><span class="sxs-lookup"><span data-stu-id="0009b-419">Stop receiving Insider builds</span></span>

<span data-ttu-id="0009b-420">如果你不再希望接收 Windows 全息版的预览体验成员版本，你可以选择在 HoloLens 运行生产版本时退出，或者可以使用高级恢复助手[](hololens-recovery.md)将设备恢复到非预览体验成员版本的 Windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="0009b-420">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="0009b-421">存在一个已知问题，即手动重新安装新的预览版本后从 Insider Preview 版本取消注册的用户将遇到蓝屏。</span><span class="sxs-lookup"><span data-stu-id="0009b-421">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="0009b-422">之后，他们必须手动恢复其设备。</span><span class="sxs-lookup"><span data-stu-id="0009b-422">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="0009b-423">有关你是否受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。</span><span class="sxs-lookup"><span data-stu-id="0009b-423">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="0009b-424">若要验证 HoloLens 是否正在运行生产版本：</span><span class="sxs-lookup"><span data-stu-id="0009b-424">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="0009b-425">转到" **系统>设置>"，** 并查找内部版本编号。</span><span class="sxs-lookup"><span data-stu-id="0009b-425">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="0009b-426">[有关生产内部版本号，请参阅发行说明](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="0009b-426">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="0009b-427">若要选择退出预览体验成员版本：</span><span class="sxs-lookup"><span data-stu-id="0009b-427">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="0009b-428">在运行生产内部版本 HoloLens 上，转到"设置>更新& Windows 预览体验>计划"，**然后选择**"停止预览**体验成员版本"。**</span><span class="sxs-lookup"><span data-stu-id="0009b-428">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="0009b-429">按照说明选择退出设备。</span><span class="sxs-lookup"><span data-stu-id="0009b-429">Follow the instructions to opt out your device.</span></span>
