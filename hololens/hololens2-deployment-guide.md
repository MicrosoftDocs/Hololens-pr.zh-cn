---
title: 外部客户端部署指南
description: 'HoloLens 2 外部客户端部署指南 (远程协助，作为示例) '
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
ms.openlocfilehash: c0ea468df2188700af408803ae1c55b9d0e4c763
ms.sourcegitcommit: ea5fa6c970756025b77c00b4ea600d60ce033106
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "11267998"
---
# <span data-ttu-id="740e3-103">使用远程协助将 HoloLens 2 部署到外部客户端</span><span class="sxs-lookup"><span data-stu-id="740e3-103">Deploying HoloLens 2 to External Clients with Remote Assist</span></span>

<span data-ttu-id="740e3-104">本文档可帮助 IT 专业人员规划并部署 HoloLens 2 设备，侧重于远程协助。</span><span class="sxs-lookup"><span data-stu-id="740e3-104">This document helps IT professions plan for and deploy HoloLens 2 devices with a focus on Remote Assist.</span></span> <span data-ttu-id="740e3-105">[了解有关远程协助的更多信息](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)。</span><span class="sxs-lookup"><span data-stu-id="740e3-105">[Learn more about Remote Assist](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).</span></span>

## <span data-ttu-id="740e3-106">方案说明</span><span class="sxs-lookup"><span data-stu-id="740e3-106">Scenario Description</span></span>

<span data-ttu-id="740e3-107">出于本文档的目的，Contoso 公司希望将 HoloLens 2 设备发运给外部客户端的工厂，以便短期或长期使用。</span><span class="sxs-lookup"><span data-stu-id="740e3-107">For the purpose of this document, Contoso Company wants to ship a HoloLens 2 device to an external client's plant for short-term or long-term use.</span></span> <span data-ttu-id="740e3-108">当客户端需要协助服务时，客户端将使用 Contoso 公司提供的凭据登录到 HoloLens 2 设备，并使用远程协助联系 Contoso 公司专家。</span><span class="sxs-lookup"><span data-stu-id="740e3-108">When the client needs assistance servicing machinery, the client will log into the HoloLens 2 device using credentials provided by Contoso Company and use Remote Assist to contact Contoso Company's experts.</span></span>

### <span data-ttu-id="740e3-109">此方案的要求</span><span class="sxs-lookup"><span data-stu-id="740e3-109">Requirements for this Scenario</span></span>

