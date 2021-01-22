---
title: 部署指南 – 使用远程协助大规模部署云连接的 HoloLens 2 - 维护
description: 随时了解有关通过云连接网络维护和支持 HoloLens 设备的提示。
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
ms.openlocfilehash: bc34c4e41c5a6cee8f3f9a0a97407ee38d419bbc
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283893"
---
# <span data-ttu-id="a7b34-104">维护 - 云连接指南</span><span class="sxs-lookup"><span data-stu-id="a7b34-104">Maintain - Cloud connected Guide</span></span>

## <span data-ttu-id="a7b34-105">更新</span><span class="sxs-lookup"><span data-stu-id="a7b34-105">Updates</span></span>

<span data-ttu-id="a7b34-106">Microsoft 设计适用于企业的 Windows 更新以为 IT 管理员提供更多以 Windows 更新为中心的管理功能，例如对一组设备部署更新的功能，以及为安装更新而定义维护窗口的功能。</span><span class="sxs-lookup"><span data-stu-id="a7b34-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="a7b34-107">了解如何管理 [HoloLens](https://docs.microsoft.com/hololens/hololens-updates) 更新，包括计划天数、计划时间和在设备上设置使用时段，以便它将在工作时间之外更新。</span><span class="sxs-lookup"><span data-stu-id="a7b34-107">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates) including scheduled days, scheduled time, and setting active hours on the device so it will update outside of working hours.</span></span>

