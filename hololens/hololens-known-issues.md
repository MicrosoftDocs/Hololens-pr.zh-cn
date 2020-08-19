---
title: HoloLens 已知问题
description: 这是可能会影响 HoloLens 开发人员的已知问题的列表。
keywords: 疑难解答、已知问题、帮助
author: mattzmsft
ms.author: mazeller
ms.date: 4/20/2020
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
ms.openlocfilehash: 6947fe2232701fb9451291bd07e1c896979861d5
ms.sourcegitcommit: 77eb85608066d9a4ed01b3862afe356f7e54d583
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "10940192"
---
# <span data-ttu-id="542b6-104">HoloLens 已知问题</span><span class="sxs-lookup"><span data-stu-id="542b6-104">Known issues for HoloLens</span></span>

<span data-ttu-id="542b6-105">这是用于 HoloLens 设备的已知问题的当前列表。</span><span class="sxs-lookup"><span data-stu-id="542b6-105">This is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="542b6-106">如果看到奇怪的行为，请先查看此处。</span><span class="sxs-lookup"><span data-stu-id="542b6-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="542b6-107">此列表将在发现或报告新问题时保持更新，或者在将来的 HoloLens 软件更新中解决问题。</span><span class="sxs-lookup"><span data-stu-id="542b6-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="542b6-108">如果发现未阻止的问题，请通过 [反馈中心](hololens-feedback.md)将其报告在 HoloLens 设备上。</span><span class="sxs-lookup"><span data-stu-id="542b6-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="542b6-109">如果你所面临的问题正在阻止你，请在 addtion 中归档反馈，请  [提交支持请求](https://aka.ms/hlsupport)。</span><span class="sxs-lookup"><span data-stu-id="542b6-109">If the issue you are facing is blocking you, in addtion to filing feedback, please  [file a support request](https://aka.ms/hlsupport).</span></span>

