---
title: 捕获和管理混合现实照片和视频
description: 了解如何使用 HoloLens 混合现实设备捕获、查看和共享混合现实照片和视频。
keywords: hololens， 照片， 视频， 捕获， mrc， 混合现实捕获， 照片， 相机， 流， 实时流， 演示
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
ms.openlocfilehash: 6b7bb29ab76a16aa518ca38ee04f434dfd0cf0c7
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283503"
---
# <span data-ttu-id="7a196-104">创建混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="7a196-104">Create mixed reality photos and videos</span></span>

<span data-ttu-id="7a196-105">HoloLens 为用户提供了将现实世界与数字世界混合的体验。</span><span class="sxs-lookup"><span data-stu-id="7a196-105">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="7a196-106">混合现实捕获 (MRC) 允许你将体验捕获为照片或视频，或与他人实时共享所见内容。</span><span class="sxs-lookup"><span data-stu-id="7a196-106">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="7a196-107">混合现实捕获使用第一人称视角，以便其他人可以在你看到全息影像时看到全息影像。</span><span class="sxs-lookup"><span data-stu-id="7a196-107">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="7a196-108">对于第三人称视角，请使用观看 [者视图](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。</span><span class="sxs-lookup"><span data-stu-id="7a196-108">For a third-person point of view, use [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="7a196-109">观众视图对于演示尤其有用。</span><span class="sxs-lookup"><span data-stu-id="7a196-109">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="7a196-110">虽然在好友和同事之间共享视频很有趣，但视频还可以帮助其他人使用应用或沟通应用和体验问题。</span><span class="sxs-lookup"><span data-stu-id="7a196-110">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="7a196-111">如果你无法启动混合现实捕获体验，并且 HoloLens 是工作设备，请与系统管理员联系。</span><span class="sxs-lookup"><span data-stu-id="7a196-111">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="7a196-112">可通过公司策略限制对相机的访问。</span><span class="sxs-lookup"><span data-stu-id="7a196-112">Access to the camera can be restricted through company policy.</span></span>

## <span data-ttu-id="7a196-113">捕获混合现实照片</span><span class="sxs-lookup"><span data-stu-id="7a196-113">Capture a mixed reality photo</span></span>

<span data-ttu-id="7a196-114">有几种方法可以拍摄 HoloLens 上混合现实的照片;可以使用硬件按钮、语音或"开始"菜单。</span><span class="sxs-lookup"><span data-stu-id="7a196-114">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="7a196-115">用于拍摄照片的硬件按钮</span><span class="sxs-lookup"><span data-stu-id="7a196-115">Hardware buttons to take photos</span></span>

<span data-ttu-id="7a196-116">若要快速拍摄当前视图的照片，请同时按调高音量和降低音量按钮。</span><span class="sxs-lookup"><span data-stu-id="7a196-116">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="7a196-117">这有点像屏幕截图或打印屏幕的 HoloLens 版本。</span><span class="sxs-lookup"><span data-stu-id="7a196-117">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="7a196-118">HoloLens 2 上的按钮位置</span><span class="sxs-lookup"><span data-stu-id="7a196-118">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="7a196-119">HoloLens 第一代 (上的按钮) </span><span class="sxs-lookup"><span data-stu-id="7a196-119">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="7a196-120">将**音量增加和\*\*\*\*音量**降低按钮按住三秒钟将开始录制视频，而不是拍摄照片。</span><span class="sxs-lookup"><span data-stu-id="7a196-120">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="7a196-121">若要停止录制，请 **同时点击调高** 音量 **和调低** 音量按钮。</span><span class="sxs-lookup"><span data-stu-id="7a196-121">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <span data-ttu-id="7a196-122">要拍摄照片的语音命令</span><span class="sxs-lookup"><span data-stu-id="7a196-122">Voice commands to take photos</span></span>

<span data-ttu-id="7a196-123">在 HoloLens 2 版本 2004 (及更高版本) ，说："拍摄照片"。</span><span class="sxs-lookup"><span data-stu-id="7a196-123">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="7a196-124">在 HoloLens (第一代) 或 HoloLens 2 版本 1903 上，说："你好小娜，拍摄照片。"</span><span class="sxs-lookup"><span data-stu-id="7a196-124">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <span data-ttu-id="7a196-125">"开始"菜单以拍摄照片</span><span class="sxs-lookup"><span data-stu-id="7a196-125">Start menu to take photos</span></span>

<span data-ttu-id="7a196-126">使用"开始"手势 **转到"开始**"菜单，然后选择 **相机** 图标。</span><span class="sxs-lookup"><span data-stu-id="7a196-126">Use the Start gesture to go to **Start**, then select the **camera** icon.</span></span>

<span data-ttu-id="7a196-127">将头指向要捕获的方向，然后通过空点击来拍摄照片[](hololens2-basic-usage.md#touch-holograms-near-you)。</span><span class="sxs-lookup"><span data-stu-id="7a196-127">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="7a196-128">你可以继续空点击并捕获其他照片。</span><span class="sxs-lookup"><span data-stu-id="7a196-128">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="7a196-129">你捕获的任何照片都将保存到你的设备。</span><span class="sxs-lookup"><span data-stu-id="7a196-129">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="7a196-130">再次使用"开始"手势结束照片捕获。</span><span class="sxs-lookup"><span data-stu-id="7a196-130">Use the Start gesture again to end photo capture.</span></span>  

## <span data-ttu-id="7a196-131">捕获混合现实视频</span><span class="sxs-lookup"><span data-stu-id="7a196-131">Capture a mixed reality video</span></span>

<span data-ttu-id="7a196-132">有几种方法在 HoloLens 上录制混合现实视频;可以使用硬件按钮、语音或"开始"菜单。</span><span class="sxs-lookup"><span data-stu-id="7a196-132">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="7a196-133">用于录制视频的硬件按钮</span><span class="sxs-lookup"><span data-stu-id="7a196-133">Hardware buttons to record videos</span></span>

<span data-ttu-id="7a196-134">录制视频的最快方法就是同时长按调高音量和调\*\*\*\* 低音量按钮\*\*\*\*，直到开始倒计时三秒钟。</span><span class="sxs-lookup"><span data-stu-id="7a196-134">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="7a196-135">若要停止录制，请同时点击这两个按钮。</span><span class="sxs-lookup"><span data-stu-id="7a196-135">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="7a196-136">同时快速**按调高**音量\*\*\*\* 和调低音量按钮将拍摄照片，而不是录制视频。</span><span class="sxs-lookup"><span data-stu-id="7a196-136">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <span data-ttu-id="7a196-137">录制视频的语音</span><span class="sxs-lookup"><span data-stu-id="7a196-137">Voice to record videos</span></span>

<span data-ttu-id="7a196-138">在 HoloLens 2 版本 2004 (及更高版本) ，例如："开始录制"。</span><span class="sxs-lookup"><span data-stu-id="7a196-138">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="7a196-139">若要停止录制，请说出"停止录制"。</span><span class="sxs-lookup"><span data-stu-id="7a196-139">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="7a196-140">在 HoloLens (第一代) 或 HoloLens 2 版本 1903 上，说："你好小娜，开始录制。"</span><span class="sxs-lookup"><span data-stu-id="7a196-140">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="7a196-141">若要停止录制，请说出"你好小娜，停止录制"。</span><span class="sxs-lookup"><span data-stu-id="7a196-141">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <span data-ttu-id="7a196-142">录制视频的"开始"菜单</span><span class="sxs-lookup"><span data-stu-id="7a196-142">Start menu to record videos</span></span>

<span data-ttu-id="7a196-143">使用"开始"手势转到"开始 **"** 菜单，然后选择 **视频** 图标。</span><span class="sxs-lookup"><span data-stu-id="7a196-143">Use the Start gesture to go to **Start**, then select the **video** icon.</span></span> <span data-ttu-id="7a196-144">将头指向要捕获的方向，然后通过空点击开始录制。 [](hololens2-basic-usage.md#touch-holograms-near-you)</span><span class="sxs-lookup"><span data-stu-id="7a196-144">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="7a196-145">将进行三秒钟倒计时，你的录制将开始。</span><span class="sxs-lookup"><span data-stu-id="7a196-145">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="7a196-146">若要停止录制，请使用"开始"手势并选择突出显示 **的视频** 图标。</span><span class="sxs-lookup"><span data-stu-id="7a196-146">To stop recording, use the Start gesture and select the highlighted **video** icon.</span></span> <span data-ttu-id="7a196-147">视频将保存到设备。</span><span class="sxs-lookup"><span data-stu-id="7a196-147">The video will be saved to your device.</span></span>

> [!NOTE]
> **<span data-ttu-id="7a196-148">仅适用于 HoloLens (第一代) 应用</span><span class="sxs-lookup"><span data-stu-id="7a196-148">Applies to HoloLens (1st gen) only</span></span>**  
> <span data-ttu-id="7a196-149">Windows [10 2018 年 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) 月更新更改了"开始"手势和 Windows 按钮在 HoloLens 第一代 (的行为) 。</span><span class="sxs-lookup"><span data-stu-id="7a196-149">The [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="7a196-150">更新之前，"开始"手势或 Windows 按钮将停止视频录制。</span><span class="sxs-lookup"><span data-stu-id="7a196-150">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="7a196-151">但是，更新后，如果你使用沉浸式应用) ，"开始"手势或 Windows\*\*\*\* 按钮将打开"开始"菜单 (或快速操作菜单，你可以从中选择突出显示的视频图标停止录制\*\*\*\*。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="7a196-151">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <span data-ttu-id="7a196-152">实时共享你所看到的信息</span><span class="sxs-lookup"><span data-stu-id="7a196-152">Share what you see in real-time</span></span>

<span data-ttu-id="7a196-153">你可以与好友和同事实时共享你在 HoloLens 中看到什么。</span><span class="sxs-lookup"><span data-stu-id="7a196-153">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="7a196-154">有一些方法可用：</span><span class="sxs-lookup"><span data-stu-id="7a196-154">There are a few methods available:</span></span>

1. <span data-ttu-id="7a196-155">连接到启用了 Miracast 的设备或适配器以观看电视。</span><span class="sxs-lookup"><span data-stu-id="7a196-155">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="7a196-156">使用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 在电脑上观看</span><span class="sxs-lookup"><span data-stu-id="7a196-156">Using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="7a196-157">使用 [Microsoft HoloLens 配套应用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 在电脑上观看。</span><span class="sxs-lookup"><span data-stu-id="7a196-157">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="7a196-158">部署 [Microsoft Dynamics 365 远程协助](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 应用，使前端工作人员能够将看到内容流式传输给远程专家。</span><span class="sxs-lookup"><span data-stu-id="7a196-158">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="7a196-159">然后，远程专家可以口头指导第一线工作人员，或者通过注释他们的世界。</span><span class="sxs-lookup"><span data-stu-id="7a196-159">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="7a196-160">通过 Windows Device Portal 或 Microsoft HoloLens 配套应用共享你看到的内容需要你的 HoloLens 进入 [开发人员模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="7a196-160">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <span data-ttu-id="7a196-161">使用 Miracast 流视频</span><span class="sxs-lookup"><span data-stu-id="7a196-161">Stream video with Miracast</span></span>

<span data-ttu-id="7a196-162">使用"开始"手势 **转到"开始**"菜单，然后选择 **连接** 图标。</span><span class="sxs-lookup"><span data-stu-id="7a196-162">Use the Start gesture to go to **Start**, then select the **connect** icon.</span></span> <span data-ttu-id="7a196-163">从出现的选取器中，选择要连接到的启用了 Miracast 的设备或适配器。</span><span class="sxs-lookup"><span data-stu-id="7a196-163">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="7a196-164">若要停止共享，请使用"开始"手势并选择突出显示的 **"连接"** 图标。</span><span class="sxs-lookup"><span data-stu-id="7a196-164">To stop sharing, use the Start gesture and select the highlighted **connect** icon.</span></span> <span data-ttu-id="7a196-165">由于你正在流式传输，因此不会将任何内容保存到设备。</span><span class="sxs-lookup"><span data-stu-id="7a196-165">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="7a196-166">从 [Windows 10 2018 年 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)月更新 (HoloLens 第一代) 启用了 Miracast 支持。</span><span class="sxs-lookup"><span data-stu-id="7a196-166">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).</span></span>

### <span data-ttu-id="7a196-167">Windows Device Portal 实时视频</span><span class="sxs-lookup"><span data-stu-id="7a196-167">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="7a196-168">由于通过 Windows Device Portal 共享需要在 HoloLens 上启用开发人员模式，请按照开发人员文档中的说明设置开发人员模式并[导航 Windows Device Portal。](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)</span><span class="sxs-lookup"><span data-stu-id="7a196-168">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <span data-ttu-id="7a196-169">Microsoft HoloLens 配套应用</span><span class="sxs-lookup"><span data-stu-id="7a196-169">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="7a196-170">由于通过 Microsoft HoloLens 配套应用共享需要在 HoloLens 上启用开发人员模式，请按照开发人员文档中的说明设置 [开发人员模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="7a196-170">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="7a196-171">然后，下载 [Microsoft HoloLens 配套](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 应用，并按照应用内的说明连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="7a196-171">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="7a196-172">使用 HoloLens 设置应用后，从应用的主菜单中\*\*\*\* 选择"实时流"选项。</span><span class="sxs-lookup"><span data-stu-id="7a196-172">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <span data-ttu-id="7a196-173">查看混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="7a196-173">View your mixed reality photos and videos</span></span>

<span data-ttu-id="7a196-174">混合现实照片和视频将保存到设备的"相机照片"中。</span><span class="sxs-lookup"><span data-stu-id="7a196-174">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="7a196-175">可以使用"文件资源管理器"应用浏览 HoloLens 上此文件夹的内容， ("图片">"相机) 。</span><span class="sxs-lookup"><span data-stu-id="7a196-175">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to Pictures > Camera Roll).</span></span>

<span data-ttu-id="7a196-176">还可以在预安装在 HoloLens 上的"照片"应用中查看混合现实照片和视频。</span><span class="sxs-lookup"><span data-stu-id="7a196-176">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="7a196-177">若要固定你世界的照片，请在"照片"应用中选择它，然后选择"**在混合世界中放置"。**</span><span class="sxs-lookup"><span data-stu-id="7a196-177">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="7a196-178">放置照片后，你可以在你的世界四处移动照片。</span><span class="sxs-lookup"><span data-stu-id="7a196-178">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="7a196-179">若要在连接到 HoloLens 的电脑上查看和/或保存混合现实照片和视频，可以通过[MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)使用[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)或电脑的文件资源管理器。</span><span class="sxs-lookup"><span data-stu-id="7a196-179">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

### <span data-ttu-id="7a196-180">使用文件资源管理器获取图片、视频和文件</span><span class="sxs-lookup"><span data-stu-id="7a196-180">Use File Explorer to get your pictures, videos and files</span></span>

<span data-ttu-id="7a196-181">与其他移动设备类似，将 HoloLens 连接到电脑以打开文件资源管理器，以访问 HoloLens 库 (照片、视频和文档) 轻松传输。</span><span class="sxs-lookup"><span data-stu-id="7a196-181">Similar to other mobile devices, connect your HoloLens to your PC to bring up File Explorer to access your HoloLens libraries (photos, videos, documents) for easy transfer.</span></span> <span data-ttu-id="7a196-182">此方法易于使用，不需要使用设备门户或 WLAN。</span><span class="sxs-lookup"><span data-stu-id="7a196-182">This method is easy to use and does not require the use of device portal or Wi-Fi.</span></span>

1. <span data-ttu-id="7a196-183">解锁设备。</span><span class="sxs-lookup"><span data-stu-id="7a196-183">Unlock the device.</span></span>
1. <span data-ttu-id="7a196-184">通过 USB 将设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="7a196-184">Connect the device to a PC via USB.</span></span>
1. <span data-ttu-id="7a196-185">文件资源管理器应在电脑上打开。</span><span class="sxs-lookup"><span data-stu-id="7a196-185">File Explorer should open on your PC.</span></span>
1. <span data-ttu-id="7a196-186">导航到：此电脑\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span><span class="sxs-lookup"><span data-stu-id="7a196-186">Navigate to: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span></span>
1. <span data-ttu-id="7a196-187">将所需的任何文件复制到电脑。</span><span class="sxs-lookup"><span data-stu-id="7a196-187">Copy whatever files you need to your PC.</span></span>

<span data-ttu-id="7a196-188">提示：</span><span class="sxs-lookup"><span data-stu-id="7a196-188">Tips:</span></span>
- <span data-ttu-id="7a196-189">如果你未看到任何文件，请确保登录到 HoloLens 以允许访问你的数据。</span><span class="sxs-lookup"><span data-stu-id="7a196-189">If you don't see any files, please ensure you sign in to your HoloLens to enable access to your data.</span></span>
- <span data-ttu-id="7a196-190">你可以获取其他文件夹中的其他文件，例如 Documents [文件夹中的](hololens-diagnostic-logs.md#offline-diagnostics) 诊断文件。</span><span class="sxs-lookup"><span data-stu-id="7a196-190">You can get other files in other folders, such as [diagnostics files](hololens-diagnostic-logs.md#offline-diagnostics) from the Documents folder.</span></span>
- <span data-ttu-id="7a196-191">在电脑上的文件资源管理器中，可以选择设备属性以查看 Windows 全息操作系统版本号 (固件版本) 、设备序列号和电池百分比。</span><span class="sxs-lookup"><span data-stu-id="7a196-191">From File Explorer on your PC, you can select Device properties to see Windows Holographic OS version number (firmware version), device serial number, and battery percentage.</span></span>
- <span data-ttu-id="7a196-192">如果组织已使用 MDM 禁用 [连接/AllowUSBConnection，](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 将无法连接到设备。</span><span class="sxs-lookup"><span data-stu-id="7a196-192">If your Organization has used MDM to disable [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) then you will be unable to connect to your device.</span></span>

## <span data-ttu-id="7a196-193">共享混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="7a196-193">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="7a196-194">捕获混合现实照片或视频后，将显示预览。</span><span class="sxs-lookup"><span data-stu-id="7a196-194">After capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="7a196-195">选择 **预览** 上方的共享图标可显示共享助手。</span><span class="sxs-lookup"><span data-stu-id="7a196-195">Select the **share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="7a196-196">你可以从该位置选择要共享该照片或视频的终点。</span><span class="sxs-lookup"><span data-stu-id="7a196-196">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="7a196-197">通过自动上传混合现实照片和视频，还可以从 OneDrive 共享混合现实照片和视频。</span><span class="sxs-lookup"><span data-stu-id="7a196-197">You can also share mixed reality photos and videos from OneDrive, by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="7a196-198">在 HoloLens 上打开 OneDrive 应用，然后使用 [个人 Microsoft](https://account.microsoft.com) 帐户登录（如果尚未登录）。</span><span class="sxs-lookup"><span data-stu-id="7a196-198">Open the OneDrive app on HoloLens and sign in with a personal [Microsoft account](https://account.microsoft.com) if you haven't already.</span></span> <span data-ttu-id="7a196-199">选择设置**图标**，然后选择"**相机上载"。**</span><span class="sxs-lookup"><span data-stu-id="7a196-199">Select the **settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="7a196-200">打开"相机上载"。</span><span class="sxs-lookup"><span data-stu-id="7a196-200">Turn Camera upload on.</span></span> <span data-ttu-id="7a196-201">每次在 HoloLens 上启动应用时，混合现实照片和视频现在都会上传到 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="7a196-201">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="7a196-202">只有在使用个人 Microsoft 帐户登录 OneDrive 时，才能在 OneDrive 中启用相机上传。</span><span class="sxs-lookup"><span data-stu-id="7a196-202">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="7a196-203">如果使用工作或学校帐户设置 HoloLens，可以在 OneDrive 应用中添加个人 Microsoft 帐户以启用此功能。</span><span class="sxs-lookup"><span data-stu-id="7a196-203">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <span data-ttu-id="7a196-204">混合现实捕获的限制</span><span class="sxs-lookup"><span data-stu-id="7a196-204">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="7a196-205">使用混合现实捕获时，HoloLens 的帧速率将放大至 30 Hz。</span><span class="sxs-lookup"><span data-stu-id="7a196-205">While using mixed reality capture, the framerate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="7a196-206">如果照片/视频相机已被另一个应用程序使用、实时流式传输或系统资源不足，则照片和视频的分辨率可能会降低。</span><span class="sxs-lookup"><span data-stu-id="7a196-206">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

### <span data-ttu-id="7a196-207">最大录音长度</span><span class="sxs-lookup"><span data-stu-id="7a196-207">Maximum recording length</span></span>

<span data-ttu-id="7a196-208">在 HoloLens 2 设备上，在 Windows 全息版之前，设备上录制的版本 20H2 视频被限制为最长 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="7a196-208">On HoloLens 2 devices before the Windows Holographic, version 20H2 videos recorded on the device were limited to maximum length of five minutes.</span></span>

<span data-ttu-id="7a196-209">由于客户反馈，我们增加了混合现实捕获 [的录制长度](holographic-photos-and-videos.md)。</span><span class="sxs-lookup"><span data-stu-id="7a196-209">Due to customer feedback we’ve increased the recording length of [mixed reality captures](holographic-photos-and-videos.md).</span></span> <span data-ttu-id="7a196-210">默认情况下，混合现实捕获将不再限制为 5 分钟，而是将基于可用磁盘空间计算最大录制长度。</span><span class="sxs-lookup"><span data-stu-id="7a196-210">Mixed reality captures will no longer be limited to 5 minutes by default but instead will calculate the maximum recording length based on available disk space.</span></span> <span data-ttu-id="7a196-211">设备将基于可用磁盘空间估计最大视频录制持续时间，最多占总磁盘空间的 80%。</span><span class="sxs-lookup"><span data-stu-id="7a196-211">The device will estimate the max video recording duration based on available disk space up to 80% of the total disk space.</span></span>

> [!NOTE]
> <span data-ttu-id="7a196-212">如果发生以下情况之一，HoloLens (5 分钟) 使用默认视频录制时长：</span><span class="sxs-lookup"><span data-stu-id="7a196-212">The HoloLens will use default video recording length (5 minutes) if one of the following occurs:</span></span>
> - <span data-ttu-id="7a196-213">估计的最大录制持续时间小于默认的 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="7a196-213">The estimated max recording duration is smaller than the default 5 mins.</span></span>
> - <span data-ttu-id="7a196-214">可用磁盘空间小于总磁盘空间的 20%。</span><span class="sxs-lookup"><span data-stu-id="7a196-214">The available disk space is less than 20% of the total disk space.</span></span>

## <span data-ttu-id="7a196-215">默认文件格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="7a196-215">Default file format and resolution</span></span>

### <span data-ttu-id="7a196-216">默认的照片格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="7a196-216">Default photo format and resolution</span></span>

|  <span data-ttu-id="7a196-217">设备</span><span class="sxs-lookup"><span data-stu-id="7a196-217">Device</span></span>  |  <span data-ttu-id="7a196-218">格式</span><span class="sxs-lookup"><span data-stu-id="7a196-218">Format</span></span>  |  <span data-ttu-id="7a196-219">扩展</span><span class="sxs-lookup"><span data-stu-id="7a196-219">Extension</span></span>  |  <span data-ttu-id="7a196-220">解决方案</span><span class="sxs-lookup"><span data-stu-id="7a196-220">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="7a196-221">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="7a196-221">HoloLens 2</span></span> | [<span data-ttu-id="7a196-222">JPEG</span><span class="sxs-lookup"><span data-stu-id="7a196-222">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="7a196-223">.jpg</span><span class="sxs-lookup"><span data-stu-id="7a196-223">.jpg</span></span> | <span data-ttu-id="7a196-224">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="7a196-224">3904x2196px</span></span> |
| <span data-ttu-id="7a196-225">HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="7a196-225">HoloLens (1st gen)</span></span> | [<span data-ttu-id="7a196-226">JPEG</span><span class="sxs-lookup"><span data-stu-id="7a196-226">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="7a196-227">.jpg</span><span class="sxs-lookup"><span data-stu-id="7a196-227">.jpg</span></span> | <span data-ttu-id="7a196-228">1408x792px</span><span class="sxs-lookup"><span data-stu-id="7a196-228">1408x792px</span></span> |

### <span data-ttu-id="7a196-229">录制的视频格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="7a196-229">Recorded video format and resolution</span></span>

| <span data-ttu-id="7a196-230">设备</span><span class="sxs-lookup"><span data-stu-id="7a196-230">Device</span></span> | <span data-ttu-id="7a196-231">格式</span><span class="sxs-lookup"><span data-stu-id="7a196-231">Format</span></span> | <span data-ttu-id="7a196-232">扩展</span><span class="sxs-lookup"><span data-stu-id="7a196-232">Extension</span></span> | <span data-ttu-id="7a196-233">解决方案</span><span class="sxs-lookup"><span data-stu-id="7a196-233">Resolution</span></span> | <span data-ttu-id="7a196-234">速度</span><span class="sxs-lookup"><span data-stu-id="7a196-234">Speed</span></span> | <span data-ttu-id="7a196-235">音频</span><span class="sxs-lookup"><span data-stu-id="7a196-235">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="7a196-236">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="7a196-236">HoloLens 2</span></span> | [<span data-ttu-id="7a196-237">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="7a196-237">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="7a196-238">.mp4</span><span class="sxs-lookup"><span data-stu-id="7a196-238">.mp4</span></span> | <span data-ttu-id="7a196-239">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="7a196-239">1920x1080px</span></span> | <span data-ttu-id="7a196-240">30fps</span><span class="sxs-lookup"><span data-stu-id="7a196-240">30fps</span></span> | <span data-ttu-id="7a196-241">48kHz 立体声</span><span class="sxs-lookup"><span data-stu-id="7a196-241">48kHz Stereo</span></span> |
| <span data-ttu-id="7a196-242">HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="7a196-242">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="7a196-243">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="7a196-243">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="7a196-244">.mp4</span><span class="sxs-lookup"><span data-stu-id="7a196-244">.mp4</span></span> | <span data-ttu-id="7a196-245">1216x684px</span><span class="sxs-lookup"><span data-stu-id="7a196-245">1216x684px</span></span> | <span data-ttu-id="7a196-246">24fps</span><span class="sxs-lookup"><span data-stu-id="7a196-246">24fps</span></span> | <span data-ttu-id="7a196-247">48kHz 立体声</span><span class="sxs-lookup"><span data-stu-id="7a196-247">48kHz Stereo</span></span> |
