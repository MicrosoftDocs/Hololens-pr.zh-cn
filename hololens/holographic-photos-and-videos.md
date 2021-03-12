---
title: 捕获、录制和共享混合现实照片和视频
description: 了解如何使用 HoloLens 混合现实设备捕获、记录和查看混合现实照片和视频。 了解如何通过 Miracast 或收集的文件共享。
keywords: hololens， 照片， 视频， 捕获， mrc， 混合现实捕获， 照片， 相机， miracast， 流， 实时流， 演示， 记录
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
ms.openlocfilehash: 86ef4328869c15517732eedf3dfb9e2a8252e713
ms.sourcegitcommit: 047738224840013bede45dbb642a0ad2115a9c84
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406706"
---
# <a name="create-mixed-reality-photos-and-videos"></a><span data-ttu-id="4b3c0-105">创建混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="4b3c0-105">Create mixed reality photos and videos</span></span>

<span data-ttu-id="4b3c0-106">HoloLens 为用户提供了将现实世界与数字世界混合的体验。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-106">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="4b3c0-107">混合现实捕获 (MRC) 允许你将体验捕获为照片或视频，或与他人实时共享所看到内容。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-107">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="4b3c0-108">混合现实捕获使用第一人称视角，以便其他人可以在你看到全息影像时看到全息影像。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-108">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="4b3c0-109">对于第三人称的视点，请使用 [观众视图](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-109">For a third-person point of view, use [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="4b3c0-110">观众视图对于演示特别有用。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-110">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="4b3c0-111">虽然在朋友和同事之间共享视频很有趣，但视频还有助于教其他人使用应用或沟通应用和体验问题。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-111">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="4b3c0-112">如果无法启动混合现实捕获体验，并且 HoloLens 是工作设备，请与系统管理员联系。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-112">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="4b3c0-113">可通过公司策略限制对相机的访问。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-113">Access to the camera can be restricted through company policy.</span></span>

## <a name="capture-a-mixed-reality-photo"></a><span data-ttu-id="4b3c0-114">捕获混合现实照片</span><span class="sxs-lookup"><span data-stu-id="4b3c0-114">Capture a mixed reality photo</span></span>

<span data-ttu-id="4b3c0-115">有几种方法在 HoloLens 上拍摄混合现实照片;可以使用硬件按钮、语音或"开始"菜单。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-115">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-take-photos"></a><span data-ttu-id="4b3c0-116">用于拍摄照片的硬件按钮</span><span class="sxs-lookup"><span data-stu-id="4b3c0-116">Hardware buttons to take photos</span></span>

<span data-ttu-id="4b3c0-117">若要快速拍摄当前视图的照片，请同时按调高音量和降低音量按钮。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-117">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="4b3c0-118">这有点像屏幕截图或打印屏幕的 HoloLens 版本。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-118">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="4b3c0-119">HoloLens 2 上的按钮位置</span><span class="sxs-lookup"><span data-stu-id="4b3c0-119">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="4b3c0-120">HoloLens 第一代 (上的按钮) </span><span class="sxs-lookup"><span data-stu-id="4b3c0-120">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="4b3c0-121">将**音量调高和\*\*\*\*音量降低**按钮按住三秒钟将开始录制视频，而不是拍摄照片。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-121">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="4b3c0-122">若要停止录制，请同时点击调 **高** 音量和 **降低** 音量按钮。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-122">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <a name="voice-commands-to-take-photos"></a><span data-ttu-id="4b3c0-123">用于拍摄照片的语音命令</span><span class="sxs-lookup"><span data-stu-id="4b3c0-123">Voice commands to take photos</span></span>

<span data-ttu-id="4b3c0-124">在 HoloLens 2 版本 2004 (及更高版本) ，说："拍摄照片"。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-124">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="4b3c0-125">在 HoloLens (第一代) 或 HoloLens 2 版本 1903 上，说："你好小娜，拍摄照片。"</span><span class="sxs-lookup"><span data-stu-id="4b3c0-125">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <a name="start-menu-to-take-photos"></a><span data-ttu-id="4b3c0-126">"开始"菜单以拍摄照片</span><span class="sxs-lookup"><span data-stu-id="4b3c0-126">Start menu to take photos</span></span>

<span data-ttu-id="4b3c0-127">使用"开始"手势转到"开始 **"** 菜单，然后选择 **相机** 图标。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-127">Use the Start gesture to go to **Start**, then select the **camera** icon.</span></span>

<span data-ttu-id="4b3c0-128">将头指向你想要捕获的方向，然后通过空敲 [击](hololens2-basic-usage.md#touch-holograms-near-you) 来拍摄照片。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-128">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="4b3c0-129">你可以继续空敲并捕获其他照片。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-129">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="4b3c0-130">你捕获的任何照片都将保存到你的设备。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-130">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="4b3c0-131">再次使用"开始"手势结束照片捕获。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-131">Use the Start gesture again to end photo capture.</span></span>  

## <a name="capture-a-mixed-reality-video"></a><span data-ttu-id="4b3c0-132">捕获混合现实视频</span><span class="sxs-lookup"><span data-stu-id="4b3c0-132">Capture a mixed reality video</span></span>

<span data-ttu-id="4b3c0-133">有几种方法在 HoloLens 上录制混合现实视频;可以使用硬件按钮、语音或"开始"菜单。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-133">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <a name="hardware-buttons-to-record-videos"></a><span data-ttu-id="4b3c0-134">用于录制视频的硬件按钮</span><span class="sxs-lookup"><span data-stu-id="4b3c0-134">Hardware buttons to record videos</span></span>

<span data-ttu-id="4b3c0-135">录制视频的最快方法就是同时按住音量增加和音量降低按钮\*\*\*\*，直到开始\*\*\*\* 倒计时 3 秒。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-135">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="4b3c0-136">若要停止录制，请同时点击这两个按钮。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-136">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="4b3c0-137">同时快速**按调高**音量\*\*\*\* 和调低音量按钮将拍摄照片，而不是录制视频。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-137">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <a name="voice-to-record-videos"></a><span data-ttu-id="4b3c0-138">录制视频的语音</span><span class="sxs-lookup"><span data-stu-id="4b3c0-138">Voice to record videos</span></span>

<span data-ttu-id="4b3c0-139">在 HoloLens 2 版本 2004 (及更高版本) ，说："开始录制"。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-139">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="4b3c0-140">若要停止录制，请说出"停止录制"。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-140">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="4b3c0-141">在 HoloLens (第一代) 或 HoloLens 2 版本 1903 上，说："你好小娜，开始录制。"</span><span class="sxs-lookup"><span data-stu-id="4b3c0-141">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="4b3c0-142">若要停止录制，请说出"你好小娜，停止录制"。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-142">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <a name="start-menu-to-record-videos"></a><span data-ttu-id="4b3c0-143">"开始"菜单录制视频</span><span class="sxs-lookup"><span data-stu-id="4b3c0-143">Start menu to record videos</span></span>

<span data-ttu-id="4b3c0-144">使用"开始"手势转到"开始 **"，** 然后选择 **视频** 图标。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-144">Use the Start gesture to go to **Start**, then select the **video** icon.</span></span> <span data-ttu-id="4b3c0-145">将头指向要捕获的方向，然后通过空击 [开始](hololens2-basic-usage.md#touch-holograms-near-you) 录制。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-145">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="4b3c0-146">有三秒钟的倒计时，你的录制将开始。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-146">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="4b3c0-147">若要停止录制，请使用"开始"手势并选择突出显示 **的视频** 图标。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-147">To stop recording, use the Start gesture and select the highlighted **video** icon.</span></span> <span data-ttu-id="4b3c0-148">视频将保存到设备。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-148">The video will be saved to your device.</span></span>

> [!NOTE]
> **<span data-ttu-id="4b3c0-149">仅适用于 HoloLens (第一代) 应用</span><span class="sxs-lookup"><span data-stu-id="4b3c0-149">Applies to HoloLens (1st gen) only</span></span>**  
> <span data-ttu-id="4b3c0-150">Windows [10 2018 年 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) 月更新更改了"开始"手势和 Windows 按钮在 HoloLens 第一代 (上的行为) 。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-150">The [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="4b3c0-151">在更新之前，"开始"手势或 Windows 按钮将停止视频录制。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-151">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="4b3c0-152">但是，更新后，如果你使用沉浸式应用) ，"开始"手势或 Windows\*\*\*\* 按钮将打开"开始"菜单 (或快速操作菜单，你可以从其中选择突出显示的视频图标来\*\*\*\* 停止录制。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4b3c0-152">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <a name="share-what-you-see-in-real-time"></a><span data-ttu-id="4b3c0-153">实时共享你所看到的信息</span><span class="sxs-lookup"><span data-stu-id="4b3c0-153">Share what you see in real-time</span></span>

<span data-ttu-id="4b3c0-154">你可以与好友和同事实时共享你在 HoloLens 中看见的。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-154">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="4b3c0-155">有一些方法可用：</span><span class="sxs-lookup"><span data-stu-id="4b3c0-155">There are a few methods available:</span></span>

1. <span data-ttu-id="4b3c0-156">连接到支持 Miracast 的设备或适配器以观看电视。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-156">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="4b3c0-157">使用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 在电脑上观看</span><span class="sxs-lookup"><span data-stu-id="4b3c0-157">Using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="4b3c0-158">使用 [Microsoft HoloLens 配套应用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 在电脑上观看。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-158">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="4b3c0-159">部署 [Microsoft Dynamics 365 远程协助](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 应用，使第一线工作人员能够将看到内容流式传输给远程专家。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-159">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="4b3c0-160">然后，远程专家可以口头指导一线工作人员，或者通过注释他们的世界来指导他们。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-160">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="4b3c0-161">通过 Windows Device Portal 或 Microsoft HoloLens 配套应用共享你看到的内容需要 HoloLens 进入开发人员 [模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-161">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <a name="stream-video-with-miracast"></a><span data-ttu-id="4b3c0-162">使用 Miracast 流视频</span><span class="sxs-lookup"><span data-stu-id="4b3c0-162">Stream video with Miracast</span></span>

<span data-ttu-id="4b3c0-163">使用"开始"手势转到"开始 **"，** 然后选择 **连接** 图标。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-163">Use the Start gesture to go to **Start**, then select the **connect** icon.</span></span> <span data-ttu-id="4b3c0-164">从出现的选取器中，选择要连接到的启用了 Miracast 的设备或适配器。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-164">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="4b3c0-165">若要停止共享，请使用"开始"手势并选择突出显示的 **"连接"** 图标。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-165">To stop sharing, use the Start gesture and select the highlighted **connect** icon.</span></span> <span data-ttu-id="4b3c0-166">因为你是流式处理，所以不会将任何内容保存到你的设备。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-166">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="4b3c0-167">Miracast 支持从 [Windows 10 2018 年 10](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)月更新 (第一代) HoloLens 上启用。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-167">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).</span></span>

### <a name="real-time-video-with-windows-device-portal"></a><span data-ttu-id="4b3c0-168">Windows Device Portal 实时视频</span><span class="sxs-lookup"><span data-stu-id="4b3c0-168">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="4b3c0-169">由于通过 Windows Device Portal 进行共享需要在 HoloLens 上启用开发人员模式，请按照开发人员文档中的说明设置开发人员模式并导航 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-169">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <a name="microsoft-hololens-companion-app"></a><span data-ttu-id="4b3c0-170">Microsoft HoloLens 配套应用</span><span class="sxs-lookup"><span data-stu-id="4b3c0-170">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="4b3c0-171">由于通过 Microsoft HoloLens 配套应用共享需要在 HoloLens 上启用开发人员模式，请按照我们的开发人员文档中的说明设置 [开发人员模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-171">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="4b3c0-172">然后，下载 [Microsoft HoloLens](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 配套应用，并按照应用内的说明连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-172">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="4b3c0-173">使用 HoloLens 设置应用后，从应用的主菜单中\*\*\*\* 选择"实时流"选项。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-173">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <a name="view-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="4b3c0-174">查看混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="4b3c0-174">View your mixed reality photos and videos</span></span>

<span data-ttu-id="4b3c0-175">混合现实照片和视频将保存到设备的"相机照片"中。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-175">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="4b3c0-176">可以使用"文件资源管理器"应用浏览 HoloLens 上此文件夹的内容， ("图片">"相机) 。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-176">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to Pictures > Camera Roll).</span></span>

<span data-ttu-id="4b3c0-177">还可以在预安装在 HoloLens 上的照片应用中查看混合现实照片和视频。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-177">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="4b3c0-178">若要固定你的世界的照片，请在"照片"应用中选择它，然后选择"**在混合世界中放置"。**</span><span class="sxs-lookup"><span data-stu-id="4b3c0-178">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="4b3c0-179">放置照片后，你可以将其四处移动。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-179">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="4b3c0-180">若要在连接到 HoloLens 的电脑上查看和/或保存混合现实照片和视频，可以通过 MTP 使用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) 或电脑 [的文件资源管理器](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-180">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

### <a name="use-file-explorer-to-get-your-pictures-videos-and-files"></a><span data-ttu-id="4b3c0-181">使用文件资源管理器获取图片、视频和文件</span><span class="sxs-lookup"><span data-stu-id="4b3c0-181">Use File Explorer to get your pictures, videos and files</span></span>

<span data-ttu-id="4b3c0-182">与其他移动设备类似，将 HoloLens 连接到电脑以打开文件资源管理器以访问 HoloLens 库 (照片、视频、文档) 轻松转移。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-182">Similar to other mobile devices, connect your HoloLens to your PC to bring up File Explorer to access your HoloLens libraries (photos, videos, documents) for easy transfer.</span></span> <span data-ttu-id="4b3c0-183">此方法易于使用，不需要使用设备门户或 WI-Fi。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-183">This method is easy to use and does not require the use of device portal or Wi-Fi.</span></span>

1. <span data-ttu-id="4b3c0-184">解锁设备。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-184">Unlock the device.</span></span>
1. <span data-ttu-id="4b3c0-185">通过 USB 将设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-185">Connect the device to a PC via USB.</span></span>
1. <span data-ttu-id="4b3c0-186">文件资源管理器应在电脑上打开。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-186">File Explorer should open on your PC.</span></span>
1. <span data-ttu-id="4b3c0-187">导航到：此电脑\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span><span class="sxs-lookup"><span data-stu-id="4b3c0-187">Navigate to: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span></span>
1. <span data-ttu-id="4b3c0-188">将所需的任何文件复制到电脑。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-188">Copy whatever files you need to your PC.</span></span>

<span data-ttu-id="4b3c0-189">提示：</span><span class="sxs-lookup"><span data-stu-id="4b3c0-189">Tips:</span></span>
- <span data-ttu-id="4b3c0-190">如果你未看到任何文件，请确保登录到 HoloLens 以允许访问你的数据。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-190">If you don't see any files, please ensure you sign in to your HoloLens to enable access to your data.</span></span>
- <span data-ttu-id="4b3c0-191">你可以获取其他文件夹中的其他文件，例如 ["文档"文件夹中的](hololens-diagnostic-logs.md#offline-diagnostics) 诊断文件。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-191">You can get other files in other folders, such as [diagnostics files](hololens-diagnostic-logs.md#offline-diagnostics) from the Documents folder.</span></span>
- <span data-ttu-id="4b3c0-192">从电脑上的文件资源管理器中，可以选择设备属性以查看 Windows 全息操作系统版本号 (固件版本) 、设备序列号和电池百分比。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-192">From File Explorer on your PC, you can select Device properties to see Windows Holographic OS version number (firmware version), device serial number, and battery percentage.</span></span>
- <span data-ttu-id="4b3c0-193">如果组织已使用 MDM 禁用 [Connectivity/AllowUSBConnection，](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) 将无法连接到设备。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-193">If your Organization has used MDM to disable [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) then you will be unable to connect to your device.</span></span>

## <a name="share-your-mixed-reality-photos-and-videos"></a><span data-ttu-id="4b3c0-194">共享混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="4b3c0-194">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="4b3c0-195">捕获混合现实照片或视频后，将显示预览。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-195">After capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="4b3c0-196">选择 **预览** 上方的共享图标可显示共享助手。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-196">Select the **share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="4b3c0-197">从该位置，可以选择要共享该照片或视频的终点。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-197">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="4b3c0-198">通过自动上传混合现实照片和视频，还可以从 OneDrive 共享混合现实照片和视频。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-198">You can also share mixed reality photos and videos from OneDrive, by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="4b3c0-199">在 HoloLens 上打开 OneDrive 应用，然后使用 [个人 Microsoft](https://account.microsoft.com) 帐户登录（如果尚未登录）。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-199">Open the OneDrive app on HoloLens and sign in with a personal [Microsoft account](https://account.microsoft.com) if you haven't already.</span></span> <span data-ttu-id="4b3c0-200">选择设置**图标**，然后选择"相机**上传"。**</span><span class="sxs-lookup"><span data-stu-id="4b3c0-200">Select the **settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="4b3c0-201">打开"相机上载"。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-201">Turn Camera upload on.</span></span> <span data-ttu-id="4b3c0-202">每次在 HoloLens 上启动应用时，混合现实照片和视频现在都会上传到 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-202">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="4b3c0-203">只有在使用个人 Microsoft 帐户登录 OneDrive 时，才能在 OneDrive 中启用相机上传。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-203">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="4b3c0-204">如果使用工作或学校帐户设置 HoloLens，可以在 OneDrive 应用中添加个人 Microsoft 帐户以启用此功能。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-204">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <a name="limitations-of-mixed-reality-capture"></a><span data-ttu-id="4b3c0-205">混合现实捕获的限制</span><span class="sxs-lookup"><span data-stu-id="4b3c0-205">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="4b3c0-206">使用混合现实捕获时，HoloLens 的帧速率将放大到 30 Hz。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-206">While using mixed reality capture, the framerate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="4b3c0-207">如果照片/视频相机已被另一个应用程序使用、实时流式传输或系统资源不足，则照片和视频的分辨率可能会降低。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-207">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

### <a name="maximum-recording-length"></a><span data-ttu-id="4b3c0-208">最大录音长度</span><span class="sxs-lookup"><span data-stu-id="4b3c0-208">Maximum recording length</span></span>

<span data-ttu-id="4b3c0-209">在 HoloLens 2 设备上，在 Windows 全息版之前，设备上录制的 20H2 版本视频的最大长度限制为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-209">On HoloLens 2 devices before the Windows Holographic, version 20H2 videos recorded on the device were limited to maximum length of five minutes.</span></span>

<span data-ttu-id="4b3c0-210">由于客户反馈，我们增加了混合现实捕获 [的录制长度](holographic-photos-and-videos.md)。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-210">Due to customer feedback we’ve increased the recording length of [mixed reality captures](holographic-photos-and-videos.md).</span></span> <span data-ttu-id="4b3c0-211">默认情况下，混合现实捕获将不再限制为 5 分钟，而是将基于可用磁盘空间计算最大录制长度。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-211">Mixed reality captures will no longer be limited to 5 minutes by default but instead will calculate the maximum recording length based on available disk space.</span></span> <span data-ttu-id="4b3c0-212">设备将基于可用磁盘空间估计最大视频录制持续时间，最多占总磁盘空间的 80%。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-212">The device will estimate the max video recording duration based on available disk space up to 80% of the total disk space.</span></span>

> [!NOTE]
> <span data-ttu-id="4b3c0-213">如果发生以下情况之一，HoloLens 将使用默认 (5 分钟) 5 分钟：</span><span class="sxs-lookup"><span data-stu-id="4b3c0-213">The HoloLens will use default video recording length (5 minutes) if one of the following occurs:</span></span>
> - <span data-ttu-id="4b3c0-214">估计的最大录音持续时间小于默认的 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-214">The estimated max recording duration is smaller than the default 5 mins.</span></span>
> - <span data-ttu-id="4b3c0-215">可用磁盘空间小于总磁盘空间的 20%。</span><span class="sxs-lookup"><span data-stu-id="4b3c0-215">The available disk space is less than 20% of the total disk space.</span></span>

## <a name="default-file-format-and-resolution"></a><span data-ttu-id="4b3c0-216">默认文件格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="4b3c0-216">Default file format and resolution</span></span>

### <a name="default-photo-format-and-resolution"></a><span data-ttu-id="4b3c0-217">默认的照片格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="4b3c0-217">Default photo format and resolution</span></span>

|  <span data-ttu-id="4b3c0-218">设备</span><span class="sxs-lookup"><span data-stu-id="4b3c0-218">Device</span></span>  |  <span data-ttu-id="4b3c0-219">格式</span><span class="sxs-lookup"><span data-stu-id="4b3c0-219">Format</span></span>  |  <span data-ttu-id="4b3c0-220">扩展</span><span class="sxs-lookup"><span data-stu-id="4b3c0-220">Extension</span></span>  |  <span data-ttu-id="4b3c0-221">解决方案</span><span class="sxs-lookup"><span data-stu-id="4b3c0-221">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="4b3c0-222">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="4b3c0-222">HoloLens 2</span></span> | [<span data-ttu-id="4b3c0-223">JPEG</span><span class="sxs-lookup"><span data-stu-id="4b3c0-223">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="4b3c0-224">.jpg</span><span class="sxs-lookup"><span data-stu-id="4b3c0-224">.jpg</span></span> | <span data-ttu-id="4b3c0-225">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="4b3c0-225">3904x2196px</span></span> |
| <span data-ttu-id="4b3c0-226">HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="4b3c0-226">HoloLens (1st gen)</span></span> | [<span data-ttu-id="4b3c0-227">JPEG</span><span class="sxs-lookup"><span data-stu-id="4b3c0-227">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="4b3c0-228">.jpg</span><span class="sxs-lookup"><span data-stu-id="4b3c0-228">.jpg</span></span> | <span data-ttu-id="4b3c0-229">1408x792px</span><span class="sxs-lookup"><span data-stu-id="4b3c0-229">1408x792px</span></span> |

### <a name="recorded-video-format-and-resolution"></a><span data-ttu-id="4b3c0-230">录制的视频格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="4b3c0-230">Recorded video format and resolution</span></span>

| <span data-ttu-id="4b3c0-231">设备</span><span class="sxs-lookup"><span data-stu-id="4b3c0-231">Device</span></span> | <span data-ttu-id="4b3c0-232">格式</span><span class="sxs-lookup"><span data-stu-id="4b3c0-232">Format</span></span> | <span data-ttu-id="4b3c0-233">扩展</span><span class="sxs-lookup"><span data-stu-id="4b3c0-233">Extension</span></span> | <span data-ttu-id="4b3c0-234">解决方案</span><span class="sxs-lookup"><span data-stu-id="4b3c0-234">Resolution</span></span> | <span data-ttu-id="4b3c0-235">速度</span><span class="sxs-lookup"><span data-stu-id="4b3c0-235">Speed</span></span> | <span data-ttu-id="4b3c0-236">音频</span><span class="sxs-lookup"><span data-stu-id="4b3c0-236">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="4b3c0-237">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="4b3c0-237">HoloLens 2</span></span> | [<span data-ttu-id="4b3c0-238">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="4b3c0-238">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="4b3c0-239">.mp4</span><span class="sxs-lookup"><span data-stu-id="4b3c0-239">.mp4</span></span> | <span data-ttu-id="4b3c0-240">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="4b3c0-240">1920x1080px</span></span> | <span data-ttu-id="4b3c0-241">30fps</span><span class="sxs-lookup"><span data-stu-id="4b3c0-241">30fps</span></span> | <span data-ttu-id="4b3c0-242">48kHz 立体声</span><span class="sxs-lookup"><span data-stu-id="4b3c0-242">48kHz Stereo</span></span> |
| <span data-ttu-id="4b3c0-243">HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="4b3c0-243">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="4b3c0-244">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="4b3c0-244">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="4b3c0-245">.mp4</span><span class="sxs-lookup"><span data-stu-id="4b3c0-245">.mp4</span></span> | <span data-ttu-id="4b3c0-246">1216x684px</span><span class="sxs-lookup"><span data-stu-id="4b3c0-246">1216x684px</span></span> | <span data-ttu-id="4b3c0-247">24fps</span><span class="sxs-lookup"><span data-stu-id="4b3c0-247">24fps</span></span> | <span data-ttu-id="4b3c0-248">48kHz 立体声</span><span class="sxs-lookup"><span data-stu-id="4b3c0-248">48kHz Stereo</span></span> |
