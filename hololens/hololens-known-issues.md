---
title: 'HoloLens 第一代 (的已知) '
description: 使用 Unity 和 Windows 设备门户，了解可能影响 HoloLens 客户和开发人员的已知问题和解决方法Windows 设备门户。
keywords: 疑难解答、已知问题、帮助
author: mattzmsft
ms.author: mazeller
ms.date: 6/15/2021
ms.topic: article
ms.custom:
- CI 111456
- CSSTroubleshooting
HoloLens and holograms: Frequently asked questions
manager: jarrettr
ms.prod: hololens
appliesto:
- HoloLens (1st Gen)
ms.openlocfilehash: 558eba8c2260b24a228e957b27927d508a077ec4
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112923544"
---
# <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="cd495-104">HoloLens 第一代 (的已知) </span><span class="sxs-lookup"><span data-stu-id="cd495-104">Known issues for HoloLens (1st Gen)</span></span>

<span data-ttu-id="cd495-105">下面是 HoloLens 设备的已知问题的当前列表。</span><span class="sxs-lookup"><span data-stu-id="cd495-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="cd495-106">如果看到异常行为，请首先查看此处。</span><span class="sxs-lookup"><span data-stu-id="cd495-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="cd495-107">发现或报告新问题时，或者在将来的 HoloLens 软件更新中解决问题时，此列表将保持更新。</span><span class="sxs-lookup"><span data-stu-id="cd495-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="cd495-108">如果发现未阻止的问题，请在 HoloLens 设备上通过[反馈中心。](hololens-feedback.md)</span><span class="sxs-lookup"><span data-stu-id="cd495-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="cd495-109">如果你所面临的问题阻止你，除了提交反馈外， [请提交支持请求](https://aka.ms/hlsupport)。</span><span class="sxs-lookup"><span data-stu-id="cd495-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>


- [<span data-ttu-id="cd495-110">所有 HoloLens 代的已知问题</span><span class="sxs-lookup"><span data-stu-id="cd495-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="cd495-111">HoloLens 第一代 (的已知) </span><span class="sxs-lookup"><span data-stu-id="cd495-111">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="cd495-112">所有 HoloLens 代的已知问题</span><span class="sxs-lookup"><span data-stu-id="cd495-112">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="cd495-113">Unity</span><span class="sxs-lookup"><span data-stu-id="cd495-113">Unity</span></span>

- <span data-ttu-id="cd495-114">有关 [用于](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) HoloLens 开发的建议最新版本的 Unity，请参阅安装工具。</span><span class="sxs-lookup"><span data-stu-id="cd495-114">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="cd495-115">[HoloLens Unity](https://forum.unity3d.com/threads/known-issues.394627/)论坛中记录了 Unity HoloLens Technical Preview 的已知问题。</span><span class="sxs-lookup"><span data-stu-id="cd495-115">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="cd495-116">Windows 设备门户</span><span class="sxs-lookup"><span data-stu-id="cd495-116">Windows Device Portal</span></span>

- <span data-ttu-id="cd495-117">混合现实捕获中的实时预览功能可能会出现几秒钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="cd495-117">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="cd495-118">在"虚拟输入"页上，"虚拟手势"部分下的"手势"和"滚动"控件不起作用。</span><span class="sxs-lookup"><span data-stu-id="cd495-118">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="cd495-119">使用它们将不起作用。</span><span class="sxs-lookup"><span data-stu-id="cd495-119">Using them will have no effect.</span></span> <span data-ttu-id="cd495-120">虚拟输入页上的虚拟键盘正常工作。</span><span class="sxs-lookup"><span data-stu-id="cd495-120">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="cd495-121">在"设置"中启用"开发人员模式"后，可能需要几秒钟时间，开关才能设备门户打开。</span><span class="sxs-lookup"><span data-stu-id="cd495-121">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="cd495-122">OneDrive 相机上传</span><span class="sxs-lookup"><span data-stu-id="cd495-122">OneDrive camera upload</span></span>

<span data-ttu-id="cd495-123">适用于 HoloLens 的 OneDrive 应用不支持为工作或学校帐户自动上传相机。</span><span class="sxs-lookup"><span data-stu-id="cd495-123">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="cd495-124">解决方法：</span><span class="sxs-lookup"><span data-stu-id="cd495-124">Workarounds:</span></span>

- <span data-ttu-id="cd495-125">如果你的业务可行，则使用者 Microsoft 帐户支持自动上传相机。</span><span class="sxs-lookup"><span data-stu-id="cd495-125">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="cd495-126">除了工作或学校帐户Microsoft 帐户 OneDrive 应用支持双重登录帐户 (还可以登录到) 。</span><span class="sxs-lookup"><span data-stu-id="cd495-126">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="cd495-127">在 OneDrive Microsoft 帐户配置文件中，可以启用自动后台相机滚动上传。</span><span class="sxs-lookup"><span data-stu-id="cd495-127">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="cd495-128">如果无法安全地使用使用者Microsoft 帐户自动上传照片，可以从 OneDrive 应用手动将照片上传到工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="cd495-128">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="cd495-129">为此，请确保已登录到 OneDrive 应用中的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="cd495-129">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="cd495-130">选择按钮 **+** ，然后选择"上传 **"。**</span><span class="sxs-lookup"><span data-stu-id="cd495-130">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="cd495-131">通过导航到"照片"和"相机滚动> **上传的照片或视频**。</span><span class="sxs-lookup"><span data-stu-id="cd495-131">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="cd495-132">选择要上传的一个或多个照片或视频，然后选择"打开 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="cd495-132">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="cd495-133">HoloLens 第一代 (的已知) </span><span class="sxs-lookup"><span data-stu-id="cd495-133">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="cd495-134">无法通过客户端连接到 HoloLens Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cd495-134">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="cd495-135">上次更新：8/8 @ 5：11PM - Visual Studio 已发布 VS 2019 版本 16.2，其中包括此问题的修补程序。</span><span class="sxs-lookup"><span data-stu-id="cd495-135">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="cd495-136">建议更新到此最新版本，以避免遇到此错误。</span><span class="sxs-lookup"><span data-stu-id="cd495-136">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="cd495-137">Visual Studio VS 2019 版本 16.2，其中包括此问题的修复。</span><span class="sxs-lookup"><span data-stu-id="cd495-137">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="cd495-138">建议更新到此最新版本，以避免遇到此错误。</span><span class="sxs-lookup"><span data-stu-id="cd495-138">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="cd495-139">问题根本原因：使用 Visual Studio 2015 或 Visual Studio 2017 早期版本在 HoloLens 上部署和调试应用程序，然后使用最新版本的 Visual Studio 2017 或 Visual Studio 2019 与同一 HoloLens 的用户将受到影响。</span><span class="sxs-lookup"><span data-stu-id="cd495-139">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="cd495-140">较新版本的 Visual Studio部署组件的新版本，但旧版本中的文件会留在设备上，从而导致较新版本失败。</span><span class="sxs-lookup"><span data-stu-id="cd495-140">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="cd495-141">这将导致以下错误消息：DEP0100：确保目标设备已启用开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="cd495-141">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="cd495-142">由于错误 \<ip\> 80004005，无法获取开发人员许可证。</span><span class="sxs-lookup"><span data-stu-id="cd495-142">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="cd495-143">解决方法</span><span class="sxs-lookup"><span data-stu-id="cd495-143">Workaround</span></span>

<span data-ttu-id="cd495-144">我们的团队目前正在致力于修复。</span><span class="sxs-lookup"><span data-stu-id="cd495-144">Our team is currently working on a fix.</span></span> <span data-ttu-id="cd495-145">在此期间，可以使用以下步骤来解决此问题，并帮助取消阻止部署和调试：</span><span class="sxs-lookup"><span data-stu-id="cd495-145">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="cd495-146">打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="cd495-146">Open Visual Studio.</span></span>

1. <span data-ttu-id="cd495-147">选择“文件” > “新建” > “项目”  。</span><span class="sxs-lookup"><span data-stu-id="cd495-147">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="cd495-148">选择 **"Visual C#**  >  **Windows 桌面**  >  **控制台应用 (.NET Framework) "。**</span><span class="sxs-lookup"><span data-stu-id="cd495-148">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="cd495-149">为项目命名 (例如"HoloLensDeploymentFix") 并确保框架至少设置为 .NET Framework 4.5，然后选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="cd495-149">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="cd495-150">右键单击"浏览"解决方案资源管理器，将以下引用 ("浏览"**部分，然后选择\*\*\*\*"浏览**) ：</span><span class="sxs-lookup"><span data-stu-id="cd495-150">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="cd495-151">如果未安装 10.0.18362.0，请使用最新版本。</span><span class="sxs-lookup"><span data-stu-id="cd495-151">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span>

1. <span data-ttu-id="cd495-152">右键单击"项目"中的解决方案资源管理器并选择"**添加**  >  **现有项"。**</span><span class="sxs-lookup"><span data-stu-id="cd495-152">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="cd495-153">浏览到 C：\Program Files (x86) \Windows Kits\10\bin\10.0.18362.0\x86，将筛选器更改为"所有文件 (**\* \* .) "。**</span><span class="sxs-lookup"><span data-stu-id="cd495-153">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="cd495-154">选择"SirepClient.dll和SshClient.dll，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="cd495-154">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="cd495-155">找到并选择这两个文件解决方案资源管理器 (它们应位于文件列表的底部，) "属性"窗口中的"复制到输出目录"更改为"始终 **复制"。** </span><span class="sxs-lookup"><span data-stu-id="cd495-155">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="cd495-156">在文件顶部，将以下内容添加到语句的现有 `using` 列表中：</span><span class="sxs-lookup"><span data-stu-id="cd495-156">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="cd495-157">在 `static void Main(...)` 内，添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="cd495-157">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="cd495-158">选择“生成” > “生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="cd495-158">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="cd495-159">打开命令提示符窗口，将 cd 打开到包含已编译 .exe 文件的文件夹 (例如 C：\MyProjects\HoloLensDeploymentFix\bin\Debug) 。</span><span class="sxs-lookup"><span data-stu-id="cd495-159">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="cd495-160">运行可执行文件，并提供设备的 IP 地址作为命令行参数。</span><span class="sxs-lookup"><span data-stu-id="cd495-160">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="cd495-161"> (如果使用 USB 进行连接，可以使用 127.0.0.1，否则请使用设备的 Wi-Fi IP 地址。) 例如，"HoloLensDeploymentFix 127.0.0.1"。</span><span class="sxs-lookup"><span data-stu-id="cd495-161">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="cd495-162">在该工具退出且没有任何消息 (此操作只需几秒钟) ，现在即可从 Visual Studio 2017 或更高版本进行部署和调试。</span><span class="sxs-lookup"><span data-stu-id="cd495-162">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="cd495-163">不需要继续使用该工具。</span><span class="sxs-lookup"><span data-stu-id="cd495-163">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="cd495-164">当更新可用时，我们将提供进一步更新。</span><span class="sxs-lookup"><span data-stu-id="cd495-164">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="cd495-165">在 HoloLens Microsoft Store应用时的问题</span><span class="sxs-lookup"><span data-stu-id="cd495-165">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="cd495-166">上次更新时间：4/2 @ 上午 10 点 - 问题已解决。</span><span class="sxs-lookup"><span data-stu-id="cd495-166">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="cd495-167">尝试在 HoloLens 上启动 Microsoft Store应用时可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="cd495-167">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="cd495-168">我们已确定，当后台应用更新部署特定序列中较新版本的框架包时，其一个或多个依赖应用仍在运行时，会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="cd495-168">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="cd495-169">在这种情况下，自动应用更新将 .NET Native Framework (版本 10.0.25531 的新版本传递到 10.0.27413) 导致正在运行的应用无法正确更新使用以前版本的框架的所有正在运行的应用。</span><span class="sxs-lookup"><span data-stu-id="cd495-169">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="cd495-170">框架更新流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="cd495-170">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="cd495-171">新框架包从存储区下载并安装。</span><span class="sxs-lookup"><span data-stu-id="cd495-171">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="cd495-172">使用较旧框架的所有应用都"更新"为使用较新版本。</span><span class="sxs-lookup"><span data-stu-id="cd495-172">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="cd495-173">如果步骤 2 在完成之前中断，则任何未注册较新框架的应用将无法从开始菜单启动。</span><span class="sxs-lookup"><span data-stu-id="cd495-173">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="cd495-174">我们认为 HoloLens 上的任何应用都可能会受此问题的影响。</span><span class="sxs-lookup"><span data-stu-id="cd495-174">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="cd495-175">一些用户报告，关闭挂起的应用并启动其他应用（例如 反馈中心、3D 查看器 或照片）可解决他们的问题 ， 但是，这 100% 的时间都不起作用。</span><span class="sxs-lookup"><span data-stu-id="cd495-175">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="cd495-176">我们的根本原因是，此问题不是由更新本身引起的，而是 OS 中的一个 bug，导致错误.NET Native框架更新。</span><span class="sxs-lookup"><span data-stu-id="cd495-176">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="cd495-177">我们很高兴地宣布，我们已确定一个修补程序，并发布了包含 (OS 版本 17763.380) 更新。</span><span class="sxs-lookup"><span data-stu-id="cd495-177">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="cd495-178">查看设备能否进行更新：</span><span class="sxs-lookup"><span data-stu-id="cd495-178">To see if your device can take the update:</span></span>

1. <span data-ttu-id="cd495-179">转到"设置"应用并打开"**更新&安全性"。**</span><span class="sxs-lookup"><span data-stu-id="cd495-179">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="cd495-180">选择 **"检查更新"。**</span><span class="sxs-lookup"><span data-stu-id="cd495-180">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="cd495-181">如果更新到 17763.380 可用，请更新到此内部版本，以接收应用挂起 bug 的修复。</span><span class="sxs-lookup"><span data-stu-id="cd495-181">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="cd495-182">更新到此版本的 OS 后，应用应可正常工作。</span><span class="sxs-lookup"><span data-stu-id="cd495-182">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="cd495-183">此外，与每次 HoloLens OS 版本一样，我们已将 FFU 映像发布给 [Microsoft 下载中心](https://aka.ms/hololensdownload/10.0.17763.380)。</span><span class="sxs-lookup"><span data-stu-id="cd495-183">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="cd495-184">如果想进行更新，我们自 3 月 29 日Microsoft Store UWP 应用的新版本。</span><span class="sxs-lookup"><span data-stu-id="cd495-184">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="cd495-185">拥有 Store 的更新版本后：</span><span class="sxs-lookup"><span data-stu-id="cd495-185">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="cd495-186">打开 Store 并确认它已加载。</span><span class="sxs-lookup"><span data-stu-id="cd495-186">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="cd495-187">使用布满手势打开菜单。</span><span class="sxs-lookup"><span data-stu-id="cd495-187">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="cd495-188">尝试打开以前损坏的应用。</span><span class="sxs-lookup"><span data-stu-id="cd495-188">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="cd495-189">如果仍然无法启动，请点击并按住损坏应用的图标，然后选择"卸载"。</span><span class="sxs-lookup"><span data-stu-id="cd495-189">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="cd495-190">从应用商店重新安装这些应用。</span><span class="sxs-lookup"><span data-stu-id="cd495-190">Reinstall these apps from the store.</span></span>

<span data-ttu-id="cd495-191">如果设备仍无法加载应用，可以按照以下步骤.NET Native下载中心旁加载 .NET Native Framework 和运行时的版本：</span><span class="sxs-lookup"><span data-stu-id="cd495-191">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="cd495-192">请从 Microsoft [下载中心](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 下载此 zip 文件。</span><span class="sxs-lookup"><span data-stu-id="cd495-192">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="cd495-193">解压缩将生成两个文件。</span><span class="sxs-lookup"><span data-stu-id="cd495-193">Unzipping will produce two files.</span></span>  <span data-ttu-id="cd495-194">Microsoft .NET.Native.Runtime.1.7.appx 和 Microsoft .NET.Native.Framework.1.7.appx。</span><span class="sxs-lookup"><span data-stu-id="cd495-194">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="cd495-195">请验证设备是否解锁了开发。</span><span class="sxs-lookup"><span data-stu-id="cd495-195">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="cd495-196">如果之前尚未这样做，请参阅 [使用](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) Windows 设备门户了解说明。</span><span class="sxs-lookup"><span data-stu-id="cd495-196">If you haven't done that before, see [Using the Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="cd495-197">然后，你需要进入Windows 设备门户。</span><span class="sxs-lookup"><span data-stu-id="cd495-197">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="cd495-198">我们的建议是使用 USB 实现此目标，为此，请键入 http://127.0.0.1:10080 浏览器。</span><span class="sxs-lookup"><span data-stu-id="cd495-198">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="cd495-199">安装好Windows 设备门户，我们需要你"旁加载"下载的两个文件。</span><span class="sxs-lookup"><span data-stu-id="cd495-199">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="cd495-200">为此，需要向下转到左侧栏，直到转到"应用 **"部分并选择**"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="cd495-200">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="cd495-201">随后会看到类似于下面的屏幕。</span><span class="sxs-lookup"><span data-stu-id="cd495-201">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="cd495-202">要转到 " **安装应用程序** " 部分，并浏览到解压这两个 APPX 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="cd495-202">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="cd495-203">你一次只能执行一个操作，因此在选择第一个项后，在 "部署" 部分下单击 "开始"。</span><span class="sxs-lookup"><span data-stu-id="cd495-203">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="cd495-204">然后对第二个 APPX 文件执行此操作。</span><span class="sxs-lookup"><span data-stu-id="cd495-204">Then do this for the second APPX file.</span></span>

   ![用于安装 Side-Loaded 应用的 Windows 设备门户](images/20190322-DevicePortal.png)

1. <span data-ttu-id="cd495-206">此时，我们相信您的应用程序应再次开始工作，您也可以访问应用商店。</span><span class="sxs-lookup"><span data-stu-id="cd495-206">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="cd495-207">在某些情况下，在启动受影响的应用程序之前，需要运行额外的步骤来启动3D 查看器应用程序。</span><span class="sxs-lookup"><span data-stu-id="cd495-207">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span>

<span data-ttu-id="cd495-208">我们非常感谢你的耐心，因为我们已经完成了解决此问题的过程，我们期待继续与我们的社区合作，以创建成功的混合现实体验。</span><span class="sxs-lookup"><span data-stu-id="cd495-208">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="cd495-209">设备更新</span><span class="sxs-lookup"><span data-stu-id="cd495-209">Device Update</span></span>

- <span data-ttu-id="cd495-210">30秒后，shell 可能会消失一次。</span><span class="sxs-lookup"><span data-stu-id="cd495-210">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="cd495-211">请执行 **布隆** 手势以恢复会话。</span><span class="sxs-lookup"><span data-stu-id="cd495-211">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="cd495-212">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cd495-212">Visual Studio</span></span>

- <span data-ttu-id="cd495-213">请参阅安装适用于 HoloLens 开发的 Visual Studio 的最新版本的 [工具](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) 。</span><span class="sxs-lookup"><span data-stu-id="cd495-213">See [Install the tools](https://docs.microsoft.com/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="cd495-214">在将应用程序从 Visual Studio 部署到 HoloLens 时，可能会看到以下错误： **无法对具有用户映射区域打开的文件执行所请求的操作。 HRESULT 中的 (异常： 0x800704C8)**。</span><span class="sxs-lookup"><span data-stu-id="cd495-214">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="cd495-215">如果发生这种情况，请重试，部署通常会成功。</span><span class="sxs-lookup"><span data-stu-id="cd495-215">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="cd495-216">API</span><span class="sxs-lookup"><span data-stu-id="cd495-216">API</span></span>

- <span data-ttu-id="cd495-217">如果应用程序将 [焦点](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 置于用户后面或 "正常" 设置为 "摄像"，则全息体将不会在混合现实捕获照片或视频中出现。</span><span class="sxs-lookup"><span data-stu-id="cd495-217">If the application sets the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="cd495-218">在 Windows 中修复此 bug 之前，如果应用程序主动设置了焦点，则应确保将平面法线设置为相对 [于](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) 照相机前进 (例如，normal =-摄像) 。</span><span class="sxs-lookup"><span data-stu-id="cd495-218">Until this bug is fixed in Windows, if applications actively set the [focus point](https://docs.microsoft.com/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="cd495-219">Xbox 无线控制器</span><span class="sxs-lookup"><span data-stu-id="cd495-219">Xbox Wireless Controller</span></span>

- <span data-ttu-id="cd495-220">必须先更新 Xbox 无线控制器，然后才能将其与 HoloLens 配合使用。</span><span class="sxs-lookup"><span data-stu-id="cd495-220">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="cd495-221">请确保在尝试将控制器与 HoloLens 配对之前处于 [最新状态](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) 。</span><span class="sxs-lookup"><span data-stu-id="cd495-221">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="cd495-222">如果在连接 Xbox 无线控制器时重新启动 HoloLens，控制器将不会自动重新连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="cd495-222">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="cd495-223">在3分钟后控制器关闭之前，"指南" 按钮指示灯会慢慢闪烁。</span><span class="sxs-lookup"><span data-stu-id="cd495-223">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="cd495-224">若要立即重新连接控制器，请关闭控制器电源，方法是按住 "指南" 按钮，直到指示灯亮起。</span><span class="sxs-lookup"><span data-stu-id="cd495-224">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="cd495-225">再次打开控制器时，它将重新连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="cd495-225">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="cd495-226">如果在连接 Xbox 无线控制器时，HoloLens 进入待机状态，则控制器上的任何输入都将唤醒 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="cd495-226">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="cd495-227">使用完控制器后，可以通过关闭控制器来阻止此操作。</span><span class="sxs-lookup"><span data-stu-id="cd495-227">You can prevent this by powering off your controller when you are done using it.</span></span>

