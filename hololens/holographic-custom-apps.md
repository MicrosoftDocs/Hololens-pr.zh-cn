---
title: 管理 HoloLens 的自定义应用
description: 在 HoloLens 上加载自定义应用程序。 了解有关安装和卸载全息应用的详细信息。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
manager: v-miegge
keywords: hololens、旁加载、端加载、侧面加载、应用商店、uwp、应用、安装
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: medium
ms.custom:
- CI 111456
- CSSTroubleshooting
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827868"
---
# <span data-ttu-id="ace43-105">管理 HoloLens 的自定义应用</span><span class="sxs-lookup"><span data-stu-id="ace43-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="ace43-106">HoloLens 支持 Microsoft Store 中的许多现有应用程序，以及专为 HoloLens 构建的新应用。</span><span class="sxs-lookup"><span data-stu-id="ace43-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="ace43-107">本文重点介绍自定义全息版应用程序。</span><span class="sxs-lookup"><span data-stu-id="ace43-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="ace43-108">有关应用商店应用的详细信息，请参阅[管理应用商店](holographic-store-apps.md)中的应用。</span><span class="sxs-lookup"><span data-stu-id="ace43-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

## <span data-ttu-id="ace43-109">安装自定义应用程序</span><span class="sxs-lookup"><span data-stu-id="ace43-109">Install custom apps</span></span>

<span data-ttu-id="ace43-110">你可以通过使用 Device Portal 或从 Visual Studio 部署应用，在 HoloLens 上安装你自己的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ace43-110">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="ace43-111">使用 Device Portal 安装应用程序包</span><span class="sxs-lookup"><span data-stu-id="ace43-111">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="ace43-112">建立从[Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)到目标 HoloLens 的连接。</span><span class="sxs-lookup"><span data-stu-id="ace43-112">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="ace43-113">在左侧导航中，导航到 "**应用**" 页面。</span><span class="sxs-lookup"><span data-stu-id="ace43-113">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="ace43-114">在 "**应用包**" 下，浏览到与你的应用程序关联的 .appx 文件。</span><span class="sxs-lookup"><span data-stu-id="ace43-114">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="ace43-115">请确保引用任何关联的相关性和证书文件。</span><span class="sxs-lookup"><span data-stu-id="ace43-115">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="ace43-116">选择 "**转到**"。</span><span class="sxs-lookup"><span data-stu-id="ace43-116">Select **Go**.</span></span>
   ![Microsoft HoloLens 上的 Windows Device Portal 中的 "安装应用" 表单](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="ace43-118">从 Microsoft Visual Studio 2015 部署</span><span class="sxs-lookup"><span data-stu-id="ace43-118">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="ace43-119">打开应用的 Visual Studio 解决方案（.sln 文件）。</span><span class="sxs-lookup"><span data-stu-id="ace43-119">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="ace43-120">打开项目的**属性**。</span><span class="sxs-lookup"><span data-stu-id="ace43-120">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="ace43-121">选择以下生成配置： "**主/x86/远程计算机**"。</span><span class="sxs-lookup"><span data-stu-id="ace43-121">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="ace43-122">选择 "**远程计算机**" 时：</span><span class="sxs-lookup"><span data-stu-id="ace43-122">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="ace43-123">请确保地址指向 HoloLens 的 Wi-fi IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ace43-123">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="ace43-124">将身份验证设置为**通用（未加密协议）**。</span><span class="sxs-lookup"><span data-stu-id="ace43-124">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="ace43-125">构建您的解决方案。</span><span class="sxs-lookup"><span data-stu-id="ace43-125">Build your solution.</span></span>
1. <span data-ttu-id="ace43-126">若要将应用从开发电脑部署到 HoloLens，请选择 "**远程计算机**"。</span><span class="sxs-lookup"><span data-stu-id="ace43-126">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="ace43-127">如果你已有 HoloLens 上的现有版本，请选择 **"是"** 以安装此较新版本。</span><span class="sxs-lookup"><span data-stu-id="ace43-127">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![Visual Studio 中适用于 Microsoft HoloLens 的应用的远程计算机部署](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="ace43-129">应用程序将在 HoloLens 上安装和自动启动。</span><span class="sxs-lookup"><span data-stu-id="ace43-129">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="ace43-130">安装应用后，你将在 "**所有应用**" 列表（"**启动**  >  **所有应用**"）中找到它。</span><span class="sxs-lookup"><span data-stu-id="ace43-130">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
