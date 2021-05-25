---
title: 具有远程协助的云连接的 HoloLens 2 概述
description: 了解如何使用 Dynamics 365 远程协助通过云连接的网络注册 HoloLens 2 设备。
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
ms.openlocfilehash: 43fbcc3a841f6c3f15006f285188e55d22f10599
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397648"
---
# <a name="deployment-guide--cloud-connected-hololens-2-with-remote-assist--overview"></a><span data-ttu-id="d3f74-104">部署指南–云连接了 HoloLens 2 与远程协助–概述</span><span class="sxs-lookup"><span data-stu-id="d3f74-104">Deployment Guide – Cloud connected HoloLens 2 with Remote Assist – Overview</span></span>

<span data-ttu-id="d3f74-105">本指南可帮助 IT 专业人员规划和部署 Microsoft HoloLens 2 设备到其组织，其整体目标是将这些设备云连接到你的组织，并使用 Dynamics 365 远程协助来使用。</span><span class="sxs-lookup"><span data-stu-id="d3f74-105">This guide helps IT professionals plan for and deploy Microsoft HoloLens 2 devices to their organization with the overall goal of having those devices cloud connected to your organization with Dynamics 365 Remote Assist ready to use.</span></span> <span data-ttu-id="d3f74-106">请记住，这将作为对你的组织进行概念证明部署的模型，涵盖各种 HoloLens 2 用例。</span><span class="sxs-lookup"><span data-stu-id="d3f74-106">Keep in mind, this will serve as a model for proof-of-concept deployments to your organization across a variety of HoloLens 2 use cases.</span></span>

<span data-ttu-id="d3f74-107">在本指南中，我们将介绍如何将设备注册到设备管理，根据需要应用许可证，并验证最终用户是否能够在设备设置时立即使用远程协助。</span><span class="sxs-lookup"><span data-stu-id="d3f74-107">During the guide we will cover how to enroll your devices into your device management, apply licenses as needed, and validate that your end users are able to immediately use Remote Assist upon device setup.</span></span> <span data-ttu-id="d3f74-108">要执行此操作，我们将介绍设置和运行所需的重要基础结构，即利用 HoloLens 2 大规模实现部署。</span><span class="sxs-lookup"><span data-stu-id="d3f74-108">To do this we will go over the important pieces of infrastructure needed to get set up and running – achieving deployment at scale with HoloLens 2.</span></span>

