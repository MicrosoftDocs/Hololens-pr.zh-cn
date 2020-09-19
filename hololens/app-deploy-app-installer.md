---
title: 如何通过 HoloLens 2 应用安装程序加载和安装应用
description: 幻灯片加载并通过 UI 安装应用
keywords: 应用程序管理、应用、hololens、应用安装程序
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
ms.openlocfilehash: 2387c0eb65efc312db4eea7118f3cca44ce6d4b6
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027458"
---
# <span data-ttu-id="e93a4-104">通过应用安装程序在 HoloLens 2 上安装应用</span><span class="sxs-lookup"><span data-stu-id="e93a4-104">Install Apps on HoloLens 2 via App Installer</span></span>

<span data-ttu-id="e93a4-105">现在，用户现在可以通过 Appx 捆绑安装应用，而无需启用开发人员模式或使用 Device Portal。</span><span class="sxs-lookup"><span data-stu-id="e93a4-105">Users can now install Apps via Appx Bundles now without the need to enable Developer Mode or use Device Portal.</span></span> <span data-ttu-id="e93a4-106">此体验对于在本地设备上安装应用或与其他不熟悉 HoloLens 上的其他应用安装方法的其他人共享应用很简单。</span><span class="sxs-lookup"><span data-stu-id="e93a4-106">This experience is simple for installing Apps on local devices or sharing an app with someone else who is unfamiliar with other app install methods on HoloLens.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e93a4-107">此功能目前仅在 Windows 预览体验计划内部版本19041.1377 中 avalible。</span><span class="sxs-lookup"><span data-stu-id="e93a4-107">This feature is currently only avalible in Windows Insider builds 19041.1377+.</span></span> <span data-ttu-id="e93a4-108">[了解有关如何在 Windows 预览体验计划内部版本中注册的详细信息](hololens-insider.md)。</span><span class="sxs-lookup"><span data-stu-id="e93a4-108">[Learn more on how to enroll in Windows Insider builds](hololens-insider.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e93a4-109">你的应用的解决方案配置必须是 " **主** " 或 " **发布** "，因为应用安装程序将使用应用商店中的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="e93a4-109">Your app’s Solution Configuration must be either **Master** or **Release** as the App Installer will use dependencies from the store.</span></span> <span data-ttu-id="e93a4-110">查看有关 [创建应用包](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e93a4-110">See more about [creating app packages](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs).</span></span>

1.  <span data-ttu-id="e93a4-111">确保 HoloLens 2 设备已开机且已登录。</span><span class="sxs-lookup"><span data-stu-id="e93a4-111">Ensure that your HoloLens 2 device is powered on and you are signed in.</span></span>
1.  <span data-ttu-id="e93a4-112">在你的电脑上导航到你的自定义应用，并将 yourapp 复制到 yourdevicename\Internal Storage\Downloads。</span><span class="sxs-lookup"><span data-stu-id="e93a4-112">On your PC navigate to your custom app, and copy yourapp.appxbundle to yourdevicename\Internal Storage\Downloads.</span></span> 
    <span data-ttu-id="e93a4-113">完成文件复制后，您可能会断开您的设备并在以后完成安装。</span><span class="sxs-lookup"><span data-stu-id="e93a4-113">After your finish copying your file you may disconnect your device and finish the install later.</span></span>
1.  <span data-ttu-id="e93a4-114">从 HoloLens 2 设备打开 " **开始" 菜单**，选择 " **所有应用** "，然后启动 " **文件资源管理器** " 应用。</span><span class="sxs-lookup"><span data-stu-id="e93a4-114">From your HoloLens 2 device Open the **Start Menu**, select **All apps** and launch the **File Explorer** app.</span></span>
1.  <span data-ttu-id="e93a4-115">导航到 "下载" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="e93a4-115">Navigate to the Downloads folder.</span></span> <span data-ttu-id="e93a4-116">你可能需要在应用的左侧面板上，选择 " **此设备** "，然后导航到 "下载"。</span><span class="sxs-lookup"><span data-stu-id="e93a4-116">You may need to on the left panel of the app select **This device** first, then navigate to Downloads.</span></span>
1.  <span data-ttu-id="e93a4-117">选择 yourapp 文件。</span><span class="sxs-lookup"><span data-stu-id="e93a4-117">Select the yourapp.appxbundle file.</span></span> 
1.  <span data-ttu-id="e93a4-118">应用安装程序将启动。</span><span class="sxs-lookup"><span data-stu-id="e93a4-118">The App Installer will launch.</span></span> <span data-ttu-id="e93a4-119">选择 " **安装** " 按钮以安装你的应用。</span><span class="sxs-lookup"><span data-stu-id="e93a4-119">Select the **Install** button to install your app.</span></span> 

<span data-ttu-id="e93a4-120">已安装的应用将在安装完成后自动启动。</span><span class="sxs-lookup"><span data-stu-id="e93a4-120">The installed app will automatically launch upon the completion of installing.</span></span> 

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

<span data-ttu-id="e93a4-122">如果你的应用无法安装，请检查以下内容：</span><span class="sxs-lookup"><span data-stu-id="e93a4-122">If your app failed to install check the following:</span></span>
-   <span data-ttu-id="e93a4-123">你的应用是 "主" 或 "发布" 内部版本。</span><span class="sxs-lookup"><span data-stu-id="e93a4-123">Your app is either a Master or Release build.</span></span>
-   <span data-ttu-id="e93a4-124">您已 [连接到 internet](hololens-network.md)。</span><span class="sxs-lookup"><span data-stu-id="e93a4-124">You are [connected to the internet](hololens-network.md).</span></span>
-   <span data-ttu-id="e93a4-125">已正确配置 [Microsoft Store 的终结点](hololens-offline.md) 。</span><span class="sxs-lookup"><span data-stu-id="e93a4-125">Your [endpoints for the Microsoft Store](hololens-offline.md) are correctly configured.</span></span>  
