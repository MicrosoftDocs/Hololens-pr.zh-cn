---
title: 如何通过 HoloLens 2 应用安装程序加载和安装应用
description: 幻灯片加载并通过 UI 安装应用
keywords: 应用程序管理、应用、hololens、应用安装程序
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
ms.openlocfilehash: 53937881d6569e6aaa17d7e60083381b13502b87
ms.sourcegitcommit: 74e9989240dc0c324df35e8651b2f307f9d42148
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2020
ms.locfileid: "11201366"
---
# <span data-ttu-id="aa153-104">通过应用安装程序在 HoloLens 2 上安装应用</span><span class="sxs-lookup"><span data-stu-id="aa153-104">Install Apps on HoloLens 2 via App Installer</span></span>


<span data-ttu-id="aa153-105">我们正在 \*\* (应用安装程序) 添加新功能，使你能够在 HoloLens 2 设备上更流畅地安装应用程序\*\* 。</span><span class="sxs-lookup"><span data-stu-id="aa153-105">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="aa153-106">默认情况下，此功能将 **在非托管设备上处于打开**状态。</span><span class="sxs-lookup"><span data-stu-id="aa153-106">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="aa153-107">为了防止企业中断，应用安装程序此时将不可 **用于托管设备** 。</span><span class="sxs-lookup"><span data-stu-id="aa153-107">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

