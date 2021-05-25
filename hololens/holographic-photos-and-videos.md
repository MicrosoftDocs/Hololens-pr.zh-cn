---
title: 捕获、录制和共享混合现实照片和视频
description: 了解如何使用 HoloLens 混合现实设备捕获、录制、查看混合现实照片和视频。 了解如何通过 Miracast 或收集的文件共享。
keywords: hololens， 照片， 视频， 捕获， mrc， 混合现实捕获， 照片， 相机， miracast， 流， 实时流， 演示， 录制
ms.assetid: 1b636ec3-6186-4fbb-81b2-71155aef0593
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 10/28/2019
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 178dff5d8a30fdd9c5012e2d14f5d4683d6cc23e
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397498"
---
# <a name="create-mixed-reality-photos-and-videos"></a><span data-ttu-id="c26c4-105">创建混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="c26c4-105">Create mixed reality photos and videos</span></span>

<span data-ttu-id="c26c4-106">HoloLens 为用户提供将现实世界与数字世界混合的体验。</span><span class="sxs-lookup"><span data-stu-id="c26c4-106">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="c26c4-107">混合现实捕获 (MRC) 使你能够将体验捕获为照片或视频，或与他人实时共享你所看到的内容。</span><span class="sxs-lookup"><span data-stu-id="c26c4-107">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="c26c4-108">混合现实捕获使用第一人称视角，以便其他人可以在看到全息影像时看到全息影像。</span><span class="sxs-lookup"><span data-stu-id="c26c4-108">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="c26c4-109">对于第三人称，请使用 [旁观视图](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。</span><span class="sxs-lookup"><span data-stu-id="c26c4-109">For a third-person point of view, use [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="c26c4-110">旁观视图对于演示特别有用。</span><span class="sxs-lookup"><span data-stu-id="c26c4-110">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="c26c4-111">虽然在朋友和同事之间共享视频很有趣，但视频还有助于指导其他人使用应用或与应用和体验交流问题。</span><span class="sxs-lookup"><span data-stu-id="c26c4-111">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="c26c4-112">如果无法启动混合现实捕获体验，并且 HoloLens 是工作设备，请与系统管理员联系。</span><span class="sxs-lookup"><span data-stu-id="c26c4-112">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="c26c4-113">可以通过公司策略限制对相机的访问。</span><span class="sxs-lookup"><span data-stu-id="c26c4-113">Access to the camera can be restricted through company policy.</span></span>

## <a name="capture-a-mixed-reality-photo"></a><span data-ttu-id="c26c4-114">捕获混合现实照片</span><span class="sxs-lookup"><span data-stu-id="c26c4-114">Capture a mixed reality photo</span></span>

<span data-ttu-id="c26c4-115">在 HoloLens 上拍摄混合现实照片的方法有多种方式;可以使用硬件按钮、语音或“开始”菜单。</span><span class="sxs-lookup"><span data-stu-id="c26c4-115">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-take-photos"></a><span data-ttu-id="c26c4-116">用于拍摄照片的硬件按钮</span><span class="sxs-lookup"><span data-stu-id="c26c4-116">Hardware buttons to take photos</span></span>

<span data-ttu-id="c26c4-117">若要快速拍摄当前视图的照片，请同时按音量调高和音量降低按钮。</span><span class="sxs-lookup"><span data-stu-id="c26c4-117">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="c26c4-118">这有点与屏幕截图或打印屏幕的 HoloLens 版本类似。</span><span class="sxs-lookup"><span data-stu-id="c26c4-118">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="c26c4-119">按钮位置HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c26c4-119">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="c26c4-120">HoloLens 第一代 (上的按钮) </span><span class="sxs-lookup"><span data-stu-id="c26c4-120">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="c26c4-121">将 " **音量朝上** " 和 " **音量减小** " 按钮设置为三秒将开始录制视频，而不是拍摄照片。</span><span class="sxs-lookup"><span data-stu-id="c26c4-121">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="c26c4-122">若要停止录制，请同时点击 " **音量调高** " 和 "调 **低音量** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="c26c4-122">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <a name="voice-commands-to-take-photos"></a><span data-ttu-id="c26c4-123">拍摄照片的语音命令</span><span class="sxs-lookup"><span data-stu-id="c26c4-123">Voice commands to take photos</span></span>

<span data-ttu-id="c26c4-124">在 HoloLens 2 上，版本 2004 (和更高版本) ，例如： "拍摄照片"。</span><span class="sxs-lookup"><span data-stu-id="c26c4-124">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="c26c4-125">在 HoloLens (第一代) 或 HoloLens 2 版本1903上，例如： "你好 Cortana，拍摄照片"。</span><span class="sxs-lookup"><span data-stu-id="c26c4-125">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <a name="start-menu-to-take-photos"></a><span data-ttu-id="c26c4-126">拍摄照片的 "开始" 菜单</span><span class="sxs-lookup"><span data-stu-id="c26c4-126">Start menu to take photos</span></span>

<span data-ttu-id="c26c4-127">使用 "开始" 手势中转到 " **开始**"，然后选择 **相机** 图标。</span><span class="sxs-lookup"><span data-stu-id="c26c4-127">Use the Start gesture to go to **Start**, then select the **Camera** icon.</span></span>

<span data-ttu-id="c26c4-128">将你的头指向你要捕获的内容，然后单击 " [空中](hololens2-basic-usage.md#touch-holograms-near-you) " 拍摄照片。</span><span class="sxs-lookup"><span data-stu-id="c26c4-128">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="c26c4-129">你可以继续空中点击并捕获其他照片。</span><span class="sxs-lookup"><span data-stu-id="c26c4-129">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="c26c4-130">您捕获的任何照片都将保存到您的设备中。</span><span class="sxs-lookup"><span data-stu-id="c26c4-130">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="c26c4-131">再次使用开始手势来结束照片捕获。</span><span class="sxs-lookup"><span data-stu-id="c26c4-131">Use the Start gesture again to end photo capture.</span></span>  

## <a name="capture-a-mixed-reality-video"></a><span data-ttu-id="c26c4-132">捕获混合现实视频</span><span class="sxs-lookup"><span data-stu-id="c26c4-132">Capture a mixed reality video</span></span>

<span data-ttu-id="c26c4-133">可以通过多种方式在 HoloLens 上录制混合现实的视频;可以使用硬件按钮、语音或 "开始" 菜单。</span><span class="sxs-lookup"><span data-stu-id="c26c4-133">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-record-videos"></a><span data-ttu-id="c26c4-134">用于录制视频的硬件按钮</span><span class="sxs-lookup"><span data-stu-id="c26c4-134">Hardware buttons to record videos</span></span>

<span data-ttu-id="c26c4-135">录制视频最快捷的方法是，同时按住 " **音量调高** " 和 "调 **低** 音量" 按钮，直到开始进行三秒钟倒计时。</span><span class="sxs-lookup"><span data-stu-id="c26c4-135">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="c26c4-136">若要停止录制，请同时点击两个按钮。</span><span class="sxs-lookup"><span data-stu-id="c26c4-136">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="c26c4-137">同时快速按下 " **音量调高** " 和 " **音量减小** " 按钮会拍摄照片，而不是录制视频。</span><span class="sxs-lookup"><span data-stu-id="c26c4-137">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <a name="voice-to-record-videos"></a><span data-ttu-id="c26c4-138">用于录制视频的语音</span><span class="sxs-lookup"><span data-stu-id="c26c4-138">Voice to record videos</span></span>

<span data-ttu-id="c26c4-139">在 HoloLens 2 上，版本 2004 (及更高版本) ，例如： "开始录制"。</span><span class="sxs-lookup"><span data-stu-id="c26c4-139">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="c26c4-140">若要停止录制，请说 "停止录制"。</span><span class="sxs-lookup"><span data-stu-id="c26c4-140">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="c26c4-141">在 HoloLens (第一代) 或HoloLens 2版本 1903 上，说："你好，Cortana，开始录制。"</span><span class="sxs-lookup"><span data-stu-id="c26c4-141">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="c26c4-142">若要停止录制，请说"你好 Cortana，停止录制"。</span><span class="sxs-lookup"><span data-stu-id="c26c4-142">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <a name="start-menu-to-record-videos"></a><span data-ttu-id="c26c4-143">“开始”菜单录制视频</span><span class="sxs-lookup"><span data-stu-id="c26c4-143">Start menu to record videos</span></span>

<span data-ttu-id="c26c4-144">使用"开始"手势转到" **开始"，** 然后选择" **视频"** 图标。</span><span class="sxs-lookup"><span data-stu-id="c26c4-144">Use the Start gesture to go to **Start**, then select the **Video** icon.</span></span> <span data-ttu-id="c26c4-145">将头部指向要捕获的方向，然后按 [Air tap](hololens2-basic-usage.md#touch-holograms-near-you) 开始录制。</span><span class="sxs-lookup"><span data-stu-id="c26c4-145">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="c26c4-146">将进行三秒倒计时，记录将开始。</span><span class="sxs-lookup"><span data-stu-id="c26c4-146">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="c26c4-147">若要停止录制，请使用"开始"手势并选择突出显示 **的视频** 图标。</span><span class="sxs-lookup"><span data-stu-id="c26c4-147">To stop recording, use the Start gesture and select the highlighted **Video** icon.</span></span> <span data-ttu-id="c26c4-148">视频将保存到设备。</span><span class="sxs-lookup"><span data-stu-id="c26c4-148">The video will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="c26c4-149">**仅适用于 HoloLens (第一代)**</span><span class="sxs-lookup"><span data-stu-id="c26c4-149">**Applies to HoloLens (1st gen) only**</span></span>  
> <span data-ttu-id="c26c4-150">该 [Windows 10 2018 年 10 月更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) 更改 HoloLens 第一代和第一代 (上的"启动手势"和"Windows"按钮) 。</span><span class="sxs-lookup"><span data-stu-id="c26c4-150">The [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="c26c4-151">在更新之前，"启动手势"或"Windows"按钮将停止视频录制。</span><span class="sxs-lookup"><span data-stu-id="c26c4-151">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="c26c4-152">但是，更新后，"开始"手势或 Windows 按钮会打开"开始"菜单 (或快速操作菜单（如果正在沉浸式应用) 中，可以从中选择突出显示的视频图标停止录制。 </span><span class="sxs-lookup"><span data-stu-id="c26c4-152">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <a name="share-what-you-see-in-real-time"></a><span data-ttu-id="c26c4-153">实时共享看到</span><span class="sxs-lookup"><span data-stu-id="c26c4-153">Share what you see in real-time</span></span>

<span data-ttu-id="c26c4-154">可以与朋友和同事实时共享在 HoloLens 中看到什么。</span><span class="sxs-lookup"><span data-stu-id="c26c4-154">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="c26c4-155">有一些方法可用：</span><span class="sxs-lookup"><span data-stu-id="c26c4-155">There are a few methods available:</span></span>

1. <span data-ttu-id="c26c4-156">连接到启用了 Miracast 的设备或适配器，以在电视上观看。</span><span class="sxs-lookup"><span data-stu-id="c26c4-156">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="c26c4-157">使用 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 在电脑上观看</span><span class="sxs-lookup"><span data-stu-id="c26c4-157">Using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="c26c4-158">使用 [Microsoft HoloLens应用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 在电脑上观看。</span><span class="sxs-lookup"><span data-stu-id="c26c4-158">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="c26c4-159">部署 [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 应用，使一线工作人员能够将看到内容流式传输给远程专家。</span><span class="sxs-lookup"><span data-stu-id="c26c4-159">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="c26c4-160">然后，远程专家可以指导一线工作人员进行言语或批注。</span><span class="sxs-lookup"><span data-stu-id="c26c4-160">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="c26c4-161">通过 Windows 设备门户或 Microsoft HoloLens 随附应用共享看到的内容要求你的 HoloLens 处于 [开发人员模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="c26c4-161">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <a name="stream-video-with-miracast"></a><span data-ttu-id="c26c4-162">通过 Miracast 流式传输视频</span><span class="sxs-lookup"><span data-stu-id="c26c4-162">Stream video with Miracast</span></span>

<span data-ttu-id="c26c4-163">使用 "开始" 手势中转到 " **开始**"，然后选择 " **连接** " 图标。</span><span class="sxs-lookup"><span data-stu-id="c26c4-163">Use the Start gesture to go to **Start**, then select the **Connect** icon.</span></span> <span data-ttu-id="c26c4-164">从显示的选取器中，选择要连接到的已启用 Miracast 的设备或适配器。</span><span class="sxs-lookup"><span data-stu-id="c26c4-164">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="c26c4-165">要停止共享，请使用 "开始手势" 并选择突出显示的 " **连接** " 图标。</span><span class="sxs-lookup"><span data-stu-id="c26c4-165">To stop sharing, use the Start gesture and select the highlighted **Connect** icon.</span></span> <span data-ttu-id="c26c4-166">由于你正在进行流式处理，因此不会将任何内容保存到你的设备。</span><span class="sxs-lookup"><span data-stu-id="c26c4-166">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="c26c4-167">在从 [Windows 10 十月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)开始，在 HoloLens (第一代) 上启用了 Miracast 支持。</span><span class="sxs-lookup"><span data-stu-id="c26c4-167">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).</span></span>

### <a name="real-time-video-with-windows-device-portal"></a><span data-ttu-id="c26c4-168">Windows 设备门户的实时视频</span><span class="sxs-lookup"><span data-stu-id="c26c4-168">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="c26c4-169">由于通过 Windows 设备门户进行的共享需要在 HoloLens 上启用开发人员模式，请按照开发人员文档中的说明 [设置开发人员模式并导航 Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="c26c4-169">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <a name="microsoft-hololens-companion-app"></a><span data-ttu-id="c26c4-170">Microsoft HoloLens 辅助应用</span><span class="sxs-lookup"><span data-stu-id="c26c4-170">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="c26c4-171">由于通过 Microsoft HoloLens 辅助应用共享需要在 HoloLens 上启用开发人员模式，请按照开发人员文档中的说明 [设置开发人员模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="c26c4-171">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="c26c4-172">然后，下载 [Microsoft HoloLens 附属应用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) ，并按照应用中的说明连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="c26c4-172">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="c26c4-173">应用设置为 HoloLens 后，从应用的主菜单中选择 " **实时流** " 选项。</span><span class="sxs-lookup"><span data-stu-id="c26c4-173">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <a name="view-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="c26c4-174">查看混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="c26c4-174">View your mixed reality photos and videos</span></span>

<span data-ttu-id="c26c4-175">混合现实照片和视频保存到设备的 "照相机"。</span><span class="sxs-lookup"><span data-stu-id="c26c4-175">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="c26c4-176">你可以通过 "文件资源管理器" 应用在你的 HoloLens 上浏览此文件夹的内容， (导航到 " **> 相机滚动**) 中的图片"。</span><span class="sxs-lookup"><span data-stu-id="c26c4-176">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to **Pictures > Camera Roll**).</span></span>

<span data-ttu-id="c26c4-177">你还可以在预安装在 HoloLens 上的照片应用中查看混合现实照片和视频。</span><span class="sxs-lookup"><span data-stu-id="c26c4-177">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="c26c4-178">若要在你的世界中固定照片，请在照片应用中选择它，然后选择 " **在混合世界中放置"**。</span><span class="sxs-lookup"><span data-stu-id="c26c4-178">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="c26c4-179">放置照片后，可以将其移动到世界各地。</span><span class="sxs-lookup"><span data-stu-id="c26c4-179">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="c26c4-180">若要在连接到 HoloLens 的电脑上查看和/或保存混合现实照片和视频，Windows 设备门户 MTP[](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)使用 文件资源管理器[或电脑](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)的设备。</span><span class="sxs-lookup"><span data-stu-id="c26c4-180">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a><span data-ttu-id="c26c4-181">使用文件资源管理器获取图片、视频和文件</span><span class="sxs-lookup"><span data-stu-id="c26c4-181">Use File Explorer to get your pictures, videos and files</span></span>

<span data-ttu-id="c26c4-182">与其他移动设备类似，将 HoloLens 连接到电脑以启动 文件资源管理器 以访问 HoloLens 库 (照片、视频、文档) 轻松传输。</span><span class="sxs-lookup"><span data-stu-id="c26c4-182">Similar to other mobile devices, connect your HoloLens to your PC to bring up File Explorer to access your HoloLens libraries (photos, videos, documents) for easy transfer.</span></span> <span data-ttu-id="c26c4-183">此方法易于使用，不需要使用设备门户或 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="c26c4-183">This method is easy to use and does not require the use of device portal or Wi-Fi.</span></span>

1. <span data-ttu-id="c26c4-184">解锁设备。</span><span class="sxs-lookup"><span data-stu-id="c26c4-184">Unlock the device.</span></span>
1. <span data-ttu-id="c26c4-185">通过 USB 将设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="c26c4-185">Connect the device to a PC via USB.</span></span>
1. <span data-ttu-id="c26c4-186">文件资源管理器应在电脑上打开。</span><span class="sxs-lookup"><span data-stu-id="c26c4-186">File Explorer should open on your PC.</span></span>
1. <span data-ttu-id="c26c4-187">导航到：此电脑 \\ *yourhololensname*\Internal Storage\Pictures\Camera Roll</span><span class="sxs-lookup"><span data-stu-id="c26c4-187">Navigate to: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span></span>
1. <span data-ttu-id="c26c4-188">将所需的任何文件复制到电脑。</span><span class="sxs-lookup"><span data-stu-id="c26c4-188">Copy whatever files you need to your PC.</span></span>

<span data-ttu-id="c26c4-189">提示：</span><span class="sxs-lookup"><span data-stu-id="c26c4-189">Tips:</span></span>
- <span data-ttu-id="c26c4-190">如果看不到任何文件，请确保登录到 HoloLens 以启用对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="c26c4-190">If you don't see any files, please ensure you sign in to your HoloLens to enable access to your data.</span></span>
- <span data-ttu-id="c26c4-191">可以从其他文件夹中获取其他文件，例如 Documents [文件夹中的](hololens-diagnostic-logs.md#offline-diagnostics) 诊断文件。</span><span class="sxs-lookup"><span data-stu-id="c26c4-191">You can get other files in other folders, such as [diagnostics files](hololens-diagnostic-logs.md#offline-diagnostics) from the Documents folder.</span></span>
- <span data-ttu-id="c26c4-192">在文件资源管理器，可以选择"设备属性"，查看 Windows Holographic OS 版本号 (固件版本) 、设备序列号和电池百分比。</span><span class="sxs-lookup"><span data-stu-id="c26c4-192">From File Explorer on your PC, you can select Device properties to see Windows Holographic OS version number (firmware version), device serial number, and battery percentage.</span></span>
- <span data-ttu-id="c26c4-193">如果组织已使用 MDM 禁用 [连接/AllowUSBConnection，](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 则将无法连接到设备。</span><span class="sxs-lookup"><span data-stu-id="c26c4-193">If your Organization has used MDM to disable [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) then you will be unable to connect to your device.</span></span>

## <a name="share-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="c26c4-194">共享混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="c26c4-194">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="c26c4-195">在 [Windows Holographic 版本 21H1](hololens-release-notes.md#windows-holographic-version-21h1)之前，捕获混合现实照片或视频后，将显示预览。</span><span class="sxs-lookup"><span data-stu-id="c26c4-195">Prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), after capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="c26c4-196">选择 **预览上方** 的"共享"图标，打开共享助手。</span><span class="sxs-lookup"><span data-stu-id="c26c4-196">Select the **Share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="c26c4-197">可以在那里选择要共享该照片或视频的终点。</span><span class="sxs-lookup"><span data-stu-id="c26c4-197">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="c26c4-198">在 Windows Holographic 版本 21H1 中，捕获混合现实照片或视频后，将显示预览。</span><span class="sxs-lookup"><span data-stu-id="c26c4-198">With Windows Holographic, version 21H1, after capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="c26c4-199">选择 **预览上方** 的"共享"图标，打开共享助手。</span><span class="sxs-lookup"><span data-stu-id="c26c4-199">Select the **Share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="c26c4-200">可以在其中选择要共享 (邮件、OneDrive 等) 的终点。</span><span class="sxs-lookup"><span data-stu-id="c26c4-200">From there, you can select the end point (Mail, OneDrive, etc.) to which you'd like to share that photo or video.</span></span> <span data-ttu-id="c26c4-201">你还可以通过转到 " **设置-> 系统 > 共享体验**，使你的 HoloLens 与附近的设备共享。</span><span class="sxs-lookup"><span data-stu-id="c26c4-201">You can also enable your HoloLens to share with nearby devices by going to **Settings -> System -> Shared Experiences**.</span></span> <span data-ttu-id="c26c4-202">有关更多详细信息，请参阅 [在 Windows 10 中与附近设备共享内容](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)。</span><span class="sxs-lookup"><span data-stu-id="c26c4-202">For more details, read [Share things with nearby devices in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).</span></span>

> [!TIP] 
> <span data-ttu-id="c26c4-203">你还可以通过自动上传混合现实照片和视频，与 OneDrive 共享混合现实照片和视频。</span><span class="sxs-lookup"><span data-stu-id="c26c4-203">You can also share mixed reality photos and videos from OneDrive by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="c26c4-204">在 HoloLens 上打开 OneDrive 应用并使用 **个人 [Microsoft 帐户](https://account.microsoft.com)** 登录（如果尚未登录）。</span><span class="sxs-lookup"><span data-stu-id="c26c4-204">Open the OneDrive app on HoloLens and sign in with a **personal [Microsoft account](https://account.microsoft.com)**, if you haven't already.</span></span> <span data-ttu-id="c26c4-205">选择 " **设置** " 图标，然后选择 " **相机上传**"。</span><span class="sxs-lookup"><span data-stu-id="c26c4-205">Select the **Settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="c26c4-206">打开相机上传。</span><span class="sxs-lookup"><span data-stu-id="c26c4-206">Turn Camera upload on.</span></span> <span data-ttu-id="c26c4-207">当你在 HoloLens 上启动应用时，你的混合现实照片和视频现在将上传到 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="c26c4-207">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="c26c4-208">仅当使用个人 Microsoft 帐户登录到 OneDrive 时，才能在 OneDrive 中启用相机上传。</span><span class="sxs-lookup"><span data-stu-id="c26c4-208">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="c26c4-209">如果使用工作或学校帐户设置了 HoloLens，则可以在 OneDrive 应用中添加个人 Microsoft 帐户来启用此功能。</span><span class="sxs-lookup"><span data-stu-id="c26c4-209">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <a name="limitations-of-mixed-reality-capture"></a><span data-ttu-id="c26c4-210">混合现实捕获的限制</span><span class="sxs-lookup"><span data-stu-id="c26c4-210">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="c26c4-211">使用混合现实捕获时，HoloLens 的帧速率将减半到 30 Hz。</span><span class="sxs-lookup"><span data-stu-id="c26c4-211">While using mixed reality capture, the frame rate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="c26c4-212">如果照片/视频相机已被其他应用程序使用、实时流式处理或系统资源不足，则可能会降低照片和视频的分辨率。</span><span class="sxs-lookup"><span data-stu-id="c26c4-212">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

### <a name="maximum-recording-length"></a><span data-ttu-id="c26c4-213">最大记录长度</span><span class="sxs-lookup"><span data-stu-id="c26c4-213">Maximum recording length</span></span>

<span data-ttu-id="c26c4-214">在早于 Windows 全息版本20H2 的 HoloLens 2 设备上，在设备上录制的视频的最大长度限制为五分钟。</span><span class="sxs-lookup"><span data-stu-id="c26c4-214">On HoloLens 2 devices before the Windows Holographic, version 20H2, videos recorded on the device were limited to maximum length of five minutes.</span></span>

<span data-ttu-id="c26c4-215">由于客户反馈，我们已增加 [混合现实捕获](holographic-photos-and-videos.md)的记录长度。</span><span class="sxs-lookup"><span data-stu-id="c26c4-215">Due to customer feedback, we’ve increased the recording length of [mixed reality captures](holographic-photos-and-videos.md).</span></span> <span data-ttu-id="c26c4-216">默认情况下，混合现实捕获将不再限制为5分钟，但会根据可用磁盘空间来计算最大记录长度。</span><span class="sxs-lookup"><span data-stu-id="c26c4-216">Mixed reality captures will no longer be limited to 5 minutes by default, but instead will calculate the maximum recording length based on available disk space.</span></span> <span data-ttu-id="c26c4-217">该设备将根据可用磁盘空间（最大为总磁盘空间的80%）估算最大视频录制持续时间。</span><span class="sxs-lookup"><span data-stu-id="c26c4-217">The device will estimate the max video recording duration based on available disk space up to 80% of the total disk space.</span></span>

> [!NOTE]
> <span data-ttu-id="c26c4-218">如果发生以下情况之一，则 HoloLens 将使用默认视频录制长度 (5 分钟) ：</span><span class="sxs-lookup"><span data-stu-id="c26c4-218">The HoloLens will use default video recording length (5 minutes) if one of the following occurs:</span></span>
> - <span data-ttu-id="c26c4-219">预计的最大记录持续时间小于默认的5分钟。</span><span class="sxs-lookup"><span data-stu-id="c26c4-219">The estimated max recording duration is smaller than the default 5 mins.</span></span>
> - <span data-ttu-id="c26c4-220">可用磁盘空间小于总磁盘空间的20%。</span><span class="sxs-lookup"><span data-stu-id="c26c4-220">The available disk space is less than 20% of the total disk space.</span></span>

## <a name="default-file-format-and-resolution"></a><span data-ttu-id="c26c4-221">默认文件格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="c26c4-221">Default file format and resolution</span></span>

### <a name="default-photo-format-and-resolution"></a><span data-ttu-id="c26c4-222">默认照片格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="c26c4-222">Default photo format and resolution</span></span>

|  <span data-ttu-id="c26c4-223">设备</span><span class="sxs-lookup"><span data-stu-id="c26c4-223">Device</span></span>  |  <span data-ttu-id="c26c4-224">格式</span><span class="sxs-lookup"><span data-stu-id="c26c4-224">Format</span></span>  |  <span data-ttu-id="c26c4-225">分机</span><span class="sxs-lookup"><span data-stu-id="c26c4-225">Extension</span></span>  |  <span data-ttu-id="c26c4-226">解决方法</span><span class="sxs-lookup"><span data-stu-id="c26c4-226">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="c26c4-227">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c26c4-227">HoloLens 2</span></span> | [<span data-ttu-id="c26c4-228">JPEG</span><span class="sxs-lookup"><span data-stu-id="c26c4-228">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="c26c4-229">.jpg</span><span class="sxs-lookup"><span data-stu-id="c26c4-229">.jpg</span></span> | <span data-ttu-id="c26c4-230">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="c26c4-230">3904x2196px</span></span> |
| <span data-ttu-id="c26c4-231">HoloLens（第 1 代）</span><span class="sxs-lookup"><span data-stu-id="c26c4-231">HoloLens (1st gen)</span></span> | [<span data-ttu-id="c26c4-232">JPEG</span><span class="sxs-lookup"><span data-stu-id="c26c4-232">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="c26c4-233">.jpg</span><span class="sxs-lookup"><span data-stu-id="c26c4-233">.jpg</span></span> | <span data-ttu-id="c26c4-234">1408x792px</span><span class="sxs-lookup"><span data-stu-id="c26c4-234">1408x792px</span></span> |

### <a name="recorded-video-format-and-resolution"></a><span data-ttu-id="c26c4-235">录制的视频格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="c26c4-235">Recorded video format and resolution</span></span>

| <span data-ttu-id="c26c4-236">设备</span><span class="sxs-lookup"><span data-stu-id="c26c4-236">Device</span></span> | <span data-ttu-id="c26c4-237">格式</span><span class="sxs-lookup"><span data-stu-id="c26c4-237">Format</span></span> | <span data-ttu-id="c26c4-238">分机</span><span class="sxs-lookup"><span data-stu-id="c26c4-238">Extension</span></span> | <span data-ttu-id="c26c4-239">解决方法</span><span class="sxs-lookup"><span data-stu-id="c26c4-239">Resolution</span></span> | <span data-ttu-id="c26c4-240">Speed</span><span class="sxs-lookup"><span data-stu-id="c26c4-240">Speed</span></span> | <span data-ttu-id="c26c4-241">音频</span><span class="sxs-lookup"><span data-stu-id="c26c4-241">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="c26c4-242">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="c26c4-242">HoloLens 2</span></span> | [<span data-ttu-id="c26c4-243">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="c26c4-243">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="c26c4-244">.mp4</span><span class="sxs-lookup"><span data-stu-id="c26c4-244">.mp4</span></span> | <span data-ttu-id="c26c4-245">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="c26c4-245">1920x1080px</span></span> | <span data-ttu-id="c26c4-246">30fps</span><span class="sxs-lookup"><span data-stu-id="c26c4-246">30fps</span></span> | <span data-ttu-id="c26c4-247">48kHz 立体声</span><span class="sxs-lookup"><span data-stu-id="c26c4-247">48kHz Stereo</span></span> |
| <span data-ttu-id="c26c4-248">HoloLens（第 1 代）</span><span class="sxs-lookup"><span data-stu-id="c26c4-248">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="c26c4-249">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="c26c4-249">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="c26c4-250">.mp4</span><span class="sxs-lookup"><span data-stu-id="c26c4-250">.mp4</span></span> | <span data-ttu-id="c26c4-251">1216x684px</span><span class="sxs-lookup"><span data-stu-id="c26c4-251">1216x684px</span></span> | <span data-ttu-id="c26c4-252">24fps</span><span class="sxs-lookup"><span data-stu-id="c26c4-252">24fps</span></span> | <span data-ttu-id="c26c4-253">48kHz 立体声</span><span class="sxs-lookup"><span data-stu-id="c26c4-253">48kHz Stereo</span></span> |
