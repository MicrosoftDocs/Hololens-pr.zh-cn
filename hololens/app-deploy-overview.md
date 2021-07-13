---
title: 概述-应用管理
description: 使用移动设备管理、适用于企业的 Microsoft 应用商店和预配包的混合现实应用管理概述入门。
keywords: HoloLens、用户、帐户、应用、应用程序管理、
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635545"
---
# <a name="app-management-overview"></a>应用管理：概述

可以在四个不同的路径上部署应用：**移动设备管理 (MDM)**、**适用于企业的 Microsoft Store**、 **Microsoft Store** 或通过 **设置** 来安装。

## <a name="mobile-device-management-mdm"></a>移动设备管理 (MDM)

通过 MDM 解决方案，IT 决策者和管理员可通过个人自动安装 (推送) 其内部、业务线应用，或者通过应用商店为一组用户购买应用。 HoloLens 设备最好与 Microsoft Endpoint Manager (Intune) 用于[应用程序管理](app-deploy-intune.md)。 Intune 还通过公司门户可下载的体验为用户提供对 IT 托管应用的精细控制。

> [!NOTE]
> 以下说明适用于想要通过 Intune 管理其应用程序的用户。 Microsoft 建议使用 Intune 进行应用程序和设备管理。

 (MDM) 的移动设备管理适用于：

* 已部署 MDM + 公司门户
* 业务线 (非公共) 应用
* 通过公司门户手动安装可用应用程序
* 通过 MDM 策略的管理员推送
* 通过 MDM 自动更新

## <a name="microsoft-store-for-business"></a>适用于企业的 Microsoft Store

[适用于企业的 Microsoft Store](app-deploy-store-business.md)为 IT 决策者和企业中的管理员提供查找、获取、管理和分发免费和付费应用程序的管理员。 IT 管理员可以在一个库存中管理 Microsoft Store 应用和私有业务线应用，还可以根据需要分配和重复使用许可证。 有关详细信息，请访问[使用适用于企业的 Microsoft Store 的先决条件](/microsoft-store/prerequisites-microsoft-store-for-business)。

适用于企业的 Microsoft Store 适用于：

* 公共或业务线应用
* 通过 MDM 关联自动安装所需的应用程序
* 用户手动下载应用
* 自动更新

## <a name="microsoft-store-apps"></a>Microsoft Store 应用

Microsoft Store 为 IT 决策者和企业中的管理员提供查找、获取、管理和分发公共应用程序的管理员。

此 Microsoft Store 适用于：

* 仅限公共应用
* 用户手动下载应用
* 如果已连接到 Internet，则自动更新

有关详细信息，请访问 [全息应用商店应用](/hololens/holographic-store-apps)。

## <a name="install-via-provisioning-packages"></a>通过预配包安装

[预配包](app-deploy-provisioning-package.md) 允许安装自定义或业务线应用，允许 IT 专业人员和管理员通过 USB 将应用快速安装到本地设备 () 。 如果没有 internet 连接，则可以进行这种安装，任何标识类型都可以这样做。

通过预配包安装适用于：

* 业务线/自行开发 (非公共) 应用
* 公开应用程序 (如果脱机安装程序可用) 
* 仅限 USB 边载
* 无自动更新 (需要通过预配包进行手动更新) 

## <a name="install-apps-on-hololens-2-via-app-installer"></a>在 HoloLens 2 通过应用安装程序安装应用

使用[应用程序安装程序](app-deploy-app-installer.md)时，用户可以体验到在本地设备上安装应用程序，或与其他不熟悉 HoloLens 上的应用程序安装方法的人员共享应用程序。 无需启用开发人员模式或使用设备门户即可执行此操作。 这是分发完全生成的应用的一种简单方法。 无论你只是想要使用 HoloLens 向另一个用户演示应用程序，还是想要部署应用程序，都可以轻松地使用此方法。

通过应用安装程序安装适用于：

* 业务线/自行开发 (非公共) 应用
* 仅侧加载
* 不需要开发人员模式或设备门户
* 便于最终用户安装
