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
# 无线和 Wi-Fi

HoloLens 2 无线 LAN 连接支持一系列令人印象深刻的最新 Wi-Fi 安全标准，例如：
  * WPA2（Wi-Fi 安全访问 2）  
  * TEAP（隧道可扩展身份验证协议）  
  * OWE（机会性无线加密）

TEAP 是下一代企业网络身份验证，它能够将多个凭据安全地链接到单个事务中。  这使管理员可以强制实施更强安全措施，即在同一身份验证事务期间要求计算机和用户均具有有效身份。

HoloLens 2 具有现代无线和 Wi-Fi 协议，可为客户提供最大支持。 HoloLens 2 对讲机是一款高通 WCN3990 解决方案，可提供优质的对讲机体验。 支持的 Wi-Fi 是 802.11 ac/n。 频率范围不可由用户配置，它取决于使用的国家/地区。 在美国，Wi-Fi 使用 2.4GHz (1-11) 频道和 5GHz（36-64、100-165）频道。 用户和设备都不能为特定频率创建允许/拒绝列表。 蓝牙 SIC 核心 5.0 具有专用于蓝牙的 2.4GHz 天线，该天线不与 Wi-Fi 共享。 HoloLens 2 的软件堆栈支持多个协议和配置文件，包括 HID、HOGP、A2DP 和 GATT。 

IT 管理员可以： 
  * 启用或限制[蓝牙访问](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth)
  * 设置[本地蓝牙设备名称](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-localdevicename)
  * 允许[设备可被发现](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bluetooth#bluetooth-allowdiscoverablemode)
  * 允许/禁止 [Wi-Fi 连接](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 
  * 允许/禁止[连接到在 MDM 服务器安装网络之外的 Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowmanualwificonfiguration)
