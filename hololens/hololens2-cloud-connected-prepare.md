---
title: 部署指南-Cloud 通过远程辅助功能在规模上部署 HoloLens 2 部署-准备
description: 如何准备通过连接到云的网络注册 HoloLens 设备
keywords: HoloLens、管理、云连接、远程协助、AAD、Azure AD、MDM、移动设备管理
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
ms.openlocfilehash: 0e9222df2c387fab8f61a585d3a7f3966b9ecd31
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196270"
---
# 准备-云连接指南

在本文末尾，你将设置 AAD、MDM 以及了解有关使用 AAD 帐户和网络要求的详细信息。 本指南的此部分将帮助你和你的组织准备将 HoloLens 2 部署到云并使用 Dynamics 365 远程协助。 它将对你的基础结构的每个部分的重要性进行比较，并提供指南的链接，以帮助你根据需要设置这些片段。

## 基础结构基础

对于个人和企业部署方案，MDM 系统是部署和管理 Windows 10 全息版设备所需的基本基础结构。 Azure AD Premium 订阅建议作为标识提供程序，并且需要用于支持某些功能。

### Azure Active Directory

Azure AD 是一项基于云的目录服务，可提供标识和访问管理。 使用 Microsoft Office 365 或 Intune 的组织已使用了三个版本：免费、高级 P1 和 Premium P2 (请参阅 [Azure Active Directory 版本](https://azure.microsoft.com/documentation/articles/active-directory-editions)。 ) 所有版本都支持 azure AD 设备注册，但需要高级 P1 才能启用在本指南中将使用的 MDM 自动注册。

> [!IMPORTANT]
> 将 Azure Active Directory 用作 HoloLens 设备不支持本地广告联接非常重要。 如果你不&#39;t 已设置 Azure Active Directory，请按照此链接中的说明开始操作，并 [在 Azure Active Directory 中创建新租户](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)。

## 标识管理

员工只能使用一个帐户来初始化一个设备，因此它&#39;s 强制您的组织控制首先启用哪个帐户。 所选帐户将确定由谁来控制设备，并影响管理功能。

在本指南中，我们选择为使用的 [标识](https://docs.microsoft.com/hololens/hololens-identity) ，我们将使用 AAD 帐户或 Azure Active Directory 帐户。 我们希望使用的 AAD 帐户有多大好处，例如：

- 员工使用其 Azure AD 帐户在 Azure AD 中注册设备，并自动将其注册到组织&#39;s MDM 解决方案 (AAD + MDM-需要 Azure AD Premium) 。
- AAD 帐户支持 [单一登录](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)。 当用户登录到远程协助时，将识别来自已登录 AAD 用户的身份，并且用户将登录到应用以简化体验。
- AAD 帐户通过[Windows Hello 企业版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)提供其他[身份验证选项](https://docs.microsoft.com/hololens/hololens-identity)。 除了虹膜登录用户之外，还可以从另一台设备登录或使用 FIDO 安全密钥。

### 移动设备管理

Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)是企业移动性 + 安全性的一部分，是一个基于云的 MDM 系统，用于管理连接到你的租户的设备。 与 Office 365 一样，Intune 使用 Azure AD 进行身份管理，因此员工使用相同凭据在 Intune 中注册设备以登录到 Office 365。 Intune 还支持运行其他操作系统（如 iOS 和 Android）的设备，以提供完整的 MDM 解决方案。 出于本指南的目的，我们&#39;重点介绍使用 Intune 在使用 HoloLens 2 的比例下启用云部署。

> [!IMPORTANT]
> 具有移动设备管理的必要条件。 如果您没有设置&#39;请按照本指南进行设置，并 [开始使用 Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)。

> [!NOTE]
> 多个 MDM 系统支持 Windows 10 并且大部分都支持个人和公司设备部署方案。 支持 Windows 10 全息版的 MDM 提供程序当前包括： AirWatch、MobileIron 和其他。 大多数行业领先的 MDM 供应商已支持与 Azure AD 集成。 可在 [Azure Marketplace](https://azure.microsoft.com/marketplace/) 中查找支持 Azure AD 的 MDM 供应商。

## 网络

在此设置中，我们预计从任何可用的开放 Wi-Fi 网络连接到 Internet 的 HoloLens 2 设备。 由于用户可能需要根据位置更改网络连接，因此他们应该了解如何 [将 HoloLens 设备连接到 wi-fi。](https://docs.microsoft.com/hololens/hololens-network)

对于 Dynamics 365 远程协助，有多种网络状况，包括带宽、延迟、抖动和数据包丢失，可能会影响视频通话体验。 虽然在带宽降低的环境中可以进行音频和视频呼叫，但你可能会遇到功能下降。 在 HoloLens 上使用 Dynamics 365 远程协助时，请记住以下网络要求：

**最小** ： 1.5 Mbps 的高至对等 HD 视频通话需要分辨率为 30 FPS 的高清1080p。

**最佳：** 对于对等高清视频通话，采用高清1080p 的分辨率，应预计 4-5 Mbps。

详细信息：

- [网络要求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [网络优化建议](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### 可选：将 HoloLens 连接到 VPN

连接到本指南的设备将通过和外部云网络连接到网络。 可能需要访问公司资源，&#39;需要通过 VPN 连接您的设备。 有多种不同的方法将设备连接到 VPN，最终用户可以通过使用设备 UI 连接的位置，也可以通过 PPKG 或 MDM 管理设备并接收 VPN 配置文件。 如何设置 VPN&#39;t 在本文中介绍，因此，如果你&#39;d 想了解有关不同的 VPN 协议或管理 VPN 的方法，请访问 [这些指南以了解有关 HoloLens 和 vpn 的详细信息。](https://docs.microsoft.com/hololens/hololens-network#vpn)

## 下一步

> [!div class="nextstepaction"]
> [云连接部署-配置](hololens2-cloud-connected-configure.md)
