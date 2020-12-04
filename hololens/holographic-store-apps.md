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
ms.openlocfilehash: 06768203459827a83d8b6e891dfc8c46e33c3da2
ms.sourcegitcommit: 1f37a06cde037f3acdc4ef3767a9384953d97c33
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "11194862"
---
# 查找、安装和卸载 Microsoft Store 中的应用程序

Microsoft Store 是 HoloLens 应用和游戏的首选来源。 当你在 HoloLens 上转到 Microsoft Store 中时，上面显示的任何应用都将能够在该设备上运行。

HoloLens 上的应用将使用 2D 视图或全息视图。 使用 2D 视图的应用外观类似于窗户，可放置在你的周围。 使用全息视图的应用将会环绕你，且将成为你能够看到的唯一应用。

HoloLens 支持 Microsoft Store 中的许多现有应用程序，以及专为 HoloLens 构建的新应用。  本文主要针对 Microsoft Store 中的全息应用程序。

若要了解有关安装和运行自定义应用的详细信息，请参阅[自定义全息应用程序](holographic-custom-apps.md)。

## 查找应用

从“开始”**** 菜单中打开 Microsoft Store。 然后浏览应用和游戏。 可以通过说出“搜索”来使用[语音命令](hololens-cortana.md)，在搜索窗口打开时请说“开始听写”，然后在收到提示后说你要查找的条款。

> [!NOTE]
> HoloLens 设备的系统要求基于应用内部版本的体系结构。 如果 HoloLens（第 1 代）的应用内部版本尚未更新到应用商店中的较新 UWP 以包括 ARM 体系结构程序包，则它将不适用于 HoloLens 2 设备。 同样，如果 HoloLens 2 应用不包含 x86 体系结构程序包，则它将不适用于 HoloLens（第一代）设备。 HoloLens 设备体系结构：
> - x86 = HoloLens（第一代）
> - ARM = HoloLens 2

> [!NOTE]
> 2021 年 1 月 12 日，以下应用将在 HoloLens 设备上终止支持。 我们建议你在设备上使用以下链接来使用该应用的 Web 版本。

| 应用        | Link                                          |
|------------|-----------------------------------------------|
| Excel Mobile      | https://office.live.com/start/Excel.aspx      |
| Word Mobile       | https://office.live.com/start/Word.aspx       |
| PowerPoint Mobile | https://office.live.com/start/PowerPoint.aspx |

## 安装应用

若要下载应用，需要使用 Microsoft 帐户登录。 有些应用是免费的，可直接下载。 对于需要购买的应用，你需要使用 Microsoft 帐户登录到 Microsoft Store，并且具有有效的付款方式。
> [!NOTE]
> 在 Microsoft Store 中使用的帐户不必与登录的帐户相同。 如果你在 HoloLens 上使用的是工作或学校帐户，则可能需要使用你的个人帐户登录 Microsoft Store 以进行购买。

若要设置付款方式，请转到 [account.microsoft.com](https://account.microsoft.com/)，然后选择“付款和计费”**** > “付款选项”**** > “添加付款选项”****。

1. 若要打开[**“开始”** 菜单](holographic-home.md)，请执行[开始手势](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture)或[开花](hololens1-basic-usage.md)手势（在 HoloLens 第 1 代上）。
1. 选择 Microsoft Store 应用。 在 Microsoft Store 应用打开后：
   1. 使用搜索栏查找任何所需的应用程序。 
   1. 从某个特选类别中选择基本应用或专为 HoloLens 制作的应用。
   1. 在 Microsoft Store 应用的右上角，选择 **“...”** 按钮，然后选择 **“我的库**”以查看以前购买的应用。
1. 在应用程序的页面上选择“获取”**** 或“安装”****（可能需要购买）。

## 更新应用
若要更新已从 Microsoft Store 应用安装的应用，还可以从Microsoft Store 应用更新相同的应用。 这对为适用于企业的 Microsoft Store 安装的应用程序也适用。 
1. 若要打开[**“开始”** 菜单](holographic-home.md)，请执行[开始手势](https://docs.microsoft.com/hololens/hololens2-basic-usage#start-gesture)或[开花](hololens1-basic-usage.md)手势（在 HoloLens 第 1 代上）。
1. 选择 Microsoft Store 应用。
1. 看看 Microsoft Store 应用的右上角。 
1. 选择 **“...” **或 "查看更多" 按钮。

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store 应用屏幕截图。](images/store-update-1.png)

1. 选择 **下载和更新**。
    1. 如果你的设备以前识别过更新，你可能会看到一个向下箭头和数字，这表示待定的更新。
1. 选择**获取更新**。 设备现在将搜索更新并将其设置为下载并安装。 
 
   > [!div class="mx-imgBorder"]
   > ![Microsoft Store 应用获取更新屏幕截图](images/store-update-2.png.jpg)

> [!NOTE]
> 如果设备上的应用程序是由组织分发的，则可以通过相同的商业应用程序管理方法对其进行更新。 如果这适用于你的情况，请参阅[商业应用部署概述。](app-deploy-overview.md)
>
> 如果要更新已旁加载或部署的自定义应用程序，则需要对应用程序的更新版本使用相同的方法。 若要了解有关安装和运行自定义应用的详细信息，请参阅[自定义全息应用程序](holographic-custom-apps.md)。

## 卸载应用

卸载应用程序的方法有两种。  可通过 Microsoft Store 或“开始”菜单卸载应用程序。

### 从“开始”菜单卸载

在“开始”**** 菜单上或“所有应用”**** 列表中，浏览到相应应用。 选择并按住，直至出现菜单，然后选择“**卸载**”。

### 从 Microsoft Store 卸载

从“开始”**** 菜单中打开 Microsoft Store，然后浏览到想要卸载的应用程序。  在 Microsoft Store 页面上，你安装的每个应用程序都有一个“卸载”**** 按钮。
