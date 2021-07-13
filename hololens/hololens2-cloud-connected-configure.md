---
title: 部署指南 - 使用 HoloLens 2 大规模部署云Remote Assist - 配置
description: 了解如何设置配置，以使用 HoloLens 通过云连接的网络大规模注册Remote Assist。
keywords: HoloLens、管理、云连接、Remote Assist、AAD、Azure AD、MDM、移动设备管理
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
ms.openlocfilehash: eb96f1cdc799551297c0373268e8cc8f35c6bd06
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635137"
---
# <a name="configure---cloud-connected-guide"></a><span data-ttu-id="4b7b6-104">配置 - 云连接指南</span><span class="sxs-lookup"><span data-stu-id="4b7b6-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="4b7b6-105">在本指南的本部分，我们将&#39;如何为租户设置自动注册，以及如何为 Intune 和 Remote Assist。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <a name="azure-users-and-groups"></a><span data-ttu-id="4b7b6-106">Azure 用户和组</span><span class="sxs-lookup"><span data-stu-id="4b7b6-106">Azure Users and Groups</span></span>

<span data-ttu-id="4b7b6-107">Azure 和 Intune（按该扩展）使用用户和组来帮助分配配置和许可证。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="4b7b6-108">为了验证此部署流并能够进行从一个用户Remote Assist调用另一个用户，&#39;两个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="4b7b6-109">我们可以创建单个用户组来分配许可证。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="4b7b6-110">我们可以将两个用户加入同一组，并应用 Intune 许可证，Remote Assist该组。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="4b7b6-111">如果尚未&#39;两个用户帐户Azure AD可以使用的用户帐户;下面是以下快速入门指南：</span><span class="sxs-lookup"><span data-stu-id="4b7b6-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="4b7b6-112">如何创建用户</span><span class="sxs-lookup"><span data-stu-id="4b7b6-112">How to create a user</span></span>](/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="4b7b6-113">如何创建组</span><span class="sxs-lookup"><span data-stu-id="4b7b6-113">How to create a group</span></span>](/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="4b7b6-114">[将用户添加到组](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 添加创建的用户以创建组</span><span class="sxs-lookup"><span data-stu-id="4b7b6-114">[Add users to a group](/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="4b7b6-115">[配置Azure AD以允许用户组加入设备](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – 确保新用户组有权将设备注册到Azure AD</span><span class="sxs-lookup"><span data-stu-id="4b7b6-115">[Configure Azure AD to allow a User Group to join devices](/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <a name="auto-enrollment-on-hololens-2"></a><span data-ttu-id="4b7b6-116">自动注册HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="4b7b6-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="4b7b6-117">若要获得顺畅无缝的体验，可以设置 Azure Active Directory Join (AADJ) ，以及自动注册到 HoloLens 2 设备的 Intune。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="4b7b6-118">这将允许用户在 OOBE 期间输入其组织登录凭据，并自动向 Azure AD 注册设备并注册到 MDM。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="4b7b6-119">通过使用[Microsoft Endpoint Manager，](https://endpoint.microsoft.com/#home)我们可以选择服务并导航几页，直到选择"获取高级版试用版。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="4b7b6-120">你可能会注意到有一Azure Active Directory Premium 1 和 2，因为自动注册 P1 已足够。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="4b7b6-121">可以选择 Intune 并选择自动注册的用户范围，然后选择之前创建的组。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="4b7b6-122">有关完整详细信息和步骤，请阅读有关 [如何为 Intune 启用自动注册的指南](/mem/intune/enrollment/quickstart-setup-auto-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <a name="application-licenses"></a><span data-ttu-id="4b7b6-123">应用程序许可证</span><span class="sxs-lookup"><span data-stu-id="4b7b6-123">Application Licenses</span></span>

<span data-ttu-id="4b7b6-124">应用程序许可证允许用户安装公司购买的应用，或者从免费试用版升级到应用的完整版本。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="4b7b6-125">应用程序许可证可应用于用户、用户组或设备组。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="4b7b6-126">你&#39;需要Remote Assist许可证，以便组织中用户使用Remote Assist。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="4b7b6-127">在本指南中，我们会将Remote Assist许可证分配给我们上面在 Azure 用户和组 [中创建的用户组](hololens2-cloud-connected-configure.md#azure-users-and-groups)。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="4b7b6-128">许可证的要求可能有所不同，具体取决于用户是从设备进行Remote Assist调用，还是远程协作者从设备Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="4b7b6-129">默认情况下，Remote Assist和Teams复选框都标记为 。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="4b7b6-130">对于本指南，建议选中默认框。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="4b7b6-131">详细了解每个角色 [的不同许可和产品要求](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-131">Learn more about the different [Licensing and product requirements per role](/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="4b7b6-132">有一些不同类型的Remote Assist许可证，因此请确保获得适合你需求的许可证。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="4b7b6-133">你&#39;需要 [获取许可证](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-133">You&#39;ll need to [acquire the license](/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="4b7b6-134">[将许可证](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 应用到组。</span><span class="sxs-lookup"><span data-stu-id="4b7b6-134">[Apply your licenses](/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <a name="next-step"></a><span data-ttu-id="4b7b6-135">下一步</span><span class="sxs-lookup"><span data-stu-id="4b7b6-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4b7b6-136">云连接部署 - 部署</span><span class="sxs-lookup"><span data-stu-id="4b7b6-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)