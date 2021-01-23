---
title: HoloLens 已知问题
description: 及时了解使用 Unity 和 Windows Device Portal 的可能影响 HoloLens 客户和开发人员的已知问题和解决方法列表。
keywords: 疑难解答， 已知问题， 帮助
author: mattzmsft
ms.author: mazeller
ms.date: 11/30/2020
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
- HoloLens 2
ms.openlocfilehash: 54bc090352983e814c64deea8f1f401c24e3261b
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11284073"
---
# <span data-ttu-id="77fac-104">HoloLens 已知问题</span><span class="sxs-lookup"><span data-stu-id="77fac-104">Known issues for HoloLens</span></span>

<span data-ttu-id="77fac-105">这是 HoloLens 设备的已知问题的当前列表。</span><span class="sxs-lookup"><span data-stu-id="77fac-105">This is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="77fac-106">如果看到奇数行为，请首先查看此处。</span><span class="sxs-lookup"><span data-stu-id="77fac-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="77fac-107">随着发现或报告新问题，或在将来的 HoloLens 软件更新中解决问题，此列表将保持更新。</span><span class="sxs-lookup"><span data-stu-id="77fac-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="77fac-108">如果你发现未阻止的问题，请通过反馈中心在 HoloLens 设备上 [报告它](hololens-feedback.md)。</span><span class="sxs-lookup"><span data-stu-id="77fac-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="77fac-109">如果你所面临的问题是阻止你，除了归档反馈外， [请提交支持请求](https://aka.ms/hlsupport)。</span><span class="sxs-lookup"><span data-stu-id="77fac-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>

