---
title: Intune 和公司门户
description: intune、应用管理、应用、公司门户、门户
keywords: intune、应用管理、应用、公司门户、门户、hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
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
ms.openlocfilehash: 5fc369caa2e5e26c91c07f9270c3984177507dbd
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009460"
---
# Intune 和公司门户

通过移动设备管理 (MDM) ，你可以通过 [Microsoft 终结点管理器 (Intune ](https://docs.microsoft.com/intune/windows-holographic-for-business) 使用你自己的自定义应用) 将其直接部署到 HoloLens 设备。 Microsoft Intune 是基于云的服务，侧重于移动设备管理 (MDM) 和移动应用管理 (MAM) 。 Intune 包含在 Microsoft 的[企业移动性 + 安全 (EMS) 套件](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)中，使用户可以提高工作效率，同时保持组织数据受保护。 若要了解有关 Intune 的详细信息，请阅读 [什么是 intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)。

## 安装

1. 将应用上载到某一业务线，或将自定义应用上载到你的 Intune 租户。 另请参阅： [企业应用管理](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)。

2. [将你的应用分配到组](https://docs.microsoft.com/mem/intune/apps/apps-deploy)。 根据你选择的作业类型，你可以将应用自动发送或打开，如果你有选择的应用，可以轻松地将其拉下。 

> [!NOTE] 
> 在构建 appx 捆绑时，请确保考虑为要部署到) 的设备 (s 的体系结构。 HoloLens 2 是 ARM64，HoloLens (第一代) 是 x86。 如果你计划拥有混合设备环境，则可以在单个 appx 捆绑包中包括这两者。

## 工作分配类型

如果你希望在注册后在设备上自动安装你的应用，你应该为该组 (s ") 选择" **必需** "。
如果你希望将应用下载到通过公司门户注册的应用，请选择 " **可用于注册的设备**"。


## 最终用户体验

在 Intune 上设置配置后，最终用户即可接收所选应用。

按照以下步骤自动获取你的应用 (s) ：
1. 向你的租户注册你的设备。 
2. 设备完成注册后，你应在设备上收到该应用。 
3. 如果你未立即看到你的应用，请转到 "**设置**  >  **帐户**  >  **工作或学校**  >  **帐户**信息"，然后向下滚动以查看有关已安装的应用状态的信息。

如何通过公司门户访问应用：
1. 打开 " **开始" 菜单** ，然后选择 " **Microsoft Store**"。 
2. 搜索 **公司门户** 并下载应用。
3. 登录到您的帐户。
4. 选择你希望接收和下载的应用。

> [!Tip]
> 了解有关 [自动安装公司门户](https://docs.microsoft.com/mem/intune/apps/company-portal-app) 和 [在 Intune 中部署和管理应用](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)的详细信息。
