---
title: 在 MDM 中注册 HoloLens
description: 了解如何在 MDM (mdm) 注册 HoloLens，以便更轻松地管理多台设备。
ms.prod: hololens
ms.sitesec: library
ms.assetid: 2a9b3fca-8370-44ec-8b57-fb98b8d317b0
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/06/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: b9473f4e80f6438ef4c438711ac0de342c5327e1
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283183"
---
# <span data-ttu-id="d3fa6-103">在 MDM 中注册 HoloLens</span><span class="sxs-lookup"><span data-stu-id="d3fa6-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="d3fa6-104">可以使用 Microsoft [Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等解决方案同时管理多个 Microsoft HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="d3fa6-105">你将能够管理设置，选择要安装的应用，并设置根据你的组织需要定制的安全配置。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="d3fa6-106">请参阅[使用 Microsoft Intune 管理运行 Windows Holographic 的设备](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支持的配置服务提供程序(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 和 [Windows Holographic for Business 支持的策略](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="d3fa6-107">移动设备管理 (MDM)（包括 VPN、Bitlocker 和展台模式功能）仅在[升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 时才可用。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <span data-ttu-id="d3fa6-108">要求</span><span class="sxs-lookup"><span data-stu-id="d3fa6-108">Requirements</span></span>

 <span data-ttu-id="d3fa6-109">你的组织将需要设置移动设备管理 (MDM) 才能管理 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="d3fa6-110">你的 MDM 提供程序可以是 Microsoft Intune 或使用 Microsoft MDM API 的第三方提供程序。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <span data-ttu-id="d3fa6-111">注册的不同方法</span><span class="sxs-lookup"><span data-stu-id="d3fa6-111">Different ways to enroll</span></span>

<span data-ttu-id="d3fa6-112">根据在 OOBE 或登录后选择的标识类型，存在不同的注册方法。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="d3fa6-113">若要了解有关 HoloLens 上每种标识类型的信息，请访问 [此页面](hololens-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="d3fa6-114">如果 Identity 为 Azure AD，则 OOBE 或"设置应用**访问工作或**  ->  **学校连接"按钮**  ->  \*\*\*\* 期间。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-114">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="d3fa6-115">对于 Azure AD，只有当 Azure AD 已配置有注册 URL 时，才能进行自动 MDM 注册。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-115">For Azure AD, automatic MDM enrollment only occurs if Azure AD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="d3fa6-116">如果 Identity 为 Azure AD，并且设备已在 Intune MDM 服务器中预注册，并且已为其分配了特定配置文件，则 Azure AD-Join 注册将在 OOBE 期间自动进行。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-116">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="d3fa6-117">也称为 [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ 版本](hololens-release-notes.md#windows-holographic-version-2004)。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="d3fa6-118">如果 Identity 为 MSA，则使用"设置**应用**  ->  **访问工作或学校连接"**  ->  \*\*\*\* 按钮。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="d3fa6-119">也称为将工作帐户 (AWA) 流。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="d3fa6-120">如果 Identity 为本地用户，则仅在设备管理链接中使用"设置**应用**访问工作  ->  \*\*\*\*  ->  **"或"学校注册**"。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="d3fa6-121">也称为纯 MDM 注册流。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="d3fa6-122">设备注册 MDM 服务器后，"设置"应用现在将反映设备已注册到设备管理中。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <span data-ttu-id="d3fa6-123">在 MDM 中自动注册</span><span class="sxs-lookup"><span data-stu-id="d3fa6-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="d3fa6-124">如果你的组织使用 Azure Active Directory (Azure AD) 以及接受 Azure AD 令牌进行身份验证 (（仅在 Microsoft Intune 和 AirWatch) 中支持）的 MDM 解决方案，则 IT 管理员可以将 Azure AD 配置为在用户使用其 Azure AD 帐户登录后自动允许 MDM 注册。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="d3fa6-125">了解如何配置 Azure AD 注册。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="d3fa6-126">启用自动注册后，不需要其他手动注册。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="d3fa6-127">当用户使用 Azure AD 帐户登录时，设备在完成首次运行体验后在 MDM 中注册。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="d3fa6-128">当设备已加入 Azure AD 时，可能会影响被视为设备 [所有者的人](security-adminless-os.md#device-owner)。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-128">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <span data-ttu-id="d3fa6-129">从 Intune 中注销 HoloLens</span><span class="sxs-lookup"><span data-stu-id="d3fa6-129">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="d3fa6-130">若要了解有关注销设备的信息，请访问 [此页面](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment)。</span><span class="sxs-lookup"><span data-stu-id="d3fa6-130">To learn more about unenrolling a device visit [this page](https://docs.microsoft.com/windows/client-management/mdm/disconnecting-from-mdm-unenrollment).</span></span> 
