---
title: 硬件支持的完整性和运行时证明
description: 硬件支持的完整性和运行时证明
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.prod: hololens
ms.topic: article
keywords: 安全性, hololens, 硬件支持的完整性, 运行时证明, UEFI, UEFI 安全启动, 安全启动, TPM, 威胁防护, Windows 反持久性保证, 代码完整性, 代码保护,
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0a89fa5e61e560f629444efd2728f6dd41db60d3
ms.sourcegitcommit: ab35169529776f0682eeb8fa448c9d9e8f598513
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2021
ms.locfileid: "11340521"
---
# <span data-ttu-id="5d657-104">硬件支持的完整性和运行时证明</span><span class="sxs-lookup"><span data-stu-id="5d657-104">Hardware-backed integrity and runtime attestation</span></span>

<span data-ttu-id="5d657-105">硬件支持的完整性和运行时证明可抵御在操作系统启动之前、运行时期间、设备使用硬件时发出的威胁以及远程证明服务，以确保在启动时和整个运行时期间保持完整性。</span><span class="sxs-lookup"><span data-stu-id="5d657-105">Hardware-backed integrity and runtime attestation protects against threats that originate prior to the start of an operating system, during runtime, when the device uses hardware, and remote attestation services to ensure integrity is maintained at startup and throughout runtime duration.</span></span>

## <span data-ttu-id="5d657-106">UEFI 安全启动</span><span class="sxs-lookup"><span data-stu-id="5d657-106">UEFI secure boot</span></span>

