---
title: 查找、安装和卸载应用程序
description: Microsoft Store 是 HoloLens 应用和游戏的来源。  了解有关查找、安装和卸载全息应用的详细信息。
ms.assetid: cbe9aa3a-884f-4a92-bf54-8d4917bc3435
ms.reviewer: v-miegge
ms.date: 9/7/2021
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
ms.openlocfilehash: 4705112ee41ce6de0598358b9c81775f261bb2fa
ms.sourcegitcommit: 8a3f925d2bda13c095b35f14d80afdd876aa859c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2021
ms.locfileid: "129800549"
---
# <a name="find-install-and-uninstall-applications-from-the-microsoft-store"></a>查找、安装和卸载 Microsoft Store 中的应用程序

Microsoft Store 是 HoloLens 应用和游戏的首选来源。 当你在 HoloLens 上转到 Microsoft Store 中时，上面显示的任何应用都将能够在该设备上运行。

HoloLens 上的应用将使用 2D 视图或全息视图。 使用 2D 视图的应用外观类似于窗户，可放置在你的周围。 使用全息视图的应用将会环绕你，且将成为你能够看到的唯一应用。

HoloLens 支持 Microsoft Store 中的许多现有应用程序，以及专为 HoloLens 构建的新应用。  本文主要针对 Microsoft Store 中的全息应用程序。

若要详细了解如何安装和运行自定义应用，请阅读[自定义全息应用程序](holographic-custom-apps.md)。

## <a name="find-apps"></a>“查找应用”

打开“开始”菜单上的 Microsoft Store。 然后，浏览应用和游戏。 可以通过说出“搜索”来使用[语音命令](hololens-cortana.md)，在搜索窗口打开时请说“开始听写”，然后在收到提示后说你要搜索的词语。

> [!NOTE]
> HoloLens 设备的系统要求基于应用内部版本的体系结构。 如果 HoloLens（第 1 代）的应用内部版本尚未更新到应用商店中的较新 UWP 以包括 ARM 体系结构程序包，则它将不适用于 HoloLens 2 设备。 同样，如果 HoloLens 2 应用不包含 x86 体系结构程序包，则它将不适用于 HoloLens（第一代）设备。 HoloLens 设备体系结构：
>
> - x86 = HoloLens（第一代）
> - ARM = HoloLens 2

> [!NOTE]
> 2021 年 1 月 12 日，以下应用将在 HoloLens 设备上终止支持。 我们建议你在设备上使用以下链接来使用该应用的 Web 版本。

