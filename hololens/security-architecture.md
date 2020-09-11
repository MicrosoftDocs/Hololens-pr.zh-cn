---
title: HoloLens 安全体系结构
description: 安全体系结构
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全, hololens, hololens 2, hololens2 安全, 安全概述, 安全体系结构, 体系结构, hololens 2 体系结构
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f8434ffe2442f270d6360018bea4b64064168d0c
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009550"
---
# <span data-ttu-id="8c0b4-104">安全概述和体系结构</span><span class="sxs-lookup"><span data-stu-id="8c0b4-104">Security overview and architecture</span></span>

<span data-ttu-id="8c0b4-105">HoloLens 2 安全体系结构是从头开始进行设计的，不会出现遗留的安全问题，同时最大限度地减少了攻击面。</span><span class="sxs-lookup"><span data-stu-id="8c0b4-105">The HoloLens 2 security architecture was designed and engineered from the ground up to be free from legacy security issues, while creating a minimized attack surface.</span></span> <span data-ttu-id="8c0b4-106">这种新颖的创新体系结构可提供安全的存储位置和高级安全元素，并具有能够使操作系统免受潜在威胁和漏洞影响的机制。</span><span class="sxs-lookup"><span data-stu-id="8c0b4-106">This new, innovative architecture offers secure storage locations and advanced security elements, with mechanisms capable of shielding operating systems from potential threats and vulnerabilities.</span></span>

<span data-ttu-id="8c0b4-107">HoloLens 2 将硬件、软件、网络和服务结合在一起，可提供端到端安全性，同时为用户提供最佳体验。</span><span class="sxs-lookup"><span data-stu-id="8c0b4-107">HoloLens 2 combines hardware, software, networking, and services to deliver end-to-end security, while providing the user with an optimal experience.</span></span> <span data-ttu-id="8c0b4-108">借助 HoloLens 2，大多数安全功能现在都会自动打开，从而最大限度地减少正确设置和配置操作系统所需的工作量。</span><span class="sxs-lookup"><span data-stu-id="8c0b4-108">With HoloLens 2, a large majority of security features are now turned on automatically, minimizing the effort required to correctly set up and configure the operating system.</span></span>

<span data-ttu-id="8c0b4-109">Windows HoloLens 2 和操作系统体系结构提供了以下创新的安全功能：</span><span class="sxs-lookup"><span data-stu-id="8c0b4-109">Windows HoloLens 2 and operating system architecture offers these innovative security features:</span></span>

  * <span data-ttu-id="8c0b4-110">**状态分离和隔离**：这种新的体系结构可保护 HoloLens 2 操作系统中的关键部分，防止其发生更改，例如核心操作系统启动进入受信任状态所需的部分。</span><span class="sxs-lookup"><span data-stu-id="8c0b4-110">**State separation and isolation**:  This new architecture protects critical portions of the HoloLens 2 operating system from change - such as those required for the core operating system to boot into a trusted state.</span></span> <span data-ttu-id="8c0b4-111">隔离技术用于将不受信任的应用限制在沙盒区域中，以确保它们不会影响系统安全性。</span><span class="sxs-lookup"><span data-stu-id="8c0b4-111">Isolation technology is used to confine untrusted apps in a sandbox area, ensuring that they cannot impact the system security.</span></span> <span data-ttu-id="8c0b4-112">整个操作系统分为安全部分，每个部分都由不同的安全技术组合屏蔽。</span><span class="sxs-lookup"><span data-stu-id="8c0b4-112">The entire operating system is segmented into secure sections, with each section shielded by a combination of different security technologies.</span></span>
  
  * <span data-ttu-id="8c0b4-113">**数据保护**：如果用户的设备丢失或被盗，HoloLens 2 可以依靠 BitLocker 数据加密来防止未经授权的应用程序读取敏感信息。</span><span class="sxs-lookup"><span data-stu-id="8c0b4-113">**Data Protection**: If a user’s device is lost or stolen, HoloLens 2 prevents unauthorized applications from reading sensitive information by relying on BitLocker encryption of data.</span></span> 
  
  * <span data-ttu-id="8c0b4-114">**无密码的操作系统**：基于密码的旧操作系统可能会无意中使用户暴露于网络钓鱼威胁中，并且往往会导致帐户遭到破坏。</span><span class="sxs-lookup"><span data-stu-id="8c0b4-114">**Password-less operating system**:  Older, password-based operating systems could inadvertently expose users to phishing threats and were often responsible for compromised accounts.</span></span> <span data-ttu-id="8c0b4-115">Windows Holographic for Business 无需使用密码即可登录 MSA 和 AAD，并通过 Windows Hello™ 和 FIDO2 登录增强了用户身份保护。</span><span class="sxs-lookup"><span data-stu-id="8c0b4-115">Windows Holographic for Business eliminates the use of passwords for MSA and AAD sign-in and strengthens user-identity protection with Windows Hello™ and FIDO2 sign-in.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="8c0b4-116">若要获得 FIDO2 支持，设备必须位于版本 19041 或更高版本上。</span><span class="sxs-lookup"><span data-stu-id="8c0b4-116">To have FIDO2 support, the device must be on Build 19041 or higher.</span></span> 

  * <span data-ttu-id="8c0b4-117">**网络安全**：HoloLens 2 通过改进的协议和默认设置为用户提供了更高的网络安全性。</span><span class="sxs-lookup"><span data-stu-id="8c0b4-117">**Network security**: HoloLens 2 offers the user increased network security via improved protocols and default settings.</span></span>