- [<span data-ttu-id="542b6-110">所有 HoloLens 生成的已知问题</span><span class="sxs-lookup"><span data-stu-id="542b6-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="542b6-111">HoloLens 2 设备的已知问题</span><span class="sxs-lookup"><span data-stu-id="542b6-111">Known issues for HoloLens 2 devices</span></span>](#known-issues-for-hololens-2-devices)
- [<span data-ttu-id="542b6-112">HoloLens 的已知问题 (第一代) </span><span class="sxs-lookup"><span data-stu-id="542b6-112">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)
- [<span data-ttu-id="542b6-113">HoloLens 模拟器的已知问题</span><span class="sxs-lookup"><span data-stu-id="542b6-113">Known issues for HoloLens emulator</span></span>](#known-issues-for-hololens-emulator)

## <span data-ttu-id="542b6-114">所有 HoloLens 生成的已知问题</span><span class="sxs-lookup"><span data-stu-id="542b6-114">Known issues for all HoloLens generations</span></span>

### <span data-ttu-id="542b6-115">Unity</span><span class="sxs-lookup"><span data-stu-id="542b6-115">Unity</span></span>

- <span data-ttu-id="542b6-116">有关为 HoloLens 开发推荐的最新版本的 Unity，请参阅 [安装工具](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) 。</span><span class="sxs-lookup"><span data-stu-id="542b6-116">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="542b6-117">在 [Hololens unity 论坛](https://forum.unity3d.com/threads/known-issues.394627/)中记录了 Unity HoloLens 技术预览版的已知问题。</span><span class="sxs-lookup"><span data-stu-id="542b6-117">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <span data-ttu-id="542b6-118">Windows Device Portal</span><span class="sxs-lookup"><span data-stu-id="542b6-118">Windows Device Portal</span></span>

- <span data-ttu-id="542b6-119">混合现实捕获中的实时预览功能可能会显示几秒钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="542b6-119">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>
- <span data-ttu-id="542b6-120">在 "虚拟输入" 页面上，"虚拟手势" 部分下的 "手势" 和 "滚动" 控件不起作用。</span><span class="sxs-lookup"><span data-stu-id="542b6-120">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="542b6-121">使用它们将不起作用。</span><span class="sxs-lookup"><span data-stu-id="542b6-121">Using them will have no effect.</span></span> <span data-ttu-id="542b6-122">同一页面上的虚拟键盘工作正常。</span><span class="sxs-lookup"><span data-stu-id="542b6-122">The virtual keyboard on the same page works correctly.</span></span>
- <span data-ttu-id="542b6-123">在 "设置" 中启用开发人员模式后，可能需要几秒钟才能启用设备门户。</span><span class="sxs-lookup"><span data-stu-id="542b6-123">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <span data-ttu-id="542b6-124">OneDrive 相机上传</span><span class="sxs-lookup"><span data-stu-id="542b6-124">OneDrive camera upload</span></span>

<span data-ttu-id="542b6-125">适用于 HoloLens 的 OneDrive 应用不支持工作或学校帐户的自动照相机上载。</span><span class="sxs-lookup"><span data-stu-id="542b6-125">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="542b6-126">办法</span><span class="sxs-lookup"><span data-stu-id="542b6-126">Workarounds:</span></span>
- <span data-ttu-id="542b6-127">如果你的企业可行，自动照相机上载在消费者 Microsoft 帐户上受支持。</span><span class="sxs-lookup"><span data-stu-id="542b6-127">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="542b6-128">除了你的工作或学校帐户外，你还可以登录到你的 Microsoft 帐户 (OneDrive 应用支持双重登录) 。</span><span class="sxs-lookup"><span data-stu-id="542b6-128">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="542b6-129">从 OneDrive 中的 Microsoft 帐户配置文件，你可以启用自动的后台相机滚动上载。</span><span class="sxs-lookup"><span data-stu-id="542b6-129">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>
- <span data-ttu-id="542b6-130">如果您无法安全地使用消费者 Microsoft 帐户自动上载您的照片，则可以手动将照片从 OneDrive 应用上载到您的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="542b6-130">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="542b6-131">若要执行此操作，请确保在 OneDrive 应用中登录到你的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="542b6-131">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="542b6-132">选择该 **+** 按钮，然后选择 " **上传**"。</span><span class="sxs-lookup"><span data-stu-id="542b6-132">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="542b6-133">导航到 " **照片" > "照相机卷筒**"，查找要上载的照片或视频。</span><span class="sxs-lookup"><span data-stu-id="542b6-133">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="542b6-134">选择要上传的照片或视频，然后选择 " **打开** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="542b6-134">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <span data-ttu-id="542b6-135">HoloLens 2 设备的已知问题</span><span class="sxs-lookup"><span data-stu-id="542b6-135">Known issues for HoloLens 2 devices</span></span>

### <span data-ttu-id="542b6-136">键盘不切换到特殊字符</span><span class="sxs-lookup"><span data-stu-id="542b6-136">Keyboard does not switch to special characters</span></span>

<span data-ttu-id="542b6-137">在 OOBE 期间存在一个问题，即用户选择了工作或学校帐户并输入其密码后，通过点击 &123 按钮不会更改为特殊字符，尝试切换到键盘上的特殊字符。</span><span class="sxs-lookup"><span data-stu-id="542b6-137">There is an issue during OOBE, where once the user has chosen a work or school account and is entering their password, trying to switch to the special characters on the keyboard by tapping the &123 button does not change to special characters.</span></span> 

<span data-ttu-id="542b6-138">解决方法：</span><span class="sxs-lookup"><span data-stu-id="542b6-138">Work-arounds:</span></span>
-   <span data-ttu-id="542b6-139">关闭键盘，然后点击文本字段将其重新打开。</span><span class="sxs-lookup"><span data-stu-id="542b6-139">Close the keyboard and reopen it by tapping the text field.</span></span>
-   <span data-ttu-id="542b6-140">输入密码不正确。</span><span class="sxs-lookup"><span data-stu-id="542b6-140">Incorrectly enter your password.</span></span> <span data-ttu-id="542b6-141">下一次更高一筹键盘时，它将按预期工作。</span><span class="sxs-lookup"><span data-stu-id="542b6-141">When the keyboard is relaunched next time it will then work as expected.</span></span>
- <span data-ttu-id="542b6-142">Web 身份验证，关闭键盘，然后 **从其他设备中选择 "登录**"。</span><span class="sxs-lookup"><span data-stu-id="542b6-142">Web Authentication, close the keyboard and select **Sign in from another device**.</span></span> 
-   <span data-ttu-id="542b6-143">如果仅输入数字，则用户可以按住某些键以打开展开的菜单。</span><span class="sxs-lookup"><span data-stu-id="542b6-143">If entering only numbers, a user may press and hold certain keys to open an expanded menu.</span></span>
-   <span data-ttu-id="542b6-144">使用 USB 键盘。</span><span class="sxs-lookup"><span data-stu-id="542b6-144">Using a USB keyboard.</span></span>

<span data-ttu-id="542b6-145">这不会影响：</span><span class="sxs-lookup"><span data-stu-id="542b6-145">This does not affect:</span></span>
- <span data-ttu-id="542b6-146">选择使用个人帐户的用户。</span><span class="sxs-lookup"><span data-stu-id="542b6-146">Users who choose to use a personal account.</span></span>

### <span data-ttu-id="542b6-147">通过在具有预览体验计划的设备 reflashed 上的预览体验计划内部版本后显示的蓝色屏幕</span><span class="sxs-lookup"><span data-stu-id="542b6-147">Blue screen is shown after unenrolling from Insider preview builds on a device reflashed with a Insider build</span></span>

<span data-ttu-id="542b6-148">这是影响到预览体验成员预览版中的用户的问题，reflashed 其 HoloLens 2 与新的预览体验计划版本，然后从预览体验计划 unenrolled。</span><span class="sxs-lookup"><span data-stu-id="542b6-148">This is an issue affecting that affects users who are were on an Insider preview build, reflashed their HoloLens 2 with a new insider preview build, and then unenrolled from the Insider program.</span></span> 

<span data-ttu-id="542b6-149">这不会影响：</span><span class="sxs-lookup"><span data-stu-id="542b6-149">This does not affect:</span></span>
- <span data-ttu-id="542b6-150">未在 Windows 预览体验成员中注册的用户</span><span class="sxs-lookup"><span data-stu-id="542b6-150">Users who are not enrolled in Windows Insider</span></span> 
- <span data-ttu-id="542b6-151">预览</span><span class="sxs-lookup"><span data-stu-id="542b6-151">Insiders:</span></span>
    - <span data-ttu-id="542b6-152">由于预览体验成员版本18362的设备已注册</span><span class="sxs-lookup"><span data-stu-id="542b6-152">If a device has been enrolled since Insider builds were version 18362.x</span></span>
    - <span data-ttu-id="542b6-153">如果他们刷新了预览体验成员签名的19041版本，并保持已注册预览体验计划</span><span class="sxs-lookup"><span data-stu-id="542b6-153">If they flashed a Insider signed 19041.x build AND stay enrolled in the Insider program</span></span> 

<span data-ttu-id="542b6-154">解决办法：</span><span class="sxs-lookup"><span data-stu-id="542b6-154">Work-around:</span></span> 
- <span data-ttu-id="542b6-155">避免此问题</span><span class="sxs-lookup"><span data-stu-id="542b6-155">Avoid the issue</span></span> 
    - <span data-ttu-id="542b6-156">快速刷新非预览体验成员内部版本。</span><span class="sxs-lookup"><span data-stu-id="542b6-156">Flash a non-insider build.</span></span> <span data-ttu-id="542b6-157">常规的每月更新之一。</span><span class="sxs-lookup"><span data-stu-id="542b6-157">One of the regular monthly updates.</span></span> 
    - <span data-ttu-id="542b6-158">继续预览预览体验计划</span><span class="sxs-lookup"><span data-stu-id="542b6-158">Stay on Insider Preview</span></span>
- <span data-ttu-id="542b6-159">Reflash 设备</span><span class="sxs-lookup"><span data-stu-id="542b6-159">Reflash the device</span></span>
    1. <span data-ttu-id="542b6-160">通过在不连接时完全关闭，将 [HoloLens 2 手动置于闪烁模式](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) 。</span><span class="sxs-lookup"><span data-stu-id="542b6-160">Put the [HoloLens 2 into flashing mode](https://review.docs.microsoft.com/hololens/hololens-recovery?branch=master#hololens-2) manually by fully powering down while not connect.</span></span> <span data-ttu-id="542b6-161">然后，在按住音量时，点击 "电源" 按钮。</span><span class="sxs-lookup"><span data-stu-id="542b6-161">Then while holding Volume up, tap the Power button.</span></span>
    1. <span data-ttu-id="542b6-162">连接到电脑并打开高级恢复助理。</span><span class="sxs-lookup"><span data-stu-id="542b6-162">Connect to the PC and open Advanced Recovery Companion.</span></span> 
    1. <span data-ttu-id="542b6-163">将 HoloLens 2 闪存到默认内部版本。</span><span class="sxs-lookup"><span data-stu-id="542b6-163">Flash the HoloLens 2 to the default build.</span></span>   

## <span data-ttu-id="542b6-164">HoloLens 的已知问题 (第一代) </span><span class="sxs-lookup"><span data-stu-id="542b6-164">Known issues for HoloLens (1st Gen)</span></span>

### <span data-ttu-id="542b6-165">无法通过 Visual Studio 连接和部署到 HoloLens</span><span class="sxs-lookup"><span data-stu-id="542b6-165">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="542b6-166">上次更新时间： 8/8 @ 5： 11PM-Visual Studio 已发布 VS 2019 版本16.2，其中包括对此问题的修复。</span><span class="sxs-lookup"><span data-stu-id="542b6-166">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="542b6-167">我们建议更新到此最新版本，以避免遇到此错误。</span><span class="sxs-lookup"><span data-stu-id="542b6-167">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="542b6-168">Visual Studio 已发布 VS 2019 版本16.2，其中包括对此问题的修复。</span><span class="sxs-lookup"><span data-stu-id="542b6-168">Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="542b6-169">我们建议更新到此最新版本，以避免遇到此错误。</span><span class="sxs-lookup"><span data-stu-id="542b6-169">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="542b6-170">问题根本原因：使用 Visual studio 2015 或早期版本的 Visual Studio 2017 的用户在其 HoloLens 上部署和调试应用程序，随后使用同一 HoloLens 的最新版本的 Visual Studio 2017 或 Visual Studio 2019 将受到影响。</span><span class="sxs-lookup"><span data-stu-id="542b6-170">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="542b6-171">较新版本的 Visual Studio 部署了组件的新版本，但是较旧版本中的文件会保留在设备上，从而导致更新版本失败。</span><span class="sxs-lookup"><span data-stu-id="542b6-171">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="542b6-172">这将导致以下错误消息： DEP0100：请确保目标设备已启用开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="542b6-172">This causes the following error message: DEP0100: Please ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="542b6-173">由于错误80004005，无法获取开发人员许可证 \<ip\> 。</span><span class="sxs-lookup"><span data-stu-id="542b6-173">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <span data-ttu-id="542b6-174">解决方法</span><span class="sxs-lookup"><span data-stu-id="542b6-174">Workaround</span></span>

<span data-ttu-id="542b6-175">我们的团队目前正在努力解决问题。</span><span class="sxs-lookup"><span data-stu-id="542b6-175">Our team is currently working on a fix.</span></span> <span data-ttu-id="542b6-176">在此期间，你可以使用以下步骤来解决此问题并帮助取消阻止部署和调试：</span><span class="sxs-lookup"><span data-stu-id="542b6-176">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="542b6-177">打开 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="542b6-177">Open Visual Studio</span></span>
1. <span data-ttu-id="542b6-178">选择 "**文件**  >  **新建**  >  **项目**"。</span><span class="sxs-lookup"><span data-stu-id="542b6-178">Select **File** > **New** > **Project**.</span></span>
1. <span data-ttu-id="542b6-179">选择 " **Visual c #**  >  **Windows 桌面版**  >  \*\*控制台应用 ( .net Framework) \*\*。</span><span class="sxs-lookup"><span data-stu-id="542b6-179">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>
1. <span data-ttu-id="542b6-180">为项目提供一个名称 (如 "HoloLensDeploymentFix" ) ，确保框架至少设置为 .NET Framework 4.5，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="542b6-180">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>
1. <span data-ttu-id="542b6-181">在 "解决方案资源管理器" 中右键单击 " **引用** " 节点，然后添加以下引用 (选择到 " **浏览** " 部分，然后选择 " **浏览** ") ：</span><span class="sxs-lookup"><span data-stu-id="542b6-181">Right-click on the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="542b6-182">如果尚未安装10.0.18362.0，请使用您拥有的最新版本。</span><span class="sxs-lookup"><span data-stu-id="542b6-182">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span> 

1. <span data-ttu-id="542b6-183">在 "解决方案资源管理器" 中右键单击该项目，然后选择 "**添加**  >  **现有项**"。</span><span class="sxs-lookup"><span data-stu-id="542b6-183">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>
1. <span data-ttu-id="542b6-184">通过浏览找到 C:\Program 文件 (x86) \Windows Kits\10\bin\10.0.18362.0\x86，并将筛选器更改为 \*\* ( \ \* \ \* \ \* ) 的所有文件 \*\*。</span><span class="sxs-lookup"><span data-stu-id="542b6-184">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>
1. <span data-ttu-id="542b6-185">同时选择 "SirepClient.dll" 和 "SshClient.dll"，然后选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="542b6-185">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>
1. <span data-ttu-id="542b6-186">在 "解决方案资源管理器" 中找到并选择两个文件 (它们应位于文件列表的底部) 并将 "**属性**" 窗口中的 "**复制到输出目录**" 更改为 "**始终复制**"。</span><span class="sxs-lookup"><span data-stu-id="542b6-186">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>
1. <span data-ttu-id="542b6-187">在文件的顶部，将以下内容添加到现有语句列表中 `using` ：</span><span class="sxs-lookup"><span data-stu-id="542b6-187">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="542b6-188">在中 `static void Main(...)` ，添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="542b6-188">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="542b6-189">选择 "**生成**  >  **生成解决方案**"。</span><span class="sxs-lookup"><span data-stu-id="542b6-189">Select **Build** > **Build Solution**.</span></span>
1. <span data-ttu-id="542b6-190">打开命令提示符窗口和 cd 到包含已编译 .exe 文件的文件夹 (例如，C:\MyProjects\HoloLensDeploymentFix\bin\Debug) </span><span class="sxs-lookup"><span data-stu-id="542b6-190">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug)</span></span>
1. <span data-ttu-id="542b6-191">运行可执行文件，并以命令行参数的形式提供设备的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="542b6-191">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="542b6-192"> (如果使用 USB 进行连接，则可以使用127.0.0.1，否则使用设备的 Wi-fi IP 地址。 ) 例如，"HoloLensDeploymentFix 127.0.0.1"</span><span class="sxs-lookup"><span data-stu-id="542b6-192">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1"</span></span>

1. <span data-ttu-id="542b6-193">在该工具退出后没有任何消息 (此操作只需几秒钟) ，您现在就可以从 Visual Studio 2017 或更高版本部署和调试。</span><span class="sxs-lookup"><span data-stu-id="542b6-193">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="542b6-194">无需继续使用该工具。</span><span class="sxs-lookup"><span data-stu-id="542b6-194">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="542b6-195">我们将提供进一步的更新，因为它们变得可用。</span><span class="sxs-lookup"><span data-stu-id="542b6-195">We will provide further updates as they become available.</span></span>

### <span data-ttu-id="542b6-196">在 HoloLens 上启动 Microsoft Store 和应用时出现问题</span><span class="sxs-lookup"><span data-stu-id="542b6-196">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="542b6-197">上次更新时间： 4/2 @ 10 点-问题已解决。</span><span class="sxs-lookup"><span data-stu-id="542b6-197">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span> 

<span data-ttu-id="542b6-198">尝试在 HoloLens 上启动 Microsoft Store 和应用时，可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="542b6-198">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="542b6-199">我们已确定，当后台应用更新在特定序列中部署较新版本的 framework 程序包，而其一个或多个依赖应用仍在运行时，则会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="542b6-199">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="542b6-200">在此情况下，自动应用更新向10.0.27413 提供了一个新版本的 .NET Native Framework (10.0.25531 到) ，从而导致使用以前版本的 Framework 的所有运行应用无法正确更新运行的应用。</span><span class="sxs-lookup"><span data-stu-id="542b6-200">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="542b6-201">框架更新流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="542b6-201">The flow for framework update is as follows:</span></span> 

1. <span data-ttu-id="542b6-202">将从应用商店下载并安装新的框架程序包</span><span class="sxs-lookup"><span data-stu-id="542b6-202">The new framework package is downloaded from the store and installed</span></span>
1. <span data-ttu-id="542b6-203">所有使用较旧框架的应用均 "更新" 为使用较新的版本</span><span class="sxs-lookup"><span data-stu-id="542b6-203">All apps using the older framework are 'updated' to use the newer version</span></span>

<span data-ttu-id="542b6-204">如果步骤2在完成之前中断，则未注册较新框架的任何应用都将无法从 "开始" 菜单启动。</span><span class="sxs-lookup"><span data-stu-id="542b6-204">If step 2 is interrupted before completion then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="542b6-205">我们认为 HoloLens 上的任何应用都可能受此问题的影响。</span><span class="sxs-lookup"><span data-stu-id="542b6-205">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="542b6-206">某些用户已报告关闭挂起的应用并启动其他应用（如反馈中心、3D 查看器或照片）解决了这些应用的问题 &mdash; ，但这不会在100% 的时间起作用。</span><span class="sxs-lookup"><span data-stu-id="542b6-206">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them&mdash;however, this does not work 100% of the time.</span></span>

<span data-ttu-id="542b6-207">我们的根本原因导致此问题不会导致更新，但操作系统中导致 .NET Native framework 更新未正确处理的 bug。</span><span class="sxs-lookup"><span data-stu-id="542b6-207">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="542b6-208">我们很高兴地宣布我们已确定修补程序，并已发布 (OS 版本 17763.380) 包含该修补程序的更新。</span><span class="sxs-lookup"><span data-stu-id="542b6-208">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="542b6-209">若要查看设备是否可以进行更新，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="542b6-209">To see if your device can take the update, please:</span></span>

1. <span data-ttu-id="542b6-210">转到 "设置" 应用，打开 " **更新 & 安全性**"。</span><span class="sxs-lookup"><span data-stu-id="542b6-210">Go to the Settings app and open **Update & Security**.</span></span>
1. <span data-ttu-id="542b6-211">选择 " **检查更新**"。</span><span class="sxs-lookup"><span data-stu-id="542b6-211">Select **Check for Updates**.</span></span>
1. <span data-ttu-id="542b6-212">如果有17763.380 更新可用，请更新到此内部版本以接收应用挂起 bug 的修补程序</span><span class="sxs-lookup"><span data-stu-id="542b6-212">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug</span></span>
1. <span data-ttu-id="542b6-213">更新到此版本的操作系统后，应用应按预期工作。</span><span class="sxs-lookup"><span data-stu-id="542b6-213">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="542b6-214">此外，在每次 HoloLens 操作系统发布时，我们已将 FFU 映像发布到 [Microsoft 下载中心](https://aka.ms/hololensdownload/10.0.17763.380)。</span><span class="sxs-lookup"><span data-stu-id="542b6-214">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="542b6-215">如果您不想进行更新，我们发布了一个新版本的 Microsoft Store UWP 应用，3/29。</span><span class="sxs-lookup"><span data-stu-id="542b6-215">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="542b6-216">在拥有更新版本的应用商店后：</span><span class="sxs-lookup"><span data-stu-id="542b6-216">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="542b6-217">打开应用商店并确认它已加载。</span><span class="sxs-lookup"><span data-stu-id="542b6-217">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="542b6-218">使用绽放手势打开菜单。</span><span class="sxs-lookup"><span data-stu-id="542b6-218">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="542b6-219">尝试打开以前损坏的应用。</span><span class="sxs-lookup"><span data-stu-id="542b6-219">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="542b6-220">如果仍然无法启动，请点击并按住损坏的应用的图标，然后选择 "卸载"。</span><span class="sxs-lookup"><span data-stu-id="542b6-220">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="542b6-221">从应用商店 Resinstall 这些应用。</span><span class="sxs-lookup"><span data-stu-id="542b6-221">Resinstall these apps from the store.</span></span>

<span data-ttu-id="542b6-222">如果你的设备仍无法加载应用，你可以通过以下步骤通过下载中心旁加载 .NET Native Framework 和运行时的版本：</span><span class="sxs-lookup"><span data-stu-id="542b6-222">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="542b6-223">请从 Microsoft 下载中心下载 [此 zip 文件](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 。</span><span class="sxs-lookup"><span data-stu-id="542b6-223">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="542b6-224">解压缩将产生两个文件。</span><span class="sxs-lookup"><span data-stu-id="542b6-224">Unzipping will produce two files.</span></span>  <span data-ttu-id="542b6-225">Microsoft NET.TCP. 1.7. .appx 和 Microsoft .NET。 .appx.-.appx</span><span class="sxs-lookup"><span data-stu-id="542b6-225">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx</span></span>
1. <span data-ttu-id="542b6-226">请验证您的设备是否已进行开发解锁。</span><span class="sxs-lookup"><span data-stu-id="542b6-226">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="542b6-227">如果您尚未执行此操作，请参阅 [此处](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)的说明。</span><span class="sxs-lookup"><span data-stu-id="542b6-227">If you haven't done that before the instructions to do that are [here](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="542b6-228">然后，你需要进入 Windows Device Portal。</span><span class="sxs-lookup"><span data-stu-id="542b6-228">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="542b6-229">我们建议通过 USB 执行此操作，并通过在浏览器中键入来执行此操作 http://127.0.0.1:10080 。</span><span class="sxs-lookup"><span data-stu-id="542b6-229">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>
1. <span data-ttu-id="542b6-230">在安装好 Windows Device Portal 之后，我们需要你已下载的两个文件 "端加载"。</span><span class="sxs-lookup"><span data-stu-id="542b6-230">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="542b6-231">若要执行此操作，您需要沿左侧栏，直到找到 " **应用** " 部分，然后选择 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="542b6-231">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>
1. <span data-ttu-id="542b6-232">然后，你将看到类似于下面的屏幕。</span><span class="sxs-lookup"><span data-stu-id="542b6-232">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="542b6-233">你希望转到表示 " **安装应用** " 的部分，并浏览到解压缩这两个 APPX 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="542b6-233">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="542b6-234">一次只能执行一个操作，因此在选择第一个，然后单击 "部署" 部分下的 "开始"。</span><span class="sxs-lookup"><span data-stu-id="542b6-234">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="542b6-235">然后为第二个 APPX 文件执行此操作。</span><span class="sxs-lookup"><span data-stu-id="542b6-235">Then do this for the second APPX file.</span></span>

   ![用于安装面加载应用的 Windows Device Portal](images/20190322-DevicePortal.png)
1. <span data-ttu-id="542b6-237">此时，我们认为你的应用程序应再次开始工作，并且你也可以访问应用商店。</span><span class="sxs-lookup"><span data-stu-id="542b6-237">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>
1. <span data-ttu-id="542b6-238">在某些情况下，在启动受影响的应用之前，需要运行其他启动3D 查看器应用的步骤。</span><span class="sxs-lookup"><span data-stu-id="542b6-238">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span> 

<span data-ttu-id="542b6-239">我们已完成解决此问题的过程，我们非常感谢你的耐心等待，我们期待继续与社区协作以创建成功的混合现实体验。</span><span class="sxs-lookup"><span data-stu-id="542b6-239">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <span data-ttu-id="542b6-240">设备更新</span><span class="sxs-lookup"><span data-stu-id="542b6-240">Device Update</span></span>

- <span data-ttu-id="542b6-241">新更新后30秒后，shell 可能会消失一次。</span><span class="sxs-lookup"><span data-stu-id="542b6-241">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="542b6-242">请执行 **绽放** 手势以恢复你的会话。</span><span class="sxs-lookup"><span data-stu-id="542b6-242">Please perform the **bloom** gesture to resume your session.</span></span>

### <span data-ttu-id="542b6-243">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="542b6-243">Visual Studio</span></span>

- <span data-ttu-id="542b6-244">请参阅安装适用于 HoloLens 开发的最新版本 Visual Studio 的 [工具](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) 。</span><span class="sxs-lookup"><span data-stu-id="542b6-244">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>
- <span data-ttu-id="542b6-245">从 Visual Studio 向 HoloLens 部署应用时，你可能会看到错误：无法对已 \*\*打开用户映射区域的文件执行所请求的操作。 (异常来自 HRESULT： 0x800704C8) \*\*。</span><span class="sxs-lookup"><span data-stu-id="542b6-245">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="542b6-246">如果发生这种情况，请重试，部署通常会成功。</span><span class="sxs-lookup"><span data-stu-id="542b6-246">If this happens, try again and your deployment will generally succeed.</span></span>

### <span data-ttu-id="542b6-247">API</span><span class="sxs-lookup"><span data-stu-id="542b6-247">API</span></span>

- <span data-ttu-id="542b6-248">如果应用程序设置了用户 [关注的焦点](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 或将其设置为 "垂直于照相机"。转发，则全息图将不会在混合现实中捕获照片或视频。</span><span class="sxs-lookup"><span data-stu-id="542b6-248">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="542b6-249">在 Windows 中修复此 bug 之前，如果应用程序主动设置了 [焦点](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) ，则应确保平面法线的设置不是相对的相机前向 (例如，正常 =-摄像机前) 。</span><span class="sxs-lookup"><span data-stu-id="542b6-249">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <span data-ttu-id="542b6-250">Xbox 无线控制器</span><span class="sxs-lookup"><span data-stu-id="542b6-250">Xbox Wireless Controller</span></span>

- <span data-ttu-id="542b6-251">Xbox 无线控制器必须先更新，然后才能与 HoloLens 配合使用。</span><span class="sxs-lookup"><span data-stu-id="542b6-251">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="542b6-252">在尝试将控制器与 HoloLens 配对之前，请确保你处于 [最](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) 新状态。</span><span class="sxs-lookup"><span data-stu-id="542b6-252">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>
- <span data-ttu-id="542b6-253">如果您在 Xbox 无线控制器连接的情况下重新启动 HoloLens，控制器将不会自动重新连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="542b6-253">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="542b6-254">"辅助线" 按钮指示灯将慢慢地闪烁，直到控制器在3分钟后关机。</span><span class="sxs-lookup"><span data-stu-id="542b6-254">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="542b6-255">要立即重新连接控制器，请通过按住 "指南" 按钮来关闭控制器，直到指示灯熄灭。</span><span class="sxs-lookup"><span data-stu-id="542b6-255">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="542b6-256">再次打开控制器电源时，它将重新连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="542b6-256">When you power your controller on again, it will reconnect to HoloLens.</span></span>
- <span data-ttu-id="542b6-257">如果你的 HoloLens 在 Xbox 无线控制器连接时进入待机状态，则控制器上的任何输入都将唤醒 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="542b6-257">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="542b6-258">您可以通过在使用控制器后关闭控制器来阻止此操作。</span><span class="sxs-lookup"><span data-stu-id="542b6-258">You can prevent this by powering off your controller when you are done using it.</span></span>

## <span data-ttu-id="542b6-259">HoloLens 模拟器的已知问题</span><span class="sxs-lookup"><span data-stu-id="542b6-259">Known issues for HoloLens emulator</span></span>

- <span data-ttu-id="542b6-260">并非 Microsoft Store 中的所有应用都与模拟器兼容。</span><span class="sxs-lookup"><span data-stu-id="542b6-260">Not all apps in the Microsoft Store are compatible with the emulator.</span></span> <span data-ttu-id="542b6-261">例如，不能在仿真器上播放年轻人 Conker 和片段。</span><span class="sxs-lookup"><span data-stu-id="542b6-261">For example, Young Conker and Fragments are not playable on the emulator.</span></span>
- <span data-ttu-id="542b6-262">您不能在仿真器中使用 PC 网络摄像头。</span><span class="sxs-lookup"><span data-stu-id="542b6-262">You cannot use the PC webcam in the Emulator.</span></span>
- <span data-ttu-id="542b6-263">Windows Device Portal 的实时预览功能不能与模拟器配合使用。</span><span class="sxs-lookup"><span data-stu-id="542b6-263">The Live Preview feature of the Windows Device Portal does not work with the emulator.</span></span> <span data-ttu-id="542b6-264">您仍然可以捕获混合现实视频和图像。</span><span class="sxs-lookup"><span data-stu-id="542b6-264">You can still capture Mixed Reality videos and images.</span></span>
