---
title: 部署指南-云通过远程辅助功能在扩展时连接到 HoloLens 2 部署-配置
description: 如何设置配置以通过云连接的网络注册 HoloLens 设备
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
ms.openlocfilehash: 43b9db96a2c29d1e3a798d0c695ab6edaa8199ac
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196267"
---
# <span data-ttu-id="4d6a8-104">配置-云连接指南</span><span class="sxs-lookup"><span data-stu-id="4d6a8-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="4d6a8-105">在本指南的此部分中，我们&#39;将介绍如何为租户设置自动注册，以及如何为 Intune 和远程协助应用许可证。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-105">In this section of the guide we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <span data-ttu-id="4d6a8-106">Azure 用户和组</span><span class="sxs-lookup"><span data-stu-id="4d6a8-106">Azure Users and Groups</span></span>

<span data-ttu-id="4d6a8-107">Azure 和通过该扩展的 Intune，使用用户和组来帮助分配配置和许可证。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="4d6a8-108">为了验证此部署流程并能够使来自一个用户的远程协助呼叫成为另一个用户，&#39;需要2个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need 2 user accounts.</span></span>

<span data-ttu-id="4d6a8-109">我们可以创建单个用户组来分配许可证。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="4d6a8-110">我们可以将这两个用户加入同一组，并对该组应用 Intune 和远程协助的许可证。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="4d6a8-111">如果您没有&#39;t 对您可以使用的用户组中的两个 AAD 帐户具有访问权限，请执行以下设置：以下是的快速入门指南：</span><span class="sxs-lookup"><span data-stu-id="4d6a8-111">If you don&#39;t already have access to two AAD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="4d6a8-112">如何创建用户</span><span class="sxs-lookup"><span data-stu-id="4d6a8-112">How to create a user</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="4d6a8-113">如何创建组</span><span class="sxs-lookup"><span data-stu-id="4d6a8-113">How to create a group</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="4d6a8-114">[将用户添加到组](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) -添加创建的用户以创建组</span><span class="sxs-lookup"><span data-stu-id="4d6a8-114">[Add users to a group](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="4d6a8-115">[将 AAD 配置为允许用户组加入设备](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) -确保新用户组有权向 AAD 注册设备</span><span class="sxs-lookup"><span data-stu-id="4d6a8-115">[Configure AAD to allow a User Group to join devices](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to AAD</span></span>

## <span data-ttu-id="4d6a8-116">HoloLens 2 上的自动注册</span><span class="sxs-lookup"><span data-stu-id="4d6a8-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="4d6a8-117">为了获得流畅且无缝的体验，设置 Azure Active Directory 加入 (AADJ) 并将自动注册到 HoloLens 2 设备的方式是转到 Intune 2 设备。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="4d6a8-118">这将允许用户只需在 OOBE 期间输入其组织的登录凭据，并自动向 AAD 注册，并将设备注册到 MDM。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-118">This will allow users to simply input their organization log-in credentials during OOBE and automatically register with AAD and enroll the device into MDM.</span></span>

<span data-ttu-id="4d6a8-119">通过使用 [Microsoft 终结点管理器](https://endpoint.microsoft.com/#home) ，我们可以选择服务并导航几个页面，直到可以选择 "获取 Premium 试用版"。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home) we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="4d6a8-120">你很多注意到有 Azure Active Directory Premium 1 和2，因此自动注册 P1 已足够。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-120">You many notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="4d6a8-121">我们可以选择 Intune 并选择自动注册的用户范围，并选择之前创建的组。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="4d6a8-122">有关完整的详细信息和步骤，请阅读有关 [如何启用 Intune 自动注册](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)的指南。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-122">For full details and steps please read the guide on [how to enable auto enrollment for Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <span data-ttu-id="4d6a8-123">应用程序许可证</span><span class="sxs-lookup"><span data-stu-id="4d6a8-123">Application Licenses</span></span>

<span data-ttu-id="4d6a8-124">应用程序许可证允许用户安装公司购买的应用或从免费试用版升级到应用的完整版本。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="4d6a8-125">应用程序许可证可应用于用户、用户组或设备组。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="4d6a8-126">您&#39;需要您组织中的用户使用远程协助的远程协助许可证。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="4d6a8-127">出于本指南的目的，我们将向在 [Azure 用户和组](hololens2-cloud-connected-configure.md#azure-users-and-groups)中创建的用户组分配远程协助许可证。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="4d6a8-128">根据用户是否要从设备进行远程协助呼叫或从 Microsoft 团队发起远程协作者，许可证的要求可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="4d6a8-129">默认情况下，"远程协助" 和 "团队" 复选框均标记。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="4d6a8-130">出于本指南的目的，建议保持选中 "默认框"。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-130">For the purposes of this guide, we suggest to leave the default boxes checked.</span></span>

1. <span data-ttu-id="4d6a8-131">了解有关 [每个角色的不同许可和产品要求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-131">Learn more about the different [Licensing and product requirements per role](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="4d6a8-132">有几种不同类型的远程协助许可证，因此请务必为您的需要获得正确的许可证。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="4d6a8-133">您&#39;需要 [获取许可证](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-133">You&#39;ll need to [acquire the license](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="4d6a8-134">[将许可证应用](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 到组。</span><span class="sxs-lookup"><span data-stu-id="4d6a8-134">[Apply your licenses](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <span data-ttu-id="4d6a8-135">下一步</span><span class="sxs-lookup"><span data-stu-id="4d6a8-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4d6a8-136">云连接部署-部署</span><span class="sxs-lookup"><span data-stu-id="4d6a8-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)