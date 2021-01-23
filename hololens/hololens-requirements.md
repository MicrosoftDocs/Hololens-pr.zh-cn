---
title: 在商业环境中设置 HoloLens
description: 了解有关在企业环境中部署和管理 HoloLens（包括基础结构、azure Active directory 和移动设备管理）中有关详细信息。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
ms.openlocfilehash: 9458a6fd02cf96dd265580cb099e39fa221d4206
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284043"
---
# HoloLens 2 企业版部署和管理

本概述旨在帮助 IT 专业人员了解在企业内部署和管理 Microsoft HoloLens 2 设备的注意事项。

HoloLens 2 在 Windows 10 全息版上运行，可为组织提供可靠、灵活、内置的移动设备以及应用管理技术。 Windows 10 全息版支持端到端设备生命周期管理，使公司能够控制其设备、数据和应用。 HoloLens 2 可轻松纳入标准生命周期做法，从设备注册、配置和应用程序管理到使用全面的移动设备管理解决方案进行维护和停用。

## 准备

准备将 HoloLens 2 部署到企业企业环境时，开始规划 HoloLens 2 的大规模部署时，应查看和理解一些注意事项。

### 基础结构要素

对于企业企业部署方案中的 HoloLens 2，需要某些基础结构服务来支持整套功能。 HoloLens 2 是在部署和管理 [时](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) 考虑现代移动设备管理而构建的。 使用 Azure AD 加入 + MDM 作为在不断增加的移动员工中实现此目标的主要方式。 以下主题简要概述了在 HoloLens 2 的部署规划中应考虑的每个基础结构组件。

### Azure Active Directory
Azure AD 是一项基于云的目录服务，可提供标识和访问管理。 可以将其与现有的本地目录集成以创建混合标识解决方案。 使用 Microsoft Office 365 或 Intune 的组织已在使用 Azure AD，Azure AD 具有三个版本：免费版、高级 P1 版和高级 P2 (请参阅 [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions/)) 。 所有版本都支持 Azure AD 设备注册，但需要高级 P1 才能启用 MDM 自动注册。 HoloLens 2 需要 Azure Active Directory 联接才能启用大多数企业级特性和功能。

> [!NOTE]
> HoloLens 2 不支持本地 Active Directory 加入。

### 移动设备管理
HoloLens 2 专为在企业环境中由移动设备管理 (MDM) 系统进行管理。 Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)是企业移动性 + 安全性的一部分，它是一个基于云的 MDM 系统，用于管理企业中的设备。 与 Office 365 一样，Intune 使用 Azure AD 进行身份管理，因此员工使用相同的凭据在 Intune 中注册他们用于登录 Office 365 的设备。 多个 MDM 系统支持 Windows 10 并且大部分都支持个人和公司设备部署方案。 MDM 系统还可以管理 HoloLens 2 的应用程序部署和更新。 支持 HoloLens 2 的其他 MDM 提供程序目前包括：AirWatch、MobileIron 和其他。 所有 MDM 系统供应商均具有对 Windows 10 设备管理配置服务提供程序 (CSP) 的同等访问权限，使 IT 组织可以自由地选择最符合其管理要求的任何系统，无论是 Microsoft Intune 还是第三方 MDM 产品。

> [!NOTE]
> HoloLens 2 不支持传统的本地电脑管理系统，如 System Center Configuration Manager。