- [<span data-ttu-id="77fac-110">所有 HoloLens 代的已知问题</span><span class="sxs-lookup"><span data-stu-id="77fac-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="77fac-111">HoloLens 2 设备的已知问题</span><span class="sxs-lookup"><span data-stu-id="77fac-111">Known issues for HoloLens 2 devices</span></span>](#known-issues-for-hololens-2-devices)
- [<span data-ttu-id="77fac-112">HoloLens 第一代 (已知) </span><span class="sxs-lookup"><span data-stu-id="77fac-112">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)
- [<span data-ttu-id="77fac-113">HoloLens 仿真器已知问题</span><span class="sxs-lookup"><span data-stu-id="77fac-113">Known issues for HoloLens emulator</span></span>](#known-issues-for-hololens-emulator)

## <span data-ttu-id="77fac-114">所有 HoloLens 代的已知问题</span><span class="sxs-lookup"><span data-stu-id="77fac-114">Known issues for all HoloLens generations</span></span>

### <span data-ttu-id="77fac-115">Unity</span><span class="sxs-lookup"><span data-stu-id="77fac-115">Unity</span></span>

- <span data-ttu-id="77fac-116">请参阅 [安装适用于](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) HoloLens 开发建议最新版本的 Unity 的工具。</span><span class="sxs-lookup"><span data-stu-id="77fac-116">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="77fac-117">Unity HoloLens Technical Preview 的已知问题记录在 [HoloLens Unity 论坛中](https://forum.unity3d.com/threads/known-issues.394627/)。</span><span class="sxs-lookup"><span data-stu-id="77fac-117">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <span data-ttu-id="77fac-118">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="77fac-118">Windows Device Portal</span></span>

- <span data-ttu-id="77fac-119">混合现实捕获中的实时预览功能可能会显示几秒钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="77fac-119">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="77fac-120">在"虚拟输入"页上，"虚拟手势"部分下的"手势"和"滚动"控件不起作用。</span><span class="sxs-lookup"><span data-stu-id="77fac-120">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="77fac-121">使用它们将不起作用。</span><span class="sxs-lookup"><span data-stu-id="77fac-121">Using them will have no effect.</span></span> <span data-ttu-id="77fac-122">同一页面上的虚拟键盘可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="77fac-122">The virtual keyboard on the same page works correctly.</span></span>

- <span data-ttu-id="77fac-123">在"设置"中启用开发人员模式后，可能需要几秒钟的时间才能启用打开 Device Portal 的开关。</span><span class="sxs-lookup"><span data-stu-id="77fac-123">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <span data-ttu-id="77fac-124">OneDrive 相机上传</span><span class="sxs-lookup"><span data-stu-id="77fac-124">OneDrive camera upload</span></span>

<span data-ttu-id="77fac-125">适用于 HoloLens 的 OneDrive 应用不支持工作或学校帐户的自动相机上载。</span><span class="sxs-lookup"><span data-stu-id="77fac-125">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="77fac-126">解决方法：</span><span class="sxs-lookup"><span data-stu-id="77fac-126">Workarounds:</span></span>

- <span data-ttu-id="77fac-127">如果适用于你的企业，则 Microsoft 消费者帐户支持自动相机上载。</span><span class="sxs-lookup"><span data-stu-id="77fac-127">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="77fac-128">除了工作或学校帐户外，还可以登录 Microsoft 帐户 (OneDrive 应用支持双重登录) 。</span><span class="sxs-lookup"><span data-stu-id="77fac-128">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="77fac-129">在 OneDrive 内的 Microsoft 帐户配置文件中，你可以启用自动后台相机照片上传。</span><span class="sxs-lookup"><span data-stu-id="77fac-129">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="77fac-130">如果无法安全地使用消费者 Microsoft 帐户自动上传照片，可以从 OneDrive 应用手动将照片上传到工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="77fac-130">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="77fac-131">为此，请确保你已登录到 OneDrive 应用中的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="77fac-131">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="77fac-132">选择该 **+** 按钮，然后选择"**上载"。**</span><span class="sxs-lookup"><span data-stu-id="77fac-132">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="77fac-133">通过导航到"图片"或"相机照片"> **要上载的照片或视频**。</span><span class="sxs-lookup"><span data-stu-id="77fac-133">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="77fac-134">选择要上载的照片或视频，然后选择"打开 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="77fac-134">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <span data-ttu-id="77fac-135">HoloLens 2 设备的已知问题</span><span class="sxs-lookup"><span data-stu-id="77fac-135">Known issues for HoloLens 2 devices</span></span>

### <span data-ttu-id="77fac-136">Microsoft Edge 无法启动</span><span class="sxs-lookup"><span data-stu-id="77fac-136">Microsoft Edge fails to launch</span></span>

<span data-ttu-id="77fac-137">一些客户报告了 Microsoft Edge 无法启动的问题。</span><span class="sxs-lookup"><span data-stu-id="77fac-137">A few customers have reported an issue where Microsoft Edge fails to launch.</span></span> <span data-ttu-id="77fac-138">对于这些客户，此问题通过重新启动而仍然存在，并且无法通过 Windows 或应用程序更新解决。</span><span class="sxs-lookup"><span data-stu-id="77fac-138">For these customers, the issue persists through reboot and is not resolved with Windows or application updates.</span></span> <span data-ttu-id="77fac-139">如果你遇到此问题，并且已确认[Windows](hololens-updates.md#manually-check-for-updates)是最新的，请从反馈中心应用提交具有以下类别和子类别的 Bug：[](hololens-feedback.md)安装和更新 > 下载、安装和配置 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="77fac-139">If you're experiencing this issue and you've confirmed [Windows is up-to-date](hololens-updates.md#manually-check-for-updates), please file a bug from the [Feedback Hub app](hololens-feedback.md) with the following category and sub-category: Install and Update > Downloading, installing, and configuring Windows Update.</span></span>

<span data-ttu-id="77fac-140">没有已知的解决方法，因为到目前为止，我们一直无法找出问题的根本原因。</span><span class="sxs-lookup"><span data-stu-id="77fac-140">There are no known workarounds as we've been unable to root cause the issue so far.</span></span> <span data-ttu-id="77fac-141">通过反馈中心归档 Bug 将有助于我们的调查！</span><span class="sxs-lookup"><span data-stu-id="77fac-141">Filing a bug via Feedback Hub will help our investigation!</span></span>

### <span data-ttu-id="77fac-142">键盘不切换到特殊字符</span><span class="sxs-lookup"><span data-stu-id="77fac-142">Keyboard does not switch to special characters</span></span>

<span data-ttu-id="77fac-143">OOBE 期间存在一个问题，在用户选择工作或学校帐户并输入其密码后，尝试通过点击 &123 按钮切换到键盘上的特殊字符不会更改为特殊字符。</span><span class="sxs-lookup"><span data-stu-id="77fac-143">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> 

<span data-ttu-id="77fac-144">工作：：</span><span class="sxs-lookup"><span data-stu-id="77fac-144">Work-arounds:</span></span>
-   <span data-ttu-id="77fac-145">关闭键盘，然后通过点击文本字段重新打开它。</span><span class="sxs-lookup"><span data-stu-id="77fac-145">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="77fac-146">输入的密码不正确。</span><span class="sxs-lookup"><span data-stu-id="77fac-146">Incorrectly enter your password.</span></span> <span data-ttu-id="77fac-147">下次重新启动键盘时，键盘将正常工作。</span><span class="sxs-lookup"><span data-stu-id="77fac-147">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="77fac-148">Web 身份验证，关闭键盘，然后选择 **"从另一台设备登录"。**</span><span class="sxs-lookup"><span data-stu-id="77fac-148">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span> 
-   <span data-ttu-id="77fac-149">如果仅输入数字，用户可以长按某些键以打开展开的菜单。</span><span class="sxs-lookup"><span data-stu-id="77fac-149">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="77fac-150">使用 USB 键盘。</span><span class="sxs-lookup"><span data-stu-id="77fac-150">Using a USB keyboard.</span></span>

<span data-ttu-id="77fac-151">这不会影响：</span><span class="sxs-lookup"><span data-stu-id="77fac-151">This does not affect:</span></span>
- <span data-ttu-id="77fac-152">选择使用个人帐户的用户。</span><span class="sxs-lookup"><span data-stu-id="77fac-152">Users who choose to use a personal account.</span></span>

### <span data-ttu-id="77fac-153">从预览体验成员预览版注销后，在使用预览体验成员内部版本重新更新的设备上显示蓝屏</span><span class="sxs-lookup"><span data-stu-id="77fac-153">Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with a Insider build</span></span>

<span data-ttu-id="77fac-154">This is an issue affecting that affects users who are on an Insider preview build， reflashed their HoloLens 2 with a new insider preview build， and then unenrolled from the Insider program.</span><span class="sxs-lookup"><span data-stu-id="77fac-154">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> 

<span data-ttu-id="77fac-155">这不会影响：</span><span class="sxs-lookup"><span data-stu-id="77fac-155">This does not affect:</span></span>
- <span data-ttu-id="77fac-156">未在 Windows 预览体验成员中注册的用户</span><span class="sxs-lookup"><span data-stu-id="77fac-156">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="77fac-157">预览体验成员：</span><span class="sxs-lookup"><span data-stu-id="77fac-157">Insiders:</span></span>
    - <span data-ttu-id="77fac-158">如果设备自预览体验成员版本版本 18362.x 起已注册</span><span class="sxs-lookup"><span data-stu-id="77fac-158">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="77fac-159">如果他们刷新了预览体验成员签名的 19041.x 版本，并一直注册预览体验计划</span><span class="sxs-lookup"><span data-stu-id="77fac-159">If they flashed a Insider signed 19041.x build AND stay enrolled in the Insider program</span></span> 

<span data-ttu-id="77fac-160">工作：</span><span class="sxs-lookup"><span data-stu-id="77fac-160">Work-around:</span></span> 
- <span data-ttu-id="77fac-161">避免此问题</span><span class="sxs-lookup"><span data-stu-id="77fac-161">Avoid the issue</span></span> 
    - <span data-ttu-id="77fac-162">刷新非内部版本。</span><span class="sxs-lookup"><span data-stu-id="77fac-162">Flash a non-insider build.</span></span> <span data-ttu-id="77fac-163">每月定期更新之一。</span><span class="sxs-lookup"><span data-stu-id="77fac-163">One of the regular monthly updates.</span></span> 
    - <span data-ttu-id="77fac-164">保持预览体验成员</span><span class="sxs-lookup"><span data-stu-id="77fac-164">Stay on Insider Preview</span></span>
- <span data-ttu-id="77fac-165">重新放大设备</span><span class="sxs-lookup"><span data-stu-id="77fac-165">Reflash the device</span></span>

    1. <span data-ttu-id="77fac-166">在未连接时完全关闭电源，将 [HoloLens 2](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) 手动置于闪烁模式。</span><span class="sxs-lookup"><span data-stu-id="77fac-166">Put the [HoloLens 2 into flashing mode](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manually by fully powering down while not connect.</span></span> <span data-ttu-id="77fac-167">然后，在保持音量的同时，点击电源按钮。</span><span class="sxs-lookup"><span data-stu-id="77fac-167">Then while holding Volume up, tap the Power button.</span></span>
    
    1. <span data-ttu-id="77fac-168">连接到电脑并打开"高级恢复助手"。</span><span class="sxs-lookup"><span data-stu-id="77fac-168">Connect to the PC and open Advanced Recovery Companion.</span></span> 
    
    1. <span data-ttu-id="77fac-169">将 HoloLens 2 闪烁为默认版本。</span><span class="sxs-lookup"><span data-stu-id="77fac-169">Flash the HoloLens 2 to the default build.</span></span>   

## <span data-ttu-id="77fac-170">HoloLens 第一代 (已知) </span><span class="sxs-lookup"><span data-stu-id="77fac-170">Known issues for HoloLens (1st Gen)</span></span>

### <span data-ttu-id="77fac-171">无法通过客户端连接到 HoloLens Visual Studio</span><span class="sxs-lookup"><span data-stu-id="77fac-171">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="77fac-172">Last Update： 8/8 @ 5：11PM - Visual Studio 已发布 VS 2019 版本 16.2，其中包括解决此问题的修补程序。</span><span class="sxs-lookup"><span data-stu-id="77fac-172">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="77fac-173">我们建议更新到此最新版本以避免遇到此错误。</span><span class="sxs-lookup"><span data-stu-id="77fac-173">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="77fac-174">Visual Studio VS 2019 版本 16.2，其中包含解决此问题的修补程序。</span><span class="sxs-lookup"><span data-stu-id="77fac-174">Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="77fac-175">我们建议更新到此最新版本以避免遇到此错误。</span><span class="sxs-lookup"><span data-stu-id="77fac-175">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="77fac-176">问题的根本原因：使用 Visual Studio 2015 或早期版本的 Visual Studio 2017 在 HoloLens 上部署和调试应用程序，然后使用具有相同 HoloLens 的 Visual Studio 2017 或 Visual Studio 2019 的最新版本的用户将受到影响。</span><span class="sxs-lookup"><span data-stu-id="77fac-176">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="77fac-177">较新版本的 Visual Studio部署新版本的组件，但较旧版本的文件将留在设备上，从而导致较新版本失败。</span><span class="sxs-lookup"><span data-stu-id="77fac-177">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="77fac-178">这将导致以下错误消息：DEP0100：请确保目标设备已启用开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="77fac-178">This causes the following error message: DEP0100: Please ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="77fac-179">由于错误 \<ip\> 80004005，无法获取开发人员许可证。</span><span class="sxs-lookup"><span data-stu-id="77fac-179">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <span data-ttu-id="77fac-180">解决方法</span><span class="sxs-lookup"><span data-stu-id="77fac-180">Workaround</span></span>

<span data-ttu-id="77fac-181">Our team is currently working on a fix.</span><span class="sxs-lookup"><span data-stu-id="77fac-181">Our team is currently working on a fix.</span></span> <span data-ttu-id="77fac-182">在此期间，可以使用以下步骤解决该问题，并帮助取消阻止部署和调试：</span><span class="sxs-lookup"><span data-stu-id="77fac-182">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="77fac-183">打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="77fac-183">Open Visual Studio.</span></span>

1. <span data-ttu-id="77fac-184">选择 **"**  >  **文件新建**  >  **项目"。**</span><span class="sxs-lookup"><span data-stu-id="77fac-184">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="77fac-185">选择**Visual C#**  >  **Windows 桌面**  >  \*\*控制台应用 (.NET Framework) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="77fac-185">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="77fac-186">为项目命名 (例如"HoloLensDeploymentFix") 并确保框架至少设置为 .NET Framework 4.5，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="77fac-186">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="77fac-187">右键单击解决方案\*\*\*\* 资源管理器中的"引用"节点，将以下引用 ("浏览"部分，然后选择\*\*\*\*"浏览) ： \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="77fac-187">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="77fac-188">如果未安装 10.0.18362.0，请使用最新版本。</span><span class="sxs-lookup"><span data-stu-id="77fac-188">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span> 

1. <span data-ttu-id="77fac-189">右键单击解决方案资源管理器中的项目，然后选择 **"添加**  >  **现有项目"。**</span><span class="sxs-lookup"><span data-stu-id="77fac-189">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="77fac-190">浏览到 C：\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86，将筛选器更改为所有\*\*文件 (\*.\*) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="77fac-190">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="77fac-191">选择"SirepClient.dll和SshClient.dll，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="77fac-191">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="77fac-192">在解决方案资源管理器中查找并选择这两个文件 (它们应位于文件列表的底部) 将"属性"窗口中的"复制到输出目录"\*\*\*\* 更改为"始终**复制"。** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="77fac-192">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="77fac-193">在文件顶部，将以下内容添加到现有语句 `using` 列表中：</span><span class="sxs-lookup"><span data-stu-id="77fac-193">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="77fac-194">在 `static void Main(...)` 内部，添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="77fac-194">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="77fac-195">选择**生成**  >  **解决方案**。</span><span class="sxs-lookup"><span data-stu-id="77fac-195">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="77fac-196">打开命令提示符窗口，将 cd 打开到包含已编译的 .exe 文件 (例如 C：\MyProjects\HoloLensDeploymentFix\bin\Debug) 。</span><span class="sxs-lookup"><span data-stu-id="77fac-196">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="77fac-197">运行可执行文件，并提供设备的 IP 地址作为命令行参数。</span><span class="sxs-lookup"><span data-stu-id="77fac-197">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="77fac-198"> (如果使用 USB 进行连接，可以使用 127.0.0.1，否则使用设备的 Wi-Fi IP 地址。) 例如，"HoloLensDeploymentFix 127.0.0.1"。</span><span class="sxs-lookup"><span data-stu-id="77fac-198">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="77fac-199">在该工具退出后，没有任何消息 (此操作仅需要几秒钟) ，现在您将能够从 Visual Studio 2017 或更高版本进行部署和调试。</span><span class="sxs-lookup"><span data-stu-id="77fac-199">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="77fac-200">不需要继续使用该工具。</span><span class="sxs-lookup"><span data-stu-id="77fac-200">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="77fac-201">我们将在更新可用时提供进一步更新。</span><span class="sxs-lookup"><span data-stu-id="77fac-201">We will provide further updates as they become available.</span></span>

### <span data-ttu-id="77fac-202">在 HoloLens 上启动 Microsoft Store 和应用时的问题</span><span class="sxs-lookup"><span data-stu-id="77fac-202">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="77fac-203">上次更新：4/2 @ 10 AM - 问题已解决。</span><span class="sxs-lookup"><span data-stu-id="77fac-203">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span> 

<span data-ttu-id="77fac-204">尝试在 HoloLens 上启动 Microsoft Store 和应用时可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="77fac-204">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="77fac-205">我们已确定当后台应用更新在一个或多个从属应用仍在运行时以特定顺序部署较新版本的框架包时，会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="77fac-205">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="77fac-206">在这种情况下，自动应用更新将新版本的 .NET Native Framework (版本 10.0.25531 传递到 10.0.27413) 导致正在运行的应用无法正确更新使用以前版本的框架的所有正在运行的应用。</span><span class="sxs-lookup"><span data-stu-id="77fac-206">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="77fac-207">框架更新流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="77fac-207">The flow for framework update is as follows:</span></span> 

1. <span data-ttu-id="77fac-208">新框架包从应用商店下载并安装。</span><span class="sxs-lookup"><span data-stu-id="77fac-208">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="77fac-209">使用旧框架的所有应用都"更新"为使用较新版本。</span><span class="sxs-lookup"><span data-stu-id="77fac-209">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="77fac-210">如果步骤 2 在完成之前中断，则任何未注册较新框架的应用将无法从"开始"菜单启动。</span><span class="sxs-lookup"><span data-stu-id="77fac-210">If step 2 is interrupted before completion then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="77fac-211">我们认为 HoloLens 上的任何应用都可能会受此问题的影响。</span><span class="sxs-lookup"><span data-stu-id="77fac-211">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="77fac-212">一些用户已报告关闭挂起的应用并启动其他应用（如反馈中心、3D 查看器或照片）可解决他们的问题，但是，这 &mdash; 100% 不起作用。</span><span class="sxs-lookup"><span data-stu-id="77fac-212">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them&mdash;however, this does not work 100% of the time.</span></span>

<span data-ttu-id="77fac-213">我们已找到根本原因，导致此问题不是由更新本身引起的，而是操作系统中的一个缺陷，导致未正确处理 .NET Native framework 更新。</span><span class="sxs-lookup"><span data-stu-id="77fac-213">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="77fac-214">我们很高兴地宣布我们已确定修补程序，并发布了包含 (操作系统版本 17763.380) 更新。</span><span class="sxs-lookup"><span data-stu-id="77fac-214">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="77fac-215">若要了解你的设备能否接受更新，请：</span><span class="sxs-lookup"><span data-stu-id="77fac-215">To see if your device can take the update, please:</span></span>

1. <span data-ttu-id="77fac-216">转到"设置"应用并打开"&**安全"。**</span><span class="sxs-lookup"><span data-stu-id="77fac-216">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="77fac-217">选择 **"检查更新"。**</span><span class="sxs-lookup"><span data-stu-id="77fac-217">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="77fac-218">如果更新到 17763.380 可用，请更新到此内部版本，以接收应用挂起 Bug 的修复。</span><span class="sxs-lookup"><span data-stu-id="77fac-218">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="77fac-219">更新到此版本的操作系统后，应用应能正常工作。</span><span class="sxs-lookup"><span data-stu-id="77fac-219">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="77fac-220">此外，与处理每个 HoloLens 操作系统版本一样，我们已将 FFU 映像张贴到 [Microsoft 下载中心](https://aka.ms/hololensdownload/10.0.17763.380)。</span><span class="sxs-lookup"><span data-stu-id="77fac-220">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="77fac-221">如果你不希望进行更新，我们自 2019 年 3 月 29 日发布新版本的 Microsoft Store UWP 应用。</span><span class="sxs-lookup"><span data-stu-id="77fac-221">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="77fac-222">拥有应用商店的更新版本后：</span><span class="sxs-lookup"><span data-stu-id="77fac-222">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="77fac-223">打开应用商店并确认它已加载。</span><span class="sxs-lookup"><span data-stu-id="77fac-223">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="77fac-224">使用花红手势打开菜单。</span><span class="sxs-lookup"><span data-stu-id="77fac-224">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="77fac-225">尝试打开以前损坏的应用。</span><span class="sxs-lookup"><span data-stu-id="77fac-225">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="77fac-226">如果仍然无法启动，请点击并按住损坏应用的图标，然后选择卸载。</span><span class="sxs-lookup"><span data-stu-id="77fac-226">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="77fac-227">从应用商店重新安装这些应用。</span><span class="sxs-lookup"><span data-stu-id="77fac-227">Re-install these apps from the store.</span></span>

<span data-ttu-id="77fac-228">如果你的设备仍然无法加载应用，你可以按照以下步骤通过下载中心旁加载 .NET Native Framework 和运行时的版本：</span><span class="sxs-lookup"><span data-stu-id="77fac-228">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="77fac-229">请从 Microsoft [下载中心](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 下载此 zip 文件。</span><span class="sxs-lookup"><span data-stu-id="77fac-229">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="77fac-230">解压缩将生成两个文件。</span><span class="sxs-lookup"><span data-stu-id="77fac-230">Unzipping will produce two files.</span></span>  <span data-ttu-id="77fac-231">Microsoft.NET.Native.Runtime.1.7.appx 和 Microsoft.NET.Native.Framework.1.7.appx。</span><span class="sxs-lookup"><span data-stu-id="77fac-231">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="77fac-232">请验证你的设备是否解锁了开发。</span><span class="sxs-lookup"><span data-stu-id="77fac-232">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="77fac-233">如果你之前没有这样做，请参阅使用 Windows [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 了解说明。</span><span class="sxs-lookup"><span data-stu-id="77fac-233">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="77fac-234">然后，你想要进入 Windows Device Portal。</span><span class="sxs-lookup"><span data-stu-id="77fac-234">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="77fac-235">我们的建议是使用 USB 进行此操作，你将通过键入浏览器 http://127.0.0.1:10080 来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="77fac-235">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="77fac-236">安装 Windows Device Portal 后，我们需要你"旁加载"你下载的两个文件。</span><span class="sxs-lookup"><span data-stu-id="77fac-236">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="77fac-237">为此，你需要转到左侧栏，直到到达"应用"部分并选择"**应用"。** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="77fac-237">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="77fac-238">然后，你将看到类似于下面的屏幕。</span><span class="sxs-lookup"><span data-stu-id="77fac-238">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="77fac-239">你想要转到"安装应用"部分，并\*\*\*\* 浏览到解压缩这两个 APPX 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="77fac-239">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="77fac-240">一次只能执行一个操作，因此选择第一个后，单击"部署"部分下的"转到"。</span><span class="sxs-lookup"><span data-stu-id="77fac-240">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="77fac-241">然后为第二个 APPX 文件执行此操作。</span><span class="sxs-lookup"><span data-stu-id="77fac-241">Then do this for the second APPX file.</span></span>

   ![Windows Device Portal 以安装Side-Loaded应用](images/20190322-DevicePortal.png)
   
1. <span data-ttu-id="77fac-243">此时，我们认为你的应用程序应该重新开始工作，并且你还可访问应用商店。</span><span class="sxs-lookup"><span data-stu-id="77fac-243">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="77fac-244">在某些情况下，在受影响的应用启动之前，必须运行启动 3D 查看器应用的额外步骤。</span><span class="sxs-lookup"><span data-stu-id="77fac-244">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span> 

<span data-ttu-id="77fac-245">感谢你耐心等待，在我们完成解决此问题的过程中，并期待继续与社区合作，以创造成功的混合现实体验。</span><span class="sxs-lookup"><span data-stu-id="77fac-245">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <span data-ttu-id="77fac-246">设备更新</span><span class="sxs-lookup"><span data-stu-id="77fac-246">Device Update</span></span>

- <span data-ttu-id="77fac-247">新更新后 30 秒，命令行管理程序可能会消失一次。</span><span class="sxs-lookup"><span data-stu-id="77fac-247">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="77fac-248">Please perform the **bloom** gesture to resume your session.</span><span class="sxs-lookup"><span data-stu-id="77fac-248">Please perform the **bloom** gesture to resume your session.</span></span>

### <span data-ttu-id="77fac-249">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="77fac-249">Visual Studio</span></span>

- <span data-ttu-id="77fac-250">请参阅 [安装适用于](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) HoloLens 开发Visual Studio最新版本的工具。</span><span class="sxs-lookup"><span data-stu-id="77fac-250">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="77fac-251">将应用从 Visual Studio 部署到 HoloLens 时，你可能会看到错误：无法在用户映射分区打开的文件上执行请求的操作 \*\*。 (HRESULT 的异常：0x800704C8) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="77fac-251">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="77fac-252">如果发生这种情况，请重试，部署通常会成功。</span><span class="sxs-lookup"><span data-stu-id="77fac-252">If this happens, try again and your deployment will generally succeed.</span></span>

### <span data-ttu-id="77fac-253">API</span><span class="sxs-lookup"><span data-stu-id="77fac-253">API</span></span>

- <span data-ttu-id="77fac-254">如果应用程序 [将焦点设置](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 在用户后面或普通到 camera.forward，全息影像将不会显示在混合现实捕获照片或视频中。</span><span class="sxs-lookup"><span data-stu-id="77fac-254">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="77fac-255">在 Windows 中修复此 bug 之前，如果应用程序[](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity)主动设置对焦点，它们应确保将平面法线设置为与相机前进方向相反 (例如 normal = -camera.forward) 。</span><span class="sxs-lookup"><span data-stu-id="77fac-255">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <span data-ttu-id="77fac-256">Xbox 无线控制器</span><span class="sxs-lookup"><span data-stu-id="77fac-256">Xbox Wireless Controller</span></span>

- <span data-ttu-id="77fac-257">Xbox 无线控制器 S 必须先更新，然后才能与 HoloLens 一起使用。</span><span class="sxs-lookup"><span data-stu-id="77fac-257">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="77fac-258">在尝试 [将控制器](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) 与 HoloLens 配对之前，请确保你为最新版本。</span><span class="sxs-lookup"><span data-stu-id="77fac-258">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="77fac-259">如果在连接 Xbox 无线控制器时重新启动 HoloLens，控制器不会自动重新连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="77fac-259">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="77fac-260">"指南"按钮指示灯将缓慢闪烁，直到控制器在 3 分钟后关闭电源。</span><span class="sxs-lookup"><span data-stu-id="77fac-260">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="77fac-261">若要立即重新连接控制器，请按住"指南"按钮关闭控制器，直到灯关闭。</span><span class="sxs-lookup"><span data-stu-id="77fac-261">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="77fac-262">当你再次打开控制器时，它将重新连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="77fac-262">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="77fac-263">如果你的 HoloLens 在 Xbox 无线控制器连接时进入待机状态，控制器上的任何输入都将唤醒 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="77fac-263">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="77fac-264">使用完控制器后，可以通过关闭控制器来阻止这种情况。</span><span class="sxs-lookup"><span data-stu-id="77fac-264">You can prevent this by powering off your controller when you are done using it.</span></span>

## <span data-ttu-id="77fac-265">HoloLens 仿真器已知问题</span><span class="sxs-lookup"><span data-stu-id="77fac-265">Known issues for HoloLens emulator</span></span>

- <span data-ttu-id="77fac-266">并非所有 Microsoft Store 中的应用都与仿真器兼容。</span><span class="sxs-lookup"><span data-stu-id="77fac-266">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="77fac-267">例如，Young Conker 和 Fragments 在仿真器上不可播放。</span><span class="sxs-lookup"><span data-stu-id="77fac-267">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="77fac-268">无法在仿真器中使用电脑摄像头。</span><span class="sxs-lookup"><span data-stu-id="77fac-268">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="77fac-269">Windows Device Portal 的"实时预览"功能对仿真器不起作用。</span><span class="sxs-lookup"><span data-stu-id="77fac-269">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="77fac-270">你仍然可以捕获混合现实视频和图像。</span><span class="sxs-lookup"><span data-stu-id="77fac-270">You can still capture Mixed Reality videos and images.</span></span>
