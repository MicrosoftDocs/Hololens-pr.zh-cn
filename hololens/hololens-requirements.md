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
ms.openlocfilehash: 5a4f251f3ca6eae5e85e4d763074e035039159cb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032149"
---
# <a name="common-deployment-scenarios"></a>常见部署方案

## <a name="overview"></a>概述

第一次尝试时，如何部署新设备可能很难。 在这里，我们分享了部署和管理Microsoft HoloLens 2 台设备的不同方式。

需要解决方案 - 大规模部署。 我们希望你到达此地。 让我们首先讨论部署设备（因此使用全息影像）以实现目标混合现实方案价值的步骤，无论是使用 D365 Remote Assist、Guides 还是创建的已启用 Azure 混合现实服务的应用程序。

你可能是业务决策者、IT 专业人员或创新团队，想要在HoloLens采用解决方案。 从概念证明到缩放部署进行构建时，我们的部署指南HoloLens IT 基础结构内部部署， 无论大小如何。 以下部署方案是最常见的：

| 方案 |使用情况 | 要点 |
|---------|---------|---------|
| [方案 A：云连接的设备](hololens2-cloud-connected-overview.md) | 首次开始部署时，你可以从小型开始，并部署连接到云的单个设备，只是为了查看基本过程。 | 设备将连接到云服务和公共 Internet。 这最适合客户用例、现场服务和概念证明。|
| [方案 B：组织的网络](hololens2-corp-connected-overview.md) | 大规模部署到生产环境时，可能需要与自己的组织网络集成。 | 设备将连接到"公司"wi-fi 网络。 这最适合内部用户，或在企业环境中使用。|
| [方案 C：脱机安全环境](hololens-common-scenarios-offline-secure.md) | 某些任务关键型流程或某些公司策略可能要求使用脱机环境。 | 设备将连接到严格限制的网络，或者将完全脱机设备。 这最适用于高度安全的环境或远程区域中的 Internet 连接限制。 |

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a>方案 A：部署到已连接云的设备

此方案相当于在公司内部署托管移动设备。 HoloLens 2部署 ，主要在企业网络外部的环境中使用。 不访问公司资源，或者可能会通过 VPN 限制公司资源。

[![方案关系图。](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)

### <a name="when-to-use"></a>何时使用

请考虑以下部署模型：

* 部署概念证明、试点和现场服务
* 部署 [Remote Assist](hololens2-options-remote-assist.md)

### <a name="basic-common-configurations"></a>基本常见配置

* Wi-Fi网络通常对 Internet 和云服务完全开放
* Azure AD Mobile 设备管理 (MDM) 自动注册 -MDM (Intune) 托管
* 用户使用自己的公司帐户登录 (Azure AD) 
  * 支持每个设备的一个或多个用户
* 根据特定用例应用不同级别的设备锁定配置，从"完全打开"到"单应用展台"。
* 通过 MDM 部署一个或多个应用程序

### <a name="common-challenges"></a>常见挑战

* 根据方案要求确定HoloLens 2哪些 MDM 配置

相应的云连接指南介绍如何将 HoloLens 2注册到设备管理中，根据需要应用许可证，并验证最终用户能否在设备设置Remote Assist立即使用云连接。

> [!div class="nextstepaction"]
> [云连接部署指南](hololens2-cloud-connected-overview.md)

使用外部客户端指南将设备部署到远程站点，供短期或长期外部使用。

> [!div class="nextstepaction"]
> [云连接 (外部客户端) 部署指南](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a>方案 B：在组织的网络中部署

此方案与大多数电脑的经典部署Windows 10相同。 HoloLens 2部署 ，主要在有权访问内部公司资源的公司网络上使用。 Internet 和云服务可能会受到限制。 

[![方案 B1 示意图。](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)

[![方案 B2 示意图。](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)

### <a name="when-to-use"></a>何时使用

请考虑以下部署模型：

* 内部用户
* 在企业环境中 (试点) 大规模部署

### <a name="basic-common-configurations"></a>基本常见配置

* Wi-Fi网络是内部企业网络，可以访问内部资源，对 Internet 或云服务的访问有限。
* Azure AD MDM 自动注册加入
* MDM (Intune) 托管
* 用户使用自己的公司帐户登录 (Azure AD) 
  * 支持每个设备的一个或多个用户
* 根据特定用例应用不同级别的设备锁定配置，从"完全打开"到"单应用展台"。
* 通过 MDM 部署一个或多个应用程序

### <a name="common-challenges"></a>常见挑战

* HoloLens 2不支持本地 AD 联接或 SYSTEM CENTER CONFIGURATION MANAGER (SCCM) 。 仅Azure AD MDM 联接。 如今，许多公司仍在此方案中将 Windows 10 台 PC 部署为本地 AD 联接设备，由 SCCM 管理，并且可能未部署/配置基础结构以通过基于云的 MDM 解决方案管理内部 Windows 10 设备。
* 由于HoloLens 2云第一设备，因此它严重依赖于 Internet 和云连接服务进行用户身份验证、OS 更新、MDM 管理等。 连接到公司网络时，很可能需要调整代理/防火墙规则，以启用对 HoloLens 2 及其运行的应用程序的访问。
* 企业Wi-Fi连接通常需要证书来向网络验证设备或用户身份。 通过 MDM 将证书部署到 Windows 10所需的基础结构或设置可能难以配置。

相应的企业连接指南指导如何在设置设备后将 HoloLens 2 注册到现有设备管理、根据需要应用许可证，并验证最终用户是否能够操作 Dynamics 365 指南以及使用自定义业务线应用。

> [!div class="nextstepaction"]
> [企业连接部署指南](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a>方案 C：在安全的脱机环境中部署

这是高度安全或机密位置的典型部署。 HoloLens 2部署 ，主要以脱机方式使用，无需网络或 Internet 访问。

[![脱机安全关系图 1。](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)

### <a name="when-to-use"></a>何时使用

请考虑以下部署模型：

* 需要将数据保留在内部的高度安全的环境
* "体验"，其中公众将使用设备
* 远程区域中的 Internet 连接问题

### <a name="basic-common-configurations"></a>基本常见配置

* Wi-Fi连接已禁用。 如有必要，可以通过 USB 为 LAN 连接启用以太网
* 非托管
* 用于设备登录的本地用户帐户
  * HoloLens 2仅支持一个本地帐户
* 根据特定用例，通过预配包应用不同级别的设备锁定配置。 由于安全环境要求，这些配置通常受到限制
* 通过预配包部署一个或多个应用程序

### <a name="common-challenges"></a>常见挑战

* 可以通过预配包使用有限的一组配置
* 云服务无法使用，因此限制了HoloLens 2功能。
* 由于必须手动设置、配置和更新这些设备，因此管理开销较高。

相应的脱机安全指南提供有关应用示例预配包的指导，该包将锁定HoloLens 2以在安全环境中使用。

> [!div class="nextstepaction"]
> [脱机安全环境部署指南](hololens-common-scenarios-offline-secure.md)
