---
title: 捕获、记录和共享混合现实照片和视频
description: 了解如何使用 HoloLens 混合现实设备来捕获、记录和查看和混合现实照片和视频。 了解如何通过 Miracast 或收集的文件进行共享。
keywords: hololens，照片，视频，捕获，mrc，混合现实捕获，照片，照相机，miracast，流，livestream，演示，记录
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032087"
---
# <a name="create-mixed-reality-photos-and-videos"></a>创建混合现实照片和视频

HoloLens 为用户提供了与数字世界混合现实世界的经验。  混合现实捕获 (MRC) 使你可以将该体验作为照片或视频进行捕获，或与他人实时共享你所看到的内容。

混合现实捕获使用第一个用户的观点，使其他人可以看到你看到的全息影像。 对于第三人的观点，请使用 [spectator 视图](/windows/mixed-reality/spectator-view)。 Spectator 视图对于演示特别有用。

虽然在朋友和同事之间共享视频非常有趣，但视频还有助于教授其他人使用应用或与应用和体验相关的问题。

> [!NOTE]
> 如果无法启动混合现实捕获体验并且 HoloLens 是工作设备，请与系统管理员联系。 可以通过公司政策限制对相机的访问。

## <a name="capture-a-mixed-reality-photo"></a>捕获混合现实照片

有多种方法可在 HoloLens 上利用混合现实照片;你可以使用硬件按钮、语音或 "开始"菜单。

### <a name="hardware-buttons-to-take-photos"></a>拍摄照片的硬件按钮

若要快速查看当前视图，请同时按下的 "音量" 和 "音量" 按钮。  这有点类似于屏幕截图或打印屏幕的 HoloLens 版本。

