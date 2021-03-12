---
title: 查找、安装和卸载应用程序
description: Microsoft Store 是 HoloLens 应用和游戏的来源。  了解有关查找、安装和卸载全息应用的详细信息。
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 10/27/2020
manager: jarrettr
keywords: hololens, Microsoft Store, uwp, 应用, 安装
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.topic: article
ms.localizationpriority: high
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 44c79a41d7864cd6000ffed1bdd32dab8ffabc39
ms.sourcegitcommit: b437c738f101ac870a29bbdb7fd642eda3d67f00
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2021
ms.locfileid: "11406264"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a><span data-ttu-id="459e4-105">查找、安装和卸载 Microsoft Store 中的应用程序</span><span class="sxs-lookup"><span data-stu-id="459e4-105">Find, install, and uninstall applications from the Microsoft Store</span></span>

<span data-ttu-id="459e4-106">Microsoft Store 是 HoloLens 应用和游戏的首选来源。</span><span class="sxs-lookup"><span data-stu-id="459e4-106">The Microsoft Store is your go-to source for apps and games that work with HoloLens.</span></span> <span data-ttu-id="459e4-107">当你在 HoloLens 上转到 Microsoft Store 中时，上面显示的任何应用都将能够在该设备上运行。</span><span class="sxs-lookup"><span data-stu-id="459e4-107">When you go to the Store on your HoloLens, any apps you see there will run on it.</span></span>

<span data-ttu-id="459e4-108">HoloLens 上的应用将使用 2D 视图或全息视图。</span><span class="sxs-lookup"><span data-stu-id="459e4-108">Apps on HoloLens use either 2D view or holographic view.</span></span> <span data-ttu-id="459e4-109">使用 2D 视图的应用外观类似于窗户，可放置在你的周围。</span><span class="sxs-lookup"><span data-stu-id="459e4-109">Apps that use 2D view look like windows and can be positioned all around you.</span></span> <span data-ttu-id="459e4-110">使用全息视图的应用将会环绕你，且将成为你能够看到的唯一应用。</span><span class="sxs-lookup"><span data-stu-id="459e4-110">Apps that use holographic view surround you and become the only app you see.</span></span>

<span data-ttu-id="459e4-111">HoloLens 支持 Microsoft Store 中的许多现有应用程序，以及专为 HoloLens 构建的新应用。</span><span class="sxs-lookup"><span data-stu-id="459e4-111">HoloLens supports many existing applications from the Microsoft Store, and new apps built specifically for HoloLens.</span></span>  <span data-ttu-id="459e4-112">本文主要针对 Microsoft Store 中的全息应用程序。</span><span class="sxs-lookup"><span data-stu-id="459e4-112">This article focuses on holographic applications from the Microsoft Store.</span></span>

