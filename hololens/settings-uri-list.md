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
# 页面设置可见性

HoloLens 设备的其中一项易管理的功能是使用 [Settings/PageVisibilityList 策略](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)限制“设置”应用中显示的页面。 PageVisibilityList 是一项策略，它允许 IT 管理员阻止查看或访问“系统设置”应用中的特定页面，或者对除指定页面之外的所有页面执行此操作。

> [!NOTE]
> 此功能仅在适用于 HoloLens 2 设备的 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中可用。 请确保要使用此功能的设备已更新。

> [!NOTE]
> 即将添加超过 20 种新的 SettingsURI。 如果有兴趣在 [HoloLens 预览体验计划](hololens-insider.md) 内部版本上预览此设置，请查看 [Windows 预览体验计划页面 - 页面设置可见性的新 SettingsURI](hololens-insider.md#new-settingsuris-for-page-settings-visibility)。

下面的示例阐释了仅允许访问 "关于" 和 "蓝牙" 页面的策略，该策略的 URI 为 "ms-settings： network/wifi" 和 "ms settings：蓝牙"。 以下示例说明了一个策略，该策略仅允许访问 about 和 bluetooth 页面，它们分别具有URI“ms-settings:network-wifi”和“ms-settings:bluetooth”：
- `showonly:network-wifi;network-proxy;bluetooth`

若要通过预配包对此进行设置：

1. 在 Windows 配置设计器中创建包时，导航到“**策略”>“设置”>“PageVisibilityList**”
1. 输入字符串：**`showonly:network-wifi;network-proxy;bluetooth`**
1. 导出预配包。
1. 将该包应用于你的设备。
有关如何创建和应用预配包的完整详细信息，请访问 [此页面](hololens-provisioning.md)。

可使用 OMA-URI 通过 Intune 执行此操作：

1. 创建 **自定义策略**。
1. 设置 OMA-URI 时，请使用字符串：**`./Device/Vendor/MSFT/Policy/Config/Settings/PageVisibilityList`**
1. 选择数据选取时，请选择：**字符串**
1. 键入值时，请使用：**`showonly:network-wifi;network-proxy;bluetooth`**
1. 请确保将自定义设备配置分配给设备所属的组。

有关 Intune 组和设备配置的详细信息，请参阅 [HoloLens MDM 配置](hololens-mdm-configure.md)。

无论选择哪种方法，你的设备现在都应接收更改，并且将向用户显示以下“设置”应用。

![在“设置”应用中修改的使用时段的屏幕截图](images/hololens-page-visibility-list.jpg)

若要配置“设置”应用页面以显示或隐藏自己选择的页面，请查看 HoloLens 上可用的“设置 URI”。

## 设置 URI

HoloLens 设备和 Windows 10 设备在“设置”应用中的页面选择方面有所不同。 在此页面上，你将只能找到 HoloLens 上已有的设置。

### 帐户
| 设置页面           | URI                                            |
|-------------------------|------------------------------------------------|
| 登录选项         | ` ms-settings:signinoptions `                   |
| Iris 注册       | `ms-settings:signinoptions-launchirisenrollment` |
| 访问工作或学校帐户 | `ms-settings:workplace`                         |

### 设备
| 设置页面 | URI                          |
|---------------|------------------------------|
| 蓝牙     | `ms-settings:bluetooth` <br> `ms-settings:connecteddevices` |

### 隐私
| 设置页面            | URI                                             |
|--------------------------|-------------------------------------------------|
| 帐户信息             | `ms-settings:privacy-accountinfo`              |
| 应用诊断        | `ms-settings:privacy-appdiagnostics`              |
| 后台应用        | `ms-settings:privacy-backgroundapps`              |
| 用户移动           | `ms-settings:privacy-backgroundspatialperception` |
| 文件系统              | `ms-settings:privacy-broadfilesystemaccess`       |
| 日历                 | `ms-settings:privacy-calendar`                    |
| 呼叫历史记录             | `ms-settings:privacy-callhistory`                 |
| 联系人                 | `ms-settings:privacy-contacts`                    |
| 其他设备            | `ms-settings:privacy-customdevices`               |
| 文档                | `ms-settings:privacy-documents`                   |
| 电子邮件                    | `ms-settings:privacy-email`                       |
| 诊断和反馈 | `ms-settings:privacy-feedback`                    |
| 位置                 | `ms-settings:privacy-location`                    |
| 消息                | `ms-settings:privacy-messaging`                   |
| 麦克风               | `ms-settings:privacy-microphone`                  |
| 通知            | `ms-settings:privacy-notifications`               |
| 图片                 | `ms-settings:privacy-pictures`                    |
| 无线电收发器                   | `ms-settings:privacy-radios`                      |
| 语音                   | `ms-settings:privacy-speech`                      |
| 任务                    | `ms-settings:privacy-tasks`                       |
| 视频                   | `ms-settings:privacy-videos`                      |
| 语音激活       | `ms-settings:privacy-voiceactivation`             |
| 摄像头                   | `ms-settings:privacy-webcam`                      |

### 网络和 Internet
| 设置页面 | URI                              |
|---------------|----------------------------------|
| Wi-Fi  | `ms-settings:network-wifi`<br>`ms-settings:network-wifisettings`<br>`ms-settings:network-status`<br>`ms-settings:wifi-provisioning`    |
| VPN   | `ms-settings:network-vpn`          |
| 代理 | `ms-settings:network-proxy`        |

### 系统
| 设置页面      | URI                                |
|--------------------|------------------------------------|
| 共享体验 | `ms-settings:crossdevice`            |
| 颜色             | `ms-settings:colors`<br>`ms-settings:personalization-colors` |
| 通知和操作  | `ms-settings:notifications`          |
| 存储            | `ms-settings:storagesense`           |

### 时间和语言
| 设置页面 | URI                                           |
|---------------|-----------------------------------------------|
| 区域        | `ms-settings:regionformatting`                  |
| 语言      | `ms-settings:regionlanguage`<br>`ms-settings:regionlanguage-adddisplaylanguage`<br>`ms-settings:regionlanguage-setdisplaylanguage` |

### 更新和安全
| 设置页面                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Windows 预览体验计划               | `ms-settings:windowsinsider` <br>`ms-settings:windowsinsider-optin`          |
| Windows 更新                        | `ms-settings:windowsupdate`<br> `ms-settings:windowsupdate-activehours`  <br> `ms-settings:windowsupdate-history` <br> `ms-settings:windowsupdate-optionalupdates` <br><sup>1</sup>`ms-settings:windowsupdate-options`<br><sup>1</sup>`ms-settings:windowsupdate-restartoptions` |
| Windows 更新 - 检查更新 | `ms-settings:windowsupdate-action`          |
| 高级选项                    | `ms-settings:windowsupdate-options`         |

>  <sup>1</sup> 以下两个 URI 实际上并不会将您转到**高级选项**或**选项页面**；它们将仅阻止或显示主 Windows 更新页面。
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

有关 Windows 10 设置 URI 的完整列表，请访问[启动设置](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)文档。
