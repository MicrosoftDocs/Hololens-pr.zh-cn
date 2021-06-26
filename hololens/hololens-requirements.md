---
title: 在商业环境中规划 HoloLens 2 部署
description: 详细了解如何在企业环境中部署和管理 HoloLens，包括基础结构、Azure Active Directory 和移动设备管理。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bogenera
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: 2a0933bb754043934621a22ffa7764c9c88d93da
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924598"
---
# <a name="common-deployment-scenarios"></a><span data-ttu-id="be459-103">常见部署方案</span><span class="sxs-lookup"><span data-stu-id="be459-103">Common Deployment Scenarios</span></span>

## <a name="overview"></a><span data-ttu-id="be459-104">概述</span><span class="sxs-lookup"><span data-stu-id="be459-104">Overview</span></span>

<span data-ttu-id="be459-105">本页提供了在企业内部部署和管理 Microsoft HoloLens 2 设备时三个常见方案的高级体系结构概述。</span><span class="sxs-lookup"><span data-stu-id="be459-105">This page provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

<span data-ttu-id="be459-106">通常，管理设备和访问组织资源的方式很大程度上取决于已有的因素。</span><span class="sxs-lookup"><span data-stu-id="be459-106">Often, how you manage your devices and access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="be459-107">根据你的现有基础结构，我们邀请你在以下情况下查看常见的设备管理样式 (MDM) ，然后 [在商业环境中阅读规划 HoloLens 2 部署](hololens-core-components.md) ，以确定哪种方案符合你的需求。</span><span class="sxs-lookup"><span data-stu-id="be459-107">Based on your existing infrastructure, we invite you to review the common device management style (MDM) in the following scenarios and then read [Planning HoloLens 2 deployments in a commercial environment](hololens-core-components.md) to determine which scenario matches your needs.</span></span> <span data-ttu-id="be459-108">在部署过程中，还可以使用三个对应的指南。</span><span class="sxs-lookup"><span data-stu-id="be459-108">There are also three corresponding guides available for use during your deployment.</span></span>


 1. [<span data-ttu-id="be459-109">连接到云的环境部署指南</span><span class="sxs-lookup"><span data-stu-id="be459-109">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
     1. [<span data-ttu-id="be459-110">连接到云的环境（外部客户端）部署指南</span><span class="sxs-lookup"><span data-stu-id="be459-110">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)
 1. [<span data-ttu-id="be459-111">企业网络部署指南</span><span class="sxs-lookup"><span data-stu-id="be459-111">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)
 1. [<span data-ttu-id="be459-112">脱机安全环境部署指南</span><span class="sxs-lookup"><span data-stu-id="be459-112">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="be459-113">方案 A：部署到连接到云的设备</span><span class="sxs-lookup"><span data-stu-id="be459-113">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="be459-114">此方案相当于在公司中部署托管移动设备。</span><span class="sxs-lookup"><span data-stu-id="be459-114">This scenario is comparable to deploying managed mobile devices within a company.</span></span> <span data-ttu-id="be459-115">HoloLens 2 部署为主要用于公司网络外部的环境。</span><span class="sxs-lookup"><span data-stu-id="be459-115">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="be459-116">不会访问公司资源，也不能通过 VPN 进行限制。</span><span class="sxs-lookup"><span data-stu-id="be459-116">Corporate resources aren't accessed or may be limited through VPN.</span></span> 
 * <span data-ttu-id="be459-117">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="be459-117">Basic Common Configurations</span></span>
   * <span data-ttu-id="be459-118">Wi-Fi 网络通常会完全公开到 Internet 和云服务。</span><span class="sxs-lookup"><span data-stu-id="be459-118">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="be459-119">Azure AD 加入移动设备管理 (MDM) 自动注册--MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="be459-119">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="be459-120">用户用自己的公司帐户登录 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="be459-120">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="be459-121">每个设备支持一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="be459-121">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="be459-122">根据特定用例（从完全打开到单应用展台）应用不同级别的设备锁定配置。</span><span class="sxs-lookup"><span data-stu-id="be459-122">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="be459-123">通过 MDM 部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="be459-123">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="be459-124">常见挑战</span><span class="sxs-lookup"><span data-stu-id="be459-124">Common Challenges</span></span>
   * <span data-ttu-id="be459-125">根据方案要求确定要应用于 HoloLens 2 的 MDM 配置。</span><span class="sxs-lookup"><span data-stu-id="be459-125">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="be459-126">[![方案 A 关系图 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="be459-126">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="be459-127">对应的云连接指南介绍了如何将 HoloLens 2 注册到设备管理，根据需要应用许可证，并验证最终用户是否能够在设备设置时立即使用远程协助。</span><span class="sxs-lookup"><span data-stu-id="be459-127">The corresponding Cloud connected guide covers how to enroll HoloLens 2 into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="be459-128">使用外部客户端指南将设备部署到远程站点，以便短期或长期外部使用。</span><span class="sxs-lookup"><span data-stu-id="be459-128">Use the External Clients guide to deploy devices to a remote site for short-term or long-term external use.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="be459-129">连接到云的环境部署指南</span><span class="sxs-lookup"><span data-stu-id="be459-129">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="be459-130">连接到云的环境（外部客户端）部署指南</span><span class="sxs-lookup"><span data-stu-id="be459-130">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="be459-131">方案 B：在组织的网络中部署</span><span class="sxs-lookup"><span data-stu-id="be459-131">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="be459-132">此方案与大多数 Windows 10 电脑的经典部署相同。</span><span class="sxs-lookup"><span data-stu-id="be459-132">This scenario is identical to a classic deployment for most Windows 10 PCs.</span></span> <span data-ttu-id="be459-133">HoloLens 2 部署用于主要在公司网络上使用，可以访问内部公司资源。</span><span class="sxs-lookup"><span data-stu-id="be459-133">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="be459-134">Internet 和云服务可能受到限制。</span><span class="sxs-lookup"><span data-stu-id="be459-134">Internet and cloud services may be limited.</span></span> 

 * <span data-ttu-id="be459-135">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="be459-135">Basic Common Configurations</span></span>
   * <span data-ttu-id="be459-136">Wi-Fi 网络是一种内部公司网络，有权访问内部资源，并限制了对 internet 或云服务的访问。</span><span class="sxs-lookup"><span data-stu-id="be459-136">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="be459-137">与 MDM 自动注册 Azure AD 联接</span><span class="sxs-lookup"><span data-stu-id="be459-137">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="be459-138">MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="be459-138">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="be459-139">用户用自己的公司帐户登录 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="be459-139">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="be459-140">每个设备支持一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="be459-140">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="be459-141">根据特定用例（从完全打开到单应用展台）应用不同级别的设备锁定配置。</span><span class="sxs-lookup"><span data-stu-id="be459-141">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="be459-142">通过 MDM 部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="be459-142">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="be459-143">常见挑战</span><span class="sxs-lookup"><span data-stu-id="be459-143">Common Challenges</span></span>
   * <span data-ttu-id="be459-144">HoloLens 2 不支持本地 AD 联接或 SCCM。</span><span class="sxs-lookup"><span data-stu-id="be459-144">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="be459-145">仅 Azure AD 加入 MDM。</span><span class="sxs-lookup"><span data-stu-id="be459-145">Only Azure AD join with MDM.</span></span> <span data-ttu-id="be459-146">如今，许多公司在这种情况下仍会将 Windows 10 电脑部署为本地 AD 加入设备，由 System Center Configuration Manager (SCCM) 管理，并且可能没有部署/配置基础结构来通过基于云的 MDM 解决方案来管理内部 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="be459-146">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="be459-147">因为 HoloLens 2 是云优先设备，所以它很大程度上依赖于连接 internet 和云连接的服务进行用户身份验证、操作系统更新、MDM 管理等。</span><span class="sxs-lookup"><span data-stu-id="be459-147">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="be459-148">在连接到公司网络时，可能需要对代理/防火墙规则进行调整，以便为 HoloLens 2 和在其上运行的应用程序启用访问权限。</span><span class="sxs-lookup"><span data-stu-id="be459-148">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="be459-149">企业 Wi-Fi 连接通常需要证书以向网络验证设备或用户。</span><span class="sxs-lookup"><span data-stu-id="be459-149">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="be459-150">配置所需的基础结构或设置，以通过 MDM 将证书部署到 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="be459-150">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="be459-151">[![方案 B1 关系图 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="be459-151">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="be459-152">[![方案 B2 关系图 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="be459-152">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="be459-153">相应的企业网络指南将指导你如何将 HoloLens 2 注册到你的现有设备管理中，根据需要应用许可证，并验证你的最终用户是否能够操作 Dynamics 365 指南，以及如何在设备设置后使用自定义业务线应用。</span><span class="sxs-lookup"><span data-stu-id="be459-153">The corresponding Corporate network guide instructs on how to enroll HoloLens 2 into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="be459-154">企业网络部署指南</span><span class="sxs-lookup"><span data-stu-id="be459-154">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="be459-155">方案 C：在安全脱机环境中部署</span><span class="sxs-lookup"><span data-stu-id="be459-155">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="be459-156">这是高度安全或机密位置的典型部署。</span><span class="sxs-lookup"><span data-stu-id="be459-156">This is a typical deployment for highly secure or confidential locations.</span></span> <span data-ttu-id="be459-157">HoloLens 2 的部署目的是在没有网络或 internet 访问的情况下使用。</span><span class="sxs-lookup"><span data-stu-id="be459-157">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> 
 * <span data-ttu-id="be459-158">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="be459-158">Basic Common Configurations</span></span>
   * <span data-ttu-id="be459-159">Wi-Fi 连接处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="be459-159">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="be459-160">如果需要，可以为 LAN 连接启用通过 USB 的以太网。</span><span class="sxs-lookup"><span data-stu-id="be459-160">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="be459-161">非托管。</span><span class="sxs-lookup"><span data-stu-id="be459-161">Not Managed.</span></span>
   * <span data-ttu-id="be459-162">设备登录的本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="be459-162">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="be459-163">HoloLens 2 仅支持一个本地帐户。</span><span class="sxs-lookup"><span data-stu-id="be459-163">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="be459-164">通过基于特定用例的预配包应用不同级别的设备锁定配置。</span><span class="sxs-lookup"><span data-stu-id="be459-164">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="be459-165">由于安全环境要求，这些配置通常会受到限制。</span><span class="sxs-lookup"><span data-stu-id="be459-165">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="be459-166">通过预配包部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="be459-166">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="be459-167">常见挑战</span><span class="sxs-lookup"><span data-stu-id="be459-167">Common Challenges</span></span>
   * <span data-ttu-id="be459-168">通过预配包提供一组有限的配置</span><span class="sxs-lookup"><span data-stu-id="be459-168">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="be459-169">无法使用云服务，因此限制了 HoloLens 2 功能。</span><span class="sxs-lookup"><span data-stu-id="be459-169">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="be459-170">更高的管理开销，因为这些设备必须手动设置、配置和更新。</span><span class="sxs-lookup"><span data-stu-id="be459-170">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="be459-171">[![脱机安全图 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="be459-171">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="be459-172">对应的脱机安全指南提供了有关应用示例设置包的说明，该设置包将锁定 HoloLens 2 以便在安全环境中使用。</span><span class="sxs-lookup"><span data-stu-id="be459-172">The corresponding Offline secure guide provides instruction for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="be459-173">脱机安全环境部署指南</span><span class="sxs-lookup"><span data-stu-id="be459-173">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)


