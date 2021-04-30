---
title: 疑难解答
description: 随时了解 HoloLens 设备问题和故障排除方法的最常见解决方案。
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
keywords: 问题、错误、故障排除、修复、帮助、支持、HoloLens
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308427"
---
# <a name="troubleshooting"></a>疑难解答

本文介绍如何解决几个常见的 HoloLens 问题。

## <a name="my-hololens-is-unresponsive-or-wont-start"></a>HoloLens 无响应或不启动

如果 HoloLens 无法启动：

- 如果电源按钮旁的 Led 指示灯未亮起，或只有一个 LED 闪烁，则您可能需要为 [HoloLens 充电。](hololens-recovery.md#charge-the-device)
- 如果在按下电源按钮时 Led 亮起，但在显示器上看不到任何内容， [执行硬重置设备](hololens-recovery.md#hard-reset-procedure)。

如果 HoloLens 已冻结或无响应：

- 按下电源按钮关闭 HoloLens，直到所有5个 Led 关闭，或在 Led 无响应时为15秒。 若要开始 HoloLens，请再次按下 "电源" 按钮。

如果这些步骤不起作用，可以尝试 [恢复 hololens 2 设备](hololens-recovery.md) 或 [hololens (第一代) 设备。](hololens1-recovery.md)

## <a name="holograms-dont-look-good"></a>全息影像看起来不好

如果全息影像不稳定、jumpy 或看起来不正确，请尝试执行以下操作：

- 清理 HoloLens 前面的设备面板和传感器栏。
- 提高房间中的光线。
- 浏览并查看您的环境，以便 HoloLens 可以更完整地扫描它们。
- 校准你的 HoloLens。 中转到 "**设置**" "系统" "  >    >  **实用工具**"。 在 **校准** 下，选择 " **打开校准**"。
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a>找出全息影像不稳定或不正确的问题
 
1. 请记录并记录问题的 [混合现实](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 。 此视频稍后可通过反馈中心作为附加文件上传。  
1. 通过 "**设置**" 应用启用整个遥测 >**隐私**  ->  **诊断 & 反馈**，并在 **可选诊断数据** 下，确保将切换设置为 **"开**"
1. 通过更新到最新的 [Windows 全息操作系统， (20H2 或更高) ， ](hololens-release-notes.md#windows-holographic-version-20h2)获取最新的全息图缩放和稳定性修复。 更新后，请执行以下操作：
    1. 通过 "**设置**" "应用" "应用" "> **>"**"" "" "" "" 中删除所有全息  ->   
    1. 戴上 HoloLens 并浏览房间并观看空间中的所有区域和图面，从而创建空间的新地图。 为2-3 分钟执行此操作。
    1. 执行 IPD 校准。 中转到 "**设置**" "系统" "  >    >  **实用工具**"。 在 **校准** 下，选择 " **打开校准**"。
    1. 重新测试方案，并查看它是否仍然存在。
1. 如果更新不能解决问题，请提交 [反馈中心问题](hololens-feedback.md)。 填写反馈后，可以使用 " **共享** " 按钮，创建一个易于共享的链接，以便在联系支持人员时发送。

## <a name="hololens-doesnt-respond-to-hand-input"></a>HoloLens 未响应手写输入

若要确保 HoloLens 能看到你的手，你需要将它们保留在手势帧中。  混合现实主页提供反馈，让你知道何时跟踪你的手。  不同版本的 HoloLens 的反馈有所不同：
- 在 HoloLens (第一代) 上，注视光标从点变为圆圈
- 在 HoloLens 2 上，当您的手接近于一手指时，会出现一个 "

许多沉浸式应用都遵循类似于混合现实主页的输入模式。  详细了解如何在 [hololens (第一代) ](hololens1-basic-usage.md#use-hololens-with-your-hands) 和 [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)上使用手动输入。

如果戴上手套，请注意，某些类型的手套不适用于手动跟踪。  常见的例子是黑色橡胶手套，这通常会吸收红外线，而不是由深度相机选取。  如果你的工作涉及橡胶手套，我们建议尝试使用较浅的颜色，如蓝色或灰色。  另一个示例是大型 baggy 手套，这种情况通常会使手不会遮盖。 为了获得最佳效果，我们建议使用以窗体为形式的手套。

如果面板具有指纹或无污迹，请使用 HoloLens 附带的 microfiber 清洁抹布来轻轻地清理面板。

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a>HoloLens 未响应语音命令

如果 Cortana 没有响应语音命令，请确保 Cortana 已打开。 在 "所有应用" 列表中，选择 " **Cortana**  >  **Menu**  >  **笔记本**  >  **设置**" 进行更改。 若要详细了解你可以说的内容，请参阅 [将你的语音与 HoloLens 配合使用](hololens-cortana.md)。

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a>我无法放置全息影像或查看以前放置的全息影像

如果 HoloLens 无法映射或加载空间，则它将进入限制模式，你将无法放置全息影像或查看已放置的全息影像。 可以尝试以下操作：

- 请确保环境中有足够的光线，以便 HoloLens 能够查看和映射空间。
- 请确保已连接到 Wi-Fi 网络。 如果你未连接到 Wi-fi，则 HoloLens 无法识别并加载已知的空间。
- 如果需要创建新空间，请连接到 Wi-fi，然后重启 HoloLens。
- 若要查看正确的空间是否处于活动状态，或要手动加载空间，请参阅 **设置**  >  **系统**  >  **空间**。
- 如果加载了正确的空间并且仍有问题，则空间可能已损坏。 若要解决此问题，请选择该空间，然后选择 " **删除**"。 删除空间后，HoloLens 会开始映射你的环境并创建新空间。

## <a name="my-hololens-cant-tell-what-space-im-in"></a>我的 HoloLens 无法判断我的空间

如果你的 HoloLens 无法识别并加载你自动登录的空间，请检查以下因素：

- 请确保已连接到 Wi-Fi
- 请确保房间内有充足的光线
- 请确保不存在对周围环境的任何重大更改。

还可以通过转到 "**设置**" "  >  **系统**  >  **空间**" 手动加载空间或管理空间。

## <a name="im-getting-a-low-disk-space-error"></a>我收到 "磁盘空间不足" 错误

你需要通过执行以下一项或多项操作来释放一些存储空间：

- 删除某些未使用的空间。 单击 "**设置**"  >  "**系统**  >  **空间**"，选择不再需要的空间，然后选择 "**删除**"。
- 删除已放置的部分全息影像。
- 从照片应用中删除一些图片和视频。
- 从 HoloLens 卸载某些应用。 在 " **所有应用** " 列表中，点击并按住你要卸载的应用，然后选择 " **卸载**"。

## <a name="my-hololens-cant-create-a-new-space"></a>我的 HoloLens 无法创建新的空间

最可能的问题是在存储空间不足的情况下运行。 请尝试前面的某个 [提示](#im-getting-a-low-disk-space-error) 以释放一些磁盘空间。

## <a name="the-hololens-emulator-isnt-working"></a>HoloLens 模拟器不工作

有关 HoloLens 模拟器的信息位于我们的开发人员文档中。  阅读有关 [排查 HoloLens 模拟器问题的](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)详细信息。
