---
title: 如何旁加载并安装应用HoloLens 2 应用安装程序
description: 了解如何使用应用安装程序安装和排查应用问题，以及如何通过 UI 旁加载和安装应用。
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
ms.openlocfilehash: 8f236ee27903069b65d3ded8eb7a1f37c65f535e
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635579"
---
# <a name="install-apps-on-hololens-2-via-app-installer"></a><span data-ttu-id="6862f-104">通过 应用安装程序 在 HoloLens 2 安装应用</span><span class="sxs-lookup"><span data-stu-id="6862f-104">Install Apps on HoloLens 2 via App Installer</span></span>

> [!NOTE]
> <span data-ttu-id="6862f-105">此功能在 Holographic 版本[20H2 Windows 2020 年 12](hololens-release-notes.md)月更新中提供。</span><span class="sxs-lookup"><span data-stu-id="6862f-105">This feature was made available in [Windows Holographic, version 20H2 – December 2020 Update](hololens-release-notes.md).</span></span> <span data-ttu-id="6862f-106">确保设备 [已更新为](hololens-update-hololens.md) 使用此功能。</span><span class="sxs-lookup"><span data-stu-id="6862f-106">Ensure your device is [updated](hololens-update-hololens.md) to use this feature.</span></span>

<span data-ttu-id="6862f-107">我们 **添加了新功能 (应用安装程序) ，** 让你能够更无缝地在 HoloLens 2 设备上安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="6862f-107">We have **added a new capability (App Installer) to allow you to install applications more seamlessly** on your HoloLens 2 devices.</span></span> <span data-ttu-id="6862f-108">对于非 **托管设备，此功能默认为打开状态**。</span><span class="sxs-lookup"><span data-stu-id="6862f-108">The feature will be **on by default for unmanaged devices**.</span></span> <span data-ttu-id="6862f-109">为了防止企业中断，应用安装程序 **目前不适用于托管** 设备。</span><span class="sxs-lookup"><span data-stu-id="6862f-109">To prevent disruption to enterprises, app installer will be **not be available for managed devices** at this time.</span></span>  

<span data-ttu-id="6862f-110">如果以下任一情况 **成立，则** 设备被视为"托管"设备：</span><span class="sxs-lookup"><span data-stu-id="6862f-110">A device is considered “managed” if **any** of the following are true:</span></span>

- <span data-ttu-id="6862f-111">MDM [已注册](hololens-enroll-mdm.md)</span><span class="sxs-lookup"><span data-stu-id="6862f-111">MDM [Enrolled](hololens-enroll-mdm.md)</span></span>
- <span data-ttu-id="6862f-112">配置了 [预配包](hololens-provisioning.md)</span><span class="sxs-lookup"><span data-stu-id="6862f-112">Configured with [provisioning package](hololens-provisioning.md)</span></span>
- <span data-ttu-id="6862f-113">用户 [标识](hololens-identity.md) Azure AD</span><span class="sxs-lookup"><span data-stu-id="6862f-113">User [Identity](hololens-identity.md) is Azure AD</span></span>

