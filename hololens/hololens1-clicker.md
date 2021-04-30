---
title: 使用 HoloLens clicker
description: 本文概述了如何使用 HoloLens clicker，包括 clicker 配对、充电和恢复。
ms.assetid: 7d4a30fd-cf1d-4c9a-8eb1-1968ccecbe59
ms.date: 09/16/2019
manager: jarrettr
keywords: hololens
ms.prod: hololens
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4b17fc134846a66046a819c56755d87206c5643e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308526"
---
# <a name="use-the-hololens-1st-gen-clicker"></a>使用 HoloLens (第一代) clicker

Clicker 专用于 HoloLens (第一代) ，为你提供另一种与全息影像交互的方法。 它随附于 HoloLens (第一代) ，位于单独的框中。

使用它代替手动笔势来选择、滚动、移动和调整应用的大小。

## <a name="clicker-hardware-and-pairing"></a>Clicker 硬件和配对

HoloLens (第一代) clicker 有一个手指循环，使其更易于保持，并具有一个指示器。

![HoloLens Clicker](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a>Clicker 指示器光源

Clicker 上的灯光是什么意思。

- **闪烁的白色**。 Clicker 处于配对模式。
- **快速闪烁白色**。 配对成功。
- **纯白。** Clicker 正在充电。
- **琥珀色闪烁**。 电池电量不足。
- **稳定琥珀色**。 Clicker 遇到错误，需要重新启动。 按配对按钮时，请单击并按住15秒。

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a>将 clicker 与 HoloLens (第一代搭配) 

1. 使用布隆手势 **开始** 使用，然后选择 "**设置**  >  **设备**" 并验证蓝牙是否已打开。
1. 在 clicker 上，按住配对按钮，直至状态灯闪烁白色。
1. 在配对屏幕上，选择 " **Clicker**  >  **对**"。

### <a name="charge-the-clicker"></a>收取 clicker

当 clicker 电池电量不足时，电池指示器会闪烁琥珀色。 将微型 USB 电缆插入 USB 电源，以对设备进行计费。

## <a name="use-the-clicker-with-hololens-1st-gen"></a>结合使用 clicker 和 HoloLens (第一代) 

### <a name="hold-the-clicker"></a>保留 clicker

若要放入 clicker，请将循环滑过环或中间指，使微 USB 端口面向手腕。 将您的拇指放在缩进中。

![如何保存 Clicker](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a>Clicker 手势

Clicker 手势为小手腕旋转，而不是用于 HoloLens 手势的更大运动。 并且 HoloLens 识别你的手势，并单击，即使 clicker 在 [手势帧](hololens1-basic-usage.md)外，你也可以将 clicker 放在最适合的位置。

- **选择**。 若要选择一个全息图、按钮或其他元素，请在其上注视，然后单击。

- **单击并按住**。 单击并按住按钮，可以执行一些与点击和按住操作相同的操作，例如移动或调整全息图大小。

- **滚动**。 在应用栏上，选择 " **滚动工具**"。 单击并按住，然后将 clicker 向上、向下、向左或向右旋转。 若要加快滚动，请从滚动工具的中心越远移动手。

- **缩放**。 在应用栏上，选择 " **缩放工具**"。 单击并按住，然后向上旋转 clicker，或向下旋转以缩小。

> [!TIP]
> 若要在使用 Microsoft Edge 时进行放大或缩小，请注视页面并双击。

## <a name="restart-or-recover-the-clicker"></a>重新启动或恢复 clicker

如果 HoloLens clicker 无响应或工作不正常，请尝试以下操作。

### <a name="restart-the-clicker"></a>重新启动 clicker

使用笔的笔尖按下并按住 "配对" 按钮。 同时，单击并按住 clicker 15 秒。 如果 clicker 已与 HoloLens 配对，它将在重新启动后保持配对。

如果 clicker 无法打开或重新启动，请尝试使用 HoloLens 充电器对其充电。 如果电池电量非常低，则可能需要几分钟的时间，白色指示器才会亮起。

### <a name="re-pair-the-clicker"></a>重新配对 clicker

选择 "**设置**  >  **设备**" 并选择 "clicker"。 选择 " **删除**"，等待几秒钟，然后再次配对 clicker。

### <a name="recover-the-clicker"></a>恢复 clicker

如果重新启动并重新配对 clicker 不能解决问题，Windows 设备恢复工具可以帮助你恢复问题。 恢复过程可能需要一段时间，并将安装最新版本的 clicker 软件。 若要使用该工具，你需要一台运行 Windows 10 或更高版本且至少具有 4 GB 可用存储空间的计算机。

恢复 clicker：

1. 在计算机上下载并安装 [Windows 设备恢复工具](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) 。
1. 使用 HoloLens 随附的微 USB 电缆将 clicker 连接到计算机。
1. 运行 Windows 设备恢复工具并按照说明进行操作。

如果未自动检测到 clicker，请选择 " **未检测到设备** "，然后按照说明将设备置于恢复模式。
