---
title: 部署指南–与云连接的 HoloLens 2 部署，并通过远程协助保持部署
description: 通过云连接网络维护 HoloLens 设备的提示
keywords: HoloLens、管理、云连接、远程协助、AAD、Azure AD、MDM、移动设备管理
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
ms.openlocfilehash: beee64159415c0635812463f81c0b5565e44e4a8
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196266"
---
# 维护-云连接指南

## 更新

Microsoft 设计适用于企业的 Windows 更新以为 IT 管理员提供更多以 Windows 更新为中心的管理功能，例如对一组设备部署更新的功能，以及为安装更新而定义维护窗口的功能。

了解如何 [管理 HoloLens 更新](https://docs.microsoft.com/hololens/hololens-updates) ，包括计划的天数、计划时间和在设备上设置活动工时，以便它在工作时间之外更新。

远程协助是 In-Box 应用，可通过 Microsoft Store 应用进行更新。 对于通过 Microsoft Store 下载的所有应用，可 [通过 Microsoft store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 应用本身手动更新这些应用。

## 支持计划

支持计划是一个很好的做法。 对 HoloLens 设备上的注册过程进行故障排除的人员或组进行过培训，同时也非常有用。 为了让你的用户能够更快地解决问题，我们建议你通过类似方式处理升级过程：

1. 您的支持台。
2. 您的 HoloLens 专家团队
3. [HoloLens 文档](https://docs.microsoft.com/hololens/)  / [HoloLens 疑难解答文档](https://docs.microsoft.com/hololens/hololens-troubleshooting)
4. [联系支持人员](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## 开发计划

已成功注册你的设备后，你现在已准备好在你的设备上部署 (LOB 应用的业务线应用) 。 这些是为您的组织创建的自定义应用&#39;的需要。

如果你已有一条业务应用程序，则&#39;准备 [通过 MDM 部署你的应用](https://docs.microsoft.com/hololens/app-deploy-intune)。 如果&#39;d 希望使用其他方法，请查看 [HoloLens 2 的应用程序部署概述](https://docs.microsoft.com/hololens/app-deploy-overview) ，了解将 LOB 应用部署到你的设备的更多方法。

如果你&#39;仍在创建你自己的 LOB 应用，或者仍在创建过程中，请查看我们的混合现实开发文档，[开始设计和创建原型](https://docs.microsoft.com/windows/mixed-reality/design/design)或了解开始[使用混合现实开发](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)的核心概念。

## 设备管理 

本指南讨论了如何设置移动设备管理 (MDM) 它不用于应用设备限制或策略应用于设备。 通过推送证书或使用各种设备限制限制访问，设备管理既可用于允许访问。 

在许多情况下，设备可以具有连接限制，例如，蓝牙、VPN、USB 甚至关闭对相机或麦克风的访问。 如果有任何兴趣，我们建议你阅读 " [常见设备限制" 页面](hololens-common-device-restrictions.md)。

你可以使用其他更复杂的设备限制。 例如：

- 通过使用 [SettingsPageVisibility](settings-uri-list.md)限制可在 "设置" 应用中查看的页面，从而允许用户仅访问他们需要调整的设置，例如更改其 Wi-Fi 连接。
- 使用 [展台模式](hololens-kiosk.md) 限制在设备上向用户显示的 UI。 你可以将展台设置为显示单个应用，或使用自定义起始页显示多个应用。 网亭还可以向不同用户提供不同的体验。  
- [Windows 应用程序控件 (WDAC) ](windows-defender-application-control-wdac.md) ，以使特定应用或进程完全启动。

如果你想要了解更多不同的设备管理方法或设备限制，请执行下一步操作，并阅读我们的设备管理概述。

## 下一步

> [!div class="nextstepaction"]
> [阅读 Csp 和设备管理概述](hololens-csp-policy-overview.md)