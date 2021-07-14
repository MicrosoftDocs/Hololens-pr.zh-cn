---
title: HoloLens 2 Windows Autopilot 注册支持
description: 了解如何在 HoloLens 2 设备上获取对 Autopilot 的注册支持。
author: joyjaz
ms.author: v-jjaswinski
ms.date: 5/20/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: ylempidakis
ms.openlocfilehash: cdd2ab68905d5cc82b1c5ccc50640112e857f2f4
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110398851"
---
# <a name="hololens-2-registration-support-for-autopilot"></a><span data-ttu-id="b386d-104">HoloLens 2 Autopilot 注册支持</span><span class="sxs-lookup"><span data-stu-id="b386d-104">HoloLens 2 Registration Support for Autopilot</span></span>

<span data-ttu-id="b386d-105">客户和 Microsoft 云解决方案提供商 (CSP) 现在可以通过直接向 Microsoft 支持部门提交请求来注册 HoloLens 2 设备。</span><span class="sxs-lookup"><span data-stu-id="b386d-105">Customers and Microsoft Cloud Solution Providers (CSPs) can now register HoloLens 2 devices by directly submitting requests to Microsoft Support.</span></span> <span data-ttu-id="b386d-106">本页概述了以下受支持的 Autopilot 注册情形的要求：</span><span class="sxs-lookup"><span data-stu-id="b386d-106">This page outlines the requirements for the following supported Autopilot registration scenarios:</span></span>

- <span data-ttu-id="b386d-107">HoloLens 2 设备 Autopilot 注册。</span><span class="sxs-lookup"><span data-stu-id="b386d-107">**HoloLens 2 Device Autopilot Registration**.</span></span> <span data-ttu-id="b386d-108">提交向 Windows Autopilot 注册 HoloLens 2 设备的请求。</span><span class="sxs-lookup"><span data-stu-id="b386d-108">Submits request to register HoloLens 2 devices into Windows Autopilot.</span></span>
- <span data-ttu-id="b386d-109">HoloLens 2 设备硬件哈希请求。</span><span class="sxs-lookup"><span data-stu-id="b386d-109">**HoloLens 2 Device Hardware Hash Request**.</span></span> <span data-ttu-id="b386d-110">向 Microsoft 支持部门提交请求，以便为你提供客户或 CSP 可用于通过 Microsoft Intune 或 Microsoft 合作伙伴中心自行注册设备的硬件哈希。</span><span class="sxs-lookup"><span data-stu-id="b386d-110">Submits request to Microsoft Support to provide you with hardware hashes that customers or CSPs can use to self-register devices via Microsoft Intune or the Microsoft Partner Center.</span></span>
- <span data-ttu-id="b386d-111">HoloLens 2 设备 Autopilot 取消注册。</span><span class="sxs-lookup"><span data-stu-id="b386d-111">**HoloLens 2 Device Autopilot Deregistration**.</span></span> <span data-ttu-id="b386d-112">提交从 Windows Autopilot 删除设备的请求，通常在设备生命周期结束情形中使用。</span><span class="sxs-lookup"><span data-stu-id="b386d-112">Submits request to delete devices from Windows Autopilot, typically used in device end of life scenarios.</span></span>

<span data-ttu-id="b386d-113">下表详细说明了向 Microsoft 支持部门提交注册请求之前需要收集的信息。</span><span class="sxs-lookup"><span data-stu-id="b386d-113">The following table details the information you will need to collect *prior* to submitting registration requests to Microsoft Support.</span></span>

