---
title: Windows Defender 应用程序控制 - WDAC
description: 概述什么是 WDAC 以及如何用于管理 HoloLens 设备。
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
ms.openlocfilehash: d337f9856eaeac433524d7bb8b60e9a24e264b80
ms.sourcegitcommit: fc268335e5df529a1cedc2c6b88fa86245fe1b9b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2020
ms.locfileid: "11252643"
---
# <span data-ttu-id="cd6e1-103">Windows Defender 应用程序控制 - WDAC</span><span class="sxs-lookup"><span data-stu-id="cd6e1-103">Windows Defender Application Control - WDAC</span></span>

<span data-ttu-id="cd6e1-104">WDAC 允许 IT 管理员配置其设备以阻止在设备上启动应用。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-104">WDAC allows an IT Admin to configure their devices to block the launch of apps on devices.</span></span> <span data-ttu-id="cd6e1-105">这不同于设备限制方法（如展台模式）的方法，即向用户显示隐藏设备上应用但仍可以启动应用的 UI。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-105">This is different than methods of device restriction such as Kiosk mode, where  the user is presented with a UI that hides the apps on the device but they can still be launched.</span></span> <span data-ttu-id="cd6e1-106">实现 WDAC 时，应用仍显示在"所有应用"列表中，但 WDAC 会阻止设备用户启动这些应用和进程。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-106">While WDAC is implemented, the apps are still visible in the All Apps list but WDAC stops those apps and processes from being able to be launched by the device user.</span></span>

<span data-ttu-id="cd6e1-107">可以为设备分配多个 WDAC 策略。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-107">A device may be assigned more than one WDAC policy.</span></span> <span data-ttu-id="cd6e1-108">如果在一个系统上设置了多个 WDAC 策略，则最严格的策略将生效。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-108">If multiple WDAC policies are set on a system, most restrictive ones take effect.</span></span> 

> [!NOTE]
> <span data-ttu-id="cd6e1-109">当最终用户尝试启动被 WDAC 阻止的应用时，在 HoloLens 上，他们将不会收到有关无法启动该应用的通知。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-109">When end users attempt to launch an app that is blocked by WDAC, on HoloLens they will not receive a notification about not being able to launch that app.</span></span>

<span data-ttu-id="cd6e1-110">以下是用户了解如何使用 WDAC 和 Windows PowerShell在 [HoloLens 2](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)设备上使用 Microsoft Intune 允许或阻止应用的指南。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-110">The following is a guide for users to learn how to [use WDAC and Windows PowerShell to allow or block apps on HoloLens 2 devices with Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens).</span></span>

<span data-ttu-id="cd6e1-111">当用户使用第一个示例步骤搜索安装在其 Windows 10 电脑上的应用时，他们可能需要尝试缩小结果范围。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-111">When users search for apps installed on their Windows 10 PC using the first example step, they may need to make a few attempts to narrow down the results.</span></span>

```powershell
$package1 = Get-AppxPackage -name *<applicationname>*
``` 

<span data-ttu-id="cd6e1-112">如果不知道程序包的完整名称，可能需要多次运行"Get-AppxPackage -name \*YourBestGuess\*"才能找到它。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-112">If you don’t know the full name of the package, you may need to run ‘Get-AppxPackage -name \*YourBestGuess\*’ a few times to find it.</span></span> <span data-ttu-id="cd6e1-113">然后，运行名称"$package 1 = Get-AppxPackage -name Actual.PackageName"</span><span class="sxs-lookup"><span data-stu-id="cd6e1-113">Then once you have the name run ‘$package1 = Get-AppxPackage -name Actual.PackageName‘</span></span>

<span data-ttu-id="cd6e1-114">例如，为 Microsoft Edge 运行以下代码将返回多个结果，但从该列表可确定所需的全名是 Microsoft.MicrosoftEdge。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-114">For example running the following for Microsoft Edge will return more than one result, but from that list you can identify that the full name you need is Microsoft.MicrosoftEdge.</span></span>

```powershell
Get-AppxPackage -name *edge*
``` 

## <span data-ttu-id="cd6e1-115">HoloLens 上应用的程序包系列名称</span><span class="sxs-lookup"><span data-stu-id="cd6e1-115">Package Family Names for apps on HoloLens</span></span>

