---
title: 部署指南-Cloud 通过远程辅助功能在规模上部署 HoloLens 2 部署-准备
description: 如何准备通过连接到云的网络注册 HoloLens 设备
keywords: HoloLens、管理、云连接、远程协助、AAD、Azure AD、MDM、移动设备管理
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.date: 12/04/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 0e9222df2c387fab8f61a585d3a7f3966b9ecd31
ms.sourcegitcommit: 8e2c268733adce2662bf320cf96ccfea5919425e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "11196270"
---
# <span data-ttu-id="bc016-104">准备-云连接指南</span><span class="sxs-lookup"><span data-stu-id="bc016-104">Prepare - Cloud connected Guide</span></span>

<span data-ttu-id="bc016-105">在本文末尾，你将设置 AAD、MDM 以及了解有关使用 AAD 帐户和网络要求的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bc016-105">By the end of this article you will have set up AAD, MDM, and understand more about using AAD accounts and network requirements.</span></span> <span data-ttu-id="bc016-106">本指南的此部分将帮助你和你的组织准备将 HoloLens 2 部署到云并使用 Dynamics 365 远程协助。</span><span class="sxs-lookup"><span data-stu-id="bc016-106">This section of the guide will help you and your organization get prepared to deploy HoloLens 2 to the cloud and use Dynamics 365 Remote Assist.</span></span> <span data-ttu-id="bc016-107">它将对你的基础结构的每个部分的重要性进行比较，并提供指南的链接，以帮助你根据需要设置这些片段。</span><span class="sxs-lookup"><span data-stu-id="bc016-107">It will go over the importance of each piece of your infrastructure as well as providing links to guides to help you set up those pieces as needed.</span></span>

## <span data-ttu-id="bc016-108">基础结构基础</span><span class="sxs-lookup"><span data-stu-id="bc016-108">Infrastructure Essentials</span></span>

<span data-ttu-id="bc016-109">对于个人和企业部署方案，MDM 系统是部署和管理 Windows 10 全息版设备所需的基本基础结构。</span><span class="sxs-lookup"><span data-stu-id="bc016-109">For both personal and corporate deployment scenarios, an MDM system is the essential infrastructure required to deploy and manage Windows 10 Holographic devices.</span></span> <span data-ttu-id="bc016-110">Azure AD Premium 订阅建议作为标识提供程序，并且需要用于支持某些功能。</span><span class="sxs-lookup"><span data-stu-id="bc016-110">An Azure AD premium subscription is recommended as an identity provider and required to support certain capabilities.</span></span>

### <span data-ttu-id="bc016-111">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bc016-111">Azure Active Directory</span></span>

