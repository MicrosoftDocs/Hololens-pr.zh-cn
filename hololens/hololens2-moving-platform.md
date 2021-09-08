---
title: HoloLens 2 移动平台模式
description: 如何在移动平台上使用 HoloLens
keywords: 移动平台, 动态运动, hololens, 移动平台模式
author: evmill
ms.author: v-evmill
ms.reviewer: yabahman
ms.date: 8/10/2021
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: high
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: a0717524cd1f762c92a5b821ae90acb8474dafd2
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "123190389"
---
# <a name="moving-platform-mode-on-low-dynamic-motion-moving-platforms"></a>低动态运动移动平台上的移动平台模式

在预览体验版本 20348.1411 中，我们在 HoloLens 2 上增加了对在低动态运动移动平台上进行跟踪的 beta 版支持。 安装该版本并启用移动平台模式后，你能够在以前无法访问的环境（如大型船只和大型海船）中使用 HoloLens 2。 目前，该功能的目标是仅启用这些特定的移动平台。 虽然你可以随意地尝试在其他环境中使用该功能，但该功能首先侧重于增加对这些环境的支持。

> [!NOTE]
> 此功能目前仅通过 [Windows 预览体验成员](hololens-insider.md)提供。

![移动平台示例。](./images/mpm-compare.gif)

本文介绍：

1. [为什么必需移动平台](#why-moving-platform-mode-is-necessary)
1. [启用移动平台模式](#enabling-moving-platform-mode)

## <a name="why-moving-platform-mode-is-necessary"></a>为什么必需移动平台模式

HoloLens 需要能够以[六自由度](https://en.wikipedia.org/wiki/Six_degrees_of_freedom)（X、Y、Z、平移和翻滚、俯仰、偏航旋转）跟踪你的头部位置，以便显示稳定的全息影像。 为此，HoloLens 跟踪来自两个不同源的两条相似的信息：

1. 可见光相机 - 用于跟踪环境，例如在其中使用 HoloLens 的物理房间
1. 惯性测量单元 (IMU) - 由加速度计、陀螺仪和磁力计组成，用于跟踪头部相对于地球的运动和方向

来自这两个源的信息被合成，以低延迟和足够高的频率跟踪你的头部位置，从而呈现平滑的全息影像。

然而，这种方法依赖于一个关键的假设；环境（由摄像机跟踪）相对于地球保持静止（IMU 可以对其进行测量）。 如果情况并非如此，就像在水中的船上，来自两个源的信息可能会相互冲突，导致跟踪器迷失方向。 此冲突会产生不正确的位置信息，导致全息影像模糊（甚至跟踪丢失）。

移动平台模式解决了此问题。 启用移动平台模式时，这是对跟踪器的提示，即我们不能指望传感器输入在任何时候都彼此完全一致。 相反，在我们能够使用 IMU 输入之前，我们需要更多地依赖于视觉跟踪，快速识别不一致的惯性运动数据，并相应地筛选掉这些数据。

## <a name="supported-environments-and-known-limitations"></a>支持的环境和已知限制

虽然移动平台模式是为了智能处理惯性数据和视觉数据冲突的情况而开发的，但它目前仅限于处于低动态运动的大型船舶。 这意味着肯定存在限制和不受支持的场景。

### <a name="known-limitations"></a>已知限制

- 移动平台模式 (MPM) 唯一支持的环境是处于低动态运动的大型船舶。 换句话说，许多常见的环境/情况由于其高频率运动和高水平的加速和[急动](https://en.wikipedia.org/wiki/Jerk_(physics))而尚未得到支持。 例如：飞机、火车、汽车、自行车、客车、小船、电梯等。
- 启用了 MPM 时，全息影像可能会轻微抖动（尤其是在波涛汹涌的水面上）。
- 用户可以随意地尝试在不受支持的环境中使用 MPM，但如果设备能够在不受支持的空间中保持跟踪，用户可能会遇到不良的副作用。 例如，使用 MPM 时，用户可能会发现，可以在正在楼层间移动的电梯里使用，而这在以前是不可能的。 遗憾的是，虽然 MPM 允许设备保持跟踪，但它目前不处理地图管理。 因此，用户会发现，在电梯里改变楼层会导致设备混淆上下楼层，对地图质量产生负面影响。

## <a name="prerequisites"></a>必备条件

对移动平台模式的 Beta 版支持仅需几个先决条件：

1. 安装版本 20348.1411 或更高版本，方法是[通过 ARC 刷新最新的预览体验版本](hololens-insider.md#ffu-download-and-flash-directions)，或者[注册并更新设备](hololens-insider.md#start-receiving-insider-builds)。

   > [!NOTE]
   > 此版本当前仅在[预览体验成员开发频道](hololens-insider.md#start-receiving-insider-builds)上提供。

2. 启用[开发人员模式和设备门户](/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)

## <a name="enabling-moving-platform-mode"></a>启用移动平台模式

若要启用移动平台模式，请先[启用设备门户](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。

1. 选择左侧菜单中的“系统”可折叠面板

   ![第一张图像。](.\images\moving-platform-1w.png)

2. 选择“移动平台模式”页，并选中“移动平台模式”复选框 

    ![第二张图像。](.\images\moving-platform-2z.png)

3. 出现警告提示时，选择“确定”

   ![第三张图像。](.\images\moving-platform-3w.png)

4. 重启设备（这可通过设备门户右上角的“电源”菜单完成，也可以通过发出以下语音命令&quot;重启设备&quot;来完成），然后选择&quot;是&quot;。

   ![第四张图像。](.\images\moving-platform-4z.png)

如果在设备门户中看不到“移动平台模式”选项，则很可能意味着你尚未使用正确的版本。 请参阅[先决条件](#prerequisites)部分。

## <a name="reporting-issues"></a>报告问题

如上所述，此功能处于 beta 阶段，仅在开发人员模式下可用，这意味着你可能会遇到问题。 如果遇到问题，请通过以下方式帮助我们调查和改进产品

1. 通过[反馈中心](hololens-feedback.md)在“全息影像准确性、稳定性和可靠性”类别下报告问题，包括：
    1. 问题的描述，包括预期的行为和出现的行为
    1. 此问题的混合现实[视频捕获](holographic-photos-and-videos.md#capture-a-mixed-reality-video)
2.  通过 [https://aka.ms/hlsupport](https://aka.ms/hlsupport) 创建支持案例并共享反馈中心 URL，以便我们在遇到后续问题时可以与你联系