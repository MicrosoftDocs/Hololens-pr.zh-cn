---
title: 捕获、录制和共享混合现实照片和视频
description: 了解如何使用混合现实设备捕获、录制、查看和HoloLens混合现实照片和视频。 了解如何通过共享或Miracast共享。
keywords: hololens， 照片， 视频， 捕获， mrc， 混合现实捕获， 照片， 相机， miracast， 流， 实时流， 演示， 录制
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
ms.openlocfilehash: daced6fab65f779b7bd670bf1275f99ae5311d3f
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635953"
---
# <a name="create-mixed-reality-photos-and-videos"></a>创建混合现实照片和视频

HoloLens为用户提供将现实世界与数字世界混合的体验。  混合现实捕获 (MRC) 使你能够将体验捕获为照片或视频，或与他人实时共享你所看到的内容。

混合现实捕获使用第一人称视角，以便其他人可以在看到全息影像时看到全息影像。 对于第三人称，请使用 [旁观视图](/windows/mixed-reality/spectator-view)。 旁观视图对于演示特别有用。

虽然在朋友和同事之间共享视频很有趣，但视频还有助于指导其他人使用应用或与应用和体验交流问题。

> [!NOTE]
> 如果无法启动混合现实捕获体验，并且你的HoloLens是工作设备，请与系统管理员联系。 可以通过公司策略限制对相机的访问。

## <a name="capture-a-mixed-reality-photo"></a>捕获混合现实照片

有几种方法可以拍摄混合现实的照片，HoloLens;可以使用硬件按钮、语音或"开始"菜单。

### <a name="hardware-buttons-to-take-photos"></a>用于拍摄照片的硬件按钮

若要快速拍摄当前视图的照片，请同时按音量调高和音量降低按钮。  这有点与屏幕截图HoloLens打印屏幕的版本类似。

