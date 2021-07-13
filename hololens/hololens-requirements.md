---
title: 常见部署方案
description: 详细了解在企业环境中部署和管理HoloLens，包括基础结构、Azure Active Directory和移动设备管理。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 88bf50aa-0bac-4142-afa4-20b37c013001
author: bgener
ms.author: bogenera
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/04/2020
appliesto:
- HoloLens 2
ms.openlocfilehash: ccccdcc7d3188919d02eb5855131137415c12d16
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639822"
---
# <a name="common-deployment-scenarios"></a><span data-ttu-id="a822c-103">常见部署方案</span><span class="sxs-lookup"><span data-stu-id="a822c-103">Common Deployment Scenarios</span></span>

## <a name="overview"></a><span data-ttu-id="a822c-104">概述</span><span class="sxs-lookup"><span data-stu-id="a822c-104">Overview</span></span>

<span data-ttu-id="a822c-105">本页提供在企业中部署和管理 Microsoft HoloLens 2 台设备时三种常见方案的概要体系结构概述。</span><span class="sxs-lookup"><span data-stu-id="a822c-105">This page provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

<span data-ttu-id="a822c-106">通常，管理设备和访问组织资源大致取决于已有的因素。</span><span class="sxs-lookup"><span data-stu-id="a822c-106">Often, how you manage your devices and access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="a822c-107">根据现有的基础结构，我们邀请你查看以下方案中常见的设备管理样式 (MDM) ，然后阅读在商业环境中规划[HoloLens 2](hololens-core-components.md)部署，以确定哪种方案符合你的需求。</span><span class="sxs-lookup"><span data-stu-id="a822c-107">Based on your existing infrastructure, we invite you to review the common device management style (MDM) in the following scenarios and then read [Planning HoloLens 2 deployments in a commercial environment](hololens-core-components.md) to determine which scenario matches your needs.</span></span> <span data-ttu-id="a822c-108">在部署期间，还有三个相应的指南可供使用。</span><span class="sxs-lookup"><span data-stu-id="a822c-108">There are also three corresponding guides available for use during your deployment.</span></span>


 1. [<span data-ttu-id="a822c-109">连接到云的环境部署指南</span><span class="sxs-lookup"><span data-stu-id="a822c-109">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)
     1. [<span data-ttu-id="a822c-110">连接到云的环境（外部客户端）部署指南</span><span class="sxs-lookup"><span data-stu-id="a822c-110">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)
 1. [<span data-ttu-id="a822c-111">企业网络部署指南</span><span class="sxs-lookup"><span data-stu-id="a822c-111">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)
 1. [<span data-ttu-id="a822c-112">脱机安全环境部署指南</span><span class="sxs-lookup"><span data-stu-id="a822c-112">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)

## <a name="scenario-a-deploy-to-cloud-connected-devices"></a><span data-ttu-id="a822c-113">方案 A：部署到已连接云的设备</span><span class="sxs-lookup"><span data-stu-id="a822c-113">Scenario A: Deploy to cloud connected devices</span></span>

