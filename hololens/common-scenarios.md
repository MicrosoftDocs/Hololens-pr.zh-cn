---
title: 常见基础结构部署方案
ms.assetid: 651d0430-bfbc-4685-a4fd-db7c33ce9325
ms.date: 6/30/2020
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
ms.openlocfilehash: f8d69fc988afabad5f4ae1cce9003381ceb8e68c
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857865"
---
# <span data-ttu-id="62cb7-103">常见基础结构部署方案</span><span class="sxs-lookup"><span data-stu-id="62cb7-103">Common Infrastructure Deployment Scenarios</span></span>
<span data-ttu-id="62cb7-104">以下信息提供了在企业内部部署和管理 Microsoft HoloLens 2 设备的三种常见方案的高级体系结构概述。</span><span class="sxs-lookup"><span data-stu-id="62cb7-104">This following information provides a high-level architecture overview for three common scenarios when deploying and managing Microsoft HoloLens 2 devices within the enterprise.</span></span>

## <span data-ttu-id="62cb7-105">场景</span><span class="sxs-lookup"><span data-stu-id="62cb7-105">Scenarios</span></span>

<span data-ttu-id="62cb7-106">下图表示 HoloLens 2 部署的三种典型方案。</span><span class="sxs-lookup"><span data-stu-id="62cb7-106">The diagram below represents three typical scenarios for HoloLens 2 deployments.</span></span> 
![环境](images/scenarios.jpg)

### <span data-ttu-id="62cb7-108">方案 A</span><span class="sxs-lookup"><span data-stu-id="62cb7-108">Scenario A</span></span>

<span data-ttu-id="62cb7-109">HoloLens 2 部署主要用于企业网络外部的环境。</span><span class="sxs-lookup"><span data-stu-id="62cb7-109">HoloLens 2 is deployed for use primarily in environments external to a corporate network.</span></span> <span data-ttu-id="62cb7-110">公司资源不会被访问或通过 VPN 限制。</span><span class="sxs-lookup"><span data-stu-id="62cb7-110">Corporate resources are not accessed or may be limited through VPN.</span></span> <span data-ttu-id="62cb7-111">这是一个与公司中托管的移动设备非常类似的部署。</span><span class="sxs-lookup"><span data-stu-id="62cb7-111">This is a deployment very similar to managed mobile devices within a company.</span></span>
 * <span data-ttu-id="62cb7-112">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="62cb7-112">Basic Common Configurations</span></span>
   * <span data-ttu-id="62cb7-113">Wlan 网络通常完全开放于 Internet 和云服务。</span><span class="sxs-lookup"><span data-stu-id="62cb7-113">Wi-Fi networks are typically fully open to the Internet and Cloud services.</span></span>
   * <span data-ttu-id="62cb7-114">具有 MDM 自动注册的 Azure AD 联接--MDM （Intune）托管</span><span class="sxs-lookup"><span data-stu-id="62cb7-114">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
   * <span data-ttu-id="62cb7-115">用户利用其自己的公司帐户（AAD）登录</span><span class="sxs-lookup"><span data-stu-id="62cb7-115">Users sign in with their own corporate account (AAD)</span></span> 
     * <span data-ttu-id="62cb7-116">每个设备支持的单个或多个用户</span><span class="sxs-lookup"><span data-stu-id="62cb7-116">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="62cb7-117">不同级别的设备锁定配置基于特定使用情形（从完全打开到单应用展台）应用。</span><span class="sxs-lookup"><span data-stu-id="62cb7-117">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="62cb7-118">一个或多个应用程序通过 MDM 进行部署</span><span class="sxs-lookup"><span data-stu-id="62cb7-118">One or more applications are deployed via MDM</span></span>

* <span data-ttu-id="62cb7-119">常见挑战</span><span class="sxs-lookup"><span data-stu-id="62cb7-119">Common Challenges</span></span>
   * <span data-ttu-id="62cb7-120">根据方案要求确定要对 HoloLens 2 应用哪些 MDM 配置。</span><span class="sxs-lookup"><span data-stu-id="62cb7-120">Determining which MDM configurations to apply to the HoloLens 2 based on scenario requirements.</span></span>

### <span data-ttu-id="62cb7-121">情形 B</span><span class="sxs-lookup"><span data-stu-id="62cb7-121">Scenario B</span></span>

