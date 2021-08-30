---
title: 常见方案 - 脱机安全HoloLens 2
description: 了解如何使用预配为设备设置脱机安全部署HoloLens方案。
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
ms.openlocfilehash: 10d1955249630202a05fbf2057e1d175855ce0b5
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189114"
---
# <a name="common-scenarios--offline-secure-hololens-2"></a>常见方案 - 脱机安全HoloLens 2

## <a name="overview"></a>概述

本指南提供有关应用示例预配包的指导，该包将锁定HoloLens 2，以在安全环境中使用，但具有以下限制：

-   禁用 WiFi。
-   禁用蓝牙。
-   禁用麦克风。
-   阻止添加或删除预配包。
-   任何用户都不得启用上述任何受限组件。

[![脱机安全方案。 ](./images/deployment-guides-revised-scenario-c-01.png)](./images/deployment-guides-revised-scenario-c-01.png#lightbox)

## <a name="prepare"></a>准备

Windows 10电脑设置
1. [将最新的 HoloLens 2 OS 文件](https://aka.ms/hololens2download)直接下载到电脑。 
   1. 内部版本 19041.1117 及以上版本中包含对此配置的支持。
1. 从电脑下载/安装 (ARC) 工具[Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)高级恢复助手工具
1. 将 WCD Windows工具Windows/ ([WCD) ](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab)工具Microsoft Store到电脑。
1. [下载OfflineSecureHL2_Sample文件的文件夹以](https://aka.ms/HoloLensDocs-SecureOfflineSample) 生成 PPKG。
1. 为 [PPKG 部署 准备脱机业务线应用程序](app-deploy-provisioning-package.md)。 


## <a name="configure"></a>配置

生成安全配置预配包

1. 在电脑上启动 WCD 工具。
1. 选择 **"文件"->打开项目 "。**
  1. 导航到以前保存的 OfflineSecureHL2_Sample 文件夹的位置，然后选择：OfflineSecureHL2_Sample.icdproj.xml
1. 项目应打开，现在应具有可用自定义项的列表：

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中打开的配置包的屏幕截图。](images/offline-secure-sample-wcd.png)

   此预配包中设置的配置：
   
   |     项目                                                |     设置                       |     说明                                                                                                                    |
   |---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
   |     帐户/用户                                    |     本地用户名&密码    |     对于这些脱机设备，需要设置单个用户名和密码，并且由设备的所有用户共享。          |
   |     First Experience / HoloLens / SkipCalibration       |     True                          |     仅在初始设备设置期间跳过校准                                                                             |
   |     First Experience / HoloLens / SkipTraining          |     True                          |     在初始设备设置过程中跳过设备训练                                                                              |
   |     First Experience / HoloLens / WiFi                  |     True                          |     在Wi-Fi安装期间跳过配置                                                                                 |
   |     策略/连接/AllowBluetooth                |     否                            |     禁用蓝牙                                                                                                             |
   |     Policies/Experience/AllowCortana                    |     否                            |     禁用Cortana (以消除潜在问题，因为麦克风已禁用)                                           |
   |     Policies/MixedReality/MicrophoneDisabled            |     是                           |     禁用麦克风                                                                                                            |
   |     Policies/Privacy/LetAppsAccessLocation              |     强制拒绝                    |     防止应用尝试访问位置 (，以消除潜在问题，因为位置跟踪已禁用)     |
   |     Policies/Privacy/LetAppsAccessMicrophone            |     强制拒绝                    |     防止应用尝试访问麦克风 (消除潜在问题，因为麦克风已禁用)            |
   |     Policies/Security/AllowAddProvisioningPackage       |     否                            |     防止任何人添加可能尝试替代锁定策略的预配包。                         |
   |     Policies/Security/AllowRemoveProvisioningPackage    |     否                            |     防止任何人删除此锁定的预配包。                                                           |
   |     Policies/System/AllowLocation                       |     否                            |     阻止设备尝试跟踪位置数据。                                                                        |
   |     Policies/WiFi/AllowWiFi                             |     否                            |     禁用Wi-Fi                                                                                                                 |

1. 在"运行时设置"下，选择"**帐户/用户/用户名：Holo/密码"。**

   记下密码并重置（如果需要）。

1. 导航到"UniversalAppInstall/UserContextApp"，并配置要部署到这些设备的 [LOB](app-deploy-provisioning-package.md) 应用。

   > [!div class="mx-imgBorder"]
   > ![WCD 中应用添加位置的屏幕截图。](images/offline-secure-sample-wcd-usercontextapp2.png)

1. 完成后，选择"导出"按钮，并按照所有提示操作，直到创建预配包。

   > [!div class="mx-imgBorder"]
   > ![WCD 中此包的"导出"按钮的屏幕截图。](images/offline-secure-sample-wcd-export.png)

## <a name="deploy"></a>部署

1. 连接 USB 电缆将 HL2 Windows 10电脑。
1. 启动 ARC 工具并选择 **"HoloLens 2**

   ![HoloLens 2初始屏幕的干净重新滑动。](images/ARC2.png)

1. 在下一个屏幕上，选择"**手动包选择"。**

   ![HoloLens 2ARC 信息屏幕。](images/arc_device_info.png)

1. 导航到以前下载的 .ffu 文件，然后选择"打开 **"。**
1. 在"警告"页上，选择"**继续"。**

   ![HoloLens 2ARC 警告屏幕。](images/arc_warning.png)

1. 等待 ARC 工具完成 OS HoloLens 2安装。
1. 设备完成安装并启动后，从电脑导航到文件资源管理器，将以前保存的 PPKG 文件复制到设备文件夹。

   > [!div class="mx-imgBorder"]
   > ![电脑窗口内电脑上的 PPKG 文件资源管理器文件。](images/offline-secure-file-explorer.png)

1. 在HoloLens 2，按以下按钮组合以运行预配包：同时点击"音量降低"和"**电源** 按钮"。
1. 系统将提示你应用预配包，选择"确认 **"**
1. 预配包完成后，选择"确定 **"。**
1. 然后，系统会提示你使用共享的本地帐户和密码登录到设备。

## <a name="maintain"></a>维护

通过此配置，建议重启上述过程，使用 ARC 工具重新运行设备，并应用新的 PPKG，以对 OS 和/或应用程序进行 (更新) 。
