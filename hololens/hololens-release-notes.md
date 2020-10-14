---
title: HoloLens 2 发行说明
description: 了解每个新的 HoloLens 2 版本中的更新。
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
ms.openlocfilehash: 23ec5478c35977d1fd1fa20a33827e441d4b5c12
ms.sourcegitcommit: 264c8ff6726f702c3770525d774e0c1d263a2705
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117767"
---
# HoloLens 2 发行说明

为确保您的 HoloLens 设备具有高效的体验，我们将继续发布功能、缺陷和安全更新。 在此页面上，您可以查看每月 HoloLens 的新增功能。 若要获取最新的 HoloLens 2 完整闪存更新 (FFU) [通过 "高级恢复助理" 将您的设备闪存](hololens-recovery.md#clean-reflash-the-device)，请 [在此处下载](https://aka.ms/hololens2download)。 下载将保持最新状态，并提供最新的通用内部版本。

>[!NOTE]
> 若要阅读 HoloLens 模拟器发行说明，请 [访问存档](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)。

## Windows 全息版 2004-2020 更新
- 内部版本19041.1124
 
更新中的改进和修复：

- 已删除导致运行时系统错误的不必要检查。

## Windows 全息版 1903-2020 更新
- 内部版本18362.1081

此每月质量更新不包含任何显著更改，我们鼓励你试用 Windows 全息版2004的最新版本。

## Windows 全息版 2004-2020 更新
- 内部版本19041.1117

更新中的改进和修复：

- 解决了阻止 Visual Studio 在 package.appxmanifest 中存在 SupportsMultipleInstances = "true" 时调试应用程序的问题。
- 此版本包括 NCSI 代理检测修复，以解决通过网络代理进行的 Internet 检测失败。 NCSI 可以使用计算机代理和每个配置文件的代理进行 Internet 连接检测。 未来版本中的 NCSI 将支持每用户代理。
- 在大多数 Windows Mixed Reality 设备上，当用户的 head 位于要进行转发的中性位置时，向前矢量平行于地面。 但是，较早版本的 HoloLens 2 将矢量调整为垂直于显示面板，而不是相对于理想方向向下倾斜几度。 较新版本的 HoloLens 2 已更正此情况，以确保各种形式因素的语义一致性。
- 改善了右手跟踪的可靠性，这些可靠性将导致特定方案中的跟踪损失较少。
- 此版本包含一个修补程序，可改进音频时间戳质量，这可能会导致视频捕获问题。

## Windows 全息版 1903-2020 更新
- 内部版本18362.1079

更新中的改进和修复：

- 在大多数 Windows Mixed Reality 设备上，当用户的 head 位于要进行转发的中性位置时，向前矢量平行于地面。 但是，较早版本的 HoloLens 2 将矢量调整为垂直于显示面板，而不是相对于理想方向向下倾斜几度。 较新版本的 HoloLens 2 已更正此情况，以确保各种形式因素的语义一致性。
- 改善了右手跟踪的可靠性，这些可靠性将导致特定方案中的跟踪损失较少。

## Windows 全息版 2004-2020 更新
- 内部版本19041.1113

更新中的改进和修复：

- "设置" 应用将不再关注用户进入虹膜注册或目视跟踪校准体验。
- 修复了在 OOBE 期间应用预配包的 bug，用于重命名设备并执行其他操作 (例如，连接到网络) 将无法在设备重启（由于重命名）后执行其他操作。
- 已修改初始设备设置流的配色方案，以提高视觉质量。

## Windows 全息版 1903-2020 更新
- 内部版本18362.1074

此每月质量更新不包含任何显著更改，我们鼓励你试用 Windows 全息版2004的最新版本。

## Windows 全息版 2004-2020 年7月更新
- 内部版本19041.1109

更新中的改进和修复：

- 现在，开发人员可以在启用或禁用设备门户时选择是否需要安全连接。
- 操作系统更新后，应用程序启动时的可靠性有所改进。
- 已将默认收件箱亮度更改为100%。
- 解决了有关 HoloLens 2 上的 Windows Device Portal 的 HTTPS 转发的问题。

## Windows 全息版 1903-2020 年7月更新
- 内部版本18362.1071

更新中的改进和修复：

- 修复了一个问题，该问题可能会导致全息图在丢失或执行跟踪时无法在 Unity 应用程序中消失。
- 修复了在某些设备上使用 HoloLens 模拟器和硬件加速时，导致独占 HoloLens 应用崩溃的问题。
- 解决了与 HoloLens 2 上的 Windows Device Portal 的 HTTPS 转发有关的问题。

## Windows 全息版 2004-2020 更新
- 内部版本19041.1106

更新中的改进和修复：

- 如果未指定某些属性，自定义 MRC 记录器现在具有新的默认值。
  - 在 " *MRC 视频" 效果*中：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式头戴式耳机) # A5
  - 在 " *MRC 音频" 效果*中：
    - LoopbackGain (Windows Device Portal 中混合现实捕获页面上的当前 "应用音频收益" 值) 
    - MicrophoneGain (Windows Device Portal 中混合现实捕获页面上的当前 "Mic Audio 增益" 值) 