### 适用于企业的 Windows 更新
Microsoft 设计适用于企业的 Windows 更新以为 IT 管理员提供更多以 Windows 更新为中心的管理功能，例如对一组设备部署更新的功能，以及为安装更新而定义维护窗口的功能。 有关管理 [HoloLens](https://docs.microsoft.com/hololens/hololens-updates) 2 更新的详细信息，请参阅 HoloLens 更新文档。

### 证书
如果你的环境需要 Corp 证书Wi-Fi网络身份验证或访问其他资源，HoloLens 2 支持通过 MDM 部署证书。 可能需要一些 MDM 基础结构配置才能将证书部署到 HoloLens 2。 了解如何为 [HoloLens 2](https://docs.microsoft.com/hololens/hololens-certificates-network)准备证书和网络配置文件。 如果你使用的是 Intune，请查看认证 [配置](https://docs.microsoft.com/mem/intune/protect/certificates-configure) 详细信息。

## 配置

MDM 管理员可以在 MDM 系统中注册的任何公司设备上定义和实施策略设置。 根据部署方案，使用的配置设置将有所不同。 在 Windows 10 中， (CSP) 是一个接口，用于读取、设置、修改或删除设备的配置设置。 这些设置将映射到注册表项或文件。 有关适用于 HoloLens 2 的 Windows 10 设备管理 CSP 有关详细信息，请参阅 [HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)设备中支持的 AP 的完整列表。

HoloLens 2 还支持通过自定义预配包设置一组有限的云解决方案提供商配置。 预配包通常用于非 MDM 托管设备，并且需要手动应用到每台设备。 有关生成自定义预配包的详细信息，请参阅 [HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning) 预配文档。

> [!NOTE]
> HoloLens 2 支持 [Windows Autopilot，](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)提供用于管理企业 Windows 10 设备配置的简单简单过程。

### 身份管理

员工只能使用一个帐户初始化设备，&#39;必须控制首先启用的帐户。 所选帐户将确定由谁来控制设备，并影响管理功能。 HoloLens 2 支持 3 种帐户类型：本地用户帐户、个人 Microsoft 帐户和 Azure Active Directory 帐户。 强烈建议将 Azure Active Directory 用于企业标识管理解决方案，因为它将在 HoloLens 2 设备上启用全部功能。 查看 [HoloLens 标识](https://docs.microsoft.com/hololens/hololens-identity) ，了解有关 HoloLens 2 的标识的更多详细信息。

### 网络和连接

由于 HoloLens 2 是云第一设备，因此网络访问联机资源是提供完整功能所需的。 如果要部署与公司 Intranet 网络连接的 HoloLens 2 设备，可能需要更新代理/防火墙规则以允许访问 HoloLens 2 云服务。 有关详细信息，请参阅 [HoloLens 2](https://docs.microsoft.com/hololens/hololens-offline)操作系统的常见终结点列表。 应用程序或其他云服务可能需要访问其他终结点才能成功在 HoloLens 2 上运行。

需要其他终结点访问的一些常见 HoloLens 2 服务如下所示：

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365 指南](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 远程协助 (O365 Teams 基础结构) ](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### 证书部署

如果需要证书才能访问公司证书Wi-Fi组织内部的其他服务，HoloLens 2 支持通过 MDM 部署用户和设备证书。 注意：MDM 解决方案可能需要其他基础结构配置，以将证书部署到 Windows 10 设备。

### 安全审查

大多数企业 IT 部门都需要评估和审查要部署到企业企业网络的新设备。 如果你的组织需要 HoloLens 2 的安全审查，你可以找到更多详细信息来帮助 [获取安全批准](https://docs.microsoft.com/hololens/security-overview)。

### 通用 HoloLens 2 设备设置

将 HoloLens 2 设备部署到企业企业环境时，在规划 HoloLens 2 部署时，可能会考虑许多常见设备配置。 此列表突出显示了发现非常常见的配置和设置，它们不包含可用选项的完整列表：

| 设备设置 | 简要说明。                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [硬件限制](hololens-requirements.md#hardware-restrictions)               | 硬件限制会降低连接性，并有助于数据保护。                        |
| [WLAN 配置文件](hololens-requirements.md#wi-fi-profiles)               | 配置Wi-Fi配置文件，而无需用户干预或交互。                              |
| [证书](hololens-requirements.md#certificates-1)               | 提供帐户和/Wi-Fi Web 内容的身份验证、VPN 加密和 SSL 加密。 |
| [代理](hololens-requirements.md#proxy)              | 管理内部流量。                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | 控制对公司 Intranet 上应用和资源的访问。                               |
| [展台模式](hololens-requirements.md#kiosk-mode) | 限制通过 UI 向用户显示的应用程序。 |

#### 硬件限制

HoloLens 2 使用一线技术，其中包括常用硬件功能，如相机、麦克风、扬声器、USB 接口、Bluetooth接口和 WLAN。 可使用硬件限制控制这些功能的可用性。

下面列出了 HoloLens 2 支持配置硬件限制的最常用的 MDM 设置。 其中某些硬件限制提供连接性，并有助于数据保护。

- [**允许 WiFi：**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 用户是否可以在设备上启用和使用Wi-Fi无线广播
- [**允许 USB 连接：**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) USB 连接是否已启用 (&#39;USB 充电) 
- [**允许Bluetooth：**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 用户是否可以在设备上启用和使用Bluetooth无线广播

阅读有关其他 [常见设备限制的信息。](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)

#### WLAN 配置文件

大多数企业 WLAN 网络需要证书和其他复杂信息来限制和保护用户访问。 此高级Wi-Fi用户很难配置，但 MDM 系统可以完全配置这些Wi-Fi配置文件，而无需用户干预。 在 MDM 系统中，你可以创建多个 WLAN 配置文件。

有关 Windows 10 Wi-Fi设置的详细信息，请参阅 [企业配置文件 WiFi 设置](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)。

#### 证书

证书通过提供帐户身份验证、Wi-Fi、VPN 加密和 Web 内容的 SSL 加密来帮助提高安全性。 尽管管理员可以通过预配包手动管理设备上证书，&#39;最佳做法是在整个生命周期（从注册到续订和吊销）使用 MDM 系统管理这些证书。 MDM 系统可以在注册设备 (后自动将这些证书部署到设备&#39; 证书存储，只要 MDM 系统支持简单证书注册协议 (SCEP) 或公钥加密标准 #12 (PKCS#12) ) 。 MDM 还可以在当前证书过期之前查询和删除已注册的客户端证书或触发新的注册请求。

阅读更多有关如何为 [HoloLens 2 准备证书和网络配置文件的信息。](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### 代理

大多数企业 Intranet 网络都利用代理来管理内部流量。 使用 HoloLens 2，可以配置用于以太网和 Wi-Fi连接的代理服务器。 这些设置不适用于 VPN 连接。

有关 Windows 10 的代理设置的更多详细信息，请参阅[NetworkProxy CSP。](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)

#### VPN

组织通常使用 VPN 控制对公司或 Intranet 上&#39;资源的访问。 HoloLens 2 支持 SSL VPN 连接，这需要从 Microsoft Store 下载插件，并且特定于你选择的 VPN 供应商。

有关 VPN 配置文件的更多详细信息，请参阅 [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### 展台模式

你可以将 HoloLens 2 设备配置为在展台模式下运行，以用作固定用途的设备（也称为展台）。 展台模式限制 (或) 设备上可用的应用程序。 展台模式是一项便捷功能，可用于将 HoloLens 2 设备专用于业务应用，或在应用演示中使用 HoloLens 2 设备。

有关在展台模式下配置 HoloLens 2 的更多详细信息，请参阅将 [HoloLens 设置为展台](https://docs.microsoft.com/hololens/hololens-kiosk)

## 部署

### MDM 设备注册

对于企业部署，建议仅通过 Azure [](https://docs.microsoft.com/hololens/hololens-enroll-mdm) AD 加入和 Azure AD+MDM (将设备注册为公司设备) 。 这需要 Azure AD Premium，并支持自动注册多个 MDM 提供程序（包括 Intune）。

了解有关自部署注册方法 [Autopilot 的更多信息](https://docs.microsoft.com/hololens/hololens2-autopilot)。

### 应用程序部署

用户在移动设备上的工作效率通常由应用驱动。

通过 Windows 10，能够使用适用于 Windows 应用的通用 Windows 平台 (UWP) 开发可跨多台设备无缝工作的应用。

有多种方法将应用程序部署到 HoloLens 2 设备。 可通过 MDM、适用于企业 Microsoft Store 直接部署应用，或通过预配包旁加载应用。 有关详细信息， [请查看应用](https://docs.microsoft.com/hololens/app-deploy-overview) 部署文档。

> [!NOTE]
> HoloLens 2 仅支持运行 UWP ARM64 应用。

## 维护

在企业 IT 环境中，安全性和成本控制的需求需要与为用户提供最新技术的需求平衡。 由于网络攻击已成为日常事件，因此正确维护 Windows 10 设备的状态非常重要。 IT 需要控制配置设置，使其退出合规性，以及强制哪些设备可以访问内部应用程序。 HoloLens 2 提供确保设备符合公司策略所需的移动操作管理功能。

### 操作系统服务选项

**简化的更新过程**

Microsoft 简化了 Windows 产品工程设计和发布周期，以便能够比以往更快地提供市场需要的新特性、体验以及功能。 Microsoft 计划每年（12 个月期限）提供两个功能更新。 **功能更新** 建立 Current Branch 或 CB，并且具有关联的版本。

Microsoft 还将直接向 HoloLens 2 设备提供和安装安全性和稳定性更新。 这些 **质量更新** 通过 Windows 更新在 Microsoft 控制下发布，每月提供一次。 HoloLens 2 使用功能更新和质量更新作为同一标准更新过程的一部分。

企业客户可以使用 MDM 系统在 HoloLens 2s 上管理更新体验和过程。 在大多数情况下，管理更新过程的策略将应用于功能和质量更新。 有关为 [HoloLens](https://docs.microsoft.com/hololens/hololens-updates)更新配置 MDM 的更多详细信息。

### 管理应用程序

IT 管理员可以控制允许哪些应用安装在 HoloLens 2 上，以及如何使应用保持最新。

HoloLens 2 支持 Windows Defender 应用程序控制 [ (WDAC) ， ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)这允许管理员创建、允许或禁止 Microsoft Store 中的应用列表。 此功能还扩展到内置应用。 允许或拒绝应用的能力有助于确保用户出于预期目的使用其设备。 但是，这并不总是在员工需求或请求和安全问题之间寻求平衡的简便方法。 创建允许或禁止列表还需要在 Microsoft Store 中不断更改应用横向布局。

有关详细信息，请参阅应用程序[控制 CSP。](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)

### 停用

设备停用是设备生命周期的最后阶段。 &#39;使用较新型号替换的设备安全停用非常重要，因为&#39;不希望任何公司数据保留在可能损害数据机密性的丢弃设备上。 IT 还需要一种充分支持需要擦除已丢失或被盗设备的用户的方式。

HoloLens 2 支持 3 种擦除设备的方法

**MDM 工厂擦除：** 通过管理员启动的 MDM 命令将 HoloLens 2 重置回出厂映像。 擦除设备上存储的所有数据。

**从"设置"中重置设备：** 最终用户可以在设备的"设置"应用中手动重置 HoloLens 2。 擦除设备上存储的所有数据。

**高级恢复助手 (ARC) ：** 从运行 ARC 工具的电脑中，用户或管理员可以通过 USB 电缆闪烁连接到电脑的 HoloLens 2。 擦除设备上存储的所有数据。

> [!div class="nextstepaction"]
> [常见部署方案](common-scenarios.md)
