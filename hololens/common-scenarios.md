---
title: 常见基础结构部署方案
description: 了解一些基于混合现实的不同基础结构部署的最常见部署方案。
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: Hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448490"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>常见基础结构部署方案概述

以下信息提供了在企业内部署和管理 Microsoft HoloLens 2 设备时三种常见方案高级体系结构概述。 通常，设备管理方式和访问组织资源方式很大程度上取决于已有因素。 基于现有基础结构，我们邀请你查看以下方案中的常见设备管理风格，并尝试我们的指南，以在满足你需求的方案中进行部署。

## <a name="scenarios"></a>方案

下图显示了 HoloLens 2 部署的三种典型方案。
![方案图](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>方案 A：部署到云连接设备

HoloLens 2 已部署，主要在企业网络外部的环境中使用。 公司资源无法访问或可能通过 VPN 受限。 此部署类似于公司内的托管移动设备。
 * 基本常见配置
   * Wi-Fi网络通常完全开放到 Internet 和云服务。
   * Azure AD Join with Mobile Device Management (MDM) Auto Enrollment --MDM (Intune) Managed
   * 用户使用自己的公司帐户在 Azure AD (登录) 
     * 支持每个设备的一个或多个用户
   * 根据特定用例（从完全打开到单个应用展台）应用不同级别的设备锁定配置。
   * 通过 MDM 部署一个或多个应用程序

* 常见挑战
   * 根据方案要求确定应用于 HoloLens 2 的 MDM 配置。

有关与方案类似的部署指南，请查看我们的云连接 [HoloLens 2 和远程协助指南](hololens2-cloud-connected-overview.md)。

> [!div class="nextstepaction"]
> [部署指南 – 云连接的 HoloLens 2 与远程协助](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>方案 B：在组织的网络内部部署

HoloLens 2 主要部署在可以访问内部公司资源的公司网络上使用。 Internet 和云服务可能会受到限制。 此部署是大多数 Windows 10 电脑的典型部署。

 * 基本常见配置
   * Wi-Fi网络是一个内部企业网络，可以访问内部资源，并且对 Internet 或云服务的访问受到限制。
   * 通过 MDM 自动注册加入 Azure AD
   * Mdm (Intune) 托管
   * 用户使用自己的公司帐户在 Azure AD (登录) 
     * 支持每个设备的一个或多个用户
   * 根据特定用例（从完全打开到单个应用展台）应用不同级别的设备锁定配置。
   * 通过 MDM 部署一个或多个应用程序

 * 常见挑战
   * HoloLens 2 不支持本地 AD 加入或 SCCM。 仅 Azure AD 与 MDM 联接。 目前，许多公司仍在此方案中将 Windows 10 电脑部署为加入本地 AD 的设备，这些设备由 System Center Configuration Manager (SCCM) 管理，并且可能未部署/配置基础结构以通过基于云的 MDM 解决方案管理内部 Windows 10 设备。
   * 由于 HoloLens 2 是云第一设备，它严重依赖 Internet 和云连接服务进行用户身份验证、操作系统更新、MDM 管理等。 连接到企业网络时，很可能需要调整代理/防火墙规则，以启用对 HoloLens 2 及其运行的应用程序的访问。
   * 企业Wi-Fi连接通常需要证书来向网络验证设备或用户。 通过 MDM 将证书部署到 Windows 10 设备所需的基础结构或设置可能难以配置。

> [!div class="nextstepaction"]
> [部署指南 - 使用 Dynamics 365 指南的企业连接的 HoloLens 2](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>方案 C：在安全的脱机环境中部署

HoloLens 2 已部署，主要在无网络或 Internet 访问的脱机状态下使用。 这是高度安全或机密位置的典型部署。
 * 基本常见配置
   * Wi-Fi连接已禁用。 如有必要，可以通过 USB 为 LAN 连接启用以太网。
   * 未托管。
   * 设备登录的本地用户帐户。
     * HoloLens 2 仅支持一个本地帐户。
   * 根据特定用例，通过预配包应用不同级别的设备锁定配置。 由于安全环境要求，这些配置通常受到限制。
   * 通过预配包部署一个或多个应用程序

 * 常见挑战
   * 通过预配包提供的配置集有限
   * 云服务无法使用，因此限制了 HoloLens 2 功能。
   * 由于必须手动设置、配置和更新这些设备，因此管理开销较高。

有关与此方案类似的部署指南，请查看我们的 [脱机安全部署指南](hololens-common-scenarios-offline-secure.md)。

> [!div class="nextstepaction"]
> [部署指南 - 脱机安全 HoloLens 2](hololens-common-scenarios-offline-secure.md)