<span data-ttu-id="cd6e1-116">在以上链接的指南中，你可以手动编辑newPolicy.xml并添加仅安装在 HoloLens 及其程序包系列名称上的应用程序的规则。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-116">In the guide linked above, you can manually edit newPolicy.xml and add rules for applications that are only installed on HoloLens with their package family names.</span></span> <span data-ttu-id="cd6e1-117">有时，你可能使用一些应用，这些应用不在你希望添加到策略的台式电脑上。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-117">Sometimes there are apps you may use to use that are not on your desktop PC that you wish to add to policy.</span></span>

<span data-ttu-id="cd6e1-118">下面是 HoloLens 2 设备的常用In-Box应用列表。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-118">Here is a list of commonly used and In-Box apps for HoloLens 2 devices.</span></span>

| <span data-ttu-id="cd6e1-119">应用名称</span><span class="sxs-lookup"><span data-stu-id="cd6e1-119">App Name</span></span>                   | <span data-ttu-id="cd6e1-120">程序包系列名称</span><span class="sxs-lookup"><span data-stu-id="cd6e1-120">Package Family Name</span></span>                                |
|----------------------------|----------------------------------------------------|
| <span data-ttu-id="cd6e1-121">3D 查看器</span><span class="sxs-lookup"><span data-stu-id="cd6e1-121">3D Viewer</span></span>                  | <span data-ttu-id="cd6e1-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cd6e1-122">Microsoft.Microsoft3DViewer_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="cd6e1-123">应用安装程序</span><span class="sxs-lookup"><span data-stu-id="cd6e1-123">App Installer</span></span>              | <span data-ttu-id="cd6e1-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup> 1</span><span class="sxs-lookup"><span data-stu-id="cd6e1-124">Microsoft.DesktopAppInstaller_8wekyb3d8bbwe <sup>1</span></span></sup>         |
| <span data-ttu-id="cd6e1-125">日历</span><span class="sxs-lookup"><span data-stu-id="cd6e1-125">Calendar</span></span>                   | <span data-ttu-id="cd6e1-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cd6e1-126">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="cd6e1-127">相机</span><span class="sxs-lookup"><span data-stu-id="cd6e1-127">Camera</span></span>                     | <span data-ttu-id="cd6e1-128">HoloCamera_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="cd6e1-128">HoloCamera_cw5n1h2txyewy</span></span>                           |
| <span data-ttu-id="cd6e1-129">Cortana</span><span class="sxs-lookup"><span data-stu-id="cd6e1-129">Cortana</span></span>                    | <span data-ttu-id="cd6e1-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cd6e1-130">Microsoft.549981C3F5F10_8wekyb3d8bbwe</span></span>              |
| <span data-ttu-id="cd6e1-131">Dynamics 365 Guides</span><span class="sxs-lookup"><span data-stu-id="cd6e1-131">Dynamics 365 Guides</span></span>        | <span data-ttu-id="cd6e1-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cd6e1-132">Microsoft.Dynamics365.Guides_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="cd6e1-133">Dynamics 365 Remote Assist</span><span class="sxs-lookup"><span data-stu-id="cd6e1-133">Dynamics 365 Remote Assist</span></span> | <span data-ttu-id="cd6e1-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cd6e1-134">Microsoft.MicrosoftRemoteAssist_8wekyb3d8bbwe</span></span>      |
| <span data-ttu-id="cd6e1-135">反馈中心</span><span class="sxs-lookup"><span data-stu-id="cd6e1-135">Feedback Hub</span></span>               | <span data-ttu-id="cd6e1-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cd6e1-136">Microsoft.WindowsFeedbackHub_8wekyb3d8bbwe</span></span>         |
| <span data-ttu-id="cd6e1-137">文件资源管理器</span><span class="sxs-lookup"><span data-stu-id="cd6e1-137">File Explorer</span></span>              | <span data-ttu-id="cd6e1-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="cd6e1-138">c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy</span></span> |
| <span data-ttu-id="cd6e1-139">Mail</span><span class="sxs-lookup"><span data-stu-id="cd6e1-139">Mail</span></span>                       | <span data-ttu-id="cd6e1-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cd6e1-140">microsoft.windowscommunicationsapps_8wekyb3d8bbwe</span></span>  |
| <span data-ttu-id="cd6e1-141">Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="cd6e1-141">Microsoft Store</span></span>            | <span data-ttu-id="cd6e1-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cd6e1-142">Microsoft.WindowsStore_8wekyb3d8bbwe</span></span>               |
| <span data-ttu-id="cd6e1-143">电影和电视</span><span class="sxs-lookup"><span data-stu-id="cd6e1-143">Movies & TV</span></span>                | <span data-ttu-id="cd6e1-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cd6e1-144">Microsoft.ZuneVideo_8wekyb3d8bbwe</span></span>                  |
| <span data-ttu-id="cd6e1-145">OneDrive</span><span class="sxs-lookup"><span data-stu-id="cd6e1-145">OneDrive</span></span>                   | <span data-ttu-id="cd6e1-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cd6e1-146">microsoft.microsoftskydrive_8wekyb3d8bbwe</span></span>          |
| <span data-ttu-id="cd6e1-147">照片</span><span class="sxs-lookup"><span data-stu-id="cd6e1-147">Photos</span></span>                     | <span data-ttu-id="cd6e1-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cd6e1-148">Microsoft.Windows.Photos_8wekyb3d8bbwe</span></span>             |
| <span data-ttu-id="cd6e1-149">“设置”</span><span class="sxs-lookup"><span data-stu-id="cd6e1-149">Settings</span></span>                   | <span data-ttu-id="cd6e1-150">HolographicSystemSettings_cw5n1h2txyewy</span><span class="sxs-lookup"><span data-stu-id="cd6e1-150">HolographicSystemSettings_cw5n1h2txyewy</span></span>            |
| <span data-ttu-id="cd6e1-151">提示</span><span class="sxs-lookup"><span data-stu-id="cd6e1-151">Tips</span></span>                       | <span data-ttu-id="cd6e1-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="cd6e1-152">Microsoft.HoloLensTips_8wekyb3d8bbwe</span></span>               |

