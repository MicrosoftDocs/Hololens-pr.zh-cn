---
title: 部署指南 - HoloLens 2 Dynamics 365 指南 - 概述
description: 了解如何通过企业HoloLens 2使用 Dynamics 365 指南注册设备。
keywords: HoloLens， 管理， 企业连接， Dynamics 365 指南， AAD， Azure AD， MDM， 移动设备管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: ee6c24f65e5990f1e84a71d86b24dd782cf9f4cc
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397190"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="6046c-104">部署指南 - HoloLens 2 Dynamics 365 指南 - 概述</span><span class="sxs-lookup"><span data-stu-id="6046c-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="6046c-105">本指南将帮助 IT 专业人员使用 Dynamics 365 指南Microsoft HoloLens 2 台设备的计划和部署 (指南) 其组织。</span><span class="sxs-lookup"><span data-stu-id="6046c-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="6046c-106">本指南适用于试点和生产部署，类似于方案 [B：在组织的网络内部署指南](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 。</span><span class="sxs-lookup"><span data-stu-id="6046c-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="6046c-107">测试概念证明后，使用本指南继续将 HoloLens 集成到组织中。</span><span class="sxs-lookup"><span data-stu-id="6046c-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="6046c-108">本指南将介绍如何在设置设备后将设备注册到现有设备管理、根据需要应用许可证，并验证最终用户是否能够操作 Dynamics 365 指南以及使用自定义业务线应用。</span><span class="sxs-lookup"><span data-stu-id="6046c-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="6046c-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="6046c-109">Prerequisites</span></span>

