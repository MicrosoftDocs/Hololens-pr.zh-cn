---
title: 外部客户端部署指南
description: '适用于使用远程协助作为示例的适用于外部客户 (端的 HoloLens 2 部署指南) '
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
ms.openlocfilehash: 56930ceea05cd5713b9c7eb57e0967a9d0cd4988
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308382"
---
# <a name="deploying-hololens-2-to-external-clients-with-remote-assist"></a><span data-ttu-id="ba4a2-103">将 HoloLens 2 部署到具有远程协助的外部客户端</span><span class="sxs-lookup"><span data-stu-id="ba4a2-103">Deploying HoloLens 2 to External Clients with Remote Assist</span></span>

<span data-ttu-id="ba4a2-104">本指南可帮助 IT 专业人员在其组织中部署 Microsoft HoloLens 2 设备：</span><span class="sxs-lookup"><span data-stu-id="ba4a2-104">This guide helps IT professionals with the following goals deploy Microsoft HoloLens 2 devices in their organization:</span></span>

1. <span data-ttu-id="ba4a2-105">Cloud connect HoloLens 2 设备</span><span class="sxs-lookup"><span data-stu-id="ba4a2-105">Cloud connect HoloLens 2 devices</span></span>
1. <span data-ttu-id="ba4a2-106">向外部客户端贷款 HoloLens 2 设备以供使用</span><span class="sxs-lookup"><span data-stu-id="ba4a2-106">Loan HoloLens 2 devices to external clients for use</span></span>
1. <span data-ttu-id="ba4a2-107">安全借出设备</span><span class="sxs-lookup"><span data-stu-id="ba4a2-107">Secure loaned devices</span></span>

