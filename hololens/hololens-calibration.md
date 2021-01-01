---
title: 改善视觉质量和舒适度
description: 校准 IPD（瞳孔间距）可以提高视觉对象的质量。 HoloLens 和 Windows Mixed Reality 沉浸式头戴显示设备都提供了自定义 IPD 的方法。
author: Teresa-Motiv
ms.author: xerxesb
ms.date: 9/13/2019
ms.topic: article
keywords: 校准, 舒适, 视觉对象, 质量, ipd
ms.prod: hololens
ms.sitesec: library
ms.localizationpriority: high
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 748475cb3e3c51e36904109ecfe03e65bdad6c1e
ms.sourcegitcommit: 6446a80bece77d67077f36a390f13b8ce59af26e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252525"
---
# <span data-ttu-id="9ab1b-105">改善视觉质量和舒适度</span><span class="sxs-lookup"><span data-stu-id="9ab1b-105">Improve visual quality and comfort</span></span>

<span data-ttu-id="9ab1b-106">在根据你自己的瞳距校准 HoloLens 2 和 HoloLens（第一代）后，体验效果会更好。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-106">HoloLens 2 and HoloLens (1st gen) both work better when they're calibrated to your unique eyes.</span></span>

<span data-ttu-id="9ab1b-107">虽然两种设备都需要通过校准才能带来最佳的全息图观看体验，但它们所用的校准技术不同。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-107">While both devices need to calibrate for the best hologram viewing experience, they use different calibration technologies and techniques.</span></span>  <span data-ttu-id="9ab1b-108">跳转到[HoloLens 2 校准](#calibrating-your-hololens-2) 或 [HoloLens（第一代）校准](#calibrating-your-hololens-1st-gen)。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-108">Jump to [HoloLens 2 calibration](#calibrating-your-hololens-2) or [HoloLens (1st gen) calibration](#calibrating-your-hololens-1st-gen).</span></span>

## <span data-ttu-id="9ab1b-109">校准 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="9ab1b-109">Calibrating your HoloLens 2</span></span>

<span data-ttu-id="9ab1b-110">HoloLens 2 使用眼球跟踪技术来改善你观看虚拟环境以及与虚拟环境互动的体验。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-110">HoloLens 2 uses eye-tracking technology to improve your experience seeing and interacting with the virtual environment.</span></span> <span data-ttu-id="9ab1b-111">校准 HoloLens 2 可确保它能够准确地跟踪你的眼球（以及使用该设备的其他人的眼球）。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-111">Calibrating the HoloLens 2 ensures that it can accurately track your eyes (and the eyes of anyone else who uses the device).</span></span> <span data-ttu-id="9ab1b-112">此外，它还有助于提高用户舒适度、进行全息影像对齐和实现手动跟踪。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-112">It also helps with user comfort, hologram alignment, and hand tracking.</span></span> <span data-ttu-id="9ab1b-113">校准后，会正确显示全息图，即使面罩在你的头上移动时也是如此。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-113">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

<span data-ttu-id="9ab1b-114">在下列情况中，HoloLens 2 会提示用户校准设备：</span><span class="sxs-lookup"><span data-stu-id="9ab1b-114">HoloLens 2 prompts a user to calibrate the device under the following circumstances:</span></span>

- <span data-ttu-id="9ab1b-115">用户首次使用设备</span><span class="sxs-lookup"><span data-stu-id="9ab1b-115">The user is using the device for the first time</span></span>
- <span data-ttu-id="9ab1b-116">用户之前选择退出校准过程</span><span class="sxs-lookup"><span data-stu-id="9ab1b-116">The user previously opted out of the calibration process</span></span>
- <span data-ttu-id="9ab1b-117">用户上次使用设备时校准过程不成功</span><span class="sxs-lookup"><span data-stu-id="9ab1b-117">The calibration process did not succeed the last time the user used the device</span></span>
- <span data-ttu-id="9ab1b-118">用户已删除其校准配置文件</span><span class="sxs-lookup"><span data-stu-id="9ab1b-118">The user has deleted their calibration profiles</span></span>
- <span data-ttu-id="9ab1b-119">设备将被关闭并重新打开，且上述任何情况都适用</span><span class="sxs-lookup"><span data-stu-id="9ab1b-119">The device is taken off and put back on and any of the above circumstances apply</span></span> 


![调整到眼部的校准提示。](./images/07-et-adjust-for-your-eyes.png)

<span data-ttu-id="9ab1b-121">在此过程中，你需要注视一组目标（宝石）。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-121">During this process, you'll look at a set of targets (gems).</span></span> <span data-ttu-id="9ab1b-122">校准期间，你可以眨眼，但请尽量把注意力集中在宝石上，而不是盯着房间中的其他对象。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-122">It's fine if you blink during calibration, but try to stay focused on the gems instead of other objects in the room.</span></span>  <span data-ttu-id="9ab1b-123">通过专注于这些宝石，HoloLens 可以了解你的眼睛位置，以呈现全息世界。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-123">Focusing on the gems allows HoloLens to learn about your eye position to render your holographic world.</span></span>

![校准提示告诉用户保持头部静止不动并用眼睛跟随点。](./images/07-et-hold-head-still.png)

![带有 gem 示例的校准提示。](./images/08-et-gems.png)

![校准提示调整。](./images/09-et-adjusting.png)

<span data-ttu-id="9ab1b-127">如果校准成功，你将看到一个成功屏幕。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-127">If calibration was successful, you'll see a success screen.</span></span>  <span data-ttu-id="9ab1b-128">如果不成功，请在[此处](#troubleshooting-hololens-2-calibration)了解诊断校准故障的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-128">If not, read more about diagnosing calibration failures [here](#troubleshooting-hololens-2-calibration).</span></span>

![校准提示成功。](./images/10-et-success.png)

### <span data-ttu-id="9ab1b-130">共享设备或会话时校准</span><span class="sxs-lookup"><span data-stu-id="9ab1b-130">Calibration when sharing a device or session</span></span>

<span data-ttu-id="9ab1b-131">多个用户可以共用一台 HoloLens 2 设备，但不需要每个人都走一遍设备设置流程。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-131">Multiple users can share a HoloLens 2 device, without a need for each person to go through device setup.</span></span> <span data-ttu-id="9ab1b-132">当新的用户首次将设备戴在头上时，HoloLens 2 会自动提示该用户进行视觉对象校准。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-132">When a new user puts the device on their head for the first time, HoloLens 2 automatically prompts the user to calibrate visuals.</span></span> <span data-ttu-id="9ab1b-133">当之前校准过视觉对象的用户再次将设备戴在头上时，显示屏可无缝调整，为其提供高质量的舒适观看体验。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-133">When a user that has previously calibrated visuals puts the device on their head, the display seamlessly adjusts for quality and a comfortable viewing experience.</span></span>  

### <span data-ttu-id="9ab1b-134">手动启动校准过程</span><span class="sxs-lookup"><span data-stu-id="9ab1b-134">Manually starting the calibration process</span></span>

1. <span data-ttu-id="9ab1b-135">使用开始手势打开[**开始**菜单](hololens2-basic-usage.md#start-gesture)。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-135">Use the start gesture to open the [**Start** menu](hololens2-basic-usage.md#start-gesture).</span></span>
1. <span data-ttu-id="9ab1b-136">如果“设置”应用未固定到**开始**，请选择**所有应用**。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-136">If the Settings app isn't pinned to **Start**, select **All Apps**.</span></span>
1. <span data-ttu-id="9ab1b-137">选择**设置**，然后选择**系统** > **校准** > **目视校准** > **运行目视校准**。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-137">Select **Settings**, and then select **System** > **Calibration** > **Eye Calibration** > **Run eye calibration**.</span></span>

   ![“设置”应用，显示“运行目视校准”选项](./images/C-Settings.Calibration.png)

### <span data-ttu-id="9ab1b-139">自动眼部位置支持</span><span class="sxs-lookup"><span data-stu-id="9ab1b-139">Auto Eye Position Support</span></span>

<span data-ttu-id="9ab1b-140">在 HoloLens 2 中，目视位置可实现准确的全息影像定位、舒适的观看体验和改进的显示质量。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-140">In HoloLens 2, eye positions enable accurate hologram positioning, comfortable viewing experience and improved display quality.</span></span> <span data-ttu-id="9ab1b-141">目视位置在内部计算，作为眼球跟踪计算的一部分。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-141">Eye positions are computed internally as part of the eye tracking computation.</span></span> <span data-ttu-id="9ab1b-142">但是，这要求每个用户都可以通过目视跟踪校准，即使体验可能不需要目视的注视输入也是如此。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-142">However, this requires each user to go through eye tracking calibration, even when the experience might not require eye gaze input.</span></span>

<span data-ttu-id="9ab1b-143">**自动眼部位置 (AEP)** 使这些场景能够以无交互方式为用户眼部位置。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-143">**Auto Eye Position (AEP)** enables these scenarios with an interaction-free way to compute eye positions for the user.</span></span> <span data-ttu-id="9ab1b-144">从用户戴上设备开始，“自动眼部位置”将自动在后台开始工作。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-144">Auto Eye Position starts working in the background automatically from the moment the user puts the device on.</span></span> <span data-ttu-id="9ab1b-145">如果用户没有之前的眼球跟踪校准，自动目视位置将在 20-30 秒的处理时间后开始向显示系统提供用户的眼部位置。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-145">If the user does not have a prior eye tracking calibration, Auto Eye Position will start providing the user's eye positions to the display system after a processing time of 20 - 30 seconds.</span></span> <span data-ttu-id="9ab1b-146">用户数据不会保留在设备上，因此，如果用户取下并重新戴上设备，或者设备重新启动或从睡眠状态唤醒，则会重复此过程。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-146">The user data is not persisted on the device and hence this process is repeated if the user takes off and puts the device back on or if the device reboots or wakes up from sleep.</span></span>

<span data-ttu-id="9ab1b-147">当未经校准的用户戴上设备时，“自动眼部位置”功能会改变一些系统行为。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-147">There are a few system behavior changes with Auto Eye Position feature when an uncalibrated user puts on the device.</span></span> <span data-ttu-id="9ab1b-148">在这种情况下，未校准的用户指的是之前未在设备上完成眼球跟踪校准过程的人员。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-148">In this context, an uncalibrated user refers to someone who has not gone through the eye tracking calibration process on the device previously.</span></span>

| <span data-ttu-id="9ab1b-149">活动应用程序</span><span class="sxs-lookup"><span data-stu-id="9ab1b-149">Active Application</span></span> | <span data-ttu-id="9ab1b-150">先前行为</span><span class="sxs-lookup"><span data-stu-id="9ab1b-150">Prior Behavior</span></span> | <span data-ttu-id="9ab1b-151">Windows 全息版 20H2 更新的行为</span><span class="sxs-lookup"><span data-stu-id="9ab1b-151">Behavior from Windows Holographic, version 20H2 Update</span></span> |
|:-------------------|:-----------------|:-----------------------------------|
| <span data-ttu-id="9ab1b-152">未启用凝视的应用或全息外壳</span><span class="sxs-lookup"><span data-stu-id="9ab1b-152">Non-gaze enabled app or Holographic Shell</span></span> |<span data-ttu-id="9ab1b-153">“眼球跟踪校准提示”对话框随即显示。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-153">Eye tracking calibration prompt dialog is displayed.</span></span> | <span data-ttu-id="9ab1b-154">不显示提示。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-154">No prompt is displayed.</span></span> |
| <span data-ttu-id="9ab1b-155">已启用凝视的应用</span><span class="sxs-lookup"><span data-stu-id="9ab1b-155">Gaze enabled app</span></span> | <span data-ttu-id="9ab1b-156">“眼球跟踪校准提示”对话框随即显示。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-156">Eye tracking calibration prompt dialog is displayed.</span></span> | <span data-ttu-id="9ab1b-157">仅当应用程序访问眼睛凝视流时，才会显示眼球跟踪校准提示。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-157">Eye tracking calibration prompt is displayed only when the application accesses eye gaze stream.</span></span> |

<span data-ttu-id="9ab1b-158">如果用户从未启用凝视的应用程序转换为访问凝视数据的应用程序，则会显示校准提示。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-158">If the user transitions from a non-gaze enabled application to one that accesses the gaze data, the calibration prompt will be displayed.</span></span> 

<span data-ttu-id="9ab1b-159">所有其他系统行为将类似于当前用户没有活动的眼球跟踪校准的情况。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-159">All other system behavior will be similar to when the current user does not have an active eye tracking calibration.</span></span> <span data-ttu-id="9ab1b-160">例如，将不会启用单只手的开始手势。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-160">For example, the One-handed Start gesture will not be enabled.</span></span> <span data-ttu-id="9ab1b-161">初始设置的全新体验不会有任何变化。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-161">There will be no change to the Out-Of-Box-Experience for initial setup.</span></span>

<span data-ttu-id="9ab1b-162">对于需要眼睛凝视数据或非常精确的全息影像位置的体验，我们建议未校准的用户运行眼球跟踪校准。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-162">For experiences that require eye gaze data or very precise hologram positioning, we recommend uncalibrated users to run eye tracking calibration.</span></span> <span data-ttu-id="9ab1b-163">您可以通过眼球跟踪校准提示或从开始菜单启动设置应用程序，然后选择 **“系统” > “校准” > “眼球校准” > “运行眼睛球校准”**。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-163">It is accessible from the eye tracking calibration prompt or by launching the Settings app from the start menu, and then selecting **System > Calibration > Eye Calibration > Run eye calibration**.</span></span>

#### <span data-ttu-id="9ab1b-164">延期校准提示</span><span class="sxs-lookup"><span data-stu-id="9ab1b-164">Deferred Calibration Prompt</span></span>

<span data-ttu-id="9ab1b-165">使用自动目视位置，眼球跟踪校准提示对话框将被推迟，直到应用程序请求眼球凝视数据。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-165">With Auto Eye Position, the Eye Tracking Calibration prompt dialog is deferred until an application requests Eye Gaze data.</span></span> <span data-ttu-id="9ab1b-166">这样可以确保当活动应用程序不需要凝视时，不会向用户提示。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-166">This ensures that there is no prompt to the user when the active application does not require gaze.</span></span> <span data-ttu-id="9ab1b-167">如果应用程序确实需要凝视数据，而当前用户没有校准，则会向用户显示校准提示。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-167">If the application does require gaze data and the current user is not calibrated, the user is presented with a calibration prompt.</span></span> <span data-ttu-id="9ab1b-168">这种行为可以用来显示眼球跟踪校准提示在适当的时间，以便体验。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-168">This behavior could be used to display eye tracking calibration prompt at a suitable time for the experience.</span></span> <span data-ttu-id="9ab1b-169">出于以下原因，建议使用此方法</span><span class="sxs-lookup"><span data-stu-id="9ab1b-169">This method is recommended for the following reasons</span></span>

1.  <span data-ttu-id="9ab1b-170">“眼球跟踪校准提示”对话框向用户提供了有关为什么需要眼球跟踪的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-170">The Eye Tracking Calibration Prompt dialog provides the user with details on why eye tracking is needed.</span></span>
2.  <span data-ttu-id="9ab1b-171">为用户提供了一种拒绝眼球校准的方法。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-171">Presents the user a way to decline to have their eyes calibrated.</span></span>

<span data-ttu-id="9ab1b-172">如果用户选择启动“眼球校准”，校准完成后，焦点应返回到原始应用程序。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-172">If the user chooses to launch the Eye Tracking Calibration, the focus should returning to the original application after calibration completes.</span></span> 

### <span data-ttu-id="9ab1b-173">HoloLens 2 校准疑难解答</span><span class="sxs-lookup"><span data-stu-id="9ab1b-173">Troubleshooting HoloLens 2 calibration</span></span>

<span data-ttu-id="9ab1b-174">大多数的校准会成功，但偶尔也会有失败。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-174">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="9ab1b-175">校准失败的一些可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="9ab1b-175">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="9ab1b-176">分神，没有追踪校准目标</span><span class="sxs-lookup"><span data-stu-id="9ab1b-176">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="9ab1b-177">设备面罩脏、有划痕或放置不正确</span><span class="sxs-lookup"><span data-stu-id="9ab1b-177">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="9ab1b-178">镜片脏或有划痕</span><span class="sxs-lookup"><span data-stu-id="9ab1b-178">Dirty or scratched glasses</span></span>
- <span data-ttu-id="9ab1b-179">某些类型的隐形眼镜和眼镜（彩色隐形眼镜、某些复曲面隐形眼镜、防红外线眼镜、某些高级处方眼镜和太阳镜等类似的眼睛）</span><span class="sxs-lookup"><span data-stu-id="9ab1b-179">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="9ab1b-180">浓妆和一些假睫毛</span><span class="sxs-lookup"><span data-stu-id="9ab1b-180">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="9ab1b-181">头发或厚眼镜框也可能阻碍设备追踪你的眼睛</span><span class="sxs-lookup"><span data-stu-id="9ab1b-181">Hair or thick eyeglass frames if they are blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="9ab1b-182">某些眼睛生理结构、状况、手术，如细眯眼、长睫毛、弱视、眼球震颤、LASIK 手术等</span><span class="sxs-lookup"><span data-stu-id="9ab1b-182">Certain eye physiology, eye conditions or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="9ab1b-183">如果校准不成功，请尝试：</span><span class="sxs-lookup"><span data-stu-id="9ab1b-183">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="9ab1b-184">清洁设备面罩</span><span class="sxs-lookup"><span data-stu-id="9ab1b-184">Cleaning your device visor</span></span>
- <span data-ttu-id="9ab1b-185">清洁眼镜</span><span class="sxs-lookup"><span data-stu-id="9ab1b-185">Cleaning your glasses</span></span>
- <span data-ttu-id="9ab1b-186">将设备面罩尽量靠近眼睛</span><span class="sxs-lookup"><span data-stu-id="9ab1b-186">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="9ab1b-187">除去遮挡面罩的物体（如头发）</span><span class="sxs-lookup"><span data-stu-id="9ab1b-187">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="9ab1b-188">打开房间的灯或避开阳光直射</span><span class="sxs-lookup"><span data-stu-id="9ab1b-188">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="9ab1b-189">如果你已遵循所有指南，但校准仍然失败，则可以在“设置”中禁用校准提示。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-189">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="9ab1b-190">另请在[反馈中心](hololens-feedback.md)中提交反馈，让我们了解相应情况。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-190">Please also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="9ab1b-191">另请参阅有关 [图像颜色或亮度故障排除](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)的信息。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-191">Please also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="9ab1b-192">请注意，设置 IPD 不适用于 Hololens 2，因为眼睛位置是由系统计算的。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-192">Note that setting IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span> 

### <span data-ttu-id="9ab1b-193">校准数据和安全</span><span class="sxs-lookup"><span data-stu-id="9ab1b-193">Calibration data and security</span></span>

<span data-ttu-id="9ab1b-194">校准信息本地存储在设备上，与任何帐户信息无关。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-194">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="9ab1b-195">使用设备但未校准的用户不会留下记录。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-195">There is no record of who has used the device without calibration.</span></span> <span data-ttu-id="9ab1b-196">这意味着，当新用户首次使用设备时，系统会提示他们进行视觉对象校准，而之前选择退出校准过程或校准不成功的用户也会得到同样提示。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-196">This mean new users will get prompted to calibrate visuals when they use the device for the first time, as well as users who opted out of calibration previously or if calibration was unsuccessful.</span></span>

<span data-ttu-id="9ab1b-197">设备可以在本地存储多达 50 个校准配置文件。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-197">The device can locally store up to 50 calibration profiles.</span></span> <span data-ttu-id="9ab1b-198">达到此数目后，设备将自动删除最早的未用配置文件。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-198">After this number is reached, the device automatically deletes the oldest unused profile.</span></span>

<span data-ttu-id="9ab1b-199">要想删除设备上的校准信息，只要选择**设置** > **隐私** > **眼球追踪仪**并删除即可。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-199">Calibration information can always be deleted from the device in **Settings** > **Privacy** > **Eye tracker**.</span></span>  

### <span data-ttu-id="9ab1b-200">禁用校准</span><span class="sxs-lookup"><span data-stu-id="9ab1b-200">Disable calibration</span></span>

<span data-ttu-id="9ab1b-201">还可以执行以下步骤来禁用校准提示：</span><span class="sxs-lookup"><span data-stu-id="9ab1b-201">You can also disable the calibration prompt by following these steps:</span></span>

1. <span data-ttu-id="9ab1b-202">选择**设置** > **系统** > **校准**。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-202">Select **Settings** > **System** > **Calibration**.</span></span>
1. <span data-ttu-id="9ab1b-203">关闭**当新用户使用此 HoloLens 时，自动请求运行眼球校准**。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-203">Turn off **When a new person uses this HoloLens, automatically ask to run eye calibration**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ab1b-204">此设置可能对全息影像呈现质量和舒适度产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-204">This setting may adversely affect hologram rendering quality and comfort.</span></span>  <span data-ttu-id="9ab1b-205">关闭此设置时，依赖于眼球跟踪的功能（如文本滚动）在沉浸式应用程序中将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-205">When you turn off this setting, features that depend on eye tracking (such as text scrolling) no longer work in immersive applications.</span></span>

### <span data-ttu-id="9ab1b-206">HoloLens 2 眼球跟踪技术</span><span class="sxs-lookup"><span data-stu-id="9ab1b-206">HoloLens 2 eye-tracking technology</span></span>

<span data-ttu-id="9ab1b-207">该设备使用眼球跟踪技术来提高显示质量，同时确保所有全息图放置准确、在 3D 模式下观看起来更舒适。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-207">The device uses its eye-tracking technology to improve display quality, and to ensure that all holograms are positioned accurately and comfortable to view in 3D.</span></span> <span data-ttu-id="9ab1b-208">因为它将眼睛作为地标，所以设备可以针对每个用户自我调整，并随着头戴显示设备在整个使用过程中轻微地移动调整视觉对象。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-208">Because it uses the eyes as landmarks, the device can adjust itself for every user and tune its visuals as the headset shifts slightly throughout use.</span></span>  <span data-ttu-id="9ab1b-209">所有调整都自动完成，无需手动介入。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-209">All adjustments happen on the fly without a need for manual tuning.</span></span>
> [!NOTE]
> <span data-ttu-id="9ab1b-210">设置 IPD 不适用于 Hololens 2，因为眼睛位置是由系统计算的。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-210">Setting the IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span>

<span data-ttu-id="9ab1b-211">HoloLens 应用程序使用眼动追踪技术来实时追踪你注视的地方。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-211">HoloLens applications use eye tracking to track where you are looking in real time.</span></span> <span data-ttu-id="9ab1b-212">这是开发人员可以利用来实现全息体验中全新水平的上下文、人类理解和互动的主要技术。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-212">This is the main capability developers can leverage to enable a whole new level of context, human understanding and interactions within the Holographic experience.</span></span> <span data-ttu-id="9ab1b-213">开发人员无需进行任何操作就可以使用此功能。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-213">Developers don’t need to do anything to leverage this capability.</span></span>

## <span data-ttu-id="9ab1b-214">校准你的 HoloLens（第一代）</span><span class="sxs-lookup"><span data-stu-id="9ab1b-214">Calibrating your HoloLens (1st gen)</span></span>

<span data-ttu-id="9ab1b-215">HoloLens（第一代）根据你的[瞳距](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD) 调整全息图显示。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-215">HoloLens (1st gen) adjusts hologram display according to the your [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD).</span></span> <span data-ttu-id="9ab1b-216">如果 IPD 不准确，全息图可能显示不稳定或距离不正确。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-216">If the IPD is not accurate, holograms may appear unstable or at an incorrect distance.</span></span> <span data-ttu-id="9ab1b-217">根据你的瞳距 (IPD) 来校准设备可以提高视觉对象的质量。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-217">You can improve the quality of your visuals by calibrating the device to your interpupillary distance (IPD).</span></span>

<span data-ttu-id="9ab1b-218">在设置 Hololens（第一代）设备时，当 Cortana 作完自我介绍后，系统会提示你进行视觉对象校准。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-218">When you set up your Hololens (1st gen) device, it prompts to calibrate your visuals after Cortana introduces herself.</span></span> <span data-ttu-id="9ab1b-219">建议你在此设置阶段完成校准步骤。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-219">It's recommended that you complete the calibration step during this setup phase.</span></span> <span data-ttu-id="9ab1b-220">不过，你也可以跳过这一步，只要在 Cortana 提示你时，你说“跳过”即可。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-220">However you can skip it by waiting until Cortana prompts you and then saying "Skip."</span></span>

<span data-ttu-id="9ab1b-221">在校准过程中，HoloLens 会要求你将手指与每只眼睛注视的六个目标对齐。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-221">During the calibration process, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="9ab1b-222">HoloLens 使用此过程为眼睛正确设置 IPD。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-222">HoloLens uses this process to set the IPD correctly for your eyes.</span></span>

![第二步中的 IPD 手指对齐屏幕](./images/ipd-finger-alignment-300px.jpg)

### <span data-ttu-id="9ab1b-224">手动启动校准过程</span><span class="sxs-lookup"><span data-stu-id="9ab1b-224">Manually start the calibration process</span></span>

<span data-ttu-id="9ab1b-225">如果你需要更新校准，或者新的用户需要调整校准，都可以随时手动运行“校准”应用。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-225">If you need to update the calibration or if a new user needs to adjust it, you can manually run the Calibration app at any time.</span></span> <span data-ttu-id="9ab1b-226">默认情况下安装“校准”应用。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-226">The Calibration app is installed by default.</span></span> <span data-ttu-id="9ab1b-227">要访问该应用，可以通过**开始**菜单或“设置”应用。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-227">You can access it by using eihter the **Start** menu or the Settings app.</span></span>

<span data-ttu-id="9ab1b-228">要通过**开始**菜单运行“校准”应用，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="9ab1b-228">To use the **Start** menu to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="9ab1b-229">使用[开花](hololens1-basic-usage.md)手势打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-229">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="9ab1b-230">要查看所有应用，请选择 **+**。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-230">To view all apps, select **+**.</span></span>
1. <span data-ttu-id="9ab1b-231">选择**校准**。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-231">Select **Calibration**.</span></span>

![从 shell 访问“校准”应用](./images/calibration-shell.png)

![“校准”应用启动后显示为一个活动立方体](./images/calibration-livecube-200px.png)

<span data-ttu-id="9ab1b-234">要通过“设置”应用来运行“校准”应用，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="9ab1b-234">To use the Settings app to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="9ab1b-235">使用[开花](hololens1-basic-usage.md)手势打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-235">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="9ab1b-236">如果未将**设置**固定到**开始**，请选择 **+** 来查看所有应用。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-236">If **Settings** isn't pinned to **Start**, select **+** to view all apps.</span></span>
1. <span data-ttu-id="9ab1b-237">选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-237">Select **Settings**.</span></span>
1. <span data-ttu-id="9ab1b-238">选择**系统** > **实用程序** > **打开校准**。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-238">Select **System** > **Utilities** > **Open Calibration**.</span></span>

![从“设置”应用启动“校准”应用](./images/calibration-settings-500px.jpg)

## <span data-ttu-id="9ab1b-240">沉浸式头戴显示设备</span><span class="sxs-lookup"><span data-stu-id="9ab1b-240">Immersive headsets</span></span>

<span data-ttu-id="9ab1b-241">某些沉浸式头戴显示设备提供自定义 IPD 设置的功能。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-241">Some immersive headsets provide the ability to customize the IPD setting.</span></span> <span data-ttu-id="9ab1b-242">要更改头戴显示设备的 IPD，请打开“设置”应用并选择**混合现实** > **头戴显示设备显示**，然后移动滑块控件。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-242">To change the IPD for your headset, open the Settings app and select **Mixed reality** > **Headset display**, and then move the slider control.</span></span> <span data-ttu-id="9ab1b-243">你将在头戴显示设备中实时看到变化。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-243">You’ll see the changes in real time in your headset.</span></span> <span data-ttu-id="9ab1b-244">如果你知道自己的 IPD（可能是从验光师那里得知），可以直接输入它。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-244">If you know your IPD, maybe from a visit to the optometrist, you can enter it directly as well.</span></span>

<span data-ttu-id="9ab1b-245">你还可以通过选择**设置** > **混合现实** > **头戴显示设备显示**来调整电脑上的这一设置。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-245">You can also adjust this setting on your PC by selecting **Settings** > **Mixed reality** > **Headset display**.</span></span>

<span data-ttu-id="9ab1b-246">如果你的头戴显示设备不支持 IPD 自定义，则此设置将被禁用。</span><span class="sxs-lookup"><span data-stu-id="9ab1b-246">If your headset does not support IPD customization, this setting will be disabled.</span></span>
