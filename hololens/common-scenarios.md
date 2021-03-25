---
title: 常见基础结构部署方案
description: 了解一些基于混合现实的不同基础结构部署的最常见部署方案。
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 3/24/2021
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
ms.openlocfilehash: 4b9bd4335e45180276d69af2ce5f33a38ecb800f
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448490"
---
# <a name="common-infrastructure-deployment-scenarios-overview"></a><span data-ttu-id="00a8c-104">常见基础结构部署方案概述</span><span class="sxs-lookup"><span data-stu-id="00a8c-104">Common Infrastructure Deployment Scenarios Overview</span></span>

<span data-ttu-id="00a8c-105">以下信息提供了在企业内部署和管理 Microsoft HoloLens 2 设备时三种常见方案高级体系结构概述。</span><span class="sxs-lookup"><span data-stu-id="00a8c-105">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span> <span data-ttu-id="00a8c-106">通常，设备管理方式和访问组织资源方式很大程度上取决于已有因素。</span><span class="sxs-lookup"><span data-stu-id="00a8c-106">Often how you manage your devices and how to access your organization's resources is largely determined by factors already in place.</span></span> <span data-ttu-id="00a8c-107">基于现有基础结构，我们邀请你查看以下方案中的常见设备管理风格，并尝试我们的指南，以在满足你需求的方案中进行部署。</span><span class="sxs-lookup"><span data-stu-id="00a8c-107">Based on the existing infrastructure we invite you to review the common device management style in the following scenarios, and try out our guides for deploying in the scenario matching your needs.</span></span>

## <a name="scenarios"></a><span data-ttu-id="00a8c-108">方案</span><span class="sxs-lookup"><span data-stu-id="00a8c-108">Scenarios</span></span>

<span data-ttu-id="00a8c-109">下图显示了 HoloLens 2 部署的三种典型方案。</span><span class="sxs-lookup"><span data-stu-id="00a8c-109">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span>
![方案图](images/scenarios.jpg)

### <a name="scenario-a-deploy-to-cloud-connect-devices"></a><span data-ttu-id="00a8c-111">方案 A：部署到云连接设备</span><span class="sxs-lookup"><span data-stu-id="00a8c-111">Scenario A: Deploy to cloud connect devices</span></span>

<span data-ttu-id="00a8c-112">HoloLens 2 已部署，主要在企业网络外部的环境中使用。</span><span class="sxs-lookup"><span data-stu-id="00a8c-112">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="00a8c-113">公司资源无法访问或可能通过 VPN 受限。</span><span class="sxs-lookup"><span data-stu-id="00a8c-113">Corporate resources aren't accessed or may be limited through VPN.</span></span> <span data-ttu-id="00a8c-114">此部署类似于公司内的托管移动设备。</span><span class="sxs-lookup"><span data-stu-id="00a8c-114">This  deployment is similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="00a8c-115">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="00a8c-115">Basic Common Configurations</span></span>
   * <span data-ttu-id="00a8c-116">Wi-Fi网络通常完全开放到 Internet 和云服务。</span><span class="sxs-lookup"><span data-stu-id="00a8c-116">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="00a8c-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment --MDM (Intune) Managed</span><span class="sxs-lookup"><span data-stu-id="00a8c-117">Azure AD Join with Mobile Device Management (MDM) Auto Enrollment--MDM (Intune) Managed</span></span>
   * <span data-ttu-id="00a8c-118">用户使用自己的公司帐户在 Azure AD (登录) </span><span class="sxs-lookup"><span data-stu-id="00a8c-118">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="00a8c-119">支持每个设备的一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="00a8c-119">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="00a8c-120">根据特定用例（从完全打开到单个应用展台）应用不同级别的设备锁定配置。</span><span class="sxs-lookup"><span data-stu-id="00a8c-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="00a8c-121">通过 MDM 部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="00a8c-121">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="00a8c-122">常见挑战</span><span class="sxs-lookup"><span data-stu-id="00a8c-122">Common Challenges</span></span>
   * <span data-ttu-id="00a8c-123">根据方案要求确定应用于 HoloLens 2 的 MDM 配置。</span><span class="sxs-lookup"><span data-stu-id="00a8c-123">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

