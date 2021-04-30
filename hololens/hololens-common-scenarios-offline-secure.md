---
title: 常见方案–脱机安全 HoloLens 2
description: 了解如何设置适用于 HoloLens 设备的脱机安全部署和应用部署方案。
keywords: HoloLens、管理、脱机、脱机安全
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
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308172"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>常见方案–脱机安全 HoloLens 2

## <a name="overview"></a>概述

本指南提供了有关应用示例预配包的指导，该设置包将锁定 HoloLens 2 以便在安全环境中使用，但有以下限制：

-   禁用 WiFi。
-   禁用蓝牙。
-   禁用麦克风。
-   阻止添加或删除预配包。
-   任何用户都不能启用上述任何受限制的组件。

## <a name="prepare"></a>准备

Windows 10 电脑安装程序
1. 将[最新的 HoloLens 2 OS 文件直接下载](https://aka.ms/hololens2download)到 PC。 
   1. 版本19041.1117 及更高版本中包含了对此配置的支持。
1. [从 Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)到 PC 下载/安装高级恢复助理 (ARC) 工具
1. 下载/安装最新的 [Windows 配置设计器 (WCD) ](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 工具从 MICROSOFT STORE 到 PC。
1. [下载包含项目文件的 OfflineSecureHL2_Sample 文件夹](https://aka.ms/HoloLensDocs-SecureOfflineSample) 以生成 PPKG。
1. 准备 [PPKG 部署的脱机业务线应用程序](app-deploy-provisioning-package.md)。 


## <a name="configure"></a>配置

构建安全配置预配包

1. 在电脑上启动 WCD 工具。
1. 选择 " **文件-> 打开项目**"。
  1. 导航到之前保存的 OfflineSecureHL2_Sample 文件夹的位置，并选择： OfflineSecureHL2_Sample.icdproj.xml
1. 项目应会打开，此时应会显示一个可用自定义项列表：

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中打开的配置包的屏幕截图](images/offline-secure-sample-wcd.png)

   此预配包中设置的配置：
   
   |     项                                                |     设置                       |     描述                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     帐户/用户                                    |     本地用户名 & 密码    |     对于这些脱机设备，需要为设备的所有用户设置和共享单个用户名和密码。          |
   |     首次体验/HoloLens/SkipCalibration       |     True                          |     仅在初始设备安装过程中跳过校准                                                                             |
   |     首次体验/HoloLens/SkipTraining          |     True                          |     初始设备安装过程中跳过设备培训                                                                              |
   |     首次体验/HoloLens/WiFi                  |     True                          |     初始设备安装过程中跳过 Wi-Fi 配置                                                                                 |
   |     策略/连接/AllowBluetooth                |     否                            |     禁用蓝牙                                                                                                             |
   |     策略/体验/AllowCortana                    |     否                            |     禁用 Cortana (以消除在禁用麦克风后出现的潜在问题)                                           |
   |     策略/MixedReality/MicrophoneDisabled            |     是                           |     禁用麦克风                                                                                                            |
   |     策略/隐私/LetAppsAccessLocation              |     强制拒绝                    |     阻止应用尝试访问位置数据 (以消除潜在问题，因为已禁用位置跟踪)     |
   |     策略/隐私/LetAppsAccessMicrophone            |     强制拒绝                    |     阻止应用尝试访问麦克风 (以消除在禁用麦克风后出现的潜在问题)            |
   |     策略/安全性/AllowAddProvisioningPackage       |     否                            |     阻止任何人添加可能尝试替代锁定策略的预配包。                         |
   |     策略/安全性/AllowRemoveProvisioningPackage    |     否                            |     阻止任何人删除此锁定的预配包。                                                           |
   |     策略/System/AllowLocation                       |     否                            |     阻止设备尝试跟踪位置数据。                                                                        |
   |     策略/WiFi/AllowWiFi                             |     否                            |     禁用 Wi-Fi                                                                                                                 |

1. 在 "运行时设置" 下，选择 " **帐户/用户/用户名： Holo/Password**"。

   记下密码，并根据需要重置。

1. 导航到 UniversalAppInstall/UserContextApp，并配置将部署到这些设备 [的 LOB 应用](app-deploy-provisioning-package.md) 。

   > [!div class="mx-imgBorder"]
   > ![用于在 WCD 中添加应用程序的屏幕截图。](images/offline-secure-sample-wcd-usercontextapp2.png)

1. 完成后，选择 "导出" 按钮并按照所有提示操作，直到创建了预配包。

   > [!div class="mx-imgBorder"]
   > ![WCD 中此包的 "导出" 按钮的屏幕截图。](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>部署

1. 通过 USB 电缆将 HL2 连接到 Windows 10 电脑。
1. 启动 "ARC" 工具，然后选择 " **HoloLens 2** "

   ![HoloLens 2 清理刷新初始屏幕](images/ARC2.png)

1. 在下一个屏幕上，选择 " **手动包选择**"。

   ![HoloLens 2 ARC 信息屏幕](images/arc_device_info.png)

1. 导航到以前下载的 ffu 文件，然后选择 " **打开**"。
1. 在警告页面上，选择 " **继续**"。

   ![HoloLens 2 ARC 警告屏幕](images/arc_warning.png)

1. 等待 ARC 工具完成 HoloLens 2 操作系统安装。
1. 设备完成安装并重新启动后，从电脑导航到文件资源管理器，并将以前保存的 PPKG 文件复制到设备文件夹中。

   > [!div class="mx-imgBorder"]
   > ![文件资源管理器窗口中的 PC 上的 PPKG 文件。](images/offline-secure-file-explorer.png)

1. 在 HoloLens 2 上，按以下按钮组合运行预配包：点击 " **关闭** " 和 " **电源" 按钮** 。
1. 系统将提示你应用预配包，并选择 "**确认**"
1. 预配包完成后，请选择 **"确定"**。
1. 然后，系统将提示你通过共享本地帐户和密码登录到设备。

## <a name="maintain"></a>维护

使用此配置时，建议重启上述过程，并使用 ARC 工具刷新设备，并应用新的 PPKG 来对 OS 和/或应用程序进行任何 () 的更新。
