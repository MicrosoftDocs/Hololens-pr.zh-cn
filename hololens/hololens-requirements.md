---
title: 在商业环境中设置 HoloLens
description: 了解有关在企业环境中部署和管理 HoloLens 的详细信息。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: scooley
ms.author: scooley
ms.reviewer: aboeger
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/30/2020
ms.openlocfilehash: b7523b8ab38cfc37795ea6c99f9b22953baffe47
ms.sourcegitcommit: 30e910348f5d5b68e914219c8eadb34d93770eab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2020
ms.locfileid: "11099801"
---
# HoloLens 2 企业版部署和管理

本概述旨在帮助 IT 专业人员了解在企业中部署和管理 Microsoft HoloLens 2 设备的注意事项。

HoloLens 2 在 Windows 10 全息版上运行，可为组织提供强健、灵活、内置的移动设备和应用管理技术。 Windows 10 全息版支持端到端设备生命周期管理，使公司能够控制其设备、数据和应用。 使用全面的移动设备管理解决方案，可以轻松将 HoloLens 2 合并到标准的生命周期做法中，从设备注册、配置和应用程序管理到维护和停用。

## 准备

在准备将 HoloLens 2 部署到企业企业环境时，应考虑在开始规划 HoloLens 2 的缩放部署时应考虑和理解的一些注意事项。

### 基础结构基础

对于在企业企业部署方案中使用 HoloLens 2，需要具备支持整套功能所需的一些基本基础结构服务。 HoloLens 2 是在部署和管理方面考虑的 [新式移动设备管理](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) 。 使用 Azure AD 加入 + MDM 作为在不断增长的移动工作中实现这一主要手段。 以下主题简要介绍了在 HoloLens 2 的部署规划中应考虑的每个基础结构组件。

