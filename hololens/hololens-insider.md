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
ms.openlocfilehash: 5da96d2838cbe1a02956a3e567c6ecf6da9d6b10
ms.sourcegitcommit: c93f23fe7c27dfa45fef300a4fc91aa811bc8126
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2021
ms.locfileid: "11269477"
---
# <span data-ttu-id="11016-103">Microsoft HoloLens 内部预览版</span><span class="sxs-lookup"><span data-stu-id="11016-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="11016-104">欢迎使用 HoloLens 的最新 Insider Preview 版本！</span><span class="sxs-lookup"><span data-stu-id="11016-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="11016-105">开始操作非常简单，并为[](hololens-insider.md#start-receiving-insider-builds)HoloLens 的下一个主要操作系统更新提供有价值的反馈。</span><span class="sxs-lookup"><span data-stu-id="11016-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="11016-106">Windows 预览体验成员发行说明</span><span class="sxs-lookup"><span data-stu-id="11016-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="11016-107">我们希望再次开始向 Windows 预览体验成员提供新功能。</span><span class="sxs-lookup"><span data-stu-id="11016-107">We are excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="11016-108">我们将测试到开发人员频道获取最新更新。</span><span class="sxs-lookup"><span data-stu-id="11016-108">We will be flighting to the Dev Channel for the latest updates.</span></span> <span data-ttu-id="11016-109">我们将继续更新此页面，因为我们向 Windows 预览体验成员版本添加更多功能和更新。</span><span class="sxs-lookup"><span data-stu-id="11016-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span>  <span data-ttu-id="11016-110">感到兴奋并准备好将这些更新融合到现实中。</span><span class="sxs-lookup"><span data-stu-id="11016-110">Get excited and ready to mix these updates into your reality.</span></span> 