<span data-ttu-id="459e4-113">若要了解有关安装和运行自定义应用的详细信息，请参阅[自定义全息应用程序](holographic-custom-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="459e4-113">To learn more about installing and running custom apps, read [Custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="find-apps"></a><span data-ttu-id="459e4-114">查找应用</span><span class="sxs-lookup"><span data-stu-id="459e4-114">Find apps</span></span>

<span data-ttu-id="459e4-115">从“开始”\*\*\*\* 菜单中打开 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="459e4-115">Open the Microsoft Store from the **Start** menu.</span></span> <span data-ttu-id="459e4-116">然后浏览应用和游戏。</span><span class="sxs-lookup"><span data-stu-id="459e4-116">Then browse for apps and games.</span></span> <span data-ttu-id="459e4-117">可以通过说出“搜索”来使用[语音命令](hololens-cortana.md)，在搜索窗口打开时请说“开始听写”，然后在收到提示后说你要查找的条款。</span><span class="sxs-lookup"><span data-stu-id="459e4-117">You can use [voice commands](hololens-cortana.md) to search by saying "Search", once the search window opens say "Start dictating" and then when prompted begin saying your search terms.</span></span>

> [!NOTE]
> <span data-ttu-id="459e4-118">HoloLens 设备的系统要求基于应用内部版本的体系结构。</span><span class="sxs-lookup"><span data-stu-id="459e4-118">The System Requirements for HoloLens devices are based on the architecture of the app build.</span></span> <span data-ttu-id="459e4-119">如果 HoloLens（第 1 代）的应用内部版本尚未更新到应用商店中的较新 UWP 以包括 ARM 体系结构程序包，则它将不适用于 HoloLens 2 设备。</span><span class="sxs-lookup"><span data-stu-id="459e4-119">If an app build for HoloLens (1st gen) has not been updated with to a newer UWP in the store to include the ARM architecture package, then it will not be available for HoloLens 2 devices.</span></span> <span data-ttu-id="459e4-120">同样，如果 HoloLens 2 应用不包含 x86 体系结构程序包，则它将不适用于 HoloLens（第一代）设备。</span><span class="sxs-lookup"><span data-stu-id="459e4-120">Likewise, if a HoloLens 2 app does not include the x86 architecture package, it will not be available for HoloLens (1st gen) devices.</span></span> <span data-ttu-id="459e4-121">HoloLens 设备体系结构：</span><span class="sxs-lookup"><span data-stu-id="459e4-121">HoloLens device architectures:</span></span>
> - <span data-ttu-id="459e4-122">x86 = HoloLens（第一代）</span><span class="sxs-lookup"><span data-stu-id="459e4-122">x86 = HoloLens (1st gen)</span></span>
> - <span data-ttu-id="459e4-123">ARM = HoloLens 2</span><span class="sxs-lookup"><span data-stu-id="459e4-123">ARM = HoloLens 2</span></span>

> [!NOTE]
> <span data-ttu-id="459e4-124">2021 年 1 月 12 日，以下应用将在 HoloLens 设备上终止支持。</span><span class="sxs-lookup"><span data-stu-id="459e4-124">On January 12, 2021 the following apps will reach End of Support on HoloLens devices.</span></span> <span data-ttu-id="459e4-125">我们建议你在设备上使用以下链接来使用该应用的 Web 版本。</span><span class="sxs-lookup"><span data-stu-id="459e4-125">We encourage you to use the following link on your device to use the web version of the app.</span></span>

| <span data-ttu-id="459e4-126">应用</span><span class="sxs-lookup"><span data-stu-id="459e4-126">App</span></span>        | <span data-ttu-id="459e4-127">Link</span><span class="sxs-lookup"><span data-stu-id="459e4-127">Link</span></span>                                          |
|------------|-----------------------------------------------|
| <span data-ttu-id="459e4-128">Excel Mobile</span><span class="sxs-lookup"><span data-stu-id="459e4-128">Excel mobile</span></span>      | https://office.live.com/start/Excel.aspx      |
| <span data-ttu-id="459e4-129">Word Mobile</span><span class="sxs-lookup"><span data-stu-id="459e4-129">Word mobile</span></span>       | https://office.live.com/start/Word.aspx       |
| <span data-ttu-id="459e4-130">PowerPoint Mobile</span><span class="sxs-lookup"><span data-stu-id="459e4-130">PowerPoint mobile</span></span> | https://office.live.com/start/PowerPoint.aspx |

## <a name="install-apps"></a><span data-ttu-id="459e4-131">安装应用</span><span class="sxs-lookup"><span data-stu-id="459e4-131">Install apps</span></span>

<span data-ttu-id="459e4-132">若要下载应用，需要使用 Microsoft 帐户登录。</span><span class="sxs-lookup"><span data-stu-id="459e4-132">To download apps, you'll need to be signed in with a Microsoft account.</span></span> <span data-ttu-id="459e4-133">有些应用是免费的，并且可以直接下载。</span><span class="sxs-lookup"><span data-stu-id="459e4-133">Some apps are free and can be downloaded right away.</span></span> <span data-ttu-id="459e4-134">对于需要购买的应用，你必须使用 Microsoft 帐户登录到 Microsoft Store，并且具有有效的付款方式。</span><span class="sxs-lookup"><span data-stu-id="459e4-134">For apps that require a purchase, you must be signed in to the Store with your Microsoft account and have a valid payment method.</span></span>
> [!NOTE]
> <span data-ttu-id="459e4-135">在 Microsoft Store 中使用的帐户不必与登录的帐户相同。</span><span class="sxs-lookup"><span data-stu-id="459e4-135">The account you use on Microsoft Store does not have to be the same as the account you are signed in with.</span></span> <span data-ttu-id="459e4-136">如果你在 HoloLens 上使用的是工作或学校帐户，则可能需要使用你的个人帐户登录 Microsoft Store 以进行购买。</span><span class="sxs-lookup"><span data-stu-id="459e4-136">If you are using a Work or School account on your HoloLens then you may need to sign in with your personal account in the Store App to make a purchase.</span></span>

> [!TIP]
> <span data-ttu-id="459e4-137">若要设置付款方式，请转到 [account.microsoft.com](https://account.microsoft.com/)，然后选择“付款和计费”\*\*\*\* > “付款选项”\*\*\*\* > “添加付款选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="459e4-137">To set up a payment method, go to [account.microsoft.com](https://account.microsoft.com/) and select **Payment & billing** > **Payment options** > **Add a payment option**.</span></span>

1. <span data-ttu-id="459e4-138">若要打开[**“开始”** 菜单](holographic-home.md)，请执行[开始手势](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture)或[开花](hololens1-basic-usage.md)手势（在 HoloLens 第 1 代上）。</span><span class="sxs-lookup"><span data-stu-id="459e4-138">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>
1. <span data-ttu-id="459e4-139">选择 Microsoft Store 应用。</span><span class="sxs-lookup"><span data-stu-id="459e4-139">Select the Microsoft Store app.</span></span> <span data-ttu-id="459e4-140">在 Microsoft Store 应用打开后：</span><span class="sxs-lookup"><span data-stu-id="459e4-140">After the Store app opens:</span></span>
   1. <span data-ttu-id="459e4-141">使用搜索栏查找应用程序。</span><span class="sxs-lookup"><span data-stu-id="459e4-141">Use the search bar to look for applications.</span></span> 
   1. <span data-ttu-id="459e4-142">从某个特选类别中选择基本应用或专为 HoloLens 制作的应用。</span><span class="sxs-lookup"><span data-stu-id="459e4-142">Select essential apps or apps made specifically for HoloLens from one of the curated categories.</span></span>
   1. <span data-ttu-id="459e4-143">在 Microsoft Store 应用的右上角，选择 **“...”** 按钮，然后选择 **“我的库**”以查看以前购买的应用。</span><span class="sxs-lookup"><span data-stu-id="459e4-143">On the top right of the Store app, select the **"..."** button and then select **My Library** to view any previously purchased apps.</span></span>
1. <span data-ttu-id="459e4-144">在应用程序的页面上选择“获取”\*\*\*\* 或“安装”\*\*\*\*（可能需要购买）。</span><span class="sxs-lookup"><span data-stu-id="459e4-144">Select **Get** or **Install** on the application's page (a purchase may be required).</span></span>

## <a name="update-apps"></a><span data-ttu-id="459e4-145">更新应用</span><span class="sxs-lookup"><span data-stu-id="459e4-145">Update Apps</span></span>
<span data-ttu-id="459e4-146">要更新从 Microsoft Store 安装的应用，可以从 Microsoft Store 应用更新该应用。</span><span class="sxs-lookup"><span data-stu-id="459e4-146">To update an app you installed from the Microsoft Store, you can update the app from the Microsoft Store app.</span></span> <span data-ttu-id="459e4-147">对于为适用于企业的 Microsoft Store 安装的应用，也可以从适用于企业的 Microsoft Store 更新这些应用。</span><span class="sxs-lookup"><span data-stu-id="459e4-147">For apps installed for the Microsoft Store for Business, you can also update those apps from the Microsoft Store for Business.</span></span> 
1. <span data-ttu-id="459e4-148">要打开 [**开始**菜单](holographic-home.md)，请在 HoloLens（第 1 代）上执行 [开始手势](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) 或 [开花](hololens1-basic-usage.md) 手势。</span><span class="sxs-lookup"><span data-stu-id="459e4-148">To open the [**Start** menu](holographic-home.md), perform a [Start gesture](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture) or [bloom](hololens1-basic-usage.md) gesture on HoloLens (1st gen).</span></span>
1. <span data-ttu-id="459e4-149">选择 Microsoft Store 应用。</span><span class="sxs-lookup"><span data-stu-id="459e4-149">Select the Store app.</span></span>
1. <span data-ttu-id="459e4-150">看看 Microsoft Store 应用的右上角。</span><span class="sxs-lookup"><span data-stu-id="459e4-150">Look to the top right of the Store app.</span></span> 
1. <span data-ttu-id="459e4-151">选择 \*\*“...” \*\*或 "查看更多" 按钮。</span><span class="sxs-lookup"><span data-stu-id="459e4-151">Select the **"..."** or “See more” button.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store 应用屏幕截图。](images/store-update-1.png)

1. <span data-ttu-id="459e4-153">选择 **下载和更新**。</span><span class="sxs-lookup"><span data-stu-id="459e4-153">Select **Downloads and updates**.</span></span>
    1. <span data-ttu-id="459e4-154">如果你的设备以前识别过更新，你可能会看到一个向下箭头和数字，这表示待定的更新。</span><span class="sxs-lookup"><span data-stu-id="459e4-154">If your device has previously identified updates, there may be a down arrow and a number that represents pending updates.</span></span>
1. <span data-ttu-id="459e4-155">选择 **获取更新**。</span><span class="sxs-lookup"><span data-stu-id="459e4-155">Select **Get updates**.</span></span> <span data-ttu-id="459e4-156">设备现在将搜索更新并将其设置为下载并安装。</span><span class="sxs-lookup"><span data-stu-id="459e4-156">Your device will now search for updates and set them to download and install.</span></span> 
 
   > [!div class="mx-imgBorder"]
   > ![Microsoft Store 应用获取更新屏幕截图](images/store-update-2.png.jpg)

> [!NOTE]
> <span data-ttu-id="459e4-158">如果设备上的应用程序是由组织分发的，则可以通过相同的商业应用程序管理方法对其进行更新。</span><span class="sxs-lookup"><span data-stu-id="459e4-158">If the apps on your device were distrubted by your organization they can be updated through the same commercial app management methods.</span></span> <span data-ttu-id="459e4-159">如果这适用于你的情况，请参阅[商业应用部署概述。](app-deploy-overview.md)</span><span class="sxs-lookup"><span data-stu-id="459e4-159">If this applies to your situation, read more via our [overview of commercial app deployment.](app-deploy-overview.md)</span></span>
>
> <span data-ttu-id="459e4-160">如果要更新已旁加载或部署的自定义应用程序，则需要对应用程序的更新版本使用相同的方法。</span><span class="sxs-lookup"><span data-stu-id="459e4-160">If you would like to update a custom app that has been sideloaded or deployed, you will need to use the same method with the updated version of your app.</span></span> <span data-ttu-id="459e4-161">若要了解有关安装和运行自定义应用的详细信息，请参阅[自定义全息应用程序](holographic-custom-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="459e4-161">To learn more about installing and running custom apps, read [custom holographic applications](holographic-custom-apps.md).</span></span>

## <a name="uninstall-apps"></a><span data-ttu-id="459e4-162">卸载应用</span><span class="sxs-lookup"><span data-stu-id="459e4-162">Uninstall apps</span></span>

<span data-ttu-id="459e4-163">卸载应用程序的方法有两种。</span><span class="sxs-lookup"><span data-stu-id="459e4-163">There are two ways to uninstall applications.</span></span>  <span data-ttu-id="459e4-164">可通过 Microsoft Store 或“开始”菜单卸载应用程序。</span><span class="sxs-lookup"><span data-stu-id="459e4-164">You can uninstall applications through the Microsoft Store or Start menu.</span></span>

### <a name="uninstall-from-the-start-menu"></a><span data-ttu-id="459e4-165">从“开始”菜单卸载</span><span class="sxs-lookup"><span data-stu-id="459e4-165">Uninstall from the Start menu</span></span>

<span data-ttu-id="459e4-166">在“开始”\*\*\*\* 菜单上或“所有应用”\*\*\*\* 列表中，浏览到相应应用。</span><span class="sxs-lookup"><span data-stu-id="459e4-166">On the **Start** menu or in the **All apps** list, browse to the app.</span></span> <span data-ttu-id="459e4-167">选择并按住，直至出现菜单，然后选择“**卸载**”。</span><span class="sxs-lookup"><span data-stu-id="459e4-167">Select and hold until the menu appears, then select **Uninstall**.</span></span>

### <a name="uninstall-from-the-microsoft-store"></a><span data-ttu-id="459e4-168">从 Microsoft Store 卸载</span><span class="sxs-lookup"><span data-stu-id="459e4-168">Uninstall from the Microsoft Store</span></span>

<span data-ttu-id="459e4-169">从“**开始**”菜单中打开 Microsoft Store，然后浏览到想要卸载的应用程序。</span><span class="sxs-lookup"><span data-stu-id="459e4-169">Open the Microsoft Store from the **Start** menu, and then browse for the application you want to uninstall.</span></span>  <span data-ttu-id="459e4-170">在 Microsoft Store 页面上，每个已安装应用程序都有一个“**卸载**”按钮。</span><span class="sxs-lookup"><span data-stu-id="459e4-170">On the Store page, each installed application has an **Uninstall** button.</span></span>