- 修复了在混合现实捕获方案中提高音频质量的 bug。 尤其是，此修补程序应在显示 " **开始** " 菜单时消除录制中的音频 glitching。
- 改进了录制视频中的全息图稳定性。
- 解决了在设备离开待机状态几天后混合现实捕获无法录制视频的问题。
- 对于 Unity 应用程序，HolographicSpace 通常禁用 UserPresence API。 此行为可避免在面板翻转时导致某些应用暂停的问题，即使已启用 "在后台运行" 设置。 现已针对 Unity 版本2018.4.18 及更高版本和2019.3.4 及更高版本启用 API。
- 通过 Wi-Fi 连接访问 Device Portal 时，web 浏览器可能会阻止访问，因为证书无效。 浏览器可能会报告诸如 "ERR_SSL_PROTOCOL_ERROR" 之类的错误，即使设备证书以前已受信任。 在这种情况下，你无法对 Device Portal 进行进度，因为没有用于忽略安全警告的选项。 此更新解决了此问题。 如果以前在电脑上下载并信任设备证书以删除浏览器安全警告，并且发生 SSL 错误，则必须下载新证书并信任该证书才能解决浏览器安全警告。
- 已启用创建可使用 MSIX 程序包安装应用的运行时预配包的功能。
- 在**设置**系统全息图中添加了一项设置  >  **System**  >  **Holograms** ，使用户可以在设备关闭时自动删除混合现实主页中的所有全息影像。
- 修复了导致 hololens 应用更改像素格式的问题，这些应用会在 HoloLens 模拟器中呈现黑色。
- 修复了在虹膜登录期间导致崩溃的 bug。
- 修复了有关为现有应用重复下载的应用的问题。
- 修复了一个 bug 以防止沉浸式应用重复打开 Microsoft Edge。
- 修复了从1903版本更新后初始引导中的 "照片" 应用启动时出现的问题。
- 提高了性能和可靠性。

## Windows 全息版 1903-2020 更新
- 内部版本18362.1064

更新中的改进和修复：

- 如果未指定某些属性，则自定义 MRC 记录器具有新的默认值。
  - 在 " *MRC 视频" 效果*中：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式头戴式耳机) # A5
  - 在 " *MRC 音频" 效果*中：
    - LoopbackGain (Windows Device Portal 中混合现实捕获页面上的当前 "应用音频收益" 值) 
    - MicrophoneGain (Windows Device Portal 中混合现实捕获页面上的当前 "Mic Audio 增益" 值) 
- 对于 Unity 应用程序，HolographicSpace 通常禁用 UserPresence API。 此行为可避免在面板翻转时导致某些应用暂停的问题，即使启用了在后台运行的设置也是如此。 现已针对 Unity 版本2018.4.18 和更高版本以及2019.3.4 和更高版本启用 API。
- 修复了导致 hololens 应用更改像素格式的问题，这些应用会在 HoloLens 模拟器中呈现黑色。
- 修复了从1903版本更新后初始启动时启动照片应用的问题。

## Windows 全息版2004  
- 内部版本-19041.1103

适用于 HoloLens 2、 *Windows 全息版、版本 2004* 的2020主要软件更新包括一种令人兴奋的新功能，例如对 Windows Autopilot、应用深色模式、USB 以太网支持 5G/LTE 热点的支持等。 若要更新到最新版本，请打开 "**设置**"   应用，转到 " **更新 & 安全**"，然后选择 " **检查更新**"   按钮。 

