---
title: 故障排除
description: 随时了解 HoloLens 设备问题的最常见解决方案和故障排除技术。
author: mattzmsft
ms.author: mazeller
ms.date: 12/02/2019
ms.prod: hololens
ms.topic: article
audience: HoloLens
ms.localizationpriority: medium
manager: jarrettr
ms.custom:
- CI 111456
- CSSTroubleshooting
keywords: 问题， bug， 故障排除， 修复， 帮助， 支持， HoloLens
ms.openlocfilehash: 1039af533b5039eb4eef6599c7cbb480955b0661
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397258"
---
# <a name="troubleshoot-common-issues"></a><span data-ttu-id="04b35-104">排查常见问题</span><span class="sxs-lookup"><span data-stu-id="04b35-104">Troubleshoot common issues</span></span>

<span data-ttu-id="04b35-105">本文介绍如何解决几个常见的 HoloLens 问题。</span><span class="sxs-lookup"><span data-stu-id="04b35-105">This article describes how to resolve several common HoloLens issues.</span></span>

## <a name="my-hololens-is-unresponsive-or-wont-start"></a><span data-ttu-id="04b35-106">我的 HoloLens 无响应或无法启动</span><span class="sxs-lookup"><span data-stu-id="04b35-106">My HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="04b35-107">如果 HoloLens 无法启动：</span><span class="sxs-lookup"><span data-stu-id="04b35-107">If your HoloLens won't start:</span></span>

