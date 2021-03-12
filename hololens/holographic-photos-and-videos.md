---
title: 捕获、录制和共享混合现实照片和视频
description: 了解如何使用 HoloLens 混合现实设备捕获、记录和查看混合现实照片和视频。 了解如何通过 Miracast 或收集的文件共享。
keywords: hololens， 照片， 视频， 捕获， mrc， 混合现实捕获， 照片， 相机， miracast， 流， 实时流， 演示， 记录
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 86ef4328869c15517732eedf3dfb9e2a8252e713
ms.sourcegitcommit: 047738224840013bede45dbb642a0ad2115a9c84
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406706"
---
# <a name="create-mixed-reality-photos-and-videos"></a>创建混合现实照片和视频

HoloLens 为用户提供了将现实世界与数字世界混合的体验。  混合现实捕获 (MRC) 允许你将体验捕获为照片或视频，或与他人实时共享所看到内容。

混合现实捕获使用第一人称视角，以便其他人可以在你看到全息影像时看到全息影像。 对于第三人称的视点，请使用 [观众视图](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。 观众视图对于演示特别有用。

虽然在朋友和同事之间共享视频很有趣，但视频还有助于教其他人使用应用或沟通应用和体验问题。

> [!NOTE]
> 如果无法启动混合现实捕获体验，并且 HoloLens 是工作设备，请与系统管理员联系。 可通过公司策略限制对相机的访问。

## <a name="capture-a-mixed-reality-photo"></a>捕获混合现实照片

有几种方法在 HoloLens 上拍摄混合现实照片;可以使用硬件按钮、语音或"开始"菜单。

### <a name="hardware-buttons-to-take-photos"></a>用于拍摄照片的硬件按钮

若要快速拍摄当前视图的照片，请同时按调高音量和降低音量按钮。  这有点像屏幕截图或打印屏幕的 HoloLens 版本。

- [HoloLens 2 上的按钮位置](hololens2-hardware.md)
- [HoloLens 第一代 (上的按钮) ](hololens1-hardware.md#hololens-components)

> [!NOTE]
> 将**音量调高和****音量降低**按钮按住三秒钟将开始录制视频，而不是拍摄照片。 若要停止录制，请同时点击调 **高** 音量和 **降低** 音量按钮。

### <a name="voice-commands-to-take-photos"></a>用于拍摄照片的语音命令

在 HoloLens 2 版本 2004 (及更高版本) ，说："拍摄照片"。

在 HoloLens (第一代) 或 HoloLens 2 版本 1903 上，说："你好小娜，拍摄照片。"

### <a name="start-menu-to-take-photos"></a>"开始"菜单以拍摄照片

使用"开始"手势转到"开始 **"** 菜单，然后选择 **相机** 图标。

将头指向你想要捕获的方向，然后通过空敲 [击](hololens2-basic-usage.md#touch-holograms-near-you) 来拍摄照片。 你可以继续空敲并捕获其他照片。 你捕获的任何照片都将保存到你的设备。

再次使用"开始"手势结束照片捕获。  

## <a name="capture-a-mixed-reality-video"></a>捕获混合现实视频

有几种方法在 HoloLens 上录制混合现实视频;可以使用硬件按钮、语音或"开始"菜单。

### <a name="hardware-buttons-to-record-videos"></a>用于录制视频的硬件按钮

录制视频的最快方法就是同时按住音量增加和音量降低按钮****，直到开始**** 倒计时 3 秒。 若要停止录制，请同时点击这两个按钮。

> [!NOTE]
> 同时快速**按调高**音量**** 和调低音量按钮将拍摄照片，而不是录制视频。

### <a name="voice-to-record-videos"></a>录制视频的语音

在 HoloLens 2 版本 2004 (及更高版本) ，说："开始录制"。 若要停止录制，请说出"停止录制"。

在 HoloLens (第一代) 或 HoloLens 2 版本 1903 上，说："你好小娜，开始录制。" 若要停止录制，请说出"你好小娜，停止录制"。

### <a name="start-menu-to-record-videos"></a>"开始"菜单录制视频

使用"开始"手势转到"开始 **"，** 然后选择 **视频** 图标。 将头指向要捕获的方向，然后通过空击 [开始](hololens2-basic-usage.md#touch-holograms-near-you) 录制。 有三秒钟的倒计时，你的录制将开始。

若要停止录制，请使用"开始"手势并选择突出显示 **的视频** 图标。 视频将保存到设备。

> [!NOTE]
> **仅适用于 HoloLens (第一代) 应用**  
> Windows [10 2018 年 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) 月更新更改了"开始"手势和 Windows 按钮在 HoloLens 第一代 (上的行为) 。 在更新之前，"开始"手势或 Windows 按钮将停止视频录制。 但是，更新后，如果你使用沉浸式应用) ，"开始"手势或 Windows**** 按钮将打开"开始"菜单 (或快速操作菜单，你可以从其中选择突出显示的视频图标来**** 停止录制。 ****

## <a name="share-what-you-see-in-real-time"></a>实时共享你所看到的信息

你可以与好友和同事实时共享你在 HoloLens 中看见的。 有一些方法可用：

1. 连接到支持 Miracast 的设备或适配器以观看电视。
1. 使用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 在电脑上观看
1. 使用 [Microsoft HoloLens 配套应用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 在电脑上观看。
1. 部署 [Microsoft Dynamics 365 远程协助](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 应用，使第一线工作人员能够将看到内容流式传输给远程专家。 然后，远程专家可以口头指导一线工作人员，或者通过注释他们的世界来指导他们。

> [!NOTE]
> 通过 Windows Device Portal 或 Microsoft HoloLens 配套应用共享你看到的内容需要 HoloLens 进入开发人员 [模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。

### <a name="stream-video-with-miracast"></a>使用 Miracast 流视频

使用"开始"手势转到"开始 **"，** 然后选择 **连接** 图标。 从出现的选取器中，选择要连接到的启用了 Miracast 的设备或适配器。

若要停止共享，请使用"开始"手势并选择突出显示的 **"连接"** 图标。 因为你是流式处理，所以不会将任何内容保存到你的设备。

> [!NOTE]
> Miracast 支持从 [Windows 10 2018 年 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)月更新 (第一代) HoloLens 上启用。

### <a name="real-time-video-with-windows-device-portal"></a>Windows Device Portal 实时视频

由于通过 Windows Device Portal 进行共享需要在 HoloLens 上启用开发人员模式，请按照开发人员文档中的说明设置开发人员模式并导航 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens 配套应用

由于通过 Microsoft HoloLens 配套应用共享需要在 HoloLens 上启用开发人员模式，请按照我们的开发人员文档中的说明设置 [开发人员模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。 然后，下载 [Microsoft HoloLens](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 配套应用，并按照应用内的说明连接到 HoloLens。

使用 HoloLens 设置应用后，从应用的主菜单中**** 选择"实时流"选项。

## <a name="view-your-mixed-reality-photos-and-videos"></a>查看混合现实照片和视频

混合现实照片和视频将保存到设备的"相机照片"中。 可以使用"文件资源管理器"应用浏览 HoloLens 上此文件夹的内容， ("图片">"相机) 。

还可以在预安装在 HoloLens 上的照片应用中查看混合现实照片和视频。 若要固定你的世界的照片，请在"照片"应用中选择它，然后选择"**在混合世界中放置"。** 放置照片后，你可以将其四处移动。

若要在连接到 HoloLens 的电脑上查看和/或保存混合现实照片和视频，可以通过 MTP 使用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) 或电脑 [的文件资源管理器](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>使用文件资源管理器获取图片、视频和文件

与其他移动设备类似，将 HoloLens 连接到电脑以打开文件资源管理器以访问 HoloLens 库 (照片、视频、文档) 轻松转移。 此方法易于使用，不需要使用设备门户或 WI-Fi。

1. 解锁设备。
1. 通过 USB 将设备连接到电脑。
1. 文件资源管理器应在电脑上打开。
1. 导航到：此电脑\\*yourhololensname*\Internal Storage\Pictures\Camera Roll
1. 将所需的任何文件复制到电脑。

提示：
- 如果你未看到任何文件，请确保登录到 HoloLens 以允许访问你的数据。
- 你可以获取其他文件夹中的其他文件，例如 ["文档"文件夹中的](hololens-diagnostic-logs.md#offline-diagnostics) 诊断文件。
- 从电脑上的文件资源管理器中，可以选择设备属性以查看 Windows 全息操作系统版本号 (固件版本) 、设备序列号和电池百分比。
- 如果组织已使用 MDM 禁用 [Connectivity/AllowUSBConnection，](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 将无法连接到设备。

## <a name="share-your-mixed-reality-photos-and-videos"></a>共享混合现实照片和视频

捕获混合现实照片或视频后，将显示预览。 选择 **预览** 上方的共享图标可显示共享助手。 从该位置，可以选择要共享该照片或视频的终点。

通过自动上传混合现实照片和视频，还可以从 OneDrive 共享混合现实照片和视频。 在 HoloLens 上打开 OneDrive 应用，然后使用 [个人 Microsoft](https://account.microsoft.com) 帐户登录（如果尚未登录）。 选择设置**图标**，然后选择"相机**上传"。** 打开"相机上载"。 每次在 HoloLens 上启动应用时，混合现实照片和视频现在都会上传到 OneDrive。

> [!NOTE]
> 只有在使用个人 Microsoft 帐户登录 OneDrive 时，才能在 OneDrive 中启用相机上传。 如果使用工作或学校帐户设置 HoloLens，可以在 OneDrive 应用中添加个人 Microsoft 帐户以启用此功能。

## <a name="limitations-of-mixed-reality-capture"></a>混合现实捕获的限制

- 使用混合现实捕获时，HoloLens 的帧速率将放大到 30 Hz。
- 如果照片/视频相机已被另一个应用程序使用、实时流式传输或系统资源不足，则照片和视频的分辨率可能会降低。

### <a name="maximum-recording-length"></a>最大录音长度

在 HoloLens 2 设备上，在 Windows 全息版之前，设备上录制的 20H2 版本视频的最大长度限制为 5 分钟。

由于客户反馈，我们增加了混合现实捕获 [的录制长度](holographic-photos-and-videos.md)。 默认情况下，混合现实捕获将不再限制为 5 分钟，而是将基于可用磁盘空间计算最大录制长度。 设备将基于可用磁盘空间估计最大视频录制持续时间，最多占总磁盘空间的 80%。

> [!NOTE]
> 如果发生以下情况之一，HoloLens 将使用默认 (5 分钟) 5 分钟：
> - 估计的最大录音持续时间小于默认的 5 分钟。
> - 可用磁盘空间小于总磁盘空间的 20%。

## <a name="default-file-format-and-resolution"></a>默认文件格式和分辨率

### <a name="default-photo-format-and-resolution"></a>默认的照片格式和分辨率

|  设备  |  格式  |  扩展  |  解决方案  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (第一代)  | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>录制的视频格式和分辨率

| 设备 | 格式 | 扩展 | 解决方案 | 速度 | 音频 |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48kHz 立体声 |
| HoloLens (第一代)  |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48kHz 立体声 |
