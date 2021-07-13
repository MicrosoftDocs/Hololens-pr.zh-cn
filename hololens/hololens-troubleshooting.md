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
# <a name="device-troubleshooting"></a>设备故障排除

本文介绍如何解决几个常见的 HoloLens 问题。

>[!IMPORTANT]
> 在开始任何故障排除过程之前，请确保你的设备需要支付 **20 到 40%** 的电池容量（如果可能）。 "电源" 按钮下的 " [电池指示器" 指示灯](hololens2-setup.md#lights-that-indicate-the-battery-level) 是在不登录到设备的情况下快速验证电池容量的方法。

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
-   关闭键盘，并通过点击 "文本" 字段将其重新打开。
-   输入的密码不正确。 下一次变时，它将按预期方式工作。
- Web 身份验证，关闭键盘，然后选择 **"从其他设备登录"**。
-   如果只输入数字，用户可以按并按住某些键来打开展开的菜单。
-   使用 USB 键盘。

这不会影响：
- 选择使用个人帐户的用户。

[返回到列表](#list)

## <a name="downloading-locked-files-doesnt-error"></a>下载锁定的文件不出错

> [!NOTE]
> 这是一个 **已知问题**，此问题已在 Windows 内幕版本20348.1403 中解决。

在 Windows 全息版的以前版本中，尝试下载锁定文件时，结果将是 HTTP 错误页。 在 Windows 全息版21H1 更新中，尝试下载锁定的文件会导致不会出现任何问题，文件不会下载，也不会出错。

[返回到列表](#list)

## <a name="device-portal-file-uploaddownload-times-out"></a>设备门户文件上传/下载超时
> [!NOTE]
> 这是一个 **已知问题**，此问题已在 Windows 内幕版本20348.1403 中解决。 如果你之前已禁用 SSL 连接作为解决方法的一部分，我们强烈建议你重新启用它。


有些客户在尝试上载或下载文件时发现，该操作可能会挂起，然后超时或永不完成。 这不同于 "[文件锁定" 已知问题](#downloading-locked-files-doesnt-error)-这会影响 Windows 全息版、2004版、20H2 和21H1 内部版本。 此问题根本是导致设备门户对某些请求的处理中的 bug 引起的，并且在使用 https （默认值）时，这是最常见的。 

### <a name="workaround"></a>解决方法

此解决方法（同样适用于 Wi-Fi 和 UsbNcm）是在 "SSL 连接" 下禁用 "必需" 选项。 为此，请导航到 "设备门户" 和 " **系统**"，然后选择 " **首选项** " 页。 在 " **设备安全性** " 部分中，找到 " **SSL 连接**"，并取消选中以禁用 **所需** 的。

然后，用户应转到 http://，https:// (IP 地址) 文件上传和下载等功能将正常工作。

[返回列表](#list)

## <a name="blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build"></a>从预览体验成员预览版取消注册后，在设备上以预览体验成员版本刷出蓝屏

这是影响使用 Insider 预览版的用户的问题，使用新的预览版重新HoloLens 2预览体验版，然后从预览体验计划取消注册。 这是一个 **已知问题**。

这不会影响：
- 未在预览体验成员Windows用户 
- 业内 人士：
    - 如果设备自预览体验内部版本为版本 18362.x 以来已注册
    - 如果他们刷过预览体验成员签名的 19041.x 内部版本，并一直注册到 Insider 计划

工作之一： 
- 避免此问题 
    - 刷用非预览体验内部版本。 每月定期更新之一。
    - 随时了解预览体验成员
- 重新运行设备

    1. 在[未HoloLens 2](hololens-recovery.md)时完全关闭电源，将设备手动置于闪烁模式。 然后，在按住"音量"的同时，点击"电源"按钮。
    
    1. 连接电脑并打开"高级恢复助手"。
    
    1. 将HoloLens 2刷新为默认生成。

[返回列表](#list)

## <a name="onedrive-doesnt-automatically-upload-pictures"></a>OneDrive不会自动上传图片

OneDrive应用HoloLens工作或学校帐户的自动相机上传。 这是一个 **已知问题**。

解决方法：

- 如果你的业务可行，则使用者 Microsoft 帐户支持自动上传相机。 除了工作或学校帐户Microsoft 帐户还可以登录到 (，OneDrive应用支持双重登录) 。 在Microsoft 帐户配置文件OneDrive启用自动后台相机滚动上传。

- 如果无法安全地使用使用者Microsoft 帐户自动上传照片，可以从应用将照片手动上传到工作或OneDrive帐户。 为此，请确保已登录到应用应用OneDrive帐户。 选择按钮 **+** 并选择"Upload"。  通过导航到"照片"和"相机滚动> **上传的照片或视频**。 选择要上传的一个或多个照片或视频，然后选择"打开 **"** 按钮。

[返回列表](#list)

## <a name="hololens-is-unresponsive-or-wont-start"></a>HoloLens无响应或无法启动

如果HoloLens启动：

- 如果电源按钮旁边的 LED 不亮起，或只有一个 LED 短暂闪烁，可能需要为电源[HoloLens。](hololens2-charging.md#charging-the-device)
- 如果 LED 在按下电源按钮时亮起，但在显示器上看不到任何内容，请对设备 进行 [硬重置](hololens-recovery.md#hard-reset-procedure)。

如果HoloLens冻结或无响应：

- 按电源HoloLens关闭电源按钮，直到所有五个 LED 都自行关闭，如果 LED 无响应，则关闭 15 秒。 若要启动HoloLens，请再次按电源按钮。

如果这些步骤不起作用，可以尝试恢复设备HoloLens 2或HoloLens ([](hololens-recovery.md)第[一代) 设备。](hololens1-recovery.md)

[返回列表](#list)

## <a name="low-disk-space-error"></a>"磁盘空间不足"错误

需要执行以下操作一个或多个来释放一些存储空间：

- 删除一些未使用的空格。 转到设置  >  **系统**  >  **空间"，** 选择不再需要的空间，然后选择"删除 **"。**
- 删除放置的一些全息影像。
- 从照片应用中删除一些图片和视频。
- 从应用程序卸载HoloLens。 在"**所有应用"** 列表中，点击并按住要卸载的应用，然后选择"卸载 **"。**

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

如果遵循所有准则，并且校准仍失败，可以在测试中禁用校准设置。 此外，请通过向 提交反馈来[反馈中心。](hololens-feedback.md)

另请参阅图像颜色 [或亮度故障排除的相关信息。](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)

设置 IPD 不适用于HoloLens 2，因为眼睛位置由系统计算。 

[返回列表](#list)

## <a name="cant-sign-in-because-my-hololens-was-previously-set-up-for-someone-else"></a>无法登录，因为之前为HoloLens设置了我的帐户

可以将 [设备置于 **刷用模式，** 并使用高级恢复](hololens-recovery.md#clean-reflash-the-device) 助手来恢复设备。

[返回列表](#list)


## <a name="unity-isnt-working"></a>Unity 不工作

- 请参阅[安装工具](/windows/mixed-reality/install-the-tools)，了解建议用于开发HoloLens最新版本的 Unity。
- Unity HoloLens Technical Preview 的已知问题记录在 HoloLens [Unity 论坛中](https://forum.unity3d.com/threads/known-issues.394627/)。

[返回列表](#list)

## <a name="windows-device-portal-isnt-working-correctly"></a>Windows设备门户无法正常工作

- 混合现实捕获中的实时预览功能可能会出现几秒钟的延迟。

- 在"虚拟输入"页上，"虚拟手势"部分下的"手势"和"滚动"控件不起作用。 使用它们将不起作用。 虚拟输入页上的虚拟键盘正常工作。

- 在 设置 中启用开发人员模式后，可能需要几秒钟时间，开关才能打开设备门户模式。

[返回列表](#list)

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens Emulator运行

有关 HoloLens 模拟器的信息，请参阅我们的开发人员文档。  详细了解如何[排查 HoloLens 模拟器。](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-hololens-emulator#troubleshooting)


- 并非所有应用Microsoft Store模拟器兼容。 例如，Young Conker 和 Fragments 在仿真器上不可播放。
- 不能在设备中使用电脑网络Emulator。
- Windows 设备门户的 Live Preview 功能不能与模拟器一起使用。 你仍然可以捕获混合现实视频和图像。

[返回列表](#list)

## <a name="voice-commands-arent-working"></a>语音命令无法工作

如果Cortana未响应语音命令，请确保Cortana语音命令。 在"所有应用"列表中  >  **，Cortana"菜单**  >  **笔记本**  >  **设置** 进行更改。 若要详细了解可以说出的话，请参阅将语音与[HoloLens。](hololens-cortana.md)

在HoloLens (第一代) ，内置语音识别不可配置。 它始终打开。 在HoloLens 2，可以选择在设备设置期间是否同时Cortana语音识别和语音。

如果HoloLens 2语音未响应，请确保启用语音识别。 转到"**开始**  >  **设置**  >    >  **语音"并** 打开 **语音识别**。

[返回列表](#list)

## <a name="hand-input-isnt-working"></a>手动输入不工作

若要确保HoloLens看到手，需要将它们放在手势框架中。  混合现实主页提供反馈，让你了解何时跟踪手部。  不同版本的服务的反馈HoloLens：
- 在HoloLens (第一代) 上，凝视光标从点变为环
- 在HoloLens 2，当手靠近平板电脑时，会出现一个手指光标，当板离得远时，会出现手部射线

许多沉浸式应用遵循类似于混合现实主页的输入模式。  详细了解第一代和 HoloLens ([上的) HoloLens 2。](hololens1-basic-usage.md#use-hololens-with-your-hands) [](hololens2-basic-usage.md#the-hand-tracking-frame)

如果你正在戴眼镜，请注意，某些类型的手部手部跟踪不起作用。  一个常见示例是黑色保护套，它往往能吸收光线，并且不会由深度相机拾取。  如果你的工作涉及橡皮套，我们建议尝试较浅的颜色，如蓝色或灰色。  另一个示例是大包袋套，它往往遮盖手的形状。 我们建议使用尽可能适合窗体的外套，以获得最佳结果。

如果视器具有指纹或指纹，请使用设备中HoloLens的微fiber 清理设备来清理视器。

[返回列表](#list)

## <a name="cant-connect-to-wi-fi"></a>无法连接到 Wi-Fi

如果无法将客户端连接到网络，请尝试HoloLens一Wi-Fi操作：

- 确保Wi-Fi打开。 若要检查，请使用"开始"手势，然后选择设置  >  **网络 &amp; Internet**  >  **Wi-Fi"。** 如果Wi-Fi，请尝试将其关闭，然后再次打开。
- 移动以靠近路由器或接入点。
- 重启Wi-Fi路由器，[然后重启HoloLens。](hololens-recovery.md) 请再次尝试连接。
- 如果上述操作均不起作用，请检查以确保路由器使用的是最新的固件。 可以在制造商网站上找到此信息。

[返回列表](#list)

## <a name="bluetooth-devices-arent-pairing"></a>蓝牙设备未配对

如果在与设备配对蓝牙[时遇到问题，](hololens-connect-devices.md)请尝试以下操作：

- 转到  >  **设置""** 设备"，并确保蓝牙设备" 。 如果是，请将其关闭并再次打开。
- 请确保设备已蓝牙或具有新电池。
- 如果仍然无法连接，请[重启HoloLens。](hololens-recovery.md)

[返回列表](#list)

## <a name="usb-c-microphone-isnt-working"></a>USB-C 麦克风不工作
请注意，某些 USB-C 麦克风错误地将自身报告为 *麦克风和扬声器* 。 这是麦克风的问题，而不是麦克风HoloLens。 将其中一个麦克风插入 HoloLens时，可能会丢失声音。 幸运的是，有一个简单的修复方法。  

在 **设置** System Sound 中，将"模拟功能音频驱动程序" (将内置扬声器) 设置为  ->    ->  **"默认设备"。** HoloLens应记住此设置，即使稍后删除了麦克风并重新连接。

![USB-C 麦克风疑难解答](images/usbc-mic-4.png)

## <a name="devices-listed-as-available-in-settings-dont-work"></a>在 设置 中列为可用的设备不起作用

HoloLens (第一代) 不支持蓝牙配置文件。 蓝牙音频设备（如扬声器和头戴显示设备）在HoloLens中显示为可用，但不受支持。

HoloLens 2支持蓝牙立体声播放的 A2DP 音频配置文件。 支持蓝牙麦克风捕获的无手配置文件蓝牙设备不支持从外设捕获HoloLens 2。

如果在使用设备时遇到蓝牙，请确保它是受支持的设备。 支持的设备包括：

- 英语 QWERTY 蓝牙键盘 (，可以在使用全息键盘键盘或键盘的任何位置) 。
- 蓝牙鼠标。
- 单击[HoloLens单击器](hololens1-clicker.md)。

可以将其他 HID 蓝牙 GATT 设备与设备配对HoloLens。 但是，可能需要从客户端安装相应的Microsoft Store应用，以实际使用设备。

[返回列表](#list)
