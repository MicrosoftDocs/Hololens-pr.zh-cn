---
title: 部署指南 - 使用 HoloLens 2 大规模部署云Remote Assist - 维护
description: 随时了解有关通过云连接的网络维护和HoloLens设备的技巧。
keywords: HoloLens、管理、云连接、Remote Assist、AAD、Azure AD、MDM、移动设备管理
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
ms.openlocfilehash: 941de296d59713c098718b16431fa793bd1b60e6
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032116"
---
# <a name="maintain---cloud-connected-guide"></a>维护 - 云连接指南

## <a name="updates"></a>更新

Microsoft 设计适用于企业的 Windows 更新以为 IT 管理员提供更多以 Windows 更新为中心的管理功能，例如对一组设备部署更新的功能，以及为安装更新而定义维护窗口的功能。

了解如何管理HoloLens更新，[包括](/hololens/hololens-updates)计划天数、计划时间，以及设置设备的活动小时数，以便设备在工作时间之外进行更新。

Remote Assist是一In-Box应用，可以通过 Microsoft Store 应用进行更新。 对于通过应用程序下载的所有应用Microsoft Store可以通过应用本身[手动Microsoft Store](/hololens/holographic-store-apps#update-apps)更新这些应用。

## <a name="support-plan"></a>支持计划

制定支持计划是一项极佳的计划。 让某人或某个组在设备上对注册过程进行故障排除HoloLens以及组织中对 HoloLens 设备的常规使用非常有用。 为了使用户能够更快地解决其问题，我们建议以类似于此顺序的方式处理升级过程：

1. 支持人员。
2. 你的 HoloLens 专家团队
3. [HoloLens Docs](/hololens/)  / [HoloLens故障排除文档](/hololens/hololens-troubleshooting)
4. [联系支持人员](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a>开发计划

成功注册设备后，现在可以将业务线应用部署到 (LOB) 设备。 这些自定义应用是组织根据&#39;构建的。

如果已有业务线应用，&#39;准备通过 [MDM 部署应用](/hololens/app-deploy-intune)。 如果&#39;其他方法，请查看应用程序部署概述HoloLens 2了解将 LOB[](/hololens/app-deploy-overview)应用部署到设备的更多方法。

如果你&#39;创建自己的 LOB 应用或仍处于创建过程中，请查看我们的混合现实开发文档，开始设计和原型制作，或学习核心概念以开始使用[](/windows/mixed-reality/design/design)混合现实[开发](/windows/mixed-reality/discover/get-started-with-mr)。

## <a name="device-management"></a>设备管理 

虽然本指南讨论了如何设置移动设备管理 (MDM) 但并未应用设备限制或将策略应用于设备。 设备管理可用于通过推送证书来允许访问，或者通过各种设备限制限制访问。 

在许多情况下，设备可能会受到连接限制，例如蓝牙 VPN、USB，甚至关闭对相机或麦克风的访问。 如果有任何这些兴趣，建议阅读常见的 [设备限制页](hololens-common-device-restrictions.md)。

可以使用其他更复杂的设备限制。 如：

- 通过使用[SettingsPageVisibility](settings-uri-list.md)限制可在 设置 应用中查看的页面，允许用户仅访问需要调整的设置，例如更改其Wi-Fi连接。
- 使用 [展台](hololens-kiosk.md) 模式限制向设备上用户呈现的 UI。 可以将展台设置为显示单个应用，或者使用自定义起始页显示多个应用。 展台还可以向不同的用户提供不同的体验。  
- [Windows应用程序控制 (WDAC) ，](windows-defender-application-control-wdac.md)使特定应用或进程完全启动。

若要了解设备管理或设备限制的更多不同方法，请执行下一步并阅读我们的设备管理概述。

## <a name="next-step"></a>后续步骤

> [!div class="nextstepaction"]
> [阅读 CSP 和设备管理概述](hololens-csp-policy-overview.md)