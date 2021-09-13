---
title: 将 HoloLens 设置为网亭
description: 了解如何设置和使用展台配置来锁定 HoloLens 设备上的应用。
ms.prod: hololens
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.date: 8/24/2021
ms.custom:
- CI 115262
- CI 111456
- CSSTroubleshooting
ms.reviewer: ''
manager: laurawi
appliesto:
- HoloLens (1st gen)
- HoloLens 2
ms.openlocfilehash: e856ac74e959743e8d05ea6acf583700a6450373
ms.sourcegitcommit: e9f746aa41139859edc12fbc21f926c9461da4b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2021
ms.locfileid: "126032077"
---
# <a name="set-up-hololens-as-a-kiosk"></a>将 HoloLens 设置为网亭

## <a name="what-is-kiosk-mode"></a>什么是展台模式？

展台模式是一项功能，可在用户登录到 HoloLens 时控制在 "开始" 菜单中显示哪些应用程序。 支持以下两种方案：

1. **单应用展台模式** –当用户登录时，不会显示 "开始" 菜单，并且会自动启动单个应用。 <br> *示例使用*：仅运行 Dynamics 365 Guides 应用的设备。
2. **多应用展台模式**– "开始"菜单仅显示用户登录时在展台配置中指定的那些应用程序。 如果需要，可以选择自动启动应用。 <br> *示例使用*：仅在 "开始" 菜单中显示应用商店应用、反馈中心和设置应用的设备。

    <img alt="Multi app kiosk example" src=".\images\multi-app-kiosk.jpg" width="411" height="500" />

## <a name="description-of-kiosk-mode-experience-when-a-user-signs-in"></a>用户登录时展台模式体验的说明

下表列出了不同展台模式下的功能。

| &nbsp; |“开始”菜单 |快速操作菜单 |照相机和视频 |Miracast |Cortana |内置语音命令 |
| --- | --- | --- | --- | --- | --- | --- |
|单应用展台 |已禁用 |已禁用 |已禁用 |已禁用   |已禁用 |能够 |
|多应用展台 |Enabled |能够  |即可  |即可 |即可   |能够  |

\*有关如何启用禁用功能的详细信息，或语音命令如何与禁用的 Cortana 功能进行交互的详细信息，请参阅[HoloLens AUMIDs for apps](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)。

## <a name="key-general-considerations-before-configuring-kiosk-mode"></a>配置展台模式之前的重要一般注意事项

1. 确定在你的环境中登录 HoloLens 的用户帐户的类型-HoloLens 支持 Azure Active Directory (AAD) 帐户、Microsoft 帐户 (MSA) 和本地帐户。 此外，也 (仅为 AAD 联接设备) 提供名为 "来宾/访问者" 的暂时创建的帐户。 有关详细信息[，请参阅管理用户标识和登录 HoloLens](hololens-identity.md)。
2. 确定展台模式体验的目标–无论是每个人、单个用户、特定用户还是 AAD 组 () 等成员的用户。
3. 对于多个 app 展台模式，确定要显示在 "开始" 菜单上的应用程序 () 。 对于每个应用程序，都需要 [ (AUMID) 的应用程序用户模型 ID ](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids) 。
4. 确定是否通过运行时预配包或移动设备管理 (MDM) 服务器将展台模式应用于 HoloLens。

## <a name="security-considerations"></a>安全注意事项

展台模式不应被视为一种安全方法，而是作为控制用户登录启动体验的一种方法。 如果有特定的安全相关要求，你可以将展台模式体验与下面所述的选项结合：

- 如果将设置应用配置为以展台模式显示，并且想要控制在设置应用中显示哪些页面，请参阅[设置可见性页面](settings-uri-list.md)
- 要控制某些硬件功能（例如，照相机、蓝牙等）对某些应用程序的访问权限时，请参阅[HoloLens 2 Windows 客户端管理支持的策略 CSP 中的策略](/windows/client-management/mdm/policies-in-policy-csp-supported-by-hololens2)。 可以查看常见的 [设备限制](hololens-common-device-restrictions.md) 。
- 展台模式不会阻止 (配置为展台体验的一部分) 启动其他应用程序。 如果要在 HoloLens 上完全阻止启动某些应用/进程，请参阅在[Microsoft Intune 中的 HoloLens 2 设备上使用 Windows Defender 应用程序控制](/mem/intune/configuration/custom-profile-hololens)

