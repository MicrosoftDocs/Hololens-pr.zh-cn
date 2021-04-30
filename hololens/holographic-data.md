---
title: 在 HoloLens 上查找并保存文件
description: 了解如何在 HoloLens 上使用文件资源管理器打开、查看和管理混合现实设备上的文件。
keywords: 操作说明，文件选取器，文件，照片，视频，图片，OneDrive，存储，文件资源管理器，hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308185"
---
# <a name="find-open-and-save-files-on-hololens"></a><span data-ttu-id="6f944-104">在 HoloLens 上查找、打开和保存文件</span><span class="sxs-lookup"><span data-stu-id="6f944-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="6f944-105">在 HoloLens 上创建的文件（包括照片和视频）将直接保存到 HoloLens 设备上。</span><span class="sxs-lookup"><span data-stu-id="6f944-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="6f944-106">以在 Windows 10 上管理文件的相同方式查看和管理它们：</span><span class="sxs-lookup"><span data-stu-id="6f944-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="6f944-107">使用文件资源管理器应用程序访问本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="6f944-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="6f944-108">在应用的存储中。</span><span class="sxs-lookup"><span data-stu-id="6f944-108">Within an app's storage.</span></span>
- <span data-ttu-id="6f944-109">在特殊文件夹中 (如 "视频" 或 "音乐库") 。</span><span class="sxs-lookup"><span data-stu-id="6f944-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="6f944-110">使用包含应用程序和文件选取器 (如 OneDrive) 的存储服务。</span><span class="sxs-lookup"><span data-stu-id="6f944-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="6f944-111">使用 USB 电缆连接到 HoloLens 的台式 PC，使用 MTP (媒体传输协议) 支持。</span><span class="sxs-lookup"><span data-stu-id="6f944-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <a name="view-files-on-hololens-using-file-explorer"></a><span data-ttu-id="6f944-112">使用文件资源管理器在 HoloLens 上查看文件</span><span class="sxs-lookup"><span data-stu-id="6f944-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="6f944-113">适用于所有 HoloLens 2 设备和 HoloLens (第一代) ，从 [Windows 10 2018 年4月版更新 (RS4) ](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)。</span><span class="sxs-lookup"><span data-stu-id="6f944-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="6f944-114">使用 HoloLens 上的文件资源管理器来查看和管理设备上的文件，包括3D 对象、文档和图片。</span><span class="sxs-lookup"><span data-stu-id="6f944-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="6f944-115">转到 "**启动**   >  **所有应用**   >  **文件资源管理器**" 开始。</span><span class="sxs-lookup"><span data-stu-id="6f944-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="6f944-116">如果文件资源管理器中没有列出任何文件，请在左上方窗格中选择 **此设备** 。</span><span class="sxs-lookup"><span data-stu-id="6f944-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="6f944-117">如果在文件资源管理器中看不到任何文件，则 "最近的" 筛选器可能处于活动状态 (时钟图标在左窗格中突出显示) "。</span><span class="sxs-lookup"><span data-stu-id="6f944-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="6f944-118">若要解决此问题，请在左窗格中选择 " **此设备** 文档" 图标 (时钟图标) 下，或打开菜单并选择 " **此设备**"。</span><span class="sxs-lookup"><span data-stu-id="6f944-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <a name="find-and-view-your-photos-and-videos"></a><span data-ttu-id="6f944-119">查找并查看你的照片和视频</span><span class="sxs-lookup"><span data-stu-id="6f944-119">Find and view your photos and videos</span></span>

<span data-ttu-id="6f944-120">[混合现实捕获](holographic-photos-and-videos.md) 允许在 HoloLens 上利用混合现实照片和视频。</span><span class="sxs-lookup"><span data-stu-id="6f944-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="6f944-121">这些照片和视频将保存到设备的 "相机" 滚动文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6f944-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="6f944-122">可以通过以下方式访问使用 HoloLens 拍摄的照片和视频：</span><span class="sxs-lookup"><span data-stu-id="6f944-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="6f944-123">直接访问相机 [应用程序](holographic-photos-and-videos.md)的照相机。</span><span class="sxs-lookup"><span data-stu-id="6f944-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="6f944-124">通过将照片和视频同步到 OneDrive，将照片和视频上传到云存储。</span><span class="sxs-lookup"><span data-stu-id="6f944-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="6f944-125">使用 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)的混合现实捕获页。</span><span class="sxs-lookup"><span data-stu-id="6f944-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <a name="photos-app"></a><span data-ttu-id="6f944-126">“照片”应用</span><span class="sxs-lookup"><span data-stu-id="6f944-126">Photos app</span></span>

<span data-ttu-id="6f944-127">照片应用是 " **开始** " 菜单上的默认应用之一，并内置于 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="6f944-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="6f944-128">了解有关 [使用照片应用查看内容的](holographic-photos-and-videos.md)详细信息。</span><span class="sxs-lookup"><span data-stu-id="6f944-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="6f944-129">你还可以从 Microsoft Store 安装 [OneDrive 应用](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) ，将照片同步到其他设备。</span><span class="sxs-lookup"><span data-stu-id="6f944-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <a name="onedrive-app"></a><span data-ttu-id="6f944-130">OneDrive 应用</span><span class="sxs-lookup"><span data-stu-id="6f944-130">OneDrive app</span></span>

