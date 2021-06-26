---
title: 部署指南 - 使用 HoloLens 2 大规模部署云Remote Assist - 准备
description: 了解如何准备使用 Azure Active Directory 和标识管理通过云连接的网络注册 HoloLens 设备。
keywords: HoloLens， 管理， 云连接， Remote Assist， AAD， Azure AD， MDM， 移动设备管理
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
ms.openlocfilehash: 21132ed5d1e84d92a877747ac9a4c090b177ca08
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924564"
---
# <a name="prepare---cloud-connected-guide"></a><span data-ttu-id="a8c71-104">准备 - 云连接指南</span><span class="sxs-lookup"><span data-stu-id="a8c71-104">Prepare - Cloud connected Guide</span></span>

<span data-ttu-id="a8c71-105">本文结束时，你将设置 Azure AD MDM，并了解有关使用Azure AD和网络要求。</span><span class="sxs-lookup"><span data-stu-id="a8c71-105">By the end of this article you will have set up Azure AD, MDM, and understand more about using Azure AD accounts and network requirements.</span></span> <span data-ttu-id="a8c71-106">本指南的此部分将帮助你和组织准备好将HoloLens 2部署到云并使用Dynamics 365 Remote Assist。</span><span class="sxs-lookup"><span data-stu-id="a8c71-106">This section of the guide will help you and your organization get prepared to deploy HoloLens 2 to the cloud and use Dynamics 365 Remote Assist.</span></span> <span data-ttu-id="a8c71-107">它将了解基础结构的每个部分的重要性，并提供指向指南的链接，以帮助你根据需要设置这些部分。</span><span class="sxs-lookup"><span data-stu-id="a8c71-107">It will go over the importance of each piece of your infrastructure as well as providing links to guides to help you set up those pieces as needed.</span></span>

## <a name="infrastructure-essentials"></a><span data-ttu-id="a8c71-108">基础结构基本信息</span><span class="sxs-lookup"><span data-stu-id="a8c71-108">Infrastructure Essentials</span></span>

<span data-ttu-id="a8c71-109">对于个人和公司部署方案，MDM 系统是部署和管理设备所需的Windows 10 全息版基础结构。</span><span class="sxs-lookup"><span data-stu-id="a8c71-109">For both personal and corporate deployment scenarios, an MDM system is the essential infrastructure required to deploy and manage Windows 10 Holographic devices.</span></span> <span data-ttu-id="a8c71-110">Azure AD Premium 订阅建议作为标识提供程序，并且需要用于支持某些功能。</span><span class="sxs-lookup"><span data-stu-id="a8c71-110">An Azure AD premium subscription is recommended as an identity provider and required to support certain capabilities.</span></span>

### <a name="azure-active-directory"></a><span data-ttu-id="a8c71-111">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a8c71-111">Azure Active Directory</span></span>

