---
title: HoloLens 2
description: 对HoloLens 2的期望。 图像质量最佳化配置指导。
author: BrandonBray
ms.author: branbray
ms.date: 8/13/2020
ms.topic: article
keywords: 屏幕、校准、舒适度、视觉、质量、IPD
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
appliesto:
- HoloLens 2
ms.openlocfilehash: 6cb646ec1104952b5ecfe42391c24465fd074771
ms.sourcegitcommit: fbc8ddb17e31fea8667ece43a511592b86ac3947
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "11385601"
---
# <a name="hololens-2-display"></a>HoloLens 2

HoloLens 2屏幕是波导和光投影仪的结合。 用户佩戴头戴显示设备时，通过波导（面板内的隐形眼镜）进行观看。 光投影仪在眉心上方的外壳内。 HoloLens 2 使用激光照亮屏幕。

## <a name="troubleshooting"></a>疑难解答

对于 HoloLens 2，请执行以下步骤，以确保屏幕能够呈现出最高的全息影像视觉质量：

* **增加屏幕的亮度。** 当屏幕亮度最高时，全息影像的视觉效果最好。
* **使面罩更靠近你的眼睛。** 将面罩向下旋转到距离眼睛最近的位置。
* **向下移动面罩。** 请尝试向下移动前额上的额头垫，这样面罩就会下移，更加靠近你的鼻子。
* **进行眼球校准。** 屏幕使用你的瞳距(IPD)和眼睛注视来优化屏幕上的图像。 如果未进行眼球校准，则图像质量可能会变差。 若要运行目视校准，请转到“设置” > “系统” > “校准” > “运行目视校准”。****************

## <a name="faq"></a>常见问题

### <a name="what-are-the-patterns-that-occasionally-flash-in-the-bottom-corners-of-the-display"></a>屏幕下角偶尔闪现的图案是什么？

你的HoloLens 2会偶尔在屏幕的左下角和右下角显示不同的图案。 例子如下所示（动态 Gif）。 该图案是HoloLens 2设备正常操作的一部分，用于校准屏幕以获得最佳体验。

![Biphase 图案](./images/DAT-Biphase-Fiducial.gif) ![GEO图案](./images/DAT-GEO-Fiducial.gif)

### <a name="why-am-i-unable-to-take-an-accurate-photograph-of-my-hololens-2-display"></a>为什么我的HoloLens 2屏幕无法准确拍摄照片？

HoloLens 2是为人眼观看而设计的。 设备具有可适应用户眼睛的活动颜色校正系统。 与人眼相比，摄像头看到的环境是不同的，下面是一些可能会影响摄像头捕捉到的东西和用户看到的东西之间不一致的因素。

* **目视位置。** HoloLens 2 是屏幕专为用户的目视位置设计的。 HoloLens 2 采用了目视跟踪技术来适应用户的目视位置。 如果摄像头位置错了几毫米，就会导致图像失真。 摄像头很难精确定位，况且相机需要与正在执行颜色见证的确切位置和目视保持一致。
* **眼球运动。** 屏幕能适应用户眼球运动来调整颜色。 显示的内容可能有所不同，具体取决于用户在查看屏幕的中心、边或角落。 单一的图像捕获最多只能显示与眼睛注视方向相匹配坐标轴的显示效果。
* **望远镜视觉。** HoloLens 2设计为双眼观看。 大脑适应看到两个图像，并将它们融合在一起。 一个屏幕的图像会忽略另一个屏幕的信息。
* **摄像头曝光时长。** 摄像头的曝光时长必须是1/120秒的精确倍数。 HoloLens的屏幕帧率为120Hz。 由于HoloLens 2制作图像的方式原因，捕捉一帧画面也不足以与人类的视觉体验相比。 同时，如果设备有任何移动--甚至是微动--系统会将图像重新投射到屏幕上，以便稳定全息影像。 在保持HoloLens不移动的同时捕捉多帧画面，通常需要一个检测设置。
* **摄像头光圈大小。** 摄像头光圈大小必须至少为3毫米，才能捕获准确的图像。 带小型光圈的手机摄像头与人类眼睛相比，可以从更小范围接受光线。
 这个设备可以对大光圈观察到的图案进行颜色校正。 使用小型光圈，尽管系统进行了了颜色校正，但均匀性图案仍清晰可见。
* **摄像头入射光瞳。** 摄像头入射光瞳直径至少要有3毫米，才能捕捉到准确的图像。 否则，摄像头就会捕捉到一些肉眼看不到的高频率的图案。 入射光瞳的位置既要在摄像头前方，又要保持良视距离，以避免拍摄的图像带有像差和其他变化。
* **相机位置。** 符合观看HoloLens 2要求的照相机都比较大，很难将摄像头放置在离HoloLens 2足够近的位置，以观察色彩校正后的图像。 如果照相机的位置不对，色彩校正可能会对HoloLens 2的捕捉产生负面影响。
* **图像校正。** 典型的数码相机和智能手机相机应用了色调再现曲线（TRC），这增强了对比度和色彩，以提供更敏捷的效果。 当应用到HoloLens 2时，这色调曲线会放大非均匀性。