<span data-ttu-id="bc016-112">Azure AD 是一项基于云的目录服务，可提供标识和访问管理。</span><span class="sxs-lookup"><span data-stu-id="bc016-112">Azure AD is a cloud-based directory service that provides identity and access management.</span></span> <span data-ttu-id="bc016-113">使用 Microsoft Office 365 或 Intune 的组织已使用了三个版本：免费、高级 P1 和 Premium P2 (请参阅 [Azure Active Directory 版本](https://azure.microsoft.com/documentation/articles/active-directory-editions)。 ) 所有版本都支持 azure AD 设备注册，但需要高级 P1 才能启用在本指南中将使用的 MDM 自动注册。</span><span class="sxs-lookup"><span data-stu-id="bc016-113">Organizations that use Microsoft Office 365 or Intune are already using Azure AD, which has three editions: Free, Premium P1, and Premium P2 (see [Azure Active Directory editions](https://azure.microsoft.com/documentation/articles/active-directory-editions).) All editions support Azure AD device registration, but Premium P1 is required to enable MDM auto-enrollment which we will be using in this guide later.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc016-114">将 Azure Active Directory 用作 HoloLens 设备不支持本地广告联接非常重要。</span><span class="sxs-lookup"><span data-stu-id="bc016-114">It is essential to have an Azure Active Directory as HoloLens devices do not support on-premises AD join.</span></span> <span data-ttu-id="bc016-115">如果你不&#39;t 已设置 Azure Active Directory，请按照此链接中的说明开始操作，并 [在 Azure Active Directory 中创建新租户](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)。</span><span class="sxs-lookup"><span data-stu-id="bc016-115">If you don&#39;t already have an Azure Active Directory set up follow the instructions in this link to get started and [Create a new tenant in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).</span></span>

## <span data-ttu-id="bc016-116">标识管理</span><span class="sxs-lookup"><span data-stu-id="bc016-116">Identity Management</span></span>

<span data-ttu-id="bc016-117">员工只能使用一个帐户来初始化一个设备，因此它&#39;s 强制您的组织控制首先启用哪个帐户。</span><span class="sxs-lookup"><span data-stu-id="bc016-117">Employees can use only one account to initialize a device so it&#39;s imperative that your organization controls which account is enabled first.</span></span> <span data-ttu-id="bc016-118">所选帐户将确定由谁来控制设备，并影响管理功能。</span><span class="sxs-lookup"><span data-stu-id="bc016-118">The account chosen will determine who controls the device and influence your management capabilities.</span></span>

<span data-ttu-id="bc016-119">在本指南中，我们选择为使用的 [标识](https://docs.microsoft.com/hololens/hololens-identity) ，我们将使用 AAD 帐户或 Azure Active Directory 帐户。</span><span class="sxs-lookup"><span data-stu-id="bc016-119">In this guide we have chosen that for the [Identity](https://docs.microsoft.com/hololens/hololens-identity) used we will use AAD accounts, or Azure Active Directory accounts.</span></span> <span data-ttu-id="bc016-120">我们希望使用的 AAD 帐户有多大好处，例如：</span><span class="sxs-lookup"><span data-stu-id="bc016-120">There are several benefits to AAD accounts we would like to use, such as:</span></span>

- <span data-ttu-id="bc016-121">员工使用其 Azure AD 帐户在 Azure AD 中注册设备，并自动将其注册到组织&#39;s MDM 解决方案 (AAD + MDM-需要 Azure AD Premium) 。</span><span class="sxs-lookup"><span data-stu-id="bc016-121">Employees use their Azure AD account to register the device in Azure AD and automatically enroll it with the organization&#39;s MDM solution (AAD+MDM – requires Azure AD Premium).</span></span>
- <span data-ttu-id="bc016-122">AAD 帐户支持 [单一登录](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)。</span><span class="sxs-lookup"><span data-stu-id="bc016-122">AAD accounts support [Single Sign On](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span> <span data-ttu-id="bc016-123">当用户登录到远程协助时，将识别来自已登录 AAD 用户的身份，并且用户将登录到应用以简化体验。</span><span class="sxs-lookup"><span data-stu-id="bc016-123">When a user signs into Remote Assist, their Identity from the signed in AAD user will be recognized and the user will be signed into the app for a streamlined experience.</span></span>
- <span data-ttu-id="bc016-124">AAD 帐户通过[Windows Hello 企业版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)提供其他[身份验证选项](https://docs.microsoft.com/hololens/hololens-identity)。</span><span class="sxs-lookup"><span data-stu-id="bc016-124">AAD accounts have additional [authentication options](https://docs.microsoft.com/hololens/hololens-identity) via [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification).</span></span> <span data-ttu-id="bc016-125">除了虹膜登录用户之外，还可以从另一台设备登录或使用 FIDO 安全密钥。</span><span class="sxs-lookup"><span data-stu-id="bc016-125">In addition to Iris log-in users can sign in from another device or use FIDO security keys.</span></span>

### <span data-ttu-id="bc016-126">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="bc016-126">Mobile Device Management</span></span>

<span data-ttu-id="bc016-127">Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)是企业移动性 + 安全性的一部分，是一个基于云的 MDM 系统，用于管理连接到你的租户的设备。</span><span class="sxs-lookup"><span data-stu-id="bc016-127">Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune), part of the Enterprise Mobility + Security, is a cloud-based MDM system that manages devices connected to your tenant.</span></span> <span data-ttu-id="bc016-128">与 Office 365 一样，Intune 使用 Azure AD 进行身份管理，因此员工使用相同凭据在 Intune 中注册设备以登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="bc016-128">Like Office 365, Intune uses Azure AD for identity management, so employees use the same credentials to enroll devices in Intune that they use to sign into Office 365.</span></span> <span data-ttu-id="bc016-129">Intune 还支持运行其他操作系统（如 iOS 和 Android）的设备，以提供完整的 MDM 解决方案。</span><span class="sxs-lookup"><span data-stu-id="bc016-129">Intune also supports devices that run other operating systems, such as iOS and Android, to provide a complete MDM solution.</span></span> <span data-ttu-id="bc016-130">出于本指南的目的，我们&#39;重点介绍使用 Intune 在使用 HoloLens 2 的比例下启用云部署。</span><span class="sxs-lookup"><span data-stu-id="bc016-130">For the purposes of this guide, we&#39;ll be focusing on using Intune for enabling a cloud deployment at scale with HoloLens 2.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc016-131">具有移动设备管理的必要条件。</span><span class="sxs-lookup"><span data-stu-id="bc016-131">It is essential to have Mobile Device Management.</span></span> <span data-ttu-id="bc016-132">如果您没有设置&#39;请按照本指南进行设置，并 [开始使用 Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)。</span><span class="sxs-lookup"><span data-stu-id="bc016-132">If you don&#39;t already have it set up follow this guide and [Get started with Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up).</span></span>

> [!NOTE]
> <span data-ttu-id="bc016-133">多个 MDM 系统支持 Windows 10 并且大部分都支持个人和公司设备部署方案。</span><span class="sxs-lookup"><span data-stu-id="bc016-133">Multiple MDM systems support Windows 10 and most support personal and corporate device deployment scenarios.</span></span> <span data-ttu-id="bc016-134">支持 Windows 10 全息版的 MDM 提供程序当前包括： AirWatch、MobileIron 和其他。</span><span class="sxs-lookup"><span data-stu-id="bc016-134">MDM providers that support Windows 10 Holographic currently include: AirWatch, MobileIron, and others.</span></span> <span data-ttu-id="bc016-135">大多数行业领先的 MDM 供应商已支持与 Azure AD 集成。</span><span class="sxs-lookup"><span data-stu-id="bc016-135">Most industry-leading MDM vendors already support integration with Azure AD.</span></span> <span data-ttu-id="bc016-136">可在 [Azure Marketplace](https://azure.microsoft.com/marketplace/) 中查找支持 Azure AD 的 MDM 供应商。</span><span class="sxs-lookup"><span data-stu-id="bc016-136">You can find the MDM vendors that support Azure AD in [Azure Marketplace](https://azure.microsoft.com/marketplace/).</span></span>

## <span data-ttu-id="bc016-137">网络</span><span class="sxs-lookup"><span data-stu-id="bc016-137">Network</span></span>

<span data-ttu-id="bc016-138">在此设置中，我们预计从任何可用的开放 Wi-Fi 网络连接到 Internet 的 HoloLens 2 设备。</span><span class="sxs-lookup"><span data-stu-id="bc016-138">In this setup, we anticipate HoloLens 2 devices connecting to the Internet from any available open Wi-Fi network.</span></span> <span data-ttu-id="bc016-139">由于用户可能需要根据位置更改网络连接，因此他们应该了解如何 [将 HoloLens 设备连接到 wi-fi。](https://docs.microsoft.com/hololens/hololens-network)</span><span class="sxs-lookup"><span data-stu-id="bc016-139">Since a user could need to change the network connection based on location, they should learn how to [connect HoloLens devices to Wi-Fi.](https://docs.microsoft.com/hololens/hololens-network)</span></span>

<span data-ttu-id="bc016-140">对于 Dynamics 365 远程协助，有多种网络状况，包括带宽、延迟、抖动和数据包丢失，可能会影响视频通话体验。</span><span class="sxs-lookup"><span data-stu-id="bc016-140">For Dynamics 365 Remote Assist there are a variety of network conditions, including bandwidth, latency, jitter, and packet loss, that can impact your video calling experience.</span></span> <span data-ttu-id="bc016-141">虽然在带宽降低的环境中可以进行音频和视频呼叫，但你可能会遇到功能下降。</span><span class="sxs-lookup"><span data-stu-id="bc016-141">Although audio and video calls might be possible in environments with reduced bandwidth, you might experience feature degradation.</span></span> <span data-ttu-id="bc016-142">在 HoloLens 上使用 Dynamics 365 远程协助时，请记住以下网络要求：</span><span class="sxs-lookup"><span data-stu-id="bc016-142">When using Dynamics 365 Remote Assist on HoloLens here are the network requirements to keep in mind:</span></span>

<span data-ttu-id="bc016-143">**最小** ： 1.5 Mbps 的高至对等 HD 视频通话需要分辨率为 30 FPS 的高清1080p。</span><span class="sxs-lookup"><span data-stu-id="bc016-143">**Minimum** : 1.5 Mbps up/down is required for peer-to-peer HD quality video calling with resolution of HD 1080p at 30 fps.</span></span>

<span data-ttu-id="bc016-144">**最佳：** 对于对等高清视频通话，采用高清1080p 的分辨率，应预计 4-5 Mbps。</span><span class="sxs-lookup"><span data-stu-id="bc016-144">**Optimal:** For peer-to-peer HD quality video calling with resolution of HD 1080p, 4-5 Mbps up/down should be expected.</span></span>

<span data-ttu-id="bc016-145">详细信息：</span><span class="sxs-lookup"><span data-stu-id="bc016-145">More information:</span></span>

- [<span data-ttu-id="bc016-146">网络要求</span><span class="sxs-lookup"><span data-stu-id="bc016-146">Network requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [<span data-ttu-id="bc016-147">网络优化建议</span><span class="sxs-lookup"><span data-stu-id="bc016-147">Network optimization recommendations</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <span data-ttu-id="bc016-148">可选：将 HoloLens 连接到 VPN</span><span class="sxs-lookup"><span data-stu-id="bc016-148">Optional: Connect your HoloLens to VPN</span></span>

<span data-ttu-id="bc016-149">连接到本指南的设备将通过和外部云网络连接到网络。</span><span class="sxs-lookup"><span data-stu-id="bc016-149">The devices being connected into this guide are going to connect to the network via and external cloud network.</span></span> <span data-ttu-id="bc016-150">可能需要访问公司资源，&#39;需要通过 VPN 连接您的设备。</span><span class="sxs-lookup"><span data-stu-id="bc016-150">It may be that to access company resources you&#39;ll need to connect your devices via VPN.</span></span> <span data-ttu-id="bc016-151">有多种不同的方法将设备连接到 VPN，最终用户可以通过使用设备 UI 连接的位置，也可以通过 PPKG 或 MDM 管理设备并接收 VPN 配置文件。</span><span class="sxs-lookup"><span data-stu-id="bc016-151">There are several different ways to connect your devices to VPN, both where the end user can connect via using the device UI, or the devices can be managed and receive the VPN profile from either a PPKG or MDM.</span></span> <span data-ttu-id="bc016-152">如何设置 VPN&#39;t 在本文中介绍，因此，如果你&#39;d 想了解有关不同的 VPN 协议或管理 VPN 的方法，请访问 [这些指南以了解有关 HoloLens 和 vpn 的详细信息。](https://docs.microsoft.com/hololens/hololens-network#vpn)</span><span class="sxs-lookup"><span data-stu-id="bc016-152">How to set up VPN won&#39;t be covered in this article, so if you&#39;d like to learn more about the different VPN protocols or ways to manage VPN visit [these guides for information on HoloLens and VPN.](https://docs.microsoft.com/hololens/hololens-network#vpn)</span></span>

## <span data-ttu-id="bc016-153">下一步</span><span class="sxs-lookup"><span data-stu-id="bc016-153">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bc016-154">云连接部署-配置</span><span class="sxs-lookup"><span data-stu-id="bc016-154">Cloud connected deployment - Configure</span></span>](hololens2-cloud-connected-configure.md)
