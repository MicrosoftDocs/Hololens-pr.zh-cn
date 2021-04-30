---
title: 适用于 Microsoft HoloLens 的 Insider Preview
description: 了解如何开始体验内部版本，并为更新下一个主流的操作系统更新提供有价值的反馈。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: ebd3992458daa94726e73742b1fba4d7fa97a48b
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308447"
---
# <a name="insider-preview-for-microsoft-hololens"></a>适用于 Microsoft HoloLens 的 Insider Preview

欢迎使用适用于 HoloLens 的最新 Insider preview 版本！ 简单易用 [，并为](hololens-insider.md#start-receiving-insider-builds) HoloLens 的下一个主要操作系统更新提供有价值的反馈。

## <a name="windows-insider-release-notes"></a>Windows 有问必答发行说明

我们非常高兴地开始向 Windows 预览体验人员试验新功能。 新的内部版本将试验到用于最新更新的开发渠道。 我们将继续更新此页面，因为我们将更多的功能和更新添加到我们的 Windows 预览体验内部版本。  令人兴奋并准备好将这些更新混合到您的现实中。

此功能更新包含两个目标用户的功能。 最终用户可以在设备上使用的所有功能，以及可由 IT 管理员配置的新设备管理选项。 下表详细说明了能够使用每个新功能的受众。 如果你是 IT 管理员，请查看我们的 [It 管理员更新清单](#it-admin---update-checklist)

> [!IMPORTANT]
> 如果你以前在展台上使用了 "设置" 应用或 "Microsoft Edge" 应用，我们已将这些应用替换为使用不同应用 ID 的新应用。 我们强烈建议你在下面的 [展台模式下阅读新应用的新 AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 。 这将确保在展台中继续使用 "设置" 应用程序，或包括新的 Microsoft Edge 应用。

<br>

| 功能名称                                              | 简短说明                                                                      | 目标读者 | 在生成中提供 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|------|
| [新的 Microsoft Edge](#introducing-the-new-microsoft-edge) | 新的基于 Chromium 的 Microsoft Edge 现在适用于 HoloLens 2                         | 最终用户 | 20279.1006 |
| [WebXR 和360查看器](#webxr-and-360-viewer)             | 尝试沉浸式 web 体验和360视频播放                                           | 最终用户 | 20289.1000 |
| [新建设置应用](#new-settings-app)                     | 旧的设置应用被更新的版本替换为新功能和设置 | 最终用户 | 20279.1006 |
| [显示颜色校准](#display-color-calibration)   | 为 HoloLens 2 显示器选择备用颜色配置文件                                | 最终用户 | 20293.1000 |
| [默认应用选取器](#default-app-picker)                 | 选择应为每个文件或链接类型启动哪个应用                                      | 最终用户 | 20279.1006 |
| [按应用音量控制](#per-app-volume-control) |  独立于系统卷控制应用级别卷 | 最终用户 | 20293.1000 |
| [Office web 应用](#office-web-app)                         | "所有应用" 中现在列出了 Office web 应用的快捷方式                                   | 最终用户 | 20279.1006 |
| [刷到类型](#swipe-to-type)                           | 使用手指的笔尖在全息键盘上 "轻扫" 字词                        | 最终用户 | 20279.1006 |
| [入门的 Power menu](#power-menu-from-start) | 在 "开始" 菜单上，重新启动并关闭 HoloLens 设备 | 最终用户 | 20293.1000 |
| [登录屏幕上列出了多个用户](#multiple-users-listed-on-sign-in-screen) | 在登录屏幕上显示多个用户帐户 | 最终用户 | 20293.1000 |
| [USB-C 外部麦克风支持](#usb-c-external-microphone-support) | 为应用和/或远程协助使用 USB-C 麦克风。| 最终用户 | 20279.1006 |
| [网亭的访问者自动登录](#visitor-auto-logon-for-kiosks)                          | 启用对访问者帐户的自动登录以用于展台模式。                         | IT 管理员 | 20279.1006                 |
| [展台模式下新应用的新 AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | 用于新设置和边缘应用的 AUMIDs | IT 管理员 | 20279.1006 |
| [改善了展台模式故障处理](#kiosk-mode-behavior-changes-for-handling-of-failures) | 展台模式在空 "开始" 菜单之前查找全局分配的访问权限。 | IT 管理员 | 20279.1006 |
| [新 SettingsURIs 的页面设置可见性](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | 用于设置/PageVisibilityList 策略的20多个新 SettingsURIs | IT 管理员 | 20289.1000 |
| [配置回退诊断](#configuring-fallback-diagnostics-via-settings-app) | 在 "设置" 应用中设置回退诊断行为 | IT 管理员 | 20279.1006 |
| [与附近设备共享东西](#share-things-with-nearby-devices) | 共享从 HoloLens 到 PC 的文件或 Url | 全部 | 20279.1006 |
| [新操作系统更新疑难解答](#new-os-update-troubleshooter) | OS 更新设置中的新疑难解答 | IT 管理员 | 20279.1006 |
| [传递优化预览](#delivery-optimization-preview) | 减少从多个 HoloLens 设备下载的带宽消耗 | IT 管理员 | 20301.1000 |
| [更新中的改进和修复](#improvements-and-fixes-in-the-update) | 更新中的其他修补程序。 | 全部 | 20279.1006 |

### <a name="it-admin---update-checklist"></a>IT 管理员-更新清单

此清单可帮助你了解在此功能更新中添加的功能可能会影响当前设备管理配置的新项目，或者你可能希望开始使用的新功能。

#### <a name="updates-to-kiosk-mode"></a>展台模式更新

[**展台模式下新应用的新 AUMIDs**](#use-the-new-settings-and-edge-apps-in-kiosk-modes)

如果你以前在展台上使用了 "设置" 应用或 "Microsoft Edge" 应用，我们已将这些应用替换为使用不同应用 ID 的新应用。 我们强烈建议你在下面的 [展台模式下阅读新应用的新 AUMIDs](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 。 这将确保在展台中继续使用 "设置" 应用程序，或包括新的 Microsoft Edge 应用。

现在可以完成这些更改，并将其部署到所有设备，并允许在更新时获得更平稳的过渡效果。

[**网亭的访问者自动登录**](#visitor-auto-logon-for-kiosks)

现在，访问者可以自动登录到展台。 默认情况下，此行为是启用的，但可以被管理和禁用。

[**改善了展台模式故障处理**](#kiosk-mode-behavior-changes-for-handling-of-failures)

如果未成功确定登录 AAD 用户的 AAD 组成员身份，则会将全局展台配置用于 "开始" 菜单 (如果存在，则为 "开始" 菜单) 否则显示 "开始" 菜单。 尽管空 "开始" 菜单不是可以直接设置的配置，但如果您使用的是展台，则这种新的处理可能会告诉您的支持部门，因为这可能适用于您的配置，或者您可能想要对分配的访问配置进行新调整。

#### <a name="updates-to-page-settings-visibility"></a>页面设置可见性更新

[**新 SettingsURIs 的页面设置可见性**](hololens-insider.md#new-settingsuris-for-page-settings-visibility)

如果你当前正在使用 [页面设置可见性](settings-uri-list.md) ，则你可能希望对已允许或阻止的现有 uri 进行调整。

#### <a name="updates-for-your-wdac-policy"></a>适用于 WDAC 策略的更新

如果以前通过 WDAC 阻止 Microsoft Edge，则需要更新你的 WDAC 策略。 请 [查看以下](#using-wdac-to-block-new-microsoft-edge) 代码，并使用提供的示例代码。

#### <a name="enable-new-endpoints-for-edge"></a>启用边缘的新终结点

如果你的基础结构涉及配置网络终结点（例如代理或防火墙），请 [为新的 Microsoft Edge 应用启用这些新的终结点。](#managing-endpoints-for-the-new-microsoft-edge)

#### <a name="newly-configurable-items"></a>新的可配置项

- [配置回退诊断](#configuring-fallback-diagnostics-via-settings-app)
  - 你可以配置是否可以收集回退诊断。
- [与附近设备共享东西](#share-things-with-nearby-devices)
  - 您可以禁用新的邻近共享功能。
- [为新的 Microsoft Edge 配置策略设置](#configuring-policy-settings-for-the-new-microsoft-edge)
  - 查看适用于 Microsoft Edge 的新配置。

#### <a name="new-diagnostic-tool"></a>新的诊断工具

- [新操作系统更新疑难解答](#new-os-update-troubleshooter)
  - 收集与 OS 更新相关的日志

### <a name="introducing-the-new-microsoft-edge"></a>推出新的 Microsoft Edge

![将旧版 Microsoft Edge 徽标动画用于新的 Microsoft Edge 徽标](images/new-edge.gif)

新的 Microsoft Edge [采用 Chromium 开源项目](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) ，为客户提供更好的兼容性，并为 web 开发人员创建更少的网络碎片。

通过此内幕预览版，新的 Microsoft Edge 首次适用于 HoloLens 2 客户！ 尽管新的 Microsoft Edge 最终将取代 HoloLens 2 上的旧版 Microsoft Edge，但这两个浏览器当前均可供内部使用。 请通过新的 Microsoft Edge 中的 " **发送反馈** " 功能或通过 [反馈中心](hololens-feedback.md)与我们的团队共享反馈和 bug。

![新的 Microsoft Edge 屏幕截图](images/new-edge-ui.png)

#### <a name="launching-the-new-microsoft-edge"></a>启动新的 Microsoft Edge

有两个版本的 Microsoft Edge 可用于内部人员：新的 Microsoft Edge ![ 新的 Microsoft edge 图标 ](images/new_edge_logo.png) (用蓝色和绿色的漩涡图标表示，) 和传统的 microsoft edge (用白色的 "e" 图标) 表示。 新的 Microsoft Edge 固定到 "开始" 菜单，并将在你激活 web 链接时自动启动。 如果要还原为使用旧的 Microsoft Edge 作为默认 web 浏览器，请参阅以下说明以 [重置默认应用](#default-app-picker)。

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
> 至少有两个新的 Microsoft Edge 策略 *不* 能用于 HoloLens 2：
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### <a name="what-to-expect-from-the-new-microsoft-edge-on-hololens-2"></a>新 Microsoft Edge 在 HoloLens 2 上的预期情况

由于新的 Microsoft Edge 是具有新的 UWP 适配器层的本机 Win32 应用程序，允许它在仅支持 UWP 的设备（如 HoloLens 2）上运行，因此某些功能可能无法立即使用。 我们将在未来几个月内支持新方案和功能，因此请查看此空间以获取最新信息。

**预期工作情况和功能：**
- 首次运行体验，登录到配置文件，同步
- 网站应呈现并按预期方式工作
- 大多数浏览器功能 ("收藏夹"、"历史记录" 等 ) 应按预期方式工作
- 深色模式
- 将 web 应用安装到设备
- 安装扩展 (如果你使用的扩展不会在 HoloLens 2 上正常工作，请告知我们) 
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
- Wi-Fi 代理配置是面向单个 Wi-Fi 连接的代理策略，目前不能用于新的 Microsoft Edge。 我们正在积极地致力于在公共版本的操作系统更新之前解除阻止此问题。
- 为新的 Microsoft Edge 禁用了全息键盘中的放大镜预览。 我们希望在未来的更新中重新启用此功能，一旦放大倍数工作正常。
- 日语键盘上的两个字符在新的 Microsoft Edge 中不能按预期方式工作。 此问题已是根本原因，应尽快解决。
- Microsoft Store 应用中的 Web 链接可能不会启动浏览器
- 如果有另一个浏览器窗口处于打开和活动状态，则可以从错误的浏览器窗口播放音频。 通过关闭不应播放音频的其他活动窗口，可以解决此问题。
- 在 ["关注我" 模式下](hololens2-basic-usage.md#follow-me-stop-following)从浏览器窗口播放音频时，如果禁用 "关注我" 模式，则音频将继续播放。 可以通过在禁用 "关注我" 模式之前停止音频播放，或通过使用 **X** 按钮关闭窗口，来解决此问题。
- 与活动 Microsoft Edge windows 交互可能会导致其他2D 应用程序窗口意外停用。 您可以重新激活这些窗口，方法是再次与它们进行交互。
- 除了使用 web 链接或文件链接) 的内容创建的新选项卡外，从其他应用程序或 Pdf 等某些类型的文档打开 web 链接可能会导致第二个空白选项卡在浏览器中打开 (。 可以通过关闭 "其他空白" 选项卡来解决此问题。

#### <a name="microsoft-edge-insider-channels"></a>Microsoft Edge 预览体验渠道

Microsoft Edge 团队向边缘有问必答社区提供三个预览频道： Beta 版、开发人员版和 "未之限"。 安装预览频道不会卸载 HoloLens 2 上的 Microsoft Edge 的发行版，并且可以同时安装多个版本。 

若要深入了解边缘有问必答社区，请访问 [Microsoft Edge 有问必答主页](https://www.microsoftedgeinsider.com) 。 若要详细了解不同的边缘有问必答通道并开始，请访问 [边缘有问必答下载页面](https://www.microsoftedgeinsider.com/download)。

有几种方法可用于将 Microsoft Edge 有问必答通道安装到 HoloLens 2：

**直接安装在设备上 (当前仅适用于非托管设备)**
  1. 在 HoloLens 2 上，请访问 [边缘有问必答下载页面](https://www.microsoftedgeinsider.com/download)。
  1. 选择要安装的边缘有问必答频道的 "下载" " **HoloLens 2** " 按钮。
  1. 使用文件资源管理器) ，从边缘下载队列或设备的 "下载" 文件夹启动下载的 .msix 文件 (。
  1. 将启动[应用安装程序](app-deploy-app-installer.md)。
  1. 选择“安装”按钮  。
  1. 成功安装后，你会在 "开始" 菜单的 " **所有应用** " 列表中找到 Microsoft Edge Beta、开发或工作方式为单独的条目。

**通过电脑安装 Windows 设备门户 (需要在 HoloLens 2 上启用 [开发人员模式](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal))**
  1. 在你的电脑上，访问 [边缘有问必答下载页面](https://www.microsoftedgeinsider.com/download)。
  1. 选择要安装的边缘有问必答频道的 "下载 Windows 10" 按钮旁的 **下拉箭头按钮** 。
  1. 在下拉菜单中选择 " **HoloLens 2** "。
  1. 将 .msix 文件保存到你的电脑的 "下载" 文件夹中 (或可轻松找到) 的其他文件夹。
  1. 在电脑上使用 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 安装 HoloLens 2 上下载的 .msix 文件。
  1. 成功安装后，你会在 "开始" 菜单的 " **所有应用** " 列表中找到 Microsoft Edge Beta、开发或工作方式为单独的条目。

> [!NOTE]
> 在适用于 HoloLens 2 的 Windows 内幕预览版期间，你设备上的 Microsoft Edge 版本可能比某些 (或 Microsoft Edge 内部通道的所有) 中的 Microsoft Edge 版本都高。 这是为了确保专门面向 HoloLens 2 上的 web 浏览器的新功能和修复程序尽快进入我们的 Windows 预览体验。 不久后，在公开发布下一 Windows 更新后，Microsoft Edge 预览体验版频道将超过 HoloLens 2 的 Microsoft Edge 版本。

#### <a name="using-wdac-to-block-new-microsoft-edge"></a>使用 WDAC 阻止新的 Microsoft Edge

对于希望更新其 [WDAC 策略](windows-defender-application-control-wdac.md) 以阻止新的 Microsoft Edge 应用的 IT 管理员，需要将以下项添加到策略中。

``` <Deny ID="ID_DENY_D_3_0" FriendlyName="C:\Data\Programs FileRule" PackageVersion="65535.65535.65535.65535" FileName="msedge.exe" /> ```

#### <a name="managing-endpoints-for-the-new-microsoft-edge"></a>为新的 Microsoft Edge 管理端点

出于考虑，某些环境可能具有网络限制。 若要确保具有新边缘的流畅体验，请 [启用这些 Microsoft 终结点。](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)

阅读有关当前可用的 [HoloLens 终结点](hololens-offline.md)的详细信息。

### <a name="webxr-and-360-viewer"></a>WebXR 和360查看器

*已在 Windows 预览体验内部版本20289.1000 中添加*

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
- 退出 WebXR 或360查看器体验时，可能需要30秒或更长时间才能在混合现实主页中再次显示全息影像。
- 360之外的网站中的视频不会按预期方式工作。
- 当前在 HoloLens 2 上的360查看器中禁用了字幕。 我们计划在未来的更新中启用此功能。
- 在360查看器中暂停视频会使视频不会呈现 (但选择 "播放" 按钮会正确地恢复播放) 。
- 360查看器中的 "下一个视频" 按钮当前无法使用。
- 可以采用沉浸式 "电影院" 模式播放2D 视频，但帧速率可能小于 30 fps。

#### <a name="providing-feedback-on-webxr-and-360-viewer"></a>在 WebXR 和360查看器中提供反馈

请通过新的 Microsoft Edge 中的 " **发送反馈** " 功能与我们的团队共享反馈和 bug。

### <a name="new-settings-app"></a>新建设置应用

在此版本中，我们引入了新版本的 "设置" 应用。 新的 "设置" 应用程序包括以下方面的新功能和 HoloLens 2 的扩展设置：声音、电源 & 睡眠、网络 & Internet、应用、帐户、轻松访问等。

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
- 将删除以前放置的设置窗口 (请参阅上面) 上的 "注意"。
- 你不能再用设置应用重命名你的设备。 IT 管理员可以使用 [Windows Autopilot For HoloLens 2](https://docs.microsoft.com/hololens/hololens2-autopilot) 设备名称模板或 MDM [DevDetail CSP](https://docs.microsoft.com/windows/client-management/mdm/devdetail-csp) Ext/Microsoft/DNSComputerName 节点重命名设备。
- "以太网" 页将始终显示虚拟以太网设备 ( "UsbNcm" ) 。
- 新 Microsoft Edge 的电池使用情况可能不准确，因为它的性质是 UWP 适配器层所支持的 Win32 桌面应用程序 (不会立即) 任何修补程序。

### <a name="display-color-calibration"></a>显示颜色校准

*已在 Windows 预览体验内部版本20293.1000 中添加*

使用此新设置，可以为 HoloLens 2 显示器选择备用颜色配置文件。 这可以帮助显示更准确的颜色，尤其是在较低的显示亮度级别。 可以在 "设置" 应用的 "系统 > 校准" 页上找到 "显示颜色校准"。

> [!NOTE]
> 由于此设置将新的颜色配置文件保存到显示器固件，因此它是每个设备的设置， (并且每个用户帐户) 不唯一。

#### <a name="how-to-use-display-color-calibration"></a>如何使用显示颜色校准

1. 启动 " **设置** " 应用，并导航到 " **系统 > 校准**"。
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
> - 你可以根据需要从设置重新运行显示颜色校准
> - 如果设备上的任何人以前使用了更改颜色配置文件的设置，则最近更改的日期/时间将反映在 "设置" 页上
> - 重新运行 "显示颜色校准" 时，将突出显示以前保存的颜色配置文件，并且不会显示配置文件 0 (因为配置文件0表示显示的原始颜色配置文件) 
> - 如果要恢复到显示的原始颜色配置文件，可从 "设置" 页上 (参阅 [如何重置颜色配置文件](#how-to-reset-color-profile)) 

#### <a name="how-to-reset-color-profile"></a>如何重置颜色配置文件

如果不满意保存到 HoloLens 2 的自定义颜色配置文件，则可以还原设备的原始颜色配置文件：
1. 启动 " **设置** " 应用，并导航到 " **系统 > 校准**"。
1. 在 " **显示颜色校准**" 下，选择 " **重置为默认颜色配置文件** " 按钮。
1. 当对话框打开时，如果已准备好重新启动 HoloLens 2 并应用所做的更改，请选择 " **重新启动** "。

#### <a name="top-display-color-calibration-known-issues"></a>顶部显示颜色校准已知问题

- 在 "设置" 页上，在重新加载设置页面之前，提示你上次更改颜色配置文件的状态字符串将过期。
    - 解决方法：选择其他设置页，然后重新选择校准页。

### <a name="default-app-picker"></a>默认应用选取器

当你激活超链接或打开具有多个已安装的应用程序的文件类型（该应用程序支持该类型）时，你将看到一个新窗口打开，提示你选择哪个已安装的应用程序应处理文件或链接类型。 在此窗口中，你还可以选择让选定的应用处理文件或链接类型 "一次" 或 "始终"。

![应用选取器窗口](images/default-app-picker.png)

如果选择 "始终"，但稍后要更改哪个应用处理特定文件或链接类型，则可以在 "设置" " **> 应用**" 中重置已保存的默认值。 滚动到页面底部，在 "文件类型的默认应用" 和/或 "链接类型的默认应用" 下选择 " **清除** " 按钮。 与台式计算机上类似的设置不同，不能重置单独的文件类型默认值。

### <a name="per-app-volume-control"></a>按应用音量控制

现在，在此 Windows 内幕构建中，用户可以手动调整每个应用的音量级别。 这样，用户便可以更好地专注于所需的应用，也可以更好地使用多个应用。 例如，需要在为另一个应用程序调用另一个用户时关闭一个应用程序的卷。

若要设置单个应用的音量，请导航到 "**设置**"  ->  "**系统**  ->  **声音**"，然后在 "高级声音选项" 下选择 "**应用卷和设备首选项**"。

 <img alt="App volume and device preferences." src="./images/volume-per-app.jpg" width="500" height="250" />

### <a name="office-web-app"></a>Office web 应用

>[!NOTE]
>从 Windows 有问必答版本20325.1000 开始，Office web 应用将不再预安装 (，并且将不会为即将发布的操作系统更新的公开版本预先安装该应用。 若要安装 Office web 应用，请访问 https://www.office.com 并选择地址栏中的 " **可用应用** " 或 " **安装 Office** " 按钮。 选择 " **安装** " 进行确认。

已将 Office web 应用添加到 "开始" 菜单中的 "所有应用" 列表。 也可以将此 web 应用固定到 "启动" 或 "已卸载"。 由于这是 web 应用，因此其功能与你要通过访问获得的内容完全匹配 https://www.office.com 。 仅当 HoloLens 2 具有活动 internet 连接时，Office web 应用功能才可用。

**已知问题**
- 重置设备将删除 Office web 应用

### <a name="swipe-to-type"></a>刷到类型

有些客户通过轻扫要键入的单词的形状，来更快地在虚拟键盘上 "键入"，并且我们正在为全息键盘预览此功能。 您可以通过在全息键盘的平面上传递手指的笔尖，刷一字的形状，然后从键盘飞机取出手指的笔尖，一次轻扫一个词。 您可以通过从键盘上的键盘删除手指，无需按下空格键，就可以扫开单词。 如果你在键盘上的手指移动后看到一张滑动轨迹，你会知道该功能正在运行。

请注意，此功能可能会比较棘手，因为全息键盘的性质与移动电话) 不同，你不会对手指 (。 我们正在为公共版本评估此功能，因此你的反馈非常重要;无论你是发现此功能有用，还是有建设性的反馈，请通过 [反馈中心](hololens-feedback.md)告诉我们。

### <a name="power-menu-from-start"></a>入门的 Power menu

允许用户注销、关闭和重新启动设备的新菜单。 在 "HoloLens 开始" 屏幕中显示系统更新何时可用的指示器。

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

此 Windows 内幕版本中引入的 **其他用户** 位于 "PIN 输入" 字段的右侧时，该登录屏幕将显示多个以前登录到设备的用户。 这允许用户选择其用户配置文件，然后使用他们的 Windows Hello 凭据进行登录。 还可以通过 " **添加帐户** " 按钮将新用户添加到该设备。

在 "其他用户" 菜单中，"其他用户" 按钮将显示最后一个登录到设备的用户。 选择此按钮可返回到此用户的登录屏幕。

![登录屏幕默认值](./images/multiusers1.jpg)

<br>

![其他用户登录屏幕](./images/multiusers2.jpg)

### <a name="usb-c-external-microphone-support"></a>USB-C 外部麦克风支持

> [!IMPORTANT]
> 插入 **USB 麦克风不会自动将其设置为输入设备**。 当插入一组 USB-C 耳机时，用户将看到耳机音频将自动重定向到耳机，但 HoloLens OS 会将内部麦克风阵列的优先级设置为任何其他输入设备的优先级。 **若要使用 USB-C 麦克风，请遵循以下步骤。**

用户可以使用 " **声音** 设置" 面板选择 "USB 连接的外部麦克风"。 USB-C 麦克风可用于呼叫、录制等。

打开 "**设置**" 应用程序并选择 "**系统**  >  **声音**"。

![声音设置](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 若要将外部麦克风用于 **远程协助**，用户需要单击 "管理声音设备" 超链接。
>
> 然后，使用下拉设置将外部麦克风设置为 **默认** 值或 **通信默认值。** 选择 " **默认值** " 表示将在任何位置使用外部麦克风。
>
> 选择 " **通信默认值** " 表示将在远程协助和其他通信应用中使用外部麦克风，但 HoloLens mic 数组仍可用于其他任务。

![管理声音设备](images/usbc-mic-2.png)

<br>

![设置麦克风默认值](images/usbc-mic-3.jpg)

#### <a name="what-about-bluetooth-microphone-support"></a>蓝牙麦克风支持是怎样的？

遗憾的是，目前尚不支持 HoloLens 2 的蓝牙麦克风。

#### <a name="troubleshooting-usb-c-microphones"></a>USB-C 麦克风疑难解答

请注意，某些 USB-C 麦克风会错误地将自身报告为麦克风 *和* 扬声器。 这是麦克风问题，而不是使用 HoloLens。 将其中一个麦克风插入 HoloLens 时，可能会丢失声音。 幸运的是，有一个简单的修补程序。  

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

### <a name="use-the-new-settings-and-edge-apps-in-kiosk-modes"></a>在展台模式下使用新设置和边缘应用

当在 [网亭](hololens-kiosk.md)中包含应用时，IT 管理员通常会将该应用添加到展台，但使用其应用用户模型 ID (AUMID) 。 由于 "设置" 应用和 Microsoft Edge 应用都被视为新应用，并且与将 AUMIDs 用于这些应用的较旧的应用网亭不同，因此需要将其更新为使用新的 AUMID。

修改展台以包含新应用时，建议添加新的 AUMID，并保留旧的应用。 这会在用户更新操作系统时创建轻松转换，而无需接收新策略，即可继续使用展台。

| 应用                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 旧设置应用       | HolographicSystemSettings_cw5n1h2txyewy！应用            |
| 新建设置应用       | BAEAEF15-9BAB-47FC-ACECAD2AE94B_cw5n1h2txyewy 800B！应用 |
| 旧的 Microsoft Edge 应用 | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新的 Microsoft Edge 应用 | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE    |

### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>用于处理故障的展台模式行为更改

在较旧的版本中，如果设备具有展台配置（这是全局分配的访问和 AAD 组成员分配的访问权限），则如果确定 AAD 组成员身份失败，用户将看到 "不[在启动时显示任何内容](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)" 菜单。

从 Windows 预览体验版开始，kiosk 体验将回退到全局展台配置 (如果存在，则在 AAD 组展台模式发生故障的情况下) 。

### <a name="new-settingsuris-for-page-settings-visibility"></a>新 SettingsURIs 的页面设置可见性

在 [Windows 全息版中，](hololens-release-notes.md#windows-holographic-version-20h2) 我们添加了 [settings/PageVisibilityList 策略](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) ，以限制在 "设置" 应用中查看的页面20H2。 PageVisibilityList 是一种策略，它允许 IT 管理员阻止显示或访问 "系统设置" 应用中的特定页面，或为除指定的页面之外的所有页面执行此操作。

如果访问 [页面设置可见性](settings-uri-list.md)，则可以找到使用此 CSP 的说明，以及以前版本中可用的 uri 列表。

在 Windows 有问必答版本中，我们将展开可用设置 Uri 列表（管理员可以管理）的列表。 其中一些 Uri 适用于新的设置应用内的新可用区域。 如果你使用的是设置/PageVisibilityList 策略，请查看以下列表，并根据需要调整你允许或阻止的页面。

> [!NOTE]
> **弃用： ms 设置：网络代理**
>
> 在这些较新的版本中不推荐使用一个设置页。 旧的 **网络 & Internet**  >  **代理** 页面不再作为全局设置提供。 新的每连接代理设置可在 **网络 & internet**  >  **wi-fi**  >  **属性** 或 **网络 & internet**  >  **以太网**  >  **属性** 下找到。

<br>

| “设置”页                                        | URI                                              |
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

### <a name="configuring-fallback-diagnostics-via-settings-app"></a>通过 "设置" 应用配置回退诊断

现在，在 "设置" 应用中，用户可以配置 [回退诊断](hololens-diagnostic-logs.md)的行为。 在 "设置" 应用中，导航到 "**隐私**  ->  **故障排除**" 页以配置此设置。

> [!NOTE]
> 如果为设备配置了 MDM 策略，则用户将无法重写该行为。  

### <a name="share-things-with-nearby-devices"></a>与附近设备共享东西

通过 Windows 10 设备近乎共享某些东西，包括运行 HoloLens 有问必答 build 20279.1006 + 的 Pc 和其他 HoloLens 2 设备。 可以在 "**设置**" "系统共享体验" 中试用它，  ->    ->  以将文件或 url 从 HoloLens 共享到 PC。 有关更多详细信息，请参阅有关如何 [在 Windows 10 中与附近设备共享内容](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)的详细信息。

此功能可通过 [连接/AllowConnectedDevices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)进行管理。

### <a name="new-os-update-troubleshooter"></a>新操作系统更新疑难解答

除了在 "设置" 应用程序中使用前面的疑难解答外，还添加了新的疑难解答，同时添加了新的 OS 更新设置应用。 导航到 "**设置**" "  ->  **更新 &amp; 安全**  >  **疑难解答**"  >  **Windows 更新** 并选择 "**启动**"。 这样，你就可以收集跟踪，同时在操作系统更新中重现你的问题，以帮助更好地帮助你的 IT 或支持人员进行故障排除。

### <a name="delivery-optimization-preview"></a>传递优化预览

使用此 HoloLens 有问必答更新，Windows 全息版 for Business 启用了交付优化设置的早期预览，以减少从多个 HoloLens 设备下载的带宽消耗。 此处提供了此功能以及推荐的网络配置的完整描述： [Windows 10 更新的传递优化](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization)。

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

- 仅限在此预览版中提供 HoloLens 支持。
- Windows 全息 for Business 仅支持 HTTP 下载模式和从 [Microsoft 连接缓存端点](https://docs.microsoft.com/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache)下载;目前，HoloLens 设备不支持对等下载模式和组分配。
- HoloLens 不支持 Windows Server Update Services 终结点的部署或传递优化。
- 故障排除将需要在已连接的缓存服务器上进行诊断，或者通过 **设置**  >  **更新 & 安全**  >   **故障排除**  >   **Windows 更新** 在 hololens 上收集一个跟踪。

### <a name="improvements-and-fixes-in-the-update"></a>更新中的改进和修复：

- [脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics) 还将包含序列号和操作系统版本的其他设备信息。

### <a name="known-issues-and-work-around"></a>已知问题和解决方法

#### <a name="pairing-hololens-to-pc"></a>将 HoloLens 配对到 PC

在 Windows 有问必答版本20325.1000 之前的版本中，当用户在 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 或 [windows 全息版或 windows 全息版（版本 2004](hololens-release-notes.md#windows-holographic-version-2004) ）上设置配对凭据并更新到 windows 有问必答版本时，其以前的设置凭据用于将 HoloLens 与电脑进行配对，以便部署和调试应用（如通过 Visual Studio）。 Windows 预览体验内部版本20325.1000 修复了此问题，无需执行其他操作即可使用设备门户进行恢复。

[使用内部版本闪存其设备的](#ffu-download-and-flash-directions)用户现在需要将 (其设备刷新到 20325.1000 + 或 GA build) ，以将其设备与 PC 配对。

未在 Windows 预览体验中注册并且将在其正式发布时进行功能更新的用户不会受到影响。


## <a name="start-receiving-insider-builds"></a>开始接收 Insider 内部版本

> [!NOTE]
> 如果你最近没有更新，请重新启动你的设备以更新状态并获取最新版本。
> - "重新启动设备" 语音命令正常工作。 
> - 你还可以在 "设置/Windows 预览体验计划" 中选择 "重启" 按钮。
>
> 我们在你可能遇到的后端上遇到了一个错误，这会使你返回到 "跟踪"。

在 HoloLens 2 设备上，转到 "**设置**" "  >  **更新 & 安全**  >  **Windows 预览体验计划**"，然后选择 "**开始** 使用"。 将用于注册的帐户链接到 Windows 内部。

Windows 有问必答现在正在转移到频道。 **快速** 环将成为 **开发通道**，**慢速** 环将成为 **Beta 通道**，并且 **发布预览** 环将成为 **发布预览通道**。 如下图所示：

![Windows 预览体验频道说明](images/WindowsInsiderChannels.png)

有关详细信息，请参阅 windows 上的 [Windows 有问必答通道简介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 博客。

然后，选择 " **Windows 的活动开发**"，选择是要接收 **开发渠道** 还是生成 **Beta 通道** ，并查看程序条款。

选择 " **确认" > 立即重新启动** 以完成操作。 重新启动设备后，请转到 " **设置" > 更新 & 安全 > 检查更新** 以获取最新版本。

### <a name="update-error-0x80070490-work-around"></a>更新错误0x80070490 解决方法
如果在开发或 Beta 通道上进行更新时遇到更新错误0x80070490，请尝试以下短期解决方法。 它涉及到移动预览体验，选择更新，然后再移到你的内部渠道。

#### <a name="stage-one---release-preview"></a>阶段单一发布预览版
1.  设置，更新 & 安全性，Windows 预览体验计划，请选择 " **发布预览通道**"。
2.  设置、更新 & 安全性、Windows 更新、 **检查更新**。 更新后，继续执行第二阶段。

#### <a name="stage-two---dev-channel"></a>阶段两开发人员通道
1. 设置，更新 & 安全性，Windows 预览体验计划，选择 **开发渠道**。
2. 设置、更新 & 安全性、Windows 更新、 **检查更新**。

## <a name="ffu-download-and-flash-directions"></a>FFU 下载和闪存说明
若要使用已签名 ffu 进行测试，必须先将设备解锁，然后再闪烁飞行签名 ffu。
1. 在 PC 上：

    1. 从下载 ffu [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 从 Microsoft Store 安装 ARC (高级恢复随附) ： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 。
    
1. 在 HoloLens 航班解锁：打开 **设置**  >  **更新 & 安全**  >  **Windows 预览体验计划**，然后注册，重新启动设备。

1. Flash FFU-现在可以使用 ARC 来刷新已签名的飞行 FFU。

## <a name="provide-feedback-and-report-issues"></a>提供反馈和报告问题

请使用 HoloLens 上 [的反馈中心应用](hololens-feedback.md) 提供反馈和报告问题。 使用反馈中心可确保包括所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。  需要以相同的方式报告有关中国和日本版 HoloLens 的问题。

> [!NOTE]
> 请确保接受提示，询问你是否想要反馈中心访问文档文件夹 (在出现) 提示时选择 **"是"** 。

## <a name="note-for-developers"></a>开发人员注意事项

欢迎并鼓励你尝试使用 HoloLens 的内部版本开发应用程序。  若要开始，请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 。 这些相同的说明适用于 HoloLens 的内部版本。  你可以使用与你已用于 HoloLens 开发的 Unity 和 Visual Studio 相同的版本。

## <a name="stop-receiving-insider-builds"></a>停止接收 Insider 内部版本

如果你不想再收到 Windows 全息的内部版本，你可以在你的 HoloLens 运行生产版本时选择退出，或者可以使用高级恢复助理 [恢复你](hololens-recovery.md) 的设备，以将设备恢复到非有问必答版 windows 全息版。

> [!CAUTION]
> 存在一个已知问题，即，手动重新安装全新预览版本后，从 Insider preview 版本注册的用户将会遇到蓝屏。 此后，它们必须手动恢复其设备。 有关是否受影响的详细信息，请查看此 [已知问题](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的详细信息。

验证 HoloLens 是否正在运行生产版本：

1. 请参阅 " **设置" > 系统 > 关于**，并找到内部版本号。

1. [请参阅生产内部版本号的发行说明](hololens-release-notes.md)。

选择退出内幕生成：

1. 在运行生产生成的 HoloLens 上，中转到 " **设置" > 更新 "& 安全" > Windows 预览体验计划**"，然后选择" **停止内幕生成**"。

1. 按照说明选择设备。
