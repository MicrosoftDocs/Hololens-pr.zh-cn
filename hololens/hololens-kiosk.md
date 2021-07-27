---
title: 将 HoloLens 设置为网亭
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
ms.openlocfilehash: 25227184ec33b134215dbd1f42f7b920b26dc29c
ms.sourcegitcommit: 5130823947caffd2a444e9d8fb15cd24cbb6414c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2021
ms.locfileid: "114659584"
---
# <a name="set-up-hololens-as-a-kiosk"></a>将 HoloLens 设置为网亭

您可以通过将设备配置为在展台模式下运行，将 HoloLens 设备配置为一种固定用途的设备，也称为 *展台*。 展台模式限制设备上可用的应用程序 (或用户) 。 展台模式是一项方便的功能，可用于将 HoloLens 设备专用于企业应用，或在应用演示中使用 HoloLens 设备。

本文提供了有关特定于 HoloLens 设备的展台配置的各个方面的信息。 有关不同类型的基于 Windows 的网亭以及如何对其进行配置的常规信息，请参阅[在 Windows desktop 版本上配置网亭和数字签名](/windows/configuration/kiosk-methods)。  

> [!IMPORTANT]  
> 展台模式确定用户登录到设备时可用的应用。 但展台模式并不是一种安全方法。 它不会阻止 "允许" 的应用打开不允许的其他应用。 为了阻止应用或进程打开，请使用[Windows Defender 应用程序控件 (WDAC) CSP](/windows/client-management/mdm/applicationcontrol-csp)来创建相应的策略。
>
> 若要详细了解 Microsoft 服务向用户授予 HoloLens 2 使用的高级安全级别，请参阅有关[状态分离和隔离 Defender 保护](security-state-separation-isolation.md#defender-protections)的详细信息。 或了解如何[使用 WDAC 和 Windows PowerShell 通过 Microsoft Intune 允许或阻止 HoloLens 2 设备上的应用](/mem/intune/configuration/custom-profile-hololens)。

可以在单应用或多应用配置中使用展台模式，并且可以使用三个过程之一来设置和部署展台配置。

> [!IMPORTANT]  
> 删除多应用配置将删除已分配的访问功能创建的用户锁定配置文件。 但是，它不会还原所有策略更改。 若要还原这些策略，你必须将设备重置为出厂设置。

## <a name="plan-the-kiosk-deployment"></a>规划展台部署

规划展台时，需要能够回答以下问题。 下面是在阅读本页时要考虑的一些决定，还需要考虑这些问题。
1. **Who 将使用您的展台，并将使用哪 [种类型的帐户 ()](hololens-identity.md) ？** 这是你可能已做出的决定，不应为展台进行调整，但会影响稍后分配展台的方式。
1. **是否需要为每个用户/组使用不同的网亭，或者是否为某些展台启用了一个？** 如果是这样，则需要通过 XML 创建展台。 
1. **展台会有多少应用？** 如果有1个以上的应用，则需要一个多应用展台。 
1. **你的展台中 () 哪些应用？** 除了你自己的应用外，请使用下面的 AUMIDs 列表添加任何 In-Box 应用。
1. **你计划如何部署展台？** 如果要在 MDM 中注册设备，则建议使用 MDM 部署展台。 如果不使用 MDM，则可以使用预配包进行部署。  

### <a name="kiosk-mode-requirements"></a>展台模式要求

可以将任何 HoloLens 2 设备配置为使用展台模式。

> [!IMPORTANT]
> 展台模式仅在设备已 Windows Holographic for Business 的情况下可用。 所有 HoloLens 2 设备附带 Windows Holographic for Business，无其他版本。 每个 HoloLens 2 设备都可以运行展台模式。
>
> HoloLens (第一代) 设备需要在操作系统版本和操作系统版本中进行升级。 下面详细介绍了如何将 HoloLens (第一代) 更新到[Windows Holographic for Business](hololens1-upgrade-enterprise.md)版本。 若要将第一代) 设备 (的 HoloLens 更新为使用展台模式，你必须首先确保设备运行 Windows 10 版本1803或更高版本。 如果已使用 Windows 设备恢复工具将 HoloLens (第一代) 设备恢复到其默认版本，或者安装了最新的更新，则设备已准备好进行配置。

> [!IMPORTANT]  
> 若要帮助保护在展台模式下运行的设备，请考虑添加关闭 USB 连接等功能的设备管理策略。 此外，请检查更新圈设置，确保在工作时间内不会进行自动更新。

### <a name="decide-between-a-single-app-kiosk-or-a-multi-app-kiosk"></a>确定单应用展台还是多应用展台

当用户登录到设备时，单应用展台启动指定的应用。 已禁用 "开始"菜单，Cortana。 HoloLens 2 设备不响应[开始](hololens2-basic-usage.md#start-gesture)手势。  (第一代) 设备的 HoloLens 不会响应[布隆](hololens1-basic-usage.md)手势。 由于只有一个应用可以运行，因此用户无法放置其他应用。

多应用展台显示用户登录到设备时的 "开始"菜单。 展台配置确定 "开始"菜单上可用的应用。 你可以使用多应用展台为用户提供易于理解的体验，只需向他们展示他们必须使用的东西，并删除不需要使用的东西。

下表列出了不同展台模式下的功能。

| &nbsp; |“开始”菜单 |快速操作菜单 |照相机和视频 |Miracast |Cortana |内置语音命令 |
| --- | --- | --- | --- | --- | --- | --- | 
|单应用展台 |已禁用 |已禁用 |已禁用 |已禁用   |已禁用 |已启用<sup>1</sup> |
|多应用展台 |Enabled |已启用<sup>2</sup> |可用<sup>2</sup> |可用<sup>2</sup> |可用<sup>2、3</sup>  |已启用<sup>1</sup> |

> <sup>1</sup> 与禁用功能相关的语音命令不起作用。  
> <sup>2</sup> 有关如何配置这些功能的详细信息，请参阅 [选择展台应用](#plan-kiosk-apps)。  
> <sup>3</sup>即使禁用 Cortana，也会启用内置语音命令。

下表列出了不同展台模式的用户支持功能。

| &nbsp; |支持的用户类型 | 自动登录 | 多个访问级别 |
| --- | --- | --- | --- |
|单应用展台 | Microsoft 帐户 (MSA) ，Azure Active Directory (Azure AD) 或本地帐户 |是 |否 |
|多应用展台 |Azure AD 帐户 |否 |是 |

有关如何使用这些功能的示例，请参阅下表。

|将单应用展台用于： |使用多应用展台进行以下操作： |
| --- | --- |
|仅对新员工运行 Dynamics 365 指南的设备。 |一种设备，用于为一系列员工运行指南和远程协助。 |
|仅运行自定义应用的设备。 |作为大多数用户的展台工作的设备， (仅) 运行自定义应用程序，但作为特定用户组的标准设备工作。 |

### <a name="plan-kiosk-apps"></a>规划 kiosk 应用

有关如何选择展台应用的一般信息，请参阅 [ (展台模式) 的 "为分配的访问选择应用的准则 ](/windows/configuration/guidelines-for-assigned-access-app)"。

如果使用 Windows 设备门户配置单应用展台，请在安装过程中选择应用。  

如果使用移动设备管理 (MDM) 系统或预配包来配置展台模式，请使用 [AssignedAccess 配置服务提供程序 (CSP) ](/windows/client-management/mdm/assignedaccess-csp) 来指定应用程序。 CSP 使用 [应用程序用户模型 id (AUMIDs) ](/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 来标识应用程序。 下表列出了可在多应用展台中使用的某些内置应用程序的 AUMIDs。

> [!IMPORTANT]
> 展台模式确定用户登录到设备时可用的应用。 但展台模式并不是一种安全方法。 它不会阻止 "允许" 的应用打开不允许的其他应用。 由于我们不限制此行为，因此仍可以从边缘、文件资源管理器和 Microsoft Store 应用启动应用程序。 如果你不想从展台启动特定的应用，请使用[Windows Defender 应用程序控制 (WDAC) CSP](/windows/client-management/mdm/applicationcontrol-csp)来创建相应的策略。 
> 
> 此外，不能将混合现实主页设置为展台应用。

<a id="aumids"></a>

|应用名称 |AUMID |
| --- | --- |
|3D 查看器 |Microsoft3DViewer \_ 8Wekyb3d8bbwe \! Microsoft3DViewer |
|日历 |windowscommunicationsapps \_ 8wekyb3d8bbwe \! windowslive。 |
|照相机<sup>1、2</sup> |HoloCamera \_ cw5n1h2txyewy \! HoloCamera |
|Cortana<sup>3</sup> |549981C3F5F10 \_ 8wekyb3d8bbwe \! 应用 |
| (1 代 HoloLens 上的设备选取器)  |HoloDevicesFlow \_ cw5n1h2txyewy \! HoloDevicesFlow |
|HoloLens 2 上的设备选取器 |微软.Windows。DevicesFlowHost \_ cw5n1h2txyewy \! Windows。DevicesFlowHost |
|Dynamics 365 Guides |Dynamics365 \_ 8wekyb3d8bbwe \! MicrosoftGuides |
|Dynamics 365 Remote Assist |MicrosoftRemoteAssist \_ 8Wekyb3d8bbwe \! RemoteAssist |
|反馈 &nbsp; 中心 |WindowsFeedbackHub \_ 8wekyb3d8bbwe \! 应用 |
|文件资源管理器 |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|Mail |microsoft.windowscommunicationsapps_8wekyb3d8bbwe！ windowslive |
|旧 Microsoft Edge |Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge |
|新 Microsoft Edge |Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe！MSEDGE |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast<sup>4</sup> |&nbsp; |
|电影和电视 |ZuneVideo \_ 8Wekyb3d8bbwe \! ZuneVideo |
|OneDrive |microsoftskydrive \_ 8wekyb3d8bbwe \! 应用 |
|照片 |微软.Windows。照片 \_ 8wekyb3d8bbwe \! 应用 |
|旧设置 |HolographicSystemSettings_cw5n1h2txyewy！应用 |
|新设置 |BAEAEF15-9BAB-47FC-ACECAD2AE94B_cw5n1h2txyewy 800B！应用 |
|提示 |HoloLensTips \_ 8wekyb3d8bbwe \! HoloLensTips |

> <sup>1</sup> 若要启用照片或视频捕获，你必须将相机应用启用为展台应用。  
> <sup>2</sup> 在启用照相机应用时，请注意以下情况：
> - "快速操作" 菜单包括 "照片" 和 "视频" 按钮。  
> - 还应启用应用 (如照片、邮件或 OneDrive) 可以与图片交互或检索图片。  
>  
> <sup>3</sup>即使不将 Cortana 启用为展台应用，也会启用内置语音命令。 但是，与禁用的功能相关的命令不起作用。  
> <sup>4</sup>无法直接启用 Miracast。 若要启用 Miracast 为展台应用，请启用相机应用和设备选取器应用。

### <a name="plan-kiosk-profiles-for-users-or-groups"></a>为用户或组计划展台配置文件

当创建 xml 文件或使用 Intune 的 UI 来设置展台时，需要考虑谁将成为展台。 展台配置可以限制为单个帐户或 Azure AD 组。 

通常为用户或用户组启用展台。 但是，如果你计划编写自己的 XML 展台，则可能需要考虑全局分配的访问权限，在该访问中，将在设备级别应用展台，而不考虑标识。 如果这对你很有吸引力，请 [详细了解全局分配的访问亭。](hololens-global-assigned-access-kiosk.md)

#### <a name="if-you-are-creating-an-xml-file"></a>如果要创建 XML 文件：
-   许多人都创建了多个展台配置文件，并将每个配置文件分配给不同的用户/组。 例如，具有多个应用程序的 Azure AD 组的展台，以及一个具有多个应用程序亭和一个单一应用程序的访问者。
-   展台配置将称为 **配置文件 Id** ，并具有一个 GUID。
-   你将通过指定用户类型并对 **DefaultProfile Id** 使用相同的 GUID，将该配置文件分配到 "配置" 部分。
- 通过创建自定义的 OMA URI 设备配置文件并将其应用到使用 URI 值 HoloLens 设备组，可以创建一个 XML 文件，但仍可通过 MDM 将其应用到该文件：./Device/Vendor/MSFT/AssignedAccess/Configuration

#### <a name="if-you-are-creating-a-kiosk-in-intune"></a>如果正在 Intune 中创建展台。
-   每台设备只能接收单个展台配置文件，否则它将创建冲突，根本不接收展台配置。 
    -   其他类型的配置文件和策略（如与展台配置文件无关的设备限制）不与展台配置文件冲突。
-   将为属于用户登录类型的所有用户启用展台，这将使用用户或 Azure AD 组进行设置。 
-   设置展台配置后， **用户登录类型** (可以登录展台的用户) 并且选择了应用，则必须仍将设备配置分配给组。 分配的组 () 确定哪些设备接收展台设备配置，但如果启用了展台，则不会与交互。 
    - 有关在 Intune 中分配配置文件的效果的完整讨论，请参阅[在 Microsoft Intune 中分配用户和设备配置文件](/intune/configuration/device-profile-assign)。

### <a name="select-a-deployment-method"></a>选择部署方法

您可以选择下列方法之一来部署展台配置：

- [Microsoft Intune 或其他移动设备管理 (MDM) 服务](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [预配包](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows 设备门户](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > 由于此方法要求在设备上启用开发人员模式，因此我们建议你仅将其用于演示。

下表列出了每种部署方法的功能和优势。

| &nbsp; |使用 Windows 设备门户进行部署 |使用预配包进行部署 |使用 MDM 进行部署 |
| --------------------------- | ------------- | -------------------- | ---- |
|部署单应用展台   | 是           | 是                  | 是  |
|部署多应用展台    | 否            | 是                  | 是  |
|仅部署到本地设备 | 是           | 是                  | 否   |
|使用开发人员模式进行部署 |必需       | 不是必需            | 不是必需   |
|使用部署Azure Active Directory (Azure AD)   | 不是必需            | 不是必需                   | 必须  |
|自动部署      | 否            | 否                   | 是  |
|部署速度            | 快速       | 快                 | 慢 |
|大规模部署 | 不推荐    | 建议        | 建议 |

## <a name="use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk"></a>使用Microsoft Intune或其他 MDM 设置单应用或多应用展台

若要使用设备或其他 MDM Microsoft Intune设置展台模式，请执行以下步骤。

1. [准备注册设备](#mdmenroll)。
1. [创建展台配置文件](#mdmprofile)。
1. 配置展台。
   - [配置单应用展台的设置](#mdmconfigsingle)。
   - [配置多应用展台的设置](#mdmconfigmulti)。
1. [将展台配置文件分配给组](#mdmassign)。
1. 部署设备。
   - [部署单应用展台](#mdmsingledeploy)。
   - [部署多应用展台](#mdmmultideploy)。

### <a name="mdm-step-1-ndash-prepare-to-enroll-the-devices"></a><a id="mdmenroll"></a>MDM，步骤 1 &ndash; 准备注册设备

可以将 MDM 系统配置为在HoloLens登录时自动注册设备，或让用户手动注册设备。 设备还必须加入到你的Azure AD域，并分配到相应的组。

若要详细了解如何注册设备，请参阅在 MDM 中注册 HoloLens[和](hololens-enroll-mdm.md)Intune 注册方法[Windows设备](/mem/intune/enrollment/windows-enrollment-methods)。

### <a name="mdm-step-2-ndash-create-a-kiosk-configuration-profile"></a><a id="mdmprofile"></a>MDM，步骤 2 &ndash; 创建展台配置文件

1. 打开 [Azure](https://portal.azure.com/) 门户并登录到Intune 管理员帐户。
1. 选择 **"Microsoft Intune**  >  **配置 - 配置文件**  >  **""创建配置文件"。**
1. 输入配置文件名称。
1. 选择  >  **"Windows 10及更高版本**"，然后选择"**配置文件类型**  > **设备限制"。**
1. 选择 **"**  >  **配置展** 台"，然后选择以下选项之一：
   - 若要创建单应用展台，请选择 **"展台模式**  >  **单应用展台"。**
   - 若要创建多应用展台，请选择 **"展台模式**  >  **多应用展台"。**
1. 若要开始配置展台，请选择"添加 **"。**

你的下一步根据你可能需要的展台类型而不同。 有关详细信息，请选择以下选项之一：  

- [单应用展台](#mdmconfigsingle)
- [多应用展台](#mdmconfigmulti)

若要详细了解如何创建展台配置文件，请参阅使用 Intune Windows 10 Windows Holographic for Business作为专用展台运行的设备和[设备设置](/intune/configuration/kiosk-settings)。

### <a name="mdm-step-3-single-app-ndash--configure-the-settings-for-a-single-app-kiosk"></a><a id="mdmconfigsingle"></a>MDM，步骤 3 (单应用) &ndash;  配置单应用展台的设置

本部分总结了单应用展台所需的设置。 有关更多详细信息，请参阅以下文章：

- 若要了解如何在 Intune 中配置展台配置文件，请参阅[How to Configure Kiosk Mode Using Microsoft Intune。](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)
- 有关 Intune 中单应用展台的可用设置详细信息，请参阅 [单一全屏应用展台](/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- 对于其他 MDM 服务，请查看提供商的文档，了解相关说明。 如果必须使用自定义 XML 配置在 MDM 服务中设置展台，请创建定义展台配置的 [XML 文件](#ppkioskconfig)。

1. 选择 **"用户登录类型** 本地用户帐户"，然后输入可登录到展台的本地 (设备) 帐户或 Microsoft 帐户  >   (MSA) 的用户名。
   > [!NOTE]  
   > Windows Holographic for Business 不支持“自动登录”用户帐户类型。
1. 选择 **"应用程序**  >  **类型""** 应用商店应用"，然后从列表中选择一个应用。

下一步是 [将配置文件](#mdmassign) 分配给组。

### <a name="mdm-step-3-multi-app-ndash-configure-the-settings-for-a-multi-app-kiosk"></a><a id="mdmconfigmulti"></a>MDM，步骤 3 (多应用) &ndash; 配置多应用展台的设置

本部分总结了多应用展台所需的设置。 有关更详细信息，请参阅以下文章：

- 若要了解如何在 Intune 中配置展台配置文件，请参阅[How to Configure Kiosk Mode Using Microsoft Intune。](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)
- 有关 Intune 中多应用展台的可用设置详细信息，请参阅 [多应用展台](/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- 对于其他 MDM 服务，请查看提供商的文档，了解相关说明。 如果需要使用自定义 XML 配置在 MDM 服务中设置展台，请创建 [定义](#ppkioskconfig)展台配置的 XML 文件。 如果使用 XML 文件，请确保包含"开始 ["布局](#start-layout-for-hololens)。  
- 可以选择将自定义的"开始"布局与 Intune 或其他 MDM 服务一同使用。 有关详细信息，请参阅启动[Intune 和 Intune (MDM 的布局) 。 ](#start-layout-file-for-mdm-intune-and-others)

1. 选择 **"Windows 10 S 模式设备""目标设备**  >  **否"。**  
>[!NOTE]  
> Windows Holographic for Business 上不支持 S 模式。

1. 选择 **"用户登录类型Azure AD** 组或用户登录类型HoloLens访问者 ，然后添加一个或多个  >    >  用户组或帐户。  

   只有属于你在用户登录类型中指定的组或帐户 **的用户** 才能使用展台体验。

1. 使用下列选项选择一个或多个应用：
   - 若要添加已上传的业务线应用，请选择" **添加应用商店应用** "，然后选择想要的应用。
   - 若要通过指定应用的 AUMID 来添加应用，请选择"按 **AUMID** 添加"，然后输入应用的 AUMID。 [查看可用 AUMID 的列表](#aumids)

下一步是 [将配置文件](#mdmassign) 分配给组。

### <a name="mdm-step-4-ndash-assign-the-kiosk-configuration-profile-to-a-group"></a><a id="mdmassign"></a>MDM，步骤 4 &ndash; 将展台配置文件分配给组

使用 **展** 台配置文件的"分配"页可设置展台配置的部署位置。 在最简单的情况下，将展台配置文件分配给一个组，该组将包含设备在 MDM HoloLens设备。

### <a name="mdm-step-5-single-app-ndash-deploy-a-single-app-kiosk"></a><a id="mdmsingledeploy"></a>MDM，步骤 5 (单应用) &ndash; 部署单应用展台

使用 MDM 系统时，可以在 OOBE 期间在 MDM 中注册设备。 OOBE 完成后，可以轻松登录设备。

在 OOBE 期间，请执行以下步骤：

1. 使用在展台配置文件中指定的帐户登录。
1. 注册该设备。 确保将设备添加到展台配置文件分配到的组。
1. 等待 OOBE 完成，等待应用商店应用下载和安装，并应用策略。 然后重启设备。

下次登录到设备时，展台应用应会自动启动。

如果此时看不到展台配置， [请检查分配状态](/intune/configuration/device-profile-monitor)。

### <a name="mdm-step-5-multi-app-ndash-deploy-a-multi-app-kiosk"></a><a id="mdmmultideploy"></a>MDM，步骤 5 (多应用) &ndash; 部署多应用展台

使用 MDM 系统时，可以将设备加入 Azure AD租户，在 OOBE 期间在 MDM 中注册设备。 如果适用，请为用户提供注册信息，以便他们在 OOBE 过程中可用。

> [!NOTE]  
> 如果已将展台配置文件分配给包含用户的组，请确保其中一个用户帐户是登录到设备的第一个帐户。

在 OOBE 期间，请执行以下步骤：

1. 使用属于"用户登录类型" **组的帐户登录** 。
1. 注册该设备。
1. 等待属于展台配置文件的任何应用下载并安装。 另外，请等待策略应用。  
1. 在 OOBE 完成后，可以通过 Microsoft 应用商店或旁加载来安装其他应用。 设备所属的组[所需的应用](/mem/intune/apps/apps-deploy#assign-an-app)将自动安装。
1. 安装完成后，重新启动设备。

下次使用属于 **用户登录类型** 的帐户登录到设备时，kiosk 应用应会自动启动。

如果此时未看到展台配置，请 [检查分配状态](/intune/configuration/device-profile-monitor)。

## <a name="use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk"></a>使用预配包设置单个应用程序或多应用展台

若要使用预配包设置展台模式，请执行以下步骤。

1. [创建定义 kiosk 配置的 XML 文件](#ppkioskconfig)，包括 [开始布局](#start-layout-for-hololens)。
2. [将 XML 文件添加到预配包。](#ppconfigadd)
3. [将预配包应用到 HoloLens。](#ppapply)

### <a name="provisioning-package-step-1-ndash-create-a-kiosk-configuration-xml-file"></a><a id="ppkioskconfig"></a>预配包，步骤 1 &ndash; 创建展台配置 XML 文件

按照[常规说明为 Windows 桌面创建展台配置 XML 文件](/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)，但以下情况除外：

- 不要将经典 Windows 应用程序 (Win32) 包括在内。 HoloLens 不支持这些应用程序。
- 使用[占位符开始布局 XML](#start-layout-for-hololens) HoloLens。
- 可选：向展台配置添加来宾访问权限

#### <a name="optional-add-guest-access-to-the-kiosk-configuration"></a><a id="ppkioskguest"></a>可选：向展台配置添加来宾访问权限

在 XML 文件的 "配置" [ 部分](/windows/configuration/lock-down-windows-10-to-specific-apps#configs)中，可以配置名为 "**访问者**" 的特殊组，以允许来宾使用展台。 当展台配置为支持 **访问者** 特殊组时，会将 "**来宾**" 选项添加到登录页。 **Guest** 帐户不需要密码，当帐户注销时，将删除与该帐户关联的任何数据。

若要启用 **来宾** 帐户，请将以下代码片段添加到展台配置 XML：

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```
#### <a name="enable-visitor-autologon"></a>启用访问者自动登录

[Windows 全息版、版本 21H1](hololens-release-notes.md#windows-holographic-version-21h1)和更高版本：
- AAD 和非添加配置都支持为展台模式启用自动登录的访问者帐户。

##### <a name="non-aad-configuration"></a>非 AAD 配置

1. 创建一个预配包，其中：
    1. 将运行时设置 AssignedAccess 配置为允许访问者帐户。
    1. （可选）在 MDM (运行时设置/工作区/注册) 中注册设备，以便以后可以对其进行管理。
    1. 不创建本地帐户
2. [应用设置包](hololens-provisioning.md)。

##### <a name="aad-configuration"></a>AAD 配置

为展台模式配置的 AAD 加入设备可以通过在登录屏幕上点击一次按钮，登录访问者帐户。 登录到访问者帐户后，在从 "开始" 菜单中显式注销访问者或重新启动设备之前，该设备将不会提示登录。

可以通过 [自定义 OMA URI 策略](/mem/intune/configuration/custom-settings-windows-10)来管理访问者自动登录：

- URI 值：./Device/Vendor/MSFT/MixedReality/VisitorAutoLogon


| 策略 |描述 |配置 
| --------------------------- | ------------- | -------------------- |
| MixedReality/VisitorAutoLogon | 允许访问者自动登录到展台。 | 1 (是) ，0 (否，默认值为 )  |

#### <a name="placeholder-start-layout-for-hololens"></a><a id="start-layout-for-hololens"></a>HoloLens 的占位符开始布局

如果使用 [预配包](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 配置多应用展台，此过程需要开始布局。 Windows Holographic for Business 中不支持开始布局自定义。 因此，您必须使用占位符开始布局。

> [!NOTE]  
> 由于单应用展台会在用户登录时启动展台应用，因此它不会使用 "开始"菜单，并且无需具有开始布局。

> [!NOTE]  
> 如果使用 [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 设置多应用展台，则可以选择使用 "开始布局"。 有关详细信息，请参阅 [MDM (Intune 的占位符启动布局文件和其他) ](#start-layout-file-for-mdm-intune-and-others)。

对于 "开始" 布局，请将以下 " **StartLayout** " 部分添加到展台预配 XML 文件：

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

#### <a name="placeholder-start-layout-file-for-mdm-intune-and-others"></a><a id="start-layout-file-for-mdm-intune-and-others"></a>MDM (Intune 和其他人的占位符开始布局文件) 

将以下示例另存为 XML 文件。 在 Microsoft Intune (或另一个提供展台配置文件) 的 MDM 服务中配置多应用展台时，可以使用此文件。

> [!NOTE]
> 如果需要使用自定义设置和完整的 XML 配置在 MDM 服务中设置展台，请使用 [预配包的启动布局说明](#start-layout-for-hololens)。

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

### <a name="prov-package-step-2-ndash-add-the-kiosk-configuration-xml-file-to-a-provisioning-package"></a><a id="ppconfigadd"></a>Prov. 包，步骤 2 &ndash; 将展台配置 XML 文件添加到预配包

1. 打开[Windows 配置设计器](https://www.microsoft.com/store/apps/9nblggh4tx22)。
1. 选择 " **高级设置**"，输入项目的名称，然后选择 " **下一步**"。
1. 选择 **Windows 10 全息版**，然后选择 "**下一步**"。
1. 选择“完成”  。 此时将打开你的程序包的工作区。
1. 选择 "**运行时设置**"  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**。
1. 在中心窗格中，选择 " **浏览** " 以查找并选择已创建的展台配置 XML 文件。

   ![Windows 配置设计器中的 MultiAppAssignedAccessSettings 字段的屏幕截图](./images/multiappassignedaccesssettings.png)

1. 可选。  (如果要在设备的初始设置后应用预配包，并且展台设备上已有管理员用户，请跳过此步骤。 ) 选择 " **运行时设置** &gt; **帐户** &gt; " " **用户**"，然后创建用户帐户。 提供 "用户名" 和 "密码"，然后选择 " **UserGroup**  >  **Administrators**"。  
  
     通过使用此帐户，你可以查看预配状态和日志。  
1. 可选。  (如果你已在展台设备上拥有非管理员帐户，请跳过此步骤。 ) 选择 " **运行时设置** &gt; **帐户** &gt; **用户**"，然后创建一个本地用户帐户。 确保用户名与你在配置 XML 中指定的帐户相同。 选择 **UserGroup**  >  **Standard Users**。
1. 选择“文件” > “保存”。
1. 选择 "**导出**  >  **设置包**"，然后选择 "**所有者**  >  **IT 管理员**"。这会将此预配包的优先级设置为高于从其他源应用于此设备的预配包。
1. 选择“**下一步**”。
1. 在 " **设置包安全性** " 页上，选择一个安全选项。
   > [!IMPORTANT]  
   > 如果选择 " **启用包签名**"，则还必须选择用于对包进行签名的有效证书。 为此，请选择 " **浏览** "，然后选择要用于对包进行签名的证书。
   
   > [!CAUTION]  
   > 不要选择 " **启用包加密**"。 在 HoloLens 设备上，此设置会导致预配失败。
1. 选择“**下一步**”。
1. 指定生成时要在其中进行预配包的输出位置。 默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。 如果要更改输出位置，请选择 " **浏览**"。 完成后，选择“下一步”。
1. 选择 " **生成** " 开始生成包。 无需花费太长时间即可构建设置包。 "生成" 页显示项目信息，进度栏指示生成状态。

### <a name="provisioning-package-step-3-ndash-apply-the-provisioning-package-to-hololens"></a><a id="ppapply"></a>预配包，步骤 3 &ndash; 将预配包应用到 HoloLens

"使用预配包配置 HoloLens" 一文提供了在以下情况下应用预配包的详细说明：

- 最初可以在[安装过程中将预配包应用到 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

- 你还可以在[安装后将预配包应用到 HoloLens](hololens-provisioning.md#applyremove-a-provisioning-package-to-hololens-after-setup)。

## <a name="use-the-windows-device-portal-to-set-up-a-single-app-kiosk"></a>使用 Windows 设备门户设置单应用展台

若要使用 Windows 设备门户设置展台模式，请执行以下步骤。

1. [设置 HoloLens 设备以使用 Windows 设备门户](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)。 Device Portal 是 HoloLens 上的 Web 服务器，你可以从电脑上的 Web 浏览器连接到它。

    > [!CAUTION]
    > 将 HoloLens 设置为使用设备门户时，必须在设备上启用开发人员模式。 在具有 Windows Holographic for Business 的设备上，开发人员模式使你能够进行面加载应用。 但是，此设置会创建一个风险，用户可在其中安装尚未由 Microsoft Store 认证的应用。 管理员可以通过使用 [策略 CSP](/windows/client-management/mdm/policy-configuration-service-provider)中的 **ApplicationManagement/AllowDeveloper 解锁** 设置来阻止启用开发人员模式的功能。 [了解有关开发人员模式的详细信息。](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. 在计算机上，使用[Wi-Fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) HoloLens USB 连接到[计算机](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)。

1. 执行下列操作之一：
   - 如果是首次连接到Windows 设备门户，请[创建用户名和密码](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - 输入之前设置的用户名和密码。

    > [!TIP]
    > 如果发现浏览器中的证书错误，请遵循[以下疑难解答步骤](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)。

1. 在"Windows 设备门户"中，选择"**展台模式"。**

1. 选择 **"启用展台模式**"，选择要在设备启动时运行的应用，然后选择"保存 **"。**

    ![展台模式](images/kiosk.png)
1. 重启HoloLens。 如果仍处于打开状态设备门户，可以选择页面顶部的"重启&quot;。 

> [!NOTE]
> 展台模式可以通过 设备门户 的 REST API 进行 POST 设置，对 /api/holographic/kioskmode/settings 执行 POST，其中一个必需的查询字符串参数 (&quot;kioskModeEnabled&quot;的值为&quot;true&quot;或&quot;false") ，以及一个可选参数 ("startupApp"，其值为包名称) 。 请记住，设备门户仅供开发人员使用，不应在非开发人员设备上启用。 将来REST API更新/发布中，更新版本可能会更改。

## <a name="more-information"></a>详细信息

### <a name="watch-how-to-configure-a-kiosk-by-using-a-provisioning-package"></a>了解如何使用预配包配置展台。  

> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]

### <a name="global-assigned-access--kiosk-mode"></a>全局分配访问权限 - 展台模式
- 通过启用在系统级别应用展台模式的新展台方法，减少了展台的标识管理。

此新功能允许 IT 管理员为多个应用展台模式配置 HoloLens 2 设备，该模式适用于系统级别，与系统上的任何标识没有关联，并且适用于登录设备的每个人。 有关[HoloLens的详细信息](hololens-global-assigned-access-kiosk.md)，请参阅全局分配访问展台文档。

### <a name="automatic-launch-of-an-application-in-multiple-app-kiosk-mode"></a>在多应用展台模式下自动启动应用程序 
- 具有自动应用启动的集中体验，进一步增加了为展台模式体验选择的 UI 和应用选择。

仅适用于多应用展台模式，并且只能使用"分配的访问权限配置"中下面的突出显示属性将 1 个应用指定为自动启动。 

用户登录时，应用程序会自动启动。 

```xml
<AllowedApps>                     
      <!--TODO: Add AUMIDs of apps you want to be shown here, e.g. <App AppUserModelId="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge" rs5:AutoLaunch="true"/> --> 
</AllowedApps>
```


### <a name="kiosk-mode-behavior-changes-for-handling-of-failures"></a>展台模式行为更改，用于处理故障
应用展台模式时遇到故障时，会出现以下行为：

- 在 Windows，版本 20H2 - HoloLens将在该版本中显示"开始"菜单。
- WindowsHolographic，版本 20H2 - 如果设备具有展台配置，该配置是全局分配的访问权限和 AAD 团队成员分配的访问权限的组合，则确定 AAD 组成员身份失败时，用户将看到"开始"菜单中的"未显示任何内容"。

![当展台模式发生故障时，其外观的图像。](images/hololens-kiosk-failure-behavior.png )


- 从[Holographic Windows版本 21H1](hololens-release-notes.md#windows-holographic-version-21h1)开始，展台模式在显示空的开始菜单之前查找"全局分配的访问权限"。 如果 AAD 组展台模式 (发生故障时出现) ，则展台体验将回退到全局展台配置。

### <a name="cache-azure-ad-group-membership-for-offline-kiosk"></a>缓存Azure AD展台的组成员身份

- 通过消除展台模式故障时可用的应用，实现更安全的展台模式。
- 已启用脱机展台，Azure AD组一起使用最多 60 天。

此策略控制多少天，Azure AD组成员身份缓存用于针对已登录用户Azure AD组分配的访问配置。 一旦此策略值设置为大于 0 的值，则否则使用缓存。  

名称：AADGroupMembershipCacheValidityInDays URI 值：./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays

最短 - 0 天  
最大值 - 60 天 

正确使用此策略的步骤： 
1. 为展台组创建设备配置文件Azure AD，并将其分配给HoloLens设备 () 。 
1. 创建基于 OMA URI 的自定义设备配置，将此策略值设置为所需的天数 (> 0) 并将其分配给 HoloLens 设备 () 。 
    1. URI 值应在 OMA-URI 文本框中输入为 ./Vendor/MSFT/Policy/Config/MixedReality/AADGroupMembershipCacheValidityInDays
    1. 该值可以介于允许的最小值/最大值之间。
1. 注册HoloLens并验证这两个配置是否应用于设备。 
1. 在Azure AD Internet 可用时让用户 1 登录，用户登录并成功Azure AD组成员身份后，将创建缓存。 
1. 现在Azure AD用户 1 可以脱机HoloLens，只要策略值允许 X 天，就可以在展台模式下使用它。 
1. 对于任何其他 Azure AD 用户 N，可以重复步骤 4 和 5。此处的要点是，任何 Azure AD 用户都必须使用 Internet 登录到设备，以便我们至少能够确定他们是展台配置所面向的 Azure AD 组的成员。 
 
> [!NOTE]
> 在针对用户执行步骤 4 之前Azure AD用户将遇到"断开连接"环境中提到的失败行为。 


## <a name="xml-kiosk-code-samples-for-hololens"></a>XML 展台代码示例HoloLens

### <a name="multiple-app-kiosk-mode-targeting-an-azure-ad-group"></a>面向单个组的多个应用展Azure AD模式。 
此展台部署一个展台，对于 Azure AD 组的用户，他们将启用包含 3 个应用的展台：设置、Remote Assist 和 反馈中心。 若要修改此示例以立即使用，请确保更改下面突出显示的 GUID，以匹配Azure AD组。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-group.xml" highlight="20":::


### <a name="multiple-app-kiosk-mode-targeting-azure-ad-account"></a>多个应用展台模式，Azure AD帐户。
此展台为单个用户部署展台，他们将启用包括 3 个应用的展台：设置、Remote Assist 和 反馈中心。 若要修改此示例以立即使用，请确保更改下面突出显示的帐户，以匹配Azure AD帐户。 


:::code language="xml" source="samples/kiosk-sample-multi-aad-account.xml" highlight="20":::

