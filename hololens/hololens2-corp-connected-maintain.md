---
title: 部署指南–企业连接的 HoloLens 2 （含 Dynamics 365 指南）-维护
description: 了解如何在使用 Dynamics 365 指南的公司连接网络上维护 HoloLens 2 设备。
keywords: HoloLens，管理，企业连接，Dynamics 365 指南，AAD，Azure AD，MDM，移动设备管理
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308423"
---
# <a name="maintain---corporate-connected-guide"></a><span data-ttu-id="b9fa3-104">维护-企业连接指南</span><span class="sxs-lookup"><span data-stu-id="b9fa3-104">Maintain - Corporate Connected Guide</span></span>

## <a name="update-hololens"></a><span data-ttu-id="b9fa3-105">更新 HoloLens</span><span class="sxs-lookup"><span data-stu-id="b9fa3-105">Update HoloLens</span></span>

<span data-ttu-id="b9fa3-106">Microsoft 设计适用于企业的 Windows 更新以为 IT 管理员提供更多以 Windows 更新为中心的管理功能，例如对一组设备部署更新的功能，以及为安装更新而定义维护窗口的功能。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-106">Microsoft designed Windows Update for Business to provide IT administrators with additional Windows Update-centric management capabilities, such as the ability to deploy updates to groups of devices and to define maintenance windows for installing updates.</span></span>

<span data-ttu-id="b9fa3-107">管理更新的一种常用方法是将功能延迟为30天。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-107">One popular method of managing updates is to do a feature deferral of 30 days.</span></span> <span data-ttu-id="b9fa3-108">这样，管理员就可以更新和预览新功能，获得第一手知识，并通知支持人员进行任何新的更改。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-108">This allows Admins to update and preview new features, gaining first hand knowledge and informing your support desk of any new changes.</span></span>

