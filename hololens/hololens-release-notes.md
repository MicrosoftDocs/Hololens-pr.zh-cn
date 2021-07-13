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
ms.openlocfilehash: 73d89619498c61f2809702d788ffafc532afa67e
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640026"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2 发行说明

为了确保你拥有高效体验，HoloLens设备，我们将继续发布功能、bug 和安全更新。 在此页上，可以看到每月HoloLens新增功能。 若要获取最新的 HoloLens 2更新，可以检查更新并手动更新[](hololens-update-hololens.md#check-for-updates-and-manually-update)，或获取完整闪存更新 (FFU) 通过高级恢复助手 来刷用[设备。](hololens-recovery.md#clean-reflash-the-device) [下载](https://aka.ms/hololens2download)会保持最新，并提供最新的已发布版本。

> [!NOTE]
> 最近的 Windows 11 公告侧重于 PC 版本的 Windows。 我们[最近于](https://techcommunity.microsoft.com/t5/mixed-reality-blog/what-s-new-in-windows-holographic-version-21h1/ba-p/2337067)2021 年 5 月推出了HoloLens 2 OS 更新，我们正在努力根据客户对本年五月的反馈推出即将发布的版本。

> [!IMPORTANT]
> 由于[21H1](hololens-troubleshooting.md#remote-assist-video-freezes-after-20-minutes)版本中现在解决了影响 Remote Assist 用户的已知问题，我们暂时暂停了 Windows Holographic 版本 21H1 更新的提供。 我们还将默认的 Advanced Recovery Companion (ARC) 内部版本更改为[Windows Holographic 版本 20H2 – 2021](hololens-release-notes.md#windows-holographic-version-20h2--june-2021-update)年 6 月更新。 ARC 生成现在将恢复面向 21H1 生成。

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
[WebXR 和 360 查看器](#webxr-and-360-viewer) | 尝试沉浸式 Web 体验和 360 视频播放。 | 最终用户 | 
[新建设置应用](#new-settings-app) | 旧版设置应用将被更新版本替换为新功能和设置。 | 最终用户 |
[显示颜色校准](#display-color-calibration) | 为屏幕显示选择HoloLens 2配置文件。 | 最终用户 |
[默认应用选取器](#default-app-picker) | 选择应针对每个文件或链接类型启动的应用。 | 最终用户 |
[每个应用音量控制](#per-app-volume-control) | 独立于系统卷控制应用级别卷。 | 最终用户 |
[安装 Web 应用](#install-web-apps) | 用新的 Microsoft Edge 浏览器在 HoloLens 2 上安装 web 应用，如 Microsoft Office。 | 最终用户 |
[刷到类型](#swipe-to-type) | 使用手指的笔尖在全息键盘上 "轻扫" 单词。 | 最终用户 |
[入门的 Power menu](#power-menu-from-start) | 在 "开始" 菜单上，重新启动并关闭 HoloLens 设备 "。 | 最终用户 |
[登录屏幕上列出了多个用户](#multiple-users-listed-on-sign-in-screen) | 在登录屏幕上显示多个用户帐户。 | 最终用户 |
[USB-C 外部麦克风支持](#usb-c-external-microphone-support) | 为应用和/或远程协助使用 USB-C 麦克风。 | 最终用户 |
[网亭的访问者自动登录](#visitor-auto-logon-for-kiosks) | 启用对访问者帐户的自动登录以用于展台模式。 | IT 管理员 |
[展台模式下新应用的新 AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | 用于新设置和边缘应用的 AUMIDs。 | IT 管理员 |
[改善了展台模式故障处理](#kiosk-mode-behavior-changes-for-handling-of-failures) | 展台模式在空 "开始" 菜单之前查找全局分配的访问权限。 | IT 管理员 |
[新的 SettingsURIs for Page 设置 Visibility](#new-settings-uris-for-page-settings-visibility) | 20多个新的 SettingsURIs 设置/PageVisibilityList 策略。 | IT 管理员 |
[配置回退诊断](#configuring-fallback-diagnostics-via-settings-app) | 在设置应用程序中设置回退诊断行为。 | IT 管理员 |
[与附近设备共享东西](#share-things-with-nearby-devices) | 将 HoloLens 中的文件或 url 共享到 PC。 | 全部 |
[新操作系统诊断跟踪](#new-os-diagnostic-traces) | 针对 OS 更新设置的新疑难解答。 | IT 管理员 |
[传递优化预览](#delivery-optimization-preview) | 减少从多个 HoloLens 设备下载的带宽消耗。 | IT 管理员 |

查看相关发行说明：

- [访问 HoloLens Emulator 存档](/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>新 Microsoft Edge 简介

![旧 Microsoft Edge 徽标到新 Microsoft Edge 徽标的动画](images/new-edge.gif)

新的 Microsoft Edge[采用 Chromium 开源项目](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/)，为客户提供更好的兼容性，并为 web 开发人员提供更少的 web 碎片。

> [!IMPORTANT]
> 这一新 Microsoft Edge 会自动替换旧 Microsoft Edge，这在新版本中[不再受支持](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/)。

![新 Microsoft Edge 屏幕快照](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>启动新 Microsoft Edge

新的 Microsoft Edge ![新 Microsoft Edge 图标](images/new_edge_logo.png) 用蓝色和绿色漩涡图标表示的 () 固定到 "开始"菜单，并将在你激活 web 链接时自动启动。

> [!NOTE]
> 首次启动 HoloLens 2 上的新 Microsoft Edge 时，将从旧 Microsoft Edge 导入设置和数据。 如果在启动新 Microsoft Edge 后继续使用旧的 Microsoft Edge，则不会将新数据从旧 Microsoft Edge 同步到新的 Microsoft Edge。

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>为新的 Microsoft Edge 配置策略设置

新的 Microsoft Edge 为 IT 管理员提供了在 HoloLens 2 上提供的更广泛的浏览器策略，超过了旧 Microsoft Edge 之前的版本。

下面是一些有用的资源，用于了解有关管理新 Microsoft Edge 的策略设置的详细信息：

- [Microsoft Intune 配置 Microsoft Edge 策略设置](/deployedge/configure-edge-with-intune)
- [Microsoft Edge 旧版 Microsoft Edge 策略映射](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Microsoft Edge 策略映射的 Google Chrome](/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 完整[Microsoft Edge Enterprise 文档](/deployedge/)

> [!IMPORTANT]
> 由于新 Microsoft Edge 支持的浏览器策略的数量，我们的团队无法保证每个新策略都适用于 HoloLens 2。 但是，我们已测试并确认了以前在 HoloLens 2 按预期方式支持的每个旧 Microsoft Edge 策略的新 Microsoft Edge。 请参阅[Microsoft Edge 旧版 Microsoft Edge 策略映射](/deployedge/microsoft-edge-policy-map-legacy-to-newedge)，查找与用于 HoloLens 2 的每个旧 Microsoft Edge 浏览器策略等效的新 Microsoft Edge。
>
> 至少有两个新的 Microsoft Edge 策略，我们知道这些策略 *将无法* 用于 HoloLens 2：
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>新 Microsoft Edge 对 HoloLens 2 的预期情况

由于新 Microsoft Edge 是具有新 uwp 适配器层的本机 Win32 应用程序，允许它在 HoloLens 2 的仅 UWP 设备上运行，因此某些功能可能不会立即可用。 我们将在未来几个月内支持新方案和功能，因此请查看此空间以获取最新信息。

**预期工作情况和功能：**
- 首次运行体验，登录到配置文件，同步
- 网站应呈现并按预期方式工作
- 大多数浏览器功能 ("收藏夹"、"历史记录" 等 ) 应按预期方式工作
- 深色模式
- 将 web 应用安装到设备
- 安装扩展 (如果你使用的扩展不能在 HoloLens 2 上正常工作，请告知我们) 
- 查看并标记 PDF
- 单个浏览器窗口中的空间音效
- 自动和手动更新浏览器
- 使用 "保存到 PDF" 选项从 "打印" 菜单保存 PDF () 
- WebXR 和360查看器扩展
- 当跨环境中的多个窗口进行浏览时，内容还原到正确的窗口

**不应工作的方案和功能：**
- 带有同时音频流的多个窗口的空间音效
- "看，说它"
- 打印

**最常见的浏览器已知问题：**

- 为新的 Microsoft Edge 禁用了全息键盘中的放大镜预览。 我们希望在未来的更新中重新启用此功能，一旦放大倍数工作正常。
- 如果有另一个浏览器窗口处于打开和活动状态，则可以从错误的浏览器窗口播放音频。 通过关闭不应播放音频的其他活动窗口，可以解决此问题。
- 在 ["关注我" 模式下](hololens2-basic-usage.md#follow-me-stop-following)从浏览器窗口播放音频时，如果禁用 "关注我" 模式，则音频将继续播放。 可以通过在禁用 "关注我" 模式之前停止音频播放，或通过使用 **X** 按钮关闭窗口，来解决此问题。
- 与 active Microsoft Edge windows 交互可能会导致其他2d 应用程序窗口意外停用。 您可以重新激活这些窗口，方法是再次与它们进行交互。

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge内部渠道

Microsoft Edge 团队使三个预览频道可供边缘有问必答社区使用： Beta 版、开发人员和未之用。 安装预览频道不会卸载 HoloLens 2 上的 Microsoft Edge 的发行版，并且可以同时安装多个版本。 

请访问[Microsoft Edge 有问必答主页](https://www.microsoftedgeinsider.com)以了解有关边缘有问必答社区的详细信息。 若要详细了解不同的边缘有问必答通道并开始，请访问 [边缘有问必答下载页面](https://www.microsoftedgeinsider.com/download)。

有几种方法可用于安装 Microsoft Edge 有问必答通道 HoloLens 2：

**直接安装在设备上 (当前仅适用于非托管设备)**
  1. 在 HoloLens 2 上，请访问[边缘有问必答下载页面](https://www.microsoftedgeinsider.com/download)。
  1. 选择要安装的边缘有问必答频道的 "**下载 HoloLens 2** " 按钮。
  1. 使用文件资源管理器) ，从边缘下载队列或设备的 "下载" 文件夹启动下载的 .msix 文件 (。
  1. 将启动[应用安装程序](app-deploy-app-installer.md)。
  1. 选择“安装”按钮。
  1. 安装成功后，会在 "开始"菜单的 "**所有应用**" 列表中找到 Microsoft Edge Beta、开发或工作方式为单独的条目。

**通过电脑安装 Windows 设备门户 (需要在 HoloLens 2 启用 [开发人员模式](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal))**
  1. 在你的电脑上，访问 [边缘有问必答下载页面](https://www.microsoftedgeinsider.com/download)。
  1. 选择要安装的边缘有问必答频道的 "下载 Windows 10" 按钮旁的 **下拉箭头按钮**。
  1. 在下拉菜单中选择 " **HoloLens 2** "。
  1. 将 .msix 文件保存到你的电脑的 "下载" 文件夹中 (或可轻松找到) 的其他文件夹。
  1. 使用电脑上[Windows 设备门户](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)在 HoloLens 2 上安装下载的 .msix 文件。
  1. 安装成功后，会在 "开始"菜单的 "**所有应用**" 列表中找到 Microsoft Edge Beta、开发或工作方式为单独的条目。

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>使用 WDAC 阻止新 Microsoft Edge

对于希望更新其[WDAC 策略](windows-defender-application-control-wdac.md)以阻止新的 Microsoft Edge 应用的 IT 管理员，需要将以下项添加到策略中。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>管理新 Microsoft Edge 的终结点

出于考虑，某些环境可能具有网络限制。 若要确保具有新边缘的流畅体验，请 [启用这些 Microsoft 终结点。](/deployedge/microsoft-edge-security-endpoints)

阅读有关 HoloLens 当前可用[终结点](hololens-offline.md)的详细信息。

### <a name="install-web-apps"></a>安装 web 应用
 > [!Note]
>从[Windows 全息版本 21H1](hololens-release-notes.md#windows-holographic-version-21h1)，Office web 应用将不再预装。

你可以使用新边缘来安装 web 应用和 Microsoft Store 应用。 例如，可以安装 Microsoft Office web 应用来查看和编辑托管在 SharePoint 或 OneDrive 上的文件。 若要安装 Office web 应用，请访问， https://www.office.com 并在地址栏中选择 "**可用应用**" 或 "**安装 Office** " 按钮。 选择 " **安装** " 进行确认。

> [!IMPORTANT]
> 仅当 HoloLens 2 具有活动的 internet 连接时，Office web 应用功能才可用。

### <a name="webxr-and-360-viewer"></a>WebXR 和360查看器

新 Microsoft Edge 包括对 WebXR 的支持，这是用于创建沉浸式 web 体验 (替换 WebVR) 的新标准。 许多沉浸式 web 体验在设计上都是使用 VR (它们将视图的字段替换为虚拟环境) ，但 HoloLens 2 也支持这些体验。 WebXR 标准还启用了使用物理环境的扩充和混合现实沉浸式 web 体验。 随着开发人员花更多时间来 WebXR，我们预计新增加和混合现实沉浸式体验将会让 HoloLens 2 客户尝试！

360查看器扩展是在 WebXR 上构建的，并随新 Microsoft Edge 在 HoloLens 2 上自动安装。 此 web 扩展使你能够在360度视频中从而深入了解。 YouTube 提供最大程度的360视频，因此我们鼓励你从这里开始。

#### <a name="how-to-use-webxr"></a>如何使用 WebXR

1. 导航到支持 WebXR 的网站。
1. 选择网站上的 " **输入** "。 此按钮的位置和视觉表示形式可能因网站而异，但它看起来可能类似于：

    ![输入 VR 按钮示例](images/75px-enter-vr.png)

1. 首次尝试在特定域上启动 WebXR 体验时，浏览器将要求同意输入沉浸式视图，并选择 " **允许**"。
1. 使用[HoloLens 2 手势](hololens2-basic-usage.md#the-hand-tracking-frame)来处理体验。
1. 如果体验没有 **退出** 按钮，请使用 [开始手势](hololens2-basic-usage.md#start-gesture) 返回 home。

**建议的 WebXR 示例**
- 360查看器 (参阅下一节) 
- [XR 恐龙](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR 画图](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>如何使用360查看器

1. 在 YouTube 上导航到360度视频。
1. 在视频帧中，选择混合现实耳机按钮：

    ![用于激活360查看器的按钮](images/enter-360-viewer.jpg)

1. 首次尝试在特定域上启动360查看器时，浏览器将要求同意输入沉浸式视图。 选择“允许”。
1. [点击](hololens2-basic-usage.md#select-using-air-tap) 以打开播放控件。 使用 " [手" 光线和 "空中点击](hololens2-basic-usage.md#select-using-air-tap) " 播放/暂停、向前/向后、打开/关闭字幕或停止体验 (会退出沉浸式视图) 。 播放控件将在几秒钟处于非活动状态后消失。

#### <a name="top-webxr-and-360-viewer-known-issues"></a>最 WebXR 和360查看器已知问题
- 根据 WebXR 体验的复杂性，帧速率可能下降或断断续续。
- 默认情况下，不支持 WebXR 中的已表述的手接。 开发人员可以 `edge://flags` 通过打开 "WebXR 手型输入" 启用支持。
- 360之外的网站中的视频不会按预期方式工作。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>在 WebXR 和360查看器中提供反馈

请通过新 Microsoft Edge 中的 "**发送反馈**" 功能与我们的团队共享反馈和 bug。

### <a name="new-settings-app"></a>新建设置应用

在此版本中，我们引入了新版本的设置应用。 新的设置应用程序包括以下方面 HoloLens 2 的新功能和扩展的设置：声音、电源 & 睡眠、网络 & Internet、应用、帐户、轻松访问等。

> [!NOTE]
> 由于新的设置应用与旧设置应用不同，因此在更新时将删除以前在环境中放置的任何设置窗口。

![新设置应用主页](images/new-settings-app.png)

**新功能和设置**
- 设置搜索：使用关键字或设置的名称从设置主页搜索设置。
- 系统 > 声音：
  - 输入和输出音频设备：例如，单独选择输入和输出音频设备 (例如，通过蓝牙耳机收听音频，或使用 USB C 麦克风进行音频输入) 。
    > [!NOTE]
    > HoloLens 2 不支持蓝牙麦克风。
  - 应用卷：独立调整每个应用的音量。 请参阅 [每个应用音量控制](#per-app-volume-control)。
- 系统 > Power & 睡眠：在设备处于非活动状态一段时间后，选择设备应进入睡眠状态。
- 系统 > 电池：手动启用节电模式，或设置节电模式自动开启的电池阈值。
- 设备 > USB：默认情况下，可以禁用 USB 连接。
- 网络 & Internet：
  - USB 以太网适配器现在会显示在网络 & Internet 中。
  - 现在可以使用 USB-C 以太网适配器设置，包括其 IP 地址。
  - 你现在可以在 HoloLens 2 上启用飞行模式。
- 应用：可以重置用于文件和链接类型的默认应用。 有关详细信息，请参阅 [默认应用选取器](#default-app-picker)。
- 帐户 > 其他用户：设备所有者可以添加用户、将标准用户升级到设备所有者、将设备所有者降级为标准用户以及删除用户。
- 易于访问：更改文本大小和一些视觉效果。

**已知问题**
- 将删除以前放置设置窗口 (请参阅上面) 的说明。
- 你不能再用设置应用重命名你的设备。 IT 管理员可以通过使用 HoloLens 2 设备名称模板或 MDM [DevDetail CSP](/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 节点的[Windows Autopilot](hololens2-autopilot.md)重命名设备。
- "以太网&quot; 页将始终显示虚拟以太网设备 ( &quot;UsbNcm" ) 。
- 新 Microsoft Edge 的电池使用情况可能不准确，因为它的性质是 UWP 适配器层所支持的 Win32 桌面应用程序 (不会立即) 任何修补程序。

#### <a name="display-color-calibration"></a>显示颜色校准



使用此新设置，可以为 HoloLens 2 显示选择备用颜色配置文件。 这可以帮助显示更准确的颜色，尤其是在较低的显示亮度级别。 可以在 "系统 > 校准" 页上的 "设置应用" 中找到显示颜色校准。

> [!NOTE]
> 由于此设置将新的颜色配置文件保存到显示器固件，因此它是每个设备的设置， (并且每个用户帐户) 不唯一。

##### <a name="how-to-use-display-color-calibration"></a>如何使用显示颜色校准

1. 启动 **设置** 应用并导航到 "**系统 > 校准**"。
1. 在 " **显示颜色校准**" 下，选择 " **运行显示颜色校准** " 按钮。
1. 将启动显示颜色校准体验，并鼓励您确保面板的位置正确。
1. 在您继续执行 "指令" 对话框后，您的显示器将自动变为浅亮度为30%。
    > [!TIP]
    > 如果在你的环境中查看灰显的场景时遇到问题，可以使用设备左侧的亮度按钮手动调整 HoloLens 2 的亮度级别。
1. 选择按钮1-6 可立即尝试每个颜色配置文件，并找到最适合您的眼睛的颜色配置文件 (这通常意味着可帮助场景最中性地显示的配置文件，并以灰度模式和肤色查看预期。 ) 

    ![显示颜色校准场景](images/color-cal-ui.png)
    
1. 当你对所选配置文件满意时，选择 " **保存 & 退出** " 按钮
1. 如果你不想进行更改，请选择 " **取消 & 退出** " 按钮，你的更改将恢复

> [!TIP]
> 下面是使用显示颜色校准设置时需要注意的一些有用提示：
> - 你可以根据需要重新运行显示颜色校准设置
> - 如果设备上的任何人以前使用了更改颜色配置文件的设置，则最近更改的日期/时间将反映在设置页面上
> - 重新运行 "显示颜色校准" 时，将突出显示以前保存的颜色配置文件，并且不会显示配置文件 0 (因为配置文件0表示显示的原始颜色配置文件) 
> - 如果要恢复到显示的原始颜色配置文件，可从 "设置" 页面 (参阅[如何重置颜色配置文件](#how-to-reset-color-profile)) 

##### <a name="how-to-reset-color-profile"></a>如何重置颜色配置文件 

如果你对保存到 HoloLens 2 中的自定义颜色配置文件不满意，则可以还原设备的原始颜色配置文件：
1. 启动 **设置** 应用并导航到 "**系统 > 校准**"。
1. 在 " **显示颜色校准**" 下，选择 " **重置为默认颜色配置文件** " 按钮。
1. 当对话框打开时，如果已准备好重新启动 HoloLens 2 并应用所做的更改，请选择 "**重新启动**"。

#### <a name="top-display-color-calibration-known-issues"></a>顶部显示颜色校准已知问题

- 在 "设置" 页上，通知您上次更改颜色配置文件的状态字符串将过期，直到您重新加载设置的该页面为止。
    - 解决方法：选择另一个设置页面，然后重新选择校准页面。

#### <a name="default-app-picker"></a>默认应用选取器

当你激活超链接或打开具有多个已安装的应用程序的文件类型（该应用程序支持该类型）时，你将看到一个新窗口打开，提示你选择哪个已安装的应用程序应处理文件或链接类型。 在此窗口中，你还可以选择让选定的应用处理文件或链接类型 "一次" 或 "始终"。

如果选择 "始终"，但稍后要更改哪个应用处理特定文件或链接类型，则可以在 **设置 > 应用** 中重置保存的默认值。 滚动到页面底部，在 "文件类型的默认应用" 和/或 "链接类型的默认应用" 下选择 " **清除** " 按钮。 与台式计算机上类似的设置不同，不能重置单独的文件类型默认值。

#### <a name="per-app-volume-control"></a>按应用音量控制

现在，在此 Windows 生成中，用户可以手动调整每个应用的音量级别。 这样，用户便可以更好地专注于所需的应用，也可以更好地使用多个应用。 例如，需要在为另一个应用程序调用另一个用户时关闭一个应用程序的卷。

若要设置单个应用的音量，请导航到 **设置**  ->  **系统**  ->  **声音**"，然后在" 高级声音选项 "下选择"**应用卷和设备首选项**"。<br/><br/>

<img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>刷到类型

有些客户通过轻扫要键入的单词的形状，来更快地在虚拟键盘上 "键入"，并且我们正在为全息键盘预览此功能。 您可以通过在全息键盘的平面上传递手指的笔尖，刷一字的形状，然后从键盘飞机取出手指的笔尖，一次轻扫一个词。 您可以通过从键盘上的键盘删除手指，无需按下空格键，就可以扫开单词。 如果你在键盘上的手指移动后看到一张滑动轨迹，你会知道该功能正在运行。

请注意，此功能可能会比较棘手，因为全息键盘的性质与移动电话) 不同，你不会对手指 (。 

### <a name="power-menu-from-start"></a>入门的 Power menu

允许用户注销、关闭和重新启动设备的新菜单。 HoloLens "开始" 屏幕中显示系统更新何时可用的指示器。

#### <a name="how-to-use"></a>如何使用

1. 使用[开始手势](hololens2-basic-usage.md#start-gesture)打开 HoloLens 开始屏幕，或说 "前往开始"。

2. 请注意，用户配置文件图片旁边的省略号图标 ( ) ：<br/><br/>

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 使用手或语音命令 "电源" 选择用户配置文件图片。

4. 此时将显示一个菜单，其中包含用于注销、重新启动或关闭设备的选项：<br/><br/>

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. 选择要注销、重启或关闭 HoloLens 的菜单选项。 "注销" 选项可能不可用，如果设备设置为 [单一 Microsoft 帐户 (MSA) 或本地帐户](hololens-identity.md)。

6. 通过触摸任何其他位置或使用开始手势关闭 "开始"菜单来关闭菜单。

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

### <a name="usb-c-external-microphone-support"></a>USB-C 外部麦克风支持

> [!IMPORTANT]
> 插入 **USB 麦克风不会自动将其设置为输入设备**。 当插入一组 USB-C 耳机时，用户将看到耳机音频将自动重定向到耳机，但 HoloLens OS 会将内部麦克风阵列的优先级设置为任何其他输入设备的优先级。 **若要使用 USB-C 麦克风，请遵循以下步骤。**

用户可以使用 " **声音** 设置" 面板选择 "USB 连接的外部麦克风"。 USB-C 麦克风可用于呼叫、录制等。

打开 **设置** 应用并选择 "**系统**  >  **声音**"。

![声音设置](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 若要将外部麦克风用于 **远程协助**，用户需要单击 "管理声音设备" 超链接。
>
> 然后，使用下拉设置将外部麦克风设置为 **默认** 值或 **通信默认值。** 选择 " **默认值** " 表示将在任何位置使用外部麦克风。
>
> 选择 "**通信默认值**" 表示将在远程协助和其他通信应用中使用外部麦克风，但 HoloLens mic 数组仍可用于其他任务。

![管理声音设备](images/usbc-mic-2.png)

<br>

![设置麦克风默认值](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support&quot;></a>蓝牙麦克风支持怎么办？

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

在[Windows 全息版20H2 中，](hololens-release-notes.md#windows-holographic-version-20h2)我们添加了[设置/PageVisibilityList 策略](/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)，以限制在设置应用程序中显示的页面。 PageVisibilityList 是一种策略，它允许 IT 管理员阻止系统设置应用中的特定页面可见或可访问，或为除指定的页面之外的所有页面执行此操作。

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

### <a name="delivery-optimization-preview"></a>传递优化预览

使用此 HoloLens 更新时，Windows Holographic for Business 启用 "传递优化" 设置，以减少从多个 HoloLens 设备下载的带宽消耗。 此处提供了此功能以及推荐的网络配置的完整描述： [Windows 10 更新的传递优化](/windows/deployment/update/waas-delivery-optimization)。

以下设置作为管理界面的一部分启用， [可以从 Intune 进行配置](/mem/intune/configuration/delivery-optimization-settings)：

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

有关此预览版的一些注意事项：

- 仅限此预览版中的 HoloLens 支持。
- Windows Holographic for Business 仅支持来自[Microsoft 连接缓存端点](/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)的 HTTP 下载模式和下载;HoloLens 设备目前不支持对等下载模式和组分配。
- HoloLens 不支持 Windows Server Update Services 终结点的部署或传递优化。
- 故障排除将需要在连接的缓存服务器上进行诊断，或通过 **设置**  >  **更新 & 安全**  >   **故障排除**  >   **Windows 更新** 收集对 HoloLens 上 HoloLens 的跟踪。

### <a name="it-admin---update-checklist"></a>IT 管理员-更新清单

此清单可帮助你了解在此功能更新中添加的功能可能会影响当前设备管理配置的新项目，或者你可能希望开始使用的新功能。

#### <a name="updates-to-kiosk-mode"></a>展台模式更新

[**为展台模式下的新应用✔️新 AUMIDs**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)：

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
1.  选择 yourapp 文件。
1.  应用程序安装程序将启动。 选择 "安装" 按钮以安装您的应用程序。
安装完成后，安装的应用将自动启动。

若要测试此流，可以在[Windows 通用示例 GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)上找到示例应用。

阅读有关[在 HoloLens 2 上安装](app-deploy-app-installer.md)应用程序的完整过程。  

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

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

| 功能                                              | 说明                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [自动目视定位支持](hololens-release-notes.md#auto-eye-position-support) | 主动计算眼睛位置，无需用户通过目视跟踪校准。   |
| [证书管理器](hololens-release-notes.md#certificate-manager)   | 允许新的更简单方法从设置应用安装和删除证书。     |
| [从 USB 自动启动设置](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | 在 USB 驱动器上预配包会自动提示 OOBE 中的设置页面。                                                         |
| [自动确认在 OOBE 中预配包](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 预配页面会在 OOBE 期间自动应用预配包。                                                         |
| [无需使用 UI 即可自动预配](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 如何将设置自动启动和自动确认组合在一起。 |
| [将 Autopilot 与 Wi-Fi 连接结合使用](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | 从设备 Wi-Fi 使用 autopilot，无需使用以太网适配器。 |
| [Tenantlockdown CSP 和 Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | 应用租户注册并应用策略后，在设备重置或重新刷新时，设备只能在该租户中注册。 |
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

### <a name="auto-eye-position-support"></a>自动目视定位支持

在 HoloLens 2 中，目视定位可实现准确的全息影像定位、舒适的观看体验，并改善了显示质量。 目视位置作为眼睛跟踪计算的一部分在内部进行计算。 但是，这要求每个用户都要经历眼睛跟踪校准，即使在体验可能不需要目视输入时也是如此。

**自动排列位置 (AEP)** 通过无交互的方式来计算用户的眼睛位置。 自动目视位置在用户将设备置于设备上的时刻自动开始运行。 如果用户没有先前的目视跟踪校准，则在处理时间为 20-30 秒后，自动目视定位将开始向显示系统提供用户的眼睛位置。 用户数据不会保留在设备上，因此如果用户关闭并重新打开设备，或者设备重新启动或从睡眠状态唤醒，则此过程将重复。

当 uncalibrated 用户进入设备时，会有一些系统行为随 "自动目视定位" 功能发生变化。 在这种情况下，uncalibrated 用户指的是先前尚未经历设备上的目视跟踪校准过程的人。

| 活动应用程序 | 之前的行为 | 来自 Windows 全息版 20H2 Update 的行为 |
|:-------------------|:-----------------|:-----------------------------------|
| 未启用注视的应用或全息 Shell |显示 "目视跟踪校准提示" 对话框。 | 不显示提示。 |
| 已启用注视的应用 | 显示 "目视跟踪校准提示" 对话框。 | 仅当应用程序访问眼睛注视流时才显示眼睛跟踪校准提示。 |

如果用户从未启动的已启用的应用程序转换到访问看不到的数据的应用程序，则将显示校准提示。 

当当前用户没有活动的目视跟踪校准时，所有其他系统行为将类似于。 例如，将不会启用一次传递的开始手势。 初始设置的全新体验将不会更改。

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

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP 和 Autopilot
- 通过设备重置或刷新将设备锁定到租户，从而使其在组织的租户上保持不变。 通过设置，禁止在中创建帐户，从而增强安全性。 

HoloLens 2 设备现在支持[Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2)中的 TenantLockdown CSP。 

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp)CSP 只允许使用 Autopilot 将 HoloLens 2 绑定到 MDM 注册。 将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 或 false 后 (初始设置 HoloLens 2 上的) 值，该值将保留在设备上，尽管重新闪烁、OS 更新等。 

HoloLens 2 上的 "TenantLockdown csp" RequireNetworkInOOBE 节点设置为 true 后，OOBE 会无限期等待 Autopilot 配置文件在网络连接后成功下载和应用。 

HoloLens 2 上的 "TenantLockdown csp" RequireNetworkInOOBE 节点设置为 true 后，OOBE 中不允许以下操作： 
- 使用运行时预配创建本地用户 
- 通过运行时设置执行 Azure AD 联接操作 
- 在 OOBE 体验中选择设备的所有者 

#### <a name="how-to-set-this-using-intune"></a>如何使用 Intune 进行设置？ 
1. 创建自定义 OMA URI 设备配置配置文件，并为 RequireNetworkInOOBE 节点指定 true，如下所示。
OMA-URI 值应为./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 OMA URI 设置租户锁定](images/hololens-tenant-lockdown.png)

1. 创建一个组，并将设备配置文件分配给该设备组。 

1. 创建在上一步中创建的组的 HoloLens 2 设备成员，并触发同步。  

在 Intune 门户中验证是否已成功应用设备配置。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的效果将处于活动状态。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>如何使用 Intune 在 HoloLens 2 上取消设置 TenantLockdown RequireNetworkInOOBE？ 
1. 从设备组中删除之前为其创建的设备配置以前分配的 HoloLens 2。 

1. 创建基于自定义 OMA URI 的设备配置文件，并为 RequireNetworkInOOBE 指定 false，如下所示。 OMA-URI 值应为./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 Intune 中的 OMA URI 将 RequireNetworkInOOBE 设置为 false 的屏幕截图](images/hololens-tenant-lockdown-false.png)

1. 创建一个组，并将设备配置文件分配给该设备组。 

1. 创建在上一步中创建的组的 HoloLens 2 设备成员，并触发同步。

在 Intune 门户中验证是否已成功应用设备配置。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的效果将处于非活动状态。 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>如果在将 TenantLockdown 设置为 true 后 HoloLens 未分配 Autopilot 配置文件，则在 OOBE 期间将发生什么情况？ 
OOBE 会无限期等待 Autopilot 配置文件下载并显示以下对话框。 若要删除 TenantLockdown 的效果，必须首先使用 Autopilot 向设备注册其原始租户，并且必须按照上一步骤中所述取消设置 TenantLockdown CSP 引入的限制。 

![设备上强制实施策略的设备内视图。](images/hololens-autopilot-lockdown.png)

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

| 新建 HoloLens 策略                                | 说明                                                                               | 注释                                                                |
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

|     策略文档链接                |     注释                                                                                                                                       |
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
 
![设置应用中正在修改的活动小时的屏幕截图](images/hololens-page-visibility-list.jpg)

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
    - LoopbackGain (Windows 设备门户中混合现实捕获页面上的当前 "应用音频增益" 值) 
    - MicrophoneGain (Windows 设备门户中混合现实捕获页面上的当前 "Mic 音频增益" 值) 
- 修复了一个 bug，以便在混合现实捕获方案中提高音频质量。 具体而言，当显示 " **开始** " 菜单时，此修复程序应消除录音 glitching。
- 改善了录制视频中的全息影像稳定性。
- 解决了在设备处于待机状态一段时间后混合现实捕获无法录制视频的问题。
- 对于 Unity 应用程序，通常禁用 HolographicSpace UserPresence API。 此行为可避免在向上翻转面板时导致某些应用暂停的问题，即使启用了 "在后台运行" 设置也是如此。 现在为 Unity 版本2018.4.18 和更高版本以及2019.3.4 和更高版本启用了 API。
- 通过 Wi-Fi 连接访问设备门户时，由于证书无效，web 浏览器可能会阻止访问。 即使之前信任设备证书，浏览器也可能会报告 "ERR_SSL_PROTOCOL_ERROR" 之类的错误。 在这种情况下，无法对设备门户进行进度，因为没有忽略安全警告的选项。 此更新解决了问题。 如果先前已在电脑上下载并信任设备证书以删除浏览器安全警告，并且发生 SSL 错误，则必须下载新证书并将其信任，以解决浏览器安全警告。
- 支持创建可通过使用 .MSIX 包安装应用的运行时预配包。
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

1. 将设备加入Azure Active Directory (Azure AD) 。
1. 使用 Azure AD 将设备注册到 Microsoft Intune (或其他 MDM 服务) 。
1. 下载设备目标策略、证书和网络配置文件。
1. 预配设备。
1. 向用户显示登录屏幕。

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

### <a name="additional-csps-and-policies"></a>其他 CSP 和策略

CSP [ (配置) ](/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN) 是一个接口，用于读取、设置、修改或删除设备的配置设置。 在此版本中，我们添加了对更多策略的支持，以提高管理员对已部署设备HoloLens控制。 有关云解决方案提供商支持的 CSP HoloLens，请参阅[NetworkQoSPolicy CSP](/windows/client-management/mdm/networkqospolicy-csp)。

本版本中的新主题：

**策略云解决方案提供商** 

策略配置服务提供程序使企业能够在设备Windows策略。 在此版本中，我们为 HoloLens添加了新策略，此处列出了这些策略。 若要了解有关详细信息，请参阅[由 HoloLens 2 支持的策略HOLOLENS 2。](/windows/client-management/mdm/policies-supported-by-hololens2)  

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

添加了支持，允许某些移动宽带设备（例如 5G/Wi-Fi和 Wi-Fi 热点）通过 USB 连接到 HoloLens 2设备。 这些设备现在在网络设置 **中显示为** 另一个以太网连接。  (不支持需要外部驱动程序的移动宽带设备。) 此功能在 Wi-Fi 不可用且 Wi-Fi Tethering 性能不足时启用高带宽连接。 若要详细了解支持的 USB 设备，请参阅 连接[蓝牙 和 USB-C 设备](hololens-connect-devices.md)。  

### <a name="hand-tracking-improvements"></a>手部跟踪改进

此版本包括多项手动跟踪改进：

- **指向姿势稳定性：** 现在，当手指被手指遮挡时，系统可以抵御手指的滑动。 此更改提高了按下按钮、键入、滚动内容等时的准确性！ 
- **减少了意外的敲击：** 改进了对敲击手势的检测。 现在，在多种常见情况下（例如，将手放在一边时）中的意外激活更少。
- **用户交换机可靠性：** 现在，共享设备时，系统在更新手部大小时速度更快且更可靠。
- **减少手部窃取：** 改进了传感器视图超过两手的情况的处理。 如果多人在一起工作，现在跟踪手从用户"跳转"到场景中其他人手的可能性要低得多。
- **系统可靠性：** 修复了在设备负载较高时导致手部跟踪停止工作的问题。

### <a name="dark-mode"></a>深色模式

许多Windows应用现在都支持深色和浅色模式。 HoloLens 2用户可以为支持这两者的应用选择默认模式。 更新后，默认应用模式为"深色"，**但** 可以轻松更改此设置：导航到设置  >    >    >  **选择默认应用模式**。 

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

更新后的应用与 Microsoft 365 集成，以帮助你跨设备完成更多操作 (当前仅US-English设备) 。 在HoloLens 2，Cortana不再支持某些特定于设备的命令，例如调整卷或重启。 新的系统语音命令现在支持这些选项。 在我们的博客 中[Cortana应用。](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)

### <a name="quality-improvements-and-fixes"></a>质量改进和修复

更新中的改进和修复：  
- 引入了主动显示校准系统。 此功能可提高全息影像的稳定性和对齐方式。 现在，当你将头部从一侧移到另一侧时，它们就位。
- 修复了一个 bug，Wi-Fi流式HoloLens定期中断。 如果应用程序指示它需要低延迟流式处理，请通过调用 [SetSocketMediaStreamingMode](/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)函数 来实现修复。
- 修复了在研究模式下流式传输期间发生的设备挂起。
- 修复了以下 bug：在某些情况下，恢复会话时不会在登录屏幕上显示正确的用户。
- 修复了用户无法通过 设置 导出 MDM **日志的问题**。
- 修复了以下问题：在开箱即用设置后立即进行眼动跟踪的准确性可能低于预期。
- 修复了在某些情况下眼动跟踪子系统无法初始化或执行校准的问题。
- 修复了提示已校准用户进行眼部校准的问题。
- 修复了驱动程序在眼部校准期间崩溃的问题。
- 修复了重复按下电源按钮可能导致 60 秒系统超时和 shell 崩溃的问题。
- 改进了深度缓冲区的稳定性。
- 在" **共享** "按钮反馈中心以便用户可以更轻松地共享反馈。
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

许多Windows应用同时支持深色和浅色模式。 HoloLens 2客户现在可以为支持这两种配色方案的应用选择默认模式。 根据客户反馈，我们将默认应用模式设置为"深色"，但你随时可以轻松更改此设置：导航到 **设置 > System > Colors** 以查找"选择默认应用模式"。 

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
