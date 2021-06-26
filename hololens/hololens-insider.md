---
title: 适用于 Microsoft HoloLens 的 Insider Preview
description: 了解如何开始使用预览体验内部版本，并为 HoloLens 的下一次主要操作系统更新提供有价值的反馈。
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
ms.date: 04/01/2021
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: 8b8c3c26ff743a4df0010110d0fe6e2930646c86
ms.sourcegitcommit: add53aa73588986a3430cdc0310af7665a038cfc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2021
ms.locfileid: "112977236"
---
# <a name="insider-preview-for-microsoft-hololens"></a><span data-ttu-id="6987a-103">适用于 Microsoft HoloLens 的 Insider Preview</span><span class="sxs-lookup"><span data-stu-id="6987a-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="6987a-104">欢迎使用 HoloLens 的最新 Insider Preview 版本！</span><span class="sxs-lookup"><span data-stu-id="6987a-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span> <span data-ttu-id="6987a-105">它易于入门 [，](hololens-insider.md#start-receiving-insider-builds) 并为 HoloLens 的下一次主要操作系统更新提供有价值的反馈。</span><span class="sxs-lookup"><span data-stu-id="6987a-105">It's simple to [get started](hololens-insider.md#start-receiving-insider-builds) and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <a name="windows-insider-release-notes"></a><span data-ttu-id="6987a-106">Windows 预览体验成员发行说明</span><span class="sxs-lookup"><span data-stu-id="6987a-106">Windows Insider Release Notes</span></span>

<span data-ttu-id="6987a-107">我们很高兴再次开始向 Windows 预览体验成员提供新功能。</span><span class="sxs-lookup"><span data-stu-id="6987a-107">We're excited to start flighting new features to Windows Insiders again.</span></span> <span data-ttu-id="6987a-108">新内部版本将前往开发和 Beta 通道获取最新更新。</span><span class="sxs-lookup"><span data-stu-id="6987a-108">New builds will be flighting to the Dev and Beta Channels for the latest updates.</span></span> <span data-ttu-id="6987a-109">我们将继续更新此页面，因为我们向新的内部版本添加更多功能Windows 预览体验成员更新。</span><span class="sxs-lookup"><span data-stu-id="6987a-109">We will continue to update this page as we add more features and updates to our Windows Insider builds.</span></span> <span data-ttu-id="6987a-110">准备好将这些更新混合到现实中，</span><span class="sxs-lookup"><span data-stu-id="6987a-110">Get excited and ready to mix these updates into your reality.</span></span>

| <span data-ttu-id="6987a-111">功能</span><span class="sxs-lookup"><span data-stu-id="6987a-111">Feature</span></span>                 | <span data-ttu-id="6987a-112">说明</span><span class="sxs-lookup"><span data-stu-id="6987a-112">Description</span></span>                | <span data-ttu-id="6987a-113">目标用户</span><span class="sxs-lookup"><span data-stu-id="6987a-113">Target Users</span></span> | <span data-ttu-id="6987a-114">引入的生成</span><span class="sxs-lookup"><span data-stu-id="6987a-114">Build introduced</span></span> |
|-------------------------|----------------------------|--------------|------------------|
| <span data-ttu-id="6987a-115">HoloLens 上的 CSP 更改</span><span class="sxs-lookup"><span data-stu-id="6987a-115">CSP Changes on HoloLens</span></span> | <span data-ttu-id="6987a-116">用于查询数据的新 CSP</span><span class="sxs-lookup"><span data-stu-id="6987a-116">New CSPs for to query data</span></span> | <span data-ttu-id="6987a-117">IT 管理员</span><span class="sxs-lookup"><span data-stu-id="6987a-117">IT Admins</span></span>    | <span data-ttu-id="6987a-118">20348.1403</span><span class="sxs-lookup"><span data-stu-id="6987a-118">20348.1403</span></span>                 |

### <a name="csp-changes-on-hololens"></a><span data-ttu-id="6987a-119">HoloLens 上的 CSP 更改</span><span class="sxs-lookup"><span data-stu-id="6987a-119">CSP changes on HoloLens</span></span>

- <span data-ttu-id="6987a-120">在内部Windows 预览体验成员中引入，20348.1403</span><span class="sxs-lookup"><span data-stu-id="6987a-120">Introduced in Windows Insider build, 20348.1403</span></span>

