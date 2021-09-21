---
title: 改善视觉质量和舒适度
description: 了解如何校准瞳孔间距 (IPD)，以改善 HoloLens 设备上的视觉效果。
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: 校准, 舒适, 视觉对象, 质量, ipd, HoloLens, Windows Mixed Reality, VR 头戴显示设备
ms.openlocfilehash: cdeef216cbf6d1fb165737ae194071c60b31146a
ms.sourcegitcommit: 20ea1ed37772655504ccb11a7e185ed19d85f336
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2021
ms.locfileid: "127833550"
---
# <a name="improve-visual-quality-and-comfort"></a>改善视觉质量和舒适度

在根据你自己的瞳距校准 HoloLens 2 和 HoloLens（第一代）后，体验效果会更好。

虽然两种设备都需要通过校准才能带来最佳的全息图观看体验，但它们所用的校准技术不同。  跳转到 [HoloLens 2 校准](#calibrating-your-hololens-2)或 [HoloLens（第一代）校准](#calibrating-your-hololens-1st-gen)。

## <a name="calibrating-your-hololens-2"></a>校准 HoloLens 2

HoloLens 2 使用眼球跟踪技术来改善你观看虚拟环境以及与虚拟环境互动的体验。 校准 HoloLens 2 可确保它能够准确地跟踪你的眼球（以及使用该设备的其他人的眼球）。 此外，它还有助于提高用户舒适度、进行全息影像对齐和实现手部跟踪。 校准后，会正确显示全息图，即使面罩在你的头上移动时也是如此。

在下列情况中，HoloLens 2 会提示用户校准设备：

- 用户首次使用设备
- 用户之前选择退出校准过程
- 用户上次使用设备时校准过程不成功
- 用户已删除其校准配置文件
- 设备将被关闭并重新打开，且上述任何情况都适用 

![调整到眼部的校准提示。](./images/07-et-adjust-for-your-eyes.png)

在此过程中，你需要注视一组目标（宝石）。 校准期间，你可以眨眼，但请尽量把注意力集中在宝石上，而不是盯着房间中的其他对象。  通过专注于这些宝石，HoloLens 可以了解你的眼部位置，以呈现全息世界。

![校准提示告诉用户保持头部静止不动并用眼睛跟随点。](./images/07-et-hold-head-still.png)

![带有 gem 示例的校准提示。](./images/08-et-gems.png)

![校准提示调整。](./images/09-et-adjusting.png)

如果校准成功，你将看到一个成功屏幕。  如果没有，请阅读有关[诊断校准失败](hololens2-display.md#troubleshooting)的详细信息。

![校准提示成功。](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a>共享设备或会话时校准

多个用户可以共用一台 HoloLens 2 设备，但不需要每个人都走一遍设备设置流程。 当新的用户首次将设备戴在头上时，HoloLens 2 会自动提示该用户进行视觉对象校准。 当之前校准过视觉对象的用户再次将设备戴在头上时，显示屏可无缝调整，为其提供高质量的舒适观看体验。  

### <a name="manually-starting-the-calibration-process"></a>手动启动校准过程

1. 使用开始手势打开[“开始”菜单](hololens2-basic-usage.md#start-gesture)。
1. 如果设置应用未固定到“开始”，请选择“所有应用”。
1. 选择“设置”，然后选择“系统” > “校准” > “眼部校准” > “运行眼部校准”。

   ![“设置”应用，显示“运行眼部校准”选项。](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a>自动眼部位置支持

在 HoloLens 2 中，眼部位置可实现准确的全息影像定位、舒适的观看体验和改进的显示质量。 眼部位置在内部计算，作为眼球跟踪计算的一部分。 但是，这要求每个用户都可以通过眼球跟踪校准，即使体验可能不需要眼睛凝视输入也是如此。

自动眼部位置 (AEP) 使这些场景能够以无交互方式为用户计算眼部位置。 从用户戴上设备开始，“自动眼部位置”将自动在后台开始工作。 如果用户没有之前的眼球跟踪校准，“自动眼部位置”将在 20-30 秒的处理时间后开始向显示系统提供用户的眼部位置。 用户数据不会保留在设备上，如果用户取下并重新戴上设备，或者设备重新启动或从睡眠状态唤醒，则会重复此过程。

当未经校准的用户戴上设备时，“自动眼部位置”功能会改变一些系统行为。 在这种情况下，未校准的用户指的是之前未在设备上完成眼球跟踪校准过程的人员。

| 活动应用程序 | 先前行为 | Windows 全息版 20H2 更新的行为 |
|:-------------------|:-----------------|:-----------------------------------|
| 未启用凝视的应用或全息外壳 |“眼球跟踪校准提示”对话框随即显示。 | 不显示提示。 |
| 启用了凝视的应用 | “眼球跟踪校准提示”对话框随即显示。 | 仅当应用程序访问眼睛凝视流时，才会显示眼球跟踪校准提示。 |

如果用户从未启用凝视的应用程序转换为访问凝视数据的应用程序，则会显示校准提示。 

所有其他系统行为将类似于当前用户没有活动的眼球跟踪校准的情况。 例如，将不会启用单只手的开始手势。 初始设置的全新体验不会有任何变化。

对于需要眼睛凝视数据或精确的全息影像位置的体验，我们建议未校准的用户运行眼球跟踪校准。 可以通过眼球跟踪校准提示或从“开始”菜单启动“设置”应用程序，然后选择“系统”>“校准”>“眼部校准”>“运行眼部校准”。

#### <a name="deferred-calibration-prompt"></a>延期校准提示

使用自动眼部位置，眼球跟踪校准提示对话框将被推迟，直到应用程序请求眼睛凝视数据。 这样可以确保当活动应用程序不需要凝视时，不会向用户提示。 如果应用程序确实需要凝视数据，而当前用户没有校准，则会向用户显示校准提示。 这种行为可以用来在合适的时间显示目视跟踪校准提示，有利于体验。 出于以下原因，建议使用此方法：

1.  “眼球跟踪校准提示”对话框向用户提供了有关为什么需要眼球跟踪的详细信息。
2.  为用户提供了一种拒绝眼部校准的方法。

如果用户选择启动“眼球跟踪校准”，校准完成后，焦点应返回到原始应用程序。 

### <a name="calibration-data-and-security"></a>校准数据和安全

校准信息本地存储在设备上，与任何帐户信息无关。 使用设备但未校准的用户不会留下记录。 这意味着，当新用户首次使用设备时，系统会提示他们进行视觉对象校准，之前选择退出校准过程或校准不成功的用户也会得到同样提示。

设备可以在本地存储多达 50 个校准配置文件。 达到此数目后，设备将自动删除最早的未用配置文件。

在“设置” > “隐私声明” > ”眼球跟踪程序”中，始终可以从设备中删除校准信息。  

### <a name="disable-calibration"></a>禁用校准

#### <a name="eye-calibration-behavior-on-hololens-2-builds-20h2-and-newer"></a>HoloLens 2 内部版本 20H2 和更高版本上的目视校准行为

自 Windows Holographic 20H2 版本引入[自动眼部位置支持](hololens-release-notes.md#auto-eye-position-support)起，便无需禁用校准。 仅当你使用支持目视追踪的应用时，校准提示才会自动显示。

#### <a name="disabling-eye-calibration-on-hololens-2-older-builds"></a>在较早的 HoloLens 2 内部版本上禁用目视校准

可以在头戴显示设备上切换“设置”开关来禁用校准，但开关状态可能不容易确定。 它已被删除，并已替换为[自动眼部位置支持](hololens-release-notes.md#auto-eye-position-support)，该支持在提供颜色更正和全息影像定位的同时推迟校准。

#### <a name="disabling-eye-calibration-on-hololens-1st-gen"></a>在 HoloLens 2（第一代）上禁用目视校准

对于 [HoloLens（第一代）校准](#calibrating-your-hololens-1st-gen)，可以按照以下步骤禁用目视校准提示：

1. 选择“设置” > “系统” > “校准”。
1. 关闭“新用户使用此 HoloLens 时，自动要求运行眼部校准”。

   > [!IMPORTANT]
   > 此设置可能对全息影像呈现质量和舒适度产生不利影响。  关闭此设置时，依赖于眼球跟踪的功能（如文本滚动）在沉浸式应用程序中将不再起作用。

### <a name="hololens-2-eye-tracking-technology"></a>HoloLens 2 眼球跟踪技术

该设备使用眼球跟踪技术来提高显示质量，同时确保所有全息图放置准确、在 3D 模式下观看起来更舒适。 因为它将眼睛作为地标，所以设备可以针对每个用户自我调整，并随着头戴显示设备在整个使用过程中轻微地移动调整视觉对象。  所有调整都自动完成，无需手动介入。
> [!NOTE]
> 设置 IPD 不适用于 Hololens 2，因为眼部位置是由系统计算的。

HoloLens 应用程序使用眼球跟踪技术来实时跟踪你注视的地方。 这是开发人员可以使用来实现全息体验中全新水平的上下文、人类理解和互动的主要技术。 开发人员无需进行任何操作就可以使用此功能。

## <a name="calibrating-your-hololens-1st-gen"></a>校准你的 HoloLens（第一代）

HoloLens（第一代）根据[瞳孔间距](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD) 调整全息影像显示。 如果 IPD 不准确，全息图可能显示不稳定或距离不正确。 根据你的瞳距 (IPD) 来校准设备可以提高视觉对象的质量。

在设置 Hololens（第一代）设备时，当 Cortana 作完自我介绍后，系统会提示你进行视觉对象校准。 建议在此设置阶段完成校准步骤。 不过，你也可以跳过这一步，只要在 Cortana 提示你时，你说“跳过”即可。

在校准过程中，HoloLens 会要求你将手指与每只眼睛注视的六个目标对齐。 HoloLens 使用此过程为眼睛正确设置 IPD。

![第二步中的 IPD 手指对齐屏幕。](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a>手动启动校准过程

如果你需要更新校准，或者新的用户需要调整校准，都可以随时手动运行“校准”应用。 默认情况下安装“校准”应用。 要访问该应用，可以通过“开始”菜单或“设置”应用。

要通过“开始”菜单运行“校准”应用，请按照以下步骤操作：

1. 使用[开花](hololens1-basic-usage.md)手势打开“开始”菜单。
1. 要查看所有应用，请选择“+”。
1. 选择“校准”。

   ![从 shell 访问“校准”应用。](./images/calibration-shell.png)

   ![“校准”应用启动后显示为一个活动立方体。](./images/calibration-livecube-200px.png)

要通过“设置”应用来运行“校准”应用，请按照以下步骤操作：

1. 使用[开花](hololens1-basic-usage.md)手势打开“开始”菜单。
1. 如果“设置”未固定到“开始”，请选择“+”查看所有应用。
1. 选择“设置”。
1. 选择“系统” > “实用工具” > “打开校准”。

   ![从“设置”应用启动“校准”应用。](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a>沉浸式头戴显示设备

某些沉浸式头戴显示设备提供自定义 IPD 设置的功能。 若要更改头戴显示设备的 IPD，请打开设置应用，选择“混合现实” > “头戴显示设备显示”，然后移动滑块控件。 你将在头戴显示设备中看到实时变化。 如果你知道自己的 IPD（可能是从验光师那里得知），可以直接输入它。

还可以通过选择“设置” > “混合现实” > “头戴显示设备显示”来在电脑上调整此设置。

如果你的头戴显示设备不支持 IPD 自定义，则此设置将被禁用。