<span data-ttu-id="ba4a2-108">本指南将提供 [一般的 hololens 2 部署建议](#general-deployment-recommendations-and-instructions) ，适用于大多数 hololens 2 部署方案，以及客户在部署外部使用的远程协助时的 [常见问题](#common-concerns) 。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-108">This guide will provide [general HoloLens 2 deployment recommendations](#general-deployment-recommendations-and-instructions) that is applicable to most HoloLens 2 deployment scenarios and [common concerns](#common-concerns) that customers have when deploying Remote Assist for external use.</span></span>

## <a name="scenario-description"></a><span data-ttu-id="ba4a2-109">方案描述</span><span class="sxs-lookup"><span data-stu-id="ba4a2-109">Scenario Description</span></span>

<span data-ttu-id="ba4a2-110">出于本文档的目的，Contoso 公司希望将一个 HoloLens 2 设备寄送到外部客户端的工厂，以便进行短期或长期使用。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-110">For the purpose of this document, Contoso Company wants to ship a HoloLens 2 device to an external client's plant for short-term or long-term use.</span></span> <span data-ttu-id="ba4a2-111">如果客户端需要帮助服务设备，则客户端将使用 Contoso 公司提供的凭据登录到 HoloLens 2 设备，并使用远程协助联系 Contoso 公司的专家。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-111">When the client needs assistance servicing machinery, the client will log into the HoloLens 2 device using credentials provided by Contoso Company and use Remote Assist to contact Contoso Company's experts.</span></span>

<span data-ttu-id="ba4a2-112">[在此处](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist)了解有关远程协助的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-112">Learn more about Remote Assist [here](https://docs.microsoft.com/hololens/hololens2-cloud-connected-overview#learn-about-remote-assist).</span></span>

### <a name="requirements-for-this-scenario"></a><span data-ttu-id="ba4a2-113">此方案的要求</span><span class="sxs-lookup"><span data-stu-id="ba4a2-113">Requirements for this Scenario</span></span>

1. [<span data-ttu-id="ba4a2-114">Azure AD</span><span class="sxs-lookup"><span data-stu-id="ba4a2-114">Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)
1. <span data-ttu-id="ba4a2-115">Mobile Device Manager-例如 [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span><span class="sxs-lookup"><span data-stu-id="ba4a2-115">Mobile Device Manager - such as [Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)</span></span>
1. <span data-ttu-id="ba4a2-116">远程协助许可证</span><span class="sxs-lookup"><span data-stu-id="ba4a2-116">Remote Assist License</span></span>
    1. [<span data-ttu-id="ba4a2-117">购买远程协助</span><span class="sxs-lookup"><span data-stu-id="ba4a2-117">Buy Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/buy-remote-assist)
    1. [<span data-ttu-id="ba4a2-118">试用远程协助</span><span class="sxs-lookup"><span data-stu-id="ba4a2-118">Trial Remote Assist</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/try-remote-assist)

## <a name="common-concerns"></a><span data-ttu-id="ba4a2-119">常见问题</span><span class="sxs-lookup"><span data-stu-id="ba4a2-119">Common Concerns</span></span>

- [<span data-ttu-id="ba4a2-120">如何确保外部客户端不能相互通信</span><span class="sxs-lookup"><span data-stu-id="ba4a2-120">How to ensure that external clients do not have the ability to communicate with one another</span></span>](#how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another)
- [<span data-ttu-id="ba4a2-121">如何确保客户端无法访问公司资源</span><span class="sxs-lookup"><span data-stu-id="ba4a2-121">How to ensure that clients do not have access to company resources</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-company-resources)
- [<span data-ttu-id="ba4a2-122">如何限制应用</span><span class="sxs-lookup"><span data-stu-id="ba4a2-122">How to restrict apps</span></span>](#how-to-restrict-apps)
- [<span data-ttu-id="ba4a2-123">如何管理密码</span><span class="sxs-lookup"><span data-stu-id="ba4a2-123">How to manage passwords</span></span>](#how-to-manage-passwords)
- [<span data-ttu-id="ba4a2-124">如何确保客户端无权访问聊天历史记录</span><span class="sxs-lookup"><span data-stu-id="ba4a2-124">How to ensure that clients do not have access to chat history</span></span>](#how-to-ensure-that-clients-do-not-have-access-to-chat-history)

### <a name="how-to-ensure-that-external-clients-do-not-have-the-ability-to-communicate-with-one-another"></a><span data-ttu-id="ba4a2-125">如何确保外部客户端不能相互通信</span><span class="sxs-lookup"><span data-stu-id="ba4a2-125">How to ensure that external clients do not have the ability to communicate with one another</span></span>

<span data-ttu-id="ba4a2-126">由于不支持远程协助 HoloLens 到 HoloLens 的调用，因此客户端能够搜索，但无法进行相互通信。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-126">Since Remote Assist HoloLens to HoloLens calls are not supported, clients are able to search for, but are unable to, communicate with one another.</span></span> <span data-ttu-id="ba4a2-127">为了进一步限制客户端可以搜索和调用的人员，  [信息障碍](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) 可限制客户端可以与之通信。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-127">To further restrict who clients can search for and call,  [Information barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers?view=o365-worldwide) can restrict who a client can communicate with.</span></span> <span data-ttu-id="ba4a2-128">要考虑的另一个选项是使用 [范围的目录搜索](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span><span class="sxs-lookup"><span data-stu-id="ba4a2-128">Another option to consider is using [Scoped Directory Search](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)</span></span>

 > [!NOTE]
> <span data-ttu-id="ba4a2-129">由于启用了单一登录，因此请务必使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)禁用浏览器。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-129">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="ba4a2-130">如果外部客户端打开浏览器并使用 web 版本的团队，则客户端将有权访问呼叫/聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-130">If an external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-company-resources"></a><span data-ttu-id="ba4a2-131">如何确保客户端无法访问公司资源</span><span class="sxs-lookup"><span data-stu-id="ba4a2-131">How to ensure that clients do not have access to company resources</span></span>

<span data-ttu-id="ba4a2-132">需要考虑两个选项。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-132">There are two options to consider.</span></span>

<span data-ttu-id="ba4a2-133">第一个选项是多层方法：</span><span class="sxs-lookup"><span data-stu-id="ba4a2-133">The first option is a multi-layer approach:</span></span>

1. <span data-ttu-id="ba4a2-134">仅分配用户需要的许可证。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-134">Only assign licenses that the user requires.</span></span> <span data-ttu-id="ba4a2-135">如果没有为用户分配 OneDrive、Outlook、SharePoint、Yammer 等，则他/她将无法访问这些资源。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-135">If you do not assign OneDrive, Outlook, SharePoint, Yammer, etc. to the user, he/she will not have access to those resources.</span></span> <span data-ttu-id="ba4a2-136">用户需要的唯一许可证是远程协助、Intune 和 AAD 许可证开始。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-136">The only licenses the users will need is Remote Assist, Intune, and AAD licenses to begin.</span></span>
1. <span data-ttu-id="ba4a2-137">阻止应用程序 (例如不希望客户端访问的电子邮件)  (请参阅 [如何) 限制应用](#how-to-restrict-apps) 。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-137">Block apps (such as email) that you don’t want clients to access (See [How to restrict apps](#how-to-restrict-apps)).</span></span>
1. <span data-ttu-id="ba4a2-138">不要将用户名和密码与客户端共享。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-138">Do NOT share usernames nor password with clients.</span></span> <span data-ttu-id="ba4a2-139">若要登录到 HoloLens 2，需要电子邮件和数字 PIN。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-139">To log into the HoloLens 2, an email and numerical PIN is required.</span></span>

<span data-ttu-id="ba4a2-140">第二种方法是创建一个承载客户端的单独租户 (参阅图像 1.1) 。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-140">The second option is to create a separate tenant that hosts clients (see Image 1.1).</span></span>

<span data-ttu-id="ba4a2-141">**图像1。1**</span><span class="sxs-lookup"><span data-stu-id="ba4a2-141">**Image 1.1**</span></span>

![服务租户映像](./images/hololens-service-tenant-image.png)

### <a name="how-to-restrict-apps"></a><span data-ttu-id="ba4a2-143">如何限制应用</span><span class="sxs-lookup"><span data-stu-id="ba4a2-143">How to restrict apps</span></span>

<span data-ttu-id="ba4a2-144">[展台模式](https://docs.microsoft.com/hololens/hololens-kiosk) 和/或 [WDAC (Windows Defender 应用程序控制) ](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 是用于限制应用程序的选项。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-144">[Kiosk Mode](https://docs.microsoft.com/hololens/hololens-kiosk) and/or [WDAC (Windows Defender Application Control)](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) are options for restricting applications.</span></span>

### <a name="how-to-manage-passwords"></a><span data-ttu-id="ba4a2-145">如何管理密码</span><span class="sxs-lookup"><span data-stu-id="ba4a2-145">How to manage passwords</span></span>

1. <span data-ttu-id="ba4a2-146">删除密码过期。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-146">Remove password expiration.</span></span> <span data-ttu-id="ba4a2-147">但是，这会增加帐户泄露的可能性。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-147">However, this increases the chance that that an account will be compromised.</span></span> <span data-ttu-id="ba4a2-148">NIST 密码建议每30-90 天更改一次密码。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-148">NIST password recommendation is change passwords every 30-90 days.</span></span>
1. <span data-ttu-id="ba4a2-149">将 HoloLens 2 设备的密码过期时间延长到超过90天。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-149">Extend the password expiration for HoloLens 2 devices to exceed 90 days.</span></span>
1. <span data-ttu-id="ba4a2-150">设备应返回到 Contoso 以更改密码。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-150">The devices should be returned to Contoso to change the passwords.</span></span> <span data-ttu-id="ba4a2-151">但是，如果设备预期在客户端的工厂中超过90天，这可能会导致问题。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-151">However, this can cause issues if the devices are expected to be in the client's plant for 90+ days.</span></span>  
1. <span data-ttu-id="ba4a2-152">对于发送到多个客户端的设备，在将设备发送到客户端之前重置密码。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-152">For devices that are sent to multiple clients, reset passwords before shipping the device to clients.</span></span>

### <a name="how-to-ensure-that-clients-do-not-have-access-to-chat-history"></a><span data-ttu-id="ba4a2-153">如何确保客户端无权访问聊天历史记录</span><span class="sxs-lookup"><span data-stu-id="ba4a2-153">How to ensure that clients do not have access to chat history</span></span>

<span data-ttu-id="ba4a2-154">远程协助在每个会话之后清除聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-154">Remote Assist clears chat history after each session.</span></span> <span data-ttu-id="ba4a2-155">但是，聊天历史记录将可供 Microsoft 团队用户使用。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-155">However, the chat history will be available for the Microsoft Teams user.</span></span>

> [!NOTE]
> <span data-ttu-id="ba4a2-156">由于启用了单一登录，因此请务必使用 [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac)禁用浏览器。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-156">Since single sign on is enabled, it is important to disable the browser using [**WDAC**](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac).</span></span> <span data-ttu-id="ba4a2-157">如果外部客户端打开浏览器并使用 web 版本的团队，则客户端将有权访问呼叫/聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-157">If a external client opens the browser and uses the web version of Teams, the client will have access to call/chat history.</span></span>

## <a name="general-deployment-recommendations-and-instructions"></a><span data-ttu-id="ba4a2-158">一般部署建议和说明</span><span class="sxs-lookup"><span data-stu-id="ba4a2-158">General Deployment Recommendations and Instructions</span></span>

<span data-ttu-id="ba4a2-159">建议为 HoloLens 2 部署步骤执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ba4a2-159">We recommend the following for HoloLens 2 deployment Steps:</span></span>

1. <span data-ttu-id="ba4a2-160">使用 [最新的 HOLOLENS OS 版本](https://aka.ms/hololens2download) 作为基准构建。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-160">Use the [latest HoloLens OS release](https://aka.ms/hololens2download) as your baseline build.</span></span>
1. <span data-ttu-id="ba4a2-161">分配基于用户或基于设备的许可证：</span><span class="sxs-lookup"><span data-stu-id="ba4a2-161">Assign user-based or device-based licenses:</span></span>
    1. <span data-ttu-id="ba4a2-162">基于用户和基于设备的许可证都遵循以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ba4a2-162">User-based and device-based licenses both follow the following steps:</span></span>
        1. <span data-ttu-id="ba4a2-163">[在 AAD 中创建一个组，并](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) 为 HOLOLENS/RA 用户添加成员。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-163">[Create a group in AAD and add members](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#create-a-basic-group-and-add-members) for HoloLens/RA users.</span></span>
        1. <span data-ttu-id="ba4a2-164">[将基于设备或基于用户的许可证分配](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) 给此组。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-164">[Assign device-based or user-based licenses](https://docs.microsoft.com/azure/active-directory/enterprise-users/licensing-groups-assign#:~:text=In%20this%20article%201%20Assign%20the%20required%20licenses,3%20Check%20for%20license%20problems%20and%20resolve%20them) to this group.</span></span>
        1. <span data-ttu-id="ba4a2-165"> (可选) 你可以将 MDM 策略的组作为目标。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-165">(Optional) You can target groups for MDM policies.</span></span>

1. <span data-ttu-id="ba4a2-166">设备应通过 AAD 加入你的租户、 [自动注册](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm)，并通过 [自动试验](https://docs.microsoft.com/hololens/hololens2-autopilot)进行配置。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-166">Devices should be AAD joined to your tenant, [Auto Enrolled](https://docs.microsoft.com/hololens/hololens-enroll-mdm#auto-enrollment-in-mdm), and configured through [Auto Pilot](https://docs.microsoft.com/hololens/hololens2-autopilot).</span></span>
    1. <span data-ttu-id="ba4a2-167">请注意，设备上的第一个用户将是设备所有者。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-167">Please note that the first user on the device will be the device owner.</span></span>
    1. <span data-ttu-id="ba4a2-168">请注意，如果设备已加入 AAD，则执行联接的用户将成为设备所有者。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-168">Please note that if the device is AAD joined, the user that performed the join is made device owner.</span></span>
    1. <span data-ttu-id="ba4a2-169">有关详细信息，请参阅 [设备所有者](https://docs.microsoft.com/hololens/security-adminless-os#device-owner)。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-169">For more, see [Device Owner](https://docs.microsoft.com/hololens/security-adminless-os#device-owner).</span></span>
1. <span data-ttu-id="ba4a2-170">[租户锁定](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) 设备，以便它只能加入你的租户。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-170">[Tenant lock](https://docs.microsoft.com/hololens/hololens-release-notes#tenantlockdown-csp-and-autopilot) the device so that it can only joined your tenant.</span></span>
    1. <span data-ttu-id="ba4a2-171">**附加链接：** [租户锁定 CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp)。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-171">**Additional Link:** [Tenant lock CSP](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp).</span></span>
1. <span data-ttu-id="ba4a2-172">使用 [此处](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk)的全局分配访问权限配置展台。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-172">Configure kiosk using global assigned access to [here](https://docs.microsoft.com/hololens/hololens-global-assigned-access-kiosk).</span></span>
1. <span data-ttu-id="ba4a2-173">建议禁用以下 (可选) 功能：</span><span class="sxs-lookup"><span data-stu-id="ba4a2-173">We recommend disabling the follow (optional) capabilities:</span></span>
    1. <span data-ttu-id="ba4a2-174">可以将设备置于开发[人员模式。](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock)</span><span class="sxs-lookup"><span data-stu-id="ba4a2-174">Ability to put the device into developer mode [here](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowdeveloperunlock).</span></span>
    1. <span data-ttu-id="ba4a2-175">能够将 HoloLens 连接到 PC 以复制日期 [禁用 USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection)。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-175">Ability to connect the HoloLens to a PC to copy date [disable USB](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection).</span></span>
       > [!NOTE]
        > <span data-ttu-id="ba4a2-176">如果不想禁用 USB，但希望能够使用 USB 将设置包应用于设备，请按照 [**此处**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)列出的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-176">If you don’t want to disable USB but want the ability to apply a provisioning package to the device using USB, follow the instructions listed [**here**](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage).</span></span>

1. <span data-ttu-id="ba4a2-177">使用 [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) 允许或阻止 HoloLens 2 设备上的应用。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-177">Use [WDAC](https://docs.microsoft.com/hololens/windows-defender-application-control-wdac) to allow or block apps on the HoloLens 2 device.</span></span>
1. <span data-ttu-id="ba4a2-178">在安装过程中将远程协助更新到最新版本。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-178">Update Remote Assist to the latest version as part of the setup.</span></span> <span data-ttu-id="ba4a2-179">可以通过两种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="ba4a2-179">There are two options to do this:</span></span>
    1. <span data-ttu-id="ba4a2-180">这可以通过转到 Windows **Microsoft Store--> 远程协助--> 和更新应用** 来完成。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-180">This can be done by going to Windows **Microsoft Store --> Remote Assist --> and Update App**.</span></span>
    1. <span data-ttu-id="ba4a2-181">[ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) -默认情况下启用自动应用更新。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-181">[ApplicationManagement/AllowAppStoreAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) - which allows automatic app updates - is enabled by default.</span></span> <span data-ttu-id="ba4a2-182">保持设备的连接以接收更新。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-182">Keep the device plugged in to receive updates.</span></span>
1. <span data-ttu-id="ba4a2-183">禁用除网络设置以外的[所有设置页](https://docs.microsoft.com/hololens/settings-uri-list)，以允许用户在客户端站点连接到来宾网络。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-183">[Disable all settings pages](https://docs.microsoft.com/hololens/settings-uri-list) except the network settings to allow users to connect to guest networks at client sites.</span></span>
1. [<span data-ttu-id="ba4a2-184">管理 HoloLens 更新</span><span class="sxs-lookup"><span data-stu-id="ba4a2-184">Manage HoloLens Updates</span></span>](https://docs.microsoft.com/hololens/hololens-updates)
    1. <span data-ttu-id="ba4a2-185">[控制 OS 更新](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings)或允许自由流动的选项。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-185">Option to [control OS updates](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure#create-and-assign-update-rings) or allow to flow freely.</span></span>
1. <span data-ttu-id="ba4a2-186">[常见设备限制](https://docs.microsoft.com/hololens/hololens-common-device-restrictions)。</span><span class="sxs-lookup"><span data-stu-id="ba4a2-186">[Common Device Restrictions](https://docs.microsoft.com/hololens/hololens-common-device-restrictions).</span></span>
