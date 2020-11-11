---
title: 捕获和管理混合现实照片和视频
description: 了解如何使用 HoloLens 捕获、查看和共享混合现实照片和视频。
keywords: hololens、照片、视频、捕获、mrc、混合现实捕获、照片、相机、流、livestream、演示
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
ms.openlocfilehash: 452164caaad09f2caecf7c4a51cda6242d805d7f
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163112"
---
# 创建混合现实照片和视频

HoloLens 为用户提供了与数字世界混合现实的体验。  混合现实捕获 (MRC) 使你可以将该体验捕获为照片或视频，或与其他人实时共享你所看到的内容。

混合现实捕获使用第一人的观点，以便其他人可以看到您看到的全息影像。 对于第三人的观点，请使用 [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。 Spectator 视图对演示尤其有用。

虽然在朋友和同事之间共享视频很有趣，但视频还有助于教授其他人使用应用或与应用和体验相关的问题。

> [!NOTE]
> 如果无法启动混合现实捕获体验，并且你的 HoloLens 是工作设备，请与你的系统管理员联系。 可通过公司政策限制对相机的访问。

## 捕获混合现实照片

有多种方法可以在 HoloLens 上拍摄照片混合现实;你可以使用硬件按钮、语音或 "开始" 菜单。

### 拍摄照片的硬件按钮

若要拍摄当前视图的快速照片，请同时按下 "音量" 和 "音量" 按钮。  这有点类似于版本屏幕截图或打印屏幕的 HoloLens 版本。

- [HoloLens 2 上的按钮位置](hololens2-hardware.md)
- [HoloLens 上的按钮位置 (第一代) ](hololens1-hardware.md#hololens-components)

> [!NOTE]
> 将**音量****按下并按下音量**按钮三秒钟，将开始录制视频，而不是拍摄照片。 若要停止录制，请同时点击 "调 **高音量** " 和 "调 **低音量** " 按钮。

### 用于拍摄照片的语音命令

在 HoloLens 2、版本 2004 (及更高版本) 中，说： "拍摄照片"。

在 HoloLens (第一代) 或 HoloLens 2 版本1903，例如： "你好小娜，请拍摄照片"。

### "开始" 菜单，拍照

使用 "开始" 手势转到 " **开始**"，然后选择 **照相机** 图标。

将你的头指向你想要捕获的内容，然后 [点击](hololens2-basic-usage.md#touch-holograms-near-you) "拍摄照片"。 您可以继续空中点击并捕获其他照片。 你捕获的所有照片将保存到你的设备。

再次使用 "开始" 手势来结束照片捕获。  

## 捕获混合现实视频

有多种方法可在 HoloLens 上录制混合现实的视频;你可以使用硬件按钮、语音或 "开始" 菜单。

### 用于录制视频的硬件按钮

录制视频最快的方法是同时按住 **音量** 和调 **低** 音量按钮，直到出现三秒钟倒计时。 若要停止录制，请同时点击两个按钮。

> [!NOTE]
> 同时快速按 **音量** 和 **按下音量** 按钮将拍摄照片，而不是录制视频。

### 录制视频的语音

在 HoloLens 2、版本 2004 (和更高版本) ，说： "开始录制"。 若要停止录制，请说 "停止录制"。

在 HoloLens (第一代) 或 HoloLens 2 版本1903，例如： "你好小娜，开始录制。" 若要停止录制，请说 "你好小娜，停止录制"。

### 用于录制视频的 "开始" 菜单

使用 "开始" 手势转到 " **开始**"，然后选择 " **视频** " 图标。 将你的头指向你想要捕获的内容，然后 [点击](hololens2-basic-usage.md#touch-holograms-near-you) "开始录制"。 将出现三次倒计时，录制将开始。

若要停止录制，请使用 "开始" 手势并选择突出显示的 **视频** 图标。 视频将保存到您的设备。

> [!NOTE]
> **仅适用于 HoloLens (第一代) **  
> [Windows 10 月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)将更改 "开始手势" 和 "Windows" 按钮在 HoloLens (第一代) 上的行为。 更新之前，"开始手势" 或 "Windows" 按钮将停止视频录制。 但是，更新后，"开始" 手势或 Windows 按钮将打开 " **开始** " 菜单 (或 " **快速操作" 菜单** （如果你位于沉浸式应用) 中），可从中选择突出显示的 **视频** 图标以停止录制。

## 共享您实时看到的内容

您可以实时与朋友和同事共享您的 HoloLens。 可以使用以下几种方法：

1. 连接到支持 Miracast 的设备或适配器以在电视上观看。
1. 使用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 在电脑上观看
1. 使用 [Microsoft HoloLens 配套应用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 在电脑上观看。
1. 部署 [Microsoft Dynamics 365 远程协助](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 应用，该应用使前端工作人员能够流式处理他们对远程专家所看到的内容。 然后，远程专家可以通过自己的口头或在世界上进行批注来指导他们。

> [!NOTE]
> 通过 Windows Device Portal 或 Microsoft HoloLens 附属应用共享所看到的内容要求你的 HoloLens 处于 [开发人员模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。

### 通过 Miracast 流处理视频

使用 "开始" 手势转到 " **开始**"，然后选择 " **连接** " 图标。 从出现的选取器中，选择要连接到的已启用 Miracast 的设备或适配器。

若要停止共享，请使用 "开始" 手势并选择突出显示的 " **连接** " 图标。 由于你正在进行流式处理，因此不会将任何内容保存到你的设备。

> [!NOTE]
> 在 HoloLens (第一代) 上启用了 Miracast 支持，从 [2018 年10月的更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)开始。

### Windows Device Portal 的实时视频

由于通过 Windows Device Portal 进行共享需要在 HoloLens 上启用开发人员模式，请按照我们的开发人员文档中的说明 [设置开发人员模式和导航 Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。

### Microsoft HoloLens 辅助应用

由于通过 Microsoft HoloLens 附属应用共享需要在 HoloLens 上启用开发人员模式，请按照我们的开发人员文档中的说明 [设置开发人员模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。 然后，下载 [Microsoft HoloLens 配套应用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) ，并按照应用中的说明连接到 HoloLens。

将应用与 HoloLens 一起设置后，从应用的主菜单中选择 " **实时流** " 选项。

## 查看混合现实照片和视频

混合现实照片和视频将保存到设备的 "相机翻转"。 你可以通过文件资源管理器应用在你的 HoloLens 上浏览此文件夹的内容， (导航到 > 相机辊) 的图片。

你还可以在预装在 HoloLens 上的照片应用中查看混合现实照片和视频。 若要在世界上固定照片，请在 "照片" 应用中将其选中，然后选择 " **混合世界**"。 在放置后，您可以在世界各地移动照片。

若要在连接到 HoloLens 的电脑上查看和/或保存混合现实照片和视频，可以通过 MTP 使用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) 或 [电脑的文件资源管理器](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。

### 使用文件资源管理器获取图片、视频和文件

与其他移动设备类似，将你的 HoloLens 连接到电脑以调出文件资源管理器，以便访问你的 HoloLens 库 (照片、视频、文档) 以便轻松传输。 此方法易于使用，并且不需要使用 device portal 或 Wi-fi。

1. 解锁设备。
1. 通过 USB 将设备连接到电脑。
1. 文件资源管理器应在你的电脑上打开。
1. 导航到：此 PC\\*yourhololensname*\Internal Storage\Pictures\Camera 滚
1. 将所需的任何文件复制到 PC。

提示：
- 如果您看不到任何文件，请确保您登录到 HoloLens 以允许访问您的数据。
- 可以获取其他文件夹中的其他文件，例如 "文档" 文件夹中的 " [诊断" 文件](hololens-diagnostic-logs.md#offline-diagnostics) 。
- 在电脑上的文件资源管理器中，你可以选择 "设备属性" 以查看 Windows 全息 OS 版本号 (固件版本) 和设备序列号和电池百分比。
- 如果你的组织已使用 MDM 禁用 [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ，你将无法连接到你的设备。

## 分享您的混合现实照片和视频

捕获混合现实照片或视频后，将显示预览。 选择预览上方的 " **共享** " 图标以调出 "共享助理"。 在此处，你可以选择要在其中共享照片或视频的终结点。

您也可以通过自动上载您的混合现实照片和视频，从 OneDrive 共享混合现实照片和视频。 在 HoloLens 上打开 OneDrive 应用，并使用个人 [Microsoft 帐户](https://account.microsoft.com) 登录（如果尚未登录）。 选择 " **设置** " 图标，然后选择 " **照相机上载**"。 打开相机上传。 现在，你的混合现实照片和视频将在 HoloLens 上启动应用时上载到 OneDrive。

> [!NOTE]
> 如果你已使用个人 Microsoft 帐户登录到 OneDrive，则只能在 OneDrive 中启用相机上传。 如果您使用工作或学校帐户设置 HoloLens，则可以在 OneDrive 应用中添加个人 Microsoft 帐户以启用此功能。

## 混合现实捕获的限制

- 使用混合现实捕获时，HoloLens 的帧频将减半到 30 Hz。
- 如果照片/视频相机已由另一个应用程序、实时流处理或系统资源不足，可能会降低照片和视频的分辨率。

### 最大录制长度

在 Windows 全息版上录制的版本20H2 视频之前，在设备上录制的版本视频的最大长度限制为5分钟。

由于客户反馈，我们增加了 [混合现实捕获](holographic-photos-and-videos.md)的录制长度。 默认情况下，混合现实捕获将不再限制为5分钟，而是将根据可用磁盘空间计算最大录制长度。 设备将根据可用磁盘空间达到总磁盘空间的80%，估计最大视频录制持续时间。

> [!NOTE]
> 如果出现以下情况之一，则 HoloLens 将使用默认视频录制长度 (5 分钟) ：
> - 估计的最大录制持续时间小于默认的5分钟。
> - 可用磁盘空间小于总磁盘空间的20%。

## 默认文件格式和分辨率

### 默认照片格式和分辨率

|  设备  |  格式  |  扩展  |  分辨率  |
|----------|----------|----------|----------|
| HoloLens 2 | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 3904x2196px |
| HoloLens (第一代)  | [JPEG](https://en.wikipedia.org/wiki/JPEG) | .jpg | 1408x792px |

### 录制的视频格式和分辨率

| 设备 | 格式 | 扩展 | 分辨率 | 度 | 音频 |
|----------|----------|----------|----------|----------|----------|
| HoloLens 2 | [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1920x1080px | 30fps | 48kHz 立体声 |
| HoloLens (第一代)  |  [MPEG-4](https://en.wikipedia.org/wiki/MPEG-4) | .mp4 | 1216x684px | 24fps | 48kHz 立体声 |
