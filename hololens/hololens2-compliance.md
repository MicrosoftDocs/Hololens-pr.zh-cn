---
title: HoloLens 2相容性和 GDPR
description: GDPR 文档
keywords: HoloLens、GDPR、隐私、PII
author: joyjaz
ms.author: v-jjaswinski
ms.reviewer: skerewala, evmiller
ms.date: 02/05/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 684a97a4fcdc3aaf830f164c54fb3079e296c78c
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113637109"
---
# <a name="hololens-2-privacy-statement"></a><span data-ttu-id="0c3fc-104">HoloLens 2 隐私声明</span><span class="sxs-lookup"><span data-stu-id="0c3fc-104">HoloLens 2 Privacy Statement</span></span>

<span data-ttu-id="0c3fc-105">GDPR 的核心元素之一是 "按设计数据保护"。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-105">One of the core elements of the GDPR is ‘data protection by design’.</span></span> <span data-ttu-id="0c3fc-106">此概念特别适用于移动设备（如 HoloLens 2），因为其可移植性、无限制 internet 连接和开放的通信通道。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-106">This concept especially applies to mobile devices, like the HoloLens 2, because of their portability, unlimited internet connections and open communication channels.</span></span> <span data-ttu-id="0c3fc-107">Resultingly，已对 HoloLens 2 的[安全性](/hololens/security-architecture)进行了重新设计，以提供一种端到端的高级、创新的安全和隐私保护，同时结合了 Microsoft 的[隐私和 GDPR 法规](https://privacy.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-107">Resultingly, the HoloLens 2’s [security](/hololens/security-architecture) has been redesigned to provide advanced, innovative security and privacy protection, end-to-end, incorporating both Microsoft’s approach to [privacy and GDPR regulations](https://privacy.microsoft.com/).</span></span>

 >[!NOTE]
> <span data-ttu-id="0c3fc-108">本文档不适用于 (第一代) HoloLens。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-108">This document does not apply to HoloLens (1st gen).</span></span>

## <a name="privacy-overview"></a><span data-ttu-id="0c3fc-109">隐私概述</span><span class="sxs-lookup"><span data-stu-id="0c3fc-109">Privacy Overview</span></span>

<span data-ttu-id="0c3fc-110">HoloLens 2 是一台独立的 Windows 计算机，运行 Windows 全息版，可在沉浸式现实环境中运行应用和解决方案。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-110">HoloLens 2 is a self-contained Windows computer, running Windows Holographic, that runs apps and solutions in an immersive mixed reality environment.</span></span> <span data-ttu-id="0c3fc-111">它可用作安全的脱机设备，或部署为组织内的 [托管设备](/mem/intune/fundamentals/windows-holographic-for-business) 。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-111">It can be used as a secure offline device or deployed as a [managed device](/mem/intune/fundamentals/windows-holographic-for-business) within your organization.</span></span> <span data-ttu-id="0c3fc-112">请参阅以下链接，了解 HoloLens 2 和 Microsoft 如何使用和保护你的数据：</span><span class="sxs-lookup"><span data-stu-id="0c3fc-112">See the following links to understand how the HoloLens 2 and Microsoft uses and protects your data:</span></span>

1. <span data-ttu-id="0c3fc-113">[Microsoft 隐私声明-HoloLens](https://privacy.microsoft.com/privacystatement) -展开左侧导航菜单中的 " **Enterprise 和开发人员**" 部分，然后选择 " **Enterprise 和开发人员软件和设备**"。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-113">[Microsoft Privacy Statement - HoloLens](https://privacy.microsoft.com/privacystatement) – expand the **Enterprise and developer** section in the left navigation menu and select **Enterprise and developer software and appliances**.</span></span> <span data-ttu-id="0c3fc-114">请参阅 **HoloLens** 部分。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-114">Go to the **HoloLens** section.</span></span>
2. [<span data-ttu-id="0c3fc-115">Windows 10 和联机服务</span><span class="sxs-lookup"><span data-stu-id="0c3fc-115">Windows 10 and your online services</span></span>](https://privacy.microsoft.com/windows10privacy)
3. [<span data-ttu-id="0c3fc-116">Windows 10 & 隐私符合性指南</span><span class="sxs-lookup"><span data-stu-id="0c3fc-116">Windows 10 & Privacy Compliance Guide</span></span>](/windows/privacy/windows-10-and-privacy-compliance)
4. [<span data-ttu-id="0c3fc-117">Intune 中的隐私和个人数据</span><span class="sxs-lookup"><span data-stu-id="0c3fc-117">Privacy and personal data in Intune</span></span>](/mem/intune/protect/privacy-personal-data)

## <a name="network-security"></a><span data-ttu-id="0c3fc-118">网络安全</span><span class="sxs-lookup"><span data-stu-id="0c3fc-118">Network Security</span></span>
<span data-ttu-id="0c3fc-119">按照 HoloLens 2[常见的部署方案](/hololens/common-scenarios)，你的数据将受到[Azure 世界一流的法规遵从性](/azure/compliance/)以及法律/法规标准集成的保护。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-119">Following the HoloLens 2 [Common Deployment Scenarios](/hololens/common-scenarios), your data will be protected by [Azure’s world-class compliance](/azure/compliance/) along with legal/regulatory standards integration.</span></span> <span data-ttu-id="0c3fc-120">如果不熟悉 Azure AD 和 Dynamics 365 Remote Assist，请参阅 GDPR 的[Azure 和 Dynamics 365 责任准备情况清单](/compliance/regulatory/gdpr-arc-azure-dynamics)。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-120">If you are new to Azure AD and Dynamics 365 Remote Assist, reference the [Azure and Dynamics 365 accountability readiness checklist for the GDPR](/compliance/regulatory/gdpr-arc-azure-dynamics).</span></span>

<span data-ttu-id="0c3fc-121">此外，Windows Defender 防火墙提供重要功能来保护设备连接。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-121">Furthermore, Windows Defender Firewall delivers critical functionality to secure device connectivity.</span></span> <span data-ttu-id="0c3fc-122">使用 HoloLens 2，始终启用防火墙，并且无法以编程方式或通过 UI 禁用防火墙。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-122">With HoloLens 2, the firewall is always enabled and there are no ways to disable it programmatically or through the UI.</span></span> <span data-ttu-id="0c3fc-123">如果使用[Intune](/mem/intune/protect/device-compliance-get-started)将 HoloLens 2 部署为托管设备，则可通过将[终结点与 Microsoft Intune](/mem/intune/protect/advanced-threat-protection)为移动威胁防御解决方案集成，来提供更多相容性功能。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-123">When the HoloLens 2 is deployed as a managed device using [Intune](/mem/intune/protect/device-compliance-get-started), more compliance functionality is available with integration for [Endpoint with Microsoft Intune](/mem/intune/protect/advanced-threat-protection) as a Mobile Threat Defense solution.</span></span>

<span data-ttu-id="0c3fc-124">了解有关 HoloLens 2[安全性和体系结构](/hololens/security-architecture)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-124">Learn more about the HoloLens 2 [security and architecture](/hololens/security-architecture).</span></span>

## <a name="os-security"></a><span data-ttu-id="0c3fc-125">操作系统安全性</span><span class="sxs-lookup"><span data-stu-id="0c3fc-125">OS Security</span></span>
<span data-ttu-id="0c3fc-126">默认情况下会自动执行更新)  (，因此 HoloLens 2 始终使用最新版本的 Windows 全息版和任何已安装的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-126">Updates are done automatically (by default) so your HoloLens 2 is always up to date with the latest release of Windows Holographic and any installed apps.</span></span> <span data-ttu-id="0c3fc-127">请参阅以下内容，了解有关如何安全设计我们的 OS 的详细信息：</span><span class="sxs-lookup"><span data-stu-id="0c3fc-127">See the following to understand more about how our OS is securely designed:</span></span>

1. [<span data-ttu-id="0c3fc-128">状态分离和隔离</span><span class="sxs-lookup"><span data-stu-id="0c3fc-128">State separation and isolation</span></span>](/hololens/security-state-separation-isolation)
1. [<span data-ttu-id="0c3fc-129">无管理员操作系统</span><span class="sxs-lookup"><span data-stu-id="0c3fc-129">Admin-less operating system</span></span>](/hololens/security-adminless-os)
1. [<span data-ttu-id="0c3fc-130">限制密码的使用</span><span class="sxs-lookup"><span data-stu-id="0c3fc-130">Limiting password use</span></span>](/hololens/security-limiting-password-use)

## <a name="physical-security"></a><span data-ttu-id="0c3fc-131">物理安全性</span><span class="sxs-lookup"><span data-stu-id="0c3fc-131">Physical Security</span></span>
<span data-ttu-id="0c3fc-132">HoloLens 2 具有受[BitLocker 加密](/hololens/security-encryption-data-protection)保护的闪存。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-132">HoloLens 2 has flash memory that is protected by [BitLocker encryption](/hololens/security-encryption-data-protection).</span></span> <span data-ttu-id="0c3fc-133">如果已将设备及其本地数据部署为托管设备，则可以使用 [高级恢复助理](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) 进行脱机刷新，也可以通过 MDM 远程擦除。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-133">Your device, and its local data, can be flashed offline using [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8#activetab=pivot:overviewtab) or remotely wiped via MDM if it has been deployed as a managed device.</span></span>

## <a name="data-protection"></a><span data-ttu-id="0c3fc-134">数据保护</span><span class="sxs-lookup"><span data-stu-id="0c3fc-134">Data Protection</span></span>
<span data-ttu-id="0c3fc-135">默认情况下，Windows 更新会自动运行 () 和[Azure 集成](/hololens/security-encryption-data-protection#Azure-integration)可保护其自身与云之间的数据传输。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-135">Windows updates are run automatically (by default) and [Azure integration](/hololens/security-encryption-data-protection#Azure-integration) protects data traveling between itself and the cloud.</span></span>

<span data-ttu-id="0c3fc-136">向外部客户端部署 HoloLens 2 时， [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide)确保你的敏感公司数据和资源既是单独的，又是安全的。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-136">When deploying HoloLens 2 to external clients, [Dynamics 365 Remote Assist](/hololens/hololens2-deployment-guide) ensures your sensitive company data and resources are both separate and safe.</span></span>

<span data-ttu-id="0c3fc-137">与 Microsoft 共享诊断数据可以通过 MDM 或用户在 OOBE 期间手动配置。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-137">The sharing of diagnostic data with Microsoft can be manually configured by MDM or by the user during OOBE.</span></span> <span data-ttu-id="0c3fc-138">有两种选择：可选诊断数据和所需的诊断数据。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-138">There are two choices: Optional diagnostic data and Required diagnostic data.</span></span> <span data-ttu-id="0c3fc-139">如果最初的诊断设置需要在以后进行故障排除时进行更改，则用户可以在 **设置 > 的隐私 > 诊断 & 反馈** 或 it 管理员 (MDM) （如果是托管设备）中更改它。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-139">If your original diagnostic setting needs to be changed at a later time for troubleshooting purposes, it can be changed by the user in **Settings -> Privacy -> Diagnostics & Feedback** or the IT Admin (MDM) if is a managed device.</span></span> <span data-ttu-id="0c3fc-140">有关详细信息[，请参阅 Windows 10 中的诊断、反馈和隐私](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319)。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-140">See more about [Diagnostics, feedback, and privacy in Windows 10](https://support.microsoft.com/windows/diagnostics-feedback-and-privacy-in-windows-10-28808a2b-a31b-dd73-dcd3-4559a5199319).</span></span>

> [!Important]
> <span data-ttu-id="0c3fc-141">设备诊断日志包含 (PII) 的个人身份信息，例如用户在典型操作过程中启动的进程或应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-141">Device diagnostic logs contain personally identifiable information (PII), such as about what processes or applications the user starts during typical operations.</span></span> <span data-ttu-id="0c3fc-142">当多个用户共享 HoloLens 设备时 (例如，用户使用不同的 Microsoft Azure Active Directory (Azure AD) 帐户登录到同一设备) 诊断日志可能包含适用于多个用户的 PII 信息。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-142">When multiple users share a HoloLens device (for example, users sign in to the same device by using different Microsoft Azure Active Directory (Azure AD) accounts) the diagnostic logs may contain PII information that applies to multiple users.</span></span>

<span data-ttu-id="0c3fc-143">有[几个收集方法和数据保留策略](/hololens/hololens-diagnostic-logs)可用于从 HoloLens 2 收集诊断数据。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-143">There are [several collection methods and data retention policies](/hololens/hololens-diagnostic-logs) for gathering diagnostic data from the HoloLens 2.</span></span>  <span data-ttu-id="0c3fc-144">有关 microsoft 如何收集和使用诊断数据的详细信息，请参阅左侧导航菜单中的 [microsoft 隐私声明-诊断](https://privacy.microsoft.com/privacystatement)-展开 **Windows** ，并选择 "**诊断**"。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-144">For more information about how Microsoft collects and uses diagnostic data, see [Microsoft Privacy Statement - Diagnostics](https://privacy.microsoft.com/privacystatement) - expand **Windows** in the left navigation menu and select **Diagnostics**.</span></span> <span data-ttu-id="0c3fc-145">请参阅 " **诊断** " 部分。</span><span class="sxs-lookup"><span data-stu-id="0c3fc-145">Go to the **Diagnostics** section.</span></span>
