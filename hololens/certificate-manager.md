---
title: 证书管理器
description: 了解如何在混合现实设备上手动安装、HoloLens 2和删除证书。
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
ms.openlocfilehash: f9dcf98cbd200ac54cd786648fdfe286bff1aa00
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397448"
---
# <a name="certificate-manager"></a><span data-ttu-id="6c81e-103">证书管理器</span><span class="sxs-lookup"><span data-stu-id="6c81e-103">Certificate Manager</span></span>

- <span data-ttu-id="6c81e-104">通过新的证书管理器改进了设备安全性和符合性的审核、诊断和验证工具。</span><span class="sxs-lookup"><span data-stu-id="6c81e-104">Improved auditing, diagnosis, and validation tooling for device security and compliance through the new Certificate Manager.</span></span> <span data-ttu-id="6c81e-105">此功能可让你在商业环境中大规模部署、排查和验证证书。</span><span class="sxs-lookup"><span data-stu-id="6c81e-105">This capability will enable you to deploy, troubleshoot, and validate your certificates at scale in commercial environments.</span></span>

<span data-ttu-id="6c81e-106">在 Windows Holographic 版本 20H2 中，我们将在"设置"应用中添加HoloLens 2管理器。</span><span class="sxs-lookup"><span data-stu-id="6c81e-106">In Windows Holographic, version 20H2, we are adding a Certificate Manager in the HoloLens 2 Settings app.</span></span> <span data-ttu-id="6c81e-107">转到"**设置>更新&安全>证书"。**</span><span class="sxs-lookup"><span data-stu-id="6c81e-107">Go to **Settings > Update & Security > Certificates**.</span></span> <span data-ttu-id="6c81e-108">此功能提供了一种简单且用户友好的方式来查看、安装和删除设备上证书。</span><span class="sxs-lookup"><span data-stu-id="6c81e-108">This feature provides a simple and user-friendly way to view, install and remove certificates on your device.</span></span> <span data-ttu-id="6c81e-109">借助新的证书管理器，管理员和用户现在改进了审核、诊断和验证工具，以确保设备保持安全且合规。</span><span class="sxs-lookup"><span data-stu-id="6c81e-109">With the new Certificate Manager, admins and users now have improved auditing, diagnosis and validation tooling to ensure that devices remain secure and compliant.</span></span> 

-   <span data-ttu-id="6c81e-110">**审核：** 能够验证证书是否正确部署，或确认证书已正确删除。</span><span class="sxs-lookup"><span data-stu-id="6c81e-110">**Auditing:** Ability to validate that a certificate is deployed correctly or to confirm that it was removed appropriately.</span></span> 
-   <span data-ttu-id="6c81e-111">**诊断：** 出现问题时，验证设备上是否存在相应的证书可节省时间，并有助于进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="6c81e-111">**Diagnosis:** When issues arise, validating that the appropriate certificates exist on the device saves time and helps with troubleshooting.</span></span> 
-   <span data-ttu-id="6c81e-112">**验证：** 验证证书是否符合预期目的且正常运行，可以节省大量时间，尤其是在商业环境中，然后再大规模部署证书。</span><span class="sxs-lookup"><span data-stu-id="6c81e-112">**Validation:** Verifying that a certificate serves the intended purpose and is functional, can save significant time, particularly in commercial environments before deploying certificates at larger scale.</span></span>

<span data-ttu-id="6c81e-113">若要在列表中快速查找特定证书，有一些选项可以按名称、存储或到期日期进行排序。</span><span class="sxs-lookup"><span data-stu-id="6c81e-113">To find a specific certificate in the list quickly, there are options to sort by name, store or expiration date.</span></span> <span data-ttu-id="6c81e-114">用户还可以直接搜索证书。</span><span class="sxs-lookup"><span data-stu-id="6c81e-114">Users may also directly search for a certificate.</span></span> <span data-ttu-id="6c81e-115">若要查看单个证书属性，请选择证书，然后单击"信息 **"。**</span><span class="sxs-lookup"><span data-stu-id="6c81e-115">To view individual certificate properties, select the certificate and click on **Info**.</span></span> 

