---
title: 云连接的 HoloLens 2 和远程协助概述
description: 了解如何使用 Dynamics 365 远程协助通过云连接网络注册 HoloLens 2 设备。
keywords: HoloLens， 管理， 云连接， 远程协助， AAD， Azure AD， MDM， 移动设备管理
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
ms.openlocfilehash: 835b4be101b665d2b86c2170a65c04697686e403
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283073"
---
# <span data-ttu-id="e8e44-104">部署指南 – 云连接的 HoloLens 2 和远程协助 – 概述</span><span class="sxs-lookup"><span data-stu-id="e8e44-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="e8e44-105">本指南可帮助 IT 专业人员计划 Microsoft HoloLens 2 设备并部署到其组织，总体目标是使这些设备云连接到你的组织，并准备好使用 Dynamics 365 远程协助。</span><span class="sxs-lookup"><span data-stu-id="e8e44-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="e8e44-106">请记住，这将用作跨各种 HoloLens 2 用例向组织进行概念证明部署的模型。</span><span class="sxs-lookup"><span data-stu-id="e8e44-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="e8e44-107">在指南中，我们将介绍如何将设备注册到设备管理中，根据需要应用许可证，并验证最终用户能否在设备设置时立即使用远程协助。</span><span class="sxs-lookup"><span data-stu-id="e8e44-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="e8e44-108">为此，我们将了解设置和运行所需的重要基础结构部分 ， 通过 HoloLens 2 大规模实现部署。</span><span class="sxs-lookup"><span data-stu-id="e8e44-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

## <span data-ttu-id="e8e44-109">本指南中</span><span class="sxs-lookup"><span data-stu-id="e8e44-109">In this Guide</span></span>

<span data-ttu-id="e8e44-110">本指南的特定目标是在 HoloLens 设备上在组织中设置远程协助。</span><span class="sxs-lookup"><span data-stu-id="e8e44-110">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="e8e44-111">我们将介绍实现该目标所需的措施。</span><span class="sxs-lookup"><span data-stu-id="e8e44-111">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="e8e44-112">为了继续关注此目标，将预先选择某些准备和配置，以便针对此部署进行优化或减少配置所需的项目。</span><span class="sxs-lookup"><span data-stu-id="e8e44-112">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="e8e44-113">将告知你这些选项，并可以根据您的业务需求自定义部署。</span><span class="sxs-lookup"><span data-stu-id="e8e44-113">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="e8e44-114">这是类似于方案 [A：](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)部署到云连接设备的设置，这是许多概念证明部署的良好选择，其中包括：</span><span class="sxs-lookup"><span data-stu-id="e8e44-114">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="e8e44-115">Wi-Fi网络通常对 Internet 和云服务完全开放</span><span class="sxs-lookup"><span data-stu-id="e8e44-115">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="e8e44-116">通过 MDM 自动注册加入 Azure AD - MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="e8e44-116">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="e8e44-117">用户使用自己的公司帐户登录 Azure AD (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="e8e44-117">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="e8e44-118">支持每个设备的一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="e8e44-118">Single or multiple users per device supported</span></span>
- <span data-ttu-id="e8e44-119">根据特定用例应用不同级别的设备锁定配置，从"完全打开"到"单个应用展台"</span><span class="sxs-lookup"><span data-stu-id="e8e44-119">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>

![云连接方案](./images/cloud-connected-guide-diagram.png)

<span data-ttu-id="e8e44-121">本指南中不会应用任何其他设备限制或配置，但我们鼓励你在完成后探索这些选项。</span><span class="sxs-lookup"><span data-stu-id="e8e44-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <span data-ttu-id="e8e44-122">了解远程协助</span><span class="sxs-lookup"><span data-stu-id="e8e44-122">Learn about Remote Assist</span></span>

<span data-ttu-id="e8e44-123">远程协助支持协作维护和修复、远程检查以及知识共享和培训。</span><span class="sxs-lookup"><span data-stu-id="e8e44-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="e8e44-124">通过连接不同角色和位置的用户，使用远程协助的技术人员可以与 Microsoft Teams 上的远程协作者联系。</span><span class="sxs-lookup"><span data-stu-id="e8e44-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="e8e44-125">他们可以将视频、屏幕截图和注释组合在一起，以实时解决问题，即使它们&#39;位置不同。</span><span class="sxs-lookup"><span data-stu-id="e8e44-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="e8e44-126">远程协作者可以插入参考图像、示意图和其他有用的信息，技术人员&#39;物理空间，以便他们可以在 HoloLens 上进行工作向上和自由操作时参考示意图。</span><span class="sxs-lookup"><span data-stu-id="e8e44-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <span data-ttu-id="e8e44-127">在本指南中，你将：</span><span class="sxs-lookup"><span data-stu-id="e8e44-127">In this guide you will:</span></span>

<span data-ttu-id="e8e44-128">准备：</span><span class="sxs-lookup"><span data-stu-id="e8e44-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e8e44-129">了解 HoloLens 2 设备的基础结构要素。</span><span class="sxs-lookup"><span data-stu-id="e8e44-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="e8e44-130">了解有关 Azure AD 以及设置 Azure AD（如果尚未&#39;）的信息。</span><span class="sxs-lookup"><span data-stu-id="e8e44-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="e8e44-131">了解标识管理以及如何以最佳方式设置 Azure AD 帐户。</span><span class="sxs-lookup"><span data-stu-id="e8e44-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="e8e44-132">了解有关 MDM 的更多信息，如果尚未准备好，&#39;使用 Intune 进行设置。</span><span class="sxs-lookup"><span data-stu-id="e8e44-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="e8e44-133">了解远程协助的网络要求。</span><span class="sxs-lookup"><span data-stu-id="e8e44-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="e8e44-134">（可选）：用于连接到组织资源的 VPN</span><span class="sxs-lookup"><span data-stu-id="e8e44-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="e8e44-135">配置：</span><span class="sxs-lookup"><span data-stu-id="e8e44-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e8e44-136">如何创建用户和组。</span><span class="sxs-lookup"><span data-stu-id="e8e44-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="e8e44-137">如何在 Azure AD 中设置自动注册。</span><span class="sxs-lookup"><span data-stu-id="e8e44-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="e8e44-138">如何分配应用程序许可证。</span><span class="sxs-lookup"><span data-stu-id="e8e44-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="e8e44-139">部署：</span><span class="sxs-lookup"><span data-stu-id="e8e44-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e8e44-140">设置 HoloLens 2 并验证注册。</span><span class="sxs-lookup"><span data-stu-id="e8e44-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="e8e44-141">验证你可以进行远程协助呼叫。</span><span class="sxs-lookup"><span data-stu-id="e8e44-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="e8e44-142">维护：</span><span class="sxs-lookup"><span data-stu-id="e8e44-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="e8e44-143">如何使用 Microsoft Store 应用更新远程协助。</span><span class="sxs-lookup"><span data-stu-id="e8e44-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="e8e44-144">制定支持计划。</span><span class="sxs-lookup"><span data-stu-id="e8e44-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="e8e44-145">开发计划。</span><span class="sxs-lookup"><span data-stu-id="e8e44-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <span data-ttu-id="e8e44-146">下一步</span><span class="sxs-lookup"><span data-stu-id="e8e44-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e8e44-147">云连接部署 - 准备</span><span class="sxs-lookup"><span data-stu-id="e8e44-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

