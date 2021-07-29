---
title: 加密和数据保护
description: 了解 HoloLens 2 设备的加密和数据保护，包括 BitLocker 和 Azure 集成。
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性, hololens, 加密, 数据保护, BitLocker 设备, BitLocker, bitlocker, bitlocker 加密, azure 集成,
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e156fc21bfd1541dd8718a7349e7ba82b45576be
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639363"
---
# <a name="encryption-and-data-protection"></a>加密和数据保护

加密和数据保护功能可在设备丢失或被盗时保护数据，并防止未经授权的应用程序访问敏感信息。

## <a name="bitlocker-device-encryption"></a>BitLocker 设备加密

BitLocker 是一种全卷加密功能，用于保护只读 (RO) 介质的完整性和可写介质的隐私。  自创立伊始，它一直是防止脱机攻击期间未经授权访问数据的有效屏障。 默认情况下，HoloLens 2 启用 BitLocker 设备加密 (BDE)，以保护数据免受对设备的任何未经授权的物理访问。 Microsoft 始终在不断发展以满足未来的需求，并继续投资并增强该技术。

BDE 是一种数据保护功能，在设备的状态分隔布局中的所有卷上均采用 AES-XTS-256 加密。 BDE 以状态分隔的布局提供设备级加密。 BitLocker 设备加密在操作系统和固定数据卷上自动启用，即使是 IT 管理员也不能关闭，以便设备始终受到保护。

然后使用 BDE 加密密钥对二进制文件和启动设备所需的数据进行透明的解密。 随着操作系统卷的解锁和系统启动，可使用自动解锁保护器的卷特定版本访问其他卷。 没有其他保护器可用于维护用户隐私，并且只能在同一设备上解锁驱动器。 从第一次引导开始，将立即对所需卷应用和实施只读 (RO) 强制。 HoloLens 2 生命周期中不需要 Bitlocker 恢复密钥。

## <a name="azure-integration"></a>Azure 集成 

HoloLens 2 使客户能够将其设备与 Azure 服务集成。 HoloLens 2 设备与 Azure 之间的通信使用 TLS（传输层安全性）协议来保护其自身与云服务之间传输的数据，从而提供强大的身份验证、消息隐私和完整性。 所有 Azure 服务完全支持 TLS 1.2，而客户仅使用 TLS 1.2 的任何服务只接受 TLS 1.2 流量。 [Azure 加密概述](/azure/security/fundamentals/encryption-overview)中详细介绍了 Azure 针对传输数据的加密标准。 参阅 Azure 文档，详细了解 [Azure 数据安全和加密的最佳做法](/azure/security/fundamentals/data-encryption-best-practices)。 

OneDrive 是与 HoloLens 2 的云集成示例，它具有自动上传功能，在连接到 Internet 时，你的文件和文档可以自动上传到云。 暂停文件自动同步不能通过策略关闭，但可通过 UX 直接配置。 
