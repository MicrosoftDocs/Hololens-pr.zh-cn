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
# <span data-ttu-id="02210-105">使用 HoloLens 映射物理空间</span><span class="sxs-lookup"><span data-stu-id="02210-105">Map physical spaces with HoloLens</span></span>

<span data-ttu-id="02210-106">HoloLens 将全息影像与你的物理世界融合在一起。</span><span class="sxs-lookup"><span data-stu-id="02210-106">HoloLens blends holograms with your physical world.</span></span> <span data-ttu-id="02210-107">为此，HoloLens 必须了解周围的物理世界，并记住在该空间中放置全息影像的位置。</span><span class="sxs-lookup"><span data-stu-id="02210-107">To do that, HoloLens has to learn about the physical world around you and remember where you place holograms within that space.</span></span>

<span data-ttu-id="02210-108">随着时间推移，HoloLens 会建立它所看到的环境*空间地图*。</span><span class="sxs-lookup"><span data-stu-id="02210-108">Over time, the HoloLens builds up a *spatial map* of the environment that it has seen.</span></span>  <span data-ttu-id="02210-109">HoloLens 会随着环境的变化更新映射。</span><span class="sxs-lookup"><span data-stu-id="02210-109">HoloLens updates the map as the environment changes.</span></span> <span data-ttu-id="02210-110">只要登录并打开了设备，HoloLens 就会创建和更新空间地图。</span><span class="sxs-lookup"><span data-stu-id="02210-110">As long as you are logged in and the device is turned on, HoloLens creates and updates your spatial maps.</span></span> <span data-ttu-id="02210-111">如果在相机指向某个空间的情况下握住或佩戴设备，则 HoloLens 会尝试映射此区域。</span><span class="sxs-lookup"><span data-stu-id="02210-111">If you hold or wear the device with the cameras pointed at a space, the HoloLens tries to map the area.</span></span> <span data-ttu-id="02210-112">随着 HoloLens 随着时间的推移自然会出现一个空间，你可以通过多种方式来帮助 HoloLens 更快、更高效地映射你的空间。</span><span class="sxs-lookup"><span data-stu-id="02210-112">While the HoloLens learns a space naturally over time, there are ways in which you can help HoloLens map your space more quickly and efficiently.</span></span>  

> [!NOTE]
> <span data-ttu-id="02210-113">如果 HoloLens 无法映射出你的空间或超出校准范围，则 HoloLens 可能会进入“受限”模式。</span><span class="sxs-lookup"><span data-stu-id="02210-113">If your HoloLens can't map your space or is out of calibration, HoloLens may enter Limited mode.</span></span> <span data-ttu-id="02210-114">在“受限”模式中，将无法在环境中放置全息影像。</span><span class="sxs-lookup"><span data-stu-id="02210-114">In Limited mode, you won't be able to place holograms in your surroundings.</span></span>

<span data-ttu-id="02210-115">本文介绍了 HoloLens 如何映射空间，如何改进空间映射以及如何管理 HoloLens 收集的空间数据。</span><span class="sxs-lookup"><span data-stu-id="02210-115">This article explains how HoloLens maps spaces, how to improve spatial mapping, and how to manage the spatial data that HoloLens collects.</span></span>

## <span data-ttu-id="02210-116">选择和设置共享空间</span><span class="sxs-lookup"><span data-stu-id="02210-116">Choosing and setting up and your space</span></span>

<span data-ttu-id="02210-117">环境中的功能可能会使 HoloLens 难以理解空间。</span><span class="sxs-lookup"><span data-stu-id="02210-117">Features in your environment can make it difficult for the HoloLens to interpret a space.</span></span> <span data-ttu-id="02210-118">光照水平、空间中的物质，对象的布局等都会影响 HoloLens 映射区域的方式。</span><span class="sxs-lookup"><span data-stu-id="02210-118">Light levels, materials in the space, the layout of objects, and more can all affect how HoloLens maps an area.</span></span>

