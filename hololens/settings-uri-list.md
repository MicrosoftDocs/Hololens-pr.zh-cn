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
ms.openlocfilehash: d28994d911532a940d82756aa45609571ee80ac3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924326"
---
# <a name="page-settings-visibility"></a><span data-ttu-id="aa2fe-104">页面设置可见性</span><span class="sxs-lookup"><span data-stu-id="aa2fe-104">Page Settings Visibility</span></span>

<span data-ttu-id="aa2fe-105">HoloLens 设备的可管理功能之一是使用[设置/PageVisibilityList 策略](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)来限制在“设置”应用中看到的页面。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-105">One of the manageable features for HoloLens devices is using the [Settings/PageVisibilityList policy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) to restrict the pages seen within the Settings app.</span></span> <span data-ttu-id="aa2fe-106">PageVisibilityList 是一项策略，它允许 IT 管理员阻止查看或访问“系统设置”应用中的特定页面，或者对除指定页面之外的所有页面执行此操作。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-106">PageVisibilityList is a policy that allows IT Admins to either prevent specific pages in the System Settings app from being visible or accessible, or to do so for all pages except those specified.</span></span>

> [!NOTE]
> <span data-ttu-id="aa2fe-107">此功能仅在 HoloLens 2 设备的 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 或更高版本中提供。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-107">This feature is only avalible in [Windows Holographic, version 20H2](hololens-release-notes.md#windows-holographic-version-20h2) or higher for HoloLens 2 devices.</span></span> <span data-ttu-id="aa2fe-108">请确保要使用此功能的设备已更新。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-108">Please ensure devices you intend to use this for are updated.</span></span>

<span data-ttu-id="aa2fe-109">下面的示例阐释了仅允许访问“关于”和“蓝牙”页面的策略，该策略的 URI 分别为“ms-settings:network-wifi”和“ms-settings:bluetooth”：</span><span class="sxs-lookup"><span data-stu-id="aa2fe-109">The following example illustrates a policy that would allow access only to the about and bluetooth pages, which have URI "ms-settings:network-wifi" and "ms-settings:bluetooth" respectively:</span></span>
- `showonly:network-wifi;network-proxy;bluetooth`

<span data-ttu-id="aa2fe-110">若要通过预配包对此进行设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="aa2fe-110">To set this via a Provisioning Package:</span></span>

1. <span data-ttu-id="aa2fe-111">在 Windows 配置设计器中创建包时，导航到“策略”>“设置”>“PageVisibilityList”</span><span class="sxs-lookup"><span data-stu-id="aa2fe-111">While creating your package in Windows Configuration Designer navigate to **Policies > Settings > PageVisibilityList**</span></span>
1. <span data-ttu-id="aa2fe-112">输入字符串：`showonly:network-wifi;network-proxy;bluetooth`</span><span class="sxs-lookup"><span data-stu-id="aa2fe-112">Enter the string: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="aa2fe-113">导出预配包。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-113">Export your Provisioning Package.</span></span>
1. <span data-ttu-id="aa2fe-114">将该包应用于你的设备。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-114">Apply the package to your device.</span></span>
<span data-ttu-id="aa2fe-115">有关如何创建和应用预配包的完整详细信息，请访问[此页](hololens-provisioning.md)。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-115">For full details on how to create and apply a provisioning package visit [this page](hololens-provisioning.md).</span></span>

<span data-ttu-id="aa2fe-116">可使用 OMA-URI 通过 Intune 执行此操作：</span><span class="sxs-lookup"><span data-stu-id="aa2fe-116">This can be done via Intune using OMA-URI:</span></span>

