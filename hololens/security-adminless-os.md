---
title: 安全无管理操作系统
description: 无管理操作系统和 hololens 安全
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
ms.openlocfilehash: ea35012e63f4c0d8868f9604809c1552c3212e72
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016636"
---
# <span data-ttu-id="39f81-104">无管理操作系统</span><span class="sxs-lookup"><span data-stu-id="39f81-104">Admin-less operating system</span></span>

<span data-ttu-id="39f81-105">HoloLens 2 通过禁用对 Administrators 组的支持并将所有第三方 UWP 应用程序代码限制为仅作为 AppContainer 沙盒内的标准用户执行，从而最大限度地减少了特权提升的覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="39f81-105">HoloLens 2 minimizes the surface area for privilege escalation by disabling support for the Administrators group and limiting all third-party UWP application code to only execute as standard users within the AppContainer sandbox.</span></span> <span data-ttu-id="39f81-106">除了所有 AppContainer 都可以访问的资源之外，此代码仅授予未提升用户访问受应用程序中明确显示的功能保护的资源的权限。</span><span class="sxs-lookup"><span data-stu-id="39f81-106">This code is only granted access to those resources protected by capabilities explicitly manifested in the application for an unelevated user in addition to resources accessible to all AppContainers.</span></span>
<span data-ttu-id="39f81-107">这些应用程序功能仍然具有三层分类模型：</span><span class="sxs-lookup"><span data-stu-id="39f81-107">These application capabilities continue to have the three-tiered classification model:</span></span>
  * <span data-ttu-id="39f81-108">常规</span><span class="sxs-lookup"><span data-stu-id="39f81-108">General</span></span>
  * <span data-ttu-id="39f81-109">Restricted (受限的)</span><span class="sxs-lookup"><span data-stu-id="39f81-109">Restricted</span></span>
  * <span data-ttu-id="39f81-110">Windows</span><span class="sxs-lookup"><span data-stu-id="39f81-110">Windows</span></span>

<span data-ttu-id="39f81-111">Windows 组件还可以通过系统 UWPs 利用 AppContainer 沙盒。</span><span class="sxs-lookup"><span data-stu-id="39f81-111">Windows components can also leverage the AppContainer sandbox through System UWPs.</span></span> <span data-ttu-id="39f81-112">若要了解有关通用 Windows 平台 (UWP) 的详细信息，请参阅 [UWP 文档](https://docs.microsoft.com/windows/uwp/)。</span><span class="sxs-lookup"><span data-stu-id="39f81-112">To learn more about Universal Windows Platform (UWP), see [UWP documentation](https://docs.microsoft.com/windows/uwp/).</span></span> <span data-ttu-id="39f81-113">此外，具有更大特权减少需求的 Windows 组件（例如浏览器内容页、分析程序）使用特权较少的 AppContainer (LPAC) 沙盒，该沙盒会切断对所有 AppContainer 可访问的资源集的访问。</span><span class="sxs-lookup"><span data-stu-id="39f81-113">Additionally, Windows components with greater privilege reduction needs (e.g. browser content pages, parsers) use the Less Privileged AppContainer (LPAC) sandbox which cuts off access to the set of resources accessible to all AppContainers.</span></span>

<span data-ttu-id="39f81-114">最后，仅允许“设备所有者”执行特定设备范围的操作，例如将设备加入租户或用户管理。</span><span class="sxs-lookup"><span data-stu-id="39f81-114">Finally, the execution of specific device-wide operations, such as joining the device to a tenant or user management, is only permitted for “device owners”.</span></span> <span data-ttu-id="39f81-115">此组由设备上的用户通过以下步骤之一填充：</span><span class="sxs-lookup"><span data-stu-id="39f81-115">This group is populated by users on the device through one of the following steps:</span></span>
  * <span data-ttu-id="39f81-116">设备上的第一个用户始终被指定为所有者。</span><span class="sxs-lookup"><span data-stu-id="39f81-116">The first user on the device is always designated an Owner.</span></span> 
    * <span data-ttu-id="39f81-117">此规则的例外情况是，如果设备已加入 AAD，则执行加入的用户将成为设备所有者。</span><span class="sxs-lookup"><span data-stu-id="39f81-117">The exception to this rule is that if the device is AAD joined, the user that performed the join is made device owner.</span></span> <span data-ttu-id="39f81-118">例如，如果设备是通过 Autopilot 加入 AAD 的，则此规则适用，在这种情况下，登录设备的第一个用户未加入 AAD，因此不会成为设备所有者。</span><span class="sxs-lookup"><span data-stu-id="39f81-118">This is applicable, for example, if a device is AAD joined via Autopilot in which case the first user to sign into the device did not AAD join the device and therefore will not be made a device owner.</span></span> <span data-ttu-id="39f81-119">若要了解有关谁将被设为加入 AAD 的设备的设备所有者的详细信息，请参阅[“分配本地管理员”文档](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin)（但请将“本地管理员”视为“设备所有者”，因为 HoloLens 上不存在管理员）。</span><span class="sxs-lookup"><span data-stu-id="39f81-119">To understand more about who is made a device owner on an AAD joined device, see [“Assign Local Admin” documentation](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin) (but read ‘local admin’ as ‘device owner’ since admin does not exist on HoloLens).</span></span>
  * <span data-ttu-id="39f81-120">当设备上的另一个所有者从“设置 UX”将用户提升为所有者时。</span><span class="sxs-lookup"><span data-stu-id="39f81-120">When a user is promoted to be an Owner from Settings UX by another Owner on the device.</span></span>
  * <span data-ttu-id="39f81-121">如果设备所有者不再可用（例如离开公司）且设备已加入 AAD，则租户管理员可以在 Azure 门户中将设备所有者更改为新用户。</span><span class="sxs-lookup"><span data-stu-id="39f81-121">If the device owner is no longer available (e.g. leaves the company) and the device is AAD joined, the Tenant Admin can change the device owner to a new user in Azure Portal.</span></span>
<span data-ttu-id="39f81-122">Azure AD 租户的全局管理员在设备上以所有者身份隐式登录，而无需执行上述任一步骤。</span><span class="sxs-lookup"><span data-stu-id="39f81-122">Global Administrators of an Azure AD tenant are implicitly signed in as Owners on the device without requiring either of the previous steps.</span></span> 

<span data-ttu-id="39f81-123">IT 管理员可以通过[隐私](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy)策略管理应用可访问的内容。</span><span class="sxs-lookup"><span data-stu-id="39f81-123">IT administrators can manage what apps can access through [Privacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-privacy) policies.</span></span> 
