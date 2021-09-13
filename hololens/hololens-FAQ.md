---
title: 有关设备HoloLens全息影像的常见问题
description: 你是否对全息影像HoloLens有一个快速问题？  本文提供了一个快速答案和更多资源。
keywords: hololens， 常见问题， 已知问题， 帮助
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032064"
---
# <a name="holograms-and-interactions-troubleshooting"></a>全息影像和交互故障排除

本文排查放置全息影像、使用空间和报告全息影像问题的问题。

遇到问题时，请确保：
- 尝试 [重启它](hololens-restart-recover.md) ，看看它是否修复了问题。
- 在故障排除之前，请确保HoloLens[至少](hololens2-charging.md) (小时对设备进行) 。 


请使用反馈应用向我们发送有关此问题的信息。 你将在"开始"菜单上找到" [**反馈"** 应用](holographic-home.md)。 

有关如何在设备中HoloLens的提示，请参阅[调整适应度](hololens2-setup.md#adjust-fit)。

<a id="list"></a>
- [无法创建新空间](#new-spaces-cant-be-created)
- [无法标识或加载空格](#spaces-cant-be-identified-or-loaded)
- [如何实现删除所有空格？](#how-do-i-delete-all-spaces)
- [全息影像看起来不对或正在四处移动](#holograms-dont-look-right-or-are-moving-around)
- ["查找空间"消息](#finding-your-space-message)
- [预期的全息影像未显示在我的空间中](#expected-holograms-arent-showing-in-my-space)
- [无法放置全息影像或查看以前放置的全息影像](#cant-place-holograms-or-see-previously-placed-holograms)
- [全息影像其他全息影像或对象中消失或被包住](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [全息影像在墙的另一侧显示](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [将全息影像放在墙上后，它看起来是浮动的](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [应用在移动后看起来太接近](#apps-appear-too-close-after-moving-them)
- [报告不稳定或不精确的全息影像问题](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>无法创建新空间

最可能的问题是存储空间不足。 [释放一些磁盘空间，](hololens-troubleshooting.md#low-disk-space-error) 然后重试。

[返回到列表](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>无法标识或加载空格

如果HoloLens无法识别并加载你自动占用的空间，请检查以下因素：

- 确保已连接到 Wi-Fi
- 确保房间中有足够的光线
- 请确保环境没有任何重大更改。

还可以手动加载空间，或者通过访问 System Spaces 设置  >  **空间**  >  。

[返回到列表](#list)

## <a name="how-do-i-delete-all-spaces"></a>如何实现删除所有空格？

*即将推出*

[返回到列表](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>全息影像看起来不对或正在四处移动

如果全息影像看起来不 (，例如，它们抖动或抖动，或者看到它们上面有黑色修补程序) ，请尝试以下修复之一：

- [清理设备视网，](hololens1-hardware.md#care-and-cleaning) 并确保没有任何内容阻止传感器。
- 请确保你房间照明良好，没有太多直接光照。
- 尝试在周围四处浏览和HoloLens，以便可以更彻底地扫描它们。
- 如果放置了许多全息影像，请尝试删除一些全息影像。

如果仍然遇到问题，请尝试运行校准应用。 此应用将校准HoloLens，以帮助保持全息影像的最佳显示效果。 为此，请转到 **"设置**  >    >  **实用工具"。** 在 **"校准"** 下，选择 **"打开校准"。**

[返回到列表](#list)

## <a name="finding-your-space-message"></a>"查找空间"消息

当你HoloLens或加载空间时，你可能会看到一条简短的消息，指出"正在查找空间"。 如果此消息显示几秒钟以上，你将在屏幕下看到另一条消息"开始"菜单"仍在查找你的空间"。

这些消息意味着HoloLens空间映射时遇到问题。 发生这种情况时，可以打开应用，但不能将全息影像放在环境中。

如果经常看到这些消息，请尝试以下一个或多个修补程序：

- 请确保你房间照明良好，没有太多直接光照。
- 确保设备视区干净。 [了解如何清理视区](hololens1-hardware.md#care-and-cleaning)。
- 请确保具有强Wi-Fi信号。 如果输入的新环境没有Wi-Fi信号或Wi-Fi信号，HoloLens找不到空间。 通过Wi-Fi Internet   >  **&amp;**  >  **Wi-Fi** 设置检查连接。
- 尝试更慢地移动。

[返回到列表](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>预期的全息影像未显示在我的空间中

如果看不到放置的全息影像，或者看到一些不需要的全息影像，请尝试以下一个或多个修复：

- 打开一些灯。 HoloLens在照明良好的空间中效果最佳。
- 若要删除不需要的全息影像，可  >  **设置"** 删除全息影像  >    >  **全息影像"。** 或者，如果需要，请选择 **"删除所有全息影像"。**

  > [!NOTE]
  > 如果空间中的布局或照明发生显著变化，设备可能难以识别空间和显示全息影像。

[返回到列表](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>无法放置全息影像或查看以前放置的全息影像

如果HoloLens无法映射或加载空间，它将进入受限模式，你将无法放置全息影像或查看已放置的全息影像。 可以尝试以下操作：

- 请确保环境中有足够的光线，以便HoloLens和映射空间。
- 在一到三米之间放置全息影像。
- 不要将全息影像放在黑色或反射表面上。
- 确保已连接到 Wi-Fi 网络。 如果未连接到 Wi-Fi，HoloLens无法识别和加载已知空间。
- 在房间中四HoloLens，以便可以重新扫描周围的环境。 若要查看已扫描内容，请通过敲击显示映射网格图形。
- 如果需要创建新空间，请连接到 Wi-Fi，然后重启HoloLens。
- 若要了解正确的空间是否处于活动状态，或要手动加载空间，请转到 设置  >  **System**  >  **Spaces。**
- 如果加载了正确的空间，但仍遇到问题，则空间可能已损坏。 若要解决此问题，请选择空格，然后选择"删除 **"。** 删除空间后，HoloLens开始映射周围的环境并创建新空间。

[返回到列表](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>全息影像其他全息影像或对象中消失或被包住

如果离全息影像太近，它会暂时消失以还原全息影像， &mdash; 只需离开它。 此外，如果你将多个全息影像放在一起，某些全息影像可能会消失。 请尝试删除一些。

全息影像其他全息影像或对象（如墙）阻止或包住这些图像。 如果发生这种情况，请尝试以下修复之一：

- 如果全息影像被放在另一个全息影像中，则将包住的全息影像移到另一个位置。 为此，请选择" **调整"，** 然后点击并按住以定位它。
- 如果全息影像已装在墙中，请选择"调整"，然后向墙走，直到全息影像出现。  点击并按住，然后向前和外拉全息影像。
- 如果无法通过使用手势移动全息影像，请使用语音将其删除。 凝视全息影像，然后说"删除"。 然后重新打开全息影像，将其放在新位置。

[返回到列表](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>全息影像显示在墙壁的另一端

如果您非常接近墙壁，或者 HoloLens 尚未扫描墙壁，则可以看到下一个房间中的全息影像。 若要扫描墙壁，请从墙壁开始到3米之间，看看。

黑色或反射对象 (例如，当 HoloLens 尝试扫描墙壁时，墙附近的黑色沙发或 stainless 钢冰箱) 会导致问题。 如果有此类对象，请扫描墙壁的另一面。

[返回到列表](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>在墙上放置全息影像后，它似乎是浮动的

放置在墙壁上的全息图通常会显得一英寸或远离墙壁。 如果看上去更远离，请尝试以下一项或多项修复：

- 在墙壁上放置全息影像时，从墙壁开始到一到3米之间，并直接面对墙壁。
- 单击墙壁即可显示地图网格图。 请确保网格与墙壁对齐。 如果没有，请删除全息图，重新扫描墙，然后重试。
- 如果问题仍然存在，请运行校准应用。 你会在 **设置**  >  **系统**  >  **实用工具** 中找到它。

[返回到列表](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>移动应用后，应用显示太近

尝试浏览并查看放置应用程序的区域，以便 HoloLens 从不同角度扫描区域。 [清除设备面板](hololens1-hardware.md#care-and-cleaning) 也可能会有所帮助。

[返回到列表](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>报告不稳定或不精确的全息影像的问题
 
1. 请记录并记录问题的 [混合现实](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 。 此视频稍后可通过反馈中心作为附加文件上传。  
1. 通过 **设置** 应用启用整个遥测->**隐私**  ->  **诊断 & 反馈**，并在 **可选诊断数据** 下，确保将切换设置为 **On**
1. 通过更新到最新的[Windows 全息版 OS， (20H2 或更高) 版本，](hololens-release-notes.md#windows-holographic-version-20h2)获取最新的全息图缩放和稳定性修复。 更新后，请执行以下操作：
    1. 通过 **设置** 应用程序 >**系统**  ->  **全息影像**-> 删除所有全息影像，然后选择 "**删除所有全息影像** 并从新的映射开始"。
    1. 通过戴上 HoloLens 并浏览房间并查看空间中的所有区域和表面来创建空间的新地图。 为2-3 分钟执行此操作。
    1. 执行 IPD 校准。 请参阅 **设置**  >  **系统**  >  **实用程序**"。 在 **校准** 下，选择 " **打开校准**"。
    1. 重新测试方案，并查看它是否仍然存在。
1. 如果更新不能解决问题，请提交 [反馈中心问题](hololens-feedback.md)。 填写反馈后，可以使用 " **共享** " 按钮，创建一个易于共享的链接，以便在联系支持人员时发送。

[返回到列表](#list)