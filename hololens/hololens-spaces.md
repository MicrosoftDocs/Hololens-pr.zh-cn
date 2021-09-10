---
title: 使用 HoloLens 映射物理空间
description: HoloLens 可随着时间的推移了解某个空间的外观。 用户可通过在空间中以特定方式移动 HoloLens 来促进这一过程。
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens, Windows Mixed Reality, 设计, 空间映射, HoloLens, 图面重构, 网格, 头部跟踪, 映射
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: b8bda049f0ef4610dcf0ca6fe81d89dd5a316e3e
ms.sourcegitcommit: 05537014d27d9cb60d5485ce93654371d914d5e3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2021
ms.locfileid: "124428175"
---
# <a name="map-physical-spaces-with-hololens"></a>使用 HoloLens 映射物理空间

HoloLens 将全息影像与物理世界混合在一起。 为此，HoloLens 必须了解你周围的物理世界，并记住你在该空间中放置全息影像的位置。

随着时间的推移，HoloLens 会建立起它所看到的环境的空间地图。  HoloLens 会随着环境的变化更新该地图。 只要你已登录并且设备处于打开状态，HoloLens 就会创建并更新空间地图。 如果你拿着或佩戴设备时摄像头指向某个空间，HoloLens 会尝试映射该区域。 虽然 HoloLens 随着时间的推移会自然地了解一个空间，但有一些方法可帮助 HoloLens 更快且更有效地映射空间。  

> [!NOTE]
> 如果 HoloLens 无法映射空间或未校准，HoloLens 可能会进入“受限”模式。 在“受限”模式下，你将无法在周边环境中放置全息影像。

本文介绍 HoloLens 如何映射空间，如何改进空间映射，以及如何管理 HoloLens 收集的空间数据。

## <a name="choosing-and-setting-up-and-your-space"></a>选择并设置空间

环境中的特征可能会使 HoloLens 难以理解空间。 光线水平、空间中的材料、对象的布局等都会影响 HoloLens 映射区域的方式。

HoloLens 在某些环境下效果最好。 若要构建最佳的空间地图，请选择一个光线充足且空间充足的房间。 避免黑暗空间和有大量黑暗、闪亮或半透明表面（例如镜子或薄纱窗帘）的房间。

HoloLens 针对室内使用进行了优化。 Wi-Fi 处于打开状态时，空间映射也能发挥最佳效果（尽管它不必连接到网络）。 即使未连接或未通过身份验证，HoloLens 也可获取 Wi-Fi 访问点。 无论访问点是已连接 Internet 还是仅限 Intranet/本地，HoloLens 的功能都不会改变。

