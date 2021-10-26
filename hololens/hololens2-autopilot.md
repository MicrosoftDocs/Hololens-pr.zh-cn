---
title: 适用于 HoloLens 2 的 Windows Autopilot
description: 了解如何在 HoloLens 2 设备上对 Autopilot 进行设置、配置和故障排除。
author: qianw211
ms.author: v-qianwen
ms.date: 10/11/2021
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: sekerawa
ms.openlocfilehash: b343e4dc6e217319574efa068cd72c5f5a8675a8
ms.sourcegitcommit: 38b5e4d92da6fc5d6a6a2ef875644d6db2cce822
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2021
ms.locfileid: "130202907"
---
# <a name="windows-autopilot-for-hololens-2"></a>适用于 HoloLens 2 的 Windows Autopilot

## <a name="overview"></a>概述

若要大规模部署，我们建议开始使用 Windows Autopilot。 它被认为是“低接触”的，因为它大大简化了 IT 和最终用户的 HoloLens 设置。 

在较高级别，IT 管理员通常会创建业务就绪配置并在 MDM 门户上注册 HoloLens 2 设备。 当 HoloLens 2 设备通过全新安装体验 (OOBE) 启动并连接到 Internet 时，会自动下载并应用已注册的 HoloLens 2 设备的业务就绪配置，使设备无需用户干预即可实现业务就绪。

有关详细信息，请参阅 [Windows Autopilot 概述 | Microsoft Docs](/mem/autopilot/windows-autopilot) 一问。

## <a name="supported-autopilot-scenario-on-hololens-2"></a>HoloLens 2 上受支持的 autopilot 场景

> [!NOTE]
> Microsoft Endpoint Manager 中 HoloLens 的 Autopilot 配置将从“公共预览”转换为“正式发布” 。 所有租户都可在 MEM 管理中心设置 Autopilot。

从 Windows 全息版 2004 开始，HoloLens 2 支持使用 Microsoft Intune 的 Windows Autopilot [自部署模式](/mem/autopilot/self-deploying)（不支持第三方 MDM）。 此配置减少了库存管理开销、动手准备设备的成本以及员工在设置过程中的支持电话。 在 [Windows Autopilot](/mem/autopilot/windows-autopilot) 文档中了解详细信息。

