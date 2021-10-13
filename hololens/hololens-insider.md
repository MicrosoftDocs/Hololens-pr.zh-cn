---
title: 适用于 Microsoft HoloLens 的 Insider Preview
description: 了解如何开始使用预览体验内部版本，并为我们的下一次主要操作系统更新提供有价值的HoloLens。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 10/12/2021
ms.reviewer: ''
manager: ranjibb
appliesto:
- HoloLens 2
ms.openlocfilehash: 080eb5949bc80d1ce922d57f099c375668f5633f
ms.sourcegitcommit: 9574db58592b7302bd2386bdf7fda3f6721de818
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2021
ms.locfileid: "129924366"
---
# <a name="insider-preview-for-microsoft-hololens"></a>适用于 Microsoft HoloLens 的 Insider Preview

欢迎使用最新的 Insider Preview 内部版本HoloLens！ 只需开始操作[，](hololens-insider.md#start-receiving-insider-builds)并为下一次主要操作系统更新提供有价值的反馈，HoloLens。

## <a name="windows-insider-release-notes"></a>Windows预览体验成员发行说明

我们很高兴我们最新的所有预览体验成员功能都公开了！ 若要了解这些内容，请查看发行 [说明页](hololens-release-notes.md)

## <a name="start-receiving-insider-builds"></a>开始接收预览体验内部版本

> [!NOTE]
> 如果最近尚未更新，请重启设备以更新状态并获取最新生成。
>
> - "重新启动设备"语音命令运行良好。
> - 还可以选择"重启"按钮，设置/Windows 会员计划。
>
> 我们在后端有一个 bug，你可能遇到了该 bug，这可让你重新进入轨道。

在设备上HoloLens 2 **转到"更新**  >  **设置"&"Windows 会员计划"**  >  开始 **"。** 链接用于注册为预览体验成员Windows帐户。

> [!NOTE]
> 若要在预览体验成员内部版本中注册设备，需要启用可选遥测。 如果尚未这样做，请打开 设置应用，选择"隐私诊断&  ->  **反馈"，然后选择"** 可选 **诊断数据"。**

Windows预览体验成员现在迁移到频道。 快速 **通道** 将成为 **开发通道**，慢速通道 **将成为** Beta 版频道通道，发布预览通道将成为 **发布预览通道**。 该映射如下所示：

![WindowsInsider Channels 说明。](images/WindowsInsiderChannels.png)

有关详细信息，请参阅博客[上的预览Windows](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)预览体验Windows介绍。
然后 **，选择**"Windows开发"，选择要接收 **开发** 通道还是Beta 版频道版本，并查看计划条款。 
选择 **">立即重启** "以完成操作。 重启设备后，转到"更新设置 >"&**安全性>"检查更新**"获取最新生成。

### <a name="update-error-0x80070490-work-around"></a>更新错误0x80070490问题

如果在开发或 Beta 0x80070490更新时遇到更新错误，请尝试以下短期方法。 这涉及到移动预览体验成员通道、选取更新，然后将 Insider 通道移回。

#### <a name="stage-one---release-preview"></a>第一阶段 - 发布预览版

1. 设置"更新&安全性"，Windows 会员计划，选择"**发布预览通道"。**

2. 设置、更新&安全性、Windows更新、**检查更新**。 更新后，继续进入阶段 2。

#### <a name="stage-two---dev-channel"></a>阶段 2 - 开发通道

1. 设置"更新&安全性"，Windows 会员计划，选择"**开发通道"。**

2. 设置、更新&安全性、Windows更新、**检查更新**。

## <a name="ffu-download-and-flash-directions"></a>FFU 下载和闪存说明

若要使用已签署航班的 ffu 进行测试，首先需要先对设备进行飞行解锁，然后刷出已签署航班的 ffu。

1. 在电脑上：
    1. 从 将 ffu 下载到电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。

    1. 从 (安装 ARC) 高级恢复助手 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) Microsoft Store：。

1. 在HoloLens - 航班解锁 **：打开** 设置  >  **Update & Security Windows 会员计划，**  >  然后注册、重启设备。

1. Flash FFU - 现在可以使用 ARC 刷出航班签名的 FFU。

### <a name="provide-feedback-and-report-issues"></a>提供反馈并报告问题

请使用[反馈中心应用](hololens-feedback.md)HoloLens提供反馈并报告问题。 使用反馈中心可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。  应该以相同的方式报告HoloLens日文版本的问题。

> [!NOTE]
> 请务必接受提示，询问你是否希望反馈中心 Documents 文件夹， (系统提示时选择"是) 。 

## <a name="note-for-developers"></a>开发人员说明

欢迎并鼓励你尝试使用预览体验成员内部版本开发HoloLens。  请查看开发人员[HoloLens](https://developer.microsoft.com/windows/mixed-reality/development)文档开始。 这些相同的说明与预览体验成员内部版本HoloLens。  可以使用已用于开发Visual Studio Unity 和 HoloLens版本。

## <a name="stop-receiving-insider-builds"></a>停止接收预览体验内部版本

如果不再想要接收 Windows Holographic 的预览体验内部版本，可以在 HoloLens 运行生产内部版本时选择退出，或者可以使用高级恢复助手将设备恢复到[](hololens-recovery.md)Windows Holographic 的非 Insider 版本。

> [!CAUTION]
> 存在一个已知问题：在手动重新安装新的预览版本后，从 Insider Preview 中取消注册的用户将遇到蓝屏。 之后，他们必须手动恢复其设备。 有关是否受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。

若要验证HoloLens是否正在运行生产内部版本：

1. 转到 **"设置 >系统>关于"，** 并找到生成号。

1. [有关生产内部版本号，请参阅发行说明](hololens-release-notes.md)。

选择退出预览体验内部版本：

1. 在运行HoloLens生成时，转到"设置 >更新&**安全**> Windows 会员计划，然后选择"停止 **预览体验成员生成"。**

1. 按照说明选择退出设备。
