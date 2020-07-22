---
title: 网络安全性
description: 网络安全性
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、hololens、网络、网络安全
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 147401331cb6da732a6fe37e57964d61a10dce99
ms.sourcegitcommit: 47bc3b696936dd7011b3f9dd683deb872ed25b90
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "10883136"
---
# <span data-ttu-id="94094-104">网络安全性</span><span class="sxs-lookup"><span data-stu-id="94094-104">Network security</span></span>

## <span data-ttu-id="94094-105">网络协议</span><span class="sxs-lookup"><span data-stu-id="94094-105">Network protocols</span></span>

<span data-ttu-id="94094-106">过时的 NetBIOS（网络基本输入/输出系统）在过去的 LAN 方案中广泛使用，通常用于为计算机和共享文件夹中提供名称解析。</span><span class="sxs-lookup"><span data-stu-id="94094-106">The outdated NetBIOS (Network Basic Input/Output System) was widely used in the past in LAN scenarios – often for providing name resolution to a computer and shared folders.</span></span> <span data-ttu-id="94094-107">但随着时间推移，已证明 NetBIOS 容易受到多种攻击，其相关性的降低支持了其他更安全的协议取而代之。</span><span class="sxs-lookup"><span data-stu-id="94094-107">But over time, NetBIOS proved to be susceptible to multiple attacks, and its relevance decreased in favor of other more secure protocols.</span></span> <span data-ttu-id="94094-108">为了消除此漏洞问题，HoloLens 2 已删除操作系统中与 NetBIOS 相关的代码。</span><span class="sxs-lookup"><span data-stu-id="94094-108">To remove this vulnerability issue, HoloLens 2 has eliminated the NetBIOS-related code from the operating system.</span></span>

<span data-ttu-id="94094-109">TLS（传输层安全性）协议正不断发展。</span><span class="sxs-lookup"><span data-stu-id="94094-109">TLS (Transport Layer Security) protocols are constantly evolving.</span></span> <span data-ttu-id="94094-110">为跟上在此领域已经发现的各种安全漏洞，计算机产业已升级到更新和更有效的版本。</span><span class="sxs-lookup"><span data-stu-id="94094-110">To keep up with the various security exploits that have been uncovered in this area, the computing industry has graduated to newer and more effective versions.</span></span> <span data-ttu-id="94094-111">由于所有服务器部署都需时间来采用新 TLS 协议版本，因此可实施一种回退机制，允许不同默认协议版本上的客户端和服务器在过渡期仍能通信。</span><span class="sxs-lookup"><span data-stu-id="94094-111">Due to the time required for all server deployments to adopt the new TLS protocol versions, a fallback mechanism can be implemented that permits the client and servers on different default protocol versions to still be able to communicate during the transition period.</span></span>

## <span data-ttu-id="94094-112">安全连接性</span><span class="sxs-lookup"><span data-stu-id="94094-112">Secure connectivity</span></span> 

<span data-ttu-id="94094-113">Windows Defender 防火墙提供了保护设备连接的关键功能。</span><span class="sxs-lookup"><span data-stu-id="94094-113">The Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="94094-114">使用 HoloLens 2，防火墙将始终处于启用状态，无法通过编程或 UI 禁用它。</span><span class="sxs-lookup"><span data-stu-id="94094-114">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span>

<span data-ttu-id="94094-115">移动客户端的远程访问和连接隐私可通过 [UWP VPN 插件平台](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041)。</span><span class="sxs-lookup"><span data-stu-id="94094-115">Remote access and connection privacy for mobile clients can be assured through the [UWP VPN plug-in platform](https://docs.microsoft.com/uwp/api/Windows.Networking.Vpn?view=winrt-19041).</span></span> <span data-ttu-id="94094-116">第三方 VPN 提供商可使用 WinRT APIs 创建自己的插件，WinRT APIs 将在 AppContainer 沙盒中运行，从而消除通常与写入系统级驱动程序关联的复杂性和问题。</span><span class="sxs-lookup"><span data-stu-id="94094-116">Third-party VPN providers can create their own plug-ins using WinRT APIs which will run within the AppContainer sandbox, eliminating the complexity and issues often associated with writing system-level drivers.</span></span>
