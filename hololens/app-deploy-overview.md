---
title: 概述 - 应用管理
description: 应用， 管理， 应用管理
keywords: HoloLens， 用户， 帐户， 应用， 应用程序管理，
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
ms.openlocfilehash: 2ca0b05b6ed61ddce327a44fedbbcf280b33a106
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252663"
---
# 应用管理：概述

你可以部署四种不同路径的应用：移动设备管理** (MDM) 、****适用于企业**Microsoft **Store、Microsoft Store，** 或通过预配安装**它们**。

## 移动设备管理 (MDM)

MDM 解决方案使 IT 决策者和管理员可以专用地自动安装 (推送) 其内部、业务线应用，或通过应用商店为一组用户购买应用。 HoloLens 设备最适用于 Microsoft Endpoint Manager (Intune) [应用程序管理](app-deploy-intune.md)。 Intune 还通过公司门户可下载体验为用户提供对 IT 托管应用的更精细控制。

> [!NOTE]
> 以下说明适用于想要使用 Intune 管理其应用程序的用户。 Microsoft 建议使用 Intune 进行应用程序和设备管理。

移动设备管理 (MDM) 适用于：

* MDM 已部署 + 公司门户
* 非公共 (业务线) 应用程序
* 通过公司门户手动安装可用应用程序
* 管理员推送 MDM 策略
* 通过 MDM 自动更新

## 适用于企业的 Microsoft Store

适用于 [企业的 Microsoft Store](app-deploy-store-business.md) 为企业的 IT 决策者和管理员提供查找、获取、管理和分发免费和付费应用。 IT 管理员可以在一个清单中管理 Microsoft Store 应用和专用业务线应用，并根据需要分配和重复使用许可证。 有关详细信息，请访问使用适用于企业 [Microsoft Store 的先决条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)。

适用于 Business 的 Microsoft Store 适用于：

* 公共或业务线应用
* 通过 MDM 关联自动安装所需应用程序
* 用户手动下载应用
* 自动更新

## Microsoft Store 应用

Microsoft Store 为企业的 IT 决策者和管理员提供查找、获取、管理和分发公共应用。

此 Microsoft Store 适用于：

* 仅公共应用
* 用户手动下载应用
* 连接到 Internet 时自动更新

有关详细信息，请访问 [全息应用商店应用](https://docs.microsoft.com/hololens/holographic-store-apps)。

## 通过预配包安装

[预配包](app-deploy-provisioning-package.md) 允许你安装自定义或业务线应用，使 IT 专业人员和管理员可以通过 USB 将应用 () 本地设备。 无需 Internet 连接和任何标识类型即可完成此安装。

通过预配包进行安装适用于：

* 业务线/自开发 (非公共) 应用
* 公共应用 (脱机安装程序是否可用) 
* 仅 USB 旁加载
* 无需自动更新 (通过预配包进行手动) 

## 通过应用安装程序在 HoloLens 2 上安装应用

使用 [应用](app-deploy-app-installer.md) 安装程序，用户可以拥有一种简单易用的体验：在本地设备上安装应用，或与不熟悉 HoloLens 上其他应用安装方法的其他人共享应用。 无需启用开发人员模式或使用 Device Portal 即可完成此操作。 这是分发完全生成应用的简单方法。 无论你只是希望使用 HoloLens 将应用演示给其他用户，还是想要部署你的应用，此方法都很容易实现。

通过应用安装程序安装适用于：

* 业务线/自开发 (公共) 应用程序
* 仅旁加载
* 不需要开发人员模式或设备门户
* 易于最终用户安装
