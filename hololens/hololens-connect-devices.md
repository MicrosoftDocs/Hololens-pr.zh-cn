---
title: 连接到蓝牙和 USB-C 设备
description: 开始从 HoloLens 混合现实设备连接到蓝牙和 USB-C 设备及附件。
ms.assetid: 01af0848-3b36-4c13-b797-f38ad3977e30
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 03/11/2020
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 1b4f95f43fc60dffa2ca75322466857a0a20a0a7
ms.sourcegitcommit: 145bbabc390f626ba6633fa49423c38656cd2224
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "11302266"
---
# 连接到蓝牙和 USB-C 设备

> [!NOTE]
> 无法使用外置麦克风。 HoloLens 2 使用内置 [麦克风阵列](hololens2-hardware.md#audio-and-speech)。

## 配对蓝牙设备

HoloLens 2 支持以下类别的蓝牙设备：

- 鼠标
- 键盘
- 蓝牙音频输出 (A2DP) 设备

HoloLens（第 1 代）支持以下类别的蓝牙设备：

- 鼠标
- 键盘
- HoloLens（第 1 代）点击器

> [!NOTE]
> 其他类型的蓝牙设备（例如，扬声器、耳机、智能手机和游戏板）可能会在 HoloLens 设置中列为可用。 但是，HoloLens（第 1 代）上不支持这些设备。 有关详细信息，请参阅 [HoloLens 设置将设备列为可用，但设备无法正常工作](hololens-FAQ.md#hololens-settings-lists-devices-as-available-but-the-devices-dont-work)。

### 配对蓝牙键盘或鼠标

1. 打开键盘或鼠标，使其能够被检测到。 若要了解如何使设备可被检测到，请在设备（或其文档）中查找相关信息或访问制造商的网站。

1. 使用开花手势（HoloLens [第 1 代]）或开始手势 (HoloLens 2) 转到“开始”****，然后选择“设置”****。

1. 选择“设备”****，并确保已启用蓝牙。  

1. 看到设备名称后，选择“配对”****，然后按照说明进行操作。

### HoloLens（第 1 代）：配对点击器

1. 使用开花手势转到“开始”****，然后选择“设置”****。

1. 选择“设备”****，并确保已启用蓝牙。

1. 使用笔尖长按点击器配对按钮，直到点击器状态灯呈白色闪烁。 请确保按住该按钮直至指示灯开始闪烁。  

   配对按钮在点击器的底部，指环旁边。

   ![配对按钮在指环旁边](images/use-hololens-clicker-1.png)

1. 在配对屏幕上，选择“点击器****” > “配对****”。

## 禁用蓝牙

此程序将关闭蓝牙无线电收发器的 RF 组件，并禁用 Microsoft HoloLens 上的所有蓝牙功能。

1. 使用开花手势（HoloLens [第 1 代]）或开始手势 (HoloLens 2) 转到“开始”****，然后选择“设置”**** > “设备”****。

1. 将“蓝牙”**** 的滑块开关移至“关闭”**** 位置。

## HoloLens 2：连接 USB-C 设备

HoloLens 2 支持以下类别的 USB-C 设备：

- 大容量存储设备（如 U 盘）
- 以太网适配器（包括以太网 + 充电）
- USB-C 转 3.5 毫米数字音频适配器
- USB-C 数字音频耳机（包括耳机适配器 + 充电）
- 有线鼠标
- 有线键盘
- 组合 PD 集线器（USB A + PD 充电）

> [!NOTE]
> 一些具有 USB-C 连接的移动设备会将自身作为以太网适配器呈现给 HoloLens，因此可在网络共享配置中使用（从 Windows Holographic 2004 版本开始）。 不支持需要单独的驱动程序和/或通过安装的应用程序进行配置的 USB LTE 调制解调器。

为了回应客户的反馈，我们已通过 USB-C 为直接连接到 HoloLens 的蜂窝网络提供有限的支持。  连接的网络仅适用于支持通用 Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) 驱动程序实施的设备，且不需要安装任何其他驱动程序或应用程序。  连接后，此类设备将在 HoloLens 2 网络设置 UI 中自动显示为新的以太网连接。 请联系设备的制造商，咨询其是否支持通用 Microsoft RNDIS 驱动程序的更多详细信息。

### USB-C集线器

某些用户可能需要一次连接多个设备。 对于想要预览体验成员功能和与其他已连接设备一起 [使用 USB-C 麦克风](hololens-insider.md#usb-c-external-microphone-support) 的用户，USB-C 集线器可能满足其需求。 Microsoft 尚未测试这些设备，我们也不能推荐任何特定品牌。

**USB-C 集线器和已连接设备的要求：**

- 连接的设备不得要求安装驱动程序。
- 所有已连接设备的总功耗必须低于 4.5 瓦。

## 连接到 Miracast

若要使用 Miracast，请按照下列步骤进行操作：

1. 执行下列操作之一：  

   - 打开“开始”**** 菜单，然后选择显示图标。
   - 盯着“开始”**** 菜单说“连接”。  

1. 在所显示设备的列表中，选择一个可用的设备。

1. 完成配对，开始进行投影。
