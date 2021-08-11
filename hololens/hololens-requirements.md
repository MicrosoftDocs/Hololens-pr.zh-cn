---
title: 常见部署方案
description: 了解有关在企业环境中部署和管理 HoloLens 的详细信息，包括基础结构、Azure Active Directory 和移动设备管理。
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
ms.openlocfilehash: 27fd7f81d2868134344c7563ebc0a93133a18c0a217d6eff820b5f322e9271a7
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662909"
---
# <a name="common-deployment-scenarios"></a>常见部署方案

## <a name="overview"></a>概述

第一次尝试部署新设备时，想要了解如何部署新设备可能会很困难。 在这里，我们共享了不同的方式来部署和管理组织内 Microsoft HoloLens 2 设备。

需要解决方案部署规模。 我们想要就此获得帮助。 接下来，我们将讨论部署设备的步骤，从而实现目标混合现实方案的价值，无论你使用的是 D365 远程协助、指南还是 Azure 混合现实启用服务的应用程序。

你可能是企业决策人、IT 专业人员或想要在组织中采用 HoloLens 的创新团队。 当你从概念证明构建到缩放的部署时，我们的部署指南可以在 IT 基础结构中 HoloLens，无论规模大小如何，都是如此。 下面是最常见的部署方案：

| 方案 |使用情况 | 要点 |
|---------|---------|---------|
| [方案 A：云连接设备](hololens2-cloud-connected-overview.md) | 首次开始部署时，你可能会启动小型并部署一个连接到云的单一设备，只需查看基本过程。 | 设备将连接到云服务和公共 internet。 这最适用于客户用例、现场服务和概念证明。|
| [方案 B：组织的网络](hololens2-corp-connected-overview.md) | 大规模部署到生产环境时，可能需要将与自己组织的网络集成。 | 设备将连接到 "公司" wi-fi 网络。 这最适用于内部用户或在企业环境中使用。|
| [方案 C：脱机安全环境](hololens-common-scenarios-offline-secure.md) | 某些任务关键型过程或某些企业政策可能要求使用脱机环境。 | 设备将连接到高度限制的网络，或纯脱机设备。 这最适用于高度安全的环境或远程区域中的 internet 连接限制。 |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>方案 A：部署到连接到云的设备

此方案相当于在公司中部署托管移动设备。 部署 HoloLens 2 主要用于公司网络外部的环境中。 不会访问公司资源，也不能通过 VPN 进行限制。

[![方案 A 关系图](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>何时使用

请考虑此部署模型：

* 部署概念证明、试验和现场服务
* 部署 [远程协助](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>基本常见配置

* Wi-Fi 网络通常会完全开放到 internet 和云服务
* Azure AD 加入移动设备管理 (MDM) 自动注册--MDM (Intune) 托管
* 用户用自己的公司帐户登录 (Azure AD) 
  * 每个设备支持一个或多个用户
* 根据特定用例（从完全打开到单应用展台）应用不同级别的设备锁定配置。
* 通过 MDM 部署一个或多个应用程序

### <a name="common-challenges"></a>常见挑战

* 根据方案要求确定要应用于 HoloLens 2 的 MDM 配置

对应的云连接指南介绍了如何将 HoloLens 2 注册到设备管理，根据需要应用许可证，并验证最终用户是否能够在设备设置时立即使用远程协助。

> [!div class="nextstepaction"]
> [云连接部署指南](hololens2-cloud-connected-overview.md)

使用外部客户端指南将设备部署到远程站点，以便短期或长期外部使用。

> [!div class="nextstepaction"]
> [云连接 (外部客户端) 部署指南](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>方案 B：在组织的网络中部署

此方案与大多数 Windows 10 pc 的经典部署相同。 部署 HoloLens 2，主要用于在公司网络上访问内部公司资源。 Internet 和云服务可能受到限制。 

[![方案 B1 关系图](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![方案 B2 关系图](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>何时使用

请考虑此部署模型：

* 内部用户
* 在企业环境中大规模部署 (试点和生产) 

### <a name="basic-common-configurations"></a>基本常见配置

* Wi-Fi 网络是一种内部公司网络，有权访问内部资源，并限制了对 internet 或云服务的访问。
* 与 MDM 自动注册 Azure AD 联接
* MDM (Intune) 托管
* 用户用自己的公司帐户登录 (Azure AD) 
  * 每个设备支持一个或多个用户
* 根据特定用例（从完全打开到单应用展台）应用不同级别的设备锁定配置。
* 通过 MDM 部署一个或多个应用程序

### <a name="common-challenges"></a>常见挑战

* HoloLens 2 不支持本地 AD 联接或 System Center Configuration Manager (SCCM) 。 仅 Azure AD 加入 MDM。 如今，许多公司在这种情况下仍会将 Windows 10 电脑部署在此方案中，就像在本地加入 AD 的设备一样，由 SCCM 管理，并且可能没有部署/配置基础结构来通过基于云的 MDM 解决方案来管理内部 Windows 10 设备。
* 由于 HoloLens 2 是云优先设备，因此它很大程度上依赖于连接 internet 和云连接的服务进行用户身份验证、操作系统更新、MDM 管理等。 在连接到公司网络时，可能需要对代理/防火墙规则进行调整，使其能够访问 HoloLens 2 以及在其上运行的应用程序。
* 企业 Wi-Fi 连接通常需要证书以向网络验证设备或用户。 配置所需的基础结构或设置以将证书部署到通过 MDM Windows 10 设备可能会很困难。

相应的公司连接指南指示如何向现有设备管理注册 HoloLens 2，根据需要应用许可证，并验证最终用户是否能够操作 Dynamics 365 指南，以及如何在设备设置后使用自定义业务线应用。

> [!div class="nextstepaction"]
> [企业连接部署指南](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>方案 C：在安全脱机环境中部署

这是高度安全或机密位置的典型部署。 部署 HoloLens 2 的目的是在不使用网络或访问 internet 的情况下使用。

[![脱机安全图1](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>何时使用

请考虑此部署模型：

* 需要在内部保留数据的高度安全的环境
* "体验" 公共将使用设备的位置
* 远程区域中的 Internet 连接问题

### <a name="basic-common-configurations"></a>基本常见配置

* Wi-Fi 连接处于禁用状态。 如果需要，可以为 LAN 连接启用通过 USB 的以太网
* 未托管
* 设备登录的本地用户帐户
  * HoloLens 2 仅支持一个本地帐户
* 通过基于特定用例的预配包应用不同级别的设备锁定配置。 由于安全环境要求，通常会限制这些配置
* 通过预配包部署一个或多个应用程序

### <a name="common-challenges"></a>常见挑战

* 通过预配包提供一组有限的配置
* 无法使用云服务，因此限制了 HoloLens 2 功能。
* 更高的管理开销，因为这些设备必须手动设置、配置和更新。

对应的脱机安全指南提供了应用示例设置包的说明，该示例将锁定 HoloLens 2 以便在安全环境中使用。

> [!div class="nextstepaction"]
> [脱机安全环境部署指南](hololens-common-scenarios-offline-secure.md)
