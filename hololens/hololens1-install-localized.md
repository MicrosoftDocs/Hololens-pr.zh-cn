---
title: 安装 HoloLens 的本地化版本
description: 了解如何安装 HoloLens (第一代) 的本地化版本，包括中文版和日语版。
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 74eb003aafd23218b90988abe113d35f1fc3035a
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308538"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>安装 HoloLens (第一代的本地化版本) 

若要切换到中文版或日语版的 HoloLens，需要使用 Windows 设备恢复工具 (WDRT) 下载计算机上的语言版本，然后将其安装在 HoloLens 上。

> [!IMPORTANT]
> 使用 WDRT 安装 HoloLens 的中文版或日语版时，会从你的 HoloLens 中删除现有数据，如个人文件和设置。 

1. 在电脑上，下载并安装 [Windows 设备恢复工具 (WDRT) ](https://support.microsoft.com/help/12379)。
1. 下载所需的计算机语言包：  [简体中文](https://aka.ms/hololensdownload-ch) 或 [日语](https://aka.ms/hololensdownload-jp)。
1. 下载完成后，选择 "**文件资源管理器**  >  **下载**"。 右键单击刚下载的压缩文件夹，然后选择 "**提取所有**  >  **提取**" 将其解压缩。
1. 使用随附的微 USB 电缆将你的 HoloLens 连接到你的电脑。 即使已使用其他电缆连接 HoloLens，也 (，这种方法的效果最佳。 ) 
1. 工具自动检测到 HoloLens 后，选择 "Microsoft HoloLens" 磁贴。
1. 在下一个屏幕上，选择 " **手动包选择**"，   然后选择在步骤4中解压缩的文件夹中所安装的安装文件。  (查找扩展名为 "ffu" 的文件。 )  
1. 选择 " **安装软件** "，然后按照说明进行操作。 
1. 生成安装后，HoloLens 安装程序将自动启动。 放入设备并按照安装说明进行操作。 

完成安装后，请参阅 "**设置**" "  >  **更新" "更新 & 安全**  >  **Windows 预览体验计划**"，并检查是否已配置为接收最新的预览版。 与英语预览版一样，Windows 预览体验计划将更新的中文版和日语版与最新的预览版本保持最新。

> [!NOTE]
>  
> - 不能使用 "设置" 应用更改英语、日语和中文的系统语言。 闪烁新的版本是唯一受支持的更改设备系统语言的方法。
> - 虽然可以使用屏幕拼音键盘输入简体中文或日语文本，但目前不支持使用蓝牙硬件键盘键入简体中文或日语文本。  但是，在中文或日语版 HoloLens 上，你可以继续使用蓝牙键盘键入英语 (以将硬件键盘切换为输入英语，按 ~ 键) 。
