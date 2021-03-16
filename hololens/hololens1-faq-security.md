---
title: 常见安全问题解答
description: 随时了解关于 HoloLens 混合现实设备的常见安全问题和答案。
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: pawinfie
ms.author: pawinfie
ms.date: 02/19/2020
keywords: hololens, Windows Mixed Reality, 安全
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
manager: bradke
ms.openlocfilehash: 371c901acbf23feecfe98e72569caeaf63e2198f
ms.sourcegitcommit: 01c0b0a789e156a9d29aaf6f61e36dfd09b8c01a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439028"
---
# <a name="frequently-asked-hololens-1st-gen-security-questions"></a>常见的 HoloLens 第一代安全问题

1. **HoloLens 1 提供何种级别的数据保护？**
    1. 请参阅 [HoloLens（第 1 代）BitLocker 加密](hololens1-encryption.md)
1. **它使用哪种类型的无线？**
    1. 802.11ac 和蓝牙 4.1 LE
1. **采用了哪种类型的体系结构？  例如：指向点、网格或其他内容？**
    1. 可在基础结构模式下使用 Wi-Fi 与其他无线接入点进行通信。
    1. Bluetooth客户的应用程序支持 HoloLens，或与其他其他 HoloLens 设备之间，Bluetooth对等。
1. **什么是 FCC ID？**
    1. C3K1688
1. **该设备的工作频率范围和信道是多少？是否可以配置？**
    1. Wi-Fi：频率范围不可由用户配置，它取决于使用的国家/地区。 在美国，Wi-Fi 使用 2.4 GHz (1-11) 信道和 5 GHz（36-64、100-165）信道。
    1. 蓝牙：蓝牙使用标准 2.4-2.48 GHz 范围。
1. **设备可以允许或阻止特定频率？**
    1. 用户/设备无法控制这一点。
1. **发射和接收的功率等级是多少？ 是否可以调节？ 工作范围是什么？**
    1. 可在[此处](https://fccid.io/C3K1688)找到我们的发射测试标准。 工作范围在很大程度上取决于接入点和环境 - 但大致等同于其他高质量的电话、电脑或平板电脑。
1. **正常工作的工作周期/使用寿命是多长？**
    1. 2-3 小时的活动使用时间以及最多两周的待机时间
    1. 未提供电池使用寿命。
1. **当工具不在范围内时，发射和接收行为是什么？**
    1. HoloLens 的发射/接收遵循标准 Wi-Fi/蓝牙模式。 在其范围的边缘，你可能会注意到输入变得断断续续，直到完全断开连接为止，但是在返回范围内时，它应该会快速重新连接。
1. **每平方英尺的部署密度是多少？**
    1. 这取决于你的网络基础结构。
1. **该设备是否可将基础结构用作客户端？**
    1. 是
1. **所使用的协议是什么？**
    1. HoloLens 未使用任何专用协议
1. **操作系统更新频率 - HL 的操作系统更新频率是多少？  有固定的时间表吗？  Microsoft 是否会根据需要发布安全修补程序等等。**
    1. Microsoft 按照与 Windows 10 完全相同的方式为 HoloLens 提供操作系统更新。 每年通常有两次重大更新，春季更新一次，秋季更新一次。 由于 HoloLens 是 Windows 设备，因此更新理念与任何其他 Windows 设备相同。 Microsoft 会根据需要发布安全修补程序，并遵循与任何其他 Windows 设备相同的理念。
1. **操作系统强化 - 有哪些选项可以强化操作系统？  我们能否删除或关闭不必要的应用或服务？**
    1. HoloLens 类似于智能手机。 它可以与其他现代 Windows 设备相媲美。 可以通过 Microsoft Intune 或其他现代设备管理解决方案（如 MobileIron、Airwatch 或 Soti）来管理 HoloLens。 你可以在这些管理系统中设置策略，以将安全策略应用于设备并强化设备。 如果需要，也可以选择删除任何不必要的应用程序。
1. **如何管理和更新软件应用程序？ 对于 Microsoft Store 中的应用，我们需要使用什么控件来定义要加载的应用和应用更新过程？**
    1. HoloLens 仅通过 Microsoft Store 获取软件应用程序。 只能安装专为使用 HoloLens 而开发的 Appx 应用程序包。 可以在 Microsoft Store 中查看此内容，在显示 HoloLens 设备的应用程序旁边有一些徽标。 用于管理 Store 应用程序的任何控件也适用于 HoloLens。 可使用官方应用商店或企业应用商店的理念。 这些应用可旁加载（在 Windows 设备上加载应用的手动流程），也可通过 MDM 进行管理，以便在需要时自动从应用商店中提取它们。
1. **HoloLens 应用商店中的应用的更新频率是多少？**
    1. 由于我们遵循与 Microsoft Store 相同的理念并从那里提取应用，因此更新周期将由应用程序的开发人员决定。 用于控制应用商店内的更新机制的所有管理选项也适用于 HoloLens。
1. **HoloLens 是否有安全启动功能？**
    1. 是
1. **是否可以从设备禁用或断开外设支持？**
    1. 是
1. **是否可以控制或禁用设备上的端口使用？**
    1. HoloLens 仅包含两个端口 (一个端口用于耳机，另一个端口用于充电或连接到) 。 由于功能和恢复原因，无法禁用端口。
1. **防病毒、终结点检测、IPS、应用控制允许列表 – 运行防病毒、终结点检测、IPS、应用控制允许列表等的任何功能。**
    1. Windows Holographic for Business（商业套件）支持 Windows Defender 智能屏幕。 如果防病毒公司创建应用并将其发布到通用 Windows 平台，则可以在 HoloLens 上进行下载。 目前，没有任何公司为 HoloLens 执行此操作。
    1. 通过使用 Microsoft Enterprise Store，可以将应用列入允许名单，你只能从中选择可供下载的特定应用。 此外，通过 MDM，你可以锁定可在设备上运行甚至显示的特定应用。
1. **如果设备长时间处于脱机状态，是否可以在更新设备之前将其从生产网络隔离？  例如， 设备一直坐在一个收银机中， (六个月) 未收到任何更新、修补程序等。 当它尝试进入网络时，我们能否标记它，并说你必须在另一个网络上更新，然后才能投诉加入该网络。**
    1. 对于这种情况，可通过 MDM 或本地服务器在基础结构级别进行管理。 如果设备不符合指定的更新版本要求，则可以将其标记为不兼容。
1. **Microsoft 是否提供了任何后门或对服务的访问权限，以便 Microsoft 可以连接到设备进行屏幕共享或远程支持？**
    1. 否
1. **在为受信任的通信生成 PKI 证书时，我们希望在设备上生成该证书，以便我们知道它仅位于此设备上并且是唯一的，而且不能导出或用于模拟该设备。 在 HoloLens 上是这样吗？ 如果不是，是否有潜在的缓解措施？**
    1. 该设备本身会生成适用于 SCEP 的 CSR。 Intune 和本地 SCEP 连接器通过添加并验证发送到客户端的质询字符串来帮助保护请求本身。
    1. 由于 HoloLens（第一代和第二代）具有 TPM 模块，这些证书将存储在 TPM 模块中，并且无法提取。 此外，即使可提取，也无法在其他设备上验证质询字符串，从而使证书/密钥在不同的设备上不可用。
