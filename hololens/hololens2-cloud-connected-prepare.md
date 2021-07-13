---
title: 部署指南–云连接 HoloLens 2 大规模部署，并提供远程协助-准备
description: 了解如何准备使用 azure active directory 和标识管理，通过已连接到云的网络注册 HoloLens 设备。
keywords: HoloLens，管理，云连接，远程协助，AAD，Azure AD，MDM，移动设备管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 21fffdc24f8682bc44779e1cebe8cd6eacb59619
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639652"
---
# <a name="prepare---cloud-connected-guide"></a>准备-云连接指南

本文结束时，将设置 Azure AD 和 MDM，并了解有关使用 Azure AD 帐户和网络要求的详细信息。 本指南部分将帮助你和你的组织准备好将 HoloLens 2 部署到云并使用 Dynamics 365 Remote Assist。 它将通过基础结构的每个部分的重要性，并提供指南的链接，以帮助你根据需要设置这些部分。

## <a name="infrastructure-essentials"></a>基础结构概要

对于个人和公司部署方案，MDM 系统是部署和管理 Windows 10 全息版设备所需的基本基础结构。 Azure AD Premium 订阅建议作为标识提供程序，并且需要用于支持某些功能。

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD 是一种基于云的目录服务，提供标识和访问管理。 使用 Microsoft Office 365 或 Intune 的组织已使用 Azure AD，其中有三个版本：免费版、高级版 P1 和高级版 P2 (参见[Azure Active Directory 版本](https://azure.microsoft.com/documentation/articles/active-directory-editions)。 ) 所有版本都支持 Azure AD 设备注册，但要启用 MDM 自动注册，需要使用高级版 P1，稍后将使用此指南。

> [!IMPORTANT]
> 需要 Azure Active Directory，因为 HoloLens 设备不支持本地 AD 联接。 如果&#39;t 已设置 Azure Active Directory，请参阅[在 Azure Active Directory 中创建新租户](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)。

## <a name="identity-management"></a>标识管理

员工只能使用一个帐户来初始化设备，因此，在你的组织控制首先启用哪个帐户时，它&#39;。 所选帐户将确定由谁来控制设备，并影响管理功能。

在本指南中，我们选择了为使用的[标识](/hololens/hololens-identity)使用 Azure AD 帐户，或 Azure Active Directory 帐户。 我们要使用 Azure AD 帐户有多个优点，例如：

- 员工使用他们的 Azure AD 帐户在 Azure AD 中注册设备，并自动将其注册到组织&#39;的 mdm 解决方案 (Azure AD + mdm-需要 Azure AD Premium) 。
- Azure AD 帐户支持 [单一登录](/azure/active-directory/manage-apps/what-is-single-sign-on)。 当用户登录到远程协助时，将识别其登录 Azure AD 用户的标识，并将用户登录到应用以简化体验。
- Azure AD 帐户通过[Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification)提供额外的[身份验证选项](/hololens/hololens-identity)。 除了 Iris 登录用户以外，用户还可以从其他设备登录或使用 FIDO 安全密钥。

### <a name="mobile-device-management"></a>移动设备管理

Microsoft [Intune](/mem/intune/fundamentals/what-is-intune)是企业移动性 + 安全性的一部分，它是一种基于云的 MDM 系统，用于管理连接到租户的设备。 与 Office 365 一样，Intune 使用 Azure AD 进行标识管理，因此员工使用相同的凭据在 Intune 中注册设备，这些设备用于登录 Office 365。 Intune 还支持运行其他操作系统（如 iOS 和 Android）的设备，以提供完整的 MDM 解决方案。 出于本指南的目的，我们&#39;将重点放在使用 Intune 来实现规模规模的云部署，HoloLens 2。

> [!IMPORTANT]
> 有必要进行移动设备管理。 如果未&#39;t，请遵循本指南并 [开始使用 Intune](/mem/intune/fundamentals/free-trial-sign-up)。

> [!NOTE]
> 多个 MDM 系统支持 Windows 10 并且大部分都支持个人和公司设备部署方案。 支持 Windows 10 全息版的 MDM 提供程序当前包括： AirWatch、MobileIron 和其他。 大多数行业领先的 MDM 供应商已支持与 Azure AD 集成。 可在 [Azure Marketplace](https://azure.microsoft.com/marketplace/) 中查找支持 Azure AD 的 MDM 供应商。

## <a name="network"></a>网络

在此设置中，我们预计 HoloLens 2 设备从任何可用的开放 Wi-Fi 网络连接到 Internet。 由于用户可能需要根据位置更改网络连接，因此应了解如何[将 HoloLens 设备连接到 wi-fi。](/hololens/hololens-network)

对于 Dynamics 365 Remote Assist 有各种网络条件，包括带宽、延迟、抖动和数据包丢失，这可能会影响你的视频呼叫体验。 尽管在带宽减少的环境中可能会发生音频和视频呼叫，但你可能会遇到功能下降。 使用 HoloLens 上的 Dynamics 365 Remote Assist 时，需要记住以下网络要求：

**最小值** ：对于对等 hd 质量视频调用，1.5 Mbps 向上/向下需要，分辨率为 30 fps，分辨率为高清1080p。

**最佳：** 对于对等 HD 质量视频调用（分辨率为高清1080p），应预计 4-5 Mbps。

详细信息：

- [网络要求](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [网络优化建议](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>可选：将 HoloLens 连接到 VPN

正在连接到本指南的设备将通过和外部云网络连接到网络。 可以访问公司资源，&#39;需要通过 VPN 连接设备。 可以通过多种不同的方式将设备连接到 VPN，其中，最终用户可以通过使用设备 UI 连接到这些设备，也可以通过 PPKG 或 MDM 管理设备并接收 VPN 配置文件。 在本文中，如何设置 VPN 会赢得&#39;t，因此，如果&#39;d 类了解有关不同 vpn 协议或管理 vpn 的方法的详细信息，请访问[这些指南以获取 HoloLens 和 VPN 的相关信息。](/hololens/hololens-network#vpn)

## <a name="next-step"></a>下一步

> [!div class="nextstepaction"]
> [云连接部署-配置](hololens2-cloud-connected-configure.md)
