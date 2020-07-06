---
title: 从 HoloLens 设备收集和使用诊断信息
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 03/23/2020
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
ms.openlocfilehash: f11128c66845f0e062a006855fd75ca66ffc4e5e
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827973"
---
# <span data-ttu-id="c0cd2-102">从 HoloLens 设备收集和使用诊断信息</span><span class="sxs-lookup"><span data-stu-id="c0cd2-102">Collect and use diagnostic information from HoloLens devices</span></span>

<span data-ttu-id="c0cd2-103">HoloLens 用户和管理员可以从以下四种不同的方法中进行选择，以从 HoloLens 收集诊断信息：</span><span class="sxs-lookup"><span data-stu-id="c0cd2-103">HoloLens users and administrators can choose from among four different methods to collect diagnostic information from HoloLens:</span></span>

- <span data-ttu-id="c0cd2-104">反馈中心应用</span><span class="sxs-lookup"><span data-stu-id="c0cd2-104">Feedback Hub app</span></span>
- <span data-ttu-id="c0cd2-105">DiagnosticLog 云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="c0cd2-105">DiagnosticLog CSP</span></span>
- <span data-ttu-id="c0cd2-106">“设置”应用</span><span class="sxs-lookup"><span data-stu-id="c0cd2-106">Settings app</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="c0cd2-107">设备诊断日志包含个人身份信息（PII），如用户在典型操作期间启动的进程或应用程序。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-107">Device diagnostic logs contain personally identifiable information (PII), such as about what processes or applications the user starts during typical operations.</span></span> <span data-ttu-id="c0cd2-108">当多个用户共享 HoloLens 设备时（例如，用户使用不同的 Microsoft Azure Active Directory （AAD）帐户登录到同一设备），诊断日志可能包含适用于多个用户的 PII 信息。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-108">When multiple users share a HoloLens device (for example, users sign in to the same device by using different Microsoft Azure Active Directory (AAD) accounts) the diagnostic logs may contain PII information that applies to multiple users.</span></span> <span data-ttu-id="c0cd2-109">有关详细信息，请参阅[Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-109">For more information, see [Microsoft Privacy statement](https://privacy.microsoft.com/privacystatement).</span></span>

<span data-ttu-id="c0cd2-110">下表比较了这三个集合方法。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-110">The following table compares the three collection methods.</span></span> <span data-ttu-id="c0cd2-111">"方法名称" 链接到表格后面部分中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-111">The method names link to more detailed information in the sections that follow the table.</span></span>

|<span data-ttu-id="c0cd2-112">方法</span><span class="sxs-lookup"><span data-stu-id="c0cd2-112">Method</span></span> |<span data-ttu-id="c0cd2-113">必备条件</span><span class="sxs-lookup"><span data-stu-id="c0cd2-113">Prerequisites</span></span> |<span data-ttu-id="c0cd2-114">数据位置</span><span class="sxs-lookup"><span data-stu-id="c0cd2-114">Data locations</span></span> |<span data-ttu-id="c0cd2-115">数据访问和使用</span><span class="sxs-lookup"><span data-stu-id="c0cd2-115">Data access and use</span></span> |<span data-ttu-id="c0cd2-116">数据保留</span><span class="sxs-lookup"><span data-stu-id="c0cd2-116">Data retention</span></span> |
| --- | --- | --- | --- | --- |
|[<span data-ttu-id="c0cd2-117">反馈中心</span><span class="sxs-lookup"><span data-stu-id="c0cd2-117">Feedback Hub</span></span>](#feedback-hub) |<span data-ttu-id="c0cd2-118">网络和 internet 连接</span><span class="sxs-lookup"><span data-stu-id="c0cd2-118">Network and internet connection</span></span><br /><br /><span data-ttu-id="c0cd2-119">反馈中心应用</span><span class="sxs-lookup"><span data-stu-id="c0cd2-119">Feedback Hub app</span></span><br /><br /><span data-ttu-id="c0cd2-120">将文件上传到 Microsoft 云的权限</span><span class="sxs-lookup"><span data-stu-id="c0cd2-120">Permission to upload files to the Microsoft cloud</span></span> |<span data-ttu-id="c0cd2-121">Microsoft cloud</span><span class="sxs-lookup"><span data-stu-id="c0cd2-121">Microsoft cloud</span></span><br /><br /><span data-ttu-id="c0cd2-122">HoloLens 设备（可选）</span><span class="sxs-lookup"><span data-stu-id="c0cd2-122">HoloLens device (optional)</span></span> |<span data-ttu-id="c0cd2-123">用户请求协助、同意使用条款以及上载数据</span><span class="sxs-lookup"><span data-stu-id="c0cd2-123">User requests assistance, agrees to the terms of use, and uploads the data</span></span><br /><br /><span data-ttu-id="c0cd2-124">Microsoft 员工查看数据（与使用条款一致）</span><span class="sxs-lookup"><span data-stu-id="c0cd2-124">Microsoft employees view the data, as consistent with the terms of use</span></span> |<span data-ttu-id="c0cd2-125">云中的数据在由下一代隐私（NGP）定义的时间段内保留。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-125">Data in the cloud is retained for the period that is defined by Next Generation Privacy (NGP).</span></span> <span data-ttu-id="c0cd2-126">然后，将自动删除该数据。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-126">Then the data is deleted automatically.</span></span><br /><br /><span data-ttu-id="c0cd2-127">具有**设备所有者**或**管理员**权限的用户可以随时删除设备上的数据。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-127">Data on the device can be deleted at any time by a user who has **Device owner** or **Admin** permissions.</span></span> |
|[<span data-ttu-id="c0cd2-128">设置疑难解答</span><span class="sxs-lookup"><span data-stu-id="c0cd2-128">Settings Troubleshooter</span></span>](#settings-troubleshooter) |<span data-ttu-id="c0cd2-129">“设置”应用</span><span class="sxs-lookup"><span data-stu-id="c0cd2-129">Settings app</span></span> |<span data-ttu-id="c0cd2-130">HoloLens 设备</span><span class="sxs-lookup"><span data-stu-id="c0cd2-130">HoloLens device</span></span><br /><br /><span data-ttu-id="c0cd2-131">已连接的计算机（可选）</span><span class="sxs-lookup"><span data-stu-id="c0cd2-131">Connected computer (optional)</span></span> |<span data-ttu-id="c0cd2-132">用户存储数据，并且只有用户访问数据（除非用户特别与另一个用户共享数据）。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-132">The user stores the data, and only the user accesses the data (unless the user specifically shares the data with another user).</span></span> |<span data-ttu-id="c0cd2-133">数据将保留，直到用户删除它。 \*</span><span class="sxs-lookup"><span data-stu-id="c0cd2-133">The data is retained until the user deletes it.\*</span></span> |
|[<span data-ttu-id="c0cd2-134">DiagnosticLog 云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="c0cd2-134">DiagnosticLog CSP</span></span>](#diagnosticlog-csp) |<span data-ttu-id="c0cd2-135">网络连接</span><span class="sxs-lookup"><span data-stu-id="c0cd2-135">Network connection</span></span><br /><br /><span data-ttu-id="c0cd2-136">支持 DiagnosticLog CSP 的 MDM 环境</span><span class="sxs-lookup"><span data-stu-id="c0cd2-136">MDM environment that supports the DiagnosticLog CSP</span></span> |<span data-ttu-id="c0cd2-137">管理员配置存储位置</span><span class="sxs-lookup"><span data-stu-id="c0cd2-137">Administrator configures storage locations</span></span> |<span data-ttu-id="c0cd2-138">在托管环境中，用户隐式内容对数据的管理员访问。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-138">In the managed environment, the user implicitly consents to administrator access to the data.</span></span><br /><br /><span data-ttu-id="c0cd2-139">管理员配置访问角色和权限。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-139">Administrator configures access roles and permissions.</span></span> | <span data-ttu-id="c0cd2-140">管理员配置保留策略。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-140">Administrator configures retention policy.</span></span> |


-   <span data-ttu-id="c0cd2-141">最终用户负责与其他人共享日志。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-141">End-user is responsible for sharing the logs responsibly with someone else.</span></span> <span data-ttu-id="c0cd2-142">这些文件主要用于联系客户服务和支持人员。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-142">These files are primarily useful when contacting customer service and support.</span></span>  

## <span data-ttu-id="c0cd2-143">反馈中心</span><span class="sxs-lookup"><span data-stu-id="c0cd2-143">Feedback Hub</span></span>

<span data-ttu-id="c0cd2-144">HoloLens 用户可以使用 Microsoft 反馈中心桌面应用向 Microsoft 支持人员发送诊断信息。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-144">A HoloLens user can use the Microsoft Feedback Hub desktop app to send diagnostic information to Microsoft Support.</span></span> <span data-ttu-id="c0cd2-145">有关详细信息和完整说明，请参阅[向我们提供反馈](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-145">For details and complete instructions, see [Give us feedback](hololens-feedback.md).</span></span>  

> [!NOTE]  
> <span data-ttu-id="c0cd2-146">**商业版或企业版用户：** 如果你使用 "反馈中心" 应用报告与 MDM、资源调配或任何其他设备管理方面相关的问题，请将应用类别更改为 "**企业管理**  >  **设备" 类别**。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-146">**Commercial or enterprise users:** If you use the Feedback Hub app to report a problem that relates to MDM, provisioning, or any other device management aspect, change the app category to **Enterprise Management** > **Device category**.</span></span>

### <span data-ttu-id="c0cd2-147">必备条件</span><span class="sxs-lookup"><span data-stu-id="c0cd2-147">Prerequisites</span></span>

- <span data-ttu-id="c0cd2-148">设备已连接到网络。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-148">The device is connected to a network.</span></span>
- <span data-ttu-id="c0cd2-149">"反馈中心" 应用在用户的桌面计算机上可用，用户可以将文件上传到 Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-149">The Feedback Hub app is available on the user's desktop computer, and the user can upload files to the Microsoft cloud.</span></span>

### <span data-ttu-id="c0cd2-150">数据位置、访问和保留</span><span class="sxs-lookup"><span data-stu-id="c0cd2-150">Data locations, access, and retention</span></span>

<span data-ttu-id="c0cd2-151">通过同意 "反馈中心" 的使用条款，用户明确内容数据的存储和使用情况（由该协议定义）。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-151">By agreeing to the terms-of-use of the Feedback Hub, the user explicitly consents to the storage and usage of the data (as defined by that agreement).</span></span>

<span data-ttu-id="c0cd2-152">反馈中心为用户提供两个位置来存储诊断信息：</span><span class="sxs-lookup"><span data-stu-id="c0cd2-152">The Feedback Hub provides two places for the user to store diagnostic information:</span></span>

- <span data-ttu-id="c0cd2-153">**Microsoft 云**。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-153">**The Microsoft cloud**.</span></span> <span data-ttu-id="c0cd2-154">用户使用 "反馈中心" 应用上载的数据将存储在与下一代隐私（NGP）要求一致的天数内。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-154">Data that the user uploads by using the Feedback Hub app is stored for the number of days that is consistent with Next Generation Privacy (NGP) requirements.</span></span> <span data-ttu-id="c0cd2-155">Microsoft 员工可以使用 NGP 兼容的查看器在此期间访问信息。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-155">Microsoft employees can use an NGP-compliant viewer to access the information during this period.</span></span>
   > [!NOTE]  
   > <span data-ttu-id="c0cd2-156">这些要求适用于所有 "反馈中心" 类别中的数据。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-156">These requirements apply to data in all Feedback Hub categories.</span></span>

- <span data-ttu-id="c0cd2-157">**HoloLens 设备**。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-157">**The HoloLens device**.</span></span> <span data-ttu-id="c0cd2-158">在 "反馈中心" 中存档报表时，用户可以选择 "**保存诊断的本地副本" 和 "在提供反馈时创建的附件**"。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-158">While filing a report in Feedback Hub, the user can select **Save a local copy of diagnostics and attachments created when giving feedback**.</span></span> <span data-ttu-id="c0cd2-159">如果用户选择此选项，则反馈中心会在 HoloLens 设备上存储诊断信息的副本。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-159">If the user selects this option, the Feedback Hub stores a copy of the diagnostic information on the HoloLens device.</span></span> <span data-ttu-id="c0cd2-160">该信息仍可供用户（或使用该帐户的任何人登录到 HoloLens）访问。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-160">This information remains accessible to the user (or anyone that uses that account to sign in to HoloLens).</span></span> <span data-ttu-id="c0cd2-161">若要删除此信息，用户必须拥有设备**所有者**或设备的**管理员**权限。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-161">To delete this information, a user must have **Device owner** or **Admin** permissions on the device.</span></span> <span data-ttu-id="c0cd2-162">具有相应权限的用户可以登录到反馈中心，选择 "**设置**  >  "**查看诊断日志**，然后删除信息。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-162">A user who has the appropriate permissions can sign in to the Feedback Hub, select **Settings** > **View diagnostics logs**, and delete the information.</span></span>

## <span data-ttu-id="c0cd2-163">设置疑难解答</span><span class="sxs-lookup"><span data-stu-id="c0cd2-163">Settings Troubleshooter</span></span>

<span data-ttu-id="c0cd2-164">HoloLens 用户可以使用设备上的 "设置" 应用对问题进行故障排除和收集诊断信息。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-164">A HoloLens user can use the Settings app on the device to troubleshoot problems and collect diagnostic information.</span></span> <span data-ttu-id="c0cd2-165">为此，请执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="c0cd2-165">To do this, follow these steps:</span></span>

1. <span data-ttu-id="c0cd2-166">打开 "设置" 应用，然后选择 "**更新 & 安全**  >  **疑难解答**" 页面。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-166">Open the Settings app and select **Update & Security** > **Troubleshoot** page.</span></span>
1. <span data-ttu-id="c0cd2-167">选择相应的区域，然后选择 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-167">Select the appropriate area, and select **Start**.</span></span>
1. <span data-ttu-id="c0cd2-168">重现问题。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-168">Reproduce the issue.</span></span>
1. <span data-ttu-id="c0cd2-169">重现问题后，返回到 "设置"，然后选择 "**停止**"。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-169">After you reproduce the issue, return to Settings and then select **Stop**.</span></span>

### <span data-ttu-id="c0cd2-170">必备条件</span><span class="sxs-lookup"><span data-stu-id="c0cd2-170">Prerequisites</span></span>

- <span data-ttu-id="c0cd2-171">"设置" 应用已安装在设备上，可供用户使用。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-171">The Settings app is installed on the device and is available to the user.</span></span>

### <span data-ttu-id="c0cd2-172">数据位置、访问和保留</span><span class="sxs-lookup"><span data-stu-id="c0cd2-172">Data locations, access, and retention</span></span>

<span data-ttu-id="c0cd2-173">由于用户启动数据收集，因此用户隐式内容诊断信息的存储。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-173">Because the user starts the data collection, the user implicitly consents to the storage of the diagnostic information.</span></span> <span data-ttu-id="c0cd2-174">只有用户或与用户共享数据的任何人都可以访问数据。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-174">Only the user, or anyone with whom that the user shares the data, can access the data.</span></span>

<span data-ttu-id="c0cd2-175">诊断信息存储在设备上。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-175">The diagnostic information is stored on the device.</span></span> <span data-ttu-id="c0cd2-176">如果设备连接到用户的计算机，则该信息也驻留在计算机上的以下文件中：</span><span class="sxs-lookup"><span data-stu-id="c0cd2-176">If the device is connected to the user's computer, the information also resides on the computer in the following file:</span></span>

> <span data-ttu-id="c0cd2-177">此 PC\\ \<*HoloLens device name*> \\Internal Storage\\Documents\\Trace \<*ddmmyyhhmmss*></span><span class="sxs-lookup"><span data-stu-id="c0cd2-177">This PC\\\<*HoloLens device name*>\\Internal Storage\\Documents\\Trace\<*ddmmyyhhmmss*>.etl</span></span>

> [!NOTE]  
> <span data-ttu-id="c0cd2-178">在此文件路径和名称中， \<*HoloLens device name*> 表示 HoloLens 设备的名称，并 \<*ddmmyyhhmmss*> 表示文件的创建日期和时间。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-178">In this file path and name, \<*HoloLens device name*> represents the name of the HoloLens device, and \<*ddmmyyhhmmss*> represents the date and time that the file was created.</span></span>

<span data-ttu-id="c0cd2-179">诊断信息将保留在这些位置中，直到用户删除它。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-179">The diagnostic information remains in these locations until the user deletes it.</span></span>

## <span data-ttu-id="c0cd2-180">DiagnosticLog 云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="c0cd2-180">DiagnosticLog CSP</span></span>

<span data-ttu-id="c0cd2-181">在移动设备管理（MDM）环境中，IT 管理员可以使用[DiagnosticLog 配置服务提供程序（CSP）](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp)配置已注册的 HoloLens 设备上的诊断设置。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-181">In a Mobile Device Management (MDM) environment, the IT administrator can use the the [DiagnosticLog configuration service provider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/diagnosticlog-csp) to configure diagnostic settings on enrolled HoloLens devices.</span></span> <span data-ttu-id="c0cd2-182">IT 管理员可以配置这些设置以从注册的设备收集日志。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-182">The IT administrator can configure these settings to collect logs from enrolled devices.</span></span>

### <span data-ttu-id="c0cd2-183">必备条件</span><span class="sxs-lookup"><span data-stu-id="c0cd2-183">Prerequisites</span></span>

- <span data-ttu-id="c0cd2-184">设备已连接到网络。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-184">The device is connected to a network.</span></span>
- <span data-ttu-id="c0cd2-185">设备注册到支持 DiagnosticLog CSP 的 MDM 环境中。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-185">The device is enrolled in an MDM environment that supports the DiagnosticLog CSP.</span></span>

### <span data-ttu-id="c0cd2-186">数据位置、访问和保留</span><span class="sxs-lookup"><span data-stu-id="c0cd2-186">Data locations, access, and retention</span></span>

<span data-ttu-id="c0cd2-187">由于设备是托管环境的一部分，因此用户隐式内容对诊断信息的管理访问。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-187">Because the device is part of the managed environment, the user implicitly consents to administrative access to diagnostic information.</span></span>

<span data-ttu-id="c0cd2-188">IT 管理员使用 DiagnosticLog CSP 配置数据存储、保留和访问策略，包括管理以下各项的策略：</span><span class="sxs-lookup"><span data-stu-id="c0cd2-188">The IT administrator uses the DiagnosticLog CSP to configure the data storage, retention, and access policies, including the policies that govern the following:</span></span>

- <span data-ttu-id="c0cd2-189">存储诊断信息的云基础结构。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-189">The cloud infrastructure that stores the diagnostic information.</span></span>
- <span data-ttu-id="c0cd2-190">诊断信息的保留期。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-190">The retention period for the diagnostic information.</span></span>
- <span data-ttu-id="c0cd2-191">控制诊断信息访问权限的权限。</span><span class="sxs-lookup"><span data-stu-id="c0cd2-191">Permissions that control access to the diagnostic information.</span></span>