<span data-ttu-id="00a8c-124">有关与方案类似的部署指南，请查看我们的云连接 [HoloLens 2 和远程协助指南](hololens2-cloud-connected-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="00a8c-124">For a deployment guide that is similar to scenario A review our guide for [Cloud connected HoloLens 2 with Remote Assist](hololens2-cloud-connected-overview.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="00a8c-125">部署指南 – 云连接的 HoloLens 2 与远程协助</span><span class="sxs-lookup"><span data-stu-id="00a8c-125">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist</span></span>](hololens2-cloud-connected-overview.md)

### <a name="scenario-b-deploy-inside-your-organizations-network"></a><span data-ttu-id="00a8c-126">方案 B：在组织的网络内部部署</span><span class="sxs-lookup"><span data-stu-id="00a8c-126">Scenario B: Deploy inside your organization's network</span></span>

<span data-ttu-id="00a8c-127">HoloLens 2 主要部署在可以访问内部公司资源的公司网络上使用。</span><span class="sxs-lookup"><span data-stu-id="00a8c-127">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="00a8c-128">Internet 和云服务可能会受到限制。</span><span class="sxs-lookup"><span data-stu-id="00a8c-128">Internet and cloud services may be limited.</span></span> <span data-ttu-id="00a8c-129">此部署是大多数 Windows 10 电脑的典型部署。</span><span class="sxs-lookup"><span data-stu-id="00a8c-129">This deployment is a typical deployment for most Windows 10 PCs.</span></span>

 * <span data-ttu-id="00a8c-130">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="00a8c-130">Basic Common Configurations</span></span>
   * <span data-ttu-id="00a8c-131">Wi-Fi网络是一个内部企业网络，可以访问内部资源，并且对 Internet 或云服务的访问受到限制。</span><span class="sxs-lookup"><span data-stu-id="00a8c-131">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="00a8c-132">通过 MDM 自动注册加入 Azure AD</span><span class="sxs-lookup"><span data-stu-id="00a8c-132">Azure AD Join with MDM Auto Enrollment</span></span>
   * <span data-ttu-id="00a8c-133">Mdm (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="00a8c-133">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="00a8c-134">用户使用自己的公司帐户在 Azure AD (登录) </span><span class="sxs-lookup"><span data-stu-id="00a8c-134">Users sign in with their own corporate account (Azure AD)</span></span>
     * <span data-ttu-id="00a8c-135">支持每个设备的一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="00a8c-135">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="00a8c-136">根据特定用例（从完全打开到单个应用展台）应用不同级别的设备锁定配置。</span><span class="sxs-lookup"><span data-stu-id="00a8c-136">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="00a8c-137">通过 MDM 部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="00a8c-137">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="00a8c-138">常见挑战</span><span class="sxs-lookup"><span data-stu-id="00a8c-138">Common Challenges</span></span>
   * <span data-ttu-id="00a8c-139">HoloLens 2 不支持本地 AD 加入或 SCCM。</span><span class="sxs-lookup"><span data-stu-id="00a8c-139">HoloLens 2 doesn't support on premises AD join or SCCM.</span></span> <span data-ttu-id="00a8c-140">仅 Azure AD 与 MDM 联接。</span><span class="sxs-lookup"><span data-stu-id="00a8c-140">Only Azure AD join with MDM.</span></span> <span data-ttu-id="00a8c-141">目前，许多公司仍在此方案中将 Windows 10 电脑部署为加入本地 AD 的设备，这些设备由 System Center Configuration Manager (SCCM) 管理，并且可能未部署/配置基础结构以通过基于云的 MDM 解决方案管理内部 Windows 10 设备。</span><span class="sxs-lookup"><span data-stu-id="00a8c-141">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud-based MDM solutions.</span></span>
   * <span data-ttu-id="00a8c-142">由于 HoloLens 2 是云第一设备，它严重依赖 Internet 和云连接服务进行用户身份验证、操作系统更新、MDM 管理等。</span><span class="sxs-lookup"><span data-stu-id="00a8c-142">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, and so on.</span></span> <span data-ttu-id="00a8c-143">连接到企业网络时，很可能需要调整代理/防火墙规则，以启用对 HoloLens 2 及其运行的应用程序的访问。</span><span class="sxs-lookup"><span data-stu-id="00a8c-143">When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span>
   * <span data-ttu-id="00a8c-144">企业Wi-Fi连接通常需要证书来向网络验证设备或用户。</span><span class="sxs-lookup"><span data-stu-id="00a8c-144">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="00a8c-145">通过 MDM 将证书部署到 Windows 10 设备所需的基础结构或设置可能难以配置。</span><span class="sxs-lookup"><span data-stu-id="00a8c-145">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="00a8c-146">部署指南 - 使用 Dynamics 365 指南的企业连接的 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="00a8c-146">Deployment Guide – Corporate connected HoloLens 2 with Dynamics 365 Guides</span></span>](hololens2-corp-connected-overview.md)

### <a name="scenario-c-deploy-in-secure-offline-environment"></a><span data-ttu-id="00a8c-147">方案 C：在安全的脱机环境中部署</span><span class="sxs-lookup"><span data-stu-id="00a8c-147">Scenario C: Deploy in secure offline environment</span></span>

<span data-ttu-id="00a8c-148">HoloLens 2 已部署，主要在无网络或 Internet 访问的脱机状态下使用。</span><span class="sxs-lookup"><span data-stu-id="00a8c-148">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="00a8c-149">这是高度安全或机密位置的典型部署。</span><span class="sxs-lookup"><span data-stu-id="00a8c-149">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="00a8c-150">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="00a8c-150">Basic Common Configurations</span></span>
   * <span data-ttu-id="00a8c-151">Wi-Fi连接已禁用。</span><span class="sxs-lookup"><span data-stu-id="00a8c-151">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="00a8c-152">如有必要，可以通过 USB 为 LAN 连接启用以太网。</span><span class="sxs-lookup"><span data-stu-id="00a8c-152">Ethernet via USB may be enabled for LAN connectivity if necessary.</span></span>
   * <span data-ttu-id="00a8c-153">未托管。</span><span class="sxs-lookup"><span data-stu-id="00a8c-153">Not Managed.</span></span>
   * <span data-ttu-id="00a8c-154">设备登录的本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="00a8c-154">Local user account for device sign-in.</span></span>
     * <span data-ttu-id="00a8c-155">HoloLens 2 仅支持一个本地帐户。</span><span class="sxs-lookup"><span data-stu-id="00a8c-155">HoloLens 2 supports only one local account.</span></span>
   * <span data-ttu-id="00a8c-156">根据特定用例，通过预配包应用不同级别的设备锁定配置。</span><span class="sxs-lookup"><span data-stu-id="00a8c-156">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="00a8c-157">由于安全环境要求，这些配置通常受到限制。</span><span class="sxs-lookup"><span data-stu-id="00a8c-157">These configurations are typically restricted because of secure environment requirements.</span></span>
   * <span data-ttu-id="00a8c-158">通过预配包部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="00a8c-158">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="00a8c-159">常见挑战</span><span class="sxs-lookup"><span data-stu-id="00a8c-159">Common Challenges</span></span>
   * <span data-ttu-id="00a8c-160">通过预配包提供的配置集有限</span><span class="sxs-lookup"><span data-stu-id="00a8c-160">There's a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="00a8c-161">云服务无法使用，因此限制了 HoloLens 2 功能。</span><span class="sxs-lookup"><span data-stu-id="00a8c-161">Cloud services aren't able to be used, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="00a8c-162">由于必须手动设置、配置和更新这些设备，因此管理开销较高。</span><span class="sxs-lookup"><span data-stu-id="00a8c-162">Higher administrative overhead since these devices have to be set up, configured, and updated manually.</span></span>

<span data-ttu-id="00a8c-163">有关与此方案类似的部署指南，请查看我们的 [脱机安全部署指南](hololens-common-scenarios-offline-secure.md)。</span><span class="sxs-lookup"><span data-stu-id="00a8c-163">For a deployment guide that is similar to this scenario review our [Offline Secure Deployment Guide](hololens-common-scenarios-offline-secure.md).</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="00a8c-164">部署指南 - 脱机安全 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="00a8c-164">Deployment Guide – Offline Secure HoloLens 2</span></span>](hololens-common-scenarios-offline-secure.md)
