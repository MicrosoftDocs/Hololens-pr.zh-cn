---
title: 重新启动、重置或恢复 HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: 如何使用 Windows 设备恢复工具将映像闪存到 HoloLens 第一代。
keywords: 操作方法、重新启动、重置、恢复、硬重置、软重置、电源周期、HoloLens、关机、wdrt、windows 设备恢复工具
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
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032130"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>重新启动、重置或恢复 (第一代 HoloLens) 

如果 HoloLens 遇到问题，可能需要尝试重新启动或重置，甚至通过使用设备恢复刷新设备。 本文将指导你按顺序执行建议的恢复步骤。

如果你希望恢复 HoloLens 2，请参阅[恢复 HoloLens 2](hololens-recovery.md)，因为该过程有所不同。

> [!NOTE]
> 本文重点介绍 HoloLens 设备和软件。 如果你的全息影像看起来不正确，请参阅 **[HoloLens 环境注意事项](hololens-environment-considerations.md)**，了解有关改善全息影像质量的因素的信息。

## <a name="restart"></a>重启

### <a name="do-a-safe-restart-by-using-cortana"></a>使用 Cortana 执行安全重新启动

重新启动 HoloLens 的最安全方法是使用 Cortana，这通常是在遇到 HoloLens 问题时首先要尝试的事情。

> [!NOTE] 
> Cortana 在所有设备上都不可用。
> - Cortana 在所有 HoloLens (第一代) 设备上可用。 
> - Windows Holograpic 版本2004更新之前 HoloLens 2 设备上提供 Cortana。

1. 打开 HoloLens。
1. 请确保用户已登录，且设备未等待密码来解锁。
2. 说 "你好 Cortana，restart" 或 "你好 Cortana，restart"。
3. Cortana 将做出响应，并提示你进行确认。 等待一段时间后播放声音，然后说 "是"。 设备将重新启动。

### <a name="use-the-power-button-to-do-a-safe-restart"></a>使用 "电源" 按钮执行安全重新启动

如果仍无法重新启动设备，请尝试使用 " **电源** " 按钮重新启动它：

1. 按住 **电源** 按钮5秒钟。 1秒后，所有五个 Led 都将发亮，然后慢慢地按从右到左的顺序关闭。 5秒钟后，所有 Led 都将关闭，指示已成功关闭。
      
   > [!IMPORTANT]
   > 在所有 Led 都关闭后立即停止按按钮。
1. 等待1分钟，让关闭完成。 即使在显示关闭后，关闭仍可能仍在进行中。
2. 按住 **电源** 按钮1秒钟，再次打开设备。

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>使用 Windows 设备门户执行安全重新启动

> [!NOTE]
> 对于此过程，必须将 HoloLens 配置为开发人员设备。 [Windows 设备门户](/windows/mixed-reality/using-the-windows-device-portal)上了解详细信息。

如果前面的过程不起作用，请尝试使用[Windows 设备门户](/windows/mixed-reality/using-the-windows-device-portal)重新启动设备。 在右上角，找到重新启动或关闭设备的选项。

### <a name="do-an-unsafe-forced-restart"></a>执行不安全的强制重新启动

如果以前的方法没有重新启动 HoloLens，请强制重新启动。 此方法等效于删除和重新安装电池。 这是很危险的，因为这可能会使你的设备处于损坏状态。 如果发生这种情况，则必须刷新 HoloLens。  

> [!WARNING]
> 这是潜在的有害方法，只应在以前引用的方法不起作用时使用。

1. 按住 **电源** 按钮至少10秒。
   - 可以保持按钮超过10秒。
   - 忽略任何 LED 活动是安全的。
1. 释放按钮，等待2-3 秒。
1. 按住 **电源** 按钮1秒。
1. 如果仍有问题，请按下 **电源** 按钮4秒钟，直到所有电池指示器都淡出并且屏幕停止显示全息影像。 等待1分钟，然后再次按 **电源** 按钮打开设备。

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a>返回到 (第一代 HoloLens 第一版) 

在某些情况下，你可能希望返回到 HoloLens 软件的以前版本。 为此，可以使用 Windows 设备恢复工具将 HoloLens 重置为早期版本。

> [!NOTE]
> 返回到早期版本会删除你的个人文件和设置。

