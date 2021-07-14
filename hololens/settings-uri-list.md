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
# <a name="page-settings-visibility"></a>页面设置可见性

HoloLens 设备的可管理功能之一是使用[设置/PageVisibilityList 策略](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)来限制在“设置”应用中看到的页面。 PageVisibilityList 是一项策略，它允许 IT 管理员阻止查看或访问“系统设置”应用中的特定页面，或者对除指定页面之外的所有页面执行此操作。

> [!NOTE]
> 此功能仅在 HoloLens 2 设备的 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 或更高版本中提供。 请确保要使用此功能的设备已更新。

下面的示例阐释了仅允许访问“关于”和“蓝牙”页面的策略，该策略的 URI 分别为“ms-settings:network-wifi”和“ms-settings:bluetooth”：
- `showonly:network-wifi;network-proxy;bluetooth`

若要通过预配包对此进行设置，请执行以下操作：

1. 在 Windows 配置设计器中创建包时，导航到“策略”>“设置”>“PageVisibilityList”
1. 输入字符串：`showonly:network-wifi;network-proxy;bluetooth`
1. 导出预配包。
1. 将该包应用于你的设备。
有关如何创建和应用预配包的完整详细信息，请访问[此页](hololens-provisioning.md)。

可使用 OMA-URI 通过 Intune 执行此操作：

1. 创建自定义策略。
1. 设置 OMA-URI 时，请使用字符串：`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`
1. 选择数据选取时，请选择：字符串
1. 键入值时，请使用：`showonly:network-wifi;network-proxy;bluetooth`
1. 请确保将自定义设备配置分配给设备所属的组。

有关 Intune 组和设备配置的详细信息，请参阅 [HoloLens MDM 配置](hololens-mdm-configure.md)。

无论选择哪种方法，你的设备现在都应接收更改，并且将向用户显示以下“设置”应用。

![在“设置”应用中修改的使用时段的屏幕截图](images/hololens-page-visibility-list.jpg)

若要配置“设置”应用页面以显示或隐藏自己选择的页面，请查看 HoloLens 上可用的“设置 URI”。

## <a name="settings-uris"></a>设置 URI

HoloLens 设备和 Windows 10 设备在“设置”应用中的页面选择方面有所不同。 在此页面上，你将只能找到 HoloLens 上已有的设置。

### <a name="accounts"></a>帐户
| “设置”页面           | URI                                            |
|-------------------------|------------------------------------------------|
| 访问工作单位或学校 | `ms-settings:workplace`                         |
| Iris 注册       | `ms-settings:signinoptions-launchirisenrollment` |
| 登录选项         | ` ms-settings:signinoptions `                   |

### <a name="apps"></a>应用
| “设置”页面 | URI                          |
|---------------|------------------------------|
| 应用和功能<sup>2</sup>     | `ms-settings:appsfeatures` <br> |
| 应用和功能 > 高级选项 <sup>2</sup>     | `ms-settings::appsfeatures-app` <br> |
| 应用和功能 > 脱机地图 <sup>2</sup>     | `ms-settings:maps-maps` <br> |
| 应用和功能 > 脱机地图 > 下载地图 <sup>2</sup>     | `ms-settings:maps-downloadmaps` <br> |

### <a name="devices"></a>设备
| “设置”页面 | URI                          |
|---------------|------------------------------|
| 蓝牙     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |
| 鼠标 <sup>2</sup>      | `ms-settings:mouse` <br>  |
| USB <sup>2</sup>      | `ms-settings:usb` <br>  |

