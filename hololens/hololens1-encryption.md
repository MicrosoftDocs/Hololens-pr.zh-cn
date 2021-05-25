---
title: HoloLens BitLocker 加密
description: 了解如何启用 BitLocker 设备加密来保护 HoloLens 混合现实设备上存储的文件。
ms.prod: hololens
ms.mktglfcycl: manage
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 01/26/2019
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
ms.openlocfilehash: 2929cbea826e0cc92a72550c7874995506b94257
ms.sourcegitcommit: 29573e577381a23891e9557884a6dfdaac0c1c48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "110397278"
---
# <a name="hololens-1st-gen-bitlocker-encryption"></a>HoloLens (第一代) BitLocker 加密

HoloLens (第一代) 和 HoloLens 2 都支持使用 BitLocker 进行设备加密，但 BitLocker 始终在 HoloLens 2。

本文将帮助你在 HoloLens 上启用和管理 BitLocker (第一代) 。

在 HoloLens (第一代) 可以手动启用 BitLocker 设备加密，或者使用 MDM (移动设备) 。 按照这些说明启用 [BitLocker 设备加密](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption) ，以保护存储在 HoloLens 上的文件和信息。 设备加密有助于使用 AES-CBC 128 加密方法保护数据，该方法等效于 BitLocker 配置服务提供程序 (CSP) 中的[EncryptionMethodByDriveType 方法 3。](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#encryptionmethodbydrivetype) 具有正确的加密密钥（例如 (密码）的人员) 解密或执行数据恢复。

## <a name="enable-device-encryption-using-mdm"></a>使用 MDM 启用设备加密

可以使用 Mobile 设备管理 (MDM) 应用需要设备加密的策略。 使用的策略是策略 CSP [中的 Security/RequireDeviceEncryption](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-requiredeviceencryption) 设置。

[请参阅有关使用证书启用设备加密Microsoft Intune。](https://docs.microsoft.com/intune/compliance-policy-create-windows#windows-holographic-for-business)

有关其他 MDM 工具，请参阅 MDM 提供程序文档中的说明。 如果 MDM 提供程序需要自定义 URI 进行设备加密，请使用以下配置：

- **名称**：你选择的名称
- **说明**：可选
- **OMA-URI：**`./Vendor/MSFT/Policy/Config/Security/RequireDeviceEncryption`
- **数据类型：integer**
- **值**：`1`

## <a name="enable-device-encryption-using-a-provisioning-package"></a>使用预配程序包启用设备加密

预配程序包是由 Windows 配置设计器工具创建的文件，可将指定的配置应用于设备。 

### <a name="create-a-provisioning-package-that-upgrades-the-windows-holographic-edition-and-enables-encryption"></a>创建一个预配包，用于升级 Windows Holographic 版本并启用加密

1. [为 HoloLens 创建预配包。](hololens-provisioning.md)
1. 转到"**运行时设置**  >  **策略**  >  **安全性"，** 然后选择 **"RequireDeviceEncryption"。**

    ![“要求设备加密”设置配置为“是”](images/device-encryption.png)

1. 查找购买商业套件时提供的 XML 许可证文件。

1. 浏览并选择购买 Commercial 套件时提供的 XML 许可证文件。
    > [!NOTE]
    > 你可以配置[预配包中的其他设置](hololens-provisioning.md)。

1. 在“文件”菜单上，单击“保存”。 

1. 阅读说明项目文件可能包含敏感信息的警告，然后单击 **"确定"**。

    > [!IMPORTANT]
    > 生成预配包时，可以在项目文件中包含敏感信息，并 ( ppkg) 文件中设置包。 尽管你可以选择加密 .ppkg 文件，但项目文件不会加密。 你应将项目文件存储在安全的位置，并在不再需要时删除项目文件。

1. 在 " **导出** " 菜单上，单击 " **预配包**"。
1. 将 **所有者** 更改为 **IT 管理员**，这会将此预配包的优先级设置为高于从其他源应用于此设备的预配包，然后选择 " **下一步**"。
1. 为“程序包版本”设置一个值。

    > [!TIP]
    > 你可以对现有的程序包进行更改，并更改版本号以更新之前应用的程序包。

1. 在 **选择预配包的安全性详细信息** 上，单击 **下一步**。
1. 单击 " **下一步** " 以指定在生成预配包后要将其移到的输出位置。 默认情况下，Windows ICD 会使用项目文件夹作为输出位置。

    或者，你还可以单击“浏览”更改默认输出位置。

1. 单击“下一步”  。
1. 单击“构建”开始构建程序包。 项目信息会显示在构建页面中，并且进度栏会指示构建状态。
1. 构建完成后，单击 **完成**。

### <a name="apply-the-provisioning-package-to-hololens"></a>将预配包应用于 HoloLens

1. 通过 USB 将设备连接到电脑并启动设备，但请勿继续通过初始设置体验的 **调整** 页（带有蓝色框的第一页）。
1. 短暂地同时按下 **调低音量** 和 **电源** 按钮，然后释放。
1. HoloLens 将在电脑的文件资源管理器中显示为设备。
1. 在文件资源管理器中，将预配包 (.ppkg) 拖放到设备存储中。
1. 在 **调整** 页中，再次短暂地同时按下 **调低音量** 和 **电源** 按钮，然后释放。
1. 设备将询问你是否信任该程序包并想要应用它。 确认你信任程序包。
1. 你将看到是否成功应用了程序包。 如果失败，你可以修复程序包，然后重试。 如果成功，请继续进行设备设置。

> [!NOTE]
> 如果设备的购买日期在 2016 年 8 月之前，则将需要使用 Microsoft 帐户登录设备，获取最新的操作系统更新并重置操作系统，以便应用预配程序包。

## <a name="verify-device-encryption"></a>验证设备加密

加密在 HoloLens 上无提示。 若要验证设备加密状态：

- 在 HoloLens 上，中转到 "**设置**" "  >  **系统**"  >  。 如果设备已加密，则 **启用** **BitLocker** 。 

    ![显示启用了 BitLocker 的屏幕](images/about-encryption.png)
