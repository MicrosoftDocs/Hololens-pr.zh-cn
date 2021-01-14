---
title: Microsoft HoloLens 内部预览版
description: 开始使用预览体验成员版本并为 HoloLens 的下一个主要操作系统更新提供有价值的反馈非常简单。
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
ms.date: 1/13/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 06c3faf573adabe158a72a66fc4b8a45afec48fb
ms.sourcegitcommit: e26aa9059a7d8e73914205e80a89ea9637926e74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2021
ms.locfileid: "11269393"
---
# Microsoft HoloLens 内部预览版

欢迎使用 HoloLens 的最新 Insider Preview 版本！ 开始操作非常简单，并为[](hololens-insider.md#start-receiving-insider-builds)HoloLens 的下一个主要操作系统更新提供有价值的反馈。

## Windows 预览体验成员发行说明

我们希望再次开始向 Windows 预览体验成员提供新功能。 我们将测试到开发人员频道获取最新更新。 我们将继续更新此页面，因为我们向 Windows 预览体验成员版本添加更多功能和更新。  感到兴奋并准备好将这些更新融合到你的现实中。 

| 功能名称                                              | 简短说明                                                                      | 在内部版本可用 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------|--------------------|
| [新版 Microsoft Edge](#introducing-the-new-microsoft-edge) | 新的基于 Chromium 的 Microsoft Edge 现在可用于 HoloLens 2                         | 20279.1006 |
| ["新建设置"应用](#new-settings-app)                     | 旧"设置"应用将替换为具有新功能和设置的更新版本 | 20279.1006 |
| [默认应用选取器](#default-app-picker)                 | 选择应针对每个文件或链接类型启动的应用                                      | 20279.1006 |
| [Office Web 应用](#office-web-app)                         | Office Web 应用的快捷方式现在列在"所有应用"中                                   | 20279.1006 |
| [轻扫以键入](#swipe-to-type)                           | 使用手指尖在全息键盘上"轻扫"字词                        | 20279.1006 |

### 引入新的 Microsoft Edge

![旧 Microsoft Edge 徽标到新 Microsoft Edge 徽标的动画](images/new-edge.gif)

新的 Microsoft Edge [采用 Chromium](https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/) 开放源代码项目，为客户创建更好的兼容性，减少 Web 开发人员的 Web 碎片。 

通过此预览体验成员预览版，HoloLens 2 客户首次可以使用新的 Microsoft Edge！ 虽然新 Microsoft Edge 最终将替换 HoloLens 2 上的旧版 Microsoft Edge，但预览体验成员目前可以使用这两种浏览器。 Please share feedback and bugs with our team via the **Send Feedback** feature in the new Microsoft Edge or via [Feedback Hub.](hololens-feedback.md)

![新 Microsoft Edge 屏幕截图](images/new-edge-ui.png)

#### 启动新的 Microsoft Edge

预览体验成员可以使用两个版本的 Microsoft Edge：新的 Microsoft Edge 新 Microsoft Edge 图标 (由蓝绿色旋转图标) 表示，旧 Microsoft Edge (由白色 ![ "e"图标) 表示。 ](images/new_edge_logo.png) 新的 Microsoft Edge 固定到"开始"菜单，将在激活 Web 链接时自动启动。 如果你想要还原为使用旧版 Microsoft Edge 作为默认 Web 浏览器，请参阅下面的说明 [重置默认应用](#default-app-picker)。

> [!NOTE]
> 当你首次在 HoloLens 2 上启动新的 Microsoft Edge 时，你的设置和数据将导入旧版 Microsoft Edge。 如果在启动新的 Microsoft Edge 后继续使用旧版 Microsoft Edge，则新数据将不会从旧版 Microsoft Edge 同步到新的 Microsoft Edge。

#### 配置新 Microsoft Edge 的策略设置

新版 Microsoft Edge 在 HoloLens 2 上为 IT 专业人员提供了一组比以前适用于旧版 Microsoft Edge 的更为广泛的浏览器策略。 

下面是一些有用的资源，有助于详细了解如何管理新 Microsoft Edge 的策略设置：
- [使用 Microsoft Intune 配置 Microsoft Edge 策略设置](https://docs.microsoft.com/deployedge/configure-edge-with-intune)
- [Microsoft Edge 旧版到 Microsoft Edge 策略映射](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge)
- [Google Chrome 到 Microsoft Edge 策略映射](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-chrome-to-newedge)
- [完整的 Microsoft Edge 企业版文档](https://docs.microsoft.com/deployedge/)

> [!IMPORTANT]
> 由于新的 Microsoft Edge 支持大量浏览器策略，团队无法保证每个新策略都适用于 HoloLens 2。 但是，我们已经测试并确认 HoloLens 2 上以前支持的每个旧 Microsoft Edge 策略的新 Microsoft Edge 等效项可以正常工作。 请参阅 [Microsoft Edge 旧版到 Microsoft Edge](https://docs.microsoft.com/deployedge/microsoft-edge-policy-map-legacy-to-newedge) 策略映射，查找与 HoloLens 2 一起使用的每个旧版 Microsoft Edge 浏览器策略的新 Microsoft Edge 等效项。
>
> 我们了解至少有两个新的 Microsoft Edge 策略 *将不能* 与 HoloLens 2 一起使用：
> - EnterpriseModeSiteList
> - EnterpriseSiteListServiceURL

#### HoloLens 2 上新 Microsoft Edge 的预计功能

由于新的 Microsoft Edge 是具有新的 UWP 适配器层的本机 Win32 应用，允许它在仅 UWP 设备（如 HoloLens 2）上运行，因此某些功能可能不会立即可用。 我们将支持未来几个月的新方案和功能，因此请查看此空间了解最新信息。

**应用场景和功能应能正常工作：**
- 首次运行体验、登录配置文件和同步
- 网站应按预期呈现和行为
- 大多数浏览器功能 (收藏夹、历史记录等) 应正常工作
- 深色模式
- 将 Web 应用安装到设备
- 安装扩展 (请告知我们，如果你使用的任何扩展在 HoloLens 2) 
- 查看和标记 PDF
- 单个浏览器窗口中的空间声音
- 浏览器的自动和手动更新
- 使用"保存到 PDF"选项 (打印菜单中保存 PDF) 

**即将推出方案和功能：**
- WebXR 和 360 Viewer 扩展
- 在环境中跨多个窗口浏览时，内容还原以更正窗口
- 具有同时音频流的多个窗口的空间声音
- 通过浏览器通过视频、混合现实捕获或屏幕共享功能加入 Microsoft Teams (通过音频加入通话效果) 
- "查看它，说出它"
- 打印

**热门浏览器问题：**
- 重置设备将删除新的 Microsoft Edge
- 全息键盘中的放大镜预览显示不正确的内容

### "新建设置"应用

在此版本中，我们将引入新版本的"设置"应用。 新的设置应用包括以下领域的 HoloLens 2 的新功能和扩展设置：输入/输出音频设备、单个应用音量、电源和睡眠、以太网适配器、轻松使用、飞行模式和默认应用。

> [!NOTE]
> 由于新的"设置"应用不同于旧式"设置"应用，因此更新时将删除之前围绕环境放置的任何"设置"窗口。

!["新建设置"应用主页](images/new-settings-app.png)

**新功能和设置**
- 设置搜索：使用关键字或设置名称从"设置"主页搜索设置
- 声音：
  - 输入和输出音频设备：独立选择输入和输出音频设备 (例如，通过 Bluetooth 耳机收听音频或使用 USB-C 麦克风进行音频输入) 。 注意：Bluetooth HoloLens 2 不支持麦克风。
  - 应用量：独立调整每个应用的音量
- 节电模式：手动启用节电模式或设置节电模式自动打开的电池阈值
- 电源&睡眠：选择设备在一段时间不活动后应何时进入睡眠状态
- USB：默认情况下可以禁用 USB 连接
- Internet &网络：
  - USB-C 以太网适配器现在将显示在网络和 Internet &中
  - USB-C 以太网适配器设置现已可用，包括其 IP 地址
  - 现在可以在 HoloLens 2 上启用飞行模式
- 应用：你可以重置用于文件和链接类型的默认应用。 有关详细信息 [，请参阅](#default-app-picker) 默认应用选取器。
- 轻松使用：更改文本大小和一些视觉效果

**已知问题**
- 以前放置的"设置"窗口将被删除 (请参阅上面的) 
- 访问"通知"页可能会崩溃"设置"应用 (调查) 
- 以太网页面当前不会显示 (即将修复) 
- 新 Microsoft Edge 的电池使用情况可能不准确，因为其性质是 UWP 适配器层支持的 Win32 桌面应用程序， (预计) 

### 默认应用选取器

激活超链接或打开具有多个支持超链接的已安装应用的文件类型时，你将看到一个新窗口打开，提示你选择应处理文件或链接类型的已安装应用。 在此窗口中，还可以选择让所选应用处理文件或链接类型"一次"或"始终"。 

![应用选取器窗口](images/default-app-picker.png)

如果你选择"始终"，但后来想要更改哪个应用处理特定文件或链接类型，可以在"设置"或"应用"中重置> **默认值**。 滚动到页面底部，然后选择"文件类型的默认应用****"和/或"链接类型的默认应用"下的"清除"按钮。 与桌面电脑的类似设置不同，不能重置单个文件类型默认值。

### Office Web 应用

Office Web 应用已添加到"开始"菜单中的"所有应用程序"列表中。 还可以将此 Web 应用固定到"开始"页面或将其卸载。 由于这是一个 Web 应用，因此其功能与通过访问体验完全匹配 https://www.office.com 。 仅在 HoloLens 2 具有活动的 Internet 连接时，Office Web 应用功能才可用。

### 轻扫以键入

一些客户发现通过轻扫要键入的单词的形状，在虚拟键盘上"键入"速度更快，我们正在预览全息键盘的此功能。 通过通过全息键盘的平面传递手指的尖角，轻扫该单词的形状，然后从键盘平面撤消手指的尖角，可以一次轻扫一个单词。 通过从键盘删除单词之间的手指，无需按空格键，即可轻扫后续单词。 如果你看到手指在键盘上的移动后看到轻扫轨迹，你将知道该功能正在工作。

请注意，此功能可能很难使用和掌握，因为全息键盘的性质，与移动电话显示屏不同，你无法抵御手指 (因此) 。 我们正在评估此功能以公开发布，因此您的反馈非常重要;无论你发现此功能有用还是有反馈反馈，请通过反馈中心 [告诉我们](hololens-feedback.md)。





## 开始接收预览体验成员版本

> [!NOTE]
> 如果最近尚未更新，请重启设备以更新状态并获取最新内部版本。
> - "重新启动设备"语音命令运行正常。 
> - 还可以选择"设置/Windows 预览体验计划"中的"重启"按钮。
>
> 后端有一个你可能会遇到的 Bug，这样你才能重新进入轨道。

在 HoloLens 2 设备上 **，转到&** Windows 预览  >  ****  >  **体验计划**"设置更新"，然后选择 **"开始使用"。** 链接你用于注册为 Windows 预览体验成员的帐户。

Windows 预览体验成员现在迁移到频道。 快速**圈**将变为**开发人员频道**，慢圈将成为**** **Beta**渠道，而发布预览圈将成为******发布预览频道**。 该映射如下所示：

![Windows 预览体验成员频道说明](images/WindowsInsiderChannels.png)

有关详细信息，请参阅 Windows 博客 [上的 Windows 预览](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 体验成员频道介绍。

然后，选择 **"Windows**的活动开发"，选择是希望接收 **开发人员** 频道还是 **Beta 渠道** 版本，并查看计划条款。

选择 **">立即重启** 以完成。 重启设备后，转到"设置>更新& **安全>检查** 更新，获取最新内部版本。

## FFU 下载和快速方向
若要使用已签名的 Ffu 进行测试，首先需要先对设备进行解锁，然后才能闪烁已进行测试的已签名 ffu。
1. 在电脑上：

    1. 从 下载 ffu 到你的电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 从 Microsoft store (ARC) 高级恢复配套设备： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. 在 HoloLens - Flight Unlock： Open **Settings**  >  **Update & Security**Windows Insider  >  **Program** then sign up， reboot device.

1. Flash FFU - 现在可以使用 ARC 对已进行飞行的 FFU 进行闪烁。

## 提供反馈并报告问题

请使用 [HoloLens](hololens-feedback.md) 上的"反馈中心"应用提供反馈并报告问题。 使用反馈中心可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。  应以相同方式报告与 HoloLens 的中文和日文版本有关的问题。

> [!NOTE]
> 请务必接受询问您是否希望反馈中心访问"文档"文件夹的提示， (系统提示"是") 。 ****

## 开发人员注意事项

欢迎并鼓励你尝试使用 HoloLens 预览体验成员版本开发应用程序。  请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 开始。 这些相同的说明与 HoloLens 的预览体验成员版本一致。  可以使用与 HoloLens Visual Studio相同的 Unity 版本和版本。

## 停止接收预览体验成员内部版本

如果你不再希望接收 Windows 全息版的预览体验成员版本，你可以选择在 HoloLens 运行生产版本时退出，或者可以使用高级恢复助手[](hololens-recovery.md)将设备恢复到非预览体验成员版本的 Windows 全息版。

> [!CAUTION]
> 存在一个已知问题，即手动重新安装新的预览版本后从 Insider Preview 版本取消注册的用户将遇到蓝屏。 之后，他们必须手动恢复其设备。 有关你是否受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)。

若要验证 HoloLens 是否正在运行生产版本：

1. 转到" **系统>设置>"，** 并查找内部版本编号。

1. [有关生产内部版本号，请参阅发行说明](hololens-release-notes.md)。

若要选择退出预览体验成员版本：

1. 在运行生产内部版本 HoloLens 上，转到"设置>更新& Windows 预览体验>计划"，**然后选择**"停止预览**体验成员版本"。**

1. 按照说明选择退出设备。
