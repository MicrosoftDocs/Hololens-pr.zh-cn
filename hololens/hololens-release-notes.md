---
title: HoloLens 2 发行说明
description: 了解每个新的 HoloLens 版本中的更新。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/9/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 25a1bc21638090cc5d22bc4482299f3931641dea
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827923"
---
# HoloLens 2 发行说明

为确保您的 HoloLens 设备具有高效的体验，我们将继续发布功能、bug 和安全更新。 在此页面中，您可以了解每月 HoloLens 的新增功能。 如果你想要下载最新的 HoloLens 2 FFU 以通过 "[高级恢复助理](hololens-recovery.md#clean-reflash-the-device)" 刷新你的设备，你可以从[此处](https://aka.ms/hololens2download)下载。 这将保持最新，并且将与最新的通用内部版本匹配。 

HoloLens 模拟器发行说明可在[此处](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)找到。

## Windows 全息版 2004-2020 更新
- 内部版本19041.1106

更新中的改进和修复：

- 如果未指定某些属性，则自定义 MRC 记录器具有新的默认值。
  - 在 "MRC 视频" 效果中：
    - PreferredHologramPerspective （1 PhotoVideoCamera）
    - GlobalOpacityCoefficient （0.9 （HoloLens）1.0 （沉浸式头戴式耳机））
  - 在 "MRC 音频" 效果中：
    - LoopbackGain （Windows Device Portal 中混合现实捕获页面上的当前 "应用音频增益" 值）
    - MicrophoneGain （Windows Device Portal 中混合现实捕获页面上的当前 "Mic Audio 增益" 值）
- 此更新包含一个可在混合现实捕获方案中提高音频质量的 bug 修复。 尤其是，在显示 "开始" 菜单时，它应该消除录制中的任何音频 glitching。
- 改进了录制视频中的全息图稳定性。
- 解决了混合现实捕获在设备离开待机状态几天后无法录制视频的问题。
- 对于 Unity 应用程序，UserPresence API 通常是禁用的，以避免在面板翻转时导致某些应用暂停的问题，即使在后台运行的设置处于启用状态时也是如此。 现已针对 Unity 版本2018.4.18 及更高版本、2019.3.4 和更高版本启用 API。
- 通过 WiFi 连接访问 Device Portal 时，web 浏览器可能会阻止访问，因为证书无效、报告诸如 "ERR_SSL_PROTOCOL_ERROR" 之类的错误，即使设备证书以前已受信任。  在这种情况下，你将无法对 Device Portal 进行处理，因为忽略安全警告的选项不可用。  此更新可解决此问题。  如果设备证书以前已在电脑上下载并受信任，用于删除浏览器安全警告，并且遇到 SSL 错误，则需要下载新证书并信任该证书才能解决浏览器安全警告。
- 支持创建可使用 MSIX 程序包安装应用的运行时预配包的功能。
- 用户可以在设置 > 系统 > 全息影像下找到的新设置，允许用户在设备关闭时自动删除混合现实家庭中的所有全息影像。
- 修复了导致 hololens 应用更改像素格式的问题，这些应用会在 HoloLens 模拟器中呈现黑色。
- 修复了在虹膜登录期间导致崩溃的 bug。
- 修复了现有应用的重复应用商店下载问题。
- 修复了一个 bug 以防止沉浸式应用多次启动边缘。
- 修复了从1903版本更新后初始引导中的 "照片" 应用程序启动时出现的问题。
- 提高了性能和可靠性。

## Windows 全息版 1903-2020 更新
- 内部版本18362.1064

更新中的改进和修复：

- 如果未指定某些属性，则自定义 MRC 记录器具有新的默认值。
  - 在 "MRC 视频" 效果中：
    - PreferredHologramPerspective （1 PhotoVideoCamera）
    - GlobalOpacityCoefficient （0.9 （HoloLens）1.0 （沉浸式头戴式耳机））
  - 在 "MRC 音频" 效果中：
    - LoopbackGain （Windows Device Portal 中混合现实捕获页面上的当前 "应用音频增益" 值）
    - MicrophoneGain （Windows Device Portal 中混合现实捕获页面上的当前 "Mic Audio 增益" 值）
- 对于 Unity 应用程序，UserPresence API 通常是禁用的，以避免在面板翻转时导致某些应用暂停的问题，即使在后台运行的设置处于启用状态时也是如此。 现已针对 Unity 版本2018.4.18 及更高版本、2019.3.4 和更高版本启用 API。
- 修复了导致 hololens 应用更改像素格式的问题，这些应用会在 HoloLens 模拟器中呈现黑色。
- 修复了从1903版本更新后初始引导中的 "照片" 应用程序启动时出现的问题。

## Windows 全息版2004  
内部版本-19041.1103

我们很高兴地宣布，我们可能会更新 HoloLens 2、 **Windows 全息、版本 2004**的2020主要软件更新。 此版本包含大量激动人心的新功能，例如 Windows Autopilot 支持、应用深色模式、5G/LTE 热点 USB 以太网支持等。 若要更新到最新版本，请打开 " **设置" 应用**，转到 " **更新 & 安全**"，然后选择 " **检查更新**"   按钮。 

|             功能                              |          描述                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          通过 Windows AutoPilot 预配置和无缝设置用于生产的新设备                 |
|       FIDO 2 支持                             |          支持 FIDO2 安全密钥以对共享设备启用快速和安全身份验证            |
|       改进的预配                      |          将预配包从 u 盘无缝应用到 HoloLens                              |
|       应用程序安装状态                 |          在 "设置" 应用中，检查应用的安装状态是否已通过 MDM 推送到 HoloLens 2              |
|       配置服务提供商（Csp）   |          添加了新配置服务提供程序（Csp），增强了管理员控制功能。                 |
|       USB 5G/LTE 支持                       |          扩展的 USB 以太网功能支持 5G/LTE 支持                                    |
|       深色应用模式                              |          适用于支持深色模式和浅色模式的应用的深色应用模式，改善了查看体验        |
|       语音命令                             |          支持其他系统语音命令，以控制 HoloLens、无人参与                           |
|       手动跟踪改进                 |          手动跟踪改进使按钮和2D 平板交互更准确                        |
|       质量改进和修复                 |          跨平台的各种系统性能和可靠性改进                            |

### Windows Autopilot 支持 

用于 HoloLens 2 的 Windows Autopilot 允许设备销售渠道预注册 HoloLens 到你的 Intune 租户。  当设备到达时，它们准备就绪，可以作为你的租户下的共享设备进行自我部署。 若要利用自我部署，设备需要在安装程序的第一屏中使用 USB 至以太网转换器或将 USB-C 连接到 LTE 转换器时连接到网络。 

用户启动 Autopilot 自部署进程时，该过程完成以下步骤： 

1. 将设备加入 Azure Active Directory (Azure AD)。 
1. 使用 Azure AD 在 Microsoft Intune （或其他 MDM 服务）中注册设备。 
1. 下载面向设备的策略、证书和网络配置文件。 
1. 预配设备。 
1. 向用户呈现登录屏幕。 

请通过适用于[HoloLens 2 评估指南的 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)了解详细信息。

**请与您的帐户管理员联系，立即加入 AutoPilot 预览版。 Autopilot 已准备好的设备即将开始发货。**

### FIDO2 安全密钥支持 

许多人在工作或学校环境中与许多人共享一个 HoloLens 设备。 无论是在课堂上的学生之间共享设备，还是从设备保险箱中签出设备，很重要的一点是，无需键入长用户名和密码即可快速轻松地更改用户。 

FIDO 允许你组织中的任何人（AAD 租户）无需输入用户名或密码即可无缝登录到 HoloLens。 

FIDO2 安全密钥是基于 unphishable 标准的 passwordless 身份验证方法，可采用任何形式的外观。 快速身份在线（FIDO）是 passwordless 身份验证的开放标准。 FIDO 使用户和组织可以利用标准登录到其资源，而无需使用外部安全密钥或内置于设备的平台密钥的用户名或密码。 

阅读[passwordless 安全文档](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)以开始使用。 

### 通过预配包改进了 MDM 注册 

预配程序包允许你通过配置文件设置 HoloLens 配置，而不是通过 HoloLens 全新体验。 以前，预配程序包必须复制到 HoloLens "内部内存"，现在它们可以位于 USB 驱动器上，以便更容易在多个 HoloLens 上重复使用，因此更多的人可以并行预配 HoloLens。  此外，预配包支持用于注册设备管理的新字段，因此不会手动设置后期设置。 

1. 若要试用，请从 Windows 应用商店中将最新版本的 Windows 配置设计器下载到你的电脑。 
1. 选择 "**设置 Hololens 设备**" > 选择 "**设置 hololens 2 设备**" 
1. 构建配置文件，完成后，复制所有创建到 USB-C 存储设备的文件。 
1. 将其插入任何全新刷新的 HoloLens 并按**下音量 + Power**以应用预配包。 

### 业务线应用程序安装状态 

适用于业务线（LOB）应用的 MDM 应用部署和管理对我们的客户至关重要。 管理员和用户需要能够查看应用安装状态，以供审核和诊断之用。 在此版本中，我们将在 **"> 帐户" > Access 工作或学校 > 单击您的帐户 > 信息**的 "设置" 中添加更多详细信息。

### 其他 Csp 和策略 

[配置服务提供程序（CSP）](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)是用于读取、设置、修改或删除设备上的配置设置的接口。 在此版本中，我们将添加对更多策略的支持，从而提高控制管理员对已部署的 HoloLens 设备的控制权。 有关 HoloLens 支持的 Csp 列表，请访问此[链接](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。 此版本中的新增内容：

**策略云解决方案提供商** 

策略配置服务提供程序使企业能够在 Windows 设备上配置策略。 在此版本中，我们将为 HoloLens 添加新策略，如下所示。 你可以在[此处](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)了解有关受支持的策略的详细信息。  

- LetAppsAccessCamera_ForceAllowTheseApps  
- LetAppsAccessCamera_ForceDenyTheseApps  
- LetAppsAccessCamera_UserInControlOfTheseApps 
- LetAppsAccessGazeInput 
- LetAppsAccessGazeInput_ForceAllowTheseApps 
- LetAppsAccessGazeInput_ForceDenyTheseApps 
- LetAppsAccessGazeInput_UserInControlOfTheseApps 
- LetAppsAccessMicrophone_ForceAllowTheseApps 
- LetAppsAccessMicrophone_ForceDenyTheseApps 
- LetAppsAccessMicrophone_UserInControlOfTheseApps 
- AllowWiFi 

**NETWORKQOSPOLICY CSP**NetworkQoSPolicy 配置服务提供程序创建网络服务质量（QoS）策略。 QoS 策略根据一组匹配的条件对网络流量执行一组操作。 可在[此处](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)了解有关此策略的详细信息。 

### 已展开的 USB 以太网支持 5G/LTE tethered 设备

在通过 USB tethered 到 HoloLens 2 时，已添加支持以启用某些移动宽带设备，例如 5G/LTE 手机和 WiFi hotpots。 这些设备将在 "网络设置" 中显示为另一个以太网连接。 不支持需要外部驱动程序的移动宽带设备。 这将在 WiFi 不可用的情况下启用高带宽连接，并且 WiFi tethering 不具备足够的性能。 可在[此处](https://docs.microsoft.com/hololens/hololens-connect-devices)了解有关受支持的 USB 设备的详细信息。  

### 手动跟踪改进

在此版本中，手动跟踪已收到多项改进。 

- **指针具有稳定性：** 当 palm occluded 时，系统将会对索引手指的弯曲。  这可提高推送按钮、键入、滚动内容等内容的准确性！ 
- **减少意外 AirTaps：** 我们改进了 AirTap 手势的检测。  现在，在几种常见情况下出现意外激活的次数较少，例如将手放在一侧。 
- **用户切换可靠性：** 在来回共享设备时，在更新手形的大小时，系统现在更快、更可靠。 
- **减少右手偷窃：** 我们改进了两个参与传感器的视图的处理方式。  如果多人密切协作，那么，在场景中，所跟踪的手势将从用户跳转到其他人的手边。 
- **系统可靠性：** 修复了一个问题，该问题会导致手动跟踪在设备处于高负载下时停止工作。 

### 深色模式

许多 Windows 应用现在支持深色模式和浅色模式，并且 HoloLens 2 客户可以为同时支持这两种应用的应用选择默认模式。 一旦更新，默认应用模式将为 "深色"，但可以轻松更改。 导航到 "系统 > 颜色" > 的 "设置"，找到 "选择默认应用模式"。 下面是一些支持深色模式的内置应用： 

- 设置 
- Microsoft Store 
- 邮件 
- 日历 
- 文件资源管理器 
- 反馈中心 
- OneDrive 
- 照片 
- 3D 查看器 
- 电影和电视 

![深色模式窗口平铺](images/DarkMode.jpg)

### 系统语音命令

现在，你可以使用设备上的任何应用在你的语音中快速访问和使用命令。 如果你使用其他语言运行系统，请尝试使用该语言的相应命令。 有关这些命令以及如何使用它们的详细信息，请参阅我们的[文档。](https://docs.microsoft.com/hololens/hololens-cortana)  

### Cortana 更新 

已更新的应用与 Microsoft 365 （当前仅限英语（美国））集成，以帮助你在设备上更好地完成工作。 在 HoloLens 2 上，Cortana 将不再支持某些特定于设备的命令，如调整音量或重启设备，这些命令现在受上述新系统语音命令支持。 在[此处](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)了解有关新的 Cortana 应用及其方向的详细信息。 

### 质量改进和修复 

更新中也有改进和修复：  
- 此更新引入了一个活动的显示校准系统。 这将改善全息影像的稳定性和对齐方式，从而有助于它们在移动您的头面时保持不变。 
- 修复了用于 HoloLens 的 Wi-fi 流式处理定期中断的 bug。 如果应用程序指示它需要低延迟流，则可以通过调用[此函数](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)来完成此修补程序。 
- 修复了在使用研究模式流式处理期间设备可能挂起的问题。 
- 修复的 bug，在某些情况下，在恢复会话时，登录屏幕上将不会显示正确的用户。 
- 修复了用户无法通过设置导出 MDM 日志的问题。 
- 修复了紧跟在安装后立即关注的目视跟踪的问题：安装可能低于规范。 
- 修复了在某些条件下，目视跟踪子系统无法初始化和/或执行校准的问题。 
- 修复了提示校准已校准用户的问题。 
- 修复了在目视校准期间驱动程序崩溃的问题。 
- 修复了重复的电源按钮按下可能导致60秒的系统超时和外壳崩溃的问题。 
- 改善了深度缓冲区的稳定性。 
- 在反馈中心中添加了 "共享" 按钮，以便用户可以更轻松地共享反馈。 
- 修复了 RoboRaid 未正确安装的 bug。 

### 已知问题

- 我们正在研究使用 zh-cn&platform system 语言的问题，该问题阻止使用语音命令跟踪混合现实捕获或显示设备 IP 地址的工作。
- 我们正在调查需要你在启动设备后启动 Cortana 应用才能使用 "你好 Cortana" 语音激活的问题，并且如果你从18362版本更新，你可能会在 "开始" 中看到以前版本的 Cortana 应用的第二个应用磁贴，不再有效。 

## Windows 全息版 1903-五月2020更新 
- 内部版本18362.1061

此 "每月质量更新" 不包含任何更改，因为团队致力于向您提供最高质量的功能更新，您现在可以在 Windows 全息版本2004中更新上述详细信息。 请转到最新功能更新，以获得大量激动人心的新更改。

## Windows 全息版 1903-2020 年4月更新
- 内部版本18362.1059

**支持的应用的深色模式** 

许多 Windows 应用均支持深色模式和浅色模式，不久 HoloLens 2 客户可以为支持两种配色方案的应用选择默认模式！ 根据 overwhelmingly 肯定的客户反馈，通过此更新，我们将默认应用模式设置为 "深色"，但你可以随时轻松地更改此设置。
导航到 "**系统 > 颜色" >** 的 **"设置"，找到 "选择默认应用模式"。**

下面是一些支持深色模式的内置应用：
- 设置
- Microsoft Store
- 邮件
- 日历
- 文件资源管理器
- 反馈中心
- OneDrive
- 照片
- 3D 查看器
- 电影和电视

**更新中也有改进和修复：** 
- 确保在混合现实捕获中包含外壳覆盖。
- Unreal 开发人员现在可以使用 Device Portal 中的3D 视图页面来测试和调试其应用程序。
- 在使用 HolographicDepthReprojectionMethod DepthReprojection 算法时，在混合现实捕获中改进全息图稳定性。
- 固定 WinRT IStreamSocketListener API 类在32位 ARM 应用上未注册错误。

## Windows 全息版、版本 1903-2020 更新 
- 内部版本18362.1056

更新中的改进和修复：

- 在使用 HolographicDepthReprojectionMethod AutoPlanar 算法时，在混合现实捕获中改进全息图稳定性。
- 确保连接到 depth MF 示例的坐标系与公共文档一致。
- 通过让客户通过 device portal 粘贴大量文本，提高了开发者的工作效率。

## Windows 全息版 1903-2 月2020更新 
- 内部版本18362.1053

更新中的改进和修复：

- 已暂时禁用 Unity 应用程序的 HolographicSpace API，以避免在面板翻转时导致某些应用暂停的问题，即使启用了在后台运行的设置也是如此。
- 修复了手动跟踪的随机 HUP 大小，在这种情况下，用户将在几秒钟后注意到 UI 冻结，然后返回到外壳。
- 我们对手跟踪进行了改进，因此在使用食指 poking 时，手指的上半部分将不太可能意外卷曲。
- 改进了 head 跟踪、空间映射和其他运行时的可靠性。

## Windows 全息版 1903-2020 更新 
- 内部版本18362.1043

更新改进：

- 使用 HoloLens 2 模拟器时，对独占应用的稳定性有所改进。

## Windows 全息版 1903-2019 更新 
- 内部版本18362.1042

更新中的改进和修复：

- 介绍 LSR （最后阶段重现）修补程序。 改善全息影像的视觉呈现，使其更准确地获得更稳定的深度。 如果应用在此更新后未正确设置全息影像的深度，此操作将更明显。
- 修复了独占应用和独占应用之间的导航的稳定性。
- 解决了混合现实捕获在设备离开待机状态几天后无法录制视频的问题。
- 改善全息图稳定性。

## Windows 全息版、版本 1903-2019 更新 
- 内部版本18362.1039

更新中的改进和修复：

- 修复了在初始设置 en CA 和 en-us 时出现的 **"选择"** 语音命令。
- 改进了在最新的 Unity 和 MRTK 版本中放置的对象的视觉质量。
- 修复了在启动并再次关闭 "引脚" 面板时，在启动时仍处于暂停状态的全息应用程序的解决问题。
- 适用于 HoloLens 2 和模拟器的 OpenXR 运行时一致性修复和改进。


