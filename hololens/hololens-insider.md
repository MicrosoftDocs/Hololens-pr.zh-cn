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
ms.date: 4/21/2020
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens 2
ms.openlocfilehash: e00c043f7de1142e4d2e08e41ff0d91123d4a98b
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827667"
---
# <span data-ttu-id="7cfa5-103">Microsoft HoloLens 内部预览版</span><span class="sxs-lookup"><span data-stu-id="7cfa5-103">Insider preview for Microsoft HoloLens</span></span>

<span data-ttu-id="7cfa5-104">欢迎使用适用于 HoloLens 的最新预览体验计划预览版！</span><span class="sxs-lookup"><span data-stu-id="7cfa5-104">Welcome to the latest Insider Preview builds for HoloLens!</span></span>  <span data-ttu-id="7cfa5-105">这是一种非常简单的功能，可提供针对 HoloLens 的下一个主要操作系统更新的宝贵反馈。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-105">It's simple to get started and provide valuable feedback for our next major operating system update for HoloLens.</span></span>

## <span data-ttu-id="7cfa5-106">开始接收 Insider 内部版本</span><span class="sxs-lookup"><span data-stu-id="7cfa5-106">Start receiving Insider builds</span></span>

<span data-ttu-id="7cfa5-107">在 HoloLens 2 设备上，转到 "**设置**"  ->  **更新 & 安全**  ->  **Windows 预览体验计划**"，然后选择"**开始**"。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-107">On a HoloLens 2 device go to **Settings** -> **Update & Security** -> **Windows Insider Program** and select **Get started**.</span></span> <span data-ttu-id="7cfa5-108">将用于注册的帐户链接到 Windows 预览体验成员。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-108">Link the account you used to register as a Windows Insider.</span></span>

<span data-ttu-id="7cfa5-109">然后，选择 " **Windows 的活动开发**"，选择是要接收**快速**还是**慢速**生成，并查看程序条款。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-109">Then, select **Active development of Windows**, choose whether you'd like to receive **Fast** or **Slow** builds, and review the program terms.</span></span>

<span data-ttu-id="7cfa5-110">选择 "**确认"-> "立即重启**" 完成操作。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-110">Select **Confirm -> Restart Now** to finish up.</span></span> <span data-ttu-id="7cfa5-111">重新启动设备后，转到 "**设置"-> 更新 & 安全 > 检查更新**以获取最新版本。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-111">After your device has rebooted, go to **Settings -> Update & Security -> Check for updates** to get the latest build.</span></span>

## <span data-ttu-id="7cfa5-112">停止接收 Insider 内部版本</span><span class="sxs-lookup"><span data-stu-id="7cfa5-112">Stop receiving Insider builds</span></span>

<span data-ttu-id="7cfa5-113">如果您不想再收到 Windows 全息版的预览体验计划，则可以在 HoloLens 运行生产内部版本时选择退出，也可以使用高级恢复助理将[设备恢复到](hololens-recovery.md)非预览体验的 windows 全息版。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-113">If you no longer want to receive Insider builds of Windows Holographic, you can opt out when your HoloLens is running a production build, or you can [recover your device](hololens-recovery.md) using the Advanced Recovery Companion to recover your device to a non-Insider version of Windows Holographic.</span></span>

