---
title: 证书管理器
description: 了解如何在 HoloLens 2 混合现实设备上手动安装、管理和删除证书。
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
ms.openlocfilehash: 9d221321adcb8062206695e3e610d35dee14523e
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308341"
---
# <a name="certificate-manager"></a><span data-ttu-id="d4356-103">证书管理器</span><span class="sxs-lookup"><span data-stu-id="d4356-103">Certificate Manager</span></span>

- <span data-ttu-id="d4356-104">通过新的证书管理器改进了设备安全性和符合性的审核、诊断和验证工具。</span><span class="sxs-lookup"><span data-stu-id="d4356-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="d4356-105">此功能使你能够在商业环境中大规模部署、排查和验证你的证书。</span><span class="sxs-lookup"><span data-stu-id="d4356-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="d4356-106">在 Windows 全息版20H2 中，我们将在 HoloLens 2 设置应用中添加证书管理器。</span><span class="sxs-lookup"><span data-stu-id="d4356-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="d4356-107">请参阅 " **设置" > 更新 & Security > 证书**。</span><span class="sxs-lookup"><span data-stu-id="d4356-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="d4356-108">此功能提供了一种简单易用的方法来查看、安装和删除设备上的证书。</span><span class="sxs-lookup"><span data-stu-id="d4356-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="d4356-109">使用新的证书管理器，管理员和用户现在已经改进了审核、诊断和验证工具，以确保设备保持安全性和合规性。</span><span class="sxs-lookup"><span data-stu-id="d4356-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="d4356-110">**审核：** 能够验证是否已正确部署证书，或者确认是否已正确删除证书。</span><span class="sxs-lookup"><span data-stu-id="d4356-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="d4356-111">**诊断：** 出现问题时，验证设备上存在的适当证书是否节省时间并帮助进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="d4356-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="d4356-112">**验证：** 验证证书是否服务于预期目的并能正常工作，可以节省大量时间，特别是在商业环境中，在较大规模部署证书之前。</span><span class="sxs-lookup"><span data-stu-id="d4356-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="d4356-113">若要快速查找列表中的特定证书，可以按名称、存储或到期日期排序。</span><span class="sxs-lookup"><span data-stu-id="d4356-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="d4356-114">用户还可以直接搜索证书。</span><span class="sxs-lookup"><span data-stu-id="d4356-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="d4356-115">若要查看单独的证书属性，请选择该证书，然后单击 " **信息**"。</span><span class="sxs-lookup"><span data-stu-id="d4356-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="d4356-116">证书安装当前支持 .cer 和 .crt 文件。</span><span class="sxs-lookup"><span data-stu-id="d4356-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="d4356-117">设备所有者可以在本地计算机和当前用户中安装证书; 所有其他用户只能安装到当前用户。</span><span class="sxs-lookup"><span data-stu-id="d4356-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="d4356-118">用户只能删除直接从 "设置" UI 安装的证书。</span><span class="sxs-lookup"><span data-stu-id="d4356-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="d4356-119">如果通过其他方式安装了证书，则该证书还必须通过相同的机制删除。</span><span class="sxs-lookup"><span data-stu-id="d4356-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="d4356-120">若要安装证书：</span><span class="sxs-lookup"><span data-stu-id="d4356-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="d4356-121">将 HoloLens 2 连接到 PC。</span><span class="sxs-lookup"><span data-stu-id="d4356-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="d4356-122">将要安装的证书文件放在 HoloLens 2 上的某个位置。</span><span class="sxs-lookup"><span data-stu-id="d4356-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="d4356-123">导航到 " **设置" 应用 > 更新 & 安全 > 证书**，并选择 "安装证书"。</span><span class="sxs-lookup"><span data-stu-id="d4356-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="d4356-124">单击 " **导入文件** "，并导航到保存证书的位置。</span><span class="sxs-lookup"><span data-stu-id="d4356-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="d4356-125">选择 " **存储位置**"。</span><span class="sxs-lookup"><span data-stu-id="d4356-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="d4356-126">选择 " **证书存储**"。</span><span class="sxs-lookup"><span data-stu-id="d4356-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="d4356-127">单击“安装” 。</span><span class="sxs-lookup"><span data-stu-id="d4356-127">Click **Install**.</span></span>

<span data-ttu-id="d4356-128">现在应在设备上安装证书。</span><span class="sxs-lookup"><span data-stu-id="d4356-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="d4356-129">删除证书的步骤：</span><span class="sxs-lookup"><span data-stu-id="d4356-129">To remove a certificate:</span></span> 
1. <span data-ttu-id="d4356-130">导航到 " **设置" 应用 > 更新和安全 > 证书**"。</span><span class="sxs-lookup"><span data-stu-id="d4356-130">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="d4356-131">在搜索框中按名称搜索证书。</span><span class="sxs-lookup"><span data-stu-id="d4356-131">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="d4356-132">选择证书。</span><span class="sxs-lookup"><span data-stu-id="d4356-132">Select the certificate.</span></span>
1. <span data-ttu-id="d4356-133">单击 "**删除**"</span><span class="sxs-lookup"><span data-stu-id="d4356-133">Click **Remove**</span></span>
1. <span data-ttu-id="d4356-134">出现确认提示时，选择“是”。</span><span class="sxs-lookup"><span data-stu-id="d4356-134">Select **Yes** when prompted for confirmation.</span></span>


![Ceritifcates 下的 "设置" 应用中的证书查看器](images/certificate-viewer-device.jpg)

![显示如何使用证书 UI 在 "设置" 中安装证书的图片。](images/certificate-device-install.jpg)
