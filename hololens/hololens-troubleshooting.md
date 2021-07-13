---
title: HoloLens设备故障排除
description: 随时了解最新的解决方法 HoloLens 设备问题和故障排除方法。
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
keywords: 问题、错误、故障排除、修复、帮助、支持、HoloLens、模拟器
ms.openlocfilehash: b07514e73e43d267aa856c0fb9a256448e565000
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635443"
---
# <a name="device-troubleshooting"></a><span data-ttu-id="68489-104">设备故障排除</span><span class="sxs-lookup"><span data-stu-id="68489-104">Device Troubleshooting</span></span>

<span data-ttu-id="68489-105">本文介绍如何解决几个常见的 HoloLens 问题。</span><span class="sxs-lookup"><span data-stu-id="68489-105">This article describes how to resolve several common HoloLens issues.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="68489-106">在开始任何故障排除过程之前，请确保你的设备需要支付 **20 到 40%** 的电池容量（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="68489-106">Before you start any troubleshooting procedure, make sure that your device is charged to **20 to 40 percent** of battery capacity, if possible.</span></span> <span data-ttu-id="68489-107">"电源" 按钮下的 " [电池指示器" 指示灯](hololens2-setup.md#lights-that-indicate-the-battery-level) 是在不登录到设备的情况下快速验证电池容量的方法。</span><span class="sxs-lookup"><span data-stu-id="68489-107">The [battery indicator lights](hololens2-setup.md#lights-that-indicate-the-battery-level) located under the power button are a quick way to verify the battery capacity without logging into the device.</span></span>

<a id="list"></a>

<span data-ttu-id="68489-108">**已知问题**</span><span class="sxs-lookup"><span data-stu-id="68489-108">**Known Issues**</span></span>
- [<span data-ttu-id="68489-109">远程协助视频在20分钟后冻结</span><span class="sxs-lookup"><span data-stu-id="68489-109">Remote Assist video freezes after 20 minutes</span></span>](#remote-assist-video-freezes-after-20-minutes)
- [<span data-ttu-id="68489-110">自动登录请求登录</span><span class="sxs-lookup"><span data-stu-id="68489-110">Auto-login asks for log-in</span></span>](#auto-login-asks-for-log-in)
- [<span data-ttu-id="68489-111">无法启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="68489-111">Microsoft Edge fails to launch</span></span>](#microsoft-edge-fails-to-launch)
- [<span data-ttu-id="68489-112">键盘无法切换为特殊字符</span><span class="sxs-lookup"><span data-stu-id="68489-112">Keyboard doesn't switch to special characters</span></span>](#keyboard-doesnt-switch-to-special-characters)
- [<span data-ttu-id="68489-113">下载锁定的文件不显示错误</span><span class="sxs-lookup"><span data-stu-id="68489-113">Downloading locked files doesn't show error</span></span>](#downloading-locked-files-doesnt-error)
- [<span data-ttu-id="68489-114">设备门户文件上传/下载超时</span><span class="sxs-lookup"><span data-stu-id="68489-114">Device Portal file upload/download times out</span></span>](#device-portal-file-uploaddownload-times-out)
- [<span data-ttu-id="68489-115">取消注册在使用 Insider 内部版本闪存的设备上预览有问必答后的蓝屏</span><span class="sxs-lookup"><span data-stu-id="68489-115">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [<span data-ttu-id="68489-116">OneDrive 不会自动上载图片</span><span class="sxs-lookup"><span data-stu-id="68489-116">OneDrive doesn't automatically upload pictures</span></span>](#onedrive-doesnt-automatically-upload-pictures)

<span data-ttu-id="68489-117">**常规**</span><span class="sxs-lookup"><span data-stu-id="68489-117">**General**</span></span>
- [<span data-ttu-id="68489-118">HoloLens 无响应或不启动</span><span class="sxs-lookup"><span data-stu-id="68489-118">HoloLens is unresponsive or won't start</span></span>](#hololens-is-unresponsive-or-wont-start)
- [<span data-ttu-id="68489-119">"磁盘空间不足" 错误</span><span class="sxs-lookup"><span data-stu-id="68489-119">"Low Disk Space" error</span></span>](#low-disk-space-error)
- [<span data-ttu-id="68489-120">校准失败</span><span class="sxs-lookup"><span data-stu-id="68489-120">Calibration Fails</span></span>](#calibration-fails)
- [<span data-ttu-id="68489-121">无法登录，因为以前为其他人设置了我的 HoloLens</span><span class="sxs-lookup"><span data-stu-id="68489-121">Can't sign in because my HoloLens was previously set up for someone else</span></span>](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [<span data-ttu-id="68489-122">Unity 不起作用</span><span class="sxs-lookup"><span data-stu-id="68489-122">Unity isn't working</span></span>](#unity-isnt-working)
- [<span data-ttu-id="68489-123">Windows设备门户工作不正常</span><span class="sxs-lookup"><span data-stu-id="68489-123">Windows Device Portal isn't working correctly</span></span>](#windows-device-portal-isnt-working-correctly)
- [<span data-ttu-id="68489-124">HoloLens Emulator 不起作用</span><span class="sxs-lookup"><span data-stu-id="68489-124">The HoloLens Emulator isn't working</span></span>](#the-hololens-emulator-isnt-working)

<span data-ttu-id="68489-125">**输入**</span><span class="sxs-lookup"><span data-stu-id="68489-125">**Input**</span></span>
- [<span data-ttu-id="68489-126">语音命令不起作用</span><span class="sxs-lookup"><span data-stu-id="68489-126">Voice commands aren't working</span></span>](#voice-commands-arent-working)
- [<span data-ttu-id="68489-127">手写输入不起作用</span><span class="sxs-lookup"><span data-stu-id="68489-127">Hand input isn't working</span></span>](#hand-input-isnt-working)

<span data-ttu-id="68489-128">**连接**</span><span class="sxs-lookup"><span data-stu-id="68489-128">**Connectivity**</span></span>
- [<span data-ttu-id="68489-129">无法连接到 Wi-fi</span><span class="sxs-lookup"><span data-stu-id="68489-129">Can't connect to Wi-Fi</span></span>](#cant-connect-to-wi-fi)

<span data-ttu-id="68489-130">**外部设备**</span><span class="sxs-lookup"><span data-stu-id="68489-130">**External Devices**</span></span> 
- [<span data-ttu-id="68489-131">蓝牙设备不配对</span><span class="sxs-lookup"><span data-stu-id="68489-131">Bluetooth devices aren't pairing</span></span>](#bluetooth-devices-arent-pairing)
- [<span data-ttu-id="68489-132">USB-C 麦克风不工作</span><span class="sxs-lookup"><span data-stu-id="68489-132">USB-C Microphone isn't working</span></span>](#usb-c-microphone-isnt-working)
- [<span data-ttu-id="68489-133">列为设置的设备不起作用</span><span class="sxs-lookup"><span data-stu-id="68489-133">Devices listed as available in Settings don't work</span></span>](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a><span data-ttu-id="68489-134">远程协助视频在20分钟后冻结</span><span class="sxs-lookup"><span data-stu-id="68489-134">Remote Assist video freezes after 20 minutes</span></span>

> [!NOTE]
> <span data-ttu-id="68489-135">有一个较新版本的远程协助，此问题可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="68489-135">There is a newer version of Remote Assist which has a fix for this issue.</span></span> <span data-ttu-id="68489-136">请将 [远程协助更新](holographic-store-apps.md#update-apps) 到最新版本，以避免此问题。</span><span class="sxs-lookup"><span data-stu-id="68489-136">Please [update Remote Assist](holographic-store-apps.md#update-apps) to the latest version to avoid this issue.</span></span>

> [!NOTE]
> <span data-ttu-id="68489-137">由于此已知问题的严重性，我们暂时暂停 Windows 全息版21H1 的可用性。</span><span class="sxs-lookup"><span data-stu-id="68489-137">Due to this Known Issue's severity we had temporarily paused the availability of Windows Holographic, version 21H1.</span></span> <span data-ttu-id="68489-138">现在可再次使用21H1 生成，因此设备可能会再次更新为最新的21H1 版本。</span><span class="sxs-lookup"><span data-stu-id="68489-138">The 21H1 build is now available again, so devices may once again be updated to the latest 21H1 build.</span></span>

<span data-ttu-id="68489-139">在最新版本的[Windows 全息版 21H1](hololens-release-notes.md#windows-holographic-version-21h1)上，某些远程协助用户在20分钟调用期间经历了视频冻结。</span><span class="sxs-lookup"><span data-stu-id="68489-139">On the latest release of [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), some users of Remote Assist have experienced video freezing during calls over 20 minutes.</span></span> <span data-ttu-id="68489-140">这是一个 **已知问题**。</span><span class="sxs-lookup"><span data-stu-id="68489-140">This is a **known issue**.</span></span>

### <a name="workarounds"></a><span data-ttu-id="68489-141">解决方法</span><span class="sxs-lookup"><span data-stu-id="68489-141">Workarounds</span></span>

<span data-ttu-id="68489-142">如果无法将远程协助更新到较新的版本，请尝试以下解决方法。</span><span class="sxs-lookup"><span data-stu-id="68489-142">If you are unable to update Remote Assist to a newer build try the following work around.</span></span>

#### <a name="restart-in-between-calls"></a><span data-ttu-id="68489-143">在两次调用之间重启</span><span class="sxs-lookup"><span data-stu-id="68489-143">Restart in between calls</span></span>

<span data-ttu-id="68489-144">如果调用的持续时间超过20分钟并且遇到此问题，请尝试重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="68489-144">If your calls are going over a length of 20 minutes and you are experiencing this issue, try rebooting your device.</span></span> <span data-ttu-id="68489-145">在远程协助调用之间重启设备会刷新设备，并将其恢复到正常状态。</span><span class="sxs-lookup"><span data-stu-id="68489-145">Rebooting your device between Remote Assist calls will refresh your device and put it back into a good state.</span></span>

<span data-ttu-id="68489-146">若要在 [Windows 全息版](hololens-release-notes.md#windows-holographic-version-21h1)上快速重启设备，请打开 "开始" 菜单，选择 "用户" 图标，然后选择 "**重新启动**"。</span><span class="sxs-lookup"><span data-stu-id="68489-146">To quickly restart a device on [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1) open the start menu, and select the user icon, then select **Restart**.</span></span>

[<span data-ttu-id="68489-147">返回到列表</span><span class="sxs-lookup"><span data-stu-id="68489-147">Back to list</span></span>](#list)

## <a name="auto-login-asks-for-log-in"></a><span data-ttu-id="68489-148">自动登录请求登录</span><span class="sxs-lookup"><span data-stu-id="68489-148">Auto-login asks for log-in</span></span>

<span data-ttu-id="68489-149">可以将 HoloLens 2 设备配置为通过 **设置**  ->  **帐户**  ->  **登录选项** 自动登录->，在 "**必需**" 下，将值设置为 "**从不**"。</span><span class="sxs-lookup"><span data-stu-id="68489-149">A HoloLens 2 device can be configured to automatically login in via **Settings** -> **Accounts** -> **Sign-in Options** -> and under **Required** setting the value to **Never**.</span></span> <span data-ttu-id="68489-150">当更新设备时，某些用户可能需要再次登录到该设备，如功能更新。</span><span class="sxs-lookup"><span data-stu-id="68489-150">Some users may be required to log-in to the device again when updating a device with a substantially large update, such as a feature update.</span></span> <span data-ttu-id="68489-151">这是一个 **已知问题**。</span><span class="sxs-lookup"><span data-stu-id="68489-151">This is a **known issue**.</span></span>

<span data-ttu-id="68489-152">此情况的示例：</span><span class="sxs-lookup"><span data-stu-id="68489-152">Example of when this could occur:</span></span>

- <span data-ttu-id="68489-153">将设备从 Windows 全息版本 2004 (版本生成 19041) Windows 全息，版本 21H1 (build 20346) </span><span class="sxs-lookup"><span data-stu-id="68489-153">Updating a device from Windows Holographic, version 2004 (Build 19041.xxxx) to Windows Holographic, version 21H1 (Build 20346.xxxx)</span></span>
- <span data-ttu-id="68489-154">更新设备以在同一主版本上进行较大的更新，例如 Windows 全息版，版本2004到 Windows 全息版本20H2</span><span class="sxs-lookup"><span data-stu-id="68489-154">Updating a device to take a large update on the same major build, e.g. Windows Holographic, version 2004 to Windows Holographic, version 20H2</span></span>
- <span data-ttu-id="68489-155">将设备从出厂映像更新到最新映像</span><span class="sxs-lookup"><span data-stu-id="68489-155">Updating a device from a factory image to the latest image</span></span>

<span data-ttu-id="68489-156">在以下过程中不应发生此情况：</span><span class="sxs-lookup"><span data-stu-id="68489-156">This should not occur during:</span></span>

- <span data-ttu-id="68489-157">参与每月服务更新的设备</span><span class="sxs-lookup"><span data-stu-id="68489-157">Devices taking a monthly servicing update</span></span>

<span data-ttu-id="68489-158">解决方法：</span><span class="sxs-lookup"><span data-stu-id="68489-158">Work around methods:</span></span>

- <span data-ttu-id="68489-159">登录方法，例如 PIN、Password、Iris、Web Authentication 或 FIDO2 键。</span><span class="sxs-lookup"><span data-stu-id="68489-159">Sign-in methods such as PIN, Password, Iris, Web Authentication, or FIDO2 keys.</span></span>
- <span data-ttu-id="68489-160">如果无法记住设备 PIN，并且其他身份验证方法不可用，则用户可以使用 [手动 reflashing 模式](hololens-recovery.md#manual-procedure)。</span><span class="sxs-lookup"><span data-stu-id="68489-160">If device PIN cannot be remembered, and other authentication methods are not available, then a user can use [manual reflashing mode](hololens-recovery.md#manual-procedure).</span></span>

[<span data-ttu-id="68489-161">返回到列表</span><span class="sxs-lookup"><span data-stu-id="68489-161">Back to list</span></span>](#list)

## <a name="microsoft-edge-fails-to-launch"></a><span data-ttu-id="68489-162">无法启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="68489-162">Microsoft Edge fails to launch</span></span>

> [!NOTE]
> <span data-ttu-id="68489-163">此问题最初是在 Microsoft Edge 的发货版本中创建的。</span><span class="sxs-lookup"><span data-stu-id="68489-163">This issue was originally created with the shipping version of Microsoft Edge in-mind.</span></span> <span data-ttu-id="68489-164">此问题可能已在新的[Microsoft Edge](hololens-new-edge.md)中解决。</span><span class="sxs-lookup"><span data-stu-id="68489-164">This issue may be resolved in the [new Microsoft Edge](hololens-new-edge.md).</span></span> <span data-ttu-id="68489-165">如果不是，请提供文件反馈。</span><span class="sxs-lookup"><span data-stu-id="68489-165">If it is not, please file feedback.</span></span>

<span data-ttu-id="68489-166">几个客户报告了 Microsoft Edge 无法启动的问题。</span><span class="sxs-lookup"><span data-stu-id="68489-166">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="68489-167">对于这些客户，此问题将在重新启动后仍然存在，并且不会与 Windows 或应用程序更新一起解决。</span><span class="sxs-lookup"><span data-stu-id="68489-167">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="68489-168">如果你遇到此问题，并且已确认[Windows 是最](hololens-updates.md#manually-check-for-updates)新的，请使用以下类别和子类别从[反馈中心应用](hololens-feedback.md)中提交 bug：安装和更新 > 下载、安装和配置 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="68489-168">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="68489-169">没有已知的解决方法，因为我们不能根本就会导致问题。</span><span class="sxs-lookup"><span data-stu-id="68489-169">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="68489-170">通过反馈中心归档 bug 可帮助我们调查！</span><span class="sxs-lookup"><span data-stu-id="68489-170">Filing a bug via Feedback Hub will help our investigation!</span></span> <span data-ttu-id="68489-171">这是一个 **已知问题**。</span><span class="sxs-lookup"><span data-stu-id="68489-171">This is a **known issue**.</span></span>

[<span data-ttu-id="68489-172">返回到列表</span><span class="sxs-lookup"><span data-stu-id="68489-172">Back to list</span></span>](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a><span data-ttu-id="68489-173">键盘无法切换为特殊字符</span><span class="sxs-lookup"><span data-stu-id="68489-173">Keyboard doesn't switch to special characters</span></span>

<span data-ttu-id="68489-174">OOBE 期间存在问题，在用户选择工作或学校帐户并输入密码后，尝试通过点击 "&123" 按钮切换到键盘上的特殊字符不会更改为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="68489-174">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> <span data-ttu-id="68489-175">这是一个 **已知问题**。</span><span class="sxs-lookup"><span data-stu-id="68489-175">This is a **known issue**.</span></span>

<span data-ttu-id="68489-176">解决办法：</span><span class="sxs-lookup"><span data-stu-id="68489-176">Work-arounds:</span></span>
-   <span data-ttu-id="68489-177">关闭键盘，并通过点击 "文本" 字段将其重新打开。</span><span class="sxs-lookup"><span data-stu-id="68489-177">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="68489-178">输入的密码不正确。</span><span class="sxs-lookup"><span data-stu-id="68489-178">Incorrectly enter your password.</span></span> <span data-ttu-id="68489-179">下一次变时，它将按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="68489-179">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="68489-180">Web 身份验证，关闭键盘，然后选择 **"从其他设备登录"**。</span><span class="sxs-lookup"><span data-stu-id="68489-180">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span>
-   <span data-ttu-id="68489-181">如果只输入数字，用户可以按并按住某些键来打开展开的菜单。</span><span class="sxs-lookup"><span data-stu-id="68489-181">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="68489-182">使用 USB 键盘。</span><span class="sxs-lookup"><span data-stu-id="68489-182">Using a USB keyboard.</span></span>

<span data-ttu-id="68489-183">这不会影响：</span><span class="sxs-lookup"><span data-stu-id="68489-183">This does not affect:</span></span>
- <span data-ttu-id="68489-184">选择使用个人帐户的用户。</span><span class="sxs-lookup"><span data-stu-id="68489-184">Users who choose to use a personal account.</span></span>

[<span data-ttu-id="68489-185">返回到列表</span><span class="sxs-lookup"><span data-stu-id="68489-185">Back to list</span></span>](#list)

## <a name="downloading-locked-files-doesnt-error"></a><span data-ttu-id="68489-186">下载锁定的文件不出错</span><span class="sxs-lookup"><span data-stu-id="68489-186">Downloading locked files doesn't error</span></span>

> [!NOTE]
> <span data-ttu-id="68489-187">这是一个 **已知问题**，此问题已在 Windows 内幕版本20348.1403 中解决。</span><span class="sxs-lookup"><span data-stu-id="68489-187">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span>

<span data-ttu-id="68489-188">在 Windows 全息版的以前版本中，尝试下载锁定文件时，结果将是 HTTP 错误页。</span><span class="sxs-lookup"><span data-stu-id="68489-188">In previous builds of Windows Holographic, when attempting to download a locked file, the result would be an HTTP error page.</span></span> <span data-ttu-id="68489-189">在 Windows 全息版21H1 更新中，尝试下载锁定的文件会导致不会出现任何问题，文件不会下载，也不会出错。</span><span class="sxs-lookup"><span data-stu-id="68489-189">In the Windows Holographic, version 21H1 update, trying to download a locked file results in nothing visible happening—the file doesn’t download and there’s no error.</span></span>

[<span data-ttu-id="68489-190">返回到列表</span><span class="sxs-lookup"><span data-stu-id="68489-190">Back to list</span></span>](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a><span data-ttu-id="68489-191">设备门户文件上传/下载超时</span><span class="sxs-lookup"><span data-stu-id="68489-191">Device Portal file upload/download times out</span></span>
> [!NOTE]
> <span data-ttu-id="68489-192">这是一个 **已知问题**，此问题已在 Windows 内幕版本20348.1403 中解决。</span><span class="sxs-lookup"><span data-stu-id="68489-192">This is a **known issue** that is fixed in Windows Insider build, version 20348.1403.</span></span> <span data-ttu-id="68489-193">如果你之前已禁用 SSL 连接作为解决方法的一部分，我们强烈建议你重新启用它。</span><span class="sxs-lookup"><span data-stu-id="68489-193">If you previously disabled SSL Connection as part of the workaround, we highly recommend you re-enable it.</span></span>


<span data-ttu-id="68489-194">有些客户在尝试上载或下载文件时发现，该操作可能会挂起，然后超时或永不完成。</span><span class="sxs-lookup"><span data-stu-id="68489-194">Some customers have found, when attempting to upload or download files, the operation might appear to hang and then time out or never complete.</span></span> <span data-ttu-id="68489-195">这不同于 "[文件锁定" 已知问题](#downloading-locked-files-doesnt-error)-这会影响 Windows 全息版、2004版、20H2 和21H1 内部版本。</span><span class="sxs-lookup"><span data-stu-id="68489-195">This is separate from the '[file locked' known issue](#downloading-locked-files-doesnt-error) -- this affects Windows Holographic, versions 2004, 20H2 and 21H1 in-market builds.</span></span> <span data-ttu-id="68489-196">此问题根本是导致设备门户对某些请求的处理中的 bug 引起的，并且在使用 https （默认值）时，这是最常见的。</span><span class="sxs-lookup"><span data-stu-id="68489-196">The problem has been root caused to a bug in Device Portal's handling of certain requests, and is most consistently hit when using https, which is the default.</span></span> 

### <a name="workaround"></a><span data-ttu-id="68489-197">解决方法</span><span class="sxs-lookup"><span data-stu-id="68489-197">Workaround</span></span>

<span data-ttu-id="68489-198">此解决方法（同样适用于 Wi-Fi 和 UsbNcm）是在 "SSL 连接" 下禁用 "必需" 选项。</span><span class="sxs-lookup"><span data-stu-id="68489-198">This workaround, which applies equally to Wi-Fi and UsbNcm, is to disable the "required" option under "SSL Connection".</span></span> <span data-ttu-id="68489-199">为此，请导航到 "设备门户" 和 " **系统**"，然后选择 " **首选项** " 页。</span><span class="sxs-lookup"><span data-stu-id="68489-199">To do so, navigate to Device Portal, **System**, and select the **Preferences** page.</span></span> <span data-ttu-id="68489-200">在 " **设备安全性** " 部分中，找到 " **SSL 连接**"，并取消选中以禁用 **所需** 的。</span><span class="sxs-lookup"><span data-stu-id="68489-200">In the **Device Security** section, locate **SSL Connection**, and uncheck to disable **Required**.</span></span>

<span data-ttu-id="68489-201">然后，用户应转到 http://，https:// (IP 地址) 文件上传和下载等功能将正常工作。</span><span class="sxs-lookup"><span data-stu-id="68489-201">The user should then go to http://, not https:// (IP address) and features like file upload and download will work.</span></span>

[<span data-ttu-id="68489-202">返回列表</span><span class="sxs-lookup"><span data-stu-id="68489-202">Back to list</span></span>](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a><span data-ttu-id="68489-203">从预览体验成员预览版取消注册后，在设备上以预览体验成员版本刷出蓝屏</span><span class="sxs-lookup"><span data-stu-id="68489-203">Blue screen after unenrolling from Insider preview on a device flashed with an Insider build</span></span>

<span data-ttu-id="68489-204">这是影响使用 Insider 预览版的用户的问题，使用新的预览版重新HoloLens 2预览体验版，然后从预览体验计划取消注册。</span><span class="sxs-lookup"><span data-stu-id="68489-204">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> <span data-ttu-id="68489-205">这是一个 **已知问题**。</span><span class="sxs-lookup"><span data-stu-id="68489-205">This is a **known issue**.</span></span>

<span data-ttu-id="68489-206">这不会影响：</span><span class="sxs-lookup"><span data-stu-id="68489-206">This does not affect:</span></span>
- <span data-ttu-id="68489-207">未在预览体验成员Windows用户</span><span class="sxs-lookup"><span data-stu-id="68489-207">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="68489-208">业内 人士：</span><span class="sxs-lookup"><span data-stu-id="68489-208">Insiders:</span></span>
    - <span data-ttu-id="68489-209">如果设备自预览体验内部版本为版本 18362.x 以来已注册</span><span class="sxs-lookup"><span data-stu-id="68489-209">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="68489-210">如果他们刷过预览体验成员签名的 19041.x 内部版本，并一直注册到 Insider 计划</span><span class="sxs-lookup"><span data-stu-id="68489-210">If they flashed an Insider signed 19041.x build AND stay enrolled in the Insider program</span></span>

<span data-ttu-id="68489-211">工作之一：</span><span class="sxs-lookup"><span data-stu-id="68489-211">Work-around:</span></span> 
- <span data-ttu-id="68489-212">避免此问题</span><span class="sxs-lookup"><span data-stu-id="68489-212">Avoid the issue</span></span> 
    - <span data-ttu-id="68489-213">刷用非预览体验内部版本。</span><span class="sxs-lookup"><span data-stu-id="68489-213">Flash a non-insider build.</span></span> <span data-ttu-id="68489-214">每月定期更新之一。</span><span class="sxs-lookup"><span data-stu-id="68489-214">One of the regular monthly updates.</span></span>
    - <span data-ttu-id="68489-215">随时了解预览体验成员</span><span class="sxs-lookup"><span data-stu-id="68489-215">Stay on Insider Preview</span></span>
- <span data-ttu-id="68489-216">重新运行设备</span><span class="sxs-lookup"><span data-stu-id="68489-216">Reflash the device</span></span>

    1. <span data-ttu-id="68489-217">在[未HoloLens 2](hololens-recovery.md)时完全关闭电源，将设备手动置于闪烁模式。</span><span class="sxs-lookup"><span data-stu-id="68489-217">Put the [HoloLens 2 into flashing mode](hololens-recovery.md) manually by fully powering down while not connect.</span></span> <span data-ttu-id="68489-218">然后，在按住"音量"的同时，点击"电源"按钮。</span><span class="sxs-lookup"><span data-stu-id="68489-218">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="68489-219">连接电脑并打开"高级恢复助手"。</span><span class="sxs-lookup"><span data-stu-id="68489-219">Connect to the PC and open Advanced Recovery Companion.</span></span>
    
    1. <span data-ttu-id="68489-220">将HoloLens 2刷新为默认生成。</span><span class="sxs-lookup"><span data-stu-id="68489-220">Flash the HoloLens 2 to the default build.</span></span>

[<span data-ttu-id="68489-221">返回列表</span><span class="sxs-lookup"><span data-stu-id="68489-221">Back to list</span></span>](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a><span data-ttu-id="68489-222">OneDrive不会自动上传图片</span><span class="sxs-lookup"><span data-stu-id="68489-222">OneDrive doesn't automatically upload pictures</span></span>

<span data-ttu-id="68489-223">OneDrive应用HoloLens工作或学校帐户的自动相机上传。</span><span class="sxs-lookup"><span data-stu-id="68489-223">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span> <span data-ttu-id="68489-224">这是一个 **已知问题**。</span><span class="sxs-lookup"><span data-stu-id="68489-224">This is a **known issue**.</span></span>

<span data-ttu-id="68489-225">解决方法：</span><span class="sxs-lookup"><span data-stu-id="68489-225">Workarounds:</span></span>

- <span data-ttu-id="68489-226">如果你的业务可行，则使用者 Microsoft 帐户支持自动上传相机。</span><span class="sxs-lookup"><span data-stu-id="68489-226">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="68489-227">除了工作或学校帐户Microsoft 帐户还可以登录到 (，OneDrive应用支持双重登录) 。</span><span class="sxs-lookup"><span data-stu-id="68489-227">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="68489-228">在Microsoft 帐户配置文件OneDrive启用自动后台相机滚动上传。</span><span class="sxs-lookup"><span data-stu-id="68489-228">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="68489-229">如果无法安全地使用使用者Microsoft 帐户自动上传照片，可以从应用将照片手动上传到工作或OneDrive帐户。</span><span class="sxs-lookup"><span data-stu-id="68489-229">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="68489-230">为此，请确保已登录到应用应用OneDrive帐户。</span><span class="sxs-lookup"><span data-stu-id="68489-230">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="68489-231">选择按钮 **+** 并选择"Upload"。 </span><span class="sxs-lookup"><span data-stu-id="68489-231">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="68489-232">通过导航到"照片"和"相机滚动> **上传的照片或视频**。</span><span class="sxs-lookup"><span data-stu-id="68489-232">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="68489-233">选择要上传的一个或多个照片或视频，然后选择"打开 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="68489-233">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

[<span data-ttu-id="68489-234">返回列表</span><span class="sxs-lookup"><span data-stu-id="68489-234">Back to list</span></span>](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="68489-235">HoloLens无响应或无法启动</span><span class="sxs-lookup"><span data-stu-id="68489-235">HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="68489-236">如果HoloLens启动：</span><span class="sxs-lookup"><span data-stu-id="68489-236">If your HoloLens won't start:</span></span>

- <span data-ttu-id="68489-237">如果电源按钮旁边的 LED 不亮起，或只有一个 LED 短暂闪烁，可能需要为电源[HoloLens。](hololens2-charging.md#charging-the-device)</span><span class="sxs-lookup"><span data-stu-id="68489-237">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens2-charging.md#charging-the-device)</span></span>
- <span data-ttu-id="68489-238">如果 LED 在按下电源按钮时亮起，但在显示器上看不到任何内容，请对设备 进行 [硬重置](hololens-recovery.md#hard-reset-procedure)。</span><span class="sxs-lookup"><span data-stu-id="68489-238">If the LEDs light up when you press the power button but you can't see anything on the displays, [do a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="68489-239">如果HoloLens冻结或无响应：</span><span class="sxs-lookup"><span data-stu-id="68489-239">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="68489-240">按电源HoloLens关闭电源按钮，直到所有五个 LED 都自行关闭，如果 LED 无响应，则关闭 15 秒。</span><span class="sxs-lookup"><span data-stu-id="68489-240">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="68489-241">若要启动HoloLens，请再次按电源按钮。</span><span class="sxs-lookup"><span data-stu-id="68489-241">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="68489-242">如果这些步骤不起作用，可以尝试恢复设备HoloLens 2或HoloLens ([](hololens-recovery.md)第[一代) 设备。](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="68489-242">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

[<span data-ttu-id="68489-243">返回列表</span><span class="sxs-lookup"><span data-stu-id="68489-243">Back to list</span></span>](#list)

## <a name="low-disk-space-error"></a><span data-ttu-id="68489-244">"磁盘空间不足"错误</span><span class="sxs-lookup"><span data-stu-id="68489-244">"Low Disk Space" error</span></span>

<span data-ttu-id="68489-245">需要执行以下操作一个或多个来释放一些存储空间：</span><span class="sxs-lookup"><span data-stu-id="68489-245">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="68489-246">删除一些未使用的空格。</span><span class="sxs-lookup"><span data-stu-id="68489-246">Delete some unused spaces.</span></span> <span data-ttu-id="68489-247">转到设置  >  **系统**  >  **空间"，** 选择不再需要的空间，然后选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="68489-247">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="68489-248">删除放置的一些全息影像。</span><span class="sxs-lookup"><span data-stu-id="68489-248">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="68489-249">从照片应用中删除一些图片和视频。</span><span class="sxs-lookup"><span data-stu-id="68489-249">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="68489-250">从应用程序卸载HoloLens。</span><span class="sxs-lookup"><span data-stu-id="68489-250">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="68489-251">在"**所有应用"** 列表中，点击并按住要卸载的应用，然后选择"卸载 **"。**</span><span class="sxs-lookup"><span data-stu-id="68489-251">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

[<span data-ttu-id="68489-252">返回列表</span><span class="sxs-lookup"><span data-stu-id="68489-252">Back to list</span></span>](#list)

## <a name="calibration-fails"></a><span data-ttu-id="68489-253">校准失败</span><span class="sxs-lookup"><span data-stu-id="68489-253">Calibration fails</span></span>

<span data-ttu-id="68489-254">校准应该适用于大多数人员，但在某些情况下，校准会失败。</span><span class="sxs-lookup"><span data-stu-id="68489-254">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="68489-255">校准失败的一些潜在原因包括：</span><span class="sxs-lookup"><span data-stu-id="68489-255">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="68489-256">分散注意力，不遵循校准目标</span><span class="sxs-lookup"><span data-stu-id="68489-256">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="68489-257">脏设备或暂存的设备视板或设备视板未正确定位</span><span class="sxs-lookup"><span data-stu-id="68489-257">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="68489-258">脏眼镜或暂存的眼镜</span><span class="sxs-lookup"><span data-stu-id="68489-258">Dirty or scratched glasses</span></span>
- <span data-ttu-id="68489-259">某些类型的接触镜和眼镜 (彩色接触片、一些圆环接触镜、IR 阻塞眼镜、一些高光眼镜、眼镜或类似) </span><span class="sxs-lookup"><span data-stu-id="68489-259">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="68489-260">更明显的发音和一些眼线扩展</span><span class="sxs-lookup"><span data-stu-id="68489-260">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="68489-261">如果头框或粗眼镜框阻止设备看到眼睛</span><span class="sxs-lookup"><span data-stu-id="68489-261">Hair or thick eyeglass frames if they're blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="68489-262">某些眼部眼部、眼部状况或眼部障碍，例如窄眼睛、长眼线、amblyopia、nystagmus、一些 LASIK 或其他眼部疾病</span><span class="sxs-lookup"><span data-stu-id="68489-262">Certain eye physiology, eye conditions, or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="68489-263">如果校准失败，请尝试：</span><span class="sxs-lookup"><span data-stu-id="68489-263">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="68489-264">清理设备视区</span><span class="sxs-lookup"><span data-stu-id="68489-264">Cleaning your device visor</span></span>
- <span data-ttu-id="68489-265">清理眼镜</span><span class="sxs-lookup"><span data-stu-id="68489-265">Cleaning your glasses</span></span>
- <span data-ttu-id="68489-266">将设备视器推送到尽可能靠近眼睛</span><span class="sxs-lookup"><span data-stu-id="68489-266">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="68489-267">将视器中的对象移开 (如发) </span><span class="sxs-lookup"><span data-stu-id="68489-267">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="68489-268">在房间中打开灯或离开直接光线</span><span class="sxs-lookup"><span data-stu-id="68489-268">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="68489-269">如果遵循所有准则，并且校准仍失败，可以在测试中禁用校准设置。</span><span class="sxs-lookup"><span data-stu-id="68489-269">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="68489-270">此外，请通过向 提交反馈来[反馈中心。](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="68489-270">Also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="68489-271">另请参阅图像颜色 [或亮度故障排除的相关信息。](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span><span class="sxs-lookup"><span data-stu-id="68489-271">Also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="68489-272">设置 IPD 不适用于HoloLens 2，因为眼睛位置由系统计算。</span><span class="sxs-lookup"><span data-stu-id="68489-272">Setting IPD is not applicable for HoloLens 2, since eye positions are computed by the system.</span></span> 

[<span data-ttu-id="68489-273">返回列表</span><span class="sxs-lookup"><span data-stu-id="68489-273">Back to list</span></span>](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a><span data-ttu-id="68489-274">无法登录，因为之前为HoloLens设置了我的帐户</span><span class="sxs-lookup"><span data-stu-id="68489-274">Can't sign in because my HoloLens was previously set up for someone else</span></span>

<span data-ttu-id="68489-275">可以将 [设备置于 **刷用模式，** 并使用高级恢复](hololens-recovery.md#clean-reflash-the-device) 助手来恢复设备。</span><span class="sxs-lookup"><span data-stu-id="68489-275">You can [put the device into **Flashing Mode** and use Advanced Recovery Companion](hololens-recovery.md#clean-reflash-the-device) to recover the device.</span></span>

[<span data-ttu-id="68489-276">返回列表</span><span class="sxs-lookup"><span data-stu-id="68489-276">Back to list</span></span>](#list)


## <a name="unity-isnt-working"></a><span data-ttu-id="68489-277">Unity 不工作</span><span class="sxs-lookup"><span data-stu-id="68489-277">Unity isn't working</span></span>

- <span data-ttu-id="68489-278">请参阅[安装工具](/windows/mixed-reality/install-the-tools)，了解建议用于开发HoloLens最新版本的 Unity。</span><span class="sxs-lookup"><span data-stu-id="68489-278">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="68489-279">Unity HoloLens Technical Preview 的已知问题记录在 HoloLens [Unity 论坛中](https://forum.unity3d.com/threads/known-issues.394627/)。</span><span class="sxs-lookup"><span data-stu-id="68489-279">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

[<span data-ttu-id="68489-280">返回列表</span><span class="sxs-lookup"><span data-stu-id="68489-280">Back to list</span></span>](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a><span data-ttu-id="68489-281">Windows设备门户无法正常工作</span><span class="sxs-lookup"><span data-stu-id="68489-281">Windows Device Portal isn't working correctly</span></span>

- <span data-ttu-id="68489-282">混合现实捕获中的实时预览功能可能会出现几秒钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="68489-282">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="68489-283">在"虚拟输入"页上，"虚拟手势"部分下的"手势"和"滚动"控件不起作用。</span><span class="sxs-lookup"><span data-stu-id="68489-283">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="68489-284">使用它们将不起作用。</span><span class="sxs-lookup"><span data-stu-id="68489-284">Using them will have no effect.</span></span> <span data-ttu-id="68489-285">虚拟输入页上的虚拟键盘正常工作。</span><span class="sxs-lookup"><span data-stu-id="68489-285">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="68489-286">在 设置 中启用开发人员模式后，可能需要几秒钟时间，开关才能打开设备门户模式。</span><span class="sxs-lookup"><span data-stu-id="68489-286">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

[<span data-ttu-id="68489-287">返回列表</span><span class="sxs-lookup"><span data-stu-id="68489-287">Back to list</span></span>](#list)

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="68489-288">HoloLens Emulator运行</span><span class="sxs-lookup"><span data-stu-id="68489-288">The HoloLens Emulator isn't working</span></span>

<span data-ttu-id="68489-289">有关 HoloLens 模拟器的信息，请参阅我们的开发人员文档。</span><span class="sxs-lookup"><span data-stu-id="68489-289">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="68489-290">详细了解如何[排查 HoloLens 模拟器。](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="68489-290">Read more about [troubleshooting the HoloLens emulator](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting).</span></span>


- <span data-ttu-id="68489-291">并非所有应用Microsoft Store模拟器兼容。</span><span class="sxs-lookup"><span data-stu-id="68489-291">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="68489-292">例如，Young Conker 和 Fragments 在仿真器上不可播放。</span><span class="sxs-lookup"><span data-stu-id="68489-292">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="68489-293">不能在设备中使用电脑网络Emulator。</span><span class="sxs-lookup"><span data-stu-id="68489-293">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="68489-294">Windows 设备门户的 Live Preview 功能不能与模拟器一起使用。</span><span class="sxs-lookup"><span data-stu-id="68489-294">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="68489-295">你仍然可以捕获混合现实视频和图像。</span><span class="sxs-lookup"><span data-stu-id="68489-295">You can still capture Mixed Reality videos and images.</span></span>

[<span data-ttu-id="68489-296">返回列表</span><span class="sxs-lookup"><span data-stu-id="68489-296">Back to list</span></span>](#list)

## <a name="voice-commands-arent-working"></a><span data-ttu-id="68489-297">语音命令无法工作</span><span class="sxs-lookup"><span data-stu-id="68489-297">Voice commands aren't working</span></span>

<span data-ttu-id="68489-298">如果Cortana未响应语音命令，请确保Cortana语音命令。</span><span class="sxs-lookup"><span data-stu-id="68489-298">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="68489-299">在"所有应用"列表中  >  **，Cortana"菜单**  >  **笔记本**  >  **设置** 进行更改。</span><span class="sxs-lookup"><span data-stu-id="68489-299">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="68489-300">若要详细了解可以说出的话，请参阅将语音与[HoloLens。](hololens-cortana.md)</span><span class="sxs-lookup"><span data-stu-id="68489-300">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

<span data-ttu-id="68489-301">在HoloLens (第一代) ，内置语音识别不可配置。</span><span class="sxs-lookup"><span data-stu-id="68489-301">On HoloLens (1st gen), built-in speech recognition is not configurable.</span></span> <span data-ttu-id="68489-302">它始终打开。</span><span class="sxs-lookup"><span data-stu-id="68489-302">It is always turned on.</span></span> <span data-ttu-id="68489-303">在HoloLens 2，可以选择在设备设置期间是否同时Cortana语音识别和语音。</span><span class="sxs-lookup"><span data-stu-id="68489-303">On HoloLens 2, you can choose whether to turn on both speech recognition and Cortana during device setup.</span></span>

<span data-ttu-id="68489-304">如果HoloLens 2语音未响应，请确保启用语音识别。</span><span class="sxs-lookup"><span data-stu-id="68489-304">If your HoloLens 2 is not responding to your voice, make sure Speech recognition is turned on.</span></span> <span data-ttu-id="68489-305">转到"**开始**  >  **设置**  >    >  **语音"并** 打开 **语音识别**。</span><span class="sxs-lookup"><span data-stu-id="68489-305">Go to **Start** > **Settings** > **Privacy** > **Speech** and turn on **Speech recognition**.</span></span>

[<span data-ttu-id="68489-306">返回列表</span><span class="sxs-lookup"><span data-stu-id="68489-306">Back to list</span></span>](#list)

## <a name="hand-input-isnt-working"></a><span data-ttu-id="68489-307">手动输入不工作</span><span class="sxs-lookup"><span data-stu-id="68489-307">Hand input isn't working</span></span>

<span data-ttu-id="68489-308">若要确保HoloLens看到手，需要将它们放在手势框架中。</span><span class="sxs-lookup"><span data-stu-id="68489-308">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="68489-309">混合现实主页提供反馈，让你了解何时跟踪手部。</span><span class="sxs-lookup"><span data-stu-id="68489-309">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="68489-310">不同版本的服务的反馈HoloLens：</span><span class="sxs-lookup"><span data-stu-id="68489-310">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="68489-311">在HoloLens (第一代) 上，凝视光标从点变为环</span><span class="sxs-lookup"><span data-stu-id="68489-311">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="68489-312">在HoloLens 2，当手靠近平板电脑时，会出现一个手指光标，当板离得远时，会出现手部射线</span><span class="sxs-lookup"><span data-stu-id="68489-312">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="68489-313">许多沉浸式应用遵循类似于混合现实主页的输入模式。</span><span class="sxs-lookup"><span data-stu-id="68489-313">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="68489-314">详细了解第一代和 HoloLens ([上的) HoloLens 2。](hololens1-basic-usage.md#use-hololens-with-your-hands) [](hololens2-basic-usage.md#the-hand-tracking-frame)</span><span class="sxs-lookup"><span data-stu-id="68489-314">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="68489-315">如果你正在戴眼镜，请注意，某些类型的手部手部跟踪不起作用。</span><span class="sxs-lookup"><span data-stu-id="68489-315">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="68489-316">一个常见示例是黑色保护套，它往往能吸收光线，并且不会由深度相机拾取。</span><span class="sxs-lookup"><span data-stu-id="68489-316">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="68489-317">如果你的工作涉及橡皮套，我们建议尝试较浅的颜色，如蓝色或灰色。</span><span class="sxs-lookup"><span data-stu-id="68489-317">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="68489-318">另一个示例是大包袋套，它往往遮盖手的形状。</span><span class="sxs-lookup"><span data-stu-id="68489-318">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="68489-319">我们建议使用尽可能适合窗体的外套，以获得最佳结果。</span><span class="sxs-lookup"><span data-stu-id="68489-319">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="68489-320">如果视器具有指纹或指纹，请使用设备中HoloLens的微fiber 清理设备来清理视器。</span><span class="sxs-lookup"><span data-stu-id="68489-320">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

[<span data-ttu-id="68489-321">返回列表</span><span class="sxs-lookup"><span data-stu-id="68489-321">Back to list</span></span>](#list)

## <a name="cant-connect-to-wi-fi"></a><span data-ttu-id="68489-322">无法连接到 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="68489-322">Can't connect to Wi-Fi</span></span>

<span data-ttu-id="68489-323">如果无法将客户端连接到网络，请尝试HoloLens一Wi-Fi操作：</span><span class="sxs-lookup"><span data-stu-id="68489-323">Here are some things to try if you can't connect your HoloLens to a Wi-Fi network:</span></span>

- <span data-ttu-id="68489-324">确保Wi-Fi打开。</span><span class="sxs-lookup"><span data-stu-id="68489-324">Make sure that Wi-Fi is turned on.</span></span> <span data-ttu-id="68489-325">若要检查，请使用"开始"手势，然后选择设置  >  **网络 &amp; Internet**  >  **Wi-Fi"。**</span><span class="sxs-lookup"><span data-stu-id="68489-325">To check, use the Start gesture, then select **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span> <span data-ttu-id="68489-326">如果Wi-Fi，请尝试将其关闭，然后再次打开。</span><span class="sxs-lookup"><span data-stu-id="68489-326">If Wi-Fi is on, try turning it off and then on again.</span></span>
- <span data-ttu-id="68489-327">移动以靠近路由器或接入点。</span><span class="sxs-lookup"><span data-stu-id="68489-327">Move closer to the router or access point.</span></span>
- <span data-ttu-id="68489-328">重启Wi-Fi路由器，[然后重启HoloLens。](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="68489-328">Restart your Wi-Fi router, then [restart HoloLens](hololens-recovery.md).</span></span> <span data-ttu-id="68489-329">请再次尝试连接。</span><span class="sxs-lookup"><span data-stu-id="68489-329">Try connecting again.</span></span>
- <span data-ttu-id="68489-330">如果上述操作均不起作用，请检查以确保路由器使用的是最新的固件。</span><span class="sxs-lookup"><span data-stu-id="68489-330">If none of these things work, check to make sure that your router is using the latest firmware.</span></span> <span data-ttu-id="68489-331">可以在制造商网站上找到此信息。</span><span class="sxs-lookup"><span data-stu-id="68489-331">You can find this information on the manufacturer website.</span></span>

[<span data-ttu-id="68489-332">返回列表</span><span class="sxs-lookup"><span data-stu-id="68489-332">Back to list</span></span>](#list)

## <a name="bluetooth-devices-arent-pairing"></a><span data-ttu-id="68489-333">蓝牙设备未配对</span><span class="sxs-lookup"><span data-stu-id="68489-333">Bluetooth devices aren't pairing</span></span>

<span data-ttu-id="68489-334">如果在与设备配对蓝牙[时遇到问题，](hololens-connect-devices.md)请尝试以下操作：</span><span class="sxs-lookup"><span data-stu-id="68489-334">If you're having problems [pairing a Bluetooth device](hololens-connect-devices.md), try the following:</span></span>

- <span data-ttu-id="68489-335">转到  >  **设置""** 设备"，并确保蓝牙设备" 。</span><span class="sxs-lookup"><span data-stu-id="68489-335">Go to **Settings** > **Devices**, and make sure that Bluetooth is turned on.</span></span> <span data-ttu-id="68489-336">如果是，请将其关闭并再次打开。</span><span class="sxs-lookup"><span data-stu-id="68489-336">If it is, turn it off and on again.</span></span>
- <span data-ttu-id="68489-337">请确保设备已蓝牙或具有新电池。</span><span class="sxs-lookup"><span data-stu-id="68489-337">Make sure that your Bluetooth device is fully charged or has fresh batteries.</span></span>
- <span data-ttu-id="68489-338">如果仍然无法连接，请[重启HoloLens。](hololens-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="68489-338">If you still can't connect, [restart the HoloLens](hololens-recovery.md).</span></span>

[<span data-ttu-id="68489-339">返回列表</span><span class="sxs-lookup"><span data-stu-id="68489-339">Back to list</span></span>](#list)

## <a name="usb-c-microphone-isnt-working"></a><span data-ttu-id="68489-340">USB-C 麦克风不工作</span><span class="sxs-lookup"><span data-stu-id="68489-340">USB-C Microphone isn't working</span></span>
<span data-ttu-id="68489-341">请注意，某些 USB-C 麦克风错误地将自身报告为 *麦克风和扬声器* 。</span><span class="sxs-lookup"><span data-stu-id="68489-341">Be aware that some USB-C microphones incorrectly report themselves as both a microphone *and* a speaker.</span></span> <span data-ttu-id="68489-342">这是麦克风的问题，而不是麦克风HoloLens。</span><span class="sxs-lookup"><span data-stu-id="68489-342">This is a problem with the microphone and not with HoloLens.</span></span> <span data-ttu-id="68489-343">将其中一个麦克风插入 HoloLens时，可能会丢失声音。</span><span class="sxs-lookup"><span data-stu-id="68489-343">When plugging one of these microphones into HoloLens, sound may be lost.</span></span> <span data-ttu-id="68489-344">幸运的是，有一个简单的修复方法。</span><span class="sxs-lookup"><span data-stu-id="68489-344">Fortunately there is a simple fix.</span></span>  

<span data-ttu-id="68489-345">在 **设置** System Sound 中，将"模拟功能音频驱动程序" (将内置扬声器) 设置为  ->    ->  **"默认设备"。**</span><span class="sxs-lookup"><span data-stu-id="68489-345">In **Settings** -> **System** -> **Sound**, explicitly set the built-in speakers **(Analog Feature Audio Driver)** as the **Default device**.</span></span> <span data-ttu-id="68489-346">HoloLens应记住此设置，即使稍后删除了麦克风并重新连接。</span><span class="sxs-lookup"><span data-stu-id="68489-346">HoloLens should remember this setting even if the microphone is removed and reconnected later.</span></span>

![USB-C 麦克风疑难解答](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a><span data-ttu-id="68489-348">在 设置 中列为可用的设备不起作用</span><span class="sxs-lookup"><span data-stu-id="68489-348">Devices listed as available in Settings don't work</span></span>

<span data-ttu-id="68489-349">HoloLens (第一代) 不支持蓝牙配置文件。</span><span class="sxs-lookup"><span data-stu-id="68489-349">HoloLens (1st gen) doesn't support Bluetooth audio profiles.</span></span> <span data-ttu-id="68489-350">蓝牙音频设备（如扬声器和头戴显示设备）在HoloLens中显示为可用，但不受支持。</span><span class="sxs-lookup"><span data-stu-id="68489-350">Bluetooth audio devices, such as speakers and headsets, may appear as available in HoloLens settings, but they aren't supported.</span></span>

<span data-ttu-id="68489-351">HoloLens 2支持蓝牙立体声播放的 A2DP 音频配置文件。</span><span class="sxs-lookup"><span data-stu-id="68489-351">HoloLens 2 supports the Bluetooth A2DP audio profile for stereo playback.</span></span> <span data-ttu-id="68489-352">支持蓝牙麦克风捕获的无手配置文件蓝牙设备不支持从外设捕获HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="68489-352">The Bluetooth Hands Free profile which enables microphone capture from a Bluetooth peripheral is not supported on HoloLens 2.</span></span>

<span data-ttu-id="68489-353">如果在使用设备时遇到蓝牙，请确保它是受支持的设备。</span><span class="sxs-lookup"><span data-stu-id="68489-353">If you're having trouble using a Bluetooth device, make sure that it's a supported device.</span></span> <span data-ttu-id="68489-354">支持的设备包括：</span><span class="sxs-lookup"><span data-stu-id="68489-354">Supported devices include the following:</span></span>

- <span data-ttu-id="68489-355">英语 QWERTY 蓝牙键盘 (，可以在使用全息键盘键盘或键盘的任何位置) 。</span><span class="sxs-lookup"><span data-stu-id="68489-355">English-language QWERTY Bluetooth keyboards (you can use these anywhere that you use the holographic keyboard).</span></span>
- <span data-ttu-id="68489-356">蓝牙鼠标。</span><span class="sxs-lookup"><span data-stu-id="68489-356">Bluetooth mice.</span></span>
- <span data-ttu-id="68489-357">单击[HoloLens单击器](hololens1-clicker.md)。</span><span class="sxs-lookup"><span data-stu-id="68489-357">The [HoloLens clicker](hololens1-clicker.md).</span></span>

<span data-ttu-id="68489-358">可以将其他 HID 蓝牙 GATT 设备与设备配对HoloLens。</span><span class="sxs-lookup"><span data-stu-id="68489-358">You can pair other Bluetooth HID and GATT devices together with your HoloLens.</span></span> <span data-ttu-id="68489-359">但是，可能需要从客户端安装相应的Microsoft Store应用，以实际使用设备。</span><span class="sxs-lookup"><span data-stu-id="68489-359">However, you may have to install corresponding companion apps from Microsoft Store to actually use the devices.</span></span>

[<span data-ttu-id="68489-360">返回列表</span><span class="sxs-lookup"><span data-stu-id="68489-360">Back to list</span></span>](#list)
