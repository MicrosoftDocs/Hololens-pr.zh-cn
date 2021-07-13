---
title: 外部客户端部署指南
description: '远程辅助HoloLens 2外部客户端 (部署指南作为示例) '
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: medium
ms.date: 1/12/2021
ms.custom: ''
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: acf4b5d730b9a7eee2dedfad2bb3f866931d7455
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636939"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a><span data-ttu-id="1615b-103">使用 HoloLens 2 部署到外部Remote Assist</span><span class="sxs-lookup"><span data-stu-id="1615b-103">Deploying HoloLens 2 to External Clients with Remote Assist</span></span>

<span data-ttu-id="1615b-104">本指南可帮助 IT 专业人员实现以下目标，Microsoft HoloLens 2 台设备部署：</span><span class="sxs-lookup"><span data-stu-id="1615b-104">This guide helps IT professionals with the following goals deploy Microsoft HoloLens 2 devices in their organization:</span></span>

1. <span data-ttu-id="1615b-105">云HoloLens 2连接</span><span class="sxs-lookup"><span data-stu-id="1615b-105">Cloud connect HoloLens 2 devices</span></span>
1. <span data-ttu-id="1615b-106">将HoloLens 2设备贷款给外部客户端以使用</span><span class="sxs-lookup"><span data-stu-id="1615b-106">Loan HoloLens 2 devices to external clients for use</span></span>
1. <span data-ttu-id="1615b-107">保护已贷款设备</span><span class="sxs-lookup"><span data-stu-id="1615b-107">Secure loaned devices</span></span>

