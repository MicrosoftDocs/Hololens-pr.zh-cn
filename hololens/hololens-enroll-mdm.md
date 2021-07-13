---
title: 在 MDM 中注册 HoloLens
description: 了解如何在移动设备管理HoloLens MDM (注册) ，以便更轻松地管理多个设备。
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
ms.openlocfilehash: 6c279664fa6051fab2f5e2e8f61e70b55704ae7c
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640400"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="14d91-103">在 MDM 中注册 HoloLens</span><span class="sxs-lookup"><span data-stu-id="14d91-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="14d91-104">可以使用 Microsoft HoloLens Microsoft Intune 等解决方案同时管理多个 Microsoft Intune[设备。](/intune/windows-holographic-for-business)</span><span class="sxs-lookup"><span data-stu-id="14d91-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="14d91-105">你将能够管理设置，选择要安装的应用，并设置根据你的组织需要定制的安全配置。</span><span class="sxs-lookup"><span data-stu-id="14d91-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="14d91-106">请参阅[使用 Microsoft Intune 管理运行 Windows Holographic 的设备](/intune/windows-holographic-for-business)、[Windows Holographic 中支持的配置服务提供程序(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 和 [Windows Holographic for Business 支持的策略](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。</span><span class="sxs-lookup"><span data-stu-id="14d91-106">See [Manage devices running Windows Holographic with Microsoft Intune](/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="14d91-107">移动设备管理 (MDM)（包括 VPN、Bitlocker 和展台模式功能）仅在[升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 时才可用。</span><span class="sxs-lookup"><span data-stu-id="14d91-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="14d91-108">要求</span><span class="sxs-lookup"><span data-stu-id="14d91-108">Requirements</span></span>

 <span data-ttu-id="14d91-109">组织需要设置 Mobile 设备管理 (MDM) 才能管理HoloLens设备。</span><span class="sxs-lookup"><span data-stu-id="14d91-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="14d91-110">你的 MDM 提供程序可以是 Microsoft Intune 或使用 Microsoft MDM API 的第三方提供程序。</span><span class="sxs-lookup"><span data-stu-id="14d91-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="14d91-111">注册的不同方法</span><span class="sxs-lookup"><span data-stu-id="14d91-111">Different ways to enroll</span></span>

<span data-ttu-id="14d91-112">根据在 OOBE 或登录后选择的标识类型，有不同的注册方法。 [](hololens-identity.md)</span><span class="sxs-lookup"><span data-stu-id="14d91-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="14d91-113">如果标识Azure AD，则 OOBE 或 设置 **应用** 访问  ->  **工作或学校连接**  ->  按钮。</span><span class="sxs-lookup"><span data-stu-id="14d91-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="14d91-114">例如 [Azure AD，只有在](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 已使用注册 URL 配置Azure AD MDM 注册时，才进行自动 MDM 注册。</span><span class="sxs-lookup"><span data-stu-id="14d91-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="14d91-115">如果标识Azure AD且设备已预先注册到分配有特定配置文件的 Intune MDM 服务器，则 Azure AD-Join 和自动 [MDM](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 注册将在 OOBE 期间进行。</span><span class="sxs-lookup"><span data-stu-id="14d91-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="14d91-116">也称为 [Autopilot 流](hololens2-autopilot.md) 在 [19041.1103+ 内部版本中可用](hololens-release-notes.md#windows-holographic-version-2004)。</span><span class="sxs-lookup"><span data-stu-id="14d91-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="14d91-117">如果"标识"为 MSA，则  ->  **设置"应用访问工作或学校连接**  ->  按钮。</span><span class="sxs-lookup"><span data-stu-id="14d91-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="14d91-118">也称为将工作帐户 (AWA) 流。</span><span class="sxs-lookup"><span data-stu-id="14d91-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="14d91-119">如果"标识"是本地用户，**则设置"** 应用访问  ->  **工作或** 学校注册  ->  **"链接**。</span><span class="sxs-lookup"><span data-stu-id="14d91-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="14d91-120">也称为纯 MDM 注册流。</span><span class="sxs-lookup"><span data-stu-id="14d91-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="14d91-121">向 MDM 服务器注册设备后，设置应用将反映设备已注册到设备管理中。</span><span class="sxs-lookup"><span data-stu-id="14d91-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="14d91-122">在 MDM 中自动注册</span><span class="sxs-lookup"><span data-stu-id="14d91-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="14d91-123">如果组织具有[Azure 高级版](https://azure.microsoft.com/overview/)订阅 ，则 使用 Azure Active Directory (Azure AD) 和 MDM 解决方案，该解决方案接受 Azure AD 令牌进行身份验证 (（目前仅在 Microsoft Intune 和 AirWatch) 中受支持）时，IT 管理员可以将 Azure AD 配置为在用户使用其 Azure AD 帐户登录后自动允许 MDM 注册。</span><span class="sxs-lookup"><span data-stu-id="14d91-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="14d91-124">了解如何配置 Azure AD 注册。</span><span class="sxs-lookup"><span data-stu-id="14d91-124">Learn how to configure Azure AD enrollment.</span></span>](/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="14d91-125">启用自动注册后，无需额外的手动注册。</span><span class="sxs-lookup"><span data-stu-id="14d91-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="14d91-126">当用户使用 Azure AD 帐户登录时，设备在完成首次运行体验后在 MDM 中注册。</span><span class="sxs-lookup"><span data-stu-id="14d91-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="14d91-127">如果设备已Azure AD，则可能会影响将设备所有者 [视为的所有者](security-adminless-os.md#device-owner)。</span><span class="sxs-lookup"><span data-stu-id="14d91-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="14d91-128">从 Intune HoloLens取消注册</span><span class="sxs-lookup"><span data-stu-id="14d91-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="14d91-129">根据注册方法，取消注册设备可能不可用。</span><span class="sxs-lookup"><span data-stu-id="14d91-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="14d91-130">如果设备已注册到 Azure AD 或 Autopilot，则不能从 Intune 取消注册。</span><span class="sxs-lookup"><span data-stu-id="14d91-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="14d91-131">如果要从 HoloLens取消Azure AD或重新加入其他租户Azure AD，则必须[重置/重新运行](hololens-recovery.md#reset-the-device)设备。</span><span class="sxs-lookup"><span data-stu-id="14d91-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](hololens-recovery.md#reset-the-device) the device.</span></span>

<span data-ttu-id="14d91-132">如果设备从添加了工作帐户的 MSA 帐户注册，或者从仅在设备管理中注册的本地帐户注册，则你可以取消注册该设备。</span><span class="sxs-lookup"><span data-stu-id="14d91-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="14d91-133">打开""开始"菜单"，然后选择"设置"应用访问  ->  **工作或学校**  ->  *YourAccount*  ->  **断开连接"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="14d91-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>