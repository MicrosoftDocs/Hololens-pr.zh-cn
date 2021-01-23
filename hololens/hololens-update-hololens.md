---
title: 更新 HoloLens
description: 了解如何检查 HoloLens 内部版本编号、使用设备更新保持最新、加入预览体验计划以及回滚更新。
keywords: 操作说明， 更新， 回滚， HoloLens， 检查内部版本， 内部版本编号
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283933"
---
# <span data-ttu-id="aeae7-104">更新 HoloLens</span><span class="sxs-lookup"><span data-stu-id="aeae7-104">Update HoloLens</span></span>

<span data-ttu-id="aeae7-105">HoloLens 使用 Windows 更新，就像其他 Windows 10 设备一样。</span><span class="sxs-lookup"><span data-stu-id="aeae7-105">HoloLens uses Windows Update, just like other Windows 10 devices.</span></span> <span data-ttu-id="aeae7-106">HoloLens 会在系统更新插入电源并连接到 Internet 时自动下载和安装，即使它处于待机状态。</span><span class="sxs-lookup"><span data-stu-id="aeae7-106">Your HoloLens will automatically download and install system updates whenever it is plugged-in to power and connected to the Internet, even when it is in standby.</span></span>

<span data-ttu-id="aeae7-107">本文将介绍 HoloLens 工具，</span><span class="sxs-lookup"><span data-stu-id="aeae7-107">This article will walk through HoloLens tools for:</span></span>

- <span data-ttu-id="aeae7-108">查看当前操作系统版本 (版本号) </span><span class="sxs-lookup"><span data-stu-id="aeae7-108">viewing your current operating system version (build number)</span></span>
- <span data-ttu-id="aeae7-109">检查更新</span><span class="sxs-lookup"><span data-stu-id="aeae7-109">checking for updates</span></span>
- <span data-ttu-id="aeae7-110">手动更新 HoloLens</span><span class="sxs-lookup"><span data-stu-id="aeae7-110">manually updating HoloLens</span></span>
- <span data-ttu-id="aeae7-111">回滚到较旧的更新</span><span class="sxs-lookup"><span data-stu-id="aeae7-111">rolling back to an older update</span></span>

## <span data-ttu-id="aeae7-112">检查操作系统版本 (版本号) </span><span class="sxs-lookup"><span data-stu-id="aeae7-112">Check your operating system version (build number)</span></span>

<span data-ttu-id="aeae7-113">可以通过打开"设置" (并选择"系统关于") 验证系统版本号和内部\*\*\*\*  >  **版本号**。</span><span class="sxs-lookup"><span data-stu-id="aeae7-113">You can verify the system version number, (build number) by opening the Settings app and selecting **System** > **About**.</span></span>

## <span data-ttu-id="aeae7-114">检查更新并手动更新</span><span class="sxs-lookup"><span data-stu-id="aeae7-114">Check for updates and manually update</span></span>

<span data-ttu-id="aeae7-115">你可在设置中随时检查更新。</span><span class="sxs-lookup"><span data-stu-id="aeae7-115">You can check for updates any time in settings.</span></span>  <span data-ttu-id="aeae7-116">查看可用更新并检查新更新：</span><span class="sxs-lookup"><span data-stu-id="aeae7-116">To see available updates and check for new updates:</span></span>

1. <span data-ttu-id="aeae7-117">打开 **"设置"** 应用。</span><span class="sxs-lookup"><span data-stu-id="aeae7-117">Open the **Settings** app.</span></span>
1. <span data-ttu-id="aeae7-118">导航到 **"&**  >  **Windows 更新"。**</span><span class="sxs-lookup"><span data-stu-id="aeae7-118">Navigate to **Update & Security** > **Windows Update**.</span></span>
1. <span data-ttu-id="aeae7-119">选择 **"检查更新"。**</span><span class="sxs-lookup"><span data-stu-id="aeae7-119">Select **Check for updates**.</span></span>

