---
title: HoloLens设备故障排除
description: 随时了解最常见的解决方案，HoloLens和故障排除技术。
author: evmill
ms.author: v-evmill
ms.date: 10/13/2021
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: ranjibb
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 问题， bug， 故障排除， 修复， 帮助， 支持， HoloLens， 模拟器
ms.openlocfilehash: deed0d14b2567ae0a1fb2cde8ad1fbe3dbb20bb3
ms.sourcegitcommit: 73a1555fb8b84f3d20c480282c648d8d800a6c98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2021
ms.locfileid: "130351759"
---
# <a name="device-troubleshooting"></a>设备故障排除

本文介绍如何解决几个常见的HoloLens问题。

>[!IMPORTANT]
> 在开始任何故障排除过程之前，请确保将设备充电至电池容量的 20 % 至 40%（如可能）。 通过位于电源按钮下的[电池指示灯](hololens2-setup.md#lights-that-indicate-the-battery-level)可以快速验证电池容量（无需登录到设备）。

<a id="list"></a>

**已知问题**
- [内部修复 - 每次电源达到 18% 时，设备都会突然自动关闭](#every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically)
- [OneDriveUWP 应用不适用于Azure AD用户](#onedrive-uwp-app-doesnt-work-for-azure-ad-users)
- [为什么在 Autopilot 中看到 0x80180014？](#why-do-i-see-0x80180014-during-autopilot)
- [Microsoft Store错误代码0x80131500](#microsoft-store-error-code-0x80131500)
- [Microsoft Edge无法启动麦克风](#microsoft-edge-fails-to-start-the-microphone)
- [**已** 修复 - Remote Assist 20 分钟后视频冻结](#remote-assist-video-freezes-after-20-minutes)
- [自动登录要求登录](#auto-login-asks-for-log-in)
- [Microsoft Edge启动失败](#microsoft-edge-fails-to-launch)
- [键盘不切换到特殊字符](#keyboard-doesnt-switch-to-special-characters)
- [**已** 修复 - 下载锁定的文件不会显示错误](#downloading-locked-files-doesnt-error)
- [**已** 修复 - 设备门户文件上传/下载时间过长](#device-portal-file-uploaddownload-times-out)
- [从预览体验成员预览版取消注册后，在设备上以预览体验成员版本刷出蓝屏](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive不会自动上传图片](#onedrive-doesnt-automatically-upload-pictures)

**常规**
- [HoloLens无响应或无法启动](#hololens-is-unresponsive-or-wont-start)
- ["磁盘空间不足"错误](#low-disk-space-error)
- [校准失败](#calibration-fails)
- [无法登录，因为之前为HoloLens设置了我的帐户](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity 不工作](#unity-isnt-working)
- [Windows设备门户无法正常工作](#windows-device-portal-isnt-working-correctly)
- [HoloLens Emulator运行](#the-hololens-emulator-isnt-working)

**输入**
- [语音命令无法工作](#voice-commands-arent-working)
- [手动输入不工作](#hand-input-isnt-working)

**连接**
- [无法连接到 Wi-Fi](#cant-connect-to-wi-fi)

**外部设备** 
- [蓝牙设备未配对](#bluetooth-devices-arent-pairing)
- [USB-C 麦克风不工作](#usb-c-microphone-isnt-working)
- [在 设置中列为可用的设备不起作用](#devices-listed-as-available-in-settings-dont-work)

## <a name="every-time-the-power-goes-to-18-percent-the-device-suddenly-shuts-down-automatically"></a>每次电源达到 18% 时，设备就会突然自动关闭

> [!NOTE]
> 预览体验成员中提供了此问题[Windows修复。](hololens-insider.md)

存在一个已知问题：当设备达到 18% 的电池电量时，它会意外关闭。 这是一个软件问题，而不是硬件或电池问题，因此请不要为此交换设备。 如果不确定问题是否与此 bug 匹配，请：

1. 确保在设备上启用可选诊断 () 
1. 重现问题
1. 提交 [反馈中心](hololens-feedback.md) 问题
1. 共享反馈问题 URL
1. [联系支持人员](https://aka.ms/hololenssupport)

[返回到列表](#list)

## <a name="onedrive-uwp-app-doesnt-work-for-azure-ad-users"></a>OneDriveUWP 应用不适用于Azure AD用户

如果使用 Azure AD 帐户使用 OneDrive For Business，则登录到收件箱应用时OneDrive错误。 无法登录到 OneDrive不会影响相机应用捕获的图像和视频的自动上传。 仍可从云存储中保存和访问OneDrive for Business文件。 OneDrive团队HoloLens团队正在解决此问题。

### <a name="workarounds"></a>解决方法

先决条件：客户可以使用 Microsoft Edge且设备 OS 已更新到 Windows Holographic、21H1 内部版本或更高版本。

如果遇到此问题，请尝试以下方法之一：

- 用户可以从 OneDrive 直接访问 Microsoft Edge For Business，并可以从浏览器与其文件进行交互。
- 用户可以通过从OneDrive PWA下载HoloLens应用来安装Microsoft Edge。 这将允许用户再次查看和管理设备上的文件。 阅读并按照[这些说明在OneDrive PWA应用HoloLens。](holographic-store-apps.md#install-microsoft-onedrive-pwa-app)

[返回到列表](#list)

## <a name="why-do-i-see-0x80180014-during-autopilot"></a>为什么在 Autopilot 中看到 0x80180014？

在设备重置和重新使用流期间，通常会HoloLens设备至少通过 Autopilot 一次。 若要解决此问题，请从设备中删除设备[](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode)Microsoft Intune重置它以完成 Autopilot 流。

有关详细信息，请参阅 [autopilot 页上的故障排除步骤。](hololens2-autopilot.md#issue---mdm-enrollment-fails-with-error-0x80180014-error-code-during-autopilot)

## <a name="microsoft-store-error-code-0x80131500"></a>Microsoft Store错误代码0x80131500

某些用户可能会遇到Microsoft Store运行错误，并看到错误代码0x80131500。 此问题是由上设置的区域HoloLens在 HoloLens 上的 Microsoft Store 应用HoloLens。 如果遇到错误代码0x80131500，若要解决此问题，请：

1. 将设置 >"&语言>区域>"设置为以下项之一：
    - 美国、日本、中国、德国、加拿大、英国、爱尔兰、法国、澳大利亚、新西兰。
1. 重启 Store 应用。
1. 若要使整个设备反映更改，需要重启设备。

HoloLens团队正在努力为更多区域添加支持。

请参阅此处[，了解国家/地区HoloLens 2。](hololens2-purchase.md)

## <a name="microsoft-edge-fails-to-start-the-microphone"></a>Microsoft Edge无法启动麦克风

当用户使用 Microsoft Edge麦克风可能无法启动，因此无法与 HoloLens 中的 Edge 交互。 此已知问题与 Microsoft Edge 版本相关，请不要将设备重新升级为早期版本，因为这样做无法解决此问题。

### <a name="who-is-affected"></a>Who受到影响？

具有版本 93 Microsoft Edge 94 或 95 的用户。
可以使用 Microsoft Store 应用检查Microsoft Edge版本，然后选择由 表示的"查看更多"按钮 **，** 然后选择"下载和更新 **"。**

### <a name="work-around"></a>变通方法

当前修补程序在版本 96 中，该版本可供已注册预览体验成员Microsoft Edge用户使用。 这不同于将设备注册为预览Windows预览体验计划。 阅读这些说明， [详细了解如何注册 Edge 的预览体验计划。](hololens-new-edge.md#microsoft-edge-insider-channels)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>Remote Assist视频在 20 分钟后冻结

> [!NOTE]
> 有较新版本的 Remote Assist修复了此问题。 请将 [Remote Assist](holographic-store-apps.md#update-apps) 更新到最新版本，以避免此问题。

> [!NOTE]
> 由于此已知问题的严重性，我们暂时暂停了 Holographic 版本 21H1 Windows可用性。 21H1 版本现已再次可用，因此设备可能会再次更新到最新的 21H1 内部版本。

在[Holographic Windows版本 21H1](hololens-release-notes.md#windows-holographic-version-21h1)的最新版本中，Remote Assist用户在通话期间遇到视频冻结超过 20 分钟。 这是一个 **已知问题**。

### <a name="workarounds"></a>解决方法

如果无法将更新Remote Assist更新版本，请尝试以下方法。

#### <a name="restart-in-between-calls"></a>在调用之间重启

如果通话时长超过 20 分钟，并且遇到此问题，请尝试重启设备。 在两次Remote Assist重启设备会刷新设备，并恢复为良好状态。

若要快速重启 [Holographic Windows版本 21H1](hololens-release-notes.md#windows-holographic-version-21h1)上的设备，请打开"开始"菜单，选择用户图标，然后选择"重启 **"。**

[返回到列表](#list)

## <a name="auto-login-asks-for-log-in"></a>自动登录要求登录

可以将HoloLens 2配置为通过 设置 帐户登录选项 -> 在"必需"下将值设置为"从不  ->    ->  "自动 **登录**。  更新具有较大更新（如功能更新）的设备时，某些用户可能需要再次登录到设备。 这是一个 **已知问题**。

发生这种情况的示例：

- 将设备从 Windows Holographic 版本 2004 (内部版本 19041.xxxx) 更新到 Windows Holographic 版本 21H1 (内部版本 20346.xxxx) 
- 更新设备以在同一主要版本（例如，Windows Holographic 版本 2004 到 Windows Holographic 版本 20H2）上进行大型更新
- 将设备从工厂映像更新到最新映像

这不应发生在：

- 进行每月服务更新的设备

解决方法：

- 登录方法，例如 PIN、密码、Iris、Web 身份验证或 FIDO2 密钥。
- 如果无法记住设备 PIN，并且其他身份验证方法不可用，则用户可以使用手动 [重新转换模式](hololens-recovery.md#manual-flashing-mode-procedure)。

[返回到列表](#list)

## <a name="microsoft-edge-fails-to-launch"></a>Microsoft Edge启动失败

> [!NOTE]
> 此问题最初是使用发货版本Microsoft Edge的。 此问题可以在新的 中[Microsoft Edge。](hololens-new-edge.md) 如果不是，请提交反馈。

一些客户报告了无法启动Microsoft Edge的问题。 对于这些客户，此问题通过重新启动而仍然存在，并且无法通过Windows或应用程序更新来解决。 如果遇到此问题，并且已确认[Windows](hololens-updates.md#manually-check-for-updates)是最新的，请使用以下类别和子类别从[反馈中心](hololens-feedback.md)应用提交 bug：安装和更新 > 下载、安装和配置 Windows 更新。

目前没有已知的解决方法，因为我们目前无法找出问题的根本原因。 通过 反馈中心 bug 有助于调查！ 这是一个 **已知问题**。

[返回到列表](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>键盘不切换到特殊字符

OOBE 期间存在一个问题，即用户选择工作或学校帐户并输入其密码后，尝试通过点击 &123 按钮切换到键盘上的特殊字符不会更改为特殊字符。 这是一个 **已知问题**。

周全方案：

- 关闭键盘，然后通过点击文本字段重新打开它。
- 错误地输入密码。 下次重新启动键盘时，它将如预期工作。
- Web 身份验证，关闭键盘并选择 **"从另一台设备登录"。**
- 如果仅输入数字，用户可以按住某些键打开展开的菜单。
- 使用 USB 键盘。

这不会影响：

- 选择使用个人帐户的用户。

[返回到列表](#list)

## <a name="downloading-locked-files-doesnt-error"></a>下载锁定的文件不会出错

> [!NOTE]
> 这是 Holographic **版本** [21H1 - 2021 年 7](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)月更新中已Windows的已知问题。

在 Holographic Windows的早期版本中，尝试下载锁定文件时，结果将是 HTTP 错误页。 在 Windows Holographic 版本 21H1 更新中，尝试下载锁定的文件会导致未发生任何可见情况-文件不会下载，并且没有错误。

[返回到列表](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>设备门户文件上传/下载时间已过
> [!NOTE]
> 这是 Holographic **版本** [21H1 - 2021 年 7](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)月更新中已Windows的已知问题。 如果以前已禁用 SSL 连接作为解决方法的一部分，强烈建议重新启用它。

一些客户发现，在尝试上传或下载文件时，操作可能显示为挂起，然后会退出或永不完成。 这独立于"[文件](#downloading-locked-files-doesnt-error)锁定"已知问题 - 这Windows全息版 2004、20H2 和 21H1 内部版本。 此问题是导致应用程序处理某些设备门户 bug 的根本原因，并且使用 https 时最一致，这是默认设置。

### <a name="workaround"></a>解决方法

此解决方法同样适用于 Wi-Fi UsbNcm，即禁用"SSL 连接"下的"必需"选项。 为此，请导航到设备门户" **系统**"，然后选择" **首选项"** 页。 在"**设备安全性"** 部分中，找到 **"SSL 连接"，** 取消选中以禁用"**必需"。**

然后，用户应转到 http://，https:// (IP 地址) 文件上传和下载等功能将正常工作。

[返回到列表](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>从预览体验成员预览版取消注册后，在设备上以预览体验成员版本刷出蓝屏

这是影响使用 Insider 预览版的用户、使用新的预览体验内部版本重新HoloLens 2，然后从预览体验计划取消注册的用户的问题。 这是一个 **已知问题**。

这不会影响：

- 未在预览体验成员Windows用户
- 业内 人士：
    - 如果设备自 Insider 内部版本为版本 18362.x 以来已注册
    - 如果他们刷过预览体验成员签名的 19041.x 内部版本，并一直注册到 Insider 计划

工作之一：

- 避免此问题
    - 刷用非预览体验内部版本。 每月定期更新之一。
    - 随时了解预览体验成员
- 重新运行设备

    1. 在HoloLens 2[时](hololens-recovery.md)完全关闭电源，将设备手动置于闪烁模式。 然后，在按住"音量"的同时，点击"电源"按钮。

    1. 连接电脑并打开"高级恢复助手"。

    1. 将HoloLens 2刷新到默认生成。

[返回到列表](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive不会自动上传图片

OneDrive应用HoloLens工作或学校帐户的自动相机上传。 这是一个 **已知问题**。

解决方法：

- 如果你的业务可行，则使用者 Microsoft 帐户支持自动上传相机。 除了工作或学校帐户Microsoft 帐户还可以登录到 (，OneDrive应用支持双重登录) 。 从Microsoft 帐户配置文件OneDrive启用自动后台相机滚动上传。

- 如果无法安全地使用使用者Microsoft 帐户自动上传照片，可以从应用将照片手动上传到工作或OneDrive帐户。 为此，请确保已登录到 OneDrive 应用的工作或学校帐户。 选择按钮 **+** 并选择 **"Upload"。** 通过导航到"照片"和"相机滚动> **上传的照片或视频**。 选择要上传的一个或多个照片或视频，然后选择"打开 **"** 按钮。

[返回到列表](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens无响应或无法启动

如果HoloLens启动：

- 如果电源按钮旁边的 LED 不亮起，或只有一个 LED 短暂闪烁，可能需要为电源[HoloLens。](hololens2-charging.md#charging-the-device)
- 如果 LED 在按下电源按钮时亮起，但在显示器上看不到任何内容，请对设备 进行 [硬重置](hololens-recovery.md#hard-restart-procedure)。

如果HoloLens冻结或无响应：

- 按电源HoloLens关闭电源按钮，直到所有五个 LED 都自行关闭;如果 LED 无响应，则关闭电源按钮 15 秒。 若要启动HoloLens，请再次按电源按钮。

如果这些步骤不起作用，可以尝试恢复HoloLens 2或HoloLens ([第一代) 设备。](hololens1-recovery.md) [](hololens-recovery.md)

[返回到列表](#list)

## <a name="low-disk-space-error"></a>"磁盘空间不足"错误

需要执行以下操作一个或多个来释放一些存储空间：

- 删除一些未使用的空格。 转到设置  >  **系统**  >  **空间"，** 选择不再需要的空间，然后选择"删除 **"。**
- 删除已放置的部分全息影像。
- 从照片应用中删除一些图片和视频。
- 从 HoloLens 卸载某些应用。 在 " **所有应用** " 列表中，点击并按住你要卸载的应用，然后选择 " **卸载**"。

[返回到列表](#list)

## <a name="calibration-fails"></a>校准失败

校准应该适用于大多数人，但在某些情况下校准失败。
  
校准失败的可能原因包括：

- 进行分散而不关注校准目标
- 脏或有划痕的设备面板或设备面板未正确定位
- 有脏或有划痕
- 某些类型的 contact 重用功能区和眼镜 (彩色触点重用功能区，一些 toric contact 重用功能区，红外阻挡眼镜，一些高处方、太阳镜或类似) 
- 更明显的组成部分和一些 eyelash 扩展
- 如果要阻止设备看到你的眼睛，请眼镜框架
- 某些眼睛 physiology、目视条件或眼睛，如狭窄眼睛、长 eyelashes、amblyopia、nystagmus、LASIK 或其他眼睛 surgeries 的一些情况

如果校准失败，请尝试：

- 清理设备面板
- 清除眼镜
- 尽可能接近眼睛的设备面板
- 在面板中移动对象， (如头发) 
- 打开房间中的灯光或从直射上直射

如果你遵循了所有准则，并且校准仍失败，则可以在设置中禁用校准提示。 还可以通过在 [反馈中心](hololens-feedback.md)中归档反馈来告知我们。

另请参阅[图像颜色或亮度疑难解答](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)的相关信息。

设置 IPD 不适用于 HoloLens 2，因为目视位置由系统计算。 

[返回到列表](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>无法登录，因为以前为其他人设置了我的 HoloLens

可以 [将设备置于 **闪烁模式** ，并使用高级恢复助理](hololens-recovery.md#clean-reflash-the-device) 来恢复设备。

[返回到列表](#list)


## <a name="unity-isnt-working"></a>Unity 不起作用

- 请参阅安装适用于 HoloLens 开发的最新 Unity 版本[工具](/windows/mixed-reality/install-the-tools)。
- [HoloLens unity 论坛](https://forum.unity3d.com/threads/known-issues.394627/)中介绍了 unity HoloLens Technical Preview 的已知问题。

[返回到列表](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows设备门户工作不正常

- 混合现实捕获中的实时预览功能可能会出现几秒钟的延迟。

- 在 "虚拟输入" 页上，"虚拟手势" 部分下的手势和滚动控件不起作用。 使用它们将不起作用。 虚拟输入页上的虚拟键盘工作正常。

- 在设置中启用 "开发人员模式" 后，可能需要几秒钟才能打开设备门户。

[返回到列表](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator 不起作用

有关 HoloLens 模拟器的信息位于开发人员文档中。  阅读有关[排查 HoloLens 模拟器问题的](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)详细信息。


- 并非 Microsoft Store 中的所有应用都与模拟器兼容。 例如，不能在模拟器上播放年轻人 Conker 和片段。
- 无法在 Emulator 中使用 PC 网络摄像机。
- Windows 设备门户的实时预览功能不适用于模拟器。 你仍可以捕获混合现实视频和图像。

[返回到列表](#list)

## <a name="voice-commands-arent-working"></a>语音命令不起作用

如果 Cortana 没有响应语音命令，请确保 Cortana 已打开。 在 "所有应用" 列表中，选择 **Cortana**  >  **菜单**  >  **笔记本**  >  **设置** 进行更改。 若要详细了解你可以说的内容，请参阅[将语音与 HoloLens 一起使用](hololens-cortana.md)。

在 HoloLens (1 代) ，内置语音识别不可配置。 始终打开。 在 HoloLens 2 上，你可以选择是否在设备安装期间打开语音识别和 Cortana。

如果您的 HoloLens 2 没有响应您的语音，请确保已启用语音识别。 转到 **开始**  >  **设置**  >  **隐私**  >  **语音** 并打开 **语音识别**。

[返回到列表](#list)

## <a name="hand-input-isnt-working"></a>手写输入不起作用

若要确保 HoloLens 可以看到您的手，需要将它们保留在手势帧中。  混合现实主页提供反馈，让你知道何时跟踪你的手。  不同版本的 HoloLens 的反馈有所不同：

- 在 HoloLens 第一代)  (，注视光标会从点变为圆圈
- 在 HoloLens 2 上，当手接近某个石板时，将出现一个手指光标，而当清单进一步离开时，将显示一只手

许多沉浸式应用都遵循类似于混合现实主页的输入模式。  详细了解如何使用[HoloLens (第一代) ](hololens1-basic-usage.md#use-hololens-with-your-hands)和[HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)上的手动输入。

如果戴上手套，请注意，某些类型的手套不适用于手动跟踪。  常见的例子是黑色橡胶手套，这通常会吸收红外线，而不是由深度相机选取。  如果你的工作涉及橡胶手套，我们建议尝试使用较浅的颜色，如蓝色或灰色。  另一个示例是大型 baggy 手套，这种情况通常会使手不会遮盖。 为了获得最佳效果，我们建议使用以窗体为形式的手套。

如果面板具有指纹或无污迹，请使用 HoloLens 附带的 microfiber 清洁抹布来轻轻地清理面板。

[返回到列表](#list)

## <a name="cant-connect-to-wi-fi"></a>无法连接到 Wi-Fi

如果无法将 HoloLens 连接到 Wi-Fi 网络，请尝试以下操作：

- 确保 Wi-Fi 已打开。 若要进行检查，请使用开始手势，然后选择 **设置**  >  **网络 &amp; Internet**  >  **wi-fi**"。 如果 Wi-Fi 处于打开状态，请尝试将其关闭，然后重新打开。
- 移动以靠近路由器或接入点。
- 重新启动 Wi-Fi 路由器，然后[重启 HoloLens](hololens-recovery.md)。 请再次尝试连接。
- 如果这些操作都不起作用，请进行检查以确保路由器使用的是最新固件。 你可以在制造商网站上找到此信息。

[返回到列表](#list)

## <a name="bluetooth-devices-arent-pairing"></a>蓝牙设备不配对

如果在[配对蓝牙设备](hololens-connect-devices.md)时遇到问题，请尝试以下操作：

- 转到 **设置**  >  **设备**，并确保蓝牙已打开。 如果是，请将其关闭，然后重新打开。
- 请确保蓝牙设备已完全充电或具有新电池。
- 如果仍然无法连接，请[重新启动 HoloLens](hololens-recovery.md)。

[返回到列表](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C 麦克风不工作

请注意，某些 USB-C 麦克风会错误地将自身报告为麦克风 *和* 扬声器。 这是麦克风问题，而不是 HoloLens。 将其中一个麦克风插入 HoloLens 时，可能会丢失声音。 幸运的是，有一个简单的修补程序。  

在 **设置**  ->  **系统**  ->  **声音**"中，将内置扬声器 **(模拟功能音频驱动程序")** 为 **默认设备**。 即使稍后会删除并重新连接麦克风，HoloLens 也应记住此设置。

![USB-C 麦克风故障排除。](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>列为设置的设备不起作用

HoloLens 第一代 () 不支持蓝牙音频配置文件。 蓝牙音频设备（如扬声器和耳机）在 HoloLens 设置中可能显示为可用，但不受支持。

HoloLens 2 支持用于立体声播放的蓝牙 A2DP 音频配置文件。 HoloLens 2 不支持从蓝牙外设启用麦克风捕获的蓝牙免提免费配置文件。

如果使用蓝牙设备时遇到问题，请确保它是受支持的设备。 支持的设备包括：

- 使用简体中文蓝牙键盘 (可以在任何使用全息键盘) 的地方使用。
- 蓝牙鼠标。
- [HoloLens clicker](hololens1-clicker.md)。

你可以将其他蓝牙 HID 和 GATT 设备与你的 HoloLens 配对。 但是，你可能需要从 Microsoft Store 安装相应的随附应用才能实际使用设备。

[返回到列表](#list)
