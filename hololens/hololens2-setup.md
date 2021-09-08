---
title: 准备使用全新 HoloLens 2
description: 了解如何首次设置和调整 HoloLens 2 设备，包括运行状况、安全提示和硬件指南。
keywords: hololens,灯光,适应,舒适,部件
ms.assetid: 02692dcf-aa22-4d1e-bd00-f89f51048e32
ms.date: 9/17/2019
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 2
ms.openlocfilehash: 77c061c53806e7410d73ecf3aaa20d74c217ea33
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190406"
---
# <a name="get-your-hololens-2-ready-to-use"></a>准备 HoloLens 2 以供使用

下面的步骤将帮助你完成 HoloLens 2 的首次设置。

## <a name="charge-your-hololens"></a>为 HoloLens 充电

使用 USB-C 线缆（随附）将电源与充电端口相连。 将电源插入电源插座。 设备附带的电源和 USB-C 到 C 电缆是为 HoloLens 2 充电的最佳方式。 充电器提供 18W 的电力（9V，2A）。 借助提供的壁式充电器，HoloLens 2 设备可在待机状态下在 65 分钟内将电池充满电。

充电率和速度可能因设备运行环境而异。

- 为设备充电时，电池指示灯将亮起，以指示当前的充电进度。  最后一盏灯将不停闪烁，表示正在充电。
- 当 HoloLens 处于打开状态时，电池指示灯以增量方式显示电池剩余电量。
- 当五盏灯中只有一盏亮起时，表示电池剩余电量低于 20%。
- 如果在电池剩余电量严重不足时你尝试打开设备，则一盏灯将会短暂闪烁，然后熄灭。

