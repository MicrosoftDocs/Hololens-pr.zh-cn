---
title: 有关 HoloLens 设备和全息影像的常见问题
description: 你是否有关于 HoloLens 的快速问题，或与全息影像交互？  本文提供快速的答案和更多资源。
keywords: hololens，常见问题解答，已知问题，帮助
ms.prod: hololens
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
ms.date: 02/27/2020
ms.reviewer: ''
ms.custom:
- CI 114606
- CSSTroubleshooting
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ae44ae1d9a2e088a1ef746f4e929e8fae73880bf
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924020"
---
# <a name="holograms-and-interactions-troubleshooting"></a><span data-ttu-id="7d2bd-105">全息影像和交互疑难解答</span><span class="sxs-lookup"><span data-stu-id="7d2bd-105">Holograms and interactions troubleshooting</span></span>

<span data-ttu-id="7d2bd-106">本文介绍有关如何放置全息影像、使用空间并报告全息影像问题的问题。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-106">This article troubleshoots issues with placing holograms, working with spaces, and reporting issues with holograms.</span></span>

<span data-ttu-id="7d2bd-107">遇到问题时，请确保：</span><span class="sxs-lookup"><span data-stu-id="7d2bd-107">Anytime that you have problems, make sure:</span></span>
- <span data-ttu-id="7d2bd-108">尝试 [重新启动它](hololens-restart-recover.md) 以查看是否修复了问题。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-108">Try [restarting it](hololens-restart-recover.md) to see whether that fixes things.</span></span>
- <span data-ttu-id="7d2bd-109">在进行故障排除之前，请 [确保将 HoloLens (收费](hololens2-charging.md) 至少) 一小时。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-109">Before troubleshooting, ensure the HoloLens is [charged up](hololens2-charging.md) (charged for at least an hour).</span></span> 