与 Surface 设备一样，我们建议客户与其 Microsoft [云解决方案提供商](https://partner.microsoft.com/cloud-solution-provider)（经销商或分销商）合作，通过合作伙伴中心将设备注册到 Autopilot 服务。

当用户启动 Autopilot 自部署过程时，Autopilot 会完成以下步骤：

1. 将设备加入 Azure Active Directory (Azure AD)。 适用于 HoloLens 的 Autopilot 不支持 Active Directory 联接或混合 Azure AD 联接。

1. 使用 Azure AD 在 Microsoft Endpoint Manager（或其他 MDM 服务）中注册设备。

1. 下载并应用面向设备的策略、证书、网络配置文件和应用程序。

1. 向用户展示登录屏幕。

## <a name="configuring-autopilot-for-hololens-2"></a>配置适用于 HoloLens 2 的 Autopilot

请按照以下步骤设置环境：

1. [查看适用于 HoloLens 2 的 Windows Autopilot 要求。](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [启用自动 MDM 注册](#2-enable-automatic-mdm-enrollment)

1. （仅针对 Intune）[确保未阻止 Windows 设备进行 MDM 注册。](/mem/intune/enrollment/enrollment-restrictions-set)

1. [在 Windows Autopilot 中注册设备。](#4-register-devices-in-windows-autopilot)

1. [创建设备组。](#5-create-a-device-group)

1. [创建 autopilot 配置文件并将其分配给设备组。](#6-create-autopilot-profile-and-assign-it-to-the-device-group)

1. [创建注册状态页 (ESP) 配置，并将其分配给设备组。](#7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group)

1. [验证 HoloLens 设备的配置文件状态。](#8-verify-the-profile-status-of-the-hololens-devices)

### <a name="1-review-requirements-for-windows-autopilot-for-hololens-2"></a>1. 查看适用于 HoloLens 2 的 Windows Autopilot 要求

#### <a name="review-the-following-sections-of-the-windows-autopilot-requirements-article"></a>参阅 Windows Autopilot 要求文章的以下部分：

- [网络要求](/mem/autopilot/networking-requirements)  
- [许可要求](/mem/autopilot/licensing-requirements)  
- [配置要求](/mem/autopilot/configuration-requirements)

查看 Windows Autopilot 自部署模式文章“[要求](/windows/deployment/windows-autopilot/self-deploying#requirements)”部分。 环境必须满足这些要求以及 Windows Autopilot 标准要求。 无需查看文章中的“分步操作”和“验证”部分。 本文后面的过程将提供特定于 HoloLens 的相应步骤。

确保设备尚未成为 Azure AD 的成员，并且未在 Intune（或其他 MDM 系统）中注册。 Autopilot 自部署过程完成这些步骤。 若要确保所有设备相关信息都已得到清理，请检查 Azure AD 和 Intune 门户中的“设备”页面。 HoloLens 目前暂不支持“将所有目标设备转换为 Autopilot”的功能。

#### <a name="review-hololens-os-requirements"></a>查看 HoloLens 操作系统要求：

若要确认设备上的内部版本或重刷到最新的操作系统，请使用 [Advanced Recovery Companion (ARC)](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=2&activetab=pivot:overviewtab) 和我们的[设备重刷说明](hololens-recovery.md)。 在 2020 年 9 月底之前交付的设备已预安装 Windows 全息版（版本 1903）。 请与经销商联系，确保向你提供的是预安装了 Autopilot 的设备。

 最低操作系统版本 | 受支持的功能 | 注解
 ------ | ------ | ------  
 [Windows 全息版（版本 2004）](hololens-release-notes.md#windows-holographic-version-2004)（内部版本 19041.1103）或更高版本 | 1. HoloLens 2 上 Autopilot 的自部署场景。 | 仅支持通过以太网下载 Autopilot 配置文件。 在打开 HoloLens 之前，使用“USB-C 转以太网”适配器确保其已连接到以太网。  如果计划将 Autopilot 部署到多个 HoloLens 设备，我们建议对适配器基础结构进行规划。 我们不建议使用 USB 集线器，因为它们通常需要安装第三方驱动程序，而 HoloLens 不支持这些驱动程序。
 [Windows 全息版（版本 20H2）](hololens-release-notes.md#windows-holographic-version-20h2)（内部版本 19041.1128）或更高版本 | 1. 通过 Wi-Fi 下载 autopilot 配置文件。 <br> 2. [租户锁定 CSP 和 Autopilot](#tenant-lockdown-csp-and-autopilot) 用于锁定具有 Autopilot 指定租户的设备。 | 如果需要，仍可以使用以太网适配器。 对于通过 Wi-Fi 连接的设备，用户必须仅： <ul> <li> 转到 hummingbird 场景。 </li> <li> 选择语言和区域设置。 </li> <li> 运行目视校准。 </li> <li> 成功连接到所需的 WiFi 网络。 </li> </ul>

### <a name="2-enable-automatic-mdm-enrollment"></a>2. 启用自动 MDM 注册：

为使 Autopilot 成功运行，需要在 Azure 门户中启用自动 MDM 注册。 这将允许设备在没有用户的情况下注册。

请阅读以下关于[启用 MDM 自动注册的简短指南](/windows/client-management/mdm/azure-ad-and-microsoft-intune-automatic-mdm-enrollment-in-the-new-portal)或[自动注册快速入门指南](/mem/intune/enrollment/quickstart-setup-auto-enrollment)，以获取更多设置信息。

### <a name="3-ensure-that-mdm-enrollment-isnt-blocked-for-windows-devices"></a>3. 确保未阻止 Windows 设备进行 MDM 注册。

为使 Autopilot 成功，需要确保 HoloLens 设备能够注册。 由于 HoloLens 被认为是 Windows 设备，因此需要杜绝可能阻止部署的任何注册限制。 [查看此限制列表](/mem/intune/enrollment/enrollment-restrictions-set)，确保能够注册设备。

### <a name="4-register-devices-in-windows-autopilot"></a>4. 在 Windows Autopilot 中注册设备

在首次设置之前，设备必须在 Windows Autopilot 中注册。

注册 HoloLens 设备有三种主要方法：

 - 当你下订单时，经销商可在合作伙伴中心注册设备。

   > [!NOTE]  
   > 这是添加设备到 Autopilot 服务的推荐方法。 [了解详细信息](/mem/autopilot/partner-registration)。  

 - 你可以直接向 Microsoft [提交支持请求](hololens2-autopilot-registration-support.md)。
 - 检索硬件哈希（也称为硬件 ID）并在 MEM 管理中心手动注册设备。

#### <a name="obtain-hardware-hash"></a>获取硬件哈希

可以从设备检索硬件哈希。 设备在进行 OOBE 过程时，或之后当设备所有者启动诊断日志收集过程时（在以下过程中描述），设备将其硬件哈希记录在 CSV 文件中。 通常情况下，设备所有者是第一个登录到设备的用户。

> [!WARNING]
> 在 20H2 之前的内部版本中，如果已进行 OOBE 过程，并且遥测设置为“必需”，则无法通过此方法收集 Autopilot 的硬件哈希。 为了通过此方法收集硬件哈希，请通过设置应用将遥测选项设置为“完全”，然后选择“隐私” > “诊断” 。

1. 启动 HoloLens 2 设备。

1. 在设备上，同时按下“电源”和“调低音量”按钮，然后释放这两个按钮 。 设备将收集诊断日志和硬件哈希，并将它们存储在一组 .zip 文件中。

1. 有关如何执行此操作的完整详细信息和指导视频，请了解[脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics)。

1. 使用 USB-C 电缆将设备连接到计算机。

1. 在计算机上，打开文件资源管理器。 打开 <b>This PC\\</b><*HoloLens 设备名称*><b>Internal Storage\\Documents</b>\\，找到 AutopilotDiagnostics.zip 文件。  

   > [!NOTE]  
   > .zip 文件可能不会立即可用。 如果文件尚未准备好，可能会在“文档”文件夹中看到一个 HoloLensDiagnostics.temp文件。 若要更新文件列表，请刷新窗口。

1. 提取 AutopilotDiagnostics.zip 文件的内容。

1. 在提取的文件中，找到文件名前缀为 “DeviceHash”的 CSV 文件。 将该文件复制到计算机的驱动器中，方便以后在此处访问该文件。  

   > [!IMPORTANT]  
   > CSV 文件中的数据应使用以下标题和行格式：
   >
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

#### <a name="register-device-through-mem"></a>通过 MEM 注册设备

1. 在 [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com)中，选择“设备” > “Windows” > “Windows 注册”，然后选择“Windows Autopilot Deployment 计划”下的“设备” > “导入”。

1. 在“添加 Windows Autopilot 设备”下，选择 DeviceHash CSV 文件，选择“打开”，再选择“导入”  。  

   > [!div class="mx-imgBorder"]
   > ![使用“导入”命令导入硬件哈希。](./images/hololens-ap-hash-import.png)

1. 导入完成后，选择“设备” > “Windows” > “Windows 注册” > “设备” > “同步”。此过程可能需要几分钟才能完成，具体取决于要同步的设备数。 若要查看已注册的设备，请选择“刷新”。  

   > [!div class="mx-imgBorder"]
   > ![使用“同步”和“刷新”命令查看设备列表。](./images/hololens-ap-devices-sync.png)  

### <a name="5-create-a-device-group"></a>5. 创建设备组

1. 在 [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com)中，选择“组” > “新建组”。

1. 对于“组类型”，选择“安全性” ，然后输入组名称和说明。

1. 对于“成员身份类型”，选择“已分配”或“动态设备”  。

1. 执行下列操作之一：  

   - 如果在上一步中为“成员身份类型”选择了“已分配”，请选择“成员”  ，然后将 Autopilot 设备添加到组。 通过将设备序列号用作设备名称，列出尚未注册的 Autopilot 设备。
   - 如果在上一步中为“成员身份类型”选择了“动态设备”，请选择“动态设备成员”  ，然后在“高级规则”中输入类似于以下内容的代码：
     - 若要创建包括所有 Autopilot 设备的组，请键入：`(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Intune 的组标签字段映射到 Azure AD 设备上的 OrderID 属性。 如果要创建一个包含所有具有特定组标签的 Autopilot 设备的组（Azure AD 设备 OrderID），必须键入：`(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - 如果想要创建包含所有具有特定采购订单 ID 的 Autopilot 设备的组，请键入：`(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > 这些规则针对 Autopilot 设备独有的属性。
1. 依次选择“保存”和“创建”。

### <a name="6-create-autopilot-profile-and-assign-it-to-the-device-group"></a>6. 创建 autopilot 配置文件并将其分配给设备组

1. 在 [Microsoft Endpoint Manager 管理中心](https://endpoint.microsoft.com)中，依次选择选择“设备” > “Windows” > “Windows 注册” > “Windows Autopilot 部署配置文件” > “创建配置文件” > “HoloLens”。
   ![“创建配置文件”下拉菜单包括一个 HoloLens 项。](./images/hololens-ap-enrollment-profiles.png)

1. 输入配置文件名称和说明，然后选择“下一步”。  
   你将看到一个包含 HoloLens 的列表。 如果不存在此选项，请使用[反馈](hololens2-autopilot.md#feedback-and-support-for-autopilot)选项之一与我们联系。

   > [!div class="mx-imgBorder"]
   > ![添加配置文件名称和说明。](./images/hololens-ap-profile-name.png)

1. 在“全新体验(OOBE)”页上，大多数设置已预先配置，以简化此评估的 OOBE。 另外，还可配置以下设置：  

   - “语言(地区)”：选择 OOBE 的语言。 建议从 [HoloLens 2 支持的语言](hololens2-language-support.md)列表中选择一种语言。
   - “自动配置键盘”：若要确保键盘与所选语言匹配，请选择“是”。
   - “应用设备名称模板”：若要在 OOBE 期间自动设置设备名称，请选择“是”，然后在“输入一个名称”中输入模板短语和占位符，例如，输入前缀和 `%RAND:4%` &mdash; 四位随机数字的占位符。
     > [!NOTE]  
     > 如果使用设备名称模板，OOBE 进程将在应用设备名称之后和将设备加入 Azure AD 之后重新启动该设备。 重新启动后，新名称才会生效。  

   > [!div class="mx-imgBorder"]
   > ![配置 OOBE 设置。](./images/hololens-ap-profile-oobe.png)

1. 配置设置后，选择“下一步”。
1. 在“作用域标签”页上，按需添加要应用到此配置文件的作用域标签。 若要详细了解作用域标记，请参阅[将基于角色的访问控制和作用域标记用于分布式 IT](/mem/intune/fundamentals/scope-tags.md)。 完成后，选择“下一步”。
1. 在“分配”页上，为“分配给”选择“所选组”。
1. 在“所选组”下，选择“+ 选择要包括的组”。
1. 在“选择要包括的组”列表中，选择为 Autopilot HoloLens 设备创建的设备组，然后选择“下一步”。  
  
   如果要排除任何组，请选择“选择要排除的组”，然后选择要排除的组。

   > [!div class="mx-imgBorder"]
   > ![将设备组分配给配置文件。](./images/hololens-ap-profile-assign-devicegroup.png)

1. 在“查看 + 创建”页上，查看设置，然后选择“创建”创建配置文件。  

   > [!div class="mx-imgBorder"]
   > ![查看 + 创建。](./images/hololens-ap-profile-summ.png)

### <a name="7-create-enrollment-status-page-esp-configuration-and-assign-it-to-the-device-group"></a>7. 创建注册状态页 (ESP) 配置，并将其分配给设备组

注册状态页面 (ESP) 显示完整的设备配置过程的状态，此过程在 MDM 托管用户首次登录设备时运行。 请确保你的 ESP 配置类似于以下内容，并验证分配是否正确。  

> [!div class="mx-imgBorder"]
> ![ESP 配置。](./images/hololens-ap-profile-settings.png)

有关 ESP 的详细信息，请参阅[设置注册状态页 - Microsoft Intune | Microsoft Docs](/mem/intune/enrollment/windows-enrollment-status)

### <a name="8-verify-the-profile-status-of-the-hololens-devices"></a>8. 验证 HoloLens 设备的配置文件状态

1. 在 Microsoft Endpoint Manager 管理中心中，依次选择“设备” > “Windows” > “Windows 注册” > “设备”。

1. 验证是否列出了 HoloLens 设备，以及其配置文件的状态是否为“已分配”。  

   > [!NOTE]  
   > 可能需要几分钟的时间才能将配置文件分配给设备。  

   > [!div class="mx-imgBorder"]
   > ![设备和配置文件分配。](./images/hololens-ap-devices-assignments.png)

## <a name="windows-autopilot-for-hololens-2-user-experience"></a>适用于 HoloLens 2 的 Windows Autopilot 用户体验

完成上述说明操作后，HoloLens 2 用户将通过以下体验来预配其 HoloLens 设备：  

1. Autopilot 体验需要访问 Internet。 请使用以下选项之一提供 Internet 访问：

    - 在 OOBE 期间，将设备连接到 Wi-Fi 网络，然后让它自动检测 Autopilot 体验。 这是唯一需要你与 OOBE 交互的地方，直到 Autopilot 体验自行完成。

    - 使用“USB-C 转以太网”适配器将设备与以太网连接，以实现有线 Internet 连接，并让 HoloLens 2 自动完成 Autopilot 体验。

    - 通过“USB-C 转 Wi-Fi”适配器连接设备以实现无线 Internet 连接，并让 HoloLens 2 自动完成 Autopilot 体验。

        > [!IMPORTANT]  
       > 尝试在 OOBE 过程中使用 Wi-Fi 网络完成 Autopilot 体验的设备必须使用 [Windows 全息版（版本 20H2）](hololens-release-notes.md#windows-holographic-version-20h2)。
       >
       > 对于使用以太网适配器的设备，必须在全新体验 (OOBE) 启动之前将设备连接到网络。 设备在第一个 OOBE 屏幕上确定是否将其预配为 Autopilot 设备。 如果设备无法连接到网络，或者如果选择不将设备预配为 Autopilot 设备，则以后无法更改为 Autopilot 预配。 相反，必须重新开始此过程，才能将设备预配为 Autopilot 设备。

1. 设备应自动启动 OOBE。 不要与 OOBE 交互。

    > [!IMPORTANT]
    > 在 Autopilot 部署期间，请勿与 OOBE 交互或按下电源按钮使系统进入待机/关闭状态。 这可能会导致 Autopilot 流无法完成。

   让 HoloLens 2 检测网络连接并允许它自动完成 OOBE。 设备可能会在 OOBE 过程中重启。 OOBE 屏幕应类似于以下内容。

   ![OOBE 步骤 1。](./images/autopilot-welcome.jpg)
   ![OOBE 步骤 2。](./images/autopilot-step-complete.jpg)
   ![OOBE 步骤 3。](./images/autopilot-device-setup.jpg)

1. OOBE 结束时，你可以使用用户名和密码登录到设备。

   <img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## <a name="tenant-lockdown-csp-and-autopilot"></a>租户锁定云解决方案提供商和 Autopilot

从 Windows 全息版（版本 20H2）起，HoloLens 2 设备支持 TenantLockdown 云解决方案提供商。 该云解决方案提供商将设备锁定在组织的租户上，即使在设备重置或重刷的情况下，也能将设备保持在该租户上。

[TenantLockdown](/windows/client-management/mdm/tenantlockdown-csp) 云解决方案提供商允许仅使用 Autopilot 将 HoloLens 2 绑定到 MDM 注册。 在 HoloLens 2 上将 TenantLockdown 云解决方案提供商的 RequireNetworkInOOBE 节点设置为 true 或 false（初始设置）值后，即使执行了重刷、操作系统更新等操作，值仍将保留在设备上。

在 HoloLens 2 上将 TenantLockdown 云解决方案提供商的 RequireNetworkInOOBE 节点设置为 true 后，OOBE 将无限期等待 Autopilot 配置文件在网络连接后成功下载并应用。

在 HoloLens 2 上将 TenantLockdown 云解决方案提供商的 RequireNetworkInOOBE 节点设置为 true 后，OOBE 中将不允许执行以下操作：

- 使用运行时预配创建本地用户
- 通过运行时预配执行 Azure AD 加入操作
- 选择 OOBE 体验中的设备所有者

#### <a name="how-to-set-this-using-intune"></a>如何使用 Intune 对此进行设置？

1. 创建自定义 OMA URI 设备配置文件，并为 RequireNetworkInOOBE 节点指定 true，如下所示。
OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 OMA-URI 设置租户锁定。](images/hololens-tenant-lockdown.png)

1. 创建组并将设备配置文件分配给该设备组。

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。  

在 Intune 门户中验证设备配置是否已成功应用。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的影响将处于活动状态。

#### <a name="how-to-unset-tenantlockdowns-requirenetworkinoobe-on-hololens-2-using-intune"></a>如何使用 Intune 在 HoloLens 2 上取消设置 TenantLockdown 的 RequireNetworkInOOBE？

1. 将 HoloLens 2 从先前分配了上面创建的设备配置的设备组中删除。

1. 创建基于 OMA URI 的自定义设备配置文件，并针对 RequireNetworkInOOBE 指定 false，如下所示。
OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![在 Intune 中通过 OMA URI 将 RequireNetworkInOOBE 设置为 false 的屏幕截图。](images/hololens-tenant-lockdown-false.png)

1. 创建组并将设备配置文件分配给该设备组。

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。

在 Intune 门户中验证设备配置是否已成功应用。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的影响将处于非活动状态。

#### <a name="what-would-happen-during-oobe-if-autopilot-profile-is-unassigned-on-a-hololens-after-tenantlockdown-was-set-to-true"></a>将 TenantLockdown 设置为 true 后，如果在 HoloLens 上取消分配 Autopilot 配置文件，在 OOBE 期间会发生什么情况？

OOBE 将无限期等待 Autopilot 配置文件下载，并将显示以下对话框。 为了删除 TenantLockdown 的影响，必须首先仅使用 Autopilot 将设备注册到其原始租户，并且必须按照上一步中的说明取消设置 RequireNetworkInOOBE，然后才能删除 TenantLockdown 云解决方案提供商引入的限制。

![在设备上实施策略时的设备内视图。](images/hololens-autopilot-lockdown.png)

## <a name="known-issues-and-limitations"></a>已知问题和限制

### <a name="why-do-i-see-0x80180014-during-autopilot"></a>为什么在 Autopilot 中看到 0x80180014？

当在设备上执行 Autopilot 过程时，会显示此错误。 仅在 HoloLens 设备执行完以下操作时才会显示此问题：

1. 已至少执行完一次 Autopilot。
1. 现在正在重置并再次用于 Autopilot。

体验是 Autopilot 失败并出现特定错误。

![HoloLens Autopilot 失败错误代码](images/autopilot-0x80180014-failure.jpg)

若要解决此错误，需要执行哪些步骤？

1. 按照 [Autopilot 设备导入和注册疑难解答](/mem/autopilot/troubleshoot-device-enrollment#error-code-0x80180014-when-re-enrolling-using-self-deployment-or-pre-provisioning-mode)中的步骤从 Intune 中移除设备。 （你的 Intune 管理员将需要执行此任务）
1. 步骤 1 完成后，重启设备并登录。
1. 导航到“设置” -> “更新和安全” -> “重置和恢复”，然后选择“开始使用”   。
    1. 如果步骤 2 和步骤 3 出现问题，请参阅[重置/重新刷写 HoloLens](hololens-recovery.md) 中重置设备的替代方法。

然后，AutoPilot 应该会成功注册。

### <a name="troubleshooting"></a>疑难解答

以下文章可能是你了解详细信息和排查 Autopilot 问题的有用资源，但这些文章是基于Windows 10 桌面版的，并非所有信息都适用于 HoloLens：

- [Windows Autopilot - 已知问题](/mem/autopilot/known-issues)
- [Microsoft Intune 中的 Windows 设备注册问题疑难解答](/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - 策略冲突](/mem/autopilot/policy-conflicts)

#### <a name="why-did-i-not-see-autopilot-experience-even-though-the-autopilot-profile-is-assigned-in-intune"></a>为什么即使在 Intune 中分配了 Autopilot 配置文件也看不到 Autopilot 体验？

默认情况下，HoloLens 2 在检测到 Internet 后会等待 15 秒再检测 Autopilot。 如果在 15 秒后未检测到 Autopilot 配置文件，则表示未正确发现 Autopilot，你将看到 EULA 页面。

请重启设备并重试。 有关详细信息，请参阅[已知问题和限制](hololens2-autopilot.md#known-issues-and-limitations)。

## <a name="feedback-and-support-for-autopilot"></a>Autopilot 反馈与支持

若要提供反馈或报告问题，请使用以下方法之一：

- 有关设备注册方面的支持，请联系你的经销商或分销商。
- 有关 Windows Autopilot 的常规支持问询或配置文件分配、组创建或 MEM 门户控件等问题，[请联系 Microsoft Endpoint Manager 支持](/mem/get-support)  
- 如果你的设备已注册到 Autopilot 服务，并且配置文件已分配在 MEM 门户上，请联系 HoloLens [支持](/hololens/)（参见“支持”卡）。 请开具支持票证，如果适用，请在全新体验 (OOBE) 期间捕获[脱机诊断日志](hololens-diagnostic-logs.md#offline-diagnostics)（包括屏幕截图和日志）。
- 若要从设备上报告问题，请使用 HoloLens 上的反馈中心应用程序。 在反馈中心，选择“企业管理” > “设备”类别。
- 若要提供有关适用于 HoloLens 的 Autopilot 的常规反馈，可提交此[调查](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993)

## <a name="delete-autopilot-devices"></a>删除 Autopilot 设备

你可能希望不再使用 Autopilot 设备，或者希望将你的设备注册到其他租户。 如果要执行此操作，请参阅[如何删除 Autopilot 设备。](/mem/autopilot/add-devices#delete-autopilot-devices)
