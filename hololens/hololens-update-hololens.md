---
title: 更新 HoloLens 2
description: 了解如何检查你的 HoloLens 生成号，保持最新的设备更新，加入预览体验计划，以及回滚更新。
keywords: 操作说明，更新，回滚，HoloLens，检查生成，生成号
ms.prod: hololens
ms.sitesec: library
author: scooley
ms.author: scooley
ms.topic: article
ms.localizationpriority: medium
ms.date: 11/27/2019
audience: ITPro
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens 2
ms.openlocfilehash: a27eb1d5eb32a6654f60aac98090cba1aab529d3
ms.sourcegitcommit: d5b2080868d6b74169a1bab2c7bad37dfa5a8b5a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2021
ms.locfileid: "112924105"
---
# <a name="update-hololens-2"></a><span data-ttu-id="7425a-104">更新 HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="7425a-104">Update HoloLens 2</span></span>

<span data-ttu-id="7425a-105">HoloLens 使用 Windows 更新，就像其他 Windows 10 设备一样。</span><span class="sxs-lookup"><span data-stu-id="7425a-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="7425a-106">如果你的 HoloLens 处于待机状态并连接到 Internet，则它会自动下载并安装系统更新，即使它处于备用状态。</span><span class="sxs-lookup"><span data-stu-id="7425a-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="7425a-107">本文将指导你完成以下操作的 HoloLens 工具：</span><span class="sxs-lookup"><span data-stu-id="7425a-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="7425a-108">查看当前操作系统版本 (内部版本号) </span><span class="sxs-lookup"><span data-stu-id="7425a-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="7425a-109">检查更新</span><span class="sxs-lookup"><span data-stu-id="7425a-109">checking for updates</span></span>
- <span data-ttu-id="7425a-110">手动更新 HoloLens</span><span class="sxs-lookup"><span data-stu-id="7425a-110">manually updating HoloLens</span></span>
- <span data-ttu-id="7425a-111">回退到较旧的更新</span><span class="sxs-lookup"><span data-stu-id="7425a-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="7425a-112">检查操作系统版本 (生成号) </span><span class="sxs-lookup"><span data-stu-id="7425a-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="7425a-113">您可以通过打开 "设置" 应用程序并选择 "**系统** 关于" 来验证系统版本号 (生成号)  >  。</span><span class="sxs-lookup"><span data-stu-id="7425a-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="7425a-114">检查更新并手动更新</span><span class="sxs-lookup"><span data-stu-id="7425a-114">Check for updates and manually update</span></span>

<span data-ttu-id="7425a-115">你可以在 "设置" 中随时检查更新。</span><span class="sxs-lookup"><span data-stu-id="7425a-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="7425a-116">若要查看可用的更新并检查新的更新，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7425a-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="7425a-117">打开“设置”应用  。</span><span class="sxs-lookup"><span data-stu-id="7425a-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="7425a-118">导航到 "**更新 & 安全**  >  **Windows 更新**"。</span><span class="sxs-lookup"><span data-stu-id="7425a-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="7425a-119">选择“检查更新”。</span><span class="sxs-lookup"><span data-stu-id="7425a-119">Select **Check for updates**.</span></span>

<span data-ttu-id="7425a-120">如果更新可用，则会开始下载新版本。</span><span class="sxs-lookup"><span data-stu-id="7425a-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="7425a-121">下载完成后，选择 " **立即重新启动** " 按钮以触发安装。</span><span class="sxs-lookup"><span data-stu-id="7425a-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="7425a-122">如果设备低于40% 且未接通电源，则重新启动将不会开始安装更新。</span><span class="sxs-lookup"><span data-stu-id="7425a-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="7425a-123">在 HoloLens 安装更新时，它会显示旋转的齿轮和进度指示器。</span><span class="sxs-lookup"><span data-stu-id="7425a-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="7425a-124">请勿在此时间关闭 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="7425a-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="7425a-125">完成安装后，它将自动重新启动。</span><span class="sxs-lookup"><span data-stu-id="7425a-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="7425a-126">HoloLens 一次应用一个更新。</span><span class="sxs-lookup"><span data-stu-id="7425a-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="7425a-127">如果你的 HoloLens 超过了最新版本，则可能需要多次运行更新过程，以使其完全保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="7425a-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version"></a><span data-ttu-id="7425a-128">返回到以前的版本</span><span class="sxs-lookup"><span data-stu-id="7425a-128">Go back to a previous version</span></span>

<span data-ttu-id="7425a-129">在某些情况下，你可能想要返回到以前版本的 HoloLens 软件。</span><span class="sxs-lookup"><span data-stu-id="7425a-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="7425a-130">建议的步骤如下：</span><span class="sxs-lookup"><span data-stu-id="7425a-130">The recommended steps are:</span></span>