1. [<span data-ttu-id="740e3-110">Azure AD</span><span class="sxs-lookup"><span data-stu-id="740e3-110">Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. <span data-ttu-id="740e3-111">移动设备管理器 - 例如 [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span><span class="sxs-lookup"><span data-stu-id="740e3-111">Mobile Device Manager - such as [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span></span>
1. <span data-ttu-id="740e3-112">Remote Assist 许可证</span><span class="sxs-lookup"><span data-stu-id="740e3-112">Remote Assist License</span></span>
    1. [<span data-ttu-id="740e3-113">购买远程协助</span><span class="sxs-lookup"><span data-stu-id="740e3-113">Buy Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [<span data-ttu-id="740e3-114">试用远程协助</span><span class="sxs-lookup"><span data-stu-id="740e3-114">Trial Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <span data-ttu-id="740e3-115">常见问题</span><span class="sxs-lookup"><span data-stu-id="740e3-115">Common Concerns</span></span>

- [<span data-ttu-id="740e3-116">如何确保外部客户端无法相互通信</span><span class="sxs-lookup"><span data-stu-id="740e3-116">How to ensure that external clients do not have the ability to communicate with one another</span></span>](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [<span data-ttu-id="740e3-117">如何确保客户端无法访问公司资源</span><span class="sxs-lookup"><span data-stu-id="740e3-117">How to ensure that clients do not have access to company resources</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [<span data-ttu-id="740e3-118">如何限制应用</span><span class="sxs-lookup"><span data-stu-id="740e3-118">How to restrict apps</span></span>](#how-to-restrict-apps)
- [<span data-ttu-id="740e3-119">如何管理密码</span><span class="sxs-lookup"><span data-stu-id="740e3-119">How to manage passwords</span></span>](#how-to-manage-passwords)
- [<span data-ttu-id="740e3-120">如何确保客户端无法访问聊天历史记录</span><span class="sxs-lookup"><span data-stu-id="740e3-120">How to ensure that clients do not have access to chat history</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <span data-ttu-id="740e3-121">如何确保外部客户端无法相互通信</span><span class="sxs-lookup"><span data-stu-id="740e3-121">How to ensure that external clients do not have the ability to communicate with one another</span></span>

<span data-ttu-id="740e3-122">由于不支持远程协助 HoloLens 到 HoloLens 的呼叫，因此客户端可以搜索但无法相互通信。</span><span class="sxs-lookup"><span data-stu-id="740e3-122">Since Remote Assist HoloLens to HoloLens calls are not supported, clients are able to search for, but are unable to, communicate with one another.</span></span> <span data-ttu-id="740e3-123">为了进一步限制可以搜索和呼叫的客户端[](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide)，信息屏障可以限制客户端可以与谁通信。</span><span class="sxs-lookup"><span data-stu-id="740e3-123">To further restrict who clients can search for and call,  [Information barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) can restrict who a client can communicate with.</span></span> <span data-ttu-id="740e3-124">要考虑的另一个选项是使用 [作用域目录搜索](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span><span class="sxs-lookup"><span data-stu-id="740e3-124">Another option to consider is using [Scoped Directory Search](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span></span>

 > [!NOTE]
> <span data-ttu-id="740e3-125">由于启用了单一登录，因此使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)禁用浏览器非常重要。</span><span class="sxs-lookup"><span data-stu-id="740e3-125">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="740e3-126">如果外部客户端打开浏览器并使用 Web 版本的 Teams，则客户端将有权访问呼叫/聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="740e3-126">If an external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

### <span data-ttu-id="740e3-127">如何确保客户端无法访问公司资源</span><span class="sxs-lookup"><span data-stu-id="740e3-127">How to ensure that clients do not have access to company resources</span></span>

<span data-ttu-id="740e3-128">有两个选项需要考虑。</span><span class="sxs-lookup"><span data-stu-id="740e3-128">There are two options to consider.</span></span>

<span data-ttu-id="740e3-129">第一个选项是多层方法：</span><span class="sxs-lookup"><span data-stu-id="740e3-129">The first option is a multi-layer approach:</span></span>

1. <span data-ttu-id="740e3-130">仅分配用户所需的许可证。</span><span class="sxs-lookup"><span data-stu-id="740e3-130">Only assign licenses that the user requires.</span></span> <span data-ttu-id="740e3-131">如果未将 OneDrive、Outlook、SharePoint、Yammer 等分配给用户，则他/她将无法访问这些资源。</span><span class="sxs-lookup"><span data-stu-id="740e3-131">If you do not assign OneDrive, Outlook, SharePoint, Yammer, etc. to the user, he/she will not have access to those resources.</span></span> <span data-ttu-id="740e3-132">用户需要的唯一许可证是远程协助、Intune 和 AAD 许可证才能开始。</span><span class="sxs-lookup"><span data-stu-id="740e3-132">The only licenses the users will need is Remote Assist, Intune, and AAD licenses to begin.</span></span>
1. <span data-ttu-id="740e3-133">阻止 (应用程序，) 您不希望客户端访问的电子邮件 (请参阅如何限制 [应用程序](#how-to-restrict-apps)) 。</span><span class="sxs-lookup"><span data-stu-id="740e3-133">Block apps (such as email) that you don’t want clients to access (See [How to restrict apps](#how-to-restrict-apps)).</span></span>
1. <span data-ttu-id="740e3-134">不要与客户端共享用户名或密码。</span><span class="sxs-lookup"><span data-stu-id="740e3-134">Do NOT share usernames nor password with clients.</span></span> <span data-ttu-id="740e3-135">若要登录到 HoloLens 2，需要电子邮件和数字 PIN。</span><span class="sxs-lookup"><span data-stu-id="740e3-135">To log into the HoloLens 2, an email and numerical PIN is required.</span></span>

<span data-ttu-id="740e3-136">第二个选项是创建托管客户端的单独租户 (图像 1.1) 。</span><span class="sxs-lookup"><span data-stu-id="740e3-136">The second option is to create a separate tenant that hosts clients (see Image 1.1).</span></span>

**<span data-ttu-id="740e3-137">图像 1.1</span><span class="sxs-lookup"><span data-stu-id="740e3-137">Image 1.1</span></span>**

![服务租户映像](./images/hololens-service-tenant-image.png)

### <span data-ttu-id="740e3-139">如何限制应用</span><span class="sxs-lookup"><span data-stu-id="740e3-139">How to restrict apps</span></span>

<span data-ttu-id="740e3-140">[展台模式](https://docs.microsoft.com/hololens/hololens-kiosk) 和/或 [WDAC (Windows Defender应用程序 ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)) 限制应用程序的选项。</span><span class="sxs-lookup"><span data-stu-id="740e3-140">[Kiosk Mode](https://docs.microsoft.com/hololens/hololens-kiosk) and/or [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) are options for restricting applications.</span></span>

### <span data-ttu-id="740e3-141">如何管理密码</span><span class="sxs-lookup"><span data-stu-id="740e3-141">How to manage passwords</span></span>

1. <span data-ttu-id="740e3-142">删除密码过期。</span><span class="sxs-lookup"><span data-stu-id="740e3-142">Remove password expiration.</span></span> <span data-ttu-id="740e3-143">但是，这会增加帐户遭到入侵的可能性。</span><span class="sxs-lookup"><span data-stu-id="740e3-143">However, this increases the chance that that an account will be compromised.</span></span> <span data-ttu-id="740e3-144">NIST 密码建议是每 30-90 天更改一次密码。</span><span class="sxs-lookup"><span data-stu-id="740e3-144">NIST password recommendation is change passwords every 30-90 days.</span></span>
1. <span data-ttu-id="740e3-145">将 HoloLens 2 设备的密码过期时间延长 90 天。</span><span class="sxs-lookup"><span data-stu-id="740e3-145">Extend the password expiration for HoloLens 2 devices to exceed 90 days.</span></span>
1. <span data-ttu-id="740e3-146">设备应返回到 Contoso 以更改密码。</span><span class="sxs-lookup"><span data-stu-id="740e3-146">The devices should be returned to Contoso to change the passwords.</span></span> <span data-ttu-id="740e3-147">但是，如果设备预期在客户端中工作 90 天以上，这可能会导致问题。</span><span class="sxs-lookup"><span data-stu-id="740e3-147">However, this can cause issues if the devices are expected to be in the client's plant for 90+ days.</span></span>  
1. <span data-ttu-id="740e3-148">对于发送到多个客户端的设备，在将设备寄送到客户端之前重置密码。</span><span class="sxs-lookup"><span data-stu-id="740e3-148">For devices that are sent to multiple clients, reset passwords before shipping the device to clients.</span></span>

### <span data-ttu-id="740e3-149">如何确保客户端无法访问聊天历史记录</span><span class="sxs-lookup"><span data-stu-id="740e3-149">How to ensure that clients do not have access to chat history</span></span>

<span data-ttu-id="740e3-150">远程协助在每个会话后清除聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="740e3-150">Remote Assist clears chat history after each session.</span></span> <span data-ttu-id="740e3-151">但是，聊天历史记录将提供给 Microsoft Teams 用户。</span><span class="sxs-lookup"><span data-stu-id="740e3-151">However, the chat history will be available for the Microsoft Teams user.</span></span>

> [!NOTE]
> <span data-ttu-id="740e3-152">由于启用了单一登录，因此使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)禁用浏览器非常重要。</span><span class="sxs-lookup"><span data-stu-id="740e3-152">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="740e3-153">如果外部客户端打开浏览器并使用 Web 版本的 Teams，则客户端将有权访问呼叫/聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="740e3-153">If a external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

## <span data-ttu-id="740e3-154">一般部署建议和说明</span><span class="sxs-lookup"><span data-stu-id="740e3-154">General Deployment Recommendations and Instructions</span></span>

<span data-ttu-id="740e3-155">我们建议对 HoloLens 2 部署步骤执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="740e3-155">We recommend the following for HoloLens 2 deployment Steps:</span></span>

1. <span data-ttu-id="740e3-156">使用 [最新的 HoloLens 操作系统版本](https://aka.ms/hololens2download) 作为基准版本。</span><span class="sxs-lookup"><span data-stu-id="740e3-156">Use the [latest HoloLens OS release](https://aka.ms/hololens2download) as your baseline build.</span></span>
1. <span data-ttu-id="740e3-157">分配基于用户或基于设备的许可证：</span><span class="sxs-lookup"><span data-stu-id="740e3-157">Assign user-based or device-based licenses:</span></span>
    1. <span data-ttu-id="740e3-158">基于用户的许可证和基于设备的许可证都遵循以下步骤：</span><span class="sxs-lookup"><span data-stu-id="740e3-158">User-based and device-based licenses both follow the following steps:</span></span>
        1. <span data-ttu-id="740e3-159">[在 AAD 中创建组，并添加](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) HoloLens/RA 用户的成员。</span><span class="sxs-lookup"><span data-stu-id="740e3-159">[Create a group in AAD and add members](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) for HoloLens/RA users.</span></span>
        1. <span data-ttu-id="740e3-160">[向此组分配基于设备或基于](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 用户的许可证。</span><span class="sxs-lookup"><span data-stu-id="740e3-160">[Assign device-based or user-based licenses](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) to this group.</span></span>
        1. <span data-ttu-id="740e3-161"> (可选) 你可以面向 MDM 策略的组。</span><span class="sxs-lookup"><span data-stu-id="740e3-161">(Optional) You can target groups for MDM policies.</span></span>

1. <span data-ttu-id="740e3-162">设备应已加入租户的 AAD，自动 [注册](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，并通过自动引导 [进行配置](https://docs.microsoft.com/hololens/hololens2-autopilot)。</span><span class="sxs-lookup"><span data-stu-id="740e3-162">Devices should be AAD joined to your tenant, [Auto Enrolled](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm), and configured through [Auto Pilot](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
    1. <span data-ttu-id="740e3-163">请注意，设备上第一个用户将是设备所有者。</span><span class="sxs-lookup"><span data-stu-id="740e3-163">Please note that the first user on the device will be the device owner.</span></span>
    1. <span data-ttu-id="740e3-164">请注意，如果设备已加入 AAD，则执行加入的用户将成为设备所有者。</span><span class="sxs-lookup"><span data-stu-id="740e3-164">Please note that if the device is AAD joined, the user that performed the join is made device owner.</span></span>
    1. <span data-ttu-id="740e3-165">有关详细信息，请参阅 [设备所有者](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)。</span><span class="sxs-lookup"><span data-stu-id="740e3-165">For more, see [Device Owner](https://docs.microsoft.com/hololens/security-adminless-os#device-owner).</span></span>
1. <span data-ttu-id="740e3-166">[租户锁定](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 设备，以便它只能加入你的租户。</span><span class="sxs-lookup"><span data-stu-id="740e3-166">[Tenant lock](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) the device so that it can only joined your tenant.</span></span>
    1. <span data-ttu-id="740e3-167">**其他链接：**[租户锁定 CSP。](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)</span><span class="sxs-lookup"><span data-stu-id="740e3-167">**Additional Link:** [Tenant lock CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).</span></span>
1. <span data-ttu-id="740e3-168">使用全局分配的访问权限在此处配置 [展台](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)。</span><span class="sxs-lookup"><span data-stu-id="740e3-168">Configure kiosk using global assigned access to [here](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk).</span></span>
1. <span data-ttu-id="740e3-169">我们建议禁用以下可选 () 功能：</span><span class="sxs-lookup"><span data-stu-id="740e3-169">We recommend disabling the follow (optional) capabilities:</span></span>
    1. <span data-ttu-id="740e3-170">在此处将设备置于开发人员模式 [的能力](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)。</span><span class="sxs-lookup"><span data-stu-id="740e3-170">Ability to put the device into developer mode [here](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).</span></span>
    1. <span data-ttu-id="740e3-171">将 HoloLens 连接到电脑以复制日期的能力禁用[USB。](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)</span><span class="sxs-lookup"><span data-stu-id="740e3-171">Ability to connect the HoloLens to a PC to copy date [disable USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).</span></span>
       > [!NOTE]
        > <span data-ttu-id="740e3-172">如果你不想禁用 USB，但希望能够使用 USB 将预配包应用到设备，请按照此处列出的 [**说明操作**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)。</span><span class="sxs-lookup"><span data-stu-id="740e3-172">If you don’t want to disable USB but want the ability to apply a provisioning package to the device using USB, follow the instructions listed [**here**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).</span></span>

1. <span data-ttu-id="740e3-173">使用 [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 允许或黑色 HoloLens 2 设备上应用。</span><span class="sxs-lookup"><span data-stu-id="740e3-173">Use [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to allow or black apps on the HoloLens 2 device.</span></span>
1. <span data-ttu-id="740e3-174">将远程协助更新到最新版本，作为设置的一部分。</span><span class="sxs-lookup"><span data-stu-id="740e3-174">Update Remote Assist to the latest version as part of the setup.</span></span> <span data-ttu-id="740e3-175">有两个选项可进行此操作：</span><span class="sxs-lookup"><span data-stu-id="740e3-175">There are two options to do this:</span></span>
    1. <span data-ttu-id="740e3-176">这可以通过访问 Windows Microsoft **Store --> Remote Assist --> 应用完成**。</span><span class="sxs-lookup"><span data-stu-id="740e3-176">This can be done by going to Windows **Microsoft Store --> Remote Assist --> and Update App**.</span></span>
    1. <span data-ttu-id="740e3-177">另一个方法是让 HoloLens 2 在一夜之间保持插入状态以自动更新。</span><span class="sxs-lookup"><span data-stu-id="740e3-177">Another method is to leave the HoloLens 2 plugged in overnight for auto update.</span></span>
1. <span data-ttu-id="740e3-178">[禁用除网络](https://docs.microsoft.com/hololens/settings-uri-list) 设置以外的所有设置页面，以允许用户连接到客户端站点中的来宾网络。</span><span class="sxs-lookup"><span data-stu-id="740e3-178">[Disable all settings pages](https://docs.microsoft.com/hololens/settings-uri-list) except the network settings to allow users to connect to guest networks at client sites.</span></span>
1. [<span data-ttu-id="740e3-179">管理 HoloLens 更新</span><span class="sxs-lookup"><span data-stu-id="740e3-179">Manage HoloLens Updates</span></span>](https://docs.microsoft.com/hololens/hololens-updates)
    1. <span data-ttu-id="740e3-180">控制 [操作系统更新或](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) 允许自由流动的选项。</span><span class="sxs-lookup"><span data-stu-id="740e3-180">Option to [control OS updates](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) or allow to flow freely.</span></span>
1. <span data-ttu-id="740e3-181">[常见设备限制](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="740e3-181">[Common Device Restrictions](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>
