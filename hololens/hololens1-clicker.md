---
title: 使用 HoloLens 单击器
description: 本文概述了如何使用 HoloLens 单击器，包括点击器配对、收费和恢复。
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
ms.openlocfilehash: 83e5a746b6900c547778c71a0855426563458032
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924054"
---
# <a name="use-the-hololens-1st-gen-clicker"></a>使用 HoloLens （第 1 代）遥控器

单击器专为 HoloLens (第一代) ，提供另一种与全息影像交互的方式。 它附带 HoloLens (第一代) ，在单独的框中。

使用它来不使用手势来选择、滚动、移动和调整应用的大小。

## <a name="clicker-hardware-and-pairing"></a>Clicker 硬件和配对

HoloLens (第一代) 单击器具有一个手指循环，以便更轻松地按住，并且指示器指示灯。

![The HoloLens Clicker](images/use-hololens-clicker-1.png)

### <a name="clicker-indicator-lights"></a>点击器指示器灯

点击器上的灯的含义是什么。

- **闪烁白色**。 单击器为配对模式。
- **快速闪烁的白色**。 配对成功。
- **纯白色**。 点击器正在收费。
- **闪烁的黄色**。 电池电量不足。
- **实心黄色**。 单击器出现错误，需要重启它。 按下配对按钮时，单击并按住 15 秒。

### <a name="pair-the-clicker-with-your-hololens-1st-gen"></a>将 Clicker 与 HoloLens (第一代) 

1. 使用"打开"手势转到"启动 **"，** 然后选择"设置  >  **设备**"并验证蓝牙是否打开。
1. 在单击器上，按住配对按钮，直到状态指示灯闪烁为白色。
1. 在配对屏幕上，选择 **"Clicker**  >  **Pair"。**

### <a name="charge-the-clicker"></a>对点击器收费

当点击器电池不足时，电池指示器将闪烁为黄色。 将 Micro USB 电缆插入 USB 电源，为设备充电。

## <a name="use-the-clicker-with-hololens-1st-gen"></a>将 Clicker 与 HoloLens (第一代) 

### <a name="hold-the-clicker"></a>按住单击器

若要放在点击器上，请滑动环或中指上的循环，使 Micro USB 端口面向你的手部。 将滚动块放在缩进中。

![如何按住 Clicker](images/use-hololens-clicker-2.png)

### <a name="clicker-gestures"></a>点击器笔势

点击器手势是小型旋转，而不是用于 HoloLens 手势的较大运动。 HoloLens 识别你的手势和单击（即使点击器在手势框架之外）也可以[](hololens1-basic-usage.md)，因此你可以将点击器保持在最舒适的位置。

- **选择**。 若要选择全息影像、按钮或其他元素，请凝视它，然后单击。

- **单击并按住**。 单击并按住按钮，执行一些与点击和按住相同的操作，例如移动全息影像或调整全息影像大小。

- **滚动**。 在应用栏上，选择"**滚动工具"。** 单击并按住，然后向上、向下、向左或向右旋转单击器。 若要更快地滚动，请从滚动工具的中心向前移动手部。

- **缩放**。 在应用栏上，选择"**缩放工具"。** 单击并按住，然后向上旋转单击器以放大或缩小。

> [!TIP]
> 若要在使用页面时放大Microsoft Edge缩小，请凝视页面并双击。

## <a name="im-having-problems-using-the-hololens-clicker"></a>我在使用 HoloLens 单击器时遇到问题

使用 [单击器](hololens1-clicker.md) 可以选择、滚动、移动全息影像并重设其大小。 单个应用可能支持其他点击手势。

如果在使用单击器时遇到问题，请确保它收费并与 HoloLens 配对。 如果电池电量不足，指示灯将闪烁为黄色。 若要验证单击器是否配对，请转到"设置  >  **设备**"，查看其是否显示在那里。 有关详细信息，请参阅 [对单击器](hololens1-clicker.md)。

如果单击器已收费并配对，但仍遇到问题，请按住主按钮和配对按钮 15 秒来重置它。 然后再次将单击器与 HoloLens 配对。

如果重置单击器不起作用，请参阅重启 [或恢复 HoloLens 单击器](hololens1-clicker.md#restart-or-recover-the-clicker)。
## <a name="restart-or-recover-the-clicker"></a>重启或恢复单击器

下面是在 HoloLens 单击器无响应或运行不良好时要尝试的一些操作。

### <a name="restart-the-clicker"></a>重启单击器

使用笔尖按下并按住配对按钮。 同时，单击并按住单击器 15 秒。 如果单击器已与 HoloLens 配对，它将在重启后保持配对。

如果单击器无法打开或重启，请尝试使用 HoloLens 设备进行收费。 如果电池电量非常低，则白色指示灯可能需要几分钟才能打开。

### <a name="re-pair-the-clicker"></a>重新配对单击器

选择 **"**  >  **设置设备"，** 然后选择单击器。 选择 **"删除**"，等待几秒钟，然后再次配对单击器。

### <a name="recover-the-clicker"></a>恢复点击器

如果重启并重新配对单击器无法解决问题，Windows 设备恢复工具可帮助你恢复它。 恢复过程可能需要一些时间，它将安装最新版本的点击器软件。 若要使用该工具，需要一台运行 Windows 10或更高版本的计算机，该计算机至少具有 4 GB 的可用存储空间。

若要恢复点击器，请：

1. 在计算机上下载 [并安装 Windows 设备](https://dev.azure.com/ContentIdea/ContentIdea/_queries/query/8a004dbe-73f8-4a32-94bc-368fc2f2a895/) 恢复工具。
1. 使用 HoloLens 的 Micro USB 电缆将单击器连接到计算机。
1. 运行 Windows 设备恢复工具并按照说明进行操作。

如果未自动检测到单击器，请选择"未检测到我的设备 **"，** 并按照说明将设备置于恢复模式。

