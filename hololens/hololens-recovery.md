---
title: 重启、重置或恢复 HoloLens
ms.reviewer: Follow along with our basic and advanced instructions for rebooting or resetting your HoloLens 2 device.
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
- HoloLens 2
ms.openlocfilehash: 7d8f2f8bf6aaaeb7f6f0ddbd339d428dad9335faeb99bfca48a19e68929921ed
ms.sourcegitcommit: f8e7cc2fbdcdf8962700fd50b9c017bd83d1ad65
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "115662958"
---
# <a name="restart-reset-or-recover-hololens-2"></a>重启、重置或恢复 HoloLens 2

>[!IMPORTANT]
> 在开始任何故障排除过程之前，请确保将设备充电至电池容量的 20 % 至 40%（如可能）。 通过位于电源按钮下的[电池指示灯](hololens2-setup.md#lights-that-indicate-the-battery-level)可以快速验证电池容量（无需登录到设备）。

使用 HoloLens 2 自带的[充电器和 USB Type-C 线缆](https://www.microsoft.com/en-us/p/microsoft-hololens-2-usb-c-charger-cable/8vj21f2z8pk5?rtc=1)，因为这是设备充电的最快途径。 充电器提供 18W 的电力（9V，2A）。 借助提供的壁式充电器，HoloLens 2 设备可在待机状态下在 65 分钟内将电池充满电。 如果这些附件不可用，请确保可用的充电器支持至少 15W 的功率。

> [!NOTE]
> 如果可能，请避免使用电脑通过 USB 给设备充电（速度很慢）。

如果设备已正确启动且运行，有三种方法可以检查电池电量：

- 从 HoloLens 设备 UI 的主菜单。
- 查看靠近电源按钮的 LED（对于 40% 的电量，应该可看到至少两个稳定的 LED）。
    - 为设备充电时，电池指示灯将亮起，以指示当前的充电进度。  最后一盏灯将不停闪烁，表示正在充电。
    - 当 HoloLens 处于打开状态时，电池指示灯以五个增量方式显示电池剩余电量。
    - 当五盏灯中只有一盏亮起时，表示电池剩余电量低于 20%。
    - 如果在电池剩余电量严重不足时你尝试打开设备，则一盏灯将会短暂闪烁，然后熄灭。
- 在主机上，打开“文件资源管理器”，然后在左侧的“这台电脑”下查找 HoloLens 2 设备。 右键单击该设备，并选择“属性”。 对话框将显示电池电量。

   ![HoloLens 2 属性屏幕显示电量变化情况](images/ResetRecovery2.png)

如果设备无法引导到启动菜单，请注意主机计算机上的 LED 外观和设备枚举。 然后按照[疑难解答指南](hololens-troubleshooting.md)。 如果设备的状态与疑难解答指南中列出的任何状态都不匹配，请在设备连接到电源而不是主机的情况下预先执行[硬重置程序](hololens-recovery.md#hard-reset-procedure)。 等待至少一小时，让设备充电。

## <a name="reset-the-device"></a>重置设备

在某些情况下，可能需要在不使用软件 UI 的情况下手动重置设备。

### <a name="standard-procedure"></a>标准程序

1. 拔下 Type-C 电缆，以断开设备与电源或主机计算机的连接。

2. 按住电源按钮 15 秒。 所有 LED 均应熄灭。

3. 等待 2-3 秒，然后短按电源按钮。 电源按钮附近的指示灯将亮起，并且设备将开始启动。

4. 将设备连接到主机计算机，然后打开设备管理器。 （对于 Windows 10，请按 Windows 键，然后按 X 键，然后选择“设备管理器”），并确保设备正确枚举为 Microsoft HoloLens，如下图所示：

   ![HoloLens 2 MicrosoftHoloLensRecovery 设备管理器](images/MicrosoftHoloLens_DeviceManager.png)

### <a name="hard-reset-procedure"></a>硬重置程序

如果标准重置程序不起作用，可使用硬重置程序：

1. 拔下 Type-C 电缆，以断开设备与电源或主机计算机的连接。

2. 按住“音量减小” + “电源”按钮 15 秒。 设备将自动重启。

4. 将设备连接到主机计算机。


5. 打开设备管理器（对于 Windows 10，请按 Windows 键，然后按 X 键，然后选择“设备管理器”）。 确保设备正确枚举为 Microsoft HoloLens，如下图所示：

   ![HoloLens 2 MicrosoftHoloLensRecovery 设备管理器 2](images/MicrosoftHoloLens_DeviceManager.png)

## <a name="clean-reflash-the-device"></a>对设备进行干净重刷

在特别情况下，可能需要对 HoloLens 2 进行干净刷写。 请注意，清理重刷预期不会引起以下问题：
- [显示颜色一致性](hololens2-display.md)
- 使用声音启动但无显示输出
- [1-3-5-LED 图案](hololens2-setup.md#lights-to-indicate-problems)
- [过热](hololens-environment-considerations.md#temperature-and-regulatory-information) 
- 操作系统崩溃（不同于应用程序崩溃）

对设备进行重刷的方法共有两种。 对于这两种方法，都必须首先[从 Windows 应用商店安装 Advanced Recovery Companion](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。

>[!WARNING]
>如果刷写设备，则将擦除所有个人数据、应用和设置，包括 TPM 重置。

默认情况下，Advanced Recovery Companion 设置为下载最新的功能版本版本，请查看此处阅读[发行说明](hololens-release-notes.md#)以了解最新功能版本。 若要获取最新的 HoloLens 2 映像刷写工具 (FFU) 程序包以通过 Advanced Recovery Companion 重刷设备，[单击此处下载最新的每月 HoloLens 2 图像](https://aka.ms/hololens2download)。 此版本是最新的通用版本。

开始刷写程序前，请确保已在 Windows 10 电脑上安装并运行该应用，并已准备好检测设备。 此外，请确保你的 HoloLens 的最低费用为40%。

![HoloLens 2 干净重刷屏幕截图](images/ARC1.png)

### <a name="normal-procedure"></a>正常程序

1. 在 HoloLens 设备运行期间，将其连接到你先前打开了 Advanced Recovery Companion 应用的 Windows 10 电脑。
 
   系统将自动检测设备，Advanced Recovery Companion 应用的 UI 将开始更新进程：

   ![HoloLens 2 干净重刷初始屏幕](images/ARC2.png)

3. 在 Advanced Recovery Companion 应用 UI 中选择 HoloLens 2 设备，然后按照说明完成刷写。

### <a name="manual-procedure"></a>手动程序

如果未能正确启动 HoloLens 2，或者如果 Advanced Recovery Companion 未能检测到设备，则可能需要将设备置于恢复模式：

1. 拔下 Type-C 电缆，以断开设备与电源或主机计算机的连接。

2. 按住电源按钮 15 秒。 所有 LED 均应熄灭。

3. 在按下调高音量按钮的同时，按下并释放电源以启动设备。 请等待 15 秒钟，然后再释放调高音量按钮。 五个 LED 中只有中间的 LED 会亮起。

4. 将设备连接到主机电脑，然后打开设备管理器。 （对于 Windows 10，请按 Windows 键，然后按 X 键，然后选择“设备管理器”），并确保设备正确枚举为 Microsoft HoloLens，如下图所示：

   ![HoloLens 2 MicrosoftHoloLensRecovery](images/MicrosoftHoloLensRecovery.png)

   系统将自动检测设备，Advanced Recovery Companion 应用的 UI 将开始更新进程：

   ![HoloLens 2 干净重刷屏幕](images/ARC2.png)

6. 在 Advanced Recovery Companion 应用 UI 中选择 HoloLens 2 设备，然后按照说明完成刷写。

## <a name="troubleshoot-advanced-recovery-companion"></a>Advanced Recovery Companion 故障排除

1. 在尝试刷用之前，请确保设备已充电到 40% 或以上。

2. 检查设备是否解锁。

1. 检查设备是否直接插入主机 PC，而不是中心。

1. 如果设备未在通用串行总线驱动程序下显示为 HoloLens/HoloLens 恢复设备，请检查以下内容：
    1. 端口，作为 Qualcomm HS-USB 设备
    1.   其他设备，作为 QUSB_BULK 设备 - 主机 PC 缺少检测 HoloLens 所需的驱动程序。 右键单击并选择更新驱动程序，然后在线搜索驱动程序或[检查 Windows 更新设置中的可选更新](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/improving-the-update-discoverability-experience/ba-p/1585674)。 下载驱动程序后，ARC 应能够检测到它。
 
1. 如果 ARC 未检测到设备，请确保可以通过电脑上的文件资源管理器连接到设备。 如果不能，

    1.  那么设备可能具有禁用该连接的 USB 策略。 这样的话，请尝试[手动刷写模式](hololens-recovery.md#manual-procedure)。
    2.  如果没有策略，请尝试使用不同的 USB 电缆。

1. 检查设备未显示[1-3-5-LED 模式](hololens2-setup.md#lights-to-indicate-problems)。

## <a name="download-arc-without-using-the-app-store"></a>在不使用应用商店的情况下下载 ARC

如果 IT 环境阻止使用 Windows Store 应用或限制对该零售商店的访问，IT 管理员可通过“脱机”部署路径提供此应用。

 >[!NOTE]
 > - IT 管理员也可以通过 System Center Configuration Manager (SCCM) 或 Intune 分发此应用。
 > - 本指南重点介绍 Advanced Recovery Companion，但该过程也可用于其他“脱机”应用程序。

请按照以下步骤启用部署路径：

1. 转到 [Microsoft Store for Business](https://businessstore.microsoft.com)，然后使用 Azure Active Directory 标识登录。

1. 转到“管理”–“设置”。 打开“购物体验”下的“显示脱机应用”。

1. 转到“购买组”并搜索 [_Advanced Recovery Companion_](https://businessstore.microsoft.com/store/details/advanced-recovery-companion/9P74Z35SFRS8)。

1. 将“许可证类型”更改为 **_脱机_ *_，然后选择 _“管理”***。

1. 在“下载包供脱机使用”下，选择第二个蓝色“下载”按钮。 确保文件扩展名为 .appxbundle。

    - 在此阶段，如果台式机可以访问互联网，请双击程序包以安装该应用。

    - 如果目标电脑没有 Internet 连接，请按照以下步骤操作：
       1. 选择解码的许可证，然后选择“生成许可证”。
       2. 在“所需框架”下，选择“下载”。
       3. 使用 DISM 将软件包与依赖项和许可证一起应用。 从管理员命令提示符运行以下命令：

          ```console
          C:\WINDOWS\system32>dism /online /Add-ProvisionedAppxPackage /PackagePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_1.19050.1301.0_neutral_~_8wekyb3d8bbwe.appxbundle" /DependencyPackagePath:"C:\ARCoffline\Microsoft.VCLibs.140.00.UWPDesktop_14.0.27629.0_x86__8wekyb3d8bbwe.appx" /LicensePath:"C:\ARCoffline\Microsoft.AdvancedRecoveryCompanion_8wekyb3d8bbwe_f72ce112-dd2e-d771-8827-9cbcbf89f8b5.xml" /Region:all
          ```
          > [!NOTE]
          > 此代码示例中的版本号可能与当前可用的版本不匹配。 可能还选择了与给定示例不同的下载位置。 根据需要对命令进行任何更改。

> [!TIP]
> 计划使用 Advanced Recovery Companion 脱机安装 FFU 时，下载刷写映像可能会很有用。 [下载 HoloLens 2 当前映像](https://aka.ms/hololens2download)。


其他资源：
- [分配离线应用](/microsoft-store/distribute-offline-apps) 
- [DISM 应用程序包（.appx 或 .appxbundle）服务命令行选项](/windows-hardware/manufacture/desktop/dism-app-package--appx-or-appxbundle--servicing-command-line-options)
