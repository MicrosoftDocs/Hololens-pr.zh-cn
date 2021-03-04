---
title: 收集和使用来自 HoloLens 设备的诊断信息
description: 了解如何收集、使用和保留 HoloLens 设备的诊断信息。
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/15/2020
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
ms.custom:
- CI 115131
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: medium
keywords: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: c8d9aa9fecff74a04e3f7cb395bffe5d239e18cf
ms.sourcegitcommit: 7791e470fc2e03bdf51b19a816d7215018772860
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387520"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a><span data-ttu-id="9eff2-103">收集和使用来自 HoloLens 设备的诊断信息</span><span class="sxs-lookup"><span data-stu-id="9eff2-103">Collect and use diagnostic information from HoloLens devices</span></span>

<span data-ttu-id="9eff2-104">HoloLens 用户和管理员可以从四种不同的方法中选择从 HoloLens 收集诊断信息：</span><span class="sxs-lookup"><span data-stu-id="9eff2-104">HoloLens users and administrators can choose from among four different methods to collect diagnostic information from HoloLens:</span></span>

- <span data-ttu-id="9eff2-105">反馈中心应用</span><span class="sxs-lookup"><span data-stu-id="9eff2-105">Feedback Hub app</span></span>
- <span data-ttu-id="9eff2-106">DiagnosticLog 云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="9eff2-106">DiagnosticLog CSP</span></span>
- <span data-ttu-id="9eff2-107">“设置”应用</span><span class="sxs-lookup"><span data-stu-id="9eff2-107">Settings app</span></span>
- <span data-ttu-id="9eff2-108">脱机诊断</span><span class="sxs-lookup"><span data-stu-id="9eff2-108">Offline Diagnostics</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="9eff2-109">设备诊断日志包含 PII (个人身份) ，例如有关用户在典型操作期间启动的进程或应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="9eff2-109">Device diagnostic logs contain personally identifiable information (PII), such as about what processes or applications the user starts during typical operations.</span></span> <span data-ttu-id="9eff2-110">例如，当多个用户共享 HoloLens 设备 (时，用户使用不同的 Microsoft Azure Active Directory (Azure AD) 帐户登录同一设备) 诊断日志可能包含适用于多个用户的 PII 信息。</span><span class="sxs-lookup"><span data-stu-id="9eff2-110">When multiple users share a HoloLens device (for example, users sign in to the same device by using different Microsoft Azure Active Directory (Azure AD) accounts) the diagnostic logs may contain PII information that applies to multiple users.</span></span> <span data-ttu-id="9eff2-111">有关详细信息，请参阅 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)。</span><span class="sxs-lookup"><span data-stu-id="9eff2-111">For more information, see [Microsoft Privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

<span data-ttu-id="9eff2-112">下表比较了不同的集合方法。</span><span class="sxs-lookup"><span data-stu-id="9eff2-112">The following table compares different collection methods.</span></span> <span data-ttu-id="9eff2-113">方法名称链接到表后各节中的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="9eff2-113">The method names link to more detailed information in the sections that follow the table.</span></span>

|<span data-ttu-id="9eff2-114">方法</span><span class="sxs-lookup"><span data-stu-id="9eff2-114">Method</span></span> |<span data-ttu-id="9eff2-115">必备条件</span><span class="sxs-lookup"><span data-stu-id="9eff2-115">Prerequisites</span></span> |<span data-ttu-id="9eff2-116">数据位置</span><span class="sxs-lookup"><span data-stu-id="9eff2-116">Data locations</span></span> |<span data-ttu-id="9eff2-117">数据访问和使用</span><span class="sxs-lookup"><span data-stu-id="9eff2-117">Data access and use</span></span> |<span data-ttu-id="9eff2-118">数据保留</span><span class="sxs-lookup"><span data-stu-id="9eff2-118">Data retention</span></span> |
| --- | --- | --- | --- | --- |
|[<span data-ttu-id="9eff2-119">反馈中心</span><span class="sxs-lookup"><span data-stu-id="9eff2-119">Feedback Hub</span></span>](#feedback-hub) |<span data-ttu-id="9eff2-120">网络和 Internet 连接</span><span class="sxs-lookup"><span data-stu-id="9eff2-120">Network and internet connection</span></span><br /><br /><span data-ttu-id="9eff2-121">反馈中心应用</span><span class="sxs-lookup"><span data-stu-id="9eff2-121">Feedback Hub app</span></span><br /><br /><span data-ttu-id="9eff2-122">将文件上载到 Microsoft 云的权限</span><span class="sxs-lookup"><span data-stu-id="9eff2-122">Permission to upload files to the Microsoft cloud</span></span> |<span data-ttu-id="9eff2-123">Microsoft 云</span><span class="sxs-lookup"><span data-stu-id="9eff2-123">Microsoft cloud</span></span><br /><br /><span data-ttu-id="9eff2-124">HoloLens 设备 (可选) </span><span class="sxs-lookup"><span data-stu-id="9eff2-124">HoloLens device (optional)</span></span> |<span data-ttu-id="9eff2-125">用户请求帮助、同意使用条款并上载数据</span><span class="sxs-lookup"><span data-stu-id="9eff2-125">User requests assistance, agrees to the terms of use, and uploads the data</span></span><br /><br /><span data-ttu-id="9eff2-126">Microsoft 员工根据使用条款查看数据</span><span class="sxs-lookup"><span data-stu-id="9eff2-126">Microsoft employees view the data, as consistent with the terms of use</span></span> |<span data-ttu-id="9eff2-127">云中数据将保留由 NGP (下一代隐私) 。</span><span class="sxs-lookup"><span data-stu-id="9eff2-127">Data in the cloud is retained for the period that is defined by Next Generation Privacy (NGP).</span></span> <span data-ttu-id="9eff2-128">然后自动删除数据。</span><span class="sxs-lookup"><span data-stu-id="9eff2-128">Then the data is deleted automatically.</span></span><br /><br /><span data-ttu-id="9eff2-129">拥有设备所有者或管理员权限的用户随时都可以删除**设备上的数据。** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="9eff2-129">Data on the device can be deleted at any time by a user who has **Device owner** or **Admin** permissions.</span></span> |
|[<span data-ttu-id="9eff2-130">设置疑难解答</span><span class="sxs-lookup"><span data-stu-id="9eff2-130">Settings Troubleshooter</span></span>](#settings-troubleshooter) |<span data-ttu-id="9eff2-131">“设置”应用</span><span class="sxs-lookup"><span data-stu-id="9eff2-131">Settings app</span></span> |<span data-ttu-id="9eff2-132">HoloLens 设备</span><span class="sxs-lookup"><span data-stu-id="9eff2-132">HoloLens device</span></span><br /><br /><span data-ttu-id="9eff2-133">连接的计算机 (可选) </span><span class="sxs-lookup"><span data-stu-id="9eff2-133">Connected computer (optional)</span></span> |<span data-ttu-id="9eff2-134">用户存储数据，并且只有用户访问数据 (除非用户专门与其他用户共享数据) 。</span><span class="sxs-lookup"><span data-stu-id="9eff2-134">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="9eff2-135">数据将保留在设备上，直到用户将其删除。</span><span class="sxs-lookup"><span data-stu-id="9eff2-135">The data is retained on device until the user deletes it.\*</span></span> |
|[<span data-ttu-id="9eff2-136">DiagnosticLog 云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="9eff2-136">DiagnosticLog CSP</span></span>](#diagnosticlog-csp) |<span data-ttu-id="9eff2-137">网络连接</span><span class="sxs-lookup"><span data-stu-id="9eff2-137">Network connection</span></span><br /><br /><span data-ttu-id="9eff2-138">支持 DiagnosticLog CSP 的 MDM 环境</span><span class="sxs-lookup"><span data-stu-id="9eff2-138">MDM environment that supports the DiagnosticLog CSP</span></span> |<span data-ttu-id="9eff2-139">管理员配置存储位置</span><span class="sxs-lookup"><span data-stu-id="9eff2-139">Administrator configures storage locations</span></span> |<span data-ttu-id="9eff2-140">在托管环境中，用户隐式同意管理员访问数据。</span><span class="sxs-lookup"><span data-stu-id="9eff2-140">In the managed environment, the user implicitly consents to administrator access to the data.</span></span><br /><br /><span data-ttu-id="9eff2-141">管理员配置访问角色和权限。</span><span class="sxs-lookup"><span data-stu-id="9eff2-141">Administrator configures access roles and permissions.</span></span> | <span data-ttu-id="9eff2-142">数据保留在云存储中，管理员配置保留策略。</span><span class="sxs-lookup"><span data-stu-id="9eff2-142">Data is retained in the cloud storage and Administrator configures retention policy.</span></span> |
|[<span data-ttu-id="9eff2-143">脱机诊断</span><span class="sxs-lookup"><span data-stu-id="9eff2-143">Offline diagnostics</span></span>](#offline-diagnostics) |<span data-ttu-id="9eff2-144">设备配置：</span><span class="sxs-lookup"><span data-stu-id="9eff2-144">Device configuration:</span></span><ul><li><span data-ttu-id="9eff2-145">已打开并连接到计算机</span><span class="sxs-lookup"><span data-stu-id="9eff2-145">Powered on and connected to computer</span></span></li><li><span data-ttu-id="9eff2-146">电源和音量按钮运行</span><span class="sxs-lookup"><span data-stu-id="9eff2-146">Power and Volume buttons functioning</span></span></li></ul> |<span data-ttu-id="9eff2-147">HoloLens 设备</span><span class="sxs-lookup"><span data-stu-id="9eff2-147">HoloLens device</span></span><br /><br /><span data-ttu-id="9eff2-148">连接的计算机</span><span class="sxs-lookup"><span data-stu-id="9eff2-148">Connected computer</span></span> |<span data-ttu-id="9eff2-149">用户存储数据，并且只有用户访问数据 (除非用户专门与其他用户共享数据) 。</span><span class="sxs-lookup"><span data-stu-id="9eff2-149">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="9eff2-150">数据将保留在设备上，直到用户将其删除。</span><span class="sxs-lookup"><span data-stu-id="9eff2-150">The data is retained on device until the user deletes it.</span></span> |

- <span data-ttu-id="9eff2-151">最终用户负责与他人负责共享日志。</span><span class="sxs-lookup"><span data-stu-id="9eff2-151">End-user is responsible for sharing the logs responsibly with someone else.</span></span> <span data-ttu-id="9eff2-152">这些文件主要在联系客户服务和支持人员时很有用。</span><span class="sxs-lookup"><span data-stu-id="9eff2-152">These files are primarily useful when contacting customer service and support.</span></span>  

## <a name="feedback-hub"></a><span data-ttu-id="9eff2-153">反馈中心</span><span class="sxs-lookup"><span data-stu-id="9eff2-153">Feedback Hub</span></span>

<span data-ttu-id="9eff2-154">HoloLens 用户可以使用 Microsoft 反馈中心桌面应用向 Microsoft 支持人员发送诊断信息。</span><span class="sxs-lookup"><span data-stu-id="9eff2-154">A HoloLens user can use the Microsoft Feedback Hub desktop app to send diagnostic information to Microsoft Support.</span></span> <span data-ttu-id="9eff2-155">有关详细信息和完整说明，请参阅"[提供反馈"。](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="9eff2-155">For details and complete instructions, see [Give us feedback](hololens-feedback.md).</span></span>  

> [!NOTE]  
> <span data-ttu-id="9eff2-156">**商业或企业用户：** 如果使用"反馈中心"应用报告与 MDM、预配或其他任何设备管理方面相关的问题，请更改应用类别为 **"企业管理**  >  **设备"类别**。</span><span class="sxs-lookup"><span data-stu-id="9eff2-156">**Commercial or enterprise users:** If you use the Feedback Hub app to report a problem that relates to MDM, provisioning, or any other device management aspect, change the app category to **Enterprise Management** > **Device category**.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="9eff2-157">必备条件</span><span class="sxs-lookup"><span data-stu-id="9eff2-157">Prerequisites</span></span>

- <span data-ttu-id="9eff2-158">设备已连接到网络。</span><span class="sxs-lookup"><span data-stu-id="9eff2-158">The device is connected to a network.</span></span>
- <span data-ttu-id="9eff2-159">反馈中心应用在用户的台式计算机上可用，用户可以将文件上载到 Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="9eff2-159">The Feedback Hub app is available on the user's desktop computer, and the user can upload files to the Microsoft cloud.</span></span>

### <a name="data-locations-access-and-retention"></a><span data-ttu-id="9eff2-160">数据位置、访问和保留</span><span class="sxs-lookup"><span data-stu-id="9eff2-160">Data locations, access, and retention</span></span>

<span data-ttu-id="9eff2-161">通过同意反馈中心的使用条款，用户明确同意根据该协议 (存储和使用) 。</span><span class="sxs-lookup"><span data-stu-id="9eff2-161">By agreeing to the terms-of-use of the Feedback Hub, the user explicitly consents to the storage and usage of the data (as defined by that agreement).</span></span>

<span data-ttu-id="9eff2-162">反馈中心为用户提供了两个存储诊断信息的位置：</span><span class="sxs-lookup"><span data-stu-id="9eff2-162">The Feedback Hub provides two places for the user to store diagnostic information:</span></span>

- <span data-ttu-id="9eff2-163">**Microsoft 云**。</span><span class="sxs-lookup"><span data-stu-id="9eff2-163">**The Microsoft cloud**.</span></span> <span data-ttu-id="9eff2-164">用户使用"反馈中心"应用上载的数据存储天数与"下一代隐私" (NGP) 一致。</span><span class="sxs-lookup"><span data-stu-id="9eff2-164">Data that the user uploads by using the Feedback Hub app is stored for the number of days that is consistent with Next Generation Privacy (NGP) requirements.</span></span> <span data-ttu-id="9eff2-165">在此期间，Microsoft 员工可以使用符合 NGP 的查看器访问信息。</span><span class="sxs-lookup"><span data-stu-id="9eff2-165">Microsoft employees can use an NGP-compliant viewer to access the information during this period.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="9eff2-166">这些要求适用于所有反馈中心类别的数据。</span><span class="sxs-lookup"><span data-stu-id="9eff2-166">These requirements apply to data in all Feedback Hub categories.</span></span>

- <span data-ttu-id="9eff2-167">**HoloLens 设备**。</span><span class="sxs-lookup"><span data-stu-id="9eff2-167">**The HoloLens device**.</span></span> <span data-ttu-id="9eff2-168">在反馈中心中提交报告时，用户可以选择"保存提供反馈时创建的诊断和**附件的本地副本"。**</span><span class="sxs-lookup"><span data-stu-id="9eff2-168">While filing a report in Feedback Hub, the user can select **Save a local copy of diagnostics and attachments created when giving feedback**.</span></span> <span data-ttu-id="9eff2-169">如果用户选择此选项，反馈中心将存储 HoloLens 设备上诊断信息的副本。</span><span class="sxs-lookup"><span data-stu-id="9eff2-169">If the user selects this option, the Feedback Hub stores a copy of the diagnostic information on the HoloLens device.</span></span> <span data-ttu-id="9eff2-170">用户或使用此帐户 (HoloLens 帐户的用户或任何人仍可以访问) 。</span><span class="sxs-lookup"><span data-stu-id="9eff2-170">This information remains accessible to the user (or anyone that uses that account to sign in to HoloLens).</span></span> <span data-ttu-id="9eff2-171">若要删除此信息， **用户必须在设备上** 拥有设备所有者 **或** 管理员权限。</span><span class="sxs-lookup"><span data-stu-id="9eff2-171">To delete this information, a user must have **Device owner** or **Admin** permissions on the device.</span></span> <span data-ttu-id="9eff2-172">具有相应权限的用户可以登录到反馈中心，选择"设置视图诊断日志\*\*\*\*  >  \*\*\*\*"，然后删除信息。</span><span class="sxs-lookup"><span data-stu-id="9eff2-172">A user who has the appropriate permissions can sign in to the Feedback Hub, select **Settings** > **View diagnostics logs**, and delete the information.</span></span>

## <a name="settings-troubleshooter"></a><span data-ttu-id="9eff2-173">设置疑难解答</span><span class="sxs-lookup"><span data-stu-id="9eff2-173">Settings Troubleshooter</span></span>

<span data-ttu-id="9eff2-174">HoloLens 用户可以使用设备的"设置"应用解决问题并收集诊断信息。</span><span class="sxs-lookup"><span data-stu-id="9eff2-174">A HoloLens user can use the Settings app on the device to troubleshoot problems and collect diagnostic information.</span></span> <span data-ttu-id="9eff2-175">为此，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="9eff2-175">To do this, follow these steps:</span></span>

1. <span data-ttu-id="9eff2-176">打开"设置"应用，\*\*\*\* 然后选择"&  >  **安全疑难解答"** 页。</span><span class="sxs-lookup"><span data-stu-id="9eff2-176">Open the Settings app and select **Update & Security** > **Troubleshoot** page.</span></span>
1. <span data-ttu-id="9eff2-177">选择相应的区域，然后选择"开始 **"。**</span><span class="sxs-lookup"><span data-stu-id="9eff2-177">Select the appropriate area, and select **Start**.</span></span>
1. <span data-ttu-id="9eff2-178">重现问题。</span><span class="sxs-lookup"><span data-stu-id="9eff2-178">Reproduce the issue.</span></span>
1. <span data-ttu-id="9eff2-179">重现问题后，返回到"设置"，然后选择"**停止"。**</span><span class="sxs-lookup"><span data-stu-id="9eff2-179">After you reproduce the issue, return to Settings and then select **Stop**.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="9eff2-180">必备条件</span><span class="sxs-lookup"><span data-stu-id="9eff2-180">Prerequisites</span></span>

- <span data-ttu-id="9eff2-181">"设置"应用安装在设备上，并且可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="9eff2-181">The Settings app is installed on the device and is available to the user.</span></span>

### <a name="data-locations-access-and-retention"></a><span data-ttu-id="9eff2-182">数据位置、访问和保留</span><span class="sxs-lookup"><span data-stu-id="9eff2-182">Data locations, access, and retention</span></span>

<span data-ttu-id="9eff2-183">由于用户启动数据收集，因此用户隐式同意存储诊断信息。</span><span class="sxs-lookup"><span data-stu-id="9eff2-183">Because the user starts the data collection, the user implicitly consents to the storage of the diagnostic information.</span></span> <span data-ttu-id="9eff2-184">只有用户或与之共享数据的任何人才能访问数据。</span><span class="sxs-lookup"><span data-stu-id="9eff2-184">Only the user, or anyone with whom that the user shares the data, can access the data.</span></span>

<span data-ttu-id="9eff2-185">诊断信息存储在设备上。</span><span class="sxs-lookup"><span data-stu-id="9eff2-185">The diagnostic information is stored on the device.</span></span> <span data-ttu-id="9eff2-186">如果设备已连接到用户计算机，则信息也驻留在以下文件中的计算机上：</span><span class="sxs-lookup"><span data-stu-id="9eff2-186">If the device is connected to the user's computer, the information also resides on the computer in the following file:</span></span>

> <span data-ttu-id="9eff2-187">此 PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*> .etl</span><span class="sxs-lookup"><span data-stu-id="9eff2-187">This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents\\Trace\<*ddmmyyhhmmss*>.etl</span></span>

> [!NOTE]  
> <span data-ttu-id="9eff2-188">在此文件路径和名称中，表示 HoloLens 设备的名称，表示文件的 \<*HoloLens device name*> \<*ddmmyyhhmmss*> 创建日期和时间。</span><span class="sxs-lookup"><span data-stu-id="9eff2-188">In this file path and name, \<*HoloLens device name*> represents the name of the HoloLens device, and \<*ddmmyyhhmmss*> represents the date and time that the file was created.</span></span>

<span data-ttu-id="9eff2-189">诊断信息将一直保留在这些位置，直到用户将其删除。</span><span class="sxs-lookup"><span data-stu-id="9eff2-189">The diagnostic information remains in these locations until the user deletes it.</span></span>

## <a name="diagnosticlog-csp"></a><span data-ttu-id="9eff2-190">DiagnosticLog 云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="9eff2-190">DiagnosticLog CSP</span></span>

<span data-ttu-id="9eff2-191">在移动设备管理 (MDM) 环境中，IT 管理员可以使用 [DiagnosticLog ](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) 配置服务提供程序 (CSP) 在已注册的 HoloLens 设备上配置诊断设置。</span><span class="sxs-lookup"><span data-stu-id="9eff2-191">In a Mobile Device Management (MDM) environment, the IT administrator can use the the [DiagnosticLog configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) to configure diagnostic settings on enrolled HoloLens devices.</span></span> <span data-ttu-id="9eff2-192">IT 管理员可以将这些设置配置为从已注册的设备收集日志。</span><span class="sxs-lookup"><span data-stu-id="9eff2-192">The IT administrator can configure these settings to collect logs from enrolled devices.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="9eff2-193">必备条件</span><span class="sxs-lookup"><span data-stu-id="9eff2-193">Prerequisites</span></span>

- <span data-ttu-id="9eff2-194">设备已连接到网络。</span><span class="sxs-lookup"><span data-stu-id="9eff2-194">The device is connected to a network.</span></span>
- <span data-ttu-id="9eff2-195">设备在支持 DiagnosticLog CSP 的 MDM 环境中注册。</span><span class="sxs-lookup"><span data-stu-id="9eff2-195">The device is enrolled in an MDM environment that supports the DiagnosticLog CSP.</span></span>

### <a name="data-locations-access-and-retention"></a><span data-ttu-id="9eff2-196">数据位置、访问和保留</span><span class="sxs-lookup"><span data-stu-id="9eff2-196">Data locations, access, and retention</span></span>

<span data-ttu-id="9eff2-197">由于设备是托管环境的一部分，因此用户隐式同意对诊断信息进行管理访问。</span><span class="sxs-lookup"><span data-stu-id="9eff2-197">Because the device is part of the managed environment, the user implicitly consents to administrative access to diagnostic information.</span></span>

<span data-ttu-id="9eff2-198">IT 管理员使用 DiagnosticLog CSP 配置数据存储、保留和访问策略，包括控制以下策略的策略：</span><span class="sxs-lookup"><span data-stu-id="9eff2-198">The IT administrator uses the DiagnosticLog CSP to configure the data storage, retention, and access policies, including the policies that govern the following:</span></span>

- <span data-ttu-id="9eff2-199">存储诊断信息的云基础结构。</span><span class="sxs-lookup"><span data-stu-id="9eff2-199">The cloud infrastructure that stores the diagnostic information.</span></span>
- <span data-ttu-id="9eff2-200">诊断信息的保留期。</span><span class="sxs-lookup"><span data-stu-id="9eff2-200">The retention period for the diagnostic information.</span></span>
- <span data-ttu-id="9eff2-201">控制对诊断信息的访问权限的权限。</span><span class="sxs-lookup"><span data-stu-id="9eff2-201">Permissions that control access to the diagnostic information.</span></span>

## <a name="offline-diagnostics"></a><span data-ttu-id="9eff2-202">脱机诊断</span><span class="sxs-lookup"><span data-stu-id="9eff2-202">Offline diagnostics</span></span>
<span data-ttu-id="9eff2-203">如果设备无法通过反馈中心或设置疑难解答收集诊断，你可以手动收集诊断。</span><span class="sxs-lookup"><span data-stu-id="9eff2-203">In situations where the device is not able to collect diagnostics via Feedback Hub or the Setting Troubleshooter, you can collect diagnostics manually.</span></span> <span data-ttu-id="9eff2-204">需要这样做的一种情况是设备无法连接到Wi-Fi或者无法访问上面提到的其他方法。</span><span class="sxs-lookup"><span data-stu-id="9eff2-204">One scenario where this is necessary is when the device cannot connect to Wi-Fi or you can't access other methods mentioned above.</span></span> <span data-ttu-id="9eff2-205">诊断从设备收集故障转储和日志，以帮助 Microsoft 支持工程师隔离问题。</span><span class="sxs-lookup"><span data-stu-id="9eff2-205">The diagnostics collect crash dumps and logs from the device that help a Microsoft support engineer isolate issues.</span></span>

<span data-ttu-id="9eff2-206">当设备通过 USB 电缆连接到电脑后在文件资源管理器中显示时，此功能有效。</span><span class="sxs-lookup"><span data-stu-id="9eff2-206">This works when the device shows up in File Explorer after connecting it to a PC via a USB cable.</span></span>

> [!NOTE]
> <span data-ttu-id="9eff2-207">脱机诊断生成和管理的控制方式因操作系统版本不同而不同。</span><span class="sxs-lookup"><span data-stu-id="9eff2-207">Offline Diagnostics generation and management is controlled differently depending on your OS version.</span></span> <span data-ttu-id="9eff2-208">以前它由遥测设置控制，但现在通过 MDM 策略直接控制。</span><span class="sxs-lookup"><span data-stu-id="9eff2-208">Previously it was controlled by the telemetry setting, but is now directly controlled via MDM policy.</span></span> <span data-ttu-id="9eff2-209">如果通过设置或 MDM 策略禁用，则不能使用此机制收集诊断日志。</span><span class="sxs-lookup"><span data-stu-id="9eff2-209">If disabled via either setting or MDM policy, then diagnostic logs cannot be collected using this mechanism.</span></span>

<span data-ttu-id="9eff2-210">Windows 全息版[之前的行为，verison 20H2：](hololens-release-notes.md#windows-holographic-version-20h2)</span><span class="sxs-lookup"><span data-stu-id="9eff2-210">Behavior Prior to [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2):</span></span>
 - <span data-ttu-id="9eff2-211">只有在用户通过 OOBE 或 [系统\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) 策略值设置为 Full (Basic 是 HoloLens) 的默认值时，才启用脱机诊断。</span><span class="sxs-lookup"><span data-stu-id="9eff2-211">Offline diagnostics is only enabled when user is either going through OOBE or [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) policy value is set to Full (Basic is default value on HoloLens).</span></span> 
- <span data-ttu-id="9eff2-212">若要禁用脱机诊断，请转到"设置应用>**隐私**"页，然后选择**诊断数据\*\*\*\*中的"基本"。**</span><span class="sxs-lookup"><span data-stu-id="9eff2-212">To disable Offline diagnostics, go to **Settings App > Privacy** page and select **Basic** in **Diagnostic Data**.</span></span> <span data-ttu-id="9eff2-213">在脱机诊断依赖于遥测设置内部版本上，它仅影响是否收集任何日志。</span><span class="sxs-lookup"><span data-stu-id="9eff2-213">On builds where offline diagnostics depends on telemetry setting, it only impacts whether any logs are collected or not.</span></span> <span data-ttu-id="9eff2-214">它不会影响收集的文件。</span><span class="sxs-lookup"><span data-stu-id="9eff2-214">It does not impact what files are collected.</span></span>
- <span data-ttu-id="9eff2-215">如果设备已锁定，将不会显示日志。</span><span class="sxs-lookup"><span data-stu-id="9eff2-215">If device is locked then logs won't appear.</span></span>

<span data-ttu-id="9eff2-216">在 [版本 Windows Holographic、verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 及以后版本上：</span><span class="sxs-lookup"><span data-stu-id="9eff2-216">On builds [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) and onwards:</span></span>
- <span data-ttu-id="9eff2-217">启用回退诊断时，由具有相应[设置 MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)的特定 MDM 策略控制</span><span class="sxs-lookup"><span data-stu-id="9eff2-217">When Fallback Diagnostics is enabled will be controlled by specific MDM policy with corresponding setting [MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)</span></span>
- <span data-ttu-id="9eff2-218">如果设备已锁定，将不会显示日志。</span><span class="sxs-lookup"><span data-stu-id="9eff2-218">If device is locked then logs won't appear.</span></span>

<span data-ttu-id="9eff2-219">观看此视频了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="9eff2-219">Watch this video to learn more.</span></span>

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

<span data-ttu-id="9eff2-220">按照以下步骤收集诊断：</span><span class="sxs-lookup"><span data-stu-id="9eff2-220">Follow these steps to collect diagnostics:</span></span>
1.  <span data-ttu-id="9eff2-221">使用 USB 电缆将设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="9eff2-221">Connect the device with a USB cable to your PC.</span></span>
2.  <span data-ttu-id="9eff2-222">在电脑上的文件资源管理器中，导航到 **"此电脑 \<hololens-device> \内部存储"。**</span><span class="sxs-lookup"><span data-stu-id="9eff2-222">In File Explorer on your PC, navigate to **'This PC\<hololens-device>\Internal Storage'**.</span></span>
3.  <span data-ttu-id="9eff2-223">如果 **"内部存储** "文件夹未显示，设备将等待用户登录。</span><span class="sxs-lookup"><span data-stu-id="9eff2-223">If the **Internal Storage** folder does not show up, the device is waiting for a user to sign in.</span></span> <span data-ttu-id="9eff2-224">通过按住电源按钮 10 秒来登录或电源循环设备。</span><span class="sxs-lookup"><span data-stu-id="9eff2-224">Either sign-in or power cycle the device by holding the POWER button down for 10 seconds.</span></span>
4.  <span data-ttu-id="9eff2-225">同时按下并立即释放 **POWER + VOLUME DOWN** 按钮。</span><span class="sxs-lookup"><span data-stu-id="9eff2-225">Press and immediately release the **POWER + VOLUME DOWN** buttons together.</span></span>
5.  <span data-ttu-id="9eff2-226">等待一分钟，设备准备 zip 存档。</span><span class="sxs-lookup"><span data-stu-id="9eff2-226">Wait a minute for the device to prepare the zip archives.</span></span> <span data-ttu-id="9eff2-227"> (生成 zip 存档时，名为 HololensDiagnostics.temp 的临时文件可能会可见。</span><span class="sxs-lookup"><span data-stu-id="9eff2-227">(A temporary file named HololensDiagnostics.temp may become visible while the device generates the zip archives.</span></span> <span data-ttu-id="9eff2-228">请勿访问或保存该文件。</span><span class="sxs-lookup"><span data-stu-id="9eff2-228">Do not access or save that file.</span></span> <span data-ttu-id="9eff2-229">此过程完成后，它将替换为 zip archives.) </span><span class="sxs-lookup"><span data-stu-id="9eff2-229">When the process finishes it will be replaced by the zip archives.)</span></span>
6.  <span data-ttu-id="9eff2-230">刷新文件资源管理器，然后导航到 **"\Documents"** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9eff2-230">Refresh file explorer, and navigate to the **'\Documents'** folder.</span></span>
7.  <span data-ttu-id="9eff2-231">复制诊断 ZIP 文件，并与 Microsoft 支持团队共享这些文件。</span><span class="sxs-lookup"><span data-stu-id="9eff2-231">Copy the diagnostics ZIP files and share them with the Microsoft support team.</span></span>

> [!NOTE]
> <span data-ttu-id="9eff2-232">某些诊断 ZIP 文件可能包含个人身份信息。</span><span class="sxs-lookup"><span data-stu-id="9eff2-232">Some of the diagnostics ZIP files may contain personally identifiable information.</span></span>