---
title: HoloLens 基础结构指南
description: 了解 HoloLens 设备的基础结构指南，包括无线网络支持、远程协助和移动设备管理。
ms.prod: hololens
ms.sitesec: library
author: pawinfie
ms.author: pawinfie
ms.topic: article
ms.localizationpriority: high
ms.date: 1/23/2020
ms.reviewer: ''
audience: ITPro
manager: bradke
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 4eb55bec56e53de9195ac87e0491eefd91992f3d
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283383"
---
# <span data-ttu-id="8f83f-103">为 HoloLens 配置网络</span><span class="sxs-lookup"><span data-stu-id="8f83f-103">Configure Your Network for HoloLens</span></span>

<span data-ttu-id="8f83f-104">文档的此部分将需要以下人员：</span><span class="sxs-lookup"><span data-stu-id="8f83f-104">This portion of the document will require the following people:</span></span>

1. <span data-ttu-id="8f83f-105">具有对代理/防火墙进行更改的权限的网络管理员</span><span class="sxs-lookup"><span data-stu-id="8f83f-105">Network Admin with permissions to make changes to the proxy/firewall</span></span>
2. <span data-ttu-id="8f83f-106">Azure Active Directory 管理员</span><span class="sxs-lookup"><span data-stu-id="8f83f-106">Azure Active Directory Admin</span></span>
3. <span data-ttu-id="8f83f-107">移动设备管理器管理员</span><span class="sxs-lookup"><span data-stu-id="8f83f-107">Mobile Device Manager Admin</span></span>

## <span data-ttu-id="8f83f-108">基础结构要求</span><span class="sxs-lookup"><span data-stu-id="8f83f-108">Infrastructure Requirements</span></span>

<span data-ttu-id="8f83f-109">HoloLens 从核心看来是与 Azure 集成的 Windows 移动设备。</span><span class="sxs-lookup"><span data-stu-id="8f83f-109">HoloLens is, at its core, a Windows mobile device integrated with Azure.</span></span>  <span data-ttu-id="8f83f-110">它最适用于可使用无线网络 (wi-fi) 并可访问 Microsoft 服务的商业环境。</span><span class="sxs-lookup"><span data-stu-id="8f83f-110">It works best in commercial environments with wireless network availability (wi-fi) and access to Microsoft services.</span></span>

<span data-ttu-id="8f83f-111">关键的云服务包括：</span><span class="sxs-lookup"><span data-stu-id="8f83f-111">Critical cloud services include:</span></span>

- <span data-ttu-id="8f83f-112">Azure active directory (Azure AD) </span><span class="sxs-lookup"><span data-stu-id="8f83f-112">Azure active directory (Azure AD)</span></span>
- <span data-ttu-id="8f83f-113">Windows 更新 (WU)</span><span class="sxs-lookup"><span data-stu-id="8f83f-113">Windows Update (WU)</span></span>

