---
title: " (第一) 代 HoloLens 管理自定义应用"
description: 了解如何使用设备门户和 Visual Studio 在 HoloLens 设备上安装、卸载和加载自定义全息应用。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens，旁加载，端负载，旁加载，存储，uwp，应用，安装
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
ms.openlocfilehash: a179032978e1fc062273a6754e3b0a1ad50a5211
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113635902"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a><span data-ttu-id="32200-104"> (第一) 代 HoloLens 管理自定义应用</span><span class="sxs-lookup"><span data-stu-id="32200-104">Manage custom apps for HoloLens (1st gen)</span></span>

<span data-ttu-id="32200-105">HoloLens 支持 Microsoft Store 中的许多现有应用程序以及专门为 HoloLens 构建的新应用程序。</span><span class="sxs-lookup"><span data-stu-id="32200-105">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="32200-106">本文重点介绍自定义全息应用程序。</span><span class="sxs-lookup"><span data-stu-id="32200-106">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="32200-107">有关应用商店应用的详细信息，请参阅 [管理应用商店的应用](holographic-store-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="32200-107">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32200-108">为第一代) HoloLens (创建了以下信息，同时称为 HoloLens 开发人员版。</span><span class="sxs-lookup"><span data-stu-id="32200-108">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="32200-109">作为此类旁加载应用，通过设备门户并通过 Visual Studio 安装应用非常常见。</span><span class="sxs-lookup"><span data-stu-id="32200-109">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="32200-110">对于企业部署，我们不建议启用开发人员模式，这两种方法都使用这两种模式。</span><span class="sxs-lookup"><span data-stu-id="32200-110">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="32200-111">如果你对安全应用部署方法感兴趣，请查看我们的 [应用管理：概述](app-deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="32200-111">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="32200-112">如果要为 HoloLens 2 设备查找应用程序安装的开发方法，请参阅：</span><span class="sxs-lookup"><span data-stu-id="32200-112">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
>
> - [<span data-ttu-id="32200-113">设备门户：安装应用</span><span class="sxs-lookup"><span data-stu-id="32200-113">Device Portal: Installing an App</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="32200-114">使用 Visual Studio 部署和调试应用程序</span><span class="sxs-lookup"><span data-stu-id="32200-114">Using Visual Studio to deploy and debug Apps</span></span>](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a><span data-ttu-id="32200-115">安装自定义应用</span><span class="sxs-lookup"><span data-stu-id="32200-115">Install custom apps</span></span>

<span data-ttu-id="32200-116">你可以通过使用设备门户或通过从 Visual Studio 部署应用，在 HoloLens 上安装自己的应用程序。</span><span class="sxs-lookup"><span data-stu-id="32200-116">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <a name="installing-an-application-package-with-the-device-portal"></a><span data-ttu-id="32200-117">使用设备门户安装应用程序包</span><span class="sxs-lookup"><span data-stu-id="32200-117">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="32200-118">建立从[设备门户](/windows/mixed-reality/using-the-windows-device-portal)到目标 HoloLens 的连接。</span><span class="sxs-lookup"><span data-stu-id="32200-118">Establish a connection from [Device Portal](/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>

1. <span data-ttu-id="32200-119">在左侧导航栏中，导航到 " **应用** " 页。</span><span class="sxs-lookup"><span data-stu-id="32200-119">In the left navigation, navigate to the **Apps** page.</span></span>

1. <span data-ttu-id="32200-120">在 " **应用包** " 下，浏览到与应用程序关联的 .appx 文件。</span><span class="sxs-lookup"><span data-stu-id="32200-120">Under **App Package** browse to the .appx file that is associated with your application.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="32200-121">请确保引用任何关联的依赖项和证书文件。</span><span class="sxs-lookup"><span data-stu-id="32200-121">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="32200-122">选择“转到”。</span><span class="sxs-lookup"><span data-stu-id="32200-122">Select **Go**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="32200-123">![在 Microsoft HoloLens 上 Windows 设备门户中安装应用窗体](images/deviceportal-appmanager.jpg)</span><span class="sxs-lookup"><span data-stu-id="32200-123">![Install app form in Windows Device Portal on Microsoft HoloLens](images/deviceportal-appmanager.jpg)</span></span>

### <a name="deploying-from-microsoft-visual-studio-2015"></a><span data-ttu-id="32200-124">从 Microsoft Visual Studio 2015 进行部署</span><span class="sxs-lookup"><span data-stu-id="32200-124">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="32200-125">) Visual Studio 打开应用的解决方案 ( .sln 文件。</span><span class="sxs-lookup"><span data-stu-id="32200-125">Open your app's Visual Studio solution (.sln file).</span></span>

1. <span data-ttu-id="32200-126">打开项目的 " **属性**"。</span><span class="sxs-lookup"><span data-stu-id="32200-126">Open the project's **Properties**.</span></span>

1. <span data-ttu-id="32200-127">选择以下生成配置： **Master/x86/远程计算机**。</span><span class="sxs-lookup"><span data-stu-id="32200-127">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>

1. <span data-ttu-id="32200-128">选择 " **远程计算机**" 时：</span><span class="sxs-lookup"><span data-stu-id="32200-128">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="32200-129">请确保该地址指向 HoloLens 的 Wi-Fi IP 地址。</span><span class="sxs-lookup"><span data-stu-id="32200-129">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="32200-130">将身份验证设置为 **通用 (未加密协议)**。</span><span class="sxs-lookup"><span data-stu-id="32200-130">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
   
1. <span data-ttu-id="32200-131">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="32200-131">Build your solution.</span></span>

1. <span data-ttu-id="32200-132">若要将应用从开发 PC 部署到 HoloLens，请选择 "**远程计算机**"。</span><span class="sxs-lookup"><span data-stu-id="32200-132">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="32200-133">如果 HoloLens 上已有现有的生成，请选择 **"是"** 以安装此更新版本。</span><span class="sxs-lookup"><span data-stu-id="32200-133">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![要在 Visual Studio 中 Microsoft HoloLens 的应用的远程计算机部署](images/vs2015-remotedeployment.jpg)  
   
1. <span data-ttu-id="32200-135">应用程序将在你的 HoloLens 上安装和自动启动。</span><span class="sxs-lookup"><span data-stu-id="32200-135">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="32200-136">安装应用后，可在 "**所有应用**" 列表中找到该应用， () **启动**  >  **所有应用**。</span><span class="sxs-lookup"><span data-stu-id="32200-136">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
