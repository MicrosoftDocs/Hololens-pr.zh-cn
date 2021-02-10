---
title: HoloLens 2 合规性和 GDPR
description: GDPR 文档
keywords: HoloLens， GDPR， 隐私， PII
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b795513d83c9d23f70b8dd8365e703d1fc43a51
ms.sourcegitcommit: 76a99370ab841c06e533cc2f4a0c78c1fb7eac70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "11324866"
---
# HoloLens 2 隐私声明

GDPR 的核心元素之一是"按设计进行数据保护"。 此概念尤其适用于移动设备，如 HoloLens 2，因为它们可移植性、无限 Internet 连接和开放通信通道。 因此，HoloLens 2 的安全性已经[](https://docs.microsoft.com/hololens/security-architecture)过重新设计，可提供高级、创新的安全和隐私保护，端到端，整合了 Microsoft 的隐私和[GDPR](https://privacy.microsoft.com/)法规。

 >[!NOTE]
> 本文档不适用于 HoloLens (第一代) 。

## 隐私概述

HoloLens 2 是一台自包含的 Windows 计算机，运行 Windows 全息版，在沉浸式混合现实环境中运行应用和解决方案。 它可以用作安全的脱机设备或部署为 [组织中托管](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business) 的设备。 请参阅以下链接，了解 HoloLens 2 和 Microsoft 如何使用和保护你的数据：
1. [Microsoft 隐私声明 - HoloLens](https://privacy.microsoft.com/privacystatement) **** – 展开左侧导航菜单中的"企业"和"开发人员"部分，然后选择 **"企业"和"开发人员"软件和设备**。 转到 **HoloLens** 部分。
2.  [Windows 10 和联机服务](https://privacy.microsoft.com/windows10privacy)
3.  [Windows 10 和隐私合规指南](https://docs.microsoft.com/windows/privacy/windows-10-and-privacy-compliance)
4.  [Intune 中的隐私和个人数据](https://docs.microsoft.com/mem/intune/protect/privacy-personal-data)

## 网络安全性
在 HoloLens 2 [常见](https://docs.microsoft.com/hololens/common-scenarios)部署方案之后，你的数据将受 [Azure](https://docs.microsoft.com/azure/compliance/) 世界一流的合规性以及法律/法规标准集成的保护。 如果你是 Azure AD 和 Dynamics 365 远程协助的新用户，请参考适用于 GDPR 的 [Azure 和 Dynamics 365 责任就绪清单](https://docs.microsoft.com/compliance/regulatory/gdpr-arc-azure-dynamics)。

此外，Windows Defender防火墙提供了关键功能，以确保设备连接安全。 使用 HoloLens 2，防火墙将始终处于启用状态，无法通过编程或 UI 禁用它。 当使用 [Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)将 HoloLens 2 部署为托管设备时，更多合规性功能可用于将 Endpoint 与 [Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection) 集成为移动威胁防护解决方案。 

了解有关 HoloLens 2 [安全和体系结构的更多信息](https://docs.microsoft.com/hololens/security-architecture)。

## 操作系统安全性
默认情况下， (应用) 更新，以便 HoloLens 2 始终具有最新版本的 Windows 全息版和任何已安装的应用。 请参阅以下内容，详细了解如何安全设计操作系统：
1. [状态分离和隔离](https://docs.microsoft.com/hololens/security-state-separation-isolation)
1. [无管理操作系统](https://docs.microsoft.com/hololens/security-adminless-os)
1. [限制密码的使用](https://docs.microsoft.com/hololens/security-limiting-password-use)

## 物理安全性
HoloLens 2 具有受 [BitLocker](https://docs.microsoft.com/hololens/security-encryption-data-protection)加密保护的闪存内存。 你的设备及其本地数据可以使用高级恢复助手脱机闪烁，或者通过[](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab)MDM 远程擦除（如果已将其部署为托管设备）。

## 数据保护
默认情况下，Windows 更新 (运行，) [Azure 集成](https://docs.microsoft.com/hololens/security-encryption-data-protection#Azure-integration) 保护在自身和云之间传输的数据。 

将 HoloLens 2 部署到外部客户端时 [，Dynamics 365 Remote Assist](https://docs.microsoft.com/hololens/hololens2-deployment-guide) 可确保敏感公司数据和资源是独立且安全的。 

可在 OOBE 期间由 MDM 或用户手动配置与 Microsoft 的诊断数据共享。 有两个选项：可选诊断数据和必需诊断数据。 如果稍后需要更改原始诊断设置以进行故障排除，则用户可以在"设置"-> 隐私 **->** 诊断 & 反馈或 IT 管理员 (MDM) （如果是托管设备）中更改它。 查看有关 [Windows 10 中的诊断、反馈和隐私的更多信息](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)。

> [!Important]
> 设备诊断日志包含个人身份信息 (PII) ，例如有关用户在典型操作期间启动的进程或应用程序。 例如，当多个用户共享 HoloLens 设备 (时，用户使用不同的 Microsoft Azure Active Directory (Azure AD) 帐户登录同一设备) 诊断日志可能包含适用于多个用户的 PII 信息。

 

有几种 [收集方法和数据保留策略](https://docs.microsoft.com/hololens/hololens-diagnostic-logs) ，用于收集 HoloLens 2 中的诊断数据。  有关 Microsoft 如何收集和使用诊断数据的信息，请参阅[Microsoft 隐私声明 - 诊断](https://privacy.microsoft.com/privacystatement)- 在左侧导航菜单中展开**Windows，** 然后选择 **"诊断"。** 转到" **诊断"** 部分。
