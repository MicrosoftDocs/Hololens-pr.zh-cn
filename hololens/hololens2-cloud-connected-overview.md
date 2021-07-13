---
title: 与远程协助 HoloLens 2 云连接的概述
description: 了解如何使用 Dynamics 365 Remote Assist 通过云连接网络注册 HoloLens 2 设备。
keywords: HoloLens，管理，云连接，远程协助，AAD，Azure AD，MDM，移动设备管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 86d36275d5cf1296ca3e9fec90684a188a29f3f0
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635120"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="67919-104">部署指南–云连接 HoloLens 2 与远程协助–概述</span><span class="sxs-lookup"><span data-stu-id="67919-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="67919-105">本指南将帮助 IT 专业人员规划和部署 Microsoft HoloLens 2 个设备，并向其组织提供远程协助。</span><span class="sxs-lookup"><span data-stu-id="67919-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="67919-106">在各种 HoloLens 2 用例中，这将充当对你的组织进行概念证明部署的模型。</span><span class="sxs-lookup"><span data-stu-id="67919-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="67919-107">此设置类似于 [方案 A：部署到云连接设备](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)。</span><span class="sxs-lookup"><span data-stu-id="67919-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="67919-108">在本指南中，我们将介绍如何将设备注册到设备管理，根据需要应用许可证，并验证最终用户是否能够在设备设置时立即使用远程协助。</span><span class="sxs-lookup"><span data-stu-id="67919-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="67919-109">为此，我们将介绍设置和运行所需的重要基础结构，即利用 HoloLens 2 大规模实现部署。</span><span class="sxs-lookup"><span data-stu-id="67919-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="67919-110">本指南中不会应用任何其他设备限制或配置，但是，我们建议你在完成后浏览这些选项。</span><span class="sxs-lookup"><span data-stu-id="67919-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="67919-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="67919-111">Prerequisites</span></span>

<span data-ttu-id="67919-112">为了部署 HoloLens 2，应准备好以下基础结构。</span><span class="sxs-lookup"><span data-stu-id="67919-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="67919-113">如果不是，则本指南中包括设置 Azure 和 Intune：</span><span class="sxs-lookup"><span data-stu-id="67919-113">If not, setting up Azure and Intune is included in this guide:</span></span>