## <a name="key-technical-considerations-for-kiosk-mode-for-hololens"></a>HoloLens 的展台模式的关键技术注意事项

仅适用于计划使用运行时预配包或手动创建展台配置的情况。 展台模式配置使用基于 XML 的层次结构：

- 分配的访问配置文件定义在展台模式下的 "开始" 菜单中显示哪些应用程序。 可以在同一个 XML 结构中定义多个配置文件，稍后可以引用这些配置文件。
- 分配的访问配置引用该配置文件的配置文件和目标用户 () 例如特定用户、AAD 组或访问者等。您可以根据使用方案的复杂性，在同一 XML 结构中定义多个配置 (参阅下面) 的 "支持的方案" 部分。
- 若要了解详细信息，请参阅 [ASSIGNEDACCESS CSP](/windows/client-management/mdm/assignedaccess-csp)。

## <a name="supported-scenarios-for-kiosk-mode-based-on-identity-type"></a>基于标识类型的展台模式支持的方案

请参阅基于方案的示例 [引用链接](hololens-kiosk-reference.md#kiosk-xml-code-samples) ，并在复制粘贴之前根据需要进行更新。

> [!NOTE]
> 仅当不使用 Intune 的 UI 创建展台配置时才使用 XML。

### <a name="for-users-who-sign-in-as-either-local-account-or-msa"></a>对于以本地帐户或 MSA 身份登录的用户

| **Desired 展台体验** | **推荐的展台配置** | **配置方式**  | **备注** |
| --- | --- | --- | --- |
| 每个登录用户都会获得展台体验。 | [配置多个应用全局分配的访问配置文件](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune 自定义模板](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [运行时预配-多个应用](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | 全局分配的访问权限需要 [20H2 和更新版本](hololens-release-notes.md#windows-holographic-version-20h2) |
| 登录的特定用户获取展台体验。  | [根据需要配置单个或多个应用分配的访问配置文件 () 指定特定用户的名称。](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-a-local-account-or-aad-user-account) | [请参阅下面支持的选项。](#steps-in-configuring-kiosk-mode-for-hololens) | 对于单应用展台模式，HoloLens 仅支持本地用户帐户或 MSA 帐户。 <br> 对于多个 app 展台模式，HoloLens 仅支持 MSA 帐户或 AAD 帐户。 |

### <a name="for-users-who-sign-in-as-aad-account"></a>对于以 AAD 帐户登录的用户

| **Desired 展台体验** | **推荐的展台配置** | **配置方式** | **备注** |
| --- | --- | --- | --- |
| 每个登录用户都会获得展台体验。 | [配置多个应用全局分配的访问配置文件](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile) | • [Microsoft Intune 自定义模板](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [运行时预配-多个应用](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | 全局分配的访问权限需要 [20H2 和更新版本](hololens-release-notes.md#windows-holographic-version-20h2) |
| 登录的每个用户都可以获得展台体验，某些用户除外。 | [配置多个应用全局分配的访问配置文件，方法是将必须是设备所有者) 的某些用户排除 (](hololens-kiosk-reference.md#multiple-app-global-assigned-access-profile-excluding-device-owners)。 | • [Microsoft Intune 自定义模板](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [运行时预配-多个应用](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | 全局分配的访问权限需要 [20H2 和更新版本](hololens-release-notes.md#windows-holographic-version-20h2) |
| 每个 AAD 用户获取特定于该用户的单独展台体验。 | [为每个指定其 AAD 帐户名称的用户配置分配的访问配置。](hololens-kiosk-reference.md#multiple-app-assigned-access-profiles-for-two-aad-users-or-more) | • [Microsoft Intune 自定义模板](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [运行时预配-多个应用](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | &nbsp; |
| 不同 AAD 组中的用户体验到仅适用于其组的展台模式。 | [为每个所需的 AAD 组配置分配的访问配置。](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-two-aad-groups-or-more) | • [Microsoft Intune 自定义模板](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [运行时预配-多个应用](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens) | •当用户登录并且 HoloLens 与 Internet 连接时，如果发现该用户是其 kiosk 配置所在的 AAD 组的成员，则用户将获得该 aad 组的体验展台。 <br> •当[用户登录时，如果没有可用的 internet，用户将会遇到 HoloLens 失败模式行为。](#issue---no-apps-are-shown-in-start-menu-in-kiosk-mode) <br> • 如果用户登录时不保证 Internet 可用性，并且需要使用基于 AAD 组的展台，请考虑 [使用 AADGroupMembershipCacheValidityInDayspolicy](hololens-release-notes.md#cache-azure-ad-group-membership-for-offline-kiosk)。 <br> • 为了在登录期间获得最佳 AAD 组体验，建议使用 [AADGroupMembershipCacheValidityInDayspolicy](/hololens/hololens-release-notes#cache-azure-ad-group-membership-for-offline-kiosk) |
| 出于临时目的需要HoloLens用户会获得展台体验。 | [为访问者配置分配的访问配置](hololens-kiosk-reference.md#multiple-app-assigned-access-profile-for-visitors) | • [Microsoft Intune自定义模板](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens) <br> • [运行时预配 - 单个应用](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens) | • 临时用户帐户由用户登录HoloLens创建，在临时用户注销时删除。 <br> • 考虑启用 [访问者自动登录策略](#how-can-visitor-accounts-automatically-logon-to-kiosk-experience)。 |

## <a name="steps-in-configuring-kiosk-mode-for-hololens"></a>为用户配置展台模式HoloLens

可以按照以下方式创建和应用展台配置：

1. 使用 MDM 服务器的 UI（例如 Intune 的展台模板）或自定义 OMA-URI 配置，这些配置随后会远程应用于 HoloLens。
2. 使用运行时预配包，然后直接应用于HoloLens。

下面是以下配置方法，选择与要使用的进程匹配的选项卡。

1. [Microsoft Intune应用展台模板](hololens-kiosk.md?tabs=uisak#steps-in-configuring-kiosk-mode-for-hololens)
2. [Microsoft Intune多应用展台模板](hololens-kiosk.md?tabs=uimak#steps-in-configuring-kiosk-mode-for-hololens)
1. [Microsoft Intune自定义模板](hololens-kiosk.md?tabs=intunecustom#steps-in-configuring-kiosk-mode-for-hololens)
1. [运行时预配 - 多应用](hololens-kiosk.md?tabs=ppkgmak#steps-in-configuring-kiosk-mode-for-hololens)
1. [运行时预配 - 单个应用](hololens-kiosk.md?tabs=ppkgsak#steps-in-configuring-kiosk-mode-for-hololens)

[!INCLUDE[](includes/kiosk-configure-steps.md)]

## <a name="frequently-asked-questions"></a>常见问题

### <a name="how-can-visitor-accounts-automatically-logon-to-kiosk-experience"></a>访问者帐户如何自动登录到展台体验？

在[Holographic Windows版本 21H1 及之后](hololens-release-notes.md#windows-holographic-version-21h1)的版本上：

- AAD 和非 ADD 配置都支持为展台模式启用自动登录的访问者帐户。

[!INCLUDE[](includes/kiosk-autologin.md)]

### <a name="is-kiosk-experience-supported-on-hololens-1st-gen"></a>第一代HoloLens (是否支持展台) ？

展台模式仅在设备已启动时Windows Holographic for Business。 所有HoloLens 2设备都随 Windows Holographic for Business一起提供，并且没有其他版本。 每个HoloLens 2设备都能开箱即用地运行展台模式。

HoloLens (第一代) 需要同时升级 OS 内部版本和 OS 版本。 下面是有关将第一代HoloLens (更新到) 版本[Windows Holographic for Business详细信息。](hololens1-upgrade-enterprise.md) 若要将 HoloLens (gen) 设备更新为使用展台模式，必须先确保该设备运行 Windows 10 版本 1803 或更高版本。 如果已使用 Windows 设备恢复工具将 HoloLens (第一代) 设备恢复到其默认内部版本，或者安装了最新更新，则设备已准备好进行配置。

### <a name="how-to-use-device-portal-to-configure-kiosk-in-non-production-environments"></a>如何使用设备门户在非生产环境中配置展台？

将 HoloLens[设置为使用 Windows 设备门户。](/windows/mixed-reality/using-the-windows-device-portal#setting-up-hololens-to-use-windows-device-portal) Device Portal 是 HoloLens 上的 Web 服务器，你可以从电脑上的 Web 浏览器连接到它。

 > [!CAUTION]
 > 将 HoloLens 设置为使用 设备门户 时，必须启用设备上开发人员模式。 使用设备上具有Windows Holographic for Business模式，可以旁加载应用。 但是，此设置会创建一个风险，即用户可能会安装尚未通过 Microsoft Store。 管理员可以使用策略 CSP 中的 **ApplicationManagement/AllowDeveloper Unlock** 设置阻止启用开发人员 [模式](/windows/client-management/mdm/policy-configuration-service-provider)。 [了解有关开发人员模式的详细信息。](/windows/uwp/get-started/enable-your-device-for-development#developer-mode)

展台模式可以通过 设备门户 的 REST API 进行 POST 设置，对 /api/holographic/kioskmode/settings 执行 POST 操作，其中一个必需的查询字符串参数 ("kioskModeEnabled"的值为"true"或"false") ，以及一个可选参数 ("startupApp"，其值为包名称) 。 请记住，设备门户仅适用于开发人员，不应在非开发人员设备上启用。 未来REST API更新/版本中可能会更改该版本。

## <a name="troubleshooting"></a>疑难解答

### <a name="issue---no-apps-are-shown-in-start-menu-in-kiosk-mode"></a>问题 - 展台模式下的"开始"菜单中未显示任何应用

**现象**

应用展台模式时遇到故障时，会出现以下行为：

- 在 Windows全息版 20H2 - HoloLens将在该版本中显示"开始"菜单。
- Windows全息版 20H2 - 如果设备具有展台配置（这是全局分配的访问权限和 AAD 团队成员分配的访问权限的组合）时，如果确定 AAD 组成员身份失败，用户将看到"开始"菜单中的"未显示任何内容"。

    ![当展台模式发生故障时，其外观的图像。](images/hololens-kiosk-failure-behavior.png )

- 从[Holographic Windows版本 21H1](hololens-release-notes.md#windows-holographic-version-21h1)开始，展台模式在显示空的开始菜单之前查找"全局分配的访问权限"。 如果 AAD 组展台模式 (失败，) 展台体验将回退到全局展台配置模式。

**故障排除步骤**

- 验证是否正确指定了应用的 AUMID，并且它不包含版本。 有关示例HoloLens请参阅收件箱应用的[AUMID。](hololens-kiosk-reference.md#hololens-application-user-model-ids-aumids)
- 确保为该用户在设备上安装了应用程序。
- 如果展台配置基于 AAD 组，请确保 AAD 用户登录时存在 Internet 连接。 如果需要，请配置 [MixedReality/AADGroupMembershipCacheValidityInDays](/windows/client-management/mdm/policy-csp-mixedreality#mixedreality-aadgroupmembershipcachevalidityindays) 策略，以便无需 Internet 即可正常运行。

### <a name="issue---building-a-package-with-kiosk-mode-failed"></a>问题 - 使用展台模式生成包失败

**现象**

将显示如下所示的对话框。

<kbd>
    <img alt="Kiosk failure to build" src="./images/kiosk-steps/kiosk-ppkg-failure.png"/>
</kbd>

**故障排除步骤**

1. 单击上方对话框中显示的超链接。
1. 在文本编辑器中打开 ICD.log，其内容应指示错误。

> [!NOTE]
> 如果已多次尝试，请检查日志中的时间戳。 这将帮助你仅检查当前问题。

### <a name="issue--provisioning-package-built-successfully-but-failed-to-apply"></a>问题 – 预配包已成功生成，但无法应用。

**现象**

在 Hololens 上应用预配包时显示错误

**故障排除步骤**

1. 浏览到运行时Windows配置设计器项目存在的文件夹。
1. 打开 ICD.log，并确保在生成预配包时日志中没有错误。 某些错误在生成期间未显示，但仍记录在 ICD.log 中

### <a name="issue--multiple-app-assigned-access-to-aad-group-does-not-work"></a>问题 - 对 AAD 组的多个应用分配的访问权限不起作用

**现象**

在 AAD 用户登录时，设备不会进入展台模式

**故障排除步骤**

- 在"分配的访问权限配置 XML"中，确认使用了已登录用户为 的 AAD 组的 GUID，而不是 AAD 用户的 GUID。
- 确认在 Intune 门户中，AAD 用户确实显示为目标 AAD 组的成员。
