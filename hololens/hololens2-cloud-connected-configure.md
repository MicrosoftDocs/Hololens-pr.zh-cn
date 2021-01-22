---
title: 部署指南 – 使用远程协助大规模部署云连接的 HoloLens 2 - 配置
description: 了解如何设置配置以通过云连接网络通过远程协助大规模注册 HoloLens 设备。
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
ms.openlocfilehash: 00cc3f9df1fefafc9c4c084ff642364ae3ccb85c
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283883"
---
# <span data-ttu-id="010e7-104">配置 - 云连接指南</span><span class="sxs-lookup"><span data-stu-id="010e7-104">Configure - Cloud connected Guide</span></span>

<span data-ttu-id="010e7-105">在本指南的这一部分中，&#39;将介绍如何为租户设置自动注册以及如何为 Intune 和 Remote Assist 应用许可证。</span><span class="sxs-lookup"><span data-stu-id="010e7-105">In this section of the guide, we&#39;ll go over how to set up Auto Enrollment for your tenant, and how to apply licenses for both Intune and Remote Assist.</span></span>

## <span data-ttu-id="010e7-106">Azure 用户和组</span><span class="sxs-lookup"><span data-stu-id="010e7-106">Azure Users and Groups</span></span>

<span data-ttu-id="010e7-107">Azure 和 Intune 通过该扩展使用用户和组来帮助分配配置和许可证。</span><span class="sxs-lookup"><span data-stu-id="010e7-107">Azure, and Intune by that extension, uses users and groups to help assign configurations and licenses.</span></span> <span data-ttu-id="010e7-108">为了验证此部署流并能够从一个用户向另一个用户进行远程协助呼叫，&#39;两个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="010e7-108">For the sake of validating this deployment flow and being able to make a Remote Assist call from one user to another you&#39;ll need two user accounts.</span></span>

<span data-ttu-id="010e7-109">我们可以创建一个用户组来分配许可证。</span><span class="sxs-lookup"><span data-stu-id="010e7-109">We can make a single user group for the purpose of assigning licenses.</span></span> <span data-ttu-id="010e7-110">我们可以将两个用户加入同一个组，然后向该组应用 Intune 和 Remote Assist 的许可证。</span><span class="sxs-lookup"><span data-stu-id="010e7-110">We can join both users to the same group and apply a license for Intune and Remote Assist to that group.</span></span>

<span data-ttu-id="010e7-111">如果尚未&#39;用户组中的两个 Azure AD 帐户，可以使用;下面是以下快速入门指南：</span><span class="sxs-lookup"><span data-stu-id="010e7-111">If you don&#39;t already have access to two Azure AD accounts in a user group you can use; here are the quick start guides for:</span></span>

