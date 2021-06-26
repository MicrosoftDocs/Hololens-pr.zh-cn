---
title: HoloLens 设备故障排除
description: 随时了解 HoloLens 设备问题的最常见解决方案和故障排除技术。
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 问题， bug， 故障排除， 修复， 帮助， 支持， HoloLens， 模拟器
ms.openlocfilehash: b69dddf04ac31b69f0b2f8759d095806189f33ab
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924615"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="6ec51-104">设备故障排除</span><span class="sxs-lookup"><span data-stu-id="6ec51-104">Device Troubleshooting</span></span>

<span data-ttu-id="6ec51-105">本文介绍如何解决几个常见的 HoloLens 问题。</span><span class="sxs-lookup"><span data-stu-id="6ec51-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="6ec51-106">在开始任何故障排除过程之前，请确保设备按 **电池容量的 20% 到 40%** 收费（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="6ec51-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="6ec51-107">位于 [电源](hololens2-setup.md#lights-that-indicate-the-battery-level) 按钮下的电池指示灯是验证电池容量的一种快速方法，无需登录到设备。</span><span class="sxs-lookup"><span data-stu-id="6ec51-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="6ec51-108">**已知问题**</span><span class="sxs-lookup"><span data-stu-id="6ec51-108">**Known Issues**</span></span>
- [<span data-ttu-id="6ec51-109">Remote Assist视频在 20 分钟后冻结</span><span class="sxs-lookup"><span data-stu-id="6ec51-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="6ec51-110">自动登录要求登录</span><span class="sxs-lookup"><span data-stu-id="6ec51-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="6ec51-111">Microsoft Edge启动失败</span><span class="sxs-lookup"><span data-stu-id="6ec51-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="6ec51-112">键盘不切换到特殊字符</span><span class="sxs-lookup"><span data-stu-id="6ec51-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="6ec51-113">下载锁定的文件不会显示错误</span><span class="sxs-lookup"><span data-stu-id="6ec51-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="6ec51-114">设备门户文件上传/下载时间已过</span><span class="sxs-lookup"><span data-stu-id="6ec51-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="6ec51-115">从预览体验成员预览版取消注册后，在设备上以预览体验成员版本刷出蓝屏</span><span class="sxs-lookup"><span data-stu-id="6ec51-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="6ec51-116">OneDrive 不会自动上传图片</span><span class="sxs-lookup"><span data-stu-id="6ec51-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="6ec51-117">**常规**</span><span class="sxs-lookup"><span data-stu-id="6ec51-117">**General**</span></span>
- [<span data-ttu-id="6ec51-118">HoloLens 无响应或无法启动</span><span class="sxs-lookup"><span data-stu-id="6ec51-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="6ec51-119">"磁盘空间不足"错误</span><span class="sxs-lookup"><span data-stu-id="6ec51-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="6ec51-120">校准失败</span><span class="sxs-lookup"><span data-stu-id="6ec51-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="6ec51-121">无法登录，因为之前为其他人设置了 HoloLens</span><span class="sxs-lookup"><span data-stu-id="6ec51-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="6ec51-122">Unity 不工作</span><span class="sxs-lookup"><span data-stu-id="6ec51-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="6ec51-123">Windows 设备门户无法正常工作</span><span class="sxs-lookup"><span data-stu-id="6ec51-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="6ec51-124">HoloLens 仿真器不工作</span><span class="sxs-lookup"><span data-stu-id="6ec51-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="6ec51-125">**输入**</span><span class="sxs-lookup"><span data-stu-id="6ec51-125">**Input**</span></span>
- [<span data-ttu-id="6ec51-126">语音命令无法工作</span><span class="sxs-lookup"><span data-stu-id="6ec51-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="6ec51-127">手动输入不工作</span><span class="sxs-lookup"><span data-stu-id="6ec51-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="6ec51-128">**连接**</span><span class="sxs-lookup"><span data-stu-id="6ec51-128">**Connectivity**</span></span>
- [<span data-ttu-id="6ec51-129">无法连接到 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="6ec51-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="6ec51-130">**外部设备**</span><span class="sxs-lookup"><span data-stu-id="6ec51-130">**External Devices**</span></span> 
- [<span data-ttu-id="6ec51-131">蓝牙设备未配对</span><span class="sxs-lookup"><span data-stu-id="6ec51-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="6ec51-132">USB-C 麦克风不工作</span><span class="sxs-lookup"><span data-stu-id="6ec51-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="6ec51-133">在"设置"中列为可用的设备不起作用</span><span class="sxs-lookup"><span data-stu-id="6ec51-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="6ec51-134">Remote Assist视频在 20 分钟后冻结</span><span class="sxs-lookup"><span data-stu-id="6ec51-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="6ec51-135">由于此已知问题的严重性，我们当前暂停了 Windows Holographic 版本 21H1 的可用性。</span><span class="sxs-lookup"><span data-stu-id="6ec51-135">Due to this Known Issue's severity we have currently paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="6ec51-136">如果仍希望将设备更新到 21H1，请参阅页面顶部的发行说明 [中的说明。](hololens-release-notes.md)</span><span class="sxs-lookup"><span data-stu-id="6ec51-136">If you would like to still update your devices to 21H1, please refer to [the instructions in our release notes at the top of the page.](hololens-release-notes.md)</span></span>

<span data-ttu-id="6ec51-137">在最新版本的 Windows Holographic 版本 [21H1](hololens-release-notes.md#windows-holographic-version-21h1)中，Remote Assist用户在通话期间遇到视频冻结。</span><span class="sxs-lookup"><span data-stu-id="6ec51-137">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="6ec51-138">这是一个 **已知问题**。</span><span class="sxs-lookup"><span data-stu-id="6ec51-138">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="6ec51-139">解决方法</span><span class="sxs-lookup"><span data-stu-id="6ec51-139">Workarounds</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="6ec51-140">在调用之间重启</span><span class="sxs-lookup"><span data-stu-id="6ec51-140">Restart in between calls</span></span>

<span data-ttu-id="6ec51-141">如果通话时长超过 20 分钟，并且遇到此问题，请尝试重启设备。</span><span class="sxs-lookup"><span data-stu-id="6ec51-141">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="6ec51-142">在两次Remote Assist重启设备会刷新设备，并恢复为良好状态。</span><span class="sxs-lookup"><span data-stu-id="6ec51-142">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="6ec51-143">若要在 [Windows Holographic（版本 21H1）](hololens-release-notes.md#windows-holographic-version-21h1)上快速重启设备，请打开"开始"菜单，选择用户图标，然后选择"重启 **"。**</span><span class="sxs-lookup"><span data-stu-id="6ec51-143">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

#### <a name="revert-to-an-older-build"></a><span data-ttu-id="6ec51-144">还原到较旧的生成</span><span class="sxs-lookup"><span data-stu-id="6ec51-144">Revert to an older build</span></span>

<span data-ttu-id="6ec51-145">一些客户发现，还原到较早的 OS 版本时，他们不再遇到此问题。</span><span class="sxs-lookup"><span data-stu-id="6ec51-145">Some customers have found that when reverting to an earlier OS version they no longer experience this issue.</span></span> <span data-ttu-id="6ec51-146">如果发现设备遇到此问题，请尝试以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6ec51-146">If you have found that your devices are experiencing this issue, try these steps:</span></span>


<span data-ttu-id="6ec51-147">解决方法：</span><span class="sxs-lookup"><span data-stu-id="6ec51-147">Workarounds:</span></span>

- <span data-ttu-id="6ec51-148">如果你的业务可行，则使用者 Microsoft 帐户支持自动上传相机。</span><span class="sxs-lookup"><span data-stu-id="6ec51-148">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="6ec51-149">除了工作或学校帐户Microsoft 帐户 OneDrive 应用支持双重登录帐户 (还可以登录到) 。</span><span class="sxs-lookup"><span data-stu-id="6ec51-149">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="6ec51-150">在 OneDrive Microsoft 帐户配置文件中，可以启用自动后台相机滚动上传。</span><span class="sxs-lookup"><span data-stu-id="6ec51-150">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="6ec51-151">如果无法安全地使用使用者Microsoft 帐户自动上传照片，可以从 OneDrive 应用手动将照片上传到工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="6ec51-151">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="6ec51-152">为此，请确保已登录到 OneDrive 应用中的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="6ec51-152">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="6ec51-153">选择按钮 **+** ，然后选择"上传 **"。**</span><span class="sxs-lookup"><span data-stu-id="6ec51-153">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="6ec51-154">通过导航到"照片"和"相机滚动> **上传的照片或视频**。</span><span class="sxs-lookup"><span data-stu-id="6ec51-154">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="6ec51-155">选择要上传的一个或多个照片或视频，然后选择"打开 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="6ec51-155">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>


1. [<span data-ttu-id="6ec51-156">下载适用于 Windows Holographic 版本 20H2 - 2021 年 5 月更新的版本</span><span class="sxs-lookup"><span data-stu-id="6ec51-156">Download the build for Windows Holographic, version 20H2 – May 2021 Update</span></span>](https://aka.ms/hololens2download/10.0.19041.1146)
1. <span data-ttu-id="6ec51-157">按照 [说明返回到以前的 OS 版本](hololens-update-hololens.md#go-back-to-a-previous-version)</span><span class="sxs-lookup"><span data-stu-id="6ec51-157">Follow the [instructions return to a previous OS version](hololens-update-hololens.md#go-back-to-a-previous-version)</span></span>
1. <span data-ttu-id="6ec51-158">手动 [暂停设备上 OS 更新，](hololens-updates.md#pause-updates-via-device) 或者对于许多设备，通过 [MDM 使用延迟](hololens-updates.md#configure-an-update-deferral-policy)。</span><span class="sxs-lookup"><span data-stu-id="6ec51-158">Either [pause OS updates on the device manually](hololens-updates.md#pause-updates-via-device) or for many devices use [deferral through MDM](hololens-updates.md#configure-an-update-deferral-policy).</span></span>

[<span data-ttu-id="6ec51-159">返回列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-159">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="6ec51-160">自动登录要求登录</span><span class="sxs-lookup"><span data-stu-id="6ec51-160">Auto-login asks for log-in</span></span>

<span data-ttu-id="6ec51-161">可以将HoloLens 2配置为通过"设置帐户登录选项"->在"必需"下将值  ->    ->  设置为"从不"自动 **登录**。 </span><span class="sxs-lookup"><span data-stu-id="6ec51-161">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="6ec51-162">更新具有较大更新（如功能更新）的设备时，某些用户可能需要再次登录到设备。</span><span class="sxs-lookup"><span data-stu-id="6ec51-162">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="6ec51-163">这是一个 **已知问题**。</span><span class="sxs-lookup"><span data-stu-id="6ec51-163">This is a **known issue**.</span></span>

<span data-ttu-id="6ec51-164">发生这种情况的示例：</span><span class="sxs-lookup"><span data-stu-id="6ec51-164">Example of when this could occur:</span></span>

- <span data-ttu-id="6ec51-165">将设备从 Windows Holographic 版本 2004 (内部版本 19041.xxxx) 更新到 Windows Holographic 版本 21H1 (内部版本 20346.xxxx) </span><span class="sxs-lookup"><span data-stu-id="6ec51-165">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="6ec51-166">更新设备以在同一主要版本（例如 Windows Holographic 版本 2004 到 Windows Holographic 版本 20H2）上进行大型更新</span><span class="sxs-lookup"><span data-stu-id="6ec51-166">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="6ec51-167">将设备从工厂映像更新到最新映像</span><span class="sxs-lookup"><span data-stu-id="6ec51-167">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="6ec51-168">这不应发生在：</span><span class="sxs-lookup"><span data-stu-id="6ec51-168">This should not occur during:</span></span>

- <span data-ttu-id="6ec51-169">进行每月服务更新的设备</span><span class="sxs-lookup"><span data-stu-id="6ec51-169">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="6ec51-170">解决方法：</span><span class="sxs-lookup"><span data-stu-id="6ec51-170">Work around methods:</span></span>

- <span data-ttu-id="6ec51-171">登录方法，例如 PIN、密码、Iris、Web 身份验证或 FIDO2 密钥。</span><span class="sxs-lookup"><span data-stu-id="6ec51-171">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="6ec51-172">如果无法记住设备 PIN，并且其他身份验证方法不可用，则用户可以使用手动 [重新转换模式](hololens-recovery.md#manual-procedure)。</span><span class="sxs-lookup"><span data-stu-id="6ec51-172">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="6ec51-173">返回列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-173">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="6ec51-174">Microsoft Edge启动失败</span><span class="sxs-lookup"><span data-stu-id="6ec51-174">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="6ec51-175">此问题最初是使用产品/Microsoft Edge创建的。</span><span class="sxs-lookup"><span data-stu-id="6ec51-175">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="6ec51-176">此问题可以在新的 中[Microsoft Edge。](hololens-new-edge.md)</span><span class="sxs-lookup"><span data-stu-id="6ec51-176">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="6ec51-177">如果不是，请提交反馈。</span><span class="sxs-lookup"><span data-stu-id="6ec51-177">If it is not, please file feedback.</span></span>

<span data-ttu-id="6ec51-178">一些客户报告了无法启动Microsoft Edge的问题。</span><span class="sxs-lookup"><span data-stu-id="6ec51-178">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="6ec51-179">对于这些客户，此问题通过重新启动而仍然存在，不会通过 Windows 或应用程序更新解决。</span><span class="sxs-lookup"><span data-stu-id="6ec51-179">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="6ec51-180">如果遇到此问题，并且已确认 [Windows](hololens-updates.md#manually-check-for-updates)是最新的，请从 [反馈中心](hololens-feedback.md) 应用提交以下类别和子类别的 bug：安装和更新 > 下载、安装和配置 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="6ec51-180">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="6ec51-181">目前没有已知的解决方法，因为我们目前无法找出问题的根本原因。</span><span class="sxs-lookup"><span data-stu-id="6ec51-181">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="6ec51-182">通过 反馈中心 bug 将有助于调查！</span><span class="sxs-lookup"><span data-stu-id="6ec51-182">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="6ec51-183">这是一个 **已知问题**。</span><span class="sxs-lookup"><span data-stu-id="6ec51-183">This is a **known issue**.</span></span>

[<span data-ttu-id="6ec51-184">返回列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-184">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="6ec51-185">键盘不切换到特殊字符</span><span class="sxs-lookup"><span data-stu-id="6ec51-185">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="6ec51-186">OOBE 期间存在一个问题，即用户选择工作或学校帐户并输入其密码后，尝试通过点击 &123 按钮切换到键盘上的特殊字符不会更改为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="6ec51-186">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="6ec51-187">这是一个 **已知问题**。</span><span class="sxs-lookup"><span data-stu-id="6ec51-187">This is a **known issue**.</span></span>

<span data-ttu-id="6ec51-188">周全方案：</span><span class="sxs-lookup"><span data-stu-id="6ec51-188">Work-arounds:</span></span>
-   <span data-ttu-id="6ec51-189">关闭键盘，然后通过点击文本字段重新打开它。</span><span class="sxs-lookup"><span data-stu-id="6ec51-189">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="6ec51-190">错误地输入密码。</span><span class="sxs-lookup"><span data-stu-id="6ec51-190">Incorrectly enter your password.</span></span> <span data-ttu-id="6ec51-191">下次重新启动键盘时，它将如预期工作。</span><span class="sxs-lookup"><span data-stu-id="6ec51-191">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="6ec51-192">Web 身份验证，关闭键盘并选择 **"从另一台设备登录"。**</span><span class="sxs-lookup"><span data-stu-id="6ec51-192">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="6ec51-193">如果仅输入数字，用户可以按住某些键打开展开的菜单。</span><span class="sxs-lookup"><span data-stu-id="6ec51-193">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="6ec51-194">使用 USB 键盘。</span><span class="sxs-lookup"><span data-stu-id="6ec51-194">Using a USB keyboard.</span></span>

<span data-ttu-id="6ec51-195">这不会影响：</span><span class="sxs-lookup"><span data-stu-id="6ec51-195">This does not affect:</span></span>
- <span data-ttu-id="6ec51-196">选择使用个人帐户的用户。</span><span class="sxs-lookup"><span data-stu-id="6ec51-196">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="6ec51-197">返回列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-197">Back to list</span></span>](#list)


## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="6ec51-198">下载锁定的文件不会出错</span><span class="sxs-lookup"><span data-stu-id="6ec51-198">Downloading locked files doesn't error</span></span>
> <span data-ttu-id="6ec51-199">!注意 这是在 **内部版本** 20348.1403 Windows 预览体验成员修复的已知问题。</span><span class="sxs-lookup"><span data-stu-id="6ec51-199">!NOTE This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>


<span data-ttu-id="6ec51-200">在 Windows Holographic 的早期版本中，尝试下载锁定文件时，结果将是 HTTP 错误页。</span><span class="sxs-lookup"><span data-stu-id="6ec51-200">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="6ec51-201">在 Windows Holographic 版本 21H1 更新中，尝试下载锁定的文件会导致未发生任何可见的情况-文件不会下载，并且没有错误。</span><span class="sxs-lookup"><span data-stu-id="6ec51-201">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span> 

[<span data-ttu-id="6ec51-202">返回列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-202">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="6ec51-203">设备门户文件上传/下载时间已过</span><span class="sxs-lookup"><span data-stu-id="6ec51-203">Device Portal file upload/download times out</span></span>
> <span data-ttu-id="6ec51-204">!注意 这是在 **内部版本** 20348.1403 Windows 预览体验成员修复的已知问题。</span><span class="sxs-lookup"><span data-stu-id="6ec51-204">!NOTE This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="6ec51-205">如果以前已禁用 SSL 连接作为解决方法的一部分，强烈建议重新启用它。</span><span class="sxs-lookup"><span data-stu-id="6ec51-205">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="6ec51-206">一些客户发现，在尝试上传或下载文件时，操作可能显示为挂起，然后会退出或永不完成。</span><span class="sxs-lookup"><span data-stu-id="6ec51-206">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="6ec51-207">这独立于"[文件](#downloading-locked-files-doesnt-error) 锁定"已知问题 - 这会影响 Windows Holographic 版本 2004、20H2 和 21H1 市场内版本。</span><span class="sxs-lookup"><span data-stu-id="6ec51-207">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="6ec51-208">此问题的根本原因是，设备门户处理某些请求时出现 bug，并且使用 https 时最一致，这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="6ec51-208">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="6ec51-209">解决方法</span><span class="sxs-lookup"><span data-stu-id="6ec51-209">Workaround</span></span>

<span data-ttu-id="6ec51-210">此解决方法同样适用于 Wi-Fi UsbNcm，即禁用"SSL 连接"下的"必需"选项。</span><span class="sxs-lookup"><span data-stu-id="6ec51-210">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="6ec51-211">为此，请导航到 **设备门户"系统**"，然后选择" **首选项"** 页。</span><span class="sxs-lookup"><span data-stu-id="6ec51-211">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="6ec51-212">在"**设备安全性"** 部分中，找到 **"SSL 连接"，** 取消选中以禁用"**必需"。**</span><span class="sxs-lookup"><span data-stu-id="6ec51-212">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="6ec51-213">然后，用户应转到 http://，https:// (IP 地址) 文件上传和下载等功能将正常工作。</span><span class="sxs-lookup"><span data-stu-id="6ec51-213">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="6ec51-214">返回列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-214">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="6ec51-215">从预览体验成员预览版取消注册后，在设备上以预览体验成员版本刷出蓝屏</span><span class="sxs-lookup"><span data-stu-id="6ec51-215">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="6ec51-216">此问题会影响使用 Insider 预览版的用户，使用新的预览体验内部版本重新HoloLens 2预览体验版，然后从预览体验计划取消注册。</span><span class="sxs-lookup"><span data-stu-id="6ec51-216">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="6ec51-217">这是一个 **已知问题**。</span><span class="sxs-lookup"><span data-stu-id="6ec51-217">This is a **known issue**.</span></span>

<span data-ttu-id="6ec51-218">这不会影响：</span><span class="sxs-lookup"><span data-stu-id="6ec51-218">This does not affect:</span></span>
- <span data-ttu-id="6ec51-219">未在 Windows 预览体验成员</span><span class="sxs-lookup"><span data-stu-id="6ec51-219">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="6ec51-220">业内 人士：</span><span class="sxs-lookup"><span data-stu-id="6ec51-220">Insiders:</span></span>
    - <span data-ttu-id="6ec51-221">如果设备自预览体验内部版本为版本 18362.x 以来已注册</span><span class="sxs-lookup"><span data-stu-id="6ec51-221">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="6ec51-222">如果他们刷过预览体验成员签名的 19041.x 内部版本，并一直注册到 Insider 计划</span><span class="sxs-lookup"><span data-stu-id="6ec51-222">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="6ec51-223">工作之一：</span><span class="sxs-lookup"><span data-stu-id="6ec51-223">Work-around:</span></span> 
- <span data-ttu-id="6ec51-224">避免此问题</span><span class="sxs-lookup"><span data-stu-id="6ec51-224">Avoid the issue</span></span> 
    - <span data-ttu-id="6ec51-225">刷用非预览体验内部版本。</span><span class="sxs-lookup"><span data-stu-id="6ec51-225">Flash a non-insider build.</span></span> <span data-ttu-id="6ec51-226">每月定期更新之一。</span><span class="sxs-lookup"><span data-stu-id="6ec51-226">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="6ec51-227">随时了解预览体验成员</span><span class="sxs-lookup"><span data-stu-id="6ec51-227">Stay on Insider Preview</span></span>
- <span data-ttu-id="6ec51-228">重新运行设备</span><span class="sxs-lookup"><span data-stu-id="6ec51-228">Reflash the device</span></span>

    1. <span data-ttu-id="6ec51-229">在 [HoloLens 2](hololens-recovery.md) 完全关闭电源，手动将设备置于闪烁模式。</span><span class="sxs-lookup"><span data-stu-id="6ec51-229">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="6ec51-230">然后，在按住"音量"的同时，点击"电源"按钮。</span><span class="sxs-lookup"><span data-stu-id="6ec51-230">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="6ec51-231">连接到电脑并打开"高级恢复助手"。</span><span class="sxs-lookup"><span data-stu-id="6ec51-231">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="6ec51-232">将HoloLens 2刷新为默认生成。</span><span class="sxs-lookup"><span data-stu-id="6ec51-232">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="6ec51-233">返回列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-233">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="6ec51-234">OneDrive 不会自动上传图片</span><span class="sxs-lookup"><span data-stu-id="6ec51-234">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="6ec51-235">适用于 HoloLens 的 OneDrive 应用不支持为工作或学校帐户自动上传相机。</span><span class="sxs-lookup"><span data-stu-id="6ec51-235">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="6ec51-236">这是一个 **已知问题**。</span><span class="sxs-lookup"><span data-stu-id="6ec51-236">This is a **known issue**.</span></span>

<span data-ttu-id="6ec51-237">解决方法：</span><span class="sxs-lookup"><span data-stu-id="6ec51-237">Workarounds:</span></span>

- <span data-ttu-id="6ec51-238">如果你的业务可行，则使用者 Microsoft 帐户支持自动上传相机。</span><span class="sxs-lookup"><span data-stu-id="6ec51-238">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="6ec51-239">除了工作或学校帐户Microsoft 帐户 OneDrive 应用支持双重登录帐户 (还可以登录到) 。</span><span class="sxs-lookup"><span data-stu-id="6ec51-239">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="6ec51-240">在 OneDrive Microsoft 帐户配置文件中，可以启用自动后台相机滚动上传。</span><span class="sxs-lookup"><span data-stu-id="6ec51-240">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="6ec51-241">如果无法安全地使用使用者Microsoft 帐户自动上传照片，可以从 OneDrive 应用手动将照片上传到工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="6ec51-241">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="6ec51-242">为此，请确保已登录到 OneDrive 应用中的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="6ec51-242">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="6ec51-243">选择按钮 **+** ，然后选择"上传 **"。**</span><span class="sxs-lookup"><span data-stu-id="6ec51-243">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="6ec51-244">通过导航到"照片"和"相机滚动> **上传的照片或视频**。</span><span class="sxs-lookup"><span data-stu-id="6ec51-244">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="6ec51-245">选择要上传的一个或多个照片或视频，然后选择"打开 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="6ec51-245">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="6ec51-246">返回列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-246">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="6ec51-247">HoloLens 无响应或无法启动</span><span class="sxs-lookup"><span data-stu-id="6ec51-247">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="6ec51-248">如果 HoloLens 无法启动：</span><span class="sxs-lookup"><span data-stu-id="6ec51-248">If your HoloLens won't start:</span></span>

- <span data-ttu-id="6ec51-249">如果电源按钮旁边的 LED 不亮起，或只有一个 LED 短暂闪烁，可能需要为 [HoloLens 收费。](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="6ec51-249">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="6ec51-250">如果 LED 在按下电源按钮时亮起，但在显示器上看不到任何内容，请对设备 进行 [硬重置](hololens-recovery.md#hard-reset-procedure)。</span><span class="sxs-lookup"><span data-stu-id="6ec51-250">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="6ec51-251">如果 HoloLens 冻结或无响应：</span><span class="sxs-lookup"><span data-stu-id="6ec51-251">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="6ec51-252">按电源按钮关闭 HoloLens，直到所有五个 LED 都自行关闭，如果 LED 无响应，则关闭 15 秒。</span><span class="sxs-lookup"><span data-stu-id="6ec51-252">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="6ec51-253">若要启动 HoloLens，请再次按电源按钮。</span><span class="sxs-lookup"><span data-stu-id="6ec51-253">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="6ec51-254">如果这些步骤不起作用，可以尝试恢复 HoloLens 2 或[](hololens-recovery.md) [HoloLens (第一代) 设备。](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="6ec51-254">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="6ec51-255">返回列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-255">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="6ec51-256">"磁盘空间不足"错误</span><span class="sxs-lookup"><span data-stu-id="6ec51-256">"Low Disk Space" error</span></span>

<span data-ttu-id="6ec51-257">需要执行以下操作一个或多个来释放一些存储空间：</span><span class="sxs-lookup"><span data-stu-id="6ec51-257">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="6ec51-258">删除一些未使用的空格。</span><span class="sxs-lookup"><span data-stu-id="6ec51-258">Delete some unused spaces.</span></span> <span data-ttu-id="6ec51-259">转到"**设置**  >  **系统**  >  **空间**"，选择不再需要的空间，然后选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="6ec51-259">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="6ec51-260">删除放置的一些全息影像。</span><span class="sxs-lookup"><span data-stu-id="6ec51-260">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="6ec51-261">从照片应用中删除一些图片和视频。</span><span class="sxs-lookup"><span data-stu-id="6ec51-261">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="6ec51-262">从 HoloLens 卸载某些应用。</span><span class="sxs-lookup"><span data-stu-id="6ec51-262">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="6ec51-263">在"**所有应用"** 列表中，点击并按住要卸载的应用，然后选择"卸载 **"。**</span><span class="sxs-lookup"><span data-stu-id="6ec51-263">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="6ec51-264">返回列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-264">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="6ec51-265">校准失败</span><span class="sxs-lookup"><span data-stu-id="6ec51-265">Calibration fails</span></span>

<span data-ttu-id="6ec51-266">校准应该适用于大多数人员，但在某些情况下，校准会失败。</span><span class="sxs-lookup"><span data-stu-id="6ec51-266">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="6ec51-267">校准失败的一些潜在原因包括：</span><span class="sxs-lookup"><span data-stu-id="6ec51-267">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="6ec51-268">分散注意力，不遵循校准目标</span><span class="sxs-lookup"><span data-stu-id="6ec51-268">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="6ec51-269">脏设备或暂存的设备视板或设备视板未正确定位</span><span class="sxs-lookup"><span data-stu-id="6ec51-269">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="6ec51-270">脏眼镜或暂存的眼镜</span><span class="sxs-lookup"><span data-stu-id="6ec51-270">Dirty or scratched glasses</span></span>
- <span data-ttu-id="6ec51-271">某些类型的接触镜和眼镜 (彩色接触片、一些圆环接触镜、IR 阻塞眼镜、一些高光眼镜、眼镜或类似) </span><span class="sxs-lookup"><span data-stu-id="6ec51-271">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="6ec51-272">更明显的发音和一些眼线扩展</span><span class="sxs-lookup"><span data-stu-id="6ec51-272">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="6ec51-273">如果头框或粗眼镜框阻止设备看到眼睛</span><span class="sxs-lookup"><span data-stu-id="6ec51-273">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="6ec51-274">某些眼部眼部、眼部状况或眼部障碍，例如窄眼睛、长眼线、amblyopia、nystagmus、一些 LASIK 或其他眼部疾病</span><span class="sxs-lookup"><span data-stu-id="6ec51-274">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="6ec51-275">如果校准失败，请尝试：</span><span class="sxs-lookup"><span data-stu-id="6ec51-275">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="6ec51-276">清理设备视区</span><span class="sxs-lookup"><span data-stu-id="6ec51-276">Cleaning your device visor</span></span>
- <span data-ttu-id="6ec51-277">清理眼镜</span><span class="sxs-lookup"><span data-stu-id="6ec51-277">Cleaning your glasses</span></span>
- <span data-ttu-id="6ec51-278">将设备视器推送到尽可能靠近眼睛</span><span class="sxs-lookup"><span data-stu-id="6ec51-278">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="6ec51-279">将视器中的对象移开 (如发) </span><span class="sxs-lookup"><span data-stu-id="6ec51-279">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="6ec51-280">在房间中打开灯或离开直接光线</span><span class="sxs-lookup"><span data-stu-id="6ec51-280">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="6ec51-281">如果遵循所有准则并且校准仍然失败，可以在"设置"中禁用校准提示。</span><span class="sxs-lookup"><span data-stu-id="6ec51-281">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="6ec51-282">此外，请通过向 提交反馈来[反馈中心。](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="6ec51-282">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="6ec51-283">另请参阅图像颜色 [或亮度故障排除的相关信息。](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span><span class="sxs-lookup"><span data-stu-id="6ec51-283">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="6ec51-284">设置 IPD 不适用于HoloLens 2，因为眼睛位置由系统计算。</span><span class="sxs-lookup"><span data-stu-id="6ec51-284">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="6ec51-285">返回列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-285">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="6ec51-286">无法登录，因为之前为其他人设置了 HoloLens</span><span class="sxs-lookup"><span data-stu-id="6ec51-286">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="6ec51-287">可以将 [设备置于 **刷用模式，** 并使用高级恢复](hololens-recovery.md#clean-reflash-the-device) 助手来恢复设备。</span><span class="sxs-lookup"><span data-stu-id="6ec51-287">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="6ec51-288">返回列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-288">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="6ec51-289">Unity 不工作</span><span class="sxs-lookup"><span data-stu-id="6ec51-289">Unity isn't working</span></span>

- <span data-ttu-id="6ec51-290">有关 [用于](/windows/mixed-reality/install-the-tools) HoloLens 开发的建议最新版本的 Unity，请参阅安装工具。</span><span class="sxs-lookup"><span data-stu-id="6ec51-290">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="6ec51-291">[HoloLens Unity](https://forum.unity3d.com/threads/known-issues.394627/)论坛中记录了 Unity HoloLens Technical Preview 的已知问题。</span><span class="sxs-lookup"><span data-stu-id="6ec51-291">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="6ec51-292">返回列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-292">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="6ec51-293">Windows 设备门户无法正常工作</span><span class="sxs-lookup"><span data-stu-id="6ec51-293">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="6ec51-294">混合现实捕获中的实时预览功能可能会出现几秒钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="6ec51-294">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="6ec51-295">在"虚拟输入"页上，"虚拟手势"部分下的"手势"和"滚动"控件不起作用。</span><span class="sxs-lookup"><span data-stu-id="6ec51-295">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="6ec51-296">使用它们将不起作用。</span><span class="sxs-lookup"><span data-stu-id="6ec51-296">Using them will have no effect.</span></span> <span data-ttu-id="6ec51-297">虚拟输入页上的虚拟键盘正常工作。</span><span class="sxs-lookup"><span data-stu-id="6ec51-297">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="6ec51-298">在"设置"中启用"开发人员模式"后，可能需要几秒钟时间，开关才能设备门户打开。</span><span class="sxs-lookup"><span data-stu-id="6ec51-298">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="6ec51-299">返回列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-299">Back to list</span></span>](#list)

## <a name="emulator"></a><span data-ttu-id="6ec51-300">仿真器</span><span class="sxs-lookup"><span data-stu-id="6ec51-300">Emulator</span></span>
### <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="6ec51-301">HoloLens 模拟器不工作</span><span class="sxs-lookup"><span data-stu-id="6ec51-301">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="6ec51-302">有关 HoloLens 模拟器的信息位于我们的开发人员文档中。</span><span class="sxs-lookup"><span data-stu-id="6ec51-302">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="6ec51-303">阅读有关 [排查 HoloLens 模拟器问题的](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)详细信息。</span><span class="sxs-lookup"><span data-stu-id="6ec51-303">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="6ec51-304">并非 Microsoft Store 中的所有应用都与模拟器兼容。</span><span class="sxs-lookup"><span data-stu-id="6ec51-304">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="6ec51-305">例如，不能在模拟器上播放年轻人 Conker 和片段。</span><span class="sxs-lookup"><span data-stu-id="6ec51-305">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="6ec51-306">无法在仿真程序中使用 PC 网络摄像机。</span><span class="sxs-lookup"><span data-stu-id="6ec51-306">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="6ec51-307">Windows 设备门户的实时预览功能不适用于模拟器。</span><span class="sxs-lookup"><span data-stu-id="6ec51-307">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="6ec51-308">你仍可以捕获混合现实视频和图像。</span><span class="sxs-lookup"><span data-stu-id="6ec51-308">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="6ec51-309">返回到列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-309">Back to list</span></span>](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a><span data-ttu-id="6ec51-310">我找不到或无法使用键盘键入 HoloLens 2 模拟器</span><span class="sxs-lookup"><span data-stu-id="6ec51-310">I cannot find or use the keyboard to type in the HoloLens 2 Emulator</span></span>

<span data-ttu-id="6ec51-311">*即将推出*</span><span class="sxs-lookup"><span data-stu-id="6ec51-311">*Coming soon*</span></span>

[<span data-ttu-id="6ec51-312">返回到列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-312">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="6ec51-313">语音命令不起作用</span><span class="sxs-lookup"><span data-stu-id="6ec51-313">Voice commands aren't working</span></span>

<span data-ttu-id="6ec51-314">如果 Cortana 没有响应语音命令，请确保 Cortana 已打开。</span><span class="sxs-lookup"><span data-stu-id="6ec51-314">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="6ec51-315">在 "所有应用" 列表中，选择 " **Cortana**  >  **Menu**  >  **笔记本**  >  **设置**" 进行更改。</span><span class="sxs-lookup"><span data-stu-id="6ec51-315">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="6ec51-316">若要详细了解你可以说的内容，请参阅 [将你的语音与 HoloLens 配合使用](hololens-cortana.md)。</span><span class="sxs-lookup"><span data-stu-id="6ec51-316">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="6ec51-317">在 HoloLens (第一代) 上，内置语音识别不可配置。</span><span class="sxs-lookup"><span data-stu-id="6ec51-317">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="6ec51-318">始终打开。</span><span class="sxs-lookup"><span data-stu-id="6ec51-318">It is always turned on.</span></span> <span data-ttu-id="6ec51-319">在 HoloLens 2 上，你可以选择是否在设备设置期间打开语音识别和 Cortana。</span><span class="sxs-lookup"><span data-stu-id="6ec51-319">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="6ec51-320">如果 HoloLens 2 未响应语音，请确保已启用语音识别。</span><span class="sxs-lookup"><span data-stu-id="6ec51-320">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="6ec51-321">转到 "**开始**  >  **设置**  >  " "**隐私**  >  **语音**" 并打开 **语音识别**。</span><span class="sxs-lookup"><span data-stu-id="6ec51-321">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="6ec51-322">返回到列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-322">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="6ec51-323">手写输入不起作用</span><span class="sxs-lookup"><span data-stu-id="6ec51-323">Hand input isn't working</span></span>

<span data-ttu-id="6ec51-324">若要确保 HoloLens 能看到你的手，你需要将它们保留在手势帧中。</span><span class="sxs-lookup"><span data-stu-id="6ec51-324">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="6ec51-325">混合现实主页提供反馈，让你知道何时跟踪你的手。</span><span class="sxs-lookup"><span data-stu-id="6ec51-325">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="6ec51-326">不同版本的 HoloLens 的反馈有所不同：</span><span class="sxs-lookup"><span data-stu-id="6ec51-326">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="6ec51-327">在 HoloLens (第一代) 上，注视光标从点变为圆圈</span><span class="sxs-lookup"><span data-stu-id="6ec51-327">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="6ec51-328">在 HoloLens 2 上，当您的手接近于一手指时，会出现一个 "</span><span class="sxs-lookup"><span data-stu-id="6ec51-328">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="6ec51-329">许多沉浸式应用都遵循类似于混合现实主页的输入模式。</span><span class="sxs-lookup"><span data-stu-id="6ec51-329">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="6ec51-330">详细了解如何在 [hololens (第一代) ](hololens1-basic-usage.md#use-hololens-with-your-hands) 和 [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)上使用手动输入。</span><span class="sxs-lookup"><span data-stu-id="6ec51-330">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="6ec51-331">如果戴上手套，请注意，某些类型的手套不适用于手动跟踪。</span><span class="sxs-lookup"><span data-stu-id="6ec51-331">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="6ec51-332">常见的例子是黑色橡胶手套，这通常会吸收红外线，而不是由深度相机选取。</span><span class="sxs-lookup"><span data-stu-id="6ec51-332">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="6ec51-333">如果你的工作涉及橡胶手套，我们建议尝试使用较浅的颜色，如蓝色或灰色。</span><span class="sxs-lookup"><span data-stu-id="6ec51-333">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="6ec51-334">另一个示例是大型 baggy 手套，这种情况通常会使手不会遮盖。</span><span class="sxs-lookup"><span data-stu-id="6ec51-334">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="6ec51-335">为了获得最佳效果，我们建议使用以窗体为形式的手套。</span><span class="sxs-lookup"><span data-stu-id="6ec51-335">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="6ec51-336">如果面板具有指纹或无污迹，请使用 HoloLens 附带的 microfiber 清洁抹布来轻轻地清理面板。</span><span class="sxs-lookup"><span data-stu-id="6ec51-336">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="6ec51-337">返回到列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-337">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="6ec51-338">无法连接到 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="6ec51-338">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="6ec51-339">如果无法将 HoloLens 连接到 Wi-Fi 网络，请尝试以下操作：</span><span class="sxs-lookup"><span data-stu-id="6ec51-339">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="6ec51-340">请确保已打开 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="6ec51-340">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="6ec51-341">若要检查，请使用 "开始手势"，然后选择 "**设置**" "  >  **网络 &amp; Internet**  >  **wi-fi**"。</span><span class="sxs-lookup"><span data-stu-id="6ec51-341">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="6ec51-342">如果 Wi-Fi 处于打开状态，请尝试将其关闭，然后重新打开。</span><span class="sxs-lookup"><span data-stu-id="6ec51-342">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="6ec51-343">移动以靠近路由器或接入点。</span><span class="sxs-lookup"><span data-stu-id="6ec51-343">Move closer to the router or access point.</span></span>
- <span data-ttu-id="6ec51-344">重新启动 Wi-Fi 路由器，然后 [重新启动 HoloLens](hololens-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="6ec51-344">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="6ec51-345">请再次尝试连接。</span><span class="sxs-lookup"><span data-stu-id="6ec51-345">Try connecting again.</span></span>
- <span data-ttu-id="6ec51-346">如果这些操作都不起作用，请检查以确保路由器使用的是最新的固件。</span><span class="sxs-lookup"><span data-stu-id="6ec51-346">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="6ec51-347">你可以在制造商网站上找到此信息。</span><span class="sxs-lookup"><span data-stu-id="6ec51-347">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="6ec51-348">返回到列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-348">Back to list</span></span>](#list)
## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="6ec51-349">蓝牙设备不配对</span><span class="sxs-lookup"><span data-stu-id="6ec51-349">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="6ec51-350">如果在 [配对蓝牙设备](hololens-connect-devices.md)时遇到问题，请尝试以下操作：</span><span class="sxs-lookup"><span data-stu-id="6ec51-350">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="6ec51-351">转到 "**设置**  >  " "**设备**"，并确保已启用 "蓝牙"。</span><span class="sxs-lookup"><span data-stu-id="6ec51-351">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="6ec51-352">如果是，请将其关闭，然后重新打开。</span><span class="sxs-lookup"><span data-stu-id="6ec51-352">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="6ec51-353">请确保蓝牙设备已完全充电，或具有新电池。</span><span class="sxs-lookup"><span data-stu-id="6ec51-353">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="6ec51-354">如果仍然无法连接，请 [重新启动 HoloLens](hololens-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="6ec51-354">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="6ec51-355">返回到列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-355">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="6ec51-356">USB-C 麦克风不工作</span><span class="sxs-lookup"><span data-stu-id="6ec51-356">USB-C Microphone isn't working</span></span>
<span data-ttu-id="6ec51-357">请注意，某些 USB-C 麦克风会错误地将自身报告为麦克风 *和* 扬声器。</span><span class="sxs-lookup"><span data-stu-id="6ec51-357">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="6ec51-358">这是麦克风问题，而不是使用 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6ec51-358">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="6ec51-359">将其中一个麦克风插入 HoloLens 时，可能会丢失声音。</span><span class="sxs-lookup"><span data-stu-id="6ec51-359">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="6ec51-360">幸运的是，有一个简单的修补程序。</span><span class="sxs-lookup"><span data-stu-id="6ec51-360">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="6ec51-361">在 "**设置**  ->  **系统**  ->  **声音**" 中，显式设置内置扬声器 **(模拟功能音频驱动程序)** 作为 **默认设备**。</span><span class="sxs-lookup"><span data-stu-id="6ec51-361">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="6ec51-362">即使删除了麦克风并稍后重新连接，HoloLens 也应记住此设置。</span><span class="sxs-lookup"><span data-stu-id="6ec51-362">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C 麦克风疑难解答](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="6ec51-364">在设置中列为可用的设备不起作用</span><span class="sxs-lookup"><span data-stu-id="6ec51-364">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="6ec51-365">HoloLens (第一代) 不支持蓝牙音频配置文件。</span><span class="sxs-lookup"><span data-stu-id="6ec51-365">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="6ec51-366">蓝牙音频设备（如扬声器和耳机）在 HoloLens 设置中可能显示为可用，但不受支持。</span><span class="sxs-lookup"><span data-stu-id="6ec51-366">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="6ec51-367">HoloLens 2 支持用于立体声播放的蓝牙 A2DP 音频配置文件。</span><span class="sxs-lookup"><span data-stu-id="6ec51-367">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="6ec51-368">HoloLens 2 上不支持通过蓝牙外设启用麦克风捕获的蓝牙免提配置文件。</span><span class="sxs-lookup"><span data-stu-id="6ec51-368">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="6ec51-369">如果使用 Bluetooth 设备时遇到问题，请确保它是受支持的设备。</span><span class="sxs-lookup"><span data-stu-id="6ec51-369">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="6ec51-370">支持的设备包括：</span><span class="sxs-lookup"><span data-stu-id="6ec51-370">Supported devices include the following:</span></span>

- <span data-ttu-id="6ec51-371">使用英语语言的蓝牙键盘 (可以在任何使用全息键盘) 的地方使用。</span><span class="sxs-lookup"><span data-stu-id="6ec51-371">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="6ec51-372">蓝牙鼠标。</span><span class="sxs-lookup"><span data-stu-id="6ec51-372">Bluetooth mice.</span></span>
- <span data-ttu-id="6ec51-373">[HoloLens clicker](hololens1-clicker.md)。</span><span class="sxs-lookup"><span data-stu-id="6ec51-373">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="6ec51-374">可以将其他蓝牙 HID 和 GATT 设备与 HoloLens 配对。</span><span class="sxs-lookup"><span data-stu-id="6ec51-374">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="6ec51-375">但是，你可能需要从 Microsoft Store 安装相应的随附应用才能实际使用设备。</span><span class="sxs-lookup"><span data-stu-id="6ec51-375">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="6ec51-376">返回到列表</span><span class="sxs-lookup"><span data-stu-id="6ec51-376">Back to list</span></span>](#list)
