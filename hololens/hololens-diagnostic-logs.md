---
title: 从 HoloLens 设备收集和使用诊断信息
description: 了解如何从 HoloLens 设备收集、使用和保留诊断信息。
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
ms.openlocfilehash: 4a360e99a45b855957e36dd6ba31ede3da9631ba
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308471"
---
# <a name="collect-and-use-diagnostic-information-from-hololens-devices"></a><span data-ttu-id="6934a-103">从 HoloLens 设备收集和使用诊断信息</span><span class="sxs-lookup"><span data-stu-id="6934a-103">Collect and use diagnostic information from HoloLens devices</span></span>

<span data-ttu-id="6934a-104">HoloLens 用户和管理员可以从四种不同的方法中进行选择，以从 HoloLens 收集诊断信息：</span><span class="sxs-lookup"><span data-stu-id="6934a-104">HoloLens users and administrators can choose from among four different methods to collect diagnostic information from HoloLens:</span></span>

- <span data-ttu-id="6934a-105">反馈中心应用</span><span class="sxs-lookup"><span data-stu-id="6934a-105">Feedback Hub app</span></span>
- <span data-ttu-id="6934a-106">DiagnosticLog 云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="6934a-106">DiagnosticLog CSP</span></span>
- <span data-ttu-id="6934a-107">“设置”应用</span><span class="sxs-lookup"><span data-stu-id="6934a-107">Settings app</span></span>
- <span data-ttu-id="6934a-108">脱机诊断</span><span class="sxs-lookup"><span data-stu-id="6934a-108">Offline Diagnostics</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="6934a-109">设备诊断日志包含 (PII) 的个人身份信息，例如用户在典型操作过程中启动的进程或应用程序。</span><span class="sxs-lookup"><span data-stu-id="6934a-109">Device diagnostic logs contain personally identifiable information (PII), such as about what processes or applications the user starts during typical operations.</span></span> <span data-ttu-id="6934a-110">例如，当多个用户共享一台 HoloLens 设备时 (例如，用户使用不同的 Microsoft Azure Active Directory (Azure AD) 帐户登录到相同的设备) 诊断日志可能包含适用于多个用户的 PII 信息。</span><span class="sxs-lookup"><span data-stu-id="6934a-110">When multiple users share a HoloLens device (for example, users sign in to the same device by using different Microsoft Azure Active Directory (Azure AD) accounts) the diagnostic logs may contain PII information that applies to multiple users.</span></span> <span data-ttu-id="6934a-111">有关详细信息，请参阅 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)。</span><span class="sxs-lookup"><span data-stu-id="6934a-111">For more information, see [Microsoft Privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

<span data-ttu-id="6934a-112">下表比较了不同的收集方法。</span><span class="sxs-lookup"><span data-stu-id="6934a-112">The following table compares different collection methods.</span></span> <span data-ttu-id="6934a-113">方法名称链接到该表后面各节中更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="6934a-113">The method names link to more detailed information in the sections that follow the table.</span></span>

|<span data-ttu-id="6934a-114">方法</span><span class="sxs-lookup"><span data-stu-id="6934a-114">Method</span></span> |<span data-ttu-id="6934a-115">先决条件</span><span class="sxs-lookup"><span data-stu-id="6934a-115">Prerequisites</span></span> |<span data-ttu-id="6934a-116">数据位置</span><span class="sxs-lookup"><span data-stu-id="6934a-116">Data locations</span></span> |<span data-ttu-id="6934a-117">数据访问和使用</span><span class="sxs-lookup"><span data-stu-id="6934a-117">Data access and use</span></span> |<span data-ttu-id="6934a-118">数据保留</span><span class="sxs-lookup"><span data-stu-id="6934a-118">Data retention</span></span> |
| --- | --- | --- | --- | --- |
|[<span data-ttu-id="6934a-119">反馈中心</span><span class="sxs-lookup"><span data-stu-id="6934a-119">Feedback Hub</span></span>](#feedback-hub) |<span data-ttu-id="6934a-120">网络和 internet 连接</span><span class="sxs-lookup"><span data-stu-id="6934a-120">Network and internet connection</span></span><br /><br /><span data-ttu-id="6934a-121">反馈中心应用</span><span class="sxs-lookup"><span data-stu-id="6934a-121">Feedback Hub app</span></span><br /><br /><span data-ttu-id="6934a-122">将文件上传到 Microsoft 云的权限</span><span class="sxs-lookup"><span data-stu-id="6934a-122">Permission to upload files to the Microsoft cloud</span></span> |<span data-ttu-id="6934a-123">Microsoft 云</span><span class="sxs-lookup"><span data-stu-id="6934a-123">Microsoft cloud</span></span><br /><br /><span data-ttu-id="6934a-124">HoloLens 设备 (可选) </span><span class="sxs-lookup"><span data-stu-id="6934a-124">HoloLens device (optional)</span></span> |<span data-ttu-id="6934a-125">用户请求协助，同意使用条款，并上传数据</span><span class="sxs-lookup"><span data-stu-id="6934a-125">User requests assistance, agrees to the terms of use, and uploads the data</span></span><br /><br /><span data-ttu-id="6934a-126">Microsoft 员工查看数据，与使用条款一致</span><span class="sxs-lookup"><span data-stu-id="6934a-126">Microsoft employees view the data, as consistent with the terms of use</span></span> |<span data-ttu-id="6934a-127">云中的数据保留在下一代隐私 (NGP) 定义的时间段内。</span><span class="sxs-lookup"><span data-stu-id="6934a-127">Data in the cloud is retained for the period that is defined by Next Generation Privacy (NGP).</span></span> <span data-ttu-id="6934a-128">然后，将自动删除数据。</span><span class="sxs-lookup"><span data-stu-id="6934a-128">Then the data is deleted automatically.</span></span><br /><br /><span data-ttu-id="6934a-129">具有 **设备所有者** 或 **管理员** 权限的用户可以随时删除设备上的数据。</span><span class="sxs-lookup"><span data-stu-id="6934a-129">Data on the device can be deleted at any time by a user who has **Device owner** or **Admin** permissions.</span></span> |
|[<span data-ttu-id="6934a-130">设置疑难解答</span><span class="sxs-lookup"><span data-stu-id="6934a-130">Settings Troubleshooter</span></span>](#settings-troubleshooter) |<span data-ttu-id="6934a-131">“设置”应用</span><span class="sxs-lookup"><span data-stu-id="6934a-131">Settings app</span></span> |<span data-ttu-id="6934a-132">HoloLens 设备</span><span class="sxs-lookup"><span data-stu-id="6934a-132">HoloLens device</span></span><br /><br /><span data-ttu-id="6934a-133">连接的计算机 (可选) </span><span class="sxs-lookup"><span data-stu-id="6934a-133">Connected computer (optional)</span></span> |<span data-ttu-id="6934a-134">用户存储数据，只有用户才能访问数据 (除非用户专门与其他用户) 共享数据。</span><span class="sxs-lookup"><span data-stu-id="6934a-134">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="6934a-135">数据将保留在设备上，直到用户将其删除。</span><span class="sxs-lookup"><span data-stu-id="6934a-135">The data is retained on device until the user deletes it.\*</span></span> |
|[<span data-ttu-id="6934a-136">DiagnosticLog 云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="6934a-136">DiagnosticLog CSP</span></span>](#diagnosticlog-csp) |<span data-ttu-id="6934a-137">网络连接</span><span class="sxs-lookup"><span data-stu-id="6934a-137">Network connection</span></span><br /><br /><span data-ttu-id="6934a-138">支持 DiagnosticLog CSP 的 MDM 环境</span><span class="sxs-lookup"><span data-stu-id="6934a-138">MDM environment that supports the DiagnosticLog CSP</span></span> |<span data-ttu-id="6934a-139">管理员配置存储位置</span><span class="sxs-lookup"><span data-stu-id="6934a-139">Administrator configures storage locations</span></span> |<span data-ttu-id="6934a-140">在托管环境中，用户隐式同意对数据的管理员访问权限。</span><span class="sxs-lookup"><span data-stu-id="6934a-140">In the managed environment, the user implicitly consents to administrator access to the data.</span></span><br /><br /><span data-ttu-id="6934a-141">管理员配置访问角色和权限。</span><span class="sxs-lookup"><span data-stu-id="6934a-141">Administrator configures access roles and permissions.</span></span> | <span data-ttu-id="6934a-142">数据将保留在云存储中，管理员可配置保留策略。</span><span class="sxs-lookup"><span data-stu-id="6934a-142">Data is retained in the cloud storage and Administrator configures retention policy.</span></span> |
|[<span data-ttu-id="6934a-143">脱机诊断</span><span class="sxs-lookup"><span data-stu-id="6934a-143">Offline diagnostics</span></span>](#offline-diagnostics) |<span data-ttu-id="6934a-144">设备配置：</span><span class="sxs-lookup"><span data-stu-id="6934a-144">Device configuration:</span></span><ul><li><span data-ttu-id="6934a-145">开机并连接到计算机</span><span class="sxs-lookup"><span data-stu-id="6934a-145">Powered on and connected to computer</span></span></li><li><span data-ttu-id="6934a-146">电源和音量按钮正常工作</span><span class="sxs-lookup"><span data-stu-id="6934a-146">Power and Volume buttons functioning</span></span></li></ul> |<span data-ttu-id="6934a-147">HoloLens 设备</span><span class="sxs-lookup"><span data-stu-id="6934a-147">HoloLens device</span></span><br /><br /><span data-ttu-id="6934a-148">连接的计算机</span><span class="sxs-lookup"><span data-stu-id="6934a-148">Connected computer</span></span> |<span data-ttu-id="6934a-149">用户存储数据，只有用户才能访问数据 (除非用户专门与其他用户) 共享数据。</span><span class="sxs-lookup"><span data-stu-id="6934a-149">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="6934a-150">数据将保留在设备上，直到用户将其删除。</span><span class="sxs-lookup"><span data-stu-id="6934a-150">The data is retained on device until the user deletes it.</span></span> |

- <span data-ttu-id="6934a-151">最终用户负责与其他人共享日志。</span><span class="sxs-lookup"><span data-stu-id="6934a-151">End-user is responsible for sharing the logs responsibly with someone else.</span></span> <span data-ttu-id="6934a-152">与客户服务和支持人员联系时，这些文件主要非常有用。</span><span class="sxs-lookup"><span data-stu-id="6934a-152">These files are primarily useful when contacting customer service and support.</span></span>  

## <a name="feedback-hub"></a><span data-ttu-id="6934a-153">反馈中心</span><span class="sxs-lookup"><span data-stu-id="6934a-153">Feedback Hub</span></span>

<span data-ttu-id="6934a-154">HoloLens 用户可以使用 Microsoft 反馈中心桌面应用将诊断信息发送到 Microsoft 支持部门。</span><span class="sxs-lookup"><span data-stu-id="6934a-154">A HoloLens user can use the Microsoft Feedback Hub desktop app to send diagnostic information to Microsoft Support.</span></span> <span data-ttu-id="6934a-155">有关详细信息和完整说明，请参阅 [向我们提供反馈](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="6934a-155">For details and complete instructions, see [Give us feedback](hololens-feedback.md).</span></span>  

> [!NOTE]  
> <span data-ttu-id="6934a-156">**商业或企业用户：** 如果使用反馈中心应用报告与 MDM、预配或任何其他设备管理方面相关的问题，请将应用类别更改为 **企业管理**  >  **设备类别**。</span><span class="sxs-lookup"><span data-stu-id="6934a-156">**Commercial or enterprise users:** If you use the Feedback Hub app to report a problem that relates to MDM, provisioning, or any other device management aspect, change the app category to **Enterprise Management** > **Device category**.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="6934a-157">先决条件</span><span class="sxs-lookup"><span data-stu-id="6934a-157">Prerequisites</span></span>

- <span data-ttu-id="6934a-158">设备已连接到网络。</span><span class="sxs-lookup"><span data-stu-id="6934a-158">The device is connected to a network.</span></span>
- <span data-ttu-id="6934a-159">反馈中心应用在用户的桌面计算机上可用，用户可以将文件上传到 Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="6934a-159">The Feedback Hub app is available on the user's desktop computer, and the user can upload files to the Microsoft cloud.</span></span>

### <a name="data-locations-access-and-retention"></a><span data-ttu-id="6934a-160">数据位置、访问和保留</span><span class="sxs-lookup"><span data-stu-id="6934a-160">Data locations, access, and retention</span></span>

<span data-ttu-id="6934a-161">通过同意反馈中心的使用条款，用户明确同意该协议) 定义的数据 (的存储和使用情况。</span><span class="sxs-lookup"><span data-stu-id="6934a-161">By agreeing to the terms-of-use of the Feedback Hub, the user explicitly consents to the storage and usage of the data (as defined by that agreement).</span></span>

<span data-ttu-id="6934a-162">反馈中心为用户提供了两个用于存储诊断信息的位置：</span><span class="sxs-lookup"><span data-stu-id="6934a-162">The Feedback Hub provides two places for the user to store diagnostic information:</span></span>

- <span data-ttu-id="6934a-163">**Microsoft 云**。</span><span class="sxs-lookup"><span data-stu-id="6934a-163">**The Microsoft cloud**.</span></span> <span data-ttu-id="6934a-164">用户使用反馈中心应用上传的数据存储在与下一代隐私 (NGP) 要求一致的天数内。</span><span class="sxs-lookup"><span data-stu-id="6934a-164">Data that the user uploads by using the Feedback Hub app is stored for the number of days that is consistent with Next Generation Privacy (NGP) requirements.</span></span> <span data-ttu-id="6934a-165">Microsoft 员工可以使用 NGP 兼容查看器来访问此期间的信息。</span><span class="sxs-lookup"><span data-stu-id="6934a-165">Microsoft employees can use an NGP-compliant viewer to access the information during this period.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="6934a-166">这些要求适用于所有反馈中心类别中的数据。</span><span class="sxs-lookup"><span data-stu-id="6934a-166">These requirements apply to data in all Feedback Hub categories.</span></span>

- <span data-ttu-id="6934a-167">**HoloLens 设备**。</span><span class="sxs-lookup"><span data-stu-id="6934a-167">**The HoloLens device**.</span></span> <span data-ttu-id="6934a-168">在反馈中心中存档报表时，用户可以选择 " **保存在提供反馈时创建的诊断和附件的本地副本**"。</span><span class="sxs-lookup"><span data-stu-id="6934a-168">While filing a report in Feedback Hub, the user can select **Save a local copy of diagnostics and attachments created when giving feedback**.</span></span> <span data-ttu-id="6934a-169">如果用户选择此选项，则反馈中心会在 HoloLens 设备上存储诊断信息的副本。</span><span class="sxs-lookup"><span data-stu-id="6934a-169">If the user selects this option, the Feedback Hub stores a copy of the diagnostic information on the HoloLens device.</span></span> <span data-ttu-id="6934a-170">此信息仍可供用户 (或使用该帐户登录到 HoloLens) 的任何人访问。</span><span class="sxs-lookup"><span data-stu-id="6934a-170">This information remains accessible to the user (or anyone that uses that account to sign in to HoloLens).</span></span> <span data-ttu-id="6934a-171">若要删除此信息，用户必须具有设备 **所有者** 或设备的 **管理员** 权限。</span><span class="sxs-lookup"><span data-stu-id="6934a-171">To delete this information, a user must have **Device owner** or **Admin** permissions on the device.</span></span> <span data-ttu-id="6934a-172">具有相应权限的用户可以登录到反馈中心、选择 "**设置**  >  " "**查看诊断日志**" 和 "删除信息"。</span><span class="sxs-lookup"><span data-stu-id="6934a-172">A user who has the appropriate permissions can sign in to the Feedback Hub, select **Settings** > **View diagnostics logs**, and delete the information.</span></span>

## <a name="settings-troubleshooter"></a><span data-ttu-id="6934a-173">设置疑难解答</span><span class="sxs-lookup"><span data-stu-id="6934a-173">Settings Troubleshooter</span></span>

<span data-ttu-id="6934a-174">HoloLens 用户可以使用设备上的 "设置" 应用来解决问题和收集诊断信息。</span><span class="sxs-lookup"><span data-stu-id="6934a-174">A HoloLens user can use the Settings app on the device to troubleshoot problems and collect diagnostic information.</span></span> <span data-ttu-id="6934a-175">要实现这一点，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6934a-175">To do this, follow these steps:</span></span>

1. <span data-ttu-id="6934a-176">打开 "设置" 应用，然后选择 "**更新 & 安全**  >  **疑难解答**" 页。</span><span class="sxs-lookup"><span data-stu-id="6934a-176">Open the Settings app and select **Update & Security** > **Troubleshoot** page.</span></span>
1. <span data-ttu-id="6934a-177">选择相应的区域，然后选择 " **启动**"。</span><span class="sxs-lookup"><span data-stu-id="6934a-177">Select the appropriate area, and select **Start**.</span></span>
1. <span data-ttu-id="6934a-178">重现问题。</span><span class="sxs-lookup"><span data-stu-id="6934a-178">Reproduce the issue.</span></span>
1. <span data-ttu-id="6934a-179">重现问题后，返回到 "设置"，然后选择 " **停止**"。</span><span class="sxs-lookup"><span data-stu-id="6934a-179">After you reproduce the issue, return to Settings and then select **Stop**.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="6934a-180">先决条件</span><span class="sxs-lookup"><span data-stu-id="6934a-180">Prerequisites</span></span>

- <span data-ttu-id="6934a-181">"设置" 应用安装在设备上，并可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="6934a-181">The Settings app is installed on the device and is available to the user.</span></span>

### <a name="data-locations-access-and-retention"></a><span data-ttu-id="6934a-182">数据位置、访问和保留</span><span class="sxs-lookup"><span data-stu-id="6934a-182">Data locations, access, and retention</span></span>

<span data-ttu-id="6934a-183">由于用户启动数据收集，因此用户隐式同意诊断信息的存储。</span><span class="sxs-lookup"><span data-stu-id="6934a-183">Because the user starts the data collection, the user implicitly consents to the storage of the diagnostic information.</span></span> <span data-ttu-id="6934a-184">只有用户或用户共享数据的任何人都可以访问数据。</span><span class="sxs-lookup"><span data-stu-id="6934a-184">Only the user, or anyone with whom that the user shares the data, can access the data.</span></span>

<span data-ttu-id="6934a-185">诊断信息存储在设备上。</span><span class="sxs-lookup"><span data-stu-id="6934a-185">The diagnostic information is stored on the device.</span></span> <span data-ttu-id="6934a-186">如果设备连接到用户的计算机，则信息也驻留在计算机上的以下文件中：</span><span class="sxs-lookup"><span data-stu-id="6934a-186">If the device is connected to the user's computer, the information also resides on the computer in the following file:</span></span>

> <span data-ttu-id="6934a-187">此电脑 \\ \<*HoloLens device name*> \\ 内部存储 \\ 文档 \\ 跟踪 \<*ddmmyyhhmmss*> .etl</span><span class="sxs-lookup"><span data-stu-id="6934a-187">This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents\\Trace\<*ddmmyyhhmmss*>.etl</span></span>

> [!NOTE]  
> <span data-ttu-id="6934a-188">在此文件路径和名称中， \<*HoloLens device name*> 表示 HoloLens 设备的名称，并 \<*ddmmyyhhmmss*> 表示创建该文件的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="6934a-188">In this file path and name, \<*HoloLens device name*> represents the name of the HoloLens device, and \<*ddmmyyhhmmss*> represents the date and time that the file was created.</span></span>

<span data-ttu-id="6934a-189">诊断信息将保留在这些位置，直到用户删除它。</span><span class="sxs-lookup"><span data-stu-id="6934a-189">The diagnostic information remains in these locations until the user deletes it.</span></span>

## <a name="diagnosticlog-csp"></a><span data-ttu-id="6934a-190">DiagnosticLog 云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="6934a-190">DiagnosticLog CSP</span></span>

<span data-ttu-id="6934a-191">在移动设备管理 (MDM) 环境中，IT 管理员可以使用 [DiagnosticLog 配置服务提供程序 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) 来配置已注册的 HoloLens 设备上的诊断设置。</span><span class="sxs-lookup"><span data-stu-id="6934a-191">In a Mobile Device Management (MDM) environment, the IT administrator can use the the [DiagnosticLog configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) to configure diagnostic settings on enrolled HoloLens devices.</span></span> <span data-ttu-id="6934a-192">IT 管理员可以将这些设置配置为从注册的设备收集日志。</span><span class="sxs-lookup"><span data-stu-id="6934a-192">The IT administrator can configure these settings to collect logs from enrolled devices.</span></span>

<span data-ttu-id="6934a-193">查看详细信息：</span><span class="sxs-lookup"><span data-stu-id="6934a-193">See more:</span></span>
- [<span data-ttu-id="6934a-194">从 Windows 设备收集诊断信息</span><span class="sxs-lookup"><span data-stu-id="6934a-194">Collect diagnostics from a Windows device</span></span>](https://docs.microsoft.com/mem/intune/remote-actions/collect-diagnostics)
- [<span data-ttu-id="6934a-195">Intune 公共预览版-Windows 10 设备诊断</span><span class="sxs-lookup"><span data-stu-id="6934a-195">Intune Public Preview - Windows 10 Device diagnostics</span></span>](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-public-preview-windows-10-device-diagnostics/ba-p/2179712#:~:text=This%20first%20release%20of%20device%20diagnostics%20utilizes%20the,taking%20about%205%20minutes%20from%20start%20to%20finish.)

### <a name="prerequisites"></a><span data-ttu-id="6934a-196">先决条件</span><span class="sxs-lookup"><span data-stu-id="6934a-196">Prerequisites</span></span>

- <span data-ttu-id="6934a-197">设备已连接到网络。</span><span class="sxs-lookup"><span data-stu-id="6934a-197">The device is connected to a network.</span></span>
- <span data-ttu-id="6934a-198">设备在支持 DiagnosticLog CSP 的 MDM 环境中注册。</span><span class="sxs-lookup"><span data-stu-id="6934a-198">The device is enrolled in an MDM environment that supports the DiagnosticLog CSP.</span></span>

### <a name="data-locations-access-and-retention"></a><span data-ttu-id="6934a-199">数据位置、访问和保留</span><span class="sxs-lookup"><span data-stu-id="6934a-199">Data locations, access, and retention</span></span>

<span data-ttu-id="6934a-200">由于设备是托管环境的一部分，因此用户隐式同意对诊断信息的管理访问权限。</span><span class="sxs-lookup"><span data-stu-id="6934a-200">Because the device is part of the managed environment, the user implicitly consents to administrative access to diagnostic information.</span></span>

<span data-ttu-id="6934a-201">IT 管理员使用 DiagnosticLog CSP 来配置数据存储、保留和访问策略，包括控制以下各项的策略：</span><span class="sxs-lookup"><span data-stu-id="6934a-201">The IT administrator uses the DiagnosticLog CSP to configure the data storage, retention, and access policies, including the policies that govern the following:</span></span>

- <span data-ttu-id="6934a-202">存储诊断信息的云基础结构。</span><span class="sxs-lookup"><span data-stu-id="6934a-202">The cloud infrastructure that stores the diagnostic information.</span></span>
- <span data-ttu-id="6934a-203">诊断信息的保持期。</span><span class="sxs-lookup"><span data-stu-id="6934a-203">The retention period for the diagnostic information.</span></span>
- <span data-ttu-id="6934a-204">控制诊断信息访问的权限。</span><span class="sxs-lookup"><span data-stu-id="6934a-204">Permissions that control access to the diagnostic information.</span></span>

## <a name="offline-diagnostics"></a><span data-ttu-id="6934a-205">脱机诊断</span><span class="sxs-lookup"><span data-stu-id="6934a-205">Offline diagnostics</span></span>
<span data-ttu-id="6934a-206">如果设备无法通过反馈中心或设置疑难解答收集诊断信息，则可以手动收集诊断信息。</span><span class="sxs-lookup"><span data-stu-id="6934a-206">In situations where the device is not able to collect diagnostics via Feedback Hub or the Setting Troubleshooter, you can collect diagnostics manually.</span></span> <span data-ttu-id="6934a-207">这是必需的一种情况是：设备无法连接到 Wi-Fi 或无法访问上面提到的其他方法。</span><span class="sxs-lookup"><span data-stu-id="6934a-207">One scenario where this is necessary is when the device cannot connect to Wi-Fi or you can't access other methods mentioned above.</span></span> <span data-ttu-id="6934a-208">诊断从设备收集崩溃转储和日志，帮助 Microsoft 支持工程师隔离问题。</span><span class="sxs-lookup"><span data-stu-id="6934a-208">The diagnostics collect crash dumps and logs from the device that help a Microsoft support engineer isolate issues.</span></span>

<span data-ttu-id="6934a-209">当设备通过 USB 电缆连接到电脑后，在文件资源管理器中显示时，这会起作用。</span><span class="sxs-lookup"><span data-stu-id="6934a-209">This works when the device shows up in File Explorer after connecting it to a PC via a USB cable.</span></span>

> [!NOTE]
> <span data-ttu-id="6934a-210">脱机诊断生成和管理的控制方式不同，具体取决于你的操作系统版本。</span><span class="sxs-lookup"><span data-stu-id="6934a-210">Offline Diagnostics generation and management is controlled differently depending on your OS version.</span></span> <span data-ttu-id="6934a-211">以前，它受遥测设置的控制，但现在通过 MDM 策略直接控制。</span><span class="sxs-lookup"><span data-stu-id="6934a-211">Previously it was controlled by the telemetry setting, but is now directly controlled via MDM policy.</span></span> <span data-ttu-id="6934a-212">如果是通过设置或 MDM 策略禁用的，则无法使用此机制收集诊断日志。</span><span class="sxs-lookup"><span data-stu-id="6934a-212">If disabled via either setting or MDM policy, then diagnostic logs cannot be collected using this mechanism.</span></span>

<span data-ttu-id="6934a-213">[Windows 全息版之前的行为 20H2](hololens-release-notes.md#windows-holographic-version-20h2)：</span><span class="sxs-lookup"><span data-stu-id="6934a-213">Behavior Prior to [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2):</span></span>
 - <span data-ttu-id="6934a-214">仅当用户通过 OOBE 或 [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) 策略值设置为 Full 时，才会启用脱机诊断， (Basic 是 HoloLens) 上的默认值。</span><span class="sxs-lookup"><span data-stu-id="6934a-214">Offline diagnostics is only enabled when user is either going through OOBE or [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) policy value is set to Full (Basic is default value on HoloLens).</span></span> 
- <span data-ttu-id="6934a-215">若要禁用脱机诊断，请在 "设置" " **应用 > 隐私** " 页上，选择 " **基本** " **诊断数据**。</span><span class="sxs-lookup"><span data-stu-id="6934a-215">To disable Offline diagnostics, go to **Settings App > Privacy** page and select **Basic** in **Diagnostic Data**.</span></span> <span data-ttu-id="6934a-216">在离线诊断依赖于遥测设置的生成上，它只会影响是否收集任何日志。</span><span class="sxs-lookup"><span data-stu-id="6934a-216">On builds where offline diagnostics depends on telemetry setting, it only impacts whether any logs are collected or not.</span></span> <span data-ttu-id="6934a-217">它不会影响收集的文件。</span><span class="sxs-lookup"><span data-stu-id="6934a-217">It does not impact what files are collected.</span></span>
- <span data-ttu-id="6934a-218">如果设备被锁定，则不会出现日志。</span><span class="sxs-lookup"><span data-stu-id="6934a-218">If device is locked then logs won't appear.</span></span>

<span data-ttu-id="6934a-219">生成 [Windows 全息版时，版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 和更高版本：</span><span class="sxs-lookup"><span data-stu-id="6934a-219">On builds [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) and onwards:</span></span>
- <span data-ttu-id="6934a-220">启用后备诊断后，将使用相应的设置[MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)将特定 MDM 策略控制</span><span class="sxs-lookup"><span data-stu-id="6934a-220">When Fallback Diagnostics is enabled will be controlled by specific MDM policy with corresponding setting [MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)</span></span>
- <span data-ttu-id="6934a-221">如果设备被锁定，则不会出现日志。</span><span class="sxs-lookup"><span data-stu-id="6934a-221">If device is locked then logs won't appear.</span></span>

<span data-ttu-id="6934a-222">观看此视频，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="6934a-222">Watch this video to learn more.</span></span>

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

<span data-ttu-id="6934a-223">请按照以下步骤收集诊断：</span><span class="sxs-lookup"><span data-stu-id="6934a-223">Follow these steps to collect diagnostics:</span></span>
1.  <span data-ttu-id="6934a-224">使用 USB 电缆将设备连接到您的 PC。</span><span class="sxs-lookup"><span data-stu-id="6934a-224">Connect the device with a USB cable to your PC.</span></span>
2.  <span data-ttu-id="6934a-225">在电脑上的文件资源管理器中，导航到 **"这台电脑 \<hololens-device> \Internal Storage"**。</span><span class="sxs-lookup"><span data-stu-id="6934a-225">In File Explorer on your PC, navigate to **'This PC\<hololens-device>\Internal Storage'**.</span></span>
3.  <span data-ttu-id="6934a-226">如果未显示 **内部存储** 文件夹，则设备正在等待用户登录。</span><span class="sxs-lookup"><span data-stu-id="6934a-226">If the **Internal Storage** folder does not show up, the device is waiting for a user to sign in.</span></span> <span data-ttu-id="6934a-227">登录或重启设备，方法是：按住电源按钮10秒。</span><span class="sxs-lookup"><span data-stu-id="6934a-227">Either sign-in or power cycle the device by holding the POWER button down for 10 seconds.</span></span>
4.  <span data-ttu-id="6934a-228">按下并立即释放 **电源 + 向下移动** 按钮。</span><span class="sxs-lookup"><span data-stu-id="6934a-228">Press and immediately release the **POWER + VOLUME DOWN** buttons together.</span></span>
5.  <span data-ttu-id="6934a-229">等待一分钟让设备准备 zip 存档。</span><span class="sxs-lookup"><span data-stu-id="6934a-229">Wait a minute for the device to prepare the zip archives.</span></span> <span data-ttu-id="6934a-230"> (在设备生成 zip 存档时，名为 HololensDiagnostics 的临时文件可能会变得可见。</span><span class="sxs-lookup"><span data-stu-id="6934a-230">(A temporary file named HololensDiagnostics.temp may become visible while the device generates the zip archives.</span></span> <span data-ttu-id="6934a-231">不要访问或保存该文件。</span><span class="sxs-lookup"><span data-stu-id="6934a-231">Do not access or save that file.</span></span> <span data-ttu-id="6934a-232">当进程完成时，它将替换为 zip 存档。 ) </span><span class="sxs-lookup"><span data-stu-id="6934a-232">When the process finishes it will be replaced by the zip archives.)</span></span>
6.  <span data-ttu-id="6934a-233">刷新文件资源管理器，然后导航到 **"\Documents"** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6934a-233">Refresh file explorer, and navigate to the **'\Documents'** folder.</span></span>
7.  <span data-ttu-id="6934a-234">复制诊断 ZIP 文件并将其与 Microsoft 支持团队共享。</span><span class="sxs-lookup"><span data-stu-id="6934a-234">Copy the diagnostics ZIP files and share them with the Microsoft support team.</span></span>

> [!NOTE]
> <span data-ttu-id="6934a-235">某些诊断 ZIP 文件可能包含个人身份信息。</span><span class="sxs-lookup"><span data-stu-id="6934a-235">Some of the diagnostics ZIP files may contain personally identifiable information.</span></span>
