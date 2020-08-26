---
title: 许可证要求
description: ''
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 3ac86512755620ebb6159dd4d845b488e203dbad
ms.sourcegitcommit: 238d41844116ab94d347a2ffd0fbfa18b8a81947
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2020
ms.locfileid: "10956758"
---
# 许可证要求

## 移动设备管理 (MDM) 许可证指南

如果计划管理 HoloLens 设备，则需要 Azure AD 和 MDM。 Active Director (AD) 不能用于管理 HoloLens 设备。
如果计划使用 Intune 以外的 MDM，则需要 [Azure Active Directory 许可证](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)。
如果打算将 Intune 用作 MDM，请单击[此处](https://docs.microsoft.com/intune/fundamentals/licenses)，其中列出了包含 Intune 许可证的套件。 **请注意，其中大部分套件都包含 Azure AD。**

## 确定应用场景和产品所需的许可证

### HoloLens（第 1 代）许可证要求

可能需要将 HoloLens 第 1 代设备升级为 Windows Holographic for Business。 （请参阅 [HoloLens 商业功能](holoLens-commercial-features.md#feature-comparison-between-editions)以确定是否需要升级）。

 如果需要升级，你将需要执行以下操作：

- 请求 HoloLens 企业许可证 XML 文件
- 将该 XML 文件应用到 HoloLens。 可通过[预配包](hololens-provisioning.md)或[移动设备管理器](https://docs.microsoft.com/intune/configuration/holographic-upgrade)执行此操作

### Remote Assist 许可证要求

确保拥有所需的许可和设备。 可在[此处](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)找到更新的许可和产品要求。

1. [Remote Assist 许可证](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
    1. 或者，尝试[远程协助试用版](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)
1. [Teams 免费增值版/Teams](https://products.office.com/microsoft-teams/free)
1. [Azure Active Directory (Azure AD) 许可证](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

如果打算实现**[此跨租户方案](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**，可能需要信息屏障许可证。 请参阅[这篇文章](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)，以确定是否需要信息屏障许可证。

### Guides 许可证要求

可在[此处](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)找到更新的许可和设备要求。

1. [Azure Active Directory (Azure AD) 许可证](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [Power BI](https://powerbi.microsoft.com/desktop/)
1. [指南](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
