---
title: 适用于 HoloLens 2 的 Windows Autopilot
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
ms.openlocfilehash: 95f187b2a4b6a86b59e05f3b12414c84ca0f6460
ms.sourcegitcommit: fac3e62c1fd4dd531c2c8620870213cd570980dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "11205764"
---
# 适用于 HoloLens 2 的 Windows Autopilot

从 Windows 全息版 2004 版本开始，HoloLens 2 支持 Windows Autopilot [自部署模式](https://docs.microsoft.com/mem/autopilot/self-deploying)。 管理员可在 Microsoft 终结点管理器中配置（OOBE）的全新体验，并允许终端用户在几乎未有交互的情况中为业务使用准备设备。 这减少了库存管理的开销、设备准备的成本以及员工在设置体验期间的支持电话。 若要了解更多有关 Windows Autopilot 的详细信息，请单击 [此处](https://docs.microsoft.com/mem/autopilot/windows-autopilot)。

与 Surface 设备一样，建议客户使用其 Microsoft [云解决方案提供商](https://partner.microsoft.com/cloud-solution-provider) (经销商或分销商) ，以通过合作伙伴中心将设备注册到 Autopilot 服务中。 [此处](https://docs.microsoft.com/mem/autopilot/add-devices)概述了设备注册的其他方法，尽管利用 Microsoft 的渠道合作伙伴可确保最有效的端到端路径。 

> [!NOTE]
> 截至11/20/2020，Microsoft 终结点管理器中 HoloLens 的 Autopilot 配置正在到 **公共预览版**。 客户无需再注册私人预览，所有租户都可在 MEM 管理中心中设置 Autopilot。

当用户启动 Autopilot 自部署过程时，Autopilot 会完成以下步骤：

1. 将设备加入 Azure Active Directory （Azure AD）。 请注意，Autopilot for HoloLens 不支持可用目录联接或混合 Azure AD 联接。
   
1. 使用 Azure AD 将设备注册到 Microsoft 终结点管理器（或其他 MDM 服务）中。

1. 下载并应用针对设备的策略、证书、网络配置文件和应用程序。

1. 预配设备。

1. 向用户呈现登录屏幕。


## 为 HoloLens 2 配置 Autopilot

请按照以下步骤设置你的环境：

1. [查看 HoloLens 2 的 Windows Autopilot 要求。](#1-review-requirements-for-windows-autopilot-for-hololens-2)

1. [在 Windows Autopilot 注册设备。](#2-register-devices-in-windows-autopilot)

1. [创建设备组。](#3-create-a-device-group)

1. [创建部署配置文件。](#4-create-a-deployment-profile)

1. [验证注册状态页面（ESP）配置。](#5-verify-the-esp-configuration)

1. [验证 HoloLens 设备的配置文件状态。](#6-verify-the-profile-status-of-the-hololens-devices)


#### 1. 查看适用于 HoloLens 2 的 Windows Autopilot 的要求

**参阅 Windows Autopilot 要求文章的以下部分：**

- [网络要求](https://docs.microsoft.com/mem/autopilot/networking-requirements)  
- [许可要求](https://docs.microsoft.com/mem/autopilot/licensing-requirements)  
- [配置需求](https://docs.microsoft.com/mem/autopilot/configuration-requirements)

**查看 Windows Autopilo 自部署模式文章的“[要求](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)”部分。** 环境必须满足这些要求以及 Windows Autopilot 标准要求。 无需查看本文的“分步操作”和“验证”部分。 本文后面的过程提供了特定于 HoloLens 的相应步骤。 有关如何注册设备和配置配置文件的信息，请参阅 [2. 在 Windows Autopilot 中注册设备](#2-register-devices-in-windows-autopilot) 以及 [4. 在本文中创建部署配置文件](#4-create-a-deployment-profile) 。 若要配置和管理 Autopilot 自部署模式配置文件，请确保你有权访问[Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com)。

**查看 HoloLens 操作系统要求：**

- 设备必须使用 [Windows 全息版，2004 版本](hololens-release-notes.md#windows-holographic-version-2004) （内部版本 19041.1103）或更高版本。 若要确认设备上的内部版本或重新刷新到最新操作系统，可使用 [高级恢复配套（ARC）](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab)。 可在 [此处](https://docs.microsoft.com/hololens/hololens-recovery#clean-reflash-the-device) 找到说明。 请注意，在 2020 年 9 月底之前交付的设备已预安装了 Windows 全息 1903 版本。 请与经销商联系，以确保 Autopilot 的设备已向你发送。

- Windows 全息 2004 版本仅支持通过以太网连接的 Autopilot。 **在开启 HoloLens 之前**，请确保使用 “USB-C转以太网” 适配器已连接到以太网。 设备启动后，无需用户交互。 如果计划将 Autopilot 推广到许多 HoloLens 设备上，我们建议对适配器基础设施进行规划。 我们不推荐使用 USB 集线器，因为它们通常需要安装额外的第三方驱动程序，而 HoloLens 不支持这些驱动程序。 

- [Windows 全息 20H2 版本](hololens-release-notes.md#windows-holographic-version-20h2)（内部版本 19041.1128）或更高版本通过 Wi-Fi 支持 Autopilot，尽管仍然可使用以太网适配器。  对于通过 Wi-Fi 连接的设备，用户必须仅：

     - 转到 hummingbird 场景
     - 选择语言和地区
     - 运行目视校准
     - 建立网络连接


- Windows 全息 20H2 版本支持 [Tenantlockdown 云解决方案提供商和 Autopilot](hololens2-autopilot.md#tenantlockdown-csp-and-autopilot)，这会将设备锁定在一个租户上，并确保在意外或故意重置或擦除的情况下，设备仍与该租户绑定。  

- 确保设备尚未成为 Azure AD 的成员，并且未在 Intune （或其他 MDM 系统）中注册。 Autopilot 自部署过程完成这些步骤。 若要确保清理所有设备相关信息，请检查 Azure AD 和 Intune 门户中的“**设备**”页面。 请注意，目前 HoloLens 不支持 “将所有目标设备转换为 Autopilot 功能。  

### 2. 在 Windows Autopilot 中注册设备

在首次设置之前，设备必须在 Windows Autopilot 中注册。 有关 MEM 的设备注册文档，请参阅 [将设备添加到 Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices)。  

注册 HoloLens 设备有两种主要方法： 

 - **当你下订单时，经销商可在合作伙伴中心注册设备。** 

   > [!NOTE]  
   > 这是添加设备到 Autopilot 服务的推荐路径。 [了解详细信息](https://docs.microsoft.com/mem/autopilot/add-devices#reseller-distributor-or-partner-registration)。  
   
 - **检索硬件哈希（也称为硬件 ID）并在 MEM 管理中心手动注册设备**。  

**检索硬件哈希**

设备在 OOBE 过程中，或之后当设备所有者启动诊断日志收集过程时，将其硬件哈希记录在 CSV 文件中（在以下过程中描述）。 通常情况下，设备所有者是第一个登录到设备的用户。

1. 启动 HoloLens 2 设备。

1. 在设备上，同时按下 **电源** 和 **音量** 按钮，然后松开它们。 设备收集诊断日志和硬件哈希，并将它们存储在一组 .zip 文件中。 

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

**通过 MEM 注册设备**

1. 在[Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com)中，选择** 设备 ** > **Windows** >  **Windows 注册**设备"，然后选择**设备** > **导入**至**Windows Autopilot 部署程序**下的设备。

1. 在“**添加 Windows Autopilot 设备**”中，选择 DeviceHash CSV 文件，选择“**打开**”，然后选择“**导入**”。  
   
   > [!div class="mx-imgBorder"]
   > ![使用导入命令导入硬件哈希。](./images/hololens-ap-hash-import.png)
   
1. 完成导入后，选择“**设备**” > “**Windows**” > “**Windows 注册**” > “**设备**” > “**同步**”。此过程可能需要几分钟时间才能完成，具体取决于同步的设备数量。 若要查看已注册的设备，请选择“**刷新**”。  
   
   > [!div class="mx-imgBorder"]
   > ![使用“同步”和“刷新”命令查看设备列表。](./images/hololens-ap-devices-sync.png)  

### 3. 创建设备组

1. 在 [Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com) 中，选择 **组** > **新组**。

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
1. 选择 **保存**，然后选择**创建**。

### 4. 创建部署配置文件

1. 在[Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com)中，选择 **设备** > **Windows** > **Windows 注册** > **Windows Autopilot 部署配置文件** > **创建配置文件** > **HoloLens**。
   ![创建配置文件下拉菜单包括一个 HoloLens 项目。](./images/hololens-ap-enrollment-profiles.png)

1. 输入配置文件名称和说明，然后选择“**下一步**”。  
   你将看到包括 **HoloLens**的列表。 如果不存在此选项，请使用[反馈](hololens2-autopilot.md#feedback-and-support-for-autopilot)选项之一与我们联系。

   > [!div class="mx-imgBorder"]
   > ![添加配置文件名称和说明](./images/hololens-ap-profile-name.png)
   
1. 在“**全新体验（OOBE）**”页面上，大多数设置都是预配置的，用于简化此评估的 OOBE。 另外可配置以下设置：  

   - **语言（区域）**：选择 OOBE 语言。 我们建议从[支持 HoloLens 2 的语言](hololens2-language-support.md)列表中选择一种语言。
   - **自动配置键盘**：若要确保键盘匹配所选语言，请选择“**是**”。
   - **应用设备名称模板**：若要在 OOBE 期间自动设置设备名称，请选择“**是**”，然后在“** 输入名称**”中输入模板短语和占位符。例如，输入前缀和`%RAND:4%`&mdash;四位随机数字的占位符。
     > [!NOTE]  
     > 如果使用设备名称模板，OOBE 进程将在应用设备名称之后和将设备加入 Azure AD 之前再次重新启动该设备。 重新启动后，新名称才会生效。  

   > [!div class="mx-imgBorder"]
   > ![配置 OOBE 设置](./images/hololens-ap-profile-oobe.png)
   
1. 配置设置后，选择“**下一步**”。
1. 在“**范围标记**”页面上，选择添加要应用于此配置文件的范围标记。 有关范围标记的详细信息，请参阅 [将基于角色的访问控制和范围标记用于分布式 IT](https://docs.microsoft.com/mem/intune/fundamentals/scope-tags.md)。 完成后，选择“**下一步**”。
1. 在“**分配 **”页面上，为“**分配至**”选择“**所选组**”。
1. 在“**所选组**”下，选择“** + 选择要包括的组**”。
1. 在“**选择要包含的组**”列表中，选择为 Autopilot HoloLens 设备创建的设备组，然后选择“**下一步**”。  
  
   如果要排除任何组，请选择“**选择要排除的组**”，然后选择希望排除的组。

   > [!div class="mx-imgBorder"]
   > ![将设备组分配到配置文件。](./images/hololens-ap-profile-assign-devicegroup.png)
   
1. 在“**审阅 + 创建**”页面上，查看设置，然后选择“**创建**”以创建配置文件。  
   
   > [!div class="mx-imgBorder"]
   > ![审阅 + 创建](./images/hololens-ap-profile-summ.png)

### 5. 验证 ESP 配置

注册状态页面（ESP）显示完整的设备配置过程的状态，此过程在 MDM 托管用户首次登录设备时运行。 请确保你的 ESP 配置类似于以下内容，并验证分配是否正确。  

> [!div class="mx-imgBorder"]
> ![ESP 配置](./images/hololens-ap-profile-settings.png)

### 6. 验证 HoloLens 设备的配置文件状态

1. 在 Microsoft 终结点管理器管理中心中，选择“**设备**” > “**Windows**” > “**Windows 注册**” > “**设备**”。

1. 验证是否列出了 HoloLens 设备，以及其配置文件的状态是否为“**已指派**”。  

   > [!NOTE]  
   > 可能需要几分钟时间，配置文件才会分配到设备。  

   > [!div class="mx-imgBorder"]   
   > ![设备和配置文件分配。](./images/hololens-ap-devices-assignments.png)

## 适用于 HoloLens 2 用户体验的 Windows Autopilot

完成上述说明后，HoloLens 2 用户将通过以下体验来预配其 HoloLens 设备：  

1. Autopilot 体验需要 Internet 访问。 请使用以下选项之一提供 Internet 访问：

    - 将你的设备连接到 OOBE 中的 Wi-Fi 网络，然后让它自动检测 Autopilot 体验。 这是你唯一需要与 OOBE 交互的时间，直到 Autopilot 体验自行完成。 请注意，默认情况下，HoloLens 2 会在检测到 Internet 后等待 10 秒钟以检测 Autopilot。 如果在 10 秒内未检测到 autopilot 配置文件，OOBE 将显示 EULA。 如果遇到这种情况，请重新启动你的设备，以便再次尝试检测 Autopilot。 另请注意，只有在设备上设置了 TenantLockdown 策略时，OOBE 才能无限期地等待 Autopilot。
    
    - 使用“USB-C 到以太网”适配器将设备与以太网连接，以实现有线 Internet 连接，并使 HoloLens 2 自动完成 Autopilot 体验。
    
    - 通过“USB-C 到 Wifi”适配器连接设备以实现无线 Internet 连接，并使 HoloLens 2 自动完成 Autopilot 体验。

        > [!IMPORTANT]  
       > 尝试将 OOBE 中的 Wi-Fi 网络用于 Autopilot 的设备必须位于 [Windows 全息版 20H2](hololens-release-notes.md#windows-holographic-version-20h2) 上。
       >
       > 对于使用以太网适配器的设备，必须在开箱即用体验 (OOBE) 启动之前将设备连接到网络。 设备在第一个 OOBE 屏幕上确定是否将其配置为 Autopilot 设备。 如果设备无法连接到网络，或者选择不将其配置为 Autopilot 设备，则以后无法更改为 Autopilot 配置。 相反，必须启动此过程，以便将设备设置为 Autopilot 设备。

1. 设备应自动启动 OOBE。 不要与 OOBE 交互。 放松一下！ 让 HoloLens 2 检测网络连接并允许自动完成 OOBE。 设备可能会在 OOBE 过程中重启。 OOBE 屏幕应类似于以下内容。
   
   ![OOBE 步骤 1](./images/autopilot-welcome.jpg)
   ![OOBE 步骤 2](./images/autopilot-step-complete.jpg)
   ![OOBE 步骤3](./images/autopilot-device-setup.jpg)

1. OOBE 结束时，可以使用用户名和密码登录到设备。

   <br/><img src="./images/other-user.jpg" alt="Other user" width="450" height="700" />

## Tenantlockdown 云解决方案提供商和 Autopilot

HoloLens 2 设备从 Windows 全息 20H2 版本开始支持 TenantLockdown 云解决方案提供商。 该 CSP 将设备锁定在组织的租户上，即使在设备重置或重新刷新的情况下也能保持设备在该租户上。 

[TenantLockdown](https://docs.microsoft.com/windows/client-management/mdm/tenantlockdown-csp) CSP 允许仅使用 Autopilot 将 HoloLens 2 绑定到 MDM 注册。  在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 或 false（初始设置）值后，即使进行重新刷新、操作系统更新，该值仍将保留在设备上。 

在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 后， OOBE 将无限期等待 Autopilot 配置文件在网络连接后成功下载并应用。 

在 HoloLens 2 上将 TenantLockdown CSP 的 RequireNetworkInOOBE 节点设置为 true 后，OOBE 中不允许执行以下操作： 
- 使用运行时预配创建本地用户 
- 通过运行时预配执行 AAD 加入操作 
- 在 OOBE 体验中选择设备所有者 

#### 如何使用 Intune 设置此选项？ 
1. 创建自定义 OMA URI 设备配置配置文件，并为 RequireNetworkInOOBE 节点指定 true，如下所示。
OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 OMA-URI 设置租户锁定](images/hololens-tenant-lockdown.png)

1. 创建组并将设备配置文件分配给该设备组。 

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。  

在 Intune 门户中验证设备配置是否已成功应用。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的效果将处于活动状态。

#### 如何使用 Intune 在 HoloLens 2 上取消设置 TenantLockdown 的 RequireNetworkInOOBE？ 
1. 从先前分配了上面创建的设备配置的设备组中删除 HoloLens 2。 

1. 创建基于 OMA URI 的自定义设备配置配置文件，并为 RequireNetworkInOOBE 指定 false，如下所示。 OMA-URI 值应为 ./Vendor/MSFT/TenantLockdown/RequireNetworkInOOBE

   > [!div class="mx-imgBorder"]
   > ![通过 Intune 中的 OMA URI 将 RequireNetworkInOOBE 设置为 false 的屏幕截图](images/hololens-tenant-lockdown-false.png)

1. 创建组并将设备配置文件分配给该设备组。 

1. 使 HoloLens 2 设备成为在上一步中创建的组的成员并触发同步。

在 Intune 门户中验证设备配置是否已成功应用。 此设备配置成功应用于 HoloLens 2 设备后，TenantLockdown 的效果将处于非活动状态。 

#### 如果在 TenantLockdown 设置为 true 后在 HoloLens 上取消分配 Autopilot 配置文件，则 OOBE 期间会发生什么情况？ 
OOBE 将无限期等待 Autopilot 配置文件下载，并将显示以下对话框。 为了消除 TenantLockdown 的影响，必须首先仅使用 Autopilot 将设备注册到其原始租户，并且必须按照上一步中的说明取消设置 RequireNetworkInOOBE，然后才能删除 TenantLockdown CSP 引入的限制。 

![在设备上实施策略时的设备内视图。](images/hololens-autopilot-lockdown.png)

## 已知的问题 & 限制

- 我们正在研究在 MEM 中配置的基于设备上下文的应用程序安装在不适用于 HoloLens 的问题。 [了解有关设备上下文和用户上下文安装的详细信息。](https://docs.microsoft.com/mem/intune/apps/apps-windows-10-app-deploy#install-apps-on-windows-10-devices)
- 通过 Wi-Fi 设置 Autopilot 时，可能存在 Autopilot 配置文件在首次建立 Internet 连接时未下载的情况。 在此情况下，将显示最终用户许可协议 (EULA) ，并且用户可以选择继续非 Autopilot 的设置体验。 若要重新尝试使用自动驾驶仪进行设置，请将设备置于睡眠状态再重新启动，或者重启设备，让其再次尝试。
- 目前在 HoloLens 上还未支持 "将所有目标设备转换为 Autopilot" 的功能。  

### 疑难解答

以下文章可能是你了解更多信息和解决自动驾驶问题的有用资源，但请注意，这些文章是基于Windows 10 桌面版，并非所有信息都适用于 HoloLens：
- [Windows Autopilot - 已知问题](https://docs.microsoft.com/mem/autopilot/known-issues)
- [解决 Microsoft Intune 中的 Windows 设备注册问题](https://docs.microsoft.com/mem/intune/enrollment/troubleshoot-windows-enrollment-errors)
- [Windows Autopilot - 策略冲突](https://docs.microsoft.com/mem/autopilot/policy-conflicts)

## Autopilot 的反馈与支持

若要提供反馈或报告问题，请使用以下方法之一：

- 有关设备注册的支持，请联系你的经销商或分销商。
- 有关 Windows Autopilot 的常规支持查询或有关配置文件分配、组创建或 MEM 门户控件等问题， [请联系 Microsoft 终结点管理器支持](https://docs.microsoft.com/mem/get-support)  
- 如果你的设备已注册到 Autopilot 服务，并且配置文件分配在 MEM 门户上，请联系 HoloLens [支持部门](https://docs.microsoft.com/hololens/)（参阅 “支持” 卡）。 请开具支持票证，如果适用，请在开箱体验（OOBE）期间捕获 [脱机诊断日志](hololens-diagnostic-logs.md#offline-diagnostics) ，包括截图和日志。
- 若要从设备上报告问题，请使用 HoloLens 上的反馈中心应用程序。 在反馈中心中，选择**企业管理** > **设备**类别。 
- 若要提供有关 HoloLens Autopilot 的常规反馈以及，可提交此 [调查问卷](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR7vUmjNI0XhCp1T72ODD84xUMEM3TVJPOURBRkNVWkYwM0RWWEhJNVdJSi4u&wdLOR=cEF1F57F6-AD9B-4CCE-B919-AB5AE320A993) 