<span data-ttu-id="8f83f-114">商业客户需要通过企业移动性管理 (EMM) 或移动设备管理 (MDM) 基础结构来大规模管理 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="8f83f-114">Commercial customers will need enterprise mobility management (EMM) or mobile device management (MDM) infrastructure to manage HoloLens devices at scale.</span></span>  <span data-ttu-id="8f83f-115">本指南使用 [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) 作为示例，但任何完全支持 Microsoft 策略的提供商都可支持 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="8f83f-115">This guide uses [Microsoft Intune](https://www.microsoft.com/enterprise-mobility-security/microsoft-intune) as an example, though any provider with full support for Microsoft Policy can support HoloLens.</span></span>  <span data-ttu-id="8f83f-116">询问你的移动设备管理提供商是否支持 HoloLens 2。</span><span class="sxs-lookup"><span data-stu-id="8f83f-116">Ask your mobile device management provider if they support HoloLens 2.</span></span>

<span data-ttu-id="8f83f-117">HoloLens 支持一组有限的从云断开的连接体验。</span><span class="sxs-lookup"><span data-stu-id="8f83f-117">HoloLens does support a limited set of cloud disconnected experiences.</span></span>

### <span data-ttu-id="8f83f-118">无线网络 EAP 支持</span><span class="sxs-lookup"><span data-stu-id="8f83f-118">Wireless network EAP support</span></span>

- <span data-ttu-id="8f83f-119">PEAP-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="8f83f-119">PEAP-MS-CHAPv2</span></span>
- <span data-ttu-id="8f83f-120">PEAP-TLS</span><span class="sxs-lookup"><span data-stu-id="8f83f-120">PEAP-TLS</span></span>
- <span data-ttu-id="8f83f-121">TLS</span><span class="sxs-lookup"><span data-stu-id="8f83f-121">TLS</span></span>
- <span data-ttu-id="8f83f-122">TTLS-CHAP</span><span class="sxs-lookup"><span data-stu-id="8f83f-122">TTLS-CHAP</span></span>
- <span data-ttu-id="8f83f-123">TTLS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="8f83f-123">TTLS-CHAPv2</span></span>
- <span data-ttu-id="8f83f-124">TTLS-MS-CHAPv2</span><span class="sxs-lookup"><span data-stu-id="8f83f-124">TTLS-MS-CHAPv2</span></span>
- <span data-ttu-id="8f83f-125">TTLS-PAP</span><span class="sxs-lookup"><span data-stu-id="8f83f-125">TTLS-PAP</span></span>
- <span data-ttu-id="8f83f-126">TTLS-TLS</span><span class="sxs-lookup"><span data-stu-id="8f83f-126">TTLS-TLS</span></span>

### <span data-ttu-id="8f83f-127">HoloLens 特定网络要求</span><span class="sxs-lookup"><span data-stu-id="8f83f-127">HoloLens Specific Network Requirements</span></span>

<span data-ttu-id="8f83f-128">确保你的网络防火墙允许终结点的[此列表](hololens-offline.md)。</span><span class="sxs-lookup"><span data-stu-id="8f83f-128">Make sure that [this list](hololens-offline.md) of endpoints are allowed on your network firewall.</span></span> <span data-ttu-id="8f83f-129">这将使 HoloLens 能够正常工作。</span><span class="sxs-lookup"><span data-stu-id="8f83f-129">This will enable HoloLens to function properly.</span></span>

### <span data-ttu-id="8f83f-130">Remote Assist 特定网络要求</span><span class="sxs-lookup"><span data-stu-id="8f83f-130">Remote Assist Specific Network Requirements</span></span>

1. <span data-ttu-id="8f83f-131">为保证 Remote Assist 的最佳性能，推荐的带宽为 1.5Mbps。</span><span class="sxs-lookup"><span data-stu-id="8f83f-131">The recommended bandwidth for optimal performance of Remote Assist is 1.5Mbps.</span></span> <span data-ttu-id="8f83f-132">有关其他信息，请参阅[详细的网络要求](https://docs.microsoft.com/MicrosoftTeams/prepare-network)。</span><span class="sxs-lookup"><span data-stu-id="8f83f-132">See the [detailed network requirements](https://docs.microsoft.com/MicrosoftTeams/prepare-network) for additional information.</span></span>
**<span data-ttu-id="8f83f-133">（请注意，即使你的网络速度无法至少达到 1.5Mbps，Remote Assist 也仍可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="8f83f-133">(Please note, if you don't network have network speeds of at least 1.5Mbps, Remote Assist will still work.</span></span> <span data-ttu-id="8f83f-134">但是，质量可能会受到影响。）</span><span class="sxs-lookup"><span data-stu-id="8f83f-134">However, quality may suffer).</span></span>**
1. <span data-ttu-id="8f83f-135">请确保网络防火墙上允许使用这些端口和 URL，以使 Microsoft Teams 能够正常运行。</span><span class="sxs-lookup"><span data-stu-id="8f83f-135">Make sure that these ports and URLs are allowed on your network firewall to enable Microsoft Teams to function.</span></span> <span data-ttu-id="8f83f-136">随时了解[最新端口列表](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="8f83f-136">Stay up to date with the [latest list of ports](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

- <span data-ttu-id="8f83f-137">了解有关具体的[远程协助网络要求](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8f83f-137">Learn more about the specific [Network Requirements for Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/requirements#network-requirements).</span></span> 
- <span data-ttu-id="8f83f-138">详细了解如何[为 Microsoft Team 准备组织的网络](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span><span class="sxs-lookup"><span data-stu-id="8f83f-138">Learn more about how to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</span></span>

### <span data-ttu-id="8f83f-139">Guides 特定网络要求</span><span class="sxs-lookup"><span data-stu-id="8f83f-139">Guides Specific Network Requirements</span></span>

<span data-ttu-id="8f83f-140">Guides 仅需要通过网络访问权限下载并使用该应用。</span><span class="sxs-lookup"><span data-stu-id="8f83f-140">Guides only require network access to download and use the app.</span></span>

## <span data-ttu-id="8f83f-141">Azure Active Directory 指南</span><span class="sxs-lookup"><span data-stu-id="8f83f-141">Azure Active Directory Guidance</span></span>

> [!NOTE]
> <span data-ttu-id="8f83f-142">仅当贵公司计划管理 HoloLens 时，才需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="8f83f-142">This step is only necessary if your company plans on managing the HoloLens.</span></span>

1. <span data-ttu-id="8f83f-143">确保你拥有 Azure AD 许可证。</span><span class="sxs-lookup"><span data-stu-id="8f83f-143">Ensure that you have an Azure AD License.</span></span>
<span data-ttu-id="8f83f-144">有关附加信息，请参阅 [HoloLens 许可证要求](hololens-licenses-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f83f-144">Please [HoloLens Licenses Requirements](hololens-licenses-requirements.md) for additional information.</span></span>

1. <span data-ttu-id="8f83f-145">如果计划使用自动注册，必须[配置 Azure AD 注册](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="8f83f-145">If you plan on using Auto Enrollment, you will have to [Configure Azure AD enrollment.](https://docs.microsoft.com/intune/deploy-use/.set-up-windows-device-management-with-microsoft-intune#azure-active-directory-enrollment)</span></span>

1. <span data-ttu-id="8f83f-146">确保贵公司的用户在 Azure Active Directory (Azure AD) 中。</span><span class="sxs-lookup"><span data-stu-id="8f83f-146">Ensure that your company's users are in Azure Active Directory (Azure AD).</span></span>
<span data-ttu-id="8f83f-147">请参阅以下添加用户的[说明](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="8f83f-147">See the following [instructions](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory) for adding users.</span></span>

1. <span data-ttu-id="8f83f-148">建议将需要类似许可证的用户添加到相同组中。</span><span class="sxs-lookup"><span data-stu-id="8f83f-148">We suggest that users who need similar licenses are added to the same group.</span></span>
    1. [<span data-ttu-id="8f83f-149">创建一个组</span><span class="sxs-lookup"><span data-stu-id="8f83f-149">Create a Group</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    1. [<span data-ttu-id="8f83f-150">向组中添加用户</span><span class="sxs-lookup"><span data-stu-id="8f83f-150">Add users to groups</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-members-azure-portal)

1. <span data-ttu-id="8f83f-151">确保为贵公司的用户（或用户组）分配了所需的许可证。</span><span class="sxs-lookup"><span data-stu-id="8f83f-151">Ensure that your company's users (or group of users) are assigned the necessary licenses.</span></span>
<span data-ttu-id="8f83f-152">如果你需要分配许可证，请按照以下[说明](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups)执行。</span><span class="sxs-lookup"><span data-stu-id="8f83f-152">If you need to assign licenses, follow these [directions](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups).</span></span>

1. <span data-ttu-id="8f83f-153">仅当希望用户向你注册自己的 HoloLens/移动设备时，才执行此步骤。（有三个选项。）这些步骤可确保公司的用户（或用户组）可以添加设备。</span><span class="sxs-lookup"><span data-stu-id="8f83f-153">Only do this step if users are expected to enroll their HoloLens/Mobile device into you (There are three options) These steps ensure that your company's users (or a group of users) can add devices.</span></span>
    1. <span data-ttu-id="8f83f-154">**选项 1：** 向所有用户授予将设备加入 Azure AD 的权限。</span><span class="sxs-lookup"><span data-stu-id="8f83f-154">**Option 1:** Give all users permission to join devices to Azure AD.</span></span>
<span data-ttu-id="8f83f-155">**以管理员身份登录 Azure 门户** > **Azure Active Directory** > **设备** > **设备设置** >
**将“用户可以将设备加入 Azure AD”设置为\*全部**\*</span><span class="sxs-lookup"><span data-stu-id="8f83f-155">**Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
**Set Users may join devices to Azure AD to *All***</span></span>

    1. <span data-ttu-id="8f83f-156">**选项 2：** 向所选用户/组授予将设备加入 Azure AD 的权限。以管理员身份**登录 Azure 门户** > **Azure Active Directory** > **设备** > **设备设置** >
\**将“用户可以将设备加入 Azure AD”设置为*选定\*\*\*
![此图显示加入 Azure AD 的设备的配置</span><span class="sxs-lookup"><span data-stu-id="8f83f-156">**Option 2:** Give selected users/groups permission to join devices to Azure AD **Sign in to the Azure portal as an administrator** > **Azure Active Directory** > **Devices** > **Device Settings** >
\*\*Set Users may join devices to Azure AD to \*Selected\*\*\*
![Image that shows Configuration of Azure AD Joined Devices</span></span>](images/azure-ad-image.png)

    1. <span data-ttu-id="8f83f-157">**选项 3：** 可阻止所有用户将其设备加入到域中。</span><span class="sxs-lookup"><span data-stu-id="8f83f-157">**Option 3:** You can block all users from joining their devices to the domain.</span></span> <span data-ttu-id="8f83f-158">这意味着需要手动注册所有设备。</span><span class="sxs-lookup"><span data-stu-id="8f83f-158">This means that all devices will need to be manually enrolled.</span></span>

## <span data-ttu-id="8f83f-159">移动设备管理器指南</span><span class="sxs-lookup"><span data-stu-id="8f83f-159">Mobile Device Manager Guidance</span></span>

### <span data-ttu-id="8f83f-160">持续设备管理</span><span class="sxs-lookup"><span data-stu-id="8f83f-160">Ongoing device management</span></span>

> [!NOTE]
> <span data-ttu-id="8f83f-161">只有公司计划管理 HoloLens 时才需要此步骤。</span><span class="sxs-lookup"><span data-stu-id="8f83f-161">This step is only necessary if your company plans to manage the HoloLens.</span></span>

<span data-ttu-id="8f83f-162">持续设备管理依赖于移动设备管理基础结构。</span><span class="sxs-lookup"><span data-stu-id="8f83f-162">Ongoing device management will depend on your mobile device management infrastructure.</span></span>  <span data-ttu-id="8f83f-163">大多数具有相同的常规功能，但用户界面可能会有很大差异。</span><span class="sxs-lookup"><span data-stu-id="8f83f-163">Most have the same general functionality but the user interface may vary widely.</span></span>

1. <span data-ttu-id="8f83f-164">[CSP（配置服务提供程序）](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)可用于创建和部署网络上设备的管理设置。</span><span class="sxs-lookup"><span data-stu-id="8f83f-164">[CSPs (Configuration Service Providers)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) lets you to create and deploy management settings for the devices on your network.</span></span> <span data-ttu-id="8f83f-165">请参阅 [HoloLens CSP 列表](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices)。</span><span class="sxs-lookup"><span data-stu-id="8f83f-165">See the [list of HoloLens CSPs](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#csps-supported-in-hololens-devices) for reference.</span></span>

1. <span data-ttu-id="8f83f-166">[合规性策略](https://docs.microsoft.com/intune/device-compliance-get-started)是一些规则和设置，设备必须满足这些规则和设置才能在企业基础结构中合规。</span><span class="sxs-lookup"><span data-stu-id="8f83f-166">[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) are rules and settings that devices must meet to be compliant in your corporate infrastructure.</span></span> <span data-ttu-id="8f83f-167">将这些策略与条件访问结合使用，可阻止不合规的设备访问公司资源。</span><span class="sxs-lookup"><span data-stu-id="8f83f-167">Use these policies with Conditional Access to block access to company resources for devices that are non-compliant.</span></span> <span data-ttu-id="8f83f-168">例如，可以创建一个要求启用 Bitlocker 的策略。</span><span class="sxs-lookup"><span data-stu-id="8f83f-168">For example, you can create a policy that requires Bitlocker be enabled.</span></span>

1. <span data-ttu-id="8f83f-169">[创建合规性策略](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows)。</span><span class="sxs-lookup"><span data-stu-id="8f83f-169">[Create Compliance Policy](https://docs.microsoft.com/intune/protect/compliance-policy-create-windows).</span></span>

1. <span data-ttu-id="8f83f-170">条件访问可以允许/拒绝移动设备和移动应用程序访问公司资源。</span><span class="sxs-lookup"><span data-stu-id="8f83f-170">Conditional Access allows/denies mobile devices and mobile applications from accessing company resources.</span></span> <span data-ttu-id="8f83f-171">你可能会发现[规划 CA 部署](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)和[最佳做法](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices)这两个文档非常有用。</span><span class="sxs-lookup"><span data-stu-id="8f83f-171">Two documents you may find helpful are [Plan your CA Deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) and [Best Practices](https://docs.microsoft.com/azure/active-directory/conditional-access/best-practices).</span></span>

1. <span data-ttu-id="8f83f-172">[本文](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business)介绍 Intune 的 HoloLens 管理工具。</span><span class="sxs-lookup"><span data-stu-id="8f83f-172">[This article](https://docs.microsoft.com/intune/fundamentals/windows-holographic-for-business) talks about Intune's management tools for HoloLens.</span></span>

1. [<span data-ttu-id="8f83f-173">创建设备配置文件</span><span class="sxs-lookup"><span data-stu-id="8f83f-173">Create a device profile</span></span>](https://docs.microsoft.com/intune/configuration/device-profile-create)

### <span data-ttu-id="8f83f-174">管理更新</span><span class="sxs-lookup"><span data-stu-id="8f83f-174">Manage updates</span></span>

<span data-ttu-id="8f83f-175">Intune 包含名为“更新圈”的功能，适用于 Windows 10 设备，包括 HoloLens 2 和 HoloLens v1（具有 Holographic for Business）。</span><span class="sxs-lookup"><span data-stu-id="8f83f-175">Intune includes a feature called Update rings for Windows 10 devices, including HoloLens 2 and HoloLens v1 (with Holographic for Business).</span></span> <span data-ttu-id="8f83f-176">更新圈包括一组设置，用于确定安装更新的时间和方式。</span><span class="sxs-lookup"><span data-stu-id="8f83f-176">Update rings include a group of settings that determine how and when updates are installed.</span></span>

<span data-ttu-id="8f83f-177">例如，可以创建维护时间窗口来安装更新，或选择在安装更新后重启。</span><span class="sxs-lookup"><span data-stu-id="8f83f-177">For example, you can create a maintenance window to install updates, or choose to restart after updates are installed.</span></span>  <span data-ttu-id="8f83f-178">还可以选择无限期暂停更新，直至到你准备好进行更新。</span><span class="sxs-lookup"><span data-stu-id="8f83f-178">You can also choose to pause updates indefinitely until you're ready to update.</span></span>

<span data-ttu-id="8f83f-179">阅读有关[使用 Intune 配置更新圈](https://docs.microsoft.com/intune/windows-update-for-business-configure)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8f83f-179">Read more about [configuring update rings with Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure).</span></span>

### <span data-ttu-id="8f83f-180">应用程序管理</span><span class="sxs-lookup"><span data-stu-id="8f83f-180">Application management</span></span>

<span data-ttu-id="8f83f-181">可通过以下工具管理 HoloLens 应用程序：</span><span class="sxs-lookup"><span data-stu-id="8f83f-181">Manage HoloLens applications through:</span></span>

1. <span data-ttu-id="8f83f-182">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="8f83f-182">Microsoft Store</span></span>  
  <span data-ttu-id="8f83f-183">Microsoft Store 是在 HoloLens 上分发和使用应用程序的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="8f83f-183">The Microsoft Store is the best way to distribute and consume applications on HoloLens.</span></span>  <span data-ttu-id="8f83f-184">商店中已有大量的核心 HoloLens 应用程序，你还可以[发布自己的 HoloLens 应用程序](https://docs.microsoft.com/windows/uwp/publish/)。</span><span class="sxs-lookup"><span data-stu-id="8f83f-184">There is a great set of core HoloLens applications already available in the store or you can [publish your own](https://docs.microsoft.com/windows/uwp/publish/).</span></span>  
  <span data-ttu-id="8f83f-185">商店中的所有应用程序都向所有人公开，但如果这不可接受，请使用适用于企业的 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="8f83f-185">All applications in the store are available publicly to everyone, but if it isn't acceptable, checkout the Microsoft Store for Business.</span></span>  

1. [<span data-ttu-id="8f83f-186">适用于企业的 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="8f83f-186">Microsoft Store for Business</span></span>](https://docs.microsoft.com/microsoft-store/)  
  <span data-ttu-id="8f83f-187">适用于企业和教育的 Microsoft Store 是用于企业环境的自定义商店。</span><span class="sxs-lookup"><span data-stu-id="8f83f-187">Microsoft Store for Business and Education is a custom store for your corporate environment.</span></span>  <span data-ttu-id="8f83f-188">通过该产品，可以使用内置于 Windows 10 和 HoloLens 的 Microsoft Store 为组织查找、获取、分发和管理应用。</span><span class="sxs-lookup"><span data-stu-id="8f83f-188">It lets you use the Microsoft Store built into Windows 10 and HoloLens to find, acquire, distribute, and manage apps for your organization.</span></span>  <span data-ttu-id="8f83f-189">它还可用于部署特定于你的商业环境而不适合公开的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f83f-189">It also lets you deploy apps that are specific to your commercial environment but not to the world.</span></span>

1. <span data-ttu-id="8f83f-190">通过 Intune 或其他移动设备管理解决方案进行应用程序部署和管理</span><span class="sxs-lookup"><span data-stu-id="8f83f-190">Application deployment and management via Intune or another mobile device management solution</span></span>  
  <span data-ttu-id="8f83f-191">大多数移动设备管理解决方案（包括 Intune）提供将业务线应用程序直接部署到一组注册设备的方法。</span><span class="sxs-lookup"><span data-stu-id="8f83f-191">Most mobile device management solutions, including Intune, provide a way to deploy line of business applications directly to a set of enrolled devices.</span></span>  <span data-ttu-id="8f83f-192">请参阅此文章以了解 [Intune 应用安装](https://docs.microsoft.com/intune/apps-deploy)。</span><span class="sxs-lookup"><span data-stu-id="8f83f-192">See this article for [Intune app install](https://docs.microsoft.com/intune/apps-deploy).</span></span>

1. <span data-ttu-id="8f83f-193">_不建议使用_ Device Portal</span><span class="sxs-lookup"><span data-stu-id="8f83f-193">_not recommended_ Device Portal</span></span>  
  <span data-ttu-id="8f83f-194">还可使用 Windows Device Portal 直接在 HoloLens 上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f83f-194">Applications can also be installed on HoloLens directly using the Windows Device Portal.</span></span>  <span data-ttu-id="8f83f-195">不建议这样做，因为必须启用开发人员模式才可使用 Device Portal。</span><span class="sxs-lookup"><span data-stu-id="8f83f-195">This isn't recommended since Developer Mode has to be enabled to use the device portal.</span></span>

<span data-ttu-id="8f83f-196">详细了解如何[在 HoloLens 上安装应用](https://docs.microsoft.com/hololens/hololens-install-apps)。</span><span class="sxs-lookup"><span data-stu-id="8f83f-196">Read more about [installing apps on HoloLens](https://docs.microsoft.com/hololens/hololens-install-apps).</span></span>

### <span data-ttu-id="8f83f-197">证书</span><span class="sxs-lookup"><span data-stu-id="8f83f-197">Certificates</span></span>

<span data-ttu-id="8f83f-198">可通过 MDM 提供商分发证书。</span><span class="sxs-lookup"><span data-stu-id="8f83f-198">You can distribute certificates through your MDM provider.</span></span> <span data-ttu-id="8f83f-199">如果贵公司需要证书，Intune 支持 PKCS、PFX 和 SCEP。</span><span class="sxs-lookup"><span data-stu-id="8f83f-199">If your company requires certificates, Intune supports PKCS, PFX, and SCEP.</span></span> <span data-ttu-id="8f83f-200">了解哪种证书适合公司很重要。</span><span class="sxs-lookup"><span data-stu-id="8f83f-200">It is important to understand which certificate is right for your company.</span></span> <span data-ttu-id="8f83f-201">请访问[证书配置](https://docs.microsoft.com/intune/protect/certificates-configure)文档，以确定最适合你的证书。</span><span class="sxs-lookup"><span data-stu-id="8f83f-201">Please visit the [certificate configurations](https://docs.microsoft.com/intune/protect/certificates-configure) documentation to determine which cert is best for you.</span></span> <span data-ttu-id="8f83f-202">如果计划将证书用于 HoloLens 身份验证，则 PFX 或 SCEP 可能适合你。</span><span class="sxs-lookup"><span data-stu-id="8f83f-202">If you plan to use certificates for HoloLens Authentication, PFX or SCEP may be right for you.</span></span>

<span data-ttu-id="8f83f-203">关于使用 [SCEP](https://docs.microsoft.com/intune/protect/certificates-profile-scep)，请参阅以下步骤。</span><span class="sxs-lookup"><span data-stu-id="8f83f-203">See the following steps for using [SCEP](https://docs.microsoft.com/intune/protect/certificates-profile-scep).</span></span>

### <span data-ttu-id="8f83f-204">如何升级到 Holographics for Business 商业套件</span><span class="sxs-lookup"><span data-stu-id="8f83f-204">How to Upgrade to Holographics for Business Commercial Suite</span></span>

> [!NOTE]
> <span data-ttu-id="8f83f-205">Windows Holographics for Business（商业套件）仅适用于 HoloLens 第 1 代设备。</span><span class="sxs-lookup"><span data-stu-id="8f83f-205">Windows Holographics for Business (commercial suite) is only intended for HoloLens 1st gen devices.</span></span> <span data-ttu-id="8f83f-206">配置文件不会应用于 HoloLens 2 设备。</span><span class="sxs-lookup"><span data-stu-id="8f83f-206">The profile will not be applied to HoloLens 2 devices.</span></span>

<span data-ttu-id="8f83f-207">可以在[全息升级](https://docs.microsoft.com/intune/configuration/holographic-upgrade)文档中找到升级到商业套件的说明。</span><span class="sxs-lookup"><span data-stu-id="8f83f-207">You can find directions for upgrading to the commercial suite in the [holographic upgrade](https://docs.microsoft.com/intune/configuration/holographic-upgrade) documentation.</span></span>

### <span data-ttu-id="8f83f-208">如何使用 Microsoft Intune 配置展台模式</span><span class="sxs-lookup"><span data-stu-id="8f83f-208">How to Configure Kiosk Mode Using Microsoft Intune</span></span>

1. <span data-ttu-id="8f83f-209">将 Microsoft Store 同步到 Intune（请参阅以下[说明 ](https://docs.microsoft.com/intune/apps/windows-store-for-business)）。</span><span class="sxs-lookup"><span data-stu-id="8f83f-209">Sync Microsoft Store to Intune (See the following [instructions](https://docs.microsoft.com/intune/apps/windows-store-for-business)).</span></span>

1. <span data-ttu-id="8f83f-210">检查应用设置</span><span class="sxs-lookup"><span data-stu-id="8f83f-210">Check your app settings</span></span>
    1. <span data-ttu-id="8f83f-211">登录到你的 Microsoft Store 企业帐户</span><span class="sxs-lookup"><span data-stu-id="8f83f-211">Log into your Microsoft Store Business account</span></span>
    1. **<span data-ttu-id="8f83f-212">“管理”>“产品和服务”>“应用和软件”> 选择要同步的应用 > “专用应用商店的可用性”> 选择“每个人”或“特定组”</span><span class="sxs-lookup"><span data-stu-id="8f83f-212">Manage > Products and Services > Apps and Software > Select the app you want to sync > Private Store Availability > Select "Everyone" or "Specific Groups"</span></span>**
        >[!NOTE]
        ><span data-ttu-id="8f83f-213">如果看不到所需的应用，必须通过在应用商店中搜索应用来“获取”该应用。</span><span class="sxs-lookup"><span data-stu-id="8f83f-213">If you don't see the app you want, you will have to "get" the app by searching the store for your app.</span></span> <span data-ttu-id="8f83f-214">**单击右上角的“搜索”栏 > 键入应用程序名称 > 单击应用程序 > 选择 “获取”**。</span><span class="sxs-lookup"><span data-stu-id="8f83f-214">**Click the "Search" bar in the upper right-hand corner > type in the name of the app > click on the app > select "Get"**.</span></span>
    1. <span data-ttu-id="8f83f-215">如果你在 **Intune > 客户端应用 > 应用**，中看不到你的应用，则可能必须再次[同步你的应用](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps)。</span><span class="sxs-lookup"><span data-stu-id="8f83f-215">If you do not see your apps in **Intune > Client Apps > Apps** , you may have to [sync your apps](https://docs.microsoft.com/intune/apps/windows-store-for-business#synchronize-apps) again.</span></span>

1. [<span data-ttu-id="8f83f-216">创建用于展台模式的设备配置文件</span><span class="sxs-lookup"><span data-stu-id="8f83f-216">Create a device profile for Kiosk mode</span></span>](https://docs.microsoft.com/intune/configuration/kiosk-settings#create-the-profile)

> [!NOTE]
> <span data-ttu-id="8f83f-217">通过使用“Azure AD”作为“用户登录类型”，可将不同用户配置为使用不同的展台模式体验。</span><span class="sxs-lookup"><span data-stu-id="8f83f-217">You can configure different users to have different Kiosk Mode experiences by using "Azure AD" as the "User logon type".</span></span> <span data-ttu-id="8f83f-218">但是，此选项仅在多应用展台模式下可用。</span><span class="sxs-lookup"><span data-stu-id="8f83f-218">However, this option is only available in Multi-App kiosk mode.</span></span> <span data-ttu-id="8f83f-219">多应用展台模式适用于单个应用和多个应用。</span><span class="sxs-lookup"><span data-stu-id="8f83f-219">Multi-App kiosk mode will work with only one app as well as multiple apps.</span></span>

![此图显示 Intune 中的展台模式配置](images/aad-kioskmode.png)

<span data-ttu-id="8f83f-221">对于其他 MDM 服务，请参阅提供商文档中的说明。</span><span class="sxs-lookup"><span data-stu-id="8f83f-221">For other MDM services, check your provider's documentation for instructions.</span></span> <span data-ttu-id="8f83f-222">如果需要使用自定义设置和完整 XML 配置在 MDM 服务中设置展台，请参阅 [HoloLens 展台](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)说明。</span><span class="sxs-lookup"><span data-stu-id="8f83f-222">Refer to the [HoloLens kiosk](hololens-kiosk.md#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) instructions if you need to use a custom setting and full XML configuration to set up a kiosk in your MDM service.</span></span>

## <span data-ttu-id="8f83f-223">证书和身份验证</span><span class="sxs-lookup"><span data-stu-id="8f83f-223">Certificates and Authentication</span></span>

<span data-ttu-id="8f83f-224">可通过 MDM 部署证书（请参阅 [MDM 部分](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)的“证书”）。</span><span class="sxs-lookup"><span data-stu-id="8f83f-224">Certificates can be deployed via you MDM (see "certificates" in the [MDM Section](hololens-commercial-infrastructure.md#mobile-device-manager-guidance)).</span></span> <span data-ttu-id="8f83f-225">还可以通过包预配将证书部署到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="8f83f-225">Certificates can also be deployed to the HoloLens through package provisioning.</span></span> <span data-ttu-id="8f83f-226">有关详细信息，请参阅 [HoloLens 预配](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="8f83f-226">Please see [HoloLens Provisioning](hololens-provisioning.md) for additional information.</span></span>

### <span data-ttu-id="8f83f-227">其他 Intune 快速链接</span><span class="sxs-lookup"><span data-stu-id="8f83f-227">Additional Intune Quick Links</span></span>

1. <span data-ttu-id="8f83f-228">[创建配置文件：](https://docs.microsoft.com/intune/configuration/device-profile-create)通过配置文件可以添加和配置将推送到组织内部设备的设置。</span><span class="sxs-lookup"><span data-stu-id="8f83f-228">[Create Profiles:](https://docs.microsoft.com/intune/configuration/device-profile-create) Profiles allow you to add and configure settings that will be pushed to the devices in your organization.</span></span>

