---
title: 在 MDM 中注册 HoloLens
description: 了解如何在移动设备管理中注册 HoloLens (MDM) 更轻松地管理多个设备。
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
ms.openlocfilehash: 5613c69bda8bbf70722a050ac5ce4ebeab95d332
ms.sourcegitcommit: 771e53feefbcc6bce18577515ad7d3f6a7f33840
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399380"
---
# <a name="enroll-hololens-in-mdm"></a><span data-ttu-id="510a1-103">在 MDM 中注册 HoloLens</span><span class="sxs-lookup"><span data-stu-id="510a1-103">Enroll HoloLens in MDM</span></span>

<span data-ttu-id="510a1-104">可以使用 Microsoft [Intune](https://docs.microsoft.com/intune/windows-holographic-for-business)等解决方案同时管理多个 Microsoft HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="510a1-104">You can manage multiple Microsoft HoloLens devices simultaneously using solutions like [Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business).</span></span> <span data-ttu-id="510a1-105">你将能够管理设置，选择要安装的应用，并设置根据你的组织需要定制的安全配置。</span><span class="sxs-lookup"><span data-stu-id="510a1-105">You will be able to manage settings, select apps to install and set security configurations tailored to your organization's need.</span></span> <span data-ttu-id="510a1-106">请参阅[使用 Microsoft Intune 管理运行 Windows Holographic 的设备](https://docs.microsoft.com/intune/windows-holographic-for-business)、[Windows Holographic 中支持的配置服务提供程序(CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens) 和 [Windows Holographic for Business 支持的策略](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies)。</span><span class="sxs-lookup"><span data-stu-id="510a1-106">See [Manage devices running Windows Holographic with Microsoft Intune](https://docs.microsoft.com/intune/windows-holographic-for-business), the [configuration service providers (CSPs) that are supported in Windows Holographic](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference#hololens), and the [policies supported by Windows Holographic for Business](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#hololenspolicies).</span></span>

> [!NOTE]
> <span data-ttu-id="510a1-107">移动设备管理 (MDM)（包括 VPN、Bitlocker 和展台模式功能）仅在[升级到 Windows Holographic for Business](hololens1-upgrade-enterprise.md) 时才可用。</span><span class="sxs-lookup"><span data-stu-id="510a1-107">Mobile device management (MDM), including the VPN, Bitlocker, and kiosk mode features, is only available when you [upgrade to Windows Holographic for Business](hololens1-upgrade-enterprise.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="510a1-108">要求</span><span class="sxs-lookup"><span data-stu-id="510a1-108">Requirements</span></span>

 <span data-ttu-id="510a1-109">组织需要设置移动设备管理 (MDM) 才能管理 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="510a1-109">Your organization will need to have Mobile Device Management (MDM) set up in order to manage HoloLens devices.</span></span> <span data-ttu-id="510a1-110">你的 MDM 提供程序可以是 Microsoft Intune 或使用 Microsoft MDM API 的第三方提供程序。</span><span class="sxs-lookup"><span data-stu-id="510a1-110">Your MDM provider can be Microsoft Intune or a 3rd party provider that uses Microsoft MDM APIs.</span></span>
 
## <a name="different-ways-to-enroll"></a><span data-ttu-id="510a1-111">注册的不同方法</span><span class="sxs-lookup"><span data-stu-id="510a1-111">Different ways to enroll</span></span>

<span data-ttu-id="510a1-112">根据在 OOBE 或登录后选择的标识类型，存在不同的注册方法。</span><span class="sxs-lookup"><span data-stu-id="510a1-112">Depending on the type of identity chosen either during OOBE or post sign-in there are different methods of enrollment.</span></span> <span data-ttu-id="510a1-113">若要了解有关 HoloLens 上每种类型的标识的信息，请访问 [此页面](hololens-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="510a1-113">To learn more about each type of Identity on HoloLens please visit [this page](hololens-identity.md).</span></span>

- <span data-ttu-id="510a1-114">如果 Identity 为 Azure AD，则 OOBE 或"设置应用访问工作"\*\*\*\*  ->  **或"学校连接"按钮**  ->  **期间**。</span><span class="sxs-lookup"><span data-stu-id="510a1-114">If Identity is Azure AD, then either during OOBE or **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="510a1-115">对于 Azure AD，只有当 Azure AD 已配置注册 URL 时，才进行自动 MDM 注册。</span><span class="sxs-lookup"><span data-stu-id="510a1-115">For Azure AD, automatic MDM enrollment only occurs if Azure AD has been configured with enrollment URLs.</span></span>
- <span data-ttu-id="510a1-116">如果 Identity 为 Azure AD，并且设备已在 Intune MDM 服务器中预先注册并分配了特定配置文件，则 Azure AD-Join 和注册将在 OOBE 期间自动发生。</span><span class="sxs-lookup"><span data-stu-id="510a1-116">If Identity is Azure AD and device has been pre-registered with Intune MDM server with specific configuration profile assigned to it, then Azure AD-Join and enrollment will automatically occur during OOBE.</span></span>
    - <span data-ttu-id="510a1-117">也称为 [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ 版本](hololens-release-notes.md#windows-holographic-version-2004)。</span><span class="sxs-lookup"><span data-stu-id="510a1-117">Also called [Autopilot flow](hololens2-autopilot.md) Available in [19041.1103+ builds](hololens-release-notes.md#windows-holographic-version-2004).</span></span>
- <span data-ttu-id="510a1-118">如果 Identity 为 MSA，则使用"设置**应用**  ->  **访问工作"或"学校**  ->  **连接"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="510a1-118">If Identity is MSA, then using **Settings App** -> **Access Work or School** -> **Connect** button.</span></span>
    - <span data-ttu-id="510a1-119">也称为"添加工作帐户 (AWA) 流。</span><span class="sxs-lookup"><span data-stu-id="510a1-119">Also called Add Work Account (AWA) flow.</span></span>
- <span data-ttu-id="510a1-120">如果 Identity 为本地用户，**则仅在设备**管理链接中使用"设置应用访问工作  ->  \*\*\*\*  ->  **"或"学校注册**"。</span><span class="sxs-lookup"><span data-stu-id="510a1-120">If Identity is Local User, then using **Settings App** -> **Access Work or School** -> **Enroll only in device management** link.</span></span>
    - <span data-ttu-id="510a1-121">也称为纯 MDM 注册流。</span><span class="sxs-lookup"><span data-stu-id="510a1-121">Also called pure MDM enrollment flow.</span></span>

<span data-ttu-id="510a1-122">设备注册 MDM 服务器后，"设置"应用现在将反映设备已注册到设备管理中。</span><span class="sxs-lookup"><span data-stu-id="510a1-122">Once the device is enrolled with your MDM server, the Settings app will now reflect that the device is enrolled in device management.</span></span>

## <a name="auto-enrollment-in-mdm"></a><span data-ttu-id="510a1-123">在 MDM 中自动注册</span><span class="sxs-lookup"><span data-stu-id="510a1-123">Auto-enrollment in MDM</span></span>

<span data-ttu-id="510a1-124">如果你的组织使用 Azure Active Directory (Azure AD) 和接受 Azure AD 令牌进行身份验证的 MDM 解决方案 (目前仅在 Microsoft Intune 和 AirWatch) 中受支持，则 IT 管理员可以将 Azure AD 配置为在用户使用其 Azure AD 帐户登录后自动允许 MDM 注册。</span><span class="sxs-lookup"><span data-stu-id="510a1-124">If your organization uses Azure Active Directory (Azure AD) and an MDM solution that accepts an Azure AD token for authentication (currently, only supported in Microsoft Intune and AirWatch), your IT admin can configure Azure AD to automatically allow MDM enrollment after the user signs in with their Azure AD account.</span></span> [<span data-ttu-id="510a1-125">了解如何配置 Azure AD 注册。</span><span class="sxs-lookup"><span data-stu-id="510a1-125">Learn how to configure Azure AD enrollment.</span></span>](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)

<span data-ttu-id="510a1-126">启用自动注册后，不需要其他手动注册。</span><span class="sxs-lookup"><span data-stu-id="510a1-126">When auto-enrollment is enabled, no additional manual enrollment is needed.</span></span> <span data-ttu-id="510a1-127">当用户使用 Azure AD 帐户登录时，设备在完成首次运行体验后在 MDM 中注册。</span><span class="sxs-lookup"><span data-stu-id="510a1-127">When the user signs in with an Azure AD account, the device is enrolled in MDM after completing the first-run experience.</span></span>

<span data-ttu-id="510a1-128">当设备已加入 Azure AD 时，可能会影响被视为设备 [所有者的人](security-adminless-os.md#device-owner)。</span><span class="sxs-lookup"><span data-stu-id="510a1-128">When a device is Azure AD Joined it may affect who considered the [device owner](security-adminless-os.md#device-owner).</span></span>

## <a name="unenroll-hololens-from-intune"></a><span data-ttu-id="510a1-129">从 Intune 注销 HoloLens</span><span class="sxs-lookup"><span data-stu-id="510a1-129">Unenroll HoloLens from Intune</span></span>

<span data-ttu-id="510a1-130">尽管 HoloLens 2 是 Windows 10 设备，但无法简单地从 Intune 注销。</span><span class="sxs-lookup"><span data-stu-id="510a1-130">Although HoloLens 2 is Windows 10 device, it cannot be simply unenrolled from Intune.</span></span> <span data-ttu-id="510a1-131">如果你希望从 Azure AD 中取消加入 HoloLens 或重新加入其他 Azure AD 租户，则必须重置 [/重新调整](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) 设备。</span><span class="sxs-lookup"><span data-stu-id="510a1-131">If you wish to unjoin HoloLens from Azure AD or rejoin it to a different to Azure AD tenant, you must [reset/reflash](https://docs.microsoft.com/hololens/hololens-recovery#reset-the-device) the device.</span></span>