| <span data-ttu-id="11016-111">功能名称</span><span class="sxs-lookup"><span data-stu-id="11016-111">Feature Name</span></span>                                              | <span data-ttu-id="11016-112">简短说明</span><span class="sxs-lookup"><span data-stu-id="11016-112">Short description</span></span>                                                                      | <span data-ttu-id="11016-113">在内部版本可用</span><span class="sxs-lookup"><span data-stu-id="11016-113">Available in build</span></span> |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [<span data-ttu-id="11016-114">新版 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="11016-114">New Microsoft Edge</span></span>](#introducing-the-new-microsoft-edge) | <span data-ttu-id="11016-115">新的基于 Chromium 的 Microsoft Edge 现在可用于 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="11016-115">The new, Chromium-based Microsoft Edge is now available for HoloLens 2</span></span>                         | <span data-ttu-id="11016-116">20279.1006</span><span class="sxs-lookup"><span data-stu-id="11016-116">20279.1006</span></span> |
| [<span data-ttu-id="11016-117">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="11016-117">New Settings app</span></span>](#new-settings-app)                     | <span data-ttu-id="11016-118">旧"设置"应用将替换为具有新功能和设置的更新版本</span><span class="sxs-lookup"><span data-stu-id="11016-118">The legacy Settings app is being replaced by an updated version with new features and settings</span></span> | <span data-ttu-id="11016-119">20279.1006</span><span class="sxs-lookup"><span data-stu-id="11016-119">20279.1006</span></span> |
| [<span data-ttu-id="11016-120">默认应用选取器</span><span class="sxs-lookup"><span data-stu-id="11016-120">Default app picker</span></span>](#default-app-picker)                 | <span data-ttu-id="11016-121">选择应针对每个文件或链接类型启动的应用</span><span class="sxs-lookup"><span data-stu-id="11016-121">Choose which app should launch for each file or link type</span></span>                                      | <span data-ttu-id="11016-122">20279.1006</span><span class="sxs-lookup"><span data-stu-id="11016-122">20279.1006</span></span> |
| [<span data-ttu-id="11016-123">Office Web 应用</span><span class="sxs-lookup"><span data-stu-id="11016-123">Office web app</span></span>](#office-web-app)                         | <span data-ttu-id="11016-124">Office Web 应用的快捷方式现在列在"所有应用"中</span><span class="sxs-lookup"><span data-stu-id="11016-124">A shortcut to the Office web app is now listed in "All apps"</span></span>                                   | <span data-ttu-id="11016-125">20279.1006</span><span class="sxs-lookup"><span data-stu-id="11016-125">20279.1006</span></span> |
| [<span data-ttu-id="11016-126">轻扫以键入</span><span class="sxs-lookup"><span data-stu-id="11016-126">Swipe to type</span></span>](#swipe-to-type)                           | <span data-ttu-id="11016-127">使用手指尖在全息键盘上"轻扫"字词</span><span class="sxs-lookup"><span data-stu-id="11016-127">Use the tip of your finger to "swipe" words on the holographic keyboard</span></span>                        | <span data-ttu-id="11016-128">20279.1006</span><span class="sxs-lookup"><span data-stu-id="11016-128">20279.1006</span></span> |

### <span data-ttu-id="11016-129">引入新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="11016-129">Introducing the new Microsoft Edge</span></span>

![旧 Microsoft Edge 徽标到新 Microsoft Edge 徽标的动画](images/new-edge.gif)

<span data-ttu-id="11016-131">新的 Microsoft Edge [采用 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 开放源代码项目，为客户创建更好的兼容性，减少 Web 开发人员的 Web 碎片。</span><span class="sxs-lookup"><span data-stu-id="11016-131">The new Microsoft Edge [adopts the Chromium open source project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) to create better compatibility for customers and less fragmentation of the web for web developers.</span></span> 

<span data-ttu-id="11016-132">通过此预览体验成员预览版，HoloLens 2 客户首次可以使用新的 Microsoft Edge！</span><span class="sxs-lookup"><span data-stu-id="11016-132">With this Insider preview, the new Microsoft Edge is available to HoloLens 2 customers for the first time!</span></span> <span data-ttu-id="11016-133">虽然新 Microsoft Edge 最终将替换 HoloLens 2 上的旧版 Microsoft Edge，但预览体验成员目前可以使用这两种浏览器。</span><span class="sxs-lookup"><span data-stu-id="11016-133">While the new Microsoft Edge will eventually replace legacy Microsoft Edge on HoloLens 2, both browsers are currently available to Insiders.</span></span> <span data-ttu-id="11016-134">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub.](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="11016-134">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span></span>

![新 Microsoft Edge 屏幕截图](images/new-edge-ui.png)

#### <span data-ttu-id="11016-136">启动新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="11016-136">Launching the new Microsoft Edge</span></span>

<span data-ttu-id="11016-137">预览体验成员可以使用两个版本的 Microsoft Edge：新的 Microsoft Edge 新 Microsoft Edge 图标 (由蓝绿色旋转图标) 表示，旧 Microsoft Edge (由白色 ![ "e"图标) 表示。 ](images/new_edge_logo.png)</span><span class="sxs-lookup"><span data-stu-id="11016-137">There are two versions of Microsoft Edge available to Insiders: the new Microsoft Edge ![new Microsoft Edge icon](images/new_edge_logo.png) (represented by a blue and green swirl icon) and the legacy Microsoft Edge (represented by the white "e" icon).</span></span> <span data-ttu-id="11016-138">新的 Microsoft Edge 固定到"开始"菜单，将在激活 Web 链接时自动启动。</span><span class="sxs-lookup"><span data-stu-id="11016-138">The new Microsoft Edge is pinned to the Start menu and will automatically launch when you activate a web link.</span></span> <span data-ttu-id="11016-139">如果你想要还原为使用旧版 Microsoft Edge 作为默认 Web 浏览器，请参阅下面的说明 [重置默认应用](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="11016-139">If you would like to revert to using legacy Microsoft Edge as your default web browser, see the instructions below for [resetting default apps](#default-app-picker).</span></span>

> [!NOTE]
> <span data-ttu-id="11016-140">当你首次在 HoloLens 2 上启动新的 Microsoft Edge 时，你的设置和数据将导入旧版 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="11016-140">When you first launch the new Microsoft Edge on HoloLens 2, your settings and data will be imported from legacy Microsoft Edge.</span></span> <span data-ttu-id="11016-141">如果在启动新的 Microsoft Edge 后继续使用旧版 Microsoft Edge，则新数据将不会从旧版 Microsoft Edge 同步到新的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="11016-141">If you continue to use legacy Microsoft Edge after launching the new Microsoft Edge, that new data will not be synced from legacy Microsoft Edge to the new Microsoft Edge.</span></span>

#### <span data-ttu-id="11016-142">配置新 Microsoft Edge 的策略设置</span><span class="sxs-lookup"><span data-stu-id="11016-142">Configuring policy settings for the new Microsoft Edge</span></span>

<span data-ttu-id="11016-143">新版 Microsoft Edge 在 HoloLens 2 上为 IT 专业人员提供了一组比以前适用于旧版 Microsoft Edge 的更为广泛的浏览器策略。</span><span class="sxs-lookup"><span data-stu-id="11016-143">The new Microsoft Edge offers IT Pros a much broader set of browser policies on HoloLens 2 than were previously available with legacy Microsoft Edge.</span></span> 

<span data-ttu-id="11016-144">下面是一些有用的资源，用于了解有关管理新 Microsoft Edge 的策略设置更多信息：</span><span class="sxs-lookup"><span data-stu-id="11016-144">Here are some helpful resources for learning more about managing policy settings for the new Microsoft Edge:</span></span>
- [<span data-ttu-id="11016-145">使用 Microsoft Intune 配置 Microsoft Edge 策略设置</span><span class="sxs-lookup"><span data-stu-id="11016-145">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [<span data-ttu-id="11016-146">Microsoft Edge 旧版到 Microsoft Edge 策略映射</span><span class="sxs-lookup"><span data-stu-id="11016-146">Microsoft Edge Legacy to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [<span data-ttu-id="11016-147">Google Chrome 到 Microsoft Edge 策略映射</span><span class="sxs-lookup"><span data-stu-id="11016-147">Google Chrome to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- <span data-ttu-id="11016-148">[完整的 Microsoft Edge 企业版文档](https://docs.microsoft.com/deployedge/)</span><span class="sxs-lookup"><span data-stu-id="11016-148">Full [Microsoft Edge Enterprise documentation](https://docs.microsoft.com/deployedge/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="11016-149">由于新的 Microsoft Edge 支持大量浏览器策略，因此团队无法保证每个新策略都适用于 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="11016-149">Because of the volume of browser policies supported by the new Microsoft Edge, our team is unable to guarantee that each new policy works on HoloLens 2.</span></span> <span data-ttu-id="11016-150">但是，我们已经测试并确认 HoloLens 2 上以前支持的每个旧 Microsoft Edge 策略的新 Microsoft Edge 等效项可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="11016-150">However, we've tested and confirmed that the new Microsoft Edge equivalent of each legacy Microsoft Edge policy previously supported on HoloLens 2 work as expected.</span></span> <span data-ttu-id="11016-151">请参阅 [Microsoft Edge 旧版到 Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 策略映射，查找与 HoloLens 2 一起使用的每个旧版 Microsoft Edge 浏览器策略的新 Microsoft Edge 等效项。</span><span class="sxs-lookup"><span data-stu-id="11016-151">See [Microsoft Edge Legacy to Microsoft Edge policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) to find the new Microsoft Edge equivalent of each legacy Microsoft Edge browser policy you were using with HoloLens 2.</span></span>
>
> <span data-ttu-id="11016-152">我们了解至少有两个新的 Microsoft Edge 策略将 *不能* 与 HoloLens 2 一起使用：</span><span class="sxs-lookup"><span data-stu-id="11016-152">There are at least two new Microsoft Edge policies that we know *will not* work with HoloLens 2:</span></span>
> - <span data-ttu-id="11016-153">EnterpriseModeSiteList</span><span class="sxs-lookup"><span data-stu-id="11016-153">EnterpriseModeSiteList</span></span>
> - <span data-ttu-id="11016-154">EnterpriseSiteListServiceURL</span><span class="sxs-lookup"><span data-stu-id="11016-154">EnterpriseSiteListServiceURL</span></span>

#### <span data-ttu-id="11016-155">HoloLens 2 上新 Microsoft Edge 的预计功能</span><span class="sxs-lookup"><span data-stu-id="11016-155">What to expect from the new Microsoft Edge on HoloLens 2</span></span>

<span data-ttu-id="11016-156">由于新的 Microsoft Edge 是具有新的 UWP 适配器层的本机 Win32 应用，允许它在仅 UWP 设备（如 HoloLens 2）上运行，因此某些功能可能不会立即可用。</span><span class="sxs-lookup"><span data-stu-id="11016-156">Because the new Microsoft Edge is a native Win32 app with a new UWP adapter layer allowing it to run on UWP-only devices like HoloLens 2, some features may not be immediately available.</span></span> <span data-ttu-id="11016-157">我们将支持未来几个月的新方案和功能，因此请查看此空间了解最新信息。</span><span class="sxs-lookup"><span data-stu-id="11016-157">We'll be supporting new scenarios and features over the coming months, so please check this space for up-to-date information.</span></span>

**<span data-ttu-id="11016-158">应用场景和功能应能正常工作：</span><span class="sxs-lookup"><span data-stu-id="11016-158">Scenarios and features expected to work:</span></span>**
- <span data-ttu-id="11016-159">首次运行体验、登录配置文件和同步</span><span class="sxs-lookup"><span data-stu-id="11016-159">First-run experience, sign-in to profile, and sync</span></span>
- <span data-ttu-id="11016-160">网站应按预期呈现和行为</span><span class="sxs-lookup"><span data-stu-id="11016-160">Websites should render and behave as expected</span></span>
- <span data-ttu-id="11016-161">大多数浏览器功能 (收藏夹、历史记录等) 应正常工作</span><span class="sxs-lookup"><span data-stu-id="11016-161">Most browser functionality (Favorites, History, etc.) should work as expected</span></span>
- <span data-ttu-id="11016-162">深色模式</span><span class="sxs-lookup"><span data-stu-id="11016-162">Dark mode</span></span>
- <span data-ttu-id="11016-163">将 Web 应用安装到设备</span><span class="sxs-lookup"><span data-stu-id="11016-163">Installing web apps to the device</span></span>
- <span data-ttu-id="11016-164">安装扩展 (请告诉我们，如果你使用的任何扩展在 HoloLens 2) </span><span class="sxs-lookup"><span data-stu-id="11016-164">Installing extensions (please let us know if you use any extensions that don't work properly on HoloLens 2)</span></span>
- <span data-ttu-id="11016-165">查看和标记 PDF</span><span class="sxs-lookup"><span data-stu-id="11016-165">Viewing and marking up a PDF</span></span>
- <span data-ttu-id="11016-166">单个浏览器窗口中的空间声音</span><span class="sxs-lookup"><span data-stu-id="11016-166">Spatial sound from a single browser window</span></span>
- <span data-ttu-id="11016-167">浏览器的自动和手动更新</span><span class="sxs-lookup"><span data-stu-id="11016-167">Automatic and manual updating of the browser</span></span>
- <span data-ttu-id="11016-168">使用"保存到 PDF"选项 (打印菜单中保存 PDF) </span><span class="sxs-lookup"><span data-stu-id="11016-168">Saving a PDF from the Print menu (using "Save to PDF" option)</span></span>

**<span data-ttu-id="11016-169">即将推出方案和功能：</span><span class="sxs-lookup"><span data-stu-id="11016-169">Scenarios and features coming soon:</span></span>**
- <span data-ttu-id="11016-170">WebXR 和 360 Viewer 扩展</span><span class="sxs-lookup"><span data-stu-id="11016-170">WebXR and 360 Viewer extension</span></span>
- <span data-ttu-id="11016-171">在环境中跨多个窗口浏览时，内容还原以更正窗口</span><span class="sxs-lookup"><span data-stu-id="11016-171">Content restoration to correct window when browsing across multiple windows placed in your environment</span></span>
- <span data-ttu-id="11016-172">具有同时音频流的多个窗口的空间声音</span><span class="sxs-lookup"><span data-stu-id="11016-172">Spatial sound for multiple windows with simultaneous audio streams</span></span>
- <span data-ttu-id="11016-173">通过浏览器通过视频、混合现实捕获或屏幕共享功能加入 Microsoft Teams (通过音频加入通话效果) </span><span class="sxs-lookup"><span data-stu-id="11016-173">Joining a Microsoft Teams call via the browser with video, mixed reality capture, or screen-sharing (joining calls with audio works well)</span></span>
- <span data-ttu-id="11016-174">"查看它，说出它"</span><span class="sxs-lookup"><span data-stu-id="11016-174">"See it, say it"</span></span>
- <span data-ttu-id="11016-175">打印</span><span class="sxs-lookup"><span data-stu-id="11016-175">Printing</span></span>

**<span data-ttu-id="11016-176">热门浏览器问题：</span><span class="sxs-lookup"><span data-stu-id="11016-176">Top known browser issues:</span></span>**
- <span data-ttu-id="11016-177">重置设备将删除新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="11016-177">Resetting your device will remove the new Microsoft Edge</span></span>
- <span data-ttu-id="11016-178">全息键盘中的放大镜预览显示不正确的内容</span><span class="sxs-lookup"><span data-stu-id="11016-178">The magnifier preview in the holographic keyboard shows incorrect content</span></span>

### <span data-ttu-id="11016-179">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="11016-179">New Settings app</span></span>

<span data-ttu-id="11016-180">在此版本中，我们将引入新版本的"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="11016-180">With this release, we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="11016-181">新的"设置"应用在以下方面包括 HoloLens 2 的新功能和扩展设置：声音、Power & 睡眠、网络 & Internet、应用、帐户、轻松使用等。</span><span class="sxs-lookup"><span data-stu-id="11016-181">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="11016-182">由于新的"设置"应用不同于旧式"设置"应用，因此更新时将删除之前围绕你的环境放置的任何"设置"窗口。</span><span class="sxs-lookup"><span data-stu-id="11016-182">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

!["新建设置"应用主页](images/new-settings-app.png)

**<span data-ttu-id="11016-184">新功能和设置</span><span class="sxs-lookup"><span data-stu-id="11016-184">New features and settings</span></span>**
- <span data-ttu-id="11016-185">设置搜索：使用关键字或设置名称从"设置"主页搜索设置</span><span class="sxs-lookup"><span data-stu-id="11016-185">Settings search: search for settings from the Settings homepage using keywords or the setting's name</span></span>
- <span data-ttu-id="11016-186">系统>声音：</span><span class="sxs-lookup"><span data-stu-id="11016-186">System > Sound:</span></span>
  - <span data-ttu-id="11016-187">输入和输出音频设备：独立选择输入和输出音频设备 (例如，通过 Bluetooth 耳机收听音频或使用 USB-C 麦克风进行音频输入) 。</span><span class="sxs-lookup"><span data-stu-id="11016-187">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span> <span data-ttu-id="11016-188">注意：Bluetooth HoloLens 2 不支持麦克风。</span><span class="sxs-lookup"><span data-stu-id="11016-188">Note: Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="11016-189">应用量：独立调整每个应用的音量</span><span class="sxs-lookup"><span data-stu-id="11016-189">App volume: independently adjust the volume of each app</span></span>
- <span data-ttu-id="11016-190">系统>电源&睡眠：选择设备在一段时间不活动后应何时进入睡眠状态</span><span class="sxs-lookup"><span data-stu-id="11016-190">System > Power & sleep: choose when the device should go to sleep after a period of inactivity</span></span>
- <span data-ttu-id="11016-191">系统>电池：手动启用节电模式或设置节电模式自动打开的电池阈值</span><span class="sxs-lookup"><span data-stu-id="11016-191">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically</span></span>
- <span data-ttu-id="11016-192">USB >设备：默认情况下可以禁用 USB 连接</span><span class="sxs-lookup"><span data-stu-id="11016-192">Devices > USB: you can disable USB connections by default</span></span>
- <span data-ttu-id="11016-193">Internet &网络：</span><span class="sxs-lookup"><span data-stu-id="11016-193">Network & Internet:</span></span>
  - <span data-ttu-id="11016-194">USB-C 以太网适配器现在将显示在网络和 Internet &中</span><span class="sxs-lookup"><span data-stu-id="11016-194">USB-C Ethernet adapters will now appear in Network & Internet</span></span>
  - <span data-ttu-id="11016-195">USB-C 以太网适配器设置现已可用，包括其 IP 地址</span><span class="sxs-lookup"><span data-stu-id="11016-195">USB-C Ethernet adapter settings are now available, including its IP address</span></span>
  - <span data-ttu-id="11016-196">现在可以在 HoloLens 2 上启用飞行模式</span><span class="sxs-lookup"><span data-stu-id="11016-196">You can now enable airplane mode on HoloLens 2</span></span>
- <span data-ttu-id="11016-197">应用：你可以重置用于文件和链接类型的默认应用。</span><span class="sxs-lookup"><span data-stu-id="11016-197">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="11016-198">有关详细信息 [，请参阅](#default-app-picker) 默认应用选取器。</span><span class="sxs-lookup"><span data-stu-id="11016-198">See [Default app picker](#default-app-picker) for more information.</span></span>
- <span data-ttu-id="11016-199">其他用户>的帐户：设备所有者可以添加用户、将标准用户升级到设备所有者、将设备所有者降级为标准用户以及删除用户。</span><span class="sxs-lookup"><span data-stu-id="11016-199">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="11016-200">轻松使用：更改文本大小和一些视觉效果</span><span class="sxs-lookup"><span data-stu-id="11016-200">Ease of Access: change text size and some visual effects</span></span>

**<span data-ttu-id="11016-201">已知问题</span><span class="sxs-lookup"><span data-stu-id="11016-201">Known issues</span></span>**
- <span data-ttu-id="11016-202">以前放置的"设置"窗口将被删除 (请参阅上面的) </span><span class="sxs-lookup"><span data-stu-id="11016-202">Previously placed Settings windows will be removed (see note above)</span></span>
- <span data-ttu-id="11016-203">访问"通知"页可能会崩溃"设置"应用 (调查) </span><span class="sxs-lookup"><span data-stu-id="11016-203">Visiting the Notifications page may crash the Settings app (investigating)</span></span>
- <span data-ttu-id="11016-204">以太网页面当前不会显示 (即将修复) </span><span class="sxs-lookup"><span data-stu-id="11016-204">The Ethernet page currently doesn't show up (to be fixed soon)</span></span>
- <span data-ttu-id="11016-205">新 Microsoft Edge 的电池使用情况可能不准确，因为其性质是 UWP 适配器层支持的 Win32 桌面应用程序， (预计) </span><span class="sxs-lookup"><span data-stu-id="11016-205">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon)</span></span>

### <span data-ttu-id="11016-206">默认应用选取器</span><span class="sxs-lookup"><span data-stu-id="11016-206">Default app picker</span></span>

<span data-ttu-id="11016-207">激活超链接或打开具有多个支持超链接的已安装应用的文件类型时，你将看到一个新窗口打开，提示你选择应处理文件或链接类型的已安装应用。</span><span class="sxs-lookup"><span data-stu-id="11016-207">When you activate a hyperlink or open a file type with more than one installed app which supports it, you will see a new window open prompting you to select which installed app should handle the file or link type.</span></span> <span data-ttu-id="11016-208">在此窗口中，还可以选择让所选应用处理文件或链接类型"一次"或"始终"。</span><span class="sxs-lookup"><span data-stu-id="11016-208">In this window you can also choose to have the selected app handle the file or link type "Once" or "Always."</span></span> 

![应用选取器窗口](images/default-app-picker.png)

<span data-ttu-id="11016-210">如果你选择"始终"，但后来想要更改哪个应用处理特定文件或链接类型，可以在"设置"或"应用"中重置> **默认值**。</span><span class="sxs-lookup"><span data-stu-id="11016-210">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span></span> <span data-ttu-id="11016-211">滚动到页面底部，然后选择"文件类型的默认应用\*\*\*\*"和/或"链接类型的默认应用"下的"清除"按钮。</span><span class="sxs-lookup"><span data-stu-id="11016-211">Scroll to the bottom of the page and select the **Clear** button under "Default apps for file types" and/or "Default apps for link types."</span></span> <span data-ttu-id="11016-212">与桌面电脑的类似设置不同，不能重置单个文件类型默认值。</span><span class="sxs-lookup"><span data-stu-id="11016-212">Unlike the similar setting on desktop PCs, you can't reset individual file type defaults.</span></span>

### <span data-ttu-id="11016-213">Office Web 应用</span><span class="sxs-lookup"><span data-stu-id="11016-213">Office web app</span></span>

<span data-ttu-id="11016-214">Office Web 应用已添加到"开始"菜单中的"所有应用程序"列表中。</span><span class="sxs-lookup"><span data-stu-id="11016-214">The Office web app has been added to the "All apps" list in the Start menu.</span></span> <span data-ttu-id="11016-215">还可以将此 Web 应用固定到"开始"页面或将其卸载。</span><span class="sxs-lookup"><span data-stu-id="11016-215">This web app can also be pinned to Start or uninstalled.</span></span> <span data-ttu-id="11016-216">由于这是一个 Web 应用，因此其功能与通过访问体验完全匹配 https://www.office.com 。</span><span class="sxs-lookup"><span data-stu-id="11016-216">Because this is a web app, its functionality matches exactly what you'd experience by visiting https://www.office.com.</span></span> <span data-ttu-id="11016-217">仅在 HoloLens 2 具有活动的 Internet 连接时，Office Web 应用功能才可用。</span><span class="sxs-lookup"><span data-stu-id="11016-217">Office web app functionality is only available when your HoloLens 2 has an active internet connection.</span></span>

### <span data-ttu-id="11016-218">轻扫以键入</span><span class="sxs-lookup"><span data-stu-id="11016-218">Swipe to type</span></span>

<span data-ttu-id="11016-219">一些客户发现通过轻扫要键入的单词的形状，在虚拟键盘上"键入"速度更快，我们正在预览全息键盘的此功能。</span><span class="sxs-lookup"><span data-stu-id="11016-219">Some customers find it faster to "type" on virtual keyboards by swiping the shape of the word they intend to type, and we're previewing this feature for the holographic keyboard.</span></span> <span data-ttu-id="11016-220">通过通过全息键盘的平面传递手指的尖角，轻扫该单词的形状，然后从键盘平面撤消手指的尖角，可以一次轻扫一个单词。</span><span class="sxs-lookup"><span data-stu-id="11016-220">You can swipe one word at a time by passing the tip of your finger through the plane of the holographic keyboard, swiping the shape of the word, and then withdrawing the tip of your finger from the plane of the keyboard.</span></span> <span data-ttu-id="11016-221">通过从键盘删除单词之间的手指，无需按空格键，即可轻扫后续字词。</span><span class="sxs-lookup"><span data-stu-id="11016-221">You can swipe follow-up words without needing to press the spacebar by removing your finger from the keyboard between words.</span></span> <span data-ttu-id="11016-222">如果你看到手指在键盘上的移动后看到轻扫轨迹，你将知道该功能正在工作。</span><span class="sxs-lookup"><span data-stu-id="11016-222">You will know the feature is working if you see a swipe trail following your finger's movement on the keyboard.</span></span>

<span data-ttu-id="11016-223">请注意，此功能可能很难使用和掌握，因为全息键盘的性质，与移动电话显示屏不同，你无法抵御手指 (因此) 。</span><span class="sxs-lookup"><span data-stu-id="11016-223">Please note, this feature can be tricky to use and master because of the nature of a holographic keyboard where you don't feel resistance against your finger (unlike a mobile phone display).</span></span> <span data-ttu-id="11016-224">我们正在评估此功能以公开发布，因此您的反馈非常重要;无论你发现此功能有用还是有反馈反馈，请通过反馈中心 [告诉我们](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="11016-224">We are evaluating this feature for public release, so your feedback is important; whether you find the feature useful or you have constructive feedback, please let us know via [Feedback Hub](hololens-feedback.md).</span></span>





## <span data-ttu-id="11016-225">开始接收预览体验成员版本</span><span class="sxs-lookup"><span data-stu-id="11016-225">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="11016-226">如果最近尚未更新，请重启设备以更新状态并获取最新内部版本。</span><span class="sxs-lookup"><span data-stu-id="11016-226">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="11016-227">"重新启动设备"语音命令运行良好。</span><span class="sxs-lookup"><span data-stu-id="11016-227">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="11016-228">还可以选择"设置/Windows 预览体验计划"中的"重启"按钮。</span><span class="sxs-lookup"><span data-stu-id="11016-228">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="11016-229">后端有一个你可能会遇到的 Bug，这样你才能重新进入轨道。</span><span class="sxs-lookup"><span data-stu-id="11016-229">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="11016-230">在 HoloLens 2 设备上 **，转到&** Windows 预览  >  \*\*\*\*  >  **体验计划**"设置更新"，然后选择 **"开始使用"。**</span><span class="sxs-lookup"><span data-stu-id="11016-230">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="11016-231">链接你用于注册为 Windows 预览体验成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="11016-231">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="11016-232">Windows 预览体验成员现在迁移到频道。</span><span class="sxs-lookup"><span data-stu-id="11016-232">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="11016-233">快速**圈**将变为**开发人员频道**，慢圈将成为\*\*\*\* **Beta**渠道，而发布预览圈将成为\*\*\*\*\*\*发布预览频道\*\*。</span><span class="sxs-lookup"><span data-stu-id="11016-233">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="11016-234">该映射如下所示：</span><span class="sxs-lookup"><span data-stu-id="11016-234">Here is what that mapping looks like:</span></span>

![Windows 预览体验成员频道说明](images/WindowsInsiderChannels.png)

<span data-ttu-id="11016-236">有关详细信息，请参阅 Windows 博客 [上的 Windows 预览](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 体验成员频道介绍。</span><span class="sxs-lookup"><span data-stu-id="11016-236">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="11016-237">然后，选择 **"Windows**的活动开发"，选择是希望接收 **开发人员** 频道还是 **Beta 渠道** 版本，并查看计划条款。</span><span class="sxs-lookup"><span data-stu-id="11016-237">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="11016-238">选择 **">立即重启** 以完成。</span><span class="sxs-lookup"><span data-stu-id="11016-238">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="11016-239">重启设备后，转到"设置>更新& **安全>检查** 更新，获取最新内部版本。</span><span class="sxs-lookup"><span data-stu-id="11016-239">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="11016-240">FFU 下载和快速方向</span><span class="sxs-lookup"><span data-stu-id="11016-240">FFU download and flash directions</span></span>
<span data-ttu-id="11016-241">若要使用已签名的 Ffu 进行测试，首先需要先对设备进行解锁，然后才能闪烁已进行测试的已签名 ffu。</span><span class="sxs-lookup"><span data-stu-id="11016-241">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="11016-242">在电脑上：</span><span class="sxs-lookup"><span data-stu-id="11016-242">On PC:</span></span>

    1. <span data-ttu-id="11016-243">从 下载 ffu 到你的电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="11016-243">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="11016-244">从 Microsoft store (ARC) 高级恢复配套设备： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="11016-244">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="11016-245">On HoloLens - Flight Unlock： Open **Settings**  >  **Update & Security**Windows Insider  >  **Program** then sign up， reboot device.</span><span class="sxs-lookup"><span data-stu-id="11016-245">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="11016-246">Flash FFU - 现在可以使用 ARC 对已进行飞行的 FFU 进行闪烁。</span><span class="sxs-lookup"><span data-stu-id="11016-246">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="11016-247">提供反馈并报告问题</span><span class="sxs-lookup"><span data-stu-id="11016-247">Provide feedback and report issues</span></span>

<span data-ttu-id="11016-248">请使用 [HoloLens](hololens-feedback.md) 上的"反馈中心"应用提供反馈并报告问题。</span><span class="sxs-lookup"><span data-stu-id="11016-248">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="11016-249">使用反馈中心可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。</span><span class="sxs-lookup"><span data-stu-id="11016-249">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="11016-250">应以相同方式报告与 HoloLens 的中文和日文版本有关的问题。</span><span class="sxs-lookup"><span data-stu-id="11016-250">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="11016-251">请务必接受询问您是否希望反馈中心访问"文档"文件夹的提示， (系统提示"是") 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="11016-251">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="11016-252">开发人员注意事项</span><span class="sxs-lookup"><span data-stu-id="11016-252">Note for developers</span></span>

<span data-ttu-id="11016-253">欢迎并鼓励你尝试使用 HoloLens 预览体验成员版本开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="11016-253">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="11016-254">请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 开始。</span><span class="sxs-lookup"><span data-stu-id="11016-254">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="11016-255">这些相同的说明与 HoloLens 的预览体验成员版本一致。</span><span class="sxs-lookup"><span data-stu-id="11016-255">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="11016-256">可以使用与 HoloLens Visual Studio相同的 Unity 版本和版本。</span><span class="sxs-lookup"><span data-stu-id="11016-256">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="11016-257">停止接收预览体验成员版本</span><span class="sxs-lookup"><span data-stu-id="11016-257">Stop receiving Insider builds</span></span>

<span data-ttu-id="11016-258">如果你不再希望接收 Windows 全息版的预览体验成员版本，你可以选择在 HoloLens 运行生产版本时退出，或者可以使用高级恢复助手[](hololens-recovery.md)将设备恢复到非预览体验成员版本的 Windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="11016-258">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="11016-259">存在一个已知问题，即手动重新安装全新预览版后从 Insider Preview 版本取消注册的用户将遇到蓝屏。</span><span class="sxs-lookup"><span data-stu-id="11016-259">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="11016-260">之后，他们必须手动恢复其设备。</span><span class="sxs-lookup"><span data-stu-id="11016-260">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="11016-261">有关你是否受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。</span><span class="sxs-lookup"><span data-stu-id="11016-261">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="11016-262">若要验证 HoloLens 是否正在运行生产内部版本：</span><span class="sxs-lookup"><span data-stu-id="11016-262">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="11016-263">转到" **系统>设置>"，** 并查找内部版本编号。</span><span class="sxs-lookup"><span data-stu-id="11016-263">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="11016-264">[请参阅生产内部版本号发行说明](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="11016-264">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="11016-265">若要选择退出预览体验成员版本：</span><span class="sxs-lookup"><span data-stu-id="11016-265">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="11016-266">在运行生产内部版本 HoloLens 上，转到"设置>更新& Windows 预览体验>计划"，**然后选择**"停止预览**体验成员版本"。**</span><span class="sxs-lookup"><span data-stu-id="11016-266">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="11016-267">按照说明选择退出设备。</span><span class="sxs-lookup"><span data-stu-id="11016-267">Follow the instructions to opt out your device.</span></span>
