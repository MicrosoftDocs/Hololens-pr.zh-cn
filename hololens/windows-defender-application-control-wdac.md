---
title: Windows Defender 应用程序控制 - WDAC
description: 概述什么是 WDAC 以及如何使用来管理 HoloLens 设备。
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
ms.openlocfilehash: dc1deb2b159d3d41b1a1f73c33f1cd44731f8e4d
ms.sourcegitcommit: 72ae5a270f869393872eac160e43076eaa35fe4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135564"
---
# <span data-ttu-id="1ec43-103">Windows Defender 应用程序控制 - WDAC</span><span class="sxs-lookup"><span data-stu-id="1ec43-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="1ec43-104">WDAC 允许 IT 管理员配置其设备，阻止在设备上启动应用。</span><span class="sxs-lookup"><span data-stu-id="1ec43-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="1ec43-105">这与设备限制的方法（如 Kiosk 模式）不同，其中显示了用户将隐藏设备上的应用但仍可启动的 UI。</span><span class="sxs-lookup"><span data-stu-id="1ec43-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="1ec43-106">在实现 WDAC 时，应用仍在 "所有应用" 列表中可见，但 WDAC 将阻止设备用户启动这些应用和进程。</span><span class="sxs-lookup"><span data-stu-id="1ec43-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

> [!NOTE]
> <span data-ttu-id="1ec43-107">当最终用户尝试启动由 WDAC 阻止的应用时，在 HoloLens 上，他们将不会收到有关无法启动该应用的通知。</span><span class="sxs-lookup"><span data-stu-id="1ec43-107">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="1ec43-108">以下是用户了解如何 [使用 WDAC 和 Windows PowerShell 在 HoloLens 2 设备上使用 Microsoft Intune 允许或阻止应用](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)的指南。</span><span class="sxs-lookup"><span data-stu-id="1ec43-108">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="1ec43-109">当用户使用第一个示例步骤搜索在其 Windows 10 电脑上安装的应用时，可能需要先尝试缩小结果范围。</span><span class="sxs-lookup"><span data-stu-id="1ec43-109">When users search for apps installed on their Windows 10 PC using the first example step they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="1ec43-110">如果不知道程序包的完整名称，可能需要多次运行 "Add-appxpackage-name \ \* YourBestGuess \ \*" 才能找到它。</span><span class="sxs-lookup"><span data-stu-id="1ec43-110">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="1ec43-111">然后，一旦名称运行 "$package 1 = Get-AppxPackage name PackageName"</span><span class="sxs-lookup"><span data-stu-id="1ec43-111">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="1ec43-112">例如，运行以下 for Edge 将返回多个结果，但从该列表中，你可以确定所需的完整名称是 MicrosoftEdge。</span><span class="sxs-lookup"><span data-stu-id="1ec43-112">For example running the following for Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span> 

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="1ec43-113">用于 HoloLens 应用的程序包系列名称</span><span class="sxs-lookup"><span data-stu-id="1ec43-113">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="1ec43-114">在上面链接的指南中，你可以手动编辑 newPolicy.xml，并为仅在 HoloLens 上安装的应用程序添加程序包系列名称。</span><span class="sxs-lookup"><span data-stu-id="1ec43-114">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications which are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="1ec43-115">有时，你可能使用的应用不在桌面电脑上，而你希望添加到策略。</span><span class="sxs-lookup"><span data-stu-id="1ec43-115">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span> 