<span data-ttu-id="6c81e-116">证书安装当前支持 .cer 和 .crt 文件。</span><span class="sxs-lookup"><span data-stu-id="6c81e-116">Certificate installation currently supports .cer and .crt files.</span></span> <span data-ttu-id="6c81e-117">设备所有者可以在本地计算机和当前用户中安装证书; 所有其他用户只能安装到当前用户中。</span><span class="sxs-lookup"><span data-stu-id="6c81e-117">Device Owners can install certificates in Local Machine and Current User;  all other users can only install into Current User.</span></span> <span data-ttu-id="6c81e-118">用户只能从"设置"UI 中删除直接安装的证书。</span><span class="sxs-lookup"><span data-stu-id="6c81e-118">Users can only remove certificates installed directly from the Settings UI.</span></span> <span data-ttu-id="6c81e-119">如果证书是通过其他方式安装的，则还必须使用相同的机制将其删除。</span><span class="sxs-lookup"><span data-stu-id="6c81e-119">If a certificate has been installed through other means, it must also be removed by the same mechanism.</span></span>

## <a name="to-install-a-certificate"></a><span data-ttu-id="6c81e-120">安装证书：</span><span class="sxs-lookup"><span data-stu-id="6c81e-120">To install a certificate:</span></span> 

1.  <span data-ttu-id="6c81e-121">将HoloLens 2连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="6c81e-121">Connect your HoloLens 2 to a PC.</span></span>
1.  <span data-ttu-id="6c81e-122">将要安装的证书文件放在 HoloLens 2 上的某个位置。</span><span class="sxs-lookup"><span data-stu-id="6c81e-122">Place the certificate file you want to install in a location on your HoloLens 2.</span></span>
1.  <span data-ttu-id="6c81e-123">导航到 " **设置" 应用 > 更新 & 安全 > 证书**，并选择 "安装证书"。</span><span class="sxs-lookup"><span data-stu-id="6c81e-123">Navigate to **Settings App > Update & Security > Certificates**, and select Install a certificate.</span></span>
1.  <span data-ttu-id="6c81e-124">单击 " **导入文件** "，并导航到保存证书的位置。</span><span class="sxs-lookup"><span data-stu-id="6c81e-124">Click **Import File** and navigate to the location you saved the certificate.</span></span>
1.  <span data-ttu-id="6c81e-125">选择 " **存储位置**"。</span><span class="sxs-lookup"><span data-stu-id="6c81e-125">Select **Store Location**.</span></span>
1.  <span data-ttu-id="6c81e-126">选择 " **证书存储**"。</span><span class="sxs-lookup"><span data-stu-id="6c81e-126">Select **Certificate Store**.</span></span>
1.  <span data-ttu-id="6c81e-127">单击“安装”  。</span><span class="sxs-lookup"><span data-stu-id="6c81e-127">Click **Install**.</span></span>

<span data-ttu-id="6c81e-128">现在应在设备上安装证书。</span><span class="sxs-lookup"><span data-stu-id="6c81e-128">The certificate should now be installed on the device.</span></span>

## <a name="to-remove-a-certificate"></a><span data-ttu-id="6c81e-129">删除证书的步骤：</span><span class="sxs-lookup"><span data-stu-id="6c81e-129">To remove a certificate:</span></span> 
>[!WARNING]
> <span data-ttu-id="6c81e-130">尽管可以在证书管理器中查看 MDM 部署的证书，但不能在证书管理器中将其卸载。</span><span class="sxs-lookup"><span data-stu-id="6c81e-130">Although you can view MDM-deployed certificates in Certificate Manager, you cannot uninstall them in Certificate Manager.</span></span> <span data-ttu-id="6c81e-131">必须通过 MDM 卸载它们。</span><span class="sxs-lookup"><span data-stu-id="6c81e-131">You must uninstall them through MDM.</span></span>
1. <span data-ttu-id="6c81e-132">导航到 " **设置" 应用 > 更新和安全 > 证书**"。</span><span class="sxs-lookup"><span data-stu-id="6c81e-132">Navigate to **Settings App > Update and Security > Certificates**.</span></span>
1. <span data-ttu-id="6c81e-133">在搜索框中按名称搜索证书。</span><span class="sxs-lookup"><span data-stu-id="6c81e-133">Search for the certificate by name in the search box.</span></span>
1. <span data-ttu-id="6c81e-134">选择证书。</span><span class="sxs-lookup"><span data-stu-id="6c81e-134">Select the certificate.</span></span>
1. <span data-ttu-id="6c81e-135">单击 "**删除**"</span><span class="sxs-lookup"><span data-stu-id="6c81e-135">Click **Remove**</span></span>
1. <span data-ttu-id="6c81e-136">出现确认提示时，选择“是”。</span><span class="sxs-lookup"><span data-stu-id="6c81e-136">Select **Yes** when prompted for confirmation.</span></span>



!["证书" 中的 "设置" 应用中的证书查看器](images/certificate-viewer-device.jpg)

![显示如何使用证书 UI 在 "设置" 中安装证书的图片。](images/certificate-device-install.jpg)