### Azure Active Directory
Azure AD 是一项基于云的目录服务，可提供标识和访问管理。 可以将其与现有的本地目录集成以创建混合标识解决方案。 使用 Microsoft Office 365 或 Intune 的组织已使用过以下三个版本：免费、高级 P1 和高级 P2 (请参阅 [Azure Active Directory 版本](https://azure.microsoft.com/documentation/articles/active-directory-editions/)) 。 所有版本均支持 Azure AD 设备注册，但需要高级 P1 才能启用 MDM 自动注册。 HoloLens 2 需要 Azure Active Directory Join 才能启用大多数企业级功能和功能。

> [!NOTE]
> HoloLens 2 上不支持本地活动目录联接。

### 移动设备管理
HoloLens 2 专为在企业环境中 (MDM) 系统管理的移动设备管理而设计。 Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)是企业移动性 + 安全性的一部分，是基于云的 MDM 系统，用于管理企业中的设备。 与 Office 365 一样，Intune 使用 Azure AD 进行身份管理，因此员工使用相同凭据在 Intune 中注册设备以登录到 Office 365。 多个 MDM 系统支持 Windows 10 并且大部分都支持个人和公司设备部署方案。 MDM 系统也可以同时管理 HoloLens 2 的应用程序部署和更新。 支持 HoloLens 2 的其他 MDM 提供程序目前包括： AirWatch、MobileIron 和其他支持。 所有 MDM 系统供应商都具有对 Windows 10 设备管理配置服务提供程序的相同访问权限 (CSP) s，让 IT 组织能够自由选择哪一个系统最适合其管理要求，无论是 Microsoft Intune 还是第三方 MDM 产品。

> [!NOTE]
> HoloLens 2 上不支持传统的本地电脑管理系统，如 System Center Configuration Manager。

### 适用于企业的 Windows 更新
Microsoft 设计适用于企业的 Windows 更新以为 IT 管理员提供更多以 Windows 更新为中心的管理功能，例如对一组设备部署更新的功能，以及为安装更新而定义维护窗口的功能。 可在 [此处](https://docs.microsoft.com/hololens/hololens-updates)找到用于管理 HoloLens 2 更新的详细信息。

### 证书
如果你的环境需要用于 Corp Wi-fi 网络身份验证的证书或对其他资源的访问权限，则 HoloLens 2 支持通过 MDM 部署证书。 某些 MDM 基础结构配置可能需要启用对 HoloLens 2 的证书部署。 阅读有关如何为 [HoloLens 2 准备证书和网络配置文件的](https://docs.microsoft.com/hololens/hololens-certificates-network)信息。 可 [在此处](https://docs.microsoft.com/mem/intune/protect/certificates-configure)找到 Intune 详细信息。

## 配置

MDM 管理员可以在任何在 MDM 系统中注册的企业设备上定义和实施策略设置。 你使用的配置设置将根据部署方案而有所不同。 在 Windows 10 中，配置服务提供程序 (CSP) s 是用于读取、设置、修改或删除设备上的配置设置的接口。 这些设置将映射到注册表项或文件。 有关 HoloLens 2 的 Windows 10 设备管理 Csp 的详细信息，请参阅 [hololens 设备中受支持的 csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)的完整列表。

HoloLens 2 还支持通过自定义预配程序包设置有限的 CSP 配置集。 预配程序包通常可用于非 MDM 托管设备，并且需要手动应用到每个设备。 可在 [此处](https://docs.microsoft.com/hololens/hololens-provisioning)找到有关生成自定义预配包的详细信息。

> [!NOTE]
> HoloLens 2 支持 [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)，为管理企业 Windows 10 设备配置提供了一个简单且简单的过程。

### 标识管理

员工只能使用一个帐户来初始化一个设备，因此它&#39;s 强制您的组织控制首先启用哪个帐户。 所选帐户将确定由谁来控制设备，并影响管理功能。 HoloLens 2 支持3种帐户类型：本地用户帐户、个人 Microsoft 帐户和 Azure Active Directory 帐户。 强烈建议使用适用于你的企业标识管理解决方案的 Azure Active Directory，因为它将在你的 HoloLens 2 设备上启用完整功能。 可在 [此处](https://docs.microsoft.com/hololens/hololens-identity)找到有关 HoloLens 2 上的标识的更多详细信息。

### 网络和连接性

由于 HoloLens 2 是云第一个设备，因此需要对联机资源的网络访问才能获得完整功能和功能。 如果要使用与公司 intranet 网络的连接部署 HoloLens 2 设备，可能需要更新代理/防火墙规则，以便允许访问 HoloLens 2 云服务。 可在 [此处](https://docs.microsoft.com/hololens/hololens-offline)找到 HoloLens 2 操作系统所需的常用终结点列表。 可能需要访问其他终结点，应用程序或其他云服务才能成功运行于 HoloLens 2。

某些常见的 HoloLens 2 服务需要其他终结点访问权限，如下所示：

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365 指南](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 远程协助 (O365 团队基础结构) ](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### 证书部署

如果访问企业 Wi-fi 网络或组织中的其他服务需要证书，则 HoloLens 2 支持通过 MDM 进行用户和设备证书部署。 注意：你的 MDM 解决方案可能需要额外的基础结构配置才能将证书部署到 Windows 10 设备。

### 安全检查

大多数企业 IT 部门将需要评估和查看部署到企业企业网络的新设备。 如果您的组织需要 HoloLens 2 的安全检查，您可以在 [此处找到更多详细信息以帮助您获得安全批准](https://docs.microsoft.com/hololens/security-overview)。

### 常规 HoloLens 2 设备设置

将 HoloLens 2 设备部署到企业企业环境时，在规划 HoloLens 2 部署时可能会考虑许多常见的设备配置。 此列表突出显示了非常常见的配置和设置，并且不包含可用选项的完整列表：

| 设备设置 | 简要说明。                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [硬件限制](hololens-requirements.md#hardware-restrictions)               | 硬件限制降低了连接能力并帮助保护数据。                        |
| [WLAN 配置文件](hololens-requirements.md#wi-fi-profiles)               | 配置 Wi-fi 配置文件，无需用户干预或交互。                              |
| [证书](hololens-requirements.md#certificates-1)               | 提供 web 内容的帐户和/或 Wi-fi 身份验证、VPN 加密和 SSL 加密。 |
| [代理](hololens-requirements.md#proxy)              | 管理内部流量。                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | 控制对其公司 intranet 上的应用和资源的访问。                               |
| [展台模式](hololens-requirements.md#kiosk-mode) | 限制通过 UI 向用户呈现的应用程序。 |

#### 硬件限制

HoloLens 2 使用包含常用硬件功能（如相机、麦克风、扬声器、USB 接口、蓝牙接口和 Wi-fi）的一流技术。 可使用硬件限制控制这些功能的可用性。

下表列出了 HoloLens 2 支持配置硬件限制的最常用 MDM 设置。 其中某些硬件限制提供连接性，并有助于数据保护。

- [**允许 WiFi：**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 用户是否可以在其设备上启用和使用 Wi-fi 收音机
- [**允许 USB 连接：**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 是否启用 USB 连接 (&#39;t 影响 USB 收费) 
- [**允许蓝牙：**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 用户是否可以在其设备上启用和使用蓝牙收音机

阅读有关其他[常见设备限制的](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)详细信息。

#### WLAN 配置文件

大多数企业 WLAN 网络需要证书和其他复杂信息来限制和保护用户访问。 此高级 Wi-fi 信息很难供典型用户进行配置，但 MDM 系统可以完全配置这些 Wi-fi 配置文件，而无需用户干预。 在 MDM 系统中，你可以创建多个 WLAN 配置文件。

有关 Windows 10 的 Wi-fi 设置的更多详细信息，请参阅 [企业配置文件 WiFi 设置](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)。

#### 证书

证书通过提供 web 内容的帐户身份验证、Wi-fi 身份验证、VPN 加密和 SSL 加密来帮助提高安全性。 尽管管理员可以通过预配程序包手动管理设备上的证书，但&#39;最佳做法是使用 MDM 系统在整个生命周期内管理这些证书-从注册到续订和吊销。 只要 MDM 系统支持简单证书注册协议 (SCEP) 或公钥加密标准 #12 # A5 (# A5，你的 MDM 系统就可以在注册 (设备后自动将这些证书部署到&#39; 的证书存储设备。只要 MDM 系统支持简单证书注册协议 SCEP 或公钥加密标准) # A5。 MDM 还可以在当前证书过期之前查询和删除注册的客户端证书或触发新的注册请求。

阅读有关如何[为 HoloLens 2 准备证书和网络配置文件的](https://docs.microsoft.com/hololens/hololens-certificates-network)详细信息。

#### 代理

大多数公司 intranet 网络都利用代理来管理内部流量。 使用 HoloLens 2，你可以配置用于以太网和 Wlan 连接的代理服务器。 这些设置不适用于 VPN 连接。

有关 Windows 10 的代理设置的更多详细信息，请参阅 [NETWORKPROXY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)。

#### VPN

组织通常使用 VPN 控制对其公司&#39;s intranet 上的应用和资源的访问。 HoloLens 2 支持 SSL VPN 连接，这需要 Microsoft Store 中的可下载插件，并且特定于你选择的 VPN 供应商。

有关 VPN 配置文件的更多详细信息，请参阅 [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### 展台模式

你可以将 HoloLens 2 设备配置为固定用途的设备（也称为展台），方法是将设备配置为在展台模式下运行。 展台模式限制设备上可用 (或用户) 的应用程序。 展台模式是一种方便的功能，可用于将 HoloLens 2 设备专用于商业应用，或在应用演示中使用 HoloLens 2 设备。

有关在展台模式下配置 HoloLens 2 的更多详细信息，请参阅 [设置 HoloLens 作为展台](https://docs.microsoft.com/hololens/hololens-kiosk)

## 部署

### MDM 设备注册

对于企业部署，建议仅使用 Azure AD join 和自动 MDM 注册 (AAD + MDM) ，将设备作为公司设备 [注册](https://docs.microsoft.com/hololens/hololens-enroll-mdm) 到 mdm。 这需要 Azure AD Premium 并支持自动注册到多个 MDM 提供程序（包括 Intune）。

了解有关自我部署注册方法 [Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)的详细信息。

### 应用程序部署

用户在移动设备上的工作效率通常由应用驱动。

通过 Windows 10，能够使用适用于 Windows 应用的通用 Windows 平台 (UWP) 开发可跨多台设备无缝工作的应用。

有多种方法可将应用程序部署到 HoloLens 2 设备。 可通过预配包直接部署 MDM、Microsoft Store for Business 或旁加载中的应用。 [可在此处找到有关应用部署](https://docs.microsoft.com/hololens/app-deploy-overview)的更多详细信息。

> [!NOTE]
> HoloLens 2 仅支持仅运行 UWP ARM64 应用。

## 维护

在企业 IT 环境中，安全性和成本控制的需求需要与为用户提供最新技术的需求平衡。 由于 cyberattacks 已成为日常事件，因此正确维护 Windows 10 设备的状态非常重要。 IT 需要控制配置设置，使其退出合规性，以及强制哪些设备可以访问内部应用程序。 HoloLens 2 提供了必要的移动运营管理功能，以确保设备遵守公司政策。

### OS 服务选项

**简化的更新过程**

Microsoft 简化了 Windows 产品工程设计和发布周期，以便能够比以往更快地提供市场需要的新特性、体验以及功能。 Microsoft 计划每年（12 个月期限）提供两个功能更新。 **功能更新** 建立当前分支或 CB，并且具有关联的版本。

Microsoft 还会将安全和稳定性的更新直接提交和安装到 HoloLens 2 设备。 通过 Windows Update 发布的 Microsoft control 下的这些 **质量更新** 将在每月提供。 HoloLens 2 在同一标准更新过程中使用功能更新和质量更新。

企业客户可以使用 MDM 系统管理 HoloLens 2 的更新体验和处理。 在大多数情况下，管理更新过程的策略将应用于功能和质量更新。 有关为 [HoloLens 更新配置 MDM 的](https://docs.microsoft.com/hololens/hololens-updates)详细信息。

### 管理应用程序 

IT 管理员可以控制在 HoloLens 2 上可以安装哪些应用以及它们应保持最新状态。

HoloLens 2 支持 [Windows Defender 应用程序控件 (WDAC) ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)，使管理员能够从 Microsoft Store 创建、允许或禁止应用列表。 此功能还可扩展到内置应用。 允许或拒绝应用的功能有助于确保用户使用其设备来实现其预期用途。 但是，这并不总是在员工需求或请求和安全问题之间寻求平衡的简便方法。 创建允许或禁止列表还需要在 Microsoft Store 中不断更改应用横向布局。

有关更多详细信息，请参阅 [应用程序控制 CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)。

### 停用

设备停用是设备生命周期的最后一个阶段。 很重要的是，由于&#39;您不希望任何公司数据保留在可能危及数据保密的设备上，因此在使用较新的模型替换的设备被安全停用的重要&#39;。 IT 还需要一种充分支持需要擦除已丢失或被盗设备的用户的方式。

HoloLens 2 支持用于擦除设备的3种方法

**MDM 工厂擦除：** 通过管理员启动的 MDM 命令将 HoloLens 2 重置回出厂映像。 擦除设备上存储的所有数据。

**从 "设置" 中的设备重置：** 最终用户可以在设备上的 "设置" 应用中手动重置 HoloLens 2。 擦除设备上存储的所有数据。

**高级恢复配套 (ARC) ：** 在运行 ARC 工具的 PC 上，用户或管理员可以通过 USB 电缆将已连接到电脑的 HoloLens 2 闪烁。 擦除设备上存储的所有数据。