<span data-ttu-id="1615b-108">本指南将提供[一般HoloLens 2](#general-deployment-recommendations-and-instructions)部署建议，这些建议适用于大多数 HoloLens 2部署方案，以及客户在部署外部Remote Assist时常见的问题[](#common-concerns)。</span><span class="sxs-lookup"><span data-stu-id="1615b-108">This guide will provide [general HoloLens 2 deployment recommendations](#general-deployment-recommendations-and-instructions) that is applicable to most HoloLens 2 deployment scenarios and [common concerns](#common-concerns) that customers have when deploying Remote Assist for external use.</span></span>

## <a name="scenario-description"></a><span data-ttu-id="1615b-109">方案描述</span><span class="sxs-lookup"><span data-stu-id="1615b-109">Scenario Description</span></span>

<span data-ttu-id="1615b-110">就本文档而言，Contoso 公司希望将HoloLens 2设备运送到外部客户端的工厂，以便短期或长期使用。</span><span class="sxs-lookup"><span data-stu-id="1615b-110">For the purpose of this document, Contoso Company wants to ship a HoloLens 2 device to an external client's plant for short-term or long-term use.</span></span> <span data-ttu-id="1615b-111">当客户端需要维护机器的帮助时，客户端将使用 Contoso 公司提供的凭据登录到 HoloLens 2 设备，并使用 Remote Assist 联系 Contoso 公司专家。</span><span class="sxs-lookup"><span data-stu-id="1615b-111">When the client needs assistance servicing machinery, the client will log into the HoloLens 2 device using credentials provided by Contoso Company and use Remote Assist to contact Contoso Company's experts.</span></span>

<span data-ttu-id="1615b-112">在此处详细了解[Remote Assist。](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)</span><span class="sxs-lookup"><span data-stu-id="1615b-112">Learn more about Remote Assist [here](/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).</span></span>

### <a name="requirements-for-this-scenario"></a><span data-ttu-id="1615b-113">此方案的要求</span><span class="sxs-lookup"><span data-stu-id="1615b-113">Requirements for this Scenario</span></span>

1. <span data-ttu-id="1615b-114">Azure AD</span><span class="sxs-lookup"><span data-stu-id="1615b-114">[Azure AD](/azure/active-directory/fundamentals/active-directory-whatis)</span></span>
1. <span data-ttu-id="1615b-115">移动设备管理器 - 例如 [Intune](/mem/intune/fundamentals/free-trial-sign-up)</span><span class="sxs-lookup"><span data-stu-id="1615b-115">Mobile Device Manager - such as [Intune](/mem/intune/fundamentals/free-trial-sign-up)</span></span>
1. <span data-ttu-id="1615b-116">Remote Assist许可证</span><span class="sxs-lookup"><span data-stu-id="1615b-116">Remote Assist License</span></span>
    1. [<span data-ttu-id="1615b-117">购买Remote Assist</span><span class="sxs-lookup"><span data-stu-id="1615b-117">Buy Remote Assist</span></span>](/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [<span data-ttu-id="1615b-118">试用Remote Assist</span><span class="sxs-lookup"><span data-stu-id="1615b-118">Trial Remote Assist</span></span>](/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a><span data-ttu-id="1615b-119">常见问题</span><span class="sxs-lookup"><span data-stu-id="1615b-119">Common Concerns</span></span>

- [<span data-ttu-id="1615b-120">如何确保外部客户端无法相互通信</span><span class="sxs-lookup"><span data-stu-id="1615b-120">How to ensure that external clients do not have the ability to communicate with one another</span></span>](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [<span data-ttu-id="1615b-121">如何确保客户端无法访问公司资源</span><span class="sxs-lookup"><span data-stu-id="1615b-121">How to ensure that clients do not have access to company resources</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [<span data-ttu-id="1615b-122">如何限制应用</span><span class="sxs-lookup"><span data-stu-id="1615b-122">How to restrict apps</span></span>](#how-to-restrict-apps)
- [<span data-ttu-id="1615b-123">如何管理密码</span><span class="sxs-lookup"><span data-stu-id="1615b-123">How to manage passwords</span></span>](#how-to-manage-passwords)
- [<span data-ttu-id="1615b-124">如何确保客户端无法访问聊天历史记录</span><span class="sxs-lookup"><span data-stu-id="1615b-124">How to ensure that clients do not have access to chat history</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a><span data-ttu-id="1615b-125">如何确保外部客户端无法相互通信</span><span class="sxs-lookup"><span data-stu-id="1615b-125">How to ensure that external clients do not have the ability to communicate with one another</span></span>

<span data-ttu-id="1615b-126">由于Remote Assist HoloLens HoloLens调用，因此客户端能够搜索但无法相互通信。</span><span class="sxs-lookup"><span data-stu-id="1615b-126">Since Remote Assist HoloLens to HoloLens calls are not supported, clients are able to search for, but are unable to, communicate with one another.</span></span> <span data-ttu-id="1615b-127">为了进一步限制客户端可以搜索和调用谁[](/microsoft-365/compliance/information-barriers)，信息屏障可以限制客户端可以与谁通信。</span><span class="sxs-lookup"><span data-stu-id="1615b-127">To further restrict who clients can search for and call,  [Information barriers](/microsoft-365/compliance/information-barriers) can restrict who a client can communicate with.</span></span> <span data-ttu-id="1615b-128">要考虑的另一个选项是使用 [作用域目录搜索](/MicrosoftTeams/teams-scoped-directory-search)</span><span class="sxs-lookup"><span data-stu-id="1615b-128">Another option to consider is using [Scoped Directory Search](/MicrosoftTeams/teams-scoped-directory-search)</span></span>

 > [!NOTE]
> <span data-ttu-id="1615b-129">由于已启用单一登录，因此使用 [**WDAC**](/hololens/windows-defender-application-control-wdac)禁用浏览器非常重要。</span><span class="sxs-lookup"><span data-stu-id="1615b-129">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="1615b-130">如果外部客户端打开浏览器并使用 web 版本的 Teams，则客户端将有权访问呼叫/聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="1615b-130">If an external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a><span data-ttu-id="1615b-131">如何确保客户端无法访问公司资源</span><span class="sxs-lookup"><span data-stu-id="1615b-131">How to ensure that clients do not have access to company resources</span></span>

<span data-ttu-id="1615b-132">有两个选项需要考虑。</span><span class="sxs-lookup"><span data-stu-id="1615b-132">There are two options to consider.</span></span>

<span data-ttu-id="1615b-133">第一个选项是多层方法：</span><span class="sxs-lookup"><span data-stu-id="1615b-133">The first option is a multi-layer approach:</span></span>

1. <span data-ttu-id="1615b-134">仅分配用户所需的许可证。</span><span class="sxs-lookup"><span data-stu-id="1615b-134">Only assign licenses that the user requires.</span></span> <span data-ttu-id="1615b-135">如果未向用户分配OneDrive、Outlook、SharePoint、Yammer等，则他/她将无法访问这些资源。</span><span class="sxs-lookup"><span data-stu-id="1615b-135">If you do not assign OneDrive, Outlook, SharePoint, Yammer, etc. to the user, he/she will not have access to those resources.</span></span> <span data-ttu-id="1615b-136">用户所需的唯一许可证是Remote Assist Intune 和 AAD 许可证。</span><span class="sxs-lookup"><span data-stu-id="1615b-136">The only licenses the users will need is Remote Assist, Intune, and AAD licenses to begin.</span></span>
1. <span data-ttu-id="1615b-137">阻止 (，例如) 不希望客户端访问的电子邮件 [ (请参阅如何](#how-to-restrict-apps) 限制) 。</span><span class="sxs-lookup"><span data-stu-id="1615b-137">Block apps (such as email) that you don’t want clients to access (See [How to restrict apps](#how-to-restrict-apps)).</span></span>
1. <span data-ttu-id="1615b-138">请勿与客户端共享用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="1615b-138">Do NOT share usernames nor password with clients.</span></span> <span data-ttu-id="1615b-139">若要登录到HoloLens 2，需要电子邮件和数字 PIN。</span><span class="sxs-lookup"><span data-stu-id="1615b-139">To log into the HoloLens 2, an email and numerical PIN is required.</span></span>

<span data-ttu-id="1615b-140">第二个选项是创建托管客户端的单独租户， (映像 1.1) 。</span><span class="sxs-lookup"><span data-stu-id="1615b-140">The second option is to create a separate tenant that hosts clients (see Image 1.1).</span></span>

<span data-ttu-id="1615b-141">**图像 1.1**</span><span class="sxs-lookup"><span data-stu-id="1615b-141">**Image 1.1**</span></span>

![服务租户映像](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a><span data-ttu-id="1615b-143">如何限制应用</span><span class="sxs-lookup"><span data-stu-id="1615b-143">How to restrict apps</span></span>

<span data-ttu-id="1615b-144">[展台模式](/hololens/hololens-kiosk)和/或[WDAC (Windows Defender应用程序控制) ](/hololens/windows-defender-application-control-wdac)是限制应用程序的选项。</span><span class="sxs-lookup"><span data-stu-id="1615b-144">[Kiosk Mode](/hololens/hololens-kiosk) and/or [WDAC (Windows Defender Application Control)](/hololens/windows-defender-application-control-wdac) are options for restricting applications.</span></span>

### <a name="how-to-manage-passwords"></a><span data-ttu-id="1615b-145">如何管理密码</span><span class="sxs-lookup"><span data-stu-id="1615b-145">How to manage passwords</span></span>

1. <span data-ttu-id="1615b-146">删除密码过期。</span><span class="sxs-lookup"><span data-stu-id="1615b-146">Remove password expiration.</span></span> <span data-ttu-id="1615b-147">但是，这会增加帐户遭到入侵的可能性。</span><span class="sxs-lookup"><span data-stu-id="1615b-147">However, this increases the chance that an account will be compromised.</span></span> <span data-ttu-id="1615b-148">NIST 密码建议是每 30-90 天更改一次密码。</span><span class="sxs-lookup"><span data-stu-id="1615b-148">NIST password recommendation is change passwords every 30-90 days.</span></span>
1. <span data-ttu-id="1615b-149">将设备的密码HoloLens 2超过 90 天。</span><span class="sxs-lookup"><span data-stu-id="1615b-149">Extend the password expiration for HoloLens 2 devices to exceed 90 days.</span></span>
1. <span data-ttu-id="1615b-150">设备应返回到 Contoso 以更改密码。</span><span class="sxs-lookup"><span data-stu-id="1615b-150">The devices should be returned to Contoso to change the passwords.</span></span> <span data-ttu-id="1615b-151">但是，如果设备预期在客户端的工厂中工作 90 天以上，则这可能会导致问题。</span><span class="sxs-lookup"><span data-stu-id="1615b-151">However, this can cause issues if the devices are expected to be in the client's plant for 90+ days.</span></span>  
1. <span data-ttu-id="1615b-152">对于发送到多个客户端的设备，在将设备寄送到客户端之前重置密码。</span><span class="sxs-lookup"><span data-stu-id="1615b-152">For devices that are sent to multiple clients, reset passwords before shipping the device to clients.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a><span data-ttu-id="1615b-153">如何确保客户端无法访问聊天历史记录</span><span class="sxs-lookup"><span data-stu-id="1615b-153">How to ensure that clients do not have access to chat history</span></span>

<span data-ttu-id="1615b-154">Remote Assist会话后清除聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="1615b-154">Remote Assist clears chat history after each session.</span></span> <span data-ttu-id="1615b-155">但是，聊天历史记录将可供Microsoft Teams用户使用。</span><span class="sxs-lookup"><span data-stu-id="1615b-155">However, the chat history will be available for the Microsoft Teams user.</span></span>

> [!NOTE]
> <span data-ttu-id="1615b-156">由于已启用单一登录，因此使用 [**WDAC**](/hololens/windows-defender-application-control-wdac)禁用浏览器非常重要。</span><span class="sxs-lookup"><span data-stu-id="1615b-156">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="1615b-157">如果外部客户端打开浏览器并使用 web 版本的 Teams，则客户端将有权访问呼叫/聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="1615b-157">If a external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

## <a name="general-deployment-recommendations-and-instructions"></a><span data-ttu-id="1615b-158">常规部署推荐和说明</span><span class="sxs-lookup"><span data-stu-id="1615b-158">General Deployment Recommendations and Instructions</span></span>

<span data-ttu-id="1615b-159">对于部署步骤，HoloLens 2以下内容：</span><span class="sxs-lookup"><span data-stu-id="1615b-159">We recommend the following for HoloLens 2 deployment Steps:</span></span>

1. <span data-ttu-id="1615b-160">使用[最新的 HoloLens OS 版本](https://aka.ms/hololens2download)作为基线版本。</span><span class="sxs-lookup"><span data-stu-id="1615b-160">Use the [latest HoloLens OS release](https://aka.ms/hololens2download) as your baseline build.</span></span>
1. <span data-ttu-id="1615b-161">分配基于用户或基于设备的许可证：</span><span class="sxs-lookup"><span data-stu-id="1615b-161">Assign user-based or device-based licenses:</span></span>
    1. <span data-ttu-id="1615b-162">基于用户的许可证和基于设备的许可证都遵循以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1615b-162">User-based and device-based licenses both follow the following steps:</span></span>
        1. <span data-ttu-id="1615b-163">[在 AAD 中创建组，并添加HoloLens/RA](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members)用户的成员。</span><span class="sxs-lookup"><span data-stu-id="1615b-163">[Create a group in AAD and add members](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) for HoloLens/RA users.</span></span>
        1. <span data-ttu-id="1615b-164">[将基于设备或基于用户的许可证分配到](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 此组。</span><span class="sxs-lookup"><span data-stu-id="1615b-164">[Assign device-based or user-based licenses](/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) to this group.</span></span>
        1. <span data-ttu-id="1615b-165"> (可选) 可以针对 MDM 策略的组。</span><span class="sxs-lookup"><span data-stu-id="1615b-165">(Optional) You can target groups for MDM policies.</span></span>

1. <span data-ttu-id="1615b-166">设备应已加入租户的 AAD，自动 [注册](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，并通过自动试点 [进行配置](/hololens/hololens2-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="1615b-166">Devices should be AAD joined to your tenant, [Auto Enrolled](/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm), and configured through [Auto Pilot](/hololens/hololens2-autopilot).</span></span>
    1. <span data-ttu-id="1615b-167">请注意，设备上的第一个用户将是设备所有者。</span><span class="sxs-lookup"><span data-stu-id="1615b-167">Please note that the first user on the device will be the device owner.</span></span>
    1. <span data-ttu-id="1615b-168">请注意，如果设备已加入 AAD，则执行联接的用户将成为设备所有者。</span><span class="sxs-lookup"><span data-stu-id="1615b-168">Please note that if the device is AAD joined, the user that performed the join is made device owner.</span></span>
    1. <span data-ttu-id="1615b-169">有关详细信息，请参阅 [设备所有者](/hololens/security-adminless-os#device-owner)。</span><span class="sxs-lookup"><span data-stu-id="1615b-169">For more, see [Device Owner](/hololens/security-adminless-os#device-owner).</span></span>
1. <span data-ttu-id="1615b-170">[租户锁定](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 设备，以便它只能加入你的租户。</span><span class="sxs-lookup"><span data-stu-id="1615b-170">[Tenant lock](/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) the device so that it can only joined your tenant.</span></span>
    1. <span data-ttu-id="1615b-171">**其他链接：租户**[锁定 CSP](/windows/client-management/mdm/tenantlockdown-csp)。</span><span class="sxs-lookup"><span data-stu-id="1615b-171">**Additional Link:** [Tenant lock CSP](/windows/client-management/mdm/tenantlockdown-csp).</span></span>
1. <span data-ttu-id="1615b-172">使用此处 的全局分配访问权限配置 [展台](/hololens/hololens-global-assigned-access-kiosk)。</span><span class="sxs-lookup"><span data-stu-id="1615b-172">Configure kiosk using global assigned access to [here](/hololens/hololens-global-assigned-access-kiosk).</span></span>
1. <span data-ttu-id="1615b-173">建议禁用以下可选 () 功能：</span><span class="sxs-lookup"><span data-stu-id="1615b-173">We recommend disabling the follow (optional) capabilities:</span></span>
    1. <span data-ttu-id="1615b-174">能够在此处将设备置于开发人员 [模式](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)。</span><span class="sxs-lookup"><span data-stu-id="1615b-174">Ability to put the device into developer mode [here](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).</span></span>
    1. <span data-ttu-id="1615b-175">能够将 HoloLens连接到电脑以复制日期禁用[USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)。</span><span class="sxs-lookup"><span data-stu-id="1615b-175">Ability to connect the HoloLens to a PC to copy date [disable USB](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).</span></span>
       > [!NOTE]
        > <span data-ttu-id="1615b-176">如果不想禁用 USB，但希望能够使用 USB 将预配包应用到设备，请按照此处列出的 [**说明进行操作**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)。</span><span class="sxs-lookup"><span data-stu-id="1615b-176">If you don’t want to disable USB but want the ability to apply a provisioning package to the device using USB, follow the instructions listed [**here**](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).</span></span>

1. <span data-ttu-id="1615b-177">使用[WDAC](/hololens/windows-defender-application-control-wdac)允许或阻止设备上HoloLens 2应用。</span><span class="sxs-lookup"><span data-stu-id="1615b-177">Use [WDAC](/hololens/windows-defender-application-control-wdac) to allow or block apps on the HoloLens 2 device.</span></span>
1. <span data-ttu-id="1615b-178">在Remote Assist更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="1615b-178">Update Remote Assist to the latest version as part of the setup.</span></span> <span data-ttu-id="1615b-179">有两个选项可以这样做：</span><span class="sxs-lookup"><span data-stu-id="1615b-179">There are two options to do this:</span></span>
    1. <span data-ttu-id="1615b-180">为此，可以Windows Microsoft Store **--> Remote Assist --> 更新应用**。</span><span class="sxs-lookup"><span data-stu-id="1615b-180">This can be done by going to Windows **Microsoft Store --> Remote Assist --> and Update App**.</span></span>
    1. <span data-ttu-id="1615b-181">[ApplicationManagement/AllowAppStoreAutoUpdate（](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) 允许自动应用更新）默认启用。</span><span class="sxs-lookup"><span data-stu-id="1615b-181">[ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) - which allows automatic app updates - is enabled by default.</span></span> <span data-ttu-id="1615b-182">让设备保持插入状态以接收更新。</span><span class="sxs-lookup"><span data-stu-id="1615b-182">Keep the device plugged in to receive updates.</span></span>
1. <span data-ttu-id="1615b-183">[禁用除网络设置](/hololens/settings-uri-list) 之外的所有设置页，以允许用户连接到客户端站点中的来宾网络。</span><span class="sxs-lookup"><span data-stu-id="1615b-183">[Disable all settings pages](/hololens/settings-uri-list) except the network settings to allow users to connect to guest networks at client sites.</span></span>
1. [<span data-ttu-id="1615b-184">管理HoloLens更新</span><span class="sxs-lookup"><span data-stu-id="1615b-184">Manage HoloLens Updates</span></span>](/hololens/hololens-updates)
    1. <span data-ttu-id="1615b-185">控制 [OS 更新或](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) 允许自由流动的选项。</span><span class="sxs-lookup"><span data-stu-id="1615b-185">Option to [control OS updates](/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) or allow to flow freely.</span></span>
1. <span data-ttu-id="1615b-186">[常见设备限制](/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="1615b-186">[Common Device Restrictions](/hololens/hololens-common-device-restrictions).</span></span>
