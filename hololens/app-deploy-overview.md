---
title: 概述-应用程序管理
description: 应用、管理、应用管理
keywords: HoloLens、用户、帐户、应用、应用程序管理
author: v-jodben
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisl
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: eeed478970d08eff8789a9decd084f1863c6d7f9
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857886"
---
# <span data-ttu-id="6fc96-104">应用管理：概述</span><span class="sxs-lookup"><span data-stu-id="6fc96-104">App Management: Overview</span></span>

<span data-ttu-id="6fc96-105">你可以将应用部署到四种不同路径：**移动设备管理（MDM）**、 **Microsoft store for Business**、 **Microsoft store**或通过**预配**进行安装。</span><span class="sxs-lookup"><span data-stu-id="6fc96-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span> 

## <span data-ttu-id="6fc96-106">移动设备管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="6fc96-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="6fc96-107">MDM 解决方案使 IT 决策者和管理员能够通过应用商店为一组用户私下自动安装（推送）其内部、业务线应用或购买应用。</span><span class="sxs-lookup"><span data-stu-id="6fc96-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="6fc96-108">HoloLens 设备最适用于[应用程序管理](app-deploy-intune.md)的 Microsoft 终结点管理器（Intune）。</span><span class="sxs-lookup"><span data-stu-id="6fc96-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="6fc96-109">Intune 还通过公司门户可下载体验向用户提供对 IT 托管应用的精细控制。</span><span class="sxs-lookup"><span data-stu-id="6fc96-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE] 
> <span data-ttu-id="6fc96-110">以下说明适用于希望使用 Intune 管理其应用程序的用户。</span><span class="sxs-lookup"><span data-stu-id="6fc96-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="6fc96-111">Microsoft 建议使用 Intune 进行应用和设备管理。</span><span class="sxs-lookup"><span data-stu-id="6fc96-111">Microsoft recommends using Intune for application and device management.</span></span>
    
<span data-ttu-id="6fc96-112">移动设备管理（MDM）适用于以下情况：</span><span class="sxs-lookup"><span data-stu-id="6fc96-112">Mobile Device Management (MDM) is applicable for:</span></span> 
* <span data-ttu-id="6fc96-113">已部署 MDM + 公司门户</span><span class="sxs-lookup"><span data-stu-id="6fc96-113">MDM deployed + Company Portal</span></span> 
* <span data-ttu-id="6fc96-114">Buisness （非公共）应用的线条</span><span class="sxs-lookup"><span data-stu-id="6fc96-114">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="6fc96-115">通过公司门户手动安装可用应用程序</span><span class="sxs-lookup"><span data-stu-id="6fc96-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="6fc96-116">通过 MDM 策略的管理员推送</span><span class="sxs-lookup"><span data-stu-id="6fc96-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="6fc96-117">通过 MDM 自动更新</span><span class="sxs-lookup"><span data-stu-id="6fc96-117">Auto update through MDM</span></span>

## <span data-ttu-id="6fc96-118">适用于企业的 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="6fc96-118">Microsoft Store for Business</span></span>

<span data-ttu-id="6fc96-119">[Microsoft Store For Business](app-deploy-store-business.md)向企业中的 IT 决策者和管理员提供查找、获取、管理和分发免费和付费应用的人员。</span><span class="sxs-lookup"><span data-stu-id="6fc96-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="6fc96-120">IT 管理员可以管理一份清单中的 Microsoft Store 应用、专用业务线应用以及根据需要分配和重新使用许可证。</span><span class="sxs-lookup"><span data-stu-id="6fc96-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and re-use licenses as needed.</span></span> <span data-ttu-id="6fc96-121">有关详细信息，请访问[使用 Microsoft Store For Business 的先决条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)。</span><span class="sxs-lookup"><span data-stu-id="6fc96-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>
    
<span data-ttu-id="6fc96-122">适用于企业的 Microsoft Store 适用于：</span><span class="sxs-lookup"><span data-stu-id="6fc96-122">The Microsoft Store for Business is applicable for:</span></span> 
* <span data-ttu-id="6fc96-123">公共或业务线应用程序</span><span class="sxs-lookup"><span data-stu-id="6fc96-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="6fc96-124">通过 MDM 关联自动安装所需的应用程序</span><span class="sxs-lookup"><span data-stu-id="6fc96-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="6fc96-125">用户手动下载应用</span><span class="sxs-lookup"><span data-stu-id="6fc96-125">User manually downloads apps</span></span>
* <span data-ttu-id="6fc96-126">自动更新</span><span class="sxs-lookup"><span data-stu-id="6fc96-126">Auto Update</span></span>

## <span data-ttu-id="6fc96-127">Microsoft Store 应用</span><span class="sxs-lookup"><span data-stu-id="6fc96-127">Microsoft Store apps</span></span>

<span data-ttu-id="6fc96-128">Microsoft Store 向企业中的 IT 决策者和管理员提供查找、获取、管理和分发公共应用的人员。</span><span class="sxs-lookup"><span data-stu-id="6fc96-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>
    
<span data-ttu-id="6fc96-129">此 Microsoft Store 适用于：</span><span class="sxs-lookup"><span data-stu-id="6fc96-129">This Microsoft Store is applicable for:</span></span> 
* <span data-ttu-id="6fc96-130">仅限公共应用</span><span class="sxs-lookup"><span data-stu-id="6fc96-130">Public apps only</span></span>
* <span data-ttu-id="6fc96-131">用户手动下载应用</span><span class="sxs-lookup"><span data-stu-id="6fc96-131">User manually downloads apps</span></span>
* <span data-ttu-id="6fc96-132">如果已连接到 Internet，则自动更新</span><span class="sxs-lookup"><span data-stu-id="6fc96-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="6fc96-133">有关详细信息，请访问[全息应用商店应用](https://docs.microsoft.com/hololens/holographic-store-apps)。</span><span class="sxs-lookup"><span data-stu-id="6fc96-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="6fc96-134">通过预配程序包安装</span><span class="sxs-lookup"><span data-stu-id="6fc96-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="6fc96-135">[预配程序包](app-deploy-provisioning-package.md)允许你安装自定义或业务线应用，从而允许 IT 专业人员和管理员通过 USB 将应用快速安装到本地设备。</span><span class="sxs-lookup"><span data-stu-id="6fc96-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="6fc96-136">这可以在没有互联网连接和任何标识类型的情况下完成。</span><span class="sxs-lookup"><span data-stu-id="6fc96-136">This can be done without an internet connection and for any identity type.</span></span>
    
<span data-ttu-id="6fc96-137">通过预配程序包安装适用于：</span><span class="sxs-lookup"><span data-stu-id="6fc96-137">Installing via Provisioning Packages is applicable for:</span></span> 
* <span data-ttu-id="6fc96-138">Buisness （非公共）应用的线条</span><span class="sxs-lookup"><span data-stu-id="6fc96-138">Line of Buisness (non-public) apps</span></span>
* <span data-ttu-id="6fc96-139">公共应用（如果脱机安装程序可用）</span><span class="sxs-lookup"><span data-stu-id="6fc96-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="6fc96-140">仅限 USB 盘面加载</span><span class="sxs-lookup"><span data-stu-id="6fc96-140">USB side-load only</span></span>
* <span data-ttu-id="6fc96-141">无自动更新（需要通过预配包手动更新）</span><span class="sxs-lookup"><span data-stu-id="6fc96-141">No auto update (requires manual updates via Provisioning Package)</span></span>
