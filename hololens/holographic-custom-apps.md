---
title: 管理 HoloLens 的自定义应用
description: 在 HoloLens 上旁加载自定义应用。 详细了解如何安装和卸载全息应用。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens， 旁加载， 旁加载， 旁加载， 存储， uwp， 应用， 安装
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
ms.openlocfilehash: 67a857eb35126435f5642ee60168128300401394
ms.sourcegitcommit: cd2071c12eaabe46c829b53c22d13e21b8af5b53
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "11218629"
---
# <span data-ttu-id="5409a-105">管理 HoloLens 的自定义应用</span><span class="sxs-lookup"><span data-stu-id="5409a-105">Manage custom apps for HoloLens</span></span>

<span data-ttu-id="5409a-106">HoloLens 支持 Microsoft Store 中的许多现有应用程序，以及专为 HoloLens 构建的新应用。</span><span class="sxs-lookup"><span data-stu-id="5409a-106">HoloLens supports many existing applications from the Microsoft Store, as well as new apps built specifically for HoloLens.</span></span> <span data-ttu-id="5409a-107">本文重点介绍自定义全息应用程序。</span><span class="sxs-lookup"><span data-stu-id="5409a-107">This article focuses on custom holographic applications.</span></span>  

<span data-ttu-id="5409a-108">有关应用商店应用详细信息，请参阅使用应用商店 [管理应用](holographic-store-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="5409a-108">For more information about store apps, see [Manage apps with the store](holographic-store-apps.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5409a-109">为 HoloLens 第一代 (创建以下信息) 当时也称为 HoloLens Developer Edition。</span><span class="sxs-lookup"><span data-stu-id="5409a-109">The following information was created for the HoloLens (1st gen), also called the HoloLens Developer Edition at the time.</span></span> <span data-ttu-id="5409a-110">因此，通过设备门户旁加载应用和通过 Visual Studio安装应用很常见。</span><span class="sxs-lookup"><span data-stu-id="5409a-110">As such sideloading apps via device portal and installing apps via Visual Studio were commonplace then.</span></span> <span data-ttu-id="5409a-111">对于企业部署，我们不建议启用开发人员模式，这两种方法都使用开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="5409a-111">For enterprise deployments we do not recommend enabling Developer Mode, which both of these methods use.</span></span> <span data-ttu-id="5409a-112">如果你对安全的应用部署方法感兴趣，请查看我们的 [应用管理：概述](app-deploy-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5409a-112">If you are interested in a secure app deployment method please review our [App Management: Overview](app-deploy-overview.md).</span></span>
>
> <span data-ttu-id="5409a-113">如果你正在寻找适用于 HoloLens 2 设备的应用安装的开发人员方法，请参阅：</span><span class="sxs-lookup"><span data-stu-id="5409a-113">If you are looking for either developer method of app installation for HoloLens 2 devices please refer to:</span></span>
> - [<span data-ttu-id="5409a-114">Device Portal：安装应用</span><span class="sxs-lookup"><span data-stu-id="5409a-114">Device Portal: Installing an App</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [<span data-ttu-id="5409a-115">使用 Visual Studio 部署和调试应用</span><span class="sxs-lookup"><span data-stu-id="5409a-115">Using Visual Studio to deploy and debug Apps</span></span>](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <span data-ttu-id="5409a-116">安装自定义应用</span><span class="sxs-lookup"><span data-stu-id="5409a-116">Install custom apps</span></span>

<span data-ttu-id="5409a-117">可以使用 Device Portal 或部署 HoloLens 中的应用，在 HoloLens 上Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="5409a-117">You can install your own applications on HoloLens either by using the Device Portal or by deploying the apps from Visual Studio.</span></span>

### <span data-ttu-id="5409a-118">使用 Device Portal 安装应用程序包</span><span class="sxs-lookup"><span data-stu-id="5409a-118">Installing an application package with the Device Portal</span></span>

1. <span data-ttu-id="5409a-119">建立从 [Device Portal 到](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 目标 HoloLens 的连接。</span><span class="sxs-lookup"><span data-stu-id="5409a-119">Establish a connection from [Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) to the target HoloLens.</span></span>
1. <span data-ttu-id="5409a-120">在左侧导航中，导航到 **"应用"** 页。</span><span class="sxs-lookup"><span data-stu-id="5409a-120">In the left navigation, navigate to the **Apps** page .</span></span>
1. <span data-ttu-id="5409a-121">在 **"应用** 包"下，浏览到与应用程序关联的 .appx 文件。</span><span class="sxs-lookup"><span data-stu-id="5409a-121">Under **App Package** browse to the .appx file that is associated with your application.</span></span>
   > [!IMPORTANT]
   > <span data-ttu-id="5409a-122">确保引用任何关联的依赖项和证书文件。</span><span class="sxs-lookup"><span data-stu-id="5409a-122">Make sure to reference any associated dependency and certificate files.</span></span>

1. <span data-ttu-id="5409a-123">选择 **"转到"。**</span><span class="sxs-lookup"><span data-stu-id="5409a-123">Select **Go**.</span></span>
   ![在 Microsoft HoloLens 上的 Windows Device Portal 中安装应用表单](images/deviceportal-appmanager.jpg)

### <span data-ttu-id="5409a-125">从 Microsoft Visual Studio 2015 部署</span><span class="sxs-lookup"><span data-stu-id="5409a-125">Deploying from Microsoft Visual Studio 2015</span></span>

1. <span data-ttu-id="5409a-126">打开应用的 Visual Studio 解决方案 (.sln 文件) 。</span><span class="sxs-lookup"><span data-stu-id="5409a-126">Open your app's Visual Studio solution (.sln file).</span></span>
1. <span data-ttu-id="5409a-127">打开项目 **的属性**。</span><span class="sxs-lookup"><span data-stu-id="5409a-127">Open the project's **Properties**.</span></span>
1. <span data-ttu-id="5409a-128">选择以下生成配置 **：Master/x86/Remote Machine。**</span><span class="sxs-lookup"><span data-stu-id="5409a-128">Select the following build configuration: **Master/x86/Remote Machine**.</span></span>
1. <span data-ttu-id="5409a-129">选择远程 **计算机时**：</span><span class="sxs-lookup"><span data-stu-id="5409a-129">When you select **Remote Machine**:</span></span>
   - <span data-ttu-id="5409a-130">确保地址指向 HoloLens Wi-Fi IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5409a-130">Make sure the address points to the Wi-Fi IP address of your HoloLens.</span></span>
   - <span data-ttu-id="5409a-131">将身份验证设置为\*\*通用 (未加密协议) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="5409a-131">Set authentication to **Universal (Unencrypted Protocol)**.</span></span>
1. <span data-ttu-id="5409a-132">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="5409a-132">Build your solution.</span></span>
1. <span data-ttu-id="5409a-133">若要将应用从开发电脑部署到 HoloLens，请选择 **"远程计算机"。**</span><span class="sxs-lookup"><span data-stu-id="5409a-133">To deploy the app from your development PC to your HoloLens, select **Remote Machine**.</span></span> <span data-ttu-id="5409a-134">如果 HoloLens 上已有内部版本，请选择"是\*\*\*\*"以安装此较新版本。</span><span class="sxs-lookup"><span data-stu-id="5409a-134">If you already have an existing build on the HoloLens, select **Yes** to install this newer version.</span></span>  

   ![将应用远程计算机部署到 Microsoft HoloLens Visual Studio](images/vs2015-remotedeployment.jpg)  
1. <span data-ttu-id="5409a-136">应用程序将在 HoloLens 上安装和自动启动。</span><span class="sxs-lookup"><span data-stu-id="5409a-136">The application will install and auto launch on your HoloLens.</span></span>

<span data-ttu-id="5409a-137">安装应用后，你将在"所有应用"列表中找到它\*\*\*\*\*\*\*\*  >  **， ("所有应用) 。**</span><span class="sxs-lookup"><span data-stu-id="5409a-137">After you've installed an app, you'll find it in the **All apps** list (**Start** > **All apps**).</span></span>
