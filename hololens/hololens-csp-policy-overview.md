---
title: 配置 CSP 和设备管理概述
description: 如何配置 CSP、策略和设备管理。
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
ms.openlocfilehash: c6da29506035525b1b1b5141a04603f63de1ef24
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252773"
---
# <span data-ttu-id="09bbd-103">配置 CSP 和设备管理概述</span><span class="sxs-lookup"><span data-stu-id="09bbd-103">Configure CSPs and Device Management overview</span></span>

<span data-ttu-id="09bbd-104">IT 管理员可以在 HoloLens 2 上定义和实施策略设置。</span><span class="sxs-lookup"><span data-stu-id="09bbd-104">IT Administrators can define and implement policy settings on HoloLens 2.</span></span> <span data-ttu-id="09bbd-105">你使用的配置设置将基于部署方案而异，公司设备将为 IT 提供最广泛的控制权。</span><span class="sxs-lookup"><span data-stu-id="09bbd-105">What configuration settings you use will differ based on the deployment scenario, and corporate devices will offer IT the broadest range of control.</span></span> <span data-ttu-id="09bbd-106">在 Windows 10 中， (CSP) 是一个接口，用于读取、设置、修改或删除设备的配置设置。</span><span class="sxs-lookup"><span data-stu-id="09bbd-106">In Windows 10, Configuration Service Providers (CSP)s are an interface to read, set, modify, or delete configuration settings on the device.</span></span> <span data-ttu-id="09bbd-107">这些设置将映射到注册表项或文件。</span><span class="sxs-lookup"><span data-stu-id="09bbd-107">These settings map to registry keys or files.</span></span> <span data-ttu-id="09bbd-108">一些配置服务提供程序支持 WAP 格式，一些支持 SyncML，一些支持两者。</span><span class="sxs-lookup"><span data-stu-id="09bbd-108">Some configuration service providers support the WAP format, some support SyncML, and some support both.</span></span>

<span data-ttu-id="09bbd-109">有关 Windows 10 全息设备管理 CSP 详细信息，请参阅 [HoloLens](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens)设备中支持的 AP 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="09bbd-109">For more information about Windows 10 Holographic device management CSPs, see the full list of [CSPs supported in HoloLens devices](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).</span></span>
<span data-ttu-id="09bbd-110">IT 管理员还可以在设备上管理策略 CSP，查看 [HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2)支持的策略 CSP 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="09bbd-110">IT Administrators can also manage Policy CSP on devices, see the full list of [Policy CSPs supported by HoloLens 2](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-hololens2).</span></span>

## <span data-ttu-id="09bbd-111">配置方法</span><span class="sxs-lookup"><span data-stu-id="09bbd-111">Configuration methods</span></span>

### <span data-ttu-id="09bbd-112">使用 MDM 配置</span><span class="sxs-lookup"><span data-stu-id="09bbd-112">Configure with MDM</span></span>