只能在没有绊倒危险的安全位置使用 HoloLens。 [有关安全的更多信息](https://support.microsoft.com/help/4023454/safety-information)。

## <a name="mapping-your-space"></a>映射空间

现在，你已准备好开始映射你的空间。  在 HoloLens 开始映射你的环境时，你将看到一个散布在整个空间中的网格图。  在混合现实主页中，可通过选择一个映射图面来触发地图进行显示。

下面是用于构建出色空间地图的指南。

### <a name="understand-the-scenarios-for-the-area"></a>了解区域的场景

务必要将大部分时间花在你将要使用 HoloLens 的位置，这样地图才是相关且完整的。 例如，如果 HoloLens 的用户场景涉及从 A 点到 B 点的移动，则沿着这条路径走两到三次，一边移动一边环顾四周。  

### <a name="walk-slowly-around-the-space"></a>围绕空间慢慢移动

如果在该区域中移动过快，则 HoloLens 可能会漏掉映射区域。 围绕空间慢慢移动，每隔 5-8 英尺停下环顾周围的环境。  

平滑的移动也可帮助 HoloLens 更有效地进行映射。

### <a name="look-in-all-directions"></a>全向环顾

在你映射空间时，环顾四周，这样可使 HoloLens 获得更多关于点之间相对位置的数据。  

例如，如果你不抬头，HoloLens 可能就不知道房间中天花板的位置。  

在映射空间时，请不要忘记低头看向地面。

### <a name="cover-key-areas-multiple-times"></a>多次覆盖关键区域

在一个区域中移动多次将有助于拾取你在第一次移动过程中可能错过的特征。 若要构建理想的地图，请尝试在一个区域中穿行两到三次。

如果可能，在重复这些移动时，花时间沿着一个方向穿过一个区域，然后转身朝你来的方向往回走。

### <a name="take-your-time-mapping-the-area"></a>从容地映射区域

HoloLens 需要 15 到 20 分钟的时间才能完全映射并适应周围环境。 如果你计划在一个空间中频繁使用 HoloLens，则提前花一些时间来映射该空间可防止以后出现问题。  

## <a name="possible-errors-in-the-spatial-map"></a>空间地图中可能存在的错误

空间映射数据中的错误分为几个类别：

- 孔洞：空间映射数据中缺少真实世界的图面。
- 幻像：图面存在于空间映射数据中，而在现实世界中并不存在。
- 虫洞：HoloLens“丢失”了空间地图的一部分，因为它认为该部分在地图中所在的位置不同于其实际所在的位置。
- 偏差：空间映射数据中的图面与真实世界的图面未完全对齐，要么被推入，要么被拉出。

如果看到任何这些错误，请使用 [FeedbackHub](hololens-feedback.md) 发送反馈。

## <a name="security-and-storage-for-spatial-data"></a>空间数据的安全和存储

Microsoft HoloLens 和更高版本的 Windows 10 版本 1803 更新将映射数据存储在本地（设备上的）数据库中。

即使在将设备插入电脑或在使用文件资源管理器应用时，HoloLens 用户也不能直接访问映射数据库。 在 HoloLens 上启用 BitLocker 时，存储的映射数据也将随整个卷一起加密。

### <a name="remove-map-data-and-known-spaces-from-hololens"></a>从 HoloLens 中删除映射数据和已知空间

在“设置”>“系统”>“全息影像”中有两个选项可用于删除映射数据：

- 若要删除附近的全息影像，请选择“删除附近的全息影像”。 此命令清除当前空间的映射数据和锚定全息影像。 如果继续在同一空间中使用该设备，它将创建并存储一个全新的地图部分以替换已删除的信息。

   > [!NOTE]
   > “附近的”全息影像指锚定在当前空间中同一地图部分内的全息影像。

   可使用此选项清除与工作相关的映射数据，而不影响任何与主页相关的映射数据。

- 若要删除所有全息影像，请选择“删除所有全息影像”。 此命令清除存储在设备上的所有映射数据，以及所有锚定全息影像。 你需要显式地放置任何全息影像。 无法重新发现以前放置的全息影像。

> [!NOTE]
> 删除附近的或所有的全息影像后，HoloLens 立即开始扫描并映射当前空间。

### <a name="wi-fi-data-in-spatial-maps"></a>空间地图中的 Wi-Fi 数据

HoloLens 存储 Wi-Fi 的特征，有助于关联存储在已知空间 HoloLens 数据库内的全息影像位置和地图部分。 用户无法访问有关 Wi-Fi 特征的信息，也无法使用云或遥测将其发送给 Microsoft。

只要启用了 Wi-Fi，HoloLens 就会将映射数据与附近的 Wi-Fi 接入点相关联。 无论连接了网络还是只是在附近检测到网络，行为都没有差异。 如果禁用了 Wi-Fi，HoloLens 仍会搜索该空间。 但是，HoloLens 必须在空间数据库中搜索更多映射数据，并且可能需要更多时间才能找到全息影像。 如果没有 Wi-Fi 信息，HoloLens 必须将活动扫描与设备上存储的所有全息影像锚点和地图部分进行比较，以便找到地图的正确部分。

## <a name="related-topics"></a>相关主题

- [空间映射设计](/windows/mixed-reality/spatial-mapping)