<span data-ttu-id="02210-119">HoloLens 在某些环境下效果最佳。</span><span class="sxs-lookup"><span data-stu-id="02210-119">HoloLens works best in certain kinds of environments.</span></span> <span data-ttu-id="02210-120">为了制作最佳的空间地图，请选择光线充足且空间充足的房间。</span><span class="sxs-lookup"><span data-stu-id="02210-120">To produce the best spatial map, choose a room that has adequate light and plenty of space.</span></span> <span data-ttu-id="02210-121">避免黑暗的空间和有很多黑暗、发亮或半透明表面的房间（例如镜子或薄纱幕）。</span><span class="sxs-lookup"><span data-stu-id="02210-121">Avoid dark spaces and rooms that have a lot of dark, shiny, or translucent surfaces (for instance, mirrors or gauzy curtains).</span></span>

<span data-ttu-id="02210-122">HoloLens 针对室内使用进行了优化。</span><span class="sxs-lookup"><span data-stu-id="02210-122">HoloLens is optimized for indoor use.</span></span> <span data-ttu-id="02210-123">虽然 Wi-fi 处于开启状态，但无需将其连接到网络，空间映射也能达到最佳的效果。</span><span class="sxs-lookup"><span data-stu-id="02210-123">Spatial mapping also works best when Wi-Fi is turned on, although it doesn't have to be connected to a network.</span></span> <span data-ttu-id="02210-124">HoloLens 可以获取 Wi-fi 接入点，即使未连接或未通过身份验证。</span><span class="sxs-lookup"><span data-stu-id="02210-124">HoloLens can obtain Wi-Fi access points even if it is not connected or authenticated.</span></span> <span data-ttu-id="02210-125">无论接入点是Internet 连接还是Intranet /仅本地，HoloLens 功能均不会更改。</span><span class="sxs-lookup"><span data-stu-id="02210-125">HoloLens functionality does not change whether the access points are internet-connected or intranet/local only.</span></span>

