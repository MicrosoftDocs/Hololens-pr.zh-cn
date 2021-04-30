---
title: 部署指南–云连接的 HoloLens 2 大规模部署，具有远程协助-配置
description: 了解如何设置配置以使用远程协助在大规模连接的云连接网络上注册 HoloLens 设备。
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308388"
---
# <a name="configure---cloud-connected-guide"></a><span data-ttu-id="9a08d-104">配置-云连接指南</span><span class="sxs-lookup"><span data-stu-id="9a08d-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="9a08d-105">在本指南的此部分中，我们&#39;介绍如何为租户设置自动注册，以及如何为 Intune 和远程协助应用许可证。</span><span class="sxs-lookup"><span data-stu-id="9a08d-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="9a08d-106">Azure 用户和组</span><span class="sxs-lookup"><span data-stu-id="9a08d-106">Azure Users and Groups</span></span>

<span data-ttu-id="9a08d-107">Azure 以及该扩展的 Intune 使用用户和组来帮助分配配置和许可证。</span><span class="sxs-lookup"><span data-stu-id="9a08d-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="9a08d-108">为了验证此部署流并能够向另一个用户提供远程协助调用，&#39;需要两个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9a08d-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="9a08d-109">我们可以将单个用户组作为分配许可证的目的。</span><span class="sxs-lookup"><span data-stu-id="9a08d-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="9a08d-110">我们可以将这两个用户加入到同一个组中，并将 Intune 和远程协助的许可证应用到该组。</span><span class="sxs-lookup"><span data-stu-id="9a08d-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="9a08d-111">如果你不&#39;t 已经有权访问用户组中可以使用的两个 Azure AD 帐户;下面是有关的快速入门指南：</span><span class="sxs-lookup"><span data-stu-id="9a08d-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="9a08d-112">如何创建用户</span><span class="sxs-lookup"><span data-stu-id="9a08d-112">How to create a user</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="9a08d-113">如何创建组</span><span class="sxs-lookup"><span data-stu-id="9a08d-113">How to create a group</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="9a08d-114">[将用户添加到组](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) –将创建的用户添加到创建组</span><span class="sxs-lookup"><span data-stu-id="9a08d-114">[Add users to a group](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="9a08d-115">[配置 Azure AD 允许用户组加入设备](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) –确保新的用户组有权注册设备 Azure AD</span><span class="sxs-lookup"><span data-stu-id="9a08d-115">[Configure Azure AD to allow a User Group to join devices](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="9a08d-116">在 HoloLens 2 上自动注册</span><span class="sxs-lookup"><span data-stu-id="9a08d-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="9a08d-117">若要获得流畅且无缝的体验，请将 Azure Active Directory 加入 (AADJ) 和自动注册到 Intune 2 设备的 Intune，这就是一种方法。</span><span class="sxs-lookup"><span data-stu-id="9a08d-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="9a08d-118">这将允许用户在 OOBE 期间输入其组织的登录凭据，并自动注册 Azure AD 并将设备注册到 MDM。</span><span class="sxs-lookup"><span data-stu-id="9a08d-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="9a08d-119">通过使用 [Microsoft 终结点管理器](https://endpoint.microsoft.com/#home)，我们可以选择 "服务" 并导航几个页面，直到可以选择 "获取高级试用版"。</span><span class="sxs-lookup"><span data-stu-id="9a08d-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="9a08d-120">你可能会注意到 Azure Active Directory Premium 1 和2，自动注册 P1 就已足够。</span><span class="sxs-lookup"><span data-stu-id="9a08d-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="9a08d-121">我们可以选择 Intune 并选择自动注册的用户作用域，并选择之前创建的组。</span><span class="sxs-lookup"><span data-stu-id="9a08d-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="9a08d-122">有关完整的详细信息和步骤，请阅读有关 [如何启用 Intune 自动注册](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)的指南。</span><span class="sxs-lookup"><span data-stu-id="9a08d-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="application-licenses"></a><span data-ttu-id="9a08d-123">应用程序许可证</span><span class="sxs-lookup"><span data-stu-id="9a08d-123">Application Licenses</span></span>

<span data-ttu-id="9a08d-124">使用应用程序许可证，用户可以安装公司购买的应用，也可以从免费试用版升级到完整版本的应用。</span><span class="sxs-lookup"><span data-stu-id="9a08d-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="9a08d-125">可将应用程序许可证应用到用户、用户组或设备组。</span><span class="sxs-lookup"><span data-stu-id="9a08d-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="9a08d-126">你&#39;要求你的组织中的用户使用远程协助。</span><span class="sxs-lookup"><span data-stu-id="9a08d-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="9a08d-127">出于本指南的目的，我们将向我们在 [Azure 用户和组](hololens2-cloud-connected-configure.md#azure-users-and-groups)中创建的用户组分配远程协助许可证。</span><span class="sxs-lookup"><span data-stu-id="9a08d-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="9a08d-128">根据用户是要从设备进行远程协助调用，还是从 Microsoft 团队远程协作，就许可证的要求可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="9a08d-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="9a08d-129">默认情况下，将标记 "远程协助" 和 "团队" 复选框。</span><span class="sxs-lookup"><span data-stu-id="9a08d-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="9a08d-130">出于本指南的目的，我们建议保留默认框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="9a08d-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="9a08d-131">详细了解 [每个角色的不同许可和产品要求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)。</span><span class="sxs-lookup"><span data-stu-id="9a08d-131">Learn more about the different [Licensing and product requirements per role](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="9a08d-132">有几种不同类型的远程协助许可证，请务必根据需要获取正确的许可证。</span><span class="sxs-lookup"><span data-stu-id="9a08d-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="9a08d-133">你&#39;需要 [获取许可证](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)。</span><span class="sxs-lookup"><span data-stu-id="9a08d-133">You&#39;ll need to [acquire the license](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="9a08d-134">[将许可证应用](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 到组。</span><span class="sxs-lookup"><span data-stu-id="9a08d-134">[Apply your licenses](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <a name="next-step"></a><span data-ttu-id="9a08d-135">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9a08d-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9a08d-136">云连接部署-部署</span><span class="sxs-lookup"><span data-stu-id="9a08d-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)