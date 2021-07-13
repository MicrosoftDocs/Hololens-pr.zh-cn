---
title: " (第一代 HoloLens 的已知问题) "
description: 了解已知问题和解决方法的列表，该列表可能会影响使用 Unity 的客户和开发人员和 Windows 设备门户 HoloLens。
keywords: 故障排除、已知问题、帮助
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
ms.openlocfilehash: 36991d62da91011b807dfb9ff52ab16eadac8bc7
ms.sourcegitcommit: 4c15afc772fba26683d9b75e38c44a018b4889f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113640298"
---
# <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="a3ec7-104"> (第一代 HoloLens 的已知问题) </span><span class="sxs-lookup"><span data-stu-id="a3ec7-104">Known issues for HoloLens (1st Gen)</span></span>

<span data-ttu-id="a3ec7-105">下面是 HoloLens 设备的已知问题的最新列表。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-105">Here is the current list of known issues for HoloLens devices.</span></span> <span data-ttu-id="a3ec7-106">如果看到的是奇怪的行为，请先查看此处。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-106">Check here first if you are seeing an odd behavior.</span></span> <span data-ttu-id="a3ec7-107">此列表将在发现或报告新问题时保持更新，或者在将来的 HoloLens 软件更新中解决了问题。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-107">This list will be kept updated as new issues are discovered or reported, or as issues are addressed in future HoloLens software updates.</span></span>

