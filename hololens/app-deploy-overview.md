---
title: 概述-应用管理
description: 使用移动设备管理、适用于企业的 Microsoft 应用商店和预配包的混合现实应用管理概述入门。
keywords: HoloLens、用户、帐户、应用、应用程序管理、
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
ms.openlocfilehash: ca87f34718319d489b69ba33ad24731628d87fac
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635545"
---
# <a name="app-management-overview"></a><span data-ttu-id="e7295-104">应用管理：概述</span><span class="sxs-lookup"><span data-stu-id="e7295-104">App Management: Overview</span></span>

<span data-ttu-id="e7295-105">可以在四个不同的路径上部署应用：**移动设备管理 (MDM)**、**适用于企业的 Microsoft Store**、 **Microsoft Store** 或通过 **设置** 来安装。</span><span class="sxs-lookup"><span data-stu-id="e7295-105">You can deploy apps on four different paths: **Mobile Device Management (MDM)**, **Microsoft Store for Business**, **Microsoft Store**, or by installing them via **Provisioning**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="e7295-106">移动设备管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="e7295-106">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="e7295-107">通过 MDM 解决方案，IT 决策者和管理员可通过个人自动安装 (推送) 其内部、业务线应用，或者通过应用商店为一组用户购买应用。</span><span class="sxs-lookup"><span data-stu-id="e7295-107">An MDM solution enables IT decision-makers and administrators to privately auto-install (push) their in-house, line-of-business apps, or purchase apps through the store for a group of users.</span></span> <span data-ttu-id="e7295-108">HoloLens 设备最好与 Microsoft Endpoint Manager (Intune) 用于[应用程序管理](app-deploy-intune.md)。</span><span class="sxs-lookup"><span data-stu-id="e7295-108">HoloLens devices work best with Microsoft Endpoint Manager (Intune) for [application management](app-deploy-intune.md).</span></span> <span data-ttu-id="e7295-109">Intune 还通过公司门户可下载的体验为用户提供对 IT 托管应用的精细控制。</span><span class="sxs-lookup"><span data-stu-id="e7295-109">Intune also offers users finer-grained control over IT-managed apps through the Company Portal downloadable experience.</span></span>

> [!NOTE]
> <span data-ttu-id="e7295-110">以下说明适用于想要通过 Intune 管理其应用程序的用户。</span><span class="sxs-lookup"><span data-stu-id="e7295-110">The following instructions are for users who want to manage their applications with Intune.</span></span> <span data-ttu-id="e7295-111">Microsoft 建议使用 Intune 进行应用程序和设备管理。</span><span class="sxs-lookup"><span data-stu-id="e7295-111">Microsoft recommends using Intune for application and device management.</span></span>

<span data-ttu-id="e7295-112"> (MDM) 的移动设备管理适用于：</span><span class="sxs-lookup"><span data-stu-id="e7295-112">Mobile Device Management (MDM) is applicable for:</span></span>

* <span data-ttu-id="e7295-113">已部署 MDM + 公司门户</span><span class="sxs-lookup"><span data-stu-id="e7295-113">MDM deployed + Company Portal</span></span>
* <span data-ttu-id="e7295-114">业务线 (非公共) 应用</span><span class="sxs-lookup"><span data-stu-id="e7295-114">Line of Business (non-public) apps</span></span>
* <span data-ttu-id="e7295-115">通过公司门户手动安装可用应用程序</span><span class="sxs-lookup"><span data-stu-id="e7295-115">Manual installation of available applications through Company Portal</span></span>
* <span data-ttu-id="e7295-116">通过 MDM 策略的管理员推送</span><span class="sxs-lookup"><span data-stu-id="e7295-116">Admin push through MDM policy</span></span>
* <span data-ttu-id="e7295-117">通过 MDM 自动更新</span><span class="sxs-lookup"><span data-stu-id="e7295-117">Auto update through MDM</span></span>

## <a name="microsoft-store-for-business"></a><span data-ttu-id="e7295-118">适用于企业的 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="e7295-118">Microsoft Store for Business</span></span>

