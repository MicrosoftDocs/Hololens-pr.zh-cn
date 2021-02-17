---
title: Microsoft HoloLens 内部预览版
description: 了解如何开始使用预览体验成员版本，并为 HoloLens 的下一个主要操作系统更新提供有价值的反馈。
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
ms.date: 2/16/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 885f9a841c5f59f2816667256de0856f8a1f2612
ms.sourcegitcommit: ab35169529776f0682eeb8fa448c9d9e8f598513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2021
ms.locfileid: "11340532"
---
# Microsoft HoloLens 内部预览版

欢迎使用 HoloLens 的最新 Insider Preview 版本！ 开始操作非常简单，并为[](hololens-insider.md#start-receiving-insider-builds)HoloLens 的下一个主要操作系统更新提供有价值的反馈。

## Windows 预览体验成员发行说明

我们很高兴再次开始向 Windows 预览体验成员提供新功能。 新内部版本将测试到开发人员频道获取最新更新。 我们将继续更新此页面，因为我们向 Windows 预览体验成员版本添加更多功能和更新。  感到很高兴，并准备好将这些更新融合到你的现实中。

> [!IMPORTANT]
> 如果你之前在展台中使用的是"设置"应用或 Microsoft Edge 应用，则我们将这些应用替换为使用不同的应用 ID 的新应用。 我们强烈建议你在下面的展台模式下阅读新[应用的新 AUMID。](#use-the-new-settings-and-edge-apps-in-kiosk-modes) 这将确保你继续在展台中拥有"设置"应用，或包括新的 Microsoft Edge 应用。

<br>

| 功能名称                                              | 简短说明                                                                      | 在内部版本可用 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新版 Microsoft Edge](#introducing-the-new-microsoft-edge) | 新的基于 Chromium 的 Microsoft Edge 现在可用于 HoloLens 2                         | 20279.1006 |
| [WebXR 和 360 Viewer](#webxr-and-360-viewer)             | 尝试沉浸式 Web 体验和 360 视频播放                                           | 20289.1000 |
| ["新建设置"应用](#new-settings-app)                     | 旧式"设置"应用将替换为具有新功能和设置的更新版本 | 20279.1006 |
| [显示颜色校准](#display-color-calibration)   | 为 HoloLens 2 显示器选择备用颜色配置文件                                | 20293.1000 |
| [默认应用选取器](#default-app-picker)                 | 选择应针对每个文件或链接类型启动的应用                                      | 20279.1006 |
| [Office Web 应用](#office-web-app)                         | Office Web 应用的快捷方式现在列在"所有应用"中                                   | 20279.1006 |
| [轻扫以键入](#swipe-to-type)                           | 使用手指提示在全息键盘上"轻扫"字词                        | 20279.1006 |
| [USB-C 外部麦克风支持](#usb-c-external-microphone-support) | 将 USB-C 麦克风用于应用和/或远程协助。| 20279.1006 |
| [展台模式下新应用的新 AUMID](#use-the-new-settings-and-edge-apps-in-kiosk-modes) | 新设置和边缘应用的 AUMID | 20279.1006 |
| [页面设置可见性的新 SettingsURIs](hololens-insider.md#new-settingsuris-for-page-settings-visibility) | 设置/PageVisibilityList 策略的 20+ 新 SettingsURIs | 20289.1000 |
| [改进的展台模式故障帮助](#kiosk-mode-behavior-changes-for-handling-of-failures) | 展台模式在空的"开始"菜单之前查找全局分配的访问权限。 | 20279.1006 |
| [配置回退诊断](#configuring-fallback-diagnostics-via-settings-app) | 在"设置"应用中设置回退诊断行为 | 20279.1006 |
| [与附近设备共享内容](#share-things-with-nearby-devices) | 将文件或 URL 从 HoloLens 共享到电脑 | 20279.1006 |
| [新的操作系统更新疑难解答程序](#new-os-update-troubleshooter) | 操作系统更新的设置中的新疑难解答 | 20279.1006 |
| [更新中的改进和修复](#improvements-and-fixes-in-the-update) | 更新中的其他修补程序。 | 20279.1006 |

### 新 Microsoft Edge 的介绍

![旧 Microsoft Edge 徽标到新 Microsoft Edge 徽标的动画](images/new-edge.gif)

新的 Microsoft Edge [采用 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 开放源代码项目，为客户创建更好的兼容性，减少 Web 开发人员的 Web 碎片。

通过此预览体验成员预览版，新 Microsoft Edge 首次提供给 HoloLens 2 客户！ 虽然新 Microsoft Edge 最终将替换 HoloLens 2 上的旧版 Microsoft Edge，但预览体验成员目前可以使用这两种浏览器。 请通过新 Microsoft Edge 中的"**** 发送反馈"功能或通过"反馈中心"与团队[共享反馈和 Bug。](hololens-feedback.md)

![新 Microsoft Edge 屏幕截图](images/new-edge-ui.png)

#### 启动新的 Microsoft Edge

预览体验成员可以使用两个版本的 Microsoft Edge：新的 Microsoft Edge 新 Microsoft Edge 图标 (由蓝色和绿色旋转图标) 表示，旧 Microsoft Edge (由白色 ![ ](images/new_edge_logo.png) "e"图标) 表示。 新的 Microsoft Edge 固定到"开始"菜单，并且会在激活 Web 链接时自动启动。 如果要恢复为使用旧版 Microsoft Edge 作为默认 Web 浏览器，请参阅下面的说明 [重置默认应用](#default-app-picker)。

> [!NOTE]
> 当你首次在 HoloLens 2 上启动新的 Microsoft Edge 时，你的设置和数据将导入旧版 Microsoft Edge。 如果在启动新的 Microsoft Edge 后继续使用旧版 Microsoft Edge，则新数据将不会从旧 Microsoft Edge 同步到新的 Microsoft Edge。

#### 配置新 Microsoft Edge 的策略设置

新 Microsoft Edge 为 IT 管理员提供了一组比旧版 Microsoft Edge 更为广泛的 HoloLens 2 浏览器策略。

下面是一些有用的资源，用于了解有关管理新 Microsoft Edge 的策略设置的信息：

- [使用 Microsoft Intune 配置 Microsoft Edge 策略设置](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge 旧版到 Microsoft Edge 策略映射](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome 到 Microsoft Edge 策略映射](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- [完整的 Microsoft Edge 企业版文档](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 由于新的 Microsoft Edge 支持大量浏览器策略，因此团队无法保证每个新策略都适用于 HoloLens 2。 但是，我们已测试和确认与 HoloLens 2 上以前支持的每个旧 Microsoft Edge 策略等效的新 Microsoft Edge 策略的等效项可以正常工作。 请参阅 [Microsoft Edge 旧版到 Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 策略映射，查找与 HoloLens 2 一同使用的每个旧版 Microsoft Edge 浏览器策略的新 Microsoft Edge 等效项。
>
> 我们了解至少有两个新的 Microsoft Edge 策略将 *不能与* HoloLens 2 一起使用：
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### HoloLens 2 上新 Microsoft Edge 的预计功能

由于新的 Microsoft Edge 是本机 Win32 应用，具有新的 UWP 适配器层，允许它在仅 UWP 设备（如 HoloLens 2）上运行，因此某些功能可能不会立即可用。 我们将支持未来几个月的新方案和功能，因此请查看此空间了解最新信息。

**预期可工作的方案和功能：**
- 首次运行体验、登录配置文件和同步
- 网站应按预期呈现和行为
- 大多数浏览器功能 (收藏夹、历史记录等) 应正常工作
- 深色模式
- 将 Web 应用安装到设备
- 安装扩展 (请告诉我们，如果你使用的任何扩展在 HoloLens 2) 
- 查看和标记 PDF
- 单个浏览器窗口中的空间声音
- 浏览器的自动和手动更新
- 使用"保存到 PDF"选项 (打印菜单中保存 PDF) 

**即将推出方案和功能：**
- WebXR 和 360 查看器扩展
- 在环境中跨多个窗口浏览时，内容还原以更正窗口

**不需要工作的方案和功能：**
- 具有同时音频流的多个窗口的空间声音
- "查看它，说出它"
- 打印

**热门的浏览器问题：**
- 重置设备将删除新的 Microsoft Edge
- 全息键盘中的放大镜预览显示不正确的内容

#### Microsoft Edge 预览体验成员频道

Microsoft Edge 团队向 Edge 预览体验成员社区提供三个预览频道：Beta、Dev 和 Canary。 安装预览通道不会卸载 HoloLens 2 上发布的 Microsoft Edge 版本，并且可以同时安装多个。 

访问 [Microsoft Edge 预览体验成员主页](https://www.microsoftedgeinsider.com) ，了解有关 Edge 预览体验成员社区的信息。 若要了解有关不同边缘预览体验成员频道和入门的信息，请访问 Edge [预览体验成员下载页面](https://www.microsoftedgeinsider.com/download)。

有两种方法可用于将 Microsoft Edge 预览体验成员频道安装到 HoloLens 2：

**直接安装在设备上 (当前仅适用于非托管设备) **
  1. 在 HoloLens 2 上，访问 [Edge 预览体验成员下载页面](https://www.microsoftedgeinsider.com/download)。
  1. 选择要安装的边缘预览体验成员频道的"下载 **HoloLens 2"** 按钮。
  1. 使用"文件资源管理器" (从边缘下载队列或设备的"下载"文件夹中启动下载的 .msix) 。
  1. [应用安装程序](app-deploy-app-installer.md) 将启动。
  1. 选择 **"安装"** 按钮。
  1. 成功安装后，你将在"开始"菜单的"所有应用"列表中发现 Microsoft Edge Beta、Dev 或 Canary 作为单独的条目。 ****

**通过具有 Windows Device Portal [ (的电脑进行](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) 安装需要在 HoloLens 2 设备上启用开发人员) **
  1. 在电脑上，访问 [Edge 预览体验成员下载页面](https://www.microsoftedgeinsider.com/download)。
  1. 选择要 **安装** 的边缘预览体验成员频道的"为 Windows 10 下载"按钮旁边的下拉箭头按钮。
  1. 在**下拉菜单中选择 HoloLens 2。**
  1. 将 .msix 文件保存到电脑文件夹的"下载 (或其他文件夹，你可以轻松找到) 。
  1. 使用 [电脑上的 Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app) 在 HoloLens 2 上安装下载的 .msix 文件。
  1. 成功安装后，你将在"开始"菜单的"所有应用"列表中发现 Microsoft Edge Beta、Dev 或 Canary 作为单独的条目。 ****

> [!NOTE]
> 在此适用于 HoloLens 2 的 Windows 预览体验成员预览版期间，你设备上 Microsoft Edge 的版本可能高于某些 (或所有) Microsoft Edge 预览体验成员频道中提供的版本。 这是为了确保专门面向 HoloLens 2 上的 Web 浏览器的新功能和修补程序尽快进入我们的 Windows 预览体验成员。 在公开发布下一个 Windows 更新后，Microsoft Edge 预览体验成员频道版本将超过 HoloLens 2 上的 Microsoft Edge 版本，并保持领先。

### WebXR 和 360 Viewer

*在 Windows 预览体验成员版本 20289.1000 中添加*

新的 Microsoft Edge 包括对 WebXR 的支持，WebXR 是用于创建沉浸式 Web 体验的新标准， (WebVR) 。 许多沉浸式 Web 体验在设计时都考虑到了 (将你的视野替换为虚拟环境) ，但 HoloLens 2 也支持这些体验。 WebXR 标准还支持使用物理环境的增强和混合现实沉浸式 Web 体验。 随着开发人员在 WebXR 上花费更多时间，我们预计新的增强和混合现实沉浸式体验将到达 HoloLens 2 客户试用！

360 查看器扩展基于 WebXR 构建，并自动与 HoloLens 2 上的新 Microsoft Edge 一起安装。 此 Web 扩展让你能够沉浸于 360 度视频中。 YouTube 提供了最多 360 个视频选择，因此我们建议您从该视频开始。

#### 如何使用 WebXR

1. 导航到具有 WebXR 支持的网站。
1. 选择网站上 **"输入VR"** 按钮。 此按钮的位置和视觉表示形式可能因网站而异，但外观可能类似于：

    ![输入"VR"按钮示例](images/75px-enter-vr.png)

1. 首次尝试启动特定域上的 WebXR 体验时，浏览器会请求同意以输入沉浸式视图，选择"**允许"。**
1. 使用 [HoloLens 2 手势](hololens2-basic-usage.md#the-hand-tracking-frame) 操作体验。
1. 如果体验没有**退出按钮，** 请使用"开始"手势返回主页[](hololens2-basic-usage.md#start-gesture)。

**建议的 WebXR 示例**
- 360 Viewer (请参阅下一节) 
- [XR 恐龙](https://www.xrdinosaurs.com/)
- [Barista Express](https://constructarca.de/game/barista-express/)
- [WebXR 绘制](https://threejs.org/examples/webxr_vr_paint.html)

#### 如何使用 360 查看器

1. 导航到 YouTube 上的 360 度视频。
1. 在视频帧中，选择混合现实耳机按钮：

    ![用于激活 360 查看器的按钮](images/enter-360-viewer.jpg)

1. 首次尝试在特定域中启动 360 查看器时，浏览器将请求同意输入沉浸式视图。 选择 **"允许"。**
1. [通过点击](hololens2-basic-usage.md#select-using-air-tap) 来显示播放控件。 使用 [手](hololens2-basic-usage.md#select-using-air-tap) 风和空点击播放/暂停、向前/后退、打开/关闭标题或停止体验 (退出沉浸式视图) 。 播放控件将在几秒钟的不活动状态后消失。

#### 热门 WebXR 和 360 Viewer 已知问题
- 在 WebXR 体验中，当你倾斜头或四处移动时，全息影像可能会移动或倾斜。
- 根据 WebXR 体验的复杂性，帧速率可能会下降或不一样。
- WebXR 中尚不提供手接点。
- 退出 WebXR 或 360 查看器体验时，混合现实家庭中的全息影像可能需要 30 秒或更多时间重新出现。
- 来自 YouTube 网站（而非 YouTube）的 360 个视频可能无法如期工作。
- 如果 360 个视频未进入沉浸式 (或混合现实耳机按钮未) ，请尝试刷新页面。
- 标题在 HoloLens 2 上的 360 查看器中尚不可见。
- 暂停 360 查看器中的视频会阻止视频 (但正确选择播放按钮可恢复) 。
- 360 Viewer 中的"下一个视频"按钮当前不起作用。
- 可以在沉浸式"theater"模式下播放 2D 视频，但帧速率将小于 30 fps。

#### 提供有关 WebXR 和 360 查看器的反馈

请通过新 Microsoft Edge 中的"**** 发送反馈"功能与团队共享反馈和 Bug。

### "新建设置"应用

通过此版本，我们将引入新版本的"设置"应用。 新的"设置"应用包括以下领域的 HoloLens 2 新功能和扩展设置：声音、Power & 睡眠、网络 & Internet、应用、帐户、轻松使用等。

> [!NOTE]
> 由于新的"设置"应用不同于旧式"设置"应用，因此更新时将删除之前放置在环境周围的任何"设置"窗口。

!["新建设置"应用主页](images/new-settings-app.png)

**新功能和设置**
- 设置搜索：使用关键字或设置名称从"设置"主页搜索设置。
- 系统>声音：
  - 输入和输出音频设备：独立选择输入和输出音频设备 (例如，通过 Bluetooth 耳机收听音频或使用 USB-C 麦克风进行音频输入) 。
    > [!NOTE]
    > Bluetooth HoloLens 2 不支持麦克风。
  - 应用量：独立调整每个应用的音量。
- 系统>电源&睡眠：选择设备在一段时间不活动后应何时进入睡眠状态。
- 系统>：手动启用节电模式或设置节电模式自动打开的电池阈值。
- USB >设备：默认情况下可以禁用 USB 连接。
- Internet &网络：
  - USB-C 以太网适配器现在将显示在 Internet &中。
  - USB-C 以太网适配器设置现已可用，包括其 IP 地址。
  - 你现在可以在 HoloLens 2 上启用飞行模式。
- 应用：你可以重置用于文件和链接类型的默认应用。 有关详细信息，请参阅 [默认应用选取器](#default-app-picker)。
- 其他用户>帐户：设备所有者可以添加用户、将标准用户升级到设备所有者、将设备所有者降级为标准用户以及删除用户。
- 轻松访问：更改文本大小和一些视觉效果。

**已知问题**
- 之前放置的"设置"窗口将被删除 (请参阅上述) 。
- 访问"通知"页可能会使"设置"应用崩溃 (调查) 。
- 以太网页面当前不会显示 (即将修复) 。
- 你无法再使用"设置"应用重命名设备 (IT 管理员可以使用预配包或 MDM 重命名设备) 。
- 新 Microsoft Edge 的电池使用情况可能不准确，因为其性质是 UWP 适配器层支持的 Win32 桌面应用程序 (预计) 。

### 显示颜色校准

*在 Windows 预览体验成员版本 20293.1000 中添加*

借助此新设置，你可以为 HoloLens 2 显示器选择备用颜色配置文件。 这可以帮助颜色显示更准确，尤其是在较低的显示亮度级别下。 显示颜色校准可在"设置"应用的"系统校准>找到。

#### 如何使用显示颜色校准

1. 启动"**设置"** 应用并导航到 **">校准"。**
1. 在 **"显示颜色校准"下**，选择 **"运行显示颜色校准"** 按钮。
1. 显示颜色校准体验将启动，鼓励你确保面罩处于正确的位置。
1. 在继续说明对话框后，屏幕将自动灰显为 30% 的亮度。
    > [!TIP]
    > 如果你在看到环境中灰显的场景时遇到问题，可以使用设备左侧的亮度按钮手动调整 HoloLens 2 的亮度级别。
1. 选择按钮 1-6 可立即试用每个颜色配置文件，并找到一个外观最佳 (这通常意味着帮助场景显示最中性、灰度模式和眼音按预期显示的个人资料。) 

    ![显示颜色校准场景](images/color-cal-ui.png)
    
1. 如果对所选的配置文件满意，请选择"保存& **退出** "按钮
1. 如果不希望进行更改，请选择"取消& **退出"** 按钮，更改将恢复

> [!TIP]
> 以下是在使用显示颜色校准设置时请记住的一些有用提示：
> - 可以随时从"设置"中重新运行显示颜色校准
> - 如果设备上有人之前已使用此设置更改颜色配置文件，则最新更改的日期/时间将反映在"设置"页上
> - 重新运行显示颜色校准时，将突出显示之前保存的颜色配置文件，配置文件 0 将不会 (因为配置文件 0 表示显示的原始颜色配置文件) 
> - 如果要还原到显示的原始颜色配置文件，可以从"设置"页 [ (了解如何重置](#how-to-reset-color-profile) 颜色配置文件) 

#### 如何重置颜色配置文件

如果你对保存到 HoloLens 2 的自定义颜色配置文件不满意，你可以还原设备的原始颜色配置文件：
1. 启动"**设置"** 应用并导航到 **">校准"。**
1. 在 **"显示颜色校准"** 下，选择" **重置为默认颜色配置文件"** 按钮。
1. 当屏幕重置时，屏幕将关闭几秒钟。 我们建议你在屏幕打开后重新启动设备**， ([已知问题](#top-display-color-calibration-known-issues)) 。

#### 顶部显示颜色校准已知问题

- 在"设置"页上，告知您上次更改颜色配置文件时间的状态字符串将过期，直到重新加载该"设置"页 
    - 解决方法：选择另一个"设置"页，然后重新选择"校准"页。
- "重置为默认颜色配置文件"按钮将打开一个没有文本的对话框。 但是对话框中的"重置"按钮按预期工作。
- 选择"重置"按钮后，你的屏幕可能会空白 5-10 秒，你可能会注意到混合现实家庭版中的意外行为。 请使用"重置"按钮 (请重新启动设备 (我们很快就会解决此问题，以自动重启设备，我们将相应地更新"设置"文本) 。
- 如果你的 HoloLens 2 在运行显示颜色校准时进入睡眠状态，它稍后将恢复进入混合现实主页，并且你的显示亮度级别仍将变暗。
- 你可能需要尝试按设备左侧的亮度按钮上/下几次，然后才能按预期工作。

### 默认应用选取器

激活超链接或打开具有多个已安装应用（支持该超链接）的文件类型时，你将看到一个新窗口打开，提示你选择应处理文件或链接类型的已安装应用。 在此窗口中，还可以选择让所选应用处理文件或链接类型"一次"或"始终"。

![应用选取器窗口](images/default-app-picker.png)

如果你选择"始终"，但后来想要更改哪个应用处理特定文件或链接类型，可以在"设置"或"应用"中重置> **默认值**。 滚动到页面底部，然后选择"文件类型的默认应用****"和/或"链接类型的默认应用"下的"清除"按钮。 与桌面电脑中的类似设置不同，不能重置单个文件类型默认值。

### Office Web 应用

Office Web 应用已添加到"开始"菜单中的"所有应用"列表中。 此 Web 应用还可以固定到"开始"页面或卸载。 因为这是一个 Web 应用，因此其功能与通过访问体验完全匹配 https://www.office.com 。 仅在 HoloLens 2 具有活动的 Internet 连接时，Office Web 应用功能才可用。

### 轻扫以键入

一些客户发现，通过轻扫要键入的单词的形状，在虚拟键盘上"键入"速度更快，我们正在预览全息键盘的此功能。 通过通过全息键盘的平面传递手指的尖角，轻扫该单词的形状，然后从键盘平面上撤消手指的提示，可以一次轻扫一个单词。 通过从键盘中删除手指，无需按空格键，即可轻扫后续字词。 如果你看到手指在键盘上移动后有轻扫轨迹，你将知道该功能正在工作。

请注意，此功能可能很难使用和掌握，因为全息键盘的性质，与移动电话显示器 (无法抵御手指) 。 我们正在评估此功能以公开发布，因此您的反馈非常重要;无论你发现此功能有用还是有反馈反馈，请通过反馈中心 [告诉我们](hololens-feedback.md)。

### USB-C 外部麦克风支持

> [!IMPORTANT]
> 插入 **USB 麦克风不会自动将其设置为输入设备**。 在插入一组 USB-C 耳机时，用户将观察到耳机的音频将自动重定向到耳机，但 HoloLens 操作系统会将内部麦克风阵列设置为高于任何其他输入设备的优先级。 **若要使用 USB-C 麦克风，请按照以下步骤操作。**

用户可以使用"声音设置"面板选择连接 USB-C **的外部麦克风** 。 USB-C 麦克风可用于呼叫、录制等。

打开"**设置"** 应用，然后选择 **"系统**  ->  **声音"。**

![声音设置](images/usbc-mic-1.jpg)

> [!IMPORTANT]
> 若要将外部麦克风与 **远程协助**一同使用，用户需要单击"管理声音设备"超链接。
>
> 然后使用下拉列表将外部麦克风设置为"默认" **或** " **通信默认值"。** 选择 **"** 默认值"意味着外部麦克风将在任何位置使用。
>
> 选择 **"** 通信默认值"意味着外部麦克风将用于远程协助和其他通信应用，但 HoloLens 麦克风阵列仍可用于其他任务。

![管理声音设备](images/usbc-mic-2.png)

<br>

![设置麦克风默认值](images/usbc-mic-3.jpg)

#### 麦克风Bluetooth如何？

遗憾的是Bluetooth HoloLens 2 上当前仍不支持麦克风。

#### USB-C 麦克风疑难解答

请注意，某些 USB-C 麦克风错误地将自己报告为麦克风*和扬声器。* 这是麦克风的问题，而不是 HoloLens 的问题。 将其中一个麦克风插入 HoloLens 时，可能会丢失声音。 幸运的是，有一个简单的解决方法。  

在 **"设置**  ->  **系统**  ->  **声音******"中，将内置扬声器 (**模拟功能**音频驱动程序) 默认设备。 HoloLens 应记住此设置，即使稍后删除了麦克风并重新连接。

![USB-C 麦克风疑难解答](images/usbc-mic-4.png)

### 在展台模式下使用新的"设置"和"边缘"应用

在 [展台中](hololens-kiosk.md)加入应用时，IT 管理员通常会将应用添加到展台，但使用应用用户模型 ID (AUMID) 。 由于"设置"应用和 Microsoft Edge 应用都被视为新应用，并且不同于使用这些应用的 AUMID 的较旧应用展台，因此将需要更新以使用新的 AUMID。

在修改展台以包含新应用时，我们建议在新的 AUMID 中添加并保留旧应用。 这将在用户更新操作系统时创建一个简单的转换，并且不需要接收新策略来继续如期使用展台。

| 应用                    | AUMID                                                  |
|------------------------|--------------------------------------------------------|
| 旧设置应用       | HolographicSystemSettings_cw5n1h2txyewy！应用            |
| "新建设置"应用       | BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy！应用 |
| 旧 Microsoft Edge 应用 | Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge    |
| 新的 Microsoft Edge 应用 | Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE    |

### 页面设置可见性的新 SettingsURIs

在 [Windows 全息版版本 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中，我们添加了 ["设置/PageVisibilityList"](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-pagevisibilitylist) 策略，以限制"设置"应用中显示的页面。 PageVisibilityList 是一项策略，它允许 IT 管理员阻止查看或访问“系统设置”应用中的特定页面，或者对除指定页面之外的所有页面执行此操作。

如果你访问 [页面设置可见性](settings-uri-list.md)，你可以找到使用此 CSP 的说明和以前版本中提供的 URI 列表。

在 Windows 预览体验成员内部版本，我们正在扩展可用设置 URI 的列表，IT 管理员可以管理该列表。 其中一些 URI 用于新"设置"应用中的新可用区域。 如果使用的是"设置/PageVisibilityList"策略，请查看以下列表并根据需要调整允许或阻止的页面。

> [!NOTE]
> **已弃用：ms-settings：network-proxy**
>
> 在这些较新的内部版本中，一个设置页已弃用。 旧的 **"& Internet**代理"页  >  **** 不再作为全局设置提供。 新的每连接代理设置位于**Internet**  >  **Wi-Fi**&或 Internet 以太网&  >  ********  >  ****  >  **下**。

<br>

| 设置页面                                        | URI                                              |
|------------------------------------------------------|--------------------------------------------------|
| 应用>应用&功能                               | `ms-settings:appsfeatures`                         |
| 应用>应用&高级>功能          | `ms-settings:appsfeatures-app`                     |
| 离线>应用                                  | `ms-settings:maps`                                 |
| 应用>离线地图>下载地图                  | `ms-settings:maps-downloadmaps`                    |
| 鼠标>设备                                      | `ms-settings:mouse`                                |
| USB >设备                                        | `ms-settings:usb`                                  |
| 网络& Internet >飞行模式                   | `ms-settings:network-airplanemode`                 |
| 隐私>常规                                    | `ms-settings:privacy-general`                      |
| 隐私>墨迹&个性化设置             | `ms-settings:privacy-speechtyping`                 |
| 隐私>动作                                     | `ms-settings:privacy-motion`                       |
| 隐私>屏幕截图边框                         | `ms-settings:privacy-graphicsCaptureWithoutBorder` |
| 隐私>屏幕截图和应用                       | `ms-settings:privacy-graphicsCaptureProgrammatic`  |
| 系统>电池                                     | `ms-settings:batterysaver`                         |
| 系统>电池                                     | `ms-settings:batterysaver-settings`                |
| 系统>声音                                       | `ms-settings:sound`                                |
| 系统>声音>应用音量和设备首选项 | `ms-settings:apps-volume`                          |
| 系统>声音>管理声音设备              | `ms-settings:sound-devices`                        |
| 系统>存储>配置存储感知         | `ms-settings:storagepolicies`                      |
| Time & Language > Date & time                        | `ms-settings:dateandtime`                          |
| 时间&语言>键盘                           | `ms-settings:keyboard`                             |
| Time & Language > Language                           | `ms-settings:language`                             |
| Time & Language > Language                           | `ms-settings:regionlanguage-languageoptions`       |
| 更新&安全>重置&恢复               | `ms-settings:reset`                                |

#### 更新的 URI

以前，以下两个 URI 不会将用户直接带至指示的页面，而只会阻止主更新页面。 以下项已更新为直接显示其页面：

- `ms-settings:windowsupdate-options`
- `ms-settings:windowsupdate-restartoptions`

### 用于处理故障的展台模式行为更改

在较旧的内部版本中，如果设备具有展台配置（这是全局分配的访问权限和 AAD 组成员身份分配的访问权限的组合）。如果确定 AAD 组成员身份失败，用户将看到"开始"[](https://docs.microsoft.com/hololens/hololens-kiosk#kiosk-mode-behavior-changes-for-handling-of-failures)菜单中未显示任何内容。

从 Windows 预览体验成员版本开始，如果 AAD 组展台模式 (出现故障) ，展台体验将回退到全局展台配置。

### 通过"设置"应用配置回退诊断

现在，在"设置"应用中，用户可以配置 [回退诊断的行为](hololens-diagnostic-logs.md)。 在"设置"应用中，导航到 **"隐私**  ->  **疑难解答"** 页以配置此设置。

> [!NOTE]
> 如果为设备配置了 MDM 策略，用户将不能覆盖该行为。  

### 与附近设备共享内容

与 Windows 10 设备（包括运行 HoloLens Insider 版本 20279.1006+的其他 HoloLens 2 设备）附近共享内容。 可以在"设置**系统共享体验**"中试用，以将文件或 URL 从  ->  ****  ->  **** HoloLens 共享到电脑。 有关更多详细信息，请阅读有关如何在 [Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)中与附近设备共享内容的详细信息。

此功能可以通过 [Connectivity/AllowConnectedDevices 进行管理](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowconnecteddevices)。

### 新的操作系统更新疑难解答程序

除了"设置"应用中以前的疑难解答程序之外，还添加了新的疑难解答程序，并添加了新的 OS 更新的"设置"应用。 导航到 **"设置**  ->  **更新 &amp; 安全性**  ->  **疑**  ->  **难解答 Windows 更新**"，然后选择"**开始"。** 这允许你在通过操作系统更新重现问题时收集跟踪，以帮助更好地解决 IT 或支持问题。

### 更新中的改进和修复：

- [脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics) 还将包括序列号和操作系统版本的其他设备信息。






## 开始接收预览体验成员版本

> [!NOTE]
> 如果你最近尚未更新，请重启设备以更新状态并获取最新内部版本。
> - "重新启动设备"语音命令运行良好。 
> - 还可以选择"设置/Windows 预览体验计划"中的"重启"按钮。
>
> 我们在后端有一个你可能会遇到的 bug，这样你才能重新上路。

在 HoloLens 2 设备上 **，转到"** 设置更新&  >  ****  >  **安全 Windows 预览体验计划**，然后选择 **"开始使用"。** 链接你用于注册为 Windows 预览体验成员的帐户。

Windows 预览体验成员现在将迁移到频道。 快**圈**将成为开发人员**频道**，慢圈将成为******Beta**渠道，并且发布**预览圈将成为****版本预览频道**。 该映射如下所示：

![Windows 预览体验成员频道说明](images/WindowsInsiderChannels.png)

有关详细信息，请参阅 Windows 博客 [上的 Windows 预览体验成员](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 频道介绍。

然后，选择 **"Windows 的活动**开发"，选择是希望接收 **开发人员** 频道还是 **Beta 渠道** 版本，并查看计划条款。

选择 **">立即重启** 以完成。 重启设备后，转到"设置>更新& **安全>检查** 更新，获取最新内部版本。

### 使用0x80070490更新错误
如果在开发人员或 Beta 渠道0x80070490更新时遇到更新错误，请尝试以下短期方法。 这包括移动预览体验成员频道、选取更新，然后将预览体验成员频道移回。

#### 第一阶段 - 版本预览
1.  设置，更新&，Windows 预览体验计划，选择 **版本预览频道**。
2.  设置， &安全， Windows 更新， **检查更新**。 更新后，继续第二阶段。

#### 第二阶段 - 开发人员频道
1. 设置，更新&，Windows 预览体验计划，选择 **开发人员频道**。
2. 设置， &安全， Windows 更新， **检查更新**。

## FFU 下载和快速方向
若要使用已签名的 ffu 进行测试，首先需要先对设备进行飞行解锁，然后闪烁已签名的 Ffu。
1. 在电脑上：

    1. 从 下载 ffu 到电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 从 Microsoft store (ARC) 高级恢复配套设备： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) .
    
1. On HoloLens - Flight Unlock： Open **Settings**  >  **Update & Security**Windows Insider  >  **Program** then sign up， reboot device.

1. Flash FFU - 现在可以使用 ARC 对已进行飞行的 FFU 进行闪烁。

## 提供反馈并报告问题

请使用 [HoloLens](hololens-feedback.md) 上的"反馈中心"应用提供反馈并报告问题。 使用反馈中心可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。  应该以相同方式报告有关 HoloLens 中文和日文版本的问题。

> [!NOTE]
> 请务必接受询问您是否希望反馈中心访问"文档"文件夹的提示， (系统提示"是") 。 ****

## 针对开发人员的注意事项

欢迎和鼓励你尝试使用 HoloLens 预览体验成员版本开发应用程序。  请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 开始。 这些相同的说明与 HoloLens 的预览体验成员版本一致。  可以使用与 HoloLens Visual Studio相同的 Unity 版本和版本。

## 停止接收预览体验成员版本

如果你不再希望接收 Windows 全息版的预览体验成员版本，你可以选择在 HoloLens 运行生产版本时退出，或者可以使用高级恢复助手[](hololens-recovery.md)将设备恢复为非预览体验成员版本的 Windows 全息版。

> [!CAUTION]
> 存在一个已知问题，即手动重新安装新的预览版后从 Insider Preview 版本取消注册的用户将遇到蓝屏。 之后，他们必须手动恢复设备。 有关是否将受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。

若要验证 HoloLens 是否正在运行生产内部版本，

1. 转到 **">系统>设置"，** 并查找内部版本号。

1. [请参阅生产内部版本号发行说明](hololens-release-notes.md)。

若要选择退出预览体验成员版本：

1. 在运行生产内部测试的 HoloLens 上，转到"设置>更新& Windows 预览体验计划 **>"，** 然后选择"停止预览**体验成员版本"。**

1. 按照说明选择退出设备。