如需更多信息，可以[在此处参阅有关设备充电的全部详细信息](hololens2-charging.md#charging-the-device)。 

## <a name="adjust-fit"></a>调整到合适

将 HoloLens 2 戴在头上。 如果你佩戴眼镜，请勿将其摘下。  应将额头垫舒适地放在额头上，将背带放在头后部的中间位置。

如有必要，请转动调节轮来展开头带，然后松开顶部固定带。

![HoloLens 2 舒适佩戴和调整。](images/hololens2-fit.png)

### <a name="attach-and-detach-the-overhead-strap"></a>连接和断开顶部固定带

顶部固定带不是必需的，但它可以使 HoloLens 2 在长时间使用时佩戴更舒适。

要断开顶部固定带的正面，请解开固定带并通过额头垫上的可伸缩环滑动它。 要重新连接，请拉出环并滑动固定带。

要断开顶部固定带的背面，请按每个连接标签下方的按钮并轻轻拉一下。 要重新连接，请将连接标签推回到插槽中，直到听见咔哒声。

![连接或取下 HoloLens 2 头带。](images/hololens2-headstrap.png)

## <a name="turn-on-the-hololens-2"></a>打开 HoloLens 2

要打开 HoloLens 2，请按电源按钮。  电源按钮下方的 LED 将显示电池剩余电量。

> [!NOTE]
> 要首次打开 HoloLens 2，请在开箱后长按电源按钮至少 4 秒钟，将其打开。 下一次打开 HoloLens 2 时，它将在短暂按下电源按钮后启动。

### <a name="power-button-actions-for-different-power-transitions"></a>适用于不同电源转换的电源按钮操作

| 要执行此操作 | 执行此操作 | HoloLens 2 将执行此操作 |
| - | - | - |
| 打开 | 按下按钮一次。 | 所有五盏灯亮起，然后变为指示电池剩余电量。 4 秒后，播放一段声音。 |
| 进入睡眠状态 | 按下按钮一次。 | 所有五盏灯亮起，然后一次熄灭一盏。 熄灯后，将播放一段声音，屏幕显示“再见”。 |
| 从睡眠状态唤醒 | 按下按钮一次。 | 所有五盏灯亮起，然后变为指示电池剩余电量。 将立即播放声音。 |
| 关闭 | 长按 5 秒。 |  所有五盏灯亮起，然后一次熄灭一盏。 熄灯后，将播放一段声音，屏幕显示“再见”。 |
| 强制重启 HoloLens（如果它没有响应） | 长按 10 秒。 | 所有五盏灯亮起，然后一次熄灭一盏。 熄灯后。 |

## <a name="hololens-behavior-reference"></a>HoloLens 行为参考

不确定 HoloLens 上的指示灯表示什么？ 想了解 HoloLens 在充电时会有什么表现？  下面是一些帮助！

### <a name="charging-behavior"></a>充电行为

| 设备的状态 | 操作 | HoloLens 2 将执行以下操作 |
| - | - | - |
| OFF | 插入 USB 电缆 | 设备转换为开启状态，指示灯显示电池剩余电量，设备开始充电。
| ON | 移除 USB 电缆 | 设备停止充电
| ON | 插入 USB 电缆 | 设备开始充电
| 睡眠 | 插入 USB 电缆 | 设备开始充电
| 睡眠 | 移除 USB 电缆 | 设备停止充电
| 插入 USB 电缆时开启 | 关闭设备 | 设备转换为开启状态，指示灯显示电池剩余电量，设备开始充电 |

### <a name="lights-that-indicate-the-battery-level"></a>指示电池剩余电量的灯

| 灯的数量 | 电池剩余电量 |
| - | - |
| 四盏常亮灯，一盏闪烁灯 | 介于 100% 与 81%（完全充电）之间 |
| 三盏常亮灯，一盏闪烁灯 | 介于 80% 和 61% 之间 |
| 两盏常亮灯，一盏闪烁灯 | 介于 60% 和 41% 之间 |
| 一盏常亮灯，一盏闪烁灯 | 介于 40% 和 21% 之间 |
| 一盏闪烁灯 | 介于 20% 与 5% 之间或更低（电量严重不足） |

### <a name="sleep-behavior"></a>睡眠行为

| 设备的状态 | 操作 | HoloLens 2 将执行以下操作 |
| - | - | - |
| ON | 按下单电源按钮 | 设备转换至睡眠状态，并关闭所有指示灯 |
| ON | 3 分钟不移动 | 设备转换至睡眠状态，并关闭所有指示灯 |
| 睡眠 | 按下单电源按钮 | 设备转换为开启状态，并打开指示灯 |

### <a name="lights-to-indicate-problems"></a>指示存在问题的灯

| 执行此操作时 | 指示灯执行此操作 | 这意味着 |
| - | - | - |
| 你按下电源按钮。 | 一盏灯闪烁五次，然后熄灭。 | HoloLens 电池电量严重不足。 为 HoloLens 充电。 |
| 你按下电源按钮。 | 所有五盏灯闪烁五次，然后熄灭。 |  HoloLens 无法正常启动，且处于错误状态。 [重新安装操作系统](hololens-recovery.md)以恢复设备。 |
| 你按下电源按钮。 | 第一个、第三个和第五个灯一起连续闪烁。 |  HoloLens 可能存在硬件失败。 联系[支持人员](https://support.microsoft.com/en-us/supportforbusiness/productselection?sapid=3ec35c62-022f-466b-3a1e-dbbb7b9a55fb)。 |

## <a name="safety-and-comfort"></a>安全和舒适

### <a name="use-hololens-in-safe-surroundings"></a>在安全的环境中使用 HoloLens

在没有障碍物和绊倒危险的安全空间内使用 HoloLens。 如果你需要清晰的视野或者不能集中注意力（比如，开车或者做其他可能存在危险的事情时），请不要使用它。

### <a name="stay-comfortable"></a>保持舒适

通过 HoloLens 进行的前几次互动要简短，并且中间一定要休息。 如果觉得不舒服，请停下休息，感觉好些后再继续。 这可能包括暂时的恶心、晕车、头晕、迷失方向、头痛、疲劳、眼疲劳或干眼。

参阅[产品安全警告和说明](https://support.microsoft.com/help/4558037/product-safety-warnings-and-instructions)。

> [!div class="nextstepaction"]
> [设置 HoloLens 2](hololens2-start.md)
