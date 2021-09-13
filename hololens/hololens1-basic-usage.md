---
title: 开始使用 HoloLens（第 1 代）
description: 开始简要了解 HoloLens (第一代) 界面、手动跟踪功能以及使用全息应用程序。
ms.assetid: 064f7eb0-190e-4643-abeb-ed3b09312042
ms.date: 9/16/2019
ms.reviewer: jarrettr
manager: jarrettr
keywords: HoloLens
ms.prod: hololens
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 70ee881eb0c2ffaade173b31e5168371d042bbb2
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032146"
---
# <a name="getting-around-hololens-1st-gen"></a>开始使用 HoloLens（第 1 代）

可以单步执行全息影像世界了吗？ 下面是一些入门信息。

本指南提供混合现实的简介、与全息影像交互的手势，以及 Windows 全息版的简介。

## <a name="discover-mixed-reality"></a>了解混合现实

在 HoloLens 上，全息影像与物理环境混合，看起来像是世界的一部分。 即使是在整个全息影像，你仍可查看你的环境，自由移动，并与其他人和对象进行交互。 我们称之为 "mixed reality"。

全息帧可将您眼睛最敏感的全息影像定位到详细信息，并可通过查看重用功能区离开您的外围设备视觉 unobscured。 使用空间音效，你可以找出一个全息图，即使它位于你后面。 由于 HoloLens 了解并了解你的环境，因此你可以在真实对象上放置全息影像，因此你的应用程序和游戏也可以。 因此游戏中的一个字符可能会坐在沙发上，或者 [空间机器人可能会必须](https://www.microsoft.com/store/apps/9nblggh5fv3j)。

## <a name="use-hololens-with-your-hands"></a>使用手 HoloLens

使用 HoloLens 就像使用智能电话。 你可以使用手操作全息窗口、菜单和按钮。  您将使用您的注视、[语音](hololens-cortana.md)和手势来选择应用程序和全息影像并 HoloLens，而不是指向、单击或点击。

当你知道这些基本交互时，HoloLens 将会是一个快照。

第一次使用 HoloLens 时，我们将引导你完成基本操作。 你还可以在 " **开始** " 菜单中找到手势教程，查找 "学习手势" 应用。

### <a name="the-hand-tracking-frame"></a>手部跟踪框

HoloLens 的传感器能够探测到你身体两侧几米远的地方。 用手进行操作时，你需要将其始终放在该框架内，否则 HoloLens 将无法探测到它们。 当你四处移动时，框架会随你一起移动。  

![显示 HoloLens 手部跟踪框架的图像。](./images/hololens-2-gesture-frame.png)

### <a name="open-the-start-menu-with-bloom"></a>用布隆打开 "开始"菜单

若要打开 " **开始** " 菜单：

1. 抓住你的正面，使其位于手势帧中。
1. 布隆：将所有手指集中在一起，然后打开手。
  ![显示布隆手势的动画。](./images/hololens-bloom.gif)

### <a name="select-holograms-with-gaze-and-air-tap"></a>用注视和空中点击选择全息影像

若要选择某个应用或其他全息图，请在直接查看所选全息影像时单击它。 要实现这一点，请执行下列操作：

1. 注视要选择的全息影像。
1. 将你的食指竖直向上指向天花板。
1. 分流：降低手指，然后迅速提起。
   ![隔空敲击手势动画。](./images/hololens-air-tap.gif)

### <a name="select-a-hologram-by-using-your-voice"></a>使用语音选择全息影像

1. 看起来光标是移动头的点。 您可以使用它来精确定位语音命令。
1. 注视要选择的全息影像。
1. 若要选择全息图，请说 "Select"。

## <a name="holograms-and-apps"></a>全息影像和应用

现在可以将手势放入测试！

你会在["开始"菜单](holographic-home.md)中找到已安装的应用程序，其中有更多适用于 HoloLens (第一代) 在 Microsoft Store 中的应用。

打开 " **开始** " 菜单并选择一个应用！

在 HoloLens 上使用应用与电脑上的应用稍有不同：某些应用使用2d 视图，看起来像其他 Windows 应用程序。  (沉浸式应用的其他应用) 使用三维视图，当你启动它们时，它们会成为你所看到的唯一应用。

当你放置应用程序窗口或应用程序启动器时，它将一直保留，直到你将其删除。 你随时可以在混合现实中移动或调整其大小。

## <a name="move-resize-and-rotate-apps"></a>移动、调整大小和旋转应用

在 HoloLens 上移动应用和调整其大小与在 PC 上的工作方式稍有不同。 不要拖动应用，而是将其与 [手势](https://support.microsoft.com/help/12644/hololens-use-gestures) 或 [clicker](hololens1-clicker.md)一起使用。 还可在三维空间中旋转应用窗口。

> [!TIP]
> 使用你的声音来重新安排应用程序，并显示 "面部"、"大" 或 "更小"。 或者让 Cortana 移动应用程序：说 "你好 Cortana，请 \* 在此移动 *应用 \* 名称*。"

### <a name="move-an-app"></a>移动应用

在应用程序窗口的标题栏上 (注视 ") ，然后执行以下操作之一。

- 点击并按住以选择应用。 将你的手移动到位置，并将手指抬起即可。
- 选择 " **调整**"、点击并按住，并将手上移到位置。 抬起手指，然后选择 " **完成**"。
- 依次选择 " **调整**"、"clicker" 和 "移动应用"。 释放 clicker，然后选择 " **完成**"。

> [!TIP]
> 如果在移动应用时将其删除，请确保将其置于 "注视" 旁，使其保持在手势帧中。

### <a name="resize-an-app"></a>调整应用的大小

注视应用，然后执行以下操作之一。

- 注视应用程序窗口的一个角或边缘，然后点击并按住。 移动手来更改应用的大小，完成后再抬起手指。
- 选择 " **调整**"。 在应用的角落，注视一个蓝色的方块，点击并按住，然后移动手调整应用的大小。 抬起手指将其释放，然后选择 " **完成**"。
- 选择 " **调整**"。 注视应用旁边的蓝色方块之一，单击并按住 clicker，并向下移动以调整应用大小。 释放 clicker，然后选择 " **完成**"。

> [!TIP]
> 在调整模式下，你可以移动任意全息图或调整其大小。

### <a name="rotate-an-app"></a>旋转应用

看看应用，然后点击并按住鼠标，以选择它。 通过保持一只手使其保持不动，使其旋转。 完成后，可以同时提高这两个索引。

### <a name="scroll-content-in-an-app-window"></a>滚动应用窗口中的内容

注视应用程序窗口的内容。 点击并按住鼠标，并稍微向上或向下移动，滚动内容。

## <a name="meet-the-hololens-1st-gen-clicker"></a>满足第一代) Clicker (HoloLens

[HoloLens 第一代) clicker (](hololens1-clicker.md)提供了另一种与全息影像交互的方法。 将其与你的 HoloLens[配对](hololens-connect-devices.md)，然后将其与你的注视一起用于选择、滚动等。

## <a name="next-steps"></a>后续步骤

祝贺你！ 你已准备好使用 (第一代) HoloLens。

现在，你可以配置 HoloLens (一代) ，以满足你的特定需求。

[连接 bluetooth 设备，例如鼠标和键盘](hololens-connect-devices.md)

[了解有关语音和 Cortana 的详细信息](hololens-cortana.md)

### <a name="help-i-dont-see-my-holograms"></a>帮助！ 我看不到我的全息影像

如果看不到在使用 HoloLens 时所放置的全息影像，请尝试以下操作：

- 请确保在正确的区域中 &mdash; 记住，全息影像会停留在其位置。
- 请确保你处于良好的空间，而不会产生大量直接阳光。
- 再. 如果HoloLens空间时，以前放置的全息影像可能需要一分钟才能重新显示。
- 如果问题仍然存在，你可能想要在 设置System 全息影像 中清除 全息影像 存储数据，然后将全息影像混合现实主页  >    >  中。
