---
title: 部署指南 - 使用 Dynamics 365 指南的企业连接的 HoloLens 2 - 概述
description: 了解如何通过企业连接网络通过 Dynamics 365 Guides 注册 HoloLens 2 设备。
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
ms.openlocfilehash: 3041a31e6a4f8b51385fa02dfddc21d56993721d
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448515"
---
# <a name="deployment-guide---corporate-connected-hololens-2-with-dynamics-365-guides---overview"></a><span data-ttu-id="1b96b-104">部署指南 - 使用 Dynamics 365 指南的企业连接的 HoloLens 2 - 概述</span><span class="sxs-lookup"><span data-stu-id="1b96b-104">Deployment Guide - Corporate Connected HoloLens 2 with Dynamics 365 Guides - Overview</span></span>

<span data-ttu-id="1b96b-105">本指南将借助 Dynamics 365 指南和指南帮助 IT 专业人员计划和部署 Microsoft HoloLens 2 (指南) 组织。</span><span class="sxs-lookup"><span data-stu-id="1b96b-105">This guide will help IT professionals plan for and deploy Microsoft HoloLens 2 devices with Dynamics 365 Guides (Guides) to their organization.</span></span> <span data-ttu-id="1b96b-106">本指南非常适用于试验和生产部署，类似于方案 [B：在组织的网络内部部署](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) 指南。</span><span class="sxs-lookup"><span data-stu-id="1b96b-106">This guide is great for pilots as well as production deployments and is similar to the [Scenario B: Deploy inside your organization's network](https://docs.microsoft.com/hololens/common-scenarios#scenario-b-deploy-inside-your-organizations-network) guide.</span></span> <span data-ttu-id="1b96b-107">测试概念证明后，使用本指南将 HoloLens 集成到组织中。</span><span class="sxs-lookup"><span data-stu-id="1b96b-107">After testing your proof-of-concept, use this guide to move forward with integrating HoloLens into your organization.</span></span>

<span data-ttu-id="1b96b-108">在本指南中，我们将介绍在设备设置后如何将设备注册到现有设备管理中、根据需要应用许可证，并验证最终用户能否运行 Dynamics 365 指南以及使用自定义业务线应用。</span><span class="sxs-lookup"><span data-stu-id="1b96b-108">In this guide, we will cover how to enroll your devices into your existing device management, apply licenses as needed, and validate that your end users are able to operate a Dynamics 365 Guide, as well as use custom line of business apps, after device set up.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="1b96b-109">必备条件</span><span class="sxs-lookup"><span data-stu-id="1b96b-109">Prerequisites</span></span>

<span data-ttu-id="1b96b-110">以下基础结构应已就位：</span><span class="sxs-lookup"><span data-stu-id="1b96b-110">The following infrastructure should already be in place:</span></span>
- <span data-ttu-id="1b96b-111">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="1b96b-111">Wi-Fi</span></span>
    - <span data-ttu-id="1b96b-112">具有内部资源访问权限和 Internet 或云服务受限访问权的内部企业网络</span><span class="sxs-lookup"><span data-stu-id="1b96b-112">Internal corporate network with access to internal resources and limited access to the internet or Cloud services</span></span>
    - <span data-ttu-id="1b96b-113">基于设备的证书身份验证。</span><span class="sxs-lookup"><span data-stu-id="1b96b-113">Device-based certificate authentication.</span></span>
- <span data-ttu-id="1b96b-114">Azure Active Directory (Azure AD) 加入所需的 [Azure AD P1](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) 订阅 (MDM 自动注册) </span><span class="sxs-lookup"><span data-stu-id="1b96b-114">Azure Active Directory (Azure AD) Join with MDM Auto Enrollment ([Azure AD P1 subscription](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) needed)</span></span>
- <span data-ttu-id="1b96b-115">Mdm (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="1b96b-115">MDM (Intune) Managed</span></span>
    - <span data-ttu-id="1b96b-116">一个或多个应用程序通过 MDM 部署。</span><span class="sxs-lookup"><span data-stu-id="1b96b-116">One or more applications are deployed via MDM.</span></span>
- <span data-ttu-id="1b96b-117">网络</span><span class="sxs-lookup"><span data-stu-id="1b96b-117">Network</span></span> 
    - <span data-ttu-id="1b96b-118">SCEP (PKCS 证书) </span><span class="sxs-lookup"><span data-stu-id="1b96b-118">Certificates (SCEP or PKCS)</span></span>
    - <span data-ttu-id="1b96b-119">代理配置</span><span class="sxs-lookup"><span data-stu-id="1b96b-119">Proxy configuration</span></span>
- <span data-ttu-id="1b96b-120">用户使用自己的公司帐户在 Azure AD (登录) </span><span class="sxs-lookup"><span data-stu-id="1b96b-120">Users sign in with their own corporate account (Azure AD)</span></span>
    - <span data-ttu-id="1b96b-121">支持每个设备的一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="1b96b-121">Single or multiple users per device is supported.</span></span>
- <span data-ttu-id="1b96b-122">根据特定用例应用的不同设备锁定配置级别，从完全打开到单个应用展台。</span><span class="sxs-lookup"><span data-stu-id="1b96b-122">Varying levels of device lockdown configurations applied based on specific use cases, from Fully Open to Single App Kiosk.</span></span>

## [<a name="guides-licensing-and-requirements"></a><span data-ttu-id="1b96b-123">指南 许可和要求</span><span class="sxs-lookup"><span data-stu-id="1b96b-123">Guides Licensing and Requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements#licensing-and-product-requirements)
- <span data-ttu-id="1b96b-124">Azure AD 帐户</span><span class="sxs-lookup"><span data-stu-id="1b96b-124">Azure AD account</span></span>
- <span data-ttu-id="1b96b-125">Dynamics 365 指南应用程序电脑和 HoloLens</span><span class="sxs-lookup"><span data-stu-id="1b96b-125">Dynamics 365 Guides applications PC and HoloLens</span></span>
- <span data-ttu-id="1b96b-126">Dynamics 365 Guides 订阅</span><span class="sxs-lookup"><span data-stu-id="1b96b-126">Dynamics 365 Guides subscription</span></span>
    - <span data-ttu-id="1b96b-127">Microsoft Dataverse (包括) </span><span class="sxs-lookup"><span data-stu-id="1b96b-127">Microsoft Dataverse (included)</span></span>
    - <span data-ttu-id="1b96b-128">Power Apps (包括) </span><span class="sxs-lookup"><span data-stu-id="1b96b-128">Power Apps (included)</span></span>
- <span data-ttu-id="1b96b-129">Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="1b96b-129">Power BI Desktop</span></span>
- <span data-ttu-id="1b96b-130">网络连接</span><span class="sxs-lookup"><span data-stu-id="1b96b-130">Network Connectivity</span></span>

![企业连接的网络图](./images/corpconnected-diagHL2-guides.png)

## <a name="stages-of-deployment"></a><span data-ttu-id="1b96b-132">部署阶段</span><span class="sxs-lookup"><span data-stu-id="1b96b-132">Stages of Deployment</span></span>
### <a name="prepare"></a><span data-ttu-id="1b96b-133">准备</span><span class="sxs-lookup"><span data-stu-id="1b96b-133">Prepare</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="1b96b-134">了解 HoloLens 2 设备的基础结构要素。</span><span class="sxs-lookup"><span data-stu-id="1b96b-134">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-corp-connected-prepare.md#infrastructure-essentials)
>- [<span data-ttu-id="1b96b-135">详细了解 Azure AD，如果没有，请设置一个。</span><span class="sxs-lookup"><span data-stu-id="1b96b-135">Learn more about Azure AD and set up one if you don't have it.</span></span>](hololens2-corp-connected-prepare.md#azure-active-directory)
>- [<span data-ttu-id="1b96b-136">了解标识管理以及如何以最佳方式设置 Azure AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="1b96b-136">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-corp-connected-prepare.md#identity-management)
>- [<span data-ttu-id="1b96b-137">了解有关 MDM 和 Intune 设置（如果你还没有准备好 MDM）的更多信息。</span><span class="sxs-lookup"><span data-stu-id="1b96b-137">Learn more about MDM and set up with Intune if you don't already have one ready.</span></span>](hololens2-corp-connected-prepare.md#mobile-device-management)
>- [<span data-ttu-id="1b96b-138">熟悉基于证书的 WLAN。</span><span class="sxs-lookup"><span data-stu-id="1b96b-138">Familiarize yourself with certificate-based Wi-Fi.</span></span>](hololens2-corp-connected-prepare.md#certificates)
>- [<span data-ttu-id="1b96b-139">熟悉代理。</span><span class="sxs-lookup"><span data-stu-id="1b96b-139">Familiarize yourself with Proxy.</span></span>](hololens2-corp-connected-prepare.md#proxy)
>- [<span data-ttu-id="1b96b-140">了解如何使用业务线应用。</span><span class="sxs-lookup"><span data-stu-id="1b96b-140">Understand how you can use Line of Business Apps.</span></span>](hololens2-corp-connected-prepare.md#line-of-business-apps)
>- [<span data-ttu-id="1b96b-141">了解有关你为组织使用指南的方式。</span><span class="sxs-lookup"><span data-stu-id="1b96b-141">Learn more about the way you can use Guides for your organization.</span></span>](hololens2-corp-connected-prepare.md#guides-playbook)
### <a name="configure"></a><span data-ttu-id="1b96b-142">配置</span><span class="sxs-lookup"><span data-stu-id="1b96b-142">Configure</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="1b96b-143">如何创建用户和组。</span><span class="sxs-lookup"><span data-stu-id="1b96b-143">How to create users and groups.</span></span>](hololens2-corp-connected-configure.md#azure-users-and-groups)
>- [<span data-ttu-id="1b96b-144">如何设置自动注册。</span><span class="sxs-lookup"><span data-stu-id="1b96b-144">How to set up Auto Enrollment.</span></span>](hololens2-corp-connected-configure.md#auto-enrollment-on-hololens-2)
>- [<span data-ttu-id="1b96b-145">如何为 Corporate Wi-Fi Connectivity 设置 Wi-Fi 证书和配置文件。</span><span class="sxs-lookup"><span data-stu-id="1b96b-145">How to set up Wi-Fi certificates and profiles for Corporate Wi-Fi Connectivity.</span></span>](hololens2-corp-connected-configure.md#corporate-wi-fi-connectivity)
>- [<span data-ttu-id="1b96b-146">上传并分配业务线 (LOB) 应用包。</span><span class="sxs-lookup"><span data-stu-id="1b96b-146">Upload and Assign Line of Business (LOB) App packages.</span></span>](hololens2-corp-connected-configure.md#app-deployment)
>- [<span data-ttu-id="1b96b-147">设置 Dynamics 365 Guides。</span><span class="sxs-lookup"><span data-stu-id="1b96b-147">Setup Dynamics 365 Guides.</span></span>](hololens2-corp-connected-configure.md#setup-guides-application-licenses-dataverse-and-authoring)
>- [<span data-ttu-id="1b96b-148">如何配置展台模式 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="1b96b-148">How to configure Kiosk Mode (optional).</span></span>](hololens2-corp-connected-configure.md#optional-kiosk-mode)
>- [<span data-ttu-id="1b96b-149">如何配置 WDAC (可选) 。</span><span class="sxs-lookup"><span data-stu-id="1b96b-149">How to configure WDAC (optional).</span></span>](hololens2-corp-connected-configure.md#optional-wdac)
### <a name="deploy"></a><span data-ttu-id="1b96b-150">部署</span><span class="sxs-lookup"><span data-stu-id="1b96b-150">Deploy</span></span>
> [!div class="checklist"]
>-  [<span data-ttu-id="1b96b-151">通过设备和 MDM 验证注册。</span><span class="sxs-lookup"><span data-stu-id="1b96b-151">Validate enrollment via device and MDM.</span></span>](hololens2-corp-connected-deploy.md#enrollment-validation)
>-  [<span data-ttu-id="1b96b-152">验证Wi-Fi证书。</span><span class="sxs-lookup"><span data-stu-id="1b96b-152">Validate Wi-Fi certificates.</span></span>](hololens2-corp-connected-deploy.md#wi-fi-certificate-validation)
>-  [<span data-ttu-id="1b96b-153">验证 LOB 应用安装。</span><span class="sxs-lookup"><span data-stu-id="1b96b-153">Validate LOB app install.</span></span>](hololens2-corp-connected-deploy.md#validate-lob-app-install)
>-  [<span data-ttu-id="1b96b-154">通过创作和操作验证指南。</span><span class="sxs-lookup"><span data-stu-id="1b96b-154">Validate Guides via authoring and operating.</span></span>](hololens2-corp-connected-deploy.md#validate-dynamics-365-guides)
### <a name="maintain"></a><span data-ttu-id="1b96b-155">维护</span><span class="sxs-lookup"><span data-stu-id="1b96b-155">Maintain</span></span>
> [!div class="checklist"]
>- [<span data-ttu-id="1b96b-156">更新 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="1b96b-156">Update HoloLens 2.</span></span>](hololens2-corp-connected-maintain.md#update-hololens)
>- [<span data-ttu-id="1b96b-157">如何更新指南 (应用) 。</span><span class="sxs-lookup"><span data-stu-id="1b96b-157">How to update Guides (store apps).</span></span>](hololens2-corp-connected-maintain.md#how-to-update-dynamics-365-guides-and-other-store-apps)
>- [<span data-ttu-id="1b96b-158">如何更新 LOB 应用。</span><span class="sxs-lookup"><span data-stu-id="1b96b-158">How to update LOB apps.</span></span>](hololens2-corp-connected-maintain.md#how-to-update-lob-apps) 
>- [<span data-ttu-id="1b96b-159">开发计划。</span><span class="sxs-lookup"><span data-stu-id="1b96b-159">Development plan.</span></span>](hololens2-corp-connected-maintain.md#development-plan) 
>- [<span data-ttu-id="1b96b-160">制定支持计划。</span><span class="sxs-lookup"><span data-stu-id="1b96b-160">Making a support plan.</span></span>](hololens2-corp-connected-maintain.md#support-plan)
>- [<span data-ttu-id="1b96b-161">设备管理选项。</span><span class="sxs-lookup"><span data-stu-id="1b96b-161">Device management options.</span></span>](hololens2-corp-connected-maintain.md#device-management)

## <a name="next-step"></a><span data-ttu-id="1b96b-162">下一步</span><span class="sxs-lookup"><span data-stu-id="1b96b-162">Next step</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="1b96b-163">企业连接的部署 - 准备</span><span class="sxs-lookup"><span data-stu-id="1b96b-163">Corporate connected deployment - Prepare</span></span>](hololens2-corp-connected-prepare.md)
