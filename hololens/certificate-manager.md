---
title: 证书管理器
description: 了解如何在 HoloLens 2 上手动管理证书。
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 04d7e8cb78357b5398c58e0a0c55e6e530fa363a
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163214"
---
# <span data-ttu-id="49a61-103">证书管理器</span><span class="sxs-lookup"><span data-stu-id="49a61-103">Certificate Manager</span></span>

- <span data-ttu-id="49a61-104">通过新的证书管理器改进了针对设备安全性和合规性的审核、诊断和验证工具。</span><span class="sxs-lookup"><span data-stu-id="49a61-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="49a61-105">利用此功能，你可以在商业环境中按比例部署、排除和验证你的证书。</span><span class="sxs-lookup"><span data-stu-id="49a61-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="49a61-106">在 Windows 全息版20H2 中，我们将在 HoloLens 2 设置应用中添加证书管理器。</span><span class="sxs-lookup"><span data-stu-id="49a61-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="49a61-107">转到 " **设置" > 更新 & 安全 > 证书**。</span><span class="sxs-lookup"><span data-stu-id="49a61-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="49a61-108">此功能为查看、安装和删除设备上的证书提供了一种简单且易于用户理解的方法。</span><span class="sxs-lookup"><span data-stu-id="49a61-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="49a61-109">通过新的证书管理器，管理员和用户现已改进了审核、诊断和验证工具，以确保设备保持安全和合规。</span><span class="sxs-lookup"><span data-stu-id="49a61-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="49a61-110">**审核：** 验证是否已正确部署证书或确认是否已正确删除证书的功能。</span><span class="sxs-lookup"><span data-stu-id="49a61-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="49a61-111">**诊断：** 出现问题时，验证设备上是否存在相应的证书可节省时间并帮助进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="49a61-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="49a61-112">**验证：** 验证证书是否服务于预期用途且正常运行，可以节省大量时间，尤其是在商业环境中，在以较大比例部署证书之前。</span><span class="sxs-lookup"><span data-stu-id="49a61-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="49a61-113">若要快速查找列表中的特定证书，有一些选项可按名称、存储或过期日期进行排序。</span><span class="sxs-lookup"><span data-stu-id="49a61-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="49a61-114">用户也可以直接搜索证书。</span><span class="sxs-lookup"><span data-stu-id="49a61-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="49a61-115">若要查看单个证书属性，请选择证书，然后单击 " **信息**"。</span><span class="sxs-lookup"><span data-stu-id="49a61-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="49a61-116">证书安装当前支持 .cer 和 .crt 文件。</span><span class="sxs-lookup"><span data-stu-id="49a61-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="49a61-117">设备所有者可以在本地计算机和当前用户中安装证书; 所有其他用户都只能安装到当前用户。</span><span class="sxs-lookup"><span data-stu-id="49a61-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="49a61-118">用户只能从 "设置" UI 中删除直接安装的证书。</span><span class="sxs-lookup"><span data-stu-id="49a61-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="49a61-119">如果证书已通过其他方法安装，则它还必须由相同的机制删除。</span><span class="sxs-lookup"><span data-stu-id="49a61-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <span data-ttu-id="49a61-120">要安装证书，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="49a61-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="49a61-121">将 HoloLens 2 连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="49a61-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="49a61-122">将要安装的证书文件放在 HoloLens 2 上的某个位置。</span><span class="sxs-lookup"><span data-stu-id="49a61-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="49a61-123">导航到 " **设置" 应用 > 更新 & 安全 > 证书**，然后选择 "安装证书"。</span><span class="sxs-lookup"><span data-stu-id="49a61-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="49a61-124">单击 " **导入文件** "，然后导航到保存证书的位置。</span><span class="sxs-lookup"><span data-stu-id="49a61-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="49a61-125">选择 " **存储位置**"。</span><span class="sxs-lookup"><span data-stu-id="49a61-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="49a61-126">选择 " **证书存储**"。</span><span class="sxs-lookup"><span data-stu-id="49a61-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="49a61-127">单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="49a61-127">Click **Install**.</span></span>

<span data-ttu-id="49a61-128">证书现在应安装在设备上。</span><span class="sxs-lookup"><span data-stu-id="49a61-128">The certificate should now be installed on the device.</span></span>

## <span data-ttu-id="49a61-129">要删除证书，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="49a61-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="49a61-130">导航到 " **设置" 应用 > 更新和安全 > 证书**。</span><span class="sxs-lookup"><span data-stu-id="49a61-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="49a61-131">在搜索框中按名称搜索证书。</span><span class="sxs-lookup"><span data-stu-id="49a61-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="49a61-132">选择证书。</span><span class="sxs-lookup"><span data-stu-id="49a61-132">Select the certificate.</span></span>
1. <span data-ttu-id="49a61-133">单击 "**删除**"</span><span class="sxs-lookup"><span data-stu-id="49a61-133">Click **Remove**</span></span>
1. <span data-ttu-id="49a61-134">提示确认时，请选择 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="49a61-134">Select **Yes** when prompted for confirmation.</span></span>


![Ceritifcates 下的 "设置" 应用中的证书查看器](images/certificate-viewer-device.jpg)

![显示如何使用证书 UI 在 "设置" 中安装证书的图片。](images/certificate-device-install.jpg)
