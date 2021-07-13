---
title: 在商业环境中规划 HoloLens 2 部署
description: 了解在企业环境中部署和管理 HoloLens 的核心需求，包括基础结构、azure active directory 和移动设备管理。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: joyjaz
ms.author: v-jjaswinski
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/21/2021
appliesto:
- HoloLens 2
ms.openlocfilehash: 2fb58345f623a0b70c1fda10b9fb550de70f4c6d
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635783"
---
# <a name="planning-hololens-2-deployment-in-a-commercial-environment"></a><span data-ttu-id="522f2-103">在商业环境中规划 HoloLens 2 部署</span><span class="sxs-lookup"><span data-stu-id="522f2-103">Planning HoloLens 2 deployment in a commercial environment</span></span>

## <a name="overview"></a><span data-ttu-id="522f2-104">概述</span><span class="sxs-lookup"><span data-stu-id="522f2-104">Overview</span></span>
> [!NOTE]
> <span data-ttu-id="522f2-105">本概述旨在帮助 IT 专业人员了解在组织中部署和管理 Microsoft HoloLens 2 设备的注意事项。</span><span class="sxs-lookup"><span data-stu-id="522f2-105">This overview is intended to help IT professionals understand considerations for deploying and managing Microsoft HoloLens 2 devices within an organization.</span></span> <span data-ttu-id="522f2-106">对于设备最终用户，请参阅开始[使用 HoloLens 2](hololens2-setup.md) 。</span><span class="sxs-lookup"><span data-stu-id="522f2-106">For device end users, see [Get your HoloLens 2 ready to use](hololens2-setup.md) to get started.</span></span>

<span data-ttu-id="522f2-107">HoloLens 2 在 Windows 10 全息版上运行，后者为组织提供强大、灵活的内置移动设备和应用管理技术。</span><span class="sxs-lookup"><span data-stu-id="522f2-107">HoloLens 2 runs on Windows 10 Holographic which provides organizations with robust, flexible, built-in mobile device and app management technologies.</span></span> <span data-ttu-id="522f2-108">Windows 10 全息版支持端到端设备生命周期管理，使公司可以控制其设备、数据和应用。</span><span class="sxs-lookup"><span data-stu-id="522f2-108">Windows 10 Holographic supports end-to-end device lifecycle management to give companies control over their devices, data, and apps.</span></span> <span data-ttu-id="522f2-109">使用全面的移动设备管理解决方案，可以轻松地将 HoloLens 2 纳入到标准生命周期实践，从设备注册、配置和应用程序管理到维护和停用。</span><span class="sxs-lookup"><span data-stu-id="522f2-109">The HoloLens 2 can easily be incorporated into standard lifecycle practices, from device enrollment, configuration, and application management to maintenance and retirement using a comprehensive mobile device management solution.</span></span>

<span data-ttu-id="522f2-110">以下步骤和视频可帮助指导你完成组织中的 HoloLens 2 采用过程。</span><span class="sxs-lookup"><span data-stu-id="522f2-110">The following steps and video can help guide you through the process of HoloLens 2 adoption within your organization.</span></span>

