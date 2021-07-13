---
title: 捕获、录制和共享混合现实照片和视频
description: 了解如何使用混合现实设备捕获、录制、查看和HoloLens混合现实照片和视频。 了解如何通过共享或Miracast共享。
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
ms.openlocfilehash: daced6fab65f779b7bd670bf1275f99ae5311d3f
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635953"
---
# <a name="create-mixed-reality-photos-and-videos"></a><span data-ttu-id="1e7a6-105">创建混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="1e7a6-105">Create mixed reality photos and videos</span></span>

<span data-ttu-id="1e7a6-106">HoloLens为用户提供将现实世界与数字世界混合的体验。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-106">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="1e7a6-107">混合现实捕获 (MRC) 使你能够将体验捕获为照片或视频，或与他人实时共享你所看到的内容。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-107">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="1e7a6-108">混合现实捕获使用第一人称视角，以便其他人可以在看到全息影像时看到全息影像。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-108">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="1e7a6-109">对于第三人称，请使用 [旁观视图](/windows/mixed-reality/spectator-view)。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-109">For a third-person point of view, use [spectator view](/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="1e7a6-110">旁观视图对于演示特别有用。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-110">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="1e7a6-111">虽然在朋友和同事之间共享视频很有趣，但视频还有助于指导其他人使用应用或与应用和体验交流问题。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-111">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="1e7a6-112">如果无法启动混合现实捕获体验，并且你的HoloLens是工作设备，请与系统管理员联系。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-112">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="1e7a6-113">可以通过公司策略限制对相机的访问。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-113">Access to the camera can be restricted through company policy.</span></span>

## <a name="capture-a-mixed-reality-photo"></a><span data-ttu-id="1e7a6-114">捕获混合现实照片</span><span class="sxs-lookup"><span data-stu-id="1e7a6-114">Capture a mixed reality photo</span></span>

<span data-ttu-id="1e7a6-115">有几种方法可以拍摄混合现实的照片，HoloLens;可以使用硬件按钮、语音或"开始"菜单。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-115">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-take-photos"></a><span data-ttu-id="1e7a6-116">用于拍摄照片的硬件按钮</span><span class="sxs-lookup"><span data-stu-id="1e7a6-116">Hardware buttons to take photos</span></span>

<span data-ttu-id="1e7a6-117">若要快速拍摄当前视图的照片，请同时按音量调高和音量降低按钮。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-117">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="1e7a6-118">这有点与屏幕截图HoloLens打印屏幕的版本类似。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-118">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="1e7a6-119">按钮位置HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="1e7a6-119">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="1e7a6-120">第一代HoloLens (上的按钮) </span><span class="sxs-lookup"><span data-stu-id="1e7a6-120">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="1e7a6-121">将 **音量调高** 和 **音量** 降低按钮按住三秒钟会开始录制视频，而不是拍照。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-121">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="1e7a6-122">若要停止录制，请 **同时点击音量** 增加 **和音量** 降低按钮。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-122">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <a name="voice-commands-to-take-photos"></a><span data-ttu-id="1e7a6-123">用于拍摄照片的语音命令</span><span class="sxs-lookup"><span data-stu-id="1e7a6-123">Voice commands to take photos</span></span>

<span data-ttu-id="1e7a6-124">在 HoloLens 2，版本 2004 (及更高版本) ，例如："拍照"。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-124">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="1e7a6-125">在HoloLens (第一代) 或 HoloLens 2 版本 1903 上，说："你好，Cortana，拍照。"</span><span class="sxs-lookup"><span data-stu-id="1e7a6-125">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <a name="start-menu-to-take-photos"></a><span data-ttu-id="1e7a6-126">"开始"菜单照片</span><span class="sxs-lookup"><span data-stu-id="1e7a6-126">Start menu to take photos</span></span>

<span data-ttu-id="1e7a6-127">使用"开始"手势转到" **开始"，** 然后选择" **相机"** 图标。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-127">Use the Start gesture to go to **Start**, then select the **Camera** icon.</span></span>

<span data-ttu-id="1e7a6-128">将头部指向要捕获的方向，然后通过敲击来拍摄照片[](hololens2-basic-usage.md#touch-holograms-near-you)。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-128">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="1e7a6-129">可以继续进行空敲击并捕获其他照片。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-129">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="1e7a6-130">捕获的任何照片都将保存到设备。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-130">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="1e7a6-131">再次使用"开始"手势结束照片捕获。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-131">Use the Start gesture again to end photo capture.</span></span>  

## <a name="capture-a-mixed-reality-video"></a><span data-ttu-id="1e7a6-132">捕获混合现实视频</span><span class="sxs-lookup"><span data-stu-id="1e7a6-132">Capture a mixed reality video</span></span>

<span data-ttu-id="1e7a6-133">有几种方法可以录制有关混合现实的视频，HoloLens;可以使用硬件按钮、语音或"开始"菜单。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-133">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-record-videos"></a><span data-ttu-id="1e7a6-134">用于录制视频的硬件按钮</span><span class="sxs-lookup"><span data-stu-id="1e7a6-134">Hardware buttons to record videos</span></span>

<span data-ttu-id="1e7a6-135">录制视频的最快方法就是同时按住音量和音量降低按钮，直到开始倒计时 3 秒。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-135">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="1e7a6-136">若要停止录制，请同时点击这两个按钮。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-136">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="1e7a6-137">同时快速 **向上按下** 音量和音量降低按钮会拍摄照片，而不是录制视频。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-137">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <a name="voice-to-record-videos"></a><span data-ttu-id="1e7a6-138">录制视频的语音</span><span class="sxs-lookup"><span data-stu-id="1e7a6-138">Voice to record videos</span></span>

<span data-ttu-id="1e7a6-139">在 HoloLens 2，版本 2004 (及更高版本) ，例如："开始录制"。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-139">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="1e7a6-140">若要停止录制，请说"停止录制"。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-140">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="1e7a6-141">在HoloLens (第一代) 或HoloLens 2版本 1903 上，说："你好，Cortana，开始录制。"</span><span class="sxs-lookup"><span data-stu-id="1e7a6-141">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="1e7a6-142">若要停止录制，请说"你好Cortana，停止录制。"</span><span class="sxs-lookup"><span data-stu-id="1e7a6-142">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <a name="start-menu-to-record-videos"></a><span data-ttu-id="1e7a6-143">"开始"菜单录制视频</span><span class="sxs-lookup"><span data-stu-id="1e7a6-143">Start menu to record videos</span></span>

<span data-ttu-id="1e7a6-144">使用"开始"手势转到" **开始"，** 然后选择" **视频"** 图标。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-144">Use the Start gesture to go to **Start**, then select the **Video** icon.</span></span> <span data-ttu-id="1e7a6-145">将头部指向要捕获的方向，然后按 [Air tap](hololens2-basic-usage.md#touch-holograms-near-you) 开始录制。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-145">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="1e7a6-146">将进行三秒倒计时，记录将开始。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-146">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="1e7a6-147">若要停止录制，请使用"开始"手势并选择突出显示 **的视频** 图标。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-147">To stop recording, use the Start gesture and select the highlighted **Video** icon.</span></span> <span data-ttu-id="1e7a6-148">视频将保存到设备。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-148">The video will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="1e7a6-149">**仅适用于第HoloLens (代)**</span><span class="sxs-lookup"><span data-stu-id="1e7a6-149">**Applies to HoloLens (1st gen) only**</span></span>  
> <span data-ttu-id="1e7a6-150">此[Windows 10 2018 年 10 月更新](/windows/mixed-reality/release-notes-october-2018)更改"开始"手势和Windows按钮在HoloLens (第一代) 。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-150">The [Windows 10 October 2018 Update](/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="1e7a6-151">更新之前，"开始"手势Windows按钮将停止视频录制。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-151">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="1e7a6-152">但是，更新后，"开始手势"或"Windows"按钮会打开"开始"菜单 (或快速操作菜单（如果正在沉浸式应用) 中，可以从中选择突出显示的视频图标来停止录制。 </span><span class="sxs-lookup"><span data-stu-id="1e7a6-152">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <a name="share-what-you-see-in-real-time"></a><span data-ttu-id="1e7a6-153">实时共享看到</span><span class="sxs-lookup"><span data-stu-id="1e7a6-153">Share what you see in real-time</span></span>

<span data-ttu-id="1e7a6-154">可以与朋友和同事实时HoloLens共享你在活动时看到什么。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-154">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="1e7a6-155">有一些方法可用：</span><span class="sxs-lookup"><span data-stu-id="1e7a6-155">There are a few methods available:</span></span>

1. <span data-ttu-id="1e7a6-156">连接到启用了Miracast或适配器的设备或适配器，以在电视上观看。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-156">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="1e7a6-157">使用[Windows 设备门户](/windows/mixed-reality/using-the-windows-device-portal)在电脑上观看</span><span class="sxs-lookup"><span data-stu-id="1e7a6-157">Using [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="1e7a6-158">使用[Microsoft HoloLens应用在](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)电脑上观看。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-158">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="1e7a6-159">部署[Microsoft Dynamics 365 Remote Assist应用](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)，使一线工作人员能够将看到内容流式传输给远程专家。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-159">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="1e7a6-160">然后，远程专家可以指导一线工作人员进行言语或批注。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-160">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="1e7a6-161">通过应用或Windows 设备门户应用Microsoft HoloLens看到的信息需要HoloLens开发人员[模式](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-161">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <a name="stream-video-with-miracast"></a><span data-ttu-id="1e7a6-162">使用流式传输Miracast</span><span class="sxs-lookup"><span data-stu-id="1e7a6-162">Stream video with Miracast</span></span>

<span data-ttu-id="1e7a6-163">使用"开始"手势转到"开始 **"，\*\*\*\*然后选择连接图标**。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-163">Use the Start gesture to go to **Start**, then select the **Connect** icon.</span></span> <span data-ttu-id="1e7a6-164">从出现的选取器中，Miracast连接到的已启用设备或适配器的设备。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-164">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="1e7a6-165">若要停止共享，请使用"开始"手势并选择突出显示的 **连接图标。**</span><span class="sxs-lookup"><span data-stu-id="1e7a6-165">To stop sharing, use the Start gesture and select the highlighted **Connect** icon.</span></span> <span data-ttu-id="1e7a6-166">由于已流式传输，因此不会将任何内容保存到设备。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-166">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="1e7a6-167">Miracast第一代 HoloLens (上启用了) 支持，从 Windows 10 2018 年 10 月更新[开始](/windows/mixed-reality/release-notes-october-2018)。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-167">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](/windows/mixed-reality/release-notes-october-2018).</span></span>

### <a name="real-time-video-with-windows-device-portal"></a><span data-ttu-id="1e7a6-168">实时视频与Windows 设备门户</span><span class="sxs-lookup"><span data-stu-id="1e7a6-168">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="1e7a6-169">由于通过 Windows 设备门户 共享需要在 HoloLens 上启用开发人员模式，因此请按照开发人员文档中的说明设置开发人员模式并导航到[Windows 设备门户。](/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="1e7a6-169">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <a name="microsoft-hololens-companion-app"></a><span data-ttu-id="1e7a6-170">Microsoft HoloLens配套应用</span><span class="sxs-lookup"><span data-stu-id="1e7a6-170">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="1e7a6-171">由于通过Microsoft HoloLens应用共享需要在 HoloLens 上启用开发人员模式，因此请按照开发人员文档中的说明设置[开发人员模式](/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-171">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="1e7a6-172">然后，下载[Microsoft HoloLens应用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)，并按照应用中的说明连接到HoloLens。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-172">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="1e7a6-173">使用应用设置应用后HoloLens，从应用的主菜单中选择"实时流"选项。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-173">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <a name="view-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="1e7a6-174">查看混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="1e7a6-174">View your mixed reality photos and videos</span></span>

<span data-ttu-id="1e7a6-175">混合现实照片和视频将保存到设备的"相机照片"中。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-175">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="1e7a6-176">可以使用 文件资源管理器 应用浏览 HoloLens 上此文件夹的内容 (导航到"照片>**相机) "** 。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-176">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to **Pictures > Camera Roll**).</span></span>