- [按钮位置HoloLens 2](hololens2-hardware.md)
- [第一代HoloLens (上的按钮) ](hololens1-hardware.md#hololens-components)

> [!NOTE]
> 将 **音量调高** 和 **音量** 降低按钮按住三秒钟会开始录制视频，而不是拍照。 若要停止录制，请 **同时点击音量** 增加 **和音量** 降低按钮。

### <a name="voice-commands-to-take-photos"></a>用于拍摄照片的语音命令

在 HoloLens 2，版本 2004 (及更高版本) ，例如："拍照"。

在HoloLens (第一代) 或 HoloLens 2 版本 1903 上，说："你好，Cortana，拍照。"

### <a name="start-menu-to-take-photos"></a>"开始"菜单照片

使用"开始"手势转到" **开始"，** 然后选择" **相机"** 图标。

将头部指向要捕获的方向，然后通过敲击来拍摄照片[](hololens2-basic-usage.md#touch-holograms-near-you)。 可以继续进行空敲击并捕获其他照片。 捕获的任何照片都将保存到设备。

再次使用"开始"手势结束照片捕获。  

## <a name="capture-a-mixed-reality-video"></a>捕获混合现实视频

有几种方法可以录制有关混合现实的视频，HoloLens;可以使用硬件按钮、语音或"开始"菜单。

### <a name="hardware-buttons-to-record-videos"></a>用于录制视频的硬件按钮

录制视频的最快方法就是同时按住音量和音量降低按钮，直到开始倒计时 3 秒。 若要停止录制，请同时点击这两个按钮。

> [!NOTE]
> 同时快速 **向上按下** 音量和音量降低按钮会拍摄照片，而不是录制视频。

### <a name="voice-to-record-videos"></a>录制视频的语音

在 HoloLens 2，版本 2004 (及更高版本) ，例如："开始录制"。 若要停止录制，请说"停止录制"。

在HoloLens (第一代) 或HoloLens 2版本 1903 上，说："你好，Cortana，开始录制。" 若要停止录制，请说"你好Cortana，停止录制。"

### <a name="start-menu-to-record-videos"></a>"开始"菜单录制视频

使用"开始"手势转到" **开始"，** 然后选择" **视频"** 图标。 将头部指向要捕获的方向，然后按 [Air tap](hololens2-basic-usage.md#touch-holograms-near-you) 开始录制。 将进行三秒倒计时，记录将开始。

若要停止录制，请使用"开始"手势并选择突出显示 **的视频** 图标。 视频将保存到设备。

> [!NOTE]
> **仅适用于第HoloLens (代)**  
> 此[Windows 10 2018 年 10 月更新](/windows/mixed-reality/release-notes-october-2018)更改"开始"手势和Windows按钮在HoloLens (第一代) 。 更新之前，"开始"手势Windows按钮将停止视频录制。 但是，更新后，"开始手势"或"Windows"按钮会打开"开始"菜单 (或快速操作菜单（如果正在沉浸式应用) 中，可以从中选择突出显示的视频图标来停止录制。 

## <a name="share-what-you-see-in-real-time"></a>实时共享看到

可以与朋友和同事实时HoloLens共享你在活动时看到什么。 有一些方法可用：

1. 连接到启用了Miracast或适配器的设备或适配器，以在电视上观看。
1. 使用[Windows 设备门户](/windows/mixed-reality/using-the-windows-device-portal)在电脑上观看
1. 使用[Microsoft HoloLens应用在](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)电脑上观看。
1. 部署[Microsoft Dynamics 365 Remote Assist应用](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)，使一线工作人员能够将看到内容流式传输给远程专家。 然后，远程专家可以指导一线工作人员进行言语或批注。

> [!NOTE]
> 通过应用或Windows 设备门户应用Microsoft HoloLens看到的信息需要HoloLens开发人员[模式](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。

### <a name="stream-video-with-miracast"></a>使用流式传输Miracast

使用"开始"手势转到"开始 **"，****然后选择连接图标**。 从出现的选取器中，Miracast连接到的已启用设备或适配器的设备。

若要停止共享，请使用"开始"手势并选择突出显示的 **连接图标。** 由于已流式传输，因此不会将任何内容保存到设备。

> [!NOTE]
> Miracast第一代 HoloLens (上启用了) 支持，从 Windows 10 2018 年 10 月更新[开始](/windows/mixed-reality/release-notes-october-2018)。

### <a name="real-time-video-with-windows-device-portal"></a>实时视频与Windows 设备门户

由于通过 Windows 设备门户 共享需要在 HoloLens 上启用开发人员模式，因此请按照开发人员文档中的说明设置开发人员模式并导航到[Windows 设备门户。](/windows/mixed-reality/using-the-windows-device-portal)

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens配套应用

由于通过Microsoft HoloLens应用共享需要在 HoloLens 上启用开发人员模式，因此请按照开发人员文档中的说明设置[开发人员模式](/windows/mixed-reality/using-the-windows-device-portal)。 然后，下载[Microsoft HoloLens应用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)，并按照应用中的说明连接到HoloLens。

使用应用设置应用后HoloLens，从应用的主菜单中选择"实时流"选项。

## <a name="view-your-mixed-reality-photos-and-videos"></a>查看混合现实照片和视频

混合现实照片和视频将保存到设备的"相机照片"中。 可以使用 文件资源管理器 应用浏览 HoloLens 上此文件夹的内容 (导航到"照片>**相机) "** 。

还可以在照片应用中查看混合现实照片和视频，该应用预安装在 HoloLens。 若要将照片固定在你的世界，请在"照片"应用中选择它，然后选择"**将照片放在混合世界"。** 放置照片后，可以将其移动到你的世界。

若要在连接到 HoloLens 的电脑上查看和/或保存混合现实HoloLens，可以通过 MTP Windows 设备门户或[电脑文件资源管理器设备](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。 [](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>使用文件资源管理器获取图片、视频和文件

与其他移动设备类似，将 HoloLens 连接到电脑文件资源管理器以访问 HoloLens 库 (照片、视频、文档) 轻松传输。 此方法易于使用，不需要使用设备门户或 Wi-Fi。

1. 解锁设备。
1. 连接 USB 将设备连接到电脑。
1. 文件资源管理器应在电脑上打开。
1. 导航到：此电脑 \\ *yourhololensname*\Internal 存储\Pictures\Camera Roll
1. 将所需的任何文件复制到电脑。

提示：
- 如果看不到任何文件，请确保登录到HoloLens以启用对数据的访问。
- 可以从其他文件夹中获取其他文件，例如 Documents [文件夹中的](hololens-diagnostic-logs.md#offline-diagnostics) 诊断文件。
- 在文件资源管理器，可以选择"设备属性"，Windows全息 OS 版本号 (固件版本) 、设备序列号和电池百分比。
- 如果组织已使用 MDM 禁用 [连接/AllowUSBConnection，](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 则将无法连接到设备。

## <a name="share-your-mixed-reality-photos-and-videos"></a>共享混合现实照片和视频

在全息[Windows版本 21H1](hololens-release-notes.md#windows-holographic-version-21h1)之前，捕获混合现实照片或视频后，将显示预览。 选择 **预览上方** 的"共享"图标，打开共享助手。 可以在那里选择要共享该照片或视频的终点。

在Windows全息版 21H1 中，捕获混合现实照片或视频后，将显示预览。 选择 **预览上方** 的"共享"图标，打开共享助手。 可以在其中选择要共享该照片 (视频OneDrive邮件、) 等的终点。 还可通过访问 "HoloLens "-设置""共享体验"，>**设备与>共享**。 有关详细信息，请阅读 在 中[与附近的设备共享Windows 10。](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

> [!TIP] 
> 还可通过自动上传混合现实照片OneDrive共享混合现实照片和视频。 打开 OneDrive 应用HoloLens，然后使用个人Microsoft 帐户登录（如果尚未登录 **）。 [](https://account.microsoft.com)** 选择 **"设置** 图标，然后选择"**相机上传"。** 打开"相机上传"。 现在，每次在 OneDrive 上启动应用时，混合现实照片和视频都将上传到HoloLens。

> [!NOTE]
> 如果已使用个人OneDrive登录到 OneDrive，Microsoft 帐户。 如果使用工作HoloLens帐户设置帐户，可以在 Microsoft 帐户 应用中添加OneDrive个人帐户以启用此功能。

## <a name="limitations-of-mixed-reality-capture"></a>混合现实捕获的限制

- 使用混合现实捕获时，HoloLens帧速率将缩小到 30 Hz。
- 如果另一个应用程序已在使用照片/视频相机、实时流式处理或系统资源不足，则照片和视频的分辨率可能会降低。

### <a name="maximum-recording-length"></a>最大录制长度

在 HoloLens 2 Holographic 版本 20H2 之前Windows设备上，设备上录制的视频的最大长度限制为 5 分钟。

根据客户反馈，我们增加了混合现实捕获 [的录制长度](holographic-photos-and-videos.md)。 默认情况下，混合现实捕获将不再限制为 5 分钟，而是根据可用磁盘空间计算最大录制长度。 设备将基于可用磁盘空间估计最大视频录制持续时间，最多占总磁盘空间的 80%。

> [!NOTE]
> 如果HoloLens以下情况之一， (视频录制长度) 5 分钟：
> - 估计的最大录制持续时间小于默认的 5 分钟。
> - 可用磁盘空间小于总磁盘空间的 20%。

## <a name="default-file-format-and-resolution"></a>默认文件格式和分辨率

### <a name="default-photo-format-and-resolution"></a>默认照片格式和分辨率

|  设备  |  格式  |  分机  |  解决方法  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens（第 1 代） | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### <a name="recorded-video-format-and-resolution"></a>录制的视频格式和分辨率

| 设备 | 格式 | 分机 | 解决方法 | Speed | 音频 |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48kHz 立体声 |
| HoloLens（第 1 代） |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48kHz 立体声 |
