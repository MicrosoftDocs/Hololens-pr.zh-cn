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
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308418"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a>常见基础结构部署方案概述

以下信息提供了在企业中部署和管理 Microsoft HoloLens 2 设备时三个常见方案的高级体系结构概述。 通常，如何管理设备以及如何访问组织的资源，主要取决于已有的因素。 根据现有的基础结构，我们建议你在以下情况下查看常见的设备管理样式，并试用用于在满足你的需求的方案中部署的指南。

## <a name="scenarios"></a>方案

下图表示 HoloLens 2 部署的三个典型方案。
![方案图](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a>方案 A：部署到云连接设备

HoloLens 2 部署为主要用于公司网络外部的环境。 不会访问公司资源，也不能通过 VPN 进行限制。 此部署类似于公司内托管的移动设备。
 * 基本常见配置
   * Wi-Fi 网络通常会完全公开到 Internet 和云服务。
   * Azure AD 加入移动设备管理 (MDM) 自动注册--MDM (Intune) 托管
   * 用户用自己的公司帐户登录 (Azure AD) 
     * 每个设备支持一个或多个用户
   * 根据特定用例（从完全打开到单应用展台）应用不同级别的设备锁定配置。
   * 通过 MDM 部署一个或多个应用程序

* 常见挑战
   * 根据方案要求确定要应用于 HoloLens 2 的 MDM 配置。

对于类似于方案 A 的部署指南，请查看我们的 [云与远程协助连接](hololens2-cloud-connected-overview.md)的适用于 Cloud 2 的建议指南。

> [!div class="nextstepaction"]
> [部署指南–云连接的 HoloLens 2 （含远程协助）](hololens2-cloud-connected-overview.md)

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
   * HoloLens 2 不支持本地 AD 联接或 SCCM。 仅 Azure AD 加入 MDM。 如今，许多公司在这种情况下仍会将 Windows 10 电脑部署为本地 AD 加入设备，由 System Center Configuration Manager (SCCM) 管理，并且可能没有部署/配置基础结构来通过基于云的 MDM 解决方案来管理内部 Windows 10 设备。
   * 因为 HoloLens 2 是云优先设备，所以它很大程度上依赖于连接 internet 和云连接的服务进行用户身份验证、操作系统更新、MDM 管理等。 在连接到公司网络时，可能需要对代理/防火墙规则进行调整，以便为 HoloLens 2 和在其上运行的应用程序启用访问权限。
   * 企业 Wi-Fi 连接通常需要证书以向网络验证设备或用户。 配置所需的基础结构或设置，以通过 MDM 将证书部署到 Windows 10 设备。

> [!div class="nextstepaction"]
> [部署指南–公司连接的 HoloLens 2，含 Dynamics 365 指南](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a>方案 C：在安全脱机环境中部署

HoloLens 2 的部署目的是在没有网络或 internet 访问的情况下使用。 这是高度安全或机密位置的典型部署。
 * 基本常见配置
   * Wi-Fi 连接处于禁用状态。 如果需要，可以为 LAN 连接启用通过 USB 的以太网。
   * 非托管。
   * 设备登录的本地用户帐户。
     * HoloLens 2 仅支持一个本地帐户。
   * 通过基于特定用例的预配包应用不同级别的设备锁定配置。 由于安全环境要求，这些配置通常会受到限制。
   * 通过预配包部署一个或多个应用程序

 * 常见挑战
   * 通过预配包提供一组有限的配置
   * 无法使用云服务，因此限制了 HoloLens 2 功能。
   * 更高的管理开销，因为这些设备必须手动设置、配置和更新。

对于类似于此方案的部署指南，请查看我们的 [脱机安全部署指南](hololens-common-scenarios-offline-secure.md)。

> [!div class="nextstepaction"]
> [部署指南–脱机安全 HoloLens 2](hololens-common-scenarios-offline-secure.md)
