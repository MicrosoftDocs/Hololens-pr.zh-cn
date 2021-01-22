---
title: 疑难解答
description: 了解 HoloLens 设备问题和疑难解答技术最常见的解决方案。
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
keywords: 问题， bug， 疑难解答， 修复， 帮助， 支持， HoloLens
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283043"
---
# 疑难解答

本文介绍如何解决多个常见的 HoloLens 问题。

## 我的 HoloLens 无响应或无法启动

如果你的 HoloLens 无法启动：

- 如果电源按钮旁边的 LED 不亮，或只有一个 LED 短暂闪烁，可能需要为 [HoloLens 充电。](hololens-recovery.md#charge-the-device)
- 如果在按下电源按钮时，LED 会打开，但你在显示器上看不到任何内容，请预先设置设备的硬[重置。](hololens-recovery.md#hard-reset-procedure)

如果你的 HoloLens 冻结或无响应：

- 按电源按钮关闭 HoloLens，直到所有五个 LED 自行关闭，或者如果 LED 无响应，则关闭 15 秒。 若要启动 HoloLens，请再次按电源按钮。

如果这些步骤不起作用，可以尝试恢复 [HoloLens 2](hololens-recovery.md) 设备或 [HoloLens (第一代) 设备。](hololens1-recovery.md)

## 全息影像看起来不良好

如果你的全息影像不稳定、跳转或看起来不对，请尝试：

- 清理 HoloLens 前端的设备面罩和传感器栏。
- 增加房间的光线。
- 四处移动并查看周围环境，以便 HoloLens 可以更彻底地扫描它们。
- 为眼睛校准 HoloLens。 转到 **"设置**  >  **系统**  >  **实用程序"。** 在“**校准**”下，选择“**打开校准**”。
 
### 报告全息影像不稳定或看起来不对的问题
 
1. 请录制此问题 [的混合现实](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 捕获视频。 此视频稍后可通过反馈中心作为附加文件上载。  
1. 通过"设置"应用->**隐私**诊断&反馈和可选诊断数据下启用完整遥测****，确保将切换  ->  **** 设置为 **"打开"** ****
1. 通过更新到最新的 Windows 全息操作系统（ ([20H2 ](hololens-release-notes.md#windows-holographic-version-20h2)或更高版本）获取最新的全息影像缩放和稳定性) 。 更新后，执行下列操作：
    1. 通过"设置 **"应用**->**系统**全息影像 ->删除所有全息影像，然后选择"删除所有全息影像"，然后从  ->  **** 全新的地图开始。 ****
    1. 通过佩戴 HoloLens 并四处走来走来，并查看空间中的所有区域与表面，创建空间的新地图。 此操作需要 2-3 分钟。
    1. 执行 IPD 校准。 转到 **"设置**  >  **系统**  >  **实用程序"。** 在“**校准**”下，选择“**打开校准**”。
    1. 重新测试方案，并查看它是否仍然保留。
1. 如果更新未修复该问题，请提交反馈 [中心问题](hololens-feedback.md)。 填写反馈后，可以使用"共享"按钮创建**** 一个可在联系支持人员时发送的轻松共享链接。

## HoloLens 不响应手输入

若要确保 HoloLens 可以看到你的手，你需要将它们放在手势框架中。  混合现实主页提供反馈，可让你了解何时跟踪手。  不同版本的 HoloLens 的反馈不同：
- 在 HoloLens (第一代) 上，凝视光标从一个点变为一个圈
- 在 HoloLens 2 上，当手靠近平板电脑时，会出现指尖光标，当平板电脑离得更近时会出现手部光线

许多沉浸式应用遵循与混合现实家庭类似的输入模式。  了解有关在 [HoloLens ](hololens1-basic-usage.md#use-hololens-with-your-hands) 第一代 (和 [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)) 手输入。

如果你是一只手风，请注意某些类型的便笺不能用于手部跟踪。  一个常见示例是黑色橡皮手套，它们倾向于吸收红外光，而深度相机不会选取它们。  如果你的工作涉及橡皮戳，我们建议尝试较浅的颜色，如蓝色或灰色。  另一个示例是大包袋，它们通常会遮盖手的形状。 我们建议使用尽可能适合外形的防护线，以获得最佳效果。

如果你的面罩有指纹或毛毛，请使用 HoloLens 中随其一起清理面罩的微细纸来清理面罩。

## HoloLens 不响应我的语音命令

如果 Cortana 未响应语音命令，请确保 Cortana 已打开。 在"所有应用"列表中，选择**Cortana**  >  **菜单**  >  **笔记本**  >  **设置**以进行更改。 若要了解有关可以说出的内容的详细信息，请参阅[使用语音操作 HoloLens](hololens-cortana.md)。

## 我无法放置全息影像或查看之前放置的全息影像

如果 HoloLens 无法映射或加载你的空间，它将进入受限模式，你将无法放置全息影像或查看你放置的全息影像。 你可以尝试以下操作：

- 请确保你的环境中有足够的光，以便 HoloLens 可以看到和映射空间。
- 确保你已连接到Wi-Fi网络。 如果未连接到 WLAN，HoloLens 无法识别并加载已知空间。
- 如果你需要创建新空间，请连接到 WLAN，然后重启 HoloLens。
- 若要查看正确的空间是否处于活动状态，或手动加载空格，请转到"**设置**  >  **系统**  >  **空间"。**
- 如果加载了正确的空间，但您仍有问题，则空间可能已损坏。 若要解决此问题，请选择空格，然后选择"删除 **"。** 删除空间后，HoloLens 将开始映射你的周围环境并创建新空间。

## 我的 HoloLens 无法告诉我在什么空间

如果你的 HoloLens 无法自动标识和加载你的空间，请检查以下因素：

- 确保你已连接到Wi-Fi
- 确保房间中有足够的光
- 确保周围没有发生任何重大更改。

还可以手动加载空间，或通过进入"设置系统空间"****  >  **管理**  >  **空间**。

## 我收到"磁盘空间不足"错误

你需要通过执行以下一项或多项操作来释放一些存储空间：

- 删除一些未使用的空格。 转到 **"设置**系统空间"，选择不再需要的空格，  >  ****  >  **** 然后选择"**删除"。**
- 删除你放置的一些全息影像。
- 从"照片"应用中删除一些图片和视频。
- 从 HoloLens 中卸载某些应用。 在 **"所有应用"** 列表中，点击并按住要卸载的应用，然后选择"**卸载"。**

## 我的 HoloLens 无法创建新空间

最可能的问题是存储空间不足。 请尝试使用前面的 [提示之](#im-getting-a-low-disk-space-error) 一释放一些磁盘空间。

## HoloLens 仿真器无法工作

有关 HoloLens 仿真器的信息，请参阅我们的开发人员文档。  阅读有关 [HoloLens 仿真器疑难解答的更多信息](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)。
