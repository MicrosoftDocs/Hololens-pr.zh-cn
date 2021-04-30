---
title: 更新 HoloLens
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
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: ef1721c60aca82d20e60636cbf4301de81c0177c
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308426"
---
# <a name="update-hololens"></a><span data-ttu-id="6423d-104">更新 HoloLens</span><span class="sxs-lookup"><span data-stu-id="6423d-104">Update HoloLens</span></span>

<span data-ttu-id="6423d-105">HoloLens 使用 Windows 更新，就像其他 Windows 10 设备一样。</span><span class="sxs-lookup"><span data-stu-id="6423d-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="6423d-106">如果你的 HoloLens 处于待机状态并连接到 Internet，则它会自动下载并安装系统更新，即使它处于备用状态。</span><span class="sxs-lookup"><span data-stu-id="6423d-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="6423d-107">本文将指导你完成以下操作的 HoloLens 工具：</span><span class="sxs-lookup"><span data-stu-id="6423d-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="6423d-108">查看当前操作系统版本 (内部版本号) </span><span class="sxs-lookup"><span data-stu-id="6423d-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="6423d-109">检查更新</span><span class="sxs-lookup"><span data-stu-id="6423d-109">checking for updates</span></span>
- <span data-ttu-id="6423d-110">手动更新 HoloLens</span><span class="sxs-lookup"><span data-stu-id="6423d-110">manually updating HoloLens</span></span>
- <span data-ttu-id="6423d-111">回退到较旧的更新</span><span class="sxs-lookup"><span data-stu-id="6423d-111">rolling back to an older update</span></span>

## <a name="check-your-operating-system-version-build-number"></a><span data-ttu-id="6423d-112">检查操作系统版本 (生成号) </span><span class="sxs-lookup"><span data-stu-id="6423d-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="6423d-113">您可以通过打开 "设置" 应用程序并选择 "**系统** 关于" 来验证系统版本号 (生成号)  >  。</span><span class="sxs-lookup"><span data-stu-id="6423d-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <a name="check-for-updates-and-manually-update"></a><span data-ttu-id="6423d-114">检查更新并手动更新</span><span class="sxs-lookup"><span data-stu-id="6423d-114">Check for updates and manually update</span></span>

<span data-ttu-id="6423d-115">你可以在 "设置" 中随时检查更新。</span><span class="sxs-lookup"><span data-stu-id="6423d-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="6423d-116">若要查看可用的更新并检查新的更新，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6423d-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="6423d-117">打开“设置”应用  。</span><span class="sxs-lookup"><span data-stu-id="6423d-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="6423d-118">导航到 "**更新 & 安全**  >  **Windows 更新**"。</span><span class="sxs-lookup"><span data-stu-id="6423d-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="6423d-119">选择“检查更新”。</span><span class="sxs-lookup"><span data-stu-id="6423d-119">Select **Check for updates**.</span></span>

