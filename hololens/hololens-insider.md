---
title: Microsoft HoloLens 内部预览版
description: 开始使用预览体验计划是很简单的，以便为 HoloLens 的下一个主要操作系统更新提供有价值的反馈。
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.localizationpriority: medium
audience: ITPro
ms.date: 6/29/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: b054b61b269522d673be104ffbda9abc1bc85415
ms.sourcegitcommit: 168a7659420525e5f3e3088d7ce0b5e03c969029
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2020
ms.locfileid: "10860602"
---
# <span data-ttu-id="f4186-103">Microsoft HoloLens 内部预览版</span><span class="sxs-lookup"><span data-stu-id="f4186-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="f4186-104">欢迎使用适用于 HoloLens 的最新预览体验计划预览版！</span><span class="sxs-lookup"><span data-stu-id="f4186-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span>  <span data-ttu-id="f4186-105">这是一种非常简单的功能，可提供针对 HoloLens 的下一个主要操作系统更新的宝贵反馈。</span><span class="sxs-lookup"><span data-stu-id="f4186-105">It's simple to get started and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

<span data-ttu-id="f4186-106">Windows 预览体验成员现在正在移至频道。</span><span class="sxs-lookup"><span data-stu-id="f4186-106">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="f4186-107">**快速**环将成为**开发频道**，**慢速**环将成为**Beta 通道**，并且 "**发布预览**" 环将成为 "**发布" 预览频道**。</span><span class="sxs-lookup"><span data-stu-id="f4186-107">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="f4186-108">映射如下所示：</span><span class="sxs-lookup"><span data-stu-id="f4186-108">Here is what that mapping looks like:</span></span>

![Windows 预览体验计划频道说明](images/WindowsInsiderChannels.png)

<span data-ttu-id="f4186-110">有关详细信息，请执行以下操作： [Windows 博客条目](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)</span><span class="sxs-lookup"><span data-stu-id="f4186-110">For more information: [Windows Blog entry](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels)</span></span>

## <span data-ttu-id="f4186-111">开始接收 Insider 内部版本</span><span class="sxs-lookup"><span data-stu-id="f4186-111">Start receiving Insider builds</span></span>

<span data-ttu-id="f4186-112">在 HoloLens 2 设备上，转到 "**设置**"  ->  **更新 & 安全**  ->  **Windows 预览体验计划**"，然后选择"**开始**"。</span><span class="sxs-lookup"><span data-stu-id="f4186-112">On a HoloLens 2 device go to **Settings** -> **Update & Security** -> **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="f4186-113">将用于注册的帐户链接到 Windows 预览体验成员。</span><span class="sxs-lookup"><span data-stu-id="f4186-113">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="f4186-114">然后，选择 " **Windows 的活动开发**"，选择是要接收**开发渠道**还是**Beta 频道**内部版本，并查看计划条款。</span><span class="sxs-lookup"><span data-stu-id="f4186-114">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="f4186-115">选择 "**确认"-> "立即重启**" 完成操作。</span><span class="sxs-lookup"><span data-stu-id="f4186-115">Select **Confirm -> Restart Now** to finish up.</span></span> <span data-ttu-id="f4186-116">重新启动设备后，转到 "**设置"-> 更新 & 安全 > 检查更新**以获取最新版本。</span><span class="sxs-lookup"><span data-stu-id="f4186-116">After your device has rebooted, go to **Settings -> Update & Security -> Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="f4186-117">停止接收 Insider 内部版本</span><span class="sxs-lookup"><span data-stu-id="f4186-117">Stop receiving Insider builds</span></span>

