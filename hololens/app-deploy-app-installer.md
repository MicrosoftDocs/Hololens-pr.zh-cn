---
title: 如何通过 HoloLens 2 应用安装程序进行端加载和安装应用
description: 了解如何通过应用程序安装程序和端加载应用程序并对应用程序进行故障排除，以及如何通过 UI 安装应用程序。
keywords: 应用程序管理，应用，hololens，应用安装程序
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
ms.openlocfilehash: 9e413963dbf34dd071fc9603487590065b967ee7
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308356"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="c490b-104">通过应用安装程序在 HoloLens 2 上安装应用</span><span class="sxs-lookup"><span data-stu-id="c490b-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="c490b-105">此功能在 [Windows 全息版20H2 –2020年12月版更新](hololens-release-notes.md)中提供。</span><span class="sxs-lookup"><span data-stu-id="c490b-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="c490b-106">确保你的设备已 [更新](hololens-update-hololens.md) 为使用此功能。</span><span class="sxs-lookup"><span data-stu-id="c490b-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="c490b-107">我们 **添加了新功能 (应用安装程序) ，使你能够在 HoloLens 2 设备上更无缝地安装应用程序** 。</span><span class="sxs-lookup"><span data-stu-id="c490b-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="c490b-108">**默认情况下，对于非托管设备**，此功能将处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="c490b-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="c490b-109">若要防止企业中断，此时将不能 **为托管设备提供** 应用安装程序。</span><span class="sxs-lookup"><span data-stu-id="c490b-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="c490b-110">如果满足以下 **任一** 条件，则将设备视为 "托管"：</span><span class="sxs-lookup"><span data-stu-id="c490b-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="c490b-111">已[注册](hololens-enroll-mdm.md)MDM</span><span class="sxs-lookup"><span data-stu-id="c490b-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="c490b-112">配置了 [预配包](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="c490b-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="c490b-113">用户 [标识](hololens-identity.md) Azure AD</span><span class="sxs-lookup"><span data-stu-id="c490b-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="c490b-114">你现在可以安装应用，而无需启用开发人员模式或使用设备门户。</span><span class="sxs-lookup"><span data-stu-id="c490b-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="c490b-115">通过 USB 或 Microsoft Edge 下载 () Appx 绑定到设备，并在文件资源管理器中导航到 Appx 捆绑，以提示开始安装。</span><span class="sxs-lookup"><span data-stu-id="c490b-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="c490b-116">或者， [通过网页启动安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web)。</span><span class="sxs-lookup"><span data-stu-id="c490b-116">Alternatively, [initiate an install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web).</span></span>  <span data-ttu-id="c490b-117">与使用 MDM 的 LOB 应用部署功能从 Microsoft Store 或旁加载安装的应用一样，需要使用 [签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) 对应用进行数字签名，并且在部署应用之前，必须由 HoloLens 设备 [信任用于签署的证书](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) 。</span><span class="sxs-lookup"><span data-stu-id="c490b-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="c490b-118">要求</span><span class="sxs-lookup"><span data-stu-id="c490b-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="c490b-119">对于你的设备：</span><span class="sxs-lookup"><span data-stu-id="c490b-119">For your devices:</span></span>

<span data-ttu-id="c490b-120">此功能当前在适用于 HoloLens 2 设备的 Windows 全息20H2 版本中可用。</span><span class="sxs-lookup"><span data-stu-id="c490b-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="c490b-121">确保所有使用此方法的设备都已 [更新](hololens-update-hololens.md)。</span><span class="sxs-lookup"><span data-stu-id="c490b-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="c490b-122">对于你的应用：</span><span class="sxs-lookup"><span data-stu-id="c490b-122">For your apps:</span></span>

