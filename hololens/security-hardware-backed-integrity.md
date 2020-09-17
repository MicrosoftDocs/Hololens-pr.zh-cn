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
ms.openlocfilehash: befd2d892403b7b6c7050f48ba9beffb45b241fe
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016676"
---
# 硬件支持的完整性和运行时证明

硬件支持的完整性和运行时证明可抵御在操作系统启动之前、运行时期间、设备使用硬件时发出的威胁以及远程证明服务，以确保在启动时和整个运行时期间保持完整性。

## UEFI 安全启动

HoloLens 2 始终强制实施统一可扩展固件接口 (UEFI) 安全启动，而 UEFI 仅启动 Windows Holographic for Business。
安全启动可确保验证整个启动链的完整性，并且 Windows 始终在启动时应用正确的安全策略。 若要了解有关安全启动的详细信息，请访问此处。

## TPM

受信任的平台模块 (TPM) 是终结点设备上的专用芯片。 HoloLens 2 使用 TPM 2.0，它提供硬件强制的密钥隔离。

## 持久性访问威胁防护

大多数网络攻击的目标是维持对设备的持久访问。 对于网络犯罪，保持这种持久性会使受到攻击的 Windows 设备能够加入僵尸网络，向设备或其他恶意用户出售访问权限，或者支持重复的数据盗窃。 在有针对性的攻击世界中，持久性对于成功的网络攻击至关重要 - 无论是在设备上还是（通常）在整个网络上。  

事实上，由于目标攻击的战略需要，即保持对目标设备或网络的访问，它们被视为“高级持久威胁”。 因此，Windows Holographic for Business 认为抵御持久性绝对至关重要，并使用反持久性技术做出了坚定的客户安全承诺。

### 安全启动 

HoloLens 2 在所有核心操作系统状态上强制实施统一可扩展固件接口 (UEFI) 安全启动。 UEFI 仅启动 Microsoft 受信任的平台，该平台可确保验证整个启动链的完整性，并且 Windows 始终在启动时应用正确的安全策略。 HoloLens 2 不会关闭安全启动，也不允许第三方启动加载程序。

> [!Tip]
> 了解有关[安全启动](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)的详细信息。

### Windows 反持久性保证

HoloLens 2 反持久性可确保其用户即使在系统运行时受到威胁的罕见情况下（如远程利用），只需关闭设备电源即可从系统中删除所有恶意代码，从而减轻此类事件的发生。 为了进一步增强其反持久性，HoloLens 2 增加了强大的完整性保护，并设置了只读保护。

除非用户对设备执行一键重置 (PBR) 来擦除所有可变分区，否则仍有可能以数据形式永久保留操作系统数据。 尽管对不可变分区的持久性要困难得多，但用户需要对 Hololens 2 执行 PBR 才能从可变部分中消除任何可能的威胁持久性。

## 代码完整性保护 

代码完整性 (CI) 是现代操作系统的一个关键安全属性。 强制实施 CI 可以做出可靠的安全决策，因为它可以确保代码的来源对用户和操作系统都是透明的。 完整的代码完整性需要扩展到二进制映像签名之外，并包括运行时强制实施，例如控制流完整性和动态代码限制。 CI 对于防止多种类型的攻击至关重要，包括社交工程恶意软件（如勒索软件）、远程执行代码攻击和各种其他攻击类别。
