---
title: 无线和 Wi-Fi
description: 无线和 Wi-Fi
author: jbennett
ms.date: 6/30/2020
ms.topic: article
keywords: 安全, hololens, 无线, Wi-Fi
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2771e6e5e428b2705fc2f495823480a9514fa71a
ms.sourcegitcommit: 896bdfccf4612a692a25a6bfaecfa2146860407e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2020
ms.locfileid: "10865655"
---
# <span data-ttu-id="5ec26-104">无线和 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="5ec26-104">Wireless and Wi-Fi</span></span>

<span data-ttu-id="5ec26-105">HoloLens 2 无线 LAN 连接支持一系列令人印象深刻的最新 Wi-Fi 安全标准，例如：</span><span class="sxs-lookup"><span data-stu-id="5ec26-105">HoloLens 2 Wireless LAN connectivity supports an impressive range of the latest Wi-Fi security standards, such as:</span></span>
  * <span data-ttu-id="5ec26-106">WPA2（Wi-Fi 安全访问 2）</span><span class="sxs-lookup"><span data-stu-id="5ec26-106">WPA2 (Wi-Fi Protected Access 2)</span></span>  
  * <span data-ttu-id="5ec26-107">TEAP（隧道可扩展身份验证协议）</span><span class="sxs-lookup"><span data-stu-id="5ec26-107">TEAP (Tunnel Extensible Authentication Protocol)</span></span>  
  * <span data-ttu-id="5ec26-108">OWE（机会性无线加密）</span><span class="sxs-lookup"><span data-stu-id="5ec26-108">OWE (Opportunistic Wireless Encryption)</span></span>

<span data-ttu-id="5ec26-109">TEAP 是下一代企业网络身份验证，它能够将多个凭据安全地链接到单个事务中。</span><span class="sxs-lookup"><span data-stu-id="5ec26-109">TEAP, the next generation of enterprise network authentication, provides the ability to securely chain multiple credentials into a single transaction.</span></span>  <span data-ttu-id="5ec26-110">这使管理员可以强制实施更强安全措施，即在同一身份验证事务期间要求计算机和用户均具有有效身份。</span><span class="sxs-lookup"><span data-stu-id="5ec26-110">This allows administrators to enforce a stronger security stance – one that requires valid identities for both machine and user during the same authentication transaction.</span></span>

<span data-ttu-id="5ec26-111">HoloLens 2 具有现代无线和 Wi-Fi 协议，可为客户提供最大支持。</span><span class="sxs-lookup"><span data-stu-id="5ec26-111">HoloLens 2 has modern wireless and Wi-Fi protocols that enable customers with maximum support.</span></span> <span data-ttu-id="5ec26-112">HoloLens 2 对讲机是一款高通 WCN3990 解决方案，可提供优质的对讲机体验。</span><span class="sxs-lookup"><span data-stu-id="5ec26-112">The HoloLens 2 radio is a Qualcomm WCN3990 solution delivering a premium radio experience.</span></span> <span data-ttu-id="5ec26-113">支持的 Wi-Fi 是 802.11 ac/n。</span><span class="sxs-lookup"><span data-stu-id="5ec26-113">The Wi-Fi supported is 802.11 ac/n.</span></span> <span data-ttu-id="5ec26-114">频率范围不可由用户配置，它取决于使用的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="5ec26-114">The frequency range is not user configurable and depends on the country of use.</span></span> <span data-ttu-id="5ec26-115">在美国，Wi-Fi 使用 2.4GHz (1-11) 频道和 5GHz（36-64、100-165）频道。</span><span class="sxs-lookup"><span data-stu-id="5ec26-115">In the United States, Wi-Fi uses both 2.4GHz (1-11) channels and 5GHz (36-64, 100-165) channels.</span></span> <span data-ttu-id="5ec26-116">用户和设备都不能为特定频率创建允许/拒绝列表。</span><span class="sxs-lookup"><span data-stu-id="5ec26-116">Neither user nor device can make allow/deny lists for specific frequencies.</span></span> <span data-ttu-id="5ec26-117">蓝牙 SIC 核心 5.0 具有专用于蓝牙的 2.4GHz 天线，该天线不与 Wi-Fi 共享。</span><span class="sxs-lookup"><span data-stu-id="5ec26-117">Bluetooth SIC Core 5.0 has a dedicated 2.4GHz antenna for Bluetooth which is not shared with Wi-Fi.</span></span> <span data-ttu-id="5ec26-118">HoloLens 2 的软件堆栈支持多个协议和配置文件，包括 HID、HOGP、A2DP 和 GATT。</span><span class="sxs-lookup"><span data-stu-id="5ec26-118">HoloLens 2’s software stack supports several protocols and profiles including HID, HOGP, A2DP, and GATT.</span></span> 

<span data-ttu-id="5ec26-119">IT 管理员可以：</span><span class="sxs-lookup"><span data-stu-id="5ec26-119">IT admins can:</span></span> 
  * <span data-ttu-id="5ec26-120">启用或限制[蓝牙访问](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)</span><span class="sxs-lookup"><span data-stu-id="5ec26-120">Enable or restrict  [Bluetooth access](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)</span></span>
  * <span data-ttu-id="5ec26-121">设置[本地蓝牙设备名称](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)</span><span class="sxs-lookup"><span data-stu-id="5ec26-121">Set [local Bluetooth device names](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)</span></span>
  * <span data-ttu-id="5ec26-122">允许[设备可被发现](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)</span><span class="sxs-lookup"><span data-stu-id="5ec26-122">Allow [devices to be discoverable](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)</span></span>
  * <span data-ttu-id="5ec26-123">允许/禁止 [Wi-Fi 连接](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)</span><span class="sxs-lookup"><span data-stu-id="5ec26-123">Allow/disallow [Wi-Fi connections](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi)</span></span> 
  * <span data-ttu-id="5ec26-124">允许/禁止[连接到在 MDM 服务器安装网络之外的 Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)</span><span class="sxs-lookup"><span data-stu-id="5ec26-124">Allow or disallow [connecting to Wi-Fi outside of MDM server-installed networks](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)</span></span>
