---
title: 更新 HoloLens
description: 了解如何检查 HoloLens 内部版本编号、使用设备更新保持最新、加入预览体验计划以及回滚更新。
keywords: 操作说明， 更新， 回滚， HoloLens， 检查内部版本， 内部版本编号
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283933"
---
# 更新 HoloLens

HoloLens 使用 Windows 更新，就像其他 Windows 10 设备一样。 HoloLens 会在系统更新插入电源并连接到 Internet 时自动下载和安装，即使它处于待机状态。

本文将介绍 HoloLens 工具，

- 查看当前操作系统版本 (版本号) 
- 检查更新
- 手动更新 HoloLens
- 回滚到较旧的更新

## 检查操作系统版本 (版本号) 

可以通过打开"设置" (并选择"系统关于") 验证系统版本号和内部****  >  **版本号**。

## 检查更新并手动更新

你可在设置中随时检查更新。  查看可用更新并检查新更新：

1. 打开 **"设置"** 应用。
1. 导航到 **"&**  >  **Windows 更新"。**
1. 选择 **"检查更新"。**

如果更新可用，它将开始下载新版本。 下载完成后，选择" **立即重启** "按钮以触发安装。 如果你的设备低于 40%且未插入，重启将不会开始安装更新。

当你的 HoloLens 安装更新时，它将显示旋转齿轮和进度指示器。 在此期间不要关闭 HoloLens。 安装完成后，它将自动重新启动。

HoloLens 一次应用一个更新。  如果你的 HoloLens 支持多个版本的最新版本，你可能需要多次运行更新过程，才能完全更新。

## 返回到以前的版本 - HoloLens 2

在某些情况下，你可能想要返回到 HoloLens 软件的早期版本。 为此，可以使用高级恢复助手将 HoloLens 重置为早期版本。

> [!NOTE]
> 返回到早期版本会删除你的个人文件和设置。

若要返回到 HoloLens 2 的早期版本，请按照如下步骤操作：

1. 确保你未将任何电话或 Windows 设备插入电脑。
1. 在电脑上，从 Microsoft [Store](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 下载高级恢复助手。
1. 下载[最新版本的 HoloLens 2](https://aka.ms/hololens2download)。
1. 完成这些下载后，打开"**文件资源管理器**  >  **下载"。** 右键单击刚刚下载的压缩文件夹，然后选择**全部提取** > **提取**将其解压缩。
1. 使用 USB-A 到 USB-C 电缆将 HoloLens 连接到电脑。 （即使你在连接 HoloLens 时一直使用的是其他电缆，但此电缆的使用效果更好。）
1. 高级恢复助手自动检测 HoloLens。 选择“**Microsoft HoloLens**”磁贴。
1. 下一个屏幕上，选择"手动 **程序包** 选择"，然后选择步骤 4 中解压缩的文件夹中包含的安装文件。  (查找扩展名 .ffu.) 
1. 选择 **"安装软件**"，然后按照说明操作。

## 返回到以前版本 - HoloLens (第一代) 

在某些情况下，你可能想要返回到 HoloLens 软件的早期版本。 为此，可以使用 Windows 设备恢复工具将 HoloLens 重置为早期版本。

> [!NOTE]
> 返回到早期版本会删除你的个人文件和设置。

若要返回到以前版本的 HoloLens 1，请按照以下步骤操作：

1. 确保你未将任何电话或 Windows 设备插入电脑。
1. 在电脑上，将[Windows 设备恢复工具 (WDRT) 。 ](https://support.microsoft.com/help/12379)
1. 下载 [HoloLens 周年更新恢复包](https://aka.ms/hololensrecovery)。
1. 下载完成后，打开"**文件资源管理器**  >  **下载"。** 右键单击刚下载的压缩文件夹，然后选择"提取**所有**提取"  >  **** 将其解压缩。
1. 使用它所随的微型 USB 电缆将 HoloLens 连接到电脑。 （即使你在连接 HoloLens 时一直使用的是其他电缆，但此电缆的使用效果更好。）
1. WDRT 将自动检测 HoloLens。 选择“**Microsoft HoloLens**”磁贴。
1. 下一个屏幕上，选择"手动 **程序包** 选择"，然后选择步骤 4 中解压缩的文件夹中包含的安装文件。  (查找扩展名 .ffu.) 
1. 选择 **"安装软件**"，然后按照说明操作。

> [!NOTE]
> 如果 WDRT 未检测到 HoloLens，请尝试重启电脑。 如果重启不起作用，请选择“**未检测到我的设备**”，选择“**Microsoft HoloLens**”，然后按照说明操作。

## HoloLens 上的 Windows 预览体验计划

想要查看 HoloLens 中的最新功能吗？  如果是这样，请加入 Windows 预览体验计划;在向普通公众提供 HoloLens 软件更新之前，你将有权访问预览版 HoloLens 软件更新。

[获取 Microsoft HoloLens 的 Windows 预览体验成员预览版](hololens-insider.md)。
