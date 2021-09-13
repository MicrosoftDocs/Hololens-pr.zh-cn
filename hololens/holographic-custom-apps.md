---
title: " (第一) 代 HoloLens 管理自定义应用"
description: 了解如何使用设备门户和 Visual Studio 在 HoloLens 设备上安装、卸载和加载自定义全息应用。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens，旁加载，端负载，旁加载，存储，uwp，应用，安装
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
ms.openlocfilehash: b6769c36f821ee3619ac9b62efd637ac561192bb
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032065"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a> (第一) 代 HoloLens 管理自定义应用

HoloLens 支持 Microsoft Store 中的许多现有应用程序以及专门为 HoloLens 构建的新应用程序。 本文重点介绍自定义全息应用程序。  

有关应用商店应用的详细信息，请参阅 [管理应用商店的应用](holographic-store-apps.md)。

> [!IMPORTANT]
> 为第一代) HoloLens (创建了以下信息，同时称为 HoloLens 开发人员版。 作为此类旁加载应用，通过设备门户并通过 Visual Studio 安装应用非常常见。 对于企业部署，我们不建议启用开发人员模式，这两种方法都使用这两种模式。 如果你对安全应用部署方法感兴趣，请查看我们的 [应用管理：概述](app-deploy-overview.md)。
>
> 如果要为 HoloLens 2 设备查找应用程序安装的开发方法，请参阅：
>
> - [设备门户：安装应用](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [使用 Visual Studio 部署和调试应用程序](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>安装自定义应用

你可以通过使用设备门户或通过从 Visual Studio 部署应用，在 HoloLens 上安装自己的应用程序。

### <a name="installing-an-application-package-with-the-device-portal"></a>使用设备门户安装应用程序包

1. 建立从[设备门户](/windows/mixed-reality/using-the-windows-device-portal)到目标 HoloLens 的连接。

1. 在左侧导航栏中，导航到 " **应用** " 页。

1. 在 " **应用包** " 下，浏览到与应用程序关联的 .appx 文件。

   > [!IMPORTANT]
   > 请确保引用任何关联的依赖项和证书文件。

1. 选择“转到”。

   > [!div class="mx-imgBorder"]
   > ![在 Microsoft HoloLens 上 Windows 设备门户中安装应用程序。](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>从 Microsoft Visual Studio 2015 进行部署

1. ) Visual Studio 打开应用的解决方案 ( .sln 文件。

1. 打开项目的 " **属性**"。

1. 选择以下生成配置： **Master/x86/远程计算机**。

1. 选择 " **远程计算机**" 时：
   - 请确保该地址指向 HoloLens 的 Wi-Fi IP 地址。
   - 将身份验证设置为 **通用 (未加密协议)**。
   
1. 生成解决方案。

1. 若要将应用从开发 PC 部署到 HoloLens，请选择 "**远程计算机**"。 如果 HoloLens 上已有现有的生成，请选择 **"是"** 以安装此更新版本。  

   ![要在 Visual Studio 中 Microsoft HoloLens 的应用的远程计算机部署。](images/vs2015-remotedeployment.jpg)  
   
1. 应用程序将在你的 HoloLens 上安装和自动启动。

安装应用后，可在 "**所有应用**" 列表中找到该应用， () **启动**  >  **所有应用**。
