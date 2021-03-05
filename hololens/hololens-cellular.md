---
title: 连接到手机网络和 5G
description: 从 HoloLens 混合现实设备连接到手机网络。
ms.assetid: f1aaadce-8762-41f8-bfeb-3b6067a2ec78
ms.prod: hololens
ms.sitesec: library
author: jbienzms
ms.author: jbienz
ms.topic: article
ms.localizationpriority: high
ms.date: 02/24/2021
manager: evmill
appliesto:
- HoloLens 2
ms.openlocfilehash: 3fd5f6baf05277bcbf2bf4152ba4735ca91e5bd0
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385635"
---
# <a name="connect-to-cellular-and-5g"></a>连接到手机网络和 5G

HoloLens 2 支持两种方法连接到手机网络和 5G 网络：

- 由手机设备提供的临时 WiFi 网络，通常称为“热点”
- 对 USB-C 网络共享设备的有限支持

## <a name="hotspot-wifi"></a>热点 (WiFi)

通过热点可以满足大多数手机网络连接需求。 HoloLens 2 WiFi 支持 802.11ac，可以提供大多数常见使用场景所需的带宽和延迟要求。 WiFi 也是无线连接，并与绝大多数手机设备兼容。

### <a name="connecting-to-a-hotspot"></a>正在连接到热点

1. 请参阅设备的手册，了解如何启用热点模式。
1. 启用热点模式，为网络提供名称和已知密码。
1. 在 HoloLens 2 网络设置中，找到在步骤 2 中创建的 WiFi 网络并加入。

## <a name="usb-c-tethering"></a>USB-C 网络共享

USB-C 网络共享可以为需要它的高级工作负载提供更低的延迟。 例如，[Azure 远程渲染](https://azure.microsoft.com/services/remote-rendering) 就可以从网络共享中获益。 请注意，网络共享需要在手机设备和 HoloLens 之间使用电缆连接，并且支持这一功能的设备数量有限。

### <a name="usb-c-compatibility"></a>USB-C 兼容性

将自己显示为以太网适配器的设备可以与 Windows Holographic 版本 2004 及更高版本一起使用。

未将自己显示为以太网适配器的设备必须支持通用的 Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) 驱动程序。 有关设备是否支持通用 Microsoft RNDIS 驱动程序的详细信息，请咨询设备制造商。

不支持非 RNDIS 兼容或需要安装驱动程序或应用程序的设备。

虽然 Microsoft 不维护兼容设备的列表，但 [此处](https://aka.ms/HLCommunityCell) 的主题设有一个社区。

### <a name="connecting-to-a-tethered-device"></a>正在连接到网络共享设备

1. 请参阅设备的手册，了解如何通过 USB 启用数据共享。 此设置通常称为“USB 网络共享”、“数据共享”或“USB 调制解调器”。
1. 通过 USB 启用数据共享。
1. 将设备连接到 HoloLens USB-C 端口。
1. 在 HoloLens 2 网络设置中，设备将自动显示为以太网连接。