| 应用        | 链接                                          |
|------------|-----------------------------------------------|
| Excel Mobile      | [https://office.live.com/start/Excel.aspx](https://office.live.com/start/Excel.aspx)      |
| Word Mobile       | [https://office.live.com/start/Word.aspx](https://office.live.com/start/Word.aspx)       |
| PowerPoint Mobile | [https://office.live.com/start/PowerPoint.aspx](https://office.live.com/start/PowerPoint.aspx) |

> [!NOTE]
> OneDrive 应用当前不支持 HoloLens 上的 Azure AD 帐户。 建议下载 Microsoft OneDrive PWA 应用。 [请按以下步骤下载该应用。]

## <a name="install-apps"></a>安装应用

若要下载应用，需要使用 Microsoft 帐户登录。 有些应用是免费的，并且可以直接下载。 对于需要购买的应用，你必须使用 Microsoft 帐户登录到 Microsoft Store，并且具有有效的付款方式。

> [!NOTE]
> 在 Microsoft Store 中使用的帐户不必与登录的帐户相同。 如果你在 HoloLens 上使用的是工作或学校帐户，则可能需要使用你的个人帐户登录 Microsoft Store 以进行购买。

> [!TIP]
> 若要设置付款方式，请转到 [account.microsoft.com](https://account.microsoft.com/) 并选择“付款和计费” > “支付选项” > “添加付款选项”  。

1. 若要打开[“开始”菜单](holographic-home.md)，请在 HoloLens（第一代）上执行[开始手势](/hololens/hololens2-basic-usage#start-gesture)或[开花](hololens1-basic-usage.md)手势。

1. 选择 Microsoft Store 应用。 在 Microsoft Store 应用打开后：
   1. 使用搜索栏查找应用程序。
   1. 从某个特选类别中选择基本应用或专为 HoloLens 制作的应用。
   1. 在 Microsoft Store 应用的右上角，选择“...”按钮，然后选择“我的库”，查看以前购买的应用 。

1. 在应用程序页面上选择“获取”或“安装”（可能需要购买） 。

### <a name="install-microsoft-onedrive-pwa-app"></a>安装 Microsoft OneDrive PWA 应用

> [!NOTE]
> 不能通过 Microsoft Intune/MDM 来管理或部署 PWA。

先决条件：用户已将 HoloLens 2 设备加入其工作租户。

1. 打开“开始”菜单并启动 Edge 浏览器。

    ![“开始”菜单](images/office-pwa-1.jpg)

1. 在 HoloLens 上转到 [https://onedrive.live.com/about/signin](https://onedrive.live.com/about/signin) 并输入工作帐户凭据

    ![工作登录](images/office-pwa-2.jpg)

1. 成功登录到 OneDrive Web 门户后，请等待 30 到 60 秒至 PWA 下载按钮显示

    ![PWA 安装按钮](images/office-pwa-3.jpg)

1. 选择 PWA 下载按钮，安装该应用

    ![安装提示](images/office-pwa-4.jpg)

1. 关闭 Edge 浏览器，然后在“开始”菜单中选择“所有应用”按钮，然后启动标为 Microsoft OneDrive 的 OneDrive PWA 应用

    ![“所有应用”同时显示这两个应用。](images/office-pwa-5.jpg)

    > [!NOTE]
    > “Microsoft OneDrive”是该 PWA 应用，“OneDrive”是旧的 UWP。

1. 之后你可以看到你的 OneDrive 文件。

    ![OneDrive PWA](images/office-pwa-6.jpg)

另请参阅：[启用 OneDrive for Business 自动上传](hololens-release-notes.md#onedrive-for-work-or-school-camera-roll-upload)

## <a name="update-apps"></a>更新应用

### <a name="manual-updates"></a>手动更新

要更新从 Microsoft Store 安装的应用，可以从 Microsoft Store 应用更新该应用。 对于为适用于企业的 Microsoft Store 安装的应用，也可以从适用于企业的 Microsoft Store 更新这些应用。

1. 若要打开[“开始”菜单](holographic-home.md)，请在 HoloLens（第一代）上执行[开始手势](/hololens/hololens2-basic-usage#start-gesture)或[开花](hololens1-basic-usage.md)手势。

1. 选择 Microsoft Store 应用。

1. 看看 Microsoft Store 应用的右上角。

1. 选择“...”或“查看更多”按钮。

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store 应用屏幕截图。](images/store-update-1.png)

1. 选择“下载和更新”。
    1. 如果你的设备以前识别过更新，你可能会看到一个向下箭头和数字，这表示待定的更新。

1. 选择“获取更新”。 设备现在将搜索更新并将其设置为下载并安装。

   > [!div class="mx-imgBorder"]
   > ![Microsoft Store 应用获取更新屏幕截图。](images/store-update-2.png.jpg)

> [!NOTE]
> 如果设备上的应用程序是由组织分发的，则可以通过相同的商业应用程序管理方法对其进行更新。 如果这适用于你的情况，请参阅[商业应用部署概述](app-deploy-overview.md)。
>
> 如果要更新已旁加载或部署的自定义应用程序，则需要对应用程序的更新版本使用相同的方法。 若要详细了解如何安装和运行自定义应用，请阅读[自定义全息应用程序](holographic-custom-apps.md)。

### <a name="automatic-app-updates"></a>自动应用更新

自动更新将应用于 Microsoft Store 或适用于企业的 Microsoft Store 应用，并且只有在已直接从 Store 安装了应用时，才会自动更新这些应用。 如果应用是从 Intune 安装的，IT 可以通过与适用于企业的 Microsoft Store 进行同步来获得应用的最新可用版本，并从 MDM 向下推送更新。

> [!NOTE]
> 对于来自适用于企业的 Microsoft Store 的应用，必须登录到 Store，并使用与设备上使用的适用于企业的 Microsoft Store 目录关联的同一租户进行身份验证。

#### <a name="how-automatic-updates-work"></a>自动更新的工作方式

应用的自动更新计划为每天更新（约每 24 小时一次），具体取决于网络可用性。 应使设备保持活动状态或接入交流电以接收更新。 虽然应用更新是在每日使用期间下载的，但只会在要更新的应用处于非使用状态时才会应用更新。

> [!TIP]
> 如果可能，在设备与公司网络连接的情况下，请整晚对设备充电。 如果可以整晚下载和安装更新，那么因更新中断设备正常使用的可能性会减小。

#### <a name="how-it-administrators-can-control-automatic-updates"></a>IT 管理员如何控制自动更新

IT 管理员可以通过 [ApplicationManagement/AllowAppStoreAutoUpdate](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-allowappstoreautoupdate) 策略控制自动应用更新。 此策略使他们能够完全启用或禁用自动应用更新，但无法控制更新发生的时间。

从 [21H2](hololens-release-notes.md#windows-holographic-version-21h1) 开始，IT 管理员还可使用 [ScheduleForceRestartForUpdateFailures](/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures) 策略来控制何时应强制重启那些之前在使用的但未能成功更新的应用。

## <a name="uninstall-apps"></a>卸载应用

卸载应用程序的方法有三种。 可通过 Microsoft Store、“开始”菜单或“设置”卸载应用程序。

> [!WARNING]
> 无法卸载系统应用或 Microsoft Store 本身。

> [!IMPORTANT]
> 如果 HoloLens 2 有多个用户，必须以安装该应用的用户身份登录才能进行卸载。

### <a name="uninstall-from-the-microsoft-store"></a>从 Microsoft Store 卸载

从“开始”菜单中打开 Microsoft Store，然后浏览到想要卸载的应用程序。  在 Microsoft Store 页面上，每个已安装应用程序都有一个“卸载”按钮。

### <a name="uninstall-from-the-start-menu"></a>从“开始”菜单中卸载

在“开始”菜单或“所有应用”列表中，浏览到该应用。 选择并保持，直到菜单显示，然后选择“卸载”。

### <a name="uninstall-from-settings"></a>从“设置”中卸载

从“开始”菜单中，选择“设置”>“应用” 。 从列表中找到该应用，选择它，然后单击“卸载”。

如果无法卸载某应用，请通过反馈中心提交[反馈](/hololens/hololens-feedback)。