1. <span data-ttu-id="aa2fe-117">创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-117">Create a **Custom policy**.</span></span>
1. <span data-ttu-id="aa2fe-118">设置 OMA-URI 时，请使用字符串：`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`</span><span class="sxs-lookup"><span data-stu-id="aa2fe-118">When setting the OMA-URI use the string: **`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**</span></span>
1. <span data-ttu-id="aa2fe-119">选择数据选取时，请选择：字符串</span><span class="sxs-lookup"><span data-stu-id="aa2fe-119">When selecting the data pick choose: **String**</span></span>
1. <span data-ttu-id="aa2fe-120">键入值时，请使用：`showonly:network-wifi;network-proxy;bluetooth`</span><span class="sxs-lookup"><span data-stu-id="aa2fe-120">When typing the value use: **`showonly:network-wifi;network-proxy;bluetooth`**</span></span>
1. <span data-ttu-id="aa2fe-121">请确保将自定义设备配置分配给设备所属的组。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-121">Make sure to assign the custom device configuration to a group the device is intended to be in.</span></span>

<span data-ttu-id="aa2fe-122">有关 Intune 组和设备配置的详细信息，请参阅 [HoloLens MDM 配置](hololens-mdm-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-122">See [HoloLens MDM configuration](hololens-mdm-configure.md) for more information on Intune groups and device configurations.</span></span>

<span data-ttu-id="aa2fe-123">无论选择哪种方法，你的设备现在都应接收更改，并且将向用户显示以下“设置”应用。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-123">Regardless of method chosen your device should now receive the changes and users will be presented with the following Settings App.</span></span>

![在“设置”应用中修改的使用时段的屏幕截图](images/hololens-page-visibility-list.jpg)

<span data-ttu-id="aa2fe-125">若要配置“设置”应用页面以显示或隐藏自己选择的页面，请查看 HoloLens 上可用的“设置 URI”。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-125">To configure the Settings app pages to show or hide your own selection of pages, take a look at the Settings URIs available on HoloLens.</span></span>

## <a name="settings-uris"></a><span data-ttu-id="aa2fe-126">设置 URI</span><span class="sxs-lookup"><span data-stu-id="aa2fe-126">Settings URIs</span></span>

<span data-ttu-id="aa2fe-127">HoloLens 设备和 Windows 10 设备在“设置”应用中的页面选择方面有所不同。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-127">HoloLens devices and Windows 10 devices have a different selection of pages within the Settings app.</span></span> <span data-ttu-id="aa2fe-128">在此页面上，你将只能找到 HoloLens 上已有的设置。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-128">On this page, you will find only the settings that exist on HoloLens.</span></span>

### <a name="accounts"></a><span data-ttu-id="aa2fe-129">帐户</span><span class="sxs-lookup"><span data-stu-id="aa2fe-129">Accounts</span></span>
| <span data-ttu-id="aa2fe-130">“设置”页面</span><span class="sxs-lookup"><span data-stu-id="aa2fe-130">Settings page</span></span>           | <span data-ttu-id="aa2fe-131">URI</span><span class="sxs-lookup"><span data-stu-id="aa2fe-131">URI</span></span>                                            |
|-------------------------|------------------------------------------------|
| <span data-ttu-id="aa2fe-132">访问工作单位或学校</span><span class="sxs-lookup"><span data-stu-id="aa2fe-132">Access work or school</span></span> | `ms-settings:workplace`                         |
| <span data-ttu-id="aa2fe-133">Iris 注册</span><span class="sxs-lookup"><span data-stu-id="aa2fe-133">Iris Enrollment</span></span>       | `ms-settings:signinoptions-launchirisenrollment` |
| <span data-ttu-id="aa2fe-134">登录选项</span><span class="sxs-lookup"><span data-stu-id="aa2fe-134">Sign In Options</span></span>         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a><span data-ttu-id="aa2fe-135">应用</span><span class="sxs-lookup"><span data-stu-id="aa2fe-135">Apps</span></span>
| <span data-ttu-id="aa2fe-136">“设置”页面</span><span class="sxs-lookup"><span data-stu-id="aa2fe-136">Settings page</span></span> | <span data-ttu-id="aa2fe-137">URI</span><span class="sxs-lookup"><span data-stu-id="aa2fe-137">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="aa2fe-138">应用和功能<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-138">Apps & features<sup>2</sup></span></span>     | `ms-settings:appsfeatures` <br> |
| <span data-ttu-id="aa2fe-139">应用和功能 > 高级选项 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-139">Apps & features > Advanced Options <sup>2</sup></span></span>     | `ms-settings::appsfeatures-app` <br> |
| <span data-ttu-id="aa2fe-140">应用和功能 > 脱机地图 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-140">Apps & features > Offline Maps <sup>2</sup></span></span>     | `ms-settings:maps-maps` <br> |
| <span data-ttu-id="aa2fe-141">应用和功能 > 脱机地图 > 下载地图 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-141">Apps & features > Offline Maps > Download maps <sup>2</sup></span></span>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a><span data-ttu-id="aa2fe-142">设备</span><span class="sxs-lookup"><span data-stu-id="aa2fe-142">Devices</span></span>
| <span data-ttu-id="aa2fe-143">“设置”页面</span><span class="sxs-lookup"><span data-stu-id="aa2fe-143">Settings page</span></span> | <span data-ttu-id="aa2fe-144">URI</span><span class="sxs-lookup"><span data-stu-id="aa2fe-144">URI</span></span>                          |
|---------------|------------------------------|
| <span data-ttu-id="aa2fe-145">蓝牙</span><span class="sxs-lookup"><span data-stu-id="aa2fe-145">Bluetooth</span></span>     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| <span data-ttu-id="aa2fe-146">鼠标 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-146">Mouse <sup>2</sup></span></span>      | `ms-settings:mouse` <br>  |
| <span data-ttu-id="aa2fe-147">USB <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-147">USB <sup>2</sup></span></span>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a><span data-ttu-id="aa2fe-148">隐私</span><span class="sxs-lookup"><span data-stu-id="aa2fe-148">Privacy</span></span>
| <span data-ttu-id="aa2fe-149">“设置”页面</span><span class="sxs-lookup"><span data-stu-id="aa2fe-149">Settings page</span></span>            | <span data-ttu-id="aa2fe-150">URI</span><span class="sxs-lookup"><span data-stu-id="aa2fe-150">URI</span></span>                                             |
|--------------------------|-------------------------------------------------|
| <span data-ttu-id="aa2fe-151">帐户信息</span><span class="sxs-lookup"><span data-stu-id="aa2fe-151">Account Info</span></span>             | `ms-settings:privacy-accountinfo`              |
| <span data-ttu-id="aa2fe-152">应用诊断</span><span class="sxs-lookup"><span data-stu-id="aa2fe-152">App Diagnostics</span></span>        | `ms-settings:privacy-appdiagnostics`              |
| <span data-ttu-id="aa2fe-153">后台应用</span><span class="sxs-lookup"><span data-stu-id="aa2fe-153">Background Apps</span></span>        | `ms-settings:privacy-backgroundapps`              |
| <span data-ttu-id="aa2fe-154">日历</span><span class="sxs-lookup"><span data-stu-id="aa2fe-154">Calendar</span></span>                 | `ms-settings:privacy-calendar`                    |
| <span data-ttu-id="aa2fe-155">呼叫历史记录</span><span class="sxs-lookup"><span data-stu-id="aa2fe-155">Call History</span></span>             | `ms-settings:privacy-callhistory`                 |
| <span data-ttu-id="aa2fe-156">照相机</span><span class="sxs-lookup"><span data-stu-id="aa2fe-156">Camera</span></span>                   | `ms-settings:privacy-webcam`                      |
| <span data-ttu-id="aa2fe-157">联系人</span><span class="sxs-lookup"><span data-stu-id="aa2fe-157">Contacts</span></span>                 | `ms-settings:privacy-contacts`                    |
| <span data-ttu-id="aa2fe-158">诊断和反馈</span><span class="sxs-lookup"><span data-stu-id="aa2fe-158">Diagnostics & Feedback</span></span> | `ms-settings:privacy-feedback`                    |
| <span data-ttu-id="aa2fe-159">文档</span><span class="sxs-lookup"><span data-stu-id="aa2fe-159">Documents</span></span>                | `ms-settings:privacy-documents`                   |
| <span data-ttu-id="aa2fe-160">电子邮件</span><span class="sxs-lookup"><span data-stu-id="aa2fe-160">Email</span></span>                    | `ms-settings:privacy-email`                       |
| <span data-ttu-id="aa2fe-161">文件系统</span><span class="sxs-lookup"><span data-stu-id="aa2fe-161">File system</span></span>              | `ms-settings:privacy-broadfilesystemaccess`       |
| <span data-ttu-id="aa2fe-162">常规 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-162">General <sup>2</sup></span></span>             | `ms-settings:privacy-general`       |
| <span data-ttu-id="aa2fe-163">墨迹书写和键入个性化 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-163">Ink & typing personalization <sup>2</sup></span></span>             | `ms-settings:privacy-speechtyping`       |
| <span data-ttu-id="aa2fe-164">位置</span><span class="sxs-lookup"><span data-stu-id="aa2fe-164">Location</span></span>                 | `ms-settings:privacy-location`                    |
| <span data-ttu-id="aa2fe-165">消息传递</span><span class="sxs-lookup"><span data-stu-id="aa2fe-165">Messaging</span></span>                | `ms-settings:privacy-messaging`                   |
| <span data-ttu-id="aa2fe-166">麦克风</span><span class="sxs-lookup"><span data-stu-id="aa2fe-166">Microphone</span></span>               | `ms-settings:privacy-microphone`                  |
| <span data-ttu-id="aa2fe-167">运动 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-167">Motion <sup>2</sup></span></span>               | `ms-settings:privacy-motion`                  |
| <span data-ttu-id="aa2fe-168">通知</span><span class="sxs-lookup"><span data-stu-id="aa2fe-168">Notifications</span></span>            | `ms-settings:privacy-notifications`               |
| <span data-ttu-id="aa2fe-169">其他设备</span><span class="sxs-lookup"><span data-stu-id="aa2fe-169">Other devices</span></span>            | `ms-settings:privacy-customdevices`               |
| <span data-ttu-id="aa2fe-170">图片</span><span class="sxs-lookup"><span data-stu-id="aa2fe-170">Pictures</span></span>                 | `ms-settings:privacy-pictures`                    |
| <span data-ttu-id="aa2fe-171">无线电收发器</span><span class="sxs-lookup"><span data-stu-id="aa2fe-171">Radios</span></span>                   | `ms-settings:privacy-radios`                      |
| <span data-ttu-id="aa2fe-172">屏幕截图边框 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-172">Screenshot borders <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| <span data-ttu-id="aa2fe-173">屏幕截图和应用 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-173">Screenshots and apps <sup>2</sup></span></span>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| <span data-ttu-id="aa2fe-174">语音</span><span class="sxs-lookup"><span data-stu-id="aa2fe-174">Speech</span></span>                   | `ms-settings:privacy-speech`                      |
| <span data-ttu-id="aa2fe-175">任务</span><span class="sxs-lookup"><span data-stu-id="aa2fe-175">Tasks</span></span>                    | `ms-settings:privacy-tasks`                       |
| <span data-ttu-id="aa2fe-176">用户移动</span><span class="sxs-lookup"><span data-stu-id="aa2fe-176">User movements</span></span>           | `ms-settings:privacy-backgroundspatialperception` |
| <span data-ttu-id="aa2fe-177">视频</span><span class="sxs-lookup"><span data-stu-id="aa2fe-177">Videos</span></span>                   | `ms-settings:privacy-videos`                      |
| <span data-ttu-id="aa2fe-178">语音激活</span><span class="sxs-lookup"><span data-stu-id="aa2fe-178">Voice Activation</span></span>       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a><span data-ttu-id="aa2fe-179">网络和 Internet</span><span class="sxs-lookup"><span data-stu-id="aa2fe-179">Network & Internet</span></span>
| <span data-ttu-id="aa2fe-180">“设置”页面</span><span class="sxs-lookup"><span data-stu-id="aa2fe-180">Settings page</span></span> | <span data-ttu-id="aa2fe-181">URI</span><span class="sxs-lookup"><span data-stu-id="aa2fe-181">URI</span></span>                              |
|---------------|----------------------------------|
| <span data-ttu-id="aa2fe-182">飞行模式 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-182">Airplane Mode <sup>2</sup></span></span> | `ms-settings:network-airplanemode`        |
| <span data-ttu-id="aa2fe-183">代理</span><span class="sxs-lookup"><span data-stu-id="aa2fe-183">Proxy</span></span> | `ms-settings:network-proxy`        |
| <span data-ttu-id="aa2fe-184">VPN</span><span class="sxs-lookup"><span data-stu-id="aa2fe-184">VPN</span></span>   | `ms-settings:network-vpn`          |
| <span data-ttu-id="aa2fe-185">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="aa2fe-185">Wi-Fi</span></span>  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a><span data-ttu-id="aa2fe-186">系统</span><span class="sxs-lookup"><span data-stu-id="aa2fe-186">System</span></span>
| <span data-ttu-id="aa2fe-187">“设置”页面</span><span class="sxs-lookup"><span data-stu-id="aa2fe-187">Settings page</span></span>      | <span data-ttu-id="aa2fe-188">URI</span><span class="sxs-lookup"><span data-stu-id="aa2fe-188">URI</span></span>                                |
|--------------------|------------------------------------|
| <span data-ttu-id="aa2fe-189">电池 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-189">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver`<br>|
| <span data-ttu-id="aa2fe-190">电池 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-190">Battery <sup>2</sup></span></span>           | `ms-settings:batterysaver-settings`<br>|
| <span data-ttu-id="aa2fe-191">颜色</span><span class="sxs-lookup"><span data-stu-id="aa2fe-191">Colors</span></span>             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| <span data-ttu-id="aa2fe-192">全息影像 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-192">Holograms <sup>2</sup></span></span>  |  `ms-settings:holograms`  |
| <span data-ttu-id="aa2fe-193">校准 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-193">Calibration <sup>2</sup></span></span> |  `ms-settings:calibration` |
| <span data-ttu-id="aa2fe-194">通知和操作</span><span class="sxs-lookup"><span data-stu-id="aa2fe-194">Notifications & actions</span></span>  | `ms-settings:notifications`          |
| <span data-ttu-id="aa2fe-195">共享体验</span><span class="sxs-lookup"><span data-stu-id="aa2fe-195">Shared Experiences</span></span> | `ms-settings:crossdevice` 
| <span data-ttu-id="aa2fe-196">声音 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-196">Sound <sup>2</sup></span></span>           | `ms-settings:sound`<br>|
| <span data-ttu-id="aa2fe-197">声音 > 应用音量和设备首选项 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-197">Sound > App volume and device preference <sup>2</sup></span></span>           | `ms-settings:apps-volume`<br>|
| <span data-ttu-id="aa2fe-198">声音 > 管理声音设备 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-198">Sound > Manage sound devices <sup>2</sup></span></span>           | `ms-settings:sound-devices`<br>|
| <span data-ttu-id="aa2fe-199">存储</span><span class="sxs-lookup"><span data-stu-id="aa2fe-199">Storage</span></span>            | `ms-settings:storagesense`           |
| <span data-ttu-id="aa2fe-200">存储 > 配置存储感知 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-200">Storage > Configure Storage Sense <sup>2</sup></span></span>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a><span data-ttu-id="aa2fe-201">时间和语言</span><span class="sxs-lookup"><span data-stu-id="aa2fe-201">Time & Language</span></span>
| <span data-ttu-id="aa2fe-202">“设置”页面</span><span class="sxs-lookup"><span data-stu-id="aa2fe-202">Settings page</span></span> | <span data-ttu-id="aa2fe-203">URI</span><span class="sxs-lookup"><span data-stu-id="aa2fe-203">URI</span></span>                                           |
|---------------|-----------------------------------------------|
| <span data-ttu-id="aa2fe-204">日期和时间 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-204">Date & time <sup>2</sup></span></span> | `ms-settings:dateandtime`                  |
| <span data-ttu-id="aa2fe-205">键盘 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-205">Keyboard <sup>2</sup></span></span> | `ms-settings:keyboard`                  |
| <span data-ttu-id="aa2fe-206">语言 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-206">Language <sup>2</sup></span></span> | `ms-settings:language`                  |
| <span data-ttu-id="aa2fe-207">语言 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-207">Language <sup>2</sup></span></span> | `ms-settings:regionlanguage-languageoptions`                  |
| <span data-ttu-id="aa2fe-208">语言</span><span class="sxs-lookup"><span data-stu-id="aa2fe-208">Language</span></span>      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| <span data-ttu-id="aa2fe-209">区域</span><span class="sxs-lookup"><span data-stu-id="aa2fe-209">Region</span></span>        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a><span data-ttu-id="aa2fe-210">更新和安全</span><span class="sxs-lookup"><span data-stu-id="aa2fe-210">Update & Security</span></span>
| <span data-ttu-id="aa2fe-211">“设置”页面</span><span class="sxs-lookup"><span data-stu-id="aa2fe-211">Settings page</span></span>                         | <span data-ttu-id="aa2fe-212">URI</span><span class="sxs-lookup"><span data-stu-id="aa2fe-212">URI</span></span>                                       |
|---------------------------------------|-------------------------------------------|
| <span data-ttu-id="aa2fe-213">高级选项</span><span class="sxs-lookup"><span data-stu-id="aa2fe-213">Advanced Options</span></span>                    | `ms-settings:windowsupdate-options`         |
| <span data-ttu-id="aa2fe-214">重置和恢复 <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="aa2fe-214">Reset & Recovery <sup>2</sup></span></span>      | `ms-settings:reset`         |
| <span data-ttu-id="aa2fe-215">Windows 预览体验计划</span><span class="sxs-lookup"><span data-stu-id="aa2fe-215">Windows Insider Program</span></span>               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| <span data-ttu-id="aa2fe-216">Windows 更新</span><span class="sxs-lookup"><span data-stu-id="aa2fe-216">Windows Update</span></span>                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><span data-ttu-id="aa2fe-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span><span class="sxs-lookup"><span data-stu-id="aa2fe-217"><sup>1</sup>`ms-settings:windowsupdate-options`</span></span><br><span data-ttu-id="aa2fe-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span><span class="sxs-lookup"><span data-stu-id="aa2fe-218"><sup>1</sup>`ms-settings:windowsupdate-restartoptions`</span></span> |
| <span data-ttu-id="aa2fe-219">Windows 更新 - 检查更新</span><span class="sxs-lookup"><span data-stu-id="aa2fe-219">Windows Update - Checks for updates</span></span> | `ms-settings:windowsupdate-action`          |


