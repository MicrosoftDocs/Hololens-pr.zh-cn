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
ms.openlocfilehash: e005f04088127a0e38a4dd978cd63e5d4e5c0ab9
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284103"
---
# <span data-ttu-id="ff6d4-104">加密和数据保护</span><span class="sxs-lookup"><span data-stu-id="ff6d4-104">Encryption and data protection</span></span>

<span data-ttu-id="ff6d4-105">加密和数据保护功能可在设备丢失或被盗时保护数据，并防止未经授权的应用程序访问敏感信息。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-105">Encryption and Data Protection protects data when the device is lost or stolen and prevents unauthorized applications from accessing sensitive information.</span></span>

## <span data-ttu-id="ff6d4-106">BitLocker 设备加密</span><span class="sxs-lookup"><span data-stu-id="ff6d4-106">BitLocker device encryption</span></span>

<span data-ttu-id="ff6d4-107">BitLocker 是一种全卷加密功能，用于保护只读 (RO) 介质的完整性和可写介质的隐私。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-107">BitLocker is a full-volume encryption feature for integrity protection of Read Only (RO) media and privacy protection of writable media.</span></span>  <span data-ttu-id="ff6d4-108">自创立伊始，它一直是防止脱机攻击期间未经授权访问数据的有效屏障。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-108">Since its inception, it has been an effective shield against unauthorized access to the data during offline attacks.</span></span> <span data-ttu-id="ff6d4-109">默认情况下，HoloLens 2 启用 BitLocker 设备加密 (BDE)，以保护数据免受对设备的任何未经授权的物理访问。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-109">HoloLens 2 enables Bitlocker Device Encryption (BDE) by default to protect data from any unauthorized physical access to the device.</span></span> <span data-ttu-id="ff6d4-110">Microsoft 始终在不断发展以满足未来的需求，并继续投资并增强该技术。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-110">Always evolving to meet the needs of the future, Microsoft continues to invest and enhance this technology.</span></span>

<span data-ttu-id="ff6d4-111">BDE 是一种数据保护功能，在设备的状态分隔布局中的所有卷上均采用 AES-XTS-256 加密。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-111">BDE is a data protection feature that employs AES-XTS-256 encryption on all volumes in the state-separated layout of the device.</span></span> <span data-ttu-id="ff6d4-112">BDE 以状态分隔的布局提供设备级加密。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-112">BDE provides device level encryption in a state-separated layout.</span></span> <span data-ttu-id="ff6d4-113">BitLocker 设备加密在操作系统和固定数据卷上自动启用，即使是 IT 管理员也不能关闭，以便设备始终受到保护。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-113">BitLocker Device Encryption is enabled automatically on operating system and fixed data volumes and cannot be turned off, even by IT administrators, so that the device is always protected.</span></span>

<span data-ttu-id="ff6d4-114">然后使用 BDE 加密密钥对二进制文件和启动设备所需的数据进行透明的解密。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-114">BDE encryption keys are then used to transparently decrypt binaries and the data required to boot the device.</span></span> <span data-ttu-id="ff6d4-115">随着操作系统卷的解锁和系统启动，可使用自动解锁保护器的卷特定版本访问其他卷。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-115">As the operating system volume is unlocked and a system is booting up, other volumes become accessible using a volume-specific version of the auto-unlock protector.</span></span> <span data-ttu-id="ff6d4-116">没有其他保护器可用于维护用户隐私，并且只能在同一设备上解锁驱动器。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-116">No other protectors are available to maintain user privacy and the drive can only be unlocked on the same device.</span></span> <span data-ttu-id="ff6d4-117">从第一次引导开始，将立即对所需卷应用和实施只读 (RO) 强制。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-117">Read Only (RO) enforcement on required volumes is applied and enforced immediately, starting from the first boot.</span></span>

## <span data-ttu-id="ff6d4-118">Azure 集成</span><span class="sxs-lookup"><span data-stu-id="ff6d4-118">Azure integration</span></span> 

<span data-ttu-id="ff6d4-119">HoloLens 2 使客户能够将其设备与 Azure 服务集成。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-119">HoloLens 2 enables customers to integrate their devices with Azure services.</span></span> <span data-ttu-id="ff6d4-120">HoloLens 2 设备与 Azure 之间的通信使用 TLS（传输层安全性）协议来保护其自身与云服务之间传输的数据，从而提供强大的身份验证、消息隐私和完整性。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-120">Communications between HoloLens 2 devices and Azure use TLS (Transport Layer Security) protocol to protect data traveling between itself and cloud services which delivers strong authentication, message privacy, and integrity.</span></span> <span data-ttu-id="ff6d4-121">所有 Azure 服务完全支持 TLS 1.2，而客户仅使用 TLS 1.2 的任何服务只接受 TLS 1.2 流量。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-121">All Azure services fully support TLS 1.2 and any services where customers are using only TLS 1.2 only accept TLS 1.2 traffic.</span></span> <span data-ttu-id="ff6d4-122">[Azure 加密概述](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview)中详细介绍了 Azure 的传输数据加密标准。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-122">Azure’s encryption standards for data in transit are detailed in [Azure encryption overview](https://docs.microsoft.com/azure/security/fundamentals/encryption-overview).</span></span> <span data-ttu-id="ff6d4-123">请访问 Azure文 档，以了解有关 [Azure 数据安全性和加密的最佳做法](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices)的更多信息。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-123">Visit the Azure documentation to learn more about [best practices for Azure data security and encryption](https://docs.microsoft.com/azure/security/fundamentals/data-encryption-best-practices).</span></span> 

<span data-ttu-id="ff6d4-124">OneDrive 是与 HoloLens 2 的云集成示例，它具有自动上传功能，在连接到 Internet 时，你的文件和文档可以自动上传到云。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-124">OneDrive, an example of cloud integration with HoloLens 2, has an auto upload feature where your files and documents can be automatically uploaded to the cloud when connected to the internet.</span></span> <span data-ttu-id="ff6d4-125">暂停文件自动同步不能通过策略关闭，但可通过 UX 直接配置。</span><span class="sxs-lookup"><span data-stu-id="ff6d4-125">Pausing automatic syncing of files cannot be turned off via policy but is directly configurable via the UX.</span></span> 
