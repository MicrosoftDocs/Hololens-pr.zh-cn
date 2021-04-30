---
title: 常见基础结构部署方案
description: 了解基于混合现实的不同基础结构部署的一些最常见的部署方案。
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
keywords: hololens
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: v-evmill
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308418"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="d029c-104">常见基础结构部署方案概述</span><span class="sxs-lookup"><span data-stu-id="d029c-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="d029c-105">以下信息提供了在企业中部署和管理 Microsoft HoloLens 2 设备时三个常见方案的高级体系结构概述。</span><span class="sxs-lookup"><span data-stu-id="d029c-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="d029c-106">通常，如何管理设备以及如何访问组织的资源，主要取决于已有的因素。</span><span class="sxs-lookup"><span data-stu-id="d029c-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="d029c-107">根据现有的基础结构，我们建议你在以下情况下查看常见的设备管理样式，并试用用于在满足你的需求的方案中部署的指南。</span><span class="sxs-lookup"><span data-stu-id="d029c-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="d029c-108">方案</span><span class="sxs-lookup"><span data-stu-id="d029c-108">Scenarios</span></span>

<span data-ttu-id="d029c-109">下图表示 HoloLens 2 部署的三个典型方案。</span><span class="sxs-lookup"><span data-stu-id="d029c-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
<span data-ttu-id="d029c-110">![方案图](images/scenarios.jpg)</span><span class="sxs-lookup"><span data-stu-id="d029c-110">![Scenarios diagram](images/scenarios.jpg)</span></span>

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a><span data-ttu-id="d029c-111">方案 A：部署到云连接设备</span><span class="sxs-lookup"><span data-stu-id="d029c-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="d029c-112">HoloLens 2 部署为主要用于公司网络外部的环境。</span><span class="sxs-lookup"><span data-stu-id="d029c-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="d029c-113">不会访问公司资源，也不能通过 VPN 进行限制。</span><span class="sxs-lookup"><span data-stu-id="d029c-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="d029c-114">此部署类似于公司内托管的移动设备。</span><span class="sxs-lookup"><span data-stu-id="d029c-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="d029c-115">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="d029c-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="d029c-116">Wi-Fi 网络通常会完全公开到 Internet 和云服务。</span><span class="sxs-lookup"><span data-stu-id="d029c-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="d029c-117">Azure AD 加入移动设备管理 (MDM) 自动注册--MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="d029c-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="d029c-118">用户用自己的公司帐户登录 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="d029c-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="d029c-119">每个设备支持一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="d029c-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="d029c-120">根据特定用例（从完全打开到单应用展台）应用不同级别的设备锁定配置。</span><span class="sxs-lookup"><span data-stu-id="d029c-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="d029c-121">通过 MDM 部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="d029c-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="d029c-122">常见挑战</span><span class="sxs-lookup"><span data-stu-id="d029c-122">Common Challenges</span></span>
   * <span data-ttu-id="d029c-123">根据方案要求确定要应用于 HoloLens 2 的 MDM 配置。</span><span class="sxs-lookup"><span data-stu-id="d029c-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="d029c-124">对于类似于方案 A 的部署指南，请查看我们的 [云与远程协助连接](hololens2-cloud-connected-overview.md)的适用于 Cloud 2 的建议指南。</span><span class="sxs-lookup"><span data-stu-id="d029c-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d029c-125">部署指南–云连接的 HoloLens 2 （含远程协助）</span><span class="sxs-lookup"><span data-stu-id="d029c-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="d029c-126">方案 B：在组织的网络中部署</span><span class="sxs-lookup"><span data-stu-id="d029c-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="d029c-127">HoloLens 2 部署用于主要在公司网络上使用，可以访问内部公司资源。</span><span class="sxs-lookup"><span data-stu-id="d029c-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="d029c-128">Internet 和云服务可能受到限制。</span><span class="sxs-lookup"><span data-stu-id="d029c-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="d029c-129">此部署是大多数 Windows 10 电脑的典型部署。</span><span class="sxs-lookup"><span data-stu-id="d029c-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="d029c-130">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="d029c-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="d029c-131">Wi-Fi 网络是一种内部公司网络，有权访问内部资源，并限制了对 internet 或云服务的访问。</span><span class="sxs-lookup"><span data-stu-id="d029c-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="d029c-132">与 MDM 自动注册 Azure AD 联接</span><span class="sxs-lookup"><span data-stu-id="d029c-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="d029c-133">MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="d029c-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="d029c-134">用户用自己的公司帐户登录 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="d029c-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="d029c-135">每个设备支持一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="d029c-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="d029c-136">根据特定用例（从完全打开到单应用展台）应用不同级别的设备锁定配置。</span><span class="sxs-lookup"><span data-stu-id="d029c-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="d029c-137">通过 MDM 部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="d029c-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="d029c-138">常见挑战</span><span class="sxs-lookup"><span data-stu-id="d029c-138">Common Challenges</span></span>
   * <span data-ttu-id="d029c-139">HoloLens 2 不支持本地 AD 联接或 SCCM。</span><span class="sxs-lookup"><span data-stu-id="d029c-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="d029c-140">仅 Azure AD 加入 MDM。</span><span class="sxs-lookup"><span data-stu-id="d029c-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="d029c-141">如今，许多公司在这种情况下仍会将 Windows 10 电脑部署为本地 AD 加入设备，由 System Center Configuration Manager (SCCM) 管理，并且可能没有部署/配置基础结构来通过基于云的 MDM 解决方案来管理内部 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="d029c-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="d029c-142">因为 HoloLens 2 是云优先设备，所以它很大程度上依赖于连接 internet 和云连接的服务进行用户身份验证、操作系统更新、MDM 管理等。</span><span class="sxs-lookup"><span data-stu-id="d029c-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="d029c-143">在连接到公司网络时，可能需要对代理/防火墙规则进行调整，以便为 HoloLens 2 和在其上运行的应用程序启用访问权限。</span><span class="sxs-lookup"><span data-stu-id="d029c-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="d029c-144">企业 Wi-Fi 连接通常需要证书以向网络验证设备或用户。</span><span class="sxs-lookup"><span data-stu-id="d029c-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="d029c-145">配置所需的基础结构或设置，以通过 MDM 将证书部署到 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="d029c-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d029c-146">部署指南–公司连接的 HoloLens 2，含 Dynamics 365 指南</span><span class="sxs-lookup"><span data-stu-id="d029c-146">Deployment Guide – Corporate connected HoloLens 2 with Dynamics 365 Guides</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="d029c-147">方案 C：在安全脱机环境中部署</span><span class="sxs-lookup"><span data-stu-id="d029c-147">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="d029c-148">HoloLens 2 的部署目的是在没有网络或 internet 访问的情况下使用。</span><span class="sxs-lookup"><span data-stu-id="d029c-148">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="d029c-149">这是高度安全或机密位置的典型部署。</span><span class="sxs-lookup"><span data-stu-id="d029c-149">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="d029c-150">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="d029c-150">Basic Common Configurations</span></span>
   * <span data-ttu-id="d029c-151">Wi-Fi 连接处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="d029c-151">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="d029c-152">如果需要，可以为 LAN 连接启用通过 USB 的以太网。</span><span class="sxs-lookup"><span data-stu-id="d029c-152">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="d029c-153">非托管。</span><span class="sxs-lookup"><span data-stu-id="d029c-153">Not Managed.</span></span>
   * <span data-ttu-id="d029c-154">设备登录的本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d029c-154">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="d029c-155">HoloLens 2 仅支持一个本地帐户。</span><span class="sxs-lookup"><span data-stu-id="d029c-155">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="d029c-156">通过基于特定用例的预配包应用不同级别的设备锁定配置。</span><span class="sxs-lookup"><span data-stu-id="d029c-156">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="d029c-157">由于安全环境要求，这些配置通常会受到限制。</span><span class="sxs-lookup"><span data-stu-id="d029c-157">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="d029c-158">通过预配包部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="d029c-158">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="d029c-159">常见挑战</span><span class="sxs-lookup"><span data-stu-id="d029c-159">Common Challenges</span></span>
   * <span data-ttu-id="d029c-160">通过预配包提供一组有限的配置</span><span class="sxs-lookup"><span data-stu-id="d029c-160">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="d029c-161">无法使用云服务，因此限制了 HoloLens 2 功能。</span><span class="sxs-lookup"><span data-stu-id="d029c-161">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="d029c-162">更高的管理开销，因为这些设备必须手动设置、配置和更新。</span><span class="sxs-lookup"><span data-stu-id="d029c-162">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="d029c-163">对于类似于此方案的部署指南，请查看我们的 [脱机安全部署指南](hololens-common-scenarios-offline-secure.md)。</span><span class="sxs-lookup"><span data-stu-id="d029c-163">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d029c-164">部署指南–脱机安全 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d029c-164">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