都说专门的工业相机还是可以从HoloLens 2上捕捉到有代表性的图像。 遗憾的是，智能手机、数码相机和专业相机无法捕捉到与用户在HoloLens 2上看到的一致的图像。

### <a name="what-does-eye-calibration-do-to-display-image-quality"></a>眼球校准对屏幕图像质量有什么影响？

HoloLens 2会根据用户眼球的位置积极修正图像的颜色。 [目视校准](hololens-calibration.md) 提供两个重要的输入：（1）用户的 瞳孔间 距离（IPD），以及每个眼睛在注视的方向（2）。 如果不进行目视校准，系统会默认为标称的眼球位置，无需眼球运动。 是否积极校正可用色彩取决于用户自身的生理状况。 例如，与系统默认的IPD相同的用户将看到较少的色彩校正改进。 然而，IPD比系统默认值窄得多或宽得多的用户，则会看到屏幕图像更多的变化。

请注意，[Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中的一项新功能将开始[自动检测眼部位置](hololens-calibration.md#auto-eye-position-support)。 

### <a name="what-are-the-display-differences-between-hololens-1st-gen-and-hololens-2"></a>HoloLens（第一代）和 HoloLens 2 之间的显示差异是什么？

客户体验HoloLens 1后给Microsoft 提出的首要要求有（1）增加视场角，（2）提高亮度。 技术发展使Microsoft生产出的波导使视场角范围增加了一倍，生成的光投影机的显示亮度提高了三倍。 硬件上为屏幕的图像质量三重权衡设定了基线。(1) 视场角，(2) 亮度，(3) 色彩均匀性。 技术的不断提升，有助于促进所有领域共同发展，无一落后。 在这期间，现有的技术为这些权衡设定了可用的限制。

### <a name="what-improvements-are-coming-that-will-improve-hololens-2-image-quality"></a>将会有哪些改进提高HoloLens 2的图像质量？

尽管我们正在进行很多研究以提高图像质量，但接下来的更新包含的是以下领域：

* **自动目视位置。** 这个功能将使目视校准程序在后台运行。 用户将不再需要运行目视校准来启动主动色彩校正。 它会自动运行。
* **色彩校准改进。** 这次更新的侧重点是较深色的颜色值（例如，深灰色）。 现在，颜色变暗时色调选取红色。 当整个屏幕变暗时也会发生这个问题--整个显示屏都会呈现红色。 这个问题是由这些更深的颜色在红色频道中活动过多造成的。 我们已经对这些较暗颜色的激光照明曲线进行了表征，并在致力于为用户提供校准程序。 其结果是，在整个亮度色谱中色彩精确度将更高。 它不会改变全亮度情景下白色背景的外观。 我们继续建议在应用程序中使用黑暗色调设计模式。
* **阅读模式。** 应用开发人员可以通过权衡屏幕视野来实现更高的角度分辨率。 应用开发者可以覆盖投影矩阵，使内容在绘图解析中渲染。 这一功能可减小 30% 的视界，并提高相应的角度分辨率。 目前正在努力将这个功能引入 [混合现实工具包](https://github.com/Microsoft/MixedRealityToolkit-Unity)。 当可用时，阅读模式将在任何 HoloLens 2 操作系统上运行，而不依赖于操作系统的更新。

操作系统实现自动更新。 你还可以通过内部预览计划测试软件改进的早期版本。

### <a name="what-guidance-is-available-for-developers-to-apply-dark-mode-design-principles"></a>开发人员运用暗模式设计原则有什么可用指南？


在避免白色背景的情况中，用户将获得最佳体验。 深色模式是应用在使用黑色或深色背景时所采用的设计原则。 系统设置默认为深色模式，且可通过转到“设置” > “系统” > “颜色”进行调整。************

建议开发人员遵循深色模式设计指南：

* [HoloLens 显示器的开发人员设计指南](https://docs.microsoft.com/windows/mixed-reality/designing-content-for-holographic-display#design-guidelines)
* [推荐的字号](https://docs.microsoft.com/windows/mixed-reality/typography#recommended-font-size)

如果全息影像需要白色背景，请保持全息影像的尺寸小于显示器的完整视野。 此尺寸允许用户将全息影像置于显示器中央。

### <a name="how-do-you-clean-a-hololens-2-display"></a>如何清洁 HoloLens 2 屏幕？

使用微纤维布轻轻擦拭遮光罩。 如果要对遮光板进行消毒，请使用 70% 的异丙醇轻轻浸湿布，再擦拭遮光板。 请阅在[HoloLens 2 清洁常见问题](hololens2-maintenance.md)查看完整指导。
