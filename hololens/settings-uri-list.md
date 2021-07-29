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
ms.openlocfilehash: 454d79e8b719feb73d5a39280794dcd76f134952
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113639227"
---
# <a name="page-settings-visibility"></a>页面设置可见性

HoloLens 设备的可管理功能之一是使用[设置/PageVisibilityList 策略](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)来限制在“设置”应用中看到的页面。 PageVisibilityList 是一项策略，它允许 IT 管理员阻止查看或访问“系统设置”应用中的特定页面，或者对除指定页面之外的所有页面执行此操作。

> [!NOTE]
> 此功能仅在 HoloLens 2 设备的 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 或更高版本中提供。 请确保要使用此功能的设备已更新。


## <a name="examples"></a>示例
页面由已发布的 URI 的简缩版标识，即该 URI 减去“ms-settings:”前缀。

下面的示例阐释了仅允许访问“关于”和“蓝牙”页面的策略，该策略的 URI 分别为“network-wifi”和“bluetooth”：
- `showonly:network-wifi;network-proxy;bluetooth`

以下示例阐释了将隐藏“OS 重置”页面的策略：
- `hide:reset`


## <a name="deploying-this-policy-via-intune"></a>通过 Intune 部署此策略

这些是将提供给 Intune 的配置值：

- **名称：** 管理员首选的配置文件显示名称。
- **OMA-URI：** “设置”页面的完全限定 URI，包括其[作用域](/windows/client-management/mdm/policy-configuration-service-provider)。 本页面上的示例使用 `./Device` 作用域。
- **值：** 字符串值，指示是隐藏还是仅显示指定页面。 可能值为 `hide:<pagename>` 和 `showonly:<pagename>`。 
 
可以通过使用分号分隔多个页面来对其进行指定，以下是常用页面的列表。