<span data-ttu-id="a822c-114">此方案相当于在公司内部署托管移动设备。</span><span class="sxs-lookup"><span data-stu-id="a822c-114">This scenario is comparable to deploying managed mobile devices within a company.</span></span> <span data-ttu-id="a822c-115">HoloLens 2主要在企业网络外部的环境中使用。</span><span class="sxs-lookup"><span data-stu-id="a822c-115">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="a822c-116">不访问公司资源，或者可能会通过 VPN 限制公司资源。</span><span class="sxs-lookup"><span data-stu-id="a822c-116">Corporate resources aren't accessed or may be limited through VPN.</span></span> 
 * <span data-ttu-id="a822c-117">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="a822c-117">Basic Common Configurations</span></span>
   * <span data-ttu-id="a822c-118">Wi-Fi网络通常对 Internet 和云服务完全开放。</span><span class="sxs-lookup"><span data-stu-id="a822c-118">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="a822c-119">Azure AD Mobile 设备管理 (MDM) 自动注册 -MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="a822c-119">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="a822c-120">用户使用自己的公司帐户登录 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="a822c-120">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="a822c-121">支持每个设备的一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="a822c-121">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="a822c-122">根据特定用例应用不同级别的设备锁定配置，从"完全打开"到"单应用展台"。</span><span class="sxs-lookup"><span data-stu-id="a822c-122">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="a822c-123">通过 MDM 部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="a822c-123">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="a822c-124">常见挑战</span><span class="sxs-lookup"><span data-stu-id="a822c-124">Common Challenges</span></span>
   * <span data-ttu-id="a822c-125">根据方案要求确定HoloLens 2的 MDM 配置。</span><span class="sxs-lookup"><span data-stu-id="a822c-125">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="a822c-126">[![方案关系图 ](images/deployment-guides-revised-scenario-a.png)](images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a822c-126">[ ![Scenario A diagram](images/deployment-guides-revised-scenario-a.png) ](images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>

<span data-ttu-id="a822c-127">相应的云连接指南介绍如何将 HoloLens 2注册到设备管理中，根据需要应用许可证，并验证最终用户能否在设备设置Remote Assist立即使用许可证。</span><span class="sxs-lookup"><span data-stu-id="a822c-127">The corresponding Cloud connected guide covers how to enroll HoloLens 2 into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="a822c-128">使用外部客户端指南将设备部署到远程站点，供短期或长期外部使用。</span><span class="sxs-lookup"><span data-stu-id="a822c-128">Use the External Clients guide to deploy devices to a remote site for short-term or long-term external use.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a822c-129">连接到云的环境部署指南</span><span class="sxs-lookup"><span data-stu-id="a822c-129">Cloud connected environment deployment guide</span></span>](hololens2-cloud-connected-overview.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="a822c-130">连接到云的环境（外部客户端）部署指南</span><span class="sxs-lookup"><span data-stu-id="a822c-130">Cloud connected environment (External Clients) deployment guide</span></span>](hololens2-deployment-guide.md)

## <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="a822c-131">方案 B：在组织的网络中部署</span><span class="sxs-lookup"><span data-stu-id="a822c-131">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="a822c-132">此方案与大多数电脑的经典部署Windows 10相同。</span><span class="sxs-lookup"><span data-stu-id="a822c-132">This scenario is identical to a classic deployment for most Windows 10 PCs.</span></span> <span data-ttu-id="a822c-133">HoloLens 2部署，主要在有权访问内部公司资源的公司网络上使用。</span><span class="sxs-lookup"><span data-stu-id="a822c-133">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="a822c-134">Internet 和云服务可能会受到限制。</span><span class="sxs-lookup"><span data-stu-id="a822c-134">Internet and cloud services may be limited.</span></span> 

 * <span data-ttu-id="a822c-135">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="a822c-135">Basic Common Configurations</span></span>
   * <span data-ttu-id="a822c-136">Wi-Fi网络是一个内部企业网络，可以访问内部资源，并且对 Internet 或云服务的访问有限。</span><span class="sxs-lookup"><span data-stu-id="a822c-136">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="a822c-137">Azure AD MDM 自动注册加入</span><span class="sxs-lookup"><span data-stu-id="a822c-137">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="a822c-138">MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="a822c-138">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="a822c-139">用户使用自己的公司帐户登录 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="a822c-139">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="a822c-140">支持每个设备的一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="a822c-140">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="a822c-141">根据特定用例应用不同级别的设备锁定配置，从"完全打开"到"单应用展台"。</span><span class="sxs-lookup"><span data-stu-id="a822c-141">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="a822c-142">通过 MDM 部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="a822c-142">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="a822c-143">常见挑战</span><span class="sxs-lookup"><span data-stu-id="a822c-143">Common Challenges</span></span>
   * <span data-ttu-id="a822c-144">HoloLens 2不支持本地 AD 联接或 SCCM。</span><span class="sxs-lookup"><span data-stu-id="a822c-144">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="a822c-145">仅Azure AD MDM 联接。</span><span class="sxs-lookup"><span data-stu-id="a822c-145">Only Azure AD join with MDM.</span></span> <span data-ttu-id="a822c-146">目前，许多公司仍在此方案中将 Windows 10 PC 部署为本地 AD 联接设备，由 System Center Configuration Manager (SCCM) 管理，并且可能尚未部署/配置基础结构，以通过基于云的 MDM 解决方案管理内部 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="a822c-146">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="a822c-147">由于HoloLens 2云第一设备，因此它严重依赖于 Internet 和云连接服务进行用户身份验证、OS 更新、MDM 管理等。</span><span class="sxs-lookup"><span data-stu-id="a822c-147">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="a822c-148">连接到公司网络时，很可能需要调整代理/防火墙规则，以启用对 HoloLens 2 及其运行的应用程序的访问。</span><span class="sxs-lookup"><span data-stu-id="a822c-148">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="a822c-149">企业Wi-Fi连接通常需要证书来向网络验证设备或用户身份。</span><span class="sxs-lookup"><span data-stu-id="a822c-149">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="a822c-150">通过 MDM 将证书部署到 Windows 10所需的基础结构或设置可能难以配置。</span><span class="sxs-lookup"><span data-stu-id="a822c-150">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

<span data-ttu-id="a822c-151">[![方案 B1 示意图 ](images/deployment-guides-revised-scenario-b-01-1.png)](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a822c-151">[ ![Scenario B1 diagram](images/deployment-guides-revised-scenario-b-01-1.png) ](images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="a822c-152">[![方案 B2 示意图 ](images/deployment-guides-revised-scenario-b-02-1.png)](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a822c-152">[ ![Scenario B2 diagram](images/deployment-guides-revised-scenario-b-02-1.png) ](images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

<span data-ttu-id="a822c-153">相应的企业网络指南指导如何在设置设备后将 HoloLens 2 注册到现有设备管理中、根据需要应用许可证，并验证最终用户是否能够操作 Dynamics 365 指南以及使用自定义业务线应用。</span><span class="sxs-lookup"><span data-stu-id="a822c-153">The corresponding Corporate network guide instructs on how to enroll HoloLens 2 into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a822c-154">企业网络部署指南</span><span class="sxs-lookup"><span data-stu-id="a822c-154">Corporate network deployment guide</span></span>](hololens2-corp-connected-overview.md)

## <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="a822c-155">方案 C：在安全的脱机环境中部署</span><span class="sxs-lookup"><span data-stu-id="a822c-155">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="a822c-156">这是高度安全或机密位置的典型部署。</span><span class="sxs-lookup"><span data-stu-id="a822c-156">This is a typical deployment for highly secure or confidential locations.</span></span> <span data-ttu-id="a822c-157">HoloLens 2部署 ，主要以脱机方式使用，无需网络或 Internet 访问。</span><span class="sxs-lookup"><span data-stu-id="a822c-157">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> 
 * <span data-ttu-id="a822c-158">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="a822c-158">Basic Common Configurations</span></span>
   * <span data-ttu-id="a822c-159">Wi-Fi连接已禁用。</span><span class="sxs-lookup"><span data-stu-id="a822c-159">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="a822c-160">如有必要，可以通过 USB 为 LAN 连接启用以太网。</span><span class="sxs-lookup"><span data-stu-id="a822c-160">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="a822c-161">非托管。</span><span class="sxs-lookup"><span data-stu-id="a822c-161">Not Managed.</span></span>
   * <span data-ttu-id="a822c-162">用于设备登录的本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a822c-162">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="a822c-163">HoloLens 2仅支持一个本地帐户。</span><span class="sxs-lookup"><span data-stu-id="a822c-163">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="a822c-164">根据特定用例，通过预配包应用不同级别的设备锁定配置。</span><span class="sxs-lookup"><span data-stu-id="a822c-164">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="a822c-165">由于安全环境要求，这些配置通常受到限制。</span><span class="sxs-lookup"><span data-stu-id="a822c-165">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="a822c-166">通过预配包部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="a822c-166">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="a822c-167">常见挑战</span><span class="sxs-lookup"><span data-stu-id="a822c-167">Common Challenges</span></span>
   * <span data-ttu-id="a822c-168">可以通过预配包使用有限的一组配置</span><span class="sxs-lookup"><span data-stu-id="a822c-168">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="a822c-169">云服务无法使用，因此限制了HoloLens 2功能。</span><span class="sxs-lookup"><span data-stu-id="a822c-169">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="a822c-170">由于必须手动设置、配置和更新这些设备，因此管理开销较高。</span><span class="sxs-lookup"><span data-stu-id="a822c-170">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="a822c-171">[![脱机安全关系图 1 ](images/deployment-guides-revised-scenario-c-01.png)](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a822c-171">[ ![Offline Secure diagram 1](images/deployment-guides-revised-scenario-c-01.png) ](images/deployment-guides-revised-scenario-c-01.png#lightbox)</span></span>

<span data-ttu-id="a822c-172">相应的脱机安全指南提供有关应用示例预配包的指导，该包将锁定HoloLens 2以在安全环境中使用。</span><span class="sxs-lookup"><span data-stu-id="a822c-172">The corresponding Offline secure guide provides instruction for applying a sample Provisioning Package that will lock down a HoloLens 2 for use in secure environments.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a822c-173">脱机安全环境部署指南</span><span class="sxs-lookup"><span data-stu-id="a822c-173">Offline secure environment deployment guide</span></span>](hololens-common-scenarios-offline-secure.md)


