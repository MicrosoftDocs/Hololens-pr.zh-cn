---
title: 更新 HoloLens
description: 检查 HoloLens 的版本号、更新和回滚更新。
keywords: 操作方法、更新、回滚、HoloLens、检查内部版本、内部版本号
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
ms.openlocfilehash: ee007b00b350ea0f80cda34964d32a57dc6dc0c6
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827663"
---
# 更新 HoloLens

HoloLens 使用 Windows 更新，就像其他 Windows 10 设备一样。 如果您的 HoloLens 已接通电源并连接到 Internet，则您的 HoloLens 将自动下载并安装系统更新（即使处于待机状态）。

本文将介绍 HoloLens 工具，适用于：

- 查看当前操作系统版本（内部版本号）
- 检查更新
- 手动更新 HoloLens
- 回退到较旧的更新

## 检查操作系统版本（内部版本号）

你可以通过打开 "设置" 应用并选择 "**系统**" 来验证系统版本号（内部版本号）  >  **About**。

## 检查更新和手动更新

你可以随时在 "设置" 中检查更新。  若要查看可用更新并检查新的更新，请执行以下操作：

1. 打开 "**设置**" 应用。
1. 导航到 "**更新 & 安全**  >  **Windows 更新**"。
1. 选择 "**检查更新**"。

如果有可用更新，它将开始下载新版本。 下载完成后，选择 "**立即重启**" 按钮以触发安装。 如果你的设备低于40% 且未插入，重新启动将不会开始安装更新。

当你的 HoloLens 安装更新时，它将显示旋转的齿轮和进度指示器。 在此期间不要关闭 HoloLens。 完成安装后，它将自动重新启动。

HoloLens 一次应用一个更新。  如果你的 HoloLens 超过一个最晚的版本，可能需要多次运行更新过程才能使其完全保持最新。

## 返回到以前的版本-HoloLens 2

在某些情况下，你可能希望返回到 HoloLens 软件的以前版本。 你可以通过使用高级恢复助理将 HoloLens 重置为早期版本来执行此操作。

> [!NOTE]
> 返回到早期版本删除您的个人文件和设置。

若要返回到以前版本的 HoloLens 2，请按照下列步骤操作：

1. 请确保你没有任何电话或 Windows 设备插入到电脑中。
1. 在你的电脑上，从 Microsoft Store 下载[高级恢复配套助理](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)。
1. 下载[最新的 HoloLens 2 版本](https://aka.ms/hololens2download)。
1. 完成这些下载后，打开**文件资源管理器**  >  **下载**。 右键单击刚刚下载的压缩文件夹，然后选择**全部提取** > **提取**将其解压缩。
1. 使用 USB-A 到 USB-C 电缆将 HoloLens 连接到电脑。 （即使你在连接 HoloLens 时一直使用的是其他电缆，但此电缆的使用效果更好。）
1. 高级恢复助理会自动检测到 HoloLens。 选择 " **Microsoft HoloLens** " 磁贴。
1. 在下一个屏幕上，选择 "**手动程序包选择**"，然后选择您在步骤4中解压缩的文件夹中包含的安装文件。 （查找扩展名为 ffu 的文件。）
1. 选择 "**安装软件**"，然后按照说明进行操作。

## 返回到以前版本-HoloLens （第1代）

在某些情况下，你可能希望返回到 HoloLens 软件的以前版本。 你可以通过使用 Windows 设备恢复工具将 HoloLens 重置到早期版本来执行此操作。

> [!NOTE]
> 返回到早期版本删除您的个人文件和设置。

若要返回到以前版本的 HoloLens 1，请按照下列步骤操作：

1. 请确保你没有任何电话或 Windows 设备插入到电脑中。
1. 在你的电脑上，下载[Windows Device Recovery 工具（WDRT）](https://support.microsoft.com/help/12379)。
1. 下载[HoloLens 周年更新恢复包](https://aka.ms/hololensrecovery)。
1. 下载完成后，打开**文件资源管理器**  >  **下载**。 右键单击刚刚下载的已压缩文件夹，然后选择 "**提取所有**  >  **提取**" 将其解压缩。
1. 使用随附的微型 USB 电缆将 HoloLens 连接到电脑。 （即使你在连接 HoloLens 时一直使用的是其他电缆，但此电缆的使用效果更好。）
1. WDRT 将自动检测 HoloLens。 选择 " **Microsoft HoloLens** " 磁贴。
1. 在下一个屏幕上，选择 "**手动程序包选择**"，然后选择您在步骤4中解压缩的文件夹中包含的安装文件。 （查找扩展名为 ffu 的文件。）
1. 选择 "**安装软件**"，然后按照说明进行操作。

> [!NOTE]
> 如果 WDRT 未检测到 HoloLens，请尝试重启电脑。 如果不起作用，请选择 **"我的设备未检测到**"，选择 " **Microsoft HoloLens**"，然后按照说明进行操作。

## HoloLens 上的 Windows 预览体验计划

想要查看 HoloLens 中的最新功能？  如果是，请加入 Windows 预览体验计划;你将获得更新 HoloLens 软件更新的版本，然后才可供公众使用。

[获取 Microsoft HoloLens 的 Windows 预览体验计划预览版](hololens-insider.md)。
