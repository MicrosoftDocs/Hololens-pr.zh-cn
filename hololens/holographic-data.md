---
title: 在 HoloLens 上查找和保存文件
description: 了解如何使用 HoloLens 上的文件资源管理器打开、查看和管理混合现实设备上的文件。
keywords: 操作说明， 文件选取器， 文件， 照片， 视频， 图片， OneDrive， 存储， 文件资源管理器， hololens
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
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283523"
---
# 在 HoloLens 上查找、打开和保存文件

你在 HoloLens 上创建的文件（包括照片和视频）直接保存到 HoloLens 设备。 查看和管理这些文件的方式与在 Windows 10 上管理文件的方式相同：

- 使用文件资源管理器应用访问本地文件夹。
- 在应用的存储中。
- 在特殊文件夹中 (例如视频或音乐库) 。
- 使用包含应用和文件选取器的存储服务 (OneDrive) 。
- 使用通过 USB 电缆连接到 HoloLens 的桌面电脑，使用 MTP (媒体传输协议) 支持。

## 使用文件资源管理器查看 HoloLens 上的文件

> 适用于自适用于 [HoloLens 的 Windows 10 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018)年 4 月更新 (RS4) 起的所有 HoloLens 2 设备和 HoloLens (第一代) 。

使用 HoloLens 上的文件资源管理器查看和管理设备上的文件，包括 3D 对象、文档和图片。 转到"**开始**   >  **所有应用**   >  **文件资源管理器**"以开始。

> [!TIP]
> 如果文件资源管理器中未列出任何文件 **，请在左** 上方窗格中选择"此设备"。

如果在文件资源管理器中未看到任何文件，则"最近"筛选器可能处于活动状态， (左窗格中突出显示时钟) 。 若要解决此问题，请在时钟图标**** (下选择"此设备"文档) 或打开菜单并选择 **"此设备"。**

## 查找和查看照片和视频

[混合现实捕获](holographic-photos-and-videos.md) 允许你在 HoloLens 上拍摄混合现实照片和视频。  这些照片和视频将保存到设备的"相机照片"文件夹中。

你可以访问通过 HoloLens 拍摄的照片和视频，

- 通过"照片"应用直接访问 [相机照片](holographic-photos-and-videos.md)。
- 将照片和视频同步到 OneDrive，将照片和视频上传到云存储。
- 使用 Windows Device Portal 的"混合现实捕获 ["页](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)。

### “照片”应用

"照片"应用是"开始"菜单上的默认**** 应用之一，内置于 HoloLens。 详细了解如何 [使用"照片"应用查看内容](holographic-photos-and-videos.md)。

还可以从 Microsoft [Store 安装 OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 应用，将照片同步到其他设备。

### OneDrive 应用

[OneDrive](https://onedrive.live.com/) 允许你访问、管理和与任何设备和任何用户共享照片和视频。 若要访问在 HoloLens 上捕获的照片和视频，请从 HoloLens 上的 Microsoft Store 下载 [OneDrive](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3) 应用。 下载后，打开 OneDrive 应用并选择 **"** 设置相机上载"，  >  **** 然后打开 **"相机上载"。**

### 连接到电脑

如果你的 HoloLens 运行的是 [Windows 10 2018](https://docs.microsoft.com/windows/mixed-reality/release-notes-april-2018) 年 4 月更新或更高版本，可以使用 USB 电缆将 HoloLens 连接到 Windows 10 电脑，以使用 MTP (媒体传输协议) 浏览设备上照片和视频。 如果你在设备上设置了 PIN 或密码，则需要确保设备已解锁以浏览文件。  

如果已启用 Windows [Device Portal，](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)可以使用它浏览、检索和管理设备上存储的照片和视频。

## 访问应用内的文件

如果应用程序将文件保存在设备上，可以使用该应用程序访问这些文件。

### 从另一个应用请求文件

应用程序可以使用文件选取器请求保存文件或从另一个应用 [打开文件](https://docs.microsoft.com/windows/mixed-reality/app-model#file-pickers)。

### 已知文件夹

HoloLens 支持应用可以[](https://docs.microsoft.com/windows/mixed-reality/app-model#known-folders)请求访问权限的多种已知文件夹。

## 在电脑上查看 HoloLens 文件

与其他移动设备类似，使用 MTP (媒体传输协议) 将 HoloLens 连接到台式电脑，然后打开电脑上的文件资源管理器以访问 HoloLens 库，方便转移。

若要在电脑上的文件资源管理器中查看 HoloLens 文件：

1. 登录到 HoloLens，然后使用 HoloLens 所带的 USB 电缆将其插入电脑。

1. 选择 **"打开设备"以使用文件资源管理器**查看文件，或打开电脑上的文件资源管理器并导航到该设备。

若要查看有关 HoloLens 的信息，请在电脑上的文件资源管理器中右键单击设备名称，然后选择"**属性"。**

> [!NOTE]
> HoloLens (第一代) 不支持连接到外部硬盘驱动器或 SD 卡。

## 同步到云

若要将照片和其他文件从 HoloLens 同步到云，请安装和设置 HoloLens 上的 OneDrive。 若要获取 OneDrive，请在你的 HoloLens 上的 Microsoft Store 中搜索它。

HoloLens 不会备份应用文件和数据，因此，建议将重要内容保存到 OneDrive。 这样，如果你重置设备或卸载应用，将备份你的信息。
