---
title: 部署指南 - 使用 Dynamics 365 指南的企业连接的 HoloLens 2 - 维护
description: 了解如何使用 Dynamics 365 指南通过企业连接网络维护 HoloLens 2 设备。
keywords: HoloLens， 管理， 企业连接， Dynamics 365 指南， AAD， Azure AD， MDM， 移动设备管理
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: aboeger
ms.date: 03/24/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f231e65e17ab053e34e7174e1ed7ff6e7a0a56b8
ms.sourcegitcommit: d7c86ccad7be32f7223d4b801083798454fda740
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "11448514"
---
# <a name="maintain---corporate-connected-guide"></a><span data-ttu-id="12ba1-104">Maintain - 企业连接指南</span><span class="sxs-lookup"><span data-stu-id="12ba1-104">Maintain - Corporate Connected Guide</span></span>

## <a name="update-hololens"></a><span data-ttu-id="12ba1-105">更新 HoloLens</span><span class="sxs-lookup"><span data-stu-id="12ba1-105">Update HoloLens</span></span>

<span data-ttu-id="12ba1-106">Microsoft 设计适用于企业的 Windows 更新以为 IT 管理员提供更多以 Windows 更新为中心的管理功能，例如对一组设备部署更新的功能，以及为安装更新而定义维护窗口的功能。</span><span class="sxs-lookup"><span data-stu-id="12ba1-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="12ba1-107">管理更新的一种常用方法是将功能延迟 30 天。</span><span class="sxs-lookup"><span data-stu-id="12ba1-107">One popular method of managing updates is to do a feature deferral of 30 days.</span></span> <span data-ttu-id="12ba1-108">这使管理员能够更新和预览新功能，获得第一手知识，并通知支持人员任何新更改。</span><span class="sxs-lookup"><span data-stu-id="12ba1-108">This allows Admins to update and preview new features, gaining first hand knowledge and informing your support desk of any new changes.</span></span>

