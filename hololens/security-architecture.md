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
ms.openlocfilehash: d8e68f73d05db397a7ee088382e82dfa762177b0
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2021
ms.locfileid: "124427569"
---
# <a name="security-overview-and-architecture"></a>安全概述和体系结构

HoloLens 2 安全体系结构是从头开始进行设计的，不会出现遗留的安全问题，同时最大限度地减少了攻击面。 这种新颖的创新体系结构可提供安全的存储位置和高级安全元素，并具有能够使操作系统免受潜在威胁和漏洞影响的机制。

HoloLens 2 将硬件、软件、网络和服务结合在一起，可提供端到端安全性，同时为用户提供最佳体验。 借助 HoloLens 2，大多数安全功能现在都会自动打开，从而最大限度地减少正确设置和配置操作系统所需的工作量。

Windows HoloLens 2 和操作系统体系结构提供了以下创新的安全功能：

  * 状态分离和隔离：这一新的基础结构可保护 Hololens 2 操作系统中的关键部分，防止其发生更改，例如核心操作系统启动进入受信任状态所需的部分。 隔离技术用于将不受信任的应用限制在沙盒区域中，以确保它们不会影响系统安全性。 整个操作系统分为安全部分，每个部分都由不同的安全技术组合屏蔽。
  
  * 数据保护：如果用户的设备丢失或被盗，HoloLens 2 可以依靠 BitLocker 数据加密来防止未经授权的应用程序读取敏感信息。 
  
  * 无密码操作系统：基于密码的旧操作系统可能会无意中使用户暴露于网络钓鱼威胁中，并且往往会导致帐户遭到破坏。 Windows Holographic for Business 无需使用密码即可登录 MSA 和 Azure AD，并通过 Windows Hello™ 和 FIDO2 登录增强了用户身份保护。 
  
    > [!NOTE]
    > 若要获得 FIDO2 支持，设备必须位于版本 19041 或更高版本上。 

  * 网络安全：HoloLens 2 通过改进的协议和默认设置为用户提供了更高的网络安全性。
