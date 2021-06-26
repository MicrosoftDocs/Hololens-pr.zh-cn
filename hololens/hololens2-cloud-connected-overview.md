---
title: 云连接云HoloLens 2概述Remote Assist
description: 了解如何使用云HoloLens 2通过云连接的网络注册Dynamics 365 Remote Assist。
keywords: HoloLens， 管理， 云连接， Remote Assist， AAD， Azure AD， MDM， 移动设备管理
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
ms.openlocfilehash: a44247b4afea747e4b75c974fcae344380909989
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923527"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="74416-104">部署指南 - 云HoloLens 2云Remote Assist - 概述</span><span class="sxs-lookup"><span data-stu-id="74416-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="74416-105">本指南将帮助 IT 专业人员计划 2 Microsoft HoloLens设备，Remote Assist部署到其组织。</span><span class="sxs-lookup"><span data-stu-id="74416-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Remote Assist to their organization.</span></span> <span data-ttu-id="74416-106">这将充当跨各种用例向组织部署概念证明HoloLens 2模型。</span><span class="sxs-lookup"><span data-stu-id="74416-106">This will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span> <span data-ttu-id="74416-107">设置类似于方案 [A：部署到云连接设备](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)。</span><span class="sxs-lookup"><span data-stu-id="74416-107">The setup is similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a).</span></span> 

<span data-ttu-id="74416-108">在本指南中，我们将介绍如何将设备注册到设备管理中、根据需要应用许可证，以及验证最终用户能否在设备设置Remote Assist立即使用设备。</span><span class="sxs-lookup"><span data-stu-id="74416-108">During the guide, we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="74416-109">为此，我们将了解设置和运行所需的重要基础结构部分 - 使用 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="74416-109">To do this, we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span> <span data-ttu-id="74416-110">本指南中不会应用其他设备限制或配置，但是，我们建议在完成后浏览这些选项。</span><span class="sxs-lookup"><span data-stu-id="74416-110">No other device restrictions or configurations will be applied in this guide, however, we encourage you to explore those options after finishing.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="74416-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="74416-111">Prerequisites</span></span>

<span data-ttu-id="74416-112">应采用以下基础结构来部署HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="74416-112">The following infrastructure should be in place in order to deploy the HoloLens 2.</span></span> <span data-ttu-id="74416-113">如果没有，本指南中将包含设置 Azure 和 Intune：</span><span class="sxs-lookup"><span data-stu-id="74416-113">If not, setting up Azure and Intune is included in this guide:</span></span>

- <span data-ttu-id="74416-114">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="74416-114">Wi-Fi</span></span>
    - <span data-ttu-id="74416-115">网络通常对 Internet 和云服务开放</span><span class="sxs-lookup"><span data-stu-id="74416-115">Networks are typically open to the Internet and Cloud services</span></span>
