---
title: HoloLens 2发行说明
description: 随时了解每个新版本中HoloLens 2更新。
author: scooley
ms.author: scooley
manager: laurawi
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: medium
ms.date: 02/16/2021
ms.custom:
- CI 111456
- CSSTroubleshooting
audience: ITPro
appliesto:
- HoloLens 2
ms.openlocfilehash: 554dc796ee793a3f7e81108c6eb614a9555f10d7
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397338"
---
# <a name="hololens-2-release-notes"></a>HoloLens 2发行说明

为了确保你在 HoloLens 设备上获得高效体验，我们将继续发布功能、bug 和安全更新。 在此页上，可以看到 HoloLens 每月的新增功能。 若要获取最新的HoloLens 2更新，可以检查更新并手动更新，[](hololens-update-hololens.md#check-for-updates-and-manually-update)或获取完整闪存更新 (FFU) 通过高级恢复助手 来刷用[设备](hololens-recovery.md#clean-reflash-the-device)。 [下载](https://aka.ms/hololens2download)会保持最新，并提供最新的已发布版本。

## <a name="windows-holographic-version-21h1"></a>Windows Holographic 版本 21H1
- 内部版本 20346.1002

此更新包含两个目标受众的功能;最终用户可在设备上由任何人使用的功能，以及 IT 管理员可配置的新设备管理选项。 下表指定与每个受众相关的功能。 如果你是 IT 管理员，请查看我们的 IT 管理员 [- 更新清单](#it-admin---update-checklist)。
>[!IMPORTANT]
>若要更新到此内部版本，HoloLens 2 设备 () 当前必须运行 2021 年 2 月更新 (内部版本 19041.1136) 或更高版本。 如果看不到此功能更新可用，请先更新设备，然后重试。

>[!NOTE]
>目前，Microsoft HoloLens 2 支持每月服务更新 (bug 和安全修复) 适用于以下版本：
>- Windows Holographic 版本 20H2 (内部版本 19041.1128+) 
>- Windows Holographic 版本 2004 (内部版本 19041.1103+) 
>- Windows Holographic 版本 1903 (内部版本 18362+)  
>
> 随着 Windows Holographic 版本 21H1 的引入，我们将停止为 Windows 全息版本 **1903** 提供每月服务更新。 这使我们能够专注于较新版本，并继续提供有价值的改进。 


| 功能名称                                              | 简短说明                                                                      | 目标读者 | 
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新的 Microsoft Edge](#introducing-the-new-microsoft-edge)  | 新的基于 Chromium 的 Microsoft Edge 现在适用于 HoloLens 2。 | 最终用户 | 
[WebXR 和360查看器](#webxr-and-360-viewer) | 尝试沉浸式 web 体验和360视频播放。 | 最终用户 | 
[新建设置应用](#new-settings-app) | 旧的设置应用被更新的版本替换为新功能和设置。 | 最终用户 |
[显示颜色校准](#display-color-calibration) | 为 HoloLens 2 显示器选择备用颜色配置文件。 | 最终用户 |
[默认应用选取器](#default-app-picker) | 选择应为每个文件或链接类型启动的应用。 | 最终用户 |
[按应用音量控制](#per-app-volume-control) | 独立于系统卷控制应用级别卷。 | 最终用户 |
[安装 web 应用](#install-web-apps) | 在 HoloLens 2 上安装 web 应用，如 Microsoft Office，并提供新的 Microsoft Edge 浏览器。 | 最终用户 |
[刷到类型](#swipe-to-type) | 使用手指的笔尖在全息键盘上 "轻扫" 单词。 | 最终用户 |
[入门的 Power menu](#power-menu-from-start) | 在 "开始" 菜单上，重新启动并关闭 HoloLens 设备。 | 最终用户 |
[登录屏幕上列出了多个用户](#multiple-users-listed-on-sign-in-screen) | 在登录屏幕上显示多个用户帐户。 | 最终用户 |
[USB-C 外部麦克风支持](#usb-c-external-microphone-support) | 将 USB-C 麦克风用于应用和/或Remote Assist。 | 最终用户 |
[展台的访问者自动登录](#visitor-auto-logon-for-kiosks) | 启用"访问者帐户"上的自动登录以用于展台模式。 | IT 管理员 |
[展台模式下的新应用的新 AUMID](#use-the-new-settings-and-edge-apps-in-kiosk-modes)  | 新设置和 Edge 应用的 AUMID。 | IT 管理员 |
[改进了展台模式故障切换](#kiosk-mode-behavior-changes-for-handling-of-failures) | 展台模式在空的开始菜单之前查找"全局分配的访问权限"。 | IT 管理员 |
[页面设置可见性的新设置](#new-settings-uris-for-page-settings-visibility) | 设置/PageVisibilityList 策略的 20+ 新 SettingsURIS。 | IT 管理员 |
[配置回退诊断](#configuring-fallback-diagnostics-via-settings-app) | 在设置应用中设置回退诊断行为。 | IT 管理员 |
[与附近的设备共享内容](#share-things-with-nearby-devices) | 将文件或 URL 从 HoloLens 共享到电脑。 | 全部 |
[新的 OS 诊断跟踪](#new-os-diagnostic-traces) | OS 更新设置中的新疑难解答。 | IT 管理员 |
[传递优化预览版](#delivery-optimization-preview) | 减少从多个 HoloLens 设备下载的带宽消耗。 | IT 管理员 |

请查看相关的发行说明：

- [访问 HoloLens 仿真器存档](https://docs.microsoft.com/windows/mixed-reality/hololens-emulator-archive)
- [Dynamics 365 Remote Assist](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/remote-assist/version-history-remote-assist-hololens)

### <a name="introducing-the-new-microsoft-edge"></a>推出新的 Microsoft Edge

![将旧版 Microsoft Edge 徽标动画用于新的 Microsoft Edge 徽标](images/new-edge.gif)

新的 Microsoft Edge [采用 Chromium 开源项目](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) ，为客户提供更好的兼容性，并为 web 开发人员创建更少的网络碎片。

> [!IMPORTANT]
> 这一新的 Microsoft Edge 会自动替换旧的 Microsoft Edge，新版本中 [不再支持](https://blogs.windows.com/msedgedev/2021/03/09/microsoft-edge-legacy-end-of-support/) 该版本。

![新的 Microsoft Edge 屏幕截图](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>启动新的 Microsoft Edge

新的 Microsoft Edge ![新的 Microsoft Edge 图标](images/new_edge_logo.png) 用蓝色和绿色的漩涡图标表示的 () 固定到 "开始" 菜单，当你激活 web 链接时，将自动启动。

> [!NOTE]
> 首次在 HoloLens 2 上启动新的 Microsoft Edge 时，将从旧的 Microsoft Edge 导入设置和数据。 如果在启动新的 Microsoft Edge 后继续使用旧的 Microsoft Edge，则不会将新数据从旧的 Microsoft Edge 同步到新的 Microsoft Edge。

#### <a name="configuring-policy-settings-for-the-new-microsoft-edge"></a>为新的 Microsoft Edge 配置策略设置

新的 Microsoft Edge 为 IT 管理员提供了一组在 HoloLens 2 上提供的更广泛的浏览器策略，比以前在旧式 Microsoft Edge 中提供的更广泛。

下面是一些有用的资源，用于了解有关管理新的 Microsoft Edge 的策略设置的详细信息：

- [配置 Microsoft Intune 的 Microsoft Edge 策略设置](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge 传统到 Microsoft Edge 策略映射](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome 到 Microsoft Edge 策略映射](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- 完整的 [Microsoft Edge 企业文档](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 由于新的 Microsoft Edge 支持浏览器策略的数量，我们的团队无法保证每个新策略都在 HoloLens 2 上运行。 但是，我们已测试并确认了与以前在 HoloLens 2 上所支持的每个旧版 Microsoft Edge 策略等效的新的 Microsoft Edge。 请参阅 [Microsoft Edge 旧版与 Microsoft edge 策略映射](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) ，查找与在 HoloLens 2 中使用的每个旧版 microsoft edge 浏览器策略等效的新的 microsoft edge。
>
> 我们知道至少有两个新的Microsoft Edge策略 *将不能* 与HoloLens 2：
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>HoloLens 2 上新Microsoft Edge预期HoloLens 2

由于新Microsoft Edge是一个本机 Win32 应用，具有新的 UWP 适配器层，允许它在 HoloLens 2 等仅 UWP 设备上运行，因此某些功能可能不会立即可用。 我们将支持未来几个月的新方案和功能，因此请查看此空间了解最新信息。

**方案和功能预期可正常工作：**
- 首次运行体验、登录到配置文件和同步
- 网站应按预期呈现和行为
- 大多数浏览器功能 (收藏夹、历史记录等) 应正常工作
- 深色模式
- 将 Web 应用安装到设备
- 安装扩展 (请使用任何无法正常使用扩展的扩展，请HoloLens 2) 
- 查看和标记 PDF
- 单个浏览器窗口中的空间声音
- 自动和手动更新浏览器
- 使用"保存到 PDF"选项 (从"打印"菜单保存 PDF) 
- WebXR 和 360 查看器扩展
- 在环境中跨多个窗口浏览时，内容还原到正确的窗口

**不应正常工作的方案和功能：**
- 来自具有同步音频流的多个窗口的空间声音
- "看看它，说吧"
- 打印

**最常见的浏览器已知问题：**

- 为新的 Microsoft Edge 禁用了全息键盘中的放大镜预览。 我们希望在未来的更新中重新启用此功能，一旦放大倍数工作正常。
- 如果有另一个浏览器窗口处于打开和活动状态，则可以从错误的浏览器窗口播放音频。 通过关闭不应播放音频的其他活动窗口，可以解决此问题。
- 在 ["关注我" 模式下](hololens2-basic-usage.md#follow-me-stop-following)从浏览器窗口播放音频时，如果禁用 "关注我" 模式，则音频将继续播放。 可以通过在禁用 "关注我" 模式之前停止音频播放，或通过使用 **X** 按钮关闭窗口，来解决此问题。
- 与活动 Microsoft Edge windows 交互可能会导致其他2D 应用程序窗口意外停用。 您可以重新激活这些窗口，方法是再次与它们进行交互。

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge 预览体验渠道

Microsoft Edge 团队向边缘有问必答社区提供三个预览频道： Beta 版、开发人员版和 "未之限"。 安装预览频道不会卸载 HoloLens 2 上的 Microsoft Edge 的发行版，并且可以同时安装多个版本。 

若要深入了解边缘有问必答社区，请访问 [Microsoft Edge 有问必答主页](https://www.microsoftedgeinsider.com) 。 若要详细了解不同的边缘有问必答通道并开始，请访问 [边缘有问必答下载页面](https://www.microsoftedgeinsider.com/download)。

有几种方法可用于将 Microsoft Edge 有问必答通道安装到 HoloLens 2：

**直接安装在设备上 (当前仅适用于非托管设备)**
  1. 在 HoloLens 2 上，请访问 [边缘有问必答下载页面](https://www.microsoftedgeinsider.com/download)。
  1. 选择要安装的边缘有问必答频道的 "下载" " **HoloLens 2** " 按钮。
  1. 使用文件资源管理器) ，从边缘下载队列或设备的 "下载" 文件夹启动下载的 .msix 文件 (。
  1. 将启动[应用安装程序](app-deploy-app-installer.md)。
  1. 选择“安装”按钮。
  1. 成功安装后，你将在 Microsoft Edge Beta 的"所有应用"列表中找到"“开始”菜单"作为单独的条目。 

**通过具有 Windows 设备门户 ([的电脑进行](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) 安装需要在应用程序上启用开发人员HoloLens 2)**
  1. 在电脑上，访问 [Edge 预览体验成员下载页](https://www.microsoftedgeinsider.com/download)。
  1. 选择要 **安装的** Edge 预览体验成员通道的"下载Windows 10"按钮旁边的下拉箭头按钮。
  1. 在 **HoloLens 2** 菜单中选择"HoloLens 2"。
  1. 将 .msix 文件保存到电脑文件夹的"downloads" (或其他可以轻松找到) 。
  1. 使用 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 在电脑上安装下载的 .msix 文件HoloLens 2。
  1. 成功安装后，你将在 Microsoft Edge Beta 的"所有应用"列表中找到"“开始”菜单"作为单独的条目。 

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>使用 WDAC 阻止新Microsoft Edge

对于希望更新 [WDAC](windows-defender-application-control-wdac.md) 策略以阻止新的 Microsoft Edge 应用的 IT 管理员，需要将以下内容添加到策略。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>管理新终结点的Microsoft Edge

某些环境可能需要考虑网络限制。 若要确保顺利使用新 Edge，请 [启用这些 Microsoft 终结点。](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

详细了解 [HoloLens 当前可用的终结点](hololens-offline.md)。

### <a name="install-web-apps"></a>安装 Web 应用
 > [!Note]
>从 [Windows Holographic 版本 21H1](hololens-release-notes.md#windows-holographic-version-21h1)起，将不再预安装 Office Web 应用。

可以使用新的 Edge 将 Web 应用与 Microsoft Store一起安装。 例如，可以安装 Microsoft Office Web 应用来查看和编辑 SharePoint 或 OneDrive 上托管的文件。 若要安装 Office Web 应用，请访问并选择地址栏中的"应用可用"或"安装 https://www.office.com **Office"** 按钮。  选择 **"安装** "以确认。

> [!IMPORTANT]
> 仅当 HoloLens 2 具有活动 internet 连接时，Office web 应用功能才可用。

### <a name="webxr-and-360-viewer"></a>WebXR 和360查看器

新的 Microsoft Edge 包含对 WebXR 的支持，这是 (替换 WebVR) 的新标准，用于创建沉浸式 web 体验。 许多沉浸式 web 体验在设计上都是使用 VR (它们将视图的字段替换为虚拟环境) ，但 HoloLens 2 也支持这些体验。 WebXR 标准还启用了使用物理环境的扩充和混合现实沉浸式 web 体验。 随着开发人员花更多时间来 WebXR，我们预计新增加和混合现实的丰富体验将会为 HoloLens 2 客户尝试！

360查看器扩展基于 WebXR，并在新的 Microsoft Edge 和 HoloLens 2 上自动安装。 此 web 扩展使你能够在360度视频中从而深入了解。 YouTube 提供最大程度的360视频，因此我们鼓励你从这里开始。

#### <a name="how-to-use-webxr"></a>如何使用 WebXR

1. 导航到支持 WebXR 的网站。
1. 选择网站上的 " **输入** "。 此按钮的位置和视觉表示形式可能因网站而异，但它看起来可能类似于：

    ![输入 VR 按钮示例](images/75px-enter-vr.png)

1. 首次尝试在特定域上启动 WebXR 体验时，浏览器将要求同意输入沉浸式视图，并选择 " **允许**"。
1. 使用 [HoloLens 2 手势](hololens2-basic-usage.md#the-hand-tracking-frame) 来处理体验。
1. 如果体验没有 **退出** 按钮，请使用 [开始手势](hololens2-basic-usage.md#start-gesture) 返回 home。

**建议的 WebXR 示例**
- 360查看器 (参阅下一节) 
- [XR 恐龙](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR 绘制](https://threejs.org/examples/webxr_vr_paint.html)

#### <a name="how-to-use-360-viewer"></a>如何使用 360 查看器

1. 导航到 YouTube 上的 360 度视频。
1. 在视频帧中，选择混合现实头戴显示设备按钮：

    ![用于激活 360 查看器的按钮](images/enter-360-viewer.jpg)

1. 首次尝试在特定的域上启动 360 查看器时，浏览器会请求同意进入沉浸式视图。 选择“允许”。
1. [通过敲](hololens2-basic-usage.md#select-using-air-tap) 击打开播放控件。 使用 [手部光线和敲](hololens2-basic-usage.md#select-using-air-tap) 击播放/暂停、跳过向前/后退、打开/关闭字幕或停止体验 (退出沉浸式) 。 处于非活动状态几秒钟后，播放控件将消失。

#### <a name="top-webxr-and-360-viewer-known-issues"></a>WebXR 和 360 查看器已知问题
- 根据 WebXR 体验的复杂性，帧速率可能会下降或降低。
- 默认情况下，不支持 WebXR 中的铰接式手部。 开发人员可以通过打开"WebXR 手部输入" `edge://flags` 来启用支持。
- YouTube 外网站的 360 个视频可能无法如预期工作。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>提供有关 WebXR 和 360 查看器的反馈

请通过新文章中的"发送反馈"功能与我们的团队共享Microsoft Edge。

### <a name="new-settings-app"></a>新建设置应用

在此版本中，我们将引入新版本的"设置"应用。 新的"设置"应用包括以下HoloLens 2新功能和扩展设置：声音、电源 & 睡眠、网络 & Internet、应用、帐户、轻松访问等。

> [!NOTE]
> 由于新的 "设置" 应用不同于旧的 "设置" 应用，因此在更新时将删除以前在环境中放置的任何设置窗口。

![新设置应用主页](images/new-settings-app.png)

**新功能和设置**
- 设置搜索：使用关键字或设置的名称从 "设置" 主页搜索设置。
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
- 以前放置的"设置"窗口将被删除 (请参阅上面的) 。
- 无法再使用"设置"应用重命名设备。 IT 管理员可以通过使用设备名称模板Windows Autopilot MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName [HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot)重命名设备。
- "以太网"页显示一个 ("UsbNcm") 虚拟以太网设备。
- 由于 UWP 适配器层Microsoft Edge Win32 桌面应用程序的性质，新应用程序的电池使用情况可能不准确， (预计不会) 。

#### <a name="display-color-calibration"></a>显示颜色校准



借助此新设置，可以选择其他颜色配置文件来显示HoloLens 2配置文件。 这有助于颜色看起来更准确，尤其是在较低的显示亮度级别。 可以在"设置"应用的"系统校准"页上找到显示颜色>校准。

> [!NOTE]
> 由于此设置将新的颜色配置文件保存到显示固件，因此它是每个设备设置 (，并非每个用户帐户) 。

##### <a name="how-to-use-display-color-calibration"></a>如何使用显示颜色校准

1. 启动"**设置"** 应用并导航到 **"系统>校准"。**
1. 在 **"显示颜色校准"** 下，选择 **"运行显示颜色校准"** 按钮。
1. 显示颜色校准体验将启动，鼓励你确保视器处于正确的位置。
1. 在继续浏览指令对话框后，显示将自动灰显为 30% 的亮度。
    > [!TIP]
    > 如果在环境中看到灰色场景时遇到问题，可以使用设备左侧的亮度按钮手动HoloLens 2亮度级别。
1. 选择按钮 1-6 可立即试用每个颜色配置文件，并找到最适合你眼睛的颜色配置文件 (这通常意味着有助于场景显示最中性、灰度模式和外观色调按预期呈现的配置文件。) 

    ![显示颜色校准场景](images/color-cal-ui.png)
    
1. 当你对所选配置文件满意时，选择 " **保存 & 退出** " 按钮
1. 如果你不想进行更改，请选择 " **取消 & 退出** " 按钮，你的更改将恢复

> [!TIP]
> 下面是使用显示颜色校准设置时需要注意的一些有用提示：
> - 你可以根据需要从设置重新运行显示颜色校准
> - 如果设备上的任何人以前使用了更改颜色配置文件的设置，则最近更改的日期/时间将反映在 "设置" 页上
> - 重新运行 "显示颜色校准" 时，将突出显示以前保存的颜色配置文件，并且不会显示配置文件 0 (因为配置文件0表示显示的原始颜色配置文件) 
> - 如果要恢复到显示的原始颜色配置文件，可从 "设置" 页上 (参阅 [如何重置颜色配置文件](#how-to-reset-color-profile)) 

##### <a name="how-to-reset-color-profile"></a>如何重置颜色配置文件 

如果不满意保存到 HoloLens 2 的自定义颜色配置文件，则可以还原设备的原始颜色配置文件：
1. 启动 " **设置** " 应用，并导航到 " **系统 > 校准**"。
1. 在 " **显示颜色校准**" 下，选择 " **重置为默认颜色配置文件** " 按钮。
1. 当对话框打开时，如果已准备好重新启动 HoloLens 2 并应用所做的更改，请选择 " **重新启动** "。

#### <a name="top-display-color-calibration-known-issues"></a>顶部显示颜色校准已知问题

- 在 "设置" 页上，在重新加载设置页面之前，提示你上次更改颜色配置文件的状态字符串将过期。
    - 解决方法：选择其他设置页，然后重新选择校准页。

#### <a name="default-app-picker"></a>默认应用选取器

当你激活超链接或打开具有多个已安装的应用程序的文件类型（该应用程序支持该类型）时，你将看到一个新窗口打开，提示你选择哪个已安装的应用程序应处理文件或链接类型。 在此窗口中，你还可以选择让选定的应用处理文件或链接类型 "一次" 或 "始终"。

如果选择"始终"，但以后想要更改处理特定文件或链接类型的应用，可以在"设置"或"应用"> **重置保存的默认值**。 滚动到页面底部，选择"文件类型的默认应用"和/或"链接类型的默认应用"下的"清除"按钮。 与台式电脑上的类似设置不同，无法重置单个文件类型默认值。

#### <a name="per-app-volume-control"></a>每个应用音量控制

现在在此 Windows 内部版本中，用户可以手动调整每个应用的卷级别。 这样，用户可以更好地专注于所需的应用，或在使用多个应用时更好地听到这些应用。 例如，需要关闭一个应用的数量，同时调用另一个人在另一个应用中进行远程协助。

若要设置单个应用的音量，请导航 **到"设置** 系统声音"，并在"高级声音选项"下  ->    ->  选择"**应用音量和设备首选项"。**

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

#### <a name="swipe-to-type"></a>轻扫以键入

一些客户发现，通过轻扫要键入的单词的形状，在虚拟键盘上"键入"速度更快，我们正在预览全息键盘的此功能。 可以通过将手指的尖通过全息键盘的平面，轻扫该单词的形状，然后从键盘平面中收回手指的提示，一次轻扫一个词。 通过从键盘上删除单词之间的手指，无需按空格键即可轻扫后续字词。 如果在键盘上手指移动后看到轻扫线索，则你会知道该功能正在工作。

请注意，此功能可能难以使用和掌握，因为全息键盘的性质与手机显示设备不同， (对手指的抵御) 。 

### <a name="power-menu-from-start"></a>"开始"中的电源菜单

允许用户注销、关闭和重启设备的新菜单。 HoloLens “开始”屏幕指示系统更新何时可用。

#### <a name="how-to-use"></a>如何使用

1. 使用 [开始手势](hololens2-basic-usage.md#start-gesture) 或说 "前往开始时间" 打开 HoloLens 开始屏幕。

2. 请注意，用户配置文件图片旁边的省略号图标 ( ) ：

   <img alt="ser context dots, ..." src="./images/powertransition_icon_default_cropped.png" width="586" height="330" />

3. 使用手或语音命令 "电源" 选择用户配置文件图片。

4. 此时将显示一个菜单，其中包含用于注销、重新启动或关闭设备的选项：

   <img alt="User context menu" src="./images/powertransition_aad_options_cropped.png" width="586" height="330" />

5. 选择要注销、重启或关闭 HoloLens 的菜单选项。 "注销" 选项可能不可用，如果设备设置为 [单一 Microsoft 帐户 (MSA) 或本地帐户](hololens-identity.md)。

6. 通过触摸任何其他位置或使用开始手势关闭开始菜单，消除菜单。

#### <a name="update-indicator"></a>更新指示器

当更新可用时，省略号图标会亮起，指示重新启动将会安装更新。菜单选项还会更改，以反映更新的状态。<br/><br/>

<img alt="User context menu showing update" src="./images/powertransition_aad_options_update_cropped.png" width="470" height="313" />

### <a name="multiple-users-listed-on-sign-in-screen"></a>登录屏幕上列出了多个用户

以前的登录屏幕只显示最近登录的用户，以及 "其他用户" 入口点。 如果有多个用户登录到设备，我们已收到客户反馈。 它们仍需要重新键入其用户名等。

在此 Windows 版本中引入的，选择位于 "PIN 输入" 字段右侧的 " **其他用户** " 时，"登录" 屏幕将显示多个以前登录到设备的用户。 这允许用户选择其用户配置文件，然后使用他们的 Windows Hello 凭据进行登录。 还可以通过 " **添加帐户** " 按钮将新用户添加到该设备。

在 "其他用户" 菜单中，"其他用户" 按钮将显示最后一个登录到设备的用户。 选择此按钮可返回到此用户的登录屏幕。

![登录屏幕默认值](./images/multiusers1.jpg)

<br>

![其他用户登录屏幕](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 外部麦克风支持

> [!IMPORTANT]
> 插入 **USB 麦克风不会自动将其设置为输入设备**。 在插入一组 USB-C 耳机时，用户将观察到耳机的音频将自动重定向到耳机，但 HoloLens OS 将内部麦克风阵列的优先级设置为高于任何其他输入设备。 **若要使用 USB-C 麦克风，请执行以下步骤。**

用户可以使用"声音设置"面板选择已连接 USB-C **的外部** 麦克风。 USB-C 麦克风可用于通话、录制等。

打开"**设置"** 应用，然后选择"**系统**  >  **声音"。**

![声音设置](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 若要将外部麦克风与 **Remote Assist，用户** 需要单击"管理声音设备"超链接。
>
> 然后，使用下拉列表将外部麦克风设置为"默认" **或** " **通信默认值"。** 选择 **"** 默认"意味着外部麦克风将在所有位置使用。
>
> 选择 **"** 通信默认值"意味着外部麦克风将用于 Remote Assist和其他通信应用，但 HoloLens 麦克风阵列仍可用于其他任务。

![管理声音设备](images/usbc-mic-2.png)

<br>

![设置麦克风默认值](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>蓝牙麦克风支持呢？

遗憾的是，蓝牙麦克风目前仍不受 HoloLens 2。

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C 麦克风疑难解答

请注意，某些 USB-C 麦克风错误地将自身报告为 *麦克风和扬声器* 。 这是麦克风的问题，而不是 HoloLens 的问题。 将其中一个麦克风插入 HoloLens 时，可能会丢失声音。 幸运的是，有一个简单的修补程序。  

在 "**设置**  ->  **系统**  ->  **声音**" 中，显式设置内置扬声器 **(模拟功能音频驱动程序)** 作为 **默认设备**。 即使删除了麦克风并稍后重新连接，HoloLens 也应记住此设置。

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

可以通过 [自定义 OMA URI](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10) 策略来管理访问者自动登录：

- URI 值：./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon

| 策略  | 描述   | 配置  |
|---|---|---|
| MixedReality/VisitorAutoLogon  | 允许访问者自动登录到展台   | 1 (是) ，0 (否，默认值为 )   |

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>在展台模式下使用新的设置和 Edge 应用

在展台 [中](hololens-kiosk.md)包括应用时，IT 管理员通常会将应用添加到展台，但使用应用用户模型 ID (AUMID) 。 由于设置应用和 Microsoft Edge 应用都被视为新应用，并且不同于使用这些应用的 AUMID 的较旧应用展台，因此需要更新以使用新的 AUMID。

修改展台以包含新应用时，建议在新的 AUMID 中添加 ，并保留旧应用。 当用户更新 OS 且无需接收新策略以继续使用展台时，这将创建一个简单的转换。

| 应用                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 旧设置应用       | HolographicSystemSettings_cw5n1h2txyewy！应用程序            |
| 新建设置应用       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！应用程序 |
| 旧 Microsoft Edge 应用 | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新建Microsoft Edge应用 | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>展台模式行为更改，用于处理故障

在较早的生成中，如果设备具有展台配置（这是全局分配的访问权限和 AAD 团队成员分配的访问权限的组合）时，如果确定 AAD 组成员身份失败，用户将看到"开始"[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)菜单中未显示任何内容。

从此 Windows 版本开始，展台体验将回退到全局展台配置 (在 AAD 组展台模式) 发生故障时出现。

### <a name="new-settings-uris-for-page-settings-visibility"></a>页面设置可见性的新设置 URI

在 [Windows Holographic 版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中，我们添加了 ["设置/PageVisibilityList"](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 策略，以限制在"设置"应用中看到的页面。 PageVisibilityList 是一种策略，允许 IT 管理员阻止系统设置应用中的特定页面可见或可访问，或者对除指定页面以外的所有页面执行此操作。

如果访问 ["页面设置可见性"，](settings-uri-list.md)可以找到有关使用此 CSP 的说明，以及以前版本中提供的 URI 列表。

我们正在扩展可用设置 URI 的列表，IT 管理员可以管理这些 URI。 其中一些 Uri 适用于新的设置应用内的新可用区域。 如果你使用的是设置/PageVisibilityList 策略，请查看以下列表，并根据需要调整你允许或阻止的页面。

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
| 系统>声音                                       | `ms-settings:sound`                                |
| 系统>声音>应用音量和设备首选项 | `ms-settings:apps-volume`                          |
| 系统>声音>管理声音设备              | `ms-settings:sound-devices`                        |
| 系统>存储>配置存储感知         | `ms-settings:storagepolicies`                      |
| 语言&>日期&时间                        | `ms-settings:dateandtime`                          |
| 语言&键盘>时间                           | `ms-settings:keyboard`                             |
| 语言&时间>语言                           | `ms-settings:language`                             |
| 语言&时间>语言                           | `ms-settings:regionlanguage-languageoptions`       |
| 更新&安全>重置&恢复               | `ms-settings:reset`                                |

#### <a name="updated-uris"></a>更新的 URI

以前，以下两个 URI 不会将用户直接进入所指示的页面，而只会阻止主更新页面。 以下项已更新为直接导航到其页面：

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>通过设置应用配置回退诊断

现在，在"设置应用"中，用户可以配置 [回退诊断 的行为](hololens-diagnostic-logs.md)。 在"设置"应用中，**导航到**  ->  **"隐私疑难解答"** 页以配置此设置。

> [!NOTE]
> 如果为设备配置了 MDM 策略，则用户将无法重写该行为。  

### <a name="share-things-with-nearby-devices"></a>与附近的设备共享内容

与靠近Windows 10共享内容，包括电脑和其他HoloLens 2设备。 可以在设置 **系统共享体验** 中试用它，以将文件或 URL 从  ->    ->  HoloLens 共享到电脑。 有关更多详细信息，请阅读有关如何在 Windows 10 中[与附近的设备共享Windows 10。](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)

此功能可通过 [连接/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)进行管理。

### <a name="new-os-diagnostic-traces"></a>新操作系统诊断跟踪

除了在 "设置" 应用程序中使用前面的疑难解答外，还添加了新的疑难解答，同时添加了新的 OS 更新设置应用。 导航到 "**设置**" "  ->  **更新 &amp; 安全**  >  **疑难解答**"  >  **Windows 更新** 并选择 "**启动**"。 这样，你就可以收集跟踪，同时在操作系统更新中重现你的问题，以帮助更好地帮助你的 IT 或支持人员进行故障排除。

### <a name="delivery-optimization-preview"></a>传递优化预览

使用此更新，Windows 全息版可实现交付优化设置，减少从多个 HoloLens 设备下载的带宽消耗。 此处提供了此功能以及推荐的网络配置的完整描述： [Windows 10 更新的传递优化](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)。

以下设置作为管理界面的一部分启用， [可以从 Intune 进行配置](https://docs.microsoft.com/mem/intune/configuration/delivery-optimization-settings)：

- [DOCacheHost](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehost)
- [DOCacheHostSource](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-docachehostsource)
- [DODelayCacheServerFallbackBackground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackbackground)
- [DODelayCacheServerFallbackForeground](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodelaycacheserverfallbackforeground)
- [DODownloadMode](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dodownloadmode)
- [DOMaxBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxbackgrounddownloadbandwidth)
- [DOMaxForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-domaxforegrounddownloadbandwidth)
- [DOPercentageMaxBackgroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxbackgroundbandwidth)
- [DOPercentageMaxForegroundBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dopercentagemaxforegroundbandwidth)
- [DOSetHoursToLimitForegroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitforegrounddownloadbandwidth)
- [DOSetHoursToLimitBackgroundDownloadBandwidth](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deliveryoptimization#deliveryoptimization-dosethourstolimitbackgrounddownloadbandwidth)

有关此预览版的一些注意事项：

- 在此预览版中，HoloLens 支持仅限于 OS 更新。
- Windows Holographic for Business仅支持 HTTP 下载模式和从 Microsoft 联网缓存 [终结点进行下载](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache);HoloLens 设备目前不支持对等下载模式和组分配。
- HoloLens 不支持对终结点进行部署或Windows Server Update Services优化。
- 故障排除将需要在 联网缓存 服务器上进行诊断，或通过设置更新和安全性故障排除在 HoloLens 上的 HoloLens上&  >  **跟踪**  >     >   Windows 更新。

### <a name="it-admin---update-checklist"></a>IT 管理员 - 更新清单

此清单将帮助你了解在此功能更新中添加的可能影响当前设备管理配置的新功能，或者你可能想要开始使用的新功能。

#### <a name="updates-to-kiosk-mode"></a>展台模式的更新

✔️ [**展台模式下的新应用新建 AUMID：**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

如果以前在展台中Microsoft Edge设置应用或应用，我们将这些应用替换为使用不同的应用 ID 的新应用。 强烈建议阅读下面的展台模式下的新[应用的新 AUMID。](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 这将确保展台中继续包含"设置"应用，或包括新的Microsoft Edge应用。 现在可以完成这些更改，并部署到所有设备，并允许在更新时更顺畅地转换。

✔️ [**展台的访问者自动登录：**](#visitor-auto-logon-for-kiosks) 

访问者现在可以自动登录到展台。 默认情况下，此行为处于启用状态，但可以管理和禁用。

✔️ [**改进的展台模式故障切换**](#kiosk-mode-behavior-changes-for-handling-of-failures)：

如果未成功确定已登录 AAD 用户的 AAD 组成员身份，则全局展台配置用于开始菜单 (如果存在) 则向用户显示空的开始菜单。 尽管空 "开始" 菜单不是可以直接设置的配置，但如果您使用的是展台，则这种新的处理可能会告诉您的支持部门，因为这可能适用于您的配置，或者您可能想要对分配的访问配置进行新调整。

#### <a name="updates-to-page-settings-visibility"></a>页面设置可见性更新

[**为页面设置可见性✔️新的设置 uri**](#new-settings-uris-for-page-settings-visibility)

如果你当前正在使用 [页面设置可见性](settings-uri-list.md) ，则你可能希望对已允许或阻止的现有 uri 进行调整。

#### <a name="updates-for-your-wdac-policy"></a>适用于 WDAC 策略的更新
✔️如果以前通过 WDAC 阻止 Microsoft Edge，则需要更新你的 WDAC 策略。 请查看以下代码，并使用提供的示例代码。
#### <a name="enable-new-endpoints-for-edge"></a>启用边缘的新终结点
✔️如果你有涉及配置网络终结点（例如代理或防火墙）的基础结构，请为新的 Microsoft Edge 应用启用这些新的终结点。

#### <a name="newly-configurable-items"></a>新的可配置项

✔️ [配置回退诊断](#configuring-fallback-diagnostics-via-settings-app)：你可以配置是否和谁可以收集回退诊断。

✔️[与附近设备共享内容](#share-things-with-nearby-devices)：你可以禁用新的邻近共享功能。

✔️ [为新的 Microsoft Edge 配置策略设置](#configuring-policy-settings-for-the-new-microsoft-edge)：查看适用于 Microsoft edge 的新配置。

#### <a name="new-diagnostic-tool"></a>新的诊断工具

✔️[新 os 诊断跟踪](#new-os-diagnostic-traces)：收集与 OS 更新相关的日志。

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：

- [脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics) 还将包含序列号和操作系统版本的其他设备信息。
- 解决了通过运行时预配包部署业务线应用程序的问题。
- 解决了业务线应用程序安装状态报告问题。
- 修复了跨设备重置的新应用程序包持久性的问题。
- 修复了可能导致在 Edge 中为日本客户键入错误符号的问题。
- 提高预安装应用（如 Edge）上的 OS 更新的复原能力。 
- 解决影响应用程序安装的更新可靠性Microsoft Edge。 


## <a name="windows-holographic-version-20h2--may-2021-update"></a>Windows Holographic 版本 20H2 - 2021 年 5 月更新
- 内部版本 19041.1146

更新中的改进和修复：
- 此每月质量更新不包含任何值得注意的更改，建议试用最新内部版本 Windows Holographic 版本 21H1。

## <a name="windows-holographic-version-1903---may-2021-update"></a>Windows Holographic 版本 1903 - 2021 年 5 月更新
- 内部版本 18362.1110

更新中的改进和修复：
- 此每月质量更新不包含任何显著更改。 **此生成将不再接收每月服务更新**。 我们建议你试用最新内部版本 Windows Holographic 版本 21H1。



## <a name="windows-holographic-version-20h2---april-2021-update"></a>Windows Holographic 版本 20H2 - 2021 年 4 月更新
- 内部版本 19041.1144

更新中的改进和修复：

- 修复了有关业务线应用程序安装状态报告的问题。

## <a name="windows-holographic-version-1903---april-2021-update"></a>Windows Holographic 版本 1903 - 2021 年 4 月更新
- 内部版本 18362.1108

更新中的改进和修复：

- 解决了尝试更改本地帐户的密码时设置应用崩溃的问题。


## <a name="windows-holographic-version-20h2---march-2021-update"></a>Windows 全息，版本 20H2-2021 年3月更新
- 生成19041.1140

更新中的改进和修复：

- 使用 AdvancedPhotoCapture 或 LowLagPhotoCapture 捕获照片和 HoloLens 2 的客户现在可以在捕获照片后，最多运行3秒钟。
- 修复设备门户服务中的内存泄漏问题导致其他应用程序无法分配内存，导致其他应用程序的内存使用率增加。
- 解决了在分阶段推出中注册的用户无法登录到该设备的问题。

## <a name="windows-holographic-version-1903---march-2021-update"></a>Windows 全息，版本 1903-2021 更新
- 生成18362.1102

更新中的改进和修复：

- 修复设备门户服务中的内存泄漏问题导致其他应用程序无法分配内存，导致其他应用程序的内存使用率增加。

## <a name="windows-holographic-version-20h2---february-2021-update"></a>Windows 全息，版本 20H2-2021 年2月更新
- 生成19041.1136

更新中的改进和修复：

- 修复了初始设备安装和应用程序更新的相关问题。
- 解决了以后的 HoloLens 版本的升级和航班问题。
- 从 HoloLens 设备上删除了来自 eSIM 根存储的未使用的预安装证书。

## <a name="windows-holographic-version-1903---february-2021-update"></a>Windows 全息，版本 1903-2021 更新
- 生成18362.1098

这一月度质量更新不包含任何显著的更改，我们建议你试用最新版本的 Windows 全息2004版。

## <a name="windows-holographic-version-20h2---january-2021-update"></a>Windows Holographic 版本 20H2 - 2021 年 1 月更新
- 内部版本 19041.1134

更新中的改进和修复：

- 改进了在设备上有许多用户时启动、恢复和用户切换期间的性能。
- 添加了对研究模式 的 arm32 [支持](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/research-mode)。

## <a name="windows-holographic-version-1903---january-2021-update"></a>Windows Holographic 版本 1903 - 2021 年 1 月更新
- 内部版本 18362.1091

此每月质量更新不包含任何值得注意的更改，建议试用 Windows Holographic 版本 2004 的最新版本。

## <a name="windows-holographic-version-20h2--december-2020-update"></a>Windows Holographic 版本 20H2 - 2020 年 12 月更新
- 内部版本 19041.1131

### <a name="install-apps-on-hololens-2-via-app-installer"></a>通过 HoloLens 2 在 应用安装程序

我们正在 **添加新的 (应用安装程序) ，** 以便你能够更无缝地在 HoloLens 2 设备上安装应用程序。 对于非 **托管设备，此功能默认为打开状态**。 为了防止企业中断，应用安装程序 **目前不适用于托管** 设备。  

如果以下任一情况 **成立，则** 设备被视为"托管"设备：
- MDM [已注册](hololens-enroll-mdm.md)
- 配置了 [预配包](hololens-provisioning.md)
- 用户 [标识](hololens-identity.md) Azure AD

现在可以安装应用，而无需启用开发人员模式或设备门户。  只需 (USB 或 Edge) Appx 捆绑包下载到设备，然后导航到 文件资源管理器 中的 Appx 捆绑包，以提示你启动安装。  或者， [通过网页启动安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。  与使用 MDM 的 LOB 应用部署功能从 Microsoft Store 或旁加载安装的应用一样，需要使用 [签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 对应用进行数字签名，并且在部署应用之前，必须由 HoloLens 设备 [信任用于签署的证书](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 。

**应用程序安装说明。**

1.  确保你的设备不被视为托管设备
1.  确保你的 HoloLens 2 设备已开机并连接到你的电脑
1.  确保已登录到 HoloLens 2 设备
1.  在电脑上导航到自定义应用，并将 yourapp 复制到 yourdevicename\Internal Storage\Downloads。   完成文件复制后，可以断开与设备的连接
1.  在 HoloLens 2 设备上，打开 "开始" 菜单，选择 "所有应用"，然后启动 "文件资源管理器" 应用。
1.  导航到 "下载" 文件夹。 你可能需要在应用程序的左侧面板上选择 "此设备"，然后导航到 "下载"。
1.  选择 yourapp 文件。
1.  应用程序安装程序将启动。 选择 "安装" 按钮以安装您的应用程序。
安装完成后，安装的应用将自动启动。

可以在 [Windows 通用示例 GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) 上找到示例应用来测试此流程。

阅读有关在 [HoloLens 2 上通过应用安装程序安装应用](app-deploy-app-installer.md)的完整过程。  

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：

- 手动跟踪现在可以在很多新情况下维护跟踪，这种情况先前会丢失。  在某些新情况下，只有手部位置会继续根据用户的实际手部进行更新，而其他连接则根据以前的姿势进行推断。  此更改有助于提高动作（如击球、引发、跳跃和击球）的跟踪一致性。  它还有助于手靠近表面或持有对象的情况。  在推断手部时 [，每个联合](https://docs.microsoft.com/uwp/api/windows.perception.people.jointposeaccuracy?view=winrt-19041&preserve-view=true) 准确度值将设置为"近似"，而不是"高"。
- 修复了帐户的 PIN 重置Azure AD显示错误"出现问题的问题。
- 启动 ET、设置应用中的 Iris、新用户或通知 toast 时，用户应看到更少的启动后 OOBE 故障。
- 用户应具有来自 OOBE 的正确时区。

## <a name="windows-holographic-version-1903--december-2020-update"></a>Windows Holographic 版本 1903 - 2020 年 12 月更新
- 内部版本 18362.1088

此每月质量更新不包含任何值得注意的更改，建议试用最新的 Windows Holographic 版本 20H2 – 2020 年 12 月更新和内部版本中新增的 应用安装程序 功能。


## <a name="windows-holographic-version-20h2"></a>Windows Holographic 版本 20H2
- 内部版本 19041.1128

Windows Holographic 版本 20H2 现已发布，为用户和 IT 专业人员HoloLens 2一系列新功能。 从"自动眼定位"到"设置"中的证书管理器，到改进的展台模式功能和新的 Autopilot 设置功能。 此新更新使 IT 团队能够更精细地控制 HoloLens 设备的配置和管理，并为用户提供更无缝的全息体验。 

此最新版本是版本 2004 的每月更新，但这次我们将包含新功能。 主内部版本号将保持不变，Windows 更新版本 2004 (版本 19041 版本) 。 可以在"设置"的"关于>中查看"生成号"，以确认你位于最新的可用内部版本 19041.1128+ 上。 若要更新到最新版本，请打开"设置"应用，转到"更新&安全性"，然后点击"检查更新"。 有关如何管理 HoloLens 更新的详细信息，请访问 [此页](https://docs.microsoft.com/hololens/hololens-updates)。

### <a name="whats-new-in-windows-holographic-version-20h2"></a>Windows 全息版20H2 中的新增功能  

| 功能                                              | 说明                                                                                                                                     |
|------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| [自动目视定位支持](hololens-release-notes.md#auto-eye-position-support) | 主动计算眼睛位置，无需用户通过目视跟踪校准。   |
| [证书管理器](hololens-release-notes.md#certificate-manager)   | 允许从 "设置" 应用程序中安装和删除证书的更简单方法。     |
| [从 USB 自动启动设置](hololens-release-notes.md#auto-launch-provisioning-from-usb)                    | 在 USB 驱动器上预配包会自动提示 OOBE 中的设置页面。                                                         |
| [自动确认在 OOBE 中预配包](hololens-release-notes.md#auto-confirm-provisioning-packages-in-oobe)           | 预配页面会在 OOBE 期间自动应用预配包。                                                         |
| [无需使用 UI 即可自动预配](hololens-release-notes.md#automatic-provisioning-without-using-ui) | 如何将设置自动启动和自动确认组合在一起。 |
| [将 Autopilot 与 Wi-Fi 连接结合使用](hololens-release-notes.md#using-autopilot-with-wi-fi-connection) | 从设备 Wi-Fi 使用 autopilot，无需使用以太网适配器。 |
| [Tenantlockdown CSP 和 Autopilot](hololens-release-notes.md#tenantlockdown-csp-and-autopilot)                     | 应用租户注册并应用策略后，在设备重置或重新刷新时，设备只能在该租户中注册。 |
| [全局分配的访问权限](hololens-release-notes.md#global-assigned-access--kiosk-mode)                               | 适用于多个 app 展台模式的新配置方法，它在系统级别应用展台，使其适用于所有内容。                  |
| [在多应用展台中自动启动应用](hololens-release-notes.md#automatic-launch-of-an-application-in-multiple-app-kiosk-mode)                | 将应用程序设置为在登录到多应用展台模式时自动启动。                                                        |
| [用于处理故障的展台模式行为更改](hololens-release-notes.md#kiosk-mode-behavior-changes-for-handling-of-failures) | 展台模式故障现在具有限制性回退。                                                                                                |
| [HoloLens 策略](hololens-release-notes.md#hololens-policies)                                    | HoloLens 的新策略。     |
| [缓存Azure AD展台的组成员身份](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)         | 新策略允许用户使用组成员身份缓存在设置的天数内脱机使用展台模式。                                        |
| [新的设备限制策略HoloLens 2](hololens-release-notes.md#new-device-restriction-policies-for-hololens-2)       | 为设备管理策略启用了新启用的设备HoloLens 2。                                                                                |
| [新的电源策略HoloLens 2](hololens-release-notes.md#new-power-policies-for-hololens-2)       | 新支持的电源超时设置策略。  |
| [更新策略](hololens-release-notes.md#newly-enabled-update-policies-for-hololens)        | 新启用的策略允许控制更新。           |
| [已启用的"设置"页可见性HoloLens 2](hololens-release-notes.md#enabled-settings-page-visibility-for-hololens-2)      | 用于选择"设置"应用中显示的页面的策略。             |
| [研究模式](hololens-release-notes.md#research-mode) | 在 HoloLens 2 上使用研究模式。 |
| [录制长度增加](hololens-release-notes.md#recording-length-increased) | MRC 录制不再上限为 5 分钟。 |
| [更新中的改进和修复](hololens-release-notes.md#improvements-and-fixes-in-the-update)                 | 更新中的其他修补程序。   |

### <a name="auto-eye-position-support"></a>自动眼部位置支持

在 HoloLens 2 中，目视定位可实现准确的全息影像定位、舒适的观看体验，并改善了显示质量。 目视位置作为眼睛跟踪计算的一部分在内部进行计算。 但是，这要求每个用户都要经历眼睛跟踪校准，即使在体验可能不需要目视输入时也是如此。

**自动排列位置 (AEP)** 通过无交互的方式来计算用户的眼睛位置。 自动目视位置在用户将设备置于设备上的时刻自动开始运行。 如果用户没有先前的目视跟踪校准，则在处理时间为 20-30 秒后，自动目视定位将开始向显示系统提供用户的眼睛位置。 用户数据不会保留在设备上，因此如果用户关闭并重新打开设备，或者设备重新启动或从睡眠状态唤醒，则此过程将重复。

当 uncalibrated 用户进入设备时，会有一些系统行为随 "自动目视定位" 功能发生变化。 在这种情况下，uncalibrated 用户指的是先前尚未经历设备上的目视跟踪校准过程的人。

| 活动应用程序 | 之前的行为 | Windows 全息版20H2 更新中的行为 |
|:-------------------|:-----------------|:-----------------------------------|
| 未启用注视的应用或全息 Shell |显示 "目视跟踪校准提示" 对话框。 | 不显示提示。 |
| 已启用注视的应用 | 显示 "目视跟踪校准提示" 对话框。 | 仅当应用程序访问眼睛注视流时才显示眼睛跟踪校准提示。 |

如果用户从未启动的已启用的应用程序转换到访问看不到的数据的应用程序，则将显示校准提示。 

当当前用户没有活动的目视跟踪校准时，所有其他系统行为将类似于。 例如，不会启用单手启动手势。 初始设置时，不会更改"开箱即用体验"。

对于需要眼睛凝视数据或非常精确的全息影像定位的体验，我们建议未校准的用户运行眼动跟踪校准。 可以通过眼动跟踪校准提示或从开始菜单启动"设置"应用，然后选择"系统"">校准 **">""** 眼>校准"来访问它。

稍后可与其他校准信息 [一起找到此信息](hololens-calibration.md#auto-eye-position-support)。 

### <a name="certificate-manager"></a>证书管理器

- 通过新的证书管理器改进了设备安全性和符合性的审核、诊断和验证工具。 此功能可让你在商业环境中大规模部署、排查和验证证书。

在 Windows Holographic 版本 20H2 中，我们将在"设置"应用中添加HoloLens 2管理器。 转到"**设置>更新&安全>证书"。** 此功能提供了一种简单且用户友好的方式来查看、安装和删除设备上证书。 借助新的证书管理器，管理员和用户现在改进了审核、诊断和验证工具，以确保设备保持安全且合规。 

-   **审核：** 能够验证证书是否正确部署，或确认证书已正确删除。 
-   **诊断：** 出现问题时，验证设备上是否存在相应的证书可节省时间，并有助于进行故障排除。 
-   **验证：** 验证证书是否符合预期目的且正常运行，可以节省大量时间，尤其是在商业环境中，然后再大规模部署证书。

若要在列表中快速查找特定证书，有一些选项可以按名称、存储或到期日期进行排序。 用户还可以直接搜索证书。 若要查看单个证书属性，请选择证书，然后单击"信息 **"。** 

证书安装当前支持 .cer 和 .crt 文件。 设备所有者可以在本地计算机和当前用户中安装证书; 所有其他用户只能安装到当前用户。 用户只能删除直接从 "设置" UI 安装的证书。 如果通过其他方式安装了证书，则该证书还必须通过相同的机制删除。

#### <a name="to-install-a-certificate"></a>若要安装证书： 

1.  将 HoloLens 2 连接到 PC。
1.  将要安装的证书文件放在 HoloLens 2 上的某个位置。
1.  导航到 " **设置" 应用 > 更新 & 安全 > 证书**，并选择 "安装证书"。
1.  单击 " **导入文件** "，并导航到保存证书的位置。
1.  选择 " **存储位置**"。
1.  选择 " **证书存储**"。
1.  单击“安装”  。

现在应在设备上安装证书。

#### <a name="to-remove-a-certificate"></a>删除证书的步骤： 
1. 导航到 " **设置" 应用 > 更新和安全 > 证书**"。
1. 在搜索框中按名称搜索证书。
1. 选择证书。
1. 单击 "**删除**"
1. 出现确认提示时，选择“是”。

!["设置" 应用中的证书查看器](images/certificate-viewer-device.jpg)

![显示如何使用证书 UI 安装证书的图片](images/certificate-device-install.jpg)

稍后可 [在新的证书管理器页中](certificate-manager.md)找到此信息。

### <a name="auto-launch-provisioning-from-usb"></a>从 USB 自动启动设置

- 在 OOBE 期间使用带预配包的 USB 驱动器时，自动化过程允许较少的用户交互。

在此版本之前，用户必须手动在 OOBE 期间启动预配屏幕，才能使用按钮组合进行预配。 现在，用户可以通过使用 USB 存储驱动器上的预配包跳过按钮组合。 

1. 在 OOBE 的第一个可交互时刻使用预配包插入 USB 驱动器
1. 当设备准备好进行预配时，它会自动打开包含预配页的提示。 

注意：如果在设备启动时 USB 驱动器已接通电源，则 OOBE 将枚举现有的 USB 存储设备，并监视插入的其他 USB 存储设备。

有关在 OOBE 期间应用预配包的信息，请访问 [HoloLens 预配](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup) 文档。

有关从 [USB 自动启动预配](hololens-provisioning.md#auto-launch-provisioning-from-usb) 的其他信息，请参阅 HoloLens 预配文档。

### <a name="auto-confirm-provisioning-packages-in-oobe"></a>在 OOBE 中自动确认预配包
- 自动化过程允许较少的用户交互，当显示"预配包"页时，它将自动应用列出的所有包。

当预配主屏幕出现时，OOBE 将倒计时 10 秒，然后自动开始应用所有预配包。 在验证 [预期的包](hololens-provisioning.md#auto-confirm-provisioning-packages-in-oobe) 后，用户仍然可以在此 10 秒内确认或取消。

### <a name="automatic-provisioning-without-using-ui"></a>无需使用 UI 即可自动预配
- 合并了自动过程，减少了预配的设备交互。 

通过将从 USB 设备自动启动预配和自动确认预配包相结合，用户可以自动预配 HoloLens 2 设备，而无需使用设备的 UI，甚至无需设备。 你可以继续为多个设备使用相同的 USB 驱动器和预配包。 这可用于在同一区域中一次部署多个设备。 

1. 使用[Windows 配置设计器](https://www.microsoft.com/store/productId/9NBLGGH4TX22)[创建预配包](hololens-provisioning.md)。 
1. 将包复制到 USB 存储驱动器。
1. 将[HoloLens 2 刷新](hololens-insider.md#ffu-download-and-flash-directions)到[19041.1361 或更高版本](https://aka.ms/hololens2previewdownload)。 
1. 当 [高级恢复助理](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 已完成时，设备将拔出 USB-C 电缆。 
1. 将 u 盘插入设备。
1. 当 HoloLens 2 设备启动到 OOBE 时，它会自动检测 USB 驱动器上的预配包，并启动设置页面。
1. 10秒后，设备会自动应用预配包。 

你的设备现在已配置，并将 [显示设置成功屏幕](hololens-provisioning.md#automatic-provisioning-without-using-ui)。

### <a name="using-autopilot-with-wi-fi-connection"></a>将 Autopilot 与 Wi-Fi 连接结合使用
- 通过使 Autopilot 能够在 Wi-Fi 连接的设备上正常工作，已消除了将 USB C 适配器连接到以太网以降低硬件需求的需要。

现在，在 OOBE 期间，一旦使用 Wi-fi 连接了 HoloLens 2，OOBE 就会检查设备的 Autopilot 配置文件。 如果找到一个，它将用于完成 AAD 联接和注册流的其余部分。 换句话说，不再需要使用以太网到 USB-C 或 Wi-Fi 到 USB-C 适配器，因为在 OOBE 开始时提供了它们。 详细了解 [适用于 HoloLens 2 设备的 Autopilot](hololens2-autopilot.md)。

### <a name="tenantlockdown-csp-and-autopilot"></a>Tenantlockdown CSP 和 Autopilot
- 通过设备重置或刷新将设备锁定到租户，从而使其在组织的租户上保持不变。 通过设置，禁止在中创建帐户，从而增强安全性。 

HoloLens 2 设备现在支持 TenantLockdown CSP，如 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2)。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 使 HoloLens 2 仅限使用 Autopilot 绑定到 MDM 注册。 将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 或 false 后 (初始在 HoloLens 2 上设置) 值，即使重新闪烁、OS 更新等，该值仍保留在设备上。 

在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 后，OOBE 将无限期等待 Autopilot 配置文件在网络连接后成功下载并应用。 

当 TenantLockdown CSP 的 RequireNetworkInOOBE 节点在 HoloLens 2 设置为 true 后，OOBE 中将禁止以下操作： 
- 使用运行时预配创建本地用户 
- 通过Azure AD执行联接操作 
- 选择在 OOBE 体验中拥有设备的人 

#### <a name="how-to-set-this-using-intune"></a>如何使用 Intune 设置此设置？ 
1. 创建自定义 OMA URI 设备配置文件，并指定 RequireNetworkInOOBE 节点的 true，如下所示。
OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 OMA-URI 设置锁定](images/hololens-tenant-lockdown.png)

1. 创建一个组，并将设备配置文件分配给该设备组。 

1. 使HoloLens 2在上一步中创建的组的设备成员，并触发同步。  

在 Intune 门户中验证设备配置是否已成功应用。 此设备配置成功应用于 HoloLens 2后，TenantLockdown 的效果将处于活动状态。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>如何使用 Intune 在 HoloLens 2上取消设置 TenantLockdown 的 RequireNetworkInOOBE？ 
1. 从HoloLens 2之前为其分配了设备配置的设备组中删除该配置。 

1. 创建自定义基于 OMA URI 的设备配置文件，并指定 RequireNetworkInOOBE 的 false，如下所示。 OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 Intune 中的 OMA URI 将 RequireNetworkInOOBE 设置为 false 的屏幕截图](images/hololens-tenant-lockdown-false.png)

1. 创建一个组，并将设备配置文件分配给该设备组。 

1. 使HoloLens 2在上一步中创建的组的设备成员，并触发同步。

在 Intune 门户中验证是否已成功应用设备配置。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的效果将处于非活动状态。 

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>如果 TenantLockdown 设置为 true 后在 HoloLens 上未分配 Autopilot 配置文件，则在 OOBE 期间将发生什么情况？ 
OOBE 会无限期等待 Autopilot 配置文件下载并显示以下对话框。 若要删除 TenantLockdown 的效果，必须首先使用 Autopilot 向设备注册其原始租户，并且必须按照上一步骤中所述取消设置 TenantLockdown CSP 引入的限制。 

![设备上强制实施策略的设备内视图。](images/hololens-autopilot-lockdown.png)

此信息现在可在 [TENANTLOCKDOWN CSP 和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)下的 Autopilot 的其余部分找到。

### <a name="global-assigned-access--kiosk-mode"></a>全局分配的访问–展台模式
- 通过启用在系统级别应用展台模式的新展台方法，降低了展台的标识管理。

这项新功能可让 IT 管理员为多个 app 展台模式（在系统级上适用）配置一个 HoloLens 2 设备，该模式与系统上的任何标识都无关联，并且适用于登录到该设备的所有用户。 有关此新功能的详细信息，请参阅 [HoloLens 全局分配的访问展台](hololens-global-assigned-access-kiosk.md)。

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

早于在应用展台模式时遇到故障，HoloLens 用于显示 "开始" 菜单中的所有应用程序。 现在，在 Windows Holographic 版本 20H2 中，如果出现故障，开始菜单中不会显示任何应用，如下所示： 

![当展台模式发生故障时，其外观的图像。](images/hololens-kiosk-failure-behavior.png )

### <a name="hololens-policies"></a>HoloLens 策略
- 专为 HoloLens 创建的用于管理设备的设备管理选项。 

为 Windows Holographic 版本 20H2 上的HoloLens 2设备创建了新的混合现实策略。 新的可控制设置包括：设置亮度、设置音量、禁用混合现实捕获中的音频录制、设置收集诊断的时间和 AAD 组成员身份缓存。  

| 新的 HoloLens 策略                                | 说明                                                                               | 注释                                                                |
|----------------------------------------------------|-------------------------------------------------------------------------------------------|----------------------------------------------------------------------|
| MixedReality\BrightnessButtonDisabled              | 允许禁用亮度按钮，以便按它不会更改亮度。       | 1 是，0 (默认)                                                 |
| MixedReality\VolumeButtonDisabled                  | 允许禁用音量按钮，以便按它不会更改音量。               | 1 是，0 (默认)                                                 |
| MixedReality\MicrophoneDisabled                    | 禁用麦克风，因此无法对麦克风进行音频HoloLens 2。                      | 1 是，0 (默认)                                                 |
| MixedReality\FallbackDiagnostics                   | 控制何时可以收集诊断日志的行为。                               | 0 已禁用，1 为设备所有者启用，2 为默认 (启用)  |
| MixedReality\HeadTrackingMode                      | 保留供将来使用。                                                                  |                                                                      |
| MixedReality\AADGroupMembershipCacheValidityInDays | 控制将组成员身份缓存 Azure AD 多少天用于面向 Azure AD 组的展台。 | 请参阅下文。                                                           |

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>缓存 Azure AD 脱机展台的组成员身份
- 已启用将脱机展台用于 AAD 组，最多60天。

此策略控制允许使用 Azure AD 组成员身份缓存来指定已登录用户 Azure AD 组的指定访问配置的天数。 一旦将此策略值设置为大于0的值，则不使用缓存。  

名称： AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小值为0天  
最大-60 天 

正确使用此策略的步骤： 
1. 为展台 Azure AD 组创建设备配置文件，并将其分配给 HoloLens 设备 (s) 。 
1. 创建基于自定义 OMA URI 的设备配置，该配置将此策略值设置为所需的天数 (> 0) 并将其分配给 HoloLens 设备 () 。 
    1. 应在 OMA-URI 文本框中输入 URI 值作为/Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays。
    1. 该值可以介于最小值/最大允许值之间。
1. 注册 HoloLens 设备，并验证这两项配置是否适用于设备。 
1. 当 internet 可用时，让 Azure AD 用户1登录，一旦用户登录并 Azure AD 组成员身份已成功确认，就会创建缓存。 
1. 现在 Azure AD 用户1可以使 HoloLens 脱机并将其用于展台模式，只要策略值允许 X 天。 
1. 对于任何其他 Azure AD 用户 N，可以重复执行步骤4和步骤5。以下是任何 Azure AD 用户都必须使用 Internet 登录设备，因此至少可以确定它们是展台配置所针对的 Azure AD 组的成员。 
 
> [!NOTE]
> 直到 Azure AD 执行步骤4后，才会在 "断开连接" 环境中遇到失败行为。 

### <a name="new-device-restriction-policies-for-hololens-2"></a>HoloLens 2 的新设备限制策略
- 允许用户管理特定的设备管理策略，例如阻止添加或删除预配包。

新启用的策略，允许对设备HoloLens 2选项。 
- [AllowAddProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowaddprovisioningpackage)
- [AllowRemoveProvisioningPackage](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-allowremoveprovisioningpackage) 
- [ConfigureTimeZone](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-timelanguagesettings#timelanguagesettings-configuretimezone)
- [RemoteLock](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp)

AllowAddProvisioningPackage 和 AllowRemoveProvisioningPackage 的这两个新措施将添加到 [通用设备限制](hololens-common-device-restrictions.md)。

> [!NOTE]
> 对于 RemoteLock，HoloLens 将仅支持 ./Vendor/MSFT/RemoteLock/Lock 配置。 [](https://docs.microsoft.com/windows/client-management/mdm/remotelock-csp) 不支持处理 PIN 的配置，例如重置和恢复。

### <a name="new-power-policies-for-hololens-2"></a>新的电源策略HoloLens 2
- 更多选项，适用于 HoloLens 通过电源策略休眠或锁定的时间。 

这些新添加的策略允许管理员控制电源状态，例如空闲超时。 若要详细了解每个策略，请单击该策略的链接。

|     策略文档链接                |     注释                                                                                                                                       |
|----------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|     [DisplayOffTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutonbattery)               |     在 Windows 配置设计器中使用的示例值，即  `<enabled/><data   id="EnterVideoDCPowerDownTimeOut" value="100"/>`     |
|     [DisplayOffTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-displayofftimeoutpluggedin)               |     在 Windows 配置设计器中使用的示例值，即  `<enabled/><data   id="EnterVideoACPowerDownTimeOut" value="100"/>`     |
|     [EnergySaverBatteryThresholdOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdonbattery)     |  在 Windows 配置设计器中使用的示例值，即 100                                                                             |
|     [EnergySaverBatteryThresholdPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-energysaverbatterythresholdpluggedin)     |     在 Windows 配置设计器中使用的示例值，即 100                                                                          |
|     [StandbyTimeoutOnBattery](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutonbattery)                  |     要在 Windows 配置设计器中使用的示例值，即   `<enabled/><data   id="EnterDCStandbyTimeOut" value="100"/>`          |
|     [StandbyTimeoutPluggedIn](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power#power-standbytimeoutpluggedin)                  |     要在 Windows 配置设计器中使用的示例值，即  `<enabled/><data   id="EnterACStandbyTimeOut" value="100"/>`           |

这两个适用于 DisplayOffTimeoutOnBattery 和 DisplayOffTimeoutPluggedIn 的新策略将添加到 [常见的设备限制](hololens-common-device-restrictions.md)中。

> [!NOTE]
> 若要在 HoloLens 2 上保持一致的体验，请确保 DisplayOffTimeoutOnBattery 和 StandbyTimeoutOnBattery 的值都设置为相同的值。 同样适用于 DisplayOffTimeoutPluggedIn 和 StandbyTimeoutPluggedIn。 有关新式备用的详细信息，请参阅 [显示、睡眠和休眠空闲计时器](https://docs.microsoft.com/windows-hardware/design/device-experiences/display--sleep--and-hibernate-idle-timers) 。

### <a name="newly-enabled-update-policies-for-hololens"></a>针对 HoloLens 的新启用的更新策略
- 安装更新或禁用 "暂停更新" 按钮以确保更新的更多选项。

以下更新策略现已在 HoloLens 2 设备上启用：
-   [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)
-   [Update/ActiveHoursMaxRange](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursmaxrange)
-   [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)
-   [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)

有关这些更新策略以及如何使用这些策略的详细信息，请参阅 [管理 hololens 更新](hololens-updates.md)。

### <a name="enabled-settings-page-visibility-for-hololens-2"></a>已启用 HoloLens 2 的设置页面可见性
- "设置" 应用中的 UI 控件增加，这可能会使用户感到困惑，以显示有限的页面。

现在，我们已启用了一个策略，该策略允许 IT 管理员阻止显示或访问 "系统设置" 应用中的特定页面，或为除指定的页面之外的所有页面执行此操作。 若要了解如何完全自定义此功能，请单击下面的链接。

- [PageVisibilityList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist)

若要了解可以在 HoloLens 2 上自定义的页面设置，请访问我们的 [设置 uri 页](settings-uri-list.md)。 
 
![在 "设置" 应用中修改的活动小时的屏幕截图](images/hololens-page-visibility-list.jpg)

### <a name="research-mode"></a>研究模式
在研究模式下，HoloLens 2成为计算机视觉研究的重要工具。 与以前的版本相比，HoloLens 2研究模式具有以下优点：
-   除了在 HoloLens (第一代) 研究模式下公开的传感器外，我们现在提供 IMU 传感器访问，包括加速计、陀螺仪和磁力计。
-   HoloLens 2提供了可以与研究模式一起使用的新功能。 具体而言，可以访问可交付更丰富试验集的表达式手部跟踪和眼动跟踪 API。

研究人员现在可以选择在 HoloLens 设备上启用研究模式，以访问所有这些面向外部的原始图像传感器流。 研究模式HoloLens 2提供对加速计、陀螺仪和磁力计读数的访问。 为了保护用户的隐私，无法通过研究模式使用原始眼动跟踪相机图像，但可以通过现有 API 获得眼睛凝视方向。

有关更多 [技术详细信息，请查看](https://docs.microsoft.com/windows/mixed-reality/research-mode) 研究模式文档。

### <a name="recording-length-increased"></a>录制长度增加
根据客户反馈，我们增加了混合现实捕获 [的录制长度](holographic-photos-and-videos.md)。 默认情况下，混合现实捕获将不再限制为 5 分钟，而是根据可用磁盘空间计算最大录制长度。 设备将基于可用磁盘空间估计最大视频录制持续时间，最多占总磁盘空间的 80%。

> [!NOTE]
> 如果发生下列情况之一 (HoloLens) 5 分钟：
> - 估计的最大录制持续时间小于默认的 5 分钟。
> - 可用磁盘空间小于总磁盘空间的 20%。

可以在全息照片和视频文档中 [找到完整](holographic-photos-and-videos.md#maximum-recording-length) 要求。 

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：
- OOBE 中的更多屏幕现在以深色模式显示。
- 了解更多内容应联机指向最新的隐私声明。
- 解决了用户无法通过设置包预配 VPN 配置文件的问题。
- 修复了 VPN 连接的代理配置问题。
- 已更新策略以禁用通过 MDM for NCM for AllowUsbConnection 的 USB 函数的枚举。
- 解决了在将设备设置为 [单应用展台](hololens-kiosk.md)时，会阻止 HoloLens 设备在文件资源管理器中显示在文件资源管理器中的问题， (MTP) 。 请注意，一般) 中的 MTP (和 USB 连接仍可使用 [AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 策略进行禁用。
- 修复了 "开始" 菜单中的图标在展台模式下正确缩放的问题。
- 修复了由于 HTTP 缓存干扰以展台模式为目标 Azure AD 组的问题。
- 修复了在使用预配包启用开发人员模式后，用户无法使用 "取消" 按钮的问题，除非他们禁用并重新启用了开发人员模式。

## <a name="windows-holographic-version-1903---november-2020-update"></a>Windows 全息，版本 1903-2020 更新
- 生成18362.1085

这一月度质量更新不包含任何显著的更改，我们建议你试用最新的功能版本 Windows 全息版20H2。

## <a name="windows-holographic-version-2004---october-2020-update"></a>Windows 全息，版本 2004-2020 更新
- 生成19041.1124
 
更新中的改进和修复：

- 删除导致运行时系统错误的不必要的检查。

## <a name="windows-holographic-version-1903---october-2020-update"></a>Windows 全息，版本 1903-2020 更新
- 生成18362.1081

这一月度质量更新不包含任何显著的更改，我们建议你试用最新版本的 Windows 全息2004版。

## <a name="windows-holographic-version-2004---september-2020-update"></a>Windows 全息，版本 2004-2020 更新
- 内部版本 19041.1117

更新中的改进和修复：

- 解决了当 appxmanifest Visual Studio SupportsMultipleInstances="true"时阻止用户调试应用程序的问题。
- 此版本包括 NCSI 代理检测修补程序，用于解决通过网络代理进行 Internet 检测失败的问题。 NCSI 可以使用计算机代理和按配置文件代理进行 Internet 连接检测。 NCSI 将在未来版本中支持每用户代理。
- 在大多数Windows Mixed Reality，当用户的头部处于向前的中性位置时，向前向向量与地面并行。 但是，早期版本的 HoloLens 2使矢量与显示面板垂直，而显示面板相对于理想方向向下倾斜几度。 较新版本的 HoloLens 2更正了此错误，以确保窗体因素之间的语义一致性。
- 改进了手部跟踪可靠度，这导致特定方案中的跟踪损失减少。
- 此版本包含一个修补程序，用于提高音频时间戳质量，这可能会导致视频捕获问题。

## <a name="windows-holographic-version-1903---september-2020-update"></a>Windows Holographic 版本 1903 - 2020 年 9 月更新
- 内部版本 18362.1079

更新中的改进和修复：

- 在大多数Windows Mixed Reality，当用户的头部处于向前的中性位置时，向前向向量与地面并行。 但是，早期版本的 HoloLens 2使矢量与显示面板垂直，而显示面板相对于理想方向向下倾斜几度。 较新版本的 HoloLens 2更正了此错误，以确保窗体因素之间的语义一致性。
- 改进了手部跟踪可靠度，这导致特定方案中的跟踪损失减少。

## <a name="windows-holographic-version-2004---august-2020-update"></a>Windows Holographic 版本 2004 - 2020 年 8 月更新
- 内部版本 19041.1113

更新中的改进和修复：

- "设置" 应用将不再跟随用户进入 Iris 注册或眼睛跟踪校准体验。
- 修复了一个 bug，该 bug 在用于重命名设备并执行其他操作 (例如连接到网络) 时在设备重启后执行其他操作（例如，连接到网络）的情况下应用设置包。
- 修改了初始设备设置流程的配色方案，以提高视觉质量。

## <a name="windows-holographic-version-1903---august-2020-update"></a>Windows 全息，版本 1903-8 2020 月版更新
- 生成18362.1074

这一月度质量更新不包含任何显著的更改，我们建议你试用最新版本的 Windows 全息2004版。

## <a name="windows-holographic-version-2004---july-2020-update"></a>Windows 全息，版本 2004-2020 更新
- 生成19041.1109

更新中的改进和修复：

- 现在，开发人员可以选择启用还是禁用设备门户要求安全连接。
- 操作系统更新后，针对应用程序启动的可靠性得到了提高。
- 更改了默认收件箱亮度到100%。
- 解决了在 HoloLens 2 上 Windows 设备门户的 HTTPS 转发问题。

## <a name="windows-holographic-version-1903---july-2020-update"></a>Windows 全息，版本 1903-2020 更新
- 生成18362.1071

更新中的改进和修复：

- 修复了一个问题，该问题可能导致在跟踪丢失或执行跟踪时，无法在 Unity 应用程序中消失。
- 修复了在某些设备上使用具有硬件加速功能的 HoloLens 模拟器时，专用的 HoloLens 应用程序故障回复到 shell 的问题。
- 解决了在 HoloLens 2 上 Windows 设备门户的 HTTPS 转发问题。

## <a name="windows-holographic-version-2004---june-2020-update"></a>Windows Holographic 版本 2004 - 2020 年 6 月更新
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
- 通过证书设备门户访问Wi-Fi，Web 浏览器可能会由于证书无效而阻止对 的访问。 即使设备证书以前受信任，浏览器也可能报告"ERR_SSL_PROTOCOL_ERROR"等错误。 在这种情况下，无法继续设备门户，因为无法忽略安全警告。 此更新解决了问题。 如果先前已在电脑上下载并信任设备证书以删除浏览器安全警告，并且发生 SSL 错误，则必须下载新证书并将其信任，以解决浏览器安全警告。
- 支持创建可通过使用 .MSIX 包安装应用的运行时预配包。
- 添加了 **设置**  >  **系统**  >  **全息影像** 中的设置，该设置允许用户在设备关闭时自动删除混合现实主页中的所有全息影像。
- 修复了一个问题，该问题导致在 HoloLens 模拟器中将更改像素格式的 HoloLens 应用程序呈现为黑色。
- 修复了 Iris 登录期间导致崩溃的 bug。
- 修复了有关现有应用的重复存储下载的问题。
- 修复了一个 bug，以防止沉浸式应用重复打开 Microsoft Edge。
- 修复了从1903版更新后初始启动时启动照片应用的问题。
- 提高了性能和可靠性。

## <a name="windows-holographic-version-1903---june-2020-update"></a>Windows 全息，版本 1903-2020 更新
- 生成18362.1064

更新中的改进和修复：

- 如果未指定自定义的 MRC 录像机，则为某些属性提供新的默认值。
  - 在 *MRC 视频效果*：
    - PreferredHologramPerspective (1 PhotoVideoCamera) 
    - GlobalOpacityCoefficient (0.9 (HoloLens) 1.0 (沉浸式耳机) ) 
  - 在 " *MRC 音频" 效果* 上：
    - LoopbackGain (Windows 设备门户中混合现实捕获页面上当前的 "应用音频增益" 值) 
    - MicrophoneGain (Windows 设备门户中混合现实捕获页面上的当前 "Mic 音频增益" 值) 
- 对于 Unity 应用程序，通常禁用 HolographicSpace.UserPresence API。 此行为可避免在视器翻转时导致某些应用暂停的问题，即使启用了在后台运行的设置。 现已为 Unity 版本 2018.4.18 及更高版本以及 2019.3.4 及更高版本启用 API。
- 修复了导致 HoloLens 应用更改其像素格式以在 HoloLens 仿真器中呈现黑色的问题。
- 修复了从 1903 版本更新后在初始启动中启动照片应用的问题。

## <a name="windows-holographic-version-2004"></a>Windows Holographic 版本 2004  
- 内部版本 - 19041.1103

HoloLens 2、Windows Holographic 版本 *2004 的 2020* 年 5 月主要软件更新包含一系列令人心动的新功能，例如支持 Windows Autopilot、应用深色模式、USB 以太网支持 5G/LTS 热点等。 若要更新到最新版本，请打开"设置"应用，转到"&    **安全性"，** 然后选择"检查 **更新"**   按钮。 

|             功能                              |          说明                                                                                              |
|--------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
|       Windows Autopilot                          |          使用 Windows AutoPilot 预配置并无缝设置用于生产的新设备                 |
|       FIDO 2 支持                             |          支持 FIDO2 安全密钥，为共享设备启用快速且安全的身份验证            |
|       改进了预配                      |          将预配包从 USB 驱动器无缝应用到 HoloLens                              |
|       应用程序安装状态                 |          检查已通过 MDM 将应用的"设置"应用中的HoloLens 2状态               |
|       配置服务提供商 (使用)    |          添加了新的配置服务提供程序，以增强管理员控制功能                 |
|       USB 5G/USB 支持                       |          扩展的 USB 以太网功能支持 5G/LTS                                    |
|       深色应用模式                              |          适用于支持深色和浅色模式的应用的深色应用模式，从而改善了查看体验        |
|       语音命令                             |          支持其他系统语音命令，以控制 HoloLens 免提                           |
|       手动跟踪改进                 |          手动跟踪改进使按钮和2D 石板交互更准确                        |
|       质量改进和修复                 |          跨平台的各种系统性能和可靠性改进                            |

### <a name="support-for-windows-autopilot"></a>支持 Windows Autopilot

Windows Autopilot for HoloLens 2 允许设备销售渠道预先注册到 Intune 租户中。 设备到达后，它们就可以自行部署为租户下的共享设备。 若要利用自部署，设备必须在安装过程中的第一个屏幕上通过使用 USB 到以太网连接到网络。

用户启动 Autopilot 自行部署过程后，此过程将完成以下步骤：

1. 将设备加入到 Azure Active Directory (Azure AD) 。
1. 使用 Azure AD 在 Microsoft Intune (或其他 MDM 服务) 中注册设备。
1. 下载设备目标策略、证书和网络配置文件。
1. 设置设备。
1. 向用户显示登录屏幕。

有关详细信息，请参阅 [Windows Autopilot For HoloLens 2 评估指南](https://docs.microsoft.com/hololens/hololens2-autopilot)。

*请联系你的帐户管理员立即加入 AutoPilot preview。即将开始交付 Autopilot 的设备。*

### <a name="fido2-security-key-support"></a>FIDO2 安全密钥支持

某些用户在工作或学校环境中与他人共享 HoloLens 设备。 因此，用户可以轻松地无需键入长用户名和密码，这一点很重要。 使用 Fast Identity Online (FIDO) ， (Azure AD租户中的) 无需输入用户名或密码即可无缝登录到 HoloLens。

FIDO2 安全密钥是基于标准的"不可加密"无密码身份验证方法，可以采用任何外形要求。 FIDO 是无密码身份验证的开放标准。 它允许用户和组织在没有用户名或密码的情况下登录到其资源。 而是使用内置于设备的外部安全密钥或平台密钥。

若要开始，请参阅 [启用无密码安全密钥登录](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)。

### <a name="improved-mdm-enrollment-via-provisioning-package"></a>通过预配包改进了 MDM 注册

预配包允许通过配置文件而不是 HoloLens 开箱即用体验来设置 HoloLens 配置。 以前，预配包必须复制到 HoloLens 内部内存中。 现在，它们可以位于 USB 驱动器上，以便更轻松地在多个 HoloLens 设备上重复使用，并且你可以并行预配设备。 预配包现在还支持在设备管理中注册字段，因此预配后无需手动设置。

试试看：

1. 将最新版本的 Windows 配置设计器从 Windows 应用商店下载到电脑上。
1. 选择 **"预配 HoloLens 设备**  >  **预配HoloLens 2设备"。**
2. 生成配置文件。 然后将创建的所有文件复制到 USB-C 存储设备。
3. 将 USB-C 设备插入任何全新闪烁的 HoloLens。 然后按 **音量关闭**  +  **电源** 按钮以应用预配包。

### <a name="line-of-business-application-install-status"></a>业务线应用程序安装状态

适用于业务线应用的 MDM 应用部署和管理对于 HoloLens 至关重要。 管理员和用户需要查看应用安装状态以进行审核和诊断。 在此版本中，我们在 **设置**  >  **帐户**  >  **访问工作或学校**  >  **单击你的帐户信息时添加了**  >  更多详细信息。

### <a name="additional-csps-and-policies"></a>其他 Csp 和策略

[ (CSP) 的配置服务提供程序](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference?redirectedfrom=MSDN)是一个用于读取、设置、修改或删除设备上的配置设置的接口。 在此版本中，我们添加了对更多策略的支持，以提高管理员对已部署的 HoloLens 设备的控制。 有关 HoloLens 支持的 Csp 列表，请参阅 [NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

本版本中的新主题：

**策略云解决方案提供商** 

策略配置服务提供程序使企业能够在 Windows 设备上配置策略。 在此版本中，我们为 HoloLens 添加了新策略，这里列出了这些策略。 若要了解详细信息，请参阅 [HoloLens 2 支持的策略 csp](https://docs.microsoft.com/windows/client-management/mdm/policies-supported-by-hololens2)。  

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

NetworkQoSPolicy 配置服务提供商使用 QoS 策略创建 (服务质量) 提供程序。 QoS 策略根据一组匹配的条件对网络流量执行一组操作。 有关详细信息，请参阅 [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)。

### <a name="expanded-usb-ethernet-support-for-5glte-tethered-devices"></a>扩展了对 5G/LTS 网络设备的 USB 以太网支持

添加了支持，使某些移动宽带设备（如 5G/Wi-Fi 手机和 Wi-Fi 热点）通过 USB HoloLens 2连接。 这些设备现在在网络设置 **中显示为** 另一个以太网连接。  (不支持需要外部驱动程序的移动宽带设备。) 此功能在 Wi-Fi 不可用且 Wi-Fi Tethering 性能不足时启用高带宽连接。 若要详细了解支持的 USB 设备，请参阅 [连接到蓝牙和 USB-C 设备](https://docs.microsoft.com/hololens/hololens-connect-devices)。  

### <a name="hand-tracking-improvements"></a>手部跟踪改进

此版本包括多项手动跟踪改进：

- **指向姿势稳定性：** 现在，当手指被手指遮挡时，系统可以抵御手指的滑动。 此更改提高了按下按钮、键入、滚动内容等时的准确性！ 
- **减少了意外的敲击：** 改进了对敲击手势的检测。 现在，在多种常见情况下（例如，将手放在一边时）中的意外激活更少。
- **用户交换机可靠性：** 现在，共享设备时，系统在更新手部大小时速度更快且更可靠。
- **减少手部窃取：** 改进了传感器视图超过两手的情况的处理。 如果多人在一起工作，现在跟踪手从用户"跳转"到场景中其他人手的可能性要低得多。
- **系统可靠性：** 修复了在设备负载较高时导致手部跟踪停止工作的问题。

### <a name="dark-mode"></a>深色模式

许多 Windows 应用现在支持深色和浅色模式。 HoloLens 2用户可以为支持两者的应用选择默认模式。 更新之后，默认应用模式为 "深色"，但你可以轻松地更改此设置：导航到 "**设置**" "  >  **系统**  >  **颜色**" "  >  **选择默认的应用模式**。 

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

![深色模式窗口平铺](images/DarkMode.jpg)

### <a name="system-voice-commands"></a>系统语音命令

你现在可以对设备上的任何应用使用语音命令。 有关详细信息，请参阅 [使用语音操作 HoloLens](https://docs.microsoft.com/hololens/hololens-cortana)。 另请参阅 [HoloLens 2 支持的语言](https://docs.microsoft.com/hololens/hololens2-language-support)。  

### <a name="cortana-updates"></a>Cortana 更新

更新后的应用程序可与 Microsoft 365 集成，以帮助你在设备上进行更多的操作， (当前仅 US-English) 。 在 HoloLens 2 上，Cortana 不再支持某些特定于设备的命令，例如调整音量或重新启动。 新的系统语音命令现在支持这些选项。 在 [博客](https://blogs.windows.com/windowsexperience/2020/02/28/cortana-in-the-upcoming-windows-10-release-focused-on-your-productivity-with-enhanced-security-and-privacy/)中了解有关新 Cortana 应用的详细信息。

### <a name="quality-improvements-and-fixes"></a>质量改进和修复

更新中也有改进和修复：  
- 引入了活动的显示校准系统。 此功能可改善全息影像的稳定性和对齐方式。 当你从一侧到另一侧时，它们现在就会保持不变。
- 修复了一个 bug，在这种情况下，Wi-Fi 流式传输到 HoloLens 会定期中断。 如果应用程序指示它需要低延迟流式处理，请通过调用 [SetSocketMediaStreamingMode 函数](https://docs.microsoft.com/windows/win32/api/socketapi/nf-socketapi-setsocketmediastreamingmode)来实现修复。
- 修复了在研究模式下流式传输期间发生的设备挂起。
- 修复了以下 bug：在某些情况下，恢复会话时不会在登录屏幕上显示正确的用户。
- 修复了用户无法通过"设置"导出 MDM 日志 **的问题**。
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
- 问题要求在启动设备后启动 Cortana 应用，以使用"你好 Cortana"语音激活。 如果从 18362 版本更新，则还可以在"启动"中看到以前版本的 Cortana 应用的第二个应用 **磁贴**。

## <a name="windows-holographic-version-1903---may-2020-update"></a>Windows Holographic 版本 1903 - 2020 年 5 月更新 
- 内部版本 18362.1061

此每月质量更新不包含任何值得注意的更改，因为团队正在处理 Windows Holographic 版本 2004 May Update，如前文所述。

## <a name="windows-holographic-version-1903---april-2020-update"></a>Windows Holographic 版本 1903 - 2020 年 4 月更新
- 内部版本 18362.1059

**受支持应用的深色模式** 

许多 Windows 应用都支持深色和浅色模式。 HoloLens 2 客户现在可以为支持两种配色方案的应用选择默认模式。 根据客户反馈，我们将默认的应用模式设置为 "深色"，但你随时可以轻松地更改此设置：导航到 " **设置" > 系统 > 颜色** "以找到 **" 选择你的默认应用模式 "。**

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

**更新中也有改进和修复：** 
- 确保在混合现实捕获中包含 shell 重叠。
- Unreal 开发人员现在可以在设备门户中使用3D 视图页面来测试和调试应用程序。
- 当使用 *HolographicDepthReprojectionMethod DepthReprojection* 算法时，混合现实捕获中改进了全息图稳定性。
- 修复了32位 ARM 应用上的 "WinRT IStreamSocketListener API 类未注册" 错误。

## <a name="windows-holographic-version-1903---march-2020-update"></a>Windows 全息，版本 1903-2020 更新 
- 生成18362.1056

更新中的改进和修复：

- 当使用 *HolographicDepthReprojectionMethod AutoPlanar* 算法时，混合现实捕获中改进了全息图稳定性。
- 确保连接到深度 MF 示例的坐标系与公共文档一致。
- 通过使客户能够通过设备门户粘贴大量文本，提高开发人员的工作效率。

## <a name="windows-holographic-version-1903---february-2020-update"></a>Windows 全息，版本 1903-2020 更新 
- 生成18362.1053

更新中的改进和修复：

- 暂时禁用了 Unity 应用程序的 HolographicSpace. UserPresence API。 此更改可避免在视器翻转时导致某些应用暂停的问题，即使启用了"在后台运行"设置。
- 修复了手动跟踪导致的随机 HUP 崩溃，其中用户注意到 UI 冻结，然后在几秒钟后返回到 shell。
- 改进了手部跟踪，以便当你用手指触摸时，该手指的上半部分不太可能意外地卷曲。
- 改进了头部跟踪、空间映射和其他运行时的可靠性。

## <a name="windows-holographic-version-1903---january-2020-update"></a>Windows Holographic 版本 1903 - 2020 年 1 月更新 
- 内部版本 18362.1043
 
更新中的改进和修复：

- 改进了使用专用仿真器时独占应用HoloLens 2的稳定性。

## <a name="windows-holographic-version-1903---december-2019-update"></a>Windows Holographic 版本 1903 - 2019 年 12 月更新 
- 内部版本 18362.1042

更新中的改进和修复：

- 引入了 LSR (的最后) 重现。 改进了全息影像的视觉呈现，通过更准确地计算其深度来显示更稳定、更简洁。 如果应用没有正确设置全息影像的深度，则此症状在此更新后会更加明显。
- 修复了独占应用的稳定性和独占应用之间的导航。
- 解决了混合现实捕获在设备处于待机状态数天后无法录制视频的问题。
- 提高了全息影像稳定性。

## <a name="windows-holographic-version-1903---november-2019-update"></a>Windows Holographic 版本 1903 - 2019 年 11 月更新 
- 内部版本 18362.1039

更新中的改进和修复：

- 修复了在初始安装过程中用于 en CA 和 en-us 的 **选择** 语音命令的功能。
- 提高了在最新 Unity 和混合现实工具包中放置的对象的视觉质量 (MRTK) 版本。
- 修复了在打开 "开始" 菜单并关闭之前，内置应用程序在启动时停滞处于暂停状态的问题。
- 针对 HoloLens 2 和模拟器的 OpenXR 运行时一致性修复和改进。
