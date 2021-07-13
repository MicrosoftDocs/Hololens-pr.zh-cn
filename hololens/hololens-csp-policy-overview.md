---
title: 配置 CSP 和设备管理概述
description: 了解如何使用 Mobile 设备管理和预配包配置 CSP、策略和设备管理。
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
ms.openlocfilehash: b312f9d20c9a75c5e4c1906c4ec55f42fda977f6
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640451"
---
# <a name="configure-csps-and-device-management-overview"></a><span data-ttu-id="b599e-103">配置 CSP 和设备管理概述</span><span class="sxs-lookup"><span data-stu-id="b599e-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="b599e-104">IT 管理员可以在应用程序上定义和实现HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="b599e-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="b599e-105">你使用的配置设置将基于部署方案而异，公司设备将为 IT 提供最广泛的控制权。</span><span class="sxs-lookup"><span data-stu-id="b599e-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="b599e-106">在 Windows 10中，配置服务提供商 (CSP) 是一个接口，用于读取、设置、修改或删除设备上的配置设置。</span><span class="sxs-lookup"><span data-stu-id="b599e-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="b599e-107">这些设置映射到注册表项或文件。</span><span class="sxs-lookup"><span data-stu-id="b599e-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="b599e-108">某些配置服务提供商支持 WAP 格式，一些支持 SyncML，有些支持这两种格式。</span><span class="sxs-lookup"><span data-stu-id="b599e-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="b599e-109">有关管理WINDOWS 10 全息版的 CSP，请参阅设备中支持的HOLOLENS[列表](/windows/client-management/mdm/configuration-service-provider-reference#hololens)。</span><span class="sxs-lookup"><span data-stu-id="b599e-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="b599e-110">IT 管理员还可以在设备上管理策略 CSP，请参阅管理员支持的策略[CSP 的完整HoloLens 2。](/windows/client-management/mdm/policy-csps-supported-by-hololens2)</span><span class="sxs-lookup"><span data-stu-id="b599e-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <a name="configuration-methods"></a><span data-ttu-id="b599e-111">配置方法</span><span class="sxs-lookup"><span data-stu-id="b599e-111">Configuration methods</span></span>

### <a name="configure-with-mdm"></a><span data-ttu-id="b599e-112">使用 MDM 进行配置</span><span class="sxs-lookup"><span data-stu-id="b599e-112">Configure with MDM</span></span>

<span data-ttu-id="b599e-113">可以在 MDM 系统中注册的任何个人或公司设备上轻松管理 CSP 和策略。</span><span class="sxs-lookup"><span data-stu-id="b599e-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="b599e-114">在 MDM 解决方案中注册设备后，你将能够使用设备配置管理该设备或设备集。</span><span class="sxs-lookup"><span data-stu-id="b599e-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="b599e-115">详细了解如何通过[MDM HoloLens设备](hololens-mdm-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="b599e-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <a name="configure-with-provisioning-packages"></a><span data-ttu-id="b599e-116">使用预配包进行配置</span><span class="sxs-lookup"><span data-stu-id="b599e-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="b599e-117">HoloLens 2还支持通过自定义预配包为HoloLens 2设备设置一组有限的 CSP 配置。</span><span class="sxs-lookup"><span data-stu-id="b599e-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="b599e-118">预配包通常用于非 MDM 托管设备，需要手动应用于每个设备。</span><span class="sxs-lookup"><span data-stu-id="b599e-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="b599e-119">阅读有关为 HoloLens[生成自定义预配包的信息](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="b599e-119">Read information on building custom [Provisioning Packages for HoloLens](hololens-provisioning.md).</span></span>

## <a name="configurations"></a><span data-ttu-id="b599e-120">配置</span><span class="sxs-lookup"><span data-stu-id="b599e-120">Configurations</span></span>

### <a name="common-device-restrictions"></a><span data-ttu-id="b599e-121">通用设备限制</span><span class="sxs-lookup"><span data-stu-id="b599e-121">Common device restrictions</span></span>

<span data-ttu-id="b599e-122">某些设备限制非常简单，会禁用功能或与设备的连接。</span><span class="sxs-lookup"><span data-stu-id="b599e-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="b599e-123">若要了解这些限制，请详细了解 [常见设备限制。](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="b599e-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <a name="kiosk-modes"></a><span data-ttu-id="b599e-124">展台模式</span><span class="sxs-lookup"><span data-stu-id="b599e-124">Kiosk modes</span></span>

<span data-ttu-id="b599e-125">使用展台模式控制默认情况下哪些标识有权访问哪些应用。</span><span class="sxs-lookup"><span data-stu-id="b599e-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="b599e-126">展台可用于单个应用或多个应用 UI 体验。</span><span class="sxs-lookup"><span data-stu-id="b599e-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="b599e-127">展台配置包括适用于使用设备的任何人的单个应用，以及不同组的不同应用选择。</span><span class="sxs-lookup"><span data-stu-id="b599e-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="b599e-128">展台模式不会阻止"允许的应用"启动其他应用，并且永远不会停止。</span><span class="sxs-lookup"><span data-stu-id="b599e-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="b599e-129">有关详细信息， [请阅读展台模式及其使用方法](hololens-kiosk.md)。</span><span class="sxs-lookup"><span data-stu-id="b599e-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <a name="settings-page-visibility"></a><span data-ttu-id="b599e-130">设置页面可见性</span><span class="sxs-lookup"><span data-stu-id="b599e-130">Settings Page Visibility</span></span>

<span data-ttu-id="b599e-131">默认情况下设置应用策略来控制哪些标识有权访问设置。</span><span class="sxs-lookup"><span data-stu-id="b599e-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="b599e-132">使用此策略，设置应用配置为只显示所选页面，或隐藏所有选定的页面。</span><span class="sxs-lookup"><span data-stu-id="b599e-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="b599e-133">[了解如何配置可用的页面](settings-uri-list.md)。</span><span class="sxs-lookup"><span data-stu-id="b599e-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="b599e-134">此功能目前仅在预览体验成员Windows[中可用](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="b599e-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="b599e-135">确保要用于此功能的设备位于内部版本 19041.1349+ 上。</span><span class="sxs-lookup"><span data-stu-id="b599e-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <a name="wdac"></a><span data-ttu-id="b599e-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="b599e-136">WDAC</span></span>

<span data-ttu-id="b599e-137">使用 WDAC 配置来控制允许/禁止启动的应用/进程，而不管系统是否采用展台模式。</span><span class="sxs-lookup"><span data-stu-id="b599e-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="b599e-138">请参阅 WDAC 概述。</span><span class="sxs-lookup"><span data-stu-id="b599e-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
