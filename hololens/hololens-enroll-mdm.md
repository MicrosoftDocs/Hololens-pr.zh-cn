---
title: 在 MDM 中注册 HoloLens
description: 了解如何在移动设备管理 (MDM) 中注册 HoloLens，以便更轻松地管理多个设备。
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
ms.openlocfilehash: 624ebd17335820b1d2858f9d39cabb7032a83bfe
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308469"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="ec4e3-103">在 MDM 中注册 HoloLens</span><span class="sxs-lookup"><span data-stu-id="ec4e3-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="ec4e3-104">你可以使用 [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等解决方案同时管理多个 Microsoft HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="ec4e3-105">你将能够管理设置，选择要安装的应用，并设置根据你的组织需要定制的安全配置。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="ec4e3-106">请参阅[使用 Microsoft Intune 管理运行 Windows Holographic 的设备](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支持的配置服务提供程序(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 和 [Windows Holographic for Business 支持的策略](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="ec4e3-107">移动设备管理 (MDM)（包括 VPN、Bitlocker 和展台模式功能）仅在[升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 时才可用。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="ec4e3-108">要求</span><span class="sxs-lookup"><span data-stu-id="ec4e3-108">Requirements</span></span>

 <span data-ttu-id="ec4e3-109">你的组织需要 (MDM) 设置移动设备管理，以便管理 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="ec4e3-110">你的 MDM 提供程序可以是 Microsoft Intune 或使用 Microsoft MDM API 的第三方提供程序。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="ec4e3-111">注册的不同方法</span><span class="sxs-lookup"><span data-stu-id="ec4e3-111">Different ways to enroll</span></span>

<span data-ttu-id="ec4e3-112">根据在 OOBE 或 post 登录期间选择的 [标识](hololens-identity.md) 类型，有不同的注册方法。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-112">Depending on the type of [identity](hololens-identity.md) chosen either during OOBE or post sign-in, there are different methods of enrollment.</span></span>

- <span data-ttu-id="ec4e3-113">如果 Azure AD，则在 OOBE 期间或 **设置应用**  ->  **访问工作或学校**  ->  **连接** 按钮。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-113">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="ec4e3-114">对于 Azure AD，仅当 Azure AD 配置了注册 Url 时才会进行 [自动 MDM 注册](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-114">For Azure AD, [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) only occurs if Azure AD has been configured with enrollment URLs.</span></span>
     
- <span data-ttu-id="ec4e3-115">如果标识是 Azure AD 的，并且设备已预先向分配了特定配置文件的 Intune MDM 服务器注册，则 Azure AD-Join 和 [自动 MDM 注册](hololens-enroll-mdm.md#auto-enrollment-in-mdm) 将在 OOBE 期间进行。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-115">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and [automatic MDM enrollment](hololens-enroll-mdm.md#auto-enrollment-in-mdm) will occur during OOBE.</span></span>
    - <span data-ttu-id="ec4e3-116">也称为[19041.1103 + build](hololens-release-notes.md#windows-holographic-version-2004)中的[Autopilot 流](hololens2-autopilot.md)。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-116">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
    

- <span data-ttu-id="ec4e3-117">如果标识为 MSA，则使用 **设置应用**  ->  **访问工作或学校**  ->  **连接** 按钮。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-117">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="ec4e3-118">也称为添加工作帐户 (AWS) flow。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-118">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="ec4e3-119">如果 "标识" 为本地用户，则使用 "设置" "**应用**  ->  **访问工作" 或**  ->  **"仅在设备管理中注册"** 链接。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-119">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="ec4e3-120">也称为纯 MDM 注册流。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-120">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="ec4e3-121">设备注册到 MDM 服务器后，"设置" 应用将立即反映设备是否已在 "设备管理" 中注册。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-121">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="ec4e3-122">在 MDM 中自动注册</span><span class="sxs-lookup"><span data-stu-id="ec4e3-122">Auto-enrollment in MDM</span></span>

<span data-ttu-id="ec4e3-123">如果你的组织具有 [Azure Premium 订阅](https://azure.microsoft.com/overview/)，则使用 Azure Active Directory (Azure AD) ，并使用接受 Azure AD 令牌进行身份验证的 MDM 解决方案 (目前仅支持 Microsoft Intune 和 AirWatch) 中的 Azure AD，你的 IT 管理员可以将 Azure AD 配置为在用户使用其帐户登录后自动允许 MDM 注册。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-123">If your organization has an [Azure Premium subscription](https://azure.microsoft.com/overview/), is using Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="ec4e3-124">了解如何配置 Azure AD 注册。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-124">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="ec4e3-125">启用自动注册后，无需进行额外的手动注册。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-125">When auto-enrollment is enabled, no extra manual enrollment is needed.</span></span> <span data-ttu-id="ec4e3-126">当用户使用 Azure AD 帐户登录时，设备在完成首次运行体验后在 MDM 中注册。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-126">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="ec4e3-127">Azure AD 联接设备时，可能会影响被认为是 [设备所有者](security-adminless-os.md#device-owner)的用户。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-127">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="ec4e3-128">从 Intune 取消注册 HoloLens</span><span class="sxs-lookup"><span data-stu-id="ec4e3-128">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="ec4e3-129">根据注册方法，取消注册设备可能不可用。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-129">Depending on the enrollment method, unenrolling your device may not be available.</span></span>

<span data-ttu-id="ec4e3-130">如果设备已使用 Azure AD 帐户或 Autopilot 注册，则无法从 Intune 取消注册。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-130">If your device was enrolled with an Azure AD account or Autopilot, it cannot be unenrolled from Intune.</span></span> <span data-ttu-id="ec4e3-131">如果要从 Azure AD 中脱离 HoloLens，或将其重新加入到 Azure AD 租户以外的其他设备，则必须 [重置/刷新](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) 设备。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) the device.</span></span>

<span data-ttu-id="ec4e3-132">如果设备是从添加了工作帐户的 MSA 帐户或从仅在设备管理中注册的本地帐户注册的，则可以取消注册设备。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-132">If your device was enrolled from a MSA account that added a work account or from a Local account that enrolled only in device management, then you may unenroll the device.</span></span> <span data-ttu-id="ec4e3-133">打开 "开始" 菜单，然后选择 "设置" "**应用**  ->  **访问工作或学校**  ->  *YourAccount*  ->  **断开连接**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="ec4e3-133">Open the Start menu and then select **Settings App** -> **Access Work or School** -> *YourAccount* -> **Disconnect** button.</span></span>