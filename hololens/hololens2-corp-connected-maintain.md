---
title: 部署指南–企业连接的 HoloLens 2 （含 Dynamics 365 指南）-维护
description: 了解如何在使用 Dynamics 365 指南的公司连接网络上维护 HoloLens 2 设备。
keywords: HoloLens，管理，企业连接，Dynamics 365 指南，AAD，Azure AD，MDM，移动设备管理
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308423"
---
# <a name="maintain---corporate-connected-guide"></a>维护-企业连接指南

## <a name="update-hololens"></a>更新 HoloLens

Microsoft 设计适用于企业的 Windows 更新以为 IT 管理员提供更多以 Windows 更新为中心的管理功能，例如对一组设备部署更新的功能，以及为安装更新而定义维护窗口的功能。

管理更新的一种常用方法是将功能延迟为30天。 这样，管理员就可以更新和预览新功能，获得第一手知识，并通知支持人员进行任何新的更改。

了解如何 [管理 HoloLens 更新](https://docs.microsoft.com/hololens/hololens-updates)，包括计划的日期、计划的时间和在设备上设置活动时间，以便在工作时间之外进行更新。

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a>如何 (和其他应用商店应用更新 Dynamics 365 指南) 

Dynamics 365 指南是一个 In-Box 的应用，可通过 Microsoft Store 应用进行更新。 对于通过 Microsoft Store 下载的所有应用程序，可以手动 [通过 Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 应用程序进行更新。

## <a name="how-to-update-lob-apps"></a>如何更新 LOB 应用

LOB 应用的更新方式与将其添加到 Intune 的方式相同。 可以通过将具有更高版本号的新应用上传到现有应用配置，在 Intune 中更新应用。 当设备同步到 Intune 时，会发现有一个较新的应用程序版本，将下载较新的应用程序并替换旧的应用程序。

1. 若要上传更新的应用，请导航到 "[内存门户](https://endpoint.microsoft.com/#home)  ->  **应用**-> 所有 **应用**" "  ->  *TheNameOfYourApp*"  ->  **属性。**
2. 在 "应用信息" 旁边，选择 " **编辑"。**
3. 对于 " &quot; 选择要更新的文件" 的值 &quot; ，请选择文件。
4. 从这里，使用上下文菜单打开文件资源管理器，并上传新版本的 LOB 应用。 确保根据需要包含依赖项。

了解更多： [适用于 HoloLens 的 Intune 应用部署](https://docs.microsoft.com/hololens/app-deploy-intune)

## <a name="development-plan"></a>开发计划

成功注册设备后，你现在已准备好将更多 LOB 应用部署到设备。 在本指南中，我们使用的是示例应用程序，但更有可能需要使用为组织需求构建的自定义应用。

如果你已有 LOB 应用，则可以 [通过 MDM 部署](https://docs.microsoft.com/hololens/app-deploy-intune)你的应用。 如果希望使用不同的方法，请查看 [HoloLens 2 的应用程序部署概述](https://docs.microsoft.com/hololens/app-deploy-overview) ，了解将 LOB 应用程序部署到设备的更多方法。

如果你尚未创建自己的 LOB 应用或仍处于创建过程中，请查看我们的混合现实开发文档，以[开始设计和构建原型](https://docs.microsoft.com/windows/mixed-reality/design/design)，或了解有关[混合现实开发入门](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)的核心概念。

## <a name="support-plan"></a>支持计划

支持计划是一个不错的做法。 让某个人或某个组训练了对 HoloLens 设备上的注册过程进行故障排除，并对你的组织中的 HoloLens 设备进行一般使用非常有用。 为了使用户能够更快地解决其问题，我们建议以类似于此顺序的方式处理升级过程：

1. 你的支持人员。
2. HoloLens 专家团队
3. [HoloLens 文档](https://docs.microsoft.com/hololens/)  / [HoloLens 疑难解答文档](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [联系支持人员](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a>设备管理

本指南讨论 (MDM) 设置移动设备管理，并使用它来设置某些设备配置，并应用设置以允许 Wi-Fi 证书和代理进行访问。 但是，也可以使用 MDM 通过 Csp 和策略应用设备限制。

在许多情况下，设备可能具有连接限制，如 Bluetooth、VPN、USB，甚至关闭对照相机或麦克风的访问。 如果你感兴趣，我们建议你阅读 [常见的设备限制页](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。

你还可以使用其他更复杂的设备限制。 如：

- 通过使用 [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list)限制可以在 "设置" 应用中查看的页面，允许用户仅访问他们需要调整的设置，例如更改其 Wi-Fi 连接。
- 使用 [展台模式](https://docs.microsoft.com/hololens/hololens-kiosk) 将向用户显示的 UI 限制为设备上的用户。 可以通过使用自定义起始页将网亭设置为显示单个应用程序或多个应用程序。 网亭还可以向不同用户提供不同的体验。
- [Windows 应用程序控制 (WDAC) ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) ，以使特定的应用程序或进程完全启动。

如果你想要了解设备管理或设备限制的其他方法，请执行下一步，并阅读我们的 [设备管理概述](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)。




