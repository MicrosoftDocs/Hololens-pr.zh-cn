---
title: 部署指南 - 使用 HoloLens 2 连接Dynamics 365 Guides - 维护
description: 了解如何使用 HoloLens 2 通过企业连接网络维护Dynamics 365 Guides。
keywords: HoloLens、管理、企业连接、Dynamics 365 Guides、AAD、Azure AD、MDM、移动设备管理
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
ms.openlocfilehash: 0176e816f167499574607bc16c8fbd6bde757daf
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636990"
---
# <a name="maintain---corporate-connected-guide"></a><span data-ttu-id="c2a7d-104">维护 - 企业连接指南</span><span class="sxs-lookup"><span data-stu-id="c2a7d-104">Maintain - Corporate Connected Guide</span></span>

## <a name="update-hololens"></a><span data-ttu-id="c2a7d-105">更新 HoloLens</span><span class="sxs-lookup"><span data-stu-id="c2a7d-105">Update HoloLens</span></span>

<span data-ttu-id="c2a7d-106">Microsoft 设计适用于企业的 Windows 更新以为 IT 管理员提供更多以 Windows 更新为中心的管理功能，例如对一组设备部署更新的功能，以及为安装更新而定义维护窗口的功能。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="c2a7d-107">管理更新的一种常用方法是将功能延迟 30 天。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-107">One popular method of managing updates is to do a feature deferral of 30 days.</span></span> <span data-ttu-id="c2a7d-108">这样，管理员可以更新和预览新功能，获得第一手知识，并告知支持人员任何新更改。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-108">This allows Admins to update and preview new features, gaining first hand knowledge and informing your support desk of any new changes.</span></span>

<span data-ttu-id="c2a7d-109">了解如何管理[HoloLens](/hololens/hololens-updates)更新，包括计划天数、计划时间，以及设置设备的活动小时数，以便它在工作时间之外更新。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-109">Learn how to [manage HoloLens updates](/hololens/hololens-updates), including scheduled days, scheduled time, and setting active hours on the device, so it will update outside of working hours.</span></span>

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a><span data-ttu-id="c2a7d-110">如何更新Dynamics 365 Guides (和其他应用商店应用) </span><span class="sxs-lookup"><span data-stu-id="c2a7d-110">How to update Dynamics 365 Guides (and other store apps)</span></span>