<span data-ttu-id="6f944-131">[OneDrive](https://onedrive.live.com/) 允许你使用任何设备和任何用户访问、管理和共享你的照片和视频。</span><span class="sxs-lookup"><span data-stu-id="6f944-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="6f944-132">若要访问在 HoloLens 上捕获的照片和视频，请从你的 HoloLens Microsoft Store 下载 [OneDrive 应用](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 。</span><span class="sxs-lookup"><span data-stu-id="6f944-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="6f944-133">下载完成后，打开 OneDrive 应用并选择 "**设置**  >  " "**相机上传**"，并打开 "**相机上传**"。</span><span class="sxs-lookup"><span data-stu-id="6f944-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <a name="connect-to-a-pc"></a><span data-ttu-id="6f944-134">连接到电脑</span><span class="sxs-lookup"><span data-stu-id="6f944-134">Connect to a PC</span></span>

<span data-ttu-id="6f944-135">如果你的 HoloLens 正在运行 [windows 10 四月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 或更高版本，则可以使用 USB 电缆将你的 hololens 连接到 WINDOWS 10 电脑，使用 MTP (媒体传输协议) 来浏览设备上的照片和视频。</span><span class="sxs-lookup"><span data-stu-id="6f944-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="6f944-136">如果已在设备上设置 PIN 或密码，则需要确保设备处于解锁状态才能浏览文件。</span><span class="sxs-lookup"><span data-stu-id="6f944-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="6f944-137">如果已启用 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)，则可以使用它来浏览、检索和管理存储在设备上的照片和视频。</span><span class="sxs-lookup"><span data-stu-id="6f944-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <a name="access-files-within-an-app"></a><span data-ttu-id="6f944-138">访问应用中的文件</span><span class="sxs-lookup"><span data-stu-id="6f944-138">Access files within an app</span></span>

<span data-ttu-id="6f944-139">如果应用程序将文件保存在你的设备上，则可以使用该应用程序进行访问。</span><span class="sxs-lookup"><span data-stu-id="6f944-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <a name="requesting-files-from-another-app"></a><span data-ttu-id="6f944-140">从其他应用程序请求文件</span><span class="sxs-lookup"><span data-stu-id="6f944-140">Requesting files from another app</span></span>

<span data-ttu-id="6f944-141">应用程序可以请求使用 [文件选取](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)器来保存文件或从另一个应用打开文件。</span><span class="sxs-lookup"><span data-stu-id="6f944-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <a name="known-folders"></a><span data-ttu-id="6f944-142">已知文件夹</span><span class="sxs-lookup"><span data-stu-id="6f944-142">Known folders</span></span>

<span data-ttu-id="6f944-143">HoloLens 支持多个 [已知文件夹](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) ，应用程序可以请求访问权限。</span><span class="sxs-lookup"><span data-stu-id="6f944-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <a name="view-hololens-files-on-your-pc"></a><span data-ttu-id="6f944-144">查看 PC 上的 HoloLens 文件</span><span class="sxs-lookup"><span data-stu-id="6f944-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="6f944-145">类似于其他移动设备，使用 MTP 将 HoloLens 连接到桌面 PC (媒体传输协议) 并打开电脑上的文件资源管理器，以便轻松地进行传输。</span><span class="sxs-lookup"><span data-stu-id="6f944-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="6f944-146">若要在计算机上的文件资源管理器中查看 HoloLens 文件：</span><span class="sxs-lookup"><span data-stu-id="6f944-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="6f944-147">登录到 HoloLens，并使用 HoloLens 附带的 USB 电缆将其插入 PC。</span><span class="sxs-lookup"><span data-stu-id="6f944-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="6f944-148">选择 " **打开设备" 以通过文件资源管理器查看文件**，或打开电脑上的文件资源管理器并导航到该设备。</span><span class="sxs-lookup"><span data-stu-id="6f944-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="6f944-149">若要查看有关 HoloLens 的信息，请在计算机上的文件资源管理器中右键单击设备名称，然后选择 " **属性**"。</span><span class="sxs-lookup"><span data-stu-id="6f944-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="6f944-150">HoloLens (第一代) 不支持连接到外部硬盘驱动器或 SD 卡。</span><span class="sxs-lookup"><span data-stu-id="6f944-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <a name="sync-to-the-cloud"></a><span data-ttu-id="6f944-151">同步到云</span><span class="sxs-lookup"><span data-stu-id="6f944-151">Sync to the cloud</span></span>

<span data-ttu-id="6f944-152">若要将照片和其他文件从 HoloLens 同步到云，请在 HoloLens 上安装和设置 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="6f944-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="6f944-153">若要获取 OneDrive，请在你的 HoloLens Microsoft Store 中搜索它。</span><span class="sxs-lookup"><span data-stu-id="6f944-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="6f944-154">HoloLens 不会备份应用文件和数据，因此最好将重要内容保存到 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="6f944-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="6f944-155">这样一来，如果重置设备或卸载应用，则会备份信息。</span><span class="sxs-lookup"><span data-stu-id="6f944-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>
