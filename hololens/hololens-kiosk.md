---
title: 将 HoloLens 设置为 Kiosk
description: 了解如何设置和使用展台配置来锁定 HoloLens 设备上的应用。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 10/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: 245de50fcaaf1235cce02cd1b6cae921b64f2851
ms.sourcegitcommit: d20057957aa05c025c9838119cc29264bc57b4bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "11283983"
---
# 将 HoloLens 设置为 Kiosk

你可以将 HoloLens 设备配置为在展台模式下运行，以用作固定用途的设备**（也称为展台）。 展台模式限制 (或) 设备上可用的应用程序。 展台模式是一项便捷功能，可用于将 HoloLens 设备专用于业务应用，或在应用演示中使用 HoloLens 设备。

本文提供有关特定于 HoloLens 设备的展台配置的各个方面的信息。 有关不同类型的基于 Windows 的展台以及如何配置这些展台的常规信息，请参阅在 Windows 桌面版上配置展台和 [数字签名](https://docs.microsoft.com/windows/configuration/kiosk-methods)。  

> [!IMPORTANT]  
> 展台模式确定当用户登录设备时可用的应用。 但是，展台模式不是一种安全方法。 它不会阻止"允许"应用打开不允许的另一个应用。 若要阻止应用或进程打开，请使用 [WDAC](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) Windows Defender应用程序 (CSP) 创建适当的策略。
>
> 了解有关为用户提供 HoloLens 2 使用的高级安全级别的 Microsoft 服务，详细了解状态分离和隔离 [- Defender 保护](security-state-separation-isolation.md#defender-protections)。 或者了解如何使用 WDAC 和 Windows PowerShell Microsoft Intune 在 [HoloLens 2 设备上允许或阻止应用](https://docs.microsoft.com/mem/intune/configuration/custom-profile-hololens)。

可以在单应用或多应用配置中使用展台模式，并且可以使用三个进程之一来设置和部署展台配置。

> [!IMPORTANT]  
> 删除多应用配置会删除分配的访问权限功能创建的用户锁定配置文件。 但是，它不会还原所有策略更改。 若要还原这些策略，你必须将设备重置为出厂设置。

## 规划展台部署

规划展台时，你需要能够回答以下问题。 下面是阅读此页面时要考虑的一些决策以及这些问题的一些注意事项。
1. **谁将使用你的展台，以及他们将 [ () 的帐户类型 ](hololens-identity.md) ？** 这是你可能已做出的决定，不应为了展台而进行调整，但会影响稍后如何分配展台。
1. **是否需要为每个用户/组启用不同的展台，或者没有为某些用户/组启用展台？** 如果是这样，你将希望通过 XML 创建展台。 
1. **展台中有多少应用？** 如果你有多个应用，则需要多应用展台。 
1. **展 (将) 哪个应用？** 请使用下面的 AUMID 列表添加除你自己的In-Box应用。
1. **如何计划部署展台？** 如果你在 MDM 中注册设备，我们建议使用 MDM 部署你的展台。 如果未使用 MDM，则提供具有预配包的部署。  

### 展台模式要求

你可以配置任何 HoloLens 2 设备以使用展台模式。

> [!IMPORTANT]
> 展台模式仅在设备具有 Windows Holographic for Business 时可用。 所有 HoloLens 2 设备都随 Windows Holographic for Business 一起提供，没有其他版本。 每个 HoloLens 2 设备都能开箱即用运行展台模式。
>
> HoloLens (第一代) 需要在操作系统版本和操作系统版本方面进行升级。 下面是有关将 HoloLens 第一代 (更新) [Windows Holographic for Business](hololens1-upgrade-enterprise.md) 版本的信息。 若要将 HoloLens (第一代) 设备更新为使用展台模式，必须先确保设备运行 Windows 10 版本 1803 或更高版本。 如果你已使用 Windows 设备恢复工具将 HoloLens (第一代) 设备恢复到其默认版本，或者如果你已安装了最新更新，则设备已准备好进行配置。

> [!IMPORTANT]  
> 若要帮助保护在展台模式下运行的设备，请考虑添加关闭 USB 连接等功能的设备管理策略。 此外，请检查更新圈设置以确保在工作时间不会发生自动更新。

### 在单应用展台或多应用展台之间做出决定

当用户登录设备时，单应用展台将启动指定的应用。 "开始"菜单被禁用，就像 Cortana 一样。 HoloLens 2 设备不响应"开始 ["手势](hololens2-basic-usage.md#start-gesture) 。 HoloLens (第一代) 设备不响应"放 [红"](hololens1-basic-usage.md) 手势。 因为只有一个应用可以运行，所以用户不能放置其他应用。

当用户登录设备时，多应用展台将显示"开始"菜单。 展台配置确定哪些应用在"开始"菜单上可用。 可以使用多应用展台为用户提供易于理解的体验，只需向用户呈现他们必须使用的事情，并删除他们不需要使用的事情。

下表列出了不同展台模式中的功能。

| &nbsp; |“开始”菜单 |快速操作菜单 |相机和视频 |Miracast |Cortana |内置语音命令 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|单应用展台 |已禁用 |已禁用   |已禁用 |已禁用   |已禁用 |已启用 <sup> 1</sup> |
|多应用展台。 |启用 |已启用 <sup> 2</sup> |可用 <sup> 2</sup> |可用 <sup> 2</sup> |可用 <sup> 2、3</sup>  |已启用 <sup> 1</sup> |

> <sup>1 </sup> 与已禁用功能相关的语音命令无法正常工作。  
> <sup>2 </sup> 若要详细了解如何配置这些功能，请参阅["选择展台应用"。](#plan-kiosk-apps)  
> <sup>3 </sup> 即使禁用 Cortana，内置语音命令也处于启用状态。

下表列出了不同展台模式的用户支持功能。

| &nbsp; |支持的用户类型 | 自动登录 | 多个访问级别 |
| --- | --- | --- | --- |
|单应用展台 |Azure Active Directory (Azure) 或本地帐户 (托管服务) MSA 帐户 |是 |否 |
|多应用展台。 |Azure AD 帐户 |否 |是 |

有关如何使用这些功能的示例，请参阅下表。

|将单应用展台用于： |将多应用展台用于： |
| --- | --- |
|仅为新员工运行 Dynamics 365 指南的设备。 |为一系列员工运行指南和远程协助的设备。 |
|仅运行自定义应用的设备。 |作为大多数用户的展台的设备 (运行自定义应用) ，但用作特定组用户的标准设备。 |

### 规划展台应用

有关如何选择展台应用的常规信息，请参阅有关在展台模式下选择分配的访问权限的应用 ([指南) 。 ](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)

如果使用 Windows Device Portal 配置单应用展台，请在安装过程中选择该应用。  

如果使用移动设备管理 (MDM) 系统或预配包配置展台模式，请使用 [AssignedAccess ](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 配置服务提供程序 (CSP) 来指定应用程序。 CSP 使用 [应用程序用户模型 ID (AUMID) ](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 标识应用程序。 下表列出了可在多应用展台中使用的一些 In-box 应用程序的 AUMID。

> [!IMPORTANT]
> 展台模式确定当用户登录设备时可用的应用。 但是，展台模式不是一种安全方法。 它不会阻止"允许"应用打开不允许的另一个应用。 因为我们不限制此行为，所以应用仍可从 Edge、文件资源管理器和 Microsoft Store 应用启动。 如果不希望从展台启动特定应用，请使用 [WDAC](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) Windows Defender CSP 中的 (应用程序) 策略。 
> 
> 此外，混合现实主页无法设置为网亭应用。

<a id="aumids"></a>

|应用名称 |AUMID |
| --- | --- |
|3D 查看器 |Microsoft.Microsoft3DViewer\_8wekyb3d8bbwe\！Microsoft.Microsoft3DViewer |
|日历 |microsoft.windowscommunicationsapps\_8wekyb3d8bbwe\！microsoft.windowslive.calendar |
|相机 <sup> 1、2</sup> |HoloCamera\_cw5n1h2txyewy\！HoloCamera |
|Cortana <sup> 3</sup> |Microsoft.549981C3F5F10\_8wekyb3d8bbwe\！应用 |
|HoloLens 上的设备选取器 (第一代)  |HoloDevicesFlow\_cw5n1h2txyewy\！HoloDevicesFlow |
|HoloLens 2 上的设备选取器 |Microsoft.Windows.DevicesFlowHost\_cw5n1h2txyewy\！Microsoft.Windows.DevicesFlowHost |
|Dynamics 365 Guides |Microsoft.Dynamics365.Guides\_8wekyb3d8bbwe\！MicrosoftGuides |
|Dynamics 365 Remote Assist |Microsoft.MicrosoftRemoteAssist\_8wekyb3d8bbwe\！Microsoft.RemoteAssist |
|反馈 &nbsp; 中心 |Microsoft.WindowsFeedbackHub\_8wekyb3d8bbwe\！应用 |
|文件资源管理器 |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe！microsoft.windowslive.mail |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|电影和电视 |Microsoft.ZuneVideo\_8wekyb3d8bbwe\！Microsoft.ZuneVideo |
|OneDrive |microsoft.microsoftskydrive\_8wekyb3d8bbwe\！应用 |
|照片 |Microsoft.Windows.Photos\_8wekyb3d8bbwe\！应用 |
|“设置” |HolographicSystemSettings\_cw5n1h2txyewy\！应用 |
|提示 |Microsoft.HoloLensTips\_8wekyb3d8bbwe\！HoloLensTips |

> <sup>1 </sup> 若要启用照片或视频捕获，必须启用相机应用作为展台应用。  
> <sup>2 </sup> 启用相机应用时，请注意以下条件：
> - "快速操作"菜单包括"照片和视频"按钮。  
> - 你还应启用可与图片 (或检索图片) 例如照片、邮件或 OneDrive 应用。  
>  
> <sup>3 </sup> 即使你未启用 Cortana 作为网亭应用，内置语音命令也已启用。 但是，与已禁用功能相关的命令不起作用。  
> <sup>4 </sup> 不能直接启用 Miracast。 若要将 Miracast 启用为展台应用，请启用相机应用和设备选取器应用。

### 为用户或组规划展台配置文件

创建 xml 文件或使用 Intune 的 UI 设置展台时，需要考虑谁将成为展台的用户。 展台配置可以限制为单个帐户或 Azure AD 组。 

通常为用户或用户组启用展台。 但是，如果你计划编写自己的 XML 展台，则你可能要考虑全局分配的访问权限，其中展台在设备级别应用，而不考虑标识。 如果吸引你阅读 [有关全局分配的访问权限展台的更多信息。](hololens-global-assigned-access-kiosk.md)

#### 如果要创建 XML 文件：
-   许多用户创建多个展台配置文件，并将每个配置文件分配给不同的用户/组。 例如，Azure AD 组的展台（具有多个应用）和具有多个应用展台且应用单数的访问者。
-   展台配置将被称为配置文件 **ID，** 并且具有 GUID。
-   通过指定用户类型并将相同的 GUID 用于 **DefaultProfile Id，** 你将在"配置"部分分配该配置文件。
- XML 文件可以通过 MDM 创建但仍应用于设备，方法为创建自定义 OMA URI 设备配置文件，然后使用 URI 值将其应用到 HoloLens 设备组：./Device/Vendor/MSFT/AssignedAccess/Configuration

#### 如果你在 Intune 中创建展台。
-   每台设备只能接收一个展台配置文件，否则将产生冲突，并没有任何展台配置。 
    -   其他类型的配置文件和策略（如与展台配置文件不相关的设备限制）不会与展台配置文件冲突。
-   将为属于用户登录类型的所有用户启用展台，这将使用用户或 Azure AD 组进行设置。 
-   在设置展台配置和用户登录 **类型 (** 用户可以登录到展台) 并且选择了应用后，仍必须将设备配置分配给组。 已分配 (组) 确定哪些设备接收网亭设备配置，但是，如果展台已启用，则不与之交互。 
    - 有关在 Intune 中分配配置文件的效果的完全讨论，请参阅在 [Microsoft Intune 中分配用户和设备配置文件](https://docs.microsoft.com/intune/configuration/device-profile-assign)。

### 选择部署方法

可以选择以下方法之一来部署展台配置：

- [Microsoft Intune 或其他移动设备管理 (MDM) 服务](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [设置包](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > 由于此方法要求在设备上启用开发人员模式，因此我们建议你仅将它用于演示。

下表列出了每个部署方法的功能和优点。

| &nbsp; |使用 Windows Device Portal 部署 |使用预配包进行部署 |使用 MDM 部署 |
| --------------------------- | ------------- | -------------------- | ---- |
|部署单应用展台   | 是           | 是                  | 是  |
|部署多应用展台    | 否            | 是                  | 是  |
|仅部署到本地设备 | 是           | 是                  | 否   |
|使用开发人员模式部署 |必需       | 不需要            | 不需要   |
|使用 Azure Active Directory (Azure AD)   | 不需要            | 不需要                   | 必需  |
|自动部署      | 否            | 否                   | 是  |
|部署速度            | 迅速       | 迅速                 | 慢速 |
|大规模部署 | 不建议    | 推荐        | 推荐 |

## 使用 Microsoft Intune 或其他 MDM 设置单应用或多应用展台

若要使用 Microsoft Intune 或其他 MDM 系统设置展台模式，请按照以下步骤操作。

1. [准备注册设备](#mdmenroll)。
1. [创建展台配置文件](#mdmprofile)。
1. 配置展台。
   - [配置单应用展台的设置](#mdmconfigsingle)。
   - [配置多应用展台的设置](#mdmconfigmulti)。
1. [将展台配置文件分配给组](#mdmassign)。
1. 部署设备。
   - [部署单应用展台](#mdmsingledeploy)。
   - [部署多应用展台](#mdmmultideploy)。

### <a id="mdmenroll"></a>MDM，步骤 1 &ndash; 准备注册设备

你可以将 MDM 系统配置为在用户首次登录时自动注册 HoloLens 设备，或让用户手动注册设备。 设备还必须加入 Azure AD 域，并分配到相应的组。

若要详细了解如何注册设备，请参阅在 MDM 和[Windows 设备的 Intune](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)注册方法中注册[HoloLens。](hololens-enroll-mdm.md)

### <a id="mdmprofile"></a>MDM，步骤 2 &ndash; 创建展台配置文件

1. 打开 [Azure](https://portal.azure.com/) 门户并登录到 Intune 管理员帐户。
1. 选择**Microsoft Intune**  >  **设备配置 - 配置文件**  >  **创建配置文件**。
1. 输入配置文件名称。
1. 选择**平台**  >  **Windows 10 和更高版本**，然后选择**配置文件类型**  > **设备限制**。
1. 选择 **"**  >  配置**展**台"，然后选择下列选项之一：
   - 若要创建单应用展台，请选择**展台模式**  >  **单应用展台**。
   - 若要创建多应用展台，请选择**展台模式**  >  **多应用展台**。
1. 若要开始配置展台，请选择"添加 **"。**

你的下一步将有所不同，具体取决于你需要的展台类型。 有关详细信息，请选择下列选项之一：  

- [单应用展台](#mdmconfigsingle)
- [多应用展台。](#mdmconfigmulti)

若要详细了解如何创建展台配置文件，请参阅 [Windows 10](https://docs.microsoft.com/intune/configuration/kiosk-settings)和 Windows Holographic for Business 设备设置，以使用 Intune 作为专用展台运行。

### <a id="mdmconfigsingle"></a>MDM，步骤 3 (单应用) &ndash;  配置单应用展台的设置

本部分总结了单个应用展台所需的设置。 有关详细信息，请参阅以下文章：

- 若要了解如何在 Intune 中配置展台配置文件，请参阅如何使用 [Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)配置展台模式。
- 有关 Intune 中单应用展台的可用设置详细信息，请参阅 [单个全屏应用展台](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- 对于其他 MDM 服务，请参阅提供商文档中的说明。 如果你必须使用自定义 XML 配置在 MDM 服务中设置展台，请创建一个定义展台配置的 [XML 文件](#ppkioskconfig)。

1. 选择"用户**登录**类型本地用户帐户"，然后输入可登录展台的本地 (设备) 帐户或 Microsoft 帐户  >  **** (MSA) 的用户名。
   > [!NOTE]  
   > **Windows Holographic** for Business 不支持自动登录用户帐户类型。
1. 选择 **"应用程序类型**  >  **应用商店"应用**，然后从列表中选择应用。

下一步是 [将配置文件](#mdmassign) 分配给组。

### <a id="mdmconfigmulti"></a>MDM，步骤 3 (多应用) &ndash; 配置多应用展台的设置

本部分总结了多应用展台所需的设置。 有关更多详细信息，请参阅以下文章：

- 若要了解如何在 Intune 中配置展台配置文件，请参阅如何使用 [Microsoft Intune](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)配置展台模式。
- 有关 Intune 中多应用展台的可用设置详细信息，请参阅 [多应用展台](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- 对于其他 MDM 服务，请参阅提供商文档中的说明。 如果你需要使用自定义 XML 配置在 MDM 服务中设置展台，请创建 [一个定义](#ppkioskconfig)展台配置的 XML 文件。 如果使用 XML 文件，请确保包含"开始 ["屏幕布局](#start-layout-for-hololens)。  
- 可以选择将自定义"开始"屏幕布局与 Intune 或其他 MDM 服务一同使用。 有关详细信息，请参阅[Mdm 的"开始"屏幕布局文件 (Intune 和其他) 。 ](#start-layout-file-for-mdm-intune-and-others)

1. 选择 **"S 模式设备否"中的目标 Windows 10。**  >  ****  
   >[!NOTE]  
   > Windows Holographic for Business 不支持 S 模式。
1. 选择**用户登录类型**  >  **Azure AD 用户或组**或**用户登录类型**  >  **HoloLens 访问者**，然后添加一个或多个用户组或帐户。  

   只有属于你在用户登录类型中指定的组或帐户的用户才能**** 使用展台体验。

1. 使用下列选项选择一个或多个应用：
   - 若要添加已上载的业务线应用，请选择"添加 **应用商店** 应用"，然后选择需要的应用。
   - 若要通过指定应用 AUMID 添加应用，请选择"按 **AUMID** 添加"，然后输入应用的 AUMID。 [请参阅可用 AUMID 的列表](#aumids)

下一步是 [将配置文件](#mdmassign) 分配给组。

### <a id="mdmassign"></a>MDM，步骤 4 &ndash; 将展台配置文件分配给组

使用 **展** 台配置文件的"分配"页面设置希望展台配置部署在何处。 在最简单的情况下，你将展台配置文件分配给设备在 MDM 中注册时将包含 HoloLens 设备的组。

### <a id="mdmsingledeploy"></a>MDM，步骤 5 (单应用) &ndash; 部署单应用展台

使用 MDM 系统时，可以在 OOBE 期间在 MDM 中注册设备。 OOBE 完成后，轻松登录设备。

在 OOBE 期间，请按照以下步骤操作：

1. 使用你在展台配置文件中指定的帐户登录。
1. 注册设备。 确保设备已添加到展台配置文件分配到的组中。
1. 等待 OOBE 完成、应用商店应用下载和安装以及应用策略。 然后重新启动设备。

下次登录设备时，展台应用应自动启动。

如果此时看不到展台配置， [请检查分配状态](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。

### <a id="mdmmultideploy"></a>MDM，步骤 5 (部署多应用) &ndash; 部署多应用展台

使用 MDM 系统时，可以在 OOBE 期间将设备加入 Azure AD 租户，并注册 MDM 中的设备。 如果适用，向用户提供注册信息，以便他们可以在 OOBE 过程中使用注册信息。

> [!NOTE]  
> 如果已将展台配置文件分配给包含用户的组，请确保其中一个用户帐户是登录到设备的第一个帐户。

在 OOBE 期间，请按照以下步骤操作：

1. 使用属于用户登录类型 **组的帐户登录** 。
1. 注册设备。
1. 等待作为展台配置文件一部分的任何应用下载和安装。 此外，请等待应用策略。  
1. OOBE 完成后，你可以从 Microsoft Store 安装其他应用或旁加载。 [设备](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app) 所属的组所需的应用将自动安装。
1. 安装完成后，重新启动设备。

下次使用属于用户登录类型的帐户登录设备时，展台应用应自动启动****。

如果此时看不到展台配置， [请检查分配状态](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。

## 使用预配包设置单应用或多应用展台

若要使用预配包设置展台模式，请按照以下步骤操作。

1. [创建定义展台配置的 XML 文件](#ppkioskconfig)。，包括"开始 ["屏幕布局](#start-layout-for-hololens)。
2. [将 XML 文件添加到预配包。](#ppconfigadd)
3. [将预配包应用到 HoloLens。](#ppapply)

### <a id="ppkioskconfig"></a>预配包，步骤 1 &ndash; 创建展台配置 XML 文件

按照 [一般说明创建适用于 Windows 桌面的展台配置 XML](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)文件，以下各项除外：

- 请勿将经典 Windows 应用程序 (Win32) 。 HoloLens 不支持这些应用程序。
- 将 [占位符"开始"屏幕布局 XML](#start-layout-for-hololens) 用于 HoloLens。
- 可选：向展台配置添加来宾访问

#### <a id="ppkioskguest"></a>可选：向展台配置添加来宾访问

在 XML 文件的[**"**](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs)配置"部分，可以配置一个名为 **"** 访问者"的特殊组，以允许来宾使用展台。 当展台配置为支持**访问者特殊组**时，"来宾"选项将**** 添加到登录页面。 **来宾**帐户不需要密码，当帐户退出时，与该帐户关联的任何数据都将被删除。

若要启用 **来宾帐户** ，请向展台配置 XML 添加以下代码段：

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a>HoloLens 的占位符"开始"屏幕布局

如果使用 [预配包配置](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 多应用展台，此过程需要"开始"屏幕布局。 Windows Holographic for Business 不支持"开始"屏幕布局自定义。 因此，你必须使用占位符"开始"屏幕布局。

> [!NOTE]  
> 由于单应用展台在用户登录时启动展台应用，因此它不使用"开始"菜单，也无需具有"开始"屏幕布局。

> [!NOTE]  
> 如果使用 [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 设置多应用展台，可以选择使用"开始"屏幕布局。 有关详细信息，请参阅 Mdm 的占位符"开始"屏幕布局 ([Intune 和其他) 。 ](#start-layout-file-for-mdm-intune-and-others)

对于"开始"屏幕布局，将 **以下 StartLayout** 部分添加到展台预配 XML 文件：

```xml
<!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
            <StartLayout>
                <![CDATA[<LayoutModificationTemplate xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout" Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
                      <LayoutOptions StartTileGroupCellWidth="6" />
                      <DefaultLayoutOverride>
                        <StartLayoutCollection>
                          <defaultlayout:StartLayout GroupCellWidth="6">
                            <start:Group Name="">
                              <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
                            </start:Group>
                          </defaultlayout:StartLayout>
                        </StartLayoutCollection>
                      </DefaultLayoutOverride>
                    </LayoutModificationTemplate>
                ]]>
            </StartLayout>
            <!-- This section is required for parity with Desktop Assigned Access. It is not currently used on HoloLens -->
```

#### <a id="start-layout-file-for-mdm-intune-and-others"></a>适用于 Intune 和其他托管 (MDM 的占位符"开始"屏幕布局) 

将以下示例另存为 XML 文件。 在 Microsoft Intune 应用中配置多应用展台时 (或在提供展台配置文件服务的另一个 MDM 服务中配置) 。

> [!NOTE]
> 如果你必须使用自定义设置和完整的 XML 配置在 MDM 服务中设置展台，请使用预配包的"开始" [屏幕布局说明](#start-layout-for-hololens)。

```xml
<LayoutModificationTemplate
    xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification"
    xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout"
    xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout"
    Version="1">
  <RequiredStartGroupsCollection>
    <RequiredStartGroups>
      <AppendGroup Name="">
        <start:Tile Size="2x2" Column="0" Row="0" AppUserModelID="placeholderpackagename_kzf8qxf38zg5c!App" />
      </AppendGroup>
    </RequiredStartGroups>
  </RequiredStartGroupsCollection>
 </LayoutModificationTemplate>
```

### <a id="ppconfigadd"></a>Prov. 包，步骤 2 &ndash; 将展台配置 XML 文件添加到预配包

1. 打开 [Windows 配置设计器](https://www.microsoft.com/store/apps/9nblggh4tx22)。
1. 选择 **"高级预配"，** 输入项目名称，然后选择"下一**步"。**
1. 选择**Windows 10 全息版**，然后选择"下**一步"。**
1. 选择 **"完成"。** 此时将打开你的程序包的工作区。
1. 选择**运行时设置**  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**。
1. 在中央窗格中，选择 **"浏览** "以查找并选择你创建的展台配置 XML 文件。

   ![Windows 配置设计器中的 MultiAppAssignedAccessSettings 字段的屏幕截图](./images/multiappassignedaccesssettings.png)

1. **可选**。  (如果你想要在设备的初始设置后应用预配包，并且展台设备上已有管理员用户，请跳过此步骤。) **选择运行时**设置帐户用户，然后创建用户帐户。 &gt; **** &gt; **** 提供用户名和密码，然后选择 **"用户组**  >  **管理员"。**  
  
     通过使用此帐户，可以查看设置状态和日志。  
1. **可选**。  (如果展台设备上已有非管理员帐户，请跳过此步骤。) **选择运行时**设置帐户用户，然后创建本地 &gt; **** &gt; **** 用户帐户。 确保用户名与在配置 XML 中指定的帐户相同。 选择**UserGroup**  >  **标准用户**。
1. 选择 **"文件**  >  **保存"。**
1. 选择 **"**  >  **导出预配包**"，然后选择"**所有者**  >  **IT 管理员"。** 这设置此预配包的优先级高于从其他源应用到此设备的预配包。
1. 选择**下一步** 。
1. 在 **"预配包安全** "页上，选择一个安全选项。
   > [!IMPORTANT]  
   > 如果选择" **启用程序包签名**"，则还必须选择用于对程序包进行签名的有效证书。 为此，请选择" **浏览** "，然后选择要用于对程序包进行签名的证书。
   
   > [!CAUTION]  
   > 不要选择 **"启用程序包加密"。** 在 HoloLens 设备上，此设置会导致预配失败。
1. 选择**下一步** 。
1. 指定您希望预配包在生成时转到的输出位置。 默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。 如果要更改输出位置，请选择"浏览 **"。** 完成后，选择"下一**步"。**
1. 选择 **"** 生成"开始生成程序包。 无需花费太长时间即可生成预配包。 生成页显示项目信息，进度栏指示生成状态。

### <a id="ppapply"></a>预配包，步骤 3 &ndash; 将预配包应用到 HoloLens

"使用预配包配置 HoloLens"一文提供了在下列情况下应用预配包的详细说明：

- 你可以最初[在设置期间将预配包应用到 HoloLens。](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)

- 设置后[，还可以将预配包应用到 HoloLens。](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)

## 使用 Windows Device Portal 设置单应用展台

若要使用 Windows Device Portal 设置展台模式，请按照以下步骤操作。

1. [将 HoloLens 设备设置为使用 Windows Device Portal。](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal) Device Portal 是 HoloLens 上的 Web 服务器，你可以从电脑上的 Web 浏览器连接到它。

    > [!CAUTION]
    > 将 HoloLens 设置为使用 Device Portal 时，你必须在设备上启用开发人员模式。 通过具有 Windows Holographic for Business 的设备的开发人员模式，你可以旁加载应用。 但是，此设置会面临用户安装尚未通过 Microsoft Store 认证的应用的风险。 管理员可以使用策略 CSP 中的**ApplicationManagement/AllowDeveloper Unlock**设置阻止启用开发人员[模式。](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) [了解有关开发人员模式的详细信息。](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. 在计算机上，使用 [WLAN](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 或 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)连接到 HoloLens。

1. 执行下列操作之一：
   - 如果是首次连接到 Windows Device Portal，请 [创建用户名和密码](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - 输入您之前设置的用户名和密码。

    > [!TIP]
    > 如果发现浏览器中的证书错误，请遵循[以下疑难解答步骤](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)。

1. 在 Windows Device Portal 中，选择 **展台模式**。

1. 选择 **"启用展台模式**"，选择要在设备启动时运行的应用，然后选择"保存 **"。**

    ![展台模式](images/kiosk.png)
1. 重新启动 HoloLens。 如果你仍然打开 Device Portal 页面，可以选择 **页面顶部的"** 重启"。

> [!NOTE]
> Kiosk Mode can be set via Device Portal's REST API by doing a POST to /api/holographic/kioskmode/settings with one required query string parameter ("kioskModeEnabled" with a value of "true" or "false") and one optional parameter ("startupApp" with a value of a package name) . 请记住，Device Portal 仅面向开发人员，不应在非开发人员设备上启用。 REST API 在将来的更新/版本中可能会更改。

## 详细信息

### 了解如何使用预配包配置展台。  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### 全局分配的访问权限 – 展台模式
- 通过启用在系统级别应用展台模式的新展台方法，减少展台的标识管理。

此新功能允许 IT 管理员为适用于系统级别的多个应用展台模式配置 HoloLens 2 设备，此模式与系统上的任何标识没有任何关联，并且适用于登录设备的每个人。 有关此新功能的更多详细信息，请参阅 [HoloLens](hololens-global-assigned-access-kiosk.md) 全局分配的访问权限展台文档。

### 在多应用展台模式下自动启动应用程序 
- 自动应用启动的集中体验，进一步增加了为展台模式体验选择的 UI 和应用选择。

仅适用于多应用展台模式，并且只能使用分配的访问权限配置中的以下突出显示属性将 1 个应用指定为自动启动。 

当用户登录时，应用程序将自动启动。 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### 用于处理故障的展台模式行为更改
- 通过消除展台模式故障上的可用应用，实现更安全的展台模式。 

在应用展台模式失败之前，HoloLens 用于在"开始"菜单中显示所有应用程序。 现在，在 Windows 全息版 20H2 中，如果发生故障，不会在"开始"菜单中显示应用，如下所示： 

![展台模式在出现故障时的外观的图像。](images/hololens-kiosk-failure-behavior.png )

### 为脱机展台缓存 Azure AD 组成员身份
- 启用的脱机展台，可与 Azure AD 组一起使用，最多 60 天。

此策略控制允许 Azure AD 组成员身份缓存用于面向已登录用户的 Azure AD 组的分配的访问权限配置天数。 一旦此策略值设置为大于 0 的值，则否则使用缓存。  

名称：AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最小值 - 0 天  
最大值 - 60 天 

正确使用此策略的步骤： 
1. 创建面向 Azure AD 组的展台的设备配置文件，并将其分配给 HoloLens () 。 
1. 创建基于 OMA URI 的自定义设备配置，该配置将此策略值设置为所需的天数 (> 0) 并将其分配给 HoloLens () 。 
    1. URI 值应在 OMA-URI 文本框中输入为 ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. 该值可以介于允许的最小值/最大值之间。
1. 注册 HoloLens 设备并验证这两种配置是否适用于该设备。 
1. 在 Internet 可用时允许 Azure AD 用户 1 登录，一旦成功确认用户登录和 Azure AD 组成员身份，将创建缓存。 
1. 现在，Azure AD 用户 1 可以将 HoloLens 脱机并用于展台模式，只要策略值允许 X 天数。 
1. 对于任何其他 Azure AD 用户 N，可以重复步骤 4 和 5。此处的关键点是，任何 Azure AD 用户都必须使用 Internet 登录设备，以便我们可以至少一次确定他们是展台配置面向的 Azure AD 组的成员。 
 
> [!NOTE]
> 在针对 Azure AD 用户执行步骤 4 之前，用户将遇到"断开连接"环境中提及的失败行为。 


## 适用于 HoloLens 的 XML 展台代码示例

### 面向 Azure AD 组的多个应用展台模式。 
此展台为 Azure AD 组的用户部署一个展台，他们将启用一个展台，其中包括 3 个应用：设置、远程协助和反馈中心。 若要修改此示例以立即使用，请确保更改下面突出显示的 GUID，以匹配你自己的 Azure AD 组。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### 面向 Azure AD 帐户的多个应用展台模式。
此展台为单个用户部署展台，他们将启用包括 3 个应用的展台：设置、远程协助和反馈中心。 若要修改此示例以立即使用，请确保更改下面突出显示的帐户，以匹配你自己的 Azure AD 帐户。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

