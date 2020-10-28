---
title: 如何通过 web 安装程序安装应用
description: 通过适用于应用安装程序的 web installer 安装应用
keywords: 应用管理、应用、hololens、应用安装程序、web 安装
author: evmill
ms.author: v-evmill
ms.reviewer: qizho
ms.date: 9/17/2020
ms.prod: hololens
ms.topic: article
ms.sitesec: library
ms.localizationpriority: medium
audience: HoloLens
manager: yannisle
appliesto:
- HoloLens 2
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: a3e53f0e5070d0538f3ed74259914c59413eafd0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "11135437"
---
# <span data-ttu-id="799c6-104">从网页安装应用</span><span class="sxs-lookup"><span data-stu-id="799c6-104">Installing apps from a web page</span></span>

<span data-ttu-id="799c6-105">用户可以直接从 web 服务器安装应用。</span><span class="sxs-lookup"><span data-stu-id="799c6-105">Users can install an app directly from a web server.</span></span> <span data-ttu-id="799c6-106">这会将应用安装程序与轻松下载和安装分发方法结合使用。</span><span class="sxs-lookup"><span data-stu-id="799c6-106">This takes use of the App Installer combined with an easy download and install distribution method.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="799c6-107">此功能目前仅在 Windows 预览体验计划内部版本19041.1366 中 avalible。</span><span class="sxs-lookup"><span data-stu-id="799c6-107">This feature is currently only avalible in Windows Insider builds 19041.1366+.</span></span> <span data-ttu-id="799c6-108">[了解有关如何在 Windows 预览体验计划内部版本中注册的详细信息](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="799c6-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

## <span data-ttu-id="799c6-109">如何进行设置：</span><span class="sxs-lookup"><span data-stu-id="799c6-109">How to set this up:</span></span>
1.  <span data-ttu-id="799c6-110">确保你的应用已正确配置为安装。</span><span class="sxs-lookup"><span data-stu-id="799c6-110">Ensure your app is correctly configured to install.</span></span>
1.  <span data-ttu-id="799c6-111">请按照以下 [步骤在网页上启用此操作](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。</span><span class="sxs-lookup"><span data-stu-id="799c6-111">Follow these [steps to enable this on a web page](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage).</span></span> 
1.  <span data-ttu-id="799c6-112">选择证书部署方法。</span><span class="sxs-lookup"><span data-stu-id="799c6-112">Pick a certificate deployment method.</span></span> 
    1.  <span data-ttu-id="799c6-113">[预配程序包](hololens-provisioning.md) 可应用于本地设备。</span><span class="sxs-lookup"><span data-stu-id="799c6-113">[Provisioning Packages](hololens-provisioning.md) can be applied to local devices.</span></span>
    1.  <span data-ttu-id="799c6-114">可以使用 MDM [将证书应用于设备配置](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。</span><span class="sxs-lookup"><span data-stu-id="799c6-114">MDM can be used to [apply certificates with device configurations](https://docs.microsoft.com/mem/intune/protect/certificates-configure).</span></span>
    1.  <span data-ttu-id="799c6-115">使用 "设备 [证书管理器](hololens-insider.md#certificate-manager)"。</span><span class="sxs-lookup"><span data-stu-id="799c6-115">Use the on device [Certificate Manager](hololens-insider.md#certificate-manager).</span></span> 

## <span data-ttu-id="799c6-116">最终用户体验：</span><span class="sxs-lookup"><span data-stu-id="799c6-116">End User Experience:</span></span>
1.  <span data-ttu-id="799c6-117">用户使用之前选择的方法接收和安装设备证书。</span><span class="sxs-lookup"><span data-stu-id="799c6-117">User receives and installs certificate to the device using a method previously chosen above.</span></span> 
1.  <span data-ttu-id="799c6-118">用户访问上述步骤中创建的 URL。</span><span class="sxs-lookup"><span data-stu-id="799c6-118">User visits the URL created from the step above.</span></span>

<span data-ttu-id="799c6-119">该应用现在将安装到设备。</span><span class="sxs-lookup"><span data-stu-id="799c6-119">The app will now install to the device.</span></span> <span data-ttu-id="799c6-120">若要查找应用，请打开 " **开始" 菜单** ，然后选择 " **所有应用** " 按钮以查找你的应用。</span><span class="sxs-lookup"><span data-stu-id="799c6-120">To find the app open the **Start menu** and select the **All apps** button to find your app.</span></span> 

-   <span data-ttu-id="799c6-121">有关此安装方法的疑难解答帮助，请访问 [应用安装程序问题疑难解答](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。</span><span class="sxs-lookup"><span data-stu-id="799c6-121">For help troubleshooting this installation method please visit [troubleshoot app installer issues](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues).</span></span> 

> [!NOTE]
> <span data-ttu-id="799c6-122">更新过程中不支持 UI。</span><span class="sxs-lookup"><span data-stu-id="799c6-122">UI during the update process is not supported.</span></span> <span data-ttu-id="799c6-123">因此，不支持 [此页面](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 上的 ShowPrompt 选项和相关选项。</span><span class="sxs-lookup"><span data-stu-id="799c6-123">So the ShowPrompt option on [this page](https://docs.microsoft.com/windows/msix/app-installer/update-settings) and related options are not supported.</span></span>
