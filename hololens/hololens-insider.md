---
title: Microsoft HoloLens 内部预览版
description: 开始使用预览体验成员版本并为 HoloLens 的下一个主要操作系统更新提供有价值的反馈非常简单。
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
ms.date: 1/13/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 6df24d3a8640edeb9196834f940500aa51e85af7
ms.sourcegitcommit: 50e4d61a31b94d5007776064b4012e26cf9ecbbb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271693"
---
# <span data-ttu-id="a6d97-103">Microsoft HoloLens 内部预览版</span><span class="sxs-lookup"><span data-stu-id="a6d97-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="a6d97-104">欢迎使用 HoloLens 的最新 Insider Preview 版本！</span><span class="sxs-lookup"><span data-stu-id="a6d97-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="a6d97-105">开始操作非常简单，并为[](hololens-insider.md#start-receiving-insider-builds)HoloLens 的下一个主要操作系统更新提供有价值的反馈。</span><span class="sxs-lookup"><span data-stu-id="a6d97-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="a6d97-106">Windows 预览体验成员发行说明</span><span class="sxs-lookup"><span data-stu-id="a6d97-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="a6d97-107">我们希望再次开始向 Windows 预览体验成员提供新功能。</span><span class="sxs-lookup"><span data-stu-id="a6d97-107">We are excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="a6d97-108">我们将测试到开发人员频道获取最新更新。</span><span class="sxs-lookup"><span data-stu-id="a6d97-108">We will be flighting to the Dev Channel for the latest updates.</span></span> <span data-ttu-id="a6d97-109">我们将继续更新此页面，因为我们向 Windows 预览体验成员版本添加更多功能和更新。</span><span class="sxs-lookup"><span data-stu-id="a6d97-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span>  <span data-ttu-id="a6d97-110">感到兴奋并准备好将这些更新融合到现实中。</span><span class="sxs-lookup"><span data-stu-id="a6d97-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="a6d97-111">功能名称</span><span class="sxs-lookup"><span data-stu-id="a6d97-111">Feature Name</span></span>                                              | <span data-ttu-id="a6d97-112">简短说明</span><span class="sxs-lookup"><span data-stu-id="a6d97-112">Short description</span></span>                                                                      | <span data-ttu-id="a6d97-113">在内部版本可用</span><span class="sxs-lookup"><span data-stu-id="a6d97-113">Available in build</span></span> |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [<span data-ttu-id="a6d97-114">新版 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a6d97-114">New Microsoft Edge</span></span>](#introducing-the-new-microsoft-edge) | <span data-ttu-id="a6d97-115">新的基于 Chromium 的 Microsoft Edge 现在可用于 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="a6d97-115">The new, Chromium-based Microsoft Edge is now available for HoloLens 2</span></span>                         | <span data-ttu-id="a6d97-116">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a6d97-116">20279.1006</span></span> |
| [<span data-ttu-id="a6d97-117">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="a6d97-117">New Settings app</span></span>](#new-settings-app)                     | <span data-ttu-id="a6d97-118">旧"设置"应用将替换为具有新功能和设置的更新版本</span><span class="sxs-lookup"><span data-stu-id="a6d97-118">The legacy Settings app is being replaced by an updated version with new features and settings</span></span> | <span data-ttu-id="a6d97-119">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a6d97-119">20279.1006</span></span> |
| [<span data-ttu-id="a6d97-120">默认应用选取器</span><span class="sxs-lookup"><span data-stu-id="a6d97-120">Default app picker</span></span>](#default-app-picker)                 | <span data-ttu-id="a6d97-121">选择应针对每个文件或链接类型启动的应用</span><span class="sxs-lookup"><span data-stu-id="a6d97-121">Choose which app should launch for each file or link type</span></span>                                      | <span data-ttu-id="a6d97-122">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a6d97-122">20279.1006</span></span> |
| [<span data-ttu-id="a6d97-123">Office Web 应用</span><span class="sxs-lookup"><span data-stu-id="a6d97-123">Office web app</span></span>](#office-web-app)                         | <span data-ttu-id="a6d97-124">Office Web 应用的快捷方式现在列在"所有应用"中</span><span class="sxs-lookup"><span data-stu-id="a6d97-124">A shortcut to the Office web app is now listed in "All apps"</span></span>                                   | <span data-ttu-id="a6d97-125">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a6d97-125">20279.1006</span></span> |
| [<span data-ttu-id="a6d97-126">轻扫以键入</span><span class="sxs-lookup"><span data-stu-id="a6d97-126">Swipe to type</span></span>](#swipe-to-type)                           | <span data-ttu-id="a6d97-127">使用手指尖在全息键盘上"轻扫"字词</span><span class="sxs-lookup"><span data-stu-id="a6d97-127">Use the tip of your finger to "swipe" words on the holographic keyboard</span></span>                        | <span data-ttu-id="a6d97-128">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a6d97-128">20279.1006</span></span> |
| [<span data-ttu-id="a6d97-129">USB-C 外部麦克风支持</span><span class="sxs-lookup"><span data-stu-id="a6d97-129">USB-C External Microphone Support</span></span>](#usb-c-external-microphone-support) | <span data-ttu-id="a6d97-130">将 USB-C 麦克风用于应用和/或远程协助。</span><span class="sxs-lookup"><span data-stu-id="a6d97-130">Use USB-C microphones for apps and / or Remote Assist.</span></span>| <span data-ttu-id="a6d97-131">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a6d97-131">20279.1006</span></span> |
| [<span data-ttu-id="a6d97-132">展台模式下新应用的新 AUMID</span><span class="sxs-lookup"><span data-stu-id="a6d97-132">New AUMIDs for new apps in Kiosk mode</span></span>](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | <span data-ttu-id="a6d97-133">新设置和边缘应用的 AUMID</span><span class="sxs-lookup"><span data-stu-id="a6d97-133">AUMIDs for new Settings and Edge apps</span></span> | <span data-ttu-id="a6d97-134">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a6d97-134">20279.1006</span></span> |
| [<span data-ttu-id="a6d97-135">改进的展台模式故障帮助</span><span class="sxs-lookup"><span data-stu-id="a6d97-135">Improved Kiosk mode failure handing</span></span>](#kiosk-mode-behavior-changes-for-handling-of-failures) | <span data-ttu-id="a6d97-136">展台模式在空的"开始"菜单之前查找全局分配的访问权限。</span><span class="sxs-lookup"><span data-stu-id="a6d97-136">Kiosk mode looks for Global Assigned Access before empty start menu.</span></span> | <span data-ttu-id="a6d97-137">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a6d97-137">20279.1006</span></span> |
| [<span data-ttu-id="a6d97-138">配置回退诊断</span><span class="sxs-lookup"><span data-stu-id="a6d97-138">Configure Fallback Diagnostics</span></span>](#configuring-fallback-diagnostics-via-settings-app) | <span data-ttu-id="a6d97-139">在"设置"应用中设置回退诊断行为</span><span class="sxs-lookup"><span data-stu-id="a6d97-139">Setting Fallback Diagnostic Behavior in Settings App</span></span> | <span data-ttu-id="a6d97-140">20279.1006</span><span class="sxs-lookup"><span data-stu-id="a6d97-140">20279.1006</span></span> |

### <span data-ttu-id="a6d97-141">引入新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a6d97-141">Introducing the new Microsoft Edge</span></span>

![旧 Microsoft Edge 徽标到新 Microsoft Edge 徽标的动画](images/new-edge.gif)

<span data-ttu-id="a6d97-143">新的 Microsoft Edge [采用 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 开放源代码项目，为客户创建更好的兼容性，减少 Web 开发人员的 Web 碎片。</span><span class="sxs-lookup"><span data-stu-id="a6d97-143">The new Microsoft Edge [adopts the Chromium open source project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) to create better compatibility for customers and less fragmentation of the web for web developers.</span></span>

<span data-ttu-id="a6d97-144">通过此预览体验成员预览版，HoloLens 2 客户首次可以使用新的 Microsoft Edge！</span><span class="sxs-lookup"><span data-stu-id="a6d97-144">With this Insider preview, the new Microsoft Edge is available to HoloLens 2 customers for the first time!</span></span> <span data-ttu-id="a6d97-145">虽然新 Microsoft Edge 最终将替换 HoloLens 2 上的旧版 Microsoft Edge，但预览体验成员目前可以使用这两种浏览器。</span><span class="sxs-lookup"><span data-stu-id="a6d97-145">While the new Microsoft Edge will eventually replace legacy Microsoft Edge on HoloLens 2, both browsers are currently available to Insiders.</span></span> <span data-ttu-id="a6d97-146">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="a6d97-146">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span></span>

![新 Microsoft Edge 屏幕截图](images/new-edge-ui.png)

#### <span data-ttu-id="a6d97-148">启动新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a6d97-148">Launching the new Microsoft Edge</span></span>

<span data-ttu-id="a6d97-149">预览体验成员可以使用两个版本的 Microsoft Edge：新的 Microsoft Edge 新 Microsoft Edge 图标 (由蓝绿色旋转图标) 表示，旧 Microsoft Edge (由白色 ![ ](images/new_edge_logo.png) "e"图标) 表示。</span><span class="sxs-lookup"><span data-stu-id="a6d97-149">There are two versions of Microsoft Edge available to Insiders: the new Microsoft Edge ![new Microsoft Edge icon](images/new_edge_logo.png) (represented by a blue and green swirl icon) and legacy Microsoft Edge (represented by the white "e" icon).</span></span> <span data-ttu-id="a6d97-150">新的 Microsoft Edge 固定到"开始"菜单，将在激活 Web 链接时自动启动。</span><span class="sxs-lookup"><span data-stu-id="a6d97-150">The new Microsoft Edge is pinned to the Start menu and will automatically launch when you activate a web link.</span></span> <span data-ttu-id="a6d97-151">如果你想要还原为使用旧版 Microsoft Edge 作为默认 Web 浏览器，请参阅下面的说明 [重置默认应用](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="a6d97-151">If you would like to revert to using legacy Microsoft Edge as your default web browser, see the instructions below for [resetting default apps](#default-app-picker).</span></span>

> [!NOTE]
> <span data-ttu-id="a6d97-152">当你首次在 HoloLens 2 上启动新的 Microsoft Edge 时，你的设置和数据将导入旧版 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="a6d97-152">When you first launch the new Microsoft Edge on HoloLens 2, your settings and data will be imported from legacy Microsoft Edge.</span></span> <span data-ttu-id="a6d97-153">如果在启动新的 Microsoft Edge 后继续使用旧版 Microsoft Edge，则新数据将不会从旧版 Microsoft Edge 同步到新的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="a6d97-153">If you continue to use legacy Microsoft Edge after launching the new Microsoft Edge, that new data will not be synced from legacy Microsoft Edge to the new Microsoft Edge.</span></span>

#### <span data-ttu-id="a6d97-154">配置新 Microsoft Edge 的策略设置</span><span class="sxs-lookup"><span data-stu-id="a6d97-154">Configuring policy settings for the new Microsoft Edge</span></span>

<span data-ttu-id="a6d97-155">新的 Microsoft Edge 为 IT 管理员提供 HoloLens 2 上的一组比以前适用于旧版 Microsoft Edge 的更为广泛的浏览器策略。</span><span class="sxs-lookup"><span data-stu-id="a6d97-155">The new Microsoft Edge offers IT admins a much broader set of browser policies on HoloLens 2 than were previously available with legacy Microsoft Edge.</span></span>

<span data-ttu-id="a6d97-156">下面是一些有用的资源，用于了解有关管理新 Microsoft Edge 的策略设置更多信息：</span><span class="sxs-lookup"><span data-stu-id="a6d97-156">Here are some helpful resources for learning more about managing policy settings for the new Microsoft Edge:</span></span>

- [<span data-ttu-id="a6d97-157">使用 Microsoft Intune 配置 Microsoft Edge 策略设置</span><span class="sxs-lookup"><span data-stu-id="a6d97-157">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [<span data-ttu-id="a6d97-158">Microsoft Edge 旧版到 Microsoft Edge 策略映射</span><span class="sxs-lookup"><span data-stu-id="a6d97-158">Microsoft Edge Legacy to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [<span data-ttu-id="a6d97-159">Google Chrome 到 Microsoft Edge 策略映射</span><span class="sxs-lookup"><span data-stu-id="a6d97-159">Google Chrome to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- <span data-ttu-id="a6d97-160">[完整的 Microsoft Edge 企业版文档](https://docs.microsoft.com/deployedge/)</span><span class="sxs-lookup"><span data-stu-id="a6d97-160">Full [Microsoft Edge Enterprise documentation](https://docs.microsoft.com/deployedge/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6d97-161">由于新的 Microsoft Edge 支持大量浏览器策略，团队无法保证每个新策略都适用于 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="a6d97-161">Because of the volume of browser policies supported by the new Microsoft Edge, our team is unable to guarantee that each new policy works on HoloLens 2.</span></span> <span data-ttu-id="a6d97-162">但是，我们已测试并确认 HoloLens 2 上以前支持的每个旧 Microsoft Edge 策略的新 Microsoft Edge 等效项可正常工作。</span><span class="sxs-lookup"><span data-stu-id="a6d97-162">However, we've tested and confirmed that the new Microsoft Edge equivalent of each legacy Microsoft Edge policy previously supported on HoloLens 2 work as expected.</span></span> <span data-ttu-id="a6d97-163">请参阅 [Microsoft Edge 旧版到 Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 策略映射，查找与 HoloLens 2 一起使用的每个旧版 Microsoft Edge 浏览器策略的新 Microsoft Edge 等效项。</span><span class="sxs-lookup"><span data-stu-id="a6d97-163">See [Microsoft Edge Legacy to Microsoft Edge policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) to find the new Microsoft Edge equivalent of each legacy Microsoft Edge browser policy you were using with HoloLens 2.</span></span>
>
> <span data-ttu-id="a6d97-164">我们了解至少有两个新的 Microsoft Edge 策略将 *不能* 与 HoloLens 2 一起使用：</span><span class="sxs-lookup"><span data-stu-id="a6d97-164">There are at least two new Microsoft Edge policies that we know *will not* work with HoloLens 2:</span></span>
> - <span data-ttu-id="a6d97-165">EnterpriseModeSiteList</span><span class="sxs-lookup"><span data-stu-id="a6d97-165">EnterpriseModeSiteList</span></span>
> - <span data-ttu-id="a6d97-166">EnterpriseSiteListServiceURL</span><span class="sxs-lookup"><span data-stu-id="a6d97-166">EnterpriseSiteListServiceURL</span></span>

#### <span data-ttu-id="a6d97-167">HoloLens 2 上新 Microsoft Edge 的预计功能</span><span class="sxs-lookup"><span data-stu-id="a6d97-167">What to expect from the new Microsoft Edge on HoloLens 2</span></span>

<span data-ttu-id="a6d97-168">由于新的 Microsoft Edge 是具有新的 UWP 适配器层的本机 Win32 应用，允许它在仅 UWP 设备（如 HoloLens 2）上运行，因此某些功能可能不会立即可用。</span><span class="sxs-lookup"><span data-stu-id="a6d97-168">Because the new Microsoft Edge is a native Win32 app with a new UWP adapter layer allowing it to run on UWP-only devices like HoloLens 2, some features may not be immediately available.</span></span> <span data-ttu-id="a6d97-169">我们将支持未来几个月的新方案和功能，因此请查看此空间了解最新信息。</span><span class="sxs-lookup"><span data-stu-id="a6d97-169">We'll be supporting new scenarios and features over the coming months, so please check this space for up-to-date information.</span></span>

**<span data-ttu-id="a6d97-170">应用场景和功能应能正常工作：</span><span class="sxs-lookup"><span data-stu-id="a6d97-170">Scenarios and features expected to work:</span></span>**
- <span data-ttu-id="a6d97-171">首次运行体验、登录配置文件和同步</span><span class="sxs-lookup"><span data-stu-id="a6d97-171">First-run experience, sign-in to profile, and sync</span></span>
- <span data-ttu-id="a6d97-172">网站应按预期呈现和行为</span><span class="sxs-lookup"><span data-stu-id="a6d97-172">Websites should render and behave as expected</span></span>
- <span data-ttu-id="a6d97-173">大多数浏览器功能 (收藏夹、历史记录等) 应正常工作</span><span class="sxs-lookup"><span data-stu-id="a6d97-173">Most browser functionality (Favorites, History, etc.) should work as expected</span></span>
- <span data-ttu-id="a6d97-174">深色模式</span><span class="sxs-lookup"><span data-stu-id="a6d97-174">Dark mode</span></span>
- <span data-ttu-id="a6d97-175">将 Web 应用安装到设备</span><span class="sxs-lookup"><span data-stu-id="a6d97-175">Installing web apps to the device</span></span>
- <span data-ttu-id="a6d97-176">安装扩展 (请告诉我们，如果你使用的任何扩展在 HoloLens 2) </span><span class="sxs-lookup"><span data-stu-id="a6d97-176">Installing extensions (please let us know if you use any extensions that don't work properly on HoloLens 2)</span></span>
- <span data-ttu-id="a6d97-177">查看和标记 PDF</span><span class="sxs-lookup"><span data-stu-id="a6d97-177">Viewing and marking up a PDF</span></span>
- <span data-ttu-id="a6d97-178">单个浏览器窗口中的空间声音</span><span class="sxs-lookup"><span data-stu-id="a6d97-178">Spatial sound from a single browser window</span></span>
- <span data-ttu-id="a6d97-179">浏览器的自动和手动更新</span><span class="sxs-lookup"><span data-stu-id="a6d97-179">Automatic and manual updating of the browser</span></span>
- <span data-ttu-id="a6d97-180">使用"保存到 PDF"选项 (打印菜单中保存 PDF) </span><span class="sxs-lookup"><span data-stu-id="a6d97-180">Saving a PDF from the Print menu (using "Save to PDF" option)</span></span>

**<span data-ttu-id="a6d97-181">即将推出方案和功能：</span><span class="sxs-lookup"><span data-stu-id="a6d97-181">Scenarios and features coming soon:</span></span>**
- <span data-ttu-id="a6d97-182">WebXR 和 360 Viewer 扩展</span><span class="sxs-lookup"><span data-stu-id="a6d97-182">WebXR and 360 Viewer extension</span></span>
- <span data-ttu-id="a6d97-183">在环境中跨多个窗口浏览时，内容还原以更正窗口</span><span class="sxs-lookup"><span data-stu-id="a6d97-183">Content restoration to correct window when browsing across multiple windows placed in your environment</span></span>
- <span data-ttu-id="a6d97-184">通过浏览器通过视频、混合现实捕获或屏幕共享功能加入 Microsoft Teams (通过音频加入通话效果) </span><span class="sxs-lookup"><span data-stu-id="a6d97-184">Joining a Microsoft Teams call via the browser with video, mixed reality capture, or screen-sharing (joining calls with audio works well)</span></span>

**<span data-ttu-id="a6d97-185">不应工作的方案和功能：</span><span class="sxs-lookup"><span data-stu-id="a6d97-185">Scenarios and features not expected to work:</span></span>**
- <span data-ttu-id="a6d97-186">具有同时音频流的多个窗口的空间声音</span><span class="sxs-lookup"><span data-stu-id="a6d97-186">Spatial sound from multiple windows with simultaneous audio streams</span></span>
- <span data-ttu-id="a6d97-187">"查看它，说出它"</span><span class="sxs-lookup"><span data-stu-id="a6d97-187">"See it, say it"</span></span>
- <span data-ttu-id="a6d97-188">打印</span><span class="sxs-lookup"><span data-stu-id="a6d97-188">Printing</span></span>

**<span data-ttu-id="a6d97-189">热门浏览器问题：</span><span class="sxs-lookup"><span data-stu-id="a6d97-189">Top known browser issues:</span></span>**
- <span data-ttu-id="a6d97-190">重置设备将删除新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a6d97-190">Resetting your device will remove the new Microsoft Edge</span></span>
- <span data-ttu-id="a6d97-191">全息键盘中的放大镜预览显示不正确的内容</span><span class="sxs-lookup"><span data-stu-id="a6d97-191">The magnifier preview in the holographic keyboard shows incorrect content</span></span>

### <span data-ttu-id="a6d97-192">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="a6d97-192">New Settings app</span></span>

<span data-ttu-id="a6d97-193">在此版本中，我们将引入新版本的"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="a6d97-193">With this release, we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="a6d97-194">新的"设置"应用在以下方面包括 HoloLens 2 的新功能和扩展设置：声音、Power & 睡眠、网络 & Internet、应用、帐户、轻松使用等。</span><span class="sxs-lookup"><span data-stu-id="a6d97-194">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="a6d97-195">由于新的"设置"应用不同于旧式"设置"应用，因此更新时将删除之前围绕你的环境放置的任何"设置"窗口。</span><span class="sxs-lookup"><span data-stu-id="a6d97-195">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

!["新建设置"应用主页](images/new-settings-app.png)

**<span data-ttu-id="a6d97-197">新功能和设置</span><span class="sxs-lookup"><span data-stu-id="a6d97-197">New features and settings</span></span>**
- <span data-ttu-id="a6d97-198">设置搜索：使用关键字或设置名称从"设置"主页搜索设置</span><span class="sxs-lookup"><span data-stu-id="a6d97-198">Settings search: search for settings from the Settings homepage using keywords or the setting's name</span></span>
- <span data-ttu-id="a6d97-199">系统>声音：</span><span class="sxs-lookup"><span data-stu-id="a6d97-199">System > Sound:</span></span>
  - <span data-ttu-id="a6d97-200">输入和输出音频设备：独立选择输入和输出音频设备 (例如，通过 Bluetooth 耳机收听音频或使用 USB-C 麦克风进行音频输入) 。</span><span class="sxs-lookup"><span data-stu-id="a6d97-200">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span> <span data-ttu-id="a6d97-201">注意：Bluetooth HoloLens 2 不支持麦克风。</span><span class="sxs-lookup"><span data-stu-id="a6d97-201">Note: Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="a6d97-202">应用量：独立调整每个应用的音量</span><span class="sxs-lookup"><span data-stu-id="a6d97-202">App volume: independently adjust the volume of each app</span></span>
- <span data-ttu-id="a6d97-203">系统>电源&睡眠：选择设备在一段时间不活动后应何时进入睡眠状态</span><span class="sxs-lookup"><span data-stu-id="a6d97-203">System > Power & sleep: choose when the device should go to sleep after a period of inactivity</span></span>
- <span data-ttu-id="a6d97-204">系统>电池：手动启用节电模式或设置节电模式自动打开的电池阈值</span><span class="sxs-lookup"><span data-stu-id="a6d97-204">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically</span></span>
- <span data-ttu-id="a6d97-205">USB >设备：默认情况下可以禁用 USB 连接</span><span class="sxs-lookup"><span data-stu-id="a6d97-205">Devices > USB: you can disable USB connections by default</span></span>
- <span data-ttu-id="a6d97-206">Internet &网络：</span><span class="sxs-lookup"><span data-stu-id="a6d97-206">Network & Internet:</span></span>
  - <span data-ttu-id="a6d97-207">USB-C 以太网适配器现在将显示在网络和 Internet &中</span><span class="sxs-lookup"><span data-stu-id="a6d97-207">USB-C Ethernet adapters will now appear in Network & Internet</span></span>
  - <span data-ttu-id="a6d97-208">USB-C 以太网适配器设置现已可用，包括其 IP 地址</span><span class="sxs-lookup"><span data-stu-id="a6d97-208">USB-C Ethernet adapter settings are now available, including its IP address</span></span>
  - <span data-ttu-id="a6d97-209">现在可以在 HoloLens 2 上启用飞行模式</span><span class="sxs-lookup"><span data-stu-id="a6d97-209">You can now enable airplane mode on HoloLens 2</span></span>
- <span data-ttu-id="a6d97-210">应用：你可以重置用于文件和链接类型的默认应用。</span><span class="sxs-lookup"><span data-stu-id="a6d97-210">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="a6d97-211">有关详细信息 [，请参阅](#default-app-picker) 默认应用选取器。</span><span class="sxs-lookup"><span data-stu-id="a6d97-211">See [Default app picker](#default-app-picker) for more information.</span></span>
- <span data-ttu-id="a6d97-212">其他用户>的帐户：设备所有者可以添加用户、将标准用户升级到设备所有者、将设备所有者降级为标准用户以及删除用户。</span><span class="sxs-lookup"><span data-stu-id="a6d97-212">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="a6d97-213">轻松使用：更改文本大小和一些视觉效果</span><span class="sxs-lookup"><span data-stu-id="a6d97-213">Ease of Access: change text size and some visual effects</span></span>

**<span data-ttu-id="a6d97-214">已知问题</span><span class="sxs-lookup"><span data-stu-id="a6d97-214">Known issues</span></span>**
- <span data-ttu-id="a6d97-215">以前放置的"设置"窗口将被删除 (请参阅上面的) </span><span class="sxs-lookup"><span data-stu-id="a6d97-215">Previously placed Settings windows will be removed (see note above)</span></span>
- <span data-ttu-id="a6d97-216">访问"通知"页可能会崩溃"设置"应用 (调查) </span><span class="sxs-lookup"><span data-stu-id="a6d97-216">Visiting the Notifications page may crash the Settings app (investigating)</span></span>
- <span data-ttu-id="a6d97-217">以太网页面当前不会显示 (即将修复) </span><span class="sxs-lookup"><span data-stu-id="a6d97-217">The Ethernet page currently doesn't show up (to be fixed soon)</span></span>
- <span data-ttu-id="a6d97-218">新 Microsoft Edge 的电池使用情况可能不准确，因为其性质是 UWP 适配器层支持的 Win32 桌面应用程序， (预计) </span><span class="sxs-lookup"><span data-stu-id="a6d97-218">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon)</span></span>

### <span data-ttu-id="a6d97-219">默认应用选取器</span><span class="sxs-lookup"><span data-stu-id="a6d97-219">Default app picker</span></span>

<span data-ttu-id="a6d97-220">激活超链接或打开具有多个支持超链接的已安装应用的文件类型时，你将看到一个新窗口打开，提示你选择应处理文件或链接类型的已安装应用。</span><span class="sxs-lookup"><span data-stu-id="a6d97-220">When you activate a hyperlink or open a file type with more than one installed app which supports it, you will see a new window open prompting you to select which installed app should handle the file or link type.</span></span> <span data-ttu-id="a6d97-221">在此窗口中，还可以选择让所选应用处理文件或链接类型"一次"或"始终"。</span><span class="sxs-lookup"><span data-stu-id="a6d97-221">In this window you can also choose to have the selected app handle the file or link type "Once" or "Always."</span></span>

![应用选取器窗口](images/default-app-picker.png)

<span data-ttu-id="a6d97-223">如果你选择"始终"，但后来想要更改哪个应用处理特定文件或链接类型，可以在"设置"或"应用"中重置> **默认值**。</span><span class="sxs-lookup"><span data-stu-id="a6d97-223">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span></span> <span data-ttu-id="a6d97-224">滚动到页面底部，然后选择"文件类型的默认应用\*\*\*\*"和/或"链接类型的默认应用"下的"清除"按钮。</span><span class="sxs-lookup"><span data-stu-id="a6d97-224">Scroll to the bottom of the page and select the **Clear** button under "Default apps for file types" and/or "Default apps for link types."</span></span> <span data-ttu-id="a6d97-225">与桌面电脑的类似设置不同，不能重置单个文件类型默认值。</span><span class="sxs-lookup"><span data-stu-id="a6d97-225">Unlike the similar setting on desktop PCs, you can't reset individual file type defaults.</span></span>

### <span data-ttu-id="a6d97-226">Office Web 应用</span><span class="sxs-lookup"><span data-stu-id="a6d97-226">Office web app</span></span>

<span data-ttu-id="a6d97-227">Office Web 应用已添加到"开始"菜单中的"所有应用程序"列表中。</span><span class="sxs-lookup"><span data-stu-id="a6d97-227">The Office web app has been added to the "All apps" list in the Start menu.</span></span> <span data-ttu-id="a6d97-228">还可以将此 Web 应用固定到"开始"页面或将其卸载。</span><span class="sxs-lookup"><span data-stu-id="a6d97-228">This web app can also be pinned to Start or uninstalled.</span></span> <span data-ttu-id="a6d97-229">由于这是一个 Web 应用，因此其功能与通过访问体验完全匹配 https://www.office.com 。</span><span class="sxs-lookup"><span data-stu-id="a6d97-229">Because this is a web app, its functionality matches exactly what you'd experience by visiting https://www.office.com.</span></span> <span data-ttu-id="a6d97-230">仅在 HoloLens 2 具有活动的 Internet 连接时，Office Web 应用功能才可用。</span><span class="sxs-lookup"><span data-stu-id="a6d97-230">Office web app functionality is only available when your HoloLens 2 has an active internet connection.</span></span>

### <span data-ttu-id="a6d97-231">轻扫以键入</span><span class="sxs-lookup"><span data-stu-id="a6d97-231">Swipe to type</span></span>

<span data-ttu-id="a6d97-232">一些客户发现通过轻扫要键入的单词的形状，在虚拟键盘上"键入"速度更快，我们正在预览全息键盘的此功能。</span><span class="sxs-lookup"><span data-stu-id="a6d97-232">Some customers find it faster to "type" on virtual keyboards by swiping the shape of the word they intend to type, and we're previewing this feature for the holographic keyboard.</span></span> <span data-ttu-id="a6d97-233">通过通过全息键盘的平面传递手指的尖角，轻扫该单词的形状，然后从键盘平面撤消手指的尖角，可以一次轻扫一个单词。</span><span class="sxs-lookup"><span data-stu-id="a6d97-233">You can swipe one word at a time by passing the tip of your finger through the plane of the holographic keyboard, swiping the shape of the word, and then withdrawing the tip of your finger from the plane of the keyboard.</span></span> <span data-ttu-id="a6d97-234">通过从键盘删除单词之间的手指，无需按空格键，即可轻扫后续单词。</span><span class="sxs-lookup"><span data-stu-id="a6d97-234">You can swipe follow-up words without needing to press the spacebar by removing your finger from the keyboard between words.</span></span> <span data-ttu-id="a6d97-235">如果你看到手指在键盘上移动后看到轻扫轨迹，你将知道该功能正在工作。</span><span class="sxs-lookup"><span data-stu-id="a6d97-235">You will know the feature is working if you see a swipe trail following your finger's movement on the keyboard.</span></span>

<span data-ttu-id="a6d97-236">请注意，此功能可能很难使用和掌握，因为全息键盘的性质，与移动电话显示屏不同，你无法抵御手指 (因此) 。</span><span class="sxs-lookup"><span data-stu-id="a6d97-236">Please note, this feature can be tricky to use and master because of the nature of a holographic keyboard where you don't feel resistance against your finger (unlike a mobile phone display).</span></span> <span data-ttu-id="a6d97-237">我们正在评估此功能以公开发布，因此您的反馈非常重要;无论你发现此功能有用还是有反馈反馈，请通过反馈中心 [告诉我们](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="a6d97-237">We are evaluating this feature for public release, so your feedback is important; whether you find the feature useful or you have constructive feedback, please let us know via [Feedback Hub](hololens-feedback.md).</span></span>

### <span data-ttu-id="a6d97-238">USB-C 外部麦克风支持</span><span class="sxs-lookup"><span data-stu-id="a6d97-238">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6d97-239">插入 USB **麦克风不会自动将其设置为输入设备**。</span><span class="sxs-lookup"><span data-stu-id="a6d97-239">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="a6d97-240">在插入一组 USB-C 耳机时，用户将观察到耳机的音频将自动重定向到耳机，但 HoloLens 操作系统会将内部麦克风阵列设置为高于任何其他输入设备的优先级。</span><span class="sxs-lookup"><span data-stu-id="a6d97-240">When plugging in a set of USB-C headphones users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> **<span data-ttu-id="a6d97-241">若要使用 USB-C 麦克风，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="a6d97-241">In order to use a USB-C microphone follow the steps below.</span></span>**

<span data-ttu-id="a6d97-242">用户现在可以使用"声音设置"面板选择 USB-C **连接的外部** 麦克风。</span><span class="sxs-lookup"><span data-stu-id="a6d97-242">Users can now select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="a6d97-243">这允许用户在录制和应用使用自己的已连接麦克风，但使用 USB。</span><span class="sxs-lookup"><span data-stu-id="a6d97-243">This allows users to use their own microphone connected but USB in recording and apps.</span></span> <span data-ttu-id="a6d97-244">USB-C 麦克风易于启用和使用。</span><span class="sxs-lookup"><span data-stu-id="a6d97-244">USB-C microphones are easy to enabled and use.</span></span>

<span data-ttu-id="a6d97-245">打开"**设置"** 应用，然后选择 **"系统**  ->  **声音"。**</span><span class="sxs-lookup"><span data-stu-id="a6d97-245">Open the **Settings** app and select **System** -> **Sound**.</span></span>

![声音设置](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="a6d97-247">若要将外部麦克风与 **远程协助**一同使用，用户需要单击"管理声音设备"超链接。</span><span class="sxs-lookup"><span data-stu-id="a6d97-247">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="a6d97-248">然后使用下拉列表将外部麦克风设置为"默认" **或** " **通信默认值"。**</span><span class="sxs-lookup"><span data-stu-id="a6d97-248">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="a6d97-249">选择 **"** 默认值"意味着外部麦克风将无处不在使用。</span><span class="sxs-lookup"><span data-stu-id="a6d97-249">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="a6d97-250">选择 **"** 通信默认值"意味着外部麦克风将用于远程协助和其他通信应用，但 HoloLens 麦克风阵列可能仍用于其他任务。</span><span class="sxs-lookup"><span data-stu-id="a6d97-250">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens Mic Array may still be used for other tasks.</span></span>

![管理声音设备](images/usbc-mic-2.png)

<br>

![设置麦克风默认值](images/usbc-mic-3.jpg)

#### <span data-ttu-id="a6d97-253">麦克风Bluetooth如何？</span><span class="sxs-lookup"><span data-stu-id="a6d97-253">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="a6d97-254">遗憾的是Bluetooth HoloLens 2 上目前仍不支持麦克风。</span><span class="sxs-lookup"><span data-stu-id="a6d97-254">Unfortunately Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

#### <span data-ttu-id="a6d97-255">USB-C 麦克风疑难解答</span><span class="sxs-lookup"><span data-stu-id="a6d97-255">Troubleshooting USB-C microphones</span></span>

<span data-ttu-id="a6d97-256">请注意，某些 USB-C 麦克风错误地将自己报告为 *麦克风和扬声器* 。</span><span class="sxs-lookup"><span data-stu-id="a6d97-256">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="a6d97-257">这是麦克风而不是 HoloLens 的问题。</span><span class="sxs-lookup"><span data-stu-id="a6d97-257">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="a6d97-258">将其中一个麦克风插入 HoloLens 时，可能会丢失声音。</span><span class="sxs-lookup"><span data-stu-id="a6d97-258">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="a6d97-259">幸运的是，有一个简单的解决方法。</span><span class="sxs-lookup"><span data-stu-id="a6d97-259">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="a6d97-260">在 **"设置**系统声音"中，将内置扬声器 (模拟功能音频) 设置为  ->  \*\*\*\*  ->  \*\*\*\*\*\*默认设备\*\*。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a6d97-260">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="a6d97-261">HoloLens 应记住此设置，即使麦克风稍后被删除并重新连接。</span><span class="sxs-lookup"><span data-stu-id="a6d97-261">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C 麦克风疑难解答](images/usbc-mic-4.png)

### <span data-ttu-id="a6d97-263">在展台模式下使用新的"设置"和"边缘"应用</span><span class="sxs-lookup"><span data-stu-id="a6d97-263">Use the new Settings and Edge apps in Kiosk modes</span></span>

<span data-ttu-id="a6d97-264">在展 [台中加入](hololens-kiosk.md)应用时，IT 管理员通常会将应用添加到展台，但使用应用用户模型 ID (AUMID) 。</span><span class="sxs-lookup"><span data-stu-id="a6d97-264">When including apps in in [Kiosks](hololens-kiosk.md), an IT Admin often adds the app to the Kiosk but using it's App User Model ID (AUMID).</span></span> <span data-ttu-id="a6d97-265">由于"设置"应用和 Microsoft Edge 应用都被视为新应用，并且与为这些应用使用 AUMID 的较旧应用展台需要更新以使用新的 AUMID 不同。</span><span class="sxs-lookup"><span data-stu-id="a6d97-265">Because both the Settings app and Microsoft Edge app are considered new apps and different that the older apps Kiosks that use AUMIDs for those apps will need to be updated to use the new AUMID.</span></span>

<span data-ttu-id="a6d97-266">修改展台以包含新应用时，我们建议在新的 AUMID 中添加并保留旧 AUMID。</span><span class="sxs-lookup"><span data-stu-id="a6d97-266">When modifying a Kiosk to include the new apps, we recommend adding in the new AUMID as well as leaving the old one.</span></span> <span data-ttu-id="a6d97-267">这将在用户更新操作系统时创建一个简单的转换，并且不需要接收新策略来继续像预期一样使用展台。</span><span class="sxs-lookup"><span data-stu-id="a6d97-267">This will create an easy transition when users update the OS and won't need to receive new policies to keep using the Kiosk as intended.</span></span>

| <span data-ttu-id="a6d97-268">应用</span><span class="sxs-lookup"><span data-stu-id="a6d97-268">App</span></span>                    | <span data-ttu-id="a6d97-269">AUMID</span><span class="sxs-lookup"><span data-stu-id="a6d97-269">AUMID</span></span>                                                  |
|------------------------|--------------------------------------------------------|
| <span data-ttu-id="a6d97-270">旧设置应用</span><span class="sxs-lookup"><span data-stu-id="a6d97-270">Old Settings App</span></span>       | <span data-ttu-id="a6d97-271">HolographicSystemSettings_cw5n1h2txyewy！应用</span><span class="sxs-lookup"><span data-stu-id="a6d97-271">HolographicSystemSettings_cw5n1h2txyewy!App</span></span>            |
| <span data-ttu-id="a6d97-272">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="a6d97-272">New Settings App</span></span>       | <span data-ttu-id="a6d97-273">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！应用</span><span class="sxs-lookup"><span data-stu-id="a6d97-273">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App</span></span> |
| <span data-ttu-id="a6d97-274">旧 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="a6d97-274">Old Microsoft Edge app</span></span> | <span data-ttu-id="a6d97-275">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span><span class="sxs-lookup"><span data-stu-id="a6d97-275">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span></span>    |
| <span data-ttu-id="a6d97-276">新的 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="a6d97-276">New Microsoft Edge app</span></span> | <span data-ttu-id="a6d97-277">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE</span><span class="sxs-lookup"><span data-stu-id="a6d97-277">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE</span></span>    |

### <span data-ttu-id="a6d97-278">用于处理故障的展台模式行为更改</span><span class="sxs-lookup"><span data-stu-id="a6d97-278">Kiosk mode behavior changes for handling of failures</span></span>

<span data-ttu-id="a6d97-279">在较旧的内部版本，如果设备具有展台配置（即全局分配的访问权限和 AAD 组成员身份的组合）。如果确定 AAD 组成员身份失败，用户将看到"开始"菜单中未显示[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)任何内容。</span><span class="sxs-lookup"><span data-stu-id="a6d97-279">In older builds, if a device had a kiosk configuration, which is a combination of both global assigned access and AAD group member assigned access, if determining AAD group membership failed, the user would see “[nothing shown in start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)” menu.</span></span>

<span data-ttu-id="a6d97-280">从 Windows 预览体验成员版本开始，展台体验将回退到全局展台配置 (如果存在，) AAD 组展台模式期间发生故障的情况。</span><span class="sxs-lookup"><span data-stu-id="a6d97-280">Starting in Windows Insider release, the kiosk experience will fallback to global kiosk configuration (if present) in case of failures during AAD group kiosk mode.</span></span>

### <span data-ttu-id="a6d97-281">通过"设置"应用配置回退诊断</span><span class="sxs-lookup"><span data-stu-id="a6d97-281">Configuring Fallback Diagnostics via Settings app</span></span>

<span data-ttu-id="a6d97-282">现在，在"设置"应用中，用户可以配置 [回退诊断的行为](hololens-diagnostic-logs.md)。</span><span class="sxs-lookup"><span data-stu-id="a6d97-282">Now in Settings App, a user can configure the behavior of [Fallback Diagnostics](hololens-diagnostic-logs.md).</span></span> <span data-ttu-id="a6d97-283">在"设置"应用中，**导航到**"隐私疑  ->  **难**解答"页以配置此设置。</span><span class="sxs-lookup"><span data-stu-id="a6d97-283">In the Settings app navigate to **Privacy** -> **Troubleshooting** page to configure this setting.</span></span>

> [!NOTE]
> <span data-ttu-id="a6d97-284">如果为设备配置了 MDM 策略，用户将不能覆盖该行为。</span><span class="sxs-lookup"><span data-stu-id="a6d97-284">If there is MDM policy configured for the device, user will not be able to override that behavior.</span></span>  






## <span data-ttu-id="a6d97-285">开始接收预览体验成员版本</span><span class="sxs-lookup"><span data-stu-id="a6d97-285">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="a6d97-286">如果最近尚未更新，请重启设备以更新状态并获取最新内部版本。</span><span class="sxs-lookup"><span data-stu-id="a6d97-286">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="a6d97-287">"重新启动设备"语音命令运行良好。</span><span class="sxs-lookup"><span data-stu-id="a6d97-287">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="a6d97-288">还可以选择"设置/Windows 预览体验计划"中的"重启"按钮。</span><span class="sxs-lookup"><span data-stu-id="a6d97-288">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="a6d97-289">后端有一个你可能会遇到的 Bug，这样你才能重新进入轨道。</span><span class="sxs-lookup"><span data-stu-id="a6d97-289">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="a6d97-290">在 HoloLens 2 设备上 **，转到&** Windows 预览  >  \*\*\*\*  >  **体验计划**"设置更新"，然后选择 **"开始使用"。**</span><span class="sxs-lookup"><span data-stu-id="a6d97-290">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="a6d97-291">链接你用于注册为 Windows 预览体验成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="a6d97-291">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="a6d97-292">Windows 预览体验成员现在迁移到频道。</span><span class="sxs-lookup"><span data-stu-id="a6d97-292">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="a6d97-293">快速**圈**将成为**开发人员频道**，慢圈将成为\*\*\*\*\*\*Beta**渠道，并且发布**预览圈将成为\*\*\*\*发布预览频道\*\*。</span><span class="sxs-lookup"><span data-stu-id="a6d97-293">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="a6d97-294">该映射如下所示：</span><span class="sxs-lookup"><span data-stu-id="a6d97-294">Here is what that mapping looks like:</span></span>

![Windows 预览体验成员频道说明](images/WindowsInsiderChannels.png)

<span data-ttu-id="a6d97-296">有关详细信息，请参阅 Windows 博客 [上的 Windows 预览](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 体验成员频道介绍。</span><span class="sxs-lookup"><span data-stu-id="a6d97-296">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="a6d97-297">然后，选择 **"Windows**的活动开发"，选择是希望接收 **开发人员** 频道还是 **Beta 渠道** 版本，并查看计划条款。</span><span class="sxs-lookup"><span data-stu-id="a6d97-297">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="a6d97-298">选择 **">立即重启** 以完成。</span><span class="sxs-lookup"><span data-stu-id="a6d97-298">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="a6d97-299">重启设备后，转到"设置>更新& **安全>检查** 更新，获取最新内部版本。</span><span class="sxs-lookup"><span data-stu-id="a6d97-299">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="a6d97-300">FFU 下载和快速方向</span><span class="sxs-lookup"><span data-stu-id="a6d97-300">FFU download and flash directions</span></span>
<span data-ttu-id="a6d97-301">若要使用已签名的 Ffu 进行测试，首先需要先对设备进行飞行解锁，然后才能闪烁该已签名的 Ffu。</span><span class="sxs-lookup"><span data-stu-id="a6d97-301">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="a6d97-302">在电脑上：</span><span class="sxs-lookup"><span data-stu-id="a6d97-302">On PC:</span></span>

    1. <span data-ttu-id="a6d97-303">从 下载 ffu 到你的电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="a6d97-303">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="a6d97-304">从 Microsoft store (ARC) 高级恢复配套设备： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="a6d97-304">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="a6d97-305">On HoloLens - Flight Unlock： Open **Settings**  >  **Update & Security**Windows Insider  >  **Program** then sign up， reboot device.</span><span class="sxs-lookup"><span data-stu-id="a6d97-305">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="a6d97-306">Flash FFU - 现在可以使用 ARC 对已进行飞行的 FFU 进行闪烁。</span><span class="sxs-lookup"><span data-stu-id="a6d97-306">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="a6d97-307">提供反馈并报告问题</span><span class="sxs-lookup"><span data-stu-id="a6d97-307">Provide feedback and report issues</span></span>

<span data-ttu-id="a6d97-308">请使用 [HoloLens](hololens-feedback.md) 上的"反馈中心"应用提供反馈并报告问题。</span><span class="sxs-lookup"><span data-stu-id="a6d97-308">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="a6d97-309">使用反馈中心可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。</span><span class="sxs-lookup"><span data-stu-id="a6d97-309">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="a6d97-310">应以相同方式报告与 HoloLens 的中文和日文版本有关的问题。</span><span class="sxs-lookup"><span data-stu-id="a6d97-310">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="a6d97-311">请务必接受询问您是否希望反馈中心访问"文档"文件夹的提示， (系统提示"是") 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a6d97-311">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="a6d97-312">开发人员注意事项</span><span class="sxs-lookup"><span data-stu-id="a6d97-312">Note for developers</span></span>

<span data-ttu-id="a6d97-313">欢迎并鼓励你尝试使用 HoloLens 预览体验成员版本开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="a6d97-313">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="a6d97-314">请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 以开始。</span><span class="sxs-lookup"><span data-stu-id="a6d97-314">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="a6d97-315">这些相同的说明与 HoloLens 的预览体验成员版本一致。</span><span class="sxs-lookup"><span data-stu-id="a6d97-315">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="a6d97-316">可以使用与 HoloLens Visual Studio相同的 Unity 版本和版本。</span><span class="sxs-lookup"><span data-stu-id="a6d97-316">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="a6d97-317">停止接收预览体验成员内部版本</span><span class="sxs-lookup"><span data-stu-id="a6d97-317">Stop receiving Insider builds</span></span>

<span data-ttu-id="a6d97-318">如果你不再希望接收 Windows 全息版的预览体验成员版本，你可以选择在 HoloLens 运行生产版本时退出，或者可以使用高级恢复助手[](hololens-recovery.md)将设备恢复到非预览体验成员版本的 Windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="a6d97-318">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="a6d97-319">存在一个已知问题，即手动重新安装新的预览版本后从 Insider Preview 版本取消注册的用户将遇到蓝屏。</span><span class="sxs-lookup"><span data-stu-id="a6d97-319">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="a6d97-320">之后，他们必须手动恢复其设备。</span><span class="sxs-lookup"><span data-stu-id="a6d97-320">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="a6d97-321">有关你是否受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。</span><span class="sxs-lookup"><span data-stu-id="a6d97-321">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="a6d97-322">若要验证 HoloLens 是否正在运行生产内部版本：</span><span class="sxs-lookup"><span data-stu-id="a6d97-322">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="a6d97-323">转到" **系统>设置>"，** 并查找内部版本编号。</span><span class="sxs-lookup"><span data-stu-id="a6d97-323">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="a6d97-324">[有关生产内部版本号，请参阅发行说明](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="a6d97-324">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="a6d97-325">若要选择退出预览体验成员版本：</span><span class="sxs-lookup"><span data-stu-id="a6d97-325">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="a6d97-326">在运行生产内部版本 HoloLens 上，转到"设置>更新& Windows 预览体验>计划"，**然后选择**"停止预览**体验成员版本"。**</span><span class="sxs-lookup"><span data-stu-id="a6d97-326">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="a6d97-327">按照说明选择退出设备。</span><span class="sxs-lookup"><span data-stu-id="a6d97-327">Follow the instructions to opt out your device.</span></span>
