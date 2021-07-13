---
title: Intune 和公司门户
description: 了解如何使用 Intune、移动设备管理和公司门户设置、分配和创建舒适的用户体验。
keywords: intune，应用管理，应用，公司门户，门户，hololens
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
ms.openlocfilehash: b192732f5e7edffaa1d0ab081454e4034c416191
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635494"
---
# <a name="intune--company-portal"></a><span data-ttu-id="17476-104">Intune 和公司门户</span><span class="sxs-lookup"><span data-stu-id="17476-104">Intune & Company Portal</span></span>

<span data-ttu-id="17476-105">使用移动设备管理 (MDM) ，你可以使用自己的自定义应用， [Microsoft Endpoint Manager (Intune) ](/intune/windows-holographic-for-business)将其直接部署到 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="17476-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="17476-106">Microsoft Intune 是一项基于云的服务，关注移动设备管理 (MDM) 和移动应用程序管理 (MAM)。</span><span class="sxs-lookup"><span data-stu-id="17476-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="17476-107">Intune 包含在 Microsoft 的[企业移动性 + 安全性 (EMS) 套件](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)中，使用户能够提高工作效率，同时保护组织数据。</span><span class="sxs-lookup"><span data-stu-id="17476-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="17476-108">若要了解有关 Intune 的详细信息，请阅读 [什么是 intune](/mem/intune/fundamentals/what-is-intune)。</span><span class="sxs-lookup"><span data-stu-id="17476-108">To learn more about Intune, read [What is Intune](/mem/intune/fundamentals/what-is-intune).</span></span>

## <a name="setup"></a><span data-ttu-id="17476-109">设置</span><span class="sxs-lookup"><span data-stu-id="17476-109">Setup</span></span>

1. <span data-ttu-id="17476-110">向业务线 Upload 应用，或将自定义应用上传到 Intune 租户。</span><span class="sxs-lookup"><span data-stu-id="17476-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="17476-111">另请参阅： [Enterprise 应用管理](/windows/client-management/mdm/enterprise-app-management)。</span><span class="sxs-lookup"><span data-stu-id="17476-111">See also: [Enterprise app management](/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="17476-112">[将应用分配到组](/mem/intune/apps/apps-deploy)。</span><span class="sxs-lookup"><span data-stu-id="17476-112">[Assign your app to a group](/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="17476-113">根据所选的分配类型，应用可以自动传递，也可以在有选择的应用的情况下随时向下移动。</span><span class="sxs-lookup"><span data-stu-id="17476-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="17476-114">生成 appx 捆绑时，请确保考虑要部署到) 的设备 (的体系结构。</span><span class="sxs-lookup"><span data-stu-id="17476-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="17476-115">HoloLens 2 是 ARM64，HoloLens (第一代) 为 x86。</span><span class="sxs-lookup"><span data-stu-id="17476-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="17476-116">如果你计划使用混合设备环境，则可以将这两个包都包含在单个 appx 捆绑包中。</span><span class="sxs-lookup"><span data-stu-id="17476-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <a name="assignment-types"></a><span data-ttu-id="17476-117">分配类型</span><span class="sxs-lookup"><span data-stu-id="17476-117">Assignment types</span></span>

<span data-ttu-id="17476-118">若要在注册后将应用自动安装到设备上，则应为该组 (s) 选择 " **必需** "。</span><span class="sxs-lookup"><span data-stu-id="17476-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="17476-119">若要使应用可下载到通过公司门户注册的设备，请选择 " **可用于已注册的设备**"。</span><span class="sxs-lookup"><span data-stu-id="17476-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <a name="end-user-experience"></a><span data-ttu-id="17476-120">最终用户体验</span><span class="sxs-lookup"><span data-stu-id="17476-120">End-User Experience</span></span>

<span data-ttu-id="17476-121">在 Intune 上设置配置后，最终用户就可以接收选定的应用了。</span><span class="sxs-lookup"><span data-stu-id="17476-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="17476-122">按照以下步骤自动 () 的应用：</span><span class="sxs-lookup"><span data-stu-id="17476-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="17476-123">将你的设备注册到你的租户。</span><span class="sxs-lookup"><span data-stu-id="17476-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="17476-124">设备完成注册后，你应在设备上收到应用。</span><span class="sxs-lookup"><span data-stu-id="17476-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="17476-125">如果你不能立即看到应用，请访问 **设置**  >  **帐户**"  >  **工作或学校** 查看  >  *你的帐户* 信息，并向下滚动以查看有关已安装应用状态的信息。</span><span class="sxs-lookup"><span data-stu-id="17476-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="17476-126">如何通过公司门户获取应用：</span><span class="sxs-lookup"><span data-stu-id="17476-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="17476-127">打开 "**开始" 菜单** 并选择 " **Microsoft Store**"。</span><span class="sxs-lookup"><span data-stu-id="17476-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="17476-128">搜索 **公司门户** 并下载应用。</span><span class="sxs-lookup"><span data-stu-id="17476-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="17476-129">登录到你的帐户。</span><span class="sxs-lookup"><span data-stu-id="17476-129">Sign into your account.</span></span>
4. <span data-ttu-id="17476-130">选择要接收的应用并下载它。</span><span class="sxs-lookup"><span data-stu-id="17476-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="17476-131">详细了解如何在 Intune 中[自动安装公司门户](/mem/intune/apps/company-portal-app)以及如何[部署和管理应用](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)。</span><span class="sxs-lookup"><span data-stu-id="17476-131">Learn more about [auto-installing the Company Portal](/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
