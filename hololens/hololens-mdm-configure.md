---
title: 使用 Microsoft 的终结点管理器 Intune 管理 HoloLens 设备
description: 使用 MDM 配置 CSP 和策略并按比例管理 HoloLens。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/9/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4fda0b271e915e82350f806418d2f02cbdd5a796
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009631"
---
# 使用 Microsoft 的终结点管理器 Intune 管理 HoloLens 设备

有许多不同的设置可通过 MDM 进行管理。 使用 Intune 设备可以组合在一起，并且可以将配置部署到这些用户或设备组。 还可以部署和管理应用、设置设备以连接到你的网络，以及将更新配置为在所需时间和需要的更新环上进行。 

## 如何通过 Intune 进行管理

### 设备类别和组
使用 Intune，你可以创建设备类别，以根据你创建的类别（如工程、医疗、开发人员等）自动将设备添加到组。 这样做的目的是使您能够更轻松地管理运行 Windows 全息版企业版的设备。
阅读详细信息：将 [设备分类到组](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### 设备配置文件
Intune 包括你可以在组织内的不同设备上启用或禁用的设置和功能。 这些设置和功能是使用配置文件管理的。 例如，你可以创建启用 Cortana 的配置文件，或在运行 Windows 全息版商业版的设备上使用 Microsoft Defender Smart 屏幕。
在你的配置文件中，你可以使用 OMA-URI 自定义某些设置、创建设备限制以及配置虚拟专用网络 (VPN) 和 Wlan。
[配置文件入门](https://docs.microsoft.com/mem/intune/configuration/device-profiles)和 [配置文件概述](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)。

## 可管理和配置的内容示例

使用 MDM 管理设备可提供一系列可供选择的项目。 

### WLAN
[Wi-fi 设置](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) 将无线网络设置分配给用户和设备。 分配 Wi-fi 配置文件时，用户无需自行配置即可访问您的企业 Wi-fi。
了解有关[配置 HoloLens 的网络的](hololens-commercial-infrastructure.md)详细信息

### 证书
证书通过提供 web 内容的帐户身份验证、Wi-fi 身份验证、VPN 加密和 SSL 加密来帮助提高安全性。 尽管管理员可以通过预配程序包手动管理设备上的证书，但最佳做法是使用 MDM 系统在整个生命周期中管理这些证书-从注册到续订和吊销。 注册设备后，你的 MDM 系统可以自动将这些证书部署到设备的证书存储中 (只要 MDM 系统支持简单证书注册协议 (SCEP) 或 #12 (PKCS # 12) # A5 的公钥加密标准。 MDM 还可以在当前证书过期之前查询和删除注册的客户端证书或触发新的注册请求。 

### 代理
大多数公司 intranet 网络都利用代理来管理内部流量。 使用 HoloLens 2，你可以配置用于以太网和 Wlan 连接的代理服务器。 这些设置不适用于 VPN 连接。 有关 Windows 10 的代理设置的更多详细信息，请参阅 [NETWORKPROXY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)。

### VPN
组织通常使用 VPN 来控制对其公司 Intranet 上的应用和资源的访问权限。 HoloLens 2 支持 SSL VPN 连接，这需要 Microsoft Store 中的可下载插件，并且特定于你选择的 VPN 供应商。 
- 阅读有关 [HoloLens 上的 VPN 的](hololens-network.md#vpn)详细信息。
- 有关 VPN 配置文件的更多详细信息，请参阅 [VPNV2 CSP](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)。

### 部署和管理应用
使用 Intune，你可以将应用添加到运行 Windows 全息版企业版的设备。 MDM 解决方案使 IT 决策者和管理员能够通过应用商店为一组用户在应用商店中私下自动安装 (推送) 其内部、业务线应用或购买应用。 部署应用有多种方法，包括：
-   [Intune 和公司门户]( app-deploy-intune.md)
-   [适用于企业的 Microsoft Store]( app-deploy-store-business.md)

通过 Intune 了解有关应用管理的详细信息。
-   [将应用程序添加到 Intune](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [添加 Microsoft Store 应用](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [添加你创建的应用](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [将应用分配到组](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### 软件更新
Intune 包括一个名为 Windows 10 设备的更新环的功能。 这些更新铃声包括一组确定如何安装更新的设置。 例如，可以创建维护时间窗口来安装更新，或选择在安装更新后重启。 更新铃声可应用于运行 Windows 全息版企业版的多台设备。
阅读有关如何通过 Intune [管理 HoloLens 更新](hololens-updates.md) 和 [管理软件更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)的详细信息。

### 配置展台模式
使用 Intune 中提供的共享或来宾电脑功能，您可以将 Windows 全息版设备配置为以展台身份运行。 这些设备可以 (单应用展台模式) 运行一个应用，也可以运行多个应用 (多应用展台模式) 。 展台模式是一个 UI，用于控制默认情况下哪些身份有权访问哪些应用。
了解如何 [将 HoloLens 设置为 kiosk]( hololens-kiosk.md)

