---
title: 部署指南 - 使用 Dynamics 365 指南的企业连接的 HoloLens 2 - 维护
description: 了解如何使用 Dynamics 365 指南通过企业连接网络维护 HoloLens 2 设备。
keywords: HoloLens， 管理， 企业连接， Dynamics 365 指南， AAD， Azure AD， MDM， 移动设备管理
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
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448514"
---
# <a name="maintain---corporate-connected-guide"></a>Maintain - 企业连接指南

## <a name="update-hololens"></a>更新 HoloLens

Microsoft 设计适用于企业的 Windows 更新以为 IT 管理员提供更多以 Windows 更新为中心的管理功能，例如对一组设备部署更新的功能，以及为安装更新而定义维护窗口的功能。

管理更新的一种常用方法是将功能延迟 30 天。 这使管理员能够更新和预览新功能，获得第一手知识，并通知支持人员任何新更改。

了解如何管理 [HoloLens](https://docs.microsoft.com/hololens/hololens-updates)更新，包括计划天数、计划时间和在设备上设置使用时段，以便它将在工作时间之外更新。

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>如何更新 Dynamics 365 Guides (和其他应用商店应用) 

Dynamics 365 Guides 是一款In-Box应用，可通过 Microsoft Store 应用进行更新。 对于通过 Microsoft Store 下载的所有应用，可以通过 Microsoft [Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 应用本身手动进行更新。

## <a name="how-to-update-lob-apps"></a>如何更新 LOB 应用

LOB 应用更新的方式与添加到 Intune 的方法相同。 可通过将版本号较高的新应用上载到现有应用配置，在 Intune 中更新应用。 当设备同步到 Intune 时，它将发现存在较新的应用版本，并且将下载较新的应用并替换旧应用。

1. 若要上载较新的应用，请导航到[MEM 门户](https://endpoint.microsoft.com/#home)  ->  **应用**->**所有应用**  ->  *NameOfYourApp*  ->  **属性。**
2. 在"应用信息"旁边，选择"编辑 **"。**
3. 对于"选择要 &quot; 更新的文件"的值 &quot; ，请选择您的文件。
4. 在这里，使用上下文菜单打开文件资源管理器并上传较新版本的 LOB 应用。 确保根据需要包含依赖项。

查看更多： [适用于 HoloLens 的 Intune 应用部署](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="development-plan"></a>开发计划

成功注册设备后，你现在准备好将更多 LOB 应用部署到你的设备。 在本指南的有效期内，我们使用的是示例应用，但更可能希望使用为组织需求构建的自定义应用。

如果你已有 LOB 应用，则你已准备好通过 MDM [部署你的应用](https://docs.microsoft.com/hololens/app-deploy-intune)。 如果你希望采用其他方法，请查看 [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) 的应用程序部署概述，了解将 LOB 应用部署到设备更多方法。

如果你尚未创建自己的 LOB 应用或仍在创建过程中，请查看我们的混合现实开发文档以开始设计和制作原型，或了解开始混合现实[](https://docs.microsoft.com/windows/mixed-reality/design/design)开发的核心概念。 [](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## <a name="support-plan"></a>支持计划

支持计划是一项非常好的计划。 让某人或组接受有关 HoloLens 设备上注册过程的疑难解答培训，以及组织中 HoloLens 设备的常规使用非常有用。 为了允许用户更快地解决问题，我们建议按照与此顺序类似的方式处理你的升级过程：

1. 支持人员。
2. 你的 HoloLens 专家团队
3. [HoloLens 文档](https://docs.microsoft.com/hololens/)  / [HoloLens 疑难解答文档](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [联系支持人员](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>设备管理

本指南讨论了如何设置移动设备管理 (MDM) 并用于设置一些设备配置，并应用设置以允许访问 Wi-Fi 证书和代理。 但是，MDM 还可用于通过 CSP 和策略应用设备限制。

在许多情况下，设备可能会具有连接限制，Bluetooth、VPN、USB 甚至关闭对相机或麦克风的访问。 如果你对其中任何一点感兴趣的内容，我们鼓励你阅读我们的 [常见设备限制页面](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。

可以使用其他更复杂的设备限制。 例如：

- 使用 [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list)限制可在"设置"应用中查看的页面，允许用户仅访问需要调整的设置，例如更改其Wi-Fi连接。
- 使用 [展](https://docs.microsoft.com/hololens/hololens-kiosk) 台模式限制向设备上用户呈现的 UI。 你可以将展台设置为显示单个应用，或者使用自定义起始页显示多个应用。 网亭还可以向不同的用户提供不同的体验。
- [Windows 应用程序控制 (WDAC) ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 来阻止特定应用或进程完全启动。

如果你想要了解有关设备管理或设备限制的其他方法，请执行下一步并阅读我们的 [设备管理概述](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)。