<span data-ttu-id="e7295-119">[适用于企业的 Microsoft Store](app-deploy-store-business.md)为 IT 决策者和企业中的管理员提供查找、获取、管理和分发免费和付费应用程序的管理员。</span><span class="sxs-lookup"><span data-stu-id="e7295-119">The [Microsoft Store for Business](app-deploy-store-business.md) provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute free and paid apps.</span></span> <span data-ttu-id="e7295-120">IT 管理员可以在一个库存中管理 Microsoft Store 应用和私有业务线应用，还可以根据需要分配和重复使用许可证。</span><span class="sxs-lookup"><span data-stu-id="e7295-120">IT administrators can manage Microsoft Store apps and private line-of-business apps in one inventory, plus assign and reuse licenses as needed.</span></span> <span data-ttu-id="e7295-121">有关详细信息，请访问[使用适用于企业的 Microsoft Store 的先决条件](/microsoft-store/prerequisites-microsoft-store-for-business)。</span><span class="sxs-lookup"><span data-stu-id="e7295-121">For more information, visit [Prerequisites for using the Microsoft Store for Business](/microsoft-store/prerequisites-microsoft-store-for-business).</span></span>

<span data-ttu-id="e7295-122">适用于企业的 Microsoft Store 适用于：</span><span class="sxs-lookup"><span data-stu-id="e7295-122">The Microsoft Store for Business is applicable for:</span></span>

* <span data-ttu-id="e7295-123">公共或业务线应用</span><span class="sxs-lookup"><span data-stu-id="e7295-123">Public or Line of Business apps</span></span>
* <span data-ttu-id="e7295-124">通过 MDM 关联自动安装所需的应用程序</span><span class="sxs-lookup"><span data-stu-id="e7295-124">Automatic installation of required applications through MDM association</span></span>
* <span data-ttu-id="e7295-125">用户手动下载应用</span><span class="sxs-lookup"><span data-stu-id="e7295-125">User manually downloads apps</span></span>
* <span data-ttu-id="e7295-126">自动更新</span><span class="sxs-lookup"><span data-stu-id="e7295-126">Auto Update</span></span>

## <a name="microsoft-store-apps"></a><span data-ttu-id="e7295-127">Microsoft Store 应用</span><span class="sxs-lookup"><span data-stu-id="e7295-127">Microsoft Store apps</span></span>

<span data-ttu-id="e7295-128">Microsoft Store 为 IT 决策者和企业中的管理员提供查找、获取、管理和分发公共应用程序的管理员。</span><span class="sxs-lookup"><span data-stu-id="e7295-128">The Microsoft Store provides IT decision-makers and administrators in businesses to find, acquire, manage, and distribute public apps.</span></span>

<span data-ttu-id="e7295-129">此 Microsoft Store 适用于：</span><span class="sxs-lookup"><span data-stu-id="e7295-129">This Microsoft Store is applicable for:</span></span>

* <span data-ttu-id="e7295-130">仅限公共应用</span><span class="sxs-lookup"><span data-stu-id="e7295-130">Public apps only</span></span>
* <span data-ttu-id="e7295-131">用户手动下载应用</span><span class="sxs-lookup"><span data-stu-id="e7295-131">User manually downloads apps</span></span>
* <span data-ttu-id="e7295-132">如果已连接到 Internet，则自动更新</span><span class="sxs-lookup"><span data-stu-id="e7295-132">Auto update if connected to Internet</span></span>

<span data-ttu-id="e7295-133">有关详细信息，请访问 [全息应用商店应用](/hololens/holographic-store-apps)。</span><span class="sxs-lookup"><span data-stu-id="e7295-133">For more information, visit [Holographic Store Apps](/hololens/holographic-store-apps).</span></span>

## <a name="install-via-provisioning-packages"></a><span data-ttu-id="e7295-134">通过预配包安装</span><span class="sxs-lookup"><span data-stu-id="e7295-134">Install via Provisioning Packages</span></span>