- <span data-ttu-id="74416-116">Azure Active Directory (Azure AD) 注册所需的 MDM 自动注册[ (Azure AD P1 订阅) ](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="74416-116">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="74416-117">MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="74416-117">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="74416-118">一个或多个应用程序是通过 MDM 部署的。</span><span class="sxs-lookup"><span data-stu-id="74416-118">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="74416-119">用户使用自己的公司帐户登录 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="74416-119">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="74416-120">支持每个设备的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="74416-120">Single or multiple users per device is supported.</span></span>

:::image type="content" alt-text="云连接方案" source="./images/deployment-guides-revised-scenario-a.png" lightbox="./images/deployment-guides-revised-scenario-a.png":::


## <a name="learn-about-remote-assist"></a><span data-ttu-id="74416-122">了解Remote Assist</span><span class="sxs-lookup"><span data-stu-id="74416-122">Learn about Remote Assist</span></span>

<span data-ttu-id="74416-123">Remote Assist协作维护和修复、远程检查以及知识共享和培训。</span><span class="sxs-lookup"><span data-stu-id="74416-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="74416-124">通过连接不同角色和位置的用户，使用 Remote Assist可以与 Microsoft Teams 上的远程协作者进行连接。</span><span class="sxs-lookup"><span data-stu-id="74416-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="74416-125">它们可以组合视频、屏幕截图和批注，以实时解决问题，即使它们&#39;位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="74416-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="74416-126">远程协作者可以插入参考图像、示意图和其他有用的信息，以便技术人员&#39;物理空间，以便他们可以在 HoloLens 上向上和无手工作的同时引用示意图。</span><span class="sxs-lookup"><span data-stu-id="74416-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### <a name="remote-assist-licensing-and-requirements"></a><span data-ttu-id="74416-127">Remote Assist许可和要求</span><span class="sxs-lookup"><span data-stu-id="74416-127">Remote Assist Licensing and Requirements</span></span>

- <span data-ttu-id="74416-128">Azure AD订阅 (分配许可证时所需的帐户) </span><span class="sxs-lookup"><span data-stu-id="74416-128">Azure AD account (required for purchasing the subscription and assigning licenses)</span></span>
- <span data-ttu-id="74416-129">[Remote Assist订阅](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (或[Remote Assist试用版) ](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="74416-129">[Remote Assist subscription](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist) (or [Remote Assist Trial](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist))</span></span>
    
#### <a name="dynamics-365-remote-assist-user"></a><span data-ttu-id="74416-130">Dynamics 365 Remote Assist用户</span><span class="sxs-lookup"><span data-stu-id="74416-130">Dynamics 365 Remote Assist user</span></span>

- <span data-ttu-id="74416-131">Remote Assist许可证</span><span class="sxs-lookup"><span data-stu-id="74416-131">Remote Assist license</span></span>
- <span data-ttu-id="74416-132">网络连接</span><span class="sxs-lookup"><span data-stu-id="74416-132">Network Connectivity</span></span>

#### <a name="microsoft-teams-user"></a><span data-ttu-id="74416-133">Microsoft Teams 用户</span><span class="sxs-lookup"><span data-stu-id="74416-133">Microsoft Teams user</span></span>

- <span data-ttu-id="74416-134">Microsoft Teams 或 [Teams Freemium](https://products.office.com/microsoft-teams/free)。</span><span class="sxs-lookup"><span data-stu-id="74416-134">Microsoft Teams or [Teams Freemium](https://products.office.com/microsoft-teams/free).</span></span>
- <span data-ttu-id="74416-135">网络连接</span><span class="sxs-lookup"><span data-stu-id="74416-135">Network connectivity</span></span>

<span data-ttu-id="74416-136">如果计划实现此跨租户 [方案，](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)可能需要信息屏障许可证。</span><span class="sxs-lookup"><span data-stu-id="74416-136">If you plan on implementing this [cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants), you may need an Information Barriers license.</span></span> <span data-ttu-id="74416-137">请参阅 [本文](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) ，确定是否需要信息屏障许可证。</span><span class="sxs-lookup"><span data-stu-id="74416-137">See [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="74416-138">本指南中，你将实现以下操作：</span><span class="sxs-lookup"><span data-stu-id="74416-138">In this guide you will:</span></span>

<span data-ttu-id="74416-139">准备：</span><span class="sxs-lookup"><span data-stu-id="74416-139">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="74416-140">了解适用于设备HoloLens 2要素。</span><span class="sxs-lookup"><span data-stu-id="74416-140">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="74416-141">详细了解Azure AD，如果还没有，&#39;设置一个。</span><span class="sxs-lookup"><span data-stu-id="74416-141">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="74416-142">了解标识管理以及如何以最佳方式设置Azure AD帐户。</span><span class="sxs-lookup"><span data-stu-id="74416-142">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="74416-143">详细了解 MDM，如果尚未准备好 MDM，&#39;Intune 进行设置。</span><span class="sxs-lookup"><span data-stu-id="74416-143">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="74416-144">了解应用程序的网络Remote Assist。</span><span class="sxs-lookup"><span data-stu-id="74416-144">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="74416-145">（可选）：用于连接到组织资源的 VPN</span><span class="sxs-lookup"><span data-stu-id="74416-145">Optionally: VPN to connect to organizational resources</span></span>](hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="74416-146">配置：</span><span class="sxs-lookup"><span data-stu-id="74416-146">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="74416-147">如何创建用户和组。</span><span class="sxs-lookup"><span data-stu-id="74416-147">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="74416-148">如何在 Azure AD 中设置自动Azure AD。</span><span class="sxs-lookup"><span data-stu-id="74416-148">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="74416-149">如何分配应用程序许可证。</span><span class="sxs-lookup"><span data-stu-id="74416-149">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="74416-150">部署：</span><span class="sxs-lookup"><span data-stu-id="74416-150">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="74416-151">设置你的HoloLens 2并验证注册。</span><span class="sxs-lookup"><span data-stu-id="74416-151">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="74416-152">验证是否可进行Remote Assist调用。</span><span class="sxs-lookup"><span data-stu-id="74416-152">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="74416-153">维护：</span><span class="sxs-lookup"><span data-stu-id="74416-153">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="74416-154">如何使用 Remote Assist 应用更新Microsoft Store应用。</span><span class="sxs-lookup"><span data-stu-id="74416-154">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="74416-155">制定支持计划。</span><span class="sxs-lookup"><span data-stu-id="74416-155">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="74416-156">开发计划。</span><span class="sxs-lookup"><span data-stu-id="74416-156">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="74416-157">后续步骤</span><span class="sxs-lookup"><span data-stu-id="74416-157">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="74416-158">云连接部署 - 准备</span><span class="sxs-lookup"><span data-stu-id="74416-158">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

