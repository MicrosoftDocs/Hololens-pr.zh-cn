---
title: 如何通过 HoloLens 2 应用安装程序旁加载和安装应用
description: 通过 UI 加载和安装应用
keywords: 应用管理， 应用， hololens， 应用安装程序
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 11/10/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: e52cc2f031c284b619c61ffa04f259f76397faf5
ms.sourcegitcommit: 96dcd015ad24169295690a8ed13ea1bf480e4b9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/01/2021
ms.locfileid: "11253089"
---
# <span data-ttu-id="77a87-104">通过应用安装程序在 HoloLens 2 上安装应用</span><span class="sxs-lookup"><span data-stu-id="77a87-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="77a87-105">我们将 **向应用安装程序 (** 新功能) ，以允许你在 HoloLens 2 设备上更加无缝地安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="77a87-105">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="77a87-106">对于非托管 **设备，该功能将默认打开**。</span><span class="sxs-lookup"><span data-stu-id="77a87-106">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="77a87-107">为了防止企业中断，目前应用安装程序将不适用于 **托管设备** 。</span><span class="sxs-lookup"><span data-stu-id="77a87-107">To prevent disruption to enterprises, app installer will **not be available for managed devices** at this time.</span></span>  

> [!NOTE]
> <span data-ttu-id="77a87-108">此功能在 Windows 全息版版本 [20H2 – 2020 年 12 月更新中可用](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="77a87-108">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="77a87-109">确保设备 [已更新](hololens-update-hololens.md) 为使用此功能。</span><span class="sxs-lookup"><span data-stu-id="77a87-109">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="77a87-110">我们已 **在应用安装程序 (新增** 功能) 允许你在 HoloLens 2 设备上更加无缝地安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="77a87-110">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="77a87-111">对于非托管 **设备，该功能将默认打开**。</span><span class="sxs-lookup"><span data-stu-id="77a87-111">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="77a87-112">为了防止企业中断，应用安装程序目前对托管 **设备** 不可用。</span><span class="sxs-lookup"><span data-stu-id="77a87-112">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="77a87-113">如果以下任一项为真， **则设备** 将被视为"托管"设备：</span><span class="sxs-lookup"><span data-stu-id="77a87-113">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="77a87-114">MDM [已注册](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="77a87-114">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="77a87-115">使用预配 [包配置](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="77a87-115">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="77a87-116">用户 [标识](hololens-identity.md) 为 Azure AD</span><span class="sxs-lookup"><span data-stu-id="77a87-116">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="77a87-117">你现在无需启用开发人员模式或使用 Device Portal 即可安装应用。</span><span class="sxs-lookup"><span data-stu-id="77a87-117">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="77a87-118">将 (USB 或 Microsoft Edge) Appx 捆绑包下载到设备，并在文件资源管理器中导航到 Appx 捆绑包，以提示你开始安装。</span><span class="sxs-lookup"><span data-stu-id="77a87-118">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="77a87-119">或者， [从网页启动安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。</span><span class="sxs-lookup"><span data-stu-id="77a87-119">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="77a87-120">与从 Microsoft Store 安装的应用或使用 MDM 的 LOB 应用部署功能旁加载的应用一样，需要使用签名[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)工具对应用进行[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)数字签名，并且用于签名的证书必须受 HoloLens 设备信任，然后才能部署应用。</span><span class="sxs-lookup"><span data-stu-id="77a87-120">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="77a87-121">要求</span><span class="sxs-lookup"><span data-stu-id="77a87-121">Requirements</span></span>

### <span data-ttu-id="77a87-122">对于你的设备：</span><span class="sxs-lookup"><span data-stu-id="77a87-122">For your devices:</span></span>

 <span data-ttu-id="77a87-123">功能目前适用于 HoloLens 2 设备的 Windows Holographic 20H2 版本。</span><span class="sxs-lookup"><span data-stu-id="77a87-123">feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="77a87-124">确保已更新使用此方法的任何 [设备](hololens-update-hololens.md)。</span><span class="sxs-lookup"><span data-stu-id="77a87-124">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="77a87-125">对于你的应用：</span><span class="sxs-lookup"><span data-stu-id="77a87-125">For your apps:</span></span> 
<span data-ttu-id="77a87-126">应用的解决方案配置必须是**主**版本或版本，因为应用\*\*\*\* 安装程序将使用应用商店中的依赖项。</span><span class="sxs-lookup"><span data-stu-id="77a87-126">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="77a87-127">查看有关创建 [应用包的更多内容](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)。</span><span class="sxs-lookup"><span data-stu-id="77a87-127">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="77a87-128">通过此方法安装的应用必须进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="77a87-128">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="77a87-129">你需要使用证书对应用进行签名。</span><span class="sxs-lookup"><span data-stu-id="77a87-129">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="77a87-130">可以从 MS 受信任 [CA](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)列表获取证书，在这种情况下，无需执行任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="77a87-130">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="77a87-131">或者你可以对你自己的证书进行签名，但是该证书将需要推送到设备。</span><span class="sxs-lookup"><span data-stu-id="77a87-131">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="77a87-132">如何使用签名 [工具对应用进行签名。](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="77a87-132">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="77a87-133">证书选项：</span><span class="sxs-lookup"><span data-stu-id="77a87-133">Certificate options:</span></span>**

- [<span data-ttu-id="77a87-134">MS 受信任 CA 列表</span><span class="sxs-lookup"><span data-stu-id="77a87-134">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="77a87-135">选取证书部署方法。</span><span class="sxs-lookup"><span data-stu-id="77a87-135">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="77a87-136">[预配包](hololens-provisioning.md) 可应用于本地设备。</span><span class="sxs-lookup"><span data-stu-id="77a87-136">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="77a87-137">MDM 可用于应用 [具有设备配置的证书](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。</span><span class="sxs-lookup"><span data-stu-id="77a87-137">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="77a87-138">使用 on 设备 [证书管理器](certificate-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="77a87-138">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="77a87-139">安装方法</span><span class="sxs-lookup"><span data-stu-id="77a87-139">Installation method</span></span>

1. <span data-ttu-id="77a87-140">检查设备是否被视为托管设备。</span><span class="sxs-lookup"><span data-stu-id="77a87-140">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="77a87-141">检查 HoloLens 2 设备是否打开并登录。</span><span class="sxs-lookup"><span data-stu-id="77a87-141">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="77a87-142">在电脑上导航到自定义应用，将app.appxbundle 复制到 yourdevicename\Internal Storage\Downloads。</span><span class="sxs-lookup"><span data-stu-id="77a87-142">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="77a87-143">复制完文件后，可能会断开设备连接，稍后完成安装。</span><span class="sxs-lookup"><span data-stu-id="77a87-143">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="77a87-144">从 HoloLens 2 设备打开"开始" **菜单**，选择 **"所有应用** "并启动 **"文件资源管理器"** 应用。</span><span class="sxs-lookup"><span data-stu-id="77a87-144">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="77a87-145">导航到"下载"文件夹。</span><span class="sxs-lookup"><span data-stu-id="77a87-145">Navigate to the Downloads folder.</span></span> <span data-ttu-id="77a87-146">你可能需要在应用的左侧面板上先选择"此设备\*\*\*\*"，然后导航到"下载"。</span><span class="sxs-lookup"><span data-stu-id="77a87-146">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="77a87-147">选择 yourapp.appxbundle 文件。</span><span class="sxs-lookup"><span data-stu-id="77a87-147">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="77a87-148">应用安装程序将启动。</span><span class="sxs-lookup"><span data-stu-id="77a87-148">The App Installer will launch.</span></span> <span data-ttu-id="77a87-149">选择 **"安装** "按钮以安装应用。</span><span class="sxs-lookup"><span data-stu-id="77a87-149">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="77a87-150">安装完成后，已安装的应用将自动启动。</span><span class="sxs-lookup"><span data-stu-id="77a87-150">The installed app will automatically launch upon the completion of installing.</span></span>

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="77a87-152">安装疑难解答</span><span class="sxs-lookup"><span data-stu-id="77a87-152">Troubleshooting Installs</span></span>

<span data-ttu-id="77a87-153">如果应用安装失败，请查看以下内容进行疑难解答：</span><span class="sxs-lookup"><span data-stu-id="77a87-153">If your app failed to install check the following to troubleshoot:</span></span>

- <span data-ttu-id="77a87-154">你的应用是主版本或发布版本。</span><span class="sxs-lookup"><span data-stu-id="77a87-154">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="77a87-155">你的设备将更新为提供此功能的生成。</span><span class="sxs-lookup"><span data-stu-id="77a87-155">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="77a87-156">你[已连接到 Internet。](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="77a87-156">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="77a87-157">正确 [配置了 Microsoft Store](hololens-offline.md) 终结点。</span><span class="sxs-lookup"><span data-stu-id="77a87-157">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="77a87-158">Web 安装程序</span><span class="sxs-lookup"><span data-stu-id="77a87-158">Web Installer</span></span>

<span data-ttu-id="77a87-159">用户可以直接从 Web 服务器安装应用。</span><span class="sxs-lookup"><span data-stu-id="77a87-159">Users can install an app directly from a web server.</span></span> <span data-ttu-id="77a87-160">此流将应用安装程序与简单的下载和安装分发方法结合使用。</span><span class="sxs-lookup"><span data-stu-id="77a87-160">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="77a87-161">如何设置 Web 安装：</span><span class="sxs-lookup"><span data-stu-id="77a87-161">How to set up web install:</span></span>

1. <span data-ttu-id="77a87-162">确保应用已正确配置为安装。</span><span class="sxs-lookup"><span data-stu-id="77a87-162">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="77a87-163">按照 [以下步骤从网页启用安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。</span><span class="sxs-lookup"><span data-stu-id="77a87-163">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="77a87-164">最终用户体验：</span><span class="sxs-lookup"><span data-stu-id="77a87-164">End user experience:</span></span>

1. <span data-ttu-id="77a87-165">用户使用之前选择的方法接收证书并安装到设备。</span><span class="sxs-lookup"><span data-stu-id="77a87-165">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="77a87-166">用户访问通过上述步骤创建的 URL。</span><span class="sxs-lookup"><span data-stu-id="77a87-166">User visits the URL created from the step above.</span></span>

<span data-ttu-id="77a87-167">应用现在将安装到设备。</span><span class="sxs-lookup"><span data-stu-id="77a87-167">The app will now install to the device.</span></span> <span data-ttu-id="77a87-168">若要查找应用， **请打开"** 开始"菜单并选择"所有 **应用"** 按钮以查找你的应用。</span><span class="sxs-lookup"><span data-stu-id="77a87-168">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="77a87-169">有关应用安装程序安装方法疑难解答的更多帮助，请访问 [疑难解答应用安装程序问题](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。</span><span class="sxs-lookup"><span data-stu-id="77a87-169">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="77a87-170">不支持更新过程中 UI。</span><span class="sxs-lookup"><span data-stu-id="77a87-170">UI during the update process is not supported.</span></span> <span data-ttu-id="77a87-171">因此，此页上的 ShowPrompt [选项](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 和相关选项不受支持。</span><span class="sxs-lookup"><span data-stu-id="77a87-171">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="77a87-172">示例应用</span><span class="sxs-lookup"><span data-stu-id="77a87-172">Sample Apps</span></span>

<span data-ttu-id="77a87-173">若要使用一些示例应用试用应用安装程序，请查看我们的一些可用示例：</span><span class="sxs-lookup"><span data-stu-id="77a87-173">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="77a87-174">MRTK 示例中心</span><span class="sxs-lookup"><span data-stu-id="77a87-174">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="77a87-175">Surfaces</span><span class="sxs-lookup"><span data-stu-id="77a87-175">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="77a87-176">可用于测试的 UWP 示例应用</span><span class="sxs-lookup"><span data-stu-id="77a87-176">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