<span data-ttu-id="67919-114">这是一种设置，类似于 [方案 a：部署到云连接设备](/hololens/common-scenarios#scenario-a)，这对于许多概念证明部署是一个不错的选择，其中包括：</span><span class="sxs-lookup"><span data-stu-id="67919-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="67919-115">Wi-Fi 网络通常会完全开放到 Internet 和云服务</span><span class="sxs-lookup"><span data-stu-id="67919-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="67919-116">与 MDM 自动注册 Azure AD 联接--MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="67919-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="67919-117">用户用自己的公司帐户登录 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="67919-117">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="67919-118">支持每个设备一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="67919-118">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="云连接方案" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="67919-120">了解远程协助</span><span class="sxs-lookup"><span data-stu-id="67919-120">Learn about Remote Assist</span></span>

<span data-ttu-id="67919-121">远程协助允许协作式维护和修复、远程检查以及知识共享和培训。</span><span class="sxs-lookup"><span data-stu-id="67919-121">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="67919-122">通过连接不同角色和位置的人员，使用远程协助的技术人员可以连接 Microsoft Teams 上的远程协作者。</span><span class="sxs-lookup"><span data-stu-id="67919-122">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="67919-123">即使在同一位置&#39;t，它们也可以结合视频、屏幕截图和批注来实时解决问题。</span><span class="sxs-lookup"><span data-stu-id="67919-123">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="67919-124">远程协作者可以插入引用图像、图表和其他有用信息。该技术人员&#39;的物理空间，因此，在 HoloLens 时，他们可以参考该示意性。</span><span class="sxs-lookup"><span data-stu-id="67919-124">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="67919-125">远程协助许可和要求</span><span class="sxs-lookup"><span data-stu-id="67919-125">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="67919-126">需要 Azure AD 帐户 (购买订阅和分配许可证) </span><span class="sxs-lookup"><span data-stu-id="67919-126">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="67919-127">[远程协助订阅](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (或 [远程协助试验](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)) </span><span class="sxs-lookup"><span data-stu-id="67919-127">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="67919-128">Dynamics 365 Remote Assist 用户</span><span class="sxs-lookup"><span data-stu-id="67919-128">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="67919-129">远程协助许可证</span><span class="sxs-lookup"><span data-stu-id="67919-129">Remote Assist license</span></span>
- <span data-ttu-id="67919-130">网络连接</span><span class="sxs-lookup"><span data-stu-id="67919-130">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="67919-131">Microsoft Teams 用户</span><span class="sxs-lookup"><span data-stu-id="67919-131">Microsoft Teams user</span></span>

- <span data-ttu-id="67919-132">Microsoft Teams 或[Teams 免费增值](https://products.office.com/microsoft-teams/free)。</span><span class="sxs-lookup"><span data-stu-id="67919-132">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="67919-133">网络连接</span><span class="sxs-lookup"><span data-stu-id="67919-133">Network connectivity</span></span>

<span data-ttu-id="67919-134">如果你计划实施此 [跨租户方案](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)，你可能需要一个信息障碍许可证。</span><span class="sxs-lookup"><span data-stu-id="67919-134">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="67919-135">请参阅 [本文](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) ，确定是否需要信息障碍许可证。</span><span class="sxs-lookup"><span data-stu-id="67919-135">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="67919-136">本指南中，你将实现以下操作：</span><span class="sxs-lookup"><span data-stu-id="67919-136">In this guide you will:</span></span>

<span data-ttu-id="67919-137">准备：</span><span class="sxs-lookup"><span data-stu-id="67919-137">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="67919-138">了解 HoloLens 2 设备的基础结构基础结构。</span><span class="sxs-lookup"><span data-stu-id="67919-138">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="67919-139">如果没有&#39;t，请详细了解 Azure AD 并设置一个。</span><span class="sxs-lookup"><span data-stu-id="67919-139">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="67919-140">了解身份管理，以及如何最好地设置 Azure AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="67919-140">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="67919-141">了解有关 MDM 的详细信息，并使用 Intune 进行设置（如果你未&#39;t 已经准备就绪）。</span><span class="sxs-lookup"><span data-stu-id="67919-141">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="67919-142">了解远程协助的网络要求。</span><span class="sxs-lookup"><span data-stu-id="67919-142">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="67919-143">（可选）：用于连接到组织资源的 VPN</span><span class="sxs-lookup"><span data-stu-id="67919-143">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="67919-144">配置：</span><span class="sxs-lookup"><span data-stu-id="67919-144">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="67919-145">如何创建用户和组。</span><span class="sxs-lookup"><span data-stu-id="67919-145">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="67919-146">如何在 Azure AD 中设置自动注册。</span><span class="sxs-lookup"><span data-stu-id="67919-146">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="67919-147">如何分配应用程序许可证。</span><span class="sxs-lookup"><span data-stu-id="67919-147">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="67919-148">部署：</span><span class="sxs-lookup"><span data-stu-id="67919-148">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="67919-149">设置 HoloLens 2 并验证注册。</span><span class="sxs-lookup"><span data-stu-id="67919-149">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="67919-150">验证是否可以进行远程协助呼叫。</span><span class="sxs-lookup"><span data-stu-id="67919-150">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="67919-151">维护：</span><span class="sxs-lookup"><span data-stu-id="67919-151">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="67919-152">如何使用 Microsoft Store 应用程序更新远程协助。</span><span class="sxs-lookup"><span data-stu-id="67919-152">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="67919-153">制定支持计划。</span><span class="sxs-lookup"><span data-stu-id="67919-153">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="67919-154">开发计划。</span><span class="sxs-lookup"><span data-stu-id="67919-154">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="67919-155">下一步</span><span class="sxs-lookup"><span data-stu-id="67919-155">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="67919-156">云连接部署-准备</span><span class="sxs-lookup"><span data-stu-id="67919-156">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

