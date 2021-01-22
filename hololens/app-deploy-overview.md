---
title: 概述 - 应用管理
description: 开始使用移动设备管理、适用于企业 Microsoft Store 和预配包的混合现实应用管理概述。
keywords: HoloLens， 用户， 帐户， 应用， 应用程序管理，
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 951c79e49d67c1a0308e236e4283ffa498a7139f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283703"
---
# <span data-ttu-id="a5130-104">应用管理：概述</span><span class="sxs-lookup"><span data-stu-id="a5130-104">App Management: Overview</span></span>

<span data-ttu-id="a5130-105">你可以部署四种不同路径的应用：移动设备管理\*\* (MDM) 、\*\*\*\*适用于企业**Microsoft **Store、Microsoft Store，** 或通过预配安装**它们\*\*。</span><span class="sxs-lookup"><span data-stu-id="a5130-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <span data-ttu-id="a5130-106">移动设备管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="a5130-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="a5130-107">MDM 解决方案使 IT 决策者和管理员可以专用地自动安装 (推送) 其内部、业务线应用，或通过应用商店为一组用户购买应用。</span><span class="sxs-lookup"><span data-stu-id="a5130-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="a5130-108">HoloLens 设备最适用于 Microsoft Endpoint Manager (Intune) [应用程序管理](app-deploy-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="a5130-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="a5130-109">Intune 还通过公司门户可下载体验为用户提供对 IT 托管应用的更精细控制。</span><span class="sxs-lookup"><span data-stu-id="a5130-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="a5130-110">以下说明适用于想要使用 Intune 管理其应用程序的用户。</span><span class="sxs-lookup"><span data-stu-id="a5130-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="a5130-111">Microsoft 建议使用 Intune 进行应用程序和设备管理。</span><span class="sxs-lookup"><span data-stu-id="a5130-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="a5130-112">移动设备管理 (MDM) 适用于：</span><span class="sxs-lookup"><span data-stu-id="a5130-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="a5130-113">MDM 已部署 + 公司门户</span><span class="sxs-lookup"><span data-stu-id="a5130-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="a5130-114">业务线 (非公共) 应用</span><span class="sxs-lookup"><span data-stu-id="a5130-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="a5130-115">通过公司门户手动安装可用应用程序</span><span class="sxs-lookup"><span data-stu-id="a5130-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="a5130-116">管理员推送 MDM 策略</span><span class="sxs-lookup"><span data-stu-id="a5130-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="a5130-117">通过 MDM 自动更新</span><span class="sxs-lookup"><span data-stu-id="a5130-117">Auto update through MDM</span></span>

## <span data-ttu-id="a5130-118">适用于企业的 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="a5130-118">Microsoft Store for Business</span></span>

<span data-ttu-id="a5130-119">适用于 [企业的 Microsoft Store](app-deploy-store-business.md) 为企业的 IT 决策者和管理员提供查找、获取、管理和分发免费和付费应用。</span><span class="sxs-lookup"><span data-stu-id="a5130-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="a5130-120">IT 管理员可以在一个清单中管理 Microsoft Store 应用和专用业务线应用，并根据需要分配和重复使用许可证。</span><span class="sxs-lookup"><span data-stu-id="a5130-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="a5130-121">有关详细信息，请访问使用适用于企业 [Microsoft Store 的先决条件](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business)。</span><span class="sxs-lookup"><span data-stu-id="a5130-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="a5130-122">适用于 Business 的 Microsoft Store 适用于：</span><span class="sxs-lookup"><span data-stu-id="a5130-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="a5130-123">公共或业务线应用</span><span class="sxs-lookup"><span data-stu-id="a5130-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="a5130-124">通过 MDM 关联自动安装所需应用程序</span><span class="sxs-lookup"><span data-stu-id="a5130-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="a5130-125">用户手动下载应用</span><span class="sxs-lookup"><span data-stu-id="a5130-125">User manually downloads apps</span></span>
* <span data-ttu-id="a5130-126">自动更新</span><span class="sxs-lookup"><span data-stu-id="a5130-126">Auto Update</span></span>

