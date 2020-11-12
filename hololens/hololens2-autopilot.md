---
title: 适用于 HoloLens 2 的 Windows Autopilot （个人预览版）
description: 如何在 HoloLens 2 设备上设置 Autopilot。
author: Teresa-Motiv
ms.author: v-tea
ms.date: 10/13/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: 5f887d7321c391ea9d67833373b39b3c9feeaf2c
ms.sourcegitcommit: 108b818130e2627bf08107f4e47ae159dd6ab1d2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163094"
---
# 适用于 HoloLens 2 的 Windows Autopilot

为 Windows Autopilot 计划设置 HoloLens 2 设备时，用户可以按照一个简单的过程从云中预配设备。

此 Autopilot 计划支持 Autopilot 自行部署模式，可将 HoloLens 2 设备设置为租户下的共享设备。 自部署模式在预配过程中利用设备的预安装 OEM 映像和驱动程序。 用户可预配设备，无需将设备采用并完成全新体验（OOBE）。 了解适用于 Windows 10 的 Windows Autopilot 的更多信息，请单击[此处](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)"。

用户启动 Autopilot 自部署进程时，该过程完成以下步骤：

1. 将设备加入 Azure Active Directory (Azure AD)。
   > [!NOTE]  
   > 适用于 HoloLens 的 Autopilot 不支持加入 Active Directory 或混合加入 Azure AD。
1. 使用 Azure AD 在 Microsoft Intune （或其他 MDM 服务）中注册设备。
1. 下载面向设备的策略、面向用户的应用、证书和网络配置文件。
1. 预配设备。
1. 向用户呈现登录屏幕。

## 适用于 HoloLens 2 的 Windows Autopilot 个人预览版

请按照以下步骤设置私人预览版的环境：

1. 请确保符合适用于 HoloLens 2 的 Windows Autopilot 的要求。
1. 注册“适用于 HoloLens 2 的 Windows Autopilot”个人预览版计划
1. 验证租户是否已启用 （已注册参加计划）
1. 在 Windows Autopilot 中注册设备
1. 创建设备组
1. 创建部署配置文件
1. 验证 ESP 配置
1. 配置 HoloLens 设备的自定义配置文件（已知问题）
1. 验证 HoloLens 设备的配置文件状态


### 1. 请确保符合适用于 HoloLens 2 的 Windows Autopilot 的要求。

**参阅 Windows Autopilot 要求文章的以下部分：**