<span data-ttu-id="d3f74-109">[![云连接方案 ](./images/deployment-guides-revised-scenario-a.png)](./images/deployment-guides-revised-scenario-a.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d3f74-109">[ ![Cloud connected scenario](./images/deployment-guides-revised-scenario-a.png) ](./images/deployment-guides-revised-scenario-a.png#lightbox)</span></span>
## <a name="in-this-guide"></a><span data-ttu-id="d3f74-110">本指南内容</span><span class="sxs-lookup"><span data-stu-id="d3f74-110">In this Guide</span></span>

<span data-ttu-id="d3f74-111">本指南具有在你的 HoloLens 设备上设置远程协助的具体目标。</span><span class="sxs-lookup"><span data-stu-id="d3f74-111">This guide has the specific goal of setting up Remote Assist within your organization on your HoloLens devices.</span></span> <span data-ttu-id="d3f74-112">我们将介绍实现该目标所需的必要条件。</span><span class="sxs-lookup"><span data-stu-id="d3f74-112">We will cover the necessities needed to achieve that goal.</span></span> <span data-ttu-id="d3f74-113">为了保持焦点在此目标上，将预先选择某些准备和配置，以便针对此部署进行优化或减少配置所需的项。</span><span class="sxs-lookup"><span data-stu-id="d3f74-113">In order to maintain focus on this goal certain preparation and configurations will be pre-selected in order to optimize for this deployment or to reduce the items needed to configure.</span></span> <span data-ttu-id="d3f74-114">系统会通知你这些选择，并可根据你的业务需求自定义你的部署。</span><span class="sxs-lookup"><span data-stu-id="d3f74-114">You will be informed of these choices, and can customize your deployment based on your business needs.</span></span>

<span data-ttu-id="d3f74-115">这是一种设置，类似于 [方案 a：部署到云连接设备](https://docs.microsoft.com/hololens/common-scenarios#scenario-a)，这对于许多概念证明部署是一个不错的选择，其中包括：</span><span class="sxs-lookup"><span data-stu-id="d3f74-115">This is a set up similar to [Scenario A: Deploy to cloud connect devices](https://docs.microsoft.com/hololens/common-scenarios#scenario-a), which is a good option for many Proof of Concept deployments, which will include:</span></span>

- <span data-ttu-id="d3f74-116">Wi-Fi 网络通常会完全开放到 Internet 和云服务</span><span class="sxs-lookup"><span data-stu-id="d3f74-116">Wi-Fi networks are typically fully open to the Internet and Cloud services</span></span>
- <span data-ttu-id="d3f74-117">与 MDM 自动注册 Azure AD 联接--MDM (Intune) 托管</span><span class="sxs-lookup"><span data-stu-id="d3f74-117">Azure AD Join with MDM Auto Enrollment -- MDM (Intune) Managed</span></span>
- <span data-ttu-id="d3f74-118">用户用自己的公司帐户登录 (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="d3f74-118">Users sign in with their own corporate account (Azure AD)</span></span>
  - <span data-ttu-id="d3f74-119">每个设备支持一个或多个用户</span><span class="sxs-lookup"><span data-stu-id="d3f74-119">Single or multiple users per device supported</span></span>
- <span data-ttu-id="d3f74-120">根据特定用例（从"完全打开"到"单应用展台"）应用不同级别的设备锁定配置</span><span class="sxs-lookup"><span data-stu-id="d3f74-120">Varying levels of device lockdown configurations are applied based on specific use cases, from Fully Open to Single App Kiosk</span></span>



<span data-ttu-id="d3f74-121">本指南中不会应用其他设备限制或配置，但我们建议在完成后浏览这些选项。</span><span class="sxs-lookup"><span data-stu-id="d3f74-121">No other device restrictions or configurations will be applied in this guide, however we encourage you to explore those options after finishing.</span></span>

## <a name="learn-about-remote-assist"></a><span data-ttu-id="d3f74-122">了解Remote Assist</span><span class="sxs-lookup"><span data-stu-id="d3f74-122">Learn about Remote Assist</span></span>

<span data-ttu-id="d3f74-123">Remote Assist协作维护和修复、远程检查以及知识共享和培训。</span><span class="sxs-lookup"><span data-stu-id="d3f74-123">Remote Assist allows for collaborative maintenance and repair, remote inspection, as well as knowledge sharing and training.</span></span> <span data-ttu-id="d3f74-124">通过连接不同角色和位置的用户，使用 Remote Assist可以与 Microsoft Teams 上的远程协作者进行连接。</span><span class="sxs-lookup"><span data-stu-id="d3f74-124">By connecting people in different roles and locations a technician using Remote Assist can connect with a remote collaborator on Microsoft Teams.</span></span> <span data-ttu-id="d3f74-125">它们可以组合视频、屏幕截图和批注，以实时解决问题，即使它们&#39;位于同一位置。</span><span class="sxs-lookup"><span data-stu-id="d3f74-125">They can combine video, screenshots, and annotations to solve problems in real time even when they aren&#39;t in the same location.</span></span> <span data-ttu-id="d3f74-126">远程协作者可以插入参考图像、示意图和其他有用的信息，以便技术人员&#39;物理空间，以便他们可以在 HoloLens 上向上和无手工作的同时引用示意图。</span><span class="sxs-lookup"><span data-stu-id="d3f74-126">Remote collaborators can insert reference images, schematics, and other helpful information the technician&#39;s physical space so they can refer to the schematic while working heads-up and hands-free on HoloLens.</span></span>

<iframe width="560" height="315" src="https://www.youtube.com/embed/d3YT8j0yYl0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## <a name="in-this-guide-you-will"></a><span data-ttu-id="d3f74-127">本指南中，你将实现以下操作：</span><span class="sxs-lookup"><span data-stu-id="d3f74-127">In this guide you will:</span></span>

<span data-ttu-id="d3f74-128">准备：</span><span class="sxs-lookup"><span data-stu-id="d3f74-128">Prepare:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="d3f74-129">了解适用于设备HoloLens 2要素。</span><span class="sxs-lookup"><span data-stu-id="d3f74-129">Learn about the infrastructure essentials for HoloLens 2 devices.</span></span>](hololens2-cloud-connected-prepare.md#infrastructure-essentials)
> - [<span data-ttu-id="d3f74-130">详细了解Azure AD，如果还没有，&#39;设置一个。</span><span class="sxs-lookup"><span data-stu-id="d3f74-130">Learn more about Azure AD and set up one if you don&#39;t have it.</span></span>](hololens2-cloud-connected-prepare.md#azure-active-directory)
> - [<span data-ttu-id="d3f74-131">了解标识管理以及如何以最佳方式设置Azure AD帐户。</span><span class="sxs-lookup"><span data-stu-id="d3f74-131">Learn about Identity management and how to best set up Azure AD accounts.</span></span>](hololens2-cloud-connected-prepare.md#identity-management)
> - [<span data-ttu-id="d3f74-132">详细了解 MDM，如果尚未准备好 MDM，&#39;Intune 进行设置。</span><span class="sxs-lookup"><span data-stu-id="d3f74-132">Learn more about MDM, and set up with Intune if you don&#39;t already have one ready.</span></span>](hololens2-cloud-connected-prepare.md#mobile-device-management)
> - [<span data-ttu-id="d3f74-133">了解应用程序的网络Remote Assist。</span><span class="sxs-lookup"><span data-stu-id="d3f74-133">Learn about the networking requirements of Remote Assist.</span></span>](hololens2-cloud-connected-prepare.md#network)
> - [<span data-ttu-id="d3f74-134">（可选）：用于连接到组织资源的 VPN</span><span class="sxs-lookup"><span data-stu-id="d3f74-134">Optionally: VPN to connect to organizational resources</span></span>](/hololens2-cloud-connected-prepare.md#optional-connect-your-hololens-to-vpn)

<span data-ttu-id="d3f74-135">配置：</span><span class="sxs-lookup"><span data-stu-id="d3f74-135">Configure:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="d3f74-136">如何创建用户和组。</span><span class="sxs-lookup"><span data-stu-id="d3f74-136">How to create Users and Groups.</span></span>](hololens2-cloud-connected-configure.md#azure-users-and-groups)
> - [<span data-ttu-id="d3f74-137">如何在 Azure AD 中设置自动Azure AD。</span><span class="sxs-lookup"><span data-stu-id="d3f74-137">How to set up Auto-enrollment within Azure AD.</span></span>](hololens2-cloud-connected-configure.md#auto-enrollment-on-hololens-2)
> - [<span data-ttu-id="d3f74-138">如何分配应用程序许可证。</span><span class="sxs-lookup"><span data-stu-id="d3f74-138">How to assign your Application licenses.</span></span>](hololens2-cloud-connected-configure.md#application-licenses)

<span data-ttu-id="d3f74-139">部署：</span><span class="sxs-lookup"><span data-stu-id="d3f74-139">Deploy:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="d3f74-140">设置你的HoloLens 2并验证注册。</span><span class="sxs-lookup"><span data-stu-id="d3f74-140">Set up your HoloLens 2 and validate enrollment.</span></span>](hololens2-cloud-connected-deploy.md#enrollment-validation)
> - [<span data-ttu-id="d3f74-141">验证是否可进行Remote Assist调用。</span><span class="sxs-lookup"><span data-stu-id="d3f74-141">Validate you can make a Remote Assist call.</span></span>](hololens2-cloud-connected-deploy.md#remote-assist-call-validation)

<span data-ttu-id="d3f74-142">维护：</span><span class="sxs-lookup"><span data-stu-id="d3f74-142">Maintain:</span></span>

> [!div class="checklist"]
> - [<span data-ttu-id="d3f74-143">如何使用 Remote Assist 应用更新Microsoft Store应用。</span><span class="sxs-lookup"><span data-stu-id="d3f74-143">How to update Remote Assist using the Microsoft Store app.</span></span>](hololens2-cloud-connected-maintain.md#updates)
> - [<span data-ttu-id="d3f74-144">制定支持计划。</span><span class="sxs-lookup"><span data-stu-id="d3f74-144">Making a support plan.</span></span>](hololens2-cloud-connected-maintain.md#support-plan)
> - [<span data-ttu-id="d3f74-145">开发计划。</span><span class="sxs-lookup"><span data-stu-id="d3f74-145">Development plan.</span></span>](hololens2-cloud-connected-maintain.md#development-plan)

## <a name="next-step"></a><span data-ttu-id="d3f74-146">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d3f74-146">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d3f74-147">云连接部署-准备</span><span class="sxs-lookup"><span data-stu-id="d3f74-147">Cloud connected deployment - Prepare</span></span>](hololens2-cloud-connected-prepare.md)