|             功能                              |          描述                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          使用 Windows AutoPilot 为生产预配置和无缝设置新设备                 |
|       FIDO 2 支持                             |          支持 FIDO2 安全密钥以对共享设备启用快速和安全身份验证            |
|       改进的预配                      |          将预配包从 u 盘无缝应用到 HoloLens                              |
|       应用程序安装状态                 |          在应用的 "设置" 应用中检查安装状态已通过 MDM 推送到 HoloLens 2               |
|        (Csp) 的配置服务提供商   |          添加了新的配置服务提供程序以增强管理员控制功能                 |
|       USB 5G/LTE 支持                       |          扩展的 USB 以太网功能支持 5G/LTE 支持                                    |
|       深色应用模式                              |          适用于支持深色模式和浅色模式的应用的深色应用模式，改善了查看体验        |
|       语音命令                             |          支持用于控制 HoloLens 免提的其他系统语音命令                           |
|       手动跟踪改进                 |          手动跟踪改进使按钮和2D 平板交互更准确                        |
|       质量改进和修复                 |          跨平台的各种系统性能和可靠性改进                            |

### Windows Autopilot 支持

用于 HoloLens 2 的 Windows Autopilot 允许设备销售渠道预注册 HoloLens 到你的 Intune 租户。 当设备到达时，它们准备就绪，可以作为你的租户下的共享设备进行自我部署。 若要利用自我部署，设备必须在安装过程的第一个屏幕中使用 USB-C-以太网或 USB--LTE 转换器连接到网络。

用户启动 Autopilot 自部署过程后，该过程将完成以下步骤：

1. 将设备加入 Azure Active Directory (Azure AD)。
1. 使用 Azure AD 在 Microsoft Intune （或其他 MDM 服务）中注册设备。
1. 下载面向设备的策略、证书和网络配置文件。
1. 预配设备。
1. 向用户呈现登录屏幕。

