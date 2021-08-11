---
title: 更新HoloLens 2
description: 了解如何检查内部HoloLens号、随时了解设备更新、加入预览体验计划以及回滚更新。
keywords: 操作说明、更新、回滚、HoloLens、检查生成、生成号
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
- HoloLens 2
ms.openlocfilehash: 7e63fcab4c64f151684a634bb24d9fc31826f6805d52b23c5672add0b6269430
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662834"
---
# <a name="update-hololens-2"></a>更新HoloLens 2

HoloLens使用 Windows Update，就像其他 Windows 10 设备一样。 只要HoloLens电源并连接到 Internet，即使系统处于待机状态，系统也会自动下载并安装系统更新。

本文将演练适用于HoloLens工具：

- 查看当前操作系统版本 (版本号) 
- 检查更新
- 手动更新HoloLens
- 回滚到较旧的更新

## <a name="check-your-operating-system-version-build-number"></a>检查操作系统版本 (版本号) 

可以验证系统版本号、 (内部版本号) 打开 设置应用并选择"系统关于  >  **"。**

## <a name="check-for-updates-and-manually-update"></a>检查更新并手动更新

你随时都可以在设置中检查更新。  查看可用更新并检查新更新：

1. 打开“设置”应用  。
1. 导航到"**更新&安全性**  >  **Windows更新"。**
1. 选择“检查是否有更新”。

如果更新可用，它将开始下载新版本。 下载完成后，选择"立即 **重启"** 按钮以触发安装。 如果设备低于 40% 且未接通电源，重启将不会开始安装更新。

在HoloLens安装更新时，它将显示旋转齿轮和进度指示器。 在此期间不要关闭HoloLens。 安装完成后，它将自动重启。

HoloLens一次应用一个更新。  如果HoloLens版本比最新版本晚一个版本，可能需要多次运行更新过程，才能完全更新。

## <a name="go-back-to-a-previous-version"></a>返回到以前的版本

在某些情况下，你可能想要返回到早期版本的 HoloLens 软件。 建议的步骤包括：

1. 请联系支持人员，看他们能否修复你的问题。
    1. 确保已启用 **"** 可选 **"** 或"完整"遥测 - 这使 bug 更具可操作性，更易于工程师诊断。
    1. [文件反馈](hololens-feedback.md) 尽可能具有描述性。 记下标题或使用共享功能，以便与支持人员共享 bug。
    1. 请联系 [支持](https://aka.ms/hlsupport)部门。 如果你的问题需要返回到以前的版本来解决，他们可以提供 FFU 来刷用设备。

1. 如果不起作用，则使用高级恢复助手 HoloLens 2[重置或重新使恢复状态](hololens-recovery.md)为 。
    1. 在电脑上，从计算机[下载高级](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab)恢复Microsoft Store。
    1. 请确保未将任何手机或Windows设备插入电脑。
    1. 选择要刷刷到哪个版本：
        1. 可以下载最新的[HoloLens 2 版本](https://aka.ms/hololens2download)。
        1. 可以使用 ARC 托管的默认生成。  (如果选择此选项，请跳过下一步。) 
        1. 可以使用提供的生成支持。
    1. 完成这些下载后，打开"下载  >  **文件资源管理器"**。 右键单击刚下载的压缩文件夹，然后选择"**提取所有**  >  **提取**"将其解压缩。
    1. 连接 USB-A HoloLens USB-C 电缆将设备连接到电脑。  (即使一直在使用其他电缆来连接HoloLens，此电缆也效果最佳。) 
    1. 高级恢复助手会自动检测HoloLens。 选择“Microsoft HoloLens”磁贴。
    1. 下一个屏幕上，选择"手动包选择"，然后选择步骤 4 中解压缩的文件夹中包含的安装文件。  (查找扩展名为 .ffu.) 
    1. 选择 **"安装软件**"，并按照说明进行操作。

> [!NOTE]
> 返回到早期版本会删除个人文件和设置。

此外，如果要保持当前安装的版本，还可以手动暂停 [更新](hololens-updates.md#pause-updates-via-device)。 这将为工程团队提供修复问题的时间。

## <a name="windows-insider-program-on-hololens"></a>Windows会员计划上HoloLens

想要查看中的最新功能HoloLens？  如果是这样，请联接Windows 会员计划;在向公众提供软件更新之前HoloLens预览内部版本。

[获取 Windows 预览体验成员Microsoft HoloLens。](hololens-insider.md)
