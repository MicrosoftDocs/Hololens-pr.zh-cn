---
title: 在商业环境中规划 HoloLens 2 部署
description: 详细了解如何在企业环境中部署和管理 HoloLens，包括基础结构、Azure Active Directory 和移动设备管理。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 2a0933bb754043934621a22ffa7764c9c88d93da
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924598"
---
# <a name="common-deployment-scenarios"></a>常见部署方案

## <a name="overview"></a>概述

本页提供了在企业内部部署和管理 Microsoft HoloLens 2 设备时三个常见方案的高级体系结构概述。

通常，管理设备和访问组织资源的方式很大程度上取决于已有的因素。 根据你的现有基础结构，我们邀请你在以下情况下查看常见的设备管理样式 (MDM) ，然后 [在商业环境中阅读规划 HoloLens 2 部署](hololens-core-components.md) ，以确定哪种方案符合你的需求。 在部署过程中，还可以使用三个对应的指南。


 1. [连接到云的环境部署指南](hololens2-cloud-connected-overview.md)
     1. [连接到云的环境（外部客户端）部署指南](hololens2-deployment-guide.md)
 1. [企业网络部署指南](hololens2-corp-connected-overview.md)
 1. [脱机安全环境部署指南](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>方案 A：部署到连接到云的设备

此方案相当于在公司中部署托管移动设备。 HoloLens 2 部署为主要用于公司网络外部的环境。 不会访问公司资源，也不能通过 VPN 进行限制。 
 * 基本常见配置
   * Wi-Fi 网络通常会完全公开到 Internet 和云服务。
   * Azure AD 加入移动设备管理 (MDM) 自动注册--MDM (Intune) 托管
   * 用户用自己的公司帐户登录 (Azure AD) 
     * 每个设备支持一个或多个用户
   * 根据特定用例（从完全打开到单应用展台）应用不同级别的设备锁定配置。
   * 通过 MDM 部署一个或多个应用程序

* 常见挑战
   * 根据方案要求确定要应用于 HoloLens 2 的 MDM 配置。

[![方案 A 关系图 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

对应的云连接指南介绍了如何将 HoloLens 2 注册到设备管理，根据需要应用许可证，并验证最终用户是否能够在设备设置时立即使用远程协助。 使用外部客户端指南将设备部署到远程站点，以便短期或长期外部使用。

> [!div class="nextstepaction"]
> [连接到云的环境部署指南](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [连接到云的环境（外部客户端）部署指南](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>方案 B：在组织的网络中部署

此方案与大多数 Windows 10 电脑的经典部署相同。 HoloLens 2 部署用于主要在公司网络上使用，可以访问内部公司资源。 Internet 和云服务可能受到限制。 

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

[![方案 B1 关系图 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![方案 B2 关系图 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

相应的企业网络指南将指导你如何将 HoloLens 2 注册到你的现有设备管理中，根据需要应用许可证，并验证你的最终用户是否能够操作 Dynamics 365 指南，以及如何在设备设置后使用自定义业务线应用。

> [!div class="nextstepaction"]
> [企业网络部署指南](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>方案 C：在安全脱机环境中部署

这是高度安全或机密位置的典型部署。 HoloLens 2 的部署目的是在没有网络或 internet 访问的情况下使用。 
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

[![脱机安全图 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

对应的脱机安全指南提供了有关应用示例设置包的说明，该设置包将锁定 HoloLens 2 以便在安全环境中使用。

> [!div class="nextstepaction"]
> [脱机安全环境部署指南](hololens-common-scenarios-offline-secure.md)