<span data-ttu-id="1ec43-116">下面是用于 HoloLens 2 设备的常用和 In-Box 应用的列表。</span><span class="sxs-lookup"><span data-stu-id="1ec43-116">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="1ec43-117">应用名称</span><span class="sxs-lookup"><span data-stu-id="1ec43-117">App Name</span></span>                   | <span data-ttu-id="1ec43-118">程序包系列名称</span><span class="sxs-lookup"><span data-stu-id="1ec43-118">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="1ec43-119">3D 查看器</span><span class="sxs-lookup"><span data-stu-id="1ec43-119">3D Viewer</span></span>                  | <span data-ttu-id="1ec43-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ec43-120">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="1ec43-121">应用安装程序</span><span class="sxs-lookup"><span data-stu-id="1ec43-121">App Installer</span></span>              | <span data-ttu-id="1ec43-122">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="1ec43-122">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="1ec43-123">日历</span><span class="sxs-lookup"><span data-stu-id="1ec43-123">Calendar</span></span>                   | <span data-ttu-id="1ec43-124">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ec43-124">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="1ec43-125">相机</span><span class="sxs-lookup"><span data-stu-id="1ec43-125">Camera</span></span>                     | <span data-ttu-id="1ec43-126">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="1ec43-126">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="1ec43-127">Cortana</span><span class="sxs-lookup"><span data-stu-id="1ec43-127">Cortana</span></span>                    | <span data-ttu-id="1ec43-128">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ec43-128">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="1ec43-129">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="1ec43-129">Dynamics 365 Guides</span></span>        | <span data-ttu-id="1ec43-130">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ec43-130">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="1ec43-131">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="1ec43-131">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="1ec43-132">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ec43-132">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="1ec43-133">反馈中心</span><span class="sxs-lookup"><span data-stu-id="1ec43-133">Feedback Hub</span></span>               | <span data-ttu-id="1ec43-134">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ec43-134">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="1ec43-135">文件资源管理器</span><span class="sxs-lookup"><span data-stu-id="1ec43-135">File Explorer</span></span>              | <span data-ttu-id="1ec43-136">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="1ec43-136">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="1ec43-137">Mail</span><span class="sxs-lookup"><span data-stu-id="1ec43-137">Mail</span></span>                       | <span data-ttu-id="1ec43-138">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ec43-138">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="1ec43-139">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="1ec43-139">Microsoft Store</span></span>            | <span data-ttu-id="1ec43-140">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ec43-140">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="1ec43-141">电影和电视</span><span class="sxs-lookup"><span data-stu-id="1ec43-141">Movies & TV</span></span>                | <span data-ttu-id="1ec43-142">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ec43-142">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="1ec43-143">OneDrive</span><span class="sxs-lookup"><span data-stu-id="1ec43-143">OneDrive</span></span>                   | <span data-ttu-id="1ec43-144">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ec43-144">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="1ec43-145">照片</span><span class="sxs-lookup"><span data-stu-id="1ec43-145">Photos</span></span>                     | <span data-ttu-id="1ec43-146">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ec43-146">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="1ec43-147">“设置”</span><span class="sxs-lookup"><span data-stu-id="1ec43-147">Settings</span></span>                   | <span data-ttu-id="1ec43-148">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="1ec43-148">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="1ec43-149">提示</span><span class="sxs-lookup"><span data-stu-id="1ec43-149">Tips</span></span>                       | <span data-ttu-id="1ec43-150">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="1ec43-150">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="1ec43-151">1-阻止应用安装程序仅阻止应用安装程序应用，而不会阻止从其他源（如 Microsoft Store 或你的 MDM 解决方案）安装的应用。</span><span class="sxs-lookup"><span data-stu-id="1ec43-151">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="1ec43-152">如何查找程序包系列名称</span><span class="sxs-lookup"><span data-stu-id="1ec43-152">How to find a Package Family Name</span></span>