- [<span data-ttu-id="010e7-112">如何创建用户</span><span class="sxs-lookup"><span data-stu-id="010e7-112">How to create a user</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-user)
- [<span data-ttu-id="010e7-113">如何创建组</span><span class="sxs-lookup"><span data-stu-id="010e7-113">How to create a group</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/quickstart-create-group)
- <span data-ttu-id="010e7-114">[向组添加用户](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – 添加已创建用户以创建组</span><span class="sxs-lookup"><span data-stu-id="010e7-114">[Add users to a group](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal) – Add created users to create group</span></span>
- <span data-ttu-id="010e7-115">[配置 Azure AD 以允许](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) 用户组加入设备 – 确保新用户组具有将设备注册到 Azure AD 的权限</span><span class="sxs-lookup"><span data-stu-id="010e7-115">[Configure Azure AD to allow a User Group to join devices](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) – Ensure new user group has permission to enroll devices to Azure AD</span></span>

## <span data-ttu-id="010e7-116">HoloLens 2 上的自动注册</span><span class="sxs-lookup"><span data-stu-id="010e7-116">Auto Enrollment on HoloLens 2</span></span>

<span data-ttu-id="010e7-117">若要获得流畅而无缝的体验，可以设置 Azure Active Directory Join (AADJ) 和自动注册到适用于 HoloLens 2 设备的 Intune。</span><span class="sxs-lookup"><span data-stu-id="010e7-117">In order to have a smooth and seamless experience, setting up Azure Active Directory Join (AADJ) and Auto Enrollment to Intune for HoloLens 2 devices is the way to go.</span></span> <span data-ttu-id="010e7-118">这将允许用户在 OOBE 期间输入其组织登录凭据，并自动向 Azure AD 注册设备并注册到 MDM。</span><span class="sxs-lookup"><span data-stu-id="010e7-118">This will allow users to input their organization log-in credentials during OOBE and automatically register with Azure AD and enroll the device into MDM.</span></span>

<span data-ttu-id="010e7-119">通过使用 [Microsoft Endpoint Manager，](https://endpoint.microsoft.com/#home)我们可以选择服务并导航几个页面，直到选择"获取高级试用版"。</span><span class="sxs-lookup"><span data-stu-id="010e7-119">By using [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#home), we can select services and navigate a few pages until we can select Get a Premium trial.</span></span> <span data-ttu-id="010e7-120">你可能会注意到有 Azure Active Directory Premium 1 和 2，对于自动注册 P1 就足够了。</span><span class="sxs-lookup"><span data-stu-id="010e7-120">You may notice there is Azure Active Directory Premium 1 and 2, for Automatic Enrollment P1 is sufficient.</span></span> <span data-ttu-id="010e7-121">我们可以选择 Intune 并选择用户范围进行自动注册，然后选择之前创建的组。</span><span class="sxs-lookup"><span data-stu-id="010e7-121">We can select Intune and select the user scope for automatic enrollment, and select the group that was previously created.</span></span>

<span data-ttu-id="010e7-122">有关完整的详细信息和步骤，请阅读有关如何 [为 Intune 启用自动注册的指南](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="010e7-122">For full details and steps read the guide on [how to enable auto enrollment for Intune](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

## <span data-ttu-id="010e7-123">应用程序许可证</span><span class="sxs-lookup"><span data-stu-id="010e7-123">Application Licenses</span></span>

<span data-ttu-id="010e7-124">应用程序许可证允许用户安装公司购买的应用，或从免费试用版升级到应用的完整版本。</span><span class="sxs-lookup"><span data-stu-id="010e7-124">An application license allows a user to either install company purchased Apps or upgrade from a free trial to the full version of an app.</span></span> <span data-ttu-id="010e7-125">应用程序许可证可应用于用户、用户组或设备组。</span><span class="sxs-lookup"><span data-stu-id="010e7-125">Application licenses can be applied to either users, user groups, or device groups.</span></span> <span data-ttu-id="010e7-126">你需要&#39;远程协助许可证，组织的用户可以使用远程协助。</span><span class="sxs-lookup"><span data-stu-id="010e7-126">You&#39;ll need Remote Assist licenses for users in your organization to use Remote Assist.</span></span> <span data-ttu-id="010e7-127">出于本指南的目的，我们将为上面在 Azure 用户和组中创建的用户组分配远程协助 [许可证](hololens2-cloud-connected-configure.md#azure-users-and-groups)。</span><span class="sxs-lookup"><span data-stu-id="010e7-127">For the purpose of this guide we'll assign Remote Assist licenses to the user group we created above in [Azure Users and Groups](hololens2-cloud-connected-configure.md#azure-users-and-groups).</span></span>

<span data-ttu-id="010e7-128">许可证要求可能有所不同，具体取决于用户是从设备进行远程协助呼叫还是来自 Microsoft Teams 的远程协作者。</span><span class="sxs-lookup"><span data-stu-id="010e7-128">The requirements for licenses can be different depending on if the user will be making the Remote Assist call from a device or will be a remote collaborator from Microsoft Teams.</span></span> <span data-ttu-id="010e7-129">默认情况下，远程协助和 Teams 复选框都标记为。</span><span class="sxs-lookup"><span data-stu-id="010e7-129">By default the Remote Assist and Teams check boxes are both marked.</span></span> <span data-ttu-id="010e7-130">出于本指南的目的，我们建议将默认框保留为选中状态。</span><span class="sxs-lookup"><span data-stu-id="010e7-130">For the purposes of this guide, we suggest leaving the default boxes checked.</span></span>

1. <span data-ttu-id="010e7-131">详细了解每个角色 [的不同许可和产品要求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role)。</span><span class="sxs-lookup"><span data-stu-id="010e7-131">Learn more about the different [Licensing and product requirements per role](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#licensing-and-product-requirements-per-role).</span></span> <span data-ttu-id="010e7-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span><span class="sxs-lookup"><span data-stu-id="010e7-132">There are a few different types of Remote Assist licenses so be sure to get the correct ones for your needs.</span></span>
2. <span data-ttu-id="010e7-133">你&#39;需要 [获取许可证](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)。</span><span class="sxs-lookup"><span data-stu-id="010e7-133">You&#39;ll need to [acquire the license](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist).</span></span>
3. <span data-ttu-id="010e7-134">[将许可证应用于](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) 组。</span><span class="sxs-lookup"><span data-stu-id="010e7-134">[Apply your licenses](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/deploy-remote-assist) to the group.</span></span>

## <span data-ttu-id="010e7-135">下一步</span><span class="sxs-lookup"><span data-stu-id="010e7-135">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="010e7-136">云连接部署 - 部署</span><span class="sxs-lookup"><span data-stu-id="010e7-136">Cloud connected deployment - Deploy</span></span>](hololens2-cloud-connected-deploy.md)