- <span data-ttu-id="aa2fe-220"><sup>1</sup> - 对于 Windows 全息版 21H1 之前的版本，以下两个 URI 实际上并不会将你转到“高级选项”或“选项”页；它们将仅阻止或显示主 Windows 更新页面。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-220"><sup>1</sup> - For versions prior to Windows Holographic, version 21H1, the following two URIs do not actually take you to the **Advanced options** or **Options** pages; they will only block or show the main Windows Update page.</span></span>
  -  <span data-ttu-id="aa2fe-221">ms-settings:windowsupdate-options</span><span class="sxs-lookup"><span data-stu-id="aa2fe-221">ms-settings:windowsupdate-options</span></span>
  -  <span data-ttu-id="aa2fe-222">ms-settings:windowsupdate-restartoptions</span><span class="sxs-lookup"><span data-stu-id="aa2fe-222">ms-settings:windowsupdate-restartoptions</span></span>

- <span data-ttu-id="aa2fe-223"><sup>2</sup> - 适用于 Windows 全息版 21H1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-223"><sup>2</sup> - Available in Windows Holographic 21H1 or higher.</span></span>


<span data-ttu-id="aa2fe-224">有关 Windows 10 设置 URI 的完整列表，请访问[启动设置](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)文档。</span><span class="sxs-lookup"><span data-stu-id="aa2fe-224">For a full list of Windows 10 Settings URIs, please visit the [launch settings](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference) documentation.</span></span>
