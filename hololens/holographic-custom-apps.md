---
title: 管理 HoloLens 的自定义应用
description: 在 HoloLens 上加载自定义应用程序。 了解有关安装和卸载全息应用的详细信息。
ms.assetid: 6bd124c4-731c-4bcc-86c7-23f9b67ff616
ms.date: 07/01/2019
manager: v-miegge
keywords: hololens、旁加载、端加载、侧面加载、应用商店、uwp、应用、安装
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
- HoloLens 2
ms.openlocfilehash: 12c5eedfab580be8acea48c1fc19b56c1ead08ac
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827868"
---
# 管理 HoloLens 的自定义应用

HoloLens 支持 Microsoft Store 中的许多现有应用程序，以及专为 HoloLens 构建的新应用。 本文重点介绍自定义全息版应用程序。  

有关应用商店应用的详细信息，请参阅[管理应用商店](holographic-store-apps.md)中的应用。

## 安装自定义应用程序

你可以通过使用 Device Portal 或从 Visual Studio 部署应用，在 HoloLens 上安装你自己的应用程序。

### 使用 Device Portal 安装应用程序包

1. 建立从[Device Portal](https://docs.microsoft.com/windows/mixed-reality/using-the-windows-device-portal)到目标 HoloLens 的连接。
1. 在左侧导航中，导航到 "**应用**" 页面。
1. 在 "**应用包**" 下，浏览到与你的应用程序关联的 .appx 文件。
   > [!IMPORTANT]
   > 请确保引用任何关联的相关性和证书文件。

1. 选择 "**转到**"。
   ![Microsoft HoloLens 上的 Windows Device Portal 中的 "安装应用" 表单](images/deviceportal-appmanager.jpg)

### 从 Microsoft Visual Studio 2015 部署

1. 打开应用的 Visual Studio 解决方案（.sln 文件）。
1. 打开项目的**属性**。
1. 选择以下生成配置： "**主/x86/远程计算机**"。
1. 选择 "**远程计算机**" 时：
   - 请确保地址指向 HoloLens 的 Wi-fi IP 地址。
   - 将身份验证设置为**通用（未加密协议）**。
1. 构建您的解决方案。
1. 若要将应用从开发电脑部署到 HoloLens，请选择 "**远程计算机**"。 如果你已有 HoloLens 上的现有版本，请选择 **"是"** 以安装此较新版本。  

   ![Visual Studio 中适用于 Microsoft HoloLens 的应用的远程计算机部署](images/vs2015-remotedeployment.jpg)  
1. 应用程序将在 HoloLens 上安装和自动启动。

安装应用后，你将在 "**所有应用**" 列表（"**启动**  >  **所有应用**"）中找到它。
