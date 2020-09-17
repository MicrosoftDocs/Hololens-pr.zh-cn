---
title: Windows Defender 应用程序控制-WDAC
description: 概述什么是 WDAC 以及如何使用来管理 HoloLens 设备。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 09/16/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: d1147b202d3b575fa1f2dd20f620005c786ea9fc
ms.sourcegitcommit: 785ac6f05aecffc0f3980960891617d161711a70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016760"
---
# <span data-ttu-id="d563e-103">Windows Defender 应用程序控制-WDAC</span><span class="sxs-lookup"><span data-stu-id="d563e-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="d563e-104">WDAC 允许 IT 管理员配置其设备，阻止在设备上启动应用。</span><span class="sxs-lookup"><span data-stu-id="d563e-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="d563e-105">这与设备限制的方法（如 Kiosk 模式）不同，其中显示了用户将隐藏设备上的应用但仍可启动的 UI。</span><span class="sxs-lookup"><span data-stu-id="d563e-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="d563e-106">在实现 WDAC 时，应用仍在 "所有应用" 列表中可见，但 WDAC 将阻止设备用户启动这些应用和进程。</span><span class="sxs-lookup"><span data-stu-id="d563e-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

> [!NOTE]
> <span data-ttu-id="d563e-107">当最终用户尝试启动由 WDAC 阻止的应用时，在 HoloLens 上，他们将不会收到有关无法启动该应用的通知。</span><span class="sxs-lookup"><span data-stu-id="d563e-107">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="d563e-108">以下是用户了解如何 [使用 WDAC 和 Windows PowerShell 在 HoloLens 2 设备上使用 Microsoft Intune 允许或阻止应用](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)的指南。</span><span class="sxs-lookup"><span data-stu-id="d563e-108">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="d563e-109">当用户使用第一个示例步骤搜索在其 Windows 10 电脑上安装的应用时，可能需要先尝试缩小结果范围。</span><span class="sxs-lookup"><span data-stu-id="d563e-109">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="d563e-110">如果不知道程序包的完整名称，可能需要多次运行 "Add-appxpackage-name \ \* YourBestGuess \ \*" 才能找到它。</span><span class="sxs-lookup"><span data-stu-id="d563e-110">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="d563e-111">然后，一旦名称运行 "$package 1 = Add-appxpackage-name PackageName"</span><span class="sxs-lookup"><span data-stu-id="d563e-111">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="d563e-112">例如，运行以下 for Edge 将返回多个结果，但从该列表中，你可以确定所需的完整名称是 MicrosoftEdge。</span><span class="sxs-lookup"><span data-stu-id="d563e-112">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="d563e-113">用于 HoloLens 应用的程序包系列名称</span><span class="sxs-lookup"><span data-stu-id="d563e-113">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="d563e-114">在上面链接的指南中，你可以手动编辑 newPolicy.xml，并为仅在 HoloLens 上安装的应用程序添加程序包系列名称。</span><span class="sxs-lookup"><span data-stu-id="d563e-114">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="d563e-115">有时，你可能使用的应用不在桌面电脑上，而你希望添加到策略。</span><span class="sxs-lookup"><span data-stu-id="d563e-115">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="d563e-116">下面是用于 HoloLens 2 设备的常用应用和内置应用的列表。</span><span class="sxs-lookup"><span data-stu-id="d563e-116">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="d563e-117">应用名称</span><span class="sxs-lookup"><span data-stu-id="d563e-117">App Name</span></span>                   | <span data-ttu-id="d563e-118">程序包系列名称</span><span class="sxs-lookup"><span data-stu-id="d563e-118">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="d563e-119">3D 查看器</span><span class="sxs-lookup"><span data-stu-id="d563e-119">3D Viewer</span></span>                  | <span data-ttu-id="d563e-120">Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="d563e-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="d563e-121">日历</span><span class="sxs-lookup"><span data-stu-id="d563e-121">Calendar</span></span>                   | <span data-ttu-id="d563e-122">windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="d563e-122">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="d563e-123">相机</span><span class="sxs-lookup"><span data-stu-id="d563e-123">Camera</span></span>                     | <span data-ttu-id="d563e-124">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="d563e-124">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="d563e-125">Cortana</span><span class="sxs-lookup"><span data-stu-id="d563e-125">Cortana</span></span>                    | <span data-ttu-id="d563e-126">549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="d563e-126">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="d563e-127">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="d563e-127">Dynamics 365 Guides</span></span>        | <span data-ttu-id="d563e-128">Dynamics365 Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="d563e-128">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="d563e-129">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="d563e-129">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="d563e-130">MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="d563e-130">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="d563e-131">反馈中心</span><span class="sxs-lookup"><span data-stu-id="d563e-131">Feedback Hub</span></span>               | <span data-ttu-id="d563e-132">WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="d563e-132">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="d563e-133">文件资源管理器</span><span class="sxs-lookup"><span data-stu-id="d563e-133">File Explorer</span></span>              | <span data-ttu-id="d563e-134">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="d563e-134">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="d563e-135">Mail</span><span class="sxs-lookup"><span data-stu-id="d563e-135">Mail</span></span>                       | <span data-ttu-id="d563e-136">windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="d563e-136">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="d563e-137">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="d563e-137">Microsoft Store</span></span>            | <span data-ttu-id="d563e-138">WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="d563e-138">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="d563e-139">电影和电视</span><span class="sxs-lookup"><span data-stu-id="d563e-139">Movies & TV</span></span>                | <span data-ttu-id="d563e-140">ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="d563e-140">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="d563e-141">OneDrive</span><span class="sxs-lookup"><span data-stu-id="d563e-141">OneDrive</span></span>                   | <span data-ttu-id="d563e-142">microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="d563e-142">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="d563e-143">照片</span><span class="sxs-lookup"><span data-stu-id="d563e-143">Photos</span></span>                     | <span data-ttu-id="d563e-144">Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="d563e-144">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="d563e-145">“设置”</span><span class="sxs-lookup"><span data-stu-id="d563e-145">Settings</span></span>                   | <span data-ttu-id="d563e-146">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="d563e-146">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="d563e-147">提示</span><span class="sxs-lookup"><span data-stu-id="d563e-147">Tips</span></span>                       | <span data-ttu-id="d563e-148">HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="d563e-148">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

<span data-ttu-id="d563e-149">如果应用不在此列表中，则用户可以使用 Device Portal 连接到安装了希望阻止的应用的 HoloLens 2，以确定 PackageRelativeID 以及从那里获取 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="d563e-149">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="d563e-150">在 HoloLens 2 设备上安装该应用。</span><span class="sxs-lookup"><span data-stu-id="d563e-150">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="d563e-151">打开设置 >-为开发人员 & 便捷性 > 更新，并启用 **开发人员模式** 和 **Device portal**。</span><span class="sxs-lookup"><span data-stu-id="d563e-151">Open Settings -> Updates & Securtiy -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="d563e-152">有关详细信息的详细说明 [，请参阅在此处设置和使用 device portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="d563e-152">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="d563e-153">连接设备门户后，导航到 " **视图** "，然后导航到 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="d563e-153">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="d563e-154">在 "已安装的应用" 面板中，使用下拉列表选择已安装的应用。</span><span class="sxs-lookup"><span data-stu-id="d563e-154">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="d563e-155">找到 PackageRelativeID。</span><span class="sxs-lookup"><span data-stu-id="d563e-155">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="d563e-156">在！之前复制应用字符，这将是你的 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="d563e-156">Copy app characters before the !, this will be your PackageFamilyName.</span></span>

