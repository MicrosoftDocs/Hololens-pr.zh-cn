---
title: 重启、重置或恢复 HoloLens 1
ms.reviewer: Basic and advanced instructions for rebooting or resetting your HoloLens.
description: 如何使用 Windows Device Recovery Tool 将映像刷写到第 1 代 HoloLens。
keywords: 操作方法, 重启, 重置, 恢复, 硬重置, 软重置, 电源周期, HoloLens, 关机, wdrt, windows device recovery tool
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: cd3e7a14ea811f6f3f3086563e7ead3bcd0115ae
ms.sourcegitcommit: 2122490074adb7f63edfc3576441980caa22695f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2020
ms.locfileid: "10915938"
---
# 重启、重置或恢复 HoloLens（第 1 代）

如果你的 HoloLens 出现问题，你可能想尝试重新启动或重置，甚至通过使用设备恢复来刷新设备。 本文将按顺序指导你完成建议的恢复步骤。

如果要恢复 HoloLens 2，请参阅[恢复 HoloLens 2 ](https://docs.microsoft.com/hololens/hololens-recovery)，因为此过程有所不同。

> [!NOTE]
> 本文重点介绍 HoloLens 设备和软件。 如果全息影像不正确，请参阅 **[HoloLens 环境注意事项](hololens-environment-considerations.md)**，了解有关改进全息质量因素的信息。

## “重新启动”

### 使用 Cortana 执行安全重启

重新启动 HoloLens 的最安全方法是使用 Cortana，这通常是在遇到 HoloLens 问题时首先要尝试的方法。

> [!NOTE] 
> 并非所有设备上都支持使用 Cortana。
> - Cortana 在所有 HoloLens（第 1 代）设备上都可用。 
> - 在 HoloLens 2 设备上，Cortana 在 Windows Holograpic 版本 2004 更新之前的内部版本上可用。

1. 打开 HoloLens。
1. 请确保用户已登录，并且设备并非是在等待用密码来进行解锁。
2. 说“你好小娜，请重启”。
3. Cortana 会回复并提示您确认。 提问后等待播放声音，然后说“是”。 设备将启动。

### 使用“电源”按钮执行安全重启

如果仍然无法重启设备，可尝试使用**电源**按钮进行重启：

1. 按住**电源**按钮 5 秒。 1 秒后，所有五个 LED 都将点亮，然后从右到左缓慢关闭一个 LED。 5 秒钟后，所有指示灯将熄灭，表明已成功关闭。
      
   > [!IMPORTANT]
   > 一定要在所有 LED 都熄灭后立即释放该按钮。
1. 等待 1 分钟以完成关闭。 即使屏幕关闭后，关机也可能仍在进行中。
2. 通过按住**电源**按钮 1 秒钟，重新打开设备。

### 使用 Windows 设备门户执行安全重启

> [!NOTE]
> 为此，必须将 HoloLens 配置为开发人员设备。 阅读有关 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)的详细信息。

如果以上程序不起作用，可尝试使用 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)来重新启动设备。 在右上角，可查找重启或关闭设备的选项。

### 执行不安全强制重启

如果以前的方法没有重新启动 HoloLens，请强制重新启动。 此方法等同于取下并重新安装电池。 这很危险，因为它可能会使您的设备处于损坏状态。 如果发生这种情况，则必须刷写 HoloLens。  

> [!WARNING]
> 这是一种可能有害的方法，仅在之前引用的方法无效的情况下使用。

1. 按住**电源**按钮至少 10 秒。
   - 长按时间超出 10 秒也没有关系。
   - 忽略任何 LED 活动的做法是安全的。
1. 释放该按钮，等待 2-3 秒钟。
1. 按住**电源**按钮 1 秒。
1. 如果仍有问题，请按住**电源**按钮 4 秒钟，直至所有电池指示灯熄灭，且屏幕停止显示全息影像。 等待 1 分钟，然后再次按下**电源**按钮以打开设备。

## 重置为出厂设置

> [!NOTE]
> 电池电量至少达到 40% 才能进行重置。

如果 HoloLens 仍然有问题，请尝试将其重置为出厂状态。 此步骤会保留安装在其上的 Windows Holographic 软件的版本，而将其他所有内容返回到出厂设置。

>[!WARNING]
> 如果重置设备，则将擦除所有个人数据、应用和设置，包括 TPM 重置信息。 重置将仅安装最新安装的 Windows 全息版本。 必须重新执行所有初始化步骤（校准、连接到 Wi-Fi、创建用户帐户、下载应用程序等）

1. 启动“设置”应用，然后选择“**更新**” > “**恢复**”。
1. 选择“重置设备”**** 选项，然后阅读确认消息。
1. 确认重置。 设备将重新启动并显示一组旋转的齿轮和一个进度栏。
1. 等待约 30 分钟，直至该过程完成。 完成时，设备将重启进入开箱即用体验。

## 重新安装操作系统

如果设备在重启和重置后仍然存在问题，可在计算机上使用恢复工具重装 HoloLens 的操作系统和固件。  

HoloLens 重置所需的数据封装在映像刷写工具（FFU）中，它与 .iso、.wim 或 .vhd 文件相似。 [了解 FFU 映像文件格式。](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

可通过使用 Windows Device Recovery Tool 在 HoloLens（第 1 代）上安装新操作系统。 使用此工具之前，请先看看重启或重置 HoloLens 能否修复相应问题。

恢复过程可能需要一段时间。 完成后，将安装最新版本的 Windows Holographic 软件。

若要使用此工具，需要使用运行 Windows 10 或更高版本的计算机，其中至少有 4 GB 的可用存储空间。 不能在虚拟机上运行此工具。

### 恢复 HoloLens

1. 在你的计算机上，下载并安装 [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)。
1. 通过使用 HoloLens 随附的 Micro USB 电缆将 HoloLens（第 1 代）连接到计算机。
1. 打开 Windows Device Recovery Tool 并按照说明进行操作。

如果未自动检测到 HoloLens（第一代），请选择“**未检测到我的设备**”。 然后按照说明将设备置于恢复模式。

### 手动刷写模式

如果未检测到设备，请按照以下步骤将其置于闪烁模式：

1. 将设备与任何电源断开。
1. 如果设备处于开启状态，请按住**电源**按钮，直到完全关闭。
2. 按住**上调音量**按钮，然后轻触**电源**按钮。 此时设备应启动，仅显示中间的 LED 指示灯。
3. 将设备连接至电脑。
4. 打开 Windows Device Recovery Tool。
5. 选择“**未检测到我的设备**”，然后选择“**HoloLens**”。 
6. 按照说明恢复设备。
