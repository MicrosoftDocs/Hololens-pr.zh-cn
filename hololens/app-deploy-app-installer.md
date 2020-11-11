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
ms.openlocfilehash: eba1fd00215ef197f9e32949e958bdbded089d6d
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "11162896"
---
# <span data-ttu-id="75d2f-104">通过应用安装程序在 HoloLens 2 上安装应用</span><span class="sxs-lookup"><span data-stu-id="75d2f-104">Install Apps on HoloLens 2 via App Installer</span></span>


<span data-ttu-id="75d2f-105">我们将在 Windows 全息版20H2 更新后立即发布应用安装程序功能。</span><span class="sxs-lookup"><span data-stu-id="75d2f-105">We will ship the app installer capability soon after our Windows Holographic, version 20H2 update.</span></span> <span data-ttu-id="75d2f-106">我们正在 \*\* (应用安装程序) 添加新功能，使你能够在 HoloLens 2 设备上更流畅地安装应用程序\*\* 。</span><span class="sxs-lookup"><span data-stu-id="75d2f-106">We are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="75d2f-107">默认情况下，此功能将 **在非托管设备上处于打开**状态。</span><span class="sxs-lookup"><span data-stu-id="75d2f-107">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="75d2f-108">为了防止企业中断，应用安装程序此时将不可 **用于托管设备** 。</span><span class="sxs-lookup"><span data-stu-id="75d2f-108">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="75d2f-109">此功能目前仅适用于 Windows 预览体验成员版本。</span><span class="sxs-lookup"><span data-stu-id="75d2f-109">This feature is currently only avalible in Windows Insider builds.</span></span> <span data-ttu-id="75d2f-110">[了解有关如何在 Windows 预览体验计划内部版本中注册的详细信息](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="75d2f-110">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

<span data-ttu-id="75d2f-111">在我们的 Windows 预览体验计划版本中，我们将 **添加 (应用安装程序) 的新功能，让你能够在 HoloLens 2 设备上更流畅地安装应用程序** 。</span><span class="sxs-lookup"><span data-stu-id="75d2f-111">In our Windows Insider release, we are **adding a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="75d2f-112">默认情况下，此功能将 **在非托管设备上处于打开**状态。</span><span class="sxs-lookup"><span data-stu-id="75d2f-112">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="75d2f-113">为了防止企业中断，应用安装程序此时将不可 **用于托管设备** 。</span><span class="sxs-lookup"><span data-stu-id="75d2f-113">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="75d2f-114">如果以下 **任何** 条件成立，设备将被视为 "托管"：</span><span class="sxs-lookup"><span data-stu-id="75d2f-114">A device is considered “managed” if **any** of the following are true:</span></span>
- <span data-ttu-id="75d2f-115">MDM 已 [注册](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="75d2f-115">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="75d2f-116">配置了 [预配包](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="75d2f-116">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="75d2f-117">用户 [标识](hololens-identity.md) 为 AAD</span><span class="sxs-lookup"><span data-stu-id="75d2f-117">User [Identity](hololens-identity.md) is AAD</span></span>

<span data-ttu-id="75d2f-118">现在，你可以安装应用，而无需启用开发人员模式或使用 Device Portal。</span><span class="sxs-lookup"><span data-stu-id="75d2f-118">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="75d2f-119">只需通过 USB 或边缘) 将 (下载到你的设备，然后在文件资源管理器中导航到 Appx 捆绑系统，系统会提示你启动安装。</span><span class="sxs-lookup"><span data-stu-id="75d2f-119">Simply download (over USB or through Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="75d2f-120">或者， [从网页启动安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。</span><span class="sxs-lookup"><span data-stu-id="75d2f-120">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="75d2f-121">与使用 MDM 的 LOB 应用部署功能从 Microsoft Store 或旁加载安装的应用一样，应用需要使用 [签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 进行数字签名，并且 [用于签名的证书必须受](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) HoloLens 设备信任才能部署应用。</span><span class="sxs-lookup"><span data-stu-id="75d2f-121">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>   

## <span data-ttu-id="75d2f-122">要求</span><span class="sxs-lookup"><span data-stu-id="75d2f-122">Requirements</span></span>

### <span data-ttu-id="75d2f-123">对于您的设备：</span><span class="sxs-lookup"><span data-stu-id="75d2f-123">For your devices:</span></span> 
<span data-ttu-id="75d2f-124">当前在适用于 HoloLens 2 设备的 [Windows 预览体验成员内部版本](hololens-insider.md) 中 avalible。</span><span class="sxs-lookup"><span data-stu-id="75d2f-124">This is currently avalible in [Windows Insider builds](hololens-insider.md) for HoloLens 2 devices.</span></span> <span data-ttu-id="75d2f-125">请确保使用此方法的任何设备均 [已更新](hololens-update-hololens.md)。</span><span class="sxs-lookup"><span data-stu-id="75d2f-125">Please ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span> 

### <span data-ttu-id="75d2f-126">对于你的应用：</span><span class="sxs-lookup"><span data-stu-id="75d2f-126">For your apps:</span></span> 
<span data-ttu-id="75d2f-127">你的应用的解决方案配置必须是 " **主** " 或 " **发布** "，因为应用安装程序将使用应用商店中的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="75d2f-127">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="75d2f-128">查看有关 [创建应用包](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="75d2f-128">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="75d2f-129">通过此方法安装的应用必须经过数字签名。</span><span class="sxs-lookup"><span data-stu-id="75d2f-129">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="75d2f-130">您需要使用证书对应用进行签名。</span><span class="sxs-lookup"><span data-stu-id="75d2f-130">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="75d2f-131">你可以从 [MS 受信任 CA 列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)中获取证书，在这种情况下，你无需执行任何其他操作。</span><span class="sxs-lookup"><span data-stu-id="75d2f-131">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any additional action.</span></span> <span data-ttu-id="75d2f-132">或者，你可以对自己的证书进行签名，但需要将证书推送到设备上。</span><span class="sxs-lookup"><span data-stu-id="75d2f-132">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span> 
- <span data-ttu-id="75d2f-133">如何[使用签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)对应用进行签名。</span><span class="sxs-lookup"><span data-stu-id="75d2f-133">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

**<span data-ttu-id="75d2f-134">证书选项：</span><span class="sxs-lookup"><span data-stu-id="75d2f-134">Certificate options:</span></span>** 
- [<span data-ttu-id="75d2f-135">MS 受信任的 CA 列表</span><span class="sxs-lookup"><span data-stu-id="75d2f-135">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

**<span data-ttu-id="75d2f-136">选择证书部署方法。</span><span class="sxs-lookup"><span data-stu-id="75d2f-136">Pick a certificate deployment method.</span></span>** 
- <span data-ttu-id="75d2f-137">[预配程序包](hololens-provisioning.md) 可应用于本地设备。</span><span class="sxs-lookup"><span data-stu-id="75d2f-137">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="75d2f-138">可以使用 MDM [将证书应用于设备配置](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。</span><span class="sxs-lookup"><span data-stu-id="75d2f-138">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="75d2f-139">使用 "设备 [证书管理器](certificate-manager.md)"。</span><span class="sxs-lookup"><span data-stu-id="75d2f-139">Use the on device [Certificate Manager](certificate-manager.md).</span></span> 

## <span data-ttu-id="75d2f-140">安装方法</span><span class="sxs-lookup"><span data-stu-id="75d2f-140">Installation method</span></span>

1.  <span data-ttu-id="75d2f-141">确保您的设备不被视为托管设备。</span><span class="sxs-lookup"><span data-stu-id="75d2f-141">Ensure that your device is not considered managed.</span></span>
1.  <span data-ttu-id="75d2f-142">确保 HoloLens 2 设备已开机且已登录。</span><span class="sxs-lookup"><span data-stu-id="75d2f-142">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="75d2f-143">在你的电脑上导航到你的自定义应用，并将 yourapp 复制到 yourdevicename\Internal Storage\Downloads。</span><span class="sxs-lookup"><span data-stu-id="75d2f-143">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="75d2f-144">完成文件复制后，您可能会断开您的设备并在以后完成安装。</span><span class="sxs-lookup"><span data-stu-id="75d2f-144">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="75d2f-145">从 HoloLens 2 设备打开 " **开始" 菜单**，选择 " **所有应用** "，然后启动 " **文件资源管理器** " 应用。</span><span class="sxs-lookup"><span data-stu-id="75d2f-145">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="75d2f-146">导航到 "下载" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="75d2f-146">Navigate to the Downloads folder.</span></span> <span data-ttu-id="75d2f-147">你可能需要在应用的左侧面板上，选择 " **此设备** "，然后导航到 "下载"。</span><span class="sxs-lookup"><span data-stu-id="75d2f-147">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="75d2f-148">选择 yourapp 文件。</span><span class="sxs-lookup"><span data-stu-id="75d2f-148">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="75d2f-149">应用安装程序将启动。</span><span class="sxs-lookup"><span data-stu-id="75d2f-149">The App Installer will launch.</span></span> <span data-ttu-id="75d2f-150">选择 " **安装** " 按钮以安装你的应用。</span><span class="sxs-lookup"><span data-stu-id="75d2f-150">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="75d2f-151">已安装的应用将在安装完成后自动启动。</span><span class="sxs-lookup"><span data-stu-id="75d2f-151">The installed app will automatically launch upon the completion of installing.</span></span> 

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

### <span data-ttu-id="75d2f-153">安装疑难解答</span><span class="sxs-lookup"><span data-stu-id="75d2f-153">Troubleshooting Installs</span></span>
<span data-ttu-id="75d2f-154">如果你的应用无法安装，请检查以下内容：</span><span class="sxs-lookup"><span data-stu-id="75d2f-154">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="75d2f-155">你的应用是 "主" 或 "发布" 内部版本。</span><span class="sxs-lookup"><span data-stu-id="75d2f-155">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="75d2f-156">你的设备已更新为可使用此功能的版本。</span><span class="sxs-lookup"><span data-stu-id="75d2f-156">Your device is updated to a build on which this feature is available.</span></span> 
-   <span data-ttu-id="75d2f-157">您已 [连接到 internet](hololens-network.md)。</span><span class="sxs-lookup"><span data-stu-id="75d2f-157">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="75d2f-158">已正确配置 [Microsoft Store 的终结点](hololens-offline.md) 。</span><span class="sxs-lookup"><span data-stu-id="75d2f-158">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <span data-ttu-id="75d2f-159">Web 安装程序</span><span class="sxs-lookup"><span data-stu-id="75d2f-159">Web Installer</span></span>

<span data-ttu-id="75d2f-160">用户可以直接从 web 服务器安装应用。</span><span class="sxs-lookup"><span data-stu-id="75d2f-160">Users can install an app directly from a web server.</span></span> <span data-ttu-id="75d2f-161">这会将应用安装程序与轻松下载和安装分发方法结合使用。</span><span class="sxs-lookup"><span data-stu-id="75d2f-161">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

### <span data-ttu-id="75d2f-162">如何设置 web 安装：</span><span class="sxs-lookup"><span data-stu-id="75d2f-162">How to set up web install:</span></span>
1.  <span data-ttu-id="75d2f-163">确保你的应用已正确配置为安装。</span><span class="sxs-lookup"><span data-stu-id="75d2f-163">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="75d2f-164">请按照以下 [步骤在网页上启用此操作](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。</span><span class="sxs-lookup"><span data-stu-id="75d2f-164">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 

### <span data-ttu-id="75d2f-165">最终用户体验：</span><span class="sxs-lookup"><span data-stu-id="75d2f-165">End user experience:</span></span>
1. <span data-ttu-id="75d2f-166">用户使用之前选择的方法接收和安装设备证书。</span><span class="sxs-lookup"><span data-stu-id="75d2f-166">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1. <span data-ttu-id="75d2f-167">用户访问上述步骤中创建的 URL。</span><span class="sxs-lookup"><span data-stu-id="75d2f-167">User visits the URL created from the step above.</span></span>

<span data-ttu-id="75d2f-168">该应用现在将安装到设备。</span><span class="sxs-lookup"><span data-stu-id="75d2f-168">The app will now install to the device.</span></span> <span data-ttu-id="75d2f-169">若要查找应用，请打开 " **开始" 菜单** ，然后选择 " **所有应用** " 按钮以查找你的应用。</span><span class="sxs-lookup"><span data-stu-id="75d2f-169">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="75d2f-170">有关此安装方法的疑难解答帮助，请访问 [应用安装程序问题疑难解答](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。</span><span class="sxs-lookup"><span data-stu-id="75d2f-170">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="75d2f-171">更新过程中不支持 UI。</span><span class="sxs-lookup"><span data-stu-id="75d2f-171">UI during the update process is not supported.</span></span> <span data-ttu-id="75d2f-172">因此，不支持 [此页面](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 上的 ShowPrompt 选项和相关选项。</span><span class="sxs-lookup"><span data-stu-id="75d2f-172">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <span data-ttu-id="75d2f-173">示例应用</span><span class="sxs-lookup"><span data-stu-id="75d2f-173">Sample Apps</span></span>

<span data-ttu-id="75d2f-174">如果你想要使用某些示例应用尝试此操作，请查看我们的一些可用示例：</span><span class="sxs-lookup"><span data-stu-id="75d2f-174">If you'd like to try this out with some sample apps please check out some of our available samples:</span></span>
- [<span data-ttu-id="75d2f-175">MRTK 示例中心</span><span class="sxs-lookup"><span data-stu-id="75d2f-175">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="75d2f-176">图</span><span class="sxs-lookup"><span data-stu-id="75d2f-176">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="75d2f-177">可用于测试的 UWP 示例应用</span><span class="sxs-lookup"><span data-stu-id="75d2f-177">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
