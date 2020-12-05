---
title: 常见基础结构部署方案
description: 某些基于不同通用基础结构的常见部署方案
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
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
ms.openlocfilehash: e9e91535bb49b5076547e8b9934bdc86808d41fc
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195565"
---
# 常见基础结构部署方案概述

以下信息提供了在企业内部部署和管理 Microsoft HoloLens 2 设备的三种常见方案的高级体系结构概述。 通常情况下，你管理设备的方式以及如何访问组织的资源在很大程度上取决于已存在的因素。 根据现有的基础结构，我们邀请你查看以下方案中的常见设备管理样式，并尝试在符合你的需求的方案中部署指南。

## 方案

下图表示 HoloLens 2 部署的三种典型方案。
![方案图表](images/scenarios.jpg)

### 方案 A：部署到云连接设备

HoloLens 2 部署主要用于企业网络外部的环境。 公司资源不会被访问或通过 VPN 限制。 这是一个与公司中托管的移动设备非常类似的部署。
 * 基本常见配置
   * Wi-Fi 网络通常完全开放于 Internet 和云服务。
   * 具有 MDM 自动注册的 Azure AD 联接-MDM (Intune) 托管
   * 用户利用其自己的公司帐户登录 (AAD) 
     * 每个设备支持的单个或多个用户
   * 不同级别的设备锁定配置基于特定使用情形（从完全打开到单应用展台）应用。
   * 一个或多个应用程序通过 MDM 进行部署

* 常见挑战
   * 根据方案要求确定要对 HoloLens 2 应用哪些 MDM 配置。

有关类似于本方案的部署指南，请参阅我们 [与远程协助配合使用的云与 "远程协助" 联系](hololens2-cloud-connected-overview.md)的指南。

> [!div class="nextstepaction"]
> [部署指南-云连接了 HoloLens 2 和远程协助](hololens2-cloud-connected-overview.md)

### 情形 B：在您的组织的网络内部署

HoloLens 2 已部署为主要在企业网络上使用，可访问内部公司资源。 互联网和云服务可能会受到限制。 这是大多数 Windows 10 电脑的典型部署。
 * 基本常见配置
   * Wi-Fi 网络是一种内部公司网络，具有对内部资源的访问权限，并且对 internet 或云服务的访问受限。
   * 具有 MDM 自动注册的 Azure AD 联接
   * MDM (Intune) 托管
   * 用户利用其自己的公司帐户登录 (AAD) 
     * 每个设备支持的单个或多个用户
   * 不同级别的设备锁定配置基于特定使用情形（从完全打开到单应用展台）应用。
   * 一个或多个应用程序通过 MDM 进行部署

 * 常见挑战
   * HoloLens 2 不支持本地广告加入或 SCCM。 仅适用于 MDM 的 Azure AD 加入。 目前，许多公司仍在此方案中部署 Windows 10 电脑，因为在本地加入广告的设备（由 System Center Configuration Manager (SCCM) 托管），并且可能没有部署/配置的基础结构，以便通过基于云的 MDM 解决方案管理内部 Windows 10 设备。
   * 由于 HoloLens 2 是云优先设备，因此它很大程度上依赖于 internet 和云连接的服务，用于用户身份验证、操作系统更新、MDM 管理等。连接到公司网络时，很可能需要对代理/防火墙规则进行调整，以便为 HoloLens 2 和在其上运行的应用程序启用访问权限。
   * 企业 Wi-Fi 连接通常需要证书来对网络上的设备或用户进行身份验证。 配置所需的基础结构或设置以通过 MDM 将证书部署到 Windows 10 设备的难度很大。

### 方案 C：在安全的脱机环境中部署

HoloLens 2 已部署为主要在没有网络或 internet 访问的情况下脱机使用。 这是对高度安全或机密位置的典型部署。
 * 基本常见配置
   * Wi-Fi 连接已被禁用。 如果需要，可通过 USB 使用以太网进行局域网连接。
   * 不受管理。
   * 设备登录的本地用户帐户。
     * HoloLens 2 仅支持1个本地帐户。
   * 不同级别的设备锁定配置通过基于特定使用案例的预配包进行应用。 这些配置通常因安全环境要求而受到严格限制。
   * 通过预配包部署一个或多个应用程序

 * 常见挑战
   * 预配程序包提供了一组有限的配置
   * 云服务无法利用，因此限制了 HoloLens 2 功能。
   * 更高的管理开销，因为这些设备必须手动设置、配置和更新。

有关类似于此方案的部署指南，请参阅我们的 [脱机安全部署指南](hololens-common-scenarios-offline-secure.md)。

> [!div class="nextstepaction"]
> [部署指南–脱机安全的 HoloLens 2](hololens-common-scenarios-offline-secure.md)
