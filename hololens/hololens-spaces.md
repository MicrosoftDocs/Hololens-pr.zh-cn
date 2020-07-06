---
title: 使用 HoloLens 映射物理空间
description: HoloLens 了解一段时间后空间的外观。 用户可以通过以某种方式在整个空间中移动 HoloLens 来简化此过程。
ms.assetid: bd55ecd1-697a-4b09-8274-48d1499fcb0b
author: dorreneb
ms.author: dobrown
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.date: 09/16/2019
keywords: hololens,Windows Mixed Reality,设计,空间映射,HoloLens,表面重建,网格,头部跟踪,映射
ms.prod: hololens
ms.sitesec: library
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens 1 (1st gen)
- HoloLens 2
ms.openlocfilehash: 992b17160eb6ba6ca2f6c8b12e112b98ab154774
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827920"
---
# 使用 HoloLens 映射物理空间

HoloLens 将全息影像与你的物理世界融合在一起。 为此，HoloLens 必须了解周围的物理世界，并记住在该空间中放置全息影像的位置。

随着时间推移，HoloLens 会建立它所看到的环境*空间地图*。  HoloLens 会随着环境的变化更新映射。 只要登录并打开了设备，HoloLens 就会创建和更新空间地图。 如果在相机指向某个空间的情况下握住或佩戴设备，则 HoloLens 会尝试映射此区域。 随着 HoloLens 随着时间的推移自然会出现一个空间，你可以通过多种方式来帮助 HoloLens 更快、更高效地映射你的空间。  

> [!NOTE]
> 如果 HoloLens 无法映射出你的空间或超出校准范围，则 HoloLens 可能会进入“受限”模式。 在“受限”模式中，将无法在环境中放置全息影像。

本文介绍了 HoloLens 如何映射空间，如何改进空间映射以及如何管理 HoloLens 收集的空间数据。

## 选择和设置共享空间

环境中的功能可能会使 HoloLens 难以理解空间。 光照水平、空间中的物质，对象的布局等都会影响 HoloLens 映射区域的方式。

HoloLens 在某些环境下效果最佳。 为了制作最佳的空间地图，请选择光线充足且空间充足的房间。 避免黑暗的空间和有很多黑暗、发亮或半透明表面的房间（例如镜子或薄纱幕）。

HoloLens 针对室内使用进行了优化。 虽然 Wi-fi 处于开启状态，但无需将其连接到网络，空间映射也能达到最佳的效果。 HoloLens 可以获取 Wi-fi 接入点，即使未连接或未通过身份验证。 无论接入点是Internet 连接还是Intranet /仅本地，HoloLens 功能均不会更改。

仅在没有绊倒危险的安全地方使用 HoloLens。 [有关安全的更多信息](https://support.microsoft.com/help/4023454/safety-information)。

## 映射空间

现在您准备开始映射你的空间。  HoloLens 开始映射环境时，会看到遍布空间的网格图。  在混合现实主页中，可以通过在映射的表面上进行选择来触发地图显示。

以下是构建完美空间地图的指南。

### 了解区域的场景

务必将大部分时间花在要使用 HoloLens 的地方，这样地图才是相关且完整的。 例如，如果 HoloLens 的用户场景涉及从点 A 移到点 B，则沿该路径走两到三遍，并在移动时观看所有方向。  

### 在空间中慢慢移动

如果在该区域走得太快，则 HoloLens 可能会错过绘图区域。 在空间中缓慢走动，每 5 到 8 英尺停下来环顾周围环境。  

平稳移动也有助于 HoloLens 更加有效地绘图。

### 全向环顾

绘制地图时环顾四周，可为 HoloLens 提供更多有关点相对位置的数据。  

例如，如果不抬头，HoloLens 可能不知道房间的天花板在哪里。  

映射空间时，不要忘记俯视地板。

### 多次覆盖关键区域

多次在一个区域中移动将帮助您获得在第一次走动中可能错过的功能。 要构建理想的地图，请尝试遍历2至3次区域。

如果可行，重复这些动作时，花一些时间沿一个方向走过一个区域，然后转身走回原路。

### 花时间映射区域

HoloLens 可能需要 15 到 20 分钟才能完全绘制地图并适应周围环境。 如果你有一个空间来计划经常使用 HoloLens，提前花时间来绘制空间可以防止以后发生问题。  

## 空间地图中可能存在的错误

空间映射数据中的错误分为几个类别：

- *孔洞*：空间映射数据中缺少现实表面。
- *幻象*：存在于空间映射数据中的表面在现实世界中不存在。
- *虫洞*：HoloLens 认为空间图与实际位置不在同一部分，从而“丢失”了空间图的一部分。
- *偏差*：无论推入或拉出时，空间映射数据中的表面与现实世界中的表面不完全对齐。

如果发现任何这些错误，请使用 [FeedbackHub](hololens-feedback.md) 发送反馈。

## 空间数据安全和存储

适用于 Microsoft HoloLens 的 Windows 10 版本 1803 和更新版本存储映射数据至本地（设备上）数据库内。

即使将设备插入到电脑或使用文件资源管理器应用时，HoloLens 用户也无法直接访问映射数据库。 在 HoloLens 上启用 BitLocker 后，存储的映射数据也会与整个卷一起加密。

### 从 HoloLens 中删除映射数据和已知空间

有两种方法可用于在“**设置 > 系统 > 全息影像**”中删除映射数据：

- 若要删除附近的全息影像，请选择“**删除附近的全息影像**”。 此命令清除当前空间的地图数据和锚定全息影像。 如果继续在同一空间中使用设备，它将创建并存储一个全新的映射部分以替换已删除的信息。

   > [!NOTE]
   > “附近的”全息影像是锚定在当前空间中同一映射部分内的全息影像。

   例如，可以使用此选项清除与工作相关的映射数据，而不影响任何与家庭相关的映射数据。

- 若要删除所有全息影像，请选择“**删除所有全息影像**”。 此命令清除存储在设备上的所有地图数据以及所有锚定的全息影像。 你将需要明确放置所有全息影像。 你将不能重新发现之前放置的全息影像。

> [!NOTE]
> 删除附近或所有全息影像后，HoloLens 立即开始扫描并映射当前空间。

### 空间映射中的 Wi-Fi 数据

HoloLens 会存储 Wi-fi 的特征，有助于关联存储在已知空间 HoloLens 数据库内的全息影像位置和图区。 用户无法访问有关 Wi-Fi 特征的信息，也无法使用云或遥测将其发送给 Microsoft。

只要启用了Wi-Fi，HoloLens 就会将地图数据与附近的 Wi-Fi 接入点相关联。 无论网络是否已连接或是否仅在附近检测到，都没有行为方面的差异。 如果禁用了 Wi-Fi，HoloLens 仍会搜索该空间。 但是，HoloLens 必须在空间数据库中搜索更多地图数据，并且可能需要更多时间才能找到全息影像。 如果没有 Wi-Fi 信息，HoloLens 必须将活动扫描与设备上存储的所有全息影像锚点和地图部分进行比较，以便找到地图的正确部分。

## 相关主题

- [空间映射设计](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping-design)
