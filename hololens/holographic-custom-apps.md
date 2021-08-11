---
title: '管理第一代HoloLens (自定义) '
description: 了解如何使用 设备门户 和 Visual Studio 在 HoloLens 设备上安装、卸载和旁加载自定义全息Visual Studio。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 12/10/2020
manager: v-miegge
keywords: hololens， sideload， side load， side-load， store， uwp， app， install
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
ms.openlocfilehash: 7d564fd00567033060428d5b47b34ddf827dea2fdeeb8955c73bc22e4ba87164
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115664940"
---
# <a name="manage-custom-apps-for-hololens-1st-gen"></a>管理第一代HoloLens (自定义) 

HoloLens支持来自 Microsoft Store 的许多现有应用程序，以及专为 HoloLens。 本文重点介绍自定义全息应用程序。  

有关应用商店应用的信息，请参阅 [使用应用商店管理应用](holographic-store-apps.md)。

> [!IMPORTANT]
> 为第一代HoloLens (创建了以下信息) ，HoloLens开发人员版。 因此，通过设备门户旁加载应用和通过 Visual Studio应用是很常见的。 对于企业部署，我们不建议启用这两种方法都使用的开发人员模式。 如果对安全应用部署方法感兴趣，请查看我们的应用 [管理：概述](app-deploy-overview.md)。
>
> 若要查找适用于设备的应用安装开发人员方法HoloLens 2请参阅：
>
> - [设备门户：安装应用](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-the-windows-device-portal#installing-an-app)
> - [使用Visual Studio部署和调试应用](/windows/mixed-reality/develop/platform-capabilities-and-apis/using-visual-studio)

## <a name="install-custom-apps"></a>安装自定义应用

可以通过使用 HoloLens 或从 设备门户 部署应用，在 Visual Studio。

### <a name="installing-an-application-package-with-the-device-portal"></a>使用客户端安装应用程序设备门户

1. 建立[从目标设备门户](/windows/mixed-reality/using-the-windows-device-portal)到目标HoloLens。

1. 在左侧导航栏中，导航到"应用 **"** 页。

1. 在 **"应用包** "下，浏览到与应用程序关联的 .appx 文件。

   > [!IMPORTANT]
   > 请确保引用任何关联的依赖项和证书文件。

1. 选择“转到”。

   > [!div class="mx-imgBorder"]
   > ![在 Microsoft HoloLens 上的 Windows 设备门户 中安装应用Microsoft HoloLens](images/deviceportal-appmanager.jpg)

### <a name="deploying-from-microsoft-visual-studio-2015"></a>从 2015 Microsoft Visual Studio部署

1. 打开应用的 Visual Studio 解决方案 (.sln) 。

1. 打开项目的"属性 **"。**

1. 选择以下生成配置 **：Master/x86/Remote Machine**。

1. 选择"远程 **计算机"时**：
   - 请确保地址指向Wi-Fi IP 地址HoloLens。
   - 将身份验证设置为 **"通用 (未加密协议) "**。
   
1. 生成解决方案。

1. 若要将应用从开发电脑部署到 HoloLens，请选择"远程 **计算机"。** 如果已在应用程序上拥有现有HoloLens，请选择"是"以安装此较新版本。  

   ![远程计算机部署，使应用Microsoft HoloLens Visual Studio](images/vs2015-remotedeployment.jpg)  
   
1. 应用程序将在你的客户端上安装并HoloLens。

安装应用后，你将在"所有应用&quot;列表中找到该应用， (&quot;启动所有  >  **应用") 。**
