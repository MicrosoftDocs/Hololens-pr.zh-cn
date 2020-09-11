---
title: 概述-应用程序管理
description: 应用、管理、应用管理
keywords: HoloLens、用户、帐户、应用、应用程序管理
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
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
ms.openlocfilehash: e73a56e5a2fcef14e85f5f552e264dd8d796cc8f
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009450"
---
# 应用管理：概述

你可以将应用部署到以下四种不同的路径： **移动设备管理 (MDM) **、 **Microsoft store for Business**、 **Microsoft store**或通过 **预配**进行安装。 

## 移动设备管理 (MDM)

MDM 解决方案使 IT 决策者和管理员能够通过应用商店为一组用户在应用商店中私下自动安装 (推送) 其内部、业务线应用或购买应用。 HoloLens 设备最适合使用 Microsoft 终结点管理器 (Intune) [应用程序管理](app-deploy-intune.md)。 Intune 还通过公司门户可下载体验向用户提供对 IT 托管应用的精细控制。

> [!NOTE] 
> 以下说明适用于希望使用 Intune 管理其应用程序的用户。 Microsoft 建议使用 Intune 进行应用和设备管理。
    
 (MDM) 的移动设备管理适用于以下情况： 
* 已部署 MDM + 公司门户 
*  (非公共) 应用的 Buisness 行
* 通过公司门户手动安装可用应用程序
* 通过 MDM 策略的管理员推送
* 通过 MDM 自动更新

## 适用于企业的 Microsoft Store

[Microsoft Store For Business](app-deploy-store-business.md)向企业中的 IT 决策者和管理员提供查找、获取、管理和分发免费和付费应用的人员。 IT 管理员可以管理一份清单中的 Microsoft Store 应用、专用业务线应用以及根据需要分配和重新使用许可证。 有关详细信息，请访问 [使用 Microsoft Store For Business 的先决条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)。
    
适用于企业的 Microsoft Store 适用于： 
* 公共或业务线应用程序
* 通过 MDM 关联自动安装所需的应用程序
* 用户手动下载应用
* 自动更新

## Microsoft Store 应用

Microsoft Store 向企业中的 IT 决策者和管理员提供查找、获取、管理和分发公共应用的人员。
    
此 Microsoft Store 适用于： 
* 仅限公共应用
* 用户手动下载应用
* 如果已连接到 Internet，则自动更新

有关详细信息，请访问 [全息应用商店应用](https://docs.microsoft.com/hololens/holographic-store-apps)。

## 通过预配程序包安装

[预配程序包](app-deploy-provisioning-package.md) 允许你安装自定义或业务线应用，从而允许 IT 专业人员和管理员通过 USB 将应用快速安装到本地设备 (s) 。 这可以在没有互联网连接和任何标识类型的情况下完成。
    
通过预配程序包安装适用于： 
*  (非公共) 应用的 Buisness 行
* 如果脱机安装程序可用，则公共应用 () 
* 仅限 USB 盘面加载
* 无自动更新 (需要通过预配程序包手动更新) 
