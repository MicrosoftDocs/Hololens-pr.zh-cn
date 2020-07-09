---
title: Microsoft HoloLens 内部预览版
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
ms.date: 6/29/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: b054b61b269522d673be104ffbda9abc1bc85415
ms.sourcegitcommit: 168a7659420525e5f3e3088d7ce0b5e03c969029
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2020
ms.locfileid: "10860602"
---
# Microsoft HoloLens 内部预览版

欢迎使用适用于 HoloLens 的最新预览体验计划预览版！  这是一种非常简单的功能，可提供针对 HoloLens 的下一个主要操作系统更新的宝贵反馈。

Windows 预览体验成员现在正在移至频道。 **快速**环将成为**开发频道**，**慢速**环将成为**Beta 通道**，并且 "**发布预览**" 环将成为 "**发布" 预览频道**。 映射如下所示：

![Windows 预览体验计划频道说明](images/WindowsInsiderChannels.png)

有关详细信息，请执行以下操作： [Windows 博客条目](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)

## 开始接收 Insider 内部版本

在 HoloLens 2 设备上，转到 "**设置**"  ->  **更新 & 安全**  ->  **Windows 预览体验计划**"，然后选择"**开始**"。 将用于注册的帐户链接到 Windows 预览体验成员。

然后，选择 " **Windows 的活动开发**"，选择是要接收**开发渠道**还是**Beta 频道**内部版本，并查看计划条款。

选择 "**确认"-> "立即重启**" 完成操作。 重新启动设备后，转到 "**设置"-> 更新 & 安全 > 检查更新**以获取最新版本。

## 停止接收 Insider 内部版本

如果您不想再收到 Windows 全息版的预览体验计划，则可以在 HoloLens 运行生产内部版本时选择退出，也可以使用高级恢复助理将[设备恢复到](hololens-recovery.md)非预览体验的 windows 全息版。

> [!CAUTION]
> 在手动重新安装新预览版后，从预览体验计划版本注册的用户将遇到蓝屏问题。 之后，他们必须手动恢复其设备。 有关如果你受到影响或不受影响的详细信息，请查看有关此[已知问题](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的详细信息。

若要验证 HoloLens 是否正在运行生产内部版本，请执行以下操作：

1. 转到 "**设置" > "系统 >**"，然后找到内部版本号。
1. [请参阅生产内部版本号的发行说明。](hololens-release-notes.md)

若要退出预览体验计划内部版本，请执行以下操作：

1. 在运行生产版本的 HoloLens 上，转到 "**设置" > 更新 Windows 预览体验计划 & 安全 >**，然后选择 "**停止预览体验成员版本**"。
1. 按照说明选择退出您的设备。


## 提供反馈和报告问题

请使用 HoloLens 上[的 "反馈中心" 应用](hololens-feedback.md)提供反馈和报告问题。 使用 "反馈中心" 可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。  必须以相同的方式报告与中文和日语版本的 HoloLens 有关的问题。

> [!NOTE]
> 请确保接受询问您是否希望 "反馈中心" 访问您的 "文档" 文件夹的提示（在出现提示时选择 **"是"** ）。

## 适用于开发人员的备注

欢迎和鼓励你尝试使用 HoloLens 的预览体验成员版本来开发应用程序。  请查看[HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development)以开始使用。 这些相同的说明适用于 HoloLens 的预览体验计划版本。  你可以使用你已用于 HoloLens 开发的 Unity 和 Visual Studio 的相同版本。


## Windows 预览体验计划发行说明

从我们的[Windows 全息版2020更新](hololens-release-notes.md)版本，我们的所有版本预览功能现已推出。 请确保[更新 HoloLens](hololens-update-hololens.md)以获取所有最新功能。

我们将再次通过新功能再次更新此页面，因为我们将这些新功能发布给 Windows 预览体验成员内部版本。


### 自动目视位置支持

在 HoloLens 2 中，目视位置支持准确的全息图定位、舒适的查看体验和改进的显示质量。 眼位置将作为眼睛跟踪结果的一部分进行计算。 但是，这要求每个用户都可以通过目视跟踪校准，即使体验不需要目视的注视输入也是如此。

**自动目视位置（AEP）** 通过交互方式为用户计算眼睛位置支持这些方案。  自动目视位置在用户将设备置于设备上时自动从后台开始工作。 如果用户没有以前的目视跟踪校准，则在较小的处理时间后，自动目视的位置将开始向显示系统提供用户的目视位置。 此处理时间通常介于 20-60 秒之间。 用户数据不会保留在设备上，因此，如果用户关闭并重新放置设备或者设备重新启动或从睡眠中唤醒，则会重复此过程。  

当 uncalibrated 用户放在设备上时，有一些系统行为发生了自动目视定位功能。 Uncalibrated 用户指的是尚未经历过设备上的目视跟踪校准过程的人。

|     活动应用程序                           |     当前行为                                   |     来自 Windows 预览体验成员内部版本19041.1339 的行为 +                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     不支持注视的应用程序或全息外壳    |     将显示目视跟踪校准提示。    |     不显示提示。                                                                                |
|     注视 "已启用" 应用                             |     将显示目视跟踪校准提示。    |     仅当应用程序访问眼睛注视流时，才会显示目视跟踪校准提示。     |

 如果用户从一个不支持注视的应用程序切换到一个访问注视数据的应用程序，则将显示校准提示。 将不会更改为 "现成的体验" 流程。 
 
对于需要眼睛眼数据或非常精确的全息图位置的体验，我们建议 uncalibrated 用户从目视跟踪校准提示中运行目视跟踪校准，或者从 "开始" 菜单启动 "设置" 应用，然后选择 "**系统 > 校准" > 目视校准 > "运行目视校准**"。

**已知问题**
1.  我们正在调查 "目视跟踪器驱动程序" 在较高内存负载下运行时可能会崩溃的问题。 目视跟踪驱动程序主机进程应自动恢复。

## FFU 下载和快闪路线
若要使用带流量签名的 ffu 进行测试，首先必须在闪烁已签名的 ffu 之前，再将设备解锁。
1. 在 PC 上
    1. 从以下计算机下载 ffu：[https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)
    1. 从 Microsoft Store 安装 ARC （高级恢复助理）：[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)
1. 在 HoloLens-航班解锁：打开**设置**  >  **更新 & 安全**  >  **Windows 预览体验计划**，然后注册，重新启动设备
1. Flash FFU-现在，你可以使用 ARC 对已签名的 FFU 进行闪烁
