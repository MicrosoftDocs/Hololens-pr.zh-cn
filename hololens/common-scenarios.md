---
title: 常见基础结构部署方案
description: 某些基于不同通用基础结构的常见部署方案
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 11/04/2020
keywords: Hololens
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
ms.openlocfilehash: e9e91535bb49b5076547e8b9934bdc86808d41fc
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195565"
---
# <span data-ttu-id="549db-104">常见基础结构部署方案概述</span><span class="sxs-lookup"><span data-stu-id="549db-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="549db-105">以下信息提供了在企业内部部署和管理 Microsoft HoloLens 2 设备的三种常见方案的高级体系结构概述。</span><span class="sxs-lookup"><span data-stu-id="549db-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="549db-106">通常情况下，你管理设备的方式以及如何访问组织的资源在很大程度上取决于已存在的因素。</span><span class="sxs-lookup"><span data-stu-id="549db-106">Often how you manage your devices and how access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="549db-107">根据现有的基础结构，我们邀请你查看以下方案中的常见设备管理样式，并尝试在符合你的需求的方案中部署指南。</span><span class="sxs-lookup"><span data-stu-id="549db-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <span data-ttu-id="549db-108">方案</span><span class="sxs-lookup"><span data-stu-id="549db-108">Scenarios</span></span>

<span data-ttu-id="549db-109">下图表示 HoloLens 2 部署的三种典型方案。</span><span class="sxs-lookup"><span data-stu-id="549db-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![方案图表](images/scenarios.jpg)

