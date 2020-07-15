---
title: 适用于 HoloLens 2 的 Windows Autopilot
description: ''
author: Teresa-Motiv
ms.author: v-tea
ms.date: 4/10/2020
ms.prod: hololens
ms.topic: article
ms.custom:
- CI 116283
- CSSTroubleshooting
audience: ITPro
ms.localizationpriority: high
keywords: autopilot
manager: jarrettr
ms.openlocfilehash: 9f7306e1e2f190634df7b25833e22b27089d19de
ms.sourcegitcommit: 29755f5af0086a43c532fb5a9a4ae65c36bc82de
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857780"
---
# 适用于 HoloLens 2 的 Windows Autopilot

为 Windows Autopilot 计划设置 HoloLens 2 设备时，用户可以按照一个简单的过程从云中预配设备。

此 Autopilot 计划支持 Autopilot 自行部署模式，可将 HoloLens 2 设备设置为租户下的共享设备。 自部署模式在预配过程中利用设备的预安装 OEM 映像和驱动程序。 用户可预配设备，无需将设备采用并完成全新体验（OOBE）。  

![Autopilot 自部署过程使用网络连接在“无外设”模式下配置共享设备。](./images/hololens-ap-intro.png)

用户启动 Autopilot 自部署进程时，该过程完成以下步骤：

1. 将设备加入 Azure Active Directory (Azure AD)。
   > [!NOTE]  
   > 适用于 HoloLens 的 Autopilot 不支持加入 Active Directory 或混合加入 Azure AD。
1. 使用 Azure AD 在 Microsoft Intune （或其他 MDM 服务）中注册设备。
1. 下载面向设备的策略、面向用户的应用、证书和网络配置文件。
1. 预配设备。
1. 向用户呈现登录屏幕。

## 适用于 HoloLens 2 的 Windows Autopilot：入门

以下步骤总结了适用于 HoloLens 2 的 Windows Autopilot 设置环境过程。 其余部分提供这些步骤的详细信息。

1. 请确保符合适用于 HoloLens 的 Windows Autopilot 的要求。
1. 注册适用于 HoloLens 2 计划的 Windows Autopilot。
1. 验证租户是否已启用 （已注册参加计划）。
1. 在 Windows Autopilot 注册设备。
1. 创建设备组。
1. 创建部署配置文件。
1. 验证 ESP 配置。
1. 配置 HoloLens 设备的自定义配置文件（已知问题）。
1. 验证 HoloLens 设备的配置文件状态。

