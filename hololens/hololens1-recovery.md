---
title: 重启、重置或恢复 HoloLens 1
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
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
ms.openlocfilehash: a52e8e5bae49973d92efa6ea75391dc44d8b8ddb
ms.sourcegitcommit: 357094acfd39f7c59a0a62f1dd7918b58c209ef7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "10861157"
---
# 重启、重置或恢复 HoloLens（第 1 代）

如果你的 HoloLens 出现问题，你可能想要尝试重启、重置甚至通过设备恢复进行重刷。

如果 HoloLens 不能正常运行，可尝试以下解决方法。  本文将指导你逐步完成推荐的恢复步骤。

如果你想要恢复的是 HoloLens 2，请查看有关[恢复 HoloLens 2](https://docs.microsoft.com/hololens/hololens-recovery) 的页面，因为这两种流程存在差异。

本文重点介绍 HoloLens 设备和软件，如果你的全息影像看起来有问题，[这篇文章](hololens-environment-considerations.md)讨论了改善全息影像质量的环境因素。

## “重新启动”

### 使用 Cortana 执行安全重启

重启 HoloLens 的最安全方法是使用 Cortana。 在 HoloLens 出现问题时，通常会首先执行这一简单操作。 

> [!NOTE]
> 并非所有设备上都支持使用 Cortana。 Cortana 在所有 HoloLens（第 1 代）设备上都可用。
> 在 HoloLens 2 设备上，Cortana 在 Windows Holograpic 版本 2004 更新之前的内部版本上可用。

1. 戴上你的设备
1. 请确保已接通电源，用户已登录，并且设备并非是在等待用密码来进行解锁。
1. 说“你好小娜，请重启”。
1. 收到后，她会要求你确认。 在她问完问题后，稍等片刻会有一个声音响起（这表示她正在听你说话），然后说“是”。
1. 此时设备将重启。

### 使用电源按钮执行安全重启

如果仍然无法重启设备，可以尝试使用电源按钮进行重启：

1. 按住电源按钮 5 秒。
   1. 一秒钟后，你将看到五个 LED 全部亮起，然后从右到左慢慢熄灭。
   1. 五秒钟后，所有 LED 全部熄灭，表示已成功发出关机命令。
   1. 请注意，一定要在所有 LED 都熄灭后立即释放该按钮。
1. 等待 1 分钟，以便完全关机。 请注意，即使屏幕关闭，关机也可能仍在进行中。
1. 通过按住电源按钮一秒钟，重新打开设备电源。

### 使用 Windows 设备门户执行安全重启

> [!NOTE]
> 若要执行此操作，必须将 HoloLens 配置为开发人员设备。  
> 阅读有关 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)的详细信息。

如果以上程序不起作用，可以尝试使用 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)来重新启动设备。 右上角有一个可重启或关闭设备的选项。

### 执行不安全强制重启

如果上述方法都无法成功重启设备，可以进行强制重启。 此方法等同于从 HoloLens 中取出电池。  该操作很危险，可能会使你的设备进入损坏状态。  如果发生这种情况，则必须刷写 HoloLens。  

> [!WARNING]
> 这是一种可能有害的方法，只有在上述方法都不起作用时才能使用。

1. 按住电源按钮至少 10 秒。
   - 长按时间超出 10 秒也没有关系。
   - 忽略任何 LED 活动的做法是安全的。
1. 释放该按钮，等待两到三秒钟。
1. 通过按住电源按钮一秒钟，重新打开设备电源。
如果仍有问题，请按住电源按钮 4 秒钟，直至所有电池指示灯熄灭，且屏幕停止显示全息影像。 等待 1 分钟，然后再次按下电源按钮以打开设备。

## 重置为出厂设置

> [!NOTE]
> 电池电量至少达到 40% 才能进行重置。

如果 HoloLens 在重启后仍存在问题，请尝试将其重置为出厂状态。  重置 HoloLens 时，会保留安装在其上的 Windows Holographic 软件的版本，而将其他所有内容返回到出厂设置。

如果重置设备，则将擦除所有个人数据、应用和设置，包括 TPM 重置。 重置操作将仅安装最近安装的 Windows Holographic 版本，你必须重新执行所有初始化步骤（校准、连接到 Wi-Fi、创建用户帐户、下载应用等）。

1. 启动“设置”应用，然后选择“更新”**** > “重置”****。
1. 选择“重置设备”**** 选项，然后阅读确认消息。
1. 如果你同意重置设备，则设备将重新启动并显示一组旋转的齿轮和一个进度栏。
1. 等待约 30 分钟，直至该过程完成。
1. 重置将完成，并且设备将重启进入开箱即用体验。

## 重装操作系统

如果设备在重启和重置后仍然存在问题，可在计算机上使用恢复工具重装 HoloLens 的操作系统和固件。  

HoloLens 需要重置的所有数据都将打包在一个完整刷写更新 (FFU) 内。  这类似于 iso、wim 或 vhd。  [了解 FFU 映像文件格式。](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

如有必要，可使用 Windows Device Recovery Tool 在 HoloLens（第 1 代）上安装全新的操作系统。

使用此工具之前，请先确定重启或重置 HoloLens 能否修复相应问题。 恢复过程可能需要一些时间。  完成后，系统将安装批准用于 HoloLens 的最新版本 Windows Holographic 软件。

若要使用此工具，需要使用运行 Windows 10 或更高版本的计算机，其中至少有 4 GB 的可用存储空间。  请注意，不能在虚拟机上运行此工具。

### 恢复 HoloLens：

1. 在你的计算机上，下载并安装 [Windows Device Recovery Tool](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)。
1. 使用 HoloLens 随附的 Micro USB 电缆将 HoloLens（第 1 代）连接到计算机。
1. 运行 Windows Device Recovery Tool 并按照说明进行操作。

如果该工具未自动检测到 HoloLens（第 1 代），请选择“未检测到我的设备”**** 并按照说明将设备置于恢复模式。

### 手动刷写模式：

如果未检测到你的设备，请使用以下方法手动将其置于刷写模式。

1. 将设备与所有电源断开。
1. 如果设备处于开启状态，请按住电源按钮，直到完全关闭。
1. 按住**上调音量**按钮，然后轻触**电源按钮**。 
1. 此时设备应启动，然后仅显示中间的 LED 指示灯。
1. 将设备连接至电脑。
1. 启动 Windows Device Recovery Tool。
1. 你将需要选择“未检测到我的设备”***，然后选择“HoloLens”****。 
1. 按照说明恢复设备。
