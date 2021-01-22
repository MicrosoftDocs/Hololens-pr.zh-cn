---
title: Intune 和公司门户
description: 了解如何使用 Intune、移动设备管理和公司门户设置、分配和创建舒适用户体验。
keywords: intune， 应用管理， 应用， 公司门户， 门户， hololens
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
ms.openlocfilehash: f91f97b6cddf678b20d0bdb3f381e01809b10f3f
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283713"
---
# <span data-ttu-id="1370f-104">Intune 和公司门户</span><span class="sxs-lookup"><span data-stu-id="1370f-104">Intune & Company Portal</span></span>

<span data-ttu-id="1370f-105">借助移动设备管理 (MDM) ，可以通过 [Microsoft Endpoint Manager (Intune) ](https://docs.microsoft.com/intune/windows-holographic-for-business) 使用自己的自定义应用将其直接部署到 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="1370f-105">With Mobile Device Management (MDM), you can use your own custom apps through [Microsoft Endpoint Manager (Intune)](https://docs.microsoft.com/intune/windows-holographic-for-business) to deploy it directly to your HoloLens devices.</span></span> <span data-ttu-id="1370f-106">Microsoft Intune 是一项基于云的服务，专注于移动设备管理 (MDM) 和 MAM (移动应用程序) 。</span><span class="sxs-lookup"><span data-stu-id="1370f-106">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="1370f-107">Intune 包含在 Microsoft 企业移动性 + 安全性 ([EMS) 套件中，](https://www.microsoft.com/microsoft-365/enterprise-mobility-security)使用户能够在保持组织数据受保护的同时提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="1370f-107">Intune is included in Microsoft's [Enterprise Mobility + Security (EMS) suite](https://www.microsoft.com/microsoft-365/enterprise-mobility-security), and enables users to be productive while keeping your organization data protected.</span></span> <span data-ttu-id="1370f-108">若要了解有关 Intune 的更多信息，请阅读[什么是 Intune。](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)</span><span class="sxs-lookup"><span data-stu-id="1370f-108">To learn more about Intune, read [What is Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune).</span></span>

## <span data-ttu-id="1370f-109">安装</span><span class="sxs-lookup"><span data-stu-id="1370f-109">Setup</span></span>

1. <span data-ttu-id="1370f-110">将应用上传到业务线，或将自定义应用上传到 Intune 租户。</span><span class="sxs-lookup"><span data-stu-id="1370f-110">Upload an app to a Line of Business, or upload a custom app to your Intune tenant.</span></span> <span data-ttu-id="1370f-111">另请参阅： [企业应用管理](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management)。</span><span class="sxs-lookup"><span data-stu-id="1370f-111">See also: [Enterprise app management](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management).</span></span>

2. <span data-ttu-id="1370f-112">[将应用分配给组](https://docs.microsoft.com/mem/intune/apps/apps-deploy)。</span><span class="sxs-lookup"><span data-stu-id="1370f-112">[Assign your app to a group](https://docs.microsoft.com/mem/intune/apps/apps-deploy).</span></span> <span data-ttu-id="1370f-113">根据你选择的分配类型，如果你选择了应用，该应用可以自动交付或可供轻松下拉。</span><span class="sxs-lookup"><span data-stu-id="1370f-113">Based on the assignment type you choose, the app can be delivered automatically or available to be readily pulled down if you have a selection of apps.</span></span>

> [!NOTE]
> <span data-ttu-id="1370f-114">生成 appx 捆绑包时，请务必考虑包括要部署到 () 应用的体系结构。</span><span class="sxs-lookup"><span data-stu-id="1370f-114">When building your appx bundle make sure to account for including the architecture for the device(s) that you are deploying to.</span></span> <span data-ttu-id="1370f-115">HoloLens 2 为 ARM64，HoloLens (第一代) x86。</span><span class="sxs-lookup"><span data-stu-id="1370f-115">HoloLens 2 is ARM64, and HoloLens (1st Gen) is x86.</span></span> <span data-ttu-id="1370f-116">如果你计划使用混合设备环境，你可以将两者都包括在单个 appx 捆绑包中。</span><span class="sxs-lookup"><span data-stu-id="1370f-116">You may include both in a single appx bundle if you plan on having a mixed devices environment.</span></span>

## <span data-ttu-id="1370f-117">工作分配类型</span><span class="sxs-lookup"><span data-stu-id="1370f-117">Assignment types</span></span>

<span data-ttu-id="1370f-118">若要在注册后在设备上自动安装你的应用，你应该选择该组 (必需) 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1370f-118">To have your app to be automatically installed on the device after enrollment, you should select **Required** for that group(s).</span></span>
<span data-ttu-id="1370f-119">若要将应用下载到通过公司门户注册的设备，请选择 **"可用于已注册的设备"。**</span><span class="sxs-lookup"><span data-stu-id="1370f-119">To make your app available for download to devices enrolled through the company portal, select **Available for enrolled devices**.</span></span>

## <span data-ttu-id="1370f-120">End-User体验</span><span class="sxs-lookup"><span data-stu-id="1370f-120">End-User Experience</span></span>

<span data-ttu-id="1370f-121">在 Intune 上设置配置后，你已准备好让最终用户接收所选应用。</span><span class="sxs-lookup"><span data-stu-id="1370f-121">After you have set up configuration on Intune, you are ready for end users to receive your selected apps.</span></span>

<span data-ttu-id="1370f-122">按照以下步骤自动获取应用 () ：</span><span class="sxs-lookup"><span data-stu-id="1370f-122">Follow these steps to automatically get your app(s):</span></span>

1. <span data-ttu-id="1370f-123">向租户注册设备。</span><span class="sxs-lookup"><span data-stu-id="1370f-123">Enroll your device with your tenant.</span></span>
2. <span data-ttu-id="1370f-124">设备完成注册后，你应该在设备上接收应用。</span><span class="sxs-lookup"><span data-stu-id="1370f-124">Once your device has completed enrollment, you should receive the app on your device.</span></span>
3. <span data-ttu-id="1370f-125">如果未立即看到应用，请转到"设置帐户工作或\*\*\*\* 学校帐户信息"，然后向下滚动以查看有关已安装应用  >  \*\*\*\*  >  \*\*\*\*  >  \*\* 状态的信息。</span><span class="sxs-lookup"><span data-stu-id="1370f-125">If you are not seeing you app immediately, go to **Settings** > **Accounts** > **Work or School** > *your account* Info, and scroll down to see information on installed app status.</span></span>

<span data-ttu-id="1370f-126">如何通过公司门户访问应用：</span><span class="sxs-lookup"><span data-stu-id="1370f-126">How to get to apps through the Company Portal:</span></span>

1. <span data-ttu-id="1370f-127">打开"**开始"菜单**并选择**Microsoft Store。**</span><span class="sxs-lookup"><span data-stu-id="1370f-127">Open the **Start Menu** and select **Microsoft Store**.</span></span>
2. <span data-ttu-id="1370f-128">搜索 **公司门户** 并下载应用。</span><span class="sxs-lookup"><span data-stu-id="1370f-128">Search for **Company Portal** and download the app.</span></span>
3. <span data-ttu-id="1370f-129">登录到你的帐户。</span><span class="sxs-lookup"><span data-stu-id="1370f-129">Sign into your account.</span></span>
4. <span data-ttu-id="1370f-130">选择要接收的应用并下载它。</span><span class="sxs-lookup"><span data-stu-id="1370f-130">Select the app you wish to receive and download it.</span></span>

> [!Tip]
> <span data-ttu-id="1370f-131">详细了解如何 [自动安装](https://docs.microsoft.com/mem/intune/apps/company-portal-app) 公司门户，以及 [部署和管理 Intune 中的应用](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps)。</span><span class="sxs-lookup"><span data-stu-id="1370f-131">Learn more about [auto-installing the Company Portal](https://docs.microsoft.com/mem/intune/apps/company-portal-app) and [deploying and managing apps in Intune](https://docs.microsoft.com/mem/intune/fundamentals/windows-holographic-for-business#deploy-and-manage-apps).</span></span>
