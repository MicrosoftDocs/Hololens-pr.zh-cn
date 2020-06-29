---
title: 混合现实部署许可证
description: ''
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
audience: HoloLens
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 0da2a2337b3b1f361ffbb698607f304efbf6d193
ms.sourcegitcommit: f3cda6c6b3bfb7ba4be5f4da66d8ed5b03ca807d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2020
ms.locfileid: "10830136"
---
# <span data-ttu-id="39e09-102">确定所需的许可证</span><span class="sxs-lookup"><span data-stu-id="39e09-102">Determine what licenses you need</span></span>

## <span data-ttu-id="39e09-103">移动设备管理 (MDM) 许可证指南</span><span class="sxs-lookup"><span data-stu-id="39e09-103">Mobile Device Management (MDM) Licenses Guidance</span></span>

<span data-ttu-id="39e09-104">如果计划管理 HoloLens 设备，则需要 Azure AD 和 MDM。</span><span class="sxs-lookup"><span data-stu-id="39e09-104">If you plan on managing your HoloLens devices, you will need Azure AD and an MDM.</span></span> <span data-ttu-id="39e09-105">Active Director (AD) 不能用于管理 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="39e09-105">Active Director (AD) cannot be used to manage HoloLens devices.</span></span>
<span data-ttu-id="39e09-106">如果计划使用 Intune 以外的 MDM，则需要 [Azure Active Directory 许可证](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)。</span><span class="sxs-lookup"><span data-stu-id="39e09-106">If you plan on using an MDM other than Intune, an [Azure Active Directory Licenses](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) is required.</span></span>
<span data-ttu-id="39e09-107">如果打算将 Intune 用作 MDM，请单击[此处](https://docs.microsoft.com/intune/fundamentals/licenses)，其中列出了包含 Intune 许可证的套件。</span><span class="sxs-lookup"><span data-stu-id="39e09-107">If you plan on using Intune as your MDM,  [here](https://docs.microsoft.com/intune/fundamentals/licenses) are a list of suites that includes Intune licenses.</span></span> **<span data-ttu-id="39e09-108">请注意，其中大部分套件都包含 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="39e09-108">Please note that Azure AD is included in the majority of these suites.</span></span>**

## <span data-ttu-id="39e09-109">确定应用场景和产品所需的许可证</span><span class="sxs-lookup"><span data-stu-id="39e09-109">Identify the licenses needed for your scenario and products</span></span>

### <span data-ttu-id="39e09-110">HoloLens 许可证要求</span><span class="sxs-lookup"><span data-stu-id="39e09-110">HoloLens Licenses Requirements</span></span>

<span data-ttu-id="39e09-111">可能需要将 HoloLens 第 1 代设备升级到 Windows Holographic for Business。</span><span class="sxs-lookup"><span data-stu-id="39e09-111">You may need to upgrade your HoloLens 1st Gen Device to Windows Holographic for Business.</span></span> <span data-ttu-id="39e09-112">（请参阅 [HoloLens 商业功能](holoLens-commercial-features.md#feature-comparison-between-editions)以确定是否需要升级）。</span><span class="sxs-lookup"><span data-stu-id="39e09-112">(See [HoloLens commercial features](holoLens-commercial-features.md#feature-comparison-between-editions) to determine if you need to upgrade).</span></span>

 <span data-ttu-id="39e09-113">如果需要升级，你将需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="39e09-113">If so, you will need to do the following:</span></span>

- <span data-ttu-id="39e09-114">请求 HoloLens 企业许可证 XML 文件</span><span class="sxs-lookup"><span data-stu-id="39e09-114">Acquire a HoloLens Enterprise license XML file</span></span>
- <span data-ttu-id="39e09-115">将该 XML 文件应用到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="39e09-115">Apply the XML file to the HoloLens.</span></span> <span data-ttu-id="39e09-116">可通过[预配包](hololens-provisioning.md)或[移动设备管理器](https://docs.microsoft.com/intune/configuration/holographic-upgrade)执行此操作</span><span class="sxs-lookup"><span data-stu-id="39e09-116">You can do this through a [Provisioning package](hololens-provisioning.md) or through your [Mobile Device Manager](https://docs.microsoft.com/intune/configuration/holographic-upgrade)</span></span>

### <span data-ttu-id="39e09-117">Remote Assist 许可证要求</span><span class="sxs-lookup"><span data-stu-id="39e09-117">Remote Assist License Requirements</span></span>

<span data-ttu-id="39e09-118">确保拥有所需的许可和设备。</span><span class="sxs-lookup"><span data-stu-id="39e09-118">Make sure you have the required licensing and device.</span></span> <span data-ttu-id="39e09-119">可在[此处](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements)找到更新的许可和产品要求。</span><span class="sxs-lookup"><span data-stu-id="39e09-119">Updated licensing and product requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements).</span></span>

1. [<span data-ttu-id="39e09-120">Remote Assist 许可证</span><span class="sxs-lookup"><span data-stu-id="39e09-120">Remote Assist License</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-and-deploy-remote-assist)
1. [<span data-ttu-id="39e09-121">Teams 免费增值版/Teams</span><span class="sxs-lookup"><span data-stu-id="39e09-121">Teams Freemium/Teams</span></span>](https://products.office.com/microsoft-teams/free)
1. [<span data-ttu-id="39e09-122">Azure Active Directory (Azure AD) 许可证</span><span class="sxs-lookup"><span data-stu-id="39e09-122">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)

<span data-ttu-id="39e09-123">如果打算实现**[此跨租户方案](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**，可能需要信息屏障许可证。</span><span class="sxs-lookup"><span data-stu-id="39e09-123">If you plan on implementing **[this cross-tenant scenario](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-overview#scenario-2-leasing-services-to-other-tenants)**, you may need an Information Barriers license.</span></span> <span data-ttu-id="39e09-124">请参阅[这篇文章](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary)，以确定是否需要信息屏障许可证。</span><span class="sxs-lookup"><span data-stu-id="39e09-124">Please see [this article](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/cross-tenant-licensing-implementation#step-1-determine-if-information-barriers-are-necessary) to determine if an Information Barrier License is required.</span></span>

### <span data-ttu-id="39e09-125">Guides 许可证要求</span><span class="sxs-lookup"><span data-stu-id="39e09-125">Guides License Requirements</span></span>

<span data-ttu-id="39e09-126">可在[此处](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements)找到更新的许可和设备要求。</span><span class="sxs-lookup"><span data-stu-id="39e09-126">Updated licensing and device requirements can be found [here](https://docs.microsoft.com/dynamics365/mixed-reality/guides/requirements).</span></span>

1. [<span data-ttu-id="39e09-127">Azure Active Directory (Azure AD) 许可证</span><span class="sxs-lookup"><span data-stu-id="39e09-127">Azure Active Directory (Azure AD) License</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. [<span data-ttu-id="39e09-128">Power BI</span><span class="sxs-lookup"><span data-stu-id="39e09-128">Power BI</span></span>](https://powerbi.microsoft.com/desktop/)
1. [<span data-ttu-id="39e09-129">指南</span><span class="sxs-lookup"><span data-stu-id="39e09-129">Guides</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup)
