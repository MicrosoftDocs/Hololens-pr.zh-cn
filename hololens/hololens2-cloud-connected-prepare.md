---
title: 部署指南–云连接 HoloLens 2 大规模部署，并提供远程协助-准备
description: 了解如何准备使用 azure active directory 和标识管理，通过已连接到云的网络注册 HoloLens 设备。
keywords: HoloLens，管理，云连接，远程协助，AAD，Azure AD，MDM，移动设备管理
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
ms.openlocfilehash: 21fffdc24f8682bc44779e1cebe8cd6eacb59619
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639652"
---
# <a name="prepare---cloud-connected-guide"></a><span data-ttu-id="25d5a-104">准备-云连接指南</span><span class="sxs-lookup"><span data-stu-id="25d5a-104">Prepare - Cloud connected Guide</span></span>

<span data-ttu-id="25d5a-105">本文结束时，将设置 Azure AD 和 MDM，并了解有关使用 Azure AD 帐户和网络要求的详细信息。</span><span class="sxs-lookup"><span data-stu-id="25d5a-105">By the end of this article you will have set up Azure AD, MDM, and understand more about using Azure AD accounts and network requirements.</span></span> <span data-ttu-id="25d5a-106">本指南部分将帮助你和你的组织准备好将 HoloLens 2 部署到云并使用 Dynamics 365 Remote Assist。</span><span class="sxs-lookup"><span data-stu-id="25d5a-106">This section of the guide will help you and your organization get prepared to deploy HoloLens 2 to the cloud and use Dynamics 365 Remote Assist.</span></span> <span data-ttu-id="25d5a-107">它将通过基础结构的每个部分的重要性，并提供指南的链接，以帮助你根据需要设置这些部分。</span><span class="sxs-lookup"><span data-stu-id="25d5a-107">It will go over the importance of each piece of your infrastructure as well as providing links to guides to help you set up those pieces as needed.</span></span>

## <a name="infrastructure-essentials"></a><span data-ttu-id="25d5a-108">基础结构概要</span><span class="sxs-lookup"><span data-stu-id="25d5a-108">Infrastructure Essentials</span></span>

<span data-ttu-id="25d5a-109">对于个人和公司部署方案，MDM 系统是部署和管理 Windows 10 全息版设备所需的基本基础结构。</span><span class="sxs-lookup"><span data-stu-id="25d5a-109">For both personal and corporate deployment scenarios, an MDM system is the essential infrastructure required to deploy and manage Windows 10 Holographic devices.</span></span> <span data-ttu-id="25d5a-110">Azure AD Premium 订阅建议作为标识提供程序，并且需要用于支持某些功能。</span><span class="sxs-lookup"><span data-stu-id="25d5a-110">An Azure AD premium subscription is recommended as an identity provider and required to support certain capabilities.</span></span>

### <a name="azure-active-directory"></a><span data-ttu-id="25d5a-111">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="25d5a-111">Azure Active Directory</span></span>