- <span data-ttu-id="cd6e1-153">1 - 阻止应用安装程序将仅阻止应用安装程序应用，不会阻止从其他源（如 Microsoft Store 或 MDM 解决方案）安装的应用。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-153">1 - Blocking App Installer will only block the App Installer app, and not apps installed from other sources such as the Microsoft Store or from your MDM solution.</span></span>

### <span data-ttu-id="cd6e1-154">如何查找程序包系列名称</span><span class="sxs-lookup"><span data-stu-id="cd6e1-154">How to find a Package Family Name</span></span>

<span data-ttu-id="cd6e1-155">如果应用不在此列表上，则用户可以使用 Device Portal（连接到已安装希望阻止的应用的 HoloLens 2）来确定 PackageRelativeID，然后从该门户获取 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-155">If an app is not on this list, then a user may use Device Portal, connected to a HoloLens 2 that has installed the app wished to be blocked, to determine the PackageRelativeID and from there get the PackageFamilyName.</span></span>

1. <span data-ttu-id="cd6e1-156">在 HoloLens 2 设备上安装应用。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-156">Install the app on your HoloLens 2 device.</span></span> 
1. <span data-ttu-id="cd6e1-157">打开"设置>更新&安全 ->，然后启用开发人员**模式\*\*\*\*，然后启用 Device Portal。**</span><span class="sxs-lookup"><span data-stu-id="cd6e1-157">Open Settings -> Updates & Security -> For developers, and enable **Developer mode** and then **Device portal**.</span></span> 
    1. <span data-ttu-id="cd6e1-158">更多详细信息说明在此处阅读有关 [设置和使用设备门户的详细信息](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-158">More more details instructions read more about [setup and use of device portal here](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal).</span></span>
1. <span data-ttu-id="cd6e1-159">连接 Device Portal 后，导航到 **"视图**"和"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="cd6e1-159">Once Device Portal is connected, navigate to **Views** then **Apps**.</span></span> 
1. <span data-ttu-id="cd6e1-160">在"已安装的应用"面板中，使用下拉列表选择已安装的应用。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-160">Within the Installed Apps panel, use the dropdown to select the installed app.</span></span> 
1. <span data-ttu-id="cd6e1-161">找到 PackageRelativeID。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-161">Locate the PackageRelativeID.</span></span> 
1. <span data-ttu-id="cd6e1-162">在 ！之前复制应用字符，这些字符将是你的 PackageFamilyName。</span><span class="sxs-lookup"><span data-stu-id="cd6e1-162">Copy app characters before the !, these characters will be your PackageFamilyName.</span></span>


