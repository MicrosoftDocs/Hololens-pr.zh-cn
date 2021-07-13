---
title: 使用 Microsoft Endpoint Manager Intune 管理 HoloLens 设备
description: 了解如何使用 Intune 在大规模配置 CSP、策略和管理 HoloLens 混合现实设备。
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
ms.openlocfilehash: 5485a4b2558a11a6c0545ec8b3405c120cff287c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640265"
---
# <a name="using-microsofts-endpoint-manager-intune-to-manage-hololens-devices"></a>使用 Microsoft Endpoint Manager Intune 管理 HoloLens 设备

有多种不同的设置可通过 MDM 进行管理。 使用 Intune 设备可以组合在一起，并且可以将配置部署到这些用户或设备组。 还可以部署和管理应用、设置设备以连接到网络，以及将更新配置为在所需时间和需要的更新环上发生。 

## <a name="how-to-manage-via-intune"></a>如何通过 Intune 进行管理

### <a name="device-categories-and-groups"></a>设备类别和组
使用 Intune，你可以创建设备类别，以根据你创建的类别（例如工程、医学、开发人员等）自动将设备添加到组。 其目的是让管理运行 Windows Holographic for Business 的设备变得更轻松。
了解详细信息：将 [设备分类为组](/mem/intune/enrollment/device-group-mapping)

### <a name="device-configuration-profiles"></a>设备配置文件
Intune 提供可在组织内的不同设备上启用或禁用的设置和功能。 这些设置和功能通过配置文件进行管理。 例如，可以在运行 Windows Holographic for Business 的设备上创建一个启用 Cortana 或使用 Microsoft Defender Smart Screen 的配置文件。
在配置文件中，可以使用 OMA-URI 来自定义某些设置、创建设备限制并配置虚拟专用网络 (VPN) 和 Wi-Fi。
[配置文件入门](/mem/intune/configuration/device-profiles)和 [配置文件概述](/mem/intune/configuration/device-profile-create)。

## <a name="examples-of-what-can-be-managed-and-configured"></a>可管理和配置的示例

使用 MDM 管理设备可提供一系列可以选择的项。 

### <a name="wi-fi"></a>Wi-Fi
[Wi-Fi 设置](/mem/intune/configuration/wi-fi-settings-configure)将无线网络设置分配给用户和设备。 分配 Wi-Fi 配置文件时，用户可以访问公司 Wi-Fi，而无需自行配置。
详细了解如何[配置网络以进行 HoloLens](hololens-commercial-infrastructure.md)

### <a name="certificates"></a>证书
证书通过提供 web 内容的帐户身份验证、Wi-Fi 身份验证、VPN 加密和 SSL 加密来帮助提高安全性。 尽管管理员可以通过预配包手动管理设备上的证书，但最佳做法是使用 MDM 系统管理整个生命周期中的那些证书–从注册到续订和吊销。 注册 (设备后，你的 MDM 系统可以自动将这些证书部署到设备的证书存储中，只要 MDM 系统支持简单证书注册协议 (SCEP) 或公钥加密标准 #12 (PKCS # 12) ) 。 MDM 还可以查询和删除已注册的客户端证书，或在当前证书过期之前触发新的注册请求。 

### <a name="proxy"></a>代理
大多数公司 intranet 网络都利用代理来管理内部流量。 使用 HoloLens 2 可以为以太网和 Wi-Fi 连接配置代理服务器。 这些设置不适用于 VPN 连接。 有关 Windows 10 的代理设置的详细信息，请参阅[NetworkProxy CSP](/windows/client-management/mdm/networkproxy-csp)。

### <a name="vpn"></a>VPN
组织通常使用 VPN 来控制对其公司 Intranet 上的应用和资源的访问权限。 HoloLens 2 支持 SSL VPN 连接，这需要来自 Microsoft Store 的可下载插件并且特定于所选的 VPN 供应商。 
- 阅读[HoloLens 上有关 VPN 的](hololens-network.md#vpn)详细信息。
- 有关 VPN 配置文件的详细信息，请参阅 [VPNV2 CSP](/windows/client-management/mdm/vpnv2-csp)。

### <a name="deploy-and-manage-apps"></a>部署和管理应用
使用 Intune 可以向运行 Windows Holographic for Business 的设备添加应用。 通过 MDM 解决方案，IT 决策者和管理员可通过个人自动安装 (推送) 其内部、业务线应用，或者通过应用商店为一组用户购买应用。 有多种部署应用的方法，包括：
-   [Intune 和公司门户]( app-deploy-intune.md)
-   [适用于企业的 Microsoft Store]( app-deploy-store-business.md)

了解有关通过 Intune 进行的应用管理的详细信息。
-   [向 Intune 添加应用](/mem/intune/apps/apps-add)
-   [添加 Microsoft Store 应用](/mem/intune/apps/store-apps-windows)
-   [添加自己创建的应用](/mem/intune/apps/lob-apps-windows)
- [将应用分配给组](/mem/intune/apps/apps-deploy)

### <a name="software-updates"></a>软件更新
Intune 提供了一个名为“更新圈”的功能供 Windows 10 设备使用。 这些更新圈包括一组用于确定更新安装方式的设置。 例如，你可以创建一个维护时段来安装更新，也可以选择在安装更新后重新启动。 更新圈可应用于运行 Windows Holographic for Business 的多个设备。
详细了解如何通过 Intune[管理 HoloLens 更新](hololens-updates.md)和[管理软件更新](/mem/intune/protect/windows-update-for-business-configure)。

### <a name="configure-kiosk-mode"></a>配置展台模式
使用 Intune 提供的共享或来宾 PC 功能，可将 Windows Holographic for Business 设备配置为作为展台运行。 这些设备可以运行一个（单个应用展台模式）或多个应用（多个应用展台模式）。 展台模式是一种 UI，用于控制默认情况下哪些标识有权访问哪些应用。
了解如何[将 HoloLens 设置为展台]( hololens-kiosk.md)

