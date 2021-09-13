---
title: HoloLens 2 隐私和数据保护
description: 隐私文档
keywords: HoloLens、GDPR、隐私、PII、数据保护
author: golish
ms.author: marcingo
ms.reviewer: sekerawa, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 74f74645a3fc1282f48cb7ce0f6f722979c91b04
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032089"
---
# <a name="hololens-2-privacy-and-data-protection"></a>HoloLens 2 隐私和数据保护

GDPR 的核心元素之一是"设计数据保护"。 此概念尤其适用于移动设备（如 HoloLens 2，因为它们可移植性、无限制的 Internet 连接和打开的通信通道。 因此，HoloLens 2的安全性进行了重新设计，以端到端[](/hololens/security-architecture)提供高级、创新的安全和隐私保护，同时整合了 Microsoft 的隐私和[GDPR 法规](https://privacy.microsoft.com/)。

 >[!NOTE]
> 本文档不适用于第HoloLens (代) 。

## <a name="privacy-overview"></a>隐私概述

HoloLens 2是一台独立Windows计算机，运行 Windows Holographic，在沉浸式混合现实环境中运行应用和解决方案。 它可以用作安全的脱机设备或部署为 [组织中托管](/mem/intune/fundamentals/windows-holographic-for-business) 的设备。 请参阅以下链接，了解 HoloLens 2 Microsoft 如何使用和保护数据：

1. [Microsoft 隐私声明 - HoloLens](https://privacy.microsoft.com/privacystatement) - 展开左侧Enterprise菜单中的"开发人员和开发人员"部分，然后选择"Enterprise和 **开发人员软件及设备"。** 转到 **"HoloLens** 部分。
2. [Windows 10和联机服务](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 &隐私合规性指南](/windows/privacy/windows-10-and-privacy-compliance)
4. [Intune 中的隐私和个人数据](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>网络安全
遵循HoloLens 2部署方案"，[](/hololens/common-scenarios)数据将受[Azure](/azure/compliance/)的一流合规性以及法律/法规标准集成保护。 如果对 azure 和 Azure AD Dynamics 365 Remote Assist，请引用 GDPR 的 Azure 和[Dynamics 365 责任就绪情况清单](/compliance/regulatory/gdpr-arc-azure-dynamics)。

此外，Windows Defender防火墙提供了关键功能，用于保护设备连接。 使用 HoloLens 2，防火墙将始终处于启用状态，无法通过编程或 UI 禁用它。 使用[Intune](/mem/intune/protect/device-compliance-get-started)将 HoloLens 2部署为托管设备时，与作为移动威胁防御解决方案Microsoft Intune终结点集成时[，](/mem/intune/protect/advanced-threat-protection)可以使用更多符合性功能。

详细了解安全HoloLens 2[体系结构](/hololens/security-architecture)。

## <a name="os-security"></a>OS 安全性
默认情况下，更新 (自动) ，因此HoloLens 2 Holographic 和任何已安装应用的最新版本Windows始终为最新。 请参阅以下内容，详细了解如何安全设计 OS：

1. [状态分离和隔离](/hololens/security-state-separation-isolation)
1. [无管理员操作系统](/hololens/security-adminless-os)
1. [限制密码的使用](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>物理安全性
HoloLens 2具有受[BitLocker](/hololens/security-encryption-data-protection)加密 保护的闪存。 设备及其本地数据可以使用高级恢复助手脱机刷用，或者通过[](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab)MDM 远程擦除（如果已部署为托管设备）。

## <a name="data-protection"></a>数据保护
Windows默认情况下， (自动运行更新) [Azure 集成](/hololens/security-encryption-data-protection#Azure-integration)保护自身与云之间的数据传输。

在将HoloLens 2外部客户端[时，Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide)可确保敏感公司数据和资源是独立的且安全的。

可以在 OOBE 期间由 MDM 或用户手动配置与 Microsoft 共享诊断数据。 有两种选择：可选诊断数据和所需的诊断数据。 如果需要稍后更改原始诊断设置以进行故障排除，则用户可以在 **设置 -> Privacy -> Diagnostics & Feedback** 或 IT 管理员 (MDM) （如果 是托管设备）中更改此设置。 在 中[查看有关诊断、反馈和隐私Windows 10。](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)

> [!Important]
> 设备诊断日志包含 PII (个人身份) ，例如有关用户在典型操作期间启动的进程或应用程序的信息。 例如，当多个HoloLens设备 (时，用户使用不同的 Microsoft Azure Active Directory (Azure AD) 帐户登录到同一设备) 诊断日志中可能包含适用于多个用户的 PII 信息。

有几种[收集方法和数据保留策略](/hololens/hololens-diagnostic-logs)用于从数据库收集诊断HoloLens 2。  有关 Microsoft 如何收集和使用诊断数据的信息，请参阅 Microsoft 隐私声明 [-](https://privacy.microsoft.com/privacystatement)诊断 -展开Windows左侧导航菜单中的"诊断"并选择"**诊断"。** 转到" **诊断"** 部分。
