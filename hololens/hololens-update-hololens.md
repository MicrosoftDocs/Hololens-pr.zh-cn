---
title: 更新 HoloLens 2
description: 了解如何检查您 HoloLens 的内部版本号，随时更新设备更新，加入预览体验计划，并回滚更新。
keywords: 操作说明，更新，回滚，HoloLens，检查生成，生成号
ms.prod: hololens
ms.sitesec: library
author: qianw211
ms.author: v-beehanson
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/11/2021
audience: ITPro
ms.reviewer: ''
manager: sekerawa
appliesto:
- HoloLens 2
ms.openlocfilehash: 080fb184c7eca3fdb978e860a29764f5012a179e
ms.sourcegitcommit: f105a770814ccd61e88b650448902a03c95b7a3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2021
ms.locfileid: "130151688"
---
# <a name="update-hololens-2"></a>更新 HoloLens 2

## <a name="overview"></a>概述

我们始终致力于处理新功能、bug 修复和安全更新。 当这些更新准备就绪时，你将收到通知。

根据你的偏好，你的 HoloLens 将在每次接通电源、连接到 Internet，甚至是备用时，自动下载和安装系统更新。

若要确保始终更新 HoloLens，请将其与附带的充电器连接起来。 你还希望 HoloLens 连接到 internet。 这样，它将自动下载和安装系统更新。 

利用 Windows 更新服务，你将控制更新过程的多个方面，如哪些设备将在什么时间获取更新。 此控件非常有用，因为可以将更新推出到 HoloLens 设备的子集进行测试。 然后，将更新推出到其他更新。 或是为不同类型的更新制定不同的更新计划。

## <a name="types-of-updates"></a>更新类型

对于 HoloLens，你可以自动管理两种类型的更新。

- 功能更新：每年发布两次。
- 质量更新：包括关键安全更新。 它们按月或按需发布。

使用 **更新** / **AllowAutoUpdate** 管理更新的扫描、下载和安装。 

## <a name="scheduling-updates"></a>计划更新

你还可以设置更新计划。 它可以在特定日期或每天的特定时间进行。 例如，在下午5点或在活动时间之外。

最后是关于规划更新策略的几个词。 我们支持更新延迟，以便你可以决定在 Microsoft 发布更新后要等待多长时间才能在设备上安装该更新。

有时候，公司喜欢首先尝试所有新功能，以确保一切正常，并熟悉新的更新，使其支持团队做好准备。 一旦他们确认一切都好，就会将更新推广到整个公司。 通过将设备的子集与不同的延迟策略（称为更新环）相关联，可以协调组织的更新推出策略。

## <a name="hololens-update-tools"></a>HoloLens 更新工具

本部分将指导你完成以下操作的 HoloLens 工具：

- 检查更新
- 手动更新 HoloLens
- 查看当前操作系统版本 (内部版本号) 
- 回退到较旧的更新

### <a name="check-for-updates-and-manually-update"></a>检查更新并手动更新

你可以随时在 "设置" 中检查更新。  若要查看可用的更新并检查新的更新，请执行以下操作：

1. 打开“设置”应用  。
1. 导航到 "**更新 & 安全**  >  **Windows 更新**"。
1. 选择“检查更新”。

如果更新可用，则会开始下载新版本。 下载完成后，选择 " **立即重新启动** " 按钮以触发安装。 如果设备低于40% 且未接通电源，则重新启动将不会开始安装更新。

HoloLens 安装更新时，它会显示旋转齿轮和进度指示器。 请勿在此时间关闭 HoloLens。 完成安装后，它将自动重新启动。

HoloLens 一次应用一个更新。  如果 HoloLens 的版本超过了最新版本，则可能需要多次运行更新过程，以使其完全保持最新状态。

### <a name="check-your-operating-system-version-build-number"></a>检查操作系统版本 (生成号) 

可以通过打开 **设置** 并选择 "**系统** 关于" 来验证系统版本号 (生成号)  >  。

### <a name="go-back-to-a-previous-version"></a>返回到以前的版本

在某些情况下，你可能希望返回到 HoloLens 软件的以前版本。 建议的步骤如下：

1. 请联系支持人员以查看他们能否解决你的问题。
    1. 确保启用了 **可选** 的或 **完整** 的遥测-这会使你的 bug 更具可操作性，并使工程师能够更轻松地进行诊断。
    1. 在 [文件反馈](hololens-feedback.md) 中尽可能地说明。 记下标题，或使用 "共享" 功能，以便可以与支持人员共享 bug。
    1. 联系 [支持人员](https://aka.ms/hlsupport)。 如果你的问题是需要通过返回到以前的版本来解决的问题，则可以提供 FFU 来闪存设备。

1. 或者，你可以[通过高级恢复助理刷新你的 HoloLens 2](hololens-recovery.md#clean-reflash-the-device)。
    1.  选择要刷新到的版本： 
        1.  您可以下载[最新的 HoloLens 2 版本](https://aka.ms/hololens2download)。
        1.  可以使用 ARC 宿主的默认生成。
        1.  你可以使用提供的生成支持。

> [!NOTE]
> 返回到早期版本会删除你的个人文件和设置。

此外，如果想要停留在当前安装的版本中，还可以手动 [暂停更新](hololens-updates.md#pause-updates-via-device)。 这将使工程团队时间来解决此问题。

## <a name="windows-insider-program-on-hololens"></a>WindowsHoloLens 上的预览体验计划

想要查看 HoloLens 中的最新功能？  如果是，请加入 Windows 预览体验计划;你将可以访问 HoloLens 软件更新的预览版本，然后将其提供给公众使用。

[获取 Microsoft HoloLens Windows 预览体验预览](hololens-insider.md)。