### 1. 请确保符合适用于 HoloLens 的 Windows Autopilot 的要求
有关如何参与计划的最新信息，请参阅 [Windows 预览体验成员发行说明](hololens-insider.md#windows-insider-release-notes)。

参阅 Windows Autopilot 要求文章的以下部分：

- [网络要求](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements)  
- [许可要求](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#licensing-requirements)  
- [配置需求](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#configuration-requirements)
> [!IMPORTANT]  
> 与其他 Windows Autopilot 计划不同，适用于 HoloLens 2 的 Windows Autopilot 需要特定的操作系统要求。

查看 Windows Autopilo 自部署模式文章的“[要求](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying#requirements)”部分。 环境必须满足这些要求以及 Windows Autopilot 标准要求。

> [!NOTE]  
> 无需查看本文的“分步操作”和“验证”部分。 本文后面的过程提供了特定于 HoloLens 的相应步骤。

> [!IMPORTANT]  
> 有关如何注册设备和配置配置文件的信息，请参见本文中的[ 4. 在 Windows Autopilot 中注册设备](#4-register-devices-in-windows-autopilot)和[6. 创建部署配置文件](#6-create-a-deployment-profile)。 这些部分提供了适用于 HoloLens 的特殊步骤。

启动 OOBE 和预配过程之前，请确保 HoloLens 设备符合以下要求：

- 设备尚不是 Azure AD 的成员，并且未在 Intune （或其他 MDM 系统）中注册。 Autopilot 自部署过程完成这些步骤。 若要确保清理所有设备相关信息，请检查 Azure AD 和 Intune 中的“**设备**”页面。
- 每台设备都可以连接到 Internet。 可以使用“USB C到以太网”适配器进行有线 Internet 连接，也可以使用“USB C 到 Wifi”适配器进行无线 Internet 连接。 
- 每台设备都可以使用 USB-C 电缆连接到计算机，并且计算机已安装“[高级恢复助手（ARC）](https://www.microsoft.com/p/advanced-recovery-companion/9p74z35sfrs8?rtc=1&activetab=pivot:overviewtab)”
- 每台都有最新 Windows 更新： Windows 10 版本 19041.1002.200107-0909 或更高版本。

若要配置和管理 Autopilot 自部署模式配置文件，请确保你有权访问[Microsoft 终结点管理器管理中心](https://endpoint.microsoft.com)。

### 2. 注册“适用于 HoloLens 2 的 Windows Autopilot”计划

若要参与该计划，必须使用已为 HoloLens 启用的租户。 若要执行此操作，请转到 [适用于 HoloLens 专用预览版的 Windows Autopilot](https://aka.ms/APHoloLensTAP) 或使用以下 QR 码提交请求。  

![Autopilot QR 码](./images/hololens-ap-qrcode.png)  

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
  你将看到包括 **HoloLens**的列表。 如果不存在此选项，请使用[反馈](#feedback)选项之一与我们联系。

### 4. 在 Windows Autopilot 注册设备

若要在 Windows Autopilot 计划中注册 HoloLens 设备，必须获取设备的硬件哈希（也称为硬件ID）。 设备可以在 OOBE 过程中，或者稍后当设备所有者启动诊断日志收集过程（在以下过程中描述）时，将其硬件哈希记录在 CSV 文件中。 通常情况下，设备所有者是第一个登录到设备的用户。

**检索设备硬件哈希**

1. 启动 HoloLens 2 设备。
1. 在设备上，同时按“电源”和“音量”按钮，然后松开。 设备收集诊断日志和硬件哈希，并将它们存储在一组 .zip 文件中。
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

HoloLens 用户可以按照以下步骤预配 HoloLens 设备。  

1. 使用 USB-C 电缆将 HoloLens 设备连接到已安装 Advanced Recovery 助手（ARC）并已下载合适 Windows 更新的计算机。
1. 使用 ARC 将适当版本的 Windows 刷写到设备上。
1. 将设备连接到网络，然后重新启动设备。  
   > [!IMPORTANT]  
   > 开始全新体验（OOBE）前，必须将设备连接到网络。 设备在第一个OOBE屏幕上确定是否将其配置为 Autopilot 设备。 如果设备无法连接到网络，或者选择不将其配置为 Autopilot 设备，则以后无法更改为 Autopilot 配置。 相反，必须启动此过程，以便将设备设置为 Autopilot 设备。

   设备应自动启动 OOBE。 不要与 OOBE 交互。 放松一下！ 让 HoloLens 2 检测网络连接并允许自动完成 OOBE。 设备可能会在 OOBE 过程中重启。 OOBE 屏幕应类似于以下内容。
   
   ![OOBE 步骤 1](./images/hololens-ap-uex-1.png)
   ![OOBE 步骤 2](./images/hololens-ap-uex-2.png)
   ![OOBE 步骤 3](./images/hololens-ap-uex-3.png)
   ![OOBE 步骤 4](./images/hololens-ap-uex-4.png)

OOBE 结束时，可以使用用户名和密码登录到设备。

  ![OOBE 步骤 5](./images/hololens-ap-uex-5.png)

## 已知问题

- 无法安装使用设备安全上下文的应用程序。

## 反馈

若要提供反馈或报告问题，请使用以下方法之一：

- 使用反馈中心应用。 可以在已连接 HoloLens 的计算机上找到此应用。 在反馈中心中，选择“**企业管理**” > “**设备**”类别。  

  提供反馈或报告问题时，请提供详细说明。 如果适用，则包括屏幕截图和日志。
- 向 [hlappreview@microsoft.com](mailto:hlappreview@microsoft.com)发送电子邮件。 在“电子邮件主题”中，输入**\<*Tenant*>适用于 HoloLens 2 的 Autopilot 评估反馈**（其中 \<*Tenant*> 是 Intune 租户的名称）。

  在邮件中提供详细说明。 但是，除非支持人员特别要求，否则请勿包括屏幕截图或日志之类的数据。 此类数据可能包括私人或个人身份信息（PII）。
