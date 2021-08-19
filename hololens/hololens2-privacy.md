---
title: HoloLens 2隐私和数据保护
description: 隐私文档
keywords: HoloLens，GDPR，隐私，PII，数据保护
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
ms.sourcegitcommit: 548550f309010fa95f674a7ff688166a31cf1963
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2021
ms.locfileid: "122336730"
---
# <a name="hololens-2-privacy-and-data-protection"></a>HoloLens 2隐私和数据保护

GDPR 的核心元素之一是 "按设计数据保护"。 此概念特别适用于移动设备（如 HoloLens 2），因为其可移植性、无限制 internet 连接和开放的通信通道。 Resultingly，已对 HoloLens 2 的[安全性](/hololens/security-architecture)进行了重新设计，以提供一种端到端的高级、创新的安全和隐私保护，同时结合了 Microsoft 的[隐私和 GDPR 法规](https://privacy.microsoft.com/)。

 >[!NOTE]
> 本文档不适用于 (第一代) HoloLens。

## <a name="privacy-overview"></a>隐私概述

HoloLens 2 是一台独立的 Windows 计算机，运行 Windows 全息版，可在沉浸式现实环境中运行应用和解决方案。 它可用作安全的脱机设备，或部署为组织内的 [托管设备](/mem/intune/fundamentals/windows-holographic-for-business) 。 请参阅以下链接，了解 HoloLens 2 和 Microsoft 如何使用和保护你的数据：

1. [Microsoft 隐私声明-HoloLens](https://privacy.microsoft.com/privacystatement) -展开左侧导航菜单中的 " **Enterprise 和开发人员**" 部分，然后选择 " **Enterprise 和开发人员软件和设备**"。 请参阅 **HoloLens** 部分。
2. [Windows 10 和联机服务](https://privacy.microsoft.com/windows10privacy)
3. [Windows 10 & 隐私符合性指南](/windows/privacy/windows-10-and-privacy-compliance)
4. [Intune 中的隐私和个人数据](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a>网络安全
按照 HoloLens 2[常见的部署方案](/hololens/common-scenarios)，你的数据将受到[Azure 世界一流的法规遵从性](/azure/compliance/)以及法律/法规标准集成的保护。 如果不熟悉 Azure AD 和 Dynamics 365 Remote Assist，请参阅 GDPR 的[Azure 和 Dynamics 365 责任准备情况清单](/compliance/regulatory/gdpr-arc-azure-dynamics)。

此外，Windows Defender 防火墙提供重要功能来保护设备连接。 使用 HoloLens 2，防火墙将始终处于启用状态，无法通过编程或 UI 禁用它。 如果使用[Intune](/mem/intune/protect/device-compliance-get-started)将 HoloLens 2 部署为托管设备，则可通过将[终结点与 Microsoft Intune](/mem/intune/protect/advanced-threat-protection)为移动威胁防御解决方案集成，来提供更多相容性功能。

了解有关 HoloLens 2[安全性和体系结构](/hololens/security-architecture)的详细信息。

## <a name="os-security"></a>操作系统安全性
默认情况下会自动执行更新)  (，因此 HoloLens 2 始终使用最新版本的 Windows 全息版和任何已安装的应用程序。 请参阅以下内容，了解有关如何安全设计我们的 OS 的详细信息：

1. [状态分离和隔离](/hololens/security-state-separation-isolation)
1. [无管理员操作系统](/hololens/security-adminless-os)
1. [限制密码的使用](/hololens/security-limiting-password-use)

## <a name="physical-security"></a>物理安全性
HoloLens 2 具有受[BitLocker 加密](/hololens/security-encryption-data-protection)保护的闪存。 如果已将设备及其本地数据部署为托管设备，则可以使用 [高级恢复助理](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) 进行脱机刷新，也可以通过 MDM 远程擦除。

## <a name="data-protection"></a>数据保护
默认情况下，Windows 更新会自动运行 () 和[Azure 集成](/hololens/security-encryption-data-protection#Azure-integration)可保护其自身与云之间的数据传输。

向外部客户端部署 HoloLens 2 时， [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide)确保你的敏感公司数据和资源既是单独的，又是安全的。

与 Microsoft 共享诊断数据可以通过 MDM 或用户在 OOBE 期间手动配置。 有两种选择：可选诊断数据和所需的诊断数据。 如果最初的诊断设置需要在以后进行故障排除时进行更改，则用户可以在 **设置 > 的隐私 > 诊断 & 反馈** 或 it 管理员 (MDM) （如果是托管设备）中更改它。 有关详细信息[，请参阅 Windows 10 中的诊断、反馈和隐私](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)。

> [!Important]
> 设备诊断日志包含 (PII) 的个人身份信息，例如用户在典型操作过程中启动的进程或应用程序。 当多个用户共享 HoloLens 设备时 (例如，用户使用不同的 Microsoft Azure Active Directory (Azure AD) 帐户登录到同一设备) 诊断日志可能包含适用于多个用户的 PII 信息。

有[几个收集方法和数据保留策略](/hololens/hololens-diagnostic-logs)可用于从 HoloLens 2 收集诊断数据。  有关 microsoft 如何收集和使用诊断数据的详细信息，请参阅左侧导航菜单中的 [microsoft 隐私声明-诊断](https://privacy.microsoft.com/privacystatement)-展开 **Windows** ，并选择 "**诊断**"。 请参阅 " **诊断** " 部分。
