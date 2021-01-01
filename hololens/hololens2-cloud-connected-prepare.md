---
title: 部署指南 – 使用远程协助大规模部署云连接的 HoloLens 2 - 准备
description: 如何准备通过云连接网络注册 HoloLens 设备
keywords: HoloLens， 管理， 云连接， 远程协助， AAD， Azure AD， MDM， 移动设备管理
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
ms.openlocfilehash: a4e99740d985a709683595cd5afef76094faaf76
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253049"
---
# 准备 - 云连接指南

在本文末尾，你已设置 Azure AD、MDM，并了解有关使用 Azure AD 帐户和网络要求更多内容。 本指南的这一部分将帮助你和组织准备好将 HoloLens 2 部署到云并使用 Dynamics 365 远程协助。 它将了解基础结构各个部分的重要性，并提供指南链接，以帮助您根据需要设置这些部分。

## 基础结构要素

对于个人和公司部署方案，MDM 系统是部署和管理 Windows 10 全息版设备所需的基本基础结构。 Azure AD Premium 订阅建议作为标识提供程序，并且需要用于支持某些功能。

### Azure Active Directory

Azure AD 是一项基于云的目录服务，可提供标识和访问管理。 使用 Microsoft Office 365 或 Intune 的组织已在使用 Azure AD，Azure AD 有三个版本：免费版、高级版 P1 和高级 P2 (请参阅 [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions)版本 。) 所有版本都支持 Azure AD 设备注册，但需要高级 P1 才能启用 MDM 自动注册，我们将稍后在本指南中使用它。

> [!IMPORTANT]
> 必须拥有 Azure Active Directory，因为 HoloLens 设备不支持本地 AD 加入。 如果你尚未&#39;Azure Active Directory 设置，请按照此链接中的说明开始操作，在 Azure Active [Directory 中创建新租户](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)。

## 身份管理

员工只能使用一个帐户初始化设备，&#39;必须控制首先启用的帐户。 所选帐户将确定由谁来控制设备，并影响管理功能。

在本指南中，我们选择了对于 [使用的标识](https://docs.microsoft.com/hololens/hololens-identity) ，我们将使用 Azure AD 帐户或 Azure Active Directory 帐户。 对于我们希望使用的 Azure AD 帐户，有几个好处，例如：

- 员工使用其 Azure AD 帐户在 Azure AD 中注册设备，并自动向组织注册&#39;的 MDM 解决方案 (Azure AD+MDM - 需要 Azure AD Premium) 。
- Azure AD 帐户支持 [单一登录](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)。 当用户登录到远程协助时，将识别已登录 Azure AD 用户的标识，并且用户将登录到应用，从而获得简化的体验。
- Azure AD 帐户[](https://docs.microsoft.com/hololens/hololens-identity)通过 Windows Hello[企业计划提供其他身份验证选项](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)。 除了 Iris 登录外，用户还可以从另一台设备登录或使用 FIDO 安全密钥。

### 移动设备管理

Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)是企业移动性 + 安全性的一部分，是一个基于云的 MDM 系统，用于管理连接到租户的设备。 与 Office 365 一样，Intune 使用 Azure AD 进行身份管理，因此员工使用相同的凭据在 Intune 中注册他们用于登录 Office 365 的设备。 Intune 还支持运行其他操作系统（如 iOS 和 Android）的设备，以提供完整的 MDM 解决方案。 出于本指南的目的，我们将&#39;侧重于使用 Intune 通过 HoloLens 2 大规模启用云部署。

> [!IMPORTANT]
> 必须拥有移动设备管理。 如果你尚未&#39;设置，请遵循本指南和 [Intune 入门](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)。

> [!NOTE]
> 多个 MDM 系统支持 Windows 10 并且大部分都支持个人和公司设备部署方案。 支持 Windows 10 全息版 MDM 提供程序目前包括：AirWatch、MobileIron 和其他。 大多数行业领先的 MDM 供应商已支持与 Azure AD 集成。 可在 [Azure Marketplace](https://azure.microsoft.com/marketplace/) 中查找支持 Azure AD 的 MDM 供应商。

## Network

在此设置中，我们预计 HoloLens 2 设备会从任何可用的开放Wi-Fi Internet。 由于用户可能需要根据位置更改网络连接，因此他们应了解如何将[HoloLens](https://docs.microsoft.com/hololens/hololens-network)设备连接到 WLAN。

对于 Dynamics 365 远程协助，存在各种网络条件，包括带宽、延迟、抖动和数据包丢失，这些条件可能会影响视频呼叫体验。 尽管在带宽减少的环境中可能会进行音频和视频呼叫，但您可能会遇到功能下降的情况。 在 HoloLens 上使用 Dynamics 365 远程协助时，需要记住以下网络要求：

**最小值** ：对于分辨率为 30 fps 的 HD 1080p 的对等 HD 质量视频呼叫，需要 1.5 Mbps up/down。

**最佳：** 对于分辨率为 HD 1080p 的对等 HD 质量视频呼叫，应为 4-5 Mbps 的上/下。

详细信息：

- [网络要求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [网络优化建议](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### 可选：将 HoloLens 连接到 VPN

要连接到本指南中的设备将通过网络和外部云网络连接到网络。 访问公司资源可能需要&#39;VPN 连接设备。 有几种将设备连接到 VPN 的不同方法，其中最终用户可以使用设备 UI 进行连接，也可以管理设备并接收来自 PPKG 或 MDM 的 VPN 配置文件。 本文不会&#39;如何设置 VPN，因此如果你希望&#39;了解有关不同的 VPN 协议或管理 VPN 的方法，请访问这些指南，了解有关[HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn)和 VPN 的信息。

## 下一步

> [!div class="nextstepaction"]
> [云连接部署 - 配置](hololens2-cloud-connected-configure.md)
