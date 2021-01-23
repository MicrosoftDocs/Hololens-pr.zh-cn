---
title: 配置 CSP 和设备管理概述
description: 了解如何使用移动设备管理和预配包配置 CSP、策略和设备管理。
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
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283243"
---
# 配置 CSP 和设备管理概述

IT 管理员可以在 HoloLens 2 上定义和实施策略设置。 你使用的配置设置将基于部署方案而异，公司设备将为 IT 提供最广泛的控制权。 在 Windows 10 中，配置服务提供程序 (CSP) 是一个在设备上读取、设置、修改或删除配置设置的接口。 这些设置将映射到注册表项或文件。 一些配置服务提供程序支持 WAP 格式，一些支持 SyncML，一些支持两者。

有关 Windows 10 全息设备管理 CSP 详细信息，请参阅 [HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)设备中支持的 AP 的完整列表。
IT 管理员还可以在设备上管理策略 CSP，查看 [HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)支持的策略 CSP 的完整列表。

## 配置方法

### 使用 MDM 配置

可以在 MDM 系统中注册的任何个人或公司设备上轻松管理 CSP 和策略。 在 MDM 解决方案中注册设备后，你将能够使用设备配置管理该设备或一组设备。 详细了解如何通过 MDM 管理 [HoloLens 设备](hololens-mdm-configure.md)。

### 使用预配包进行配置

HoloLens 2 还支持通过自定义预配包为 HoloLens 2 设备设置一组有限的云解决方案提供商配置。 预配包通常用于非 MDM 托管设备，并且需要手动应用到每台设备。 阅读有关为 [HoloLens 生成自定义预配包的信息](https://docs.microsoft.com/hololens/hololens-provisioning)。

## 配置

### 常见设备限制

某些设备限制非常简单，并且禁用了功能或设备连接。 若要了解有关这些限制的信息，请阅读有关 [常见设备限制的更多内容。](hololens-common-device-restrictions.md)

### 展台模式

使用展台模式控制默认情况下哪些标识有权访问哪些应用。 展台可用于单个应用或多个应用 UI 体验。 展台配置包括从单个应用（适用于使用该设备的任何人）到不同组的不同应用选择。 展台模式不会阻止"允许的应用"启动其他应用，并且永远不会这样。 通过阅读 [有关展台模式以及如何使用它们来了解更多信息](hololens-kiosk.md)。

### 设置页面可见性

使用"设置"应用策略控制默认情况下哪些标识有权访问设置。 使用此策略，可以将"设置"应用配置为只显示选择页面，或隐藏所有选定的页面。 [了解如何配置可用的页面](settings-uri-list.md)。

此功能当前仅适用于 Windows 预览 [体验成员版本](hololens-insider.md)。 确保打算使用此功能的设备在内部版本 19041.1349+ 上。

### WDAC

使用 WDAC 配置来控制允许/禁止启动的应用/进程，而不考虑系统是否位于展台模式下。
[请参阅 WDAC 概述。](windows-defender-application-control-wdac.md)
