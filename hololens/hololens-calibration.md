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
ms.openlocfilehash: 627631ee7070af6cb6c60e91890f05472ce0f6be
ms.sourcegitcommit: 8b56f4b9b5f9c928fc361f18efcbea729055a0b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919153"
---
# <span data-ttu-id="7b7ee-105">改善视觉质量和舒适度</span><span class="sxs-lookup"><span data-stu-id="7b7ee-105">Improve visual quality and comfort</span></span>

<span data-ttu-id="7b7ee-106">在根据你自己的瞳距校准 HoloLens 2 和 HoloLens（第一代）后，体验效果会更好。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-106">HoloLens 2 and HoloLens (1st gen) both work better when they're calibrated to your unique eyes.</span></span>

<span data-ttu-id="7b7ee-107">虽然两种设备都需要通过校准才能带来最佳的全息图观看体验，但它们所用的校准技术不同。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-107">While both devices need to calibrate for the best hologram viewing experience, they use different calibration technologies and techniques.</span></span>  <span data-ttu-id="7b7ee-108">跳转到[HoloLens 2 校准](#calibrating-your-hololens-2) 或 [HoloLens（第一代）校准](#calibrating-your-hololens-1st-gen)。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-108">Jump to [HoloLens 2 calibration](#calibrating-your-hololens-2) or [HoloLens (1st gen) calibration](#calibrating-your-hololens-1st-gen).</span></span>

## <span data-ttu-id="7b7ee-109">校准 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="7b7ee-109">Calibrating your HoloLens 2</span></span>

<span data-ttu-id="7b7ee-110">HoloLens 2 使用眼球跟踪技术来改善你观看虚拟环境以及与虚拟环境互动的体验。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-110">HoloLens 2 uses eye-tracking technology to improve your experience seeing and interacting with the virtual environment.</span></span> <span data-ttu-id="7b7ee-111">校准 HoloLens 2 可确保它能够准确地跟踪你的眼球（以及使用该设备的其他人的眼球）。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-111">Calibrating the HoloLens 2 ensures that it can accurately track your eyes (and the eyes of anyone else who uses the device).</span></span> <span data-ttu-id="7b7ee-112">此外，它还有助于提高用户舒适度、进行全息影像对齐和实现手动跟踪。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-112">It also helps with user comfort, hologram alignment, and hand tracking.</span></span> <span data-ttu-id="7b7ee-113">校准后，会正确显示全息图，即使面罩在你的头上移动时也是如此。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-113">After calibration, holograms will appear correctly even as the visor shifts on your head.</span></span>

<span data-ttu-id="7b7ee-114">在下列情况中，HoloLens 2 会提示用户校准设备：</span><span class="sxs-lookup"><span data-stu-id="7b7ee-114">HoloLens 2 prompts a user to calibrate the device under the following circumstances:</span></span>

- <span data-ttu-id="7b7ee-115">用户首次使用设备</span><span class="sxs-lookup"><span data-stu-id="7b7ee-115">The user is using the device for the first time</span></span>
- <span data-ttu-id="7b7ee-116">用户之前选择退出校准过程</span><span class="sxs-lookup"><span data-stu-id="7b7ee-116">The user previously opted out of the calibration process</span></span>
- <span data-ttu-id="7b7ee-117">用户上次使用设备时校准过程不成功</span><span class="sxs-lookup"><span data-stu-id="7b7ee-117">The calibration process did not succeed the last time the user used the device</span></span>
- <span data-ttu-id="7b7ee-118">用户已删除其校准配置文件</span><span class="sxs-lookup"><span data-stu-id="7b7ee-118">The user has deleted their calibration profiles</span></span>
- <span data-ttu-id="7b7ee-119">设备将被关闭并重新打开，且上述任何情况都适用</span><span class="sxs-lookup"><span data-stu-id="7b7ee-119">The device is taken off and put back on and any of the above circumstances apply</span></span> 


![校准提示](./images/07-et-adjust-for-your-eyes.png)

<span data-ttu-id="7b7ee-121">在此过程中，你需要注视一组目标（宝石）。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-121">During this process, you'll look at a set of targets (gems).</span></span> <span data-ttu-id="7b7ee-122">校准期间，你可以眨眼，但请尽量把注意力集中在宝石上，而不是盯着房间中的其他对象。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-122">It's fine if you blink during calibration, but try to stay focused on the gems instead of other objects in the room.</span></span>  <span data-ttu-id="7b7ee-123">这使 HoloLens 可以获取你的眼球位置，从而向你呈现全息世界。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-123">This allows HoloLens to learn about your eye position to render your holographic world.</span></span>

![校准提示](./images/07-et-hold-head-still.png)

![校准提示](./images/08-et-gems.png)

![校准提示](./images/09-et-adjusting.png)

<span data-ttu-id="7b7ee-127">如果校准成功，你将看到一个成功屏幕。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-127">If calibration was successful, you'll see a success screen.</span></span>  <span data-ttu-id="7b7ee-128">如果不成功，请在[此处](#troubleshooting-hololens-2-calibration)了解诊断校准故障的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-128">If not, read more about diagnosing calibration failures [here](#troubleshooting-hololens-2-calibration).</span></span>

![校准提示](./images/10-et-success.png)

### <span data-ttu-id="7b7ee-130">共享设备或会话时校准</span><span class="sxs-lookup"><span data-stu-id="7b7ee-130">Calibration when sharing a device or session</span></span>

<span data-ttu-id="7b7ee-131">多个用户可以共用一台 HoloLens 2 设备，但不需要每个人都走一遍设备设置流程。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-131">Multiple users can share a HoloLens 2 device, without a need for each person to go through device setup.</span></span> <span data-ttu-id="7b7ee-132">当新的用户首次将设备戴在头上时，HoloLens 2 会自动提示该用户进行视觉对象校准。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-132">When a new user puts the device on their head for the first time, HoloLens 2 automatically prompts the user to calibrate visuals.</span></span> <span data-ttu-id="7b7ee-133">当之前校准过视觉对象的用户再次将设备戴在头上时，显示屏可无缝调整，为其提供高质量的舒适观看体验。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-133">When a user that has previously calibrated visuals puts the device on their head, the display seamlessly adjusts for quality and a comfortable viewing experience.</span></span>  

### <span data-ttu-id="7b7ee-134">手动启动校准过程</span><span class="sxs-lookup"><span data-stu-id="7b7ee-134">Manually starting the calibration process</span></span>

1. <span data-ttu-id="7b7ee-135">使用开始手势打开[**开始**菜单](hololens2-basic-usage.md#start-gesture)。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-135">Use the start gesture to open the [**Start** menu](hololens2-basic-usage.md#start-gesture).</span></span>
1. <span data-ttu-id="7b7ee-136">如果“设置”应用未固定到**开始**，请选择**所有应用**。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-136">If the Settings app isn't pinned to **Start**, select **All Apps**.</span></span>
1. <span data-ttu-id="7b7ee-137">选择**设置**，然后选择**系统** > **校准** > **目视校准** > **运行目视校准**。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-137">Select **Settings**, and then select **System** > **Calibration** > **Eye Calibration** > **Run eye calibration**.</span></span>

   ![“设置”应用，显示“运行目视校准”选项](./images/C-Settings.Calibration.png)

### <span data-ttu-id="7b7ee-139">解决 HoloLens 2 校准问题</span><span class="sxs-lookup"><span data-stu-id="7b7ee-139">Troubleshooting HoloLens 2 calibration</span></span>

<span data-ttu-id="7b7ee-140">大多数的校准会成功，但偶尔也会有失败。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-140">Calibration should work for most people, but there are cases where calibration fails.</span></span>
  
<span data-ttu-id="7b7ee-141">校准失败的一些可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="7b7ee-141">Some potential reasons for calibration failure include:</span></span>

- <span data-ttu-id="7b7ee-142">分神，没有追踪校准目标</span><span class="sxs-lookup"><span data-stu-id="7b7ee-142">Getting distracted and not following the calibration targets</span></span>
- <span data-ttu-id="7b7ee-143">设备面罩脏、有划痕或放置不正确</span><span class="sxs-lookup"><span data-stu-id="7b7ee-143">Dirty or scratched device visor or device visor not positioned properly</span></span>
- <span data-ttu-id="7b7ee-144">镜片脏或有划痕</span><span class="sxs-lookup"><span data-stu-id="7b7ee-144">Dirty or scratched glasses</span></span>
- <span data-ttu-id="7b7ee-145">某些类型的隐形眼镜和眼镜（彩色隐形眼镜、某些复曲面隐形眼镜、防红外线眼镜、某些高级处方眼镜和太阳镜等类似的眼睛）</span><span class="sxs-lookup"><span data-stu-id="7b7ee-145">Certain types of contact lenses and glasses (colored contact lenses, some toric contact lenses, IR blocking glasses, some high prescription glasses, sunglasses, or similar)</span></span>
- <span data-ttu-id="7b7ee-146">浓妆和一些假睫毛</span><span class="sxs-lookup"><span data-stu-id="7b7ee-146">More-pronounced makeup and some eyelash extensions</span></span>
- <span data-ttu-id="7b7ee-147">头发或厚眼镜框也可能阻碍设备追踪你的眼睛</span><span class="sxs-lookup"><span data-stu-id="7b7ee-147">Hair or thick eyeglass frames if they are blocking the device from seeing your eyes</span></span>
- <span data-ttu-id="7b7ee-148">某些眼睛生理结构、状况、手术，如细眯眼、长睫毛、弱视、眼球震颤、LASIK 手术等</span><span class="sxs-lookup"><span data-stu-id="7b7ee-148">Certain eye physiology, eye conditions or eye surgery such as narrow eyes, long eyelashes, amblyopia, nystagmus, some cases of LASIK or other eye surgeries</span></span>

<span data-ttu-id="7b7ee-149">如果校准不成功，请尝试：</span><span class="sxs-lookup"><span data-stu-id="7b7ee-149">If calibration is unsuccessful try:</span></span>

- <span data-ttu-id="7b7ee-150">清洁设备面罩</span><span class="sxs-lookup"><span data-stu-id="7b7ee-150">Cleaning your device visor</span></span>
- <span data-ttu-id="7b7ee-151">清洁眼镜</span><span class="sxs-lookup"><span data-stu-id="7b7ee-151">Cleaning your glasses</span></span>
- <span data-ttu-id="7b7ee-152">将设备面罩尽量靠近眼睛</span><span class="sxs-lookup"><span data-stu-id="7b7ee-152">Pushing your device visor as close to your eyes as possible</span></span>
- <span data-ttu-id="7b7ee-153">除去遮挡面罩的物体（如头发）</span><span class="sxs-lookup"><span data-stu-id="7b7ee-153">Moving objects in your visor out of the way (such as hair)</span></span>
- <span data-ttu-id="7b7ee-154">打开房间的灯或避开阳光直射</span><span class="sxs-lookup"><span data-stu-id="7b7ee-154">Turning on a light in your room or moving out of direct sunlight</span></span>

<span data-ttu-id="7b7ee-155">如果你已遵循所有指南，但校准仍然失败，则可以在“设置”中禁用校准提示。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-155">If you followed all guidelines and calibration is still failing, you can disable the calibration prompt in Settings.</span></span> <span data-ttu-id="7b7ee-156">另请在[反馈中心](hololens-feedback.md)中提交反馈，让我们了解相应情况。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-156">Please also let us know by filing feedback in [Feedback Hub](hololens-feedback.md).</span></span>

<span data-ttu-id="7b7ee-157">另请参阅有关 [图像颜色或亮度故障排除](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)的信息。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-157">Please also see related information for [image color or brightness troubleshooting.](hololens2-fit-comfort-faq.md#hologram-image-color-or-brightness-does-not-look-right)</span></span>

<span data-ttu-id="7b7ee-158">请注意，设置 IPD 不适用于 Hololens 2，因为眼睛位置是由系统计算的。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-158">Note that setting IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span> 

### <span data-ttu-id="7b7ee-159">校准数据和安全</span><span class="sxs-lookup"><span data-stu-id="7b7ee-159">Calibration data and security</span></span>

<span data-ttu-id="7b7ee-160">校准信息本地存储在设备上，与任何帐户信息无关。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-160">Calibration information is stored locally on the device and is not associated with any account information.</span></span> <span data-ttu-id="7b7ee-161">使用设备但未校准的用户不会留下记录。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-161">There is no record of who has used the device without calibration.</span></span> <span data-ttu-id="7b7ee-162">这意味着，当新用户首次使用设备时，系统会提示他们进行视觉对象校准，而之前选择退出校准过程或校准不成功的用户也会得到同样提示。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-162">This mean new users will get prompted to calibrate visuals when they use the device for the first time, as well as users who opted out of calibration previously or if calibration was unsuccessful.</span></span>

<span data-ttu-id="7b7ee-163">设备可以在本地存储多达 50 个校准配置文件。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-163">The device can locally store up to 50 calibration profiles.</span></span> <span data-ttu-id="7b7ee-164">达到此数目后，设备将自动删除最早的未用配置文件。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-164">After this number is reached, the device automatically deletes the oldest unused profile.</span></span>

<span data-ttu-id="7b7ee-165">要想删除设备上的校准信息，只要选择**设置** > **隐私** > **眼球追踪仪**并删除即可。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-165">Calibration information can always be deleted from the device in **Settings** > **Privacy** > **Eye tracker**.</span></span>  

### <span data-ttu-id="7b7ee-166">禁用校准</span><span class="sxs-lookup"><span data-stu-id="7b7ee-166">Disable calibration</span></span>

<span data-ttu-id="7b7ee-167">还可以执行以下步骤来禁用校准提示：</span><span class="sxs-lookup"><span data-stu-id="7b7ee-167">You can also disable the calibration prompt by following these steps:</span></span>

1. <span data-ttu-id="7b7ee-168">选择**设置** > **系统** > **校准**。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-168">Select **Settings** > **System** > **Calibration**.</span></span>
1. <span data-ttu-id="7b7ee-169">关闭**当新用户使用此 HoloLens 时，自动请求运行眼球校准**。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-169">Turn off **When a new person uses this HoloLens, automatically ask to run eye calibration**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b7ee-170">此设置可能对全息影像呈现质量和舒适度产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-170">This setting may adversely affect hologram rendering quality and comfort.</span></span>  <span data-ttu-id="7b7ee-171">关闭此设置时，依赖于眼球跟踪的功能（如文本滚动）在沉浸式应用程序中将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-171">When you turn off this setting, features that depend on eye tracking (such as text scrolling) no longer work in immersive applications.</span></span>

### <span data-ttu-id="7b7ee-172">HoloLens 2 眼球跟踪技术</span><span class="sxs-lookup"><span data-stu-id="7b7ee-172">HoloLens 2 eye-tracking technology</span></span>

<span data-ttu-id="7b7ee-173">该设备使用眼球跟踪技术来提高显示质量，同时确保所有全息图放置准确、在 3D 模式下观看起来更舒适。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-173">The device uses its eye-tracking technology to improve display quality, and to ensure that all holograms are positioned accurately and comfortable to view in 3D.</span></span> <span data-ttu-id="7b7ee-174">因为它将眼睛作为地标，所以设备可以针对每个用户自我调整，并随着头戴显示设备在整个使用过程中轻微地移动调整视觉对象。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-174">Because it uses the eyes as landmarks, the device can adjust itself for every user and tune its visuals as the headset shifts slightly throughout use.</span></span>  <span data-ttu-id="7b7ee-175">所有调整都自动完成，无需手动介入。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-175">All adjustments happen on the fly without a need for manual tuning.</span></span>
> [!NOTE]
> <span data-ttu-id="7b7ee-176">设置 IPD 不适用于 Hololens 2，因为眼睛位置是由系统计算的。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-176">Setting the IPD is not applicable for Hololens 2, since eye positions are computed by the system.</span></span>

<span data-ttu-id="7b7ee-177">HoloLens 应用程序使用眼动追踪技术来实时追踪你注视的地方。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-177">HoloLens applications use eye tracking to track where you are looking in real time.</span></span> <span data-ttu-id="7b7ee-178">这是开发人员可以利用来实现全息体验中全新水平的上下文、人类理解和互动的主要技术。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-178">This is the main capability developers can leverage to enable a whole new level of context, human understanding and interactions within the Holographic experience.</span></span> <span data-ttu-id="7b7ee-179">开发人员无需进行任何操作就可以使用此功能。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-179">Developers don’t need to do anything to leverage this capability.</span></span>

## <span data-ttu-id="7b7ee-180">校准你的 HoloLens（第一代）</span><span class="sxs-lookup"><span data-stu-id="7b7ee-180">Calibrating your HoloLens (1st gen)</span></span>

<span data-ttu-id="7b7ee-181">HoloLens（第一代）根据你的[瞳距](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD) 调整全息图显示。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-181">HoloLens (1st gen) adjusts hologram display according to the your [interpupillary distance](https://en.wikipedia.org/wiki/Interpupillary_distance) (IPD).</span></span> <span data-ttu-id="7b7ee-182">如果 IPD 不准确，全息图可能显示不稳定或距离不正确。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-182">If the IPD is not accurate, holograms may appear unstable or at an incorrect distance.</span></span> <span data-ttu-id="7b7ee-183">根据你的瞳距 (IPD) 来校准设备可以提高视觉对象的质量。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-183">You can improve the quality of your visuals by calibrating the device to your interpupillary distance (IPD).</span></span>

<span data-ttu-id="7b7ee-184">在设置 Hololens（第一代）设备时，当 Cortana 作完自我介绍后，系统会提示你进行视觉对象校准。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-184">When you set up your Hololens (1st gen) device, it prompts to calibrate your visuals after Cortana introduces herself.</span></span> <span data-ttu-id="7b7ee-185">建议你在此设置阶段完成校准步骤。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-185">It's recommended that you complete the calibration step during this setup phase.</span></span> <span data-ttu-id="7b7ee-186">不过，你也可以跳过这一步，只要在 Cortana 提示你时，你说“跳过”即可。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-186">However you can skip it by waiting until Cortana prompts you and then saying "Skip."</span></span>

<span data-ttu-id="7b7ee-187">在校准过程中，HoloLens 会要求你将手指与每只眼睛注视的六个目标对齐。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-187">During the calibration process, HoloLens asks you to align your finger with a series of six targets per eye.</span></span> <span data-ttu-id="7b7ee-188">HoloLens 使用此过程为眼睛正确设置 IPD。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-188">HoloLens uses this process to set the IPD correctly for your eyes.</span></span>

![第二步中的 IPD 手指对齐屏幕](./images/ipd-finger-alignment-300px.jpg)

### <span data-ttu-id="7b7ee-190">手动启动校准过程</span><span class="sxs-lookup"><span data-stu-id="7b7ee-190">Manually start the calibration process</span></span>

<span data-ttu-id="7b7ee-191">如果你需要更新校准，或者新的用户需要调整校准，都可以随时手动运行“校准”应用。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-191">If you need to update the calibration or if a new user needs to adjust it, you can manually run the Calibration app at any time.</span></span> <span data-ttu-id="7b7ee-192">默认情况下安装“校准”应用。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-192">The Calibration app is installed by default.</span></span> <span data-ttu-id="7b7ee-193">要访问该应用，可以通过**开始**菜单或“设置”应用。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-193">You can access it by using eihter the **Start** menu or the Settings app.</span></span>

<span data-ttu-id="7b7ee-194">要通过**开始**菜单运行“校准”应用，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="7b7ee-194">To use the **Start** menu to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="7b7ee-195">使用[开花](hololens1-basic-usage.md)手势打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-195">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="7b7ee-196">要查看所有应用，请选择 **+**。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-196">To view all apps, select **+**.</span></span>
1. <span data-ttu-id="7b7ee-197">选择**校准**。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-197">Select **Calibration**.</span></span>

![从 shell 访问“校准”应用](./images/calibration-shell.png)

![“校准”应用启动后显示为一个活动立方体](./images/calibration-livecube-200px.png)

<span data-ttu-id="7b7ee-200">要通过“设置”应用来运行“校准”应用，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="7b7ee-200">To use the Settings app to run the Calibration app, follow these steps:</span></span>

1. <span data-ttu-id="7b7ee-201">使用[开花](hololens1-basic-usage.md)手势打开**开始**菜单。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-201">Use the [bloom](hololens1-basic-usage.md) gesture to open the **Start** menu.</span></span>
1. <span data-ttu-id="7b7ee-202">如果未将**设置**固定到**开始**，请选择 **+** 来查看所有应用。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-202">If **Settings** isn't pinned to **Start**, select **+** to view all apps.</span></span>
1. <span data-ttu-id="7b7ee-203">选择**设置**。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-203">Select **Settings**.</span></span>
1. <span data-ttu-id="7b7ee-204">选择**系统** > **实用程序** > **打开校准**。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-204">Select **System** > **Utilities** > **Open Calibration**.</span></span>

![从“设置”应用启动“校准”应用](./images/calibration-settings-500px.jpg)

## <span data-ttu-id="7b7ee-206">沉浸式头戴显示设备</span><span class="sxs-lookup"><span data-stu-id="7b7ee-206">Immersive headsets</span></span>

<span data-ttu-id="7b7ee-207">某些沉浸式头戴显示设备提供自定义 IPD 设置的功能。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-207">Some immersive headsets provide the ability to customize the IPD setting.</span></span> <span data-ttu-id="7b7ee-208">要更改头戴显示设备的 IPD，请打开“设置”应用并选择**混合现实** > **头戴显示设备显示**，然后移动滑块控件。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-208">To change the IPD for your headset, open the Settings app and select **Mixed reality** > **Headset display**, and then move the slider control.</span></span> <span data-ttu-id="7b7ee-209">你将在头戴显示设备中实时看到变化。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-209">You’ll see the changes in real time in your headset.</span></span> <span data-ttu-id="7b7ee-210">如果你知道自己的 IPD（可能是从验光师那里得知），可以直接输入它。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-210">If you know your IPD, maybe from a visit to the optometrist, you can enter it directly as well.</span></span>

<span data-ttu-id="7b7ee-211">你还可以通过选择**设置** > **混合现实** > **头戴显示设备显示**来调整电脑上的这一设置。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-211">You can also adjust this setting on your PC by selecting **Settings** > **Mixed reality** > **Headset display**.</span></span>

<span data-ttu-id="7b7ee-212">如果你的头戴显示设备不支持 IPD 自定义，则此设置将被禁用。</span><span class="sxs-lookup"><span data-stu-id="7b7ee-212">If your headset does not support IPD customization, this setting will be disabled.</span></span>
