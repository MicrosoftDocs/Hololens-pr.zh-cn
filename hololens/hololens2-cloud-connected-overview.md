---
title: 部署指南–云连接的 HoloLens 2 和远程协助-概述
description: 通过连接到云的网络注册 HoloLens 设备
keywords: HoloLens、管理、云连接、远程协助、AAD、Azure AD、MDM、移动设备管理
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
ms.openlocfilehash: ba3f826360f999a72e671166af7a19d19ce9c567
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196272"
---
# <span data-ttu-id="c9d1a-104">部署指南– Cloud 通过远程协助连接 HoloLens 2-概述</span><span class="sxs-lookup"><span data-stu-id="c9d1a-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="c9d1a-105">本指南可帮助 IT 专业人员规划 Microsoft HoloLens 2 设备并将其部署到其组织，其整体目标是将这些设备云与你的组织连接到你的组织，使其具有可供使用的动态365远程协助。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="c9d1a-106">请记住，这将用作你的组织在各种 HoloLens 2 使用案例中的概念证明部署的模型。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="c9d1a-107">在本指南中，我们将介绍如何将设备注册到你的设备管理，根据需要应用许可证，并验证最终用户是否能够在设置设备时立即使用远程协助。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device set up.</span></span> <span data-ttu-id="c9d1a-108">为此，我们将获得在设置和运行时需要的重要基础结构的重要部分–通过使用 HoloLens 2 的比例实现部署。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

## <span data-ttu-id="c9d1a-109">本指南中</span><span class="sxs-lookup"><span data-stu-id="c9d1a-109">In this Guide</span></span>

<span data-ttu-id="c9d1a-110">本指南具有在您的 HoloLens 设备上设置远程协助的特定目标。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-110">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="c9d1a-111">我们将介绍实现该目标所需的 necessities。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-111">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="c9d1a-112">为了保持重点关注此目标，需要预先选择某些准备和配置，以便针对此部署进行优化或减少需要配置的项目。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-112">In order to maintain focus on this goal certain preparations and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="c9d1a-113">系统将通知你这些选项，并且可以根据你的业务需求自定义你的部署。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-113">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="c9d1a-114">这种设置类似于 [方案 a：部署到云连接设备](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)，这对于许多概念验证部署都是一个不错的选择，其中包括：</span><span class="sxs-lookup"><span data-stu-id="c9d1a-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments which will include:</span></span>

- <span data-ttu-id="c9d1a-115">Wi-Fi 网络通常完全开放于 Internet 和云服务</span><span class="sxs-lookup"><span data-stu-id="c9d1a-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="c9d1a-116">具有 MDM 自动注册的 Azure AD 联接-MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="c9d1a-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="c9d1a-117">用户利用其自己的公司帐户登录 (AAD) </span><span class="sxs-lookup"><span data-stu-id="c9d1a-117">Users sign in with their own corporate account (AAD)</span></span>
  - <span data-ttu-id="c9d1a-118">每个设备支持的单个或多个用户</span><span class="sxs-lookup"><span data-stu-id="c9d1a-118">Single or multiple users per device supported</span></span>
- <span data-ttu-id="c9d1a-119">不同级别的设备锁定配置基于特定使用情形（从完全打开到单应用展台）应用</span><span class="sxs-lookup"><span data-stu-id="c9d1a-119">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![连接到云的方案](./images/cloud-connected-deployment-chart.png)

<span data-ttu-id="c9d1a-121">本指南中不会应用任何其他设备限制或配置，但我们建议你在完成后研究这些选项。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-121">No additional device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <span data-ttu-id="c9d1a-122">了解远程协助</span><span class="sxs-lookup"><span data-stu-id="c9d1a-122">Learn about Remote Assist</span></span>

<span data-ttu-id="c9d1a-123">远程协助允许进行协作维护和修复、远程检查以及知识共享和培训。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="c9d1a-124">通过连接不同角色和位置的人员，使用远程协助的技术人员可以与 Microsoft 团队中的远程协作者联系。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="c9d1a-125">即使在同一位置&#39;t，他们也可以结合视频、屏幕截图和注释来实时解决问题。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="c9d1a-126">远程协作者可以插入参考图像、图表和其他有用的信息技术人员&#39;的物理空间，以便他们可以在使用 HoloLens 和在 HoloLens 上运行时引用示意性的图表。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <span data-ttu-id="c9d1a-127">在本指南中，你将：</span><span class="sxs-lookup"><span data-stu-id="c9d1a-127">In this guide you will:</span></span>

<span data-ttu-id="c9d1a-128">准备</span><span class="sxs-lookup"><span data-stu-id="c9d1a-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="c9d1a-129">了解 HoloLens 2 设备的基础结构基础知识。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="c9d1a-130">了解有关 AAD 的详细信息，如果您不是&#39;的，请设置一个。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-130">Learn more about AAD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="c9d1a-131">了解身份管理以及如何最佳设置 AAD 帐户。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-131">Learn about Identity management and how to best set up AAD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="c9d1a-132">了解有关 MDM 的详细信息，如果&#39;t 已准备好，则使用 Intune 进行设置。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="c9d1a-133">了解远程协助的网络要求。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="c9d1a-134">可选： VPN 连接到组织资源</span><span class="sxs-lookup"><span data-stu-id="c9d1a-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="c9d1a-135">对</span><span class="sxs-lookup"><span data-stu-id="c9d1a-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="c9d1a-136">如何创建用户和组。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="c9d1a-137">如何在 AAD 中设置自动注册。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-137">How to set up Auto-enrollment within AAD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="c9d1a-138">如何分配你的应用程序许可证。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="c9d1a-139">部署</span><span class="sxs-lookup"><span data-stu-id="c9d1a-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="c9d1a-140">设置 HoloLens 2 并验证注册。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="c9d1a-141">验证您是否可以进行远程协助呼叫。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="c9d1a-142">着</span><span class="sxs-lookup"><span data-stu-id="c9d1a-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="c9d1a-143">如何使用 Microsoft Store 应用更新远程协助。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="c9d1a-144">制定支持计划。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="c9d1a-145">开发计划。</span><span class="sxs-lookup"><span data-stu-id="c9d1a-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <span data-ttu-id="c9d1a-146">下一步</span><span class="sxs-lookup"><span data-stu-id="c9d1a-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c9d1a-147">云连接部署-准备</span><span class="sxs-lookup"><span data-stu-id="c9d1a-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

