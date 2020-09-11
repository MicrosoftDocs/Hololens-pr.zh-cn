---
title: 预配程序包
description: 应用、应用部署、企业应用 demployment、预配
keywords: 应用、应用部署、企业应用 demployment、预配
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
ms.openlocfilehash: 6daf99fbb60e0daf892d5d02e86492061a665070
ms.sourcegitcommit: 72ff3174b34d2acaf72547b7d981c66aef8fa82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11009500"
---
# <span data-ttu-id="d2fcf-104">预配程序包</span><span class="sxs-lookup"><span data-stu-id="d2fcf-104">Provisioning Package</span></span>

<span data-ttu-id="d2fcf-105">预配程序包可用于在环境中准备和配置设备，而无需访问终结点管理。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-105">Provisioning packages can be used to prepare and configure devices in an environment without access to endpoint management.</span></span> <span data-ttu-id="d2fcf-106">也可以将它们部署到设备，而无需考虑用户的身份、注册状态、 (OOBE) 或 [在安装过程中应用预配包](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-106">They can also be deployed to a device regardless of identity of the user, enrollment status, during the Out of Box Experience (OOBE), or by [applying a provisioning package during setup](https://docs.microsoft.com/hololens/hololens-provisioning##apply-a-provisioning-package-to-hololens-during-setup).</span></span>

## <span data-ttu-id="d2fcf-107">预配程序包注意事项：</span><span class="sxs-lookup"><span data-stu-id="d2fcf-107">Provisioning Packages considerations:</span></span>
* <span data-ttu-id="d2fcf-108">非公共应用</span><span class="sxs-lookup"><span data-stu-id="d2fcf-108">Non-Public apps</span></span>
* <span data-ttu-id="d2fcf-109">仅限 USB 盘面加载</span><span class="sxs-lookup"><span data-stu-id="d2fcf-109">USB side-load only</span></span>
* <span data-ttu-id="d2fcf-110">无自动更新 (需要通过 PPKGs) 手动更新</span><span class="sxs-lookup"><span data-stu-id="d2fcf-110">No auto update (requires manual updates via PPKGs)</span></span>

> [!NOTE] 
> <span data-ttu-id="d2fcf-111">若要了解为 HoloLens 设备创建预配包的基础知识，请访问 [HoloLens 预配](https://docs.microsoft.com/hololens/hololens-provisioning)。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-111">To learn the basics of creating a Provisioning Package for HoloLens devices, visit [HoloLens Provisioning](https://docs.microsoft.com/hololens/hololens-provisioning).</span></span> <span data-ttu-id="d2fcf-112">若要部署应用，必须首先从高级预配开始。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-112">To deploy an app, you must start with advanced provisioning.</span></span> 

## <span data-ttu-id="d2fcf-113">安装</span><span class="sxs-lookup"><span data-stu-id="d2fcf-113">Setup</span></span>

<span data-ttu-id="d2fcf-114">在 [Windows 配置设计器](https://www.microsoft.com/store/productId/9NBLGGH4TX22) 中，请执行以下4个步骤。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-114">Within [Windows Configuration Designer](https://www.microsoft.com/store/productId/9NBLGGH4TX22) take following 4 steps.</span></span>

1. <span data-ttu-id="d2fcf-115">将 ApplicationManagement/AllowAllTrustedApps 设置为 "Yes"。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-115">Set ApplicationManagement/AllowAllTrustedApps To “Yes”.</span></span> <span data-ttu-id="d2fcf-116">请参阅： [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps)。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-116">See: [ApplicationManagement/AllowAllTrustedApps](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowalltrustedapps).</span></span>
2. <span data-ttu-id="d2fcf-117">在**UniversalAppInstall**  >  **UserContextAppLicense**请输入**PackageFamilyName**。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-117">Under **UniversalAppInstall** > **UserContextAppLicense** please enter the **PackageFamilyName**.</span></span> <span data-ttu-id="d2fcf-118">请参阅 [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall)。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-118">See [UniversalAppInstall](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall).</span></span> <span data-ttu-id="d2fcf-119">另请参阅： [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense)。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-119">See also: [UserContextAppLicense](https://docs.microsoft.com/windows/configuration/wcd/wcd-universalappinstall#usercontextapplicense).</span></span>
    - <span data-ttu-id="d2fcf-120">如果不知道这一点，则可以在已安装应用的设备上使用 Device Portal。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-120">If you don’t know this, you can use Device Portal on a device you have already installed your app to.</span></span> <span data-ttu-id="d2fcf-121">访问 "应用" 页面，查看 PackageRelativeID 行，"！" 之前的所有信息是您的 **PackageFamilyName**。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-121">Visit the Apps page, and look at the PackageRelativeID line, all the information before the "!" Is your **PackageFamilyName**.</span></span>
3. <span data-ttu-id="d2fcf-122">然后，你将看到你有一个新分区 **ApplicationFile**。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-122">You will then see that you have a new section, **ApplicationFile**.</span></span> <span data-ttu-id="d2fcf-123">使用此区域上载你的 appx 捆绑包。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-123">Use this area to upload your appx bundle.</span></span> 
4. <span data-ttu-id="d2fcf-124">根据你是否已购买你的应用或构建自己的 LOB 应用，你需要上载许可证文件或安全证书。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-124">Depending on if you have purchased your app or built your own LOB app, you will need to upload the license file or security certificate.</span></span>
    - <span data-ttu-id="d2fcf-125">对于许可证文件：在**UniversalAppInstall**  >  **UserContextAppLience**下，浏览到许可证的位置并上传。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-125">For license file: Under **UniversalAppInstall** > **UserContextAppLience** and browse to the location of your license and upload it.</span></span> 
    - <span data-ttu-id="d2fcf-126">对于安全文件，导航到 " **证书** " 并选择要在您的 .appx 捆绑包旁安装的证书。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-126">For security file navigate to **Certificates** and select your certificate to install alongside your .appx bundle.</span></span> 

<span data-ttu-id="d2fcf-127">请确保将项目保存到安全位置。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-127">Make sure to save your project to a secure location.</span></span> <span data-ttu-id="d2fcf-128">然后将其 **导出** 为 **预配包**。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-128">Then **Export** it as a **Provisioning Package**.</span></span>  
    
<span data-ttu-id="d2fcf-129">另请参阅： [将 provisiong 程序包应用于 HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup)。</span><span class="sxs-lookup"><span data-stu-id="d2fcf-129">See also: [Apply your provisiong package to HoloLens](https://docs.microsoft.com/hololens/hololens-provisioning#apply-a-provisioning-package-to-hololens-during-setup).</span></span>
