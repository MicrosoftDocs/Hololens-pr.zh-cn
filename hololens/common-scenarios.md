---
title: 常见基础结构部署方案
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 6/30/2020
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
ms.openlocfilehash: f8d69fc988afabad5f4ae1cce9003381ceb8e68c
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857865"
---
# 常见基础结构部署方案
以下信息提供了在企业内部部署和管理 Microsoft HoloLens 2 设备的三种常见方案的高级体系结构概述。

## 场景

下图表示 HoloLens 2 部署的三种典型方案。 
![环境](images/scenarios.jpg)

### 方案 A

HoloLens 2 部署主要用于企业网络外部的环境。 公司资源不会被访问或通过 VPN 限制。 这是一个与公司中托管的移动设备非常类似的部署。
 * 基本常见配置
   * Wlan 网络通常完全开放于 Internet 和云服务。
   * 具有 MDM 自动注册的 Azure AD 联接--MDM （Intune）托管
   * 用户利用其自己的公司帐户（AAD）登录 
     * 每个设备支持的单个或多个用户
   * 不同级别的设备锁定配置基于特定使用情形（从完全打开到单应用展台）应用。
   * 一个或多个应用程序通过 MDM 进行部署

* 常见挑战
   * 根据方案要求确定要对 HoloLens 2 应用哪些 MDM 配置。

### 情形 B

HoloLens 2 已部署为主要在企业网络上使用，可访问内部公司资源。 互联网和云服务可能会受到限制。 这是大多数 Windows 10 电脑的典型部署。
 * 基本常见配置
   * Wi-fi 网络是一种内部公司网络，可访问内部资源，并限制 internet 或云服务访问。
   * 具有 MDM 自动注册的 Azure AD 联接 
   * MDM （Intune）托管
   * 用户利用其自己的公司帐户（AAD）登录
     * 每个设备支持的单个或多个用户
   * 不同级别的设备锁定配置基于特定使用情形（从完全打开到单应用展台）应用。
   * 一个或多个应用程序通过 MDM 进行部署

 * 常见挑战
   * HoloLens 2 不支持本地广告加入或 SCCM。 仅适用于 MDM 的 Azure AD 加入。 目前，许多公司仍在此方案中部署 Windows 10 电脑，这是因为本地广告已加入设备，由 System Center Configuration Manager （SCCM）托管，并且可能没有为通过基于云的 MDM 解决方案管理内部 Windows 10 设备而部署/配置的基础结构。
   * 由于 HoloLens 2 是云优先设备，因此它很大程度上依赖于 internet 和云连接的服务，用于用户身份验证、操作系统更新、MDM 管理等。连接到公司网络时，很可能需要对代理/防火墙规则进行调整，以便为 HoloLens 2 和在其上运行的应用程序启用访问权限。 
   * 公司 Wlan 连接通常需要证书来对网络上的设备或用户进行身份验证。 配置所需的基础结构或设置以通过 MDM 将证书部署到 Windows 10 设备的难度很大。

### 情形 C

HoloLens 2 已部署为主要在没有网络或 internet 访问的情况下脱机使用。 这是对高度安全或机密位置的典型部署。
 * 基本常见配置
   * Wi-fi 连接已禁用。 如果需要，可通过 USB 使用以太网进行局域网连接。
   * 不受管理。
   * 设备登录的本地用户帐户。
     * HoloLens 2 仅支持1个本地帐户。
   * 不同级别的设备锁定配置通过基于特定使用案例的预配包进行应用。 这些配置通常因安全环境要求而受到严格限制。
   * 通过预配包部署一个或多个应用程序

 * 常见挑战
   * 预配程序包提供了一组有限的配置
   * 云服务无法利用，因此限制了 HoloLens 2 功能。
   * 更高的管理开销，因为这些设备必须手动设置、配置和更新。
