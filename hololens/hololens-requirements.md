---
title: 常见部署方案
description: 详细了解在企业环境中部署和管理HoloLens，包括基础结构、Azure Active Directory和移动设备管理。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: ccccdcc7d3188919d02eb5855131137415c12d16
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639822"
---
# <a name="common-deployment-scenarios"></a>常见部署方案

## <a name="overview"></a>概述

本页提供在企业中部署和管理 Microsoft HoloLens 2 台设备时三种常见方案的概要体系结构概述。

通常，管理设备和访问组织资源大致取决于已有的因素。 根据现有的基础结构，我们邀请你查看以下方案中常见的设备管理样式 (MDM) ，然后阅读在商业环境中规划[HoloLens 2](hololens-core-components.md)部署，以确定哪种方案符合你的需求。 在部署期间，还有三个相应的指南可供使用。


 1. [连接到云的环境部署指南](hololens2-cloud-connected-overview.md)
     1. [连接到云的环境（外部客户端）部署指南](hololens2-deployment-guide.md)
 1. [企业网络部署指南](hololens2-corp-connected-overview.md)
 1. [脱机安全环境部署指南](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>方案 A：部署到已连接云的设备

此方案相当于在公司内部署托管移动设备。 HoloLens 2主要在企业网络外部的环境中使用。 不访问公司资源，或者可能会通过 VPN 限制公司资源。 
 * 基本常见配置
   * Wi-Fi网络通常对 Internet 和云服务完全开放。
   * Azure AD Mobile 设备管理 (MDM) 自动注册 -MDM (Intune) 托管
   * 用户使用自己的公司帐户登录 (Azure AD) 
     * 支持每个设备的一个或多个用户
   * 根据特定用例应用不同级别的设备锁定配置，从"完全打开"到"单应用展台"。
   * 通过 MDM 部署一个或多个应用程序

* 常见挑战
   * 根据方案要求确定HoloLens 2的 MDM 配置。

[![方案关系图 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

相应的云连接指南介绍如何将 HoloLens 2注册到设备管理中，根据需要应用许可证，并验证最终用户能否在设备设置Remote Assist立即使用许可证。 使用外部客户端指南将设备部署到远程站点，供短期或长期外部使用。

> [!div class="nextstepaction"]
> [连接到云的环境部署指南](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [连接到云的环境（外部客户端）部署指南](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>方案 B：在组织的网络中部署

此方案与大多数电脑的经典部署Windows 10相同。 HoloLens 2部署，主要在有权访问内部公司资源的公司网络上使用。 Internet 和云服务可能会受到限制。 

 * 基本常见配置
   * Wi-Fi网络是一个内部企业网络，可以访问内部资源，并且对 Internet 或云服务的访问有限。
   * Azure AD MDM 自动注册加入
   * MDM (Intune) 托管
   * 用户使用自己的公司帐户登录 (Azure AD) 
     * 支持每个设备的一个或多个用户
   * 根据特定用例应用不同级别的设备锁定配置，从"完全打开"到"单应用展台"。
   * 通过 MDM 部署一个或多个应用程序

 * 常见挑战
   * HoloLens 2不支持本地 AD 联接或 SCCM。 仅Azure AD MDM 联接。 目前，许多公司仍在此方案中将 Windows 10 PC 部署为本地 AD 联接设备，由 System Center Configuration Manager (SCCM) 管理，并且可能尚未部署/配置基础结构，以通过基于云的 MDM 解决方案管理内部 Windows 10 设备。
   * 由于HoloLens 2云第一设备，因此它严重依赖于 Internet 和云连接服务进行用户身份验证、OS 更新、MDM 管理等。 连接到公司网络时，很可能需要调整代理/防火墙规则，以启用对 HoloLens 2 及其运行的应用程序的访问。
   * 企业Wi-Fi连接通常需要证书来向网络验证设备或用户身份。 通过 MDM 将证书部署到 Windows 10所需的基础结构或设置可能难以配置。

[![方案 B1 示意图 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![方案 B2 示意图 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

相应的企业网络指南指导如何在设置设备后将 HoloLens 2 注册到现有设备管理中、根据需要应用许可证，并验证最终用户是否能够操作 Dynamics 365 指南以及使用自定义业务线应用。

> [!div class="nextstepaction"]
> [企业网络部署指南](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>方案 C：在安全的脱机环境中部署

这是高度安全或机密位置的典型部署。 HoloLens 2部署 ，主要以脱机方式使用，无需网络或 Internet 访问。 
 * 基本常见配置
   * Wi-Fi连接已禁用。 如有必要，可以通过 USB 为 LAN 连接启用以太网。
   * 非托管。
   * 用于设备登录的本地用户帐户。
     * HoloLens 2仅支持一个本地帐户。
   * 根据特定用例，通过预配包应用不同级别的设备锁定配置。 由于安全环境要求，这些配置通常受到限制。
   * 通过预配包部署一个或多个应用程序

 * 常见挑战
   * 可以通过预配包使用有限的一组配置
   * 云服务无法使用，因此限制了HoloLens 2功能。
   * 由于必须手动设置、配置和更新这些设备，因此管理开销较高。

[![脱机安全关系图 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

相应的脱机安全指南提供有关应用示例预配包的指导，该包将锁定HoloLens 2以在安全环境中使用。

> [!div class="nextstepaction"]
> [脱机安全环境部署指南](hololens-common-scenarios-offline-secure.md)


