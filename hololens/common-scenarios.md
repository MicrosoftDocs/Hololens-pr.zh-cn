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
ms.openlocfilehash: 30a35fb0fe5d5b669249df25ebff0228b552596c
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397410"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="e9f85-104">常见基础结构部署方案概述</span><span class="sxs-lookup"><span data-stu-id="e9f85-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="e9f85-105">以下信息概述了在企业中部署和管理 Microsoft HoloLens 2 台设备时三种常见方案。</span><span class="sxs-lookup"><span data-stu-id="e9f85-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="e9f85-106">通常，管理设备以及如何访问组织资源主要由已有因素决定。</span><span class="sxs-lookup"><span data-stu-id="e9f85-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="e9f85-107">根据现有基础结构，我们邀请你查看以下方案中的常见设备管理样式，并尝试我们的指南，以在符合需求的方案中进行部署。</span><span class="sxs-lookup"><span data-stu-id="e9f85-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="e9f85-108">方案</span><span class="sxs-lookup"><span data-stu-id="e9f85-108">Scenarios</span></span>

<span data-ttu-id="e9f85-109">下图表示两种典型的托管方案，适用于HoloLens 2方案。</span><span class="sxs-lookup"><span data-stu-id="e9f85-109">The diagram below represents two typical managed scenarios for HoloLens 2 deployments.</span></span>
 

<span data-ttu-id="e9f85-110">还有第三种方案允许脱机安全部署。</span><span class="sxs-lookup"><span data-stu-id="e9f85-110">There is also third scenario that allows for offline secure deployments.</span></span>

### <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="e9f85-111">方案 A：部署到已连接云的设备</span><span class="sxs-lookup"><span data-stu-id="e9f85-111">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="e9f85-112">HoloLens 2主要在企业网络外部的环境中使用。</span><span class="sxs-lookup"><span data-stu-id="e9f85-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="e9f85-113">不访问公司资源，或者可能会通过 VPN 限制公司资源。</span><span class="sxs-lookup"><span data-stu-id="e9f85-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="e9f85-114">此部署类似于公司内的托管移动设备。</span><span class="sxs-lookup"><span data-stu-id="e9f85-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="e9f85-115">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="e9f85-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="e9f85-116">Wi-Fi网络通常对 Internet 和云服务完全开放。</span><span class="sxs-lookup"><span data-stu-id="e9f85-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="e9f85-117">Azure AD Mobile 设备管理 (MDM) 自动注册 -MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="e9f85-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="e9f85-118">用户使用自己的公司帐户登录 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="e9f85-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="e9f85-119">支持每个设备的一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="e9f85-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="e9f85-120">根据特定用例应用不同级别的设备锁定配置，从"完全打开"到"单应用展台"。</span><span class="sxs-lookup"><span data-stu-id="e9f85-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="e9f85-121">通过 MDM 部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="e9f85-121">One or more applications are deployed via MDM</span></span>



