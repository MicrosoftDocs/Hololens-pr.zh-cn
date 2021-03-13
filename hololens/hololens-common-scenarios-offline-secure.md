---
title: 常见方案 – 脱机安全 HoloLens 2
description: 了解如何使用 HoloLens 设备的预配设置脱机安全部署应用部署方案。
keywords: HoloLens， 管理， 脱机， 脱机安全
ms.date: 9/25/2020
manager: yannisle
ms.prod: hololens
ms.sitesec: library
author: evmill
ms.author: v-evmill
ms.reviewer: aboeger
ms.topic: article
audience: ITPro
ms.localizationpriority: medium
appliesto:
- HoloLens 2
ms.openlocfilehash: 7eb084d3de222581fd2b97eaa1c1e2812310810c
ms.sourcegitcommit: 04b7e789fe69615a60571b769e13a01a9d7aee70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2021
ms.locfileid: "11407570"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>常见方案 – 脱机安全 HoloLens 2

## <a name="overview"></a>概述

本指南提供有关应用示例预配包的指南，该预配包将锁定 HoloLens 2，以在具有以下限制的安全环境中使用：

-   禁用 WiFi。
-   禁用蓝牙。
-   禁用麦克风。
-   阻止添加或删除预配包。
-   任何用户都不得启用上述任何受限组件。

## <a name="prepare"></a>准备

Windows 10 电脑安装程序
1. [将最新的 HoloLens 2 操作系统文件](https://aka.ms/hololens2download) 直接下载到电脑。 
   1. 内部版本 19041.1117 及以上版本中包含对此配置的支持。
1. 将高级恢复助手 (ARC) 工具 [从 Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8) 下载/安装到电脑
1. 将最新的 Windows [配置设计器 (WCD) ](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 工具从 Microsoft Store 下载到电脑。
1. [下载OfflineSecureHL2_Sample文件生成](https://aka.ms/HoloLensDocs-SecureOfflineSample) PPKG 的项目文件夹。
1. 为 [PPKG 部署准备脱机业务线应用程序](app-deploy-provisioning-package.md)。 


## <a name="configure"></a>配置

生成安全配置预配包

1. 在电脑上启动 WCD 工具。
1. 选择 **文件 ->打开项目**。
  1. 导航到之前保存的 OfflineSecureHL2_Sample 文件夹的位置，然后选择：OfflineSecureHL2_Sample.icdproj.xml
1. 项目应该会打开，并且你现在应该具有可用自定义项的列表：

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中打开的配置包的屏幕截图](images/offline-secure-sample-wcd.png)

   在此预配包中设置的配置：
   
   |     项目                                                |     设置                       |     说明                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     帐户/用户                                    |     本地用户名&密码    |     对于这些脱机设备，该设备的所有用户都需要设置和共享一个用户名和密码。          |
   |     首次体验 / HoloLens / SkipCalibration       |     True                          |     仅在初始设备设置期间跳过校准                                                                             |
   |     首次体验/HoloLens/SkipTraining          |     True                          |     在初始设备设置期间跳过设备培训                                                                              |
   |     首次体验 / HoloLens / WiFi                  |     True                          |     在Wi-Fi安装期间跳过配置                                                                                 |
   |     Policies/Connectivity/AllowBluetooth                |     否                            |     禁用Bluetooth                                                                                                             |
   |     策略/体验/AllowCortana                    |     否                            |     禁用 Cortana (消除潜在的问题，因为麦克风已禁用)                                           |
   |     Policies/MixedReality/MicrophoneDisabled            |     是                           |     禁用麦克风                                                                                                            |
   |     Policies/Privacy/LetAppsAccessLocation              |     强制拒绝                    |     阻止应用尝试访问位置 (消除潜在的问题，因为位置跟踪功能已)     |
   |     Policies/Privacy/LetAppsAccessMicrophone            |     强制拒绝                    |     阻止应用尝试访问麦克风 (消除潜在的问题，因为麦克风已被禁用)            |
   |     Policies/Security/AllowAddProvisioningPackage       |     否                            |     阻止任何人添加可能尝试覆盖锁定策略的预配包。                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     否                            |     阻止任何人删除此锁定的预配包。                                                           |
   |     Policies/System/AllowLocation                       |     否                            |     阻止设备尝试跟踪位置数据。                                                                        |
   |     Policies/WiFi/AllowWiFi                             |     否                            |     禁用Wi-Fi                                                                                                                 |

1. 在"运行时设置"下，**选择"帐户/用户/用户名：Holo/密码"。**

   记下密码并重置（如果需要）。

1. 导航到 UniversalAppInstall / UserContextApp 并配置你将部署到这些设备的 [LOB](app-deploy-provisioning-package.md) 应用。

   > [!div class="mx-imgBorder"]
   > ![有关在 WCD 中添加应用位置的屏幕截图。](images/offline-secure-sample-wcd-usercontextapp2.png)

1. 完成后，选择"导出"按钮并按照所有提示操作，直到创建预配包。

   > [!div class="mx-imgBorder"]
   > ![WCD 中此程序包的"导出"按钮的屏幕截图。](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>部署

1. 通过 USB 电缆将 HL2 连接到 Windows 10 电脑。
1. 启动 ARC 工具并选择 **HoloLens 2**

   ![HoloLens 2 干净重刷初始屏幕](images/ARC2.png)

1. On the next screen select **Manual package selection**.

   ![HoloLens 2 ARC 信息屏幕](images/arc_device_info.png)

1. 导航到之前下载的 .ffu 文件，然后选择"打开 **"。**
1. 在"警告"页面上，选择"继续 **"。**

   ![HoloLens 2 ARC 警告屏幕](images/arc_warning.png)

1. 等待 ARC 工具完成 HoloLens 2 操作系统安装。
1. 设备完成安装和启动后，从电脑导航到"文件资源管理器"，将之前保存的 PPKG 文件复制到设备文件夹。

   > [!div class="mx-imgBorder"]
   > !["文件资源管理器"窗口中电脑上的 PPKG 文件。](images/offline-secure-file-explorer.png)

1. 在 HoloLens 2 上，按以下按钮组合以运行预配包 **：同时点击** "降低音量"和" **电源** 按钮"。
1. 系统将提示你应用预配包， **选择确认**
1. 预配包完成后，选择"确定 **"。**
1. 然后，系统将提示你使用共享的本地帐户和密码登录设备。

## <a name="maintain"></a>维护

借助此配置，建议重启上述过程，使用 ARC 工具重新更改设备，并应用新的 PPKG 对操作系统和/或应用程序进行 (更新) 。