<span data-ttu-id="12ba1-109">了解如何管理 [HoloLens](https://docs.microsoft.com/hololens/hololens-updates)更新，包括计划天数、计划时间和在设备上设置使用时段，以便它将在工作时间之外更新。</span><span class="sxs-lookup"><span data-stu-id="12ba1-109">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates), including scheduled days, scheduled time, and setting active hours on the device, so it will update outside of working hours.</span></span>

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a><span data-ttu-id="12ba1-110">如何更新 Dynamics 365 Guides (和其他应用商店应用) </span><span class="sxs-lookup"><span data-stu-id="12ba1-110">How to update Dynamics 365 Guides (and other store apps)</span></span>

<span data-ttu-id="12ba1-111">Dynamics 365 Guides 是一款In-Box应用，可通过 Microsoft Store 应用进行更新。</span><span class="sxs-lookup"><span data-stu-id="12ba1-111">Dynamics 365 Guides is an In-Box app, and can be updated through the Microsoft Store app.</span></span> <span data-ttu-id="12ba1-112">对于通过 Microsoft Store 下载的所有应用，可以通过 Microsoft [Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 应用本身手动进行更新。</span><span class="sxs-lookup"><span data-stu-id="12ba1-112">For all apps that are downloaded through the Microsoft Store, they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="how-to-update-lob-apps"></a><span data-ttu-id="12ba1-113">如何更新 LOB 应用</span><span class="sxs-lookup"><span data-stu-id="12ba1-113">How to update LOB apps</span></span>

<span data-ttu-id="12ba1-114">LOB 应用更新的方式与添加到 Intune 的方法相同。</span><span class="sxs-lookup"><span data-stu-id="12ba1-114">LOB apps can be updated in the same way they were added to Intune.</span></span> <span data-ttu-id="12ba1-115">可通过将版本号较高的新应用上载到现有应用配置，在 Intune 中更新应用。</span><span class="sxs-lookup"><span data-stu-id="12ba1-115">Apps can be updated in Intune by uploading the new app with a higher version number to the existing App configuration.</span></span> <span data-ttu-id="12ba1-116">当设备同步到 Intune 时，它将发现存在较新的应用版本，并且将下载较新的应用并替换旧应用。</span><span class="sxs-lookup"><span data-stu-id="12ba1-116">When the device syncs to Intune, it will observe that there is a newer app version and the newer app will be downloaded and replace the old app.</span></span>

1. <span data-ttu-id="12ba1-117">若要上载较新的应用，请导航到[MEM 门户](https://endpoint.microsoft.com/#home)  ->  **应用**->**所有应用**  ->  *NameOfYourApp*  ->  **属性。**</span><span class="sxs-lookup"><span data-stu-id="12ba1-117">To upload the newer app, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** -> *TheNameOfYourApp* -> **Properties.**</span></span>
2. <span data-ttu-id="12ba1-118">在"应用信息"旁边，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="12ba1-118">Next to App information, select **Edit.**</span></span>
3. <span data-ttu-id="12ba1-119">对于"选择要 &quot; 更新的文件"的值 &quot; ，请选择您的文件。</span><span class="sxs-lookup"><span data-stu-id="12ba1-119">For the value of &quot;Select file to update&quot;, select your file.</span></span>
4. <span data-ttu-id="12ba1-120">在这里，使用上下文菜单打开文件资源管理器并上传较新版本的 LOB 应用。</span><span class="sxs-lookup"><span data-stu-id="12ba1-120">From here, use the context menu to open your file explorer and upload the newer version of the LOB app.</span></span> <span data-ttu-id="12ba1-121">确保根据需要包含依赖项。</span><span class="sxs-lookup"><span data-stu-id="12ba1-121">Ensure to include dependencies as needed.</span></span>

<span data-ttu-id="12ba1-122">查看更多： [适用于 HoloLens 的 Intune 应用部署](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="12ba1-122">See more: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)</span></span>

## <a name="development-plan"></a><span data-ttu-id="12ba1-123">开发计划</span><span class="sxs-lookup"><span data-stu-id="12ba1-123">Development Plan</span></span>

<span data-ttu-id="12ba1-124">成功注册设备后，你现在准备好将更多 LOB 应用部署到你的设备。</span><span class="sxs-lookup"><span data-stu-id="12ba1-124">With your device successfully enrolled, you are now prepared to deploy more LOB apps to your devices.</span></span> <span data-ttu-id="12ba1-125">在本指南的有效期内，我们使用的是示例应用，但更可能希望使用为组织需求构建的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="12ba1-125">For the duration of this Guide, we're using a sample app, but it's more likely that you will want to use custom apps built for your organization's needs.</span></span>

<span data-ttu-id="12ba1-126">如果你已有 LOB 应用，则你已准备好通过 MDM [部署你的应用](https://docs.microsoft.com/hololens/app-deploy-intune)。</span><span class="sxs-lookup"><span data-stu-id="12ba1-126">If you already have a LOB app, then you're ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="12ba1-127">如果你希望采用其他方法，请查看 [HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) 的应用程序部署概述，了解将 LOB 应用部署到设备更多方法。</span><span class="sxs-lookup"><span data-stu-id="12ba1-127">If you'd prefer a different method, then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="12ba1-128">如果你尚未创建自己的 LOB 应用或仍在创建过程中，请查看我们的混合现实开发文档以开始设计和制作原型，或了解开始混合现实[](https://docs.microsoft.com/windows/mixed-reality/design/design)开发的核心概念。 [](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span><span class="sxs-lookup"><span data-stu-id="12ba1-128">If you've yet to create your own LOB app or are still in the process of creation, then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="support-plan"></a><span data-ttu-id="12ba1-129">支持计划</span><span class="sxs-lookup"><span data-stu-id="12ba1-129">Support Plan</span></span>

<span data-ttu-id="12ba1-130">支持计划是一项非常好的计划。</span><span class="sxs-lookup"><span data-stu-id="12ba1-130">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="12ba1-131">让某人或组接受有关 HoloLens 设备上注册过程的疑难解答培训，以及组织中 HoloLens 设备的常规使用非常有用。</span><span class="sxs-lookup"><span data-stu-id="12ba1-131">Having someone, or a group, trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="12ba1-132">为了允许用户更快地解决问题，我们建议按照与此顺序类似的方式处理你的升级过程：</span><span class="sxs-lookup"><span data-stu-id="12ba1-132">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="12ba1-133">支持人员。</span><span class="sxs-lookup"><span data-stu-id="12ba1-133">Your Support desk.</span></span>
2. <span data-ttu-id="12ba1-134">你的 HoloLens 专家团队</span><span class="sxs-lookup"><span data-stu-id="12ba1-134">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="12ba1-135">[HoloLens 文档](https://docs.microsoft.com/hololens/)  / [HoloLens 疑难解答文档](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="12ba1-135">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="12ba1-136">联系支持人员</span><span class="sxs-lookup"><span data-stu-id="12ba1-136">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a><span data-ttu-id="12ba1-137">设备管理</span><span class="sxs-lookup"><span data-stu-id="12ba1-137">Device Management</span></span>

<span data-ttu-id="12ba1-138">本指南讨论了如何设置移动设备管理 (MDM) 并用于设置一些设备配置，并应用设置以允许访问 Wi-Fi 证书和代理。</span><span class="sxs-lookup"><span data-stu-id="12ba1-138">This guide talked about setting up Mobile Device Management (MDM) and used it to set up some device configurations and apply settings to allow access in terms of Wi-Fi certificates and proxy.</span></span> <span data-ttu-id="12ba1-139">但是，MDM 还可用于通过 CSP 和策略应用设备限制。</span><span class="sxs-lookup"><span data-stu-id="12ba1-139">However, MDM can also be used to apply device restrictions via CSPs and Policies.</span></span>

<span data-ttu-id="12ba1-140">在许多情况下，设备可能会具有连接限制，Bluetooth、VPN、USB 甚至关闭对相机或麦克风的访问。</span><span class="sxs-lookup"><span data-stu-id="12ba1-140">In many cases, devices can have connectivity restrictions, such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="12ba1-141">如果你对其中任何一点感兴趣的内容，我们鼓励你阅读我们的 [常见设备限制页面](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="12ba1-141">If any of these interests you, then we encourage you to read our [common device restrictions page](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>

<span data-ttu-id="12ba1-142">可以使用其他更复杂的设备限制。</span><span class="sxs-lookup"><span data-stu-id="12ba1-142">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="12ba1-143">例如：</span><span class="sxs-lookup"><span data-stu-id="12ba1-143">Such as:</span></span>

- <span data-ttu-id="12ba1-144">使用 [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list)限制可在"设置"应用中查看的页面，允许用户仅访问需要调整的设置，例如更改其Wi-Fi连接。</span><span class="sxs-lookup"><span data-stu-id="12ba1-144">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list), allowing users to only access the settings they need to adjust, such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="12ba1-145">使用 [展](https://docs.microsoft.com/hololens/hololens-kiosk) 台模式限制向设备上用户呈现的 UI。</span><span class="sxs-lookup"><span data-stu-id="12ba1-145">Use [Kiosk mode](https://docs.microsoft.com/hololens/hololens-kiosk) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="12ba1-146">你可以将展台设置为显示单个应用，或者使用自定义起始页显示多个应用。</span><span class="sxs-lookup"><span data-stu-id="12ba1-146">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="12ba1-147">网亭还可以向不同的用户提供不同的体验。</span><span class="sxs-lookup"><span data-stu-id="12ba1-147">Kiosks can also present different experiences to different users.</span></span>
- <span data-ttu-id="12ba1-148">[Windows 应用程序控制 (WDAC) ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 来阻止特定应用或进程完全启动。</span><span class="sxs-lookup"><span data-stu-id="12ba1-148">[Windows Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="12ba1-149">如果你想要了解有关设备管理或设备限制的其他方法，请执行下一步并阅读我们的 [设备管理概述](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)。</span><span class="sxs-lookup"><span data-stu-id="12ba1-149">If you'd like to learn about additional methods of device management or device restrictions, then take the next step and read our [Device Management Overview](https://docs.microsoft.com/hololens/hololens-csp-policy-overview).</span></span>