<span data-ttu-id="25d5a-112">Azure AD 是一种基于云的目录服务，提供标识和访问管理。</span><span class="sxs-lookup"><span data-stu-id="25d5a-112">Azure AD is a cloud-based directory service that provides identity and access management.</span></span> <span data-ttu-id="25d5a-113">使用 Microsoft Office 365 或 Intune 的组织已使用 Azure AD，其中有三个版本：免费版、高级版 P1 和高级版 P2 (参见[Azure Active Directory 版本](https://azure.microsoft.com/documentation/articles/active-directory-editions)。 ) 所有版本都支持 Azure AD 设备注册，但要启用 MDM 自动注册，需要使用高级版 P1，稍后将使用此指南。</span><span class="sxs-lookup"><span data-stu-id="25d5a-113">Organizations that use Microsoft Office 365 or Intune are already using Azure AD, which has three editions: Free, Premium P1, and Premium P2 (see [Azure Active Directory editions](https://azure.microsoft.com/documentation/articles/active-directory-editions).) All editions support Azure AD device registration, but Premium P1 is required to enable MDM auto-enrollment which we will be using in this guide later.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25d5a-114">需要 Azure Active Directory，因为 HoloLens 设备不支持本地 AD 联接。</span><span class="sxs-lookup"><span data-stu-id="25d5a-114">It is essential to have an Azure Active Directory as HoloLens devices do not support on-premises AD join.</span></span> <span data-ttu-id="25d5a-115">如果&#39;t 已设置 Azure Active Directory，请参阅[在 Azure Active Directory 中创建新租户](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)。</span><span class="sxs-lookup"><span data-stu-id="25d5a-115">If you don&#39;t already have an Azure Active Directory set up, go to [Create a new tenant in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).</span></span>

## <a name="identity-management"></a><span data-ttu-id="25d5a-116">标识管理</span><span class="sxs-lookup"><span data-stu-id="25d5a-116">Identity Management</span></span>

<span data-ttu-id="25d5a-117">员工只能使用一个帐户来初始化设备，因此，在你的组织控制首先启用哪个帐户时，它&#39;。</span><span class="sxs-lookup"><span data-stu-id="25d5a-117">Employees can use only one account to initialize a device so it&#39;s imperative that your organization controls which account is enabled first.</span></span> <span data-ttu-id="25d5a-118">所选帐户将确定由谁来控制设备，并影响管理功能。</span><span class="sxs-lookup"><span data-stu-id="25d5a-118">The account chosen will determine who controls the device and influence your management capabilities.</span></span>

<span data-ttu-id="25d5a-119">在本指南中，我们选择了为使用的[标识](/hololens/hololens-identity)使用 Azure AD 帐户，或 Azure Active Directory 帐户。</span><span class="sxs-lookup"><span data-stu-id="25d5a-119">In this guide we have chosen that for the [Identity](/hololens/hololens-identity) used we will use Azure AD accounts, or Azure Active Directory accounts.</span></span> <span data-ttu-id="25d5a-120">我们要使用 Azure AD 帐户有多个优点，例如：</span><span class="sxs-lookup"><span data-stu-id="25d5a-120">There are several benefits to Azure AD accounts we would like to use, such as:</span></span>

- <span data-ttu-id="25d5a-121">员工使用他们的 Azure AD 帐户在 Azure AD 中注册设备，并自动将其注册到组织&#39;的 mdm 解决方案 (Azure AD + mdm-需要 Azure AD Premium) 。</span><span class="sxs-lookup"><span data-stu-id="25d5a-121">Employees use their Azure AD account to register the device in Azure AD and automatically enroll it with the organization&#39;s MDM solution (Azure AD+MDM – requires Azure AD Premium).</span></span>
- <span data-ttu-id="25d5a-122">Azure AD 帐户支持 [单一登录](/azure/active-directory/manage-apps/what-is-single-sign-on)。</span><span class="sxs-lookup"><span data-stu-id="25d5a-122">Azure AD accounts support [Single Sign On](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span> <span data-ttu-id="25d5a-123">当用户登录到远程协助时，将识别其登录 Azure AD 用户的标识，并将用户登录到应用以简化体验。</span><span class="sxs-lookup"><span data-stu-id="25d5a-123">When a user signs into Remote Assist, their Identity from the signed in Azure AD user will be recognized and the user will be signed into the app for a streamlined experience.</span></span>
- <span data-ttu-id="25d5a-124">Azure AD 帐户通过[Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification)提供额外的[身份验证选项](/hololens/hololens-identity)。</span><span class="sxs-lookup"><span data-stu-id="25d5a-124">Azure AD accounts have additional [authentication options](/hololens/hololens-identity) via [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification).</span></span> <span data-ttu-id="25d5a-125">除了 Iris 登录用户以外，用户还可以从其他设备登录或使用 FIDO 安全密钥。</span><span class="sxs-lookup"><span data-stu-id="25d5a-125">In addition to Iris log-in users can sign in from another device or use FIDO security keys.</span></span>

### <a name="mobile-device-management"></a><span data-ttu-id="25d5a-126">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="25d5a-126">Mobile Device Management</span></span>

<span data-ttu-id="25d5a-127">Microsoft [Intune](/mem/intune/fundamentals/what-is-intune)是企业移动性 + 安全性的一部分，它是一种基于云的 MDM 系统，用于管理连接到租户的设备。</span><span class="sxs-lookup"><span data-stu-id="25d5a-127">Microsoft [Intune](/mem/intune/fundamentals/what-is-intune), part of the Enterprise Mobility + Security, is a cloud-based MDM system that manages devices connected to your tenant.</span></span> <span data-ttu-id="25d5a-128">与 Office 365 一样，Intune 使用 Azure AD 进行标识管理，因此员工使用相同的凭据在 Intune 中注册设备，这些设备用于登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="25d5a-128">Like Office 365, Intune uses Azure AD for identity management, so employees use the same credentials to enroll devices in Intune that they use to sign into Office 365.</span></span> <span data-ttu-id="25d5a-129">Intune 还支持运行其他操作系统（如 iOS 和 Android）的设备，以提供完整的 MDM 解决方案。</span><span class="sxs-lookup"><span data-stu-id="25d5a-129">Intune also supports devices that run other operating systems, such as iOS and Android, to provide a complete MDM solution.</span></span> <span data-ttu-id="25d5a-130">出于本指南的目的，我们&#39;将重点放在使用 Intune 来实现规模规模的云部署，HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="25d5a-130">For the purposes of this guide, we&#39;ll be focusing on using Intune for enabling a cloud deployment at scale with HoloLens 2.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25d5a-131">有必要进行移动设备管理。</span><span class="sxs-lookup"><span data-stu-id="25d5a-131">It is essential to have Mobile Device Management.</span></span> <span data-ttu-id="25d5a-132">如果未&#39;t，请遵循本指南并 [开始使用 Intune](/mem/intune/fundamentals/free-trial-sign-up)。</span><span class="sxs-lookup"><span data-stu-id="25d5a-132">If you don&#39;t already have it set up follow this guide and [Get started with Intune](/mem/intune/fundamentals/free-trial-sign-up).</span></span>

> [!NOTE]
> <span data-ttu-id="25d5a-133">多个 MDM 系统支持 Windows 10 并且大部分都支持个人和公司设备部署方案。</span><span class="sxs-lookup"><span data-stu-id="25d5a-133">Multiple MDM systems support Windows 10 and most support personal and corporate device deployment scenarios.</span></span> <span data-ttu-id="25d5a-134">支持 Windows 10 全息版的 MDM 提供程序当前包括： AirWatch、MobileIron 和其他。</span><span class="sxs-lookup"><span data-stu-id="25d5a-134">MDM providers that support Windows 10 Holographic currently include: AirWatch, MobileIron, and others.</span></span> <span data-ttu-id="25d5a-135">大多数行业领先的 MDM 供应商已支持与 Azure AD 集成。</span><span class="sxs-lookup"><span data-stu-id="25d5a-135">Most industry-leading MDM vendors already support integration with Azure AD.</span></span> <span data-ttu-id="25d5a-136">可在 [Azure Marketplace](https://azure.microsoft.com/marketplace/) 中查找支持 Azure AD 的 MDM 供应商。</span><span class="sxs-lookup"><span data-stu-id="25d5a-136">You can find the MDM vendors that support Azure AD in [Azure Marketplace](https://azure.microsoft.com/marketplace/).</span></span>

## <a name="network"></a><span data-ttu-id="25d5a-137">网络</span><span class="sxs-lookup"><span data-stu-id="25d5a-137">Network</span></span>

<span data-ttu-id="25d5a-138">在此设置中，我们预计 HoloLens 2 设备从任何可用的开放 Wi-Fi 网络连接到 Internet。</span><span class="sxs-lookup"><span data-stu-id="25d5a-138">In this setup, we anticipate HoloLens 2 devices connecting to the Internet from any available open Wi-Fi network.</span></span> <span data-ttu-id="25d5a-139">由于用户可能需要根据位置更改网络连接，因此应了解如何[将 HoloLens 设备连接到 wi-fi。](/hololens/hololens-network)</span><span class="sxs-lookup"><span data-stu-id="25d5a-139">Since a user could need to change the network connection based on location, they should learn how to [connect HoloLens devices to Wi-Fi.](/hololens/hololens-network)</span></span>

<span data-ttu-id="25d5a-140">对于 Dynamics 365 Remote Assist 有各种网络条件，包括带宽、延迟、抖动和数据包丢失，这可能会影响你的视频呼叫体验。</span><span class="sxs-lookup"><span data-stu-id="25d5a-140">For Dynamics 365 Remote Assist there are a variety of network conditions, including bandwidth, latency, jitter, and packet loss, that can impact your video calling experience.</span></span> <span data-ttu-id="25d5a-141">尽管在带宽减少的环境中可能会发生音频和视频呼叫，但你可能会遇到功能下降。</span><span class="sxs-lookup"><span data-stu-id="25d5a-141">Although audio and video calls might be possible in environments with reduced bandwidth, you might experience feature degradation.</span></span> <span data-ttu-id="25d5a-142">使用 HoloLens 上的 Dynamics 365 Remote Assist 时，需要记住以下网络要求：</span><span class="sxs-lookup"><span data-stu-id="25d5a-142">When using Dynamics 365 Remote Assist on HoloLens here are the network requirements to keep in mind:</span></span>

<span data-ttu-id="25d5a-143">**最小值** ：对于对等 hd 质量视频调用，1.5 Mbps 向上/向下需要，分辨率为 30 fps，分辨率为高清1080p。</span><span class="sxs-lookup"><span data-stu-id="25d5a-143">**Minimum** : 1.5 Mbps up/down is required for peer-to-peer HD quality video calling with resolution of HD 1080p at 30 fps.</span></span>

<span data-ttu-id="25d5a-144">**最佳：** 对于对等 HD 质量视频调用（分辨率为高清1080p），应预计 4-5 Mbps。</span><span class="sxs-lookup"><span data-stu-id="25d5a-144">**Optimal:** For peer-to-peer HD quality video calling with resolution of HD 1080p, 4-5 Mbps up/down should be expected.</span></span>

<span data-ttu-id="25d5a-145">详细信息：</span><span class="sxs-lookup"><span data-stu-id="25d5a-145">More information:</span></span>

- [<span data-ttu-id="25d5a-146">网络要求</span><span class="sxs-lookup"><span data-stu-id="25d5a-146">Network requirements</span></span>](/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [<span data-ttu-id="25d5a-147">网络优化建议</span><span class="sxs-lookup"><span data-stu-id="25d5a-147">Network optimization recommendations</span></span>](/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a><span data-ttu-id="25d5a-148">可选：将 HoloLens 连接到 VPN</span><span class="sxs-lookup"><span data-stu-id="25d5a-148">Optional: Connect your HoloLens to VPN</span></span>

<span data-ttu-id="25d5a-149">正在连接到本指南的设备将通过和外部云网络连接到网络。</span><span class="sxs-lookup"><span data-stu-id="25d5a-149">The devices being connected into this guide are going to connect to the network via and external cloud network.</span></span> <span data-ttu-id="25d5a-150">可以访问公司资源，&#39;需要通过 VPN 连接设备。</span><span class="sxs-lookup"><span data-stu-id="25d5a-150">It may be that to access company resources you&#39;ll need to connect your devices via VPN.</span></span> <span data-ttu-id="25d5a-151">可以通过多种不同的方式将设备连接到 VPN，其中，最终用户可以通过使用设备 UI 连接到这些设备，也可以通过 PPKG 或 MDM 管理设备并接收 VPN 配置文件。</span><span class="sxs-lookup"><span data-stu-id="25d5a-151">There are several different ways to connect your devices to VPN, both where the end user can connect via using the device UI, or the devices can be managed and receive the VPN profile from either a PPKG or MDM.</span></span> <span data-ttu-id="25d5a-152">在本文中，如何设置 VPN 会赢得&#39;t，因此，如果&#39;d 类了解有关不同 vpn 协议或管理 vpn 的方法的详细信息，请访问[这些指南以获取 HoloLens 和 VPN 的相关信息。](/hololens/hololens-network#vpn)</span><span class="sxs-lookup"><span data-stu-id="25d5a-152">How to set up VPN won&#39;t be covered in this article, so if you&#39;d like to learn more about the different VPN protocols or ways to manage VPN visit [these guides for information on HoloLens and VPN.](/hololens/hololens-network#vpn)</span></span>

## <a name="next-step"></a><span data-ttu-id="25d5a-153">下一步</span><span class="sxs-lookup"><span data-stu-id="25d5a-153">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="25d5a-154">云连接部署-配置</span><span class="sxs-lookup"><span data-stu-id="25d5a-154">Cloud connected deployment - Configure</span></span>](hololens2-cloud-connected-configure.md)
