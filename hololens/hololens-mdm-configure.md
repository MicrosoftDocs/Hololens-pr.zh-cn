---
title: 使用 Microsoft 的 Endpoint Manager Intune 管理 HoloLens 设备
description: 了解如何使用 MDM 使用 Intune 大规模配置云解决方案提供商、策略和管理 HoloLens 混合现实设备。
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
ms.openlocfilehash: ce288afdcb112c17ffde75078d641f3637a8448c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283953"
---
# 使用 Microsoft 的 Endpoint Manager Intune 管理 HoloLens 设备

可以通过 MDM 管理许多不同的设置。 使用 Intune 设备可以组合在一起，并且可以将配置部署到这些用户组或设备组。 还可以部署和管理应用、将设备设置为连接到网络，以及配置在所需时间和所需的更新环上发生的更新。 

## 如何通过 Intune 管理

### 设备类别和组
使用 Intune，你可以创建设备类别，以根据你创建的类别（如工程、医疗、开发人员等）将设备自动添加到组。 其理念是更轻松地管理运行 Windows Holographic for Business 的设备。
阅读更多内容 [：将设备分为多个组](https://docs.microsoft.com/mem/intune/enrollment/device-group-mapping)

### 设备配置文件
Intune 包括可在组织的不同设备上启用或禁用的设置和功能。 这些设置和功能使用配置文件进行管理。 例如，你可以创建启用 Cortana 的配置文件，或在运行 Windows Holographic for Business 的设备上使用 Microsoft Defender 智能屏幕。
在配置文件中，可以使用 OMA-URI 自定义一些设置、创建设备限制，以及配置虚拟专用网络 (VPN) WI-Fi。
[配置文件和配置文件概述](https://docs.microsoft.com/mem/intune/configuration/device-profiles)[入门](https://docs.microsoft.com/mem/intune/configuration/device-profile-create)。

## 可以管理和配置哪些功能的示例

使用 MDM 管理设备会提供大量可选项。 

### WLAN
[WLAN 设置](https://docs.microsoft.com/mem/intune/configuration/wi-fi-settings-configure) 将无线网络设置分配给用户和设备。 分配一个Wi-Fi配置文件时，用户无需自行Wi-Fi即可访问你的公司网站。
了解有关为 [HoloLens 配置网络](hololens-commercial-infrastructure.md)

### 证书
证书通过提供帐户身份验证、Wi-Fi、VPN 加密和 Web 内容的 SSL 加密来帮助提高安全性。 尽管管理员可以通过预配包手动管理设备上证书，但最佳做法是在整个生命周期（从注册到续订和吊销）使用 MDM 系统管理这些证书。 MDM 系统可以在注册设备 (后自动将这些证书部署到设备的证书存储，只要 MDM 系统支持简单证书注册协议 (SCEP) 或公钥加密标准 #12 (PKCS#12) ) 。 MDM 还可以在当前证书过期之前查询和删除已注册的客户端证书或触发新的注册请求。 

### 代理
大多数企业 Intranet 网络都利用代理来管理内部流量。 使用 HoloLens 2，可以配置用于以太网和 Wi-Fi连接的代理服务器。 这些设置不适用于 VPN 连接。 有关 Windows 10 的代理设置的更多详细信息，请参阅[NetworkProxy CSP。](https://docs.microsoft.com/windows/client-management/mdm/networkproxy-csp)

### VPN
组织通常使用 VPN 来控制对其公司 Intranet 上的应用和资源的访问权限。 HoloLens 2 支持 SSL VPN 连接，这需要从 Microsoft Store 下载插件，并且特定于你选择的 VPN 供应商。 
- 阅读有关 [HoloLens 上的 VPN 的更多信息](hololens-network.md#vpn)。
- 有关 VPN 配置文件的更多详细信息，请参阅[VPNv2 CSP。](https://docs.microsoft.com/windows/client-management/mdm/vpnv2-csp)

### 部署和管理应用
使用 Intune，你可以将应用添加到运行 Windows Holographic for Business 的设备。 MDM 解决方案使 IT 决策者和管理员可以专用地自动安装 (推送) 其内部、业务线应用，或通过应用商店为一组用户购买应用。 部署应用的方法有很多，包括：
-   [Intune 和公司门户]( app-deploy-intune.md)
-   [适用于企业的 Microsoft Store]( app-deploy-store-business.md)

详细了解如何通过 Intune 管理应用。
-   [将应用添加到 Intune](https://docs.microsoft.com/mem/intune/apps/apps-add)
-   [添加 Microsoft Store 应用](https://docs.microsoft.com/mem/intune/apps/store-apps-windows)
-   [添加你创建的应用](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
- [将应用分配给组](https://docs.microsoft.com/mem/intune/apps/apps-deploy)

### 软件更新
Intune 包括一项称为 Windows 10 设备的更新圈的功能。 这些更新圈包括一组确定如何安装更新的设置。 例如，可以创建维护时间窗口来安装更新，或选择在安装更新后重启。 更新圈可应用于运行 Windows Holographic for Business 的多个设备。
阅读更多有关通过 Intune 管理 [HoloLens](hololens-updates.md) 更新 [和管理软件更新的信息](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)。

### 配置展台模式
使用 Intune 中提供的共享或来宾电脑功能，你可以将 Windows Holographic for Business 设备配置为作为展台运行。 这些设备可以在单应用展台 (运行一个应用) ，或在多应用展台模式下 (多个应用) 。 展台模式是一种 UI，用于控制默认情况下哪些标识有权访问哪些应用。
了解如何将 [HoloLens 设置为展台]( hololens-kiosk.md)