<span data-ttu-id="1e7a6-177">还可以在照片应用中查看混合现实照片和视频，该应用预安装在 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-177">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="1e7a6-178">若要将照片固定在你的世界，请在"照片"应用中选择它，然后选择"**将照片放在混合世界"。**</span><span class="sxs-lookup"><span data-stu-id="1e7a6-178">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="1e7a6-179">放置照片后，可以将其移动到你的世界。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-179">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="1e7a6-180">若要在连接到 HoloLens 的电脑上查看和/或保存混合现实HoloLens，可以通过 MTP Windows 设备门户或[电脑文件资源管理器设备](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。 [](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)</span><span class="sxs-lookup"><span data-stu-id="1e7a6-180">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a><span data-ttu-id="1e7a6-181">使用文件资源管理器获取图片、视频和文件</span><span class="sxs-lookup"><span data-stu-id="1e7a6-181">Use File Explorer to get your pictures, videos and files</span></span>

<span data-ttu-id="1e7a6-182">与其他移动设备类似，将 HoloLens 连接到电脑文件资源管理器以访问 HoloLens 库 (照片、视频、文档) 轻松传输。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-182">Similar to other mobile devices, connect your HoloLens to your PC to bring up File Explorer to access your HoloLens libraries (photos, videos, documents) for easy transfer.</span></span> <span data-ttu-id="1e7a6-183">此方法易于使用，不需要使用设备门户或 Wi-Fi。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-183">This method is easy to use and does not require the use of device portal or Wi-Fi.</span></span>

1. <span data-ttu-id="1e7a6-184">解锁设备。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-184">Unlock the device.</span></span>
1. <span data-ttu-id="1e7a6-185">连接 USB 将设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-185">Connect the device to a PC via USB.</span></span>
1. <span data-ttu-id="1e7a6-186">文件资源管理器应在电脑上打开。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-186">File Explorer should open on your PC.</span></span>
1. <span data-ttu-id="1e7a6-187">导航到：此电脑 \\ *yourhololensname*\Internal 存储\Pictures\Camera Roll</span><span class="sxs-lookup"><span data-stu-id="1e7a6-187">Navigate to: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span></span>
1. <span data-ttu-id="1e7a6-188">将所需的任何文件复制到电脑。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-188">Copy whatever files you need to your PC.</span></span>

<span data-ttu-id="1e7a6-189">提示：</span><span class="sxs-lookup"><span data-stu-id="1e7a6-189">Tips:</span></span>
- <span data-ttu-id="1e7a6-190">如果看不到任何文件，请确保登录到HoloLens以启用对数据的访问。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-190">If you don't see any files, please ensure you sign in to your HoloLens to enable access to your data.</span></span>
- <span data-ttu-id="1e7a6-191">可以从其他文件夹中获取其他文件，例如 Documents [文件夹中的](hololens-diagnostic-logs.md#offline-diagnostics) 诊断文件。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-191">You can get other files in other folders, such as [diagnostics files](hololens-diagnostic-logs.md#offline-diagnostics) from the Documents folder.</span></span>
- <span data-ttu-id="1e7a6-192">在文件资源管理器，可以选择"设备属性"，Windows全息 OS 版本号 (固件版本) 、设备序列号和电池百分比。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-192">From File Explorer on your PC, you can select Device properties to see Windows Holographic OS version number (firmware version), device serial number, and battery percentage.</span></span>
- <span data-ttu-id="1e7a6-193">如果组织已使用 MDM 禁用 [连接/AllowUSBConnection，](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 则将无法连接到设备。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-193">If your Organization has used MDM to disable [Connectivity/AllowUSBConnection](/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) then you will be unable to connect to your device.</span></span>

## <a name="share-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="1e7a6-194">共享混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="1e7a6-194">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="1e7a6-195">在全息[Windows版本 21H1](hololens-release-notes.md#windows-holographic-version-21h1)之前，捕获混合现实照片或视频后，将显示预览。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-195">Prior to [Windows Holographic, version 21H1](hololens-release-notes.md#windows-holographic-version-21h1), after capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="1e7a6-196">选择 **预览上方** 的"共享"图标，打开共享助手。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-196">Select the **Share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="1e7a6-197">可以在那里选择要共享该照片或视频的终点。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-197">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="1e7a6-198">在Windows全息版 21H1 中，捕获混合现实照片或视频后，将显示预览。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-198">With Windows Holographic, version 21H1, after capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="1e7a6-199">选择 **预览上方** 的"共享"图标，打开共享助手。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-199">Select the **Share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="1e7a6-200">可以在其中选择要共享该照片 (视频OneDrive邮件、) 等的终点。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-200">From there, you can select the end point (Mail, OneDrive, etc.) to which you'd like to share that photo or video.</span></span> <span data-ttu-id="1e7a6-201">还可通过访问 "HoloLens "-设置""共享体验"，>**设备与>共享**。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-201">You can also enable your HoloLens to share with nearby devices by going to **Settings -> System -> Shared Experiences**.</span></span> <span data-ttu-id="1e7a6-202">有关详细信息，请阅读 在 中[与附近的设备共享Windows 10。](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9)</span><span class="sxs-lookup"><span data-stu-id="1e7a6-202">For more details, read [Share things with nearby devices in Windows 10](https://support.microsoft.com/windows/share-things-with-nearby-devices-in-windows-10-0efbfe40-e3e2-581b-13f4-1a0e9936c2d9).</span></span>

> [!TIP] 
> <span data-ttu-id="1e7a6-203">还可通过自动上传混合现实照片OneDrive共享混合现实照片和视频。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-203">You can also share mixed reality photos and videos from OneDrive by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="1e7a6-204">打开 OneDrive 应用HoloLens，然后使用个人Microsoft 帐户登录（如果尚未登录 **）。 [](https://account.microsoft.com)**</span><span class="sxs-lookup"><span data-stu-id="1e7a6-204">Open the OneDrive app on HoloLens and sign in with a **personal [Microsoft account](https://account.microsoft.com)**, if you haven't already.</span></span> <span data-ttu-id="1e7a6-205">选择 **"设置** 图标，然后选择"**相机上传"。**</span><span class="sxs-lookup"><span data-stu-id="1e7a6-205">Select the **Settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="1e7a6-206">打开"相机上传"。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-206">Turn Camera upload on.</span></span> <span data-ttu-id="1e7a6-207">现在，每次在 OneDrive 上启动应用时，混合现实照片和视频都将上传到HoloLens。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-207">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="1e7a6-208">如果已使用个人OneDrive登录到 OneDrive，Microsoft 帐户。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-208">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="1e7a6-209">如果使用工作HoloLens帐户设置帐户，可以在 Microsoft 帐户 应用中添加OneDrive个人帐户以启用此功能。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-209">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <a name="limitations-of-mixed-reality-capture"></a><span data-ttu-id="1e7a6-210">混合现实捕获的限制</span><span class="sxs-lookup"><span data-stu-id="1e7a6-210">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="1e7a6-211">使用混合现实捕获时，HoloLens帧速率将缩小到 30 Hz。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-211">While using mixed reality capture, the frame rate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="1e7a6-212">如果另一个应用程序已在使用照片/视频相机、实时流式处理或系统资源不足，则照片和视频的分辨率可能会降低。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-212">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

### <a name="maximum-recording-length"></a><span data-ttu-id="1e7a6-213">最大录制长度</span><span class="sxs-lookup"><span data-stu-id="1e7a6-213">Maximum recording length</span></span>

<span data-ttu-id="1e7a6-214">在 HoloLens 2 Holographic 版本 20H2 之前Windows设备上，设备上录制的视频的最大长度限制为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-214">On HoloLens 2 devices before the Windows Holographic, version 20H2, videos recorded on the device were limited to maximum length of five minutes.</span></span>

<span data-ttu-id="1e7a6-215">根据客户反馈，我们增加了混合现实捕获 [的录制长度](holographic-photos-and-videos.md)。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-215">Due to customer feedback, we’ve increased the recording length of [mixed reality captures](holographic-photos-and-videos.md).</span></span> <span data-ttu-id="1e7a6-216">默认情况下，混合现实捕获将不再限制为 5 分钟，而是根据可用磁盘空间计算最大录制长度。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-216">Mixed reality captures will no longer be limited to 5 minutes by default, but instead will calculate the maximum recording length based on available disk space.</span></span> <span data-ttu-id="1e7a6-217">设备将基于可用磁盘空间估计最大视频录制持续时间，最多占总磁盘空间的 80%。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-217">The device will estimate the max video recording duration based on available disk space up to 80% of the total disk space.</span></span>

> [!NOTE]
> <span data-ttu-id="1e7a6-218">如果HoloLens以下情况之一， (视频录制长度) 5 分钟：</span><span class="sxs-lookup"><span data-stu-id="1e7a6-218">The HoloLens will use default video recording length (5 minutes) if one of the following occurs:</span></span>
> - <span data-ttu-id="1e7a6-219">估计的最大录制持续时间小于默认的 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-219">The estimated max recording duration is smaller than the default 5 mins.</span></span>
> - <span data-ttu-id="1e7a6-220">可用磁盘空间小于总磁盘空间的 20%。</span><span class="sxs-lookup"><span data-stu-id="1e7a6-220">The available disk space is less than 20% of the total disk space.</span></span>

## <a name="default-file-format-and-resolution"></a><span data-ttu-id="1e7a6-221">默认文件格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="1e7a6-221">Default file format and resolution</span></span>

### <a name="default-photo-format-and-resolution"></a><span data-ttu-id="1e7a6-222">默认照片格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="1e7a6-222">Default photo format and resolution</span></span>

|  <span data-ttu-id="1e7a6-223">设备</span><span class="sxs-lookup"><span data-stu-id="1e7a6-223">Device</span></span>  |  <span data-ttu-id="1e7a6-224">格式</span><span class="sxs-lookup"><span data-stu-id="1e7a6-224">Format</span></span>  |  <span data-ttu-id="1e7a6-225">分机</span><span class="sxs-lookup"><span data-stu-id="1e7a6-225">Extension</span></span>  |  <span data-ttu-id="1e7a6-226">解决方法</span><span class="sxs-lookup"><span data-stu-id="1e7a6-226">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="1e7a6-227">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="1e7a6-227">HoloLens 2</span></span> | [<span data-ttu-id="1e7a6-228">JPEG</span><span class="sxs-lookup"><span data-stu-id="1e7a6-228">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="1e7a6-229">.jpg</span><span class="sxs-lookup"><span data-stu-id="1e7a6-229">.jpg</span></span> | <span data-ttu-id="1e7a6-230">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="1e7a6-230">3904x2196px</span></span> |
| <span data-ttu-id="1e7a6-231">HoloLens（第 1 代）</span><span class="sxs-lookup"><span data-stu-id="1e7a6-231">HoloLens (1st gen)</span></span> | [<span data-ttu-id="1e7a6-232">JPEG</span><span class="sxs-lookup"><span data-stu-id="1e7a6-232">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="1e7a6-233">.jpg</span><span class="sxs-lookup"><span data-stu-id="1e7a6-233">.jpg</span></span> | <span data-ttu-id="1e7a6-234">1408x792px</span><span class="sxs-lookup"><span data-stu-id="1e7a6-234">1408x792px</span></span> |

### <a name="recorded-video-format-and-resolution"></a><span data-ttu-id="1e7a6-235">录制的视频格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="1e7a6-235">Recorded video format and resolution</span></span>

| <span data-ttu-id="1e7a6-236">设备</span><span class="sxs-lookup"><span data-stu-id="1e7a6-236">Device</span></span> | <span data-ttu-id="1e7a6-237">格式</span><span class="sxs-lookup"><span data-stu-id="1e7a6-237">Format</span></span> | <span data-ttu-id="1e7a6-238">分机</span><span class="sxs-lookup"><span data-stu-id="1e7a6-238">Extension</span></span> | <span data-ttu-id="1e7a6-239">解决方法</span><span class="sxs-lookup"><span data-stu-id="1e7a6-239">Resolution</span></span> | <span data-ttu-id="1e7a6-240">Speed</span><span class="sxs-lookup"><span data-stu-id="1e7a6-240">Speed</span></span> | <span data-ttu-id="1e7a6-241">音频</span><span class="sxs-lookup"><span data-stu-id="1e7a6-241">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="1e7a6-242">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="1e7a6-242">HoloLens 2</span></span> | [<span data-ttu-id="1e7a6-243">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="1e7a6-243">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="1e7a6-244">.mp4</span><span class="sxs-lookup"><span data-stu-id="1e7a6-244">.mp4</span></span> | <span data-ttu-id="1e7a6-245">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="1e7a6-245">1920x1080px</span></span> | <span data-ttu-id="1e7a6-246">30fps</span><span class="sxs-lookup"><span data-stu-id="1e7a6-246">30fps</span></span> | <span data-ttu-id="1e7a6-247">48kHz 立体声</span><span class="sxs-lookup"><span data-stu-id="1e7a6-247">48kHz Stereo</span></span> |
| <span data-ttu-id="1e7a6-248">HoloLens（第 1 代）</span><span class="sxs-lookup"><span data-stu-id="1e7a6-248">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="1e7a6-249">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="1e7a6-249">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="1e7a6-250">.mp4</span><span class="sxs-lookup"><span data-stu-id="1e7a6-250">.mp4</span></span> | <span data-ttu-id="1e7a6-251">1216x684px</span><span class="sxs-lookup"><span data-stu-id="1e7a6-251">1216x684px</span></span> | <span data-ttu-id="1e7a6-252">24fps</span><span class="sxs-lookup"><span data-stu-id="1e7a6-252">24fps</span></span> | <span data-ttu-id="1e7a6-253">48kHz 立体声</span><span class="sxs-lookup"><span data-stu-id="1e7a6-253">48kHz Stereo</span></span> |
