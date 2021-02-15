---
title: 页面设置可见性
description: 及时获取 HoloLens 混合现实设备上针对 PageVisibilityList 和指南的受支持 URI 列表。
author: evmill
ms.author: v-evmill
ms.date: 10/13/2020
ms.topic: article
keywords: hololens, hololens 2, 分配的访问权限, 展台, 设置页面
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: f004f39f4b69748e8c36ad93111f4423d14c40f3
ms.sourcegitcommit: 23ee06b659d7a51f3000d386c8f67cbf212d5aa4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327386"
---
# <span data-ttu-id="27186-104">页面设置可见性</span><span class="sxs-lookup"><span data-stu-id="27186-104">Page Settings Visibility</span></span>

<span data-ttu-id="27186-105">HoloLens 设备的其中一项易管理的功能是使用 [Settings/PageVisibilityList 策略](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)限制“设置”应用中显示的页面。</span><span class="sxs-lookup"><span data-stu-id="27186-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="27186-106">PageVisibilityList 是一项策略，它允许 IT 管理员阻止查看或访问“系统设置”应用中的特定页面，或者对除指定页面之外的所有页面执行此操作。</span><span class="sxs-lookup"><span data-stu-id="27186-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="27186-107">此功能仅在适用于 HoloLens 2 设备的 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中可用。</span><span class="sxs-lookup"><span data-stu-id="27186-107">This feature is only avalible in [Windows Holographic, verison 20H2](hololens-release-notes.md#windows-holographic-version-20h2) for HoloLens 2 devices.</span></span> <span data-ttu-id="27186-108">请确保要使用此功能的设备已更新。</span><span class="sxs-lookup"><span data-stu-id="27186-108">Please ensure devices you intend to use this for are updated.</span></span>

> [!NOTE]
> <span data-ttu-id="27186-109">即将添加超过 20 种新的 SettingsURI。</span><span class="sxs-lookup"><span data-stu-id="27186-109">20+ new SettingsURIs are being added soon.</span></span> <span data-ttu-id="27186-110">如果有兴趣在 [HoloLens 预览体验计划](hololens-insider.md) 内部版本上预览此设置，请查看 [Windows 预览体验计划页面 - 页面设置可见性的新 SettingsURI](hololens-insider.md#new-settingsuris-for-page-settings-visibility)。</span><span class="sxs-lookup"><span data-stu-id="27186-110">Please view [the Windows Insider page - New SettingsURIs for Page Settings Visibility](hololens-insider.md#new-settingsuris-for-page-settings-visibility) if you are interesting in previewing this setting on a [HoloLens Insider](hololens-insider.md) build.</span></span>

<span data-ttu-id="27186-111">下面的示例阐释了仅允许访问 "关于" 和 "蓝牙" 页面的策略，该策略的 URI 为 "ms-settings： network/wifi" 和 "ms settings：蓝牙"。 以下示例说明了一个策略，该策略仅允许访问 about 和 bluetooth 页面，它们分别具有URI“ms-settings:network-wifi”和“ms-settings:bluetooth”：</span><span class="sxs-lookup"><span data-stu-id="27186-111">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="27186-112">若要通过预配包对此进行设置：</span><span class="sxs-lookup"><span data-stu-id="27186-112">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="27186-113">在 Windows 配置设计器中创建包时，导航到“**策略”>“设置”>“PageVisibilityList**”</span><span class="sxs-lookup"><span data-stu-id="27186-113">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="27186-114">输入字符串：**`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="27186-114">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="27186-115">导出预配包。</span><span class="sxs-lookup"><span data-stu-id="27186-115">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="27186-116">将该包应用于你的设备。</span><span class="sxs-lookup"><span data-stu-id="27186-116">Apply the package to your device.</span></span>
<span data-ttu-id="27186-117">有关如何创建和应用预配包的完整详细信息，请访问 [此页面](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="27186-117">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="27186-118">可使用 OMA-URI 通过 Intune 执行此操作：</span><span class="sxs-lookup"><span data-stu-id="27186-118">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="27186-119">创建 **自定义策略**。</span><span class="sxs-lookup"><span data-stu-id="27186-119">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="27186-120">设置 OMA-URI 时，请使用字符串：**`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span><span class="sxs-lookup"><span data-stu-id="27186-120">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="27186-121">选择数据选取时，请选择：**字符串**</span><span class="sxs-lookup"><span data-stu-id="27186-121">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="27186-122">键入值时，请使用：**`showonly:network-wifi;network-proxy;bluetooth`**</span><span class="sxs-lookup"><span data-stu-id="27186-122">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="27186-123">请确保将自定义设备配置分配给设备所属的组。</span><span class="sxs-lookup"><span data-stu-id="27186-123">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="27186-124">有关 Intune 组和设备配置的详细信息，请参阅 [HoloLens MDM 配置](hololens-mdm-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="27186-124">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="27186-125">无论选择哪种方法，你的设备现在都应接收更改，并且将向用户显示以下“设置”应用。</span><span class="sxs-lookup"><span data-stu-id="27186-125">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![在“设置”应用中修改的使用时段的屏幕截图](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="27186-127">若要配置“设置”应用页面以显示或隐藏自己选择的页面，请查看 HoloLens 上可用的“设置 URI”。</span><span class="sxs-lookup"><span data-stu-id="27186-127">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <span data-ttu-id="27186-128">设置 URI</span><span class="sxs-lookup"><span data-stu-id="27186-128">Settings URIs</span></span>

<span data-ttu-id="27186-129">HoloLens 设备和 Windows 10 设备在“设置”应用中的页面选择方面有所不同。</span><span class="sxs-lookup"><span data-stu-id="27186-129">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="27186-130">在此页面上，你将只能找到 HoloLens 上已有的设置。</span><span class="sxs-lookup"><span data-stu-id="27186-130">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <span data-ttu-id="27186-131">帐户</span><span class="sxs-lookup"><span data-stu-id="27186-131">Accounts</span></span>
| <span data-ttu-id="27186-132">设置页面</span><span class="sxs-lookup"><span data-stu-id="27186-132">Settings page</span></span>           | <span data-ttu-id="27186-133">URI</span><span class="sxs-lookup"><span data-stu-id="27186-133">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="27186-134">登录选项</span><span class="sxs-lookup"><span data-stu-id="27186-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |
| <span data-ttu-id="27186-135">Iris 注册</span><span class="sxs-lookup"><span data-stu-id="27186-135">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="27186-136">访问工作或学校帐户</span><span class="sxs-lookup"><span data-stu-id="27186-136">Access work or school</span></span> | `ms-settings:workplace`                         |

### <span data-ttu-id="27186-137">设备</span><span class="sxs-lookup"><span data-stu-id="27186-137">Devices</span></span>
| <span data-ttu-id="27186-138">设置页面</span><span class="sxs-lookup"><span data-stu-id="27186-138">Settings page</span></span> | <span data-ttu-id="27186-139">URI</span><span class="sxs-lookup"><span data-stu-id="27186-139">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="27186-140">蓝牙</span><span class="sxs-lookup"><span data-stu-id="27186-140">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |

### <span data-ttu-id="27186-141">隐私</span><span class="sxs-lookup"><span data-stu-id="27186-141">Privacy</span></span>
| <span data-ttu-id="27186-142">设置页面</span><span class="sxs-lookup"><span data-stu-id="27186-142">Settings page</span></span>            | <span data-ttu-id="27186-143">URI</span><span class="sxs-lookup"><span data-stu-id="27186-143">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="27186-144">帐户信息</span><span class="sxs-lookup"><span data-stu-id="27186-144">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="27186-145">应用诊断</span><span class="sxs-lookup"><span data-stu-id="27186-145">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="27186-146">后台应用</span><span class="sxs-lookup"><span data-stu-id="27186-146">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="27186-147">用户移动</span><span class="sxs-lookup"><span data-stu-id="27186-147">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="27186-148">文件系统</span><span class="sxs-lookup"><span data-stu-id="27186-148">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="27186-149">日历</span><span class="sxs-lookup"><span data-stu-id="27186-149">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="27186-150">呼叫历史记录</span><span class="sxs-lookup"><span data-stu-id="27186-150">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="27186-151">联系人</span><span class="sxs-lookup"><span data-stu-id="27186-151">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="27186-152">其他设备</span><span class="sxs-lookup"><span data-stu-id="27186-152">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="27186-153">文档</span><span class="sxs-lookup"><span data-stu-id="27186-153">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="27186-154">电子邮件</span><span class="sxs-lookup"><span data-stu-id="27186-154">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="27186-155">诊断和反馈</span><span class="sxs-lookup"><span data-stu-id="27186-155">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="27186-156">位置</span><span class="sxs-lookup"><span data-stu-id="27186-156">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="27186-157">消息</span><span class="sxs-lookup"><span data-stu-id="27186-157">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="27186-158">麦克风</span><span class="sxs-lookup"><span data-stu-id="27186-158">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="27186-159">通知</span><span class="sxs-lookup"><span data-stu-id="27186-159">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="27186-160">图片</span><span class="sxs-lookup"><span data-stu-id="27186-160">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="27186-161">无线电收发器</span><span class="sxs-lookup"><span data-stu-id="27186-161">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="27186-162">语音</span><span class="sxs-lookup"><span data-stu-id="27186-162">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="27186-163">任务</span><span class="sxs-lookup"><span data-stu-id="27186-163">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="27186-164">视频</span><span class="sxs-lookup"><span data-stu-id="27186-164">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="27186-165">语音激活</span><span class="sxs-lookup"><span data-stu-id="27186-165">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |
| <span data-ttu-id="27186-166">摄像头</span><span class="sxs-lookup"><span data-stu-id="27186-166">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |

### <span data-ttu-id="27186-167">网络和 Internet</span><span class="sxs-lookup"><span data-stu-id="27186-167">Network & Internet</span></span>
| <span data-ttu-id="27186-168">设置页面</span><span class="sxs-lookup"><span data-stu-id="27186-168">Settings page</span></span> | <span data-ttu-id="27186-169">URI</span><span class="sxs-lookup"><span data-stu-id="27186-169">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="27186-170">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="27186-170">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |
| <span data-ttu-id="27186-171">VPN</span><span class="sxs-lookup"><span data-stu-id="27186-171">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="27186-172">代理</span><span class="sxs-lookup"><span data-stu-id="27186-172">Proxy</span></span> | `ms-settings:network-proxy`        |

### <span data-ttu-id="27186-173">系统</span><span class="sxs-lookup"><span data-stu-id="27186-173">System</span></span>
| <span data-ttu-id="27186-174">设置页面</span><span class="sxs-lookup"><span data-stu-id="27186-174">Settings page</span></span>      | <span data-ttu-id="27186-175">URI</span><span class="sxs-lookup"><span data-stu-id="27186-175">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="27186-176">共享体验</span><span class="sxs-lookup"><span data-stu-id="27186-176">Shared Experiences</span></span> | `ms-settings:crossdevice`            |
| <span data-ttu-id="27186-177">颜色</span><span class="sxs-lookup"><span data-stu-id="27186-177">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="27186-178">通知和操作</span><span class="sxs-lookup"><span data-stu-id="27186-178">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="27186-179">存储</span><span class="sxs-lookup"><span data-stu-id="27186-179">Storage</span></span>            | `ms-settings:storagesense`           |

### <span data-ttu-id="27186-180">时间和语言</span><span class="sxs-lookup"><span data-stu-id="27186-180">Time & Language</span></span>
| <span data-ttu-id="27186-181">设置页面</span><span class="sxs-lookup"><span data-stu-id="27186-181">Settings page</span></span> | <span data-ttu-id="27186-182">URI</span><span class="sxs-lookup"><span data-stu-id="27186-182">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="27186-183">区域</span><span class="sxs-lookup"><span data-stu-id="27186-183">Region</span></span>        | `ms-settings:regionformatting`                  |
| <span data-ttu-id="27186-184">语言</span><span class="sxs-lookup"><span data-stu-id="27186-184">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |

### <span data-ttu-id="27186-185">更新和安全</span><span class="sxs-lookup"><span data-stu-id="27186-185">Update & Security</span></span>
| <span data-ttu-id="27186-186">设置页面</span><span class="sxs-lookup"><span data-stu-id="27186-186">Settings page</span></span>                         | <span data-ttu-id="27186-187">URI</span><span class="sxs-lookup"><span data-stu-id="27186-187">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="27186-188">Windows 预览体验计划</span><span class="sxs-lookup"><span data-stu-id="27186-188">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="27186-189">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="27186-189">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup><span data-ttu-id="27186-190">1</span><span class="sxs-lookup"><span data-stu-id="27186-190">1</span></span></sup>`ms-settings:windowsupdate-options`<br><sup><span data-ttu-id="27186-191">1</span><span class="sxs-lookup"><span data-stu-id="27186-191">1</span></span></sup>`ms-settings:windowsupdate-restartoptions` |
| <span data-ttu-id="27186-192">Windows 更新 - 检查更新</span><span class="sxs-lookup"><span data-stu-id="27186-192">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |
| <span data-ttu-id="27186-193">高级选项</span><span class="sxs-lookup"><span data-stu-id="27186-193">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |

>  <sup><span data-ttu-id="27186-194">1</sup> 以下两个 URI 实际上并不会将您转到**高级选项**或**选项页面**；它们将仅阻止或显示主 Windows 更新页面。</span><span class="sxs-lookup"><span data-stu-id="27186-194">1</sup> The following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
> - <span data-ttu-id="27186-195">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="27186-195">ms-settings:windowsupdate-options</span></span>
> - <span data-ttu-id="27186-196">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="27186-196">ms-settings:windowsupdate-restartoptions</span></span> 

<span data-ttu-id="27186-197">有关 Windows 10 设置 URI 的完整列表，请访问[启动设置](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)文档。</span><span class="sxs-lookup"><span data-stu-id="27186-197">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