## <span data-ttu-id="a5130-127">Microsoft Store 应用</span><span class="sxs-lookup"><span data-stu-id="a5130-127">Microsoft Store apps</span></span>

<span data-ttu-id="a5130-128">Microsoft Store 为企业的 IT 决策者和管理员提供查找、获取、管理和分发公共应用。</span><span class="sxs-lookup"><span data-stu-id="a5130-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="a5130-129">此 Microsoft Store 适用于：</span><span class="sxs-lookup"><span data-stu-id="a5130-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="a5130-130">仅公共应用</span><span class="sxs-lookup"><span data-stu-id="a5130-130">Public apps only</span></span>
* <span data-ttu-id="a5130-131">用户手动下载应用</span><span class="sxs-lookup"><span data-stu-id="a5130-131">User manually downloads apps</span></span>
* <span data-ttu-id="a5130-132">连接到 Internet 时自动更新</span><span class="sxs-lookup"><span data-stu-id="a5130-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="a5130-133">有关详细信息，请访问 [全息应用商店应用](https://docs.microsoft.com/hololens/holographic-store-apps)。</span><span class="sxs-lookup"><span data-stu-id="a5130-133">For more information, visit [Holographic Store Apps](https://docs.microsoft.com/hololens/holographic-store-apps).</span></span>

## <span data-ttu-id="a5130-134">通过预配包安装</span><span class="sxs-lookup"><span data-stu-id="a5130-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="a5130-135">[预配包](app-deploy-provisioning-package.md) 允许你安装自定义或业务线应用，使 IT 专业人员和管理员可以通过 USB 将应用 () 本地设备。</span><span class="sxs-lookup"><span data-stu-id="a5130-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="a5130-136">无需 Internet 连接和任何标识类型即可完成此安装。</span><span class="sxs-lookup"><span data-stu-id="a5130-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="a5130-137">通过预配包进行安装适用于：</span><span class="sxs-lookup"><span data-stu-id="a5130-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="a5130-138">业务线/自开发 (非公共) 应用</span><span class="sxs-lookup"><span data-stu-id="a5130-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="a5130-139">公共应用 (脱机安装程序是否可用) </span><span class="sxs-lookup"><span data-stu-id="a5130-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="a5130-140">仅 USB 旁加载</span><span class="sxs-lookup"><span data-stu-id="a5130-140">USB side-loading only</span></span>
* <span data-ttu-id="a5130-141">无需自动更新 (通过预配包进行手动) </span><span class="sxs-lookup"><span data-stu-id="a5130-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <span data-ttu-id="a5130-142">通过应用安装程序在 HoloLens 2 上安装应用</span><span class="sxs-lookup"><span data-stu-id="a5130-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="a5130-143">使用 [应用](app-deploy-app-installer.md) 安装程序，用户可以拥有一种简单易用的体验：在本地设备上安装应用，或与不熟悉 HoloLens 上其他应用安装方法的其他人共享应用。</span><span class="sxs-lookup"><span data-stu-id="a5130-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="a5130-144">无需启用开发人员模式或使用 Device Portal 即可完成此操作。</span><span class="sxs-lookup"><span data-stu-id="a5130-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="a5130-145">这是分发完全生成应用的简单方法。</span><span class="sxs-lookup"><span data-stu-id="a5130-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="a5130-146">无论你是希望将应用演示给使用 HoloLens 的其他用户，还是想要部署你的应用，此方法都很容易实现。</span><span class="sxs-lookup"><span data-stu-id="a5130-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="a5130-147">通过应用安装程序安装适用于：</span><span class="sxs-lookup"><span data-stu-id="a5130-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="a5130-148">业务线/自开发 (公共) 应用程序</span><span class="sxs-lookup"><span data-stu-id="a5130-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="a5130-149">仅旁加载</span><span class="sxs-lookup"><span data-stu-id="a5130-149">Side-load only</span></span>
* <span data-ttu-id="a5130-150">不需要开发人员模式或设备门户</span><span class="sxs-lookup"><span data-stu-id="a5130-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="a5130-151">易于最终用户安装</span><span class="sxs-lookup"><span data-stu-id="a5130-151">Easy for end user to install</span></span>
