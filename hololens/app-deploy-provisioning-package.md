---
title: 预配包
description: 了解适用于 HoloLens 设备的应用打包、预配、部署和企业应用部署。
keywords: 应用，应用部署，企业应用部署，预配
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 9c73b03e6a8dca6baf6c58fed091df96994c3780
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308400"
---
# <a name="provisioning-package"></a><span data-ttu-id="64f41-104">预配包</span><span class="sxs-lookup"><span data-stu-id="64f41-104">Provisioning Package</span></span>

<span data-ttu-id="64f41-105">预配包可用于在环境中准备和配置设备，而无需访问终结点管理。</span><span class="sxs-lookup"><span data-stu-id="64f41-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="64f41-106">还可以将它们部署到设备，而无需考虑用户的身份、注册状态、 (OOBE) ，或在 [安装过程中应用预配包](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="64f41-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <a name="provisioning-packages-considerations"></a><span data-ttu-id="64f41-107">预配包注意事项：</span><span class="sxs-lookup"><span data-stu-id="64f41-107">Provisioning Packages considerations:</span></span>

* <span data-ttu-id="64f41-108">非公共应用</span><span class="sxs-lookup"><span data-stu-id="64f41-108">Non-Public apps</span></span>
* <span data-ttu-id="64f41-109">仅限 USB 边负载</span><span class="sxs-lookup"><span data-stu-id="64f41-109">USB side-load only</span></span>
* <span data-ttu-id="64f41-110">无自动更新 (需要通过 PPKGs 进行手动更新) </span><span class="sxs-lookup"><span data-stu-id="64f41-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="64f41-111">通过预配包安装的应用必须通过本地计算机存储中的证书进行签名。</span><span class="sxs-lookup"><span data-stu-id="64f41-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="64f41-112">预配包只能将证书安装到本地计算机) 存储 (设备，因此可以通过相同的设置包安装应用和证书。</span><span class="sxs-lookup"><span data-stu-id="64f41-112">Provisioning packages can only install certificates to the device (local machine) store, therefore an app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="64f41-113">如果要从 MDM 部署证书或通过 [证书管理器](certificate-manager.md)进行安装，请确保将证书部署到本地计算机存储区，以便以这种方式对应用进行签名。</span><span class="sxs-lookup"><span data-stu-id="64f41-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="64f41-114">若要了解为 HoloLens 设备创建预配包的基础知识，请访问 [Hololens 预配](https://docs.microsoft.com/hololens/hololens-provisioning)。</span><span class="sxs-lookup"><span data-stu-id="64f41-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="64f41-115">若要部署应用，必须首先使用 "高级" 设置。</span><span class="sxs-lookup"><span data-stu-id="64f41-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="64f41-116">HoloLens (第一代) 支持通过使用预配包在 **UniversalAppInstall**)  (安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="64f41-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="64f41-117">HoloLens (第一代) 设备仅支持在 OOBE 期间仅通过 PPKG 安装应用，并且仅支持使用用户上下文安装进行安装。</span><span class="sxs-lookup"><span data-stu-id="64f41-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <a name="setup"></a><span data-ttu-id="64f41-118">设置</span><span class="sxs-lookup"><span data-stu-id="64f41-118">Setup</span></span>

<span data-ttu-id="64f41-119">在 [Windows 配置设计器](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 中，执行以下四个步骤。</span><span class="sxs-lookup"><span data-stu-id="64f41-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following four steps.</span></span>

1. <span data-ttu-id="64f41-120">将 ApplicationManagement/AllowAllTrustedApps 设置为 "Yes"。</span><span class="sxs-lookup"><span data-stu-id="64f41-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="64f41-121">请参阅： [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。</span><span class="sxs-lookup"><span data-stu-id="64f41-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="64f41-122">导航到 **UniversalAppInstall**  >  **UserContextAppLicense** 输入 **PackageFamilyName**。</span><span class="sxs-lookup"><span data-stu-id="64f41-122">Navigate to **UniversalAppInstall** > **UserContextAppLicense** enter the **PackageFamilyName**.</span></span> <span data-ttu-id="64f41-123">请参阅 [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)。</span><span class="sxs-lookup"><span data-stu-id="64f41-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="64f41-124">另请参阅： [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。</span><span class="sxs-lookup"><span data-stu-id="64f41-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="64f41-125">你可以在已安装应用的设备上使用设备门户。</span><span class="sxs-lookup"><span data-stu-id="64f41-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="64f41-126">访问 "应用" 页，查看 "PackageRelativeID" 行，"！"是你的 **PackageFamilyName**。</span><span class="sxs-lookup"><span data-stu-id="64f41-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>

3. <span data-ttu-id="64f41-127">然后，你将看到一个新的 " **ApplicationFile**" 部分。</span><span class="sxs-lookup"><span data-stu-id="64f41-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="64f41-128">使用此区域上传 appx 捆绑包。</span><span class="sxs-lookup"><span data-stu-id="64f41-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="64f41-129">你需要上传许可证文件或安全证书，具体取决于你是否已购买应用或生成自己的 LOB 应用。</span><span class="sxs-lookup"><span data-stu-id="64f41-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="64f41-130">对于许可证文件：导航到 **UniversalAppInstall**  >  **UserContextAppLicence** ，浏览到你的许可证的位置并将其上传。</span><span class="sxs-lookup"><span data-stu-id="64f41-130">For license file: navigate to **UniversalAppInstall** > **UserContextAppLicence** and browse to the location of your license and upload it.</span></span>
    - <span data-ttu-id="64f41-131">对于安全文件，请导航到 " **证书** "，并选择要随 .appx 包一起安装的证书。</span><span class="sxs-lookup"><span data-stu-id="64f41-131">For the security file, navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="64f41-132">请确保将项目保存到安全位置。</span><span class="sxs-lookup"><span data-stu-id="64f41-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="64f41-133">然后将其 **导出** 为 **预配包**。</span><span class="sxs-lookup"><span data-stu-id="64f41-133">Then **Export** it as a **Provisioning Package**.</span></span>  

<span data-ttu-id="64f41-134">另请参阅： [将预配包应用于 HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="64f41-134">See also: [Apply your provisioning package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
