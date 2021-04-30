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
# <a name="maintain---cloud-connected-guide"></a><span data-ttu-id="014c0-104">维护-云连接指南</span><span class="sxs-lookup"><span data-stu-id="014c0-104">Maintain - Cloud connected Guide</span></span>

## <a name="updates"></a><span data-ttu-id="014c0-105">更新</span><span class="sxs-lookup"><span data-stu-id="014c0-105">Updates</span></span>

<span data-ttu-id="014c0-106">Microsoft 设计适用于企业的 Windows 更新以为 IT 管理员提供更多以 Windows 更新为中心的管理功能，例如对一组设备部署更新的功能，以及为安装更新而定义维护窗口的功能。</span><span class="sxs-lookup"><span data-stu-id="014c0-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="014c0-107">了解如何 [管理 HoloLens 更新](https://docs.microsoft.com/hololens/hololens-updates) ，包括计划的日期、计划的时间和在设备上设置活动时间，以便它在工作时间之外进行更新。</span><span class="sxs-lookup"><span data-stu-id="014c0-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="014c0-108">远程协助是 In-Box 应用程序，可以通过 Microsoft Store 应用进行更新。</span><span class="sxs-lookup"><span data-stu-id="014c0-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="014c0-109">对于通过 Microsoft Store 下载的所有应用程序，可以手动 [通过 Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 应用程序进行更新。</span><span class="sxs-lookup"><span data-stu-id="014c0-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="support-plan"></a><span data-ttu-id="014c0-110">支持计划</span><span class="sxs-lookup"><span data-stu-id="014c0-110">Support Plan</span></span>

<span data-ttu-id="014c0-111">支持计划是一个不错的做法。</span><span class="sxs-lookup"><span data-stu-id="014c0-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="014c0-112">在更新 HoloLens 设备上的注册过程时，让某人或组进行了培训，同时也对在你的组织内使用 HoloLens 设备进行一般使用非常有用。</span><span class="sxs-lookup"><span data-stu-id="014c0-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="014c0-113">为了使用户能够更快地解决其问题，我们建议以类似于此顺序的方式处理升级过程：</span><span class="sxs-lookup"><span data-stu-id="014c0-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="014c0-114">你的支持人员。</span><span class="sxs-lookup"><span data-stu-id="014c0-114">Your Support desk.</span></span>
2. <span data-ttu-id="014c0-115">HoloLens 专家团队</span><span class="sxs-lookup"><span data-stu-id="014c0-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="014c0-116">[HoloLens 文档](https://docs.microsoft.com/hololens/)  / [HoloLens 疑难解答文档](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="014c0-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="014c0-117">联系支持人员</span><span class="sxs-lookup"><span data-stu-id="014c0-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="development-plan"></a><span data-ttu-id="014c0-118">开发计划</span><span class="sxs-lookup"><span data-stu-id="014c0-118">Development Plan</span></span>

<span data-ttu-id="014c0-119">成功注册设备后，你现在已准备好将业务线应用 (LOB 应用) 部署到你的设备。</span><span class="sxs-lookup"><span data-stu-id="014c0-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="014c0-120">这些是为你的组织构建&#39;需求的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="014c0-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="014c0-121">如果你已经有了业务线应用，则&#39;[通过 MDM 部署你的应用](https://docs.microsoft.com/hololens/app-deploy-intune)。</span><span class="sxs-lookup"><span data-stu-id="014c0-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="014c0-122">如果&#39;d 首选其他方法，请查看 [HoloLens 2 的应用程序部署概述](https://docs.microsoft.com/hololens/app-deploy-overview) ，了解将 LOB 应用程序部署到设备的更多方法。</span><span class="sxs-lookup"><span data-stu-id="014c0-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="014c0-123">如果你&#39;ve 创建自己的 LOB 应用程序，或仍处于创建过程中，请查看我们的混合现实开发文档，以[开始设计和构建原型](https://docs.microsoft.com/windows/mixed-reality/design/design)，或了解有关[混合现实开发入门](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)的核心概念。</span><span class="sxs-lookup"><span data-stu-id="014c0-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="device-management"></a><span data-ttu-id="014c0-124">设备管理</span><span class="sxs-lookup"><span data-stu-id="014c0-124">Device Management</span></span> 

<span data-ttu-id="014c0-125">虽然本指南介绍了如何设置移动设备管理 (MDM) 不会将其应用到设备。</span><span class="sxs-lookup"><span data-stu-id="014c0-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="014c0-126">通过推送证书或使用各种设备限制来限制访问，可以使用设备管理来允许访问。</span><span class="sxs-lookup"><span data-stu-id="014c0-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="014c0-127">在许多情况下，设备可以具有连接限制，如蓝牙、VPN、USB，甚至关闭对相机或麦克风的访问。</span><span class="sxs-lookup"><span data-stu-id="014c0-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="014c0-128">如果有任何兴趣，我们建议你阅读 [常见的设备限制页](hololens-common-device-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="014c0-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="014c0-129">你还可以使用其他更复杂的设备限制。</span><span class="sxs-lookup"><span data-stu-id="014c0-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="014c0-130">如：</span><span class="sxs-lookup"><span data-stu-id="014c0-130">Such as:</span></span>

- <span data-ttu-id="014c0-131">通过使用 [SettingsPageVisibility](settings-uri-list.md)限制可以在 "设置" 应用中查看的页面，使用户只能访问他们需要进行调整的设置，例如更改其 Wi-Fi 连接。</span><span class="sxs-lookup"><span data-stu-id="014c0-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="014c0-132">使用 [展台模式](hololens-kiosk.md) 将向用户显示的 UI 限制为设备上的用户。</span><span class="sxs-lookup"><span data-stu-id="014c0-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="014c0-133">可以通过使用自定义起始页将网亭设置为显示单个应用程序或多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="014c0-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="014c0-134">网亭还可以向不同用户提供不同的体验。</span><span class="sxs-lookup"><span data-stu-id="014c0-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="014c0-135">[Windows 应用程序控制 (WDAC) ](windows-defender-application-control-wdac.md) ，以使特定的应用程序或进程完全启动。</span><span class="sxs-lookup"><span data-stu-id="014c0-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="014c0-136">如果你想要了解更多不同的设备管理方法或设备限制，请执行下一步，并阅读我们的设备管理概述。</span><span class="sxs-lookup"><span data-stu-id="014c0-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <a name="next-step"></a><span data-ttu-id="014c0-137">后续步骤</span><span class="sxs-lookup"><span data-stu-id="014c0-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="014c0-138">阅读 Csp 和设备管理概述</span><span class="sxs-lookup"><span data-stu-id="014c0-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)