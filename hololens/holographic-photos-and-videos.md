---
title: 捕获和管理混合现实照片和视频
description: 了解如何使用 HoloLens 捕获、查看和共享混合现实照片和视频。
keywords: hololens、照片、视频、捕获、mrc、混合现实捕获、照片、相机、流、livestream、演示
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
ms.openlocfilehash: df67fe8c5b29eea317a0d00a1ebdcf7331fb0936
ms.sourcegitcommit: 681e8e03e1a0250368f1f50cef6fbc3c99bac3af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2020
ms.locfileid: "11165004"
---
# <span data-ttu-id="7640f-104">创建混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="7640f-104">Create mixed reality photos and videos</span></span>

<span data-ttu-id="7640f-105">HoloLens 为用户提供了与数字世界混合现实的体验。</span><span class="sxs-lookup"><span data-stu-id="7640f-105">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="7640f-106">混合现实捕获 (MRC) 使你可以将该体验捕获为照片或视频，或与其他人实时共享你所看到的内容。</span><span class="sxs-lookup"><span data-stu-id="7640f-106">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="7640f-107">混合现实捕获使用第一人的观点，以便其他人可以看到您看到的全息影像。</span><span class="sxs-lookup"><span data-stu-id="7640f-107">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="7640f-108">对于第三人的观点，请使用 [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。</span><span class="sxs-lookup"><span data-stu-id="7640f-108">For a third-person point of view, use [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="7640f-109">Spectator 视图对演示尤其有用。</span><span class="sxs-lookup"><span data-stu-id="7640f-109">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="7640f-110">虽然在朋友和同事之间共享视频很有趣，但视频还有助于教授其他人使用应用或与应用和体验相关的问题。</span><span class="sxs-lookup"><span data-stu-id="7640f-110">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="7640f-111">如果无法启动混合现实捕获体验，并且你的 HoloLens 是工作设备，请与你的系统管理员联系。</span><span class="sxs-lookup"><span data-stu-id="7640f-111">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="7640f-112">可通过公司政策限制对相机的访问。</span><span class="sxs-lookup"><span data-stu-id="7640f-112">Access to the camera can be restricted through company policy.</span></span>

## <span data-ttu-id="7640f-113">捕获混合现实照片</span><span class="sxs-lookup"><span data-stu-id="7640f-113">Capture a mixed reality photo</span></span>

<span data-ttu-id="7640f-114">有多种方法可以在 HoloLens 上拍摄照片混合现实;你可以使用硬件按钮、语音或 "开始" 菜单。</span><span class="sxs-lookup"><span data-stu-id="7640f-114">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="7640f-115">拍摄照片的硬件按钮</span><span class="sxs-lookup"><span data-stu-id="7640f-115">Hardware buttons to take photos</span></span>

<span data-ttu-id="7640f-116">若要拍摄当前视图的快速照片，请同时按下 "音量" 和 "音量" 按钮。</span><span class="sxs-lookup"><span data-stu-id="7640f-116">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="7640f-117">这有点类似于版本屏幕截图或打印屏幕的 HoloLens 版本。</span><span class="sxs-lookup"><span data-stu-id="7640f-117">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="7640f-118">HoloLens 2 上的按钮位置</span><span class="sxs-lookup"><span data-stu-id="7640f-118">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="7640f-119">HoloLens 上的按钮位置 (第一代) </span><span class="sxs-lookup"><span data-stu-id="7640f-119">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="7640f-120">将**音量\*\*\*\*按下并按下音量**按钮三秒钟，将开始录制视频，而不是拍摄照片。</span><span class="sxs-lookup"><span data-stu-id="7640f-120">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="7640f-121">若要停止录制，请同时点击 "调 **高音量** " 和 "调 **低音量** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="7640f-121">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <span data-ttu-id="7640f-122">用于拍摄照片的语音命令</span><span class="sxs-lookup"><span data-stu-id="7640f-122">Voice commands to take photos</span></span>

<span data-ttu-id="7640f-123">在 HoloLens 2、版本 2004 (及更高版本) 中，说： "拍摄照片"。</span><span class="sxs-lookup"><span data-stu-id="7640f-123">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="7640f-124">在 HoloLens (第一代) 或 HoloLens 2 版本1903，例如： "你好小娜，请拍摄照片"。</span><span class="sxs-lookup"><span data-stu-id="7640f-124">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <span data-ttu-id="7640f-125">"开始" 菜单，拍照</span><span class="sxs-lookup"><span data-stu-id="7640f-125">Start menu to take photos</span></span>

<span data-ttu-id="7640f-126">使用 "开始" 手势转到 " **开始**"，然后选择 **照相机** 图标。</span><span class="sxs-lookup"><span data-stu-id="7640f-126">Use the Start gesture to go to **Start**, then select the **camera** icon.</span></span>

<span data-ttu-id="7640f-127">将你的头指向你想要捕获的内容，然后 [点击](hololens2-basic-usage.md#touch-holograms-near-you) "拍摄照片"。</span><span class="sxs-lookup"><span data-stu-id="7640f-127">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="7640f-128">您可以继续空中点击并捕获其他照片。</span><span class="sxs-lookup"><span data-stu-id="7640f-128">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="7640f-129">你捕获的所有照片将保存到你的设备。</span><span class="sxs-lookup"><span data-stu-id="7640f-129">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="7640f-130">再次使用 "开始" 手势来结束照片捕获。</span><span class="sxs-lookup"><span data-stu-id="7640f-130">Use the Start gesture again to end photo capture.</span></span>  

## <span data-ttu-id="7640f-131">捕获混合现实视频</span><span class="sxs-lookup"><span data-stu-id="7640f-131">Capture a mixed reality video</span></span>

<span data-ttu-id="7640f-132">有多种方法可在 HoloLens 上录制混合现实的视频;你可以使用硬件按钮、语音或 "开始" 菜单。</span><span class="sxs-lookup"><span data-stu-id="7640f-132">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="7640f-133">用于录制视频的硬件按钮</span><span class="sxs-lookup"><span data-stu-id="7640f-133">Hardware buttons to record videos</span></span>

<span data-ttu-id="7640f-134">录制视频最快的方法是同时按住 **音量** 和调 **低** 音量按钮，直到出现三秒钟倒计时。</span><span class="sxs-lookup"><span data-stu-id="7640f-134">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="7640f-135">若要停止录制，请同时点击两个按钮。</span><span class="sxs-lookup"><span data-stu-id="7640f-135">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="7640f-136">同时快速按 **音量** 和 **按下音量** 按钮将拍摄照片，而不是录制视频。</span><span class="sxs-lookup"><span data-stu-id="7640f-136">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <span data-ttu-id="7640f-137">录制视频的语音</span><span class="sxs-lookup"><span data-stu-id="7640f-137">Voice to record videos</span></span>

<span data-ttu-id="7640f-138">在 HoloLens 2、版本 2004 (和更高版本) ，说： "开始录制"。</span><span class="sxs-lookup"><span data-stu-id="7640f-138">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="7640f-139">若要停止录制，请说 "停止录制"。</span><span class="sxs-lookup"><span data-stu-id="7640f-139">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="7640f-140">在 HoloLens (第一代) 或 HoloLens 2 版本1903，例如： "你好小娜，开始录制。"</span><span class="sxs-lookup"><span data-stu-id="7640f-140">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="7640f-141">若要停止录制，请说 "你好小娜，停止录制"。</span><span class="sxs-lookup"><span data-stu-id="7640f-141">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <span data-ttu-id="7640f-142">用于录制视频的 "开始" 菜单</span><span class="sxs-lookup"><span data-stu-id="7640f-142">Start menu to record videos</span></span>

<span data-ttu-id="7640f-143">使用 "开始" 手势转到 " **开始**"，然后选择 " **视频** " 图标。</span><span class="sxs-lookup"><span data-stu-id="7640f-143">Use the Start gesture to go to **Start**, then select the **video** icon.</span></span> <span data-ttu-id="7640f-144">将你的头指向你想要捕获的内容，然后 [点击](hololens2-basic-usage.md#touch-holograms-near-you) "开始录制"。</span><span class="sxs-lookup"><span data-stu-id="7640f-144">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="7640f-145">将出现三次倒计时，录制将开始。</span><span class="sxs-lookup"><span data-stu-id="7640f-145">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="7640f-146">若要停止录制，请使用 "开始" 手势并选择突出显示的 **视频** 图标。</span><span class="sxs-lookup"><span data-stu-id="7640f-146">To stop recording, use the Start gesture and select the highlighted **video** icon.</span></span> <span data-ttu-id="7640f-147">视频将保存到您的设备。</span><span class="sxs-lookup"><span data-stu-id="7640f-147">The video will be saved to your device.</span></span>

> [!NOTE]
> **<span data-ttu-id="7640f-148">仅适用于 HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="7640f-148">Applies to HoloLens (1st gen) only</span></span>**  
> <span data-ttu-id="7640f-149">[Windows 10 月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)将更改 "开始手势" 和 "Windows" 按钮在 HoloLens (第一代) 上的行为。</span><span class="sxs-lookup"><span data-stu-id="7640f-149">The [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="7640f-150">更新之前，"开始手势" 或 "Windows" 按钮将停止视频录制。</span><span class="sxs-lookup"><span data-stu-id="7640f-150">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="7640f-151">但是，更新后，"开始" 手势或 Windows 按钮将打开 " **开始** " 菜单 (或 " **快速操作" 菜单** （如果你位于沉浸式应用) 中），可从中选择突出显示的 **视频** 图标以停止录制。</span><span class="sxs-lookup"><span data-stu-id="7640f-151">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <span data-ttu-id="7640f-152">共享您实时看到的内容</span><span class="sxs-lookup"><span data-stu-id="7640f-152">Share what you see in real-time</span></span>

<span data-ttu-id="7640f-153">您可以实时与朋友和同事共享您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="7640f-153">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="7640f-154">可以使用以下几种方法：</span><span class="sxs-lookup"><span data-stu-id="7640f-154">There are a few methods available:</span></span>

1. <span data-ttu-id="7640f-155">连接到支持 Miracast 的设备或适配器以在电视上观看。</span><span class="sxs-lookup"><span data-stu-id="7640f-155">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="7640f-156">使用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 在电脑上观看</span><span class="sxs-lookup"><span data-stu-id="7640f-156">Using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="7640f-157">使用 [Microsoft HoloLens 配套应用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) 在电脑上观看。</span><span class="sxs-lookup"><span data-stu-id="7640f-157">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="7640f-158">部署 [Microsoft Dynamics 365 远程协助](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) 应用，该应用使前端工作人员能够流式处理他们对远程专家所看到的内容。</span><span class="sxs-lookup"><span data-stu-id="7640f-158">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="7640f-159">然后，远程专家可以通过自己的口头或在世界上进行批注来指导他们。</span><span class="sxs-lookup"><span data-stu-id="7640f-159">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="7640f-160">通过 Windows Device Portal 或 Microsoft HoloLens 附属应用共享所看到的内容要求你的 HoloLens 处于 [开发人员模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="7640f-160">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <span data-ttu-id="7640f-161">通过 Miracast 流处理视频</span><span class="sxs-lookup"><span data-stu-id="7640f-161">Stream video with Miracast</span></span>

<span data-ttu-id="7640f-162">使用 "开始" 手势转到 " **开始**"，然后选择 " **连接** " 图标。</span><span class="sxs-lookup"><span data-stu-id="7640f-162">Use the Start gesture to go to **Start**, then select the **connect** icon.</span></span> <span data-ttu-id="7640f-163">从出现的选取器中，选择要连接到的已启用 Miracast 的设备或适配器。</span><span class="sxs-lookup"><span data-stu-id="7640f-163">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="7640f-164">若要停止共享，请使用 "开始" 手势并选择突出显示的 " **连接** " 图标。</span><span class="sxs-lookup"><span data-stu-id="7640f-164">To stop sharing, use the Start gesture and select the highlighted **connect** icon.</span></span> <span data-ttu-id="7640f-165">由于你正在进行流式处理，因此不会将任何内容保存到你的设备。</span><span class="sxs-lookup"><span data-stu-id="7640f-165">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="7640f-166">在 HoloLens (第一代) 上启用了 Miracast 支持，从 [2018 年10月的更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)开始。</span><span class="sxs-lookup"><span data-stu-id="7640f-166">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).</span></span>

### <span data-ttu-id="7640f-167">Windows Device Portal 的实时视频</span><span class="sxs-lookup"><span data-stu-id="7640f-167">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="7640f-168">由于通过 Windows Device Portal 进行共享需要在 HoloLens 上启用开发人员模式，请按照我们的开发人员文档中的说明 [设置开发人员模式和导航 Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="7640f-168">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <span data-ttu-id="7640f-169">Microsoft HoloLens 辅助应用</span><span class="sxs-lookup"><span data-stu-id="7640f-169">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="7640f-170">由于通过 Microsoft HoloLens 附属应用共享需要在 HoloLens 上启用开发人员模式，请按照我们的开发人员文档中的说明 [设置开发人员模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="7640f-170">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="7640f-171">然后，下载 [Microsoft HoloLens 配套应用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) ，并按照应用中的说明连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="7640f-171">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="7640f-172">将应用与 HoloLens 一起设置后，从应用的主菜单中选择 " **实时流** " 选项。</span><span class="sxs-lookup"><span data-stu-id="7640f-172">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <span data-ttu-id="7640f-173">查看混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="7640f-173">View your mixed reality photos and videos</span></span>

<span data-ttu-id="7640f-174">混合现实照片和视频将保存到设备的 "相机翻转"。</span><span class="sxs-lookup"><span data-stu-id="7640f-174">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="7640f-175">你可以通过文件资源管理器应用在你的 HoloLens 上浏览此文件夹的内容， (导航到 > 相机辊) 的图片。</span><span class="sxs-lookup"><span data-stu-id="7640f-175">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to Pictures > Camera Roll).</span></span>

<span data-ttu-id="7640f-176">你还可以在预装在 HoloLens 上的照片应用中查看混合现实照片和视频。</span><span class="sxs-lookup"><span data-stu-id="7640f-176">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="7640f-177">若要在世界上固定照片，请在 "照片" 应用中将其选中，然后选择 " **混合世界**"。</span><span class="sxs-lookup"><span data-stu-id="7640f-177">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="7640f-178">在放置后，您可以在世界各地移动照片。</span><span class="sxs-lookup"><span data-stu-id="7640f-178">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="7640f-179">若要在连接到 HoloLens 的电脑上查看和/或保存混合现实照片和视频，可以通过 MTP 使用 [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) 或 [电脑的文件资源管理器](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="7640f-179">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

### <span data-ttu-id="7640f-180">使用文件资源管理器获取图片、视频和文件</span><span class="sxs-lookup"><span data-stu-id="7640f-180">Use File Explorer to get your pictures, videos and files</span></span>

<span data-ttu-id="7640f-181">与其他移动设备类似，将你的 HoloLens 连接到电脑以调出文件资源管理器，以便访问你的 HoloLens 库 (照片、视频、文档) 以便轻松传输。</span><span class="sxs-lookup"><span data-stu-id="7640f-181">Similar to other mobile devices, connect your HoloLens to your PC to bring up File Explorer to access your HoloLens libraries (photos, videos, documents) for easy transfer.</span></span> <span data-ttu-id="7640f-182">此方法易于使用，并且不需要使用 device portal 或 Wi-fi。</span><span class="sxs-lookup"><span data-stu-id="7640f-182">This method is easy to use and does not require the use of device portal or Wi-Fi.</span></span>

1. <span data-ttu-id="7640f-183">解锁设备。</span><span class="sxs-lookup"><span data-stu-id="7640f-183">Unlock the device.</span></span>
1. <span data-ttu-id="7640f-184">通过 USB 将设备连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="7640f-184">Connect the device to a PC via USB.</span></span>
1. <span data-ttu-id="7640f-185">文件资源管理器应在你的电脑上打开。</span><span class="sxs-lookup"><span data-stu-id="7640f-185">File Explorer should open on your PC.</span></span>
1. <span data-ttu-id="7640f-186">导航到：此 PC\\*yourhololensname*\Internal Storage\Pictures\Camera 滚</span><span class="sxs-lookup"><span data-stu-id="7640f-186">Navigate to: This PC\\*yourhololensname*\Internal Storage\Pictures\Camera Roll</span></span>
1. <span data-ttu-id="7640f-187">将所需的任何文件复制到 PC。</span><span class="sxs-lookup"><span data-stu-id="7640f-187">Copy whatever files you need to your PC.</span></span>

<span data-ttu-id="7640f-188">提示：</span><span class="sxs-lookup"><span data-stu-id="7640f-188">Tips:</span></span>
- <span data-ttu-id="7640f-189">如果您看不到任何文件，请确保您登录到 HoloLens 以允许访问您的数据。</span><span class="sxs-lookup"><span data-stu-id="7640f-189">If you don't see any files, please ensure you sign in to your HoloLens to enable access to your data.</span></span>
- <span data-ttu-id="7640f-190">可以获取其他文件夹中的其他文件，例如 "文档" 文件夹中的 " [诊断" 文件](hololens-diagnostic-logs.md#offline-diagnostics) 。</span><span class="sxs-lookup"><span data-stu-id="7640f-190">You can get other files in other folders, such as [diagnostics files](hololens-diagnostic-logs.md#offline-diagnostics) from the Documents folder.</span></span>
- <span data-ttu-id="7640f-191">在电脑上的文件资源管理器中，你可以选择 "设备属性" 以查看 Windows 全息 OS 版本号 (固件版本) 、设备序列号和电池百分比。</span><span class="sxs-lookup"><span data-stu-id="7640f-191">From File Explorer on your PC, you can select Device properties to see Windows Holographic OS version number (firmware version), device serial number, and battery percentage.</span></span>
- <span data-ttu-id="7640f-192">如果你的组织已使用 MDM 禁用 [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) ，你将无法连接到你的设备。</span><span class="sxs-lookup"><span data-stu-id="7640f-192">If your Organization has used MDM to disable [Connectivity/AllowUSBConnection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity#connectivity-allowusbconnection) then you will be unable to connect to your device.</span></span>

## <span data-ttu-id="7640f-193">分享您的混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="7640f-193">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="7640f-194">捕获混合现实照片或视频后，将显示预览。</span><span class="sxs-lookup"><span data-stu-id="7640f-194">After capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="7640f-195">选择预览上方的 " **共享** " 图标以调出 "共享助理"。</span><span class="sxs-lookup"><span data-stu-id="7640f-195">Select the **share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="7640f-196">在此处，你可以选择要在其中共享照片或视频的终结点。</span><span class="sxs-lookup"><span data-stu-id="7640f-196">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="7640f-197">您也可以通过自动上载您的混合现实照片和视频，从 OneDrive 共享混合现实照片和视频。</span><span class="sxs-lookup"><span data-stu-id="7640f-197">You can also share mixed reality photos and videos from OneDrive, by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="7640f-198">在 HoloLens 上打开 OneDrive 应用，并使用个人 [Microsoft 帐户](https://account.microsoft.com) 登录（如果尚未登录）。</span><span class="sxs-lookup"><span data-stu-id="7640f-198">Open the OneDrive app on HoloLens and sign in with a personal [Microsoft account](https://account.microsoft.com) if you haven't already.</span></span> <span data-ttu-id="7640f-199">选择 " **设置** " 图标，然后选择 " **照相机上载**"。</span><span class="sxs-lookup"><span data-stu-id="7640f-199">Select the **settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="7640f-200">打开相机上传。</span><span class="sxs-lookup"><span data-stu-id="7640f-200">Turn Camera upload on.</span></span> <span data-ttu-id="7640f-201">现在，你的混合现实照片和视频将在 HoloLens 上启动应用时上载到 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="7640f-201">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="7640f-202">如果你已使用个人 Microsoft 帐户登录到 OneDrive，则只能在 OneDrive 中启用相机上传。</span><span class="sxs-lookup"><span data-stu-id="7640f-202">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="7640f-203">如果您使用工作或学校帐户设置 HoloLens，则可以在 OneDrive 应用中添加个人 Microsoft 帐户以启用此功能。</span><span class="sxs-lookup"><span data-stu-id="7640f-203">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <span data-ttu-id="7640f-204">混合现实捕获的限制</span><span class="sxs-lookup"><span data-stu-id="7640f-204">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="7640f-205">使用混合现实捕获时，HoloLens 的帧频将减半到 30 Hz。</span><span class="sxs-lookup"><span data-stu-id="7640f-205">While using mixed reality capture, the framerate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="7640f-206">如果照片/视频相机已由另一个应用程序、实时流处理或系统资源不足，可能会降低照片和视频的分辨率。</span><span class="sxs-lookup"><span data-stu-id="7640f-206">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

### <span data-ttu-id="7640f-207">最大录制长度</span><span class="sxs-lookup"><span data-stu-id="7640f-207">Maximum recording length</span></span>

<span data-ttu-id="7640f-208">在 Windows 全息版上录制的版本20H2 视频之前，在设备上录制的版本视频的最大长度限制为5分钟。</span><span class="sxs-lookup"><span data-stu-id="7640f-208">On HoloLens 2 devices before the Windows Holographic, version 20H2 videos recorded on the device were limited to maximum length of five minutes.</span></span>

<span data-ttu-id="7640f-209">由于客户反馈，我们增加了 [混合现实捕获](holographic-photos-and-videos.md)的录制长度。</span><span class="sxs-lookup"><span data-stu-id="7640f-209">Due to customer feedback we’ve increased the recording length of [mixed reality captures](holographic-photos-and-videos.md).</span></span> <span data-ttu-id="7640f-210">默认情况下，混合现实捕获将不再限制为5分钟，而是将根据可用磁盘空间计算最大录制长度。</span><span class="sxs-lookup"><span data-stu-id="7640f-210">Mixed reality captures will no longer be limited to 5 minutes by default but instead will calculate the maximum recording length based on available disk space.</span></span> <span data-ttu-id="7640f-211">设备将根据可用磁盘空间达到总磁盘空间的80%，估计最大视频录制持续时间。</span><span class="sxs-lookup"><span data-stu-id="7640f-211">The device will estimate the max video recording duration based on available disk space up to 80% of the total disk space.</span></span>

> [!NOTE]
> <span data-ttu-id="7640f-212">如果出现以下情况之一，则 HoloLens 将使用默认视频录制长度 (5 分钟) ：</span><span class="sxs-lookup"><span data-stu-id="7640f-212">The HoloLens will use default video recording length (5 minutes) if one of the following occurs:</span></span>
> - <span data-ttu-id="7640f-213">估计的最大录制持续时间小于默认的5分钟。</span><span class="sxs-lookup"><span data-stu-id="7640f-213">The estimated max recording duration is smaller than the default 5 mins.</span></span>
> - <span data-ttu-id="7640f-214">可用磁盘空间小于总磁盘空间的20%。</span><span class="sxs-lookup"><span data-stu-id="7640f-214">The available disk space is less than 20% of the total disk space.</span></span>

## <span data-ttu-id="7640f-215">默认文件格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="7640f-215">Default file format and resolution</span></span>

### <span data-ttu-id="7640f-216">默认照片格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="7640f-216">Default photo format and resolution</span></span>

|  <span data-ttu-id="7640f-217">设备</span><span class="sxs-lookup"><span data-stu-id="7640f-217">Device</span></span>  |  <span data-ttu-id="7640f-218">格式</span><span class="sxs-lookup"><span data-stu-id="7640f-218">Format</span></span>  |  <span data-ttu-id="7640f-219">扩展</span><span class="sxs-lookup"><span data-stu-id="7640f-219">Extension</span></span>  |  <span data-ttu-id="7640f-220">分辨率</span><span class="sxs-lookup"><span data-stu-id="7640f-220">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="7640f-221">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="7640f-221">HoloLens 2</span></span> | [<span data-ttu-id="7640f-222">JPEG</span><span class="sxs-lookup"><span data-stu-id="7640f-222">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="7640f-223">.jpg</span><span class="sxs-lookup"><span data-stu-id="7640f-223">.jpg</span></span> | <span data-ttu-id="7640f-224">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="7640f-224">3904x2196px</span></span> |
| <span data-ttu-id="7640f-225">HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="7640f-225">HoloLens (1st gen)</span></span> | [<span data-ttu-id="7640f-226">JPEG</span><span class="sxs-lookup"><span data-stu-id="7640f-226">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="7640f-227">.jpg</span><span class="sxs-lookup"><span data-stu-id="7640f-227">.jpg</span></span> | <span data-ttu-id="7640f-228">1408x792px</span><span class="sxs-lookup"><span data-stu-id="7640f-228">1408x792px</span></span> |

### <span data-ttu-id="7640f-229">录制的视频格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="7640f-229">Recorded video format and resolution</span></span>

| <span data-ttu-id="7640f-230">设备</span><span class="sxs-lookup"><span data-stu-id="7640f-230">Device</span></span> | <span data-ttu-id="7640f-231">格式</span><span class="sxs-lookup"><span data-stu-id="7640f-231">Format</span></span> | <span data-ttu-id="7640f-232">扩展</span><span class="sxs-lookup"><span data-stu-id="7640f-232">Extension</span></span> | <span data-ttu-id="7640f-233">分辨率</span><span class="sxs-lookup"><span data-stu-id="7640f-233">Resolution</span></span> | <span data-ttu-id="7640f-234">度</span><span class="sxs-lookup"><span data-stu-id="7640f-234">Speed</span></span> | <span data-ttu-id="7640f-235">音频</span><span class="sxs-lookup"><span data-stu-id="7640f-235">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="7640f-236">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="7640f-236">HoloLens 2</span></span> | [<span data-ttu-id="7640f-237">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="7640f-237">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="7640f-238">.mp4</span><span class="sxs-lookup"><span data-stu-id="7640f-238">.mp4</span></span> | <span data-ttu-id="7640f-239">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="7640f-239">1920x1080px</span></span> | <span data-ttu-id="7640f-240">30fps</span><span class="sxs-lookup"><span data-stu-id="7640f-240">30fps</span></span> | <span data-ttu-id="7640f-241">48kHz 立体声</span><span class="sxs-lookup"><span data-stu-id="7640f-241">48kHz Stereo</span></span> |
| <span data-ttu-id="7640f-242">HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="7640f-242">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="7640f-243">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="7640f-243">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="7640f-244">.mp4</span><span class="sxs-lookup"><span data-stu-id="7640f-244">.mp4</span></span> | <span data-ttu-id="7640f-245">1216x684px</span><span class="sxs-lookup"><span data-stu-id="7640f-245">1216x684px</span></span> | <span data-ttu-id="7640f-246">24fps</span><span class="sxs-lookup"><span data-stu-id="7640f-246">24fps</span></span> | <span data-ttu-id="7640f-247">48kHz 立体声</span><span class="sxs-lookup"><span data-stu-id="7640f-247">48kHz Stereo</span></span> |
