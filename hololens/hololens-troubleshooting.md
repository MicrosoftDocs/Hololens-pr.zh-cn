---
title: 疑难解答
description: 了解 HoloLens 设备问题和疑难解答技术最常见的解决方案。
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
keywords: 问题， bug， 疑难解答， 修复， 帮助， 支持， HoloLens
ms.openlocfilehash: f57aea52337f7ca7e15bda1363f73a3a7265a025
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283043"
---
# <span data-ttu-id="2b909-104">疑难解答</span><span class="sxs-lookup"><span data-stu-id="2b909-104">Troubleshooting</span></span>

<span data-ttu-id="2b909-105">本文介绍如何解决多个常见的 HoloLens 问题。</span><span class="sxs-lookup"><span data-stu-id="2b909-105">This article describes how to resolve several common HoloLens issues.</span></span>

## <span data-ttu-id="2b909-106">我的 HoloLens 无响应或无法启动</span><span class="sxs-lookup"><span data-stu-id="2b909-106">My HoloLens is unresponsive or won't start</span></span>

<span data-ttu-id="2b909-107">如果你的 HoloLens 无法启动：</span><span class="sxs-lookup"><span data-stu-id="2b909-107">If your HoloLens won't start:</span></span>

- <span data-ttu-id="2b909-108">如果电源按钮旁边的 LED 不亮，或只有一个 LED 短暂闪烁，可能需要为 [HoloLens 充电。](hololens-recovery.md#charge-the-device)</span><span class="sxs-lookup"><span data-stu-id="2b909-108">If the LEDs next to the power button don't light up, or only one LED briefly blinks, you may need to [charge your HoloLens.](hololens-recovery.md#charge-the-device)</span></span>
- <span data-ttu-id="2b909-109">如果在按下电源按钮时，LED 会打开，但你在显示器上看不到任何内容，请预先设置设备的硬[重置。](hololens-recovery.md#hard-reset-procedure)</span><span class="sxs-lookup"><span data-stu-id="2b909-109">If the LEDs light up when you press the power button but you can't see anything on the displays, [preform a hard reset of the device](hololens-recovery.md#hard-reset-procedure).</span></span>

<span data-ttu-id="2b909-110">如果你的 HoloLens 冻结或无响应：</span><span class="sxs-lookup"><span data-stu-id="2b909-110">If your HoloLens becomes frozen or unresponsive:</span></span>

- <span data-ttu-id="2b909-111">按电源按钮关闭 HoloLens，直到所有五个 LED 自行关闭，或者如果 LED 无响应，则关闭 15 秒。</span><span class="sxs-lookup"><span data-stu-id="2b909-111">Turn off your HoloLens by pressing the power button until all five of the LEDs turn themselves off, or for 15 seconds if the LEDs are unresponsive.</span></span> <span data-ttu-id="2b909-112">若要启动 HoloLens，请再次按电源按钮。</span><span class="sxs-lookup"><span data-stu-id="2b909-112">To start your HoloLens, press the power button again.</span></span>

<span data-ttu-id="2b909-113">如果这些步骤不起作用，可以尝试恢复 [HoloLens 2](hololens-recovery.md) 设备或 [HoloLens (第一代) 设备。](hololens1-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="2b909-113">If these steps don't work, you can try [recovering your HoloLens 2 device](hololens-recovery.md) or [HoloLens (1st gen) device.](hololens1-recovery.md)</span></span>

## <span data-ttu-id="2b909-114">全息影像看起来不良好</span><span class="sxs-lookup"><span data-stu-id="2b909-114">Holograms don't look good</span></span>

<span data-ttu-id="2b909-115">如果你的全息影像不稳定、跳转或看起来不对，请尝试：</span><span class="sxs-lookup"><span data-stu-id="2b909-115">If your holograms are unstable, jumpy, or don't look right, try:</span></span>

- <span data-ttu-id="2b909-116">清理 HoloLens 前端的设备面罩和传感器栏。</span><span class="sxs-lookup"><span data-stu-id="2b909-116">Cleaning your device visor and sensor bar on the front of your HoloLens.</span></span>
- <span data-ttu-id="2b909-117">增加房间的光线。</span><span class="sxs-lookup"><span data-stu-id="2b909-117">Increasing the light in your room.</span></span>
- <span data-ttu-id="2b909-118">四处移动并查看周围环境，以便 HoloLens 可以更彻底地扫描它们。</span><span class="sxs-lookup"><span data-stu-id="2b909-118">Walking around and looking at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="2b909-119">为眼睛校准 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="2b909-119">Calibrating your HoloLens for your eyes.</span></span> <span data-ttu-id="2b909-120">转到 **"设置**  >  **系统**  >  **实用程序"。**</span><span class="sxs-lookup"><span data-stu-id="2b909-120">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="2b909-121">在“**校准**”下，选择“**打开校准**”。</span><span class="sxs-lookup"><span data-stu-id="2b909-121">Under **Calibration**, select **Open Calibration**.</span></span>
 
### <span data-ttu-id="2b909-122">报告全息影像不稳定或看起来不对的问题</span><span class="sxs-lookup"><span data-stu-id="2b909-122">Reporting issues where Holograms are unstable or don't look right</span></span>
 
1. <span data-ttu-id="2b909-123">请录制此问题 [的混合现实](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 捕获视频。</span><span class="sxs-lookup"><span data-stu-id="2b909-123">Please record and a [Mixed Reality Capture video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) of the issue.</span></span> <span data-ttu-id="2b909-124">此视频稍后可通过反馈中心作为附加文件上载。</span><span class="sxs-lookup"><span data-stu-id="2b909-124">This video can be later uploaded through Feedback Hub as an attached file.</span></span>  
1. <span data-ttu-id="2b909-125">通过"设置"应用->**隐私**诊断&反馈和可选诊断数据下启用完整遥测\*\*\*\*，确保将切换  ->  \*\*\*\* 设置为 **"打开"** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2b909-125">Enable full telemetry via the **Settings** app -> **Privacy** -> **Diagnostics & feedback** and under **Optional diagnostics data** ensure the toggle is set to **On**</span></span>
1. <span data-ttu-id="2b909-126">通过更新到最新的 Windows 全息操作系统（ ([20H2 ](hololens-release-notes.md#windows-holographic-version-20h2)或更高版本）获取最新的全息影像缩放和稳定性) 。</span><span class="sxs-lookup"><span data-stu-id="2b909-126">Get the latest hologram scale and stability fixes by updating to the latest [Windows Holographic OS, (20H2 or higher)](hololens-release-notes.md#windows-holographic-version-20h2).</span></span> <span data-ttu-id="2b909-127">更新后，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="2b909-127">After updating perform the following:</span></span>
    1. <span data-ttu-id="2b909-128">通过"设置 **"应用**->**系统**全息影像 ->删除所有全息影像，然后选择"删除所有全息影像"，然后从  ->  \*\*\*\* 全新的地图开始。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="2b909-128">Remove all Holograms via **Settings** app -> **System** -> **Holograms** -> then select **Remove all holograms** and start with a fresh map.</span></span>
    1. <span data-ttu-id="2b909-129">通过佩戴 HoloLens 并四处走来走来，并查看空间中的所有区域与表面，创建空间的新地图。</span><span class="sxs-lookup"><span data-stu-id="2b909-129">Create a new map of your space by wearing the HoloLens and walking around your room and looking at all areas and surfaces in the space.</span></span> <span data-ttu-id="2b909-130">此操作需要 2-3 分钟。</span><span class="sxs-lookup"><span data-stu-id="2b909-130">Do this for 2-3 minutes.</span></span>
    1. <span data-ttu-id="2b909-131">执行 IPD 校准。</span><span class="sxs-lookup"><span data-stu-id="2b909-131">Perform IPD calibration.</span></span> <span data-ttu-id="2b909-132">转到 **"设置**  >  **系统**  >  **实用程序"。**</span><span class="sxs-lookup"><span data-stu-id="2b909-132">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="2b909-133">在“**校准**”下，选择“**打开校准**”。</span><span class="sxs-lookup"><span data-stu-id="2b909-133">Under **Calibration**, select **Open Calibration**.</span></span>
    1. <span data-ttu-id="2b909-134">重新测试方案，并查看它是否仍然保留。</span><span class="sxs-lookup"><span data-stu-id="2b909-134">Re-test the scenario and see if it still persists.</span></span>
1. <span data-ttu-id="2b909-135">如果更新未修复该问题，请提交反馈 [中心问题](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="2b909-135">If updating does not fix the issue, please file a [Feedback Hub issue](hololens-feedback.md).</span></span> <span data-ttu-id="2b909-136">填写反馈后，可以使用"共享"按钮创建\*\*\*\* 一个可在联系支持人员时发送的轻松共享链接。</span><span class="sxs-lookup"><span data-stu-id="2b909-136">After you've filled feedback you can use the **Share** button, to create an easy to share link that can be sent when contacting support.</span></span>

## <span data-ttu-id="2b909-137">HoloLens 不响应手输入</span><span class="sxs-lookup"><span data-stu-id="2b909-137">HoloLens doesn't respond to hand input</span></span>

<span data-ttu-id="2b909-138">若要确保 HoloLens 可以看到你的手，你需要将它们放在手势框架中。</span><span class="sxs-lookup"><span data-stu-id="2b909-138">To ensure that HoloLens can see your hands, you need to keep them in the gesture frame.</span></span>  <span data-ttu-id="2b909-139">混合现实主页提供反馈，可让你了解何时跟踪手。</span><span class="sxs-lookup"><span data-stu-id="2b909-139">The Mixed Reality Home provides feedback that lets you know when your hands are tracked.</span></span>  <span data-ttu-id="2b909-140">不同版本的 HoloLens 的反馈不同：</span><span class="sxs-lookup"><span data-stu-id="2b909-140">The feedback is different on different versions of HoloLens:</span></span>
- <span data-ttu-id="2b909-141">在 HoloLens (第一代) 上，凝视光标从一个点变为一个圈</span><span class="sxs-lookup"><span data-stu-id="2b909-141">On HoloLens (1st gen), the gaze cursor changes from a dot to a ring</span></span>
- <span data-ttu-id="2b909-142">在 HoloLens 2 上，当手靠近平板电脑时，会出现指尖光标，当平板电脑离得更近时会出现手部光线</span><span class="sxs-lookup"><span data-stu-id="2b909-142">On HoloLens 2, a fingertip cursor appears when your hand is close to a slate, and a hand ray appears when slates are further away</span></span>

<span data-ttu-id="2b909-143">许多沉浸式应用遵循与混合现实家庭类似的输入模式。</span><span class="sxs-lookup"><span data-stu-id="2b909-143">Many immersive apps follow input patterns that are similar to Mixed Reality Home.</span></span>  <span data-ttu-id="2b909-144">了解有关在 [HoloLens ](hololens1-basic-usage.md#use-hololens-with-your-hands) 第一代 (和 [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame)) 手输入。</span><span class="sxs-lookup"><span data-stu-id="2b909-144">Learn more about using hand input on [HoloLens (1st gen)](hololens1-basic-usage.md#use-hololens-with-your-hands) and [HoloLens 2](hololens2-basic-usage.md#the-hand-tracking-frame).</span></span>

<span data-ttu-id="2b909-145">如果你是一只手风，请注意某些类型的便笺不能用于手部跟踪。</span><span class="sxs-lookup"><span data-stu-id="2b909-145">If you are wearing gloves, note that some types of gloves do not work with hand tracking.</span></span>  <span data-ttu-id="2b909-146">一个常见示例是黑色橡皮手套，它们倾向于吸收红外光，而深度相机不会选取它们。</span><span class="sxs-lookup"><span data-stu-id="2b909-146">A common example is black rubber gloves, which tend to absorb infrared light and are not picked up by the depth camera.</span></span>  <span data-ttu-id="2b909-147">如果你的工作涉及橡皮戳，我们建议尝试较浅的颜色，如蓝色或灰色。</span><span class="sxs-lookup"><span data-stu-id="2b909-147">If your work involves rubber gloves, we recommend trying a lighter color such as blue or gray.</span></span>  <span data-ttu-id="2b909-148">另一个示例是大包袋，它们通常会遮盖手的形状。</span><span class="sxs-lookup"><span data-stu-id="2b909-148">Another example is large baggy gloves, which tend to obscure the shape of your hand.</span></span> <span data-ttu-id="2b909-149">我们建议使用尽可能适合外形的防护线，以获得最佳效果。</span><span class="sxs-lookup"><span data-stu-id="2b909-149">We recommend using gloves that are as form-fitting as possible for best results.</span></span>

<span data-ttu-id="2b909-150">如果你的面罩有指纹或毛毛，请使用 HoloLens 中随其一起清理面罩的微细纸来清理面罩。</span><span class="sxs-lookup"><span data-stu-id="2b909-150">If your visor has fingerprints or smudges, use the microfiber cleaning cloth that came with the HoloLens to clean your visor gently.</span></span>

## <span data-ttu-id="2b909-151">HoloLens 不响应我的语音命令</span><span class="sxs-lookup"><span data-stu-id="2b909-151">HoloLens doesn't respond to my voice commands</span></span>

<span data-ttu-id="2b909-152">如果 Cortana 未响应语音命令，请确保 Cortana 已打开。</span><span class="sxs-lookup"><span data-stu-id="2b909-152">If Cortana isn't responding to your voice commands, make sure Cortana is turned on.</span></span> <span data-ttu-id="2b909-153">在"所有应用"列表中，选择**Cortana**  >  **菜单**  >  **笔记本**  >  **设置**以进行更改。</span><span class="sxs-lookup"><span data-stu-id="2b909-153">On the All apps list, select **Cortana** > **Menu** > **Notebook** > **Settings** to make changes.</span></span> <span data-ttu-id="2b909-154">若要了解有关可以说出的内容的详细信息，请参阅[使用语音操作 HoloLens](hololens-cortana.md)。</span><span class="sxs-lookup"><span data-stu-id="2b909-154">To learn more about what you can say, see [Use your voice with HoloLens](hololens-cortana.md).</span></span>

## <span data-ttu-id="2b909-155">我无法放置全息影像或查看之前放置的全息影像</span><span class="sxs-lookup"><span data-stu-id="2b909-155">I can't place holograms or see holograms that I previously placed</span></span>

<span data-ttu-id="2b909-156">如果 HoloLens 无法映射或加载你的空间，它将进入受限模式，你将无法放置全息影像或查看你放置的全息影像。</span><span class="sxs-lookup"><span data-stu-id="2b909-156">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="2b909-157">你可以尝试以下操作：</span><span class="sxs-lookup"><span data-stu-id="2b909-157">Here are some things to try:</span></span>

- <span data-ttu-id="2b909-158">请确保你的环境中有足够的光，以便 HoloLens 可以看到和映射空间。</span><span class="sxs-lookup"><span data-stu-id="2b909-158">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="2b909-159">确保你已连接到Wi-Fi网络。</span><span class="sxs-lookup"><span data-stu-id="2b909-159">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="2b909-160">如果未连接到 WLAN，HoloLens 无法识别并加载已知空间。</span><span class="sxs-lookup"><span data-stu-id="2b909-160">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="2b909-161">如果你需要创建新空间，请连接到 WLAN，然后重启 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="2b909-161">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="2b909-162">若要查看正确的空间是否处于活动状态，或手动加载空格，请转到"**设置**  >  **系统**  >  **空间"。**</span><span class="sxs-lookup"><span data-stu-id="2b909-162">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="2b909-163">如果加载了正确的空间，但您仍有问题，则空间可能已损坏。</span><span class="sxs-lookup"><span data-stu-id="2b909-163">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="2b909-164">若要解决此问题，请选择空格，然后选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="2b909-164">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="2b909-165">删除空间后，HoloLens 将开始映射你的周围环境并创建新空间。</span><span class="sxs-lookup"><span data-stu-id="2b909-165">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

## <span data-ttu-id="2b909-166">我的 HoloLens 无法告诉我在什么空间</span><span class="sxs-lookup"><span data-stu-id="2b909-166">My HoloLens can't tell what space I'm in</span></span>

<span data-ttu-id="2b909-167">如果你的 HoloLens 无法自动标识和加载你的空间，请检查以下因素：</span><span class="sxs-lookup"><span data-stu-id="2b909-167">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="2b909-168">确保你已连接到Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="2b909-168">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="2b909-169">确保房间中有足够的光</span><span class="sxs-lookup"><span data-stu-id="2b909-169">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="2b909-170">确保周围没有发生任何重大更改。</span><span class="sxs-lookup"><span data-stu-id="2b909-170">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="2b909-171">还可以手动加载空间，或通过进入"设置系统空间"\*\*\*\*  >  **管理**  >  **空间**。</span><span class="sxs-lookup"><span data-stu-id="2b909-171">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

## <span data-ttu-id="2b909-172">我收到"磁盘空间不足"错误</span><span class="sxs-lookup"><span data-stu-id="2b909-172">I'm getting a "low disk space" error</span></span>

<span data-ttu-id="2b909-173">你需要通过执行以下一项或多项操作来释放一些存储空间：</span><span class="sxs-lookup"><span data-stu-id="2b909-173">You'll need to free up some storage space by doing one or more of the following:</span></span>

- <span data-ttu-id="2b909-174">删除一些未使用的空格。</span><span class="sxs-lookup"><span data-stu-id="2b909-174">Delete some unused spaces.</span></span> <span data-ttu-id="2b909-175">转到 **"设置**系统空间"，选择不再需要的空格，  >  \*\*\*\*  >  \*\*\*\* 然后选择"**删除"。**</span><span class="sxs-lookup"><span data-stu-id="2b909-175">Go to **Settings** > **System** > **Spaces**, select a space that you no longer need, and then select **Remove**.</span></span>
- <span data-ttu-id="2b909-176">删除你放置的一些全息影像。</span><span class="sxs-lookup"><span data-stu-id="2b909-176">Remove some of the holograms that you've placed.</span></span>
- <span data-ttu-id="2b909-177">从"照片"应用中删除一些图片和视频。</span><span class="sxs-lookup"><span data-stu-id="2b909-177">Delete some pictures and videos from the Photos app.</span></span>
- <span data-ttu-id="2b909-178">从 HoloLens 中卸载某些应用。</span><span class="sxs-lookup"><span data-stu-id="2b909-178">Uninstall some apps from your HoloLens.</span></span> <span data-ttu-id="2b909-179">在 **"所有应用"** 列表中，点击并按住要卸载的应用，然后选择"**卸载"。**</span><span class="sxs-lookup"><span data-stu-id="2b909-179">In the **All apps** list, tap and hold the app you want to uninstall, and then select **Uninstall**.</span></span>

## <span data-ttu-id="2b909-180">我的 HoloLens 无法创建新空间</span><span class="sxs-lookup"><span data-stu-id="2b909-180">My HoloLens can't create a new space</span></span>

<span data-ttu-id="2b909-181">最可能的问题是存储空间不足。</span><span class="sxs-lookup"><span data-stu-id="2b909-181">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="2b909-182">请尝试使用前面的 [提示之](#im-getting-a-low-disk-space-error) 一释放一些磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="2b909-182">Try one of the [previous tips](#im-getting-a-low-disk-space-error) to free up some disk space.</span></span>

## <span data-ttu-id="2b909-183">HoloLens 仿真器无法工作</span><span class="sxs-lookup"><span data-stu-id="2b909-183">The HoloLens emulator isn't working</span></span>

<span data-ttu-id="2b909-184">有关 HoloLens 仿真器的信息，请参阅我们的开发人员文档。</span><span class="sxs-lookup"><span data-stu-id="2b909-184">Information about the HoloLens emulator is located in our developer documentation.</span></span>  <span data-ttu-id="2b909-185">阅读有关 [HoloLens 仿真器疑难解答的更多信息](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting)。</span><span class="sxs-lookup"><span data-stu-id="2b909-185">Read more about [troubleshooting the HoloLens emulator](https://docs.microsoft.com/windows/mixed-reality/using-the-hololens-emulator#troubleshooting).</span></span>