请通过适用于 [HoloLens 2 评估指南的 Windows Autopilot](https://docs.microsoft.com/hololens/hololens2-autopilot)了解详细信息。

*请与您的帐户管理员联系，立即加入 AutoPilot 预览版。 Autopilot 已准备好的设备即将开始发货。*

### FIDO2 安全密钥支持

某些用户在工作或学校环境中与其他用户共享一个 HoloLens 设备。 因此，用户不必输入长的用户名和密码，就很重要。 快速身份联机 (FIDO) 允许你组织中的任何人 (Azure AD 租户) 无需输入用户名或密码即可无缝登录到 HoloLens。

FIDO2 安全密钥是一种基于标准的 "unphishable" passwordless 身份验证方法，可采用任何形式的外观。 FIDO 是一种用于 passwordless 身份验证的开放式标准。 它允许用户和组织无需用户名或密码即可登录到其资源。 而是使用内置的安全密钥或内置于设备的平台密钥。

若要开始使用，请参阅 [启用 passwordless 安全密钥登录](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### 通过预配包改进了 MDM 注册

预配程序包允许你通过配置文件（而不是 HoloLens 全新体验）设置 HoloLens 配置。 以前，必须将预配包复制到 HoloLens 内部内存。 现在，他们可以在 USB 驱动器上使用，以便更轻松地在多个 HoloLens 设备上重用，并且可以并行预配设备。 预配程序包现在还支持用于注册设备管理的字段，因此预配后无手动设置。

若要试用：

1. 将 windows 配置设计器的最新版本从 Windows 应用商店下载到你的电脑。
1. 选择 "**预配 hololens 设备**"  >  **预配 hololens 2 设备**。
2. 构建配置文件。 然后将创建的所有文件复制到一个 USB-C 存储设备。
3. 将 USB-C 设备插入任何全新刷新的 HoloLens。 然后按**音量按下**  +  **电源**按钮以应用预配包。

### 业务线应用程序安装状态

适用于 HoloLens 的 MDM 应用部署和业务线应用的管理是 HoloLens 的关键。 管理员和用户需要查看用于审核和诊断的应用安装状态。 在此版本中，我们在**设置**帐户中添加了更多详细信息  >  **Accounts**  >  **访问工作或学校**  >  **单击您的帐户**  >  **信息**。

### 其他 Csp 和策略

[配置服务提供程序 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)是用于读取、设置、修改或删除设备上的配置设置的接口。 在此版本中，我们添加了对更多策略的支持，以增加管理员对已部署的 HoloLens 设备的控制。 有关 HoloLens 支持的 Csp 列表，请参阅 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

此版本中的新增内容：

**策略云解决方案提供商** 

策略配置服务提供程序使企业能够在 Windows 设备上配置策略。 在此版本中，我们为 HoloLens 添加了新策略，这些策略将在此处列出。 若要了解详细信息，请参阅 [HoloLens 2 支持的策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)。  

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

**NetworkQoSPolicy 云解决方案提供商**

NetworkQoSPolicy 配置服务提供程序创建网络服务质量 (QoS) 策略。 QoS 策略根据一组匹配的条件对网络流量执行一组操作。 若要了解详细信息，请参阅 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

### 已展开的 USB 以太网支持 5G/LTE tethered 设备

已添加支持以启用某些移动宽带设备，如 5G/LTE 电话和 Wi-Fi hotpots，它们通过 USB tethered 到 HoloLens 2。 这些设备现在在 " **网络设置** " 中显示为另一个以太网连接。 不支持需要外部驱动程序的 (移动宽带设备。 ) 此功能可在 Wi-Fi 不可用时启用高带宽连接，并且 Wi-Fi 的 tethering 没有足够的性能。 若要了解有关受支持的 USB 设备的详细信息，请参阅 [连接到蓝牙和 USB-C 设备](https://docs.microsoft.com/hololens/hololens-connect-devices)。  

### 手动跟踪改进

此版本包括多项跟踪改进：

- **指针具有稳定性：** 现在，系统通过 palm 获取 occluded 时，resists 将对食指进行弯曲。 当你推送按钮、键入、滚动内容等时，此更改可提高精确度。 
- **减少了意外的空中点击：** 我们改进了对空中点击手势的检测。 现在，在几种常见方案中（例如，当您将手放到您的一侧时），会减少意外激活的次数。
- **用户切换可靠性：** 当您共享设备时，系统现在可以更快、更可靠地更新手形大小。
- **减少右手偷窃：** 我们改进了对传感器的两次手的处理情形。 如果多人一起密切协作，现在，所跟踪的手势将从用户 "跳转" 到场景中其他人的手边。
- **系统可靠性：** 修复了当设备处于高负载时导致手动跟踪停止工作的问题。

### 深色模式

许多 Windows 应用现在支持深色模式和浅色模式。 HoloLens 2 用户可以为支持两者的应用选择默认模式。 更新后，默认应用模式为 "深色"，但你可以轻松地更改此设置：导航到 "**设置**"  >  **系统**  >  **颜色**  >  **选择默认应用模式**。 

这些 "机箱中" 应用支持深色模式： 

- “设置” 
- Microsoft Store 
- Mail 
- 日历 
- 文件资源管理器 
- 反馈中心 
- OneDrive 
- 照片 
- 3D 查看器 
- 电影和电视 

![深色模式窗口平铺](images/DarkMode.jpg)

### 系统语音命令

现在，你可以将语音命令与设备上的任何应用配合使用。 有关详细信息，请参阅 [使用语音操作 HoloLens](https://docs.microsoft.com/hololens/hololens-cortana)。 另请参阅 [HoloLens 2 支持的语言](https://docs.microsoft.com/hololens/hololens2-language-support)。  

### Cortana 更新

已更新的应用与 Microsoft 365 集成以帮助你在设备上进行更多的操作 (当前仅 US-English) 。 在 HoloLens 2 上，Cortana 不再支持特定于设备的命令，如调整音量或重启。 新的系统语音命令现在支持这些选项。 在我们的 [博客](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)中了解有关新的 Cortana 应用的详细信息。

### 质量改进和修复

更新中也有改进和修复：  
- 引入了活动的显示校准系统。 此功能可改善全息影像的稳定性和对齐方式。 当您的打印头并排移动时，它们将保留在原地。
- 修复了 Wi-Fi 到 HoloLens 的数据流定期中断的 bug。 如果应用程序指示它需要低延迟流，请通过调用 [SetSocketMediaStreamingMode 函数](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)来实现修复。
- 修复了在研究模式下流式处理期间发生的设备挂起。
- 修复了一个 bug，在某些情况下，在恢复会话时，在登录屏幕上无法显示正确的用户。
- 修复了用户无法通过 **设置**导出 MDM 日志的问题。
- 修复了立即关注全新设置的目视跟踪的问题，这可能比预期的要低。
- 修复了目视跟踪子系统无法在特定条件下初始化或执行校准的问题。
- 修复了提示校准已校准用户的问题。
- 修复了在目视校准期间驱动程序崩溃的问题。
- 修复了重复的电源按钮按下可能导致60秒系统超时和外壳崩溃的问题。
- 改善了深度缓冲区的稳定性。
- 在 "反馈中心" 添加了 " **共享** " 按钮，以便用户可以更轻松地共享反馈。
- 修复了 RoboRaid wan't 正确安装的 bug。

### 已知问题

- Zh-cn&platform 系统语言的问题阻止语音命令接受混合现实捕获或显示设备 IP 地址。
- 问题要求你在启动设备后启动 Cortana 应用以使用 "你好 Cortana" 语音激活。 如果从18362版本更新，你可能还会看到以前版本的 Cortana 应用的第二个应用磁贴，在 **开始**时不再有效。

## Windows 全息版 1903-五月2020更新 
- 内部版本18362.1061

此每月质量更新不包含任何显著的更改，因为团队正在处理 Windows 全息版本2004可能会更新，如前文所述。

## Windows 全息版 1903-2020 年4月更新
- 内部版本18362.1059

**支持的应用的深色模式** 

许多 Windows 应用均支持深色模式和浅色模式。 HoloLens 2 客户现在可以为支持两种配色方案的应用选择默认模式。 根据客户反馈，我们将默认应用模式设置为 "深色"，但你可以随时轻松地更改此设置：导航到 " **设置" > "系统 > 颜色** " 以找到 **"选择默认应用模式"。**

这些 "机箱中" 应用支持深色模式：
- “设置”
- Microsoft Store
- Mail
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
- 在使用 *HolographicDepthReprojectionMethod DepthReprojection* 算法时，在混合现实捕获中改进了全息图稳定性。
- 修复了32位 ARM 应用上的 "WinRT IStreamSocketListener API 类未注册" 错误。

## Windows 全息版、版本 1903-2020 更新 
- 内部版本18362.1056

更新中的改进和修复：

- 在使用 *HolographicDepthReprojectionMethod AutoPlanar* 算法时，在混合现实捕获中改进了全息图稳定性。
- 已确保连接到 depth MF 示例的坐标系与公共文档一致。
- 通过让客户通过 device portal 粘贴大量文本，提高了开发人员的工作效率。

## Windows 全息版 1903-2 月2020更新 
- 内部版本18362.1053

更新中的改进和修复：

- 已暂时禁用 Unity 应用程序的 UserPresence API HolographicSpace。 此更改避免了在面板翻转时导致某些应用暂停的问题，即使 "在后台运行" 设置也是如此。
- 修复了手动跟踪导致的随机 HUP 崩溃，在此情况下，用户注意到 UI 冻结，然后在几秒钟后返回到外壳。
- 改善了手动跟踪，以便在您用食指向您外出时，该手指的上半部分不太可能意外卷曲。
- 改进了 head 跟踪、空间映射和其他运行时的可靠性。

## Windows 全息版 1903-2020 更新 
- 内部版本18362.1043
 
更新中的改进和修复：

- 使用 HoloLens 2 模拟器时，改进了独占应用的稳定性。

## Windows 全息版 1903-2019 更新 
- 内部版本18362.1042

更新中的改进和修复：

- 引入了上一阶段复制 (LSR) 修复。 改进了全息图的视觉呈现，使其更准确地获得更稳定的深度。 如果应用未正确设置全息影像的深度，此更新后的症状将更明显。
- 固定应用和独占应用之间导航的固定稳定性。
- 解决了在设备处于待机状态几天后混合现实捕获无法录制视频的问题。
- 改进了全息图稳定性。

## Windows 全息版、版本 1903-2019 更新 
- 内部版本18362.1039

更新中的改进和修复：

- 固定的功能：在初始设置中为 en-us 和 en-us **选择** 语音命令。
- 改进了在最新的 Unity 和混合现实工具包中最远地放置的对象的视觉质量 (MRTK) 版本。
- 修复了在启动时，全息应用程序在处于暂停状态时处于暂停状态的问题，直到打开 "开始" 菜单，然后关闭。
- 适用于 HoloLens 2 和模拟器的 OpenXR 运行时一致性修复和改进。