<span data-ttu-id="f4186-118">如果您不想再收到 Windows 全息版的预览体验计划，则可以在 HoloLens 运行生产内部版本时选择退出，也可以使用高级恢复助理将[设备恢复到](hololens-recovery.md)非预览体验的 windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="f4186-118">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="f4186-119">在手动重新安装新预览版后，从预览体验计划版本注册的用户将遇到蓝屏问题。</span><span class="sxs-lookup"><span data-stu-id="f4186-119">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="f4186-120">之后，他们必须手动恢复其设备。</span><span class="sxs-lookup"><span data-stu-id="f4186-120">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="f4186-121">有关如果你受到影响或不受影响的详细信息，请查看有关此[已知问题](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f4186-121">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="f4186-122">若要验证 HoloLens 是否正在运行生产内部版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f4186-122">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="f4186-123">转到 "**设置" > "系统 >**"，然后找到内部版本号。</span><span class="sxs-lookup"><span data-stu-id="f4186-123">Go to **Settings > System > About**, and find the build number.</span></span>
1. [<span data-ttu-id="f4186-124">请参阅生产内部版本号的发行说明。</span><span class="sxs-lookup"><span data-stu-id="f4186-124">See the release notes for production build numbers.</span></span>](hololens-release-notes.md)

<span data-ttu-id="f4186-125">若要退出预览体验计划内部版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f4186-125">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="f4186-126">在运行生产版本的 HoloLens 上，转到 "**设置" > 更新 Windows 预览体验计划 & 安全 >**，然后选择 "**停止预览体验成员版本**"。</span><span class="sxs-lookup"><span data-stu-id="f4186-126">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="f4186-127">按照说明选择退出您的设备。</span><span class="sxs-lookup"><span data-stu-id="f4186-127">Follow the instructions to opt out your device.</span></span>


## <span data-ttu-id="f4186-128">提供反馈和报告问题</span><span class="sxs-lookup"><span data-stu-id="f4186-128">Provide feedback and report issues</span></span>

<span data-ttu-id="f4186-129">请使用 HoloLens 上[的 "反馈中心" 应用](hololens-feedback.md)提供反馈和报告问题。</span><span class="sxs-lookup"><span data-stu-id="f4186-129">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="f4186-130">使用 "反馈中心" 可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。</span><span class="sxs-lookup"><span data-stu-id="f4186-130">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="f4186-131">必须以相同的方式报告与中文和日语版本的 HoloLens 有关的问题。</span><span class="sxs-lookup"><span data-stu-id="f4186-131">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="f4186-132">请确保接受询问您是否希望 "反馈中心" 访问您的 "文档" 文件夹的提示（在出现提示时选择 **"是"** ）。</span><span class="sxs-lookup"><span data-stu-id="f4186-132">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="f4186-133">适用于开发人员的备注</span><span class="sxs-lookup"><span data-stu-id="f4186-133">Note for developers</span></span>

<span data-ttu-id="f4186-134">欢迎和鼓励你尝试使用 HoloLens 的预览体验成员版本来开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="f4186-134">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="f4186-135">请查看[HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development)以开始使用。</span><span class="sxs-lookup"><span data-stu-id="f4186-135">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="f4186-136">这些相同的说明适用于 HoloLens 的预览体验计划版本。</span><span class="sxs-lookup"><span data-stu-id="f4186-136">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="f4186-137">你可以使用你已用于 HoloLens 开发的 Unity 和 Visual Studio 的相同版本。</span><span class="sxs-lookup"><span data-stu-id="f4186-137">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>


## <span data-ttu-id="f4186-138">Windows 预览体验计划发行说明</span><span class="sxs-lookup"><span data-stu-id="f4186-138">Windows Insider Release Notes</span></span>

<span data-ttu-id="f4186-139">从我们的[Windows 全息版2020更新](hololens-release-notes.md)版本，我们的所有版本预览功能现已推出。</span><span class="sxs-lookup"><span data-stu-id="f4186-139">As of our [Windows Holographic May 2020 Update](hololens-release-notes.md) release all of our release preview features are now generally available!</span></span> <span data-ttu-id="f4186-140">请确保[更新 HoloLens](hololens-update-hololens.md)以获取所有最新功能。</span><span class="sxs-lookup"><span data-stu-id="f4186-140">Make sure to [update your HoloLens](hololens-update-hololens.md) to get all the latest features.</span></span>

<span data-ttu-id="f4186-141">我们将再次通过新功能再次更新此页面，因为我们将这些新功能发布给 Windows 预览体验成员内部版本。</span><span class="sxs-lookup"><span data-stu-id="f4186-141">We'll be updating this page again with new features again as we release them to Windows Insider builds.</span></span>


### <span data-ttu-id="f4186-142">自动目视位置支持</span><span class="sxs-lookup"><span data-stu-id="f4186-142">Auto Eye Position Support</span></span>

<span data-ttu-id="f4186-143">在 HoloLens 2 中，目视位置支持准确的全息图定位、舒适的查看体验和改进的显示质量。</span><span class="sxs-lookup"><span data-stu-id="f4186-143">In HoloLens 2, eye positions enable accurate hologram positioning, comfortable viewing experience and improved display quality.</span></span> <span data-ttu-id="f4186-144">眼位置将作为眼睛跟踪结果的一部分进行计算。</span><span class="sxs-lookup"><span data-stu-id="f4186-144">Eye positions are computed as part of the eye tracking result.</span></span> <span data-ttu-id="f4186-145">但是，这要求每个用户都可以通过目视跟踪校准，即使体验不需要目视的注视输入也是如此。</span><span class="sxs-lookup"><span data-stu-id="f4186-145">However, this requires each user to go through eye tracking calibration, even when the experience does not require eye gaze input.</span></span>

<span data-ttu-id="f4186-146">**自动目视位置（AEP）** 通过交互方式为用户计算眼睛位置支持这些方案。</span><span class="sxs-lookup"><span data-stu-id="f4186-146">**Auto Eye Position (AEP)** enables these scenarios with an interaction-free way to compute eye positions for the user.</span></span>  <span data-ttu-id="f4186-147">自动目视位置在用户将设备置于设备上时自动从后台开始工作。</span><span class="sxs-lookup"><span data-stu-id="f4186-147">Auto Eye Position starts working in the background automatically from the moment the user puts the device on.</span></span> <span data-ttu-id="f4186-148">如果用户没有以前的目视跟踪校准，则在较小的处理时间后，自动目视的位置将开始向显示系统提供用户的目视位置。</span><span class="sxs-lookup"><span data-stu-id="f4186-148">If the user does not have a prior eye tracking calibration, Auto Eye position will start providing the user's eye positions to the display system after a small processing time.</span></span> <span data-ttu-id="f4186-149">此处理时间通常介于 20-60 秒之间。</span><span class="sxs-lookup"><span data-stu-id="f4186-149">This processing time typically is between 20 - 60 seconds.</span></span> <span data-ttu-id="f4186-150">用户数据不会保留在设备上，因此，如果用户关闭并重新放置设备或者设备重新启动或从睡眠中唤醒，则会重复此过程。</span><span class="sxs-lookup"><span data-stu-id="f4186-150">The user data is not persisted on the device and hence this process is repeated if the user takes off and puts the device back on or if the device reboots or wakes up from sleep.</span></span>  

<span data-ttu-id="f4186-151">当 uncalibrated 用户放在设备上时，有一些系统行为发生了自动目视定位功能。</span><span class="sxs-lookup"><span data-stu-id="f4186-151">There are a few system behavior changes with Auto Eye Position feature when an uncalibrated user puts on the device.</span></span> <span data-ttu-id="f4186-152">Uncalibrated 用户指的是尚未经历过设备上的目视跟踪校准过程的人。</span><span class="sxs-lookup"><span data-stu-id="f4186-152">An uncalibrated user refers to someone who has not gone through the eye tracking calibration process on the device previously.</span></span>

|     <span data-ttu-id="f4186-153">活动应用程序</span><span class="sxs-lookup"><span data-stu-id="f4186-153">Active Application</span></span>                           |     <span data-ttu-id="f4186-154">当前行为</span><span class="sxs-lookup"><span data-stu-id="f4186-154">Current Behavior</span></span>                                   |     <span data-ttu-id="f4186-155">来自 Windows 预览体验成员内部版本19041.1339 的行为 +</span><span class="sxs-lookup"><span data-stu-id="f4186-155">Behavior from Windows Insider   build 19041.1339+</span></span>                                                      |
|--------------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="f4186-156">不支持注视的应用程序或全息外壳</span><span class="sxs-lookup"><span data-stu-id="f4186-156">Non-gaze enabled app or Holographic Shell</span></span>    |     <span data-ttu-id="f4186-157">将显示目视跟踪校准提示。</span><span class="sxs-lookup"><span data-stu-id="f4186-157">Eye tracking calibration prompt is   displayed.</span></span>    |     <span data-ttu-id="f4186-158">不显示提示。</span><span class="sxs-lookup"><span data-stu-id="f4186-158">No prompt is displayed.</span></span>                                                                                |
|     <span data-ttu-id="f4186-159">注视 "已启用" 应用</span><span class="sxs-lookup"><span data-stu-id="f4186-159">Gaze enabled app</span></span>                             |     <span data-ttu-id="f4186-160">将显示目视跟踪校准提示。</span><span class="sxs-lookup"><span data-stu-id="f4186-160">Eye tracking calibration prompt is   displayed.</span></span>    |     <span data-ttu-id="f4186-161">仅当应用程序访问眼睛注视流时，才会显示目视跟踪校准提示。</span><span class="sxs-lookup"><span data-stu-id="f4186-161">Eye tracking calibration prompt is   displayed only when the application accesses eye gaze stream.</span></span>     |

 <span data-ttu-id="f4186-162">如果用户从一个不支持注视的应用程序切换到一个访问注视数据的应用程序，则将显示校准提示。</span><span class="sxs-lookup"><span data-stu-id="f4186-162">If the user transitions from a non-gaze enabled application to one that accesses the gaze data, the calibration prompt will be displayed.</span></span> <span data-ttu-id="f4186-163">将不会更改为 "现成的体验" 流程。</span><span class="sxs-lookup"><span data-stu-id="f4186-163">There will be no changed to Out Of Box Experience flow.</span></span> 
 
<span data-ttu-id="f4186-164">对于需要眼睛眼数据或非常精确的全息图位置的体验，我们建议 uncalibrated 用户从目视跟踪校准提示中运行目视跟踪校准，或者从 "开始" 菜单启动 "设置" 应用，然后选择 "**系统 > 校准" > 目视校准 > "运行目视校准**"。</span><span class="sxs-lookup"><span data-stu-id="f4186-164">For experiences that require eye gaze data or very precise hologram positioning, we recommend uncalibrated users to run eye tracking calibration from the eye tracking calibration prompt or by launching the Settings app from the start menu, and then selecting **System > Calibration > Eye Calibration > Run eye calibration**.</span></span>

**<span data-ttu-id="f4186-165">已知问题</span><span class="sxs-lookup"><span data-stu-id="f4186-165">Known issues</span></span>**
1.  <span data-ttu-id="f4186-166">我们正在调查 "目视跟踪器驱动程序" 在较高内存负载下运行时可能会崩溃的问题。</span><span class="sxs-lookup"><span data-stu-id="f4186-166">We're investigating an issue where the eye tracker driver host process could crash when running under heavy memory load.</span></span> <span data-ttu-id="f4186-167">目视跟踪驱动程序主机进程应自动恢复。</span><span class="sxs-lookup"><span data-stu-id="f4186-167">The eye tracking driver host process should auto recover.</span></span>

## <span data-ttu-id="f4186-168">FFU 下载和快闪路线</span><span class="sxs-lookup"><span data-stu-id="f4186-168">FFU download and flash directions</span></span>
<span data-ttu-id="f4186-169">若要使用带流量签名的 ffu 进行测试，首先必须在闪烁已签名的 ffu 之前，再将设备解锁。</span><span class="sxs-lookup"><span data-stu-id="f4186-169">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="f4186-170">在 PC 上</span><span class="sxs-lookup"><span data-stu-id="f4186-170">On PC</span></span>
    1. <span data-ttu-id="f4186-171">从以下计算机下载 ffu：[https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)</span><span class="sxs-lookup"><span data-stu-id="f4186-171">Download ffu to your PC from: [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)</span></span>
    1. <span data-ttu-id="f4186-172">从 Microsoft Store 安装 ARC （高级恢复助理）：[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="f4186-172">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
1. <span data-ttu-id="f4186-173">在 HoloLens-航班解锁：打开**设置**  >  **更新 & 安全**  >  **Windows 预览体验计划**，然后注册，重新启动设备</span><span class="sxs-lookup"><span data-stu-id="f4186-173">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device</span></span>
1. <span data-ttu-id="f4186-174">Flash FFU-现在，你可以使用 ARC 对已签名的 FFU 进行闪烁</span><span class="sxs-lookup"><span data-stu-id="f4186-174">Flash FFU - Now you can flash the flight signed FFU using ARC</span></span>
