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
ms.openlocfilehash: ab0c58d5a97d5dbaf83adf321d1f9fbc01b3ad03
ms.sourcegitcommit: 37910c10f0f98aa9cbdc29124cd8f14ee0af3fbd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2021
ms.locfileid: "11280651"
---
# <span data-ttu-id="ea152-104">通过应用安装程序在 HoloLens 2 上安装应用</span><span class="sxs-lookup"><span data-stu-id="ea152-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="ea152-105">此功能在 Windows 全息版版本 [20H2 – 2020 年 12 月更新中可用](hololens-release-notes.md)。</span><span class="sxs-lookup"><span data-stu-id="ea152-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="ea152-106">确保设备 [已更新](hololens-update-hololens.md) 为使用此功能。</span><span class="sxs-lookup"><span data-stu-id="ea152-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="ea152-107">我们已 **在应用安装程序 (新增** 功能) 允许你在 HoloLens 2 设备上更加无缝地安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="ea152-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="ea152-108">对于非 **托管设备，该功能将默认打开**。</span><span class="sxs-lookup"><span data-stu-id="ea152-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="ea152-109">为了防止企业中断，应用安装程序目前对托管 **设备** 不可用。</span><span class="sxs-lookup"><span data-stu-id="ea152-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="ea152-110">如果以下任一项为真， **则设备** 将被视为"托管"设备：</span><span class="sxs-lookup"><span data-stu-id="ea152-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="ea152-111">MDM [已注册](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="ea152-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="ea152-112">使用预配 [包配置](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="ea152-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="ea152-113">用户 [标识](hololens-identity.md) 为 Azure AD</span><span class="sxs-lookup"><span data-stu-id="ea152-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="ea152-114">你现在无需启用开发人员模式或使用 Device Portal 即可安装应用。</span><span class="sxs-lookup"><span data-stu-id="ea152-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="ea152-115">将 (USB 或 Microsoft Edge) Appx 捆绑包下载到设备，并在文件资源管理器中导航到 Appx 捆绑包，以提示开始安装。</span><span class="sxs-lookup"><span data-stu-id="ea152-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="ea152-116">或者， [从网页启动安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。</span><span class="sxs-lookup"><span data-stu-id="ea152-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="ea152-117">与从 Microsoft Store 安装的应用或使用 MDM 的 LOB 应用部署功能旁加载的应用一样，需要使用签名[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)工具对应用进行[](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)数字签名，并且用于签名的证书必须受 HoloLens 设备信任，然后才能部署应用。</span><span class="sxs-lookup"><span data-stu-id="ea152-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <span data-ttu-id="ea152-118">要求</span><span class="sxs-lookup"><span data-stu-id="ea152-118">Requirements</span></span>

### <span data-ttu-id="ea152-119">对于你的设备：</span><span class="sxs-lookup"><span data-stu-id="ea152-119">For your devices:</span></span>

 <span data-ttu-id="ea152-120">功能目前适用于 HoloLens 2 设备的 Windows Holographic 20H2 版本。</span><span class="sxs-lookup"><span data-stu-id="ea152-120">feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="ea152-121">确保已更新使用此方法的任何 [设备](hololens-update-hololens.md)。</span><span class="sxs-lookup"><span data-stu-id="ea152-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <span data-ttu-id="ea152-122">对于你的应用：</span><span class="sxs-lookup"><span data-stu-id="ea152-122">For your apps:</span></span> 