#### <a name="devdetail-csp"></a><span data-ttu-id="6987a-121">DevDetail 云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="6987a-121">DevDetail CSP</span></span>

<span data-ttu-id="6987a-122">DevDetail CSP 现在还会报告 HoloLens 设备上的免费存储空间。</span><span class="sxs-lookup"><span data-stu-id="6987a-122">DevDetail CSP now also reports free storage space on HoloLens device.</span></span> <span data-ttu-id="6987a-123">这应该与设置应用的"存储"页中显示的值大致匹配。</span><span class="sxs-lookup"><span data-stu-id="6987a-123">This should approximately match with the value shown in Settings App's Storage page.</span></span> <span data-ttu-id="6987a-124">下面是包含此信息的特定节点。</span><span class="sxs-lookup"><span data-stu-id="6987a-124">Following is the specific node containing this information.</span></span>

- <span data-ttu-id="6987a-125">./DevDetail/Ext/Microsoft/FreeStorage (GET) </span><span class="sxs-lookup"><span data-stu-id="6987a-125">./DevDetail/Ext/Microsoft/FreeStorage (GET operation only)</span></span>

#### <a name="devicestatus-csp"></a><span data-ttu-id="6987a-126">DeviceStatus 云解决方案提供商</span><span class="sxs-lookup"><span data-stu-id="6987a-126">DeviceStatus CSP</span></span>

<span data-ttu-id="6987a-127">DeviceStatus CSP 现在还报告主动连接 HoloLens 的 Wifi 网络的 SSID 和 BSSID。</span><span class="sxs-lookup"><span data-stu-id="6987a-127">DeviceStatus CSP now also reports SSID and BSSID of Wifi network with which HoloLens is actively connected.</span></span> <span data-ttu-id="6987a-128">下面是包含此信息的特定节点。</span><span class="sxs-lookup"><span data-stu-id="6987a-128">Following are the specific nodes containing this information.</span></span>

- <span data-ttu-id="6987a-129">适配器 /SSID 的 ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac* Wi-Fi /SSID</span><span class="sxs-lookup"><span data-stu-id="6987a-129">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/SSID</span></span>
- <span data-ttu-id="6987a-130">适配器 /BSSID 的 ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac* 地址Wi-Fi /BSSID</span><span class="sxs-lookup"><span data-stu-id="6987a-130">./Vendor/MSFT/DeviceStatus/NetworkIdentifiers/*mac address of Wi-Fi adapter*/BSSID</span></span>

<span data-ttu-id="6987a-131">用于 MDM 供应商的 syncml blob (示例) 用于查询 NetworkIdentifiers</span><span class="sxs-lookup"><span data-stu-id="6987a-131">Example syncml blob (for MDM vendors) to query for NetworkIdentifiers</span></span>

```xml
<SyncML>
<SyncBody>
    <Get>
        <CmdID>$CmdID$</CmdID>
        <Item>
            <Target>
            <LocURI>
                ./Vendor/MSFT/DeviceStatus/NetworkIdentifiers?list=StructData
            </LocURI>
            </Target>
        </Item>
    </Get>
    <Final/>
</SyncBody>
</SyncML>
```

### <a name="fixes-and-improvements"></a><span data-ttu-id="6987a-132">修复和改进：</span><span class="sxs-lookup"><span data-stu-id="6987a-132">Fixes and improvements:</span></span>