| | |
|--|--|
| ![步骤 1](images/1green.png)| <br/> <span data-ttu-id="522f2-112">**[常见部署方案](hololens-requirements.md)**：了解部署方案，并探索部署 HoloLens 2 设备所需的核心组件。</span><span class="sxs-lookup"><span data-stu-id="522f2-112">**[Common Deployment Scenarios](hololens-requirements.md)**: Understand deployment scenarios and explore the core components needed to deploy HoloLens 2 devices.</span></span> |
| ![步骤 2](images/2green.png)| <br/> <span data-ttu-id="522f2-114">**[准备](#prepare)**：熟悉 HoloLens 2 所需的基础结构要点。</span><span class="sxs-lookup"><span data-stu-id="522f2-114">**[Prepare](#prepare)**: Become familiar with the infrastructure essentials needed for HoloLens 2.</span></span> |
| ![步骤 3](images/3green.png) | <br/> <span data-ttu-id="522f2-116">**[配置](#configure)**：了解如何配置基于云的部署的基本组件。</span><span class="sxs-lookup"><span data-stu-id="522f2-116">**[Configure](#configure)**: Learn how to configure your essential components for a cloud-based deployment.</span></span> |
| ![步骤 4](images/4green.png) | <br/> <span data-ttu-id="522f2-118">**[部署](#deploy)**：了解如何部署设备并安全高效地分发应用程序。</span><span class="sxs-lookup"><span data-stu-id="522f2-118">**[Deploy](#deploy)**: Discover how to deploy your devices and distribute your applications securely and efficiently.</span></span> |
| ![步骤 5](images/5green.png) | <br/> <span data-ttu-id="522f2-120">**[维护](#maintain)**：查找正确维护 HoloLens 2 设备的状态所需的内容，并确保符合公司策略。</span><span class="sxs-lookup"><span data-stu-id="522f2-120">**[Maintain](#maintain)**: Find out what's needed to properly maintain the state of your HoloLens 2 devices and ensure compliance with corporate policy.</span></span> |

> [!VIDEO https://channel9.msdn.com/Shows/IT-Ops-Talk/HoloLens-2-Deployment-Overview/player]

## <a name="prepare"></a><span data-ttu-id="522f2-121">准备</span><span class="sxs-lookup"><span data-stu-id="522f2-121">Prepare</span></span>

<span data-ttu-id="522f2-122">了解支持整套 HoloLens 2 功能所需的基本基础结构服务。</span><span class="sxs-lookup"><span data-stu-id="522f2-122">Learn about essential infrastructure services required to support the full set of HoloLens 2 capabilities.</span></span> 

| <span data-ttu-id="522f2-123">组件</span><span class="sxs-lookup"><span data-stu-id="522f2-123">Component</span></span> | <span data-ttu-id="522f2-124">说明</span><span class="sxs-lookup"><span data-stu-id="522f2-124">Description</span></span> |
|-----------|------------|
| <span data-ttu-id="522f2-125">Azure AD</span><span class="sxs-lookup"><span data-stu-id="522f2-125">[Azure AD](hololens-identity.md)</span></span> | <span data-ttu-id="522f2-126">提供 HoloLens 2 的标识和访问管理</span><span class="sxs-lookup"><span data-stu-id="522f2-126">Provides identity and access management for the HoloLens 2</span></span>  |
| [<span data-ttu-id="522f2-127">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="522f2-127">Mobile Device Management</span></span>](hololens-mdm-configure.md)| <span data-ttu-id="522f2-128">管理连接到租户 HoloLens 2 设备</span><span class="sxs-lookup"><span data-stu-id="522f2-128">Manages HoloLens 2 devices connected to your tenant</span></span>  |
| [<span data-ttu-id="522f2-129">Wi-fi 网络</span><span class="sxs-lookup"><span data-stu-id="522f2-129">Wi-Fi Network</span></span>](hololens-commercial-infrastructure.md)| <span data-ttu-id="522f2-130">Wi-Fi 可用并且设备可以连接到 Internet</span><span class="sxs-lookup"><span data-stu-id="522f2-130">Wi-Fi is available and devices can be connected to the Internet</span></span>  |

## <a name="configure"></a><span data-ttu-id="522f2-131">配置</span><span class="sxs-lookup"><span data-stu-id="522f2-131">Configure</span></span>

<span data-ttu-id="522f2-132">使用 Intune 和 Autopilot 作为低接触解决方案，将 HoloLens 2 注册和配置到组织的 Azure AD 租户和 MDM。</span><span class="sxs-lookup"><span data-stu-id="522f2-132">Use Intune and Autopilot as low-touch solutions for enrolling and configuring HoloLens 2 to your organization’s Azure AD tenant and MDM.</span></span>

| <span data-ttu-id="522f2-133">组件</span><span class="sxs-lookup"><span data-stu-id="522f2-133">Component</span></span> | <span data-ttu-id="522f2-134">说明</span><span class="sxs-lookup"><span data-stu-id="522f2-134">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="522f2-135">自动注册</span><span class="sxs-lookup"><span data-stu-id="522f2-135">Auto Enrollment</span></span>](hololens-enroll-mdm.md#auto-enrollment-in-mdm) | <span data-ttu-id="522f2-136">初次登录后，设备会自动注册到 Azure AD 并注册到 MDM</span><span class="sxs-lookup"><span data-stu-id="522f2-136">After initial login, devices automatically register with Azure AD and enroll into MDM</span></span>  |
| [<span data-ttu-id="522f2-137">应用程序许可证</span><span class="sxs-lookup"><span data-stu-id="522f2-137">Application Licenses</span></span>](hololens2-cloud-connected-configure.md#application-licenses)| <span data-ttu-id="522f2-138">可应用于用户、用户组或设备组</span><span class="sxs-lookup"><span data-stu-id="522f2-138">Can be applied to either users, user groups, or device groups</span></span>  |
| [<span data-ttu-id="522f2-139">Azure 用户和组</span><span class="sxs-lookup"><span data-stu-id="522f2-139">Azure Users and Groups</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups) | <span data-ttu-id="522f2-140">帮助为 HoloLens 2 分配配置和许可证</span><span class="sxs-lookup"><span data-stu-id="522f2-140">Helps assign configurations and licenses for the HoloLens 2</span></span>  |

## <a name="deploy"></a><span data-ttu-id="522f2-141">部署</span><span class="sxs-lookup"><span data-stu-id="522f2-141">Deploy</span></span>

<span data-ttu-id="522f2-142">分发 HoloLens 2 设备并验证其配置。</span><span class="sxs-lookup"><span data-stu-id="522f2-142">Distribute your HoloLens 2 devices and validate their configuration.</span></span> 

| <span data-ttu-id="522f2-143">组件</span><span class="sxs-lookup"><span data-stu-id="522f2-143">Component</span></span> | <span data-ttu-id="522f2-144">说明</span><span class="sxs-lookup"><span data-stu-id="522f2-144">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="522f2-145">注册验证</span><span class="sxs-lookup"><span data-stu-id="522f2-145">Enrollment Validation</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation) | <span data-ttu-id="522f2-146">验证设备是否已从设置或 Azure 门户 Azure AD 联接</span><span class="sxs-lookup"><span data-stu-id="522f2-146">Validate the device has Azure AD Joined from Settings or the Azure Portal</span></span> |
| [<span data-ttu-id="522f2-147">证书验证</span><span class="sxs-lookup"><span data-stu-id="522f2-147">Certificate Validation</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation) | <span data-ttu-id="522f2-148">检查设置，并验证它们是否已正确分发</span><span class="sxs-lookup"><span data-stu-id="522f2-148">Check settings and validate they have been distributed correctly</span></span> |
| [<span data-ttu-id="522f2-149">验证应用安装</span><span class="sxs-lookup"><span data-stu-id="522f2-149">Validate app installs</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install) | <span data-ttu-id="522f2-150">确认应用是否存在，并处理 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="522f2-150">Confirm the app is present and working on your HoloLens 2</span></span> |

## <a name="maintain"></a><span data-ttu-id="522f2-151">维护</span><span class="sxs-lookup"><span data-stu-id="522f2-151">Maintain</span></span>

<span data-ttu-id="522f2-152">将 Windows 更新用于业务与 MDM 系统或 Microsoft Store，以使你的 HoloLens 2 和应用更新。</span><span class="sxs-lookup"><span data-stu-id="522f2-152">Use Windows Update for Business along with your MDM system or the Microsoft Store to keep your fleet of HoloLens 2 and apps updated.</span></span>

| <span data-ttu-id="522f2-153">组件</span><span class="sxs-lookup"><span data-stu-id="522f2-153">Component</span></span> | <span data-ttu-id="522f2-154">说明</span><span class="sxs-lookup"><span data-stu-id="522f2-154">Description</span></span> |
|-----------|------------|
| [<span data-ttu-id="522f2-155">更新 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="522f2-155">Update HoloLens 2</span></span>](hololens-updates.md) | <span data-ttu-id="522f2-156">通过 Windows 业务更新来根据需要配置更新</span><span class="sxs-lookup"><span data-stu-id="522f2-156">Configure updates as needed through Windows Updates for Business</span></span> |
| [<span data-ttu-id="522f2-157">更新应用</span><span class="sxs-lookup"><span data-stu-id="522f2-157">Update apps</span></span>](app-deploy-overview.md) | <span data-ttu-id="522f2-158">通过 MDM 系统或 Microsoft Store 进行配置</span><span class="sxs-lookup"><span data-stu-id="522f2-158">Configure through your MDM system or the Microsoft Store</span></span>
