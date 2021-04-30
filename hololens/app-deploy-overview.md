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
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308360"
---
# <a name="app-management-overview"></a>应用管理：概述

你可以在四个不同的路径上部署应用： **移动设备管理 (MDM)**、 **Microsoft Store for Business**、 **Microsoft Store** 或通过 **预配** 安装这些应用。

## <a name="mobile-device-management-mdm"></a>移动设备管理 (MDM)

通过 MDM 解决方案，IT 决策者和管理员可通过个人自动安装 (推送) 其内部、业务线应用，或者通过应用商店为一组用户购买应用。 HoloLens 设备最好与 Microsoft 终结点管理器 (Intune) 用于 [应用程序管理](app-deploy-intune.md)。 Intune 还通过公司门户可下载的体验为用户提供对 IT 托管应用的精细控制。

> [!NOTE]
> 以下说明适用于想要通过 Intune 管理其应用程序的用户。 Microsoft 建议使用 Intune 进行应用程序和设备管理。

 (MDM) 的移动设备管理适用于：

* 已部署 MDM + 公司门户
* 业务线 (非公共) 应用
* 通过公司门户手动安装可用应用程序
* 通过 MDM 策略的管理员推送
* 通过 MDM 自动更新

## <a name="microsoft-store-for-business"></a>适用于企业的 Microsoft Store

[企业 Microsoft Store](app-deploy-store-business.md)向 IT 决策者和管理员提供了查找、获取、管理和分发免费和付费应用程序的企业。 IT 管理员可以在一个库存中管理 Microsoft Store 应用和私有业务线应用，还可以根据需要分配和重复使用许可证。 有关详细信息，请访问 [使用 Microsoft Store For Business 的先决条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)。

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

有关详细信息，请访问 [全息应用商店应用](https://docs.microsoft.com/hololens/holographic-store-apps)。

## <a name="install-via-provisioning-packages"></a>通过预配包安装

[预配包](app-deploy-provisioning-package.md) 允许安装自定义或业务线应用，允许 IT 专业人员和管理员通过 USB 将应用快速安装到本地设备 () 。 如果没有 internet 连接，则可以进行这种安装，任何标识类型都可以这样做。

通过预配包安装适用于：

* 业务线/自行开发 (非公共) 应用
* 公开应用程序 (如果脱机安装程序可用) 
* 仅限 USB 边载
* 无自动更新 (需要通过预配包进行手动更新) 

## <a name="install-apps-on-hololens-2-via-app-installer"></a>通过应用安装程序在 HoloLens 2 上安装应用

使用 [应用程序安装程序](app-deploy-app-installer.md) 时，用户可以体验到在本地设备上安装应用程序，或与不熟悉 HoloLens 上其他应用安装方法的其他人共享应用程序。 无需启用开发人员模式或使用设备门户即可执行此操作。 这是分发完全生成的应用的一种简单方法。 无论你是想要使用 HoloLens 向另一个用户演示应用，还是想要部署应用，都可以轻松地使用此方法。

通过应用安装程序安装适用于：

* 业务线/自行开发 (非公共) 应用
* 仅侧加载
* 不需要开发人员模式或设备门户
* 便于最终用户安装
