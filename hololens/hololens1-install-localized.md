---
title: 安装 HoloLens 的本地化版本
description: 了解如何安装 HoloLens 的本地化版本（第一代），包括中文和日语版本。
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: high
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: af79e42477a3a317dde03a795c442fa31241600d
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11282973"
---
# 安装 HoloLens（第一代）的本地化版本

若要切换到 HoloLens 的中文或日语版本，你需要在电脑上使用 Windows Device Recovery Tool (WDRT) 下载相应语言的内部版本，然后将其安装到 HoloLens 上。

> [!IMPORTANT]
> 使用 WDRT 安装 HoloLens 的中文或日语版本时，将从 HoloLens 中删除现有数据，如个人文件和设置。 

1. 在你的电脑上，下载并安装 [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379)。
1. 将所需语言的程序包下载到电脑：[简体中文](https://aka.ms/hololensdownload-ch)或[日语](https://aka.ms/hololensdownload-jp)。
1. 下载完成后，选择**文件资源管理器** > **下载**。 右键单击刚刚下载的压缩文件夹，然后选择**全部提取** > **提取**将其解压缩。
1. 使用随附的微型 USB 电缆将 HoloLens 连接到电脑。 （即使你在连接 HoloLens 时一直使用的是其他电缆，但此电缆的使用效果更好。）
1. 在工具自动检测到 HoloLens 后，选择 Microsoft HoloLens 磁贴。
1. 在下一个屏幕上，选择 **手动选择程序包** ，然后选择你在步骤 4 中解压缩的文件夹中的安装文件。 （查找扩展名为“.ffu”的文件。） 
1. 选择 **安装软件**，然后按照说明操作。 
1. 在安装版本后，HoloLens 设置将自动启动。 戴上设备，按照设置说明操作。 

完成设置后，转到**设置** > "**更新和安全** > **Windows 预览体验计划**，检查是否已配置为接收最新预览版。 与英语预览版一样，Windows 预览体验计划将使用最新预览版让 HoloLens 的中文和日语版本保持最新状态。

> [!NOTE]
>  
> - 你无法使用“设置”应用在英语、日语和中文之间更改系统语言。 支持更改设备系统语言的唯一方法是更新新版本。
> - 虽然你可以使用屏幕上的拼音键盘输入简体中文或日语文本，但目前不支持使用蓝牙硬件键盘键入简体中文或日语文本。  但是，在中文或日语版 HoloLens 中，你可以继续使用蓝牙键盘键入英文（若要将硬件键盘切换为键入英文，请按 ~ 键）。
