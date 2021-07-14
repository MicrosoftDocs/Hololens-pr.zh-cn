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
ms.openlocfilehash: 8318d011d6a593c1036b6bcf6f7973870b0dc294
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397488"
---
# <a name="connect-to-cellular-and-5g"></a><span data-ttu-id="5e5b1-103">连接到手机网络和 5G</span><span class="sxs-lookup"><span data-stu-id="5e5b1-103">Connect to Cellular and 5G</span></span>

<span data-ttu-id="5e5b1-104">HoloLens 2 支持两种方法连接到手机网络和 5G 网络：</span><span class="sxs-lookup"><span data-stu-id="5e5b1-104">HoloLens 2 supports two methods for connecting to cellular and 5G networks:</span></span>

- <span data-ttu-id="5e5b1-105">由手机设备提供的临时 WiFi 网络，通常称为“热点”</span><span class="sxs-lookup"><span data-stu-id="5e5b1-105">An ad hoc WiFi network provided by the cellular device, commonly referred to as a "Hotspot"</span></span>
- <span data-ttu-id="5e5b1-106">对 USB-C 网络共享设备的有限支持</span><span class="sxs-lookup"><span data-stu-id="5e5b1-106">Limited support for USB-C tethered devices</span></span>

## <a name="hotspot-wifi"></a><span data-ttu-id="5e5b1-107">热点 (WiFi)</span><span class="sxs-lookup"><span data-stu-id="5e5b1-107">Hotspot (WiFi)</span></span>

<span data-ttu-id="5e5b1-108">通过热点可以满足大多数手机网络连接需求。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-108">Most cellular connectivity needs can be met with a hotspot.</span></span> <span data-ttu-id="5e5b1-109">HoloLens 2 WiFi 支持 802.11ac，可以提供大多数常见使用场景所需的带宽和延迟要求。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-109">HoloLens 2 WiFi supports 802.11ac, which can provide the bandwidth and latency requirements necessary for most common use cases.</span></span> <span data-ttu-id="5e5b1-110">WiFi 也是无线连接，并与绝大多数手机设备兼容。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-110">WiFi is also cable-free and offers compatibility with the largest number of cellular devices.</span></span>

### <a name="connecting-to-a-hotspot"></a><span data-ttu-id="5e5b1-111">正在连接到热点</span><span class="sxs-lookup"><span data-stu-id="5e5b1-111">Connecting to a Hotspot</span></span>

1. <span data-ttu-id="5e5b1-112">请参阅设备的手册，了解如何启用热点模式。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-112">Consult your device's manual on how to enable its hotspot mode.</span></span>
1. <span data-ttu-id="5e5b1-113">启用热点模式，为网络提供名称和已知密码。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-113">Enable hotspot mode, supplying a name for the network as well as a known password.</span></span>
1. <span data-ttu-id="5e5b1-114">在 HoloLens 2 网络设置中，找到在步骤 2 中创建的 WiFi 网络并加入。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-114">In HoloLens 2 Network settings, locate the WiFi network created in step 2 and join it.</span></span>

## <a name="usb-c-tethering"></a><span data-ttu-id="5e5b1-115">USB-C 网络共享</span><span class="sxs-lookup"><span data-stu-id="5e5b1-115">USB-C Tethering</span></span>

<span data-ttu-id="5e5b1-116">USB-C 网络共享可以为需要它的高级工作负载提供更低的延迟。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-116">USB-C tethering can provide lower latency for advanced workloads that need it.</span></span> <span data-ttu-id="5e5b1-117">例如，[Azure 远程渲染](https://azure.microsoft.com/services/remote-rendering)可以从网络共享中获益。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-117">[Azure Remote Rendering](https://azure.microsoft.com/services/remote-rendering), for example, can benefit from tethering.</span></span> <span data-ttu-id="5e5b1-118">请注意，网络共享需要在手机设备和 HoloLens 之间使用电缆连接，并且支持这一功能的设备数量有限。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-118">Note that tethering requires a cable between the cellular device and HoloLens, and tethering is supported by a limited number of devices.</span></span>

### <a name="usb-c-compatibility"></a><span data-ttu-id="5e5b1-119">USB-C 兼容性</span><span class="sxs-lookup"><span data-stu-id="5e5b1-119">USB-C compatibility</span></span>

<span data-ttu-id="5e5b1-120">将自己显示为以太网适配器的有限数量的设备可以与 Windows Holographic 版本 2004 及更高版本一起使用。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-120">A limited number of devices that present themselves as an ethernet adaptor can be used with Windows Holographic version 2004 and later.</span></span>

<span data-ttu-id="5e5b1-121">未将自己显示为以太网适配器的设备必须支持通用的 Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-121">Devices that do not present themselves as an ethernet adapter must support the generic Microsoft [RNDIS](https://docs.microsoft.com/windows-hardware/drivers/network/overview-of-remote-ndis--rndis-) driver.</span></span> <span data-ttu-id="5e5b1-122">但是，仅有有限数量的设备与 HoloLens 2 兼容。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-122">But, only a limited number of those devices are compatible with HoloLens 2.</span></span> <span data-ttu-id="5e5b1-123">有关设备是否支持通用 Microsoft RNDIS 驱动程序的详细信息，请咨询设备制造商。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-123">Please consult your device's manufacturer for details on whether it supports the generic Microsoft RNDIS driver.</span></span>

<span data-ttu-id="5e5b1-124">不支持非 RNDIS 兼容或需要安装驱动程序或应用程序的设备。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-124">Devices that are not RNDIS compatible, or require a driver or application to be installed, are not supported.</span></span>

<span data-ttu-id="5e5b1-125">虽然 Microsoft 不维护兼容设备的列表，但[此处](https://aka.ms/HLCommunityCell)的主题设有一个社区讨论。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-125">While Microsoft does not maintain a list of compatible devices, there is a community discussion on the topic [here](https://aka.ms/HLCommunityCell).</span></span>

### <a name="connecting-to-a-tethered-device"></a><span data-ttu-id="5e5b1-126">正在连接到网络共享设备</span><span class="sxs-lookup"><span data-stu-id="5e5b1-126">Connecting to a tethered device</span></span>

1. <span data-ttu-id="5e5b1-127">请参阅设备的手册，了解如何通过 USB 启用数据共享。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-127">Consult your device's manual on how to enable data sharing over USB.</span></span> <span data-ttu-id="5e5b1-128">此设置通常称为“USB 网络共享”、“数据共享”或“USB 调制解调器”。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-128">This setting is often referred to as "USB Tethering", "Data Sharing" or "USB Modem".</span></span>
1. <span data-ttu-id="5e5b1-129">通过 USB 启用数据共享。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-129">Enable data sharing over USB.</span></span>
1. <span data-ttu-id="5e5b1-130">将设备连接到 HoloLens USB-C 端口。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-130">Connect your device to the HoloLens USB-C port.</span></span>
1. <span data-ttu-id="5e5b1-131">在 HoloLens 2 网络设置中，设备将自动显示为以太网连接。</span><span class="sxs-lookup"><span data-stu-id="5e5b1-131">In HoloLens 2 Network settings, the device will automatically appear as an Ethernet connection.</span></span>
