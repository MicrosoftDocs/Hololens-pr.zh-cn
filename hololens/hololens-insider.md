---
title: Microsoft HoloLens 的 Insider Preview
description: 开始使用预览体验计划是很简单的，以便为 HoloLens 的下一个主要操作系统更新提供有价值的反馈。
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
ms.date: 11/10/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 260b195a18ecb7fe05d819fcd3e86d56fc2022bf
ms.sourcegitcommit: 74e9989240dc0c324df35e8651b2f307f9d42148
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2020
ms.locfileid: "11201336"
---
# Microsoft HoloLens 的 Insider Preview

欢迎使用适用于 HoloLens 的最新预览体验计划预览版！ 这是一种非常简单的功能 [，可提供](hololens-insider.md#start-receiving-insider-builds) 针对 HoloLens 的下一个主要操作系统更新的宝贵反馈。

## Windows 预览体验计划发行说明

我们最近发布了所有 Windows 预览体验计划功能。 由于所有这些功能现在均可使用，我们建议你阅读我们的 [发行说明](hololens-release-notes.md) ，查看我们的所有最新功能。 继续在此处查看，了解我们何时开始外部测试版新的激动人心的功能来试用！

## 开始接收 Insider 内部版本

> [!NOTE]
> 如果您最近未进行更新，请重启设备以更新状态并获取最新版本。
> - "重新启动设备" 语音命令的效果很好。 
> - 您也可以选择 "设置/Windows 预览体验计划" 中的 "重新启动" 按钮。
>
> 我们在可能遇到的后端遇到错误，这将使你恢复进度。

在 HoloLens 2 设备上，转到 "**设置**"  >  **更新 & 安全**  >  **Windows 预览体验计划**"，然后选择"**开始**"。 将用于注册的帐户链接到 Windows 预览体验成员。

Windows 预览体验成员现在正在移至频道。 **快速**环将成为**开发频道**，**慢速**环将成为**Beta 通道**，并且 "**发布预览**" 环将成为 "**发布" 预览频道**。 映射如下所示：

![Windows 预览体验计划频道说明](images/WindowsInsiderChannels.png)

有关详细信息，请参阅 Windows 博客上的 [Windows 预览体验成员频道简介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 。

然后，选择 " **Windows 的活动开发**"，选择是要接收 **开发渠道** 还是 **Beta 频道** 内部版本，并查看计划条款。

选择 " **确认" > "立即重启** " 完成。 重新启动设备后，转到 " **设置" > 更新 & 安全 > 检查更新** 以获取最新版本。

## FFU 下载和快闪路线
若要使用带流量签名的 ffu 进行测试，首先必须在闪烁已签名的 ffu 之前，再将设备解锁。
1. 在 PC 上：

    1. 将 ffu 下载到电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。
    
    1. 从 Microsoft Store 安装 ARC (高级恢复配套) ： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
    
1. 在 HoloLens-航班解锁：打开**设置**  >  **更新 & 安全**  >  **Windows 预览体验计划**，然后注册，重新启动设备。

1. Flash FFU-现在，你可以使用 ARC 对已签名的 FFU 进行闪烁。

## 提供反馈和报告问题

请使用 HoloLens 上 [的 "反馈中心" 应用](hololens-feedback.md) 提供反馈和报告问题。 使用 "反馈中心" 可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。  必须以相同的方式报告与中文和日语版本的 HoloLens 有关的问题。

> [!NOTE]
> 请务必接受询问是否希望 "反馈中心" 访问你的 "文档" 文件夹的提示 (在出现提示时选择 **"是"**) 。

## 适用于开发人员的备注

欢迎和鼓励你尝试使用 HoloLens 的预览体验成员版本来开发应用程序。  请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 以开始使用。 这些相同的说明适用于 HoloLens 的预览体验计划版本。  你可以使用你已用于 HoloLens 开发的 Unity 和 Visual Studio 的相同版本。

## 停止接收 Insider 内部版本

如果您不想再收到 Windows 全息版的预览体验计划，则可以在 HoloLens 运行生产内部版本时选择退出，也可以使用高级恢复助理将 [设备恢复到](hololens-recovery.md) 非预览体验的 windows 全息版。

> [!CAUTION]
> 在手动重新安装新预览版后，从预览体验计划版本注册的用户将遇到蓝屏问题。 之后，他们必须手动恢复其设备。 有关如果你受到影响或不受影响的详细信息，请查看有关此 [已知问题](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的详细信息。

若要验证 HoloLens 是否正在运行生产内部版本，请执行以下操作：

1. 转到 " **设置" > "系统 >**"，然后找到内部版本号。

1. [请参阅生产内部版本号的发行说明](hololens-release-notes.md)。

若要退出预览体验计划内部版本，请执行以下操作：

1. 在运行生产版本的 HoloLens 上，转到 " **设置" > 更新 Windows 预览体验计划 & 安全 >**，然后选择 " **停止预览体验成员版本**"。

1. 按照说明选择退出您的设备。