- [HoloLens 2 上的按钮位置](hololens2-hardware.md)
- [第一代 (HoloLens 上的按钮位置) ](hololens1-hardware.md#hololens-components)

> [!NOTE]
> 将 " **音量朝上** " 和 " **音量减小** " 按钮设置为三秒将开始录制视频，而不是拍摄照片。 若要停止录制，请同时点击 " **音量调高** " 和 "调 **低音量** " 按钮。

### <a name="voice-commands-to-take-photos"></a>拍摄照片的语音命令

在 HoloLens 2 上，版本 2004 (和更高版本) ，例如： "拍摄照片"。

在 HoloLens (第一代) 或 HoloLens 2 版本1903，例如： "你好 Cortana，拍摄照片"。

### <a name="start-menu-to-take-photos"></a>拍摄照片的 "开始"菜单

使用 "开始" 手势中转到 " **开始**"，然后选择 **相机** 图标。

将你的头指向你要捕获的内容，然后单击 " [空中](hololens2-basic-usage.md#touch-holograms-near-you) " 拍摄照片。 你可以继续空中点击并捕获其他照片。 您捕获的任何照片都将保存到您的设备中。

再次使用开始手势来结束照片捕获。  

## <a name="capture-a-mixed-reality-video"></a>捕获混合现实视频

有多种方法可在 HoloLens 上记录 mixed reality 的视频;你可以使用硬件按钮、语音或 "开始"菜单。

### <a name="hardware-buttons-to-record-videos"></a>用于录制视频的硬件按钮

录制视频最快捷的方法是，同时按住 " **音量调高** " 和 "调 **低** 音量" 按钮，直到开始进行三秒钟倒计时。 若要停止录制，请同时点击两个按钮。

> [!NOTE]
> 同时快速按下 " **音量调高** " 和 " **音量减小** " 按钮会拍摄照片，而不是录制视频。

### <a name="voice-to-record-videos"></a>用于录制视频的语音

在 HoloLens 2 上，版本 2004 (和更高版本) ，例如： "开始记录"。 若要停止录制，请说 "停止录制"。

在 HoloLens (第一代) 或 HoloLens 2 版本1903，例如： "你好 Cortana，开始录制"。 若要停止录制，请说 "你好 Cortana，停止录制"。

### <a name="start-menu-to-record-videos"></a>"开始"菜单录制视频

使用 "开始" 手势中转到 " **开始**"，然后选择 **视频** 图标。 将你的头指向你要捕获的内容，然后 [点击](hololens2-basic-usage.md#touch-holograms-near-you) 即可开始录制。 将有三秒钟倒计时，并且记录将开始。

若要停止录制，请使用 "开始手势" 并选择突出显示的 **视频** 图标。 视频将保存到你的设备。

> [!NOTE]
> **仅适用于 HoloLens (第一代)**  
> [Windows 10 2018 年10月更新](/windows/mixed-reality/release-notes-october-2018)将更改开始手势和 Windows 按钮在 HoloLens (第一代) 上的行为方式。 在更新之前，开始手势或 Windows 按钮将停止视频录制。 但在更新后，如果你在沉浸式应用程序) 中，则 "开始手势" 或 "Windows" 按钮将打开 "**开始**" 菜单 (或 "**快速操作" 菜单**，你可以从中选择突出显示的 **视频** 图标以停止录制。

## <a name="share-what-you-see-in-real-time"></a>共享你的实时显示内容

你可以实时共享你在 HoloLens 中看到的内容。 有几种方法可用：

1. 连接到已启用 Miracast 的设备或适配器以在电视上观看。
1. 使用[Windows 设备门户](/windows/mixed-reality/using-the-windows-device-portal)观看电脑
1. 使用[Microsoft HoloLens 辅助应用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)在电脑上观看。
1. 部署[Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)应用，使前端工作人员能够流式传输他们对远程专家所见的内容。 然后，该远程专家就可以指导口头方式传达，或通过在其世界中进行注释来指导。

> [!NOTE]
> 通过 Windows 设备门户或 Microsoft HoloLens 辅助应用共享看到的内容，你的 HoloLens 需要处于[开发人员模式](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。

### <a name="stream-video-with-miracast"></a>与 Miracast 传输视频

使用 "开始" 手势中转到 "**开始**"，然后选择 "**连接**" 图标。 从显示的选取器中，选择要连接到 Miracast 的设备或适配器。

若要停止共享，请使用 "开始" 手势，然后选择突出显示的 **连接** 图标。 由于你正在进行流式处理，因此不会将任何内容保存到你的设备。

> [!NOTE]
> HoloLens (第一代) 从[Windows 10 2018 年10月更新](/windows/mixed-reality/release-notes-october-2018)开始启用 Miracast 支持。

### <a name="real-time-video-with-windows-device-portal"></a>Windows 设备门户的实时视频

由于通过 Windows 设备门户进行共享需要在 HoloLens 上启用开发人员模式，请按照开发人员文档中的说明[设置开发人员模式并导航 Windows 设备门户](/windows/mixed-reality/using-the-windows-device-portal)。

### <a name="microsoft-hololens-companion-app"></a>Microsoft HoloLens 辅助应用

由于通过 Microsoft HoloLens 辅助应用共享需要在 HoloLens 上启用开发人员模式，请按照开发人员文档中的说明[设置开发人员模式](/windows/mixed-reality/using-the-windows-device-portal)。 然后，下载[Microsoft HoloLens 配套应用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)，并按照应用中的说明连接到 HoloLens。

在 HoloLens 中设置应用后，从应用的主菜单中选择 "**实时流**" 选项。

## <a name="view-your-mixed-reality-photos-and-videos"></a>查看混合现实照片和视频

混合现实照片和视频保存到设备的 "照相机"。 您可以通过文件资源管理器应用在 HoloLens 上浏览此文件夹的内容， (导航到 "**相机滚动 > 的图片**") 。

你还可以在 HoloLens 上预先安装的照片应用中查看混合现实照片和视频。 若要在你的世界中固定照片，请在照片应用中选择它，然后选择 " **在混合世界中放置"**。 放置照片后，可以将其移动到世界各地。

若要在连接到 HoloLens 的 pc 上查看和/或保存混合现实照片和视频，可以通过 MTP 使用[Windows 设备门户](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)或[电脑的文件资源管理器](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a>使用文件资源管理器获取图片、视频和文件

与其他移动设备类似，将 HoloLens 连接到电脑，使文件资源管理器能够访问 HoloLens 库 (照片、视频、文档) 以便于轻松传输。 此方法很容易使用，不需要使用设备门户或 Wi-fi。

1. 锁定设备。
1. 通过 USB 连接设备到 PC。
1. 文件资源管理器应在您的 PC 上打开。
1. 导航至：此电脑 \\ *yourhololensname*\Internal 存储 \Pictures\Camera 卷筒
1. 将需要的任何文件复制到 PC。

提示：
- 如果看不到任何文件，请确保登录到 HoloLens 以启用对数据的访问。
- 可以获取其他文件夹中的其他文件，如 "文档" 文件夹中的 [诊断文件](hololens-diagnostic-logs.md#offline-diagnostics) 。
- 在电脑上的文件资源管理器中，可以选择 "设备属性" 以查看 Windows 全息版 OS 版本号 (固件版本) 、设备序列号和电池百分比。
- 如果你的组织已使用 MDM 禁用 [连接/AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ，则你将无法连接到你的设备。

## <a name="share-your-mixed-reality-photos-and-videos"></a>共享混合现实照片和视频

在捕获混合现实照片或视频后[Windows 全息版本 21H1](hololens-release-notes.md#windows-holographic-version-21h1)之前，会显示预览。 选择预览上方的 **共享** 图标以打开共享助手。 你可以从此处选择要共享该照片或视频的终结点。

在捕获混合现实照片或视频后，使用 Windows 全息版21H1，将显示预览。 选择预览上方的 **共享** 图标以打开共享助手。 在该处，你可以选择要将该照片或视频共享到 )  (Mail、OneDrive 等的终点。 你还可以通过转到 **设置 > 系统 > 共享体验** 来使你的 HoloLens 与附近的设备共享。 有关更多详细信息，请阅读[在 Windows 10 中与附近设备共享内容](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)。

> [!TIP] 
> 你还可以通过自动上传混合现实照片和视频，从 OneDrive 共享混合现实照片和视频。 打开 HoloLens 上的 OneDrive 应用，并使用 **个人 [Microsoft 帐户](https://account.microsoft.com)** 登录（如果尚未登录）。 选择 **设置** 图标，然后选择 "**相机上传**"。 打开相机上传。 当你在 HoloLens 上启动应用时，你的混合现实照片和视频现在将上传到 OneDrive。

> [!NOTE]
> 仅当使用个人 Microsoft 帐户登录到 OneDrive 时，才能在 OneDrive 中启用相机上传。 如果使用工作或学校帐户设置 HoloLens，则可以在 OneDrive 应用中添加个人 Microsoft 帐户以启用此功能。

## <a name="limitations-of-mixed-reality-capture"></a>混合现实捕获的限制

- 使用混合现实捕获时，HoloLens 的帧速率将减半到 30 Hz。
- 如果照片/视频相机已被其他应用程序使用、实时流式处理或系统资源不足，则可能会降低照片和视频的分辨率。

### <a name="maximum-recording-length"></a>最大记录长度

在 Windows 全息版20H2 之前 HoloLens 2 设备上，在设备上录制的视频的最大长度限制为五分钟。

由于客户反馈，我们已增加 [混合现实捕获](holographic-photos-and-videos.md)的记录长度。 默认情况下，混合现实捕获将不再限制为5分钟，但会根据可用磁盘空间来计算最大记录长度。 该设备将根据可用磁盘空间（最大为总磁盘空间的80%）估算最大视频录制持续时间。

> [!NOTE]
> 如果发生以下情况之一，HoloLens 将使用默认视频录制长度 (5 分钟) ：
> - 预计的最大记录持续时间小于默认的5分钟。
> - 可用磁盘空间小于总磁盘空间的20%。

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
