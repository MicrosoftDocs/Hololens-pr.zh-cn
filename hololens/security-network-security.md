---
title: 网络安全
description: 网络安全性
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全性、hololens、网络、网络安全
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 416a4f7b9e3cf2e52b79fb29f50424a9c573a18a
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640485"
---
# <a name="network-security"></a>网络安全

## <a name="network-protocols"></a>网络协议

过时的 NetBIOS（网络基本输入/输出系统）在过去的 LAN 方案中广泛使用，通常用于为计算机和共享文件夹中提供名称解析。 但随着时间推移，已证明 NetBIOS 容易受到多种攻击，其相关性的降低支持了其他更安全的协议取而代之。 为了消除此漏洞问题，HoloLens 2 已删除操作系统中与 NetBIOS 相关的代码。

TLS（传输层安全性）协议正不断发展。 为跟上在此领域已经发现的各种安全漏洞，计算机产业已升级到更新和更有效的版本。 由于所有服务器部署都需时间来采用新 TLS 协议版本，因此可实施一种回退机制，允许不同默认协议版本上的客户端和服务器在过渡期仍能通信。

## <a name="secure-connectivity"></a>安全的连接 

Windows Defender 防火墙提供了保护设备连接的关键功能。 使用 HoloLens 2，防火墙将始终处于启用状态，无法通过编程或 UI 禁用它。

可通过 [UWP VPN 插件平台](/uwp/api/Windows.Networking.Vpn?view=winrt-19041)确保移动客户端的远程访问和连接隐私。 第三方 VPN 提供商可使用 WinRT API 创建自己的插件，WinRT API 将在 AppContainer 沙盒中运行，从而消除通常与写入系统级驱动程序关联的复杂性和问题。
