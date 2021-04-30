---
title: 配置 Csp 和设备管理概述
description: 了解如何使用移动设备管理和预配包配置 Csp、策略和设备管理。
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308470"
---
# <a name="configure-csps-and-device-management-overview"></a>配置 Csp 和设备管理概述

IT 管理员可以在 HoloLens 2 上定义和实施策略设置。 你使用的配置设置将基于部署方案而异，公司设备将为 IT 提供最广泛的控制权。 在 Windows 10 中，配置服务提供程序 (CSP) s 是用于读取、设置、修改或删除设备上的配置设置的接口。 这些设置将映射到注册表项或文件。 某些配置服务提供程序支持 WAP 格式，某些支持 SyncML，一些支持 SyncML。

有关 Windows 10 全息版设备管理 Csp 的详细信息，请参阅 [HoloLens 设备中支持的 csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)的完整列表。
IT 管理员还可以在设备上管理策略 CSP，请参阅 [HoloLens 2 支持的策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)的完整列表。

## <a name="configuration-methods"></a>配置方法

### <a name="configure-with-mdm"></a>配置 MDM

在 MDM 系统中注册的任何个人或公司设备上都可以轻松管理 Csp 和策略。 在 MDM 解决方案中注册设备后，你将能够使用设备配置来管理该设备或设备集。 了解有关如何 [通过 MDM 管理 HoloLens 设备](hololens-mdm-configure.md)的详细信息。

### <a name="configure-with-provisioning-packages"></a>配置预配包

HoloLens 2 还支持通过自定义预配包为 HoloLens 2 设备设置有限的 CSP 配置集。 预配包通常用于非 MDM 托管设备，需要手动应用于每个设备。 阅读有关为 HoloLens 构建自定义 [设置包](https://docs.microsoft.com/hololens/hololens-provisioning)的信息。

## <a name="configurations"></a>配置

### <a name="common-device-restrictions"></a>常见设备限制

某些设备限制非常简单，禁用了设备或与设备的连接。 若要了解相关信息，请阅读有关[常见设备限制的](hololens-common-device-restrictions.md)详细信息。

### <a name="kiosk-modes"></a>展台模式

使用展台模式来控制默认情况下哪些标识有权访问哪些应用。 网亭可用于单个应用程序或多个应用程序 UI 体验。 展台配置范围是从使用设备的任何人的单个应用到不同组的不同应用选择。 展台模式不会阻止 "允许的应用" 启动其他应用程序，并且不会出现这种情况。 [阅读有关展台模式以及如何使用它们](hololens-kiosk.md)的详细信息。

### <a name="settings-page-visibility"></a>设置页面可见性

使用 "设置" 应用策略来控制默认情况下哪些标识有权访问设置。 使用此策略时，可以将设置应用配置为仅显示选定页面，或隐藏所有选定页面。 [阅读有关如何配置可用页面的信息](settings-uri-list.md)。

此功能目前仅适用于 [Windows 有问必答版本](hololens-insider.md)。 确保要为其使用此功能的设备在 build 19041.1349 + 上。

### <a name="wdac"></a>WDAC

使用 WDAC 配置来控制允许或禁止启动哪些应用/进程，而不管系统是否处于展台模式。
[请参阅有关 WDAC 的概述。](windows-defender-application-control-wdac.md)