<span data-ttu-id="aeae7-120">如果更新可用，它将开始下载新版本。</span><span class="sxs-lookup"><span data-stu-id="aeae7-120">If an update is available, it will start downloading the new version.</span></span> <span data-ttu-id="aeae7-121">下载完成后，选择" **立即重启** "按钮以触发安装。</span><span class="sxs-lookup"><span data-stu-id="aeae7-121">After the download is complete, select the **Restart Now** button to trigger the installation.</span></span> <span data-ttu-id="aeae7-122">如果你的设备低于 40%且未插入，重启将不会开始安装更新。</span><span class="sxs-lookup"><span data-stu-id="aeae7-122">If your device is below 40% and not plugged in, restarting will not start installing the update.</span></span>

<span data-ttu-id="aeae7-123">当你的 HoloLens 安装更新时，它将显示旋转齿轮和进度指示器。</span><span class="sxs-lookup"><span data-stu-id="aeae7-123">While your HoloLens is installing the update, it will display spinning gears and a progress indicator.</span></span> <span data-ttu-id="aeae7-124">在此期间不要关闭 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="aeae7-124">Do not turn off your HoloLens during this time.</span></span> <span data-ttu-id="aeae7-125">安装完成后，它将自动重新启动。</span><span class="sxs-lookup"><span data-stu-id="aeae7-125">It will restart automatically once it has completed the installation.</span></span>

<span data-ttu-id="aeae7-126">HoloLens 一次应用一个更新。</span><span class="sxs-lookup"><span data-stu-id="aeae7-126">HoloLens applies one update at a time.</span></span>  <span data-ttu-id="aeae7-127">如果你的 HoloLens 支持多个版本的最新版本，你可能需要多次运行更新过程，才能完全更新。</span><span class="sxs-lookup"><span data-stu-id="aeae7-127">If your HoloLens is more than one version behind the latest you may need to run through the update process multiple times to get it fully up to date.</span></span>

## <span data-ttu-id="aeae7-128">返回到以前的版本 - HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="aeae7-128">Go back to a previous version - HoloLens 2</span></span>

<span data-ttu-id="aeae7-129">在某些情况下，你可能想要返回到 HoloLens 软件的早期版本。</span><span class="sxs-lookup"><span data-stu-id="aeae7-129">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="aeae7-130">为此，可以使用高级恢复助手将 HoloLens 重置为早期版本。</span><span class="sxs-lookup"><span data-stu-id="aeae7-130">You can do this by using the Advanced Recovery Companion to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="aeae7-131">返回到早期版本会删除你的个人文件和设置。</span><span class="sxs-lookup"><span data-stu-id="aeae7-131">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="aeae7-132">若要返回到 HoloLens 2 的早期版本，请按照如下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="aeae7-132">To go back to a previous version of HoloLens 2, follow these steps:</span></span>

