---
title: Intune 和公司门户
description: 了解如何使用 Intune、移动设备管理和公司门户设置、分配和创建舒适的用户体验。
keywords: intune，应用管理，应用，公司门户，门户，hololens
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308472"
---
# <a name="intune--company-portal"></a>Intune & 公司门户

使用移动设备管理 (MDM) ，你可以通过 [Microsoft 终结点管理器 (Intune) ](https://docs.microsoft.com/intune/windows-holographic-for-business) 使用你自己的自定义应用，以将其直接部署到 HoloLens 设备。 Microsoft Intune 是一项基于云的服务，关注移动设备管理 (MDM) 和移动应用程序管理 (MAM)。 Intune 包含在 Microsoft 的[企业移动性 + 安全性 (EMS) 套件](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)中，使用户能够提高工作效率，同时保护组织数据。 若要了解有关 Intune 的详细信息，请阅读 [什么是 intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)。

## <a name="setup"></a>设置

1. 将应用上传到业务线，或将自定义应用上传到 Intune 租户。 另请参阅： [企业应用管理](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)。

2. [将应用分配到组](https://docs.microsoft.com/mem/intune/apps/apps-deploy)。 根据所选的分配类型，应用可以自动传递，也可以在有选择的应用的情况下随时向下移动。

> [!NOTE]
> 生成 appx 捆绑时，请确保考虑要部署到) 的设备 (的体系结构。 HoloLens 2 为 ARM64，且 HoloLens (第一代) 为 x86。 如果你计划使用混合设备环境，则可以将这两个包都包含在单个 appx 捆绑包中。

## <a name="assignment-types"></a>分配类型

若要在注册后将应用自动安装到设备上，则应为该组 (s) 选择 " **必需** "。
若要使应用可下载到通过公司门户注册的设备，请选择 " **可用于已注册的设备**"。

## <a name="end-user-experience"></a>最终用户体验

在 Intune 上设置配置后，最终用户就可以接收选定的应用了。

按照以下步骤自动 () 的应用：

1. 将你的设备注册到你的租户。
2. 设备完成注册后，你应在设备上收到应用。
3. 如果你没有立即看到应用，请访问 "**设置**  >    >  " "帐户" "**工作或学校**  >  *帐户* 信息"，并向下滚动以查看有关已安装应用状态的信息。

如何通过公司门户获取应用：

1. 打开 " **开始" 菜单** 并选择 " **Microsoft Store**"。
2. 搜索 **公司门户** 并下载应用。
3. 登录到你的帐户。
4. 选择要接收的应用并下载它。

> [!Tip]
> 详细了解如何在 Intune 中 [自动安装公司门户](https://docs.microsoft.com/mem/intune/apps/company-portal-app) 以及如何 [部署和管理应用](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)。
