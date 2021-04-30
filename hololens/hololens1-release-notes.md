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
ms.date: 10/13/2020
audience: ITPro
appliesto:
- HoloLens 1
ms.openlocfilehash: 0fb6c9ed1cd8d3ecc23975052eed54512a465bfb
ms.sourcegitcommit: 35e180e09e3938c25e4cac8e99885d7e57fa4dad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "108308540"
---
# <a name="hololens-1st-gen-release-notes"></a>HoloLens 1 (gen) 发行说明

## <a name="hololens-1st-gen-long-term-servicing"></a>HoloLens (第一代) 长期服务
HoloLens (第一代) 已进入长期维护 (LTS) 状态。 将来的更新将重点介绍问题和安全修补程序，同时保持与适用于 HoloLens (第一代) 版本1809版本的功能的奇偶校验。

对于开发人员而言，这意味着 HoloLens (第一代) 应用将不支持 OpenXR API。  在 Unity 2019 LTS 中，这些耳机仍受支持，其中包含 WinRT API 后端，以实现 Unity 2019 LTS 2022 到的完整生命周期。

### <a name="windows-10-holographic-version-1809"></a>Windows 10 全息版，1809版

> **适用于：** HoloLens (第一代) 

| 功能 | 详细信息 |
|---|---|
| **快速操作菜单** | 当你在应用程序中时，布隆手势现在将打开一个 "快速操作" 菜单，可让你快速访问常用的系统功能，而无需离开应用。 <br> 有关展台模式下 "快速操作" 菜单的信息，请参阅 [在展台模式下设置 HoloLens](hololens-kiosk.md) 。<br><br> |
| **从 "开始" 或 "快速操作" 菜单停止视频捕获** | 如果从 "开始" 菜单或 "快速操作" 菜单启动视频捕获，则可以从同一位置停止录制。  (别忘了，您也可以通过语音命令来执行此操作。 )  |
| **投影到启用了 Miracast 的设备** | 如果使用 Microsoft 显示适配器，请将你的 HoloLens 内容投影到附近的 Surface 设备或电视/显示器。  在 " **开始**" 中，选择 " **连接**"，然后选择要投影到的设备。 **注意：** 你可以在不启用开发人员模式的情况下部署 HoloLens 来使用 Miracast 投影。 |
| **新通知** | 查看和响应 HoloLens 上的通知 toast，就像在电脑上操作一样。 看看响应或消除这些问题 (或者如果你处于沉浸式体验，请使用布隆手势) 。 |
| **HoloLens 覆盖**<br> (文件选取器、键盘、对话框等 )  | 你现在可以在使用沉浸式应用时看到叠加，如键盘、对话框、文件选取器等。 |
| **卷更改的视觉反馈覆盖用户界面** | 使用 HoloLens 上的 "音量向上/向下" 按钮时，会看到音量级别的直观显示。 |
| **设备启动的新用户界面** | 在启动过程中添加了一个加载指示器，以提供系统正在加载的视觉反馈。 重新启动设备以查看新的加载指示器-它在 "Hello" 消息和 Windows 启动徽标之间。 |
| **邻近共享** | 添加了 Windows 附近共享体验，使你可以与附近的 Windows 设备共享捕获。 当你在 HoloLens 上捕获照片或视频时 (或者使用 Microsoft Edge) 等应用中的 "共享" 按钮时，请选择要与之共享的附近 Windows 设备。 |
| **从 Microsoft Edge 共享** | "共享" 按钮现在在 HoloLens 上的 Microsoft Edge windows 中可用。 在 Microsoft Edge 中，选择 " **共享**"。 使用 HoloLens 共享选取器共享 web 内容。 |

#### <a name="for-international-customers"></a>对于国际客户