<span data-ttu-id="62cb7-122">HoloLens 2 已部署为主要在企业网络上使用，可访问内部公司资源。</span><span class="sxs-lookup"><span data-stu-id="62cb7-122">HoloLens 2 is deployed for use primarily on the corporate network with access to internal corporate resources.</span></span> <span data-ttu-id="62cb7-123">互联网和云服务可能会受到限制。</span><span class="sxs-lookup"><span data-stu-id="62cb7-123">Internet and cloud services may be limited.</span></span> <span data-ttu-id="62cb7-124">这是大多数 Windows 10 电脑的典型部署。</span><span class="sxs-lookup"><span data-stu-id="62cb7-124">This is a typical deployment for most Windows 10 PCs.</span></span>
 * <span data-ttu-id="62cb7-125">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="62cb7-125">Basic Common Configurations</span></span>
   * <span data-ttu-id="62cb7-126">Wi-fi 网络是一种内部公司网络，可访问内部资源，并限制 internet 或云服务访问。</span><span class="sxs-lookup"><span data-stu-id="62cb7-126">Wi-Fi network is an internal corporate network with access to internal resources, and limited access to the internet or Cloud services.</span></span>
   * <span data-ttu-id="62cb7-127">具有 MDM 自动注册的 Azure AD 联接</span><span class="sxs-lookup"><span data-stu-id="62cb7-127">Azure AD Join with MDM Auto Enrollment</span></span> 
   * <span data-ttu-id="62cb7-128">MDM （Intune）托管</span><span class="sxs-lookup"><span data-stu-id="62cb7-128">MDM (Intune) Managed</span></span>
   * <span data-ttu-id="62cb7-129">用户利用其自己的公司帐户（AAD）登录</span><span class="sxs-lookup"><span data-stu-id="62cb7-129">Users sign in with their own corporate account (AAD)</span></span>
     * <span data-ttu-id="62cb7-130">每个设备支持的单个或多个用户</span><span class="sxs-lookup"><span data-stu-id="62cb7-130">Single or multiple users per device supported</span></span>
   * <span data-ttu-id="62cb7-131">不同级别的设备锁定配置基于特定使用情形（从完全打开到单应用展台）应用。</span><span class="sxs-lookup"><span data-stu-id="62cb7-131">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>
   * <span data-ttu-id="62cb7-132">一个或多个应用程序通过 MDM 进行部署</span><span class="sxs-lookup"><span data-stu-id="62cb7-132">One or more applications are deployed via MDM</span></span>

 * <span data-ttu-id="62cb7-133">常见挑战</span><span class="sxs-lookup"><span data-stu-id="62cb7-133">Common Challenges</span></span>
   * <span data-ttu-id="62cb7-134">HoloLens 2 不支持本地广告加入或 SCCM。</span><span class="sxs-lookup"><span data-stu-id="62cb7-134">HoloLens 2 does not support on premises AD join or SCCM.</span></span> <span data-ttu-id="62cb7-135">仅适用于 MDM 的 Azure AD 加入。</span><span class="sxs-lookup"><span data-stu-id="62cb7-135">Only Azure AD join with MDM.</span></span> <span data-ttu-id="62cb7-136">目前，许多公司仍在此方案中部署 Windows 10 电脑，这是因为本地广告已加入设备，由 System Center Configuration Manager （SCCM）托管，并且可能没有为通过基于云的 MDM 解决方案管理内部 Windows 10 设备而部署/配置的基础结构。</span><span class="sxs-lookup"><span data-stu-id="62cb7-136">Many companies today still deploy Windows 10 PCs in this scenario as on premises AD joined devices, managed by System Center Configuration Manager (SCCM) and may not have the infrastructure deployed/configured for managing internal Windows 10 devices via cloud based MDM solutions.</span></span>
   * <span data-ttu-id="62cb7-137">由于 HoloLens 2 是云优先设备，因此它很大程度上依赖于 internet 和云连接的服务，用于用户身份验证、操作系统更新、MDM 管理等。连接到公司网络时，很可能需要对代理/防火墙规则进行调整，以便为 HoloLens 2 和在其上运行的应用程序启用访问权限。</span><span class="sxs-lookup"><span data-stu-id="62cb7-137">As HoloLens 2 is a cloud first device, it relies heavily on internet and cloud connected services for User authentication, OS updates, MDM management, etc. When connecting to a corporate network, Proxy/Firewall rules will most likely need to be adjusted to enable access for HoloLens 2 and the applications that run on it.</span></span> 
   * <span data-ttu-id="62cb7-138">公司 Wlan 连接通常需要证书来对网络上的设备或用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="62cb7-138">Corporate Wi-Fi connectivity typically requires certificates to authenticate the device or user to the network.</span></span> <span data-ttu-id="62cb7-139">配置所需的基础结构或设置以通过 MDM 将证书部署到 Windows 10 设备的难度很大。</span><span class="sxs-lookup"><span data-stu-id="62cb7-139">The required infrastructure or settings to deploy certificates to Windows 10 devices through MDM can be challenging to configure.</span></span>