> [!CAUTION]
> <span data-ttu-id="7cfa5-114">在手动重新安装新预览版后，从预览体验计划版本注册的用户将遇到蓝屏问题。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-114">There is a known issue in which users who un-enroll from Insider Preview builds after manually reinstalling a fresh preview build would experience a blue screen.</span></span> <span data-ttu-id="7cfa5-115">之后，他们必须手动恢复其设备。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-115">Afterwards they must manually recover their device.</span></span> <span data-ttu-id="7cfa5-116">有关如果你受到影响或不受影响的详细信息，请查看有关此[已知问题](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-116">For full details on if you would be impacted or not, please view more on this [Known Issue](https://docs.microsoft.com/hololens/hololens-known-issues?source=docs#blue-screen-is-shown-after-unenrolling-from-insider-preview-builds-on-a-device-reflashed-with-a-insider-build).</span></span>

<span data-ttu-id="7cfa5-117">若要验证 HoloLens 是否正在运行生产内部版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7cfa5-117">To verify that your HoloLens is running a production build:</span></span>

1. <span data-ttu-id="7cfa5-118">转到 "**设置" > "系统 >**"，然后找到内部版本号。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-118">Go to **Settings > System > About**, and find the build number.</span></span>
1. [<span data-ttu-id="7cfa5-119">请参阅生产内部版本号的发行说明。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-119">See the release notes for production build numbers.</span></span>](hololens-release-notes.md)

<span data-ttu-id="7cfa5-120">若要退出预览体验计划内部版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7cfa5-120">To opt out of Insider builds:</span></span>

1. <span data-ttu-id="7cfa5-121">在运行生产版本的 HoloLens 上，转到 "**设置" > 更新 Windows 预览体验计划 & 安全 >**，然后选择 "**停止预览体验成员版本**"。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-121">On a HoloLens running a production build, go to **Settings > Update & Security > Windows Insider Program**, and select **Stop Insider builds**.</span></span>
1. <span data-ttu-id="7cfa5-122">按照说明选择退出您的设备。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-122">Follow the instructions to opt out your device.</span></span>



## <span data-ttu-id="7cfa5-123">提供反馈和报告问题</span><span class="sxs-lookup"><span data-stu-id="7cfa5-123">Provide feedback and report issues</span></span>

<span data-ttu-id="7cfa5-124">请使用 HoloLens 上[的 "反馈中心" 应用](hololens-feedback.md)提供反馈和报告问题。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-124">Please use [the Feedback Hub app](hololens-feedback.md) on your HoloLens to provide feedback and report issues.</span></span> <span data-ttu-id="7cfa5-125">使用 "反馈中心" 可确保包含所有必要的诊断信息，以帮助我们的工程师快速调试和解决问题。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-125">Using Feedback Hub ensures that all necessary diagnostics information is included to help our engineers quickly debug and resolve the problem.</span></span>  <span data-ttu-id="7cfa5-126">必须以相同的方式报告与中文和日语版本的 HoloLens 有关的问题。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-126">Issues with the Chinese and Japanese version of HoloLens should be reported the same way.</span></span>

> [!NOTE]
> <span data-ttu-id="7cfa5-127">请确保接受询问您是否希望 "反馈中心" 访问您的 "文档" 文件夹的提示（在出现提示时选择 **"是"** ）。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-127">Be sure to accept the prompt that asks whether you'd like Feedback Hub to access your Documents folder (select **Yes** when prompted).</span></span>

## <span data-ttu-id="7cfa5-128">适用于开发人员的备注</span><span class="sxs-lookup"><span data-stu-id="7cfa5-128">Note for developers</span></span>

<span data-ttu-id="7cfa5-129">欢迎和鼓励你尝试使用 HoloLens 的预览体验成员版本来开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-129">You are welcome and encouraged to try developing your applications using Insider builds of HoloLens.</span></span>  <span data-ttu-id="7cfa5-130">请查看[HoloLens 开发人员文档](https://developer.microsoft.com/windows/mixed-reality/development)以开始使用。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-130">Check out the [HoloLens Developer Documentation](https://developer.microsoft.com/windows/mixed-reality/development) to get started.</span></span> <span data-ttu-id="7cfa5-131">这些相同的说明适用于 HoloLens 的预览体验计划版本。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-131">Those same instructions work with Insider builds of HoloLens.</span></span>  <span data-ttu-id="7cfa5-132">你可以使用你已用于 HoloLens 开发的 Unity 和 Visual Studio 的相同版本。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-132">You can use the same builds of Unity and Visual Studio that you're already using for HoloLens development.</span></span>


## <span data-ttu-id="7cfa5-133">Windows 预览体验计划发行说明</span><span class="sxs-lookup"><span data-stu-id="7cfa5-133">Windows Insider Release Notes</span></span>

<span data-ttu-id="7cfa5-134">从我们的[Windows 全息版2020更新](hololens-release-notes.md)发布，我们的所有发布预览版 feautres 现在都 avalible！</span><span class="sxs-lookup"><span data-stu-id="7cfa5-134">As of our [Windows Holographic May 2020 Update](hololens-release-notes.md) release all of our release preview feautres are now generally avalible!</span></span> <span data-ttu-id="7cfa5-135">请确保[更新 HoloLens](hololens-update-hololens.md)以获取所有最新功能。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-135">Make sure to [update your HoloLens](hololens-update-hololens.md) to get all the latest features.</span></span>  

<span data-ttu-id="7cfa5-136">我们将再次通过新功能再次更新此页面，因为我们将这些新功能发布给 Windows 预览体验成员内部版本。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-136">We'll be updating this page again with new features again as we release them to Windows Insider builds.</span></span> 

### <span data-ttu-id="7cfa5-137">FFU 下载和快闪路线</span><span class="sxs-lookup"><span data-stu-id="7cfa5-137">FFU download and flash directions</span></span>
<span data-ttu-id="7cfa5-138">若要使用带流量签名的 ffu 进行测试，首先必须在闪烁已签名的 ffu 之前，再将设备解锁。</span><span class="sxs-lookup"><span data-stu-id="7cfa5-138">To test with a flight signed ffu, you first have to flight unlock your device prior to flashing the flight signed ffu.</span></span>
1. <span data-ttu-id="7cfa5-139">在 PC 上</span><span class="sxs-lookup"><span data-stu-id="7cfa5-139">On PC</span></span>
    1. <span data-ttu-id="7cfa5-140">从以下计算机下载 ffu：[https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)</span><span class="sxs-lookup"><span data-stu-id="7cfa5-140">Download ffu to your PC from: [https://aka.ms/hololenspreviewdownload](https://aka.ms/hololenspreviewdownload)</span></span>
    1. <span data-ttu-id="7cfa5-141">从 Microsoft Store 安装 ARC （高级恢复助理）：[https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span><span class="sxs-lookup"><span data-stu-id="7cfa5-141">Install ARC (Advanced Recovery Companion) from the Microsoft Store: [https://www.microsoft.com/store/productId/9P74Z35SFRS8](https://www.microsoft.com/store/productId/9P74Z35SFRS8)</span></span> 
1. <span data-ttu-id="7cfa5-142">在 HoloLens-航班解锁：打开**设置**  >  **更新 & 安全**  >  **Windows 预览体验计划**，然后注册，重新启动设备</span><span class="sxs-lookup"><span data-stu-id="7cfa5-142">On HoloLens - Flight Unlock: Open **Settings** > **Update & Security** > **Windows Insider Program** then sign up, reboot device</span></span>
1. <span data-ttu-id="7cfa5-143">Flash FFU-现在，你可以使用 ARC 对已签名的 FFU 进行闪烁</span><span class="sxs-lookup"><span data-stu-id="7cfa5-143">Flash FFU - Now you can flash the flight signed FFU using ARC</span></span> 