<span data-ttu-id="7d2bd-110">请使用反馈应用向我们发送有关此问题的信息。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-110">Please use the Feedback app to send us information about the issue.</span></span> <span data-ttu-id="7d2bd-111">你将在 " [**开始** " 菜单](holographic-home.md)上找到 "反馈" 应用。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-111">You'll find the Feedback app on the [**Start** menu](holographic-home.md).</span></span> 

<span data-ttu-id="7d2bd-112">有关如何磨损 HoloLens 的提示，请参阅 [调整大小](hololens2-setup.md#adjust-fit)。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-112">For tips about how to wear your HoloLens, see [Adjust Fit](hololens2-setup.md#adjust-fit).</span></span>

<a id="list"></a>
- [<span data-ttu-id="7d2bd-113">无法创建新的空格</span><span class="sxs-lookup"><span data-stu-id="7d2bd-113">New spaces can't be created</span></span>](#new-spaces-cant-be-created)
- [<span data-ttu-id="7d2bd-114">无法标识或加载空格</span><span class="sxs-lookup"><span data-stu-id="7d2bd-114">Spaces can't be identified or loaded</span></span>](#spaces-cant-be-identified-or-loaded)
- [<span data-ttu-id="7d2bd-115">如何实现删除所有空格？</span><span class="sxs-lookup"><span data-stu-id="7d2bd-115">How do I delete all spaces?</span></span>](#how-do-i-delete-all-spaces)
- [<span data-ttu-id="7d2bd-116">全息影像看起来不正确或正在四处移动</span><span class="sxs-lookup"><span data-stu-id="7d2bd-116">Holograms don't look right or are moving around</span></span>](#holograms-dont-look-right-or-are-moving-around)
- [<span data-ttu-id="7d2bd-117">"查找空间" 消息</span><span class="sxs-lookup"><span data-stu-id="7d2bd-117">"Finding your space" message</span></span>](#finding-your-space-message)
- [<span data-ttu-id="7d2bd-118">我的空间中不显示预期的全息影像</span><span class="sxs-lookup"><span data-stu-id="7d2bd-118">Expected holograms aren't showing in my space</span></span>](#expected-holograms-arent-showing-in-my-space)
- [<span data-ttu-id="7d2bd-119">无法放置全息影像或查看以前放置的全息影像</span><span class="sxs-lookup"><span data-stu-id="7d2bd-119">Can't place holograms or see previously placed holograms</span></span>](#cant-place-holograms-or-see-previously-placed-holograms)
- [<span data-ttu-id="7d2bd-120">全息影像或 try</span><span class="sxs-lookup"><span data-stu-id="7d2bd-120">Holograms disappear or are encased in other holograms or objects</span></span>](#holograms-disappear-or-are-encased-in-other-holograms-or-objects)
- [<span data-ttu-id="7d2bd-121">全息影像显示在墙壁的另一端</span><span class="sxs-lookup"><span data-stu-id="7d2bd-121">Holograms are appearing on the other side of a wall</span></span>](#holograms-are-appearing-on-the-other-side-of-a-wall)
- [<span data-ttu-id="7d2bd-122">在墙上放置全息影像后，它似乎是浮动的</span><span class="sxs-lookup"><span data-stu-id="7d2bd-122">After placing a hologram on a wall, it seems to float</span></span>](#after-placing-a-hologram-on-a-wall-it-seems-to-float)
- [<span data-ttu-id="7d2bd-123">移动应用后，应用显示太近</span><span class="sxs-lookup"><span data-stu-id="7d2bd-123">Apps appear too close after moving them</span></span>](#apps-appear-too-close-after-moving-them)
- [<span data-ttu-id="7d2bd-124">报告不稳定或不精确的全息影像的问题</span><span class="sxs-lookup"><span data-stu-id="7d2bd-124">Reporting issues with unstable or inexact holograms</span></span>](#reporting-issues-with-unstable-or-inexact-holograms)

## <a name="new-spaces-cant-be-created"></a><span data-ttu-id="7d2bd-125">无法创建新的空格</span><span class="sxs-lookup"><span data-stu-id="7d2bd-125">New spaces can't be created</span></span>

<span data-ttu-id="7d2bd-126">最可能的问题是在存储空间不足的情况下运行。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-126">The most likely problem is that you're running low on storage space.</span></span> <span data-ttu-id="7d2bd-127">请[释放一些磁盘空间](hololens-troubleshooting.md#low-disk-space-error)，然后重试。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-127">[Free up some disk space](hololens-troubleshooting.md#low-disk-space-error) and then retry.</span></span>

[<span data-ttu-id="7d2bd-128">返回到列表</span><span class="sxs-lookup"><span data-stu-id="7d2bd-128">Back to list</span></span>](#list)

## <a name="spaces-cant-be-identified-or-loaded"></a><span data-ttu-id="7d2bd-129">无法标识或加载空格</span><span class="sxs-lookup"><span data-stu-id="7d2bd-129">Spaces can't be identified or loaded</span></span>

<span data-ttu-id="7d2bd-130">如果你的 HoloLens 无法识别并加载你自动登录的空间，请检查以下因素：</span><span class="sxs-lookup"><span data-stu-id="7d2bd-130">If your HoloLens can't identify and load the space you're in automatically, check the following factors:</span></span>

- <span data-ttu-id="7d2bd-131">请确保已连接到 Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="7d2bd-131">Make sure that you're connected to Wi-Fi</span></span>
- <span data-ttu-id="7d2bd-132">请确保房间内有充足的光线</span><span class="sxs-lookup"><span data-stu-id="7d2bd-132">Make sure that there's plenty of light in the room</span></span>
- <span data-ttu-id="7d2bd-133">请确保不存在对周围环境的任何重大更改。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-133">Make sure that there haven't been any major changes to the surroundings.</span></span>

<span data-ttu-id="7d2bd-134">还可以通过转到 "**设置**" "  >  **系统**  >  **空间**" 手动加载空间或管理空间。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-134">You can also load a space manually or manage your spaces by going to **Settings** > **System** > **Spaces**.</span></span>

[<span data-ttu-id="7d2bd-135">返回到列表</span><span class="sxs-lookup"><span data-stu-id="7d2bd-135">Back to list</span></span>](#list)

## <a name="how-do-i-delete-all-spaces"></a><span data-ttu-id="7d2bd-136">如何实现删除所有空格？</span><span class="sxs-lookup"><span data-stu-id="7d2bd-136">How do I delete all spaces?</span></span>

<span data-ttu-id="7d2bd-137">*即将推出*</span><span class="sxs-lookup"><span data-stu-id="7d2bd-137">*Coming soon*</span></span>

[<span data-ttu-id="7d2bd-138">返回到列表</span><span class="sxs-lookup"><span data-stu-id="7d2bd-138">Back to list</span></span>](#list)

## <a name="holograms-dont-look-right-or-are-moving-around"></a><span data-ttu-id="7d2bd-139">全息影像看起来不正确或正在四处移动</span><span class="sxs-lookup"><span data-stu-id="7d2bd-139">Holograms don't look right or are moving around</span></span>

<span data-ttu-id="7d2bd-140">例如，如果你的全息影像看上去不正常 (例如，它们抖动或晃动，或者你) 上看到了黑色的修补程序，请尝试以下解决方法之一：</span><span class="sxs-lookup"><span data-stu-id="7d2bd-140">If your holograms don't look right (for example, they're jittery or shaky, or you see black patches on top of them), try one of these fixes:</span></span>

- <span data-ttu-id="7d2bd-141">[清洁你的设备面板](hololens1-hardware.md#care-and-cleaning) ，确保没有任何传感器阻止。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-141">[Clean your device visor](hololens1-hardware.md#care-and-cleaning) and make sure nothing is blocking the sensors.</span></span>
- <span data-ttu-id="7d2bd-142">请确保你处于一个良好的空间，不会有很多直接阳光。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-142">Make sure that you're in a well-lit room that does not have a lot of direct sunlight.</span></span>
- <span data-ttu-id="7d2bd-143">尝试在你的环境中浏览和 gazing，以便 HoloLens 可以更完整地扫描它们。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-143">Try walking around and gazing at your surroundings so that HoloLens can scan them more completely.</span></span>
- <span data-ttu-id="7d2bd-144">如果你已放入大量全息影像，请尝试删除一些全息影像。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-144">If you've placed a lot of holograms, try removing some.</span></span>

<span data-ttu-id="7d2bd-145">如果仍有问题，请尝试运行校准应用。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-145">If you're still having problems, trying running the Calibration app.</span></span> <span data-ttu-id="7d2bd-146">此应用校准你的 HoloLens，只是为了帮助你保持全息的外观。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-146">This app calibrates your HoloLens just for you to help keep your holograms looking their best.</span></span> <span data-ttu-id="7d2bd-147">为此，请在 "**设置**" "系统" "  >    >  **实用程序**"。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-147">To do this, go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="7d2bd-148">在 **校准** 下，选择 " **打开校准**"。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-148">Under **Calibration**, select **Open Calibration**.</span></span>

[<span data-ttu-id="7d2bd-149">返回到列表</span><span class="sxs-lookup"><span data-stu-id="7d2bd-149">Back to list</span></span>](#list)

## <a name="finding-your-space-message"></a><span data-ttu-id="7d2bd-150">"查找空间" 消息</span><span class="sxs-lookup"><span data-stu-id="7d2bd-150">"Finding your space" message</span></span>

<span data-ttu-id="7d2bd-151">当 HoloLens 正在学习或加载空间时，可能会看到一条简短消息，其中显示 "查找你的空间"。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-151">When HoloLens is learning or loading a space, you may see a brief message that says "Finding your space."</span></span> <span data-ttu-id="7d2bd-152">如果此消息显示超过几秒钟，则会在 "开始" 菜单下看到另一条消息，显示 "仍在查找你的空间"。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-152">If this message displays for more than a few seconds, you'll see another message under the Start menu that says "Still looking for your space."</span></span>

<span data-ttu-id="7d2bd-153">这些消息表示 HoloLens 在映射空间时遇到问题。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-153">These messages mean that HoloLens is having trouble mapping your space.</span></span> <span data-ttu-id="7d2bd-154">发生这种情况时，可以打开应用程序，但不能在环境中放置全息影像。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-154">When this happens, you can open apps, but you can't place holograms in your environment.</span></span>

<span data-ttu-id="7d2bd-155">如果经常看到这些消息，请尝试下列一项或多项修复：</span><span class="sxs-lookup"><span data-stu-id="7d2bd-155">If you see these messages often, try one or more of the following fixes:</span></span>

- <span data-ttu-id="7d2bd-156">请确保你处于一个良好的空间，不会有很多直接阳光。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-156">Make sure that you're in a well-lit room that does not have a lot of direct sunlight.</span></span>
- <span data-ttu-id="7d2bd-157">确保设备面板清晰。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-157">Make sure that your device visor is clean.</span></span> <span data-ttu-id="7d2bd-158">[了解如何清理面板](hololens1-hardware.md#care-and-cleaning)。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-158">[Learn how to clean your visor](hololens1-hardware.md#care-and-cleaning).</span></span>
- <span data-ttu-id="7d2bd-159">请确保有一个强 Wi-Fi 信号。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-159">Make sure that you have a strong Wi-Fi signal.</span></span> <span data-ttu-id="7d2bd-160">如果输入的新环境没有 Wi-Fi 或弱 Wi-Fi 信号，则 HoloLens 将找不到你的空间。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-160">If you enter a new environment that has no Wi-Fi or a weak Wi-Fi signal, HoloLens won't be able find your space.</span></span> <span data-ttu-id="7d2bd-161">转到 **设置**  >  **网络 &amp; Internet**  >  **wi-fi** 来检查 Wi-Fi 连接。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-161">Check your Wi-Fi connection by going to **Settings** > **Network &amp; Internet** > **Wi-Fi**.</span></span>
- <span data-ttu-id="7d2bd-162">尝试移动速度缓慢。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-162">Try moving more slowly.</span></span>

[<span data-ttu-id="7d2bd-163">返回到列表</span><span class="sxs-lookup"><span data-stu-id="7d2bd-163">Back to list</span></span>](#list)

## <a name="expected-holograms-arent-showing-in-my-space"></a><span data-ttu-id="7d2bd-164">我的空间中不显示预期的全息影像</span><span class="sxs-lookup"><span data-stu-id="7d2bd-164">Expected holograms aren't showing in my space</span></span>

<span data-ttu-id="7d2bd-165">如果看不到你所放置的全息影像，或者你看到的是不需要的影像，请尝试以下一项或多项修复：</span><span class="sxs-lookup"><span data-stu-id="7d2bd-165">If you don't see the holograms that you placed, or if you're seeing some that you don't expect, try one or more of the following fixes:</span></span>

- <span data-ttu-id="7d2bd-166">开启一些光源。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-166">Turn on some lights.</span></span> <span data-ttu-id="7d2bd-167">HoloLens 最好在良好的空间中运行。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-167">HoloLens works best in a well-lit space.</span></span>
- <span data-ttu-id="7d2bd-168">转到 "**设置**" "  >  **系统**  >  **全息影像**"，删除不需要的全息影像  >  。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-168">Remove holograms that you don't need by going to **Settings** > **System** > **Holograms** > **Remove nearby holograms**.</span></span> <span data-ttu-id="7d2bd-169">或者，如果需要，请选择 " **删除所有全息影像**"。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-169">Or, if needed, select **Remove all holograms**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="7d2bd-170">如果空间中的布局或光照发生了重大变化，则设备可能无法识别空间并显示全息影像。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-170">If the layout or lighting in your space changes significantly, your device might have trouble identifying your space and showing your holograms.</span></span>

[<span data-ttu-id="7d2bd-171">返回到列表</span><span class="sxs-lookup"><span data-stu-id="7d2bd-171">Back to list</span></span>](#list)

## <a name="cant-place-holograms-or-see-previously-placed-holograms"></a><span data-ttu-id="7d2bd-172">无法放置全息影像或查看以前放置的全息影像</span><span class="sxs-lookup"><span data-stu-id="7d2bd-172">Can't place holograms or see previously placed holograms</span></span>

<span data-ttu-id="7d2bd-173">如果 HoloLens 无法映射或加载空间，则它将进入限制模式，你将无法放置全息影像或查看已放置的全息影像。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-173">If HoloLens can't map or load your space, it enters Limited mode and you won't be able to place holograms or see holograms that you've placed.</span></span> <span data-ttu-id="7d2bd-174">可以尝试以下操作：</span><span class="sxs-lookup"><span data-stu-id="7d2bd-174">Here are some things to try:</span></span>

- <span data-ttu-id="7d2bd-175">请确保环境中有足够的光线，以便 HoloLens 能够查看和映射空间。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-175">Make sure that there's enough light in your environment so HoloLens can see and map the space.</span></span>
- <span data-ttu-id="7d2bd-176">介于您尝试放置全息影像的一到三米之间。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-176">Stand between one and three meters from where you're trying to place the hologram.</span></span>
- <span data-ttu-id="7d2bd-177">请勿在黑色或反光的表面上放置全息影像。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-177">Don't place holograms on black or reflective surfaces.</span></span>
- <span data-ttu-id="7d2bd-178">请确保已连接到 Wi-Fi 网络。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-178">Make sure that you're connected to a Wi-Fi network.</span></span> <span data-ttu-id="7d2bd-179">如果你未连接到 Wi-fi，则 HoloLens 无法识别并加载已知的空间。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-179">If you're not connected to Wi-Fi, HoloLens can't identify and load a known space.</span></span>
- <span data-ttu-id="7d2bd-180">四处浏览房间，以便 HoloLens 可以重新扫描您的环境。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-180">Walk around the rooms so HoloLens can rescan your surroundings.</span></span> <span data-ttu-id="7d2bd-181">若要查看已扫描的内容，请点击以显示地图网格图。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-181">To see what's already been scanned, air tap to reveal the mapping mesh graphic.</span></span>
- <span data-ttu-id="7d2bd-182">如果需要创建新空间，请连接到 Wi-fi，然后重启 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-182">If you need to create a new space, connect to Wi-Fi, then restart your HoloLens.</span></span>
- <span data-ttu-id="7d2bd-183">若要查看正确的空间是否处于活动状态，或要手动加载空间，请参阅 **设置**  >  **系统**  >  **空间**。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-183">To see if the correct space is active, or to manually load a space, go to **Settings** > **System** > **Spaces**.</span></span>
- <span data-ttu-id="7d2bd-184">如果加载了正确的空间并且仍有问题，则空间可能已损坏。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-184">If the correct space is loaded and you're still having problems, the space may be corrupt.</span></span> <span data-ttu-id="7d2bd-185">若要解决此问题，请选择该空间，然后选择 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-185">To fix this issue, select the space, then select **Remove**.</span></span> <span data-ttu-id="7d2bd-186">删除空间后，HoloLens 会开始映射你的环境并创建新空间。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-186">After you remove the space, HoloLens starts to map your surroundings and create a new space.</span></span>

[<span data-ttu-id="7d2bd-187">返回到列表</span><span class="sxs-lookup"><span data-stu-id="7d2bd-187">Back to list</span></span>](#list)

## <a name="holograms-disappear-or-are-encased-in-other-holograms-or-objects"></a><span data-ttu-id="7d2bd-188">全息影像或 try</span><span class="sxs-lookup"><span data-stu-id="7d2bd-188">Holograms disappear or are encased in other holograms or objects</span></span>

<span data-ttu-id="7d2bd-189">如果你的全息图太近，则会暂时将其消失 &mdash; ，以便还原全息图，只需离开。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-189">If you get too close to a hologram, it will temporarily disappear&mdash;to restore the hologram, just move away from it.</span></span> <span data-ttu-id="7d2bd-190">此外，如果将多个全息影像放置在一起，某些影像可能会消失。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-190">Also, if you've placed several holograms close together, some may disappear.</span></span> <span data-ttu-id="7d2bd-191">请尝试删除一些。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-191">Try removing a few.</span></span>

<span data-ttu-id="7d2bd-192">还可以通过其他全息影像或对象（如墙壁）阻止或 try 全息影像。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-192">Holograms can also be blocked or encased by other holograms or by objects such as walls.</span></span> <span data-ttu-id="7d2bd-193">如果发生这种情况，请尝试以下修复之一：</span><span class="sxs-lookup"><span data-stu-id="7d2bd-193">If this happens, try one of the following fixes:</span></span>

- <span data-ttu-id="7d2bd-194">如果在另一个全息图中 try 全息图，请将 try 全息图移到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-194">If the hologram is encased in another hologram, move the encased hologram to another location.</span></span> <span data-ttu-id="7d2bd-195">为此，请选择 " **调整**"，然后点击并按住以定位它。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-195">To do this, select **Adjust**, then tap and hold to position it.</span></span>
- <span data-ttu-id="7d2bd-196">如果在墙壁中 try 全息图，请选择 " **调整**"，然后向墙壁方向直到出现全息图。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-196">If the hologram is encased in a wall, select **Adjust**, then walk toward the wall until the hologram appears.</span></span> <span data-ttu-id="7d2bd-197">点击并按住，并向前和向外拉出全息影像。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-197">Tap and hold, then pull the hologram forward and out of the wall.</span></span>
- <span data-ttu-id="7d2bd-198">如果无法通过使用笔势移动全息图，请使用语音将其删除。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-198">If you can't move the hologram by using gestures, use your voice to remove it.</span></span> <span data-ttu-id="7d2bd-199">注视全息图，然后说 "删除"。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-199">Gaze at the hologram, then say "Remove."</span></span> <span data-ttu-id="7d2bd-200">然后重新打开全息图，并将其放在新位置。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-200">Then reopen the hologram and place it in a new location.</span></span>

[<span data-ttu-id="7d2bd-201">返回列表</span><span class="sxs-lookup"><span data-stu-id="7d2bd-201">Back to list</span></span>](#list)

## <a name="holograms-are-appearing-on-the-other-side-of-a-wall"></a><span data-ttu-id="7d2bd-202">全息影像显示在墙的另一侧</span><span class="sxs-lookup"><span data-stu-id="7d2bd-202">Holograms are appearing on the other side of a wall</span></span>

<span data-ttu-id="7d2bd-203">如果你非常靠近墙，或者 HoloLens 尚未扫描墙，则可以看到下一个房间中的全息影像。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-203">If you're very close to a wall, or if HoloLens hasn't scanned the wall yet, you can see holograms that are in the next room.</span></span> <span data-ttu-id="7d2bd-204">若要扫描墙，请站到距离墙 1 到 3 米之间，然后凝视它。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-204">To scan the wall, stand between one and three meters from the wall and gaze at it.</span></span>

<span data-ttu-id="7d2bd-205">当 HoloLens (，黑色或反射对象（例如，在墙附近) 一个黑色长相或反射对象）可能会导致问题。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-205">A black or reflective object (for example, a black couch or a stainless steel refrigerator) near the wall may cause problems when HoloLens tries to scan the wall.</span></span> <span data-ttu-id="7d2bd-206">如果存在此类对象，请扫描墙的另一侧。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-206">If there is such an object, scan the other side of the wall.</span></span>

[<span data-ttu-id="7d2bd-207">返回列表</span><span class="sxs-lookup"><span data-stu-id="7d2bd-207">Back to list</span></span>](#list)

## <a name="after-placing-a-hologram-on-a-wall-it-seems-to-float"></a><span data-ttu-id="7d2bd-208">将全息影像放在墙上后，它似乎已浮动</span><span class="sxs-lookup"><span data-stu-id="7d2bd-208">After placing a hologram on a wall, it seems to float</span></span>

<span data-ttu-id="7d2bd-209">放在墙上的全息影像通常看起来离墙大约一英寸。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-209">A hologram that you place on a wall typically appears to be an inch or so away from the wall.</span></span> <span data-ttu-id="7d2bd-210">如果看起来距离较远，请尝试以下一个或多个修复：</span><span class="sxs-lookup"><span data-stu-id="7d2bd-210">If it appears to be farther away, try one or more of the following fixes:</span></span>

- <span data-ttu-id="7d2bd-211">将全息影像放在墙上时，请从墙 1 到 3 米之间直视墙面。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-211">When you place a hologram on a wall, stand between one and three meters from the wall and face the wall straight on.</span></span>
- <span data-ttu-id="7d2bd-212">通过敲击墙来显示映射网格图形。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-212">Air tap the wall to reveal the mapping mesh graphic.</span></span> <span data-ttu-id="7d2bd-213">确保网格与墙对齐。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-213">Make sure that the mesh aligns with the wall.</span></span> <span data-ttu-id="7d2bd-214">如果没有，请删除全息影像，重新扫描墙，然后重试。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-214">If it doesn't, remove the hologram, rescan the wall, and then try again.</span></span>
- <span data-ttu-id="7d2bd-215">如果问题仍然存在，请运行校准应用。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-215">If the issue persists, run the Calibration app.</span></span> <span data-ttu-id="7d2bd-216">在"设置系统实用工具 **"**  >    >  **中可以找到它**。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-216">You'll find it in **Settings** > **System** > **Utilities**.</span></span>

[<span data-ttu-id="7d2bd-217">返回列表</span><span class="sxs-lookup"><span data-stu-id="7d2bd-217">Back to list</span></span>](#list)

## <a name="apps-appear-too-close-after-moving-them"></a><span data-ttu-id="7d2bd-218">应用在移动后看起来太接近</span><span class="sxs-lookup"><span data-stu-id="7d2bd-218">Apps appear too close after moving them</span></span>

<span data-ttu-id="7d2bd-219">尝试四处浏览并查看放置应用的区域，以便 HoloLens 从不同角度扫描该区域。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-219">Try walking around and looking at the area where you're placing the app so that HoloLens scans the area from different angles.</span></span> <span data-ttu-id="7d2bd-220">[清理设备视器](hololens1-hardware.md#care-and-cleaning) 也可能有所帮助。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-220">[Cleaning your device visor](hololens1-hardware.md#care-and-cleaning) may also help.</span></span>

[<span data-ttu-id="7d2bd-221">返回列表</span><span class="sxs-lookup"><span data-stu-id="7d2bd-221">Back to list</span></span>](#list)

## <a name="reporting-issues-with-unstable-or-inexact-holograms"></a><span data-ttu-id="7d2bd-222">报告不稳定或不精确的全息影像问题</span><span class="sxs-lookup"><span data-stu-id="7d2bd-222">Reporting issues with unstable or inexact holograms</span></span>
 
1. <span data-ttu-id="7d2bd-223">请录制混合现实捕获 [问题](holographic-photos-and-videos.md#capture-a-mixed-reality-video) 的视频。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-223">Please record and a [Mixed Reality Capture video](holographic-photos-and-videos.md#capture-a-mixed-reality-video) of the issue.</span></span> <span data-ttu-id="7d2bd-224">稍后可以通过附加文件反馈中心上传此视频。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-224">This video can be later uploaded through Feedback Hub as an attached file.</span></span>  
1. <span data-ttu-id="7d2bd-225">通过"设置"应用启用完整遥测 ->**隐私** 诊断&反馈，在"可选诊断数据"下确保将切换  ->  设置为 **"打开"** </span><span class="sxs-lookup"><span data-stu-id="7d2bd-225">Enable full telemetry via the **Settings** app -> **Privacy** -> **Diagnostics & feedback** and under **Optional diagnostics data** ensure the toggle is set to **On**</span></span>
1. <span data-ttu-id="7d2bd-226">通过更新到最新的 Windows 全息操作系统（ ([20H2 ](hololens-release-notes.md#windows-holographic-version-20h2)或更高版本）获取最新的全息影像缩放和稳定性) 。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-226">Get the latest hologram scale and stability fixes by updating to the latest [Windows Holographic OS, (20H2 or higher)](hololens-release-notes.md#windows-holographic-version-20h2).</span></span> <span data-ttu-id="7d2bd-227">更新后，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7d2bd-227">After updating perform the following:</span></span>
    1. <span data-ttu-id="7d2bd-228">通过"设置 **"应用删除** 所有全息影像 ->**系统** 全息影像 ->然后选择"删除所有全息影像  ->  "，然后从全新的地图开始。 </span><span class="sxs-lookup"><span data-stu-id="7d2bd-228">Remove all Holograms via **Settings** app -> **System** -> **Holograms** -> then select **Remove all holograms** and start with a fresh map.</span></span>
    1. <span data-ttu-id="7d2bd-229">通过穿过 HoloLens 并四处移动并查看空间内的所有区域与表面，创建空间的新地图。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-229">Create a new map of your space by wearing the HoloLens and walking around your room and looking at all areas and surfaces in the space.</span></span> <span data-ttu-id="7d2bd-230">此操作需要 2-3 分钟。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-230">Do this for 2-3 minutes.</span></span>
    1. <span data-ttu-id="7d2bd-231">执行 IPD 校准。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-231">Perform IPD calibration.</span></span> <span data-ttu-id="7d2bd-232">转到"**设置**  >  **系统**  >  **实用工具"。**</span><span class="sxs-lookup"><span data-stu-id="7d2bd-232">Go to **Settings** > **System** > **Utilities**.</span></span> <span data-ttu-id="7d2bd-233">在 **"校准"** 下，选择 **"打开校准"。**</span><span class="sxs-lookup"><span data-stu-id="7d2bd-233">Under **Calibration**, select **Open Calibration**.</span></span>
    1. <span data-ttu-id="7d2bd-234">重新测试该方案，并查看其是否仍然存在。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-234">Re-test the scenario and see if it still persists.</span></span>
1. <span data-ttu-id="7d2bd-235">如果更新无法解决问题，请提交反馈中心 [问题](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-235">If updating does not fix the issue, please file a [Feedback Hub issue](hololens-feedback.md).</span></span> <span data-ttu-id="7d2bd-236">填写反馈后，可以使用"共享"按钮创建一个可在联系支持人员时发送的易于共享的链接。</span><span class="sxs-lookup"><span data-stu-id="7d2bd-236">After you've filled feedback you can use the **Share** button, to create an easy to share link that can be sent when contacting support.</span></span>

[<span data-ttu-id="7d2bd-237">返回列表</span><span class="sxs-lookup"><span data-stu-id="7d2bd-237">Back to list</span></span>](#list)