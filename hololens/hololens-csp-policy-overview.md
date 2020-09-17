---
title: 配置 Csp 和设备管理概述
description: 如何配置 Csp、策略和设备管理。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4c31f7f92116031535a2dc2860e3f048a2311a39
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016764"
---
# 配置 Csp 和设备管理概述

IT 管理员可以在 HoloLens 2 上定义和实施策略设置。 你使用的配置设置将基于部署方案而异，公司设备将为 IT 提供最广泛的控制权。 在 Windows 10 中，配置服务提供程序 (CSP) s 是用于读取、设置、修改或删除设备上的配置设置的接口。 这些设置将映射到注册表项或文件。 某些配置服务提供程序支持 WAP 格式、某些支持 SyncML 以及某些支持。 

有关 Windows 10 全息版设备管理 Csp 的详细信息，请参阅 [HoloLens 设备中受支持的 csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)的完整列表。 IT 管理员还可以在设备上管理策略 CSP，请参阅 [HoloLens 2 支持的策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)的完整列表。

## 配置方法

### 配置 MDM
可在 MDM 系统中注册的任何个人设备或公司设备上轻松管理 Csp 和策略。 在你的 MDM 解决方案中注册设备后，你将能够使用设备配置管理该设备或设备集。 了解有关如何 [通过 MDM 管理 HoloLens 设备](hololens-mdm-configure.md)的详细信息。

### 通过预配程序包进行配置
HoloLens 2 还支持通过自定义预配程序包为 HoloLens 2 设备设置有限的 CSP 配置集。 预配程序包通常可用于非 MDM 托管设备，并且需要手动应用到每个设备。 阅读有关生成 [适用于 HoloLens 的自定义预配包的](https://docs.microsoft.com/hololens/hololens-provisioning)信息。 

## 配置 

### 常见设备限制
某些设备限制既简单又可禁用设备的功能或连接。 若要了解这些信息，请阅读有关[常见设备限制的](hololens-common-device-restrictions.md)详细信息。

### 展台模式
使用展台模式控制哪些身份对默认情况有权访问哪些应用。 展台可用于单个应用或多个应用 UI 体验。 展台配置范围从单个应用到使用该设备的任何人，到不同组的不同选择应用。 这不会阻止 "允许的应用" 启动其他应用，也不是有意的。 了解 [有关展台模式以及如何使用它们](hololens-kiosk.md)的详细信息。

### 设置页面可见性
在默认情况下，使用 "设置" 应用策略控制哪些标识有权访问设置。 通过此策略，可将 "设置" 应用配置为仅显示选择页面，或 "隐藏所有选定页面"。 了解[如何配置可用的页面](settings-uri-list.md)。

此功能目前仅在 [Windows 预览体验计划内部版本](hololens-insider.md)中 avalible。 请确保要使用此 for 的设备位于 build 19041.1349 +。

### WDAC
使用 WDAC 配置来控制允许/禁止启动哪些应用/进程，无论系统是否处于展台模式。
[请参阅我们对 WDAC 的概述。](windows-defender-application-control-wdac.md)
