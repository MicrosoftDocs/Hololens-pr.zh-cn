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
ms.date: 9/8/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: f27a469e76df1ccf29a2823b48f3640bdf414050
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032150"
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
> 随着 Holographic Windows 21H1 的推出，我们将停止为全息版 **1903** Windows每月服务更新。 这使我们能够专注于较新版本，并继续提供有价值的改进。


| 功能名称                                              | 简短说明                                                                      | 目标读者 | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新的 Microsoft Edge](#introducing-the-new-microsoft-edge)  | 新的基于 Chromium 的 Microsoft Edge 现可用于 HoloLens 2。 | 最终用户 | 
[WebXR 和 360 Viewer](#webxr-and-360-viewer) | 尝试沉浸式 Web 体验和 360 视频播放。 | 最终用户 | 
[新“设置”应用](#new-settings-app) | 旧版设置应用将被更新版本替换为新功能和设置。 | 最终用户 |
[显示颜色校准](#display-color-calibration) | 为 HoloLens 2 屏幕选择替代颜色配置文件。 | 最终用户 |
[默认应用选取器](#default-app-picker) | 选择应针对每个文件或链接类型启动的应用。 | 最终用户 |
[每个应用音量控制](#per-app-volume-control) | 独立于系统卷控制应用级别卷。 | 最终用户 |
[安装 Web 应用](#install-web-apps) | 使用新的 Microsoft Edge 浏览器在 HoloLens 2（例如 Microsoft Office）上安装 Web 应用。 | 最终用户 |
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
[新的 OS 诊断跟踪](#new-os-diagnostic-traces) | OS 更新设置中的新疑难解答。 | IT 管理员 |
[传递优化预览版](#delivery-optimization-preview) | 减少从多个设备下载的带宽HoloLens消耗。 | IT 管理员 |

请查看相关的发行说明：

- [访问 HoloLens Emulator 存档](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>新版 Microsoft Edge 简介

![旧版 Microsoft Edge 徽标动画升级为新版 Microsoft Edge 徽标动画。](images/new-edge.gif)

新版 Microsoft Edge [采用 Chromium 开源项目](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/)，为客户提供更好的兼容性，同时为 Web 开发人员减少 Web 碎片。

> [!IMPORTANT]
> 新版 Microsoft Edge 会自动替换旧版 Microsoft Edge，新版本中[不再支持](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/)旧版 Microsoft Edge。

![新版 Microsoft Edge 屏幕截图。](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>启动新版 Microsoft Edge

新的 Microsoft Edge ![新版 Microsoft Edge 图标。](images/new_edge_logo.png) （由蓝绿色漩涡图标表示）固定在“开始”菜单上，并将在你激活 Web 链接时自动启动。

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

**最常见的浏览器已知问题：**

- 全息键盘中的放大镜预览在新版 Microsoft Edge 中被禁用。 我们希望等放大功能恢复正常后，在未来的更新中重新启用此功能。
- 如果有其他浏览器窗口打开并处于活动状态，则音频可能会从错误的浏览器窗口播放。 通过关闭不应播放音频的其他活动窗口，可以解决此问题。
- 在 ["关注我" 模式下](hololens2-basic-usage.md#follow-me-stop-following)从浏览器窗口播放音频时，如果禁用 "关注我" 模式，则音频将继续播放。 可以通过在禁用 "关注我" 模式之前停止音频播放，或通过使用 **X** 按钮关闭窗口，来解决此问题。
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

    ![“进入 VR”按钮示例。](images/75px-enter-vr.png)

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

    ![激活 360 Viewer 的按钮。](images/enter-360-viewer.jpg)

1. 首次尝试在特定域上启动 360 Viewer 时，浏览器将询问你是否同意进入沉浸式视图。 选择“允许”。
1. [隔空敲击](hololens2-basic-usage.md#select-using-air-tap)以打开播放控件。 使用[手部射线和隔空敲击](hololens2-basic-usage.md#select-using-air-tap)来播放/暂停、快进/后退、打开/关闭字幕或停止体验（该操作会退出沉浸式视图）。 播放控件将在保持几秒的非活动状态后消失。

#### <a name="top-webxr-and-360-viewer-known-issues"></a>WebXR 和 360 Viewer 常见已知问题
- 根据 WebXR 体验的复杂度，帧速率可能下降或卡顿。
- 默认情况下，WebXR 中不支持铰接式手关节。 开发人员可以 `edge://flags` 通过打开 "WebXR 手型输入" 启用支持。
- YouTube 网站之外的 360 度视频可能无法按预期运行。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>提供关于 WebXR 和 360 Viewer 的反馈

请通过新版 Microsoft Edge 中的“发送反馈”功能与我们的团队分享反馈和错误。

### <a name="new-settings-app"></a>新“设置”应用

在此版本中，我们引入了新版本的设置应用。 新的“设置”应用包括 HoloLens 2 在以下领域的新功能和扩展设置：声音、电源和休眠、网络和 Internet、应用、帐户、轻松访问等。

> [!NOTE]
> 由于新的“设置”应用不同于旧版“设置”应用，因此，此前围绕环境放置的任何“设置”窗口都将在更新时删除。

![新“设置”应用主页。](images/new-settings-app.png)

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



借助此新设置，可以选择其他颜色配置文件来显示HoloLens 2配置文件。 这可以帮助显示更准确的颜色，尤其是在较低的屏幕亮度级别。 显示颜色校准可在"系统设置校准"页上的">应用中找到。

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

    ![显示颜色校准场景。](images/color-cal-ui.png)
    
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

- 在"设置"页上，指示上次更改颜色配置文件时间的状态字符串将过期，直到重新加载该页设置。
    - 解决方法：选择另一个“设置”页面，然后重新选择“校准”页面。

#### <a name="default-app-picker"></a>默认应用选取器

激活超链接或打开具有多个已安装应用（支持它）的文件类型时，将看到一个新窗口打开，提示你选择哪个已安装的应用应处理文件或链接类型。 在该窗口中，还可以选择选定的应用“一次”或“始终”处理文件或链接类型。

如果选择“始终”，但以后想要更改处理特定文件或链接类型的应用，可以在“设置”>“应用”中重置设置默认值。 滚动到页面底部，然后选择“文件类型的默认应用”和/或“链接类型的默认应用”下的“清除”按钮。 与台式电脑类似设置不同的是，无法重置单个文件类型默认值。

#### <a name="per-app-volume-control"></a>每个应用音量控制

现在在此Windows中，用户可以手动调整每个应用的卷级别。 这样，用户可以更好地关注他们所需要的应用，或者在使用多个应用时能更清晰地听到。 例如，在呼叫另一个人寻求远程帮助时降低其中一个应用的音量。

若要设置单个应用的音量，请导航到“设置” -> “系统” -> “声音”，然后在“高级”声音选项中选择“应用音量和设备首选项”。<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>轻扫以键入

一些客户发现，通过轻扫要键入的单词的形状，在虚拟键盘上"键入"速度更快，我们正在预览全息键盘的此功能。 可以通过将手指的尖通过全息键盘的平面、轻扫单词的形状，然后从键盘平面中收回手指的尖，一次轻扫一个词。 通过在键盘上删除单词之间的手指，无需按删除键就可以轻扫后面的单词。 如果在键盘上看到轻扫轨迹按照手指移动，你将知道该功能正在运作。

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

当更新可用时，省略号图标将亮起，指示重启将安装更新 菜单选项也会更改以反映更新的存在。<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>登录屏幕上列出的多个用户

以前，"登录"屏幕只显示最近登录的用户，以及"其他用户"入口点。 我们已收到客户反馈，如果多个用户已登录到设备，这是不够的。 他们仍然需要重新键入其用户名等。

本Windows中引入，在选择"PIN 输入"字段右侧"其他用户"时，"登录"屏幕将显示以前已登录到设备的多个用户。 这允许用户选择其用户配置文件，然后使用其凭据Windows Hello登录。 还可通过"添加帐户"按钮从此"其他用户"页将新 **用户添加到** 设备。

在"其他用户"菜单中，"其他用户"按钮将显示最后一个登录到设备的用户。 选择此按钮可返回到此用户的"登录"屏幕。

![默认登录屏幕。](./images/multiusers1.jpg)

<br>

![其他用户的登录屏幕。](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 外置麦克风支持

> [!IMPORTANT]
> 插入 **USB 麦克风不会自动将其设置为输入设备**。 在插入一组 USB-C 耳机时，用户将观察到耳机的音频将自动重定向到耳机，但 HoloLens OS 会将内部麦克风阵列的优先级设置为高于任何其他输入设备。 若要使用 USB-C 麦克风，请执行以下步骤。

用户可以使用“声音”设置面板选择 USB-C 连接的外置麦克风。 USB-C 麦克风可用于呼叫、录制等。

打开“设置”应用并选择“系统” > “声音”。

![声音设置。](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 若要将外置麦克风用于 Remote Assist，用户需要单击“管理声音设备”超链接。
>
> 然后，使用下拉菜单将外置麦克风设置为“默认值”或“通信默认值”。 选择“默认值”表示将在任何位置使用外置麦克风。
>
> 选择“通信默认值”表示将在 Remote Assist 和其他通信应用中使用外置麦克风，但 HoloLens 麦克风阵列仍可用于其他任务。

![管理声音设备。](images/usbc-mic-2.png)

<br>

![设置麦克风默认值。](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support&quot;></a>蓝牙麦克风支持怎么样？

遗憾的是，HoloLens 2 当前不支持蓝牙麦克风。

#### <a name=&quot;troubleshooting-usb-c-microphones&quot;></a>USB-C 麦克风疑难解答

请注意，某些 USB-C 麦克风会错误地将自身报告为麦克风 *和* 扬声器。 这是麦克风问题，而不是 HoloLens。 将其中一个麦克风插入 HoloLens 时，可能会丢失声音。 幸运的是，有一个简单的修补程序。  

在 **设置**  ->  **系统**  ->  **声音**&quot;中，将内置扬声器 **(模拟功能音频驱动程序")** 为 **默认设备**。 即使稍后会删除并重新连接麦克风，HoloLens 也应记住此设置。

![USB-C 麦克风故障排除。](images/usbc-mic-4.png)

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

除了之前在 设置 应用中的疑难解答外，还添加了新的疑难解答，并添加了新的 设置 应用进行 OS 更新。 导航到 **"设置**  ->  **&amp; 安全更新故障排除**  >    >  **Windows"，然后选择**"启动 **"。** 这样，在重现 OS 更新问题时可以收集跟踪，以更好地帮助 IT 或支持人员进行故障排除。

### <a name="delivery-optimization-preview"></a>传递优化预览版

通过此HoloLens更新，Windows Holographic for Business启用传递优化设置，以减少从多个设备下载的HoloLens消耗。 此处提供了此功能的更完整说明以及建议的网络配置：[Windows 10 更新的传递优化](/windows/deployment/update/waas-delivery-optimization)。

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

如果以前在展台设置应用或 Microsoft Edge 应用，我们将这些应用替换为使用不同的应用 ID 的新应用。 强烈建议阅读下面的展台模式下的新[应用的新 AUMID。](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 这将确保展台中继续设置应用，或包括新的 Microsoft Edge 应用。 现在可以完成这些更改，并部署到所有设备，并允许在更新时更顺畅地转换。

✔️ [**展台的访问者自动登录：**](#visitor-auto-logon-for-kiosks) 

访问者现在可以自动登录到展台。 默认情况下，此行为处于启用状态，但可以管理和禁用。

✔️ [**改进的展台模式故障切换**](#kiosk-mode-behavior-changes-for-handling-of-failures)：

如果未成功确定已登录 AAD 用户的 AAD 组成员身份，则全局展台配置用于开始菜单 (如果存在) 则向用户显示空的开始菜单。 虽然空的开始菜单不是可直接设置的配置，但如果使用的是展台，则此新处理可能会通知支持部门，因为这可能适用于配置，或者你可能希望对分配的访问配置进行新的调整。

#### <a name="updates-to-page-settings-visibility"></a>页面和可见性设置更新

✔️ [**页面设置可见性的新 设置 URI**](#new-settings-uris-for-page-settings-visibility)

如果当前[正在使用"页面](settings-uri-list.md)设置可见性"，可能需要调整已允许或阻止的现有 URI。

#### <a name="updates-for-your-wdac-policy"></a>WDAC 策略的更新
✔️如果以前阻止Microsoft Edge WDAC，需要更新 WDAC 策略。 请查看以下内容并使用提供的示例代码。
#### <a name="enable-new-endpoints-for-edge"></a>为 Edge 启用新终结点
✔️如果基础结构涉及配置网络终结点（如代理或防火墙），请为新的应用启用Microsoft Edge终结点。

#### <a name="newly-configurable-items"></a>新可配置的项

✔️ [配置回退诊断](#configuring-fallback-diagnostics-via-settings-app)：可以配置是否收集回退诊断以及收集回退诊断的人。

✔️[附近设备](#share-things-with-nearby-devices)共享内容：可以禁用新的附近共享功能。

✔️[配置新应用的策略Microsoft Edge：](#configuring-policy-settings-for-the-new-microsoft-edge)查看可用于新Microsoft Edge。

#### <a name="new-diagnostic-tool"></a>新的诊断工具

✔️[新的 OS 诊断跟踪：](#new-os-diagnostic-traces)收集与 OS 更新相关的日志。

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
- 此每月质量更新不包含任何值得注意的更改，建议试用最新内部版本（Windows全息版 21H1）。

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
- 从设备中删除了 eSIM 根存储中未使用的HoloLens证书。

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows全息版 1903 - 2021 年 2 月更新
- 内部版本 18362.1098

此每月质量更新不包含任何值得注意的更改，建议试用 Holographic 版本 2004 Windows最新版本。

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows全息版 20H2 - 2021 年 1 月更新
- 内部版本 19041.1134

更新中的改进和修复：

- 改进了在设备上有许多用户时启动、恢复和用户切换期间的性能。
- 为 [研究模式](/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)添加了 arm32 支持。

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows全息版，版本 1903-2021 更新
- 生成18362.1091

这一月度质量更新不包含任何显著的更改，我们建议你试用 Windows 全息版本2004的最新版本。

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows版本20H2 –2020年12月更新
- 生成19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>在 HoloLens 2 通过应用安装程序安装应用

我们正在 **添加新功能 (应用安装程序) ，使你能够在 HoloLens 2 设备上更无缝地安装应用程序**。 **默认情况下，对于非托管设备**，此功能将处于启用状态。 若要防止企业中断，此时将不能 **为托管设备提供** 应用安装程序。  

如果满足以下 **任一** 条件，则将设备视为 "托管"：
- 已[注册](hololens-enroll-mdm.md)MDM
- 配置了 [预配包](hololens-provisioning.md)
- 用户 [标识](hololens-identity.md) Azure AD

你现在可以安装应用，而无需启用开发人员模式或使用设备门户。  只需通过 USB 或边缘) Appx 包下载到设备的 (，然后在文件资源管理器中导航到 Appx 捆绑，系统将提示开始安装。  或者， [通过网页启动安装](/windows/msix/app-installer/installing-windows10-apps-web)。  与使用 MDM 的 LOB 应用部署功能从 Microsoft Store 或旁加载安装的应用一样，应用需要使用[签名工具](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)进行数字签名，并且必须在部署应用之前，HoloLens 设备[信任用于签署的证书](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)。

**应用程序安装说明。**

1.  确保你的设备不被视为托管设备
1.  确保 HoloLens 2 设备已打开并已连接到你的电脑
1.  确保已登录到 HoloLens 2 设备
1.  在电脑上导航到自定义应用，并将 yourapp 复制到 yourdevicename\Internal 存储 \Downloads。   完成文件复制后，可以断开与设备的连接
1.  在 HoloLens 2 设备中打开 "开始" 菜单，选择 "所有应用"，然后启动 "文件资源管理器" 应用。
1.  导航到 "下载" 文件夹。 你可能需要在应用程序的左侧面板上选择 "此设备"，然后导航到 "下载"。
1.  选择 yourapp 文件。
1.  应用程序安装程序将启动。 选择 "安装" 按钮以安装您的应用程序。
安装完成后，安装的应用将自动启动。

若要测试此流，可以在[Windows 通用示例 GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)上找到示例应用。

阅读有关[在 HoloLens 2 上安装](app-deploy-app-installer.md)应用程序的完整过程。  

![通过应用安装程序安装 MRTK 示例。](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：

- 手动跟踪现在可以在很多新情况下维护跟踪，这种情况先前会丢失。  在其中一些新情况下，只会根据用户的真实情况继续更新手掌位置，而其他联系则基于上一个姿势进行推断。  此更改有助于改进跟踪的一致性，例如 slapping、抛出、scooping 和拍手。  它还有助于在手接近某个表面或持有对象的情况下使用。  当推理出手动联接时，" [每个联合准确性](/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) " 值将设置为 "近似" 而不是 "高"。
- 修复了 Azure AD 帐户的 PIN 重置会显示错误 "出现错误的问题。
- 从 "设置" 应用、"新建用户" 或 "通知 toast" 启动 ET、Iris 时，用户应会看到更少的引导后 OOBE 崩溃。
- 用户应具有来自 OOBE 的正确时区。

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows全息版，1903– 12 2020 月更新
- 生成18362.1088

这一每月质量更新不包含任何显著的更改，我们建议你试用最新的 Windows 全息版20H2 –2020年12月更新和在生成中添加的新应用安装程序功能。


## <a name="windows-holographic-version-20h2"></a>Windows全息版20H2
- 生成19041.1128

Windows现在可以使用全息版20H2，并为用户和 IT 专业人员提供了一套丰富的新 HoloLens 2 功能。 从自动目视定位到设置中的证书管理器，到改进的展台模式功能和新的 Autopilot 设置功能。 这一新的更新使 IT 团队能够更精细地控制如何配置和管理 HoloLens 设备，并为用户提供更无缝的无缝体验。 

此最新版本是对版本2004的每月更新，但这次我们将包括新功能。 主要内部版本号将保持不变，Windows 更新将指示每月版本 2004 (版本 19041) 。 你可以在设置 > 的屏幕上查看生成号，以确认你在19041.1128 的最新版本。 若要更新到最新版本，请打开设置应用，请单击 "更新 & 安全"，然后点击 "检查更新"。 有关如何管理 HoloLens 更新的详细信息，请访问[管理 HoloLens 更新](hololens-updates.md)。

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows 全息版20H2 的新增功能  

| Feature                                              | 说明                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [自动眼部位置支持](hololens-release-notes.md#auto-eye-position-support) | 主动计算眼睛位置，无需用户通过目视跟踪校准。   |
| [证书管理器](hololens-release-notes.md#certificate-manager)   | 允许新的更简单方法从设置应用安装和删除证书。     |
| [从 USB 自动启动设置](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | 在 USB 驱动器上预配包会自动提示 OOBE 中的设置页面。                                                         |
| [自动确认在 OOBE 中预配包](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 预配页面会在 OOBE 期间自动应用预配包。                                                         |
| [无需使用 UI 即可自动预配](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 如何将设置自动启动和自动确认组合在一起。 |
| [将 Autopilot 与 Wi-Fi 连接结合使用](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | 从设备 Wi-Fi 使用 autopilot，无需使用以太网适配器。 |
| [Tenantlockdown 云解决方案提供商和 Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | 应用租户注册并应用策略后，在设备重置或重新刷新时，设备只能在该租户中注册。 |
| [全局分配的访问权限](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | 适用于多个 app 展台模式的新配置方法，它在系统级别应用展台，使其适用于所有内容。                  |
| [在多应用展台中自动启动应用](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 将应用程序设置为在登录到多应用展台模式时自动启动。                                                        |
| [用于处理故障的展台模式行为更改](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 展台模式故障现在具有限制的回退。                                                                                                |
| [HoloLens政策](hololens-release-notes.md#hololens-policies)                                    | HoloLens 的新策略。     |
| [缓存 Azure AD 脱机展台的组成员身份](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 新策略允许用户使用 "组成员身份缓存" 在设置的天数内脱机使用展台模式。                                        |
| [HoloLens 2 的新设备限制策略](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | 为 HoloLens 2 启用了新启用的设备管理策略。                                                                                |
| [HoloLens 2 的新电源策略](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 最新支持的电源超时设置策略。  |
| [更新策略](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 允许控制更新的新启用的策略。           |
| [已启用 HoloLens 2 的设置页面可见性](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 用于选择在设置应用中出现哪些页的策略。             |
| [研究模式](hololens-release-notes.md#research-mode) | 在 HoloLens 2 上使用研究模式。 |
| [记录长度增加](hololens-release-notes.md#recording-length-increased) | MRC 记录不再超过5分钟。 |
| [更新中的改进和修复](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新中的其他修补程序。   |

### <a name="auto-eye-position-support"></a>自动眼部位置支持

在 HoloLens 2 中，目视定位可实现准确的全息影像定位、舒适的观看体验，并改善了显示质量。 眼部位置在内部计算，作为眼球跟踪计算的一部分。 但是，这要求每个用户都可以通过眼球跟踪校准，即使体验可能不需要眼睛凝视输入也是如此。

自动眼部位置 (AEP) 使这些场景能够以无交互方式为用户计算眼部位置。 自动眼睛位置从用户打开设备那一刻开始自动在后台工作。 如果用户没有以前的眼动跟踪校准，则自动眼部定位将在处理 20 - 30 秒后开始向显示系统提供用户眼睛位置。 用户数据不会持久保存在设备上，因此，如果用户关闭并重新启动设备，或者设备重新启动或从睡眠状态唤醒，则重复此过程。

当未经校准的用户戴上设备时，“自动眼部位置”功能会改变一些系统行为。 在此上下文中，未校准的用户是指以前未在设备上完成眼动跟踪校准过程的用户。

| 活动应用程序 | 先前行为 | Windows 全息版 20H2 更新的行为 |
|:-------------------|:-----------------|:-----------------------------------|
| 未启用凝视的应用或全息外壳 |“眼球跟踪校准提示”对话框随即显示。 | 不显示提示。 |
| 启用了凝视的应用 | “眼球跟踪校准提示”对话框随即显示。 | 仅当应用程序访问眼睛凝视流时，才会显示眼球跟踪校准提示。 |

如果用户从未启用凝视的应用程序转换为访问凝视数据的应用程序，则会显示校准提示。 

当当前用户没有活动的眼动跟踪校准时，所有其他系统行为将类似于 。 例如，不会启用单手启动手势。 初始设置的全新体验不会有任何变化。

对于需要眼睛凝视数据或非常精确的全息影像定位的体验，我们建议未校准的用户运行眼动跟踪校准。 可从眼动跟踪校准提示符访问它，或者从开始菜单中启动 设置 应用，然后选择"系统 >**校准>** 眼>校准"。

稍后可与其他校准信息 [一起找到此信息](hololens-calibration.md#auto-eye-position-support)。 

### <a name="certificate-manager"></a>证书管理器

- 通过新的证书管理器改进了设备安全性和符合性的审核、诊断和验证工具。 此功能可让你在商业环境中大规模部署、排查和验证证书。

在Windows 20H2 版中，我们将在 HoloLens 2 设置 应用中添加证书管理器。 转到 **"设置 >更新&安全>证书"。** 此功能提供了一种简单且用户友好的方式来查看、安装和删除设备上证书。 借助新的证书管理器，管理员和用户现在改进了审核、诊断和验证工具，以确保设备保持安全且合规。 

-   **审核：** 能够验证证书是否正确部署，或确认证书已正确删除。 
-   **诊断：** 出现问题时，验证设备上是否存在相应的证书可节省时间，并有助于进行故障排除。 
-   **验证：** 验证证书是否符合预期目的且正常运行，可以节省大量时间，尤其是在商业环境中，然后再大规模部署证书。

若要在列表中快速查找特定证书，有一些选项可以按名称、存储或到期日期进行排序。 用户还可以直接搜索证书。 若要查看单个证书属性，请选择证书，然后单击"信息 **"。** 

证书安装当前支持 .cer 和 .crt 文件。 设备所有者可以在本地计算机和当前用户中安装证书; 所有其他用户只能安装到当前用户中。 用户只能从应用程序 UI 中删除设置证书。 如果证书是通过其他方式安装的，则还必须使用相同的机制将其删除。

#### <a name="to-install-a-certificate"></a>安装证书： 

1.  连接HoloLens 2电脑。
1.  将要安装的证书文件放在证书HoloLens 2。
1.  导航到 **设置应用>更新&安全>证书"，** 然后选择"安装证书"。
1.  单击 **"导入** 文件"并导航到保存证书的位置。
1.  选择"**存储位置"。**
1.  选择 **"证书存储"。**
1.  单击“安装”  。

现在应在设备上安装证书。

#### <a name="to-remove-a-certificate"></a>删除证书： 
1. 导航到 **设置应用>更新和安全>证书"**。
1. 在搜索框中按名称搜索证书。
1. 选择证书。
1. 单击" **删除"**
1. 出现确认提示时，选择“是”。

![证书应用中的设置查看器。](images/certificate-viewer-device.jpg)

![显示如何使用证书 UI 安装证书的图片。](images/certificate-device-install.jpg)

稍后可在新的"证书管理器 ["页上找到此信息](certificate-manager.md)。

### <a name="auto-launch-provisioning-from-usb"></a>从 USB 自动启动预配

- 在 OOBE 期间使用带预配包的 USB 驱动器时，自动化过程允许较少的用户交互。

在此版本之前，用户必须手动在 OOBE 期间启动预配屏幕，才能使用按钮组合进行预配。 现在，用户可以通过使用 USB 存储驱动器上的预配包跳过按钮组合。 

1. 在 OOBE 的第一个可交互时刻使用预配包插入 USB 驱动器
1. 当设备准备好进行预配时，它会自动打开包含预配页的提示。 

注意：如果在设备启动时 USB 驱动器已接通电源，则 OOBE 将枚举现有的 USB 存储设备，并监视插入的其他 USB 存储设备。

有关在 OOBE 期间应用预配包的信息，请访问HoloLens[文档](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

有关从[USB](hololens-provisioning.md#auto-launch-provisioning-from-usb)自动启动预配的其他信息，请参阅HoloLens预配文档。

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>在 OOBE 中自动确认预配包
- 自动化过程允许较少的用户交互，当显示"预配包"页时，它将自动应用列出的所有包。

当预配主屏幕出现时，OOBE 将倒计时 10 秒，然后自动开始应用所有预配包。 在验证 [预期的包](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) 后，用户仍然可以在此 10 秒内确认或取消。

### <a name="automatic-provisioning-without-using-ui"></a>无需使用 UI 即可自动预配
- 组合了自动过程，减少了预配的设备交互。 

通过将从 USB 设备自动启动预配和自动确认预配包相结合，用户可以自动预配 HoloLens 2 设备，而无需使用设备的 UI，甚至无需设备。 你可以继续为多个设备使用相同的 USB 驱动器和预配包。 这可用于在同一区域中一次部署多个设备。 

1. [使用配置设计器](hololens-provisioning.md)创建[Windows包](https://www.microsoft.com/store/productId/9NBLGGH4TX22)。 
1. 将包复制到 USB 存储驱动器。
1. [将HoloLens 2](hololens-insider.md#ffu-download-and-flash-directions)刷新到[19041.1361 或更高版本。](https://aka.ms/hololens2previewdownload) 
1. 高级 [恢复助手](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 完成刷用设备后，拔下 USB-C 电缆。 
1. 将 USB 驱动器插入设备。
1. 当HoloLens 2设备启动到 OOBE 时，它会自动检测 USB 驱动器上的预配包并启动预配页。
1. 10 秒后，设备将自动应用预配包。 

设备现已配置，将显示 ["预配成功"屏幕](hololens-provisioning.md#automatic-provisioning-without-using-ui)。

### <a name="using-autopilot-with-wi-fi-connection"></a>将 Autopilot 与 Wi-Fi连接一起使用
- 通过使 Autopilot 在连接的设备上运行，无需使用 USB-C 适配器Wi-Fi硬件需求。

现在，在 OOBE 期间，HoloLens 2连接到 Wi-Fi 后，OOBE 将检查设备的 Autopilot 配置文件。 如果找到一个，它将用于完成 AAD 联接和注册流的其余部分。 换句话说，不再要求使用以太网到 USB-C 或Wi-Fi连接到 USB-C 适配器，但如果在 OOBE 开始时提供，它们将继续工作。 详细了解适用于[设备 HoloLens 2 Autopilot。](hololens2-autopilot.md)

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown 云解决方案提供商和 Autopilot
- 通过锁定组织租户上的设备，即使设备重置或重启，也可以将设备锁定到租户中。 通过禁止通过预配在 中创建帐户，进一步实现安全性。 

HoloLens 2自 Holographic 版本[20H2](hololens-release-notes.md#windows-holographic-version-20h2)起，Windows支持 TenantLockdown CSP。 

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
   > ![通过 OMA-URI 设置租户锁定。](images/hololens-tenant-lockdown.png)

1. 创建组并将设备配置文件分配给该设备组。 

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。  

在 Intune 门户中验证设备配置是否已成功应用。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的影响将处于活动状态。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>如何使用 Intune 在 HoloLens 2 上取消设置 TenantLockdown 的 RequireNetworkInOOBE？ 
1. 将 HoloLens 2 从先前分配了上面创建的设备配置的设备组中删除。 

1. 创建基于 OMA URI 的自定义设备配置文件，并为 RequireNetworkInOOBE 指定 false，如下所示。 OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![在 Intune 中通过 OMA URI 将 RequireNetworkInOOBE 设置为 false 的屏幕截图。](images/hololens-tenant-lockdown-false.png)

1. 创建组并将设备配置文件分配给该设备组。

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。

在 Intune 门户中验证设备配置是否已成功应用。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的影响将处于非活动状态。

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>将 TenantLockdown 设置为 true 后，如果在 HoloLens 上取消分配 Autopilot 配置文件，在 OOBE 期间会发生什么情况？ 
OOBE 将无限期等待 Autopilot 配置文件下载，并将显示以下对话框。 为了删除 TenantLockdown 的影响，必须首先仅使用 Autopilot 将设备注册到其原始租户，并且必须按照上一步中的说明取消设置 RequireNetworkInOOBE，然后才能删除 TenantLockdown 云解决方案提供商引入的限制。

![在设备上实施策略时的设备内视图。](images/hololens-autopilot-lockdown.png)

现在，可以在 [Tenantlockdown CSP 和 Autopilot](hololens2-autopilot.md#tenant-lockdown-csp-and-autopilot)下与 Autopilot 的其余部分一起找到此信息。

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

之前在应用展台模式时遇到HoloLens，用于显示开始菜单中的所有应用程序。 现在，Windows 20H2 版在发生故障时，开始菜单中不会显示任何应用，如下所示：

![当展台模式发生故障时，其外观的图像。](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens政策

- 专用于管理设备HoloLens的设备管理选项。 

在全息版 20H2 上为 HoloLens 2 设备Windows混合现实策略。 新的可控制设置包括：设置亮度、设置音量、禁用混合现实捕获中的音频录制、设置收集诊断的时间和 AAD 组成员身份缓存。  

| 新建HoloLens策略                                | 说明                                                                               | 说明                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 允许禁用亮度按钮，以便按它不会更改亮度。       | 1 是，0 (默认)                                                 |
| MixedReality\VolumeButtonDisabled                  | 允许禁用音量按钮，以便按它不会更改音量。               | 1 是，0 (默认)                                                 |
| MixedReality\MicrophoneDisabled                    | 禁用麦克风，因此无法对麦克风进行音频HoloLens 2。                      | 1 是，0 (默认)                                                 |
| MixedReality\FallbackDiagnostics                   | 控制何时可以收集诊断日志的行为。                               | 0 已禁用，1 为设备所有者启用，2 为默认 (启用)  |
| MixedReality\HeadTrackingMode                      | 保留供将来使用。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 控制将组Azure AD缓存用于展台目标组组Azure AD天数。 | 请参阅下文。                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>缓存Azure AD展台的组成员身份
- 已启用脱机展台，可与 AAD 组一起使用最多 60 天。

此策略控制允许Azure AD组成员身份缓存的天数，用于针对已登录用户Azure AD组分配的访问配置。 一旦此策略值设置为大于 0 的值，则否则使用缓存。  

名称：AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最短 - 0 天  
最大值 - 60 天 

正确使用此策略的步骤： 
1. 为展台组创建设备配置文件Azure AD并将其分配给HoloLens设备 () 。 
1. 创建自定义基于 OMA URI 的设备配置，将此策略值设置为所需的天数 (> 0) 并将其分配给 HoloLens 设备 () 。 
    1. URI 值应在 OMA-URI 文本框中输入为 ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. 该值可以介于允许的最小值/最大值之间。
1. 注册HoloLens并验证这两个配置是否应用到设备。 
1. 在Azure AD Internet 可用时让用户 1 登录，用户登录并成功Azure AD组成员身份后，将创建缓存。 
1. 现在Azure AD用户 1 可以脱机HoloLens，只要策略值允许 X 天，就可以在展台模式下使用它。 
1. 对于任何其他 Azure AD 用户 N，可以重复步骤 4 和 5。此处的要点是，任何 Azure AD 用户都必须使用 Internet 登录到设备，以便我们至少能够确定他们是展台配置所面向的 Azure AD 组的成员。 
 
> [!NOTE]
> 在针对设备执行步骤 4 之前Azure AD用户将遇到"断开连接"环境中提到的故障行为。 

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

### <a name="new-power-policies-for-hololens-2"></a>新电源策略HoloLens 2
- 更多选项，用于HoloLens电源策略进入睡眠或锁定状态。 

这些新添加的策略允许管理员控制电源状态，例如空闲超时。 若要详细了解每个策略，请单击该策略的链接。

|     策略文档链接                |     说明                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     在配置设计器Windows的示例值，即`<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     在配置设计器Windows的示例值，即`<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  配置设计器中Windows的示例值，即 100                                                                             |
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
 
![在“设置”应用中修改活动时段的屏幕截图。](images/hololens-page-visibility-list.jpg)

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

- 修复了在丢失或重新获取跟踪时可能导致全息影像在 Unity 应用程序中消失的问题。
- 修复了在某些设备上使用具有硬件加速HoloLens HoloLens Emulator应用崩溃回 shell 的问题。
- 解决了有关应用程序上 HTTPS 转发Windows 设备门户的问题HoloLens 2。

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows全息版 2004 - 2020 年 6 月更新
- 内部版本 19041.1106

更新中的改进和修复：

- 如果未指定自定义 MRC 记录器，则自定义 MRC 记录器现在具有某些属性的新默认值。
  - 在 *MRC 视频效果上*：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式头戴显示设备) ) 
  - 在 *MRC 音频效果上*：
    - LoopbackGain (应用音频获取"页上的当前混合现实捕获"值Windows 设备门户) 
    - MicrophoneGain (中"麦克风音频增益"页上的当前混合现实捕获"Windows 设备门户) 
- 修复了一个 bug，以提高混合现实捕获方案中的音频质量。 具体而言，此修复应消除在显示"开始"菜单时录制 **的音频** 问题。
- 改进了录制视频中的全息影像稳定性。
- 解决了混合现实捕获在设备处于待机状态多天后无法录制视频的问题。
- 对于 Unity 应用程序，通常禁用 HolographicSpace.UserPresence API。 此行为可避免在视器翻转时导致某些应用暂停的问题，即使启用了"在后台运行"设置。 现已为 Unity 版本 2018.4.18 及更高版本以及 2019.3.4 及更高版本启用 API。
- 通过证书设备门户访问Wi-Fi，Web 浏览器可能会由于证书无效而阻止对 的访问。 浏览器可能会报告错误，例如"ERR_SSL_PROTOCOL_ERROR"，即使设备证书以前受信任。 在这种情况下，无法继续设备门户，因为无法忽略安全警告。 此更新解决了问题。 如果以前在电脑上下载并信任设备证书以删除浏览器安全警告，并且发生 SSL 错误，必须下载并信任新证书，以解决浏览器安全警告。
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
    - LoopbackGain (应用音频获取"页上的当前混合现实捕获"值Windows 设备门户) 
    - MicrophoneGain (中"麦克风音频增益"页上的当前混合现实捕获"Windows 设备门户) 
- 对于 Unity 应用程序，通常禁用 HolographicSpace.UserPresence API。 此行为可避免在视器翻转时导致某些应用暂停的问题，即使启用了在后台运行的设置。 现已为 Unity 版本 2018.4.18 及更高版本以及 2019.3.4 及更高版本启用 API。
- 修复了导致应用HoloLens像素格式以在应用中呈现黑色HoloLens Emulator。
- 修复了从 1903 版本更新后在初始启动中启动照片应用的问题。

## <a name="windows-holographic-version-2004"></a>Windows全息版 2004  
- 内部版本 - 19041.1103

HoloLens 2、Windows Holographic 版本 *2004 的 2020* 年 5 月主要软件更新包含许多令人心动的新功能，例如支持 Windows Autopilot、应用深色模式、USB 以太网支持 5G/LT 热点等。 若要更新到最新版本，请打开 设置应用，转到"更新&    **安全性"，然后选择"检查** **更新"**   按钮。 

|             Feature                              |          说明                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          使用 AutoPilot 预配置和无缝设置用于生产Windows设备                 |
|       FIDO 2 支持                             |          支持 FIDO2 安全密钥，为共享设备启用快速且安全的身份验证            |
|       改进了预配                      |          将预配包从 USB 驱动器无缝应用到HoloLens                              |
|       应用程序安装状态                 |          检查已通过 MDM 设置应用推送到 HoloLens 2应用的安装状态               |
|       配置服务提供商 (使用)    |          添加了新的配置服务提供程序，以增强管理员控制功能                 |
|       USB 5G/USB 支持                       |          扩展的 USB 以太网功能支持 5G/LTS                                    |
|       深色应用模式                              |          深色应用模式适用于支持深色和浅色模式的应用，从而改善观看体验        |
|       语音命令                             |          支持使用其他系统语音命令来控制HoloLens操作                           |
|       手部跟踪改进                 |          手部跟踪改进使按钮和 2D 板交互更准确                        |
|       质量改进和修复                 |          跨平台的各种系统性能和可靠性改进                            |

### <a name="support-for-windows-autopilot"></a>支持 Windows Autopilot

WindowsAutopilot for HoloLens 2允许设备销售渠道预先注册HoloLens Intune 租户。 设备到达时，可以自行部署为租户下的共享设备。 若要利用自我部署，设备必须使用 USB-C 到以太网在安装的第一个屏幕期间连接到网络。

用户启动 Autopilot 自我部署过程后，该过程将完成以下步骤：

1. 将设备加入 Azure Active Directory (Azure AD)。
1. 使用 Azure AD 将设备注册到 Microsoft Intune (或其他 MDM 服务) 。
1. 下载设备目标策略、证书和网络配置文件。
1. 预配设备。
1. 向用户展示登录屏幕。

有关详细信息，请Windows [Autopilot for HoloLens 2指南](hololens2-autopilot.md)。

*立即联系帐户管理员以加入 AutoPilot 预览版。Autopilot 就绪设备即将开始交付。*

### <a name="fido2-security-key-support"></a>FIDO2 安全密钥支持

某些用户与HoloLens或学校环境中的用户共享设备。 因此，用户可以轻松地无需键入长用户名和密码，这一点很重要。 使用 Fast Identity Online (FIDO) ，组织租户 (Azure AD任何人都可以) 无缝登录到 HoloLens 而无需输入用户名或密码。

FIDO2 安全密钥是基于标准的"不可加密"无密码身份验证方法，可以采用任何外形要求。 FIDO 是无密码身份验证的开放标准。 它允许用户和组织在没有用户名或密码的情况下登录到其资源。 而是使用内置于设备的外部安全密钥或平台密钥。

若要开始，请参阅 [启用无密码安全密钥登录](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>通过预配包改进了 MDM 注册

通过预配包，HoloLens配置文件设置配置，而不是通过HoloLens即用体验进行配置。 以前，预配包必须复制到内部HoloLens上。 现在，它们可以位于 USB 驱动器上，因此可以更轻松地在多个设备HoloLens重复使用，并且你可以并行预配设备。 预配包现在还支持用于在设备管理中注册的字段，因此，在预配后无手动设置。

试试看：

1. 从 Windows 商店将最新版本的 Windows 配置设计器下载到你的电脑上。
1. 选择 "**预配 HoloLens 设备**" "  >  **预配 HoloLens 2 设备**"。
2. 生成配置文件。 然后将创建的所有文件复制到 USB-C 存储设备。
3. 将 USB-C 设备插入任何刚闪 HoloLens。 然后按 **下音量**  +  **键**，以应用预配包。

### <a name="line-of-business-application-install-status"></a>业务线应用程序安装状态

适用于业务线应用的 MDM 应用部署和管理对于 HoloLens 至关重要。 管理员和用户需要查看应用安装状态以进行审核和诊断。 在此版本中，我们在 **设置** 帐户中添加了更多详细信息  >    >  。**访问工作或学校**  >  **单击你的帐户**  >  **信息**。

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
- 文件资源管理器 
- 反馈中心 
- OneDrive 
- 照片 
- 3D 查看器 
- 电影和电视 

![平铺窗口。](images/DarkMode.jpg)

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
- 文件资源管理器
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

- 改进了使用专用仿真器时独占应用HoloLens 2的稳定性。

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

- 修复了在 en-CA **和** en-AU 的初始设置过程中选择语音命令的功能。
- 改进了放置在最新 Unity 和混合现实中的对象的视觉质量Toolkit (MRTK) 版本。
- 修复了全息应用程序在启动时停滞在暂停状态的问题，"开始"菜单打开然后关闭。
- OpenXR 运行时的一致性修复和改进HoloLens 2和模拟器。
