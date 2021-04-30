---
title: Windows Defender 应用程序控制-WDAC
description: 概述什么是 Windows Defender 应用程序控制，以及如何使用它来管理 HoloLens 混合现实设备。
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/26/2020
ms.reviewer: ''
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 23c9a274387424e8f084a4729ee621e130820716
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308399"
---
# <a name="windows-defender-application-control---wdac"></a><span data-ttu-id="25e0e-103">Windows Defender 应用程序控制-WDAC</span><span class="sxs-lookup"><span data-stu-id="25e0e-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="25e0e-104">WDAC 允许 IT 管理员配置其设备，以阻止在设备上启动应用。</span><span class="sxs-lookup"><span data-stu-id="25e0e-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="25e0e-105">这不同于设备限制方法，例如展台模式，其中向用户提供了一个用户界面，用于隐藏设备上的应用，但仍可以启动这些应用。</span><span class="sxs-lookup"><span data-stu-id="25e0e-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="25e0e-106">实现 WDAC 后，应用仍会显示在 "所有应用" 列表中，但 WDAC 会阻止设备用户启动这些应用和进程。</span><span class="sxs-lookup"><span data-stu-id="25e0e-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="25e0e-107">可以为设备分配多个 WDAC 策略。</span><span class="sxs-lookup"><span data-stu-id="25e0e-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="25e0e-108">如果在系统上设置了多个 WDAC 策略，则最严格的策略会生效。</span><span class="sxs-lookup"><span data-stu-id="25e0e-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="25e0e-109">当最终用户尝试启动由 WDAC 阻止的应用时，在 HoloLens 上，它们将不会收到关于无法启动该应用的通知。</span><span class="sxs-lookup"><span data-stu-id="25e0e-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="25e0e-110">下面是一个指导，让用户了解如何 [使用 WDAC 和 Windows PowerShell 来允许或阻止使用 Microsoft Intune 的 HoloLens 2 设备上的应用](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)。</span><span class="sxs-lookup"><span data-stu-id="25e0e-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="25e0e-111">当用户使用第一个示例步骤搜索安装在其 Windows 10 电脑上的应用时，可能需要进行一些尝试来缩小结果范围。</span><span class="sxs-lookup"><span data-stu-id="25e0e-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="25e0e-112">如果你不知道包的完整名称，则可能需要多次运行 "Add-appxpackage-name \* YourBestGuess \* " 才能找到它。</span><span class="sxs-lookup"><span data-stu-id="25e0e-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="25e0e-113">一旦名称运行 "$package 1 = Get-AppxPackage PackageName"</span><span class="sxs-lookup"><span data-stu-id="25e0e-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="25e0e-114">例如，为 Microsoft Edge 运行以下各项将返回多个结果，但从该列表中，你可以确定所需的完整名称为 MicrosoftEdge。</span><span class="sxs-lookup"><span data-stu-id="25e0e-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <a name="package-family-names-for-apps-on-hololens"></a><span data-ttu-id="25e0e-115">HoloLens 上应用的包系列名称</span><span class="sxs-lookup"><span data-stu-id="25e0e-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="25e0e-116">在上面链接的指南中，你可以手动编辑 newPolicy.xml 并为仅安装在 HoloLens 上的应用程序添加其包系列名称的规则。</span><span class="sxs-lookup"><span data-stu-id="25e0e-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="25e0e-117">有时，你可能会使用不在台式计算机上的应用，你想要添加到策略中。</span><span class="sxs-lookup"><span data-stu-id="25e0e-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="25e0e-118">下面列出了适用于 HoloLens 2 设备的常用和 In-Box 应用。</span><span class="sxs-lookup"><span data-stu-id="25e0e-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="25e0e-119">应用名称</span><span class="sxs-lookup"><span data-stu-id="25e0e-119">App Name</span></span>                   | <span data-ttu-id="25e0e-120">包系列名称</span><span class="sxs-lookup"><span data-stu-id="25e0e-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="25e0e-121">3D 查看器</span><span class="sxs-lookup"><span data-stu-id="25e0e-121">3D Viewer</span></span>                  | <span data-ttu-id="25e0e-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="25e0e-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="25e0e-123">应用安装程序</span><span class="sxs-lookup"><span data-stu-id="25e0e-123">App Installer</span></span>              | <span data-ttu-id="25e0e-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="25e0e-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</sup></span></span>         |
| <span data-ttu-id="25e0e-125">日历</span><span class="sxs-lookup"><span data-stu-id="25e0e-125">Calendar</span></span>                   | <span data-ttu-id="25e0e-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="25e0e-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="25e0e-127">照相机</span><span class="sxs-lookup"><span data-stu-id="25e0e-127">Camera</span></span>                     | <span data-ttu-id="25e0e-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="25e0e-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="25e0e-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="25e0e-129">Cortana</span></span>                    | <span data-ttu-id="25e0e-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="25e0e-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="25e0e-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="25e0e-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="25e0e-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="25e0e-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="25e0e-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="25e0e-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="25e0e-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="25e0e-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="25e0e-135">反馈中心</span><span class="sxs-lookup"><span data-stu-id="25e0e-135">Feedback Hub</span></span>               | <span data-ttu-id="25e0e-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="25e0e-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="25e0e-137">文件资源管理器</span><span class="sxs-lookup"><span data-stu-id="25e0e-137">File Explorer</span></span>              | <span data-ttu-id="25e0e-138">c5e2524a-ea46-4f67-6a9465d9d515_cw5n1h2txyewy 841f</span><span class="sxs-lookup"><span data-stu-id="25e0e-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="25e0e-139">Mail</span><span class="sxs-lookup"><span data-stu-id="25e0e-139">Mail</span></span>                       | <span data-ttu-id="25e0e-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="25e0e-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="25e0e-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="25e0e-141">Microsoft Store</span></span>            | <span data-ttu-id="25e0e-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="25e0e-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="25e0e-143">电影和电视</span><span class="sxs-lookup"><span data-stu-id="25e0e-143">Movies & TV</span></span>                | <span data-ttu-id="25e0e-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="25e0e-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="25e0e-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="25e0e-145">OneDrive</span></span>                   | <span data-ttu-id="25e0e-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="25e0e-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="25e0e-147">照片</span><span class="sxs-lookup"><span data-stu-id="25e0e-147">Photos</span></span>                     | <span data-ttu-id="25e0e-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="25e0e-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="25e0e-149">设置</span><span class="sxs-lookup"><span data-stu-id="25e0e-149">Settings</span></span>                   | <span data-ttu-id="25e0e-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="25e0e-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="25e0e-151">提示</span><span class="sxs-lookup"><span data-stu-id="25e0e-151">Tips</span></span>                       | <span data-ttu-id="25e0e-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="25e0e-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="25e0e-153">1-阻止应用程序安装程序将仅阻止应用程序安装程序应用程序，而不会阻止从其他源（例如 Microsoft Store 或 MDM 解决方案）安装的应用程序。</span><span class="sxs-lookup"><span data-stu-id="25e0e-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <a name="how-to-find-a-package-family-name"></a><span data-ttu-id="25e0e-154">如何查找包系列名称</span><span class="sxs-lookup"><span data-stu-id="25e0e-154">How to find a Package Family Name</span></span>

<span data-ttu-id="25e0e-155">如果某个应用不在此列表中，则用户可以使用设备门户连接到已安装了希望被阻止的应用的 HoloLens 2，以确定 PackageRelativeID，并从那里获取 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="25e0e-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="25e0e-156">在 HoloLens 2 设备上安装该应用。</span><span class="sxs-lookup"><span data-stu-id="25e0e-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="25e0e-157">打开设置-> 更新 & 的安全 >，并启用 **开发人员模式** 和 **设备门户**。</span><span class="sxs-lookup"><span data-stu-id="25e0e-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="25e0e-158">更多详细信息说明详细了解如何 [设置和使用设备门户](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="25e0e-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="25e0e-159">连接设备门户后，请导航到 " **视图** "，然后导航到 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="25e0e-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="25e0e-160">在 "已安装的应用" 面板中，使用下拉列表选择已安装的应用。</span><span class="sxs-lookup"><span data-stu-id="25e0e-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="25e0e-161">找到 PackageRelativeID。</span><span class="sxs-lookup"><span data-stu-id="25e0e-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="25e0e-162">在！之前复制应用字符，这些字符将是你的 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="25e0e-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