<span data-ttu-id="a7b34-108">远程协助是一In-Box应用，可通过 Microsoft Store 应用进行更新。</span><span class="sxs-lookup"><span data-stu-id="a7b34-108">Remote Assist is an In-Box app, and can be update through the Microsoft Store app.</span></span> <span data-ttu-id="a7b34-109">对于通过 Microsoft Store 下载的所有应用，可以通过 [Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 应用本身手动进行更新。</span><span class="sxs-lookup"><span data-stu-id="a7b34-109">For all apps that are downloaded through the Microsoft Store they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <span data-ttu-id="a7b34-110">支持计划</span><span class="sxs-lookup"><span data-stu-id="a7b34-110">Support Plan</span></span>

<span data-ttu-id="a7b34-111">支持计划是一项非常好的计划。</span><span class="sxs-lookup"><span data-stu-id="a7b34-111">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="a7b34-112">让某人或组接受有关 HoloLens 设备上注册过程的疑难解答培训，以及组织中 HoloLens 设备的常规使用非常有用。</span><span class="sxs-lookup"><span data-stu-id="a7b34-112">Having someone, or a group trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="a7b34-113">为了允许用户更快地解决其问题，我们建议按照与此顺序类似的方式处理你的升级过程：</span><span class="sxs-lookup"><span data-stu-id="a7b34-113">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="a7b34-114">支持人员。</span><span class="sxs-lookup"><span data-stu-id="a7b34-114">Your Support desk.</span></span>
2. <span data-ttu-id="a7b34-115">HoloLens 专家团队</span><span class="sxs-lookup"><span data-stu-id="a7b34-115">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="a7b34-116">[HoloLens 文档](https://docs.microsoft.com/hololens/)  / [HoloLens 疑难解答文档](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="a7b34-116">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="a7b34-117">联系支持人员</span><span class="sxs-lookup"><span data-stu-id="a7b34-117">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <span data-ttu-id="a7b34-118">开发计划</span><span class="sxs-lookup"><span data-stu-id="a7b34-118">Development Plan</span></span>

<span data-ttu-id="a7b34-119">在成功注册设备后，你现在准备好将业务线应用部署到 (LOB 应用) 设备。</span><span class="sxs-lookup"><span data-stu-id="a7b34-119">With your device successfully enrolled you are now prepared to deploy Line of Business apps (LOB apps) to your devices.</span></span> <span data-ttu-id="a7b34-120">这些是专为组织构建的自定义&#39;需求。</span><span class="sxs-lookup"><span data-stu-id="a7b34-120">These are custom apps built for your organization&#39;s needs.</span></span>

<span data-ttu-id="a7b34-121">如果你已有业务线应用，&#39;通过 [MDM 部署应用](https://docs.microsoft.com/hololens/app-deploy-intune)。</span><span class="sxs-lookup"><span data-stu-id="a7b34-121">If you already have a line of business app then you&#39;re ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="a7b34-122">如果你&#39;其他方法，请查看 [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) 的应用程序部署概述，以了解有关将 LOB 应用部署到设备的更多方法。</span><span class="sxs-lookup"><span data-stu-id="a7b34-122">If you&#39;d prefer a different method then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="a7b34-123">如果你&#39;创建自己的 LOB 应用或仍在创建中，请查看我们的混合现实开发文档以开始设计和制作原型，或了解开始混合现实开发的核心[](https://docs.microsoft.com/windows/mixed-reality/design/design)概念。 [](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="a7b34-123">If you&#39;ve yet to create your own LOB app or are still in the process of creation then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <span data-ttu-id="a7b34-124">设备管理</span><span class="sxs-lookup"><span data-stu-id="a7b34-124">Device Management</span></span> 

<span data-ttu-id="a7b34-125">虽然本指南讨论了在 MDM (移动设备管理) ，但并未将设备限制或策略应用于设备。</span><span class="sxs-lookup"><span data-stu-id="a7b34-125">While this guide talked about setting up Mobile Device Management (MDM) it wasn't employed to apply device restrictions or policies were applied to devices.</span></span> <span data-ttu-id="a7b34-126">设备管理可用于通过推送证书来允许访问，或者通过各种设备限制来限制访问。</span><span class="sxs-lookup"><span data-stu-id="a7b34-126">Device management can be used to both to allow access by pushing certificates, or restrict access with a variety of device restrictions.</span></span> 

<span data-ttu-id="a7b34-127">在许多情况下，设备可能会具有连接限制，例如Bluetooth、VPN、USB 甚至关闭对相机或麦克风的访问。</span><span class="sxs-lookup"><span data-stu-id="a7b34-127">In many cases devices can have connectivity restrictions such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="a7b34-128">If any of these interests you then we encourage you to read our [common device restrictions page.](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="a7b34-128">If any of these interests you then we encourage you to read our [common device restrictions page](hololens-common-device-restrictions.md).</span></span>

<span data-ttu-id="a7b34-129">可以使用其他更复杂的设备限制。</span><span class="sxs-lookup"><span data-stu-id="a7b34-129">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="a7b34-130">例如：</span><span class="sxs-lookup"><span data-stu-id="a7b34-130">Such as:</span></span>

- <span data-ttu-id="a7b34-131">使用 [SettingsPageVisibility](settings-uri-list.md)限制可在"设置"应用中查看的页面，从而允许用户仅访问需要调整的设置，例如更改其Wi-Fi连接。</span><span class="sxs-lookup"><span data-stu-id="a7b34-131">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](settings-uri-list.md), allowing users to only access the settings they need to adjust such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="a7b34-132">使用 [展](hololens-kiosk.md) 台模式限制向设备上用户呈现的 UI。</span><span class="sxs-lookup"><span data-stu-id="a7b34-132">Use [Kiosk mode](hololens-kiosk.md) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="a7b34-133">你可以将展台设置为显示单个应用，或使用自定义起始页显示多个应用。</span><span class="sxs-lookup"><span data-stu-id="a7b34-133">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="a7b34-134">网亭还可以向不同的用户提供不同的体验。</span><span class="sxs-lookup"><span data-stu-id="a7b34-134">Kiosks can also present different experiences to different users.</span></span>  
- <span data-ttu-id="a7b34-135">[Windows 应用程序控制 (WDAC) ](windows-defender-application-control-wdac.md) 来阻止特定应用或进程完全启动。</span><span class="sxs-lookup"><span data-stu-id="a7b34-135">[Windows Application Control (WDAC)](windows-defender-application-control-wdac.md) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="a7b34-136">如果你想要了解有关设备管理或设备限制的更多不同方法的信息，请执行下一步并阅读我们的设备管理概述。</span><span class="sxs-lookup"><span data-stu-id="a7b34-136">If you'd like to learn about more different methods of device management or device restrictions, then take the next step and read our Device Management Overview.</span></span>

## <span data-ttu-id="a7b34-137">下一步</span><span class="sxs-lookup"><span data-stu-id="a7b34-137">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a7b34-138">阅读 CSP 和设备管理概述</span><span class="sxs-lookup"><span data-stu-id="a7b34-138">Read the CSPs and Device Management Overview</span></span>](hololens-csp-policy-overview.md)