---
title: 适用于 Microsoft HoloLens 的 Insider Preview
description: 了解如何开始体验内部版本，并为 HoloLens 的下一个主要操作系统更新提供有价值的反馈。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 87b606e634d4035da02802ddd1a8e1a980f1f1d6
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636075"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="ae8ad-103">适用于 Microsoft HoloLens 的 Insider Preview</span><span class="sxs-lookup"><span data-stu-id="ae8ad-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="ae8ad-104">欢迎使用 HoloLens 的最新 Insider preview 版本！</span><span class="sxs-lookup"><span data-stu-id="ae8ad-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="ae8ad-105">这是一种非常简单的[入门](hololens-insider.md#start-receiving-insider-builds)方法，为 HoloLens 的下一个主要操作系统更新提供有价值的反馈。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="ae8ad-106">Windows内幕发行说明</span><span class="sxs-lookup"><span data-stu-id="ae8ad-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="ae8ad-107">我们非常高兴地开始试验新功能，以便 Windows 的预览体验。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="ae8ad-108">新版本将会试验到适用于最新更新的开发和测试渠道。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="ae8ad-109">我们将继续更新此页面，因为我们将更多的功能和更新添加到 Windows 有问必答版本。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="ae8ad-110">令人兴奋并准备好将这些更新混合到您的现实中。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="ae8ad-111">功能</span><span class="sxs-lookup"><span data-stu-id="ae8ad-111">Feature</span></span>                 | <span data-ttu-id="ae8ad-112">说明</span><span class="sxs-lookup"><span data-stu-id="ae8ad-112">Description</span></span>                | <span data-ttu-id="ae8ad-113">用户或方案</span><span class="sxs-lookup"><span data-stu-id="ae8ad-113">User or Scenario</span></span> | <span data-ttu-id="ae8ad-114">引入的生成</span><span class="sxs-lookup"><span data-stu-id="ae8ad-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| [<span data-ttu-id="ae8ad-115">reporting HoloLens 详细信息的 CSP 更改</span><span class="sxs-lookup"><span data-stu-id="ae8ad-115">CSP changes for reporting HoloLens details</span></span>](#csp-changes-for-reporting-hololens-details) | <span data-ttu-id="ae8ad-116">用于查询数据的新 Csp</span><span class="sxs-lookup"><span data-stu-id="ae8ad-116">New CSPs for to query data</span></span> | <span data-ttu-id="ae8ad-117">IT 管理员</span><span class="sxs-lookup"><span data-stu-id="ae8ad-117">IT Admins</span></span>    | <span data-ttu-id="ae8ad-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="ae8ad-118">20348.1403</span></span>                 |
| [<span data-ttu-id="ae8ad-119">由 CSP 控制的自动登录策略</span><span class="sxs-lookup"><span data-stu-id="ae8ad-119">Auto login policy controlled by CSP</span></span>](#auto-login-policy-controlled-by-csp) | <span data-ttu-id="ae8ad-120">用于自动登录帐户</span><span class="sxs-lookup"><span data-stu-id="ae8ad-120">Used to log in an account automatically</span></span> | <span data-ttu-id="ae8ad-121">IT 管理员</span><span class="sxs-lookup"><span data-stu-id="ae8ad-121">IT Admins</span></span> | <span data-ttu-id="ae8ad-122">20348.1405</span><span class="sxs-lookup"><span data-stu-id="ae8ad-122">20348.1405</span></span> |
| [<span data-ttu-id="ae8ad-123">证书管理器的 PFX 文件支持</span><span class="sxs-lookup"><span data-stu-id="ae8ad-123">PFX file support for Certificate Manager</span></span>](#pfx-file-support-for-certificate-manager) | <span data-ttu-id="ae8ad-124">通过设置 UI 添加 PFX 证书</span><span class="sxs-lookup"><span data-stu-id="ae8ad-124">Add PFX certs via Settings UI</span></span> | <span data-ttu-id="ae8ad-125">最终用户</span><span class="sxs-lookup"><span data-stu-id="ae8ad-125">End User</span></span> | <span data-ttu-id="ae8ad-126">20348.1405</span><span class="sxs-lookup"><span data-stu-id="ae8ad-126">20348.1405</span></span> |
| [<span data-ttu-id="ae8ad-127">查看 HoloLens 上设置的高级诊断报告</span><span class="sxs-lookup"><span data-stu-id="ae8ad-127">View advanced diagnostic report in Settings on HoloLens</span></span>](#view-advanced-diagnostic-report-in-settings-on-hololens) | <span data-ttu-id="ae8ad-128">查看设备上的 MDM 诊断日志</span><span class="sxs-lookup"><span data-stu-id="ae8ad-128">View MDM diagnostic logs on device</span></span> | <span data-ttu-id="ae8ad-129">疑难解答</span><span class="sxs-lookup"><span data-stu-id="ae8ad-129">Troubleshooting</span></span> | <span data-ttu-id="ae8ad-130">20348.1405</span><span class="sxs-lookup"><span data-stu-id="ae8ad-130">20348.1405</span></span> |
| [<span data-ttu-id="ae8ad-131">脱机诊断通知</span><span class="sxs-lookup"><span data-stu-id="ae8ad-131">Offline Diagnostics notifications</span></span>](#offline-diagnostics-notifications) | <span data-ttu-id="ae8ad-132">日志收集的视听反馈</span><span class="sxs-lookup"><span data-stu-id="ae8ad-132">Audiovisual feedback for log collection</span></span> | <span data-ttu-id="ae8ad-133">疑难解答</span><span class="sxs-lookup"><span data-stu-id="ae8ad-133">Troubleshooting</span></span> | <span data-ttu-id="ae8ad-134">20348.1405</span><span class="sxs-lookup"><span data-stu-id="ae8ad-134">20348.1405</span></span> |


### <a name="csp-changes-for-reporting-hololens-details"></a><span data-ttu-id="ae8ad-135">reporting HoloLens 详细信息的 CSP 更改</span><span class="sxs-lookup"><span data-stu-id="ae8ad-135">CSP changes for reporting HoloLens details</span></span>

- <span data-ttu-id="ae8ad-136">在 Windows 有问必答版本20348.1403 中引入</span><span class="sxs-lookup"><span data-stu-id="ae8ad-136">Introduced in Windows Insider build, 20348.1403</span></span>

<span data-ttu-id="ae8ad-137">下面的 csp 已经用新方法进行了更新，以从 HoloLens 设备报告信息。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-137">The following CSPs have been updated with new ways to report information from your HoloLens devices.</span></span>

#### <a name="devdetail-csp---free-storage"></a><span data-ttu-id="ae8ad-138">DevDetail CSP-免费存储</span><span class="sxs-lookup"><span data-stu-id="ae8ad-138">DevDetail CSP - Free Storage</span></span>

<span data-ttu-id="ae8ad-139">DevDetail CSP 现在还报告 HoloLens 设备上的可用存储空间。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-139">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="ae8ad-140">这应该与设置应用的存储页面中显示的值大致匹配。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-140">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="ae8ad-141">下面是包含此信息的特定节点。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-141">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="ae8ad-142">/DevDetail/Ext/Microsoft/FreeStorage (仅获取操作) </span><span class="sxs-lookup"><span data-stu-id="ae8ad-142">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp---ssid-and-bssid"></a><span data-ttu-id="ae8ad-143">DeviceStatus CSP-SSID 和 BSSID</span><span class="sxs-lookup"><span data-stu-id="ae8ad-143">DeviceStatus CSP - SSID and BSSID</span></span>

<span data-ttu-id="ae8ad-144">DeviceStatus CSP 现在还会报告与 HoloLens 主动连接 Wi-Fi 网络的 SSID 和 BSSID。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-144">DeviceStatus CSP now also reports SSID and BSSID of Wi-Fi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="ae8ad-145">下面是包含此信息的特定节点。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-145">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="ae8ad-146">/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span><span class="sxs-lookup"><span data-stu-id="ae8ad-146">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="ae8ad-147">/Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span><span class="sxs-lookup"><span data-stu-id="ae8ad-147">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="ae8ad-148">适用于 MDM 供应商的 syncml blob (的示例) 查询 NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="ae8ad-148">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="auto-login-policy-controlled-by-csp"></a><span data-ttu-id="ae8ad-149">由 CSP 控制的自动登录策略</span><span class="sxs-lookup"><span data-stu-id="ae8ad-149">Auto login policy controlled by CSP</span></span>

<span data-ttu-id="ae8ad-150">这个新的 AutoLogonUser 策略控制用户是否将自动登录。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-150">This new AutoLogonUser policy controls whether a user will be automatically logged on.</span></span> <span data-ttu-id="ae8ad-151">某些客户需要设置绑定到标识的设备，但不需要任何登录体验。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-151">Some customers want to set up devices that are tied to an identity but don't want any sign-in experience.</span></span> <span data-ttu-id="ae8ad-152">Imagine 立即提取设备并使用远程协助。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-152">Imagine picking up a device and using remote assist immediately.</span></span> <span data-ttu-id="ae8ad-153">或者有一个好处，即能够快速分发 HoloLens 设备，并使最终用户能够快速登录。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-153">Or have a benefit of being able to rapidly  distribute HoloLens devices and enable their end users to expedite login.</span></span>

<span data-ttu-id="ae8ad-154">如果策略设置为非空值，则它指定自动登录用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-154">When the policy is set to a non-empty value, it specifies the email address of the auto-logon user.</span></span> <span data-ttu-id="ae8ad-155">指定的用户必须至少登录到设备一次，才能启用自动登录。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-155">The specified user must logon to the device at least once to enable auto-logon.</span></span>

<span data-ttu-id="ae8ad-156">新策略 `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` 字符串值的 oma-uri</span><span class="sxs-lookup"><span data-stu-id="ae8ad-156">The OMA-URI of new policy `./Device/Vendor/MSFT/Policy/Config/MixedReality/AutoLogonUser` String value</span></span>

- <span data-ttu-id="ae8ad-157">具有相同电子邮件地址的用户将启用自动登录。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-157">User with the same email address will have auto logon enabled.</span></span>

<span data-ttu-id="ae8ad-158">在配置了此策略的设备上，策略中指定的用户至少需要登录一次。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-158">On a device where this policy is configured, the user specified in the policy will need to logon at least once.</span></span> <span data-ttu-id="ae8ad-159">第一次登录后，随后的设备重新启动将使指定的用户自动登录。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-159">Subsequent reboots of the device after the first logon will have the specified user automatically logged on.</span></span> <span data-ttu-id="ae8ad-160">仅支持单个自动登录用户。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-160">Only a single auto-logon user is supported.</span></span> <span data-ttu-id="ae8ad-161">启用后，自动登录的用户将不能手动注销。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-161">Once enabled, the automatically logged on user will not be able to log out manually.</span></span> <span data-ttu-id="ae8ad-162">若要以其他用户身份登录，必须先禁用策略。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-162">To logon as a different user, the policy must first be disabled.</span></span>

> [!NOTE]
> - <span data-ttu-id="ae8ad-163">某些事件（例如，主要 OS 更新）可能需要指定的用户重新登录到设备，才能恢复自动登录行为。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-163">Some events such as major OS updates may require the specified user to logon to the device again to resume auto-logon behavior.</span></span> 
> - <span data-ttu-id="ae8ad-164">仅 MSA 和 AAD 用户支持自动登录。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-164">Auto-logon is only supported for MSA and AAD users.</span></span>

### <a name="pfx-file-support-for-certificate-manager"></a><span data-ttu-id="ae8ad-165">证书管理器的 PFX 文件支持</span><span class="sxs-lookup"><span data-stu-id="ae8ad-165">PFX file support for Certificate Manager</span></span>

<span data-ttu-id="ae8ad-166">在 Windows 有问必答版本20348.1405 中引入。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-166">Introduced in Windows Insider build 20348.1405.</span></span> <span data-ttu-id="ae8ad-167">我们已向 [证书管理器添加了对证书管理器](certificate-manager.md) 的支持，以便现在使用 .pfx 证书。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-167">We’ve added support to the [Certificate Manager](certificate-manager.md) to now use .pfx certificates.</span></span> <span data-ttu-id="ae8ad-168">当用户导航到 **设置**  >  **更新 & 安全**  >  **证书**，并选择 "**安装证书**" 时，UI 现在支持 .pfx 证书文件。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-168">When users navigate to **Settings** > **Update & Security** > **Certificates**, and select **Install a certificate** the UI now supports .pfx certificate file.</span></span>
<span data-ttu-id="ae8ad-169">用户可以将包含私钥的 .pfx 证书导入到用户存储或计算机存储。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-169">Users can import .pfx certificate, with private key, to user store or machine store.</span></span>

### <a name="view-advanced-diagnostic-report-in-settings-on-hololens"></a><span data-ttu-id="ae8ad-170">查看 HoloLens 上设置的高级诊断报告</span><span class="sxs-lookup"><span data-stu-id="ae8ad-170">View advanced diagnostic report in Settings on HoloLens</span></span>

<span data-ttu-id="ae8ad-171">对于托管设备，在对行为进行故障排除时，确认应用了预期的策略配置是一个重要的步骤。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-171">For managed devices when troubleshooting behavior, confirming that an expected policy configuration is applied is an important step.</span></span> <span data-ttu-id="ae8ad-172">之前，此新功能必须通过 mdm 或附近的设备完成，然后再导出通过 **设置**  ->  **帐户**  >  **访问工作或学校** 收集的 mdm 诊断日志，并选择 "**导出管理日志** 并在附近的 PC 上查看"。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-172">Previously to this new feature, this had to be done off device via MDM or near the device after exporting MDM diagnostic logs gathered via **Settings** -> **Accounts** > **Access work or school**, and select **Export your management logs** and viewed on a nearby PC.</span></span>

<span data-ttu-id="ae8ad-173">现在可以使用 Edge 浏览器在设备上查看 MDM 诊断。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-173">Now the MDM Diagnostics can be viewed on device using the Edge browser.</span></span> <span data-ttu-id="ae8ad-174">若要更轻松地查看 MDM 诊断报告，请导航到 "访问" 工作或学校页面，然后选择 " **查看高级诊断报告**"。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-174">To more easily view the MDM Diagnostic report navigate to the Access work or school page, and select **View advanced diagnostic report**.</span></span> <span data-ttu-id="ae8ad-175">这会在新的边缘窗口中生成并打开报表。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-175">This will generate and open the report in a new Edge window.</span></span>

![在设置应用中查看高级诊断报告。](./images/view-advanced-diagnostic-report.jpg)

### <a name="offline-diagnostics-notifications"></a><span data-ttu-id="ae8ad-177">脱机诊断通知</span><span class="sxs-lookup"><span data-stu-id="ae8ad-177">Offline Diagnostics notifications</span></span>

<span data-ttu-id="ae8ad-178">此更新适用于称为 [脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics)的现有功能。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-178">This an update for an existing feature called [Offline Diagnostics](hololens-diagnostic-logs.md#offline-diagnostics).</span></span> <span data-ttu-id="ae8ad-179">以前，用户已触发诊断收集或已完成，没有明确的指示器。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-179">Previously, there was no clear indicator to users that they had triggered diagnostic collection or it had completed.</span></span>
<span data-ttu-id="ae8ad-180">现已添加到 Windows 内部版本中，对于脱机诊断，有两种形式的视听反馈。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-180">Now added in Windows Insider builds, there are two forms of audiovisual feedback for Offline Diagnostics.</span></span> <span data-ttu-id="ae8ad-181">当收集开始和完成时，将显示第一个 toast 通知。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-181">The first being toasts notifications displayed for both when collection starts and completes.</span></span> <span data-ttu-id="ae8ad-182">当用户登录并具有视觉对象时，将显示这些用户。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-182">These will be displayed when the user is logged in and has visuals.</span></span>

![用于收集日志的 Toast。](./images/logcollection1.jpg)

![记录收集完成时 Toast。](./images/logcollection2.jpg)
 
<span data-ttu-id="ae8ad-185">由于用户经常会使用脱机诊断作为回退日志收集机制来访问显示器、无法登录或仍处于 OOBE 状态，因此在收集日志时也会播放音频提示。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-185">Because users often use Offline Diagnostics as a fallback log gathering mechanism for when they don’t have access to a display, can’t log-in or are still in OOBE there will also be an audio cue played when logs are gathered.</span></span> <span data-ttu-id="ae8ad-186">除了 toast 通知外，还会播放此声音。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-186">This sound will be played in addition to the toast notification.</span></span>

<span data-ttu-id="ae8ad-187">这项新功能将在设备更新时启用，不需要启用或管理。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-187">This new feature will be enabled when your device updates, and doesn’t need to be enabled or managed.</span></span> <span data-ttu-id="ae8ad-188">如果无法显示或听不到此新反馈，则仍将生成脱机诊断。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-188">In any event that this new feedback cannot be displayed or heard, Offline Diagnostics will still be generated.</span></span>

<span data-ttu-id="ae8ad-189">我们希望这种新的视听反馈增加，更易于收集诊断数据，并能更快地解决问题。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-189">We hope with this newer addition of audiovisual feedback it is easier to gather diagnostic data, and more quickly be able to troubleshoot your problems.</span></span>



### <a name="fixes-and-improvements"></a><span data-ttu-id="ae8ad-190">修复和改进：</span><span class="sxs-lookup"><span data-stu-id="ae8ad-190">Fixes and improvements:</span></span>

- <span data-ttu-id="ae8ad-191">修复了在 [未提示下载锁定文件的情况下设备门户的已知问题。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="ae8ad-191">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="ae8ad-192">修复了 [包含文件上传和下载超时的设备门户的已知问题。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="ae8ad-192">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>


## <a name="start-receiving-insider-builds"></a><span data-ttu-id="ae8ad-193">开始接收 Insider 内部版本</span><span class="sxs-lookup"><span data-stu-id="ae8ad-193">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="ae8ad-194">如果你最近没有更新，请重新启动你的设备以更新状态并获取最新版本。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-194">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="ae8ad-195">"重新启动设备" 语音命令正常工作。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-195">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="ae8ad-196">你还可以在设置/Windows 预览体验计划 "中选择" 重新启动 "按钮。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-196">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="ae8ad-197">我们在你可能遇到的后端上遇到了一个错误，这会使你返回到 "跟踪"。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-197">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="ae8ad-198">在 HoloLens 2 设备上，转到 **设置**  >  **更新 & 安全**  >  **Windows 预览体验计划**，并选择 "**入门**"。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-198">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="ae8ad-199">将用于注册的帐户链接到 Windows 有问必答。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-199">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="ae8ad-200">Windows 有问必答现在正在移至频道。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-200">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="ae8ad-201">快速 **通道** 将成为 **开发通道**，慢速通道 **将成为** Beta 版频道通道，发布预览通道将成为 **发布预览通道**。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-201">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="ae8ad-202">该映射如下所示：</span><span class="sxs-lookup"><span data-stu-id="ae8ad-202">Here is what that mapping looks like:</span></span>

![Windows预览体验成员频道说明](images/WindowsInsiderChannels.png)

<span data-ttu-id="ae8ad-204">有关详细信息，请参阅博客[上的预览Windows](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)预览体验Windows介绍。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-204">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="ae8ad-205">然后 **，选择**"Windows开发"，选择要接收 **开发** 通道还是Beta 版频道版本，并查看计划条款。 </span><span class="sxs-lookup"><span data-stu-id="ae8ad-205">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="ae8ad-206">选择 **">立即重启** "以完成操作。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-206">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="ae8ad-207">重启设备后，转到"更新设置 >"&**安全性>检查更新** 以获取最新生成。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-207">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="ae8ad-208">更新错误0x80070490问题</span><span class="sxs-lookup"><span data-stu-id="ae8ad-208">Update error 0x80070490 work-around</span></span>

<span data-ttu-id="ae8ad-209">如果在开发或 Beta 0x80070490更新时遇到更新错误，请尝试以下短期工作。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-209">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="ae8ad-210">这涉及到移动预览体验成员通道、选取更新，然后将 Insider 通道移回。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-210">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>

#### <a name="stage-one---release-preview"></a><span data-ttu-id="ae8ad-211">第一阶段 - 发布预览版</span><span class="sxs-lookup"><span data-stu-id="ae8ad-211">Stage one - Release Preview</span></span>

1.  <span data-ttu-id="ae8ad-212">设置"更新&安全性"，Windows 会员计划，选择"**发布预览通道"。**</span><span class="sxs-lookup"><span data-stu-id="ae8ad-212">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>

2.  <span data-ttu-id="ae8ad-213">设置、更新&安全性、Windows更新、**检查更新**。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-213">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="ae8ad-214">更新后，继续进入阶段 2。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-214">After the update, continue on to Stage two.</span></span>

#### <a name="stage-two---dev-channel"></a><span data-ttu-id="ae8ad-215">阶段 2 - 开发通道</span><span class="sxs-lookup"><span data-stu-id="ae8ad-215">Stage two - Dev Channel</span></span>

1. <span data-ttu-id="ae8ad-216">设置"更新&安全性"，选择Windows 会员计划"**开发通道"。**</span><span class="sxs-lookup"><span data-stu-id="ae8ad-216">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>

2. <span data-ttu-id="ae8ad-217">设置、更新&安全性、Windows更新、**检查更新**。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-217">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>

## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="ae8ad-218">FFU 下载和闪存说明</span><span class="sxs-lookup"><span data-stu-id="ae8ad-218">FFU download and flash directions</span></span>

<span data-ttu-id="ae8ad-219">若要使用已签署航班的 ffu 进行测试，首先需要先对设备进行飞行解锁，然后刷出已签署航班的 ffu。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-219">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>

1. <span data-ttu-id="ae8ad-220">在电脑上：</span><span class="sxs-lookup"><span data-stu-id="ae8ad-220">On PC:</span></span>
    1. <span data-ttu-id="ae8ad-221">从 将 ffu 下载到电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-221">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="ae8ad-222">从 (安装 ARC) 高级恢复助手 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) Microsoft Store：。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-222">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="ae8ad-223">在HoloLens - 航班解锁：打开 **设置**  >  **Update & Security**  >  **Windows 会员计划，** 然后注册、重启设备。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-223">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="ae8ad-224">Flash FFU - 现在可以使用 ARC 刷出航班签名的 FFU。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-224">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="ae8ad-225">提供反馈并报告问题</span><span class="sxs-lookup"><span data-stu-id="ae8ad-225">Provide feedback and report issues</span></span>

<span data-ttu-id="ae8ad-226">请使用[反馈中心应用](hololens-feedback.md)HoloLens提供反馈并报告问题。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-226">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="ae8ad-227">使用 反馈中心可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-227">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="ae8ad-228">应该以相同的方式报告HoloLens日文版本的问题。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-228">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="ae8ad-229">请务必接受提示，询问你是否希望反馈中心 Documents 文件夹， (系统提示时选择"是) 。 </span><span class="sxs-lookup"><span data-stu-id="ae8ad-229">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <a name="note-for-developers"></a><span data-ttu-id="ae8ad-230">开发人员说明</span><span class="sxs-lookup"><span data-stu-id="ae8ad-230">Note for developers</span></span>

<span data-ttu-id="ae8ad-231">欢迎并鼓励你尝试使用预览体验成员内部版本开发HoloLens。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-231">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="ae8ad-232">请查看开发人员[HoloLens文档](https://developer.microsoft.com/windows/mixed-reality/development)开始。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-232">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="ae8ad-233">这些相同的说明与预览体验成员内部版本HoloLens。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-233">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="ae8ad-234">可以使用已用于开发Visual Studio Unity 和 HoloLens版本。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-234">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="ae8ad-235">停止接收预览体验内部版本</span><span class="sxs-lookup"><span data-stu-id="ae8ad-235">Stop receiving Insider builds</span></span>

<span data-ttu-id="ae8ad-236">如果不再想要接收 Windows Holographic 的预览体验内部版本，可以在 HoloLens 运行生产内部版本时选择退出，或者可以使用高级恢复助手将设备恢复到[](hololens-recovery.md)Windows Holographic 的非 Insider 版本。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-236">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="ae8ad-237">存在一个已知问题：在手动重新安装新的预览版本后，从 Insider Preview 版本取消注册的用户将遇到蓝屏。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-237">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="ae8ad-238">之后，他们必须手动恢复其设备。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-238">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="ae8ad-239">有关是否受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-239">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>

<span data-ttu-id="ae8ad-240">若要验证HoloLens是否正在运行生产内部版本：</span><span class="sxs-lookup"><span data-stu-id="ae8ad-240">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="ae8ad-241">转到 **"设置 >系统>关于**"，并找到生成号。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-241">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="ae8ad-242">[有关生产内部版本号，请参阅发行说明](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-242">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="ae8ad-243">选择退出预览体验内部版本：</span><span class="sxs-lookup"><span data-stu-id="ae8ad-243">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="ae8ad-244">在运行HoloLens生成时，转到"设置 >更新&**安全**> Windows 会员计划，然后选择"停止 **预览体验成员生成"。**</span><span class="sxs-lookup"><span data-stu-id="ae8ad-244">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="ae8ad-245">按照说明选择退出设备。</span><span class="sxs-lookup"><span data-stu-id="ae8ad-245">Follow the instructions to opt out your device.</span></span>
