---
title: 重启、重置或恢复 HoloLens 1
ms.reviewer: Keep up to date on the basic and advanced instructions for rebooting or resetting your HoloLens mixed reality device.
description: 如何使用 Windows 设备恢复工具将映像刷刷到 HoloLens 第 1 代。
keywords: 操作说明、重启、重置、恢复、硬重置、软重置、电源周期、HoloLens、关闭、wdrt、Windows 设备恢复工具
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
ms.openlocfilehash: f855aa84a347edc85e5b9f02458721778eb2515a
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397688"
---
# <a name="restart-reset-or-recover-hololens-1st-gen"></a>重启、重置或恢复 HoloLens (第一代) 

如果遇到 HoloLens 问题，可能需要尝试重启或重置，甚至使用设备恢复来重启设备。 本文指导你按序完成建议的恢复步骤。

若要恢复服务，请参阅HoloLens 2恢复 [HoloLens 2，因为](https://docs.microsoft.com/hololens/hololens-recovery)该过程有所不同。

> [!NOTE]
> 本文重点介绍 HoloLens 设备和软件。 如果全息影像看起来不对，请参阅 **[HoloLens](hololens-environment-considerations.md)** 环境注意事项，了解提高全息影像质量的因素。

## <a name="restart"></a>重启

### <a name="do-a-safe-restart-by-using-cortana"></a>使用 Cortana 执行安全重启

重启 HoloLens 的最安全方法就是使用 Cortana，这通常是遇到 HoloLens 问题时要尝试的第一件事。

> [!NOTE] 
> Cortana 并非在所有设备上都可用。
> - Cortana 在所有 HoloLens (第一代) 设备上可用。 
> - 在 Windows Holograpic 版本 2004 更新之前HoloLens 2内部版本上的设备上提供 Cortana。

1. 打开 HoloLens。
1. 确保用户已登录，并且设备未等待密码解锁。
2. 说"你好，Cortana，重启"或"你好，Cortana，重启"。
3. Cortana 将做出响应并提示你确认。 等待问题后播放声音，然后说"是"。 设备将重启。

### <a name="use-the-power-button-to-do-a-safe-restart"></a>使用 "电源" 按钮执行安全重新启动

如果仍无法重新启动设备，请尝试使用 " **电源** " 按钮重新启动它：

1. 按住 **电源** 按钮5秒钟。 1秒后，所有五个 Led 都将发亮，然后慢慢地按从右到左的顺序关闭。 5秒钟后，所有 Led 都将关闭，指示已成功关闭。
      
   > [!IMPORTANT]
   > 在所有 Led 都关闭后立即停止按按钮。
1. 等待1分钟，让关闭完成。 即使在显示关闭后，关闭仍可能仍在进行中。
2. 按住 **电源** 按钮1秒钟，再次打开设备。

### <a name="do-a-safe-restart-by-using-windows-device-portal"></a>使用 Windows 设备门户执行安全重新启动

> [!NOTE]
> 对于此过程，必须将 HoloLens 配置为开发人员设备。 有关详细信息，请参阅 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。

如果前面的过程不起作用，请尝试使用 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)重新启动设备。 在右上角，找到重新启动或关闭设备的选项。

### <a name="do-an-unsafe-forced-restart"></a>执行不安全的强制重新启动

如果以前的方法未重启 HoloLens，请强制重新启动。 此方法等效于删除和重新安装电池。 这是很危险的，因为这可能会使你的设备处于损坏状态。 如果发生这种情况，则必须闪现 HoloLens。  

> [!WARNING]
> 这是潜在的有害方法，只应在以前引用的方法不起作用时使用。

1. 按住电源 **按钮** 至少 10 秒。
   - 可以按住按钮超过 10 秒。
   - 可以放心地忽略任何 LED 活动。
1. 释放按钮并等待 2-3 秒。
1. 按住 **电源按钮** 1 秒。
1. 如果仍有问题，请按电源按钮4 秒，直到所有电池指示器消失，屏幕停止显示全息影像。 等待 1 分钟，然后再次按 **电源** 按钮打开设备。

## <a name="reset-to-factory-settings"></a>重置为出厂设置

> [!NOTE]
> 电池需要至少 40% 的费用进行重置。

如果 HoloLens 仍有问题，请尝试将 HoloLens 重置为工厂状态。 此步骤将保留安装于该版本的 Windows Holographic 软件，将其他所有内容返回到工厂设置。

>[!WARNING]
> 如果重置设备，将清除所有个人数据、应用和设置，包括 TPM 重置信息。 重置将仅安装最新安装的 Windows Holographic 版本。 必须重新执行所有初始化步骤， (校准、连接到 Wi-Fi、创建用户帐户、下载应用) 。

1. 打开"设置"应用，然后选择"**更新恢复**  >  **"。**
1. 选择" **重置设备"** 选项并阅读确认消息。
1. 确认重置。 设备将重启并显示一组旋转齿轮和进度栏。
1. 等待大约 30 分钟，等待此过程完成。 完成后，设备将重启进入"开箱即用"体验。

## <a name="reinstall-the-operating-system"></a>重新安装操作系统

如果在重新启动并重置后设备仍有问题，你可以在计算机上使用恢复工具来重新安装 HoloLens 操作系统和固件。  

用于重置的 HoloLens 要求的数据将打包 (FFU) ，这与 .iso、.wim 或 .vhd 文件类似。 [了解 FFU 图像文件格式。](https://docs.microsoft.com/windows-hardware/manufacture/desktop/wim-vs-ffu-image-file-formats)

可以使用 Windows 设备恢复工具在 HoloLens (第一代) 上安装新操作系统。 使用该工具之前，请查看重新启动或重置 HoloLens 是否会解决此问题。

恢复过程可能需要一段时间。 完成后，将安装最新版本的 Windows 全息软件。

若要使用该工具，需要一台运行 Windows 10 或更高版本的计算机，其中至少有 4 GB 的可用存储空间。 不能在虚拟机上运行此工具。

### <a name="recover-your-hololens"></a>恢复 HoloLens

1. 在计算机上下载并安装 [Windows 设备恢复工具](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq) 。
1. 使用 HoloLens 随附的微 USB 电缆将 HoloLens (第一代) 连接到计算机。
1. 打开 Windows 设备恢复工具并按照说明进行操作。

如果未自动检测 HoloLens (第一代) ，请选择 **"我的设备未检测到"**。 然后按照说明将设备置于恢复模式。

### <a name="manual-flashing-mode"></a>手动闪烁模式

如果未检测到设备，请按照以下步骤将其置于闪烁模式：

1. 从任何电源拔出设备。
1. 如果设备已打开，请按住 **电源** 按钮，直到它完全关闭。
2. 按住 **音量向上** 按钮，然后短暂点击 **电源** 按钮。 设备应启动并仅显示中间 LED。
3. 将设备插入电脑。
4. 打开 Windows 设备恢复工具。
5. 选择 **"未检测到我的设备"，** 然后选择 **"HoloLens"。** 
6. 按照说明恢复设备。