<span data-ttu-id="e7295-135">[预配包](app-deploy-provisioning-package.md) 允许安装自定义或业务线应用，允许 IT 专业人员和管理员通过 USB 将应用快速安装到本地设备 () 。</span><span class="sxs-lookup"><span data-stu-id="e7295-135">[Provisioning Packages](app-deploy-provisioning-package.md) allow you to install custom or Line of Business apps, allowing IT pros and administrators to quickly install apps to a local device(s) via USB.</span></span> <span data-ttu-id="e7295-136">如果没有 internet 连接，则可以进行这种安装，任何标识类型都可以这样做。</span><span class="sxs-lookup"><span data-stu-id="e7295-136">This installation can be done without an internet connection and for any identity type.</span></span>

<span data-ttu-id="e7295-137">通过预配包安装适用于：</span><span class="sxs-lookup"><span data-stu-id="e7295-137">Installing via Provisioning Packages is applicable for:</span></span>

* <span data-ttu-id="e7295-138">业务线/自行开发 (非公共) 应用</span><span class="sxs-lookup"><span data-stu-id="e7295-138">Line of Business / Self-developed (non-public) apps</span></span>
* <span data-ttu-id="e7295-139">公开应用程序 (如果脱机安装程序可用) </span><span class="sxs-lookup"><span data-stu-id="e7295-139">Public apps (if offline installer is available)</span></span>
* <span data-ttu-id="e7295-140">仅限 USB 边载</span><span class="sxs-lookup"><span data-stu-id="e7295-140">USB side-loading only</span></span>
* <span data-ttu-id="e7295-141">无自动更新 (需要通过预配包进行手动更新) </span><span class="sxs-lookup"><span data-stu-id="e7295-141">No auto update (requires manual updates via Provisioning Package)</span></span>

## <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="e7295-142">在 HoloLens 2 通过应用安装程序安装应用</span><span class="sxs-lookup"><span data-stu-id="e7295-142">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="e7295-143">使用[应用程序安装程序](app-deploy-app-installer.md)时，用户可以体验到在本地设备上安装应用程序，或与其他不熟悉 HoloLens 上的应用程序安装方法的人员共享应用程序。</span><span class="sxs-lookup"><span data-stu-id="e7295-143">Using the [App Installer](app-deploy-app-installer.md) users can have an experience that is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> <span data-ttu-id="e7295-144">无需启用开发人员模式或使用设备门户即可执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e7295-144">This can be done without needing to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="e7295-145">这是分发完全生成的应用的一种简单方法。</span><span class="sxs-lookup"><span data-stu-id="e7295-145">This is a simple method of distributing a completely built app.</span></span> <span data-ttu-id="e7295-146">无论你只是想要使用 HoloLens 向另一个用户演示应用程序，还是想要部署应用程序，都可以轻松地使用此方法。</span><span class="sxs-lookup"><span data-stu-id="e7295-146">Regardless of if you simply wish to demo your app to another user with a HoloLens, or you'd like to deploy your app this method works easily.</span></span>

<span data-ttu-id="e7295-147">通过应用安装程序安装适用于：</span><span class="sxs-lookup"><span data-stu-id="e7295-147">Installing via App Installer is applicable for:</span></span>

* <span data-ttu-id="e7295-148">业务线/自行开发 (非公共) 应用</span><span class="sxs-lookup"><span data-stu-id="e7295-148">Line of Business / Self developed (non-public) apps</span></span>
* <span data-ttu-id="e7295-149">仅侧加载</span><span class="sxs-lookup"><span data-stu-id="e7295-149">Side-load only</span></span>
* <span data-ttu-id="e7295-150">不需要开发人员模式或设备门户</span><span class="sxs-lookup"><span data-stu-id="e7295-150">Does not require Developer mode or Device portal</span></span>
* <span data-ttu-id="e7295-151">便于最终用户安装</span><span class="sxs-lookup"><span data-stu-id="e7295-151">Easy for end user to install</span></span>
