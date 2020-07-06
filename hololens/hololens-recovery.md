---
title: 重启、重置或恢复 HoloLens
ms.reviewer: Both basic and advanced instructions for rebooting or resetting your HoloLens.
description: 如何使用 Advanced Recovery Companion 将映像刷写到 HoloLens 2。
keywords: 操作方法, 重启, 重置, 恢复, 硬重置, 软重置, 电源周期, HoloLens, 关机, arc, advanced recovery companion
ms.prod: hololens
ms.sitesec: library
author: mattzmsft
ms.author: mazeller
ms.date: 04/27/2020
ms.custom:
- CI 111456
- CSSTroubleshooting
ms.topic: article
ms.localizationpriority: high
manager: jarrettr
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 5da7f954454b5713823c5aa94742f9c9c0033ca2
ms.sourcegitcommit: 7c057aeeaeebb4daffa2120491d4e897a31e8d0f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827664"
---
# HoloLens 2 的重置和恢复

## 对设备充电

在开始任何故障排除程序之前，如果可能，请确保设备电量至少在 20% 到 40% 之间。

请确保使用 HoloLens2 设备附带的充电器和 USB Type-C 电缆。 如果没有，请确保所用的充电器支持至少 15W 的功率。

> [!NOTE]
> 如有可能，请勿使用电脑通过 USB 对设备进行充电，因为这将导致充电非常慢。

如果设备已正确启动且运行，有三种不同的方法可用来检查电池的电量。

1. 从 HoloLens 设备 UI 的主菜单。
2. 使用靠近电源按钮的 LED（对于 40% 的电量，应该可看到至少两个稳定的 LED）。
3. 在主机上，打开“文件资源管理器”窗口，然后在左侧的“此电脑”下查找 HoloLens 2 设备。
    
      a. 右键单击设备的名称，然后选择“属性”。 此时将出现一个对话框，显示你设备的电池电量。

![HoloLens 2 重置恢复](images/ResetRecovery2.png)

