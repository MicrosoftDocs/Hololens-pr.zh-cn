---
title: HoloLens 2 功能和解决方案
description: 了解使企业能够更轻松地管理 HoloLens 设备的 Microsoft HoloLens Commercial 功能。
author: joyjaz
ms.author: v-jjaswinski
ms.date: 06/28/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
audience: ITPro
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: skerewa
appliesto:
- HoloLens 2
keywords: HoloLens 2, 商业, 功能, mdm, 移动设备管理, 展台模式, 应用程序, 标识, Bitlocker, iris, Windows Hello, Azure 助力, Autopilot, 混合现实, WDAC
ms.openlocfilehash: 88a75224909fd64e387cfb5677056e2ae5d62e4b3518aa758f22ec66a86a8355
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115665330"
---
# <a name="hololens-2-capabilities-and-solutions"></a>HoloLens 2 功能和解决方案

## <a name="what-can-hololens-2-do-for-you"></a>HoloLens 2 有何用途？

借助 HoloLens 2 上的混合现实应用程序，无界限协作并精确操作，以提高员工的工作效率。 使用内置语音命令、眼动跟踪和外部环境锚定功能更长时间、更舒适地保持抬头、免提状态，持续专注于安全、正确地完成任务。 与远程同事实时联系并在覆盖于物理环境中的大幅全息画布上协同工作，以快速解决工作中的问题。 在 Microsoft 的安全性、可靠性和可缩放性的支持下，可靠的应用程序生态系统可以立即实现投资回报。  

[!INCLUDE [solutions](includes/hlsolutions.md)]

## <a name="hololens-2-capabilities"></a>HoloLens 2 功能

什么使 HoloLens 2 如此强大？

| 功能 | 说明 |
|---------|-------------|
| 外部环境锚定 | 锚定全息图精确落准位置。 HoloLens 2 了解你的工作区。 因此，数字内容会持续存在，锚定在工作的物体或表面上。 |
| 手部跟踪 | 自然地触摸、抓取和移动全息影像。 HoloLens 2 可适应你的双手，让你在互动中获得前所未有的满足感。 |
| 眼动跟踪 | 对环境和人的理解已达到新的高度，尽情享受吧。 HoloLens 2 可以准确理解你正在看的位置，因此可以理解你的意图并为你的眼睛实时调整全息图。 |
| 已启用语音 | 借助内置语音命令，你可以在双手忙于任务时快速导航和操作 HoloLens 2。 |
| 人体工学 | HoloLens 2 重量轻 (3.28 kg)，其中包含一个拨盘式适配系统以支持扩展使用。 |
| 大视场 | 使用高分辨率、大视场的显示器展开全息画布。 |
| 无连接线 | 移动自如，无需电线或外部组件即可工作。 |
| Azure 助力 | 流式传输高保真 3D 内容，这些内容可以锚定到在使用 Azure 混合现实服务的用户中持续存在的位置和/或对象。
| 混合现实捕获 | 用照片或视频记录体验，以便与他人实时共享。 |
| Windows Hello for Business | 基于虹膜的生物识别身份验证可让你快速安全地进入工作流程。 |
| Windows Autopilot | 为 HoloLens 2 设置和预配服务，以便在分散的工作场所中立即使用。 |
| 操作系统更新 | 通过每月的服务更新确保安全，并利用一年两次的发布版本中新增的工作效率和可管理性功能。 |
| 轻松管理设备 | 使用 Microsoft Intune、VMware Workspace One、MobileIron 等解决方案同时管理多个 HoloLens 2 设备。 |
| 在管控环境中操作 | HoloLens 2 拥有广泛的设备组合，支持高度管制的环境，包括名为 ISO 5.0 类和 UL I 类，第 2 部分的环境。 |


## <a name="managing-hololens-2-in-your-organization"></a>管理组织中的 HoloLens 2
HoloLens 2 具有使组织能够更轻松地管理和使用 HoloLens 设备的功能。 部分功能包含在设备中，其他功能则可在 [Windows 配置设计器](app-deploy-provisioning-package.md#setup)中通过 [HoloLens 的移动设备管理 (MDM)](hololens-mdm-configure.md) 或通过[预配包](hololens-provisioning.md)启用。

| 我想… | 解决方案 | 说明 |  
|---------| ------------|------------|
管理最终用户的登录方式 | [**标识**](hololens-identity.md) | HoloLens 2 支持多种用户标识 - Azure Active Directory (AAD)、Microsoft 帐户 (MSA) 和本地帐户。  |
| 加密用户数据 | [**数据安全**](security-encryption-data-protection.md) | 在 HoloLens 2 上启用 BitLocker 数据加密，从而提供与任何其他 Windows 设备相同的安全保护级别。 | 
管理组织中的 Hololens 设备 | [**移动设备管理**](hololens-mdm-configure.md) | 从一个中心位置在多个 HoloLens 2 设备上管理设置、选择要安装的应用并根据组织的需要设置安全配置。 | 
|最大程度地缩减新用户和设备的设置时间 | [**Autopilot**](hololens2-autopilot.md) | 在 Microsoft Endpoint Manager 中配置全新体验 (OOBE)，并允许终端用户在几乎没有交互的情况下为业务使用准备设备。 |  
| 控制设备的 OS 更新 | [**适用于企业的 Windows 更新**](hololens-updates.md#managing-updates-by-using-windows-update-for-business) | 适用于企业的 Windows 更新为设备提供受控的操作系统更新，并支持长期服务渠道。 |  
| 允许下载特定应用和 LOB 应用 |[**应用程序管理**](app-deploy-overview.md) | 选择如何为选定的 HoloLens 2 用户组分发和控制应用。 | 
| 显示或隐藏“开始”菜单上的特定应用 |[**展台模式**](hololens-kiosk.md) | 将 HoloLens 2 配置为固定用途设备，用于应用演示或专用业务应用。 
| 通过锁定应用来保护环境 | [**WDAC**](windows-defender-application-control-wdac.md) | Windows Defender 应用程序控制 (WDAC) 阻止设备用户启动应用和进程。
| 使用应用规则和进程规则管理设备安全 | [**策略 (CSP)**](hololens-csp-policy-overview.md) | IT 管理员可以使用 HoloLens 2 上支持的策略 CSP 的现有列表来定义和实现策略设置。 |  
| 管理设备如何连接到 Internet | [**网络和连接性**](hololens-certificates-network.md) | 使用基于证书的身份验证访问 Wi-Fi、VPN 或内部资源。 | 
| 与多个用户共享设备 | [**自动自定义显示**](hololens-calibration.md#auto-eye-position-support) | HoloLens 2 显示通过自动眼部位置 (AEP) 自动调整，无需在[用户共享](hololens-multiple-users.md)设备时运行手动校准过程。 |

了解上述解决方案的[许可要求](hololens-licenses-requirements.md)。

## <a name="next-steps"></a>后续步骤
> [!div class="nextstepaction"]
> [探索 HoloLens 2 选项](hololens2-options.md)

> [!div class="nextstepaction"]
>[规划 HoloLens 2 部署](hololens-requirements.md) 
