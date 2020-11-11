---
title: 概述-应用程序管理
description: 应用、管理、应用管理
keywords: HoloLens、用户、帐户、应用、应用程序管理
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
ms.openlocfilehash: 36d86e24cc10d6b8457cfb415528398a8d43aa27
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162867"
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
*  (非公共) 应用的 Buisness/自行开发的行
* 如果脱机安装程序可用，则公共应用 () 
* 仅限 USB 盘面加载
* 无自动更新 (需要通过预配程序包手动更新) 

## 通过应用安装程序在 HoloLens 2 上安装应用
使用 [应用安装程序](app-deploy-app-installer.md) 用户可以获得在本地设备上安装应用或与其他不熟悉 HoloLens 上的其他应用安装方法的其他人共享应用的体验。 无需启用开发人员模式或使用 Device Portal，即可执行此操作。 这是分发完全生成的应用的简单方法。 无论你是希望使用 HoloLens 向另一位用户演示你的应用，还是想要部署你的应用，此方法都很容易。

通过应用安装程序安装适用于： 
*  (非公共) 应用的 Buisness/自行开发的行
* 仅限侧加载
* 不需要开发人员模式或 Device portal
* 便于最终用户安装