1. <span data-ttu-id="aeae7-133">确保你未将任何电话或 Windows 设备插入电脑。</span><span class="sxs-lookup"><span data-stu-id="aeae7-133">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="aeae7-134">在电脑上，从 Microsoft [Store](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) 下载高级恢复助手。</span><span class="sxs-lookup"><span data-stu-id="aeae7-134">On your PC, download the [Advanced Recovery Companion](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?activetab=pivot:overviewtab) from the Microsoft Store.</span></span>
1. <span data-ttu-id="aeae7-135">下载[最新版本的 HoloLens 2](https://aka.ms/hololens2download)。</span><span class="sxs-lookup"><span data-stu-id="aeae7-135">Download the [most recent HoloLens 2 release](https://aka.ms/hololens2download).</span></span>
1. <span data-ttu-id="aeae7-136">完成这些下载后，打开"**文件资源管理器**  >  **下载"。**</span><span class="sxs-lookup"><span data-stu-id="aeae7-136">When you have finished these downloads, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="aeae7-137">右键单击刚刚下载的压缩文件夹，然后选择**全部提取** > **提取**将其解压缩。</span><span class="sxs-lookup"><span data-stu-id="aeae7-137">Right-click the zipped folder that you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="aeae7-138">使用 USB-A 到 USB-C 电缆将 HoloLens 连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="aeae7-138">Connect your HoloLens to your PC using a USB-A to USB-C cable.</span></span> <span data-ttu-id="aeae7-139">（即使你在连接 HoloLens 时一直使用的是其他电缆，但此电缆的使用效果更好。）</span><span class="sxs-lookup"><span data-stu-id="aeae7-139">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="aeae7-140">高级恢复助手自动检测 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="aeae7-140">The Advanced Recovery Companion automatically detects your HoloLens.</span></span> <span data-ttu-id="aeae7-141">选择“**Microsoft HoloLens**”磁贴。</span><span class="sxs-lookup"><span data-stu-id="aeae7-141">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="aeae7-142">下一个屏幕上，选择"手动 **程序包** 选择"，然后选择步骤 4 中解压缩的文件夹中包含的安装文件。</span><span class="sxs-lookup"><span data-stu-id="aeae7-142">On the next screen, select **Manual package selection** and then select the installation file contained in the folder that you unzipped in step 4.</span></span> <span data-ttu-id="aeae7-143"> (查找扩展名 .ffu.) </span><span class="sxs-lookup"><span data-stu-id="aeae7-143">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="aeae7-144">选择 **"安装软件**"，然后按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="aeae7-144">Select **Install software**, and follow the instructions.</span></span>

## <span data-ttu-id="aeae7-145">返回到以前版本 - HoloLens (第一代) </span><span class="sxs-lookup"><span data-stu-id="aeae7-145">Go back to a previous version - HoloLens (1st Gen)</span></span>

<span data-ttu-id="aeae7-146">在某些情况下，你可能想要返回到 HoloLens 软件的早期版本。</span><span class="sxs-lookup"><span data-stu-id="aeae7-146">In some cases, you might want to go back to a previous version of the HoloLens software.</span></span> <span data-ttu-id="aeae7-147">为此，可以使用 Windows 设备恢复工具将 HoloLens 重置为早期版本。</span><span class="sxs-lookup"><span data-stu-id="aeae7-147">You can do this by using the Windows Device Recovery Tool to reset your HoloLens to the earlier version.</span></span>

> [!NOTE]
> <span data-ttu-id="aeae7-148">返回到早期版本会删除你的个人文件和设置。</span><span class="sxs-lookup"><span data-stu-id="aeae7-148">Going back to an earlier version deletes your personal files and settings.</span></span>

<span data-ttu-id="aeae7-149">若要返回到以前版本的 HoloLens 1，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="aeae7-149">To go back to a previous version of HoloLens 1, follow these steps:</span></span>

1. <span data-ttu-id="aeae7-150">确保你未将任何电话或 Windows 设备插入电脑。</span><span class="sxs-lookup"><span data-stu-id="aeae7-150">Make sure that you don't have any phones or Windows devices plugged in to your PC.</span></span>
1. <span data-ttu-id="aeae7-151">在电脑上，将[Windows 设备恢复工具 (WDRT) 。 ](https://support.microsoft.com/help/12379)</span><span class="sxs-lookup"><span data-stu-id="aeae7-151">On your PC, download the [Windows Device Recovery Tool (WDRT)](https://support.microsoft.com/help/12379).</span></span>
1. <span data-ttu-id="aeae7-152">下载 [HoloLens 周年更新恢复包](https://aka.ms/hololensrecovery)。</span><span class="sxs-lookup"><span data-stu-id="aeae7-152">Download the [HoloLens Anniversary Update recovery package](https://aka.ms/hololensrecovery).</span></span>
1. <span data-ttu-id="aeae7-153">下载完成后，打开"**文件资源管理器**  >  **下载"。**</span><span class="sxs-lookup"><span data-stu-id="aeae7-153">When the downloads finish, open **File explorer** > **Downloads**.</span></span> <span data-ttu-id="aeae7-154">右键单击刚下载的压缩文件夹，然后选择"提取**所有**提取"  >  \*\*\*\* 将其解压缩。</span><span class="sxs-lookup"><span data-stu-id="aeae7-154">Right-click the zipped folder you just downloaded, and select **Extract all** > **Extract** to unzip it.</span></span>
1. <span data-ttu-id="aeae7-155">使用它所随的微型 USB 电缆将 HoloLens 连接到电脑。</span><span class="sxs-lookup"><span data-stu-id="aeae7-155">Connect your HoloLens to your PC using the micro-USB cable that it came with.</span></span> <span data-ttu-id="aeae7-156">（即使你在连接 HoloLens 时一直使用的是其他电缆，但此电缆的使用效果更好。）</span><span class="sxs-lookup"><span data-stu-id="aeae7-156">(Even if you've been using other cables to connect your HoloLens, this one works best.)</span></span>
1. <span data-ttu-id="aeae7-157">WDRT 将自动检测 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="aeae7-157">The WDRT will automatically detect your HoloLens.</span></span> <span data-ttu-id="aeae7-158">选择“**Microsoft HoloLens**”磁贴。</span><span class="sxs-lookup"><span data-stu-id="aeae7-158">Select the **Microsoft HoloLens** tile.</span></span>
1. <span data-ttu-id="aeae7-159">下一个屏幕上，选择"手动 **程序包** 选择"，然后选择步骤 4 中解压缩的文件夹中包含的安装文件。</span><span class="sxs-lookup"><span data-stu-id="aeae7-159">On the next screen, select **Manual package selection** and choose the installation file contained in the folder you unzipped in step 4.</span></span> <span data-ttu-id="aeae7-160"> (查找扩展名 .ffu.) </span><span class="sxs-lookup"><span data-stu-id="aeae7-160">(Look for a file with the .ffu extension.)</span></span>
1. <span data-ttu-id="aeae7-161">选择 **"安装软件**"，然后按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="aeae7-161">Select **Install software**, and follow the instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="aeae7-162">如果 WDRT 未检测到 HoloLens，请尝试重启电脑。</span><span class="sxs-lookup"><span data-stu-id="aeae7-162">If the WDRT doesn't detect your HoloLens, try restarting your PC.</span></span> <span data-ttu-id="aeae7-163">如果重启不起作用，请选择“**未检测到我的设备**”，选择“**Microsoft HoloLens**”，然后按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="aeae7-163">If that doesn't work, select **My device was not detected**, select **Microsoft HoloLens**, and then follow the instructions.</span></span>

## <span data-ttu-id="aeae7-164">HoloLens 上的 Windows 预览体验计划</span><span class="sxs-lookup"><span data-stu-id="aeae7-164">Windows Insider Program on HoloLens</span></span>

<span data-ttu-id="aeae7-165">想要查看 HoloLens 中的最新功能吗？</span><span class="sxs-lookup"><span data-stu-id="aeae7-165">Want to see the latest features in HoloLens?</span></span>  <span data-ttu-id="aeae7-166">如果是这样，请加入 Windows 预览体验计划;在向普通公众提供 HoloLens 软件更新之前，你将有权访问预览版 HoloLens 软件更新。</span><span class="sxs-lookup"><span data-stu-id="aeae7-166">If so, join the Windows Insider Program; you'll get access to preview builds of HoloLens software updates before they're available to the general public.</span></span>

<span data-ttu-id="aeae7-167">[获取 Microsoft HoloLens 的 Windows 预览体验成员预览版](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="aeae7-167">[Get Windows Insider preview for Microsoft HoloLens](hololens-insider.md).</span></span>