1. 创建自定义策略。
1. 设置 OMA-URI 时，输入全作用域 URI。 例如：**`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. 选择数据选取时，请选择：字符串
1. 指定值时，使用上述指南。 例如 `showonly:network-wifi;network-proxy;bluetooth` 或 `hide:reset`  
> [!IMPORTANT]
> 请确保将自定义设备配置分配给设备所属的组。 如果不执行此步骤，则将推送但不应用策略。

有关 Intune 组和设备配置的详细信息，请参阅 [HoloLens MDM 配置](hololens-mdm-configure.md)。


## <a name="deploying-this-policy-via-a-provisioning-package"></a>使用预配程序包部署此策略

以下是将在 Windows 配置设计器中指定的配置值：

**值：** 字符串值，指示是隐藏还是仅显示指定页面。 可能值为 `hide:<pagename>` 和 `showonly:<pagename>`。 可以通过使用分号分隔多个页面来对其进行指定，以下是常用页面的列表。


1. 在 Windows 配置设计器中创建包时，导航到“策略”>“设置”>“PageVisibilityList”
1. 输入字符串：`showonly:network-wifi;network-proxy;bluetooth`
1. 导出预配包。
1. 将该包应用于你的设备。
有关如何创建和应用预配包的完整详细信息，请访问 [HoloLens 预配页面](hololens-provisioning.md)。


无论选择哪种方法，你的设备现在都应接收更改，并且将向用户显示以下“设置”应用。

![在“设置”应用中修改的使用时段的屏幕截图](images/hololens-page-visibility-list.jpg)

若要配置“设置”应用页面以显示或隐藏自己选择的页面，请查看 HoloLens 上可用的“设置 URI”。

## <a name="settings-uris"></a>设置 URI

HoloLens 设备和 Windows 10 设备在“设置”应用中的页面选择方面有所不同。 在此页面上，你将只能找到 HoloLens 上已有的设置。

### <a name="accounts"></a>帐户
| “设置”页面           | URI                                            |
|-------------------------|------------------------------------------------|
| 访问工作单位或学校 | `workplace`                         |
| Iris 注册       | `signinoptions-launchirisenrollment` |
| 登录选项         | ` signinoptions `                   |

### <a name="apps"></a>应用
| “设置”页面 | URI                          |
|---------------|------------------------------|
| 应用和功能 <sup>2</sup>     | `appsfeatures` <br> |
| 应用和功能 > 高级选项 <sup>2</sup>     | `appsfeatures-app` <br> |
| 应用和功能 > 脱机地图 <sup>2</sup>     | `maps-maps` <br> |
| 应用和功能 > 脱机地图 > 下载地图 <sup>2</sup>     | `maps-downloadmaps` <br> |

### <a name="devices"></a>设备
| “设置”页面 | URI                          |
|---------------|------------------------------|
| 蓝牙     | `bluetooth` <br> `connecteddevices` |
| 鼠标 <sup>2</sup>      | `mouse` <br>  |
| USB <sup>2</sup>      | `usb` <br>  |

### <a name="privacy"></a>隐私
| “设置”页面            | URI                                             |
|--------------------------|-------------------------------------------------|
| 帐户信息             | `privacy-accountinfo`              |
| 应用诊断        | `privacy-appdiagnostics`              |
| 后台应用        | `privacy-backgroundapps`              |
| 日历                 | `privacy-calendar`                    |
| 呼叫历史记录             | `privacy-callhistory`                 |
| 照相机                   | `privacy-webcam`                      |
| 联系人                 | `privacy-contacts`                    |
| 诊断和反馈 | `privacy-feedback`                    |
| 文档                | `privacy-documents`                   |
| 电子邮件                    | `privacy-email`                       |
| 文件系统              | `privacy-broadfilesystemaccess`       |
| 常规 <sup>2</sup>             | `privacy-general`       |
| 墨迹书写和键入个性化 <sup>2</sup>             | `privacy-speechtyping`       |
| 位置                 | `privacy-location`                    |
| 消息传递                | `privacy-messaging`                   |
| 麦克风               | `privacy-microphone`                  |
| 运动 <sup>2</sup>               | `privacy-motion`                  |
| 通知            | `privacy-notifications`               |
| 其他设备            | `privacy-customdevices`               |
| 图片                 | `privacy-pictures`                    |
| 无线电收发器                   | `privacy-radios`                      |
| 屏幕截图边框 <sup>2</sup>             | `privacy-graphicsCaptureWithoutBorder`       |
| 屏幕截图和应用 <sup>2</sup>             | `privacy-graphicsCaptureProgrammatic`       |
| 语音                   | `privacy-speech`                      |
| 任务                    | `privacy-tasks`                       |
| 用户移动           | `privacy-backgroundspatialperception` |
| 视频                   | `privacy-videos`                      |
| 语音激活       | `privacy-voiceactivation`             |

### <a name="network--internet"></a>网络和 Internet
| “设置”页面 | URI                              |
|---------------|----------------------------------|
| 飞行模式 <sup>2</sup> | `network-airplanemode`        |
| 代理 | `network-proxy`        |
| VPN   | `network-vpn`          |
| Wi-Fi  | `network-wifi`<br>`network-wifisettings`<br>`network-status`<br>`wifi-provisioning`    |



### <a name="system"></a>系统
| “设置”页面      | URI                                |
|--------------------|------------------------------------|
| 电池 <sup>2</sup>           | `batterysaver`<br>|
| 电池 <sup>2</sup>           | `batterysaver-settings`<br>|
| 颜色             | `colors`<br>`personalization-colors` |
| 全息影像 <sup>2</sup>  |  `holograms`  |
| 校准 <sup>2</sup> |  `calibration` |
| 通知和操作  | `notifications`          |
| 共享体验 | `crossdevice` 
| 声音 <sup>2</sup>           | `sound`<br>|
| 声音 > 应用音量和设备首选项 <sup>2</sup>           | `apps-volume`<br>|
| 声音 > 管理声音设备 <sup>2</sup>           | `sound-devices`<br>|
| 存储            | `storagesense`           |
| 存储 > 配置存储感知 <sup>2</sup>           | `storagepolicies`<br>|

### <a name="time--language"></a>时间和语言
| “设置”页面 | URI                                           |
|---------------|-----------------------------------------------|
| 日期和时间 <sup>2</sup> | `dateandtime`                  |
| 键盘 <sup>2</sup> | `keyboard`                  |
| 语言 <sup>2</sup> | `language`                  |
| 语言 <sup>2</sup> | `regionlanguage-languageoptions`                  |
| 语言      | `regionlanguage`<br>`regionlanguage-adddisplaylanguage`<br>`regionlanguage-setdisplaylanguage` |
| 区域        | `regionformatting`                  |

### <a name="update--security"></a>更新和安全
| “设置”页面                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| 高级选项                    | `windowsupdate-options`         |
| 重置和恢复 <sup>2</sup>      | `reset`         |
| Windows 预览体验计划               | `windowsinsider` <br>`windowsinsider-optin`          |
| Windows 更新                        | `windowsupdate`<br> `windowsupdate-activehours`  <br> `windowsupdate-history` <br> `windowsupdate-optionalupdates` <br><sup>1</sup>`windowsupdate-options`<br><sup>1</sup>`windowsupdate-restartoptions` |
| Windows 更新 - 检查更新 | `windowsupdate-action`          |


- <sup>1</sup> - 对于 Windows 全息版 21H1 之前的版本，以下两个 URI 实际上并不会将你转到“高级选项”或“选项”页；它们将仅阻止或显示主 Windows 更新页面。
  -  windowsupdate-options
  -  windowsupdate-restartoptions

- <sup>2</sup> - 适用于 Windows 全息版 21H1 或更高版本。


有关 Windows 10 设置 URI 的完整列表，请访问[启动设置](/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)文档。
