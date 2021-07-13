---
title: 部署指南 - 使用 HoloLens 2 连接Dynamics 365 Guides - 概述
description: 了解如何通过企业HoloLens 2注册Dynamics 365 Guides设备。
keywords: HoloLens、管理、企业连接、Dynamics 365 Guides、AAD、Azure AD、MDM、移动设备管理
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
ms.openlocfilehash: f2f7e1425a208e1f466d995f66118b7e68984242
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637007"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="c70d2-104">部署指南 - 企业HoloLens 2连接Dynamics 365 Guides - 概述</span><span class="sxs-lookup"><span data-stu-id="c70d2-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="c70d2-105">本指南将帮助 IT 专业人员使用 Dynamics 365 Guides (指南Microsoft HoloLens 2 台设备) 部署到其组织。</span><span class="sxs-lookup"><span data-stu-id="c70d2-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="c70d2-106">本指南适用于试点和生产部署，类似于方案 [B：在组织的网络内部署指南](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 。</span><span class="sxs-lookup"><span data-stu-id="c70d2-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="c70d2-107">测试概念证明后，请使用本指南继续将概念HoloLens集成到组织中。</span><span class="sxs-lookup"><span data-stu-id="c70d2-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="c70d2-108">本指南将介绍如何在设置设备后将设备注册到现有设备管理、根据需要应用许可证，并验证最终用户是否能够操作 Dynamics 365 指南以及使用自定义业务线应用。</span><span class="sxs-lookup"><span data-stu-id="c70d2-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c70d2-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="c70d2-109">Prerequisites</span></span>

