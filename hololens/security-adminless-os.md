---
title: 无管理操作系统安全性
description: 了解 HoloLens 混合现实设备上无管理操作系统、设备所有者和安全性。
ms.prod: hololens
author: evmill
ms.author: v-evmill
ms.reviewer: tagran
ms.date: 6/30/2020
ms.topic: article
keywords: 安全, hololens, 无管理, 操作系统, 无管理操作系统, 管理操作系统, 无管理操作系统, hololens 2, hololens 2 安全,
ms.localizationpriority: high
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 972bbc689505d42993cf47d82351ceeb79a0606b
ms.sourcegitcommit: 257720deb27f3bbc301175ce2a4afa79001862d3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2021
ms.locfileid: "11440333"
---
# <a name="admin-less-operating-system"></a><span data-ttu-id="33d99-104">无管理操作系统</span><span class="sxs-lookup"><span data-stu-id="33d99-104">Admin-less operating system</span></span>

<span data-ttu-id="33d99-105">HoloLens 2 通过禁用对 Administrators 组的支持并将所有第三方 UWP 应用程序代码限制为仅作为 AppContainer 沙盒内的标准用户执行，从而最大限度地减少了特权提升的覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="33d99-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="33d99-106">除了所有 AppContainer 都可以访问的资源之外，此代码仅授予未提升用户访问受应用程序中明确显示的功能保护的资源的权限。</span><span class="sxs-lookup"><span data-stu-id="33d99-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="33d99-107">这些应用程序功能仍然具有三层分类模型：</span><span class="sxs-lookup"><span data-stu-id="33d99-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="33d99-108">常规</span><span class="sxs-lookup"><span data-stu-id="33d99-108">General</span></span>
  * <span data-ttu-id="33d99-109">Restricted (受限的)</span><span class="sxs-lookup"><span data-stu-id="33d99-109">Restricted</span></span>
  * <span data-ttu-id="33d99-110">Windows</span><span class="sxs-lookup"><span data-stu-id="33d99-110">Windows</span></span>

<span data-ttu-id="33d99-111">Windows 组件还可以通过系统 UWPs 利用 AppContainer 沙盒。</span><span class="sxs-lookup"><span data-stu-id="33d99-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="33d99-112">若要了解有关通用 Windows 平台 (UWP) 的详细信息，请参阅 [UWP 文档](https://docs.microsoft.com/windows/uwp/)。</span><span class="sxs-lookup"><span data-stu-id="33d99-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](https://docs.microsoft.com/windows/uwp/).</span></span> <span data-ttu-id="33d99-113">此外，具有较大权限缩减需求的 Windows 组件（如浏览器内容页或分析程序）使用较低权限的 AppContainer （LPAC） 沙盒，该沙盒能省去所有 AppContainers 可访问的资源集的访问权限。</span><span class="sxs-lookup"><span data-stu-id="33d99-113">Additionally, Windows components with greater privilege reduction needs (like browser content pages or parsers) use the Less Privileged AppContainer (LPAC) sandbox, which cuts off access to the set of resources accessible to all AppContainers.</span></span>

## <a name="device-owner"></a><span data-ttu-id="33d99-114">设备所有者</span><span class="sxs-lookup"><span data-stu-id="33d99-114">Device owner</span></span>

<span data-ttu-id="33d99-115">最后，仅允许“设备所有者”执行特定设备范围的操作，例如将设备加入租户或用户管理。</span><span class="sxs-lookup"><span data-stu-id="33d99-115">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="33d99-116">此组由设备上的用户通过以下步骤之一填充：</span><span class="sxs-lookup"><span data-stu-id="33d99-116">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="33d99-117">设备上的第一个用户始终被指定为所有者。</span><span class="sxs-lookup"><span data-stu-id="33d99-117">The first user on the device is always designated an Owner.</span></span> 
> [!IMPORTANT]
><span data-ttu-id="33d99-118">对于 Azure AD 用户，此规则的例外情况是，如果设备通过 Autopi预览或批量 Azure AD 注册加入 Azure AD，则其使用非真实用户。</span><span class="sxs-lookup"><span data-stu-id="33d99-118">For Azure AD Users, the exception to this rule is that if the device is Azure AD joined via Autopilot or bulk Azure AD enrollment, which uses a non-real user.</span></span> <span data-ttu-id="33d99-119">在这种情况下，第一个登录到设备的 AAD 用户不会自动成为设备所有者，除非该用户在 Azure 门户中分配了"全局管理员"或"设备管理员"角色。</span><span class="sxs-lookup"><span data-stu-id="33d99-119">In this case, the first AAD user to sign into the device may not be made device owner automatically unless that user has the "global administrator" or "device administrator" role assigned in Azure portal.</span></span> <span data-ttu-id="33d99-120">有关详细信息，请参阅以下备注。</span><span class="sxs-lookup"><span data-stu-id="33d99-120">For more information, see the note below.</span></span>  

  * <span data-ttu-id="33d99-121">当用户被另一所有者从"设置用户体验"提升为所有者。</span><span class="sxs-lookup"><span data-stu-id="33d99-121">When a user is promoted to be an Owner from the Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="33d99-122">如果设备所有者不再可用（已离开公司），并且设备是加入 Azure AD 的，则租户管理员可以在 Azure 门户中将设备所有者更改为新用户。</span><span class="sxs-lookup"><span data-stu-id="33d99-122">If the device owner is no longer available (leaves the company) and the device is Azure AD joined, the Tenant Admin can change the device owner to a new user in Azure portal.</span></span> <span data-ttu-id="33d99-123">Azure AD 租户的全局管理员和设备管理员在设备上以所有者形式隐式登录，无需执行上述任一步骤。</span><span class="sxs-lookup"><span data-stu-id="33d99-123">Global Administrators and Device Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span>  

 <span data-ttu-id="33d99-124">IT 管理员可以通过[隐私](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy)策略管理应用可访问的内容。</span><span class="sxs-lookup"><span data-stu-id="33d99-124">IT administrators can manage what apps can access through [Privacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 

> [!NOTE]
> <span data-ttu-id="33d99-125">若要了解有关谁将被设为加入 Azure AD 的设备的设备所有者的详细信息，请参阅[“分配本地管理员”文档](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin)（但请将“本地管理员”视为“设备所有者”，因为 HoloLens 上不存在管理员）。</span><span class="sxs-lookup"><span data-stu-id="33d99-125">To understand more about who is made a device owner on an Azure AD joined device, see [“Assign Local Admin” documentation](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>