若要返回到 HoloLens 1 的以前版本，请执行以下步骤：

1. 请确保没有任何手机或 Windows 设备连接到 PC。
1. 在电脑上，下载[Windows 设备恢复工具 (WDRT) ](https://support.microsoft.com/help/12379)。
1. 下载 [HoloLens 周年更新恢复包](https://aka.ms/hololensrecovery)。
1. 下载完成后，打开 **文件资源管理器**  >  **下载**。 右键单击刚下载的压缩文件夹，然后选择 "**提取所有**  >  **提取**" 将其解压缩。
1. 使用附带的微 USB 电缆将你的 HoloLens 连接到你的电脑。 即使已使用其他电缆来连接 HoloLens， (也是如此。 ) 
1. WDRT 会自动检测 HoloLens。 选择“Microsoft HoloLens”磁贴。
1. 在下一个屏幕上，选择 " **手动包选择** "，然后选择在步骤4中解压缩的文件夹中包含的安装文件。  (查找扩展名为 ffu 的文件 ) 
1. 选择 " **安装软件**"，然后按照说明进行操作。

> [!NOTE]
> 如果 WDRT 未检测到 HoloLens，请尝试重新启动计算机。 如果重启不起作用，请选择“未检测到我的设备”，选择“Microsoft HoloLens”，然后按照说明操作。

## <a name="reset-to-factory-settings"></a>重置为出厂设置

> [!NOTE]
> 电池需要至少40% 的电量才能重置。

如果 HoloLens 仍有问题，请尝试将其重置为出厂状态。 此步骤保留安装在其中的 Windows 全息软件的版本，并将其他所有内容返回到出厂设置。

>[!WARNING]
> 如果重置设备，将擦除所有个人数据、应用和设置，包括 TPM 重置信息。 重置将仅安装 Windows 全息版的最新安装版本。 必须重做所有初始化步骤 (校准、连接到 Wi-fi、创建用户帐户、下载应用，等等) 。

1. 打开设置应用，然后选择 "**更新**  >  **恢复**"。
1. 选择 " **重置设备** " 选项并阅读确认消息。
1. 确认重置。 设备将重新启动并显示一组旋转齿轮和一个进度栏。
1. 等待大约30分钟才能完成此过程。 完成后，设备将重新启动进入 "现成" 体验。

## <a name="reinstall-the-operating-system"></a>重新安装操作系统

如果在重新启动并重置后设备仍有问题，你可以在计算机上使用恢复工具来重新安装 HoloLens 的操作系统和固件。  

重置 HoloLens 所需的数据将打包 (FFU) 的完整闪存更新中，该更新类似于 .iso、.wim 或 .vhd 文件。 [了解 FFU 图像文件格式。](/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

你可以使用 Windows 设备恢复工具在 HoloLens (1 代) 上安装新操作系统。 使用该工具之前，请查看重新启动或重置 HoloLens 是否修复了此问题。

恢复过程可能需要一段时间。 完成后，将安装最新版本的 Windows 全息软件。

若要使用该工具，需要一台运行 Windows 10 或更高版本的计算机，其中至少有 4 GB 的可用存储空间。 不能在虚拟机上运行此工具。

### <a name="recover-your-hololens"></a>恢复 HoloLens

1. 在计算机上下载并安装[Windows 设备恢复工具](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)。
1. 使用 HoloLens 附带的微 USB 电缆将 HoloLens (第一代) 连接到计算机。
1. 打开 Windows 设备恢复工具，然后按照说明进行操作。

如果未自动检测到 HoloLens (第一代) ，则 **未检测到 "我的设备**"。 然后按照说明将设备置于恢复模式。

### <a name="manual-flashing-mode"></a>手动闪烁模式

如果未检测到设备，请按照以下步骤将其置于闪烁模式：

1. 从任何电源拔出设备。
1. 如果设备已打开，请按住 **电源** 按钮，直到它完全关闭。
2. 按住 **音量向上** 按钮，然后短暂点击 **电源** 按钮。 设备应启动并仅显示中间 LED。
3. 将设备插入电脑。
4. 打开"Windows恢复工具"。
5. 选择 **"未检测到我的设备"，** 然后选择 **"HoloLens"。** 
6. 按照说明恢复设备。