### <a name="privacy"></a>隐私
| “设置”页面            | URI                                             |
|--------------------------|-------------------------------------------------|
| 帐户信息             | `ms-settings:privacy-accountinfo`              |
| 应用诊断        | `ms-settings:privacy-appdiagnostics`              |
| 后台应用        | `ms-settings:privacy-backgroundapps`              |
| 日历                 | `ms-settings:privacy-calendar`                    |
| 呼叫历史记录             | `ms-settings:privacy-callhistory`                 |
| 照相机                   | `ms-settings:privacy-webcam`                      |
| 联系人                 | `ms-settings:privacy-contacts`                    |
| 诊断和反馈 | `ms-settings:privacy-feedback`                    |
| 文档                | `ms-settings:privacy-documents`                   |
| 电子邮件                    | `ms-settings:privacy-email`                       |
| 文件系统              | `ms-settings:privacy-broadfilesystemaccess`       |
| 常规 <sup>2</sup>             | `ms-settings:privacy-general`       |
| 墨迹书写和键入个性化 <sup>2</sup>             | `ms-settings:privacy-speechtyping`       |
| 位置                 | `ms-settings:privacy-location`                    |
| 消息传递                | `ms-settings:privacy-messaging`                   |
| 麦克风               | `ms-settings:privacy-microphone`                  |
| 运动 <sup>2</sup>               | `ms-settings:privacy-motion`                  |
| 通知            | `ms-settings:privacy-notifications`               |
| 其他设备            | `ms-settings:privacy-customdevices`               |
| 图片                 | `ms-settings:privacy-pictures`                    |
| 无线电收发器                   | `ms-settings:privacy-radios`                      |
| 屏幕截图边框 <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureWithoutBorder`       |
| 屏幕截图和应用 <sup>2</sup>             | `ms-settings:privacy-graphicsCaptureProgrammatic`       |
| 语音                   | `ms-settings:privacy-speech`                      |
| 任务                    | `ms-settings:privacy-tasks`                       |
| 用户移动           | `ms-settings:privacy-backgroundspatialperception` |
| 视频                   | `ms-settings:privacy-videos`                      |
| 语音激活       | `ms-settings:privacy-voiceactivation`             |

### <a name="network--internet"></a>网络和 Internet
| “设置”页面 | URI                              |
|---------------|----------------------------------|
| 飞行模式 <sup>2</sup> | `ms-settings:network-airplanemode`        |
| 代理 | `ms-settings:network-proxy`        |
| VPN   | `ms-settings:network-vpn`          |
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |



### <a name="system"></a>系统
| “设置”页面      | URI                                |
|--------------------|------------------------------------|
| 电池 <sup>2</sup>           | `ms-settings:batterysaver`<br>|
| 电池 <sup>2</sup>           | `ms-settings:batterysaver-settings`<br>|
| 颜色             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| 全息影像 <sup>2</sup>  |  `ms-settings:holograms`  |
| 校准 <sup>2</sup> |  `ms-settings:calibration` |
| 通知和操作  | `ms-settings:notifications`          |
| 共享体验 | `ms-settings:crossdevice` 
| 声音 <sup>2</sup>           | `ms-settings:sound`<br>|
| 声音 > 应用音量和设备首选项 <sup>2</sup>           | `ms-settings:apps-volume`<br>|
| 声音 > 管理声音设备 <sup>2</sup>           | `ms-settings:sound-devices`<br>|
| 存储            | `ms-settings:storagesense`           |
| 存储 > 配置存储感知 <sup>2</sup>           | `ms-settings:storagepolicies`<br>|

### <a name="time--language"></a>时间和语言
| “设置”页面 | URI                                           |
|---------------|-----------------------------------------------|
| 日期和时间 <sup>2</sup> | `ms-settings:dateandtime`                  |
| 键盘 <sup>2</sup> | `ms-settings:keyboard`                  |
| 语言 <sup>2</sup> | `ms-settings:language`                  |
| 语言 <sup>2</sup> | `ms-settings:regionlanguage-languageoptions`                  |
| 语言      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |
| 区域        | `ms-settings:regionformatting`                  |

### <a name="update--security"></a>更新和安全
| “设置”页面                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| 高级选项                    | `ms-settings:windowsupdate-options`         |
| 重置和恢复 <sup>2</sup>      | `ms-settings:reset`         |
| Windows 预览体验计划               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows 更新                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows 更新 - 检查更新 | `ms-settings:windowsupdate-action`          |


- <sup>1</sup> - 对于 Windows 全息版 21H1 之前的版本，以下两个 URI 实际上并不会将你转到“高级选项”或“选项”页；它们将仅阻止或显示主 Windows 更新页面。
  -  ms-settings:windowsupdate-options
  -  ms-settings:windowsupdate-restartoptions

- <sup>2</sup> - 适用于 Windows 全息版 21H1 或更高版本。


有关 Windows 10 设置 URI 的完整列表，请访问[启动设置](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)文档。
