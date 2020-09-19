---
title: 如何通过 web 安装程序安装应用
description: 通过适用于应用安装程序的 web installer 安装应用
keywords: 应用管理、应用、hololens、应用安装程序、web 安装
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
ms.openlocfilehash: 186cbefb2822455dcf922804ea09533b833b8663
ms.sourcegitcommit: 4ad9b6c73913808175b1a448d2be9e33592f65af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "11027457"
---
# 从网页安装应用

用户可以直接从 web 服务器安装应用。 这会将应用安装程序与轻松下载和安装分发方法结合使用。 

> [!IMPORTANT]
> 此功能目前仅在 Windows 预览体验计划内部版本19041.1366 中 avalible。 [了解有关如何在 Windows 预览体验计划内部版本中注册的详细信息](hololens-insider.md)。

## 如何进行设置：
1.  确保你的应用已正确配置为安装。
1.  请按照以下 [步骤在网页上启用此操作](https://docs.microsoft.com/windows/msix/app-installer/installing-windows10-apps-web#how-to-enable-this-on-a-webpage)。 
1.  选择证书部署方法。 
    1.  [预配程序包](hololens-provisioning.md) 可应用于本地设备。
    1.  可以使用 MDM [将证书应用于设备配置](https://docs.microsoft.com/mem/intune/protect/certificates-configure)。
    1.  使用 "设备 [证书管理器](hololens-insider.md#certificate-manager)"。 

## 最终用户体验：
1.  用户使用之前选择的方法接收和安装设备证书。 
1.  用户访问上述步骤中创建的 URL。

该应用现在将安装到设备。 若要查找应用，请打开 " **开始" 菜单** ，然后选择 " **所有应用** " 按钮以查找你的应用。 

-   有关此安装方法的疑难解答帮助，请访问 [应用安装程序问题疑难解答](https://docs.microsoft.com/windows/msix/app-installer/troubleshoot-appinstaller-issues)。 

> [!NOTE]
> 更新过程中不支持 UI。 因此，不支持 [此页面](https://docs.microsoft.com/windows/msix/app-installer/update-settings) 上的 ShowPrompt 选项和相关选项。