<span data-ttu-id="09bbd-113">可以在 MDM 系统中注册的任何个人或公司设备上轻松管理 CSP 和策略。</span><span class="sxs-lookup"><span data-stu-id="09bbd-113">CSPs and Policies can be easily managed on any personal or corporate device enrolled in an MDM system.</span></span> <span data-ttu-id="09bbd-114">在 MDM 解决方案中注册设备后，你将能够使用设备配置管理该设备或一组设备。</span><span class="sxs-lookup"><span data-stu-id="09bbd-114">Once a device is enrolled in your MDM solution, you will be able to manage that device, or set of devices using device configurations.</span></span> <span data-ttu-id="09bbd-115">详细了解如何通过 MDM 管理 [HoloLens 设备](hololens-mdm-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="09bbd-115">Learn more about how to [manage your HoloLens devices through MDM](hololens-mdm-configure.md).</span></span>

### <span data-ttu-id="09bbd-116">使用预配包进行配置</span><span class="sxs-lookup"><span data-stu-id="09bbd-116">Configure with Provisioning Packages</span></span>

<span data-ttu-id="09bbd-117">HoloLens 2 还支持通过自定义预配包为 HoloLens 2 设备设置一组有限的云解决方案提供商配置。</span><span class="sxs-lookup"><span data-stu-id="09bbd-117">HoloLens 2 also supports setting a limited set of CSP configurations for HoloLens 2 devices through custom Provisioning Packages.</span></span> <span data-ttu-id="09bbd-118">预配包通常用于非 MDM 托管设备，并且需要手动应用到每台设备。</span><span class="sxs-lookup"><span data-stu-id="09bbd-118">Provisioning Packages are typically leveraged for non-MDM managed devices and require to be manually applied to each device.</span></span> <span data-ttu-id="09bbd-119">阅读有关为 [HoloLens 生成自定义预配包的信息](https://docs.microsoft.com/hololens/hololens-provisioning)。</span><span class="sxs-lookup"><span data-stu-id="09bbd-119">Read information on building custom [Provisioning Packages for HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span>

## <span data-ttu-id="09bbd-120">配置</span><span class="sxs-lookup"><span data-stu-id="09bbd-120">Configurations</span></span>

### <span data-ttu-id="09bbd-121">常见设备限制</span><span class="sxs-lookup"><span data-stu-id="09bbd-121">Common device restrictions</span></span>

<span data-ttu-id="09bbd-122">某些设备限制非常简单，并且禁用了功能或设备连接。</span><span class="sxs-lookup"><span data-stu-id="09bbd-122">Some device restrictions are as simple and disabling a functionality or connection to the device.</span></span> <span data-ttu-id="09bbd-123">若要了解有关这些限制的信息，请阅读有关 [常见设备限制的更多内容。](hololens-common-device-restrictions.md)</span><span class="sxs-lookup"><span data-stu-id="09bbd-123">To learn about these read more about [common device restrictions.](hololens-common-device-restrictions.md)</span></span>

### <span data-ttu-id="09bbd-124">展台模式</span><span class="sxs-lookup"><span data-stu-id="09bbd-124">Kiosk modes</span></span>

<span data-ttu-id="09bbd-125">使用展台模式控制默认情况下哪些标识有权访问哪些应用。</span><span class="sxs-lookup"><span data-stu-id="09bbd-125">Use Kiosk mode to control which identities have access to which apps by default.</span></span> <span data-ttu-id="09bbd-126">展台可用于单个应用或多个应用 UI 体验。</span><span class="sxs-lookup"><span data-stu-id="09bbd-126">Kiosks can be used for a single app or multiple app UI experience.</span></span> <span data-ttu-id="09bbd-127">展台配置包括从单个应用（适用于使用该设备的任何人）到不同组的不同应用选择。</span><span class="sxs-lookup"><span data-stu-id="09bbd-127">Kiosk configurations range from a single app for anyone using the device, to different selections of apps for different groups.</span></span> <span data-ttu-id="09bbd-128">展台模式不会阻止"允许的应用"启动其他应用，并且永远不会这样。</span><span class="sxs-lookup"><span data-stu-id="09bbd-128">Kiosk mode does not stop “allowed apps” from launching other apps and was not intended to ever.</span></span> <span data-ttu-id="09bbd-129">通过阅读 [有关展台模式以及如何使用它们来了解更多信息](hololens-kiosk.md)。</span><span class="sxs-lookup"><span data-stu-id="09bbd-129">Learn more by [reading about Kiosk modes and how to use them](hololens-kiosk.md).</span></span>

### <span data-ttu-id="09bbd-130">设置页面可见性</span><span class="sxs-lookup"><span data-stu-id="09bbd-130">Settings Page Visibility</span></span>

<span data-ttu-id="09bbd-131">使用"设置"应用策略控制默认情况下哪些标识有权访问设置。</span><span class="sxs-lookup"><span data-stu-id="09bbd-131">Use Settings app policy to control which identities have access to settings by default.</span></span> <span data-ttu-id="09bbd-132">使用此策略，可以将"设置"应用配置为只显示选择页面，或隐藏所有选定的页面。</span><span class="sxs-lookup"><span data-stu-id="09bbd-132">Using this policy the Settings app can be configured to either show only the select pages, or hide all selected pages.</span></span> <span data-ttu-id="09bbd-133">[了解如何配置可用的页面](settings-uri-list.md)。</span><span class="sxs-lookup"><span data-stu-id="09bbd-133">[Read about how to configure the pages available](settings-uri-list.md).</span></span>

<span data-ttu-id="09bbd-134">此功能当前仅适用于 Windows 预览 [体验成员版本](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="09bbd-134">This feature is currently only available in [Windows Insider builds](hololens-insider.md).</span></span> <span data-ttu-id="09bbd-135">确保打算使用此功能的设备在内部版本 19041.1349+ 上。</span><span class="sxs-lookup"><span data-stu-id="09bbd-135">Ensure devices you intend to use this feature for are on build 19041.1349+.</span></span>

### <span data-ttu-id="09bbd-136">WDAC</span><span class="sxs-lookup"><span data-stu-id="09bbd-136">WDAC</span></span>

<span data-ttu-id="09bbd-137">使用 WDAC 配置来控制允许/禁止启动的应用/进程，而不考虑系统是否位于展台模式下。</span><span class="sxs-lookup"><span data-stu-id="09bbd-137">Use WDAC configuration to control which apps / processes are allowed / disallowed to be launched irrespective of whether system is in kiosk mode or not.</span></span>
[<span data-ttu-id="09bbd-138">请参阅 WDAC 概述。</span><span class="sxs-lookup"><span data-stu-id="09bbd-138">See our overview for WDAC.</span></span>](windows-defender-application-control-wdac.md)