- <span data-ttu-id="04b35-108">如果电源按钮旁边的 LED 不亮起，或只有一个 LED 短暂闪烁，可能需要为 [HoloLens 收费。](hololens-recovery.md#charge-the-device)</span><span class="sxs-lookup"><span data-stu-id="04b35-108">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens-recovery.md#charge-the-device)</span></span>
- <span data-ttu-id="04b35-109">如果 LED 在按下电源按钮时亮起，但在显示器上看不到任何内容，请对设备 进行硬 [重置](hololens-recovery.md#hard-reset-procedure)。</span><span class="sxs-lookup"><span data-stu-id="04b35-109">If the LEDs light up when you press the power button but you can't see anything on the displays, [preform a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="04b35-110">如果 HoloLens 冻结或无响应：</span><span class="sxs-lookup"><span data-stu-id="04b35-110">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="04b35-111">按电源按钮关闭 HoloLens，直到所有五个 LED 都自行关闭，如果 LED 无响应，则关闭 15 秒。</span><span class="sxs-lookup"><span data-stu-id="04b35-111">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="04b35-112">若要启动 HoloLens，请再次按电源按钮。</span><span class="sxs-lookup"><span data-stu-id="04b35-112">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="04b35-113">如果这些步骤不起作用，可以尝试恢复 HoloLens 2 或[](hololens-recovery.md) [HoloLens (第一代) 设备。](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="04b35-113">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

## <a name="holograms-dont-look-good"></a><span data-ttu-id="04b35-114">全息影像看起来不错</span><span class="sxs-lookup"><span data-stu-id="04b35-114">Holograms don't look good</span></span>

<span data-ttu-id="04b35-115">如果全息影像不稳定、跳转或看起来不对，请尝试：</span><span class="sxs-lookup"><span data-stu-id="04b35-115">If your holograms are unstable, jumpy, or don't look right, try:</span></span>

- <span data-ttu-id="04b35-116">清理 HoloLens 前面的设备视网和传感器栏。</span><span class="sxs-lookup"><span data-stu-id="04b35-116">Cleaning your device visor and sensor bar on the front of your HoloLens.</span></span>
- <span data-ttu-id="04b35-117">增加房间中的光线。</span><span class="sxs-lookup"><span data-stu-id="04b35-117">Increasing the light in your room.</span></span>
- <span data-ttu-id="04b35-118">四处浏览并查看周围的环境，以便 HoloLens 可以更彻底地扫描它们。</span><span class="sxs-lookup"><span data-stu-id="04b35-118">Walking around and looking at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="04b35-119">为眼睛校准 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="04b35-119">Calibrating your HoloLens for your eyes.</span></span> <span data-ttu-id="04b35-120">转到"**设置**  >  **系统**  >  **实用工具"。**</span><span class="sxs-lookup"><span data-stu-id="04b35-120">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="04b35-121">在 **"校准"** 下，选择 **"打开校准"。**</span><span class="sxs-lookup"><span data-stu-id="04b35-121">Under **Calibration**, select **Open Calibration**.</span></span>
 
### <a name="reporting-issues-where-holograms-are-unstable-or-dont-look-right"></a><span data-ttu-id="04b35-122">报告全息影像不稳定或外观错误的问题</span><span class="sxs-lookup"><span data-stu-id="04b35-122">Reporting issues where Holograms are unstable or don't look right</span></span>
 
1. <span data-ttu-id="04b35-123">请记录并记录问题的 [混合现实](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 。</span><span class="sxs-lookup"><span data-stu-id="04b35-123">Please record and a [Mixed Reality Capture video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) of the issue.</span></span> <span data-ttu-id="04b35-124">此视频稍后可通过反馈中心作为附加文件上传。</span><span class="sxs-lookup"><span data-stu-id="04b35-124">This video can be later uploaded through Feedback Hub as an attached file.</span></span>  
1. <span data-ttu-id="04b35-125">通过 "**设置**" 应用启用整个遥测 >**隐私**  ->  **诊断 & 反馈**，并在 **可选诊断数据** 下，确保将切换设置为 **"开**"</span><span class="sxs-lookup"><span data-stu-id="04b35-125">Enable full telemetry via the **Settings** app -> **Privacy** -> **Diagnostics & feedback** and under **Optional diagnostics data** ensure the toggle is set to **On**</span></span>
1. <span data-ttu-id="04b35-126">通过更新到最新的 [Windows 全息操作系统， (20H2 或更高) ， ](hololens-release-notes.md#windows-holographic-version-20h2)获取最新的全息图缩放和稳定性修复。</span><span class="sxs-lookup"><span data-stu-id="04b35-126">Get the latest hologram scale and stability fixes by updating to the latest [Windows Holographic OS, (20H2 or higher)](hololens-release-notes.md#windows-holographic-version-20h2).</span></span> <span data-ttu-id="04b35-127">更新后，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="04b35-127">After updating perform the following:</span></span>
    1. <span data-ttu-id="04b35-128">通过 "**设置**" "应用" "应用" "> **>"**"" "" "" "" 中删除所有全息  ->   </span><span class="sxs-lookup"><span data-stu-id="04b35-128">Remove all Holograms via **Settings** app -> **System** -> **Holograms** -> then select **Remove all holograms** and start with a fresh map.</span></span>
    1. <span data-ttu-id="04b35-129">戴上 HoloLens 并浏览房间并观看空间中的所有区域和图面，从而创建空间的新地图。</span><span class="sxs-lookup"><span data-stu-id="04b35-129">Create a new map of your space by wearing the HoloLens and walking around your room and looking at all areas and surfaces in the space.</span></span> <span data-ttu-id="04b35-130">为2-3 分钟执行此操作。</span><span class="sxs-lookup"><span data-stu-id="04b35-130">Do this for 2-3 minutes.</span></span>
    1. <span data-ttu-id="04b35-131">执行 IPD 校准。</span><span class="sxs-lookup"><span data-stu-id="04b35-131">Perform IPD calibration.</span></span> <span data-ttu-id="04b35-132">中转到 "**设置**" "系统" "  >    >  **实用工具**"。</span><span class="sxs-lookup"><span data-stu-id="04b35-132">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="04b35-133">在 **校准** 下，选择 " **打开校准**"。</span><span class="sxs-lookup"><span data-stu-id="04b35-133">Under **Calibration**, select **Open Calibration**.</span></span>
    1. <span data-ttu-id="04b35-134">重新测试方案，并查看它是否仍然存在。</span><span class="sxs-lookup"><span data-stu-id="04b35-134">Re-test the scenario and see if it still persists.</span></span>
1. <span data-ttu-id="04b35-135">如果更新不能解决问题，请提交 [反馈中心问题](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="04b35-135">If updating does not fix the issue, please file a [Feedback Hub issue](hololens-feedback.md).</span></span> <span data-ttu-id="04b35-136">填写反馈后，可以使用 " **共享** " 按钮，创建一个易于共享的链接，以便在联系支持人员时发送。</span><span class="sxs-lookup"><span data-stu-id="04b35-136">After you've filled feedback you can use the **Share** button, to create an easy to share link that can be sent when contacting support.</span></span>

## <a name="hololens-doesnt-respond-to-hand-input"></a><span data-ttu-id="04b35-137">HoloLens 未响应手写输入</span><span class="sxs-lookup"><span data-stu-id="04b35-137">HoloLens doesn't respond to hand input</span></span>

<span data-ttu-id="04b35-138">若要确保 HoloLens 能看到你的手，你需要将它们保留在手势帧中。</span><span class="sxs-lookup"><span data-stu-id="04b35-138">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="04b35-139">混合现实主页提供反馈，让你知道何时跟踪你的手。</span><span class="sxs-lookup"><span data-stu-id="04b35-139">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="04b35-140">不同版本的 HoloLens 的反馈有所不同：</span><span class="sxs-lookup"><span data-stu-id="04b35-140">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="04b35-141">在 HoloLens (第一代) 上，注视光标从点变为圆圈</span><span class="sxs-lookup"><span data-stu-id="04b35-141">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="04b35-142">在 HoloLens 2 上，当您的手接近于一手指时，会出现一个 "</span><span class="sxs-lookup"><span data-stu-id="04b35-142">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="04b35-143">许多沉浸式应用遵循类似于混合现实主页的输入模式。</span><span class="sxs-lookup"><span data-stu-id="04b35-143">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="04b35-144">详细了解在[HoloLens (第一](hololens1-basic-usage.md#use-hololens-with-your-hands)代) 和[HoloLens 2。](hololens2-basic-usage.md#the-hand-tracking-frame)</span><span class="sxs-lookup"><span data-stu-id="04b35-144">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="04b35-145">如果你正在戴眼镜，请注意，某些类型的手部手部跟踪不起作用。</span><span class="sxs-lookup"><span data-stu-id="04b35-145">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="04b35-146">一个常见示例是黑色保护套，它往往能吸收光线，并且不会由深度相机拾取。</span><span class="sxs-lookup"><span data-stu-id="04b35-146">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="04b35-147">如果你的工作涉及橡皮套，我们建议尝试较浅的颜色，如蓝色或灰色。</span><span class="sxs-lookup"><span data-stu-id="04b35-147">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="04b35-148">另一个示例是大包袋套，它往往遮盖手的形状。</span><span class="sxs-lookup"><span data-stu-id="04b35-148">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="04b35-149">我们建议使用尽可能适合窗体的外套，以获得最佳结果。</span><span class="sxs-lookup"><span data-stu-id="04b35-149">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="04b35-150">如果你的视器有指纹或指纹，请使用 HoloLens 中随它一起使用的微fiber 清理设备来清理视道。</span><span class="sxs-lookup"><span data-stu-id="04b35-150">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

## <a name="hololens-doesnt-respond-to-my-voice-commands"></a><span data-ttu-id="04b35-151">HoloLens 不响应我的语音命令</span><span class="sxs-lookup"><span data-stu-id="04b35-151">HoloLens doesn't respond to my voice commands</span></span>

<span data-ttu-id="04b35-152">如果 Cortana 未响应语音命令，请确保 Cortana 已打开。</span><span class="sxs-lookup"><span data-stu-id="04b35-152">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="04b35-153">在"所有应用"列表中，选择 **"Cortana**  >  **菜单**  >  **笔记本**  >  **设置**"以进行更改。</span><span class="sxs-lookup"><span data-stu-id="04b35-153">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="04b35-154">若要详细了解可以说出的话，请参阅将语音 [与 HoloLens 一起使用](hololens-cortana.md)。</span><span class="sxs-lookup"><span data-stu-id="04b35-154">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

## <a name="i-cant-place-holograms-or-see-holograms-that-i-previously-placed"></a><span data-ttu-id="04b35-155">无法放置全息影像或查看之前放置的全息影像</span><span class="sxs-lookup"><span data-stu-id="04b35-155">I can't place holograms or see holograms that I previously placed</span></span>

<span data-ttu-id="04b35-156">如果 HoloLens 无法映射或加载空间，它将进入受限模式，你将无法放置全息影像或查看已放置的全息影像。</span><span class="sxs-lookup"><span data-stu-id="04b35-156">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="04b35-157">可以尝试以下操作：</span><span class="sxs-lookup"><span data-stu-id="04b35-157">Here are some things to try:</span></span>

- <span data-ttu-id="04b35-158">请确保环境中有足够的光线，以便 HoloLens 可以看到和映射空间。</span><span class="sxs-lookup"><span data-stu-id="04b35-158">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="04b35-159">确保已连接到 Wi-Fi 网络。</span><span class="sxs-lookup"><span data-stu-id="04b35-159">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="04b35-160">如果未连接到 Wi-Fi，HoloLens 无法识别和加载已知空间。</span><span class="sxs-lookup"><span data-stu-id="04b35-160">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="04b35-161">如果需要创建新空间，请连接到 Wi-Fi，然后重启 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="04b35-161">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="04b35-162">若要查看正确的空间是否处于活动状态，或要手动加载空间，请转到"设置  >  **系统** 空间  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="04b35-162">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="04b35-163">如果加载了正确的空间，但仍遇到问题，则空间可能已损坏。</span><span class="sxs-lookup"><span data-stu-id="04b35-163">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="04b35-164">若要解决此问题，请选择该空间，然后选择 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="04b35-164">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="04b35-165">删除空间后，HoloLens 会开始映射你的环境并创建新空间。</span><span class="sxs-lookup"><span data-stu-id="04b35-165">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

## <a name="my-hololens-cant-tell-what-space-im-in"></a><span data-ttu-id="04b35-166">我的 HoloLens 无法判断我的空间</span><span class="sxs-lookup"><span data-stu-id="04b35-166">My HoloLens can't tell what space I'm in</span></span>

<span data-ttu-id="04b35-167">如果你的 HoloLens 无法识别并加载你自动登录的空间，请检查以下因素：</span><span class="sxs-lookup"><span data-stu-id="04b35-167">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="04b35-168">请确保已连接到 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="04b35-168">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="04b35-169">请确保房间内有充足的光线</span><span class="sxs-lookup"><span data-stu-id="04b35-169">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="04b35-170">请确保不存在对周围环境的任何重大更改。</span><span class="sxs-lookup"><span data-stu-id="04b35-170">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="04b35-171">还可以通过转到 "**设置**" "  >  **系统**  >  **空间**" 手动加载空间或管理空间。</span><span class="sxs-lookup"><span data-stu-id="04b35-171">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

## <a name="im-getting-a-low-disk-space-error"></a><span data-ttu-id="04b35-172">我收到 "磁盘空间不足" 错误</span><span class="sxs-lookup"><span data-stu-id="04b35-172">I'm getting a "low disk space" error</span></span>

<span data-ttu-id="04b35-173">你需要通过执行以下一项或多项操作来释放一些存储空间：</span><span class="sxs-lookup"><span data-stu-id="04b35-173">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="04b35-174">删除某些未使用的空间。</span><span class="sxs-lookup"><span data-stu-id="04b35-174">Delete some unused spaces.</span></span> <span data-ttu-id="04b35-175">单击 "**设置**"  >  "**系统**  >  **空间**"，选择不再需要的空间，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="04b35-175">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="04b35-176">删除已放置的部分全息影像。</span><span class="sxs-lookup"><span data-stu-id="04b35-176">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="04b35-177">从照片应用中删除一些图片和视频。</span><span class="sxs-lookup"><span data-stu-id="04b35-177">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="04b35-178">从 HoloLens 卸载某些应用。</span><span class="sxs-lookup"><span data-stu-id="04b35-178">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="04b35-179">在 " **所有应用** " 列表中，点击并按住你要卸载的应用，然后选择 " **卸载**"。</span><span class="sxs-lookup"><span data-stu-id="04b35-179">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

## <a name="my-hololens-cant-create-a-new-space"></a><span data-ttu-id="04b35-180">我的 HoloLens 无法创建新的空间</span><span class="sxs-lookup"><span data-stu-id="04b35-180">My HoloLens can't create a new space</span></span>

<span data-ttu-id="04b35-181">最可能的问题是在存储空间不足的情况下运行。</span><span class="sxs-lookup"><span data-stu-id="04b35-181">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="04b35-182">请尝试前面的某个 [提示](#im-getting-a-low-disk-space-error) 以释放一些磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="04b35-182">Try one of the [previous tips](#im-getting-a-low-disk-space-error) to free up some disk space.</span></span>

## <a name="the-hololens-emulator-isnt-working"></a><span data-ttu-id="04b35-183">HoloLens 模拟器不工作</span><span class="sxs-lookup"><span data-stu-id="04b35-183">The HoloLens emulator isn't working</span></span>

<span data-ttu-id="04b35-184">有关 HoloLens 模拟器的信息，请参阅我们的开发人员文档。</span><span class="sxs-lookup"><span data-stu-id="04b35-184">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="04b35-185">详细了解如何 [排查 HoloLens 模拟器问题](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="04b35-185">Read more about [troubleshooting the HoloLens emulator](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>
