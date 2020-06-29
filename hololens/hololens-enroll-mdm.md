---
title: 在 MDM 中注册 HoloLens
description: 在移动设备管理 (MDM) 中注册 HoloLens，以便轻松管理多个设备。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 07/15/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 054c4ded7496957671c055e3161a1297de7abc1a
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827683"
---
# <span data-ttu-id="eb290-103">在 MDM 中注册 HoloLens</span><span class="sxs-lookup"><span data-stu-id="eb290-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="eb290-104">你可以使用[Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等解决方案同时管理多个 Microsoft HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="eb290-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="eb290-105">你将能够管理设置，选择要安装的应用，并设置根据你的组织需要定制的安全配置。</span><span class="sxs-lookup"><span data-stu-id="eb290-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="eb290-106">请参阅[使用 Microsoft Intune 管理运行 Windows Holographic 的设备](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支持的配置服务提供程序(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 和 [Windows Holographic for Business 支持的策略](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。</span><span class="sxs-lookup"><span data-stu-id="eb290-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="eb290-107">移动设备管理 (MDM)（包括 VPN、Bitlocker 和展台模式功能）仅在[升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 时才可用。</span><span class="sxs-lookup"><span data-stu-id="eb290-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="eb290-108">要求</span><span class="sxs-lookup"><span data-stu-id="eb290-108">Requirements</span></span>

 <span data-ttu-id="eb290-109">你的组织需要设置移动设备管理（MDM）才能管理 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="eb290-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="eb290-110">你的 MDM 提供程序可以是 Microsoft Intune 或使用 Microsoft MDM API 的第三方提供程序。</span><span class="sxs-lookup"><span data-stu-id="eb290-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>

## <span data-ttu-id="eb290-111">在 MDM 中自动注册</span><span class="sxs-lookup"><span data-stu-id="eb290-111">Auto-enrollment in MDM</span></span>

<span data-ttu-id="eb290-112">如果你的组织使用 Azure Active Directory (Azure AD) 和接受 AAD 令牌的 MDM 解决方案进行身份验证（目前仅在 Microsoft Intune 和 AirWatch 中支持），则 IT 管理员可以配置 Azure AD，以在用户使用其 Azure AD 帐户登录后自动允许 MDM 注册。</span><span class="sxs-lookup"><span data-stu-id="eb290-112">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an AAD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="eb290-113">了解如何配置 Azure AD 注册。</span><span class="sxs-lookup"><span data-stu-id="eb290-113">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="eb290-114">启用自动注册后，不需要其他手动注册。</span><span class="sxs-lookup"><span data-stu-id="eb290-114">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="eb290-115">当用户使用 Azure AD 帐户登录时，设备在完成首次运行体验后在 MDM 中注册。</span><span class="sxs-lookup"><span data-stu-id="eb290-115">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

## <span data-ttu-id="eb290-116">通过“设置”应用进行注册</span><span class="sxs-lookup"><span data-stu-id="eb290-116">Enroll through Settings app</span></span>

 <span data-ttu-id="eb290-117">当设备在首次运行体验期间未注册时，用户可以使用“设置”应用通过组织的 MDM 服务器手动注册设备。</span><span class="sxs-lookup"><span data-stu-id="eb290-117">When the device is not enrolled in MDM during the first-run experience, the user can manually enroll the device with the organization's MDM server using the Settings app.</span></span>

1. <span data-ttu-id="eb290-118">转到**设置** > **帐户** > **工作访问**。</span><span class="sxs-lookup"><span data-stu-id="eb290-118">Go to **Settings** > **Accounts** > **Work access**.</span></span>
1. <span data-ttu-id="eb290-119">选择**注册到设备管理**，然后输入你的组织帐户。</span><span class="sxs-lookup"><span data-stu-id="eb290-119">Select **Enroll into device management** and enter your organizational account.</span></span> <span data-ttu-id="eb290-120">你将被重定向到你的组织登录页。</span><span class="sxs-lookup"><span data-stu-id="eb290-120">You will be redirected to your organization's sign in page.</span></span>
1. <span data-ttu-id="eb290-121">成功对 MDM 服务器进行身份验证后，会显示成功的消息。</span><span class="sxs-lookup"><span data-stu-id="eb290-121">Upon successful authentication to the MDM server, a success message is shown.</span></span>

<span data-ttu-id="eb290-122">你的设备现在已注册 MDM 服务器。</span><span class="sxs-lookup"><span data-stu-id="eb290-122">Your device is now enrolled with your MDM server.</span></span> <span data-ttu-id="eb290-123">现在，“设置”应用将反映设备已在设备管理中注册。</span><span class="sxs-lookup"><span data-stu-id="eb290-123">The Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="eb290-124">从 Intune 取消 HoloLens</span><span class="sxs-lookup"><span data-stu-id="eb290-124">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="eb290-125">你无法从 Intune 远程[取消注册](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) HoloLens。</span><span class="sxs-lookup"><span data-stu-id="eb290-125">You cannot [unenroll](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-windows) HoloLens from Intune remotely.</span></span> <span data-ttu-id="eb290-126">如果管理员使用 MDM 取消注册设备，则设备将从 Intune 仪表板中脱离。</span><span class="sxs-lookup"><span data-stu-id="eb290-126">If the administrator unenrolls the device using MDM, the device will age out of the Intune dashboard.</span></span>