<span data-ttu-id="ea152-123">应用的解决方案配置必须是**主**版本或版本，因为应用\*\*\*\* 安装程序将使用应用商店中的依赖项。</span><span class="sxs-lookup"><span data-stu-id="ea152-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="ea152-124">查看有关创建 [应用包的更多内容](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)。</span><span class="sxs-lookup"><span data-stu-id="ea152-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="ea152-125">通过此方法安装的应用必须进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="ea152-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="ea152-126">你需要使用证书对应用进行签名。</span><span class="sxs-lookup"><span data-stu-id="ea152-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="ea152-127">可以从 MS 受信任 [CA](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)列表获取证书，在这种情况下，无需执行任何额外操作。</span><span class="sxs-lookup"><span data-stu-id="ea152-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="ea152-128">或者你可以对你自己的证书进行签名，但是该证书将需要推送到设备。</span><span class="sxs-lookup"><span data-stu-id="ea152-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="ea152-129">如何使用签名 [工具对应用进行签名。](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="ea152-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="ea152-130">证书选项：</span><span class="sxs-lookup"><span data-stu-id="ea152-130">Certificate options:</span></span>**

- [<span data-ttu-id="ea152-131">MS 受信任 CA 列表</span><span class="sxs-lookup"><span data-stu-id="ea152-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="ea152-132">选取证书部署方法。</span><span class="sxs-lookup"><span data-stu-id="ea152-132">Pick a certificate deployment method.</span></span>**

- <span data-ttu-id="ea152-133">[预配包](hololens-provisioning.md) 可应用于本地设备。</span><span class="sxs-lookup"><span data-stu-id="ea152-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="ea152-134">MDM 可用于应用 [具有设备配置的证书](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。</span><span class="sxs-lookup"><span data-stu-id="ea152-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="ea152-135">使用 on 设备 [证书管理器](certificate-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="ea152-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <span data-ttu-id="ea152-136">安装方法</span><span class="sxs-lookup"><span data-stu-id="ea152-136">Installation method</span></span>

1. <span data-ttu-id="ea152-137">检查设备是否被视为托管设备。</span><span class="sxs-lookup"><span data-stu-id="ea152-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="ea152-138">检查 HoloLens 2 设备是否打开并登录。</span><span class="sxs-lookup"><span data-stu-id="ea152-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="ea152-139">在电脑上导航到自定义应用，将app.appxbundle 复制到 yourdevicename\Internal Storage\Downloads。</span><span class="sxs-lookup"><span data-stu-id="ea152-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="ea152-140">复制完文件后，可能会断开设备连接，稍后完成安装。</span><span class="sxs-lookup"><span data-stu-id="ea152-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="ea152-141">从 HoloLens 2 设备打开"开始" **菜单**，选择 **"所有应用** "并启动 **"文件资源管理器"** 应用。</span><span class="sxs-lookup"><span data-stu-id="ea152-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="ea152-142">导航到"下载"文件夹。</span><span class="sxs-lookup"><span data-stu-id="ea152-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="ea152-143">你可能需要在应用的左侧面板上先选择"此设备\*\*\*\*"，然后导航到"下载"。</span><span class="sxs-lookup"><span data-stu-id="ea152-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="ea152-144">选择 yourapp.appxbundle 文件。</span><span class="sxs-lookup"><span data-stu-id="ea152-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="ea152-145">应用安装程序将启动。</span><span class="sxs-lookup"><span data-stu-id="ea152-145">The App Installer will launch.</span></span> <span data-ttu-id="ea152-146">选择 **"安装** "按钮以安装应用。</span><span class="sxs-lookup"><span data-stu-id="ea152-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="ea152-147">安装完成后，已安装的应用将自动启动。</span><span class="sxs-lookup"><span data-stu-id="ea152-147">The installed app will automatically launch upon the completion of installing.</span></span>

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="ea152-149">安装疑难解答</span><span class="sxs-lookup"><span data-stu-id="ea152-149">Troubleshooting Installs</span></span>

<span data-ttu-id="ea152-150">如果应用安装失败，请查看以下内容进行疑难解答：</span><span class="sxs-lookup"><span data-stu-id="ea152-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="ea152-151">你的应用是主版本或发布版本。</span><span class="sxs-lookup"><span data-stu-id="ea152-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="ea152-152">你的设备将更新为提供此功能的生成。</span><span class="sxs-lookup"><span data-stu-id="ea152-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="ea152-153">你[已连接到 Internet。](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="ea152-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="ea152-154">正确 [配置了 Microsoft Store](hololens-offline.md) 终结点。</span><span class="sxs-lookup"><span data-stu-id="ea152-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="ea152-155">Web 安装程序</span><span class="sxs-lookup"><span data-stu-id="ea152-155">Web Installer</span></span>

<span data-ttu-id="ea152-156">用户可以直接从 Web 服务器安装应用。</span><span class="sxs-lookup"><span data-stu-id="ea152-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="ea152-157">此流将应用安装程序与简单的下载和安装分发方法结合使用。</span><span class="sxs-lookup"><span data-stu-id="ea152-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <span data-ttu-id="ea152-158">如何设置 Web 安装：</span><span class="sxs-lookup"><span data-stu-id="ea152-158">How to set up web install:</span></span>

1. <span data-ttu-id="ea152-159">确保应用已正确配置为安装。</span><span class="sxs-lookup"><span data-stu-id="ea152-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="ea152-160">按照 [以下步骤从网页启用安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。</span><span class="sxs-lookup"><span data-stu-id="ea152-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <span data-ttu-id="ea152-161">最终用户体验：</span><span class="sxs-lookup"><span data-stu-id="ea152-161">End user experience:</span></span>

1. <span data-ttu-id="ea152-162">用户使用之前选择的方法接收证书并安装到设备。</span><span class="sxs-lookup"><span data-stu-id="ea152-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="ea152-163">用户访问通过上述步骤创建的 URL。</span><span class="sxs-lookup"><span data-stu-id="ea152-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="ea152-164">应用现在将安装到设备。</span><span class="sxs-lookup"><span data-stu-id="ea152-164">The app will now install to the device.</span></span> <span data-ttu-id="ea152-165">若要查找应用， **请打开"** 开始"菜单并选择"所有 **应用"** 按钮以查找你的应用。</span><span class="sxs-lookup"><span data-stu-id="ea152-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="ea152-166">有关应用安装程序安装方法疑难解答的更多帮助，请访问 [疑难解答应用安装程序问题](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。</span><span class="sxs-lookup"><span data-stu-id="ea152-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="ea152-167">不支持更新过程中 UI。</span><span class="sxs-lookup"><span data-stu-id="ea152-167">UI during the update process is not supported.</span></span> <span data-ttu-id="ea152-168">因此，此页上的 ShowPrompt [选项](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 和相关选项不受支持。</span><span class="sxs-lookup"><span data-stu-id="ea152-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="ea152-169">示例应用</span><span class="sxs-lookup"><span data-stu-id="ea152-169">Sample Apps</span></span>

<span data-ttu-id="ea152-170">若要使用一些示例应用试用应用安装程序，请查看我们的一些可用示例：</span><span class="sxs-lookup"><span data-stu-id="ea152-170">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="ea152-171">MRTK 示例中心</span><span class="sxs-lookup"><span data-stu-id="ea152-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="ea152-172">Surfaces</span><span class="sxs-lookup"><span data-stu-id="ea152-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="ea152-173">可用于测试的 UWP 示例应用</span><span class="sxs-lookup"><span data-stu-id="ea152-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
