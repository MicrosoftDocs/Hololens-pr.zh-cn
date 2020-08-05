---
title: 疑难解答
description: 常见 HoloLens 问题的解决方案。
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
keywords: 问题、缺陷、故障排除、修复、帮助、支持、HoloLens
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 469848cf306675fcfb99247b5c91b159c204a5fe
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915937"
---
# 疑难解答

本文介绍如何解决几个常见的 HoloLens 问题。

## 我的 HoloLens 没有响应或无法启动

如果您的 HoloLens 无法启动：

- 如果电源按钮旁边的指示灯未亮起，或者只有一个指示灯闪烁，则您可能需要为[HoloLens 收费。](hololens-recovery.md#charge-the-device)
- 如果在按下电源按钮时指示灯亮起，但在显示器上看不到任何内容，请[preform 设备的硬重置](hololens-recovery.md#hard-reset-procedure)。

如果你的 HoloLens 已冻结或无响应：

- 按 "电源" 按钮以关闭 HoloLens，直到所有五个指示灯关闭，或者如果指示灯无响应，则为15秒。 若要启动 HoloLens，请再次按下电源按钮。

如果这些步骤不起作用，可以尝试[恢复 hololens 2 设备](hololens-recovery.md)或[hololens (第一代) 设备。](hololens1-recovery.md)

## 全息影像看起来不好

如果您的全息影像不稳定、jumpy 或看起来不稳定，请尝试：

- 在 HoloLens 前面清洗设备面板和传感器栏。
- 增加房间中的光线。
- 浏览和查看你的周围环境，以便 HoloLens 能够更完整地对其进行扫描。
- 为眼睛校准您的 HoloLens。 转到 "**设置**  >  **系统**  >  **实用工具**"。 在“**校准**”下，选择“**打开校准**”。

## HoloLens 未响应手动输入

为确保 HoloLens 能够看到你的手，你需要将它们放在手势帧中。  混合现实主页提供的反馈可让你了解你的手何时被跟踪。  不同版本的 HoloLens 的反馈不同：
- 在 HoloLens (第一代) ，注视光标从一个点更改为圆圈
- 在 HoloLens 2 上，当你的手型接近盖板时，将显示一个指尖光标，当 slates 更远时，将显示一个手形射线

许多沉浸式应用都遵循类似于混合现实主页的输入模式。  了解有关在[HoloLens (第一代) ](hololens1-basic-usage.md#use-hololens-with-your-hands)和[HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)上使用手动输入的详细信息。

如果戴上手套，请注意，某些类型的手套不能与手动跟踪一起使用。  一个常见的示例是黑色橡胶手套，它趋向于吸收红外线，而不是由深度相机拾取。  如果你的工作涉及橡胶手套，我们建议尝试使用较浅的颜色，如蓝色或灰色。  另一个示例是大型 baggy 手套，它往往会遮盖你的手型形状。 我们建议使用符合窗体的手套以获得最佳效果。

如果你的面板有指纹或涂抹，请使用 HoloLens 随附的 microfiber 清洁布来轻轻清理你的面板。

## HoloLens 没有响应我的语音命令

如果 Cortana 没有响应你的语音命令，请确保 Cortana 已打开。 在 "所有应用" 列表中，选择 " **Cortana**  >  **菜单**  >  **笔记本**  >  **设置**" 以进行更改。 若要了解有关可以说出的内容的详细信息，请参阅[使用语音操作 HoloLens](hololens-cortana.md)。

## 我无法放置全息影像或查看以前放置的全息影像

如果 HoloLens 无法映射或加载你的空间，它将进入 "有限模式"，你将无法放置全息影像或查看你放置的全息影像。 你可以尝试以下操作：

- 请确保你的环境中有足够的光线，以便 HoloLens 可以查看和映射空间。
- 请确保您已连接到 Wi-fi 网络。 如果你未连接到 Wi-fi，则 HoloLens 无法识别和加载已知空间。
- 如果需要创建新的空间，请连接到 Wi-fi，然后重新启动 HoloLens。
- 若要查看正确的空间是否处于活动状态，或者要手动加载空间，请转到 "**设置**  >  **系统**  >  **空间**"。
- 如果加载了正确的空间，但仍遇到问题，则空间可能已损坏。 若要解决此问题，请选择空间，然后选择 "**删除**"。 删除空间后，HoloLens 将开始映射你的周围环境并创建新空间。

## 我的 HoloLens 无法分辨我正在输入的空间

如果你的 HoloLens 无法识别和加载你自动加载的空间，请检查以下因素：

- 请确保您已连接到 Wi-fi
- 确保房间中有充足的光线
- 请确保没有对周围环境进行任何重大更改。

您也可以通过转到 "**设置**  >  **系统**  >  **空间**" 手动加载空间或管理您的共享空间。

## 收到 "磁盘空间不足" 错误

您需要通过执行下列一项或多项操作来释放存储空间：

- 删除一些未使用的空间。 转到 "**设置**  >  **系统**  >  **空间**"，选择不再需要的空间，然后选择 "**删除**"。
- 删除一些你放置的全息影像。
- 从 "照片" 应用中删除一些图片和视频。
- 从 HoloLens 中卸载某些应用。 在 "**所有应用**" 列表中，点击并按住要卸载的应用，然后选择 "**卸载**"。

## 我的 HoloLens 无法创建新的空间

最可能的问题是你的存储空间不足。 请尝试以前的一个[提示](#im-getting-a-low-disk-space-error)，释放一些磁盘空间。

## HoloLens 模拟器无法正常工作

有关 HoloLens 模拟器的信息位于我们的开发人员文档中。  阅读有关[对 HoloLens 模拟器进行故障排除的](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)详细信息。