<span data-ttu-id="6046c-110">以下基础结构应已就位：</span><span class="sxs-lookup"><span data-stu-id="6046c-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="6046c-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="6046c-111">Wi-Fi</span></span>
    - <span data-ttu-id="6046c-112">可以访问内部资源且对 Internet 或云服务的访问受限的内部公司网络</span><span class="sxs-lookup"><span data-stu-id="6046c-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="6046c-113">基于设备的证书身份验证。</span><span class="sxs-lookup"><span data-stu-id="6046c-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="6046c-114">Azure Active Directory (Azure AD) 注册所需的 MDM 自动注册[ (Azure AD P1 订阅) ](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="6046c-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="6046c-115">MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="6046c-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="6046c-116">一个或多个应用程序是通过 MDM 部署的。</span><span class="sxs-lookup"><span data-stu-id="6046c-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="6046c-117">网络</span><span class="sxs-lookup"><span data-stu-id="6046c-117">Network</span></span> 
    - <span data-ttu-id="6046c-118">SCEP (PKCS 证书) </span><span class="sxs-lookup"><span data-stu-id="6046c-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="6046c-119">代理配置</span><span class="sxs-lookup"><span data-stu-id="6046c-119">Proxy configuration</span></span>
- <span data-ttu-id="6046c-120">用户使用自己的公司帐户登录 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="6046c-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="6046c-121">支持每个设备的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="6046c-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="6046c-122">根据特定用例应用的不同设备锁定配置级别，从"完全打开"到"单应用展台"。</span><span class="sxs-lookup"><span data-stu-id="6046c-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="6046c-123">指南许可和要求</span><span class="sxs-lookup"><span data-stu-id="6046c-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="6046c-124">Azure AD 帐户</span><span class="sxs-lookup"><span data-stu-id="6046c-124">Azure AD account</span></span>
- <span data-ttu-id="6046c-125">Dynamics 365 Guides 应用程序电脑和 HoloLens</span><span class="sxs-lookup"><span data-stu-id="6046c-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="6046c-126">Dynamics 365 指南订阅</span><span class="sxs-lookup"><span data-stu-id="6046c-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="6046c-127">Microsoft Dataverse (包含) </span><span class="sxs-lookup"><span data-stu-id="6046c-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="6046c-128"> (包含的 Power Apps) </span><span class="sxs-lookup"><span data-stu-id="6046c-128">Power Apps (included)</span></span>
- <span data-ttu-id="6046c-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="6046c-129">Power BI Desktop</span></span>
- <span data-ttu-id="6046c-130">网络连接</span><span class="sxs-lookup"><span data-stu-id="6046c-130">Network Connectivity</span></span>

<span data-ttu-id="6046c-131">[![Corp 连接网络图，阶段 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="6046c-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="6046c-132">[![Corp 连接网络关系图，第 2 ](./images/deployment-guides-revised-scenario-b-02-1.png) 阶段](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="6046c-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="6046c-133">本指南中，你将实现以下操作：</span><span class="sxs-lookup"><span data-stu-id="6046c-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="6046c-134">准备</span><span class="sxs-lookup"><span data-stu-id="6046c-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="6046c-135">了解 HoloLens 2 设备的基础结构基础结构。</span><span class="sxs-lookup"><span data-stu-id="6046c-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="6046c-136">了解 Azure AD 的详细信息，并设置一个（如果没有）。</span><span class="sxs-lookup"><span data-stu-id="6046c-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="6046c-137">了解身份管理，以及如何最好地设置 Azure AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="6046c-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="6046c-138">如果尚未准备好，请详细了解 MDM 并使用 Intune 进行设置。</span><span class="sxs-lookup"><span data-stu-id="6046c-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="6046c-139">熟悉基于证书的 Wi-fi。</span><span class="sxs-lookup"><span data-stu-id="6046c-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="6046c-140">熟悉代理。</span><span class="sxs-lookup"><span data-stu-id="6046c-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="6046c-141">了解如何使用业务线应用。</span><span class="sxs-lookup"><span data-stu-id="6046c-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="6046c-142">详细了解你的组织使用指南的方式。</span><span class="sxs-lookup"><span data-stu-id="6046c-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="6046c-143">配置</span><span class="sxs-lookup"><span data-stu-id="6046c-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="6046c-144">如何创建用户和组。</span><span class="sxs-lookup"><span data-stu-id="6046c-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="6046c-145">如何设置自动注册。</span><span class="sxs-lookup"><span data-stu-id="6046c-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="6046c-146">如何为公司 Wi-Fi 连接设置 Wi-Fi 证书和配置文件。</span><span class="sxs-lookup"><span data-stu-id="6046c-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="6046c-147">将业务线 (LOB) 应用包上传和分配。</span><span class="sxs-lookup"><span data-stu-id="6046c-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="6046c-148">设置 Dynamics 365 指南。</span><span class="sxs-lookup"><span data-stu-id="6046c-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="6046c-149">如何配置展台模式 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="6046c-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="6046c-150">如何配置 WDAC (可选) 。</span><span class="sxs-lookup"><span data-stu-id="6046c-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="6046c-151">部署</span><span class="sxs-lookup"><span data-stu-id="6046c-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="6046c-152">通过设备和 MDM 验证注册。</span><span class="sxs-lookup"><span data-stu-id="6046c-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="6046c-153">验证Wi-Fi证书。</span><span class="sxs-lookup"><span data-stu-id="6046c-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="6046c-154">验证 LOB 应用安装。</span><span class="sxs-lookup"><span data-stu-id="6046c-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="6046c-155">通过创作和操作验证指南。</span><span class="sxs-lookup"><span data-stu-id="6046c-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="6046c-156">维护</span><span class="sxs-lookup"><span data-stu-id="6046c-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="6046c-157">更新HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="6046c-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="6046c-158">如何更新指南 (应用商店应用) 。</span><span class="sxs-lookup"><span data-stu-id="6046c-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="6046c-159">如何更新 LOB 应用。</span><span class="sxs-lookup"><span data-stu-id="6046c-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="6046c-160">开发计划。</span><span class="sxs-lookup"><span data-stu-id="6046c-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="6046c-161">制定支持计划。</span><span class="sxs-lookup"><span data-stu-id="6046c-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="6046c-162">设备管理选项。</span><span class="sxs-lookup"><span data-stu-id="6046c-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="6046c-163">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6046c-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="6046c-164">企业连接部署 - 准备</span><span class="sxs-lookup"><span data-stu-id="6046c-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