<span data-ttu-id="5d657-107">HoloLens 2 始终强制实施统一可扩展固件接口 (UEFI) 安全启动，而 UEFI 仅启动 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="5d657-107">HoloLens 2 enforces Unified Extensible Firmware Interface (UEFI) Secure Boot always, and UEFI only boots Windows Holographic for Business.</span></span>
<span data-ttu-id="5d657-108">安全启动可确保验证整个启动链的完整性，并且 Windows 始终在启动时应用正确的安全策略。</span><span class="sxs-lookup"><span data-stu-id="5d657-108">Secure Boot ensures that the entire boot chain is verified for integrity, and that Windows always boots with the correct security policies applied to it.</span></span> <span data-ttu-id="5d657-109">了解有关[安全启动](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5d657-109">Learn more about [Secure Boot](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).</span></span>

## <span data-ttu-id="5d657-110">TPM</span><span class="sxs-lookup"><span data-stu-id="5d657-110">TPM</span></span>

<span data-ttu-id="5d657-111">受信任的平台模块 (TPM) 是终结点设备上的专用芯片。</span><span class="sxs-lookup"><span data-stu-id="5d657-111">The Trusted Platform Module (TPM) is a specialized chip on an endpoint device.</span></span> <span data-ttu-id="5d657-112">HoloLens 2 使用 TPM 2.0，它提供硬件强制的密钥隔离。</span><span class="sxs-lookup"><span data-stu-id="5d657-112">HoloLens 2 uses a TPM 2.0, which provides hardware-enforced key isolation.</span></span> <span data-ttu-id="5d657-113">了解有关《[TPM 基础知识](https://docs.microsoft.com/windows/security/information-protection/tpm/tpm-fundamentals)》的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5d657-113">Learn more about [TPM fundamentals](https://docs.microsoft.com/windows/security/information-protection/tpm/tpm-fundamentals).</span></span>

## <span data-ttu-id="5d657-114">持久性访问威胁防护</span><span class="sxs-lookup"><span data-stu-id="5d657-114">Persistence Access Threat Protection</span></span>

<span data-ttu-id="5d657-115">大多数网络攻击的目标是维持对设备的持久访问。</span><span class="sxs-lookup"><span data-stu-id="5d657-115">The goal of most cyberattacks is to maintain persistent access to a device.</span></span> <span data-ttu-id="5d657-116">对于网络犯罪，保持这种持久性会使受到攻击的 Windows 设备能够加入僵尸网络，向设备或其他恶意用户出售访问权限，或者支持重复的数据盗窃。</span><span class="sxs-lookup"><span data-stu-id="5d657-116">For cybercrime, maintaining this persistence enables a compromised Windows device to join a botnet, sell access to the device or other nefarious users, or to enable repeated data theft.</span></span> <span data-ttu-id="5d657-117">在有针对性的攻击世界中，持久性对于成功的网络攻击至关重要 - 无论是在设备上还是（通常）在整个网络上。</span><span class="sxs-lookup"><span data-stu-id="5d657-117">In the world of targeted attacks, persistence is essential to a successful cyberattack – whether on a device or (more commonly), an entire network.</span></span>  

<span data-ttu-id="5d657-118">事实上，由于目标攻击的战略需要，即保持对目标设备或网络的访问，它们被视为“高级持久威胁”。</span><span class="sxs-lookup"><span data-stu-id="5d657-118">In fact, targeted attacks are considered “advanced persistent threats”, due to their strategic need to maintain access to a target device or network.</span></span> <span data-ttu-id="5d657-119">因此，Windows Holographic for Business 认为抵御持久性绝对至关重要，并使用反持久性技术做出了坚定的客户安全承诺。</span><span class="sxs-lookup"><span data-stu-id="5d657-119">For this reason, Windows Holographic for Business considers defending against persistence absolutely crucial and uses anti-persistence technology to make an ironclad customer security promise.</span></span>

### <span data-ttu-id="5d657-120">安全启动</span><span class="sxs-lookup"><span data-stu-id="5d657-120">Secure boot</span></span>

<span data-ttu-id="5d657-121">HoloLens 2 在所有核心操作系统状态上强制实施统一可扩展固件接口 (UEFI) 安全启动。</span><span class="sxs-lookup"><span data-stu-id="5d657-121">HoloLens 2 enforces Unified Extensible Firmware Interface (UEFI) Secure Boot on all core operating system state.</span></span> <span data-ttu-id="5d657-122">UEFI 仅启动 Microsoft 受信任的平台，该平台可确保验证整个启动链的完整性，并且 Windows 始终在启动时应用正确的安全策略。</span><span class="sxs-lookup"><span data-stu-id="5d657-122">UEFI only boots Microsoft trusted platforms, which ensures that the entire boot chain is verified for integrity, and that Windows always boots with the correct security policies applied to it.</span></span> <span data-ttu-id="5d657-123">HoloLens 2 不会关闭安全启动，也不允许第三方启动加载程序。</span><span class="sxs-lookup"><span data-stu-id="5d657-123">HoloLens 2 does not Secure Boot to be turned off, nor does it allow 3rd party boot loaders.</span></span>

> [!Tip]
> <span data-ttu-id="5d657-124">了解有关[安全启动](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5d657-124">Learn more about [Secure boot](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot).</span></span>

### <span data-ttu-id="5d657-125">Windows 反持久性保证</span><span class="sxs-lookup"><span data-stu-id="5d657-125">Windows Anti-Persistence Assurance</span></span>

<span data-ttu-id="5d657-126">HoloLens 2 反持久性可确保其用户即使在系统运行时受到威胁的罕见情况下（如远程利用），只需关闭设备电源即可从系统中删除所有恶意代码，从而减轻此类事件的发生。</span><span class="sxs-lookup"><span data-stu-id="5d657-126">HoloLens 2 anti-persistence guarantees its users that even in the rare situation that a runtime compromise of the system were to ever occur – such as a remote exploit – such an event would be mitigated with all malicious code removed from the system simply by powering off the device.</span></span> <span data-ttu-id="5d657-127">为了进一步增强其反持久性，HoloLens 2 增加了强大的完整性保护，并设置了只读保护。</span><span class="sxs-lookup"><span data-stu-id="5d657-127">To further strengthen its anti-persistence, HoloLens 2 has added powerful integrity protection, and put read-only protections in place.</span></span>

<span data-ttu-id="5d657-128">除非用户对设备执行一键重置 (PBR) 来擦除所有可变分区，否则仍有可能以数据形式永久保留操作系统数据。</span><span class="sxs-lookup"><span data-stu-id="5d657-128">Persistence to operating system data in form of data is still possible, unless the user performs Push-button reset (PBR) of the device that wipes all mutable partitions.</span></span> <span data-ttu-id="5d657-129">尽管对不可变分区的持久性要困难得多，但用户需要对 HoloLens 2 执行 PBR 才能从可变部分中消除任何可能的威胁持久性。</span><span class="sxs-lookup"><span data-stu-id="5d657-129">While persistence to immutable partitions is made much harder, the user needs to PBR the HoloLens 2 to remove any possible threat-persistence from mutable parts.</span></span>

## <span data-ttu-id="5d657-130">代码完整性保护</span><span class="sxs-lookup"><span data-stu-id="5d657-130">Code integrity protection</span></span>

<span data-ttu-id="5d657-131">代码完整性 (CI) 是现代操作系统的一个关键安全属性。</span><span class="sxs-lookup"><span data-stu-id="5d657-131">Code integrity (CI) is a key security property of a modern operating system.</span></span> <span data-ttu-id="5d657-132">强制实施 CI 可以做出可靠的安全决策，因为它可以确保代码的来源对用户和操作系统都是透明的。</span><span class="sxs-lookup"><span data-stu-id="5d657-132">Enforcing CI enables sound security decisions, because it guarantees the provenance of code is transparent to both the user and operating system.</span></span> <span data-ttu-id="5d657-133">完整的代码完整性需要扩展到二进制映像签名之外，并包括运行时强制实施，例如控制流完整性和动态代码限制。</span><span class="sxs-lookup"><span data-stu-id="5d657-133">Complete code integrity needs to extend past binary image signing and include runtime enforcement, such as control flow integrity and dynamic code restrictions.</span></span> <span data-ttu-id="5d657-134">CI 对于防止多种类型的攻击至关重要，包括社交工程恶意软件（如勒索软件）、远程执行代码攻击和各种其他攻击类别。</span><span class="sxs-lookup"><span data-stu-id="5d657-134">CI is critical to preventing multiple classes of attacks including socially engineered malware, such as ransomware, remote code execution exploits, and various other attack classes.</span></span>
