---
title: 部署指南 – 使用远程协助大规模部署云连接的 HoloLens 2 - 维护
description: 通过云连接网络维护 HoloLens 设备的提示
keywords: HoloLens， 管理， 云连接， 远程协助， AAD， Azure AD， MDM， 移动设备管理
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
ms.openlocfilehash: 8117c73516d2775ec67f37bad524bcf377ece2e5
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252693"
---
# 维护 - 云连接指南

## 更新

Microsoft 设计适用于企业的 Windows 更新以为 IT 管理员提供更多以 Windows 更新为中心的管理功能，例如对一组设备部署更新的功能，以及为安装更新而定义维护窗口的功能。

了解如何管理 [HoloLens](https://docs.microsoft.com/hololens/hololens-updates) 更新，包括计划天数、计划时间和在设备上设置使用时段，以便它将在工作时间之外更新。

远程协助是一In-Box应用，可通过 Microsoft Store 应用进行更新。 对于通过 Microsoft Store 下载的所有应用，可以通过 [Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 应用本身手动进行更新。

## 支持计划

支持计划是一项非常好的计划。 让某人或组接受有关 HoloLens 设备上注册过程的疑难解答培训，以及组织中 HoloLens 设备的常规使用非常有用。 为了允许用户更快地解决其问题，我们建议按照与此顺序类似的方式处理你的升级过程：

1. 支持人员。
2. HoloLens 专家团队
3. [HoloLens 文档](https://docs.microsoft.com/hololens/)  / [HoloLens 疑难解答文档](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [联系支持人员](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## 开发计划

在设备成功注册后，你现在已准备好将业务线应用部署到 (LOB 应用) 设备。 这些是专为组织构建的自定义&#39;需求。

如果你已有业务线应用，&#39;通过 [MDM 部署应用](https://docs.microsoft.com/hololens/app-deploy-intune)。 如果你&#39;其他方法，请查看 [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) 的应用程序部署概述，以了解有关将 LOB 应用部署到设备的更多方法。

如果你&#39;创建自己的 LOB 应用或仍在创建中，请查看我们的混合现实开发文档以开始设计和制作原型，或了解开始混合现实开发的核心[](https://docs.microsoft.com/windows/mixed-reality/design/design)概念。 [](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)

## 设备管理 

虽然本指南讨论了在 MDM (移动设备管理) ，但并未将设备限制或策略应用于设备。 设备管理可用于通过推送证书来允许访问，或者通过各种设备限制来限制访问。 

在许多情况下，设备可能会具有连接限制，例如Bluetooth、VPN、USB 甚至关闭对相机或麦克风的访问。 If any of these interests you then we encourage you to read our [common device restrictions page.](hololens-common-device-restrictions.md)

可以使用其他更复杂的设备限制。 例如：

- 使用 [SettingsPageVisibility](settings-uri-list.md)限制可在"设置"应用中查看的页面，从而允许用户仅访问需要调整的设置，例如更改其Wi-Fi连接。
- 使用 [展](hololens-kiosk.md) 台模式限制向设备上用户呈现的 UI。 你可以将展台设置为显示单个应用，或使用自定义起始页显示多个应用。 网亭还可以向不同的用户提供不同的体验。  
- [Windows 应用程序控制 (WDAC) ](windows-defender-application-control-wdac.md) 来阻止特定应用或进程完全启动。

如果你想要了解有关设备管理或设备限制的更多不同方法的信息，请执行下一步并阅读我们的设备管理概述。

## 下一步

> [!div class="nextstepaction"]
> [阅读 CSP 和设备管理概述](hololens-csp-policy-overview.md)