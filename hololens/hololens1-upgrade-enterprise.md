---
title: 解锁 Windows Holographic for Business 功能
description: 升级到 Windows Holographic for Business 时，HoloLens提供专为业务设计的额外功能。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 9/16/2019
ms.reviewer: ''
manager: jarrettr
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: c6d1225dc6da1c039a34fc2782f23330ae40f280
ms.sourcegitcommit: f04f631fbe7798a82a57cc01fc56dc2edf13c5f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "123189182"
---
# <a name="unlock-windows-holographic-for-business-features"></a>解锁 Windows Holographic for Business 功能

> [!IMPORTANT]
> 此页仅适用于第HoloLens代。

Microsoft HoloLens在 Development *Edition* 中提供，它运行 Windows Holographic (是专为 HoloLens) 设计的 Windows 10 版本，商业套件提供专为业务设计的额外功能。 [](hololens-commercial-features.md)

购买商业套件时，你会收到可将 Windows 全息版升级为 Windows Holographic for Business 的许可。 可以使用组织的移动设备管理提供程序或预配包 将 (许可证[) ](#edition-upgrade-by-using-mdm)[设备](#edition-upgrade-by-using-a-provisioning-package)。

> [!TIP]
> 在 Windows 10版本 1803 中，可以通过选择"HoloLens系统"来检查设置  >  **版本**。

## <a name="edition-upgrade-by-using-mdm"></a>使用 MDM 进行版本升级

可通过支持 [WindowsLicensing 配置服务提供程序 (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) 的任意 MDM 提供程序应用企业许可。 最新版的 Microsoft MDM API 将支持 WindowsLicensing CSP。

有关使用 HoloLens 升级 Microsoft Intune 的分步说明，请参阅将运行 Windows 的设备升级到[Windows Holographic for Business。](/intune/holographic-upgrade)

 在其他 MDM 提供程序中，策略的具体设置和部署步骤可能不同。

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>使用预配包进行版本升级

预配程序包是由 Windows 配置设计器工具创建的文件，可将指定的配置应用于设备。

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>创建可升级 Windows 全息版的预配程序包

1. [创建适用于 HoloLens 的预配包。](hololens-provisioning.md)
1. 转到"**运行时设置**  >  **""版本""升级"，** 然后选择 **"EditionUpgradeWithLicense"。**

    ![升级版本，并选中许可证设置。](images/icd1.png)

1. 查找购买商业套件时提供的 XML 许可证文件。

    > [!NOTE]
    > 你可以配置[预配包中的其他设置](hololens-provisioning.md)。

1. 在“文件”菜单上，选择“保存” 。 

1. 阅读项目文件可能包含敏感信息的警告，然后单击"确定 **"。**

    > [!IMPORTANT]
    > 生成预配包时，你可能会在项目文件和预配包文件 (.ppkg) 包含敏感信息。 尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。 应该将项目文件存储在安全的位置，并删除不再需要的项目文件。

1. 在“导出”菜单上，选择“设置包”。

1. 将 **"****所有者"更改为"IT** 管理员"，这会将此预配包的优先级设置得高于其他从不同源应用到此设备的包，然后选择"下一 **步"。**

1. 为“程序包版本”设置一个值。

    > [!TIP]
    > 你可以对现有的程序包进行更改，并更改版本号以更新之前应用的程序包。

1. 在 **"选择预配包的安全详细信息"中，选择**"下一 **步"。**

1. 选择 **"** 下一步"，指定生成预配包后要转到的输出位置。 默认情况下，Windows ICD 会使用项目文件夹作为输出位置。

    （可选）可以选择" **浏览"** 以更改默认输出位置。

1. 选择“**下一页**”。

1. 选择 **"生成** "以开始生成包。 生成页显示项目信息，进度栏指示生成状态。

1. 生成完成后，选择"完成 **"。**

### <a name="apply-the-provisioning-package-to-hololens"></a>将预配包应用于 HoloLens

1. 使用 USB 电缆将设备连接到电脑。 启动设备，但不要继续通过第一页中初始设置体验的 (安装体验页面，) 。 在电脑上，HoloLens设备会显示为文件资源管理器。

    > [!NOTE]
    > 如果HoloLens设备Windows 10版本 1607 或更早版本，请文件资源管理器在设备上同时按下并松开"关闭音量"和"电源"按钮，打开文件资源管理器。 

1. 在文件资源管理器中，将预配包 (.ppkg) 拖放到设备存储中。

1. 虽然HoloLens仍在调整大小页上，但请再次短暂地按下并松开"音量降低"和"**电源**"按钮。

1. HoloLens询问是否信任包并要应用它。 确认你信任程序包。

1. 你将看到是否成功应用了程序包。 如果未成功应用，可以修复包，然后重试。 如果成功，请继续安装设备。
