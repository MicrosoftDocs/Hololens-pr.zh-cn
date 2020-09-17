---
title: Intune 和公司门户
description: intune、应用管理、应用、公司门户、门户
keywords: intune、应用管理、应用、公司门户、门户、hololens
author: evmill
ms.author: v-evmill
ms.date: 6/22/2020
ms.prod: hololens
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 55e2b15808e52bb80e8114e215bc0cef52358842
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016660"
---
# <span data-ttu-id="57490-104">Intune 和公司门户</span><span class="sxs-lookup"><span data-stu-id="57490-104">Intune & Company Portal</span></span>

<span data-ttu-id="57490-105">通过移动设备管理 (MDM) ，你可以通过 [Microsoft 终结点管理器 (Intune ](https://docs.microsoft.com/intune/windows-holographic-for-business) 使用你自己的自定义应用) 将其直接部署到 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="57490-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="57490-106">Microsoft Intune 是基于云的服务，侧重于移动设备管理 (MDM) 和移动应用管理 (MAM) 。</span><span class="sxs-lookup"><span data-stu-id="57490-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="57490-107">Intune 包含在 Microsoft 的[企业移动性 + 安全 (EMS) 套件](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)中，使用户可以提高工作效率，同时保持组织数据受保护。</span><span class="sxs-lookup"><span data-stu-id="57490-107">Intune is included in Microsoft's[Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="57490-108">若要了解有关 Intune 的详细信息，请阅读 [什么是 intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)。</span><span class="sxs-lookup"><span data-stu-id="57490-108">To learn more about Intune, please read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="57490-109">安装</span><span class="sxs-lookup"><span data-stu-id="57490-109">Setup</span></span>

1. <span data-ttu-id="57490-110">将应用上载到某一业务线，或将自定义应用上载到你的 Intune 租户。</span><span class="sxs-lookup"><span data-stu-id="57490-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="57490-111">另请参阅： [企业应用管理](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)。</span><span class="sxs-lookup"><span data-stu-id="57490-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="57490-112">[将你的应用分配到组](https://docs.microsoft.com/mem/intune/apps/apps-deploy)。</span><span class="sxs-lookup"><span data-stu-id="57490-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="57490-113">根据你选择的作业类型，你可以将应用自动发送或打开，如果你有选择的应用，可以轻松地将其拉下。</span><span class="sxs-lookup"><span data-stu-id="57490-113">Based on the assignment type you choose you can have the app delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span> 

> [!NOTE] 
> <span data-ttu-id="57490-114">在构建 appx 捆绑时，请确保考虑为要部署到) 的设备 (s 的体系结构。</span><span class="sxs-lookup"><span data-stu-id="57490-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="57490-115">HoloLens 2 是 ARM64，HoloLens (第一代) 是 x86。</span><span class="sxs-lookup"><span data-stu-id="57490-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="57490-116">如果你计划拥有混合设备环境，则可以在单个 appx 捆绑包中包括这两者。</span><span class="sxs-lookup"><span data-stu-id="57490-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="57490-117">工作分配类型</span><span class="sxs-lookup"><span data-stu-id="57490-117">Assignment types</span></span>

<span data-ttu-id="57490-118">如果你希望在注册后在设备上自动安装你的应用，你应该为该组 (s ") 选择" **必需** "。</span><span class="sxs-lookup"><span data-stu-id="57490-118">If you prefer your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="57490-119">如果你希望将应用下载到通过公司门户注册的应用，请选择 " **可用于注册的设备**"。</span><span class="sxs-lookup"><span data-stu-id="57490-119">If you prefer to make your app available for download to those enrolled through the company portal, select **Available for enrolled devices**.</span></span>


## <span data-ttu-id="57490-120">最终用户体验</span><span class="sxs-lookup"><span data-stu-id="57490-120">End User Experience</span></span>

<span data-ttu-id="57490-121">在 Intune 上设置配置后，最终用户即可接收所选应用。</span><span class="sxs-lookup"><span data-stu-id="57490-121">After you have set up configuration on Intune you are ready for end users to recieve your selected apps.</span></span>

<span data-ttu-id="57490-122">按照以下步骤自动获取你的应用 (s) ：</span><span class="sxs-lookup"><span data-stu-id="57490-122">Follow these steps to automatically get your app(s):</span></span>
1. <span data-ttu-id="57490-123">向你的租户注册你的设备。</span><span class="sxs-lookup"><span data-stu-id="57490-123">Enroll your device with your tenant.</span></span> 
2. <span data-ttu-id="57490-124">设备完成注册后，你应在设备上收到该应用。</span><span class="sxs-lookup"><span data-stu-id="57490-124">Once your device has completed enrollment, you should receive the app on your device.</span></span> 
3. <span data-ttu-id="57490-125">如果你未立即看到你的应用，请转到 "**设置**  >  **帐户**  >  **工作或学校**  >  **帐户**信息"，然后向下滚动以查看有关已安装的应用状态的信息。</span><span class="sxs-lookup"><span data-stu-id="57490-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > **youraccount** Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="57490-126">如何通过公司门户访问应用：</span><span class="sxs-lookup"><span data-stu-id="57490-126">How to get to apps through the Company Portal:</span></span>
1. <span data-ttu-id="57490-127">打开 " **开始" 菜单** ，然后选择 " **Microsoft Store**"。</span><span class="sxs-lookup"><span data-stu-id="57490-127">Open the **Start Menu** and select **Microsoft Store**.</span></span> 
2. <span data-ttu-id="57490-128">搜索 **公司门户** 并下载应用。</span><span class="sxs-lookup"><span data-stu-id="57490-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="57490-129">登录到您的帐户。</span><span class="sxs-lookup"><span data-stu-id="57490-129">Sign into your account.</span></span>
4. <span data-ttu-id="57490-130">选择你希望接收和下载的应用。</span><span class="sxs-lookup"><span data-stu-id="57490-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="57490-131">了解有关 [自动安装公司门户](https://docs.microsoft.com/mem/intune/apps/company-portal-app) 和 [在 Intune 中部署和管理应用](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="57490-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
