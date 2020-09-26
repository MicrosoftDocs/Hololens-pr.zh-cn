---
title: 常见方案-脱机安全 HoloLens 2
description: 通过预配进行脱机安全部署和应用部署。
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
ms.openlocfilehash: d53f9ce19b020a866770b756dde6ab97b8331362
ms.sourcegitcommit: e6885d03c980b33dd0bab5c418cbd1892d5ff123
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2020
ms.locfileid: "11080466"
---
# 常见方案-脱机安全 HoloLens 2

## 概述
本指南提供了应用示例预配包的指南，该软件包将在安全环境中锁定 HoloLens 2 以供以下限制使用：
-   禁用 WiFi。
-   禁用蓝牙。
-   禁用麦克风。
-   阻止添加或删除预配程序包。
-   任何用户都无法启用上述任何受限制的组件。

## 准备 
Windows 10 电脑设置
1. 将[最新的 HoloLens 2 OS 文件直接下载](https://aka.ms/hololens2download)到电脑。 
   1. 内部版本19041.1117 和更高版本中包含对此配置的支持。
1. [从 Microsoft Store](https://www.microsoft.com/store/productId/9P74Z35SFRS8)下载/安装高级恢复配套 (ARC) 工具
1. 从 Microsoft Store 中的 WCD) 工具下载/安装最新 [Windows 配置设计器 (](https://www.microsoft.com/p/windows-configuration-designer/9nblggh4tx22?activetab=pivot:overviewtab) 工具。
1. [下载包含项目文件的 OfflineSecureHL2_Sample 文件夹](https://aka.ms/HoloLensDocs-SecureOfflineSample) 以生成 PPKG。
1. [为 PPKG 部署准备脱机的业务线应用程序](app-deploy-provisioning-package.md)。 


## 配置
构建安全配置预配程序包

1. 在电脑上启动 WCD 工具。
1. 选择 " **文件"-> "打开项目**"。
  1. 导航到之前保存的 OfflineSecureHL2_Sample 文件夹的位置，然后选择： OfflineSecureHL2_Sample.icdproj.xml
1. 此时应打开该项目，您现在应具有可用的自定义列表： 

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中打开的配置包的屏幕截图](images/offline-secure-sample-wcd.png)

此预配包中设置的配置：

|     项目                                                |     设置                       |     描述                                                                                                                    |
|---------------------------------------------------------|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|     帐户/用户                                    |     本地用户名 & 密码    |     对于这些脱机设备，需要为该设备的所有用户设置和共享单个用户名和密码。          |
|     首次体验/HoloLens/SkipCalibration       |     True                          |     仅在初始设备设置期间跳过校准                                                                             |
|     首次体验/HoloLens/SkipTraining          |     True                          |     在初始设备设置过程中跳过设备培训                                                                              |
|     首次体验/HoloLens/WiFi                  |     True                          |     在初始设备设置期间跳过 Wi-fi 配置                                                                                 |
|     策略/连接/AllowBluetooth                |     否                            |     禁用蓝牙                                                                                                             |
|     政策/体验/AllowCortana                    |     否                            |     禁用 Cortana (可在禁用麦克风后消除潜在问题)                                           |
|     政策/MixedReality/MicrophoneDisabled            |     是                           |     禁用麦克风                                                                                                            |
|     政策/隐私权/LetAppsAccessLocation              |     强制拒绝                    |     阻止应用尝试访问位置数据 (以消除潜在问题，因为禁用位置跟踪)     |
|     政策/隐私权/LetAppsAccessMicrophone            |     强制拒绝                    |     阻止应用尝试访问麦克风 (，以便在禁用麦克风后消除潜在问题)            |
|     政策/Security/AllowAddProvisioningPackage       |     否                            |     阻止任何人添加可能会尝试覆盖已锁定策略的预配包。                         |
|     政策/Security/AllowRemoveProvisioningPackage    |     否                            |     阻止任何人删除此锁定的预配包。                                                           |
|     政策/系统/AllowLocation                       |     否                            |     阻止设备尝试跟踪位置数据。                                                                        |
|     政策/WiFi/AllowWiFi                             |     否                            |     禁用 Wi-fi                                                                                                                 |

4. 在 "运行时设置" 下，选择 "**帐户/用户/用户名： Holo/密码**" 
    - 记下密码，如果需要，重置。
5. 导航到 UniversalAppInstall/UserContextApp 并配置将部署到这些设备 [的 LOB 应用](app-deploy-provisioning-package.md) 。

   > [!div class="mx-imgBorder"]
   > ![在 WCD 中的何处添加应用的屏幕截图。](images/offline-secure-sample-wcd-usercontextapp.png)

6. 完成后，选择 "导出" 按钮并按照所有提示进行操作，直到创建你的预配包。

   > [!div class="mx-imgBorder"]
   > ![WCD 中此程序包的 "导出" 按钮的屏幕截图。](images/offline-secure-sample-wcd-export.png)


## 部署
1. 通过 USB 电缆将 HL2 连接到 Windows 10 电脑。
1. 启动 "弧形" 工具，然后选择 " **HoloLens 2** "

   <img src=images/offline-secure-arc-1.png alt=arc1 width="577" height="322" />

1. 在下一个屏幕上，选择 " **手动程序包选择**"。
   
   <img src=images/offline-secure-arc-2.png alt=arc2 width="577" height="322" />

1. 导航到以前下载的 ffu 文件，然后选择 " **打开**"。
1. 在警告页面上选择 " **继续**"。

   <img src=images/offline-secure-arc-3.png alt=arc3 width="577" height="322" />

1. 等待弧形工具完成 HoloLens 2 操作系统安装。
1. 设备完成安装并重新启动后，从你的电脑导航到 "文件资源管理器" 并将以前保存的 PPKG 文件复制到设备文件夹。

   > [!div class="mx-imgBorder"]
   > ![PPKG 在文件资源管理器窗口中的 PC 上的文件。](images/offline-secure-file-explorer.png)

1. 在 HoloLens 2 上，按以下按钮组合运行预配包：点击 " **音量降低** " 和 " **电源" 按钮** 。
1. 系统将提示你应用预配包，请选择 "**确认**"
1. 预配包完成后，选择 **"确定"**。
1. 然后，系统将提示您通过共享的本地帐户和密码登录到设备。

## 维护
使用此配置时，建议重启上述过程并使用 ARC 工具 reflash 设备，并应用新的 PPKG，以便对操作系统和/或应用程序 (s) 进行任何更新。 

