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
ms.openlocfilehash: f5481d6466459667deb99232fdd67c4491798cbe
ms.sourcegitcommit: 1b19b0eb552189d7c50617bbdf3a102d3c85ee0e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016283"
---
# <span data-ttu-id="66bf3-103">使用 HoloLens（第 1 代）上的 3D 查看器 Beta 版</span><span class="sxs-lookup"><span data-stu-id="66bf3-103">Using 3D Viewer Beta on HoloLens (1st gen)</span></span>

<span data-ttu-id="66bf3-104">3D 查看器 Beta 版可用于在 HoloLens（第 1 代）上查看 3D 模型。</span><span class="sxs-lookup"><span data-stu-id="66bf3-104">3D Viewer Beta lets you view 3D models on HoloLens (1st gen).</span></span> <span data-ttu-id="66bf3-105">你可以从 Microsoft Edge、OneDrive 和其他应用打开并查看支持的\*\* .fbx 文件。</span><span class="sxs-lookup"><span data-stu-id="66bf3-105">You can open and view *supported* .fbx files from Microsoft Edge, OneDrive, and other apps.</span></span>

>[!NOTE]
><span data-ttu-id="66bf3-106">本文适用于沉浸式 Unity **3D 查看器 Beta 版**应用，该应用支持 .fbx 文件且仅在 HoloLens（第 1 代）上提供。</span><span class="sxs-lookup"><span data-stu-id="66bf3-106">This article applies to the immersive Unity **3D Viewer Beta** app, which supports .fbx files and is only available on HoloLens (1st gen).</span></span> <span data-ttu-id="66bf3-107">HoloLens 2 上预装的 3D 查看器\*\*\*\* 应用支持在混合现实主页中打开自定义 .glb 3D 模型（有关详细信息，请参阅[资产需求概述](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview)。</span><span class="sxs-lookup"><span data-stu-id="66bf3-107">The pre-installed **3D Viewer** app on HoloLens 2 supports opening custom .glb 3D models in the mixed reality home (see [Asset requirements overview](https://docs.microsoft.com/windows/mixed-reality/creating-3d-models-for-use-in-the-windows-mixed-reality-home#asset-requirements-overview) for more details.</span></span>

>[!IMPORTANT]
><span data-ttu-id="66bf3-108">虽然 3D 查看器 Beta 版可能在 Microsoft Store 中仍可用于 HoloLens（第一代），但它不再处于活动开发阶段并且不再受支持。</span><span class="sxs-lookup"><span data-stu-id="66bf3-108">While 3D Viewer Beta may remain available in the Microsoft Store for HoloLens (1st gen), it is no longer in active development and is no longer supported.</span></span>

<span data-ttu-id="66bf3-109">如果在 3D 查看器 Beta 版中打开 3D 模型时遇到问题，或 3D 模型的某些功能不受支持，请参阅下面的[支持内容规范](#supported-content-specifications)。</span><span class="sxs-lookup"><span data-stu-id="66bf3-109">If you're having trouble opening a 3D model in 3D Viewer Beta, or certain features of your 3D model are unsupported, see [Supported content specifications](#supported-content-specifications) below.</span></span>

<span data-ttu-id="66bf3-110">若要生成或优化 3D 模型以便通过 3D 查看器 Beta 版进行使用，请参阅下面的[为 3D 查看器 Beta 版优化 3D 模型](#optimizing-3d-models-for-3d-viewer-beta)。</span><span class="sxs-lookup"><span data-stu-id="66bf3-110">To build or optimize 3D models for use with 3D Viewer Beta, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) below.</span></span>

<span data-ttu-id="66bf3-111">在 HoloLens 上打开 3D 模型的方法有两种。</span><span class="sxs-lookup"><span data-stu-id="66bf3-111">There are two ways to open a 3D model on HoloLens.</span></span> <span data-ttu-id="66bf3-112">请参阅下面的[在 HoloLens 上查看 FBX 文件](#viewing-fbx-files-on-hololens)，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="66bf3-112">See [Viewing FBX files on HoloLens](#viewing-fbx-files-on-hololens) below to learn more.</span></span>

<span data-ttu-id="66bf3-113">如果阅读这些主题后仍有问题，请参阅下面的[疑难解答](#troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="66bf3-113">If you're having trouble after reading these topics, see [Troubleshooting](#troubleshooting) below.</span></span>

## <span data-ttu-id="66bf3-114">支持内容规范</span><span class="sxs-lookup"><span data-stu-id="66bf3-114">Supported content specifications</span></span>

### <span data-ttu-id="66bf3-115">文件格式</span><span class="sxs-lookup"><span data-stu-id="66bf3-115">File format</span></span>

- <span data-ttu-id="66bf3-116">FBX 格式</span><span class="sxs-lookup"><span data-stu-id="66bf3-116">FBX format</span></span>
- <span data-ttu-id="66bf3-117">最高 FBX 版本 2015.1.0</span><span class="sxs-lookup"><span data-stu-id="66bf3-117">Maximum FBX release 2015.1.0</span></span>

### <span data-ttu-id="66bf3-118">文件大小</span><span class="sxs-lookup"><span data-stu-id="66bf3-118">File size</span></span>

- <span data-ttu-id="66bf3-119">最小 5 KB</span><span class="sxs-lookup"><span data-stu-id="66bf3-119">Minimum 5 KB</span></span>
- <span data-ttu-id="66bf3-120">最大 500 MB</span><span class="sxs-lookup"><span data-stu-id="66bf3-120">Maximum 500 MB</span></span>

### <span data-ttu-id="66bf3-121">几何图形</span><span class="sxs-lookup"><span data-stu-id="66bf3-121">Geometry</span></span>

- <span data-ttu-id="66bf3-122">仅多边形模型。</span><span class="sxs-lookup"><span data-stu-id="66bf3-122">Polygonal models only.</span></span> <span data-ttu-id="66bf3-123">无细分曲面或 NURB</span><span class="sxs-lookup"><span data-stu-id="66bf3-123">No subdivision surfaces or NURBs</span></span>
- <span data-ttu-id="66bf3-124">右手坐标系</span><span class="sxs-lookup"><span data-stu-id="66bf3-124">Right-handed coordinate system</span></span>
- <span data-ttu-id="66bf3-125">不支持转换矩阵中的剪切</span><span class="sxs-lookup"><span data-stu-id="66bf3-125">Shear in transformation matrices is not supported</span></span>

### <span data-ttu-id="66bf3-126">纹理</span><span class="sxs-lookup"><span data-stu-id="66bf3-126">Textures</span></span>

- <span data-ttu-id="66bf3-127">纹理贴图必须嵌入 FBX 文件中</span><span class="sxs-lookup"><span data-stu-id="66bf3-127">Texture maps must be embedded in the FBX file</span></span>
- <span data-ttu-id="66bf3-128">支持的图像格式</span><span class="sxs-lookup"><span data-stu-id="66bf3-128">Supported image formats</span></span>
  - <span data-ttu-id="66bf3-129">JPEG 和 PNG 图像</span><span class="sxs-lookup"><span data-stu-id="66bf3-129">JPEG and PNG images</span></span>
  - <span data-ttu-id="66bf3-130">BMP 图像（24 位 RGB 真彩色）</span><span class="sxs-lookup"><span data-stu-id="66bf3-130">BMP images (24-bit RGB true-color)</span></span>
  - <span data-ttu-id="66bf3-131">TGA 图像（24 位 RGB 和 32 位 RGBQ 真彩色）</span><span class="sxs-lookup"><span data-stu-id="66bf3-131">TGA images (24-bit RGB and 32-bit RGBQ true-color)</span></span>
- <span data-ttu-id="66bf3-132">2048x2048 的最大纹理分辨率</span><span class="sxs-lookup"><span data-stu-id="66bf3-132">Maximum texture resolution of 2048x2048</span></span>
- <span data-ttu-id="66bf3-133">每个网格最多一个漫射贴图、一个法线贴图和一个反射立方体贴图</span><span class="sxs-lookup"><span data-stu-id="66bf3-133">Maximum of one diffuse map, one normal map, and one reflection cube map per mesh</span></span>
- <span data-ttu-id="66bf3-134">漫射纹理中的 Alpha 通道会导致像素在低于 50% 时被丢弃</span><span class="sxs-lookup"><span data-stu-id="66bf3-134">Alpha channel in diffuse textures causes pixels to be discarded if below 50%</span></span>

### <span data-ttu-id="66bf3-135">动画</span><span class="sxs-lookup"><span data-stu-id="66bf3-135">Animation</span></span>

- <span data-ttu-id="66bf3-136">单个对象上的缩放/旋转/平移动画</span><span class="sxs-lookup"><span data-stu-id="66bf3-136">Scale/rotation/translation animation on individual objects</span></span>
- <span data-ttu-id="66bf3-137">蒙皮的骨骼（操纵式）动画</span><span class="sxs-lookup"><span data-stu-id="66bf3-137">Skeletal (rigged) animation with skinning</span></span>
  - <span data-ttu-id="66bf3-138">每个顶点最多 4 条影响线</span><span class="sxs-lookup"><span data-stu-id="66bf3-138">Maximum of 4 influences per vertex</span></span>

### <span data-ttu-id="66bf3-139">材料</span><span class="sxs-lookup"><span data-stu-id="66bf3-139">Materials</span></span>

- <span data-ttu-id="66bf3-140">支持朗伯和 Phong 材料，参数可调</span><span class="sxs-lookup"><span data-stu-id="66bf3-140">Lambert and Phong materials are supported, with adjustable parameters</span></span>
- <span data-ttu-id="66bf3-141">支持的朗伯材料属性</span><span class="sxs-lookup"><span data-stu-id="66bf3-141">Supported material properties for Lambert</span></span>
  - <span data-ttu-id="66bf3-142">主纹理（RGB + Alpha 测试）</span><span class="sxs-lookup"><span data-stu-id="66bf3-142">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="66bf3-143">漫射颜色 (RGB)</span><span class="sxs-lookup"><span data-stu-id="66bf3-143">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="66bf3-144">环境颜色 (RGB)</span><span class="sxs-lookup"><span data-stu-id="66bf3-144">Ambient Color (RGB)</span></span>
- <span data-ttu-id="66bf3-145">支持的 Phong 材料属性</span><span class="sxs-lookup"><span data-stu-id="66bf3-145">Supported material properties for Phong</span></span>
  - <span data-ttu-id="66bf3-146">主纹理（RGB + Alpha 测试）</span><span class="sxs-lookup"><span data-stu-id="66bf3-146">Main Texture (RGB + Alpha Test)</span></span>
  - <span data-ttu-id="66bf3-147">漫射颜色 (RGB)</span><span class="sxs-lookup"><span data-stu-id="66bf3-147">Diffuse Color (RGB)</span></span>
  - <span data-ttu-id="66bf3-148">环境颜色 (RGB)</span><span class="sxs-lookup"><span data-stu-id="66bf3-148">Ambient Color (RGB)</span></span>
  - <span data-ttu-id="66bf3-149">反射颜色 (RGB)</span><span class="sxs-lookup"><span data-stu-id="66bf3-149">Specular Color (RGB)</span></span>
  - <span data-ttu-id="66bf3-150">有光泽</span><span class="sxs-lookup"><span data-stu-id="66bf3-150">Shininess</span></span>
  - <span data-ttu-id="66bf3-151">具有反射性</span><span class="sxs-lookup"><span data-stu-id="66bf3-151">Reflectivity</span></span>
- <span data-ttu-id="66bf3-152">不支持自定义材料</span><span class="sxs-lookup"><span data-stu-id="66bf3-152">Custom materials are not supported</span></span>
- <span data-ttu-id="66bf3-153">每个网格最多一种材料</span><span class="sxs-lookup"><span data-stu-id="66bf3-153">Maximum of one material per mesh</span></span>
- <span data-ttu-id="66bf3-154">最多一个材料层</span><span class="sxs-lookup"><span data-stu-id="66bf3-154">Maximum of one material layer</span></span>
- <span data-ttu-id="66bf3-155">每个文件最多 8 种材料</span><span class="sxs-lookup"><span data-stu-id="66bf3-155">Maximum of 8 materials per file</span></span>

### <span data-ttu-id="66bf3-156">文件和模型限制</span><span class="sxs-lookup"><span data-stu-id="66bf3-156">File and model limitations</span></span>

<span data-ttu-id="66bf3-157">3D 查看器 Beta 版对文件大小以及可同时打开的模型、顶点和网格的数量有硬性限制：</span><span class="sxs-lookup"><span data-stu-id="66bf3-157">There are hard limits on the size of files, as well as the number of models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta:</span></span>

- <span data-ttu-id="66bf3-158">每个模型的最大文件大小为 500 MB</span><span class="sxs-lookup"><span data-stu-id="66bf3-158">500 MB maximum file size per model</span></span>
- <span data-ttu-id="66bf3-159">顶点：所有打开的模型上共 600,000 个</span><span class="sxs-lookup"><span data-stu-id="66bf3-159">Vertices: 600,000 combined on all open models</span></span>
- <span data-ttu-id="66bf3-160">网格：所有打开的模型上共 1,600 个</span><span class="sxs-lookup"><span data-stu-id="66bf3-160">Meshes: 1,600 combined on all open models</span></span>
- <span data-ttu-id="66bf3-161">同一时间最多可打开 40 个模型</span><span class="sxs-lookup"><span data-stu-id="66bf3-161">Maximum of 40 models open at one time</span></span>

## <span data-ttu-id="66bf3-162">为 3D 查看器 Beta 版优化 3D 模型</span><span class="sxs-lookup"><span data-stu-id="66bf3-162">Optimizing 3D models for 3D Viewer Beta</span></span>

### <span data-ttu-id="66bf3-163">特殊注意事项</span><span class="sxs-lookup"><span data-stu-id="66bf3-163">Special considerations</span></span>

- <span data-ttu-id="66bf3-164">避免在纹理贴图中使用黑色材料或黑色区域。</span><span class="sxs-lookup"><span data-stu-id="66bf3-164">Avoid black materials or black areas in texture maps.</span></span> <span data-ttu-id="66bf3-165">全息影像是由光构成的，因此 HoloLens 会将黑色（没有光）呈现为透明色。</span><span class="sxs-lookup"><span data-stu-id="66bf3-165">Holograms are made of light, thus HoloLens renders black (the absence of light) as transparent.</span></span>
- <span data-ttu-id="66bf3-166">从创建工具导出到 FBX 之前，请确保所有几何图形均可见且未锁定，并且没有关闭或模板化任何包含几何图形的图层。</span><span class="sxs-lookup"><span data-stu-id="66bf3-166">Before exporting to FBX from your creation tool, ensure all geometry is visible and unlocked and no layers that contain geometry are turned off or templated.</span></span> <span data-ttu-id="66bf3-167">不考虑可见性。</span><span class="sxs-lookup"><span data-stu-id="66bf3-167">Visibility is not respected.</span></span>
- <span data-ttu-id="66bf3-168">避免节点之间存在非常大的平移偏移（例如，100,000 个单位）。</span><span class="sxs-lookup"><span data-stu-id="66bf3-168">Avoid very large translation offsets between nodes (for example, 100,000 units).</span></span> <span data-ttu-id="66bf3-169">这可能会导致模型在移动/缩放/旋转时抖动。</span><span class="sxs-lookup"><span data-stu-id="66bf3-169">This can cause the model to jitter while being moved/scaled/rotated.</span></span>

### <span data-ttu-id="66bf3-170">性能优化</span><span class="sxs-lookup"><span data-stu-id="66bf3-170">Performance optimization</span></span>

<span data-ttu-id="66bf3-171">在创作内容时，请牢记性能，并在创作过程中在 HoloLens 上的 3D 查看器 Beta 版应用中进行验证，以获得最佳效果。</span><span class="sxs-lookup"><span data-stu-id="66bf3-171">Keep performance in mind while authoring content and validate in the 3D Viewer Beta app on HoloLens during the authoring process for best results.</span></span> <span data-ttu-id="66bf3-172">3D 查看器 Beta 版会实时呈现内容，性能则受 HoloLens 硬件功能的制约。</span><span class="sxs-lookup"><span data-stu-id="66bf3-172">3D Viewer Beta renders content real-time and performance is subject to HoloLens hardware capabilities.</span></span>  

<span data-ttu-id="66bf3-173">3D 模型中有许多可影响性能的变量。</span><span class="sxs-lookup"><span data-stu-id="66bf3-173">There are many variables in a 3D model that can impact performance.</span></span> <span data-ttu-id="66bf3-174">如果有超过 150,000 个顶点或超过 400 个网格，3D 查看器 Beta 版会在加载时显示警告。</span><span class="sxs-lookup"><span data-stu-id="66bf3-174">3D Viewer Beta will show a warning on load if there are more than 150,000 vertices or more than 400 meshes.</span></span> <span data-ttu-id="66bf3-175">动画可能会对其他打开的模型的性能产生影响。</span><span class="sxs-lookup"><span data-stu-id="66bf3-175">Animations can have an impact on the performance of other open models.</span></span> <span data-ttu-id="66bf3-176">3D 查看器 Beta 版还对可同时打开的模型、顶点和网格的总数有硬性限制（请参阅[文件和模型限制](#file-and-model-limitations)）。</span><span class="sxs-lookup"><span data-stu-id="66bf3-176">There are also hard limits on the total number models, vertices, and meshes that can be open simultaneously in 3D Viewer Beta (see [File and model limitations](#file-and-model-limitations)).</span></span>  

<span data-ttu-id="66bf3-177">如果 3D 模型由于模型的复杂性而无法正常运行，请考虑：</span><span class="sxs-lookup"><span data-stu-id="66bf3-177">If the 3D model isn't running well due to model complexity, consider:</span></span>

- <span data-ttu-id="66bf3-178">减少多边形的数量</span><span class="sxs-lookup"><span data-stu-id="66bf3-178">Reducing polygon count</span></span>
- <span data-ttu-id="66bf3-179">减少操纵式动画中的骨骼数</span><span class="sxs-lookup"><span data-stu-id="66bf3-179">Reducing number of bones in rigged animation</span></span>
- <span data-ttu-id="66bf3-180">避免自遮挡</span><span class="sxs-lookup"><span data-stu-id="66bf3-180">Avoiding self-occlusion</span></span>

<span data-ttu-id="66bf3-181">3D 查看器 Beta 版支持双面呈现，不过出于性能原因，默认情况下该功能处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="66bf3-181">Double-sided rendering is supported in 3D Viewer Beta, although it is turned off by default for performance reasons.</span></span> <span data-ttu-id="66bf3-182">可通过“详细信息\*\*\*\*”页面上的“双面”\*\*\*\* 按钮启用此功能。</span><span class="sxs-lookup"><span data-stu-id="66bf3-182">This can be turned on via the **Double Sided** button on the **Details** page.</span></span> <span data-ttu-id="66bf3-183">为获得最佳性能，请避免需要在内容中进行双面呈现的情况。</span><span class="sxs-lookup"><span data-stu-id="66bf3-183">For best performance, avoid the need for double-sided rendering in your content.</span></span>

### <span data-ttu-id="66bf3-184">验证 3D 模型</span><span class="sxs-lookup"><span data-stu-id="66bf3-184">Validating your 3D model</span></span>

<span data-ttu-id="66bf3-185">在 HoloLens 的 3D 查看器 Beta 版中打开模型以对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="66bf3-185">Validate your model by opening it in 3D Viewer Beta on HoloLens.</span></span> <span data-ttu-id="66bf3-186">选择“详细信息”\*\*\*\* 按钮以查看模型的特征和有关不受支持内容（如果存在）的警告。</span><span class="sxs-lookup"><span data-stu-id="66bf3-186">Select the **Details** button to view your model's characteristics and warnings of unsupported content (if present).</span></span>

### <span data-ttu-id="66bf3-187">使用真实的维度呈现 3D 模型</span><span class="sxs-lookup"><span data-stu-id="66bf3-187">Rendering 3D models with true-to-life dimensions</span></span>

<span data-ttu-id="66bf3-188">默认情况下，3D 查看器 Beta 版会以合适的尺寸和用户相对位置显示 3D 模型。</span><span class="sxs-lookup"><span data-stu-id="66bf3-188">By default, 3D Viewer Beta displays 3D models at a comfortable size and position relative to the user.</span></span> <span data-ttu-id="66bf3-189">但是，如果使用真实的测量数据呈现 3D 模型很重要（例如，在评估房间中的家具模型时），则内容创建者可以在文件的元数据中设置一个标志，以防止应用程序和用户调整该模型的大小。</span><span class="sxs-lookup"><span data-stu-id="66bf3-189">However, if rendering a 3D model with true-to-life measurements is important (for example, when evaluating furniture models in a room), the content creator can set a flag within the file's metadata to prevent resizing of that model by both the application and the user.</span></span>

<span data-ttu-id="66bf3-190">若要防止模型缩放，请向名为 Microsoft_DisableScale 的场景中的任何对象添加 Boolean 自定义属性，并将其设置为 true。</span><span class="sxs-lookup"><span data-stu-id="66bf3-190">To prevent scaling of the model, add a Boolean custom attribute to any object in the scene named Microsoft_DisableScale and set it to true.</span></span> <span data-ttu-id="66bf3-191">然后，3D 查看器 Beta 版会考虑存储到 FBX 文件中的 FbxSystemUnit 信息。</span><span class="sxs-lookup"><span data-stu-id="66bf3-191">3D Viewer Beta will then respect the FbxSystemUnit information baked into the FBX file.</span></span> <span data-ttu-id="66bf3-192">3D 查看器 Beta 版中的缩放比例为每 FBX 单位 1 米。</span><span class="sxs-lookup"><span data-stu-id="66bf3-192">Scale in 3D Viewer Beta is 1 meter per FBX unit.</span></span>

## <span data-ttu-id="66bf3-193">在 HoloLens 上查看 FBX 文件</span><span class="sxs-lookup"><span data-stu-id="66bf3-193">Viewing FBX files on HoloLens</span></span>

### <span data-ttu-id="66bf3-194">从 Microsoft Edge 打开 FBX 文件</span><span class="sxs-lookup"><span data-stu-id="66bf3-194">Open an FBX file from Microsoft Edge</span></span>

<span data-ttu-id="66bf3-195">你可以在 HoloLens 上使用 Microsoft Edge 直接从网站打开 FBX 文件。</span><span class="sxs-lookup"><span data-stu-id="66bf3-195">FBX files can be opened directly from a website using Microsoft Edge on HoloLens.</span></span>

1. <span data-ttu-id="66bf3-196">在 Microsoft Edge 中，导航到包含要查看的 FBX 文件的网页。</span><span class="sxs-lookup"><span data-stu-id="66bf3-196">In Microsoft Edge, navigate to the webpage containing the FBX file you want to view.</span></span>
1. <span data-ttu-id="66bf3-197">选择该文件，以进行下载。</span><span class="sxs-lookup"><span data-stu-id="66bf3-197">Select the file to download it.</span></span>
1. <span data-ttu-id="66bf3-198">下载完成后，选择 Microsoft Edge 中的“**打开**”按钮以在 3D 查看器 Beta 版中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="66bf3-198">When the download is complete, select the **Open** button in Microsoft Edge to open the file in 3D Viewer Beta.</span></span>

<span data-ttu-id="66bf3-199">以后可在 Microsoft Edge 中使用“下载”，再次访问和打开下载的文件。</span><span class="sxs-lookup"><span data-stu-id="66bf3-199">The downloaded file can be accessed and opened again later by using Downloads in Microsoft Edge.</span></span> <span data-ttu-id="66bf3-200">若要保存 3D 模型并确保后续访问，请在电脑上下载相应文件并将其保存到你的 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="66bf3-200">To save a 3D model and ensure continued access, download the file on your PC and save it to your OneDrive account.</span></span> <span data-ttu-id="66bf3-201">然后便可在 HoloLens 上从 OneDrive 应用打开该文件。</span><span class="sxs-lookup"><span data-stu-id="66bf3-201">The file can then be opened from the OneDrive app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="66bf3-202">一些具有可下载 FBX 模型的网站会以压缩 ZIP 格式提供这些模型。</span><span class="sxs-lookup"><span data-stu-id="66bf3-202">Some websites with downloadable FBX models provide them in compressed ZIP format.</span></span> <span data-ttu-id="66bf3-203">3D 查看器 Beta 版无法直接打开 ZIP 文件。</span><span class="sxs-lookup"><span data-stu-id="66bf3-203">3D Viewer Beta cannot open ZIP files directly.</span></span> <span data-ttu-id="66bf3-204">请改为使用电脑解压缩 FBX 文件，并将其保存到你的 OneDrive 帐户。</span><span class="sxs-lookup"><span data-stu-id="66bf3-204">Instead, use your PC to extract the FBX file and save it to your OneDrive account.</span></span> <span data-ttu-id="66bf3-205">然后便可在 HoloLens 上从 OneDrive 应用打开该文件。</span><span class="sxs-lookup"><span data-stu-id="66bf3-205">The file can then be opened from the OneDrive app on HoloLens.</span></span>

### <span data-ttu-id="66bf3-206">从 OneDrive 打开 FBX 文件</span><span class="sxs-lookup"><span data-stu-id="66bf3-206">Open an FBX file from OneDrive</span></span>

<span data-ttu-id="66bf3-207">你可以在 HoloLens 上使用 OneDrive 应用从 OneDrive 打开 FBX 文件。</span><span class="sxs-lookup"><span data-stu-id="66bf3-207">FBX files can be opened from OneDrive by using the OneDrive app on HoloLens.</span></span> <span data-ttu-id="66bf3-208">请确保已在 HoloLens 上使用 Microsoft Store 应用安装 OneDrive，并且已在电脑上将 FBX 文件上载到 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="66bf3-208">Be sure you've installed OneDrive using Microsoft Store app on HoloLens and that you've already uploaded the FBX file to OneDrive on your PC.</span></span>

<span data-ttu-id="66bf3-209">上载到 OneDrive 中后，可通过以下两种方式在 HoloLens 上使用 3D 查看器 Beta 版打开 FBX 文件：</span><span class="sxs-lookup"><span data-stu-id="66bf3-209">Once in OneDrive, FBX files can be opened on HoloLens using 3D Viewer Beta in one of two ways:</span></span>

- <span data-ttu-id="66bf3-210">在 HoloLens 上启动 OneDrive 并选择 FBX 文件，从而将其在 3D 查看器 Beta 版中打开。</span><span class="sxs-lookup"><span data-stu-id="66bf3-210">Launch OneDrive on HoloLens and select the FBX file to open it in 3D Viewer Beta.</span></span>
- <span data-ttu-id="66bf3-211">启动 3D 查看器 Beta 版，隔空敲击以显示工具栏，然后选择“**打开文件**”。</span><span class="sxs-lookup"><span data-stu-id="66bf3-211">Launch 3D Viewer Beta, air tap to show the toolbar, and select **Open File**.</span></span> <span data-ttu-id="66bf3-212">OneDrive 将启动，允许你选择 FBX 文件。</span><span class="sxs-lookup"><span data-stu-id="66bf3-212">OneDrive will launch, allowing you to select an FBX file.</span></span>

## <span data-ttu-id="66bf3-213">疑难解答</span><span class="sxs-lookup"><span data-stu-id="66bf3-213">Troubleshooting</span></span>

### <span data-ttu-id="66bf3-214">我在打开 3D 模型时看到警告</span><span class="sxs-lookup"><span data-stu-id="66bf3-214">I see a warning when I open a 3D model</span></span>

<span data-ttu-id="66bf3-215">如果尝试打开的 3D 模型中包含 3D 查看器 Beta 版不支持的功能，或者模型太复杂，可能会影响性能，则将显示一条警告。</span><span class="sxs-lookup"><span data-stu-id="66bf3-215">You will see a warning if you attempt to open a 3D model that contains features that are not supported by 3D Viewer Beta, or if the model is too complex and performance may be affected.</span></span> <span data-ttu-id="66bf3-216">3D 查看器 Beta 版仍将加载 3D 模型，但性能或视觉保真度可能会受损。</span><span class="sxs-lookup"><span data-stu-id="66bf3-216">3D Viewer Beta will still load the 3D model, but performance or visual fidelity may be compromised.</span></span>

<span data-ttu-id="66bf3-217">有关详细信息，请参阅[支持内容规范](#supported-content-specifications)和[为 3D 查看器 Beta 版优化 3D 模型](#optimizing-3d-models-for-3d-viewer-beta)。</span><span class="sxs-lookup"><span data-stu-id="66bf3-217">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <span data-ttu-id="66bf3-218">我看到警告，且 3D 模型未加载</span><span class="sxs-lookup"><span data-stu-id="66bf3-218">I see a warning and the 3D model doesn't load</span></span>

<span data-ttu-id="66bf3-219">当 3D 查看器 Beta 版因复杂性或文件大小而无法加载 3D 模型，或者 FBX 文件损坏或无效时，你将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="66bf3-219">You will see an error message when 3D Viewer Beta cannot load a 3D model due to complexity or file size, or if the FBX file is corrupt or invalid.</span></span> <span data-ttu-id="66bf3-220">或者，如果达到可同时打开的模型、顶点或网格总数的上限，则也会显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="66bf3-220">You will also see an error message if you have reached the limit on the total number of models, vertices, or meshes that can be open simultaneously.</span></span>  

<span data-ttu-id="66bf3-221">有关详细信息，请参阅[支持内容规范](#supported-content-specifications)和[文件和模型限制](#file-and-model-limitations)。</span><span class="sxs-lookup"><span data-stu-id="66bf3-221">For more info, see [Supported content specifications](#supported-content-specifications) and [File and model limitations](#file-and-model-limitations).</span></span>

### <span data-ttu-id="66bf3-222">我的 3D 模型已加载，但未按预期方式显示</span><span class="sxs-lookup"><span data-stu-id="66bf3-222">My 3D model loads, but does not appear as expected</span></span>

<span data-ttu-id="66bf3-223">如果 3D 模型在 3D 查看器 Beta 版中的显示效果与预期不符，请隔空敲击以显示工具栏，然后选择“**详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="66bf3-223">If your 3D model does not look as expected in 3D Viewer Beta, air tap to show the toolbar, then select **Details**.</span></span> <span data-ttu-id="66bf3-224">3D 查看器 Beta 版不支持的文件部分将突出显示为警告。</span><span class="sxs-lookup"><span data-stu-id="66bf3-224">Aspects of the file which are not supported by 3D Viewer Beta will be highlighted as warnings.</span></span>

<span data-ttu-id="66bf3-225">最常见的问题是纹理缺失，这可能是因为它们未嵌入 FBX 文件中。</span><span class="sxs-lookup"><span data-stu-id="66bf3-225">The most common issue you might see is missing textures, likely because they are not embedded in the FBX file.</span></span> <span data-ttu-id="66bf3-226">在这种情况下，模型将显示为白色。</span><span class="sxs-lookup"><span data-stu-id="66bf3-226">In this case, the model will appear white.</span></span> <span data-ttu-id="66bf3-227">此问题可在创建过程中解决，方法是：在选中嵌入纹理选项的情况下从创建工具导出到 FBX。</span><span class="sxs-lookup"><span data-stu-id="66bf3-227">This issue can be addressed in the creation process by exporting from your creation tool to FBX with the embed textures option selected.</span></span>

<span data-ttu-id="66bf3-228">有关详细信息，请参阅[支持内容规范](#supported-content-specifications)和[为 3D 查看器 Beta 版优化 3D 模型](#optimizing-3d-models-for-3d-viewer-beta)。</span><span class="sxs-lookup"><span data-stu-id="66bf3-228">For more info, see [Supported content specifications](#supported-content-specifications) and [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta).</span></span>

### <span data-ttu-id="66bf3-229">查看我的 3D 模型时出现性能下降</span><span class="sxs-lookup"><span data-stu-id="66bf3-229">I experience performance drops while viewing my 3D model</span></span>

<span data-ttu-id="66bf3-230">在加载和查看 3D 模型时，性能可能会受到以下因素的影响：模型的复杂性、同时打开的模型数量或具有活动动画的模型数量。</span><span class="sxs-lookup"><span data-stu-id="66bf3-230">Performance when loading and viewing a 3D model can be affected by the complexity of the model, number of models open simultaneously, or number of models with active animations.</span></span>

<span data-ttu-id="66bf3-231">有关详细信息，请参阅[为 3D 查看器 Beta 版优化 3D 模型](#optimizing-3d-models-for-3d-viewer-beta)和[文件和模型限制](#file-and-model-limitations)。</span><span class="sxs-lookup"><span data-stu-id="66bf3-231">For more info, see [Optimizing 3D models for 3D Viewer Beta](#optimizing-3d-models-for-3d-viewer-beta) and [File and model limitations](#file-and-model-limitations).</span></span>

### <span data-ttu-id="66bf3-232">当我在 HoloLens 上打开 FBX 文件时，该文件未在 3D 查看器 Beta 版中打开</span><span class="sxs-lookup"><span data-stu-id="66bf3-232">When I open an FBX file on HoloLens, it doesn't open in 3D Viewer Beta</span></span>

<span data-ttu-id="66bf3-233">3D 查看器 Beta 版会在安装后自动与 .fbx 文件扩展名相关联。</span><span class="sxs-lookup"><span data-stu-id="66bf3-233">3D Viewer Beta is automatically associated with the .fbx file extension when it is installed.</span></span>

<span data-ttu-id="66bf3-234">如果你在尝试打开 FBX 文件时看到一个对话框，该对话框指引你访问 Microsoft Store，则表明 HoloLens 上目前没有与 .fbx 文件扩展名相关联的应用。</span><span class="sxs-lookup"><span data-stu-id="66bf3-234">If you try to open an FBX file and see a dialog box that directs you to Microsoft Store, you do not currently have an app associated with the .fbx file extension on HoloLens.</span></span>

<span data-ttu-id="66bf3-235">请验证是否安装了 3D 查看器 Beta 版。</span><span class="sxs-lookup"><span data-stu-id="66bf3-235">Verify that 3D Viewer Beta is installed.</span></span> <span data-ttu-id="66bf3-236">如果未安装，请在 HoloLens 上从 Microsoft Store 下载。</span><span class="sxs-lookup"><span data-stu-id="66bf3-236">If it is not installed, download it from Microsoft Store on HoloLens.</span></span>

<span data-ttu-id="66bf3-237">如果已安装 3D 查看器 Beta 版，请启动 3D 查看器 Beta 版，然后再次尝试打开文件。</span><span class="sxs-lookup"><span data-stu-id="66bf3-237">If 3D Viewer Beta is already installed, launch 3D Viewer Beta, then try opening the file again.</span></span> <span data-ttu-id="66bf3-238">如果问题仍然存在，请卸载并重新安装 3D 查看器 Beta 版。</span><span class="sxs-lookup"><span data-stu-id="66bf3-238">If the issue persists, uninstall and reinstall 3D Viewer Beta.</span></span> <span data-ttu-id="66bf3-239">这将使 .fbx 文件扩展名与 3D 查看器 Beta 版重新关联。</span><span class="sxs-lookup"><span data-stu-id="66bf3-239">This will re-associate the .fbx file extension with 3D Viewer Beta.</span></span>

<span data-ttu-id="66bf3-240">如果尝试打开 FBX 文件时打开了 3D 查看器 Beta 版以外的其他应用，则该应用可能是在 3D 查看器 Beta 版之后安装的，并且已接管与 .fbx 文件扩展名的关联。</span><span class="sxs-lookup"><span data-stu-id="66bf3-240">If attempting to open an FBX file opens an app other than 3D Viewer Beta, that app was likely installed after 3D Viewer Beta and has taken over association with the .fbx file extension.</span></span> <span data-ttu-id="66bf3-241">如果你更喜欢将 3D 查看器 Beta 版与 .fbx 文件扩展名相关联，请卸载并重新安装 3D 查看器 Beta 版。</span><span class="sxs-lookup"><span data-stu-id="66bf3-241">If you prefer 3D Viewer Beta to be associated with the .fbx file extension, uninstall and reinstall 3D Viewer Beta.</span></span>

### <span data-ttu-id="66bf3-242">3D 查看器 Beta 版中的“打开文件”按钮无法启动应用</span><span class="sxs-lookup"><span data-stu-id="66bf3-242">The Open File button in 3D Viewer Beta doesn't launch an app</span></span>

<span data-ttu-id="66bf3-243">“打开文件”\*\*\*\* 按钮将打开与 HoloLens 上的文件选取器功能相关联的应用。</span><span class="sxs-lookup"><span data-stu-id="66bf3-243">The **Open File** button will open the app associated with the file picker function on HoloLens.</span></span> <span data-ttu-id="66bf3-244">如果已安装 OneDrive，“打开文件”\*\*\*\* 按钮将启动 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="66bf3-244">If OneDrive is installed, the **Open File** button should launch OneDrive.</span></span> <span data-ttu-id="66bf3-245">但是，如果 HoloLens 上当前没有安装与文件选取器功能相关联的应用，将转到 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="66bf3-245">However, if there is currently no app associated with the file picker function installed on HoloLens, you will be directed to Microsoft Store.</span></span>

<span data-ttu-id="66bf3-246">如果“打开文件”\*\*\*\* 按钮启动的是 OneDrive 之外的应用，则该应用可能是在 OneDrive 之后安装的，并且已接管与文件选取器功能的关联。</span><span class="sxs-lookup"><span data-stu-id="66bf3-246">If the **Open File** button launches an app other than OneDrive, that app was likely installed after OneDrive and has taken over association with the file picker function.</span></span> <span data-ttu-id="66bf3-247">在 3D 查看器 Beta 版中选择“**打开文件**”按钮时，如果你更喜欢启动 OneDrive，请卸载并重新安装 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="66bf3-247">If you prefer OneDrive to launch when selecting the **Open File** button in 3D Viewer Beta, uninstall and reinstall OneDrive.</span></span>

<span data-ttu-id="66bf3-248">如果“**打开文件**”按钮未处于活动状态，则可能已达到同一时间可在 3D 查看器 Beta 版中打开的模型数量上限。</span><span class="sxs-lookup"><span data-stu-id="66bf3-248">If the **Open File** button is not active, it's possible that you have reached the limit of models that can be open in 3D Viewer Beta at one time.</span></span> <span data-ttu-id="66bf3-249">如果已在 3D 查看器 Beta 版中打开了 40 个模型，则需要关闭一些模型，然后才能打开其他模型。</span><span class="sxs-lookup"><span data-stu-id="66bf3-249">If you have 40 models open in 3D Viewer Beta, you will need to close some before you will be able to open additional models.</span></span>

## <span data-ttu-id="66bf3-250">其他资源</span><span class="sxs-lookup"><span data-stu-id="66bf3-250">Additional resources</span></span>

- <span data-ttu-id="66bf3-251">[支持论坛](http://forums.hololens.com/categories/3d-viewer-beta) - 仅用于存档目的。</span><span class="sxs-lookup"><span data-stu-id="66bf3-251">[Support forums](http://forums.hololens.com/categories/3d-viewer-beta) - For archival purposes only.</span></span> <span data-ttu-id="66bf3-252">此论坛不再有效。</span><span class="sxs-lookup"><span data-stu-id="66bf3-252">This forum is no longer active.</span></span>
- [<span data-ttu-id="66bf3-253">第三方通知</span><span class="sxs-lookup"><span data-stu-id="66bf3-253">Third-party notices</span></span>](https://www.microsoft.com/{lang-locale}/legal/products)
