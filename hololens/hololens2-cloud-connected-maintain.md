---
title: 部署指南–云连接的 HoloLens 2 大规模部署，具有远程协助-维护
description: 通过云连接网络来维护和支持 HoloLens 设备，随时保持最新状态。
keywords: HoloLens，管理，云连接，远程协助，AAD，Azure AD，MDM，移动设备管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308483"
---
# <a name="maintain---cloud-connected-guide"></a>维护-云连接指南

## <a name="updates"></a>更新

Microsoft 设计适用于企业的 Windows 更新以为 IT 管理员提供更多以 Windows 更新为中心的管理功能，例如对一组设备部署更新的功能，以及为安装更新而定义维护窗口的功能。

了解如何 [管理 HoloLens 更新](https://docs.microsoft.com/hololens/hololens-updates) ，包括计划的日期、计划的时间和在设备上设置活动时间，以便它在工作时间之外进行更新。

远程协助是 In-Box 应用程序，可以通过 Microsoft Store 应用进行更新。 对于通过 Microsoft Store 下载的所有应用程序，可以手动 [通过 Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 应用程序进行更新。

## <a name="support-plan"></a>支持计划

支持计划是一个不错的做法。 在更新 HoloLens 设备上的注册过程时，让某人或组进行了培训，同时也对在你的组织内使用 HoloLens 设备进行一般使用非常有用。 为了使用户能够更快地解决其问题，我们建议以类似于此顺序的方式处理升级过程：

1. 你的支持人员。
2. HoloLens 专家团队
3. [HoloLens 文档](https://docs.microsoft.com/hololens/)  / [HoloLens 疑难解答文档](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [联系支持人员](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>开发计划

成功注册设备后，你现在已准备好将业务线应用 (LOB 应用) 部署到你的设备。 这些是为你的组织构建&#39;需求的自定义应用。

如果你已经有了业务线应用，则&#39;[通过 MDM 部署你的应用](https://docs.microsoft.com/hololens/app-deploy-intune)。 如果&#39;d 首选其他方法，请查看 [HoloLens 2 的应用程序部署概述](https://docs.microsoft.com/hololens/app-deploy-overview) ，了解将 LOB 应用程序部署到设备的更多方法。

如果你&#39;ve 创建自己的 LOB 应用程序，或仍处于创建过程中，请查看我们的混合现实开发文档，以[开始设计和构建原型](https://docs.microsoft.com/windows/mixed-reality/design/design)，或了解有关[混合现实开发入门](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)的核心概念。

## <a name="device-management"></a>设备管理 

虽然本指南介绍了如何设置移动设备管理 (MDM) 不会将其应用到设备。 通过推送证书或使用各种设备限制来限制访问，可以使用设备管理来允许访问。 

在许多情况下，设备可以具有连接限制，如蓝牙、VPN、USB，甚至关闭对相机或麦克风的访问。 如果有任何兴趣，我们建议你阅读 [常见的设备限制页](hololens-common-device-restrictions.md)。

你还可以使用其他更复杂的设备限制。 如：

- 通过使用 [SettingsPageVisibility](settings-uri-list.md)限制可以在 "设置" 应用中查看的页面，使用户只能访问他们需要进行调整的设置，例如更改其 Wi-Fi 连接。
- 使用 [展台模式](hololens-kiosk.md) 将向用户显示的 UI 限制为设备上的用户。 可以通过使用自定义起始页将网亭设置为显示单个应用程序或多个应用程序。 网亭还可以向不同用户提供不同的体验。  
- [Windows 应用程序控制 (WDAC) ](windows-defender-application-control-wdac.md) ，以使特定的应用程序或进程完全启动。

如果你想要了解更多不同的设备管理方法或设备限制，请执行下一步，并阅读我们的设备管理概述。

## <a name="next-step"></a>后续步骤

> [!div class="nextstepaction"]
> [阅读 Csp 和设备管理概述](hololens-csp-policy-overview.md)