<span data-ttu-id="c70d2-110">以下基础结构应已就位：</span><span class="sxs-lookup"><span data-stu-id="c70d2-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="c70d2-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="c70d2-111">Wi-Fi</span></span>
    - <span data-ttu-id="c70d2-112">可以访问内部资源且对 Internet 或云服务的访问受限的内部公司网络</span><span class="sxs-lookup"><span data-stu-id="c70d2-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="c70d2-113">基于设备的证书身份验证。</span><span class="sxs-lookup"><span data-stu-id="c70d2-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="c70d2-114">Azure Active Directory (Azure AD) 注册所需的 MDM 自动注册[ (Azure AD P1 订阅) ](/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="c70d2-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="c70d2-115">MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="c70d2-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="c70d2-116">一个或多个应用程序是通过 MDM 部署的。</span><span class="sxs-lookup"><span data-stu-id="c70d2-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="c70d2-117">网络</span><span class="sxs-lookup"><span data-stu-id="c70d2-117">Network</span></span> 
    - <span data-ttu-id="c70d2-118">SCEP (PKCS 证书) </span><span class="sxs-lookup"><span data-stu-id="c70d2-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="c70d2-119">代理配置</span><span class="sxs-lookup"><span data-stu-id="c70d2-119">Proxy configuration</span></span>
- <span data-ttu-id="c70d2-120">用户使用自己的公司帐户登录 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="c70d2-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="c70d2-121">支持每个设备的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="c70d2-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="c70d2-122">根据特定用例应用的不同设备锁定配置级别，从"完全打开"到"单应用展台"。</span><span class="sxs-lookup"><span data-stu-id="c70d2-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## <a name="guides-licensing-and-requirements"></a>[<span data-ttu-id="c70d2-123">指南许可和要求</span><span class="sxs-lookup"><span data-stu-id="c70d2-123">Guides Licensing and Requirements</span></span>](/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)

- <span data-ttu-id="c70d2-124">Azure AD 帐户</span><span class="sxs-lookup"><span data-stu-id="c70d2-124">Azure AD account</span></span>
- <span data-ttu-id="c70d2-125">Dynamics 365 Guides PC 和 HoloLens</span><span class="sxs-lookup"><span data-stu-id="c70d2-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="c70d2-126">Dynamics 365 Guides订阅</span><span class="sxs-lookup"><span data-stu-id="c70d2-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="c70d2-127">Microsoft Dataverse (包含) </span><span class="sxs-lookup"><span data-stu-id="c70d2-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="c70d2-128">Power Apps (包含) </span><span class="sxs-lookup"><span data-stu-id="c70d2-128">Power Apps (included)</span></span>
- <span data-ttu-id="c70d2-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="c70d2-129">Power BI Desktop</span></span>
- <span data-ttu-id="c70d2-130">网络连接</span><span class="sxs-lookup"><span data-stu-id="c70d2-130">Network Connectivity</span></span>

<span data-ttu-id="c70d2-131">[![公司联网网络示意图，阶段 1 ](./images/deployment-guides-revised-scenario-b-01-1.png)](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c70d2-131">[ ![Corp connected network diagram, stage 1](./images/deployment-guides-revised-scenario-b-01-1.png) ](./images/deployment-guides-revised-scenario-b-01-1.png#lightbox)</span></span>

<span data-ttu-id="c70d2-132">[![公司联网网络示意图，阶段 2 ](./images/deployment-guides-revised-scenario-b-02-1.png)](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c70d2-132">[ ![Corp connected network diagram, stage 2](./images/deployment-guides-revised-scenario-b-02-1.png) ](./images/deployment-guides-revised-scenario-b-02-1.png#lightbox)</span></span>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="c70d2-133">本指南中，你将实现以下操作：</span><span class="sxs-lookup"><span data-stu-id="c70d2-133">In this guide you will:</span></span>
### <a name="prepare"></a><span data-ttu-id="c70d2-134">准备</span><span class="sxs-lookup"><span data-stu-id="c70d2-134">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="c70d2-135">了解适用于设备HoloLens 2要素。</span><span class="sxs-lookup"><span data-stu-id="c70d2-135">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="c70d2-136">详细了解Azure AD，如果没有，请设置一个。</span><span class="sxs-lookup"><span data-stu-id="c70d2-136">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="c70d2-137">了解标识管理以及如何以最佳方式设置Azure AD帐户。</span><span class="sxs-lookup"><span data-stu-id="c70d2-137">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="c70d2-138">详细了解 MDM，并设置 Intune（如果尚未准备好）。</span><span class="sxs-lookup"><span data-stu-id="c70d2-138">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="c70d2-139">熟悉基于证书的 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="c70d2-139">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="c70d2-140">熟悉代理。</span><span class="sxs-lookup"><span data-stu-id="c70d2-140">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="c70d2-141">了解如何使用业务线应用。</span><span class="sxs-lookup"><span data-stu-id="c70d2-141">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="c70d2-142">详细了解为组织使用指南的方式。</span><span class="sxs-lookup"><span data-stu-id="c70d2-142">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="c70d2-143">配置</span><span class="sxs-lookup"><span data-stu-id="c70d2-143">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="c70d2-144">如何创建用户和组。</span><span class="sxs-lookup"><span data-stu-id="c70d2-144">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="c70d2-145">如何设置自动注册。</span><span class="sxs-lookup"><span data-stu-id="c70d2-145">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="c70d2-146">如何为企业Wi-Fi连接设置Wi-Fi证书和配置文件。</span><span class="sxs-lookup"><span data-stu-id="c70d2-146">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="c70d2-147">Upload和分配业务线 (LOB) 应用包。</span><span class="sxs-lookup"><span data-stu-id="c70d2-147">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="c70d2-148">安装程序Dynamics 365 Guides。</span><span class="sxs-lookup"><span data-stu-id="c70d2-148">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="c70d2-149">如何配置展台模式 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="c70d2-149">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="c70d2-150">如何配置 WDAC (可选) 。</span><span class="sxs-lookup"><span data-stu-id="c70d2-150">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="c70d2-151">部署</span><span class="sxs-lookup"><span data-stu-id="c70d2-151">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="c70d2-152">通过设备和 MDM 验证注册。</span><span class="sxs-lookup"><span data-stu-id="c70d2-152">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="c70d2-153">验证Wi-Fi证书。</span><span class="sxs-lookup"><span data-stu-id="c70d2-153">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="c70d2-154">验证 LOB 应用安装。</span><span class="sxs-lookup"><span data-stu-id="c70d2-154">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="c70d2-155">通过创作和操作验证指南。</span><span class="sxs-lookup"><span data-stu-id="c70d2-155">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="c70d2-156">维护</span><span class="sxs-lookup"><span data-stu-id="c70d2-156">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="c70d2-157">更新HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="c70d2-157">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="c70d2-158">如何更新指南 (应用商店应用) 。</span><span class="sxs-lookup"><span data-stu-id="c70d2-158">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="c70d2-159">如何更新 LOB 应用。</span><span class="sxs-lookup"><span data-stu-id="c70d2-159">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="c70d2-160">开发计划。</span><span class="sxs-lookup"><span data-stu-id="c70d2-160">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="c70d2-161">制定支持计划。</span><span class="sxs-lookup"><span data-stu-id="c70d2-161">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="c70d2-162">设备管理选项。</span><span class="sxs-lookup"><span data-stu-id="c70d2-162">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="c70d2-163">下一步</span><span class="sxs-lookup"><span data-stu-id="c70d2-163">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="c70d2-164">企业连接部署 - 准备</span><span class="sxs-lookup"><span data-stu-id="c70d2-164">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
