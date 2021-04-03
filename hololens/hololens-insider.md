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
ms.date: 3/4/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 9b4ce7d05849191ae242396f50df740f25a2cdfe
ms.sourcegitcommit: 86dba9e8a5e25f0bf29f4c0580970c25c44b7359
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470060"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="3423a-103">Microsoft HoloLens 内部预览版</span><span class="sxs-lookup"><span data-stu-id="3423a-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="3423a-104">欢迎使用 HoloLens 的最新 Insider Preview 版本！</span><span class="sxs-lookup"><span data-stu-id="3423a-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="3423a-105">开始操作非常简单，并为[](hololens-insider.md#start-receiving-insider-builds)HoloLens 的下一个主要操作系统更新提供有价值的反馈。</span><span class="sxs-lookup"><span data-stu-id="3423a-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="3423a-106">Windows 预览体验成员发行说明</span><span class="sxs-lookup"><span data-stu-id="3423a-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="3423a-107">我们很高兴再次开始向 Windows 预览体验成员提供新功能。</span><span class="sxs-lookup"><span data-stu-id="3423a-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="3423a-108">新内部版本将进行到开发人员频道的测试版，获取最新更新。</span><span class="sxs-lookup"><span data-stu-id="3423a-108">New builds will be flighting to the Dev Channel for the latest updates.</span></span> <span data-ttu-id="3423a-109">随着我们向 Windows 预览体验成员版本添加更多功能和更新，我们将继续更新此页面。</span><span class="sxs-lookup"><span data-stu-id="3423a-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span>  <span data-ttu-id="3423a-110">感到兴奋，并准备好将这些更新混合到你的现实中。</span><span class="sxs-lookup"><span data-stu-id="3423a-110">Get excited and ready to mix these updates into your reality.</span></span>