### <span data-ttu-id="549db-111">方案 A：部署到云连接设备</span><span class="sxs-lookup"><span data-stu-id="549db-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="549db-112">HoloLens 2 部署主要用于企业网络外部的环境。</span><span class="sxs-lookup"><span data-stu-id="549db-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="549db-113">公司资源不会被访问或通过 VPN 限制。</span><span class="sxs-lookup"><span data-stu-id="549db-113">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="549db-114">这是一个与公司中托管的移动设备非常类似的部署。</span><span class="sxs-lookup"><span data-stu-id="549db-114">This is a deployment very similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="549db-115">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="549db-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="549db-116">Wi-Fi 网络通常完全开放于 Internet 和云服务。</span><span class="sxs-lookup"><span data-stu-id="549db-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="549db-117">具有 MDM 自动注册的 Azure AD 联接-MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="549db-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
   * <span data-ttu-id="549db-118">用户利用其自己的公司帐户登录 (AAD) </span><span class="sxs-lookup"><span data-stu-id="549db-118">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="549db-119">每个设备支持的单个或多个用户</span><span class="sxs-lookup"><span data-stu-id="549db-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="549db-120">不同级别的设备锁定配置基于特定使用情形（从完全打开到单应用展台）应用。</span><span class="sxs-lookup"><span data-stu-id="549db-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="549db-121">一个或多个应用程序通过 MDM 进行部署</span><span class="sxs-lookup"><span data-stu-id="549db-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="549db-122">常见挑战</span><span class="sxs-lookup"><span data-stu-id="549db-122">Common Challenges</span></span>
   * <span data-ttu-id="549db-123">根据方案要求确定要对 HoloLens 2 应用哪些 MDM 配置。</span><span class="sxs-lookup"><span data-stu-id="549db-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="549db-124">有关类似于本方案的部署指南，请参阅我们 [与远程协助配合使用的云与 "远程协助" 联系](hololens2-cloud-connected-overview.md)的指南。</span><span class="sxs-lookup"><span data-stu-id="549db-124">For a deployment guide that is similar to this scenario please review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="549db-125">部署指南-云连接了 HoloLens 2 和远程协助</span><span class="sxs-lookup"><span data-stu-id="549db-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <span data-ttu-id="549db-126">情形 B：在您的组织的网络内部署</span><span class="sxs-lookup"><span data-stu-id="549db-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="549db-127">HoloLens 2 已部署为主要在企业网络上使用，可访问内部公司资源。</span><span class="sxs-lookup"><span data-stu-id="549db-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="549db-128">互联网和云服务可能会受到限制。</span><span class="sxs-lookup"><span data-stu-id="549db-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="549db-129">这是大多数 Windows 10 电脑的典型部署。</span><span class="sxs-lookup"><span data-stu-id="549db-129">This is a typical deployment for most Windows 10 PCs.</span></span>
 * <span data-ttu-id="549db-130">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="549db-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="549db-131">Wi-Fi 网络是一种内部公司网络，具有对内部资源的访问权限，并且对 internet 或云服务的访问受限。</span><span class="sxs-lookup"><span data-stu-id="549db-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="549db-132">具有 MDM 自动注册的 Azure AD 联接</span><span class="sxs-lookup"><span data-stu-id="549db-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="549db-133">MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="549db-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="549db-134">用户利用其自己的公司帐户登录 (AAD) </span><span class="sxs-lookup"><span data-stu-id="549db-134">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="549db-135">每个设备支持的单个或多个用户</span><span class="sxs-lookup"><span data-stu-id="549db-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="549db-136">不同级别的设备锁定配置基于特定使用情形（从完全打开到单应用展台）应用。</span><span class="sxs-lookup"><span data-stu-id="549db-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="549db-137">一个或多个应用程序通过 MDM 进行部署</span><span class="sxs-lookup"><span data-stu-id="549db-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="549db-138">常见挑战</span><span class="sxs-lookup"><span data-stu-id="549db-138">Common Challenges</span></span>
   * <span data-ttu-id="549db-139">HoloLens 2 不支持本地广告加入或 SCCM。</span><span class="sxs-lookup"><span data-stu-id="549db-139">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="549db-140">仅适用于 MDM 的 Azure AD 加入。</span><span class="sxs-lookup"><span data-stu-id="549db-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="549db-141">目前，许多公司仍在此方案中部署 Windows 10 电脑，因为在本地加入广告的设备（由 System Center Configuration Manager (SCCM) 托管），并且可能没有部署/配置的基础结构，以便通过基于云的 MDM 解决方案管理内部 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="549db-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud based MDM solutions.</span></span>
   * <span data-ttu-id="549db-142">由于 HoloLens 2 是云优先设备，因此它很大程度上依赖于 internet 和云连接的服务，用于用户身份验证、操作系统更新、MDM 管理等。连接到公司网络时，很可能需要对代理/防火墙规则进行调整，以便为 HoloLens 2 和在其上运行的应用程序启用访问权限。</span><span class="sxs-lookup"><span data-stu-id="549db-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="549db-143">企业 Wi-Fi 连接通常需要证书来对网络上的设备或用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="549db-143">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="549db-144">配置所需的基础结构或设置以通过 MDM 将证书部署到 Windows 10 设备的难度很大。</span><span class="sxs-lookup"><span data-stu-id="549db-144">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="549db-145">方案 C：在安全的脱机环境中部署</span><span class="sxs-lookup"><span data-stu-id="549db-145">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="549db-146">HoloLens 2 已部署为主要在没有网络或 internet 访问的情况下脱机使用。</span><span class="sxs-lookup"><span data-stu-id="549db-146">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="549db-147">这是对高度安全或机密位置的典型部署。</span><span class="sxs-lookup"><span data-stu-id="549db-147">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="549db-148">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="549db-148">Basic Common Configurations</span></span>
   * <span data-ttu-id="549db-149">Wi-Fi 连接已被禁用。</span><span class="sxs-lookup"><span data-stu-id="549db-149">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="549db-150">如果需要，可通过 USB 使用以太网进行局域网连接。</span><span class="sxs-lookup"><span data-stu-id="549db-150">Ethernet via USB may be enabled for LAN connectivity if required.</span></span>
   * <span data-ttu-id="549db-151">不受管理。</span><span class="sxs-lookup"><span data-stu-id="549db-151">Not Managed.</span></span>
   * <span data-ttu-id="549db-152">设备登录的本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="549db-152">Local user account for device sign in.</span></span>
     * <span data-ttu-id="549db-153">HoloLens 2 仅支持1个本地帐户。</span><span class="sxs-lookup"><span data-stu-id="549db-153">HoloLens 2 supports only 1 local account.</span></span>
   * <span data-ttu-id="549db-154">不同级别的设备锁定配置通过基于特定使用案例的预配包进行应用。</span><span class="sxs-lookup"><span data-stu-id="549db-154">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="549db-155">这些配置通常因安全环境要求而受到严格限制。</span><span class="sxs-lookup"><span data-stu-id="549db-155">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="549db-156">通过预配包部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="549db-156">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="549db-157">常见挑战</span><span class="sxs-lookup"><span data-stu-id="549db-157">Common Challenges</span></span>
   * <span data-ttu-id="549db-158">预配程序包提供了一组有限的配置</span><span class="sxs-lookup"><span data-stu-id="549db-158">There are a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="549db-159">云服务无法利用，因此限制了 HoloLens 2 功能。</span><span class="sxs-lookup"><span data-stu-id="549db-159">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="549db-160">更高的管理开销，因为这些设备必须手动设置、配置和更新。</span><span class="sxs-lookup"><span data-stu-id="549db-160">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>

<span data-ttu-id="549db-161">有关类似于此方案的部署指南，请参阅我们的 [脱机安全部署指南](hololens-common-scenarios-offline-secure.md)。</span><span class="sxs-lookup"><span data-stu-id="549db-161">For a deployment guide that is similar to this scenario please review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="549db-162">部署指南–脱机安全的 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="549db-162">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
