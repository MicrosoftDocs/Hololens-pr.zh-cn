---
title: 使用 HoloLens（第 1 代）上的 3D 查看器 Beta 版
description: 介绍 HoloLens（第 1 代）上的 3D 查看器 Beta 版支持的文件类型和功能，以及如何使用该应用和解决出现的问题。
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.localizationpriority: high
ms.date: 10/30/2019
ms.reviewer: scooley
audience: ITPro
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 00e99d3f67e9e4371da12612b9b01c3ce58e71bd
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126034032"
---
# <a name="using-3d-viewer-beta-on-hololens-1st-gen"></a>使用 HoloLens（第 1 代）上的 3D 查看器 Beta 版

3D 查看器 Beta 版可用于在 HoloLens（第 1 代）上查看 3D 模型。 可以从 Microsoft Edge、OneDrive 和其他应用中打开并查看支持的 .fbx 文件。

>[!NOTE]
>本文适用于沉浸式 Unity 3D 查看器 Beta 版应用，该应用支持 .fbx 文件且仅在 HoloLens（第 1 代）上提供。 HoloLens 2 上预安装的 3D 查看器应用支持在混合现实主页中打开自定义 .glb 3D 模型（有关详细信息，请参阅[资产要求概述](/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)。

>[!IMPORTANT]
>虽然 Microsoft Store 中的 3D 查看器 Beta 版可能仍可用于 HoloLens（第 1 代），但已不处于活跃开发状态且不再受支持。