<span data-ttu-id="c2a7d-111">Dynamics 365 Guides是一In-Box应用，可通过 Microsoft Store 应用进行更新。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-111">Dynamics 365 Guides is an In-Box app, and can be updated through the Microsoft Store app.</span></span> <span data-ttu-id="c2a7d-112">对于通过 Microsoft Store 下载的所有应用，可以通过手动更新[Microsoft Store应用本身](/hololens/holographic-store-apps#update-apps)进行更新。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-112">For all apps that are downloaded through the Microsoft Store, they can be [updated through the Microsoft Store](/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="how-to-update-lob-apps"></a><span data-ttu-id="c2a7d-113">如何更新 LOB 应用</span><span class="sxs-lookup"><span data-stu-id="c2a7d-113">How to update LOB apps</span></span>

<span data-ttu-id="c2a7d-114">LOB 应用的更新方式与添加到 Intune 的方式相同。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-114">LOB apps can be updated in the same way they were added to Intune.</span></span> <span data-ttu-id="c2a7d-115">可以通过将版本号更高的新应用上传到现有应用配置，在 Intune 中更新应用。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-115">Apps can be updated in Intune by uploading the new app with a higher version number to the existing App configuration.</span></span> <span data-ttu-id="c2a7d-116">当设备同步到 Intune 时，它会观察到存在更新的应用版本，并且将下载更新的应用并替换旧应用。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-116">When the device syncs to Intune, it will observe that there is a newer app version and the newer app will be downloaded and replace the old app.</span></span>

1. <span data-ttu-id="c2a7d-117">若要上传较新的应用，请导航到 [MEM](https://endpoint.microsoft.com/#home)门户"应用  ->  "-">**应用**  ->  *""NameOfYourApp*  ->  **属性"。**</span><span class="sxs-lookup"><span data-stu-id="c2a7d-117">To upload the newer app, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** -> *TheNameOfYourApp* -> **Properties.**</span></span>
2. <span data-ttu-id="c2a7d-118">在"应用信息"旁边，选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="c2a7d-118">Next to App information, select **Edit.**</span></span>
3. <span data-ttu-id="c2a7d-119">对于"选择要 &quot; 更新的文件"的值 &quot; ，请选择文件。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-119">For the value of &quot;Select file to update&quot;, select your file.</span></span>
4. <span data-ttu-id="c2a7d-120">在此处，使用上下文菜单打开文件资源管理器并上传较新版本的 LOB 应用。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-120">From here, use the context menu to open your file explorer and upload the newer version of the LOB app.</span></span> <span data-ttu-id="c2a7d-121">确保根据需要包含依赖项。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-121">Ensure to include dependencies as needed.</span></span>

<span data-ttu-id="c2a7d-122">有关详细信息，请参阅[Intune 应用部署HoloLens](/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="c2a7d-122">See more: [Intune App Deployment for HoloLens](/hololens/app-deploy-intune)</span></span>

## <a name="development-plan"></a><span data-ttu-id="c2a7d-123">开发计划</span><span class="sxs-lookup"><span data-stu-id="c2a7d-123">Development Plan</span></span>

<span data-ttu-id="c2a7d-124">成功注册设备后，现在可以将更多 LOB 应用部署到设备。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-124">With your device successfully enrolled, you are now prepared to deploy more LOB apps to your devices.</span></span> <span data-ttu-id="c2a7d-125">在本指南的持续时间内，我们将使用示例应用，但更可能希望使用根据组织需求构建的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-125">For the duration of this Guide, we're using a sample app, but it's more likely that you will want to use custom apps built for your organization's needs.</span></span>

<span data-ttu-id="c2a7d-126">如果已有 LOB 应用，则可以通过 [MDM 部署应用](/hololens/app-deploy-intune)。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-126">If you already have a LOB app, then you're ready to [deploy your app through MDM](/hololens/app-deploy-intune).</span></span> <span data-ttu-id="c2a7d-127">如果希望使用不同的方法，请查看应用程序部署概述HoloLens 2了解将[](/hololens/app-deploy-overview)LOB 应用部署到设备的更多方法。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-127">If you'd prefer a different method, then review the [application deployment overview for HoloLens 2](/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="c2a7d-128">如果尚未创建自己的 LOB 应用或仍处于创建过程中，请查看我们的混合现实开发文档，开始设计和原型制作，或学习核心概念[](/windows/mixed-reality/design/design)以开始使用混合现实[开发](/windows/mixed-reality/discover/get-started-with-mr)。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-128">If you've yet to create your own LOB app or are still in the process of creation, then review our mixed reality development docs to [start designing and prototyping](/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="support-plan"></a><span data-ttu-id="c2a7d-129">支持计划</span><span class="sxs-lookup"><span data-stu-id="c2a7d-129">Support Plan</span></span>

<span data-ttu-id="c2a7d-130">制定支持计划是一项极佳的计划。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-130">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="c2a7d-131">让某人或一个组在设备上对注册过程进行故障排除HoloLens以及组织中对 HoloLens 设备的常规使用非常有用。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-131">Having someone, or a group, trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="c2a7d-132">为了使用户更快地解决其问题，我们建议以类似于此顺序的方式处理升级过程：</span><span class="sxs-lookup"><span data-stu-id="c2a7d-132">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="c2a7d-133">支持人员。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-133">Your Support desk.</span></span>
2. <span data-ttu-id="c2a7d-134">你的 HoloLens 专家团队</span><span class="sxs-lookup"><span data-stu-id="c2a7d-134">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="c2a7d-135">[HoloLens Docs](/hololens/)  / [HoloLens故障排除文档](/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="c2a7d-135">[HoloLens Docs](/hololens/) / [HoloLens Troubleshooting Docs](/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="c2a7d-136">联系支持人员</span><span class="sxs-lookup"><span data-stu-id="c2a7d-136">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a><span data-ttu-id="c2a7d-137">设备管理</span><span class="sxs-lookup"><span data-stu-id="c2a7d-137">Device Management</span></span>

<span data-ttu-id="c2a7d-138">本指南讨论了如何设置 Mobile 设备管理 (MDM) 并用于设置一些设备配置，并应用设置以允许访问Wi-Fi证书和代理。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-138">This guide talked about setting up Mobile Device Management (MDM) and used it to set up some device configurations and apply settings to allow access in terms of Wi-Fi certificates and proxy.</span></span> <span data-ttu-id="c2a7d-139">但是，MDM 还可用于通过 CSP 和策略应用设备限制。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-139">However, MDM can also be used to apply device restrictions via CSPs and Policies.</span></span>

<span data-ttu-id="c2a7d-140">在许多情况下，设备可能会受到连接限制，例如蓝牙 VPN、USB，甚至会关闭对相机或麦克风的访问。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-140">In many cases, devices can have connectivity restrictions, such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="c2a7d-141">如果你对上述任一内容感兴趣的内容，建议阅读常见的 [设备限制页](/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-141">If any of these interests you, then we encourage you to read our [common device restrictions page](/hololens/hololens-common-device-restrictions).</span></span>

<span data-ttu-id="c2a7d-142">可以使用其他更复杂的设备限制。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-142">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="c2a7d-143">如：</span><span class="sxs-lookup"><span data-stu-id="c2a7d-143">Such as:</span></span>

- <span data-ttu-id="c2a7d-144">通过使用[SettingsPageVisibility](/hololens/settings-uri-list)限制可在 设置 应用中查看的页面，允许用户仅访问需要调整的设置，例如更改Wi-Fi连接。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-144">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](/hololens/settings-uri-list), allowing users to only access the settings they need to adjust, such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="c2a7d-145">使用 [展台](/hololens/hololens-kiosk) 模式限制向设备上用户呈现的 UI。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-145">Use [Kiosk mode](/hololens/hololens-kiosk) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="c2a7d-146">可以将展台设置为显示单个应用，或者使用自定义起始页显示多个应用。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-146">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="c2a7d-147">展台还可以向不同的用户提供不同的体验。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-147">Kiosks can also present different experiences to different users.</span></span>
- <span data-ttu-id="c2a7d-148">[Windows应用程序控制 (WDAC) ，](/hololens/windows-defender-application-control-wdac)使特定应用或进程完全启动。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-148">[Windows Application Control (WDAC)](/hololens/windows-defender-application-control-wdac) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="c2a7d-149">若要了解设备管理或设备限制的其他方法，请执行下一步并阅读我们的设备管理 [概述](/hololens/hololens-csp-policy-overview)。</span><span class="sxs-lookup"><span data-stu-id="c2a7d-149">If you'd like to learn about additional methods of device management or device restrictions, then take the next step and read our [Device Management Overview](/hololens/hololens-csp-policy-overview).</span></span>





