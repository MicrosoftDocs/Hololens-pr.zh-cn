---
title: 在 HoloLens 上查找和保存文件
description: 使用 HoloLens 上的文件资源管理器查看和管理设备上的文件
keywords: hololens
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
ms.openlocfilehash: 50a13e1634344bea66bb6b7ce90d9e3fc8c2a783
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827656"
---
# <span data-ttu-id="0621c-104">在 HoloLens 上查找、打开和保存文件</span><span class="sxs-lookup"><span data-stu-id="0621c-104">Find, open, and save files on HoloLens</span></span>

<span data-ttu-id="0621c-105">在 HoloLens 上创建的文件（包括照片和视频）将直接保存到 HoloLens 设备。</span><span class="sxs-lookup"><span data-stu-id="0621c-105">Files you create on HoloLens, including photos and videos, are saved directly to your HoloLens device.</span></span> <span data-ttu-id="0621c-106">按照管理 Windows 10 上的文件的方式查看和管理它们：</span><span class="sxs-lookup"><span data-stu-id="0621c-106">View and manage them in the same way you would manage files on Windows 10:</span></span>

- <span data-ttu-id="0621c-107">使用文件资源管理器应用访问本地文件夹。</span><span class="sxs-lookup"><span data-stu-id="0621c-107">Using the File Explorer app to access local folders.</span></span>
- <span data-ttu-id="0621c-108">在应用的存储中。</span><span class="sxs-lookup"><span data-stu-id="0621c-108">Within an app's storage.</span></span>
- <span data-ttu-id="0621c-109">在特殊文件夹中（如视频或音乐库）。</span><span class="sxs-lookup"><span data-stu-id="0621c-109">In a special folder (such as the video or music library).</span></span>
- <span data-ttu-id="0621c-110">使用包含应用和文件选取器（如 OneDrive）的存储服务。</span><span class="sxs-lookup"><span data-stu-id="0621c-110">Using a storage service that includes an app and file picker (such as OneDrive).</span></span>
- <span data-ttu-id="0621c-111">使用 MTP （媒体传输协议）支持，通过使用 USB 电缆连接到 HoloLens 的桌面电脑。</span><span class="sxs-lookup"><span data-stu-id="0621c-111">Using a desktop PC connected to your HoloLens by using a USB cable, using MTP (Media Transfer Protocol) support.</span></span>

## <span data-ttu-id="0621c-112">使用文件资源管理器在 HoloLens 上查看文件</span><span class="sxs-lookup"><span data-stu-id="0621c-112">View files on HoloLens using File Explorer</span></span>

> <span data-ttu-id="0621c-113">适用于[hololens 的 Windows 10 四月 2018 Update （RS4）](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)的所有 hololens 2 设备和 HoloLens （第1代）。</span><span class="sxs-lookup"><span data-stu-id="0621c-113">Applies to all HoloLens 2 devices and HoloLens (1st gen) as of the [Windows 10 April 2018 Update (RS4) for HoloLens](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018).</span></span>

<span data-ttu-id="0621c-114">使用 HoloLens 上的文件资源管理器查看和管理设备上的文件，包括3D 对象、文档和图片。</span><span class="sxs-lookup"><span data-stu-id="0621c-114">Use File Explorer on HoloLens to view and manage files on your device, including 3D objects, documents, and pictures.</span></span> <span data-ttu-id="0621c-115">转到 "**开始**   >  **所有应用**"   >  **文件资源管理器**以开始使用。</span><span class="sxs-lookup"><span data-stu-id="0621c-115">Go to **Start**  > **All apps**  > **File Explorer** to get started.</span></span>

> [!TIP]
> <span data-ttu-id="0621c-116">如果文件资源管理器中未列出任何文件，请在顶部左窗格中选择 "**此设备**"。</span><span class="sxs-lookup"><span data-stu-id="0621c-116">If there are no files listed in File Explorer, select **This Device** in the top left pane.</span></span>

<span data-ttu-id="0621c-117">如果在文件资源管理器中看不到任何文件，则 "最近" 筛选器可能处于活动状态（时钟图标在左窗格中突出显示）。</span><span class="sxs-lookup"><span data-stu-id="0621c-117">If you don’t see any files in File Explorer, the "Recent" filter may be active (clock icon is highlighted in left pane).</span></span> <span data-ttu-id="0621c-118">若要解决此问题，请在左窗格（时钟图标下方）中选择 "**此设备**文档" 图标，或者打开菜单并选择 "**此设备**"。</span><span class="sxs-lookup"><span data-stu-id="0621c-118">To fix this, select the **This Device** document icon in the left pane (beneath the clock icon), or open the menu and select **This Device**.</span></span>

## <span data-ttu-id="0621c-119">查找和查看您的照片和视频</span><span class="sxs-lookup"><span data-stu-id="0621c-119">Find and view your photos and videos</span></span>

