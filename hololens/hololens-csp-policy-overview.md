---
title: 配置 CSP 和设备管理概述
description: 了解如何使用 Mobile 设备管理和预配包配置 CSP、策略和设备管理。
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
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640451"
---
# <a name="configure-csps-and-device-management-overview"></a>配置 CSP 和设备管理概述

IT 管理员可以在应用程序上定义和实现HoloLens 2。 你使用的配置设置将基于部署方案而异，公司设备将为 IT 提供最广泛的控制权。 在 Windows 10中，配置服务提供商 (CSP) 是一个接口，用于读取、设置、修改或删除设备上的配置设置。 这些设置映射到注册表项或文件。 某些配置服务提供商支持 WAP 格式，一些支持 SyncML，有些支持这两种格式。

有关管理WINDOWS 10 全息版的 CSP，请参阅设备中支持的HOLOLENS[列表](/windows/client-management/mdm/configuration-service-provider-reference#hololens)。
IT 管理员还可以在设备上管理策略 CSP，请参阅管理员支持的策略[CSP 的完整HoloLens 2。](/windows/client-management/mdm/policy-csps-supported-by-hololens2)

## <a name="configuration-methods"></a>配置方法

### <a name="configure-with-mdm"></a>使用 MDM 进行配置

可以在 MDM 系统中注册的任何个人或公司设备上轻松管理 CSP 和策略。 在 MDM 解决方案中注册设备后，你将能够使用设备配置管理该设备或设备集。 详细了解如何通过[MDM HoloLens设备](hololens-mdm-configure.md)。

### <a name="configure-with-provisioning-packages"></a>使用预配包进行配置

HoloLens 2还支持通过自定义预配包为HoloLens 2设备设置一组有限的 CSP 配置。 预配包通常用于非 MDM 托管设备，需要手动应用于每个设备。 阅读有关为 HoloLens[生成自定义预配包的信息](hololens-provisioning.md)。

## <a name="configurations"></a>配置

### <a name="common-device-restrictions"></a>通用设备限制

某些设备限制非常简单，会禁用功能或与设备的连接。 若要了解这些限制，请详细了解 [常见设备限制。](hololens-common-device-restrictions.md)

### <a name="kiosk-modes"></a>展台模式

使用展台模式控制默认情况下哪些标识有权访问哪些应用。 展台可用于单个应用或多个应用 UI 体验。 展台配置包括适用于使用设备的任何人的单个应用，以及不同组的不同应用选择。 展台模式不会阻止"允许的应用"启动其他应用，并且永远不会停止。 有关详细信息， [请阅读展台模式及其使用方法](hololens-kiosk.md)。

### <a name="settings-page-visibility"></a>设置页面可见性

默认情况下设置应用策略来控制哪些标识有权访问设置。 使用此策略，设置应用配置为只显示所选页面，或隐藏所有选定的页面。 [了解如何配置可用的页面](settings-uri-list.md)。

此功能目前仅在预览体验成员Windows[中可用](hololens-insider.md)。 确保要用于此功能的设备位于内部版本 19041.1349+ 上。

### <a name="wdac"></a>WDAC

使用 WDAC 配置来控制允许/禁止启动的应用/进程，而不管系统是否采用展台模式。
[请参阅 WDAC 概述。](windows-defender-application-control-wdac.md)
