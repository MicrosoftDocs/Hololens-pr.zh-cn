---
title: HoloLens 2 发行说明
description: 随时了解每个新版本中HoloLens 2更新。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 06/17/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 1c0beed39fa6b4642a581da6baac44c732642e74d8b2c41ebca1b6d3f24b127d
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115663476"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 发行说明

为了确保你拥有高效体验，HoloLens设备，我们将继续发布功能、bug 和安全更新。 在此页上，可以看到每月HoloLens新增功能。 若要获取最新的 HoloLens 2更新，可以检查更新并手动更新[](hololens-update-hololens.md#check-for-updates-and-manually-update)，或获取完整闪存更新 (FFU) 通过高级恢复助手 来刷用[设备。](hololens-recovery.md#clean-reflash-the-device) [下载](https://aka.ms/hololens2download)会保持最新，并提供最新的已发布版本。

> [!NOTE]
> 最近的 Windows 11 公告侧重于 PC 版本的 Windows。 最近于 2021 年 5 月推出了 HoloLens 2 [主要 OS 更新](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067)，我们正在根据客户的反馈为今年秋季推出一个即将到来的版本。

> [!IMPORTANT]
> 由于[21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)版本中现在解决了影响 Remote Assist 用户的已知问题，我们暂时暂停了 Windows Holographic 版本 21H1 更新的提供。 我们还将默认的 Advanced Recovery Companion (ARC) 内部版本更改为[Windows Holographic 版本 20H2 – 2021](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)年 6 月更新。 ARC 生成现在将恢复面向 21H1 生成。

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows全息版 21H1 - 2021 年 7 月更新
- 内部版本 20348.1010

更新中的改进和修复：

- 设备门户在打开锁定文件时遇到问题文件资源管理器通知客户的方法。
- 现在，在所有受支持的浏览器中使用 https 时，文件上传、下载、重命名和删除已修复。
- 修复了Wi-Fi从 **设置 -> Network & Internet 启动** Wi-Fi 属性 UI 时无法保存>状态 -> 属性的问题。
- 解决了跨 OS 更新删除 eSIM 证书的问题。 此修补程序确保在更新到 21H1 版本时删除 eSIM 证书和相关组件。
- 更正了影响跨 OS 重置的预安装应用的问题。 
- 电池充电性能经过优化，在增加 CPU 负载的情况下增加运行时。

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows全息版 20H2 - 2021 年 7 月更新
- 内部版本 19041.1157

更新中的改进和修复：

- 设备门户在打开锁定文件时遇到问题文件资源管理器通知客户的方法。 
- 现在，在所有受支持的浏览器中使用 https 时，文件上传、下载、重命名和删除已修复。

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows全息版 21H1 - 2021 年 6 月更新
- 内部版本 20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive工作或学校相机照片上传

我们向 HoloLens 2 设置 应用添加了一项新功能，使客户能够自动将混合现实照片和视频从设备的"图片"> 相机"Roll 文件夹上传到相应的"OneDrive"工作或学校文件夹。 此功能解决了 HoloLens 2 上的[OneDrive](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos)应用中的功能差距，它仅支持自动将相机滚动上传到客户的个人Microsoft 帐户 (而不允许其工作或学校帐户) 。

**工作原理**

- 请访问 **设置 > System > 混合现实相机** 启用"相机上传"。
- 将此功能设置为"打开"位置后，捕获到设备的任何混合现实照片或视频将自动排队，以上传到工作或学校帐户的 OneDrive 的 Pictures > Camera Roll 文件夹。
    >[!NOTE]
    >启用此功能之前捕获的照片和视频不会排队等待上传，并且仍然需要手动上传。
- 当所有挂起设置文件已上传到 (时，OneDrive 页上的状态消息将显示挂起的文件数) 。
- 如果担心带宽或出于任何原因想要"暂停"上传，可以将该功能切换到"关闭 **"** 位置。 暂时禁用该功能可确保在将新文件添加到 Camera Roll 文件夹时上传队列将继续增加，但在重新启用该功能之前，文件不会上传。
- 最新文件将先上传 (最后一个，第一个上传) 。
- 例如，OneDrive帐户 (密码更改后 **) "立即** 修复"按钮会显示在设置页上。
- 没有最大文件大小，但请注意，上传大型文件 (尤其是当上传带宽受限时) 。 如果在上传大型文件时"暂停"或关闭上传，将保留部分上传。 如果在"暂停"或关闭后几个小时内重新启用上传，上传将继续从中断位置开始。 但是，如果在几个小时后重新启用上传，则大型文件的上传会从头开始重启。

**已知问题和注意事项**

- 此设置没有基于当前带宽使用情况的内置限制。 如果需要为其他方案最大化带宽，请手动关闭设置。 Upload将暂停，但该功能将继续监视新添加到相机滚动更新的文件。 准备好继续上传后，请重新启用上传。
- 必须为设备上每个用户帐户启用此功能，并且只能主动上传当前已登录到设备的用户的文件。
- 如果在实时观看 设置 页上的上传计数时拍摄照片或视频，请注意，在当前文件完成上传之前，挂起的文件计数可能不会更改。
- Upload设备睡眠或关机时，设备将暂停。 若要确保挂起的上传完成，请主动使用设备，直到 设置 页显示为"OneDrive"或调整 **Power &睡眠设置**。
### <a name="added-support-for-some-telemetry-policies"></a>添加了对某些遥测策略的支持

现在支持以下遥测策略HoloLens 2：
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry 和 System\ConfigureTelemetryOptInSettingsUx 应一起用于完全控制 设置 应用中的遥测和行为。

更新中的改进和修复：
- 使用颜色校准修复了主要视频损坏。
- 解决在"电源"菜单中可能会截断文本的问题。
- 启用对 RequirePrivateStoreOnly 策略的支持。

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows全息版 20H2 - 2021 年 6 月更新
- 内部版本 19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>添加了对某些遥测策略的支持

现在支持以下遥测策略HoloLens 2：
- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry 和 System\ConfigureTelemetryOptInSettingsUx 应一起用于完全控制 设置 应用中的遥测和行为。

我们建议你试用最新的内部版本，Windows全息版 21H1。

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows全息版 1903 - 2021 年 6 月更新
- 内部版本 18362.1116

更新中的改进和修复：
- 此每月质量更新不包含任何值得注意的更改，我们建议你试用我们的最新内部版本，Windows全息版 21H1。

>[!IMPORTANT]
> 将不再为此生成提供服务。

## <a name="windows-holographic-version-21h1"></a>Windows全息版 21H1
- 内部版本 20346.1002

此更新包含两个目标受众的功能;最终用户可在设备上由任何人使用的功能，以及 IT 管理员可配置的新设备管理选项。 下表指定与每个受众相关的功能。 如果你是 IT 管理员，请查看我们的 IT 管理员 [- 更新清单](#it-admin---update-checklist)。
>[!IMPORTANT]
>若要更新到此内部版本，HoloLens 2 设备 () 当前必须运行 2021 年 2 月更新 (内部版本 19041.1136) 或更高版本。 如果看不到此功能更新可用，请先更新设备，然后重试。

>[!NOTE]
>目前，Microsoft HoloLens 2 支持每月服务更新 (bug 和安全修复) 适用于以下版本：
>- WindowsHolographic 版本 20H2 (内部版本 19041.1128+) 
>- WindowsHolographic 版本 2004 (内部版本 19041.1103+) 
>- WindowsHolographic 版本 1903 (内部版本 18362+)  
>
> 随着 Holographic Windows 21H1 的推出，我们将停止为全息版本 **1903 Windows每月服务更新**。 这使我们能够专注于较新版本，并继续提供有价值的改进。 


| 功能名称                                              | 简短说明                                                                      | 目标读者 | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新Microsoft Edge](#introducing-the-new-microsoft-edge)  | 新的基于 Chromium 的 Microsoft Edge 现可用于HoloLens 2。 | 最终用户 | 
[WebXR 和 360 Viewer](#webxr-and-360-viewer) | 尝试沉浸式 Web 体验和 360 视频播放。 | 最终用户 | 
[新“设置”应用](#new-settings-app) | 旧版设置应用将被更新版本替换为新功能和设置。 | 最终用户 |
[显示颜色校准](#display-color-calibration) | 为 HoloLens 2 屏幕选择替代颜色配置文件。 | 最终用户 |
[默认应用选取器](#default-app-picker) | 选择应针对每个文件或链接类型启动的应用。 | 最终用户 |
[每个应用音量控制](#per-app-volume-control) | 独立于系统卷控制应用级别卷。 | 最终用户 |
[安装 Web 应用](#install-web-apps) | 使用新的 Microsoft Edge 浏览器在 HoloLens 2（如 Microsoft Office）上安装 Web 应用。 | 最终用户 |
[轻扫以键入](#swipe-to-type) | 使用手指的提示在全息键盘上"轻扫"单词。 | 最终用户 |
[“开始”中的 Power 菜单](#power-menu-from-start) | 在"开始"菜单上，重启并HoloLens设备。 | 最终用户 |
[登录屏幕上列出的多个用户](#multiple-users-listed-on-sign-in-screen) | 在"登录"屏幕上显示多个用户帐户。 | 最终用户 |
[USB-C 外置麦克风支持](#usb-c-external-microphone-support) | 将 USB-C 麦克风用于应用和/或Remote Assist。 | 最终用户 |
[展台的访问者自动登录](#visitor-auto-logon-for-kiosks) | 启用"访问者帐户"上的自动登录以用于展台模式。 | IT 管理员 |
[展台模式下的新应用的新 AUMID](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | 新应用和 Edge 设置 AUMID。 | IT 管理员 |
[改进了展台模式故障切换](#kiosk-mode-behavior-changes-for-handling-of-failures) | 展台模式在空的开始菜单之前查找"全局分配的访问权限"。 | IT 管理员 |
[页面和可见性的新设置值](#new-settings-uris-for-page-settings-visibility) | 20 多个新的 SettingsURIS，设置/PageVisibilityList 策略。 | IT 管理员 |
[配置回退诊断](#configuring-fallback-diagnostics-via-settings-app) | 在应用中设置回退设置行为。 | IT 管理员 |
[与附近的设备共享内容](#share-things-with-nearby-devices) | 将文件或 URL 从 HoloLens电脑。 | 全部 |
[新的 OS 诊断跟踪](#new-os-diagnostic-traces) | 操作系统更新设置中的新疑难解答。 | IT 管理员 |
[传递优化预览版](#delivery-optimization-preview) | 减少从多个设备下载的带宽HoloLens消耗。 | IT 管理员 |

请查看相关的发行说明：

- [访问 HoloLens Emulator 存档](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>新版 Microsoft Edge 简介

![旧版 Microsoft Edge 徽标动画升级为新版 Microsoft Edge 徽标动画](images/new-edge.gif)

新版 Microsoft Edge [采用 Chromium 开源项目](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/)，为客户提供更好的兼容性，同时为 Web 开发人员减少 Web 碎片。

> [!IMPORTANT]
> 新版 Microsoft Edge 会自动替换旧版 Microsoft Edge，新版本中[不再支持](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/)旧版 Microsoft Edge。

![新版 Microsoft Edge 屏幕截图](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>启动新版 Microsoft Edge

新的 Microsoft Edge ![新版 Microsoft Edge 图标](images/new_edge_logo.png) （由蓝绿色漩涡图标表示）固定在“开始”菜单上，并将在你激活 Web 链接时自动启动。

> [!NOTE]
> 首次在 HoloLens 2 上启动新版 Microsoft Edge 时，系统将从旧版 Microsoft Edge 导入你的设置和数据。 如果在启动新 Microsoft Edge后继续使用旧 Microsoft Edge，则新数据不会从旧 Microsoft Edge 同步到新Microsoft Edge。

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>为新版 Microsoft Edge 配置策略设置

相较于旧版 Microsoft Edge，新版 Microsoft Edge 在 HoloLens 2 上为 IT 管理员提供了一套更广泛的浏览器策略。

下面是一些有用的资源，可用于了解有关管理新版 Microsoft Edge 策略设置的详细信息：

- [使用 Microsoft Intune 配置 Microsoft Edge 策略设置](/deployedge/configure-edge-with-intune)
- [Microsoft Edge 旧版到 Microsoft Edge 策略映射](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome 到 Microsoft Edge 策略映射](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 完整的 [Microsoft Edge 企业版文档](/deployedge/)

> [!IMPORTANT]
> 由于新版 Microsoft Edge 支持的浏览器策略较多，我们的团队无法保证每个新策略都适用于 HoloLens 2。 但是我们已测试并已确认的是，新版 Microsoft Edge 在 HoloLens 2 上支持等效于以前在其上支持的每个旧版 Microsoft Edge 策略。 请参阅 [Microsoft Edge 旧版到 Microsoft Edge 策略映射](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)，查找与用于 HoloLens 2 的每个旧版 Microsoft Edge 浏览器策略等效的新版 Microsoft Edge 策略。
>
> 我们知道至少有两个新版 Microsoft Edge 策略无法用于 HoloLens 2：
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>在 HoloLens 2 上应用新版 Microsoft Edge 有哪些好处

由于新版 Microsoft Edge 是具有新的 UWP 适配器层的本机 Win32 应用程序，因此它可以在仅使用 UWP 的设备（如 HoloLens 2）上运行，某些功能可能还不能立即使用。 我们将在未来几个月内提供对新方案和功能的支持，敬请关注此板块的最新信息。

支持的场景和功能：
- 首次运行体验、登录到配置文件和同步
- 网站应呈现并按预期运行
- 大多数浏览器功能（收藏夹、历史记录等）都应按预期运行
- 深色模式
- 将 Web 应用安装到设备
- 安装扩展（如果使用的扩展在 HoloLens 2 上无法正常运行，请告知我们）
- 查看并标记 PDF
- 来自单个浏览器窗口的空间音效
- 自动和手动更新浏览器
- 从“打印”菜单保存 PDF（使用“保存到 PDF”选项）
- WebXR 和 360 Viewer 扩展
- 跨环境中的多个窗口浏览时，内容还原到正确的窗口

不支持的场景和功能：
- 带有同步音频流，来自多个窗口的空间音效
- “看到它，说出来”
- 打印

**浏览器已知问题排名前：**

- 全息键盘中的放大镜预览在新版 Microsoft Edge 中被禁用。 我们希望等放大功能恢复正常后，在未来的更新中重新启用此功能。
- 如果有其他浏览器窗口打开并处于活动状态，则音频可能会从错误的浏览器窗口播放。 通过关闭不应播放音频的其他活动窗口，可以解决此问题。
- 在"关注我"模式下从浏览器窗口播放 [音频时](hololens2-basic-usage.md#follow-me-stop-following)，如果禁用"关注我"模式，音频将继续播放。 可以通过在禁用"跟踪我"模式之前停止音频播放，或者使用 X 按钮关闭窗口来 **解决此问题** 。
- 与处于活动状态的 Microsoft Edge 窗口交互可能会导致其他 2D 应用程序窗口意外变为非活动状态。 可以通过再次与这些窗口交互重新将其激活。

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge Insider Channels

Microsoft Edge 团队为 Edge Insider 社区提供了三个预览渠道：Beta、Dev 和 Canary。 在 HoloLens 2 上安装预览渠道不会卸载已发布的 Microsoft Edge 版本，而且你可以同时安装多个渠道。 

请访问 [Microsoft Edge Insider 主页](https://www.microsoftedgeinsider.com)，了解有关 Edge Insider 社区的详细信息。 若要详细了解不同的 Edge Insider 渠道并开始体验，请访问 [Edge Insider 下载页面](https://www.microsoftedgeinsider.com/download)。

在 HoloLens 2 上安装 Microsoft Edge Insider Channels 有多种方法：

直接在设备上安装（当前仅适用于非托管设备）
  1. 在 HoloLens 2 上，访问 [Edge Insider 下载页面](https://www.microsoftedgeinsider.com/download)。
  1. 为想要安装的 Edge Insider 渠道选择“适用于 HoloLens 2 的下载”按钮。
  1. 从 Edge 下载队列或设备的“下载”文件夹（使用文件资源管理器）启动下载的 .msix 文件。
  1. 将启动[应用安装程序](app-deploy-app-installer.md)。
  1. 选择“安装”按钮。
  1. 安装成功后，你将在“开始”菜单的“所有应用”列表中找到以单独条目显示的 Beta、Dev 或 Canary。

**使用 Windows 设备门户通过电脑安装（需要在 HoloLens 2 上启用 [开发人员模式](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)）**
  1. 在你的电脑上，访问 [Edge Insider 下载页面](https://www.microsoftedgeinsider.com/download)。
  1. 为想要安装的 Edge Insider 渠道选择“适用于 Windows 10 的下载”旁的下拉箭头按钮。
  1. 在下拉菜单中选择“HoloLens 2”。
  1. 将 .msix 文件保存到电脑的“下载”文件夹（或便于你查找的其他文件夹）。
  1. 在电脑上使用 [Windows 设备门户](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)将下载的 .msix 文件安装到 HoloLens 2 上。
  1. 安装成功后，你将在“开始”菜单的“所有应用”列表中找到以单独条目显示的 Beta、Dev 或 Canary。

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>使用 WDAC 阻止新版 Microsoft Edge

对于希望更新其 [WDAC 策略](windows-defender-application-control-wdac.md)以阻止新版 Microsoft Edge 应用的 IT 管理员，需要向策略添加以下内容。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>管理新版 Microsoft Edge 的终结点

某些环境可能需要考虑网络限制。 为了确保在使用新版 Edge 时获得流畅的体验，请[启用这些 Microsoft 终结点。](/deployedge/microsoft-edge-security-endpoints)

阅读有关当前可用的 [HoloLens 终结点](hololens-offline.md)的详细信息。

### <a name="install-web-apps"></a>安装 Web 应用
 > [!Note]
>从 [Windows 全息版（版本 21H1）](hololens-release-notes.md#windows-holographic-version-21h1)开始，将不再预安装 Office Web 应用。

你可以使用新版 Edge 将 Web 应用与 Microsoft Store 应用一起安装。 例如，可以安装 Microsoft Office Web 应用来查看和编辑托管在 SharePoint 或 OneDrive 上的文件。 若要安装 Office Web 应用，请访问 https://www.office.com 并在地址栏中选择“可用应用”或“安装 Office”。 选择“安装”确认该操作。

> [!IMPORTANT]
> 仅当 HoloLens 2 具有活动的 Internet 连接时，Office Web 应用功能才可用。

### <a name="webxr-and-360-viewer"></a>WebXR 和 360 Viewer

新版 Microsoft Edge 包含对 WebXR 的支持，这是创建沉浸式 Web 体验的新标准（替代 WebVR）。 许多沉浸式 Web 体验在设计时都考虑了 VR 应用场景（它们用虚拟环境来替代你的视野），但 HoloLens 2 也支持这些体验。 WebXR 标准还支持使用物理环境的增强和混合现实沉浸式 Web 体验。 随着 WebXR 在开发人员中的应用逐渐普及，我们预计未来将有新的增强和混合现实沉浸式体验供 HoloLens 2 客户尝试！

360 Viewer 扩展是在 WebXR 的基础之上构建的，它随新版 Microsoft Edge 一起自动安装在 HoloLens 2 上。 该网络扩展使你能够沉浸在 360 度视频中。 YouTube 上提供的 360 度视频选择范围最多，我们建议你从该平台开始体验。

#### <a name="how-to-use-webxr"></a>如何使用 WebXR

1. 导航到支持 WebXR 的网站。
1. 选择网站上的“进入 VR”。 此按钮的位置和视觉表现形式可能因网站而异，但其外观可能类似于：

    ![“进入 VR”按钮示例](images/75px-enter-vr.png)

1. 首次尝试在特定域上启动 WebXR 体验时，浏览器将询问你是否同意进入沉浸式视图，选择“允许”。
1. 使用 [HoloLens 2 手势](hololens2-basic-usage.md#the-hand-tracking-frame)来操作体验。
1. 如果在体验时没有“退出”按钮，请使用[开始手势](hololens2-basic-usage.md#start-gesture)返回主菜单。

建议的 WebXR 示例
- 360 Viewer（参阅下一部分）
- [XR Dinosaurs](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR Paint](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>如何使用 360 Viewer

1. 在 YouTube 上导航到 360 度视频。
1. 在视频帧中，选择“混合现实头戴显示设备”按钮：

    ![激活 360 Viewer 的按钮](images/enter-360-viewer.jpg)

1. 首次尝试在特定域上启动 360 Viewer 时，浏览器将询问你是否同意进入沉浸式视图。 选择“允许”。
1. [隔空敲击](hololens2-basic-usage.md#select-using-air-tap)以打开播放控件。 使用[手部射线和隔空敲击](hololens2-basic-usage.md#select-using-air-tap)来播放/暂停、快进/后退、打开/关闭字幕或停止体验（该操作会退出沉浸式视图）。 播放控件将在保持几秒的非活动状态后消失。

#### <a name="top-webxr-and-360-viewer-known-issues"></a>WebXR 和 360 Viewer 常见已知问题
- 根据 WebXR 体验的复杂度，帧速率可能下降或卡顿。
- 默认情况下，WebXR 中不支持铰接式手关节。 开发人员可以通过打开"WebXR 手部输入" `edge://flags` 来启用支持。
- YouTube 网站之外的 360 度视频可能无法按预期运行。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>提供关于 WebXR 和 360 Viewer 的反馈

请通过新版 Microsoft Edge 中的“发送反馈”功能与我们的团队分享反馈和错误。

### <a name="new-settings-app"></a>新“设置”应用

在此版本中，我们将引入新版本的 设置 应用。 新的“设置”应用包括 HoloLens 2 在以下领域的新功能和扩展设置：声音、电源和休眠、网络和 Internet、应用、帐户、轻松访问等。

> [!NOTE]
> 由于新的“设置”应用不同于旧版“设置”应用，因此，此前围绕环境放置的任何“设置”窗口都将在更新时删除。

![新“设置”应用主页](images/new-settings-app.png)

**新功能和设置**
- 设置搜索：使用关键字或设置名称搜索“设置”主页中的设置。
- 系统> 声音：
  - 输入和输出音频设备：独立选择输入和输出音频设备（例如，通过蓝牙耳机侦听音频，或使用 USB-C 麦克风进行音频输入）。
    > [!NOTE]
    > HoloLens 2 不支持蓝牙麦克风。
  - 应用音量：独立调整每个应用的音量。 请参阅[每个应用的音量控制](#per-app-volume-control)。
- 系统 > 电源和休眠：如果希望设备在一段时间不活动后进入休眠状态时选择此选项。
- 系统 > 电池：手动启用节电模式或设置节电模式模式自动打开的电池阈值。
- 设备 > USB：默认禁用 USB 连接。
- 网络和 Internet：
  - USB-C 以太网适配器将出现在“网络和 Internet”中。
  - USB-C 以太网适配器设置现已可用，包括其 IP 地址。
  - 现在可以在 HoloLens 2 上启用飞行模式。
- 应用：可以重置用于文件和链接类型的默认应用。 有关详细信息，请参见[默认应用选取器](#default-app-picker)。
- 帐户 > 其他用户：设备所有者可以添加用户、将标准用户升级到设备所有者、将设备所有者降级为标准用户以及删除用户。
- 轻松访问：更改文本大小和一些视觉效果。

**已知问题**
- 将删除之前放置的“设置”窗口（请参见上面的注释）。
- 无法再使用“设置”应用重命名设备。 IT 管理员可以使用[适用于 HoloLens 2 的 Windows Autopilot](hololens2-autopilot.md) 设备名称模板或 MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 节点来重命名设备。
- “以太网”页随时显示一个虚拟以太网设备（“UsbNcm”）。
- 新 Microsoft Edge 的电池使用情况可能不准确，因为它是一个由 UWP 适配器层支持的 Win32 桌面应用程序（预计近期不会有任何修复）。

#### <a name="display-color-calibration"></a>显示颜色校准



使用此新设置，可以为 HoloLens 2 显示选择备用颜色配置文件。 这可以帮助显示更准确的颜色，尤其是在较低的屏幕亮度级别。 可以在 "系统 > 校准" 页上的 "设置应用" 中找到显示颜色校准。

> [!NOTE]
> 由于此设置将新的颜色配置文件保存到屏幕固件，因此它是每个设备的设置（并且对每个用户帐户不是唯一的）。

##### <a name="how-to-use-display-color-calibration"></a>如何使用显示颜色校准

1. 启动“设置”应用，导航到“系统”>“校准”。
1. 在“显示颜色校准”下，选择“运行显示颜色校准”按钮。
1. 将启动显示颜色校准体验，并建议你确保面罩的位置正确。
1. 在继续执行指令对话框后，屏幕将自动调暗到 30% 的亮度。
    > [!TIP]
    > 如果你在环境中看不清昏暗的场景，可以使用设备左侧的亮度按钮手动调整 HoloLens 2 的亮度级别。
1. 选择按钮 1-6 可立即尝试每个颜色配置文件，并找到最适合你的眼睛的颜色配置文件（这通常意味着可帮助最中性地显示场景的配置文件，并且灰度模式和肤色符合预期。）

    ![显示颜色校准场景](images/color-cal-ui.png)
    
1. 当你对所选配置文件感到满意，选择“保存和退出”按钮
1. 如果你不想进行更改，请选择“取消并退出”按钮，更改将恢复

> [!TIP]
> 下面是使用显示颜色校准设置时需要注意的一些有用的提示：
> - 你可以根据需要在“设置”中重新运行显示颜色校准
> - 如果设备上的任何人以前使用了设置来更改颜色配置文件，则最近更改的日期/时间将反映在“设置”页面上
> - 重新运行显示颜色校准时，将突出显示以前保存的颜色配置文件，并且不会显示配置文件 0（因为配置文件 0 表示屏幕的原始颜色配置文件）
> - 如果要恢复到屏幕的原始颜色配置文件，可从“设置”页面执行此查找（参阅[如何重置颜色配置文件](#how-to-reset-color-profile)）

##### <a name="how-to-reset-color-profile"></a>如何重置颜色配置文件 

如果你对保存到 HoloLens 2 中的自定义颜色配置文件不满意，则可以还原设备的原始颜色配置文件：
1. 启动“设置”应用，导航到“系统”>“校准”。
1. 在“显示颜色校准”下，选择“重置为默认颜色配置文件”按钮。
1. 当对话框打开时，如果已准备好重新启动 HoloLens 2 并应用所做的更改，请选择“重新启动”。

#### <a name="top-display-color-calibration-known-issues"></a>顶部显示颜色校准已知问题

- 在 "设置" 页上，通知您上次更改颜色配置文件的状态字符串将过期，直到您重新加载设置的该页面为止。
    - 解决方法：选择另一个“设置”页面，然后重新选择“校准”页面。

#### <a name="default-app-picker"></a>默认应用选取器

当你激活超链接或打开具有多个已安装的应用程序的文件类型（该应用程序支持该类型）时，你将看到一个新窗口打开，提示你选择哪个已安装的应用程序应处理文件或链接类型。 在该窗口中，还可以选择选定的应用“一次”或“始终”处理文件或链接类型。

如果选择“始终”，但以后想要更改处理特定文件或链接类型的应用，可以在“设置”>“应用”中重置设置默认值。 滚动到页面底部，然后选择“文件类型的默认应用”和/或“链接类型的默认应用”下的“清除”按钮。 与台式电脑类似设置不同的是，无法重置单个文件类型默认值。

#### <a name="per-app-volume-control"></a>每个应用音量控制

现在，在此 Windows 生成中，用户可以手动调整每个应用的音量级别。 这样，用户可以更好地关注他们所需要的应用，或者在使用多个应用时能更清晰地听到。 例如，在呼叫另一个人寻求远程帮助时降低其中一个应用的音量。

若要设置单个应用的音量，请导航到“设置” -> “系统” -> “声音”，然后在“高级”声音选项中选择“应用音量和设备首选项”。<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>轻扫以键入

有些客户通过轻扫要键入的单词的形状，来更快地在虚拟键盘上 "键入"，并且我们正在为全息键盘预览此功能。 您可以通过在全息键盘的平面上传递手指的笔尖，刷一字的形状，然后从键盘飞机取出手指的笔尖，一次轻扫一个词。 通过在键盘上删除单词之间的手指，无需按删除键就可以轻扫后面的单词。 如果在键盘上看到轻扫轨迹按照手指移动，你将知道该功能正在运作。

请注意，由于全息键盘的性质，如果不能感觉到手指的阻力（不像手机显示一样），该功能使用和掌握起来可能比较麻烦。 

### <a name="power-menu-from-start"></a>“开始”中的 Power 菜单

通过新菜单，用户可以注销、关闭和重启设备。 HoloLens“开始”屏幕中的指示器显示系统更新何时可用。

#### <a name="how-to-use"></a>如何使用

1. 使用[“开始”手势](hololens2-basic-usage.md#start-gesture)或说出“转到开始”来打开 HoloLens“开始”屏幕。

2. 请注意用户个人资料图片旁边的省略号图标 (...)：<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 使用手或语音命令“Power”选择用户个人资料图片。

4. 将显示包含“注销”、“重启”或“关闭”设备选项的菜单：<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. 选择菜单选项以注销、重启或关闭 HoloLens。 如果将设备设置为[单个 Microsoft 帐户 (MSA) 或本地帐户](hololens-identity.md)，“注销”选项可能不可用。

6. 通过触摸其他任意位置或关闭具有“开始”手势的“开始”菜单来关闭菜单。

#### <a name="update-indicator"></a>更新指示器

当更新可用时，省略号图标会亮起，指示重新启动将会安装更新。菜单选项还会更改，以反映更新的状态。<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>登录屏幕上列出了多个用户

以前的登录屏幕只显示最近登录的用户，以及 "其他用户" 入口点。 如果有多个用户登录到设备，我们已收到客户反馈。 它们仍需要重新键入其用户名等。

此 Windows 生成中引入了 "其他用户"，当选择位于 "PIN 输入" 字段右侧的 **其他用户** 时，登录屏幕将显示多个以前登录到设备的用户。 这允许用户选择其用户配置文件，然后使用其 Windows Hello 凭据进行登录。 还可以通过 " **添加帐户** " 按钮将新用户添加到该设备。

在 "其他用户" 菜单中，"其他用户" 按钮将显示最后一个登录到设备的用户。 选择此按钮可返回到此用户的登录屏幕。

![登录屏幕默认值](./images/multiusers1.jpg)

<br>

![其他用户登录屏幕](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 外置麦克风支持

> [!IMPORTANT]
> 插入 **USB 麦克风不会自动将其设置为输入设备**。 当插入一组 USB-C 耳机时，用户将看到耳机音频将自动重定向到耳机，但 HoloLens OS 会将内部麦克风阵列的优先级设置为任何其他输入设备的优先级。 若要使用 USB-C 麦克风，请执行以下步骤。

用户可以使用“声音”设置面板选择 USB-C 连接的外置麦克风。 USB-C 麦克风可用于呼叫、录制等。

打开“设置”应用并选择“系统” > “声音”。

![声音设置](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 若要将外置麦克风用于 Remote Assist，用户需要单击“管理声音设备”超链接。
>
> 然后，使用下拉菜单将外置麦克风设置为“默认值”或“通信默认值”。 选择“默认值”表示将在任何位置使用外置麦克风。
>
> 选择“通信默认值”表示将在 Remote Assist 和其他通信应用中使用外置麦克风，但 HoloLens 麦克风阵列仍可用于其他任务。

![管理声音设备](images/usbc-mic-2.png)

<br>

![设置麦克风默认值](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support&quot;></a>蓝牙麦克风支持怎么样？

遗憾的是，HoloLens 2 当前不支持蓝牙麦克风。

#### <a name=&quot;troubleshooting-usb-c-microphones&quot;></a>USB-C 麦克风疑难解答

请注意，某些 USB-C 麦克风会错误地将自身报告为麦克风 *和* 扬声器。 这是麦克风问题，而不是 HoloLens。 将其中一个麦克风插入 HoloLens 时，可能会丢失声音。 幸运的是，有一个简单的修补程序。  

在 **设置**  ->  **系统**  ->  **声音**&quot;中，将内置扬声器 **(模拟功能音频驱动程序")** 为 **默认设备**。 即使稍后会删除并重新连接麦克风，HoloLens 也应记住此设置。

![USB-C 麦克风疑难解答](images/usbc-mic-4.png)

### <a name="visitor-auto-logon-for-kiosks"></a>网亭的访问者自动登录

这项新功能使访问者帐户上的自动登录可用于展台模式。

对于非 AAD 配置，为访问者自动登录配置设备：

1. 创建一个预配包，其中：
    1. 将 **运行时设置 AssignedAccess** 配置为允许访问者帐户。
    1. （可选）在 MDM **(运行时设置/工作区/注册)** 中注册设备，以便以后可以对其进行管理。
    1. 不创建本地帐户
1. [应用设置包](hololens-provisioning.md)。

对于 AAD 配置，用户可以立即获得类似于此的内容，而无需进行此更改。 为展台模式配置的 AAD 加入设备可以通过在登录屏幕上点击一次按钮，登录访问者帐户。 登录到访问者帐户后，在从 "开始" 菜单中显式注销访问者或重新启动设备之前，该设备将不会提示登录。

可以通过 [自定义 OMA URI](/mem/intune/configuration/custom-settings-windows-10) 策略来管理访问者自动登录：

- URI 值：./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| 策略  | 描述   | 配置  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | 允许访问者自动登录到展台   | 1 (是) ，0 (否，默认值为 )   |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>在展台模式下使用新的设置和边缘应用

当在 [网亭](hololens-kiosk.md)中包含应用时，IT 管理员通常会将该应用添加到展台，但使用其应用用户模型 ID (AUMID) 。 由于设置应用和 Microsoft Edge 应用都被视为新应用，并且与将 AUMIDs 用于这些应用的早期应用亭不同，因此需要将其更新为使用新的 AUMID。

修改展台以包含新应用时，建议添加新的 AUMID，并保留旧的应用。 这会在用户更新操作系统时创建轻松转换，而无需接收新策略，即可继续使用展台。

| 应用                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 旧设置应用       | HolographicSystemSettings_cw5n1h2txyewy！应用            |
| 新建设置应用       | BAEAEF15-9BAB-47FC-ACECAD2AE94B_cw5n1h2txyewy 800B！应用 |
| 旧 Microsoft Edge 应用 | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新建 Microsoft Edge 应用 | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>用于处理故障的展台模式行为更改

在较旧的版本中，如果设备具有展台配置（这是全局分配的访问和 AAD 组成员分配的访问权限），则如果确定 AAD 组成员身份失败，用户将看到 "不[在启动时显示任何内容](hololens-kiosk.md#kiosk-mode-behavior-changes-for-handling-of-failures)" 菜单。

从此 Windows 版开始，kiosk 体验将回退到全局展台配置 (如果在 AAD 组展台模式发生故障时存在) 。

### <a name="new-settings-uris-for-page-settings-visibility"></a>页面设置可见性的新设置 uri

在[Windows 全息版20H2 中，](hololens-release-notes.md#windows-holographic-version-20h2)我们添加了[设置/PageVisibilityList 策略](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)，以限制在设置应用程序中显示的页面。 PageVisibilityList 是一项策略，它允许 IT 管理员阻止查看或访问“系统设置”应用中的特定页面，或者对除指定页面之外的所有页面执行此操作。

如果访问[页面设置可见性](settings-uri-list.md)，则可以找到使用此 CSP 的说明，以及以前版本中可用的 uri 列表。

我们将扩展可用设置 uri 的列表，管理员可以管理此列表。 其中一些 Uri 适用于新的设置应用内的新可用区域。 如果使用设置/PageVisibilityList 策略，请查看以下列表，并根据需要调整允许或阻止的页面。

> [!NOTE]
> **弃用： ms 设置：网络代理**
>
> 在这些较新的版本中不推荐使用一个设置页。 旧的 **网络 & Internet**  >  **代理** 页面不再作为全局设置提供。 新的每连接代理设置可在 **网络 & internet**  >  **wi-fi**  >  **属性** 或 **网络 & internet**  >  **以太网**  >  **属性** 下找到。

<br>

| “设置”页面                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| 应用 > 应用 & 功能                               | `ms-settings:appsfeatures`                         |
| 应用 > 应用 & 功能 > 高级选项          | `ms-settings:appsfeatures-app`                     |
| 脱机地图 > 应用                                  | `ms-settings:maps`                                 |
| 应用 > 脱机地图 > 下载地图                  | `ms-settings:maps-downloadmaps`                    |
| 设备 > 鼠标                                      | `ms-settings:mouse`                                |
| 设备 > USB                                        | `ms-settings:usb`                                  |
| 网络 & Internet > 飞行模式                   | `ms-settings:network-airplanemode`                 |
| 隐私 > 常规                                    | `ms-settings:privacy-general`                      |
| 隐私 > 墨迹 & 键入个性化             | `ms-settings:privacy-speechtyping`                 |
| 隐私 > 动作                                     | `ms-settings:privacy-motion`                       |
| 隐私 > 屏幕快照边框                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| 隐私 > 屏幕截图和应用                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| 系统 > 电池                                     | `ms-settings:batterysaver`                         |
| 系统 > 电池                                     | `ms-settings:batterysaver-settings`                |
| 系统 > 声音                                       | `ms-settings:sound`                                |
| 系统 > 声音 > 应用卷和设备首选项 | `ms-settings:apps-volume`                          |
| 系统 > 声 > 管理声音设备              | `ms-settings:sound-devices`                        |
| 系统 > 存储 > 配置存储感知         | `ms-settings:storagepolicies`                      |
| 时间 & 语言 > 日期 & 时间                        | `ms-settings:dateandtime`                          |
| > 键盘的时间 & 语言                           | `ms-settings:keyboard`                             |
| > 语言 & 语言                           | `ms-settings:language`                             |
| > 语言 & 语言                           | `ms-settings:regionlanguage-languageoptions`       |
| 更新 & 安全 > 重置 & 恢复               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>已更新 Uri

以前，以下两个 Uri 不会直接将用户带到所指示的页面，而只会阻止主更新页面。 以下项已更新为定向到其页面：

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>通过设置应用配置回退诊断

现在，在设置应用中，用户可以配置[回退诊断](hololens-diagnostic-logs.md)的行为。 在设置应用中，导航到 "**隐私**  ->  **故障排除**" 页以配置此设置。

> [!NOTE]
> 如果为设备配置了 MDM 策略，则用户将无法重写该行为。  

### <a name="share-things-with-nearby-devices"></a>与附近设备共享东西

Windows 10 设备（包括电脑和其他 HoloLens 2 设备）与附近共享东西。 你可以在 **设置**  ->  **系统**  ->  **共享体验** 中试用它，以将文件或 url 从 HoloLens 共享到 PC。 有关更多详细信息，请参阅有关如何[在 Windows 10 中与附近设备共享内容](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)的详细信息。

此功能可通过 [连接/AllowConnectedDevices](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)进行管理。

### <a name="new-os-diagnostic-traces"></a>新操作系统诊断跟踪

除了设置应用中以前的疑难解答外，还添加了新的疑难解答，并添加了新的设置应用以进行操作系统更新。 导航到 **设置**  ->  **更新 &amp; 安全**  >  **疑难解答**  >  **Windows 更新** 并选择 "**启动**"。 这样，你就可以收集跟踪，同时在操作系统更新中重现你的问题，以帮助更好地帮助你的 IT 或支持人员进行故障排除。

### <a name="delivery-optimization-preview"></a>传递优化预览版

使用此 HoloLens 更新时，Windows Holographic for Business 启用 "传递优化" 设置，以减少从多个 HoloLens 设备下载的带宽消耗。 此处提供了此功能的更完整说明以及建议的网络配置：[Windows 10 更新的传递优化](/windows/deployment/update/waas-delivery-optimization)。

以下设置作为管理图面的一部分启用，并且[可以从 Intune 进行配置](/mem/intune/configuration/delivery-optimization-settings)：

- [DOCacheHost](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

有关此预览版产品/服务的一些注意事项：

- 此预览版中的 HoloLens 支持仅限于 OS 更新。
- Windows Holographic for Business 仅支持 HTTP 下载模式并从 [Microsoft 联网缓存终结点](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)进行下载；目前，HoloLens 设备不支持对等下载模式和组分配。
- HoloLens 不支持 Windows Server Update Services 终结点的部署或传递优化。
- 故障排除将需要对联网缓存服务器进行诊断，或通过“设置” > “更新和安全” >  “故障排除” >  “Windows 更新”在 HoloLens 上收集跟踪。

### <a name="it-admin---update-checklist"></a>IT 管理员 - 更新清单

此清单将帮助你了解在此功能更新中添加的可能影响当前设备管理配置的新功能，或者你可能想要开始使用的新功能。

#### <a name="updates-to-kiosk-mode"></a>展台模式的更新

✔️ [**展台模式下的新应用新建 AUMID：**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

如果以前在展台设置或 Microsoft Edge应用，我们将这些应用替换为使用不同的应用 ID 的新应用。 强烈建议阅读下面的展台模式下的新[应用的新 AUMID。](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 这将确保你继续在展台设置应用，或包括新的 Microsoft Edge 应用。 现在可以完成这些更改，并部署到所有设备，并允许在更新时更顺畅地转换。

✔️ [**展台的访问者自动登录：**](#visitor-auto-logon-for-kiosks) 

访问者现在可以自动登录到展台。 默认情况下，此行为处于启用状态，但可以管理和禁用。

✔️ [**改进的展台模式故障切换**](#kiosk-mode-behavior-changes-for-handling-of-failures)：

如果未成功确定已登录 AAD 用户的 AAD 组成员身份，则全局展台配置用于开始菜单 (如果存在) 则向用户显示空的开始菜单。 虽然空的开始菜单不是可直接设置的配置，但如果使用的是展台，则此新处理可能会通知支持部门，因为这可能适用于配置，或者你可能希望对分配的访问配置进行新的调整。

#### <a name="updates-to-page-settings-visibility"></a>页面和可见性设置更新

✔️ [**页面设置可见性的新 设置 URI**](#new-settings-uris-for-page-settings-visibility)

如果当前[正在使用"页面](settings-uri-list.md)设置可见性"，可能需要调整已允许或阻止的现有 URI。

#### <a name="updates-for-your-wdac-policy"></a>WDAC 策略的更新
✔️如果以前阻止通过 WDAC Microsoft Edge，需要更新 WDAC 策略。 请查看以下内容并使用提供的示例代码。
#### <a name="enable-new-endpoints-for-edge"></a>为 Edge 启用新终结点
✔️如果基础结构涉及配置网络终结点（如代理或防火墙），请为新的应用启用Microsoft Edge终结点。

#### <a name="newly-configurable-items"></a>新可配置的项

✔️ [配置回退诊断](#configuring-fallback-diagnostics-via-settings-app)：可以配置是否收集回退诊断以及收集回退诊断的人。

✔️[附近设备](#share-things-with-nearby-devices)共享内容：可以禁用新的附近共享功能。

✔️[配置新应用的策略Microsoft Edge：](#configuring-policy-settings-for-the-new-microsoft-edge)查看可用于新Microsoft Edge。

#### <a name="new-diagnostic-tool"></a>新的诊断工具

✔️新的[OS 诊断跟踪：](#new-os-diagnostic-traces)收集与 OS 更新相关的日志。

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：

- [脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics) 还将包含序列号和 OS 版本的其他设备信息。
- 修复了通过运行时预配包部署业务线应用程序的问题。
- 修复了有关业务线应用程序安装状态报告的问题。
- 修复了跨设备重置新应用包的持久性问题。
- 修复了可能导致在 Edge 中为日本客户键入错误符号的问题。
- 提高预安装应用（如 Edge）上的 OS 更新的复原能力。 
- 解决影响应用程序安装的更新可靠性Microsoft Edge。 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows全息版 20H2 - 2021 年 5 月更新
- 内部版本 19041.1146

更新中的改进和修复：
- 此每月质量更新不包含任何值得注意的更改，我们建议你试用我们的最新内部版本，Windows全息版 21H1。

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows全息版 1903 - 2021 年 5 月更新
- 内部版本 18362.1110

更新中的改进和修复：
- 此每月质量更新不包含任何显著更改。 **此生成将不再接收每月服务更新**。 我们建议你试用最新的内部版本，Windows全息版 21H1。



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows全息版 20H2 - 2021 年 4 月更新
- 内部版本 19041.1144

更新中的改进和修复：

- 修复了有关业务线应用程序安装状态报告的问题。

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows全息版 1903 - 2021 年 4 月更新
- 内部版本 18362.1108

更新中的改进和修复：

- 解决了尝试更改设置帐户的密码时，应用崩溃的问题。


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows全息版 20H2 - 2021 年 3 月更新
- 内部版本 19041.1140

更新中的改进和修复：

- 使用 AdvancedPhotoCapture 或 LowLagPhotoCapture 通过 HoloLens 2 捕获照片的客户现在可以在捕获照片后最多 3 秒检索相机姿势。
- 修复了服务中的设备门户泄漏，该问题导致服务的内存使用量增加，导致其他应用程序无法分配内存。
- 修复了在"分步推出"中注册的用户无法登录到设备的问题。

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows全息版 1903 - 2021 年 3 月更新
- 内部版本 18362.1102

更新中的改进和修复：

- 修复了服务中的设备门户泄漏，该问题导致服务的内存使用量增加，导致其他应用程序无法分配内存。

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows全息版 20H2 - 2021 年 2 月更新
- 内部版本 19041.1136

更新中的改进和修复：

- 修复了有关初始设备设置和存储应用更新的问题。
- 解决有关升级和航班的问题，供HoloLens版本。
- 从设备中删除了 eSIM 根存储中未使用的预HoloLens证书。

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows全息版 1903 - 2021 年 2 月更新
- 内部版本 18362.1098

此每月质量更新不包含任何值得注意的更改，建议试用 Holographic 版本 2004 Windows的最新内部版本。

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows全息版 20H2 - 2021 年 1 月更新
- 内部版本 19041.1134

更新中的改进和修复：

- 改进了在设备上有许多用户时启动、恢复和用户切换期间的性能。
- 添加了对研究模式 的 arm32 [支持](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)。

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows全息版 1903 - 2021 年 1 月更新
- 内部版本 18362.1091

此每月质量更新不包含任何值得注意的更改，建议试用 Holographic 版本 2004 Windows的最新内部版本。

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows全息版 20H2 - 2020 年 12 月更新
- 内部版本 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>通过 应用安装程序 在 HoloLens 2 安装应用

我们 **添加了一项新功能 (应用安装程序) ，** 让你能够更无缝地在 HoloLens 2 设备上安装应用程序。 对于非 **托管设备，此功能默认为打开状态**。 为了防止企业中断，应用安装程序 **目前不适用于托管** 设备。  

如果以下任一情况 **成立，则** 设备被视为"托管"设备：
- MDM [已注册](hololens-enroll-mdm.md)
- 配置了 [预配包](hololens-provisioning.md)
- 用户 [标识](hololens-identity.md) Azure AD

现在可以安装应用，而无需启用开发人员模式或设备门户。  只需 (USB 或 Edge) Appx 捆绑包下载到设备，然后导航到 文件资源管理器 中的 Appx 捆绑包，以提示你启动安装。  或者， [从网页 启动安装](/windows/msix/app-installer/installing-windows10-apps-web)。  与从 Microsoft Store 安装的应用或使用 MDM 的 LOB 应用部署功能旁加载的应用一样，应用需要使用签名工具进行数字签名[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)，并且用于签名[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)的证书必须受 HoloLens 设备信任，然后才能部署应用。

**应用程序安装说明。**

1.  确保设备未被视为托管设备
1.  确保 HoloLens 2设备已打开并连接到电脑
1.  确保已登录到 HoloLens 2 设备
1.  在电脑上导航到自定义应用，将 yourapp.appxbundle 复制到 yourdevicename\Internal 存储\Downloads。   复制完文件后，可以断开设备连接
1.  从HoloLens 2打开"开始"菜单，选择"所有应用"并启动文件资源管理器应用。
1.  导航到"下载"文件夹。 可能需要先在应用的左侧面板中选择"此设备"，然后导航到"下载"。
1.  选择 yourapp.appxbundle 文件。
1.  系统应用安装程序启动。 选择"安装"按钮以安装应用。
安装完成后，已安装的应用将自动启动。

可以在通用示例Windows[上](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)GitHub应用来测试此流。

阅读有关使用 HoloLens 2 在 应用安装程序[安装应用的完整过程](app-deploy-app-installer.md)。  

![通过 应用安装程序 安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：

- 手部跟踪现在在许多以前丢失手部的新情况下保持跟踪。  在某些新情况下，只有手部位置会继续根据用户的实际手部进行更新，而其他连接则根据以前的姿势进行推断。  此更改有助于提高动作（如击球、引发、跳跃和击球）的跟踪一致性。  它还有助于手靠近表面或持有对象的情况。  在推断手部时 [，每个联合](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) 准确度值将设置为"近似"，而不是"高"。
- 修复了帐户的 PIN 重置Azure AD显示错误"出现问题的问题。
- 启动 ET、设置应用中的 Iris、新用户或通知 toast 时，用户应看到更少的启动后 OOBE 故障。
- 用户应具有来自 OOBE 的正确时区。

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows全息版 1903 - 2020 年 12 月更新
- 内部版本 18362.1088

此每月质量更新不包含任何值得注意的更改，建议试用最新的 Windows Holographic 版本 20H2 – 2020 年 12 月更新，以及生成中添加的新 应用安装程序 功能。


## <a name="windows-holographic-version-20h2"></a>Windows全息版 20H2
- 内部版本 19041.1128

Windows全息版 20H2 现已发布，为用户和 IT 专业人员HoloLens 2一系列新功能。 从自动眼定位到 设置 中的证书管理器，改进的展台模式功能和新的 Autopilot 设置功能。 此新更新使 IT 团队能够更精细地控制如何配置HoloLens设备，并为用户提供更无缝的全息体验。 

此最新版本是版本 2004 的每月更新，但这次我们将包含新功能。 主内部版本号将保持不变，Windows更新将指示每月发布版本 2004 (内部版本 19041) 。 可以在"关于"屏幕中查看设置 >号，以确认你位于最新的可用内部版本 19041.1128+ 上。 若要更新到最新版本，请打开 设置 应用，转到"更新&安全性"，然后点击"检查更新"。 若要详细了解如何管理更新HoloLens，请访问[管理HoloLens更新](hololens-updates.md)。

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Holographic 版本 20H2 Windows新增功能  

| 功能                                              | 说明                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [自动眼部位置支持](hololens-release-notes.md#auto-eye-position-support) | 主动计算眼睛位置，用户无需经过眼动跟踪校准。   |
| [证书管理器](hololens-release-notes.md#certificate-manager)   | 允许使用更简单的新方法来安装和删除应用设置证书。     |
| [从 USB 自动启动预配](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB 驱动器上的预配包会自动提示 OOBE 中的预配页。                                                         |
| [在 OOBE 中自动确认预配包](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 预配包会在 OOBE 期间从预配页自动应用。                                                         |
| [无需使用 UI 即可自动预配](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 如何将预配自动启动和自动确认组合在一起。 |
| [将 Autopilot 与 Wi-Fi连接一起使用](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | 无需以太网适配器，即可Wi-Fi设备中的 autopilot。 |
| [Tenantlockdown 云解决方案提供商和 Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | 应用租户注册并应用策略后，设备只能在重置或重新刷用设备时注册到该租户中。 |
| [全局分配的访问权限](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | 适用于多个应用展台模式的新配置方法，该方法在系统级别应用展台，使其适用于所有应用展台。                  |
| [在多应用展台中自动启动应用](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 将应用程序设置为在登录多应用展台模式时自动启动。                                                        |
| [展台模式行为更改，用于处理故障](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 展台模式故障现在具有限制性回退。                                                                                                |
| [HoloLens政策](hololens-release-notes.md#hololens-policies)                                    | 新策略HoloLens。     |
| [缓存Azure AD展台的组成员身份](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 新策略允许用户使用组成员身份缓存在设置的天数内脱机使用展台模式。                                        |
| [新的设备限制策略HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | 为设备管理策略启用了新启用的设备HoloLens 2。                                                                                |
| [新的电源策略HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 新支持的电源超时设置策略。  |
| [更新策略](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 新启用的策略允许控制更新。           |
| [已启用设置页面可见性HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 策略，选择在应用设置页面。             |
| [研究模式](hololens-release-notes.md#research-mode) | 在 HoloLens 2 上使用研究模式。 |
| [录制长度增加](hololens-release-notes.md#recording-length-increased) | MRC 录制不再上限为 5 分钟。 |
| [更新中的改进和修复](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新中的其他修补程序。   |

### <a name="auto-eye-position-support"></a>自动眼部位置支持

在HoloLens 2中，眼部位置可实现准确的全息影像定位、舒适观看体验和改进的显示质量。 眼部位置在内部计算，作为眼球跟踪计算的一部分。 但是，这要求每个用户都可以通过眼球跟踪校准，即使体验可能不需要眼睛凝视输入也是如此。

自动眼部位置 (AEP) 使这些场景能够以无交互方式为用户计算眼部位置。 自动眼睛位置从用户打开设备那一刻开始自动在后台工作。 如果用户没有以前的眼动跟踪校准，则自动眼部定位将在处理 20 - 30 秒后开始向显示系统提供用户眼睛位置。 用户数据不会持久保存在设备上，因此，如果用户关闭并重新启动设备，或者设备重新启动或从睡眠状态唤醒，则重复此过程。

当未经校准的用户戴上设备时，“自动眼部位置”功能会改变一些系统行为。 在此上下文中，未校准的用户是指以前未在设备上完成眼动跟踪校准过程的用户。

| 活动应用程序 | 先前行为 | Windows 全息版 20H2 更新的行为 |
|:-------------------|:-----------------|:-----------------------------------|
| 未启用凝视的应用或全息外壳 |“眼球跟踪校准提示”对话框随即显示。 | 不显示提示。 |
| 启用了凝视的应用 | “眼球跟踪校准提示”对话框随即显示。 | 仅当应用程序访问眼睛凝视流时，才会显示眼球跟踪校准提示。 |

如果用户从未启用凝视的应用程序转换为访问凝视数据的应用程序，则会显示校准提示。 

当当前用户没有活动的目视跟踪校准时，所有其他系统行为将类似于。 例如，将不会启用一次传递的开始手势。 初始设置的全新体验不会有任何变化。

对于需要眼睛眼睛数据或非常精确的全息图定位的体验，建议 uncalibrated 用户运行目视跟踪校准。 可以从目视跟踪校准提示进行访问，也可以从 "开始" 菜单启动设置应用程序，然后选择 "**系统 > 校准 > 目视校准 >" 运行目视校准**"。

稍后可以在 [其他校准信息](hololens-calibration.md#auto-eye-position-support)中找到此信息。 

### <a name="certificate-manager"></a>证书管理器

- 通过新的证书管理器改进了设备安全性和符合性的审核、诊断和验证工具。 此功能使你能够在商业环境中大规模部署、排查和验证你的证书。

在 Windows 全息版20H2 中，我们将在 HoloLens 2 设置应用中添加证书管理器。 请参阅 **设置 > 更新 & 安全 > 证书**。 此功能提供了一种简单易用的方法来查看、安装和删除设备上的证书。 使用新的证书管理器，管理员和用户现在已经改进了审核、诊断和验证工具，以确保设备保持安全性和合规性。 

-   **审核：** 能够验证是否已正确部署证书，或者确认是否已正确删除证书。 
-   **诊断：** 出现问题时，验证设备上存在的适当证书是否节省时间并帮助进行故障排除。 
-   **验证：** 验证证书是否服务于预期目的并能正常工作，可以节省大量时间，特别是在商业环境中，在较大规模部署证书之前。

若要快速查找列表中的特定证书，可以按名称、存储或到期日期排序。 用户还可以直接搜索证书。 若要查看单独的证书属性，请选择该证书，然后单击 " **信息**"。 

证书安装当前支持 .cer 和 .crt 文件。 设备所有者可以在本地计算机和当前用户中安装证书; 所有其他用户只能安装到当前用户。 用户只能删除直接从设置 UI 安装的证书。 如果通过其他方式安装了证书，则该证书还必须通过相同的机制删除。

#### <a name="to-install-a-certificate"></a>若要安装证书： 

1.  将 HoloLens 2 连接到 PC。
1.  将要安装的证书文件放在 HoloLens 2 上的某个位置。
1.  导航到 **设置应用 > 更新 & 安全 > 证书**，并选择 "安装证书"。
1.  单击 " **导入文件** "，并导航到保存证书的位置。
1.  选择 " **存储位置**"。
1.  选择 " **证书存储**"。
1.  单击“安装”  。

现在应在设备上安装证书。

#### <a name="to-remove-a-certificate"></a>删除证书的步骤： 
1. 导航到 **设置应用 > 更新和安全 > 证书**。
1. 在搜索框中按名称搜索证书。
1. 选择证书。
1. 单击 "**删除**"
1. 出现确认提示时，选择“是”。

![设置应用中的证书查看器](images/certificate-viewer-device.jpg)

![显示如何使用证书 UI 安装证书的图片](images/certificate-device-install.jpg)

稍后可 [在新的证书管理器页中](certificate-manager.md)找到此信息。

### <a name="auto-launch-provisioning-from-usb"></a>从 USB 自动启动设置

- 在 OOBE 期间使用带有预配包的 USB 驱动器时，可通过自动化过程来减少用户交互。

在此版本之前，用户必须在 OOBE 期间手动启动预配屏幕，才能使用按钮组合进行设置。 现在，用户可以通过使用 USB 存储驱动器上的预配包跳过按钮组合。 

1. 在 OOBE 的第一次种不可交互时插入带有预配包的 USB 驱动器
1. 当设备准备好进行预配时，将自动在 "设置" 页中打开提示。 

注意：如果在设备启动时，会将 USB 驱动器插入，则 OOBE 会枚举现有 USB 存储设备，并监视其他设备是否已插入。

有关在 OOBE 期间应用预配包的详细信息，请访问[HoloLens 预配](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)文档。

可以在 HoloLens 预配文档中找到有关[USB 中的自动启动设置](hololens-provisioning.md#auto-launch-provisioning-from-usb)的其他信息。

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>自动确认在 OOBE 中预配包
- 自动进程允许进行更少的用户交互，当 "预配包" 页面显示时，它将自动应用列出的所有包。

当设置主屏幕出现时，OOBE 将在10秒内计数，然后自动开始应用所有预配包。 验证所需的包后，用户仍可以在此10秒内 [确认或取消](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) 。

### <a name="automatic-provisioning-without-using-ui"></a>无需使用 UI 即可自动预配
- 合并了自动过程，减少了设置的设备交互。 

通过将预配的自动启动和预配包的自动启动结合在一起，用户可以自动预配 HoloLens 2 设备，而无需使用设备的 UI，甚至还可以戴上设备。 你可以继续为多个设备使用相同的 USB 驱动器和预配包。 这适用于同一区域中同时部署多个设备。 

1. 使用[Windows 配置设计器](https://www.microsoft.com/store/productId/9NBLGGH4TX22)[创建预配包](hololens-provisioning.md)。 
1. 将包复制到 USB 存储驱动器。
1. 将[HoloLens 2 闪存](hololens-insider.md#ffu-download-and-flash-directions)到[19041.1361 或更高版本](https://aka.ms/hololens2previewdownload)。 
1. 当 [高级恢复助理](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 已完成时，设备将拔出 USB-C 电缆。 
1. 将 u 盘插入设备。
1. HoloLens 2 设备启动到 OOBE 时，它会自动检测 USB 驱动器上的预配包，并启动设置页面。
1. 10秒后，设备会自动应用预配包。 

你的设备现在已配置，并将 [显示设置成功屏幕](hololens-provisioning.md#automatic-provisioning-without-using-ui)。

### <a name="using-autopilot-with-wi-fi-connection"></a>将 Autopilot 与 Wi-Fi 连接结合使用
- 通过使 Autopilot 能够在 Wi-Fi 连接的设备上正常工作，已消除了将 USB C 适配器连接到以太网以降低硬件需求的需要。

现在，在 OOBE 期间，一旦使用 wi-fi 连接 HoloLens 2，OOBE 就会检查设备的 Autopilot 配置文件。 如果找到一个，它将用于完成 AAD 联接和注册流的其余部分。 换句话说，不再需要使用以太网到 USB-C 或 Wi-Fi 到 USB-C 适配器，因为在 OOBE 开始时提供了它们。 详细了解[HoloLens 2 设备的 Autopilot](hololens2-autopilot.md)。

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown 云解决方案提供商和 Autopilot
- 通过设备重置或刷新将设备锁定到租户，从而使其在组织的租户上保持不变。 通过设置，禁止在中创建帐户，从而增强安全性。 

HoloLens 2 设备现在支持[Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2)中的 TenantLockdown CSP。 

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) 云解决方案提供商允许仅使用 Autopilot 将 HoloLens 2 绑定到 MDM 注册。 在 HoloLens 2 上将 TenantLockdown 云解决方案提供商的 RequireNetworkInOOBE 节点设置为 true 或 false（初始设置）值后，即使执行了重刷、操作系统更新等操作，值仍将保留在设备上。 

在 HoloLens 2 上将 TenantLockdown 云解决方案提供商的 RequireNetworkInOOBE 节点设置为 true 后，OOBE 将无限期等待 Autopilot 配置文件在网络连接后成功下载并应用。 

在 HoloLens 2 上将 TenantLockdown 云解决方案提供商的 RequireNetworkInOOBE 节点设置为 true 后，OOBE 中将不允许执行以下操作： 
- 使用运行时预配创建本地用户 
- 通过运行时预配执行 Azure AD 加入操作 
- 选择 OOBE 体验中的设备所有者 

#### <a name="how-to-set-this-using-intune"></a>如何使用 Intune 对此进行设置？ 
1. 创建自定义 OMA URI 设备配置文件，并为 RequireNetworkInOOBE 节点指定 true，如下所示。
OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 OMA-URI 设置租户锁定](images/hololens-tenant-lockdown.png)

1. 创建组并将设备配置文件分配给该设备组。 

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。  

在 Intune 门户中验证设备配置是否已成功应用。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的影响将处于活动状态。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>如何使用 Intune 在 HoloLens 2 上取消设置 TenantLockdown 的 RequireNetworkInOOBE？ 
1. 将 HoloLens 2 从先前分配了上面创建的设备配置的设备组中删除。 

1. 创建基于 OMA URI 的自定义设备配置文件，并为 RequireNetworkInOOBE 指定 false，如下所示。 OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![在 Intune 中通过 OMA URI 将 RequireNetworkInOOBE 设置为 false 的屏幕截图](images/hololens-tenant-lockdown-false.png)

1. 创建组并将设备配置文件分配给该设备组。 

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。

在 Intune 门户中验证设备配置是否已成功应用。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的影响将处于非活动状态。 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>将 TenantLockdown 设置为 true 后，如果在 HoloLens 上取消分配 Autopilot 配置文件，在 OOBE 期间会发生什么情况？ 
OOBE 将无限期等待 Autopilot 配置文件下载，并将显示以下对话框。 为了删除 TenantLockdown 的影响，必须首先仅使用 Autopilot 将设备注册到其原始租户，并且必须按照上一步中的说明取消设置 RequireNetworkInOOBE，然后才能删除 TenantLockdown 云解决方案提供商引入的限制。 

![在设备上实施策略时的设备内视图。](images/hololens-autopilot-lockdown.png)

此信息现在可在 [TENANTLOCKDOWN CSP 和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)下的 Autopilot 的其余部分找到。

### <a name="global-assigned-access--kiosk-mode"></a>全局分配的访问–展台模式
- 通过启用在系统级别应用展台模式的新展台方法，降低了展台的标识管理。

这项新功能可让 IT 管理员为多个 app 展台模式配置 HoloLens 2 设备，此模式适用于系统级别，与系统上的任何标识都无关联，适用于登录到该设备的所有用户。 在[HoloLens 全局分配的访问展台](hololens-global-assigned-access-kiosk.md)中详细了解此新功能。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>在多应用展台模式下自动启动应用程序 
- 自动应用启动的聚焦体验，进一步增加了为展台模式体验选择的 UI 和应用选择。

仅适用于多应用展台模式，并且只有1个应用可以使用下面的突出显示属性指定为自动启动。 

当用户登录时，应用程序将自动启动。 

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>用于处理故障的展台模式行为更改
- 通过消除展台模式故障中的可用应用，更安全的展台模式。 

之前，在应用展台模式时遇到故障，HoloLens 用于显示 "开始" 菜单中的所有应用程序。 在出现故障的情况下，现在 Windows 全息版20H2 中，"开始" 菜单中将不会显示任何应用： 

![显示故障时的展台模式的图像。](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens政策
- 专用于为管理设备创建 HoloLens 的设备管理选项。 

已为 Windows 全息版20H2 上的 HoloLens 2 设备创建新的混合现实策略。 新的可控制设置包括：设置亮度、设置卷、禁用混合现实捕获中的录音、诊断可以收集时设置以及 AAD 组成员身份缓存。  

| 新建 HoloLens 策略                                | 说明                                                                               | 说明                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 允许禁用亮度按钮，因此按下不会更改亮度。       | 1是，0无 (默认值)                                                 |
| MixedReality\VolumeButtonDisabled                  | 允许禁用音量按钮，因此按下不会更改音量。               | 1是，0无 (默认值)                                                 |
| MixedReality\MicrophoneDisabled                    | 禁用麦克风，因此 HoloLens 2 不能录音。                      | 1是，0无 (默认值)                                                 |
| MixedReality\FallbackDiagnostics                   | 控制诊断日志可以收集的行为。                               | 0已禁用，1为设备所有者启用1，2为所有 (默认值启用)  |
| MixedReality\HeadTrackingMode                      | 保留供将来使用。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 控制将组成员身份缓存 Azure AD 多少天用于面向 Azure AD 组的展台。 | 请参阅下文。                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>缓存 Azure AD 脱机展台的组成员身份
- 已启用将脱机展台用于 AAD 组，最多60天。

此策略控制允许使用 Azure AD 组成员身份缓存来指定已登录用户 Azure AD 组的指定访问配置的天数。 一旦将此策略值设置为大于0的值，则不使用缓存。  

名称： AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小值为0天  
最大-60 天 

正确使用此策略的步骤： 
1. 为展台 Azure AD 组创建设备配置文件，并将其分配给 HoloLens 设备 () 。 
1. 创建基于自定义 OMA URI 的设备配置，该配置将此策略值设置为所需的天数 (> 0) 并将其分配给 HoloLens 设备 () 。 
    1. 应在 OMA-URI 文本框中输入 URI 值作为/Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays。
    1. 该值可以介于最小值/最大允许值之间。
1. 注册 HoloLens 设备，并验证两个配置是否应用于设备。 
1. 当 internet 可用时，让 Azure AD 用户1登录，一旦用户登录并 Azure AD 组成员身份已成功确认，就会创建缓存。 
1. 现在 Azure AD 用户1可以 HoloLens 脱机并将其用于展台模式，只要策略值允许 X 天。 
1. 对于任何其他 Azure AD 用户 N，可以重复执行步骤4和步骤5。以下是任何 Azure AD 用户都必须使用 Internet 登录设备，因此至少可以确定它们是展台配置所针对的 Azure AD 组的成员。 
 
> [!NOTE]
> 直到 Azure AD 执行步骤4后，才会在 "断开连接" 环境中遇到失败行为。 

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 的新设备限制策略
- 允许用户管理特定的设备管理策略，如阻止添加或删除预配包。

允许 HoloLens 2 设备的更多管理选项的新启用的策略。 
- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [高](/windows/client-management/mdm/remotelock-csp)

这两个适用于 AllowAddProvisioningPackage 和 AllowRemoveProvisioningPackage 的新策略将添加到 [常见的设备限制](hololens-common-device-restrictions.md)中。

> [!NOTE]
> 就[高](/windows/client-management/mdm/remotelock-csp)而言，HoloLens 仅支持/Vendor/MSFT/RemoteLock/Lock 配置。 不支持处理 PIN （如 reset 和 recover）的配置。

### <a name="new-power-policies-for-hololens-2"></a>HoloLens 2 的新电源策略
- 通过电源策略 HoloLens 睡眠或锁定时的更多选项。 

这些新添加的策略使管理员能够控制电源状态，如空闲超时。 若要阅读有关每个策略的详细信息，请单击该策略的链接。

|     策略文档链接                |     备注                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     要在 Windows 配置设计器中使用的示例值，即`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     要在 Windows 配置设计器中使用的示例值，即`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  要在 Windows 配置设计器中使用的示例值，即100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     要在 Windows 配置设计器中使用的示例值，即100                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     要在 Windows 配置设计器中使用的示例值，即`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     要在 Windows 配置设计器中使用的示例值，即`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

这两个适用于 DisplayOffTimeoutOnBattery 和 DisplayOffTimeoutPluggedIn 的新策略将添加到 [常见的设备限制](hololens-common-device-restrictions.md)中。

> [!NOTE]
> 若要在 HoloLens 2 上获得一致的体验，请确保将 DisplayOffTimeoutOnBattery 和 StandbyTimeoutOnBattery 的值设置为相同的值。 同样适用于 DisplayOffTimeoutPluggedIn 和 StandbyTimeoutPluggedIn。 有关新式备用的详细信息，请参阅 [显示、睡眠和休眠空闲计时器](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 。

### <a name="newly-enabled-update-policies-for-hololens"></a>针对 HoloLens 的新启用的更新策略
- 安装更新或禁用 "暂停更新" 按钮以确保更新的更多选项。

现在 HoloLens 2 设备上启用了这些更新策略：
-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

有关这些更新策略以及如何使用这些策略的详细信息，请参阅[管理 HoloLens 更新](hololens-updates.md)中的 HoloLens 设备。

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>已启用 HoloLens 2 的设置页面可见性
- 设置应用中增加的 UI 控件，这可能会使用户感到困惑，以显示有限的页面。

现在，我们已启用了一个策略，该策略允许 IT 管理员阻止系统设置应用中的特定页面可见或访问，或为除指定的页面之外的所有页面执行此操作。 若要了解如何完全自定义此功能，请单击下面的链接。

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

若要了解可以在 HoloLens 2 上自定义的页面设置，请访问我们的[设置 uri "页](settings-uri-list.md)。 
 
![在“设置”应用中修改的使用时段的屏幕截图](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>研究模式
在研究模式下，HoloLens 2 成为计算机视觉研究的强大工具。 与以前的版本相比，HoloLens 2 的研究模式具有以下优点：
-   除了 HoloLens 中公开的传感器 (第一代) 研究模式，我们现在提供 IMU 传感器访问，包括加速感应器、陀螺仪和磁力仪。
-   HoloLens 2 提供了可与研究模式一起使用的新功能。 具体来说，就是访问可提供更丰富的试验集的有表述的手动跟踪和目视跟踪 Api。

研究人员现在可以选择在其 HoloLens 设备上启用研究模式，以访问所有面向外部的原始图像传感器流。 HoloLens 2 的研究模式还提供对加速计、陀螺仪和磁力仪读数的访问。 为了保护用户的隐私性，无法通过 "调查" 模式获取原始眼睛跟踪相机图像，但可通过现有 Api 使用 "目视" 方向。

有关更多技术详细信息，请查看 [研究模式文档](/windows/mixed-reality/research-mode) 。

### <a name="recording-length-increased"></a>记录长度增加
由于客户反馈，我们已增加 [混合现实捕获](holographic-photos-and-videos.md)的记录长度。 默认情况下，混合现实捕获将不再限制为5分钟，但会根据可用磁盘空间来计算最大记录长度。 该设备将根据可用磁盘空间（最大为总磁盘空间的80%）估算最大视频录制持续时间。

> [!NOTE]
> 如果发生以下情况之一，HoloLens 将使用默认视频录制长度 (5 分钟) ：
> - 预计的最大记录持续时间小于默认的5分钟。
> - 可用磁盘空间小于总磁盘空间的20%。

你可以在 " [全息照片和视频](holographic-photos-and-videos.md#maximum-recording-length) " 文档中找到完全要求。 

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：
- OOBE 中的更多屏幕现在处于暗色模式。
- 了解更多内容应联机指向最新的隐私声明。
- 解决了用户无法通过设置包预配 VPN 配置文件的问题。
- 修复了 VPN 连接的代理配置问题。
- 已更新策略以禁用通过 MDM for NCM for AllowUsbConnection 的 USB 函数的枚举。
- 解决了在将设备设置为[单应用展台](hololens-kiosk.md)后，阻止 HoloLens 设备在文件资源管理器中显示在 (MTP) 上的问题。 请注意，一般) 中的 MTP (和 USB 连接仍可使用 [AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 策略进行禁用。
- 修复了在展台模式下正确缩放 "开始"菜单中的图标的问题。
- 修复了由于 HTTP 缓存干扰以展台模式为目标 Azure AD 组的问题。
- 修复了在使用预配包启用开发人员模式后，用户无法使用 "取消" 按钮的问题，除非他们禁用并重新启用了开发人员模式。

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows全息版，版本 1903-2020 更新
- 生成18362.1085

这一月度质量更新不包含任何显著的更改，我们建议你试用最新的功能版本 Windows 全息版20H2。

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows全息版，版本 2004-2020 更新
- 生成19041.1124
 
更新中的改进和修复：

- 删除导致运行时系统错误的不必要的检查。

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows全息版，版本 1903-2020 更新
- 生成18362.1081

这一月度质量更新不包含任何显著的更改，我们建议你试用 Windows 全息版本2004的最新版本。

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows全息版，版本 2004-2020 更新
- 生成19041.1117

更新中的改进和修复：

- 解决了在 appxmanifest.xml 中存在 SupportsMultipleInstances = "true" 时阻止 Visual Studio 调试应用程序的问题。
- 此版本包含 NCSI proxy 检测修复，可解决通过网络代理进行的 Internet 检测失败的问题。 NCSI 可以使用计算机代理和每个配置文件的代理来检测 Internet 连接。 将来的版本中，NCSI 将支持每个用户的代理。
- 在大多数 Windows Mixed Reality 设备上，当用户的头处于期待的非特定位置时，正向矢量平行于地面。 但是，的较早版本 HoloLens 2 将矢量调整为垂直于显示面板，而相对于理想方向，该向量相对向下倾斜几度。 HoloLens 2 的较新版本已更正此情况，以确保各种形式因素的语义一致性。
- 提高了手动跟踪可靠性，在特定情况下将导致更少的跟踪损失。
- 此版本包含一个修补程序，可改进音频时间戳质量，这可能会导致视频捕获问题。

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows全息版，版本 1903-2020 更新
- 生成18362.1079

更新中的改进和修复：

- 在大多数 Windows Mixed Reality 设备上，当用户的头处于期待的非特定位置时，正向矢量平行于地面。 但是，的较早版本 HoloLens 2 将矢量调整为垂直于显示面板，而相对于理想方向，该向量相对向下倾斜几度。 HoloLens 2 的较新版本已更正此情况，以确保各种形式因素的语义一致性。
- 提高了手动跟踪可靠性，在特定情况下将导致更少的跟踪损失。

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows全息版，版本 2004-8 2020 月版更新
- 生成19041.1113

更新中的改进和修复：

- 设置应用将不再跟随用户进入 Iris 注册或眼睛跟踪校准体验。
- 修复了一个 bug，该 bug 在用于重命名设备并执行其他操作 (例如连接到网络) 时在设备重启后执行其他操作（例如，连接到网络）的情况下应用设置包。
- 修改了初始设备设置流程的配色方案，以提高视觉质量。

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows全息版，版本 1903-8 2020 月版更新
- 生成18362.1074

这一月度质量更新不包含任何显著的更改，我们建议你试用 Windows 全息版本2004的最新版本。

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows全息版，版本 2004-2020 更新
- 生成19041.1109

更新中的改进和修复：

- 现在，开发人员可以选择启用还是禁用设备门户要求安全连接。
- 操作系统更新后，针对应用程序启动的可靠性得到了提高。
- 更改了默认收件箱亮度到100%。
- 解决了 HoloLens 2 上 Windows 设备门户的 HTTPS 转发问题。

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows全息版，版本 1903-2020 更新
- 生成18362.1071

更新中的改进和修复：

- 修复了一个问题，该问题可能导致在跟踪丢失或执行跟踪时，无法在 Unity 应用程序中消失。
- 修复了在某些设备上使用 HoloLens Emulator 硬件加速时，使独占 HoloLens 应用程序故障回复到 shell 的问题。
- 解决了 HoloLens 2 上 Windows 设备门户的 HTTPS 转发问题。

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows全息版，版本 2004-2020 更新
- 生成19041.1106

更新中的改进和修复：

- 对于某些属性，如果未指定，则自定义 MRC 记录器现在具有新的默认值。
  - 在 *MRC 视频效果*：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳机) ) 
  - 在 " *MRC 音频" 效果* 上：
    - LoopbackGain (中"应用音频增益"页上的当前混合现实捕获"Windows 设备门户) 
    - MicrophoneGain (中"麦克风音频增益"页上的当前混合现实捕获"Windows 设备门户) 
- 修复了一个 bug，以提高混合现实捕获方案中的音频质量。 具体而言，此修复应消除在显示"开始"菜单时录制 **的音频** 问题。
- 改进了录制视频中的全息影像稳定性。
- 解决了混合现实捕获在设备处于待机状态多天后无法录制视频的问题。
- 对于 Unity 应用程序，通常禁用 HolographicSpace.UserPresence API。 此行为可避免在视器翻转时导致某些应用暂停的问题，即使启用了"在后台运行"设置。 现已为 Unity 版本 2018.4.18 及更高版本以及 2019.3.4 及更高版本启用 API。
- 通过证书设备门户访问Wi-Fi，Web 浏览器可能会由于证书无效而阻止对 的访问。 即使设备证书以前受信任，浏览器也可能报告"ERR_SSL_PROTOCOL_ERROR"等错误。 在这种情况下，无法继续设备门户，因为无法忽略安全警告。 此更新解决了问题。 如果以前在电脑上下载并信任设备证书以删除浏览器安全警告，并且发生 SSL 错误，必须下载并信任新证书，以解决浏览器安全警告。
- 启用了创建运行时预配包的能力，该包可以使用 MSIX 包安装应用。
- 在 设置System 全息影像 中添加了一个设置，允许用户在设备关闭时自动从混合现实主页  >    >  中删除所有全息影像。
- 修复了导致应用HoloLens像素格式在仿真器中呈现黑色HoloLens的问题。
- 修复了 Iris 登录期间导致崩溃的 bug。
- 修复了针对当前应用重复下载应用商店的问题。
- 修复了一个 bug，以防止沉浸式应用Microsoft Edge打开。
- 修复了从 1903 版本更新后在初始启动中启动照片应用的问题。
- 提高了性能和可靠性。

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows全息版 1903 - 2020 年 6 月更新
- 内部版本 18362.1064

更新中的改进和修复：

- 如果未指定某些属性，则自定义 MRC 记录器具有新的默认值。
  - 在 *MRC 视频效果上*：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式头戴显示设备) ) 
  - 在 *MRC 音频效果上*：
    - LoopbackGain (中"应用音频增益"页上的当前混合现实捕获"Windows 设备门户) 
    - MicrophoneGain (中"麦克风音频增益"页上的当前混合现实捕获"Windows 设备门户) 
- 对于 Unity 应用程序，通常禁用 HolographicSpace.UserPresence API。 此行为可避免在视器翻转时导致某些应用暂停的问题，即使启用了在后台运行的设置。 现已为 Unity 版本 2018.4.18 及更高版本以及 2019.3.4 及更高版本启用 API。
- 修复了导致应用HoloLens像素格式以在应用中呈现黑色HoloLens Emulator。
- 修复了从 1903 版本更新后在初始启动中启动照片应用的问题。

## <a name="windows-holographic-version-2004"></a>Windows全息版 2004  
- 内部版本 - 19041.1103

HoloLens 2、Windows Holographic 版本 *2004 的 2020* 年 5 月主要软件更新包含许多令人心动的新功能，例如支持 Windows Autopilot、应用深色模式、USB 以太网支持 5G/LT 热点等。 若要更新到最新版本，请打开 设置应用，转到"更新&    **安全性"，** 然后选择"检查 **更新"**   按钮。 

|             功能                              |          说明                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          使用 AutoPilot 预配置和无缝设置用于生产Windows设备                 |
|       FIDO 2 支持                             |          支持 FIDO2 安全密钥，为共享设备启用快速且安全的身份验证            |
|       改进了预配                      |          将预配包从 USB 驱动器无缝应用到HoloLens                              |
|       应用程序安装状态                 |          检查已通过 MDM 将设置应用推送到 HoloLens 2应用的安装状态               |
|       配置服务提供商 (使用)    |          添加了新的配置服务提供程序，以增强管理员控制功能                 |
|       USB 5G/USB 支持                       |          扩展的 USB 以太网功能支持 5G/LTS                                    |
|       深色应用模式                              |          深色应用模式适用于支持深色和浅色模式的应用，从而改善观看体验        |
|       语音命令                             |          支持使用其他系统语音命令来控制HoloLens操作                           |
|       手部跟踪改进                 |          手部跟踪改进使按钮和 2D 板交互更准确                        |
|       质量改进和修复                 |          跨平台的各种系统性能和可靠性改进                            |

### <a name="support-for-windows-autopilot"></a>支持 Windows Autopilot

WindowsAutopilot for HoloLens 2允许设备销售渠道预先HoloLens Intune 租户。 设备到达时，可以自行部署为租户下的共享设备。 若要利用自我部署，设备必须使用 USB-C 到以太网在安装的第一个屏幕期间连接到网络。

用户启动 Autopilot 自我部署过程后，该过程将完成以下步骤：

1. 将设备加入 Azure Active Directory (Azure AD)。
1. 使用 Azure AD 将设备注册到 Microsoft Intune (或其他 MDM 服务) 。
1. 下载设备目标策略、证书和网络配置文件。
1. 预配设备。
1. 向用户展示登录屏幕。

有关详细信息，请Windows [Autopilot for HoloLens 2指南](hololens2-autopilot.md)。

*立即联系帐户管理员以加入 AutoPilot 预览版。Autopilot 就绪设备即将开始交付。*

### <a name="fido2-security-key-support"></a>FIDO2 安全密钥支持

某些用户与HoloLens或学校环境中的用户共享设备。 因此，用户可以轻松地无需键入长用户名和密码，这一点很重要。 使用 Fast Identity Online (FIDO) ，组织 (Azure AD 租户) 无需输入用户名或密码即可HoloLens无缝登录到 HoloLens。

FIDO2 安全密钥是基于标准的"不可加密"无密码身份验证方法，可以采用任何外形要求。 FIDO 是无密码身份验证的开放标准。 它允许用户和组织在没有用户名或密码的情况下登录到其资源。 而是使用内置于设备的外部安全密钥或平台密钥。

若要开始，请参阅 [启用无密码安全密钥登录](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>通过预配包改进了 MDM 注册

通过预配包，HoloLens配置文件设置配置，而不是通过HoloLens体验进行配置。 以前，预配包必须复制到内部HoloLens上。 现在，它们可以位于 USB 驱动器上，因此可以更轻松地在多个设备HoloLens重复使用，并且你可以并行预配设备。 预配包现在还支持在设备管理中注册字段，因此预配后无需手动设置。

试试看：

1. 将最新版本的 Windows 配置设计器从 Windows 存储下载到电脑上。
1. 选择 **"预配HoloLens**  >  **设备预配HoloLens 2设备"。**
2. 生成配置文件。 然后将创建的所有文件复制到 USB-C 存储设备。
3. 将 USB-C 设备插入任何新刷入的HoloLens。 然后按 **音量关闭**  +  **电源** 按钮以应用预配包。

### <a name="line-of-business-application-install-status"></a>业务线应用程序安装状态

业务线应用的 MDM 应用部署和管理对于HoloLens。 管理员和用户需要查看应用安装状态，以便进行审核和诊断。 在此版本中，我们在"帐户访问工作或设置"单击帐户信息"中添加  >    >    >  **了**  >  **更多详细信息**。

### <a name="additional-csps-and-policies"></a>其他 Csp 和策略

[ (CSP) 的配置服务提供程序](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)是一个用于读取、设置、修改或删除设备上的配置设置的接口。 在此版本中，我们添加了对更多策略的支持，以提高管理员对已部署 HoloLens 设备的控制。 有关 HoloLens 支持的 csp 列表，请参阅[NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp)。

本版本中的新主题：

**策略云解决方案提供商** 

策略配置服务提供程序使企业能够在 Windows 设备上配置策略。 在此版本中，我们为 HoloLens 添加了新策略，这里列出了这些策略。 若要了解详细信息，请参阅[HoloLens 2 支持的策略 csp](/windows/client-management/mdm/policies-supported-by-hololens2)。  

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

NetworkQoSPolicy 配置服务提供程序创建 (QoS) 策略的网络服务质量。 QoS 策略根据一组匹配的条件对网络流量执行一组操作。 若要了解详细信息，请参阅 [NETWORKQOSPOLICY CSP](/windows/client-management/mdm/networkqospolicy-csp)。

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>为 5G/LTE 受限设备扩展 USB 以太网支持

添加了支持，使某些移动宽带设备（例如 5G/LTE 手机和 Wi-Fi 热点）通过 USB 受限到 HoloLens 2。 这些设备现在作为另一个以太网连接显示在 " **网络设置** " 中。  (不支持需要外部驱动程序的移动宽带设备。 ) 此功能在 Wi-Fi 不可用时启用了高带宽连接，并且 Wi-Fi tethering 的性能不够高。 若要了解有关受支持的 USB 设备的详细信息，请参阅[蓝牙和 USB-C 设备连接](hololens-connect-devices.md)。  

### <a name="hand-tracking-improvements"></a>手动跟踪改进

此版本包含多项跟踪改进：

- 指示 **稳定性：** 系统现在在拒绝封闭像素时，会对索引手指进行弯曲。 当你推送按钮、类型、滚动内容和其他内容时，此更改会提高准确性！ 
- **减少了意外的空中点击：** 我们改进了对 $ 攻分流手势的检测。 现在几个常见情况下的意外激活次数较少，例如，当您将指针放在您的侧面时。
- **用户交换机可靠性：** 当你共享设备时，系统现在更快、更可靠。
- **精简的手偷窃：** 我们改进了对传感器进行两次干预的情况的处理。 如果有多个人密切合作，则现在会有很少的机会将用户从用户 "跳转" 到场景中的其他人。
- **系统可靠性：** 修复了一个问题，该问题导致手动跟踪在设备负载较高时停止工作。

### <a name="dark-mode"></a>深色模式

许多 Windows 应用现在同时支持深色和浅色模式。 HoloLens 2 用户可以为同时支持这两种应用的应用选择默认模式。 更新之后，默认应用模式为 "深色"，但你可以轻松地更改此设置：导航到 **设置**  >  **系统**  >  **颜色**"  >  **选择默认的应用模式**。 

这些 "内置" 应用支持暗色模式： 

- 设置 
- Microsoft Store 
- Mail 
- 日历 
- 文件资源浏览器 
- 反馈中心 
- OneDrive 
- 照片 
- 3D 查看器 
- 电影和电视 

![深色模式窗口平铺](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>系统语音命令

你现在可以对设备上的任何应用使用语音命令。 有关详细信息，请参阅[使用语音操作 HoloLens](hololens-cortana.md)。 另请参阅[HoloLens 2 支持的语言](hololens2-language-support.md)。  

### <a name="cortana-updates"></a>Cortana 更新

更新后的应用程序可与 Microsoft 365 集成，以帮助你在设备上进行更多的操作， (当前仅 US-English) 。 在 HoloLens 2 上，Cortana 不再支持特定于设备的命令，例如调整音量或重新启动。 新的系统语音命令现在支持这些选项。 在[博客](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)中了解有关新 Cortana 应用的详细信息。

### <a name="quality-improvements-and-fixes"></a>质量改进和修复

更新中也有改进和修复：  
- 引入了活动的显示校准系统。 此功能可改善全息影像的稳定性和对齐方式。 当你从一侧到另一侧时，它们现在就会保持不变。
- 修复了 HoloLens 定期中断 Wi-Fi 流式处理的 bug。 如果应用程序指示它需要低延迟流式处理，请通过调用 [SetSocketMediaStreamingMode 函数](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)来实现修复。
- 修复了在研究模式下流式处理期间发生的设备挂起。
- 修复了一个 bug，在某些情况下，当恢复会话时，正确的用户将不会显示在登录屏幕上。
- 修复了用户无法通过 **设置** 导出 MDM 日志的问题。
- 修复了在全新安装后立即进行目视跟踪的准确性可能低于预期的问题。
- 修复了在某些情况下，眼睛跟踪子系统未能初始化或执行校准的问题。
- 解决了向已校准的用户提示目视校准的问题。
- 修复了驱动程序在目视校准过程中崩溃的问题。
- 解决了重复电源按钮按下的问题可能导致60秒系统超时和 shell 崩溃。
- 提高了深度缓冲区的稳定性。
- 在反馈中心添加了 " **共享** " 按钮，以便用户可以更轻松地共享反馈。
- 修复了 RoboRaid wan't 安装正确的 bug。

### <a name="known-issues"></a>已知问题

- Zh-chs 系统语言的问题会阻止语音命令采用混合现实捕获或显示设备 IP 地址。
- 问题要求在启动设备以使用 "你好 Cortana" 语音激活之后启动 Cortana 应用。 如果从18362版本进行了更新，则在 **启动** 时，可能还会看到 Cortana 应用程序的早期版本的第二个应用磁贴。

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows全息版，版本 1903-5 2020 月更新 
- 生成18362.1061

此月度质量更新不包含任何显著的更改，因为团队正在处理 Windows 全息版2004可能会更新，如前文所述。

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows全息版，版本 1903-2020 更新
- 生成18362.1059

**支持的应用的深色模式** 

许多 Windows 应用都支持深色和浅色模式。 HoloLens 2 客户现在可以为支持两种配色方案的应用选择默认模式。 根据客户反馈，我们将默认的应用模式设置为 "深色"，但你随时可以轻松地更改此设置：导航到 **设置 > 系统 > 颜色** 以找到 **"选择你的默认应用模式"。**

这些 "内置" 应用支持暗色模式：
- 设置
- Microsoft Store
- Mail
- 日历
- 文件资源浏览器
- 反馈中心
- OneDrive
- 照片
- 3D 查看器
- 电影和电视

**更新中也有改进和修复：** 
- 确保在混合现实捕获中包含 shell 重叠。
- Unreal 开发人员现在可以在设备门户中使用3D 视图页面来测试和调试应用程序。
- 当使用 *HolographicDepthReprojectionMethod DepthReprojection* 算法时，混合现实捕获中改进了全息图稳定性。
- 修复了32位 ARM 应用上的 "WinRT IStreamSocketListener API 类未注册" 错误。

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows全息版，版本 1903-2020 更新 
- 生成18362.1056

更新中的改进和修复：

- 当使用 *HolographicDepthReprojectionMethod AutoPlanar* 算法时，混合现实捕获中改进了全息图稳定性。
- 确保连接到深度 MF 示例的坐标系与公共文档一致。
- 通过使客户能够通过设备门户粘贴大量文本，提高开发人员的工作效率。

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows全息版，1903 2020 年2月版更新 
- 生成18362.1053

更新中的改进和修复：

- 暂时禁用了 Unity 应用程序的 HolographicSpace. UserPresence API。 此更改避免了在向上翻转面板时导致某些应用暂停的问题，即使启用了 "在后台运行" 设置也是如此。
- 修复了手动跟踪引起的随机 HUP 崩溃，在这种情况下，用户会注意到，在几秒钟后，UI 冻结后会返回到 shell。
- 改善了手动跟踪，这样当你通过食指时，该手指的上半部分就不会意外地弯曲。
- 提高了头跟踪、空间映射和其他运行时的可靠性。

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows全息版，版本 1903-2020 更新 
- 生成18362.1043
 
更新中的改进和修复：

- 使用 HoloLens 2 模拟器时，对独占应用的稳定性得到提高。

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows全息版，1903 2019 年12月更新 
- 生成18362.1042

更新中的改进和修复：

- 引入了 (LSR) 修补程序的最后阶段复制。 改善了全息影像渲染，使其深度更准确地显示更稳定，更清晰。 如果应用未正确设置全息影像的深度，则此更新后，此症状将更为明显。
- 固定应用和独占应用之间的导航的固定稳定性。
- 解决了在设备处于待机状态几天后混合现实捕获无法录制视频的问题。
- 改善了全息影像稳定性。

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows全息版，版本 1903-2019 更新 
- 生成18362.1039

更新中的改进和修复：

- 修复了在初始安装过程中用于 en CA 和 en-us 的 **选择** 语音命令的功能。
- 提高了在最新 Unity 和混合现实中处于最新 Unity 和混合现实 Toolkit (MRTK) 版本的视觉对象质量。
- 修复了在打开并关闭 "开始"菜单之前，内置应用程序在启动时停滞处于暂停状态的问题。
- HoloLens 2 和模拟器的 OpenXR 运行时一致性修复和改进。