<span data-ttu-id="0621c-120">[混合现实捕获](holographic-photos-and-videos.md)允许你在 HoloLens 上拍摄混合现实照片和视频。</span><span class="sxs-lookup"><span data-stu-id="0621c-120">[Mixed reality capture](holographic-photos-and-videos.md) lets you take mixed reality photos and videos on HoloLens.</span></span>  <span data-ttu-id="0621c-121">这些照片和视频将保存到设备的 "相机" 滚动文件夹。</span><span class="sxs-lookup"><span data-stu-id="0621c-121">These photos and videos are saved to the device's Camera Roll folder.</span></span>

<span data-ttu-id="0621c-122">你可以通过以下方式访问使用 HoloLens 拍摄的照片和视频：</span><span class="sxs-lookup"><span data-stu-id="0621c-122">You can access photos and videos taken with HoloLens by:</span></span>

- <span data-ttu-id="0621c-123">直接通过 "[照片" 应用](holographic-photos-and-videos.md)访问相机的滚动。</span><span class="sxs-lookup"><span data-stu-id="0621c-123">accessing the Camera Roll directly through the [Photos app](holographic-photos-and-videos.md).</span></span>
- <span data-ttu-id="0621c-124">通过将照片和视频同步到 OneDrive，将照片和视频上载到云存储。</span><span class="sxs-lookup"><span data-stu-id="0621c-124">uploading photos and videos to cloud storage by syncing your photos and videos to OneDrive.</span></span>
- <span data-ttu-id="0621c-125">使用[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)的混合现实捕获页面。</span><span class="sxs-lookup"><span data-stu-id="0621c-125">using the Mixed Reality Capture page of the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture).</span></span>

### <span data-ttu-id="0621c-126">“照片”应用</span><span class="sxs-lookup"><span data-stu-id="0621c-126">Photos app</span></span>

