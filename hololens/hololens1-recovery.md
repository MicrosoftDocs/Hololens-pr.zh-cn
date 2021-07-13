---
title: 重启、重置或恢复HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: 如何使用设备Windows工具将映像刷刷到第一代HoloLens映像。
keywords: 操作说明、重启、重置、恢复、硬重置、软重置、电源循环、HoloLens、关闭、wdrt、Windows 设备恢复工具
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.date: 06/01/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: medium
manager: yannisle
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 4840535030cc81f222cb25357474f1c751426e91
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635222"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>重启、重置或恢复HoloLens (第一代) 

如果遇到设备问题，HoloLens尝试重启或重置，甚至使用设备恢复来重新运行设备。 本文指导你按序完成建议的恢复步骤。

如果要恢复服务，请参阅HoloLens 2恢复[HoloLens 2，因为](hololens-recovery.md)该过程有所不同。

> [!NOTE]
> 本文重点介绍HoloLens和软件。 如果全息影像看起来不正确，请参阅HoloLens环境注意事项，**[](hololens-environment-considerations.md)** 了解提高全息影像质量的因素。

## <a name="restart"></a>重启

### <a name="do-a-safe-restart-by-using-cortana"></a>使用安全重启Cortana

重启 HoloLens 的最安全Cortana是使用 Cortana，这通常是遇到问题时要尝试的第一HoloLens。

> [!NOTE] 
> Cortana并非在所有设备上都可用。
> - Cortana第一代HoloLens (设备上均) 可用。 
> - Cortana Holograpic 版本 2004 更新HoloLens 2版本之前，Windows设备上可用。

1. 打开HoloLens。
1. 确保用户已登录，并且设备未等待密码解锁。
2. 说"你好，Cortana，重启"或"你好Cortana，重启"。
3. Cortana响应并提示你确认。 等待问题后播放声音，然后说"是"。 设备将重启。

### <a name="use-the-power-button-to-do-a-safe-restart"></a>使用电源按钮执行安全重启

如果仍无法重启设备，请尝试使用电源按钮 **重启** 设备：

1. 按住电源 **按钮** 5 秒。 1 秒后，所有五个 LED 都会亮起，然后从右到左缓慢地一个地关闭。 5 秒后，所有 LED 都将关闭，表示已成功关闭。
      
   > [!IMPORTANT]
   > 在所有 LED 关闭后立即停止按下按钮。
1. 等待 1 分钟，关闭完成。 即使关闭显示器，关闭也可能仍在进行中。
2. 通过按住电源按钮 1 秒再次打开设备。

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>使用安全重启Windows 设备门户

> [!NOTE]
> 对于此过程，HoloLens必须配置为开发人员设备。 有关详细信息[，Windows 设备门户。](/windows/mixed-reality/using-the-windows-device-portal)

如果上一过程不起作用，请尝试使用 Windows 设备门户[重启设备](/windows/mixed-reality/using-the-windows-device-portal)。 在右上角，找到重启或关闭设备的选项。

### <a name="do-an-unsafe-forced-restart"></a>执行不安全的强制重启

如果前面的方法未重启HoloLens，请强制重启。 此方法等效于删除并重新安装电池。 这十分危险，因为它可能会使设备保持损坏状态。 如果发生这种情况，必须刷出HoloLens。  

> [!WARNING]
> 这是一种可能有害的方法，应仅在前面引用的方法不起作用时使用。

1. 按住电源 **按钮** 至少 10 秒。
   - 可以按住按钮超过 10 秒。
   - 可以放心地忽略任何 LED 活动。
1. 释放按钮并等待 2-3 秒。
1. 按住 **电源按钮** 1 秒。
1. 如果仍有问题，请按电源按钮4 秒，直到所有电池指示器消失，屏幕停止显示全息影像。 等待 1 分钟，然后再次按 **电源** 按钮打开设备。

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>返回到以前的版本 - HoloLens (第一代) 

在某些情况下，你可能想要返回到早期版本的 HoloLens 软件。 为此，可以使用 Windows Device Recovery 工具将HoloLens重置为早期版本。

