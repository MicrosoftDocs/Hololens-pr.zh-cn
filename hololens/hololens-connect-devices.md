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
ms.openlocfilehash: d9c8b813ba54edbcfef8d1a32e641dad39a7f193
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427726"
---
# <a name="connect-to-bluetooth-and-usb-c-devices"></a>连接到蓝牙和 USB-C 设备

## <a name="pair-bluetooth-devices"></a>配对蓝牙设备

HoloLens 2 支持以下类别的蓝牙设备：

- [HID](/windows-hardware/drivers/hid/)：
    - 鼠标
    - Keyboard
- 音频输出 (A2DP) 设备

HoloLens 2 支持以下蓝牙 API：
- GATT [服务器](/windows/uwp/devices-sensors/gatt-server)和[客户端](/windows/uwp/devices-sensors/gatt-client)
- [RFCOMM](/windows/uwp/devices-sensors/send-or-receive-files-with-rfcomm)
>[!IMPORTANT]
> 你可能必须从 Microsoft Store 安装相应的伴侣应用才能实际使用 HID 和 GATT 设备。

HoloLens（第 1 代）支持以下类别的蓝牙设备：

- 鼠标
- Keyboard
- [HoloLens（第 1 代）点击器](hololens1-clicker.md)

> [!NOTE]
> 其他类型的蓝牙设备（例如，扬声器、耳机、智能手机和游戏板）可能会在 HoloLens 设置中列为可用。 但是，HoloLens（第 1 代）上不支持这些设备。 有关详细信息，请参阅 [HoloLens 设置将设备列为可用，但设备无法使用](hololens-troubleshooting.md#devices-listed-as-available-in-settings-dont-work)。

### <a name="pair-a-bluetooth-keyboard-or-mouse"></a>配对蓝牙键盘或鼠标

1. 打开键盘或鼠标，使其能够被检测到。 若要了解如何使设备可被检测到，请在设备（或其文档）中查找相关信息或访问制造商的网站。

1. 使用开花手势（HoloLens [第 1 代]）或开始手势 (HoloLens 2) 转到“开始”，然后选择“设置”。

1. 选择“设备”，并确保已启用蓝牙。  

1. 看到设备名称后，选择“配对”，然后按照说明操作。

## <a name="disable-bluetooth"></a>禁用蓝牙

此程序将关闭蓝牙无线电收发器的 RF 组件，并禁用 Microsoft HoloLens 上的所有蓝牙功能。

1. 使用开花手势（HoloLens [第 1 代]）或开始手势 (HoloLens 2) 转到“开始”，然后选择“设置” > “设备”。

1. 将“蓝牙”的滑块开关移至“关闭”位置。

## <a name="hololens-2-connect-usb-c-devices"></a>HoloLens 2：连接 USB-C 设备

HoloLens 2 支持以下类别的 USB-C 设备：

- 大容量存储设备（如 U 盘）
- 以太网适配器（包括以太网 + 充电）
- USB-C 转 3.5 毫米数字音频适配器
- USB-C 数字音频耳机（包括耳机适配器 + 充电）
- USB-C 外置麦克风（[Windows 全息版 21H1](hololens-release-notes.md#windows-holographic-version-21h1) 及更高版本）
- 有线鼠标
- 有线键盘
- 组合 PD 集线器（USB A + PD 充电）


> [!NOTE]
> 为了回应客户的反馈，我们已通过 USB-C 向直接连接到 HoloLens 的手机网络连接提供有限的支持。 有关详细信息，请参阅[连接到手机网络和 5G](hololens-cellular.md)。

### <a name="usb-c-external-microphone-support"></a>USB-C 外置麦克风支持

> [!IMPORTANT]
> 插入 **USB 麦克风不会自动将其设置为输入设备**。 当插入一组 USB-C 耳机时，用户会看到耳机音频将自动重定向到耳机，但 HoloLens OS 会将内置麦克风阵列的优先级优于任何其他输入设备。 若要使用 USB-C 麦克风，请执行以下步骤。

> [!NOTE]
> 在 [Windows 全息版 21H1](hololens-release-notes.md#windows-holographic-version-21h1) 及更高版本之前的内部版本中，不能使用外置麦克风。 

用户可以使用“声音”设置面板选择 USB-C 连接的外置麦克风。 USB-C 麦克风可用于呼叫、录制等。

打开“设置”应用并选择“系统” > “声音”。

![声音设置。](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 若要将外置麦克风用于 Remote Assist，用户需要单击“管理声音设备”超链接。
>
> 然后，使用下拉菜单将外置麦克风设置为“默认值”或“通信默认值”。 选择“默认值”表示将在任何位置使用外置麦克风。
>
> 选择“通信默认值”表示将在 Remote Assist 和其他通信应用中使用外置麦克风，但 HoloLens 麦克风阵列仍可用于其他任务。

![管理声音设备。](images/usbc-mic-2.png)

<br>

![设置麦克风默认值。](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>蓝牙麦克风支持怎么样？

遗憾的是，HoloLens 2 目前仍不支持蓝牙麦克风。

### <a name="usb-c-hubs"></a>USB-C 集线器

某些用户可能需要一次连接多个设备。 对于想要将 [USB-C 麦克风](#usb-c-external-microphone-support)与其他已连接设备一起使用的用户，USB-C 集线器可能满足客户的需求。 Microsoft 尚未测试这些设备，我们也不能推荐任何特定品牌。

USB-C 集线器和已连接设备的要求：

- 连接的设备不得要求安装驱动程序。
- 所有已连接设备的总功耗必须低于 4.5 瓦。

## <a name="connect-to-miracast"></a>连接到 Miracast

若要使用 Miracast，请按照下列步骤进行操作：

1. 执行下列操作之一：  

   - 打开“开始”菜单，然后选择“显示”图标。
   - 盯着“开始”菜单说“连接”。  

1. 在所显示设备的列表中，选择一个可用的设备。

1. 完成配对，开始进行投影。
