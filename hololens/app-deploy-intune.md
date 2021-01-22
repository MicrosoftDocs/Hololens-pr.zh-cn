---
title: Intune 和公司门户
description: 了解如何使用 Intune、移动设备管理和公司门户设置、分配和创建舒适用户体验。
keywords: intune， 应用管理， 应用， 公司门户， 门户， hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283713"
---
# Intune 和公司门户

借助移动设备管理 (MDM) ，可以通过 [Microsoft Endpoint Manager (Intune) ](https://docs.microsoft.com/intune/windows-holographic-for-business) 使用自己的自定义应用将其直接部署到 HoloLens 设备。 Microsoft Intune 是一项基于云的服务，专注于移动设备管理 (MDM) 和 MAM (移动应用程序) 。 Intune 包含在 Microsoft 企业移动性 + 安全性 ([EMS) 套件中，](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)使用户能够在保持组织数据受保护的同时提高工作效率。 若要了解有关 Intune 的更多信息，请阅读[什么是 Intune。](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

## 安装

1. 将应用上传到业务线，或将自定义应用上传到 Intune 租户。 另请参阅： [企业应用管理](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)。

2. [将应用分配给组](https://docs.microsoft.com/mem/intune/apps/apps-deploy)。 根据你选择的分配类型，如果你选择了应用，该应用可以自动交付或可供轻松下拉。

> [!NOTE]
> 生成 appx 捆绑包时，请务必考虑包括要部署到 () 应用的体系结构。 HoloLens 2 为 ARM64，HoloLens (第一代) x86。 如果你计划使用混合设备环境，你可以将两者都包括在单个 appx 捆绑包中。

## 工作分配类型

若要在注册后在设备上自动安装你的应用，你应该选择该组 (必需) 。 ****
若要将应用下载到通过公司门户注册的设备，请选择 **"可用于已注册的设备"。**

## End-User体验

在 Intune 上设置配置后，你已准备好让最终用户接收所选应用。

按照以下步骤自动获取应用 () ：

1. 向租户注册设备。
2. 设备完成注册后，你应该在设备上接收应用。
3. 如果未立即看到应用，请转到"设置帐户工作或**** 学校帐户信息"，然后向下滚动以查看有关已安装应用  >  ****  >  ****  >  ** 状态的信息。

如何通过公司门户访问应用：

1. 打开"**开始"菜单**并选择**Microsoft Store。**
2. 搜索 **公司门户** 并下载应用。
3. 登录到你的帐户。
4. 选择要接收的应用并下载它。

> [!Tip]
> 详细了解如何 [自动安装](https://docs.microsoft.com/mem/intune/apps/company-portal-app) 公司门户，以及 [部署和管理 Intune 中的应用](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)。