> [!NOTE]
> 返回到早期版本会删除个人文件和设置。

若要返回到早期版本的 HoloLens 1，请执行以下步骤：

1. 请确保未将任何手机或Windows设备插入电脑。
1. 在电脑上，下载[WINDOWS 设备恢复工具 (WDRT) 。 ](https://support.microsoft.com/help/12379)
1. 下载 HoloLens[周年更新恢复包](https://aka.ms/hololensrecovery)。
1. 下载完成后，打开"文件 **资源管理器**  >  **下载"。** 右键单击刚下载的压缩文件夹，然后选择"**提取所有**  >  **提取**"将其解压缩。
1. 连接HoloLens微型 USB 电缆将设备连接到电脑。  (即使一直在使用其他电缆来连接HoloLens，此电缆也效果最佳。) 
1. WDRT 会自动检测HoloLens。 选择 **"Microsoft HoloLens** 磁贴。
1. 下一个屏幕选择" **手动包** 选择"，然后选择步骤 4 中解压缩的文件夹中包含的安装文件。  (查找扩展名为 .ffu.) 
1. 选择 **"安装软件**"，并按照说明进行操作。

> [!NOTE]
> 如果 WDRT 未检测到你的HoloLens，请尝试重启电脑。 如果不起作用，请选择"未检测到我的设备 **"，** 选择 **Microsoft HoloLens，然后** 按照说明操作。

## <a name="reset-to-factory-settings"></a>重置为出厂设置

> [!NOTE]
> 电池需要至少 40% 的费用进行重置。

如果HoloLens仍然存在问题，请尝试将问题重置为工厂状态。 此步骤将保留安装Windows全息软件的版本，并返回工厂设置中其他所有内容。

>[!WARNING]
> 如果重置设备，将清除所有个人数据、应用和设置，包括 TPM 重置信息。 重置将仅安装 Holographic Windows版本。 必须重新执行所有初始化步骤， (校准、连接到 Wi-Fi、创建用户帐户、下载应用) 。

1. 打开设置应用，然后选择"更新 **恢复**  >  **"。**
1. 选择" **重置设备"** 选项并阅读确认消息。
1. 确认重置。 设备将重启并显示一组旋转齿轮和进度栏。
1. 等待大约 30 分钟，等待此过程完成。 完成后，设备将重启进入"开箱即用"体验。

## <a name="reinstall-the-operating-system"></a>重新安装操作系统

如果重启和重置后设备仍然出现问题，可以使用计算机上恢复工具重新安装HoloLens和固件。  

重置HoloLens数据打包在完全闪存更新 (FFU) 中，类似于 .iso、.wim 或 .vhd 文件。 [了解 FFU 图像文件格式。](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

可以使用设备恢复工具HoloLens (第一代) 安装Windows操作系统。 使用该工具之前，请参阅重新启动或重置HoloLens问题。

恢复过程可能需要一段时间。 完成后，将安装最新版本Windows全息软件。

若要使用该工具，需要一台运行 Windows 10 或更高版本的计算机，该计算机至少具有 4 GB 的可用存储空间。 无法对虚拟机运行此工具。

### <a name="recover-your-hololens"></a>恢复HoloLens

1. 在计算机上下载Windows[设备](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)恢复工具。
1. 连接HoloLens (设备) Micro USB 电缆将第一代设备连接到HoloLens。
1. 打开"Windows恢复工具"并按照说明进行操作。

如果未HoloLens (第一代) ，请选择"未 **检测到我的设备"。** 然后按照说明将设备置于恢复模式。

### <a name="manual-flashing-mode"></a>手动闪烁模式

如果未检测到设备，请按照以下步骤将设备置于闪烁模式：

1. 从任何电源拔下设备。
1. 如果设备已打开，请按住 **电源** 按钮，直到完全关闭。
2. 按住 " **音量向上** " 按钮，并单击 " **电源** " 按钮。 设备应启动并仅显示中间 LED。
3. 将设备插入 PC。
4. 打开 Windows 设备恢复工具。
5. **未检测到 "我的设备"** ，然后 **HoloLens**。 
6. 按照说明恢复你的设备。