如果设备无法启动到启动菜单，请记下 LED 和主机上的和枚举情况，然后按照故障排除指南 (https://docs.microsoft.com/hololens/hololens-troubleshooting) 进行操作。 如果设备的状态不符合故障排除指南中列出的任何状态，请执行硬重置程序****，且不是将设备重新连接到主机，而是将其连接到电源。 至少等待一小时，让设备充电。

## 重置设备

在某些情况下，客户可能需要在不使用 SW UI 的情况下手动重置设备。 

### 标准程序
1. 拔出 Type-C 电缆，以断开设备与电源或主机的连接。

2. 按住电源按钮**** 15 秒。 所有 LED 均应熄灭。

3. 等待 2-3 秒，然后短按电源按钮****，电源按钮旁的 LED 将亮起，设备将开始启动。 

4. 将设备连接到主机，打开设备管理器（对于 Windows 10，请按“Windows”键****，然后按“X”**** 键，然后单击“设备管理器”），并确保设备正确枚举为 Microsoft HoloLens，如下图所示：

![HoloLens 2 MicrosoftHoloLens恢复](images/MicrosoftHoloLensRecovery.png)

### 硬重置程序

如果标准重置程序不起作用，可使用硬重置程序。

1. 拔出 Type-C 电缆，以断开设备与电源或主机的连接。

2. 按住下调音量按钮 + 电源按钮**** 15 秒钟。

3. 设备将自动重启。 

4. 将设备连接到主机，打开设备管理器（对于 Windows 10，请按“Windows”键****，然后按“X”**** 键，然后单击“设备管理器”），并确保设备正确枚举为 Microsoft HoloLens，如下图所示。

![HoloLens 2 MicrosoftHoloLens恢复](images/MicrosoftHoloLens_DeviceManager.png)

## 对设备进行干净重刷

在特别情况下，可能需要对设备进行干净刷写。 对 HoloLens2 设备进行重刷的方法共有两种。 所有重刷程序都要求[从 Windows Store 安装 Advanced Recovery Companion 应用](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。 如果重置设备，则将擦除所有个人数据、应用和设置，包括 TPM 重置。

Advanced Recovery Companion 目前已设置为下载 [Windows Holographic 2004](hololens-release-notes.md#windows-holographic-version-2004) 的功能发布内部版本。若要下载最新的 HoloLens 2 FFU 以通过 Advanced Recovery Companion 来刷写设备，可从[此处](https://aka.ms/hololens2download)下载。 此处的 FFU 会实时更新，并将与最新的通用内部版本匹配。 

开始刷写程序之前，请确保已在 Windows 10 电脑上安装并运行该应用，并已准备好检测设备。

![HoloLens 2 干净重刷](images/ARC1.png)

### 正常程序

1. 在 HoloLens 设备运行期间，将其连接到你先前启动了 Advanced Recovery Companion 应用的 Windows 10 电脑。

2. 系统将自动检测设备，Advanced Recovery Companion 应用的 UI 将更新为如下所示：

![HoloLens 2 干净重刷](images/ARC2.png)

3. 在 Advanced Recovery Companion 应用 UI 中选择 HoloLens2 设备，然后按照说明完成刷写。

### 手动程序

如果设备未正确启动，可能需要将 HoloLens 2 设备置于恢复模式。

1. 拔出 Type-C 电缆，以断开设备与电源或主机的连接。 

2. 按住电源按钮**** 15 秒。 所有 LED 均应熄灭。 

3. 在按下上调音量按钮的同时****，按下并释放电源按钮**** 以启动设备。 请等待 15 秒钟，然后再释放上调音量按钮。 在设备上的 5 个 LED 中，只有中间的 LED 会亮起。

4. 将设备连接到主机，打开设备管理器（对于 Windows 10，请按“Windows”键****，然后按“X”**** 键，然后单击“设备管理器”），并确保设备正确枚举为 Microsoft HoloLens，如下图所示。

![HoloLens 2 MicrosoftHoloLens恢复](images/MicrosoftHoloLensRecovery.png)

5. 系统将自动检测设备，Advanced Recovery Companion 应用的 UI 将更新为如下所示：

![HoloLens 2 干净重刷](images/ARC2.png)

6. 在 Advanced Recovery Companion 应用 UI 中选择 HoloLens 2 设备，然后按照说明完成刷写。

## 在不使用应用商店的情况下下载 ARC

如果 IT 环境阻止使用 Windows Store 应用或限制对该零售商店的访问，IT 管理员可通过其他“脱机”部署路径提供此应用。 

- 此流程也可用于其他应用，如步骤 2 所示。 本指南将重点介绍 Advanced Recovery Companion，对于其他脱机应用则可能需要稍作修改。  

可通过以下步骤启用此部署路径：
1.  转到[适用于企业的 Microsoft Store](https://businessstore.microsoft.com) 网站并使用 Azure AD 标识登录。
1.  转到“管理”–“设置”****，然后打开“购物体验”下的“显示脱机应用”********，详见 https://businessstore.microsoft.com/manage/settings/shop 
1.  转到“为我的组购买”****，搜索 [Advanced Recovery Companion](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8) 应用。
1.  将“许可证类型”**** 框更改为“脱机”，然后单击“管理”****。
1.  在“下载脱机使用的程序包”下，单击第二个蓝色“下载”**** 按钮。 确保文件扩展名为 .appxbundle。
1.  在这个阶段，如果台式电脑可以访问 Internet，只需双击并安装。 
1.  IT 管理员也可以通过 System Center Configuration Manager (SCCM) 或 Intune 分发此应用。
1.  如果目标电脑没有 Internet 连接，则需要额外执行一些步骤： 
    1.  选择未编码的许可证并单击“生成许可证”，然后在“所需框架”下单击“下载”。************ 
    1.  无法访问 Internet 的电脑将需要使用 DISM 来应用具有依赖项的程序包和许可证。 在管理员命令提示符处，键入：

      ```console
      C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
      ```
> [!NOTE]
> 此代码示例中的版本号可能与当前可用的版本不匹配。 你可能还选择了与给定示例不同的下载位置。 请确保根据需要进行更改。

> [!TIP]
> 在计划使用 Advanced Recovery Companion 来脱机安装 FFU 时，下载刷写映像可能会很有用，这里是 [HoloLens 2 的当前映像](https://aka.ms/hololens2download)。 

其他资源：
- https://docs.microsoft.com/microsoft-store/distribute-offline-apps 
- https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options


