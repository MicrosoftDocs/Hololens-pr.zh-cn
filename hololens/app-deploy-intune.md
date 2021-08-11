---
title: Intune 和 公司门户
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
ms.openlocfilehash: f1c178c940224ed3cd07c58b886b176108614caf7a8463af089e2f2357f45553
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665244"
---
# <a name="intune--company-portal"></a>Intune 和公司门户

使用 Mobile 设备管理 (MDM) ，可以通过[Microsoft Endpoint Manager (Intune) ](/intune/windows-holographic-for-business)使用自己的自定义应用，将其直接部署到 HoloLens 设备。 Microsoft Intune 是一项基于云的服务，关注移动设备管理 (MDM) 和移动应用程序管理 (MAM)。 Intune 包含在 Microsoft 的[企业移动性 + 安全性 (EMS) 套件](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)中，使用户能够提高工作效率，同时保护组织数据。 若要详细了解 Intune，请阅读[什么是 Intune。](/mem/intune/fundamentals/what-is-intune)

## <a name="setup"></a>设置

1. Upload应用上传到业务线，或将自定义应用上传到 Intune 租户。 另请参阅[：Enterprise应用管理。](/windows/client-management/mdm/enterprise-app-management)

2. [将应用分配到组](/mem/intune/apps/apps-deploy)。 根据你选择的分配类型，如果选择了应用，则应用可以自动传送或可供随时下拉。

> [!NOTE]
> 生成 appx 捆绑包时，请务必考虑包括要 () 的设备的体系结构。 HoloLens 2 ARM64，HoloLens (第一代) x86。 如果计划使用混合设备环境，可以同时在单个 appx 捆绑包中包括这两者。

## <a name="assignment-types"></a>分配类型

若要在注册后在设备上自动安装应用，应为该组选择"必需 (") 。 
若要使应用可供下载到通过公司门户注册的设备，请选择"**可用于已注册的设备"。**

## <a name="end-user-experience"></a>最终用户体验

在 Intune 上设置配置后，最终用户即可接收所选应用。

按照以下步骤自动获取应用 (应用) ：

1. 向租户注册设备。
2. 设备完成注册后，应会收到设备上的应用。
3. 如果未立即看到应用，请转到"设置工作或学校帐户信息"，然后向下滚动以查看  >    >    >  有关已安装应用状态的信息。

如何通过以下应用公司门户：

1. 打开"**开始"菜单** 并选择 **"Microsoft Store"。**
2. 搜索公司门户 **并** 下载应用。
3. 登录到帐户。
4. 选择要接收的应用并下载它。

> [!Tip]
> 详细了解如何[自动安装应用公司门户](/mem/intune/apps/company-portal-app) [Intune 中部署和管理应用](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)。
