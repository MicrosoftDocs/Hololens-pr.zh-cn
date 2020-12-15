---
title: 预配程序包
description: 应用， 应用部署， 企业应用计划， 预配
keywords: 应用， 应用部署， 企业应用计划， 预配
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
ms.openlocfilehash: 60efc454f9e1221372279401da9f8ee918e061e7
ms.sourcegitcommit: efa3fb7e353c5e56ee467cc7fd94ffdfaf46e2e5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2020
ms.locfileid: "11219219"
---
# <span data-ttu-id="408fb-104">预配程序包</span><span class="sxs-lookup"><span data-stu-id="408fb-104">Provisioning Package</span></span>

<span data-ttu-id="408fb-105">预配包可用于在无法访问终结点管理的环境中准备和配置设备。</span><span class="sxs-lookup"><span data-stu-id="408fb-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="408fb-106">它们还可以部署到设备，无论用户的身份、注册状态、在开箱即用体验 (OOBE) 期间，或在设置过程中应用预配 [包](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="408fb-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="408fb-107">预配包注意事项：</span><span class="sxs-lookup"><span data-stu-id="408fb-107">Provisioning Packages considerations:</span></span>
* <span data-ttu-id="408fb-108">非公共应用</span><span class="sxs-lookup"><span data-stu-id="408fb-108">Non-Public apps</span></span>
* <span data-ttu-id="408fb-109">仅 USB 旁加载</span><span class="sxs-lookup"><span data-stu-id="408fb-109">USB side-load only</span></span>
* <span data-ttu-id="408fb-110">无需自动更新 (需要通过 PPG 或) </span><span class="sxs-lookup"><span data-stu-id="408fb-110">No auto update (requires manual updates via PPKGs)</span></span>

<span data-ttu-id="408fb-111">通过预配包安装的应用必须由本地计算机存储中的证书签名。</span><span class="sxs-lookup"><span data-stu-id="408fb-111">Apps installed via a provisioning package must be signed by a certificate in the local machine store.</span></span> <span data-ttu-id="408fb-112">预配包只能将证书安装到本地计算机 (存储) ，因此应用和证书可以通过同一预配包进行安装。</span><span class="sxs-lookup"><span data-stu-id="408fb-112">Provisioning packages can only install certificates to the device (local machine) store, therefore the app and certificate may be installed via the same provisioning package.</span></span> <span data-ttu-id="408fb-113">如果要从 MDM 部署证书或通过证书管理器进行安装，请确保[](certificate-manager.md)将证书部署到本地计算机存储，以通过这种方法对安装的应用进行签名。</span><span class="sxs-lookup"><span data-stu-id="408fb-113">If you are deploying your certificate from MDM or installing via the [Certificate Manager](certificate-manager.md), please make sure to deploy the certificate to the local machine store to sign apps installed this way.</span></span>

<span data-ttu-id="408fb-114">若要了解为 HoloLens 设备创建预配包的基础知识，请访问 [HoloLens 预配](https://docs.microsoft.com/hololens/hololens-provisioning)。</span><span class="sxs-lookup"><span data-stu-id="408fb-114">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="408fb-115">若要部署应用，必须从高级预配开始。</span><span class="sxs-lookup"><span data-stu-id="408fb-115">To deploy an app, you must start with advanced provisioning.</span></span>

> [!NOTE]
> <span data-ttu-id="408fb-116">HoloLens (第一代) 具有有限的支持，支持使用预配包 (**UniversalAppInstall**) 安装应用。</span><span class="sxs-lookup"><span data-stu-id="408fb-116">HoloLens (1st gen) has limited support installing apps (**UniversalAppInstall**) by using a provisioning package.</span></span> <span data-ttu-id="408fb-117">HoloLens (第一代) 设备仅在 OOBE 期间仅支持通过 PPKG 安装应用，并且仅支持用户上下文安装。</span><span class="sxs-lookup"><span data-stu-id="408fb-117">HoloLens (1st gen) devices only support installing an app via PPKG only during OOBE and only with user context installs.</span></span>

## <span data-ttu-id="408fb-118">安装</span><span class="sxs-lookup"><span data-stu-id="408fb-118">Setup</span></span>

<span data-ttu-id="408fb-119">在 [Windows 配置设计器中](https://www.microsoft.com/store/productId/9NBLGGH4TX22) ，执行下列 4 个步骤。</span><span class="sxs-lookup"><span data-stu-id="408fb-119">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following 4 steps.</span></span>

1. <span data-ttu-id="408fb-120">将 ApplicationManagement/AllowAllTrustedApps 设置为"是"。</span><span class="sxs-lookup"><span data-stu-id="408fb-120">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="408fb-121">请参阅 [：ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。</span><span class="sxs-lookup"><span data-stu-id="408fb-121">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>

2. <span data-ttu-id="408fb-122">在**UniversalAppInstall**  >  **UserContextAppLicense**下，请输入**PackageFamilyName。**</span><span class="sxs-lookup"><span data-stu-id="408fb-122">Under **UniversalAppInstall** > **UserContextAppLicense** please enter the **PackageFamilyName**.</span></span> <span data-ttu-id="408fb-123">请参阅 [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)。</span><span class="sxs-lookup"><span data-stu-id="408fb-123">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="408fb-124">另请参阅 [：UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。</span><span class="sxs-lookup"><span data-stu-id="408fb-124">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>

   <span data-ttu-id="408fb-125">可以在已安装应用的设备上使用 Device Portal。</span><span class="sxs-lookup"><span data-stu-id="408fb-125">You can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="408fb-126">访问"应用"页，查看 PackageRelativeID 行，"！"是 **PackageFamilyName**。</span><span class="sxs-lookup"><span data-stu-id="408fb-126">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>
    
3. <span data-ttu-id="408fb-127">然后，你将看到有一个新节**ApplicationFile。**</span><span class="sxs-lookup"><span data-stu-id="408fb-127">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="408fb-128">使用此区域上载 appx 捆绑包。</span><span class="sxs-lookup"><span data-stu-id="408fb-128">Use this area to upload your appx bundle.</span></span>

4. <span data-ttu-id="408fb-129">根据你已购买应用还是生成自己的 LOB 应用，你将需要上载许可证文件或安全证书。</span><span class="sxs-lookup"><span data-stu-id="408fb-129">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>

    - <span data-ttu-id="408fb-130">对于许可证文件：在**UniversalAppInstall**  >  **UserContextAppLience**下，浏览到许可证的位置并上载它。</span><span class="sxs-lookup"><span data-stu-id="408fb-130">For license file: Under **UniversalAppInstall** > **UserContextAppLience** and browse to the location of your license and upload it.</span></span> 
    - <span data-ttu-id="408fb-131">对于安全文件，请导航到 **"** 证书"，然后选择要随 .appx 捆绑包一起安装的证书。</span><span class="sxs-lookup"><span data-stu-id="408fb-131">For security file navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span>

<span data-ttu-id="408fb-132">确保将项目保存到安全位置。</span><span class="sxs-lookup"><span data-stu-id="408fb-132">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="408fb-133">然后 **导出** 为 **预配包**。</span><span class="sxs-lookup"><span data-stu-id="408fb-133">Then **Export** it as a **Provisioning Package**.</span></span>  
    
<span data-ttu-id="408fb-134">另请参阅：[将预配包应用到 HoloLens。](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)</span><span class="sxs-lookup"><span data-stu-id="408fb-134">See also: [Apply your provisiong package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