* <span data-ttu-id="e9f85-122">常见挑战</span><span class="sxs-lookup"><span data-stu-id="e9f85-122">Common Challenges</span></span>
   * <span data-ttu-id="e9f85-123">根据方案要求确定要应用于 HoloLens 2 的 MDM 配置。</span><span class="sxs-lookup"><span data-stu-id="e9f85-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="e9f85-124">[![方案 A 关系图 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e9f85-124">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="e9f85-125">对于类似于此方案的部署指南，请查看我们的 [云连接环境部署](hololens2-cloud-connected-overview.md)指南指南。</span><span class="sxs-lookup"><span data-stu-id="e9f85-125">For a deployment guide that is similar to this scenario review our guide for [Cloud connected environment deployment guide](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e9f85-126">云连接环境部署指南</span><span class="sxs-lookup"><span data-stu-id="e9f85-126">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="e9f85-127">云连接环境 (外部客户端) 部署指南</span><span class="sxs-lookup"><span data-stu-id="e9f85-127">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="e9f85-128">方案 B：在组织的网络中部署</span><span class="sxs-lookup"><span data-stu-id="e9f85-128">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="e9f85-129">HoloLens 2 部署用于主要在公司网络上使用，可以访问内部公司资源。</span><span class="sxs-lookup"><span data-stu-id="e9f85-129">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="e9f85-130">Internet 和云服务可能受到限制。</span><span class="sxs-lookup"><span data-stu-id="e9f85-130">Internet and cloud services may be limited.</span></span> <span data-ttu-id="e9f85-131">此部署是大多数 Windows 10 电脑的典型部署。</span><span class="sxs-lookup"><span data-stu-id="e9f85-131">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="e9f85-132">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="e9f85-132">Basic Common Configurations</span></span>
   * <span data-ttu-id="e9f85-133">Wi-Fi 网络是一种内部公司网络，有权访问内部资源，并限制了对 internet 或云服务的访问。</span><span class="sxs-lookup"><span data-stu-id="e9f85-133">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="e9f85-134">与 MDM 自动注册 Azure AD 联接</span><span class="sxs-lookup"><span data-stu-id="e9f85-134">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="e9f85-135">MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="e9f85-135">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="e9f85-136">用户用自己的公司帐户登录 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="e9f85-136">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="e9f85-137">每个设备支持一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="e9f85-137">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="e9f85-138">根据特定用例（从完全打开到单应用展台）应用不同级别的设备锁定配置。</span><span class="sxs-lookup"><span data-stu-id="e9f85-138">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="e9f85-139">通过 MDM 部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="e9f85-139">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="e9f85-140">常见挑战</span><span class="sxs-lookup"><span data-stu-id="e9f85-140">Common Challenges</span></span>
   * <span data-ttu-id="e9f85-141">HoloLens 2 不支持本地 AD 联接或 SCCM。</span><span class="sxs-lookup"><span data-stu-id="e9f85-141">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="e9f85-142">仅Azure AD MDM 联接。</span><span class="sxs-lookup"><span data-stu-id="e9f85-142">Only Azure AD join with MDM.</span></span> <span data-ttu-id="e9f85-143">目前，许多公司仍在此方案中将 Windows 10 电脑部署为本地 AD 联接设备，由 System Center 配置服务器 (SCCM) 管理，并且可能尚未部署/配置基础结构，以通过基于云的 MDM 解决方案管理内部 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="e9f85-143">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="e9f85-144">由于HoloLens 2云第一设备，因此它严重依赖于 Internet 和云连接服务进行用户身份验证、OS 更新、MDM 管理等。</span><span class="sxs-lookup"><span data-stu-id="e9f85-144">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="e9f85-145">连接到公司网络时，很可能需要调整代理/防火墙规则，以启用对 HoloLens 2 及其运行的应用程序的访问。</span><span class="sxs-lookup"><span data-stu-id="e9f85-145">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="e9f85-146">企业Wi-Fi连接通常需要证书来向网络验证设备或用户身份。</span><span class="sxs-lookup"><span data-stu-id="e9f85-146">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="e9f85-147">通过 MDM 将证书部署到 Windows 10所需的基础结构或设置可能难以配置。</span><span class="sxs-lookup"><span data-stu-id="e9f85-147">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="e9f85-148">[![方案 B1 示意图 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e9f85-148">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="e9f85-149">[![方案 B2 示意图 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e9f85-149">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="e9f85-150">有关与此方案类似的部署指南，请查看企业 [网络部署指南](hololens2-corp-connected-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e9f85-150">For a deployment guide that is similar to this scenario review our guide for [Corporate network deployment guide](hololens2-corp-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e9f85-151">企业网络部署指南</span><span class="sxs-lookup"><span data-stu-id="e9f85-151">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="e9f85-152">方案 C：在安全的脱机环境中部署</span><span class="sxs-lookup"><span data-stu-id="e9f85-152">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="e9f85-153">HoloLens 2部署 ，主要以脱机方式使用，无需网络或 Internet 访问。</span><span class="sxs-lookup"><span data-stu-id="e9f85-153">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="e9f85-154">这是高度安全或机密位置的典型部署。</span><span class="sxs-lookup"><span data-stu-id="e9f85-154">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="e9f85-155">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="e9f85-155">Basic Common Configurations</span></span>
   * <span data-ttu-id="e9f85-156">Wi-Fi连接已禁用。</span><span class="sxs-lookup"><span data-stu-id="e9f85-156">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="e9f85-157">如有必要，可以通过 USB 为 LAN 连接启用以太网。</span><span class="sxs-lookup"><span data-stu-id="e9f85-157">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="e9f85-158">非托管。</span><span class="sxs-lookup"><span data-stu-id="e9f85-158">Not Managed.</span></span>
   * <span data-ttu-id="e9f85-159">用于设备登录的本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e9f85-159">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="e9f85-160">HoloLens 2仅支持一个本地帐户。</span><span class="sxs-lookup"><span data-stu-id="e9f85-160">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="e9f85-161">根据特定用例，通过预配包应用不同级别的设备锁定配置。</span><span class="sxs-lookup"><span data-stu-id="e9f85-161">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="e9f85-162">由于安全环境要求，这些配置通常会受到限制。</span><span class="sxs-lookup"><span data-stu-id="e9f85-162">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="e9f85-163">通过预配包部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="e9f85-163">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="e9f85-164">常见挑战</span><span class="sxs-lookup"><span data-stu-id="e9f85-164">Common Challenges</span></span>
   * <span data-ttu-id="e9f85-165">通过预配包提供一组有限的配置</span><span class="sxs-lookup"><span data-stu-id="e9f85-165">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="e9f85-166">无法使用云服务，因此限制了 HoloLens 2 功能。</span><span class="sxs-lookup"><span data-stu-id="e9f85-166">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="e9f85-167">更高的管理开销，因为这些设备必须手动设置、配置和更新。</span><span class="sxs-lookup"><span data-stu-id="e9f85-167">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="e9f85-168">[![脱机安全图 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="e9f85-168">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="e9f85-169">对于类似于此方案的部署指南，请查看我们的 [脱机安全环境部署指南](hololens-common-scenarios-offline-secure.md)。</span><span class="sxs-lookup"><span data-stu-id="e9f85-169">For a deployment guide that is similar to this scenario review our [Offline secure environment deployment guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e9f85-170">脱机安全环境部署指南</span><span class="sxs-lookup"><span data-stu-id="e9f85-170">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)