1. <span data-ttu-id="7425a-131">请联系支持人员以查看他们能否解决你的问题。</span><span class="sxs-lookup"><span data-stu-id="7425a-131">Contact Support to see if they can fix your issue.</span></span>
    1. <span data-ttu-id="7425a-132">确保启用了 **可选** 的或 **完整** 的遥测-这会使你的 bug 更具可操作性，并使工程师能够更轻松地进行诊断。</span><span class="sxs-lookup"><span data-stu-id="7425a-132">Ensure that **Optional** or **Full** telemetry is enabled -  this makes your bug more actionable and easier for engineers to diagnose.</span></span>
    1. <span data-ttu-id="7425a-133">[文件反馈](hololens-feedback.md) 尽可能地说明。</span><span class="sxs-lookup"><span data-stu-id="7425a-133">[File Feedback](hololens-feedback.md) being as descriptive as possible.</span></span> <span data-ttu-id="7425a-134">记下标题或使用共享功能，以便可以与支持人员共享 bug。</span><span class="sxs-lookup"><span data-stu-id="7425a-134">Take note of the title or use the share feature so you can share your bug with Support.</span></span>
    1. <span data-ttu-id="7425a-135">联系 [支持人员](https://aka.ms/hlsupport)。</span><span class="sxs-lookup"><span data-stu-id="7425a-135">Contact [Support](https://aka.ms/hlsupport).</span></span> <span data-ttu-id="7425a-136">如果你的问题是需要通过返回到以前的版本来解决的问题，则可以提供 FFU 来闪存设备。</span><span class="sxs-lookup"><span data-stu-id="7425a-136">If your issue is one that needs to be solved by returning to a previous version, they can supply you the FFU to flash your device.</span></span>

1. <span data-ttu-id="7425a-137">如果这不起作用，请 [使用高级恢复助理重置或刷新你的 HoloLens 2](hololens-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="7425a-137">If that does not work, then [reset or reflash your HoloLens 2 with the Advanced Recovery Companion](hololens-recovery.md).</span></span>
    1. <span data-ttu-id="7425a-138">在电脑上，从 Microsoft Store 下载 [高级恢复助理](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 。</span><span class="sxs-lookup"><span data-stu-id="7425a-138">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
    1. <span data-ttu-id="7425a-139">请确保没有任何手机或 Windows 设备连接到您的 PC。</span><span class="sxs-lookup"><span data-stu-id="7425a-139">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
    1. <span data-ttu-id="7425a-140">选择要刷新到的版本：</span><span class="sxs-lookup"><span data-stu-id="7425a-140">Choose which version you want to flash to:</span></span>
        1. <span data-ttu-id="7425a-141">您可以下载 [最新的 HoloLens 2 版本](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="7425a-141">You can download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
        1. <span data-ttu-id="7425a-142">可以使用 ARC 宿主的默认生成。</span><span class="sxs-lookup"><span data-stu-id="7425a-142">You can use the default build that ARC hosts.</span></span> <span data-ttu-id="7425a-143"> (如果选择此选项，则跳过下一步。 ) </span><span class="sxs-lookup"><span data-stu-id="7425a-143">(If you choose this option skip the next step.)</span></span>
        1. <span data-ttu-id="7425a-144">你可以使用提供的生成支持。</span><span class="sxs-lookup"><span data-stu-id="7425a-144">You can use a build Support provided you with.</span></span>
    1. <span data-ttu-id="7425a-145">完成这些下载后，打开 **文件资源管理器**  >  **下载**。</span><span class="sxs-lookup"><span data-stu-id="7425a-145">When you have finished these downloads, open **File Explorer** > **Downloads**.</span></span> <span data-ttu-id="7425a-146">右键单击刚下载的压缩文件夹，然后选择 "**提取所有**  >  **提取**" 将其解压缩。</span><span class="sxs-lookup"><span data-stu-id="7425a-146">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
    1. <span data-ttu-id="7425a-147">使用 USB-A 到 USB 电缆将你的 HoloLens 连接到你的电脑。</span><span class="sxs-lookup"><span data-stu-id="7425a-147">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="7425a-148">即使已使用其他电缆连接 HoloLens，也 (，这种方法的效果最佳。 ) </span><span class="sxs-lookup"><span data-stu-id="7425a-148">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
    1. <span data-ttu-id="7425a-149">高级恢复助理会自动检测到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="7425a-149">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="7425a-150">选择 " **Microsoft HoloLens** " 磁贴。</span><span class="sxs-lookup"><span data-stu-id="7425a-150">Select the **Microsoft HoloLens** tile.</span></span>
    1. <span data-ttu-id="7425a-151">在下一个屏幕上，选择 " **手动包选择** "，然后选择在步骤4中解压缩的文件夹中包含的安装文件。</span><span class="sxs-lookup"><span data-stu-id="7425a-151">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="7425a-152"> (查找扩展名为 ffu 的文件 ) </span><span class="sxs-lookup"><span data-stu-id="7425a-152">(Look for a file with the .ffu extension.)</span></span>
    1. <span data-ttu-id="7425a-153">选择 " **安装软件**"，然后按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="7425a-153">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="7425a-154">返回到早期版本会删除你的个人文件和设置。</span><span class="sxs-lookup"><span data-stu-id="7425a-154">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="7425a-155">此外，如果想要停留在当前安装的版本中，还可以手动 [暂停更新](hololens-updates.md#pause-updates-via-device)。</span><span class="sxs-lookup"><span data-stu-id="7425a-155">Additionally, if you would like to stay on your currently installed release, you can also manually [pause updates](hololens-updates.md#pause-updates-via-device).</span></span> <span data-ttu-id="7425a-156">这将使工程团队时间来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="7425a-156">This will give the Engineering Team time to fix the issue.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="7425a-157">HoloLens 上的 Windows 预览体验计划</span><span class="sxs-lookup"><span data-stu-id="7425a-157">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="7425a-158">想要查看 HoloLens 中的最新功能？</span><span class="sxs-lookup"><span data-stu-id="7425a-158">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="7425a-159">如果是这样，请加入 Windows 预览体验计划;你将在更新 HoloLens 软件更新的预览版本之前获得对它们的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7425a-159">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="7425a-160">[获取适用于 Microsoft HoloLens 的 Windows 预览体验预览](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="7425a-160">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
