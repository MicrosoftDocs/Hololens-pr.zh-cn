---
title: 安装本地化版本的 HoloLens
description: 了解如何安装第一代HoloLens (的本地化) ，包括中文和日语版本。
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
ms.openlocfilehash: fe29e4ed611f86764f0db576b1a8794fa0ceec3047cadd26f502209faadea8b0
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115661807"
---
# <a name="install-localized-versions-of-hololens-1st-gen"></a>安装第一代HoloLens (的本地化) 

若要切换到中文版或日语版 HoloLens，需使用 Windows 设备恢复工具 (WDRT) 在电脑上下载该语言的生成，然后将它安装在 HoloLens 上。

> [!IMPORTANT]
> 使用 WDRT 安装中文或日语版本HoloLens删除数据中的现有数据，例如个人文件和设置HoloLens。 

1. 在电脑上，下载并安装[WINDOWS 设备恢复工具 (WDRT) 。 ](https://support.microsoft.com/help/12379)
1. 下载要用于电脑的语言的包：[简体中文或](https://aka.ms/hololensdownload-ch)[日语](https://aka.ms/hololensdownload-jp)。
1. 下载完成后，选择 **"文件资源管理器**  >  **下载"。** 右键单击刚下载的压缩文件夹，然后选择"**提取所有**  >  **提取**"将其解压缩。
1. 连接HoloLens附带的微 USB 电缆将设备连接到电脑。  (即使一直在使用其他电缆来连接HoloLens，此电缆也效果最佳。) 
1. 在该工具自动检测你的HoloLens后，选择"Microsoft HoloLens磁贴。
1. 下一个屏幕上，选择 ****"手动包选择"，然后选择位于步骤 4 中解压缩的文件夹中的安装   文件。  (查找扩展名为".ffu".)  
1. 选择 **"安装软件** "并按照说明进行操作。 
1. 安装生成后，HoloLens安装程序自动启动。 将 置于设备上，并按照设置说明操作。 

完成设置后，转到"更新设置"&"Windows 会员计划"，并检查是否配置为接收最新的  >    >  预览版本。 与英语预览版一样，Windows 会员计划使用最新的预览版本HoloLens中文和日语版本。

> [!NOTE]
>  
> - 你无法使用 设置 更改英语、日语和中文之间的系统语言。 刷新新生成是更改设备系统语言的唯一受支持方法。
> - 虽然可以使用屏幕上的 Pinyin 键盘输入简体中文或日语文本，但目前不支持使用 蓝牙 硬件键盘键入简体中文或日语文本。  但是，在中文或日语HoloLens，可以继续使用 蓝牙 键盘键入英语 (以切换硬件键盘以键入英语，按 ~ 键) 。