<span data-ttu-id="b9fa3-109">了解如何 [管理 HoloLens 更新](https://docs.microsoft.com/hololens/hololens-updates)，包括计划的日期、计划的时间和在设备上设置活动时间，以便在工作时间之外进行更新。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-109">Learn how to [manage HoloLens updates](https://docs.microsoft.com/hololens/hololens-updates), including scheduled days, scheduled time, and setting active hours on the device, so it will update outside of working hours.</span></span>

## <a name="how-to-update-dynamics-365-guides-and-other-store-apps"></a><span data-ttu-id="b9fa3-110">如何 (和其他应用商店应用更新 Dynamics 365 指南) </span><span class="sxs-lookup"><span data-stu-id="b9fa3-110">How to update Dynamics 365 Guides (and other store apps)</span></span>

<span data-ttu-id="b9fa3-111">Dynamics 365 指南是一个 In-Box 的应用，可通过 Microsoft Store 应用进行更新。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-111">Dynamics 365 Guides is an In-Box app, and can be updated through the Microsoft Store app.</span></span> <span data-ttu-id="b9fa3-112">对于通过 Microsoft Store 下载的所有应用程序，可以手动 [通过 Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) 应用程序进行更新。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-112">For all apps that are downloaded through the Microsoft Store, they can be [updated through the Microsoft Store](https://docs.microsoft.com/hololens/holographic-store-apps#update-apps) app itself manually.</span></span>

## <a name="how-to-update-lob-apps"></a><span data-ttu-id="b9fa3-113">如何更新 LOB 应用</span><span class="sxs-lookup"><span data-stu-id="b9fa3-113">How to update LOB apps</span></span>

<span data-ttu-id="b9fa3-114">LOB 应用的更新方式与将其添加到 Intune 的方式相同。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-114">LOB apps can be updated in the same way they were added to Intune.</span></span> <span data-ttu-id="b9fa3-115">可以通过将具有更高版本号的新应用上传到现有应用配置，在 Intune 中更新应用。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-115">Apps can be updated in Intune by uploading the new app with a higher version number to the existing App configuration.</span></span> <span data-ttu-id="b9fa3-116">当设备同步到 Intune 时，会发现有一个较新的应用程序版本，将下载较新的应用程序并替换旧的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-116">When the device syncs to Intune, it will observe that there is a newer app version and the newer app will be downloaded and replace the old app.</span></span>

1. <span data-ttu-id="b9fa3-117">若要上传更新的应用，请导航到 "[内存门户](https://endpoint.microsoft.com/#home)  ->  **应用**-> 所有 **应用**" "  ->  *TheNameOfYourApp*"  ->  **属性。**</span><span class="sxs-lookup"><span data-stu-id="b9fa3-117">To upload the newer app, navigate to the [MEM portal](https://endpoint.microsoft.com/#home) -> **Apps** -> All **apps** -> *TheNameOfYourApp* -> **Properties.**</span></span>
2. <span data-ttu-id="b9fa3-118">在 "应用信息" 旁边，选择 " **编辑"。**</span><span class="sxs-lookup"><span data-stu-id="b9fa3-118">Next to App information, select **Edit.**</span></span>
3. <span data-ttu-id="b9fa3-119">对于 " &quot; 选择要更新的文件" 的值 &quot; ，请选择文件。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-119">For the value of &quot;Select file to update&quot;, select your file.</span></span>
4. <span data-ttu-id="b9fa3-120">从这里，使用上下文菜单打开文件资源管理器，并上传新版本的 LOB 应用。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-120">From here, use the context menu to open your file explorer and upload the newer version of the LOB app.</span></span> <span data-ttu-id="b9fa3-121">确保根据需要包含依赖项。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-121">Ensure to include dependencies as needed.</span></span>

<span data-ttu-id="b9fa3-122">了解更多： [适用于 HoloLens 的 Intune 应用部署](https://docs.microsoft.com/hololens/app-deploy-intune)</span><span class="sxs-lookup"><span data-stu-id="b9fa3-122">See more: [Intune App Deployment for HoloLens](https://docs.microsoft.com/hololens/app-deploy-intune)</span></span>

## <a name="development-plan"></a><span data-ttu-id="b9fa3-123">开发计划</span><span class="sxs-lookup"><span data-stu-id="b9fa3-123">Development Plan</span></span>

<span data-ttu-id="b9fa3-124">成功注册设备后，你现在已准备好将更多 LOB 应用部署到设备。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-124">With your device successfully enrolled, you are now prepared to deploy more LOB apps to your devices.</span></span> <span data-ttu-id="b9fa3-125">在本指南中，我们使用的是示例应用程序，但更有可能需要使用为组织需求构建的自定义应用。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-125">For the duration of this Guide, we're using a sample app, but it's more likely that you will want to use custom apps built for your organization's needs.</span></span>

<span data-ttu-id="b9fa3-126">如果你已有 LOB 应用，则可以 [通过 MDM 部署](https://docs.microsoft.com/hololens/app-deploy-intune)你的应用。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-126">If you already have a LOB app, then you're ready to [deploy your app through MDM](https://docs.microsoft.com/hololens/app-deploy-intune).</span></span> <span data-ttu-id="b9fa3-127">如果希望使用不同的方法，请查看 [HoloLens 2 的应用程序部署概述](https://docs.microsoft.com/hololens/app-deploy-overview) ，了解将 LOB 应用程序部署到设备的更多方法。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-127">If you'd prefer a different method, then review the [application deployment overview for HoloLens 2](https://docs.microsoft.com/hololens/app-deploy-overview) to learn more methods of deploying your LOB app to your devices.</span></span>

<span data-ttu-id="b9fa3-128">如果你尚未创建自己的 LOB 应用或仍处于创建过程中，请查看我们的混合现实开发文档，以[开始设计和构建原型](https://docs.microsoft.com/windows/mixed-reality/design/design)，或了解有关[混合现实开发入门](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)的核心概念。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-128">If you've yet to create your own LOB app or are still in the process of creation, then review our mixed reality development docs to [start designing and prototyping](https://docs.microsoft.com/windows/mixed-reality/design/design) or learn the core concepts to [get started with mixed reality development.](https://docs.microsoft.com/windows/mixed-reality/discover/get-started-with-mr)</span></span>

## <a name="support-plan"></a><span data-ttu-id="b9fa3-129">支持计划</span><span class="sxs-lookup"><span data-stu-id="b9fa3-129">Support Plan</span></span>

<span data-ttu-id="b9fa3-130">支持计划是一个不错的做法。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-130">A support plan is an excellent thing to have in place.</span></span> <span data-ttu-id="b9fa3-131">让某个人或某个组训练了对 HoloLens 设备上的注册过程进行故障排除，并对你的组织中的 HoloLens 设备进行一般使用非常有用。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-131">Having someone, or a group, trained up on troubleshooting the enrollment process on HoloLens devices and also general use of the HoloLens device within your organization is useful.</span></span> <span data-ttu-id="b9fa3-132">为了使用户能够更快地解决其问题，我们建议以类似于此顺序的方式处理升级过程：</span><span class="sxs-lookup"><span data-stu-id="b9fa3-132">In order to allow your users to have the faster resolution of their issues, we suggest that your escalation process is handled in a similar manner to this order:</span></span>

1. <span data-ttu-id="b9fa3-133">你的支持人员。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-133">Your Support desk.</span></span>
2. <span data-ttu-id="b9fa3-134">HoloLens 专家团队</span><span class="sxs-lookup"><span data-stu-id="b9fa3-134">Your HoloLens Expert team</span></span>
3. <span data-ttu-id="b9fa3-135">[HoloLens 文档](https://docs.microsoft.com/hololens/)  / [HoloLens 疑难解答文档](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span><span class="sxs-lookup"><span data-stu-id="b9fa3-135">[HoloLens Docs](https://docs.microsoft.com/hololens/) / [HoloLens Troubleshooting Docs](https://docs.microsoft.com/hololens/hololens-troubleshooting)</span></span>
4. [<span data-ttu-id="b9fa3-136">联系支持人员</span><span class="sxs-lookup"><span data-stu-id="b9fa3-136">Contact Support</span></span>](https://support.serviceshub.microsoft.com/supportforbusiness/create?sapId=e9391227-fa6d-927b-0fff-f96288631b8f)

## <a name="device-management"></a><span data-ttu-id="b9fa3-137">设备管理</span><span class="sxs-lookup"><span data-stu-id="b9fa3-137">Device Management</span></span>

<span data-ttu-id="b9fa3-138">本指南讨论 (MDM) 设置移动设备管理，并使用它来设置某些设备配置，并应用设置以允许 Wi-Fi 证书和代理进行访问。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-138">This guide talked about setting up Mobile Device Management (MDM) and used it to set up some device configurations and apply settings to allow access in terms of Wi-Fi certificates and proxy.</span></span> <span data-ttu-id="b9fa3-139">但是，也可以使用 MDM 通过 Csp 和策略应用设备限制。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-139">However, MDM can also be used to apply device restrictions via CSPs and Policies.</span></span>

<span data-ttu-id="b9fa3-140">在许多情况下，设备可能具有连接限制，如 Bluetooth、VPN、USB，甚至关闭对照相机或麦克风的访问。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-140">In many cases, devices can have connectivity restrictions, such as Bluetooth, VPN, USB or even turning off access to the camera or microphone.</span></span> <span data-ttu-id="b9fa3-141">如果你感兴趣，我们建议你阅读 [常见的设备限制页](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-141">If any of these interests you, then we encourage you to read our [common device restrictions page](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>

<span data-ttu-id="b9fa3-142">你还可以使用其他更复杂的设备限制。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-142">There are other more complex device restrictions you can use.</span></span> <span data-ttu-id="b9fa3-143">如：</span><span class="sxs-lookup"><span data-stu-id="b9fa3-143">Such as:</span></span>

- <span data-ttu-id="b9fa3-144">通过使用 [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list)限制可以在 "设置" 应用中查看的页面，允许用户仅访问他们需要调整的设置，例如更改其 Wi-Fi 连接。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-144">Limiting the pages that can be viewed in the Settings app by using [SettingsPageVisibility](https://docs.microsoft.com/hololens/settings-uri-list), allowing users to only access the settings they need to adjust, such as changing their Wi-Fi connection.</span></span>
- <span data-ttu-id="b9fa3-145">使用 [展台模式](https://docs.microsoft.com/hololens/hololens-kiosk) 将向用户显示的 UI 限制为设备上的用户。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-145">Use [Kiosk mode](https://docs.microsoft.com/hololens/hololens-kiosk) to limit the UI presented to users on a device.</span></span> <span data-ttu-id="b9fa3-146">可以通过使用自定义起始页将网亭设置为显示单个应用程序或多个应用程序。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-146">You can set Kiosks to show a single app, or multiple apps with a custom start page.</span></span> <span data-ttu-id="b9fa3-147">网亭还可以向不同用户提供不同的体验。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-147">Kiosks can also present different experiences to different users.</span></span>
- <span data-ttu-id="b9fa3-148">[Windows 应用程序控制 (WDAC) ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) ，以使特定的应用程序或进程完全启动。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-148">[Windows Application Control (WDAC)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to keep specific apps or processes from launching entirely.</span></span>

<span data-ttu-id="b9fa3-149">如果你想要了解设备管理或设备限制的其他方法，请执行下一步，并阅读我们的 [设备管理概述](https://docs.microsoft.com/hololens/hololens-csp-policy-overview)。</span><span class="sxs-lookup"><span data-stu-id="b9fa3-149">If you'd like to learn about additional methods of device management or device restrictions, then take the next step and read our [Device Management Overview](https://docs.microsoft.com/hololens/hololens-csp-policy-overview).</span></span>





