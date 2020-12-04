---
title: 疑难解答
description: 常见 HoloLens 问题的解决方案。
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
keywords: 问题、缺陷、故障排除、修复、帮助、支持、HoloLens
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.openlocfilehash: 4f077a8bb2592ab9b650e2e8021c97d3d8524dcc
ms.sourcegitcommit: d20f610edd7db452ccc2ac554fc8d21bd89b0b99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "11195278"
---
# <span data-ttu-id="fd6f0-104">疑难解答</span><span class="sxs-lookup"><span data-stu-id="fd6f0-104">Troubleshooting</span></span>

<span data-ttu-id="fd6f0-105">本文介绍如何解决几个常见的 HoloLens 问题。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-105">This article describes how to resolve several common HoloLens issues.</span></span>

## <span data-ttu-id="fd6f0-106">我的 HoloLens 没有响应或无法启动</span><span class="sxs-lookup"><span data-stu-id="fd6f0-106">My HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="fd6f0-107">如果您的 HoloLens 无法启动：</span><span class="sxs-lookup"><span data-stu-id="fd6f0-107">If your HoloLens won't start:</span></span>

- <span data-ttu-id="fd6f0-108">如果电源按钮旁边的指示灯未亮起，或者只有一个指示灯闪烁，则您可能需要为 [HoloLens 收费。](hololens-recovery.md#charge-the-device)</span><span class="sxs-lookup"><span data-stu-id="fd6f0-108">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens-recovery.md#charge-the-device)</span></span>
- <span data-ttu-id="fd6f0-109">如果在按下电源按钮时指示灯亮起，但在显示器上看不到任何内容，请 [preform 设备的硬重置](hololens-recovery.md#hard-reset-procedure)。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-109">If the LEDs light up when you press the power button but you can't see anything on the displays, [preform a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="fd6f0-110">如果你的 HoloLens 已冻结或无响应：</span><span class="sxs-lookup"><span data-stu-id="fd6f0-110">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="fd6f0-111">按 "电源" 按钮以关闭 HoloLens，直到所有五个指示灯关闭，或者如果指示灯无响应，则为15秒。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-111">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="fd6f0-112">若要启动 HoloLens，请再次按下电源按钮。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-112">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="fd6f0-113">如果这些步骤不起作用，可以尝试 [恢复 hololens 2 设备](hololens-recovery.md) 或 [hololens (第一代) 设备。](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="fd6f0-113">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

## <span data-ttu-id="fd6f0-114">全息影像看起来不好</span><span class="sxs-lookup"><span data-stu-id="fd6f0-114">Holograms don't look good</span></span>

<span data-ttu-id="fd6f0-115">如果您的全息影像不稳定、jumpy 或看起来不稳定，请尝试：</span><span class="sxs-lookup"><span data-stu-id="fd6f0-115">If your holograms are unstable, jumpy, or don't look right, try:</span></span>

- <span data-ttu-id="fd6f0-116">在 HoloLens 前面清洗设备面板和传感器栏。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-116">Cleaning your device visor and sensor bar on the front of your HoloLens.</span></span>
- <span data-ttu-id="fd6f0-117">增加房间中的光线。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-117">Increasing the light in your room.</span></span>
- <span data-ttu-id="fd6f0-118">浏览和查看你的周围环境，以便 HoloLens 能够更完整地对其进行扫描。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-118">Walking around and looking at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="fd6f0-119">为眼睛校准您的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-119">Calibrating your HoloLens for your eyes.</span></span> <span data-ttu-id="fd6f0-120">转到 "**设置**  >  **系统**  >  **实用工具**"。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-120">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="fd6f0-121">在“**校准**”下，选择“**打开校准**”。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-121">Under **Calibration**, select **Open Calibration**.</span></span>
 
### <span data-ttu-id="fd6f0-122">报告全息图不稳定或未正确显示的问题</span><span class="sxs-lookup"><span data-stu-id="fd6f0-122">Reporting issues where Holograms are unstable or don't look right</span></span>
 
1. <span data-ttu-id="fd6f0-123">请记录和 [混合现实捕获](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 问题的视频。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-123">Please record and a [Mixed Reality Capture video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) of the issue.</span></span> <span data-ttu-id="fd6f0-124">此视频稍后可通过 "反馈中心" 上传为附加的文件。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-124">This video can be later uploaded through Feedback Hub as an attached file.</span></span>  
1. <span data-ttu-id="fd6f0-125">通过 "**设置**" 应用的 "设置" 应用 > "**隐私**  ->  **诊断" & 反馈**和可选的 "**诊断" 数据**下，确保切换设置为 **"打开**"</span><span class="sxs-lookup"><span data-stu-id="fd6f0-125">Enable full telemetry via the **Settings** app -> **Privacy** -> **Diagnostics & feedback** and under **Optional diagnostics data** ensure the toggle is set to **On**</span></span>
1. <span data-ttu-id="fd6f0-126">通过更新到最新的 [Windows 全息操作系统、 (20H2 或更高版本的) ， ](hololens-release-notes.md#windows-holographic-version-20h2)获取最新的全息图缩放和稳定性修复。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-126">Get the latest hologram scale and stability fixes by updating to the latest [Windows Holographic OS, (20H2 or higher)](hololens-release-notes.md#windows-holographic-version-20h2).</span></span> <span data-ttu-id="fd6f0-127">更新后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fd6f0-127">After updating perform the following:</span></span>
    1. <span data-ttu-id="fd6f0-128">通过 "**设置**" 应用删除所有全息影像->**系统**  ->  **全息影像**-> 然后选择 "**删除所有全息影像**" 并从新地图开始。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-128">Remove all Holograms via **Settings** app -> **System** -> **Holograms** -> then select **Remove all holograms** and start with a fresh map.</span></span>
    1. <span data-ttu-id="fd6f0-129">通过戴上 HoloLens 并浏览房间并查看空间中的所有区域和表面来创建新的空间地图。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-129">Create a new map of your space by wearing the HoloLens and walking around your room and looking at all areas and surfaces in the space.</span></span> <span data-ttu-id="fd6f0-130">为2-3 分钟执行此操作。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-130">Do this for 2-3 minutes.</span></span>
    1. <span data-ttu-id="fd6f0-131">执行 IPD 校准。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-131">Perform IPD calibration.</span></span> <span data-ttu-id="fd6f0-132">转到 "**设置**  >  **系统**  >  **实用工具**"。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-132">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="fd6f0-133">在“**校准**”下，选择“**打开校准**”。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-133">Under **Calibration**, select **Open Calibration**.</span></span>
    1. <span data-ttu-id="fd6f0-134">重新测试方案，并查看它是否仍然存在。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-134">Re-test the scenario and see if it still persists.</span></span>
1. <span data-ttu-id="fd6f0-135">如果更新不能解决问题，请为 " [反馈中心" 问题](hololens-feedback.md)提供文件。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-135">If updating does not fix the issue, please file a [Feedback Hub issue](hololens-feedback.md).</span></span> <span data-ttu-id="fd6f0-136">填写反馈后，您可以使用 " **共享** " 按钮创建一个易于共享的链接，该链接可以在联系支持人员时发送。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-136">After you've filled feedback you can use the **Share** button, to create an easy to share link that can be sent when contacting support.</span></span>

## <span data-ttu-id="fd6f0-137">HoloLens 未响应手动输入</span><span class="sxs-lookup"><span data-stu-id="fd6f0-137">HoloLens doesn't respond to hand input</span></span>

<span data-ttu-id="fd6f0-138">为确保 HoloLens 能够看到你的手，你需要将它们放在手势帧中。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-138">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="fd6f0-139">混合现实主页提供的反馈可让你了解你的手何时被跟踪。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-139">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="fd6f0-140">不同版本的 HoloLens 的反馈不同：</span><span class="sxs-lookup"><span data-stu-id="fd6f0-140">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="fd6f0-141">在 HoloLens (第一代) ，注视光标从一个点更改为圆圈</span><span class="sxs-lookup"><span data-stu-id="fd6f0-141">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="fd6f0-142">在 HoloLens 2 上，当你的手型接近盖板时，将显示一个指尖光标，当 slates 更远时，将显示一个手形射线</span><span class="sxs-lookup"><span data-stu-id="fd6f0-142">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="fd6f0-143">许多沉浸式应用都遵循类似于混合现实主页的输入模式。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-143">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="fd6f0-144">了解有关在 [HoloLens (第一代) ](hololens1-basic-usage.md#use-hololens-with-your-hands) 和 [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)上使用手动输入的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-144">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="fd6f0-145">如果戴上手套，请注意，某些类型的手套不能与手动跟踪一起使用。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-145">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="fd6f0-146">一个常见的示例是黑色橡胶手套，它趋向于吸收红外线，而不是由深度相机拾取。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-146">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="fd6f0-147">如果你的工作涉及橡胶手套，我们建议尝试使用较浅的颜色，如蓝色或灰色。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-147">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="fd6f0-148">另一个示例是大型 baggy 手套，它往往会遮盖你的手型形状。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-148">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="fd6f0-149">我们建议使用符合窗体的手套以获得最佳效果。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-149">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="fd6f0-150">如果你的面板有指纹或涂抹，请使用 HoloLens 随附的 microfiber 清洁布来轻轻清理你的面板。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-150">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

## <span data-ttu-id="fd6f0-151">HoloLens 没有响应我的语音命令</span><span class="sxs-lookup"><span data-stu-id="fd6f0-151">HoloLens doesn't respond to my voice commands</span></span>

<span data-ttu-id="fd6f0-152">如果 Cortana 没有响应你的语音命令，请确保 Cortana 已打开。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-152">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="fd6f0-153">在 "所有应用" 列表中，选择 " **Cortana**  >  **菜单**  >  **笔记本**  >  **设置**" 以进行更改。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-153">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="fd6f0-154">若要了解有关可以说出的内容的详细信息，请参阅[使用语音操作 HoloLens](hololens-cortana.md)。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-154">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

## <span data-ttu-id="fd6f0-155">我无法放置全息影像或查看以前放置的全息影像</span><span class="sxs-lookup"><span data-stu-id="fd6f0-155">I can't place holograms or see holograms that I previously placed</span></span>

<span data-ttu-id="fd6f0-156">如果 HoloLens 无法映射或加载你的空间，它将进入 "有限模式"，你将无法放置全息影像或查看你放置的全息影像。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-156">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="fd6f0-157">你可以尝试以下操作：</span><span class="sxs-lookup"><span data-stu-id="fd6f0-157">Here are some things to try:</span></span>

- <span data-ttu-id="fd6f0-158">请确保你的环境中有足够的光线，以便 HoloLens 可以查看和映射空间。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-158">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="fd6f0-159">请确保已连接到 Wi-Fi 网络。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-159">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="fd6f0-160">如果你未连接到 Wi-fi，则 HoloLens 无法识别和加载已知空间。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-160">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="fd6f0-161">如果需要创建新的空间，请连接到 Wi-fi，然后重新启动 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-161">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="fd6f0-162">若要查看正确的空间是否处于活动状态，或者要手动加载空间，请转到 "**设置**  >  **系统**  >  **空间**"。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-162">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="fd6f0-163">如果加载了正确的空间，但仍遇到问题，则空间可能已损坏。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-163">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="fd6f0-164">若要解决此问题，请选择空间，然后选择 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-164">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="fd6f0-165">删除空间后，HoloLens 将开始映射你的周围环境并创建新空间。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-165">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

## <span data-ttu-id="fd6f0-166">我的 HoloLens 无法分辨我正在输入的空间</span><span class="sxs-lookup"><span data-stu-id="fd6f0-166">My HoloLens can't tell what space I'm in</span></span>

<span data-ttu-id="fd6f0-167">如果你的 HoloLens 无法识别和加载你自动加载的空间，请检查以下因素：</span><span class="sxs-lookup"><span data-stu-id="fd6f0-167">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="fd6f0-168">请确保您已连接到 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="fd6f0-168">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="fd6f0-169">确保房间中有充足的光线</span><span class="sxs-lookup"><span data-stu-id="fd6f0-169">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="fd6f0-170">请确保没有对周围环境进行任何重大更改。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-170">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="fd6f0-171">您也可以通过转到 "**设置**  >  **系统**  >  **空间**" 手动加载空间或管理您的共享空间。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-171">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

## <span data-ttu-id="fd6f0-172">收到 "磁盘空间不足" 错误</span><span class="sxs-lookup"><span data-stu-id="fd6f0-172">I'm getting a "low disk space" error</span></span>

<span data-ttu-id="fd6f0-173">您需要通过执行下列一项或多项操作来释放存储空间：</span><span class="sxs-lookup"><span data-stu-id="fd6f0-173">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="fd6f0-174">删除一些未使用的空间。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-174">Delete some unused spaces.</span></span> <span data-ttu-id="fd6f0-175">转到 "**设置**  >  **系统**  >  **空间**"，选择不再需要的空间，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-175">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="fd6f0-176">删除一些你放置的全息影像。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-176">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="fd6f0-177">从 "照片" 应用中删除一些图片和视频。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-177">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="fd6f0-178">从 HoloLens 中卸载某些应用。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-178">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="fd6f0-179">在 " **所有应用** " 列表中，点击并按住要卸载的应用，然后选择 " **卸载**"。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-179">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

## <span data-ttu-id="fd6f0-180">我的 HoloLens 无法创建新的空间</span><span class="sxs-lookup"><span data-stu-id="fd6f0-180">My HoloLens can't create a new space</span></span>

<span data-ttu-id="fd6f0-181">最可能的问题是你的存储空间不足。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-181">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="fd6f0-182">请尝试以前的一个 [提示](#im-getting-a-low-disk-space-error) ，释放一些磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-182">Try one of the [previous tips](#im-getting-a-low-disk-space-error) to free up some disk space.</span></span>

## <span data-ttu-id="fd6f0-183">HoloLens 模拟器无法正常工作</span><span class="sxs-lookup"><span data-stu-id="fd6f0-183">The HoloLens emulator isn't working</span></span>

<span data-ttu-id="fd6f0-184">有关 HoloLens 模拟器的信息位于我们的开发人员文档中。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-184">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="fd6f0-185">阅读有关 [对 HoloLens 模拟器进行故障排除的](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)详细信息。</span><span class="sxs-lookup"><span data-stu-id="fd6f0-185">Read more about [troubleshooting the HoloLens emulator](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>