### <span data-ttu-id="62cb7-140">情形 C</span><span class="sxs-lookup"><span data-stu-id="62cb7-140">Scenario C</span></span>

<span data-ttu-id="62cb7-141">HoloLens 2 已部署为主要在没有网络或 internet 访问的情况下脱机使用。</span><span class="sxs-lookup"><span data-stu-id="62cb7-141">HoloLens 2 is deployed for use primarily offline with no network or internet access.</span></span> <span data-ttu-id="62cb7-142">这是对高度安全或机密位置的典型部署。</span><span class="sxs-lookup"><span data-stu-id="62cb7-142">This is a typical deployment for highly secure or confidential locations.</span></span>
 * <span data-ttu-id="62cb7-143">基本常见配置</span><span class="sxs-lookup"><span data-stu-id="62cb7-143">Basic Common Configurations</span></span>
   * <span data-ttu-id="62cb7-144">Wi-fi 连接已禁用。</span><span class="sxs-lookup"><span data-stu-id="62cb7-144">Wi-Fi connectivity is disabled.</span></span> <span data-ttu-id="62cb7-145">如果需要，可通过 USB 使用以太网进行局域网连接。</span><span class="sxs-lookup"><span data-stu-id="62cb7-145">Ethernet via USB may be enabled for LAN connectivity if required.</span></span>
   * <span data-ttu-id="62cb7-146">不受管理。</span><span class="sxs-lookup"><span data-stu-id="62cb7-146">Not Managed.</span></span>
   * <span data-ttu-id="62cb7-147">设备登录的本地用户帐户。</span><span class="sxs-lookup"><span data-stu-id="62cb7-147">Local user account for device sign in.</span></span>
     * <span data-ttu-id="62cb7-148">HoloLens 2 仅支持1个本地帐户。</span><span class="sxs-lookup"><span data-stu-id="62cb7-148">HoloLens 2 supports only 1 local account.</span></span>
   * <span data-ttu-id="62cb7-149">不同级别的设备锁定配置通过基于特定使用案例的预配包进行应用。</span><span class="sxs-lookup"><span data-stu-id="62cb7-149">Varying levels of device lockdown configurations are applied via Provisioning Packages based on specific use cases.</span></span> <span data-ttu-id="62cb7-150">这些配置通常因安全环境要求而受到严格限制。</span><span class="sxs-lookup"><span data-stu-id="62cb7-150">These configurations are typically very restricted due to secure environment requirements.</span></span>
   * <span data-ttu-id="62cb7-151">通过预配包部署一个或多个应用程序</span><span class="sxs-lookup"><span data-stu-id="62cb7-151">One or more applications are deployed via Provisioning Package</span></span>

 * <span data-ttu-id="62cb7-152">常见挑战</span><span class="sxs-lookup"><span data-stu-id="62cb7-152">Common Challenges</span></span>
   * <span data-ttu-id="62cb7-153">预配程序包提供了一组有限的配置</span><span class="sxs-lookup"><span data-stu-id="62cb7-153">There are a limited set of configurations available through Provisioning Packages</span></span>
   * <span data-ttu-id="62cb7-154">云服务无法利用，因此限制了 HoloLens 2 功能。</span><span class="sxs-lookup"><span data-stu-id="62cb7-154">Cloud services are not able to be leveraged, therefore limiting the HoloLens 2 capabilities.</span></span>
   * <span data-ttu-id="62cb7-155">更高的管理开销，因为这些设备必须手动设置、配置和更新。</span><span class="sxs-lookup"><span data-stu-id="62cb7-155">Higher administrative overhead since these devices have to be setup, configured, and updated manually.</span></span>
