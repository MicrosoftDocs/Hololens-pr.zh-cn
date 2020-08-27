---
title: 设置 URI
description: HoloLens 支持的 URI 的列表，这些 URI 适用于 PageVisibilityList
author: evmill
ms.author: v-evmill
ms.date: 8/1/2020
ms.topic: article
keywords: hololens, hololens 2, 分配的访问权限, 展台, 设置页面
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: widuff
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 6b506b36915c8f34b90c455410db67e55a2cca09
ms.sourcegitcommit: 7f48e7103f869a22a0d20a54dc8f9b708b22484c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "10963708"
---
# 设置 URI

HoloLens 设备的其中一项易管理的功能是使用 [Settings/PageVisibilityList 策略](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)限制“设置”应用中显示的页面。 HoloLens 设备和 Windows 10 设备在“设置”应用中的页面选择方面有所不同。 在此页面上，你将只能找到 HoloLens 上已有的设置。 

## 帐户
| 设置页面           | URI                                            |
|-------------------------|------------------------------------------------|
| 登录选项         | ms-settings:signinoptions                      |
| Iris 注册       | ms-settings:signinoptions-launchirisenrollment |
| 访问工作或学校帐户 | ms-settings:workplace                          |

## 设备
| 设置页面 | URI                          |
|---------------|------------------------------|
| 蓝牙     | ms-settings:bluetooth <br> ms-settings:connecteddevices |

## 隐私
| 设置页面            | URI                                             |
|--------------------------|-------------------------------------------------|
| 帐户信息             | ms-settings:privacy-accountinfo                 |
| 应用诊断        | ms-settings:privacy-appdiagnostics              |
| 后台应用        | ms-settings:privacy-backgroundapps              |
| 用户移动           | ms-settings:privacy-backgroundspatialperception |
| 文件系统              | ms-settings:privacy-broadfilesystemaccess       |
| 日历                 | ms-settings:privacy-calendar                    |
| 呼叫历史记录             | ms-settings:privacy-callhistory                 |
| 联系人                 | ms-settings:privacy-contacts                    |
| 其他设备            | ms-settings:privacy-customdevices               |
| 文档                | ms-settings:privacy-documents                   |
| 电子邮件                    | ms-settings:privacy-email                       |
| 反馈和诊断 | ms-settings:privacy-feedback                    |
| 位置                 | ms-settings:privacy-location                    |
| 消息                | ms-settings:privacy-messaging                   |
| 麦克风               | ms-settings:privacy-microphone                  |
| 通知            | ms-settings:privacy-notifications               |
| 图片                 | ms-settings:privacy-pictures                    |
| 无线电收发器                   | ms-settings:privacy-radios                      |
| 语音                   | ms-settings:privacy-speech                      |
| 任务                    | ms-settings:privacy-tasks                       |
| 视频                   | ms-settings:privacy-videos                      |
| 语音激活       | ms-settings:privacy-voiceactivation             |
| 相机                   | ms-settings:privacy-webcam                      |

## 网络和 Internet
| 设置页面 | URI                              |
|---------------|----------------------------------|
| WLAN  | ms-settings:network-wifi<br>ms-settings:network-wifisettings<br>ms-settings:network-status<br>ms-settings:wifi-provisioning    |
| VPN   | ms-settings:network-vpn          |
| 代理 | ms-settings:network-proxy        |

## 系统
| 设置页面      | URI                                |
|--------------------|------------------------------------|
| 共享体验 | ms-settings:crossdevice            |
| 颜色             | ms-settings:colors<br>ms-settings:personalization-colors |
| 通知和操作  | ms-settings:notifications          |
| 存储            | ms-settings:storagesense           |

## 时间和语言
| 设置页面 | URI                                           |
|---------------|-----------------------------------------------|
| Region        | ms-settings:regionformatting                  |
| 语言      | ms-settings:regionlanguage<br>ms-settings:regionlanguage-adddisplaylanguage<br>ms-settings:regionlanguage-setdisplaylanguage |

## 更新和安全
| 设置页面                         | URI                                       |
|---------------------------------------|-------------------------------------------|
| Windows 预览体验计划               | ms-settings:windowsinsider <br>ms-settings:windowsinsider-optin          |
| Windows 更新                        | ms-settings:windowsupdate<br> ms-settings:windowsupdate-activehours  <br> ms-settings:windowsupdate-history <br> ms-settings:windowsupdate-optionalupdates <br><sup>1</sup>ms-settings:windowsupdate-options<br><sup>1</sup>ms-settings:windowsupdate-restartoptions |
| Windows 更新 - 检查更新 | ms-settings:windowsupdate-action          |
| 高级选项                    | ms-settings:windowsupdate-options         |

> [!NOTE]
>  1 下面两个 URI 实际上并不会将你转到高级选项或选项页面，它们将仅阻止/显示主要 Windows 更新页面。 
> - ms-settings:windowsupdate-options
> - ms-settings:windowsupdate-restartoptions 

有关 Windows 10 设置 URI 的完整列表，请访问[此处](https://docs.microsoft.com/windows/uwp/launch-resume/launch-settings-app#ms-settings-uri-scheme-reference)。 
