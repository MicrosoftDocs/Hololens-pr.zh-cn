---
title: 查找并保存HoloLens
description: 了解如何在 文件资源管理器 上HoloLens，以打开、查看和管理混合现实设备上的文件。
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
ms.openlocfilehash: 18dc962b869dafaea9ff9c605eef51fcbb35bfb2
ms.sourcegitcommit: c43cd2f450b643ad4fc8e749235d03ec5aa3ffcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "113636174"
---
# <a name="find-open-and-save-files-on-hololens"></a>在 HoloLens 上查找、打开和保存文件

在设备上创建HoloLens文件（包括照片和视频）将直接保存到HoloLens设备。 查看和管理这些文件的方式与管理文件存储Windows 10：

- 使用文件资源管理器访问本地文件夹。
- 在应用的存储中。
- 在特殊文件夹中 (例如视频或音乐库) 。
- 使用包含应用和文件选取器的存储服务 (例如OneDrive) 。
- 使用通过 USB 电缆连接到HoloLens电脑，使用 MTP (媒体传输协议) 支持。

## <a name="view-files-on-hololens-using-file-explorer"></a>使用 HoloLens 查看文件资源管理器

> 适用于自 HoloLens) HoloLens 2 [2018](/windows/mixed-reality/release-notes-april-2018)年 4 月 Windows 10 日更新 (RS4) 起的所有 HoloLens (设备和第一代 HoloLens。

在文件资源管理器上HoloLens查看和管理设备上的文件，包括 3D 对象、文档和图片。 转到"   >  **开始所有应用**   >  **文件资源管理器** 开始。

> [!TIP]
> 如果未列出任何文件，文件资源管理器左上方 **窗格中选择"** 此设备"。

如果未在左侧窗格中看到任何文件，文件资源管理器"最近"筛选器可能处于活动状态， (左窗格中突出显示时钟) 。 若要解决此问题，请选择左窗格中的"此设备"文档 (位于时钟图标下方，) 菜单并选择"**此设备"。**

## <a name="find-and-view-your-photos-and-videos"></a>查找和查看你的照片和视频

[通过混合现实](holographic-photos-and-videos.md)捕获，可以在 HoloLens 上拍摄混合现实HoloLens。  这些照片和视频将保存到设备的 Camera Roll 文件夹中。

可以通过访问使用设备拍摄的照片HoloLens：

- 直接通过照片应用 访问[相机滚动。](holographic-photos-and-videos.md)
- 将照片和视频同步到云存储，将OneDrive。
- 使用 混合现实捕获 的 Windows 设备门户[页](/windows/mixed-reality/using-the-windows-device-portal#mixed-reality-capture)。

### <a name="photos-app"></a>“照片”应用

照片应用是"开始"菜单上的默认应用之一，内置有HoloLens。 详细了解使用 [照片应用查看内容](holographic-photos-and-videos.md)。

还可以从设备[OneDrive应用](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)，Microsoft Store照片同步到其他设备。

### <a name="onedrive-app"></a>OneDrive 应用

[OneDrive](https://onedrive.live.com/)允许访问、管理和与任何设备以及任何用户共享你的照片和视频。 若要访问在 HoloLens 上捕获的HoloLens，请从 OneDrive[上的](https://www.microsoft.com/p/onedrive/9wzdncrfj1p3)Microsoft Store 下载HoloLens。 下载后，打开 OneDrive 应用并选择"设置  >  **相机上传"，** 然后打开"**相机上传"。**

### <a name="connect-to-a-pc"></a>连接电脑

如果 HoloLens 运行[Windows 10 2018](/windows/mixed-reality/release-notes-april-2018)年 4 月更新或更高版本，可以使用 USB 电缆将 HoloLens 连接到 Windows 10 电脑，以使用 MTP (媒体传输协议) 浏览设备上的照片和视频。 如果在设备上设置了 PIN 或密码，则需要确保设备已解锁以浏览文件。  

如果已启用 Windows 设备门户，[](/windows/mixed-reality/using-the-windows-device-portal)可以使用它浏览、检索和管理设备上存储的照片和视频。

## <a name="access-files-within-an-app"></a>访问应用中的文件

如果应用程序将文件保存在设备上，可以使用该应用程序来访问它们。

### <a name="requesting-files-from-another-app"></a>从另一个应用请求文件

应用程序可以使用文件选取器 请求保存文件或从另一个应用 [打开文件](/windows/mixed-reality/app-model#file-pickers)。

### <a name="known-folders"></a>已知文件夹

HoloLens支持应用可以请求[访问权限](/windows/mixed-reality/app-model#known-folders)的多种已知文件夹。

## <a name="view-hololens-files-on-your-pc"></a>查看HoloLens电脑上的文件

与其他移动设备类似，HoloLens MTP (媒体传输协议) 连接到台式电脑，在电脑上打开 文件资源管理器 以访问 HoloLens 库，方便传输。

若要在电脑上HoloLens查看文件资源管理器文件，请运行：

1. 登录到 HoloLens，然后使用设备随设备一起连接的 USB 电缆将其插入电脑HoloLens。

1. 选择 **"打开设备"以查看** 文件资源管理器，或在电脑上打开文件资源管理器并导航到设备。

若要查看有关HoloLens的信息，请右键单击电脑上文件资源管理器中的设备名称，然后选择"属性 **"。**

> [!NOTE]
> HoloLens (第一代) 不支持连接到外部硬盘驱动器或 SD 卡。

## <a name="sync-to-the-cloud"></a>同步到云

若要将照片和其他文件从HoloLens同步到云，请安装并设置OneDrive HoloLens。 若要获取OneDrive，请在你的Microsoft Store中搜索HoloLens。

HoloLens不会备份应用文件和数据，因此建议保存重要内容以OneDrive。 这样一来，如果重置设备或卸载应用，将备份信息。
