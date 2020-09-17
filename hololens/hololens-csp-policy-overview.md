---
title: 配置 Csp 和设备管理概述
description: 如何配置 Csp、策略和设备管理。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: lavinds
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4c31f7f92116031535a2dc2860e3f048a2311a39
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016764"
---
# <span data-ttu-id="98e48-103">配置 Csp 和设备管理概述</span><span class="sxs-lookup"><span data-stu-id="98e48-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="98e48-104">IT 管理员可以在 HoloLens 2 上定义和实施策略设置。</span><span class="sxs-lookup"><span data-stu-id="98e48-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="98e48-105">你使用的配置设置将基于部署方案而异，公司设备将为 IT 提供最广泛的控制权。</span><span class="sxs-lookup"><span data-stu-id="98e48-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="98e48-106">在 Windows 10 中，配置服务提供程序 (CSP) s 是用于读取、设置、修改或删除设备上的配置设置的接口。</span><span class="sxs-lookup"><span data-stu-id="98e48-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="98e48-107">这些设置将映射到注册表项或文件。</span><span class="sxs-lookup"><span data-stu-id="98e48-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="98e48-108">某些配置服务提供程序支持 WAP 格式、某些支持 SyncML 以及某些支持。</span><span class="sxs-lookup"><span data-stu-id="98e48-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span> 

<span data-ttu-id="98e48-109">有关 Windows 10 全息版设备管理 Csp 的详细信息，请参阅 [HoloLens 设备中受支持的 csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)的完整列表。</span><span class="sxs-lookup"><span data-stu-id="98e48-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span> <span data-ttu-id="98e48-110">IT 管理员还可以在设备上管理策略 CSP，请参阅 [HoloLens 2 支持的策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)的完整列表。</span><span class="sxs-lookup"><span data-stu-id="98e48-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <span data-ttu-id="98e48-111">配置方法</span><span class="sxs-lookup"><span data-stu-id="98e48-111">Configuration methods</span></span>

### <span data-ttu-id="98e48-112">配置 MDM</span><span class="sxs-lookup"><span data-stu-id="98e48-112">Configure with MDM</span></span>
<span data-ttu-id="98e48-113">可在 MDM 系统中注册的任何个人设备或公司设备上轻松管理 Csp 和策略。</span><span class="sxs-lookup"><span data-stu-id="98e48-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="98e48-114">在你的 MDM 解决方案中注册设备后，你将能够使用设备配置管理该设备或设备集。</span><span class="sxs-lookup"><span data-stu-id="98e48-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="98e48-115">了解有关如何 [通过 MDM 管理 HoloLens 设备](hololens-mdm-configure.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="98e48-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <span data-ttu-id="98e48-116">通过预配程序包进行配置</span><span class="sxs-lookup"><span data-stu-id="98e48-116">Configure with Provisioning Packages</span></span>
<span data-ttu-id="98e48-117">HoloLens 2 还支持通过自定义预配程序包为 HoloLens 2 设备设置有限的 CSP 配置集。</span><span class="sxs-lookup"><span data-stu-id="98e48-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="98e48-118">预配程序包通常可用于非 MDM 托管设备，并且需要手动应用到每个设备。</span><span class="sxs-lookup"><span data-stu-id="98e48-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="98e48-119">阅读有关生成 [适用于 HoloLens 的自定义预配包的](https://docs.microsoft.com/hololens/hololens-provisioning)信息。</span><span class="sxs-lookup"><span data-stu-id="98e48-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> 

## <span data-ttu-id="98e48-120">配置</span><span class="sxs-lookup"><span data-stu-id="98e48-120">Configurations</span></span> 

### <span data-ttu-id="98e48-121">常见设备限制</span><span class="sxs-lookup"><span data-stu-id="98e48-121">Common device restrictions</span></span>
<span data-ttu-id="98e48-122">某些设备限制既简单又可禁用设备的功能或连接。</span><span class="sxs-lookup"><span data-stu-id="98e48-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="98e48-123">若要了解这些信息，请阅读有关[常见设备限制的](hololens-common-device-restrictions.md)详细信息。</span><span class="sxs-lookup"><span data-stu-id="98e48-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <span data-ttu-id="98e48-124">展台模式</span><span class="sxs-lookup"><span data-stu-id="98e48-124">Kiosk modes</span></span>
<span data-ttu-id="98e48-125">使用展台模式控制哪些身份对默认情况有权访问哪些应用。</span><span class="sxs-lookup"><span data-stu-id="98e48-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="98e48-126">展台可用于单个应用或多个应用 UI 体验。</span><span class="sxs-lookup"><span data-stu-id="98e48-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="98e48-127">展台配置范围从单个应用到使用该设备的任何人，到不同组的不同选择应用。</span><span class="sxs-lookup"><span data-stu-id="98e48-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="98e48-128">这不会阻止 "允许的应用" 启动其他应用，也不是有意的。</span><span class="sxs-lookup"><span data-stu-id="98e48-128">This does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="98e48-129">了解 [有关展台模式以及如何使用它们](hololens-kiosk.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="98e48-129">To learn more [start reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <span data-ttu-id="98e48-130">设置页面可见性</span><span class="sxs-lookup"><span data-stu-id="98e48-130">Settings Page Visibility</span></span>
<span data-ttu-id="98e48-131">在默认情况下，使用 "设置" 应用策略控制哪些标识有权访问设置。</span><span class="sxs-lookup"><span data-stu-id="98e48-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="98e48-132">通过此策略，可将 "设置" 应用配置为仅显示选择页面，或 "隐藏所有选定页面"。</span><span class="sxs-lookup"><span data-stu-id="98e48-132">With this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="98e48-133">了解[如何配置可用的页面](settings-uri-list.md)。</span><span class="sxs-lookup"><span data-stu-id="98e48-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="98e48-134">此功能目前仅在 [Windows 预览体验计划内部版本](hololens-insider.md)中 avalible。</span><span class="sxs-lookup"><span data-stu-id="98e48-134">This feature is currently only avalible in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="98e48-135">请确保要使用此 for 的设备位于 build 19041.1349 +。</span><span class="sxs-lookup"><span data-stu-id="98e48-135">Please ensure devices you intend to use this for are on build 19041.1349+.</span></span>

### <span data-ttu-id="98e48-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="98e48-136">WDAC</span></span>
<span data-ttu-id="98e48-137">使用 WDAC 配置来控制允许/禁止启动哪些应用/进程，无论系统是否处于展台模式。</span><span class="sxs-lookup"><span data-stu-id="98e48-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="98e48-138">请参阅我们对 WDAC 的概述。</span><span class="sxs-lookup"><span data-stu-id="98e48-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
