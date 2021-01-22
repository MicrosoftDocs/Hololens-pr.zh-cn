---
title: '管理 HoloLens 第一代 (自定义) '
description: 了解如何使用 Device Portal 和 Visual Studio 在 HoloLens 设备上安装、卸载和旁加载自定义全息Visual Studio。
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
ms.openlocfilehash: 721c169c8ad34acab6914448af8ffc6ceec97a0e
ms.sourcegitcommit: 4c6d982bee72195bef955532738711f2b00ac8be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "11296985"
---
# 管理 HoloLens 第一代 (自定义) 

HoloLens 支持 Microsoft Store 中的许多现有应用程序，以及专为 HoloLens 构建的新应用。 本文重点介绍自定义全息应用程序。  

有关应用商店应用详细信息，请参阅使用应用商店 [管理应用](holographic-store-apps.md)。

> [!IMPORTANT]
> 为 HoloLens 第一代 (创建以下信息) 当时也称为 HoloLens Developer Edition。 因此，通过设备门户旁加载应用和通过 Visual Studio安装应用很常见。 对于企业部署，我们不建议启用开发人员模式，这两种方法都使用开发人员模式。 如果你对安全应用部署方法感兴趣，请查看我们的 [应用管理：概述](app-deploy-overview.md)。
>
> 如果你正在寻找适用于 HoloLens 2 设备的应用安装的开发人员方法，请参阅：
> - [Device Portal：安装应用](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [使用 Visual Studio 部署和调试应用](https://docs.microsoft.com/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## 安装自定义应用

可以使用 Device Portal 或部署 HoloLens 中的应用，在 HoloLens 上Visual Studio。

### 使用 Device Portal 安装应用程序包

1. 建立从 [Device Portal 到](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal) 目标 HoloLens 的连接。

1. 在左侧导航中，导航到 **"应用"** 页。

1. 在 **"应用** 包"下，浏览到与应用程序关联的 .appx 文件。

   > [!IMPORTANT]
   > 确保引用任何关联的依赖项和证书文件。

1. 选择 **"转到"。**

   > [!div class="mx-imgBorder"]
   > ![在 Microsoft HoloLens 上的 Windows Device Portal 中安装应用表单](images/deviceportal-appmanager.jpg)

### 从 Microsoft Visual Studio 2015 部署

1. 打开应用的 Visual Studio 解决方案 (.sln 文件) 。

1. 打开项目 **的属性**。

1. 选择以下生成配置 **：Master/x86/Remote Machine。**

1. 选择远程 **计算机时**：
   - 确保地址指向 HoloLens Wi-Fi IP 地址。
   - 将身份验证设置为**通用 (未加密协议) 。 **
   
1. 生成解决方案。

1. 若要将应用从开发电脑部署到 HoloLens，请选择 **"远程计算机"。** 如果 HoloLens 上已有内部版本，请选择"是****"以安装此较新版本。  

   ![将应用远程计算机部署到 Microsoft HoloLens Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. 应用程序将在 HoloLens 上安装和自动启动。

安装应用后，你将在"所有应用"列表中找到它********  >  **， ("所有应用) 。**
