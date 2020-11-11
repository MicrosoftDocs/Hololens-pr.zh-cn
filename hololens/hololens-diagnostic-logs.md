---
title: 收集和使用来自 HoloLens 设备的诊断信息
description: 收集和使用来自 HoloLens 设备的诊断信息
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
ms.openlocfilehash: b0a068bb50d033544b4bf44100d005dfedc1d94d
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162942"
---
# <span data-ttu-id="0361b-103">收集和使用来自 HoloLens 设备的诊断信息</span><span class="sxs-lookup"><span data-stu-id="0361b-103">Collect and use diagnostic information from HoloLens devices</span></span>

<span data-ttu-id="0361b-104">HoloLens 用户和管理员可以从以下四种不同的方法中进行选择，以从 HoloLens 收集诊断信息：</span><span class="sxs-lookup"><span data-stu-id="0361b-104">HoloLens users and administrators can choose from among four different methods to collect diagnostic information from HoloLens:</span></span>

- <span data-ttu-id="0361b-105">反馈中心应用</span><span class="sxs-lookup"><span data-stu-id="0361b-105">Feedback Hub app</span></span>
- <span data-ttu-id="0361b-106">DiagnosticLog 云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="0361b-106">DiagnosticLog CSP</span></span>
- <span data-ttu-id="0361b-107">“设置”应用</span><span class="sxs-lookup"><span data-stu-id="0361b-107">Settings app</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="0361b-108">设备诊断日志包含 (PII) 的个人身份信息，例如用户在典型操作期间启动哪些进程或应用程序。</span><span class="sxs-lookup"><span data-stu-id="0361b-108">Device diagnostic logs contain personally identifiable information (PII), such as about what processes or applications the user starts during typical operations.</span></span> <span data-ttu-id="0361b-109">当多个用户共享 HoloLens 设备时 (例如，用户使用不同的 Microsoft Azure Active Directory (AAD) 帐户登录到同一设备) 诊断日志可能包含适用于多个用户的 PII 信息。</span><span class="sxs-lookup"><span data-stu-id="0361b-109">When multiple users share a HoloLens device (for example, users sign in to the same device by using different Microsoft Azure Active Directory (AAD) accounts) the diagnostic logs may contain PII information that applies to multiple users.</span></span> <span data-ttu-id="0361b-110">有关详细信息，请参阅 [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)。</span><span class="sxs-lookup"><span data-stu-id="0361b-110">For more information, see [Microsoft Privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

<span data-ttu-id="0361b-111">下表比较了这三个集合方法。</span><span class="sxs-lookup"><span data-stu-id="0361b-111">The following table compares the three collection methods.</span></span> <span data-ttu-id="0361b-112">"方法名称" 链接到表格后面部分中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0361b-112">The method names link to more detailed information in the sections that follow the table.</span></span>

|<span data-ttu-id="0361b-113">方法</span><span class="sxs-lookup"><span data-stu-id="0361b-113">Method</span></span> |<span data-ttu-id="0361b-114">必备条件</span><span class="sxs-lookup"><span data-stu-id="0361b-114">Prerequisites</span></span> |<span data-ttu-id="0361b-115">数据位置</span><span class="sxs-lookup"><span data-stu-id="0361b-115">Data locations</span></span> |<span data-ttu-id="0361b-116">数据访问和使用</span><span class="sxs-lookup"><span data-stu-id="0361b-116">Data access and use</span></span> |<span data-ttu-id="0361b-117">数据保留</span><span class="sxs-lookup"><span data-stu-id="0361b-117">Data retention</span></span> |
| --- | --- | --- | --- | --- |
|[<span data-ttu-id="0361b-118">反馈中心</span><span class="sxs-lookup"><span data-stu-id="0361b-118">Feedback Hub</span></span>](#feedback-hub) |<span data-ttu-id="0361b-119">网络和 internet 连接</span><span class="sxs-lookup"><span data-stu-id="0361b-119">Network and internet connection</span></span><br /><br /><span data-ttu-id="0361b-120">反馈中心应用</span><span class="sxs-lookup"><span data-stu-id="0361b-120">Feedback Hub app</span></span><br /><br /><span data-ttu-id="0361b-121">将文件上传到 Microsoft 云的权限</span><span class="sxs-lookup"><span data-stu-id="0361b-121">Permission to upload files to the Microsoft cloud</span></span> |<span data-ttu-id="0361b-122">Microsoft cloud</span><span class="sxs-lookup"><span data-stu-id="0361b-122">Microsoft cloud</span></span><br /><br /><span data-ttu-id="0361b-123">HoloLens 设备 (可选) </span><span class="sxs-lookup"><span data-stu-id="0361b-123">HoloLens device (optional)</span></span> |<span data-ttu-id="0361b-124">用户请求协助、同意使用条款以及上载数据</span><span class="sxs-lookup"><span data-stu-id="0361b-124">User requests assistance, agrees to the terms of use, and uploads the data</span></span><br /><br /><span data-ttu-id="0361b-125">Microsoft 员工查看数据（与使用条款一致）</span><span class="sxs-lookup"><span data-stu-id="0361b-125">Microsoft employees view the data, as consistent with the terms of use</span></span> |<span data-ttu-id="0361b-126">云中的数据在由下一代隐私 (NGP) 定义的期间内保留。</span><span class="sxs-lookup"><span data-stu-id="0361b-126">Data in the cloud is retained for the period that is defined by Next Generation Privacy (NGP).</span></span> <span data-ttu-id="0361b-127">然后，将自动删除该数据。</span><span class="sxs-lookup"><span data-stu-id="0361b-127">Then the data is deleted automatically.</span></span><br /><br /><span data-ttu-id="0361b-128">具有 **设备所有者** 或 **管理员** 权限的用户可以随时删除设备上的数据。</span><span class="sxs-lookup"><span data-stu-id="0361b-128">Data on the device can be deleted at any time by a user who has **Device owner** or **Admin** permissions.</span></span> |
|[<span data-ttu-id="0361b-129">设置疑难解答</span><span class="sxs-lookup"><span data-stu-id="0361b-129">Settings Troubleshooter</span></span>](#settings-troubleshooter) |<span data-ttu-id="0361b-130">“设置”应用</span><span class="sxs-lookup"><span data-stu-id="0361b-130">Settings app</span></span> |<span data-ttu-id="0361b-131">HoloLens 设备</span><span class="sxs-lookup"><span data-stu-id="0361b-131">HoloLens device</span></span><br /><br /><span data-ttu-id="0361b-132">已连接的计算机 (可选) </span><span class="sxs-lookup"><span data-stu-id="0361b-132">Connected computer (optional)</span></span> |<span data-ttu-id="0361b-133">用户存储数据，只有用户访问数据 (除非用户特别与另一个用户共享数据) 。</span><span class="sxs-lookup"><span data-stu-id="0361b-133">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="0361b-134">数据将保留，直到用户删除它。 \*</span><span class="sxs-lookup"><span data-stu-id="0361b-134">The data is retained until the user deletes it.\*</span></span> |
|[<span data-ttu-id="0361b-135">DiagnosticLog 云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="0361b-135">DiagnosticLog CSP</span></span>](#diagnosticlog-csp) |<span data-ttu-id="0361b-136">网络连接</span><span class="sxs-lookup"><span data-stu-id="0361b-136">Network connection</span></span><br /><br /><span data-ttu-id="0361b-137">支持 DiagnosticLog CSP 的 MDM 环境</span><span class="sxs-lookup"><span data-stu-id="0361b-137">MDM environment that supports the DiagnosticLog CSP</span></span> |<span data-ttu-id="0361b-138">管理员配置存储位置</span><span class="sxs-lookup"><span data-stu-id="0361b-138">Administrator configures storage locations</span></span> |<span data-ttu-id="0361b-139">在托管环境中，用户隐式内容对数据的管理员访问。</span><span class="sxs-lookup"><span data-stu-id="0361b-139">In the managed environment, the user implicitly consents to administrator access to the data.</span></span><br /><br /><span data-ttu-id="0361b-140">管理员配置访问角色和权限。</span><span class="sxs-lookup"><span data-stu-id="0361b-140">Administrator configures access roles and permissions.</span></span> | <span data-ttu-id="0361b-141">管理员配置保留策略。</span><span class="sxs-lookup"><span data-stu-id="0361b-141">Administrator configures retention policy.</span></span> |
|[<span data-ttu-id="0361b-142">离线诊断</span><span class="sxs-lookup"><span data-stu-id="0361b-142">Offline diagnostics</span></span>](#offline-diagnostics) |<span data-ttu-id="0361b-143">设备配置：</span><span class="sxs-lookup"><span data-stu-id="0361b-143">Device configuration:</span></span><ul><li><span data-ttu-id="0361b-144">已接通电源并已连接到计算机</span><span class="sxs-lookup"><span data-stu-id="0361b-144">Powered on and connected to computer</span></span></li><li><span data-ttu-id="0361b-145">电源和音量按钮正常工作</span><span class="sxs-lookup"><span data-stu-id="0361b-145">Power and Volume buttons functioning</span></span></li></ul> |<span data-ttu-id="0361b-146">HoloLens 设备</span><span class="sxs-lookup"><span data-stu-id="0361b-146">HoloLens device</span></span><br /><br /><span data-ttu-id="0361b-147">已连接计算机</span><span class="sxs-lookup"><span data-stu-id="0361b-147">Connected computer</span></span> |<span data-ttu-id="0361b-148">用户存储数据，只有用户访问数据 (除非用户特别与另一个用户共享数据) 。</span><span class="sxs-lookup"><span data-stu-id="0361b-148">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="0361b-149">数据将保留，直到用户删除它。</span><span class="sxs-lookup"><span data-stu-id="0361b-149">The data is retained until the user deletes it.</span></span> | 


-   <span data-ttu-id="0361b-150">最终用户负责与其他人共享日志。</span><span class="sxs-lookup"><span data-stu-id="0361b-150">End-user is responsible for sharing the logs responsibly with someone else.</span></span> <span data-ttu-id="0361b-151">这些文件主要用于联系客户服务和支持人员。</span><span class="sxs-lookup"><span data-stu-id="0361b-151">These files are primarily useful when contacting customer service and support.</span></span>  

## <span data-ttu-id="0361b-152">反馈中心</span><span class="sxs-lookup"><span data-stu-id="0361b-152">Feedback Hub</span></span>

<span data-ttu-id="0361b-153">HoloLens 用户可以使用 Microsoft 反馈中心桌面应用向 Microsoft 支持人员发送诊断信息。</span><span class="sxs-lookup"><span data-stu-id="0361b-153">A HoloLens user can use the Microsoft Feedback Hub desktop app to send diagnostic information to Microsoft Support.</span></span> <span data-ttu-id="0361b-154">有关详细信息和完整说明，请参阅 [向我们提供反馈](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="0361b-154">For details and complete instructions, see [Give us feedback](hololens-feedback.md).</span></span>  

> [!NOTE]  
> <span data-ttu-id="0361b-155">**商业版或企业版用户：** 如果你使用 "反馈中心" 应用报告与 MDM、资源调配或任何其他设备管理方面相关的问题，请将应用类别更改为 "**企业管理**  >  **设备" 类别**。</span><span class="sxs-lookup"><span data-stu-id="0361b-155">**Commercial or enterprise users:** If you use the Feedback Hub app to report a problem that relates to MDM, provisioning, or any other device management aspect, change the app category to **Enterprise Management** > **Device category**.</span></span>

### <span data-ttu-id="0361b-156">必备条件</span><span class="sxs-lookup"><span data-stu-id="0361b-156">Prerequisites</span></span>

- <span data-ttu-id="0361b-157">设备已连接到网络。</span><span class="sxs-lookup"><span data-stu-id="0361b-157">The device is connected to a network.</span></span>
- <span data-ttu-id="0361b-158">"反馈中心" 应用在用户的桌面计算机上可用，用户可以将文件上传到 Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="0361b-158">The Feedback Hub app is available on the user's desktop computer, and the user can upload files to the Microsoft cloud.</span></span>

### <span data-ttu-id="0361b-159">数据位置、访问和保留</span><span class="sxs-lookup"><span data-stu-id="0361b-159">Data locations, access, and retention</span></span>

<span data-ttu-id="0361b-160">通过同意 "反馈中心" 的使用条款，用户明确内容该协议) 所定义的数据 (的存储和使用。</span><span class="sxs-lookup"><span data-stu-id="0361b-160">By agreeing to the terms-of-use of the Feedback Hub, the user explicitly consents to the storage and usage of the data (as defined by that agreement).</span></span>

<span data-ttu-id="0361b-161">反馈中心为用户提供两个位置来存储诊断信息：</span><span class="sxs-lookup"><span data-stu-id="0361b-161">The Feedback Hub provides two places for the user to store diagnostic information:</span></span>

- <span data-ttu-id="0361b-162">**Microsoft 云**。</span><span class="sxs-lookup"><span data-stu-id="0361b-162">**The Microsoft cloud**.</span></span> <span data-ttu-id="0361b-163">用户使用 "反馈中心" 应用上载的数据将存储在与下一代隐私 (NGP) 要求一致的天数内。</span><span class="sxs-lookup"><span data-stu-id="0361b-163">Data that the user uploads by using the Feedback Hub app is stored for the number of days that is consistent with Next Generation Privacy (NGP) requirements.</span></span> <span data-ttu-id="0361b-164">Microsoft 员工可以使用 NGP 兼容的查看器在此期间访问信息。</span><span class="sxs-lookup"><span data-stu-id="0361b-164">Microsoft employees can use an NGP-compliant viewer to access the information during this period.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="0361b-165">这些要求适用于所有 "反馈中心" 类别中的数据。</span><span class="sxs-lookup"><span data-stu-id="0361b-165">These requirements apply to data in all Feedback Hub categories.</span></span>

- <span data-ttu-id="0361b-166">**HoloLens 设备**。</span><span class="sxs-lookup"><span data-stu-id="0361b-166">**The HoloLens device**.</span></span> <span data-ttu-id="0361b-167">在 "反馈中心" 中存档报表时，用户可以选择 " **保存诊断的本地副本" 和 "在提供反馈时创建的附件**"。</span><span class="sxs-lookup"><span data-stu-id="0361b-167">While filing a report in Feedback Hub, the user can select **Save a local copy of diagnostics and attachments created when giving feedback**.</span></span> <span data-ttu-id="0361b-168">如果用户选择此选项，则反馈中心会在 HoloLens 设备上存储诊断信息的副本。</span><span class="sxs-lookup"><span data-stu-id="0361b-168">If the user selects this option, the Feedback Hub stores a copy of the diagnostic information on the HoloLens device.</span></span> <span data-ttu-id="0361b-169">此信息仍可供用户访问 (或使用该帐户登录 HoloLens) 的任何人。</span><span class="sxs-lookup"><span data-stu-id="0361b-169">This information remains accessible to the user (or anyone that uses that account to sign in to HoloLens).</span></span> <span data-ttu-id="0361b-170">若要删除此信息，用户必须拥有设备 **所有者** 或设备的 **管理员** 权限。</span><span class="sxs-lookup"><span data-stu-id="0361b-170">To delete this information, a user must have **Device owner** or **Admin** permissions on the device.</span></span> <span data-ttu-id="0361b-171">具有相应权限的用户可以登录到反馈中心，选择 "**设置**  >  "**查看诊断日志**，然后删除信息。</span><span class="sxs-lookup"><span data-stu-id="0361b-171">A user who has the appropriate permissions can sign in to the Feedback Hub, select **Settings** > **View diagnostics logs**, and delete the information.</span></span>

## <span data-ttu-id="0361b-172">设置疑难解答</span><span class="sxs-lookup"><span data-stu-id="0361b-172">Settings Troubleshooter</span></span>

<span data-ttu-id="0361b-173">HoloLens 用户可以使用设备上的 "设置" 应用对问题进行故障排除和收集诊断信息。</span><span class="sxs-lookup"><span data-stu-id="0361b-173">A HoloLens user can use the Settings app on the device to troubleshoot problems and collect diagnostic information.</span></span> <span data-ttu-id="0361b-174">为此，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="0361b-174">To do this, follow these steps:</span></span>

1. <span data-ttu-id="0361b-175">打开 "设置" 应用，然后选择 "**更新 & 安全**  >  **疑难解答**" 页面。</span><span class="sxs-lookup"><span data-stu-id="0361b-175">Open the Settings app and select **Update & Security** > **Troubleshoot** page.</span></span>
1. <span data-ttu-id="0361b-176">选择相应的区域，然后选择 " **开始**"。</span><span class="sxs-lookup"><span data-stu-id="0361b-176">Select the appropriate area, and select **Start**.</span></span>
1. <span data-ttu-id="0361b-177">重现问题。</span><span class="sxs-lookup"><span data-stu-id="0361b-177">Reproduce the issue.</span></span>
1. <span data-ttu-id="0361b-178">重现问题后，返回到 "设置"，然后选择 " **停止**"。</span><span class="sxs-lookup"><span data-stu-id="0361b-178">After you reproduce the issue, return to Settings and then select **Stop**.</span></span>

### <span data-ttu-id="0361b-179">必备条件</span><span class="sxs-lookup"><span data-stu-id="0361b-179">Prerequisites</span></span>

- <span data-ttu-id="0361b-180">"设置" 应用已安装在设备上，可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="0361b-180">The Settings app is installed on the device and is available to the user.</span></span>

### <span data-ttu-id="0361b-181">数据位置、访问和保留</span><span class="sxs-lookup"><span data-stu-id="0361b-181">Data locations, access, and retention</span></span>

<span data-ttu-id="0361b-182">由于用户启动数据收集，因此用户隐式内容诊断信息的存储。</span><span class="sxs-lookup"><span data-stu-id="0361b-182">Because the user starts the data collection, the user implicitly consents to the storage of the diagnostic information.</span></span> <span data-ttu-id="0361b-183">只有用户或与用户共享数据的任何人都可以访问数据。</span><span class="sxs-lookup"><span data-stu-id="0361b-183">Only the user, or anyone with whom that the user shares the data, can access the data.</span></span>

<span data-ttu-id="0361b-184">诊断信息存储在设备上。</span><span class="sxs-lookup"><span data-stu-id="0361b-184">The diagnostic information is stored on the device.</span></span> <span data-ttu-id="0361b-185">如果设备连接到用户的计算机，则该信息也驻留在计算机上的以下文件中：</span><span class="sxs-lookup"><span data-stu-id="0361b-185">If the device is connected to the user's computer, the information also resides on the computer in the following file:</span></span>

> <span data-ttu-id="0361b-186">此 PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*></span><span class="sxs-lookup"><span data-stu-id="0361b-186">This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents\\Trace\<*ddmmyyhhmmss*>.etl</span></span>

> [!NOTE]  
> <span data-ttu-id="0361b-187">在此文件路径和名称中， \<*HoloLens device name*> 表示 HoloLens 设备的名称，并 \<*ddmmyyhhmmss*> 表示文件的创建日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0361b-187">In this file path and name, \<*HoloLens device name*> represents the name of the HoloLens device, and \<*ddmmyyhhmmss*> represents the date and time that the file was created.</span></span>

<span data-ttu-id="0361b-188">诊断信息将保留在这些位置中，直到用户删除它。</span><span class="sxs-lookup"><span data-stu-id="0361b-188">The diagnostic information remains in these locations until the user deletes it.</span></span>

## <span data-ttu-id="0361b-189">DiagnosticLog 云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="0361b-189">DiagnosticLog CSP</span></span>

<span data-ttu-id="0361b-190">在 (MDM) 环境的移动设备管理中，IT 管理员可以使用 [DiagnosticLog 配置服务提供程序 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) 来配置已注册的 HoloLens 设备上的诊断设置。</span><span class="sxs-lookup"><span data-stu-id="0361b-190">In a Mobile Device Management (MDM) environment, the IT administrator can use the the [DiagnosticLog configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) to configure diagnostic settings on enrolled HoloLens devices.</span></span> <span data-ttu-id="0361b-191">IT 管理员可以配置这些设置以从注册的设备收集日志。</span><span class="sxs-lookup"><span data-stu-id="0361b-191">The IT administrator can configure these settings to collect logs from enrolled devices.</span></span>

### <span data-ttu-id="0361b-192">必备条件</span><span class="sxs-lookup"><span data-stu-id="0361b-192">Prerequisites</span></span>

- <span data-ttu-id="0361b-193">设备已连接到网络。</span><span class="sxs-lookup"><span data-stu-id="0361b-193">The device is connected to a network.</span></span>
- <span data-ttu-id="0361b-194">设备注册到支持 DiagnosticLog CSP 的 MDM 环境中。</span><span class="sxs-lookup"><span data-stu-id="0361b-194">The device is enrolled in an MDM environment that supports the DiagnosticLog CSP.</span></span>

### <span data-ttu-id="0361b-195">数据位置、访问和保留</span><span class="sxs-lookup"><span data-stu-id="0361b-195">Data locations, access, and retention</span></span>

<span data-ttu-id="0361b-196">由于设备是托管环境的一部分，因此用户隐式内容对诊断信息的管理访问。</span><span class="sxs-lookup"><span data-stu-id="0361b-196">Because the device is part of the managed environment, the user implicitly consents to administrative access to diagnostic information.</span></span>

<span data-ttu-id="0361b-197">IT 管理员使用 DiagnosticLog CSP 配置数据存储、保留和访问策略，包括管理以下各项的策略：</span><span class="sxs-lookup"><span data-stu-id="0361b-197">The IT administrator uses the DiagnosticLog CSP to configure the data storage, retention, and access policies, including the policies that govern the following:</span></span>

- <span data-ttu-id="0361b-198">存储诊断信息的云基础结构。</span><span class="sxs-lookup"><span data-stu-id="0361b-198">The cloud infrastructure that stores the diagnostic information.</span></span>
- <span data-ttu-id="0361b-199">诊断信息的保留期。</span><span class="sxs-lookup"><span data-stu-id="0361b-199">The retention period for the diagnostic information.</span></span>
- <span data-ttu-id="0361b-200">控制诊断信息访问权限的权限。</span><span class="sxs-lookup"><span data-stu-id="0361b-200">Permissions that control access to the diagnostic information.</span></span>

## <span data-ttu-id="0361b-201">离线诊断</span><span class="sxs-lookup"><span data-stu-id="0361b-201">Offline diagnostics</span></span>
<span data-ttu-id="0361b-202">如果设备不能通过 "反馈中心" 或 "设置疑难解答" 收集诊断，则可以手动收集诊断。</span><span class="sxs-lookup"><span data-stu-id="0361b-202">In situations where the device is not able to collect diagnostics via Feedback Hub or the Setting Troubleshooter, you can collect diagnostics manually.</span></span> <span data-ttu-id="0361b-203">需要此功能的一种情况是设备无法连接到 Wi-fi。</span><span class="sxs-lookup"><span data-stu-id="0361b-203">One scenario where this is necessary is when the device cannot connect to Wi-Fi.</span></span> <span data-ttu-id="0361b-204">诊断程序从设备收集故障转储和日志，帮助 Microsoft 支持工程师隔离问题。</span><span class="sxs-lookup"><span data-stu-id="0361b-204">The diagnostics collect crash dumps and logs from the device that help a Microsoft support engineer isolate issues.</span></span>

<span data-ttu-id="0361b-205">在通过 USB 电缆将设备连接到电脑后，在文件资源管理器中显示该设备时，此操作将起作用。</span><span class="sxs-lookup"><span data-stu-id="0361b-205">This works when the device shows up in File Explorer after connecting it to a PC via a USB cable.</span></span> 

> [!NOTE]
> <span data-ttu-id="0361b-206">离线诊断生成和管理的控制方式因操作系统版本而异。</span><span class="sxs-lookup"><span data-stu-id="0361b-206">Offline Diagnostics generation and management is controlled differently depending on your OS version.</span></span> <span data-ttu-id="0361b-207">以前它由遥测设置控制，但现在通过策略直接控制。</span><span class="sxs-lookup"><span data-stu-id="0361b-207">Previously it was controlled by the telemetry setting, but is now directly controlled via policy.</span></span> 

<span data-ttu-id="0361b-208">[Windows 全息版之前的行为 Verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2)：</span><span class="sxs-lookup"><span data-stu-id="0361b-208">Behavior Prior to [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2):</span></span>
 - <span data-ttu-id="0361b-209">仅当用户通过 OOBE 或 [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) 策略值设置为 "完全" 时，才会启用脱机诊断。在 HoloLens) 上，"基本" 默认值为 " (基本"。</span><span class="sxs-lookup"><span data-stu-id="0361b-209">Offline diagnostics is only enabled when user is either going through OOBE or [System\AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry) policy value is set to Full (Basic is default value on HoloLens).</span></span> 
- <span data-ttu-id="0361b-210">若要禁用脱机诊断，请转到 "**设置" 应用 > 隐私**"页面，然后选择" 在**诊断数据**中**基本**"。</span><span class="sxs-lookup"><span data-stu-id="0361b-210">To disable Offline diagnostics, go to **Settings App > Privacy** page and select **Basic** in **Diagnostic Data**.</span></span> <span data-ttu-id="0361b-211">在 "离线诊断" 依赖 "遥测" 设置的版本中，它只会影响是否收集任何日志。</span><span class="sxs-lookup"><span data-stu-id="0361b-211">On builds where offline diagnostics depends on telemetry setting, it only impacts whether any logs are collected or not.</span></span> <span data-ttu-id="0361b-212">它不会影响收集的文件。</span><span class="sxs-lookup"><span data-stu-id="0361b-212">It does not impact what files are collected.</span></span>
- <span data-ttu-id="0361b-213">如果设备处于锁定状态，则不会显示日志。</span><span class="sxs-lookup"><span data-stu-id="0361b-213">If device is locked then logs won't appear.</span></span>

<span data-ttu-id="0361b-214">在生成 [Windows 全息版、Verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 和向上：</span><span class="sxs-lookup"><span data-stu-id="0361b-214">On builds [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) and onwards:</span></span>
- <span data-ttu-id="0361b-215">启用回退诊断后，将由特定 MDM 策略控制，其中包含相应的设置 [MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)</span><span class="sxs-lookup"><span data-stu-id="0361b-215">When Fallback Diagnostics is enabled will be controlled by specific MDM policy with corresponding setting [MixedReality/FallbackDiagnostics](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-fallbackdiagnostics)</span></span>
- <span data-ttu-id="0361b-216">如果设备处于锁定状态，则不会显示日志。</span><span class="sxs-lookup"><span data-stu-id="0361b-216">If device is locked then logs won't appear.</span></span>


<span data-ttu-id="0361b-217">观看此视频以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="0361b-217">Watch this video to learn more.</span></span> 

> [!VIDEO https://channel9.msdn.com/Shows/Docs-Mixed-Reality/Gathering-Diagnostic-Files-on-HoloLens2/player]

<span data-ttu-id="0361b-218">请按照以下步骤收集诊断：</span><span class="sxs-lookup"><span data-stu-id="0361b-218">Follow these steps to collect diagnostics:</span></span>
1.  <span data-ttu-id="0361b-219">将设备与 USB 电缆连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="0361b-219">Connect the device with a USB cable to your PC.</span></span>
2.  <span data-ttu-id="0361b-220">在电脑上的文件资源管理器中，导航到 **"这台电脑 \<hololens-device> \Internal 存储"**。</span><span class="sxs-lookup"><span data-stu-id="0361b-220">In File Explorer on your PC, navigate to **'This PC\<hololens-device>\Internal Storage'**.</span></span>
3.  <span data-ttu-id="0361b-221">如果未显示 " **内部存储** " 文件夹，则表示设备正在等待用户登录。</span><span class="sxs-lookup"><span data-stu-id="0361b-221">If the **Internal Storage** folder does not show up, the device is waiting for a user to sign in.</span></span> <span data-ttu-id="0361b-222">您可以通过按住电源按钮10秒钟来登录或重启设备。</span><span class="sxs-lookup"><span data-stu-id="0361b-222">Either sign-in or power cycle the device by holding the POWER button down for 10 seconds.</span></span>
4.  <span data-ttu-id="0361b-223">按下并立即释放 **+ "音量按下** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="0361b-223">Press and immediately release the **POWER + VOLUME DOWN** buttons together.</span></span>
5.  <span data-ttu-id="0361b-224">等待一分钟，让设备准备 zip 存档。</span><span class="sxs-lookup"><span data-stu-id="0361b-224">Wait a minute for the device to prepare the zip archives.</span></span> <span data-ttu-id="0361b-225"> (在设备生成 zip 存档时，名为 HololensDiagnostics 的临时文件可能会变得可见。</span><span class="sxs-lookup"><span data-stu-id="0361b-225">(A temporary file named HololensDiagnostics.temp may become visible while the device generates the zip archives.</span></span> <span data-ttu-id="0361b-226">不要访问或保存该文件。</span><span class="sxs-lookup"><span data-stu-id="0361b-226">Do not access or save that file.</span></span> <span data-ttu-id="0361b-227">过程完成后，zip 存档将替换该过程。 ) </span><span class="sxs-lookup"><span data-stu-id="0361b-227">When the process finishes it will be replaced by the zip archives.)</span></span>
6.  <span data-ttu-id="0361b-228">刷新文件资源管理器，并导航到 **"\Documents"** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0361b-228">Refresh file explorer, and navigate to the **'\Documents'** folder.</span></span>
7.  <span data-ttu-id="0361b-229">复制诊断 ZIP 文件，并将其与 Microsoft 支持团队共享。</span><span class="sxs-lookup"><span data-stu-id="0361b-229">Copy the diagnostics ZIP files and share them with the Microsoft support team.</span></span>

> [!NOTE]
> <span data-ttu-id="0361b-230">某些诊断 ZIP 文件可能包含个人身份信息。</span><span class="sxs-lookup"><span data-stu-id="0361b-230">Some of the diagnostics ZIP files may contain personally identifiable information.</span></span>