<span data-ttu-id="1ec43-153">如果应用不在此列表中，则用户可以使用 Device Portal 连接到安装了希望阻止的应用的 HoloLens 2，以确定 PackageRelativeID 以及从那里获取 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="1ec43-153">If an app is not on this list then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="1ec43-154">在 HoloLens 2 设备上安装该应用。</span><span class="sxs-lookup"><span data-stu-id="1ec43-154">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="1ec43-155">打开设置 >-为开发人员 & 便捷性 > 更新，并启用 **开发人员模式** 和 **Device portal**。</span><span class="sxs-lookup"><span data-stu-id="1ec43-155">Open Settings -> Updates & Securtiy -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="1ec43-156">有关详细信息的详细说明 [，请参阅在此处设置和使用 device portal](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="1ec43-156">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="1ec43-157">连接设备门户后，导航到 " **视图** "，然后导航到 " **应用**"。</span><span class="sxs-lookup"><span data-stu-id="1ec43-157">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="1ec43-158">在 "已安装的应用" 面板中，使用下拉列表选择已安装的应用。</span><span class="sxs-lookup"><span data-stu-id="1ec43-158">Within the Installed Apps panel use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="1ec43-159">找到 PackageRelativeID。</span><span class="sxs-lookup"><span data-stu-id="1ec43-159">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="1ec43-160">在！之前复制应用字符，这将是你的 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="1ec43-160">Copy app characters before the !, this will be your PackageFamilyName.</span></span>

## <span data-ttu-id="1ec43-161">示例阻止应用安装程序</span><span class="sxs-lookup"><span data-stu-id="1ec43-161">Sample - Blocking App Installer</span></span>

<span data-ttu-id="1ec43-162">例如，你可能希望阻止 [应用安装程序](app-deploy-app-installer.md) 应用。</span><span class="sxs-lookup"><span data-stu-id="1ec43-162">As an example you may wish to block the [App Installer](app-deploy-app-installer.md) app.</span></span> <span data-ttu-id="1ec43-163">我们为此示例提供了一些示例代码。</span><span class="sxs-lookup"><span data-stu-id="1ec43-163">We have included some sample code for this example.</span></span> <span data-ttu-id="1ec43-164">请下载 [此示例的这些代码示例](https://aka.ms/HoloLensDocs-Sample-WDAC-App-Installer)。</span><span class="sxs-lookup"><span data-stu-id="1ec43-164">Please download these [code samples for this example](https://aka.ms/HoloLensDocs-Sample-WDAC-App-Installer).</span></span> <span data-ttu-id="1ec43-165">在 zip 文件中，您可以找到：</span><span class="sxs-lookup"><span data-stu-id="1ec43-165">In the zip file you'll find:</span></span>

| <span data-ttu-id="1ec43-166">文件</span><span class="sxs-lookup"><span data-stu-id="1ec43-166">File</span></span> | <span data-ttu-id="1ec43-167">用途</span><span class="sxs-lookup"><span data-stu-id="1ec43-167">Use</span></span> |
|-|-|
| <span data-ttu-id="1ec43-168">compiledPolicy</span><span class="sxs-lookup"><span data-stu-id="1ec43-168">compiledPolicy.bin</span></span> | [<span data-ttu-id="1ec43-169">在步骤9中创建，在最后步骤10中使用。</span><span class="sxs-lookup"><span data-stu-id="1ec43-169">Created in Step 9, used in final Step 10.</span></span>](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| <span data-ttu-id="1ec43-170">mergedPolicy.xml</span><span class="sxs-lookup"><span data-stu-id="1ec43-170">mergedPolicy.xml</span></span> | [<span data-ttu-id="1ec43-171">在步骤6中创建。</span><span class="sxs-lookup"><span data-stu-id="1ec43-171">Created in Step 6.</span></span>](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens) |
| <span data-ttu-id="1ec43-172">WDAC_Set syncml</span><span class="sxs-lookup"><span data-stu-id="1ec43-172">WDAC_Set.syncml</span></span> | <span data-ttu-id="1ec43-173">不在 WDAC 中使用，但可用于 [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp)</span><span class="sxs-lookup"><span data-stu-id="1ec43-173">Not used in WDAC but can be used for for [EnterpriseModernAppManagement CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp)</span></span> |

<span data-ttu-id="1ec43-174">如果你想要尝试立即阻止应用，在这种情况下是应用安装程序安装应用，请使用 compiledPolicy 文件，然后跳到上面的链接中的步骤10。</span><span class="sxs-lookup"><span data-stu-id="1ec43-174">If you would like to try immediately blocking an app, in this case the App Installer app, then use the compiledPolicy.bin file and skip to step 10 in the link above.</span></span> <span data-ttu-id="1ec43-175">这将允许你测试自定义策略并确保组分配和策略配置正确无误。</span><span class="sxs-lookup"><span data-stu-id="1ec43-175">This will allow you to test out the custom policy and ensure the group assignments and policy configuration is correct.</span></span> 

<span data-ttu-id="1ec43-176">如果你想要将阻止应用安装程序的 WDAC 策略与上述列表中的其他应用程序合并，或任何其他应用，则可以使用 mergedPolicy.xml 文件并继续合并新策略。</span><span class="sxs-lookup"><span data-stu-id="1ec43-176">If you would like to combine the WDAC policy for blocking App Installer with other apps from the list above, or any other app, then you may use the mergedPolicy.xml file and continue to merge new policies.</span></span> <span data-ttu-id="1ec43-177">正如上面所述，WDAC 策略是累加的，因此不是必需的。</span><span class="sxs-lookup"><span data-stu-id="1ec43-177">As stated above WDAC policies are additive so this is not required.</span></span> 

<span data-ttu-id="1ec43-178">由于应用程序安装程序应用通过尝试打开文件启动，将显示一个提示。</span><span class="sxs-lookup"><span data-stu-id="1ec43-178">Since the App Installer app is launched via trying to open a file will be presented with a prompt.</span></span> <span data-ttu-id="1ec43-179">按 WDAC 阻止的上述应用不会出现提示，因为用户正在尝试在其设备上打开文件，因此会显示一个错误以打开文件。</span><span class="sxs-lookup"><span data-stu-id="1ec43-179">As stated above Apps blocked by WDAC do not present a prompt they are blocked, however since the user is attempting to open a file on their device they are presented with an error for opening the file.</span></span> 

![从 WDAC 阻止应用安装](images\wdac-app-installer-no-launch.jpg)

<span data-ttu-id="1ec43-181">如果你不希望使用 WDAC，你可以选择使用 [ENTERPRISEMODERNAPPMANAGEMENT CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) 来删除应用安装 UX，它是一个应用。</span><span class="sxs-lookup"><span data-stu-id="1ec43-181">If you do not wish to use WDAC, you may as an alternative use [EnterpriseModernAppManagement CSP](https://docs.microsoft.com/windows/client-management/mdm/enterprisemodernappmanagement-csp) to remove the App Installer UX, which is an app after all.</span></span> <span data-ttu-id="1ec43-182">这样做的结果是将从设备卸载应用安装程序应用。</span><span class="sxs-lookup"><span data-stu-id="1ec43-182">The result of this is that the App Installer app will be uninstalled from the device.</span></span> <span data-ttu-id="1ec43-183">.appx、msix、msixbundle 和其他文件扩展名以及用于 web 到应用启动的协议将不再由应用安装程序应用处理。</span><span class="sxs-lookup"><span data-stu-id="1ec43-183">.appx, .msix, .msixbundle, and other file extensions as well as protocol for web-to-app launch will no longer be handled by the App Installer app.</span></span> <span data-ttu-id="1ec43-184">用户将收到在应用商店中搜索文件扩展名/协议的处理程序的提示，并且由于未列出该应用，因此不会找到该应用。</span><span class="sxs-lookup"><span data-stu-id="1ec43-184">The user will get a prompt to search for a handler for the file extension/protocol in the store and they will not find the app because it’s not listed.</span></span>