<span data-ttu-id="02210-126">仅在没有绊倒危险的安全地方使用 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="02210-126">Only use HoloLens in safe places with no tripping hazards.</span></span> <span data-ttu-id="02210-127">[有关安全的更多信息](https://support.microsoft.com/help/4023454/safety-information)。</span><span class="sxs-lookup"><span data-stu-id="02210-127">[More on safety](https://support.microsoft.com/help/4023454/safety-information).</span></span>

## <span data-ttu-id="02210-128">映射空间</span><span class="sxs-lookup"><span data-stu-id="02210-128">Mapping your space</span></span>

<span data-ttu-id="02210-129">现在您准备开始映射你的空间。</span><span class="sxs-lookup"><span data-stu-id="02210-129">Now you're ready to start mapping your spare.</span></span>  <span data-ttu-id="02210-130">HoloLens 开始映射环境时，会看到遍布空间的网格图。</span><span class="sxs-lookup"><span data-stu-id="02210-130">When HoloLens starts mapping your surroundings, you'll see a mesh graphic spreading over the space.</span></span>  <span data-ttu-id="02210-131">在混合现实主页中，可以通过在映射的表面上进行选择来触发地图显示。</span><span class="sxs-lookup"><span data-stu-id="02210-131">In mixed reality home, you can trigger the map to show by selecting on a mapped surface.</span></span>

<span data-ttu-id="02210-132">以下是构建完美空间地图的指南。</span><span class="sxs-lookup"><span data-stu-id="02210-132">Here are guidelines for building a great spatial map.</span></span>

### <span data-ttu-id="02210-133">了解区域的场景</span><span class="sxs-lookup"><span data-stu-id="02210-133">Understand the scenarios for the area</span></span>

<span data-ttu-id="02210-134">务必将大部分时间花在要使用 HoloLens 的地方，这样地图才是相关且完整的。</span><span class="sxs-lookup"><span data-stu-id="02210-134">It is important to spend the most time where you will be using the HoloLens, so that the map is relevant and complete.</span></span> <span data-ttu-id="02210-135">例如，如果 HoloLens 的用户场景涉及从点 A 移到点 B，则沿该路径走两到三遍，并在移动时观看所有方向。</span><span class="sxs-lookup"><span data-stu-id="02210-135">For example, if a user scenario for HoloLens involves moving from Point A to Point B, walk that path two to three times, looking in all directions as you move.</span></span>  

### <span data-ttu-id="02210-136">在空间中慢慢移动</span><span class="sxs-lookup"><span data-stu-id="02210-136">Walk slowly around the space</span></span>

<span data-ttu-id="02210-137">如果在该区域走得太快，则 HoloLens 可能会错过绘图区域。</span><span class="sxs-lookup"><span data-stu-id="02210-137">If you walk too quickly around the area, it's likely that the HoloLens will miss mapping areas.</span></span> <span data-ttu-id="02210-138">在空间中缓慢走动，每 5 到 8 英尺停下来环顾周围环境。</span><span class="sxs-lookup"><span data-stu-id="02210-138">Walk slowly around the space, stopping every 5-8 feet to look around at your surroundings.</span></span>  

<span data-ttu-id="02210-139">平稳移动也有助于 HoloLens 更加有效地绘图。</span><span class="sxs-lookup"><span data-stu-id="02210-139">Smooth movements also help the HoloLens map more efficiently.</span></span>

### <span data-ttu-id="02210-140">全向环顾</span><span class="sxs-lookup"><span data-stu-id="02210-140">Look in all directions</span></span>

<span data-ttu-id="02210-141">绘制地图时环顾四周，可为 HoloLens 提供更多有关点相对位置的数据。</span><span class="sxs-lookup"><span data-stu-id="02210-141">Looking around as you map the space gives the HoloLens more data on where points are relative to each other.</span></span>  

<span data-ttu-id="02210-142">例如，如果不抬头，HoloLens 可能不知道房间的天花板在哪里。</span><span class="sxs-lookup"><span data-stu-id="02210-142">If you don't look up, for example, the HoloLens may not know where the ceiling in a room is.</span></span>  

<span data-ttu-id="02210-143">映射空间时，不要忘记俯视地板。</span><span class="sxs-lookup"><span data-stu-id="02210-143">Don't forget to look down at the floor as you map the space.</span></span>

### <span data-ttu-id="02210-144">多次覆盖关键区域</span><span class="sxs-lookup"><span data-stu-id="02210-144">Cover key areas multiple times</span></span>

<span data-ttu-id="02210-145">多次在一个区域中移动将帮助您获得在第一次走动中可能错过的功能。</span><span class="sxs-lookup"><span data-stu-id="02210-145">Moving through an area multiple times will help pick up features you may have missed on the first walkthrough.</span></span> <span data-ttu-id="02210-146">要构建理想的地图，请尝试遍历2至3次区域。</span><span class="sxs-lookup"><span data-stu-id="02210-146">To build an ideal map, try traversing an area two to three times.</span></span>

<span data-ttu-id="02210-147">如果可行，重复这些动作时，花一些时间沿一个方向走过一个区域，然后转身走回原路。</span><span class="sxs-lookup"><span data-stu-id="02210-147">If possible, while repeating these movements, spend time walking through an area in one direction, then turn around and walk back the way you came.</span></span>

### <span data-ttu-id="02210-148">花时间映射区域</span><span class="sxs-lookup"><span data-stu-id="02210-148">Take your time mapping the area</span></span>

<span data-ttu-id="02210-149">HoloLens 可能需要 15 到 20 分钟才能完全绘制地图并适应周围环境。</span><span class="sxs-lookup"><span data-stu-id="02210-149">It can take between 15 and 20 minutes for the HoloLens to fully map and adjust itself to its surroundings.</span></span> <span data-ttu-id="02210-150">如果你有一个空间来计划经常使用 HoloLens，提前花时间来绘制空间可以防止以后发生问题。</span><span class="sxs-lookup"><span data-stu-id="02210-150">If you have a space in which you plan to use a HoloLens frequently, taking that time up front to map the space can prevent issues later on.</span></span>  

## <span data-ttu-id="02210-151">空间地图中可能存在的错误</span><span class="sxs-lookup"><span data-stu-id="02210-151">Possible errors in the spatial map</span></span>

<span data-ttu-id="02210-152">空间映射数据中的错误分为几个类别：</span><span class="sxs-lookup"><span data-stu-id="02210-152">Errors in spatial mapping data fall into a few categories:</span></span>

- <span data-ttu-id="02210-153">*孔洞*：空间映射数据中缺少现实表面。</span><span class="sxs-lookup"><span data-stu-id="02210-153">*Holes*: Real-world surfaces are missing from the spatial mapping data.</span></span>
- <span data-ttu-id="02210-154">*幻象*：存在于空间映射数据中的表面在现实世界中不存在。</span><span class="sxs-lookup"><span data-stu-id="02210-154">*Hallucinations*: Surfaces exist in the spatial mapping data that do not exist in the real world.</span></span>
- <span data-ttu-id="02210-155">*虫洞*：HoloLens 认为空间图与实际位置不在同一部分，从而“丢失”了空间图的一部分。</span><span class="sxs-lookup"><span data-stu-id="02210-155">*Wormholes*: HoloLens 'loses' part of the spatial map by thinking it is in a different part of the map than it actually is.</span></span>
- <span data-ttu-id="02210-156">*偏差*：无论推入或拉出时，空间映射数据中的表面与现实世界中的表面不完全对齐。</span><span class="sxs-lookup"><span data-stu-id="02210-156">*Bias*: Surfaces in the spatial mapping data are imperfectly aligned with real-world surfaces, either pushed in or pulled out.</span></span>

<span data-ttu-id="02210-157">如果发现任何这些错误，请使用 [FeedbackHub](hololens-feedback.md) 发送反馈。</span><span class="sxs-lookup"><span data-stu-id="02210-157">If you see any of these errors please use the [FeedbackHub](hololens-feedback.md) to send feedback.</span></span>

## <span data-ttu-id="02210-158">空间数据安全和存储</span><span class="sxs-lookup"><span data-stu-id="02210-158">Security and storage for spatial data</span></span>

<span data-ttu-id="02210-159">适用于 Microsoft HoloLens 的 Windows 10 版本 1803 和更新版本存储映射数据至本地（设备上）数据库内。</span><span class="sxs-lookup"><span data-stu-id="02210-159">Windows 10 version 1803 update for Microsoft HoloLens and later stores mapping data in a local (on-device) database.</span></span>

<span data-ttu-id="02210-160">即使将设备插入到电脑或使用文件资源管理器应用时，HoloLens 用户也无法直接访问映射数据库。</span><span class="sxs-lookup"><span data-stu-id="02210-160">HoloLens users cannot directly access the map database, even when the device is plugged into a PC or when using the File Explorer app.</span></span> <span data-ttu-id="02210-161">在 HoloLens 上启用 BitLocker 后，存储的映射数据也会与整个卷一起加密。</span><span class="sxs-lookup"><span data-stu-id="02210-161">When BitLocker is enabled on HoloLens, the stored map data is also encrypted along with the entire volume.</span></span>

### <span data-ttu-id="02210-162">从 HoloLens 中删除映射数据和已知空间</span><span class="sxs-lookup"><span data-stu-id="02210-162">Remove map data and known spaces from HoloLens</span></span>

<span data-ttu-id="02210-163">有两种方法可用于在“**设置 > 系统 > 全息影像**”中删除映射数据：</span><span class="sxs-lookup"><span data-stu-id="02210-163">There are two options for deleting map data in **Settings > System > Holograms**:</span></span>

- <span data-ttu-id="02210-164">若要删除附近的全息影像，请选择“**删除附近的全息影像**”。</span><span class="sxs-lookup"><span data-stu-id="02210-164">To delete nearby holograms, select **Remove nearby holograms**.</span></span> <span data-ttu-id="02210-165">此命令清除当前空间的地图数据和锚定全息影像。</span><span class="sxs-lookup"><span data-stu-id="02210-165">This command clears the map data and anchored holograms for the current space.</span></span> <span data-ttu-id="02210-166">如果继续在同一空间中使用设备，它将创建并存储一个全新的映射部分以替换已删除的信息。</span><span class="sxs-lookup"><span data-stu-id="02210-166">If you continue to use the device in the same space, it creates and stores a brand new map section to replace the deleted information.</span></span>

   > [!NOTE]
   > <span data-ttu-id="02210-167">“附近的”全息影像是锚定在当前空间中同一映射部分内的全息影像。</span><span class="sxs-lookup"><span data-stu-id="02210-167">"Nearby" holograms are holograms that are anchored within the same map section in the current space.</span></span>

   <span data-ttu-id="02210-168">例如，可以使用此选项清除与工作相关的映射数据，而不影响任何与家庭相关的映射数据。</span><span class="sxs-lookup"><span data-stu-id="02210-168">For example, you can use this option to clear work-related map data without affecting any home-related map data.</span></span>

- <span data-ttu-id="02210-169">若要删除所有全息影像，请选择“**删除所有全息影像**”。</span><span class="sxs-lookup"><span data-stu-id="02210-169">To delete all holograms, select **Remove all holograms**.</span></span> <span data-ttu-id="02210-170">此命令清除存储在设备上的所有地图数据以及所有锚定的全息影像。</span><span class="sxs-lookup"><span data-stu-id="02210-170">This command clears all map data that is stored on the device as well as all anchored holograms.</span></span> <span data-ttu-id="02210-171">你将需要明确放置所有全息影像。</span><span class="sxs-lookup"><span data-stu-id="02210-171">You will need to explicitly place any holograms.</span></span> <span data-ttu-id="02210-172">你将不能重新发现之前放置的全息影像。</span><span class="sxs-lookup"><span data-stu-id="02210-172">You will not be able to rediscover the previously-placed holograms.</span></span>

> [!NOTE]
> <span data-ttu-id="02210-173">删除附近或所有全息影像后，HoloLens 立即开始扫描并映射当前空间。</span><span class="sxs-lookup"><span data-stu-id="02210-173">After you remove nearby or all holograms, HoloLens immediately starts scanning and mapping the current space.</span></span>

### <span data-ttu-id="02210-174">空间映射中的 Wi-Fi 数据</span><span class="sxs-lookup"><span data-stu-id="02210-174">Wi-Fi data in spatial maps</span></span>

<span data-ttu-id="02210-175">HoloLens 会存储 Wi-fi 的特征，有助于关联存储在已知空间 HoloLens 数据库内的全息影像位置和图区。</span><span class="sxs-lookup"><span data-stu-id="02210-175">HoloLens stores Wi-Fi characteristics to help correlate hologram locations and map sections that are stored within the HoloLens database of known spaces.</span></span> <span data-ttu-id="02210-176">用户无法访问有关 Wi-Fi 特征的信息，也无法使用云或遥测将其发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="02210-176">Information about Wi-Fi characteristics is not accessible to users, and not sent to Microsoft using the cloud or using telemetry.</span></span>

<span data-ttu-id="02210-177">只要启用了Wi-Fi，HoloLens 就会将地图数据与附近的 Wi-Fi 接入点相关联。</span><span class="sxs-lookup"><span data-stu-id="02210-177">As long as Wi-Fi is enabled, HoloLens correlates map data with nearby Wi-Fi access points.</span></span> <span data-ttu-id="02210-178">无论网络是否已连接或是否仅在附近检测到，都没有行为方面的差异。</span><span class="sxs-lookup"><span data-stu-id="02210-178">There is no difference in behavior whether a network is connected or just detected nearby.</span></span> <span data-ttu-id="02210-179">如果禁用了 Wi-Fi，HoloLens 仍会搜索该空间。</span><span class="sxs-lookup"><span data-stu-id="02210-179">If Wi-Fi is disabled, HoloLens still searches the space.</span></span> <span data-ttu-id="02210-180">但是，HoloLens 必须在空间数据库中搜索更多地图数据，并且可能需要更多时间才能找到全息影像。</span><span class="sxs-lookup"><span data-stu-id="02210-180">However, HoloLens has to search more of the map data within the spaces database, and may need more time to find holograms.</span></span> <span data-ttu-id="02210-181">如果没有 Wi-Fi 信息，HoloLens 必须将活动扫描与设备上存储的所有全息影像锚点和地图部分进行比较，以便找到地图的正确部分。</span><span class="sxs-lookup"><span data-stu-id="02210-181">Without the Wi-Fi info, the HoloLens has to compare active scans to all hologram anchors and map sections that are stored on the device in order to locate the correct portion of the map.</span></span>

## <span data-ttu-id="02210-182">相关主题</span><span class="sxs-lookup"><span data-stu-id="02210-182">Related topics</span></span>

- [<span data-ttu-id="02210-183">空间映射设计</span><span class="sxs-lookup"><span data-stu-id="02210-183">Spatial mapping design</span></span>](https://docs.microsoft.com/windows/mixed-reality/spatial-mapping-design)
