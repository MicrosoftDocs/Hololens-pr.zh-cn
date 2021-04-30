---
title: 更新 HoloLens
description: 了解如何检查你的 HoloLens 生成号，保持最新的设备更新，加入预览体验计划，以及回滚更新。
keywords: 操作说明，更新，回滚，HoloLens，检查生成，生成号
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308426"
---
# <a name="update-hololens"></a>更新 HoloLens

HoloLens 使用 Windows 更新，就像其他 Windows 10 设备一样。 如果你的 HoloLens 处于待机状态并连接到 Internet，则它会自动下载并安装系统更新，即使它处于备用状态。

本文将指导你完成以下操作的 HoloLens 工具：

- 查看当前操作系统版本 (内部版本号) 
- 检查更新
- 手动更新 HoloLens
- 回退到较旧的更新

## <a name="check-your-operating-system-version-build-number"></a>检查操作系统版本 (生成号) 

您可以通过打开 "设置" 应用程序并选择 "**系统** 关于" 来验证系统版本号 (生成号)  >  。

## <a name="check-for-updates-and-manually-update"></a>检查更新并手动更新

你可以在 "设置" 中随时检查更新。  若要查看可用的更新并检查新的更新，请执行以下操作：

1. 打开“设置”应用  。
1. 导航到 "**更新 & 安全**  >  **Windows 更新**"。
1. 选择“检查更新”。

如果更新可用，则会开始下载新版本。 下载完成后，选择 " **立即重新启动** " 按钮以触发安装。 如果设备低于40% 且未接通电源，则重新启动将不会开始安装更新。

在 HoloLens 安装更新时，它会显示旋转的齿轮和进度指示器。 请勿在此时间关闭 HoloLens。 完成安装后，它将自动重新启动。

HoloLens 一次应用一个更新。  如果你的 HoloLens 超过了最新版本，则可能需要多次运行更新过程，以使其完全保持最新状态。

## <a name="go-back-to-a-previous-version---hololens-2"></a>返回到以前的版本-HoloLens 2

在某些情况下，你可能想要返回到以前版本的 HoloLens 软件。 为此，可以使用 "高级恢复助理" 将 HoloLens 重置为早期版本。

> [!NOTE]
> 返回到早期版本会删除你的个人文件和设置。

若要返回到 HoloLens 2 的以前版本，请执行以下步骤：

1. 请确保没有任何手机或 Windows 设备连接到您的 PC。
1. 在电脑上，从 Microsoft Store 下载 [高级恢复助理](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 。
1. 下载 [最新的 HoloLens 2 版本](https://aka.ms/hololens2download)。
1. 完成这些下载后，打开 **文件资源管理器**  >  **下载**。 右键单击刚下载的压缩文件夹，然后选择 "**提取所有**  >  **提取**" 将其解压缩。
1. 使用 USB-A 到 USB 电缆将你的 HoloLens 连接到你的电脑。 即使已使用其他电缆连接 HoloLens，也 (，这种方法的效果最佳。 ) 
1. 高级恢复助理会自动检测到 HoloLens。 选择 " **Microsoft HoloLens** " 磁贴。
1. 在下一个屏幕上，选择 " **手动包选择** "，然后选择在步骤4中解压缩的文件夹中包含的安装文件。  (查找扩展名为 ffu 的文件 ) 
1. 选择 " **安装软件**"，然后按照说明进行操作。

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>返回到以前的版本-HoloLens (第一代) 

在某些情况下，你可能想要返回到以前版本的 HoloLens 软件。 为此，可以使用 Windows 设备恢复工具将 HoloLens 重置为早期版本。

> [!NOTE]
> 返回到早期版本会删除你的个人文件和设置。

若要返回到以前版本的 HoloLens 1，请执行以下步骤：

1. 请确保没有任何手机或 Windows 设备连接到您的 PC。
1. 在电脑上，下载 [Windows 设备恢复工具 (WDRT) ](https://support.microsoft.com/help/12379)。
1. 下载 [HoloLens 周年更新恢复包](https://aka.ms/hololensrecovery)。
1. 下载完成后，打开 **文件资源管理器**  >  **下载**。 右键单击刚下载的压缩文件夹，然后选择 "**提取所有**  >  **提取**" 将其解压缩。
1. 使用随附的微 USB 电缆将您的 HoloLens 连接到您的 PC。 即使已使用其他电缆连接 HoloLens，也 (，这种方法的效果最佳。 ) 
1. WDRT 将自动检测你的 HoloLens。 选择 " **Microsoft HoloLens** " 磁贴。
1. 在下一个屏幕上，选择 " **手动包选择** "，然后选择在步骤4中解压缩的文件夹中包含的安装文件。  (查找扩展名为 ffu 的文件 ) 
1. 选择 " **安装软件**"，然后按照说明进行操作。

> [!NOTE]
> 如果 WDRT 未检测到 HoloLens，请尝试重新启动计算机。 如果这不起作用，请选择 **"未检测到设备**"，选择 " **Microsoft HoloLens**"，然后按照说明进行操作。

## <a name="windows-insider-program-on-hololens"></a>HoloLens 上的 Windows 预览体验计划

想要查看 HoloLens 中的最新功能？  如果是这样，请加入 Windows 预览体验计划;你将在更新 HoloLens 软件更新的预览版本之前获得对它们的访问权限。

[获取适用于 Microsoft HoloLens 的 Windows 预览体验预览](hololens-insider.md)。