<span data-ttu-id="a8c71-112">Azure AD是一种基于云的目录服务，可提供标识和访问管理。</span><span class="sxs-lookup"><span data-stu-id="a8c71-112">Azure AD is a cloud-based directory service that provides identity and access management.</span></span> <span data-ttu-id="a8c71-113">使用 Microsoft Office 365 或 Intune 的组织已使用具有三个版本的 Azure AD：免费版、高级 P1 版和高级 P2 版 (请参阅 [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-editions)版本 .) 所有版本都支持 Azure AD 设备注册，但需要 Premium P1 才能启用 MDM 自动注册，我们稍后将在本指南中使用它。</span><span class="sxs-lookup"><span data-stu-id="a8c71-113">Organizations that use Microsoft Office 365 or Intune are already using Azure AD, which has three editions: Free, Premium P1, and Premium P2 (see [Azure Active Directory editions](https://azure.microsoft.com/documentation/articles/active-directory-editions).) All editions support Azure AD device registration, but Premium P1 is required to enable MDM auto-enrollment which we will be using in this guide later.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8c71-114">必须创建一个Azure Active Directory，因为 HoloLens 设备不支持本地 AD 联接。</span><span class="sxs-lookup"><span data-stu-id="a8c71-114">It is essential to have an Azure Active Directory as HoloLens devices do not support on-premises AD join.</span></span> <span data-ttu-id="a8c71-115">如果尚未&#39;设置Azure Active Directory，请转到在 中[创建新Azure Active Directory。](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant)</span><span class="sxs-lookup"><span data-stu-id="a8c71-115">If you don&#39;t already have an Azure Active Directory set up, go to [Create a new tenant in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant).</span></span>

## <a name="identity-management"></a><span data-ttu-id="a8c71-116">标识管理</span><span class="sxs-lookup"><span data-stu-id="a8c71-116">Identity Management</span></span>

<span data-ttu-id="a8c71-117">员工只能使用一个帐户来初始化设备，因此&#39;组织必须控制首先启用的帐户。</span><span class="sxs-lookup"><span data-stu-id="a8c71-117">Employees can use only one account to initialize a device so it&#39;s imperative that your organization controls which account is enabled first.</span></span> <span data-ttu-id="a8c71-118">所选帐户将确定由谁来控制设备，并影响管理功能。</span><span class="sxs-lookup"><span data-stu-id="a8c71-118">The account chosen will determine who controls the device and influence your management capabilities.</span></span>

<span data-ttu-id="a8c71-119">在本指南中，我们已选择"标识使用 ["，](https://docs.microsoft.com/hololens/hololens-identity) 我们将使用Azure AD帐户或Azure Active Directory帐户。</span><span class="sxs-lookup"><span data-stu-id="a8c71-119">In this guide we have chosen that for the [Identity](https://docs.microsoft.com/hololens/hololens-identity) used we will use Azure AD accounts, or Azure Active Directory accounts.</span></span> <span data-ttu-id="a8c71-120">使用Azure AD帐户有几个好处，例如：</span><span class="sxs-lookup"><span data-stu-id="a8c71-120">There are several benefits to Azure AD accounts we would like to use, such as:</span></span>

- <span data-ttu-id="a8c71-121">员工使用Azure AD帐户在 Azure AD 中注册设备，并自动向组织注册&#39;MDM 解决方案 (Azure AD+MDM – 需要Azure AD Premium) 。</span><span class="sxs-lookup"><span data-stu-id="a8c71-121">Employees use their Azure AD account to register the device in Azure AD and automatically enroll it with the organization&#39;s MDM solution (Azure AD+MDM – requires Azure AD Premium).</span></span>
- <span data-ttu-id="a8c71-122">Azure AD帐户支持 [单一登录](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on)。</span><span class="sxs-lookup"><span data-stu-id="a8c71-122">Azure AD accounts support [Single Sign On](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span> <span data-ttu-id="a8c71-123">当用户登录到 Remote Assist，将识别已登录用户Azure AD标识，并且用户将登录到应用，获得简化的体验。</span><span class="sxs-lookup"><span data-stu-id="a8c71-123">When a user signs into Remote Assist, their Identity from the signed in Azure AD user will be recognized and the user will be signed into the app for a streamlined experience.</span></span>
- <span data-ttu-id="a8c71-124">Azure AD帐户具有其他[身份验证选项，Windows Hello 企业版。](https://docs.microsoft.com/hololens/hololens-identity) [](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)</span><span class="sxs-lookup"><span data-stu-id="a8c71-124">Azure AD accounts have additional [authentication options](https://docs.microsoft.com/hololens/hololens-identity) via [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification).</span></span> <span data-ttu-id="a8c71-125">除了 Iris 登录外，用户还可以从另一台设备登录或使用 FIDO 安全密钥。</span><span class="sxs-lookup"><span data-stu-id="a8c71-125">In addition to Iris log-in users can sign in from another device or use FIDO security keys.</span></span>

### <a name="mobile-device-management"></a><span data-ttu-id="a8c71-126">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="a8c71-126">Mobile Device Management</span></span>

<span data-ttu-id="a8c71-127">Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)是 企业移动性 + 安全性的一部分，是一个基于云的 MDM 系统，用于管理连接到租户的设备。</span><span class="sxs-lookup"><span data-stu-id="a8c71-127">Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune), part of the Enterprise Mobility + Security, is a cloud-based MDM system that manages devices connected to your tenant.</span></span> <span data-ttu-id="a8c71-128">与 Office 365 一样，Intune 使用 Azure AD 进行标识管理，因此员工使用相同的凭据在 Intune 中注册设备，这些凭据用于登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="a8c71-128">Like Office 365, Intune uses Azure AD for identity management, so employees use the same credentials to enroll devices in Intune that they use to sign into Office 365.</span></span> <span data-ttu-id="a8c71-129">Intune 还支持运行其他操作系统（如 iOS 和 Android）的设备，以提供完整的 MDM 解决方案。</span><span class="sxs-lookup"><span data-stu-id="a8c71-129">Intune also supports devices that run other operating systems, such as iOS and Android, to provide a complete MDM solution.</span></span> <span data-ttu-id="a8c71-130">在本指南中，我们将重点介绍&#39;Intune，以便通过 HoloLens 2 实现大规模云部署。</span><span class="sxs-lookup"><span data-stu-id="a8c71-130">For the purposes of this guide, we&#39;ll be focusing on using Intune for enabling a cloud deployment at scale with HoloLens 2.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8c71-131">必须拥有移动设备管理。</span><span class="sxs-lookup"><span data-stu-id="a8c71-131">It is essential to have Mobile Device Management.</span></span> <span data-ttu-id="a8c71-132">如果尚未&#39;，请按照本指南和 [Intune 入门操作](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up)。</span><span class="sxs-lookup"><span data-stu-id="a8c71-132">If you don&#39;t already have it set up follow this guide and [Get started with Intune](https://docs.microsoft.com/mem/intune/fundamentals/free-trial-sign-up).</span></span>

> [!NOTE]
> <span data-ttu-id="a8c71-133">多个 MDM 系统支持 Windows 10 并且大部分都支持个人和公司设备部署方案。</span><span class="sxs-lookup"><span data-stu-id="a8c71-133">Multiple MDM systems support Windows 10 and most support personal and corporate device deployment scenarios.</span></span> <span data-ttu-id="a8c71-134">目前，支持Windows 10 全息版 MDM 提供程序包括：AirWatch、MobileIron 等。</span><span class="sxs-lookup"><span data-stu-id="a8c71-134">MDM providers that support Windows 10 Holographic currently include: AirWatch, MobileIron, and others.</span></span> <span data-ttu-id="a8c71-135">大多数行业领先的 MDM 供应商已支持与 Azure AD 集成。</span><span class="sxs-lookup"><span data-stu-id="a8c71-135">Most industry-leading MDM vendors already support integration with Azure AD.</span></span> <span data-ttu-id="a8c71-136">可在 [Azure Marketplace](https://azure.microsoft.com/marketplace/) 中查找支持 Azure AD 的 MDM 供应商。</span><span class="sxs-lookup"><span data-stu-id="a8c71-136">You can find the MDM vendors that support Azure AD in [Azure Marketplace](https://azure.microsoft.com/marketplace/).</span></span>

## <a name="network"></a><span data-ttu-id="a8c71-137">网络</span><span class="sxs-lookup"><span data-stu-id="a8c71-137">Network</span></span>

<span data-ttu-id="a8c71-138">在此设置中，我们HoloLens 2任何可用的开放网络连接到 Internet Wi-Fi设备。</span><span class="sxs-lookup"><span data-stu-id="a8c71-138">In this setup, we anticipate HoloLens 2 devices connecting to the Internet from any available open Wi-Fi network.</span></span> <span data-ttu-id="a8c71-139">由于用户可能需要根据位置更改网络连接，因此他们应了解如何将 [HoloLens 设备连接到 Wi-Fi。](https://docs.microsoft.com/hololens/hololens-network)</span><span class="sxs-lookup"><span data-stu-id="a8c71-139">Since a user could need to change the network connection based on location, they should learn how to [connect HoloLens devices to Wi-Fi.](https://docs.microsoft.com/hololens/hololens-network)</span></span>

<span data-ttu-id="a8c71-140">例如Dynamics 365 Remote Assist各种网络条件（包括带宽、延迟、抖动和数据包丢失）可能会影响视频通话体验。</span><span class="sxs-lookup"><span data-stu-id="a8c71-140">For Dynamics 365 Remote Assist there are a variety of network conditions, including bandwidth, latency, jitter, and packet loss, that can impact your video calling experience.</span></span> <span data-ttu-id="a8c71-141">尽管可以在带宽降低的环境中进行音频和视频调用，但可能会遇到功能降级的情况。</span><span class="sxs-lookup"><span data-stu-id="a8c71-141">Although audio and video calls might be possible in environments with reduced bandwidth, you might experience feature degradation.</span></span> <span data-ttu-id="a8c71-142">在 HoloLens Dynamics 365 Remote Assist时，请记住以下网络要求：</span><span class="sxs-lookup"><span data-stu-id="a8c71-142">When using Dynamics 365 Remote Assist on HoloLens here are the network requirements to keep in mind:</span></span>

<span data-ttu-id="a8c71-143">**最低** ：对等 HD 质量视频通话需要 1.5 Mbps 向上/向下，HD 1080p 分辨率为 30 fps。</span><span class="sxs-lookup"><span data-stu-id="a8c71-143">**Minimum** : 1.5 Mbps up/down is required for peer-to-peer HD quality video calling with resolution of HD 1080p at 30 fps.</span></span>

<span data-ttu-id="a8c71-144">**最佳：** 对于 HD 1080p 分辨率为 4-5 Mbps 的对等 HD 质量视频通话，应会向上/向下 4-5 Mbps。</span><span class="sxs-lookup"><span data-stu-id="a8c71-144">**Optimal:** For peer-to-peer HD quality video calling with resolution of HD 1080p, 4-5 Mbps up/down should be expected.</span></span>

<span data-ttu-id="a8c71-145">详细信息：</span><span class="sxs-lookup"><span data-stu-id="a8c71-145">More information:</span></span>

- [<span data-ttu-id="a8c71-146">网络要求</span><span class="sxs-lookup"><span data-stu-id="a8c71-146">Network requirements</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)
- [<span data-ttu-id="a8c71-147">网络优化建议</span><span class="sxs-lookup"><span data-stu-id="a8c71-147">Network optimization recommendations</span></span>](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#dynamics-365-remote-assist-hololens)

### <a name="optional-connect-your-hololens-to-vpn"></a><span data-ttu-id="a8c71-148">可选：将 HoloLens 连接到 VPN</span><span class="sxs-lookup"><span data-stu-id="a8c71-148">Optional: Connect your HoloLens to VPN</span></span>

<span data-ttu-id="a8c71-149">连接到本指南的设备将通过网络和外部云网络连接到网络。</span><span class="sxs-lookup"><span data-stu-id="a8c71-149">The devices being connected into this guide are going to connect to the network via and external cloud network.</span></span> <span data-ttu-id="a8c71-150">访问公司资源可能需要&#39;VPN 连接设备。</span><span class="sxs-lookup"><span data-stu-id="a8c71-150">It may be that to access company resources you&#39;ll need to connect your devices via VPN.</span></span> <span data-ttu-id="a8c71-151">可通过多种不同方式将设备连接到 VPN，其中最终用户可以使用设备 UI 进行连接，也可以通过 PPKG 或 MDM 管理设备并接收 VPN 配置文件。</span><span class="sxs-lookup"><span data-stu-id="a8c71-151">There are several different ways to connect your devices to VPN, both where the end user can connect via using the device UI, or the devices can be managed and receive the VPN profile from either a PPKG or MDM.</span></span> <span data-ttu-id="a8c71-152">本文不会&#39;VPN 设置方法，因此，&#39;详细了解不同的 VPN 协议或 VPN 管理方法，请访问这些指南，了解有关[HoloLens](https://docs.microsoft.com/hololens/hololens-network#vpn)和 VPN 的信息。</span><span class="sxs-lookup"><span data-stu-id="a8c71-152">How to set up VPN won&#39;t be covered in this article, so if you&#39;d like to learn more about the different VPN protocols or ways to manage VPN visit [these guides for information on HoloLens and VPN.](https://docs.microsoft.com/hololens/hololens-network#vpn)</span></span>

## <a name="next-step"></a><span data-ttu-id="a8c71-153">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a8c71-153">Next step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a8c71-154">云连接部署 - 配置</span><span class="sxs-lookup"><span data-stu-id="a8c71-154">Cloud connected deployment - Configure</span></span>](hololens2-cloud-connected-configure.md)