<span data-ttu-id="c490b-123">应用的解决方案配置必须为 **Master** 或 **Release** ，因为应用安装程序将使用应用商店中的依赖项。</span><span class="sxs-lookup"><span data-stu-id="c490b-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="c490b-124">请参阅 [创建应用包](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c490b-124">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="c490b-125">通过此方法安装的应用必须进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="c490b-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="c490b-126">需要使用证书对应用进行签名。</span><span class="sxs-lookup"><span data-stu-id="c490b-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="c490b-127">你可以从 [MS 可信 CA 列表](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)中获取证书，在这种情况下，你无需执行任何额外操作。</span><span class="sxs-lookup"><span data-stu-id="c490b-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="c490b-128">或者，你可以对自己的证书进行签名，但需要将证书推送到设备上。</span><span class="sxs-lookup"><span data-stu-id="c490b-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="c490b-129">如何[使用签名工具](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)对应用进行签名。</span><span class="sxs-lookup"><span data-stu-id="c490b-129">How to sign apps [using the Sign Tool.](https://docs.microsoft.com/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="c490b-130">**证书选项：**</span><span class="sxs-lookup"><span data-stu-id="c490b-130">**Certificate options:**</span></span>

- [<span data-ttu-id="c490b-131">MS 受信任的 CA 列表</span><span class="sxs-lookup"><span data-stu-id="c490b-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="c490b-132">**选择证书部署方法。**</span><span class="sxs-lookup"><span data-stu-id="c490b-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="c490b-133">[预配包](hololens-provisioning.md) 可应用于本地设备。</span><span class="sxs-lookup"><span data-stu-id="c490b-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="c490b-134">MDM 可用于 [应用具有设备配置的证书](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。</span><span class="sxs-lookup"><span data-stu-id="c490b-134">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="c490b-135">在设备 [证书管理器](certificate-manager.md)上使用。</span><span class="sxs-lookup"><span data-stu-id="c490b-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="c490b-136">安装方法</span><span class="sxs-lookup"><span data-stu-id="c490b-136">Installation method</span></span>

1. <span data-ttu-id="c490b-137">检查设备是否被视为托管设备。</span><span class="sxs-lookup"><span data-stu-id="c490b-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="c490b-138">检查你的 HoloLens 2 设备是否已开机并且已登录。</span><span class="sxs-lookup"><span data-stu-id="c490b-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="c490b-139">在电脑上导航到自定义应用，并将 yourapp 复制到 yourdevicename\Internal Storage\Downloads。</span><span class="sxs-lookup"><span data-stu-id="c490b-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="c490b-140">完成文件复制后，你可能会断开设备连接并稍后完成安装。</span><span class="sxs-lookup"><span data-stu-id="c490b-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="c490b-141">在 HoloLens 2 设备上，打开 " **开始" 菜单**，选择 " **所有应用** "，然后启动 " **文件资源管理器** " 应用。</span><span class="sxs-lookup"><span data-stu-id="c490b-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="c490b-142">导航到 "下载" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="c490b-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="c490b-143">你可能需要在应用程序的左侧面板上选择 " **此设备** "，然后导航到 "下载"。</span><span class="sxs-lookup"><span data-stu-id="c490b-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="c490b-144">选择 yourapp 文件。</span><span class="sxs-lookup"><span data-stu-id="c490b-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="c490b-145">应用程序安装程序将启动。</span><span class="sxs-lookup"><span data-stu-id="c490b-145">The App Installer will launch.</span></span> <span data-ttu-id="c490b-146">选择 " **安装** " 按钮以安装您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c490b-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="c490b-147">安装完成后，安装的应用将自动启动。</span><span class="sxs-lookup"><span data-stu-id="c490b-147">The installed app will automatically launch upon the completion of installing.</span></span>

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="c490b-149">安装疑难解答</span><span class="sxs-lookup"><span data-stu-id="c490b-149">Troubleshooting Installs</span></span>

<span data-ttu-id="c490b-150">如果你的应用程序安装失败，请检查以下内容以进行故障排除：</span><span class="sxs-lookup"><span data-stu-id="c490b-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="c490b-151">您的应用程序可以是主版本或发布版本。</span><span class="sxs-lookup"><span data-stu-id="c490b-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="c490b-152">你的设备已更新到可用此功能的版本。</span><span class="sxs-lookup"><span data-stu-id="c490b-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="c490b-153">你已 [连接到 internet](hololens-network.md)。</span><span class="sxs-lookup"><span data-stu-id="c490b-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="c490b-154">已正确配置 [Microsoft Store 的终结点](hololens-offline.md) 。</span><span class="sxs-lookup"><span data-stu-id="c490b-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="c490b-155">Web 安装程序</span><span class="sxs-lookup"><span data-stu-id="c490b-155">Web Installer</span></span>

<span data-ttu-id="c490b-156">用户可以直接从 web 服务器安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="c490b-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="c490b-157">此流程将应用安装程序与轻松下载和安装分发方法结合使用。</span><span class="sxs-lookup"><span data-stu-id="c490b-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="c490b-158">如何设置 web 安装：</span><span class="sxs-lookup"><span data-stu-id="c490b-158">How to set up web install:</span></span>

1. <span data-ttu-id="c490b-159">确保你的应用已正确配置为安装。</span><span class="sxs-lookup"><span data-stu-id="c490b-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="c490b-160">按照以下 [步骤启用从网页安装](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。</span><span class="sxs-lookup"><span data-stu-id="c490b-160">Follow these [steps to enable install from a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="c490b-161">最终用户体验：</span><span class="sxs-lookup"><span data-stu-id="c490b-161">End user experience:</span></span>

1. <span data-ttu-id="c490b-162">用户使用之前选择的方法接收证书并将其安装到设备。</span><span class="sxs-lookup"><span data-stu-id="c490b-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="c490b-163">用户访问上述步骤中创建的 URL。</span><span class="sxs-lookup"><span data-stu-id="c490b-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="c490b-164">现在，该应用将安装到设备上。</span><span class="sxs-lookup"><span data-stu-id="c490b-164">The app will now install to the device.</span></span> <span data-ttu-id="c490b-165">若要查找应用，请打开 " **开始" 菜单** ，并选择 " **所有应用** " 按钮以查找应用。</span><span class="sxs-lookup"><span data-stu-id="c490b-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="c490b-166">有关应用程序安装程序安装方法疑难解答的更多帮助，请访问 [排查应用程序安装问题](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。</span><span class="sxs-lookup"><span data-stu-id="c490b-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="c490b-167">更新过程中不支持 UI。</span><span class="sxs-lookup"><span data-stu-id="c490b-167">UI during the update process is not supported.</span></span> <span data-ttu-id="c490b-168">因此，不支持 [此页](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 上的 ShowPrompt 选项以及相关选项。</span><span class="sxs-lookup"><span data-stu-id="c490b-168">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="c490b-169">示例应用</span><span class="sxs-lookup"><span data-stu-id="c490b-169">Sample Apps</span></span>

<span data-ttu-id="c490b-170">若要试用具有一些示例应用的应用安装程序，请查看我们的一些可用示例：</span><span class="sxs-lookup"><span data-stu-id="c490b-170">To try the App Installer with some sample apps check out some of our available samples:</span></span>

- [<span data-ttu-id="c490b-171">MRTK 中心示例</span><span class="sxs-lookup"><span data-stu-id="c490b-171">MRTK Examples Hub</span></span>](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/README_ExampleHub.html)
- [<span data-ttu-id="c490b-172">表面</span><span class="sxs-lookup"><span data-stu-id="c490b-172">Surfaces</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/unity/sampleapp-surfaces)
- [<span data-ttu-id="c490b-173">可用于测试的 UWP 示例应用</span><span class="sxs-lookup"><span data-stu-id="c490b-173">UWP Sample Apps that can be used for testing</span></span>](https://github.com/microsoft/Windows-universal-samples/tree/master/Samples)
