---
title: 部署指南 - 使用 HoloLens 2 连接Dynamics 365 Guides - 维护
description: 了解如何使用 HoloLens 2 通过企业连接网络维护Dynamics 365 Guides。
keywords: HoloLens、管理、企业连接、Dynamics 365 Guides、AAD、Azure AD、MDM、移动设备管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 2649e370e98747562591c031b8ae262674c831e071f4ef228557dda66d2dc768
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115660274"
---
# <a name="maintain---corporate-connected-guide"></a>维护 - 企业连接指南

## <a name="update-hololens"></a>更新 HoloLens

Microsoft 设计适用于企业的 Windows 更新以为 IT 管理员提供更多以 Windows 更新为中心的管理功能，例如对一组设备部署更新的功能，以及为安装更新而定义维护窗口的功能。

管理更新的一种常用方法是将功能延迟 30 天。 这样，管理员可以更新和预览新功能，获得第一手知识，并告知支持人员任何新更改。

了解如何管理[HoloLens](/hololens/hololens-updates)更新，包括计划天数、计划时间，以及设置设备的活动小时数，以便它在工作时间之外更新。

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>如何更新Dynamics 365 Guides (和其他应用商店应用) 

Dynamics 365 Guides是一In-Box应用，可通过 Microsoft Store 应用进行更新。 对于通过 Microsoft Store 下载的所有应用，可以通过手动更新[Microsoft Store应用本身](/hololens/holographic-store-apps#update-apps)进行更新。

## <a name="how-to-update-lob-apps"></a>如何更新 LOB 应用

LOB 应用的更新方式与添加到 Intune 的方式相同。 可以通过将版本号更高的新应用上传到现有应用配置，在 Intune 中更新应用。 当设备同步到 Intune 时，它会观察到存在更新的应用版本，并且将下载更新的应用并替换旧应用。

1. 若要上传较新的应用，请导航到 [MEM](https://endpoint.microsoft.com/#home)门户"应用  ->  "-">**应用**  ->  *""NameOfYourApp*  ->  **属性"。**
2. 在"应用信息"旁边，选择"编辑 **"。**
3. 对于"选择要 &quot; 更新的文件"的值 &quot; ，请选择文件。
4. 在此处，使用上下文菜单打开文件资源管理器并上传较新版本的 LOB 应用。 确保根据需要包含依赖项。

有关详细信息，请参阅[Intune 应用部署HoloLens](/hololens/app-deploy-intune)

## <a name="development-plan"></a>开发计划

成功注册设备后，现在可以将更多 LOB 应用部署到设备。 在本指南的持续时间内，我们将使用示例应用，但更可能希望使用根据组织需求构建的自定义应用。

如果已有 LOB 应用，则可以通过 [MDM 部署应用](/hololens/app-deploy-intune)。 如果希望使用不同的方法，请查看应用程序部署概述HoloLens 2了解将[](/hololens/app-deploy-overview)LOB 应用部署到设备的更多方法。

如果尚未创建自己的 LOB 应用或仍处于创建过程中，请查看我们的混合现实开发文档，开始设计和原型制作，或学习核心概念[](/windows/mixed-reality/design/design)以开始使用混合现实[开发](/windows/mixed-reality/discover/get-started-with-mr)。

## <a name="support-plan"></a>支持计划

制定支持计划是一项极佳的计划。 让某人或一个组在设备上对注册过程进行故障排除HoloLens以及组织中对 HoloLens 设备的常规使用非常有用。 为了使用户更快地解决其问题，我们建议以类似于此顺序的方式处理升级过程：

1. 支持人员。
2. 你的 HoloLens 专家团队
3. [HoloLens Docs](/hololens/)  / [HoloLens故障排除文档](/hololens/hololens-troubleshooting)
4. [联系支持人员](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>设备管理

本指南讨论了如何设置 Mobile 设备管理 (MDM) 并用于设置一些设备配置，并应用设置以允许访问Wi-Fi证书和代理。 但是，MDM 还可用于通过 CSP 和策略应用设备限制。

在许多情况下，设备可能会受到连接限制，例如蓝牙 VPN、USB，甚至会关闭对相机或麦克风的访问。 如果你对上述任一内容感兴趣的内容，建议阅读常见的 [设备限制页](/hololens/hololens-common-device-restrictions)。

可以使用其他更复杂的设备限制。 如：

- 通过使用[SettingsPageVisibility](/hololens/settings-uri-list)限制可在 设置 应用中查看的页面，允许用户仅访问需要调整的设置，例如更改Wi-Fi连接。
- 使用 [展台](/hololens/hololens-kiosk) 模式限制向设备上用户呈现的 UI。 可以将展台设置为显示单个应用，或者使用自定义起始页显示多个应用。 展台还可以向不同的用户提供不同的体验。
- [Windows应用程序控制 (WDAC) ，](/hololens/windows-defender-application-control-wdac)使特定应用或进程完全启动。

若要了解设备管理或设备限制的其他方法，请执行下一步并阅读我们的设备管理 [概述](/hololens/hololens-csp-policy-overview)。