<span data-ttu-id="0621c-127">"照片" 应用是 "**开始**" 菜单上的一个默认应用，并附带 HoloLens。</span><span class="sxs-lookup"><span data-stu-id="0621c-127">The Photos app is one of the default apps on the **Start** menu, and comes built-in with HoloLens.</span></span> <span data-ttu-id="0621c-128">了解有关[使用照片应用查看内容](holographic-photos-and-videos.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0621c-128">Learn more about [using the Photos app to view content](holographic-photos-and-videos.md).</span></span>

<span data-ttu-id="0621c-129">你还可以从 Microsoft Store 安装[OneDrive 应用](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)以将照片同步到其他设备。</span><span class="sxs-lookup"><span data-stu-id="0621c-129">You can also install the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store to sync photos to other devices.</span></span>

### <span data-ttu-id="0621c-130">OneDrive 应用</span><span class="sxs-lookup"><span data-stu-id="0621c-130">OneDrive app</span></span>

<span data-ttu-id="0621c-131">[OneDrive](https://onedrive.live.com/)允许你使用任何设备和任何用户访问、管理和共享你的照片和视频。</span><span class="sxs-lookup"><span data-stu-id="0621c-131">[OneDrive](https://onedrive.live.com/) lets you access, manage, and share your photos and videos with any device and with any user.</span></span> <span data-ttu-id="0621c-132">若要访问 HoloLens 上捕获的照片和视频，请从 HoloLens 上的 Microsoft Store 下载[OneDrive 应用](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)。</span><span class="sxs-lookup"><span data-stu-id="0621c-132">To access the photos and videos captured on HoloLens, download the [OneDrive app](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) from the Microsoft Store on your HoloLens.</span></span> <span data-ttu-id="0621c-133">下载后，打开 OneDrive 应用并选择 "**设置**  >  **相机上载**"，然后打开 "**相机上传**"。</span><span class="sxs-lookup"><span data-stu-id="0621c-133">Once downloaded, open the OneDrive app and select **Settings** > **Camera upload**, and turn on **Camera upload**.</span></span>

### <span data-ttu-id="0621c-134">连接到电脑</span><span class="sxs-lookup"><span data-stu-id="0621c-134">Connect to a PC</span></span>

<span data-ttu-id="0621c-135">如果你的 HoloLens 运行的是[windows 10 四月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)或更高版本，你可以使用 USB 电缆将 HoloLens 连接到 WINDOWS 10 电脑，方法是使用 MTP （媒体传输协议）浏览设备上的照片和视频。</span><span class="sxs-lookup"><span data-stu-id="0621c-135">If your HoloLens is running the [Windows 10 April 2018 update](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) or later, you can connect your HoloLens to a Windows 10 PC by using a USB cable to browse photos and videos on the device by using MTP (media transfer protocol).</span></span> <span data-ttu-id="0621c-136">如果你在设备上设置了 PIN 或密码，你将需要确保设备已解锁才能浏览文件。</span><span class="sxs-lookup"><span data-stu-id="0621c-136">You'll need to make sure the device is unlocked to browse files if you have a PIN or password set up on your device.</span></span>  

<span data-ttu-id="0621c-137">如果你已启用[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)，则可以使用它来浏览、检索和管理存储在你的设备上的照片和视频。</span><span class="sxs-lookup"><span data-stu-id="0621c-137">If you have enabled the [Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal), you can use it to browse, retrieve, and manage the photos and videos stored on your device.</span></span>

## <span data-ttu-id="0621c-138">访问应用内的文件</span><span class="sxs-lookup"><span data-stu-id="0621c-138">Access files within an app</span></span>

<span data-ttu-id="0621c-139">如果应用程序将文件保存在你的设备上，你可以使用该应用程序来访问它们。</span><span class="sxs-lookup"><span data-stu-id="0621c-139">If an application saves files on your device, you can use that application to access them.</span></span>

### <span data-ttu-id="0621c-140">从另一个应用请求文件</span><span class="sxs-lookup"><span data-stu-id="0621c-140">Requesting files from another app</span></span>

<span data-ttu-id="0621c-141">通过使用[文件选取](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)器，应用程序可以请求保存文件或从另一个应用打开文件。</span><span class="sxs-lookup"><span data-stu-id="0621c-141">An application can request to save a file or open a file from another app by using [file pickers](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers).</span></span>

### <span data-ttu-id="0621c-142">已知文件夹</span><span class="sxs-lookup"><span data-stu-id="0621c-142">Known folders</span></span>

<span data-ttu-id="0621c-143">HoloLens 支持应用可请求访问权限的许多[已知文件夹](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders)。</span><span class="sxs-lookup"><span data-stu-id="0621c-143">HoloLens supports a number of [known folders](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) that apps can request permission to access.</span></span>

## <span data-ttu-id="0621c-144">在电脑上查看 HoloLens 文件</span><span class="sxs-lookup"><span data-stu-id="0621c-144">View HoloLens files on your PC</span></span>

<span data-ttu-id="0621c-145">与其他移动设备类似，使用 MTP （媒体传输协议）将 HoloLens 连接到桌面电脑，并在电脑上打开文件资源管理器以轻松传输。</span><span class="sxs-lookup"><span data-stu-id="0621c-145">Similar to other mobile devices, connect HoloLens to your desktop PC using MTP (Media Transfer Protocol) and open File Explorer on the PC to access your HoloLens libraries for easy transfer.</span></span>

<span data-ttu-id="0621c-146">若要在电脑上的文件资源管理器中查看 HoloLens 文件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0621c-146">To see your HoloLens files in File Explorer on your PC:</span></span>

1. <span data-ttu-id="0621c-147">登录 HoloLens，然后使用 HoloLens 随附的 USB 电缆将其插入电脑。</span><span class="sxs-lookup"><span data-stu-id="0621c-147">Sign in to HoloLens, then plug it into the PC using the USB cable that came with the HoloLens.</span></span>

1. <span data-ttu-id="0621c-148">选择 "**打开设备" 以查看文件资源管理器**中的文件，或打开电脑上的文件资源管理器并导航到该设备。</span><span class="sxs-lookup"><span data-stu-id="0621c-148">Select **Open Device to view files with File Explorer**, or open File Explorer on the PC and navigate to the device.</span></span>

<span data-ttu-id="0621c-149">若要查看有关 HoloLens 的信息，请在电脑上的文件资源管理器中右键单击设备名称，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="0621c-149">To see info about your HoloLens, right-click the device name in File Explorer on your PC, then select **Properties**.</span></span>

> [!NOTE]
> <span data-ttu-id="0621c-150">HoloLens （第1代）不支持连接到外部硬盘驱动器或 SD 卡。</span><span class="sxs-lookup"><span data-stu-id="0621c-150">HoloLens (1st gen) does not support connecting to external hard drives or SD cards.</span></span>

## <span data-ttu-id="0621c-151">同步到云</span><span class="sxs-lookup"><span data-stu-id="0621c-151">Sync to the cloud</span></span>

<span data-ttu-id="0621c-152">若要将你的 HoloLens 中的照片和其他文件与云同步，请在 HoloLens 上安装并设置 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="0621c-152">To sync photos and other files from your HoloLens to the cloud, install and set up OneDrive on HoloLens.</span></span> <span data-ttu-id="0621c-153">若要获取 OneDrive，请在 HoloLens 上的 Microsoft Store 中搜索它。</span><span class="sxs-lookup"><span data-stu-id="0621c-153">To get OneDrive, search for it in the Microsoft Store on your HoloLens.</span></span>

<span data-ttu-id="0621c-154">HoloLens 不备份应用文件和数据，因此最好将重要资料保存到 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="0621c-154">HoloLens doesn't back up app files and data, so it's a good idea to save your important stuff to OneDrive.</span></span> <span data-ttu-id="0621c-155">这样，如果重置设备或卸载应用，则将备份你的信息。</span><span class="sxs-lookup"><span data-stu-id="0621c-155">That way, if you reset your device or uninstall an app, your info will be backed up.</span></span>