---
title: 配置 Csp 和设备管理概述
description: 了解如何使用移动设备管理和预配包配置 Csp、策略和设备管理。
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
ms.openlocfilehash: 60e73a9a70a70c5c583edc73a0add2f0f502ef80
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308470"
---
# <a name="configure-csps-and-device-management-overview"></a><span data-ttu-id="2f711-103">配置 Csp 和设备管理概述</span><span class="sxs-lookup"><span data-stu-id="2f711-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="2f711-104">IT 管理员可以在 HoloLens 2 上定义和实施策略设置。</span><span class="sxs-lookup"><span data-stu-id="2f711-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="2f711-105">你使用的配置设置将基于部署方案而异，公司设备将为 IT 提供最广泛的控制权。</span><span class="sxs-lookup"><span data-stu-id="2f711-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="2f711-106">在 Windows 10 中，配置服务提供程序 (CSP) s 是用于读取、设置、修改或删除设备上的配置设置的接口。</span><span class="sxs-lookup"><span data-stu-id="2f711-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="2f711-107">这些设置将映射到注册表项或文件。</span><span class="sxs-lookup"><span data-stu-id="2f711-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="2f711-108">某些配置服务提供程序支持 WAP 格式，某些支持 SyncML，一些支持 SyncML。</span><span class="sxs-lookup"><span data-stu-id="2f711-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="2f711-109">有关 Windows 10 全息版设备管理 Csp 的详细信息，请参阅 [HoloLens 设备中支持的 csp](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)的完整列表。</span><span class="sxs-lookup"><span data-stu-id="2f711-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="2f711-110">IT 管理员还可以在设备上管理策略 CSP，请参阅 [HoloLens 2 支持的策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)的完整列表。</span><span class="sxs-lookup"><span data-stu-id="2f711-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <a name="configuration-methods"></a><span data-ttu-id="2f711-111">配置方法</span><span class="sxs-lookup"><span data-stu-id="2f711-111">Configuration methods</span></span>

### <a name="configure-with-mdm"></a><span data-ttu-id="2f711-112">配置 MDM</span><span class="sxs-lookup"><span data-stu-id="2f711-112">Configure with MDM</span></span>

<span data-ttu-id="2f711-113">在 MDM 系统中注册的任何个人或公司设备上都可以轻松管理 Csp 和策略。</span><span class="sxs-lookup"><span data-stu-id="2f711-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="2f711-114">在 MDM 解决方案中注册设备后，你将能够使用设备配置来管理该设备或设备集。</span><span class="sxs-lookup"><span data-stu-id="2f711-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="2f711-115">了解有关如何 [通过 MDM 管理 HoloLens 设备](hololens-mdm-configure.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2f711-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <a name="configure-with-provisioning-packages"></a><span data-ttu-id="2f711-116">配置预配包</span><span class="sxs-lookup"><span data-stu-id="2f711-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="2f711-117">HoloLens 2 还支持通过自定义预配包为 HoloLens 2 设备设置有限的 CSP 配置集。</span><span class="sxs-lookup"><span data-stu-id="2f711-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="2f711-118">预配包通常用于非 MDM 托管设备，需要手动应用于每个设备。</span><span class="sxs-lookup"><span data-stu-id="2f711-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="2f711-119">阅读有关为 HoloLens 构建自定义 [设置包](https://docs.microsoft.com/hololens/hololens-provisioning)的信息。</span><span class="sxs-lookup"><span data-stu-id="2f711-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <a name="configurations"></a><span data-ttu-id="2f711-120">配置</span><span class="sxs-lookup"><span data-stu-id="2f711-120">Configurations</span></span>

### <a name="common-device-restrictions"></a><span data-ttu-id="2f711-121">常见设备限制</span><span class="sxs-lookup"><span data-stu-id="2f711-121">Common device restrictions</span></span>

<span data-ttu-id="2f711-122">某些设备限制非常简单，禁用了设备或与设备的连接。</span><span class="sxs-lookup"><span data-stu-id="2f711-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="2f711-123">若要了解相关信息，请阅读有关[常见设备限制的](hololens-common-device-restrictions.md)详细信息。</span><span class="sxs-lookup"><span data-stu-id="2f711-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <a name="kiosk-modes"></a><span data-ttu-id="2f711-124">展台模式</span><span class="sxs-lookup"><span data-stu-id="2f711-124">Kiosk modes</span></span>

<span data-ttu-id="2f711-125">使用展台模式来控制默认情况下哪些标识有权访问哪些应用。</span><span class="sxs-lookup"><span data-stu-id="2f711-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="2f711-126">网亭可用于单个应用程序或多个应用程序 UI 体验。</span><span class="sxs-lookup"><span data-stu-id="2f711-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="2f711-127">展台配置范围是从使用设备的任何人的单个应用到不同组的不同应用选择。</span><span class="sxs-lookup"><span data-stu-id="2f711-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="2f711-128">展台模式不会阻止 "允许的应用" 启动其他应用程序，并且不会出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="2f711-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="2f711-129">[阅读有关展台模式以及如何使用它们](hololens-kiosk.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2f711-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <a name="settings-page-visibility"></a><span data-ttu-id="2f711-130">设置页面可见性</span><span class="sxs-lookup"><span data-stu-id="2f711-130">Settings Page Visibility</span></span>

<span data-ttu-id="2f711-131">使用 "设置" 应用策略来控制默认情况下哪些标识有权访问设置。</span><span class="sxs-lookup"><span data-stu-id="2f711-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="2f711-132">使用此策略时，可以将设置应用配置为仅显示选定页面，或隐藏所有选定页面。</span><span class="sxs-lookup"><span data-stu-id="2f711-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="2f711-133">[阅读有关如何配置可用页面的信息](settings-uri-list.md)。</span><span class="sxs-lookup"><span data-stu-id="2f711-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="2f711-134">此功能目前仅适用于 [Windows 有问必答版本](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="2f711-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="2f711-135">确保要为其使用此功能的设备在 build 19041.1349 + 上。</span><span class="sxs-lookup"><span data-stu-id="2f711-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <a name="wdac"></a><span data-ttu-id="2f711-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="2f711-136">WDAC</span></span>

<span data-ttu-id="2f711-137">使用 WDAC 配置来控制允许或禁止启动哪些应用/进程，而不管系统是否处于展台模式。</span><span class="sxs-lookup"><span data-stu-id="2f711-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="2f711-138">请参阅有关 WDAC 的概述。</span><span class="sxs-lookup"><span data-stu-id="2f711-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
