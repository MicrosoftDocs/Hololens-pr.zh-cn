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
ms.openlocfilehash: 6ac86acf85e8e4fc1b97473732ea358d3d612d12
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190015"
---
# <a name="device-troubleshooting"></a>设备故障排除

本文介绍如何解决几个常见的 HoloLens 问题。

>[!IMPORTANT]
> 在开始任何故障排除过程之前，请确保将设备充电至电池容量的 20 % 至 40%（如可能）。 通过位于电源按钮下的[电池指示灯](hololens2-setup.md#lights-that-indicate-the-battery-level)可以快速验证电池容量（无需登录到设备）。

<a id="list"></a>

**已知问题**
- [远程协助视频在20分钟后冻结](#remote-assist-video-freezes-after-20-minutes)
- [自动登录请求登录](#auto-login-asks-for-log-in)
- [无法启动 Microsoft Edge](#microsoft-edge-fails-to-launch)
- [键盘无法切换为特殊字符](#keyboard-doesnt-switch-to-special-characters)
- [下载锁定的文件不显示错误](#downloading-locked-files-doesnt-error)
- [设备门户文件上传/下载超时](#device-portal-file-uploaddownload-times-out)
- [取消注册在使用 Insider 内部版本闪存的设备上预览有问必答后的蓝屏](#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)
- [OneDrive 不会自动上载图片](#onedrive-doesnt-automatically-upload-pictures)

**常规**
- [HoloLens 无响应或不启动](#hololens-is-unresponsive-or-wont-start)
- ["磁盘空间不足" 错误](#low-disk-space-error)
- [校准失败](#calibration-fails)
- [无法登录，因为以前为其他人设置了我的 HoloLens](#cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else)
- [Unity 不起作用](#unity-isnt-working)
- [Windows设备门户工作不正常](#windows-device-portal-isnt-working-correctly)
- [HoloLens Emulator 不起作用](#the-hololens-emulator-isnt-working)

**输入**
- [语音命令不起作用](#voice-commands-arent-working)
- [手写输入不起作用](#hand-input-isnt-working)

**连接**
- [无法连接到 Wi-fi](#cant-connect-to-wi-fi)

**外部设备** 
- [蓝牙设备不配对](#bluetooth-devices-arent-pairing)
- [USB-C 麦克风不工作](#usb-c-microphone-isnt-working)
- [列为设置的设备不起作用](#devices-listed-as-available-in-settings-dont-work)

## <a name="remote-assist-video-freezes-after-20-minutes"></a>远程协助视频在20分钟后冻结

> [!NOTE]
> 有一个较新版本的远程协助，此问题可以解决此问题。 请将 [远程协助更新](holographic-store-apps.md#update-apps) 到最新版本，以避免此问题。

> [!NOTE]
> 由于此已知问题的严重性，我们暂时暂停 Windows 全息版21H1 的可用性。 现在可再次使用21H1 生成，因此设备可能会再次更新为最新的21H1 版本。

在最新版本的[Windows 全息版 21H1](hololens-release-notes.md#windows-holographic-version-21h1)上，某些远程协助用户在20分钟调用期间经历了视频冻结。 这是一个 **已知问题**。

### <a name="workarounds"></a>解决方法

如果无法将远程协助更新到较新的版本，请尝试以下解决方法。

#### <a name="restart-in-between-calls"></a>在两次调用之间重启

如果调用的持续时间超过20分钟并且遇到此问题，请尝试重新启动设备。 在远程协助调用之间重启设备会刷新设备，并将其恢复到正常状态。

若要在 [Windows 全息版](hololens-release-notes.md#windows-holographic-version-21h1)上快速重启设备，请打开 "开始" 菜单，选择 "用户" 图标，然后选择 "**重新启动**"。

[返回到列表](#list)

## <a name="auto-login-asks-for-log-in"></a>自动登录请求登录

可以将 HoloLens 2 设备配置为通过 **设置**  ->  **帐户**  ->  **登录选项** 自动登录->，在 "**必需**" 下，将值设置为 "**从不**"。 当更新设备时，某些用户可能需要再次登录到该设备，如功能更新。 这是一个 **已知问题**。

此情况的示例：

- 将设备从 Windows 全息版本 2004 (版本生成 19041) Windows 全息，版本 21H1 (build 20346) 
- 更新设备以在同一主版本上进行较大的更新，例如 Windows 全息版，版本2004到 Windows 全息版本20H2
- 将设备从出厂映像更新到最新映像

在以下过程中不应发生此情况：

- 参与每月服务更新的设备

解决方法：

- 登录方法，例如 PIN、Password、Iris、Web Authentication 或 FIDO2 键。
- 如果无法记住设备 PIN，并且其他身份验证方法不可用，则用户可以使用 [手动 reflashing 模式](hololens-recovery.md#manual-procedure)。

[返回到列表](#list)

## <a name="microsoft-edge-fails-to-launch"></a>无法启动 Microsoft Edge

> [!NOTE]
> 此问题最初是在 Microsoft Edge 的发货版本中创建的。 此问题可能已在新的[Microsoft Edge](hololens-new-edge.md)中解决。 如果不是，请提供文件反馈。

几个客户报告了 Microsoft Edge 无法启动的问题。 对于这些客户，此问题将在重新启动后仍然存在，并且不会与 Windows 或应用程序更新一起解决。 如果你遇到此问题，并且已确认[Windows 是最](hololens-updates.md#manually-check-for-updates)新的，请使用以下类别和子类别从[反馈中心应用](hololens-feedback.md)中提交 bug：安装和更新 > 下载、安装和配置 Windows 更新。

没有已知的解决方法，因为我们不能根本就会导致问题。 通过反馈中心归档 bug 可帮助我们调查！ 这是一个 **已知问题**。

[返回到列表](#list)

## <a name="keyboard-doesnt-switch-to-special-characters"></a>键盘无法切换为特殊字符

OOBE 期间存在问题，在用户选择工作或学校帐户并输入密码后，尝试通过点击 "&123" 按钮切换到键盘上的特殊字符不会更改为特殊字符。 这是一个 **已知问题**。

解决办法：

- 关闭键盘，并通过点击 "文本" 字段将其重新打开。
- 输入的密码不正确。 下一次变时，它将按预期方式工作。
- Web 身份验证，关闭键盘，然后选择 **"从其他设备登录"**。
- 如果只输入数字，用户可以按并按住某些键来打开展开的菜单。
- 使用 USB 键盘。

这不会影响：

- 选择使用个人帐户的用户。

[返回到列表](#list)

## <a name="downloading-locked-files-doesnt-error"></a>下载锁定的文件不出错

> [!NOTE]
> 这是一个 **已知问题**，此问题已在 [Windows 21H1-2021-7 月更新版本](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)中得到修复。

在 Windows 全息版的以前版本中，尝试下载锁定文件时，结果将是 HTTP 错误页。 在 Windows 全息版21H1 更新中，尝试下载锁定的文件会导致不会出现任何问题，文件不会下载，也不会出错。

[返回到列表](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>设备门户文件上传/下载超时
> [!NOTE]
> 这是一个 **已知问题**，此问题已在 [Windows 21H1-2021-7 月更新版本](hololens-release-notes.md#windows-holographic-version-21h1---july-2021-update)中得到修复。 如果你之前已禁用 SSL 连接作为解决方法的一部分，我们强烈建议你重新启用它。

有些客户在尝试上载或下载文件时发现，该操作可能会挂起，然后超时或永不完成。 这不同于 "[文件锁定" 已知问题](#downloading-locked-files-doesnt-error)-这会影响 Windows 全息版、2004版、20H2 和21H1 内部版本。 此问题根本是导致设备门户对某些请求的处理中的 bug 引起的，并且在使用 https （默认值）时，这是最常见的。

### <a name="workaround"></a>解决方法

此解决方法（同样适用于 Wi-Fi 和 UsbNcm）是在 "SSL 连接" 下禁用 "必需" 选项。 为此，请导航到 "设备门户" 和 " **系统**"，然后选择 " **首选项** " 页。 在 " **设备安全性** " 部分中，找到 " **SSL 连接**"，并取消选中以禁用 **所需** 的。

然后，用户应中转到 http://，而不是 https:// (IP 地址) 并且文件上传和下载等功能将正常运行。

[返回到列表](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>取消注册在使用 Insider 内部版本闪存的设备上预览有问必答后的蓝屏

这是一种影响现有预览版本用户的问题，它会将他们的 HoloLens 2 与新的内部版本预览版一起使用，然后从有问必答程序取消注册 reflashed。 这是一个 **已知问题**。

这不会影响：
- 未在 Windows 有问必答注册的用户 
- 人员
    - 如果设备已注册，因为有问必答版本是版本 18362. x
    - 如果他们刷新了预览体验的19041生成并在预览体验计划中保持注册

解决方法： 
- 避免此问题 
    - 刷新非预览体验内部版本。 定期每月更新一次。
    - 保持预览体验体验
- 刷新设备

    1. 通过在不连接的情况下完全关闭，将 HoloLens 2 手动置于[闪烁模式](hololens-recovery.md)。 然后按住该按钮，然后点击 "电源" 按钮。
    
    1. 连接计算机，并打开 "高级恢复助理"。
    
    1. 将 HoloLens 2 闪存到默认生成。

[返回到列表](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive 不会自动上载图片

HoloLens 的 OneDrive 应用不支持工作或学校帐户的自动照相机上传。 这是一个 **已知问题**。

解决方法：

- 对于你的业务，在使用者 Microsoft 帐户上支持自动照相机上传。 除了使用工作或学校帐户外，还可以登录到 Microsoft 帐户 (OneDrive 应用支持双重登录) 。 在 OneDrive 内的 Microsoft 帐户配置文件中，你可以启用自动播放背景照相机滚动。

- 如果你不能安全地使用使用者 Microsoft 帐户来自动上载照片，你可以从 OneDrive 应用手动将照片上传到你的工作或学校帐户。 为此，请确保已登录到 OneDrive 应用中的工作或学校帐户。 选择 "" **+** 按钮，然后选择 " **Upload**"。 通过导航到 " **照片" > 照相机滚动**"查找要上传的照片或视频。 选择要上传的照片或视频，然后选择 " **打开** " 按钮。

[返回到列表](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens 无响应或不启动

如果 HoloLens 不会启动：

- 如果电源按钮旁边的 Led 没有亮起，或只有一个 LED 闪烁，则您可能需要对[HoloLens 收费。](hololens2-charging.md#charging-the-device)
- 如果在按下电源按钮时 Led 亮起，但在显示器上看不到任何内容，请对 [设备进行硬重置](hololens-recovery.md#hard-reset-procedure)。

如果 HoloLens 变为冻结或无响应：

- 按下电源按钮关闭 HoloLens，直到所有5个 led 关闭，或者如果 led 无响应，则为15秒。 要开始 HoloLens，请再次按下 "电源" 按钮。

如果这些步骤不起作用，你可以尝试[恢复 HoloLens 2 设备](hololens-recovery.md)或[HoloLens (第一代) 设备。](hololens1-recovery.md)

[返回到列表](#list)

## <a name="low-disk-space-error"></a>"磁盘空间不足" 错误

你需要通过执行以下一项或多项操作来释放一些存储空间：

- 删除某些未使用的空间。 中转到 **设置**  >  **系统**  >  **空间**"，选择不再需要的空间，然后选择"**删除**"。
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

在HoloLens (第一代) ，内置语音识别不可配置。 它始终打开。 在HoloLens 2，可以选择在设备设置期间是否同时Cortana语音识别和语音。

如果HoloLens 2语音未响应，请确保已打开语音识别。 转到"**开始**  >  **设置**  >    >  **语音"并** 启用 **语音识别**。

[返回到列表](#list)

## <a name="hand-input-isnt-working"></a>手动输入不工作

若要确保HoloLens看到手，需要将它们放在手势框架中。  混合现实主页提供反馈，让你了解何时跟踪手部。  不同版本的服务的反馈HoloLens：
- 在HoloLens (第一代) 上，凝视光标从点变为环
- 在HoloLens 2，当手靠近平板电脑时，会出现一个手指光标，当板离得远时，会出现手部射线

许多沉浸式应用遵循类似于混合现实主页的输入模式。  详细了解第一代和 HoloLens ([上](hololens1-basic-usage.md#use-hololens-with-your-hands)[) HoloLens 2。](hololens2-basic-usage.md#the-hand-tracking-frame)

如果你正在戴眼镜，请注意，某些类型的手部手部跟踪不起作用。  一个常见示例是黑色保护套，它往往能吸收光线，并且不会由深度相机拾取。  如果你的工作涉及橡皮套，我们建议尝试较浅的颜色，如蓝色或灰色。  另一个示例是大包袋套，它往往遮盖手的形状。 我们建议使用尽可能适合窗体的外套，以获得最佳结果。

如果你的视器具有指纹或指纹，请使用设备中HoloLens清理视板。

[返回到列表](#list)

## <a name="cant-connect-to-wi-fi"></a>无法连接到 Wi-Fi

如果无法将 HoloLens 连接到 Wi-Fi 网络，请尝试以下操作：

- 确保 Wi-Fi 已打开。 若要检查，请使用"开始"手势，然后选择 **"设置**  >  **&amp; Internet**  >  **Wi-Fi"。** 如果 Wi-Fi 处于打开状态，请尝试将其关闭，然后重新打开。
- 移动以靠近路由器或接入点。
- 重启Wi-Fi路由器，[然后重启HoloLens。](hololens-recovery.md) 请再次尝试连接。
- 如果这些操作都不起作用，请进行检查以确保路由器使用的是最新固件。 你可以在制造商网站上找到此信息。

[返回到列表](#list)

## <a name="bluetooth-devices-arent-pairing"></a>蓝牙设备未配对

如果在将设备与设备[蓝牙时遇到问题，](hololens-connect-devices.md)请尝试以下操作：

- 转到 **设置**  >  **"设备**"，并确保蓝牙设备" 。 如果是，请将其关闭并再次打开。
- 请确保设备已蓝牙或具有新电池。
- 如果仍然无法连接，请[重启HoloLens。](hololens-recovery.md)

[返回到列表](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C 麦克风不工作
请注意，某些 USB-C 麦克风错误地将自身报告为 *麦克风和扬声器* 。 这是麦克风的问题，而不是麦克风HoloLens。 将其中一个麦克风插入 HoloLens时，可能会丢失声音。 幸运的是，有一个简单的修复方法。  

在 **设置** System Sound 中，将"模拟功能音频驱动程序" (的内置扬声器)  ->    ->  设置为 **"默认设备"。**  HoloLens应记住此设置，即使稍后删除了麦克风并重新连接。

![USB-C 麦克风疑难解答。](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>在 设置 中列为可用的设备不起作用

HoloLens (第一代) 不支持蓝牙配置文件。 蓝牙音频设备（如扬声器和头戴显示设备）在HoloLens中显示为可用，但不受支持。

HoloLens 2支持蓝牙立体声播放的 A2DP 音频配置文件。 支持蓝牙麦克风捕获的无手配置文件蓝牙不支持从外设捕获麦克风HoloLens 2。

如果在使用设备时遇到蓝牙，请确保它是受支持的设备。 支持的设备包括：

- 英语 QWERTY 蓝牙键盘 (可以在使用全息键盘键盘或键盘的任何位置) 。
- 蓝牙鼠标。
- 单击[HoloLens器](hololens1-clicker.md)。

可以将其他 蓝牙 HID 和 GATT 设备与设备HoloLens。 但是，可能需要从设备安装相应的Microsoft Store应用，以实际使用设备。

[返回到列表](#list)
