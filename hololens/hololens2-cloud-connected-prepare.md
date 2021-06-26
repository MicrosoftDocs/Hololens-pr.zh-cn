---
title: 部署指南 - 使用 HoloLens 2 大规模部署云Remote Assist - 准备
description: 了解如何准备使用 Azure Active Directory 和标识管理通过云连接的网络注册 HoloLens 设备。
keywords: HoloLens， 管理， 云连接， Remote Assist， AAD， Azure AD， MDM， 移动设备管理
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
ms.openlocfilehash: 21132ed5d1e84d92a877747ac9a4c090b177ca08
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924564"
---
# <a name="prepare---cloud-connected-guide"></a>准备 - 云连接指南

本文结束时，你将设置 Azure AD MDM，并了解有关使用Azure AD和网络要求。 本指南的此部分将帮助你和组织准备好将HoloLens 2部署到云并使用Dynamics 365 Remote Assist。 它将了解基础结构的每个部分的重要性，并提供指向指南的链接，以帮助你根据需要设置这些部分。

## <a name="infrastructure-essentials"></a>基础结构基本信息

对于个人和公司部署方案，MDM 系统是部署和管理设备所需的Windows 10 全息版基础结构。 Azure AD Premium 订阅建议作为标识提供程序，并且需要用于支持某些功能。

### <a name="azure-active-directory"></a>Azure Active Directory

Azure AD是一种基于云的目录服务，可提供标识和访问管理。 使用 Microsoft Office 365 或 Intune 的组织已使用具有三个版本的 Azure AD：免费版、高级 P1 版和高级 P2 版 (请参阅 [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions)版本 .) 所有版本都支持 Azure AD 设备注册，但需要 Premium P1 才能启用 MDM 自动注册，我们稍后将在本指南中使用它。

> [!IMPORTANT]
> 必须创建一个Azure Active Directory，因为 HoloLens 设备不支持本地 AD 联接。 如果尚未&#39;设置Azure Active Directory，请转到在 中[创建新Azure Active Directory。](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)

## <a name="identity-management"></a>标识管理

员工只能使用一个帐户来初始化设备，因此&#39;组织必须控制首先启用的帐户。 所选帐户将确定由谁来控制设备，并影响管理功能。

在本指南中，我们已选择"标识使用 ["，](https://docs.microsoft.com/hololens/hololens-identity) 我们将使用Azure AD帐户或Azure Active Directory帐户。 使用Azure AD帐户有几个好处，例如：

- 员工使用Azure AD帐户在 Azure AD 中注册设备，并自动向组织注册&#39;MDM 解决方案 (Azure AD+MDM – 需要Azure AD Premium) 。
- Azure AD帐户支持 [单一登录](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)。 当用户登录到 Remote Assist，将识别已登录用户Azure AD标识，并且用户将登录到应用，获得简化的体验。
- Azure AD帐户具有其他[身份验证选项，Windows Hello 企业版。](https://docs.microsoft.com/hololens/hololens-identity) [](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) 除了 Iris 登录外，用户还可以从另一台设备登录或使用 FIDO 安全密钥。

### <a name="mobile-device-management"></a>移动设备管理

Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)是 企业移动性 + 安全性的一部分，是一个基于云的 MDM 系统，用于管理连接到租户的设备。 与 Office 365 一样，Intune 使用 Azure AD 进行标识管理，因此员工使用相同的凭据在 Intune 中注册设备，这些凭据用于登录 Office 365。 Intune 还支持运行其他操作系统（如 iOS 和 Android）的设备，以提供完整的 MDM 解决方案。 在本指南中，我们将重点介绍&#39;Intune，以便通过 HoloLens 2 实现大规模云部署。

> [!IMPORTANT]
> 必须拥有移动设备管理。 如果尚未&#39;，请按照本指南和 [Intune 入门操作](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)。

> [!NOTE]
> 多个 MDM 系统支持 Windows 10 并且大部分都支持个人和公司设备部署方案。 目前，支持Windows 10 全息版 MDM 提供程序包括：AirWatch、MobileIron 等。 大多数行业领先的 MDM 供应商已支持与 Azure AD 集成。 可在 [Azure Marketplace](https://azure.microsoft.com/marketplace/) 中查找支持 Azure AD 的 MDM 供应商。

## <a name="network"></a>网络

在此设置中，我们HoloLens 2任何可用的开放网络连接到 Internet Wi-Fi设备。 由于用户可能需要根据位置更改网络连接，因此他们应了解如何将 [HoloLens 设备连接到 Wi-Fi。](https://docs.microsoft.com/hololens/hololens-network)

例如Dynamics 365 Remote Assist各种网络条件（包括带宽、延迟、抖动和数据包丢失）可能会影响视频通话体验。 尽管可以在带宽降低的环境中进行音频和视频调用，但可能会遇到功能降级的情况。 在 HoloLens Dynamics 365 Remote Assist时，请记住以下网络要求：

**最低** ：对等 HD 质量视频通话需要 1.5 Mbps 向上/向下，HD 1080p 分辨率为 30 fps。

**最佳：** 对于 HD 1080p 分辨率为 4-5 Mbps 的对等 HD 质量视频通话，应会向上/向下 4-5 Mbps。

详细信息：

- [网络要求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [网络优化建议](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a>可选：将 HoloLens 连接到 VPN

连接到本指南的设备将通过网络和外部云网络连接到网络。 访问公司资源可能需要&#39;VPN 连接设备。 可通过多种不同方式将设备连接到 VPN，其中最终用户可以使用设备 UI 进行连接，也可以通过 PPKG 或 MDM 管理设备并接收 VPN 配置文件。 本文不会&#39;VPN 设置方法，因此，&#39;详细了解不同的 VPN 协议或 VPN 管理方法，请访问这些指南，了解有关[HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn)和 VPN 的信息。

## <a name="next-step"></a>后续步骤

> [!div class="nextstepaction"]
> [云连接部署 - 配置](hololens2-cloud-connected-configure.md)
