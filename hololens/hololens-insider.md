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
ms.date: 1/13/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 5936f721c1279dce45fa3e92e160f10d880de207
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283193"
---
# <span data-ttu-id="39a61-103">Microsoft HoloLens 内部预览版</span><span class="sxs-lookup"><span data-stu-id="39a61-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="39a61-104">欢迎使用 HoloLens 的最新 Insider Preview 版本！</span><span class="sxs-lookup"><span data-stu-id="39a61-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="39a61-105">开始操作非常简单，并为[](hololens-insider.md#start-receiving-insider-builds)HoloLens 的下一个主要操作系统更新提供有价值的反馈。</span><span class="sxs-lookup"><span data-stu-id="39a61-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="39a61-106">Windows 预览体验成员发行说明</span><span class="sxs-lookup"><span data-stu-id="39a61-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="39a61-107">我们希望再次开始向 Windows 预览体验成员提供新功能。</span><span class="sxs-lookup"><span data-stu-id="39a61-107">We are excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="39a61-108">我们将测试到开发人员频道获取最新更新。</span><span class="sxs-lookup"><span data-stu-id="39a61-108">We will be flighting to the Dev Channel for the latest updates.</span></span> <span data-ttu-id="39a61-109">我们将继续更新此页面，因为我们向 Windows 预览体验成员版本添加更多功能和更新。</span><span class="sxs-lookup"><span data-stu-id="39a61-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span>  <span data-ttu-id="39a61-110">感到兴奋并准备好将这些更新融合到你的现实中。</span><span class="sxs-lookup"><span data-stu-id="39a61-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="39a61-111">功能名称</span><span class="sxs-lookup"><span data-stu-id="39a61-111">Feature Name</span></span>                                              | <span data-ttu-id="39a61-112">简短说明</span><span class="sxs-lookup"><span data-stu-id="39a61-112">Short description</span></span>                                                                      | <span data-ttu-id="39a61-113">在内部版本可用</span><span class="sxs-lookup"><span data-stu-id="39a61-113">Available in build</span></span> |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [<span data-ttu-id="39a61-114">新版 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="39a61-114">New Microsoft Edge</span></span>](#introducing-the-new-microsoft-edge) | <span data-ttu-id="39a61-115">新的基于 Chromium 的 Microsoft Edge 现在可用于 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="39a61-115">The new, Chromium-based Microsoft Edge is now available for HoloLens 2</span></span>                         | <span data-ttu-id="39a61-116">20279.1006</span><span class="sxs-lookup"><span data-stu-id="39a61-116">20279.1006</span></span> |
| [<span data-ttu-id="39a61-117">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="39a61-117">New Settings app</span></span>](#new-settings-app)                     | <span data-ttu-id="39a61-118">旧"设置"应用将替换为具有新功能和设置的更新版本</span><span class="sxs-lookup"><span data-stu-id="39a61-118">The legacy Settings app is being replaced by an updated version with new features and settings</span></span> | <span data-ttu-id="39a61-119">20279.1006</span><span class="sxs-lookup"><span data-stu-id="39a61-119">20279.1006</span></span> |
| [<span data-ttu-id="39a61-120">默认应用选取器</span><span class="sxs-lookup"><span data-stu-id="39a61-120">Default app picker</span></span>](#default-app-picker)                 | <span data-ttu-id="39a61-121">选择应针对每个文件或链接类型启动的应用</span><span class="sxs-lookup"><span data-stu-id="39a61-121">Choose which app should launch for each file or link type</span></span>                                      | <span data-ttu-id="39a61-122">20279.1006</span><span class="sxs-lookup"><span data-stu-id="39a61-122">20279.1006</span></span> |
| [<span data-ttu-id="39a61-123">Office Web 应用</span><span class="sxs-lookup"><span data-stu-id="39a61-123">Office web app</span></span>](#office-web-app)                         | <span data-ttu-id="39a61-124">Office Web 应用的快捷方式现在列在"所有应用"中</span><span class="sxs-lookup"><span data-stu-id="39a61-124">A shortcut to the Office web app is now listed in "All apps"</span></span>                                   | <span data-ttu-id="39a61-125">20279.1006</span><span class="sxs-lookup"><span data-stu-id="39a61-125">20279.1006</span></span> |
| [<span data-ttu-id="39a61-126">轻扫以键入</span><span class="sxs-lookup"><span data-stu-id="39a61-126">Swipe to type</span></span>](#swipe-to-type)                           | <span data-ttu-id="39a61-127">使用手指尖在全息键盘上"轻扫"字词</span><span class="sxs-lookup"><span data-stu-id="39a61-127">Use the tip of your finger to "swipe" words on the holographic keyboard</span></span>                        | <span data-ttu-id="39a61-128">20279.1006</span><span class="sxs-lookup"><span data-stu-id="39a61-128">20279.1006</span></span> |
| [<span data-ttu-id="39a61-129">USB-C 外部麦克风支持</span><span class="sxs-lookup"><span data-stu-id="39a61-129">USB-C External Microphone Support</span></span>](#usb-c-external-microphone-support) | <span data-ttu-id="39a61-130">将 USB-C 麦克风用于应用和/或远程协助。</span><span class="sxs-lookup"><span data-stu-id="39a61-130">Use USB-C microphones for apps and / or Remote Assist.</span></span>| <span data-ttu-id="39a61-131">20279.1006</span><span class="sxs-lookup"><span data-stu-id="39a61-131">20279.1006</span></span> |
| [<span data-ttu-id="39a61-132">展台模式下新应用的新 AUMID</span><span class="sxs-lookup"><span data-stu-id="39a61-132">New AUMIDs for new apps in Kiosk mode</span></span>](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | <span data-ttu-id="39a61-133">新设置和边缘应用的 AUMID</span><span class="sxs-lookup"><span data-stu-id="39a61-133">AUMIDs for new Settings and Edge apps</span></span> | <span data-ttu-id="39a61-134">20279.1006</span><span class="sxs-lookup"><span data-stu-id="39a61-134">20279.1006</span></span> |
| [<span data-ttu-id="39a61-135">改进的展台模式故障帮助</span><span class="sxs-lookup"><span data-stu-id="39a61-135">Improved Kiosk mode failure handing</span></span>](#kiosk-mode-behavior-changes-for-handling-of-failures) | <span data-ttu-id="39a61-136">展台模式在空的"开始"菜单之前查找全局分配的访问权限。</span><span class="sxs-lookup"><span data-stu-id="39a61-136">Kiosk mode looks for Global Assigned Access before empty start menu.</span></span> | <span data-ttu-id="39a61-137">20279.1006</span><span class="sxs-lookup"><span data-stu-id="39a61-137">20279.1006</span></span> |
| [<span data-ttu-id="39a61-138">配置回退诊断</span><span class="sxs-lookup"><span data-stu-id="39a61-138">Configure Fallback Diagnostics</span></span>](#configuring-fallback-diagnostics-via-settings-app) | <span data-ttu-id="39a61-139">在"设置"应用中设置回退诊断行为</span><span class="sxs-lookup"><span data-stu-id="39a61-139">Setting Fallback Diagnostic Behavior in Settings App</span></span> | <span data-ttu-id="39a61-140">20279.1006</span><span class="sxs-lookup"><span data-stu-id="39a61-140">20279.1006</span></span> |

### <span data-ttu-id="39a61-141">引入新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="39a61-141">Introducing the new Microsoft Edge</span></span>

![旧 Microsoft Edge 徽标到新 Microsoft Edge 徽标的动画](images/new-edge.gif)

<span data-ttu-id="39a61-143">新的 Microsoft Edge [采用 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 开放源代码项目，为客户创建更好的兼容性，减少 Web 开发人员的 Web 碎片。</span><span class="sxs-lookup"><span data-stu-id="39a61-143">The new Microsoft Edge [adopts the Chromium open source project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) to create better compatibility for customers and less fragmentation of the web for web developers.</span></span>

<span data-ttu-id="39a61-144">借助此预览体验成员预览版，HoloLens 2 客户首次可以使用新的 Microsoft Edge！</span><span class="sxs-lookup"><span data-stu-id="39a61-144">With this Insider preview, the new Microsoft Edge is available to HoloLens 2 customers for the first time!</span></span> <span data-ttu-id="39a61-145">虽然新 Microsoft Edge 最终将替换 HoloLens 2 上的旧版 Microsoft Edge，但预览体验成员目前可以使用这两种浏览器。</span><span class="sxs-lookup"><span data-stu-id="39a61-145">While the new Microsoft Edge will eventually replace legacy Microsoft Edge on HoloLens 2, both browsers are currently available to Insiders.</span></span> <span data-ttu-id="39a61-146">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="39a61-146">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span></span>

![新 Microsoft Edge 屏幕截图](images/new-edge-ui.png)

#### <span data-ttu-id="39a61-148">启动新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="39a61-148">Launching the new Microsoft Edge</span></span>

<span data-ttu-id="39a61-149">预览体验成员可以使用两个版本的 Microsoft Edge：新的 Microsoft Edge 新 Microsoft Edge 图标 (由蓝绿色旋转图标) 表示，旧 Microsoft Edge (由白色 ![ ](images/new_edge_logo.png) "e"图标) 表示。</span><span class="sxs-lookup"><span data-stu-id="39a61-149">There are two versions of Microsoft Edge available to Insiders: the new Microsoft Edge ![new Microsoft Edge icon](images/new_edge_logo.png) (represented by a blue and green swirl icon) and legacy Microsoft Edge (represented by the white "e" icon).</span></span> <span data-ttu-id="39a61-150">新的 Microsoft Edge 已固定到"开始"菜单，并且会在激活 Web 链接时自动启动。</span><span class="sxs-lookup"><span data-stu-id="39a61-150">The new Microsoft Edge is pinned to the Start menu and will automatically launch when you activate a web link.</span></span> <span data-ttu-id="39a61-151">如果你想要还原为使用旧版 Microsoft Edge 作为默认 Web 浏览器，请参阅下面的说明 [重置默认应用](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="39a61-151">If you would like to revert to using legacy Microsoft Edge as your default web browser, see the instructions below for [resetting default apps](#default-app-picker).</span></span>

> [!NOTE]
> <span data-ttu-id="39a61-152">当你首次在 HoloLens 2 上启动新的 Microsoft Edge 时，你的设置和数据将导入旧版 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="39a61-152">When you first launch the new Microsoft Edge on HoloLens 2, your settings and data will be imported from legacy Microsoft Edge.</span></span> <span data-ttu-id="39a61-153">如果在启动新的 Microsoft Edge 后继续使用旧版 Microsoft Edge，则新数据将不会从旧版 Microsoft Edge 同步到新的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="39a61-153">If you continue to use legacy Microsoft Edge after launching the new Microsoft Edge, that new data will not be synced from legacy Microsoft Edge to the new Microsoft Edge.</span></span>

#### <span data-ttu-id="39a61-154">配置新 Microsoft Edge 的策略设置</span><span class="sxs-lookup"><span data-stu-id="39a61-154">Configuring policy settings for the new Microsoft Edge</span></span>

<span data-ttu-id="39a61-155">新的 Microsoft Edge 为 IT 管理员提供 HoloLens 2 上的一组比以前适用于旧版 Microsoft Edge 的更为广泛的浏览器策略。</span><span class="sxs-lookup"><span data-stu-id="39a61-155">The new Microsoft Edge offers IT admins a much broader set of browser policies on HoloLens 2 than were previously available with legacy Microsoft Edge.</span></span>

<span data-ttu-id="39a61-156">下面是一些有用的资源，用于了解有关管理新 Microsoft Edge 的策略设置更多信息：</span><span class="sxs-lookup"><span data-stu-id="39a61-156">Here are some helpful resources for learning more about managing policy settings for the new Microsoft Edge:</span></span>

- [<span data-ttu-id="39a61-157">使用 Microsoft Intune 配置 Microsoft Edge 策略设置</span><span class="sxs-lookup"><span data-stu-id="39a61-157">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [<span data-ttu-id="39a61-158">Microsoft Edge 旧版到 Microsoft Edge 策略映射</span><span class="sxs-lookup"><span data-stu-id="39a61-158">Microsoft Edge Legacy to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [<span data-ttu-id="39a61-159">Google Chrome 到 Microsoft Edge 策略映射</span><span class="sxs-lookup"><span data-stu-id="39a61-159">Google Chrome to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- <span data-ttu-id="39a61-160">[完整的 Microsoft Edge 企业版文档](https://docs.microsoft.com/deployedge/)</span><span class="sxs-lookup"><span data-stu-id="39a61-160">Full [Microsoft Edge Enterprise documentation](https://docs.microsoft.com/deployedge/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39a61-161">由于新的 Microsoft Edge 支持大量浏览器策略，团队无法保证每个新策略都适用于 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="39a61-161">Because of the volume of browser policies supported by the new Microsoft Edge, our team is unable to guarantee that each new policy works on HoloLens 2.</span></span> <span data-ttu-id="39a61-162">但是，我们已经测试并确认 HoloLens 2 上以前支持的每个旧 Microsoft Edge 策略的新 Microsoft Edge 等效项可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="39a61-162">However, we've tested and confirmed that the new Microsoft Edge equivalent of each legacy Microsoft Edge policy previously supported on HoloLens 2 work as expected.</span></span> <span data-ttu-id="39a61-163">请参阅 [Microsoft Edge 旧版到 Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 策略映射，查找与 HoloLens 2 一起使用的每个旧版 Microsoft Edge 浏览器策略的新 Microsoft Edge 等效项。</span><span class="sxs-lookup"><span data-stu-id="39a61-163">See [Microsoft Edge Legacy to Microsoft Edge policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) to find the new Microsoft Edge equivalent of each legacy Microsoft Edge browser policy you were using with HoloLens 2.</span></span>
>
> <span data-ttu-id="39a61-164">我们了解至少有两个新的 Microsoft Edge 策略 *将不能* 与 HoloLens 2 一起使用：</span><span class="sxs-lookup"><span data-stu-id="39a61-164">There are at least two new Microsoft Edge policies that we know *will not* work with HoloLens 2:</span></span>
> - <span data-ttu-id="39a61-165">EnterpriseModeSiteList</span><span class="sxs-lookup"><span data-stu-id="39a61-165">EnterpriseModeSiteList</span></span>
> - <span data-ttu-id="39a61-166">EnterpriseSiteListServiceURL</span><span class="sxs-lookup"><span data-stu-id="39a61-166">EnterpriseSiteListServiceURL</span></span>

#### <span data-ttu-id="39a61-167">HoloLens 2 上新 Microsoft Edge 的预计功能</span><span class="sxs-lookup"><span data-stu-id="39a61-167">What to expect from the new Microsoft Edge on HoloLens 2</span></span>

<span data-ttu-id="39a61-168">由于新的 Microsoft Edge 是具有新的 UWP 适配器层的本机 Win32 应用，允许它在仅 UWP 设备（如 HoloLens 2）上运行，因此某些功能可能不会立即可用。</span><span class="sxs-lookup"><span data-stu-id="39a61-168">Because the new Microsoft Edge is a native Win32 app with a new UWP adapter layer allowing it to run on UWP-only devices like HoloLens 2, some features may not be immediately available.</span></span> <span data-ttu-id="39a61-169">我们将支持未来几个月的新方案和功能，因此请查看此空间了解最新信息。</span><span class="sxs-lookup"><span data-stu-id="39a61-169">We'll be supporting new scenarios and features over the coming months, so please check this space for up-to-date information.</span></span>

**<span data-ttu-id="39a61-170">应用场景和功能应能正常工作：</span><span class="sxs-lookup"><span data-stu-id="39a61-170">Scenarios and features expected to work:</span></span>**
- <span data-ttu-id="39a61-171">首次运行体验、登录配置文件和同步</span><span class="sxs-lookup"><span data-stu-id="39a61-171">First-run experience, sign-in to profile, and sync</span></span>
- <span data-ttu-id="39a61-172">网站应按预期呈现和行为</span><span class="sxs-lookup"><span data-stu-id="39a61-172">Websites should render and behave as expected</span></span>
- <span data-ttu-id="39a61-173">大多数浏览器功能 (收藏夹、历史记录等) 应正常工作</span><span class="sxs-lookup"><span data-stu-id="39a61-173">Most browser functionality (Favorites, History, etc.) should work as expected</span></span>
- <span data-ttu-id="39a61-174">深色模式</span><span class="sxs-lookup"><span data-stu-id="39a61-174">Dark mode</span></span>
- <span data-ttu-id="39a61-175">将 Web 应用安装到设备</span><span class="sxs-lookup"><span data-stu-id="39a61-175">Installing web apps to the device</span></span>
- <span data-ttu-id="39a61-176">安装扩展 (请告诉我们，如果你使用的任何扩展在 HoloLens 2) </span><span class="sxs-lookup"><span data-stu-id="39a61-176">Installing extensions (please let us know if you use any extensions that don't work properly on HoloLens 2)</span></span>
- <span data-ttu-id="39a61-177">查看和标记 PDF</span><span class="sxs-lookup"><span data-stu-id="39a61-177">Viewing and marking up a PDF</span></span>
- <span data-ttu-id="39a61-178">单个浏览器窗口中的空间声音</span><span class="sxs-lookup"><span data-stu-id="39a61-178">Spatial sound from a single browser window</span></span>
- <span data-ttu-id="39a61-179">浏览器的自动和手动更新</span><span class="sxs-lookup"><span data-stu-id="39a61-179">Automatic and manual updating of the browser</span></span>
- <span data-ttu-id="39a61-180">使用"保存到 PDF"选项 (打印菜单中保存 PDF) </span><span class="sxs-lookup"><span data-stu-id="39a61-180">Saving a PDF from the Print menu (using "Save to PDF" option)</span></span>

**<span data-ttu-id="39a61-181">即将推出方案和功能：</span><span class="sxs-lookup"><span data-stu-id="39a61-181">Scenarios and features coming soon:</span></span>**
- <span data-ttu-id="39a61-182">WebXR 和 360 Viewer 扩展</span><span class="sxs-lookup"><span data-stu-id="39a61-182">WebXR and 360 Viewer extension</span></span>
- <span data-ttu-id="39a61-183">在环境中跨多个窗口浏览时，内容还原以更正窗口</span><span class="sxs-lookup"><span data-stu-id="39a61-183">Content restoration to correct window when browsing across multiple windows placed in your environment</span></span>
- <span data-ttu-id="39a61-184">通过浏览器通过视频、混合现实捕获或屏幕共享功能加入 Microsoft Teams (通过音频加入通话效果) </span><span class="sxs-lookup"><span data-stu-id="39a61-184">Joining a Microsoft Teams call via the browser with video, mixed reality capture, or screen-sharing (joining calls with audio works well)</span></span>

**<span data-ttu-id="39a61-185">无法工作的方案和功能：</span><span class="sxs-lookup"><span data-stu-id="39a61-185">Scenarios and features not expected to work:</span></span>**
- <span data-ttu-id="39a61-186">具有同时音频流的多个窗口的空间声音</span><span class="sxs-lookup"><span data-stu-id="39a61-186">Spatial sound from multiple windows with simultaneous audio streams</span></span>
- <span data-ttu-id="39a61-187">"查看它，说出它"</span><span class="sxs-lookup"><span data-stu-id="39a61-187">"See it, say it"</span></span>
- <span data-ttu-id="39a61-188">打印</span><span class="sxs-lookup"><span data-stu-id="39a61-188">Printing</span></span>

**<span data-ttu-id="39a61-189">热门浏览器问题：</span><span class="sxs-lookup"><span data-stu-id="39a61-189">Top known browser issues:</span></span>**
- <span data-ttu-id="39a61-190">重置设备将删除新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="39a61-190">Resetting your device will remove the new Microsoft Edge</span></span>
- <span data-ttu-id="39a61-191">全息键盘中的放大镜预览显示不正确的内容</span><span class="sxs-lookup"><span data-stu-id="39a61-191">The magnifier preview in the holographic keyboard shows incorrect content</span></span>

#### <span data-ttu-id="39a61-192">Microsoft Edge 预览体验成员频道</span><span class="sxs-lookup"><span data-stu-id="39a61-192">Microsoft Edge Insider channels</span></span>

<span data-ttu-id="39a61-193">Microsoft Edge 团队向 Edge 预览体验成员社区提供三个预览频道：Beta、Dev 和 Canary。</span><span class="sxs-lookup"><span data-stu-id="39a61-193">The Microsoft Edge team makes three preview channels available to the Edge Insider community: Beta, Dev, and Canary.</span></span> <span data-ttu-id="39a61-194">安装预览频道不会卸载 HoloLens 2 上发布的 Microsoft Edge 版本，并且可以同时安装多个。</span><span class="sxs-lookup"><span data-stu-id="39a61-194">Installing a preview channel doesn't uninstall the released version of Microsoft Edge on your HoloLens 2, and you can install more than one at the same time.</span></span> 

<span data-ttu-id="39a61-195">访问 [Microsoft Edge 预览体验成员主页](https://www.microsoftedgeinsider.com) ，详细了解 Edge 预览体验成员社区。</span><span class="sxs-lookup"><span data-stu-id="39a61-195">Visit the [Microsoft Edge Insider homepage](https://www.microsoftedgeinsider.com) to learn more about the Edge Insider community.</span></span> <span data-ttu-id="39a61-196">若要了解有关不同边缘预览体验成员频道和入门信息，请访问 Edge [预览体验成员下载页面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="39a61-196">To learn more about the different Edge Insider channels and get started, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>

> [!NOTE]
> <span data-ttu-id="39a61-197">在此适用于 HoloLens 2 的 Windows 预览体验成员预览体验期间，你设备上 Microsoft Edge 的版本可能高于某些 (或 Microsoft Edge 预览体验成员) 中提供的版本。</span><span class="sxs-lookup"><span data-stu-id="39a61-197">During this Windows Insider preview for HoloLens 2, the version of Microsoft Edge on your device may be higher than those available in some (or all) of the Microsoft Edge Insider channels.</span></span> <span data-ttu-id="39a61-198">这是为了确保专门针对 HoloLens 2 上的 Web 浏览器的新功能和修补程序尽快进入我们的 Windows 预览体验成员。</span><span class="sxs-lookup"><span data-stu-id="39a61-198">This is to ensure new features and fixes specifically targeting the web browser on HoloLens 2 are getting to our Windows Insiders as quickly as possible.</span></span> <span data-ttu-id="39a61-199">在公开发布下一个 Windows 更新后，Microsoft Edge 预览体验成员频道版本将超过 HoloLens 2 上的 Microsoft Edge 版本，并保持领先。</span><span class="sxs-lookup"><span data-stu-id="39a61-199">Shortly after the public release of the next Windows update, the Microsoft Edge Insider channel builds will surpass, and stay ahead of, the version of Microsoft Edge on your HoloLens 2.</span></span>

### <span data-ttu-id="39a61-200">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="39a61-200">New Settings app</span></span>

<span data-ttu-id="39a61-201">在此版本中，我们将引入新版本的"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="39a61-201">With this release, we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="39a61-202">新的"设置"应用在以下方面包括 HoloLens 2 的新功能和扩展设置：声音、Power & 睡眠、网络 & Internet、应用、帐户、轻松使用等。</span><span class="sxs-lookup"><span data-stu-id="39a61-202">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="39a61-203">由于新的"设置"应用不同于旧式"设置"应用，因此更新时将删除之前围绕环境放置的任何"设置"窗口。</span><span class="sxs-lookup"><span data-stu-id="39a61-203">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

!["新建设置"应用主页](images/new-settings-app.png)

**<span data-ttu-id="39a61-205">新功能和设置</span><span class="sxs-lookup"><span data-stu-id="39a61-205">New features and settings</span></span>**
- <span data-ttu-id="39a61-206">设置搜索：使用关键字或设置名称从"设置"主页搜索设置</span><span class="sxs-lookup"><span data-stu-id="39a61-206">Settings search: search for settings from the Settings homepage using keywords or the setting's name</span></span>
- <span data-ttu-id="39a61-207">系统>声音：</span><span class="sxs-lookup"><span data-stu-id="39a61-207">System > Sound:</span></span>
  - <span data-ttu-id="39a61-208">输入和输出音频设备：独立选择输入和输出音频设备 (例如，通过 Bluetooth 耳机收听音频或使用 USB-C 麦克风进行音频输入) 。</span><span class="sxs-lookup"><span data-stu-id="39a61-208">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span> <span data-ttu-id="39a61-209">注意：Bluetooth HoloLens 2 不支持麦克风。</span><span class="sxs-lookup"><span data-stu-id="39a61-209">Note: Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="39a61-210">应用量：独立调整每个应用的音量</span><span class="sxs-lookup"><span data-stu-id="39a61-210">App volume: independently adjust the volume of each app</span></span>
- <span data-ttu-id="39a61-211">系统>电源&睡眠：选择设备在一段时间不活动后应何时进入睡眠状态</span><span class="sxs-lookup"><span data-stu-id="39a61-211">System > Power & sleep: choose when the device should go to sleep after a period of inactivity</span></span>
- <span data-ttu-id="39a61-212">系统>电池：手动启用节电模式或设置节电模式自动打开的电池阈值</span><span class="sxs-lookup"><span data-stu-id="39a61-212">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically</span></span>
- <span data-ttu-id="39a61-213">USB >设备：默认情况下可以禁用 USB 连接</span><span class="sxs-lookup"><span data-stu-id="39a61-213">Devices > USB: you can disable USB connections by default</span></span>
- <span data-ttu-id="39a61-214">Internet &网络：</span><span class="sxs-lookup"><span data-stu-id="39a61-214">Network & Internet:</span></span>
  - <span data-ttu-id="39a61-215">USB-C 以太网适配器现在将显示在 Internet &中</span><span class="sxs-lookup"><span data-stu-id="39a61-215">USB-C Ethernet adapters will now appear in Network & Internet</span></span>
  - <span data-ttu-id="39a61-216">USB-C 以太网适配器设置现已可用，包括其 IP 地址</span><span class="sxs-lookup"><span data-stu-id="39a61-216">USB-C Ethernet adapter settings are now available, including its IP address</span></span>
  - <span data-ttu-id="39a61-217">现在可以在 HoloLens 2 上启用飞行模式</span><span class="sxs-lookup"><span data-stu-id="39a61-217">You can now enable airplane mode on HoloLens 2</span></span>
- <span data-ttu-id="39a61-218">应用：你可以重置用于文件和链接类型的默认应用。</span><span class="sxs-lookup"><span data-stu-id="39a61-218">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="39a61-219">有关详细信息 [，请参阅](#default-app-picker) 默认应用选取器。</span><span class="sxs-lookup"><span data-stu-id="39a61-219">See [Default app picker](#default-app-picker) for more information.</span></span>
- <span data-ttu-id="39a61-220">其他用户>帐户：设备所有者可以添加用户、将标准用户升级到设备所有者、将设备所有者降级为标准用户以及删除用户。</span><span class="sxs-lookup"><span data-stu-id="39a61-220">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="39a61-221">轻松使用：更改文本大小和一些视觉效果</span><span class="sxs-lookup"><span data-stu-id="39a61-221">Ease of Access: change text size and some visual effects</span></span>

**<span data-ttu-id="39a61-222">已知问题</span><span class="sxs-lookup"><span data-stu-id="39a61-222">Known issues</span></span>**
- <span data-ttu-id="39a61-223">以前放置的"设置"窗口将被删除 (请参阅上面的) </span><span class="sxs-lookup"><span data-stu-id="39a61-223">Previously placed Settings windows will be removed (see note above)</span></span>
- <span data-ttu-id="39a61-224">访问"通知"页可能会崩溃"设置"应用 (调查) </span><span class="sxs-lookup"><span data-stu-id="39a61-224">Visiting the Notifications page may crash the Settings app (investigating)</span></span>
- <span data-ttu-id="39a61-225">以太网页面当前不会显示 (即将修复) </span><span class="sxs-lookup"><span data-stu-id="39a61-225">The Ethernet page currently doesn't show up (to be fixed soon)</span></span>
- <span data-ttu-id="39a61-226">新 Microsoft Edge 的电池使用情况可能不准确，因为其性质是 UWP 适配器层支持的 Win32 桌面应用程序， (预计) </span><span class="sxs-lookup"><span data-stu-id="39a61-226">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon)</span></span>

### <span data-ttu-id="39a61-227">默认应用选取器</span><span class="sxs-lookup"><span data-stu-id="39a61-227">Default app picker</span></span>

<span data-ttu-id="39a61-228">激活超链接或打开具有多个支持超链接的已安装应用的文件类型时，你将看到一个新窗口打开，提示你选择应处理文件或链接类型的已安装应用。</span><span class="sxs-lookup"><span data-stu-id="39a61-228">When you activate a hyperlink or open a file type with more than one installed app which supports it, you will see a new window open prompting you to select which installed app should handle the file or link type.</span></span> <span data-ttu-id="39a61-229">在此窗口中，还可以选择让所选应用处理文件或链接类型"一次"或"始终"。</span><span class="sxs-lookup"><span data-stu-id="39a61-229">In this window you can also choose to have the selected app handle the file or link type "Once" or "Always."</span></span>

![应用选取器窗口](images/default-app-picker.png)

<span data-ttu-id="39a61-231">如果你选择"始终"，但后来想要更改哪个应用处理特定文件或链接类型，可以在"设置"或"应用"中重置> **默认值**。</span><span class="sxs-lookup"><span data-stu-id="39a61-231">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span></span> <span data-ttu-id="39a61-232">滚动到页面底部，然后选择"文件类型的默认应用\*\*\*\*"和/或"链接类型的默认应用"下的"清除"按钮。</span><span class="sxs-lookup"><span data-stu-id="39a61-232">Scroll to the bottom of the page and select the **Clear** button under "Default apps for file types" and/or "Default apps for link types."</span></span> <span data-ttu-id="39a61-233">与桌面电脑的类似设置不同，不能重置单个文件类型默认值。</span><span class="sxs-lookup"><span data-stu-id="39a61-233">Unlike the similar setting on desktop PCs, you can't reset individual file type defaults.</span></span>

### <span data-ttu-id="39a61-234">Office Web 应用</span><span class="sxs-lookup"><span data-stu-id="39a61-234">Office web app</span></span>

<span data-ttu-id="39a61-235">Office Web 应用已添加到"开始"菜单中的"所有应用程序"列表中。</span><span class="sxs-lookup"><span data-stu-id="39a61-235">The Office web app has been added to the "All apps" list in the Start menu.</span></span> <span data-ttu-id="39a61-236">还可以将此 Web 应用固定到"开始"页面或将其卸载。</span><span class="sxs-lookup"><span data-stu-id="39a61-236">This web app can also be pinned to Start or uninstalled.</span></span> <span data-ttu-id="39a61-237">由于这是一个 Web 应用，因此其功能与通过访问体验完全匹配 https://www.office.com 。</span><span class="sxs-lookup"><span data-stu-id="39a61-237">Because this is a web app, its functionality matches exactly what you'd experience by visiting https://www.office.com.</span></span> <span data-ttu-id="39a61-238">仅在 HoloLens 2 具有活动的 Internet 连接时，Office Web 应用功能才可用。</span><span class="sxs-lookup"><span data-stu-id="39a61-238">Office web app functionality is only available when your HoloLens 2 has an active internet connection.</span></span>

### <span data-ttu-id="39a61-239">轻扫以键入</span><span class="sxs-lookup"><span data-stu-id="39a61-239">Swipe to type</span></span>

<span data-ttu-id="39a61-240">一些客户发现通过轻扫要键入的单词的形状，在虚拟键盘上"键入"速度更快，我们正在预览全息键盘的此功能。</span><span class="sxs-lookup"><span data-stu-id="39a61-240">Some customers find it faster to "type" on virtual keyboards by swiping the shape of the word they intend to type, and we're previewing this feature for the holographic keyboard.</span></span> <span data-ttu-id="39a61-241">通过通过全息键盘的平面传递手指的尖角，轻扫该单词的形状，然后从键盘平面撤消手指的尖角，可以一次轻扫一个单词。</span><span class="sxs-lookup"><span data-stu-id="39a61-241">You can swipe one word at a time by passing the tip of your finger through the plane of the holographic keyboard, swiping the shape of the word, and then withdrawing the tip of your finger from the plane of the keyboard.</span></span> <span data-ttu-id="39a61-242">通过从键盘删除单词之间的手指，无需按空格键，即可轻扫后续字词。</span><span class="sxs-lookup"><span data-stu-id="39a61-242">You can swipe follow-up words without needing to press the spacebar by removing your finger from the keyboard between words.</span></span> <span data-ttu-id="39a61-243">如果你看到手指在键盘上移动后看到轻扫轨迹，你将知道该功能正在工作。</span><span class="sxs-lookup"><span data-stu-id="39a61-243">You will know the feature is working if you see a swipe trail following your finger's movement on the keyboard.</span></span>

<span data-ttu-id="39a61-244">请注意，此功能可能很难使用和掌握，因为全息键盘的性质，与移动电话显示屏不同，你无法抵御手指 (因此) 。</span><span class="sxs-lookup"><span data-stu-id="39a61-244">Please note, this feature can be tricky to use and master because of the nature of a holographic keyboard where you don't feel resistance against your finger (unlike a mobile phone display).</span></span> <span data-ttu-id="39a61-245">我们正在评估此功能以公开发布，因此您的反馈非常重要;无论你发现此功能有用还是有反馈反馈，请通过反馈中心 [告诉我们](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="39a61-245">We are evaluating this feature for public release, so your feedback is important; whether you find the feature useful or you have constructive feedback, please let us know via [Feedback Hub](hololens-feedback.md).</span></span>

### <span data-ttu-id="39a61-246">USB-C 外部麦克风支持</span><span class="sxs-lookup"><span data-stu-id="39a61-246">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39a61-247">插入 USB **麦克风不会自动将其设置为输入设备**。</span><span class="sxs-lookup"><span data-stu-id="39a61-247">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="39a61-248">在插入一组 USB-C 耳机时，用户将观察到耳机的音频将自动重定向到耳机，但 HoloLens 操作系统会将内部麦克风阵列设置为高于任何其他输入设备的优先级。</span><span class="sxs-lookup"><span data-stu-id="39a61-248">When plugging in a set of USB-C headphones users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> **<span data-ttu-id="39a61-249">若要使用 USB-C 麦克风，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="39a61-249">In order to use a USB-C microphone follow the steps below.</span></span>**

<span data-ttu-id="39a61-250">用户可以使用"声音设置"面板选择连接 USB-C **的外部麦克风** 。</span><span class="sxs-lookup"><span data-stu-id="39a61-250">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="39a61-251">USB-C 麦克风可用于呼叫、录制等。</span><span class="sxs-lookup"><span data-stu-id="39a61-251">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="39a61-252">打开"**设置"** 应用，然后选择 **"系统**  ->  **声音"。**</span><span class="sxs-lookup"><span data-stu-id="39a61-252">Open the **Settings** app and select **System** -> **Sound**.</span></span>

![声音设置](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="39a61-254">若要将外部麦克风与 **远程协助**一同使用，用户需要单击"管理声音设备"超链接。</span><span class="sxs-lookup"><span data-stu-id="39a61-254">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="39a61-255">然后使用下拉列表将外部麦克风设置为"默认" **或** " **通信默认值"。**</span><span class="sxs-lookup"><span data-stu-id="39a61-255">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="39a61-256">选择 **"** 默认值"意味着外部麦克风将无处不在使用。</span><span class="sxs-lookup"><span data-stu-id="39a61-256">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="39a61-257">选择 **"** 通信默认值"意味着外部麦克风将用于远程协助和其他通信应用，但 HoloLens 麦克风阵列可能仍用于其他任务。</span><span class="sxs-lookup"><span data-stu-id="39a61-257">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![管理声音设备](images/usbc-mic-2.png)

<br>

![设置麦克风默认值](images/usbc-mic-3.jpg)

#### <span data-ttu-id="39a61-260">麦克风Bluetooth如何？</span><span class="sxs-lookup"><span data-stu-id="39a61-260">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="39a61-261">遗憾的是Bluetooth HoloLens 2 上目前仍不支持麦克风。</span><span class="sxs-lookup"><span data-stu-id="39a61-261">Unfortunately Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

#### <span data-ttu-id="39a61-262">USB-C 麦克风疑难解答</span><span class="sxs-lookup"><span data-stu-id="39a61-262">Troubleshooting USB-C microphones</span></span>

<span data-ttu-id="39a61-263">请注意，某些 USB-C 麦克风错误地将自己报告为 *麦克风和扬声器* 。</span><span class="sxs-lookup"><span data-stu-id="39a61-263">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="39a61-264">这是麦克风的问题，而不是 HoloLens 的问题。</span><span class="sxs-lookup"><span data-stu-id="39a61-264">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="39a61-265">将其中一个麦克风插入 HoloLens 时，声音可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="39a61-265">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="39a61-266">幸运的是，有一个简单的解决方法。</span><span class="sxs-lookup"><span data-stu-id="39a61-266">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="39a61-267">在 **"设置**系统声音"中，将内置扬声器 (模拟功能音频) 设置为  ->  \*\*\*\*  ->  \*\*\*\*\*\*默认设备\*\*。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="39a61-267">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="39a61-268">HoloLens 应记住此设置，即使麦克风稍后被删除并重新连接。</span><span class="sxs-lookup"><span data-stu-id="39a61-268">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C 麦克风疑难解答](images/usbc-mic-4.png)

### <span data-ttu-id="39a61-270">在展台模式下使用新的"设置"和"边缘"应用</span><span class="sxs-lookup"><span data-stu-id="39a61-270">Use the new Settings and Edge apps in Kiosk modes</span></span>

<span data-ttu-id="39a61-271">在展 [台中加入](hololens-kiosk.md)应用时，IT 管理员通常会将应用添加到展台，但使用应用用户模型 ID (AUMID) 。</span><span class="sxs-lookup"><span data-stu-id="39a61-271">When including apps in in [Kiosks](hololens-kiosk.md), an IT Admin often adds the app to the Kiosk but using it's App User Model ID (AUMID).</span></span> <span data-ttu-id="39a61-272">由于"设置"应用和 Microsoft Edge 应用都被视为新应用，并且与为这些应用使用 AUMID 的较旧应用展台需要更新以使用新的 AUMID 不同。</span><span class="sxs-lookup"><span data-stu-id="39a61-272">Because both the Settings app and Microsoft Edge app are considered new apps and different that the older apps Kiosks that use AUMIDs for those apps will need to be updated to use the new AUMID.</span></span>

<span data-ttu-id="39a61-273">修改展台以包含新应用时，我们建议在新的 AUMID 中添加并保留旧 AUMID。</span><span class="sxs-lookup"><span data-stu-id="39a61-273">When modifying a Kiosk to include the new apps, we recommend adding in the new AUMID as well as leaving the old one.</span></span> <span data-ttu-id="39a61-274">这将在用户更新操作系统时创建一个简单的转换，并且不需要接收新策略来继续像预期一样使用展台。</span><span class="sxs-lookup"><span data-stu-id="39a61-274">This will create an easy transition when users update the OS and won't need to receive new policies to keep using the Kiosk as intended.</span></span>

| <span data-ttu-id="39a61-275">应用</span><span class="sxs-lookup"><span data-stu-id="39a61-275">App</span></span>                    | <span data-ttu-id="39a61-276">AUMID</span><span class="sxs-lookup"><span data-stu-id="39a61-276">AUMID</span></span>                                                  |
|------------------------|--------------------------------------------------------|
| <span data-ttu-id="39a61-277">旧设置应用</span><span class="sxs-lookup"><span data-stu-id="39a61-277">Old Settings App</span></span>       | <span data-ttu-id="39a61-278">HolographicSystemSettings_cw5n1h2txyewy！应用</span><span class="sxs-lookup"><span data-stu-id="39a61-278">HolographicSystemSettings_cw5n1h2txyewy!App</span></span>            |
| <span data-ttu-id="39a61-279">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="39a61-279">New Settings App</span></span>       | <span data-ttu-id="39a61-280">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！应用</span><span class="sxs-lookup"><span data-stu-id="39a61-280">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App</span></span> |
| <span data-ttu-id="39a61-281">旧 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="39a61-281">Old Microsoft Edge app</span></span> | <span data-ttu-id="39a61-282">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span><span class="sxs-lookup"><span data-stu-id="39a61-282">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span></span>    |
| <span data-ttu-id="39a61-283">新的 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="39a61-283">New Microsoft Edge app</span></span> | <span data-ttu-id="39a61-284">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE</span><span class="sxs-lookup"><span data-stu-id="39a61-284">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE</span></span>    |

### <span data-ttu-id="39a61-285">用于处理故障的展台模式行为更改</span><span class="sxs-lookup"><span data-stu-id="39a61-285">Kiosk mode behavior changes for handling of failures</span></span>

<span data-ttu-id="39a61-286">在较旧的内部版本，如果设备具有展台配置（即全局分配的访问权限和 AAD 组成员身份的组合）。如果确定 AAD 组成员身份失败，用户将看到"开始"菜单中未显示[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)任何内容。</span><span class="sxs-lookup"><span data-stu-id="39a61-286">In older builds, if a device had a kiosk configuration, which is a combination of both global assigned access and AAD group member assigned access, if determining AAD group membership failed, the user would see “[nothing shown in start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)” menu.</span></span>

<span data-ttu-id="39a61-287">从 Windows 预览体验成员版本开始，展台体验将回退到全局展台配置 (如果存在) AAD 组展台模式期间发生故障的情况。</span><span class="sxs-lookup"><span data-stu-id="39a61-287">Starting in Windows Insider release, the kiosk experience will fallback to global kiosk configuration (if present) in case of failures during AAD group kiosk mode.</span></span>

### <span data-ttu-id="39a61-288">通过"设置"应用配置回退诊断</span><span class="sxs-lookup"><span data-stu-id="39a61-288">Configuring Fallback Diagnostics via Settings app</span></span>

<span data-ttu-id="39a61-289">现在，在"设置"应用中，用户可以配置 [回退诊断的行为](hololens-diagnostic-logs.md)。</span><span class="sxs-lookup"><span data-stu-id="39a61-289">Now in Settings App, a user can configure the behavior of [Fallback Diagnostics](hololens-diagnostic-logs.md).</span></span> <span data-ttu-id="39a61-290">在"设置"应用中，**导航到**"隐私疑  ->  **难**解答"页以配置此设置。</span><span class="sxs-lookup"><span data-stu-id="39a61-290">In the Settings app navigate to **Privacy** -> **Troubleshooting** page to configure this setting.</span></span>

> [!NOTE]
> <span data-ttu-id="39a61-291">如果有为设备配置的 MDM 策略，用户将不能覆盖该行为。</span><span class="sxs-lookup"><span data-stu-id="39a61-291">If there is MDM policy configured for the device, user will not be able to override that behavior.</span></span>  






## <span data-ttu-id="39a61-292">开始接收预览体验成员版本</span><span class="sxs-lookup"><span data-stu-id="39a61-292">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="39a61-293">如果最近尚未更新，请重启设备以更新状态并获取最新内部版本。</span><span class="sxs-lookup"><span data-stu-id="39a61-293">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="39a61-294">"重新启动设备"语音命令运行正常。</span><span class="sxs-lookup"><span data-stu-id="39a61-294">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="39a61-295">还可以选择"设置/Windows 预览体验计划"中的"重启"按钮。</span><span class="sxs-lookup"><span data-stu-id="39a61-295">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="39a61-296">后端有一个你可能会遇到的 Bug，这样你才能重新进入轨道。</span><span class="sxs-lookup"><span data-stu-id="39a61-296">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="39a61-297">在 HoloLens 2 设备上 **，转到&** Windows 预览  >  \*\*\*\*  >  **体验计划**"设置更新"，然后选择 **"开始使用"。**</span><span class="sxs-lookup"><span data-stu-id="39a61-297">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="39a61-298">链接你用于注册为 Windows 预览体验成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="39a61-298">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="39a61-299">Windows 预览体验成员现在迁移到频道。</span><span class="sxs-lookup"><span data-stu-id="39a61-299">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="39a61-300">快速**圈**将变为**开发人员频道**，慢圈将成为\*\*\*\* **Beta**渠道，而发布预览圈将成为\*\*\*\*\*\*发布预览频道\*\*。</span><span class="sxs-lookup"><span data-stu-id="39a61-300">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="39a61-301">该映射如下所示：</span><span class="sxs-lookup"><span data-stu-id="39a61-301">Here is what that mapping looks like:</span></span>

![Windows 预览体验成员频道说明](images/WindowsInsiderChannels.png)

<span data-ttu-id="39a61-303">有关详细信息，请参阅 Windows 博客 [上的 Windows 预览](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 体验成员频道介绍。</span><span class="sxs-lookup"><span data-stu-id="39a61-303">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="39a61-304">然后，选择 **"Windows**的活动开发"，选择是希望接收 **开发人员** 频道还是 **Beta 渠道** 版本，并查看计划条款。</span><span class="sxs-lookup"><span data-stu-id="39a61-304">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="39a61-305">选择 **">立即重启** 以完成。</span><span class="sxs-lookup"><span data-stu-id="39a61-305">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="39a61-306">重启设备后，转到"设置>更新& **安全>检查** 更新，获取最新内部版本。</span><span class="sxs-lookup"><span data-stu-id="39a61-306">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="39a61-307">FFU 下载和快速方向</span><span class="sxs-lookup"><span data-stu-id="39a61-307">FFU download and flash directions</span></span>
<span data-ttu-id="39a61-308">若要使用已签名的 Ffu 进行测试，首先需要先对设备进行解锁，然后才能闪烁已进行测试的已签名 ffu。</span><span class="sxs-lookup"><span data-stu-id="39a61-308">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="39a61-309">在电脑上：</span><span class="sxs-lookup"><span data-stu-id="39a61-309">On PC:</span></span>

    1. <span data-ttu-id="39a61-310">从 下载 ffu 到你的电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="39a61-310">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="39a61-311">从 Microsoft store (ARC) 高级恢复配套设备： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="39a61-311">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="39a61-312">在 HoloLens - Flight Unlock： Open **Settings**  >  **Update & Security**Windows Insider  >  **Program** then sign up， reboot device.</span><span class="sxs-lookup"><span data-stu-id="39a61-312">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="39a61-313">Flash FFU - 现在可以使用 ARC 对已进行飞行的 FFU 进行闪烁。</span><span class="sxs-lookup"><span data-stu-id="39a61-313">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="39a61-314">提供反馈并报告问题</span><span class="sxs-lookup"><span data-stu-id="39a61-314">Provide feedback and report issues</span></span>

<span data-ttu-id="39a61-315">请使用 [HoloLens](hololens-feedback.md) 上的"反馈中心"应用提供反馈并报告问题。</span><span class="sxs-lookup"><span data-stu-id="39a61-315">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="39a61-316">使用反馈中心可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。</span><span class="sxs-lookup"><span data-stu-id="39a61-316">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="39a61-317">应以相同方式报告与 HoloLens 的中文和日文版本有关的问题。</span><span class="sxs-lookup"><span data-stu-id="39a61-317">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="39a61-318">请务必接受询问您是否希望反馈中心访问"文档"文件夹的提示， (系统提示"是") 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="39a61-318">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="39a61-319">开发人员注意事项</span><span class="sxs-lookup"><span data-stu-id="39a61-319">Note for developers</span></span>

<span data-ttu-id="39a61-320">欢迎并鼓励你尝试使用 HoloLens 预览体验成员版本开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="39a61-320">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="39a61-321">请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 开始。</span><span class="sxs-lookup"><span data-stu-id="39a61-321">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="39a61-322">这些相同的说明与 HoloLens 的预览体验成员版本一致。</span><span class="sxs-lookup"><span data-stu-id="39a61-322">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="39a61-323">可以使用与 HoloLens Visual Studio相同的 Unity 版本和版本。</span><span class="sxs-lookup"><span data-stu-id="39a61-323">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="39a61-324">停止接收预览体验成员内部版本</span><span class="sxs-lookup"><span data-stu-id="39a61-324">Stop receiving Insider builds</span></span>

<span data-ttu-id="39a61-325">如果你不再希望接收 Windows 全息版的预览体验成员版本，你可以选择在 HoloLens 运行生产版本时退出，或者可以使用高级恢复助手[](hololens-recovery.md)将设备恢复到非预览体验成员版本的 Windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="39a61-325">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="39a61-326">存在一个已知问题，即手动重新安装新的预览版本后从 Insider Preview 版本取消注册的用户将遇到蓝屏。</span><span class="sxs-lookup"><span data-stu-id="39a61-326">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="39a61-327">之后，他们必须手动恢复其设备。</span><span class="sxs-lookup"><span data-stu-id="39a61-327">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="39a61-328">有关你是否受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。</span><span class="sxs-lookup"><span data-stu-id="39a61-328">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="39a61-329">若要验证 HoloLens 是否正在运行生产版本：</span><span class="sxs-lookup"><span data-stu-id="39a61-329">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="39a61-330">转到" **系统>设置>"，** 并查找内部版本编号。</span><span class="sxs-lookup"><span data-stu-id="39a61-330">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="39a61-331">[有关生产内部版本号，请参阅发行说明](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="39a61-331">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="39a61-332">若要选择退出预览体验成员版本：</span><span class="sxs-lookup"><span data-stu-id="39a61-332">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="39a61-333">在运行生产内部版本 HoloLens 上，转到"设置>更新& Windows 预览体验>计划"，**然后选择**"停止预览**体验成员版本"。**</span><span class="sxs-lookup"><span data-stu-id="39a61-333">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="39a61-334">按照说明选择退出设备。</span><span class="sxs-lookup"><span data-stu-id="39a61-334">Follow the instructions to opt out your device.</span></span>
