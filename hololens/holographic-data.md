---
title: 在 HoloLens 上查找并保存文件
description: 了解如何在 HoloLens 上使用文件资源管理器打开、查看和管理混合现实设备上的文件。
keywords: 操作说明，文件选取器，文件，照片，视频，图片，OneDrive，存储，文件资源管理器，hololens
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
ms.openlocfilehash: 2d979b2cffd20589ddef7f11db5c7206eaea23cb
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308185"
---
# <a name="find-open-and-save-files-on-hololens"></a>在 HoloLens 上查找、打开和保存文件

在 HoloLens 上创建的文件（包括照片和视频）将直接保存到 HoloLens 设备上。 以在 Windows 10 上管理文件的相同方式查看和管理它们：

- 使用文件资源管理器应用程序访问本地文件夹。
- 在应用的存储中。
- 在特殊文件夹中 (如 "视频" 或 "音乐库") 。
- 使用包含应用程序和文件选取器 (如 OneDrive) 的存储服务。
- 使用 USB 电缆连接到 HoloLens 的台式 PC，使用 MTP (媒体传输协议) 支持。

## <a name="view-files-on-hololens-using-file-explorer"></a>使用文件资源管理器在 HoloLens 上查看文件

> 适用于所有 HoloLens 2 设备和 HoloLens (第一代) ，从 [Windows 10 2018 年4月版更新 (RS4) ](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)。

使用 HoloLens 上的文件资源管理器来查看和管理设备上的文件，包括3D 对象、文档和图片。 转到 "**启动**   >  **所有应用**   >  **文件资源管理器**" 开始。

> [!TIP]
> 如果文件资源管理器中没有列出任何文件，请在左上方窗格中选择 **此设备** 。

如果在文件资源管理器中看不到任何文件，则 "最近的" 筛选器可能处于活动状态 (时钟图标在左窗格中突出显示) "。 若要解决此问题，请在左窗格中选择 " **此设备** 文档" 图标 (时钟图标) 下，或打开菜单并选择 " **此设备**"。

## <a name="find-and-view-your-photos-and-videos"></a>查找并查看你的照片和视频

[混合现实捕获](holographic-photos-and-videos.md) 允许在 HoloLens 上利用混合现实照片和视频。  这些照片和视频将保存到设备的 "相机" 滚动文件夹中。

可以通过以下方式访问使用 HoloLens 拍摄的照片和视频：

- 直接访问相机 [应用程序](holographic-photos-and-videos.md)的照相机。
- 通过将照片和视频同步到 OneDrive，将照片和视频上传到云存储。
- 使用 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)的混合现实捕获页。

### <a name="photos-app"></a>“照片”应用

照片应用是 " **开始** " 菜单上的默认应用之一，并内置于 HoloLens。 了解有关 [使用照片应用查看内容的](holographic-photos-and-videos.md)详细信息。

你还可以从 Microsoft Store 安装 [OneDrive 应用](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) ，将照片同步到其他设备。

### <a name="onedrive-app"></a>OneDrive 应用

[OneDrive](https://onedrive.live.com/) 允许你使用任何设备和任何用户访问、管理和共享你的照片和视频。 若要访问在 HoloLens 上捕获的照片和视频，请从你的 HoloLens Microsoft Store 下载 [OneDrive 应用](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 。 下载完成后，打开 OneDrive 应用并选择 "**设置**  >  " "**相机上传**"，并打开 "**相机上传**"。

### <a name="connect-to-a-pc"></a>连接到电脑

如果你的 HoloLens 正在运行 [windows 10 四月2018更新](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 或更高版本，则可以使用 USB 电缆将你的 hololens 连接到 WINDOWS 10 电脑，使用 MTP (媒体传输协议) 来浏览设备上的照片和视频。 如果已在设备上设置 PIN 或密码，则需要确保设备处于解锁状态才能浏览文件。  

如果已启用 [Windows 设备门户](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)，则可以使用它来浏览、检索和管理存储在设备上的照片和视频。

## <a name="access-files-within-an-app"></a>访问应用中的文件

如果应用程序将文件保存在你的设备上，则可以使用该应用程序进行访问。

### <a name="requesting-files-from-another-app"></a>从其他应用程序请求文件

应用程序可以请求使用 [文件选取](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)器来保存文件或从另一个应用打开文件。

### <a name="known-folders"></a>已知文件夹

HoloLens 支持多个 [已知文件夹](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders) ，应用程序可以请求访问权限。

## <a name="view-hololens-files-on-your-pc"></a>查看 PC 上的 HoloLens 文件

类似于其他移动设备，使用 MTP 将 HoloLens 连接到桌面 PC (媒体传输协议) 并打开电脑上的文件资源管理器，以便轻松地进行传输。

若要在计算机上的文件资源管理器中查看 HoloLens 文件：

1. 登录到 HoloLens，并使用 HoloLens 附带的 USB 电缆将其插入 PC。

1. 选择 " **打开设备" 以通过文件资源管理器查看文件**，或打开电脑上的文件资源管理器并导航到该设备。

若要查看有关 HoloLens 的信息，请在计算机上的文件资源管理器中右键单击设备名称，然后选择 " **属性**"。

> [!NOTE]
> HoloLens (第一代) 不支持连接到外部硬盘驱动器或 SD 卡。

## <a name="sync-to-the-cloud"></a>同步到云

若要将照片和其他文件从 HoloLens 同步到云，请在 HoloLens 上安装和设置 OneDrive。 若要获取 OneDrive，请在你的 HoloLens Microsoft Store 中搜索它。

HoloLens 不会备份应用文件和数据，因此最好将重要内容保存到 OneDrive。 这样一来，如果重置设备或卸载应用，则会备份信息。
