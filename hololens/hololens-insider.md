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
ms.date: 11/10/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: cb8ac3b6b74fd6998cde4d32df12dcbd84556597
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162952"
---
# <span data-ttu-id="e0f87-103">Microsoft HoloLens 内部预览版</span><span class="sxs-lookup"><span data-stu-id="e0f87-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="e0f87-104">欢迎使用适用于 HoloLens 的最新预览体验计划预览版！</span><span class="sxs-lookup"><span data-stu-id="e0f87-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="e0f87-105">这是一种非常简单的功能 [，可提供](hololens-insider.md#start-receiving-insider-builds) 针对 HoloLens 的下一个主要操作系统更新的宝贵反馈。</span><span class="sxs-lookup"><span data-stu-id="e0f87-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="e0f87-106">Windows 预览体验计划发行说明</span><span class="sxs-lookup"><span data-stu-id="e0f87-106">Windows Insider Release Notes</span></span>

### <span data-ttu-id="e0f87-107">通过应用安装程序在 HoloLens 2 上安装应用</span><span class="sxs-lookup"><span data-stu-id="e0f87-107">Install Apps on HoloLens 2 via App Installer</span></span>
<span data-ttu-id="e0f87-108">我们将在 Windows 全息版20H2 更新后立即发布应用安装程序功能。</span><span class="sxs-lookup"><span data-stu-id="e0f87-108">We will ship the app installer capability soon after our Windows Holographic, version 20H2 update.</span></span> <span data-ttu-id="e0f87-109">我们正在 \*\* (应用安装程序) 添加新功能，使你能够在 HoloLens 2 设备上更流畅地安装应用程序\*\* 。</span><span class="sxs-lookup"><span data-stu-id="e0f87-109">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="e0f87-110">默认情况下，此功能将 **在非托管设备上处于打开**状态。</span><span class="sxs-lookup"><span data-stu-id="e0f87-110">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="e0f87-111">为了防止企业中断，应用安装程序此时将不可 **用于托管设备** 。</span><span class="sxs-lookup"><span data-stu-id="e0f87-111">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="e0f87-112">如果以下 **任何** 条件成立，设备将被视为 "托管"：</span><span class="sxs-lookup"><span data-stu-id="e0f87-112">A device is considered “managed” if **any** of the following are true:</span></span>
- <span data-ttu-id="e0f87-113">MDM 已 [注册](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="e0f87-113">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="e0f87-114">配置了 [预配包](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="e0f87-114">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="e0f87-115">用户 [标识](hololens-identity.md) 为 AAD</span><span class="sxs-lookup"><span data-stu-id="e0f87-115">User [Identity](hololens-identity.md) is AAD</span></span>

<span data-ttu-id="e0f87-116">现在，你可以安装应用，而无需启用开发人员模式或使用 Device Portal。</span><span class="sxs-lookup"><span data-stu-id="e0f87-116">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="e0f87-117">只需通过 USB 或边缘) 将 (下载到你的设备，然后在文件资源管理器中导航到 Appx 捆绑系统，系统会提示你启动安装。</span><span class="sxs-lookup"><span data-stu-id="e0f87-117">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="e0f87-118">或者， [从网页启动安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。</span><span class="sxs-lookup"><span data-stu-id="e0f87-118">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="e0f87-119">与使用 MDM 的 LOB 应用部署功能从 Microsoft Store 或旁加载安装的应用一样，应用需要使用 [签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 进行数字签名，并且 [用于签名的证书必须受](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) HoloLens 设备信任才能部署应用。</span><span class="sxs-lookup"><span data-stu-id="e0f87-119">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

**<span data-ttu-id="e0f87-120">应用程序安装说明。</span><span class="sxs-lookup"><span data-stu-id="e0f87-120">Application install instructions.</span></span>**

1.  <span data-ttu-id="e0f87-121">确保你的设备不被视为托管设备</span><span class="sxs-lookup"><span data-stu-id="e0f87-121">Ensure that your device is not considered managed</span></span>
1.  <span data-ttu-id="e0f87-122">确保 HoloLens 2 设备已开机且已连接到你的电脑</span><span class="sxs-lookup"><span data-stu-id="e0f87-122">Ensure that your HoloLens 2 device is powered on and connected to your PC</span></span>
1.  <span data-ttu-id="e0f87-123">确保已登录到 HoloLens 2 设备</span><span class="sxs-lookup"><span data-stu-id="e0f87-123">Ensure that you are signed into the HoloLens 2 device</span></span>
1.  <span data-ttu-id="e0f87-124">在你的电脑上导航到你的自定义应用，并将 yourapp 复制到 yourdevicename\Internal Storage\Downloads。</span><span class="sxs-lookup"><span data-stu-id="e0f87-124">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>   <span data-ttu-id="e0f87-125">完成文件复制后，您可以断开设备连接</span><span class="sxs-lookup"><span data-stu-id="e0f87-125">After you’ve finished copying your file you can disconnect your device</span></span>
1.  <span data-ttu-id="e0f87-126">从 HoloLens 2 设备打开 "开始" 菜单，选择 "所有应用"，然后启动 "文件资源管理器" 应用。</span><span class="sxs-lookup"><span data-stu-id="e0f87-126">From your HoloLens 2 device Open the Start Menu, select All apps and launch the File Explorer app.</span></span>
1.  <span data-ttu-id="e0f87-127">导航到 "下载" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="e0f87-127">Navigate to the Downloads folder.</span></span> <span data-ttu-id="e0f87-128">你可能需要在应用的左侧面板上，选择 "此设备"，然后导航到 "下载"。</span><span class="sxs-lookup"><span data-stu-id="e0f87-128">You may need to on the left panel of the app select This device first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="e0f87-129">选择 yourapp 文件。</span><span class="sxs-lookup"><span data-stu-id="e0f87-129">Select the yourapp.appxbundle file.</span></span>
1.  <span data-ttu-id="e0f87-130">应用安装程序将启动。</span><span class="sxs-lookup"><span data-stu-id="e0f87-130">The App Installer will launch.</span></span> <span data-ttu-id="e0f87-131">选择 "安装" 按钮以安装你的应用。</span><span class="sxs-lookup"><span data-stu-id="e0f87-131">Select the Install button to install your app.</span></span>
<span data-ttu-id="e0f87-132">已安装的应用将在安装完成后自动启动。</span><span class="sxs-lookup"><span data-stu-id="e0f87-132">The installed app will automatically launch upon completion of installation.</span></span>

<span data-ttu-id="e0f87-133">你可以在 [Windows 通用示例 GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) 上找到示例应用来测试此流程。</span><span class="sxs-lookup"><span data-stu-id="e0f87-133">You can find sample apps on [Windows Universal Samples GitHub](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples) to test this flow.</span></span>

<span data-ttu-id="e0f87-134">有关 [在 HoloLens 2 上安装应用](app-deploy-app-installer.md)的完整过程，请参阅应用安装程序。</span><span class="sxs-lookup"><span data-stu-id="e0f87-134">Read about the full process of [installing apps on HoloLens 2 with the App Installer](app-deploy-app-installer.md).</span></span>  

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

## <span data-ttu-id="e0f87-136">开始接收 Insider 内部版本</span><span class="sxs-lookup"><span data-stu-id="e0f87-136">Start receiving Insider builds</span></span>

> [!NOTE]
> <span data-ttu-id="e0f87-137">如果您最近未进行更新，请重启设备以更新状态并获取最新版本。</span><span class="sxs-lookup"><span data-stu-id="e0f87-137">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="e0f87-138">"重新启动设备" 语音命令的效果很好。</span><span class="sxs-lookup"><span data-stu-id="e0f87-138">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="e0f87-139">您也可以选择 "设置/Windows 预览体验计划" 中的 "重新启动" 按钮。</span><span class="sxs-lookup"><span data-stu-id="e0f87-139">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="e0f87-140">我们在可能遇到的后端遇到错误，这将使你恢复进度。</span><span class="sxs-lookup"><span data-stu-id="e0f87-140">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="e0f87-141">在 HoloLens 2 设备上，转到 "**设置**"  >  **更新 & 安全**  >  **Windows 预览体验计划**"，然后选择"**开始**"。</span><span class="sxs-lookup"><span data-stu-id="e0f87-141">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="e0f87-142">将用于注册的帐户链接到 Windows 预览体验成员。</span><span class="sxs-lookup"><span data-stu-id="e0f87-142">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="e0f87-143">Windows 预览体验成员现在正在移至频道。</span><span class="sxs-lookup"><span data-stu-id="e0f87-143">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="e0f87-144">**快速**环将成为**开发频道**，**慢速**环将成为**Beta 通道**，并且 "**发布预览**" 环将成为 "**发布" 预览频道**。</span><span class="sxs-lookup"><span data-stu-id="e0f87-144">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="e0f87-145">映射如下所示：</span><span class="sxs-lookup"><span data-stu-id="e0f87-145">Here is what that mapping looks like:</span></span>

![Windows 预览体验计划频道说明](images/WindowsInsiderChannels.png)

<span data-ttu-id="e0f87-147">有关详细信息，请参阅 Windows 博客上的 [Windows 预览体验成员频道简介](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 。</span><span class="sxs-lookup"><span data-stu-id="e0f87-147">For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>

<span data-ttu-id="e0f87-148">然后，选择 " **Windows 的活动开发**"，选择是要接收 **开发渠道** 还是 **Beta 频道** 内部版本，并查看计划条款。</span><span class="sxs-lookup"><span data-stu-id="e0f87-148">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>

<span data-ttu-id="e0f87-149">选择 " **确认" > "立即重启** " 完成。</span><span class="sxs-lookup"><span data-stu-id="e0f87-149">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="e0f87-150">重新启动设备后，转到 " **设置" > 更新 & 安全 > 检查更新** 以获取最新版本。</span><span class="sxs-lookup"><span data-stu-id="e0f87-150">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="e0f87-151">FFU 下载和快闪路线</span><span class="sxs-lookup"><span data-stu-id="e0f87-151">FFU download and flash directions</span></span>
<span data-ttu-id="e0f87-152">若要使用带流量签名的 ffu 进行测试，首先必须在闪烁已签名的 ffu 之前，再将设备解锁。</span><span class="sxs-lookup"><span data-stu-id="e0f87-152">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="e0f87-153">在 PC 上：</span><span class="sxs-lookup"><span data-stu-id="e0f87-153">On PC:</span></span>

    1. <span data-ttu-id="e0f87-154">将 ffu 下载到电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="e0f87-154">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="e0f87-155">从 Microsoft Store 安装 ARC (高级恢复配套) ： [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="e0f87-155">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span>
    
1. <span data-ttu-id="e0f87-156">在 HoloLens-航班解锁：打开**设置**  >  **更新 & 安全**  >  **Windows 预览体验计划**，然后注册，重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="e0f87-156">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>

1. <span data-ttu-id="e0f87-157">Flash FFU-现在，你可以使用 ARC 对已签名的 FFU 进行闪烁。</span><span class="sxs-lookup"><span data-stu-id="e0f87-157">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>

## <span data-ttu-id="e0f87-158">提供反馈和报告问题</span><span class="sxs-lookup"><span data-stu-id="e0f87-158">Provide feedback and report issues</span></span>

<span data-ttu-id="e0f87-159">请使用 HoloLens 上 [的 "反馈中心" 应用](hololens-feedback.md) 提供反馈和报告问题。</span><span class="sxs-lookup"><span data-stu-id="e0f87-159">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="e0f87-160">使用 "反馈中心" 可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。</span><span class="sxs-lookup"><span data-stu-id="e0f87-160">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="e0f87-161">必须以相同的方式报告与中文和日语版本的 HoloLens 有关的问题。</span><span class="sxs-lookup"><span data-stu-id="e0f87-161">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="e0f87-162">请务必接受询问是否希望 "反馈中心" 访问你的 "文档" 文件夹的提示 (在出现提示时选择 **"是"**) 。</span><span class="sxs-lookup"><span data-stu-id="e0f87-162">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="e0f87-163">适用于开发人员的备注</span><span class="sxs-lookup"><span data-stu-id="e0f87-163">Note for developers</span></span>

<span data-ttu-id="e0f87-164">欢迎和鼓励你尝试使用 HoloLens 的预览体验成员版本来开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="e0f87-164">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="e0f87-165">请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 以开始使用。</span><span class="sxs-lookup"><span data-stu-id="e0f87-165">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="e0f87-166">这些相同的说明适用于 HoloLens 的预览体验计划版本。</span><span class="sxs-lookup"><span data-stu-id="e0f87-166">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="e0f87-167">你可以使用你已用于 HoloLens 开发的 Unity 和 Visual Studio 的相同版本。</span><span class="sxs-lookup"><span data-stu-id="e0f87-167">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>

## <span data-ttu-id="e0f87-168">停止接收 Insider 内部版本</span><span class="sxs-lookup"><span data-stu-id="e0f87-168">Stop receiving Insider builds</span></span>

<span data-ttu-id="e0f87-169">如果您不想再收到 Windows 全息版的预览体验计划，则可以在 HoloLens 运行生产内部版本时选择退出，也可以使用高级恢复助理将 [设备恢复到](hololens-recovery.md) 非预览体验的 windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="e0f87-169">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="e0f87-170">在手动重新安装新预览版后，从预览体验计划版本注册的用户将遇到蓝屏问题。</span><span class="sxs-lookup"><span data-stu-id="e0f87-170">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="e0f87-171">之后，他们必须手动恢复其设备。</span><span class="sxs-lookup"><span data-stu-id="e0f87-171">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="e0f87-172">有关如果你受到影响或不受影响的详细信息，请查看有关此 [已知问题](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e0f87-172">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="e0f87-173">若要验证 HoloLens 是否正在运行生产内部版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e0f87-173">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="e0f87-174">转到 " **设置" > "系统 >**"，然后找到内部版本号。</span><span class="sxs-lookup"><span data-stu-id="e0f87-174">Go to **Settings > System > About**, and find the build number.</span></span>

1. <span data-ttu-id="e0f87-175">[请参阅生产内部版本号的发行说明](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="e0f87-175">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>

<span data-ttu-id="e0f87-176">若要退出预览体验计划内部版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e0f87-176">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="e0f87-177">在运行生产版本的 HoloLens 上，转到 " **设置" > 更新 Windows 预览体验计划 & 安全 >**，然后选择 " **停止预览体验成员版本**"。</span><span class="sxs-lookup"><span data-stu-id="e0f87-177">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>

1. <span data-ttu-id="e0f87-178">按照说明选择退出您的设备。</span><span class="sxs-lookup"><span data-stu-id="e0f87-178">Follow the instructions to opt out your device.</span></span>
