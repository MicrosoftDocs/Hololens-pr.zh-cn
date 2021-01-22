---
title: 管理 HoloLens 2 的自定义应用
description: 了解如何使用 Device Portal 和 Visual Studio 在 HoloLens 2 设备上安装、卸载和旁加载自定义全息Visual Studio。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 01/21/2021
manager: yannisle
keywords: hololens， hololens 2， 旁加载， 旁加载， 旁加载， 存储， uwp， 应用， 安装
ms.prod: hololens
ms.sitesec: library
author: joyjaz
ms.author: v-jjaswinski
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens 2
ms.openlocfilehash: e3ae180697c889a426108992ba345dc23b96505c
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296996"
---
# <span data-ttu-id="51336-104">管理 HoloLens 2 的自定义应用</span><span class="sxs-lookup"><span data-stu-id="51336-104">Manage custom apps for HoloLens 2</span></span>

<span data-ttu-id="51336-105">HoloLens 支持 Microsoft Store 中的许多现有应用程序，以及专为 HoloLens 构建的新应用。</span><span class="sxs-lookup"><span data-stu-id="51336-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> 

<span data-ttu-id="51336-106">有关应用商店应用详细信息，请参阅使用应用商店 [管理应用](holographic-store-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="51336-106">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51336-107">对于企业部署，我们不建议启用开发人员模式，这两种方法都使用开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="51336-107">For enterprise deployments, we don't recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="51336-108">如果你对安全的应用部署方法感兴趣，请查看我们的 [应用管理：概述](app-deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="51336-108">If you're interested in a secure app deployment method, please review our [App Management: Overview](app-deploy-overview.md).</span></span>

<span data-ttu-id="51336-109">如果你正在寻找适用于 HoloLens 2 设备的应用安装的开发人员方法，请参阅：</span><span class="sxs-lookup"><span data-stu-id="51336-109">If you're looking for either developer method of app installation for HoloLens 2 devices, refer to:</span></span>
- [<span data-ttu-id="51336-110">Device Portal：安装应用</span><span class="sxs-lookup"><span data-stu-id="51336-110">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
- [<span data-ttu-id="51336-111">使用 Visual Studio 部署和调试应用</span><span class="sxs-lookup"><span data-stu-id="51336-111">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

<span data-ttu-id="51336-112">如果你想要 [在](holographic-custom-apps.md) HoloLens 第一代 (部署自定义应用，请参阅我们的) 。</span><span class="sxs-lookup"><span data-stu-id="51336-112">See our [guide](holographic-custom-apps.md) if you'd like to deploy custom apps on HoloLens (1st gen).</span></span>