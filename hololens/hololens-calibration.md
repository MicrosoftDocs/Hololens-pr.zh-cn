---
title: 改善视觉质量和舒适度
description: 了解如何校准瞳孔间距 (IPD)，以改善 HoloLens 设备上的视觉效果。
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
keywords: 校准, 舒适, 视觉对象, 质量, ipd, HoloLens, Windows Mixed Reality, VR 头戴显示设备
ms.openlocfilehash: 62d83aa5c6032d15b26fbc7938859bdaf74151f4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924139"
---
# <a name="improve-visual-quality-and-comfort"></a><span data-ttu-id="d2f86-104">改善视觉质量和舒适度</span><span class="sxs-lookup"><span data-stu-id="d2f86-104">Improve visual quality and comfort</span></span>

<span data-ttu-id="d2f86-105">在根据你自己的瞳距校准 HoloLens 2 和 HoloLens（第一代）后，体验效果会更好。</span><span class="sxs-lookup"><span data-stu-id="d2f86-105">HoloLens 2 and HoloLens (1st gen) both work better when they're calibrated to your unique eyes.</span></span>

<span data-ttu-id="d2f86-106">虽然两种设备都需要通过校准才能带来最佳的全息图观看体验，但它们所用的校准技术不同。</span><span class="sxs-lookup"><span data-stu-id="d2f86-106">While both devices need to calibrate for the best hologram viewing experience, they use different calibration technologies and techniques.</span></span>  <span data-ttu-id="d2f86-107">跳转到 [HoloLens 2 校准](#calibrating-your-hololens-2)或 [HoloLens（第一代）校准](#calibrating-your-hololens-1st-gen)。</span><span class="sxs-lookup"><span data-stu-id="d2f86-107">Jump to [HoloLens 2 calibration](#calibrating-your-hololens-2) or [HoloLens (1st gen) calibration](#calibrating-your-hololens-1st-gen).</span></span>

## <a name="calibrating-your-hololens-2"></a><span data-ttu-id="d2f86-108">校准 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="d2f86-108">Calibrating your HoloLens 2</span></span>

<span data-ttu-id="d2f86-109">HoloLens 2 使用眼球跟踪技术来改善你观看虚拟环境以及与虚拟环境互动的体验。</span><span class="sxs-lookup"><span data-stu-id="d2f86-109">HoloLens 2 uses eye-tracking technology to improve your experience seeing and interacting with the virtual environment.</span></span> <span data-ttu-id="d2f86-110">校准 HoloLens 2 可确保它能够准确地跟踪你的眼球（以及使用该设备的其他人的眼球）。</span><span class="sxs-lookup"><span data-stu-id="d2f86-110">Calibrating the HoloLens 2 ensures that it can accurately track your eyes (and the eyes of anyone else who uses the device).</span></span> <span data-ttu-id="d2f86-111">此外，它还有助于提高用户舒适度、进行全息影像对齐和实现手部跟踪。</span><span class="sxs-lookup"><span data-stu-id="d2f86-111">It also helps with user comfort, hologram alignment, and hand tracking.</span></span> <span data-ttu-id="d2f86-112">校准后，会正确显示全息图，即使面罩在你的头上移动时也是如此。</span><span class="sxs-lookup"><span data-stu-id="d2f86-112">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

<span data-ttu-id="d2f86-113">在下列情况中，HoloLens 2 会提示用户校准设备：</span><span class="sxs-lookup"><span data-stu-id="d2f86-113">HoloLens 2 prompts a user to calibrate the device under the following circumstances:</span></span>

- <span data-ttu-id="d2f86-114">用户首次使用设备</span><span class="sxs-lookup"><span data-stu-id="d2f86-114">The user is using the device for the first time</span></span>
- <span data-ttu-id="d2f86-115">用户之前选择退出校准过程</span><span class="sxs-lookup"><span data-stu-id="d2f86-115">The user previously opted out of the calibration process</span></span>
- <span data-ttu-id="d2f86-116">用户上次使用设备时校准过程不成功</span><span class="sxs-lookup"><span data-stu-id="d2f86-116">The calibration process didn't succeed the last time the user used the device</span></span>
- <span data-ttu-id="d2f86-117">用户已删除其校准配置文件</span><span class="sxs-lookup"><span data-stu-id="d2f86-117">The user has deleted their calibration profiles</span></span>
- <span data-ttu-id="d2f86-118">设备将被关闭并重新打开，且上述任何情况都适用</span><span class="sxs-lookup"><span data-stu-id="d2f86-118">The device is taken off and puts back on and any of the above circumstances apply</span></span> 


![调整到眼部的校准提示。](./images/07-et-adjust-for-your-eyes.png)

<span data-ttu-id="d2f86-120">在此过程中，你需要注视一组目标（宝石）。</span><span class="sxs-lookup"><span data-stu-id="d2f86-120">During this process, you'll look at a set of targets (gems).</span></span> <span data-ttu-id="d2f86-121">校准期间，你可以眨眼，但请尽量把注意力集中在宝石上，而不是盯着房间中的其他对象。</span><span class="sxs-lookup"><span data-stu-id="d2f86-121">It's fine if you blink during calibration, but try to stay focused on the gems instead of other objects in the room.</span></span>  <span data-ttu-id="d2f86-122">通过专注于这些宝石，HoloLens 可以了解你的眼部位置，以呈现全息世界。</span><span class="sxs-lookup"><span data-stu-id="d2f86-122">Focusing on the gems allows HoloLens to learn about your eye position to render your holographic world.</span></span>

![校准提示告诉用户保持头部静止不动并用眼睛跟随点。](./images/07-et-hold-head-still.png)

![带有 gem 示例的校准提示。](./images/08-et-gems.png)

![校准提示调整。](./images/09-et-adjusting.png)

<span data-ttu-id="d2f86-126">如果校准成功，你将看到一个成功屏幕。</span><span class="sxs-lookup"><span data-stu-id="d2f86-126">If calibration was successful, you'll see a success screen.</span></span>  <span data-ttu-id="d2f86-127">如果没有，请阅读有关[诊断校准失败](hololens2-display.md#troubleshooting)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d2f86-127">If not, read more about [diagnosing calibration failures](hololens2-display.md#troubleshooting).</span></span>

![校准提示成功。](./images/10-et-success.png)

### <a name="calibration-when-sharing-a-device-or-session"></a><span data-ttu-id="d2f86-129">共享设备或会话时校准</span><span class="sxs-lookup"><span data-stu-id="d2f86-129">Calibration when sharing a device or session</span></span>

<span data-ttu-id="d2f86-130">多个用户可以共用一台 HoloLens 2 设备，但不需要每个人都走一遍设备设置流程。</span><span class="sxs-lookup"><span data-stu-id="d2f86-130">Multiple users can share a HoloLens 2 device, without a need for each person to go through device setup.</span></span> <span data-ttu-id="d2f86-131">当新的用户首次将设备戴在头上时，HoloLens 2 会自动提示该用户进行视觉对象校准。</span><span class="sxs-lookup"><span data-stu-id="d2f86-131">When a new user puts the device on their head for the first time, HoloLens 2 automatically prompts the user to calibrate visuals.</span></span> <span data-ttu-id="d2f86-132">当之前校准过视觉对象的用户再次将设备戴在头上时，显示屏可无缝调整，为其提供高质量的舒适观看体验。</span><span class="sxs-lookup"><span data-stu-id="d2f86-132">When a user that has previously calibrated visuals puts the device on their head, the display seamlessly adjusts for quality and a comfortable viewing experience.</span></span>  

### <a name="manually-starting-the-calibration-process"></a><span data-ttu-id="d2f86-133">手动启动校准过程</span><span class="sxs-lookup"><span data-stu-id="d2f86-133">Manually starting the calibration process</span></span>

1. <span data-ttu-id="d2f86-134">使用开始手势打开[“开始”菜单](hololens2-basic-usage.md#start-gesture)。</span><span class="sxs-lookup"><span data-stu-id="d2f86-134">Use the start gesture to open the [**Start** menu](hololens2-basic-usage.md#start-gesture).</span></span>
1. <span data-ttu-id="d2f86-135">如果设置应用未固定到“开始”，请选择“所有应用”。</span><span class="sxs-lookup"><span data-stu-id="d2f86-135">If the Settings app isn't pinned to **Start**, select **All Apps**.</span></span>
1. <span data-ttu-id="d2f86-136">选择“设置”，然后选择“系统” > “校准” > “眼部校准” > “运行眼部校准”。</span><span class="sxs-lookup"><span data-stu-id="d2f86-136">Select **Settings**, and then select **System** > **Calibration** > **Eye Calibration** > **Run eye calibration**.</span></span>

   ![“设置”应用，显示“运行眼部校准”选项](./images/C-Settings.Calibration.png)

### <a name="auto-eye-position-support"></a><span data-ttu-id="d2f86-138">自动眼部位置支持</span><span class="sxs-lookup"><span data-stu-id="d2f86-138">Auto Eye Position Support</span></span>

<span data-ttu-id="d2f86-139">在 HoloLens 2 中，眼部位置可实现准确的全息影像定位、舒适的观看体验和改进的显示质量。</span><span class="sxs-lookup"><span data-stu-id="d2f86-139">In HoloLens 2, eye positions enable accurate hologram positioning, comfortable viewing experience, and improved display quality.</span></span> <span data-ttu-id="d2f86-140">眼部位置在内部计算，作为眼球跟踪计算的一部分。</span><span class="sxs-lookup"><span data-stu-id="d2f86-140">Eye positions are computed internally as part of the eye tracking computation.</span></span> <span data-ttu-id="d2f86-141">但是，这要求每个用户都可以通过眼球跟踪校准，即使体验可能不需要眼睛凝视输入也是如此。</span><span class="sxs-lookup"><span data-stu-id="d2f86-141">However, this requires each user to go through eye tracking calibration, even when the experience might not require eye gaze input.</span></span>

<span data-ttu-id="d2f86-142">自动眼部位置 (AEP) 使这些场景能够以无交互方式为用户计算眼部位置。</span><span class="sxs-lookup"><span data-stu-id="d2f86-142">**Auto Eye Position (AEP)** enables these scenarios with an interaction-free way to compute eye positions for the user.</span></span> <span data-ttu-id="d2f86-143">从用户戴上设备开始，“自动眼部位置”将自动在后台开始工作。</span><span class="sxs-lookup"><span data-stu-id="d2f86-143">Auto Eye Position starts working in the background automatically from the moment the user puts on the device.</span></span> <span data-ttu-id="d2f86-144">如果用户没有之前的眼球跟踪校准，“自动眼部位置”将在 20-30 秒的处理时间后开始向显示系统提供用户的眼部位置。</span><span class="sxs-lookup"><span data-stu-id="d2f86-144">If the user doesn't have a prior eye tracking calibration, Auto Eye Position will start providing the user's eye positions to the display system after a processing time of 20 - 30 seconds.</span></span> <span data-ttu-id="d2f86-145">用户数据不会保留在设备上，如果用户取下并重新戴上设备，或者设备重新启动或从睡眠状态唤醒，则会重复此过程。</span><span class="sxs-lookup"><span data-stu-id="d2f86-145">The user data isn't persisted on the device and this process is repeated if the user takes off and puts the device back on or if the device reboots or wakes up from sleep.</span></span>

<span data-ttu-id="d2f86-146">当未经校准的用户戴上设备时，“自动眼部位置”功能会改变一些系统行为。</span><span class="sxs-lookup"><span data-stu-id="d2f86-146">There are a few system behavior changes with Auto Eye Position feature when an uncalibrated user puts on the device.</span></span> <span data-ttu-id="d2f86-147">在这种情况下，未校准的用户指的是之前未在设备上完成眼球跟踪校准过程的人员。</span><span class="sxs-lookup"><span data-stu-id="d2f86-147">In this context, an uncalibrated user refers to someone who hasn't gone through the eye tracking calibration process on the device previously.</span></span>

| <span data-ttu-id="d2f86-148">活动应用程序</span><span class="sxs-lookup"><span data-stu-id="d2f86-148">Active Application</span></span> | <span data-ttu-id="d2f86-149">先前行为</span><span class="sxs-lookup"><span data-stu-id="d2f86-149">Prior Behavior</span></span> | <span data-ttu-id="d2f86-150">Windows 全息版 20H2 更新的行为</span><span class="sxs-lookup"><span data-stu-id="d2f86-150">Behavior from Windows Holographic, version 20H2 Update</span></span> |
|:-------------------|:-----------------|:-----------------------------------|
| <span data-ttu-id="d2f86-151">未启用凝视的应用或全息外壳</span><span class="sxs-lookup"><span data-stu-id="d2f86-151">Non-gaze enabled app or Holographic Shell</span></span> |<span data-ttu-id="d2f86-152">“眼球跟踪校准提示”对话框随即显示。</span><span class="sxs-lookup"><span data-stu-id="d2f86-152">Eye tracking calibration prompt dialog is displayed.</span></span> | <span data-ttu-id="d2f86-153">不显示提示。</span><span class="sxs-lookup"><span data-stu-id="d2f86-153">No prompt is displayed.</span></span> |
| <span data-ttu-id="d2f86-154">启用了凝视的应用</span><span class="sxs-lookup"><span data-stu-id="d2f86-154">Gaze enabled app</span></span> | <span data-ttu-id="d2f86-155">“眼球跟踪校准提示”对话框随即显示。</span><span class="sxs-lookup"><span data-stu-id="d2f86-155">Eye tracking calibration prompt dialog is displayed.</span></span> | <span data-ttu-id="d2f86-156">仅当应用程序访问眼睛凝视流时，才会显示眼球跟踪校准提示。</span><span class="sxs-lookup"><span data-stu-id="d2f86-156">Eye tracking calibration prompt is displayed only when the application accesses eye gaze stream.</span></span> |

<span data-ttu-id="d2f86-157">如果用户从未启用凝视的应用程序转换为访问凝视数据的应用程序，则会显示校准提示。</span><span class="sxs-lookup"><span data-stu-id="d2f86-157">If the user transitions from a non-gaze enabled application to one that accesses the gaze data, the calibration prompt will be displayed.</span></span> 

<span data-ttu-id="d2f86-158">所有其他系统行为将类似于当前用户没有活动的眼球跟踪校准的情况。</span><span class="sxs-lookup"><span data-stu-id="d2f86-158">All other system behavior will be similar to when the current user doesn't have an active eye tracking calibration.</span></span> <span data-ttu-id="d2f86-159">例如，将不会启用单只手的开始手势。</span><span class="sxs-lookup"><span data-stu-id="d2f86-159">For example, the One-handed Start gesture won't be enabled.</span></span> <span data-ttu-id="d2f86-160">初始设置的全新体验不会有任何变化。</span><span class="sxs-lookup"><span data-stu-id="d2f86-160">There will be no change to the Out-Of-Box-Experience for initial setup.</span></span>

<span data-ttu-id="d2f86-161">对于需要眼睛凝视数据或精确的全息影像位置的体验，我们建议未校准的用户运行眼球跟踪校准。</span><span class="sxs-lookup"><span data-stu-id="d2f86-161">For experiences that require eye gaze data or precise hologram positioning, we recommend uncalibrated users to run eye tracking calibration.</span></span> <span data-ttu-id="d2f86-162">可以通过眼球跟踪校准提示或从“开始”菜单启动“设置”应用程序，然后选择“系统”>“校准”>“眼部校准”>“运行眼部校准”。</span><span class="sxs-lookup"><span data-stu-id="d2f86-162">It's accessible from the eye tracking calibration prompt or by launching the Settings app from the start menu, and then selecting **System > Calibration > Eye Calibration > Run eye calibration**.</span></span>

#### <a name="deferred-calibration-prompt"></a><span data-ttu-id="d2f86-163">延期校准提示</span><span class="sxs-lookup"><span data-stu-id="d2f86-163">Deferred Calibration Prompt</span></span>

<span data-ttu-id="d2f86-164">使用自动眼部位置，眼球跟踪校准提示对话框将被推迟，直到应用程序请求眼睛凝视数据。</span><span class="sxs-lookup"><span data-stu-id="d2f86-164">With Auto Eye Position, the Eye Tracking Calibration prompt dialog is deferred until an application requests Eye Gaze data.</span></span> <span data-ttu-id="d2f86-165">这样可以确保当活动应用程序不需要凝视时，不会向用户提示。</span><span class="sxs-lookup"><span data-stu-id="d2f86-165">This ensures that there's no prompt to the user when the active application doesn't require gaze.</span></span> <span data-ttu-id="d2f86-166">如果应用程序确实需要凝视数据，而当前用户没有校准，则会向用户显示校准提示。</span><span class="sxs-lookup"><span data-stu-id="d2f86-166">If the application does require gaze data and the current user isn't calibrated, the user is presented with a calibration prompt.</span></span> <span data-ttu-id="d2f86-167">这种行为可以用来在合适的时间显示眼球跟踪校准提示，有利于体验。</span><span class="sxs-lookup"><span data-stu-id="d2f86-167">This behavior could be used to display eye tracking calibration prompt at a suitable time for the experience.</span></span> <span data-ttu-id="d2f86-168">出于以下原因，建议使用此方法</span><span class="sxs-lookup"><span data-stu-id="d2f86-168">This method is recommended for the following reasons</span></span>

1.  <span data-ttu-id="d2f86-169">“眼球跟踪校准提示”对话框向用户提供了有关为什么需要眼球跟踪的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d2f86-169">The Eye Tracking Calibration Prompt dialog provides the user with details on why eye tracking is needed.</span></span>
2.  <span data-ttu-id="d2f86-170">为用户提供了一种拒绝眼部校准的方法。</span><span class="sxs-lookup"><span data-stu-id="d2f86-170">Presents the user a way to decline to have their eyes calibrated.</span></span>

<span data-ttu-id="d2f86-171">如果用户选择启动“眼球跟踪校准”，校准完成后，焦点应返回到原始应用程序。</span><span class="sxs-lookup"><span data-stu-id="d2f86-171">If the user chooses to launch the Eye Tracking Calibration, the focus should returning to the original application after calibration completes.</span></span> 

### <a name="calibration-data-and-security"></a><span data-ttu-id="d2f86-172">校准数据和安全</span><span class="sxs-lookup"><span data-stu-id="d2f86-172">Calibration data and security</span></span>

<span data-ttu-id="d2f86-173">校准信息本地存储在设备上，与任何帐户信息无关。</span><span class="sxs-lookup"><span data-stu-id="d2f86-173">Calibration information is stored locally on the device and isn't associated with any account information.</span></span> <span data-ttu-id="d2f86-174">使用设备但未校准的用户不会留下记录。</span><span class="sxs-lookup"><span data-stu-id="d2f86-174">There's no record of who has used the device without calibration.</span></span> <span data-ttu-id="d2f86-175">这意味着，当新用户首次使用设备时，系统会提示他们进行视觉对象校准，之前选择退出校准过程或校准不成功的用户也会得到同样提示。</span><span class="sxs-lookup"><span data-stu-id="d2f86-175">This mean new users will get prompted to calibrate visuals when they use the device for the first time, and users who opted out of calibration previously or if calibration was unsuccessful.</span></span>

<span data-ttu-id="d2f86-176">设备可以在本地存储多达 50 个校准配置文件。</span><span class="sxs-lookup"><span data-stu-id="d2f86-176">The device can locally store up to 50 calibration profiles.</span></span> <span data-ttu-id="d2f86-177">达到此数目后，设备将自动删除最早的未用配置文件。</span><span class="sxs-lookup"><span data-stu-id="d2f86-177">After this number is reached, the device automatically deletes the oldest unused profile.</span></span>

<span data-ttu-id="d2f86-178">在“设置” > “隐私声明” > ”眼球跟踪程序”中，始终可以从设备中删除校准信息。</span><span class="sxs-lookup"><span data-stu-id="d2f86-178">Calibration information can always be deleted from the device in **Settings** > **Privacy** > **Eye tracker**.</span></span>  

### <a name="disable-calibration"></a><span data-ttu-id="d2f86-179">禁用校准</span><span class="sxs-lookup"><span data-stu-id="d2f86-179">Disable calibration</span></span>

<span data-ttu-id="d2f86-180">还可以执行以下步骤来禁用校准提示：</span><span class="sxs-lookup"><span data-stu-id="d2f86-180">You can also disable the calibration prompt by following these steps:</span></span>

1. <span data-ttu-id="d2f86-181">选择“设置” > “系统” > “校准”。</span><span class="sxs-lookup"><span data-stu-id="d2f86-181">Select **Settings** > **System** > **Calibration**.</span></span>
1. <span data-ttu-id="d2f86-182">关闭“新用户使用此 HoloLens 时，自动要求运行眼部校准”。</span><span class="sxs-lookup"><span data-stu-id="d2f86-182">Turn off **When a new person uses this HoloLens, automatically ask to run eye calibration**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d2f86-183">此设置可能对全息影像呈现质量和舒适度产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="d2f86-183">This setting may adversely affect hologram rendering quality and comfort.</span></span>  <span data-ttu-id="d2f86-184">关闭此设置时，依赖于眼球跟踪的功能（如文本滚动）在沉浸式应用程序中将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="d2f86-184">When you turn off this setting, features that depend on eye tracking (such as text scrolling) no longer work in immersive applications.</span></span>

### <a name="hololens-2-eye-tracking-technology"></a><span data-ttu-id="d2f86-185">HoloLens 2 眼球跟踪技术</span><span class="sxs-lookup"><span data-stu-id="d2f86-185">HoloLens 2 eye-tracking technology</span></span>

<span data-ttu-id="d2f86-186">该设备使用眼球跟踪技术来提高显示质量，同时确保所有全息图放置准确、在 3D 模式下观看起来更舒适。</span><span class="sxs-lookup"><span data-stu-id="d2f86-186">The device uses its eye-tracking technology to improve display quality, and to ensure that all holograms are positioned accurately and comfortable to view in 3D.</span></span> <span data-ttu-id="d2f86-187">因为它将眼睛作为地标，所以设备可以针对每个用户自我调整，并随着头戴显示设备在整个使用过程中轻微地移动调整视觉对象。</span><span class="sxs-lookup"><span data-stu-id="d2f86-187">Because it uses the eyes as landmarks, the device can adjust itself for every user and tune its visuals as the headset shifts slightly throughout use.</span></span>  <span data-ttu-id="d2f86-188">所有调整都自动完成，无需手动介入。</span><span class="sxs-lookup"><span data-stu-id="d2f86-188">All adjustments happen on the fly without a need for manual tuning.</span></span>
> [!NOTE]
> <span data-ttu-id="d2f86-189">设置 IPD 不适用于 Hololens 2，因为眼部位置是由系统计算的。</span><span class="sxs-lookup"><span data-stu-id="d2f86-189">Setting the IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span>

<span data-ttu-id="d2f86-190">HoloLens 应用程序使用眼球跟踪技术来实时跟踪你注视的地方。</span><span class="sxs-lookup"><span data-stu-id="d2f86-190">HoloLens applications use eye tracking to track where you're looking in real time.</span></span> <span data-ttu-id="d2f86-191">这是开发人员可以使用来实现全息体验中全新水平的上下文、人类理解和互动的主要技术。</span><span class="sxs-lookup"><span data-stu-id="d2f86-191">This is the main capability developers can use to enable a whole new level of context, human understanding, and interactions within the Holographic experience.</span></span> <span data-ttu-id="d2f86-192">开发人员无需进行任何操作就可以使用此功能。</span><span class="sxs-lookup"><span data-stu-id="d2f86-192">Developers don’t need to do anything to use this capability.</span></span>

## <a name="calibrating-your-hololens-1st-gen"></a><span data-ttu-id="d2f86-193">校准你的 HoloLens（第一代）</span><span class="sxs-lookup"><span data-stu-id="d2f86-193">Calibrating your HoloLens (1st gen)</span></span>

<span data-ttu-id="d2f86-194">HoloLens（第一代）根据[瞳孔间距](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD) 调整全息影像显示。</span><span class="sxs-lookup"><span data-stu-id="d2f86-194">HoloLens (1st gen) adjusts hologram display according to your [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD).</span></span> <span data-ttu-id="d2f86-195">如果 IPD 不准确，全息图可能显示不稳定或距离不正确。</span><span class="sxs-lookup"><span data-stu-id="d2f86-195">If the IPD isn't accurate, holograms may appear unstable or at an incorrect distance.</span></span> <span data-ttu-id="d2f86-196">根据你的瞳距 (IPD) 来校准设备可以提高视觉对象的质量。</span><span class="sxs-lookup"><span data-stu-id="d2f86-196">You can improve the quality of your visuals by calibrating the device to your interpupillary distance (IPD).</span></span>

<span data-ttu-id="d2f86-197">在设置 Hololens（第一代）设备时，当 Cortana 作完自我介绍后，系统会提示你进行视觉对象校准。</span><span class="sxs-lookup"><span data-stu-id="d2f86-197">When you set up your HoloLens (1st gen) device, it prompts to calibrate your visuals after Cortana introduces herself.</span></span> <span data-ttu-id="d2f86-198">建议在此设置阶段完成校准步骤。</span><span class="sxs-lookup"><span data-stu-id="d2f86-198">It's recommended that you complete the calibration step during this setup phase.</span></span> <span data-ttu-id="d2f86-199">不过，你也可以跳过这一步，只要在 Cortana 提示你时，你说“跳过”即可。</span><span class="sxs-lookup"><span data-stu-id="d2f86-199">However you can skip it by waiting until Cortana prompts you and then saying "Skip."</span></span>

<span data-ttu-id="d2f86-200">在校准过程中，HoloLens 会要求你将手指与每只眼睛注视的六个目标对齐。</span><span class="sxs-lookup"><span data-stu-id="d2f86-200">During the calibration process, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="d2f86-201">HoloLens 使用此过程为眼睛正确设置 IPD。</span><span class="sxs-lookup"><span data-stu-id="d2f86-201">HoloLens uses this process to set the IPD correctly for your eyes.</span></span>

![第二步中的 IPD 手指对齐屏幕](./images/ipd-finger-alignment-300px.jpg)

### <a name="manually-start-the-calibration-process"></a><span data-ttu-id="d2f86-203">手动启动校准过程</span><span class="sxs-lookup"><span data-stu-id="d2f86-203">Manually start the calibration process</span></span>

<span data-ttu-id="d2f86-204">如果你需要更新校准，或者新的用户需要调整校准，都可以随时手动运行“校准”应用。</span><span class="sxs-lookup"><span data-stu-id="d2f86-204">If you need to update the calibration or if a new user needs to adjust it, you can manually run the Calibration app at any time.</span></span> <span data-ttu-id="d2f86-205">默认情况下安装“校准”应用。</span><span class="sxs-lookup"><span data-stu-id="d2f86-205">The Calibration app is installed by default.</span></span> <span data-ttu-id="d2f86-206">要访问该应用，可以通过“开始”菜单或“设置”应用。</span><span class="sxs-lookup"><span data-stu-id="d2f86-206">You can access it by using either the **Start** menu or the Settings app.</span></span>

<span data-ttu-id="d2f86-207">要通过“开始”菜单运行“校准”应用，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d2f86-207">To use the **Start** menu to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="d2f86-208">使用[开花](hololens1-basic-usage.md)手势打开“开始”菜单。</span><span class="sxs-lookup"><span data-stu-id="d2f86-208">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="d2f86-209">要查看所有应用，请选择“+”。</span><span class="sxs-lookup"><span data-stu-id="d2f86-209">To view all apps, select **+**.</span></span>
1. <span data-ttu-id="d2f86-210">选择“校准”。</span><span class="sxs-lookup"><span data-stu-id="d2f86-210">Select **Calibration**.</span></span>

![从 shell 访问“校准”应用](./images/calibration-shell.png)

![“校准”应用启动后显示为一个活动立方体](./images/calibration-livecube-200px.png)

<span data-ttu-id="d2f86-213">要通过“设置”应用来运行“校准”应用，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d2f86-213">To use the Settings app to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="d2f86-214">使用[开花](hololens1-basic-usage.md)手势打开“开始”菜单。</span><span class="sxs-lookup"><span data-stu-id="d2f86-214">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="d2f86-215">如果“设置”未固定到“开始”，请选择“+”查看所有应用。</span><span class="sxs-lookup"><span data-stu-id="d2f86-215">If **Settings** isn't pinned to **Start**, select **+** to view all apps.</span></span>
1. <span data-ttu-id="d2f86-216">选择“设置”。</span><span class="sxs-lookup"><span data-stu-id="d2f86-216">Select **Settings**.</span></span>
1. <span data-ttu-id="d2f86-217">选择“系统” > “实用工具” > “打开校准”。</span><span class="sxs-lookup"><span data-stu-id="d2f86-217">Select **System** > **Utilities** > **Open Calibration**.</span></span>

![从“设置”应用启动“校准”应用](./images/calibration-settings-500px.jpg)

## <a name="immersive-headsets"></a><span data-ttu-id="d2f86-219">沉浸式头戴显示设备</span><span class="sxs-lookup"><span data-stu-id="d2f86-219">Immersive headsets</span></span>

<span data-ttu-id="d2f86-220">某些沉浸式头戴显示设备提供自定义 IPD 设置的功能。</span><span class="sxs-lookup"><span data-stu-id="d2f86-220">Some immersive headsets provide the ability to customize the IPD setting.</span></span> <span data-ttu-id="d2f86-221">若要更改头戴显示设备的 IPD，请打开设置应用，选择“混合现实” > “头戴显示设备显示”，然后移动滑块控件。</span><span class="sxs-lookup"><span data-stu-id="d2f86-221">To change the IPD for your headset, open the Settings app and select **Mixed reality** > **Headset display**, and then move the slider control.</span></span> <span data-ttu-id="d2f86-222">你将在头戴显示设备中看到实时变化。</span><span class="sxs-lookup"><span data-stu-id="d2f86-222">You’ll see the changes in real time in your headset.</span></span> <span data-ttu-id="d2f86-223">如果你知道自己的 IPD（可能是从验光师那里得知），可以直接输入它。</span><span class="sxs-lookup"><span data-stu-id="d2f86-223">If you know your IPD, maybe from a visit to the optometrist, you can enter it directly as well.</span></span>

<span data-ttu-id="d2f86-224">还可以通过选择“设置” > “混合现实” > “头戴显示设备显示”来在电脑上调整此设置。</span><span class="sxs-lookup"><span data-stu-id="d2f86-224">You can also adjust this setting on your PC by selecting **Settings** > **Mixed reality** > **Headset display**.</span></span>

<span data-ttu-id="d2f86-225">如果你的头戴显示设备不支持 IPD 自定义，则此设置将被禁用。</span><span class="sxs-lookup"><span data-stu-id="d2f86-225">If your headset doesn't support IPD customization, this setting will be disabled.</span></span>
