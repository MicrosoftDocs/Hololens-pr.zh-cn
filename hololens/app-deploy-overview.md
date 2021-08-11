---
title: 概述 - 应用管理
description: 开始使用移动设备管理、适用于业务的 Microsoft 应用商店和预配包的混合现实应用管理概述。
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
ms.openlocfilehash: 019700c7e35f31c234c9fe69870cae54b3364b631253c37a17d8eaa0fe3053bd
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665227"
---
# <a name="app-management-overview"></a>应用管理：概述

可以在四个不同的路径上部署应用：移动 **设备管理 (MDM**) 、适用于企业的 Microsoft Store、Microsoft Store，或通过预配 来 **安装它们**。 

## <a name="mobile-device-management-mdm"></a>移动设备管理 (MDM)

MDM 解决方案使 IT 决策者和管理员能够以私密方式自动安装 (推送) 其内部应用、业务线应用，或者通过应用商店为一组用户购买应用。 HoloLens设备最适合使用 Microsoft Endpoint Manager (Intune) 应用程序[管理](app-deploy-intune.md)。 Intune 还通过可下载体验为用户提供更精细的 IT 公司门户控制。

> [!NOTE]
> 以下说明适用于想要使用 Intune 管理其应用程序的用户。 Microsoft 建议使用 Intune 进行应用程序和设备管理。

移动设备管理 (MDM) 适用于：

* MDM 已部署 + 公司门户
* 业务线 (非公共) 应用
* 手动安装可用应用程序公司门户
* 管理员通过 MDM 策略推送
* 通过 MDM 自动更新

## <a name="microsoft-store-for-business"></a>适用于企业的 Microsoft Store

该[适用于企业的 Microsoft Store](app-deploy-store-business.md)为企业中的 IT 决策者和管理员提供查找、获取、管理和分发免费和付费应用。 IT 管理员可以管理Microsoft Store一个清单中的应用和专用业务线应用，并根据需要分配和重复使用许可证。 有关详细信息，请访问使用[适用于企业的 Microsoft Store](/microsoft-store/prerequisites-microsoft-store-for-business)的先决条件。

此适用于企业的 Microsoft Store适用于：

* 公共或业务线应用
* 通过 MDM 关联自动安装所需的应用程序
* 用户手动下载应用
* 自动更新

## <a name="microsoft-store-apps"></a>Microsoft Store 应用

该Microsoft Store为企业中的 IT 决策者和管理员提供查找、获取、管理和分发公共应用。

此Microsoft Store适用于：

* 仅公共应用
* 用户手动下载应用
* 连接到 Internet 时自动更新

有关详细信息，请访问 [全息应用商店应用](/hololens/holographic-store-apps)。

## <a name="install-via-provisioning-packages"></a>通过预配包安装

[预配包](app-deploy-provisioning-package.md) 允许安装自定义应用或业务线应用，使 IT 专业人员和管理员可以通过 USB 将应用 (本地) 设备。 无需 Internet 连接和任何标识类型即可完成此安装。

通过预配包进行安装适用于：

* 业务线/自 (非公共) 应用
* 如果脱机 (安装程序可用，则公共应用) 
* 仅 USB 旁加载
* 无需自动更新 (通过预配包包进行手动) 

## <a name="install-apps-on-hololens-2-via-app-installer"></a>通过 应用安装程序 在 HoloLens 2 安装应用

使用[应用安装程序，](app-deploy-app-installer.md)用户可以获得一种简单的体验，即在本地设备上安装应用，或者与不熟悉其他应用安装方法的用户共享应用HoloLens。 无需启用开发人员模式或使用开发人员模式即可设备门户。 这是分发完全生成应用的简单方法。 无论你只是希望将应用演示给其他用户HoloLens，还是想要部署应用，此方法都很容易。

通过 应用安装程序 适用于：

* 业务线/自 (非公共) 应用
* 仅旁加载
* 不需要开发人员模式或设备门户
* 最终用户易于安装