>[!NOTE]
> - <span data-ttu-id="a3ec7-108">如果发现未阻止的问题，请通过[反馈中心](hololens-feedback.md)将其报告在 HoloLens 设备上。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-108">If you discover an issue that is not blocking you please report it on your HoloLens device via [Feedback Hub](hololens-feedback.md).</span></span>
> - <span data-ttu-id="a3ec7-109">如果你面临的问题正在阻止你，则除了提供反馈外，请 [提交支持请求](https://aka.ms/hlsupport)。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-109">If the issue you are facing is blocking you, in addition to filing feedback, please [file a support request](https://aka.ms/hlsupport).</span></span>


- [<span data-ttu-id="a3ec7-110">所有 HoloLens 代的已知问题</span><span class="sxs-lookup"><span data-stu-id="a3ec7-110">Known issues for all HoloLens generations</span></span>](#known-issues-for-all-hololens-generations)
- [<span data-ttu-id="a3ec7-111"> (第一代 HoloLens 的已知问题) </span><span class="sxs-lookup"><span data-stu-id="a3ec7-111">Known issues for HoloLens (1st Gen)</span></span>](#known-issues-for-hololens-1st-gen)

## <a name="known-issues-for-all-hololens-generations"></a><span data-ttu-id="a3ec7-112">所有 HoloLens 代的已知问题</span><span class="sxs-lookup"><span data-stu-id="a3ec7-112">Known issues for all HoloLens generations</span></span>

### <a name="unity"></a><span data-ttu-id="a3ec7-113">Unity</span><span class="sxs-lookup"><span data-stu-id="a3ec7-113">Unity</span></span>

- <span data-ttu-id="a3ec7-114">请参阅安装适用于 HoloLens 开发的最新 Unity 版本[工具](/windows/mixed-reality/install-the-tools)。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-114">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Unity recommended for HoloLens development.</span></span>
- <span data-ttu-id="a3ec7-115">[HoloLens unity 论坛](https://forum.unity3d.com/threads/known-issues.394627/)中介绍了 unity HoloLens Technical Preview 的已知问题。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-115">Known issues with the Unity HoloLens Technical Preview are documented in the [HoloLens Unity forums](https://forum.unity3d.com/threads/known-issues.394627/).</span></span>

### <a name="windows-device-portal"></a><span data-ttu-id="a3ec7-116">Windows 设备门户</span><span class="sxs-lookup"><span data-stu-id="a3ec7-116">Windows Device Portal</span></span>

- <span data-ttu-id="a3ec7-117">混合现实捕获中的实时预览功能可能会出现几秒钟的延迟。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-117">The Live Preview feature in Mixed Reality capture may exhibit several seconds of latency.</span></span>

- <span data-ttu-id="a3ec7-118">在 "虚拟输入" 页上，"虚拟手势" 部分下的手势和滚动控件不起作用。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-118">On the Virtual Input page, the Gesture and Scroll controls under the Virtual Gestures section are not functional.</span></span> <span data-ttu-id="a3ec7-119">使用它们将不起作用。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-119">Using them will have no effect.</span></span> <span data-ttu-id="a3ec7-120">虚拟输入页上的虚拟键盘工作正常。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-120">The virtual keyboard on the virtual input page works correctly.</span></span>

- <span data-ttu-id="a3ec7-121">在设置中启用 "开发人员模式" 后，可能需要几秒钟才能打开设备门户。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-121">After enabling Developer Mode in Settings, it may take a few seconds before the switch to turn on the Device Portal is enabled.</span></span>

### <a name="onedrive-camera-upload"></a><span data-ttu-id="a3ec7-122">OneDrive 照相机上传</span><span class="sxs-lookup"><span data-stu-id="a3ec7-122">OneDrive camera upload</span></span>

<span data-ttu-id="a3ec7-123">HoloLens 的 OneDrive 应用不支持工作或学校帐户的自动照相机上传。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-123">The OneDrive app for HoloLens does not support automatic camera upload for work or school accounts.</span></span>

<span data-ttu-id="a3ec7-124">解决方法：</span><span class="sxs-lookup"><span data-stu-id="a3ec7-124">Workarounds:</span></span>

- <span data-ttu-id="a3ec7-125">对于你的业务，在使用者 Microsoft 帐户上支持自动照相机上传。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-125">If viable for your business, automatic camera upload is supported on consumer Microsoft accounts.</span></span> <span data-ttu-id="a3ec7-126">除了使用工作或学校帐户外，还可以登录到 Microsoft 帐户 (OneDrive 应用支持双重登录) 。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-126">You can sign in to your Microsoft account in addition to your work or school account (the OneDrive app supports dual sign-in).</span></span> <span data-ttu-id="a3ec7-127">在 OneDrive 内的 Microsoft 帐户配置文件中，你可以启用自动播放背景照相机滚动。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-127">From your Microsoft account profile within OneDrive you can enable automatic, background camera roll upload.</span></span>

- <span data-ttu-id="a3ec7-128">如果你不能安全地使用使用者 Microsoft 帐户来自动上载照片，你可以从 OneDrive 应用手动将照片上传到你的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-128">If you cannot safely use a consumer Microsoft account for uploading your photos automatically, you can manually upload photos to your work or school account from the OneDrive app.</span></span> <span data-ttu-id="a3ec7-129">为此，请确保已登录到 OneDrive 应用中的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-129">To do that, make sure you're signed into your work or school account in the OneDrive app.</span></span> <span data-ttu-id="a3ec7-130">选择 "" **+** 按钮，然后选择 " **Upload**"。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-130">Select the **+** button and choose **Upload**.</span></span> <span data-ttu-id="a3ec7-131">通过导航到 " **照片" > 照相机滚动**"查找要上传的照片或视频。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-131">Find the photos or videos you want to upload by navigating to **Pictures > Camera Roll**.</span></span> <span data-ttu-id="a3ec7-132">选择要上传的照片或视频，然后选择 " **打开** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-132">Select the photos or videos you want to upload, and then select the **Open** button.</span></span>

## <a name="known-issues-for-hololens-1st-gen"></a><span data-ttu-id="a3ec7-133"> (第一代 HoloLens 的已知问题) </span><span class="sxs-lookup"><span data-stu-id="a3ec7-133">Known issues for HoloLens (1st Gen)</span></span>

### <a name="unable-to-connect-and-deploy-to-hololens-through-visual-studio"></a><span data-ttu-id="a3ec7-134">无法通过 Visual Studio 连接和部署到 HoloLens</span><span class="sxs-lookup"><span data-stu-id="a3ec7-134">Unable to connect and deploy to HoloLens through Visual Studio</span></span>

> [!NOTE]
> <span data-ttu-id="a3ec7-135">上次更新时间： 8/8 @ 5： Visual Studio 晚上11点已发布 VS 2019 版本16.2，其中包括对此问题的修复。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-135">Last Update: 8/8 @ 5:11PM - Visual Studio has released VS 2019 Version 16.2 which includes a fix to this issue.</span></span> <span data-ttu-id="a3ec7-136">建议更新到此最新版本，以避免出现此错误。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-136">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="a3ec7-137">Visual Studio 发布了 VS 2019 版本16.2，其中包括对此问题的修复。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-137">Visual Studio has released VS 2019 Version 16.2, which includes a fix to this issue.</span></span> <span data-ttu-id="a3ec7-138">建议更新到此最新版本，以避免出现此错误。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-138">We recommend updating to this newest version to avoid experiencing this error.</span></span>

<span data-ttu-id="a3ec7-139">问题根本原因：使用 Visual Studio 2015 或早期版本的 Visual Studio 2017 的用户在其 HoloLens 上部署和调试应用程序，然后使用相同 Visual Studio 的最新版本 Visual Studio 2017 或 HoloLens 2019 将受到影响。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-139">Issue root-cause: Users who used Visual Studio 2015 or early releases of Visual Studio 2017 to deploy and debug applications on their HoloLens and then subsequently used the latest versions of Visual Studio 2017 or Visual Studio 2019 with the same HoloLens will be affected.</span></span> <span data-ttu-id="a3ec7-140">较新版本的 Visual Studio 会部署新版本的组件，但较旧版本中的文件将保留在设备上，导致较新版本失败。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-140">The newer releases of Visual Studio deploy a new version of a component, but files from the older version are left over on the device, causing the newer version to fail.</span></span>  <span data-ttu-id="a3ec7-141">这会导致出现以下错误消息： DEP0100：确保目标设备已启用开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-141">This causes the following error message: DEP0100: Ensure that target device has developer mode enabled.</span></span> <span data-ttu-id="a3ec7-142">由于错误80004005，无法获取开发人员许可证 \<ip\> 。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-142">Could not obtain a developer license on \<ip\> due to error 80004005.</span></span>

#### <a name="workaround"></a><span data-ttu-id="a3ec7-143">解决方法</span><span class="sxs-lookup"><span data-stu-id="a3ec7-143">Workaround</span></span>

<span data-ttu-id="a3ec7-144">我们的团队当前正在努力解决问题。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-144">Our team is currently working on a fix.</span></span> <span data-ttu-id="a3ec7-145">同时，你可以使用以下步骤来解决此问题，并帮助取消阻止部署和调试：</span><span class="sxs-lookup"><span data-stu-id="a3ec7-145">In the meantime, you can use the following steps to work around the issue and help unblock deployment and debugging:</span></span>  

1. <span data-ttu-id="a3ec7-146">打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-146">Open Visual Studio.</span></span>

1. <span data-ttu-id="a3ec7-147">选择“文件” > “新建” > “项目”  。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-147">Select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="a3ec7-148">选择 " **Visual c #**"  >  **Windows 桌面**  >  **控制台应用 (.NET Framework ")**"。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-148">Select **Visual C#** > **Windows Desktop** > **Console App (.NET Framework)**.</span></span>

1. <span data-ttu-id="a3ec7-149">为项目指定名称 (如 "HoloLensDeploymentFix" ) ，并确保框架至少设置为 4.5 .NET Framework，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-149">Give the project a name (such as "HoloLensDeploymentFix") and make sure the Framework is set to at least .NET Framework 4.5, then Select **OK**.</span></span>

1. <span data-ttu-id="a3ec7-150">右键单击解决方案资源管理器中的 " **引用** " 节点，然后添加以下引用 (选择 " **浏览** " 部分并选择 " **浏览**) "：</span><span class="sxs-lookup"><span data-stu-id="a3ec7-150">Right-click the **References** node in Solution Explorer and add the following references (select to the **Browse** section and select **Browse**):</span></span>

    ```console
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Deploy.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\Microsoft.Tools.Connectivity.dll
    C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86\SirepInterop.dll
    ```

    > [!NOTE]
    > <span data-ttu-id="a3ec7-151">如果尚未安装10.0.18362.0，请使用最新版本。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-151">If you don't have 10.0.18362.0 installed, use the most recent version that you have.</span></span>

1. <span data-ttu-id="a3ec7-152">在解决方案资源管理器中右键单击该项目，然后选择 "**添加**  >  **现有项**"。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-152">Right-click on the project in Solution Explorer and select **Add** > **Existing Item**.</span></span>

1. <span data-ttu-id="a3ec7-153">浏览到 C:\Program 文件 (x86) \ Windows Kits\10\bin\10.0.18362.0\x86，并将筛选器更改为 "**所有文件 (\* 。 \*)**"。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-153">Browse to C:\Program Files (x86)\Windows Kits\10\bin\10.0.18362.0\x86 and change the filter to **All Files (\*.\*)**.</span></span>

1. <span data-ttu-id="a3ec7-154">选择 "SirepClient.dll" 和 "SshClient.dll"，然后选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-154">Select both SirepClient.dll and SshClient.dll, and Select **Add**.</span></span>

1. <span data-ttu-id="a3ec7-155">找到并选择解决方案资源管理器中的两个文件 (它们应位于文件列表的底部) 并将 "**属性**" 窗口中的 "**复制到输出目录**" 改为 "**始终复制**"。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-155">Locate and select both files in Solution Explorer (they should be at the bottom of the list of files) and change **Copy to Output Directory** in the **Properties** window to **Copy always**.</span></span>

1. <span data-ttu-id="a3ec7-156">在该文件的顶部，将以下内容添加到现有的语句列表中 `using` ：</span><span class="sxs-lookup"><span data-stu-id="a3ec7-156">At the top of the file, add the following to the existing list of `using` statements:</span></span>

    ```console
    using Microsoft.Tools.Deploy;
    using System.Net;
    ```

1. <span data-ttu-id="a3ec7-157">在中 `static void Main(...)` ，添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="a3ec7-157">Inside of `static void Main(...)`, add the following code:</span></span>

    ```PowerShell
    RemoteDeployClient client = RemoteDeployClient.CreateRemoteDeployClient();
    client.Connect(new ConnectionOptions()
    {
        Credentials = new NetworkCredential("DevToolsUser", string.Empty),
        IPAddress = IPAddress.Parse(args[0])
    });
    client.RemoteDevice.DeleteFile(@"C:\Data\Users\DefaultAccount\AppData\Local\DevelopmentFiles\VSRemoteTools\x86\CoreCLR\mscorlib.ni.dll");
    ```

1. <span data-ttu-id="a3ec7-158">选择“生成” > “生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-158">Select **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="a3ec7-159">打开一个命令提示符窗口，然后将 cd 放到包含已编译 .exe 文件的文件夹中 (例如，C:\MyProjects\HoloLensDeploymentFix\bin\Debug) 。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-159">Open a Command Prompt Window and cd to the folder that contains the compiled .exe file (for example, C:\MyProjects\HoloLensDeploymentFix\bin\Debug).</span></span>

1. <span data-ttu-id="a3ec7-160">运行可执行文件，并提供设备的 IP 地址作为命令行参数。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-160">Run the executable and provide the device's IP address as a command-line argument.</span></span> <span data-ttu-id="a3ec7-161"> (如果使用 USB 进行连接，则可以使用127.0.0.1，否则请使用设备的 Wi-Fi IP 地址。 ) 例如，"HoloLensDeploymentFix 127.0.0.1"。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-161">(If connected using USB, you can use 127.0.0.1, otherwise use the device's Wi-Fi IP address.)  For example, "HoloLensDeploymentFix 127.0.0.1".</span></span>

1. <span data-ttu-id="a3ec7-162">退出该工具而不使用任何消息 (仅需几秒钟时间) ，你现在便可以从 Visual Studio 2017 或更高版本进行部署和调试。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-162">After the tool has exited without any messages (this should only take a few seconds), you will now be able to deploy and debug from Visual Studio 2017 or newer.</span></span>  <span data-ttu-id="a3ec7-163">不需要继续使用该工具。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-163">Continued use of the tool is not necessary.</span></span>

<span data-ttu-id="a3ec7-164">我们将在可用时提供更多更新。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-164">We will provide further updates as they become available.</span></span>

### <a name="issues-launching-the-microsoft-store-and-apps-on-hololens"></a><span data-ttu-id="a3ec7-165">在 HoloLens 上启动 Microsoft Store 和应用程序时出现问题</span><span class="sxs-lookup"><span data-stu-id="a3ec7-165">Issues launching the Microsoft Store and apps on HoloLens</span></span>

> [!NOTE]
> <span data-ttu-id="a3ec7-166">上次更新时间： 4/2 @ 10 点-已解决问题。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-166">Last Update: 4/2 @ 10 AM - Issue resolved.</span></span>

<span data-ttu-id="a3ec7-167">尝试在 HoloLens 上启动 Microsoft Store 和应用时可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-167">You may experience issues when trying to launch the Microsoft Store and apps on HoloLens.</span></span> <span data-ttu-id="a3ec7-168">我们确定，当后台应用程序更新在特定序列中部署较新版本的框架包，而其一个或多个从属应用仍在运行时，会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-168">We've determined that the issue occurs when background app updates deploy a newer version of framework packages in specific sequences while one or more of their dependent apps are still running.</span></span> <span data-ttu-id="a3ec7-169">在这种情况下，自动应用更新将 .NET Native Framework (版本10.0.25531 的新版本传递到 10.0.27413) 导致正在运行的应用无法针对使用以前版本 Framework 的所有正在运行的应用进行正确更新。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-169">In this case,  an automatic app update delivered a new version of the .NET Native Framework (version 10.0.25531 to 10.0.27413) caused the apps that are running to not correctly update for all running apps consuming the prior version of the framework.</span></span>  <span data-ttu-id="a3ec7-170">用于框架更新的流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="a3ec7-170">The flow for framework update is as follows:</span></span>

1. <span data-ttu-id="a3ec7-171">新框架包将从应用商店下载并安装。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-171">The new framework package is downloaded from the store and installed.</span></span>

1. <span data-ttu-id="a3ec7-172">使用较旧框架的所有应用程序都是 "更新"，以使用较新的版本。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-172">All apps using the older framework are 'updated' to use the newer version.</span></span>

<span data-ttu-id="a3ec7-173">如果步骤2在完成之前中断，则未注册新框架的任何应用都将无法从 "开始" 菜单启动。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-173">If step 2 is interrupted before completion, then any apps for which the newer framework wasn't registered will fail to launch from the start menu.</span></span>  <span data-ttu-id="a3ec7-174">我们相信 HoloLens 上的任何应用程序都可能受此问题影响。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-174">We believe any app on HoloLens could be affected by this issue.</span></span>

<span data-ttu-id="a3ec7-175">某些用户已报告关闭挂起的应用程序并启动其他应用程序（如反馈中心、三维查看器或照片）解决了这些问题-但是，这不能在100% 的时间运行。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-175">Some users have reported that closing hung apps and launching other apps such as Feedback Hub, 3D Viewer or Photos resolves the issue for them - however, this does not work 100% of the time.</span></span>

<span data-ttu-id="a3ec7-176">我们有根本原因导致此问题不是由更新本身引起的，而是操作系统中导致 .NET Native framework 更新处理不正确的 bug。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-176">We have root caused that this issue was not caused the update itself, but a bug in the OS that resulted in the .NET Native framework update being handled incorrectly.</span></span> <span data-ttu-id="a3ec7-177">我们很高兴地宣布，我们已确定了一个修补程序，并且发布了一个更新 (操作系统版本 17763.380) 包含该修补程序。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-177">We are pleased to announce that we have identified a fix and have released an update (OS version 17763.380) containing the fix.</span></span>  

<span data-ttu-id="a3ec7-178">若要查看设备是否可以进行更新，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a3ec7-178">To see if your device can take the update:</span></span>

1. <span data-ttu-id="a3ec7-179">请参阅设置应用并打开 **更新 & 安全**"。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-179">Go to the Settings app and open **Update & Security**.</span></span>

1. <span data-ttu-id="a3ec7-180">选择 " **检查更新**"。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-180">Select **Check for Updates**.</span></span>

1. <span data-ttu-id="a3ec7-181">如果更新到17763.380，请更新到此版本以接收应用挂起 bug 的修补程序。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-181">If update to 17763.380 is available, please update to this build to receive the fix for the App Hang bug.</span></span>

1. <span data-ttu-id="a3ec7-182">更新到此版本的操作系统时，应用程序应按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-182">Upon updating to this version of the OS, the Apps should work as expected.</span></span>

<span data-ttu-id="a3ec7-183">此外，与每个 HoloLens 操作系统版本一样，我们已将 FFU 图像发布到[Microsoft 下载中心](https://aka.ms/hololensdownload/10.0.17763.380)。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-183">Additionally, as we do with every HoloLens OS release, we have posted the FFU image to the [Microsoft Download Center](https://aka.ms/hololensdownload/10.0.17763.380).</span></span>

<span data-ttu-id="a3ec7-184">如果你不想进行更新，我们发布了 3/29 Microsoft Store UWP 应用的新版本。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-184">If you would not like to take the update, we have released a new version of the Microsoft Store UWP app as of 3/29.</span></span> <span data-ttu-id="a3ec7-185">更新版本的应用商店后：</span><span class="sxs-lookup"><span data-stu-id="a3ec7-185">After you have the updated version of the Store:</span></span>

1. <span data-ttu-id="a3ec7-186">打开应用商店并确认它已加载。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-186">Open the Store and confirm that it loads.</span></span>
1. <span data-ttu-id="a3ec7-187">使用布隆笔势打开菜单。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-187">Use the bloom gesture to open the menu.</span></span>
1. <span data-ttu-id="a3ec7-188">尝试打开以前中断的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-188">Attempt to open previously broken apps.</span></span>
1. <span data-ttu-id="a3ec7-189">如果仍无法启动，请点击并按住损坏的应用程序的图标，然后选择 "卸载"。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-189">If it still cannot be launched, tap and hold the icon of the broken app and select uninstall.</span></span>
1. <span data-ttu-id="a3ec7-190">从应用商店重新安装这些应用。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-190">Reinstall these apps from the store.</span></span>

<span data-ttu-id="a3ec7-191">如果设备仍无法加载应用，则可以通过以下步骤，通过下载中心旁加载 .NET Native Framework 和运行时的版本：</span><span class="sxs-lookup"><span data-stu-id="a3ec7-191">If your device is still unable to load apps, you can sideload a version of the .NET Native Framework and Runtime through the download center by following these steps:</span></span>

1. <span data-ttu-id="a3ec7-192">请从 Microsoft 下载中心下载 [此 zip 文件](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) 。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-192">Please download [this zip file](https://download.microsoft.com/download/8/5/C/85C23745-794C-419D-B8D7-115FBCCD6DA7/netfx_1.7.zip) from the Microsoft Download Center.</span></span> <span data-ttu-id="a3ec7-193">解压缩会生成两个文件。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-193">Unzipping will produce two files.</span></span>  <span data-ttu-id="a3ec7-194">。 .Appx. .appx. .appx. .appx. .appx. .appx. .appx。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-194">Microsoft.NET.Native.Runtime.1.7.appx and Microsoft.NET.Native.Framework.1.7.appx.</span></span>

1. <span data-ttu-id="a3ec7-195">请验证你的设备是否已进行开发解锁。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-195">Please verify that your device is dev unlocked.</span></span>  <span data-ttu-id="a3ec7-196">如果之前尚未执行此操作，请参阅[使用 Windows 设备门户](/windows/mixed-reality/using-the-windows-device-portal)了解相关说明。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-196">If you haven't done that before, see [Using the Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal) for instructions.</span></span>

1. <span data-ttu-id="a3ec7-197">然后，你需要进入 Windows 设备门户。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-197">You then want to get into the Windows Device Portal.</span></span> <span data-ttu-id="a3ec7-198">我们的建议是通过 USB 来完成此操作，可以通过在浏览器中键入来完成此操作 http://127.0.0.1:10080 。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-198">Our recommendation is to do this over USB and you would do that by typing http://127.0.0.1:10080 into your browser.</span></span>

1. <span data-ttu-id="a3ec7-199">完成 Windows 设备门户后，我们需要你将下载的两个文件 "端加载"。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-199">After you have the Windows Device Portal up we need you to "side load" the two files that you downloaded.</span></span> <span data-ttu-id="a3ec7-200">要执行此操作，需要向下滚动到 " **应用** " 部分，并选择 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-200">To do that you need to go down the left side bar until you get to the **Apps** section and select **Apps**.</span></span>

1. <span data-ttu-id="a3ec7-201">随后会看到类似于下面的屏幕。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-201">You will then see a screen that is similar to the below.</span></span>  <span data-ttu-id="a3ec7-202">要转到 " **安装应用程序** " 部分，并浏览到解压这两个 APPX 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-202">You want to go to the section that says **Install App** and browse to where you unzipped those two APPX files.</span></span> <span data-ttu-id="a3ec7-203">你一次只能执行一个操作，因此在选择第一个项后，在 "部署" 部分下单击 "开始"。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-203">You can only do one at a time, so after you select the first one, then click on "Go" under the Deploy section.</span></span> <span data-ttu-id="a3ec7-204">然后对第二个 APPX 文件执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-204">Then do this for the second APPX file.</span></span>

   ![Windows用于安装 Side-Loaded 应用的设备门户](images/20190322-DevicePortal.png)

1. <span data-ttu-id="a3ec7-206">此时，我们相信您的应用程序应再次开始工作，您也可以访问应用商店。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-206">At this point we believe your applications should start working again and that you can also get to the Store.</span></span>

1. <span data-ttu-id="a3ec7-207">在某些情况下，在启动受影响的应用程序之前，需要运行额外的步骤来启动3D 查看器应用程序。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-207">In some cases, it is necessary run the additional step of launching the 3D Viewer app before affected apps will launch.</span></span>

<span data-ttu-id="a3ec7-208">我们非常感谢你的耐心，因为我们已经完成了解决此问题的过程，我们期待继续与我们的社区合作，以创建成功的混合现实体验。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-208">We appreciate your patience as we have gone through the process to get this issue resolved, and we look forward to continued working with our community to create successful Mixed Reality experiences.</span></span>

### <a name="device-update"></a><span data-ttu-id="a3ec7-209">设备更新</span><span class="sxs-lookup"><span data-stu-id="a3ec7-209">Device Update</span></span>

- <span data-ttu-id="a3ec7-210">30秒后，shell 可能会消失一次。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-210">30 seconds after a new update, the shell may disappear one time.</span></span> <span data-ttu-id="a3ec7-211">请执行 **布隆** 手势以恢复会话。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-211">Please perform the **bloom** gesture to resume your session.</span></span>

### <a name="visual-studio"></a><span data-ttu-id="a3ec7-212">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a3ec7-212">Visual Studio</span></span>

- <span data-ttu-id="a3ec7-213">请参阅安装适用于 HoloLens 开发的 Visual Studio 的最新版本的[工具](/windows/mixed-reality/install-the-tools)。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-213">See [Install the tools](/windows/mixed-reality/install-the-tools) for the most up-to-date version of Visual Studio that is recommended for HoloLens development.</span></span>

- <span data-ttu-id="a3ec7-214">将 Visual Studio 中的应用部署到 HoloLens 时，可能会看到以下错误：**无法在已打开用户映射的文件中对文件执行所请求的操作。 (异常从 HRESULT： 0x800704C8)**。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-214">When deploying an app from Visual Studio to your HoloLens, you may see the error: **The requested operation cannot be performed on a file with a user-mapped section open. (Exception from HRESULT: 0x800704C8)**.</span></span> <span data-ttu-id="a3ec7-215">如果发生这种情况，请重试，部署通常会成功。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-215">If this happens, try again and your deployment will generally succeed.</span></span>

### <a name="api"></a><span data-ttu-id="a3ec7-216">API</span><span class="sxs-lookup"><span data-stu-id="a3ec7-216">API</span></span>

- <span data-ttu-id="a3ec7-217">如果应用程序将 [焦点](/windows/mixed-reality/focus-point-in-unity) 置于用户后面或 "正常" 设置为 "摄像"，则全息体将不会在混合现实捕获照片或视频中出现。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-217">If the application sets the [focus point](/windows/mixed-reality/focus-point-in-unity) behind the user or the normal to camera.forward, holograms will not appear in Mixed Reality Capture photos or videos.</span></span> <span data-ttu-id="a3ec7-218">在 Windows 中修复此 bug 之前，如果应用程序主动设置了[焦点](/windows/mixed-reality/focus-point-in-unity)，则应确保平面正常设置为相对相机前 (例如，normal =-摄像) 。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-218">Until this bug is fixed in Windows, if applications actively set the [focus point](/windows/mixed-reality/focus-point-in-unity) they should ensure the plane normal is set opposite camera-forward (for example, normal = -camera.forward).</span></span>

### <a name="xbox-wireless-controller"></a><span data-ttu-id="a3ec7-219">Xbox 无线控制器</span><span class="sxs-lookup"><span data-stu-id="a3ec7-219">Xbox Wireless Controller</span></span>

- <span data-ttu-id="a3ec7-220">必须先更新 Xbox 无线控制器，然后才能将其与 HoloLens 一起使用。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-220">Xbox Wireless Controller S must be updated before it can be used with HoloLens.</span></span> <span data-ttu-id="a3ec7-221">尝试将控制器与 HoloLens 配对之前，请确保你是[最](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter)新的。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-221">Ensure you are [up to date](https://support.xbox.com/xbox-one/accessories/update-controller-for-stereo-headset-adapter) before attempting to pair your controller with a HoloLens.</span></span>

- <span data-ttu-id="a3ec7-222">如果在连接 Xbox 无线控制器时重新启动 HoloLens，控制器将不会自动重新连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-222">If you reboot your HoloLens while the Xbox Wireless Controller is connected, the controller will not automatically reconnect to HoloLens.</span></span> <span data-ttu-id="a3ec7-223">在3分钟后控制器关闭之前，"指南" 按钮指示灯会慢慢闪烁。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-223">The Guide button light will flash slowly until the controller powers off after 3 minutes.</span></span> <span data-ttu-id="a3ec7-224">若要立即重新连接控制器，请关闭控制器电源，方法是按住 "指南" 按钮，直到指示灯亮起。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-224">To reconnect your controller immediately, power off the controller by holding the Guide button until the light turns off.</span></span> <span data-ttu-id="a3ec7-225">再次打开控制器时，它会重新连接到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-225">When you power your controller on again, it will reconnect to HoloLens.</span></span>

- <span data-ttu-id="a3ec7-226">如果在连接 Xbox 无线控制器时 HoloLens 进入待机状态，则控制器上的任何输入都将唤醒 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-226">If your HoloLens enters standby while the Xbox Wireless Controller is connected, any input on the controller will wake the HoloLens.</span></span> <span data-ttu-id="a3ec7-227">使用完控制器后，可以通过关闭控制器来阻止此操作。</span><span class="sxs-lookup"><span data-stu-id="a3ec7-227">You can prevent this by powering off your controller when you are done using it.</span></span>

