---
title: HoloLens 设备和全息影像的常见问题
description: 你是否有关于 HoloLens 或与全息影像交互的常见问题解答？  本文提供快速的答案和更多资源。
keywords: hololens，常见问题解答，已知问题，帮助
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
ms.openlocfilehash: b20e5784711fdbae0602943cbad35a37f5be72fdd2a709ec8c04d95b05e75ada
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664615"
---
# <a name="holograms-and-interactions-troubleshooting"></a>全息影像和交互疑难解答

本文介绍有关如何放置全息影像、使用空间并报告全息影像问题的问题。

遇到问题时，请确保：
- 尝试 [重新启动它](hololens-restart-recover.md) 以查看是否修复了问题。
- 在进行故障排除之前，请确保 HoloLens (按至少) 一[小时收费。](hololens2-charging.md) 


请使用反馈应用向我们发送有关此问题的信息。 你将在 " [**开始** " 菜单](holographic-home.md)上找到 "反馈" 应用。 

有关如何磨损 HoloLens 的提示，请参阅[调整大小](hololens2-setup.md#adjust-fit)。

<a id="list"></a>
- [无法创建新的空格](#new-spaces-cant-be-created)
- [无法标识或加载空格](#spaces-cant-be-identified-or-loaded)
- [如何实现删除所有空格？](#how-do-i-delete-all-spaces)
- [全息影像看起来不正确或正在四处移动](#holograms-dont-look-right-or-are-moving-around)
- ["查找空间" 消息](#finding-your-space-message)
- [我的空间中不显示预期的全息影像](#expected-holograms-arent-showing-in-my-space)
- [无法放置全息影像或查看以前放置的全息影像](#cant-place-holograms-or-see-previously-placed-holograms)
- [全息影像消失，或者在其他全息影像或对象中 try](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [全息影像显示在墙壁的另一端](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [在墙上放置全息影像后，它似乎是浮动的](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [移动应用后，应用显示太近](#apps-appear-too-close-after-moving-them)
- [报告不稳定或不精确的全息影像的问题](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a>无法创建新的空格

最可能的问题是在存储空间不足的情况下运行。 请[释放一些磁盘空间](hololens-troubleshooting.md#low-disk-space-error)，然后重试。

[返回到列表](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a>无法标识或加载空格

如果您的 HoloLens 无法识别并加载您自动处于的空间，请检查以下因素：

- 请确保已连接到 Wi-Fi
- 请确保房间内有充足的光线
- 请确保不存在对周围环境的任何重大更改。

还可以通过转到 **设置**  >  **系统**  >  **空间**，手动加载空间或管理空间。

[返回到列表](#list)

## <a name="how-do-i-delete-all-spaces"></a>如何实现删除所有空格？

*即将推出*

[返回到列表](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a>全息影像看起来不正确或正在四处移动

例如，如果你的全息影像看上去不正常 (例如，它们抖动或晃动，或者你) 上看到了黑色的修补程序，请尝试以下解决方法之一：

- [清洁你的设备面板](hololens1-hardware.md#care-and-cleaning) ，确保没有任何传感器阻止。
- 请确保你处于一个良好的空间，不会有很多直接阳光。
- 尝试在你的环境中浏览和 gazing，以便 HoloLens 可以更完整地扫描它们。
- 如果你已放入大量全息影像，请尝试删除一些全息影像。

如果仍有问题，请尝试运行校准应用。 此应用校准您的 HoloLens 只是为了帮助您保持全息影像的外观。 为此，请参阅 **设置**  >  **系统**  >  **实用程序**"。 在 **校准** 下，选择 " **打开校准**"。

[返回到列表](#list)

## <a name="finding-your-space-message"></a>"查找空间" 消息

当 HoloLens 学习或加载空间时，可能会看到一条简短消息，其中显示 "查找你的空间"。 如果此消息显示超过几秒钟，则会在 ""开始"菜单" 下看到另一条消息，显示 "仍在查找空间"。

这些消息表示 HoloLens 在映射空间时遇到问题。 发生这种情况时，可以打开应用程序，但不能在环境中放置全息影像。

如果经常看到这些消息，请尝试下列一项或多项修复：

- 请确保你处于一个良好的空间，不会有很多直接阳光。
- 确保设备面板清晰。 [了解如何清理面板](hololens1-hardware.md#care-and-cleaning)。
- 请确保有一个强 Wi-Fi 信号。 如果输入的新环境没有 Wi-Fi 或弱 Wi-Fi 信号，HoloLens 将找不到你的空间。 转到 **设置**  >  **网络 &amp; Internet**  >  **wi-fi** 来检查 Wi-Fi 连接。
- 尝试移动速度缓慢。

[返回到列表](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a>我的空间中不显示预期的全息影像

如果看不到你所放置的全息影像，或者你看到的是不需要的影像，请尝试以下一项或多项修复：

- 开启一些光源。 HoloLens 最好在良好的空间中运行。
- 转到 **设置**  >  **系统**  >  **全息影像**  >  **删除附近的全息影像**，删除不需要的全息影像。 或者，如果需要，请选择 " **删除所有全息影像**"。

  > [!NOTE]
  > 如果空间中的布局或光照发生了重大变化，则设备可能无法识别空间并显示全息影像。

[返回到列表](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a>无法放置全息影像或查看以前放置的全息影像

如果 HoloLens 无法映射或加载空间，则它将进入限制模式，你将无法放置全息影像或查看已放置的全息影像。 可以尝试以下操作：

- 请确保环境中有足够的灯光，以便 HoloLens 可以查看和映射空间。
- 介于您尝试放置全息影像的一到三米之间。
- 请勿在黑色或反光的表面上放置全息影像。
- 请确保已连接到 Wi-Fi 网络。 如果未连接到 wi-fi，HoloLens 无法识别和加载已知的空间。
- 四处浏览房间，以便 HoloLens 可以重新扫描您的环境。 若要查看已扫描的内容，请点击以显示地图网格图。
- 如果需要创建新空间，请连接到 Wi-fi，然后重新启动 HoloLens。
- 若要查看正确的空间是否处于活动状态，或要手动加载空间，请参阅 **设置**  >  **系统**  >  **空间**。
- 如果加载了正确的空间并且仍有问题，则空间可能已损坏。 若要解决此问题，请选择该空间，然后选择 " **删除**"。 删除空间后，HoloLens 会开始映射你的环境并创建新空间。

[返回到列表](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a>全息影像消失，或者在其他全息影像或对象中 try

如果你的全息图太近，则会暂时将其消失 &mdash; ，以便还原全息图，只需离开。 此外，如果将多个全息影像放置在一起，某些影像可能会消失。 请尝试删除一些。

全息影像还可以被其他影像或对象（如墙壁）阻止或 try。 如果发生这种情况，请尝试以下修复之一：

- 如果在另一个全息图中 try 全息图，请将 try 全息图移到另一个位置。 为此，请选择 " **调整**"，然后点击并按住以定位它。
- 如果在墙壁中 try 全息图，请选择 " **调整**"，然后向墙壁方向直到出现全息图。 点击并按住，并向前和向外拉出全息影像。
- 如果无法通过使用笔势移动全息图，请使用语音将其删除。 注视全息图，然后说 "删除"。 然后重新打开全息图，并将其放在新位置。

[返回到列表](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a>全息影像在墙的另一侧显示

如果你非常靠近墙，或者HoloLens尚未扫描墙，则可以看到下一个房间中的全息影像。 若要扫描墙，请站到距离墙 1 到 3 米之间，然后凝视它。

黑色或反射对象 (，例如，当用户尝试扫描墙时，) 的黑色长相或HoloLens可能引发问题。 如果存在此类对象，请扫描墙的另一侧。

[返回到列表](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a>将全息影像放在墙上后，它似乎已浮动

放在墙上的全息影像通常看起来离墙大约一英寸。 如果看起来距离较远，请尝试以下一个或多个修复：

- 将全息影像放在墙上时，请从墙 1 到 3 米之间直视墙面。
- 通过敲击墙来显示映射网格图形。 确保网格与墙对齐。 如果没有，请删除全息影像，重新扫描墙，然后重试。
- 如果问题仍然存在，请运行校准应用。 你将在系统实用工具 **设置**  >    >  **找到它**。

[返回到列表](#list)

## <a name="apps-appear-too-close-after-moving-them"></a>应用在移动后看起来太接近

尝试四处浏览并查看放置应用的区域，以便HoloLens从不同角度扫描该区域。 [清理设备视器](hololens1-hardware.md#care-and-cleaning) 也可能有所帮助。

[返回到列表](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a>报告不稳定或不精确的全息影像问题
 
1. 请录制混合现实捕获 [问题](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 的视频。 稍后可以通过附加文件反馈中心上传此视频。  
1. 通过应用启用完整 **遥测** 设置 ->**隐私** 诊断&反馈，在"可选诊断数据"下确保将切换  ->  设置为 **"打开"**
1. 通过更新到最新的全息 OS（Windows [20H2](hololens-release-notes.md#windows-holographic-version-20h2)或更高版本） (获取最新的全息影像缩放和稳定性) 。 更新后，执行以下操作：
    1. 通过 全息影像 应用 -> **System** 全息影像 ->应用 -设置 删除所有图像，然后选择"删除所有全息影像"，然后从全新的地图  ->  开始。 
    1. 在房间周围穿过HoloLens并查看空间的所有区域与表面，创建空间的新地图。 此操作需要 2-3 分钟。
    1. 执行 IPD 校准。 转到 **"设置**  >    >  **实用工具"。** 在 **"校准"** 下，选择 **"打开校准"。**
    1. 重新测试该方案，并查看其是否仍然存在。
1. 如果更新无法解决问题，请提交反馈中心 [问题](hololens-feedback.md)。 填写反馈后，可以使用"共享"按钮创建一个可在联系支持人员时发送的易于共享的链接。

[返回到列表](#list)