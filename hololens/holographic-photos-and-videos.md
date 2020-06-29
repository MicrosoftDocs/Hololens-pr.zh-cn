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
ms.openlocfilehash: 1be4e80c040d5b8e451c07fb931c7c7fb8d5ab48
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827936"
---
# <span data-ttu-id="ae367-104">创建混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="ae367-104">Create mixed reality photos and videos</span></span>

<span data-ttu-id="ae367-105">HoloLens 为用户提供了与数字世界混合现实的体验。</span><span class="sxs-lookup"><span data-stu-id="ae367-105">HoloLens gives users the experience of mixing the real world with the digital world.</span></span>  <span data-ttu-id="ae367-106">混合现实捕获（MRC）可让你以照片或视频的形式捕获该体验，或与其他人实时共享你所看到的内容。</span><span class="sxs-lookup"><span data-stu-id="ae367-106">Mixed reality capture (MRC) lets you capture that experience as a photo or video, or share what you see with others in real-time.</span></span>

<span data-ttu-id="ae367-107">混合现实捕获使用第一人的观点，以便其他人可以看到您看到的全息影像。</span><span class="sxs-lookup"><span data-stu-id="ae367-107">Mixed reality capture uses a first-person point of view so other people can see holograms as you see them.</span></span> <span data-ttu-id="ae367-108">对于第三人的观点，请使用[spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view)。</span><span class="sxs-lookup"><span data-stu-id="ae367-108">For a third-person point of view, use [spectator view](https://docs.microsoft.com/windows/mixed-reality/spectator-view).</span></span> <span data-ttu-id="ae367-109">Spectator 视图对演示尤其有用。</span><span class="sxs-lookup"><span data-stu-id="ae367-109">Spectator view is especially useful for demos.</span></span>

<span data-ttu-id="ae367-110">虽然在朋友和同事之间共享视频很有趣，但视频还有助于教授其他人使用应用或与应用和体验相关的问题。</span><span class="sxs-lookup"><span data-stu-id="ae367-110">While it's fun to share videos amongst friends and colleagues, videos can also help teach other people to use an app or to communicate problems with apps and experiences.</span></span>

> [!NOTE]
> <span data-ttu-id="ae367-111">如果无法启动混合现实捕获体验，并且你的 HoloLens 是工作设备，请与你的系统管理员联系。</span><span class="sxs-lookup"><span data-stu-id="ae367-111">If you can't launch mixed reality capture experiences and your HoloLens is a work device, check with your system administrator.</span></span> <span data-ttu-id="ae367-112">可通过公司政策限制对相机的访问。</span><span class="sxs-lookup"><span data-stu-id="ae367-112">Access to the camera can be restricted through company policy.</span></span>

## <span data-ttu-id="ae367-113">捕获混合现实照片</span><span class="sxs-lookup"><span data-stu-id="ae367-113">Capture a mixed reality photo</span></span>

<span data-ttu-id="ae367-114">有多种方法可以在 HoloLens 上拍摄照片混合现实;你可以使用硬件按钮、语音或 "开始" 菜单。</span><span class="sxs-lookup"><span data-stu-id="ae367-114">There are several ways to take a photo of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="ae367-115">拍摄照片的硬件按钮</span><span class="sxs-lookup"><span data-stu-id="ae367-115">Hardware buttons to take photos</span></span>

<span data-ttu-id="ae367-116">若要拍摄当前视图的快速照片，请同时按下 "音量" 和 "音量" 按钮。</span><span class="sxs-lookup"><span data-stu-id="ae367-116">To take a quick photo of your current view, press the volume up and volume down buttons at the same time.</span></span>  <span data-ttu-id="ae367-117">这有点类似于版本屏幕截图或打印屏幕的 HoloLens 版本。</span><span class="sxs-lookup"><span data-stu-id="ae367-117">This is a bit like the HoloLens version of a screenshot or print screen.</span></span>

- [<span data-ttu-id="ae367-118">HoloLens 2 上的按钮位置</span><span class="sxs-lookup"><span data-stu-id="ae367-118">Button locations on HoloLens 2</span></span>](hololens2-hardware.md)
- [<span data-ttu-id="ae367-119">HoloLens 上的按钮位置（第1代）</span><span class="sxs-lookup"><span data-stu-id="ae367-119">Button locations on HoloLens (1st gen)</span></span>](hololens1-hardware.md#hololens-components)

> [!NOTE]
> <span data-ttu-id="ae367-120">将**音量\*\*\*\*按下并按下音量**按钮三秒钟，将开始录制视频，而不是拍摄照片。</span><span class="sxs-lookup"><span data-stu-id="ae367-120">Holding the **volume up** and **volume down** buttons for three seconds will start recording a video rather than taking a photo.</span></span> <span data-ttu-id="ae367-121">若要停止录制，请同时点击 "调**高音量**" 和 "调**低音量**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="ae367-121">To stop recording, tap both **volume up** and **volume down** buttons simultaneously.</span></span>

### <span data-ttu-id="ae367-122">用于拍摄照片的语音命令</span><span class="sxs-lookup"><span data-stu-id="ae367-122">Voice commands to take photos</span></span>

<span data-ttu-id="ae367-123">在 HoloLens 2 （版本2004（及更高版本）上，说： "拍摄照片"。</span><span class="sxs-lookup"><span data-stu-id="ae367-123">On HoloLens 2, version 2004 (and later), say: "Take a picture."</span></span>

<span data-ttu-id="ae367-124">在 HoloLens （第1代）或 HoloLens 2 版本1903上，说： "你好小娜，拍一张照片。"</span><span class="sxs-lookup"><span data-stu-id="ae367-124">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, take a picture."</span></span>

### <span data-ttu-id="ae367-125">"开始" 菜单，拍照</span><span class="sxs-lookup"><span data-stu-id="ae367-125">Start menu to take photos</span></span>

<span data-ttu-id="ae367-126">使用 "开始" 手势转到 "**开始**"，然后选择**照相机**图标。</span><span class="sxs-lookup"><span data-stu-id="ae367-126">Use the Start gesture to go to **Start**, then select the **camera** icon.</span></span>

<span data-ttu-id="ae367-127">将你的头指向你想要捕获的内容，然后[点击](hololens2-basic-usage.md#touch-holograms-near-you)"拍摄照片"。</span><span class="sxs-lookup"><span data-stu-id="ae367-127">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to take a photo.</span></span> <span data-ttu-id="ae367-128">您可以继续空中点击并捕获其他照片。</span><span class="sxs-lookup"><span data-stu-id="ae367-128">You can continue to air tap and capture additional photos.</span></span> <span data-ttu-id="ae367-129">你捕获的所有照片将保存到你的设备。</span><span class="sxs-lookup"><span data-stu-id="ae367-129">Any photos you capture will be saved to your device.</span></span>

<span data-ttu-id="ae367-130">再次使用 "开始" 手势来结束照片捕获。</span><span class="sxs-lookup"><span data-stu-id="ae367-130">Use the Start gesture again to end photo capture.</span></span>  

## <span data-ttu-id="ae367-131">捕获混合现实视频</span><span class="sxs-lookup"><span data-stu-id="ae367-131">Capture a mixed reality video</span></span>

<span data-ttu-id="ae367-132">有多种方法可在 HoloLens 上录制混合现实的视频;你可以使用硬件按钮、语音或 "开始" 菜单。</span><span class="sxs-lookup"><span data-stu-id="ae367-132">There are several ways to record a video of mixed reality on HoloLens; you can use hardware buttons, voice, or the Start menu.</span></span>

### <span data-ttu-id="ae367-133">用于录制视频的硬件按钮</span><span class="sxs-lookup"><span data-stu-id="ae367-133">Hardware buttons to record videos</span></span>

<span data-ttu-id="ae367-134">录制视频最快的方法是同时按住**音量**和调**低**音量按钮，直到出现三秒钟倒计时。</span><span class="sxs-lookup"><span data-stu-id="ae367-134">The quickest way to record a video is to press and hold the **volume up** and **volume down** buttons simultaneously until a three-second countdown begins.</span></span> <span data-ttu-id="ae367-135">若要停止录制，请同时点击两个按钮。</span><span class="sxs-lookup"><span data-stu-id="ae367-135">To stop recording, tap both buttons simultaneously.</span></span>

> [!NOTE]
> <span data-ttu-id="ae367-136">同时快速按**音量**和**按下音量**按钮将拍摄照片，而不是录制视频。</span><span class="sxs-lookup"><span data-stu-id="ae367-136">Quickly pressing the **volume up** and **volume down** buttons at the same time will take a photo rather than recording a video.</span></span>

### <span data-ttu-id="ae367-137">录制视频的语音</span><span class="sxs-lookup"><span data-stu-id="ae367-137">Voice to record videos</span></span>

<span data-ttu-id="ae367-138">在 HoloLens 2 （版本2004（及更高版本）上，说： "开始录制"。</span><span class="sxs-lookup"><span data-stu-id="ae367-138">On HoloLens 2, version 2004 (and later), say: "Start recording."</span></span> <span data-ttu-id="ae367-139">若要停止录制，请说 "停止录制"。</span><span class="sxs-lookup"><span data-stu-id="ae367-139">To stop recording, say "Stop recording."</span></span>

<span data-ttu-id="ae367-140">在 HoloLens （第1代）或 HoloLens 2 （版本1903）上，说： "你好小娜，开始录制。"</span><span class="sxs-lookup"><span data-stu-id="ae367-140">On HoloLens (1st gen) or HoloLens 2, version 1903, say: "Hey Cortana, start recording."</span></span> <span data-ttu-id="ae367-141">若要停止录制，请说 "你好小娜，停止录制"。</span><span class="sxs-lookup"><span data-stu-id="ae367-141">To stop recording, say "Hey Cortana, stop recording."</span></span>

### <span data-ttu-id="ae367-142">用于录制视频的 "开始" 菜单</span><span class="sxs-lookup"><span data-stu-id="ae367-142">Start menu to record videos</span></span>

<span data-ttu-id="ae367-143">使用 "开始" 手势转到 "**开始**"，然后选择 "**视频**" 图标。</span><span class="sxs-lookup"><span data-stu-id="ae367-143">Use the Start gesture to go to **Start**, then select the **video** icon.</span></span> <span data-ttu-id="ae367-144">将你的头指向你想要捕获的内容，然后[点击](hololens2-basic-usage.md#touch-holograms-near-you)"开始录制"。</span><span class="sxs-lookup"><span data-stu-id="ae367-144">Point your head in the direction of what you want to capture, then [air tap](hololens2-basic-usage.md#touch-holograms-near-you) to start recording.</span></span> <span data-ttu-id="ae367-145">将出现三次倒计时，录制将开始。</span><span class="sxs-lookup"><span data-stu-id="ae367-145">There will be a three second countdown and your recording will begin.</span></span>

<span data-ttu-id="ae367-146">若要停止录制，请使用 "开始" 手势并选择突出显示的**视频**图标。</span><span class="sxs-lookup"><span data-stu-id="ae367-146">To stop recording, use the Start gesture and select the highlighted **video** icon.</span></span> <span data-ttu-id="ae367-147">视频将保存到您的设备。</span><span class="sxs-lookup"><span data-stu-id="ae367-147">The video will be saved to your device.</span></span>

> [!NOTE]
> **<span data-ttu-id="ae367-148">仅适用于 HoloLens （第1代）</span><span class="sxs-lookup"><span data-stu-id="ae367-148">Applies to HoloLens (1st gen) only</span></span>**  
> <span data-ttu-id="ae367-149">[Windows 10 月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)将更改 "开始手势" 和 "Windows" 按钮在 HoloLens （第一代）上的行为方式。</span><span class="sxs-lookup"><span data-stu-id="ae367-149">The [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018) changes how the Start gesture and Windows button behave on HoloLens (1st gen).</span></span> <span data-ttu-id="ae367-150">更新之前，"开始手势" 或 "Windows" 按钮将停止视频录制。</span><span class="sxs-lookup"><span data-stu-id="ae367-150">Before the update, the Start gesture or Windows button would stop a video recording.</span></span> <span data-ttu-id="ae367-151">但是，在更新后，"开始手势" 或 "Windows" 按钮将打开 "**开始**" 菜单（如果你在沉浸式应用中，则会打开 "**快速操作" 菜单**），从中可以选择突出显示的**视频**图标以停止录制。</span><span class="sxs-lookup"><span data-stu-id="ae367-151">After the update, however, the Start gesture or Windows button opens the **Start** menu (or the **quick actions menu** if you are in an immersive app), from which you can select the highlighted **video** icon to stop recording.</span></span>

## <span data-ttu-id="ae367-152">共享您实时看到的内容</span><span class="sxs-lookup"><span data-stu-id="ae367-152">Share what you see in real-time</span></span>

<span data-ttu-id="ae367-153">您可以实时与朋友和同事共享您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="ae367-153">You can share what you see in HoloLens with friends and colleagues in real-time.</span></span> <span data-ttu-id="ae367-154">可以使用以下几种方法：</span><span class="sxs-lookup"><span data-stu-id="ae367-154">There are a few methods available:</span></span>

1. <span data-ttu-id="ae367-155">连接到支持 Miracast 的设备或适配器以在电视上观看。</span><span class="sxs-lookup"><span data-stu-id="ae367-155">Connecting to a Miracast-enabled device or adapter to watch on a TV.</span></span>
1. <span data-ttu-id="ae367-156">使用[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)在电脑上观看</span><span class="sxs-lookup"><span data-stu-id="ae367-156">Using [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to watch on a PC</span></span>
1. <span data-ttu-id="ae367-157">使用[Microsoft HoloLens 配套应用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)在电脑上观看。</span><span class="sxs-lookup"><span data-stu-id="ae367-157">Using the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) to watch on a PC.</span></span>
1. <span data-ttu-id="ae367-158">部署[Microsoft Dynamics 365 远程协助](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist)应用，该应用使前端工作人员能够流式处理他们对远程专家所看到的内容。</span><span class="sxs-lookup"><span data-stu-id="ae367-158">Deploying the [Microsoft Dynamics 365 Remote Assist](https://dynamics.microsoft.com/en-us/mixed-reality/remote-assist) app, which enables front-line workers to stream what they see to a remote expert.</span></span> <span data-ttu-id="ae367-159">然后，远程专家可以通过自己的口头或在世界上进行批注来指导他们。</span><span class="sxs-lookup"><span data-stu-id="ae367-159">The remote expert can then guide the front-line worker verbally or by annotating in their world.</span></span>

> [!NOTE]
> <span data-ttu-id="ae367-160">通过 Windows Device Portal 或 Microsoft HoloLens 附属应用共享所看到的内容要求你的 HoloLens 处于[开发人员模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="ae367-160">Sharing what you see via Windows Device Portal or Microsoft HoloLens companion app requires your HoloLens to be in [Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal).</span></span>

### <span data-ttu-id="ae367-161">通过 Miracast 流处理视频</span><span class="sxs-lookup"><span data-stu-id="ae367-161">Stream video with Miracast</span></span>

<span data-ttu-id="ae367-162">使用 "开始" 手势转到 "**开始**"，然后选择 "**连接**" 图标。</span><span class="sxs-lookup"><span data-stu-id="ae367-162">Use the Start gesture to go to **Start**, then select the **connect** icon.</span></span> <span data-ttu-id="ae367-163">从出现的选取器中，选择要连接到的已启用 Miracast 的设备或适配器。</span><span class="sxs-lookup"><span data-stu-id="ae367-163">From the picker that appears, select the Miracast-enabled device or adapter to which you want to connect.</span></span>

<span data-ttu-id="ae367-164">若要停止共享，请使用 "开始" 手势并选择突出显示的 "**连接**" 图标。</span><span class="sxs-lookup"><span data-stu-id="ae367-164">To stop sharing, use the Start gesture and select the highlighted **connect** icon.</span></span> <span data-ttu-id="ae367-165">由于你正在进行流式处理，因此不会将任何内容保存到你的设备。</span><span class="sxs-lookup"><span data-stu-id="ae367-165">Because you were streaming, nothing will be saved to your device.</span></span>

> [!NOTE]
> <span data-ttu-id="ae367-166">在 HoloLens （第1代）上启用了 Miracast 支持，从[Windows 10 年10月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018)开始。</span><span class="sxs-lookup"><span data-stu-id="ae367-166">Miracast support was enabled on HoloLens (1st gen) beginning with the [Windows 10 October 2018 Update](https://docs.microsoft.com/windows/mixed-reality/release-notes-october-2018).</span></span>

### <span data-ttu-id="ae367-167">Windows Device Portal 的实时视频</span><span class="sxs-lookup"><span data-stu-id="ae367-167">Real time video with Windows Device Portal</span></span>

<span data-ttu-id="ae367-168">由于通过 Windows Device Portal 进行共享需要在 HoloLens 上启用开发人员模式，请按照我们的开发人员文档中的说明[设置开发人员模式和导航 Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="ae367-168">Because sharing via Windows Device Portal requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode and navigate Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>

### <span data-ttu-id="ae367-169">Microsoft HoloLens 辅助应用</span><span class="sxs-lookup"><span data-stu-id="ae367-169">Microsoft HoloLens companion app</span></span>

<span data-ttu-id="ae367-170">由于通过 Microsoft HoloLens 附属应用共享需要在 HoloLens 上启用开发人员模式，请按照我们的开发人员文档中的说明[设置开发人员模式](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="ae367-170">Because sharing via the Microsoft HoloLens companion app requires Developer mode to be enabled on HoloLens, follow the instructions in our developer documentation to [set up Developer mode](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span> <span data-ttu-id="ae367-171">然后，下载[Microsoft HoloLens 配套应用](https://www.microsoft.com/store/productId/9NBLGGH4QWNX)，并按照应用中的说明连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="ae367-171">Then, download the [Microsoft HoloLens companion app](https://www.microsoft.com/store/productId/9NBLGGH4QWNX) and follow the instructions within the app to connect to your HoloLens.</span></span>

<span data-ttu-id="ae367-172">将应用与 HoloLens 一起设置后，从应用的主菜单中选择 "**实时流**" 选项。</span><span class="sxs-lookup"><span data-stu-id="ae367-172">Once the app is set up with your HoloLens, select the **Live stream** option from the app's main menu.</span></span>

## <span data-ttu-id="ae367-173">查看混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="ae367-173">View your mixed reality photos and videos</span></span>

<span data-ttu-id="ae367-174">混合现实照片和视频将保存到设备的 "相机翻转"。</span><span class="sxs-lookup"><span data-stu-id="ae367-174">Mixed reality photos and videos are saved to the device's "Camera Roll".</span></span> <span data-ttu-id="ae367-175">你可以通过 "文件资源管理器" 应用（导航到 "图片 > 相机滚动"）在你的 HoloLens 上浏览此文件夹的内容。</span><span class="sxs-lookup"><span data-stu-id="ae367-175">You can browse the contents of this folder on your HoloLens with the File Explorer app (navigate to Pictures > Camera Roll).</span></span>

<span data-ttu-id="ae367-176">你还可以在预装在 HoloLens 上的照片应用中查看混合现实照片和视频。</span><span class="sxs-lookup"><span data-stu-id="ae367-176">You can also view your mixed reality photos and videos in the Photos app, which is pre-installed on HoloLens.</span></span> <span data-ttu-id="ae367-177">若要在世界上固定照片，请在 "照片" 应用中将其选中，然后选择 "**混合世界**"。</span><span class="sxs-lookup"><span data-stu-id="ae367-177">To pin a photo in your world, select it in the Photos app and choose **Place in mixed world**.</span></span> <span data-ttu-id="ae367-178">在放置后，您可以在世界各地移动照片。</span><span class="sxs-lookup"><span data-stu-id="ae367-178">You can move the photo around your world after it's been placed.</span></span>

<span data-ttu-id="ae367-179">若要在连接到 HoloLens 的电脑上查看和/或保存混合现实照片和视频，可以通过 MTP 使用[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)或[电脑的文件资源管理器](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens)。</span><span class="sxs-lookup"><span data-stu-id="ae367-179">To view and/or save your mixed reality photos and videos on a PC connected to HoloLens, you can use [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture) or your [PC's File Explorer via MTP](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018#new-features-for-hololens).</span></span>

## <span data-ttu-id="ae367-180">分享您的混合现实照片和视频</span><span class="sxs-lookup"><span data-stu-id="ae367-180">Share your mixed reality photos and videos</span></span>

<span data-ttu-id="ae367-181">捕获混合现实照片或视频后，将显示预览。</span><span class="sxs-lookup"><span data-stu-id="ae367-181">After capturing a mixed reality photo or video, a preview will appear.</span></span> <span data-ttu-id="ae367-182">选择预览上方的 "**共享**" 图标以调出 "共享助理"。</span><span class="sxs-lookup"><span data-stu-id="ae367-182">Select the **share** icon above the preview to bring up the share assistant.</span></span> <span data-ttu-id="ae367-183">在此处，你可以选择要在其中共享照片或视频的终结点。</span><span class="sxs-lookup"><span data-stu-id="ae367-183">From there, you can select the end point to which you'd like to share that photo or video.</span></span>

<span data-ttu-id="ae367-184">您也可以通过自动上载您的混合现实照片和视频，从 OneDrive 共享混合现实照片和视频。</span><span class="sxs-lookup"><span data-stu-id="ae367-184">You can also share mixed reality photos and videos from OneDrive, by automatically uploading your mixed reality photos and videos.</span></span> <span data-ttu-id="ae367-185">在 HoloLens 上打开 OneDrive 应用，并使用个人[Microsoft 帐户](https://account.microsoft.com)登录（如果尚未登录）。</span><span class="sxs-lookup"><span data-stu-id="ae367-185">Open the OneDrive app on HoloLens and sign in with a personal [Microsoft account](https://account.microsoft.com) if you haven't already.</span></span> <span data-ttu-id="ae367-186">选择 "**设置**" 图标，然后选择 "**照相机上载**"。</span><span class="sxs-lookup"><span data-stu-id="ae367-186">Select the **settings** icon and choose **Camera upload**.</span></span> <span data-ttu-id="ae367-187">打开相机上传。</span><span class="sxs-lookup"><span data-stu-id="ae367-187">Turn Camera upload on.</span></span> <span data-ttu-id="ae367-188">现在，你的混合现实照片和视频将在 HoloLens 上启动应用时上载到 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="ae367-188">Your mixed reality photos and videos will now be uploaded to OneDrive each time you launch the app on HoloLens.</span></span>

> [!NOTE]
> <span data-ttu-id="ae367-189">如果你已使用个人 Microsoft 帐户登录到 OneDrive，则只能在 OneDrive 中启用相机上传。</span><span class="sxs-lookup"><span data-stu-id="ae367-189">You can only enable camera upload in OneDrive if you’re signed into OneDrive with a personal Microsoft account.</span></span> <span data-ttu-id="ae367-190">如果您使用工作或学校帐户设置 HoloLens，则可以在 OneDrive 应用中添加个人 Microsoft 帐户以启用此功能。</span><span class="sxs-lookup"><span data-stu-id="ae367-190">If you set up HoloLens with a work or school account, you can add a personal Microsoft account in the OneDrive app to enable this feature.</span></span>

## <span data-ttu-id="ae367-191">混合现实捕获的限制</span><span class="sxs-lookup"><span data-stu-id="ae367-191">Limitations of mixed reality capture</span></span>

- <span data-ttu-id="ae367-192">使用混合现实捕获时，HoloLens 的帧频将减半到 30 Hz。</span><span class="sxs-lookup"><span data-stu-id="ae367-192">While using mixed reality capture, the framerate of HoloLens will be halved to 30 Hz.</span></span>
- <span data-ttu-id="ae367-193">视频的最大长度为5分钟。</span><span class="sxs-lookup"><span data-stu-id="ae367-193">Videos have a maximum length of five minutes.</span></span>
- <span data-ttu-id="ae367-194">如果照片/视频相机已由另一个应用程序、实时流处理或系统资源不足，可能会降低照片和视频的分辨率。</span><span class="sxs-lookup"><span data-stu-id="ae367-194">The resolution of photos and videos may be reduced if the photo/video camera is already in use by another application, while live streaming, or when system resources are low.</span></span>

## <span data-ttu-id="ae367-195">默认文件格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="ae367-195">Default file format and resolution</span></span>

### <span data-ttu-id="ae367-196">默认照片格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="ae367-196">Default photo format and resolution</span></span>

|  <span data-ttu-id="ae367-197">设备</span><span class="sxs-lookup"><span data-stu-id="ae367-197">Device</span></span>  |  <span data-ttu-id="ae367-198">格式</span><span class="sxs-lookup"><span data-stu-id="ae367-198">Format</span></span>  |  <span data-ttu-id="ae367-199">扩展</span><span class="sxs-lookup"><span data-stu-id="ae367-199">Extension</span></span>  |  <span data-ttu-id="ae367-200">分辨率</span><span class="sxs-lookup"><span data-stu-id="ae367-200">Resolution</span></span>  |
|----------|----------|----------|----------|
| <span data-ttu-id="ae367-201">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="ae367-201">HoloLens 2</span></span> | [<span data-ttu-id="ae367-202">JPEG</span><span class="sxs-lookup"><span data-stu-id="ae367-202">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="ae367-203">.jpg</span><span class="sxs-lookup"><span data-stu-id="ae367-203">.jpg</span></span> | <span data-ttu-id="ae367-204">3904x2196px</span><span class="sxs-lookup"><span data-stu-id="ae367-204">3904x2196px</span></span> |
| <span data-ttu-id="ae367-205">HoloLens （第1代）</span><span class="sxs-lookup"><span data-stu-id="ae367-205">HoloLens (1st gen)</span></span> | [<span data-ttu-id="ae367-206">JPEG</span><span class="sxs-lookup"><span data-stu-id="ae367-206">JPEG</span></span>](https://en.wikipedia.org/wiki/JPEG) | <span data-ttu-id="ae367-207">.jpg</span><span class="sxs-lookup"><span data-stu-id="ae367-207">.jpg</span></span> | <span data-ttu-id="ae367-208">1408x792px</span><span class="sxs-lookup"><span data-stu-id="ae367-208">1408x792px</span></span> |

### <span data-ttu-id="ae367-209">录制的视频格式和分辨率</span><span class="sxs-lookup"><span data-stu-id="ae367-209">Recorded video format and resolution</span></span>

| <span data-ttu-id="ae367-210">设备</span><span class="sxs-lookup"><span data-stu-id="ae367-210">Device</span></span> | <span data-ttu-id="ae367-211">格式</span><span class="sxs-lookup"><span data-stu-id="ae367-211">Format</span></span> | <span data-ttu-id="ae367-212">扩展</span><span class="sxs-lookup"><span data-stu-id="ae367-212">Extension</span></span> | <span data-ttu-id="ae367-213">分辨率</span><span class="sxs-lookup"><span data-stu-id="ae367-213">Resolution</span></span> | <span data-ttu-id="ae367-214">度</span><span class="sxs-lookup"><span data-stu-id="ae367-214">Speed</span></span> | <span data-ttu-id="ae367-215">音频</span><span class="sxs-lookup"><span data-stu-id="ae367-215">Audio</span></span> |
|----------|----------|----------|----------|----------|----------|
| <span data-ttu-id="ae367-216">HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="ae367-216">HoloLens 2</span></span> | [<span data-ttu-id="ae367-217">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="ae367-217">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="ae367-218">.mp4</span><span class="sxs-lookup"><span data-stu-id="ae367-218">.mp4</span></span> | <span data-ttu-id="ae367-219">1920x1080px</span><span class="sxs-lookup"><span data-stu-id="ae367-219">1920x1080px</span></span> | <span data-ttu-id="ae367-220">30fps</span><span class="sxs-lookup"><span data-stu-id="ae367-220">30fps</span></span> | <span data-ttu-id="ae367-221">48kHz 立体声</span><span class="sxs-lookup"><span data-stu-id="ae367-221">48kHz Stereo</span></span> |
| <span data-ttu-id="ae367-222">HoloLens （第1代）</span><span class="sxs-lookup"><span data-stu-id="ae367-222">HoloLens (1st gen)</span></span> |  [<span data-ttu-id="ae367-223">MPEG-4</span><span class="sxs-lookup"><span data-stu-id="ae367-223">MPEG-4</span></span>](https://en.wikipedia.org/wiki/MPEG-4) | <span data-ttu-id="ae367-224">.mp4</span><span class="sxs-lookup"><span data-stu-id="ae367-224">.mp4</span></span> | <span data-ttu-id="ae367-225">1216x684px</span><span class="sxs-lookup"><span data-stu-id="ae367-225">1216x684px</span></span> | <span data-ttu-id="ae367-226">24fps</span><span class="sxs-lookup"><span data-stu-id="ae367-226">24fps</span></span> | <span data-ttu-id="ae367-227">48kHz 立体声</span><span class="sxs-lookup"><span data-stu-id="ae367-227">48kHz Stereo</span></span> |