| <span data-ttu-id="b386d-114">所需信息</span><span class="sxs-lookup"><span data-stu-id="b386d-114">Required Information</span></span> | <span data-ttu-id="b386d-115">说明</span><span class="sxs-lookup"><span data-stu-id="b386d-115">Description</span></span> | <span data-ttu-id="b386d-116">Autopilot 注册</span><span class="sxs-lookup"><span data-stu-id="b386d-116">Autopilot Registration</span></span>  | <span data-ttu-id="b386d-117">硬件哈希请求</span><span class="sxs-lookup"><span data-stu-id="b386d-117">Hardware Hash Request</span></span> | <span data-ttu-id="b386d-118">Autopilot 取消注册</span><span class="sxs-lookup"><span data-stu-id="b386d-118">Autopilot Deregistration</span></span> |
------------|-------------------------------|--------------------------------------------------|------------------------------|--------------------------------|
|  <span data-ttu-id="b386d-119">Azure Active Directory 租户 ID</span><span class="sxs-lookup"><span data-stu-id="b386d-119">Azure Active Directory Tenant ID</span></span>    |    <span data-ttu-id="b386d-120">Azure Active Directory 租户 ID 是一个全局唯一标识符 (GUID)，与组织名称或域不同。</span><span class="sxs-lookup"><span data-stu-id="b386d-120">Your Azure Active Directory tenant ID is a globally unique identifier (GUID) that is different than your organization name or domain.</span></span>    <span data-ttu-id="b386d-121">若要查找租户 ID，请登录到 [Azure 门户](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。</span><span class="sxs-lookup"><span data-stu-id="b386d-121">To find your Tenant ID sign into the [Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>    |     <span data-ttu-id="b386d-122">✔️</span><span class="sxs-lookup"><span data-stu-id="b386d-122">✔️</span></span>                         |                              |                         <span data-ttu-id="b386d-123">✔️</span><span class="sxs-lookup"><span data-stu-id="b386d-123">✔️</span></span>                        |
|  <span data-ttu-id="b386d-124">Azure Active Directory 域名</span><span class="sxs-lookup"><span data-stu-id="b386d-124">Azure Active Directory Domain Name</span></span>    |   <span data-ttu-id="b386d-125">顶级域名；例如，contoso.com。</span><span class="sxs-lookup"><span data-stu-id="b386d-125">Your top-level domain name; for example, contoso.com.</span></span>    |     <span data-ttu-id="b386d-126">✔️</span><span class="sxs-lookup"><span data-stu-id="b386d-126">✔️</span></span>                         |                              |                         <span data-ttu-id="b386d-127">✔️</span><span class="sxs-lookup"><span data-stu-id="b386d-127">✔️</span></span>                        |
|  <span data-ttu-id="b386d-128">所有权证明</span><span class="sxs-lookup"><span data-stu-id="b386d-128">Proof of Ownership</span></span>    |   <span data-ttu-id="b386d-129">通过上传原始销售单或 PDF 格式的发票来验证所有权证明。</span><span class="sxs-lookup"><span data-stu-id="b386d-129">Verify proof of ownership by uploading the original bill of sale or invoice in PDF format.</span></span> <span data-ttu-id="b386d-130">不接受屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="b386d-130">Screenshots are not accepted.</span></span> <span data-ttu-id="b386d-131">销售单或发票必须包括以下内容：设备序列号。</span><span class="sxs-lookup"><span data-stu-id="b386d-131">The bill of sale or invoice must include the following: Device serial numbers.</span></span> <span data-ttu-id="b386d-132">公司名称。</span><span class="sxs-lookup"><span data-stu-id="b386d-132">Company name.</span></span>     |     <span data-ttu-id="b386d-133">✔️</span><span class="sxs-lookup"><span data-stu-id="b386d-133">✔️</span></span>                         |              <span data-ttu-id="b386d-134">✔️</span><span class="sxs-lookup"><span data-stu-id="b386d-134">✔️</span></span>                |                         <span data-ttu-id="b386d-135">✔️</span><span class="sxs-lookup"><span data-stu-id="b386d-135">✔️</span></span>                        |
|  <span data-ttu-id="b386d-136">设备序列号</span><span class="sxs-lookup"><span data-stu-id="b386d-136">Device serial numbers</span></span>    |   <span data-ttu-id="b386d-137">上传 CSV 格式的 Excel 文件，其中每个设备序列号都位于一个新行。</span><span class="sxs-lookup"><span data-stu-id="b386d-137">Upload Excel file in CSV format with each device serial number in a new line.</span></span>     |     <span data-ttu-id="b386d-138">✔️</span><span class="sxs-lookup"><span data-stu-id="b386d-138">✔️</span></span>                         |              <span data-ttu-id="b386d-139">✔️</span><span class="sxs-lookup"><span data-stu-id="b386d-139">✔️</span></span>                |                         <span data-ttu-id="b386d-140">✔️</span><span class="sxs-lookup"><span data-stu-id="b386d-140">✔️</span></span>                        |

## <a name="submit-support-requests"></a><span data-ttu-id="b386d-141">提交支持请求</span><span class="sxs-lookup"><span data-stu-id="b386d-141">Submit support requests</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b386d-142">提交 HoloLens 2 Autopilot 注册支持</span><span class="sxs-lookup"><span data-stu-id="b386d-142">Submit Autopilot Registration Support for HoloLens 2</span></span>](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
