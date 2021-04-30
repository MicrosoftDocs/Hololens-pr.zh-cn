---
title: 解锁 Windows Holographic for Business 功能
description: 升级到 Windows 全息版时，HoloLens 提供适用于企业的额外功能。
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
ms.openlocfilehash: 8d42c935e698f156aed894e4fa5012c9f04d8d49
ms.sourcegitcommit: ad53ba5edd567a18f0c172578d78db3190701650
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "108308416"
---
# <a name="unlock-windows-holographic-for-business-features"></a>解锁 Windows Holographic for Business 功能

> [!IMPORTANT]
> 此页仅适用于 HoloLens 第一代。

Microsoft HoloLens 在 *开发版* 中提供，该版本可运行 windows 全息 (windows 10 版本，该版本是为 HoloLens) 设计的，也是在 [商业套件](hololens-commercial-features.md)中提供的，后者提供了为企业设计的额外功能。

购买商业套件时，你会收到可将 Windows 全息版升级为 Windows Holographic for Business 的许可。 你可以使用组织的 [移动设备管理 (MDM) 提供程序](#edition-upgrade-by-using-mdm) 或 [预配包](#edition-upgrade-by-using-a-provisioning-package)将此许可证应用到设备。

> [!TIP]
> 在 Windows 10 版本1803中，可以通过选择 "**设置**" "系统" 来检查是否已将 HoloLens 升级到 business edition  >  。

## <a name="edition-upgrade-by-using-mdm"></a>使用 MDM 升级版本

可通过支持 [WindowsLicensing 配置服务提供程序 (CSP)](https://msdn.microsoft.com/library/windows/hardware/dn904983.aspx) 的任意 MDM 提供程序应用企业许可。 最新版的 Microsoft MDM API 将支持 WindowsLicensing CSP。

有关使用 Microsoft Intune 升级 HoloLens 的分步说明，请参阅 [将运行 Windows 全息的设备升级到 Windows 全息版 For Business](https://docs.microsoft.com/intune/holographic-upgrade)。

 在其他 MDM 提供程序中，策略的具体设置和部署步骤可能不同。

## <a name="edition-upgrade-by-using-a-provisioning-package"></a>使用预配包进行版本升级

预配程序包是由 Windows 配置设计器工具创建的文件，可将指定的配置应用于设备。

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition"></a>创建可升级 Windows 全息版的预配程序包

1. [为 HoloLens 创建预配包。](hololens-provisioning.md)
1. 请参阅 **运行时设置**  >  **EditionUpgrade**，然后选择 **EditionUpgradeWithLicense**。

    ![使用已选择的许可证设置升级版本](images/icd1.png)

1. 找到购买商用套件时提供的 XML 许可证文件。

    > [!NOTE]
    > 你可以配置[预配包中的其他设置](hololens-provisioning.md)。

1. 在“文件”菜单中，选择“保存”。 

1. 阅读警告：项目文件可能包含敏感信息，然后单击 **"确定"**。

    > [!IMPORTANT]
    > 生成预配包时，可以在项目文件中包含敏感信息，并 ( ppkg) 文件中设置包。 尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。 你应将项目文件存储在安全的位置，并在不再需要时删除项目文件。

1. 在“导出”菜单上，选择“设置包”。

1. 将 **所有者** 更改为 **IT 管理员**，这会将此预配包的优先级设置为高于从不同源应用到此设备的其他设置，然后选择 " **下一步**"。

1. 为“程序包版本”设置一个值。

    > [!TIP]
    > 你可以对现有的程序包进行更改，并更改版本号以更新之前应用的程序包。

1. 在 **"选择预配包的安全详细信息**" 中，选择 " **下一步**"。

1. 选择 " **下一步** " 以指定在生成预配包后要将其移到的输出位置。 默认情况下，Windows ICD 会使用项目文件夹作为输出位置。

    还可以选择 " **浏览** " 以更改默认输出位置。

1. 选择“**下一页**”。

1. 选择 " **生成** " 开始生成包。 "生成" 页显示项目信息，进度栏指示生成状态。

1. 生成完成后，选择 " **完成**"。

### <a name="apply-the-provisioning-package-to-hololens"></a>将预配包应用于 HoloLens

1. 使用 USB 电缆将设备连接到 PC。 启动该设备，但不要继续在初始设置体验的 " **适合** " 页上 (第一页中) 蓝色框。 在电脑上，HoloLens 作为设备显示在文件资源管理器中。

    > [!NOTE]
    > 如果 HoloLens 设备运行的是 Windows 10 1607 版或更早版本，请在设备上暂时按下并释放 " **音量** " 和 " **电源** " 按钮以打开文件资源管理器。

1. 在文件资源管理器中，将预配包 (.ppkg) 拖放到设备存储中。

1. 虽然 HoloLens 仍处于 " **适合** " 页，但请暂时按下并释放 " **音量降低** " 和 " **电源** 按钮"。

1. HoloLens 会询问你是否信任包，并想要应用它。 确认你信任程序包。

1. 你将看到是否成功应用了程序包。 如果未成功应用，你可以修复包并重试。 如果成功，则继续执行设备设置。