如果在 3D 查看器 Beta 版中打开 3D 模型时遇到问题，或 3D 模型的某些功能不受支持，请参阅下面的[支持的内容规范](#supported-content-specifications)。

若要生成或优化 3D 模型以使其能够用于 3D 查看器 Beta 版，请参阅下面的[为 3D 查看器 Beta 版优化 3D 模型](#optimizing-3d-models-for-3d-viewer-beta)。

在 HoloLens 上打开 3D 模型的方法有两种。 有关详细信息，请参阅下面的[查看 HoloLens 上的 FBX 文件](#viewing-fbx-files-on-hololens)。

如果在阅读这些主题相关的内容后仍遇到问题，请参阅下面的[故障排除](#troubleshooting)。

## <a name="supported-content-specifications"></a>支持的内容规范

### <a name="file-format"></a>文件格式

- FBX 格式
- 最高 FBX 版本 2015.1.0

### <a name="file-size"></a>文件大小

- 最小 5 KB
- 最大 500 MB

### <a name="geometry"></a>Geometry

- 仅多边形模型。 无细分曲面或 NURB
- 右手坐标系
- 不支持转换矩阵中的剪切

### <a name="textures"></a>纹理

- 纹理贴图必须嵌入 FBX 文件中
- 支持的图像格式
  - JPEG 和 PNG 图像
  - BMP 图像（24 位 RGB 真彩色）
  - TGA 图像（24 位 RGB 和 32 位 RGBQ 真彩色）
- 2048x2048 的最大纹理分辨率
- 每个网格最多一个漫射贴图、一个法线贴图和一个反射立方体贴图
- 漫射纹理中的 Alpha 通道会导致像素在低于 50% 时被丢弃

### <a name="animation"></a>动画

- 单个对象上的缩放/旋转/平移动画
- 蒙皮的骨骼（操纵式）动画
  - 每个顶点最多 4 条影响线

### <a name="materials"></a>材料

- 支持朗伯和 Phong 材料，参数可调
- 支持的朗伯材料属性
  - 主纹理（RGB + Alpha 测试）
  - 漫射颜色 (RGB)
  - 环境颜色 (RGB)
- 支持的 Phong 材料属性
  - 主纹理（RGB + Alpha 测试）
  - 漫射颜色 (RGB)
  - 环境颜色 (RGB)
  - 反射颜色 (RGB)
  - 有光泽
  - 具有反射性
- 不支持自定义材料
- 每个网格最多一种材料
- 最多一个材料层
- 每个文件最多 8 种材料

### <a name="file-and-model-limitations"></a>文件和模型限制

3D 查看器 Beta 版对文件大小以及可同时打开的模型、顶点和网格的数量有硬性限制：

- 每个模型的最大文件大小为 500 MB
- 顶点：所有打开的模型上共 600,000 个
- 网格：所有打开的模型上共 1,600 个
- 同一时间最多可打开 40 个模型

## <a name="optimizing-3d-models-for-3d-viewer-beta"></a>为 3D 查看器 Beta 版优化 3D 模型

### <a name="special-considerations"></a>特殊注意事项

- 避免在纹理贴图中使用黑色材料或黑色区域。 全息影像是由光构成的，因此 HoloLens 会将黑色（没有光）呈现为透明色。
- 从创建工具导出到 FBX 之前，请确保所有几何图形均可见且未锁定，并且没有关闭或模板化任何包含几何图形的图层。 不考虑可见性。
- 避免节点之间存在非常大的平移偏移（例如，100,000 个单位）。 这可能会导致模型在移动/缩放/旋转时抖动。

### <a name="performance-optimization"></a>性能优化

在创作内容时，请牢记性能，并在创作过程中在 HoloLens 上的 3D 查看器 Beta 版应用中进行验证，以获得最佳效果。 3D 查看器 Beta 版会实时呈现内容，性能则受 HoloLens 硬件功能的制约。  

3D 模型中有许多可影响性能的变量。 如果有超过 150,000 个顶点或超过 400 个网格，3D 查看器 Beta 版会在加载时显示警告。 动画可能会对其他打开的模型的性能产生影响。 3D 查看器 Beta 版还对可同时打开的模型、顶点和网格的总数有硬性限制（请参阅[文件和模型限制](#file-and-model-limitations)）。  

如果 3D 模型由于模型的复杂性而无法正常运行，请考虑：

- 减少多边形的数量
- 减少操纵式动画中的骨骼数
- 避免自遮挡

3D 查看器 Beta 版支持双面呈现，不过出于性能原因，默认情况下该功能处于关闭状态。 可以通过“详细信息”页上的“双面”按钮启用此功能 。 为获得最佳性能，请避免需要在内容中进行双面呈现的情况。

### <a name="validating-your-3d-model"></a>验证 3D 模型

在 HoloLens 的 3D 查看器 Beta 版中打开模型以对其进行验证。 选择“详细信息”按钮以查看模型的特征和有关不受支持内容（如果存在）的警告。

### <a name="rendering-3d-models-with-true-to-life-dimensions"></a>使用真实的维度呈现 3D 模型

默认情况下，3D 查看器 Beta 版会以合适的尺寸和用户相对位置显示 3D 模型。 但是，如果使用真实的测量数据呈现 3D 模型很重要（例如，在评估房间中的家具模型时），则内容创建者可以在文件的元数据中设置一个标志，以防止应用程序和用户调整该模型的大小。

若要防止模型缩放，请向名为 Microsoft_DisableScale 的场景中的任何对象添加 Boolean 自定义属性，并将其设置为 true。 然后，3D 查看器 Beta 版会考虑存储到 FBX 文件中的 FbxSystemUnit 信息。 3D 查看器 Beta 版中的缩放比例为每 FBX 单位 1 米。

## <a name="viewing-fbx-files-on-hololens"></a>在 HoloLens 上查看 FBX 文件

### <a name="open-an-fbx-file-from-microsoft-edge"></a>从 Microsoft Edge 打开 FBX 文件

你可以在 HoloLens 上使用 Microsoft Edge 直接从网站打开 FBX 文件。

1. 在 Microsoft Edge 中，导航到包含要查看的 FBX 文件的网页。
1. 选择该文件，以进行下载。
1. 下载完成后，选择 Microsoft Edge 中的“打开”按钮以在 3D 查看器 Beta 版中打开该文件。

以后可在 Microsoft Edge 中使用“下载”，再次访问和打开下载的文件。 若要保存 3D 模型并确保后续访问，请在电脑上下载相应文件并将其保存到你的 OneDrive 帐户。 然后便可在 HoloLens 上从 OneDrive 应用打开该文件。

> [!NOTE]
> 一些具有可下载 FBX 模型的网站会以压缩 ZIP 格式提供这些模型。 3D 查看器 Beta 版无法直接打开 ZIP 文件。 请改为使用电脑解压缩 FBX 文件，并将其保存到你的 OneDrive 帐户。 然后便可在 HoloLens 上从 OneDrive 应用打开该文件。

### <a name="open-an-fbx-file-from-onedrive"></a>从 OneDrive 打开 FBX 文件

你可以在 HoloLens 上使用 OneDrive 应用从 OneDrive 打开 FBX 文件。 请确保已在 HoloLens 上使用 Microsoft Store 应用安装 OneDrive，并且已在电脑上将 FBX 文件上载到 OneDrive。

上载到 OneDrive 中后，可通过以下两种方式在 HoloLens 上使用 3D 查看器 Beta 版打开 FBX 文件：

- 在 HoloLens 上启动 OneDrive 并选择 FBX 文件，从而将其在 3D 查看器 Beta 版中打开。
- 启动 3D 查看器 Beta 版，隔空敲击以显示工具栏，然后选择“打开文件”。 OneDrive 将启动，允许你选择 FBX 文件。

## <a name="troubleshooting"></a>疑难解答

### <a name="i-see-a-warning-when-i-open-a-3d-model"></a>我在打开 3D 模型时看到警告

如果尝试打开的 3D 模型中包含 3D 查看器 Beta 版不支持的功能，或者模型太复杂，可能会影响性能，则将显示一条警告。 3D 查看器 Beta 版仍将加载 3D 模型，但性能或视觉保真度可能会受损。

有关详细信息，请参阅[支持的内容规范](#supported-content-specifications)和[为 3D 查看器 Beta 版优化 3D 模型](#optimizing-3d-models-for-3d-viewer-beta)。

### <a name="i-see-a-warning-and-the-3d-model-doesnt-load"></a>我看到警告，且 3D 模型未加载

当 3D 查看器 Beta 版因复杂性或文件大小而无法加载 3D 模型，或者 FBX 文件损坏或无效时，你将看到一条错误消息。 或者，如果达到可同时打开的模型、顶点或网格总数的上限，则也会显示一条错误消息。  

有关详细信息，请参阅[支持的内容规范](#supported-content-specifications)和[文件和模型限制](#file-and-model-limitations)。

### <a name="my-3d-model-loads-but-does-not-appear-as-expected"></a>我的 3D 模型已加载，但未按预期方式显示

如果 3D 模型在 3D 查看器 Beta 版中的显示效果与预期不符，请隔空敲击以显示工具栏，然后选择“详细信息”。 3D 查看器 Beta 版不支持的文件部分将突出显示为警告。

最常见的问题是纹理缺失，这可能是因为它们未嵌入 FBX 文件中。 在这种情况下，模型将显示为白色。 此问题可在创建过程中解决，方法是：在选中嵌入纹理选项的情况下从创建工具导出到 FBX。

有关详细信息，请参阅[支持的内容规范](#supported-content-specifications)和[为 3D 查看器 Beta 版优化 3D 模型](#optimizing-3d-models-for-3d-viewer-beta)。

### <a name="i-experience-performance-drops-while-viewing-my-3d-model"></a>查看我的 3D 模型时出现性能下降

在加载和查看 3D 模型时，性能可能会受到以下因素的影响：模型的复杂性、同时打开的模型数量或具有活动动画的模型数量。

有关详细信息，请参阅[为 3D 查看器 Beta 版优化 3D 模型](#optimizing-3d-models-for-3d-viewer-beta)和[文件和模型限制](#file-and-model-limitations)。

### <a name="when-i-open-an-fbx-file-on-hololens-it-doesnt-open-in-3d-viewer-beta"></a>当我在 HoloLens 上打开 FBX 文件时，该文件未在 3D 查看器 Beta 版中打开

3D 查看器 Beta 版会在安装后自动与 .fbx 文件扩展名相关联。

如果你在尝试打开 FBX 文件时看到一个对话框，该对话框指引你访问 Microsoft Store，则表明 HoloLens 上目前没有与 .fbx 文件扩展名相关联的应用。

请验证是否安装了 3D 查看器 Beta 版。 如果未安装，请在 HoloLens 上从 Microsoft Store 下载。

如果已安装 3D 查看器 Beta 版，请启动 3D 查看器 Beta 版，然后再次尝试打开文件。 如果问题仍然存在，请卸载并重新安装 3D 查看器 Beta 版。 这将使 .fbx 文件扩展名与 3D 查看器 Beta 版重新关联。

如果尝试打开 FBX 文件时打开了 3D 查看器 Beta 版以外的其他应用，则该应用可能是在 3D 查看器 Beta 版之后安装的，并且已接管与 .fbx 文件扩展名的关联。 如果你更喜欢将 3D 查看器 Beta 版与 .fbx 文件扩展名相关联，请卸载并重新安装 3D 查看器 Beta 版。

### <a name="the-open-file-button-in-3d-viewer-beta-doesnt-launch-an-app"></a>3D 查看器 Beta 版中的“打开文件”按钮无法启动应用

“打开文件”按钮将打开与 HoloLens 上的文件选取器功能相关联的应用。 如果已安装 OneDrive，“打开文件”按钮将启动 OneDrive。 但是，如果 HoloLens 上当前没有安装与文件选取器功能相关联的应用，将转到 Microsoft Store。

如果“打开文件”按钮启动的是 OneDrive 之外的应用，则该应用可能是在 OneDrive 之后安装的，并且已接管与文件选取器功能的关联。 在 3D 查看器 Beta 版中选择“打开文件”按钮时，如果你更喜欢启动 OneDrive，请卸载并重新安装 OneDrive。

如果“打开文件”按钮未处于活动状态，则可能已达到同一时间可在 3D 查看器 Beta 版中打开的模型数量上限。 如果已在 3D 查看器 Beta 版中打开了 40 个模型，则需要关闭一些模型，然后才能打开其他模型。

## <a name="additional-resources"></a>其他资源

- [支持论坛](http://forums.hololens.com/categories/3d-viewer-beta) - 仅用于存档目的。 此论坛不再有效。
- [第三方声明](https://www.microsoft.com/{lang-locale}/legal/products)
