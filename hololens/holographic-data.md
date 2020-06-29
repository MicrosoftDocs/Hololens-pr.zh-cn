---
title: 在 HoloLens 上查找和保存文件
description: 使用 HoloLens 上的文件资源管理器查看和管理设备上的文件
keywords: hololens
ms.assetid: 77d2e357-f65f-43c8-b62f-6cd9bf37070a
author: mattzmsft
ms.author: mazeller
manager: v-miegge
ms.reviewer: jarrettrenshaw
ms.date: 12/30/2019
ms.prod: hololens
ms.sitesec: library
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 50a13e1634344bea66bb6b7ce90d9e3fc8c2a783
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827656"
---
# 在 HoloLens 上查找、打开和保存文件

在 HoloLens 上创建的文件（包括照片和视频）将直接保存到 HoloLens 设备。 按照管理 Windows 10 上的文件的方式查看和管理它们：

- 使用文件资源管理器应用访问本地文件夹。
- 在应用的存储中。
- 在特殊文件夹中（如视频或音乐库）。
- 使用包含应用和文件选取器（如 OneDrive）的存储服务。
- 使用 MTP （媒体传输协议）支持，通过使用 USB 电缆连接到 HoloLens 的桌面电脑。

## 使用文件资源管理器在 HoloLens 上查看文件

> 适用于[hololens 的 Windows 10 四月 2018 Update （RS4）](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)的所有 hololens 2 设备和 HoloLens （第1代）。

使用 HoloLens 上的文件资源管理器查看和管理设备上的文件，包括3D 对象、文档和图片。 转到 "**开始**   >  **所有应用**"   >  **文件资源管理器**以开始使用。

> [!TIP]
> 如果文件资源管理器中未列出任何文件，请在顶部左窗格中选择 "**此设备**"。

如果在文件资源管理器中看不到任何文件，则 "最近" 筛选器可能处于活动状态（时钟图标在左窗格中突出显示）。 若要解决此问题，请在左窗格（时钟图标下方）中选择 "**此设备**文档" 图标，或者打开菜单并选择 "**此设备**"。

## 查找和查看您的照片和视频

[混合现实捕获](holographic-photos-and-videos.md)允许你在 HoloLens 上拍摄混合现实照片和视频。  这些照片和视频将保存到设备的 "相机" 滚动文件夹。

你可以通过以下方式访问使用 HoloLens 拍摄的照片和视频：

- 直接通过 "[照片" 应用](holographic-photos-and-videos.md)访问相机的滚动。
- 通过将照片和视频同步到 OneDrive，将照片和视频上载到云存储。
- 使用[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)的混合现实捕获页面。

### “照片”应用

"照片" 应用是 "**开始**" 菜单上的一个默认应用，并附带 HoloLens。 了解有关[使用照片应用查看内容](holographic-photos-and-videos.md)的详细信息。

你还可以从 Microsoft Store 安装[OneDrive 应用](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)以将照片同步到其他设备。

### OneDrive 应用

[OneDrive](https://onedrive.live.com/)允许你使用任何设备和任何用户访问、管理和共享你的照片和视频。 若要访问 HoloLens 上捕获的照片和视频，请从 HoloLens 上的 Microsoft Store 下载[OneDrive 应用](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)。 下载后，打开 OneDrive 应用并选择 "**设置**  >  **相机上载**"，然后打开 "**相机上传**"。

### 连接到电脑

如果你的 HoloLens 运行的是[windows 10 四月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)或更高版本，你可以使用 USB 电缆将 HoloLens 连接到 WINDOWS 10 电脑，方法是使用 MTP （媒体传输协议）浏览设备上的照片和视频。 如果你在设备上设置了 PIN 或密码，你将需要确保设备已解锁才能浏览文件。  

如果你已启用[Windows Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)，则可以使用它来浏览、检索和管理存储在你的设备上的照片和视频。

## 访问应用内的文件

如果应用程序将文件保存在你的设备上，你可以使用该应用程序来访问它们。

### 从另一个应用请求文件

通过使用[文件选取](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)器，应用程序可以请求保存文件或从另一个应用打开文件。

### 已知文件夹

HoloLens 支持应用可请求访问权限的许多[已知文件夹](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders)。

## 在电脑上查看 HoloLens 文件

与其他移动设备类似，使用 MTP （媒体传输协议）将 HoloLens 连接到桌面电脑，并在电脑上打开文件资源管理器以轻松传输。

若要在电脑上的文件资源管理器中查看 HoloLens 文件，请执行以下操作：

1. 登录 HoloLens，然后使用 HoloLens 随附的 USB 电缆将其插入电脑。

1. 选择 "**打开设备" 以查看文件资源管理器**中的文件，或打开电脑上的文件资源管理器并导航到该设备。

若要查看有关 HoloLens 的信息，请在电脑上的文件资源管理器中右键单击设备名称，然后选择 "**属性**"。

> [!NOTE]
> HoloLens （第1代）不支持连接到外部硬盘驱动器或 SD 卡。

## 同步到云

若要将你的 HoloLens 中的照片和其他文件与云同步，请在 HoloLens 上安装并设置 OneDrive。 若要获取 OneDrive，请在 HoloLens 上的 Microsoft Store 中搜索它。

HoloLens 不备份应用文件和数据，因此最好将重要资料保存到 OneDrive。 这样，如果重置设备或卸载应用，则将备份你的信息。
