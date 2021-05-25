---
title: 常见基础结构部署方案
description: 了解基于混合现实的不同基础结构部署的一些最常见的部署方案。
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: hololens
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
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397410"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>常见基础结构部署方案概述

以下信息概述了在企业中部署和管理 Microsoft HoloLens 2 台设备时三种常见方案。 通常，管理设备以及如何访问组织资源主要由已有因素决定。 根据现有基础结构，我们邀请你查看以下方案中的常见设备管理样式，并尝试我们的指南，以在符合需求的方案中进行部署。

## <a name="scenarios"></a>方案

下图表示两种典型的托管方案，适用于HoloLens 2方案。
 

还有第三种方案允许脱机安全部署。

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a>方案 A：部署到已连接云的设备

HoloLens 2主要在企业网络外部的环境中使用。 不访问公司资源，或者可能会通过 VPN 限制公司资源。 此部署类似于公司内的托管移动设备。
 * 基本常见配置
   * Wi-Fi网络通常对 Internet 和云服务完全开放。
   * Azure AD Mobile 设备管理 (MDM) 自动注册 -MDM (Intune) 托管
   * 用户使用自己的公司帐户登录 (Azure AD) 
     * 支持每个设备的一个或多个用户
   * 根据特定用例应用不同级别的设备锁定配置，从"完全打开"到"单应用展台"。
   * 通过 MDM 部署一个或多个应用程序



* 常见挑战
   * 根据方案要求确定要应用于 HoloLens 2 的 MDM 配置。

[![方案 A 关系图 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

对于类似于此方案的部署指南，请查看我们的 [云连接环境部署](hololens2-cloud-connected-overview.md)指南指南。

> [!div class="nextstepaction"]
> [云连接环境部署指南](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [云连接环境 (外部客户端) 部署指南](hololens2-deployment-guide.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a>方案 B：在组织的网络中部署

HoloLens 2 部署用于主要在公司网络上使用，可以访问内部公司资源。 Internet 和云服务可能受到限制。 此部署是大多数 Windows 10 电脑的典型部署。

 * 基本常见配置
   * Wi-Fi 网络是一种内部公司网络，有权访问内部资源，并限制了对 internet 或云服务的访问。
   * 与 MDM 自动注册 Azure AD 联接
   * MDM (Intune) 托管
   * 用户用自己的公司帐户登录 (Azure AD) 
     * 每个设备支持一个或多个用户
   * 根据特定用例（从完全打开到单应用展台）应用不同级别的设备锁定配置。
   * 通过 MDM 部署一个或多个应用程序

 * 常见挑战
   * HoloLens 2 不支持本地 AD 联接或 SCCM。 仅Azure AD MDM 联接。 目前，许多公司仍在此方案中将 Windows 10 电脑部署为本地 AD 联接设备，由 System Center 配置服务器 (SCCM) 管理，并且可能尚未部署/配置基础结构，以通过基于云的 MDM 解决方案管理内部 Windows 10 设备。
   * 由于HoloLens 2云第一设备，因此它严重依赖于 Internet 和云连接服务进行用户身份验证、OS 更新、MDM 管理等。 连接到公司网络时，很可能需要调整代理/防火墙规则，以启用对 HoloLens 2 及其运行的应用程序的访问。
   * 企业Wi-Fi连接通常需要证书来向网络验证设备或用户身份。 通过 MDM 将证书部署到 Windows 10所需的基础结构或设置可能难以配置。

[![方案 B1 示意图 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![方案 B2 示意图 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

有关与此方案类似的部署指南，请查看企业 [网络部署指南](hololens2-corp-connected-overview.md)。

> [!div class="nextstepaction"]
> [企业网络部署指南](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>方案 C：在安全的脱机环境中部署

HoloLens 2部署 ，主要以脱机方式使用，无需网络或 Internet 访问。 这是高度安全或机密位置的典型部署。
 * 基本常见配置
   * Wi-Fi连接已禁用。 如有必要，可以通过 USB 为 LAN 连接启用以太网。
   * 非托管。
   * 用于设备登录的本地用户帐户。
     * HoloLens 2仅支持一个本地帐户。
   * 根据特定用例，通过预配包应用不同级别的设备锁定配置。 由于安全环境要求，这些配置通常会受到限制。
   * 通过预配包部署一个或多个应用程序

 * 常见挑战
   * 通过预配包提供一组有限的配置
   * 无法使用云服务，因此限制了 HoloLens 2 功能。
   * 更高的管理开销，因为这些设备必须手动设置、配置和更新。

[![脱机安全图 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

对于类似于此方案的部署指南，请查看我们的 [脱机安全环境部署指南](hololens-common-scenarios-offline-secure.md)。

> [!div class="nextstepaction"]
> [脱机安全环境部署指南](hololens-common-scenarios-offline-secure.md)
