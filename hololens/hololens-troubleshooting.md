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
# <a name="device-troubleshooting"></a>设备故障排除

本文介绍如何解决几个常见的 HoloLens 问题。

>[!IMPORTANT]
> 在开始任何故障排除过程之前，请确保设备按 **电池容量的 20% 到 40%** 收费（如果可能）。 位于 [电源](hololens2-setup.md#lights-that-indicate-the-battery-level) 按钮下的电池指示灯是验证电池容量的一种快速方法，无需登录到设备。

<a id="list"></a>

**已知问题**
- [Remote Assist视频在 20 分钟后冻结](#remote-assist-video-freezes-after-20-minutes)
- [自动登录要求登录](#auto-login-asks-for-log-in)
- [Microsoft Edge启动失败](#microsoft-edge-fails-to-launch)
- [键盘不切换到特殊字符](#keyboard-doesnt-switch-to-special-characters)
- [下载锁定的文件不会显示错误](#downloading-locked-files-doesnt-error)
- [设备门户文件上传/下载时间已过](#device-portal-file-uploaddownload-times-out)
- [从预览体验成员预览版取消注册后，在设备上以预览体验成员版本刷出蓝屏](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive 不会自动上传图片](#onedrive-doesnt-automatically-upload-pictures)

**常规**
- [HoloLens 无响应或无法启动](#hololens-is-unresponsive-or-wont-start)
- ["磁盘空间不足"错误](#low-disk-space-error)
- [校准失败](#calibration-fails)
- [无法登录，因为之前为其他人设置了 HoloLens](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity 不工作](#unity-isnt-working)
- [Windows 设备门户无法正常工作](#windows-device-portal-isnt-working-correctly)
- [HoloLens 仿真器不工作](#the-hololens-emulator-isnt-working)

**输入**
- [语音命令无法工作](#voice-commands-arent-working)
- [手动输入不工作](#hand-input-isnt-working)

**连接**
- [无法连接到 Wi-Fi](#cant-connect-to-wi-fi)

**外部设备** 
- [蓝牙设备未配对](#bluetooth-devices-arent-pairing)
- [USB-C 麦克风不工作](#usb-c-microphone-isnt-working)
- [在"设置"中列为可用的设备不起作用](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist视频在 20 分钟后冻结

> [!NOTE]
> 由于此已知问题的严重性，我们当前暂停了 Windows Holographic 版本 21H1 的可用性。 如果仍希望将设备更新到 21H1，请参阅页面顶部的发行说明 [中的说明。](hololens-release-notes.md)

在最新版本的 Windows Holographic 版本 [21H1](hololens-release-notes.md#windows-holographic-version-21h1)中，Remote Assist用户在通话期间遇到视频冻结。 这是一个 **已知问题**。

### <a name="workarounds"></a>解决方法

#### <a name="restart-in-between-calls"></a>在调用之间重启

如果通话时长超过 20 分钟，并且遇到此问题，请尝试重启设备。 在两次Remote Assist重启设备会刷新设备，并恢复为良好状态。

若要在 [Windows Holographic（版本 21H1）](hololens-release-notes.md#windows-holographic-version-21h1)上快速重启设备，请打开"开始"菜单，选择用户图标，然后选择"重启 **"。**

#### <a name="revert-to-an-older-build"></a>还原到较旧的生成

一些客户发现，还原到较早的 OS 版本时，他们不再遇到此问题。 如果发现设备遇到此问题，请尝试以下步骤：


解决方法：

- 如果你的业务可行，则使用者 Microsoft 帐户支持自动上传相机。 除了工作或学校帐户Microsoft 帐户 OneDrive 应用支持双重登录帐户 (还可以登录到) 。 在 OneDrive Microsoft 帐户配置文件中，可以启用自动后台相机滚动上传。

- 如果无法安全地使用使用者Microsoft 帐户自动上传照片，可以从 OneDrive 应用手动将照片上传到工作或学校帐户。 为此，请确保已登录到 OneDrive 应用中的工作或学校帐户。 选择按钮 **+** ，然后选择"上传 **"。** 通过导航到"照片"和"相机滚动> **上传的照片或视频**。 选择要上传的一个或多个照片或视频，然后选择"打开 **"** 按钮。


1. [下载适用于 Windows Holographic 版本 20H2 - 2021 年 5 月更新的版本](https://aka.ms/hololens2download/10.0.19041.1146)
1. 按照 [说明返回到以前的 OS 版本](hololens-update-hololens.md#go-back-to-a-previous-version)
1. 手动 [暂停设备上 OS 更新，](hololens-updates.md#pause-updates-via-device) 或者对于许多设备，通过 [MDM 使用延迟](hololens-updates.md#configure-an-update-deferral-policy)。

[返回列表](#list)

## <a name="auto-login-asks-for-log-in"></a>自动登录要求登录

可以将HoloLens 2配置为通过"设置帐户登录选项"->在"必需"下将值  ->    ->  设置为"从不"自动 **登录**。  更新具有较大更新（如功能更新）的设备时，某些用户可能需要再次登录到设备。 这是一个 **已知问题**。

发生这种情况的示例：

- 将设备从 Windows Holographic 版本 2004 (内部版本 19041.xxxx) 更新到 Windows Holographic 版本 21H1 (内部版本 20346.xxxx) 
- 更新设备以在同一主要版本（例如 Windows Holographic 版本 2004 到 Windows Holographic 版本 20H2）上进行大型更新
- 将设备从工厂映像更新到最新映像

这不应发生在：

- 进行每月服务更新的设备

解决方法：

- 登录方法，例如 PIN、密码、Iris、Web 身份验证或 FIDO2 密钥。
- 如果无法记住设备 PIN，并且其他身份验证方法不可用，则用户可以使用手动 [重新转换模式](hololens-recovery.md#manual-procedure)。

[返回列表](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge启动失败

> [!NOTE]
> 此问题最初是使用产品/Microsoft Edge创建的。 此问题可以在新的 中[Microsoft Edge。](hololens-new-edge.md) 如果不是，请提交反馈。

一些客户报告了无法启动Microsoft Edge的问题。 对于这些客户，此问题通过重新启动而仍然存在，不会通过 Windows 或应用程序更新解决。 如果遇到此问题，并且已确认 [Windows](hololens-updates.md#manually-check-for-updates)是最新的，请从 [反馈中心](hololens-feedback.md) 应用提交以下类别和子类别的 bug：安装和更新 > 下载、安装和配置 Windows 更新。

目前没有已知的解决方法，因为我们目前无法找出问题的根本原因。 通过 反馈中心 bug 将有助于调查！ 这是一个 **已知问题**。

[返回列表](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>键盘不切换到特殊字符

OOBE 期间存在一个问题，即用户选择工作或学校帐户并输入其密码后，尝试通过点击 &123 按钮切换到键盘上的特殊字符不会更改为特殊字符。 这是一个 **已知问题**。

周全方案：
-   关闭键盘，然后通过点击文本字段重新打开它。
-   错误地输入密码。 下次重新启动键盘时，它将如预期工作。
- Web 身份验证，关闭键盘并选择 **"从另一台设备登录"。**
-   如果仅输入数字，用户可以按住某些键打开展开的菜单。
-   使用 USB 键盘。

这不会影响：
- 选择使用个人帐户的用户。

[返回列表](#list)


## <a name="downloading-locked-files-doesnt-error"></a>下载锁定的文件不会出错
> !注意 这是在 **内部版本** 20348.1403 Windows 预览体验成员修复的已知问题。


在 Windows Holographic 的早期版本中，尝试下载锁定文件时，结果将是 HTTP 错误页。 在 Windows Holographic 版本 21H1 更新中，尝试下载锁定的文件会导致未发生任何可见的情况-文件不会下载，并且没有错误。 

[返回列表](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>设备门户文件上传/下载时间已过
> !注意 这是在 **内部版本** 20348.1403 Windows 预览体验成员修复的已知问题。 如果以前已禁用 SSL 连接作为解决方法的一部分，强烈建议重新启用它。


一些客户发现，在尝试上传或下载文件时，操作可能显示为挂起，然后会退出或永不完成。 这独立于"[文件](#downloading-locked-files-doesnt-error) 锁定"已知问题 - 这会影响 Windows Holographic 版本 2004、20H2 和 21H1 市场内版本。 此问题的根本原因是，设备门户处理某些请求时出现 bug，并且使用 https 时最一致，这是默认设置。 

### <a name="workaround"></a>解决方法

此解决方法同样适用于 Wi-Fi UsbNcm，即禁用"SSL 连接"下的"必需"选项。 为此，请导航到 **设备门户"系统**"，然后选择" **首选项"** 页。 在"**设备安全性"** 部分中，找到 **"SSL 连接"，** 取消选中以禁用"**必需"。**

然后，用户应转到 http://，https:// (IP 地址) 文件上传和下载等功能将正常工作。

[返回列表](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>从预览体验成员预览版取消注册后，在设备上以预览体验成员版本刷出蓝屏

此问题会影响使用 Insider 预览版的用户，使用新的预览体验内部版本重新HoloLens 2预览体验版，然后从预览体验计划取消注册。 这是一个 **已知问题**。

这不会影响：
- 未在 Windows 预览体验成员 
- 业内 人士：
    - 如果设备自预览体验内部版本为版本 18362.x 以来已注册
    - 如果他们刷过预览体验成员签名的 19041.x 内部版本，并一直注册到 Insider 计划

工作之一： 
- 避免此问题 
    - 刷用非预览体验内部版本。 每月定期更新之一。
    - 随时了解预览体验成员
- 重新运行设备

    1. 在 [HoloLens 2](hololens-recovery.md) 完全关闭电源，手动将设备置于闪烁模式。 然后，在按住"音量"的同时，点击"电源"按钮。
    
    1. 连接到电脑并打开"高级恢复助手"。
    
    1. 将HoloLens 2刷新为默认生成。

[返回列表](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive 不会自动上传图片

适用于 HoloLens 的 OneDrive 应用不支持为工作或学校帐户自动上传相机。 这是一个 **已知问题**。

解决方法：

- 如果你的业务可行，则使用者 Microsoft 帐户支持自动上传相机。 除了工作或学校帐户Microsoft 帐户 OneDrive 应用支持双重登录帐户 (还可以登录到) 。 在 OneDrive Microsoft 帐户配置文件中，可以启用自动后台相机滚动上传。

- 如果无法安全地使用使用者Microsoft 帐户自动上传照片，可以从 OneDrive 应用手动将照片上传到工作或学校帐户。 为此，请确保已登录到 OneDrive 应用中的工作或学校帐户。 选择按钮 **+** ，然后选择"上传 **"。** 通过导航到"照片"和"相机滚动> **上传的照片或视频**。 选择要上传的一个或多个照片或视频，然后选择"打开 **"** 按钮。

[返回列表](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens 无响应或无法启动

如果 HoloLens 无法启动：

- 如果电源按钮旁边的 LED 不亮起，或只有一个 LED 短暂闪烁，可能需要为 [HoloLens 收费。](hololens2-charging.md#charging-the-device)
- 如果 LED 在按下电源按钮时亮起，但在显示器上看不到任何内容，请对设备 进行 [硬重置](hololens-recovery.md#hard-reset-procedure)。

如果 HoloLens 冻结或无响应：

- 按电源按钮关闭 HoloLens，直到所有五个 LED 都自行关闭，如果 LED 无响应，则关闭 15 秒。 若要启动 HoloLens，请再次按电源按钮。

如果这些步骤不起作用，可以尝试恢复 HoloLens 2 或[](hololens-recovery.md) [HoloLens (第一代) 设备。](hololens1-recovery.md)

[返回列表](#list)

## <a name="low-disk-space-error"></a>"磁盘空间不足"错误

需要执行以下操作一个或多个来释放一些存储空间：

- 删除一些未使用的空格。 转到"**设置**  >  **系统**  >  **空间**"，选择不再需要的空间，然后选择"删除 **"。**
- 删除放置的一些全息影像。
- 从照片应用中删除一些图片和视频。
- 从 HoloLens 卸载某些应用。 在"**所有应用"** 列表中，点击并按住要卸载的应用，然后选择"卸载 **"。**

[返回列表](#list)

## <a name="calibration-fails"></a>校准失败

校准应该适用于大多数人员，但在某些情况下，校准会失败。
  
校准失败的一些潜在原因包括：

- 分散注意力，不遵循校准目标
- 脏设备或暂存的设备视板或设备视板未正确定位
- 脏眼镜或暂存的眼镜
- 某些类型的接触镜和眼镜 (彩色接触片、一些圆环接触镜、IR 阻塞眼镜、一些高光眼镜、眼镜或类似) 
- 更明显的发音和一些眼线扩展
- 如果头框或粗眼镜框阻止设备看到眼睛
- 某些眼部眼部、眼部状况或眼部障碍，例如窄眼睛、长眼线、amblyopia、nystagmus、一些 LASIK 或其他眼部疾病

如果校准失败，请尝试：

- 清理设备视区
- 清理眼镜
- 将设备视器推送到尽可能靠近眼睛
- 将视器中的对象移开 (如发) 
- 在房间中打开灯或离开直接光线

如果遵循所有准则并且校准仍然失败，可以在"设置"中禁用校准提示。 此外，请通过向 提交反馈来[反馈中心。](hololens-feedback.md)

另请参阅图像颜色 [或亮度故障排除的相关信息。](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

设置 IPD 不适用于HoloLens 2，因为眼睛位置由系统计算。 

[返回列表](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>无法登录，因为之前为其他人设置了 HoloLens

可以将 [设备置于 **刷用模式，** 并使用高级恢复](hololens-recovery.md#clean-reflash-the-device) 助手来恢复设备。

[返回列表](#list)


## <a name="unity-isnt-working"></a>Unity 不工作

- 有关 [用于](/windows/mixed-reality/install-the-tools) HoloLens 开发的建议最新版本的 Unity，请参阅安装工具。
- [HoloLens Unity](https://forum.unity3d.com/threads/known-issues.394627/)论坛中记录了 Unity HoloLens Technical Preview 的已知问题。

[返回列表](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows 设备门户无法正常工作

- 混合现实捕获中的实时预览功能可能会出现几秒钟的延迟。

- 在"虚拟输入"页上，"虚拟手势"部分下的"手势"和"滚动"控件不起作用。 使用它们将不起作用。 虚拟输入页上的虚拟键盘正常工作。

- 在"设置"中启用"开发人员模式"后，可能需要几秒钟时间，开关才能设备门户打开。

[返回列表](#list)

## <a name="emulator"></a>仿真器
### <a name="the-hololens-emulator-isnt-working"></a>HoloLens 模拟器不工作

有关 HoloLens 模拟器的信息位于我们的开发人员文档中。  阅读有关 [排查 HoloLens 模拟器问题的](/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)详细信息。


- 并非 Microsoft Store 中的所有应用都与模拟器兼容。 例如，不能在模拟器上播放年轻人 Conker 和片段。
- 无法在仿真程序中使用 PC 网络摄像机。
- Windows 设备门户的实时预览功能不适用于模拟器。 你仍可以捕获混合现实视频和图像。

[返回到列表](#list)

## <a name="i-cannot-find-or-use-the-keyboard-to-type-in-the-hololens-2-emulator"></a>我找不到或无法使用键盘键入 HoloLens 2 模拟器

*即将推出*

[返回到列表](#list)

## <a name="voice-commands-arent-working"></a>语音命令不起作用

如果 Cortana 没有响应语音命令，请确保 Cortana 已打开。 在 "所有应用" 列表中，选择 " **Cortana**  >  **Menu**  >  **笔记本**  >  **设置**" 进行更改。 若要详细了解你可以说的内容，请参阅 [将你的语音与 HoloLens 配合使用](hololens-cortana.md)。

在 HoloLens (第一代) 上，内置语音识别不可配置。 始终打开。 在 HoloLens 2 上，你可以选择是否在设备设置期间打开语音识别和 Cortana。

如果 HoloLens 2 未响应语音，请确保已启用语音识别。 转到 "**开始**  >  **设置**  >  " "**隐私**  >  **语音**" 并打开 **语音识别**。

[返回到列表](#list)

## <a name="hand-input-isnt-working"></a>手写输入不起作用

若要确保 HoloLens 能看到你的手，你需要将它们保留在手势帧中。  混合现实主页提供反馈，让你知道何时跟踪你的手。  不同版本的 HoloLens 的反馈有所不同：
- 在 HoloLens (第一代) 上，注视光标从点变为圆圈
- 在 HoloLens 2 上，当您的手接近于一手指时，会出现一个 "

许多沉浸式应用都遵循类似于混合现实主页的输入模式。  详细了解如何在 [hololens (第一代) ](hololens1-basic-usage.md#use-hololens-with-your-hands) 和 [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)上使用手动输入。

如果戴上手套，请注意，某些类型的手套不适用于手动跟踪。  常见的例子是黑色橡胶手套，这通常会吸收红外线，而不是由深度相机选取。  如果你的工作涉及橡胶手套，我们建议尝试使用较浅的颜色，如蓝色或灰色。  另一个示例是大型 baggy 手套，这种情况通常会使手不会遮盖。 为了获得最佳效果，我们建议使用以窗体为形式的手套。

如果面板具有指纹或无污迹，请使用 HoloLens 附带的 microfiber 清洁抹布来轻轻地清理面板。

[返回到列表](#list)

## <a name="cant-connect-to-wi-fi"></a>无法连接到 Wi-Fi

如果无法将 HoloLens 连接到 Wi-Fi 网络，请尝试以下操作：

- 请确保已打开 Wi-Fi。 若要检查，请使用 "开始手势"，然后选择 "**设置**" "  >  **网络 &amp; Internet**  >  **wi-fi**"。 如果 Wi-Fi 处于打开状态，请尝试将其关闭，然后重新打开。
- 移动以靠近路由器或接入点。
- 重新启动 Wi-Fi 路由器，然后 [重新启动 HoloLens](hololens-recovery.md)。 请再次尝试连接。
- 如果这些操作都不起作用，请检查以确保路由器使用的是最新的固件。 你可以在制造商网站上找到此信息。

[返回到列表](#list)
## <a name="bluetooth-devices-arent-pairing"></a>蓝牙设备不配对

如果在 [配对蓝牙设备](hololens-connect-devices.md)时遇到问题，请尝试以下操作：

- 转到 "**设置**  >  " "**设备**"，并确保已启用 "蓝牙"。 如果是，请将其关闭，然后重新打开。
- 请确保蓝牙设备已完全充电，或具有新电池。
- 如果仍然无法连接，请 [重新启动 HoloLens](hololens-recovery.md)。

[返回到列表](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C 麦克风不工作
请注意，某些 USB-C 麦克风会错误地将自身报告为麦克风 *和* 扬声器。 这是麦克风问题，而不是使用 HoloLens。 将其中一个麦克风插入 HoloLens 时，可能会丢失声音。 幸运的是，有一个简单的修补程序。  

在 "**设置**  ->  **系统**  ->  **声音**" 中，显式设置内置扬声器 **(模拟功能音频驱动程序)** 作为 **默认设备**。 即使删除了麦克风并稍后重新连接，HoloLens 也应记住此设置。

![USB-C 麦克风疑难解答](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>在设置中列为可用的设备不起作用

HoloLens (第一代) 不支持蓝牙音频配置文件。 蓝牙音频设备（如扬声器和耳机）在 HoloLens 设置中可能显示为可用，但不受支持。

HoloLens 2 支持用于立体声播放的蓝牙 A2DP 音频配置文件。 HoloLens 2 上不支持通过蓝牙外设启用麦克风捕获的蓝牙免提配置文件。

如果使用 Bluetooth 设备时遇到问题，请确保它是受支持的设备。 支持的设备包括：

- 使用英语语言的蓝牙键盘 (可以在任何使用全息键盘) 的地方使用。
- 蓝牙鼠标。
- [HoloLens clicker](hololens1-clicker.md)。

可以将其他蓝牙 HID 和 GATT 设备与 HoloLens 配对。 但是，你可能需要从 Microsoft Store 安装相应的随附应用才能实际使用设备。

[返回到列表](#list)
