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
# 通过应用安装程序在 HoloLens 2 上安装应用

现在，用户现在可以通过 Appx 捆绑安装应用，而无需启用开发人员模式或使用 Device Portal。 此体验对于在本地设备上安装应用或与其他不熟悉 HoloLens 上的其他应用安装方法的其他人共享应用很简单。 

> [!IMPORTANT]
> 此功能目前仅在 Windows 预览体验计划内部版本19041.1377 中 avalible。 [了解有关如何在 Windows 预览体验计划内部版本中注册的详细信息](hololens-insider.md)。

> [!NOTE]
> 你的应用的解决方案配置必须是 " **主** " 或 " **发布** "，因为应用安装程序将使用应用商店中的依赖关系。 查看有关 [创建应用包](https://docs.microsoft.com/windows/msix/app-installer/create-appinstallerfile-vs)的详细信息。

1.  确保 HoloLens 2 设备已开机且已登录。
1.  在你的电脑上导航到你的自定义应用，并将 yourapp 复制到 yourdevicename\Internal Storage\Downloads。 
    完成文件复制后，您可能会断开您的设备并在以后完成安装。
1.  从 HoloLens 2 设备打开 " **开始" 菜单**，选择 " **所有应用** "，然后启动 " **文件资源管理器** " 应用。
1.  导航到 "下载" 文件夹。 你可能需要在应用的左侧面板上，选择 " **此设备** "，然后导航到 "下载"。
1.  选择 yourapp 文件。 
1.  应用安装程序将启动。 选择 " **安装** " 按钮以安装你的应用。 

已安装的应用将在安装完成后自动启动。 

![通过应用安装程序安装 MRTK 示例](images/hololens-app-installer-picture.jpg)

如果你的应用无法安装，请检查以下内容：
-   你的应用是 "主" 或 "发布" 内部版本。
-   您已 [连接到 internet](hololens-network.md)。
-   已正确配置 [Microsoft Store 的终结点](hololens-offline.md) 。  
