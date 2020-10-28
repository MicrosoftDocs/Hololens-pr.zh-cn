---
title: HoloLens 1 (gen) 发行说明
description: 了解每个新的 HoloLens 版本中的更新。
author: evmill
ms.author: v-evmill
manager: yannisle
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 05/12/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: ab67962efdafe3f39097210d60589dc6db715837
ms.sourcegitcommit: c870802ea75a9dd602319c59fedb124f80c19b71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "11136167"
---
# HoloLens 1 (gen) 发行说明

## HoloLens (第一代) 长期服务
HoloLens (第一代) 已进入长期服务 (LTS) 状态。 将来的更新将重点介绍问题和安全修补程序，同时通过 Windows 10 全息版1809版本（即版本)  (发行版）维护功能奇偶校验。

对于开发人员，这意味着 HoloLens (第一代) 应用将不支持 OpenXR API。  在 Unity 2019 LTS 中，这些耳机保持受支持，使用 WinRT API 后端通过 2022 mid 2019 LTS 的完整生命周期。

### Windows 10 全息版1809

> **适用于：** HoloLens (第一代) 

| 功能 | 详细信息 |
|---|---|
| **"快速操作" 菜单** | 在应用中，绽放手势现在将打开 "快速操作" 菜单，让你能够快速访问常用的系统功能，而无需离开应用。 <br> 有关展台模式中的 "快速操作" 菜单的信息，请参阅 [在展台模式下设置 HoloLens](hololens-kiosk.md) 。<br><br> |
| **从 "开始" 或 "快速操作" 菜单停止视频捕获** | 如果从 "开始" 菜单或 "快速操作" 菜单启动视频捕获，则可以从同一位置停止录制。  (别忘了，您也可以随时用语音命令执行此操作。 )  |
| **投影到启用了 Miracast 的设备** | 如果使用 Microsoft 显示适配器，请将 HoloLens 内容投影到附近的 Surface 设备或电视/显示器。  在 " **开始**" 上，选择 " **连接**"，然后选择要投影到的设备。 **注意：** 你可以将 HoloLens 部署到使用 Miracast 投影，而无需启用开发人员模式。 |
| **新通知** | 在 HoloLens 上查看和响应通知 toast，就像在电脑上执行的操作一样。 注视或关闭它们 (或者如果你使用的是沉浸式体验，请使用绽放手势) 。 |
| **HoloLens 覆盖**<br> (文件选取器、键盘、对话框等 )  | 现在，你可以在使用沉浸式应用时看到叠加（如键盘、对话框、文件选取器等）。 |
| **用于卷更改的视觉反馈覆盖 UI** | 使用 HoloLens 上的音量向上/向下按钮时，你将看到音量级别的视觉显示。 |
| **用于设备启动的新 UI** | 在启动过程中添加了一个加载指示器，可提供系统正在加载的视觉反馈。 重启设备以查看新的加载指示器-它位于 "Hello" 消息和 Windows 启动徽标之间。 |
| **附近共享** | 其他 Windows 附近的共享体验，允许你与附近的 Windows 设备共享捕获。 在 HoloLens 上捕获照片或视频时 (或使用应用（如 Microsoft Edge) ）中的 "共享" 按钮，选择附近要共享的 Windows 设备。 |
| **从 Microsoft Edge 共享** | "共享" 按钮现已在 HoloLens 上的 Microsoft Edge windows 上可用。 在 Microsoft Edge 中，选择 " **共享**"。 使用 HoloLens 共享选取器共享 web 内容。 |

#### 对于国际客户

| 功能 | 详细信息 |
| --- | --- |
| 本地化的中文和日语版本 | 使用适用于简体中文或日语的已本地化用户界面的 HoloLens，包括本地化拼音键盘、听写和语音命令。<br>[了解如何安装 HoloLens 的中文和日语版本。](hololens1-install-localized.md) |
|  (TTS) 的语音合成 | 语音合成功能现在支持中文、日语和英语。 |

#### 对于管理员

| 功能 |  详细信息  |
|---|----|
| [启用安装后预配](hololens-provisioning.md) | 现在，你可以随时使用 " **设置**" 应用运行时预配包。 |
| 已分配具有 Azure AD 组的访问权限 | 现在，你可以使用 Azure AD 组配置 Windows 分配的访问权限，以便设置单个或多应用展台配置。 |
| 登录屏幕上的配置文件切换时的 PIN 登录 | PIN 登录现在可供 **其他用户**使用。 |
| 使用密码登录 Web 凭据提供程序 | 现在，你可以选择 "全球登录" 选项来启动带密码的 web 登录。 在登录屏幕上，选择 " **登录选项** "，然后选择 "全球" 选项以启动 "web 登录"。 如果需要，请输入您的用户名，然后输入您的密码。 <br>**注意：** 在 web 登录期间出现提示时，您可以选择绕过任何引脚/智能卡选项。 |
| 通过 MDM 读取设备硬件信息，以便可以按序列号跟踪设备 | IT 管理员可以在其 MDM 控制台中按设备序列号查看和跟踪 HoloLens。 有关功能的可用性和说明，请参阅 MDM 文档。 |
| 通过 MDM 设置 HoloLens 设备名称 (重命名)  | IT 管理员可以在其 MDM 控制台中查看和重命名 HoloLens 设备。 有关功能的可用性和说明，请参阅 MDM 文档。 |

### 适用于 Microsoft HoloLens 的 Windows 10 版本1803

> **适用于：** HoloLens (第一代) 

Windows 10 版本1803是自 windows 全息版的 windows 10 版本1607版以来对 Windows 全息版的第一项功能更新。 此更新引入以下更改：

- 以前，您只能验证是否已将商业套件的升级许可证应用于 HoloLens 设备，方法是检查是否已在设备上使用 VPN。 现在， **Settings**  >  在应用升级许可证后，设置**系统**将显示**Windows 全息版企业**版。 [了解如何解锁 Windows 全息版商业版功能](hololens1-upgrade-enterprise.md)。

- 你可以在文件资源管理器应用和 [Windows Device Recovery 工具 (WDRT ") ](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)中查看设备属性中的操作系统内部版本号。
- 使用 Windows 配置设计器工具中的 "新建 **预配 hololens 设备** " 向导，预配 hololens 设备现在更容易。 在向导中，你可以配置设置体验和网络连接，设置开发人员模式，并获取批量 Azure AD 令牌。 [了解如何使用适用于 HoloLens 的简单预配向导](hololens-provisioning.md#provisioning-package-hololens-wizard)。

- 在预配包中创建本地帐户时，密码不再每42天过期。

- 你可以 [将 HoloLens 配置为单应用或多应用展台](hololens-kiosk.md)。 多应用展台模式允许你将 HoloLens 设置为仅运行你指定的应用，并阻止用户进行更改。

- 已启用 MTP)  (媒体传输协议，以便你可以通过 USB 将 HoloLens 设备连接到电脑，并在 HoloLens 和电脑之间传输文件。 你还可以使用文件资源管理器应用在 HoloLens 中移动和删除文件。

- 以前，使用 Azure Active Directory (Azure AD) 帐户登录到设备之后，你必须在 "**设置**" 中**添加工作访问权限**，才能访问企业资源。 现在，你使用 Azure AD 帐户登录，并且注册会自动发生。

- 登录前，您可以选择密码字段下方的 "网络" 图标，选择要连接的其他 Wi-Fi 网络。 您也可以连接到来宾网络，如宾馆、会议中心或企业。

- 现在，你可以使用 Azure AD 帐户轻松 [与多个用户共享 HoloLens](hololens-multiple-users.md) 。

- 当安装程序或登录失败时，选择新的 " **收集信息** " 选项以获取诊断日志以进行故障排除。

- 在 (MDM) 中，单个用户可以同步其公司电子邮件，而无需在移动设备管理中注册其设备。 你可以将设备与 Microsoft 帐户配合使用，下载并安装 "邮件" 应用，然后直接添加电子邮件帐户。

- 你可以在 "**设置**" 帐户中查看设备的 MDM 同步状态，以  >  **Accounts**  >  **访问工作或学校**  >  **信息**。 在 " **设备同步状态** " 部分中，你可以启动同步，查看由 MDM 管理的区域，以及创建和导出高级诊断报告。