<span data-ttu-id="3423a-111">此功能更新包含两个目标访问群体的功能。</span><span class="sxs-lookup"><span data-stu-id="3423a-111">This feature update contains features for two target audiences.</span></span> <span data-ttu-id="3423a-112">最终用户可在设备上使用的功能，以及 IT 管理员可配置的新设备管理选项。</span><span class="sxs-lookup"><span data-stu-id="3423a-112">Features that can be used by anyone on a device by the end user, and new device management options that can be configured by IT Admins.</span></span> <span data-ttu-id="3423a-113">下面的功能表具体列出了能够使用每个新功能的受众。</span><span class="sxs-lookup"><span data-stu-id="3423a-113">The feature table below specifics the audiences with who be able to use each new feature.</span></span> <span data-ttu-id="3423a-114">如果你是 IT 管理员，请查看我们的 IT 管理员 [- 更新清单](#it-admin---update-checklist)</span><span class="sxs-lookup"><span data-stu-id="3423a-114">If you are an IT Admin, please take a look at our [IT Admin - Update Checklist](#it-admin---update-checklist)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3423a-115">如果你之前在网亭中使用的是"设置"应用或 Microsoft Edge 应用，我们已经用使用不同的应用 ID 的新应用替换了这些应用。</span><span class="sxs-lookup"><span data-stu-id="3423a-115">If you were previously using either the Settings app or Microsoft Edge app in a Kiosk, we have replaced these apps with new apps which use a different App ID.</span></span> <span data-ttu-id="3423a-116">我们强烈建议你在展台模式下阅读下面的新应用[的新 AUMID。](#use-the-new-settings-and-edge-apps-in-kiosk-modes)</span><span class="sxs-lookup"><span data-stu-id="3423a-116">We highly encourage you to read [New AUMIDs for new apps in Kiosk mode](#use-the-new-settings-and-edge-apps-in-kiosk-modes) below.</span></span> <span data-ttu-id="3423a-117">这将确保你继续在展台中安装"设置"应用，或包括新的 Microsoft Edge 应用。</span><span class="sxs-lookup"><span data-stu-id="3423a-117">This will ensure you either continue to have the Settings app in your Kiosk, or include the new Microsoft Edge app.</span></span>

<br>

| <span data-ttu-id="3423a-118">功能名称</span><span class="sxs-lookup"><span data-stu-id="3423a-118">Feature Name</span></span>                                              | <span data-ttu-id="3423a-119">简短说明</span><span class="sxs-lookup"><span data-stu-id="3423a-119">Short description</span></span>                                                                      | <span data-ttu-id="3423a-120">目标访问群体</span><span class="sxs-lookup"><span data-stu-id="3423a-120">Target Audience</span></span> | <span data-ttu-id="3423a-121">在内部版本中可用</span><span class="sxs-lookup"><span data-stu-id="3423a-121">Available in build</span></span> |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [<span data-ttu-id="3423a-122">新版 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3423a-122">New Microsoft Edge</span></span>](#introducing-the-new-microsoft-edge) | <span data-ttu-id="3423a-123">新的基于 Chromium 的 Microsoft Edge 现在可用于 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="3423a-123">The new, Chromium-based Microsoft Edge is now available for HoloLens 2</span></span>                         | <span data-ttu-id="3423a-124">最终用户</span><span class="sxs-lookup"><span data-stu-id="3423a-124">End User</span></span> | <span data-ttu-id="3423a-125">20279.1006</span><span class="sxs-lookup"><span data-stu-id="3423a-125">20279.1006</span></span> |
| [<span data-ttu-id="3423a-126">WebXR 和 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="3423a-126">WebXR and 360 Viewer</span></span>](#webxr-and-360-viewer)             | <span data-ttu-id="3423a-127">尝试沉浸式 Web 体验和 360 视频播放</span><span class="sxs-lookup"><span data-stu-id="3423a-127">Try immersive web experiences and 360 video playback</span></span>                                           | <span data-ttu-id="3423a-128">最终用户</span><span class="sxs-lookup"><span data-stu-id="3423a-128">End User</span></span> | <span data-ttu-id="3423a-129">20289.1000</span><span class="sxs-lookup"><span data-stu-id="3423a-129">20289.1000</span></span> |
| [<span data-ttu-id="3423a-130">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="3423a-130">New Settings app</span></span>](#new-settings-app)                     | <span data-ttu-id="3423a-131">旧式"设置"应用将替换为具有新功能和设置的更新版本</span><span class="sxs-lookup"><span data-stu-id="3423a-131">The legacy Settings app is being replaced by an updated version with new features and settings</span></span> | <span data-ttu-id="3423a-132">最终用户</span><span class="sxs-lookup"><span data-stu-id="3423a-132">End User</span></span> | <span data-ttu-id="3423a-133">20279.1006</span><span class="sxs-lookup"><span data-stu-id="3423a-133">20279.1006</span></span> |
| [<span data-ttu-id="3423a-134">显示颜色校准</span><span class="sxs-lookup"><span data-stu-id="3423a-134">Display color calibration</span></span>](#display-color-calibration)   | <span data-ttu-id="3423a-135">为 HoloLens 2 显示器选择备用颜色配置文件</span><span class="sxs-lookup"><span data-stu-id="3423a-135">Select an alternative color profile for your HoloLens 2 display</span></span>                                | <span data-ttu-id="3423a-136">最终用户</span><span class="sxs-lookup"><span data-stu-id="3423a-136">End User</span></span> | <span data-ttu-id="3423a-137">20293.1000</span><span class="sxs-lookup"><span data-stu-id="3423a-137">20293.1000</span></span> |
| [<span data-ttu-id="3423a-138">默认应用选取器</span><span class="sxs-lookup"><span data-stu-id="3423a-138">Default app picker</span></span>](#default-app-picker)                 | <span data-ttu-id="3423a-139">选择应针对每个文件或链接类型启动的应用</span><span class="sxs-lookup"><span data-stu-id="3423a-139">Choose which app should launch for each file or link type</span></span>                                      | <span data-ttu-id="3423a-140">最终用户</span><span class="sxs-lookup"><span data-stu-id="3423a-140">End User</span></span> | <span data-ttu-id="3423a-141">20279.1006</span><span class="sxs-lookup"><span data-stu-id="3423a-141">20279.1006</span></span> |
| [<span data-ttu-id="3423a-142">每个应用音量控制</span><span class="sxs-lookup"><span data-stu-id="3423a-142">Per app volume control</span></span>](#per-app-volume-control) |  <span data-ttu-id="3423a-143">独立于系统卷控制应用级别音量</span><span class="sxs-lookup"><span data-stu-id="3423a-143">Control app level volume independently from system volume</span></span> | <span data-ttu-id="3423a-144">最终用户</span><span class="sxs-lookup"><span data-stu-id="3423a-144">End User</span></span> | <span data-ttu-id="3423a-145">20293.1000</span><span class="sxs-lookup"><span data-stu-id="3423a-145">20293.1000</span></span> |
| [<span data-ttu-id="3423a-146">Office Web 应用</span><span class="sxs-lookup"><span data-stu-id="3423a-146">Office web app</span></span>](#office-web-app)                         | <span data-ttu-id="3423a-147">Office Web 应用的快捷方式现在列在"所有应用"中</span><span class="sxs-lookup"><span data-stu-id="3423a-147">A shortcut to the Office web app is now listed in "All apps"</span></span>                                   | <span data-ttu-id="3423a-148">最终用户</span><span class="sxs-lookup"><span data-stu-id="3423a-148">End User</span></span> | <span data-ttu-id="3423a-149">20279.1006</span><span class="sxs-lookup"><span data-stu-id="3423a-149">20279.1006</span></span> |
| [<span data-ttu-id="3423a-150">轻扫以键入</span><span class="sxs-lookup"><span data-stu-id="3423a-150">Swipe to type</span></span>](#swipe-to-type)                           | <span data-ttu-id="3423a-151">使用手指提示在全息键盘上"轻扫"字词</span><span class="sxs-lookup"><span data-stu-id="3423a-151">Use the tip of your finger to "swipe" words on the holographic keyboard</span></span>                        | <span data-ttu-id="3423a-152">最终用户</span><span class="sxs-lookup"><span data-stu-id="3423a-152">End User</span></span> | <span data-ttu-id="3423a-153">20279.1006</span><span class="sxs-lookup"><span data-stu-id="3423a-153">20279.1006</span></span> |
| [<span data-ttu-id="3423a-154">"开始"菜单的电源菜单</span><span class="sxs-lookup"><span data-stu-id="3423a-154">Power menu from Start</span></span>](#power-menu-from-start) | <span data-ttu-id="3423a-155">在"开始"菜单上，重启并关闭 HoloLens 设备</span><span class="sxs-lookup"><span data-stu-id="3423a-155">On Start Menu, restart and shut down HoloLens device</span></span> | <span data-ttu-id="3423a-156">最终用户</span><span class="sxs-lookup"><span data-stu-id="3423a-156">End User</span></span> | <span data-ttu-id="3423a-157">20293.1000</span><span class="sxs-lookup"><span data-stu-id="3423a-157">20293.1000</span></span> |
| [<span data-ttu-id="3423a-158">登录屏幕上列出的多个用户</span><span class="sxs-lookup"><span data-stu-id="3423a-158">Multiple users listed on Sign in screen</span></span>](#multiple-users-listed-on-sign-in-screen) | <span data-ttu-id="3423a-159">在登录屏幕上显示多个用户帐户</span><span class="sxs-lookup"><span data-stu-id="3423a-159">Display multiple user accounts on the Sign in screen</span></span> | <span data-ttu-id="3423a-160">最终用户</span><span class="sxs-lookup"><span data-stu-id="3423a-160">End User</span></span> | <span data-ttu-id="3423a-161">20293.1000</span><span class="sxs-lookup"><span data-stu-id="3423a-161">20293.1000</span></span> |
| [<span data-ttu-id="3423a-162">USB-C 外部麦克风支持</span><span class="sxs-lookup"><span data-stu-id="3423a-162">USB-C External Microphone Support</span></span>](#usb-c-external-microphone-support) | <span data-ttu-id="3423a-163">将 USB-C 麦克风用于应用和/或远程协助。</span><span class="sxs-lookup"><span data-stu-id="3423a-163">Use USB-C microphones for apps and / or Remote Assist.</span></span>| <span data-ttu-id="3423a-164">最终用户</span><span class="sxs-lookup"><span data-stu-id="3423a-164">End User</span></span> | <span data-ttu-id="3423a-165">20279.1006</span><span class="sxs-lookup"><span data-stu-id="3423a-165">20279.1006</span></span> |
| [<span data-ttu-id="3423a-166">展台的访问者自动登录</span><span class="sxs-lookup"><span data-stu-id="3423a-166">Visitor Auto-logon for Kiosks</span></span>](#visitor-auto-logon-for-kiosks)                          | <span data-ttu-id="3423a-167">启用要用于展台模式的访问者帐户的自动登录。</span><span class="sxs-lookup"><span data-stu-id="3423a-167">Enables the auto-logon on Visitor accounts to be used for Kiosk modes.</span></span>                         | <span data-ttu-id="3423a-168">IT 管理员</span><span class="sxs-lookup"><span data-stu-id="3423a-168">IT Admin</span></span> | <span data-ttu-id="3423a-169">20279.1006</span><span class="sxs-lookup"><span data-stu-id="3423a-169">20279.1006</span></span>                 |
| [<span data-ttu-id="3423a-170">展台模式下新应用的新 AUMID</span><span class="sxs-lookup"><span data-stu-id="3423a-170">New AUMIDs for new apps in Kiosk mode</span></span>](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | <span data-ttu-id="3423a-171">新设置和边缘应用的 AUMID</span><span class="sxs-lookup"><span data-stu-id="3423a-171">AUMIDs for new Settings and Edge apps</span></span> | <span data-ttu-id="3423a-172">IT 管理员</span><span class="sxs-lookup"><span data-stu-id="3423a-172">IT Admin</span></span> | <span data-ttu-id="3423a-173">20279.1006</span><span class="sxs-lookup"><span data-stu-id="3423a-173">20279.1006</span></span> |
| [<span data-ttu-id="3423a-174">改进的展台模式故障帮助</span><span class="sxs-lookup"><span data-stu-id="3423a-174">Improved Kiosk mode failure handing</span></span>](#kiosk-mode-behavior-changes-for-handling-of-failures) | <span data-ttu-id="3423a-175">展台模式在空的"开始"菜单前查找全局分配的访问权限。</span><span class="sxs-lookup"><span data-stu-id="3423a-175">Kiosk mode looks for Global Assigned Access before empty start menu.</span></span> | <span data-ttu-id="3423a-176">IT 管理员</span><span class="sxs-lookup"><span data-stu-id="3423a-176">IT Admin</span></span> | <span data-ttu-id="3423a-177">20279.1006</span><span class="sxs-lookup"><span data-stu-id="3423a-177">20279.1006</span></span> |
| [<span data-ttu-id="3423a-178">页面设置可见性的新设置 URIs</span><span class="sxs-lookup"><span data-stu-id="3423a-178">New SettingsURIs for Page Settings Visibility</span></span>](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | <span data-ttu-id="3423a-179">设置/PageVisibilityList 策略的 20 多个新 SettingsURIs</span><span class="sxs-lookup"><span data-stu-id="3423a-179">20+ new SettingsURIs for Settings/PageVisibilityList policy</span></span> | <span data-ttu-id="3423a-180">IT 管理员</span><span class="sxs-lookup"><span data-stu-id="3423a-180">IT Admin</span></span> | <span data-ttu-id="3423a-181">20289.1000</span><span class="sxs-lookup"><span data-stu-id="3423a-181">20289.1000</span></span> |
| [<span data-ttu-id="3423a-182">配置回退诊断</span><span class="sxs-lookup"><span data-stu-id="3423a-182">Configure Fallback Diagnostics</span></span>](#configuring-fallback-diagnostics-via-settings-app) | <span data-ttu-id="3423a-183">在"设置"应用中设置回退诊断行为</span><span class="sxs-lookup"><span data-stu-id="3423a-183">Setting Fallback Diagnostic Behavior in Settings App</span></span> | <span data-ttu-id="3423a-184">IT 管理员</span><span class="sxs-lookup"><span data-stu-id="3423a-184">IT Admin</span></span> | <span data-ttu-id="3423a-185">20279.1006</span><span class="sxs-lookup"><span data-stu-id="3423a-185">20279.1006</span></span> |
| [<span data-ttu-id="3423a-186">与附近设备共享内容</span><span class="sxs-lookup"><span data-stu-id="3423a-186">Share things with nearby devices</span></span>](#share-things-with-nearby-devices) | <span data-ttu-id="3423a-187">将 HoloLens 中的文件或 URL 共享到电脑</span><span class="sxs-lookup"><span data-stu-id="3423a-187">Share files or URLs from a HoloLens to a PC</span></span> | <span data-ttu-id="3423a-188">全部</span><span class="sxs-lookup"><span data-stu-id="3423a-188">All</span></span> | <span data-ttu-id="3423a-189">20279.1006</span><span class="sxs-lookup"><span data-stu-id="3423a-189">20279.1006</span></span> |
| [<span data-ttu-id="3423a-190">新的操作系统更新疑难解答程序</span><span class="sxs-lookup"><span data-stu-id="3423a-190">New OS Update troubleshooter</span></span>](#new-os-update-troubleshooter) | <span data-ttu-id="3423a-191">操作系统更新的设置中的新疑难解答</span><span class="sxs-lookup"><span data-stu-id="3423a-191">New troubleshooter in Settings for OS updates</span></span> | <span data-ttu-id="3423a-192">IT 管理员</span><span class="sxs-lookup"><span data-stu-id="3423a-192">IT Admin</span></span> | <span data-ttu-id="3423a-193">20279.1006</span><span class="sxs-lookup"><span data-stu-id="3423a-193">20279.1006</span></span> |
| [<span data-ttu-id="3423a-194">传递优化预览</span><span class="sxs-lookup"><span data-stu-id="3423a-194">Delivery Optimization Preview</span></span>](#delivery-optimization-preview) | <span data-ttu-id="3423a-195">减少从多个 HoloLens 设备下载的带宽消耗</span><span class="sxs-lookup"><span data-stu-id="3423a-195">Reduce bandwidth consumption for downloads from multiple HoloLens devices</span></span> | <span data-ttu-id="3423a-196">IT 管理员</span><span class="sxs-lookup"><span data-stu-id="3423a-196">IT Admin</span></span> | <span data-ttu-id="3423a-197">20301.1000</span><span class="sxs-lookup"><span data-stu-id="3423a-197">20301.1000</span></span> |
| [<span data-ttu-id="3423a-198">更新中的改进和修复</span><span class="sxs-lookup"><span data-stu-id="3423a-198">Improvements and fixes in the update</span></span>](#improvements-and-fixes-in-the-update) | <span data-ttu-id="3423a-199">更新中的其他修补程序。</span><span class="sxs-lookup"><span data-stu-id="3423a-199">Additional fixes in the update.</span></span> | <span data-ttu-id="3423a-200">全部</span><span class="sxs-lookup"><span data-stu-id="3423a-200">All</span></span> | <span data-ttu-id="3423a-201">20279.1006</span><span class="sxs-lookup"><span data-stu-id="3423a-201">20279.1006</span></span> |

### <a name="it-admin---update-checklist"></a><span data-ttu-id="3423a-202">IT 管理员 - 更新清单</span><span class="sxs-lookup"><span data-stu-id="3423a-202">IT Admin - Update Checklist</span></span>

<span data-ttu-id="3423a-203">此清单将帮助你了解此功能更新中要添加的可能影响当前设备管理配置的功能的新增项，或你可能希望开始使用的新功能。</span><span class="sxs-lookup"><span data-stu-id="3423a-203">This checklist will help you know the new items that features that are being added in this feature update that may affect your current device management configurations, or new features you might wish to start using.</span></span>

#### <a name="updates-to-kiosk-mode"></a><span data-ttu-id="3423a-204">展台模式的更新</span><span class="sxs-lookup"><span data-stu-id="3423a-204">Updates to Kiosk mode</span></span>

[**<span data-ttu-id="3423a-205">展台模式下新应用的新 AUMID</span><span class="sxs-lookup"><span data-stu-id="3423a-205">New AUMIDs for new apps in Kiosk mode</span></span>**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

<span data-ttu-id="3423a-206">如果你之前在网亭中使用的是"设置"应用或 Microsoft Edge 应用，我们已经用使用不同的应用 ID 的新应用替换了这些应用。</span><span class="sxs-lookup"><span data-stu-id="3423a-206">If you were previously using either the Settings app or Microsoft Edge app in a Kiosk, we have replaced these apps with new apps which use a different App ID.</span></span> <span data-ttu-id="3423a-207">我们强烈建议你在展台模式下阅读下面的新应用[的新 AUMID。](#use-the-new-settings-and-edge-apps-in-kiosk-modes)</span><span class="sxs-lookup"><span data-stu-id="3423a-207">We highly encourage you to read [New AUMIDs for new apps in Kiosk mode](#use-the-new-settings-and-edge-apps-in-kiosk-modes) below.</span></span> <span data-ttu-id="3423a-208">这将确保你继续在展台中安装"设置"应用，或包括新的 Microsoft Edge 应用。</span><span class="sxs-lookup"><span data-stu-id="3423a-208">This will ensure you either continue to have the Settings app in your Kiosk, or include the new Microsoft Edge app.</span></span>

<span data-ttu-id="3423a-209">现在可以完成这些更改，并部署到所有设备，并允许在更新时更顺畅地过渡。</span><span class="sxs-lookup"><span data-stu-id="3423a-209">These changes can be done now, and deployed to all devices and allow for a smoother transition on update.</span></span>

[**<span data-ttu-id="3423a-210">展台的访问者自动登录</span><span class="sxs-lookup"><span data-stu-id="3423a-210">Visitor Auto-logon for Kiosks</span></span>**](#visitor-auto-logon-for-kiosks)

<span data-ttu-id="3423a-211">访问者现在可以自动登录网亭。</span><span class="sxs-lookup"><span data-stu-id="3423a-211">Visitors can now be automatically logged into a Kiosk.</span></span> <span data-ttu-id="3423a-212">此行为默认处于打开状态，但可以管理和禁用。</span><span class="sxs-lookup"><span data-stu-id="3423a-212">This behavior is on by default but can be managed and disabled.</span></span>

[**<span data-ttu-id="3423a-213">改进的展台模式故障帮助</span><span class="sxs-lookup"><span data-stu-id="3423a-213">Improved Kiosk mode failure handing</span></span>**](#kiosk-mode-behavior-changes-for-handling-of-failures)

<span data-ttu-id="3423a-214">如果登录 AAD 用户的 AAD 组成员身份未成功确定，则全局展台配置用于"开始"菜单 (如果存在) 则向用户显示空的"开始"菜单。</span><span class="sxs-lookup"><span data-stu-id="3423a-214">If AAD group membership of signed-in AAD user is not successfully determined, then global kiosk configuration is used for start menu (if present) otherwise user is presented with empty start menu.</span></span> <span data-ttu-id="3423a-215">尽管空的"开始"菜单不是你可以直接设置的配置，但如果使用展台，则新的处理方法可能会通知支持部门，因为这可能适用于你的配置，或者你可能希望对分配的访问权限配置进行新的调整。</span><span class="sxs-lookup"><span data-stu-id="3423a-215">While the empty start menu is not a configuration you can directly set, this new handling may be something to inform your support department of if you are using Kiosks, as this may apply to your configurations or you may want to make new adjustments to your assigned access configurations.</span></span>

#### <a name="updates-to-page-settings-visibility"></a><span data-ttu-id="3423a-216">页面设置可见性更新</span><span class="sxs-lookup"><span data-stu-id="3423a-216">Updates to Page Settings Visibility</span></span>

[**<span data-ttu-id="3423a-217">页面设置可见性的新设置 URIs</span><span class="sxs-lookup"><span data-stu-id="3423a-217">New SettingsURIs for Page Settings Visibility</span></span>**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

<span data-ttu-id="3423a-218">如果当前正在使用页面 [设置可见性](settings-uri-list.md) ，则你可能希望对已允许或阻止的现有 URI 进行调整。</span><span class="sxs-lookup"><span data-stu-id="3423a-218">IF you are currently using [Page Settings Visibility](settings-uri-list.md) then you may wish to make adjustments to your existing URIs you have either allowed or blocked.</span></span>

#### <a name="updates-for-your-wdac-policy"></a><span data-ttu-id="3423a-219">WDAC 策略的更新</span><span class="sxs-lookup"><span data-stu-id="3423a-219">Updates for your WDAC policy</span></span>

<span data-ttu-id="3423a-220">如果你之前通过 WDAC 阻止 Microsoft Edge，你将希望更新 WDAC 策略。</span><span class="sxs-lookup"><span data-stu-id="3423a-220">If you were previously blocking Microsoft Edge via WDAC, you'll want to update your WDAC policy.</span></span> <span data-ttu-id="3423a-221">请查看 [以下内容并使用](#using-wdac-to-block-new-microsoft-edge) 提供的示例代码。</span><span class="sxs-lookup"><span data-stu-id="3423a-221">Please [review the following](#using-wdac-to-block-new-microsoft-edge) and use the sample code provided.</span></span>

#### <a name="enable-new-endpoints-for-edge"></a><span data-ttu-id="3423a-222">为边缘启用新终结点</span><span class="sxs-lookup"><span data-stu-id="3423a-222">Enable new endpoints for Edge</span></span>

<span data-ttu-id="3423a-223">如果你有涉及配置网络终结点（如代理或防火墙）的基础结构，请为新的 Microsoft Edge 应用启用这些新 [终结点。](#managing-endpoints-for-the-new-microsoft-edge)</span><span class="sxs-lookup"><span data-stu-id="3423a-223">If you have an infrastructure that involves configuring network endpoints such as proxy or firewall, please [enable these new endpoints for the new Microsoft Edge app.](#managing-endpoints-for-the-new-microsoft-edge)</span></span>

#### <a name="newly-configurable-items"></a><span data-ttu-id="3423a-224">新可配置项</span><span class="sxs-lookup"><span data-stu-id="3423a-224">Newly configurable items</span></span>

- [<span data-ttu-id="3423a-225">配置回退诊断</span><span class="sxs-lookup"><span data-stu-id="3423a-225">Configure Fallback Diagnostics</span></span>](#configuring-fallback-diagnostics-via-settings-app)
  - <span data-ttu-id="3423a-226">你可以配置是否收集回退诊断以及谁可以收集回退诊断。</span><span class="sxs-lookup"><span data-stu-id="3423a-226">You may configure if and who may collect Fallback Diagnostics.</span></span>
- [<span data-ttu-id="3423a-227">与附近设备共享内容</span><span class="sxs-lookup"><span data-stu-id="3423a-227">Share things with nearby devices</span></span>](#share-things-with-nearby-devices)
  - <span data-ttu-id="3423a-228">可以禁用新的附近共享功能。</span><span class="sxs-lookup"><span data-stu-id="3423a-228">You may disable the new nearby sharing feature.</span></span>
- [<span data-ttu-id="3423a-229">配置新 Microsoft Edge 的策略设置</span><span class="sxs-lookup"><span data-stu-id="3423a-229">Configuring policy settings for the new Microsoft Edge</span></span>](#configuring-policy-settings-for-the-new-microsoft-edge)
  - <span data-ttu-id="3423a-230">查看适用于 Microsoft Edge 的新配置。</span><span class="sxs-lookup"><span data-stu-id="3423a-230">Review the newly configurations available for Microsoft Edge.</span></span>

#### <a name="new-diagnostic-tool"></a><span data-ttu-id="3423a-231">新的诊断工具</span><span class="sxs-lookup"><span data-stu-id="3423a-231">New diagnostic tool</span></span>

- [<span data-ttu-id="3423a-232">新的操作系统更新疑难解答程序</span><span class="sxs-lookup"><span data-stu-id="3423a-232">New OS Update troubleshooter</span></span>](#new-os-update-troubleshooter)
  - <span data-ttu-id="3423a-233">收集与操作系统更新相关的日志</span><span class="sxs-lookup"><span data-stu-id="3423a-233">Collect logs related to OS Updates</span></span>

### <a name="introducing-the-new-microsoft-edge"></a><span data-ttu-id="3423a-234">推出新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3423a-234">Introducing the new Microsoft Edge</span></span>

![新 Microsoft Edge 徽标的旧 Microsoft Edge 徽标动画](images/new-edge.gif)

<span data-ttu-id="3423a-236">新的 Microsoft Edge [采用 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 开放源代码项目，为客户创建更好的兼容性，并针对 Web 开发人员减少 Web 碎片。</span><span class="sxs-lookup"><span data-stu-id="3423a-236">The new Microsoft Edge [adopts the Chromium open source project](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) to create better compatibility for customers and less fragmentation of the web for web developers.</span></span>

<span data-ttu-id="3423a-237">通过此 Insider 预览版，HoloLens 2 客户首次可以使用新的 Microsoft Edge！</span><span class="sxs-lookup"><span data-stu-id="3423a-237">With this Insider preview, the new Microsoft Edge is available to HoloLens 2 customers for the first time!</span></span> <span data-ttu-id="3423a-238">虽然新 Microsoft Edge 最终将替换 HoloLens 2 上的旧版 Microsoft Edge，但预览体验成员当前可以使用这两个浏览器。</span><span class="sxs-lookup"><span data-stu-id="3423a-238">While the new Microsoft Edge will eventually replace legacy Microsoft Edge on HoloLens 2, both browsers are currently available to Insiders.</span></span> <span data-ttu-id="3423a-239">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span><span class="sxs-lookup"><span data-stu-id="3423a-239">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub](hololens-feedback.md).</span></span>

![新 Microsoft Edge 屏幕截图](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a><span data-ttu-id="3423a-241">启动新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3423a-241">Launching the new Microsoft Edge</span></span>

<span data-ttu-id="3423a-242">预览体验成员可以使用两个版本的 Microsoft Edge：新的 Microsoft Edge 新 Microsoft Edge 图标 (由蓝色和绿色旋转图标) 和由白色"e"图标) 表示的旧版 ![ ](images/new_edge_logo.png) Microsoft Edge (。</span><span class="sxs-lookup"><span data-stu-id="3423a-242">There are two versions of Microsoft Edge available to Insiders: the new Microsoft Edge ![new Microsoft Edge icon](images/new_edge_logo.png) (represented by a blue and green swirl icon) and legacy Microsoft Edge (represented by the white "e" icon).</span></span> <span data-ttu-id="3423a-243">新的 Microsoft Edge 固定到"开始"菜单，并且会在你激活 Web 链接时自动启动。</span><span class="sxs-lookup"><span data-stu-id="3423a-243">The new Microsoft Edge is pinned to the Start menu and will automatically launch when you activate a web link.</span></span> <span data-ttu-id="3423a-244">如果你想要还原为使用旧版 Microsoft Edge 作为默认 Web 浏览器，请参阅下面的说明重置 [默认应用](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="3423a-244">If you would like to revert to using legacy Microsoft Edge as your default web browser, see the instructions below for [resetting default apps](#default-app-picker).</span></span>

> [!NOTE]
> <span data-ttu-id="3423a-245">当你首次在 HoloLens 2 上启动新的 Microsoft Edge 时，你的设置和数据会从旧版 Microsoft Edge 导入。</span><span class="sxs-lookup"><span data-stu-id="3423a-245">When you first launch the new Microsoft Edge on HoloLens 2, your settings and data will be imported from legacy Microsoft Edge.</span></span> <span data-ttu-id="3423a-246">如果在启动新的 Microsoft Edge 后继续使用旧版 Microsoft Edge，则新数据不会从旧版 Microsoft Edge 同步到新的 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="3423a-246">If you continue to use legacy Microsoft Edge after launching the new Microsoft Edge, that new data will not be synced from legacy Microsoft Edge to the new Microsoft Edge.</span></span>

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a><span data-ttu-id="3423a-247">配置新 Microsoft Edge 的策略设置</span><span class="sxs-lookup"><span data-stu-id="3423a-247">Configuring policy settings for the new Microsoft Edge</span></span>

<span data-ttu-id="3423a-248">新 Microsoft Edge 为 IT 管理员提供 HoloLens 2 上的一组范围更广的浏览器策略，这一点与之前在旧版 Microsoft Edge 中提供的策略相较。</span><span class="sxs-lookup"><span data-stu-id="3423a-248">The new Microsoft Edge offers IT admins a much broader set of browser policies on HoloLens 2 than were previously available with legacy Microsoft Edge.</span></span>

<span data-ttu-id="3423a-249">下面是一些有用的资源，用于详细了解如何管理新 Microsoft Edge 的策略设置：</span><span class="sxs-lookup"><span data-stu-id="3423a-249">Here are some helpful resources for learning more about managing policy settings for the new Microsoft Edge:</span></span>

- [<span data-ttu-id="3423a-250">使用 Microsoft Intune 配置 Microsoft Edge 策略设置</span><span class="sxs-lookup"><span data-stu-id="3423a-250">Configure Microsoft Edge policy settings with Microsoft Intune</span></span>](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [<span data-ttu-id="3423a-251">Microsoft Edge 旧版到 Microsoft Edge 策略映射</span><span class="sxs-lookup"><span data-stu-id="3423a-251">Microsoft Edge Legacy to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [<span data-ttu-id="3423a-252">Google Chrome 到 Microsoft Edge 策略映射</span><span class="sxs-lookup"><span data-stu-id="3423a-252">Google Chrome to Microsoft Edge policy mapping</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- <span data-ttu-id="3423a-253">[Microsoft Edge 企业版文档完整](https://docs.microsoft.com/deployedge/)</span><span class="sxs-lookup"><span data-stu-id="3423a-253">Full [Microsoft Edge Enterprise documentation](https://docs.microsoft.com/deployedge/)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3423a-254">由于新的 Microsoft Edge 支持大量浏览器策略，团队无法保证每个新策略在 HoloLens 2 上正常工作。</span><span class="sxs-lookup"><span data-stu-id="3423a-254">Because of the volume of browser policies supported by the new Microsoft Edge, our team is unable to guarantee that each new policy works on HoloLens 2.</span></span> <span data-ttu-id="3423a-255">但是，我们已测试和确认与 HoloLens 2 上以前支持的每个旧版 Microsoft Edge 策略等效的新 Microsoft Edge 策略能正常工作。</span><span class="sxs-lookup"><span data-stu-id="3423a-255">However, we've tested and confirmed than the new Microsoft Edge equivalent of each legacy Microsoft Edge policy previously supported on HoloLens 2 work as expected.</span></span> <span data-ttu-id="3423a-256">请参阅 [Microsoft Edge 旧版到 Microsoft Edge 策略映射](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) ，查找与 HoloLens 2 一同使用的每个旧版 Microsoft Edge 浏览器策略的新 Microsoft Edge 等效项。</span><span class="sxs-lookup"><span data-stu-id="3423a-256">See [Microsoft Edge Legacy to Microsoft Edge policy mapping](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) to find the new Microsoft Edge equivalent of each legacy Microsoft Edge browser policy you were using with HoloLens 2.</span></span>
>
> <span data-ttu-id="3423a-257">我们至少知道有两个新的 Microsoft Edge 策略 *无法与* HoloLens 2 一起使用：</span><span class="sxs-lookup"><span data-stu-id="3423a-257">There are at least two new Microsoft Edge policies that we know *will not* work with HoloLens 2:</span></span>
> - <span data-ttu-id="3423a-258">EnterpriseModeSiteList</span><span class="sxs-lookup"><span data-stu-id="3423a-258">EnterpriseModeSiteList</span></span>
> - <span data-ttu-id="3423a-259">EnterpriseSiteListServiceURL</span><span class="sxs-lookup"><span data-stu-id="3423a-259">EnterpriseSiteListServiceURL</span></span>

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a><span data-ttu-id="3423a-260">HoloLens 2 上的新 Microsoft Edge 预期功能</span><span class="sxs-lookup"><span data-stu-id="3423a-260">What to expect from the new Microsoft Edge on HoloLens 2</span></span>

<span data-ttu-id="3423a-261">由于新的 Microsoft Edge 是具有新的 UWP 适配器层的本机 Win32 应用，允许它在仅 UWP 设备（如 HoloLens 2）上运行，因此某些功能可能不会立即可用。</span><span class="sxs-lookup"><span data-stu-id="3423a-261">Because the new Microsoft Edge is a native Win32 app with a new UWP adapter layer allowing it to run on UWP-only devices like HoloLens 2, some features may not be immediately available.</span></span> <span data-ttu-id="3423a-262">我们将支持未来几个月的新方案和功能，因此请查看此空间获取最新信息。</span><span class="sxs-lookup"><span data-stu-id="3423a-262">We'll be supporting new scenarios and features over the coming months, so check this space for up-to-date information.</span></span>

**<span data-ttu-id="3423a-263">应用场景和功能应能正常工作：</span><span class="sxs-lookup"><span data-stu-id="3423a-263">Scenarios and features expected to work:</span></span>**
- <span data-ttu-id="3423a-264">首次运行体验、登录配置文件和同步</span><span class="sxs-lookup"><span data-stu-id="3423a-264">First-run experience, sign in to profile, and sync</span></span>
- <span data-ttu-id="3423a-265">网站应按预期呈现和行为</span><span class="sxs-lookup"><span data-stu-id="3423a-265">Websites should render and behave as expected</span></span>
- <span data-ttu-id="3423a-266">大多数浏览器功能 (收藏夹、历史记录等) 应正常工作</span><span class="sxs-lookup"><span data-stu-id="3423a-266">Most browser functionality (Favorites, History, etc.) should work as expected</span></span>
- <span data-ttu-id="3423a-267">深色模式</span><span class="sxs-lookup"><span data-stu-id="3423a-267">Dark mode</span></span>
- <span data-ttu-id="3423a-268">将 Web 应用安装到设备</span><span class="sxs-lookup"><span data-stu-id="3423a-268">Installing web apps to the device</span></span>
- <span data-ttu-id="3423a-269">安装扩展 (请告诉我们你使用的任何扩展在 HoloLens 2) </span><span class="sxs-lookup"><span data-stu-id="3423a-269">Installing extensions (please let us know if you use any extensions that don't work properly on HoloLens 2)</span></span>
- <span data-ttu-id="3423a-270">查看和标记 PDF</span><span class="sxs-lookup"><span data-stu-id="3423a-270">Viewing and marking up a PDF</span></span>
- <span data-ttu-id="3423a-271">单个浏览器窗口中的空间声音</span><span class="sxs-lookup"><span data-stu-id="3423a-271">Spatial sound from a single browser window</span></span>
- <span data-ttu-id="3423a-272">浏览器的自动和手动更新</span><span class="sxs-lookup"><span data-stu-id="3423a-272">Automatic and manual updating of the browser</span></span>
- <span data-ttu-id="3423a-273">使用"保存到 PDF" (从"打印"菜单中保存 PDF) </span><span class="sxs-lookup"><span data-stu-id="3423a-273">Saving a PDF from the Print menu (using "Save to PDF" option)</span></span>
- <span data-ttu-id="3423a-274">WebXR 和 360 Viewer 扩展</span><span class="sxs-lookup"><span data-stu-id="3423a-274">WebXR and 360 Viewer extension</span></span>
- <span data-ttu-id="3423a-275">在环境中放置的多个窗口之间浏览时，内容还原以更正窗口</span><span class="sxs-lookup"><span data-stu-id="3423a-275">Content restoration to correct window, when browsing across multiple windows placed in your environment</span></span>

**<span data-ttu-id="3423a-276">不应工作的方案和功能：</span><span class="sxs-lookup"><span data-stu-id="3423a-276">Scenarios and features not expected to work:</span></span>**
- <span data-ttu-id="3423a-277">具有同时音频流的多个窗口的空间声音</span><span class="sxs-lookup"><span data-stu-id="3423a-277">Spatial sound from multiple windows with simultaneous audio streams</span></span>
- <span data-ttu-id="3423a-278">"看到它，说它"</span><span class="sxs-lookup"><span data-stu-id="3423a-278">"See it, say it"</span></span>
- <span data-ttu-id="3423a-279">打印</span><span class="sxs-lookup"><span data-stu-id="3423a-279">Printing</span></span>

**<span data-ttu-id="3423a-280">热门已知浏览器问题：</span><span class="sxs-lookup"><span data-stu-id="3423a-280">Top known browser issues:</span></span>**
- <span data-ttu-id="3423a-281">重置设备将删除新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3423a-281">Resetting your device will remove the new Microsoft Edge</span></span>
- <span data-ttu-id="3423a-282">全息键盘中的放大镜预览显示不正确的内容</span><span class="sxs-lookup"><span data-stu-id="3423a-282">The magnifier preview in the holographic keyboard shows incorrect content</span></span>
- <span data-ttu-id="3423a-283">滚动有时可能会不流畅</span><span class="sxs-lookup"><span data-stu-id="3423a-283">Scrolling can sometimes stutter</span></span>
- <span data-ttu-id="3423a-284">Microsoft Store 应用中的 Web 链接可能无法启动浏览器</span><span class="sxs-lookup"><span data-stu-id="3423a-284">Web links in the Microsoft Store app may not launch the browser</span></span>
- <span data-ttu-id="3423a-285">如果之前从不同的浏览器窗口播放过音频，则可能会从错误的浏览器窗口播放音频</span><span class="sxs-lookup"><span data-stu-id="3423a-285">Audio may play from the wrong browser window if you've previously played audio from a different browser window</span></span>

#### <a name="microsoft-edge-insider-channels"></a><span data-ttu-id="3423a-286">Microsoft Edge 预览体验成员频道</span><span class="sxs-lookup"><span data-stu-id="3423a-286">Microsoft Edge Insider channels</span></span>

<span data-ttu-id="3423a-287">Microsoft Edge 团队向 Edge 预览体验成员社区提供三个预览频道：Beta、Dev 和 Canary。</span><span class="sxs-lookup"><span data-stu-id="3423a-287">The Microsoft Edge team makes three preview channels available to the Edge Insider community: Beta, Dev, and Canary.</span></span> <span data-ttu-id="3423a-288">安装预览通道不会卸载 HoloLens 2 上发布的 Microsoft Edge 版本，并且可以同时安装多个。</span><span class="sxs-lookup"><span data-stu-id="3423a-288">Installing a preview channel doesn't uninstall the released version of Microsoft Edge on your HoloLens 2, and you can install more than one at the same time.</span></span> 

<span data-ttu-id="3423a-289">访问 [Microsoft Edge 预览体验成员主页](https://www.microsoftedgeinsider.com) ，详细了解 Edge 预览体验成员社区。</span><span class="sxs-lookup"><span data-stu-id="3423a-289">Visit the [Microsoft Edge Insider homepage](https://www.microsoftedgeinsider.com) to learn more about the Edge Insider community.</span></span> <span data-ttu-id="3423a-290">若要了解有关不同 Edge 预览体验成员频道和入门信息，请访问 [Edge 预览体验成员下载页面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="3423a-290">To learn more about the different Edge Insider channels and get started, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>

<span data-ttu-id="3423a-291">有两种方法可用于将 Microsoft Edge 预览体验成员频道安装到 HoloLens 2：</span><span class="sxs-lookup"><span data-stu-id="3423a-291">There are a couple methods available for installing Microsoft Edge Insider channels to HoloLens 2:</span></span>

**<span data-ttu-id="3423a-292">直接安装在设备上 (当前仅适用于非托管设备) </span><span class="sxs-lookup"><span data-stu-id="3423a-292">Direct install on device (currently only available to unmanaged devices)</span></span>**
  1. <span data-ttu-id="3423a-293">在 HoloLens 2 上，访问 [Edge 预览体验成员下载页面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="3423a-293">On your HoloLens 2, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>
  1. <span data-ttu-id="3423a-294">为你要 **安装的边缘预览体验成员频道选择适用于 HoloLens 2** 的下载按钮。</span><span class="sxs-lookup"><span data-stu-id="3423a-294">Select the **Download for HoloLens 2** button for the Edge Insider channel you wish to install.</span></span>
  1. <span data-ttu-id="3423a-295">使用"文件资源管理器" (从边缘下载队列或设备的"下载"文件夹中启动下载的 .msix) 。</span><span class="sxs-lookup"><span data-stu-id="3423a-295">Launch the downloaded .msix file from the Edge download queue or from your device's "Downloads" folder (using File Explorer).</span></span>
  1. <span data-ttu-id="3423a-296">[应用安装程序](app-deploy-app-installer.md) 将启动。</span><span class="sxs-lookup"><span data-stu-id="3423a-296">[App installer](app-deploy-app-installer.md) will launch.</span></span>
  1. <span data-ttu-id="3423a-297">选择" **安装"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="3423a-297">Select the **Install** button.</span></span>
  1. <span data-ttu-id="3423a-298">成功安装后，你将在"开始"菜单的"所有应用"列表中找到 Microsoft Edge Beta、Dev 或 Canary 作为单独的条目。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3423a-298">After successful install, you'll find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu.</span></span>

**<span data-ttu-id="3423a-299">使用 Windows Device Portal [ (电脑安装](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) 需要在 HoloLens 2 设备上启用开发人员) </span><span class="sxs-lookup"><span data-stu-id="3423a-299">Install via PC with Windows Device Portal (requires [developer mode](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) to be enabled on HoloLens 2)</span></span>**
  1. <span data-ttu-id="3423a-300">在电脑上，访问 [Edge 预览体验成员下载页面](https://www.microsoftedgeinsider.com/download)。</span><span class="sxs-lookup"><span data-stu-id="3423a-300">On your PC, visit the [Edge Insider download page](https://www.microsoftedgeinsider.com/download).</span></span>
  1. <span data-ttu-id="3423a-301">选择要 **安装** 的边缘预览体验成员频道的"下载适用于 Windows 10"按钮旁边的下拉箭头按钮。</span><span class="sxs-lookup"><span data-stu-id="3423a-301">Select the **drop-down arrow button** next to the "Download for Windows 10" button for the Edge Insider channel you wish to install.</span></span>
  1. <span data-ttu-id="3423a-302">在**下拉菜单中选择 HoloLens 2。**</span><span class="sxs-lookup"><span data-stu-id="3423a-302">Select **HoloLens 2** in the drop-down menu.</span></span>
  1. <span data-ttu-id="3423a-303">将 .msix 文件保存到电脑文件夹的"下载 (或其他文件夹，你可以轻松找到) 。</span><span class="sxs-lookup"><span data-stu-id="3423a-303">Save the .msix file to the "Downloads" folder of your PC (or another folder you can easily find).</span></span>
  1. <span data-ttu-id="3423a-304">使用 [电脑上的 Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 在 HoloLens 2 上安装下载的 .msix 文件。</span><span class="sxs-lookup"><span data-stu-id="3423a-304">Use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) on your PC to install the downloaded .msix file on HoloLens 2.</span></span>
  1. <span data-ttu-id="3423a-305">成功安装后，你将在"开始"菜单的"所有应用"列表中找到 Microsoft Edge Beta、Dev 或 Canary 作为单独的条目。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3423a-305">After successful install, you'll find Microsoft Edge Beta, Dev, or Canary as a separate entry in the **All apps** list of the Start menu.</span></span>

> [!NOTE]
> <span data-ttu-id="3423a-306">在此适用于 HoloLens 2 的 Windows Insider Preview 期间，你的设备上 Microsoft Edge 的版本可能高于 Microsoft Edge 预览体验成员频道的 (或所有) 中提供的版本。</span><span class="sxs-lookup"><span data-stu-id="3423a-306">During this Windows Insider preview for HoloLens 2, the version of Microsoft Edge on your device may be higher than those available in some (or all) of the Microsoft Edge Insider channels.</span></span> <span data-ttu-id="3423a-307">这是为了确保专门针对 HoloLens 2 上的 Web 浏览器的新功能和修补程序尽快向 Windows 预览体验成员提供。</span><span class="sxs-lookup"><span data-stu-id="3423a-307">This is to ensure new features and fixes specifically targeting the web browser on HoloLens 2 are getting to our Windows Insiders as quickly as possible.</span></span> <span data-ttu-id="3423a-308">在公开发布下一个 Windows 更新后，Microsoft Edge 预览体验成员频道版本将超过 HoloLens 2 上的 Microsoft Edge 版本，并保持领先。</span><span class="sxs-lookup"><span data-stu-id="3423a-308">Shortly after the public release of the next Windows update, the Microsoft Edge Insider channel builds will surpass, and stay ahead of, the version of Microsoft Edge on your HoloLens 2.</span></span>

#### <a name="using-wdac-to-block-new-microsoft-edge"></a><span data-ttu-id="3423a-309">使用 WDAC 阻止新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3423a-309">Using WDAC to block new Microsoft Edge</span></span>

<span data-ttu-id="3423a-310">对于想要更新 [WDAC](windows-defender-application-control-wdac.md) 策略以阻止新 Microsoft Edge 应用的 IT 管理员，你需要将以下内容添加到策略中。</span><span class="sxs-lookup"><span data-stu-id="3423a-310">For IT Admins looking to update their [WDAC policy](windows-defender-application-control-wdac.md) to block the new Microsoft Edge app, you'll need to add the following to your policy.</span></span>

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a><span data-ttu-id="3423a-311">管理新 Microsoft Edge 的终结点</span><span class="sxs-lookup"><span data-stu-id="3423a-311">Managing endpoints for the new Microsoft Edge</span></span>

<span data-ttu-id="3423a-312">一些环境可能需要考虑网络限制。</span><span class="sxs-lookup"><span data-stu-id="3423a-312">Some environments may have network restrictions to account for as a consideration.</span></span> <span data-ttu-id="3423a-313">若要确保新 Edge 的流畅体验， [请启用这些 Microsoft 终结点。](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)</span><span class="sxs-lookup"><span data-stu-id="3423a-313">To ensure a smooth experience with the new Edge please [enable these Microsoft endpoints.](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)</span></span>

<span data-ttu-id="3423a-314">阅读有关 [HoloLens](hololens-offline.md)当前可用终结点的信息。</span><span class="sxs-lookup"><span data-stu-id="3423a-314">Read more about the currently available [endpoints for HoloLens](hololens-offline.md).</span></span>

### <a name="webxr-and-360-viewer"></a><span data-ttu-id="3423a-315">WebXR 和 360 Viewer</span><span class="sxs-lookup"><span data-stu-id="3423a-315">WebXR and 360 Viewer</span></span>

*<span data-ttu-id="3423a-316">已添加到 Windows 预览体验成员版本 20289.1000</span><span class="sxs-lookup"><span data-stu-id="3423a-316">Added in Windows Insider build 20289.1000</span></span>*

<span data-ttu-id="3423a-317">新的 Microsoft Edge 支持 WebXR，这是创建沉浸式 Web 体验的新标准， (WebVR) 。</span><span class="sxs-lookup"><span data-stu-id="3423a-317">The new Microsoft Edge includes support for WebXR, which is the new standard for creating immersive web experiences (replacing WebVR).</span></span> <span data-ttu-id="3423a-318">许多沉浸式 Web 体验在设计时都考虑到了 (将你的视野替换为虚拟环境) ，但 HoloLens 2 也支持这些体验。</span><span class="sxs-lookup"><span data-stu-id="3423a-318">Many immersive web experiences were designed with VR in mind (they replace your field of view with a virtual environment), but these experiences are also supported by HoloLens 2.</span></span> <span data-ttu-id="3423a-319">WebXR 标准还支持使用物理环境的增强和混合现实沉浸式 Web 体验。</span><span class="sxs-lookup"><span data-stu-id="3423a-319">The WebXR standard also enables augmented and mixed reality immersive web experiences that use your physical environment.</span></span> <span data-ttu-id="3423a-320">随着开发人员在 WebXR 上花费更多时间，我们预计新的增强和混合现实沉浸式体验将到达 HoloLens 2 客户试用！</span><span class="sxs-lookup"><span data-stu-id="3423a-320">As developers spend more time with WebXR, we anticipate new augmented and mixed reality immersive experiences will arrive for HoloLens 2 customers to try!</span></span>

<span data-ttu-id="3423a-321">360 Viewer 扩展基于 WebXR 构建，并自动随 HoloLens 2 上的新 Microsoft Edge 一起安装。</span><span class="sxs-lookup"><span data-stu-id="3423a-321">The 360 Viewer extension is built on WebXR and automatically installs alongside the new Microsoft Edge on HoloLens 2.</span></span> <span data-ttu-id="3423a-322">此 Web 扩展让你能够沉浸于 360 度的视频中。</span><span class="sxs-lookup"><span data-stu-id="3423a-322">This web extension gives you the ability to immerse yourself in 360-degree videos.</span></span> <span data-ttu-id="3423a-323">YouTube 提供最多 360 个视频选择，因此我们建议您从该视频开始。</span><span class="sxs-lookup"><span data-stu-id="3423a-323">YouTube offers the largest selection of 360 videos, so we encourage you to start there.</span></span>

#### <a name="how-to-use-webxr"></a><span data-ttu-id="3423a-324">如何使用 WebXR</span><span class="sxs-lookup"><span data-stu-id="3423a-324">How to use WebXR</span></span>

1. <span data-ttu-id="3423a-325">导航到具有 WebXR 支持的网站。</span><span class="sxs-lookup"><span data-stu-id="3423a-325">Navigate to a website with WebXR support.</span></span>
1. <span data-ttu-id="3423a-326">选择网站上 **"输入 VR"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="3423a-326">Select the **Enter VR** button on the website.</span></span> <span data-ttu-id="3423a-327">此按钮的位置和视觉表示形式可能因网站而异，但它可能类似于：</span><span class="sxs-lookup"><span data-stu-id="3423a-327">The location and visual representation of this button may vary per website, but it may look similar to:</span></span>

    ![输入 VR 按钮示例](images/75px-enter-vr.png)

1. <span data-ttu-id="3423a-329">首次尝试启动特定域上的 WebXR 体验时，浏览器会请求同意进入沉浸式视图，选择"允许 **"。**</span><span class="sxs-lookup"><span data-stu-id="3423a-329">The first time you try to launch a WebXR experience on a specific domain, the browser will ask for consent to enter an immersive view, select **Allow**.</span></span>
1. <span data-ttu-id="3423a-330">使用 [HoloLens 2 手势](hololens2-basic-usage.md#the-hand-tracking-frame) 操作体验。</span><span class="sxs-lookup"><span data-stu-id="3423a-330">Use [HoloLens 2 gestures](hololens2-basic-usage.md#the-hand-tracking-frame) to manipulate the experience.</span></span>
1. <span data-ttu-id="3423a-331">如果体验没有 **退出按钮，** 请使用开始 [手势](hololens2-basic-usage.md#start-gesture) 返回主页。</span><span class="sxs-lookup"><span data-stu-id="3423a-331">If the experience doesn't have an **Exit** button, use the [Start gesture](hololens2-basic-usage.md#start-gesture) to return home.</span></span>

**<span data-ttu-id="3423a-332">建议的 WebXR 示例</span><span class="sxs-lookup"><span data-stu-id="3423a-332">Recommended WebXR samples</span></span>**
- <span data-ttu-id="3423a-333">360 Viewer (请参阅下一部分) </span><span class="sxs-lookup"><span data-stu-id="3423a-333">360 Viewer (see next section)</span></span>
- [<span data-ttu-id="3423a-334">XR 恐龙</span><span class="sxs-lookup"><span data-stu-id="3423a-334">XR Dinosaurs</span></span>](https://www.xrdinosaurs.com/)
- [<span data-ttu-id="3423a-335">Barista Express</span><span class="sxs-lookup"><span data-stu-id="3423a-335">Barista Express</span></span>](https://constructarca.de/game/barista-express/)
- [<span data-ttu-id="3423a-336">WebXR 画图</span><span class="sxs-lookup"><span data-stu-id="3423a-336">WebXR Paint</span></span>](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a><span data-ttu-id="3423a-337">如何使用 360 查看器</span><span class="sxs-lookup"><span data-stu-id="3423a-337">How to use 360 Viewer</span></span>

1. <span data-ttu-id="3423a-338">导航到 YouTube 上的 360 度视频。</span><span class="sxs-lookup"><span data-stu-id="3423a-338">Navigate to a 360-degree video on YouTube.</span></span>
1. <span data-ttu-id="3423a-339">在视频帧中，选择混合现实头戴显示设备按钮：</span><span class="sxs-lookup"><span data-stu-id="3423a-339">In the video frame, select the mixed reality headset button:</span></span>

    ![用于激活 360 查看器的按钮](images/enter-360-viewer.jpg)

1. <span data-ttu-id="3423a-341">首次尝试启动特定域上的 360 查看器时，浏览器会请求同意进入沉浸式视图。</span><span class="sxs-lookup"><span data-stu-id="3423a-341">The first time you try to launch 360 Viewer on a specific domain, the browser will ask for consent to enter an immersive view.</span></span> <span data-ttu-id="3423a-342">选择 **"允许"。**</span><span class="sxs-lookup"><span data-stu-id="3423a-342">Select **Allow**.</span></span>
1. <span data-ttu-id="3423a-343">[空敲](hololens2-basic-usage.md#select-using-air-tap) 以打开播放控件。</span><span class="sxs-lookup"><span data-stu-id="3423a-343">[Air tap](hololens2-basic-usage.md#select-using-air-tap) to bring up the playback controls.</span></span> <span data-ttu-id="3423a-344">使用 [手部](hololens2-basic-usage.md#select-using-air-tap) 光线和空敲击播放/暂停、跳过前进/后退、打开/关闭描述文字或停止体验 (退出沉浸式视图) 。</span><span class="sxs-lookup"><span data-stu-id="3423a-344">Use [hand rays and air tap](hololens2-basic-usage.md#select-using-air-tap) to play/pause, skip forward/back, turn captions on/off, or stop the experience (which exits the immersive view).</span></span> <span data-ttu-id="3423a-345">在几秒钟的不活动状态后，播放控件将消失。</span><span class="sxs-lookup"><span data-stu-id="3423a-345">The playback controls will disappear after a few seconds of inactivity.</span></span>

#### <a name="top-webxr-and-360-viewer-known-issues"></a><span data-ttu-id="3423a-346">热门 WebXR 和 360 Viewer 已知问题</span><span class="sxs-lookup"><span data-stu-id="3423a-346">Top WebXR and 360 Viewer known issues</span></span>
- <span data-ttu-id="3423a-347">在 WebXR 体验中，当你倾斜头部或四处移动时，全息影像可能会移动或倾斜。</span><span class="sxs-lookup"><span data-stu-id="3423a-347">In WebXR experiences, holograms may shift or tilt when you tilt your head or move around your environment.</span></span>
- <span data-ttu-id="3423a-348">根据 WebXR 体验的复杂性，帧速率可能会下降或断断续续。</span><span class="sxs-lookup"><span data-stu-id="3423a-348">Depending on the complexity of the WebXR experience, the framerate may drop or stutter.</span></span>
- <span data-ttu-id="3423a-349">WebXR 中尚不可用手部连接。</span><span class="sxs-lookup"><span data-stu-id="3423a-349">Articulated hand joints are not yet available in WebXR.</span></span>
- <span data-ttu-id="3423a-350">退出 WebXR 或 360 查看器体验时，混合现实主页中的全息影像可能需要 30 秒或更多时间重新出现。</span><span class="sxs-lookup"><span data-stu-id="3423a-350">When exiting a WebXR or 360 Viewer experience, it may take 30 seconds or more for holograms in the mixed reality home to reappear.</span></span>
- <span data-ttu-id="3423a-351">YouTube 外的其他网站的 360 个视频可能无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="3423a-351">360 videos from websites other than YouTube may not work as expected.</span></span>
- <span data-ttu-id="3423a-352">如果 360 个视频未进入沉浸式 (或混合现实头戴显示设备按钮未) ，请尝试刷新页面。</span><span class="sxs-lookup"><span data-stu-id="3423a-352">If 360 videos don't enter immersive view (or the mixed reality headset button doesn't appear), try refreshing the page.</span></span>
- <span data-ttu-id="3423a-353">标题在 HoloLens 2 上的 360 查看器中尚不可见。</span><span class="sxs-lookup"><span data-stu-id="3423a-353">Captions are not yet visible in 360 Viewer on HoloLens 2.</span></span>
- <span data-ttu-id="3423a-354">在 360 查看器中暂停视频会阻止视频呈现 (但选择播放按钮会正确恢复) 。</span><span class="sxs-lookup"><span data-stu-id="3423a-354">Pausing a video in 360 Viewer stops the video from rendering (but selecting the play button correctly resumes playback).</span></span>
- <span data-ttu-id="3423a-355">360 Viewer 中的"下一个视频"按钮当前不起作用。</span><span class="sxs-lookup"><span data-stu-id="3423a-355">The "next video" button in 360 Viewer does not currently work.</span></span>
- <span data-ttu-id="3423a-356">可以在沉浸式"theater"模式下播放 2D 视频，但帧速率将小于 30 fps。</span><span class="sxs-lookup"><span data-stu-id="3423a-356">You can play 2D videos in an immersive "theater" mode, but the framerate will be less than 30 fps.</span></span>

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a><span data-ttu-id="3423a-357">在 WebXR 和 360 查看器上提供反馈</span><span class="sxs-lookup"><span data-stu-id="3423a-357">Providing feedback on WebXR and 360 Viewer</span></span>

<span data-ttu-id="3423a-358">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="3423a-358">Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge.</span></span>

### <a name="new-settings-app"></a><span data-ttu-id="3423a-359">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="3423a-359">New Settings app</span></span>

<span data-ttu-id="3423a-360">在此版本中，我们将引入新版本的"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="3423a-360">With this release, we're introducing a new version of the Settings app.</span></span> <span data-ttu-id="3423a-361">新的设置应用包括 HoloLens 2 的新功能和扩展设置，包括以下方面：声音、电源 & 睡眠、网络 & Internet、应用、帐户、轻松使用等。</span><span class="sxs-lookup"><span data-stu-id="3423a-361">The new Settings app includes new features and expanded settings for HoloLens 2 in the following areas: Sound, Power & sleep, Network & Internet, Apps, Accounts, Ease of Access, and more.</span></span>

> [!NOTE]
> <span data-ttu-id="3423a-362">由于新的"设置"应用不同于旧"设置"应用，因此更新时将删除之前围绕环境放置的任何"设置"窗口。</span><span class="sxs-lookup"><span data-stu-id="3423a-362">Because the new Settings app is distinct from the legacy Settings app, any Settings windows you previously placed around your environment will be removed upon update.</span></span>

!["新建设置"应用主页](images/new-settings-app.png)

**<span data-ttu-id="3423a-364">新功能和设置</span><span class="sxs-lookup"><span data-stu-id="3423a-364">New features and settings</span></span>**
- <span data-ttu-id="3423a-365">设置搜索：使用关键字或设置名称从"设置"主页搜索设置。</span><span class="sxs-lookup"><span data-stu-id="3423a-365">Settings search: search for settings from the Settings homepage using keywords or the setting's name.</span></span>
- <span data-ttu-id="3423a-366">系统>声音：</span><span class="sxs-lookup"><span data-stu-id="3423a-366">System > Sound:</span></span>
  - <span data-ttu-id="3423a-367">输入和输出音频设备：独立选择输入和输出音频设备 (例如，通过 Bluetooth 耳机收听音频或使用 USB-C 麦克风进行音频输入) 。</span><span class="sxs-lookup"><span data-stu-id="3423a-367">Input and output audio devices: independently choose your input and output audio devices (for example, listen to audio via Bluetooth headphones or use a USB-C microphone for audio input).</span></span>
    > [!NOTE]
    > <span data-ttu-id="3423a-368">Bluetooth HoloLens 2 不支持麦克风。</span><span class="sxs-lookup"><span data-stu-id="3423a-368">Bluetooth microphones are not supported by HoloLens 2.</span></span>
  - <span data-ttu-id="3423a-369">应用量：独立调整每个应用的音量。</span><span class="sxs-lookup"><span data-stu-id="3423a-369">App volume: independently adjust the volume of each app.</span></span> <span data-ttu-id="3423a-370">请参阅 [每个应用音量控制](#per-app-volume-control)。</span><span class="sxs-lookup"><span data-stu-id="3423a-370">See [per app volume control](#per-app-volume-control).</span></span>
- <span data-ttu-id="3423a-371">系统>电源&睡眠：选择设备在一段时间不活动后应进入睡眠状态的时间。</span><span class="sxs-lookup"><span data-stu-id="3423a-371">System > Power & sleep: choose when the device should go to sleep after a period of inactivity.</span></span>
- <span data-ttu-id="3423a-372">系统>电池：手动启用节电模式或设置节电模式自动打开的电池阈值。</span><span class="sxs-lookup"><span data-stu-id="3423a-372">System > Battery: manually enable battery saver mode or set a battery threshold at which point battery saver mode turns on automatically.</span></span>
- <span data-ttu-id="3423a-373">设备> USB：默认情况下可以禁用 USB 连接。</span><span class="sxs-lookup"><span data-stu-id="3423a-373">Devices > USB: you can disable USB connections by default.</span></span>
- <span data-ttu-id="3423a-374">网络& Internet：</span><span class="sxs-lookup"><span data-stu-id="3423a-374">Network & Internet:</span></span>
  - <span data-ttu-id="3423a-375">USB-C 以太网适配器现在将显示在 Network & Internet 中。</span><span class="sxs-lookup"><span data-stu-id="3423a-375">USB-C Ethernet adapters will now appear in Network & Internet.</span></span>
  - <span data-ttu-id="3423a-376">USB-C 以太网适配器设置现已可用，包括其 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="3423a-376">USB-C Ethernet adapter settings are now available, including its IP address.</span></span>
  - <span data-ttu-id="3423a-377">现在可以在 HoloLens 2 上启用飞行模式。</span><span class="sxs-lookup"><span data-stu-id="3423a-377">You can now enable airplane mode on HoloLens 2.</span></span>
- <span data-ttu-id="3423a-378">应用：可以重置用于文件和链接类型的默认应用。</span><span class="sxs-lookup"><span data-stu-id="3423a-378">Apps: you can reset the default apps used for file and link types.</span></span> <span data-ttu-id="3423a-379">有关详细信息，请参阅默认 [应用选取器](#default-app-picker)。</span><span class="sxs-lookup"><span data-stu-id="3423a-379">For more information see [Default app picker](#default-app-picker).</span></span>
- <span data-ttu-id="3423a-380">帐户>其他用户：设备所有者可以添加用户、将标准用户升级到设备所有者、将设备所有者降级为标准用户以及删除用户。</span><span class="sxs-lookup"><span data-stu-id="3423a-380">Accounts > Other users: device owners can add users, upgrade standard users to device owners, downgrade device owners to standard users, and remove users.</span></span>
- <span data-ttu-id="3423a-381">轻松使用：更改文本大小和一些视觉效果。</span><span class="sxs-lookup"><span data-stu-id="3423a-381">Ease of Access: change text size and some visual effects.</span></span>

**<span data-ttu-id="3423a-382">已知问题</span><span class="sxs-lookup"><span data-stu-id="3423a-382">Known issues</span></span>**
- <span data-ttu-id="3423a-383">之前放置的设置窗口将被删除 (请参阅上述) 。</span><span class="sxs-lookup"><span data-stu-id="3423a-383">Previously placed Settings windows will be removed (see note above).</span></span>
- <span data-ttu-id="3423a-384">你无法再使用"设置"应用重命名设备。</span><span class="sxs-lookup"><span data-stu-id="3423a-384">You can no longer rename your device with the Settings app.</span></span> <span data-ttu-id="3423a-385">IT 管理员可以使用 [适用于 HoloLens 2 的 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot) 设备名称模板或 MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 节点重命名设备。</span><span class="sxs-lookup"><span data-stu-id="3423a-385">IT admins can rename devices by using the [Windows Autopilot for HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) device name template or the MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName node.</span></span>
- <span data-ttu-id="3423a-386">以太网页面显示一个 ( UsbNcm") 虚拟以太网设备。</span><span class="sxs-lookup"><span data-stu-id="3423a-386">The Ethernet page shows a virtual Ethernet device ("UsbNcm") at all times.</span></span>
- <span data-ttu-id="3423a-387">新 Microsoft Edge 的电池使用情况可能不准确，由于其性质是 UWP 适配器层支持的 Win32 桌面应用程序， (即将修复) 。</span><span class="sxs-lookup"><span data-stu-id="3423a-387">Battery usage for the new Microsoft Edge may not be accurate, due to its nature as a Win32 desktop application supported by a UWP adapter layer (no fix anticipated soon).</span></span>

### <a name="display-color-calibration"></a><span data-ttu-id="3423a-388">显示颜色校准</span><span class="sxs-lookup"><span data-stu-id="3423a-388">Display color calibration</span></span>

*<span data-ttu-id="3423a-389">已添加到 Windows 预览体验成员版本 20293.1000</span><span class="sxs-lookup"><span data-stu-id="3423a-389">Added in Windows Insider build 20293.1000</span></span>*

<span data-ttu-id="3423a-390">借助这一新设置，你可以为 HoloLens 2 屏幕选择备用颜色配置文件。</span><span class="sxs-lookup"><span data-stu-id="3423a-390">With this new setting, you can select an alternative color profile for your HoloLens 2 display.</span></span> <span data-ttu-id="3423a-391">这可以帮助颜色显示更准确，尤其是在较低的显示亮度级别下。</span><span class="sxs-lookup"><span data-stu-id="3423a-391">This may help colors appear more accurate, especially at lower display brightness levels.</span></span> <span data-ttu-id="3423a-392">显示颜色校准可在"设置"应用的"系统校准>找到。</span><span class="sxs-lookup"><span data-stu-id="3423a-392">Display color calibration can be found in the Settings app, on the System > Calibration page.</span></span>

> [!NOTE]
> <span data-ttu-id="3423a-393">由于此设置将新的颜色配置文件保存到显示固件，因此它是每个设备设置 (，而不是每个用户帐户设置) 。</span><span class="sxs-lookup"><span data-stu-id="3423a-393">Because this setting saves a new color profile to your display firmware, it is a per-device setting (and not unique to each user account).</span></span>

#### <a name="how-to-use-display-color-calibration"></a><span data-ttu-id="3423a-394">如何使用显示颜色校准</span><span class="sxs-lookup"><span data-stu-id="3423a-394">How to use display color calibration</span></span>

1. <span data-ttu-id="3423a-395">启动"**设置"** 应用并导航到 **"系统>校准"。**</span><span class="sxs-lookup"><span data-stu-id="3423a-395">Launch the **Settings** app and navigate to **System > Calibration**.</span></span>
1. <span data-ttu-id="3423a-396">在 **"显示颜色校准"** 下，选择" **运行显示颜色校准"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="3423a-396">Under **Display color calibration**, select the **Run display color calibration** button.</span></span>
1. <span data-ttu-id="3423a-397">显示颜色校准体验将启动并鼓励你确保面罩处于正确的位置。</span><span class="sxs-lookup"><span data-stu-id="3423a-397">The display color calibration experience will launch and encourage you to make sure your visor is in the correct position.</span></span>
1. <span data-ttu-id="3423a-398">继续执行指令对话框后，屏幕将自动变暗为 30% 的亮度。</span><span class="sxs-lookup"><span data-stu-id="3423a-398">After you proceed through the instruction dialog boxes, your display will automatically be dimmed to 30% brightness.</span></span>
    > [!TIP]
    > <span data-ttu-id="3423a-399">如果你在看到环境中灰显的场景时遇到问题，可以使用设备左侧的亮度按钮手动调整 HoloLens 2 的亮度级别。</span><span class="sxs-lookup"><span data-stu-id="3423a-399">If you're having trouble seeing the dimmed scene in your environment, you can manually adjust the brightness level of HoloLens 2 using the brightness buttons on the left side of the device.</span></span>
1. <span data-ttu-id="3423a-400">选择按钮 1-6 可立即试用每个颜色配置文件，并找到最符合你的眼睛外观的配置文件 (这通常意味着帮助场景显示最中性的个人资料，灰度图案和眼音按预期显示。) </span><span class="sxs-lookup"><span data-stu-id="3423a-400">Select buttons 1-6 to instantly try out each color profile, and find one that looks the best to your eyes (this usually means the profile that helps the scene appear most neutral, with the grayscale pattern and skin tones looking as expected.)</span></span>

    ![显示颜色校准场景](images/color-cal-ui.png)
    
1. <span data-ttu-id="3423a-402">如果对所选的配置文件满意，请选择"保存& **退出"** 按钮</span><span class="sxs-lookup"><span data-stu-id="3423a-402">When you're happy with the selected profile, select the **Save & Exit** button</span></span>
1. <span data-ttu-id="3423a-403">如果您不希望进行更改，请选择"取消& **退出"** 按钮，更改将还原</span><span class="sxs-lookup"><span data-stu-id="3423a-403">If you prefer not to make changes, select the **Cancel & Exit** button and your changes will be reverted</span></span>

> [!TIP]
> <span data-ttu-id="3423a-404">以下是在使用显示颜色校准设置时请记住的一些有用提示：</span><span class="sxs-lookup"><span data-stu-id="3423a-404">Here are some helpful tips to keep in mind while using the display color calibration setting:</span></span>
> - <span data-ttu-id="3423a-405">你可以随时从"设置"重新运行显示颜色校准</span><span class="sxs-lookup"><span data-stu-id="3423a-405">You can re-run display color calibration from Settings whenever you'd like</span></span>
> - <span data-ttu-id="3423a-406">如果设备上有人之前已使用此设置更改颜色配置文件，最新更改的日期/时间将反映在"设置"页面上</span><span class="sxs-lookup"><span data-stu-id="3423a-406">If anyone on the device has previously used the setting to change color profiles, the date/time of the most recent change will be reflected on the Settings page</span></span>
> - <span data-ttu-id="3423a-407">重新运行显示颜色校准时，将突出显示之前保存的颜色配置文件，并且配置文件 0 不会 (因为配置文件 0 表示显示的原始颜色配置文件) </span><span class="sxs-lookup"><span data-stu-id="3423a-407">When you re-run display color calibration, the color profile that was previously saved will be highlighted and Profile 0 will not appear (as Profile 0 represents the display's original color profile)</span></span>
> - <span data-ttu-id="3423a-408">如果要还原为显示的原始颜色配置文件，可以从"设置"页 (了解如何重置颜色配置文件) [](#how-to-reset-color-profile)</span><span class="sxs-lookup"><span data-stu-id="3423a-408">If you want to revert to the display's original color profile, you can do so from the Settings page (see [how to reset color profile](#how-to-reset-color-profile))</span></span>

#### <a name="how-to-reset-color-profile"></a><span data-ttu-id="3423a-409">如何重置颜色配置文件</span><span class="sxs-lookup"><span data-stu-id="3423a-409">How to reset color profile</span></span>

<span data-ttu-id="3423a-410">如果你对保存到 HoloLens 2 的自定义颜色配置文件不满意，你可以还原设备的原始颜色配置文件：</span><span class="sxs-lookup"><span data-stu-id="3423a-410">If you're unhappy with the custom color profile saved to your HoloLens 2, you can restore the device's original color profile:</span></span>
1. <span data-ttu-id="3423a-411">启动"**设置"** 应用并导航到 **"系统>校准"。**</span><span class="sxs-lookup"><span data-stu-id="3423a-411">Launch the **Settings** app and navigate to **System > Calibration**.</span></span>
1. <span data-ttu-id="3423a-412">在 **"显示颜色校准"** 下，选择 **"重置为默认颜色配置文件"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="3423a-412">Under **Display color calibration**, select the **Reset to default color profile** button.</span></span>
1. <span data-ttu-id="3423a-413">对话框打开后，如果已准备好重启\*\*\*\* HoloLens 2 并应用更改，请选择"重启"。</span><span class="sxs-lookup"><span data-stu-id="3423a-413">When the dialog box opens, select **Restart** if you're ready to restart HoloLens 2 and apply your changes.</span></span>

#### <a name="top-display-color-calibration-known-issues"></a><span data-ttu-id="3423a-414">顶部显示颜色校准已知问题</span><span class="sxs-lookup"><span data-stu-id="3423a-414">Top display color calibration known issues</span></span>

- <span data-ttu-id="3423a-415">在"设置"页上，在重新加载"设置"页之前，告知您上次更改颜色配置文件时间的状态字符串将过期。</span><span class="sxs-lookup"><span data-stu-id="3423a-415">On the Settings page, the status string that tells you when the color profile was last changed will be out of date until you reload that page of Settings</span></span> 
    - <span data-ttu-id="3423a-416">解决方法：选择另一个"设置"页，然后重新选择"校准"页。</span><span class="sxs-lookup"><span data-stu-id="3423a-416">Workaround: Select another Settings page and then re-select the Calibration page.</span></span>
- <span data-ttu-id="3423a-417">如果 HoloLens 2 在运行显示颜色校准时进入睡眠状态，它稍后将恢复为混合现实空间，并且你的屏幕亮度级别仍将变暗。</span><span class="sxs-lookup"><span data-stu-id="3423a-417">If your HoloLens 2 goes to sleep while running display color calibration, it will later resume into the mixed reality home and your display brightness level will still be dimmed.</span></span>
- <span data-ttu-id="3423a-418">你可能需要尝试按设备左侧的亮度按钮向上/向下几次，然后它们才能按预期工作。</span><span class="sxs-lookup"><span data-stu-id="3423a-418">You may need to try pressing the brightness buttons on the left side of your device up/down a few times before they work as expected.</span></span>
- <span data-ttu-id="3423a-419">并非所有市场都完成本地化</span><span class="sxs-lookup"><span data-stu-id="3423a-419">Localization is not complete for all markets</span></span>

### <a name="default-app-picker"></a><span data-ttu-id="3423a-420">默认应用选取器</span><span class="sxs-lookup"><span data-stu-id="3423a-420">Default app picker</span></span>

<span data-ttu-id="3423a-421">当你激活超链接或打开具有多个已安装应用的文件类型（支持它）时，你将看到一个新窗口打开，提示你选择哪个已安装的应用应处理文件或链接类型。</span><span class="sxs-lookup"><span data-stu-id="3423a-421">When you activate a hyperlink or open a file type with more than one installed app, which supports it, you will see a new window open prompting you to select which installed app should handle the file or link type.</span></span> <span data-ttu-id="3423a-422">在此窗口中，还可以选择让所选应用处理文件或链接类型"一次"或"始终"。</span><span class="sxs-lookup"><span data-stu-id="3423a-422">In this window, you can also choose to have the selected app handle the file or link type "Once" or "Always."</span></span>

![应用选取器窗口](images/default-app-picker.png)

<span data-ttu-id="3423a-424">如果你选择"始终"，但后来想要更改哪个应用处理特定文件或链接类型，可以在"设置"或"应用"中重置 **>默认值**。</span><span class="sxs-lookup"><span data-stu-id="3423a-424">If you choose "Always" but later want to change which app handles a particular file or link type, you can reset your saved defaults in **Settings > Apps**.</span></span> <span data-ttu-id="3423a-425">滚动到页面底部，然后选择"文件类型的默认应用\*\*\*\*"和/或"链接类型的默认应用"下的"清除"按钮。</span><span class="sxs-lookup"><span data-stu-id="3423a-425">Scroll to the bottom of the page and select the **Clear** button under "Default apps for file types" and/or "Default apps for link types."</span></span> <span data-ttu-id="3423a-426">与桌面电脑中的类似设置不同，无法重置单个文件类型默认值。</span><span class="sxs-lookup"><span data-stu-id="3423a-426">Unlike the similar setting on desktop PCs, you can't reset individual file type defaults.</span></span>

### <a name="per-app-volume-control"></a><span data-ttu-id="3423a-427">每个应用音量控制</span><span class="sxs-lookup"><span data-stu-id="3423a-427">Per app volume control</span></span>

<span data-ttu-id="3423a-428">现在，在此 Windows 预览体验成员版本中，用户可以手动调整每个应用的音量级别。</span><span class="sxs-lookup"><span data-stu-id="3423a-428">Now in this Windows Insider build users can manually adjust the volume level of each app.</span></span> <span data-ttu-id="3423a-429">这使用户可以更好地关注所需的应用，或在使用多个应用时更好地听到这些应用。</span><span class="sxs-lookup"><span data-stu-id="3423a-429">This allows for users to better focus on the apps that they need to, or better hear when using multiple apps.</span></span> <span data-ttu-id="3423a-430">例如，需要关闭一个应用的数量，同时呼叫另一个人在另一个应用中寻求远程协助。</span><span class="sxs-lookup"><span data-stu-id="3423a-430">Such as needing to turn down volume of one app while calling another person for remote assistance in another.</span></span>

<span data-ttu-id="3423a-431">若要设置单个应用的音量，请**导航到"** 设置""系统声音"，并在"高级声音选项"下选择  ->  \*\*\*\*  ->  \*\*\*\*\*\*应用音量和设备首选项\*\*。</span><span class="sxs-lookup"><span data-stu-id="3423a-431">To set the volume of an individual app navigate to **Settings** -> **System** -> **Sound**, and under Advanced sound options select **App volume and device preferences**.</span></span>

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a><span data-ttu-id="3423a-432">Office Web 应用</span><span class="sxs-lookup"><span data-stu-id="3423a-432">Office web app</span></span>

<span data-ttu-id="3423a-433">Office Web 应用已添加到"开始"菜单中的"所有应用程序"列表中。</span><span class="sxs-lookup"><span data-stu-id="3423a-433">The Office web app has been added to the "All apps" list in the Start menu.</span></span> <span data-ttu-id="3423a-434">此 Web 应用还可以固定到"开始"或卸载。</span><span class="sxs-lookup"><span data-stu-id="3423a-434">This web app can also be pinned to Start or uninstalled.</span></span> <span data-ttu-id="3423a-435">由于这是一个 Web 应用，其功能与通过访问 体验完全匹配 https://www.office.com 。</span><span class="sxs-lookup"><span data-stu-id="3423a-435">Because this is a web app, its functionality matches exactly what you'd experience by visiting https://www.office.com.</span></span> <span data-ttu-id="3423a-436">只有当 HoloLens 2 具有活动的 Internet 连接时，Office Web 应用功能才可用。</span><span class="sxs-lookup"><span data-stu-id="3423a-436">Office web app functionality is only available when your HoloLens 2 has an active internet connection.</span></span>

**<span data-ttu-id="3423a-437">已知问题</span><span class="sxs-lookup"><span data-stu-id="3423a-437">Known issue</span></span>**
- <span data-ttu-id="3423a-438">重置设备将删除 Office Web 应用</span><span class="sxs-lookup"><span data-stu-id="3423a-438">Resetting your device will remove the Office web app</span></span>

### <a name="swipe-to-type"></a><span data-ttu-id="3423a-439">轻扫以键入</span><span class="sxs-lookup"><span data-stu-id="3423a-439">Swipe to type</span></span>

<span data-ttu-id="3423a-440">一些客户发现，通过轻扫要键入的单词的形状，在虚拟键盘上"键入"速度更快，我们正在预览全息键盘的此功能。</span><span class="sxs-lookup"><span data-stu-id="3423a-440">Some customers find it faster to "type" on virtual keyboards by swiping the shape of the word they intend to type, and we're previewing this feature for the holographic keyboard.</span></span> <span data-ttu-id="3423a-441">通过通过全息键盘的平面传递手指的尖角，轻扫该单词的形状，然后从键盘平面撤消手指的尖角，可以一次轻扫一个单词。</span><span class="sxs-lookup"><span data-stu-id="3423a-441">You can swipe one word at a time by passing the tip of your finger through the plane of the holographic keyboard, swiping the shape of the word, and then withdrawing the tip of your finger from the plane of the keyboard.</span></span> <span data-ttu-id="3423a-442">你可以轻扫后续字词，而无需按空格键，只需将手指从键盘上移过字词即可。</span><span class="sxs-lookup"><span data-stu-id="3423a-442">You can swipe follow up words without needing to press the space bar by removing your finger from the keyboard between words.</span></span> <span data-ttu-id="3423a-443">如果你在键盘上看到手指移动后看到轻扫记录，则你将知道该功能正在工作。</span><span class="sxs-lookup"><span data-stu-id="3423a-443">You will know the feature is working if you see a swipe trail following your finger's movement on the keyboard.</span></span>

<span data-ttu-id="3423a-444">请注意，此功能可能难以使用和掌握，因为全息键盘的性质与移动电话显示器和屏幕设备不同，你无法 (手指) 。</span><span class="sxs-lookup"><span data-stu-id="3423a-444">Please note, this feature can be tricky to use and master because of the nature of a holographic keyboard where you don't feel resistance against your finger (unlike a mobile phone display).</span></span> <span data-ttu-id="3423a-445">我们正在评估此功能以公开发布，因此您的反馈非常重要;无论你发现此功能有用还是有反馈反馈，请通过反馈 [中心告诉我们](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="3423a-445">We are evaluating this feature for public release, so your feedback is important; whether you find the feature useful or you have constructive feedback, please let us know via [Feedback Hub](hololens-feedback.md).</span></span>

### <a name="power-menu-from-start"></a><span data-ttu-id="3423a-446">"开始"菜单的电源菜单</span><span class="sxs-lookup"><span data-stu-id="3423a-446">Power menu from Start</span></span>

<span data-ttu-id="3423a-447">允许用户注销、关闭并重新启动设备的新菜单。</span><span class="sxs-lookup"><span data-stu-id="3423a-447">A new menu that allows the user to sign out, shut down and restart the device.</span></span> <span data-ttu-id="3423a-448">HoloLens"开始"屏幕中的指示器，显示系统更新何时可用。</span><span class="sxs-lookup"><span data-stu-id="3423a-448">An indicator in the HoloLens Start screen that shows when a system update is available.</span></span>

#### <a name="how-to-use"></a><span data-ttu-id="3423a-449">如何使用</span><span class="sxs-lookup"><span data-stu-id="3423a-449">How to use</span></span>

1. <span data-ttu-id="3423a-450">使用"开始"手势或说"转到开始" [打开](hololens2-basic-usage.md#start-gesture) HoloLens""开始"屏幕。</span><span class="sxs-lookup"><span data-stu-id="3423a-450">Open the HoloLens Start screen using the [Start gesture](hololens2-basic-usage.md#start-gesture) or saying "Go to Start".</span></span>

2. <span data-ttu-id="3423a-451">请注意用户配置文件图片 (...) 旁边的省略号图标：</span><span class="sxs-lookup"><span data-stu-id="3423a-451">Notice the ellipsis icon (...) next to the user profile picture:</span></span>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. <span data-ttu-id="3423a-452">使用双手或语音命令"Power"选择用户配置文件图片。</span><span class="sxs-lookup"><span data-stu-id="3423a-452">Select the user profile picture using your hands or the voice command "Power".</span></span>

4. <span data-ttu-id="3423a-453">将出现一个菜单，包含"注销"、"重启"或"关闭设备"选项：</span><span class="sxs-lookup"><span data-stu-id="3423a-453">A menu appears with options to Sign out, Restart or Shut down the device:</span></span>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. <span data-ttu-id="3423a-454">选择菜单选项以注销、重启或关闭 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="3423a-454">Select the menu options to sign out, restart or shut down your HoloLens.</span></span> <span data-ttu-id="3423a-455">如果为 MSA 帐户或本地帐户的单个 Microsoft 帐户 (，) [选项可能不可用](hololens-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="3423a-455">The Sign out option might not be available, if the device is set up for a [single Microsoft Account (MSA) or local account](hololens-identity.md).</span></span>

6. <span data-ttu-id="3423a-456">通过触摸任何其他位置或用"开始"手势关闭"开始"菜单来消除菜单。</span><span class="sxs-lookup"><span data-stu-id="3423a-456">Dismiss the menu by touching anywhere else or closing the Start menu with the Start gesture.</span></span>

#### <a name="update-indicator"></a><span data-ttu-id="3423a-457">更新指示器</span><span class="sxs-lookup"><span data-stu-id="3423a-457">Update indicator</span></span>

<span data-ttu-id="3423a-458">更新可用时，省略号图标将打开，以指示重新启动将安装更新 菜单选项也会更改以反映更新状态。</span><span class="sxs-lookup"><span data-stu-id="3423a-458">When an update is available, the ellipsis icon will light up to indicate that a restart will install the update The menu options also change to reflect the presence of the update.</span></span><br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a><span data-ttu-id="3423a-459">登录屏幕上列出的多个用户</span><span class="sxs-lookup"><span data-stu-id="3423a-459">Multiple users listed on Sign in screen</span></span>

<span data-ttu-id="3423a-460">以前，登录屏幕只显示最近登录的用户，以及"其他用户"入口点。</span><span class="sxs-lookup"><span data-stu-id="3423a-460">Previously the Sign In screen showed only the most recently signed in user, as well as an 'Other user' entry point.</span></span> <span data-ttu-id="3423a-461">我们已收到客户反馈，表示如果多个用户已登录设备，这是不够的。</span><span class="sxs-lookup"><span data-stu-id="3423a-461">We have received customer feedback that this not sufficient if multiple users have signed into the device.</span></span> <span data-ttu-id="3423a-462">他们仍然需要重新键入用户名等。</span><span class="sxs-lookup"><span data-stu-id="3423a-462">They were still required to retype their username etc.</span></span>

<span data-ttu-id="3423a-463">在此 Windows 预览体验成员版本中\*\*\*\* 引入，当选择"PIN 条目"字段右边的"其他用户"时，"登录"屏幕将显示之前已登录到设备的多个用户。</span><span class="sxs-lookup"><span data-stu-id="3423a-463">Introduced in this Windows Insider build, when selecting **Other user** which is located to the right of the PIN entry field, the Sign in screen will display multiple users with have previously signed into the device.</span></span> <span data-ttu-id="3423a-464">这允许用户选择其用户配置文件，然后使用其 Windows Hello 凭据登录。</span><span class="sxs-lookup"><span data-stu-id="3423a-464">This allows users to select their user profile and then sign-in using their Windows Hello credentials.</span></span> <span data-ttu-id="3423a-465">通过"添加帐户"按钮，也可以从此"其他用户"页面向 **设备添加新** 用户。</span><span class="sxs-lookup"><span data-stu-id="3423a-465">A new user can also be added to the device from this Other users page via the **Add account** button.</span></span>

<span data-ttu-id="3423a-466">在"其他用户"菜单中时，"其他用户"按钮将显示最后一个登录到设备的用户。</span><span class="sxs-lookup"><span data-stu-id="3423a-466">When in the Other users menu, the Other users button will display the last user signed into the device.</span></span> <span data-ttu-id="3423a-467">Select this button to return to the Sign in screen for this user.</span><span class="sxs-lookup"><span data-stu-id="3423a-467">Select this button to return to the Sign in screen for this user.</span></span>

![登录屏幕默认](./images/multiusers1.jpg)

<br>

![其他用户的登录屏幕](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a><span data-ttu-id="3423a-470">USB-C 外部麦克风支持</span><span class="sxs-lookup"><span data-stu-id="3423a-470">USB-C External Microphone Support</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3423a-471">插入 USB **麦克风不会自动将其设置为输入设备**。</span><span class="sxs-lookup"><span data-stu-id="3423a-471">Plugging in **a USB mic will not automatically set it as the input device**.</span></span> <span data-ttu-id="3423a-472">在插入一组 USB-C 耳机时，用户将观察到耳机的音频将自动重定向到耳机，但 HoloLens 操作系统会将内部麦克风阵列的优先级设置为高于任何其他输入设备。</span><span class="sxs-lookup"><span data-stu-id="3423a-472">When plugging in a set of USB-C headphones users will observe that the headphone's audio will automatically be redirected to the headphones, but the HoloLens OS prioritizes the internal microphone array above any other input device.</span></span> **<span data-ttu-id="3423a-473">若要使用 USB-C 麦克风，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="3423a-473">In order to use a USB-C microphone follow the steps below.</span></span>**

<span data-ttu-id="3423a-474">用户可以使用"声音设置"面板选择 USB-C **连接** 的外部麦克风。</span><span class="sxs-lookup"><span data-stu-id="3423a-474">Users can select USB-C connected external microphones using the **Sound** settings panel.</span></span> <span data-ttu-id="3423a-475">USB-C 麦克风可用于呼叫、录制等。</span><span class="sxs-lookup"><span data-stu-id="3423a-475">USB-C microphones can be used for calling, recording, etc.</span></span>

<span data-ttu-id="3423a-476">打开"**设置"** 应用，然后选择"**系统**  >  **声音"。**</span><span class="sxs-lookup"><span data-stu-id="3423a-476">Open the **Settings** app and select **System** > **Sound**.</span></span>

![声音设置](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> <span data-ttu-id="3423a-478">若要将外部麦克风与 **远程协助**一同使用，用户需要单击"管理声音设备"超链接。</span><span class="sxs-lookup"><span data-stu-id="3423a-478">To use external microphones with **Remote Assist**, users will need to click the “Manage sound devices” hyperlink.</span></span>
>
> <span data-ttu-id="3423a-479">然后使用下拉列表将外部麦克风设置为"默认" **或** " **通信默认值"。**</span><span class="sxs-lookup"><span data-stu-id="3423a-479">Then use the drop-down to set the external microphone as either **Default** or **Communications Default.**</span></span> <span data-ttu-id="3423a-480">选择 **"** 默认"意味着将无处不在使用外部麦克风。</span><span class="sxs-lookup"><span data-stu-id="3423a-480">Choosing **Default** means that the external microphone will be used everywhere.</span></span>
>
> <span data-ttu-id="3423a-481">选择 **"** 通信默认值"意味着外部麦克风将用于远程协助和其他通信应用，但 HoloLens 麦克风阵列仍可用于其他任务。</span><span class="sxs-lookup"><span data-stu-id="3423a-481">Choosing **Communications Default** means that the external microphone will be used in Remote Assist and other communications apps, but the HoloLens mic array may still be used for other tasks.</span></span>

![管理声音设备](images/usbc-mic-2.png)

<br>

![设置麦克风默认值](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a><span data-ttu-id="3423a-484">麦克风Bluetooth如何？</span><span class="sxs-lookup"><span data-stu-id="3423a-484">What about Bluetooth microphone support?</span></span>

<span data-ttu-id="3423a-485">遗憾的是Bluetooth HoloLens 2 上当前仍不支持麦克风。</span><span class="sxs-lookup"><span data-stu-id="3423a-485">Unfortunately Bluetooth microphones are still not currently supported on HoloLens 2.</span></span>

#### <a name="troubleshooting-usb-c-microphones"></a><span data-ttu-id="3423a-486">USB-C 麦克风疑难解答</span><span class="sxs-lookup"><span data-stu-id="3423a-486">Troubleshooting USB-C microphones</span></span>

<span data-ttu-id="3423a-487">请注意，某些 USB-C 麦克风错误地将自己报告 *为麦克风和* 扬声器。</span><span class="sxs-lookup"><span data-stu-id="3423a-487">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="3423a-488">这是麦克风而不是 HoloLens 的问题。</span><span class="sxs-lookup"><span data-stu-id="3423a-488">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="3423a-489">将其中一个麦克风插入 HoloLens 时，可能会丢失声音。</span><span class="sxs-lookup"><span data-stu-id="3423a-489">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="3423a-490">幸运的是，有一个简单的解决方法。</span><span class="sxs-lookup"><span data-stu-id="3423a-490">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="3423a-491">在 **"**  ->  **设置系统**声音"中，将内置扬声器 (模拟功能音频驱动程序)  ->  \*\*\*\*\*\*设置为\*\*\*\*默认设备\*\*。</span><span class="sxs-lookup"><span data-stu-id="3423a-491">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="3423a-492">HoloLens 应记住此设置，即使麦克风稍后被删除并重新连接。</span><span class="sxs-lookup"><span data-stu-id="3423a-492">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C 麦克风疑难解答](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a><span data-ttu-id="3423a-494">展台的访问者自动登录</span><span class="sxs-lookup"><span data-stu-id="3423a-494">Visitor Auto logon for Kiosks</span></span>

<span data-ttu-id="3423a-495">此新功能允许自动登录访问者帐户以用于展台模式。</span><span class="sxs-lookup"><span data-stu-id="3423a-495">This new feature enables the auto logon on Visitor accounts to be used for Kiosk modes.</span></span>

<span data-ttu-id="3423a-496">对于非 AAD 配置，若要为访问者自动登录配置设备：</span><span class="sxs-lookup"><span data-stu-id="3423a-496">For a non-AAD configuration, to configure a device for visitor auto-logon:</span></span>

1. <span data-ttu-id="3423a-497">创建一个预配包，该包：</span><span class="sxs-lookup"><span data-stu-id="3423a-497">Create a provisioning package that:</span></span>
    1. <span data-ttu-id="3423a-498">配置 **运行时设置/AssignedAccess** 以允许访问者帐户。</span><span class="sxs-lookup"><span data-stu-id="3423a-498">Configures **Runtime settings/AssignedAccess** to allow Visitor accounts.</span></span>
    1. <span data-ttu-id="3423a-499">可以选择在 MDM 中注册设备 \*\* (运行时设置/工作区/ \*\* 注册) 以便以后可以管理设备。</span><span class="sxs-lookup"><span data-stu-id="3423a-499">Optionally enrolls the device in MDM **(Runtime settings/Workplace/Enrollments)** so that it can be managed later.</span></span>
    1. <span data-ttu-id="3423a-500">不要创建本地帐户</span><span class="sxs-lookup"><span data-stu-id="3423a-500">Do not create a local account</span></span>
1. <span data-ttu-id="3423a-501">[应用预配包](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="3423a-501">[Apply the provisioning package](hololens-provisioning.md).</span></span>

<span data-ttu-id="3423a-502">对于 AAD 配置，用户现在可以实现与现在类似的功能，而无需进行此更改。</span><span class="sxs-lookup"><span data-stu-id="3423a-502">For an AAD configuration, users can achieve something similar to this today without this change.</span></span> <span data-ttu-id="3423a-503">为展台模式配置的已加入 AAD 的设备可以通过从登录屏幕中点击一个按钮来登录访问者帐户。</span><span class="sxs-lookup"><span data-stu-id="3423a-503">AAD joined devices configured for kiosk mode can sign in a Visitor account with a single button tap from the sign in screen.</span></span> <span data-ttu-id="3423a-504">登录到访问者帐户后，设备不会提示再次登录，直到"访问者"从"开始"菜单显式注销或设备重新启动。</span><span class="sxs-lookup"><span data-stu-id="3423a-504">Once signed in to the visitor account, the device will not prompt for sign in again until the Visitor is explicitly signed out from the start menu or the device is restarted.</span></span>

<span data-ttu-id="3423a-505">访问者自动登录可以通过自定义 [OMA-URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) 策略进行管理：</span><span class="sxs-lookup"><span data-stu-id="3423a-505">Visitor Auto logon can be managed via [custom OMA-URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) policy:</span></span>

- <span data-ttu-id="3423a-506">URI 值：./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon</span><span class="sxs-lookup"><span data-stu-id="3423a-506">URI value: ./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon</span></span>

| <span data-ttu-id="3423a-507">策略</span><span class="sxs-lookup"><span data-stu-id="3423a-507">Policy</span></span>  | <span data-ttu-id="3423a-508">描述</span><span class="sxs-lookup"><span data-stu-id="3423a-508">Description</span></span>   | <span data-ttu-id="3423a-509">配置</span><span class="sxs-lookup"><span data-stu-id="3423a-509">Configurations</span></span>  |
|---|---|---|
| <span data-ttu-id="3423a-510">MixedReality/VisitorAutoLogon</span><span class="sxs-lookup"><span data-stu-id="3423a-510">MixedReality/VisitorAutoLogon</span></span>  | <span data-ttu-id="3423a-511">允许访问者自动登录展台</span><span class="sxs-lookup"><span data-stu-id="3423a-511">Allows for a Visitor to Auto logon to a Kiosk</span></span>   | <span data-ttu-id="3423a-512">1 (是) ，0 (否，默认。) </span><span class="sxs-lookup"><span data-stu-id="3423a-512">1 (Yes), 0 (No, default.)</span></span>  |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a><span data-ttu-id="3423a-513">在展台模式下使用新的设置和边缘应用</span><span class="sxs-lookup"><span data-stu-id="3423a-513">Use the new Settings and Edge apps in Kiosk modes</span></span>

<span data-ttu-id="3423a-514">在 [展台包含](hololens-kiosk.md)应用时，IT 管理员通常会将应用添加到展台，但使用应用用户模型 ID (AUMID) 。</span><span class="sxs-lookup"><span data-stu-id="3423a-514">When including apps in [Kiosks](hololens-kiosk.md), an IT Admin often adds the app to the Kiosk but using it's App User Model ID (AUMID).</span></span> <span data-ttu-id="3423a-515">由于"设置"应用和 Microsoft Edge 应用都被视为新应用，并且不同于使用这些应用的 AUMID 的较旧应用展台，因此将需要更新为使用新的 AUMID。</span><span class="sxs-lookup"><span data-stu-id="3423a-515">Because both the Settings app and Microsoft Edge app are considered new apps and different than the older apps Kiosks that use AUMIDs for those apps will need to be updated to use the new AUMID.</span></span>

<span data-ttu-id="3423a-516">在修改展台以包含新应用时，我们建议在新的 AUMID 中添加 ，同时保留旧应用。</span><span class="sxs-lookup"><span data-stu-id="3423a-516">When modifying a Kiosk to include the new apps, we recommend adding in the new AUMID as well as leaving the old one.</span></span> <span data-ttu-id="3423a-517">这将在用户更新操作系统时创建一个简单的转换，并且不需要接收新策略来继续如期使用展台。</span><span class="sxs-lookup"><span data-stu-id="3423a-517">This will create an easy transition when users update the OS and won't need to receive new policies to keep using the Kiosk as intended.</span></span>

| <span data-ttu-id="3423a-518">应用</span><span class="sxs-lookup"><span data-stu-id="3423a-518">App</span></span>                    | <span data-ttu-id="3423a-519">AUMID</span><span class="sxs-lookup"><span data-stu-id="3423a-519">AUMID</span></span>                                                  |
|------------------------|--------------------------------------------------------|
| <span data-ttu-id="3423a-520">旧设置应用</span><span class="sxs-lookup"><span data-stu-id="3423a-520">Old Settings App</span></span>       | <span data-ttu-id="3423a-521">HolographicSystemSettings_cw5n1h2txyewy！应用</span><span class="sxs-lookup"><span data-stu-id="3423a-521">HolographicSystemSettings_cw5n1h2txyewy!App</span></span>            |
| <span data-ttu-id="3423a-522">"新建设置"应用</span><span class="sxs-lookup"><span data-stu-id="3423a-522">New Settings App</span></span>       | <span data-ttu-id="3423a-523">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！应用</span><span class="sxs-lookup"><span data-stu-id="3423a-523">BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App</span></span> |
| <span data-ttu-id="3423a-524">旧 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="3423a-524">Old Microsoft Edge app</span></span> | <span data-ttu-id="3423a-525">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span><span class="sxs-lookup"><span data-stu-id="3423a-525">Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge</span></span>    |
| <span data-ttu-id="3423a-526">新 Microsoft Edge 应用</span><span class="sxs-lookup"><span data-stu-id="3423a-526">New Microsoft Edge app</span></span> | <span data-ttu-id="3423a-527">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE</span><span class="sxs-lookup"><span data-stu-id="3423a-527">Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE</span></span>    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a><span data-ttu-id="3423a-528">用于处理故障的展台模式行为更改</span><span class="sxs-lookup"><span data-stu-id="3423a-528">Kiosk mode behavior changes for handling of failures</span></span>

<span data-ttu-id="3423a-529">在较旧版本中，如果设备具有展台配置（即全局分配的访问权限和 AAD 组成员身份分配的访问权限的组合）。如果确定 AAD 组成员身份失败，用户将看到"开始"菜单中未[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)显示任何内容。</span><span class="sxs-lookup"><span data-stu-id="3423a-529">In older builds, if a device had a kiosk configuration, which is a combination of both global assigned access and AAD group member assigned access, if determining AAD group membership failed, the user would see “[nothing shown in start](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)” menu.</span></span>

<span data-ttu-id="3423a-530">从 Windows 预览体验成员版本开始，展台体验将回退到全局展台配置 (如果存在，) AAD 组展台模式期间发生故障的情况。</span><span class="sxs-lookup"><span data-stu-id="3423a-530">Starting in Windows Insider release, the kiosk experience will fallback to global kiosk configuration (if present) in case of failures during AAD group kiosk mode.</span></span>

### <a name="new-settingsuris-for-page-settings-visibility"></a><span data-ttu-id="3423a-531">页面设置可见性的新设置 URIs</span><span class="sxs-lookup"><span data-stu-id="3423a-531">New SettingsURIs for Page Settings Visibility</span></span>

<span data-ttu-id="3423a-532">在 [Windows 全息版版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中，我们添加了 [Settings/PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 策略，以限制在"设置"应用中看到的页面。</span><span class="sxs-lookup"><span data-stu-id="3423a-532">In [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) we added the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="3423a-533">PageVisibilityList 是一项策略，它允许 IT 管理员阻止查看或访问“系统设置”应用中的特定页面，或者对除指定页面之外的所有页面执行此操作。</span><span class="sxs-lookup"><span data-stu-id="3423a-533">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

<span data-ttu-id="3423a-534">如果你访问页面 [设置可见性](settings-uri-list.md)，你可以找到使用此 CSP 的说明和以前版本中提供的 URI 列表。</span><span class="sxs-lookup"><span data-stu-id="3423a-534">If you visit [Page Settings Visibility](settings-uri-list.md), you can find instructions to use this CSP and the list of URIs available in previous releases.</span></span>

<span data-ttu-id="3423a-535">在 Windows 预览体验成员版本，我们正在扩展可用设置 URI 的列表，IT 管理员可以管理该列表。</span><span class="sxs-lookup"><span data-stu-id="3423a-535">In Windows Insider builds we are expanding upon the list of list of available Settings URIs, which IT Admins can manage.</span></span> <span data-ttu-id="3423a-536">其中一些 URI 用于新"设置"应用中新可用的区域。</span><span class="sxs-lookup"><span data-stu-id="3423a-536">Some of these URIs are for newly available areas within the new Settings app.</span></span> <span data-ttu-id="3423a-537">如果使用的是"设置/PageVisibilityList"策略，请查看以下列表并根据需要调整允许或阻止的页面。</span><span class="sxs-lookup"><span data-stu-id="3423a-537">If you are using Settings/PageVisibilityList policy, review the following list and adjust your allowed or blocked pages as needed.</span></span>

> [!NOTE]
> **<span data-ttu-id="3423a-538">已弃用：ms-settings：network-proxy</span><span class="sxs-lookup"><span data-stu-id="3423a-538">Deprecated: ms-settings:network-proxy</span></span>**
>
> <span data-ttu-id="3423a-539">在这些较新的内部版本中，一个设置页已弃用。</span><span class="sxs-lookup"><span data-stu-id="3423a-539">One settings page is deprecated in these newer builds.</span></span> <span data-ttu-id="3423a-540">旧的 **"& Internet**  >  **代理**"页不再作为全局设置提供。</span><span class="sxs-lookup"><span data-stu-id="3423a-540">The old **Network & Internet** > **Proxy** page is no longer available as a global setting.</span></span> <span data-ttu-id="3423a-541">新的每连接代理设置位于"网络 **"&"Internet**Wi-Fi 属性"或"网络&  >  \*\*\*\*  >  \*\*\*\* **Internet**  >  **以太网**  >  **属性"下**。</span><span class="sxs-lookup"><span data-stu-id="3423a-541">The new per-connection proxy settings can be found under **Network & Internet** > **Wi-Fi** > **Properties** or **Network & Internet** > **Ethernet** > **Properties**.</span></span>

<br>

| <span data-ttu-id="3423a-542">设置页面</span><span class="sxs-lookup"><span data-stu-id="3423a-542">Settings page</span></span>                                        | <span data-ttu-id="3423a-543">URI</span><span class="sxs-lookup"><span data-stu-id="3423a-543">URI</span></span>                                              |
|------------------------------------------------------|--------------------------------------------------|
| <span data-ttu-id="3423a-544">应用>应用&功能</span><span class="sxs-lookup"><span data-stu-id="3423a-544">Apps > Apps & features</span></span>                               | `ms-settings:appsfeatures`                         |
| <span data-ttu-id="3423a-545">应用>应用&高级>功能</span><span class="sxs-lookup"><span data-stu-id="3423a-545">Apps > Apps & features > Advanced options</span></span>          | `ms-settings:appsfeatures-app`                     |
| <span data-ttu-id="3423a-546">应用>离线地图</span><span class="sxs-lookup"><span data-stu-id="3423a-546">Apps > Offline maps</span></span>                                  | `ms-settings:maps`                                 |
| <span data-ttu-id="3423a-547">应用>离线地图>下载地图</span><span class="sxs-lookup"><span data-stu-id="3423a-547">Apps > Offline maps > Download maps</span></span>                  | `ms-settings:maps-downloadmaps`                    |
| <span data-ttu-id="3423a-548">鼠标>设备</span><span class="sxs-lookup"><span data-stu-id="3423a-548">Devices > Mouse</span></span>                                      | `ms-settings:mouse`                                |
| <span data-ttu-id="3423a-549">USB >设备</span><span class="sxs-lookup"><span data-stu-id="3423a-549">Devices > USB</span></span>                                        | `ms-settings:usb`                                  |
| <span data-ttu-id="3423a-550">网络& Internet >飞行模式</span><span class="sxs-lookup"><span data-stu-id="3423a-550">Network & Internet > Airplane mode</span></span>                   | `ms-settings:network-airplanemode`                 |
| <span data-ttu-id="3423a-551">隐私>常规</span><span class="sxs-lookup"><span data-stu-id="3423a-551">Privacy > General</span></span>                                    | `ms-settings:privacy-general`                      |
| <span data-ttu-id="3423a-552">隐私>墨迹&键入个性化设置</span><span class="sxs-lookup"><span data-stu-id="3423a-552">Privacy > Ink & typing personalization</span></span>             | `ms-settings:privacy-speechtyping`                 |
| <span data-ttu-id="3423a-553">隐私>运动</span><span class="sxs-lookup"><span data-stu-id="3423a-553">Privacy > Motion</span></span>                                     | `ms-settings:privacy-motion`                       |
| <span data-ttu-id="3423a-554">隐私>屏幕截图边框</span><span class="sxs-lookup"><span data-stu-id="3423a-554">Privacy > Screenshot borders</span></span>                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| <span data-ttu-id="3423a-555">隐私>屏幕截图和应用</span><span class="sxs-lookup"><span data-stu-id="3423a-555">Privacy > Screenshots and apps</span></span>                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| <span data-ttu-id="3423a-556">系统>电池</span><span class="sxs-lookup"><span data-stu-id="3423a-556">System > Battery</span></span>                                     | `ms-settings:batterysaver`                         |
| <span data-ttu-id="3423a-557">系统>电池</span><span class="sxs-lookup"><span data-stu-id="3423a-557">System > Battery</span></span>                                     | `ms-settings:batterysaver-settings`                |
| <span data-ttu-id="3423a-558">系统>声音</span><span class="sxs-lookup"><span data-stu-id="3423a-558">System > Sound</span></span>                                       | `ms-settings:sound`                                |
| <span data-ttu-id="3423a-559">系统>声音>应用音量和设备首选项</span><span class="sxs-lookup"><span data-stu-id="3423a-559">System > Sound > App volume and device preferences</span></span> | `ms-settings:apps-volume`                          |
| <span data-ttu-id="3423a-560">系统>声音>管理声音设备</span><span class="sxs-lookup"><span data-stu-id="3423a-560">System > Sound > Manage sound   devices</span></span>              | `ms-settings:sound-devices`                        |
| <span data-ttu-id="3423a-561">系统>存储>配置存储感知</span><span class="sxs-lookup"><span data-stu-id="3423a-561">System > Storage > Configure Storage Sense</span></span>         | `ms-settings:storagepolicies`                      |
| <span data-ttu-id="3423a-562">Time & Language > Date & time</span><span class="sxs-lookup"><span data-stu-id="3423a-562">Time & Language > Date & time</span></span>                        | `ms-settings:dateandtime`                          |
| <span data-ttu-id="3423a-563">时间&语言>键盘</span><span class="sxs-lookup"><span data-stu-id="3423a-563">Time & Language > Keyboard</span></span>                           | `ms-settings:keyboard`                             |
| <span data-ttu-id="3423a-564">Time & Language > Language</span><span class="sxs-lookup"><span data-stu-id="3423a-564">Time & Language > Language</span></span>                           | `ms-settings:language`                             |
| <span data-ttu-id="3423a-565">Time & Language > Language</span><span class="sxs-lookup"><span data-stu-id="3423a-565">Time & Language > Language</span></span>                           | `ms-settings:regionlanguage-languageoptions`       |
| <span data-ttu-id="3423a-566">更新&安全>重置&恢复</span><span class="sxs-lookup"><span data-stu-id="3423a-566">Update & Security > Reset & recovery</span></span>               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a><span data-ttu-id="3423a-567">更新的 URI</span><span class="sxs-lookup"><span data-stu-id="3423a-567">Updated URIs</span></span>

<span data-ttu-id="3423a-568">以前，以下两个 URI 不会将用户直接进入指示的页面，但只会阻止主更新页面。</span><span class="sxs-lookup"><span data-stu-id="3423a-568">Previously the following two URIs would not take a user directly to the pages indicated but only blocked the main updates page.</span></span> <span data-ttu-id="3423a-569">以下项目已更新为直接访问其页面：</span><span class="sxs-lookup"><span data-stu-id="3423a-569">The following items have been updated to direct to their pages:</span></span>

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a><span data-ttu-id="3423a-570">通过"设置"应用配置回退诊断</span><span class="sxs-lookup"><span data-stu-id="3423a-570">Configuring Fallback Diagnostics via Settings app</span></span>

<span data-ttu-id="3423a-571">现在，在"设置"应用中，用户可以配置 [回退诊断的行为](hololens-diagnostic-logs.md)。</span><span class="sxs-lookup"><span data-stu-id="3423a-571">Now in Settings App, a user can configure the behavior of [Fallback Diagnostics](hololens-diagnostic-logs.md).</span></span> <span data-ttu-id="3423a-572">在"设置"应用中，\*\*\*\* 导航到"  ->  **隐私疑难解答"** 页以配置此设置。</span><span class="sxs-lookup"><span data-stu-id="3423a-572">In the Settings app navigate to **Privacy** -> **Troubleshooting** page to configure this setting.</span></span>

> [!NOTE]
> <span data-ttu-id="3423a-573">如果有为设备配置的 MDM 策略，用户将不能替代该行为。</span><span class="sxs-lookup"><span data-stu-id="3423a-573">If there is MDM policy configured for the device, user will not be able to override that behavior.</span></span>  

### <a name="share-things-with-nearby-devices"></a><span data-ttu-id="3423a-574">与附近设备共享内容</span><span class="sxs-lookup"><span data-stu-id="3423a-574">Share things with nearby devices</span></span>

<span data-ttu-id="3423a-575">与 Windows 10 设备（包括运行 HoloLens 预览体验成员版本 20279.1006+的其他 HoloLens 2 设备）附近共享内容。</span><span class="sxs-lookup"><span data-stu-id="3423a-575">Share things with near by Windows 10 devices, including both PCs and other HoloLens 2 devices running HoloLens Insider builds 20279.1006+.</span></span> <span data-ttu-id="3423a-576">你可以尝试在**设置系统**共享体验中试用，以将文件或  ->  \*\*\*\*  ->  \*\*\*\* URL 从 HoloLens 共享到电脑。</span><span class="sxs-lookup"><span data-stu-id="3423a-576">You can try it out in **Settings** -> **System** -> **Shared Experiences** to share files or URLs from a HoloLens to a PC.</span></span> <span data-ttu-id="3423a-577">有关更多详细信息，请阅读有关如何在 [Windows 10 中与附近设备共享内容的详细信息](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)。</span><span class="sxs-lookup"><span data-stu-id="3423a-577">For more details read more about how to [Share things with nearby devices in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).</span></span>

<span data-ttu-id="3423a-578">可通过 [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)管理此功能。</span><span class="sxs-lookup"><span data-stu-id="3423a-578">This feature can be managed via [Connectivity/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices).</span></span>

### <a name="new-os-update-troubleshooter"></a><span data-ttu-id="3423a-579">新的操作系统更新疑难解答程序</span><span class="sxs-lookup"><span data-stu-id="3423a-579">New OS Update troubleshooter</span></span>

<span data-ttu-id="3423a-580">除了"设置"应用中以前的疑难解答外，还新增了一个疑难解答程序，新增了适用于操作系统更新的"设置"应用。</span><span class="sxs-lookup"><span data-stu-id="3423a-580">In addition to the previous troubleshooters within the Settings app, a new troubleshooter has been added with the addition of the new Settings app for OS Updates.</span></span> <span data-ttu-id="3423a-581">导航到**设置**  ->  **更新 &amp; 安全疑难**  >  **解答**  >  **Windows 更新，** 然后选择开始 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3423a-581">Navigate to **Settings** -> **Update &amp; Security** > **Troubleshoot** > **Windows Update** and select **Start**.</span></span> <span data-ttu-id="3423a-582">这允许你在通过操作系统更新重现问题时收集跟踪，以更好地协助 IT 或支持进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="3423a-582">This allows you to collect traces while reproducing your issue with OS Updates to assist better in troubleshooting with your IT or support.</span></span>

### <a name="delivery-optimization-preview"></a><span data-ttu-id="3423a-583">传递优化预览</span><span class="sxs-lookup"><span data-stu-id="3423a-583">Delivery Optimization Preview</span></span>

<span data-ttu-id="3423a-584">通过此 HoloLens 预览体验成员更新，Windows Holographic for Business 支持传递优化设置的早期预览，以减少从多个 HoloLens 设备下载的带宽消耗。</span><span class="sxs-lookup"><span data-stu-id="3423a-584">With this HoloLens Insider update, Windows Holographic for Business enables an early preview for delivery optimization settings to reduce bandwidth consumption for downloads from multiple HoloLens devices.</span></span> <span data-ttu-id="3423a-585">有关此功能的完整说明以及推荐的网络配置，可在此处获取 [：Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)更新的传递优化。</span><span class="sxs-lookup"><span data-stu-id="3423a-585">A fuller description of this functionality along with the recommended network configuration is available here: [Delivery Optimization for Windows 10 updates](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization).</span></span>

<span data-ttu-id="3423a-586">以下设置作为管理图面的一部分启用， [并且可以从 Intune 进行配置](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)：</span><span class="sxs-lookup"><span data-stu-id="3423a-586">The following settings are enabled as part of the management surface and [can be configured from Intune](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings):</span></span>

- [<span data-ttu-id="3423a-587">DOCacheHost</span><span class="sxs-lookup"><span data-stu-id="3423a-587">DOCacheHost</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [<span data-ttu-id="3423a-588">DOCacheHostSource</span><span class="sxs-lookup"><span data-stu-id="3423a-588">DOCacheHostSource</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [<span data-ttu-id="3423a-589">DODelayCacheServerFallbackBackground</span><span class="sxs-lookup"><span data-stu-id="3423a-589">DODelayCacheServerFallbackBackground</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [<span data-ttu-id="3423a-590">DODelayCacheServerFallbackForeground</span><span class="sxs-lookup"><span data-stu-id="3423a-590">DODelayCacheServerFallbackForeground</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [<span data-ttu-id="3423a-591">DODownloadMode</span><span class="sxs-lookup"><span data-stu-id="3423a-591">DODownloadMode</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [<span data-ttu-id="3423a-592">DOMaxBackgroundDownloadBandwidth</span><span class="sxs-lookup"><span data-stu-id="3423a-592">DOMaxBackgroundDownloadBandwidth</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [<span data-ttu-id="3423a-593">DOMaxForegroundDownloadBandwidth</span><span class="sxs-lookup"><span data-stu-id="3423a-593">DOMaxForegroundDownloadBandwidth</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [<span data-ttu-id="3423a-594">DOPercentageMaxBackgroundBandwidth</span><span class="sxs-lookup"><span data-stu-id="3423a-594">DOPercentageMaxBackgroundBandwidth</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [<span data-ttu-id="3423a-595">DOPercentageMaxForegroundBandwidth</span><span class="sxs-lookup"><span data-stu-id="3423a-595">DOPercentageMaxForegroundBandwidth</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [<span data-ttu-id="3423a-596">DOSetHoursToLimitForegroundDownloadBandwidth</span><span class="sxs-lookup"><span data-stu-id="3423a-596">DOSetHoursToLimitForegroundDownloadBandwidth</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [<span data-ttu-id="3423a-597">DOSetHoursToLimitBackgroundDownloadBandwidth</span><span class="sxs-lookup"><span data-stu-id="3423a-597">DOSetHoursToLimitBackgroundDownloadBandwidth</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

<span data-ttu-id="3423a-598">关于此预览产品/服务，有一些注意事项：</span><span class="sxs-lookup"><span data-stu-id="3423a-598">A few caveats about this preview offering:</span></span>

- <span data-ttu-id="3423a-599">在此预览版中，HoloLens 支持仅限于操作系统更新。</span><span class="sxs-lookup"><span data-stu-id="3423a-599">HoloLens support is limited in this preview to OS updates only.</span></span>
- <span data-ttu-id="3423a-600">Windows Holographic for Business 仅支持 HTTP 下载模式和 [从 Microsoft 连接缓存终结点进行下载](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache);目前 HoloLens 设备不支持对等下载模式和组分配。</span><span class="sxs-lookup"><span data-stu-id="3423a-600">Windows Holographic for Business only supports HTTP download modes and downloads from a [Microsoft Connected Cache endpoint](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache); peer-to-peer download modes and group assignments are not supported for HoloLens devices at this time.</span></span>
- <span data-ttu-id="3423a-601">HoloLens 不支持 Windows Server Update Services 终结点的部署或传递优化。</span><span class="sxs-lookup"><span data-stu-id="3423a-601">HoloLens does not support deployment or delivery optimization for Windows Server Update Services endpoints.</span></span>
- <span data-ttu-id="3423a-602">疑难解答将要求在连接的缓存服务器上进行诊断，或通过设置更新和安全疑难解答\*\*\*\* Windows 更新收集 HoloLens  >  **&跟踪**  >   \*\*\*\*  >   \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3423a-602">Troubleshooting will require either diagnostics on the Connected Cache server or collecting a trace on HoloLens on HoloLens via **Settings** > **Update & Security** >  **Troubleshooting** >  **Windows Update**.</span></span>

### <a name="improvements-and-fixes-in-the-update"></a><span data-ttu-id="3423a-603">更新中的改进和修复：</span><span class="sxs-lookup"><span data-stu-id="3423a-603">Improvements and fixes in the update:</span></span>

- <span data-ttu-id="3423a-604">[脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics) 还将包含序列号和操作系统版本的其他设备信息。</span><span class="sxs-lookup"><span data-stu-id="3423a-604">[Offline diagnostics](hololens-diagnostic-logs.md#offline-diagnostics) will also include additional device information for serial number and OS version.</span></span>






## <a name="start-receiving-insider-builds"></a><span data-ttu-id="3423a-605">开始接收预览体验成员版本</span><span class="sxs-lookup"><span data-stu-id="3423a-605">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="3423a-606">如果你最近未更新，请重启设备以更新状态并获取最新版本。</span><span class="sxs-lookup"><span data-stu-id="3423a-606">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="3423a-607">"重新启动设备"语音命令运行良好。</span><span class="sxs-lookup"><span data-stu-id="3423a-607">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="3423a-608">还可以选择"设置/Windows 预览体验计划"中的"重启"按钮。</span><span class="sxs-lookup"><span data-stu-id="3423a-608">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="3423a-609">我们在后端上遇到一个 Bug，你可能遇到了此错误，这可让你重新上路。</span><span class="sxs-lookup"><span data-stu-id="3423a-609">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="3423a-610">在 HoloLens 2 设备上，**转到"设置**"& Windows 预览  >  \*\*\*\*  >  **体验计划**"并选择 **"开始使用"。**</span><span class="sxs-lookup"><span data-stu-id="3423a-610">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="3423a-611">链接你用于注册为 Windows 预览体验成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="3423a-611">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="3423a-612">Windows 预览体验成员现在正在迁移到频道。</span><span class="sxs-lookup"><span data-stu-id="3423a-612">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="3423a-613">快**圈**将成为**开发人员频道**，慢圈将成为\*\*\*\*\*\*Beta**渠道，并且**发布**预览圈将成为**发布预览频道\*\*。</span><span class="sxs-lookup"><span data-stu-id="3423a-613">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="3423a-614">该映射如下所示：</span><span class="sxs-lookup"><span data-stu-id="3423a-614">Here is what that mapping looks like:</span></span>

![Windows 预览体验成员频道说明](images/WindowsInsiderChannels.png)

<span data-ttu-id="3423a-616">有关详细信息，请参阅 Windows [博客上的 Windows 预览](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 体验成员频道介绍。</span><span class="sxs-lookup"><span data-stu-id="3423a-616">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="3423a-617">然后，选择 **"Windows 的活动开发"，** 选择是希望接收 **开发人员频道** 还是 **Beta 渠道** 版本，然后查看计划条款。</span><span class="sxs-lookup"><span data-stu-id="3423a-617">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="3423a-618">选择 **">立即重新启动** "完成操作。</span><span class="sxs-lookup"><span data-stu-id="3423a-618">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="3423a-619">重启设备后，转到设置>更新& **安全>检查** 更新，获取最新版本。</span><span class="sxs-lookup"><span data-stu-id="3423a-619">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="3423a-620">更新错误0x80070490问题</span><span class="sxs-lookup"><span data-stu-id="3423a-620">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="3423a-621">如果在 Dev 或 Beta 0x80070490更新时遇到更新错误，请尝试以下短期方法。</span><span class="sxs-lookup"><span data-stu-id="3423a-621">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="3423a-622">这包括移动预览体验成员频道、选取更新，然后将预览体验成员频道移回。</span><span class="sxs-lookup"><span data-stu-id="3423a-622">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="3423a-623">第一阶段 - 版本预览</span><span class="sxs-lookup"><span data-stu-id="3423a-623">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="3423a-624">设置，更新&安全，Windows 预览体验计划，选择 **发布预览频道**。</span><span class="sxs-lookup"><span data-stu-id="3423a-624">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="3423a-625">设置，更新&安全性，Windows 更新， **检查更新**。</span><span class="sxs-lookup"><span data-stu-id="3423a-625">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="3423a-626">更新后，继续执行第二阶段。</span><span class="sxs-lookup"><span data-stu-id="3423a-626">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="3423a-627">第二阶段 - 开发人员频道</span><span class="sxs-lookup"><span data-stu-id="3423a-627">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="3423a-628">设置，更新&安全，Windows 预览体验计划，选择 **开发人员频道**。</span><span class="sxs-lookup"><span data-stu-id="3423a-628">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="3423a-629">设置，更新&安全性，Windows 更新， **检查更新**。</span><span class="sxs-lookup"><span data-stu-id="3423a-629">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="3423a-630">FFU 下载和快速方向</span><span class="sxs-lookup"><span data-stu-id="3423a-630">FFU download and flash directions</span></span>
<span data-ttu-id="3423a-631">若要使用已签名 ffu 进行测试，首先必须先对设备进行飞行解锁，然后才能闪烁已进行测试的已签名 ffu。</span><span class="sxs-lookup"><span data-stu-id="3423a-631">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="3423a-632">在电脑上：</span><span class="sxs-lookup"><span data-stu-id="3423a-632">On PC:</span></span>

    1. <span data-ttu-id="3423a-633">从 下载 ffu 到你的电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="3423a-633">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="3423a-634">从 Microsoft store (ARC) 高级恢复配套设备 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) ：。</span><span class="sxs-lookup"><span data-stu-id="3423a-634">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="3423a-635">On HoloLens - Flight Unlock： Open **Settings**  >  **Update & Security**Windows Insider  >  **Program** then sign up， reboot device.</span><span class="sxs-lookup"><span data-stu-id="3423a-635">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="3423a-636">Flash FFU - 现在，可以使用 ARC 对已签名的 FFU 进行飞行。</span><span class="sxs-lookup"><span data-stu-id="3423a-636">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="3423a-637">提供反馈并报告问题</span><span class="sxs-lookup"><span data-stu-id="3423a-637">Provide feedback and report issues</span></span>

<span data-ttu-id="3423a-638">请在[](hololens-feedback.md)HoloLens 上使用反馈中心应用提供反馈并报告问题。</span><span class="sxs-lookup"><span data-stu-id="3423a-638">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="3423a-639">使用反馈中心可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。</span><span class="sxs-lookup"><span data-stu-id="3423a-639">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="3423a-640">应以相同方式报告有关 HoloLens 中文和日语版本的问题。</span><span class="sxs-lookup"><span data-stu-id="3423a-640">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="3423a-641">请务必接受询问是否希望反馈中心访问"文档"文件夹的提示， (系统提示时选择"是) 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="3423a-641">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="3423a-642">开发人员注意事项</span><span class="sxs-lookup"><span data-stu-id="3423a-642">Note for developers</span></span>

<span data-ttu-id="3423a-643">欢迎并鼓励你尝试使用 HoloLens 的预览体验成员版本开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="3423a-643">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="3423a-644">请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 以开始。</span><span class="sxs-lookup"><span data-stu-id="3423a-644">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="3423a-645">这些相同的说明与 HoloLens 的预览体验成员版本一致。</span><span class="sxs-lookup"><span data-stu-id="3423a-645">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="3423a-646">可以使用与 HoloLens Visual Studio相同的 Unity 版本和版本。</span><span class="sxs-lookup"><span data-stu-id="3423a-646">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="3423a-647">停止接收预览体验成员版本</span><span class="sxs-lookup"><span data-stu-id="3423a-647">Stop receiving Insider builds</span></span>

<span data-ttu-id="3423a-648">如果你不再希望接收 Windows 全息版的预览体验成员版本，你可以选择在 HoloLens 运行生产内部版本时退出，或者可以使用高级恢复[](hololens-recovery.md)助手将设备恢复为非预览体验成员版本的 Windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="3423a-648">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="3423a-649">存在一个已知问题，即手动重新安装全新预览版后从 Insider Preview 版本取消注册的用户将遇到蓝屏。</span><span class="sxs-lookup"><span data-stu-id="3423a-649">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="3423a-650">之后，他们必须手动恢复其设备。</span><span class="sxs-lookup"><span data-stu-id="3423a-650">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="3423a-651">有关是否将受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。</span><span class="sxs-lookup"><span data-stu-id="3423a-651">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="3423a-652">若要验证 HoloLens 是否正在运行生产内部版本：</span><span class="sxs-lookup"><span data-stu-id="3423a-652">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="3423a-653">转到" **系统>设置>"关于**"，并查找内部版本编号。</span><span class="sxs-lookup"><span data-stu-id="3423a-653">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="3423a-654">[请参阅生产内部版本号发行说明](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="3423a-654">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="3423a-655">若要选择退出预览体验成员版本：</span><span class="sxs-lookup"><span data-stu-id="3423a-655">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="3423a-656">在运行生产内部运行的 HoloLens 上，转到 Windows 预览体验计划>更新&安全> **设置"，然后选择**停止 **预览体验成员版本**。</span><span class="sxs-lookup"><span data-stu-id="3423a-656">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="3423a-657">按照说明选择退出设备。</span><span class="sxs-lookup"><span data-stu-id="3423a-657">Follow the instructions to opt out your device.</span></span>
