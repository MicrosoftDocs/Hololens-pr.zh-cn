---
title: 在商业环境中设置 HoloLens
description: 详细了解如何在企业环境中部署和管理 HoloLens，包括基础结构、azure active directory 和移动设备管理。
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308428"
---
# <a name="hololens-2-enterprise-deployment-and-management"></a>HoloLens 2 企业部署和管理

本概述旨在帮助 IT 专业人员了解在企业中部署和管理 Microsoft HoloLens 2 设备的注意事项。

HoloLens 2 在 Windows 10 全息版上运行，可为组织提供强大灵活的内置移动设备和应用管理技术。 Windows 10 全息版支持端到端设备生命周期管理，使公司可以控制其设备、数据和应用。 使用全面的移动设备管理解决方案，可以轻松地将 HoloLens 2 纳入到标准生命周期实践中，从设备注册、配置和应用程序管理到维护和停用。

## <a name="prepare"></a>准备

当你准备向企业企业环境中部署 HoloLens 2 时，应考虑几个注意事项，因为你开始规划 HoloLens 2 的规模部署。

### <a name="infrastructure-essentials"></a>基础结构概要

对于公司企业部署方案中的 HoloLens 2，需要具备一些必要的基本基础结构服务才能支持完整的功能集。 HoloLens 2 是在部署和管理的 [新式移动设备管理](https://www.microsoft.com/itshowcase/managing-windows-10-devices-with-microsoft-intune) 基础上构建的。 使用 Azure AD 加入到 MDM，作为在不断增长的移动工作人员中实现这一点的主要手段。 以下主题提供了有关在部署计划中应考虑的每个基础结构组件的简要概述。

### <a name="azure-active-directory"></a>Azure Active Directory
Azure AD 是一种基于云的目录服务，提供标识和访问管理。 可以将其与现有的本地目录集成以创建混合标识解决方案。 使用 Microsoft Office 365 或 Intune 的组织已使用 Azure AD，其中有三个版本：免费版、高级版 P1 和高级 P2 (，请参阅 [Azure Active Directory 版本](https://azure.microsoft.com/documentation/articles/active-directory-editions/)) 。 所有版本都支持 Azure AD 设备注册，但要求使用高级 P1 来启用 MDM 自动注册。 HoloLens 2 需要 Azure Active Directory 联接才能实现大多数企业级特性和功能。

> [!NOTE]
> 在本地 Active Directory 联接在 HoloLens 2 上不受支持。

### <a name="mobile-device-management"></a>移动设备管理
HoloLens 2 专用于企业环境中的移动设备管理 (MDM) 系统进行管理。 Microsoft [Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)是企业移动性 + 安全性的一部分，它是一种基于云的 MDM 系统，用于管理企业中的设备。 与 Office 365 一样，Intune 使用 Azure AD 进行标识管理，因此员工使用相同的凭据在 Intune 中注册设备，以用于登录到 Office 365。 多个 MDM 系统支持 Windows 10 并且大部分都支持个人和公司设备部署方案。 MDM 系统还可以管理 HoloLens 2 的应用程序部署和更新。 其他支持 HoloLens 2 的 MDM 提供程序当前包括： AirWatch、MobileIron 和其他。 所有 MDM 系统供应商都有权访问 Windows 10 设备管理配置服务提供程序 (CSP) s，使 IT 组织可以自由选择哪个系统最适合其管理要求，无论 Microsoft Intune 还是第三方 MDM 产品。

> [!NOTE]
> HoloLens 2 上不支持传统的本地电脑管理系统，如 System Center Configuration Manager。

### <a name="windows-update-for-business"></a>Windows Update for Business
Microsoft 设计适用于企业的 Windows 更新以为 IT 管理员提供更多以 Windows 更新为中心的管理功能，例如对一组设备部署更新的功能，以及为安装更新而定义维护窗口的功能。 有关管理 HoloLens 2 更新的详细信息，请参阅 [HoloLens 更新](https://docs.microsoft.com/hololens/hololens-updates) 文档。

### <a name="certificates"></a>证书
如果你的环境需要用于企业 Wi-Fi 网络身份验证或访问其他资源的证书，则 HoloLens 2 支持通过 MDM 部署证书。 若要启用到 HoloLens 2 的证书部署，可能需要某些 MDM 基础结构配置。 了解如何为 [HoloLens 2 准备证书和网络配置文件](https://docs.microsoft.com/hololens/hololens-certificates-network)。 如果使用 Intune，请查看 [证书配置](https://docs.microsoft.com/mem/intune/protect/certificates-configure) 详细信息。

## <a name="configure"></a>配置

MDM 管理员可以在 MDM 系统中注册的任何公司设备上定义和实施策略设置。 你使用的配置设置会因部署方案而异。 在 Windows 10 中，配置服务提供程序 (CSP) s 是用于读取、设置、修改或删除设备上的配置设置的接口。 这些设置将映射到注册表项或文件。 有关适用于 HoloLens 2 的 Windows 10 设备管理 Csp 的详细信息，请参阅 [hololens 设备中受支持的 csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)的完整列表。

HoloLens 2 还支持通过自定义设置包设置有限的 CSP 配置集。 预配包通常用于非 MDM 托管设备，需要手动应用于每个设备。 有关生成自定义预配包的详细信息，请参阅 [HoloLens 预配](https://docs.microsoft.com/hololens/hololens-provisioning) 文档。

> [!NOTE]
> HoloLens 2 支持 [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)，它为管理公司 Windows 10 设备配置提供了一个简单简单的过程。

### <a name="identity-management"></a>标识管理

员工只能使用一个帐户来初始化设备，因此，在你的组织控制首先启用哪个帐户时，它&#39;。 所选帐户将确定由谁来控制设备，并影响管理功能。 HoloLens 2 支持3种帐户类型：本地用户帐户、个人 Microsoft 帐户和 Azure Active Directory 帐户。 强烈建议将 Azure Active Directory 用于企业标识管理解决方案，因为它将在你的 HoloLens 2 设备上启用全部功能。 有关 HoloLens 2 的标识的详细信息，请查看 [hololens 标识](https://docs.microsoft.com/hololens/hololens-identity) 。

### <a name="network-and-connectivity"></a>网络和连接

因为 HoloLens 2 是云优先设备，所以需要对联机资源进行网络访问，才能获得完整功能和功能。 如果要使用连接到公司 intranet 网络的安装 HoloLens 2 设备，则可能需要更新代理/防火墙规则，以允许对 HoloLens 2 云服务进行访问。 有关详细信息，请查看 [HoloLens 2 操作系统的常见终结点](https://docs.microsoft.com/hololens/hololens-offline)列表。 若要成功在 HoloLens 2 上运行应用程序或其他云服务，可能需要访问其他终结点。

某些常见的 HoloLens 2 服务需要其他终结点访问权限，如下所示：

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)
- [D365 指南](https://support.microsoft.com/en-us/help/2655102/internet-accessible-urls-required-for-connectivity-to-microsoft-dynami)
- [D365 远程协助 (O365 团队基础结构) ](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

### <a name="certificate-deployment"></a>证书部署

如果需要证书来访问企业 Wi-Fi 网络或组织中的其他服务，HoloLens 2 支持通过 MDM 部署用户和设备证书。 注意： MDM 解决方案可能需要额外的基础结构配置才能将证书部署到 Windows 10 设备。

### <a name="security-review"></a>安全检查

大多数企业 IT 部门需要对部署到公司企业网络的新设备进行评估和审查。 如果你的组织需要 HoloLens 2 的安全审查，你可以找到更多详细信息以帮助你 [获取安全批准](https://docs.microsoft.com/hololens/security-overview)。

### <a name="common-hololens-2-device-settings"></a>常见的 HoloLens 2 设备设置

将 HoloLens 2 设备部署到公司企业环境时，在规划 HoloLens 2 的部署时，可能会考虑许多常见的设备配置。 此列表突出显示了非常常见的配置和设置，并且不包括可用选项的完整列表：

| 设备设置 | 简短说明。                                                                              |
|----------------|-------------------------------------------------------------------------------------------------|
| [硬件限制](hololens-requirements.md#hardware-restrictions)               | 硬件限制降低了连接性并帮助保护数据。                        |
| [Wi-Fi 配置文件](hololens-requirements.md#wi-fi-profiles)               | 配置 Wi-Fi 配置文件，无需用户干预或交互。                              |
| [Certificates](hololens-requirements.md#certificates-1)               | 为 web 内容提供帐户和/或 Wi-Fi 身份验证、VPN 加密和 SSL 加密。 |
| [Proxy](hololens-requirements.md#proxy)              | 管理内部流量。                                                                        |
|  [VPN](hololens-requirements.md#vpn)              | 控制对其公司 intranet 上的应用程序和资源的访问。                               |
| [展台模式](hololens-requirements.md#kiosk-mode) | 限制通过 UI 向用户显示的应用程序。 |

#### <a name="hardware-restrictions"></a>硬件限制

HoloLens 2 使用先进的技术，其中包括相机、麦克风、扬声器、USB 接口、蓝牙接口和 Wi-fi 等热门硬件功能。 可使用硬件限制控制这些功能的可用性。

以下列出了 HoloLens 2 支持用于配置硬件限制的最常用 MDM 设置。 其中一些硬件限制提供连接和协助数据保护。

- [**允许 WiFi：**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi#wifi-allowwifi) 用户是否可以在其设备上启用并使用 Wi-Fi 收音机
- [**允许 USB 连接：**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 是否启用 USB 连接 (&#39;t 是否会影响 USB 充电) 
- [**允许蓝牙：**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowbluetooth) 用户是否可以在其设备上启用和使用蓝牙收音机

阅读有关其他[常见设备限制的](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)详细信息。

#### <a name="wi-fi-profiles"></a>Wi-Fi 配置文件

大多数企业 Wi-Fi 网络都需要证书和其他复杂信息来限制和保护用户访问。 这种高级 Wi-Fi 的信息对典型用户来说很难配置，但 MDM 系统无需用户干预即可完全配置这些 Wi-Fi 配置文件。 在 MDM 系统中，你可以创建多个 WLAN 配置文件。

有关适用于 Windows 10 的 Wi-Fi 设置的更多详细信息，请参阅 [企业配置文件 WiFi 设置](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-windows#enterprise-profile)。

#### <a name="certificates"></a>证书

证书通过提供 web 内容的帐户身份验证、Wi-Fi 身份验证、VPN 加密和 SSL 加密来帮助提高安全性。 尽管管理员可以通过预配包手动管理设备上的证书，但它&#39;是使用 MDM 系统在整个生命周期（从注册到续订和吊销）管理这些证书的最佳做法。 在注册设备 (之后，你的 MDM 系统可以自动将这些证书部署到&#39; 的证书存储设备，前提是 MDM 系统支持简单证书注册协议 (SCEP) 或 #12 PKCS # 12 () ) 的公钥加密标准。 MDM 还可以查询和删除已注册的客户端证书，或在当前证书过期之前触发新的注册请求。

详细了解如何为 [HoloLens 2 准备证书和网络配置文件。](https://docs.microsoft.com/hololens/hololens-certificates-network)

#### <a name="proxy"></a>代理

大多数公司 intranet 网络都利用代理来管理内部流量。 使用 HoloLens 2，你可以为以太网和 Wi-Fi 连接配置代理服务器。 这些设置不适用于 VPN 连接。

有关适用于 Windows 10 的代理设置的更多详细信息，请参阅 [NETWORKPROXY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)。

#### <a name="vpn"></a>VPN

组织通常使用 VPN 来控制对其公司&#39;的 intranet 上的应用程序和资源的访问。 HoloLens 2 支持 SSL VPN 连接，这需要 Microsoft Store 的可下载插件，并特定于所选的 VPN 供应商。

有关 VPN 配置文件的更多详细信息，请参阅 [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx)

#### <a name="kiosk-mode"></a>展台模式

可以通过将设备配置为在展台模式下运行，将 HoloLens 2 设备配置为固定用途的设备，也称为展台。 展台模式限制设备上可用的应用程序 (或用户) 。 展台模式是一项方便的功能，可用于将 HoloLens 2 设备专用于企业应用，或在应用演示中使用 HoloLens 2 设备。

有关在展台模式下配置 HoloLens 2 的详细信息，请参阅 [将 Hololens 设置为展台](https://docs.microsoft.com/hololens/hololens-kiosk)

## <a name="deploy"></a>部署

### <a name="mdm-device-enrollment"></a>MDM 设备注册

对于企业部署，建议仅使用 Azure AD 联接和自动 MDM 注册 (Azure AD + MDM) 将设备作为公司设备 [注册](https://docs.microsoft.com/hololens/hololens-enroll-mdm) 到 mdm。 这需要 Azure AD Premium 并支持自动注册到多个 MDM 提供程序，包括 Intune。

详细了解自行部署注册方法 [Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)。

### <a name="application-deployment"></a>应用程序部署

用户在移动设备上的工作效率通常由应用驱动。

通过 Windows 10，能够使用适用于 Windows 应用的通用 Windows 平台 (UWP) 开发可跨多台设备无缝工作的应用。

可以通过多种方式将应用程序部署到 HoloLens 2 设备。 可以通过 MDM、Microsoft Store for Business 或旁加载通过预配包直接部署应用。 有关更多详细信息，请查看 [应用部署](https://docs.microsoft.com/hololens/app-deploy-overview) 文档。

> [!NOTE]
> HoloLens 2 仅支持运行 UWP ARM64 应用。

## <a name="maintain"></a>维护

在企业 IT 环境中，安全性和成本控制的需求需要与为用户提供最新技术的需求平衡。 由于网络攻击已成为日常事件，因此务必正确维护 Windows 10 设备的状态。 IT 需要控制配置设置，使其退出合规性，以及强制哪些设备可以访问内部应用程序。 HoloLens 2 提供了移动运营管理功能，以确保设备符合公司策略。

### <a name="os-servicing-options"></a>OS 服务选项

**简化的更新过程**

Microsoft 简化了 Windows 产品工程设计和发布周期，以便能够比以往更快地提供市场需要的新特性、体验以及功能。 Microsoft 计划每年（12 个月期限）提供两个功能更新。 **功能更新** 建立 CURRENT BRANCH 或 CB，并具有关联的版本。

Microsoft 还将直接向 HoloLens 2 设备交付和安装安全更新和稳定更新。 每月都提供通过 Windows 更新在 Microsoft 控制下发布的这些 **质量更新** 。 HoloLens 2 在同一标准更新过程中使用功能更新和质量更新。

企业客户可以使用 MDM 系统管理更新体验并在 HoloLens 2 上进行处理。 在大多数情况下，管理更新过程的策略将应用于功能和质量更新。 更多详细信息，请 [为 HoloLens 更新配置 MDM](https://docs.microsoft.com/hololens/hololens-updates)。

### <a name="managing-applications"></a>管理应用程序

IT 管理员可以控制哪些应用程序可安装在 HoloLens 2 上，以及应如何保持最新。

HoloLens 2 支持 [Windows Defender 应用程序控制 (WDAC) ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)，这使管理员能够从 Microsoft Store 创建、允许或禁止应用列表。 此功能也可扩展到内置应用。 允许或拒绝应用的功能有助于确保用户使用其设备来实现其预期目的。 但是，这并不总是在员工需求或请求和安全问题之间寻求平衡的简便方法。 创建允许或禁止列表还需要在 Microsoft Store 中不断更改应用横向布局。

有关更多详细信息，请参阅 [应用程序控制 CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp)。

### <a name="retire"></a>停用

设备停用是设备生命周期的最后一个阶段。 这&#39;重要的是，由于不&#39;t 想让任何公司数据保留在可能危及数据机密性的丢弃设备上，因此，要替换为较新型号的设备会被安全停用。 IT 还需要一种充分支持需要擦除已丢失或被盗设备的用户的方式。

HoloLens 2 支持通过3种方法擦除设备

**MDM 工厂擦除：** 通过管理员启动的 MDM 命令将 HoloLens 2 重置回出厂映像。 清除设备上的所有存储的数据。

**从 "设置" 中重置设备：** 最终用户可以在设备上的 "设置" 应用中手动重置 HoloLens 2。 清除设备上的所有存储的数据。

**高级恢复助理 (ARC) ：** 在运行 ARC 工具的电脑上，用户或管理员可以通过 USB 电缆闪烁连接到电脑的 HoloLens 2。 清除设备上的所有存储的数据。

> [!div class="nextstepaction"]
> [常见部署方案](common-scenarios.md)