<span data-ttu-id="6423d-120">如果更新可用，则会开始下载新版本。</span><span class="sxs-lookup"><span data-stu-id="6423d-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="6423d-121">下载完成后，选择 " **立即重新启动** " 按钮以触发安装。</span><span class="sxs-lookup"><span data-stu-id="6423d-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="6423d-122">如果设备低于40% 且未接通电源，则重新启动将不会开始安装更新。</span><span class="sxs-lookup"><span data-stu-id="6423d-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="6423d-123">在 HoloLens 安装更新时，它会显示旋转的齿轮和进度指示器。</span><span class="sxs-lookup"><span data-stu-id="6423d-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="6423d-124">请勿在此时间关闭 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6423d-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="6423d-125">完成安装后，它将自动重新启动。</span><span class="sxs-lookup"><span data-stu-id="6423d-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="6423d-126">HoloLens 一次应用一个更新。</span><span class="sxs-lookup"><span data-stu-id="6423d-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="6423d-127">如果你的 HoloLens 超过了最新版本，则可能需要多次运行更新过程，以使其完全保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="6423d-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <a name="go-back-to-a-previous-version---hololens-2"></a><span data-ttu-id="6423d-128">返回到以前的版本-HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="6423d-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="6423d-129">在某些情况下，你可能想要返回到以前版本的 HoloLens 软件。</span><span class="sxs-lookup"><span data-stu-id="6423d-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="6423d-130">为此，可以使用 "高级恢复助理" 将 HoloLens 重置为早期版本。</span><span class="sxs-lookup"><span data-stu-id="6423d-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="6423d-131">返回到早期版本会删除你的个人文件和设置。</span><span class="sxs-lookup"><span data-stu-id="6423d-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="6423d-132">若要返回到 HoloLens 2 的以前版本，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6423d-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="6423d-133">请确保没有任何手机或 Windows 设备连接到您的 PC。</span><span class="sxs-lookup"><span data-stu-id="6423d-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="6423d-134">在电脑上，从 Microsoft Store 下载 [高级恢复助理](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 。</span><span class="sxs-lookup"><span data-stu-id="6423d-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="6423d-135">下载 [最新的 HoloLens 2 版本](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="6423d-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="6423d-136">完成这些下载后，打开 **文件资源管理器**  >  **下载**。</span><span class="sxs-lookup"><span data-stu-id="6423d-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="6423d-137">右键单击刚下载的压缩文件夹，然后选择 "**提取所有**  >  **提取**" 将其解压缩。</span><span class="sxs-lookup"><span data-stu-id="6423d-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="6423d-138">使用 USB-A 到 USB 电缆将你的 HoloLens 连接到你的电脑。</span><span class="sxs-lookup"><span data-stu-id="6423d-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="6423d-139">即使已使用其他电缆连接 HoloLens，也 (，这种方法的效果最佳。 ) </span><span class="sxs-lookup"><span data-stu-id="6423d-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="6423d-140">高级恢复助理会自动检测到 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6423d-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="6423d-141">选择 " **Microsoft HoloLens** " 磁贴。</span><span class="sxs-lookup"><span data-stu-id="6423d-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="6423d-142">在下一个屏幕上，选择 " **手动包选择** "，然后选择在步骤4中解压缩的文件夹中包含的安装文件。</span><span class="sxs-lookup"><span data-stu-id="6423d-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="6423d-143"> (查找扩展名为 ffu 的文件 ) </span><span class="sxs-lookup"><span data-stu-id="6423d-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="6423d-144">选择 " **安装软件**"，然后按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="6423d-144">Select **Install software**, and follow the instructions.</span></span>

## <a name="go-back-to-a-previous-version---hololens-1st-gen"></a><span data-ttu-id="6423d-145">返回到以前的版本-HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="6423d-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="6423d-146">在某些情况下，你可能想要返回到以前版本的 HoloLens 软件。</span><span class="sxs-lookup"><span data-stu-id="6423d-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="6423d-147">为此，可以使用 Windows 设备恢复工具将 HoloLens 重置为早期版本。</span><span class="sxs-lookup"><span data-stu-id="6423d-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="6423d-148">返回到早期版本会删除你的个人文件和设置。</span><span class="sxs-lookup"><span data-stu-id="6423d-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="6423d-149">若要返回到以前版本的 HoloLens 1，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6423d-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="6423d-150">请确保没有任何手机或 Windows 设备连接到您的 PC。</span><span class="sxs-lookup"><span data-stu-id="6423d-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="6423d-151">在电脑上，下载 [Windows 设备恢复工具 (WDRT) ](https://support.microsoft.com/help/12379)。</span><span class="sxs-lookup"><span data-stu-id="6423d-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="6423d-152">下载 [HoloLens 周年更新恢复包](https://aka.ms/hololensrecovery)。</span><span class="sxs-lookup"><span data-stu-id="6423d-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="6423d-153">下载完成后，打开 **文件资源管理器**  >  **下载**。</span><span class="sxs-lookup"><span data-stu-id="6423d-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="6423d-154">右键单击刚下载的压缩文件夹，然后选择 "**提取所有**  >  **提取**" 将其解压缩。</span><span class="sxs-lookup"><span data-stu-id="6423d-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="6423d-155">使用随附的微 USB 电缆将您的 HoloLens 连接到您的 PC。</span><span class="sxs-lookup"><span data-stu-id="6423d-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="6423d-156">即使已使用其他电缆连接 HoloLens，也 (，这种方法的效果最佳。 ) </span><span class="sxs-lookup"><span data-stu-id="6423d-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="6423d-157">WDRT 将自动检测你的 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6423d-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="6423d-158">选择 " **Microsoft HoloLens** " 磁贴。</span><span class="sxs-lookup"><span data-stu-id="6423d-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="6423d-159">在下一个屏幕上，选择 " **手动包选择** "，然后选择在步骤4中解压缩的文件夹中包含的安装文件。</span><span class="sxs-lookup"><span data-stu-id="6423d-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="6423d-160"> (查找扩展名为 ffu 的文件 ) </span><span class="sxs-lookup"><span data-stu-id="6423d-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="6423d-161">选择 " **安装软件**"，然后按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="6423d-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="6423d-162">如果 WDRT 未检测到 HoloLens，请尝试重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="6423d-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="6423d-163">如果这不起作用，请选择 **"未检测到设备**"，选择 " **Microsoft HoloLens**"，然后按照说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="6423d-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <a name="windows-insider-program-on-hololens"></a><span data-ttu-id="6423d-164">HoloLens 上的 Windows 预览体验计划</span><span class="sxs-lookup"><span data-stu-id="6423d-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="6423d-165">想要查看 HoloLens 中的最新功能？</span><span class="sxs-lookup"><span data-stu-id="6423d-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="6423d-166">如果是这样，请加入 Windows 预览体验计划;你将在更新 HoloLens 软件更新的预览版本之前获得对它们的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6423d-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="6423d-167">[获取适用于 Microsoft HoloLens 的 Windows 预览体验预览](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="6423d-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
