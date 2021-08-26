---
title: HoloLens 2 发行说明
description: 随时了解每个新 HoloLens 2 版本中的所有更新。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 08/10/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 4aa0ea03850277e528b134c9686633a140c64721
ms.sourcegitcommit: 6ce962ede986ebfab21d1665722694eaee13c280
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2021
ms.locfileid: "122859436"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 发行说明

若要确保你的 HoloLens 设备具有工作效率，我们将继续发布功能、bug 和安全更新。 在此页上，可以查看每个月 HoloLens 的新增功能。 若要获取最新的 HoloLens 2 更新，可以[检查更新并手动更新](hololens-update-hololens.md#check-for-updates-and-manually-update)或获取完全更新， (FFU) [通过高级恢复助理来闪存设备](hololens-recovery.md#clean-reflash-the-device)。 [下载](https://aka.ms/hololens2download)内容保持最新，并提供最新的公开发布版本。

> [!NOTE]
> 最近的 Windows 11 公告侧重于 PC 版本的 Windows。 最近于 2021 年 5 月推出了 HoloLens 2 [主要 OS 更新](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067)，我们正在根据客户的反馈为今年秋季推出一个即将到来的版本。

> [!IMPORTANT]
> 由于现已解决[了21H1 内部版本中影响远程协助用户的已知问题](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)，我们暂时暂停了 Windows 全息版21H1 更新的产品/服务。 我们还更改了默认的高级恢复助理 (ARC) 生成到[Windows 全息，版本20H2 –2021年6月更新](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)。 现在，圆弧生成将恢复为21H1 生成的目标。

## <a name="windows-holographic-version-21h1---august-2021-update"></a>Windows全息版 21H1-2021 年8月更新

- 生成20348.1014

更新中的改进和修复：

- 修复了一个问题，该问题阻止 Xbox 控制器在具有控制器支持的沉浸式应用程序中工作。
- 改善了设备更新故障的诊断。

## <a name="windows-holographic-version-20h2---august-2021-update"></a>Windows全息版 20H2-2021 年8月更新

- 生成19041.1161

更新中的改进和修复：

- 这一月度质量更新不包含任何显著的更改，我们建议你试用最新的版本，Windows 全息版21H1。

## <a name="windows-holographic-version-21h1---july-2021-update"></a>Windows21H1 版本-2021 年7月更新

- 生成20348.1010

更新中的改进和修复：

- 当文件资源管理器在打开锁定的文件时遇到问题时，设备门户已增强了通知客户的方法。
- 在所有受支持的浏览器中使用 https 时，文件上载、下载、重命名和删除现已修复。
- 修复了从设置 > 网络启动 Wi-Fi 属性 UI 时无法保存 Wi-Fi 代理 **& > > 状态的** 问题。
- 解决了跨 OS 更新删除 eSIM 证书的问题。 此修补程序可确保在更新到21H1 版本时删除 eSIM 证书和相关组件。
- 更正了影响操作系统重置的预安装应用的问题。
- 在增加 CPU 负载时，经过调整以增加运行时的电池充电性能。 HoloLens 2 设备充电时，如果检测到设备正在热运行，则内部电池的充电速度将会降低，降低热量。 正权衡的是，设备不太可能因热量问题而关闭，影响在于设备运行时间更长。 如果设备运行非常酷，则不会影响充电费率。

## <a name="windows-holographic-version-20h2--july-2021-update"></a>Windows版本20H2 –2021年7月更新

- 生成19041.1157

更新中的改进和修复：

- 当文件资源管理器在打开锁定的文件时遇到问题时，设备门户已增强了通知客户的方法。
- 在所有受支持的浏览器中使用 https 时，文件上载、下载、重命名和删除现已修复。

## <a name="windows-holographic-version-21h1---june-2021-update"></a>Windows全息版 21H1-2021 年6月更新

- 生成20348.1007

### <a name="onedrive-for-work-or-school-camera-roll-upload"></a>OneDrive 工作或学校相机滚动上传

我们已向 HoloLens 2 设置应用添加了一项新功能，该功能使客户能够将混合现实照片和视频从设备的照片 > 照相机滚动文件夹自动上载到工作或学校文件夹的相应 OneDrive。 此功能解决了 HoloLens 2 上[的 OneDrive 应用内的功能间隙](holographic-photos-and-videos.md#share-your-mixed-reality-photos-and-videos)，该功能仅支持将自动相机滚动更新到客户的个人 Microsoft 帐户 (而不支持其工作或学校帐户) 。

**工作原理**

- 请访问 **设置 > 系统 > 混合现实相机**，以启用 "相机上传"。
- 如果将此功能设置为 "**开**" 位置，则捕获到你的设备的所有混合现实照片或视频都将自动排队，以便上传到工作或学校帐户的 OneDrive > 照相机滚动文件夹中。
    >[!NOTE]
    >在启用此功能之前捕获的照片和视频 *不* 会排队等待上载，但仍需手动上传。
- "设置" 页上的状态消息将显示等待上传的文件数 (或读取 "OneDrive 是最新的) "。
- 如果你担心带宽或出于任何原因要 "暂停" 上载，则可以将该功能切换到 " **关闭** " 位置。 临时禁用该功能可确保在将新文件添加到 "相机照片" 文件夹中时，上传队列将继续增加，但在重新启用该功能之前，将不会上载文件。
- 最新文件将首先上传 (最后一个) 。
- 如果 OneDrive 帐户有问题 (例如，更改密码后) "**立即修复**" 按钮将显示在 "设置" 页上。
- 没有最大文件大小，但请注意，大文件上传会花费较长的时间，尤其是当上传带宽受到限制) 时 (。 如果在上传大型文件时 "暂停" 或关闭上载，将保留部分上传。 如果在 "已暂停" 或关闭的几个小时内重新启用上传，则上传将从中断的位置继续。 但是，如果在几个小时后重新启用上传，将从头开始重新启动大文件上传。

**已知问题和注意事项**

- 此设置没有基于当前带宽使用情况的内置限制。 如果需要将其他方案的带宽最大化，请手动关闭该设置。 Upload 将暂停，但该功能将继续监视新添加到摄像卷筒中的文件。 准备就绪后，请重新启用上传。
- 必须为设备上的每个用户帐户启用此功能，并且只能为当前已登录到设备的用户主动上载文件。
- 如果你正在拍摄照片或视频，同时在设置页面上实时观看上传计数，请注意，在完成当前文件上传之前，挂起的文件数可能不会更改。
- 如果设备处于睡眠状态还是已关闭，Upload 将暂停。 若要确保等待的上载完成，请主动使用该设备，直到设置页面读取 "OneDrive 是最新的"，或调整 **Power & 睡眠** 设置。

### <a name="added-support-for-some-telemetry-policies"></a>添加了对某些遥测策略的支持

HoloLens 2 上现在支持以下遥测策略：

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry 和 System\ConfigureTelemetryOptInSettingsUx 都应该一起使用，以便对设置应用程序中的遥测和行为具有完全控制。

更新中的改进和修复：

- 修复了颜色校准导致的重大视频损坏。
- 解决了 "电源" 菜单中的文本可能被截断的问题。
- 支持 RequirePrivateStoreOnly 策略。

## <a name="windows-holographic-version-20h2--june-2021-update"></a>Windows版本20H2 –2021年6月更新

- 生成19041.1154

### <a name="added-support-for-some-telemetry-policies"></a>添加了对某些遥测策略的支持

HoloLens 2 上现在支持以下遥测策略：

- ConfigureTelemetryOptInSettingsUx
- DisableDeviceDelete
- AllowDeviceNameInDiagnosticData
- FeedbackHubAlwaysSaveDiagnosticsLocally

System\AllowTelemetry 和 System\ConfigureTelemetryOptInSettingsUx 都应该一起使用，以便对设置应用程序中的遥测和行为具有完全控制。

建议试用21H1 的最新版本，Windows 全息版。

## <a name="windows-holographic-version-1903---june-2021-update"></a>Windows全息版，版本 1903-2021 更新

- 生成18362.1116

更新中的改进和修复：

- 这一月度质量更新不包含任何显著的更改，我们建议你试用最新的版本，Windows 全息版21H1。

>[!IMPORTANT]
> 此生成将不再提供服务。

## <a name="windows-holographic-version-21h1"></a>Windows全息版21H1
- 生成20346.1002

此更新包含两个目标受众的功能;最终用户可以在设备上使用的所有功能，以及可由 IT 管理员配置的新设备管理选项。 下表指定了与每个受众相关的功能。 如果你是 IT 管理员，请查看我们的 [It 管理员更新清单](#it-admin---update-checklist)。
>[!IMPORTANT]
>若要更新到此生成，HoloLens 2 设备 (s) 必须当前正在运行2021年2月更新 (版本 19041.1136) 或更高版本。 如果未看到此功能更新可用，请先更新设备，然后重试。

>[!NOTE]
>目前，Microsoft HoloLens 2 支持以下版本的每月服务更新 (bug 和安全修补程序) ：
>- WindowsHolographic 版本 20H2 (内部版本 19041.1128+) 
>- WindowsHolographic 版本 2004 (内部版本 19041.1103+) 
>- WindowsHolographic 版本 1903 (内部版本 18362+) 
>
> 随着 Holographic Windows 21H1 的推出，我们将停止每月为全息版本 **1903 Windows服务更新**。 这使我们能够专注于较新版本，并继续提供有价值的改进。


| 功能名称                                              | 简短说明                                                                      | 目标读者 | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新的 Microsoft Edge](#introducing-the-new-microsoft-edge)  | 新的基于 Chromium 的 Microsoft Edge 现可用于HoloLens 2。 | 最终用户 | 
[WebXR 和 360 Viewer](#webxr-and-360-viewer) | 尝试沉浸式 Web 体验和 360 视频播放。 | 最终用户 | 
[新“设置”应用](#new-settings-app) | 旧版 设置应用将被更新版本替换为新功能和设置。 | 最终用户 |
[显示颜色校准](#display-color-calibration) | 为 HoloLens 2 屏幕选择替代颜色配置文件。 | 最终用户 |
[默认应用选取器](#default-app-picker) | 选择应针对每个文件或链接类型启动的应用。 | 最终用户 |
[每个应用音量控制](#per-app-volume-control) | 独立于系统卷控制应用级别卷。 | 最终用户 |
[安装 Web 应用](#install-web-apps) | 使用新的 Microsoft Edge 浏览器HoloLens 2 Web 应用，例如 Microsoft Office。 | 最终用户 |
[轻扫以键入](#swipe-to-type) | 使用手指的提示在全息键盘上"轻扫"单词。 | 最终用户 |
[“开始”中的 Power 菜单](#power-menu-from-start) | 在"开始"菜单上，重启并HoloLens设备。 | 最终用户 |
[登录屏幕上列出的多个用户](#multiple-users-listed-on-sign-in-screen) | 在"登录"屏幕上显示多个用户帐户。 | 最终用户 |
[USB-C 外置麦克风支持](#usb-c-external-microphone-support) | 将 USB-C 麦克风用于应用和/或Remote Assist。 | 最终用户 |
[展台的访问者自动登录](#visitor-auto-logon-for-kiosks) | 启用"访问者帐户"上的自动登录以用于展台模式。 | IT 管理员 |
[展台模式下的新应用的新 AUMID](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | 新应用和 Edge 设置 AUMID。 | IT 管理员 |
[改进了展台模式故障切换](#kiosk-mode-behavior-changes-for-handling-of-failures) | 展台模式在空的开始菜单之前查找"全局分配的访问权限"。 | IT 管理员 |
[页面和可见性的新设置值](#new-settings-uris-for-page-settings-visibility) | 20 多个新的 SettingsURIS，设置/PageVisibilityList 策略。 | IT 管理员 |
[配置回退诊断](#configuring-fallback-diagnostics-via-settings-app) | 在应用中设置回退设置行为。 | IT 管理员 |
[与附近的设备共享内容](#share-things-with-nearby-devices) | 将文件或 URL 从HoloLens共享到电脑。 | 全部 |
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
> 首次在 HoloLens 2 上启动新版 Microsoft Edge 时，系统将从旧版 Microsoft Edge 导入你的设置和数据。 如果在启动新 Microsoft Edge后继续使用旧 Microsoft Edge，则新数据不会从旧数据同步到Microsoft Edge新Microsoft Edge。

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
- 默认情况下，WebXR 中不支持铰接式手关节。 开发人员可以通过打开 `edge://flags` "WebXR 手动输入"来启用支持。
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

在较旧的版本中，如果设备具有展台配置（这是全局分配的访问和 AAD 组成员分配的访问权限），则如果确定 AAD 组成员身份失败，用户将看到 "不[在启动时显示任何内容](hololens-kiosk.md#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode)" 菜单。

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

### <a name="it-admin---update-checklist"></a>IT 管理员-更新清单

此清单可帮助你了解在此功能更新中添加的功能可能会影响当前设备管理配置的新项目，或者你可能希望开始使用的新功能。

#### <a name="updates-to-kiosk-mode"></a>展台模式更新

[**为展台模式下的新应用✔️新 AUMIDs**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)：

如果你以前在展台使用设置应用或 Microsoft Edge 应用，我们已将这些应用替换为使用不同应用 ID 的新应用。 我们强烈建议你在下面的 [展台模式下阅读新应用的新 AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 。 这将确保在展台上继续拥有设置的应用程序，或包括新的 Microsoft Edge 应用程序。 现在可以完成这些更改，并将其部署到所有设备，并允许在更新时获得更平稳的过渡效果。

[**网亭的✔️访问者自动登录**](#visitor-auto-logon-for-kiosks)： 

现在，访问者可以自动登录到展台。 默认情况下，此行为是启用的，但可以被管理和禁用。

✔️ [**改进了展台模式故障**](#kiosk-mode-behavior-changes-for-handling-of-failures)处理：

如果未成功确定登录 AAD 用户的 AAD 组成员身份，则会将全局展台配置用于 "开始" 菜单 (如果存在，则为 "开始" 菜单) 否则显示 "开始" 菜单。 尽管空 "开始" 菜单不是可以直接设置的配置，但如果您使用的是展台，则这种新的处理可能会告诉您的支持部门，因为这可能适用于您的配置，或者您可能想要对分配的访问配置进行新调整。

#### <a name="updates-to-page-settings-visibility"></a>页面设置可见性更新

[**为页设置可见性✔️新的设置 uri**](#new-settings-uris-for-page-settings-visibility)

如果你当前正在使用[页面设置可见性](settings-uri-list.md)，则你可能希望对已允许或阻止的现有 uri 进行调整。

#### <a name="updates-for-your-wdac-policy"></a>适用于 WDAC 策略的更新
✔️如果以前通过 WDAC 阻止 Microsoft Edge，则需要更新你的 wdac 策略。 请查看以下代码，并使用提供的示例代码。
#### <a name="enable-new-endpoints-for-edge"></a>启用边缘的新终结点
✔️如果你有涉及配置网络终结点（例如代理或防火墙）的基础结构，请为新的 Microsoft Edge 应用启用这些新的终结点。

#### <a name="newly-configurable-items"></a>新的可配置项

✔️ [配置回退诊断](#configuring-fallback-diagnostics-via-settings-app)：你可以配置是否和谁可以收集回退诊断。

✔️[与附近设备共享内容](#share-things-with-nearby-devices)：你可以禁用新的邻近共享功能。

[为新 Microsoft Edge ✔️配置策略设置](#configuring-policy-settings-for-the-new-microsoft-edge)：查看适用于 Microsoft Edge 的新配置。

#### <a name="new-diagnostic-tool"></a>新的诊断工具

✔️[新 os 诊断跟踪](#new-os-diagnostic-traces)：收集与 OS 更新相关的日志。

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：

- [脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics) 还将包含序列号和操作系统版本的其他设备信息。
- 解决了通过运行时预配包部署业务线应用程序的问题。
- 解决了业务线应用程序安装状态报告问题。
- 修复了跨设备重置的新应用程序包持久性的问题。
- 修复了一个问题，该问题可能导致日语客户在边缘内键入错误的符号。
- 提高了 OS 更新的复原能力，如边缘的预安装应用。 
- 解决了影响 Microsoft Edge 安装的更新可靠性。 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows全息版20H2 –2021版更新
- 生成19041.1146

更新中的改进和修复：
- 这一月度质量更新不包含任何显著的更改，我们建议你试用最新的版本，Windows 全息版21H1。

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows全息版，版本 1903-5 2021 月更新
- 生成18362.1110

更新中的改进和修复：
- 此月度质量更新不包含任何显著的更改。 **此生成将不再接收每月服务更新**。 建议试用21H1 的最新版本，Windows 全息版。



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows版本 20H2-2021 年4月更新
- 生成19041.1144

更新中的改进和修复：

- 解决了业务线应用程序安装状态报告问题。

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows全息版，版本 1903-2021 更新
- 生成18362.1108

更新中的改进和修复：

- 解决了尝试更改本地帐户的密码时设置应用崩溃的问题。


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows全息版 20H2-2021 年3月更新
- 生成19041.1140

更新中的改进和修复：

- 如果客户使用 AdvancedPhotoCapture 或 LowLagPhotoCapture 来捕获带有 HoloLens 2 的照片，则现在可以在捕获照片后检索照相机最多3秒。
- 修复设备门户服务中的内存泄漏问题导致其他应用程序无法分配内存，导致其他应用程序的内存使用率增加。
- 解决了在分阶段推出中注册的用户无法登录到该设备的问题。

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows全息版，版本 1903-2021 更新
- 生成18362.1102

更新中的改进和修复：

- 修复设备门户服务中的内存泄漏问题导致其他应用程序无法分配内存，导致其他应用程序的内存使用率增加。

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows全息版 20H2-2021 年2月更新
- 生成19041.1136

更新中的改进和修复：

- 修复了初始设备安装和应用程序更新的相关问题。
- 解决了以后 HoloLens 版本的升级和航班问题。
- 从 HoloLens 设备中删除了 eSIM 根存储中未使用的预安装证书。

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows全息版，1903 2021 年2月版更新
- 生成18362.1098

这一月度质量更新不包含任何显著的更改，我们建议你试用 Windows 全息版本2004的最新版本。

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows全息版 20H2-2021 年1月更新
- 生成19041.1134

更新中的改进和修复：

- 当设备上有多个用户时，在启动、恢复和用户切换期间提高了性能。
- 添加了对研究模式的 arm32 [支持](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)。

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows全息版 1903 - 2021 年 1 月更新
- 内部版本 18362.1091

此每月质量更新不包含任何值得注意的更改，建议试用 Holographic 版本 2004 Windows最新版本。

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows全息版 20H2 - 2020 年 12 月更新
- 内部版本 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>通过 HoloLens 2 在 应用安装程序

我们正在 **添加新的 (应用安装程序) ，以便你** 能够更无缝地在 HoloLens 2 设备上安装应用程序。 对于非 **托管设备，此功能默认为打开状态**。 为了防止企业中断，应用安装程序 **目前不适用于托管** 设备。  

如果以下任一情况 **成立，则** 设备被视为"托管"设备：
- MDM [已注册](hololens-enroll-mdm.md)
- 配置了 [预配包](hololens-provisioning.md)
- 用户 [标识](hololens-identity.md) Azure AD

现在可以安装应用，而无需启用开发人员模式或设备门户。  只需 (USB 或 Edge) Appx 捆绑包下载到设备，然后导航到 文件资源管理器 中的 Appx 捆绑包，以提示你启动安装。  或者， [从网页 启动安装](/windows/msix/app-installer/installing-windows10-apps-web)。  与从 Microsoft Store 安装的应用或使用 MDM 的 LOB 应用部署功能旁加载的应用一样，应用需要使用签名工具进行数字签名[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)，并且用于签名[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)的证书必须受 HoloLens 设备信任，然后才能部署应用。

**应用程序安装说明。**

1.  确保设备未被视为托管设备
1.  确保HoloLens 2设备已打开并连接到电脑
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
- 修复了帐户的 PIN 重置Azure AD显示错误"出现问题。
- 启动 ET、设置应用中的 Iris、新用户或通知 toast 时，用户应看到更少的启动后 OOBE 故障。
- 用户应具有来自 OOBE 的正确时区。

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows全息版 1903 - 2020 年 12 月更新
- 内部版本 18362.1088

此每月质量更新不包含任何值得注意的更改，建议试用最新的 Windows Holographic 版本 20H2 – 2020 年 12 月更新，以及生成中添加的新 应用安装程序 功能。


## <a name="windows-holographic-version-20h2"></a>Windows全息版 20H2
- 内部版本 19041.1128

Windows全息版 20H2 现已发布，为用户和 IT 专业人员HoloLens 2一系列新功能。 从自动眼定位到 设置 中的证书管理器，改进展台模式功能和新的 Autopilot 设置功能。 此新更新使 IT 团队能够更精细地控制如何配置HoloLens设备，并为用户提供更无缝的全息体验。 

此最新版本是版本 2004 的每月更新，但这次我们将包含新功能。 主内部版本号将保持不变，Windows更新将指示每月发布到版本 2004 (内部版本 19041) 。 可以在"关于"屏幕中查看设置 >号，以确认你位于最新的可用内部版本 19041.1128+ 上。 若要更新到最新版本，请打开 设置 应用，转到"更新&安全性"，然后点击"检查更新"。 若要详细了解如何管理更新HoloLens，请访问[管理HoloLens更新](hololens-updates.md)。

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Holographic 版本 20H2 Windows新增功能  

| 功能                                              | 说明                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [自动眼部位置支持](hololens-release-notes.md#auto-eye-position-support) | 主动计算眼睛位置，用户无需经过眼动跟踪校准。   |
| [证书管理器](hololens-release-notes.md#certificate-manager)   | 允许使用更简单的新方法来安装和删除应用设置证书。     |
| [从 USB 自动启动预配](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | USB 驱动器上的预配包会自动提示 OOBE 中的预配页。                                                         |
| [在 OOBE 中自动确认预配包](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 预配包会在 OOBE 期间从预配页自动应用。                                                         |
| [无需使用 UI 即可自动预配](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 如何将预配自动启动和自动确认组合在一起。 |
| [将 Autopilot 与 Wi-Fi连接一起使用](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | 无需以太网适配器，即可从设备Wi-Fi autopilot。 |
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
| [研究模式](hololens-release-notes.md#research-mode) | 使用研究模式HoloLens 2。 |
| [录制长度增加](hololens-release-notes.md#recording-length-increased) | MRC 录制不再上限为 5 分钟。 |
| [更新中的改进和修复](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新中的其他修补程序。   |

### <a name="auto-eye-position-support"></a>自动眼部位置支持

在HoloLens 2中，眼部位置可实现准确的全息影像定位、舒适观看体验和改进的显示质量。 眼部位置在内部计算，作为眼球跟踪计算的一部分。 但是，这要求每个用户都可以通过眼球跟踪校准，即使体验可能不需要眼睛凝视输入也是如此。

自动眼部位置 (AEP) 使这些场景能够以无交互方式为用户计算眼部位置。 自动目视位置在用户将设备置于设备上的时刻自动开始运行。 如果用户没有先前的目视跟踪校准，则在处理时间为 20-30 秒后，自动目视定位将开始向显示系统提供用户的眼睛位置。 用户数据不会保留在设备上，因此如果用户关闭并重新打开设备，或者设备重新启动或从睡眠状态唤醒，则此过程将重复。

当未经校准的用户戴上设备时，“自动眼部位置”功能会改变一些系统行为。 在这种情况下，uncalibrated 用户指的是先前尚未经历设备上的目视跟踪校准过程的人。

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

现在，可以在 [Tenantlockdown CSP 和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)下与 Autopilot 的其余部分一起找到此信息。

### <a name="global-assigned-access--kiosk-mode"></a>全局分配访问权限 - 展台模式
- 通过启用在系统级别应用展台模式的新展台方法，减少了展台的标识管理。

此新功能允许 IT 管理员为多个应用展台模式配置 HoloLens 2 设备，该模式适用于系统级别，与系统上的任何标识没有关联，并且适用于登录设备的每个人。 在展台模式下详细了解HoloLens[功能](hololens-kiosk.md)。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>在多应用展台模式下自动启动应用程序 
- 具有自动应用启动的集中体验，进一步增加了为展台模式体验选择的 UI 和应用选择。

仅适用于多应用展台模式，并且只能使用"分配的访问权限配置"中下面的突出显示属性将 1 个应用指定为自动启动。

用户登录时，应用程序会自动启动。

```xml
<AllowedApps>                     
    <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
```

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>展台模式行为更改，用于处理故障
- 通过消除展台模式故障时可用的应用，实现更安全的展台模式。 

在应用展台模式时遇到故障之前，HoloLens在"开始"菜单中显示所有应用程序。 现在，Windows 20H2 版在发生故障时，开始菜单中不会显示任何应用，如下所示：

![当展台模式发生故障时，其外观的图像。](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens政策

- 专用于管理设备HoloLens的设备管理选项。 

在全息版 20H2 上为HoloLens 2设备Windows混合现实策略。 新的可控制设置包括：设置亮度、设置音量、禁用混合现实捕获中的音频录制、设置收集诊断的时间和 AAD 组成员身份缓存。  

| 新建HoloLens策略                                | 说明                                                                               | 说明                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 允许禁用亮度按钮，以便按它不会更改亮度。       | 1 是，0 (默认值)                                                 |
| MixedReality\VolumeButtonDisabled                  | 允许禁用音量按钮，以便按它不会更改音量。               | 1 是，0 (默认值)                                                 |
| MixedReality\MicrophoneDisabled                    | 禁用麦克风，因此无法对麦克风进行音频HoloLens 2。                      | 1 是，0 (默认值)                                                 |
| MixedReality\FallbackDiagnostics                   | 控制何时可以收集诊断日志的行为。                               | 0 已禁用，1 为设备所有者启用，2 为默认 (启用)  |
| MixedReality\HeadTrackingMode                      | 保留供将来使用。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 控制组成员身份缓存Azure AD组成员身份缓存用于展台目标组Azure AD天数。 | 请参阅下文。                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>缓存Azure AD展台的组成员身份
- 已启用脱机展台，可与 AAD 组一起使用最多 60 天。

此策略控制允许Azure AD组成员身份缓存用于针对已登录用户Azure AD组分配的访问配置。 一旦此策略值设置为大于 0 的值，则否则使用缓存。  

名称：AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最短 - 0 天  
最大值 - 60 天 

正确使用此策略的步骤： 
1. 为展台组创建设备配置文件Azure AD并将其分配给HoloLens设备 () 。 
1. 创建自定义基于 OMA URI 的设备配置，将此策略值设置为所需的天数 (> 0) 并将其分配给 HoloLens 设备 () 。 
    1. URI 值应在 OMA-URI 文本框中输入为 ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. 该值可以介于允许的最小值/最大值之间。
1. 注册HoloLens并验证这两个配置是否应用到设备。 
1. 在Azure AD Internet 可用时让用户 1 登录，用户登录并成功确认Azure AD组成员身份后，将创建缓存。 
1. 现在Azure AD用户 1 可以脱机HoloLens，只要策略值允许 X 天，就可以在展台模式下使用它。 
1. 对于任何其他 Azure AD 用户 N，可以重复步骤 4 和 5。此处的要点是，任何 Azure AD 用户都必须使用 Internet 登录到设备，以便我们至少能够确定他们是展台配置所面向的 Azure AD 组的成员。 
 
> [!NOTE]
> 在针对用户执行步骤 4 之前Azure AD用户将遇到"断开连接"环境中提到的失败行为。 

### <a name="new-device-restriction-policies-for-hololens-2"></a>新的设备限制策略HoloLens 2
- 允许用户管理特定的设备管理策略，例如阻止添加或删除预配包。

新启用的策略，允许对设备HoloLens 2选项。 
- [AllowAddProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage 和 AllowRemoveProvisioningPackage 的这两个新措施将添加到 [通用设备限制](hololens-common-device-restrictions.md)。

> [!NOTE]
> 对于[RemoteLock，HoloLens](/windows/client-management/mdm/remotelock-csp)仅支持 ./Vendor/MSFT/RemoteLock/Lock 配置。 不支持处理 PIN 的配置，例如重置和恢复。

### <a name="new-power-policies-for-hololens-2"></a>新的电源策略HoloLens 2
- 更多选项，用于HoloLens电源策略进入睡眠或锁定状态。 

这些新添加的策略允许管理员控制电源状态，例如空闲超时。 若要详细了解每个策略，请单击该策略的链接。

|     策略文档链接                |     备注                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     在配置设计器Windows的示例值，即`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     在配置设计器Windows的示例值，即`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  配置设计器中Windows的示例值，即 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     配置设计器中Windows的示例值，即 100                                                                          |
|     [StandbyTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     在配置设计器Windows的示例值，即`<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     在配置设计器Windows的示例值，即`<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

DisplayOffTimeoutOnBattery 和 DisplayOffTimeoutPluggedIn 的这两个新设置将添加到[通用设备限制 。](hololens-common-device-restrictions.md)

> [!NOTE]
> 若要获得一致的HoloLens 2，请确保将 DisplayOffTimeoutOnBattery 和 StandbyTimeoutOnBattery 的值设置为相同的值。 这同样适用于 DisplayOffTimeoutPluggedIn 和 StandbyTimeoutPluggedIn。 有关新式 [待机的](/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 更多详细信息，请参阅显示、睡眠和休眠空闲计时器。

### <a name="newly-enabled-update-policies-for-hololens"></a>新启用的更新策略HoloLens
- 有关安装更新或禁用"暂停更新"按钮以确保更新的更多选项。

这些更新策略现已在 HoloLens 2设备上启用：
-   [Update/ActiveHoursEnd](/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

有关这些更新策略以及如何将它们用于 HoloLens的完整详细信息，请参阅管理 HoloLens[更新](hololens-updates.md)。

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>已启用设置页面可见性HoloLens 2
- 增加了应用设置 UI 控件，这可能与显示有限的页面选择混淆。

现在，我们启用了一个策略，允许 IT 管理员阻止系统 设置 应用中的特定页面可见或可访问，或者针对除指定页面以外的所有页面启用此策略。 若要了解如何完全自定义此功能，请单击以下链接。

- [PageVisibilityList](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

若要了解可以在 HoloLens 2 自定义的页面设置，请访问 设置[URI 页](settings-uri-list.md)。 
 
![在“设置”应用中修改的使用时段的屏幕截图](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>研究模式
在研究模式下，HoloLens 2成为计算机视觉研究的重要工具。 与以前的版本相比，HoloLens 2研究模式具有以下优点：
-   除了第一代HoloLens (研究) 中公开的传感器，我们现在提供 IMU 传感器访问，包括加速计、陀螺仪和磁力计。
-   HoloLens 2提供可以与研究模式一起使用的新功能。 具体而言，可以访问可交付更丰富试验集的表达式手部跟踪和眼动跟踪 API。

研究人员现在可以选择在设备上启用研究模式HoloLens访问所有这些面向外部的原始图像传感器流。 研究模式HoloLens 2提供对加速计、陀螺仪和磁力计读数的访问。 为了保护用户的隐私，无法通过研究模式使用原始眼动跟踪相机图像，但可以通过现有 API 获得眼睛凝视方向。

有关更多 [技术详细信息，请查看](/windows/mixed-reality/research-mode) 研究模式文档。

### <a name="recording-length-increased"></a>录制长度增加
根据客户反馈，我们增加了混合现实捕获 [的录制长度](holographic-photos-and-videos.md)。 默认情况下，混合现实捕获将不再限制为 5 分钟，而是根据可用磁盘空间计算最大录制长度。 设备将基于可用磁盘空间估计最大视频录制持续时间，最多占总磁盘空间的 80%。

> [!NOTE]
> 如果HoloLens以下情况之一， (视频录制) 5 分钟：
> - 估计的最大录制持续时间小于默认的 5 分钟。
> - 可用磁盘空间小于总磁盘空间的 20%。

可以在全息照片和视频文档中 [找到完整](holographic-photos-and-videos.md#maximum-recording-length) 要求。 

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：
- OOBE 中的更多屏幕现在以深色模式显示。
- 了解更多内容应指向最新的联机隐私声明。
- 解决了用户无法通过预配包预配 VPN 配置文件的问题。
- 修复了 VPN 连接的代理配置问题。
- 更新了策略，以禁用通过适用于 NCM for AllowUsbConnection 的 MDM 枚举 USB 函数。
- 解决了当设备设置为单应用展台时，HoloLens设备无法通过媒体传输协议 (MTP) 在 文件资源管理器 中显示[的问题](hololens-kiosk.md)。 请注意，通常 (MTP 连接和 USB 连接) [AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 策略禁用。
- 修复了在展台模式下正确缩放"开始"菜单图标的问题。
- 修复了由于 HTTP 缓存干扰以组为目标的展台模式Azure AD问题。
- 修复了在预配包中启用开发人员模式后用户无法使用"配对"按钮的问题，除非用户禁用并重新启用开发人员模式。

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows全息版 1903 - 2020 年 11 月更新
- 内部版本 18362.1085

此每月质量更新不包含任何值得注意的更改，我们建议你试用 Holographic 版本 20H2 Windows的最新功能发布版本。

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows全息版 2004 - 2020 年 10 月更新
- 内部版本 19041.1124
 
更新中的改进和修复：

- 删除了导致运行时系统错误的不必要检查。

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows全息版 1903 - 2020 年 10 月更新
- 内部版本 18362.1081

此每月质量更新不包含任何值得注意的更改，建议试用 Holographic 版本 2004 Windows最新版本。

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows全息版 2004 - 2020 年 9 月更新
- 内部版本 19041.1117

更新中的改进和修复：

- 解决了当 appxmanifest Visual Studio SupportsMultipleInstances="true"时阻止用户调试应用程序的问题。
- 此版本包括 NCSI 代理检测修补程序，用于解决通过网络代理进行 Internet 检测失败的问题。 NCSI 可以使用计算机代理和按配置文件代理进行 Internet 连接检测。 NCSI 将在未来版本中支持每用户代理。
- 在大多数Windows Mixed Reality，当用户的头部处于向前的中性位置时，向前向向量与地面并行。 但是，早期版本的 HoloLens 2将矢量对齐为与显示面板垂直，而显示面板相对于理想方向向下倾斜几度。 较新版本的 HoloLens 2更正了此错误，以确保各外形因素之间的语义一致性。
- 改进了手部跟踪稳定性，这可减少特定方案中的跟踪损失。
- 此版本包含一个修补程序，用于提高音频时间戳质量，这可能会导致视频捕获问题。

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows全息版 1903 - 2020 年 9 月更新
- 内部版本 18362.1079

更新中的改进和修复：

- 在大多数Windows Mixed Reality，当用户的头部处于向前的中性位置时，向前向向量与地面并行。 但是，早期版本的 HoloLens 2将矢量对齐为与显示面板垂直，而显示面板相对于理想方向向下倾斜几度。 较新版本的 HoloLens 2更正了此错误，以确保各外形因素之间的语义一致性。
- 改进了手部跟踪稳定性，这可减少特定方案中的跟踪损失。

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows全息版 2004 - 2020 年 8 月更新
- 内部版本 19041.1113

更新中的改进和修复：

- 设置应用将不再跟随用户进入 Iris 注册或眼动跟踪校准体验。
- 修复了以下 bug：在 OOBE 期间应用预配包以重命名设备并执行其他操作 (例如连接到网络) 由于重命名，设备重启后将无法执行其他操作。
- 修改了初始设备设置流的配色方案，以提高视觉质量。

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows全息版 1903 - 2020 年 8 月更新
- 内部版本 18362.1074

此每月质量更新不包含任何值得注意的更改，建议试用 Holographic 版本 2004 Windows最新版本。

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows全息版 2004 - 2020 年 7 月更新
- 内部版本 19041.1109

更新中的改进和修复：

- 开发人员现在可以选择启用或禁用设备门户需要安全连接。
- 改进了 OS 更新后应用程序启动的可靠性。
- 将默认收件箱亮度更改为 100%。
- 解决了有关应用程序上 HTTPS 转发Windows 设备门户的问题HoloLens 2。

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows全息版 1903 - 2020 年 7 月更新
- 内部版本 18362.1071

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
    - LoopbackGain (Windows 设备门户中混合现实捕获页面上的当前 "应用音频增益" 值) 
    - MicrophoneGain (Windows 设备门户中混合现实捕获页面上的当前 "Mic 音频增益" 值) 
- 修复了一个 bug，以便在混合现实捕获方案中提高音频质量。 具体而言，当显示 " **开始** " 菜单时，此修复程序应消除录音 glitching。
- 改善了录制视频中的全息影像稳定性。
- 解决了在设备处于待机状态一段时间后混合现实捕获无法录制视频的问题。
- 对于 Unity 应用程序，通常禁用 HolographicSpace UserPresence API。 此行为可避免在向上翻转面板时导致某些应用暂停的问题，即使启用了 "在后台运行" 设置也是如此。 现在为 Unity 版本2018.4.18 和更高版本以及2019.3.4 和更高版本启用了 API。
- 通过 Wi-Fi 连接访问设备门户时，由于证书无效，web 浏览器可能会阻止访问。 即使之前信任设备证书，浏览器也可能会报告 "ERR_SSL_PROTOCOL_ERROR" 之类的错误。 在这种情况下，无法对设备门户进行进度，因为没有忽略安全警告的选项。 此更新解决了问题。 如果先前已在电脑上下载并信任设备证书以删除浏览器安全警告，并且发生 SSL 错误，则必须下载新证书并将其信任，以解决浏览器安全警告。
- 支持创建可通过使用 .MSIX 包安装应用的运行时预配包。
- 添加了 **设置**  >  **系统**  >  **全息影像** 中的设置，该设置允许用户在设备关闭时自动从混合现实总部删除所有全息影像。
- 修复了一个问题，该问题会导致在 HoloLens 模拟器中更改像素格式以呈现黑色 HoloLens 应用。
- 修复了 Iris 登录期间导致崩溃的 bug。
- 修复了有关现有应用的重复存储下载的问题。
- 修复了一个 bug，以防止沉浸式应用重复打开 Microsoft Edge。
- 修复了从1903版更新后初始启动时启动照片应用的问题。
- 提高了性能和可靠性。

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows全息版，版本 1903-2020 更新
- 生成18362.1064

更新中的改进和修复：

- 如果未指定自定义的 MRC 录像机，则为某些属性提供新的默认值。
  - 在 *MRC 视频效果*：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳机) ) 
  - 在 " *MRC 音频" 效果* 上：
    - LoopbackGain (Windows 设备门户中混合现实捕获页面上的当前 "应用音频增益" 值) 
    - MicrophoneGain (Windows 设备门户中混合现实捕获页面上的当前 "Mic 音频增益" 值) 
- 对于 Unity 应用程序，通常禁用 HolographicSpace UserPresence API。 此行为可避免当面板翻转时导致某些应用暂停的问题，即使启用了在后台运行的设置也是如此。 现在为 Unity 版本2018.4.18 和更高版本以及2019.3.4 和更高版本启用了 API。
- 修复了一个问题，该问题会导致 HoloLens 应用更改其像素格式，使其在 HoloLens Emulator 呈现为黑色。
- 修复了从1903版更新后初始启动时启动的照片应用程序的问题。

## <a name="windows-holographic-version-2004"></a>Windows全息版，版本2004  
- 版本-19041.1103

*Windows 全息版* HoloLens 2 的主要软件更新2020，版本2004包含一种令人兴奋的新功能，例如支持 Windows Autopilot、应用程序暗模式、USB 以太网支持 5G/LTE 热点，等等。 若要更新到最新版本，请打开 **设置**   应用，请参阅  **更新 & 安全**"，然后选择" **检查更新**"   按钮。 

|             功能                              |          说明                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          使用 Windows AutoPilot 预配置新设备并将其无缝设置为生产                 |
|       FIDO 2 支持                             |          支持 FIDO2 安全密钥，为共享设备启用快速和安全身份验证            |
|       改进的预配                      |          无缝地将预配包应用于 u 盘到 HoloLens                              |
|       应用程序安装状态                 |          在应用的设置应用中检查安装状态已通过 MDM 推送到 HoloLens 2               |
|       配置服务提供程序 (Csp)    |          添加了新的配置服务提供程序以增强管理员控制功能                 |
|       USB 5G/LTE 支持                       |          通过扩展 USB 以太网功能，支持 5G/LTE                                    |
|       深色应用模式                              |          适用于支持深色和浅色模式的应用的深色应用模式，从而改善了查看体验        |
|       语音命令                             |          支持其他系统语音命令，以控制 HoloLens 无人参与                           |
|       手动跟踪改进                 |          手动跟踪改进使按钮和2D 石板交互更准确                        |
|       质量改进和修复                 |          跨平台的各种系统性能和可靠性改进                            |

### <a name="support-for-windows-autopilot"></a>支持 Windows Autopilot

WindowsAutopilot for HoloLens 2 允许设备销售渠道 HoloLens 预注册到你的 Intune 租户。 设备到达后，它们就可以自行部署为租户下的共享设备。 若要利用自部署，设备必须在安装过程中的第一个屏幕上通过使用 USB 到以太网连接到网络。

用户启动 Autopilot 自行部署过程后，此过程将完成以下步骤：

1. 将设备加入 Azure Active Directory (Azure AD)。
1. 使用 Azure AD 在 Microsoft Intune (或其他 MDM 服务) 中注册设备。
1. 下载设备目标策略、证书和网络配置文件。
1. 预配设备。
1. 向用户展示登录屏幕。

有关详细信息，请参阅[Windows Autopilot for HoloLens 2 评估指南](hololens2-autopilot.md)。

*请联系你的帐户管理员立即加入 AutoPilot preview。即将开始交付 Autopilot 的设备。*

### <a name="fido2-security-key-support"></a>FIDO2 安全密钥支持

某些用户在工作或学校环境中与他人共享 HoloLens 设备。 因此，用户无需键入较长的用户名和密码，就很重要。 快速标识在线 (FIDO) 允许组织中的任何人 (Azure AD 租户) 无需输入用户名或密码即可无缝登录到 HoloLens。

FIDO2 安全密钥是一种基于标准的无密码身份验证方法，可采用任何外形规格。 FIDO 是无密码 authentication 的开放标准。 它允许用户和组织无需用户名或密码即可登录到其资源。 相反，它们使用内置于设备中的外部安全密钥或平台密钥。

若要开始，请参阅 [Enable 无密码 security key sign in](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>通过预配包改进了 MDM 注册

预配包使你可以通过配置文件而不是 HoloLens 全新体验来设置 HoloLens 配置。 以前，必须将预配包复制到 HoloLens 内部内存。 现在，它们可以位于 USB 驱动器上，因此可以更轻松地在多个 HoloLens 设备上重复使用，并且可以并行设置设备。 预配包现在还支持在设备管理中注册字段，因此预配后无需手动设置。

试试看：

1. 将最新版本的 Windows 配置设计器从 Windows 存储下载到电脑上。
1. 选择 **"HoloLens设备预配**  >  **HoloLens 2设备"。**
2. 生成配置文件。 然后将创建的所有文件复制到 USB-C 存储设备。
3. 将 USB-C 设备插入任何新刷入的HoloLens。 然后按 **音量关闭**  +  **电源** 按钮以应用预配包。

### <a name="line-of-business-application-install-status"></a>业务线应用程序安装状态

业务线应用的 MDM 应用部署和管理对于HoloLens。 管理员和用户需要查看应用安装状态，以便进行审核和诊断。 在此版本中，我们在"帐户访问工作或设置"单击帐户信息"中添加  >    >    >  **了**  >  **更多详细信息**。

### <a name="additional-csps-and-policies"></a>其他 CSP 和策略

CSP [ (配置) ](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) 是一个接口，用于读取、设置、修改或删除设备的配置设置。 在此版本中，我们添加了对更多策略的支持，以增加管理员对部署在设备上HoloLens控制。 有关云支持的 CSP 列表，HoloLens [NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp)。

本版本中的新主题：

**策略云解决方案提供商** 

策略配置服务提供程序使企业能够在设备Windows策略。 在此版本中，我们为 HoloLens添加了新策略，此处列出了这些策略。 若要了解有关详细信息，请参阅 HoloLens 2[支持的策略HOLOLENS 2。](/windows/client-management/mdm/policies-supported-by-hololens2)  

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

NetworkQoSPolicy 配置服务提供商使用 QoS 策略创建 (服务质量) 提供程序。 QoS 策略根据一组匹配的条件对网络流量执行一组操作。 有关详细信息，请参阅 [NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp)。

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>扩展了对 5G/LTS 网络设备的 USB 以太网支持

添加了支持，以启用某些移动宽带设备，例如 5G/Wi-Fi手机和 Wi-Fi 热点（当它们通过 USB HoloLens 2连接时）。 这些设备现在在网络设置 **中显示为** 另一个以太网连接。  (不支持需要外部驱动程序的移动宽带设备。) 当 Wi-Fi 不可用且网络Wi-Fi性能不足时，此功能可实现高带宽连接。 若要详细了解支持的 USB 设备，请参阅 连接[蓝牙 和 USB-C 设备](hololens-connect-devices.md)。  

### <a name="hand-tracking-improvements"></a>手部跟踪改进

此版本包括多项手动跟踪改进：

- **指向姿势稳定性：** 现在，当手指被手指遮挡时，系统可以抵御手指的滑动。 此更改提高了按下按钮、键入、滚动内容等时的准确性！ 
- **减少了意外的敲击：** 改进了对敲击手势的检测。 现在，在多种常见情况下（例如，将手放在两侧时）中的意外激活更少。
- **用户交换机可靠性：** 现在，共享设备时，系统在更新手部大小时速度更快且更可靠。
- **减少手部窃取：** 改进了传感器视图超过两手的情况的处理。 如果多人在一起工作，现在跟踪手从用户"跳转"到场景中其他人手的可能性要低得多。
- **系统可靠性：** 修复了在设备负载较高时导致手部跟踪停止工作的问题。

### <a name="dark-mode"></a>深色模式

许多Windows应用现在都支持深色和浅色模式。 HoloLens 2用户可以为支持这两者的应用选择默认模式。 更新后，默认应用模式为"深色"，**但** 可以轻松更改此设置：导航到"设置  >    >    >  **选择默认应用模式"。** 

这些"盒中"应用支持深色模式： 

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

现在可以对设备上的任何应用使用语音命令。 有关详细信息，请参阅[使用语音操作HoloLens。](hololens-cortana.md) 另请参阅[支持的语言HoloLens 2。](hololens2-language-support.md)  

### <a name="cortana-updates"></a>Cortana更新

更新后的应用与 Microsoft 365 集成，可帮助你跨设备完成更多操作 (当前仅US-English) 。 在HoloLens 2，Cortana不再支持某些特定于设备的命令，例如调整卷或重启。 新的系统语音命令现在支持这些选项。 在我们的博客 中[Cortana新应用](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)。

### <a name="quality-improvements-and-fixes"></a>质量改进和修复

更新中的改进和修复：  
- 引入了主动显示校准系统。 此功能可提高全息影像的稳定性和对齐方式。 现在，当你将头部从一侧移到另一侧时，它们就位。
- 修复了一个 bug，Wi-Fi流式HoloLens定期中断。 如果应用程序指示它需要低延迟流式处理，请通过调用 [SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)函数 来实现修复。
- 修复了在研究模式下流式传输期间发生的设备挂起。
- 修复了以下 bug：在某些情况下，恢复会话时不会在登录屏幕上显示正确的用户。
- 修复了用户无法通过 设置 导出 MDM **日志的问题**。
- 修复了以下问题：在开箱即用设置后立即进行眼动跟踪的准确性可能低于预期。
- 修复了在某些情况下眼动跟踪子系统无法初始化或执行校准的问题。
- 修复了提示已校准用户的眼部校准问题。
- 修复了驱动程序在眼部校准期间崩溃的问题。
- 修复了重复按下电源按钮可能导致 60 秒系统超时和 shell 崩溃的问题。
- 改进了深度缓冲区的稳定性。
- 在" **共享** "按钮反馈中心，以便用户可以更轻松地共享反馈。
- 修复了 RoboRaid wan 未正确安装的 bug。

### <a name="known-issues"></a>已知问题

- zh-CN 系统语言的问题阻止语音命令捕获混合现实或显示设备 IP 地址。
- 问题要求在启动设备Cortana"Hey Cortana"语音激活后启动应用。 如果从 18362 版本更新，则还可以在"启动"中看到以前版本的 Cortana 应用的第二个应用 **磁贴**。

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows全息版 1903 - 2020 年 5 月更新 
- 内部版本 18362.1061

此每月质量更新不包含任何值得注意的更改，因为团队正在处理全息Windows 2004 年 5 月更新，如前文所述。

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows全息版 1903 - 2020 年 4 月更新
- 内部版本 18362.1059

**受支持应用的深色模式** 

许多Windows应用都支持深色和浅色模式。 HoloLens 2客户现在可以为支持这两种配色方案的应用选择默认模式。 根据客户反馈，我们将默认应用模式设置为"深色"，但你随时可以轻松更改此设置：导航到 **设置 > System > Colors** 以查找"选择 **默认** 应用模式"。

这些"盒中"应用支持深色模式：
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

**更新中的改进和修复：** 
- 确保混合现实捕获中包含 shell 覆盖。
- Unreal 开发人员现在可以使用 设备门户中的"3D 视图"页来测试和调试其应用程序。
- 改进了使用 *HolographicDepthReprojectionMethod DepthReprojection* 算法时混合现实捕获中的全息影像稳定性。
- 修复了 32 位 ARM 应用上的"WinRT IStreamSocketListener API 类未注册"错误。

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows全息版 1903 - 2020 年 3 月更新 
- 内部版本 18362.1056

更新中的改进和修复：

- 改进了使用 *HolographicDepthReprojectionMethod AutoPlanar* 算法时混合现实捕获中的全息影像稳定性。
- 确保附加到深度 MF 样本的坐标系与公共文档一致。
- 通过让客户通过设备门户粘贴大量文本，提高了开发人员的工作效率。

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows全息版 1903 - 2020 年 2 月更新 
- 内部版本 18362.1053

更新中的改进和修复：

- 暂时禁用了 Unity 应用程序的 HolographicSpace.UserPresence API。 此更改可避免在视器翻转时导致某些应用暂停的问题，即使启用了"在后台运行"设置。
- 修复了手动跟踪导致的随机 HUP 崩溃，其中用户注意到 UI 冻结，然后在几秒钟后返回到 shell。
- 改进了手部跟踪，以便当你用手指触摸时，该手指的上半部分不太可能意外地卷曲。
- 改进了头部跟踪、空间映射和其他运行时的可靠性。

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows全息版 1903 - 2020 年 1 月更新 
- 内部版本 18362.1043
 
更新中的改进和修复：

- 改进了使用专用仿真器时排他HoloLens 2的稳定性。

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows全息版 1903 - 2019 年 12 月更新 
- 内部版本 18362.1042

更新中的改进和修复：

- 引入了 LSR (的最后) 重现。 改进了全息影像的视觉呈现，通过更准确地计算其深度来显示更稳定、更简洁。 如果应用没有正确设置全息影像的深度，则此症状在此更新后会更明显。
- 修复了独占应用的稳定性和独占应用之间的导航。
- 解决了混合现实捕获在设备处于待机状态数天后无法录制视频的问题。
- 提高了全息影像稳定性。

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows全息版 1903 - 2019 年 11 月更新 
- 内部版本 18362.1039

更新中的改进和修复：

- 修复了在 **en-CA** 和 en-AU 的初始设置过程中选择语音命令的功能。
- 改进了放置在最新 Unity 和混合现实中的对象的视觉质量Toolkit (MRTK) 版本。
- 修复了全息应用程序在启动时停滞在暂停状态的问题，"开始"菜单打开然后关闭。
- OpenXR 运行时针对 HoloLens 2 仿真程序的一致性修复和改进。