- <span data-ttu-id="6987a-133">修复 [了在未提示设备门户锁定文件时出现此问题的已知问题。](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span><span class="sxs-lookup"><span data-stu-id="6987a-133">Fixed a [known issue for Device Portal where there was no prompt downloading locked files.](hololens-troubleshooting.md#downloading-locked-files-doesnt-error)</span></span>
- <span data-ttu-id="6987a-134">修复了 [文件上传设备门户下载的已知问题。](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span><span class="sxs-lookup"><span data-stu-id="6987a-134">Fixed a [known issue for Device Portal with file upload and download time outs.](hololens-troubleshooting.md#device-portal-file-uploaddownload-times-out)</span></span>

## <a name="start-receiving-insider-builds"></a><span data-ttu-id="6987a-135">开始接收预览体验内部版本</span><span class="sxs-lookup"><span data-stu-id="6987a-135">Start receiving Insider builds</span></span>
> [!NOTE]
> <span data-ttu-id="6987a-136">如果最近尚未更新，请重启设备以更新状态并获取最新生成。</span><span class="sxs-lookup"><span data-stu-id="6987a-136">If you haven’t updated recently, please reboot your device to update state and get the latest build.</span></span>
> - <span data-ttu-id="6987a-137">"重新启动设备"语音命令运行良好。</span><span class="sxs-lookup"><span data-stu-id="6987a-137">The “Reboot device” voice command works well.</span></span> 
> - <span data-ttu-id="6987a-138">还可以选择"设置/设置"中的"重启"Windows 预览体验计划。</span><span class="sxs-lookup"><span data-stu-id="6987a-138">You can also choose the restart button in Settings/Windows Insider Program.</span></span>
>
> <span data-ttu-id="6987a-139">我们在后端有一个 bug，你可能遇到了该 bug，这可让你重新进入轨道。</span><span class="sxs-lookup"><span data-stu-id="6987a-139">We had a bug on the back-end that you may have encountered and this will get you back on track.</span></span>

<span data-ttu-id="6987a-140">在设备上HoloLens 2"设置 **""更新**  >  **&"安全**  >  **Windows 预览体验计划并选择"\*\*\*\*开始使用"。**</span><span class="sxs-lookup"><span data-stu-id="6987a-140">On a HoloLens 2 device go to **Settings** > **Update & Security** > **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="6987a-141">链接用于注册为 Windows 预览体验成员。</span><span class="sxs-lookup"><span data-stu-id="6987a-141">Link the account you used to register as a Windows Insider.</span></span>
<span data-ttu-id="6987a-142">Windows 预览体验成员现在正在迁移到频道。</span><span class="sxs-lookup"><span data-stu-id="6987a-142">Windows insider is now moving to Channels.</span></span> <span data-ttu-id="6987a-143">快速 **通道** 将成为 **开发通道**，慢速通道 **将成为** Beta 版频道通道，发布预览通道将成为 **发布预览通道**。</span><span class="sxs-lookup"><span data-stu-id="6987a-143">The **Fast** ring will become the **Dev Channel**, the **Slow** ring will become the **Beta Channel**, and the **Release Preview** ring will become the **Release Preview Channel**.</span></span> <span data-ttu-id="6987a-144">下面是该映射的外观：Windows 预览体验成员频道说明。有关详细信息，请参阅 Windows 博客Windows 预览体验成员 ![ ](images/WindowsInsiderChannels.png) [频道](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) 介绍。</span><span class="sxs-lookup"><span data-stu-id="6987a-144">Here is what that mapping looks like: ![Windows Insider Channels explanation](images/WindowsInsiderChannels.png) For more information, see [Introducing Windows Insider Channels](https://blogs.windows.com/windowsexperience/2020/06/15/introducing-windows-insider-channels) on Windows Blogs.</span></span>
<span data-ttu-id="6987a-145">然后，**选择"Windows** 的活动开发"，选择要接收开发通道还是Beta 版频道 **版本，** 并查看计划条款。</span><span class="sxs-lookup"><span data-stu-id="6987a-145">Then, select **Active development of Windows**, choose whether you'd like to receive **Dev Channel** or **Beta Channel** builds, and review the program terms.</span></span>
<span data-ttu-id="6987a-146">选择 **">立即重启** "以完成操作。</span><span class="sxs-lookup"><span data-stu-id="6987a-146">Select **Confirm > Restart Now** to finish up.</span></span> <span data-ttu-id="6987a-147">重启设备后，转到"设置">更新 **&"安全性>检查更新** 以获取最新生成。</span><span class="sxs-lookup"><span data-stu-id="6987a-147">After your device has rebooted, go to **Settings > Update & Security > Check for updates** to get the latest build.</span></span>
### <a name="update-error-0x80070490-work-around"></a><span data-ttu-id="6987a-148">更新错误0x80070490问题</span><span class="sxs-lookup"><span data-stu-id="6987a-148">Update error 0x80070490 work-around</span></span>
<span data-ttu-id="6987a-149">如果在开发或 Beta 0x80070490更新时遇到更新错误，请尝试以下短期工作。</span><span class="sxs-lookup"><span data-stu-id="6987a-149">If you encounter an update error 0x80070490 when updating on the Dev or Beta channel, try the following short-term work around.</span></span> <span data-ttu-id="6987a-150">这涉及到移动预览体验成员通道、选取更新，然后将 Insider 通道移回。</span><span class="sxs-lookup"><span data-stu-id="6987a-150">It involves moving your insider channel, picking up the update and then moving your Insider channel back.</span></span>
#### <a name="stage-one---release-preview"></a><span data-ttu-id="6987a-151">第一阶段 - 发布预览版</span><span class="sxs-lookup"><span data-stu-id="6987a-151">Stage one - Release Preview</span></span>
1.  <span data-ttu-id="6987a-152">设置，更新&安全性，Windows 预览体验计划，选择"**发布预览通道"。**</span><span class="sxs-lookup"><span data-stu-id="6987a-152">Settings, Update & Security, Windows Insider Program, select **Release Preview Channel**.</span></span>
2.  <span data-ttu-id="6987a-153">设置、更新&安全性、Windows 更新、 **检查更新**。</span><span class="sxs-lookup"><span data-stu-id="6987a-153">Settings, Update & Security, Windows Update, **Check for updates**.</span></span> <span data-ttu-id="6987a-154">更新后，继续进入阶段 2。</span><span class="sxs-lookup"><span data-stu-id="6987a-154">After the update, continue on to Stage two.</span></span>
#### <a name="stage-two---dev-channel"></a><span data-ttu-id="6987a-155">阶段 2 - 开发通道</span><span class="sxs-lookup"><span data-stu-id="6987a-155">Stage two - Dev Channel</span></span>
1. <span data-ttu-id="6987a-156">设置，更新&安全性，Windows 预览体验计划，选择 **"开发通道"。**</span><span class="sxs-lookup"><span data-stu-id="6987a-156">Settings, Update & Security, Windows Insider Program, select **Dev Channel**.</span></span>
2. <span data-ttu-id="6987a-157">设置、更新&安全性、Windows 更新、 **检查更新**。</span><span class="sxs-lookup"><span data-stu-id="6987a-157">Settings, Update & Security, Windows Update, **Check for updates**.</span></span>
## <a name="ffu-download-and-flash-directions"></a><span data-ttu-id="6987a-158">FFU 下载和闪存说明</span><span class="sxs-lookup"><span data-stu-id="6987a-158">FFU download and flash directions</span></span>
<span data-ttu-id="6987a-159">若要使用已签署航班的 ffu 进行测试，首先需要先对设备进行飞行解锁，然后刷出已签署航班的 ffu。</span><span class="sxs-lookup"><span data-stu-id="6987a-159">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="6987a-160">在电脑上：</span><span class="sxs-lookup"><span data-stu-id="6987a-160">On PC:</span></span>
    1. <span data-ttu-id="6987a-161">从 将 ffu 下载到电脑 [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload) 。</span><span class="sxs-lookup"><span data-stu-id="6987a-161">Download ffu to your PC from [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload).</span></span>
    
    1. <span data-ttu-id="6987a-162">从以下 (安装 ARC) 高级恢复助手 [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8) Microsoft Store：。</span><span class="sxs-lookup"><span data-stu-id="6987a-162">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8).</span></span>
    
1. <span data-ttu-id="6987a-163">在"HoloLens - 航班解锁 **：打开设置** 更新  >  **&安全** Windows 预览体验计划  >  注册，重启设备。</span><span class="sxs-lookup"><span data-stu-id="6987a-163">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device.</span></span>
1. <span data-ttu-id="6987a-164">Flash FFU - 现在可以使用 ARC 刷出航班签名的 FFU。</span><span class="sxs-lookup"><span data-stu-id="6987a-164">Flash FFU - Now you can flash the flight signed FFU using ARC.</span></span>
### <a name="provide-feedback-and-report-issues"></a><span data-ttu-id="6987a-165">提供反馈并报告问题</span><span class="sxs-lookup"><span data-stu-id="6987a-165">Provide feedback and report issues</span></span>
<span data-ttu-id="6987a-166">请使用 [HoloLens](hololens-feedback.md) 反馈中心应用提供反馈并报告问题。</span><span class="sxs-lookup"><span data-stu-id="6987a-166">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="6987a-167">使用 反馈中心可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。</span><span class="sxs-lookup"><span data-stu-id="6987a-167">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="6987a-168">应该以相同方式报告中文版和日语版 HoloLens 的问题。</span><span class="sxs-lookup"><span data-stu-id="6987a-168">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>
> [!NOTE]
> <span data-ttu-id="6987a-169">请务必接受提示，询问你是否希望反馈中心 Documents 文件夹， (系统提示时选择"是) 。 </span><span class="sxs-lookup"><span data-stu-id="6987a-169">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>
## <a name="note-for-developers"></a><span data-ttu-id="6987a-170">开发人员说明</span><span class="sxs-lookup"><span data-stu-id="6987a-170">Note for developers</span></span>
<span data-ttu-id="6987a-171">欢迎并鼓励你尝试使用 HoloLens 预览体验内部版本开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="6987a-171">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="6987a-172">请查看 [HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development) 以开始使用。</span><span class="sxs-lookup"><span data-stu-id="6987a-172">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="6987a-173">这些相同的说明与 HoloLens 的预览体验内部版本一致。</span><span class="sxs-lookup"><span data-stu-id="6987a-173">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="6987a-174">可以使用与 HoloLens Visual Studio相同的 Unity 版本和版本。</span><span class="sxs-lookup"><span data-stu-id="6987a-174">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>
## <a name="stop-receiving-insider-builds"></a><span data-ttu-id="6987a-175">停止接收预览体验内部版本</span><span class="sxs-lookup"><span data-stu-id="6987a-175">Stop receiving Insider builds</span></span>
<span data-ttu-id="6987a-176">如果不再想要接收 Windows Holographic 的预览体验内部版本，可以在 HoloLens 运行生产版本时选择退出，或者可以使用高级[](hololens-recovery.md)恢复助手恢复设备，将设备恢复到 Windows Holographic 的非 Insider 版本。</span><span class="sxs-lookup"><span data-stu-id="6987a-176">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>
> [!CAUTION]
> <span data-ttu-id="6987a-177">存在一个已知问题：在手动重新安装新的预览版本后，从 Insider Preview 版本取消注册的用户将遇到蓝屏。</span><span class="sxs-lookup"><span data-stu-id="6987a-177">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="6987a-178">之后，他们必须手动恢复其设备。</span><span class="sxs-lookup"><span data-stu-id="6987a-178">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="6987a-179">有关是否受到影响的完整详细信息，请查看有关此已知 [问题的详细信息](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build)。</span><span class="sxs-lookup"><span data-stu-id="6987a-179">For full details on if you would be impacted or not, please view more on this [Known Issue](hololens-troubleshooting.md#blue-screen-after-unenrolling-from-insider-preview-on-a-device-flashed-with-an-insider-build).</span></span>
<span data-ttu-id="6987a-180">若要验证 HoloLens 是否正在运行生产内部版本，请运行：</span><span class="sxs-lookup"><span data-stu-id="6987a-180">To verify that your HoloLens is running a production build:</span></span>
1. <span data-ttu-id="6987a-181">转到" **系统>设置>"关于"，** 并找到生成号。</span><span class="sxs-lookup"><span data-stu-id="6987a-181">Go to **Settings > System > About**, and find the build number.</span></span>
1. <span data-ttu-id="6987a-182">[有关生产内部版本号，请参阅发行说明](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="6987a-182">[See the release notes for production build numbers](hololens-release-notes.md).</span></span>
<span data-ttu-id="6987a-183">选择退出预览体验内部版本：</span><span class="sxs-lookup"><span data-stu-id="6987a-183">To opt out of Insider builds:</span></span>
1. <span data-ttu-id="6987a-184">在运行生产内部运行的 HoloLens 上，转到"设置>更新&**安全> Windows 预览体验计划，** 然后选择"停止 **预览体验成员生成"。**</span><span class="sxs-lookup"><span data-stu-id="6987a-184">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="6987a-185">按照说明选择退出设备。</span><span class="sxs-lookup"><span data-stu-id="6987a-185">Follow the instructions to opt out your device.</span></span>