<span data-ttu-id="6862f-114">现在可以安装应用，而无需启用开发人员模式或设备门户。</span><span class="sxs-lookup"><span data-stu-id="6862f-114">You are now able to install Apps without needing to enable Developer Mode or using Device Portal.</span></span>  <span data-ttu-id="6862f-115">通过 USB Microsoft Edge) Appx 捆绑包将 (下载到设备，然后导航到 文件资源管理器 中的 Appx 捆绑包，以提示你启动安装。</span><span class="sxs-lookup"><span data-stu-id="6862f-115">Download (over USB or through Microsoft Edge) the Appx Bundle to your device and navigate to the Appx Bundle in the File Explorer to be prompted to kick off the installation.</span></span>  <span data-ttu-id="6862f-116">或者， [从网页 启动安装](/windows/msix/app-installer/installing-windows10-apps-web)。</span><span class="sxs-lookup"><span data-stu-id="6862f-116">Alternatively, [initiate an install from a web page](/windows/msix/app-installer/installing-windows10-apps-web).</span></span> <span data-ttu-id="6862f-117">与从 Microsoft Store 安装的应用或使用 MDM 的 LOB 应用部署功能旁加载的应用一样，应用需要使用签名工具进行数字签名[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)，并且用于签名[](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations)的证书必须受 HoloLens 设备信任，然后才能部署应用。</span><span class="sxs-lookup"><span data-stu-id="6862f-117">Just like apps you install from the Microsoft Store or sideload using MDM’s LOB App deployment capability, apps need to be digitally signed with the [Sign Tool](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool) and the [certificate used to sign must be trusted](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool#security-considerations) by the HoloLens device before the app can be deployed.</span></span>

## <a name="requirements"></a><span data-ttu-id="6862f-118">要求</span><span class="sxs-lookup"><span data-stu-id="6862f-118">Requirements</span></span>

### <a name="for-your-devices"></a><span data-ttu-id="6862f-119">对于设备：</span><span class="sxs-lookup"><span data-stu-id="6862f-119">For your devices:</span></span>

<span data-ttu-id="6862f-120">此功能当前在适用于Windows的 Holographic 20H2 内部HoloLens 2提供。</span><span class="sxs-lookup"><span data-stu-id="6862f-120">This feature is currently available in Windows Holographic 20H2 builds for HoloLens 2 devices.</span></span> <span data-ttu-id="6862f-121">确保已更新使用此方法的任何 [设备](hololens-update-hololens.md)。</span><span class="sxs-lookup"><span data-stu-id="6862f-121">Ensure any devices using this method are [updated](hololens-update-hololens.md).</span></span>

### <a name="for-your-apps"></a><span data-ttu-id="6862f-122">对于应用：</span><span class="sxs-lookup"><span data-stu-id="6862f-122">For your apps:</span></span>

<span data-ttu-id="6862f-123">应用的"解决方案配置"必须是 **"主**"或"发布"，应用安装程序将使用存储中的依赖项。</span><span class="sxs-lookup"><span data-stu-id="6862f-123">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="6862f-124">详细了解如何 [创建应用包](/windows/msix/app-installer/create-appinstallerfile-vs)。</span><span class="sxs-lookup"><span data-stu-id="6862f-124">See more about [creating app packages](/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

<span data-ttu-id="6862f-125">通过此方法安装的应用必须进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="6862f-125">Apps that are installed via this method must be digitally signed.</span></span> <span data-ttu-id="6862f-126">你需要使用证书对应用进行签名。</span><span class="sxs-lookup"><span data-stu-id="6862f-126">You'll need to use a certificate to sign the app.</span></span> <span data-ttu-id="6862f-127">可以从 MS 受信任的 CA 列表 [获取](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)证书，在这种情况下，无需执行任何额外操作。</span><span class="sxs-lookup"><span data-stu-id="6862f-127">You can either get a certificate from the [MS Trusted CA List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT), in which case you won't need to take any extra action.</span></span> <span data-ttu-id="6862f-128">也可以对自己的证书进行签名，但需要将证书推送到设备上。</span><span class="sxs-lookup"><span data-stu-id="6862f-128">Or you can sign your own certificate however that certificate will need to be pushed onto the device.</span></span>

- <span data-ttu-id="6862f-129">如何使用签名 [工具对应用进行签名。](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span><span class="sxs-lookup"><span data-stu-id="6862f-129">How to sign apps [using the Sign Tool.](/windows/win32/appxpkg/how-to-sign-a-package-using-signtool)</span></span>

<span data-ttu-id="6862f-130">**证书选项：**</span><span class="sxs-lookup"><span data-stu-id="6862f-130">**Certificate options:**</span></span>

- [<span data-ttu-id="6862f-131">MS 受信任的 CA 列表</span><span class="sxs-lookup"><span data-stu-id="6862f-131">MS Trusted CA List</span></span>](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)

<span data-ttu-id="6862f-132">**选择证书部署方法。**</span><span class="sxs-lookup"><span data-stu-id="6862f-132">**Pick a certificate deployment method.**</span></span>

- <span data-ttu-id="6862f-133">[预配包](hololens-provisioning.md) 可应用于本地设备。</span><span class="sxs-lookup"><span data-stu-id="6862f-133">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
- <span data-ttu-id="6862f-134">MDM 可用于应用 [具有设备配置的证书](/mem/intune/protect/certificates-configure)。</span><span class="sxs-lookup"><span data-stu-id="6862f-134">MDM can be used to [apply certificates with device configurations](/mem/intune/protect/certificates-configure).</span></span>
- <span data-ttu-id="6862f-135">使用设备证书 [管理器 上的](certificate-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="6862f-135">Use the on device [Certificate Manager](certificate-manager.md).</span></span>

## <a name="installation-method"></a><span data-ttu-id="6862f-136">安装方法</span><span class="sxs-lookup"><span data-stu-id="6862f-136">Installation method</span></span>

1. <span data-ttu-id="6862f-137">检查设备是否被视为托管设备。</span><span class="sxs-lookup"><span data-stu-id="6862f-137">Check that your device is not considered managed.</span></span>
1. <span data-ttu-id="6862f-138">检查你的HoloLens 2设备是否已打开且已登录。</span><span class="sxs-lookup"><span data-stu-id="6862f-138">Check that your HoloLens 2 device is powered on and you are signed in.</span></span>
1. <span data-ttu-id="6862f-139">在电脑上导航到自定义应用，将 yourapp.appxbundle 复制到 yourdevicename\Internal 存储\Downloads。</span><span class="sxs-lookup"><span data-stu-id="6862f-139">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span>
    <span data-ttu-id="6862f-140">复制完文件后，可以断开设备连接，并稍后完成安装。</span><span class="sxs-lookup"><span data-stu-id="6862f-140">After you finish copying your file, you may disconnect your device and finish the install later.</span></span>
1. <span data-ttu-id="6862f-141">从HoloLens 2打开"开始 **"菜单**，选择"所有 **应用**"**并** 启动文件资源管理器应用。</span><span class="sxs-lookup"><span data-stu-id="6862f-141">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1. <span data-ttu-id="6862f-142">导航到"下载"文件夹。</span><span class="sxs-lookup"><span data-stu-id="6862f-142">Navigate to the Downloads folder.</span></span> <span data-ttu-id="6862f-143">可能需要先在应用的左侧面板中选择"此 **设备** "，然后导航到"下载"。</span><span class="sxs-lookup"><span data-stu-id="6862f-143">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1. <span data-ttu-id="6862f-144">选择 yourapp.appxbundle 文件。</span><span class="sxs-lookup"><span data-stu-id="6862f-144">Select the yourapp.appxbundle file.</span></span>
1. <span data-ttu-id="6862f-145">系统应用安装程序启动。</span><span class="sxs-lookup"><span data-stu-id="6862f-145">The App Installer will launch.</span></span> <span data-ttu-id="6862f-146">选择" **安装** "按钮以安装应用。</span><span class="sxs-lookup"><span data-stu-id="6862f-146">Select the **Install** button to install your app.</span></span>

<span data-ttu-id="6862f-147">安装完成后，已安装的应用将自动启动。</span><span class="sxs-lookup"><span data-stu-id="6862f-147">The installed app will automatically launch upon the completion of installing.</span></span>

![通过 应用安装程序 安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

### <a name="troubleshooting-installs"></a><span data-ttu-id="6862f-149">安装疑难解答</span><span class="sxs-lookup"><span data-stu-id="6862f-149">Troubleshooting Installs</span></span>

<span data-ttu-id="6862f-150">如果应用安装失败，请检查以下各项以进行故障排除：</span><span class="sxs-lookup"><span data-stu-id="6862f-150">If your app failed to install,  check the following to troubleshoot:</span></span>

- <span data-ttu-id="6862f-151">应用是主版本或发布版本。</span><span class="sxs-lookup"><span data-stu-id="6862f-151">Your app is either a Master or Release build.</span></span>
- <span data-ttu-id="6862f-152">设备将更新为提供此功能的生成。</span><span class="sxs-lookup"><span data-stu-id="6862f-152">Your device is updated to a build on which this feature is available.</span></span>
- <span data-ttu-id="6862f-153">已[连接到 Internet。](hololens-network.md)</span><span class="sxs-lookup"><span data-stu-id="6862f-153">You are [connected to the internet](hololens-network.md).</span></span>
- <span data-ttu-id="6862f-154">[已正确配置Microsoft Store](hololens-offline.md)终结点。</span><span class="sxs-lookup"><span data-stu-id="6862f-154">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  

## <a name="web-installer"></a><span data-ttu-id="6862f-155">Web 安装程序</span><span class="sxs-lookup"><span data-stu-id="6862f-155">Web Installer</span></span>

<span data-ttu-id="6862f-156">用户可以直接从 Web 服务器安装应用。</span><span class="sxs-lookup"><span data-stu-id="6862f-156">Users can install an app directly from a web server.</span></span> <span data-ttu-id="6862f-157">此流使用结合使用应用安装程序下载和安装分发方法。</span><span class="sxs-lookup"><span data-stu-id="6862f-157">This flow takes use of the App Installer combined with an easy download and install distribution method.</span></span>

### <a name="how-to-set-up-web-install"></a><span data-ttu-id="6862f-158">如何设置 Web 安装：</span><span class="sxs-lookup"><span data-stu-id="6862f-158">How to set up web install:</span></span>

1. <span data-ttu-id="6862f-159">确保应用已正确配置为安装。</span><span class="sxs-lookup"><span data-stu-id="6862f-159">Ensure your app is correctly configured to install.</span></span>
1. <span data-ttu-id="6862f-160">按照 [以下步骤从网页 启用安装](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。</span><span class="sxs-lookup"><span data-stu-id="6862f-160">Follow these [steps to enable install from a web page](/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span>

### <a name="end-user-experience"></a><span data-ttu-id="6862f-161">最终用户体验：</span><span class="sxs-lookup"><span data-stu-id="6862f-161">End user experience:</span></span>

1. <span data-ttu-id="6862f-162">用户使用前面选择的方法接收证书并安装到设备。</span><span class="sxs-lookup"><span data-stu-id="6862f-162">User receives and installs certificate to the device using a method previously chosen above.</span></span>
1. <span data-ttu-id="6862f-163">用户访问通过上述步骤创建的 URL。</span><span class="sxs-lookup"><span data-stu-id="6862f-163">User visits the URL created from the step above.</span></span>

<span data-ttu-id="6862f-164">应用现在将安装到设备。</span><span class="sxs-lookup"><span data-stu-id="6862f-164">The app will now install to the device.</span></span> <span data-ttu-id="6862f-165">若要查找应用，请打开"开始"菜单并选择"所有 **应用**"按钮以查找应用。</span><span class="sxs-lookup"><span data-stu-id="6862f-165">To find the app, open the **Start menu** and select the **All apps** button to find your app.</span></span>

- <span data-ttu-id="6862f-166">有关排查应用安装程序安装方法问题的帮助，请访问 [排查应用安装程序问题](/windows/msix/app-installer/troubleshoot-appinstaller-issues)。</span><span class="sxs-lookup"><span data-stu-id="6862f-166">For more help with troubleshooting the app installer installation method visit [troubleshoot app installer issues](/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span>

> [!NOTE]
> <span data-ttu-id="6862f-167">不支持在更新过程中使用 UI。</span><span class="sxs-lookup"><span data-stu-id="6862f-167">UI during the update process is not supported.</span></span> <span data-ttu-id="6862f-168">因此，此页上的 ShowPrompt [选项](/windows/msix/app-installer/update-settings) 和相关选项不受支持。</span><span class="sxs-lookup"><span data-stu-id="6862f-168">So the ShowPrompt option on [this page](/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>

## <a name="sample-apps"></a><span data-ttu-id="6862f-169">示例应用</span><span class="sxs-lookup"><span data-stu-id="6862f-169">Sample Apps</span></span>

<span data-ttu-id="6862f-170">尝试使用应用安装程序示例应用之一来试用该示例。</span><span class="sxs-lookup"><span data-stu-id="6862f-170">Try out the App Installer with one of our available sample apps.</span></span> 
> [!div class="nextstepaction"]
> [<span data-ttu-id="6862f-171">示例应用</span><span class="sxs-lookup"><span data-stu-id="6862f-171">Sample apps</span></span>](/windows/mixed-reality/develop/features-and-samples)