| 功能 | 详细信息 |
| --- | --- |
| 本地化中文和日语版 | 将 HoloLens 用于简体中文或日语的本地化用户界面，包括本地化拼音键盘、听写和语音命令。<br>[了解如何安装 HoloLens 的中文版和日语版。](hololens1-install-localized.md) |
| ) 的语音合成 ( | 语音合成功能现在支持中文、日语和英语。 |

#### <a name="for-administrators"></a>面向管理员

| 功能 |  详细信息  |
|---|----|
| [启用安装后设置](hololens-provisioning.md) | 你现在可以使用 " **设置**" 随时应用运行时预配包。 |
| 使用 Azure AD 组分配访问权限 | 你现在可以使用 Azure AD 组来配置 Windows 分配的访问权限，以设置单个或多应用展台配置。 |
| 在登录屏幕上从配置文件切换进行 PIN 登录 | PIN 登录目前可供 **其他用户** 使用。 |
| 使用密码通过 Web 凭据提供程序登录 | 你现在可以选择 "全球登录" 选项以启动具有密码的 web 登录。 在登录屏幕中，选择 " **登录" 选项** ，然后选择 "地球" 选项以启动 web 登录。 如果需要，请输入你的用户名，然后输入你的密码。 <br>**注意：** 你可以在 web 登录过程中出现提示时，选择绕过任何 PIN/智能卡选项。 |
| 通过 MDM 读取设备硬件信息，使设备能够按序列号进行跟踪 | IT 管理员可以在其 MDM 控制台中按设备序列号查看和跟踪 HoloLens。 请参阅 MDM 文档了解功能可用性和说明。 |
| 通过 MDM 设置 HoloLens 设备名称 (重命名)  | IT 管理员可以在其 MDM 控制台中查看和重命名 HoloLens 设备。 请参阅 MDM 文档了解功能可用性和说明。 |

### <a name="windows-10-version-1803-for-microsoft-hololens"></a>Windows 10，版本1803，适用于 Microsoft HoloLens

> **适用于：** HoloLens (第一代) 

Windows 10 版本1803是自 windows 10 版本1607中的 windows 全息版的第一项功能更新。 此更新引入了以下更改：

- 以前，只能通过检查设备上的 VPN 是否为可用选项，验证是否已将商用套件的升级许可证应用到了你的 HoloLens 设备。 现在，   >  在应用升级许可证后，设置 **系统** 会显示 **Windows 全息 for Business** 。 [了解如何解锁 Windows 全息版功能](hololens1-upgrade-enterprise.md)。

- 你可以在文件资源管理器应用程序的 "设备属性" 中查看操作系统内部版本号，在 [Windows 设备恢复工具中 (WDRT ") ](https://support.microsoft.com/help/12379/windows-10-mobile-device-recovery-tool-faq)。
- 使用 Windows 配置设计器工具中的 "新建 **预配 hololens 设备** " 向导，预配 HoloLens 设备现在更容易。 在向导中，你可以配置安装体验和网络连接、设置开发人员模式并获取批量 Azure AD 令牌。 [了解如何使用适用于 HoloLens 的简单设置向导](hololens-provisioning.md#provisioning-package-hololens-wizard)。

- 当你在预配包中创建本地帐户时，该密码每42天将不再过期。

- 可以 [将 HoloLens 配置为单应用或多应用展台](hololens-kiosk.md)。 多应用展台模式可让你将 HoloLens 设置为仅运行指定的应用，并阻止用户进行更改。

- 已启用 (MTP) 的媒体传输协议，以便你可以通过 USB 将 HoloLens 设备连接到电脑，并在 HoloLens 与电脑之间传输文件。 你还可以使用文件资源管理器应用在 HoloLens 内移动和删除文件。

- 以前，使用 Azure Active Directory (Azure AD) 帐户登录到设备后，你必须在 "**设置**" 中 **添加 "工作访问**" 才能访问公司资源。 现在，使用 Azure AD 帐户登录，并自动进行注册。

- 登录之前，可以选择 "密码" 字段下面的网络图标，选择要连接到的其他 Wi-Fi 网络。 你还可以连接到来宾网络，如宾馆、会议中心或企业。

- 你现在可以使用 Azure AD 帐户轻松地 [与多个用户共享 HoloLens](hololens-multiple-users.md) 。

- 当安装或登录失败时，选择 "新 **收集信息** " 选项以获取诊断日志进行故障排除。

- 单个用户可以同步其公司电子邮件，而无需在移动设备管理 (MDM) 中注册其设备。 你可以使用具有 Microsoft 帐户的设备，下载并安装邮件应用程序，并直接添加电子邮件帐户。

- 可以在 "**设置**" "帐户" "  >    >  **访问工作或学校**  >  **信息**" 中检查设备的 MDM 同步状态。 在 " **设备同步状态** " 部分中，可以开始同步、查看由 MDM 管理的区域，以及创建和导出高级诊断报告。
