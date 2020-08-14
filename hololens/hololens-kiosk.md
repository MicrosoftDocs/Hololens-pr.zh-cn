---
title: 将 HoloLens 设置为 Kiosk
description: 使用展台配置锁定 HoloLens 上的应用。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/27/2020
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: f5c45477ab33064afe30e275f8b0003bc6022eac
ms.sourcegitcommit: bdbaed42dd9ecbd0ed9517de2e98a0465f584c1d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2020
ms.locfileid: "10929848"
---
# 将 HoloLens 设置为 Kiosk

你可以将 HoloLens 设备配置为固定用途的设备（也称为 *展台*），方法是将设备配置为在展台模式下运行。 展台模式限制设备上可用 (或用户) 的应用程序。 展台模式是一种方便的功能，可用于将 HoloLens 设备专用于商业应用，或在应用演示中使用 HoloLens 设备。

本文提供有关特定于 HoloLens 设备的展台配置方面的信息。 有关不同类型的基于 Windows 的网亭以及如何配置它们的常规信息，请参阅 [在 Windows 桌面版上配置网亭和数字签名](https://docs.microsoft.com/windows/configuration/kiosk-methods)。  

> [!IMPORTANT]  
> 展台模式确定当用户登录到设备时，哪些应用可用。 但是，展台模式不是一种安全方法。 它不会阻止 "允许" 应用打开不允许的另一个应用。 为了阻止应用或进程打开，请使用 [Windows Defender 应用程序控件 (WDAC) CSP](https://docs.microsoft.com/windows/client-management/mdm/applicationcontrol-csp) 来创建相应的策略。  

你可以在单个应用或多个应用配置中使用展台模式，并且可以使用三个进程之一来设置和部署展台配置。

> [!IMPORTANT]  
> 删除多应用配置将删除分配的访问功能所创建的用户锁定配置文件。 但是，它不会还原所有策略更改。 若要还原这些策略，必须将设备重置为出厂设置。

## 规划展台部署

### 展台模式要求

您可以将任何 HoloLens 2 设备配置为使用展台模式。

若要将 HoloLens (第一代) 设备配置为使用展台模式，必须首先确保该设备运行的是 Windows 10 版本1803或更高版本。 如果你已使用 Windows 设备恢复工具将 HoloLens (第一代) 设备恢复为默认版本，或者如果已安装了最新的更新，则设备已准备好进行配置。

> [!IMPORTANT]  
> 若要帮助保护在展台模式下运行的设备，请考虑添加关闭诸如 USB 连接等功能的设备管理策略。 此外，检查更新铃声设置以确保在工作时间内不会自动更新。

### 在单应用展台或多应用展台之间做出选择

当用户登录到设备时，单应用展台会启动指定的应用。 "开始" 菜单已禁用，与 Cortana 一样。 HoloLens 2 设备不响应 [开始](hololens2-basic-usage.md#start-gesture) 手势。 HoloLens (第一代) 设备不会响应 [绽放](hololens1-basic-usage.md) 手势。 由于只有一个应用可以运行，因此用户无法放置其他应用。

当用户登录到设备时，多应用展台显示 "开始" 菜单。 展台配置确定哪些应用在 "开始" 菜单上可用。 你可以使用多应用展台为用户提供简单易懂的体验，只需向他们展示他们必须使用的功能，并删除不需要使用的功能。

下表列出了不同展台模式下的功能功能。

| &nbsp; |“开始”菜单 |"快速操作" 菜单 |摄像头和视频 |Miracast |Cortana |内置语音命令 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|单应用展台 |已禁用 |已禁用   |已禁用 |已禁用   |已禁用 |已启用 <sup> 1</sup> |
|多应用展台 |启用 |已启用 <sup> 2</sup> |可用 <sup> 2</sup> |可用 <sup> 2</sup> |可用 <sup> 2，3</sup>  |已启用 <sup> 1</sup> |

> <sup>1与 </sup> 禁用的功能相关的语音命令不起作用。  
> <sup>2有关 </sup> 如何配置这些功能的详细信息，请参阅 [选择展台应用](#plan-kiosk-apps)。  
> <sup>3 </sup> 即使禁用 Cortana，也会启用内置语音命令。

下表列出了不同展台模式的用户支持功能。

| &nbsp; |支持的用户类型 | 自动登录 | 多个访问级别 |
| --- | --- | --- | --- |
|单应用展台 |托管服务帐户在 Azure Active Directory (AAD) 或本地帐户中 (MSA)  |是 |否 |
|多应用展台 |AAD 帐户 |否 |是 |

有关如何使用这些功能的示例，请参阅下表。

|使用单应用展台进行以下操作： |使用多应用展台进行以下操作： |
| --- | --- |
|仅运行新员工的 Dynamics 365 指南的设备。 |为一系列员工运行指南和远程协助的设备。 |
|仅运行自定义应用的设备。 |作为大多数用户的展台工作的设备 (仅运行自定义应用) ，但作为特定用户组的标准设备运行。 |

### 规划展台应用

有关如何选择展台应用的一般信息，请参阅 [ (展台模式下为分配的 access 选择应用指南) ](https://docs.microsoft.com/windows/configuration/guidelines-for-assigned-access-app)。

如果你使用 Windows Device Portal 配置单应用展台，请在安装过程中选择该应用。  

如果你使用 (MDM) 系统或预配包来配置展台模式的移动设备管理，请使用 [AssignedAccess 配置服务提供程序 (CSP) ](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) 来指定应用程序。 CSP 使用 [应用程序用户模型 id (aumid) ](https://docs.microsoft.com/windows/configuration/find-the-application-user-model-id-of-an-installed-app) 来标识应用程序。 下表列出了可在多应用展台中使用的一些内置应用程序的 Aumid。

> [!CAUTION]
> 您不能选择 "外壳" 应用作为展台应用。 此外，我们 **建议你不要选择 "** microsoft Edge"、"microsoft Store" 或 "文件资源管理器" 作为展台应用。  

<a id="aumids"></a>

|应用名称 |AUMID |
| --- | --- |
|3D 查看器 |Microsoft3DViewer \ _8wekyb3d8bbwe \！Microsoft3DViewer |
|日历 |windowscommunicationsapps \ _8wekyb3d8bbwe \！ windowslive。 |
|相机 <sup> 1、2</sup> |HoloCamera \ _cw5n1h2txyewy \！HoloCamera |
|Cortana <sup> 3</sup> |549981C3F5F10 \ _8wekyb3d8bbwe \！应用 |
|HoloLens 上的设备选取器 (第一代)  |HoloDevicesFlow \ _cw5n1h2txyewy \！HoloDevicesFlow |
|HoloLens 2 上的设备选取器 |DevicesFlowHost \ _cw5n1h2txyewy \！DevicesFlowHost |
|Dynamics 365 Guides |Dynamics365 _8wekyb3d8bbwe \！MicrosoftGuides |
|Dynamics 365 Remote Assist |MicrosoftRemoteAssist \ _8wekyb3d8bbwe \！RemoteAssist |
|反馈 &nbsp; 中心 |WindowsFeedbackHub \ _8wekyb3d8bbwe \！应用 |
|文件资源管理器 |c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App |
|邮件 |windowscommunicationsapps_8wekyb3d8bbwe！ windowslive！ |
|Microsoft Store |Microsoft.WindowsStore_8wekyb3d8bbwe!App |
|Miracast <sup> 4</sup> |&nbsp; |
|电影和电视 |ZuneVideo \ _8wekyb3d8bbwe \！ZuneVideo |
|OneDrive |microsoftskydrive \ _8wekyb3d8bbwe \！应用 |
|照片 |_8wekyb3d8bbwe \ 照片。应用 |
|“设置” |HolographicSystemSettings \ _cw5n1h2txyewy \！应用 |
|提示 |HoloLensTips \ _8wekyb3d8bbwe \！HoloLensTips |

> <sup>1 </sup> 要启用照片或视频捕获，您必须将相机应用启用为展台应用。  
> <sup>2 </sup> 启用摄像头应用时，请注意以下条件：
> - "快速操作" 菜单包含 "照片" 和 "视频" 按钮。  
> - 你还应启用可与图片交互或检索图片的应用 (例如照片、邮件或 OneDrive) 。  
>  
> <sup>3 </sup> 即使不将 Cortana 启用为展台应用，也会启用内置语音命令。 但是，与禁用的功能相关的命令不起作用。  
> <sup>4 </sup> 不能直接启用 Miracast。 若要将 Miracast 启用为展台应用，请启用相机应用和设备选取器应用。

### 规划用户和设备组

在 MDM 环境中，使用组管理设备配置和用户访问。 

展台配置文件包括 " **用户登录类型** " 设置。 **用户登录类型** 标识用户 (或组，其中包含可以使用你添加的应用或应用的用户) 。 如果用户使用未包含在配置文件中的帐户登录，则该用户无法使用展台上的应用。  

> [!NOTE]  
> 单应用展台的 **用户登录类型** 指定单个用户帐户。 这是在其下运行展台的用户上下文。 多应用展台的 **用户登录类型** 可以指定可以使用展台的一个或多个用户帐户或组。

在将 kiosk 配置部署到设备之前，必须将 kiosk 配置配置文件 *分配* 给包含设备的组或可登录设备的用户。 此设置将产生如下所示的行为。

- 如果设备是分配组的成员，则在任何用户首次登录设备时，展台配置将部署到设备。  
- 如果设备不是分配组的成员，但属于该组成员的用户登录，则 kiosk 配置将在此时部署到设备。

有关在 Intune 中分配配置文件的效果的完整讨论，请参阅 [在 Microsoft Intune 中分配用户和设备配置文件](https://docs.microsoft.com/intune/configuration/device-profile-assign)。

> [!NOTE]  
> 以下示例介绍了多应用网亭。 单应用网亭以类似的方式运行，但只有一个用户帐户才获得展台体验。

**示例 1**

为设备和用户使用单个组 (组 1) 。 一个设备和用户 A、B 和 C 是该组的成员。 配置展台配置文件的方式如下所示：  

- **用户登录类型**：组1
- **已分配的组**：组1

无论哪个用户首先登录到设备 (并通过 "全新体验" 或 "OOBE) "，"展台配置" 都将部署到设备。 用户 A、B 和 C 均可登录到设备并获取 kiosk 体验。

**示例 2**

您向需要不同展台体验的两个不同供应商推出了设备。 两个供应商都有用户，您希望所有用户都可以从其自己的供应商和其他供应商处访问展台。 按如下方式配置组：

- 设备组1：
  - 设备 1 (供应商 1) 
  - 设备 2 (供应商 1) 

- 设备组2：
  - 设备 3 (供应商 2) 
  - 设备 4 (供应商 2) 

- 用户组：
  - 用户 A (供应商 1) 
  - 用户 B (供应商 2) 

创建两个具有以下设置的展台配置文件：

- 展台档案1：
   - **用户登录类型**：用户组
   - **已分配的组**：设备组1

- 展台档案2：
   - **用户登录类型**：用户组
   - **已分配的组**：设备组2

这些配置将产生以下结果：

- 当任何用户登录到设备1或设备2时，Intune 将展台配置文件1部署到该设备。
- 当任何用户登录到设备3或设备4时，Intune 将展台配置文件2部署到该设备。
- 用户 A 和用户 B 可以登录到四个设备中的任何一个。 如果他们登录到设备1或设备2，他们将看到供应商1的展台体验。 如果他们登录到设备3或设备4，他们将看到供应商2的展台体验。

#### 配置文件冲突

如果两个或更多展台配置文件的目标设备相同，则会发生冲突。 在 Intune 托管设备的情况下，Intune 不会应用任何冲突的配置文件。

其他类型的配置文件和策略（如与展台配置文件无关的设备限制）不会与展台配置文件冲突。

### 选择部署方法

你可以选择以下方法之一来部署展台配置：

- [ (MDM) 服务的 Microsoft Intune 或其他移动设备管理](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk)

- [设置包](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk)

- [Windows Device Portal](#use-the-windows-device-portal-to-set-up-a-single-app-kiosk)

   > [!NOTE]  
   > 由于此方法需要在设备上启用开发人员模式，因此我们建议仅将其用于演示。

下表列出了每个部署方法的功能和优点。

| &nbsp; |使用 Windows Device Portal 进行部署 |使用预配包进行部署 |使用 MDM 进行部署 |
| --------------------------- | ------------- | -------------------- | ---- |
|部署单应用网亭   | 是           | 是                  | 是  |
|部署多路应用网亭    | 否            | 是                  | 是  |
|仅部署到本地设备 | 是           | 是                  | 否   |
|使用开发人员模式进行部署 |必需       | 不需要            | 不需要   |
|使用 Azure Active Directory (AAD) 进行部署  | 不需要            | 不需要                   | 必需  |
|自动部署      | 否            | 否                   | 是  |
|部署速度            | 迅速       | 迅速                 | 慢速 |
|按比例部署 | 不建议    | 不建议        | 推荐 |

## 使用 Microsoft Intune 或其他 MDM 设置单应用或多应用展台

若要使用 Microsoft Intune 或其他 MDM 系统设置展台模式，请按照下列步骤操作。

1. [准备注册设备](#mdmenroll)。
1. [创建展台配置文件](#mdmprofile)。
1. 配置展台。
   - [配置单应用展台的设置](#mdmconfigsingle)。
   - [配置多应用展台的设置](#mdmconfigmulti)。
1. [将展台配置文件分配到组](#mdmassign)。
1. 部署设备。
   - [部署单应用展台](#mdmsingledeploy)。
   - [部署多应用展台](#mdmmultideploy)。

### <a id="mdmenroll"></a>MDM，步骤 1 &ndash; 准备注册设备

你可以将 MDM 系统配置为在用户首次登录时自动注册 HoloLens 设备，或者让用户手动注册设备。 设备还必须加入到 Azure AD 域，并分配给相应的组。

有关如何注册设备的详细信息，请参阅 [在 MDM 中注册 HoloLens](hololens-enroll-mdm.md) 和 [Windows 设备的 Intune 注册方法](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-methods)。

### <a id="mdmprofile"></a>MDM、步骤 2 &ndash; 创建展台配置文件

1. 打开 [Azure](https://portal.azure.com/) 门户并登录到你的 Intune 管理员帐户。
1. 选择 " **Microsoft Intune**  >  **设备配置"-配置文件**  >  **创建配置文件**。
1. 输入配置文件名称。
1. 选择 "**平台**  >  **Windows 10 及更高版本**"，然后选择 "**配置文件类型**  > **设备限制**"。
1. 选择 "**配置**  >  **展台**"，然后选择下列操作之一：
   - 若要创建单应用展台，请选择 "**展台模式**  >  **单应用展台**"。
   - 若要创建多应用程序亭，请选择 "**展台模式**  >  **多应用展台**"。
1. 要开始配置展台，请选择 " **添加**"。

根据所需的展台类型，后续步骤会有所不同。 有关详细信息，请选择下列选项之一：  

- [单应用展台](#mdmconfigsingle)
- [多应用展台](#mdmconfigmulti)

有关如何创建展台配置文件的详细信息，请参阅 [windows 10 和 Windows 全息版 For Business 设备设置，以使用 Intune 作为专用展台运行](https://docs.microsoft.com/intune/configuration/kiosk-settings)。

### <a id="mdmconfigsingle"></a>MDM、步骤 3 (单应用) &ndash;  配置单应用展台的设置

本部分概述了单应用展台所需的设置。 有关更多详细信息，请参阅以下文章：

- 有关如何在 Intune 中配置展台配置文件的信息，请参阅 [如何使用 Microsoft Intune 配置展台模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。
- 有关 Intune 中的单应用网亭可用设置的详细信息，请参阅 [单个全屏应用网亭](https://docs.microsoft.com/intune/configuration/kiosk-settings-holographic#single-full-screen-app-kiosks)
- 对于其他 MDM 服务，请参阅提供商文档中的说明。 如果必须使用自定义 XML 配置在 MDM 服务中设置展台，请 [创建一个定义 kiosk 配置的 XML 文件](#ppkioskconfig)。

1. 选择 "**用户登录类型**  >  **本地用户帐户**"，然后输入可登录到展台的本地 (设备) 帐户或 Microsoft 帐户 (MSA) 的用户名。
   > [!NOTE]  
   > Windows 全息版商业版不支持**自动登录**用户帐户类型。
1. 选择 "**应用程序类型**  >  **存储应用**"，然后从列表中选择一个应用。

下一步是将配置文件 [分配](#mdmassign) 给组。

### <a id="mdmconfigmulti"></a>MDM、步骤 3 (多应用) &ndash; 配置多应用展台的设置

本部分概述了多应用展台所需的设置。 有关更多详细信息，请参阅以下文章：

- 有关如何在 Intune 中配置展台配置文件的信息，请参阅 [如何使用 Microsoft Intune 配置展台模式](hololens-commercial-infrastructure.md#how-to-configure-kiosk-mode-using-microsoft-intune)。
- 有关 Intune 中的多应用网亭可用设置的详细信息，请参阅 [多路应用网亭](https://docs.microsoft.com/mem/intune/configuration/kiosk-settings-holographic#multi-app-kiosks)
- 对于其他 MDM 服务，请参阅提供商文档中的说明。 如果需要使用自定义 XML 配置在 MDM 服务中设置展台，请 [创建一个定义 kiosk 配置的 XML 文件](#ppkioskconfig)。 如果使用 XML 文件，请确保包含 " [开始" 布局](#start-layout-for-hololens)。  
- 你可以选择将自定义开始布局与 Intune 或其他 MDM 服务配合使用。 有关详细信息，请参阅 [为 MDM (启动布局文件 Intune 和其他) ](#start-layout-file-for-mdm-intune-and-others)。

1. 选择 **"在 S 模式设备中确定目标 Windows 10 设备"**  >  **No**  
   >[!NOTE]  
   > S 模式在 Windows 全息版商业版上不受支持。
1. 选择 "**用户登录类型**"  >  **Azure AD 用户或组**或**用户登录类型**  >  **HoloLens 访问者**，然后添加一个或多个用户组或帐户。  

   只有属于你在 " **用户登录类型** " 中指定的组或帐户的用户才能使用展台体验。

1. 使用以下选项选择一个或多个应用：
   - 若要添加已上载的业务线应用程序，请选择 " **添加应用商店应用** "，然后选择所需的应用。
   - 若要通过指定其 AUMID 添加应用，请选择 " **由 AUMID 添加** "，然后输入应用的 AUMID。 [查看可用的 Aumid 列表](#aumids)

下一步是将配置文件 [分配](#mdmassign) 给组。

### <a id="mdmassign"></a>MDM，步骤 4 &ndash; 将展台配置文件分配到组

使用展台配置文件的 " **分配** " 页面设置要在其中部署 kiosk 配置的位置。 在最简单的情况下，你将展台配置配置文件分配给将在使用 MDM 注册设备时包含 HoloLens 设备的组。

### <a id="mdmsingledeploy"></a>MDM、步骤 5 (单应用) &ndash; 部署单应用展台

使用 MDM 系统时，可以在 OOBE 期间在 MDM 中注册设备。 在 OOBE 完成后，登录到设备非常简单。

在 OOBE 期间，请按照下列步骤操作：

1. 使用在展台配置文件中指定的帐户登录。
1. 注册设备。 请确保将设备添加到将设备配置文件分配到的组。
1. 等待 OOBE 完成，针对要下载和安装的应用商店应用以及要应用的策略。 然后重新启动设备。

下次登录设备时，展台应用应自动启动。

如果此时看不到展台配置，请 [检查作业状态](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。

### <a id="mdmmultideploy"></a>MDM、步骤 5 (多应用) &ndash; 部署多应用展台

使用 MDM 系统时，你可以将设备加入 Azure AD 租户，并在 OOBE 期间在 MDM 中注册设备。 如果适用，请向用户提供注册信息，以便用户可以在 OOBE 过程中使用它。

> [!NOTE]  
> 如果您已将展台配置文件分配给包含用户的组，请确保其中一个用户帐户是登录到该设备的第一个帐户。

在 OOBE 期间，请按照下列步骤操作：

1. 使用属于 " **用户登录类型** " 组的帐户登录。
1. 注册设备。
1. 等待所有属于展台配置文件的应用下载并安装。 此外，请等待应用策略。  
1. 在 OOBE 完成后，你可以通过 Microsoft store 或通过旁加载来安装其他应用。 设备所属的组自动安装[所需的应用](https://docs.microsoft.com/mem/intune/apps/apps-deploy#assign-an-app)。
1. 安装完成后，重新启动设备。

下次使用属于 **用户登录类型**的帐户登录设备时，展台应用应自动启动。

如果此时看不到展台配置，请 [检查作业状态](https://docs.microsoft.com/intune/configuration/device-profile-monitor)。

## 使用预配包设置单应用或多应用展台

若要使用预配包设置展台模式，请按照下列步骤操作。

1. [创建一个定义展台配置的 XML 文件](#ppkioskconfig)，包括 "开始" [布局](#start-layout-for-hololens)。
2. [将 XML 文件添加到预配包。](#ppconfigadd)
3. [将预配包应用于 HoloLens。](#ppapply)

### <a id="ppkioskconfig"></a>预配程序包，步骤 1 &ndash; 创建展台配置 XML 文件

按照 [常规说明为 Windows 桌面版创建展台配置 XML 文件](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file)，但以下内容除外：

- 不要在 Win32) 中包括经典 Windows 应用程序 (。 HoloLens 不支持这些应用程序。
- 使用适用于 HoloLens 的 [占位符开始布局 XML](#start-layout-for-hololens) 。
- 可选：将来宾访问添加到展台配置

#### <a id="ppkioskguest"></a>可选：将来宾访问添加到展台配置

在 XML 文件的 "配置" 部分中，可以将名为 "**访问者**" 的特殊组配置为允许来宾使用展台。 [ **Configs** ](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configs) 当展台配置为支持 **访问者** 特殊组时，登录页面中将添加一个 "**来宾**" 选项。 **来宾**帐户不需要密码，并且与帐户关联的任何数据在帐户注销时都将被删除。

若要启用 **来宾** 帐户，请将以下代码片段添加到展台配置 XML：

```xml
<Configs>
  <Config>  
    <SpecialGroup Name="Visitor" />  
    <DefaultProfile Id="enter a profile ID"/>  
  </Config>  
</Configs>  
```

#### <a id="start-layout-for-hololens"></a>HoloLens 的占位符开始布局

如果使用 [预配包](#use-a-provisioning-package-to-set-up-a-single-app-or-multi-app-kiosk) 配置多应用展台，则该过程需要 "开始" 布局。 Windows 全息版中不支持 "开始布局自定义"。 因此，你必须使用占位符开始布局。

> [!NOTE]  
> 由于单应用展台在用户登录时启动展台应用，因此它不使用 "开始" 菜单，也不需要具有 "开始" 布局。

> [!NOTE]  
> 如果使用 [MDM](#use-microsoft-intune-or-other-mdm-to-set-up-a-single-app-or-multi-app-kiosk) 设置多应用展台，则可以选择使用 "开始" 布局。 有关详细信息，请参阅 [MDM (Intune 和其他) 的占位符启动布局文件 ](#start-layout-file-for-mdm-intune-and-others)。

对于 "开始" 布局，将以下 **StartLayout** 部分添加到展台预配 XML 文件：

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

#### <a id="start-layout-file-for-mdm-intune-and-others"></a>适用于 MDM (Intune 和其他人的占位符开始布局文件) 

将以下示例另存为 XML 文件。 在 Microsoft Intune 中配置多应用展台时，你可以使用此文件 (或在提供展台配置文件的其他 MDM 服务中使用此文件) 。

> [!NOTE]
> 如果必须使用自定义设置和完整的 XML 配置来设置 MDM 服务中的展台，请使用 [预配包的启动布局说明](#start-layout-for-hololens)。

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

### <a id="ppconfigadd"></a>Prov. 程序包，步骤 2 &ndash; 将 kiosk 配置 XML 文件添加到预配包

1. 打开 [Windows 配置设计器](https://www.microsoft.com/store/apps/9nblggh4tx22)。
1. 选择 " **高级设置**"，输入项目的名称，然后选择 " **下一步**"。
1. 选择 " **Windows 10 全息**版"，然后选择 " **下一步**"。
1. 选择 " **完成**"。 此时将打开你的程序包的工作区。
1. 选择 "**运行时设置**"  >  **AssignedAccess**  >  **MultiAppAssignedAccessSettings**。
1. 在中心窗格中，选择 " **浏览** "，找到并选择您创建的展台配置 XML 文件。

   ![Windows 配置设计器中的 MultiAppAssignedAccessSettings 字段的屏幕截图](./images/multiappassignedaccesssettings.png)

1. **可选**。  (如果你希望在设备的初始设置之后应用预配程序包，并且在展台设备上已有管理员用户，请跳过此步骤。 ) 选择 " **运行时设置** &gt; **帐户** &gt; **用户**"，然后创建用户帐户。 提供用户名和密码，然后选择 " **UserGroup**  >  **管理员**"。  
  
     通过使用此帐户，你可以查看预配状态和日志。  
1. **可选**。  (如果在展台设备上已有非管理员帐户，请跳过此步骤。 ) 选择 " **运行时设置** &gt; **帐户** &gt; **用户**"，然后创建一个本地用户帐户。 请确保用户名与你在配置 XML 中指定的帐户相同。 选择 " **UserGroup**  >  **标准用户**"。
1. 选择**File**"  >  **保存**文件"。
1. 选择 "**导出**  >  **预配包**"，然后选择 "**所有者**  >  **IT 管理员**"。这会将此预配包的优先级设置为高于从其他源应用到此设备的预配包。
1. 选择**下一步** 。
1. 在 " **预配程序包安全** " 页面上，选择一个安全选项。
   > [!IMPORTANT]  
   > 如果选择 " **启用包签名**"，还必须选择用于对程序包进行签名的有效证书。 若要执行此操作，请选择 " **浏览** "，然后选择要用于对程序包进行签名的证书。
   
   > [!CAUTION]  
   > 不要选择 " **启用包加密**"。 在 HoloLens 设备上，此设置会导致预配失败。
1. 选择**下一步** 。
1. 指定在构建预配包时希望该预配包转到的输出位置。 默认情况下，Windows 配置设计器使用项目文件夹作为输出位置。 如果要更改输出位置，请选择 " **浏览**"。 完成后，选择 " **下一步**"。
1. 选择 " **生成** " 开始构建程序包。 无需花费太长时间即可生成预配包。 "生成" 页面显示项目信息，进度栏指示生成状态。

### <a id="ppapply"></a>预配程序包，步骤 3 &ndash; 将预配包应用于 HoloLens

"使用预配包配置 HoloLens" 一文提供了在以下情况下应用预配包的详细说明：

- 在安装期间，您最初可以 [将预配包应用于 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-during-setup)。

- 您还可以 [在安装完成后将预配包应用于 HoloLens](hololens-provisioning.md#apply-a-provisioning-package-to-hololens-after-setup)。

## 使用 Windows Device Portal 设置单应用展台

若要使用 Windows Device Portal 设置展台模式，请按照下列步骤操作。

> [!IMPORTANT]
> 展台模式仅在设备安装了 [Windows 全息版企业](hololens1-upgrade-enterprise.md) 版时可用。

1. [将 HoloLens 设备设置为使用 Windows Device Portal](https://developer.microsoft.com/windows/mixed-reality/using_the_windows_device_portal#setting_up_hololens_to_use_windows_device_portal)。 Device Portal 是 HoloLens 上的 Web 服务器，你可以从电脑上的 Web 浏览器连接到它。

    > [!CAUTION]
    > 将 HoloLens 设置为使用 Device Portal 时，必须在设备上启用开发人员模式。 具有 Windows 全息版企业版的设备上的开发人员模式使你能够使用面加载应用。 但是，此设置会创建一个风险，用户可以安装 Microsoft Store 尚未认证的应用。 管理员可以通过使用[策略 CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)中的**ApplicationManagement/AllowDeveloper 解锁**设置阻止启用开发人员模式的功能。 [了解有关开发人员模式的详细信息。](https://docs.microsoft.com/windows/uwp/get-started/enable-your-device-for-development#developer-mode)
    
1. 在计算机上，使用 [wi-fi](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_wi-fi) 或 [USB](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#connecting_over_usb)连接到 HoloLens。

1. 执行下列操作之一：
   - 如果您是首次连接到 Windows Device Portal，请 [创建用户名和密码](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#creating_a_username_and_password)
   - 输入您以前设置的用户名和密码。

    > [!TIP]
    > 如果发现浏览器中的证书错误，请遵循[以下疑难解答步骤](https://developer.microsoft.com/windows/mixed-reality/Using_the_Windows_Device_Portal#security_certificate)。

1. 在 Windows Device Portal 中，选择 " **展台模式**"。

1. 选择 " **启用展台模式**"，选择要在设备启动时运行的应用，然后选择 " **保存**"。

    ![展台模式](images/kiosk.png)
1. 重新启动 HoloLens。 如果您的设备门户页面仍处于打开状态，则可以在页面顶部选择 " **重新启动** "。

## 详细信息

观看如何使用预配包配置展台。  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/fa125d0f-77e4-4f64-b03e-d634a4926884?autoplay=false]