> [!NOTE]
> <span data-ttu-id="aa153-108">此功能在 [Windows 全息版 20H2-2020 更新](hololens-release-notes.md)中提供。</span><span class="sxs-lookup"><span data-stu-id="aa153-108">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="aa153-109">确保您的设备已 [更新](hololens-update-hololens.md) 为使用此功能。</span><span class="sxs-lookup"><span data-stu-id="aa153-109">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="aa153-110">我们已 **添加了 (应用安装程序) 的新功能，使你能够在 HoloLens 2 设备上更流畅地安装应用程序** 。</span><span class="sxs-lookup"><span data-stu-id="aa153-110">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="aa153-111">默认情况下，此功能将 **在非托管设备上处于打开**状态。</span><span class="sxs-lookup"><span data-stu-id="aa153-111">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="aa153-112">为了防止企业中断，应用安装程序此时将不可 **用于托管设备** 。</span><span class="sxs-lookup"><span data-stu-id="aa153-112">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="aa153-113">如果以下 **任何** 条件成立，设备将被视为 "托管"：</span><span class="sxs-lookup"><span data-stu-id="aa153-113">A device is considered “managed” if **any** of the following are true:</span></span>
- <span data-ttu-id="aa153-114">MDM 已 [注册](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="aa153-114">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="aa153-115">配置了 [预配包](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="aa153-115">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="aa153-116">用户 [标识](hololens-identity.md) 为 AAD</span><span class="sxs-lookup"><span data-stu-id="aa153-116">User [Identity](hololens-identity.md) is AAD</span></span>

<span data-ttu-id="aa153-117">现在，你可以安装应用，而无需启用开发人员模式或使用 Device Portal。</span><span class="sxs-lookup"><span data-stu-id="aa153-117">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="aa153-118">只需通过 USB 或边缘) 将 (下载到你的设备，然后在文件资源管理器中导航到 Appx 捆绑系统，系统会提示你启动安装。</span><span class="sxs-lookup"><span data-stu-id="aa153-118">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="aa153-119">或者， [从网页启动安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。</span><span class="sxs-lookup"><span data-stu-id="aa153-119">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="aa153-120">与使用 MDM 的 LOB 应用部署功能从 Microsoft Store 或旁加载安装的应用一样，应用需要使用 [签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 进行数字签名，并且 [用于签名的证书必须受](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) HoloLens 设备信任才能部署应用。</span><span class="sxs-lookup"><span data-stu-id="aa153-120">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>   

## <span data-ttu-id="aa153-121">要求</span><span class="sxs-lookup"><span data-stu-id="aa153-121">Requirements</span></span>

### <span data-ttu-id="aa153-122">对于您的设备：</span><span class="sxs-lookup"><span data-stu-id="aa153-122">For your devices:</span></span> 
<span data-ttu-id="aa153-123">当前在适用于 HoloLens 2 设备的 [Windows 预览体验成员内部版本](hololens-insider.md) 中 avalible。</span><span class="sxs-lookup"><span data-stu-id="aa153-123">This is currently avalible in [Windows Insider builds](hololens-insider.md) for HoloLens 2 devices.</span></span> <span data-ttu-id="aa153-124">请确保使用此方法的任何设备均 [已更新](hololens-update-hololens.md)。</span><span class="sxs-lookup"><span data-stu-id="aa153-124">Please ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span> 

### <span data-ttu-id="aa153-125">对于你的应用：</span><span class="sxs-lookup"><span data-stu-id="aa153-125">For your apps:</span></span> 
<span data-ttu-id="aa153-126">你的应用的解决方案配置必须是 " **主** " 或 " **发布** "，因为应用安装程序将使用应用商店中的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="aa153-126">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="aa153-127">查看有关 [创建应用包](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="aa153-127">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="aa153-128">通过此方法安装的应用必须经过数字签名。</span><span class="sxs-lookup"><span data-stu-id="aa153-128">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="aa153-129">您需要使用证书对应用进行签名。</span><span class="sxs-lookup"><span data-stu-id="aa153-129">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="aa153-130">你可以从 [MS 受信任 CA 列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)中获取证书，在这种情况下，你无需执行任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="aa153-130">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="aa153-131">或者，你可以对自己的证书进行签名，但需要将证书推送到设备上。</span><span class="sxs-lookup"><span data-stu-id="aa153-131">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span> 
- <span data-ttu-id="aa153-132">如何[使用签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)对应用进行签名。</span><span class="sxs-lookup"><span data-stu-id="aa153-132">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="aa153-133">证书选项：</span><span class="sxs-lookup"><span data-stu-id="aa153-133">Certificate options:</span></span>** 
- [<span data-ttu-id="aa153-134">MS 受信任的 CA 列表</span><span class="sxs-lookup"><span data-stu-id="aa153-134">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="aa153-135">选择证书部署方法。</span><span class="sxs-lookup"><span data-stu-id="aa153-135">Pick a certificate deployment method.</span></span>** 
- <span data-ttu-id="aa153-136">[预配程序包](hololens-provisioning.md) 可应用于本地设备。</span><span class="sxs-lookup"><span data-stu-id="aa153-136">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="aa153-137">可以使用 MDM [将证书应用于设备配置](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。</span><span class="sxs-lookup"><span data-stu-id="aa153-137">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="aa153-138">使用 "设备 [证书管理器](certificate-manager.md)"。</span><span class="sxs-lookup"><span data-stu-id="aa153-138">Use the on device [Certificate Manager](certificate-manager.md).</span></span> 

## <span data-ttu-id="aa153-139">安装方法</span><span class="sxs-lookup"><span data-stu-id="aa153-139">Installation method</span></span>

1.  <span data-ttu-id="aa153-140">确保您的设备不被视为托管设备。</span><span class="sxs-lookup"><span data-stu-id="aa153-140">Ensure that your device is not considered managed.</span></span>
1.  <span data-ttu-id="aa153-141">确保 HoloLens 2 设备已开机且已登录。</span><span class="sxs-lookup"><span data-stu-id="aa153-141">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="aa153-142">在你的电脑上导航到你的自定义应用，并将 yourapp 复制到 yourdevicename\Internal Storage\Downloads。</span><span class="sxs-lookup"><span data-stu-id="aa153-142">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="aa153-143">完成文件复制后，您可能会断开您的设备并在以后完成安装。</span><span class="sxs-lookup"><span data-stu-id="aa153-143">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="aa153-144">从 HoloLens 2 设备打开 " **开始" 菜单**，选择 " **所有应用** "，然后启动 " **文件资源管理器** " 应用。</span><span class="sxs-lookup"><span data-stu-id="aa153-144">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="aa153-145">导航到 "下载" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa153-145">Navigate to the Downloads folder.</span></span> <span data-ttu-id="aa153-146">你可能需要在应用的左侧面板上，选择 " **此设备** "，然后导航到 "下载"。</span><span class="sxs-lookup"><span data-stu-id="aa153-146">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="aa153-147">选择 yourapp 文件。</span><span class="sxs-lookup"><span data-stu-id="aa153-147">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="aa153-148">应用安装程序将启动。</span><span class="sxs-lookup"><span data-stu-id="aa153-148">The App Installer will launch.</span></span> <span data-ttu-id="aa153-149">选择 " **安装** " 按钮以安装你的应用。</span><span class="sxs-lookup"><span data-stu-id="aa153-149">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="aa153-150">已安装的应用将在安装完成后自动启动。</span><span class="sxs-lookup"><span data-stu-id="aa153-150">The installed app will automatically launch upon the completion of installing.</span></span> 

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="aa153-152">安装疑难解答</span><span class="sxs-lookup"><span data-stu-id="aa153-152">Troubleshooting Installs</span></span>
<span data-ttu-id="aa153-153">如果你的应用无法安装，请检查以下内容：</span><span class="sxs-lookup"><span data-stu-id="aa153-153">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="aa153-154">你的应用是 "主" 或 "发布" 内部版本。</span><span class="sxs-lookup"><span data-stu-id="aa153-154">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="aa153-155">你的设备已更新为可使用此功能的版本。</span><span class="sxs-lookup"><span data-stu-id="aa153-155">Your device is updated to a build on which this feature is available.</span></span> 
-   <span data-ttu-id="aa153-156">您已 [连接到 internet](hololens-network.md)。</span><span class="sxs-lookup"><span data-stu-id="aa153-156">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="aa153-157">已正确配置 [Microsoft Store 的终结点](hololens-offline.md) 。</span><span class="sxs-lookup"><span data-stu-id="aa153-157">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="aa153-158">Web 安装程序</span><span class="sxs-lookup"><span data-stu-id="aa153-158">Web Installer</span></span>

<span data-ttu-id="aa153-159">用户可以直接从 web 服务器安装应用。</span><span class="sxs-lookup"><span data-stu-id="aa153-159">Users can install an app directly from a web server.</span></span> <span data-ttu-id="aa153-160">这会将应用安装程序与轻松下载和安装分发方法结合使用。</span><span class="sxs-lookup"><span data-stu-id="aa153-160">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

### <span data-ttu-id="aa153-161">如何设置 web 安装：</span><span class="sxs-lookup"><span data-stu-id="aa153-161">How to set up web install:</span></span>
1.  <span data-ttu-id="aa153-162">确保你的应用已正确配置为安装。</span><span class="sxs-lookup"><span data-stu-id="aa153-162">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="aa153-163">请按照以下 [步骤在网页上启用此操作](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。</span><span class="sxs-lookup"><span data-stu-id="aa153-163">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 

### <span data-ttu-id="aa153-164">最终用户体验：</span><span class="sxs-lookup"><span data-stu-id="aa153-164">End user experience:</span></span>
1. <span data-ttu-id="aa153-165">用户使用之前选择的方法接收和安装设备证书。</span><span class="sxs-lookup"><span data-stu-id="aa153-165">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1. <span data-ttu-id="aa153-166">用户访问上述步骤中创建的 URL。</span><span class="sxs-lookup"><span data-stu-id="aa153-166">User visits the URL created from the step above.</span></span>

<span data-ttu-id="aa153-167">该应用现在将安装到设备。</span><span class="sxs-lookup"><span data-stu-id="aa153-167">The app will now install to the device.</span></span> <span data-ttu-id="aa153-168">若要查找应用，请打开 " **开始" 菜单** ，然后选择 " **所有应用** " 按钮以查找你的应用。</span><span class="sxs-lookup"><span data-stu-id="aa153-168">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="aa153-169">有关此安装方法的疑难解答帮助，请访问 [应用安装程序问题疑难解答](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。</span><span class="sxs-lookup"><span data-stu-id="aa153-169">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="aa153-170">更新过程中不支持 UI。</span><span class="sxs-lookup"><span data-stu-id="aa153-170">UI during the update process is not supported.</span></span> <span data-ttu-id="aa153-171">因此，不支持 [此页面](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 上的 ShowPrompt 选项和相关选项。</span><span class="sxs-lookup"><span data-stu-id="aa153-171">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="aa153-172">示例应用</span><span class="sxs-lookup"><span data-stu-id="aa153-172">Sample Apps</span></span>

<span data-ttu-id="aa153-173">如果你想要使用某些示例应用尝试此操作，请查看我们的一些可用示例：</span><span class="sxs-lookup"><span data-stu-id="aa153-173">If you'd like to try this out with some sample apps please check out some of our available samples:</span></span>
- [<span data-ttu-id="aa153-174">MRTK 示例中心</span><span class="sxs-lookup"><span data-stu-id="aa153-174">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="aa153-175">图</span><span class="sxs-lookup"><span data-stu-id="aa153-175">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="aa153-176">可用于测试的 UWP 示例应用</span><span class="sxs-lookup"><span data-stu-id="aa153-176">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