- [网络要求](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [许可要求](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [配置需求](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)

**查看 Windows Autopilo 自部署模式文章的“[要求](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)”部分。** 环境必须满足这些要求以及 Windows Autopilot 标准要求。 无需查看本文的“分步操作”和“验证”部分。 本文后面的过程提供了特定于 HoloLens 的相应步骤。 有关如何注册设备和配置配置文件的信息，请参见本文中的[ 4. 在 Windows Autopilot 中注册设备](#4-register-devices-in-windows-autopilot)和[6. 创建部署配置文件](#6-create-a-deployment-profile)。 这些部分提供了适用于 HoloLens 的特殊步骤。

> [!IMPORTANT]  
> 适用于 HoloLens 2 的 Windows Autopilot 有特定的操作系统要求。 Autopilot 依赖于 HoloLens 设备上预安装的 Windows 全息版的版本 2004（内部版本 19041.1103 或更高版本）。 在 2020 年 9 月底之前交付的设备已预装了 Windows 全息版（版本 1903）。 请联系分销商，了解向你派发可使用 Autopilot 的设备的时间。 如果想要参加个人预览版，请查看下面的说明和要求。

每个 HoloLens OS 版本的 Autopilot 特定信息。
- 若要使用 Autopilot，设备必须具有 [Windows 全息版 2004](hololens-release-notes.md#windows-holographic-version-2004) 或更新版本。
- 为了通过 Wi-Fi 使用 Autopilot，设备必须具有 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 或更新版本。 但是，这些内部版本可能仍然使用以太网适配器。 
- 在内部版本 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 上，已启用新的设备管理选项 [Tenantlockdown CSP 和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)。  

如果你想要在你的设备上确认内部版本或更新它，请将其连接到 Windows 10 电脑并启动[高级恢复助理](https://www.microsoft.com/store/productId/9P74Z35SFRS8)。 

**如果你想尝试 Autopilot 预览版，请在启动 OOBE 和预配过程之前，确保 HoloLens 设备符合以下要求：**

- 确保设备安装了 Windows 全息版的版本 2004（内部版本 19041.1103 或更高版本）。 如果未预安装最新操作系统，则必须使用“[高级恢复配套（ARC）](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab)”手动更新。 可在[此处](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device)找到说明。 
- 设备必须在 Windows Autopilot 中注册。 有关如何注册设备的更多信息，请参阅 [4. 在 Windows Autopilot 中注册设备](#4-register-devices-in-windows-autopilot)。 推荐的方法是让经销商或分销商为你注册设备。  
- 在 [Windows 全息版 2004](hololens-release-notes.md#windows-holographic-version-2004) 中，在打开 HoloLens 并启动 Autopilot 预配过程之前，需要将设备连接到 Internet。 使用“USB-C 到以太网”适配器将设备连接到以太网，实现有线 Internet 连接。
- 在 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 中，设备可能连接到 OOBE 中的 Wi-Fi 以检测 Autopilot。 
- 设备尚不是 Azure AD 的成员，并且未在 Intune（或其他 MDM 系统）中注册。 Autopilot 自部署过程完成这些步骤。 若要确保清理所有设备相关信息，请检查 Azure AD 和 Intune 门户中的“**设备**”页面。
- 若要配置和管理 Autopilot 自部署模式配置文件，请确保你有权访问[Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com)。


### 2. 注册“适用于 HoloLens 2 的 Windows Autopilot”计划

**若要参与该计划，必须将租户注册到“专用预览版计划”。 这将为 Autopilot 启用 HoloLens 特定 Intune （也称为 MEM） UI 控件。** 若要执行此操作，请转到 [适用于 HoloLens 专用预览版的 Windows Autopilot](https://aka.ms/APHoloLensTAP) 或使用以下 QR 码提交请求。  

![Autopilot QR 码](./images/hololens-ap-qrcode.png)  

Microsoft 每周将会测试一次租户。 测试完成后，你将收到一封电子邮件通知。 

在此请求中，提供以下信息：

- 租户域
- 租户 ID
- 参与此评估的 HoloLens 2 设备数量
- 计划使用 Autopilot 自部署模式部署的 HoloLens 2 设备数量

### 3. 验证租户是否已启用

提交请求后，若要验证是否为 Autopilot 计划启用了租户，请按照以下步骤进行操作：

1. 登录 [Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com)。
1. 选择“**设备**” > “**Windows**” > “**Windows 注册**” > “**Windows Autopilot 部署配置文件**” > “**创建配置文件**”。  
   
   ![“创建配置文件”下拉列表包含一个 HoloLens 项。](./images/hololens-ap-enrollment-profiles.png)
  你将看到包括 **HoloLens**的列表。 如果不存在此选项，请使用[反馈](hololens2-autopilot.md#feedback-for-autopilot)选项之一与我们联系。

### 4. 在 Windows Autopilot 注册设备

在准备阶段，有两种主要方式可将设备注册到 Windows Autopilot： 

1. **下订单时，联系分销商或经销商以注册设备**或
2. **检索硬件哈希（也称为硬件 ID）并手动注册设备。** 

有关设备注册的详细信息，请参阅 [将设备添加到 Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices) 文档。  

**检索设备硬件哈希**

设备可以在 OOBE 过程中，或者稍后当设备所有者启动诊断日志收集过程（在以下过程中描述）时，将其硬件哈希记录在 CSV 文件中。 通常情况下，设备所有者是第一个登录到设备的用户。

1. 启动 HoloLens 2 设备。
1. 在设备上，同时按“电源”和“音量”按钮，然后松开。 设备收集诊断日志和硬件哈希，并将它们存储在一组 .zip 文件中。 
   1. 有关完整的详细信息和如何执行此操作的说明视频，请阅读有关[脱机诊断](hololens-diagnostic-logs.md#offline-diagnostics)的信息。 
1. 使用 USB-C 电缆将设备连接到计算机。
1. 在计算机上，打开“文件资源管理器”。 打开**此计算机 \\\<*HoloLens device name*>\\内部存储\\文档**，并定位至AutopilotDiagnostics.zip 文件。  

   > [!NOTE]  
   > .zip 文件可能不会立即可用。 如果该文件尚未准备好，可能会在“文档”文件夹中看到一个 HoloLensDiagnostics.temp文件。 若要更新文件列表，请刷新窗口。

1. 提取 AutopilotDiagnostics.zip 文件的内容。
1. 在提取的文件中，找到文件名前缀为 “DeviceHash” 的 CSV 文件。 将该文件复制到计算机上的驱动器上，以后可以访问它。  
   > [!IMPORTANT]  
   > CSV 文件中的数据应使用以下标题和行格式：
   > ```
   > Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User <serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>
   >```

**注册设备至 Windows Autopilot 中**

1. 在 Microsoft 终结点管理器管理中心中，选择“**设备**” > “** Windows **” >  “**Windows 注册**”，然后选择 **Windows Autopilot 部署计划**下的“**设备**” > “**导入**”。

1. 在“**添加 Windows Autopilot 设备**”中，选择 DeviceHash CSV 文件，选择“**打开**”，然后选择“**导入**”。  
   
   ![使用导入命令导入硬件哈希。](./images/hololens-ap-hash-import.png)
1. 完成导入后，选择“**设备**” > “**Windows**” > “**Windows 注册**” > “**设备**” > “**同步**”。此过程可能需要几分钟时间才能完成，具体取决于同步的设备数量。 若要查看已注册的设备，请选择“**刷新**”。  
   
   ![使用“同步”和“刷新”命令查看设备列表。](./images/hololens-ap-devices-sync.png)  

### 5. 创建设备组

1. 在Microsoft 终结点管理器管理中心中，选择“**组**” > “**新建组**”。
1. 对于“**组类型**”，选择“**安全性**”，然后输入组名称和描述。
1. 对于“**成员身份类型**”，选择“**已指派**” 或“**动态设备**”。
1. 执行下列操作之一：  
   
   - 如果在上一步中为“**成员身份类型**”选择了“**已指派**”，请选择“**成员**”，然后将 Autopilot 设备添加到组中。 通过将设备序列号用作设备名称，列出尚未注册的 Autopilot 设备。
   - 如果在上一步中为“**成员身份类型**”选择了“**动态设备**”，请选择“**动态设备成员**”，然后在“**高级规则**”中输入代码，如下所示：
     - 若要创建包含所有 Autopilot 设备的组，请键入： `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
     - Intune 的“组标记”字段映射到 Azure AD 设备的“**OrderID**”属性。 如果要创建一个包含所有具有特定组标签的 Autopilot 设备的组（Azure AD 设备OrderID），必须键入： `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
     - 如果你想要创建包含所有具有特定购买订单 ID 的 Autopilot 设备的组，请键入： `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`

     > [!NOTE]  
     > 这些规则针对 Autopilot 设备独有的属性。
1. 选择“**保存**”，然后选择“**创建**”。

### 6. 创建部署配置文件

1. 在 Microsoft 终结点管理器管理中心中，选择“**设备**” > “**Windows**” > “**Windows 注册**” > “**Windows Autopilot 部署配置文件**” > “**创建配置文件**” > “**HoloLens**”。
1. 输入配置文件名称和说明，然后选择“**下一步**”。  
   
   ![添加配置文件名称和说明](./images/hololens-ap-profile-name.png)
1. 在“**全新体验（OOBE）**”页面上，大多数设置都是预配置的，用于简化此评估的 OOBE。 另外可配置以下设置：  

   - **语言（区域）**：选择 OOBE 语言。 我们建议从[支持 HoloLens 2 的语言](hololens2-language-support.md)列表中选择一种语言。
   - **自动配置键盘**：若要确保键盘匹配所选语言，请选择“**是**”。
   - **应用设备名称模板**：若要在 OOBE 期间自动设置设备名称，请选择“**是**”，然后在“** 输入名称**”中输入模板短语和占位符。例如，输入前缀和`%RAND:4%`&mdash;四位随机数字的占位符。
     > [!NOTE]  
     > 如果使用设备名称模板，OOBE 进程将在应用设备名称之后和将设备加入 Azure AD 之前再次重新启动该设备。 重新启动后，新名称才会生效。  

   ![配置 OOBE 设置](./images/hololens-ap-profile-oobe.png)
1. 配置设置后，选择“**下一步**”。
1. 在“**范围标记**”页面上，选择添加要应用于此配置文件的范围标记。 有关范围标记的详细信息，请参阅 [将基于角色的访问控制和范围标记用于分布式 IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)。 完成后，选择“**下一步**”。
1. 在“**分配 **”页面上，为“**分配至**”选择“**所选组**”。
1. 在“**所选组**”下，选择“** + 选择要包括的组**”。
1. 在“**选择要包含的组**”列表中，选择为 Autopilot HoloLens 设备创建的设备组，然后选择“**下一步**”。  
  
   如果要排除任何组，请选择“**选择要排除的组**”，然后选择希望排除的组。

   ![将设备组分配到配置文件。](./images/hololens-ap-profile-assign-devicegroup.png)
1. 在“**审阅 + 创建**”页面上，查看设置，然后选择“**创建**”以创建配置文件。  
   
   ![审阅 + 创建](./images/hololens-ap-profile-summ.png)

### 7. 验证 ESP 配置

注册状态页面（ESP）显示完整的设备配置过程的状态，此过程在 MDM 托管用户首次登录设备时运行。 请确保你的 ESP 配置类似于以下内容，并验证分配是否正确。  

![EAP 配置](./images/hololens-ap-profile-settings.png)

### 8. 验证 HoloLens 设备的配置文件状态

1. 在 Microsoft 终结点管理器管理中心中，选择“**设备**” > “**Windows**” > “**Windows 注册**” > “**设备**”。
1. 验证是否列出了 HoloLens 设备，以及其配置文件的状态是否为“**已指派**”。  
   > [!NOTE]  
   > 可能需要几分钟时间，配置文件才会分配到设备。  
   
   ![设备和配置文件分配。](./images/hololens-ap-devices-assignments.png)

## 适用于 HoloLens 2 用户体验的 Windows Autopilot

完成上述说明后，HoloLens 2 用户将通过以下体验来预配其 HoloLens 设备：  

1. Autopilot 体验需要 Internet 访问。 请使用以下选项之一提供 Internet 访问：
    - 将你的设备连接到 OOBE 中的 Wi-Fi 网络，然后让它自动检测 Autopilot 体验。 这是你唯一需要与 OOBE 交互的时间，直到 Autopilot 体验自行完成。 请注意，默认情况下，HoloLens 2 会在检测到 Internet 后等待 10 秒钟以检测 Autopilot。 如果在 10 秒内未检测到 autopilot 配置文件，OOBE 将显示 EULA。 如果遇到这种情况，请重新启动你的设备，以便再次尝试检测 Autopilot。 另请注意，只有在设备上设置了 TenantLockdown 策略时，OOBE 才能无限期地等待 Autopilot。
    - 使用“USB-C 到以太网”适配器将设备与以太网连接，以实现有线 Internet 连接，并使 HoloLens 2 自动完成 Autopilot 体验。
    - 通过“USB-C 到 Wifi”适配器连接设备以实现无线 Internet 连接，并使 HoloLens 2 自动完成 Autopilot 体验。

       > [!NOTE]
       > 使用 Autopilot 将对[设备所有者](security-adminless-os.md#device-owner)产生影响。
   
       > [!IMPORTANT]  
       > 尝试将 OOBE 中的 Wi-Fi 网络用于 Autopilot 的设备必须位于 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 上。
       >
       > 对于使用以太网适配器的设备，必须在开箱即用体验 (OOBE) 启动之前将设备连接到网络。 设备在第一个 OOBE 屏幕上确定是否将其配置为 Autopilot 设备。 如果设备无法连接到网络，或者选择不将其配置为 Autopilot 设备，则以后无法更改为 Autopilot 配置。 相反，必须启动此过程，以便将设备设置为 Autopilot 设备。

1. 设备应自动启动 OOBE。 不要与 OOBE 交互。 放松一下！ 让 HoloLens 2 检测网络连接并允许自动完成 OOBE。 设备可能会在 OOBE 过程中重启。 OOBE 屏幕应类似于以下内容。
   
   ![OOBE 步骤 1](./images/hololens-ap-uex-1.png)
   ![OOBE 步骤 2](./images/hololens-ap-uex-2.png)
   ![OOBE 步骤 3](./images/hololens-ap-uex-3.png)
   ![OOBE 步骤 4](./images/hololens-ap-uex-4.png)

1. OOBE 结束时，可以使用用户名和密码登录到设备。

   ![OOBE 步骤 5](./images/hololens-ap-uex-5.png)

## 已知问题

- 无法安装使用设备安全上下文的应用程序。

## Tenantlockdown CSP 和 Autopilot
- 将设备锁定到租户后，即使进行设备重置或重新刷新也可将设备保留在组织的租户上。 通过预配禁用帐户创建，进一步增强安全性。 

从 Windows 全息版 20H2 开始，HoloLens 2 设备现在支持 TenantLockdown CSP。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 允许仅使用 Autopilot 将 HoloLens 2 绑定到 MDM 注册。 在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 或 false（初始设置）值后，即使进行重新刷新、操作系统更新，该值仍将保留在设备上。 

在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 后， OOBE 将无限期等待 Autopilot 配置文件在网络连接后成功下载并应用。 

在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 后，OOBE 中不允许执行以下操作： 
- 使用运行时预配创建本地用户 
- 通过运行时预配执行 AAD 加入操作 
- 在 OOBE 体验中选择设备所有者 

### 如何使用 Intune 设置此选项？ 
1. 创建自定义 OMA URI 设备配置配置文件，并为 RequireNetworkInOOBE 节点指定 true，如下所示。
OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 OMA-URI 设置租户锁定](images/hololens-tenant-lockdown.png)

1. 创建组并将设备配置文件分配给该设备组。 

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。  

在 Intune 门户中验证设备配置是否已成功应用。 此设备配置成功应用于 Hololens 2 设备后，TenantLockdown 的效果将处于活动状态。

### 如何使用 Intune 在 HoloLens 2 上取消设置 TenantLockdown 的 RequireNetworkInOOBE？ 
1. 从先前分配了上面创建的设备配置的设备组中删除 HoloLens 2。 

1. 创建基于 OMA URI 的自定义设备配置配置文件，并为 RequireNetworkInOOBE 指定 false，如下所示。 OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 Intune 中的 OMA URI 将 RequireNetworkInOOBE 设置为 false 的屏幕截图](images/hololens-tenant-lockdown-false.png)

1. 创建组并将设备配置文件分配给该设备组。 

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。

在 Intune 门户中验证设备配置是否已成功应用。 此设备配置成功应用于 Hololens 2 设备后，TenantLockdown 的效果将处于非活动状态。 

### 如果在 TenantLockdown 设置为 true 后在 HoloLens 上取消分配 Autopilot 配置文件，则 OOBE 期间会发生什么情况？ 
OOBE 将无限期等待 Autopilot 配置文件下载，并将显示以下对话框。 为了消除 TenantLockdown 的影响，必须首先仅使用 Autopilot 将设备注册到其原始租户，并且必须按照上一步中的说明取消设置 RequireNetworkInOOBE，然后才能删除 TenantLockdown CSP 引入的限制。 

![在设备上实施策略时的设备内视图。](images/hololens-autopilot-lockdown.png)

## Autopilot 的反馈

若要提供反馈或报告问题，请使用以下方法之一：

- 使用反馈中心应用。 可以在已连接 HoloLens 的计算机上找到此应用。 在反馈中心中，选择“**企业管理**” > “**设备**”类别。  

  提供反馈或报告问题时，请提供详细说明。 如果适用，则包括屏幕截图和日志。
- 向 [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com)发送电子邮件。 在“电子邮件主题”中，输入**\<*Tenant*>适用于 HoloLens 2 的 Autopilot 评估反馈**（其中 \<*Tenant*> 是 Intune 租户的名称）。

  在邮件中提供详细说明。 但是，除非支持人员特别要求，否则请勿包括屏幕截图或日志之类的数据。 此类数据可能包括私人或个人身份信息（PII）。
